# R_DhcpServerSetConfigVQ

- ea: `0x1800302a0`
- end: `0x180030dbd`
- name: `R_DhcpServerSetConfigVQ`
- size: `2845`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180030290`

## callees

- `0x180002040`
- `0x180002854`
- `0x18000323c`
- `0x1800055ec`
- `0x180005844`
- `0x18002efe8`
- `0x18002f1e4`
- `0x1800302a0`
- `0x180030dc4`
- `0x180062310`
- `0x1800623a4`
- `0x18008f418`
- `0x18008f540`
- `0x18009b7a0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800303ad`
- `ADVAPI32!RegSetValueExW` at `0x18003040c`
- `ADVAPI32!RegSetValueExW` at `0x180030454`
- `ADVAPI32!RegSetValueExW` at `0x1800304b2`
- `ADVAPI32!RegSetValueExW` at `0x180030544`
- `ADVAPI32!RegSetValueExW` at `0x1800306e5`
- `ADVAPI32!RegSetValueExW` at `0x18003087c`
- `ADVAPI32!RegSetValueExW` at `0x180030b04`
- `ADVAPI32!RegSetValueExW` at `0x180030b64`
- `ADVAPI32!RegSetValueExW` at `0x180030bb5`
- `ADVAPI32!RegSetValueExW` at `0x180030c28`
- `ADVAPI32!RegSetValueExW` at `0x180030c95`
- `ADVAPI32!RegSetValueExW` at `0x1800303ad`
- `ADVAPI32!RegSetValueExW` at `0x18003040c`
- `ADVAPI32!RegSetValueExW` at `0x180030454`
- `ADVAPI32!RegSetValueExW` at `0x1800304b2`
- `ADVAPI32!RegSetValueExW` at `0x180030544`
- `ADVAPI32!RegSetValueExW` at `0x1800306e5`
- `ADVAPI32!RegSetValueExW` at `0x18003087c`
- `ADVAPI32!RegSetValueExW` at `0x180030b04`
- `ADVAPI32!RegSetValueExW` at `0x180030b64`
- `ADVAPI32!RegSetValueExW` at `0x180030bb5`
- `ADVAPI32!RegSetValueExW` at `0x180030c28`
- `ADVAPI32!RegSetValueExW` at `0x180030c95`
- `RPCRT4!RpcImpersonateClient` at `0x1800305b9`
- `RPCRT4!RpcImpersonateClient` at `0x180030761`
- `RPCRT4!RpcImpersonateClient` at `0x1800305b9`
- `RPCRT4!RpcImpersonateClient` at `0x180030761`
- `RPCRT4!RpcRevertToSelf` at `0x18003062d`
- `RPCRT4!RpcRevertToSelf` at `0x18003064e`
- `RPCRT4!RpcRevertToSelf` at `0x1800307d1`
- `RPCRT4!RpcRevertToSelf` at `0x1800307f5`
- `RPCRT4!RpcRevertToSelf` at `0x18003062d`
- `RPCRT4!RpcRevertToSelf` at `0x18003064e`
- `RPCRT4!RpcRevertToSelf` at `0x1800307d1`
- `RPCRT4!RpcRevertToSelf` at `0x1800307f5`
- `KERNEL32!HeapAlloc` at `0x1800308cc`
- `KERNEL32!HeapAlloc` at `0x180030991`
- `KERNEL32!HeapAlloc` at `0x1800308cc`
- `KERNEL32!HeapAlloc` at `0x180030991`
- `KERNEL32!SetEvent` at `0x180030d8a`
- `KERNEL32!SetEvent` at `0x180030d8a`
- `KERNEL32!GetLastError` at `0x1800305d5`
- `KERNEL32!GetLastError` at `0x18003077d`
- `KERNEL32!GetLastError` at `0x180030959`
- `KERNEL32!GetLastError` at `0x180030d9a`
- `KERNEL32!GetLastError` at `0x1800305d5`
- `KERNEL32!GetLastError` at `0x18003077d`
- `KERNEL32!GetLastError` at `0x180030959`
- `KERNEL32!GetLastError` at `0x180030d9a`
- `KERNEL32!EnterCriticalSection` at `0x1800309e1`
- `KERNEL32!EnterCriticalSection` at `0x180030a57`
- `KERNEL32!EnterCriticalSection` at `0x1800309e1`
- `KERNEL32!EnterCriticalSection` at `0x180030a57`
- `KERNEL32!LeaveCriticalSection` at `0x180030a44`
- `KERNEL32!LeaveCriticalSection` at `0x180030a92`
- `KERNEL32!LeaveCriticalSection` at `0x180030a44`
- `KERNEL32!LeaveCriticalSection` at `0x180030a92`
- `KERNEL32!HeapFree` at `0x180030a02`
- `KERNEL32!HeapFree` at `0x180030a2a`
- `KERNEL32!HeapFree` at `0x180030a78`
- `KERNEL32!HeapFree` at `0x180030d11`
- `KERNEL32!HeapFree` at `0x180030d33`
- `KERNEL32!HeapFree` at `0x180030d50`
- `KERNEL32!HeapFree` at `0x180030d6d`
- `KERNEL32!HeapFree` at `0x180030a02`
- `KERNEL32!HeapFree` at `0x180030a2a`
- `KERNEL32!HeapFree` at `0x180030a78`
- `KERNEL32!HeapFree` at `0x180030d11`
- `KERNEL32!HeapFree` at `0x180030d33`
- `KERNEL32!HeapFree` at `0x180030d50`
- `KERNEL32!HeapFree` at `0x180030d6d`

## string_xrefs

- `0x1800306cf`: `DatabasePath`
- `0x180030866`: `BackupDatabasePath`
- `0x180030396`: `APIProtocolSupport`

## pseudocode

```c
__int64 __fastcall R_DhcpServerSetConfigVQ(__int64 a1, int a2, __int64 a3)
{
  char *v4; // rbp
  char *v5; // rsi
  unsigned int LastError; // ebx
  DWORD cbData; // ecx
  const BYTE *v10; // rax
  __int64 v11; // r13
  const WCHAR *v12; // rcx
  __int64 v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  __int64 v17; // rax
  RPC_STATUS v18; // r14d
  _QWORD *v19; // rcx
  __int64 v20; // rax
  int v21; // edx
  const BYTE *v22; // rcx
  __int64 v23; // rax
  const WCHAR *v24; // rcx
  __int64 v25; // rax
  RPC_STATUS v26; // r15d
  const BYTE *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r15
  SIZE_T v30; // r15
  char *v31; // rax
  SIZE_T v32; // rdx
  signed __int64 v33; // r9
  char *v34; // rcx
  char v35; // al
  wchar_t *v36; // r14
  _DWORD *v37; // r14
  _DWORD *v38; // r14
  DWORD v39; // eax
  void *lpMem; // [rsp+38h] [rbp-40h]
  void *v41; // [rsp+40h] [rbp-38h]
  int v42; // [rsp+98h] [rbp+20h]

  lpMem = 0;
  v4 = 0;
  v41 = 0;
  v5 = 0;
  v42 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_29e438781bd734b298acb188cdd8d55c_Traceguids);
  LastError = DhcpApiAccessCheck(0xA0000000);
  if ( LastError )
    goto LABEL_9;
  if ( !a2 )
    return LastError;
  if ( (a2 & 1) != 0 )
  {
    if ( !*(_DWORD *)a3 )
    {
LABEL_8:
      LastError = 87;
      goto LABEL_9;
    }
    LastError = RegSetValueExW(DhcpGlobalRegParam, L"APIProtocolSupport", 0, 4u, (const BYTE *)a3, 4u);
    if ( LastError )
      goto LABEL_9;
    DhcpGlobalRpcProtocols = *(_DWORD *)a3;
  }
  if ( (a2 & 0x200) != 0 )
  {
    if ( *(_DWORD *)(a3 + 52) > 5u )
      goto LABEL_8;
    LastError = RegSetValueExW(DhcpGlobalRegParam, L"DetectConflictRetries", 0, 4u, (const BYTE *)(a3 + 52), 4u);
    if ( LastError )
      goto LABEL_9;
    DhcpGlobalDetectConflictRetries = *(_DWORD *)(a3 + 52);
  }
  if ( (a2 & 0x800) != 0 )
  {
    LastError = RegSetValueExW(DhcpGlobalRegParam, L"ActivityLogFlag", 0, 4u, (const BYTE *)(a3 + 72), 4u);
    if ( LastError )
      goto LABEL_9;
    DhcpGlobalAuditLogFlag = *(_DWORD *)(a3 + 72);
  }
  if ( (a2 & 0x400) == 0 )
    goto LABEL_26;
  cbData = *(_DWORD *)(a3 + 56);
  if ( cbData > 0x100000 )
    goto LABEL_8;
  v10 = *(const BYTE **)(a3 + 64);
  if ( !v10 || (LastError = RegSetValueExW(DhcpGlobalRegParam, L"BootFileTable", 0, 7u, v10, cbData)) == 0 )
  {
LABEL_26:
    v11 = -1;
    if ( (a2 & 2) == 0 )
      goto LABEL_38;
    v12 = *(const WCHAR **)(a3 + 8);
    if ( !v12 )
      goto LABEL_8;
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( !v13 )
      goto LABEL_8;
    if ( (unsigned int)IsStringTroublesome(v12) )
    {
      LastError = 123;
      goto LABEL_9;
    }
    v14 = *(const BYTE **)(a3 + 8);
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)&v14[2 * v15] );
    LastError = RegSetValueExW(DhcpGlobalRegParam, L"DatabaseName", 0, 1u, v14, 2 * v15 + 2);
    if ( !LastError )
    {
      lpMem = (void *)DhcpUnicodeToOem(*(PCWSTR *)(a3 + 8));
      if ( !lpMem )
      {
        LastError = 8;
        goto LABEL_9;
      }
LABEL_38:
      if ( (a2 & 4) != 0 )
      {
        v16 = *(const WCHAR **)(a3 + 16);
        if ( !v16 )
          goto LABEL_64;
        v17 = -1;
        do
          ++v17;
        while ( v16[v17] );
        if ( !v17 )
          goto LABEL_64;
        if ( (unsigned int)IsStringTroublesome(v16) )
        {
LABEL_44:
          LastError = 123;
          goto LABEL_144;
        }
        v18 = RpcImpersonateClient(0);
        if ( !(unsigned int)CreateDirectoryPathW(*(LPCWSTR *)(a3 + 16)) )
        {
          LastError = GetLastError();
          if ( LastError != 183 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_LS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                (unsigned int)&WPP_29e438781bd734b298acb188cdd8d55c_Traceguids,
                LastError,
                *(_QWORD *)(a3 + 16));
            }
            if ( !v18 )
              RpcRevertToSelf();
            goto LABEL_144;
          }
        }
        LastError = DhcpAddServiceAceToDir(*(LPWSTR *)(a3 + 16));
        if ( !v18 && RpcRevertToSelf() )
          goto LABEL_144;
        if ( LastError )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_144;
          }
          v20 = *(_QWORD *)(a3 + 16);
          v21 = 18;
          goto LABEL_58;
        }
        v22 = *(const BYTE **)(a3 + 16);
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)&v22[2 * v23] );
        LastError = RegSetValueExW(DhcpGlobalRegParam, L"DatabasePath", 0, 2u, v22, 2 * v23 + 2);
        if ( LastError )
          goto LABEL_144;
        v41 = (void *)DhcpUnicodeToOem(*(PCWSTR *)(a3 + 16));
        if ( !v41 )
        {
          LastError = 8;
          goto LABEL_144;
        }
      }
      if ( (a2 & 8) == 0 )
        goto LABEL_115;
      v24 = *(const WCHAR **)(a3 + 24);
      if ( v24 )
      {
        v25 = -1;
        do
          ++v25;
        while ( v24[v25] );
        if ( v25 )
        {
          if ( (unsigned int)IsStringTroublesome(v24) )
            goto LABEL_44;
          v26 = RpcImpersonateClient(0);
          if ( !(unsigned int)CreateDirectoryPathW(*(LPCWSTR *)(a3 + 24)) )
          {
            LastError = GetLastError();
            if ( LastError != 183 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                WPP_SF_LS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  19,
                  (unsigned int)&WPP_29e438781bd734b298acb188cdd8d55c_Traceguids,
                  LastError,
                  *(_QWORD *)(a3 + 24));
              }
              if ( !v26 )
                RpcRevertToSelf();
              goto LABEL_144;
            }
          }
          LastError = DhcpAddServiceAceToDir(*(LPWSTR *)(a3 + 24));
          if ( !v26 && RpcRevertToSelf() )
            goto LABEL_144;
          if ( LastError )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_144;
            }
            v20 = *(_QWORD *)(a3 + 24);
            v21 = 20;
