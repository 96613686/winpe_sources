# Microsoft.Crm.Asynchronous.ImportOperationTransform::DeriveAdditionalHeaderRowAndCreateColumns

- ea: `0x17670`
- end: `0x17749`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::DeriveAdditionalHeaderRowAndCreateColumns`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x16690`

## callees

- `0x3b80`
- `0x5ed0`
- `0x60a0`
- `0x6520`
- `0x65d0`
- `0x8f70`
- `0x9640`
- `0x9660`
- `0x17670`
- `0x18490`

## pseudocode

```c

```

## disassembly

```asm
0x17670  ldarg.0
0x17671  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x17676  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x1767b  ldarg.1
0x1767c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x17681  stloc.0
0x17682  ldloc.0
0x17683  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x17688  ldstr    aAdditionalhead// "additionalheaderrow"
0x1768d  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x17692  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17697  brtrue.s loc_176A0
0x17699  ldloc.0
0x1769a  callvirt instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAdditionalHeaderData()
0x1769f  ret
0x176a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x176a5  stloc.1
0x176a6  ldloc.0
0x176a7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TransformationMappingIdToTransformationMappingHelperDataDictionary()
0x176ac  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::GetEnumerator()
0x176b1  stloc.2
0x176b2  br.s     loc_17712
0x176b4  ldloca.s 2
0x176b6  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::get_Current()
0x176bb  stloc.3
0x176bc  ldloca.s 3
0x176be  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::get_Value()
0x176c3  stloc.s  4
0x176c5  ldloc.s  4
0x176c7  callvirt instance valuetype Microsoft.Crm.Asynchronous.TransformationApplicability Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_Applicability()
0x176cc  brtrue.s loc_17712
0x176ce  ldloc.s  4
0x176d0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.TransformationMappingHelperData::get_OutputColumns()
0x176d5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x176da  stloc.s  5
0x176dc  br.s     loc_176F9
0x176de  ldloca.s 5
0x176e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x176e5  stloc.s  6
0x176e7  ldloc.1
0x176e8  ldloc.s  6
0x176ea  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x176ef  brtrue.s loc_176F9
0x176f1  ldloc.1
0x176f2  ldloc.s  6
0x176f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x176f9  ldloca.s 5
0x176fb  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x17700  brtrue.s loc_176DE
0x17702  leave.s  loc_17712
0x17704  ldloca.s 5
0x17706  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x1770c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17711  endfinally
0x17712  ldloca.s 2
0x17714  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>::MoveNext()
0x17719  brtrue.s loc_176B4
0x1771b  leave.s  loc_1772B
0x1771d  ldloca.s 2
0x1771f  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.TransformationMappingHelperData>
0x17725  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1772a  endfinally
0x1772b  ldloc.1
0x1772c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x17731  ldc.i4.0
0x17732  ble.s    loc_1773C
0x17734  ldarg.0
0x17735  ldloc.0
0x17736  ldloc.1
0x17737  call     instance void Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAdditionalHeaderRowInImportFileAndCreateColumnsInParsedTable(class Microsoft.Crm.Asynchronous.ImportFileHelperData importFileHelperData, class [mscorlib]System.Collections.Generic.List`1<string> additionalHeaderColumns)
0x1773c  ldloc.0
0x1773d  ldloc.1
0x1773e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x17743  callvirt instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAdditionalHeaderData(string[] additionalHeaderColumns)
0x17748  ret
```
