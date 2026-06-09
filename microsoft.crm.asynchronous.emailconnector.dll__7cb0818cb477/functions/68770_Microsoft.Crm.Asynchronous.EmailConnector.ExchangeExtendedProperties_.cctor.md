# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::.cctor

- ea: `0x68770`
- end: `0x69651`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::.cctor`
- size: `3809`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x68d39`: `crmLinkState`
- `0x69452`: `CrmLinkState`
- `0x695e1`: `CrmLinkState`
- `0x68e34`: `crmsecondpagexml`
- `0x68ddb`: `crmxml`
- `0x69292`: `PostalAddressId`
- `0x68d03`: `crmServiceId`
- `0x68e58`: `crmSecondLinkState`
- `0x68e7c`: `crmTaskAssignedUniqueId`
- `0x68e8e`: `crmTaskTrackerUserId`
- `0x68ea0`: `crmTaskAssigneeUserId`
- `0x68eb2`: `crmTaskAssignerUserId`
- `0x68ec4`: `crmtaskstatus`
- `0x69062`: `CompanyTelephone`
- `0x690e2`: `CompanyName`
- `0x692d2`: `TaskAcceptanceState`
- `0x692e2`: `TaskAccepted`
- `0x692f2`: `TaskOwnership`
- `0x69302`: `TaskCreator`
- `0x69312`: `TaskFlagStatus`
- `0x69342`: `ScheduledStart`
- `0x69352`: `ScheduledEnd`
- `0x69422`: `CrmServiceId`
- `0x694e2`: `CrmXml`
- `0x69552`: `CrmSecondLinkState`
- `0x69582`: `CrmTaskAssignedUniqueId`
- `0x69592`: `CrmTaskTrackerUserId`
- `0x695a2`: `CrmTaskAssigneeUserId`
- `0x695b2`: `CrmTaskAssignerUserId`
- `0x695c2`: `CrmTaskStatus`

## pseudocode

```c

```

## disassembly

