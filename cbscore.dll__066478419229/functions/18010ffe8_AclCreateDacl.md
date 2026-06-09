# AclCreateDacl

- ea: `0x18010ffe8`
- end: `0x180110314`
- name: `AclCreateDacl`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005857c`

## callees

- `0x18004f454`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800f19ec`
- `0x1801026fc`
- `0x18010ffe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801100e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011026f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801100e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011026f`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x1801101b9`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x1801101b9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180110193`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180110193`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801100cf`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801100cf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011008c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18011008c`

## string_xrefs

- `0x180110102`: `failed to initialize ACL`
- `0x18011006d`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x180110223`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x1801102f5`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x1801101e5`: `AclCreateDacl() - created invalid ACL`
- `0x18011029a`: `failed to add access allowed ACE #{} to ACL`

## pseudocode

```c
__int64 __fastcall AclCreateDacl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, struct _ACL **a5)
{
  unsigned int v6; // ebx
  int v7; // edx
  DWORD LengthSid; // eax
  DWORD v10; // esi
  __int64 v11; // rdx
  struct _ACL *v12; // rbx
  signed int LastError; // ebx
  int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned int v18; // ecx
  int v19; // edx
  int v20; // edx
  unsigned int v21; // eax
  unsigned int pSid; // [rsp+20h] [rbp-40h]
  PACL pAcl; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v24[2]; // [rsp+38h] [rbp-28h] BYREF
  int v25; // [rsp+40h] [rbp-20h] BYREF
  int *v26; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( !a3 )
  {
    v6 = -2147024809;
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid parameter 'cAllow'.");
      pAcl = (PACL)&v25;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)&pAcl);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
      (const char *)0x80070057LL,
      pSid);
    return v6;
  }
  LengthSid = GetLengthSid(*(PSID *)(a3 + 8));
  pAcl = 0;
  v10 = LengthSid + 16;
  if ( !Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(&pAcl, LengthSid + 16) )
  {
    v6 = -2147024882;
    v11 = 30;
    goto LABEL_24;
  }
  v12 = pAcl;
  if ( !InitializeAcl(pAcl, v10, 2u) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "failed to initialize ACL");
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      else
        v15 = LastError;
      v25 = v15;
      LOBYTE(v14) = 1;
      v26 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {0}",
        (__int64)&v26);
    }
    if ( !LastError )
    {
      v6 = 0;
      goto LABEL_35;
    }
    v16 = 33;
    goto LABEL_34;
  }
  v17 = 0;
  v25 = 0;
  v18 = 0;
  do
  {
    if ( !AddAccessAllowedAceEx(
            v12,
            2u,
            *(_DWORD *)(a3 + 16LL * v18),
            *(_DWORD *)(a3 + 16LL * v18 + 4),
            *(PSID *)(a3 + 16 * v17 + 8)) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<unsigned long>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"failed to add access allowed ACE #{} to ACL",
          (__int64)&v25);
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        else
          v21 = LastError;
        LODWORD(v26) = v21;
        LOBYTE(v20) = 1;
        *(_QWORD *)v24 = &v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v20,
          3,
          (unsigned int)": {0}",
          (__int64)v24);
      }
      if ( LastError )
      {
        v16 = 46;
LABEL_34:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v16,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
               (const char *)(unsigned int)LastError,
               pSid);
        goto LABEL_35;
      }
LABEL_26:
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&pAcl);
      return 0;
    }
    v17 = (unsigned int)(v25 + 1);
    v25 = v17;
    v18 = v17;
  }
  while ( !(_DWORD)v17 );
  if ( IsValidAcl(v12) )
  {
    *a5 = v12;
    pAcl = 0;
    goto LABEL_26;
  }
  v6 = -2146498560;
  LODWORD(v26) = -2146498560;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "AclCreateDacl() - created invalid ACL");
    *(_QWORD *)v24 = &v26;
    LOBYTE(v19) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v19,
      3,
      (unsigned int)": {}",
      (__int64)v24);
  }
  v11 = 49;
LABEL_24:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
    (const char *)v6,
    pSid);
LABEL_35:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&pAcl);
  return v6;
}

```

## disassembly

