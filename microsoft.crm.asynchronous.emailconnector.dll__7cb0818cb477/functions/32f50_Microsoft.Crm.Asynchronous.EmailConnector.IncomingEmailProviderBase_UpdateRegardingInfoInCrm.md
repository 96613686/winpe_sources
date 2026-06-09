# Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::UpdateRegardingInfoInCrm

- ea: `0x32f50`
- end: `0x3347a`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::UpdateRegardingInfoInCrm`
- size: `1322`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xa6b0`
- `0x32680`
- `0x32970`
- `0x32980`
- `0x32d90`
- `0x32f50`
- `0x33480`
- `0x334f0`
- `0x33890`
- `0x35770`
- `0x35820`
- `0x35830`
- `0x40e10`
- `0x41a50`
- `0x41ab0`
- `0x4da80`
- `0x4e870`
- `0x4f410`
- `0x51800`
- `0x71c40`
- `0x71ff0`
- `0x81500`
- `0x81640`

## string_xrefs

- `0x330c7`: `Delete crm email message`
- `0x33307`: `Updated CRM email message`
- `0x33334`: `Mailbox: {0} - FaultException thrown from platform in UpdateRegardingInfo : {1}`
- `0x33378`: `EmailUpdateRegarding.FaultException.Error`

## pseudocode

```c

```

## disassembly

