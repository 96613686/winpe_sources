# Microsoft.Crm.Caching.MailboxCacheData::Initialize

- ea: `0x84ad0`
- end: `0x85112`
- name: `Microsoft.Crm.Caching.MailboxCacheData::Initialize`
- size: `1602`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x81f50`
- `0x81f60`
- `0x84ad0`

## string_xrefs

- `0x84b5d`: `enabledforincomingemail`
- `0x84b6b`: `enabledforincomingemail`
- `0x84b80`: `incomingemaildeliverymethod`
- `0x84b8e`: `incomingemaildeliverymethod`
- `0x84bc6`: `incomingemailstatus`
- `0x84bd4`: `incomingemailstatus`
- `0x84c9d`: `processanddeleteemails`
- `0x84cab`: `processanddeleteemails`
- `0x84d39`: `emailrouteraccessapproval`
- `0x84d47`: `emailrouteraccessapproval`
- `0x84f46`: `lastsuccessfulsynccompletedon`
- `0x84f54`: `lastsuccessfulsynccompletedon`
- `0x85018`: `isserviceaccount`
- `0x85026`: `isserviceaccount`
- `0x8505e`: `isexchangecontactsimportscheduled`
- `0x8506c`: `isexchangecontactsimportscheduled`
- `0x850a4`: `exchangecontactsimportcompletedon`
- `0x850b2`: `exchangecontactsimportcompletedon`

## pseudocode

```c

