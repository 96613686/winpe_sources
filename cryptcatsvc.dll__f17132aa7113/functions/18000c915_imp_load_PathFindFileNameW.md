# __imp_load_PathFindFileNameW

- ea: `0x18000c915`
- end: `0x18000c921`
- name: `__imp_load_PathFindFileNameW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c896`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000c915`

## pseudocode

```c
__int64 load_PathFindFileNameW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x18000c915  lea     rax, __imp_PathFindFileNameW
0x18000c91c  jmp     __tailMerge_shlwapi_dll
```
