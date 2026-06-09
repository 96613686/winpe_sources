# Microsoft.Crm.Common.Application.WebServices.QueueItemWebService::GetQueueItemId

- ea: `0x10`
- end: `0x69`
- name: `Microsoft.Crm.Common.Application.WebServices.QueueItemWebService::GetQueueItemId`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldstr    aQueueitem// "queueitem"
0x15  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x1a  dup
0x1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x20  ldstr    aQueueitemid// "queueitemid"
0x25  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x2a  dup
0x2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x30  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x35  ldstr    aObjectid// "objectid"
0x3a  ldc.i4.0
0x3b  ldarg.1
0x3c  box      [mscorlib]System.Guid
0x41  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4b  pop
0x4c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x56  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection)
0x5b  stloc.0
0x5c  leave.s  loc_67
0x5e  stloc.1
0x5f  ldarg.0
0x60  ldloc.1
0x61  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x66  throw
0x67  ldloc.0
0x68  ret
```
