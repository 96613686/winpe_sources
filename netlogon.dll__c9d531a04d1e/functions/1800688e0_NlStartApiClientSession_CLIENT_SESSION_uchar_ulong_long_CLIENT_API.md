# NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)

- ea: `0x1800688e0`
- end: `0x18006916f`
- name: `?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z`
- size: `2191`
- prototype: `__int64 __usercall@<rax>(struct _CLIENT_SESSION *@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, int@<r9d>, struct _CLIENT_API *)`
- caller_count: `13`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022374`
- `0x1800291f4`
- `0x18002e478`
- `0x18002fdb4`
- `0x180032160`
- `0x1800344a4`
- `0x180034a68`
- `0x180034cfc`
- `0x180036df8`
- `0x1800378d4`
- `0x180057434`
- `0x1800585a0`
- `0x180069580`

## callees

- `0x1800065c8`
- `0x180007278`
- `0x18000d100`
- `0x18000d710`
- `0x1800395e8`
- `0x18003e71c`
- `0x1800527c0`
- `0x1800688e0`
- `0x18006b1d4`
- `0x180082ac4`
- `0x180089a90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180068d8e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180068d8e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180068a3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180068a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068a82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180068a82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180068a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180068a79`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180068aa7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180068aa7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800689f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800689f9`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x180068ad3`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x180068ad3`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180069109`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180069109`
- `logoncli!NlBindingSetAuthInfo` at `0x18006909a`
- `logoncli!NlBindingSetAuthInfo` at `0x18006909a`
- `logoncli!NlBindingAddServerToCache` at `0x180068c98`
- `logoncli!NlBindingAddServerToCache` at `0x180068c98`
- `ntdll!NtImpersonateAnonymousToken` at `0x180068bc7`
- `ntdll!NtImpersonateAnonymousToken` at `0x180068bc7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800689b5`
- `ntdll!RtlLeaveCriticalSection` at `0x180068b85`
- `ntdll!RtlLeaveCriticalSection` at `0x180068d6b`
- `ntdll!RtlLeaveCriticalSection` at `0x180069148`
- `ntdll!RtlLeaveCriticalSection` at `0x180069156`
- `ntdll!RtlLeaveCriticalSection` at `0x1800689b5`
- `ntdll!RtlLeaveCriticalSection` at `0x180068b85`
- `ntdll!RtlLeaveCriticalSection` at `0x180068d6b`
- `ntdll!RtlLeaveCriticalSection` at `0x180069148`
- `ntdll!RtlLeaveCriticalSection` at `0x180069156`
- `ntdll!RtlEnterCriticalSection` at `0x180068918`
- `ntdll!RtlEnterCriticalSection` at `0x1800689eb`
- `ntdll!RtlEnterCriticalSection` at `0x180068d50`
- `ntdll!RtlEnterCriticalSection` at `0x180068db6`
- `ntdll!RtlEnterCriticalSection` at `0x180068918`
- `ntdll!RtlEnterCriticalSection` at `0x1800689eb`
- `ntdll!RtlEnterCriticalSection` at `0x180068d50`
- `ntdll!RtlEnterCriticalSection` at `0x180068db6`
- `netutils!NetApiBufferFree` at `0x180068ea8`
- `netutils!NetApiBufferFree` at `0x180068ea8`
- `netutils!NetApiBufferAllocate` at `0x180068f85`
- `netutils!NetApiBufferAllocate` at `0x180068f85`
- `DSPARSE!DsMakeSpnW` at `0x180068f3c`
- `DSPARSE!DsMakeSpnW` at `0x180068fdb`
- `DSPARSE!DsMakeSpnW` at `0x180068f3c`
- `DSPARSE!DsMakeSpnW` at `0x180068fdb`

## string_xrefs

