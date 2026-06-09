# WfpFlagsPrint

- ea: `0x18000f020`
- end: `0x18000f0ab`
- name: `WfpFlagsPrint`
- size: `139`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f7f0`
- `0x18000fda0`
- `0x180010088`

## callees

- `0x18000f020`
- `0x180012010`

## pseudocode

```c
wchar_t **__fastcall WfpFlagsPrint(
        __int64 (*a1)(__int64, const wchar_t *, ...),
        __int64 a2,
        unsigned int a3,
        unsigned __int64 a4,
        __int64 a5,
        int a6)
{
  wchar_t **result; // rax
  wchar_t *v10; // r14
  unsigned __int64 i; // rbx

  if ( a3 < 7 )
    result = (wchar_t **)((char *)&off_180014118 + 8 * a3);
  else
    result = off_180014148;
  v10 = *result;
  for ( i = 0; i < a4; ++i )
  {
    if ( (a6 & *(_DWORD *)(a5 + 16 * i)) != 0 )
      result = (wchar_t **)a1(a2, L"%s%s\n", v10, *(_QWORD *)(a5 + 16 * i + 8));
  }
  return result;
}

```

## disassembly

```asm
0x18000f020  push    rbx
0x18000f022  push    rbp
0x18000f023  push    rsi
0x18000f024  push    rdi
0x18000f025  push    r12
0x18000f027  push    r14
0x18000f029  push    r15
0x18000f02b  sub     rsp, 30h
0x18000f02f  mov     rsi, [rsp+68h+arg_20]
0x18000f037  mov     rdi, r9
0x18000f03a  mov     r15, rdx
0x18000f03d  mov     r12, rcx
0x18000f040  cmp     r8d, 7
0x18000f044  jb      short loc_18000F04F
0x18000f046  lea     rax, off_180014148; "            "
0x18000f04d  jmp     short loc_18000F05D
0x18000f04f  mov     eax, r8d
0x18000f052  lea     rcx, off_180014118
0x18000f059  lea     rax, [rcx+rax*8]
0x18000f05d  mov     r14, [rax]
0x18000f060  xor     ebx, ebx
0x18000f062  test    rdi, rdi
0x18000f065  jz      short loc_18000F09C
0x18000f067  mov     ebp, [rsp+68h+arg_28]
0x18000f06e  mov     r9, rbx
0x18000f071  add     r9, r9
0x18000f074  test    [rsi+r9*8], ebp
0x18000f078  jz      short loc_18000F094
0x18000f07a  mov     r9, [rsi+r9*8+8]
0x18000f07f  lea     rdx, aSS_0; "%s%s\n"
0x18000f086  mov     r8, r14
0x18000f089  mov     rcx, r15
0x18000f08c  mov     rax, r12
0x18000f08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f094  inc     rbx
0x18000f097  cmp     rbx, rdi
0x18000f09a  jb      short loc_18000F06E
0x18000f09c  add     rsp, 30h
0x18000f0a0  pop     r15
0x18000f0a2  pop     r14
0x18000f0a4  pop     r12
0x18000f0a6  pop     rdi
0x18000f0a7  pop     rsi
0x18000f0a8  pop     rbp
0x18000f0a9  pop     rbx
0x18000f0aa  retn
```
