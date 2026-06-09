# ProcessSelectableUpdates(wchar_t * *,wchar_t const *,wchar_t const *,CCbsStringArray &,int)

- ea: `0x14000c384`
- end: `0x14000c7a6`
- name: `?ProcessSelectableUpdates@@YAJPEAPEA_WPEB_W1AEAVCCbsStringArray@@H@Z`
- size: `1058`
- prototype: `__int64 __fastcall(wchar_t **, const wchar_t *, const wchar_t *, struct CCbsStringArray *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000aca8`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000c384`
- `0x140011100`
- `0x1400113d4`

## string_xrefs

- `0x14000c3e9`: `Failed to allocate memory for command line.`
- `0x14000c44e`: `Failed to allocate memory for command line.`
- `0x14000c4d9`: `Failed to allocate memory for command line.`
- `0x14000c545`: `Failed to allocate memory for command line.`
- `0x14000c5bd`: `Failed to allocate memory for command line.`
- `0x14000c625`: `Failed to allocate memory for command line.`
- `0x14000c6f6`: `Failed to allocate memory for command line.`
- `0x14000c749`: `Failed to allocate memory for command line.`
- `0x14000c4b4`: ` /packagepath:"%s"`
- `0x14000c689`: ` /featurename:"%s"`

## pseudocode

```c
__int64 __fastcall ProcessSelectableUpdates(
        wchar_t **a1,
        const wchar_t *a2,
        const wchar_t *a3,
        struct CCbsStringArray *a4,
        int a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // edx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // edx
  int v17; // eax
  int v18; // edx
  int v19; // eax
  int v20; // edx
  int v21; // eax
  int v22; // edx
  __int64 v23; // rbx
  int v24; // esi
  int v26; // edx
  __int64 v27; // rdx
  int v28; // edx
  int v29; // [rsp+20h] [rbp-48h]
  int v30[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v31[2]; // [rsp+38h] [rbp-30h] BYREF
  int v32; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v31[1] = -2;
  v31[0] = 0;
  if ( a5 )
  {
    v9 = SczAllocConcatSz(a1, L" /enable-feature /ignorecheck");
    v10 = v9;
    if ( v9 < 0 )
    {
      v32 = v9;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v30 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v12 = 261;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
        (const char *)v10,
        v29);
      goto LABEL_35;
    }
  }
  else
  {
    v13 = SczAllocConcatSz(a1, L" /disable-feature");
    v10 = v13;
    if ( v13 < 0 )
    {
      v32 = v13;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v30 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v14,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v12 = 265;
      goto LABEL_10;
    }
  }
  if ( a2 )
  {
    v15 = SczAllocFormatted(v31, L" /packagepath:\"%s\"", a2);
    v10 = v15;
    if ( v15 < 0 )
    {
      v32 = v15;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v30 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v16,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v12 = 270;
      goto LABEL_10;
    }
    v17 = SczAllocConcatSz(a1, v31[0]);
    v10 = v17;
    if ( v17 < 0 )
    {
      v32 = v17;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v30 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v18,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v12 = 271;
      goto LABEL_10;
    }
  }
  else if ( a3 )
  {
    v19 = SczAllocFormatted(v31, L" /packagename:\"%s\"", a3);
    v10 = v19;
    if ( v19 < 0 )
    {
      v32 = v19;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v30 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v20,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v12 = 275;
      goto LABEL_10;
    }
    v21 = SczAllocConcatSz(a1, v31[0]);
    v10 = v21;
    if ( v21 < 0 )
    {
      v32 = v21;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
        *(_QWORD *)v30 = &v32;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {}",
          (__int64)v30);
      }
      v12 = 276;
      goto LABEL_10;
    }
  }
  if ( *((_QWORD *)a4 + 3) )
  {
    v23 = 0;
    while ( 1 )
    {
      v24 = SczAllocFormatted(v31, L" /featurename:\"%s\"", *(_QWORD *)(*((_QWORD *)a4 + 5) + 8 * v23));
      if ( v24 < 0 )
        break;
      v24 = SczAllocConcatSz(a1, v31[0]);
      if ( v24 < 0 )
      {
        v32 = v24;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
          *(_QWORD *)v30 = &v32;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v26,
            3,
            (unsigned int)": {}",
            (__int64)v30);
        }
        v27 = 282;
        goto LABEL_42;
      }
      if ( (unsigned __int64)++v23 >= *((_QWORD *)a4 + 3) )
        goto LABEL_34;
    }
    v32 = v24;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v30 = &v32;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v28,
        3,
        (unsigned int)": {}",
        (__int64)v30);
    }
    v27 = 281;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
      (const char *)(unsigned int)v24,
      v29);
    v10 = v24;
  }
  else
  {
LABEL_34:
    v10 = 0;
  }
