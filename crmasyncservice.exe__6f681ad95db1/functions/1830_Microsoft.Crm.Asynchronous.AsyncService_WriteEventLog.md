# Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog

- ea: `0x1830`
- end: `0x1847`
- name: `Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`
- `0x12c0`
- `0x1570`
- `0xa620`

## callees

- `0x1830`

## pseudocode

```c

```

## disassembly

```asm
0x1830  ldarg.0
0x1831  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::_eventLog
0x1836  brfalse.s loc_1846
0x1838  ldarg.0
0x1839  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::_eventLog
0x183e  ldarg.1
0x183f  ldarg.2
0x1840  ldarg.3
0x1841  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x1846  ret
```
