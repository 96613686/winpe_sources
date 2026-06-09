# SczAllocConcatSz

- ea: `0x140011100`
- end: `0x1400113cc`
- name: `SczAllocConcatSz`
- size: `716`
- prototype: `__int64 __fastcall(const void **, const wchar_t *, __int64, size_t)`
- caller_count: `9`
- callee_count: `11`
- tags: ``

## callers

- `0x14000a1dc`
- `0x14000aca8`
- `0x14000b454`
- `0x14000bf34`
- `0x14000c384`
- `0x14000d410`
- `0x140011d50`
- `0x140012b88`
- `0x140013288`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x140005bf0`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000eab4`
- `0x14000eae0`
- `0x140011100`
- `0x140011e8c`
- `0x140029bf4`

## pseudocode

```c
__int64 __fastcall SczAllocConcatSz(const void **a1, const wchar_t *a2, __int64 a3, size_t a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v10; // rdx
  size_t v11; // rsi
  __int64 v12; // rdi
  const void *v13; // rcx
  __int64 v14; // r14
  int v15; // eax
  unsigned int v16; // edi
  size_t v17; // rdx
  size_t *v18; // rax
  _WORD *v19; // r14
  int v20; // eax
  __int64 v21; // rdx
  int v22[2]; // [rsp+30h] [rbp-30h] BYREF
  int v23[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v24; // [rsp+40h] [rbp-20h]
  size_t *v25; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v24 = -2;
  if ( !a1 )
  {
    v6 = -2147467261;
    LODWORD(v25) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v22 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v22);
    }
    v8 = 202;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v6);
    return v6;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    LODWORD(v25) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string to append specified");
      *(_QWORD *)v22 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        3,
        (__int64)": {}",
        (__int64)v22);
    }
    v8 = 203;
    goto LABEL_5;
  }
  v11 = 0;
  *(_QWORD *)v22 = 0;
  v12 = 0;
  v13 = *a1;
  v14 = -1;
  if ( v13 )
  {
    v15 = SczSize(v13, v22);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
        (const char *)(unsigned int)v15);
      return v16;
    }
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)*a1 + v12) );
    v11 = *(_QWORD *)v22;
  }
  do
    ++v14;
  while ( a2[v14] );
  *(_QWORD *)v22 = 0;
  v17 = v14 + v12 + 1;
  if ( v11 < v17 )
  {
    v11 = v14 + v12 + 1;
    v25 = 0;
    if ( !Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&v25, 2 * v17 + 8) )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDD,
        (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
        (const char *)0x8007000ELL);
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v25);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v22);
      return v6;
    }
    v18 = v25;
    *v25 = v11;
    v19 = v18 + 1;
    if ( *a1 )
      memcpy_0(v18 + 1, *a1, 2 * v12 + 2);
    else
      *v19 = 0;
    *(_QWORD *)v22 = *a1;
    *a1 = v19;
    v25 = 0;
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v25);
  }
  v20 = StringCchCatW((wchar_t *)*a1, v11, a2, a4);
  v6 = v20;
  if ( v20 < 0 )
  {
    LODWORD(v25) = v20;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to concat string.");
      *(_QWORD *)v23 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v21,
        3,
        (__int64)": {}",
        (__int64)v23);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v6);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v22);
    return v6;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v22);
  return 0;
}

```

## disassembly