LABEL_58:
            WPP_SF_LS(v19[2], v21, (unsigned int)&WPP_29e438781bd734b298acb188cdd8d55c_Traceguids, LastError, v20);
            goto LABEL_144;
          }
          v27 = *(const BYTE **)(a3 + 24);
          v28 = -1;
          do
            ++v28;
          while ( *(_WORD *)&v27[2 * v28] );
          LastError = RegSetValueExW(DhcpGlobalRegParam, L"BackupDatabasePath", 0, 2u, v27, 2 * v28 + 2);
          if ( LastError )
            goto LABEL_144;
          v4 = (char *)DhcpUnicodeToOem(*(PCWSTR *)(a3 + 24));
          if ( !v4 )
            goto LABEL_89;
          v29 = -1;
          do
            ++v29;
          while ( v4[v29] );
          v30 = v29 + 2;
          v31 = (char *)HeapAlloc(gDhcpHeap, 8u, v30);
          v5 = v31;
          if ( !v31 )
          {
            LastError = 8;
            goto LABEL_144;
          }
          if ( v30 )
          {
            if ( v30 <= 0x7FFFFFFF )
            {
              v32 = v30;
              v33 = v4 - v31;
              v34 = v31;
              do
              {
                if ( !(2147483646 - v30 + v32) )
                  break;
                v35 = v34[v33];
                if ( !v35 )
                  break;
                *v34++ = v35;
                --v32;
              }
              while ( v32 );
              v31 = v34 - 1;
              if ( v32 )
                v31 = v34;
            }
            *v31 = 0;
          }
          StringCbCatA(v5, v30, "\\");
          if ( !(unsigned int)CreateDirectoryPathOem(v5) )
          {
            LastError = GetLastError();
            if ( LastError != 183 )
              goto LABEL_144;
            LastError = 0;
          }
          do
            ++v11;
          while ( v4[v11] );
          if ( !HeapAlloc(gDhcpHeap, 8u, 2 * v11 + 18) )
          {
LABEL_89:
            LastError = 8;
            goto LABEL_144;
          }
          v36 = (wchar_t *)DhcpOemToUnicode(v4);
          StringCchCatW(v36, v11 + 9, L"\\");
          StringCchCatW(v36, v11 + 9, L"DhcpCfg");
          EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
          if ( DhcpGlobalOemBackupPath )
            HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalOemBackupPath);
          DhcpGlobalOemBackupPath = v4;
          if ( DhcpGlobalOemJetBackupPath )
            HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalOemJetBackupPath);
          DhcpGlobalOemJetBackupPath = v5;
          LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
          EnterCriticalSection(&DhcpGlobalRegCritSect);
          if ( DhcpGlobalBackupConfigFileName )
            HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalBackupConfigFileName);
          DhcpGlobalBackupConfigFileName = v36;
          LeaveCriticalSection(&DhcpGlobalRegCritSect);
