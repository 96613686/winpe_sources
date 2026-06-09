# Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::InternalExecute

- ea: `0x2c50`
- end: `0x2d3e`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::InternalExecute`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x2c50`
- `0x2d40`
- `0x2de0`

## string_xrefs

- `0x2c5a`: `Operation type must be 'BulkDeleteChild'`
- `0x2c97`: `Insufficient privilege to perform this operation`
- `0x2d20`: `Error in Bulk Delete child handler | {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2c50  ldarg.1
0x2c51  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x2c56  ldc.i4.s 0x17
0x2c58  ceq
0x2c5a  ldstr    aOperationTypeM// "Operation type must be 'BulkDeleteChild"...
0x2c5f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2c64  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x2c69  stloc.0
0x2c6a  ldarg.0
0x2c6b  ldarg.1
0x2c6c  ldc.i4.0
0x2c6d  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x2c72  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_crmService
0x2c77  ldarg.0
0x2c78  ldarg.1
0x2c79  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2c7e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_organizationId
0x2c83  ldarg.0
0x2c84  ldarg.1
0x2c85  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x2c8a  ldarg.1
0x2c8b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2c90  call     instance bool Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::UserHasBulkDeletePrivilege(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId)
0x2c95  brtrue.s loc_2CA7
0x2c97  ldstr    aInsufficientPr// "Insufficient privilege to perform this "...
0x2c9c  ldc.i4   0x8004024B
0x2ca1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2ca6  throw
0x2ca7  ldnull
0x2ca8  stloc.1
0x2ca9  ldtoken  [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData
0x2cae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2cb3  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x2cb8  stloc.2
0x2cb9  ldarg.1
0x2cba  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x2cbf  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x2cc4  stloc.3
0x2cc5  ldloc.2
0x2cc6  ldloc.3
0x2cc7  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x2ccc  castclass [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData
0x2cd1  stloc.1
0x2cd2  leave.s  loc_2CDE
0x2cd4  ldloc.3
0x2cd5  brfalse.s loc_2CDD
0x2cd7  ldloc.3
0x2cd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2cdd  endfinally
0x2cde  ldarg.0
0x2cdf  ldloc.1
0x2ce0  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData::get_StartRow()
0x2ce5  stfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_nextRow
0x2cea  ldarg.0
0x2ceb  ldloc.1
0x2cec  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData::get_EndRow()
0x2cf1  stfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_lastRow
0x2cf6  ldarg.0
0x2cf7  ldloc.1
0x2cf8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.BulkDeleteChildData::get_TempTableName()
0x2cfd  stfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_tempTableName
0x2d02  ldloc.0
0x2d03  isinst   [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult
0x2d08  brfalse.s loc_2D12
0x2d0a  ldarg.0
0x2d0b  ldarg.1
0x2d0c  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::DoDelete(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x2d11  stloc.0
0x2d12  leave.s  loc_2D3C
0x2d14  stloc.s  4
0x2d16  ldloc.s  4
0x2d18  ldarg.1
0x2d19  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2d1e  ldc.i4.s 0x15
0x2d20  ldstr    aErrorInBulkDel// "Error in Bulk Delete child handler | {0"...
0x2d25  ldc.i4.1
0x2d26  newarr   [mscorlib]System.Object
0x2d2b  dup
0x2d2c  ldc.i4.0
0x2d2d  ldloc.s  4
0x2d2f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x2d34  stelem.ref
0x2d35  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2d3a  rethrow
0x2d3c  ldloc.0
0x2d3d  ret
```
