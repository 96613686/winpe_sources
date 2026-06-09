# __imp_load_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z

- ea: `0x18000483d`
- end: `0x180004849`
- name: `__imp_load_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003601`

## import_xrefs

- `DMCmnUtils!DmGetAadUserToken` at `0x18000483d`

## pseudocode

```c
__int64 load__DmGetAadUserToken__YAJPEBG00PEAPEAGPEAH_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x18000483d  lea     rax, __imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x180004844  jmp     __tailMerge_dmcmnutils_dll
```
