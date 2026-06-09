# Cab_CreateCab

- ea: `0x180006b60`
- end: `0x180006d15`
- name: `Cab_CreateCab`
- size: `437`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001540`
- `0x180002f70`
- `0x180003648`
- `0x18000553c`
- `0x180006b60`
- `0x180008c24`

## pseudocode

```c
__int64 __fastcall Cab_CreateCab(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  unsigned int Cab; // eax
  _OWORD *v15; // rcx
  int v17; // [rsp+20h] [rbp-A1h]
  _OWORD v18[2]; // [rsp+30h] [rbp-91h] BYREF
  _OWORD v19[2]; // [rsp+50h] [rbp-71h] BYREF
  _OWORD v20[2]; // [rsp+70h] [rbp-51h] BYREF
  _OWORD v21[2]; // [rsp+90h] [rbp-31h] BYREF
  _OWORD v22[2]; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  if ( !a1 )
  {
    v8 = 340;
LABEL_3:
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\cabapi.cpp",
      (const char *)0x80004003LL,
      v17);
    return v9;
  }
  if ( !a2 )
  {
    v8 = 341;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v8 = 342;
    goto LABEL_3;
  }
  v10 = -1;
  memset(v20, 0, sizeof(v20));
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a1 + 2 * v11) );
  std::wstring::_Construct<1,wchar_t const *>(v20, a1, v11);
  memset(v19, 0, sizeof(v19));
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(a2 + 2 * v12) );
  std::wstring::_Construct<1,wchar_t const *>(v19, a2, v12);
  memset(v18, 0, sizeof(v18));
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(a3 + 2 * v13) );
  std::wstring::_Construct<1,wchar_t const *>(v18, a3, v13);
  if ( a4 )
  {
    memset(v22, 0, sizeof(v22));
    do
      ++v10;
    while ( *(_WORD *)(a4 + 2 * v10) );
    std::wstring::_Construct<1,wchar_t const *>(v22, a4, v10);
    Cab = Cabinet::CreateCab((unsigned int)v20, (unsigned int)v19, (unsigned int)v18, (unsigned int)v22, a5);
    v15 = v22;
  }
  else
  {
    v21[0] = 0;
    LOWORD(v21[0]) = 0;
    v21[1] = _mm_load_si128((const __m128i *)&_xmm);
    Cab = Cabinet::CreateCab((unsigned int)v20, (unsigned int)v19, (unsigned int)v18, (unsigned int)v21, a5);
    v15 = v21;
  }
  v9 = Cab;
  std::wstring::~wstring(v15);
  std::wstring::~wstring(v18);
  std::wstring::~wstring(v19);
  std::wstring::~wstring(v20);
  return v9;
}

