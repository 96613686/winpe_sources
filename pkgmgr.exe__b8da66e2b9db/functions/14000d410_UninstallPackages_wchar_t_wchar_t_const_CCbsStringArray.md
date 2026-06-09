# UninstallPackages(wchar_t * *,wchar_t const *,CCbsStringArray &)

- ea: `0x14000d410`
- end: `0x14000d6d2`
- name: `?UninstallPackages@@YAJPEAPEA_WPEB_WAEAVCCbsStringArray@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(wchar_t **, const wchar_t *, struct CCbsStringArray *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14000aca8`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000d410`
- `0x140011100`
- `0x1400113d4`

## string_xrefs

- `0x14000d466`: `Failed to allocate memory for command line.`
- `0x14000d4db`: `Failed to allocate memory for command line.`
- `0x14000d556`: `Failed to allocate memory for command line.`
- `0x14000d622`: `Failed to allocate memory for command line.`
- `0x14000d675`: `Failed to allocate memory for command line.`
- `0x14000d445`: ` /remove-package`
- `0x14000d4b6`: ` /packagepath:"%s"`

## pseudocode

```c
__int64 __fastcall UninstallPackages(wchar_t **a1, const wchar_t *a2, struct CCbsStringArray *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // edx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edx
  __int64 v14; // rbx
  int v15; // esi
  int v17; // edx
  __int64 v18; // rdx
  int v19; // edx
  int v20; // [rsp+20h] [rbp-40h]
  int v21[2]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v22[2]; // [rsp+38h] [rbp-28h] BYREF
  int v23; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v22[1] = -2;
  v22[0] = 0;
  v6 = SczAllocConcatSz(a1, L" /remove-package");
  v7 = v6;
  if ( v6 < 0 )
  {
    v23 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v21 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v9 = 229;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
      (const char *)v7,
      v20);
    goto LABEL_21;
  }
  if ( a2 )
  {
    v10 = SczAllocFormatted(v22, L" /packagepath:\"%s\"", a2);
    v7 = v10;
    if ( v10 < 0 )
    {
      v23 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v21 = &v23;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)v21);
      }
      v9 = 233;
      goto LABEL_10;
    }
    v12 = SczAllocConcatSz(a1, v22[0]);
    v7 = v12;
    if ( v12 < 0 )
    {
      v23 = v12;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v21 = &v23;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          3,
          (unsigned int)": {}",
          (__int64)v21);
      }
      v9 = 234;
      goto LABEL_10;
    }
  }
  if ( *((_QWORD *)a3 + 3) )
  {
    v14 = 0;
    while ( 1 )
    {
      v15 = SczAllocFormatted(v22, L" /packagename:\"%s\"", *(_QWORD *)(*((_QWORD *)a3 + 5) + 8 * v14));
      if ( v15 < 0 )
        break;
      v15 = SczAllocConcatSz(a1, v22[0]);
      if ( v15 < 0 )
      {
        v23 = v15;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
          *(_QWORD *)v21 = &v23;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v17,
            3,
            (unsigned int)": {}",
            (__int64)v21);
        }
        v18 = 240;
        goto LABEL_28;
      }
      if ( (unsigned __int64)++v14 >= *((_QWORD *)a3 + 3) )
        goto LABEL_20;
    }
    v23 = v15;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v21 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v19,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v18 = 239;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
      (const char *)(unsigned int)v15,
      v20);
    v7 = v15;
  }
  else
  {
LABEL_20:
    v7 = 0;
  }
LABEL_21:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v22);
  return v7;
}

