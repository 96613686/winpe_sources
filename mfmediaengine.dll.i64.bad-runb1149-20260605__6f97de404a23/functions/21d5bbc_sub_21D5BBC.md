# sub_21D5BBC

- ea: `0x21d5bbc`
- end: `0x21d5c0c`
- name: `sub_21D5BBC`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
long double __fastcall sub_21D5BBC(__int64 a1, __int64 a2, _BYTE *a3, _BYTE *a4, __int64 a5, __int64 a6, __int64 a7)
{
  _DWORD *v7; // rax
  _BYTE *v8; // rbx
  __int64 v9; // rbp
  long double v10; // fst7
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  bool v13; // cf
  long double result; // fst7
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  LOBYTE(v7) = *a4 + (_BYTE)v7;
  *((_BYTE *)&dword_1030001 + a1) += BYTE1(v8);
  *((_BYTE *)&dword_1020001 + v9) += (_BYTE)v8;
  *((_BYTE *)&dword_1030001 + (_QWORD)v8) += (_BYTE)a4;
  *(_BYTE *)(v9 + 1) += (_BYTE)a4;
  *a3 += (_BYTE)v7;
  *v7 += (_DWORD)v7;
  *v8 += (_BYTE)v8;
  *v7 += (_DWORD)v7;
  LOBYTE(v7) = *a3 + (_BYTE)v7;
  *((_BYTE *)v7 + (_QWORD)v8) += (_BYTE)a4;
  *v7 += (_DWORD)v7;
  v11 = (unsigned int)(*(_DWORD *)a4 + (_DWORD)v7);
  a4[v11] += (_BYTE)v8;
  LOBYTE(v11) = *a4 + v11;
  a4[v11] += (_BYTE)a4;
  v12 = (unsigned int)(*(_DWORD *)a4 + v11);
  *a3 += BYTE1(a4);
  *(_DWORD *)v12 += v12;
  LOBYTE(v12) = *a3 + v12;
  v13 = __CFADD__((_BYTE)a4, *v8);
  *v8 += (_BYTE)a4;
  *a4 -= v13 + v12;
  *v8 += v12;
  *(_DWORD *)v12 += v12;
  result = v10 + (long double)*(int *)a4;
  *a3 += v12;
  *(_DWORD *)v12 += v12;
  MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
  return result;
}

```

## disassembly

```asm
0x21d5bbc  add     al, [rcx]
0x21d5bbe  add     byte ptr ds:dword_1030001[rdi], bh
0x21d5bc4  add     byte ptr ss:dword_1020001[rbp], bl
0x21d5bca  add     byte ptr ds:dword_1030001[rbx], cl
0x21d5bd0  add     [rbp+1], cl
0x21d5bd3  add     [rdx], al
0x21d5bd5  add     [rax], eax
0x21d5bd7  cmp     eax, offset dword_1030001
0x21d5bdc  add     [rbx], bl
0x21d5bde  add     [rax], eax
0x21d5be0  add     al, [rdx]
0x21d5be2  add     [rbx+rax], cl
0x21d5be5  add     [rax], eax
0x21d5be7  add     eax, [rcx]
0x21d5be9  add     [rcx+rax+0], bl
0x21d5bed  add     al, [rcx]
0x21d5bef  add     [rcx+rax+0], cl
0x21d5bf3  add     eax, [rcx]
0x21d5bf5  add     [rdx], ch
0x21d5bf7  add     [rax], eax
0x21d5bf9  add     al, [rdx]
0x21d5bfb  add     [rbx], cl
0x21d5bfd  sbb     [rcx], al
0x21d5bff  add     [rbx], al
0x21d5c01  add     [rax], eax
0x21d5c03  fiadd   dword ptr [rcx]
0x21d5c05  add     [rdx], al
0x21d5c07  add     [rax], eax
0x21d5c09  retf    1
```
