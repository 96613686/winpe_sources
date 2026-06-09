# std::filesystem::filesystem_error::filesystem_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::filesystem::path const &,std::error_code)

- ea: `0x180008988`
- end: `0x180008a60`
- name: `??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64, const struct std::filesystem::path *, __int128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a960`

## callees

- `0x180001ba0`
- `0x1800085fc`
- `0x180008988`
- `0x180008a68`
- `0x180008d88`
- `0x18000a59c`

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
  std::wstring::~wstring(v11);
  return a1;
}

```

## disassembly

```asm
0x180008988  push    rbp
0x18000898a  push    rbx
0x18000898b  push    rdi
0x18000898c  mov     rbp, rsp
0x18000898f  sub     rsp, 70h
0x180008993  mov     rax, cs:__security_cookie
0x18000899a  xor     rax, rsp
0x18000899d  mov     [rbp+var_10], rax
0x1800089a1  mov     rdi, r8
0x1800089a4  mov     rbx, rcx
0x1800089a7  mov     [rbp+var_40], rcx
0x1800089ab  movaps  xmm0, xmmword ptr [r9]
0x1800089af  movdqa  [rbp+var_50], xmm0
0x1800089b4  mov     r8, rdx
0x1800089b7  lea     rdx, [rbp+var_50]
0x1800089bb  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x1800089c0  nop
0x1800089c1  lea     rax, ??_7filesystem_error@filesystem@std@@6B@; const std::filesystem::filesystem_error::`vftable'
0x1800089c8  mov     [rbx], rax
0x1800089cb  lea     rcx, [rbx+28h]; this
0x1800089cf  mov     rdx, rdi; struct std::filesystem::path *
0x1800089d2  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x1800089d7  nop
0x1800089d8  xorps   xmm0, xmm0
0x1800089db  movups  xmmword ptr [rbx+48h], xmm0
0x1800089df  xor     edx, edx
0x1800089e1  mov     [rbx+58h], rdx
0x1800089e5  mov     qword ptr [rbx+60h], 7
0x1800089ed  mov     [rbx+48h], dx
0x1800089f1  movups  [rbp+var_30], xmm0
0x1800089f5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800089fd  movdqu  [rbp+var_20], xmm1
0x180008a02  mov     word ptr [rbp+var_30], dx
0x180008a06  lea     rax, aUnknownExcepti; "Unknown exception"
0x180008a0d  cmp     [rbx+8], rdx
0x180008a11  cmovnz  rax, [rbx+8]
0x180008a16  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008a1a  inc     rcx
0x180008a1d  cmp     [rax+rcx], dl
0x180008a20  jnz     short loc_180008A1A
0x180008a22  mov     qword ptr [rbp+var_50], rax
0x180008a26  mov     qword ptr [rbp+var_50+8], rcx
0x180008a2a  lea     rcx, [rbx+68h]; Src
0x180008a2e  lea     r9, [rbp+var_30]
0x180008a32  mov     r8, rdi
0x180008a35  lea     rdx, [rbp+var_50]
0x180008a39  call    ?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z; std::filesystem::filesystem_error::_Pretty_message(std::string_view,std::filesystem::path const &,std::filesystem::path const &)
0x180008a3e  nop
0x180008a3f  lea     rcx, [rbp+var_30]
0x180008a43  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a48  nop
0x180008a49  mov     rax, rbx
0x180008a4c  mov     rcx, [rbp+var_10]
0x180008a50  xor     rcx, rsp; StackCookie
0x180008a53  call    __security_check_cookie
0x180008a58  add     rsp, 70h
0x180008a5c  pop     rdi
0x180008a5d  pop     rbx
0x180008a5e  pop     rbp
0x180008a5f  retn
```
