# sub_2F9DBA9

- ea: `0x2f9dba9`
- end: `0x2f9dbbb`
- name: `sub_2F9DBA9`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_2F9DBA9(__int64 a1, __int64 a2, char a3, _BYTE *a4)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rbx

  LOBYTE(v4) = *v4 | (unsigned __int8)v4;
  *a4 += (_BYTE)v4;
  ++*a4;
  *v5 += a3;
  LOBYTE(v4) = *v4 | (unsigned __int8)v4;
  return (char)v4;
}

```

## disassembly

```asm
0x2f9dba9  or      al, [rax]
0x2f9dbab  enter   78h, 0
0x2f9dbaf  add     [rcx], al
0x2f9dbb1  cmp     byte ptr [rcx], 0F7h
0x2f9dbb4  inc     byte ptr [rcx]
0x2f9dbb6  add     [rbx], dl
0x2f9dbb8  or      al, [rax]
0x2f9dbba  retn
```
