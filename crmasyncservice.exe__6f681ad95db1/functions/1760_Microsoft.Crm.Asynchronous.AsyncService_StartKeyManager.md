# Microsoft.Crm.Asynchronous.AsyncService::StartKeyManager

- ea: `0x1760`
- end: `0x1774`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StartKeyManager`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1650`

## callees

- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0x1760  ldarg.0
0x1761  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0x1766  ldc.i4.1
0x1767  bne.un.s loc_1773
0x1769  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyManager [Microsoft.Crm.Core]Microsoft.Crm.CrmScaleGroupKeyManager::get_Instance()
0x176e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyManager::Start()
0x1773  ret
```
