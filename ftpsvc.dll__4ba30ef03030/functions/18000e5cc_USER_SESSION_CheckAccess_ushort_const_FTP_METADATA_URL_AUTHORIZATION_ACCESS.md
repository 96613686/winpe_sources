# USER_SESSION::CheckAccess(ushort const *,FTP_METADATA *,URL_AUTHORIZATION_ACCESS)

- ea: `0x18000e5cc`
- end: `0x18000eced`
- name: `?CheckAccess@USER_SESSION@@AEAAJPEBGPEAVFTP_METADATA@@W4URL_AUTHORIZATION_ACCESS@@@Z`
- size: `1825`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fdd8`

## callees

- `0x180009090`
- `0x18000e5cc`
- `0x18000fb34`
- `0x1800235b0`
- `0x180024764`
- `0x1800296f0`
- `0x1800298a4`
- `0x180029a10`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e697`
- `msvcrt!_wcsicmp` at `0x18000e697`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e7b5`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e7b5`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000ecb3`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000ecb3`
- `iisutil!PuDbgPrint` at `0x18000e700`
- `iisutil!PuDbgPrint` at `0x18000e79f`
- `iisutil!PuDbgPrint` at `0x18000e8cd`
- `iisutil!PuDbgPrint` at `0x18000e922`
- `iisutil!PuDbgPrint` at `0x18000e95e`
- `iisutil!PuDbgPrint` at `0x18000e9e2`
- `iisutil!PuDbgPrint` at `0x18000ea21`
- `iisutil!PuDbgPrint` at `0x18000ea89`
- `iisutil!PuDbgPrint` at `0x18000eae0`
- `iisutil!PuDbgPrint` at `0x18000eb31`
- `iisutil!PuDbgPrint` at `0x18000eb88`
- `iisutil!PuDbgPrint` at `0x18000ebe3`
- `iisutil!PuDbgPrint` at `0x18000ec5f`
- `iisutil!PuDbgPrint` at `0x18000e700`
- `iisutil!PuDbgPrint` at `0x18000e79f`
- `iisutil!PuDbgPrint` at `0x18000e8cd`
- `iisutil!PuDbgPrint` at `0x18000e922`
- `iisutil!PuDbgPrint` at `0x18000e95e`
- `iisutil!PuDbgPrint` at `0x18000e9e2`
- `iisutil!PuDbgPrint` at `0x18000ea21`
- `iisutil!PuDbgPrint` at `0x18000ea89`
- `iisutil!PuDbgPrint` at `0x18000eae0`
- `iisutil!PuDbgPrint` at `0x18000eb31`
- `iisutil!PuDbgPrint` at `0x18000eb88`
- `iisutil!PuDbgPrint` at `0x18000ebe3`
- `iisutil!PuDbgPrint` at `0x18000ec5f`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e7ea`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e7ea`
- `iisutil!WriteRefTraceLog` at `0x18000e7da`
- `iisutil!WriteRefTraceLog` at `0x18000ec96`
- `iisutil!WriteRefTraceLog` at `0x18000e7da`
- `iisutil!WriteRefTraceLog` at `0x18000ec96`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000e615`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000e615`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ecbe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ecbe`

## string_xrefs

- `0x18000e75b`: `IP restriction rules denied the access.`
- `0x18000e6d9`: `Denied write access. Paths exactly matching a virtual directory path paths are only allowed for read access.\n`
- `0x18000e6e5`: `USER_SESSION::CheckAccess`
- `0x18000e784`: `USER_SESSION::CheckAccess`
- `0x18000e8b2`: `USER_SESSION::CheckAccess`
- `0x18000e943`: `USER_SESSION::CheckAccess`
- `0x18000ea06`: `USER_SESSION::CheckAccess`
- `0x18000ea6e`: `USER_SESSION::CheckAccess`
- `0x18000eac5`: `USER_SESSION::CheckAccess`
- `0x18000eb16`: `USER_SESSION::CheckAccess`
- `0x18000eb6d`: `USER_SESSION::CheckAccess`
- `0x18000ebc8`: `USER_SESSION::CheckAccess`
- `0x18000ec44`: `USER_SESSION::CheckAccess`
- `0x18000e710`: `Write access for the root of the virtual directory is forbidden.`
- `0x18000e778`: `Denied access by Ip Restriction check.\n`
- `0x18000e848`: `Write`
- `0x18000e87b`: `Authorization rules denied the access.`
- `0x18000e8a6`: `Denied access by Url authorization check.\n`
- `0x18000e96e`: `Path is too long based on request filtering rules.`
- `0x18000e937`: `Denied access by Request Filtering check: long Url.\n`
- `0x18000ea31`: `High bit characters detected in the path based on request filtering rules.`
- `0x18000e9fa`: `Denied access by Request Filtering check: high bit flags used.\n`
- `0x18000ea99`: `Denied Url sequence detected in the path based on request filtering rules.`
- `0x18000eab9`: `Denied access by Request Filtering check: url sequence.\n`
- `0x18000eb41`: `Hidden segment was detected in the path based on request filtering rules.`
- `0x18000eb61`: `Denied access by Request Filtering check: hidden segment.\n`
- `0x18000ebbc`: `CheckForAllowedFileExtension failed - error 0x%08x.\n`
- `0x18000ebf3`: `File extension was denied based on request filtering rules.`
- `0x18000ec38`: `Denied access by Request Filtering check: file extensions.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall USER_SESSION::CheckAccess(__int64 a1, const wchar_t *a2, __int64 a3, int a4)
{
  __int64 v8; // r13
  int v9; // esi
  const wchar_t *v10; // rax
  int v11; // ecx
  int v12; // edx
  int v13; // ebx
  const wchar_t *v14; // rax
  __int64 v15; // r14
  CReaderWriterLock3 *v16; // rbx
  __int64 v17; // rdx
  struct FTP_SITE_CONFIG *v18; // r14
  enum _FTP_ACCESS v19; // r8d
  int v20; // eax
  __int64 v21; // rax
  const unsigned __int16 *v22; // r8
  const wchar_t *v23; // rax
  FTP_REQUEST_FILTER *v24; // rsi
  unsigned int v25; // ecx
  char v26; // al
  int v27; // ebx
  const wchar_t *v28; // rax
  int v29; // ecx
  unsigned int v30; // edx
  int v31; // eax
  unsigned int v32; // r8d
  int v33; // eax
  unsigned int v34; // r8d
  int v35; // eax
  unsigned __int32 v36; // edi
  int v38; // [rsp+40h] [rbp-39h] BYREF
  int v39; // [rsp+44h] [rbp-35h]
  int v40; // [rsp+48h] [rbp-31h] BYREF
  int v41; // [rsp+4Ch] [rbp-2Dh]
  __int64 v42; // [rsp+50h] [rbp-29h]
  _BYTE v43[56]; // [rsp+58h] [rbp-21h] BYREF

  v42 = a3;
  v40 = 0;
  v38 = 0;
  STRU::STRU(v43);
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v39 = 0;
  v9 = 0;
  v41 = 0;
  if ( a4 > 18 )
  {
    if ( a4 != 19 )
    {
      if ( a4 == 21 || a4 == 22 )
        goto LABEL_24;
      if ( a4 != 33 )
        goto LABEL_26;
      goto LABEL_15;
    }
LABEL_25:
    v39 = 1;
    goto LABEL_26;
  }
  if ( a4 == 18 )
    goto LABEL_15;
  if ( a4 == 1 )
    goto LABEL_25;
  if ( a4 != 2 && a4 != 3 )
  {
    if ( a4 != 4 )
    {
      if ( a4 != 17 )
        goto LABEL_26;
      goto LABEL_15;
    }
LABEL_24:
    v41 = 1;
    goto LABEL_26;
  }
LABEL_15:
  if ( !_wcsicmp(*(const wchar_t **)(a3 + 360), a2) )
    goto LABEL_20;
  v9 = 1;
  v10 = a2;
  do
  {
    v11 = *(const wchar_t *)((char *)v10 + *(_QWORD *)(a1 + 320) - (_QWORD)a2);
    v12 = *v10 - v11;
    if ( v12 )
      break;
    ++v10;
  }
  while ( v11 );
  if ( !v12 )
  {
LABEL_20:
    v13 = -2147024891;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        557,
        "USER_SESSION::CheckAccess",
        "Denied write access. Paths exactly matching a virtual directory path paths are only allowed for read access.\r\n");
    *(_DWORD *)(a1 + 1112) = 5;
    v14 = L"Write access for the root of the virtual directory is forbidden.";
    goto LABEL_23;
  }
