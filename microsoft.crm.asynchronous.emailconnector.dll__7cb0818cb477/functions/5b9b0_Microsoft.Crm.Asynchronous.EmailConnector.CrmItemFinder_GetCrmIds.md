# Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::GetCrmIds

- ea: `0x5b9b0`
- end: `0x5bb6d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmItemFinder::GetCrmIds`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x5b480`

## callees

- `0x4da80`
- `0x58a20`
- `0x58c10`
- `0x5b9b0`
- `0x5e4b0`
- `0x5e4c0`
- `0x5e610`

## string_xrefs

- `0x5ba08`: `DistinctPhysicalAndLogicalDeletesForExchangeSync`
- `0x5ba6e`: `Skipping delete for entity {0}, type {1}, and mailbox {2} because org opted in to skip logical deletes.`
- `0x5baa5`: `Got physical delete for entity {0}, type {1}, and mailbox : {2}, entity will be deleted in Exchange.`

## pseudocode

```c

```

## disassembly

```asm
0x5b9b0  ldarg.s  4
0x5b9b2  ldc.i4.0
0x5b9b3  stind.i4
0x5b9b4  ldarg.2
0x5b9b5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5b9ba  brfalse.s loc_5B9C7
0x5b9bc  ldstr    aInvalidInput// "Invalid input."
0x5b9c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5b9c6  throw
0x5b9c7  nop
0x5b9c8  ldc.i4.0
0x5b9c9  ldarg.0
0x5b9ca  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b9cf  ldstr    aGetcrmids// "GetCrmIds"
0x5b9d4  ldstr    asc_8A7C2// ""
0x5b9d9  ldstr    asc_8A7C2// ""
0x5b9de  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5b9e3  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x5b9e8  stloc.0
0x5b9e9  ldarg.3
0x5b9ea  ldc.i4.2
0x5b9eb  bne.un.s loc_5BA1F
0x5b9ed  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x5b9f2  ldarg.0
0x5b9f3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5b9f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5b9fd  ldarg.0
0x5b9fe  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5ba03  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x5ba08  ldstr    aDistinctphysic// "DistinctPhysicalAndLogicalDeletesForExc"...
0x5ba0d  ldc.i4.0
0x5ba0e  box      [mscorlib]System.Boolean
0x5ba13  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x5ba18  unbox.any [mscorlib]System.Boolean
0x5ba1d  br.s     loc_5BA20
0x5ba1f  ldc.i4.0
0x5ba20  stloc.1
0x5ba21  ldarg.1
0x5ba22  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x5ba27  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x5ba2c  stloc.2
0x5ba2d  br       loc_5BAFE
0x5ba32  ldloc.2
0x5ba33  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x5ba38  stloc.3
0x5ba39  ldarg.3
0x5ba3a  ldc.i4.2
0x5ba3b  bne.un   loc_5BAD0
0x5ba40  ldloc.1
0x5ba41  brfalse.s loc_5BAA3
0x5ba43  ldloc.3
0x5ba44  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x5ba49  ldstr    aVersionnumber// "versionnumber"
0x5ba4e  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5ba53  brfalse.s loc_5BAA3
0x5ba55  ldloc.3
0x5ba56  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x5ba5b  ldstr    aVersionnumber// "versionnumber"
0x5ba60  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5ba65  unbox.any [mscorlib]System.Int64
0x5ba6a  brtrue.s loc_5BAA3
0x5ba6c  ldarg.0
0x5ba6d  ldc.i4.3
0x5ba6e  ldstr    aSkippingDelete// "Skipping delete for entity {0}, type {1"...
0x5ba73  ldc.i4.3
0x5ba74  newarr   [mscorlib]System.Object
0x5ba79  dup
0x5ba7a  ldc.i4.0
0x5ba7b  ldloc.3
0x5ba7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x5ba81  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x5ba86  stelem.ref
0x5ba87  dup
0x5ba88  ldc.i4.1
0x5ba89  ldarg.2
0x5ba8a  stelem.ref
0x5ba8b  dup
0x5ba8c  ldc.i4.2
0x5ba8d  ldarg.0
0x5ba8e  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5ba93  stelem.ref
0x5ba94  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5ba99  ldarg.s  4
0x5ba9b  ldarg.s  4
0x5ba9d  ldind.i4
0x5ba9e  ldc.i4.1
0x5ba9f  add
0x5baa0  stind.i4
0x5baa1  br.s     loc_5BAFE
0x5baa3  ldarg.0
0x5baa4  ldc.i4.3
0x5baa5  ldstr    aGotPhysicalDel// "Got physical delete for entity {0}, typ"...
0x5baaa  ldc.i4.3
0x5baab  newarr   [mscorlib]System.Object
0x5bab0  dup
0x5bab1  ldc.i4.0
0x5bab2  ldloc.3
0x5bab3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x5bab8  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x5babd  stelem.ref
0x5babe  dup
0x5babf  ldc.i4.1
0x5bac0  ldarg.2
0x5bac1  stelem.ref
0x5bac2  dup
0x5bac3  ldc.i4.2
0x5bac4  ldarg.0
0x5bac5  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5baca  stelem.ref
0x5bacb  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5bad0  ldloc.3
0x5bad1  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x5bad6  ldarg.2
0x5bad7  ldc.i4.5
0x5bad8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x5badd  brtrue.s loc_5BAFE
0x5badf  ldloc.3
0x5bae0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x5bae5  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x5baea  stloc.s  4
0x5baec  ldloc.s  4
0x5baee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5baf3  brtrue.s loc_5BAFE
0x5baf5  ldloc.0
0x5baf6  ldloc.s  4
0x5baf8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x5bafd  pop
0x5bafe  ldloc.2
0x5baff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5bb04  brtrue   loc_5BA32
0x5bb09  leave.s  loc_5BB15
0x5bb0b  ldloc.2
0x5bb0c  brfalse.s loc_5BB14
0x5bb0e  ldloc.2
0x5bb0f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5bb14  endfinally
0x5bb15  ldloc.0
0x5bb16  stloc.s  5
0x5bb18  leave.s  loc_5BB6A
0x5bb1a  stloc.s  6
0x5bb1c  ldarg.0
0x5bb1d  ldc.i4.2
0x5bb1e  ldstr    aFailedToGetThe_5// "Failed to get the entity id list for th"...
0x5bb23  ldc.i4.2
0x5bb24  newarr   [mscorlib]System.Object
0x5bb29  dup
0x5bb2a  ldc.i4.0
0x5bb2b  ldarg.0
0x5bb2c  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5bb31  stelem.ref
0x5bb32  dup
0x5bb33  ldc.i4.1
0x5bb34  ldloc.s  6
0x5bb36  ldarg.0
0x5bb37  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5bb3c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5bb41  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x5bb46  stelem.ref
0x5bb47  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5bb4c  rethrow
0x5bb4e  ldc.i4.1
0x5bb4f  ldarg.0
0x5bb50  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5bb55  ldstr    aGetcrmids// "GetCrmIds"
0x5bb5a  ldstr    asc_8A7C2// ""
0x5bb5f  ldstr    asc_8A7C2// ""
0x5bb64  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5bb69  endfinally
0x5bb6a  ldloc.s  5
0x5bb6c  ret
```
