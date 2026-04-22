# Gri Sustainability Taxonomy Architecture And Implementation Guide 10

# The GRI Sustainability Taxonomy Architecture and Implementation

# Guide

## Last updated: 19th June 2025

© GRI 2025

## Table of Contents

- Introduction to GRI .... 3

  - 1.1 GRI and its mission .... 3

  - 1.2 The GRI Standards and its main features .... 3

  - 1.3 Impact and financial sustainability disclosures .... 5

- Why is GRI developing an XBRL taxonomy? .... 6

- Understanding the Structure of the GRI Standards .... 8

- The GRI Sustainability Taxonomy Architecture .... 11

4.1
- Considerations for determining the Taxonomy Architecture .... 11

  - 4.2 Folder Structure .... 11

  - 4.3 Taxonomy Package .... 12

  - 4.4 Approaches used for data modelling in the Taxonomy .... 13

  - 4.5 Element grouping in the Taxonomy .... 17

- Reporting Material Topics and Omissions .... 19

- Technical features .... 21

  - 6.1 Categorical Elements – Extensible Enumerations .... 21

  - 6.2 Categorical Elements – BooleanItemType .... 22

  - 6.3 Different Datatypes used across the Taxonomy .... 22

  - 6.4 Use of specific labels within the Taxonomy .... 23

  - 6.5 Tagging of intensity ratios .... 24

- Validation rules .... 26

  - 7.1 Modelling of validation rules in formula linkbase .... 26

- Use of Unit Type Registry .... 28

- Appendix A: XBRL Glossary .... 29

© GRI 2025

1 Introduction to GRI

## 1.1 GRI and its mission

Established in 1997, GRI (Global Reporting Initiative) is an independent, international not for profit organization that helps businesses and other organizations take responsibility for their impacts by providing them with the global common language to communicate those impacts – the GRI Standards, which are provided as a free public good for use by reporting organizations.

GRI envisions a sustainable future enabled by transparency and open dialogue about impacts. This is a future in which reporting on impacts is common practice by all organizations around the world. By better understanding, managing and disclosing their impacts, organizations can unlock benefits that inform decisions, reduce risks, improve business opportunities and strengthen stakeholder relationships, and enables organizations to demonstrate their contributions towards sustainable development.

GRI works with its partners, businesses, investors, policymakers, civil society, labor organizations and other experts to develop the GRI Standards and promote their use around the world. They are the first global reporting standards to fully reflect the due diligence expectations for sustainability impacts, including on human rights, as set out in intergovernmental instruments by the UN and OECD.

The GRI Standards have been developed by the Global Sustainability Standards Board (GSSB) through a rigorous, independent, multi-stakeholder, transparent process, in the public interest, that ensures reporting requirements reflect and align with the requirements of authoritative intergovernmental instruments.

Today, more than 14,000 organizations around the world use GRI for their sustainability reporting. It is estimated that 78% of the world’s biggest 250 companies by revenue have adopted the GRI Standards for sustainability reporting, and there are 128 countries with national or jurisdictional policies that reference the GRI Standards.

## 1.2 The GRI Standards and its main features

The GRI Standards are a modular system of interconnected standards organized into three series: the GRI Universal Standards, GRI Sector Standards, and GRI Topic Standards, see Figure 1.1.

The Universal Standards are used by all organizations when reporting in accordance with the GRI Standards. Organizations use the Sector Standards according to the sectors in which they operate, and the Topic Standards according to their list of material topics. Further information about each of these series of the GRI Standards is included below: - Universal Standards The Universal Standards are composed of three Standards: GRI 1, GRI 2 and GRI 3. The purpose and content of these Standards are set out below: GRI 1: Foundation 2021 introduces the purpose and system of GRI Standards and explains key concepts for sustainability reporting. It also specifies the requirements and reporting principles that the organization must comply with to report in accordance with the GRI Standards. GRI 2: General Disclosures 2021 contains disclosures that the organization uses to provide information about its reporting practices and other organizational details, such as its activities,

**[Figure: The modular structure of the GRI Standards]**

Type: diagram

Description: This diagram illustrates the modular structure of the GRI Standards, which are organized into three main categories: Universal Standards, Sector Standards, and Topic Standards. The Universal Standards provide a foundation for reporting, while the Sector Standards apply to specific sectors, and the Topic Standards cover various material topics.

Key Elements:

* Universal Standards -> Provide a foundation for reporting
* Sector Standards -> Apply to specific sectors
* Topic Standards -> Cover various material topics

This diagram provides a clear overview of the GRI Standards' structure, highlighting the different components and their relationships. It serves as a useful tool for understanding the framework and its application in sustainability reporting.

governance, and policies. This information gives insight into the profile and scale of the organization and provides a context for understanding the organization’s impacts. GRI 3: Material Topics 2021 provides step-by-step guidance on how to determine material topics (i.e. topics that represent the organization’s most significant impacts on the economy, environment, and people, including impacts on their human rights). GRI 3 also contains disclosures that the organization uses to report information about its process of determining material topics, its list of material topics, and how it manages each topic.

- Sector Standards The Sector Standards provide information for organizations about their likely material topics. An organization uses the Sector Standards that apply to its sectors to help determine its material topics and what information to report for the material topics. The Sector Standards increase the quality, completeness, and consistency of reporting by organizations within sectors. The GRI Standards currently contain four Sector Standards: GRI 11: Oil and Gas Sector 2021, GRI 12: Coal Sector 2022, GRI 13: Agriculture, Aquaculture and Fishing Sectors 2022 and GRI 14: Mining Sector 2024.
- Topic Standards The Topic Standards contain disclosures for the organization to report information about its impacts in relation to particular topics. The Topic Standards cover a wide range of topics. The organization uses the Topic Standards according to the list of material topics it has determined using GRI 3.

Organizations can choose to either report ‘in accordance’ or ‘with reference’ to the GRI Standards. When organizations report in accordance, they provide a comprehensive picture of their most significant impacts on the economy, environment, and people, including impacts on their human rights, and how they manage these impacts. Organizations report with reference when they cannot comply with all the requirements for reporting in accordance with the GRI Standards or when they use selected GRI Standards, or parts of their content, to report information about specific topics for specific purposes.

The requirements that have to be met for an organization to claim it is reporting in accordance with, or with reference to, the GRI Standards are set out in GRI 1: Foundation 2021, Section 3. Reporting in accordance with the GRI Standards.

## 1.3 Impact and financial sustainability disclosures

The GRI Standards enable organizations to report information about the most significant impacts of their activities and business relationships on the economy, environment, and people, including impacts on their human rights. These impacts are identified and reported using GRI 3: Material Topics 2021. The reported impacts are important to sustainable development and to an organization’s stakeholders, such as investors, workers, customers, or local communities. This perspective is also referred to as ‘impact materiality’. It has been adopted in the European Sustainability Reporting Standards (ESRS) as one of the two dimensions an undertaking needs to report on and is expected to see more widespread adoption in regulatory approaches around the world.

The most significant impacts of an organization can also affect the availability, quality, and affordability of the resources and relationships it depends on. Thus, an organization’s impacts can result in risks and opportunities for the organization.

