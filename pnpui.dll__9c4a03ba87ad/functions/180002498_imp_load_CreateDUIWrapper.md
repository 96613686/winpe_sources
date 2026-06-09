# __imp_load_CreateDUIWrapper

- ea: `0x180002498`
- end: `0x1800024a4`
- name: `__imp_load_CreateDUIWrapper`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023b4`

## import_xrefs

- `DUI70!CreateDUIWrapper` at `0x180002498`

## pseudocode

```c
__int64 load_CreateDUIWrapper()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180002498  lea     rax, __imp_CreateDUIWrapper
0x18000249f  jmp     __tailMerge_dui70_dll
```