- `0x1800689ca`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180068c78`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180068bd6`: `NlStartApiClientSession: cannot NtImpersonateAnonymousToken: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlStartApiClientSession(
        struct _CLIENT_SESSION *a1,
        char a2,
        DWORD a3,
        int a4,
        struct _CLIENT_API *a5)
{
  char v6; // r13
  int v7; // edi
  struct _CLIENT_API *v9; // r14
  unsigned int v10; // ebp
  bool v11; // zf
  char v12; // r12
  int v13; // ebx
  char *v14; // r9
  __int64 v15; // rdx
  struct _FILETIME v16; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v20; // rax
  DWORD v21; // eax
  unsigned int v22; // eax
  char v23; // di
  int v24; // eax
  char v25; // di
  NTSTATUS v26; // eax
  int v27; // ebx
  const char *v28; // r12
  const char *v29; // r15
  char *v30; // r9
  unsigned __int16 *v31; // rcx
  int v32; // eax
  unsigned __int16 *v33; // r8
  unsigned int v34; // ecx
  unsigned int v35; // eax
  struct _RTL_CRITICAL_SECTION *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  char *v39; // r9
  _DWORD *v40; // rax
  unsigned int v41; // eax
  LPWSTR *v42; // r15
  void *v43; // rcx
  const wchar_t *v44; // rbx
  const wchar_t *v45; // rdi
  const WCHAR *v46; // r12
  const WCHAR *v47; // r13
  DWORD SpnW; // eax
  DWORD v50; // eax
  int v51; // eax
  DWORD v52; // eax
  char v53; // r8
  LPWSTR v54; // rax
  __int64 v55; // r9
  int v56; // eax
  unsigned int v57; // r9d
  void *v58; // rcx
  unsigned __int16 *v59; // rdx
  unsigned int v60; // eax
  unsigned int v61; // ecx
  int dwDesiredAccess; // [rsp+20h] [rbp-88h]
  BOOL bInheritHandle[2]; // [rsp+28h] [rbp-80h]
  BOOL bInheritHandlea[2]; // [rsp+28h] [rbp-80h]
  BOOL bInheritHandleb[2]; // [rsp+28h] [rbp-80h]
  DWORD dwOptions[2]; // [rsp+30h] [rbp-78h]
  DWORD dwOptionsa[2]; // [rsp+30h] [rbp-78h]
  SECURITY_INTEGER ptsExpiry; // [rsp+50h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+8h] BYREF
  DWORD pcSpnLength; // [rsp+B8h] [rbp+10h] BYREF
  DWORD v71; // [rsp+C0h] [rbp+18h]
  int v72; // [rsp+C8h] [rbp+20h]

  v72 = a4;
  v71 = a3;
  LOBYTE(pcSpnLength) = a2;
  v6 = 0;
  v7 = a4;
  SystemTimeAsFileTime = 0;
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v9 = a5;
  if ( (*((_BYTE *)a1 + 408) & 4) != 0 && (NlGlobalWinsockPnpAddresses || NlGlobalV6WinsockPnpAddresses) )
  {
    if ( !a3 )
    {
      v10 = 2;
      goto LABEL_11;
    }
    v11 = (unsigned int)((a5 - a1 - 680) / 560) == 0;
  }
  else
  {
    if ( (unsigned int)((a5 - a1 - 680) / 560) )
      goto LABEL_108;
    v11 = a3 == 0;
  }
  if ( v11 )
  {
    v10 = 1;
LABEL_11:
    v12 = 0;
    v13 = 0;
    RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
    if ( !*((_QWORD *)a1 + 63) )
      NlAssertFailed(
        "ClientSession->CsUncServerName != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
        10172,
        v14);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v11 = NlGlobalBindingHandleCount == 0;
    v16 = SystemTimeAsFileTime;
    *(struct _FILETIME *)v9 = SystemTimeAsFileTime;
    *((_DWORD *)v9 + 2) = dwMilliseconds;
    if ( v11 && dword_1800F1C08 != dwMilliseconds )
    {
      dword_1800F1C08 = dwMilliseconds;
      NlGlobalApiTimer = v16;
      if ( !SetEvent(NlGlobalTimerEvent) )
      {
        LastError = GetLastError();
        NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: SetEvent failed %ld\n", LastError);
      }
    }
    if ( !*((_QWORD *)v9 + 2) )
    {
      CurrentProcess = GetCurrentProcess();
      CurrentThread = GetCurrentThread();
      v20 = GetCurrentProcess();
      if ( !DuplicateHandle(v20, CurrentThread, CurrentProcess, (LPHANDLE)v9 + 2, 0, 0, 2u) )
      {
        v21 = GetLastError();
        NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: DuplicateHandle failed %ld\n", v21);
      }
      v22 = RpcMgmtSetCancelTimeout(1);
      if ( v22 )
        NlPrintCsRoutine(
          0x80000u,
          a1,
          L"NlStartApiClientSession: Cannot RpcMgmtSetCancelTimeout: %ld (continuing)\n",
          v22);
      v13 = 0;
    }
    v23 = *((_DWORD *)v9 + 6);
    v24 = *((_DWORD *)v9 + 6) | 1;
    *((_DWORD *)v9 + 6) = v24;
    v25 = v23 & 1;
    if ( v25 )
    {
      if ( (v24 & 2) == 0 )
      {
        v10 = 1;
        goto LABEL_31;
      }
      if ( v10 == 1 )
      {
        v24 &= 0xFFFFFFF9;
        v13 = 2;
        *((_DWORD *)v9 + 6) = v24;
        v12 = 1;
      }
    }
    else
    {
      ++NlGlobalBindingHandleCount;
    }
    if ( v10 == 2 )
    {
      v24 |= 2u;
      *((_DWORD *)v9 + 6) = v24;
    }
LABEL_31:
    if ( (v24 & 4) == 0 && *((_DWORD *)a1 + 71) == 2 )
    {
      if ( (*((_DWORD *)a1 + 79) & 0x40000000) != 0
        || dword_1800F12A4
        && (LOBYTE(v15) = 1,
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl'::`2'::impl,
              v15),
            *((int *)a1 + 79) < 0) )
      {
        v6 = 1;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    if ( v12 )
    {
      v25 = 0;
      NlpSecureChannelUnbind(a1, *((_QWORD *)a1 + 63), "NlStartApiClientSession", 0, *((_QWORD *)v9 + 4), v13);
    }
    if ( (*((_BYTE *)v9 + 24) & 2) != 0 )
    {
      v27 = 0;
    }
    else
    {
      v26 = NtImpersonateAnonymousToken((HANDLE)0xFFFFFFFFFFFFFFFELL);
      v27 = v26;
      if ( v26 < 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NlStartApiClientSession: cannot NtImpersonateAnonymousToken: 0x%lx\n",
          (unsigned int)v26);
LABEL_63:
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
        if ( v27 < 0 || !v6 )
          goto LABEL_107;
        NlPrintCsRoutine(0x80000u, a1, L"NlStartApiClientSession: Try to NlBindingSetAuthInfo\n");
        if ( !*((_QWORD *)a1 + 57) && *((int *)a1 + 79) >= 0 )
        {
          v40 = NlBuildAuthData(a1, v37, v38, v39);
          *((_QWORD *)a1 + 57) = v40;
          if ( !v40 )
          {
            v27 = -1073741801;
LABEL_107:
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
            return (unsigned int)v27;
          }
          v41 = AcquireCredentialsHandleW(0, 0, 2u, 0, v40, 0, 0, (PCredHandle)a1 + 29, &ptsExpiry);
          if ( v41 )
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: AcquireCredentialsHandleW failed 0x%lx\n", v41);
        }
        if ( dword_1800F12A4
          && (LOBYTE(v37) = 1,
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl'::`2'::impl,
                v37),
              *((int *)a1 + 79) < 0) )
        {
          v42 = (LPWSTR *)((char *)a1 + 656);
          v43 = (void *)*((_QWORD *)a1 + 82);
          if ( v43 )
          {
            NetApiBufferFree(v43);
            *v42 = 0;
          }
          v44 = (const wchar_t *)*((_QWORD *)a1 + 63);
          v45 = *(const wchar_t **)(*((_QWORD *)a1 + 34) + 136LL);
          pcSpnLength = 0;
          v46 = v44 + 2;
          if ( wcsncmp_0(v44, L"\\\\", 2u) )
            v46 = v44;
          v47 = v45 + 2;
          if ( wcsncmp_0(v45, L"\\\\", 2u) )
            v47 = v45;
          SpnW = DsMakeSpnW(L"netlogon", v47, v46, 0, 0, &pcSpnLength, 0);
          v27 = SpnW;
          if ( SpnW != 111 )
          {
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: Cannot make Kerberos Auth SPN %lu\n", SpnW);
            if ( v27 > 0 )
              return (unsigned __int16)v27 | 0xC0070000;
            return (unsigned int)v27;
          }
          v50 = NetApiBufferAllocate(2 * pcSpnLength + 2, (LPVOID *)a1 + 82);
          v51 = NetpApiStatusToNtStatus(v50);
          v27 = v51;
          if ( v51 < 0 )
          {
            NlPrintCsRoutine(
              0x100u,
              a1,
              L"NlStartApiClientSession: Cannot allocate memory for SPN %lx\n",
              (unsigned int)v51);
            return (unsigned int)v27;
          }
          v52 = DsMakeSpnW(L"netlogon", v47, v46, 0, 0, &pcSpnLength, *v42);
          v7 = v52;
          if ( v52 )
          {
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: Cannot make Kerberos Auth SPN %lu\n", v52);
            if ( v7 > 0 )
              return (unsigned __int16)v7 | 0xC0070000;
            return (unsigned int)v7;
          }
          v53 = 1;
        }
        else
        {
          v53 = 0;
          v42 = (LPWSTR *)((char *)a1 + 656);
        }
        if ( (unsigned int)((v9 - a1 - 680) / 560) )
        {
          if ( v53 )
          {
            v59 = *v42;
            v58 = 0;
            v57 = 16;
          }
          else
          {
            v57 = 68;
            v58 = (void *)*((_QWORD *)a1 + 57);
            if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
              v59 = (unsigned __int16 *)*((_QWORD *)a1 + 27);
            else
              v59 = *(unsigned __int16 **)(*((_QWORD *)a1 + 34) + 264LL);
          }
          v60 = RpcBindingSetAuthInfoW(*((RPC_BINDING_HANDLE *)v9 + 4), v59, 6u, v57, v58, 1u);
          if ( v60 )
          {
            v27 = NetpApiStatusToNtStatus(v60);
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: Cannot RpcBindingSetAuthInfoW: %ld\n", v61);
            goto LABEL_107;
          }
        }
        else
        {
          if ( v53 )
          {
            v54 = *v42;
            v55 = 0;
          }
          else
          {
            if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
              v54 = (LPWSTR)*((_QWORD *)a1 + 27);
            else
              v54 = *(LPWSTR *)(*((_QWORD *)a1 + 34) + 264LL);
            v55 = *((_QWORD *)a1 + 57);
          }
          v56 = NlBindingSetAuthInfo(*((_QWORD *)a1 + 63), v10, 1, v55, v54);
          v27 = v56;
          if ( v56 < 0 )
          {
            NlPrintCsRoutine(
              0x100u,
              a1,
              L"NlStartApiClientSession: Cannot NlBindingSetAuthInfo: %lx\n",
              (unsigned int)v56);
            goto LABEL_107;
          }
        }
        *((_DWORD *)v9 + 6) |= 4u;
        goto LABEL_107;
      }
    }
    if ( v25 )
      goto LABEL_63;
    v28 = "TCP";
    v29 = "TCP";
    if ( v10 != 2 )
      v29 = "PIPE";
    dwOptions[0] = v71;
    bInheritHandle[0] = (v9 - a1 - 680) / 560;
    NlPrintCsRoutine(
      0x80000u,
      a1,
      L"NlStartApiClientSession: Bind to server %ws (%hs) %ld (Retry: %ld).\n",
      *((_QWORD *)a1 + 63),
      v29,
      *(_QWORD *)bInheritHandle,
      *(_QWORD *)dwOptions);
    if ( !*((_DWORD *)a1 + 71) )
      NlAssertFailed(
        "ClientSession->CsState != CS_IDLE",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
        10377,
        v30);
    v31 = (unsigned __int16 *)*((_QWORD *)a1 + 63);
    if ( (unsigned int)((v9 - a1 - 680) / 560) )
    {
      v35 = NlRpcpBindRpc(v31, dwDesiredAccess, (RPC_BINDING_HANDLE *)v9 + 4);
      if ( !v35 )
      {
        v27 = 0;
        goto LABEL_61;
      }
      *((_QWORD *)v9 + 4) = 0;
      dwOptionsa[0] = NetpApiStatusToNtStatus(v35);
      bInheritHandleb[0] = (v9 - a1 - 680) / 560;
      v27 = dwOptionsa[0];
      NlPrintCsRoutine(
        0x100u,
        a1,
        L"NlStartApiClientSession: Bind to server %ws (%hs) %ld failed 0x%lx.\n",
        *((_QWORD *)a1 + 63),
        v29,
        *(_QWORD *)bInheritHandleb,
        *(_QWORD *)dwOptionsa);
    }
    else
    {
      v32 = NlBindingAddServerToCache(v31, v10);
      v27 = v32;
      if ( v32 >= 0 )
      {
        *((_QWORD *)v9 + 4) = *((_QWORD *)a1 + 63);
        goto LABEL_61;
      }
      if ( v32 == -1073610748 && v10 == 2 )
      {
        v27 = v72;
        v33 = L"NlStartApiClientSession: Bind to server %ws (%hs) %ld failed 0x%lx (Client doesn't support TCP/IP).\n";
        v34 = 0x80000;
      }
      else
      {
        v34 = 256;
        v33 = L"NlStartApiClientSession: Bind to server %ws (%hs) %ld failed 0x%lx.\n";
        v28 = v29;
      }
      dwOptionsa[0] = v32;
      bInheritHandlea[0] = 0;
      NlPrintCsRoutine(v34, a1, v33, *((_QWORD *)a1 + 63), v28, *(_QWORD *)bInheritHandlea, *(_QWORD *)dwOptionsa);
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    *((_DWORD *)v9 + 6) &= 0xFFFFFFF8;
    v36 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 34);
    --NlGlobalBindingHandleCount;
    RtlLeaveCriticalSection(v36 + 10);
    if ( v27 < 0 )
    {
LABEL_62:
      *((_DWORD *)v9 + 10) = *((_DWORD *)a1 + 81);
      goto LABEL_63;
    }
