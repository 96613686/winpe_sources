# __imp_load_DeleteAppContainerEnumerator

- ea: `0x18001204b`
- end: `0x180012057`
- name: `__imp_load_DeleteAppContainerEnumerator`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_DeleteAppContainerEnumerator` at `0x18001204b`

## pseudocode

```c
__int64 load_DeleteAppContainerEnumerator()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x18001204b  lea     rax, __imp_DeleteAppContainerEnumerator
0x180012052  jmp     __tailMerge_profapi_dll
```
