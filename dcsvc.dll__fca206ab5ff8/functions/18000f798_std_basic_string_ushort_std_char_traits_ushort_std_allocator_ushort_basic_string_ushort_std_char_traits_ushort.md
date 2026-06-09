# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const * const)

- ea: `0x18000f798`
- end: `0x18000f8be`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z`
- size: `294`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fcfc`
- `0x180010a14`
- `0x180010af0`

## callees

- `0x180002a80`
- `0x18000f798`
- `0x1800118bc`
- `0x1800118fc`
- `0x180011c6c`

## pseudocode

```c
_QWORD *__fastcall std::wstring::wstring(_QWORD *a1, _WORD *a2)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  size_t v6; // rbx
  size_t v7; // rcx
  void *v8; // rax
  _QWORD *v9; // rsi
  size_t v10; // rbx

  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( (v4 | 7) < 0xA )
        v5 = 10;
      if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_22;
      v7 = 2 * (v5 + 1);
      if ( !v7 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v7 = -2;
    }
    if ( v7 >= 0x1000 )
    {
      if ( v7 + 39 >= v7 )
      {
        v8 = operator new(v7 + 39);
        if ( !v8 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v7);
LABEL_19:
    a1[2] = v4;
    v10 = 2 * v4;
    *a1 = v9;
    a1[3] = v5;
    memcpy_0(v9, a2, v10);
    *(_WORD *)((char *)v9 + v10) = 0;
    return a1;
  }
  a1[2] = v4;
  v6 = 2 * v4;
  a1[3] = 7;
  memcpy_0(a1, a2, v6);
  *(_WORD *)((char *)a1 + v6) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000f798  push    rbx
0x18000f79a  push    rbp
0x18000f79b  push    rsi
0x18000f79c  push    rdi
0x18000f79d  push    r14
0x18000f79f  push    r15
0x18000f7a1  sub     rsp, 28h
0x18000f7a5  xor     r15d, r15d
0x18000f7a8  xorps   xmm0, xmm0
0x18000f7ab  movups  xmmword ptr [rcx], xmm0
0x18000f7ae  mov     [rcx+10h], r15
0x18000f7b2  mov     r14, rdx
0x18000f7b5  mov     [rcx+18h], r15
0x18000f7b9  mov     rdi, rcx
0x18000f7bc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f7c0  inc     rbx
0x18000f7c3  cmp     [rdx+rbx*2], r15w
0x18000f7c8  jnz     short loc_18000F7C0
0x18000f7ca  mov     rbp, 7FFFFFFFFFFFFFFEh
0x18000f7d4  cmp     rbx, rbp
0x18000f7d7  ja      loc_18000F8B2
0x18000f7dd  cmp     rbx, 7
0x18000f7e1  ja      short loc_18000F804
0x18000f7e3  mov     [rcx+10h], rbx
0x18000f7e7  add     rbx, rbx
0x18000f7ea  mov     r8, rbx; Size
0x18000f7ed  mov     qword ptr [rcx+18h], 7
0x18000f7f5  call    memcpy_0
0x18000f7fa  mov     [rbx+rdi], r15w
0x18000f7ff  jmp     loc_18000F8A2
0x18000f804  mov     rax, rbx
0x18000f807  or      rax, 7
0x18000f80b  cmp     rax, rbp
0x18000f80e  jbe     short loc_18000F83F
0x18000f810  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x18000f817  cmp     rcx, 1000h
0x18000f81e  jb      short loc_18000F879
0x18000f820  lea     rax, [rcx+27h]
0x18000f824  cmp     rax, rcx
0x18000f827  jbe     loc_18000F8B8
0x18000f82d  mov     rcx, rax; Size
0x18000f830  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f835  test    rax, rax
0x18000f838  jnz     short loc_18000F86B
0x18000f83a  lea     ecx, [rax+5]
0x18000f83d  int     29h; Win8: RtlFailFast(ecx)
0x18000f83f  mov     ecx, 0Ah
0x18000f844  mov     rbp, rax
0x18000f847  cmp     rax, rcx
0x18000f84a  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000f854  cmovb   rbp, rcx
0x18000f858  lea     rcx, [rbp+1]
0x18000f85c  cmp     rcx, rax
0x18000f85f  ja      short loc_18000F8B8
0x18000f861  add     rcx, rcx
0x18000f864  jnz     short loc_18000F817
0x18000f866  mov     rsi, r15
0x18000f869  jmp     short loc_18000F881
0x18000f86b  lea     rsi, [rax+27h]
0x18000f86f  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18000f873  mov     [rsi-8], rax
0x18000f877  jmp     short loc_18000F881
0x18000f879  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f87e  mov     rsi, rax
0x18000f881  mov     [rdi+10h], rbx
0x18000f885  mov     rdx, r14; Src
0x18000f888  add     rbx, rbx
0x18000f88b  mov     [rdi], rsi
0x18000f88e  mov     r8, rbx; Size
0x18000f891  mov     [rdi+18h], rbp
0x18000f895  mov     rcx, rsi; void *
0x18000f898  call    memcpy_0
0x18000f89d  mov     [rbx+rsi], r15w
0x18000f8a2  mov     rax, rdi
0x18000f8a5  add     rsp, 28h
0x18000f8a9  pop     r15
0x18000f8ab  pop     r14
0x18000f8ad  pop     rdi
0x18000f8ae  pop     rsi
0x18000f8af  pop     rbp
0x18000f8b0  pop     rbx
0x18000f8b1  retn
0x18000f8b2  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000f8b8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
