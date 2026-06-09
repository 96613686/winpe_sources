# Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSSetState

- ea: `0x13670`
- end: `0x138f4`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSSetState`
- size: `644`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x12d00`
- `0x12dd0`
- `0x13280`
- `0x13300`
- `0x13570`
- `0x13600`

## callees

- `0x3b80`
- `0x3bb0`
- `0x51f0`
- `0x6000`
- `0x8f70`
- `0x10a50`
- `0x13670`

## string_xrefs

- `0x1372a`: `The record was created but the state could not be changed to target value: `

## pseudocode

```c

```

## disassembly

```asm
0x13670  ldsfld   string [mscorlib]System.String::Empty
0x13675  stloc.0
0x13676  ldarg.0
0x13677  ldarg.s  5
0x13679  ldloca.s 0
0x1367b  ldarg.s  4
0x1367d  call     instance void Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetStateName(int32 stateCodeValue, string& stateCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x13682  ldloc.0
0x13683  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13688  brtrue   loc_1383A
0x1368d  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SetStateRequest::.ctor()
0x13692  stloc.1
0x13693  ldloc.1
0x13694  ldarg.2
0x13695  ldarg.3
0x13696  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1369b  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SetStateRequest::set_EntityMoniker(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x136a0  ldloc.1
0x136a1  ldarg.s  5
0x136a3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x136a8  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SetStateRequest::set_State(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue)
0x136ad  ldloc.1
0x136ae  ldarg.s  6
0x136b0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x136b5  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SetStateRequest::set_Status(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue)
0x136ba  ldc.i4.1
0x136bb  stloc.2
0x136bc  ldc.i4.1
0x136bd  stloc.3
0x136be  br       loc_137B8
0x136c3  nop
0x136c4  ldarg.0
0x136c5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x136ca  ldloc.1
0x136cb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x136d0  pop
0x136d1  ldc.i4.0
0x136d2  stloc.3
0x136d3  leave    loc_137B8
0x136d8  stloc.s  4
0x136da  ldloc.s  4
0x136dc  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x136e1  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x136e6  stloc.s  5
0x136e8  ldloc.s  4
0x136ea  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x136ef  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault fault)
0x136f4  stloc.s  6
0x136f6  ldloc.s  5
0x136f8  ldc.i4   0x8004A001
0x136fd  bne.un.s loc_13706
0x136ff  ldloc.2
0x13700  ldc.i4.3
0x13701  ble      loc_1378B
0x13706  ldloc.s  4
0x13708  ldarg.1
0x13709  ldc.i4.s 0x18
0x1370b  ldstr    aErrorInSetstat// "Error in SetState. ImportDataId {0} | D"...
0x13710  ldc.i4.2
0x13711  newarr   [mscorlib]System.Object
0x13716  dup
0x13717  ldc.i4.0
0x13718  ldarg.s  8
0x1371a  box      [mscorlib]System.Guid
0x1371f  stelem.ref
0x13720  dup
0x13721  ldc.i4.1
0x13722  ldloc.s  6
0x13724  stelem.ref
0x13725  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1372a  ldstr    aTheRecordWasCr// "The record was created but the state co"...
0x1372f  ldloc.s  4
0x13731  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x13736  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1373b  call     string [mscorlib]System.String::Concat(string, string)
0x13740  stloc.s  7
0x13742  ldarg.0
0x13743  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x13748  ldarg.0
0x13749  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x1374e  ldarg.0
0x1374f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x13754  ldarg.s  7
0x13756  ldarg.s  8
0x13758  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1375d  ldarg.0
0x1375e  ldfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0x13763  ldc.i4.2
0x13764  beq.s    loc_13769
0x13766  ldc.i4.2
0x13767  br.s     loc_1376A
0x13769  ldc.i4.3
0x1376a  ldsfld   string [mscorlib]System.String::Empty
0x1376f  ldsfld   string [mscorlib]System.String::Empty
0x13774  ldloc.s  5
0x13776  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1377b  ldloc.s  7
0x1377d  ldc.i4.1
0x1377e  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x13783  ldc.i4.0
0x13784  stloc.s  8
0x13786  leave    loc_138F1
0x1378b  ldarg.1
0x1378c  ldc.i4.s 0x18
0x1378e  ldstr    aServerBusyRetr_4// "Server busy ,retrying SetState.ImportDa"...
0x13793  ldc.i4.1
0x13794  newarr   [mscorlib]System.Object
0x13799  dup
0x1379a  ldc.i4.0
0x1379b  ldarg.s  8
0x1379d  box      [mscorlib]System.Guid
0x137a2  stelem.ref
0x137a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x137a8  ldloc.2
0x137a9  ldc.i4.1
0x137aa  add
0x137ab  stloc.2
0x137ac  ldc.i4   0x7530
0x137b1  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x137b6  leave.s  loc_137B8
0x137b8  ldloc.3
0x137b9  brtrue   loc_136C3
0x137be  leave    loc_138EF
0x137c3  stloc.s  9
0x137c5  ldarg.1
0x137c6  ldc.i4.s 0x18
0x137c8  ldstr    aErrorInSetstat// "Error in SetState. ImportDataId {0} | D"...
0x137cd  ldc.i4.2
0x137ce  newarr   [mscorlib]System.Object
0x137d3  dup
0x137d4  ldc.i4.0
0x137d5  ldarg.s  8
0x137d7  box      [mscorlib]System.Guid
0x137dc  stelem.ref
0x137dd  dup
0x137de  ldc.i4.1
0x137df  ldloc.s  9
0x137e1  stelem.ref
0x137e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x137e7  ldc.i4   0x80040357
0x137ec  stloc.s  0xA
0x137ee  ldarg.0
0x137ef  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x137f4  ldarg.0
0x137f5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x137fa  ldarg.0
0x137fb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x13800  ldarg.s  7
0x13802  ldarg.s  8
0x13804  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x13809  ldarg.0
0x1380a  ldfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0x1380f  ldc.i4.2
0x13810  beq.s    loc_13815
0x13812  ldc.i4.2
0x13813  br.s     loc_13816
0x13815  ldc.i4.3
0x13816  ldsfld   string [mscorlib]System.String::Empty
0x1381b  ldsfld   string [mscorlib]System.String::Empty
0x13820  ldloc.s  0xA
0x13822  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x13827  ldsfld   string [mscorlib]System.String::Empty
0x1382c  ldc.i4.1
0x1382d  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x13832  ldc.i4.0
0x13833  stloc.s  8
0x13835  leave    loc_138F1
0x1383a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1383f  ldstr    a0IsNotAValidSt// "{0} is not a valid state code on {1}."
0x13844  ldc.i4.2
0x13845  newarr   [mscorlib]System.Object
0x1384a  dup
0x1384b  ldc.i4.0
0x1384c  ldarg.s  5
0x1384e  box      [mscorlib]System.Int32
0x13853  stelem.ref
0x13854  dup
0x13855  ldc.i4.1
0x13856  ldarg.2
0x13857  stelem.ref
0x13858  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1385d  stloc.s  0xB
0x1385f  ldnull
0x13860  ldarg.1
0x13861  ldc.i4.s 0x18
0x13863  ldstr    aErrorInSetstat// "Error in SetState. ImportDataId {0} | D"...
0x13868  ldc.i4.2
0x13869  newarr   [mscorlib]System.Object
0x1386e  dup
0x1386f  ldc.i4.0
0x13870  ldarg.s  8
0x13872  box      [mscorlib]System.Guid
0x13877  stelem.ref
0x13878  dup
0x13879  ldc.i4.1
0x1387a  ldloc.s  0xB
0x1387c  stelem.ref
0x1387d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13882  ldarg.0
0x13883  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x13888  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x1388d  ldarg.s  7
0x1388f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x13894  stloc.s  0xC
0x13896  ldarg.0
0x13897  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1389c  ldarg.0
0x1389d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x138a2  ldarg.0
0x138a3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x138a8  ldarg.s  7
0x138aa  ldarg.s  8
0x138ac  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x138b1  ldarg.0
0x138b2  ldfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0x138b7  ldc.i4.2
0x138b8  beq.s    loc_138BD
0x138ba  ldc.i4.2
0x138bb  br.s     loc_138BE
0x138bd  ldc.i4.3
0x138be  ldloc.s  0xC
0x138c0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_StateColumnMapping()
0x138c5  ldstr    aSourceattribut// "sourceattributename"
0x138ca  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x138cf  ldarga.s 5
0x138d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x138d6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x138db  ldc.i4   0x80048408
0x138e0  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x138e5  ldloc.s  0xB
0x138e7  ldc.i4.1
0x138e8  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x138ed  ldc.i4.0
0x138ee  ret
0x138ef  ldc.i4.1
0x138f0  ret
0x138f1  ldloc.s  8
0x138f3  ret
```
