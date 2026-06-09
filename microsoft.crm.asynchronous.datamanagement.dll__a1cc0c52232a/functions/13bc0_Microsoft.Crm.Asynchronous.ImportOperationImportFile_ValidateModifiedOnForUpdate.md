# Microsoft.Crm.Asynchronous.ImportOperationImportFile::ValidateModifiedOnForUpdate

- ea: `0x13bc0`
- end: `0x13bfe`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::ValidateModifiedOnForUpdate`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf190`

## callees

- `0x13bc0`
- `0x13c00`

## pseudocode

```c

```

## disassembly

```asm
0x13bc0  ldarg.2
0x13bc1  brfalse.s loc_13BFC
0x13bc3  ldarg.2
0x13bc4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x13bc9  ldstr    aModifiedon_0// "modifiedon"
0x13bce  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13bd3  brfalse.s loc_13BFC
0x13bd5  ldarg.2
0x13bd6  ldstr    aModifiedon_0// "modifiedon"
0x13bdb  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x13be0  unbox.any [mscorlib]System.DateTime
0x13be5  stloc.0
0x13be6  ldarg.0
0x13be7  ldarg.1
0x13be8  ldc.i4.1
0x13be9  ldarg.3
0x13bea  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetStandardizedDateTimeValue(string attributeValue, bool isExistingRecord, int32 fileTypeCode)
0x13bef  stloc.1
0x13bf0  ldloca.s 1
0x13bf2  ldloc.0
0x13bf3  call     instance int32 [mscorlib]System.DateTime::CompareTo(valuetype [mscorlib]System.DateTime)
0x13bf8  ldc.i4.0
0x13bf9  ceq
0x13bfb  ret
0x13bfc  ldc.i4.0
0x13bfd  ret
```
