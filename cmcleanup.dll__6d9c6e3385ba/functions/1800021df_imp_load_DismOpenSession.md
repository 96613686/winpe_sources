# __imp_load_DismOpenSession

- ea: `0x1800021df`
- end: `0x1800021eb`
- name: `__imp_load_DismOpenSession`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000212a`

## import_xrefs

- `DismApi!DismOpenSession` at `0x1800021df`

## pseudocode

```c
__int64 load_DismOpenSession()
{
  return _tailMerge_dismapi_dll();
}

```

## disassembly

```asm
0x1800021df  lea     rax, __imp_DismOpenSession
0x1800021e6  jmp     __tailMerge_dismapi_dll
```
