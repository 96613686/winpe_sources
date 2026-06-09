# ServerRoleStateHelper::WindowsAsyncServiceDisable

- ea: `0x1a130`
- end: `0x1a175`
- name: `ServerRoleStateHelper::WindowsAsyncServiceDisable`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1a130`
- `0x1a180`
- `0x1a3d0`

## string_xrefs

- `0x1a134`: `MSCRMAsyncService`
- `0x1a157`: `MSCRMAsyncService`
- `0x1a143`: `MSCRMAsyncService$maintenance`
- `0x1a166`: `MSCRMAsyncService$maintenance`

## pseudocode

```c

```

## disassembly

```asm
0x1a130  ldc.i4.1
0x1a131  stloc.0
0x1a132  ldloc.0
0x1a133  ldarg.0
0x1a134  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x1a139  ldc.i4.4
0x1a13a  call     bool ServerRoleStateHelper::SetServiceStartMode(string serverName, string serviceName, valuetype [System.ServiceProcess]System.ServiceProcess.ServiceStartMode mode)
0x1a13f  and
0x1a140  stloc.0
0x1a141  ldloc.0
0x1a142  ldarg.0
0x1a143  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService$maintenance"
0x1a148  ldc.i4.4
0x1a149  call     bool ServerRoleStateHelper::SetServiceStartMode(string serverName, string serviceName, valuetype [System.ServiceProcess]System.ServiceProcess.ServiceStartMode mode)
0x1a14e  and
0x1a14f  stloc.0
0x1a150  ldloc.0
0x1a151  brtrue.s loc_1A155
0x1a153  ldc.i4.0
0x1a154  ret
0x1a155  ldloc.0
0x1a156  ldarg.0
0x1a157  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x1a15c  ldc.i4.0
0x1a15d  call     bool ServerRoleStateHelper::WindowsServiceSetStatus(string serverName, string serviceName, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState newState)
0x1a162  and
0x1a163  stloc.0
0x1a164  ldloc.0
0x1a165  ldarg.0
0x1a166  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService$maintenance"
0x1a16b  ldc.i4.0
0x1a16c  call     bool ServerRoleStateHelper::WindowsServiceSetStatus(string serverName, string serviceName, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState newState)
0x1a171  and
0x1a172  stloc.0
0x1a173  ldloc.0
0x1a174  ret
```
