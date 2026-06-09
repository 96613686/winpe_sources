# Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetImportFileType

- ea: `0xfd00`
- end: `0xfd8a`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetImportFileType`
- size: `138`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xea10`
- `0xf190`
- `0x10ec0`
- `0x12e20`
- `0x13030`
- `0x13240`

## callees

- `0x8f60`
- `0xfd00`

## pseudocode

```c

```

## disassembly

```asm
0xfd00  ldnull
0xfd01  stloc.0
0xfd02  ldarg.0
0xfd03  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xfd08  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0xfd0d  ldarg.1
0xfd0e  ldloca.s 0
0xfd10  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::TryGetValue(var<u1>, !!T0)
0xfd15  pop
0xfd16  ldloc.0
0xfd17  ldnull
0xfd18  cgt.un
0xfd1a  ldstr    aImportfileidto// "ImportFileIdToImportFileObjectDictionar"...
0xfd1f  ldc.i4.1
0xfd20  newarr   [mscorlib]System.Object
0xfd25  dup
0xfd26  ldc.i4.0
0xfd27  ldarg.1
0xfd28  box      [mscorlib]System.Guid
0xfd2d  stelem.ref
0xfd2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0xfd33  ldloc.0
0xfd34  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xfd39  ldstr    aFiletypecode// "filetypecode"
0xfd3e  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xfd43  brfalse.s loc_FD5A
0xfd45  ldloc.0
0xfd46  ldstr    aFiletypecode// "filetypecode"
0xfd4b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xfd50  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xfd55  ldnull
0xfd56  cgt.un
0xfd58  br.s     loc_FD5B
0xfd5a  ldc.i4.0
0xfd5b  ldstr    aImportfileReco// "ImportFile record for id=\"{0}\" does n"...
0xfd60  ldc.i4.1
0xfd61  newarr   [mscorlib]System.Object
0xfd66  dup
0xfd67  ldc.i4.0
0xfd68  ldarg.1
0xfd69  box      [mscorlib]System.Guid
0xfd6e  stelem.ref
0xfd6f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0xfd74  ldloc.0
0xfd75  ldstr    aFiletypecode// "filetypecode"
0xfd7a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xfd7f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xfd84  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xfd89  ret
```
