# Microsoft.Crm.PageParametersCache::Dispose

- ea: `0x450`
- end: `0x45e`
- name: `Microsoft.Crm.PageParametersCache::Dispose`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xff0`

## callees

- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x450  ldarg.0
0x451  ldc.i4.1
0x452  call     instance void Microsoft.Crm.PageParametersCache::Dispose(bool disposing)
0x457  ldarg.0
0x458  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x45d  ret
```
