# Microsoft.Crm.Asynchronous.AsyncService::StopKeyManager

- ea: `0x1780`
- end: `0x1794`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StopKeyManager`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16a0`

## callees

- `0x1780`

## pseudocode

```c

```

## disassembly

```asm
0x1780  ldarg.0
0x1781  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x1786  ldc.i4.1
0x1787  bne.un.s loc_1793
0x1789  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyManager [Microsoft.Crm.Core]Microsoft.Crm.CrmScaleGroupKeyManager::get_Instance()
0x178e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyManager::Stop()
0x1793  ret
```
