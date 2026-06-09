# Microsoft.Crm.Asynchronous.AsyncService::get_IsRunningInSafeMode

- ea: `0x18d0`
- end: `0x18e6`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_IsRunningInSafeMode`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xc70`
- `0x18d0`

## pseudocode

```c

```

## disassembly

```asm
0x18d0  ldarg.0
0x18d1  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::get_Configuration()
0x18d6  brfalse.s loc_18E4
0x18d8  ldarg.0
0x18d9  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::get_Configuration()
0x18de  callvirt instance bool [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IServiceConfiguration::get_IsRunningInSafeMode()
0x18e3  ret
0x18e4  ldc.i4.0
0x18e5  ret
```
