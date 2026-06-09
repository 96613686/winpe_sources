# __imp_load_JetCreateDatabase2W

- ea: `0x180002bf2`
- end: `0x180002bfe`
- name: `__imp_load_JetCreateDatabase2W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002abf`

## import_xrefs

- `ESENT!JetCreateDatabase2W` at `0x180002bf2`

## pseudocode

```c
__int64 load_JetCreateDatabase2W()
{
  return _tailMerge_esent_dll();
}

```

## disassembly

```asm
0x180002bf2  lea     rax, __imp_JetCreateDatabase2W
0x180002bf9  jmp     __tailMerge_esent_dll
```
