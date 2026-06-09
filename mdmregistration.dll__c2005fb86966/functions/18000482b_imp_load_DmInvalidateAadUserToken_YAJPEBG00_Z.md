# __imp_load_?DmInvalidateAadUserToken@@YAJPEBG00@Z

- ea: `0x18000482b`
- end: `0x180004837`
- name: `__imp_load_?DmInvalidateAadUserToken@@YAJPEBG00@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmInvalidateAadUserToken` at `0x18000482b`

## pseudocode

```c
__int64 load__DmInvalidateAadUserToken__YAJPEBG00_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x18000482b  lea     rax, __imp_?DmInvalidateAadUserToken@@YAJPEBG00@Z; DmInvalidateAadUserToken(ushort const *,ushort const *,ushort const *)
0x180004832  jmp     __tailMerge_dmcmnutils_dll
```
