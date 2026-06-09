# TXTCreateIndex(x,x,x,x,x,x,x)

- ea: `0x10013640`
- end: `0x1001365e`
- name: `_TXTCreateIndex@28`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10014460`

## pseudocode

```c
int __stdcall TXTCreateIndex(int a1, int a2, int a3, int a4, int a5, int a6, int a7)
{
  return ISAMDBFindCursor(a1, a2) != 0 ? -1001 : -1310;
}

```

## disassembly

```asm
0x10013640  push    [esp+arg_4]
0x10013644  push    [esp+4+arg_0]
0x10013648  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1001364d  neg     eax
0x1001364f  sbb     eax, eax
0x10013651  and     eax, 135h
0x10013656  add     eax, 0FFFFFAE2h
0x1001365b  retn    1Ch
```
