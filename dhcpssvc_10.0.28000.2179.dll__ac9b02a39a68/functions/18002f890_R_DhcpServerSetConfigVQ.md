# R_DhcpServerSetConfigVQ

- ea: `0x18002f890`
- end: `0x180030362`
- name: `R_DhcpServerSetConfigVQ`
- size: `2770`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002f880`

## callees

- `0x180002030`
- `0x18000282c`
- `0x180003228`
- `0x1800055e8`
- `0x180005834`
- `0x18002e7b4`
- `0x18002f890`
- `0x180030368`
- `0x180062094`
- `0x180062128`
- `0x18008f5b4`
- `0x18008f6d8`
- `0x18009c43c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002f99d`
- `ADVAPI32!RegSetValueExW` at `0x18002f9fb`
- `ADVAPI32!RegSetValueExW` at `0x18002fa42`
- `ADVAPI32!RegSetValueExW` at `0x18002fa9f`
- `ADVAPI32!RegSetValueExW` at `0x18002fb31`
- `ADVAPI32!RegSetValueExW` at `0x18002fccf`
- `ADVAPI32!RegSetValueExW` at `0x18002fe65`
- `ADVAPI32!RegSetValueExW` at `0x1800300e6`
- `ADVAPI32!RegSetValueExW` at `0x180030145`
- `ADVAPI32!RegSetValueExW` at `0x180030195`
- `ADVAPI32!RegSetValueExW` at `0x180030205`
- `ADVAPI32!RegSetValueExW` at `0x18003026d`
- `ADVAPI32!RegSetValueExW` at `0x18002f99d`
- `ADVAPI32!RegSetValueExW` at `0x18002f9fb`
- `ADVAPI32!RegSetValueExW` at `0x18002fa42`
- `ADVAPI32!RegSetValueExW` at `0x18002fa9f`
- `ADVAPI32!RegSetValueExW` at `0x18002fb31`
- `ADVAPI32!RegSetValueExW` at `0x18002fccf`
- `ADVAPI32!RegSetValueExW` at `0x18002fe65`
- `ADVAPI32!RegSetValueExW` at `0x1800300e6`
- `ADVAPI32!RegSetValueExW` at `0x180030145`
- `ADVAPI32!RegSetValueExW` at `0x180030195`
- `ADVAPI32!RegSetValueExW` at `0x180030205`
- `ADVAPI32!RegSetValueExW` at `0x18003026d`
- `RPCRT4!RpcImpersonateClient` at `0x18002fba6`
- `RPCRT4!RpcImpersonateClient` at `0x18002fd4a`
- `RPCRT4!RpcImpersonateClient` at `0x18002fba6`
- `RPCRT4!RpcImpersonateClient` at `0x18002fd4a`
- `RPCRT4!RpcRevertToSelf` at `0x18002fc18`
- `RPCRT4!RpcRevertToSelf` at `0x18002fc38`
- `RPCRT4!RpcRevertToSelf` at `0x18002fdba`
- `RPCRT4!RpcRevertToSelf` at `0x18002fdde`
- `RPCRT4!RpcRevertToSelf` at `0x18002fc18`
- `RPCRT4!RpcRevertToSelf` at `0x18002fc38`
- `RPCRT4!RpcRevertToSelf` at `0x18002fdba`
- `RPCRT4!RpcRevertToSelf` at `0x18002fdde`
- `KERNEL32!HeapAlloc` at `0x18002feb1`
- `KERNEL32!HeapAlloc` at `0x18002ff74`
- `KERNEL32!HeapAlloc` at `0x18002feb1`
- `KERNEL32!HeapAlloc` at `0x18002ff74`
- `KERNEL32!SetEvent` at `0x18003032f`
- `KERNEL32!SetEvent` at `0x18003032f`
- `KERNEL32!GetLastError` at `0x18002fbc1`
- `KERNEL32!GetLastError` at `0x18002fd66`
- `KERNEL32!GetLastError` at `0x18002ff3d`
- `KERNEL32!GetLastError` at `0x18003033f`
- `KERNEL32!GetLastError` at `0x18002fbc1`
- `KERNEL32!GetLastError` at `0x18002fd66`
- `KERNEL32!GetLastError` at `0x18002ff3d`
- `KERNEL32!GetLastError` at `0x18003033f`
- `KERNEL32!EnterCriticalSection` at `0x18002ffc2`
- `KERNEL32!EnterCriticalSection` at `0x18003003b`
- `KERNEL32!EnterCriticalSection` at `0x18002ffc2`
- `KERNEL32!EnterCriticalSection` at `0x18003003b`
- `KERNEL32!LeaveCriticalSection` at `0x180030028`
- `KERNEL32!LeaveCriticalSection` at `0x180030076`
- `KERNEL32!LeaveCriticalSection` at `0x180030028`
- `KERNEL32!LeaveCriticalSection` at `0x180030076`
- `KERNEL32!HeapFree` at `0x18002ffe6`
- `KERNEL32!HeapFree` at `0x18003000e`
- `KERNEL32!HeapFree` at `0x18003005c`
- `KERNEL32!HeapFree` at `0x1800302b6`
- `KERNEL32!HeapFree` at `0x1800302d8`
- `KERNEL32!HeapFree` at `0x1800302f5`
- `KERNEL32!HeapFree` at `0x180030312`
- `KERNEL32!HeapFree` at `0x18002ffe6`
- `KERNEL32!HeapFree` at `0x18003000e`
- `KERNEL32!HeapFree` at `0x18003005c`
- `KERNEL32!HeapFree` at `0x1800302b6`
- `KERNEL32!HeapFree` at `0x1800302d8`
- `KERNEL32!HeapFree` at `0x1800302f5`
- `KERNEL32!HeapFree` at `0x180030312`

## string_xrefs

- `0x18002fcb9`: `DatabasePath`
- `0x18002fe4f`: `BackupDatabasePath`
- `0x18002f986`: `APIProtocolSupport`

## pseudocode

```c
__int64 __fastcall R_DhcpServerSetConfigVQ(__int64 a1, int a2, __int64 a3)
{
  char *v4; // rbp
  char *v5; // r14
  DWORD LastError; // ebx
  DWORD cbData; // ecx
  const BYTE *v10; // rax
  __int64 v11; // r13
  const WCHAR *v12; // rcx
  __int64 v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  __int64 v17; // rax
  RPC_STATUS v18; // esi
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
  __int64 v29; // rax
  size_t v30; // r15
  char *v31; // rax
  size_t v32; // rdx
  signed __int64 v33; // r9
  char *v34; // rcx
  char v35; // al
  wchar_t *v36; // rsi
  _DWORD *v37; // rsi
  _DWORD *v38; // rsi
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids);
  LastError = DhcpApiAccessCheck(2684354560LL);
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
          goto LABEL_138;
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
                (unsigned int)&WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids,
                LastError,
                *(_QWORD *)(a3 + 16));
            }
            if ( !v18 )
              RpcRevertToSelf();
            goto LABEL_138;
          }
        }
        LastError = DhcpAddServiceAceToDir(*(LPWSTR *)(a3 + 16));
        if ( !v18 && RpcRevertToSelf() )
          goto LABEL_138;
        if ( LastError )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_138;
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
          goto LABEL_138;
        v41 = (void *)DhcpUnicodeToOem(*(PCWSTR *)(a3 + 16));
        if ( !v41 )
        {
          LastError = 8;
          goto LABEL_138;
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
                  (unsigned int)&WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids,
                  LastError,
                  *(_QWORD *)(a3 + 24));
              }
              if ( !v26 )
                RpcRevertToSelf();
              goto LABEL_138;
            }
          }
          LastError = DhcpAddServiceAceToDir(*(LPWSTR *)(a3 + 24));
          if ( !v26 && RpcRevertToSelf() )
            goto LABEL_138;
          if ( LastError )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_138;
            }
            v20 = *(_QWORD *)(a3 + 24);
            v21 = 20;