The risks and opportunities that arise from an organization’s impacts can affect the organization’s business model or strategy and, consequently, its cash flow, access to finance, or cost of capital over the short, medium, or long term. For example, an organization’s high use of non-renewable energy contributes to climate change and could, at the same time, result in increased operating costs due to legislation that seeks to shift energy use toward renewable sources. Nearly all, if not all, of the most significant impacts of an organization, will eventually translate into risks and opportunities. Therefore, understanding these impacts is a necessary first step in identifying risks and opportunities that result from an organization’s impacts.

Information about the risks and opportunities that arise from an organization’s most significant impacts, as well as risks and opportunities that arise from the organization’s dependencies on resources and relationships, are reported under the IFRS Sustainability Disclosure Standards. The material topics and related impacts determined with the GRI Standards provide crucial input for identifying the risks and opportunities that arise from an organization’s impacts.

As a result, use of the GRI Standards and the IFRS Sustainability Disclosure Standards provides a comprehensive overview of an organization’s sustainability-related impacts, risks, and opportunities. The perspectives these standards bring are relevant in their own right and complement each other.

The European Sustainability Reporting Standards have adopted ‘financial materiality’ as the second dimension an undertaking needs to report on. The combination of impact and financial materiality is referred to as ‘double materiality’ under the European Sustainability Reporting Standards.

The GSSB is committed to cooperating with global, national, and other jurisdictional standardsetting bodies, including the IFRS Foundation and EFRAG, to ensure complementarity and interoperability between standards. For more information on the collaboration with the IFRS Foundation and EFRAG, visit https://www.globalreporting.org/public-policy/the-reportinglandscape/.

2 Why is GRI developing an XBRL

# taxonomy?

This is not the first taxonomy GRI has released. In 2013 a taxonomy was developed based on the G4 version of the GRI Guidelines. At the time, however, reporting of sustainability impacts was in an earlier phase and the sector not ready for digital reporting.

Today, however, the landscape has changed. With both the IFRS Sustainability Disclosure Standards and Corporate Sustainability Reporting Directive (CSRD) in the EU supporting reporting using XBRL, reporting organizations will increasingly need to produce their reports in digital format alongside traditional, human readable formats.

There is also an increasing need for consistent, robust sustainability data that digital reporting enables access to. Examples of the potential use of sustainability data include: - allowing reporting organizations to compare themselves to their peers and competitors, as well as track performance against industry benchmarks for important sustainability metrics;

- supporting data-driven decision making by organizations, to improve sustainability strategies and provide the basis for more accurate identification of sustainability-related financial risks and opportunities;
- providing a richer set of evidence on which regulators can design, improve and effectively implement regional sustainability policies;
- enabling robust data to support assessments made by rankers and raters, and allowing investors to better identify companies that align with the sustainability requirements of their portfolios;
- supporting robust auditing of sustainability reports, and
- enabling academic and other research into sustainability topics and trends.

Access to robust data is also essential given the potential use of Generative AI (GenAI) to support the drafting of sustainability reports. While GenAI offers opportunities to reduce the burden of drafting, allowing reporters to focus on improving quality of disclosures instead, it is important that its application is based upon and supported by comprehensive, accurate and robust data.

The GRI Standards provide the ideal basis for developing this sustainability data because: - The GRI Standards are already embedded in sustainability reporting practices, used by more than 14,000 organizations across different countries and sectors, many of whom have reported using GRI over several years. This provides a rich source of existing sustainability data that could, for example, be used for robust benchmarking.

- The GRI Topic Standards provide comprehensive coverage of sustainability topics, including impacts on the economy, environment, and people. This could be used, for example, to investigate correlations between and trends in performance against different topics.
- The GRI Standards are widely recognized by regulators. There are 128 countries with national or jurisdictional policies that reference the GRI Standards.

By digitizing its Standards, therefore, GRI aims to unlock access to sustainability data in a way that benefits the entire reporting community.

Digitally formatted reports filed with GRI will also be subject to validation checks, which will enable reporters to check that they are adhering to certain requirements for reporting in accordance or with reference to the GRI Standards, including the use of omissions and application of Sector Standards. These checks offer a tool to help drive improvements in the quality of reporting and recognize organizations who fulfil these requirements.

The GRI Sustainability Taxonomy will also provide a tool for regulators to define reporting requirements for new policies and regulations. This will help close the loop between the design of future policies, where these are based on the GRI Standards, and the implementation of reporting against these using digital formats.

Finally, having a global set of digital sustainability reporting standards offers the opportunity for GRI to help harmonize the reporting landscape even further by providing a bridge between different sets of regulations that include non-financial sustainability disclosures.

3 Understanding the Structure of

# the GRI Standards

The GRI Standards are a modular system of interconnected standards organized into three series: the GRI Universal Standards, GRI Sector Standards, and GRI Topic Standards, see Figure 1.1.

The Universal Standards are used by all organizations when reporting in accordance with the GRI Standards. Organizations use the Sector Standards according to the sectors in which they operate, and the Topic Standards according to their list of material topics. Further information about each of these series of the GRI Standards is included below: - Universal Standards The Universal Standards are composed of three Standards: GRI 1, GRI 2 and GRI 3. The purpose and content of these Standards are set out below: GRI 1: Foundation 2021 introduces the purpose and system of GRI Standards and explains key concepts for sustainability reporting. It also specifies the requirements and reporting principles that the organization must comply with to report in accordance with the GRI Standards (see below). GRI 2: General Disclosures 2021 contains disclosures that the organization uses to provide information about its reporting practices and other organizational details, such as its activities, governance, and policies. This information gives insight into the profile and scale of the organization and provides a context for understanding the organization’s impacts. GRI 3: Material Topics 2021 provides step-by-step guidance on how to determine material topics (i.e. topics that represent the organization’s most significant impacts on the economy, environment, and people, including impacts on their human rights). GRI 3 also contains disclosures that the organization uses to report information about its process of determining material topics, its list of material topics, and how it manages each topic.

- Sector Standards The Sector Standards provide information for organizations about their likely material topics. An organization uses the Sector Standards that apply to its sectors to help determine its material topics and what information to report for the material topics. The Sector Standards increase the quality, completeness, and consistency of reporting by organizations within sectors. The GRI Standards currently contain four Sector Standards: GRI 11: Oil and Gas Sector 2021, GRI 12: Coal Sector 2022, GRI 13: Agriculture, Aquaculture and Fishing Sectors 2022 and GRI 14: Mining Sector 2024.
- Topic Standards The Topic Standards contain disclosures for the organization to report information about its impacts in relation to particular topics. The Topic Standards cover a wide range of topics. The organization uses the Topic Standards according to the list of material topics it has determined using GRI 3.

All disclosures in the GRI Standards contain requirements that specify information that needs to be reported in order to comply with the GRI Standards. Some disclosures also contain compilation requirements, which specify how the information specified in the requirements must be collected, calculated or compiled. The GRI Sustainability Taxonomy has been designed to capture all the requirements of the GRI Standards including, where applicable, compilation requirements.

Disclosures may also contain guidance, which facilitates understanding of the reporting requirements by including background information, advice, explanations, and examples, and can also include recommendations, which specify reporting actions that are encouraged but not required. Both guidance and recommendations are advisory in nature and have not been included in the current version of the GRI Sustainability Taxonomy.

