# std::filesystem::filesystem_error::filesystem_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::filesystem::path const &,std::error_code)

- ea: `0x180009824`
- end: `0x1800098fc`
- name: `??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64, const struct std::filesystem::path *, __int128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180001380`

## callees

- `0x1800019a0`
- `0x1800036b4`
- `0x1800042a4`
- `0x180005020`
- `0x180009608`
- `0x180009824`

## pseudocode

```c
__int64 __fastcall std::filesystem::filesystem_error::filesystem_error(
        __int64 a1,
        __int64 a2,
        const struct std::filesystem::path *a3,
        __int128 *a4)
{
  const char *v6; // rax
  __int64 v7; // rcx
  __int128 v9; // [rsp+20h] [rbp-50h] BYREF
  __int64 v10; // [rsp+30h] [rbp-40h]
  _OWORD v11[2]; // [rsp+40h] [rbp-30h] BYREF

  v10 = a1;
  v9 = *a4;
  std::_System_error::_System_error(a1, &v9, a2);
  *(_QWORD *)a1 = &std::filesystem::filesystem_error::`vftable';
  std::filesystem::path::path((std::filesystem::path *)(a1 + 40), a3);
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  v11[0] = 0;
  v11[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11[0]) = 0;
  v6 = "Unknown exception";
  if ( *(_QWORD *)(a1 + 8) )
    v6 = *(const char **)(a1 + 8);
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  *(_QWORD *)&v9 = v6;
  *((_QWORD *)&v9 + 1) = v7;
  std::filesystem::filesystem_error::_Pretty_message((void *)(a1 + 104));
  std::wstring::_Tidy_deallocate(v11);
  return a1;
}

```

## disassembly

```asm
0x180009824  push    rbp
0x180009826  push    rbx
0x180009827  push    rdi
0x180009828  mov     rbp, rsp
0x18000982b  sub     rsp, 70h
0x18000982f  mov     rax, cs:__security_cookie
0x180009836  xor     rax, rsp
0x180009839  mov     [rbp+var_10], rax
0x18000983d  mov     rdi, r8
0x180009840  mov     rbx, rcx
0x180009843  mov     [rbp+var_40], rcx
0x180009847  movaps  xmm0, xmmword ptr [r9]
0x18000984b  movdqa  [rbp+var_50], xmm0
0x180009850  mov     r8, rdx
0x180009853  lea     rdx, [rbp+var_50]
0x180009857  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x18000985c  nop
0x18000985d  lea     rax, ??_7filesystem_error@filesystem@std@@6B@; const std::filesystem::filesystem_error::`vftable'
0x180009864  mov     [rbx], rax
0x180009867  lea     rcx, [rbx+28h]; this
0x18000986b  mov     rdx, rdi; struct std::filesystem::path *
0x18000986e  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180009873  nop
0x180009874  xorps   xmm0, xmm0
0x180009877  movups  xmmword ptr [rbx+48h], xmm0
0x18000987b  xor     edx, edx
0x18000987d  mov     [rbx+58h], rdx
0x180009881  mov     qword ptr [rbx+60h], 7
0x180009889  mov     [rbx+48h], dx
0x18000988d  movups  [rbp+var_30], xmm0
0x180009891  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180009899  movdqu  [rbp+var_20], xmm1
0x18000989e  mov     word ptr [rbp+var_30], dx
0x1800098a2  lea     rax, aUnknownExcepti; "Unknown exception"
0x1800098a9  cmp     [rbx+8], rdx
0x1800098ad  cmovnz  rax, [rbx+8]
0x1800098b2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800098b6  inc     rcx
0x1800098b9  cmp     [rax+rcx], dl
0x1800098bc  jnz     short loc_1800098B6
0x1800098be  mov     qword ptr [rbp+var_50], rax
0x1800098c2  mov     qword ptr [rbp+var_50+8], rcx
0x1800098c6  lea     rcx, [rbx+68h]; Src
0x1800098ca  lea     r9, [rbp+var_30]
0x1800098ce  mov     r8, rdi
0x1800098d1  lea     rdx, [rbp+var_50]
0x1800098d5  call    ?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z; std::filesystem::filesystem_error::_Pretty_message(std::string_view,std::filesystem::path const &,std::filesystem::path const &)
0x1800098da  nop
0x1800098db  lea     rcx, [rbp+var_30]
0x1800098df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800098e4  nop
0x1800098e5  mov     rax, rbx
0x1800098e8  mov     rcx, [rbp+var_10]
0x1800098ec  xor     rcx, rsp; StackCookie
0x1800098ef  call    __security_check_cookie
0x1800098f4  add     rsp, 70h
0x1800098f8  pop     rdi
0x1800098f9  pop     rbx
0x1800098fa  pop     rbp
0x1800098fb  retn
```
