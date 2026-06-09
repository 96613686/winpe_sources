# Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::OnExecuteComplete

- ea: `0xb90`
- end: `0xbac`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::OnExecuteComplete`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x80`
- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0xb90  ldarg.0
0xb91  castclass Microsoft.Crm.Sandbox.InternalSandboxSdkClient
0xb96  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_Server()
0xb9b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0xba0  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xba5  call     bool Microsoft.Crm.Sandbox.InternalSandboxSdkClientManager::TryUpdateServerOutageHistory(string serverName, valuetype [mscorlib]System.DateTime outageTime)
0xbaa  pop
0xbab  ret
```