Organizations can choose to either report ‘in accordance’ or ‘with reference’ to the GRI Standards. When organizations reporting in accordance, they provide a comprehensive picture of their most significant impacts on the economy, environment, and people, including impacts on their human rights, and how they manage these impacts. Organizations report with reference when they cannot comply with all the requirements for reporting in accordance with the GRI Standards or when they use selected GRI Standards, or parts of their content, to report information about specific topics for specific purposes.

The requirements that have to be met for an organization to claim it is reporting in accordance with, or with reference to, the GRI Standards are set out in GRI 1: Foundation 2021, Section 3. Reporting in accordance with the GRI Standards.

A reporting organization must comply with nine requirements, set out in GRI 1: Foundation 2021, in order to claim that it is reporting in accordance with the GRI Standards: Requirement 1: Apply the reporting principles Requirement 2: Report the disclosures in GRI 2: General Disclosures 2021 Requirement 3: Determine material topics.

Requirement 4: Report the disclosures in GRI 3: Material Topics 2021 Requirement 5: Report disclosures from the GRI Topic Standards for each material topic Requirement 6: Provide reasons for omission for disclosures and requirements that the organization cannot comply with Requirement 7: Publish a GRI content index.

Requirement 8: Provide a statement of use.

Requirement 9: Notify GRI If the organization does not meet all nine requirements, it cannot claim that it is reporting in accordance with the GRI Standards.

To report with reference to the GRI Standards, a reporting organization must fulfill three requirements, as set out in GRI 1 Foundation 2021: Requirement 1: Publish a GRI content index.

Requirement 2: Provide a statement of use.

Requirement 3: Notify GRI For more information about reporting in accordance with the GRI Standards please see GRI 1 Foundation 2021, Section 3: Reporting in accordance with the GRI Standards.

4 The GRI Sustainability

# Taxonomy Architecture

## 4.1 Considerations for determining the Taxonomy Architecture

The GRI Sustainability Taxonomy represents the architecture of the GRI Standards: three Universal Standards (GRI 1, GRI 2 and GRI 3), thirty-three Topic Standards and four Sector Standards (GRI-11, GRI-12, GRI-13 and GRI-14).

The architecture of the GRI Sustainability Taxonomy is based on a methodical assessment of the relationship between the Universal Standards, Sector Standards and Topic Standards, to ensure that the architecture and contents of the Standards are reflected in the taxonomy and there are no duplication of elements and tags.

The GRI Sustainability Taxonomy is intended to accurately represent the GRI Standards in digital format as per specifications defined by XBRL standards1. The creation of this taxonomy was guided by several assumptions: (a) Its primary aim is to facilitate the tagging of sustainability reports that are prepared using the GRI Standards, ensuring data is presented in a machine-readable format while retaining the qualitative features of the human-readable format. (b) The taxonomy elements include only those necessary for disclosing the requirements and compilation requirements of the GRI Standards. (c) The taxonomy structure is designed to establish a direct alignment between its elements and the presentation of requirements in the Standards, including paragraphs, subparagraphs, and soib-subparagraphs.

## 4.2 Folder Structure

Taxonomy structure refers to the general composition of the files and folders within the taxonomy. The GRI Sustainability Taxonomy is distributed as a package according to the Taxonomy Packages 1.0 specification. This allows users to quickly identify relevant entry points and enables software to automatically configure the necessary remapping.

The GRI Sustainability Taxonomy contains: a. META-INF folder at root level which includes the taxonomyPackage.xml files. taxonomyPackage.xml – contains information about identifier, name, version, publisher, publisher URL, publisher country, publication date. b. gri_srs – contains sub-folders of core and includes schema files and other related linkbase files (presentation, definition, label, and references)

1 XBRL Specification 2.1, Dimensions 1.0, Enumeration Elements 2.0, Formula 1.0, Taxonomy Packages 1.0. Data type registry and Unit type registry. For the preparation of the tagged illustrative reports, the Inline XBRL specification 1.1 as well as the transformation registries have been used. The full specifications are available in https://specifications.xbrl.org/

I. gri_srs_entry_point_2025-06-23.xsd – is a schema which contains ELRs for disclosures reported under GRI Standards II. core folder – includes schema files where GRI Standards elements are defined including extensible enumerations.

- gri_srs_core_ 2025-06-23.xsd – is the schema file which contains all the data points along with its properties.

- gri_srs_part_2025-06-23.xsd – includes the list of all the typed dimensions domain defined in the taxonomy.

- country-current-PR-2024-01-31 – the folder includes all the country taxonomy files which are imported in the taxonomy.

- lei folder includes LEI taxonomy files to capture LEI number and applicable validation rules.

III. Formula folder – includes validation rules defined in the taxonomy.

- formula_gri-2_2025-06-23 – includes validation rules specific to GRI 2 disclosures.

- formula_gri-3_2025-06-23 – includes validation rules specific to GRI 3 disclosures.

- formula_gri-101_2025-06-23 – includes validation rules specific to GRI 101 series disclosures.

- formula_gri-200_2025-06-23 – includes validation rules specific to GRI 200 series disclosures.

- formula_gri-300_2025-06-23 – includes validation rules specific to GRI 300 series disclosure.

- formula_gri-400_2025-06-23 – includes validation rules specific to GRI 400 series disclosures.

- formula_gri-generic_2025-06-23 – includes general validation rules applicable for all disclosures.

IV. labels folder - is the folder which contains label linkbases.

- lab_gri_srs_2025-06-23.xml is the main English language label linkbase file.

V. linkbases folder - contain modular presentation, definition, and reference linkbase files for each GRI Standard - {pre\ def} _GRI disclosures number_2025-06-23.xml are the modular presentation and definition linkbase files for each GRI Standards.

- ref_gri_srs_2025-06-23.xml is the modular reference linkbase file for the GRI Standards.

- rol_gri_srs_2025-06-23.xsd is the schema which contains the ELRs for the presentation and definition linkbases of the GRI Standards.

## 4.3 Taxonomy Package

The Taxonomy Package 1.0 specification provides a standardized mechanism for documenting the taxonomy's content. This includes information about the name, version, and publisher of the taxonomy, as well as a list of the "entry points" available within the taxonomy.

The GRI Sustainability Taxonomy package contains META-INF folder at root level which includes catalog.xml files and the taxonomyPackage.xml files. a. Catalog.xml – contains dummy strings which have been provided for time being.

b. taxonomyPackage.xml – contains information about identifier, name, description, version, publisher, publisher URL, publisher country, publication date.

Within the taxonomy package xml, following xml elements are defined with their respective purposes. a. identifier – <tp: identifier> provides a URI that uniquely identifies the package. The URI defined in identifier is different from the namespace defined in each extended link roles. b. name – <tp:name> provides human readable name for the taxonomy. c. description – <tp: description> provides human readable description for the taxonomy. d. version – <tp: version> provides a version identifier for the taxonomy. e. publisher – <tp: publisher> describes the entity responsible for publishing the taxonomy. f. publisherURL – <tp:description> element provides a human-readable description for the entry point. g. publisherCountry – <tp: publisherCountry> provides the country or region of taxonomy publisher. h. publicationDate – <tp: publicationDate> provides a date on which the taxonomy was published. i. entry points – <tp: entryPoints> provides list of all entry points. j. Each entry point can be documented with name, description, and version number.