LABEL_58:
            WPP_SF_LS(v19[2], v21, (unsigned int)&WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids, LastError, v20);
            goto LABEL_138;
          }
          v27 = *(const BYTE **)(a3 + 24);
          v28 = -1;
          do
            ++v28;
          while ( *(_WORD *)&v27[2 * v28] );
          LastError = RegSetValueExW(DhcpGlobalRegParam, L"BackupDatabasePath", 0, 2u, v27, 2 * v28 + 2);
          if ( LastError )
            goto LABEL_138;
          v4 = (char *)DhcpUnicodeToOem(*(PCWSTR *)(a3 + 24));
          if ( !v4 )
          {
            LastError = 8;
            goto LABEL_138;
          }
          v29 = -1;
          do
            ++v29;
          while ( v4[v29] );
          v30 = v29 + 2;
          v31 = (char *)HeapAlloc(gDhcpHeap, 8u, v29 + 2);
          v5 = v31;
          if ( !v31 )
            goto LABEL_93;
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
              goto LABEL_138;
            LastError = 0;
          }
          do
            ++v11;
          while ( v4[v11] );
          if ( !HeapAlloc(gDhcpHeap, 8u, 2 * (v11 + 9)) )
          {
LABEL_93:
            LastError = 8;
            goto LABEL_138;
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
LABEL_118:
              v4 = 0;
              v5 = 0;
              goto LABEL_138;
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
              goto LABEL_138;
            v42 = 1;
            DhcpGlobalBackupInterval = 60000 * *v37;
          }
          if ( (a2 & 0x20) != 0 )
          {
            v4 = 0;
            v5 = 0;
            LastError = RegSetValueExW(DhcpGlobalRegParam, L"DatabaseLoggingFlag", 0, 4u, (const BYTE *)(a3 + 36), 4u);
            if ( LastError )
              goto LABEL_138;
            DhcpGlobalDatabaseLoggingFlag = *(_DWORD *)(a3 + 36);
          }
          if ( (a2 & 0x40) != 0 )
          {
            v4 = 0;
            v5 = 0;
            LastError = RegSetValueExW(DhcpGlobalRegParam, L"RestoreFlag", 0, 4u, (const BYTE *)(a3 + 40), 4u);
            if ( LastError )
              goto LABEL_138;
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
              goto LABEL_138;
            v42 = 1;
            DhcpGlobalCleanupInterval = 60000 * *v38;
          }
          if ( (a2 & 0x100) == 0
            || (DhcpGlobalDebugFlag = *(_DWORD *)(a3 + 48),
                v4 = 0,
                v5 = 0,
                (LastError = RegSetValueExW(DhcpGlobalRegParam, L"DebugFlag", 0, 4u, (const BYTE *)(a3 + 48), 4u)) == 0) )
          {
            v4 = 0;
            v5 = 0;
            if ( (a2 & 0x3000) != 0 )
              LastError = 20138;
          }
