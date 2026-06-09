# Microsoft.Crm.PageParametersCache::Finalize

- ea: `0x3c0`
- end: `0x3d1`
- name: `Microsoft.Crm.PageParametersCache::Finalize`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x3c0`
- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x3c0  ldarg.0
0x3c1  ldc.i4.0
0x3c2  call     instance void Microsoft.Crm.PageParametersCache::Dispose(bool disposing)
0x3c7  leave.s  loc_3D0
0x3c9  ldarg.0
0x3ca  call     instance void [mscorlib]System.Object::Finalize()
0x3cf  endfinally
0x3d0  ret
```
