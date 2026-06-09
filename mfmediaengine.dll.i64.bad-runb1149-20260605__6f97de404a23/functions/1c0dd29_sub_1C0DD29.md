# sub_1C0DD29

- ea: `0x1c0dd29`
- end: `0x1c0dd3b`
- name: `sub_1C0DD29`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_1C0DD29(__int64 a1, __int64 a2, _BYTE *a3, _BYTE *a4)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rbx
  bool v6; // cf
  _BYTE *v7; // rax

  LOBYTE(v4) = *v4 | (unsigned __int8)v4;
  v6 = __CFADD__((_BYTE)v4, *a4);
  *a4 += (_BYTE)v4;
  *a3 += v6 + 53;
  v7 = (_BYTE *)(*(_DWORD *)a4 ^ (unsigned int)v4);
  *v5 += (_BYTE)a3;
  return *v7 | (unsigned __int8)v7;
}

```

## disassembly

```asm
0x1c0dd29  or      al, [rax]
0x1c0dd2b  enter   78h, 0
0x1c0dd2f  add     [rcx], al
0x1c0dd31  adc     byte ptr [rdx], 35h ; '5'
0x1c0dd34  xor     eax, [rcx]
0x1c0dd36  add     [rbx], dl
0x1c0dd38  or      al, [rax]
0x1c0dd3a  retn
```