```asm
0x140011100  mov     rax, rsp
0x140011103  push    rbp
0x140011104  push    rdi
0x140011105  push    r12
0x140011107  push    r14
0x140011109  push    r15
0x14001110b  mov     rbp, rsp
0x14001110e  sub     rsp, 60h
0x140011112  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x14001111a  mov     [rax+18h], rbx
0x14001111e  mov     [rax+20h], rsi
0x140011122  mov     rax, cs:__security_cookie
0x140011129  xor     rax, rsp
0x14001112c  mov     [rbp+var_10], rax
0x140011130  mov     r15, rdx
0x140011133  mov     rbx, rcx
0x140011136  xor     r12d, r12d
0x140011139  test    rcx, rcx
0x14001113c  jnz     short loc_1400111AE
0x14001113e  mov     ebx, 80004003h
0x140011143  mov     dword ptr [rbp+var_18], ebx
0x140011146  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001114d  test    rcx, rcx
0x140011150  jz      short loc_14001118F
0x140011152  lea     r9, aNoStringResult; "No string result specified"
0x140011159  lea     edi, [r12+3]
0x14001115e  mov     r8d, edi
0x140011161  xor     edx, edx
0x140011163  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011168  lea     rax, [rbp+var_18]
0x14001116c  mov     qword ptr [rbp+var_30], rax
0x140011170  lea     rcx, [rbp+var_30]
0x140011174  mov     qword ptr [rsp+60h+var_40], rcx; int
0x140011179  lea     r9, asc_14002D4FC; ": {}"
0x140011180  mov     r8d, edi
0x140011183  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001118a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001118f  mov     edx, 0CAh; void *
0x140011194  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001119b  mov     r9d, ebx; char *
0x14001119e  mov     rcx, [rbp+28h]; this
0x1400111a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400111a7  mov     eax, ebx
0x1400111a9  jmp     loc_1400113A7
0x1400111ae  test    r15, r15
0x1400111b1  jnz     short loc_14001120A
0x1400111b3  mov     ebx, 80070057h
0x1400111b8  mov     dword ptr [rbp+var_18], ebx
0x1400111bb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400111c2  test    rcx, rcx
0x1400111c5  jz      short loc_140011203
0x1400111c7  lea     r9, aNoStringToAppe; "No string to append specified"
0x1400111ce  lea     edi, [r15+3]
0x1400111d2  mov     r8d, edi
0x1400111d5  xor     edx, edx
0x1400111d7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400111dc  lea     rax, [rbp+var_18]
0x1400111e0  mov     qword ptr [rbp+var_30], rax
0x1400111e4  lea     rcx, [rbp+var_30]
0x1400111e8  mov     qword ptr [rsp+60h+var_40], rcx
0x1400111ed  lea     r9, asc_14002D4FC; ": {}"
0x1400111f4  mov     r8d, edi
0x1400111f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400111fe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011203  mov     edx, 0CBh
0x140011208  jmp     short loc_140011194
0x14001120a  mov     rsi, r12
0x14001120d  mov     qword ptr [rbp+var_30], r12
0x140011211  mov     rdi, r12
0x140011214  mov     rcx, [rcx]
0x140011217  or      r14, 0FFFFFFFFFFFFFFFFh
0x14001121b  test    rcx, rcx
0x14001121e  jz      short loc_140011262
0x140011220  lea     rdx, [rbp+var_30]
0x140011224  call    SczSize
0x140011229  mov     edi, eax
0x14001122b  test    eax, eax
0x14001122d  jns     short loc_14001124E
0x14001122f  mov     rcx, [rbp+28h]; this
0x140011233  mov     r9d, eax; char *
0x140011236  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001123d  mov     edx, 0D2h; void *
0x140011242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011247  mov     eax, edi
0x140011249  jmp     loc_1400113A7
0x14001124e  mov     rax, [rbx]
0x140011251  mov     rdi, r14
0x140011254  inc     rdi
0x140011257  cmp     [rax+rdi*2], r12w
0x14001125c  jnz     short loc_140011254
0x14001125e  mov     rsi, qword ptr [rbp+var_30]
0x140011262  inc     r14
0x140011265  cmp     [r15+r14*2], r12w
0x14001126a  jnz     short loc_140011262
0x14001126c  mov     qword ptr [rbp+var_30], r12
0x140011270  lea     rdx, [rdi+1]
0x140011274  add     rdx, r14
0x140011277  cmp     rsi, rdx
0x14001127a  jnb     loc_140011313
0x140011280  mov     rsi, rdx
0x140011283  mov     [rbp+var_18], r12
0x140011287  lea     rdx, ds:8[rdx*2]
0x14001128f  lea     rcx, [rbp+var_18]
0x140011293  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x140011298  test    rax, rax
0x14001129b  jnz     short loc_1400112D3
0x14001129d  mov     rcx, [rbp+28h]; this
0x1400112a1  mov     ebx, 8007000Eh
0x1400112a6  mov     r9d, ebx; char *
0x1400112a9  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1400112b0  mov     edx, 0DDh; void *
0x1400112b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400112ba  lea     rcx, [rbp+var_18]
0x1400112be  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x1400112c3  nop
0x1400112c4  lea     rcx, [rbp+var_30]
0x1400112c8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400112cd  nop
0x1400112ce  jmp     loc_1400111A7
0x1400112d3  mov     rax, [rbp+var_18]
0x1400112d7  mov     [rax], rsi
0x1400112da  lea     r14, [rax+8]
0x1400112de  mov     rdx, [rbx]; Src
0x1400112e1  test    rdx, rdx
0x1400112e4  jz      short loc_1400112F8
0x1400112e6  lea     r8, ds:2[rdi*2]; Size
0x1400112ee  mov     rcx, r14; void *
0x1400112f1  call    memcpy_0
0x1400112f6  jmp     short loc_1400112FC
0x1400112f8  mov     [r14], r12w
0x1400112fc  mov     rax, [rbx]
0x1400112ff  mov     qword ptr [rbp+var_30], rax
0x140011303  mov     [rbx], r14
0x140011306  mov     [rbp+var_18], r12
0x14001130a  lea     rcx, [rbp+var_18]
0x14001130e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x140011313  mov     r8, r15; wchar_t *
0x140011316  mov     rdx, rsi; unsigned __int64
0x140011319  mov     rcx, [rbx]; wchar_t *
0x14001131c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140011321  mov     ebx, eax
0x140011323  test    eax, eax
0x140011325  jns     short loc_14001139B
0x140011327  mov     dword ptr [rbp+var_18], eax
0x14001132a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011331  test    rcx, rcx
0x140011334  jz      short loc_140011373
0x140011336  lea     r9, aFailedToConcat; "Failed to concat string."
0x14001133d  mov     edi, 3
0x140011342  mov     r8d, edi
0x140011345  xor     edx, edx
0x140011347  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001134c  lea     rax, [rbp+var_18]
0x140011350  mov     qword ptr [rbp+var_28], rax
0x140011354  lea     rax, [rbp+var_28]
0x140011358  mov     qword ptr [rsp+60h+var_40], rax; int
0x14001135d  lea     r9, asc_14002D4FC; ": {}"
0x140011364  mov     r8d, edi
0x140011367  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001136e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011373  mov     rcx, [rbp+28h]; this
0x140011377  mov     r9d, ebx; char *
0x14001137a  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140011381  mov     edx, 0F4h; void *
0x140011386  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001138b  nop
0x14001138c  lea     rcx, [rbp+var_30]
0x140011390  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140011395  nop
0x140011396  jmp     loc_1400111A7
0x14001139b  lea     rcx, [rbp+var_30]
0x14001139f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400113a4  nop
0x1400113a5  xor     eax, eax
0x1400113a7  mov     rcx, [rbp+var_10]
0x1400113ab  xor     rcx, rsp; StackCookie
0x1400113ae  call    __security_check_cookie
0x1400113b3  lea     r11, [rsp+60h+var_s0]
0x1400113b8  mov     rbx, [r11+40h]
0x1400113bc  mov     rsi, [r11+48h]
0x1400113c0  mov     rsp, r11
0x1400113c3  pop     r15
0x1400113c5  pop     r14
0x1400113c7  pop     r12
0x1400113c9  pop     rdi
0x1400113ca  pop     rbp
0x1400113cb  retn
```
