# Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::CreateOperationSucceededResult

- ea: `0x1230`
- end: `0x1296`
- name: `Microsoft.Crm.Asynchronous.BackupOrganizationLogOperation::CreateOperationSucceededResult`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb80`

## callees

- `0x1230`

## pseudocode

```c

```

## disassembly

```asm
0x1230  ldarg.1
0x1231  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrenceStartTime()
0x1236  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.MaintenanceWindowHelper::FitJobRecurrenceToMaintenanceWindow(valuetype [mscorlib]System.DateTime)
0x123b  stloc.0
0x123c  ldnull
0x123d  stloc.1
0x123e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1243  ldstr    aDatabasebackup// "DatabaseBackupRecurrence"
0x1248  callvirt T0x2B000001
0x124d  stloc.2
0x124e  ldloc.2
0x124f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1254  brtrue.s loc_1266
0x1256  ldarg.1
0x1257  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrencePattern()
0x125c  ldloc.2
0x125d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1262  brfalse.s loc_1266
0x1264  ldloc.2
0x1265  stloc.1
0x1266  ldloca.s 0
0x1268  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x126d  brtrue.s loc_1272
0x126f  ldloc.1
0x1270  brfalse.s loc_1290
0x1272  ldloc.1
0x1273  dup
0x1274  brtrue.s loc_127D
0x1276  pop
0x1277  ldarg.1
0x1278  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrencePattern()
0x127d  ldloca.s 0
0x127f  ldarg.1
0x1280  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrenceStartTime()
0x1285  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault(!!T0)
0x128a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::.ctor(string, valuetype [mscorlib]System.DateTime)
0x128f  ret
0x1290  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x1295  ret
```
