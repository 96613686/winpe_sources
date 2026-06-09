# __imp_load_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z

- ea: `0x1800042f1`
- end: `0x1800042fd`
- name: `__imp_load_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180004272`

## import_xrefs

- `dmxmlhelputils!XMLHEscapeString` at `0x1800042f1`

## pseudocode

```c
__int64 load__XMLHEscapeString__YAJPEBGPEAPEAGPEAK_Z()
{
  return _tailMerge_dmxmlhelputils_dll();
}

```

## disassembly

```asm
0x1800042f1  lea     rax, __imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x1800042f8  jmp     __tailMerge_dmxmlhelputils_dll
```
