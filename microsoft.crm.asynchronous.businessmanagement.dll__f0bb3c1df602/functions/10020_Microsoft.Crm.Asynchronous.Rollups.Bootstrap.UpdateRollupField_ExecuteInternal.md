# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.UpdateRollupField::ExecuteInternal

- ea: `0x10020`
- end: `0x10039`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.UpdateRollupField::ExecuteInternal`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10020`
- `0x10040`
- `0x10100`

## pseudocode

```c

```

## disassembly

```asm
0x10020  ldarg.0
0x10021  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.Bootstrap.UpdateRollupField::UpdateMainTable()
0x10026  ldc.i4.0
0x10027  ble.s    loc_10030
0x10029  ldarg.0
0x1002a  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_StepNumber()
0x1002f  ret
0x10030  ldarg.0
0x10031  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_StepNumber()
0x10036  ldc.i4.1
0x10037  add
0x10038  ret
```