```asm
0x18010ffe8  mov     [rsp-18h+arg_0], rbx
0x18010ffed  mov     [rsp-18h+arg_8], rsi
0x18010fff2  push    rbp
0x18010fff3  push    rdi
0x18010fff4  push    r14
0x18010fff6  mov     rbp, rsp
0x18010fff9  sub     rsp, 60h
0x18010fffd  mov     rax, cs:__security_cookie
0x180110004  xor     rax, rsp
0x180110007  mov     [rbp+var_10], rax
0x18011000b  mov     r14, [rbp+arg_20]
0x18011000f  mov     rdi, r8
0x180110012  test    r8, r8
0x180110015  jnz     short loc_180110088
0x180110017  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011001e  mov     ebx, 80070057h
0x180110023  mov     [rbp+var_20], ebx
0x180110026  test    rcx, rcx
0x180110029  jz      short loc_180110069
0x18011002b  lea     edi, [r8+3]
0x18011002f  xor     edx, edx
0x180110031  mov     r8d, edi
0x180110034  lea     r9, aInvalidParamet_14; "Invalid parameter 'cAllow'."
0x18011003b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180110040  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180110047  lea     rax, [rbp+var_20]
0x18011004b  mov     [rbp+pAcl], rax
0x18011004f  lea     r9, asc_1802EE7AC; ": {}"
0x180110056  lea     rax, [rbp+pAcl]
0x18011005a  mov     r8d, edi
0x18011005d  mov     dl, 1
0x18011005f  mov     qword ptr [rsp+60h+pSid], rax; int
0x180110064  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180110069  mov     rcx, [rbp+18h]; this
0x18011006d  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x180110074  mov     r9d, ebx; char *
0x180110077  mov     edx, 0Fh; void *
0x18011007c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110081  mov     eax, ebx
0x180110083  jmp     loc_18011024D
0x180110088  mov     rcx, [r8+8]; pSid
0x18011008c  call    cs:__imp_GetLengthSid
0x180110093  nop     dword ptr [rax+rax+00h]
0x180110098  lea     rcx, [rbp+pAcl]
0x18011009c  mov     [rbp+pAcl], 0
0x1801100a4  lea     esi, [rax+10h]
0x1801100a7  mov     edx, esi
0x1801100a9  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x1801100ae  test    rax, rax
0x1801100b1  jnz     short loc_1801100C0
0x1801100b3  mov     ebx, 8007000Eh
0x1801100b8  lea     edx, [rax+1Eh]
0x1801100bb  jmp     loc_18011021F
0x1801100c0  mov     rbx, [rbp+pAcl]
0x1801100c4  mov     r8d, 2; dwAclRevision
0x1801100ca  mov     rcx, rbx; pAcl
0x1801100cd  mov     edx, esi; nAclLength
0x1801100cf  call    cs:__imp_InitializeAcl
0x1801100d6  nop     dword ptr [rax+rax+00h]
0x1801100db  test    eax, eax
0x1801100dd  jnz     loc_180110164
0x1801100e3  call    cs:__imp_GetLastError
0x1801100ea  nop     dword ptr [rax+rax+00h]
0x1801100ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801100f6  mov     ebx, eax
0x1801100f8  test    rcx, rcx
0x1801100fb  jz      short loc_18011014F
0x1801100fd  mov     edi, 3
0x180110102  lea     r9, aFailedToInitia_9; "failed to initialize ACL"
0x180110109  mov     r8d, edi
0x18011010c  xor     edx, edx
0x18011010e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180110113  test    ebx, ebx
0x180110115  jg      short loc_18011011B
0x180110117  mov     eax, ebx
0x180110119  jmp     short loc_180110123
0x18011011b  movzx   eax, bx
0x18011011e  or      eax, 80070000h
0x180110123  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011012a  lea     r9, a0; ": {0}"
0x180110131  mov     [rbp+var_20], eax
0x180110134  mov     r8d, edi
0x180110137  lea     rax, [rbp+var_20]
0x18011013b  mov     dl, 1
0x18011013d  mov     [rbp+var_18], rax
0x180110141  lea     rax, [rbp+var_18]
0x180110145  mov     qword ptr [rsp+60h+pSid], rax
0x18011014a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011014f  test    ebx, ebx
0x180110151  jz      short loc_18011015D
0x180110153  mov     edx, 21h ; '!'
0x180110158  jmp     loc_1801102F1
0x18011015d  xor     ebx, ebx
0x18011015f  jmp     loc_180110306
0x180110164  xor     eax, eax
0x180110166  mov     [rbp+var_20], 0
0x18011016d  xor     ecx, ecx
0x18011016f  mov     r8d, ecx
0x180110172  add     rax, rax
0x180110175  add     r8, r8
0x180110178  mov     edx, 2; dwAceRevision
0x18011017d  mov     rcx, rbx; pAcl
0x180110180  mov     rax, [rdi+rax*8+8]
0x180110185  mov     r9d, [rdi+r8*8+4]; AccessMask
0x18011018a  mov     r8d, [rdi+r8*8]; AceFlags
0x18011018e  mov     qword ptr [rsp+60h+pSid], rax; pSid
0x180110193  call    cs:__imp_AddAccessAllowedAceEx
0x18011019a  nop     dword ptr [rax+rax+00h]
0x18011019f  test    eax, eax
0x1801101a1  jz      loc_18011026F
0x1801101a7  mov     eax, [rbp+var_20]
0x1801101aa  inc     eax
0x1801101ac  mov     [rbp+var_20], eax
0x1801101af  mov     ecx, eax
0x1801101b1  cmp     eax, 1
0x1801101b4  jb      short loc_18011016F
0x1801101b6  mov     rcx, rbx; pAcl
0x1801101b9  call    cs:__imp_IsValidAcl
0x1801101c0  nop     dword ptr [rax+rax+00h]
0x1801101c5  test    eax, eax
0x1801101c7  jnz     short loc_180110237
0x1801101c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801101d0  mov     ebx, 800F0800h
0x1801101d5  mov     dword ptr [rbp+var_18], ebx
0x1801101d8  test    rcx, rcx
0x1801101db  jz      short loc_18011021A
0x1801101dd  lea     edi, [rax+3]
0x1801101e0  xor     edx, edx
0x1801101e2  mov     r8d, edi
0x1801101e5  lea     r9, aAclcreatedaclC; "AclCreateDacl() - created invalid ACL"
0x1801101ec  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801101f1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801101f8  lea     rax, [rbp+var_18]
0x1801101fc  mov     qword ptr [rbp+var_28], rax
0x180110200  lea     r9, asc_1802EE7AC; ": {}"
0x180110207  lea     rax, [rbp+var_28]
0x18011020b  mov     r8d, edi
0x18011020e  mov     dl, 1
0x180110210  mov     qword ptr [rsp+60h+pSid], rax; int
0x180110215  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011021a  mov     edx, 31h ; '1'; void *
0x18011021f  mov     rcx, [rbp+18h]; this
0x180110223  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x18011022a  mov     r9d, ebx; char *
0x18011022d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110232  jmp     loc_180110306
0x180110237  mov     [r14], rbx
0x18011023a  mov     [rbp+pAcl], 0
0x180110242  lea     rcx, [rbp+pAcl]
0x180110246  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18011024b  xor     eax, eax
0x18011024d  mov     rcx, [rbp+var_10]
0x180110251  xor     rcx, rsp; StackCookie
0x180110254  call    __security_check_cookie
0x180110259  lea     r11, [rsp+60h+var_s0]
0x18011025e  mov     rbx, [r11+20h]
0x180110262  mov     rsi, [r11+28h]
0x180110266  mov     rsp, r11
0x180110269  pop     r14
0x18011026b  pop     rdi
0x18011026c  pop     rbp
0x18011026d  retn
0x18011026f  call    cs:__imp_GetLastError
0x180110276  nop     dword ptr [rax+rax+00h]
0x18011027b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180110282  mov     ebx, eax
0x180110284  test    rcx, rcx
0x180110287  jz      short loc_1801102E4
0x180110289  lea     rax, [rbp+var_20]
0x18011028d  mov     edi, 3
0x180110292  mov     r8d, edi
0x180110295  mov     qword ptr [rsp+60h+pSid], rax
0x18011029a  lea     r9, aFailedToAddAcc; "failed to add access allowed ACE #{} to"...
0x1801102a1  xor     edx, edx
0x1801102a3  call    ??$LogNumObjects@K@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBK@Z; LogAdapter::Logger::LogNumObjects<ulong>(bool,LogAdapter::LogLevel,char const * const,ulong const &)
0x1801102a8  test    ebx, ebx
0x1801102aa  jg      short loc_1801102B0
0x1801102ac  mov     eax, ebx
0x1801102ae  jmp     short loc_1801102B8
0x1801102b0  movzx   eax, bx
0x1801102b3  or      eax, 80070000h
0x1801102b8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801102bf  lea     r9, a0; ": {0}"
0x1801102c6  mov     dword ptr [rbp+var_18], eax
0x1801102c9  mov     r8d, edi
0x1801102cc  lea     rax, [rbp+var_18]
0x1801102d0  mov     dl, 1
0x1801102d2  mov     qword ptr [rbp+var_28], rax
0x1801102d6  lea     rax, [rbp+var_28]
0x1801102da  mov     qword ptr [rsp+60h+pSid], rax; unsigned int
0x1801102df  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801102e4  test    ebx, ebx
0x1801102e6  jz      loc_180110242
0x1801102ec  mov     edx, 2Eh ; '.'; void *
0x1801102f1  mov     rcx, [rbp+18h]; this
0x1801102f5  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x1801102fc  mov     r9d, ebx; char *
0x1801102ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180110304  mov     ebx, eax
0x180110306  lea     rcx, [rbp+pAcl]
0x18011030a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x18011030f  jmp     loc_180110081
```