```asm
0x32f50  ldarg.2
0x32f51  brfalse.s loc_32F7A
0x32f53  ldarg.2
0x32f54  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x32f59  brfalse.s loc_32F7A
0x32f5b  ldarg.2
0x32f5c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x32f61  ldstr    aOwnerid// "ownerid"
0x32f66  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x32f6b  brfalse.s loc_32F7A
0x32f6d  ldarg.2
0x32f6e  ldstr    aOwnerid// "ownerid"
0x32f73  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x32f78  brtrue.s loc_32F81
0x32f7a  ldsfld   string [mscorlib]System.String::Empty
0x32f7f  br.s     loc_32FA4
0x32f81  ldarg.2
0x32f82  ldstr    aOwnerid// "ownerid"
0x32f87  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x32f8c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x32f91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x32f96  stloc.2
0x32f97  ldloca.s 2
0x32f99  constrained. [mscorlib]System.Guid
0x32f9f  callvirt instance string [mscorlib]System.Object::ToString()
0x32fa4  stloc.0
0x32fa5  ldarg.0
0x32fa6  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x32fab  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x32fb0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::GetMailboxData()
0x32fb5  stloc.1
0x32fb6  ldloc.0
0x32fb7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32fbc  brtrue.s loc_32FE1
0x32fbe  ldloc.1
0x32fbf  brfalse  loc_3305D
0x32fc4  ldloc.1
0x32fc5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OwnerId()
0x32fca  stloc.2
0x32fcb  ldloca.s 2
0x32fcd  constrained. [mscorlib]System.Guid
0x32fd3  callvirt instance string [mscorlib]System.Object::ToString()
0x32fd8  ldloc.0
0x32fd9  ldc.i4.5
0x32fda  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32fdf  brfalse.s loc_3305D
0x32fe1  ldloc.0
0x32fe2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32fe7  brtrue.s loc_3300A
0x32fe9  ldstr    aTheOwneridOfTh// "The ownerid of the CRM Entity {0} is no"...
0x32fee  ldloc.0
0x32fef  ldloc.1
0x32ff0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OwnerId()
0x32ff5  stloc.2
0x32ff6  ldloca.s 2
0x32ff8  constrained. [mscorlib]System.Guid
0x32ffe  callvirt instance string [mscorlib]System.Object::ToString()
0x33003  call     string [mscorlib]System.String::Format(string, object, object)
0x33008  br.s     loc_3300F
0x3300a  ldstr    aTheOwneridOfTh_0// "The ownerid of the CRM Entity is null o"...
0x3300f  stloc.3
0x33010  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x33015  stloc.s  4
0x33017  ldloc.s  4
0x33019  ldloc.3
0x3301a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3301f  pop
0x33020  ldarg.s  4
0x33022  brfalse.s loc_33039
0x33024  ldarg.0
0x33025  ldarg.2
0x33026  ldarg.3
0x33027  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::GetRegardingInfoForExchange(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity crmEmailEntity, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> regardingInfoForExchange)
0x3302c  ldloc.s  4
0x3302e  ldstr    aForFolderbased// " For FolderBasedTrackedEmail"
0x33033  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x33038  pop
0x33039  ldarg.0
0x3303a  ldarg.0
0x3303b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x33040  ldloc.s  4
0x33042  callvirt instance string [mscorlib]System.Object::ToString()
0x33047  ldc.i4.0
0x33048  ldc.i4.0
0x33049  ldstr    asc_8A7C2// ""
0x3304e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x33053  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x33058  leave    loc_33479
0x3305d  ldarg.1
0x3305e  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x33063  ldc.i4.3
0x33064  beq.s    loc_33072
0x33066  ldarg.1
0x33067  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x3306c  ldc.i4.4
0x3306d  bne.un   loc_33108
0x33072  ldarg.1
0x33073  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x33078  ldc.i4.4
0x33079  bne.un   loc_33418
0x3307e  ldarg.0
0x3307f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x33084  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x33089  ldloca.s 2
0x3308b  initobj  [mscorlib]System.Guid
0x33091  ldloc.2
0x33092  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.Utility::GetCrmService(valuetype [mscorlib]System.Guid organizationId, [opt] valuetype [mscorlib]System.Guid userId)
0x33097  stloc.s  5
0x33099  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0x3309e  dup
0x3309f  ldstr    aEmail// "email"
0x330a4  ldarg.2
0x330a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x330aa  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x330af  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x330b4  stloc.s  6
0x330b6  ldloc.s  5
0x330b8  ldloc.s  6
0x330ba  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x330bf  pop
0x330c0  ldarg.0
0x330c1  ldarg.0
0x330c2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x330c7  ldstr    aDeleteCrmEmail// "Delete crm email message"
0x330cc  ldc.i4.3
0x330cd  ldc.i4.0
0x330ce  ldstr    asc_8A7C2// ""
0x330d3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x330d8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x330dd  ldarg.0
0x330de  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_SyncResponse()
0x330e3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x330e8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse::set_TimeSyncedInCrm(valuetype [mscorlib]System.DateTime value)
0x330ed  leave    loc_33418
0x330f2  stloc.s  7
0x330f4  ldarg.0
0x330f5  ldloc.s  7
0x330f7  ldc.i4.1
0x330f8  ldstr    aDeletingCrmEma// "Deleting crm email message"
0x330fd  ldc.i4.3
0x330fe  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ProcessException(class [mscorlib]System.Exception e, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string errorMessage, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x33103  leave    loc_33418
0x33108  ldc.i4.0
0x33109  stloc.s  8
0x3310b  ldstr    aEmail// "email"
0x33110  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x33115  stloc.s  9
0x33117  ldarg.0
0x33118  ldarg.1
0x33119  ldloc.s  9
0x3311b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::GetRegardingProperties(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity extraProperties)
0x33120  ldarg.1
0x33121  callvirt instance int64 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_RegardingObjectTypeCode()
0x33126  brfalse  loc_33291
0x3312b  ldarg.2
0x3312c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x33131  ldstr    aRegardingobjec// "regardingobjectid"
0x33136  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3313b  brfalse  loc_33214
0x33140  ldloc.s  9
0x33142  ldstr    aRegardingobjec// "regardingobjectid"
0x33147  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x3314c  brfalse  loc_33214
0x33151  ldarg.2
0x33152  ldstr    aRegardingobjec// "regardingobjectid"
0x33157  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3315c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x33161  stloc.s  0xA
0x33163  ldloc.s  9
0x33165  ldstr    aRegardingobjec// "regardingobjectid"
0x3316a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3316f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x33174  stloc.s  0xB
0x33176  ldloc.s  0xA
0x33178  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x3317d  ldloc.s  0xB
0x3317f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x33184  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x33189  brtrue.s loc_331A3
0x3318b  ldloc.s  0xA
0x3318d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x33192  ldloc.s  0xB
0x33194  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x33199  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3319e  brfalse  loc_332CC
0x331a3  ldarg.2
0x331a4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x331a9  ldstr    aRegardingobjec// "regardingobjectid"
0x331ae  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x331b3  pop
0x331b4  ldarg.2
0x331b5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x331ba  ldstr    aRegardingobjec// "regardingobjectid"
0x331bf  ldloc.s  9
0x331c1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x331c6  ldstr    aRegardingobjec// "regardingobjectid"
0x331cb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x331d0  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::.ctor(var<u1>, !!T0)
0x331d5  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>)
0x331da  ldarg.3
0x331db  ldstr    aRegardingobjec// "regardingobjectid"
0x331e0  ldloc.s  0xA
0x331e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x331e7  stloc.2
0x331e8  ldloca.s 2
0x331ea  constrained. [mscorlib]System.Guid
0x331f0  callvirt instance string [mscorlib]System.Object::ToString()
0x331f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x331fa  ldarg.3
0x331fb  ldstr    aRegardingobjec_0// "regardingobjectidname"
0x33200  ldloc.s  0xA
0x33202  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Name()
0x33207  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3320c  ldc.i4.1
0x3320d  stloc.s  8
0x3320f  br       loc_332CC
0x33214  ldloc.s  9
0x33216  ldstr    aRegardingobjec// "regardingobjectid"
0x3321b  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x33220  brfalse.s loc_3324D
0x33222  ldarg.2
0x33223  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x33228  ldstr    aRegardingobjec// "regardingobjectid"
0x3322d  ldloc.s  9
0x3322f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x33234  ldstr    aRegardingobjec// "regardingobjectid"
0x33239  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3323e  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::.ctor(var<u1>, !!T0)
0x33243  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>)
0x33248  ldc.i4.1
0x33249  stloc.s  8
0x3324b  br.s     loc_332CC
0x3324d  ldarg.0
0x3324e  ldc.i4.2
0x3324f  ldstr    aNoRegardingObj// "No regarding object found in exchange e"...
0x33254  ldc.i4.3
0x33255  newarr   [mscorlib]System.Object
0x3325a  dup
0x3325b  ldc.i4.0
0x3325c  ldarg.0
0x3325d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33262  ldstr    aMailboxid// "mailboxid"
0x33267  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3326c  stelem.ref
0x3326d  dup
0x3326e  ldc.i4.1
0x3326f  ldloc.s  9
0x33271  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x33276  box      [mscorlib]System.Guid
0x3327b  stelem.ref
0x3327c  dup
0x3327d  ldc.i4.2
0x3327e  ldarg.1
0x3327f  callvirt instance int64 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_RegardingObjectTypeCode()
0x33284  box      [mscorlib]System.Int64
0x33289  stelem.ref
0x3328a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3328f  br.s     loc_332CC
0x33291  ldarg.1
0x33292  callvirt instance int64 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_RegardingObjectTypeCode()
0x33297  brtrue.s loc_332CC
0x33299  ldarg.2
0x3329a  ldstr    aRegardingobjec// "regardingobjectid"
0x3329f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x332a4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x332a9  ldarg.2
0x332aa  ldstr    aRegardingobjec_0// "regardingobjectidname"
0x332af  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x332b4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x332b9  ldarg.2
0x332ba  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x332bf  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x332c4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x332c9  ldc.i4.1
0x332ca  stloc.s  8
0x332cc  nop
0x332cd  ldloc.s  8
0x332cf  brfalse.s loc_3332D
0x332d1  ldarg.0
0x332d2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x332d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x332dc  ldloca.s 2
0x332de  initobj  [mscorlib]System.Guid
0x332e4  ldloc.2
0x332e5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.Utility::GetCrmService(valuetype [mscorlib]System.Guid organizationId, [opt] valuetype [mscorlib]System.Guid userId)
0x332ea  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x332ef  dup
0x332f0  ldarg.2
0x332f1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x332f6  stloc.s  0xC
0x332f8  ldloc.s  0xC
0x332fa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x332ff  pop
0x33300  ldarg.0
0x33301  ldarg.0
0x33302  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x33307  ldstr    aUpdatedCrmEmai// "Updated CRM email message"
0x3330c  ldc.i4.2
0x3330d  ldc.i4.0
0x3330e  ldstr    asc_8A7C2// ""
  ... truncated ...
```