LABEL_26:
  v13 = IP_RESTRICTION_LIST::Check(
          (IP_RESTRICTION_LIST *)(a3 + 640),
          (const struct sockaddr *)(a1 + 352),
          (struct STRU *)v43,
          &v40,
          0);
  if ( v13 < 0 )
  {
LABEL_27:
    *(_DWORD *)(a1 + 1112) = 4;
    v14 = L"IP restriction rules denied the access.";
LABEL_23:
    *(_QWORD *)(a1 + 1104) = v14;
    goto LABEL_98;
  }
  if ( !v40 )
  {
    v13 = -2147024891;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        588,
        "USER_SESSION::CheckAccess",
        "Denied access by Ip Restriction check.\r\n");
    goto LABEL_27;
  }
  v15 = *(_QWORD *)(a1 + 16);
  v16 = (CReaderWriterLock3 *)(v15 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v15 + 208));
  v17 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v15 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v17);
  v18 = *(struct FTP_SITE_CONFIG **)(v15 + 192);
  CReaderWriterLock3::ReadUnlock(v16);
  if ( *((_DWORD *)v18 + 74) == 1 )
  {
    if ( v39 )
      v19 = FTP_ACCESS_READ;
    else
      v19 = 3 - (v9 != 0);
    v20 = USER_SESSION::DoCustomAuthorization((USER_SESSION *)a1, a2, v19, v18, &v38);
  }
  else
  {
    v21 = v42;
    if ( v39 )
    {
      v22 = L"Read";
    }
    else if ( v9 )
    {
      v22 = L"Write";
    }
    else
    {
      if ( !v41 )
        goto LABEL_49;
      v22 = &WideCharStr;
    }
    v20 = URL_AUTHZ_RULE_LIST::DoAuthorizationCheck(
            (URL_AUTHZ_RULE_LIST *)(v42 + 664),
            (struct FTP_USER *)(a1 + 24),
            v22,
            &v38);
  }
  v13 = v20;
  if ( v20 >= 0 )
  {
    v21 = v42;
LABEL_49:
    if ( !v38 )
    {
      v13 = -2147024891;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          661,
          "USER_SESSION::CheckAccess",
          "Denied access by Url authorization check.\r\n");
      goto LABEL_46;
    }
    v24 = (FTP_REQUEST_FILTER *)(v21 + 680);
    v25 = *(_DWORD *)(v21 + 696);
    if ( (unsigned int)v8 > v25 )
    {
      v26 = g_dwDebugFlags;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_request_filter\\ftp_request_filter.cxx",
          622,
          "FTP_REQUEST_FILTER::CheckForLongUrl",
          "URL '%S' exceeds %d chars and will be rejected.\r\n",
          a2,
          v25);
        v26 = g_dwDebugFlags;
      }
      v13 = -2147024891;
      if ( (v26 & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          703,
          "USER_SESSION::CheckAccess",
          "Denied access by Request Filtering check: long Url.\r\n");
      *(_DWORD *)(a1 + 1112) = 12;
      v23 = L"Path is too long based on request filtering rules.";
      goto LABEL_47;
    }
    v27 = 0;
    v38 = 0;
    if ( !*(_DWORD *)v24 )
    {
      v28 = a2;
      v29 = v8;
      if ( (_DWORD)v8 )
      {
        while ( 1 )
        {
          v30 = *v28;
          if ( v30 > 0x7F )
            break;
          ++v28;
          if ( !--v29 )
            goto LABEL_65;
        }
        v27 = 1;
        v38 = 1;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_request_filter\\ftp_request_filter.cxx",
            678,
            "FTP_REQUEST_FILTER::CheckForHighBitChars",
            "Found high bit char '%C' in URL '%S'.\r\n",
            v30,
            a2);
      }
    }