I. Entry point – <tp: entryPoint> defines a single-entry point. References to elements in the following sections refer only to those elements present as children of the <tp: entryPoint> element.

II. name – <tp:name> provides a human-readable name for the entry point.

III. version – <tp: version> provides a version identifier for the entry point.

IV. entryPointDocument – <tp: entryPointDocument> defines a taxonomy schema or a linkbase document that forms part of this entry point.

## 4.4 Approaches used for data modelling in the Taxonomy

### 4.4.1 Simple Hierarchy Modelling

In the GRI Sustainability Taxonomy, most of the relationships between elements are defined using a simple hierarchy which denotes parent and child relationships. This linear hierarchy is used across presentation and definition link bases. In other words, the concepts are organized in the form of a list following a logical order.

Filing Information Hierarchy Structure presented in the Taxonomy

**[Figure: Filing Information]**

Type: table

Data:

| Filing Information [abstract] |
| --- |
| Legal Entity Identifier |
| GRI Company Identifier Number |
| Level of accordance |
| Sectors Standards used |

Notes: This table represents the filing information for a company, including its legal entity identifier, GRI company identifier number, level of accordance, and sectors standards used.

- The Legal Entity Identifier2 (LEI) is a 20-character, alpha-numeric code based on the ISO 17442 standard. It provides a globally unique identifier for legal entities, such as companies. LEIs enable uniform and unique identification of legal entities and provide value when used in conjunction with structured, electronic reporting formats such as XBRL. This field will be optional to ensure that organizations who do not have an LEI can still submit reports digitally.
- GRI Company Identifier Number is a 12-digit numeric number that will be generated by GRI portal at the time of registering the company. This field will be mandatory as the system will need unique identifier apart from the name of the company.
- Organizations will have to declare whether they are reporting in accordance or with reference to the GRI Standards. Further guidance on the requirements for reporting at different levels of accordance can be found in GRI 1: Foundation 2021, Section 3: Reporting in accordance with the GRI Standards.
- Organizations will also have to declare which GRI Sector Standards they are using in their report, if any. The GRI Standards currently contain four Sector Standards: GRI 11: Oil and Gas Sector 2021, GRI 12: Coal Sector 2021, GRI 13: Agriculture, Aquaculture and Fishing Sectors 2021 and GRI 14: Mining Sector 2024.

### 4.4.2 Dimensional Modelling

The second modelling technique used in the GRI Sustainability Taxonomy is modelling through tables (hypercube) and axes (explicit and typed dimensions). The non-dimensional elements are generally referred to as line items. Dimensions are generally used to model tabular data having information in both rows and columns. Dimensions are also used when detailed breakdowns are to be provided for any reporting concepts. For creating a dimensional model, the line items are linked to a table, and the table is linked to an axis, or axes. The sub-categories in the breakdown are referred to as domain members. There are two types of dimensions used in taxonomy: explicit and typed dimensions.

2 For more information on LEI number refer “https://www.xbrl.org/guidance/lei-taxonomyguidance/#:~:text=related%20entity%20identifier.- ,3.1%20LEI%20as%20a%20primary%20identifier,which%20that%20identifier%20is%20taken.” and https://www.gleif.org/en/about-lei/introducing-the-legal-entity-identifier-lei Logical Structure of dimension

**[Figure: Root Level]**

Type: diagram

Description: The diagram illustrates the hierarchical structure of a root level, showcasing its components and their relationships. It provides a visual representation of how different elements are organized within this level.

Key Elements:

- Hypercube [Table] -> Represents a multidimensional data structure.
- Axis [Axis] -> Defines the dimensions or categories along which data is measured.
- Domain [Domain] -> Specifies the scope or range of values for each axis.
- Member [Member] -> Denotes individual data points or entries within the hypercube.
- Primary Elements [line items] -> Lists the fundamental components or line items that make up the root level.
- Primary Element 1 -> A specific primary element contributing to the root level.
- Primary Element 2 -> Another primary element that is part of the root level.
- Primary Element 3 -> The third primary element included in the root level.

### 4.4.3 Modelling using explicit dimensions

Explicit dimensions are used where the subcategories against which information (i.e. line items) need to be reported are defined explicitly by a requirement in the Standards. Dimensions are used for modelling concepts that frequently repeat when reporting certain facts. The axes of such dimensions have relationships with line items.

GRI 301-1 Materials used by weight or volume

**[Figure: Disclosure 301-1 Materials used by weight or volume]**

Type: diagram

Description: The figure presents a disclosure statement regarding the materials used by weight or volume, as required by the reporting organization. It outlines the total weight or volume of materials used to produce and package the organization's primary products and services during the reporting period.

Key Elements:

- **Total weight or volume of materials**: The figure provides a comprehensive overview of the materials used, categorized into non-renewable and renewable materials.
- **Non-renewable materials**: This component represents the materials that are not replenished naturally and are depleted over time.
- **Renewable materials**: This component represents the materials that can be replenished naturally and are sustainable in the long term.

The figure serves as a visual representation of the organization's commitment to transparency and sustainability, providing stakeholders with valuable information about its environmental impact.

Hierarchy Structure presented in the Taxonomy For example, for Disclosure 301-1 Materials used by weight or volume, the dimension ‘Material Resource’ is classified into ‘Non-renewable material’ and ‘Renewable material’ as domain member and will be reported for line items “Total weight of material used” and “Total volume of material used” as required by the GRI Standard.

**[Figure: GRI 301] Materials**

Type: diagram

Description: The figure illustrates the materials used by weight or volume, categorized into different types such as material resource, non-renewable material, and renewable material. It also includes a table that provides more detailed information about the materials used.

Key Elements:

- Material Resource [axis] -> represents the different types of materials used
- Non-renewable material -> indicates the amount of non-renewable materials used
- Renewable material -> indicates the amount of renewable materials used

This figure provides a visual representation of the materials used by weight or volume, allowing for easy comparison and analysis of the data.

### 4.4.4 Modelling using typed dimensions

In the GRI Sustainability Taxonomy, typed dimensions are used when the subcategories against which information (i.e. line items) need to be reported are not defined explicitly by a requirement in the Standards. Typed dimension values are defined by the preparer and are not present in the taxonomy. The preparer can create any number of members as per the reporting requirement.

GRI 401-1: New employee hires and employee turnover.

**[Figure: Disclosure 401-1 New employee hires and employee turnover]**

Type: table

Data:

| REQUIREMENTS | The reporting organization shall report the following information: |
| --- | --- |
| a. | Total number and rate of new employee hires during the reporting period, by age group, gender and region. |
| b. | Total number and rate of employee turnover during the reporting period, by age group, gender and region. |

Notes: This table represents the requirements for reporting new employee hires and employee turnover.

Hierarchy Structure presented in the Taxonomy For example, for Disclosure 2-7 Employees, the employee number must be reported by region. In the GRI Sustainability Taxonomy the region category is not pre-defined and allows preparers to define under Region [axis].

**[Figure: Disclosure of Employees, Breakdown By Region]**

Type: diagram

Description: The figure presents a breakdown of employees by region, providing a visual representation of the distribution of employees across different regions.

Key Elements:

- Region [axis] -> The x-axis represents the different regions.
- Typed Dimension -> The y-axis represents the number of employees in each region.

This diagram allows for a quick comparison of the number of employees in each region, facilitating an understanding of the regional distribution of the workforce.

