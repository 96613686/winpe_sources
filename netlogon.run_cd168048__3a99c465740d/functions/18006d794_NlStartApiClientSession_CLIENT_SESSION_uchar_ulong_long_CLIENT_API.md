# NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)

- ea: `0x18006d794`
- end: `0x18006e0c9`
- name: `?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z`
- size: `2357`
- prototype: `__int64 __usercall@<rax>(struct _CLIENT_SESSION *@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, int@<r9d>, struct _CLIENT_API *)`
- caller_count: `13`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002346c`
- `0x18002a8e0`
- `0x180030078`
- `0x180031a3c`
- `0x180033f80`
- `0x180036420`
- `0x1800369f8`
- `0x180036c94`
- `0x180038f68`
- `0x180039ac4`
- `0x18005b2b0`
- `0x18005c514`
- `0x18006e50c`

## callees

- `0x1800067fc`
- `0x180007518`
- `0x18000d7a0`
- `0x18000dd00`
- `0x18003b8d4`
- `0x180040f18`
- `0x180056150`
- `0x18006d794`
- `0x180070260`
- `0x180088be4`
- `0x1800901e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18006dca8`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18006dca8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006d90b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006d90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d9a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d9a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d948`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d948`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006d966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d957`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006d991`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006d991`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d8bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d8bf`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x18006d9c9`
- `RPCRT4!RpcMgmtSetCancelTimeout` at `0x18006d9c9`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18006e050`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x18006e050`
- `logoncli!NlBindingSetAuthInfo` at `0x18006dfd8`
- `logoncli!NlBindingSetAuthInfo` at `0x18006dfd8`
- `logoncli!NlBindingAddServerToCache` at `0x18006dba0`
- `logoncli!NlBindingAddServerToCache` at `0x18006dba0`
- `ntdll!NtImpersonateAnonymousToken` at `0x18006dac9`
- `ntdll!NtImpersonateAnonymousToken` at `0x18006dac9`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d86f`
- `ntdll!RtlLeaveCriticalSection` at `0x18006da81`
- `ntdll!RtlLeaveCriticalSection` at `0x18006dc7f`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e095`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e0a9`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d86f`
- `ntdll!RtlLeaveCriticalSection` at `0x18006da81`
- `ntdll!RtlLeaveCriticalSection` at `0x18006dc7f`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e095`
- `ntdll!RtlLeaveCriticalSection` at `0x18006e0a9`
- `ntdll!RtlEnterCriticalSection` at `0x18006d7cc`
- `ntdll!RtlEnterCriticalSection` at `0x18006d8ab`
- `ntdll!RtlEnterCriticalSection` at `0x18006dc5e`
- `ntdll!RtlEnterCriticalSection` at `0x18006dcd6`
- `ntdll!RtlEnterCriticalSection` at `0x18006d7cc`
- `ntdll!RtlEnterCriticalSection` at `0x18006d8ab`
- `ntdll!RtlEnterCriticalSection` at `0x18006dc5e`
- `ntdll!RtlEnterCriticalSection` at `0x18006dcd6`
- `netutils!NetApiBufferFree` at `0x18006ddce`
- `netutils!NetApiBufferFree` at `0x18006ddce`
- `netutils!NetApiBufferAllocate` at `0x18006deb7`
- `netutils!NetApiBufferAllocate` at `0x18006deb7`
- `DSPARSE!DsMakeSpnW` at `0x18006de68`
- `DSPARSE!DsMakeSpnW` at `0x18006df13`
- `DSPARSE!DsMakeSpnW` at `0x18006de68`
- `DSPARSE!DsMakeSpnW` at `0x18006df13`

## string_xrefs

- `0x18006d88a`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006db80`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006dade`: `NlStartApiClientSession: cannot NtImpersonateAnonymousToken: 0x%lx\n`

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
  void *v38; // rax
  unsigned int v39; // eax
  LPWSTR *v40; // r15
  void *v41; // rcx
  const wchar_t *v42; // rbx
  const wchar_t *v43; // rdi
  const WCHAR *v44; // r12
  const WCHAR *v45; // r13
  DWORD SpnW; // eax
  DWORD v48; // eax
  int v49; // eax
  DWORD v50; // eax
  char v51; // r8
  LPWSTR v52; // rax
  __int64 v53; // r9
  int v54; // eax
  unsigned int v55; // r9d
  void *v56; // rcx
  unsigned __int16 *v57; // rdx
  unsigned int v58; // eax
  unsigned int v59; // ecx
  int dwDesiredAccess; // [rsp+20h] [rbp-88h]
  BOOL bInheritHandle[2]; // [rsp+28h] [rbp-80h]
  BOOL bInheritHandlea[2]; // [rsp+28h] [rbp-80h]
  BOOL bInheritHandleb[2]; // [rsp+28h] [rbp-80h]
  DWORD dwOptions[2]; // [rsp+30h] [rbp-78h]
  DWORD dwOptionsa[2]; // [rsp+30h] [rbp-78h]
  SECURITY_INTEGER ptsExpiry; // [rsp+50h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+8h] BYREF
  DWORD pcSpnLength; // [rsp+B8h] [rbp+10h] BYREF
  DWORD v69; // [rsp+C0h] [rbp+18h]
  int v70; // [rsp+C8h] [rbp+20h]

  v70 = a4;
  v69 = a3;
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
        0x27BCu,
        v14);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v11 = NlGlobalBindingHandleCount == 0;
    v16 = SystemTimeAsFileTime;
    *(struct _FILETIME *)v9 = SystemTimeAsFileTime;
    *((_DWORD *)v9 + 2) = dwMilliseconds;
    if ( v11 && dword_1800F8BD8 != dwMilliseconds )
    {
      dword_1800F8BD8 = dwMilliseconds;
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
        || dword_1800F82A4
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
          v38 = NlBuildAuthData(a1);
          *((_QWORD *)a1 + 57) = v38;
          if ( !v38 )
          {
            v27 = -1073741801;
LABEL_107:
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
            return (unsigned int)v27;
          }
          v39 = AcquireCredentialsHandleW(0, 0, 2u, 0, v38, 0, 0, (PCredHandle)a1 + 29, &ptsExpiry);
          if ( v39 )
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: AcquireCredentialsHandleW failed 0x%lx\n", v39);
        }
        if ( dword_1800F82A4
          && (LOBYTE(v37) = 1,
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl'::`2'::impl,
                v37),
              *((int *)a1 + 79) < 0) )
        {
          v40 = (LPWSTR *)((char *)a1 + 656);
          v41 = (void *)*((_QWORD *)a1 + 82);
          if ( v41 )
          {
            NetApiBufferFree(v41);
            *v40 = 0;
          }
          v42 = (const wchar_t *)*((_QWORD *)a1 + 63);
          v43 = *(const wchar_t **)(*((_QWORD *)a1 + 34) + 136LL);
          pcSpnLength = 0;
          v44 = v42 + 2;
          if ( wcsncmp_0(v42, L"\\\\", 2u) )
            v44 = v42;
          v45 = v43 + 2;
          if ( wcsncmp_0(v43, L"\\\\", 2u) )
            v45 = v43;
          SpnW = DsMakeSpnW(L"netlogon", v45, v44, 0, 0, &pcSpnLength, 0);
          v27 = SpnW;
          if ( SpnW != 111 )
          {
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: Cannot make Kerberos Auth SPN %lu\n", SpnW);
            if ( v27 > 0 )
              return (unsigned __int16)v27 | 0xC0070000;
            return (unsigned int)v27;
          }
          v48 = NetApiBufferAllocate(2 * pcSpnLength + 2, (LPVOID *)a1 + 82);
          v49 = NetpApiStatusToNtStatus(v48);
          v27 = v49;
          if ( v49 < 0 )
          {
            NlPrintCsRoutine(
              0x100u,
              a1,
              L"NlStartApiClientSession: Cannot allocate memory for SPN %lx\n",
              (unsigned int)v49);
            return (unsigned int)v27;
          }
          v50 = DsMakeSpnW(L"netlogon", v45, v44, 0, 0, &pcSpnLength, *v40);
          v7 = v50;
          if ( v50 )
          {
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: Cannot make Kerberos Auth SPN %lu\n", v50);
            if ( v7 > 0 )
              return (unsigned __int16)v7 | 0xC0070000;
            return (unsigned int)v7;
          }
          v51 = 1;
        }
        else
        {
          v51 = 0;
          v40 = (LPWSTR *)((char *)a1 + 656);
        }
        if ( (unsigned int)((v9 - a1 - 680) / 560) )
        {
          if ( v51 )
          {
            v57 = *v40;
            v56 = 0;
            v55 = 16;
          }
          else
          {
            v55 = 68;
            v56 = (void *)*((_QWORD *)a1 + 57);
            if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
              v57 = (unsigned __int16 *)*((_QWORD *)a1 + 27);
            else
              v57 = *(unsigned __int16 **)(*((_QWORD *)a1 + 34) + 264LL);
          }
          v58 = RpcBindingSetAuthInfoW(*((RPC_BINDING_HANDLE *)v9 + 4), v57, 6u, v55, v56, 1u);
          if ( v58 )
          {
            v27 = NetpApiStatusToNtStatus(v58);
            NlPrintCsRoutine(0x100u, a1, L"NlStartApiClientSession: Cannot RpcBindingSetAuthInfoW: %ld\n", v59);
            goto LABEL_107;
          }
        }
        else
        {
          if ( v51 )
          {
            v52 = *v40;
            v53 = 0;
          }
          else
          {
            if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
              v52 = (LPWSTR)*((_QWORD *)a1 + 27);
            else
              v52 = *(LPWSTR *)(*((_QWORD *)a1 + 34) + 264LL);
            v53 = *((_QWORD *)a1 + 57);
          }
          v54 = NlBindingSetAuthInfo(*((_QWORD *)a1 + 63), v10, 1, v53, v52);
          v27 = v54;
          if ( v54 < 0 )
          {
            NlPrintCsRoutine(
              0x100u,
              a1,
              L"NlStartApiClientSession: Cannot NlBindingSetAuthInfo: %lx\n",
              (unsigned int)v54);
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
    dwOptions[0] = v69;
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
        0x2889u,
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
        v27 = v70;
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
    _o_wcsncpy_s((char *)v9 + 44, 258, *((_QWORD *)a1 + 63));
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
0x18006d794  mov     rax, rsp
0x18006d797  mov     [rax+20h], r9d
0x18006d79b  mov     [rax+18h], r8d
0x18006d79f  mov     [rax+10h], dl
0x18006d7a2  push    rbx
0x18006d7a3  push    rbp
0x18006d7a4  push    rsi
0x18006d7a5  push    rdi
0x18006d7a6  push    r12
0x18006d7a8  push    r13
0x18006d7aa  push    r14
0x18006d7ac  push    r15
0x18006d7ae  sub     rsp, 68h
0x18006d7b2  mov     rsi, rcx
0x18006d7b5  lea     r15, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDcDiscoveryCritSect
0x18006d7bc  xor     r13d, r13d
0x18006d7bf  mov     rcx, r15; CriticalSection
0x18006d7c2  mov     edi, r9d
0x18006d7c5  mov     [rax+8], r13
0x18006d7c9  mov     ebx, r8d
0x18006d7cc  call    cs:__imp_RtlEnterCriticalSection
0x18006d7d3  nop     dword ptr [rax+rax+00h]
0x18006d7d8  test    byte ptr [rsi+198h], 4
0x18006d7df  mov     eax, 2A8h
0x18006d7e4  mov     r14, [rsp+0A8h+arg_20]
0x18006d7ec  mov     rdx, 0EA0EA0EA0EA0EA1h
0x18006d7f6  jz      short loc_18006D834
0x18006d7f8  cmp     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, r13; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x18006d7ff  jnz     short loc_18006D80A
0x18006d801  cmp     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, r13; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x18006d808  jz      short loc_18006D834
0x18006d80a  test    ebx, ebx
0x18006d80c  jnz     short loc_18006D813
0x18006d80e  lea     ebp, [rbx+2]
0x18006d811  jmp     short loc_18006D866
0x18006d813  mov     rcx, r14
0x18006d816  sub     rcx, rsi
0x18006d819  sub     rcx, rax
0x18006d81c  mov     rax, rdx
0x18006d81f  imul    rcx
0x18006d822  sar     rdx, 5
0x18006d826  mov     rax, rdx
0x18006d829  shr     rax, 3Fh
0x18006d82d  add     rdx, rax
0x18006d830  test    edx, edx
0x18006d832  jmp     short loc_18006D85B
0x18006d834  mov     rcx, r14
0x18006d837  sub     rcx, rsi
0x18006d83a  sub     rcx, rax
0x18006d83d  mov     rax, rdx
0x18006d840  imul    rcx
0x18006d843  sar     rdx, 5
0x18006d847  mov     rax, rdx
0x18006d84a  shr     rax, 3Fh
0x18006d84e  add     rdx, rax
0x18006d851  test    edx, edx
0x18006d853  jnz     loc_18006E0A6
0x18006d859  test    ebx, ebx
0x18006d85b  jnz     loc_18006E0A6
0x18006d861  mov     ebp, 1
0x18006d866  mov     rcx, r15; CriticalSection
0x18006d869  mov     r12b, r13b
0x18006d86c  mov     ebx, r13d
0x18006d86f  call    cs:__imp_RtlLeaveCriticalSection
0x18006d876  nop     dword ptr [rax+rax+00h]
0x18006d87b  cmp     [rsi+1F8h], r13
0x18006d882  jnz     short loc_18006D89D
0x18006d884  mov     r8d, 27BCh; unsigned int
0x18006d88a  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006d891  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18006d898  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006d89d  mov     rcx, [rsi+110h]
0x18006d8a4  add     rcx, 190h; CriticalSection
0x18006d8ab  call    cs:__imp_RtlEnterCriticalSection
0x18006d8b2  nop     dword ptr [rax+rax+00h]
0x18006d8b7  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006d8bf  call    cs:__imp_GetSystemTimeAsFileTime
0x18006d8c6  nop     dword ptr [rax+rax+00h]
0x18006d8cb  cmp     cs:?NlGlobalBindingHandleCount@@3KA, r13d; ulong NlGlobalBindingHandleCount
0x18006d8d2  mov     rax, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x18006d8da  mov     [r14], rax
0x18006d8dd  mov     ecx, cs:dwMilliseconds
0x18006d8e3  mov     [r14+8], ecx
0x18006d8e7  jnz     short loc_18006D93E
0x18006d8e9  mov     ecx, cs:dwMilliseconds
0x18006d8ef  cmp     cs:dword_1800F8BD8, ecx
0x18006d8f5  jz      short loc_18006D93E
0x18006d8f7  mov     cs:dword_1800F8BD8, ecx
0x18006d8fd  mov     rcx, cs:?NlGlobalTimerEvent@@3PEAXEA; hEvent
0x18006d904  mov     cs:?NlGlobalApiTimer@@3U_TIMER@@A, rax; _TIMER NlGlobalApiTimer
0x18006d90b  call    cs:__imp_SetEvent
0x18006d912  nop     dword ptr [rax+rax+00h]
0x18006d917  test    eax, eax
0x18006d919  jnz     short loc_18006D93E
0x18006d91b  call    cs:__imp_GetLastError
0x18006d922  nop     dword ptr [rax+rax+00h]
0x18006d927  lea     r8, aNlstartapiclie_0; "NlStartApiClientSession: SetEvent faile"...
0x18006d92e  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006d931  mov     r9d, eax
0x18006d934  mov     ecx, 100h; unsigned int
0x18006d939  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d93e  cmp     [r14+10h], r13
0x18006d942  jnz     loc_18006D9F3
0x18006d948  call    cs:__imp_GetCurrentProcess
0x18006d94f  nop     dword ptr [rax+rax+00h]
0x18006d954  mov     rdi, rax
0x18006d957  call    cs:__imp_GetCurrentThread
0x18006d95e  nop     dword ptr [rax+rax+00h]
0x18006d963  mov     rbx, rax
0x18006d966  call    cs:__imp_GetCurrentProcess
0x18006d96d  nop     dword ptr [rax+rax+00h]
0x18006d972  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x18006d97a  lea     r9, [r14+10h]; lpTargetHandle
0x18006d97e  mov     rcx, rax; hSourceProcessHandle
0x18006d981  mov     [rsp+0A8h+bInheritHandle], r13d; bInheritHandle
0x18006d986  mov     r8, rdi; hTargetProcessHandle
0x18006d989  mov     [rsp+0A8h+dwDesiredAccess], r13d; dwDesiredAccess
0x18006d98e  mov     rdx, rbx; hSourceHandle
0x18006d991  call    cs:__imp_DuplicateHandle
0x18006d998  nop     dword ptr [rax+rax+00h]
0x18006d99d  test    eax, eax
0x18006d99f  jnz     short loc_18006D9C4
0x18006d9a1  call    cs:__imp_GetLastError
0x18006d9a8  nop     dword ptr [rax+rax+00h]
0x18006d9ad  lea     r8, aNlstartapiclie_7; "NlStartApiClientSession: DuplicateHandl"...
0x18006d9b4  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006d9b7  mov     r9d, eax
0x18006d9ba  mov     ecx, 100h; unsigned int
0x18006d9bf  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d9c4  mov     ecx, 1; Timeout
0x18006d9c9  call    cs:__imp_RpcMgmtSetCancelTimeout
0x18006d9d0  nop     dword ptr [rax+rax+00h]
0x18006d9d5  test    eax, eax
0x18006d9d7  jz      short loc_18006D9F0
0x18006d9d9  mov     r9d, eax
0x18006d9dc  lea     r8, aNlstartapiclie_9; "NlStartApiClientSession: Cannot RpcMgmt"...
0x18006d9e3  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006d9e6  mov     ecx, 80000h; unsigned int
0x18006d9eb  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006d9f0  mov     ebx, r13d
0x18006d9f3  mov     eax, [r14+18h]
0x18006d9f7  mov     dil, al
0x18006d9fa  or      eax, 1
0x18006d9fd  mov     [r14+18h], eax
0x18006da01  and     dil, 1
0x18006da05  jnz     short loc_18006DA0F
0x18006da07  inc     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x18006da0d  jmp     short loc_18006DA25
0x18006da0f  test    al, 2
0x18006da11  jz      short loc_18006DA32
0x18006da13  cmp     ebp, 1
0x18006da16  jnz     short loc_18006DA25
0x18006da18  and     eax, 0FFFFFFF9h
0x18006da1b  lea     ebx, [rbp+1]
0x18006da1e  mov     [r14+18h], eax
0x18006da22  mov     r12b, bpl
0x18006da25  cmp     ebp, 2
0x18006da28  jnz     short loc_18006DA37
0x18006da2a  or      eax, ebp
0x18006da2c  mov     [r14+18h], eax
0x18006da30  jmp     short loc_18006DA37
0x18006da32  mov     ebp, 1
0x18006da37  test    al, 4
0x18006da39  jnz     short loc_18006DA73
0x18006da3b  cmp     dword ptr [rsi+11Ch], 2
0x18006da42  jnz     short loc_18006DA73
0x18006da44  test    dword ptr [rsi+13Ch], 40000000h
0x18006da4e  jnz     short loc_18006DA70
0x18006da50  cmp     cs:dword_1800F82A4, r13d
0x18006da57  jz      short loc_18006DA73
0x18006da59  mov     dl, 1
0x18006da5b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos> `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl(void)'::`2'::impl
0x18006da62  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18006da67  cmp     [rsi+13Ch], r13d
0x18006da6e  jge     short loc_18006DA73
0x18006da70  mov     r13b, 1
0x18006da73  mov     rcx, [rsi+110h]
0x18006da7a  add     rcx, 190h; CriticalSection
0x18006da81  call    cs:__imp_RtlLeaveCriticalSection
0x18006da88  nop     dword ptr [rax+rax+00h]
0x18006da8d  test    r12b, r12b
0x18006da90  jz      short loc_18006DABB
0x18006da92  mov     rax, [r14+20h]
0x18006da96  lea     r8, aNlstartapiclie_1; "NlStartApiClientSession"
0x18006da9d  mov     rdx, [rsi+1F8h]
0x18006daa4  xor     dil, dil
0x18006daa7  mov     [rsp+0A8h+bInheritHandle], ebx
0x18006daab  xor     r9d, r9d
0x18006daae  mov     rcx, rsi
0x18006dab1  mov     qword ptr [rsp+0A8h+dwDesiredAccess], rax
0x18006dab6  call    ?NlpSecureChannelUnbind@@YAXPEAU_CLIENT_SESSION@@PEBGPEBDKPEAXW4_NL_RPC_BINDING@@@Z; NlpSecureChannelUnbind(_CLIENT_SESSION *,ushort const *,char const *,ulong,void *,_NL_RPC_BINDING)
0x18006dabb  test    byte ptr [r14+18h], 2
0x18006dac0  jnz     short loc_18006DAF4
0x18006dac2  mov     rcx, 0FFFFFFFFFFFFFFFEh; Thread
0x18006dac9  call    cs:__imp_NtImpersonateAnonymousToken
0x18006dad0  nop     dword ptr [rax+rax+00h]
0x18006dad5  mov     ebx, eax
0x18006dad7  test    eax, eax
0x18006dad9  jns     short loc_18006DAF6
0x18006dadb  mov     r8d, eax
0x18006dade  lea     rdx, aNlstartapiclie_11; "NlStartApiClientSession: cannot NtImper"...
0x18006dae5  mov     ecx, 100h; unsigned int
0x18006daea  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006daef  jmp     loc_18006DCC8
0x18006daf4  xor     ebx, ebx
0x18006daf6  test    dil, dil
0x18006daf9  jnz     loc_18006DCC8
0x18006daff  mov     r9, [rsi+1F8h]
0x18006db06  lea     r12, aTcp_0; "TCP"
0x18006db0d  mov     rcx, r14
0x18006db10  lea     r8, aNlstartapiclie_2; "NlStartApiClientSession: Bind to server"...
0x18006db17  sub     rcx, rsi
0x18006db1a  mov     rax, 0EA0EA0EA0EA0EA1h
0x18006db24  sub     rcx, 2A8h
0x18006db2b  mov     r15, r12
0x18006db2e  imul    rcx
0x18006db31  mov     ecx, 80000h; unsigned int
0x18006db36  mov     rdi, rdx
0x18006db39  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006db3c  sar     rdi, 5
0x18006db40  mov     rax, rdi
0x18006db43  shr     rax, 3Fh
0x18006db47  add     rdi, rax
0x18006db4a  lea     rax, aPipe; "PIPE"
0x18006db51  cmp     ebp, 2
0x18006db54  cmovnz  r15, rax
0x18006db58  mov     eax, [rsp+0A8h+arg_10]
0x18006db5f  mov     [rsp+0A8h+dwOptions], eax
0x18006db63  mov     [rsp+0A8h+bInheritHandle], edi
0x18006db67  mov     qword ptr [rsp+0A8h+dwDesiredAccess], r15; int
0x18006db6c  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006db71  cmp     dword ptr [rsi+11Ch], 0
0x18006db78  jnz     short loc_18006DB93
0x18006db7a  mov     r8d, 2889h; unsigned int
0x18006db80  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006db87  lea     rcx, aClientsessionC_7; "ClientSession->CsState != CS_IDLE"
0x18006db8e  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006db93  mov     rcx, [rsi+1F8h]; NetworkAddr
0x18006db9a  test    edi, edi
0x18006db9c  jnz     short loc_18006DC05
0x18006db9e  mov     edx, ebp
0x18006dba0  call    cs:__imp_NlBindingAddServerToCache
0x18006dba7  nop     dword ptr [rax+rax+00h]
0x18006dbac  mov     ebx, eax
0x18006dbae  test    eax, eax
0x18006dbb0  jns     short loc_18006DBF5
0x18006dbb2  cmp     eax, 0C0020004h
0x18006dbb7  jnz     short loc_18006DBD3
0x18006dbb9  cmp     ebp, 2
0x18006dbbc  jnz     short loc_18006DBD3
0x18006dbbe  mov     ebx, [rsp+0A8h+arg_18]
0x18006dbc5  lea     r8, aNlstartapiclie_8; "NlStartApiClientSession: Bind to server"...
0x18006dbcc  mov     ecx, 80000h
0x18006dbd1  jmp     short loc_18006DBE2
0x18006dbd3  mov     ecx, 100h
0x18006dbd8  lea     r8, aNlstartapiclie; "NlStartApiClientSession: Bind to server"...
0x18006dbdf  mov     r12, r15
0x18006dbe2  mov     [rsp+0A8h+dwOptions], eax
0x18006dbe6  mov     [rsp+0A8h+bInheritHandle], 0
0x18006dbee  mov     qword ptr [rsp+0A8h+dwDesiredAccess], r12
0x18006dbf3  jmp     short loc_18006DC40
0x18006dbf5  mov     rax, [rsi+1F8h]
0x18006dbfc  mov     [r14+20h], rax
0x18006dc00  jmp     loc_18006DC93
0x18006dc05  lea     rbx, [r14+20h]
0x18006dc09  mov     qword ptr [rsp+0A8h+bInheritHandle], rbx; Binding
0x18006dc0e  call    NlRpcpBindRpc
0x18006dc13  test    eax, eax
0x18006dc15  jz      short loc_18006DC91
0x18006dc17  mov     ecx, eax
0x18006dc19  mov     qword ptr [rbx], 0
0x18006dc20  call    NetpApiStatusToNtStatus
0x18006dc25  mov     [rsp+0A8h+dwOptions], eax
0x18006dc29  lea     r8, aNlstartapiclie; "NlStartApiClientSession: Bind to server"...
0x18006dc30  mov     [rsp+0A8h+bInheritHandle], edi
0x18006dc34  mov     ebx, eax
0x18006dc36  mov     qword ptr [rsp+0A8h+dwDesiredAccess], r15
0x18006dc3b  mov     ecx, 100h; unsigned int
0x18006dc40  mov     r9, [rsi+1F8h]
0x18006dc47  mov     rdx, rsi; struct _CLIENT_SESSION *
0x18006dc4a  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006dc4f  mov     rcx, [rsi+110h]
0x18006dc56  mov     edi, 190h
0x18006dc5b  add     rcx, rdi; CriticalSection
0x18006dc5e  call    cs:__imp_RtlEnterCriticalSection
0x18006dc65  nop     dword ptr [rax+rax+00h]
0x18006dc6a  and     dword ptr [r14+18h], 0FFFFFFF8h
0x18006dc6f  mov     rcx, [rsi+110h]
0x18006dc76  dec     cs:?NlGlobalBindingHandleCount@@3KA; ulong NlGlobalBindingHandleCount
0x18006dc7c  add     rcx, rdi; CriticalSection
0x18006dc7f  call    cs:__imp_RtlLeaveCriticalSection
0x18006dc86  nop     dword ptr [rax+rax+00h]
0x18006dc8b  test    ebx, ebx
0x18006dc8d  js      short loc_18006DCBE
0x18006dc8f  jmp     short loc_18006DC93
0x18006dc91  xor     ebx, ebx
0x18006dc93  mov     r8, [rsi+1F8h]
0x18006dc9a  lea     rcx, [r14+2Ch]
0x18006dc9e  mov     r9d, 101h
0x18006dca4  lea     edx, [r9+1]
  ... truncated ...
```
