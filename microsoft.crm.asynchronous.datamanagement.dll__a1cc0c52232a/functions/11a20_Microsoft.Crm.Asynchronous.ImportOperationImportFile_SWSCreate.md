# Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSCreate

- ea: `0x11a20`
- end: `0x120aa`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSCreate`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0xf190`

## callees

- `0x3bb0`
- `0x51d0`
- `0x5ee0`
- `0x5ef0`
- `0x5f00`
- `0x5f60`
- `0x5fb0`
- `0x8f70`
- `0xaab0`
- `0x11a20`
- `0x120b0`
- `0x12110`
- `0x12170`
- `0x12230`
- `0x123d0`
- `0x12520`
- `0x13dd0`

## string_xrefs

- `0x11d2b`: `Error in Create. ImportDataId {0} | Details: {1}`
- `0x11d59`: `Record with primary key for ImportDataId {0} already exists.`
- `0x11fc0`: `Error in Create. ImportDataId {0} | {1}`
- `0x12034`: `Error in Create. ImportDataId {0} | {1}`

## pseudocode

```c

```

## disassembly

```asm
0x11a20  ldarg.0
0x11a21  ldarg.2
0x11a22  ldarg.3
0x11a23  ldarg.s  4
0x11a25  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::CheckAndLogEmptyRecord(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity dynamicEntity, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid importDataId)
0x11a2a  brtrue.s loc_11A2E
0x11a2c  ldc.i4.0
0x11a2d  ret
0x11a2e  ldarg.0
0x11a2f  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x11a34  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x11a39  ldarg.3
0x11a3a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x11a3f  stloc.0
0x11a40  ldloc.0
0x11a41  callvirt instance bool Microsoft.Crm.Asynchronous.ImportFileHelperData::get_EnableDuplicateDetection()
0x11a46  stloc.1
0x11a47  ldloc.0
0x11a48  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Asynchronous.ImportFileHelperData::get_RecordsOwner()
0x11a4d  stloc.2
0x11a4e  ldloc.0
0x11a4f  callvirt instance bool Microsoft.Crm.Asynchronous.ImportFileHelperData::get_IsUserOrTeamOwned()
0x11a54  stloc.3
0x11a55  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11a5a  stloc.s  4
0x11a5c  ldarg.2
0x11a5d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x11a62  ldstr    aSystemuser// "systemuser"
0x11a67  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11a6c  brtrue.s loc_11A83
0x11a6e  ldarg.2
0x11a6f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x11a74  ldstr    aTeam// "team"
0x11a79  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11a7e  brfalse  loc_11B83
0x11a83  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11a88  stloc.s  7
0x11a8a  ldarg.2
0x11a8b  ldstr    aBusinessunitid// "businessunitid"
0x11a90  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x11a95  brfalse.s loc_11ABD
0x11a97  ldarg.2
0x11a98  ldstr    aBusinessunitid// "businessunitid"
0x11a9d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x11aa2  brfalse.s loc_11ABD
0x11aa4  ldarg.2
0x11aa5  ldstr    aBusinessunitid// "businessunitid"
0x11aaa  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x11aaf  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x11ab4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x11ab9  stloc.s  7
0x11abb  br.s     loc_11AE0
0x11abd  ldarg.0
0x11abe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x11ac3  stloc.s  7
0x11ac5  ldarg.2
0x11ac6  ldstr    aBusinessunitid// "businessunitid"
0x11acb  ldstr    aBusinessunit// "businessunit"
0x11ad0  ldarg.0
0x11ad1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x11ad6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x11adb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11ae0  ldarg.0
0x11ae1  ldloc.s  7
0x11ae3  ldloca.s 4
0x11ae5  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::TryGetSalesPersonRoleId(valuetype [mscorlib]System.Guid businessUnitId, [out] valuetype [mscorlib]System.Guid& roleId)
0x11aea  stloc.s  8
0x11aec  ldarg.2
0x11aed  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x11af2  ldstr    aSystemuser// "systemuser"
0x11af7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11afc  brfalse.s loc_11B44
0x11afe  ldarg.0
0x11aff  ldarg.2
0x11b00  ldloc.s  7
0x11b02  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::ValidateEntityForSystemUserCreateAndFillDefaults(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity user, valuetype [mscorlib]System.Guid businessUnitId)
0x11b07  brtrue.s loc_11B44
0x11b09  ldarg.0
0x11b0a  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x11b0f  ldarg.0
0x11b10  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x11b15  ldarg.0
0x11b16  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x11b1b  ldarg.3
0x11b1c  ldarg.s  4
0x11b1e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x11b23  ldc.i4.2
0x11b24  ldsfld   string [mscorlib]System.String::Empty
0x11b29  ldsfld   string [mscorlib]System.String::Empty
0x11b2e  ldc.i4   0x80048438
0x11b33  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x11b38  ldstr    aFirstnameLastn// "firstname, lastname, internalemailaddre"...
0x11b3d  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x11b42  ldc.i4.0
0x11b43  ret
0x11b44  ldloc.s  8
0x11b46  brtrue.s loc_11BA7
0x11b48  ldarg.0
0x11b49  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x11b4e  ldarg.0
0x11b4f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x11b54  ldarg.0
0x11b55  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x11b5a  ldarg.3
0x11b5b  ldarg.s  4
0x11b5d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x11b62  ldc.i4.2
0x11b63  ldsfld   string [mscorlib]System.String::Empty
0x11b68  ldsfld   string [mscorlib]System.String::Empty
0x11b6d  ldc.i4   0x80040216
0x11b72  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x11b77  ldstr    aCouldNotRetrie_0// "Could not retrieve salesperson role"
0x11b7c  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x11b81  ldc.i4.0
0x11b82  ret
0x11b83  ldloc.3
0x11b84  brfalse.s loc_11BA7
0x11b86  ldloc.2
0x11b87  brfalse.s loc_11BA7
0x11b89  ldarg.2
0x11b8a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11b8f  ldstr    aOwnerid_1// "ownerid"
0x11b94  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11b99  brtrue.s loc_11BA7
0x11b9b  ldarg.2
0x11b9c  ldstr    aOwnerid_1// "ownerid"
0x11ba1  ldloc.2
0x11ba2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11ba7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::.ctor()
0x11bac  stloc.s  5
0x11bae  ldloc.s  5
0x11bb0  ldarg.2
0x11bb1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x11bb6  ldloc.s  5
0x11bb8  ldstr    aSuppressduplic// "SuppressDuplicateDetection"
0x11bbd  ldloc.1
0x11bbe  ldc.i4.0
0x11bbf  ceq
0x11bc1  box      [mscorlib]System.Boolean
0x11bc6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x11bcb  ldloc.s  5
0x11bcd  ldstr    aCalculatematch// "CalculateMatchCodeSynchronously"
0x11bd2  ldloc.1
0x11bd3  box      [mscorlib]System.Boolean
0x11bd8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x11bdd  ldnull
0x11bde  stloc.s  6
0x11be0  ldc.i4.1
0x11be1  stloc.s  9
0x11be3  ldc.i4.1
0x11be4  stloc.s  0xA
0x11be6  ldc.i4.1
0x11be7  stloc.s  0xB
0x11be9  ldc.i4.1
0x11bea  stloc.s  0xC
0x11bec  ldloc.2
0x11bed  brfalse  loc_11E51
0x11bf2  ldarg.2
0x11bf3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11bf8  ldstr    aOwnerid_1// "ownerid"
0x11bfd  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11c02  brfalse  loc_11E51
0x11c07  ldarg.2
0x11c08  ldstr    aOwnerid_1// "ownerid"
0x11c0d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x11c12  ldloc.2
0x11c13  bne.un   loc_11E51
0x11c18  ldc.i4.0
0x11c19  stloc.s  0xC
0x11c1b  br       loc_11E51
0x11c20  nop
0x11c21  ldarg.0
0x11c22  ldloc.0
0x11c23  ldarg.1
0x11c24  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::IfUseUpsert(class Microsoft.Crm.Asynchronous.ImportFileHelperData importFileData, valuetype [mscorlib]System.Guid organizationId)
0x11c29  brfalse.s loc_11C66
0x11c2b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertRequest::.ctor()
0x11c30  stloc.s  0xD
0x11c32  ldloc.s  0xD
0x11c34  ldarg.2
0x11c35  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x11c3a  ldarg.0
0x11c3b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x11c40  ldloc.s  0xD
0x11c42  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x11c47  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertResponse
0x11c4c  stloc.s  0xE
0x11c4e  ldarg.s  5
0x11c50  ldloc.s  0xE
0x11c52  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpsertResponse::get_Target()
0x11c57  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x11c5c  stobj    [mscorlib]System.Guid
0x11c61  ldc.i4.0
0x11c62  stloc.s  0xA
0x11c64  br.s     loc_11C8B
0x11c66  ldarg.0
0x11c67  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x11c6c  ldloc.s  5
0x11c6e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x11c73  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse
0x11c78  stloc.s  6
0x11c7a  ldarg.s  5
0x11c7c  ldloc.s  6
0x11c7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.CreateResponse::get_id()
0x11c83  stobj    [mscorlib]System.Guid
0x11c88  ldc.i4.0
0x11c89  stloc.s  0xA
0x11c8b  leave    loc_11E51
0x11c90  stloc.s  0xF
0x11c92  ldloc.s  0xF
0x11c94  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x11c99  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x11c9e  stloc.s  0x10
0x11ca0  ldloc.s  0xF
0x11ca2  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x11ca7  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetCallStack(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault fault)
0x11cac  stloc.s  0x11
0x11cae  ldloc.s  0x10
0x11cb0  ldc.i4   0x8004A001
0x11cb5  bne.un.s loc_11CBF
0x11cb7  ldloc.s  9
0x11cb9  ldc.i4.3
0x11cba  ble      loc_11E22
0x11cbf  ldloc.s  0x10
0x11cc1  ldc.i4   0x80048306
0x11cc6  beq.s    loc_11CEC
0x11cc8  ldloc.s  0x10
0x11cca  ldc.i4   0x80040220
0x11ccf  beq.s    loc_11CEC
0x11cd1  ldloc.s  0x10
0x11cd3  ldc.i4   0x80040231
0x11cd8  beq.s    loc_11CEC
0x11cda  ldloc.s  0x10
0x11cdc  ldc.i4   0x80042F09
0x11ce1  beq.s    loc_11CEC
0x11ce3  ldloc.s  0x10
0x11ce5  ldc.i4   0x80040217
0x11cea  bne.un.s loc_11D26
0x11cec  ldloc.3
0x11ced  ldloc.s  0xB
0x11cef  and
0x11cf0  brfalse.s loc_11D26
0x11cf2  ldloc.s  0xC
0x11cf4  brfalse.s loc_11D0D
0x11cf6  ldloc.2
0x11cf7  brfalse.s loc_11D0D
0x11cf9  ldarg.2
0x11cfa  ldstr    aOwnerid_1// "ownerid"
0x11cff  ldloc.2
0x11d00  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x11d05  ldc.i4.0
0x11d06  stloc.s  0xC
0x11d08  leave    loc_11E51
0x11d0d  ldarg.2
0x11d0e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11d13  ldstr    aOwnerid_1// "ownerid"
0x11d18  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0x11d1d  pop
0x11d1e  ldc.i4.0
0x11d1f  stloc.s  0xB
0x11d21  leave    loc_11E51
0x11d26  ldloc.s  0xF
0x11d28  ldarg.1
0x11d29  ldc.i4.s 0x18
0x11d2b  ldstr    aErrorInCreateI// "Error in Create. ImportDataId {0} | Det"...
0x11d30  ldc.i4.2
0x11d31  newarr   [mscorlib]System.Object
0x11d36  dup
0x11d37  ldc.i4.0
0x11d38  ldarg.s  4
0x11d3a  box      [mscorlib]System.Guid
0x11d3f  stelem.ref
0x11d40  dup
0x11d41  ldc.i4.1
0x11d42  ldloc.s  0x11
0x11d44  stelem.ref
0x11d45  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11d4a  ldloc.s  0x10
0x11d4c  ldc.i4   0x80040237
0x11d51  bne.un   loc_11DDD
0x11d56  ldarg.1
0x11d57  ldc.i4.s 0x18
0x11d59  ldstr    aRecordWithPrim// "Record with primary key for ImportDataI"...
0x11d5e  ldc.i4.1
0x11d5f  newarr   [mscorlib]System.Object
0x11d64  dup
0x11d65  ldc.i4.0
0x11d66  ldarg.s  4
0x11d68  box      [mscorlib]System.Guid
0x11d6d  stelem.ref
0x11d6e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11d73  ldarg.0
0x11d74  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x11d79  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x11d7e  ldarg.3
0x11d7f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x11d84  callvirt instance string Microsoft.Crm.Asynchronous.ImportFileHelperData::get_PrimaryKeyName()
0x11d89  stloc.s  0x12
0x11d8b  ldarg.2
0x11d8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
  ... truncated ...
```
