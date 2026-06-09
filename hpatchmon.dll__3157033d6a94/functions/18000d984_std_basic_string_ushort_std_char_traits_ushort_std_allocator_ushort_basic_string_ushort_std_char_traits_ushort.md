# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const * const)

- ea: `0x18000d984`
- end: `0x18000daaa`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z`
- size: `294`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ca0`
- `0x18000df40`
- `0x180010710`

## callees

- `0x180002cdc`
- `0x18000d984`
- `0x18000eb80`
- `0x18000ec88`
- `0x180014050`

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
0x18000d984  push    rbx
0x18000d986  push    rbp
0x18000d987  push    rsi
0x18000d988  push    rdi
0x18000d989  push    r14
0x18000d98b  push    r15
0x18000d98d  sub     rsp, 28h
0x18000d991  xor     r15d, r15d
0x18000d994  xorps   xmm0, xmm0
0x18000d997  movups  xmmword ptr [rcx], xmm0
0x18000d99a  mov     [rcx+10h], r15
0x18000d99e  mov     r14, rdx
0x18000d9a1  mov     [rcx+18h], r15
0x18000d9a5  mov     rdi, rcx
0x18000d9a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d9ac  inc     rbx
0x18000d9af  cmp     [rdx+rbx*2], r15w
0x18000d9b4  jnz     short loc_18000D9AC
0x18000d9b6  mov     rbp, 7FFFFFFFFFFFFFFEh
0x18000d9c0  cmp     rbx, rbp
0x18000d9c3  ja      loc_18000DA9E
0x18000d9c9  cmp     rbx, 7
0x18000d9cd  ja      short loc_18000D9F0
0x18000d9cf  mov     [rcx+10h], rbx
0x18000d9d3  add     rbx, rbx
0x18000d9d6  mov     r8, rbx; Size
0x18000d9d9  mov     qword ptr [rcx+18h], 7
0x18000d9e1  call    memcpy_0
0x18000d9e6  mov     [rbx+rdi], r15w
0x18000d9eb  jmp     loc_18000DA8E
0x18000d9f0  mov     rax, rbx
0x18000d9f3  or      rax, 7
0x18000d9f7  cmp     rax, rbp
0x18000d9fa  jbe     short loc_18000DA2B
0x18000d9fc  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x18000da03  cmp     rcx, 1000h
0x18000da0a  jb      short loc_18000DA65
0x18000da0c  lea     rax, [rcx+27h]
0x18000da10  cmp     rax, rcx
0x18000da13  jbe     loc_18000DAA4
0x18000da19  mov     rcx, rax; Size
0x18000da1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da21  test    rax, rax
0x18000da24  jnz     short loc_18000DA57
0x18000da26  lea     ecx, [rax+5]
0x18000da29  int     29h; Win8: RtlFailFast(ecx)
0x18000da2b  mov     ecx, 0Ah
0x18000da30  mov     rbp, rax
0x18000da33  cmp     rax, rcx
0x18000da36  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000da40  cmovb   rbp, rcx
0x18000da44  lea     rcx, [rbp+1]
0x18000da48  cmp     rcx, rax
0x18000da4b  ja      short loc_18000DAA4
0x18000da4d  add     rcx, rcx
0x18000da50  jnz     short loc_18000DA03
0x18000da52  mov     rsi, r15
0x18000da55  jmp     short loc_18000DA6D
0x18000da57  lea     rsi, [rax+27h]
0x18000da5b  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18000da5f  mov     [rsi-8], rax
0x18000da63  jmp     short loc_18000DA6D
0x18000da65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da6a  mov     rsi, rax
0x18000da6d  mov     [rdi+10h], rbx
0x18000da71  mov     rdx, r14; Src
0x18000da74  add     rbx, rbx
0x18000da77  mov     [rdi], rsi
0x18000da7a  mov     r8, rbx; Size
0x18000da7d  mov     [rdi+18h], rbp
0x18000da81  mov     rcx, rsi; void *
0x18000da84  call    memcpy_0
0x18000da89  mov     [rbx+rsi], r15w
0x18000da8e  mov     rax, rdi
0x18000da91  add     rsp, 28h
0x18000da95  pop     r15
0x18000da97  pop     r14
0x18000da99  pop     rdi
0x18000da9a  pop     rsi
0x18000da9b  pop     rbp
0x18000da9c  pop     rbx
0x18000da9d  retn
0x18000da9e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000daa4  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
