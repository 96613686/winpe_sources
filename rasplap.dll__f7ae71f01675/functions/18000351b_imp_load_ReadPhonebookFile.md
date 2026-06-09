# __imp_load_ReadPhonebookFile

- ea: `0x18000351b`
- end: `0x180003527`
- name: `__imp_load_ReadPhonebookFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003430`

## import_xrefs

- `RASAPI32!ReadPhonebookFile` at `0x18000351b`

## pseudocode

```c
__int64 load_ReadPhonebookFile()
{
  return _tailMerge_rasapi32_dll();
}

```

## disassembly

```asm
0x18000351b  lea     rax, __imp_ReadPhonebookFile
0x180003522  jmp     __tailMerge_rasapi32_dll
```