## 4.5 Element grouping in the Taxonomy

The GRI Sustainability Taxonomy organizes elements to streamline the reporting process, ensuring clarity and precision. The taxonomy groups elements based on their relevance to specific disclosure requirements within the GRI Standards. Grouping facilitates the tagging of sustainability data in a machine-readable format while maintaining the integrity of human-readable reports. By aligning elements with mandatory and optional information specified in the Standards, the taxonomy ensures comprehensive and accurate representation of sustainability data.

The taxonomy elements are organized according to the specific GRI Standards from which the data points are derived. For instance, elements related to GRI 2 General Disclosure 2021 will be arranged in the same order as they appear in Standard (with minor adjustments for technical reasons, such as XBRL requirements) and grouped under a ‘GRI 2’ heading. Similarly, elements associated with GRI 3 Material Topics 2021 will be organized under a ‘GRI 3’ heading. This method simplifies the process for preparers and users of sustainability reports, making it easier to find elements corresponding to disclosures in the GRI Standards. This structure aligns with the practices used in other digital taxonomies globally.

The GRI Standards are intended to provide a comprehensive and consistent basis for reporting sustainability impacts. Consequently, the GRI Sustainability Taxonomy restricts the creation of extension taxonomies and entity-specific elements within the taxonomy. Extension taxonomies3 require creating a new XBRL taxonomy that references to the base taxonomy, involving XML schema files and linkbases. The decision not to allow extensions in the current release ensures a consistent basis for reporting and future data use by maintaining uniformity in the data structure and content across different reporting entities, which minimizes discrepancies and ambiguities. This uniformity is essential for precise comparison, analysis, and aggregation of data.

## 4.6 General granularity of elements defined in the Taxonomy

The GRI Sustainability Taxonomy maintains a consistent structure for data points that reflect the presentation of requirements in the GRI Standards (namely, by replicating the breakdown of GRI disclosures with paragraphs, sub-paragraphs, and sub-subparagraphs).

The disclosure structure was established according to Universal and Topic Standard disclosures, forming a hierarchy with three levels: - Level 1: Represents the entire disclosure.

- Level 2: Represents requirements identified using alphabetical labels (a, b, c, etc).

- Level 3: Represents requirements identified using roman numerals labels (i, ii, iii, etc).

Exclusion of Level 1 Information: GRI has decided not to base any taxonomy data points on Level 1 information. This decision helps to reduce the overall number of data points and simplifies the taxonomy.

Inclusion of Level 2 and Level 3 Information: To ensure comprehensive coverage of the General and Topic Standards disclosures, GRI mandates that all Level 2 and Level 3 information must be represented by at least one data point in the taxonomy. Level 2 and Level 3 information is more specific and detailed than Level 1.

Identification of Independent ‘Items of Information’: For all Universal and Topic Standards disclosures, GRI reviewed Level 2 and Level 3 information to identify independent 'items of 3 Extension taxonomies are built upon the existing taxonomy (referred to as a base taxonomy). Typically, these are created by preparers, known as entity-specific extension taxonomies. There are challenges in preparing the XBRL/iXBRL instances using these taxonomies, since all the Schema files and linkbases files (xsd and xml) need to be provided.

information'. These items represent distinct pieces of information that need to be reported to meet the disclosure requirements. Each identified item forms the basis for a data point in the taxonomy.

Disclosure 2-2 Entities included in the organization’s sustainability reporting Hierarchy Structure presented in the Taxonomy By focusing on Level 2 and Level 3 information and identifying specific items of information within these levels, GRI aims to ensure that all necessary disclosure requirements are captured efficiently without overburdening reporting organizations with excessive data points. This approach also facilitates more precise and manageable reporting, enhancing the usability and relevance of the taxonomy for stakeholders.

Level 1 Level 2 Level 3 Level 2 Level 3

5 Reporting Material Topics and

# Omissions

Reporting Material Topics: The organization’s material topics are disclosed in accordance with GRI 3 Material Topics 2021. The requirements for reporting include listing the material topics, detailing the process undertaken to identify them, including how stakeholders are involved, and describing the approach taken to manage each topic.

In the GRI Sustainability Taxonomy, reporting using GRI 3 disclosures is structured in a way to also enable reporting using Sector Standards When reporting Disclosure 3-2 List of material topics, organizations must also disclose which, if any, of the ‘likely material topics’ listed in the applicable Sector Standards are being used (“List of likely material topics”). They must also identify which disclosures are relevant to their material topics and will be used for reporting (“List of applicable disclosures”).

Hierarchy Structure presented in the Taxonomy The GRI Sector Standards offer organizations guidance on identifying their likely material topics. These topics are derived from the sectors’ most significant impacts, based on multi-stakeholder expertise, authoritative intergovernmental instruments, and other relevant evidence.

**[Figure: Disclosure 3-2 List of material topics]**

Type: diagram

Description: The figure presents a hierarchical list of material topics, categorized into three main sections: "Material Topics [table]," "Material Topics [axis]," and "Material Topics [line items]." Each section contains subtopics that are further divided into more specific categories.

Key Elements:

- Material Topics [table] -> A table listing material topics.
- Material Topics [axis] -> An axis representing material topics.
- Material Topics [line items] -> A list of line items related to material topics.

This diagram provides a structured overview of material topics, facilitating easy navigation and understanding of the various categories and subtopics involved.

When reporting in accordance with the GRI Standards, if any of the GRI Sector Standards are applicable to them, the organizations must use the Sector Standard to help determine their material topics (see Requirement 3-b in GRI 1: Foundation 2021).

Note: Use of the Sector Standards is intended to assist, not replace, the process of determining material topics. Organizations must still consider their specific circumstances when identifying their material topics.

Organizations are required to review each of the likely material topics listed in the Sector Standards applicable to them and determine which of these are relevant to them. It is possible, however, that not all likely material topics will be material to the organization. In this case, the organization is required to report information separately under “[666666] Topics in Sector Standards determined as not material” and explain why they are not considered to be relevant (see Requirement 3-b-ii in GRI 1: Foundation 2021).

Hierarchy Structure presented in the Taxonomy Note: The GRI Sustainability Taxonomy does not include separate ELRs for each of the GRI Sector Standards because the disclosures that form requirements of reporting are the same as those used for reporting without Sector Standards. This first version of the taxonomy excludes additional disclosures and recommendations that do not form requirements of reporting.

**[Figure: Topics in Sector Standards Determined as Not Material]**

Type: diagram

Description: This diagram illustrates the topics in sector standards that are determined as not material. It provides a visual representation of the various sectors and their corresponding topics that are considered non-material.

Key Elements:

- Topics in Applicable Sector Standards Determined as Not Material [abstract] -> This component represents the abstract concept of topics in sector standards that are determined as not material.
- Topics in Oil and Gas Sector Determined as Not Material [axis] -> This component represents the topics in the oil and gas sector that are determined as not material, displayed on an axis.
- Topics in Coal Sector Determined as Not Material [axis] -> This component represents the topics in the coal sector that are determined as not material, displayed on an axis.
- Topics in Agriculture, Aquaculture and Fishing Sectors Determined as Not Material [axis] -> This component represents the topics in the agriculture, aquaculture, and fishing sectors that are determined as not material, displayed on an axis.
- Topics in Mining Sector Determined as Not Material [axis] -> This component represents the topics in the mining sector that are determined as not material, displayed on an axis.
- Topics in Applicable Sector Standards Determined as Not Material [line items] -> This component represents the specific line items within the applicable sector standards that are determined as not material.

