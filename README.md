# Bootstrapping and Open-Source Friendly (BOOS-FL) license

Copyright 2020 Uprtcl Exective DAO, Inc

> ## Warning: This document is under construction

# PREAMBLE

The idea behind this license is simple: successfull and commercially viable applications should trickle down their benefits to the companies and developers of the software components they are built upon. At the same time, software licenses should not stiffle innovation and create artificial barries in the path of hackers, startups, students and developers who are just getting started.

We solve this by creating a license that let's people and organizations use this software for commercial applications and pay for it in the future, only if their endeavor is successful. The license uses the public Ethereum blockchain to streamline the license registration and payment process that completely reduces bureacracy.

# THE LICENSE

This software is intended to be used as a library on other applications.

You need a license to use this software as part of your application (YOUR APPLICATION) with the following exceptions:

1. YOUR APPLICATION code is licensed using a FOSS copyleft license like GPL or AGPL.
2. YOUR APPLICATION is not for commercial use.

If YOUR APPLICATION is licensed under an MIT, APACHE, or other similar permissive FOSS license, you cannot use this software.

If YOUR APPLICATION has reserved copyrights and is intended for commercial use, you then have to buy a license from us in order to use this software as part of YOUR APPLICATION. The payment of this license can be postponed for a maximum period of 4 years and the price to pay will depend on how long you decide to postpone it.

You can install and test this software as part of YOUR APPLICATION for a period of 1 month, after which time you MUST register its use on the smart contract (see below) if you want to continue using the software.

To register YOUR APPLICATION you shall call the method `register(bytes32 packageHash,bytes32 organizationHash)` of the `licensing.uprtcl.eth` smart contract, where `packageHash` should be the sha256 hash of the name of the node package of YOUR APPLICATION, and organization should be the sha256 hash of the name of the legal entity with copyrights on YOUR APPLICATION.

Once registered you can use this software without any upfront payment. However, by registering you are commit to paying for the license as soon as you decide to do it and within a period of 4 years. Remeber, if you register, you are commiting to pay for the license as long as you keep using this software in YOUR APPLICATION.

The price, in DAI, for buying a license of this software can be calculated by calling the method `getPrice(bytes32 packageHash, bytes32 organizationHash)` of the smart contract. This price will change in time, starting at a minimum value on the date you registered the application and reaching a maximum value after 4 years.

The sooner you decide to buy the license, the cheaper it will be. Payment can be done automatically by calling the method `pay(bytes32 packageHash, bytes32 organizationHash, address account)`. This method will debit the price in DAI from the specified Ethereum `account`. You can get the price you have to pay at a given point in time, past or future, by calling the `getPrice(bytes32 packageHash, bytes32 organizationHash, uint256 timestamp)` method of the smart contract.

If you have not paid for the license before the expiration date of 4 years, you must stop using this software as part of YOUR APPLICATION.

Some clarifications

- The payment obligation is acquired based on YOUR APPLICATION development, not on YOU as a person, company or legal entity. This means that

  - If your organization stops developing YOUR APPLICATION, and, thus, this software, you can safely omit the payment of this license.
  - If you are using this software in two different applications under the same organization, you must buy one license for each application.
  - If your organization sells the copyrights of YOUR APPLICATION to a third party, that third party will still have to pay for this license without any modifications to the registration date.
  - If your organization is disolved or stop existing, you can safely omit the payment of this license.
  - If you were bootstrapping and never ended up registering a company or becoming a commercially viable startup, you can safely omit the payment of this license.

- If after 4 years YOUR APPLICATION is no longer under active development and is not being used, you can safely omit the payment of this license.

- If you decide to stop using this software in YOUR APPLICATION, but continue developing YOUR APPLICATION, you can unregister the license by calling the `unregister(bytes32 packageHash,bytes32 organizationHash)` method of the smart contract. This will explicitely free you from any payment obligations and it will also prevent you from using this software on YOUR APPLICATION.
