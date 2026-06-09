# Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSUpdate

- ea: `0x11690`
- end: `0x11a12`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSUpdate`
- size: `898`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf190`
- `0x10ec0`

## callees

- `0x3bb0`
- `0x51f0`
- `0x8f70`
- `0xaab0`
- `0x11690`
- `0x120b0`
- `0x13dd0`

## string_xrefs

- `0x117a8`: `Error in Update. ImportDataId {0} | Details: {1}`
- `0x1181c`: `Server busy ,retrying update.ImportDataId {0} `
- `0x11956`: `Server busy ,retrying update.ImportDataId {0} `
- `0x1198f`: `Error in Update. ImportDataId {0} | {1}`

## pseudocode

```c

```

## disassembly

```asm
0x11690  ldarg.0
0x11691  ldarg.2
0x11692  ldarg.3
0x11693  ldarg.s  4
0x11695  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::CheckAndLogEmptyRecord(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity dynamicEntity, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid importDataId)
0x1169a  brtrue.s loc_1169E
0x1169c  ldc.i4.0
0x1169d  ret
0x1169e  ldnull
0x1169f  stloc.0
0x116a0  ldarg.2
0x116a1  ldstr    aOwnerid_1// "ownerid"
0x116a6  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x116ab  brfalse.s loc_116CF
0x116ad  ldarg.2
0x116ae  ldstr    aOwnerid_1// "ownerid"
0x116b3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x116b8  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x116bd  stloc.0
0x116be  ldarg.2
0x116bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x116c4  ldstr    aOwnerid_1// "ownerid"
0x116c9  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x116ce  pop
0x116cf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0x116d4  stloc.1
0x116d5  ldloc.1
0x116d6  ldarg.2
0x116d7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x116dc  ldloc.1
0x116dd  ldstr    aSuppressduplic// "SuppressDuplicateDetection"
0x116e2  ldarg.s  5
0x116e4  ldc.i4.0
0x116e5  ceq
0x116e7  box      [mscorlib]System.Boolean
0x116ec  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x116f1  ldloc.1
0x116f2  ldstr    aCalculatematch// "CalculateMatchCodeSynchronously"
0x116f7  ldarg.s  5
0x116f9  box      [mscorlib]System.Boolean
0x116fe  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x11703  ldc.i4.1
0x11704  stloc.2
0x11705  ldc.i4.1
0x11706  stloc.3
0x11707  ldarg.0
0x11708  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1170d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x11712  ldarg.3
0x11713  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x11718  stloc.s  4
0x1171a  br       loc_11846
0x1171f  nop
0x11720  ldarg.0
0x11721  ldloc.s  4
0x11723  ldarg.1
0x11724  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::IfUseUpsert(class Microsoft.Crm.Asynchronous.ImportFileHelperData importFileData, valuetype [mscorlib]System.Guid organizationId)
0x11729  brfalse.s loc_11764
0x1172b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertRequest::.ctor()
0x11730  stloc.s  5
0x11732  ldloc.s  5
0x11734  ldarg.2
0x11735  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x1173a  ldarg.0
0x1173b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x11740  ldloc.s  5
0x11742  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x11747  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertResponse
0x1174c  stloc.s  6
0x1174e  ldarg.2
0x1174f  ldloc.s  6
0x11751  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertResponse::get_Target()
0x11756  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1175b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x11760  ldc.i4.0
0x11761  stloc.3
0x11762  br.s     loc_11773
0x11764  ldarg.0
0x11765  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x1176a  ldloc.1
0x1176b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x11770  pop
0x11771  ldc.i4.0
0x11772  stloc.3
0x11773  leave    loc_11846
0x11778  stloc.s  7
0x1177a  ldloc.s  7
0x1177c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x11781  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x11786  stloc.s  8
0x11788  ldloc.s  7
0x1178a  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1178f  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault fault)
0x11794  stloc.s  9
0x11796  ldloc.s  8
0x11798  ldc.i4   0x8004A001
0x1179d  bne.un.s loc_117A3
0x1179f  ldloc.2
0x117a0  ldc.i4.3
0x117a1  ble.s    loc_11819
0x117a3  ldloc.s  7
0x117a5  ldarg.1
0x117a6  ldc.i4.s 0x18
0x117a8  ldstr    aErrorInUpdateI// "Error in Update. ImportDataId {0} | Det"...
0x117ad  ldc.i4.2
0x117ae  newarr   [mscorlib]System.Object
0x117b3  dup
0x117b4  ldc.i4.0
0x117b5  ldarg.s  4
0x117b7  box      [mscorlib]System.Guid
0x117bc  stelem.ref
0x117bd  dup
0x117be  ldc.i4.1
0x117bf  ldloc.s  9
0x117c1  stelem.ref
0x117c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x117c7  ldarg.0
0x117c8  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x117cd  ldarg.0
0x117ce  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x117d3  ldarg.0
0x117d4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x117d9  ldarg.3
0x117da  ldarg.s  4
0x117dc  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x117e1  ldarg.0
0x117e2  ldfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0x117e7  ldc.i4.2
0x117e8  beq.s    loc_117ED
0x117ea  ldc.i4.2
0x117eb  br.s     loc_117EE
0x117ed  ldc.i4.3
0x117ee  ldsfld   string [mscorlib]System.String::Empty
0x117f3  ldsfld   string [mscorlib]System.String::Empty
0x117f8  ldloc.s  8
0x117fa  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x117ff  ldloc.s  7
0x11801  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x11806  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1180b  ldc.i4.1
0x1180c  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x11811  ldc.i4.0
0x11812  stloc.s  0xA
0x11814  leave    loc_11A0F
0x11819  ldarg.1
0x1181a  ldc.i4.s 0x18
0x1181c  ldstr    aServerBusyRetr// "Server busy ,retrying update.ImportData"...
0x11821  ldc.i4.1
0x11822  newarr   [mscorlib]System.Object
0x11827  dup
0x11828  ldc.i4.0
0x11829  ldarg.s  4
0x1182b  box      [mscorlib]System.Guid
0x11830  stelem.ref
0x11831  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11836  ldloc.2
0x11837  ldc.i4.1
0x11838  add
0x11839  stloc.2
0x1183a  ldc.i4   0x7530
0x1183f  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x11844  leave.s  loc_11846
0x11846  ldloc.3
0x11847  brtrue   loc_1171F
0x1184c  ldloc.0
0x1184d  brfalse  loc_11986
0x11852  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AssignRequest::.ctor()
0x11857  stloc.s  0xB
0x11859  ldloc.s  0xB
0x1185b  ldarg.2
0x1185c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x11861  ldarg.2
0x11862  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x11867  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1186c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AssignRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x11871  ldloc.s  0xB
0x11873  ldloc.0
0x11874  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AssignRequest::set_Assignee(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x11879  ldc.i4.1
0x1187a  stloc.2
0x1187b  ldc.i4.1
0x1187c  stloc.3
0x1187d  br       loc_11980
0x11882  nop
0x11883  ldarg.0
0x11884  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x11889  ldloc.s  0xB
0x1188b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x11890  pop
0x11891  ldc.i4.0
0x11892  stloc.3
0x11893  leave    loc_11980
0x11898  stloc.s  0xC
0x1189a  ldloc.s  0xC
0x1189c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x118a1  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x118a6  stloc.s  0xD
0x118a8  ldloc.s  0xC
0x118aa  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x118af  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault fault)
0x118b4  stloc.s  0xE
0x118b6  ldloc.s  0xD
0x118b8  ldc.i4   0x8004A001
0x118bd  bne.un.s loc_118C6
0x118bf  ldloc.2
0x118c0  ldc.i4.3
0x118c1  ble      loc_11953
0x118c6  ldloc.s  0xC
0x118c8  ldarg.1
0x118c9  ldc.i4.s 0x18
0x118cb  ldstr    aErrorInAssigni// "Error in Assigning record to owner [{2}"...
0x118d0  ldc.i4.4
0x118d1  newarr   [mscorlib]System.Object
0x118d6  dup
0x118d7  ldc.i4.0
0x118d8  ldarg.s  4
0x118da  box      [mscorlib]System.Guid
0x118df  stelem.ref
0x118e0  dup
0x118e1  ldc.i4.1
0x118e2  ldloc.s  0xE
0x118e4  stelem.ref
0x118e5  dup
0x118e6  ldc.i4.2
0x118e7  ldloc.0
0x118e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x118ed  box      [mscorlib]System.Guid
0x118f2  stelem.ref
0x118f3  dup
0x118f4  ldc.i4.3
0x118f5  ldloc.0
0x118f6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x118fb  stelem.ref
0x118fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11901  ldarg.0
0x11902  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x11907  ldarg.0
0x11908  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x1190d  ldarg.0
0x1190e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x11913  ldarg.3
0x11914  ldarg.s  4
0x11916  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1191b  ldarg.0
0x1191c  ldfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0x11921  ldc.i4.2
0x11922  beq.s    loc_11927
0x11924  ldc.i4.2
0x11925  br.s     loc_11928
0x11927  ldc.i4.3
0x11928  ldsfld   string [mscorlib]System.String::Empty
0x1192d  ldsfld   string [mscorlib]System.String::Empty
0x11932  ldloc.s  0xD
0x11934  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x11939  ldloc.s  0xC
0x1193b  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x11940  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x11945  ldc.i4.1
0x11946  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x1194b  ldc.i4.0
0x1194c  stloc.s  0xA
0x1194e  leave    loc_11A0F
0x11953  ldarg.1
0x11954  ldc.i4.s 0x18
0x11956  ldstr    aServerBusyRetr// "Server busy ,retrying update.ImportData"...
0x1195b  ldc.i4.1
0x1195c  newarr   [mscorlib]System.Object
0x11961  dup
0x11962  ldc.i4.0
0x11963  ldarg.s  4
0x11965  box      [mscorlib]System.Guid
0x1196a  stelem.ref
0x1196b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11970  ldloc.2
0x11971  ldc.i4.1
0x11972  add
0x11973  stloc.2
0x11974  ldc.i4   0x7530
0x11979  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1197e  leave.s  loc_11980
0x11980  ldloc.3
0x11981  brtrue   loc_11882
0x11986  leave.s  loc_11A02
0x11988  stloc.s  0xF
0x1198a  ldloc.s  0xF
0x1198c  ldarg.1
0x1198d  ldc.i4.s 0x18
0x1198f  ldstr    aErrorInUpdateI_0// "Error in Update. ImportDataId {0} | {1}"
0x11994  ldc.i4.2
0x11995  newarr   [mscorlib]System.Object
0x1199a  dup
0x1199b  ldc.i4.0
0x1199c  ldarg.s  4
0x1199e  box      [mscorlib]System.Guid
0x119a3  stelem.ref
0x119a4  dup
0x119a5  ldc.i4.1
0x119a6  ldloc.s  0xF
0x119a8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x119ad  stelem.ref
  ... truncated ...
```