This diagram provides a clear and concise visual representation of the topics in sector standards that are determined as not material, allowing for easy understanding and analysis of the data.

Reporting Omissions For organizations reporting in accordance with the GRI Standards, if the organization cannot comply with a Topic Standard disclosure that is determined to be relevant to its material topics (or any of the requirements in a relevant disclosure) they must: a. specify the disclosure or the requirement it cannot comply with. b. provide a reason for omission (chosen from a list of four options, as set out in GRI 1 Foundation 2021) and provide an explanation for the omission.

Reasons for omission are also permitted for all disclosures in GRI 2: General Disclosures 2021 and GRI 3: Material Topics 2021 except for: a. Disclosure 2-1 Organizational details b. Disclosure 2-2 Entities included in the organization’s sustainability reporting c. Disclosure 2-3 Reporting period, frequency and contact point d. Disclosure 2-4 Restatements of information e. Disclosure 2-5 External assurance f. Disclosure 3-1 Process to determine material topics g. Disclosure 3-2 List of material topics Omissions can be reported at the individual requirement level, which determines the level of granularity with which omissions can be reported using the taxonomy. There are two ways in which this is managed: 1. Requirements that are presented in a non-dimensional format should be reported under a separate ELR: [777777] Information on Omission. 2. For dimensionally structured requirements, omissions must be reported within the same ELR. Each requirement in the table has dedicated concepts for "Reason for Omission" and "Explanation for Reason for Omission," which should be used when the required information is not provided.

6 Technical features This section summarizes the technical features of the GRI Sustainability Taxonomy and is intended to: a. provide technical details on the usability of the taxonomy as per XBRL specification. b. provide better understanding of the content used in the GRI Sustainability Taxonomy The features will address the following components of the GRI Sustainability Taxonomy:

## 6.1 Categorical Elements – Extensible Enumerations

The use of extensible enumerations in the GRI Sustainability Taxonomy is to maintain the enumerations list in a standardized manner. Enumerations4 are predefined lists (analogous to 'drop-down menus') within the taxonomy, enabling users to select the most appropriate item (single choice) or multiple items (multiple choices) from the list. The inclusion of these element type in the taxonomy is intended to enhance the usability and comparability of information.

Below are several examples of elements having “enum2: enumerationItemType” and “enum2: enumerationSetItemType”.

### Table: Data Table

| Data type | Assigned to data element |
|---|---|
| enum2: enumerationItemType | 2-1-b: Nature of ownership, 2-1-b: Legal form, 2-3-a: Frequency of sustainability reporting |
| enum2: enumerationSetItemType | 2-1-d: Countries of operation 302-3-c: Types of energy included in the energy intensity ratio, 305-4-d: Gases included in the calculation of direct (Scope 1) GHG emissions intensity ratio |

Illustrated example of tagging enumerationItemType and enumerationSetItemType: Tagging enumeration elements, with single select and multi select fact values will be represented as shown below in the XBRL instances: <ix:nonNumeric contextRef="D20241231" name="gri:NatureOfOwnership" id="Tag5">https://www.globalreporting.org/standards/standards-development/digitalization-ofthe-gri-standards-project/consultation-for-xbrl-specialists/draft-gritaxonomy/gri_srs/core#PubliclyOwnedMember</ix:nonNumeric>

<ix:nonNumeric contextRef="D20241231" name="gri:CountriesOfOperation" id="Tag7">

4 Extensible Enumerations 2.0 specification permits the use of predefined domain members within the taxonomy as an enumerated list for reporting any XBRL item. Software vendors are required to include this functionality in their platforms for reporting purposes.

https://xbrl.org/2023/iso3166/PR/2024-01-31#AE https://xbrl.org/2023/iso3166/PR/2024-01-31#AR https://xbrl.org/2023/iso3166/PR/2024-01-31#AT https://xbrl.org/2023/iso3166/PR/2024-01-31#AU </ix:nonNumeric>

## 6.2 Categorical Elements – BooleanItemType

This data type is valuable for reporting financial or business information that can be framed as true/false. The usage of BooleanItemType contributes to the standardization and interoperability of data, ensuring that stakeholders can easily interpret and analyse information with a clear understanding of the binary nature of the reported elements.

These data types are used in the taxonomy to reflect disclosure requirements including conditions. All the booleanItemType element starts with word “Whether….” (Example; The organization has audited consolidated financial statements or financial information filed on public record).

However, in addition to the BooleanItemType "Whether…", narrative elements (textblockItemType) are frequently introduced to capture complimentary information according to the requirements of the Standards.

See below examples of booleanItemType used in the taxonomy.

### Table: Data Table

| Data Type | Element Name |
|---|---|
| booleanItemType | WhetherConsolidatedFinancialStatementsAreAuditedOrFinancialI nformationFiledOnPublicRecord |
| booleanItemType | WhetherOrganizationConsistsOfMultipleEntities |
| booleanItemType | WhetherApproachUsedForConsolidatingInformationInvolvesAdjus tmentsToInformationForMinorityInterests |
| booleanItemType | WhetherApproachUsedForConsolidatingInformationDiffersAcross DisclosuresInGRI2AndAcrossMaterialTopics |

Illustrated example of tagging BooleanItemType: Boolean facts can be tagged with a true or false value using the Inline XBRL transformations and will be represented as shown below in the XBRL instances: <ix:nonNumeric contextRef="D20241231" name="gri:WhetherOffsetsWereUsedToMeetGHGEmissionsTargets" id="Tag13">false</ix:nonNumeric>

## 6.3 Different Datatypes used across the Taxonomy

The GRI Sustainability Taxonomy uses item types as defined in XBRL 2.1 specification under “The Data Type Registry5” which is a centralised list of data types to be used in XBRL taxonomies. Below is the list of datatypes used in the GRI Sustainability Taxonomy:

5 http://www.xbrl.org/dtr/type/2024-01-31/types.xsd

### Table: Data Table

| Data Type | Assigned to element |
|---|---|
| areaItemType | SizeOfOperationalSite |
| domainItemType | HighestGovernanceBodyMember |
| energyItemType | TotalEnergyConsumptionWithinOrganization |
| enum2:enumerationItemType | NatureOfOwnership |
| enum2:enumerationSetItemTyp e | CountriesOfOperation |
| ghgEmissionsItemType | GrossDirectScope1GHGEmissions |
| lengthItemType | DistanceOfSiteToEcologicallySensitiveArea |
| massItemType | WeightOfWasteGenerated |
| percentItemType | PercentageOfTotalEmployeesCoveredByCollectiveBargaini ngAgreements |
| textBlockItemType | DescriptionOfMethodologiesAndAssumptionsUsedToCompi leEmployeeDataTextBlock |
| volumeItemType | WaterWithdrawal |
| xbrli:booleanItemType | WhetherSustainabilityReportingHasBeenExternallyAssured |
| xbrli:dateItemType | StartDateOfSustainabilityReporting |
| xbrli:decimalItemType | TotalNumberOfEmployees |
| xbrli:integerItemType | TotalNumberOfConfirmedIncidentsOfCorruption |
| xbrli:monetaryItemType | EconomicValueDistributed |
| xbrli:stringItemType | LegalName |