LABEL_35:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v31);
  return v10;
}

```

## disassembly

```asm
0x14000c384  push    rbp
0x14000c386  push    rbx
0x14000c387  push    rsi
0x14000c388  push    rdi
0x14000c389  push    r14
0x14000c38b  push    r15
0x14000c38d  mov     rbp, rsp
0x14000c390  sub     rsp, 68h
0x14000c394  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x14000c39c  mov     rax, cs:__security_cookie
0x14000c3a3  xor     rax, rsp
0x14000c3a6  mov     [rbp+var_18], rax
0x14000c3aa  mov     r15, r9
0x14000c3ad  mov     rsi, r8
0x14000c3b0  mov     r14, rdx
0x14000c3b3  mov     rdi, rcx
0x14000c3b6  mov     [rbp+var_30], 0
0x14000c3be  cmp     [rbp+arg_20], 0
0x14000c3c2  jz      short loc_14000C42D
0x14000c3c4  lea     rdx, aEnableFeatureI; " /enable-feature /ignorecheck"
0x14000c3cb  call    SczAllocConcatSz
0x14000c3d0  mov     ebx, eax
0x14000c3d2  test    eax, eax
0x14000c3d4  jns     loc_14000C4A8
0x14000c3da  mov     [rbp+var_20], eax
0x14000c3dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c3e4  test    rcx, rcx
0x14000c3e7  jz      short loc_14000C426
0x14000c3e9  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c3f0  mov     edi, 3
0x14000c3f5  mov     r8d, edi
0x14000c3f8  xor     edx, edx
0x14000c3fa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c3ff  lea     rax, [rbp+var_20]
0x14000c403  mov     qword ptr [rbp+var_38], rax
0x14000c407  lea     rax, [rbp+var_38]
0x14000c40b  mov     qword ptr [rsp+68h+var_48], rax
0x14000c410  lea     r9, asc_14002D4FC; ": {}"
0x14000c417  mov     r8d, edi
0x14000c41a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c421  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c426  mov     edx, 105h
0x14000c42b  jmp     short loc_14000C490
0x14000c42d  lea     rdx, aDisableFeature; " /disable-feature"
0x14000c434  call    SczAllocConcatSz
0x14000c439  mov     ebx, eax
0x14000c43b  test    eax, eax
0x14000c43d  jns     short loc_14000C4A8
0x14000c43f  mov     [rbp+var_20], eax
0x14000c442  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c449  test    rcx, rcx
0x14000c44c  jz      short loc_14000C48B
0x14000c44e  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c455  mov     edi, 3
0x14000c45a  mov     r8d, edi
0x14000c45d  xor     edx, edx
0x14000c45f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c464  lea     rax, [rbp+var_20]
0x14000c468  mov     qword ptr [rbp+var_38], rax
0x14000c46c  lea     rax, [rbp+var_38]
0x14000c470  mov     qword ptr [rsp+68h+var_48], rax; int
0x14000c475  lea     r9, asc_14002D4FC; ": {}"
0x14000c47c  mov     r8d, edi
0x14000c47f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c486  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c48b  mov     edx, 109h; void *
0x14000c490  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000c497  mov     r9d, ebx; char *
0x14000c49a  mov     rcx, [rbp+30h]; this
0x14000c49e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c4a3  jmp     loc_14000C6C3
0x14000c4a8  test    r14, r14
0x14000c4ab  jz      loc_14000C58C
0x14000c4b1  mov     r8, r14
0x14000c4b4  lea     rdx, aPackagepathS; " /packagepath:\"%s\""
0x14000c4bb  lea     rcx, [rbp+var_30]
0x14000c4bf  call    SczAllocFormatted
0x14000c4c4  mov     ebx, eax
0x14000c4c6  test    eax, eax
0x14000c4c8  jns     short loc_14000C520
0x14000c4ca  mov     [rbp+var_20], eax
0x14000c4cd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c4d4  test    rcx, rcx
0x14000c4d7  jz      short loc_14000C516
0x14000c4d9  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c4e0  mov     edi, 3
0x14000c4e5  mov     r8d, edi
0x14000c4e8  xor     edx, edx
0x14000c4ea  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c4ef  lea     rax, [rbp+var_20]
0x14000c4f3  mov     qword ptr [rbp+var_38], rax
0x14000c4f7  lea     rax, [rbp+var_38]
0x14000c4fb  mov     qword ptr [rsp+68h+var_48], rax
0x14000c500  lea     r9, asc_14002D4FC; ": {}"
0x14000c507  mov     r8d, edi
0x14000c50a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c511  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c516  mov     edx, 10Eh
0x14000c51b  jmp     loc_14000C490
0x14000c520  mov     rdx, [rbp+var_30]
0x14000c524  mov     rcx, rdi
0x14000c527  call    SczAllocConcatSz
0x14000c52c  mov     ebx, eax
0x14000c52e  test    eax, eax
0x14000c530  jns     loc_14000C66C
0x14000c536  mov     [rbp+var_20], eax
0x14000c539  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c540  test    rcx, rcx
0x14000c543  jz      short loc_14000C582
0x14000c545  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c54c  mov     edi, 3
0x14000c551  mov     r8d, edi
0x14000c554  xor     edx, edx
0x14000c556  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c55b  lea     rax, [rbp+var_20]
0x14000c55f  mov     qword ptr [rbp+var_38], rax
0x14000c563  lea     rax, [rbp+var_38]
0x14000c567  mov     qword ptr [rsp+68h+var_48], rax
0x14000c56c  lea     r9, asc_14002D4FC; ": {}"
0x14000c573  mov     r8d, edi
0x14000c576  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c57d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c582  mov     edx, 10Fh
0x14000c587  jmp     loc_14000C490
0x14000c58c  test    rsi, rsi
0x14000c58f  jz      loc_14000C66C
0x14000c595  mov     r8, rsi
0x14000c598  lea     rdx, aPackagenameS; " /packagename:\"%s\""
0x14000c59f  lea     rcx, [rbp+var_30]
0x14000c5a3  call    SczAllocFormatted
0x14000c5a8  mov     ebx, eax
0x14000c5aa  test    eax, eax
0x14000c5ac  jns     short loc_14000C604
0x14000c5ae  mov     [rbp+var_20], eax
0x14000c5b1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c5b8  test    rcx, rcx
0x14000c5bb  jz      short loc_14000C5FA
0x14000c5bd  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c5c4  mov     edi, 3
0x14000c5c9  mov     r8d, edi
0x14000c5cc  xor     edx, edx
0x14000c5ce  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c5d3  lea     rax, [rbp+var_20]
0x14000c5d7  mov     qword ptr [rbp+var_38], rax
0x14000c5db  lea     rax, [rbp+var_38]
0x14000c5df  mov     qword ptr [rsp+68h+var_48], rax
0x14000c5e4  lea     r9, asc_14002D4FC; ": {}"
0x14000c5eb  mov     r8d, edi
0x14000c5ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c5f5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c5fa  mov     edx, 113h
0x14000c5ff  jmp     loc_14000C490
0x14000c604  mov     rdx, [rbp+var_30]
0x14000c608  mov     rcx, rdi
0x14000c60b  call    SczAllocConcatSz
0x14000c610  mov     ebx, eax
0x14000c612  test    eax, eax
0x14000c614  jns     short loc_14000C66C
0x14000c616  mov     [rbp+var_20], eax
0x14000c619  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c620  test    rcx, rcx
0x14000c623  jz      short loc_14000C662
0x14000c625  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c62c  mov     edi, 3
0x14000c631  mov     r8d, edi
0x14000c634  xor     edx, edx
0x14000c636  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c63b  lea     rax, [rbp+var_20]
0x14000c63f  mov     qword ptr [rbp+var_38], rax
0x14000c643  lea     rax, [rbp+var_38]
0x14000c647  mov     qword ptr [rsp+68h+var_48], rax
0x14000c64c  lea     r9, asc_14002D4FC; ": {}"
0x14000c653  mov     r8d, edi
0x14000c656  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c65d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c662  mov     edx, 114h
0x14000c667  jmp     loc_14000C490
0x14000c66c  mov     rax, [r15+18h]
0x14000c670  test    rax, rax
0x14000c673  jz      short loc_14000C6C1
0x14000c675  xor     ebx, ebx
0x14000c677  cmp     rbx, rax
0x14000c67a  jb      short loc_14000C681
0x14000c67c  lea     ecx, [rbx+8]
0x14000c67f  int     29h; Win8: RtlFailFast(ecx)
0x14000c681  mov     r8, [r15+28h]
0x14000c685  mov     r8, [r8+rbx*8]
0x14000c689  lea     rdx, aFeaturenameS; " /featurename:\"%s\""
0x14000c690  lea     rcx, [rbp+var_30]
0x14000c694  call    SczAllocFormatted
0x14000c699  mov     esi, eax
0x14000c69b  test    eax, eax
0x14000c69d  js      loc_14000C73A
0x14000c6a3  mov     rdx, [rbp+var_30]
0x14000c6a7  mov     rcx, rdi
0x14000c6aa  call    SczAllocConcatSz
0x14000c6af  mov     esi, eax
0x14000c6b1  test    eax, eax
0x14000c6b3  js      short loc_14000C6E7
0x14000c6b5  inc     rbx
0x14000c6b8  mov     rax, [r15+18h]
0x14000c6bc  cmp     rbx, rax
0x14000c6bf  jb      short loc_14000C681
0x14000c6c1  xor     ebx, ebx
0x14000c6c3  lea     rcx, [rbp+var_30]
0x14000c6c7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000c6cc  mov     eax, ebx
0x14000c6ce  mov     rcx, [rbp+var_18]
0x14000c6d2  xor     rcx, rsp; StackCookie
0x14000c6d5  call    __security_check_cookie
0x14000c6da  add     rsp, 68h
0x14000c6de  pop     r15
0x14000c6e0  pop     r14
0x14000c6e2  pop     rdi
0x14000c6e3  pop     rsi
0x14000c6e4  pop     rbx
0x14000c6e5  pop     rbp
0x14000c6e6  retn
0x14000c6e7  mov     [rbp+var_20], esi
0x14000c6ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c6f1  test    rcx, rcx
0x14000c6f4  jz      short loc_14000C733
0x14000c6f6  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c6fd  mov     edi, 3
0x14000c702  mov     r8d, edi
0x14000c705  xor     edx, edx
0x14000c707  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c70c  lea     rax, [rbp+var_20]
0x14000c710  mov     qword ptr [rbp+var_38], rax
0x14000c714  lea     rax, [rbp+var_38]
0x14000c718  mov     qword ptr [rsp+68h+var_48], rax
0x14000c71d  lea     r9, asc_14002D4FC; ": {}"
0x14000c724  mov     r8d, edi
0x14000c727  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c72e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c733  mov     edx, 11Ah
0x14000c738  jmp     short loc_14000C78B
0x14000c73a  mov     [rbp+var_20], esi
0x14000c73d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c744  test    rcx, rcx
0x14000c747  jz      short loc_14000C786
0x14000c749  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000c750  mov     edi, 3
0x14000c755  mov     r8d, edi
0x14000c758  xor     edx, edx
0x14000c75a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c75f  lea     rax, [rbp+var_20]
0x14000c763  mov     qword ptr [rbp+var_38], rax
0x14000c767  lea     rax, [rbp+var_38]
0x14000c76b  mov     qword ptr [rsp+68h+var_48], rax; int
0x14000c770  lea     r9, asc_14002D4FC; ": {}"
0x14000c777  mov     r8d, edi
0x14000c77a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c781  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c786  mov     edx, 119h; void *
0x14000c78b  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000c792  mov     r9d, esi; char *
0x14000c795  mov     rcx, [rbp+30h]; this
0x14000c799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c79e  mov     ebx, esi
0x14000c7a0  jmp     loc_14000C6C3
```
