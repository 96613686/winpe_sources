# AddAccessSidToDacl

- ea: `0x18005f6f0`
- end: `0x18005fc1b`
- name: `AddAccessSidToDacl`
- size: `1323`
- prototype: `__int64 __fastcall(PSID pSid, PACL pAcl, DWORD AccessMask)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005ffc8`

## callees

- `0x18004e2d4`
- `0x18005f6f0`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x18010ff7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb65`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18005fb55`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18005fb55`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005f974`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005f974`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18005fab1`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18005fab1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005fa0b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005fa0b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18005f888`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18005f888`
- `ntdll!RtlLengthSid` at `0x18005f932`
- `ntdll!RtlLengthSid` at `0x18005f932`

## string_xrefs

- `0x18005f85b`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x18005f919`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x18005f75c`: `No sid specified`
- `0x18005f9a3`: `Could not initialize ACL`
- `0x18005f8bb`: `Could not get file ACL info`
- `0x18005f818`: `No new ACL result specified`
- `0x18005f7b9`: `No dacl specified`
- `0x18005fb7f`: `Could not add access allowed to Dacl`

## pseudocode

```c
__int64 __fastcall AddAccessSidToDacl(PSID pSid, PACL pAcl, DWORD AccessMask, __int64 a4)
{
  unsigned int v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  int v11; // edx
  int v12; // edx
  signed int LastError; // ebx
  int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // rdx
  ULONG v17; // eax
  DWORD v18; // esi
  DWORD v19; // edx
  struct _ACL *v20; // rsi
  int v21; // edx
  unsigned int v22; // eax
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  unsigned int v26; // eax
  int v27; // edx
  unsigned int v28; // eax
  struct _ACL *v29; // rax
  __int64 v30; // rcx
  unsigned int nAceListLength; // [rsp+20h] [rbp-58h]
  unsigned int v33[2]; // [rsp+30h] [rbp-48h] BYREF
  PACL pAcla; // [rsp+38h] [rbp-40h] BYREF
  __int64 v35; // [rsp+40h] [rbp-38h]
  LPVOID pAce; // [rsp+48h] [rbp-30h] BYREF
  int v37; // [rsp+50h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+58h] [rbp-20h] BYREF
  int v39; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  pAce = 0;
  pAcla = 0;
  v35 = 0;
  pAclInformation = 0;
  v39 = 0;
  if ( !pSid )
  {
    v8 = -2147024809;
    v37 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No sid specified");
      *(_QWORD *)v33 = &v37;
      LOBYTE(v9) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v10 = 162;
    goto LABEL_13;
  }
  if ( !pAcl )
  {
    v8 = -2147024809;
    v37 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No dacl specified");
      *(_QWORD *)v33 = &v37;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v10 = 163;
    goto LABEL_13;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v37 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No new ACL result specified");
      *(_QWORD *)v33 = &v37;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v33);
    }
    v10 = 164;
    goto LABEL_13;
  }
  Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(a4);
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not get file ACL info");
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      else
        v15 = LastError;
      v37 = v15;
      LOBYTE(v14) = 1;
      *(_QWORD *)v33 = &v37;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {0}",
        (__int64)v33);
    }
    if ( LastError )
    {
      v16 = 170;
LABEL_22:
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v16,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
             (const char *)(unsigned int)LastError,
             nAceListLength);
      goto LABEL_59;
    }
    goto LABEL_58;
  }
  v17 = RtlLengthSid(pSid);
  v18 = v17 + HIDWORD(pAclInformation) + 8;
  if ( Windows::AutoHeapBlockPtr<_ACL>::AllocateBytes(&pAcla, v18) )
  {
    v19 = v18;
    v20 = pAcla;
    if ( InitializeAcl(pAcla, v19, 2u) )
    {
      if ( GetAce(pAcl, 0, &pAce) )
      {
        if ( AddAce(v20, 2u, 0, pAce, HIDWORD(pAclInformation) - 8) )
        {
          if ( AddAccessAllowedAceEx(v20, 2u, 3u, AccessMask, pSid) )
          {
            v29 = *(struct _ACL **)a4;
            v30 = v35;
            *(_QWORD *)a4 = v20;
            pAcla = v29;
            v35 = *(_QWORD *)(a4 + 8);
            *(_QWORD *)(a4 + 8) = v30;
          }
          else
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not add access allowed to Dacl");
              if ( LastError > 0 )
                v28 = (unsigned __int16)LastError | 0x80070000;
              else
                v28 = LastError;
              v37 = v28;
              LOBYTE(v27) = 1;
              *(_QWORD *)v33 = &v37;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v27,
                3,
                (unsigned int)": {0}",
                (__int64)v33);
            }
            if ( LastError )
            {
              v16 = 190;
              goto LABEL_22;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not add ACE");
            if ( LastError > 0 )
              v26 = (unsigned __int16)LastError | 0x80070000;
            else
              v26 = LastError;
            v37 = v26;
            LOBYTE(v25) = 1;
            *(_QWORD *)v33 = &v37;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v25,
              3,
              (unsigned int)": {0}",
              (__int64)v33);
          }
          if ( LastError )
          {
            v16 = 184;
            goto LABEL_22;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not get ACE");
          if ( LastError > 0 )
            v24 = (unsigned __int16)LastError | 0x80070000;
          else
            v24 = LastError;
          v37 = v24;
          LOBYTE(v23) = 1;
          *(_QWORD *)v33 = &v37;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v23,
            3,
            (unsigned int)": {0}",
            (__int64)v33);
        }
        if ( LastError )
        {
          v16 = 180;
          goto LABEL_22;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not initialize ACL");
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        else
          v22 = LastError;
        v37 = v22;
        LOBYTE(v21) = 1;
        *(_QWORD *)v33 = &v37;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v21,
          3,
          (unsigned int)": {0}",
          (__int64)v33);
      }
      if ( LastError )
      {
        v16 = 177;
        goto LABEL_22;
      }
    }
LABEL_58:
    v8 = 0;
    goto LABEL_59;
  }
  v8 = -2147024882;
  v10 = 175;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
    (const char *)v8,
    nAceListLength);
LABEL_59:
  Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(&pAcla);
  return v8;
}

```

