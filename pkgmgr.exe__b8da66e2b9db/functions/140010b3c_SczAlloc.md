# SczAlloc

- ea: `0x140010b3c`
- end: `0x140010d2c`
- name: `SczAlloc`
- size: `496`
- prototype: `__int64 __fastcall(unsigned __int64 **, unsigned __int64)`
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140008de8`
- `0x14000903c`
- `0x14001154c`
- `0x140011884`
- `0x140015a08`
- `0x140016328`
- `0x1400170c0`
- `0x140017eb4`

## callees

- `0x140001fcc`
- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000eab4`
- `0x14000eae0`
- `0x140010b3c`
- `0x140011e8c`

## pseudocode

```c
__int64 __fastcall SczAlloc(unsigned __int64 **a1, unsigned __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  unsigned __int64 *v9; // rcx
  int v10; // eax
  unsigned int v11; // esi
  unsigned __int64 *v12; // rcx
  int v13[2]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v14; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  if ( !a1 )
  {
    v4 = -2147467261;
    LODWORD(v14) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v13 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v13);
    }
    v6 = 12;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v4);
    return v4;
  }
  if ( a2 > 0x3FFFFFFF )
  {
    v4 = -2147317563;
    LODWORD(v14) = -2147317563;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"string size too big");
      *(_QWORD *)v13 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v13);
    }
    v6 = 13;
    goto LABEL_5;
  }
  v9 = *a1;
  v14 = 0;
  if ( !v9 )
  {
LABEL_17:
    if ( *a1 )
      return 0;
    goto LABEL_18;
  }
  v10 = SczSize(v9, &v14);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v10);
    return v11;
  }
  if ( v14 >= a2 )
  {
    if ( v14 )
      *(_WORD *)*a1 = 0;
    goto LABEL_17;
  }
  operator delete(*a1 - 1);
  *a1 = 0;
LABEL_18:
  v14 = 0;
  if ( !Windows::AutoNewArrayPtr<unsigned char>::AllocateArray(&v14, 2 * a2 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)0x8007000ELL);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v14);
    return 2147942414LL;
  }
  v12 = (unsigned __int64 *)v14;
  v14 = 0;
  *v12++ = a2;
  *a1 = v12;
  *(_WORD *)v12 = 0;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)&v14);
  return 0;
}

```

## disassembly

