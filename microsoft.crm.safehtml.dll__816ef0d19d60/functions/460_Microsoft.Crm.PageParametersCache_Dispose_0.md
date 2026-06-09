# Microsoft.Crm.PageParametersCache::Dispose_0

- ea: `0x460`
- end: `0x47e`
- name: `Microsoft.Crm.PageParametersCache::Dispose_0`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3c0`
- `0x450`

## callees

- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x460  ldarg.1
0x461  brfalse.s loc_47D
0x463  ldarg.0
0x464  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x469  brfalse.s loc_47D
0x46b  ldarg.0
0x46c  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x471  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::Dispose()
0x476  ldarg.0
0x477  ldnull
0x478  stfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.PageParametersCache::_lock
0x47d  ret
```
