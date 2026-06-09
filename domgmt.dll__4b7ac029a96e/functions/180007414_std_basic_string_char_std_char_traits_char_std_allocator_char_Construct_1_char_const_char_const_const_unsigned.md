# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Construct<1,char const *>(char const * const,unsigned __int64)

- ea: `0x180007414`
- end: `0x1800074fe`
- name: `??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z`
- size: `234`
- prototype: `void *__fastcall(_QWORD *, const void *, size_t)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800082f8`
- `0x18000ac40`
- `0x18000ac90`

## callees

- `0x180001fb8`
- `0x180007414`
- `0x18000a938`
- `0x18000aa3c`
- `0x18000d5b4`

## pseudocode

```c
void *__fastcall std::string::_Construct<1,char const *>(_QWORD *a1, const void *a2, size_t a3)
{
  __int64 v3; // rsi
  void *result; // rax
  size_t v8; // rax
  void *v9; // rax
  size_t v10; // rcx
  _QWORD *v11; // rdi

  v3 = 0x7FFFFFFFFFFFFFFFLL;
  if ( a3 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( a3 <= 0xF )
  {
    a1[2] = a3;
    a1[3] = 15;
    result = memcpy_0(a1, a2, a3);
    *((_BYTE *)a1 + a3) = 0;
    return result;
  }
  if ( (a3 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
  {
    v8 = 0x8000000000000027uLL;
LABEL_6:
    v9 = operator new(v8);
    if ( !v9 )
      __fastfail(5u);
    v11 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v11 - 1) = v9;
    goto LABEL_17;
  }
  v3 = a3 | 0xF;
  if ( (a3 | 0xF) < 0x16 )
    v3 = 22;
  v10 = v3 + 1;
  if ( v3 == -1 )
  {
    v11 = 0;
  }
  else
  {
    if ( v10 >= 0x1000 )
    {
      v8 = v3 + 40;
      if ( v3 + 40 < (unsigned __int64)(v3 + 1) )
        __scrt_throw_std_bad_array_new_length();
      goto LABEL_6;
    }
    v11 = operator new(v10);
  }
LABEL_17:
  *a1 = v11;
  a1[2] = a3;
  a1[3] = v3;
  result = memcpy_0(v11, a2, a3);
  *((_BYTE *)v11 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180007414  push    rbx
0x180007416  push    rbp
0x180007417  push    rsi
0x180007418  push    rdi
0x180007419  push    r14
0x18000741b  sub     rsp, 20h
0x18000741f  mov     rsi, 7FFFFFFFFFFFFFFFh
0x180007429  mov     rbx, r8
0x18000742c  mov     rbp, rdx
0x18000742f  mov     r14, rcx
0x180007432  cmp     r8, rsi
0x180007435  ja      loc_1800074F2
0x18000743b  cmp     rbx, 0Fh
0x18000743f  ja      short loc_18000745C
0x180007441  mov     [rcx+10h], rbx
0x180007445  mov     qword ptr [rcx+18h], 0Fh
0x18000744d  call    memcpy_0
0x180007452  mov     byte ptr [rbx+r14], 0
0x180007457  jmp     loc_1800074E7
0x18000745c  mov     rax, rbx
0x18000745f  or      rax, 0Fh
0x180007463  cmp     rax, rsi
0x180007466  jbe     short loc_180007484
0x180007468  mov     rax, 8000000000000027h
0x180007472  mov     rcx, rax; Size
0x180007475  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000747a  test    rax, rax
0x18000747d  jnz     short loc_1800074B4
0x18000747f  lea     ecx, [rax+5]
0x180007482  int     29h; Win8: RtlFailFast(ecx)
0x180007484  mov     ecx, 16h
0x180007489  mov     rsi, rax
0x18000748c  cmp     rax, rcx
0x18000748f  cmovb   rsi, rcx
0x180007493  lea     rcx, [rsi+1]; Size
0x180007497  test    rcx, rcx
0x18000749a  jnz     short loc_1800074A0
0x18000749c  xor     edi, edi
0x18000749e  jmp     short loc_1800074CA
0x1800074a0  cmp     rcx, 1000h
0x1800074a7  jb      short loc_1800074C2
0x1800074a9  lea     rax, [rcx+27h]
0x1800074ad  cmp     rax, rcx
0x1800074b0  jbe     short loc_1800074F8
0x1800074b2  jmp     short loc_180007472
0x1800074b4  lea     rdi, [rax+27h]
0x1800074b8  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1800074bc  mov     [rdi-8], rax
0x1800074c0  jmp     short loc_1800074CA
0x1800074c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800074c7  mov     rdi, rax
0x1800074ca  mov     r8, rbx; Size
0x1800074cd  mov     [r14], rdi
0x1800074d0  mov     rdx, rbp; Src
0x1800074d3  mov     [r14+10h], rbx
0x1800074d7  mov     rcx, rdi; void *
0x1800074da  mov     [r14+18h], rsi
0x1800074de  call    memcpy_0
0x1800074e3  mov     byte ptr [rdi+rbx], 0
0x1800074e7  add     rsp, 20h
0x1800074eb  pop     r14
0x1800074ed  pop     rdi
0x1800074ee  pop     rsi
0x1800074ef  pop     rbp
0x1800074f0  pop     rbx
0x1800074f1  retn
0x1800074f2  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800074f8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
