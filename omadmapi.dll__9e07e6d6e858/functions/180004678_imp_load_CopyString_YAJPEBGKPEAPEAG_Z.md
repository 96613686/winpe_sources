# __imp_load_?CopyString@@YAJPEBGKPEAPEAG@Z

- ea: `0x180004678`
- end: `0x180004684`
- name: `__imp_load_?CopyString@@YAJPEBGKPEAPEAG@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800045f9`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x180004678`

## pseudocode

```c
__int64 load__CopyString__YAJPEBGKPEAPEAG_Z()
{
  return _tailMerge_dmcmnutils_dll();
}

```

## disassembly

```asm
0x180004678  lea     rax, __imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000467f  jmp     __tailMerge_dmcmnutils_dll
```
