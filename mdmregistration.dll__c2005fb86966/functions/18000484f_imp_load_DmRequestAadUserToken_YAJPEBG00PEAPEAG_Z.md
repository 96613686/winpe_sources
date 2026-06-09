# __imp_load_?DmRequestAadUserToken@@YAJPEBG00PEAPEAG@Z

- ea: `0x18000484f`
- end: `0x18000485b`
- name: `__imp_load_?DmRequestAadUserToken@@YAJPEBG00PEAPEAG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmRequestAadUserToken` at `0x18000484f`

## pseudocode

```c
__int64 load__DmRequestAadUserToken__YAJPEBG00PEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x18000484f  lea     rax, __imp_?DmRequestAadUserToken@@YAJPEBG00PEAPEAG@Z; DmRequestAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *)
0x180004856  jmp     __tailMerge_dmcmnutils_dll
```