LABEL_115:
          if ( (a2 & 0x10) != 0 )
          {
            v37 = (_DWORD *)(a3 + 32);
            if ( !*(_DWORD *)(a3 + 32) )
            {
LABEL_117:
              LastError = 87;
              goto LABEL_118;
            }
            if ( 60000 * *v37 / 0xEA60u != *v37 )
            {
LABEL_120:
              LastError = 534;
              goto LABEL_118;
            }
            v4 = 0;
            v5 = 0;
            LastError = RegSetValueExW(DhcpGlobalRegParam, L"BackupInterval", 0, 4u, (const BYTE *)(a3 + 32), 4u);
            if ( LastError )
              goto LABEL_144;
            v42 = 1;
            DhcpGlobalBackupInterval = 60000 * *v37;
          }
          if ( (a2 & 0x20) != 0 )
          {
            v4 = 0;
            v5 = 0;
            LastError = RegSetValueExW(DhcpGlobalRegParam, L"DatabaseLoggingFlag", 0, 4u, (const BYTE *)(a3 + 36), 4u);
            if ( LastError )
              goto LABEL_144;
            DhcpGlobalDatabaseLoggingFlag = *(_DWORD *)(a3 + 36);
          }
          if ( (a2 & 0x40) != 0 )
          {
            v4 = 0;
            v5 = 0;
            LastError = RegSetValueExW(DhcpGlobalRegParam, L"RestoreFlag", 0, 4u, (const BYTE *)(a3 + 40), 4u);
            if ( LastError )
              goto LABEL_144;
            *(_DWORD *)&DhcpGlobalRestoreFlag = *(_DWORD *)(a3 + 40);
          }
          if ( (a2 & 0x80u) != 0 )
          {
            v38 = (_DWORD *)(a3 + 44);
            if ( !*(_DWORD *)(a3 + 44) )
              goto LABEL_117;
            if ( 60000 * *v38 / 0xEA60u != *v38 )
              goto LABEL_120;
            v4 = 0;
            v5 = 0;
            LastError = RegSetValueExW(
                          DhcpGlobalRegParam,
                          L"DatabaseCleanupInterval",
                          0,
                          4u,
                          (const BYTE *)(a3 + 44),
                          4u);
            if ( LastError )
              goto LABEL_144;
            v42 = 1;
            DhcpGlobalCleanupInterval = 60000 * *v38;
          }
          if ( (a2 & 0x100) != 0 )
          {
            DhcpGlobalDebugFlag = *(_DWORD *)(a3 + 48);
            v4 = 0;
            v5 = 0;
            LastError = RegSetValueExW(DhcpGlobalRegParam, L"DebugFlag", 0, 4u, (const BYTE *)(a3 + 48), 4u);
            if ( LastError )
              goto LABEL_144;
          }
          if ( (unsigned int)Feature_Servicing_DhcpServerSetConfigFix__private_IsEnabledDeviceUsageNoInline() )
          {
            v4 = 0;
            v5 = 0;
            if ( (a2 & 0x3000) != 0 )
              LastError = 20138;
LABEL_144:
            if ( lpMem )
              HeapFree(gDhcpHeap, 0, lpMem);
            if ( v41 )
              HeapFree(gDhcpHeap, 0, v41);
            if ( v4 )
              HeapFree(gDhcpHeap, 0, v4);
            if ( v5 )
              HeapFree(gDhcpHeap, 0, v5);
            if ( v42 && !SetEvent(DhcpGlobalRecomputeTimerEvent) )
            {
              v39 = GetLastError();
              if ( LastError )
                goto LABEL_9;
              LastError = v39;
            }
            if ( !LastError )
              return LastError;
            goto LABEL_9;
          }
          if ( (a2 & 0x1000) == 0 || !*(_DWORD *)(a3 + 76) )
          {
            v4 = 0;
            v5 = 0;
            if ( (a2 & 0x2000) == 0 || !*(_DWORD *)(a3 + 80) )
              goto LABEL_144;
          }
          LastError = 20138;
