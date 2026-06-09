# Microsoft.Crm.Asynchronous.ImportOperationImport::ExecuteImportOperation

- ea: `0xbe90`
- end: `0xc403`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImport::ExecuteImportOperation`
- size: `1395`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3bb0`
- `0x3d80`
- `0x51d0`
- `0x8f40`
- `0x8f60`
- `0x8f90`
- `0xb0e0`
- `0xbe90`
- `0xc410`
- `0xc4c0`
- `0xc560`
- `0xc5a0`
- `0xd040`
- `0xd1c0`
- `0xd5a0`
- `0xd7f0`
- `0xdc50`
- `0x10b00`
- `0x13c50`
- `0x13cf0`

## string_xrefs

- `0xc2b8`: `Update Mode is not valid if more than one importfile is associated with the import`

## pseudocode

```c

```

## disassembly

```asm
0xbe90  ldarg.0
0xbe91  ldarg.2
0xbe92  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_importId
0xbe97  ldarg.3
0xbe98  ldc.i4.5
0xbe99  ceq
0xbe9b  ldstr    aOperationTypeM_2// "Operation type must be 'Import'"
0xbea0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xbea5  ldarg.0
0xbea6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xbeab  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_collectionOfAllImportFilesRequiringUpdate
0xbeb0  ldarg.0
0xbeb1  ldarg.2
0xbeb2  ldarg.0
0xbeb3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0xbeb8  ldarg.1
0xbeb9  ldarg.0
0xbeba  ldfld    int32 Microsoft.Crm.Asynchronous.ImportOperation::_languageCode
0xbebf  newobj   instance void Microsoft.Crm.Asynchronous.ImportHelperData::.ctor(valuetype [mscorlib]System.Guid importId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, valuetype [mscorlib]System.Guid organizationId, int32 languageCode)
0xbec4  stfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xbec9  ldarg.0
0xbeca  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xbecf  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_JobsToBeResumed
0xbed4  ldarg.0
0xbed5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xbeda  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportOperationImport::_failedJobs
0xbedf  ldarg.0
0xbee0  ldarg.0
0xbee1  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_HandlerGroup()
0xbee6  castclass Microsoft.Crm.Asynchronous.DataManagementHandlerGroup
0xbeeb  ldfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.DataManagementHandlerGroup::importOperationImportRecordThroughput
0xbef0  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.ImportOperation::_throughputCounter
0xbef5  ldarg.0
0xbef6  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xbefb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xbf00  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xbf05  brtrue.s loc_BF37
0xbf07  ldarg.1
0xbf08  ldc.i4.s 0x18
0xbf0a  ldstr    aNoImportfileSF// "No importfile(s) found for import id = "...
0xbf0f  ldc.i4.1
0xbf10  newarr   [mscorlib]System.Object
0xbf15  dup
0xbf16  ldc.i4.0
0xbf17  ldarg.2
0xbf18  box      [mscorlib]System.Guid
0xbf1d  stelem.ref
0xbf1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xbf23  ldarg.0
0xbf24  ldarg.2
0xbf25  ldc.i4.4
0xbf26  ldc.i4.1
0xbf27  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::SetImportStatus(valuetype [mscorlib]System.Guid importId, int32 importStatus, bool cleanupImportFilesContent)
0xbf2c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0xbf31  stloc.1
0xbf32  leave    loc_C401
0xbf37  ldarg.0
0xbf38  ldarg.2
0xbf39  ldc.i4.3
0xbf3a  ldc.i4.0
0xbf3b  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::SetImportStatus(valuetype [mscorlib]System.Guid importId, int32 importStatus, bool cleanupImportFilesContent)
0xbf40  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0xbf45  stloc.0
0xbf46  ldarg.0
0xbf47  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xbf4c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xbf51  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xbf56  ldc.i4.1
0xbf57  bne.un   loc_C26B
0xbf5c  ldnull
0xbf5d  stloc.2
0xbf5e  ldc.i4.1
0xbf5f  newarr   [mscorlib]System.Guid
0xbf64  stloc.3
0xbf65  ldarg.0
0xbf66  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xbf6b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xbf70  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Keys()
0xbf75  ldloc.3
0xbf76  ldc.i4.0
0xbf77  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::CopyTo(var<u1>[], !!T0)
0xbf7c  ldloc.3
0xbf7d  ldc.i4.0
0xbf7e  ldelem   [mscorlib]System.Guid
0xbf83  stloc.s  4
0xbf85  ldarg.0
0xbf86  ldloc.0
0xbf87  call     instance void Microsoft.Crm.Asynchronous.ImportOperationImport::GetOrderedGraph(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> orderedGraphOfEntities)
0xbf8c  ldc.i4.2
0xbf8d  stloc.s  5
0xbf8f  ldloc.0
0xbf90  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Count()
0xbf95  ldc.i4.0
0xbf96  ble      loc_C028
0xbf9b  ldarg.0
0xbf9c  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xbfa1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xbfa6  ldloc.s  4
0xbfa8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0xbfad  ldstr    aProcessingstat_0// "processingstatus"
0xbfb2  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xbfb7  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xbfbc  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xbfc1  ldc.i4.s 0xB
0xbfc3  bge.s    loc_BFE0
0xbfc5  ldarg.0
0xbfc6  ldc.i4.1
0xbfc7  stfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0xbfcc  ldarg.0
0xbfcd  ldloc.s  4
0xbfcf  ldarg.1
0xbfd0  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationImportFile::ProcessImportFileNeedingPassTwo(valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid organizationId)
0xbfd5  stloc.2
0xbfd6  ldloc.2
0xbfd7  brfalse.s loc_BFE0
0xbfd9  ldloc.2
0xbfda  stloc.1
0xbfdb  leave    loc_C401
0xbfe0  ldarg.0
0xbfe1  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xbfe6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xbfeb  ldloc.s  4
0xbfed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0xbff2  ldstr    aProcessingstat_0// "processingstatus"
0xbff7  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xbffc  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xc001  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xc006  ldc.i4.s 0xC
0xc008  bge.s    loc_C06D
0xc00a  ldc.i4.3
0xc00b  stloc.s  5
0xc00d  ldarg.0
0xc00e  ldc.i4.2
0xc00f  stfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0xc014  ldarg.0
0xc015  ldarg.1
0xc016  ldloc.s  4
0xc018  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationImportFile::ProcessImportFileForPassTwo(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid importFileId)
0xc01d  stloc.2
0xc01e  ldloc.2
0xc01f  brfalse.s loc_C06D
0xc021  ldloc.2
0xc022  stloc.1
0xc023  leave    loc_C401
0xc028  ldarg.0
0xc029  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xc02e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xc033  ldloc.s  4
0xc035  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0xc03a  ldstr    aProcessingstat_0// "processingstatus"
0xc03f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xc044  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xc049  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xc04e  ldc.i4.s 0xB
0xc050  bge.s    loc_C06D
0xc052  ldarg.0
0xc053  ldc.i4.0
0xc054  stfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0xc059  ldarg.0
0xc05a  ldloc.s  4
0xc05c  ldarg.1
0xc05d  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationImportFile::ProcessImportFileNotNeedingPassTwo(valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid organizationId)
0xc062  stloc.2
0xc063  ldloc.2
0xc064  brfalse.s loc_C06D
0xc066  ldloc.2
0xc067  stloc.1
0xc068  leave    loc_C401
0xc06d  leave    loc_C3C5
0xc072  stloc.s  6
0xc074  ldloc.s  6
0xc076  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0xc07b  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0xc080  stloc.s  7
0xc082  ldloc.s  6
0xc084  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0xc089  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault fault)
0xc08e  stloc.s  8
0xc090  ldloc.s  6
0xc092  ldarg.1
0xc093  ldc.i4.s 0x18
0xc095  ldstr    aErrorInFileWit// "Error in file with id {0} | Details: {1"...
0xc09a  ldc.i4.2
0xc09b  newarr   [mscorlib]System.Object
0xc0a0  dup
0xc0a1  ldc.i4.0
0xc0a2  ldloc.s  4
0xc0a4  box      [mscorlib]System.Guid
0xc0a9  stelem.ref
0xc0aa  dup
0xc0ab  ldc.i4.1
0xc0ac  ldloc.s  8
0xc0ae  stelem.ref
0xc0af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc0b4  ldarg.0
0xc0b5  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xc0ba  ldarg.0
0xc0bb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xc0c0  ldarg.0
0xc0c1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xc0c6  ldloc.s  4
0xc0c8  ldloca.s 9
0xc0ca  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xc0d0  ldloc.s  9
0xc0d2  ldloc.s  5
0xc0d4  ldsfld   string [mscorlib]System.String::Empty
0xc0d9  ldsfld   string [mscorlib]System.String::Empty
0xc0de  ldloc.s  7
0xc0e0  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc0e5  ldloc.s  6
0xc0e7  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0xc0ec  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0xc0f1  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0xc0f6  ldarg.0
0xc0f7  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xc0fc  ldloc.s  4
0xc0fe  ldc.i4.5
0xc0ff  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus(valuetype [mscorlib]System.Guid importFileId, int32 status)
0xc104  rethrow
0xc106  stloc.s  0xA
0xc108  ldloc.s  0xA
0xc10a  ldarg.1
0xc10b  ldc.i4.s 0x18
0xc10d  ldstr    aErrorOccurredW// "Error occurred while uploading import f"...
0xc112  ldc.i4.2
0xc113  newarr   [mscorlib]System.Object
0xc118  dup
0xc119  ldc.i4.0
0xc11a  ldloc.s  4
0xc11c  box      [mscorlib]System.Guid
0xc121  stelem.ref
0xc122  dup
0xc123  ldc.i4.1
0xc124  ldloc.s  0xA
0xc126  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xc12b  stelem.ref
0xc12c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc131  ldarg.0
0xc132  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xc137  ldarg.0
0xc138  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xc13d  ldarg.0
0xc13e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xc143  ldloc.s  4
0xc145  ldloca.s 9
0xc147  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xc14d  ldloc.s  9
0xc14f  ldloc.s  5
0xc151  ldsfld   string [mscorlib]System.String::Empty
0xc156  ldsfld   string [mscorlib]System.String::Empty
0xc15b  ldloc.s  0xA
0xc15d  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0xc162  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc167  ldloc.s  0xA
0xc169  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc16e  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0xc173  ldarg.0
0xc174  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xc179  ldloc.s  4
0xc17b  ldc.i4.5
0xc17c  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus(valuetype [mscorlib]System.Guid importFileId, int32 status)
0xc181  rethrow
0xc183  stloc.s  0xB
0xc185  ldloc.s  0xB
0xc187  ldarg.1
0xc188  ldc.i4.s 0x18
0xc18a  ldstr    aErrorOccurredW_0// "Error occurred while processing import "...
0xc18f  ldc.i4.2
0xc190  newarr   [mscorlib]System.Object
0xc195  dup
0xc196  ldc.i4.0
0xc197  ldloc.s  4
0xc199  box      [mscorlib]System.Guid
0xc19e  stelem.ref
0xc19f  dup
0xc1a0  ldc.i4.1
0xc1a1  ldloc.s  0xB
0xc1a3  stelem.ref
0xc1a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc1a9  ldarg.0
0xc1aa  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xc1af  ldloc.s  4
0xc1b1  ldc.i4.5
0xc1b2  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus(valuetype [mscorlib]System.Guid importFileId, int32 status)
0xc1b7  ldarg.0
0xc1b8  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xc1bd  ldarg.0
0xc1be  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xc1c3  ldarg.0
0xc1c4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xc1c9  ldloc.s  4
0xc1cb  ldloca.s 9
0xc1cd  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xc1d3  ldloc.s  9
0xc1d5  ldloc.s  5
0xc1d7  ldsfld   string [mscorlib]System.String::Empty
0xc1dc  ldsfld   string [mscorlib]System.String::Empty
0xc1e1  ldc.i4   0x80040351
0xc1e6  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xc1eb  ldsfld   string [mscorlib]System.String::Empty
  ... truncated ...
```
