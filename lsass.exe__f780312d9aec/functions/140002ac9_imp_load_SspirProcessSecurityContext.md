# __imp_load_SspirProcessSecurityContext

- ea: `0x140002ac9`
- end: `0x140002ad5`
- name: `__imp_load_SspirProcessSecurityContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002a26`

## import_xrefs

- `SspiSrv!SspirProcessSecurityContext` at `0x140002ac9`

## pseudocode

```c
__int64 load_SspirProcessSecurityContext()
{
  return _tailMerge_sspisrv_dll();
}

```

## disassembly

```asm
0x140002ac9  lea     rax, __imp_SspirProcessSecurityContext
0x140002ad0  jmp     __tailMerge_sspisrv_dll
```
