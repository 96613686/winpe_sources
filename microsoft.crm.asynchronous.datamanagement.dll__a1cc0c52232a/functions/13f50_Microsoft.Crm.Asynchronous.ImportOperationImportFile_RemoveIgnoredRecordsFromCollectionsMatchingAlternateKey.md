# Microsoft.Crm.Asynchronous.ImportOperationImportFile::RemoveIgnoredRecordsFromCollectionsMatchingAlternateKey

- ea: `0x13f50`
- end: `0x14094`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::RemoveIgnoredRecordsFromCollectionsMatchingAlternateKey`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xe550`
- `0x10b00`

## callees

- `0x3b80`
- `0x5ef0`
- `0x60c0`
- `0x8f70`
- `0x13e50`
- `0x13f50`

## pseudocode

```c

```

## disassembly

```asm
0x13f50  ldarg.0
0x13f51  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x13f56  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x13f5b  ldarg.2
0x13f5c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x13f61  stloc.0
0x13f62  ldloc.0
0x13f63  callvirt instance string Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TargetEntityName()
0x13f68  stloc.1
0x13f69  ldarg.1
0x13f6a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x13f6f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13f74  ldloc.1
0x13f75  ldc.i4.1
0x13f76  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x13f7b  pop
0x13f7c  ldsfld   string [mscorlib]System.String::Empty
0x13f81  stloc.2
0x13f82  ldc.i4.0
0x13f83  stloc.3
0x13f84  br       loc_14087
0x13f89  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x13f8e  stloc.s  4
0x13f90  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor()
0x13f95  stloc.s  5
0x13f97  ldloc.s  5
0x13f99  ldloc.1
0x13f9a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_LogicalName(string)
0x13f9f  ldarg.s  5
0x13fa1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x13fa6  stloc.s  6
0x13fa8  br.s     loc_14004
0x13faa  ldloca.s 6
0x13fac  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x13fb1  dup
0x13fb2  ldstr    aTargetattribut// "targetattributename"
0x13fb7  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x13fbc  stloc.s  7
0x13fbe  ldstr    aSourceattribut// "sourceattributename"
0x13fc3  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x13fc8  stloc.s  8
0x13fca  ldloc.0
0x13fcb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumnToParsedTableColumnIndexDictionary()
0x13fd0  ldloc.s  8
0x13fd2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x13fd7  stloc.s  9
0x13fd9  ldarg.0
0x13fda  ldloc.s  7
0x13fdc  ldloc.0
0x13fdd  ldarg.1
0x13fde  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::isPresentInAlternateKey(string targetAttributeName, class Microsoft.Crm.Asynchronous.ImportFileHelperData importFileHelperData, valuetype [mscorlib]System.Guid organizationId)
0x13fe3  brfalse.s loc_14004
0x13fe5  ldarg.3
0x13fe6  ldloc.3
0x13fe7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Item(!!T0)
0x13fec  ldloc.s  9
0x13fee  ldelem.ref
0x13fef  castclass [mscorlib]System.String
0x13ff4  stloc.2
0x13ff5  ldloc.s  5
0x13ff7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.KeyAttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_KeyAttributes()
0x13ffc  ldloc.s  7
0x13ffe  ldloc.2
0x13fff  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x14004  ldloca.s 6
0x14006  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::MoveNext()
0x1400b  brtrue.s loc_13FAA
0x1400d  leave.s  loc_1401D
0x1400f  ldloca.s 6
0x14011  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x14017  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1401c  endfinally
0x1401d  ldloc.s  4
0x1401f  ldloc.s  5
0x14021  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x14026  ldloc.s  4
0x14028  ldc.i4.1
0x14029  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x1402e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x14033  ldarg.0
0x14034  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportOperation::_crmService
0x14039  ldloc.s  4
0x1403b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x14040  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0x14045  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x1404a  callvirt instance int32 class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Count()
0x1404f  brfalse.s loc_14061
0x14051  ldarg.3
0x14052  ldarg.3
0x14053  ldloc.3
0x14054  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Item(!!T0)
0x14059  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<object[]>::Remove(var<u1>)
0x1405e  pop
0x1405f  br.s     loc_14065
0x14061  ldloc.3
0x14062  ldc.i4.1
0x14063  add
0x14064  stloc.3
0x14065  leave.s  loc_14087
0x14067  stloc.s  0xA
0x14069  ldc.i4   0x80060891
0x1406e  ldloc.s  0xA
0x14070  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x14075  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x1407a  bne.un.s loc_14082
0x1407c  ldloc.3
0x1407d  ldc.i4.1
0x1407e  add
0x1407f  stloc.3
0x14080  br.s     loc_14085
0x14082  ldloc.s  0xA
0x14084  throw
0x14085  leave.s  loc_14087
0x14087  ldloc.3
0x14088  ldarg.3
0x14089  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Count()
0x1408e  blt      loc_13F89
0x14093  ret
```