```asm
0x140010b3c  mov     [rsp-18h+arg_10], rbx
0x140010b41  push    rbp
0x140010b42  push    rsi
0x140010b43  push    rdi
0x140010b44  mov     rbp, rsp
0x140010b47  sub     rsp, 50h
0x140010b4b  mov     rax, cs:__security_cookie
0x140010b52  xor     rax, rsp
0x140010b55  mov     [rbp+var_10], rax
0x140010b59  mov     rdi, rdx
0x140010b5c  mov     rbx, rcx
0x140010b5f  test    rcx, rcx
0x140010b62  jnz     short loc_140010BD4
0x140010b64  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140010b6b  mov     edi, 80004003h
0x140010b70  mov     dword ptr [rbp+var_18], edi
0x140010b73  test    rcx, rcx
0x140010b76  jz      short loc_140010BB5
0x140010b78  mov     ebx, 3
0x140010b7d  lea     r9, aNoStringResult; "No string result specified"
0x140010b84  mov     r8d, ebx
0x140010b87  xor     edx, edx
0x140010b89  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140010b8e  lea     rcx, [rbp+var_20]
0x140010b92  mov     r8d, ebx
0x140010b95  mov     qword ptr [rsp+50h+var_30], rcx; int
0x140010b9a  lea     rax, [rbp+var_18]
0x140010b9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140010ba5  lea     r9, asc_14002D4FC; ": {}"
0x140010bac  mov     qword ptr [rbp+var_20], rax
0x140010bb0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140010bb5  mov     edx, 0Ch; void *
0x140010bba  mov     rcx, [rbp+18h]; this
0x140010bbe  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140010bc5  mov     r9d, edi; char *
0x140010bc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010bcd  mov     eax, edi
0x140010bcf  jmp     loc_140010D10
0x140010bd4  cmp     rdi, 3FFFFFFFh
0x140010bdb  jbe     short loc_140010C35
0x140010bdd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140010be4  mov     edi, 800288C5h
0x140010be9  mov     dword ptr [rbp+var_18], edi
0x140010bec  test    rcx, rcx
0x140010bef  jz      short loc_140010C2E
0x140010bf1  mov     ebx, 3
0x140010bf6  lea     r9, aStringSizeTooB; "string size too big"
0x140010bfd  mov     r8d, ebx
0x140010c00  xor     edx, edx
0x140010c02  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140010c07  lea     rcx, [rbp+var_20]
0x140010c0b  mov     r8d, ebx
0x140010c0e  mov     qword ptr [rsp+50h+var_30], rcx
0x140010c13  lea     rax, [rbp+var_18]
0x140010c17  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140010c1e  lea     r9, asc_14002D4FC; ": {}"
0x140010c25  mov     qword ptr [rbp+var_20], rax
0x140010c29  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140010c2e  mov     edx, 0Dh
0x140010c33  jmp     short loc_140010BBA
0x140010c35  mov     rcx, [rcx]
0x140010c38  mov     [rbp+var_18], 0
0x140010c40  test    rcx, rcx
0x140010c43  jz      short loc_140010C9E
0x140010c45  lea     rdx, [rbp+var_18]
0x140010c49  call    SczSize
0x140010c4e  mov     esi, eax
0x140010c50  test    eax, eax
0x140010c52  jns     short loc_140010C73
0x140010c54  mov     rcx, [rbp+18h]; this
0x140010c58  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140010c5f  mov     r9d, eax; char *
0x140010c62  mov     edx, 15h; void *
0x140010c67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010c6c  mov     eax, esi
0x140010c6e  jmp     loc_140010D10
0x140010c73  mov     rax, [rbp+var_18]
0x140010c77  cmp     rax, rdi
0x140010c7a  jnb     short loc_140010C91
0x140010c7c  mov     rcx, [rbx]
0x140010c7f  sub     rcx, 8; Block
0x140010c83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140010c88  mov     qword ptr [rbx], 0
0x140010c8f  jmp     short loc_140010CA4
0x140010c91  test    rax, rax
0x140010c94  jz      short loc_140010C9E
0x140010c96  mov     rcx, [rbx]
0x140010c99  xor     eax, eax
0x140010c9b  mov     [rcx], ax
0x140010c9e  cmp     qword ptr [rbx], 0
0x140010ca2  jnz     short loc_140010D0E
0x140010ca4  lea     rdx, ds:8[rdi*2]
0x140010cac  mov     [rbp+var_18], 0
0x140010cb4  lea     rcx, [rbp+var_18]
0x140010cb8  call    ?AllocateArray@?$AutoNewArrayPtr@E@Windows@@QEAAPEAE_K@Z; Windows::AutoNewArrayPtr<uchar>::AllocateArray(unsigned __int64)
0x140010cbd  test    rax, rax
0x140010cc0  jnz     short loc_140010CEA
0x140010cc2  mov     rcx, [rbp+18h]; this
0x140010cc6  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140010ccd  mov     ebx, 8007000Eh
0x140010cd2  lea     edx, [rax+27h]; void *
0x140010cd5  mov     r9d, ebx; char *
0x140010cd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010cdd  lea     rcx, [rbp+var_18]
0x140010ce1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x140010ce6  mov     eax, ebx
0x140010ce8  jmp     short loc_140010D10
0x140010cea  mov     rcx, [rbp+var_18]
0x140010cee  xor     eax, eax
0x140010cf0  mov     [rbp+var_18], 0
0x140010cf8  mov     [rcx], rdi
0x140010cfb  add     rcx, 8
0x140010cff  mov     [rbx], rcx
0x140010d02  mov     [rcx], ax
0x140010d05  lea     rcx, [rbp+var_18]
0x140010d09  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x140010d0e  xor     eax, eax
0x140010d10  mov     rcx, [rbp+var_10]
0x140010d14  xor     rcx, rsp; StackCookie
0x140010d17  call    __security_check_cookie
0x140010d1c  mov     rbx, [rsp+50h+arg_10]
0x140010d24  add     rsp, 50h
0x140010d28  pop     rdi
0x140010d29  pop     rsi
0x140010d2a  pop     rbp
0x140010d2b  retn
```