## 6.4 Use of specific labels within the Taxonomy

The labels defined in the GRI Sustainability Taxonomy are implemented to maintain as closely as possible the original wording of the GRI Standards. The purpose of defining these labels is to ensure that organizations can easily navigate and relate to the disclosures and requirements. The element labels are named according to the disclosures: - Level 2 represents requirements identified using alphabetical labels.

- Level 3 represents requirements identified using Roman numeral labels.

Example: In the Disclosure 2-2 Entities included in the organization’s sustainability reporting, the requirements labelled with alphabetical letters are Level 2 tags. In contrast, those labelled with Roman numerals are Level 3 tags as defined in the taxonomy.

Disclosure 2-2 Entities included in the organization’s sustainability reporting Hierarchy Structure presented in the Taxonomy The elements within the taxonomy are initially assigned a 'standard label' by default, but there are additional preferred labels designated for these elements, namely "terse" and "verbose".

**[Figure: Disclosure 2-2 Entities included in the organization's sustainability reporting]**

Type: diagram

Description: The diagram illustrates the requirements for entities included in an organization's sustainability reporting. It outlines the steps and considerations for determining which entities to include, including the use of consolidated financial statements, the differences between financial reporting and sustainability reporting, and the approach used for consolidating information.

Key Elements:

- List all entities included in sustainability reporting -> This step involves identifying all entities that are part of the organization's sustainability reporting.
- If the organization has audited consolidated financial statements or financial information filed on public record, specify the differences between the list of entities included in its financial reporting and the list included in its sustainability reporting -> This step requires comparing the entities included in financial reporting with those in sustainability reporting and highlighting any differences.
- If the organization consists of multiple entities, explain the approach used for consolidating the information, including -> This step involves explaining how the organization consolidates information from multiple entities, including whether adjustments are made for minority interests, how mergers, acquisitions, and disposal of entities or parts of entities are handled, and whether the approach differs across disclosures in this Standard and across material topics.

This diagram provides a structured approach to determining which entities should be included in an organization's sustainability reporting, ensuring transparency and consistency in the reporting process.

**[Figure: Disclosure 2-2 Entities included in the organization's sustainability reporting]**

Type: diagram

Description: The figure presents a structured outline of the entities included in an organization's sustainability reporting, organized into sections and subsections for clarity.

Key Elements:

- **2-2-a: List of all entities included in the sustainability reporting** -> Provides a comprehensive list of entities covered in the report.
- **2-2-b: Differences between the list of entities included in financial reporting and the list included in sustainability reporting** -> Highlights the variations between entities reported in financial statements and those in sustainability reports.
- **2-2-c: Explanation of the approach used for consolidating the information across multiple entities** -> Details the methodology employed for consolidating data from various entities.
- **2-2-c-i: The approach used for consolidating the information involves adjustments to information** -> Specifies that the consolidation approach includes making adjustments to the information.
- **2-2-c-ii: Explanation of how the approach takes into account mergers, acquisitions, and disposal** -> Explains how the consolidation approach considers mergers, acquisitions, and disposals.
- **2-2-c-iii: The approach used for consolidating the information is different across the disclosures in GRI 2 and across material topics** -> Notes that the consolidation approach differs across GRI 2 disclosures and material topics.

This structured diagram aids in understanding the scope and methodology of sustainability reporting, emphasizing the importance of transparency and consistency in presenting organizational data.

The 'verbose' labels are structured in the taxonomy so that the labels are read along with the corresponding GRI Disclosure number (para, subparagraph and sub-subparagraph). This helps the user navigate the taxonomy more effectively and connect with specific disclosures, and will be particularly helpful for users who have published pdf reports previously using the GRI Standards.

The 'terse' labels are applied to specific elements where referencing the GRI Standards is not necessary.

## 6.5 Tagging of intensity ratios

### Table: Data Table

| In GRI Sustainability Taxonomy there are intensity-related datapoints that require specific |  |
|---|---|
| implementation in the taxonomy. Below is the list of elements related to intensity ratio | : |

### Table: Data Table

| Intensity ratio | Data Type | Element ID |
|---|---|---|
| 302-3-a: Energy intensity ratio for the organization | decimalItemType | gri EnergyIntensityRatioForOrganization _ |
| 305-4-a: Direct (Scope 1) GHG emissions intensity ratio | decimalItemType | gri DirectScope1GHGEmissionsIntensityRati _ o |
| 305-4-a: Location-based energy indirect (Scope 2) GHG emissions intensity ratio | decimalItemType | gri LocationBasedEnergyIndirectScope2GHG _ EmissionsIntensityRatio |
|  |  |  |
| 305-4-a: Market-based energy indirect (Scope 2) GHG emissions intensity ratio | decimalItemType | gri MarketBasedEnergyIndirectScope2GHGE _ missionsIntensityRatio |
| 305-4-a: Direct (Scope 1) and energy indirect (Scope 2) GHG emissions intensity ratio | decimalItemType | gri DirectScope1AndEnergyIndirectScope2G _ HGEmissionsIntensityRatio |
| 305-4-a: Other indirect (Scope 3) GHG emissions intensity ratio | decimalItemType | gri OtherIndirectScope3GHGEmissionsIntens _ ityRatio |

Intensity ratios are metrics that quantify the extent of an impact (like CO2 emissions, energy use, or waste production) in relation to a particular activity, output, or relevant denominator. The GRI Standards allow reporters to report intensity ratio by the organization-specific metric (the denominator) as defined by organization. For example, intensity ratios can be provided for, - products (such as energy consumed/metric tons of CO2 emissions per unit produced);

- services (such as energy consumed/ metric tons of CO2 emissions per function or per service);
- sales (such as energy consumed/ metric tons of CO2 emissions per monetary unit of sales).

Organization-specific metrics (denominator) can include - units of product;

- production volume (such as metric tons, liters, or MWh);
- size (such as m2 floor space);
- number of full-time employees;
- monetary units (such as revenue or sales).

These intensity ratios express the energy or amount of GHG emission required per unit of activity, output, or any other organization specific metric.

Intensity ratios have been implemented in the taxonomy to allow various denominator factors specific to organizations. The GRI Sustainability taxonomy has implemented those elements with a decimalItemType to facilitate digital reporting. In addition to the intensity ratio, organizations are required to report the denominator used for calculating intensity ratio when preparing their XBRL reports Example: If GHG emission intensity ratio is expressed as CO2 equivalent emissions per monetary unit, it will be expressed as ‘actual value’ in the XBRL/iXBRL reports due to datatype being ‘decimalItemType’.

7 Validation rules The GRI Sustainability Taxonomy implements several validations rules based on Formula Linkbase 1.0 specification6. The formula linkbase is created to define all the validation rules which can ensure consistency of data and adherence to the requirements of reporting set out in the Standards (e.g. correct use of omissions). These validation rules include operations such as comparing values, totaling values, checking if values are reported, checking if proper signs are provided, etc. The validation rules are classified by different categorizations within the taxonomy.

## 7.1 Modelling of validation rules in formula linkbase

The GRI taxonomy uses existenceAssertion and valueAssertion for modelling the validation rules in formula linkbase. The modelling of different categories of business rules and the assertions used for them are explained in this section. The approach for modelling business rules in the GRI Sustainability Taxonomy is considering a positive outcome. Thus, the result “true” indicates that the rule is passed, while “false” indicates that the rule is not passed.

### 7.1.1 Derived Mandatory

There are some elements which are required to be reported depending on the values submitted for other elements. These are termed as derived mandatory elements. A derived mandatory element is only required under certain circumstances. The derived mandatory items are modelled using preconditions and valueAssertions. In precondition, the base element and its expected value are provided, and the dependent element is mentioned as part of valueAssertion.

Example: When reporting in accordance with the GRI Standards, the legal name must be reported.

### 7.1.2 Non-negative checks

Non-negative checks are a crucial validation process in various fields, ensuring that certain values or quantities are not reported to be less than zero. Implementing non-negative checks helps keep data accurate, prevents errors, and ensures operations make sense.

Example: The total weight of waste generated must not be negative.

### 7.1.3 Validation related to omissions

In the GRI Sustainability Taxonomy there are specific scenarios identified where validation checks will be applied for organizations reporting in accordance with the GRI Standards.

Example: The total number of employees must be reported. If this information is not reported, a reason for omission and an explanation for the omission must be provided. If this information is reported, however, details about omissions must not be provided.

### 7.1.4 Generic checks

The GRI Sustainability Taxonomy includes checks related to the pattern of company identifier number. The GRI Company Identifier Number should be a 12-digit numeric number which will be mandatory field to be reported by each organization.

GRI will introduce additional validation rules and consistency checks in future versions of the taxonomy to enhance the quality of digital report and assist preparers in using the XBRL taxonomy for reporting

6 https://specifications.xbrl.org/spec-group-index-formula.html In the GRI Sustainability Taxonomy, assertion severity is assigned to cater to unsatisfied or failed scenarios only. Every validation rule is assigned an assertion severity to distinguish it as either an “Error” or a “Warning”, along with unsatisfied error message.

- A WARNING constitutes a recommendation to check or review the data submitted but does not prevent filing from being accepted.
- An ERROR constitutes an issue with the data submitted that has to be corrected in order for the filing to be accepted.

8 Use of Unit Type Registry The XBRL 2.1 specification requires that all numeric facts be associated with a unit, and mandates specific units to be used in a small number of cases such as monetary facts. The Unit Type Registry provides a centralized list of units, in order to promote consistent use of units across preparers and jurisdictions. GRI Standards require using newly added units such as ‘Ml – Megalitre’ regardless of their status being designated as ‘CR (Candidate Recommendation)’. To ensure alignment with GRI reporting requirements, the taxonomy includes and references these units even if they have not yet reached the 'REC (Recommendation)' status in the Unit Type Registry. Preparers must ensure that their XBRL tools support such units and that these are correctly defined within instance documents. Currently, the GRI-specific unit ‘metric tons of CFC-11 (trichlorofluoromethane) equivalent’ (related to Disclosure 305-6 Emissions of ozone-depleting substances (ODS)) has not yet been approved. Discussions are ongoing with XBRL International, and the unit is expected to be included in the UTR shortly.

# Appendix A: XBRL Glossary

### Table: Data Table

| Abstract | An attribute of an element used to indicate that the element is only used in a hierarchy to group related elements together. An abstract element cannot be used to tag data in an instance document. |
|---|---|
| Arc | According to XBRL Specification 2.1 arcs relate concepts to each other by associating their locators; they also link concepts with resources by connecting the concept locators to the resources themselves; arcs are also used to connect fact locators to footnote resources in footnote extended links; arcs have a set of attributes that document the nature of the expressed relationships; in particular they possess attributes: type (whose value must be "arc"), from, to and arcrole. |
| Attribute | A property of an element such as its name, balance, data type, and whether the element is abstract. Attributes of XBRL taxonomy elements cannot be changed. |
| Axis | An instance document contains facts; an axis differentiates facts, and each axis represents a way that the facts may be classified. |
| Context | Entity and report-specific information (reporting period, segment information, and so forth) required by XBRL that allows tagged data to be understood in relation to other information. |
| Data type | Data types (monetary, string, share, decimal, and so forth) define the kind of data to be tagged with the element name. |
| Decimal | Instance document fact attribute used to express the number of decimal places to which numbers have been rounded. |
| Dimension | A dimension represents a specific aspect or characteristic of data being reported. Dimensions can be explicit, where members are explicitly named, or typed dimensions, where the number of members is too large to enumerate individually. |
| Domain | An element that represents a complete set of other elements; the domain and its members are used to classify facts along the axis of a table. |
| Domain member | An element representing one of the possibilities within a domain. |
| Element | XBRL components (items, domain members, dimensions, and so forth). The representation of a financial reporting concept, including line items in the face of the financial statements, important narrative disclosures, and rows and columns in tables. |
| Element ID | Represents refers to a unique identifier assigned to each data element within an XBRL taxonomy. |
| Element definition | A human-readable description of a reporting concept. From an XBRL technical point of view, the element definition is the label with the type "documentation," and there are label relationships in a label relationships file, but from a user point of view the definition is an unchangeable attribute of the element. |
| Extended linkrole (ELR) | Refers to a specific type of link role in the XBRL taxonomy. Link roles are used to define relationships between elements within an XBRL instance document, providing a structured way to organize and present data. |
| Extension taxonomy or extension | A taxonomy that allows users to add to a published taxonomy to define new elements or change element relationships and attributes (presentation, calculation, labels, and so forth) without altering the original. |
| Explicit dimension | Explicit dimensions are those classifications which are known and can be defined in the taxonomy |
| Fact | The occurrence in an instance document of a value or other information tagged by a taxonomy element. |
| Hierarchy | Trees (presentation, calculation, and so forth) used to express and navigate relationships. |
| Hypercube | XBRL technical term for a table. |
| Instance document | XML file that contains business reporting information and represents a collection of financial facts and report-specific information using tags from one or more XBRL taxonomies. |
| iXBRL | iXBRL stands for Inline eXtensible Business Reporting Language. iXBRL combines the human-readable presentation of a financial and non-financial statement with the machine-readable XBRL data |
| Label | Human-readable name for an element; each element has a standard label that corresponds to the element name and is unique across the taxonomy. |
| Line item | Elements that conventionally appear on the vertical axis (rows) of a table. |
| Linkbase | XBRL technical term for a relationships file. It provides a way to express linkages and connections between various elements in a standardized manner |
| Schema | Defines the structure and semantics of XBRL documents. It serves as a blueprint or a set of rules that dictate how data should be organized and what types of elements are allowed within an XBRL instance document |
| Typed dimension | Typed dimensions are those classifications which cannot be ascertained or defined in the taxonomy |
| Taxonomy | Electronic dictionary of business reporting elements used to report business data. A taxonomy is composed of an element names file (.xsd) and relationships files directly referenced by that schema. The taxonomy schema files together with the relationships files define the concepts (elements) and relationships that form the basis of the taxonomy. The set of related schemas and relationships files altogether constitute a taxonomy. |
| Validation | Process of checking that instance documents and taxonomies correctly meet the rules of the XBRL specification and adhere to requirements of reporting in accordance or with reference to the GRI Standards |
