# TransactionLogDataAndDriveUsageComparer::Compare

- ea: `0xf840`
- end: `0xf8b2`
- name: `TransactionLogDataAndDriveUsageComparer::Compare`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x9db0`
- `0xa460`
- `0xa4e0`
- `0xa500`
- `0xf840`

## pseudocode

```c

```

## disassembly

```asm
0xf840  ldarg.1
0xf841  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf846  callvirt instance int64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_FreeDriveBytes()
0xf84b  ldarg.2
0xf84c  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf851  callvirt instance int64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_FreeDriveBytes()
0xf856  ble.s    loc_F85A
0xf858  ldc.i4.m1
0xf859  ret
0xf85a  ldarg.1
0xf85b  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf860  callvirt instance int64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_FreeDriveBytes()
0xf865  ldarg.2
0xf866  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf86b  callvirt instance int64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_FreeDriveBytes()
0xf870  bge.s    loc_F874
0xf872  ldc.i4.1
0xf873  ret
0xf874  ldarg.1
0xf875  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf87a  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_FileSizeInMB()
0xf87f  ldarg.1
0xf880  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf885  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_CurrentSizeInMB()
0xf88a  sub
0xf88b  stloc.0
0xf88c  ldarg.2
0xf88d  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf892  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_FileSizeInMB()
0xf897  ldarg.2
0xf898  callvirt instance class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction::get_TransactionLogDescription()
0xf89d  callvirt instance float64 Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsage::get_CurrentSizeInMB()
0xf8a2  sub
0xf8a3  stloc.1
0xf8a4  ldloc.0
0xf8a5  ldloc.1
0xf8a6  ble.un.s loc_F8AA
0xf8a8  ldc.i4.m1
0xf8a9  ret
0xf8aa  ldloc.0
0xf8ab  ldloc.1
0xf8ac  bge.un.s loc_F8B0
0xf8ae  ldc.i4.1
0xf8af  ret
0xf8b0  ldc.i4.0
0xf8b1  ret
```