LABEL_118:
          v4 = 0;
          v5 = 0;
          goto LABEL_144;
        }
      }
LABEL_64:
      LastError = 87;
      goto LABEL_144;
    }
  }
LABEL_9:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_29e438781bd734b298acb188cdd8d55c_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800302a0  mov     [rsp+arg_0], rbx
0x1800302a5  mov     [rsp+arg_8], rbp
0x1800302aa  mov     [rsp+arg_10], rsi
0x1800302af  push    rdi
0x1800302b0  push    r12
0x1800302b2  push    r13
0x1800302b4  push    r14
0x1800302b6  push    r15
0x1800302b8  sub     rsp, 50h
0x1800302bc  xor     r15d, r15d
0x1800302bf  mov     rdi, r8
0x1800302c2  mov     [rsp+78h+lpMem], r15
0x1800302c7  mov     ebp, r15d
0x1800302ca  mov     [rsp+78h+var_38], r15
0x1800302cf  mov     esi, r15d
0x1800302d2  mov     [rsp+78h+arg_18], r15d
0x1800302da  mov     r12d, edx
0x1800302dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800302e4  lea     rax, WPP_GLOBAL_Control
0x1800302eb  cmp     rcx, rax
0x1800302ee  jz      short loc_18003030D
0x1800302f0  test    dword ptr [rcx+1Ch], 200h
0x1800302f7  jz      short loc_18003030D
0x1800302f9  mov     rcx, [rcx+10h]
0x1800302fd  lea     edx, [r15+10h]
0x180030301  lea     r8, WPP_29e438781bd734b298acb188cdd8d55c_Traceguids
0x180030308  call    WPP_SF_
0x18003030d  mov     ecx, 0A0000000h
0x180030312  call    DhcpApiAccessCheck
0x180030317  mov     ebx, eax
0x180030319  test    eax, eax
0x18003031b  jnz     short loc_18003033A
0x18003031d  test    r12d, r12d
0x180030320  jz      short loc_18003036E
0x180030322  lea     r13d, [rax+4]
0x180030326  test    r12b, 1
0x18003032a  jz      loc_1800303CB
0x180030330  cmp     [rdi], r15d
0x180030333  jnz     short loc_18003038F
0x180030335  mov     ebx, 57h ; 'W'
0x18003033a  lea     r12, WPP_GLOBAL_Control
0x180030341  mov     rcx, cs:WPP_GLOBAL_Control
0x180030348  cmp     rcx, r12
0x18003034b  jz      short loc_18003036E
0x18003034d  test    dword ptr [rcx+1Ch], 200h
0x180030354  jz      short loc_18003036E
0x180030356  mov     rcx, [rcx+10h]
0x18003035a  lea     r8, WPP_29e438781bd734b298acb188cdd8d55c_Traceguids
0x180030361  mov     edx, 1Ah
0x180030366  mov     r9d, ebx
0x180030369  call    WPP_SF_D
0x18003036e  lea     r11, [rsp+78h+var_28]
0x180030373  mov     eax, ebx
0x180030375  mov     rbx, [r11+30h]
0x180030379  mov     rbp, [r11+38h]
0x18003037d  mov     rsi, [r11+40h]
0x180030381  mov     rsp, r11
0x180030384  pop     r15
0x180030386  pop     r14
0x180030388  pop     r13
0x18003038a  pop     r12
0x18003038c  pop     rdi
0x18003038d  retn
0x18003038f  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180030396  lea     rdx, aApiprotocolsup; "APIProtocolSupport"
0x18003039d  mov     [rsp+78h+cbData], r13d; cbData
0x1800303a2  mov     r9d, r13d; dwType
0x1800303a5  xor     r8d, r8d; Reserved
0x1800303a8  mov     [rsp+78h+lpData], rdi; lpData
0x1800303ad  call    cs:__imp_RegSetValueExW
0x1800303b4  nop     dword ptr [rax+rax+00h]
0x1800303b9  mov     ebx, eax
0x1800303bb  test    eax, eax
0x1800303bd  jnz     loc_18003033A
0x1800303c3  mov     eax, [rdi]
0x1800303c5  mov     cs:DhcpGlobalRpcProtocols, eax
0x1800303cb  bt      r12d, 9
0x1800303d0  jnb     short loc_18003042B
0x1800303d2  lea     r14, [rdi+34h]
0x1800303d6  mov     ecx, [r14]
0x1800303d9  lea     eax, [rcx+1]
0x1800303dc  cmp     eax, 1
0x1800303df  jb      loc_180030335
0x1800303e5  cmp     ecx, 5
0x1800303e8  ja      loc_180030335
0x1800303ee  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x1800303f5  lea     rdx, aDetectconflict; "DetectConflictRetries"
0x1800303fc  mov     [rsp+78h+cbData], r13d; cbData
0x180030401  mov     r9d, r13d; dwType
0x180030404  xor     r8d, r8d; Reserved
0x180030407  mov     [rsp+78h+lpData], r14; lpData
0x18003040c  call    cs:__imp_RegSetValueExW
0x180030413  nop     dword ptr [rax+rax+00h]
0x180030418  mov     ebx, eax
0x18003041a  test    eax, eax
0x18003041c  jnz     loc_18003033A
0x180030422  mov     eax, [r14]
0x180030425  mov     cs:DhcpGlobalDetectConflictRetries, eax
0x18003042b  bt      r12d, 0Bh
0x180030430  jnb     short loc_180030473
0x180030432  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180030439  lea     r14, [rdi+48h]
0x18003043d  mov     [rsp+78h+cbData], r13d; cbData
0x180030442  lea     rdx, aActivitylogfla; "ActivityLogFlag"
0x180030449  mov     r9d, r13d; dwType
0x18003044c  mov     [rsp+78h+lpData], r14; lpData
0x180030451  xor     r8d, r8d; Reserved
0x180030454  call    cs:__imp_RegSetValueExW
0x18003045b  nop     dword ptr [rax+rax+00h]
0x180030460  mov     ebx, eax
0x180030462  test    eax, eax
0x180030464  jnz     loc_18003033A
0x18003046a  mov     eax, [r14]
0x18003046d  mov     cs:DhcpGlobalAuditLogFlag, eax
0x180030473  bt      r12d, 0Ah
0x180030478  jnb     short loc_1800304C8
0x18003047a  mov     ecx, [rdi+38h]
0x18003047d  cmp     ecx, 100000h
0x180030483  ja      loc_180030335
0x180030489  mov     rax, [rdi+40h]
0x18003048d  test    rax, rax
0x180030490  jz      short loc_1800304C8
0x180030492  mov     [rsp+78h+cbData], ecx; cbData
0x180030496  lea     rdx, aBootfiletable; "BootFileTable"
0x18003049d  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x1800304a4  mov     r9d, 7; dwType
0x1800304aa  xor     r8d, r8d; Reserved
0x1800304ad  mov     [rsp+78h+lpData], rax; lpData
0x1800304b2  call    cs:__imp_RegSetValueExW
0x1800304b9  nop     dword ptr [rax+rax+00h]
0x1800304be  mov     ebx, eax
0x1800304c0  test    eax, eax
0x1800304c2  jnz     loc_18003033A
0x1800304c8  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800304cc  test    r12b, 2
0x1800304d0  jz      loc_180030577
0x1800304d6  mov     rcx, [rdi+8]; lpWideCharStr
0x1800304da  test    rcx, rcx
0x1800304dd  jz      loc_180030335
0x1800304e3  mov     rax, r13
0x1800304e6  inc     rax
0x1800304e9  cmp     [rcx+rax*2], r15w
0x1800304ee  jnz     short loc_1800304E6
0x1800304f0  test    rax, rax
0x1800304f3  jz      loc_180030335
0x1800304f9  call    IsStringTroublesome
0x1800304fe  test    eax, eax
0x180030500  jz      short loc_18003050C
0x180030502  mov     ebx, 7Bh ; '{'
0x180030507  jmp     loc_18003033A
0x18003050c  mov     rcx, [rdi+8]
0x180030510  mov     rax, r13
0x180030513  inc     rax
0x180030516  cmp     [rcx+rax*2], r15w
0x18003051b  jnz     short loc_180030513
0x18003051d  lea     eax, ds:2[rax*2]
0x180030524  mov     r9d, 1; dwType
0x18003052a  mov     [rsp+78h+cbData], eax; cbData
0x18003052e  lea     rdx, aDatabasename_0; "DatabaseName"
0x180030535  mov     [rsp+78h+lpData], rcx; lpData
0x18003053a  xor     r8d, r8d; Reserved
0x18003053d  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180030544  call    cs:__imp_RegSetValueExW
0x18003054b  nop     dword ptr [rax+rax+00h]
0x180030550  mov     ebx, eax
0x180030552  test    eax, eax
0x180030554  jnz     loc_18003033A
0x18003055a  mov     rcx, [rdi+8]; SourceString
0x18003055e  xor     edx, edx
0x180030560  call    DhcpUnicodeToOem
0x180030565  mov     [rsp+78h+lpMem], rax
0x18003056a  test    rax, rax
0x18003056d  jnz     short loc_180030577
0x18003056f  lea     ebx, [rax+8]
0x180030572  jmp     loc_18003033A
0x180030577  test    r12b, 4
0x18003057b  jz      loc_180030725
0x180030581  mov     rcx, [rdi+10h]; lpWideCharStr
0x180030585  test    rcx, rcx
0x180030588  jz      loc_18003071B
0x18003058e  mov     rax, r13
0x180030591  inc     rax
0x180030594  cmp     [rcx+rax*2], r15w
0x180030599  jnz     short loc_180030591
0x18003059b  test    rax, rax
0x18003059e  jz      loc_18003071B
0x1800305a4  call    IsStringTroublesome
0x1800305a9  test    eax, eax
0x1800305ab  jz      short loc_1800305B7
0x1800305ad  mov     ebx, 7Bh ; '{'
0x1800305b2  jmp     loc_180030CF4
0x1800305b7  xor     ecx, ecx; BindingHandle
0x1800305b9  call    cs:__imp_RpcImpersonateClient
0x1800305c0  nop     dword ptr [rax+rax+00h]
0x1800305c5  mov     rcx, [rdi+10h]; lpPathName
0x1800305c9  mov     r14d, eax
0x1800305cc  call    CreateDirectoryPathW
0x1800305d1  test    eax, eax
0x1800305d3  jnz     short loc_18003063E
0x1800305d5  call    cs:__imp_GetLastError
0x1800305dc  nop     dword ptr [rax+rax+00h]
0x1800305e1  mov     ebx, eax
0x1800305e3  cmp     eax, 0B7h
0x1800305e8  jz      short loc_18003063E
0x1800305ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305f1  lea     r12, WPP_GLOBAL_Control
0x1800305f8  cmp     rcx, r12
0x1800305fb  jz      short loc_180030624
0x1800305fd  test    byte ptr [rcx+1Ch], 10h
0x180030601  jz      short loc_180030624
0x180030603  mov     rax, [rdi+10h]
0x180030607  lea     r8, WPP_29e438781bd734b298acb188cdd8d55c_Traceguids
0x18003060e  mov     rcx, [rcx+10h]
0x180030612  mov     edx, 11h
0x180030617  mov     r9d, ebx
0x18003061a  mov     [rsp+78h+lpData], rax
0x18003061f  call    WPP_SF_LS
0x180030624  test    r14d, r14d
0x180030627  jnz     loc_180030CFB
0x18003062d  call    cs:__imp_RpcRevertToSelf
0x180030634  nop     dword ptr [rax+rax+00h]
0x180030639  jmp     loc_180030CFB
0x18003063e  mov     rcx, [rdi+10h]; pObjectName
0x180030642  call    DhcpAddServiceAceToDir
0x180030647  mov     ebx, eax
0x180030649  test    r14d, r14d
0x18003064c  jnz     short loc_180030662
0x18003064e  call    cs:__imp_RpcRevertToSelf
0x180030655  nop     dword ptr [rax+rax+00h]
0x18003065a  test    eax, eax
0x18003065c  jnz     loc_180030CF4
0x180030662  test    ebx, ebx
0x180030664  jz      short loc_1800306AD
0x180030666  mov     rcx, cs:WPP_GLOBAL_Control
0x18003066d  lea     r12, WPP_GLOBAL_Control
0x180030674  cmp     rcx, r12
0x180030677  jz      loc_180030CFB
0x18003067d  test    byte ptr [rcx+1Ch], 10h
0x180030681  jz      loc_180030CFB
0x180030687  mov     rax, [rdi+10h]
0x18003068b  mov     edx, 12h
0x180030690  mov     rcx, [rcx+10h]
0x180030694  lea     r8, WPP_29e438781bd734b298acb188cdd8d55c_Traceguids
0x18003069b  mov     r9d, ebx
0x18003069e  mov     [rsp+78h+lpData], rax
0x1800306a3  call    WPP_SF_LS
0x1800306a8  jmp     loc_180030CFB
0x1800306ad  mov     rcx, [rdi+10h]
0x1800306b1  mov     rax, r13
0x1800306b4  inc     rax
0x1800306b7  cmp     [rcx+rax*2], r15w
0x1800306bc  jnz     short loc_1800306B4
0x1800306be  lea     eax, ds:2[rax*2]
0x1800306c5  mov     r9d, 2; dwType
0x1800306cb  mov     [rsp+78h+cbData], eax; cbData
0x1800306cf  lea     rdx, aDatabasepath; "DatabasePath"
0x1800306d6  mov     [rsp+78h+lpData], rcx; lpData
0x1800306db  xor     r8d, r8d; Reserved
0x1800306de  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x1800306e5  call    cs:__imp_RegSetValueExW
0x1800306ec  nop     dword ptr [rax+rax+00h]
0x1800306f1  mov     ebx, eax
0x1800306f3  test    eax, eax
0x1800306f5  jnz     loc_180030CF4
0x1800306fb  mov     rcx, [rdi+10h]; SourceString
0x1800306ff  xor     edx, edx
0x180030701  call    DhcpUnicodeToOem
0x180030706  mov     [rsp+78h+var_38], rax
0x18003070b  test    rax, rax
0x18003070e  jnz     short loc_180030725
0x180030710  lea     ebx, [rax+8]
0x180030713  xor     r15d, r15d
0x180030716  jmp     loc_180030CF4
0x18003071b  mov     ebx, 57h ; 'W'
0x180030720  jmp     loc_180030CF4
0x180030725  mov     r14d, 8
0x18003072b  xor     r15d, r15d
0x18003072e  test    r14b, r12b
0x180030731  jz      loc_180030A9E
0x180030737  mov     rcx, [rdi+18h]; lpWideCharStr
0x18003073b  test    rcx, rcx
0x18003073e  jz      short loc_18003071B
0x180030740  mov     rax, r13
0x180030743  inc     rax
0x180030746  cmp     [rcx+rax*2], r15w
0x18003074b  jnz     short loc_180030743
0x18003074d  test    rax, rax
0x180030750  jz      short loc_18003071B
0x180030752  call    IsStringTroublesome
0x180030757  test    eax, eax
0x180030759  jnz     loc_1800305AD
0x18003075f  xor     ecx, ecx; BindingHandle
0x180030761  call    cs:__imp_RpcImpersonateClient
0x180030768  nop     dword ptr [rax+rax+00h]
0x18003076d  mov     rcx, [rdi+18h]; lpPathName
0x180030771  mov     r15d, eax
0x180030774  call    CreateDirectoryPathW
0x180030779  test    eax, eax
0x18003077b  jnz     short loc_1800307E5
0x18003077d  call    cs:__imp_GetLastError
  ... truncated ...
```