```

## disassembly

```asm
0x84ad0  ldarg.1
0x84ad1  ldstr    aMailboxid// "mailboxid"
0x84ad6  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84adb  brtrue.s loc_84AF3
0x84add  ldarg.0
0x84ade  ldarg.1
0x84adf  ldstr    aMailboxid// "mailboxid"
0x84ae4  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84ae9  unbox.any [mscorlib]System.Guid
0x84aee  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.MailboxCacheData::_mailboxId
0x84af3  ldarg.1
0x84af4  ldstr    aName_0// "name"
0x84af9  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84afe  brtrue.s loc_84B16
0x84b00  ldarg.0
0x84b01  ldarg.1
0x84b02  ldstr    aName_0// "name"
0x84b07  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84b0c  castclass [mscorlib]System.String
0x84b11  stfld    string Microsoft.Crm.Caching.MailboxCacheData::_name
0x84b16  ldarg.1
0x84b17  ldstr    aEmailaddress// "emailaddress"
0x84b1c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84b21  brtrue.s loc_84B39
0x84b23  ldarg.0
0x84b24  ldarg.1
0x84b25  ldstr    aEmailaddress// "emailaddress"
0x84b2a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84b2f  castclass [mscorlib]System.String
0x84b34  stfld    string Microsoft.Crm.Caching.MailboxCacheData::_emailAddress
0x84b39  ldarg.1
0x84b3a  ldstr    aEmailserverpro_0// "emailserverprofile"
0x84b3f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84b44  brtrue.s loc_84B5C
0x84b46  ldarg.0
0x84b47  ldarg.1
0x84b48  ldstr    aEmailserverpro_0// "emailserverprofile"
0x84b4d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84b52  unbox.any [mscorlib]System.Guid
0x84b57  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.MailboxCacheData::_emailServerProfileId
0x84b5c  ldarg.1
0x84b5d  ldstr    aEnabledforinco// "enabledforincomingemail"
0x84b62  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84b67  brtrue.s loc_84B7F
0x84b69  ldarg.0
0x84b6a  ldarg.1
0x84b6b  ldstr    aEnabledforinco// "enabledforincomingemail"
0x84b70  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84b75  unbox.any [mscorlib]System.Boolean
0x84b7a  stfld    bool Microsoft.Crm.Caching.MailboxCacheData::_enabledForIncomingEmail
0x84b7f  ldarg.1
0x84b80  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x84b85  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84b8a  brtrue.s loc_84BA2
0x84b8c  ldarg.0
0x84b8d  ldarg.1
0x84b8e  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x84b93  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84b98  unbox.any Microsoft.Crm.Caching.EmailDeliveryMethod
0x84b9d  stfld    valuetype Microsoft.Crm.Caching.EmailDeliveryMethod Microsoft.Crm.Caching.MailboxCacheData::_incomingEmailDeliveryMethodKey
0x84ba2  ldarg.1
0x84ba3  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x84ba8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84bad  brtrue.s loc_84BC5
0x84baf  ldarg.0
0x84bb0  ldarg.1
0x84bb1  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x84bb6  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84bbb  unbox.any Microsoft.Crm.Caching.EmailDeliveryMethod
0x84bc0  stfld    valuetype Microsoft.Crm.Caching.EmailDeliveryMethod Microsoft.Crm.Caching.MailboxCacheData::_outgoingEmailDeliveryMethodKey
0x84bc5  ldarg.1
0x84bc6  ldstr    aIncomingemails// "incomingemailstatus"
0x84bcb  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84bd0  brtrue.s loc_84BE8
0x84bd2  ldarg.0
0x84bd3  ldarg.1
0x84bd4  ldstr    aIncomingemails// "incomingemailstatus"
0x84bd9  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84bde  unbox.any Microsoft.Crm.Caching.MailboxAccessStatus
0x84be3  stfld    valuetype Microsoft.Crm.Caching.MailboxAccessStatus Microsoft.Crm.Caching.MailboxCacheData::_incomingEmailStatusKey
0x84be8  ldarg.1
0x84be9  ldstr    aActdeliverymet// "actdeliverymethod"
0x84bee  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84bf3  brtrue.s loc_84C0B
0x84bf5  ldarg.0
0x84bf6  ldarg.1
0x84bf7  ldstr    aActdeliverymet// "actdeliverymethod"
0x84bfc  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84c01  unbox.any Microsoft.Crm.Caching.ACTDeliveryMethod
0x84c06  stfld    valuetype Microsoft.Crm.Caching.ACTDeliveryMethod Microsoft.Crm.Caching.MailboxCacheData::_actDeliveryMethodKey
0x84c0b  ldarg.1
0x84c0c  ldstr    aActstatus// "actstatus"
0x84c11  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84c16  brtrue.s loc_84C2E
0x84c18  ldarg.0
0x84c19  ldarg.1
0x84c1a  ldstr    aActstatus// "actstatus"
0x84c1f  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84c24  unbox.any Microsoft.Crm.Caching.MailboxAccessStatus
0x84c29  stfld    valuetype Microsoft.Crm.Caching.MailboxAccessStatus Microsoft.Crm.Caching.MailboxCacheData::_actStatus
0x84c2e  ldarg.1
0x84c2f  ldstr    aIsforwardmailb// "isforwardmailbox"
0x84c34  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84c39  brtrue.s loc_84C51
0x84c3b  ldarg.0
0x84c3c  ldarg.1
0x84c3d  ldstr    aIsforwardmailb// "isforwardmailbox"
0x84c42  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84c47  unbox.any [mscorlib]System.Boolean
0x84c4c  stfld    bool Microsoft.Crm.Caching.MailboxCacheData::_isForwardMailbox
0x84c51  ldarg.1
0x84c52  ldstr    aUsername// "username"
0x84c57  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84c5c  brtrue.s loc_84C74
0x84c5e  ldarg.0
0x84c5f  ldarg.1
0x84c60  ldstr    aUsername// "username"
0x84c65  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84c6a  castclass [mscorlib]System.String
0x84c6f  stfld    string Microsoft.Crm.Caching.MailboxCacheData::_userName
0x84c74  ldarg.1
0x84c75  ldstr    aPassword// "password"
0x84c7a  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84c7f  brtrue.s loc_84C9C
0x84c81  ldarg.0
0x84c82  ldarg.1
0x84c83  ldstr    aPassword// "password"
0x84c88  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84c8d  castclass [mscorlib]System.String
0x84c92  call     class [mscorlib]System.Security.SecureString [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::StringToSecureString(string)
0x84c97  stfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.Caching.MailboxCacheData::_password
0x84c9c  ldarg.1
0x84c9d  ldstr    aProcessanddele// "processanddeleteemails"
0x84ca2  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84ca7  brtrue.s loc_84CBF
0x84ca9  ldarg.0
0x84caa  ldarg.1
0x84cab  ldstr    aProcessanddele// "processanddeleteemails"
0x84cb0  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84cb5  unbox.any [mscorlib]System.Boolean
0x84cba  stfld    bool Microsoft.Crm.Caching.MailboxCacheData::_processandDeleteEmailsKey
0x84cbf  ldarg.1
0x84cc0  ldstr    aRegardingobjec// "regardingobjectid"
0x84cc5  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84cca  brtrue.s loc_84CE2
0x84ccc  ldarg.0
0x84ccd  ldarg.1
0x84cce  ldstr    aRegardingobjec// "regardingobjectid"
0x84cd3  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84cd8  unbox.any [mscorlib]System.Guid
0x84cdd  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.MailboxCacheData::_regardingObjectId
0x84ce2  ldarg.1
0x84ce3  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0x84ce8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84ced  brtrue.s loc_84D05
0x84cef  ldarg.0
0x84cf0  ldarg.1
0x84cf1  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0x84cf6  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84cfb  unbox.any [mscorlib]System.Int32
0x84d00  stfld    int32 Microsoft.Crm.Caching.MailboxCacheData::_regardingObjectTypeCode
0x84d05  ldarg.1
0x84d06  ldstr    aStatecode// "statecode"
0x84d0b  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84d10  brtrue.s loc_84D38
0x84d12  ldarg.0
0x84d13  ldarg.1
0x84d14  ldstr    aStatecode// "statecode"
0x84d19  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84d1e  callvirt instance string [mscorlib]System.Object::ToString()
0x84d23  ldstr    a0_0// "0"
0x84d28  callvirt instance bool [mscorlib]System.String::Equals(string)
0x84d2d  brtrue.s loc_84D32
0x84d2f  ldc.i4.0
0x84d30  br.s     loc_84D33
0x84d32  ldc.i4.1
0x84d33  stfld    bool Microsoft.Crm.Caching.MailboxCacheData::_isMailboxActivated
0x84d38  ldarg.1
0x84d39  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x84d3e  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84d43  brtrue.s loc_84D5B
0x84d45  ldarg.0
0x84d46  ldarg.1
0x84d47  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x84d4c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84d51  unbox.any Microsoft.Crm.Caching.EmailRouterAccessApproval
0x84d56  stfld    valuetype Microsoft.Crm.Caching.EmailRouterAccessApproval Microsoft.Crm.Caching.MailboxCacheData::_emailRouterAccessApproval
0x84d5b  ldarg.1
0x84d5c  ldstr    aAllowemailconn// "allowemailconnectortousecredentials"
0x84d61  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84d66  brtrue.s loc_84D7E
0x84d68  ldarg.0
0x84d69  ldarg.1
0x84d6a  ldstr    aAllowemailconn// "allowemailconnectortousecredentials"
0x84d6f  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84d74  unbox.any [mscorlib]System.Boolean
0x84d79  stfld    bool Microsoft.Crm.Caching.MailboxCacheData::_allowEmailConnectorToUseCredentials
0x84d7e  ldarg.1
0x84d7f  ldstr    aOwnerid// "ownerid"
0x84d84  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84d89  brtrue.s loc_84DA1
0x84d8b  ldarg.0
0x84d8c  ldarg.1
0x84d8d  ldstr    aOwnerid// "ownerid"
0x84d92  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84d97  unbox.any [mscorlib]System.Guid
0x84d9c  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.MailboxCacheData::_ownerId
0x84da1  ldarg.1
0x84da2  ldstr    aOwneridtype// "owneridtype"
0x84da7  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84dac  brtrue.s loc_84DC4
0x84dae  ldarg.0
0x84daf  ldarg.1
0x84db0  ldstr    aOwneridtype// "owneridtype"
0x84db5  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84dba  unbox.any [mscorlib]System.Int32
0x84dbf  stfld    int32 Microsoft.Crm.Caching.MailboxCacheData::_ownerType
0x84dc4  ldarg.1
0x84dc5  ldstr    aUndeliverablef// "undeliverablefolder"
0x84dca  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84dcf  brtrue.s loc_84DE7
0x84dd1  ldarg.0
0x84dd2  ldarg.1
0x84dd3  ldstr    aUndeliverablef// "undeliverablefolder"
0x84dd8  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84ddd  castclass [mscorlib]System.String
0x84de2  stfld    string Microsoft.Crm.Caching.MailboxCacheData::_undeliverableFolder
0x84de7  ldarg.1
0x84de8  ldstr    aEwsurl// "ewsurl"
0x84ded  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84df2  brtrue.s loc_84E0A
0x84df4  ldarg.0
0x84df5  ldarg.1
0x84df6  ldstr    aEwsurl// "ewsurl"
0x84dfb  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84e00  castclass [mscorlib]System.String
0x84e05  stfld    string Microsoft.Crm.Caching.MailboxCacheData::_ewsUrl
0x84e0a  ldarg.1
0x84e0b  ldstr    aLastautodiscov// "lastautodiscoveredon"
0x84e10  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84e15  brtrue.s loc_84E2D
0x84e17  ldarg.0
0x84e18  ldarg.1
0x84e19  ldstr    aLastautodiscov// "lastautodiscoveredon"
0x84e1e  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84e23  unbox.any [mscorlib]System.DateTime
0x84e28  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Caching.MailboxCacheData::_lastAutoDiscoveredOn
0x84e2d  ldarg.1
0x84e2e  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x84e33  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84e38  brtrue.s loc_84E50
0x84e3a  ldarg.0
0x84e3b  ldarg.1
0x84e3c  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x84e41  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84e46  unbox.any [mscorlib]System.Boolean
0x84e4b  stfld    bool Microsoft.Crm.Caching.MailboxCacheData::_isEmailAddressApprovedByO365Admin
0x84e50  ldarg.1
0x84e51  ldstr    aLastsyncerror// "lastsyncerror"
0x84e56  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84e5b  brtrue.s loc_84E73
0x84e5d  ldarg.0
0x84e5e  ldarg.1
0x84e5f  ldstr    aLastsyncerror// "lastsyncerror"
0x84e64  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84e69  castclass [mscorlib]System.String
0x84e6e  stfld    string Microsoft.Crm.Caching.MailboxCacheData::_lastSyncError
0x84e73  ldarg.1
0x84e74  ldstr    aLastsyncerrorc// "lastsyncerrorcount"
0x84e79  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84e7e  brtrue.s loc_84E96
0x84e80  ldarg.0
0x84e81  ldarg.1
0x84e82  ldstr    aLastsyncerrorc// "lastsyncerrorcount"
0x84e87  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84e8c  unbox.any [mscorlib]System.Int32
0x84e91  stfld    int32 Microsoft.Crm.Caching.MailboxCacheData::_lastSyncErrorCount
0x84e96  ldarg.1
0x84e97  ldstr    aLastsyncerrorc_0// "lastsyncerrorcode"
0x84e9c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84ea1  brtrue.s loc_84EB9
0x84ea3  ldarg.0
0x84ea4  ldarg.1
0x84ea5  ldstr    aLastsyncerrorc_0// "lastsyncerrorcode"
0x84eaa  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84eaf  unbox.any [mscorlib]System.Int32
0x84eb4  stfld    int32 Microsoft.Crm.Caching.MailboxCacheData::_lastSyncErrorCode
0x84eb9  ldarg.1
0x84eba  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x84ebf  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x84ec4  brtrue.s loc_84EDC
0x84ec6  ldarg.0
0x84ec7  ldarg.1
0x84ec8  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x84ecd  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x84ed2  unbox.any [mscorlib]System.DateTime
0x84ed7  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Caching.MailboxCacheData::_lastSyncErrorOccurredOn
0x84edc  ldarg.1
0x84edd  ldstr    aLastsyncerrorm// "lastsyncerrormachinename"
0x84ee2  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
  ... truncated ...
```
