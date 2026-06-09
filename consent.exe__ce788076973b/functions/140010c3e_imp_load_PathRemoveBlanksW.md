# __imp_load_PathRemoveBlanksW

- ea: `0x140010c3e`
- end: `0x140010c4a`
- name: `__imp_load_PathRemoveBlanksW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140010bad`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x140010c3e`

## pseudocode

```c
__int64 load_PathRemoveBlanksW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x140010c3e  lea     rax, __imp_PathRemoveBlanksW
0x140010c45  jmp     __tailMerge_shlwapi_dll
```
