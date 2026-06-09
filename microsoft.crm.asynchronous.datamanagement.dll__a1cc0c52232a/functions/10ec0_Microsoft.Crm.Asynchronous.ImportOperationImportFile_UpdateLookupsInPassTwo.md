# Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateLookupsInPassTwo

- ea: `0x10ec0`
- end: `0x115c9`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateLookupsInPassTwo`
- size: `1801`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10b00`

## callees

- `0x3b80`
- `0x51d0`
- `0x51f0`
- `0x5be0`
- `0x5c00`
- `0x5c30`
- `0x5c50`
- `0x5c60`
- `0x5c80`
- `0x5ef0`
- `0x5f20`
- `0x5f40`
- `0x5fb0`
- `0x6000`
- `0x6030`
- `0x60c0`
- `0x6190`
- `0x61d0`
- `0x8f40`
- `0x8f70`
- `0xea10`
- `0xfd00`
- `0x100c0`
- `0x10ec0`
- `0x115d0`
- `0x11690`
- `0x12d00`
- `0x13b80`

## string_xrefs

- `0x10fd9`: `Entity {0}:{1} has possibly been deleted from CRM`

## pseudocode

```c

```

## disassembly

```asm
0x10ec0  ldc.i4.0
0x10ec1  stloc.0
0x10ec2  ldarg.0
0x10ec3  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x10ec8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x10ecd  ldarg.2
0x10ece  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x10ed3  stloc.1
0x10ed4  ldarg.0
0x10ed5  ldarg.2
0x10ed6  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetImportFileType(valuetype [mscorlib]System.Guid importFileId)
0x10edb  stloc.2
0x10edc  ldloc.1
0x10edd  callvirt instance string Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TargetEntityName()
0x10ee2  stloc.3
0x10ee3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0x10ee8  stloc.s  4
0x10eea  ldloc.s  4
0x10eec  ldloc.3
0x10eed  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0x10ef2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10ef7  stloc.s  5
0x10ef9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10efe  stloc.s  6
0x10f00  ldc.i4.0
0x10f01  stloc.s  7
0x10f03  newobj   instance void Microsoft.Crm.Asynchronous.StateStatusHelper::.ctor()
0x10f08  stloc.s  8
0x10f0a  ldsfld   string [mscorlib]System.String::Empty
0x10f0f  stloc.s  9
0x10f11  ldsfld   string [mscorlib]System.String::Empty
0x10f16  stloc.s  0xA
0x10f18  ldarg.1
0x10f19  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x10f1e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10f23  ldloc.3
0x10f24  ldc.i4.1
0x10f25  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x10f2a  stloc.s  0xB
0x10f2c  ldloc.s  0xB
0x10f2e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x10f33  ldstr    aOpportunity// "opportunity"
0x10f38  ldc.i4.4
0x10f39  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x10f3e  stloc.s  0xC
0x10f40  ldsfld   string [mscorlib]System.String::Empty
0x10f45  stloc.s  0xD
0x10f47  ldsfld   string [mscorlib]System.String::Empty
0x10f4c  stloc.s  0xE
0x10f4e  ldsfld   string [mscorlib]System.String::Empty
0x10f53  stloc.s  0xF
0x10f55  ldc.i4.0
0x10f56  stloc.s  0x10
0x10f58  ldloc.s  0xB
0x10f5a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasStateCode()
0x10f5f  brfalse.s loc_10F84
0x10f61  ldloc.s  0xB
0x10f63  ldstr    aStatecode// "statecode"
0x10f68  ldc.i4.1
0x10f69  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x10f6e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x10f73  stloc.s  0x12
0x10f75  ldloc.s  8
0x10f77  ldloc.s  0x12
0x10f79  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_DefaultValue()
0x10f7e  ldc.i4.m1
0x10f7f  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::SetStateStatus(int32 stateCode, int32 statusCode)
0x10f84  nop
0x10f85  ldarg.3
0x10f86  ldc.i4.2
0x10f87  ldelem.ref
0x10f88  unbox.any [mscorlib]System.Guid
0x10f8d  stloc.s  5
0x10f8f  ldarg.3
0x10f90  ldc.i4.3
0x10f91  ldelem.ref
0x10f92  unbox.any [mscorlib]System.Boolean
0x10f97  stloc.s  7
0x10f99  ldarg.3
0x10f9a  ldc.i4.4
0x10f9b  ldelem.ref
0x10f9c  unbox.any [mscorlib]System.Guid
0x10fa1  stloc.s  6
0x10fa3  ldloc.s  7
0x10fa5  brfalse.s loc_10FBC
0x10fa7  ldarg.0
0x10fa8  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x10fad  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x10fb2  brtrue.s loc_10FBC
0x10fb4  ldc.i4.1
0x10fb5  stloc.s  0x14
0x10fb7  leave    loc_115C6
0x10fbc  ldnull
0x10fbd  stloc.s  0x13
0x10fbf  ldloc.s  7
0x10fc1  brfalse  loc_110BA
0x10fc6  ldarg.s  4
0x10fc8  brfalse.s loc_10FD5
0x10fca  ldarg.s  4
0x10fcc  ldloc.s  6
0x10fce  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::ContainsKey(var<u1>)
0x10fd3  brtrue.s loc_1104F
0x10fd5  ldnull
0x10fd6  ldarg.1
0x10fd7  ldc.i4.s 0x18
0x10fd9  ldstr    aEntity01HasPos// "Entity {0}:{1} has possibly been delete"...
0x10fde  ldc.i4.2
0x10fdf  newarr   [mscorlib]System.Object
0x10fe4  dup
0x10fe5  ldc.i4.0
0x10fe6  ldloc.3
0x10fe7  stelem.ref
0x10fe8  dup
0x10fe9  ldc.i4.1
0x10fea  ldloc.s  6
0x10fec  box      [mscorlib]System.Guid
0x10ff1  stelem.ref
0x10ff2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10ff7  ldloc.1
0x10ff8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_PrimaryKeyColumnMapping()
0x10ffd  ldstr    aSourceattribut// "sourceattributename"
0x11002  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x11007  stloc.s  9
0x11009  ldarg.0
0x1100a  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1100f  ldarg.0
0x11010  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x11015  ldarg.0
0x11016  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1101b  ldarg.2
0x1101c  ldloc.s  5
0x1101e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x11023  ldc.i4.3
0x11024  ldloc.s  9
0x11026  ldloca.s 6
0x11028  constrained. [mscorlib]System.Guid
0x1102e  callvirt instance string [mscorlib]System.Object::ToString()
0x11033  ldc.i4   0x8004F603
0x11038  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1103d  ldsfld   string [mscorlib]System.String::Empty
0x11042  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x11047  ldc.i4.0
0x11048  stloc.s  0x14
0x1104a  leave    loc_115C6
0x1104f  ldarg.s  4
0x11051  ldloc.s  6
0x11053  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x11058  stloc.s  0x13
0x1105a  ldloc.s  0x13
0x1105c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11061  ldstr    aStatecode// "statecode"
0x11066  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1106b  brfalse.s loc_1108A
0x1106d  ldloc.s  8
0x1106f  ldloc.s  0x13
0x11071  ldstr    aStatecode// "statecode"
0x11076  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1107b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x11080  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x11085  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_OldStateCode(int32 value)
0x1108a  ldloc.s  0x13
0x1108c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11091  ldstr    aStatuscode// "statuscode"
0x11096  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1109b  brfalse.s loc_110BA
0x1109d  ldloc.s  8
0x1109f  ldloc.s  0x13
0x110a1  ldstr    aStatuscode// "statuscode"
0x110a6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x110ab  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x110b0  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x110b5  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_OldStatusCode(int32 value)
0x110ba  ldloc.s  4
0x110bc  ldloc.s  6
0x110be  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x110c3  ldarg.s  5
0x110c5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x110ca  stloc.s  0x15
0x110cc  br       loc_1115D
0x110d1  ldloca.s 0x15
0x110d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x110d8  dup
0x110d9  ldstr    aTargetattribut// "targetattributename"
0x110de  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x110e3  stloc.s  0x16
0x110e5  ldstr    aSourceattribut// "sourceattributename"
0x110ea  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x110ef  stloc.s  9
0x110f1  ldloc.1
0x110f2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumnToParsedTableColumnIndexDictionary()
0x110f7  ldloc.s  9
0x110f9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x110fe  stloc.s  0x17
0x11100  ldc.i4.0
0x11101  stloc.s  0x18
0x11103  ldarg.0
0x11104  ldloc.s  0x16
0x11106  ldloc.s  0x17
0x11108  ldloc.s  9
0x1110a  ldarg.3
0x1110b  ldarg.2
0x1110c  ldarg.1
0x1110d  ldloc.s  0x13
0x1110f  ldc.i4.0
0x11110  ldloca.s 0x18
0x11112  ldloca.s 0xA
0x11114  ldloc.s  8
0x11116  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::TryGetAttributeValue(string targetAttributeName, int32 columnIndex, string sourceAttributeName, object[] colValues, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity originalEntity, bool isFirstPass, bool& skipAttribute, string& attributeValue, class Microsoft.Crm.Asynchronous.StateStatusHelper stateStatusHelper)
0x1111b  brtrue.s loc_11125
0x1111d  ldc.i4.0
0x1111e  stloc.s  0x14
0x11120  leave    loc_115C6
0x11125  ldloc.s  0x18
0x11127  brtrue.s loc_1115D
0x11129  ldloc.1
0x1112a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_SchemaColumnNameToAttributeMetadataDictionary()
0x1112f  ldloc.s  0x16
0x11131  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(void)
0x11136  stloc.s  0x19
0x11138  ldarg.0
0x11139  ldloc.s  0xC
0x1113b  ldloc.s  0x19
0x1113d  ldloc.s  0xA
0x1113f  ldloca.s 0xD
0x11141  ldloca.s 0xE
0x11143  call     instance void Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetOpportunityCloseFields(bool isOpportunity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, string attributeValue, string& opportunityCloseDate, string& opportunityActualRevenue)
0x11148  ldarg.0
0x11149  ldloc.s  0x19
0x1114b  ldloca.s 4
0x1114d  ldloc.s  0xA
0x1114f  ldloc.s  8
0x11151  ldloc.s  7
0x11153  ldloc.2
0x11154  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::FillDynamicEntityInstanceForPassTwo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity& dynamicEntity, string value, class Microsoft.Crm.Asynchronous.StateStatusHelper stateStatusHelper, bool isExistingRecord, int32 importFileType)
0x11159  brfalse.s loc_1115D
0x1115b  ldc.i4.1
0x1115c  stloc.0
0x1115d  ldloca.s 0x15
0x1115f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::MoveNext()
0x11164  brtrue   loc_110D1
0x11169  leave.s  loc_11179
0x1116b  ldloca.s 0x15
0x1116d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x11173  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11178  endfinally
0x11179  ldc.i4.1
0x1117a  stloc.s  0x10
0x1117c  ldarg.s  6
0x1117e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x11183  stloc.s  0x1A
0x11185  br       loc_1122D
0x1118a  ldloca.s 0x1A
0x1118c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x11191  stloc.s  0x1B
0x11193  ldsfld   string [mscorlib]System.String::Empty
0x11198  stloc.s  9
0x1119a  ldsfld   string [mscorlib]System.String::Empty
0x1119f  stloc.s  0xA
0x111a1  ldloc.1
0x111a2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_AdditionalHeaderColumnToParsedTableColumnIndexDictionary()
0x111a7  ldloc.s  0x1B
0x111a9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x111ae  stloc.s  0x1C
0x111b0  ldc.i4.0
0x111b1  stloc.s  0x1D
0x111b3  ldarg.0
0x111b4  ldloc.s  0x1B
0x111b6  ldloc.s  0x1C
0x111b8  ldloc.s  9
0x111ba  ldarg.3
0x111bb  ldarg.2
0x111bc  ldarg.1
0x111bd  ldnull
0x111be  ldc.i4.0
0x111bf  ldloca.s 0x1D
0x111c1  ldloca.s 0xA
0x111c3  ldloc.s  8
0x111c5  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::TryGetAttributeValue(string targetAttributeName, int32 columnIndex, string sourceAttributeName, object[] colValues, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity originalEntity, bool isFirstPass, bool& skipAttribute, string& attributeValue, class Microsoft.Crm.Asynchronous.StateStatusHelper stateStatusHelper)
0x111ca  brtrue.s loc_111D4
0x111cc  ldc.i4.0
0x111cd  stloc.s  0x14
0x111cf  leave    loc_115C6
0x111d4  ldloc.s  0x1D
0x111d6  brtrue.s loc_1122D
0x111d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x111dd  ldstr    aDataTypeMismat// "Data type mismatch for output parameter"...
0x111e2  ldc.i4.2
0x111e3  newarr   [mscorlib]System.Object
0x111e8  dup
0x111e9  ldc.i4.0
0x111ea  ldloc.s  0x1B
0x111ec  stelem.ref
0x111ed  dup
0x111ee  ldc.i4.1
0x111ef  ldloc.s  0xA
0x111f1  stelem.ref
0x111f2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x111f7  stloc.s  0xF
0x111f9  ldloc.1
0x111fa  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_SchemaColumnNameToAttributeMetadataDictionary()
  ... truncated ...
```
