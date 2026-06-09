# Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSDelete

- ea: `0x12610`
- end: `0x1277f`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSDelete`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0xf190`

## callees

- `0x3bb0`
- `0x51f0`
- `0x12610`

## string_xrefs

- `0x12639`: `Error in Delete. ImportDataId {0} | Details: {1}`
- `0x126bb`: `Error in Delete. ImportDataId {0} | Details: {1}`
- `0x1271e`: `Error in Delete. ImportDataId {0} | Details: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x12610  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::.ctor()
0x12615  stloc.0
0x12616  ldloc.0
0x12617  ldarg.2
0x12618  ldarg.3
0x12619  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1261e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.DeleteRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x12623  ldarg.0
0x12624  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x12629  ldloc.0
0x1262a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1262f  pop
0x12630  leave    loc_1277E
0x12635  stloc.1
0x12636  ldarg.1
0x12637  ldc.i4.s 0x18
0x12639  ldstr    aErrorInDeleteI// "Error in Delete. ImportDataId {0} | Det"...
0x1263e  ldc.i4.2
0x1263f  newarr   [mscorlib]System.Object
0x12644  dup
0x12645  ldc.i4.0
0x12646  ldarg.s  5
0x12648  box      [mscorlib]System.Guid
0x1264d  stelem.ref
0x1264e  dup
0x1264f  ldc.i4.1
0x12650  ldloc.1
0x12651  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x12656  stelem.ref
0x12657  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1265c  ldarg.0
0x1265d  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x12662  ldarg.0
0x12663  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x12668  ldarg.0
0x12669  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1266e  ldarg.s  4
0x12670  ldarg.s  5
0x12672  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x12677  ldc.i4.2
0x12678  ldsfld   string [mscorlib]System.String::Empty
0x1267d  ldsfld   string [mscorlib]System.String::Empty
0x12682  ldloc.1
0x12683  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x12688  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1268d  ldloc.1
0x1268e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x12693  ldc.i4.1
0x12694  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x12699  leave    loc_1277E
0x1269e  stloc.2
0x1269f  ldloc.2
0x126a0  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x126a5  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x126aa  stloc.3
0x126ab  ldloc.2
0x126ac  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x126b1  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault fault)
0x126b6  stloc.s  4
0x126b8  ldarg.1
0x126b9  ldc.i4.s 0x18
0x126bb  ldstr    aErrorInDeleteI// "Error in Delete. ImportDataId {0} | Det"...
0x126c0  ldc.i4.2
0x126c1  newarr   [mscorlib]System.Object
0x126c6  dup
0x126c7  ldc.i4.0
0x126c8  ldarg.s  5
0x126ca  box      [mscorlib]System.Guid
0x126cf  stelem.ref
0x126d0  dup
0x126d1  ldc.i4.1
0x126d2  ldloc.s  4
0x126d4  stelem.ref
0x126d5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x126da  ldarg.0
0x126db  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x126e0  ldarg.0
0x126e1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x126e6  ldarg.0
0x126e7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x126ec  ldarg.s  4
0x126ee  ldarg.s  5
0x126f0  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x126f5  ldc.i4.2
0x126f6  ldsfld   string [mscorlib]System.String::Empty
0x126fb  ldsfld   string [mscorlib]System.String::Empty
0x12700  ldloc.3
0x12701  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x12706  ldloc.2
0x12707  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1270c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x12711  ldc.i4.1
0x12712  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x12717  leave.s  loc_1277E
0x12719  stloc.s  5
0x1271b  ldarg.1
0x1271c  ldc.i4.s 0x18
0x1271e  ldstr    aErrorInDeleteI// "Error in Delete. ImportDataId {0} | Det"...
0x12723  ldc.i4.2
0x12724  newarr   [mscorlib]System.Object
0x12729  dup
0x1272a  ldc.i4.0
0x1272b  ldarg.s  5
0x1272d  box      [mscorlib]System.Guid
0x12732  stelem.ref
0x12733  dup
0x12734  ldc.i4.1
0x12735  ldloc.s  5
0x12737  stelem.ref
0x12738  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1273d  ldc.i4   0x80040358
0x12742  stloc.s  6
0x12744  ldarg.0
0x12745  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1274a  ldarg.0
0x1274b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x12750  ldarg.0
0x12751  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x12756  ldarg.s  4
0x12758  ldarg.s  5
0x1275a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1275f  ldc.i4.2
0x12760  ldsfld   string [mscorlib]System.String::Empty
0x12765  ldsfld   string [mscorlib]System.String::Empty
0x1276a  ldloc.s  6
0x1276c  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x12771  ldsfld   string [mscorlib]System.String::Empty
0x12776  ldc.i4.1
0x12777  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x1277c  leave.s  loc_1277E
0x1277e  ret
```
