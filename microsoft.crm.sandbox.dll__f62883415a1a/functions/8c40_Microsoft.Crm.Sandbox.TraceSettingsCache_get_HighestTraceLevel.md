# Microsoft.Crm.Sandbox.TraceSettingsCache::get_HighestTraceLevel

- ea: `0x8c40`
- end: `0x8c4c`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::get_HighestTraceLevel`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x12a0`

## callees

- `0x8c50`

## pseudocode

```c

```

## disassembly

```asm
0x8c40  ldarg.0
0x8c41  ldstr    aSandbox// "Sandbox.*"
0x8c46  call     instance valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevel(string specificCategory)
0x8c4b  ret
```
