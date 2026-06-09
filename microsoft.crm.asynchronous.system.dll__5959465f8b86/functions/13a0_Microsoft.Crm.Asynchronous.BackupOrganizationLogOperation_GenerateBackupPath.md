# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::GenerateBackupPath

- ea: `0x13a0`
- end: `0x13ee`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::GenerateBackupPath`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xb80`

## callees

- `0x13a0`
- `0x1440`
- `0x1450`

## string_xrefs

- `0x13b0`: `Error creating backup path for organization id: {0}  : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x13a0  ldarg.1
0x13a1  ldc.i4.1
0x13a2  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility::GenerateBackupPath(valuetype [mscorlib]System.Guid, bool)
0x13a7  stloc.0
0x13a8  leave.s  loc_13EC
0x13aa  stloc.1
0x13ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13b0  ldstr    aErrorCreatingB_2// "Error creating backup path for organiza"...
0x13b5  ldc.i4.2
0x13b6  newarr   [mscorlib]System.Object
0x13bb  dup
0x13bc  ldc.i4.0
0x13bd  ldarg.1
0x13be  box      [mscorlib]System.Guid
0x13c3  stelem.ref
0x13c4  dup
0x13c5  ldc.i4.1
0x13c6  ldloc.1
0x13c7  callvirt instance string [mscorlib]System.Object::ToString()
0x13cc  stelem.ref
0x13cd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13d2  stloc.2
0x13d3  ldarg.0
0x13d4  ldloc.2
0x13d5  ldarg.1
0x13d6  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::LogError(string message, valuetype [mscorlib]System.Guid orgId)
0x13db  rethrow
0x13dd  stloc.3
0x13de  ldarg.0
0x13df  ldloc.3
0x13e0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x13e5  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::LogError(string message)
0x13ea  rethrow
0x13ec  ldloc.0
0x13ed  ret
```
