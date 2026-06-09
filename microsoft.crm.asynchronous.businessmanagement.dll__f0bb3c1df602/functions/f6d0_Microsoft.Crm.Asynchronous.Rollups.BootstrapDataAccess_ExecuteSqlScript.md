# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript

- ea: `0xf6d0`
- end: `0xf6dd`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript`
- size: `13`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe940`
- `0xf3f0`
- `0xf4b0`
- `0xf5c0`
- `0xf600`

## callees

- `0xf6e0`

## pseudocode

```c

```

## disassembly

```asm
0xf6d0  ldarg.0
0xf6d1  ldarg.1
0xf6d2  callvirt instance string [mscorlib]System.Object::ToString()
0xf6d7  call     instance void Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript(string cleanupScript)
0xf6dc  ret
```
