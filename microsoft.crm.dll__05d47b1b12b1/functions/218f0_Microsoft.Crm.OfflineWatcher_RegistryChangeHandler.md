# Microsoft.Crm.OfflineWatcher::RegistryChangeHandler

- ea: `0x218f0`
- end: `0x21987`
- name: `Microsoft.Crm.OfflineWatcher::RegistryChangeHandler`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x21750`
- `0x217a0`
- `0x21860`
- `0x218f0`

## string_xrefs

- `0x218fd`: `Received Registry Change Notification. Current Status = {0} New Status = {1}`
- `0x21970`: `The registry change handler threw an exception: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x218f0  call     int32 Microsoft.Crm.OfflineWatcher::GetRCOfflineValue()
0x218f5  stloc.0
0x218f6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x218fb  ldc.i4.s 0x14
0x218fd  ldstr    aReceivedRegist// "Received Registry Change Notification. "...
0x21902  ldc.i4.2
0x21903  newarr   [mscorlib]System.Object
0x21908  dup
0x21909  ldc.i4.0
0x2190a  ldsfld   int32 Microsoft.Crm.OfflineWatcher::currentRCOfflineValue
0x2190f  box      [mscorlib]System.Int32
0x21914  stelem.ref
0x21915  dup
0x21916  ldc.i4.1
0x21917  ldloc.0
0x21918  box      [mscorlib]System.Int32
0x2191d  stelem.ref
0x2191e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21923  ldsfld   int32 Microsoft.Crm.OfflineWatcher::currentRCOfflineValue
0x21928  ldloc.0
0x21929  bne.un.s loc_2192D
0x2192b  leave.s  loc_21986
0x2192d  ldloc.0
0x2192e  stsfld   int32 Microsoft.Crm.OfflineWatcher::currentRCOfflineValue
0x21933  ldloc.0
0x21934  brtrue.s loc_2194F
0x21936  ldsfld   class Microsoft.Crm.RCWentOnlineEventHandler Microsoft.Crm.OfflineWatcher::RCWentOnline
0x2193b  brfalse.s loc_21966
0x2193d  ldsfld   class Microsoft.Crm.RCWentOnlineEventHandler Microsoft.Crm.OfflineWatcher::RCWentOnline
0x21942  ldarg.0
0x21943  newobj   instance void [mscorlib]System.EventArgs::.ctor()
0x21948  callvirt instance void Microsoft.Crm.RCWentOnlineEventHandler::Invoke(object sender, class [mscorlib]System.EventArgs e)
0x2194d  br.s     loc_21966
0x2194f  ldsfld   class Microsoft.Crm.RCWentOfflineEventHandler Microsoft.Crm.OfflineWatcher::RCWentOffline
0x21954  brfalse.s loc_21966
0x21956  ldsfld   class Microsoft.Crm.RCWentOfflineEventHandler Microsoft.Crm.OfflineWatcher::RCWentOffline
0x2195b  ldarg.0
0x2195c  newobj   instance void [mscorlib]System.EventArgs::.ctor()
0x21961  callvirt instance void Microsoft.Crm.RCWentOfflineEventHandler::Invoke(object sender, class [mscorlib]System.EventArgs e)
0x21966  leave.s  loc_21986
0x21968  stloc.1
0x21969  ldloc.1
0x2196a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2196f  ldc.i4.6
0x21970  ldstr    aTheRegistryCha// "The registry change handler threw an ex"...
0x21975  ldc.i4.1
0x21976  newarr   [mscorlib]System.Object
0x2197b  dup
0x2197c  ldc.i4.0
0x2197d  ldloc.1
0x2197e  stelem.ref
0x2197f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21984  leave.s  loc_21986
0x21986  ret
```
