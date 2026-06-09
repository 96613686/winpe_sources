# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.UpdateRollupField::UpdateMainTable

- ea: `0x10040`
- end: `0x10080`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.UpdateRollupField::UpdateMainTable`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10020`

## callees

- `0xbf80`
- `0xf7e0`
- `0xf7f0`
- `0x10040`
- `0x100e0`

## pseudocode

```c

```

## disassembly

```asm
0x10040  ldarg.0
0x10041  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_Process()
0x10046  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x1004b  ldc.i4.0
0x1004c  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::CallUpdateProcedure(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapMainTableUpdateOperation operationType)
0x10051  stloc.0
0x10052  leave.s  loc_1007E
0x10054  stloc.1
0x10055  ldarg.0
0x10056  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_Process()
0x1005b  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x10060  ldloc.1
0x10061  callvirt instance bool Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::IsErrorExpected(class [mscorlib]System.Exception ex)
0x10066  brfalse.s loc_1007C
0x10068  ldarg.0
0x10069  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_Process()
0x1006e  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x10073  ldc.i4.1
0x10074  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::CallUpdateProcedure(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Rollups.BootstrapMainTableUpdateOperation operationType)
0x10079  stloc.0
0x1007a  leave.s  loc_1007E
0x1007c  rethrow
0x1007e  ldloc.0
0x1007f  ret
```
