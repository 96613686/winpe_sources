# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAttributeLength

- ea: `0x1d050`
- end: `0x1d2d7`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAttributeLength`
- size: `647`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1cf60`
- `0x1d410`

## callees

- `0x3bb0`
- `0x51d0`
- `0x1d050`
- `0x1d2e0`

## pseudocode

```c

```

## disassembly

```asm
0x1d050  ldarg.0
0x1d051  ldarg.1
0x1d052  ldarg.2
0x1d053  ldarg.3
0x1d054  ldarg.s  4
0x1d056  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationTransform::TryToHandleAddressAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, int32 maxLength, valuetype [mscorlib]System.Guid importFileId, string sourceColumnName)
0x1d05b  brtrue.s loc_1D05F
0x1d05d  ldc.i4.0
0x1d05e  ret
0x1d05f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateAttributeRequest::.ctor()
0x1d064  stloc.0
0x1d065  ldarg.1
0x1d066  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0x1d06b  stloc.1
0x1d06c  ldloc.1
0x1d06d  brfalse.s loc_1D09B
0x1d06f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata::.ctor()
0x1d074  stloc.2
0x1d075  ldloc.2
0x1d076  ldarg.2
0x1d077  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1d07c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.StringAttributeMetadata::set_MaxLength(valuetype [mscorlib]System.Nullable`1<int32>)
0x1d081  ldloc.2
0x1d082  ldarg.1
0x1d083  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x1d088  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1d08d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1d092  ldloc.0
0x1d093  ldloc.2
0x1d094  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateAttributeRequest::set_Attribute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata)
0x1d099  br.s     loc_1D0C5
0x1d09b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MemoAttributeMetadata::.ctor()
0x1d0a0  stloc.3
0x1d0a1  ldloc.3
0x1d0a2  ldarg.2
0x1d0a3  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1d0a8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MemoAttributeMetadata::set_MaxLength(valuetype [mscorlib]System.Nullable`1<int32>)
0x1d0ad  ldloc.3
0x1d0ae  ldarg.1
0x1d0af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x1d0b4  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1d0b9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1d0be  ldloc.0
0x1d0bf  ldloc.3
0x1d0c0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateAttributeRequest::set_Attribute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata)
0x1d0c5  ldloc.0
0x1d0c6  ldarg.1
0x1d0c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1d0cc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1d0d1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateAttributeRequest::set_EntityName(string)
0x1d0d6  ldloc.0
0x1d0d7  ldc.i4.0
0x1d0d8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateAttributeRequest::set_MergeLabels(bool)
0x1d0dd  ldarg.0
0x1d0de  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x1d0e3  ldloc.0
0x1d0e4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1d0e9  pop
0x1d0ea  ldc.i4.1
0x1d0eb  stloc.s  4
0x1d0ed  leave    loc_1D2D4
0x1d0f2  stloc.s  5
0x1d0f4  ldarg.0
0x1d0f5  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1d0fa  ldarg.0
0x1d0fb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x1d100  ldarg.0
0x1d101  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1d106  ldarg.3
0x1d107  ldloca.s 6
0x1d109  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1d10f  ldloc.s  6
0x1d111  ldc.i4.1
0x1d112  ldarg.s  4
0x1d114  ldnull
0x1d115  ldc.i4   0x80044351
0x1d11a  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1d11f  ldloc.s  5
0x1d121  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1d126  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1d12b  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x1d130  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1d135  ldc.i4.s 0x18
0x1d137  ldstr    aErrorInUpdatin// "Error in updating length of Attribute {"...
0x1d13c  ldc.i4.3
0x1d13d  newarr   [mscorlib]System.Object
0x1d142  dup
0x1d143  ldc.i4.0
0x1d144  ldarg.1
0x1d145  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1d14a  stelem.ref
0x1d14b  dup
0x1d14c  ldc.i4.1
0x1d14d  ldarg.1
0x1d14e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1d153  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1d158  stelem.ref
0x1d159  dup
0x1d15a  ldc.i4.2
0x1d15b  ldloc.s  5
0x1d15d  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1d162  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault fault)
0x1d167  stelem.ref
0x1d168  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d16d  leave    loc_1D2D2
0x1d172  stloc.s  7
0x1d174  ldarg.0
0x1d175  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1d17a  ldarg.0
0x1d17b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x1d180  ldarg.0
0x1d181  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1d186  ldarg.3
0x1d187  ldloca.s 6
0x1d189  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1d18f  ldloc.s  6
0x1d191  ldc.i4.1
0x1d192  ldarg.s  4
0x1d194  ldnull
0x1d195  ldc.i4   0x80044351
0x1d19a  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1d19f  ldloc.s  7
0x1d1a1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1d1a6  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x1d1ab  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1d1b0  ldc.i4.s 0x18
0x1d1b2  ldstr    aErrorInUpdatin// "Error in updating length of Attribute {"...
0x1d1b7  ldc.i4.3
0x1d1b8  newarr   [mscorlib]System.Object
0x1d1bd  dup
0x1d1be  ldc.i4.0
0x1d1bf  ldarg.1
0x1d1c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1d1c5  stelem.ref
0x1d1c6  dup
0x1d1c7  ldc.i4.1
0x1d1c8  ldarg.1
0x1d1c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1d1ce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1d1d3  stelem.ref
0x1d1d4  dup
0x1d1d5  ldc.i4.2
0x1d1d6  ldloc.s  7
0x1d1d8  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1d1dd  stelem.ref
0x1d1de  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d1e3  leave    loc_1D2D2
0x1d1e8  stloc.s  8
0x1d1ea  ldarg.0
0x1d1eb  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1d1f0  ldarg.0
0x1d1f1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x1d1f6  ldarg.0
0x1d1f7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1d1fc  ldarg.3
0x1d1fd  ldloca.s 6
0x1d1ff  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1d205  ldloc.s  6
0x1d207  ldc.i4.1
0x1d208  ldarg.s  4
0x1d20a  ldnull
0x1d20b  ldc.i4   0x80044351
0x1d210  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1d215  ldloc.s  8
0x1d217  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1d21c  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x1d221  ldloc.s  8
0x1d223  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1d228  ldc.i4.s 0x18
0x1d22a  ldstr    aErrorInUpdatng// "Error in updatng length of Attribute {0"...
0x1d22f  ldc.i4.3
0x1d230  newarr   [mscorlib]System.Object
0x1d235  dup
0x1d236  ldc.i4.0
0x1d237  ldarg.1
0x1d238  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1d23d  stelem.ref
0x1d23e  dup
0x1d23f  ldc.i4.1
0x1d240  ldarg.1
0x1d241  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1d246  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1d24b  stelem.ref
0x1d24c  dup
0x1d24d  ldc.i4.2
0x1d24e  ldloc.s  8
0x1d250  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1d255  stelem.ref
0x1d256  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d25b  leave.s  loc_1D2D2
0x1d25d  stloc.s  9
0x1d25f  ldarg.0
0x1d260  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1d265  ldarg.0
0x1d266  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x1d26b  ldarg.0
0x1d26c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1d271  ldarg.3
0x1d272  ldloca.s 6
0x1d274  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1d27a  ldloc.s  6
0x1d27c  ldc.i4.1
0x1d27d  ldarg.s  4
0x1d27f  ldnull
0x1d280  ldc.i4   0x80044351
0x1d285  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1d28a  ldloc.s  9
0x1d28c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1d291  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x1d296  ldloc.s  9
0x1d298  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1d29d  ldc.i4.s 0x18
0x1d29f  ldstr    aErrorInUpdatng// "Error in updatng length of Attribute {0"...
0x1d2a4  ldc.i4.3
0x1d2a5  newarr   [mscorlib]System.Object
0x1d2aa  dup
0x1d2ab  ldc.i4.0
0x1d2ac  ldarg.1
0x1d2ad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1d2b2  stelem.ref
0x1d2b3  dup
0x1d2b4  ldc.i4.1
0x1d2b5  ldarg.1
0x1d2b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1d2bb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1d2c0  stelem.ref
0x1d2c1  dup
0x1d2c2  ldc.i4.2
0x1d2c3  ldloc.s  9
0x1d2c5  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1d2ca  stelem.ref
0x1d2cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d2d0  leave.s  loc_1D2D2
0x1d2d2  ldc.i4.0
0x1d2d3  ret
0x1d2d4  ldloc.s  4
0x1d2d6  ret
```
