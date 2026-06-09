# __imp_load_CreateAppContainerEnumerator

- ea: `0x180012039`
- end: `0x180012045`
- name: `__imp_load_CreateAppContainerEnumerator`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011fa8`

## import_xrefs

- `profapi!__imp_CreateAppContainerEnumerator` at `0x180012039`

## pseudocode

```c
__int64 load_CreateAppContainerEnumerator()
{
  return _tailMerge_profapi_dll();
}

```

## disassembly

```asm
0x180012039  lea     rax, __imp_CreateAppContainerEnumerator
0x180012040  jmp     __tailMerge_profapi_dll
```
