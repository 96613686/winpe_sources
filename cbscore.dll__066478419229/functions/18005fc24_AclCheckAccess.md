# AclCheckAccess

- ea: `0x18005fc24`
- end: `0x18005ffc0`
- name: `AclCheckAccess`
- size: `924`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005e64c`

## callees

- `0x18005fc24`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fe47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fe47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fef9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005fee5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005fee5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005ff94`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005ff94`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005fe33`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005fe33`

## string_xrefs

- `0x18005fcaa`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x18005feba`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x18005ff6c`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x18005fcd9`: `Invalid ACL; DenyAccess must not be specified`
- `0x18005fc65`: `No ACL specified`
- `0x18005fe63`: `Failed to allocate SID to check membership.`
- `0x18005fda3`: `Failed to get SID for account: {}`
- `0x18005fd38`: `Invalid ACL; dwAccessMask must not be specified`

## pseudocode

```c
int __fastcall AclCheckAccess(HANDLE TokenHandle, __int64 a2)
{
  unsigned int v3; // ebx
  int v4; // edx
  __int64 v5; // rdx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  DWORD v9; // r9d
  DWORD v10; // r8d
  struct _SID_IDENTIFIER_AUTHORITY *v11; // rcx
  DWORD v12; // eax
  BYTE v13; // dl
  signed int v14; // ebx
  int v15; // edx
  unsigned int v16; // eax
  signed int LastError; // ebx
  int v19; // edx
  unsigned int v20; // eax
  int v21; // eax
  int nSubAuthority2; // [rsp+20h] [rbp-60h]
  unsigned int nSubAuthority2a; // [rsp+20h] [rbp-60h]
  DWORD nSubAuthority3; // [rsp+28h] [rbp-58h]
  DWORD nSubAuthority4; // [rsp+30h] [rbp-50h]
  DWORD nSubAuthority5; // [rsp+38h] [rbp-48h]
  DWORD nSubAuthority6; // [rsp+40h] [rbp-40h]
  DWORD nSubAuthority7; // [rsp+48h] [rbp-38h]
  unsigned int v29[2]; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  int v31; // [rsp+70h] [rbp-10h] BYREF
  WINBOOL IsMember; // [rsp+74h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  IsMember = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v31 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No ACL specified");
      *(_QWORD *)v29 = &v31;
      LOBYTE(v4) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)v29);
    }
    v5 = 71;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
      (const char *)v3,
      nSubAuthority2);
    return v3;
  }
  if ( *(_DWORD *)a2 )
  {
    v3 = -2147024809;
    v31 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid ACL; DenyAccess must not be specified");
      *(_QWORD *)v29 = &v31;
      LOBYTE(v6) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)v29);
    }
    v5 = 72;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(a2 + 4) )
  {
    v3 = -2147024809;
    v31 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid ACL; dwAccessMask must not be specified");
      *(_QWORD *)v29 = &v31;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v29);
    }
    v5 = 73;
    goto LABEL_5;
  }
  if ( *(_QWORD *)(a2 + 8) )
  {
    v3 = -2147467263;
    v31 = -2147467263;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to get SID for account: {}",
        a2 + 8);
      *(_QWORD *)v29 = &v31;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v29);
    }
    v5 = 77;
    goto LABEL_5;
  }
  v9 = *(_DWORD *)(a2 + 28);
  v10 = *(_DWORD *)(a2 + 24);
  v11 = (struct _SID_IDENTIFIER_AUTHORITY *)(a2 + 16);
  nSubAuthority7 = *(_DWORD *)(a2 + 52);
  nSubAuthority6 = *(_DWORD *)(a2 + 48);
  nSubAuthority5 = *(_DWORD *)(a2 + 44);
  nSubAuthority4 = *(_DWORD *)(a2 + 40);
  nSubAuthority3 = *(_DWORD *)(a2 + 36);
  v12 = *(_DWORD *)(a2 + 32);
  v13 = *(_BYTE *)(a2 + 22);
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(
         v11,
         v13,
         v10,
         v9,
         v12,
         nSubAuthority3,
         nSubAuthority4,
         nSubAuthority5,
         nSubAuthority6,
         nSubAuthority7,
         &SidToCheck) )
  {
    if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
    {
      v21 = IsMember == 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to check membership");
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        else
          v20 = LastError;
        v31 = v20;
        LOBYTE(v19) = 1;
        *(_QWORD *)v29 = &v31;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v19,
          3,
          (unsigned int)": {0}",
          (__int64)v29);
      }
      if ( !LastError )
      {
        v3 = 0;
LABEL_38:
        FreeSid(SidToCheck);
        return v3;
      }
      v21 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x63,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
              (const char *)(unsigned int)LastError,
              nSubAuthority2a);
    }
    v3 = v21;
    goto LABEL_38;
  }
  v14 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate SID to check membership.");
    if ( v14 > 0 )
      v16 = (unsigned __int16)v14 | 0x80070000;
    else
      v16 = v14;
    v31 = v16;
    LOBYTE(v15) = 1;
    *(_QWORD *)v29 = &v31;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v15,
      3,
      (unsigned int)": {0}",
      (__int64)v29);
  }
  if ( v14 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x5E,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
             (const char *)(unsigned int)v14,
             nSubAuthority2a);
  else
    return 0;
}

```

