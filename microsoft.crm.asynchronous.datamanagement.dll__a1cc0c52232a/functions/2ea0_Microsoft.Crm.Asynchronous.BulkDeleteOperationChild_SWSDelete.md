# Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::SWSDelete

- ea: `0x2ea0`
- end: `0x2fac`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::SWSDelete`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x2de0`

## callees

- `0x1450`
- `0x14d0`
- `0x2ea0`
- `0x2fb0`

## string_xrefs

- `0x2ee8`: `Error in Delete. recordID {0} | {1}`
- `0x2f59`: `Error in Delete. recordID {0} | {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2ea0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0x2ea5  stloc.0
0x2ea6  ldloc.0
0x2ea7  ldarg.2
0x2ea8  ldarg.1
0x2ea9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x2eae  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x2eb3  ldarg.0
0x2eb4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_crmService
0x2eb9  ldloc.0
0x2eba  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x2ebf  pop
0x2ec0  ldarg.0
0x2ec1  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_bulkDeleteDataAccess
0x2ec6  ldarg.3
0x2ec7  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RequestId()
0x2ecc  stloc.1
0x2ecd  ldloca.s 1
0x2ecf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2ed4  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateSuccessCount(valuetype [mscorlib]System.Guid asyncOperationId)
0x2ed9  leave    loc_2F97
0x2ede  stloc.2
0x2edf  ldloc.2
0x2ee0  ldarg.0
0x2ee1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_organizationId
0x2ee6  ldc.i4.s 0x15
0x2ee8  ldstr    aErrorInDeleteR// "Error in Delete. recordID {0} | {1}"
0x2eed  ldc.i4.2
0x2eee  newarr   [mscorlib]System.Object
0x2ef3  dup
0x2ef4  ldc.i4.0
0x2ef5  ldarg.1
0x2ef6  box      [mscorlib]System.Guid
0x2efb  stelem.ref
0x2efc  dup
0x2efd  ldc.i4.1
0x2efe  ldloc.2
0x2eff  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2f04  stelem.ref
0x2f05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f0a  ldloc.2
0x2f0b  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x2f10  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x2f15  stloc.3
0x2f16  ldloc.3
0x2f17  ldc.i4   0x80040217
0x2f1c  beq.s    loc_2F32
0x2f1e  ldarg.0
0x2f1f  ldarg.3
0x2f20  ldarg.1
0x2f21  ldarg.2
0x2f22  ldarg.s  4
0x2f24  ldloc.2
0x2f25  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2f2a  ldloc.3
0x2f2b  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::CreateFailureRow(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, valuetype [mscorlib]System.Guid recordId, string entityName, int32 queryIndex, string errorMessage, int32 crmErrorCode)
0x2f30  br.s     loc_2F4B
0x2f32  ldarg.0
0x2f33  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_bulkDeleteDataAccess
0x2f38  ldarg.3
0x2f39  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RequestId()
0x2f3e  stloc.1
0x2f3f  ldloca.s 1
0x2f41  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2f46  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateSuccessCount(valuetype [mscorlib]System.Guid asyncOperationId)
0x2f4b  leave.s  loc_2F97
0x2f4d  stloc.s  4
0x2f4f  ldloc.s  4
0x2f51  ldarg.0
0x2f52  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_organizationId
0x2f57  ldc.i4.s 0x15
0x2f59  ldstr    aErrorInDeleteR// "Error in Delete. recordID {0} | {1}"
0x2f5e  ldc.i4.2
0x2f5f  newarr   [mscorlib]System.Object
0x2f64  dup
0x2f65  ldc.i4.0
0x2f66  ldarg.1
0x2f67  box      [mscorlib]System.Guid
0x2f6c  stelem.ref
0x2f6d  dup
0x2f6e  ldc.i4.1
0x2f6f  ldloc.s  4
0x2f71  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2f76  stelem.ref
0x2f77  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f7c  ldc.i4   0x80048435
0x2f81  stloc.s  5
0x2f83  ldarg.0
0x2f84  ldarg.3
0x2f85  ldarg.1
0x2f86  ldarg.2
0x2f87  ldarg.s  4
0x2f89  ldsfld   string [mscorlib]System.String::Empty
0x2f8e  ldloc.s  5
0x2f90  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::CreateFailureRow(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, valuetype [mscorlib]System.Guid recordId, string entityName, int32 queryIndex, string errorMessage, int32 crmErrorCode)
0x2f95  leave.s  loc_2F97
0x2f97  ldarg.0
0x2f98  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_bulkDeleteDataAccess
0x2f9d  ldarg.0
0x2f9e  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_tempTableName
0x2fa3  ldarg.1
0x2fa4  ldarg.s  4
0x2fa6  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateRecordsAsProcessed(string tableName, valuetype [mscorlib]System.Guid recordId, int32 queryIndex)
0x2fab  ret
```
