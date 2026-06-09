# __imp_load_PathFindFileNameW

- ea: `0x140010c50`
- end: `0x140010c5c`
- name: `__imp_load_PathFindFileNameW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140010bad`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x140010c50`

## pseudocode

```c
__int64 load_PathFindFileNameW()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x140010c50  lea     rax, __imp_PathFindFileNameW
0x140010c57  jmp     __tailMerge_shlwapi_dll
```
