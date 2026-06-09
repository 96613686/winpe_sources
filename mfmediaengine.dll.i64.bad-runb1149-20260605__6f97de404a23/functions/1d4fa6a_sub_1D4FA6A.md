# sub_1D4FA6A

- ea: `0x1d4fa6a`
- end: `0x1d4fa80`
- name: `sub_1D4FA6A`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_1D4FA6A(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27,
        __int64 a28,
        __int64 a29,
        __int64 a30,
        __int64 a31,
        __int64 a32,
        __int64 a33,
        __int64 a34,
        __int64 a35,
        __int64 a36,
        __int64 a37,
        __int64 a38,
        __int64 a39,
        __int64 a40,
        __int64 a41)
{
  _BYTE *v41; // rax
  _BYTE *v42; // rbx
  unsigned __int64 v43; // rax

  *v42 += a3;
  LOBYTE(v41) = *v41 | (unsigned __int8)v41;
  v43 = (unsigned int)((_DWORD)v41 - 88);
  *(int *)((char *)&dword_1EAC114 + v43) += v43;
  *v42 += a3;
  return *(_BYTE *)v43 + v43;
}

```

## disassembly

```asm
0x1d4fa6a  add     [rbx], dl
0x1d4fa6c  or      al, [rax]
0x1d4fa6e  sub     eax, 58h ; 'X'
0x1d4fa73  add     ds:dword_1EAC114[rax], eax
0x1d4fa79  add     [rbx], dl
0x1d4fa7b  add     al, [rax]
0x1d4fa7d  retn    114h
```
