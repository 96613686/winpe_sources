# Microsoft.Crm.Caching.UserData::InitUserProperties

- ea: `0x92c00`
- end: `0x92f80`
- name: `Microsoft.Crm.Caching.UserData::InitUserProperties`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x929a0`

## callees

- `0x81f50`
- `0x81f60`
- `0x919b0`
- `0x919d0`
- `0x919f0`
- `0x91a10`
- `0x91a30`
- `0x91a70`
- `0x91a90`
- `0x91f70`
- `0x92050`
- `0x92070`
- `0x92090`
- `0x920b0`
- `0x920d0`
- `0x920f0`
- `0x92410`
- `0x92430`
- `0x926e0`
- `0x92700`
- `0x92720`
- `0x92740`
- `0x927a0`
- `0x927d0`
- `0x927f0`
- `0x92c00`

## string_xrefs

- `0x92e1a`: `incomingemaildeliverymethod`
- `0x92e28`: `incomingemaildeliverymethod`
- `0x92c24`: `activedirectoryguid`
- `0x92c32`: `activedirectoryguid`
- `0x92cb0`: `accessmode`
- `0x92cbe`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0x92c00  ldarg.1
0x92c01  ldstr    aBusinessunitid// "businessunitid"
0x92c06  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92c0b  brtrue.s loc_92C23
0x92c0d  ldarg.0
0x92c0e  ldarg.1
0x92c0f  ldstr    aBusinessunitid// "businessunitid"
0x92c14  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92c19  unbox.any [mscorlib]System.Guid
0x92c1e  call     instance void Microsoft.Crm.Caching.UserData::set_BusinessId(valuetype [mscorlib]System.Guid value)
0x92c23  ldarg.1
0x92c24  ldstr    aActivedirector_0// "activedirectoryguid"
0x92c29  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92c2e  brtrue.s loc_92C46
0x92c30  ldarg.0
0x92c31  ldarg.1
0x92c32  ldstr    aActivedirector_0// "activedirectoryguid"
0x92c37  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92c3c  unbox.any [mscorlib]System.Guid
0x92c41  call     instance void Microsoft.Crm.Caching.UserData::set_ActiveDirectoryId(valuetype [mscorlib]System.Guid value)
0x92c46  ldarg.1
0x92c47  ldstr    aSystemuserid// "systemuserid"
0x92c4c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92c51  brtrue.s loc_92C69
0x92c53  ldarg.0
0x92c54  ldarg.1
0x92c55  ldstr    aSystemuserid// "systemuserid"
0x92c5a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92c5f  unbox.any [mscorlib]System.Guid
0x92c64  call     instance void Microsoft.Crm.Caching.UserData::set_SystemUserId(valuetype [mscorlib]System.Guid value)
0x92c69  ldarg.1
0x92c6a  ldstr    aIsdisabled// "isdisabled"
0x92c6f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92c74  brtrue.s loc_92C8C
0x92c76  ldarg.0
0x92c77  ldarg.1
0x92c78  ldstr    aIsdisabled// "isdisabled"
0x92c7d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92c82  unbox.any [mscorlib]System.Boolean
0x92c87  call     instance void Microsoft.Crm.Caching.UserData::set_IsDisabled(bool value)
0x92c8c  ldarg.1
0x92c8d  ldstr    aIsintegrationu// "isintegrationuser"
0x92c92  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92c97  brtrue.s loc_92CAF
0x92c99  ldarg.0
0x92c9a  ldarg.1
0x92c9b  ldstr    aIsintegrationu// "isintegrationuser"
0x92ca0  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92ca5  unbox.any [mscorlib]System.Boolean
0x92caa  call     instance void Microsoft.Crm.Caching.UserData::set_IsIntegrationUser(bool value)
0x92caf  ldarg.1
0x92cb0  ldstr    aAccessmode// "accessmode"
0x92cb5  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92cba  brtrue.s loc_92CD2
0x92cbc  ldarg.0
0x92cbd  ldarg.1
0x92cbe  ldstr    aAccessmode// "accessmode"
0x92cc3  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92cc8  unbox.any [mscorlib]System.Int32
0x92ccd  call     instance void Microsoft.Crm.Caching.UserData::set_AccessMode(int32 value)
0x92cd2  ldarg.1
0x92cd3  ldstr    aDomainname// "domainname"
0x92cd8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92cdd  brtrue.s loc_92CF5
0x92cdf  ldarg.0
0x92ce0  ldarg.1
0x92ce1  ldstr    aDomainname// "domainname"
0x92ce6  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92ceb  castclass [mscorlib]System.String
0x92cf0  call     instance void Microsoft.Crm.Caching.UserData::set_DomainName(string value)
0x92cf5  ldarg.1
0x92cf6  ldstr    aFullname// "fullname"
0x92cfb  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92d00  brtrue.s loc_92D18
0x92d02  ldarg.0
0x92d03  ldarg.1
0x92d04  ldstr    aFullname// "fullname"
0x92d09  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92d0e  castclass [mscorlib]System.String
0x92d13  call     instance void Microsoft.Crm.Caching.UserData::set_UserName(string value)
0x92d18  ldarg.1
0x92d19  ldstr    aFirstname// "firstname"
0x92d1e  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92d23  brtrue.s loc_92D3B
0x92d25  ldarg.0
0x92d26  ldarg.1
0x92d27  ldstr    aFirstname// "firstname"
0x92d2c  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92d31  castclass [mscorlib]System.String
0x92d36  call     instance void Microsoft.Crm.Caching.UserData::set_FirstName(string value)
0x92d3b  ldarg.1
0x92d3c  ldstr    aLastname// "lastname"
0x92d41  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92d46  brtrue.s loc_92D5E
0x92d48  ldarg.0
0x92d49  ldarg.1
0x92d4a  ldstr    aLastname// "lastname"
0x92d4f  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92d54  castclass [mscorlib]System.String
0x92d59  call     instance void Microsoft.Crm.Caching.UserData::set_LastName(string value)
0x92d5e  ldarg.1
0x92d5f  ldstr    aInternalemaila// "internalemailaddress"
0x92d64  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92d69  brtrue.s loc_92DD3
0x92d6b  ldarg.0
0x92d6c  ldarg.1
0x92d6d  ldstr    aInternalemaila// "internalemailaddress"
0x92d72  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92d77  brfalse.s loc_92DBE
0x92d79  ldarg.1
0x92d7a  ldstr    aPersonalemaila// "personalemailaddress"
0x92d7f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92d84  brfalse.s loc_92DAC
0x92d86  ldarg.1
0x92d87  ldstr    aMobilealertema// "mobilealertemail"
0x92d8c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92d91  brfalse.s loc_92D9A
0x92d93  ldsfld   string [mscorlib]System.String::Empty
0x92d98  br.s     loc_92DCE
0x92d9a  ldarg.1
0x92d9b  ldstr    aMobilealertema// "mobilealertemail"
0x92da0  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92da5  castclass [mscorlib]System.String
0x92daa  br.s     loc_92DCE
0x92dac  ldarg.1
0x92dad  ldstr    aPersonalemaila// "personalemailaddress"
0x92db2  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92db7  castclass [mscorlib]System.String
0x92dbc  br.s     loc_92DCE
0x92dbe  ldarg.1
0x92dbf  ldstr    aInternalemaila// "internalemailaddress"
0x92dc4  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92dc9  castclass [mscorlib]System.String
0x92dce  call     instance void Microsoft.Crm.Caching.UserData::set_EmailAddress(string value)
0x92dd3  ldarg.1
0x92dd4  ldstr    aBusinessunitid_0// "businessunitidname"
0x92dd9  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92dde  brtrue.s loc_92DF6
0x92de0  ldarg.0
0x92de1  ldarg.1
0x92de2  ldstr    aBusinessunitid_0// "businessunitidname"
0x92de7  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92dec  castclass [mscorlib]System.String
0x92df1  call     instance void Microsoft.Crm.Caching.UserData::set_BusinessName(string value)
0x92df6  ldarg.1
0x92df7  ldstr    aQueueid// "queueid"
0x92dfc  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92e01  brtrue.s loc_92E19
0x92e03  ldarg.0
0x92e04  ldarg.1
0x92e05  ldstr    aQueueid// "queueid"
0x92e0a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92e0f  unbox.any [mscorlib]System.Guid
0x92e14  call     instance void Microsoft.Crm.Caching.UserData::set_DefaultQueue(valuetype [mscorlib]System.Guid value)
0x92e19  ldarg.1
0x92e1a  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x92e1f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92e24  brtrue.s loc_92E3C
0x92e26  ldarg.0
0x92e27  ldarg.1
0x92e28  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x92e2d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92e32  unbox.any [mscorlib]System.Int32
0x92e37  call     instance void Microsoft.Crm.Caching.UserData::set_IncomingEmailDeliveryMethod(valuetype Microsoft.Crm.Caching.EmailDeliveryMethod value)
0x92e3c  ldarg.1
0x92e3d  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x92e42  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92e47  brtrue.s loc_92E5F
0x92e49  ldarg.0
0x92e4a  ldarg.1
0x92e4b  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x92e50  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92e55  unbox.any [mscorlib]System.Int32
0x92e5a  call     instance void Microsoft.Crm.Caching.UserData::set_OutgoingEmailDeliveryMethod(valuetype Microsoft.Crm.Caching.EmailDeliveryMethod value)
0x92e5f  ldarg.1
0x92e60  ldstr    aDefaultmailbox// "defaultmailbox"
0x92e65  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92e6a  brtrue.s loc_92E82
0x92e6c  ldarg.0
0x92e6d  ldarg.1
0x92e6e  ldstr    aDefaultmailbox// "defaultmailbox"
0x92e73  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92e78  unbox.any [mscorlib]System.Guid
0x92e7d  call     instance void Microsoft.Crm.Caching.UserData::set_DefaultMailbox(valuetype [mscorlib]System.Guid value)
0x92e82  ldarg.1
0x92e83  ldstr    aIslicensed// "islicensed"
0x92e88  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92e8d  brtrue.s loc_92EA5
0x92e8f  ldarg.0
0x92e90  ldarg.1
0x92e91  ldstr    aIslicensed// "islicensed"
0x92e96  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92e9b  unbox.any [mscorlib]System.Boolean
0x92ea0  call     instance void Microsoft.Crm.Caching.UserData::set_IsLicensed(bool value)
0x92ea5  ldarg.1
0x92ea6  ldstr    aUserlicensetyp// "userlicensetype"
0x92eab  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92eb0  brtrue.s loc_92EC8
0x92eb2  ldarg.0
0x92eb3  ldarg.1
0x92eb4  ldstr    aUserlicensetyp// "userlicensetype"
0x92eb9  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92ebe  unbox.any [mscorlib]System.Int32
0x92ec3  call     instance void Microsoft.Crm.Caching.UserData::set_UserLicenseType(int32 value)
0x92ec8  ldarg.1
0x92ec9  ldstr    aCaltype// "caltype"
0x92ece  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92ed3  brtrue.s loc_92EEB
0x92ed5  ldarg.0
0x92ed6  ldarg.1
0x92ed7  ldstr    aCaltype// "caltype"
0x92edc  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92ee1  unbox.any [mscorlib]System.Int32
0x92ee6  call     instance void Microsoft.Crm.Caching.UserData::set_CalType(int32 value)
0x92eeb  ldarg.1
0x92eec  ldstr    aInvitestatusco// "invitestatuscode"
0x92ef1  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92ef6  brtrue.s loc_92F0E
0x92ef8  ldarg.0
0x92ef9  ldarg.1
0x92efa  ldstr    aInvitestatusco// "invitestatuscode"
0x92eff  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92f04  unbox.any [mscorlib]System.Int32
0x92f09  call     instance void Microsoft.Crm.Caching.UserData::set_InviteStatusCode(int32 value)
0x92f0e  ldarg.1
0x92f0f  ldstr    aYammeremailadd// "yammeremailaddress"
0x92f14  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92f19  brtrue.s loc_92F39
0x92f1b  ldarg.0
0x92f1c  ldarg.1
0x92f1d  ldstr    aYammeremailadd// "yammeremailaddress"
0x92f22  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92f27  castclass [mscorlib]System.String
0x92f2c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x92f31  ldc.i4.0
0x92f32  ceq
0x92f34  call     instance void Microsoft.Crm.Caching.UserData::set_IsYammerConfigured(bool value)
0x92f39  ldarg.1
0x92f3a  ldstr    aYammeremailadd// "yammeremailaddress"
0x92f3f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92f44  brtrue.s loc_92F5C
0x92f46  ldarg.0
0x92f47  ldarg.1
0x92f48  ldstr    aYammeremailadd// "yammeremailaddress"
0x92f4d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92f52  castclass [mscorlib]System.String
0x92f57  call     instance void Microsoft.Crm.Caching.UserData::set_YammerEmailAddress(string value)
0x92f5c  ldarg.1
0x92f5d  ldstr    aYammeruserid// "yammeruserid"
0x92f62  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x92f67  brtrue.s loc_92F7F
0x92f69  ldarg.0
0x92f6a  ldarg.1
0x92f6b  ldstr    aYammeruserid// "yammeruserid"
0x92f70  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x92f75  castclass [mscorlib]System.String
0x92f7a  call     instance void Microsoft.Crm.Caching.UserData::set_YammerUserId(string value)
0x92f7f  ret
```
