# Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::CreateItem

- ea: `0x62730`
- end: `0x62859`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::CreateItem`
- size: `297`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x602d0`
- `0x61d90`
- `0x620a0`

## callees

- `0x4da80`
- `0x58a20`
- `0x58b30`
- `0x60b90`
- `0x62580`
- `0x625c0`
- `0x62680`
- `0x62730`
- `0x63ca0`
- `0x70120`
- `0x702d0`
- `0x70300`

## string_xrefs

- `0x6275c`: `CreateItem`
- `0x62847`: `CreateItem`
- `0x62751`: `CreateRequest`
- `0x6283c`: `CreateRequest`
- `0x627bb`: `Created a crm {0} item {1} on the crm server for the mailbox : {2}.`
- `0x627ee`: `Failed to create a crm {0} item {1} on the crm server for the mailbox : {2}. Exception details : {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x62730  ldarg.1
0x62731  brtrue.s loc_6273E
0x62733  ldstr    aInvalidInput// "Invalid input."
0x62738  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x6273d  throw
0x6273e  ldarg.1
0x6273f  castclass Microsoft.Crm.Asynchronous.EmailConnector.CrmItem
0x62744  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.CrmItem::get_Entity()
0x62749  stloc.0
0x6274a  ldc.i4.0
0x6274b  ldarg.0
0x6274c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x62751  ldstr    aCreaterequest// "CreateRequest"
0x62756  ldloc.0
0x62757  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x6275c  ldstr    aCreateitem// "CreateItem"
0x62761  ldstr    asc_8A7C2// ""
0x62766  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x6276b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor()
0x62770  stloc.1
0x62771  ldarg.2
0x62772  brtrue.s loc_62785
0x62774  ldarg.0
0x62775  ldarg.1
0x62776  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x6277b  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::IsDuplicateDetectionEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x62780  brtrue.s loc_62785
0x62782  ldc.i4.1
0x62783  starg.s  2
0x62785  ldloc.1
0x62786  ldloc.0
0x62787  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x6278c  ldloc.1
0x6278d  ldstr    aSuppressduplic// "SuppressDuplicateDetection"
0x62792  ldarg.2
0x62793  box      [mscorlib]System.Boolean
0x62798  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x6279d  ldarg.0
0x6279e  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_CrmService()
0x627a3  ldloc.1
0x627a4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x627a9  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse
0x627ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse::get_id()
0x627b3  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x627b8  stloc.2
0x627b9  ldarg.0
0x627ba  ldc.i4.4
0x627bb  ldstr    aCreatedACrm0It// "Created a crm {0} item {1} on the crm s"...
0x627c0  ldc.i4.3
0x627c1  newarr   [mscorlib]System.Object
0x627c6  dup
0x627c7  ldc.i4.0
0x627c8  ldarg.1
0x627c9  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x627ce  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x627d3  stelem.ref
0x627d4  dup
0x627d5  ldc.i4.1
0x627d6  ldloc.2
0x627d7  stelem.ref
0x627d8  dup
0x627d9  ldc.i4.2
0x627da  ldarg.0
0x627db  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x627e0  stelem.ref
0x627e1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x627e6  ldloc.2
0x627e7  stloc.3
0x627e8  leave.s  loc_62857
0x627ea  stloc.s  4
0x627ec  ldarg.0
0x627ed  ldc.i4.2
0x627ee  ldstr    aFailedToCreate// "Failed to create a crm {0} item {1} on "...
0x627f3  ldc.i4.4
0x627f4  newarr   [mscorlib]System.Object
0x627f9  dup
0x627fa  ldc.i4.0
0x627fb  ldarg.1
0x627fc  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x62801  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x62806  stelem.ref
0x62807  dup
0x62808  ldc.i4.1
0x62809  ldarg.1
0x6280a  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x6280f  stelem.ref
0x62810  dup
0x62811  ldc.i4.2
0x62812  ldarg.0
0x62813  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::get_MailboxId()
0x62818  stelem.ref
0x62819  dup
0x6281a  ldc.i4.3
0x6281b  ldloc.s  4
0x6281d  ldarg.0
0x6281e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x62823  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x62828  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x6282d  stelem.ref
0x6282e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x62833  rethrow
0x62835  ldc.i4.1
0x62836  ldarg.0
0x62837  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::_context
0x6283c  ldstr    aCreaterequest// "CreateRequest"
0x62841  ldloc.0
0x62842  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x62847  ldstr    aCreateitem// "CreateItem"
0x6284c  ldstr    asc_8A7C2// ""
0x62851  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteCrmServiceExecuteEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string requestName, string entityType, string functionName, [opt] string functionParam)
0x62856  endfinally
0x62857  ldloc.3
0x62858  ret
```
