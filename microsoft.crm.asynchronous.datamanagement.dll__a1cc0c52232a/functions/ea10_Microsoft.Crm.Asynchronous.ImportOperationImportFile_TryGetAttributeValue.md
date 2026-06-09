# Microsoft.Crm.Asynchronous.ImportOperationImportFile::TryGetAttributeValue

- ea: `0xea10`
- end: `0xee12`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::TryGetAttributeValue`
- size: `1026`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0xf190`
- `0x10ec0`

## callees

- `0x3bb0`
- `0x51f0`
- `0x5ed0`
- `0x5ef0`
- `0x60c0`
- `0x60d0`
- `0x61d0`
- `0x8f70`
- `0xea10`
- `0xeed0`
- `0xfd00`
- `0x13900`
- `0x13e50`

## string_xrefs

- `0xea44`: `overriddencreatedon`
- `0xeb45`: `Attribute {0} is not ValidForCreate.ImportDataId {1}`
- `0xeb6d`: `Target CRM Attribute: {0} for CRM Entity: {1} is not ValidForCreate.`

## pseudocode

```c

```

## disassembly

```asm
0xea10  ldarg.s  4
0xea12  ldc.i4.2
0xea13  ldelem.ref
0xea14  unbox.any [mscorlib]System.Guid
0xea19  stloc.0
0xea1a  ldarg.s  4
0xea1c  ldc.i4.3
0xea1d  ldelem.ref
0xea1e  unbox.any [mscorlib]System.Boolean
0xea23  stloc.1
0xea24  ldarg.0
0xea25  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xea2a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0xea2f  ldarg.s  5
0xea31  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0xea36  stloc.2
0xea37  ldarg.0
0xea38  ldarg.s  5
0xea3a  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetImportFileType(valuetype [mscorlib]System.Guid importFileId)
0xea3f  stloc.3
0xea40  ldloc.1
0xea41  brfalse.s loc_EA56
0xea43  ldarg.1
0xea44  ldstr    aOverriddencrea// "overriddencreatedon"
0xea49  call     bool [mscorlib]System.String::op_Equality(string, string)
0xea4e  brfalse.s loc_EA56
0xea50  ldarg.s  9
0xea52  ldc.i4.1
0xea53  stind.i1
0xea54  ldc.i4.1
0xea55  ret
0xea56  nop
0xea57  ldloc.2
0xea58  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_SchemaColumnNameToAttributeMetadataDictionary()
0xea5d  ldarg.1
0xea5e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(void)
0xea63  stloc.s  4
0xea65  ldarg.s  9
0xea67  ldc.i4.0
0xea68  stind.i1
0xea69  ldarg.s  0xA
0xea6b  ldsfld   string [mscorlib]System.String::Empty
0xea70  stind.ref
0xea71  ldloc.s  4
0xea73  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xea78  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xea7d  ldc.i4.s 0xE
0xea7f  ceq
0xea81  stloc.s  5
0xea83  ldarg.s  4
0xea85  ldarg.2
0xea86  ldelem.ref
0xea87  brfalse.s loc_EAB2
0xea89  ldarg.s  4
0xea8b  ldarg.2
0xea8c  ldelem.ref
0xea8d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea92  beq.s    loc_EAB2
0xea94  ldarg.s  4
0xea96  ldarg.2
0xea97  ldelem.ref
0xea98  isinst   [mscorlib]System.String
0xea9d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeaa2  brtrue.s loc_EAB2
0xeaa4  ldarg.s  0xA
0xeaa6  ldarg.s  4
0xeaa8  ldarg.2
0xeaa9  ldelem.ref
0xeaaa  castclass [mscorlib]System.String
0xeaaf  stind.ref
0xeab0  br.s     loc_EB21
0xeab2  ldloc.1
0xeab3  brtrue.s loc_EB21
0xeab5  ldarg.3
0xeab6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeabb  brfalse.s loc_EAEA
0xeabd  ldarg.s  6
0xeabf  ldc.i4.s 0x18
0xeac1  ldstr    aSkippingTheEmp// "Skipping the empty value for transforma"...
0xeac6  ldc.i4.3
0xeac7  newarr   [mscorlib]System.Object
0xeacc  dup
0xeacd  ldc.i4.0
0xeace  ldarg.1
0xeacf  stelem.ref
0xead0  dup
0xead1  ldc.i4.1
0xead2  ldarg.s  5
0xead4  box      [mscorlib]System.Guid
0xead9  stelem.ref
0xeada  dup
0xeadb  ldc.i4.2
0xeadc  ldloc.0
0xeadd  box      [mscorlib]System.Guid
0xeae2  stelem.ref
0xeae3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeae8  br.s     loc_EB15
0xeaea  ldarg.s  6
0xeaec  ldc.i4.s 0x18
0xeaee  ldstr    aSkippingTheEmp_0// "Skipping the empty value for column {0}"...
0xeaf3  ldc.i4.3
0xeaf4  newarr   [mscorlib]System.Object
0xeaf9  dup
0xeafa  ldc.i4.0
0xeafb  ldarg.3
0xeafc  stelem.ref
0xeafd  dup
0xeafe  ldc.i4.1
0xeaff  ldarg.s  5
0xeb01  box      [mscorlib]System.Guid
0xeb06  stelem.ref
0xeb07  dup
0xeb08  ldc.i4.2
0xeb09  ldloc.0
0xeb0a  box      [mscorlib]System.Guid
0xeb0f  stelem.ref
0xeb10  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb15  ldarg.s  9
0xeb17  ldc.i4.1
0xeb18  stind.i1
0xeb19  ldc.i4.1
0xeb1a  stloc.s  9
0xeb1c  leave    loc_EE0F
0xeb21  ldloc.s  5
0xeb23  ldc.i4.0
0xeb24  ceq
0xeb26  ldarg.s  8
0xeb28  and
0xeb29  brfalse  loc_EBEE
0xeb2e  ldloc.1
0xeb2f  brtrue   loc_EBEE
0xeb34  ldloc.s  4
0xeb36  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0xeb3b  brtrue   loc_EBEE
0xeb40  ldnull
0xeb41  ldarg.s  6
0xeb43  ldc.i4.s 0x18
0xeb45  ldstr    aAttribute0IsNo// "Attribute {0} is not ValidForCreate.Imp"...
0xeb4a  ldc.i4.2
0xeb4b  newarr   [mscorlib]System.Object
0xeb50  dup
0xeb51  ldc.i4.0
0xeb52  ldloc.s  4
0xeb54  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xeb59  stelem.ref
0xeb5a  dup
0xeb5b  ldc.i4.1
0xeb5c  ldloc.0
0xeb5d  box      [mscorlib]System.Guid
0xeb62  stelem.ref
0xeb63  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xeb68  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeb6d  ldstr    aTargetCrmAttri// "Target CRM Attribute: {0} for CRM Entit"...
0xeb72  ldc.i4.2
0xeb73  newarr   [mscorlib]System.Object
0xeb78  dup
0xeb79  ldc.i4.0
0xeb7a  ldloc.s  4
0xeb7c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xeb81  stelem.ref
0xeb82  dup
0xeb83  ldc.i4.1
0xeb84  ldloc.s  4
0xeb86  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0xeb8b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xeb90  stelem.ref
0xeb91  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xeb96  stloc.s  0xA
0xeb98  ldarg.0
0xeb99  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xeb9e  ldarg.0
0xeb9f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xeba4  ldarg.0
0xeba5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xebaa  ldarg.s  5
0xebac  ldloc.0
0xebad  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xebb2  ldarg.s  8
0xebb4  brtrue.s loc_EBB9
0xebb6  ldc.i4.3
0xebb7  br.s     loc_EBBA
0xebb9  ldc.i4.2
0xebba  ldarg.3
0xebbb  ldarg.3
0xebbc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xebc1  brtrue.s loc_EBC8
0xebc3  ldarg.s  0xA
0xebc5  ldind.ref
0xebc6  br.s     loc_EBCD
0xebc8  ldsfld   string [mscorlib]System.String::Empty
0xebcd  ldc.i4   0x80048438
0xebd2  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xebd7  ldloc.s  0xA
0xebd9  ldarg.s  8
0xebdb  brtrue.s loc_EBE0
0xebdd  ldc.i4.1
0xebde  br.s     loc_EBE1
0xebe0  ldc.i4.0
0xebe1  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0xebe6  ldc.i4.0
0xebe7  stloc.s  9
0xebe9  leave    loc_EE0F
0xebee  ldarg.3
0xebef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xebf4  stloc.s  6
0xebf6  ldloc.2
0xebf7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0xebfc  ldstr    aDatadelimiterc// "datadelimitercode"
0xec01  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xec06  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xec0b  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xec10  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CsvDataParser::GetDataDelimiter(int32)
0xec15  stloc.s  7
0xec17  ldc.i4.1
0xec18  stloc.s  8
0xec1a  ldloc.1
0xec1b  brfalse.s loc_EC98
0xec1d  ldloc.s  6
0xec1f  brtrue.s loc_EC98
0xec21  ldloc.2
0xec22  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumnForNewValueToHeaderColumnForOldValueDictionary()
0xec27  ldsfld   string [mscorlib]System.String::Empty
0xec2c  stloc.s  0xB
0xec2e  ldnull
0xec2f  stloc.s  0xC
0xec31  ldarg.3
0xec32  ldloca.s 0xB
0xec34  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0xec39  brfalse.s loc_EC78
0xec3b  ldloc.2
0xec3c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumnToParsedTableColumnIndexDictionary()
0xec41  ldloc.s  0xB
0xec43  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xec48  stloc.s  0xD
0xec4a  ldloc.s  0xD
0xec4c  ldarg.s  4
0xec4e  ldlen
0xec4f  conv.i4
0xec50  bge.s    loc_EC78
0xec52  ldarg.s  4
0xec54  ldloc.s  0xD
0xec56  ldelem.ref
0xec57  brfalse.s loc_EC71
0xec59  ldarg.s  4
0xec5b  ldloc.s  0xD
0xec5d  ldelem.ref
0xec5e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xec63  beq.s    loc_EC71
0xec65  ldarg.s  4
0xec67  ldloc.s  0xD
0xec69  ldelem.ref
0xec6a  castclass [mscorlib]System.String
0xec6f  br.s     loc_EC76
0xec71  ldsfld   string [mscorlib]System.String::Empty
0xec76  stloc.s  0xC
0xec78  ldloc.s  0xC
0xec7a  brfalse.s loc_EC98
0xec7c  ldarg.0
0xec7d  ldarg.s  0xA
0xec7f  ldind.ref
0xec80  ldloc.s  0xC
0xec82  ldloc.1
0xec83  ldloc.s  7
0xec85  ldloc.3
0xec86  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::WantToSkip(string attributeValue, object referenceValue, bool isExistingRecord, string dataDelimiter, int32 fileTypeCode)
0xec8b  ldc.i4.0
0xec8c  ceq
0xec8e  stloc.s  8
0xec90  ldarg.s  9
0xec92  ldloc.s  8
0xec94  ldc.i4.0
0xec95  ceq
0xec97  stind.i1
0xec98  ldarg.s  9
0xec9a  ldind.u1
0xec9b  brtrue.s loc_ECEA
0xec9d  ldarg.s  7
0xec9f  brfalse.s loc_ECEA
0xeca1  ldarg.s  7
0xeca3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xeca8  ldarg.1
0xeca9  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xecae  brtrue.s loc_ECBD
0xecb0  ldarg.s  9
0xecb2  ldarg.s  0xA
0xecb4  ldind.ref
0xecb5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xecba  stind.i1
0xecbb  br.s     loc_ECEA
0xecbd  ldarg.s  9
0xecbf  ldarg.0
0xecc0  ldarg.s  0xA
0xecc2  ldind.ref
0xecc3  ldarg.s  7
0xecc5  ldarg.1
0xecc6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xeccb  ldloc.1
0xeccc  ldloc.s  7
0xecce  ldloc.3
0xeccf  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::WantToSkip(string attributeValue, object referenceValue, bool isExistingRecord, string dataDelimiter, int32 fileTypeCode)
  ... truncated ...
```
