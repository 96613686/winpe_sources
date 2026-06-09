# TXTDeleteIndex(x,x,x)

- ea: `0x10013660`
- end: `0x1001367c`
- name: `_TXTDeleteIndex@12`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10014460`

## pseudocode

```c
int __stdcall TXTDeleteIndex(int a1, int a2, int a3)
{
  return ISAMDBFindCursor(a1, a2) != 0 ? -1404 : -1310;
}

```

## disassembly

```asm
0x10013660  push    [esp+arg_4]
0x10013664  push    [esp+4+arg_0]
0x10013668  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1001366d  neg     eax
0x1001366f  sbb     eax, eax
0x10013671  and     eax, 0FFFFFFA2h
0x10013674  add     eax, 0FFFFFAE2h
0x10013679  retn    0Ch
```