```

## disassembly

```asm
0x14000d410  push    rbp
0x14000d412  push    rbx
0x14000d413  push    rsi
0x14000d414  push    rdi
0x14000d415  push    r14
0x14000d417  mov     rbp, rsp
0x14000d41a  sub     rsp, 60h
0x14000d41e  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x14000d426  mov     rax, cs:__security_cookie
0x14000d42d  xor     rax, rsp
0x14000d430  mov     [rbp+var_10], rax
0x14000d434  mov     rdi, r8
0x14000d437  mov     rsi, rdx
0x14000d43a  mov     r14, rcx
0x14000d43d  mov     [rbp+var_28], 0
0x14000d445  lea     rdx, aRemovePackage; " /remove-package"
0x14000d44c  call    SczAllocConcatSz
0x14000d451  mov     ebx, eax
0x14000d453  test    eax, eax
0x14000d455  jns     short loc_14000D4AA
0x14000d457  mov     [rbp+var_18], eax
0x14000d45a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d461  test    rcx, rcx
0x14000d464  jz      short loc_14000D4A3
0x14000d466  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000d46d  mov     edi, 3
0x14000d472  mov     r8d, edi
0x14000d475  xor     edx, edx
0x14000d477  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000d47c  lea     rax, [rbp+var_18]
0x14000d480  mov     qword ptr [rbp+var_30], rax
0x14000d484  lea     rax, [rbp+var_30]
0x14000d488  mov     qword ptr [rsp+60h+var_40], rax
0x14000d48d  lea     r9, asc_14002D4FC; ": {}"
0x14000d494  mov     r8d, edi
0x14000d497  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d49e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000d4a3  mov     edx, 0E5h
0x14000d4a8  jmp     short loc_14000D51D
0x14000d4aa  test    rsi, rsi
0x14000d4ad  jz      loc_14000D59A
0x14000d4b3  mov     r8, rsi
0x14000d4b6  lea     rdx, aPackagepathS; " /packagepath:\"%s\""
0x14000d4bd  lea     rcx, [rbp+var_28]
0x14000d4c1  call    SczAllocFormatted
0x14000d4c6  mov     ebx, eax
0x14000d4c8  test    eax, eax
0x14000d4ca  jns     short loc_14000D535
0x14000d4cc  mov     [rbp+var_18], eax
0x14000d4cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d4d6  test    rcx, rcx
0x14000d4d9  jz      short loc_14000D518
0x14000d4db  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000d4e2  mov     edi, 3
0x14000d4e7  mov     r8d, edi
0x14000d4ea  xor     edx, edx
0x14000d4ec  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000d4f1  lea     rax, [rbp+var_18]
0x14000d4f5  mov     qword ptr [rbp+var_30], rax
0x14000d4f9  lea     rax, [rbp+var_30]
0x14000d4fd  mov     qword ptr [rsp+60h+var_40], rax; int
0x14000d502  lea     r9, asc_14002D4FC; ": {}"
0x14000d509  mov     r8d, edi
0x14000d50c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d513  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000d518  mov     edx, 0E9h; void *
0x14000d51d  mov     rcx, [rbp+28h]; this
0x14000d521  mov     r9d, ebx; char *
0x14000d524  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000d52b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d530  jmp     loc_14000D5F1
0x14000d535  mov     rdx, [rbp+var_28]
0x14000d539  mov     rcx, r14
0x14000d53c  call    SczAllocConcatSz
0x14000d541  mov     ebx, eax
0x14000d543  test    eax, eax
0x14000d545  jns     short loc_14000D59A
0x14000d547  mov     [rbp+var_18], eax
0x14000d54a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d551  test    rcx, rcx
0x14000d554  jz      short loc_14000D593
0x14000d556  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000d55d  mov     edi, 3
0x14000d562  mov     r8d, edi
0x14000d565  xor     edx, edx
0x14000d567  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000d56c  lea     rax, [rbp+var_18]
0x14000d570  mov     qword ptr [rbp+var_30], rax
0x14000d574  lea     rax, [rbp+var_30]
0x14000d578  mov     qword ptr [rsp+60h+var_40], rax
0x14000d57d  lea     r9, asc_14002D4FC; ": {}"
0x14000d584  mov     r8d, edi
0x14000d587  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d58e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000d593  mov     edx, 0EAh
0x14000d598  jmp     short loc_14000D51D
0x14000d59a  mov     rax, [rdi+18h]
0x14000d59e  test    rax, rax
0x14000d5a1  jz      short loc_14000D5EF
0x14000d5a3  xor     ebx, ebx
0x14000d5a5  cmp     rbx, rax
0x14000d5a8  jb      short loc_14000D5AF
0x14000d5aa  lea     ecx, [rbx+8]
0x14000d5ad  int     29h; Win8: RtlFailFast(ecx)
0x14000d5af  mov     r8, [rdi+28h]
0x14000d5b3  mov     r8, [r8+rbx*8]
0x14000d5b7  lea     rdx, aPackagenameS; " /packagename:\"%s\""
0x14000d5be  lea     rcx, [rbp+var_28]
0x14000d5c2  call    SczAllocFormatted
0x14000d5c7  mov     esi, eax
0x14000d5c9  test    eax, eax
0x14000d5cb  js      loc_14000D666
0x14000d5d1  mov     rdx, [rbp+var_28]
0x14000d5d5  mov     rcx, r14
0x14000d5d8  call    SczAllocConcatSz
0x14000d5dd  mov     esi, eax
0x14000d5df  test    eax, eax
0x14000d5e1  js      short loc_14000D613
0x14000d5e3  inc     rbx
0x14000d5e6  mov     rax, [rdi+18h]
0x14000d5ea  cmp     rbx, rax
0x14000d5ed  jb      short loc_14000D5AF
0x14000d5ef  xor     ebx, ebx
0x14000d5f1  lea     rcx, [rbp+var_28]
0x14000d5f5  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000d5fa  mov     eax, ebx
0x14000d5fc  mov     rcx, [rbp+var_10]
0x14000d600  xor     rcx, rsp; StackCookie
0x14000d603  call    __security_check_cookie
0x14000d608  add     rsp, 60h
0x14000d60c  pop     r14
0x14000d60e  pop     rdi
0x14000d60f  pop     rsi
0x14000d610  pop     rbx
0x14000d611  pop     rbp
0x14000d612  retn
0x14000d613  mov     [rbp+var_18], esi
0x14000d616  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d61d  test    rcx, rcx
0x14000d620  jz      short loc_14000D65F
0x14000d622  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000d629  mov     edi, 3
0x14000d62e  mov     r8d, edi
0x14000d631  xor     edx, edx
0x14000d633  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000d638  lea     rax, [rbp+var_18]
0x14000d63c  mov     qword ptr [rbp+var_30], rax
0x14000d640  lea     rax, [rbp+var_30]
0x14000d644  mov     qword ptr [rsp+60h+var_40], rax
0x14000d649  lea     r9, asc_14002D4FC; ": {}"
0x14000d650  mov     r8d, edi
0x14000d653  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d65a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000d65f  mov     edx, 0F0h
0x14000d664  jmp     short loc_14000D6B7
0x14000d666  mov     [rbp+var_18], esi
0x14000d669  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d670  test    rcx, rcx
0x14000d673  jz      short loc_14000D6B2
0x14000d675  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000d67c  mov     edi, 3
0x14000d681  mov     r8d, edi
0x14000d684  xor     edx, edx
0x14000d686  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000d68b  lea     rax, [rbp+var_18]
0x14000d68f  mov     qword ptr [rbp+var_30], rax
0x14000d693  lea     rax, [rbp+var_30]
0x14000d697  mov     qword ptr [rsp+60h+var_40], rax; int
0x14000d69c  lea     r9, asc_14002D4FC; ": {}"
0x14000d6a3  mov     r8d, edi
0x14000d6a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000d6ad  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000d6b2  mov     edx, 0EFh; void *
0x14000d6b7  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000d6be  mov     r9d, esi; char *
0x14000d6c1  mov     rcx, [rbp+28h]; this
0x14000d6c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d6ca  mov     ebx, esi
0x14000d6cc  jmp     loc_14000D5F1
```
