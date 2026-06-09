# SczAllocFromSz

- ea: `0x140011884`
- end: `0x140011a46`
- name: `SczAllocFromSz`
- size: `450`
- prototype: `__int64 __fastcall(unsigned __int64 **, const wchar_t *)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400072a8`
- `0x140007524`
- `0x14000903c`
- `0x1400092fc`
- `0x14000a1dc`
- `0x14000b454`
- `0x14000baa4`
- `0x140012b88`
- `0x140013288`
- `0x140015a08`
- `0x140017568`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x140005c44`
- `0x1400067bc`
- `0x140006c50`
- `0x140010b3c`
- `0x140011884`

## string_xrefs

- `0x1400119e2`: `Failed to copy source string to destination`

## pseudocode

```c
__int64 __fastcall SczAllocFromSz(unsigned __int64 **a1, const wchar_t *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  size_t v10; // r14
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  __int64 v14; // rdx
  int v15[2]; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a1 )
  {
    v4 = -2147467261;
    v16 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v15);
    }
    v6 = 399;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v4);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v16 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      *(_QWORD *)v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v15);
    }
    v6 = 400;
    goto LABEL_5;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 1;
  v11 = SczAlloc(a1, v9 + 1);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = StringCchCopyW((wchar_t *)*a1, v10, a2);
    v4 = v13;
    if ( v13 < 0 )
    {
      v16 = v13;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
        *(_QWORD *)v15 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v14,
          3,
          (__int64)": {}",
          (__int64)v15);
      }
      v6 = 404;
      goto LABEL_5;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v11);
    return v12;
  }
}

```

## disassembly

```asm
0x140011884  mov     [rsp-28h+arg_10], rbx
0x140011889  push    rbp
0x14001188a  push    rsi
0x14001188b  push    rdi
0x14001188c  push    r14
0x14001188e  push    r15
0x140011890  mov     rbp, rsp
0x140011893  sub     rsp, 50h
0x140011897  mov     rax, cs:__security_cookie
0x14001189e  xor     rax, rsp
0x1400118a1  mov     [rbp+var_10], rax
0x1400118a5  xor     r15d, r15d
0x1400118a8  mov     rbx, rdx
0x1400118ab  mov     rsi, rcx
0x1400118ae  test    rcx, rcx
0x1400118b1  jnz     short loc_140011921
0x1400118b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400118ba  mov     ebx, 80004003h
0x1400118bf  mov     [rbp+var_18], ebx
0x1400118c2  test    rcx, rcx
0x1400118c5  jz      short loc_140011902
0x1400118c7  lea     edi, [rsi+3]
0x1400118ca  xor     edx, edx
0x1400118cc  mov     r8d, edi
0x1400118cf  lea     r9, aNoStringResult; "No string result specified"
0x1400118d6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400118db  lea     rcx, [rbp+var_20]
0x1400118df  mov     r8d, edi
0x1400118e2  mov     qword ptr [rsp+50h+var_30], rcx; int
0x1400118e7  lea     rax, [rbp+var_18]
0x1400118eb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400118f2  lea     r9, asc_14002D4FC; ": {}"
0x1400118f9  mov     qword ptr [rbp+var_20], rax
0x1400118fd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011902  mov     edx, 18Fh; void *
0x140011907  mov     rcx, [rbp+28h]; this
0x14001190b  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140011912  mov     r9d, ebx; char *
0x140011915  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001191a  mov     eax, ebx
0x14001191c  jmp     loc_140011A26
0x140011921  test    rbx, rbx
0x140011924  jnz     short loc_14001197E
0x140011926  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001192d  mov     ebx, 80070057h
0x140011932  mov     [rbp+var_18], ebx
0x140011935  test    rcx, rcx
0x140011938  jz      short loc_140011977
0x14001193a  mov     edi, 3
0x14001193f  lea     r9, aNoStringSpecif; "No string specified"
0x140011946  mov     r8d, edi
0x140011949  xor     edx, edx
0x14001194b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011950  lea     rcx, [rbp+var_20]
0x140011954  mov     r8d, edi
0x140011957  mov     qword ptr [rsp+50h+var_30], rcx
0x14001195c  lea     rax, [rbp+var_18]
0x140011960  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011967  lea     r9, asc_14002D4FC; ": {}"
0x14001196e  mov     qword ptr [rbp+var_20], rax
0x140011972  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011977  mov     edx, 190h
0x14001197c  jmp     short loc_140011907
0x14001197e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011982  inc     rax
0x140011985  cmp     [rdx+rax*2], r15w
0x14001198a  jnz     short loc_140011982
0x14001198c  lea     r14, [rax+1]
0x140011990  mov     rdx, r14
0x140011993  call    SczAlloc
0x140011998  mov     edi, eax
0x14001199a  test    eax, eax
0x14001199c  jns     short loc_1400119BA
0x14001199e  mov     rcx, [rbp+28h]; this
0x1400119a2  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1400119a9  mov     r9d, eax; char *
0x1400119ac  mov     edx, 193h; void *
0x1400119b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400119b6  mov     eax, edi
0x1400119b8  jmp     short loc_140011A26
0x1400119ba  mov     rcx, [rsi]; wchar_t *
0x1400119bd  mov     r8, rbx; wchar_t *
0x1400119c0  mov     rdx, r14; unsigned __int64
0x1400119c3  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400119c8  mov     ebx, eax
0x1400119ca  test    eax, eax
0x1400119cc  jns     short loc_140011A24
0x1400119ce  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400119d5  mov     [rbp+var_18], eax
0x1400119d8  test    rcx, rcx
0x1400119db  jz      short loc_140011A1A
0x1400119dd  mov     edi, 3
0x1400119e2  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x1400119e9  mov     r8d, edi
0x1400119ec  xor     edx, edx
0x1400119ee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400119f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400119fa  lea     rax, [rbp+var_18]
0x1400119fe  mov     qword ptr [rbp+var_20], rax
0x140011a02  lea     r9, asc_14002D4FC; ": {}"
0x140011a09  lea     rax, [rbp+var_20]
0x140011a0d  mov     r8d, edi
0x140011a10  mov     qword ptr [rsp+50h+var_30], rax
0x140011a15  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011a1a  mov     edx, 194h
0x140011a1f  jmp     loc_140011907
0x140011a24  xor     eax, eax
0x140011a26  mov     rcx, [rbp+var_10]
0x140011a2a  xor     rcx, rsp; StackCookie
0x140011a2d  call    __security_check_cookie
0x140011a32  mov     rbx, [rsp+50h+arg_10]
0x140011a3a  add     rsp, 50h
0x140011a3e  pop     r15
0x140011a40  pop     r14
0x140011a42  pop     rdi
0x140011a43  pop     rsi
0x140011a44  pop     rbp
0x140011a45  retn
```
