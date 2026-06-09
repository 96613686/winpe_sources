# sub_2CD61C

- ea: `0x2cd61c`
- end: `0x2cd638`
- name: `sub_2CD61C`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
long double __fastcall sub_2CD61C(_BYTE *a1, _BYTE *a2, _DWORD *a3, int *a4, __int64 a5, __int64 a6, __int64 a7)
{
  _DWORD *v7; // rax
  _BYTE *v8; // rbx
  __int64 v9; // rbp
  unsigned __int64 v10; // rax
  long double v11; // fst7
  long double result; // fst7

  *v7 += (_DWORD)v7;
  v10 = (unsigned int)(*a3 + (_DWORD)v7);
  *(_BYTE *)(v9 + 50331923) += BYTE1(v10);
  LOBYTE(v10) = *(_BYTE *)v10 + v10;
  *a1 = *a2;
  v11 = (long double)*a4;
  *v8 += v10;
  *(_DWORD *)v10 += v10;
  result = v11 + (long double)*a4;
  *v8 += v10;
  *(_DWORD *)v10 += v10;
  return result;
}

```

## disassembly

```asm
0x2cd61c  add     [rax], eax
0x2cd61e  add     eax, [rdx]
0x2cd620  add     [rbp+3000113h], ah
0x2cd626  add     al, [rax]
0x2cd628  movsb
0x2cd629  fild    dword ptr [rcx]
0x2cd62b  add     [rbx], al
0x2cd62d  add     [rax], eax
0x2cd62f  fiadd   dword ptr [rcx]
0x2cd631  add     [rbx], al
0x2cd633  add     [rax], eax
0x2cd635  retn    1
```