LABEL_65:
    if ( v27 )
    {
      v13 = -2147024891;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          740,
          "USER_SESSION::CheckAccess",
          "Denied access by Request Filtering check: high bit flags used.\r\n");
      *(_DWORD *)(a1 + 1112) = 10;
      v23 = L"High bit characters detected in the path based on request filtering rules.";
      goto LABEL_47;
    }
    v31 = FTP_REQUEST_FILTER::CheckForUrlSequences(v24, a2, v8, &v38);
    v13 = v31;
    if ( v31 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          759,
          "USER_SESSION::CheckAccess",
          "CheckForUrlSequences failed - error 0x%08x.\r\n",
          v31);
LABEL_72:
      *(_DWORD *)(a1 + 1112) = 9;
      v23 = L"Denied Url sequence detected in the path based on request filtering rules.";
      goto LABEL_47;
    }
    if ( v38 )
    {
      v13 = -2147024891;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          776,
          "USER_SESSION::CheckAccess",
          "Denied access by Request Filtering check: url sequence.\r\n");
      goto LABEL_72;
    }
    v33 = FTP_REQUEST_FILTER::CheckForHiddenSegments(v24, a2, v32, &v38);
    v13 = v33;
    if ( v33 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          796,
          "USER_SESSION::CheckAccess",
          "CheckForHiddenSegments failed - error 0x%08x.\r\n",
          v33);
