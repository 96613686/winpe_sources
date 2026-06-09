# AddAccessSidToFileFromFileTemplate

- ea: `0x18005ffc8`
- end: `0x1800603c0`
- name: `AddAccessSidToFileFromFileTemplate`
- size: `1016`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR, PSID pSid, DWORD AccessMask)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800532d4`
- `0x180095950`
- `0x1801c1c0c`

## callees

- `0x180010cc0`
- `0x18004e2d4`
- `0x18005f6f0`
- `0x18005ffc8`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060390`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180060158`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006037f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180060158`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006037f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800601ba`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800601ba`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800602f3`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800602f3`

## string_xrefs

- `0x180060137`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x180060233`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x1800600f4`: `No sid specified`
- `0x180060091`: `No file template specified`
- `0x180060316`: `Could not set named security info for file`
- `0x18006026c`: `Could not get named security info Dacl for file`
- `0x1800601dd`: `Could not get named security info for file`

## pseudocode

```c
__int64 __fastcall AddAccessSidToFileFromFileTemplate(LPWSTR pObjectName, LPCWSTR a2, PSID pSid, DWORD AccessMask)
{
  int v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  int v11; // edx
  int v12; // edx
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // rax
  signed int NamedSecurityInfoW; // ebx
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // rdx
  int v19; // edi
  int v20; // edx
  int v21; // edx
  unsigned int v22; // eax
  unsigned int ppsidGroup; // [rsp+20h] [rbp-60h]
  unsigned int v24[2]; // [rsp+40h] [rbp-40h] BYREF
  PACL pDacl[2]; // [rsp+48h] [rbp-38h] BYREF
  PACL pAcl; // [rsp+58h] [rbp-28h] BYREF
  int v27; // [rsp+60h] [rbp-20h] BYREF
  int v28[2]; // [rsp+68h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  hMem = 0;
  pDacl[0] = 0;
  pDacl[1] = 0;
  pAcl = 0;
  if ( !pObjectName )
  {
    v8 = -2147024809;
    v27 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file specified");
      *(_QWORD *)v28 = &v27;
      LOBYTE(v9) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v28);
    }
    v10 = 203;
    goto LABEL_13;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    v27 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file template specified");
      *(_QWORD *)v28 = &v27;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v28);
    }
    v10 = 204;
    goto LABEL_13;
  }
  if ( !pSid )
  {
    v8 = -2147024809;
    v27 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No sid specified");
      *(_QWORD *)v28 = &v27;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v28);
    }
    v10 = 205;
    goto LABEL_13;
  }
  ppSecurityDescriptor = (PSECURITY_DESCRIPTOR *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&hMem);
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, ppSecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not get named security info for file");
      if ( NamedSecurityInfoW > 0 )
        v17 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
      else
        v17 = NamedSecurityInfoW;
      v27 = v17;
      LOBYTE(v16) = 1;
      *(_QWORD *)v24 = &v27;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {0}",
        (__int64)v24);
    }
    v18 = 218;
LABEL_25:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v18,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
           (const char *)(unsigned int)NamedSecurityInfoW,
           ppsidGroup);
    goto LABEL_14;
  }
  if ( !pAcl )
  {
    v8 = -2147467259;
    v28[0] = -2147467259;
    if ( LogAdapter::g_Logger )
    {
      v19 = (_DWORD)pAcl + 3;
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        (unsigned int)((_DWORD)pAcl + 3),
        "Could not get named security info Dacl for file");
      *(_QWORD *)v24 = v28;
      LOBYTE(v20) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v20,
        v19,
        (unsigned int)": {}",
        (__int64)v24);
    }
    v10 = 220;
    goto LABEL_13;
  }
  v8 = AddAccessSidToDacl(pSid, pAcl, AccessMask, (__int64)pDacl);
  if ( v8 < 0 )
  {
    v10 = 222;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
      (const char *)(unsigned int)v8,
      ppsidGroup);
LABEL_14:
    Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(pDacl);
    if ( hMem )
    {
      if ( LocalFree(hMem) )
      {
        GetLastError();
        __fastfail(7u);
      }
    }
    return (unsigned int)v8;
  }
  NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pDacl[0], 0);
  if ( NamedSecurityInfoW )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not set named security info for file");
      if ( NamedSecurityInfoW > 0 )
        v22 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
      else
        v22 = NamedSecurityInfoW;
      v28[0] = v22;
      LOBYTE(v21) = 1;
      *(_QWORD *)v24 = v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {0}",
        (__int64)v24);
    }
    v18 = 227;
    goto LABEL_25;
  }
  Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(pDacl);
  if ( hMem && LocalFree(hMem) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x18005ffc8  push    rbp
0x18005ffca  push    rbx
0x18005ffcb  push    rsi
0x18005ffcc  push    rdi
0x18005ffcd  push    r14
0x18005ffcf  mov     rbp, rsp
0x18005ffd2  sub     rsp, 80h
0x18005ffd9  mov     rax, cs:__security_cookie
0x18005ffe0  xor     rax, rsp
0x18005ffe3  mov     [rbp+var_8], rax
0x18005ffe7  mov     [rbp+hMem], 0
0x18005ffef  mov     r14d, r9d
0x18005fff2  mov     [rbp+pDacl], 0
0x18005fffa  mov     rdi, r8
0x18005fffd  mov     [rbp+var_30], 0
0x180060005  mov     rbx, rdx
0x180060008  mov     [rbp+pAcl], 0
0x180060010  mov     rsi, rcx
0x180060013  test    rcx, rcx
0x180060016  jnz     short loc_180060073
0x180060018  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006001f  mov     ebx, 80070057h
0x180060024  mov     [rbp+var_20], ebx
0x180060027  test    rcx, rcx
0x18006002a  jz      short loc_180060069
0x18006002c  lea     edi, [rsi+3]
0x18006002f  xor     edx, edx
0x180060031  mov     r8d, edi
0x180060034  lea     r9, aNoFileSpecifie; "No file specified"
0x18006003b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180060040  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180060047  lea     rax, [rbp+var_20]
0x18006004b  mov     qword ptr [rbp+var_18], rax
0x18006004f  lea     r9, asc_1802EE7AC; ": {}"
0x180060056  lea     rax, [rbp+var_18]
0x18006005a  mov     r8d, edi
0x18006005d  mov     dl, 1
0x18006005f  mov     [rsp+80h+ppsidGroup], rax
0x180060064  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180060069  mov     edx, 0CBh
0x18006006e  jmp     loc_180060133
0x180060073  test    rbx, rbx
0x180060076  jnz     short loc_1800600D2
0x180060078  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006007f  mov     ebx, 80070057h
0x180060084  mov     [rbp+var_20], ebx
0x180060087  test    rcx, rcx
0x18006008a  jz      short loc_1800600CB
0x18006008c  mov     edi, 3
0x180060091  lea     r9, aNoFileTemplate; "No file template specified"
0x180060098  mov     r8d, edi
0x18006009b  xor     edx, edx
0x18006009d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800600a2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800600a9  lea     rax, [rbp+var_20]
0x1800600ad  mov     qword ptr [rbp+var_18], rax
0x1800600b1  lea     r9, asc_1802EE7AC; ": {}"
0x1800600b8  lea     rax, [rbp+var_18]
0x1800600bc  mov     r8d, edi
0x1800600bf  mov     dl, 1
0x1800600c1  mov     [rsp+80h+ppsidGroup], rax
0x1800600c6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800600cb  mov     edx, 0CCh
0x1800600d0  jmp     short loc_180060133
0x1800600d2  test    rdi, rdi
0x1800600d5  jnz     loc_180060183
0x1800600db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800600e2  mov     ebx, 80070057h
0x1800600e7  mov     [rbp+var_20], ebx
0x1800600ea  test    rcx, rcx
0x1800600ed  jz      short loc_18006012E
0x1800600ef  mov     edi, 3
0x1800600f4  lea     r9, aNoSidSpecified; "No sid specified"
0x1800600fb  mov     r8d, edi
0x1800600fe  xor     edx, edx
0x180060100  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180060105  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006010c  lea     rax, [rbp+var_20]
0x180060110  mov     qword ptr [rbp+var_18], rax
0x180060114  lea     r9, asc_1802EE7AC; ": {}"
0x18006011b  lea     rax, [rbp+var_18]
0x18006011f  mov     r8d, edi
0x180060122  mov     dl, 1
0x180060124  mov     [rsp+80h+ppsidGroup], rax; int
0x180060129  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006012e  mov     edx, 0CDh; void *
0x180060133  mov     rcx, [rbp+28h]; this
0x180060137  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18006013e  mov     r9d, ebx; char *
0x180060141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060146  lea     rcx, [rbp+pDacl]
0x18006014a  call    ?Close@?$AutoPointerAndSizeBase@PEAU_ACL@@V?$AutoHeapBlockPtr@U_ACL@@@Windows@@@Windows@@QEAAXXZ; Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(void)
0x18006014f  mov     rcx, [rbp+hMem]; hMem
0x180060153  test    rcx, rcx
0x180060156  jz      short loc_18006017C
0x180060158  call    cs:__imp_LocalFree
0x18006015f  nop     dword ptr [rax+rax+00h]
0x180060164  test    rax, rax
0x180060167  jz      short loc_18006017C
0x180060169  call    cs:__imp_GetLastError
0x180060170  nop     dword ptr [rax+rax+00h]
0x180060175  mov     ecx, 7
0x18006017a  int     29h; Win8: RtlFailFast(ecx)
0x18006017c  mov     eax, ebx
0x18006017e  jmp     loc_1800603A5
0x180060183  lea     rcx, [rbp+hMem]
0x180060187  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18006018c  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180060191  xor     r9d, r9d; ppsidOwner
0x180060194  lea     rax, [rbp+pAcl]
0x180060198  mov     [rsp+80h+ppSacl], 0; ppSacl
0x1800601a1  mov     [rsp+80h+ppDacl], rax; ppDacl
0x1800601a6  mov     rcx, rbx; pObjectName
0x1800601a9  mov     [rsp+80h+ppsidGroup], 0; ppsidGroup
0x1800601b2  lea     edx, [r9+1]; ObjectType
0x1800601b6  lea     r8d, [r9+4]; SecurityInfo
0x1800601ba  call    cs:__imp_GetNamedSecurityInfoW
0x1800601c1  nop     dword ptr [rax+rax+00h]
0x1800601c6  mov     ebx, eax
0x1800601c8  test    eax, eax
0x1800601ca  jz      short loc_180060249
0x1800601cc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800601d3  test    rcx, rcx
0x1800601d6  jz      short loc_18006022A
0x1800601d8  mov     edi, 3
0x1800601dd  lea     r9, aCouldNotGetNam; "Could not get named security info for f"...
0x1800601e4  mov     r8d, edi
0x1800601e7  xor     edx, edx
0x1800601e9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800601ee  test    ebx, ebx
0x1800601f0  jg      short loc_1800601F6
0x1800601f2  mov     eax, ebx
0x1800601f4  jmp     short loc_1800601FE
0x1800601f6  movzx   eax, bx
0x1800601f9  or      eax, 80070000h
0x1800601fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180060205  lea     r9, a0; ": {0}"
0x18006020c  mov     [rbp+var_20], eax
0x18006020f  mov     r8d, edi
0x180060212  lea     rax, [rbp+var_20]
0x180060216  mov     dl, 1
0x180060218  mov     qword ptr [rbp+var_40], rax
0x18006021c  lea     rax, [rbp+var_40]
0x180060220  mov     [rsp+80h+ppsidGroup], rax; unsigned int
0x180060225  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006022a  mov     edx, 0DAh; void *
0x18006022f  mov     rcx, [rbp+28h]; this
0x180060233  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18006023a  mov     r9d, ebx; char *
0x18006023d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180060242  mov     ebx, eax
0x180060244  jmp     loc_180060146
0x180060249  mov     rdx, [rbp+pAcl]; pAcl
0x18006024d  test    rdx, rdx
0x180060250  jnz     short loc_1800602AB
0x180060252  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180060259  mov     ebx, 80004005h
0x18006025e  mov     [rbp+var_18], ebx
0x180060261  test    rcx, rcx
0x180060264  jz      short loc_1800602A1
0x180060266  lea     edi, [rdx+3]
0x180060269  mov     r8d, edi
0x18006026c  lea     r9, aCouldNotGetNam_0; "Could not get named security info Dacl "...
0x180060273  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180060278  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006027f  lea     rax, [rbp+var_18]
0x180060283  mov     qword ptr [rbp+var_40], rax
0x180060287  lea     r9, asc_1802EE7AC; ": {}"
0x18006028e  lea     rax, [rbp+var_40]
0x180060292  mov     r8d, edi
0x180060295  mov     dl, 1
0x180060297  mov     [rsp+80h+ppsidGroup], rax
0x18006029c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800602a1  mov     edx, 0DCh
0x1800602a6  jmp     loc_180060133
0x1800602ab  lea     r9, [rbp+pDacl]
0x1800602af  mov     r8d, r14d; AccessMask
0x1800602b2  mov     rcx, rdi; pSid
0x1800602b5  call    AddAccessSidToDacl
0x1800602ba  mov     ebx, eax
0x1800602bc  test    eax, eax
0x1800602be  jns     short loc_1800602CA
0x1800602c0  mov     edx, 0DEh
0x1800602c5  jmp     loc_180060133
0x1800602ca  mov     rax, [rbp+pDacl]
0x1800602ce  xor     r9d, r9d; psidOwner
0x1800602d1  mov     [rsp+80h+ppSacl], 0; pSacl
0x1800602da  mov     rcx, rsi; pObjectName
0x1800602dd  mov     [rsp+80h+ppDacl], rax; pDacl
0x1800602e2  mov     [rsp+80h+ppsidGroup], 0; psidGroup
0x1800602eb  lea     edx, [r9+1]; ObjectType
0x1800602ef  lea     r8d, [r9+4]; SecurityInfo
0x1800602f3  call    cs:__imp_SetNamedSecurityInfoW
0x1800602fa  nop     dword ptr [rax+rax+00h]
0x1800602ff  mov     ebx, eax
0x180060301  test    eax, eax
0x180060303  jz      short loc_18006036D
0x180060305  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006030c  test    rcx, rcx
0x18006030f  jz      short loc_180060363
0x180060311  mov     edi, 3
0x180060316  lea     r9, aCouldNotSetNam; "Could not set named security info for f"...
0x18006031d  mov     r8d, edi
0x180060320  xor     edx, edx
0x180060322  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180060327  test    ebx, ebx
0x180060329  jg      short loc_18006032F
0x18006032b  mov     eax, ebx
0x18006032d  jmp     short loc_180060337
0x18006032f  movzx   eax, bx
0x180060332  or      eax, 80070000h
0x180060337  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006033e  lea     r9, a0; ": {0}"
0x180060345  mov     [rbp+var_18], eax
0x180060348  mov     r8d, edi
0x18006034b  lea     rax, [rbp+var_18]
0x18006034f  mov     dl, 1
0x180060351  mov     qword ptr [rbp+var_40], rax
0x180060355  lea     rax, [rbp+var_40]
0x180060359  mov     [rsp+80h+ppsidGroup], rax
0x18006035e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180060363  mov     edx, 0E3h
0x180060368  jmp     loc_18006022F
0x18006036d  lea     rcx, [rbp+pDacl]
0x180060371  call    ?Close@?$AutoPointerAndSizeBase@PEAU_ACL@@V?$AutoHeapBlockPtr@U_ACL@@@Windows@@@Windows@@QEAAXXZ; Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(void)
0x180060376  mov     rcx, [rbp+hMem]; hMem
0x18006037a  test    rcx, rcx
0x18006037d  jz      short loc_1800603A3
0x18006037f  call    cs:__imp_LocalFree
0x180060386  nop     dword ptr [rax+rax+00h]
0x18006038b  test    rax, rax
0x18006038e  jz      short loc_1800603A3
0x180060390  call    cs:__imp_GetLastError
0x180060397  nop     dword ptr [rax+rax+00h]
0x18006039c  mov     ecx, 7
0x1800603a1  int     29h; Win8: RtlFailFast(ecx)
0x1800603a3  xor     eax, eax
0x1800603a5  mov     rcx, [rbp+var_8]
0x1800603a9  xor     rcx, rsp; StackCookie
0x1800603ac  call    __security_check_cookie
0x1800603b1  add     rsp, 80h
0x1800603b8  pop     r14
0x1800603ba  pop     rdi
0x1800603bb  pop     rsi
0x1800603bc  pop     rbx
0x1800603bd  pop     rbp
0x1800603be  retn
```