## disassembly

```asm
0x18005f6f0  push    rbp
0x18005f6f2  push    rbx
0x18005f6f3  push    rsi
0x18005f6f4  push    rdi
0x18005f6f5  push    r14
0x18005f6f7  push    r15
0x18005f6f9  mov     rbp, rsp
0x18005f6fc  sub     rsp, 78h
0x18005f700  mov     rax, cs:__security_cookie
0x18005f707  xor     rax, rsp
0x18005f70a  mov     [rbp+var_10], rax
0x18005f70e  xor     eax, eax
0x18005f710  mov     [rbp+pAce], 0
0x18005f718  mov     [rbp+pAcl], 0
0x18005f720  mov     rbx, r9
0x18005f723  mov     [rbp+var_38], 0
0x18005f72b  mov     r15d, r8d
0x18005f72e  mov     [rbp+pAclInformation], rax
0x18005f732  mov     rdi, rdx
0x18005f735  mov     [rbp+var_18], eax
0x18005f738  mov     r14, rcx
0x18005f73b  test    rcx, rcx
0x18005f73e  jnz     short loc_18005F79B
0x18005f740  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f747  mov     ebx, 80070057h
0x18005f74c  mov     [rbp+var_28], ebx
0x18005f74f  test    rcx, rcx
0x18005f752  jz      short loc_18005F791
0x18005f754  lea     edi, [rax+3]
0x18005f757  xor     edx, edx
0x18005f759  mov     r8d, edi
0x18005f75c  lea     r9, aNoSidSpecified; "No sid specified"
0x18005f763  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005f768  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f76f  lea     rax, [rbp+var_28]
0x18005f773  mov     qword ptr [rbp+var_48], rax
0x18005f777  lea     r9, asc_1802EE7AC; ": {}"
0x18005f77e  lea     rax, [rbp+var_48]
0x18005f782  mov     r8d, edi
0x18005f785  mov     dl, 1
0x18005f787  mov     qword ptr [rsp+78h+nAceListLength], rax
0x18005f78c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005f791  mov     edx, 0A2h
0x18005f796  jmp     loc_18005F857
0x18005f79b  test    rdi, rdi
0x18005f79e  jnz     short loc_18005F7FA
0x18005f7a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f7a7  mov     ebx, 80070057h
0x18005f7ac  mov     [rbp+var_28], ebx
0x18005f7af  test    rcx, rcx
0x18005f7b2  jz      short loc_18005F7F3
0x18005f7b4  mov     edi, 3
0x18005f7b9  lea     r9, aNoDaclSpecifie; "No dacl specified"
0x18005f7c0  mov     r8d, edi
0x18005f7c3  xor     edx, edx
0x18005f7c5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005f7ca  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f7d1  lea     rax, [rbp+var_28]
0x18005f7d5  mov     qword ptr [rbp+var_48], rax
0x18005f7d9  lea     r9, asc_1802EE7AC; ": {}"
0x18005f7e0  lea     rax, [rbp+var_48]
0x18005f7e4  mov     r8d, edi
0x18005f7e7  mov     dl, 1
0x18005f7e9  mov     qword ptr [rsp+78h+nAceListLength], rax
0x18005f7ee  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005f7f3  mov     edx, 0A3h
0x18005f7f8  jmp     short loc_18005F857
0x18005f7fa  test    rbx, rbx
0x18005f7fd  jnz     short loc_18005F86F
0x18005f7ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f806  mov     ebx, 80004003h
0x18005f80b  mov     [rbp+var_28], ebx
0x18005f80e  test    rcx, rcx
0x18005f811  jz      short loc_18005F852
0x18005f813  mov     edi, 3
0x18005f818  lea     r9, aNoNewAclResult; "No new ACL result specified"
0x18005f81f  mov     r8d, edi
0x18005f822  xor     edx, edx
0x18005f824  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005f829  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f830  lea     rax, [rbp+var_28]
0x18005f834  mov     qword ptr [rbp+var_48], rax
0x18005f838  lea     r9, asc_1802EE7AC; ": {}"
0x18005f83f  lea     rax, [rbp+var_48]
0x18005f843  mov     r8d, edi
0x18005f846  mov     dl, 1
0x18005f848  mov     qword ptr [rsp+78h+nAceListLength], rax; int
0x18005f84d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005f852  mov     edx, 0A4h; void *
0x18005f857  mov     rcx, [rbp+30h]; this
0x18005f85b  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18005f862  mov     r9d, ebx; char *
0x18005f865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f86a  jmp     loc_18005FBF6
0x18005f86f  mov     rcx, rbx
0x18005f872  call    ?Close@?$AutoPointerAndSizeBase@PEAU_ACL@@V?$AutoHeapBlockPtr@U_ACL@@@Windows@@@Windows@@QEAAXXZ; Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(void)
0x18005f877  mov     r9d, 2; dwAclInformationClass
0x18005f87d  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18005f881  mov     rcx, rdi; pAcl
0x18005f884  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18005f888  call    cs:__imp_GetAclInformation
0x18005f88f  nop     dword ptr [rax+rax+00h]
0x18005f894  test    eax, eax
0x18005f896  jnz     loc_18005F92F
0x18005f89c  call    cs:__imp_GetLastError
0x18005f8a3  nop     dword ptr [rax+rax+00h]
0x18005f8a8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f8af  mov     ebx, eax
0x18005f8b1  test    rcx, rcx
0x18005f8b4  jz      short loc_18005F908
0x18005f8b6  mov     edi, 3
0x18005f8bb  lea     r9, aCouldNotGetFil; "Could not get file ACL info"
0x18005f8c2  mov     r8d, edi
0x18005f8c5  xor     edx, edx
0x18005f8c7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005f8cc  test    ebx, ebx
0x18005f8ce  jg      short loc_18005F8D4
0x18005f8d0  mov     eax, ebx
0x18005f8d2  jmp     short loc_18005F8DC
0x18005f8d4  movzx   eax, bx
0x18005f8d7  or      eax, 80070000h
0x18005f8dc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f8e3  lea     r9, a0; ": {0}"
0x18005f8ea  mov     [rbp+var_28], eax
0x18005f8ed  mov     r8d, edi
0x18005f8f0  lea     rax, [rbp+var_28]
0x18005f8f4  mov     dl, 1
0x18005f8f6  mov     qword ptr [rbp+var_48], rax
0x18005f8fa  lea     rax, [rbp+var_48]
0x18005f8fe  mov     qword ptr [rsp+78h+nAceListLength], rax; unsigned int
0x18005f903  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005f908  test    ebx, ebx
0x18005f90a  jz      loc_18005FBF4
0x18005f910  mov     edx, 0AAh; void *
0x18005f915  mov     rcx, [rbp+30h]; this
0x18005f919  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18005f920  mov     r9d, ebx; char *
0x18005f923  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005f928  mov     ebx, eax
0x18005f92a  jmp     loc_18005FBF6
0x18005f92f  mov     rcx, r14; Sid
0x18005f932  call    cs:__imp_RtlLengthSid
0x18005f939  nop     dword ptr [rax+rax+00h]
0x18005f93e  mov     esi, dword ptr [rbp+pAclInformation+4]
0x18005f941  lea     rcx, [rbp+pAcl]
0x18005f945  add     esi, 8
0x18005f948  add     esi, eax
0x18005f94a  mov     edx, esi
0x18005f94c  call    ?AllocateBytes@?$AutoHeapBlockPtr@U_ACL@@@Windows@@QEAAPEAU_ACL@@_K@Z; Windows::AutoHeapBlockPtr<_ACL>::AllocateBytes(unsigned __int64)
0x18005f951  test    rax, rax
0x18005f954  jnz     short loc_18005F965
0x18005f956  mov     ebx, 8007000Eh
0x18005f95b  mov     edx, 0AFh
0x18005f960  jmp     loc_18005F857
0x18005f965  mov     edx, esi; nAclLength
0x18005f967  mov     r8d, 2; dwAclRevision
0x18005f96d  mov     rsi, [rbp+pAcl]
0x18005f971  mov     rcx, rsi; pAcl
0x18005f974  call    cs:__imp_InitializeAcl
0x18005f97b  nop     dword ptr [rax+rax+00h]
0x18005f980  test    eax, eax
0x18005f982  jnz     short loc_18005FA02
0x18005f984  call    cs:__imp_GetLastError
0x18005f98b  nop     dword ptr [rax+rax+00h]
0x18005f990  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f997  mov     ebx, eax
0x18005f999  test    rcx, rcx
0x18005f99c  jz      short loc_18005F9F0
0x18005f99e  mov     edi, 3
0x18005f9a3  lea     r9, aCouldNotInitia; "Could not initialize ACL"
0x18005f9aa  mov     r8d, edi
0x18005f9ad  xor     edx, edx
0x18005f9af  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005f9b4  test    ebx, ebx
0x18005f9b6  jg      short loc_18005F9BC
0x18005f9b8  mov     eax, ebx
0x18005f9ba  jmp     short loc_18005F9C4
0x18005f9bc  movzx   eax, bx
0x18005f9bf  or      eax, 80070000h
0x18005f9c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005f9cb  lea     r9, a0; ": {0}"
0x18005f9d2  mov     [rbp+var_28], eax
0x18005f9d5  mov     r8d, edi
0x18005f9d8  lea     rax, [rbp+var_28]
0x18005f9dc  mov     dl, 1
0x18005f9de  mov     qword ptr [rbp+var_48], rax
0x18005f9e2  lea     rax, [rbp+var_48]
0x18005f9e6  mov     qword ptr [rsp+78h+nAceListLength], rax
0x18005f9eb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005f9f0  test    ebx, ebx
0x18005f9f2  jz      loc_18005FBF4
0x18005f9f8  mov     edx, 0B1h
0x18005f9fd  jmp     loc_18005F915
0x18005fa02  lea     r8, [rbp+pAce]; pAce
0x18005fa06  xor     edx, edx; dwAceIndex
0x18005fa08  mov     rcx, rdi; pAcl
0x18005fa0b  call    cs:__imp_GetAce
0x18005fa12  nop     dword ptr [rax+rax+00h]
0x18005fa17  test    eax, eax
0x18005fa19  jnz     short loc_18005FA99
0x18005fa1b  call    cs:__imp_GetLastError
0x18005fa22  nop     dword ptr [rax+rax+00h]
0x18005fa27  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fa2e  mov     ebx, eax
0x18005fa30  test    rcx, rcx
0x18005fa33  jz      short loc_18005FA87
0x18005fa35  mov     edi, 3
0x18005fa3a  lea     r9, aCouldNotGetAce; "Could not get ACE"
0x18005fa41  mov     r8d, edi
0x18005fa44  xor     edx, edx
0x18005fa46  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005fa4b  test    ebx, ebx
0x18005fa4d  jg      short loc_18005FA53
0x18005fa4f  mov     eax, ebx
0x18005fa51  jmp     short loc_18005FA5B
0x18005fa53  movzx   eax, bx
0x18005fa56  or      eax, 80070000h
0x18005fa5b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fa62  lea     r9, a0; ": {0}"
0x18005fa69  mov     [rbp+var_28], eax
0x18005fa6c  mov     r8d, edi
0x18005fa6f  lea     rax, [rbp+var_28]
0x18005fa73  mov     dl, 1
0x18005fa75  mov     qword ptr [rbp+var_48], rax
0x18005fa79  lea     rax, [rbp+var_48]
0x18005fa7d  mov     qword ptr [rsp+78h+nAceListLength], rax
0x18005fa82  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005fa87  test    ebx, ebx
0x18005fa89  jz      loc_18005FBF4
0x18005fa8f  mov     edx, 0B4h
0x18005fa94  jmp     loc_18005F915
0x18005fa99  mov     eax, dword ptr [rbp+pAclInformation+4]
0x18005fa9c  xor     r8d, r8d; dwStartingAceIndex
0x18005fa9f  mov     r9, [rbp+pAce]; pAceList
0x18005faa3  add     eax, 0FFFFFFF8h
0x18005faa6  mov     rcx, rsi; pAcl
0x18005faa9  mov     [rsp+78h+nAceListLength], eax; nAceListLength
0x18005faad  lea     edx, [r8+2]; dwAceRevision
0x18005fab1  call    cs:__imp_AddAce
0x18005fab8  nop     dword ptr [rax+rax+00h]
0x18005fabd  test    eax, eax
0x18005fabf  jnz     short loc_18005FB3F
0x18005fac1  call    cs:__imp_GetLastError
0x18005fac8  nop     dword ptr [rax+rax+00h]
0x18005facd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fad4  mov     ebx, eax
0x18005fad6  test    rcx, rcx
0x18005fad9  jz      short loc_18005FB2D
0x18005fadb  mov     edi, 3
0x18005fae0  lea     r9, aCouldNotAddAce; "Could not add ACE"
0x18005fae7  mov     r8d, edi
0x18005faea  xor     edx, edx
0x18005faec  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005faf1  test    ebx, ebx
0x18005faf3  jg      short loc_18005FAF9
0x18005faf5  mov     eax, ebx
0x18005faf7  jmp     short loc_18005FB01
0x18005faf9  movzx   eax, bx
0x18005fafc  or      eax, 80070000h
0x18005fb01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fb08  lea     r9, a0; ": {0}"
0x18005fb0f  mov     [rbp+var_28], eax
0x18005fb12  mov     r8d, edi
0x18005fb15  lea     rax, [rbp+var_28]
0x18005fb19  mov     dl, 1
0x18005fb1b  mov     qword ptr [rbp+var_48], rax
0x18005fb1f  lea     rax, [rbp+var_48]
0x18005fb23  mov     qword ptr [rsp+78h+nAceListLength], rax
0x18005fb28  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005fb2d  test    ebx, ebx
0x18005fb2f  jz      loc_18005FBF4
0x18005fb35  mov     edx, 0B8h
0x18005fb3a  jmp     loc_18005F915
0x18005fb3f  mov     edi, 3
0x18005fb44  mov     qword ptr [rsp+78h+nAceListLength], r14; pSid
0x18005fb49  mov     r9d, r15d; AccessMask
0x18005fb4c  mov     r8d, edi; AceFlags
0x18005fb4f  mov     rcx, rsi; pAcl
0x18005fb52  lea     edx, [rdi-1]; dwAceRevision
0x18005fb55  call    cs:__imp_AddAccessAllowedAceEx
0x18005fb5c  nop     dword ptr [rax+rax+00h]
0x18005fb61  test    eax, eax
0x18005fb63  jnz     short loc_18005FBDA
0x18005fb65  call    cs:__imp_GetLastError
0x18005fb6c  nop     dword ptr [rax+rax+00h]
0x18005fb71  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fb78  mov     ebx, eax
0x18005fb7a  test    rcx, rcx
0x18005fb7d  jz      short loc_18005FBCC
0x18005fb7f  lea     r9, aCouldNotAddAcc; "Could not add access allowed to Dacl"
0x18005fb86  mov     r8d, edi
0x18005fb89  xor     edx, edx
0x18005fb8b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005fb90  test    ebx, ebx
0x18005fb92  jg      short loc_18005FB98
0x18005fb94  mov     eax, ebx
0x18005fb96  jmp     short loc_18005FBA0
0x18005fb98  movzx   eax, bx
0x18005fb9b  or      eax, 80070000h
0x18005fba0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
  ... truncated ...
```