LABEL_138:
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
      }
LABEL_64:
      LastError = 87;
      goto LABEL_138;
    }
  }
LABEL_9:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18002f890  mov     [rsp+arg_0], rbx
0x18002f895  mov     [rsp+arg_8], rbp
0x18002f89a  mov     [rsp+arg_10], rsi
0x18002f89f  push    rdi
0x18002f8a0  push    r12
0x18002f8a2  push    r13
0x18002f8a4  push    r14
0x18002f8a6  push    r15
0x18002f8a8  sub     rsp, 50h
0x18002f8ac  xor     r15d, r15d
0x18002f8af  mov     rdi, r8
0x18002f8b2  mov     [rsp+78h+lpMem], r15
0x18002f8b7  mov     ebp, r15d
0x18002f8ba  mov     [rsp+78h+var_38], r15
0x18002f8bf  mov     r14d, r15d
0x18002f8c2  mov     [rsp+78h+arg_18], r15d
0x18002f8ca  mov     r12d, edx
0x18002f8cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8d4  lea     rax, WPP_GLOBAL_Control
0x18002f8db  cmp     rcx, rax
0x18002f8de  jz      short loc_18002F8FD
0x18002f8e0  test    dword ptr [rcx+1Ch], 200h
0x18002f8e7  jz      short loc_18002F8FD
0x18002f8e9  mov     rcx, [rcx+10h]
0x18002f8ed  lea     edx, [r15+10h]
0x18002f8f1  lea     r8, WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids
0x18002f8f8  call    WPP_SF_
0x18002f8fd  mov     ecx, 0A0000000h
0x18002f902  call    DhcpApiAccessCheck
0x18002f907  mov     ebx, eax
0x18002f909  test    eax, eax
0x18002f90b  jnz     short loc_18002F92A
0x18002f90d  test    r12d, r12d
0x18002f910  jz      short loc_18002F95E
0x18002f912  lea     r13d, [rax+4]
0x18002f916  test    r12b, 1
0x18002f91a  jz      loc_18002F9BB
0x18002f920  cmp     [rdi], r15d
0x18002f923  jnz     short loc_18002F97F
0x18002f925  mov     ebx, 57h ; 'W'
0x18002f92a  lea     r12, WPP_GLOBAL_Control
0x18002f931  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f938  cmp     rcx, r12
0x18002f93b  jz      short loc_18002F95E
0x18002f93d  test    dword ptr [rcx+1Ch], 200h
0x18002f944  jz      short loc_18002F95E
0x18002f946  mov     rcx, [rcx+10h]
0x18002f94a  lea     r8, WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids
0x18002f951  mov     edx, 1Ah
0x18002f956  mov     r9d, ebx
0x18002f959  call    WPP_SF_D
0x18002f95e  lea     r11, [rsp+78h+var_28]
0x18002f963  mov     eax, ebx
0x18002f965  mov     rbx, [r11+30h]
0x18002f969  mov     rbp, [r11+38h]
0x18002f96d  mov     rsi, [r11+40h]
0x18002f971  mov     rsp, r11
0x18002f974  pop     r15
0x18002f976  pop     r14
0x18002f978  pop     r13
0x18002f97a  pop     r12
0x18002f97c  pop     rdi
0x18002f97d  retn
0x18002f97f  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18002f986  lea     rdx, aApiprotocolsup; "APIProtocolSupport"
0x18002f98d  mov     [rsp+78h+cbData], r13d; cbData
0x18002f992  mov     r9d, r13d; dwType
0x18002f995  xor     r8d, r8d; Reserved
0x18002f998  mov     [rsp+78h+lpData], rdi; lpData
0x18002f99d  call    cs:__imp_RegSetValueExW
0x18002f9a4  nop     dword ptr [rax+rax+00h]
0x18002f9a9  mov     ebx, eax
0x18002f9ab  test    eax, eax
0x18002f9ad  jnz     loc_18002F92A
0x18002f9b3  mov     eax, [rdi]
0x18002f9b5  mov     cs:DhcpGlobalRpcProtocols, eax
0x18002f9bb  bt      r12d, 9
0x18002f9c0  jnb     short loc_18002FA19
0x18002f9c2  lea     rsi, [rdi+34h]
0x18002f9c6  mov     ecx, [rsi]
0x18002f9c8  lea     eax, [rcx+1]
0x18002f9cb  cmp     eax, 1
0x18002f9ce  jb      loc_18002F925
0x18002f9d4  cmp     ecx, 5
0x18002f9d7  ja      loc_18002F925
0x18002f9dd  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18002f9e4  lea     rdx, aDetectconflict; "DetectConflictRetries"
0x18002f9eb  mov     [rsp+78h+cbData], r13d; cbData
0x18002f9f0  mov     r9d, r13d; dwType
0x18002f9f3  xor     r8d, r8d; Reserved
0x18002f9f6  mov     [rsp+78h+lpData], rsi; lpData
0x18002f9fb  call    cs:__imp_RegSetValueExW
0x18002fa02  nop     dword ptr [rax+rax+00h]
0x18002fa07  mov     ebx, eax
0x18002fa09  test    eax, eax
0x18002fa0b  jnz     loc_18002F92A
0x18002fa11  mov     eax, [rsi]
0x18002fa13  mov     cs:DhcpGlobalDetectConflictRetries, eax
0x18002fa19  bt      r12d, 0Bh
0x18002fa1e  jnb     short loc_18002FA60
0x18002fa20  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18002fa27  lea     rsi, [rdi+48h]
0x18002fa2b  mov     [rsp+78h+cbData], r13d; cbData
0x18002fa30  lea     rdx, aActivitylogfla; "ActivityLogFlag"
0x18002fa37  mov     r9d, r13d; dwType
0x18002fa3a  mov     [rsp+78h+lpData], rsi; lpData
0x18002fa3f  xor     r8d, r8d; Reserved
0x18002fa42  call    cs:__imp_RegSetValueExW
0x18002fa49  nop     dword ptr [rax+rax+00h]
0x18002fa4e  mov     ebx, eax
0x18002fa50  test    eax, eax
0x18002fa52  jnz     loc_18002F92A
0x18002fa58  mov     eax, [rsi]
0x18002fa5a  mov     cs:DhcpGlobalAuditLogFlag, eax
0x18002fa60  bt      r12d, 0Ah
0x18002fa65  jnb     short loc_18002FAB5
0x18002fa67  mov     ecx, [rdi+38h]
0x18002fa6a  cmp     ecx, 100000h
0x18002fa70  ja      loc_18002F925
0x18002fa76  mov     rax, [rdi+40h]
0x18002fa7a  test    rax, rax
0x18002fa7d  jz      short loc_18002FAB5
0x18002fa7f  mov     [rsp+78h+cbData], ecx; cbData
0x18002fa83  lea     rdx, aBootfiletable; "BootFileTable"
0x18002fa8a  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18002fa91  mov     r9d, 7; dwType
0x18002fa97  xor     r8d, r8d; Reserved
0x18002fa9a  mov     [rsp+78h+lpData], rax; lpData
0x18002fa9f  call    cs:__imp_RegSetValueExW
0x18002faa6  nop     dword ptr [rax+rax+00h]
0x18002faab  mov     ebx, eax
0x18002faad  test    eax, eax
0x18002faaf  jnz     loc_18002F92A
0x18002fab5  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002fab9  test    r12b, 2
0x18002fabd  jz      loc_18002FB64
0x18002fac3  mov     rcx, [rdi+8]; lpWideCharStr
0x18002fac7  test    rcx, rcx
0x18002faca  jz      loc_18002F925
0x18002fad0  mov     rax, r13
0x18002fad3  inc     rax
0x18002fad6  cmp     [rcx+rax*2], r15w
0x18002fadb  jnz     short loc_18002FAD3
0x18002fadd  test    rax, rax
0x18002fae0  jz      loc_18002F925
0x18002fae6  call    IsStringTroublesome
0x18002faeb  test    eax, eax
0x18002faed  jz      short loc_18002FAF9
0x18002faef  mov     ebx, 7Bh ; '{'
0x18002faf4  jmp     loc_18002F92A
0x18002faf9  mov     rcx, [rdi+8]
0x18002fafd  mov     rax, r13
0x18002fb00  inc     rax
0x18002fb03  cmp     [rcx+rax*2], r15w
0x18002fb08  jnz     short loc_18002FB00
0x18002fb0a  lea     eax, ds:2[rax*2]
0x18002fb11  mov     r9d, 1; dwType
0x18002fb17  mov     [rsp+78h+cbData], eax; cbData
0x18002fb1b  lea     rdx, aDatabasename_0; "DatabaseName"
0x18002fb22  mov     [rsp+78h+lpData], rcx; lpData
0x18002fb27  xor     r8d, r8d; Reserved
0x18002fb2a  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18002fb31  call    cs:__imp_RegSetValueExW
0x18002fb38  nop     dword ptr [rax+rax+00h]
0x18002fb3d  mov     ebx, eax
0x18002fb3f  test    eax, eax
0x18002fb41  jnz     loc_18002F92A
0x18002fb47  mov     rcx, [rdi+8]; SourceString
0x18002fb4b  xor     edx, edx
0x18002fb4d  call    DhcpUnicodeToOem
0x18002fb52  mov     [rsp+78h+lpMem], rax
0x18002fb57  test    rax, rax
0x18002fb5a  jnz     short loc_18002FB64
0x18002fb5c  lea     ebx, [rax+8]
0x18002fb5f  jmp     loc_18002F92A
0x18002fb64  test    r12b, 4
0x18002fb68  jz      loc_18002FD0F
0x18002fb6e  mov     rcx, [rdi+10h]; lpWideCharStr
0x18002fb72  test    rcx, rcx
0x18002fb75  jz      loc_18002FD05
0x18002fb7b  mov     rax, r13
0x18002fb7e  inc     rax
0x18002fb81  cmp     [rcx+rax*2], r15w
0x18002fb86  jnz     short loc_18002FB7E
0x18002fb88  test    rax, rax
0x18002fb8b  jz      loc_18002FD05
0x18002fb91  call    IsStringTroublesome
0x18002fb96  test    eax, eax
0x18002fb98  jz      short loc_18002FBA4
0x18002fb9a  mov     ebx, 7Bh ; '{'
0x18002fb9f  jmp     loc_180030299
0x18002fba4  xor     ecx, ecx; BindingHandle
0x18002fba6  call    cs:__imp_RpcImpersonateClient
0x18002fbad  nop     dword ptr [rax+rax+00h]
0x18002fbb2  mov     rcx, [rdi+10h]; lpPathName
0x18002fbb6  mov     esi, eax
0x18002fbb8  call    CreateDirectoryPathW
0x18002fbbd  test    eax, eax
0x18002fbbf  jnz     short loc_18002FC29
0x18002fbc1  call    cs:__imp_GetLastError
0x18002fbc8  nop     dword ptr [rax+rax+00h]
0x18002fbcd  mov     ebx, eax
0x18002fbcf  cmp     eax, 0B7h
0x18002fbd4  jz      short loc_18002FC29
0x18002fbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbdd  lea     r12, WPP_GLOBAL_Control
0x18002fbe4  cmp     rcx, r12
0x18002fbe7  jz      short loc_18002FC10
0x18002fbe9  test    byte ptr [rcx+1Ch], 10h
0x18002fbed  jz      short loc_18002FC10
0x18002fbef  mov     rax, [rdi+10h]
0x18002fbf3  lea     r8, WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids
0x18002fbfa  mov     rcx, [rcx+10h]
0x18002fbfe  mov     edx, 11h
0x18002fc03  mov     r9d, ebx
0x18002fc06  mov     [rsp+78h+lpData], rax
0x18002fc0b  call    WPP_SF_LS
0x18002fc10  test    esi, esi
0x18002fc12  jnz     loc_1800302A0
0x18002fc18  call    cs:__imp_RpcRevertToSelf
0x18002fc1f  nop     dword ptr [rax+rax+00h]
0x18002fc24  jmp     loc_1800302A0
0x18002fc29  mov     rcx, [rdi+10h]; pObjectName
0x18002fc2d  call    DhcpAddServiceAceToDir
0x18002fc32  mov     ebx, eax
0x18002fc34  test    esi, esi
0x18002fc36  jnz     short loc_18002FC4C
0x18002fc38  call    cs:__imp_RpcRevertToSelf
0x18002fc3f  nop     dword ptr [rax+rax+00h]
0x18002fc44  test    eax, eax
0x18002fc46  jnz     loc_180030299
0x18002fc4c  test    ebx, ebx
0x18002fc4e  jz      short loc_18002FC97
0x18002fc50  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc57  lea     r12, WPP_GLOBAL_Control
0x18002fc5e  cmp     rcx, r12
0x18002fc61  jz      loc_1800302A0
0x18002fc67  test    byte ptr [rcx+1Ch], 10h
0x18002fc6b  jz      loc_1800302A0
0x18002fc71  mov     rax, [rdi+10h]
0x18002fc75  mov     edx, 12h
0x18002fc7a  mov     rcx, [rcx+10h]
0x18002fc7e  lea     r8, WPP_a7b48f02fc403f8c163d0b6186df0d4f_Traceguids
0x18002fc85  mov     r9d, ebx
0x18002fc88  mov     [rsp+78h+lpData], rax
0x18002fc8d  call    WPP_SF_LS
0x18002fc92  jmp     loc_1800302A0
0x18002fc97  mov     rcx, [rdi+10h]
0x18002fc9b  mov     rax, r13
0x18002fc9e  inc     rax
0x18002fca1  cmp     [rcx+rax*2], r15w
0x18002fca6  jnz     short loc_18002FC9E
0x18002fca8  lea     eax, ds:2[rax*2]
0x18002fcaf  mov     r9d, 2; dwType
0x18002fcb5  mov     [rsp+78h+cbData], eax; cbData
0x18002fcb9  lea     rdx, aDatabasepath; "DatabasePath"
0x18002fcc0  mov     [rsp+78h+lpData], rcx; lpData
0x18002fcc5  xor     r8d, r8d; Reserved
0x18002fcc8  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18002fccf  call    cs:__imp_RegSetValueExW
0x18002fcd6  nop     dword ptr [rax+rax+00h]
0x18002fcdb  mov     ebx, eax
0x18002fcdd  test    eax, eax
0x18002fcdf  jnz     loc_180030299
0x18002fce5  mov     rcx, [rdi+10h]; SourceString
0x18002fce9  xor     edx, edx
0x18002fceb  call    DhcpUnicodeToOem
0x18002fcf0  mov     [rsp+78h+var_38], rax
0x18002fcf5  test    rax, rax
0x18002fcf8  jnz     short loc_18002FD0F
0x18002fcfa  lea     ebx, [rax+8]
0x18002fcfd  xor     r15d, r15d
0x18002fd00  jmp     loc_180030299
0x18002fd05  mov     ebx, 57h ; 'W'
0x18002fd0a  jmp     loc_180030299
0x18002fd0f  mov     esi, 8
0x18002fd14  xor     r15d, r15d
0x18002fd17  test    sil, r12b
0x18002fd1a  jz      loc_180030082
0x18002fd20  mov     rcx, [rdi+18h]; lpWideCharStr
0x18002fd24  test    rcx, rcx
0x18002fd27  jz      short loc_18002FD05
0x18002fd29  mov     rax, r13
0x18002fd2c  inc     rax
0x18002fd2f  cmp     [rcx+rax*2], r15w
0x18002fd34  jnz     short loc_18002FD2C
0x18002fd36  test    rax, rax
0x18002fd39  jz      short loc_18002FD05
0x18002fd3b  call    IsStringTroublesome
0x18002fd40  test    eax, eax
0x18002fd42  jnz     loc_18002FB9A
0x18002fd48  xor     ecx, ecx; BindingHandle
0x18002fd4a  call    cs:__imp_RpcImpersonateClient
0x18002fd51  nop     dword ptr [rax+rax+00h]
0x18002fd56  mov     rcx, [rdi+18h]; lpPathName
0x18002fd5a  mov     r15d, eax
0x18002fd5d  call    CreateDirectoryPathW
0x18002fd62  test    eax, eax
0x18002fd64  jnz     short loc_18002FDCE
0x18002fd66  call    cs:__imp_GetLastError
  ... truncated ...
```
