# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::UpdateBackupHistory

- ea: `0x13f0`
- end: `0x1432`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::UpdateBackupHistory`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb80`

## callees

- `0x13f0`
- `0x1440`

## string_xrefs

- `0x1405`: `Unable to update backup history for organization id: {0} : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x13f0  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.OrganizationBackupHistoryManager [Microsoft.Crm.Core.Extensions]Microsoft.Crm.OrganizationBackupHistoryManager::get_Instance()
0x13f5  ldarg.1
0x13f6  ldarg.2
0x13f7  ldarg.3
0x13f8  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.OrganizationBackupHistoryManager::UpdateBackupHistory(valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmOrganizationBackupData)
0x13fd  leave.s  loc_1431
0x13ff  stloc.0
0x1400  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1405  ldstr    aUnableToUpdate// "Unable to update backup history for org"...
0x140a  ldc.i4.2
0x140b  newarr   [mscorlib]System.Object
0x1410  dup
0x1411  ldc.i4.0
0x1412  ldarg.1
0x1413  box      [mscorlib]System.Guid
0x1418  stelem.ref
0x1419  dup
0x141a  ldc.i4.1
0x141b  ldloc.0
0x141c  callvirt instance string [mscorlib]System.Object::ToString()
0x1421  stelem.ref
0x1422  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1427  stloc.1
0x1428  ldarg.0
0x1429  ldloc.1
0x142a  call     instance void Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::LogError(string message)
0x142f  leave.s  loc_1431
0x1431  ret
```