## disassembly

```asm
0x18005fc24  mov     [rsp-8+arg_10], rbx
0x18005fc29  push    rbp
0x18005fc2a  mov     rbp, rsp
0x18005fc2d  sub     rsp, 80h
0x18005fc34  mov     rax, cs:__security_cookie
0x18005fc3b  xor     rax, rsp
0x18005fc3e  mov     [rbp+var_8], rax
0x18005fc42  mov     [rbp+IsMember], 0
0x18005fc49  mov     rbx, rcx
0x18005fc4c  test    rdx, rdx
0x18005fc4f  jnz     short loc_18005FCBE
0x18005fc51  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fc58  mov     ebx, 80070057h
0x18005fc5d  mov     [rbp+var_10], ebx
0x18005fc60  test    rcx, rcx
0x18005fc63  jz      short loc_18005FCA1
0x18005fc65  lea     r9, aNoAclSpecified; "No ACL specified"
0x18005fc6c  lea     r8d, [rdx+3]
0x18005fc70  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005fc75  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fc7c  lea     rax, [rbp+var_10]
0x18005fc80  mov     qword ptr [rbp+var_20], rax
0x18005fc84  lea     r9, asc_1802EE7AC; ": {}"
0x18005fc8b  lea     rax, [rbp+var_20]
0x18005fc8f  mov     r8d, 3
0x18005fc95  mov     dl, 1
0x18005fc97  mov     qword ptr [rsp+80h+nSubAuthority2], rax; int
0x18005fc9c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005fca1  mov     edx, 47h ; 'G'; void *
0x18005fca6  mov     rcx, [rbp+8]; this
0x18005fcaa  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18005fcb1  mov     r9d, ebx; char *
0x18005fcb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fcb9  jmp     loc_18005FFA0
0x18005fcbe  cmp     dword ptr [rdx], 0
0x18005fcc1  jz      short loc_18005FD1C
0x18005fcc3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fcca  mov     ebx, 80070057h
0x18005fccf  mov     [rbp+var_10], ebx
0x18005fcd2  test    rcx, rcx
0x18005fcd5  jz      short loc_18005FD15
0x18005fcd7  xor     edx, edx
0x18005fcd9  lea     r9, aInvalidAclDeny; "Invalid ACL; DenyAccess must not be spe"...
0x18005fce0  lea     r8d, [rdx+3]
0x18005fce4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005fce9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fcf0  lea     rax, [rbp+var_10]
0x18005fcf4  mov     qword ptr [rbp+var_20], rax
0x18005fcf8  lea     r9, asc_1802EE7AC; ": {}"
0x18005fcff  lea     rax, [rbp+var_20]
0x18005fd03  mov     r8d, 3
0x18005fd09  mov     dl, 1
0x18005fd0b  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x18005fd10  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005fd15  mov     edx, 48h ; 'H'
0x18005fd1a  jmp     short loc_18005FCA6
0x18005fd1c  cmp     dword ptr [rdx+4], 0
0x18005fd20  jz      short loc_18005FD7E
0x18005fd22  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fd29  mov     ebx, 80070057h
0x18005fd2e  mov     [rbp+var_10], ebx
0x18005fd31  test    rcx, rcx
0x18005fd34  jz      short loc_18005FD74
0x18005fd36  xor     edx, edx
0x18005fd38  lea     r9, aInvalidAclDwac; "Invalid ACL; dwAccessMask must not be s"...
0x18005fd3f  lea     r8d, [rdx+3]
0x18005fd43  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005fd48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fd4f  lea     rax, [rbp+var_10]
0x18005fd53  mov     qword ptr [rbp+var_20], rax
0x18005fd57  lea     r9, asc_1802EE7AC; ": {}"
0x18005fd5e  lea     rax, [rbp+var_20]
0x18005fd62  mov     r8d, 3
0x18005fd68  mov     dl, 1
0x18005fd6a  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x18005fd6f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005fd74  mov     edx, 49h ; 'I'
0x18005fd79  jmp     loc_18005FCA6
0x18005fd7e  lea     rax, [rdx+8]
0x18005fd82  cmp     qword ptr [rax], 0
0x18005fd86  jz      short loc_18005FDE9
0x18005fd88  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fd8f  mov     ebx, 80004001h
0x18005fd94  mov     [rbp+var_10], ebx
0x18005fd97  test    rcx, rcx
0x18005fd9a  jz      short loc_18005FDDF
0x18005fd9c  xor     edx, edx
0x18005fd9e  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x18005fda3  lea     r9, aFailedToGetSid_2; "Failed to get SID for account: {}"
0x18005fdaa  lea     r8d, [rdx+3]
0x18005fdae  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18005fdb3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fdba  lea     rax, [rbp+var_10]
0x18005fdbe  mov     qword ptr [rbp+var_20], rax
0x18005fdc2  lea     r9, asc_1802EE7AC; ": {}"
0x18005fdc9  lea     rax, [rbp+var_20]
0x18005fdcd  mov     r8d, 3
0x18005fdd3  mov     dl, 1
0x18005fdd5  mov     qword ptr [rsp+80h+nSubAuthority2], rax
0x18005fdda  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005fddf  mov     edx, 4Dh ; 'M'
0x18005fde4  jmp     loc_18005FCA6
0x18005fde9  mov     r9d, [rdx+1Ch]; nSubAuthority1
0x18005fded  lea     rax, [rbp+SidToCheck]
0x18005fdf1  mov     r8d, [rdx+18h]; nSubAuthority0
0x18005fdf5  lea     rcx, [rdx+10h]; pIdentifierAuthority
0x18005fdf9  mov     [rsp+80h+pSid], rax; pSid
0x18005fdfe  mov     eax, [rdx+34h]
0x18005fe01  mov     [rsp+80h+nSubAuthority7], eax; nSubAuthority7
0x18005fe05  mov     eax, [rdx+30h]
0x18005fe08  mov     [rsp+80h+nSubAuthority6], eax; nSubAuthority6
0x18005fe0c  mov     eax, [rdx+2Ch]
0x18005fe0f  mov     [rsp+80h+nSubAuthority5], eax; nSubAuthority5
0x18005fe13  mov     eax, [rdx+28h]
0x18005fe16  mov     [rsp+80h+nSubAuthority4], eax; nSubAuthority4
0x18005fe1a  mov     eax, [rdx+24h]
0x18005fe1d  mov     [rsp+80h+nSubAuthority3], eax; nSubAuthority3
0x18005fe21  mov     eax, [rdx+20h]
0x18005fe24  mov     dl, [rdx+16h]; nSubAuthorityCount
0x18005fe27  mov     [rbp+SidToCheck], 0
0x18005fe2f  mov     [rsp+80h+nSubAuthority2], eax; nSubAuthority2
0x18005fe33  call    cs:__imp_AllocateAndInitializeSid
0x18005fe3a  nop     dword ptr [rax+rax+00h]
0x18005fe3f  test    eax, eax
0x18005fe41  jnz     loc_18005FEDA
0x18005fe47  call    cs:__imp_GetLastError
0x18005fe4e  nop     dword ptr [rax+rax+00h]
0x18005fe53  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fe5a  mov     ebx, eax
0x18005fe5c  test    rcx, rcx
0x18005fe5f  jz      short loc_18005FEB2
0x18005fe61  xor     edx, edx
0x18005fe63  lea     r9, aFailedToAlloca_21; "Failed to allocate SID to check members"...
0x18005fe6a  lea     r8d, [rdx+3]
0x18005fe6e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005fe73  test    ebx, ebx
0x18005fe75  jg      short loc_18005FE7B
0x18005fe77  mov     eax, ebx
0x18005fe79  jmp     short loc_18005FE83
0x18005fe7b  movzx   eax, bx
0x18005fe7e  or      eax, 80070000h
0x18005fe83  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005fe8a  lea     r9, a0; ": {0}"
0x18005fe91  mov     [rbp+var_10], eax
0x18005fe94  mov     r8d, 3
0x18005fe9a  lea     rax, [rbp+var_10]
0x18005fe9e  mov     dl, 1
0x18005fea0  mov     qword ptr [rbp+var_20], rax
0x18005fea4  lea     rax, [rbp+var_20]
0x18005fea8  mov     qword ptr [rsp+80h+nSubAuthority2], rax; unsigned int
0x18005fead  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005feb2  test    ebx, ebx
0x18005feb4  jz      short loc_18005FED3
0x18005feb6  mov     rcx, [rbp+8]; this
0x18005feba  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18005fec1  mov     r9d, ebx; char *
0x18005fec4  mov     edx, 5Eh ; '^'; void *
0x18005fec9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005fece  jmp     loc_18005FFA2
0x18005fed3  xor     eax, eax
0x18005fed5  jmp     loc_18005FFA2
0x18005feda  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18005fede  lea     r8, [rbp+IsMember]; IsMember
0x18005fee2  mov     rcx, rbx; TokenHandle
0x18005fee5  call    cs:__imp_CheckTokenMembership
0x18005feec  nop     dword ptr [rax+rax+00h]
0x18005fef1  test    eax, eax
0x18005fef3  jnz     loc_18005FF86
0x18005fef9  call    cs:__imp_GetLastError
0x18005ff00  nop     dword ptr [rax+rax+00h]
0x18005ff05  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ff0c  mov     ebx, eax
0x18005ff0e  test    rcx, rcx
0x18005ff11  jz      short loc_18005FF64
0x18005ff13  xor     edx, edx
0x18005ff15  lea     r9, aFailedToCheckM; "Failed to check membership"
0x18005ff1c  lea     r8d, [rdx+3]
0x18005ff20  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005ff25  test    ebx, ebx
0x18005ff27  jg      short loc_18005FF2D
0x18005ff29  mov     eax, ebx
0x18005ff2b  jmp     short loc_18005FF35
0x18005ff2d  movzx   eax, bx
0x18005ff30  or      eax, 80070000h
0x18005ff35  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005ff3c  lea     r9, a0; ": {0}"
0x18005ff43  mov     [rbp+var_10], eax
0x18005ff46  mov     r8d, 3
0x18005ff4c  lea     rax, [rbp+var_10]
0x18005ff50  mov     dl, 1
0x18005ff52  mov     qword ptr [rbp+var_20], rax
0x18005ff56  lea     rax, [rbp+var_20]
0x18005ff5a  mov     qword ptr [rsp+80h+nSubAuthority2], rax; unsigned int
0x18005ff5f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18005ff64  test    ebx, ebx
0x18005ff66  jz      short loc_18005FF82
0x18005ff68  mov     rcx, [rbp+8]; this
0x18005ff6c  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18005ff73  mov     r9d, ebx; char *
0x18005ff76  mov     edx, 63h ; 'c'; void *
0x18005ff7b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005ff80  jmp     short loc_18005FF8E
0x18005ff82  xor     ebx, ebx
0x18005ff84  jmp     short loc_18005FF90
0x18005ff86  xor     eax, eax
0x18005ff88  cmp     [rbp+IsMember], eax
0x18005ff8b  setz    al
0x18005ff8e  mov     ebx, eax
0x18005ff90  mov     rcx, [rbp+SidToCheck]; pSid
0x18005ff94  call    cs:__imp_FreeSid
0x18005ff9b  nop     dword ptr [rax+rax+00h]
0x18005ffa0  mov     eax, ebx
0x18005ffa2  mov     rcx, [rbp+var_8]
0x18005ffa6  xor     rcx, rsp; StackCookie
0x18005ffa9  call    __security_check_cookie
0x18005ffae  mov     rbx, [rsp+80h+arg_10]
0x18005ffb6  add     rsp, 80h
0x18005ffbd  pop     rbp
0x18005ffbe  retn
```
