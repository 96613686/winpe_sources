# WBTCreateIndex(x,x,x,x,x,x,x)

- ea: `0x1002a3f0`
- end: `0x1002a412`
- name: `_WBTCreateIndex@28`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1002acaf`

## pseudocode

```c
int __stdcall WBTCreateIndex(int a1, int a2, int a3, int a4, int a5, int a6, int a7)
{
  return ISAMDBFindCursor(a1, a2) != 0 ? -1001 : -1310;
}

```

## disassembly

```asm
0x1002a3f0  mov     edi, edi
0x1002a3f2  push    ebp
0x1002a3f3  mov     ebp, esp
0x1002a3f5  mov     edx, [ebp+arg_4]
0x1002a3f8  mov     ecx, [ebp+arg_0]
0x1002a3fb  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1002a400  neg     eax
0x1002a402  sbb     eax, eax
0x1002a404  and     eax, 135h
0x1002a409  add     eax, 0FFFFFAE2h
0x1002a40e  pop     ebp
0x1002a40f  retn    1Ch
```
