# sub_1DF7B61

- ea: `0x1df7b61`
- end: `0x1df7b76`
- name: `sub_1DF7B61`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_1DF7B61(__int64 a1, __int64 a2, _BYTE *a3, _BYTE *a4, __int64 a5, __int64 a6, __int64 a7)
{
  _DWORD *v7; // rax
  char v8; // bl
  bool v9; // cf

  *a4 += (_BYTE)a3;
  v9 = __CFADD__(*(_BYTE *)v7, (_BYTE)v7);
  LOBYTE(v7) = *(_BYTE *)v7 + (_BYTE)v7;
  BYTE1(a3) += *a3 + v9;
  v9 = __CFADD__((_DWORD)v7, *v7);
  *v7 += (_DWORD)v7;
  *(_DWORD *)a4 += (_DWORD)v7 + v9;
  BYTE1(a3) += v8;
  v9 = __CFADD__((_DWORD)v7, *v7);
  *v7 += (_DWORD)v7;
  *(_DWORD *)a3 += (_DWORD)v7 + v9;
  *(_BYTE *)v7 += (_BYTE)a3;
  return (char)v7;
}

```

## disassembly

```asm
0x1df7b61  add     [rcx], dl
0x1df7b63  add     al, [rax]
0x1df7b65  adc     dh, [rdx]
0x1df7b67  add     [rax], eax
0x1df7b69  adc     [rcx], eax
0x1df7b6b  add     dh, bl
0x1df7b6d  add     [rax], eax
0x1df7b6f  adc     [rdx], eax
0x1df7b71  add     [rax], dl
0x1df7b73  retn    1
```
