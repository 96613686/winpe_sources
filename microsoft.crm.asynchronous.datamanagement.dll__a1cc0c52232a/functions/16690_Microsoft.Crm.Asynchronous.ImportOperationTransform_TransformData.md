# Microsoft.Crm.Asynchronous.ImportOperationTransform::TransformData

- ea: `0x16690`
- end: `0x16be3`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::TransformData`
- size: `1363`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x16570`

## callees

- `0x3b80`
- `0x3ec0`
- `0x45f0`
- `0x5ed0`
- `0x5ef0`
- `0x6030`
- `0x6050`
- `0x6090`
- `0x60a0`
- `0x8f20`
- `0x8f40`
- `0x8f60`
- `0x8f70`
- `0x16690`
- `0x16bf0`
- `0x16f30`
- `0x17420`
- `0x17670`
- `0x17750`
- `0x19b90`
- `0x1b1e0`
- `0x1b860`
- `0x1c630`
- `0x1ce10`

## string_xrefs

- `0x16979`: `Applying Complex transformations. ImportFileId {0}`

## pseudocode

```c

```

## disassembly

```asm
0x16690  ldarg.0
0x16691  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x16696  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0x1669b  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x166a0  stloc.0
0x166a1  br       loc_16820
0x166a6  ldloca.s 0
0x166a8  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x166ad  stloc.1
0x166ae  ldarg.0
0x166af  ldarg.2
0x166b0  ldloc.1
0x166b1  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationTransform::SkipImportFile(valuetype [mscorlib]System.Guid importId, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> kvp_importfile)
0x166b6  brtrue   loc_16820
0x166bb  ldarg.0
0x166bc  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x166c1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x166c6  ldloca.s 1
0x166c8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x166cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x166d2  stloc.2
0x166d3  ldnull
0x166d4  stloc.3
0x166d5  ldloca.s 1
0x166d7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x166dc  ldstr    aProcessingstat_0// "processingstatus"
0x166e1  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x166e6  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x166eb  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x166f0  ldc.i4.3
0x166f1  bne.un.s loc_16762
0x166f3  ldloc.2
0x166f4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_PrimaryKeyColumnMapping()
0x166f9  brfalse.s loc_16721
0x166fb  ldarg.0
0x166fc  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x16701  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x16706  brtrue.s loc_16716
0x16708  ldarg.0
0x16709  ldloca.s 1
0x1670b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x16710  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyPrimaryKeyTransformations(valuetype [mscorlib]System.Guid importFileId)
0x16715  stloc.3
0x16716  ldloc.3
0x16717  brfalse.s loc_16721
0x16719  ldloc.3
0x1671a  stloc.s  4
0x1671c  leave    loc_16BE0
0x16721  ldarg.0
0x16722  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x16727  ldloca.s 1
0x16729  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x1672e  ldc.i4.4
0x1672f  ldc.i4.0
0x16730  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetProcessingStatusDetail(valuetype [mscorlib]System.Guid importFileId, int32 processingStatusDetail, int32 progressCounter)
0x16735  ldloca.s 1
0x16737  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x1673c  ldstr    aProcessingstat_0// "processingstatus"
0x16741  ldc.i4.4
0x16742  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x16747  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1674c  ldloc.2
0x1674d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x16752  ldstr    aProcessingstat_0// "processingstatus"
0x16757  ldc.i4.4
0x16758  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1675d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x16762  ldloca.s 1
0x16764  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x16769  ldstr    aProcessingstat_0// "processingstatus"
0x1676e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x16773  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x16778  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x1677d  ldc.i4.4
0x1677e  bne.un.s loc_167F5
0x16780  ldloc.2
0x16781  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ResolutionMappingCollection()
0x16786  brfalse.s loc_167B4
0x16788  ldloc.2
0x16789  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ResolutionMappingCollection()
0x1678e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x16793  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x16798  ldc.i4.0
0x16799  ble.s    loc_167B4
0x1679b  ldarg.0
0x1679c  ldloca.s 1
0x1679e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x167a3  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyResolutionTransformations(valuetype [mscorlib]System.Guid importFileId)
0x167a8  stloc.3
0x167a9  ldloc.3
0x167aa  brfalse.s loc_167B4
0x167ac  ldloc.3
0x167ad  stloc.s  4
0x167af  leave    loc_16BE0
0x167b4  ldarg.0
0x167b5  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x167ba  ldloca.s 1
0x167bc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x167c1  ldc.i4.5
0x167c2  ldc.i4.0
0x167c3  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetProcessingStatusDetail(valuetype [mscorlib]System.Guid importFileId, int32 processingStatusDetail, int32 progressCounter)
0x167c8  ldloca.s 1
0x167ca  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x167cf  ldstr    aProcessingstat_0// "processingstatus"
0x167d4  ldc.i4.5
0x167d5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x167da  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x167df  ldloc.2
0x167e0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x167e5  ldstr    aProcessingstat_0// "processingstatus"
0x167ea  ldc.i4.5
0x167eb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x167f0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x167f5  ldarg.0
0x167f6  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x167fb  ldloc.2
0x167fc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x16801  ldstr    aParsedtablenam_0// "parsedtablename"
0x16806  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1680b  ldloc.2
0x1680c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x16811  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x16816  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1681b  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateNonClusteredIndexOnCOL0(string tableName, string columnPrefix)
0x16820  ldloca.s 0
0x16822  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::MoveNext()
0x16827  brtrue   loc_166A6
0x1682c  leave.s  loc_1683C
0x1682e  ldloca.s 0
0x16830  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x16836  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1683b  endfinally
0x1683c  ldarg.0
0x1683d  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x16842  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0x16847  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1684c  stloc.0
0x1684d  br       loc_16BBE
0x16852  ldloca.s 0
0x16854  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x16859  stloc.s  5
0x1685b  ldarg.0
0x1685c  ldarg.2
0x1685d  ldloc.s  5
0x1685f  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationTransform::SkipImportFile(valuetype [mscorlib]System.Guid importId, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> kvp_importfile)
0x16864  brtrue   loc_16BBE
0x16869  ldarg.0
0x1686a  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1686f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x16874  ldloca.s 5
0x16876  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x1687b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x16880  stloc.s  6
0x16882  ldnull
0x16883  stloc.s  7
0x16885  ldloca.s 5
0x16887  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x1688c  ldstr    aProcessingstat_0// "processingstatus"
0x16891  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x16896  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x1689b  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x168a0  ldc.i4.5
0x168a1  bne.un.s loc_16901
0x168a3  ldarg.0
0x168a4  ldloca.s 5
0x168a6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x168ab  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyOwnerTransformations(valuetype [mscorlib]System.Guid importFileId)
0x168b0  stloc.s  7
0x168b2  ldloc.s  7
0x168b4  brfalse.s loc_168BF
0x168b6  ldloc.s  7
0x168b8  stloc.s  4
0x168ba  leave    loc_16BE0
0x168bf  ldarg.0
0x168c0  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x168c5  ldloca.s 5
0x168c7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x168cc  ldc.i4.6
0x168cd  ldc.i4.0
0x168ce  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetProcessingStatusDetail(valuetype [mscorlib]System.Guid importFileId, int32 processingStatusDetail, int32 progressCounter)
0x168d3  ldloca.s 5
0x168d5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x168da  ldstr    aProcessingstat_0// "processingstatus"
0x168df  ldc.i4.6
0x168e0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x168e5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x168ea  ldloc.s  6
0x168ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x168f1  ldstr    aProcessingstat_0// "processingstatus"
0x168f6  ldc.i4.6
0x168f7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x168fc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x16901  ldloca.s 5
0x16903  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x16908  ldstr    aProcessingstat_0// "processingstatus"
0x1690d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x16912  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x16917  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x1691c  ldc.i4.6
0x1691d  bne.un   loc_169F6
0x16922  ldloc.s  6
0x16924  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TransformationMappingIdToTransformationMappingHelperDataDictionary()
0x16929  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::get_Count()
0x1692e  ldc.i4.0
0x1692f  ble      loc_169B4
0x16934  ldloc.s  6
0x16936  callvirt instance string Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TargetEntityName()
0x1693b  ldstr    aSystemuser// "systemuser"
0x16940  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x16945  brfalse.s loc_169B4
0x16947  ldarg.1
0x16948  ldc.i4.s 0x18
0x1694a  ldstr    aCreatingAdditi// "Creating Additional Header Columns. Imp"...
0x1694f  ldc.i4.1
0x16950  newarr   [mscorlib]System.Object
0x16955  dup
0x16956  ldc.i4.0
0x16957  ldloca.s 5
0x16959  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x1695e  box      [mscorlib]System.Guid
0x16963  stelem.ref
0x16964  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16969  ldarg.0
0x1696a  ldloca.s 5
0x1696c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x16971  call     instance void Microsoft.Crm.Asynchronous.ImportOperationTransform::DeriveAdditionalHeaderRowAndCreateColumns(valuetype [mscorlib]System.Guid importFileId)
0x16976  ldarg.1
0x16977  ldc.i4.s 0x18
0x16979  ldstr    aApplyingComple// "Applying Complex transformations. Impor"...
0x1697e  ldc.i4.1
0x1697f  newarr   [mscorlib]System.Object
0x16984  dup
0x16985  ldc.i4.0
0x16986  ldloca.s 5
0x16988  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x1698d  box      [mscorlib]System.Guid
0x16992  stelem.ref
0x16993  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16998  ldarg.0
0x16999  ldloca.s 5
0x1699b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x169a0  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyComplexTransformations(valuetype [mscorlib]System.Guid importFileId)
0x169a5  stloc.s  7
0x169a7  ldloc.s  7
0x169a9  brfalse.s loc_169B4
0x169ab  ldloc.s  7
0x169ad  stloc.s  4
0x169af  leave    loc_16BE0
0x169b4  ldarg.0
0x169b5  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x169ba  ldloca.s 5
0x169bc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x169c1  ldc.i4.7
0x169c2  ldc.i4.0
0x169c3  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetProcessingStatusDetail(valuetype [mscorlib]System.Guid importFileId, int32 processingStatusDetail, int32 progressCounter)
0x169c8  ldloca.s 5
0x169ca  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x169cf  ldstr    aProcessingstat_0// "processingstatus"
0x169d4  ldc.i4.7
0x169d5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x169da  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x169df  ldloc.s  6
0x169e1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x169e6  ldstr    aProcessingstat_0// "processingstatus"
0x169eb  ldc.i4.7
0x169ec  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x169f1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x169f6  ldloca.s 5
0x169f8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x169fd  ldstr    aProcessingstat_0// "processingstatus"
0x16a02  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x16a07  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x16a0c  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x16a11  ldc.i4.7
0x16a12  bne.un.s loc_16A90
0x16a14  ldloc.s  6
0x16a16  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TransformationMappingIdToTransformationMappingHelperDataDictionary()
0x16a1b  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::get_Count()
0x16a20  ldc.i4.0
0x16a21  bgt.s    loc_16A32
0x16a23  ldloc.s  6
0x16a25  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ColumnMappingIdToLookupMappingCollectionDictionary()
0x16a2a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::get_Count()
0x16a2f  ldc.i4.0
0x16a30  ble.s    loc_16A4E
0x16a32  ldarg.0
0x16a33  ldloca.s 5
0x16a35  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x16a3a  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyLookupTransformations(valuetype [mscorlib]System.Guid importFileId)
0x16a3f  stloc.s  7
0x16a41  ldloc.s  7
0x16a43  brfalse.s loc_16A4E
0x16a45  ldloc.s  7
0x16a47  stloc.s  4
0x16a49  leave    loc_16BE0
0x16a4e  ldarg.0
0x16a4f  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x16a54  ldloca.s 5
0x16a56  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x16a5b  ldc.i4.8
  ... truncated ...
```
