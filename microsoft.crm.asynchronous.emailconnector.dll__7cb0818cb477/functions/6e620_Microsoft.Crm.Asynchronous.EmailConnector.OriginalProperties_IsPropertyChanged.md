# Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged

- ea: `0x6e620`
- end: `0x6e910`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::IsPropertyChanged`
- size: `752`
- prototype: ``
- caller_count: `14`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x5fa20`
- `0x5fcf0`
- `0x60e70`
- `0x63f60`
- `0x64590`
- `0x647f0`
- `0x64840`
- `0x64e30`
- `0x64e90`
- `0x65c30`
- `0x65d90`
- `0x69b10`
- `0x70390`
- `0x705c0`

## callees

- `0x7d00`
- `0x417a0`
- `0x42280`
- `0x4d8c0`
- `0x4da80`
- `0x6e160`
- `0x6e200`
- `0x6e250`
- `0x6e270`
- `0x6e280`
- `0x6e2f0`
- `0x6e380`
- `0x6e620`
- `0x6e910`

## string_xrefs

- `0x6e645`: `scheduledstart`
- `0x6e64d`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x6e620  ldarg.0
0x6e621  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_PropertiesMap()
0x6e626  ldarg.1
0x6e627  ldloca.s 0
0x6e629  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x6e62e  brfalse.s loc_6E63B
0x6e630  ldloc.0
0x6e631  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e636  ldc.i4.0
0x6e637  ceq
0x6e639  br.s     loc_6E63C
0x6e63b  ldc.i4.0
0x6e63c  stloc.1
0x6e63d  ldc.i4.7
0x6e63e  newarr   [mscorlib]System.String
0x6e643  dup
0x6e644  ldc.i4.0
0x6e645  ldstr    aScheduledstart// "scheduledstart"
0x6e64a  stelem.ref
0x6e64b  dup
0x6e64c  ldc.i4.1
0x6e64d  ldstr    aScheduledend// "scheduledend"
0x6e652  stelem.ref
0x6e653  dup
0x6e654  ldc.i4.2
0x6e655  ldstr    aAnniversary// "anniversary"
0x6e65a  stelem.ref
0x6e65b  dup
0x6e65c  ldc.i4.3
0x6e65d  ldstr    aBirthdate// "birthdate"
0x6e662  stelem.ref
0x6e663  dup
0x6e664  ldc.i4.4
0x6e665  ldstr    aPatternstartda// "patternstartdate"
0x6e66a  stelem.ref
0x6e66b  dup
0x6e66c  ldc.i4.5
0x6e66d  ldstr    aPatternenddate// "patternenddate"
0x6e672  stelem.ref
0x6e673  dup
0x6e674  ldc.i4.6
0x6e675  ldstr    aActualend// "actualend"
0x6e67a  stelem.ref
0x6e67b  ldarg.1
0x6e67c  call     T0x2B000079
0x6e681  stloc.2
0x6e682  ldloc.2
0x6e683  brfalse.s loc_6E6E3
0x6e685  ldarg.2
0x6e686  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e68b  brtrue.s loc_6E6E3
0x6e68d  ldarg.2
0x6e68e  ldloca.s 4
0x6e690  call     bool [mscorlib]System.DateTime::TryParse(string, valuetype [mscorlib]System.DateTime&)
0x6e695  brfalse.s loc_6E6E3
0x6e697  ldloc.s  4
0x6e699  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::CrmMinValue
0x6e69e  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x6e6a3  brfalse.s loc_6E6E3
0x6e6a5  ldarg.0
0x6e6a6  ldc.i4.2
0x6e6a7  ldstr    aDatetimeValue0// "Datetime value {0} for Attribute {1} is"...
0x6e6ac  ldc.i4.4
0x6e6ad  newarr   [mscorlib]System.Object
0x6e6b2  dup
0x6e6b3  ldc.i4.0
0x6e6b4  ldloc.s  4
0x6e6b6  box      [mscorlib]System.DateTime
0x6e6bb  stelem.ref
0x6e6bc  dup
0x6e6bd  ldc.i4.1
0x6e6be  ldarg.1
0x6e6bf  stelem.ref
0x6e6c0  dup
0x6e6c1  ldc.i4.2
0x6e6c2  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::CrmMinValue
0x6e6c7  box      [mscorlib]System.DateTime
0x6e6cc  stelem.ref
0x6e6cd  dup
0x6e6ce  ldc.i4.3
0x6e6cf  ldarg.0
0x6e6d0  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_MailboxId()
0x6e6d5  stelem.ref
0x6e6d6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6e6db  ldc.i4.0
0x6e6dc  stloc.s  5
0x6e6de  leave    loc_6E90D
0x6e6e3  ldarg.1
0x6e6e4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e6e9  brtrue   loc_6E7C9
0x6e6ee  ldarg.0
0x6e6ef  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::isEntityEnabledForFieldLevelSecurity
0x6e6f4  brfalse  loc_6E7C9
0x6e6f9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x6e6fe  ldarg.0
0x6e6ff  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_Context()
0x6e704  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x6e709  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x6e70e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_RegardingObjectId()
0x6e713  ldarg.0
0x6e714  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_Context()
0x6e719  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6e71e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x6e723  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x6e728  stloc.s  6
0x6e72a  ldarg.0
0x6e72b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.IFieldLevelSecurityHelper Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_ExchangeSyncFLSChecker()
0x6e730  ldarg.1
0x6e731  ldloc.s  6
0x6e733  ldarg.0
0x6e734  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityRequestType Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::_requestType
0x6e739  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.IFieldLevelSecurityHelper::IsAttributeSecured(string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityRequestType)
0x6e73e  brfalse  loc_6E7C9
0x6e743  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::ClientContextOrganizationId
0x6e748  ldarg.0
0x6e749  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_Context()
0x6e74e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x6e753  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x6e758  ldarg.0
0x6e759  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_Context()
0x6e75e  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x6e763  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x6e768  ldc.i4.1
0x6e769  ldc.i4.4
0x6e76a  ldstr    aCurrentUserDoe// "Current user does not have {0} permissi"...
0x6e76f  ldc.i4.3
0x6e770  newarr   [mscorlib]System.Object
0x6e775  dup
0x6e776  ldc.i4.0
0x6e777  ldarg.0
0x6e778  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityRequestType Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::_requestType
0x6e77d  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityRequestType
0x6e782  stelem.ref
0x6e783  dup
0x6e784  ldc.i4.1
0x6e785  ldarg.1
0x6e786  stelem.ref
0x6e787  dup
0x6e788  ldc.i4.2
0x6e789  ldarg.0
0x6e78a  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_EntityName()
0x6e78f  stelem.ref
0x6e790  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6e795  ldarg.2
0x6e796  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e79b  brfalse.s loc_6E7AC
0x6e79d  ldarg.0
0x6e79e  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityRequestType Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::_requestType
0x6e7a3  ldc.i4.3
0x6e7a4  bne.un.s loc_6E7AC
0x6e7a6  ldloc.1
0x6e7a7  ldc.i4.0
0x6e7a8  ceq
0x6e7aa  br.s     loc_6E7AD
0x6e7ac  ldc.i4.0
0x6e7ad  ldloc.2
0x6e7ae  and
0x6e7af  brfalse.s loc_6E7B9
0x6e7b1  ldc.i4.0
0x6e7b2  stloc.s  5
0x6e7b4  leave    loc_6E90D
0x6e7b9  ldarg.0
0x6e7ba  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityRequestType Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::_requestType
0x6e7bf  ldc.i4.3
0x6e7c0  ceq
0x6e7c2  stloc.s  5
0x6e7c4  leave    loc_6E90D
0x6e7c9  ldarg.2
0x6e7ca  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e7cf  ldc.i4.0
0x6e7d0  ceq
0x6e7d2  stloc.3
0x6e7d3  ldloc.2
0x6e7d4  brfalse  loc_6E85C
0x6e7d9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x6e7de  stloc.s  7
0x6e7e0  ldloc.3
0x6e7e1  ldc.i4.0
0x6e7e2  ceq
0x6e7e4  call     valuetype [System.Data]System.Data.SqlTypes.SqlBoolean [System.Data]System.Data.SqlTypes.SqlBoolean::op_Implicit(bool)
0x6e7e9  stloc.s  8
0x6e7eb  ldloc.s  8
0x6e7ed  call     bool [System.Data]System.Data.SqlTypes.SqlBoolean::op_True(valuetype [System.Data]System.Data.SqlTypes.SqlBoolean)
0x6e7f2  brtrue.s loc_6E831
0x6e7f4  ldloc.s  8
0x6e7f6  ldarg.2
0x6e7f7  ldloca.s 7
0x6e7f9  call     bool [mscorlib]System.DateTime::TryParse(string, valuetype [mscorlib]System.DateTime&)
0x6e7fe  call     valuetype [System.Data]System.Data.SqlTypes.SqlBoolean [System.Data]System.Data.SqlTypes.SqlBoolean::op_Implicit(bool)
0x6e803  stloc.s  9
0x6e805  ldloc.s  9
0x6e807  call     bool [System.Data]System.Data.SqlTypes.SqlBoolean::op_False(valuetype [System.Data]System.Data.SqlTypes.SqlBoolean)
0x6e80c  brtrue.s loc_6E828
0x6e80e  ldloc.s  9
0x6e810  ldloc.s  7
0x6e812  call     valuetype [System.Data]System.Data.SqlTypes.SqlDateTime [System.Data]System.Data.SqlTypes.SqlDateTime::op_Implicit(valuetype [mscorlib]System.DateTime)
0x6e817  ldsfld   valuetype [System.Data]System.Data.SqlTypes.SqlDateTime [System.Data]System.Data.SqlTypes.SqlDateTime::MinValue
0x6e81c  call     valuetype [System.Data]System.Data.SqlTypes.SqlBoolean [System.Data]System.Data.SqlTypes.SqlDateTime::op_LessThan(valuetype [System.Data]System.Data.SqlTypes.SqlDateTime, valuetype [System.Data]System.Data.SqlTypes.SqlDateTime)
0x6e821  call     valuetype [System.Data]System.Data.SqlTypes.SqlBoolean [System.Data]System.Data.SqlTypes.SqlBoolean::op_BitwiseAnd(valuetype [System.Data]System.Data.SqlTypes.SqlBoolean, valuetype [System.Data]System.Data.SqlTypes.SqlBoolean)
0x6e826  br.s     loc_6E82A
0x6e828  ldloc.s  9
0x6e82a  call     valuetype [System.Data]System.Data.SqlTypes.SqlBoolean [System.Data]System.Data.SqlTypes.SqlBoolean::op_BitwiseOr(valuetype [System.Data]System.Data.SqlTypes.SqlBoolean, valuetype [System.Data]System.Data.SqlTypes.SqlBoolean)
0x6e82f  br.s     loc_6E833
0x6e831  ldloc.s  8
0x6e833  call     bool [System.Data]System.Data.SqlTypes.SqlBoolean::op_True(valuetype [System.Data]System.Data.SqlTypes.SqlBoolean)
0x6e838  brfalse.s loc_6E842
0x6e83a  ldc.i4.0
0x6e83b  stloc.s  5
0x6e83d  leave    loc_6E90D
0x6e842  ldloc.1
0x6e843  brfalse.s loc_6E84F
0x6e845  ldloc.0
0x6e846  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6e84b  ldc.i4.s 0x13
0x6e84d  bgt.s    loc_6E852
0x6e84f  ldloc.0
0x6e850  br.s     loc_6E85B
0x6e852  ldloc.0
0x6e853  ldc.i4.0
0x6e854  ldc.i4.s 0x13
0x6e856  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6e85b  stloc.0
0x6e85c  ldloc.1
0x6e85d  ldc.i4.0
0x6e85e  ceq
0x6e860  ldloc.3
0x6e861  and
0x6e862  brtrue.s loc_6E86A
0x6e864  ldloc.1
0x6e865  brfalse.s loc_6E872
0x6e867  ldloc.3
0x6e868  brtrue.s loc_6E872
0x6e86a  ldc.i4.1
0x6e86b  stloc.s  5
0x6e86d  leave    loc_6E90D
0x6e872  ldloc.1
0x6e873  ldloc.3
0x6e874  and
0x6e875  brfalse.s loc_6E899
0x6e877  ldarg.3
0x6e878  brfalse.s loc_6E88C
0x6e87a  ldarg.3
0x6e87b  ldloc.0
0x6e87c  ldarg.2
0x6e87d  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.PropertyCompare::Invoke(string oldValue, string newValue)
0x6e882  ldc.i4.0
0x6e883  ceq
0x6e885  stloc.s  5
0x6e887  leave    loc_6E90D
0x6e88c  ldarg.0
0x6e88d  ldarg.1
0x6e88e  ldloc.0
0x6e88f  ldarg.2
0x6e890  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::Compare(string propertyName, string oldValue, string newValue)
0x6e895  stloc.s  5
0x6e897  leave.s  loc_6E90D
0x6e899  leave.s  loc_6E90B
0x6e89b  stloc.s  0xA
0x6e89d  ldarg.0
0x6e89e  ldc.i4.1
0x6e89f  ldstr    aExceptionDetai// "Exception details : {0} Mailbox {1}"
0x6e8a4  ldc.i4.2
0x6e8a5  newarr   [mscorlib]System.Object
0x6e8aa  dup
0x6e8ab  ldc.i4.0
0x6e8ac  ldloc.s  0xA
0x6e8ae  ldarg.0
0x6e8af  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::_context
0x6e8b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6e8b9  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x6e8be  stelem.ref
0x6e8bf  dup
0x6e8c0  ldc.i4.1
0x6e8c1  ldarg.0
0x6e8c2  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_MailboxId()
0x6e8c7  stelem.ref
0x6e8c8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6e8cd  rethrow
0x6e8cf  stloc.s  0xB
0x6e8d1  ldarg.0
0x6e8d2  ldc.i4.2
0x6e8d3  ldstr    aFailedToCheckT_0// "Failed to check the property {0} : {1} "...
0x6e8d8  ldc.i4.4
0x6e8d9  newarr   [mscorlib]System.Object
0x6e8de  dup
0x6e8df  ldc.i4.0
0x6e8e0  ldarg.1
0x6e8e1  stelem.ref
0x6e8e2  dup
0x6e8e3  ldc.i4.1
0x6e8e4  ldarg.2
0x6e8e5  stelem.ref
0x6e8e6  dup
0x6e8e7  ldc.i4.2
0x6e8e8  ldarg.0
0x6e8e9  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.OriginalProperties::get_MailboxId()
0x6e8ee  stelem.ref
0x6e8ef  dup
0x6e8f0  ldc.i4.3
0x6e8f1  ldloc.s  0xB
  ... truncated ...
```