LABEL_79:
      *(_DWORD *)(a1 + 1112) = 8;
      v23 = L"Hidden segment was detected in the path based on request filtering rules.";
      goto LABEL_47;
    }
    if ( v38 )
    {
      v13 = -2147024891;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          812,
          "USER_SESSION::CheckAccess",
          "Denied access by Request Filtering check: hidden segment.\r\n");
      goto LABEL_79;
    }
    if ( (a4 & 0x10) == 0 )
    {
      v35 = FTP_REQUEST_FILTER::CheckForAllowedFileExtension(v24, a2, v34, &v38);
      v13 = v35;
      if ( v35 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
            846,
            "USER_SESSION::CheckAccess",
            "CheckForAllowedFileExtension failed - error 0x%08x.\r\n",
            v35);
LABEL_87:
        *(_DWORD *)(a1 + 1112) = 11;
        v23 = L"File extension was denied based on request filtering rules.";
        goto LABEL_47;
      }
      if ( v38
        && ((a4 & 0x20) == 0
         || (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64))(*(_QWORD *)a1 + 88LL))(a1, a2, 0, 1) < 0) )
      {
        v13 = -2147024891;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
            888,
            "USER_SESSION::CheckAccess",
            "Denied access by Request Filtering check: file extensions.\r\n");
        goto LABEL_87;
      }
    }
    *(_QWORD *)(a1 + 1128) = *(_QWORD *)(v42 + 688);
    v13 = 0;
    goto LABEL_94;
  }
LABEL_46:
  *(_DWORD *)(a1 + 1112) = 1;
  v23 = L"Authorization rules denied the access.";
LABEL_47:
  *(_QWORD *)(a1 + 1104) = v23;
LABEL_94:
  v36 = _InterlockedDecrement((volatile signed __int32 *)v18);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v36);
  if ( !v36 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG(v18);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, v18);
  }
LABEL_98:
  STRU::~STRU(v43);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000e5cc  mov     [rsp-8+arg_18], rbx
