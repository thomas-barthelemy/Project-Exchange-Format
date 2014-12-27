Projects and Issues Exchange Format v1.0
=======================

A JSON-based data exchange format for Project and Issue tracking systems meant to be used a standard.

Introduction
===

The number of project and issue tracking system is fastly growing but this fastly evolving environment
lacks of a common data structure to exchange projects, issues (tasks, bugs...)
which results in little to no interoperability.

**The Projects and Issues Exchange Format** aims to provide a common format for exchanging data between
the existings platforms that could be exposed via APIs or as an export/import format.

Scope
===

**The Projects and Issues Exchange Format** targets Project and Issue tracking system.

This document specifies the exchange format for Projects and Issues,
including their respecting fields and fields type.

Terms and Definitions
===

    API: Application Program Interface.
    JSON: JavaScript Object Notation, a lightweight data-interchange format.
    PIEF: Projects and Issues Exchange Format, defined in this document.

Normative References
===

RFC 2119
====
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and
"OPTIONAL" in this document are to be interpreted as described in
RFC 2119.

http://www.ietf.org/rfc/rfc2119.txt

Date, Time and Duraction
====

* Dates should be formatted as recommended by RFC 3339.
* Time durations should be formatted as recommended by ISO 8601.

General Exchange Format
===

* The platform serving the data (via API and/or export) MUST propose at least the JSON format.
* Data MAY be proposed in other format than JSON as an option.
* When a field is required but countains no data in JSON, it MUST use the **null** JSON value.
* An un-set, unknown or empty field MUST NOT use an empty string.

Fields
====
This part of the requirements specifies the root fields of the data format.

* MUST have a **projects** field as an Array of containing the list of projects as Objects.
* MUST have a **issues** field as an Array containing the list of issues as Objects.
* SHOULD have a **version** field as a string representing the version of the PIEF used to create the data.
* SHOULD have a **exportDate** field as a string representing the data creation date.
* SHOULD have a **exportOrigin** field as an Object providing information on the tool or platform that generated the data.

Export Origin
===
The part of the requirements specifies the fields of the **exportOrigin** Object definied at the root

* MUST have a **name** field representing the name of the tool or platform that generated the data.
* SHOULD have a **version** field representing the version of the tool or platform that generated the data.

Project
===

* MUST have a **name** field as a string representing the project name.
* MUST have an **id** field as a string representing the project unique identifier. 
* SHOULD have a **description** field as a string representing the project description.
* SHOULD have a **parentId** field as a string representing the unique identifier of the parent project (if any).
* SHOULD have a **authorId** field as a string representing the unique identifier of 
* SHOULD have a **creationDate** field as a string representing the project creation date.
* SHOULD have a **lastUpdate** field as a string representing the project last update date.

Issue
===