LABEL_61:
    _o_wcsncpy_s((char *)v9 + 44, 258, *((_QWORD *)a1 + 63), 257);
    *((_WORD *)v9 + 279) = 0;
    goto LABEL_62;
  }
LABEL_108:
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800688e0  mov     rax, rsp
0x1800688e3  mov     [rax+20h], r9d
0x1800688e7  mov     [rax+18h], r8d
0x1800688eb  mov     [rax+10h], dl
0x1800688ee  push    rbx
0x1800688ef  push    rbp
0x1800688f0  push    rsi
0x1800688f1  push    rdi
0x1800688f2  push    r12
0x1800688f4  push    r13
0x1800688f6  push    r14
0x1800688f8  push    r15
0x1800688fa  sub     rsp, 68h
0x1800688fe  mov     rsi, rcx
0x180068901  lea     r15, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDcDiscoveryCritSect
0x180068908  xor     r13d, r13d
0x18006890b  mov     rcx, r15; CriticalSection
0x18006890e  mov     edi, r9d
0x180068911  mov     [rax+8], r13
0x180068915  mov     ebx, r8d
0x180068918  call    cs:__imp_RtlEnterCriticalSection
0x18006891e  test    byte ptr [rsi+198h], 4
0x180068925  mov     eax, 2A8h
0x18006892a  mov     r14, [rsp+0A8h+arg_20]
0x180068932  mov     rdx, 0EA0EA0EA0EA0EA1h
0x18006893c  jz      short loc_18006897A
0x18006893e  cmp     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, r13; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180068945  jnz     short loc_180068950
0x180068947  cmp     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, r13; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x18006894e  jz      short loc_18006897A
0x180068950  test    ebx, ebx
0x180068952  jnz     short loc_180068959
0x180068954  lea     ebp, [rbx+2]
0x180068957  jmp     short loc_1800689AC
0x180068959  mov     rcx, r14
0x18006895c  sub     rcx, rsi
0x18006895f  sub     rcx, rax
0x180068962  mov     rax, rdx
0x180068965  imul    rcx
0x180068968  sar     rdx, 5
0x18006896c  mov     rax, rdx
0x18006896f  shr     rax, 3Fh
0x180068973  add     rdx, rax
0x180068976  test    edx, edx
0x180068978  jmp     short loc_1800689A1
0x18006897a  mov     rcx, r14
0x18006897d  sub     rcx, rsi
0x180068980  sub     rcx, rax
0x180068983  mov     rax, rdx
0x180068986  imul    rcx
0x180068989  sar     rdx, 5
0x18006898d  mov     rax, rdx
0x180068990  shr     rax, 3Fh
0x180068994  add     rdx, rax
0x180068997  test    edx, edx
0x180068999  jnz     loc_180069153
0x18006899f  test    ebx, ebx
0x1800689a1  jnz     loc_180069153
0x1800689a7  mov     ebp, 1
0x1800689ac  mov     rcx, r15; CriticalSection
0x1800689af  mov     r12b, r13b
0x1800689b2  mov     ebx, r13d
0x1800689b5  call    cs:__imp_RtlLeaveCriticalSection
0x1800689bb  cmp     [rsi+1F8h], r13
0x1800689c2  jnz     short loc_1800689DD
0x1800689c4  mov     r8d, 27BCh; unsigned int
0x1800689ca  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800689d1  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x1800689d8  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800689dd  mov     rcx, [rsi+110h]
0x1800689e4  add     rcx, 190h; CriticalSection
0x1800689eb  call    cs:__imp_RtlEnterCriticalSection
0x1800689f1  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800689f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800689ff  cmp     cs:?NlGlobalBindingHandleCount@@3KA, r13d; ulong NlGlobalBindingHandleCount
0x180068a06  mov     rax, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x180068a0e  mov     [r14], rax
0x180068a11  mov     ecx, cs:dwMilliseconds
0x180068a17  mov     [r14+8], ecx
0x180068a1b  jnz     short loc_180068A66
0x180068a1d  mov     ecx, cs:dwMilliseconds
0x180068a23  cmp     cs:dword_1800F1C08, ecx
0x180068a29  jz      short loc_180068A66
0x180068a2b  mov     cs:dword_1800F1C08, ecx
0x180068a31  mov     rcx, cs:?NlGlobalTimerEvent@@3PEAXEA; hEvent
0x180068a38  mov     cs:?NlGlobalApiTimer@@3U_TIMER@@A, rax; _TIMER NlGlobalApiTimer
0x180068a3f  call    cs:__imp_SetEvent
0x180068a45  test    eax, eax
0x180068a47  jnz     short loc_180068A66
0x180068a49  call    cs:__imp_GetLastError
0x180068a4f  lea     r8, aNlstartapiclie_0; "NlStartApiClientSession: SetEvent faile"...
0x180068a56  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180068a59  mov     r9d, eax
0x180068a5c  mov     ecx, 100h; unsigned int
0x180068a61  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068a66  cmp     [r14+10h], r13
0x180068a6a  jnz     loc_180068AF7
0x180068a70  call    cs:__imp_GetCurrentProcess
0x180068a76  mov     rdi, rax
0x180068a79  call    cs:__imp_GetCurrentThread
0x180068a7f  mov     rbx, rax
0x180068a82  call    cs:__imp_GetCurrentProcess
0x180068a88  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x180068a90  lea     r9, [r14+10h]; lpTargetHandle
0x180068a94  mov     rcx, rax; hSourceProcessHandle
0x180068a97  mov     [rsp+0A8h+bInheritHandle], r13d; bInheritHandle
0x180068a9c  mov     r8, rdi; hTargetProcessHandle
0x180068a9f  mov     [rsp+0A8h+dwDesiredAccess], r13d; dwDesiredAccess
0x180068aa4  mov     rdx, rbx; hSourceHandle
0x180068aa7  call    cs:__imp_DuplicateHandle
0x180068aad  test    eax, eax
0x180068aaf  jnz     short loc_180068ACE
0x180068ab1  call    cs:__imp_GetLastError
0x180068ab7  lea     r8, aNlstartapiclie_7; "NlStartApiClientSession: DuplicateHandl"...
0x180068abe  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180068ac1  mov     r9d, eax
0x180068ac4  mov     ecx, 100h; unsigned int
0x180068ac9  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068ace  mov     ecx, 1; Timeout
0x180068ad3  call    cs:__imp_RpcMgmtSetCancelTimeout
0x180068ad9  test    eax, eax
0x180068adb  jz      short loc_180068AF4
0x180068add  mov     r9d, eax
0x180068ae0  lea     r8, aNlstartapiclie_9; "NlStartApiClientSession: Cannot RpcMgmt"...
0x180068ae7  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180068aea  mov     ecx, 80000h; unsigned int
0x180068aef  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068af4  mov     ebx, r13d
0x180068af7  mov     eax, [r14+18h]
0x180068afb  mov     dil, al
0x180068afe  or      eax, 1
0x180068b01  mov     [r14+18h], eax
0x180068b05  and     dil, 1
0x180068b09  jnz     short loc_180068B13
0x180068b0b  inc     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x180068b11  jmp     short loc_180068B29
0x180068b13  test    al, 2
0x180068b15  jz      short loc_180068B36
0x180068b17  cmp     ebp, 1
0x180068b1a  jnz     short loc_180068B29
0x180068b1c  and     eax, 0FFFFFFF9h
0x180068b1f  lea     ebx, [rbp+1]
0x180068b22  mov     [r14+18h], eax
0x180068b26  mov     r12b, bpl
0x180068b29  cmp     ebp, 2
0x180068b2c  jnz     short loc_180068B3B
0x180068b2e  or      eax, ebp
0x180068b30  mov     [r14+18h], eax
0x180068b34  jmp     short loc_180068B3B
0x180068b36  mov     ebp, 1
0x180068b3b  test    al, 4
0x180068b3d  jnz     short loc_180068B77
0x180068b3f  cmp     dword ptr [rsi+11Ch], 2
0x180068b46  jnz     short loc_180068B77
0x180068b48  test    dword ptr [rsi+13Ch], 40000000h
0x180068b52  jnz     short loc_180068B74
0x180068b54  cmp     cs:dword_1800F12A4, r13d
0x180068b5b  jz      short loc_180068B77
0x180068b5d  mov     dl, 1
0x180068b5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos> `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl(void)'::`2'::impl
0x180068b66  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180068b6b  cmp     [rsi+13Ch], r13d
0x180068b72  jge     short loc_180068B77
0x180068b74  mov     r13b, 1
0x180068b77  mov     rcx, [rsi+110h]
0x180068b7e  add     rcx, 190h; CriticalSection
0x180068b85  call    cs:__imp_RtlLeaveCriticalSection
0x180068b8b  test    r12b, r12b
0x180068b8e  jz      short loc_180068BB9
0x180068b90  mov     rax, [r14+20h]
0x180068b94  lea     r8, aNlstartapiclie_1; "NlStartApiClientSession"
0x180068b9b  mov     rdx, [rsi+1F8h]
0x180068ba2  xor     dil, dil
0x180068ba5  mov     [rsp+0A8h+bInheritHandle], ebx
0x180068ba9  xor     r9d, r9d
0x180068bac  mov     rcx, rsi
0x180068baf  mov     qword ptr [rsp+0A8h+dwDesiredAccess], rax
0x180068bb4  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x180068bb9  test    byte ptr [r14+18h], 2
0x180068bbe  jnz     short loc_180068BEC
0x180068bc0  mov     rcx, 0FFFFFFFFFFFFFFFEh; Thread
0x180068bc7  call    cs:__imp_NtImpersonateAnonymousToken
0x180068bcd  mov     ebx, eax
0x180068bcf  test    eax, eax
0x180068bd1  jns     short loc_180068BEE
0x180068bd3  mov     r8d, eax
0x180068bd6  lea     rdx, aNlstartapiclie_11; "NlStartApiClientSession: cannot NtImper"...
0x180068bdd  mov     ecx, 100h; unsigned int
0x180068be2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180068be7  jmp     loc_180068DA8
0x180068bec  xor     ebx, ebx
0x180068bee  test    dil, dil
0x180068bf1  jnz     loc_180068DA8
0x180068bf7  mov     r9, [rsi+1F8h]
0x180068bfe  lea     r12, aTcp_0; "TCP"
0x180068c05  mov     rcx, r14
0x180068c08  lea     r8, aNlstartapiclie_2; "NlStartApiClientSession: Bind to server"...
0x180068c0f  sub     rcx, rsi
0x180068c12  mov     rax, 0EA0EA0EA0EA0EA1h
0x180068c1c  sub     rcx, 2A8h
0x180068c23  mov     r15, r12
0x180068c26  imul    rcx
0x180068c29  mov     ecx, 80000h; unsigned int
0x180068c2e  mov     rdi, rdx
0x180068c31  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180068c34  sar     rdi, 5
0x180068c38  mov     rax, rdi
0x180068c3b  shr     rax, 3Fh
0x180068c3f  add     rdi, rax
0x180068c42  lea     rax, aPipe; "PIPE"
0x180068c49  cmp     ebp, 2
0x180068c4c  cmovnz  r15, rax
0x180068c50  mov     eax, [rsp+0A8h+arg_10]
0x180068c57  mov     [rsp+0A8h+dwOptions], eax
0x180068c5b  mov     [rsp+0A8h+bInheritHandle], edi
0x180068c5f  mov     qword ptr [rsp+0A8h+dwDesiredAccess], r15; int
0x180068c64  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068c69  cmp     dword ptr [rsi+11Ch], 0
0x180068c70  jnz     short loc_180068C8B
0x180068c72  mov     r8d, 2889h; unsigned int
0x180068c78  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180068c7f  lea     rcx, aClientsessionC_7; "ClientSession->CsState != CS_IDLE"
0x180068c86  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180068c8b  mov     rcx, [rsi+1F8h]; NetworkAddr
0x180068c92  test    edi, edi
0x180068c94  jnz     short loc_180068CF7
0x180068c96  mov     edx, ebp
0x180068c98  call    cs:__imp_NlBindingAddServerToCache
0x180068c9e  mov     ebx, eax
0x180068ca0  test    eax, eax
0x180068ca2  jns     short loc_180068CE7
0x180068ca4  cmp     eax, 0C0020004h
0x180068ca9  jnz     short loc_180068CC5
0x180068cab  cmp     ebp, 2
0x180068cae  jnz     short loc_180068CC5
0x180068cb0  mov     ebx, [rsp+0A8h+arg_18]
0x180068cb7  lea     r8, aNlstartapiclie_8; "NlStartApiClientSession: Bind to server"...
0x180068cbe  mov     ecx, 80000h
0x180068cc3  jmp     short loc_180068CD4
0x180068cc5  mov     ecx, 100h
0x180068cca  lea     r8, aNlstartapiclie; "NlStartApiClientSession: Bind to server"...
0x180068cd1  mov     r12, r15
0x180068cd4  mov     [rsp+0A8h+dwOptions], eax
0x180068cd8  mov     [rsp+0A8h+bInheritHandle], 0
0x180068ce0  mov     qword ptr [rsp+0A8h+dwDesiredAccess], r12
0x180068ce5  jmp     short loc_180068D32
0x180068ce7  mov     rax, [rsi+1F8h]
0x180068cee  mov     [r14+20h], rax
0x180068cf2  jmp     loc_180068D79
0x180068cf7  lea     rbx, [r14+20h]
0x180068cfb  mov     qword ptr [rsp+0A8h+bInheritHandle], rbx; Binding
0x180068d00  call    NlRpcpBindRpc
0x180068d05  test    eax, eax
0x180068d07  jz      short loc_180068D77
0x180068d09  mov     ecx, eax
0x180068d0b  mov     qword ptr [rbx], 0
0x180068d12  call    NetpApiStatusToNtStatus
0x180068d17  mov     [rsp+0A8h+dwOptions], eax
0x180068d1b  lea     r8, aNlstartapiclie; "NlStartApiClientSession: Bind to server"...
0x180068d22  mov     [rsp+0A8h+bInheritHandle], edi
0x180068d26  mov     ebx, eax
0x180068d28  mov     qword ptr [rsp+0A8h+dwDesiredAccess], r15
0x180068d2d  mov     ecx, 100h; unsigned int
0x180068d32  mov     r9, [rsi+1F8h]
0x180068d39  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180068d3c  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068d41  mov     rcx, [rsi+110h]
0x180068d48  mov     edi, 190h
0x180068d4d  add     rcx, rdi; CriticalSection
0x180068d50  call    cs:__imp_RtlEnterCriticalSection
0x180068d56  and     dword ptr [r14+18h], 0FFFFFFF8h
0x180068d5b  mov     rcx, [rsi+110h]
0x180068d62  dec     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x180068d68  add     rcx, rdi; CriticalSection
0x180068d6b  call    cs:__imp_RtlLeaveCriticalSection
0x180068d71  test    ebx, ebx
0x180068d73  js      short loc_180068D9E
0x180068d75  jmp     short loc_180068D79
0x180068d77  xor     ebx, ebx
0x180068d79  mov     r8, [rsi+1F8h]
0x180068d80  lea     rcx, [r14+2Ch]
0x180068d84  mov     r9d, 101h
0x180068d8a  lea     edx, [r9+1]
0x180068d8e  call    cs:__imp__o_wcsncpy_s
0x180068d94  xor     eax, eax
0x180068d96  mov     [r14+22Eh], ax
0x180068d9e  mov     eax, [rsi+144h]
0x180068da4  mov     [r14+28h], eax
0x180068da8  mov     rcx, [rsi+110h]
0x180068daf  add     rcx, 190h; CriticalSection
0x180068db6  call    cs:__imp_RtlEnterCriticalSection
0x180068dbc  test    ebx, ebx
0x180068dbe  js      loc_18006913A
0x180068dc4  test    r13b, r13b
0x180068dc7  jz      loc_18006913A
0x180068dcd  lea     r8, aNlstartapiclie_10; "NlStartApiClientSession: Try to NlBindi"...
0x180068dd4  mov     rdx, rsi; struct _CLIENT_SESSION *
0x180068dd7  mov     ecx, 80000h; unsigned int
0x180068ddc  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068de1  cmp     qword ptr [rsi+1C8h], 0
  ... truncated ...
```
