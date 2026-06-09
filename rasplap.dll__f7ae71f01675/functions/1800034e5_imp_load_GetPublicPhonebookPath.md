# __imp_load_GetPublicPhonebookPath

- ea: `0x1800034e5`
- end: `0x1800034f1`
- name: `__imp_load_GetPublicPhonebookPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003430`

## import_xrefs

- `RASAPI32!GetPublicPhonebookPath` at `0x1800034e5`

## pseudocode

```c
__int64 load_GetPublicPhonebookPath()
{
  return _tailMerge_rasapi32_dll();
}

```

## disassembly

```asm
0x1800034e5  lea     rax, __imp_GetPublicPhonebookPath
0x1800034ec  jmp     __tailMerge_rasapi32_dll
```
