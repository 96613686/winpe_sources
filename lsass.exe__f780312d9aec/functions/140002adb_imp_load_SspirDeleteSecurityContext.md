# __imp_load_SspirDeleteSecurityContext

- ea: `0x140002adb`
- end: `0x140002ae7`
- name: `__imp_load_SspirDeleteSecurityContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002a26`

## import_xrefs

- `SspiSrv!SspirDeleteSecurityContext` at `0x140002adb`

## pseudocode

```c
__int64 load_SspirDeleteSecurityContext()
{
  return _tailMerge_sspisrv_dll();
}

```

## disassembly

```asm
0x140002adb  lea     rax, __imp_SspirDeleteSecurityContext
0x140002ae2  jmp     __tailMerge_sspisrv_dll
```
