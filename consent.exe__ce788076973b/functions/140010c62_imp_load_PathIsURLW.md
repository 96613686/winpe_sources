# __imp_load_PathIsURLW

- ea: `0x140010c62`
- end: `0x140010c6e`
- name: `__imp_load_PathIsURLW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140010bad`

## import_xrefs

- `SHLWAPI!PathIsURLW` at `0x140010c62`

## pseudocode

```c
__int64 load_PathIsURLW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x140010c62  lea     rax, __imp_PathIsURLW
0x140010c69  jmp     __tailMerge_shlwapi_dll
```