0x18000e5d1  push    rbp
0x18000e5d2  push    rsi
0x18000e5d3  push    rdi
0x18000e5d4  push    r12
0x18000e5d6  push    r13
0x18000e5d8  push    r14
0x18000e5da  push    r15
0x18000e5dc  lea     rbp, [rsp-27h]
0x18000e5e1  sub     rsp, 0A0h
0x18000e5e8  mov     rax, cs:__security_cookie
0x18000e5ef  xor     rax, rsp
0x18000e5f2  mov     [rbp+57h+var_40], rax
0x18000e5f6  mov     r12d, r9d
0x18000e5f9  mov     rbx, r8
0x18000e5fc  mov     [rbp+57h+var_80], rbx
0x18000e600  mov     r15, rdx
0x18000e603  mov     rdi, rcx
0x18000e606  xor     r14d, r14d
0x18000e609  mov     [rbp+57h+var_88], r14d
0x18000e60d  mov     [rbp+57h+var_90], r14d
0x18000e611  lea     rcx, [rbp+57h+var_78]
0x18000e615  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000e61b  nop
0x18000e61c  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000e620  inc     r13
0x18000e623  cmp     [r15+r13*2], r14w
0x18000e628  jnz     short loc_18000E620
0x18000e62a  mov     [rbp+57h+var_8C], r14d
0x18000e62e  mov     esi, r14d
0x18000e631  mov     [rbp+57h+var_84], r14d
0x18000e635  mov     edx, 1
0x18000e63a  cmp     r12d, 12h
0x18000e63e  jg      short loc_18000E667
0x18000e640  jz      short loc_18000E68D
0x18000e642  mov     ecx, r12d
0x18000e645  sub     ecx, edx
0x18000e647  jz      loc_18000E728
0x18000e64d  sub     ecx, edx
0x18000e64f  jz      short loc_18000E68D
0x18000e651  sub     ecx, edx
0x18000e653  jz      short loc_18000E68D
0x18000e655  sub     ecx, edx
0x18000e657  jz      loc_18000E723
0x18000e65d  cmp     ecx, 0Dh
0x18000e660  jz      short loc_18000E68D
0x18000e662  jmp     loc_18000E72B
0x18000e667  mov     ecx, r12d
0x18000e66a  sub     ecx, 13h
0x18000e66d  jz      loc_18000E728
0x18000e673  sub     ecx, 2
0x18000e676  jz      loc_18000E723
0x18000e67c  sub     ecx, edx
0x18000e67e  jz      loc_18000E723
0x18000e684  cmp     ecx, 0Bh
0x18000e687  jnz     loc_18000E72B
0x18000e68d  mov     rdx, r15; String2
0x18000e690  mov     rcx, [rbx+168h]; String1
0x18000e697  call    cs:__imp__wcsicmp
0x18000e69d  test    eax, eax
0x18000e69f  jz      short loc_18000E6CB
0x18000e6a1  mov     esi, 1
0x18000e6a6  mov     rax, r15
0x18000e6a9  mov     r8, [rdi+140h]
0x18000e6b0  sub     r8, r15
0x18000e6b3  movzx   edx, word ptr [rax]
0x18000e6b6  movzx   ecx, word ptr [rax+r8]
0x18000e6bb  sub     edx, ecx
0x18000e6bd  jnz     short loc_18000E6C7
0x18000e6bf  add     rax, 2
0x18000e6c3  test    ecx, ecx
0x18000e6c5  jnz     short loc_18000E6B3
0x18000e6c7  test    edx, edx
0x18000e6c9  jnz     short loc_18000E72B
0x18000e6cb  mov     ebx, 80070005h
0x18000e6d0  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e6d7  jz      short loc_18000E706
0x18000e6d9  lea     rax, aDeniedWriteAcc_0; "Denied write access. Paths exactly matc"...
0x18000e6e0  mov     [rsp+0D0h+var_B0], rax
0x18000e6e5  lea     r9, aUserSessionChe_1; "USER_SESSION::CheckAccess"
0x18000e6ec  mov     r8d, 22Dh
0x18000e6f2  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000e6f9  mov     rcx, cs:g_pDebug
0x18000e700  call    cs:__imp_PuDbgPrint
0x18000e706  mov     dword ptr [rdi+458h], 5
0x18000e710  lea     rax, aWriteAccessFor; "Write access for the root of the virtua"...
0x18000e717  mov     [rdi+450h], rax
0x18000e71e  jmp     loc_18000ECBA
0x18000e723  mov     [rbp+57h+var_84], edx
0x18000e726  jmp     short loc_18000E72B
0x18000e728  mov     [rbp+57h+var_8C], edx
0x18000e72b  lea     rdx, [rdi+160h]; struct sockaddr *
0x18000e732  lea     rcx, [rbx+280h]; this
0x18000e739  mov     [rsp+0D0h+var_B0], r14; int *
0x18000e73e  lea     r9, [rbp+57h+var_88]; int *
0x18000e742  lea     r8, [rbp+57h+var_78]; struct STRU *
0x18000e746  call    ?Check@IP_RESTRICTION_LIST@@QEAAJPEBUsockaddr@@PEAVSTRU@@PEAH2@Z; IP_RESTRICTION_LIST::Check(sockaddr const *,STRU *,int *,int *)
0x18000e74b  mov     ebx, eax
0x18000e74d  test    eax, eax
0x18000e74f  jns     short loc_18000E764
0x18000e751  mov     dword ptr [rdi+458h], 4
0x18000e75b  lea     rax, aIpRestrictionR; "IP restriction rules denied the access."
0x18000e762  jmp     short loc_18000E717
0x18000e764  cmp     [rbp+57h+var_88], r14d
0x18000e768  jnz     short loc_18000E7A7
0x18000e76a  mov     ebx, 80070005h
0x18000e76f  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e776  jz      short loc_18000E751
0x18000e778  lea     rax, aDeniedAccessBy_1; "Denied access by Ip Restriction check."...
0x18000e77f  mov     [rsp+0D0h+var_B0], rax
0x18000e784  lea     r9, aUserSessionChe_1; "USER_SESSION::CheckAccess"
0x18000e78b  mov     r8d, 24Ch
0x18000e791  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000e798  mov     rcx, cs:g_pDebug
0x18000e79f  call    cs:__imp_PuDbgPrint
0x18000e7a5  jmp     short loc_18000E751
0x18000e7a7  mov     r14, [rdi+10h]
0x18000e7ab  lea     rbx, [r14+0D0h]
0x18000e7b2  mov     rcx, rbx
0x18000e7b5  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000e7bb  mov     r8, [r14+0C0h]
0x18000e7c2  mov     edx, 1
0x18000e7c7  lock xadd [r8], edx
0x18000e7cc  inc     edx
0x18000e7ce  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000e7d5  test    rcx, rcx
0x18000e7d8  jz      short loc_18000E7E0
0x18000e7da  call    cs:__imp_WriteRefTraceLog
0x18000e7e0  mov     r14, [r14+0C0h]
0x18000e7e7  mov     rcx, rbx
0x18000e7ea  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000e7f0  cmp     dword ptr [r14+128h], 1
0x18000e7f8  jnz     short loc_18000E82A
0x18000e7fa  cmp     [rbp+57h+var_8C], 0
0x18000e7fe  jz      short loc_18000E808
0x18000e800  mov     r8d, 1
0x18000e806  jmp     short loc_18000E811
0x18000e808  neg     esi
0x18000e80a  sbb     r8d, r8d
0x18000e80d  add     r8d, 3; enum _FTP_ACCESS
0x18000e811  lea     rax, [rbp+57h+var_90]
0x18000e815  mov     [rsp+0D0h+var_B0], rax; int *
0x18000e81a  mov     r9, r14; struct FTP_SITE_CONFIG *
0x18000e81d  mov     rdx, r15; unsigned __int16 *
0x18000e820  mov     rcx, rdi; this
0x18000e823  call    ?DoCustomAuthorization@USER_SESSION@@AEAAJPEBGW4_FTP_ACCESS@@PEAVFTP_SITE_CONFIG@@PEAH@Z; USER_SESSION::DoCustomAuthorization(ushort const *,_FTP_ACCESS,FTP_SITE_CONFIG *,int *)
0x18000e828  jmp     short loc_18000E86B
0x18000e82a  mov     rax, [rbp+57h+var_80]
0x18000e82e  lea     rcx, [rax+298h]; this
0x18000e835  cmp     [rbp+57h+var_8C], 0
0x18000e839  jz      short loc_18000E844
0x18000e83b  lea     r8, aRead; "Read"
0x18000e842  jmp     short loc_18000E85E
0x18000e844  test    esi, esi
0x18000e846  jz      short loc_18000E851
0x18000e848  lea     r8, aWrite; "Write"
0x18000e84f  jmp     short loc_18000E85E
0x18000e851  cmp     [rbp+57h+var_84], 0
0x18000e855  jz      short loc_18000E892
0x18000e857  lea     r8, WideCharStr; unsigned __int16 *
0x18000e85e  lea     r9, [rbp+57h+var_90]; int *
0x18000e862  lea     rdx, [rdi+18h]; struct FTP_USER *
0x18000e866  call    ?DoAuthorizationCheck@URL_AUTHZ_RULE_LIST@@QEAAJPEAVFTP_USER@@PEBGPEAH@Z; URL_AUTHZ_RULE_LIST::DoAuthorizationCheck(FTP_USER *,ushort const *,int *)
0x18000e86b  mov     ebx, eax
0x18000e86d  test    eax, eax
0x18000e86f  jns     short loc_18000E88E
0x18000e871  mov     dword ptr [rdi+458h], 1
0x18000e87b  lea     rax, aAuthorizationR; "Authorization rules denied the access."
0x18000e882  mov     [rdi+450h], rax
0x18000e889  jmp     loc_18000EC7B
0x18000e88e  mov     rax, [rbp+57h+var_80]
0x18000e892  cmp     [rbp+57h+var_90], 0
0x18000e896  jnz     short loc_18000E8D5
0x18000e898  mov     ebx, 80070005h
0x18000e89d  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e8a4  jz      short loc_18000E871
0x18000e8a6  lea     rax, aDeniedAccessBy_5; "Denied access by Url authorization chec"...
0x18000e8ad  mov     [rsp+0D0h+var_B0], rax
0x18000e8b2  lea     r9, aUserSessionChe_1; "USER_SESSION::CheckAccess"
0x18000e8b9  mov     r8d, 295h
0x18000e8bf  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000e8c6  mov     rcx, cs:g_pDebug
0x18000e8cd  call    cs:__imp_PuDbgPrint
0x18000e8d3  jmp     short loc_18000E871
0x18000e8d5  lea     rsi, [rax+2A8h]
0x18000e8dc  mov     ecx, [rsi+10h]
0x18000e8df  cmp     r13d, ecx
0x18000e8e2  jbe     loc_18000E97A
0x18000e8e8  mov     eax, cs:g_dwDebugFlags
0x18000e8ee  test    al, 3
0x18000e8f0  jz      short loc_18000E92E
0x18000e8f2  mov     dword ptr [rsp+0D0h+var_A0], ecx
0x18000e8f6  mov     [rsp+0D0h+var_A8], r15
0x18000e8fb  lea     rax, aUrlSExceedsDCh; "URL '%S' exceeds %d chars and will be r"...
0x18000e902  mov     [rsp+0D0h+var_B0], rax
0x18000e907  lea     r9, aFtpRequestFilt_1; "FTP_REQUEST_FILTER::CheckForLongUrl"
0x18000e90e  mov     r8d, 26Eh
0x18000e914  lea     rdx, aInetsrvIisIisr_22; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18000e91b  mov     rcx, cs:g_pDebug
0x18000e922  call    cs:__imp_PuDbgPrint
0x18000e928  mov     eax, cs:g_dwDebugFlags
0x18000e92e  mov     ebx, 80070005h
0x18000e933  test    al, 3
0x18000e935  jz      short loc_18000E964
0x18000e937  lea     rax, aDeniedAccessBy; "Denied access by Request Filtering chec"...
0x18000e93e  mov     [rsp+0D0h+var_B0], rax
0x18000e943  lea     r9, aUserSessionChe_1; "USER_SESSION::CheckAccess"
0x18000e94a  mov     r8d, 2BFh
0x18000e950  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000e957  mov     rcx, cs:g_pDebug
0x18000e95e  call    cs:__imp_PuDbgPrint
0x18000e964  mov     dword ptr [rdi+458h], 0Ch
0x18000e96e  lea     rax, aPathIsTooLongB; "Path is too long based on request filte"...
0x18000e975  jmp     loc_18000E882
0x18000e97a  xor     ebx, ebx
0x18000e97c  mov     [rbp+57h+var_90], ebx
0x18000e97f  cmp     [rsi], ebx
0x18000e981  jnz     short loc_18000E9E8
0x18000e983  mov     rax, r15
0x18000e986  mov     ecx, r13d
0x18000e989  test    r13d, r13d
0x18000e98c  jz      short loc_18000E9E8
0x18000e98e  movzx   edx, word ptr [rax]
0x18000e991  cmp     edx, 7Fh
0x18000e994  ja      short loc_18000E9A1
0x18000e996  add     rax, 2
0x18000e99a  add     ecx, 0FFFFFFFFh
0x18000e99d  jnz     short loc_18000E98E
0x18000e99f  jmp     short loc_18000E9E8
0x18000e9a1  mov     ebx, 1
0x18000e9a6  mov     [rbp+57h+var_90], ebx
0x18000e9a9  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e9b0  jz      short loc_18000E9E8
0x18000e9b2  mov     [rsp+0D0h+var_A0], r15
0x18000e9b7  mov     dword ptr [rsp+0D0h+var_A8], edx
0x18000e9bb  lea     rax, aFoundHighBitCh; "Found high bit char '%C' in URL '%S'.\r"...
0x18000e9c2  mov     [rsp+0D0h+var_B0], rax
0x18000e9c7  lea     r9, aFtpRequestFilt_4; "FTP_REQUEST_FILTER::CheckForHighBitChar"...
0x18000e9ce  mov     r8d, 2A6h
0x18000e9d4  lea     rdx, aInetsrvIisIisr_22; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18000e9db  mov     rcx, cs:g_pDebug
0x18000e9e2  call    cs:__imp_PuDbgPrint
0x18000e9e8  test    ebx, ebx
0x18000e9ea  jz      short loc_18000EA3D
0x18000e9ec  mov     ebx, 80070005h
0x18000e9f1  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e9f8  jz      short loc_18000EA27
0x18000e9fa  lea     rax, aDeniedAccessBy_4; "Denied access by Request Filtering chec"...
0x18000ea01  mov     [rsp+0D0h+var_B0], rax
0x18000ea06  lea     r9, aUserSessionChe_1; "USER_SESSION::CheckAccess"
0x18000ea0d  mov     r8d, 2E4h
0x18000ea13  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000ea1a  mov     rcx, cs:g_pDebug
0x18000ea21  call    cs:__imp_PuDbgPrint
0x18000ea27  mov     dword ptr [rdi+458h], 0Ah
0x18000ea31  lea     rax, aHighBitCharact; "High bit characters detected in the pat"...
0x18000ea38  jmp     loc_18000E882
0x18000ea3d  lea     r9, [rbp+57h+var_90]; int *
0x18000ea41  mov     r8d, r13d; unsigned int
0x18000ea44  mov     rdx, r15; unsigned __int16 *
0x18000ea47  mov     rcx, rsi; this
0x18000ea4a  call    ?CheckForUrlSequences@FTP_REQUEST_FILTER@@QEAAJPEBGKPEAH@Z; FTP_REQUEST_FILTER::CheckForUrlSequences(ushort const *,ulong,int *)
0x18000ea4f  mov     ebx, eax
0x18000ea51  test    eax, eax
0x18000ea53  jns     short loc_18000EAA5
0x18000ea55  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ea5c  jz      short loc_18000EA8F
0x18000ea5e  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18000ea62  lea     rax, aCheckforurlseq; "CheckForUrlSequences failed - error 0x%"...
0x18000ea69  mov     [rsp+0D0h+var_B0], rax
0x18000ea6e  lea     r9, aUserSessionChe_1; "USER_SESSION::CheckAccess"
0x18000ea75  mov     r8d, 2F7h
0x18000ea7b  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000ea82  mov     rcx, cs:g_pDebug
0x18000ea89  call    cs:__imp_PuDbgPrint
0x18000ea8f  mov     dword ptr [rdi+458h], 9
0x18000ea99  lea     rax, aDeniedUrlSeque; "Denied Url sequence detected in the pat"...
0x18000eaa0  jmp     loc_18000E882
0x18000eaa5  cmp     [rbp+57h+var_90], 0
0x18000eaa9  jz      short loc_18000EAE8
0x18000eaab  mov     ebx, 80070005h
0x18000eab0  test    byte ptr cs:g_dwDebugFlags, 3
0x18000eab7  jz      short loc_18000EA8F
0x18000eab9  lea     rax, aDeniedAccessBy_3; "Denied access by Request Filtering chec"...
0x18000eac0  mov     [rsp+0D0h+var_B0], rax
0x18000eac5  lea     r9, aUserSessionChe_1; "USER_SESSION::CheckAccess"
0x18000eacc  mov     r8d, 308h
0x18000ead2  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000ead9  mov     rcx, cs:g_pDebug
0x18000eae0  call    cs:__imp_PuDbgPrint
0x18000eae6  jmp     short loc_18000EA8F
0x18000eae8  lea     r9, [rbp+57h+var_90]; int *
0x18000eaec  mov     rdx, r15; unsigned __int16 *
0x18000eaef  mov     rcx, rsi; this
0x18000eaf2  call    ?CheckForHiddenSegments@FTP_REQUEST_FILTER@@QEAAJPEBGKPEAH@Z; FTP_REQUEST_FILTER::CheckForHiddenSegments(ushort const *,ulong,int *)
0x18000eaf7  mov     ebx, eax
0x18000eaf9  test    eax, eax
0x18000eafb  jns     short loc_18000EB4D
0x18000eafd  test    byte ptr cs:g_dwDebugFlags, 3
0x18000eb04  jz      short loc_18000EB37
  ... truncated ...
```
