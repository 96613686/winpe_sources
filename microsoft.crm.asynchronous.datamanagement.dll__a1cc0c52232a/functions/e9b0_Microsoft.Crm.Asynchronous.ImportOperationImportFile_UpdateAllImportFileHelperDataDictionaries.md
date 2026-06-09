# Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateAllImportFileHelperDataDictionaries

- ea: `0xe9b0`
- end: `0xea10`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateAllImportFileHelperDataDictionaries`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xfd90`
- `0x12170`

## callees

- `0x8f60`
- `0x8f70`
- `0x9150`
- `0xe9b0`

## pseudocode

```c

```

## disassembly

```asm
0xe9b0  ldarg.0
0xe9b1  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xe9b6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xe9bb  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0xe9c0  stloc.0
0xe9c1  br.s     loc_E9F6
0xe9c3  ldloca.s 0
0xe9c5  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0xe9ca  stloc.1
0xe9cb  ldarg.0
0xe9cc  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xe9d1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0xe9d6  ldloca.s 1
0xe9d8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0xe9dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0xe9e2  brtrue.s loc_E9F6
0xe9e4  ldarg.0
0xe9e5  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xe9ea  ldloca.s 1
0xe9ec  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0xe9f1  callvirt instance void Microsoft.Crm.Asynchronous.ImportHelperData::UpdateImportFileHelperDataDictionary(valuetype [mscorlib]System.Guid importFileId)
0xe9f6  ldloca.s 0
0xe9f8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::MoveNext()
0xe9fd  brtrue.s loc_E9C3
0xe9ff  leave.s  loc_EA0F
0xea01  ldloca.s 0
0xea03  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0xea09  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xea0e  endfinally
0xea0f  ret
```
