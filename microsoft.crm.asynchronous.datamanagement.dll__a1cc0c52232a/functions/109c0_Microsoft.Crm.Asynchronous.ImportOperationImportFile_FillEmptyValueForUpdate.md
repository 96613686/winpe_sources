# Microsoft.Crm.Asynchronous.ImportOperationImportFile::FillEmptyValueForUpdate

- ea: `0x109c0`
- end: `0x109f4`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::FillEmptyValueForUpdate`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10620`
- `0x115d0`

## callees

- `0x109c0`

## pseudocode

```c

```

## disassembly

```asm
0x109c0  ldarg.1
0x109c1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x109c6  stloc.0
0x109c7  ldarg.1
0x109c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x109cd  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x109d2  stloc.1
0x109d3  ldloc.1
0x109d4  ldc.i4.8
0x109d5  beq.s    loc_109DC
0x109d7  ldloc.1
0x109d8  ldc.i4.s 0x10
0x109da  bne.un.s loc_109EA
0x109dc  ldarg.2
0x109dd  ldind.ref
0x109de  ldloc.0
0x109df  ldsfld   string [mscorlib]System.String::Empty
0x109e4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x109e9  ret
0x109ea  ldarg.2
0x109eb  ldind.ref
0x109ec  ldloc.0
0x109ed  ldnull
0x109ee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x109f3  ret
```
