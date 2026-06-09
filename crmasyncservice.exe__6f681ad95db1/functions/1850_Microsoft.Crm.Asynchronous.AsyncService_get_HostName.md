# Microsoft.Crm.Asynchronous.AsyncService::get_HostName

- ea: `0x1850`
- end: `0x1856`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_HostName`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`
- `0x12c0`
- `0x1570`
- `0xa620`

## pseudocode

```c

```

## disassembly

```asm
0x1850  call     string [mscorlib]System.Environment::get_MachineName()
0x1855  ret
```
