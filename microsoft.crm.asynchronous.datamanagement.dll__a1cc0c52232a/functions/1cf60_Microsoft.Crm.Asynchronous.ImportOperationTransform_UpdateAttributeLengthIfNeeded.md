# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAttributeLengthIfNeeded

- ea: `0x1cf60`
- end: `0x1d042`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAttributeLengthIfNeeded`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ce10`

## callees

- `0x4ab0`
- `0x8f40`
- `0x1cf60`
- `0x1d050`

## pseudocode

```c

```

## disassembly

```asm
0x1cf60  ldarg.1
0x1cf61  ldarg.2
0x1cf62  ldc.i4.1
0x1cf63  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1cf68  stloc.0
0x1cf69  ldloc.0
0x1cf6a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsCustomizable()
0x1cf6f  brfalse.s loc_1CF79
0x1cf71  ldloc.0
0x1cf72  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanModifyAdditionalSettings()
0x1cf77  brtrue.s loc_1CF7B
0x1cf79  ldc.i4.0
0x1cf7a  ret
0x1cf7b  ldloc.0
0x1cf7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x1cf81  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x1cf86  ldc.i4.s 0x10
0x1cf88  beq.s    loc_1CF9B
0x1cf8a  ldloc.0
0x1cf8b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x1cf90  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x1cf95  ldc.i4.8
0x1cf96  bne.un   loc_1D040
0x1cf9b  ldloc.0
0x1cf9c  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0x1cfa1  stloc.1
0x1cfa2  ldloc.0
0x1cfa3  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MemoAttributeMetadata
0x1cfa8  stloc.2
0x1cfa9  ldloc.1
0x1cfaa  brtrue.s loc_1CFB1
0x1cfac  ldloc.2
0x1cfad  brtrue.s loc_1CFB1
0x1cfaf  ldc.i4.0
0x1cfb0  ret
0x1cfb1  ldc.i4.0
0x1cfb2  stloc.3
0x1cfb3  ldc.i4.0
0x1cfb4  stloc.s  4
0x1cfb6  ldloc.1
0x1cfb7  brfalse.s loc_1CFC7
0x1cfb9  ldloc.1
0x1cfba  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x1cfbf  stloc.3
0x1cfc0  ldc.i4   0xFA0
0x1cfc5  stloc.s  4
0x1cfc7  ldloc.2
0x1cfc8  brfalse.s loc_1CFD8
0x1cfca  ldloc.2
0x1cfcb  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x1cfd0  stloc.3
0x1cfd1  ldc.i4   0x100000
0x1cfd6  stloc.s  4
0x1cfd8  ldarg.0
0x1cfd9  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1cfde  ldarg.3
0x1cfdf  ldarg.s  4
0x1cfe1  ldarg.0
0x1cfe2  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1cfe7  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x1cfec  ldc.i4.0
0x1cfed  ceq
0x1cfef  ldc.i4.s 9
0x1cff1  ldc.i4.0
0x1cff2  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveMaxLength(string tableName, string columnName, bool addIsExistingRecordCheck, int32 importFileStatusCode, bool successRowsOnly)
0x1cff7  stloc.s  5
0x1cff9  ldloc.3
0x1cffa  ldc.i4.0
0x1cffb  ble.s    loc_1D032
0x1cffd  ldloc.s  5
0x1cfff  ldloc.3
0x1d000  bge.s    loc_1D004
0x1d002  ldc.i4.0
0x1d003  ret
0x1d004  ldarg.0
0x1d005  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1d00a  ldarg.3
0x1d00b  ldarg.s  4
0x1d00d  ldarg.0
0x1d00e  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1d013  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x1d018  ldc.i4.0
0x1d019  ceq
0x1d01b  ldc.i4.s 9
0x1d01d  ldc.i4.1
0x1d01e  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveMaxLength(string tableName, string columnName, bool addIsExistingRecordCheck, int32 importFileStatusCode, bool successRowsOnly)
0x1d023  stloc.s  5
0x1d025  ldloc.s  5
0x1d027  ldloc.3
0x1d028  ble.s    loc_1D030
0x1d02a  ldloc.s  5
0x1d02c  ldloc.s  4
0x1d02e  ble.s    loc_1D032
0x1d030  ldc.i4.0
0x1d031  ret
0x1d032  ldarg.0
0x1d033  ldloc.0
0x1d034  ldloc.s  5
0x1d036  ldarg.s  5
0x1d038  ldarg.s  6
0x1d03a  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAttributeLength(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, int32 maxLength, valuetype [mscorlib]System.Guid importFileId, string sourceColumnName)
0x1d03f  ret
0x1d040  ldc.i4.0
0x1d041  ret
```
