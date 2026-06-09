# ServerRoleStateHelper::WindowsAsyncServiceEnable

- ea: `0x1a0e0`
- end: `0x1a125`
- name: `ServerRoleStateHelper::WindowsAsyncServiceEnable`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1a0e0`
- `0x1a180`
- `0x1a3d0`

## string_xrefs

- `0x1a0e4`: `MSCRMAsyncService`
- `0x1a107`: `MSCRMAsyncService`
- `0x1a0f3`: `MSCRMAsyncService$maintenance`
- `0x1a116`: `MSCRMAsyncService$maintenance`

## pseudocode

```c

```

## disassembly

```asm
0x1a0e0  ldc.i4.1
0x1a0e1  stloc.0
0x1a0e2  ldloc.0
0x1a0e3  ldarg.0
0x1a0e4  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x1a0e9  ldc.i4.2
0x1a0ea  call     bool ServerRoleStateHelper::SetServiceStartMode(string serverName, string serviceName, valuetype [System.ServiceProcess]System.ServiceProcess.ServiceStartMode mode)
0x1a0ef  and
0x1a0f0  stloc.0
0x1a0f1  ldloc.0
0x1a0f2  ldarg.0
0x1a0f3  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService$maintenance"
0x1a0f8  ldc.i4.2
0x1a0f9  call     bool ServerRoleStateHelper::SetServiceStartMode(string serverName, string serviceName, valuetype [System.ServiceProcess]System.ServiceProcess.ServiceStartMode mode)
0x1a0fe  and
0x1a0ff  stloc.0
0x1a100  ldloc.0
0x1a101  brtrue.s loc_1A105
0x1a103  ldc.i4.0
0x1a104  ret
0x1a105  ldloc.0
0x1a106  ldarg.0
0x1a107  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x1a10c  ldc.i4.1
0x1a10d  call     bool ServerRoleStateHelper::WindowsServiceSetStatus(string serverName, string serviceName, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState newState)
0x1a112  and
0x1a113  stloc.0
0x1a114  ldloc.0
0x1a115  ldarg.0
0x1a116  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService$maintenance"
0x1a11b  ldc.i4.1
0x1a11c  call     bool ServerRoleStateHelper::WindowsServiceSetStatus(string serverName, string serviceName, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState newState)
0x1a121  and
0x1a122  stloc.0
0x1a123  ldloc.0
0x1a124  ret
```
