# Microsoft.Crm.Asynchronous.BulkDeleteOperation::SWSDelete

- ea: `0x1e80`
- end: `0x1fa8`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::SWSDelete`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1db0`

## callees

- `0x1450`
- `0x14d0`
- `0x1e80`
- `0x1fb0`

## string_xrefs

- `0x1ed4`: `Error in Delete. recordID {0} | {1}`
- `0x1f56`: `Error in Delete. recordID {0} | {1}`
- `0x1f28`: `Record already deleted. recordID {0} | {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1e80  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0x1e85  stloc.0
0x1e86  ldloc.0
0x1e87  ldarg.2
0x1e88  ldarg.1
0x1e89  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1e8e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x1e93  ldarg.0
0x1e94  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x1e99  ldloc.0
0x1e9a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1e9f  pop
0x1ea0  ldarg.0
0x1ea1  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1ea6  ldarg.3
0x1ea7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1eac  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateSuccessCount(valuetype [mscorlib]System.Guid asyncOperationId)
0x1eb1  leave    loc_1F93
0x1eb6  stloc.1
0x1eb7  ldloc.1
0x1eb8  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1ebd  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x1ec2  stloc.2
0x1ec3  ldloc.2
0x1ec4  ldc.i4   0x80040217
0x1ec9  beq.s    loc_1F0F
0x1ecb  ldloc.1
0x1ecc  ldarg.0
0x1ecd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1ed2  ldc.i4.s 0x15
0x1ed4  ldstr    aErrorInDeleteR// "Error in Delete. recordID {0} | {1}"
0x1ed9  ldc.i4.2
0x1eda  newarr   [mscorlib]System.Object
0x1edf  dup
0x1ee0  ldc.i4.0
0x1ee1  ldarg.1
0x1ee2  box      [mscorlib]System.Guid
0x1ee7  stelem.ref
0x1ee8  dup
0x1ee9  ldc.i4.1
0x1eea  ldloc.1
0x1eeb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1ef0  stelem.ref
0x1ef1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ef6  ldarg.0
0x1ef7  ldarg.3
0x1ef8  ldarg.1
0x1ef9  ldarg.2
0x1efa  ldarg.s  4
0x1efc  ldloc.1
0x1efd  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1f02  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1f07  ldloc.2
0x1f08  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::CreateFailureRow(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, valuetype [mscorlib]System.Guid recordId, string entityName, int32 queryIndex, string errorMessage, int32 crmErrorCode)
0x1f0d  br.s     loc_1F4A
0x1f0f  ldarg.0
0x1f10  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f15  ldarg.3
0x1f16  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x1f1b  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateSuccessCount(valuetype [mscorlib]System.Guid asyncOperationId)
0x1f20  ldarg.0
0x1f21  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1f26  ldc.i4.s 0x15
0x1f28  ldstr    aRecordAlreadyD// "Record already deleted. recordID {0} | "...
0x1f2d  ldc.i4.2
0x1f2e  newarr   [mscorlib]System.Object
0x1f33  dup
0x1f34  ldc.i4.0
0x1f35  ldarg.1
0x1f36  box      [mscorlib]System.Guid
0x1f3b  stelem.ref
0x1f3c  dup
0x1f3d  ldc.i4.1
0x1f3e  ldloc.1
0x1f3f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1f44  stelem.ref
0x1f45  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f4a  leave.s  loc_1F93
0x1f4c  stloc.3
0x1f4d  ldloc.3
0x1f4e  ldarg.0
0x1f4f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1f54  ldc.i4.s 0x15
0x1f56  ldstr    aErrorInDeleteR// "Error in Delete. recordID {0} | {1}"
0x1f5b  ldc.i4.2
0x1f5c  newarr   [mscorlib]System.Object
0x1f61  dup
0x1f62  ldc.i4.0
0x1f63  ldarg.1
0x1f64  box      [mscorlib]System.Guid
0x1f69  stelem.ref
0x1f6a  dup
0x1f6b  ldc.i4.1
0x1f6c  ldloc.3
0x1f6d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1f72  stelem.ref
0x1f73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f78  ldc.i4   0x80048435
0x1f7d  stloc.s  4
0x1f7f  ldarg.0
0x1f80  ldarg.3
0x1f81  ldarg.1
0x1f82  ldarg.2
0x1f83  ldarg.s  4
0x1f85  ldsfld   string [mscorlib]System.String::Empty
0x1f8a  ldloc.s  4
0x1f8c  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::CreateFailureRow(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, valuetype [mscorlib]System.Guid recordId, string entityName, int32 queryIndex, string errorMessage, int32 crmErrorCode)
0x1f91  leave.s  loc_1F93
0x1f93  ldarg.0
0x1f94  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1f99  ldarg.0
0x1f9a  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempDependentTableName
0x1f9f  ldarg.1
0x1fa0  ldarg.s  4
0x1fa2  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateRecordsAsProcessed(string tableName, valuetype [mscorlib]System.Guid recordId, int32 queryIndex)
0x1fa7  ret
```