```asm
0x68770  ldc.i4.4
0x68771  ldc.i4   0x802C
0x68776  ldc.i4.s 0x19
0x68778  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6877d  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidYomiFirstName
0x68782  ldc.i4.4
0x68783  ldc.i4   0x802D
0x68788  ldc.i4.s 0x19
0x6878a  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6878f  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidYomiLastName
0x68794  ldc.i4   0x3A4F
0x68799  ldc.i4.s 0x19
0x6879b  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x687a0  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_NICKNAME
0x687a5  ldc.i4   0x3A17
0x687aa  ldc.i4.s 0x19
0x687ac  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x687b1  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_TITLE
0x687b6  ldc.i4   0x3A18
0x687bb  ldc.i4.s 0x19
0x687bd  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x687c2  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_DEPARTMENT_NAME
0x687c7  ldc.i4   0x3A4E
0x687cc  ldc.i4.s 0x19
0x687ce  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x687d3  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_MANAGER_NAME
0x687d8  ldc.i4   0x3A30
0x687dd  ldc.i4.s 0x19
0x687df  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x687e4  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_ASSISTANT
0x687e9  ldc.i4   0x3A2E
0x687ee  ldc.i4.s 0x19
0x687f0  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x687f5  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_ASSISTANT_TELEPHONE_NUMBER
0x687fa  ldc.i4   0x3A48
0x687ff  ldc.i4.s 0x19
0x68801  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68806  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_SPOUSE_NAME
0x6880b  ldc.i4   0x3A58
0x68810  ldc.i4.s 0x1A
0x68812  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68817  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_CHILDRENS_NAMES_W
0x6881c  ldc.i4   0x3A08
0x68821  ldc.i4.s 0x19
0x68823  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68828  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_BUSINESS_TELEPHONE_NUMBER
0x6882d  ldc.i4   0x3A09
0x68832  ldc.i4.s 0x19
0x68834  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68839  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_HOME_TELEPHONE_NUMBER
0x6883e  ldc.i4   0x3A1B
0x68843  ldc.i4.s 0x19
0x68845  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6884a  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_BUSINESS2_TELEPHONE_NUMBER
0x6884f  ldc.i4   0x3A02
0x68854  ldc.i4.s 0x19
0x68856  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6885b  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_CALLBACK_TELEPHONE_NUMBER
0x68860  ldc.i4   0x3A57
0x68865  ldc.i4.s 0x19
0x68867  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6886c  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_COMPANY_TELEPHONE_NUMBER
0x68871  ldc.i4   0x3A2F
0x68876  ldc.i4.s 0x19
0x68878  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6887d  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_HOME2_TELEPHONE_NUMBER
0x68882  ldc.i4   0x3A1F
0x68887  ldc.i4.s 0x19
0x68889  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6888e  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_OTHER_TELEPHONE_NUMBER
0x68893  ldc.i4   0x3A1C
0x68898  ldc.i4.s 0x19
0x6889a  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6889f  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_CELLULAR_TELEPHONE_NUMBER
0x688a4  ldc.i4   0x3A21
0x688a9  ldc.i4.s 0x19
0x688ab  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x688b0  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_PAGER_TELEPHONE_NUMBER
0x688b5  ldc.i4   0x3A51
0x688ba  ldc.i4.s 0x19
0x688bc  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x688c1  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_BUSINESS_HOME_PAGE
0x688c6  ldc.i4   0x3A4C
0x688cb  ldc.i4.s 0x19
0x688cd  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x688d2  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_FTP_SITE
0x688d7  ldc.i4   0x3A41
0x688dc  ldc.i4.s 0x17
0x688de  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x688e3  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_WEDDING_ANNIVERSARY
0x688e8  ldc.i4   0x3A42
0x688ed  ldc.i4.s 0x17
0x688ef  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x688f4  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_BIRTHDAY
0x688f9  ldc.i4   0x3A07
0x688fe  ldc.i4.s 0x19
0x68900  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68905  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_GOVERNMENT_ID_NUMBER
0x6890a  ldc.i4   0x1000
0x6890f  ldc.i4.s 0x19
0x68911  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68916  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_BODY
0x6891b  ldc.i4   0x3A11
0x68920  ldc.i4.s 0x19
0x68922  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68927  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_SURNAME
0x6892c  ldc.i4   0x3A44
0x68931  ldc.i4.s 0x19
0x68933  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68938  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_MIDDLE_NAME
0x6893d  ldc.i4   0x3A06
0x68942  ldc.i4.s 0x19
0x68944  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68949  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_GIVEN_NAME
0x6894e  ldc.i4   0x3A05
0x68953  ldc.i4.s 0x19
0x68955  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6895a  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_GENERATION
0x6895f  ldc.i4   0x3A45
0x68964  ldc.i4.s 0x19
0x68966  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6896b  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_DISPLAY_NAME_PREFIX
0x68970  ldc.i4   0x3001
0x68975  ldc.i4.s 0x19
0x68977  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6897c  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_DISPLAY_NAME
0x68981  ldc.i4   0x3A16
0x68986  ldc.i4.s 0x19
0x68988  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6898d  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_COMPANY_NAME
0x68992  ldc.i4.4
0x68993  ldc.i4   0x8083
0x68998  ldc.i4.s 0x19
0x6899a  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x6899f  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail1EmailAddress
0x689a4  ldc.i4.4
0x689a5  ldc.i4   0x8080
0x689aa  ldc.i4.s 0x19
0x689ac  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x689b1  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail1DisplayName
0x689b6  ldc.i4.4
0x689b7  ldc.i4   0x8084
0x689bc  ldc.i4.s 0x19
0x689be  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x689c3  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail1OriginalDisplayName
0x689c8  ldc.i4.4
0x689c9  ldc.i4   0x8082
0x689ce  ldc.i4.s 0x19
0x689d0  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x689d5  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail1AddressType
0x689da  ldc.i4.4
0x689db  ldc.i4   0x8085
0x689e0  ldc.i4.2
0x689e1  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x689e6  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail1OriginalEntryId
0x689eb  ldc.i4.4
0x689ec  ldc.i4   0x8093
0x689f1  ldc.i4.s 0x19
0x689f3  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x689f8  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail2EmailAddress
0x689fd  ldc.i4.4
0x689fe  ldc.i4   0x8090
0x68a03  ldc.i4.s 0x19
0x68a05  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a0a  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail2DisplayName
0x68a0f  ldc.i4.4
0x68a10  ldc.i4   0x8094
0x68a15  ldc.i4.s 0x19
0x68a17  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a1c  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail2OriginalDisplayName
0x68a21  ldc.i4.4
0x68a22  ldc.i4   0x8092
0x68a27  ldc.i4.s 0x19
0x68a29  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a2e  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail2AddressType
0x68a33  ldc.i4.4
0x68a34  ldc.i4   0x8095
0x68a39  ldc.i4.2
0x68a3a  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a3f  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail2OriginalEntryId
0x68a44  ldc.i4.4
0x68a45  ldc.i4   0x80A3
0x68a4a  ldc.i4.s 0x19
0x68a4c  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a51  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail3EmailAddress
0x68a56  ldc.i4.4
0x68a57  ldc.i4   0x80A0
0x68a5c  ldc.i4.s 0x19
0x68a5e  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a63  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail3DisplayName
0x68a68  ldc.i4.4
0x68a69  ldc.i4   0x80A4
0x68a6e  ldc.i4.s 0x19
0x68a70  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a75  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail3OriginalDisplayName
0x68a7a  ldc.i4.4
0x68a7b  ldc.i4   0x80A2
0x68a80  ldc.i4.s 0x19
0x68a82  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a87  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail3AddressType
0x68a8c  ldc.i4.4
0x68a8d  ldc.i4   0x80A5
0x68a92  ldc.i4.2
0x68a93  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68a98  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidEmail3OriginalEntryId
0x68a9d  ldc.i4   0x3A24
0x68aa2  ldc.i4.s 0x19
0x68aa4  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68aa9  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_BUSINESS_FAX_NUMBER
0x68aae  ldc.i4.4
0x68aaf  ldc.i4   0x80C3
0x68ab4  ldc.i4.s 0x19
0x68ab6  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68abb  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidFax2EmailAddress
0x68ac0  ldc.i4.4
0x68ac1  ldc.i4   0x80C4
0x68ac6  ldc.i4.s 0x19
0x68ac8  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68acd  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidFax2OriginalDisplayName
0x68ad2  ldc.i4.4
0x68ad3  ldc.i4   0x80C2
0x68ad8  ldc.i4.s 0x19
0x68ada  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68adf  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidFax2AddressType
0x68ae4  ldc.i4.4
0x68ae5  ldc.i4   0x80C5
0x68aea  ldc.i4.2
0x68aeb  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68af0  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidFax2OriginalEntryId
0x68af5  ldc.i4.4
0x68af6  ldc.i4   0x8028
0x68afb  ldc.i4.s 0xF
0x68afd  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b02  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidAddressBookProviderEmailList
0x68b07  ldc.i4.4
0x68b08  ldc.i4   0x8029
0x68b0d  ldc.i4.s 0xE
0x68b0f  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b14  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidAddressBookProviderArrayType
0x68b19  ldc.i4.4
0x68b1a  ldc.i4   0x804A
0x68b1f  ldc.i4.s 0x19
0x68b21  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b26  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_BUSINESS_ADDRESS_POST_OFFICE_BOX
0x68b2b  ldc.i4   0x3A5E
0x68b30  ldc.i4.s 0x19
0x68b32  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b37  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_HOME_ADDRESS_POST_OFFICE_BOX
0x68b3c  ldc.i4   0x3A64
0x68b41  ldc.i4.s 0x19
0x68b43  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b48  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_OTHER_ADDRESS_POST_OFFICE_BOX
0x68b4d  ldc.i4.4
0x68b4e  ldc.i4   0x8022
0x68b53  ldc.i4.s 0xE
0x68b55  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b5a  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidPostalAddressId
0x68b5f  ldc.i4.4
0x68b60  ldc.i4   0x8006
0x68b65  ldc.i4.s 0xE
0x68b67  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b6c  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidFileUnderId
0x68b71  ldc.i4.s 0x37
0x68b73  ldc.i4.s 0x19
0x68b75  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b7a  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_SUBJECT
0x68b7f  ldc.i4.s 0x36
0x68b81  ldc.i4.s 0xE
0x68b83  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b88  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_SENSITIVITY
0x68b8d  ldc.i4.s 0x1A
0x68b8f  ldc.i4.s 0x19
0x68b91  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68b96  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_MESSAGE_CLASS
0x68b9b  ldc.i4.8
0x68b9c  ldc.i4   0x8129
0x68ba1  ldc.i4.s 0xE
0x68ba3  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68ba8  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidTaskOwnership
0x68bad  ldc.i4.8
0x68bae  ldc.i4   0x812A
0x68bb3  ldc.i4.s 0xE
0x68bb5  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68bba  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidTaskAcceptanceState
0x68bbf  ldc.i4.8
0x68bc0  ldc.i4   0x8108
0x68bc5  ldc.i4.4
0x68bc6  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.DefaultExtendedPropertySet, int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68bcb  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PidLidTaskAccepted
0x68bd0  ldc.i4   0x3FF8
0x68bd5  ldc.i4.s 0x19
0x68bd7  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68bdc  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_CREATOR_NAME
0x68be1  ldc.i4   0x1090
0x68be6  ldc.i4.s 0xE
0x68be8  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition::.ctor(int32, valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.MapiPropertyType)
0x68bed  stsfld   class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExtendedPropertyDefinition Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExtendedProperties::PR_FLAG_STATUS
0x68bf2  ldc.i4.1
0x68bf3  ldc.i4   0x8208
0x68bf8  ldc.i4.s 0x19
  ... truncated ...
```