```

## disassembly

```asm
0x180006b60  push    rbp
0x180006b62  push    rbx
0x180006b63  push    rsi
0x180006b64  push    rdi
0x180006b65  push    r14
0x180006b67  push    r15
0x180006b69  lea     rbp, [rsp-27h]
0x180006b6e  sub     rsp, 0E8h
0x180006b75  mov     rax, cs:__security_cookie
0x180006b7c  xor     rax, rsp
0x180006b7f  mov     [rbp+4Fh+var_40], rax
0x180006b83  xor     r15d, r15d
0x180006b86  mov     r14, r9
0x180006b89  mov     rdi, r8
0x180006b8c  mov     rsi, rdx
0x180006b8f  test    rcx, rcx
0x180006b92  jnz     short loc_180006BB6
0x180006b94  mov     edx, 154h; void *
0x180006b99  mov     rcx, [rbp+57h]; this
0x180006b9d  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\cabapi\\cab"...
0x180006ba4  mov     ebx, 80004003h
0x180006ba9  mov     r9d, ebx; char *
0x180006bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006bb1  jmp     loc_180006CF7
0x180006bb6  test    rsi, rsi
0x180006bb9  jnz     short loc_180006BC2
0x180006bbb  mov     edx, 155h
0x180006bc0  jmp     short loc_180006B99
0x180006bc2  test    rdi, rdi
0x180006bc5  jnz     short loc_180006BCE
0x180006bc7  mov     edx, 156h
0x180006bcc  jmp     short loc_180006B99
0x180006bce  xorps   xmm0, xmm0
0x180006bd1  xorps   xmm1, xmm1
0x180006bd4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006bd8  movups  [rbp+4Fh+var_A0], xmm0
0x180006bdc  mov     r8, rbx
0x180006bdf  movdqu  [rbp+4Fh+var_90], xmm1
0x180006be4  inc     r8
0x180006be7  cmp     [rcx+r8*2], r15w
0x180006bec  jnz     short loc_180006BE4
0x180006bee  mov     rdx, rcx
0x180006bf1  lea     rcx, [rbp+4Fh+var_A0]
0x180006bf5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006bfa  xorps   xmm0, xmm0
0x180006bfd  xorps   xmm1, xmm1
0x180006c00  movups  [rbp+4Fh+var_C0], xmm0
0x180006c04  mov     r8, rbx
0x180006c07  movdqu  [rbp+4Fh+var_B0], xmm1
0x180006c0c  inc     r8
0x180006c0f  cmp     [rsi+r8*2], r15w
0x180006c14  jnz     short loc_180006C0C
0x180006c16  mov     rdx, rsi
0x180006c19  lea     rcx, [rbp+4Fh+var_C0]
0x180006c1d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006c22  xorps   xmm0, xmm0
0x180006c25  xorps   xmm1, xmm1
0x180006c28  movups  [rsp+110h+var_E0], xmm0
0x180006c2d  mov     r8, rbx
0x180006c30  movdqu  [rsp+110h+var_D0], xmm1
0x180006c36  inc     r8
0x180006c39  cmp     [rdi+r8*2], r15w
0x180006c3e  jnz     short loc_180006C36
0x180006c40  mov     rdx, rdi
0x180006c43  lea     rcx, [rsp+110h+var_E0]
0x180006c48  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006c4d  xorps   xmm0, xmm0
0x180006c50  test    r14, r14
0x180006c53  jnz     short loc_180006C8E
0x180006c55  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180006c5d  lea     r9, [rbp+4Fh+var_80]
0x180006c61  mov     eax, [rbp+4Fh+arg_20]
0x180006c64  lea     r8, [rsp+110h+var_E0]
0x180006c69  movups  [rbp+4Fh+var_80], xmm0
0x180006c6d  lea     rdx, [rbp+4Fh+var_C0]
0x180006c71  mov     word ptr [rbp+4Fh+var_80], r15w
0x180006c76  lea     rcx, [rbp+4Fh+var_A0]
0x180006c7a  mov     [rsp+110h+var_F0], eax
0x180006c7e  movdqu  [rbp+4Fh+var_70], xmm1
0x180006c83  call    ?CreateCab@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000W4CompressionType@@@Z; Cabinet::CreateCab(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,CompressionType)
0x180006c88  lea     rcx, [rbp+4Fh+var_80]
0x180006c8c  jmp     short loc_180006CD4
0x180006c8e  xorps   xmm1, xmm1
0x180006c91  movdqu  [rbp+4Fh+var_50], xmm1
0x180006c96  movups  [rbp+4Fh+var_60], xmm0
0x180006c9a  inc     rbx
0x180006c9d  cmp     [r14+rbx*2], r15w
0x180006ca2  jnz     short loc_180006C9A
0x180006ca4  mov     r8, rbx
0x180006ca7  lea     rcx, [rbp+4Fh+var_60]
0x180006cab  mov     rdx, r14
0x180006cae  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006cb3  mov     eax, [rbp+4Fh+arg_20]
0x180006cb6  lea     r9, [rbp+4Fh+var_60]
0x180006cba  lea     r8, [rsp+110h+var_E0]
0x180006cbf  mov     [rsp+110h+var_F0], eax
0x180006cc3  lea     rdx, [rbp+4Fh+var_C0]
0x180006cc7  lea     rcx, [rbp+4Fh+var_A0]
0x180006ccb  call    ?CreateCab@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000W4CompressionType@@@Z; Cabinet::CreateCab(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,CompressionType)
0x180006cd0  lea     rcx, [rbp+4Fh+var_60]
0x180006cd4  mov     ebx, eax
0x180006cd6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006cdb  lea     rcx, [rsp+110h+var_E0]
0x180006ce0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006ce5  lea     rcx, [rbp+4Fh+var_C0]
0x180006ce9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006cee  lea     rcx, [rbp+4Fh+var_A0]
0x180006cf2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006cf7  mov     eax, ebx
0x180006cf9  mov     rcx, [rbp+4Fh+var_40]
0x180006cfd  xor     rcx, rsp; StackCookie
0x180006d00  call    __security_check_cookie
0x180006d05  add     rsp, 0E8h
0x180006d0c  pop     r15
0x180006d0e  pop     r14
0x180006d10  pop     rdi
0x180006d11  pop     rsi
0x180006d12  pop     rbx
0x180006d13  pop     rbp
0x180006d14  retn
```
