# Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyComplexTransformationsOnDataSet

- ea: `0x17910`
- end: `0x17eab`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyComplexTransformationsOnDataSet`
- size: `1435`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x17750`

## callees

- `0x3b80`
- `0x51d0`
- `0x58a0`
- `0x58b0`
- `0x58c0`
- `0x59d0`
- `0x5fd0`
- `0x60a0`
- `0x8f70`
- `0x9620`
- `0x9630`
- `0x9640`
- `0x9660`
- `0x9670`
- `0x96c0`
- `0x96d0`
- `0x96f0`
- `0x9700`
- `0xaab0`
- `0x17910`
- `0x18690`
- `0x18840`
- `0x19a20`

## pseudocode

```c

```

## disassembly

```asm
0x17910  ldarg.2
0x17911  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Count()
0x17916  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::.ctor(int32)
0x1791b  stloc.0
0x1791c  ldarg.0
0x1791d  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x17922  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x17927  ldarg.1
0x17928  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x1792d  stloc.1
0x1792e  ldloc.1
0x1792f  callvirt instance string[] Microsoft.Crm.Asynchronous.ImportFileHelperData::get_AdditionalHeaderColumns()
0x17934  ldlen
0x17935  conv.i4
0x17936  stloc.2
0x17937  ldarg.2
0x17938  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::GetEnumerator()
0x1793d  stloc.3
0x1793e  br       loc_17E8D
0x17943  ldloca.s 3
0x17945  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Current()
0x1794a  stloc.s  4
0x1794c  ldloc.s  4
0x1794e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_ImportDataId()
0x17953  ldloc.s  4
0x17955  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_RecordId()
0x1795a  ldloc.2
0x1795b  newarr   Microsoft.Crm.Asynchronous.ParsedDataObject
0x17960  ldloc.s  4
0x17962  callvirt instance bool Microsoft.Crm.Asynchronous.ParsedDataRow::get_IsExistingRecord()
0x17967  newobj   instance void Microsoft.Crm.Asynchronous.ParsedDataRow::.ctor(valuetype [mscorlib]System.Guid importDataId, valuetype [mscorlib]System.Guid recordId, class Microsoft.Crm.Asynchronous.ParsedDataObject[] parsedDataObjects, bool isExistingRecord)
0x1796c  stloc.s  5
0x1796e  ldloc.0
0x1796f  ldloc.s  5
0x17971  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::Add(var<u1>)
0x17976  ldc.i4.0
0x17977  stloc.s  6
0x17979  ldloc.1
0x1797a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TransformationMappingIdToTransformationMappingHelperDataDictionary()
0x1797f  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::GetEnumerator()
0x17984  stloc.s  7
0x17986  br       loc_17E66
0x1798b  ldloca.s 7
0x1798d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::get_Current()
0x17992  stloc.s  8
0x17994  ldloca.s 8
0x17996  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::get_Value()
0x1799b  stloc.s  9
0x1799d  ldloc.s  9
0x1799f  callvirt instance valuetype Microsoft.Crm.Asynchronous.TransformationApplicability Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_Applicability()
0x179a4  ldc.i4.1
0x179a5  bne.un.s loc_179E6
0x179a7  ldarg.0
0x179a8  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x179ad  ldarg.0
0x179ae  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x179b3  ldarg.0
0x179b4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x179b9  ldarg.1
0x179ba  ldloc.s  4
0x179bc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_ImportDataId()
0x179c1  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x179c6  ldc.i4.1
0x179c7  ldnull
0x179c8  ldnull
0x179c9  ldloc.s  9
0x179cb  callvirt instance int32 Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_ErrorCode()
0x179d0  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x179d5  ldloc.s  9
0x179d7  callvirt instance string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_ErrorDescription()
0x179dc  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x179e1  br       loc_17E66
0x179e6  ldloc.s  9
0x179e8  callvirt instance valuetype Microsoft.Crm.Asynchronous.TransformationApplicability Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_Applicability()
0x179ed  ldc.i4.2
0x179ee  bne.un.s loc_17A2A
0x179f0  ldarg.0
0x179f1  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x179f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x179fb  ldc.i4.s 0x18
0x179fd  ldstr    aNoneOfTheHeade// "None of the header columns for the impo"...
0x17a02  ldc.i4.2
0x17a03  newarr   [mscorlib]System.Object
0x17a08  dup
0x17a09  ldc.i4.0
0x17a0a  ldarg.1
0x17a0b  box      [mscorlib]System.Guid
0x17a10  stelem.ref
0x17a11  dup
0x17a12  ldc.i4.1
0x17a13  ldloc.s  9
0x17a15  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_TransformationMappingId()
0x17a1a  box      [mscorlib]System.Guid
0x17a1f  stelem.ref
0x17a20  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17a25  br       loc_17E66
0x17a2a  ldarg.0
0x17a2b  ldarg.1
0x17a2c  ldloc.s  9
0x17a2e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_TransformationMappingId()
0x17a33  ldloc.s  4
0x17a35  ldarg.3
0x17a36  call     instance object[] Microsoft.Crm.Asynchronous.ImportOperationTransform::GetInputParameterBag(valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid transformationMappingId, class Microsoft.Crm.Asynchronous.ParsedDataRow inputRow, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> columnNameToArrayIndex)
0x17a3b  stloc.s  0xA
0x17a3d  ldloc.s  0xA
0x17a3f  brtrue.s loc_17A57
0x17a41  ldloc.s  6
0x17a43  ldloc.s  9
0x17a45  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_OutputColumns()
0x17a4a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x17a4f  add
0x17a50  stloc.s  6
0x17a52  br       loc_17E66
0x17a57  ldloc.s  9
0x17a59  callvirt instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ITransformation Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_TransformationType()
0x17a5e  stloc.s  0xB
0x17a60  ldnull
0x17a61  stloc.s  0xC
0x17a63  ldloc.s  0xB
0x17a65  ldloc.s  0xA
0x17a67  callvirt instance object[] [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.ITransformation::Evaluate(object[])
0x17a6c  stloc.s  0xC
0x17a6e  leave    loc_17E41
0x17a73  stloc.s  0xD
0x17a75  ldloc.s  9
0x17a77  callvirt instance string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_InputParametersToString()
0x17a7c  ldstr    aInputParameter_0// "Input Parameter Values: "
0x17a81  ldarg.0
0x17a82  ldloc.s  0xA
0x17a84  call     instance string Microsoft.Crm.Asynchronous.ImportOperationTransform::ParameterBagToString(object[] inputBag)
0x17a89  ldstr    asc_28120// "\n"
0x17a8e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x17a93  stloc.s  0xE
0x17a95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17a9a  ldsfld   string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::AdditionalInfoFormatString
0x17a9f  ldc.i4.5
0x17aa0  newarr   [mscorlib]System.Object
0x17aa5  dup
0x17aa6  ldc.i4.0
0x17aa7  ldc.i4   0x80040389
0x17aac  box      [mscorlib]System.Int32
0x17ab1  stelem.ref
0x17ab2  dup
0x17ab3  ldc.i4.1
0x17ab4  ldloc.s  9
0x17ab6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_TransformationMapping()
0x17abb  ldstr    aTransformation_1// "transformationtypename"
0x17ac0  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x17ac5  stelem.ref
0x17ac6  dup
0x17ac7  ldc.i4.2
0x17ac8  ldloc.s  0xE
0x17aca  stelem.ref
0x17acb  dup
0x17acc  ldc.i4.3
0x17acd  ldloc.s  9
0x17acf  callvirt instance string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_OutputParametersToString()
0x17ad4  stelem.ref
0x17ad5  dup
0x17ad6  ldc.i4.4
0x17ad7  ldloc.s  0xD
0x17ad9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x17ade  stelem.ref
0x17adf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17ae4  stloc.s  0xF
0x17ae6  ldloc.s  0xD
0x17ae8  ldarg.0
0x17ae9  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x17aee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x17af3  ldc.i4.s 0x18
0x17af5  ldloc.s  0xF
0x17af7  ldc.i4.0
0x17af8  newarr   [mscorlib]System.Object
0x17afd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17b02  ldarg.0
0x17b03  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x17b08  ldarg.0
0x17b09  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x17b0e  ldarg.0
0x17b0f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x17b14  ldarg.1
0x17b15  ldloc.s  4
0x17b17  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_ImportDataId()
0x17b1c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x17b21  ldc.i4.1
0x17b22  ldnull
0x17b23  ldnull
0x17b24  ldc.i4   0x80040389
0x17b29  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x17b2e  ldloc.s  0xF
0x17b30  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x17b35  ldloc.s  6
0x17b37  ldloc.s  9
0x17b39  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_OutputColumns()
0x17b3e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x17b43  add
0x17b44  stloc.s  6
0x17b46  leave    loc_17E66
0x17b4b  stloc.s  0x10
0x17b4d  ldloc.s  0x10
0x17b4f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17b54  ldc.i4   0x80048506
0x17b59  beq.s    loc_17BC0
0x17b5b  ldloc.s  0x10
0x17b5d  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17b62  ldc.i4   0x80048507
0x17b67  beq.s    loc_17BC0
0x17b69  ldloc.s  0x10
0x17b6b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17b70  ldc.i4   0x80048508
0x17b75  beq.s    loc_17BC0
0x17b77  ldloc.s  0x10
0x17b79  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17b7e  ldc.i4   0x80048509
0x17b83  beq.s    loc_17BC0
0x17b85  ldloc.s  0x10
0x17b87  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17b8c  ldc.i4   0x80048510
0x17b91  beq.s    loc_17BC0
0x17b93  ldloc.s  0x10
0x17b95  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17b9a  ldc.i4   0x80048511
0x17b9f  beq.s    loc_17BC0
0x17ba1  ldloc.s  0x10
0x17ba3  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17ba8  ldc.i4   0x80048512
0x17bad  beq.s    loc_17BC0
0x17baf  ldloc.s  0x10
0x17bb1  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x17bb6  ldc.i4   0x80048513
0x17bbb  bne.un   loc_17C96
0x17bc0  ldloc.s  9
0x17bc2  callvirt instance string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_InputParametersToString()
0x17bc7  ldstr    aInputParameter_0// "Input Parameter Values: "
0x17bcc  ldarg.0
0x17bcd  ldloc.s  0xA
0x17bcf  call     instance string Microsoft.Crm.Asynchronous.ImportOperationTransform::ParameterBagToString(object[] inputBag)
0x17bd4  ldstr    asc_28120// "\n"
0x17bd9  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x17bde  stloc.s  0x11
0x17be0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17be5  ldsfld   string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::AdditionalInfoFormatString
0x17bea  ldc.i4.5
0x17beb  newarr   [mscorlib]System.Object
0x17bf0  dup
0x17bf1  ldc.i4.0
0x17bf2  ldc.i4   0x80040389
0x17bf7  box      [mscorlib]System.Int32
0x17bfc  stelem.ref
0x17bfd  dup
0x17bfe  ldc.i4.1
0x17bff  ldloc.s  9
0x17c01  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_TransformationMapping()
0x17c06  ldstr    aTransformation_1// "transformationtypename"
0x17c0b  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x17c10  stelem.ref
0x17c11  dup
0x17c12  ldc.i4.2
0x17c13  ldloc.s  0x11
0x17c15  stelem.ref
0x17c16  dup
0x17c17  ldc.i4.3
0x17c18  ldloc.s  9
0x17c1a  callvirt instance string Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_OutputParametersToString()
0x17c1f  stelem.ref
0x17c20  dup
0x17c21  ldc.i4.4
0x17c22  ldloc.s  0x10
0x17c24  callvirt instance string [mscorlib]System.Exception::get_Message()
0x17c29  stelem.ref
0x17c2a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17c2f  stloc.s  0x12
0x17c31  ldloc.s  0x10
0x17c33  ldarg.0
0x17c34  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x17c39  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x17c3e  ldc.i4.s 0x18
0x17c40  ldloc.s  0x12
0x17c42  ldc.i4.0
0x17c43  newarr   [mscorlib]System.Object
0x17c48  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17c4d  ldarg.0
0x17c4e  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x17c53  ldarg.0
0x17c54  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x17c59  ldarg.0
0x17c5a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x17c5f  ldarg.1
0x17c60  ldloc.s  4
0x17c62  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ParsedDataRow::get_ImportDataId()
0x17c67  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x17c6c  ldc.i4.1
0x17c6d  ldnull
0x17c6e  ldnull
0x17c6f  ldc.i4   0x80040389
0x17c74  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x17c79  ldloc.s  0x12
0x17c7b  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x17c80  ldloc.s  6
0x17c82  ldloc.s  9
  ... truncated ...
```
