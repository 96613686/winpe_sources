# Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateOwnerColumnForOtherParseTables

- ea: `0xfd90`
- end: `0xfe69`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateOwnerColumnForOtherParseTables`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf190`

## callees

- `0x3b80`
- `0x3c70`
- `0x5ed0`
- `0x6020`
- `0x60b0`
- `0x8f70`
- `0xe9b0`
- `0xfd90`

## string_xrefs

- `0xfe01`: `UPDATE {0} SET {1}='{2},{3}' WHERE {1}='{2},{4}'`

## pseudocode

```c

```

## disassembly

```asm
0xfd90  ldarg.0
0xfd91  call     instance void Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateAllImportFileHelperDataDictionaries()
0xfd96  ldarg.0
0xfd97  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xfd9c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0xfda1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::GetEnumerator()
0xfda6  stloc.0
0xfda7  br       loc_FE4C
0xfdac  ldloca.s 0
0xfdae  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Current()
0xfdb3  stloc.1
0xfdb4  ldloca.s 1
0xfdb6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Key()
0xfdbb  pop
0xfdbc  ldloca.s 1
0xfdbe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Value()
0xfdc3  stloc.2
0xfdc4  ldloc.2
0xfdc5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_OwnerColumnMapping()
0xfdca  stloc.3
0xfdcb  ldloc.3
0xfdcc  brfalse.s loc_FE4C
0xfdce  ldloc.3
0xfdcf  ldstr    aSourceattribut// "sourceattributename"
0xfdd4  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0xfdd9  stloc.s  4
0xfddb  ldloc.2
0xfddc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumnToParsedTableColumnDictionary()
0xfde1  ldloc.s  4
0xfde3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0xfde8  stloc.s  5
0xfdea  ldloc.2
0xfdeb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0xfdf0  ldstr    aParsedtablenam_0// "parsedtablename"
0xfdf5  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0xfdfa  stloc.s  6
0xfdfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfe01  ldstr    aUpdate0Set123W// "UPDATE {0} SET {1}='{2},{3}' WHERE {1}="...
0xfe06  ldc.i4.5
0xfe07  newarr   [mscorlib]System.Object
0xfe0c  dup
0xfe0d  ldc.i4.0
0xfe0e  ldloc.s  6
0xfe10  stelem.ref
0xfe11  dup
0xfe12  ldc.i4.1
0xfe13  ldloc.s  5
0xfe15  stelem.ref
0xfe16  dup
0xfe17  ldc.i4.2
0xfe18  ldarg.3
0xfe19  stelem.ref
0xfe1a  dup
0xfe1b  ldc.i4.3
0xfe1c  ldarga.s 2
0xfe1e  ldstr    aD_0// "D"
0xfe23  call     instance string [mscorlib]System.Guid::ToString(string)
0xfe28  stelem.ref
0xfe29  dup
0xfe2a  ldc.i4.4
0xfe2b  ldarga.s 1
0xfe2d  ldstr    aD_0// "D"
0xfe32  call     instance string [mscorlib]System.Guid::ToString(string)
0xfe37  stelem.ref
0xfe38  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfe3d  stloc.s  7
0xfe3f  ldarg.0
0xfe40  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xfe45  ldloc.s  7
0xfe47  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLString(string command)
0xfe4c  ldloca.s 0
0xfe4e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::MoveNext()
0xfe53  brtrue   loc_FDAC
0xfe58  leave.s  loc_FE68
0xfe5a  ldloca.s 0
0xfe5c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>
0xfe62  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfe67  endfinally
0xfe68  ret
```
