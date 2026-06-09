# DsaWaitShutdownForStartupPhase2

- ea: `0x1800b0d60`
- end: `0x1800b14b6`
- name: `DsaWaitShutdownForStartupPhase2`
- size: `1878`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800a3bac`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000bb80`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x1800acdc0`
- `0x1800b0d60`
- `0x1800b6724`
- `0x180114868`
- `0x180172ffc`
- `0x18032df4c`

## import_xrefs

- `NTDSKCC!KccUnInitializeWait` at `0x1800b0f1d`
- `NTDSKCC!KccUnInitializeWait` at `0x1800b0f1d`
- `ntdsbsrv!UnRegisterBackupServices` at `0x1800b0e7a`
- `ntdsbsrv!UnRegisterBackupServices` at `0x1800b0e7a`
- `RPCRT4!RpcBindingVectorFree` at `0x1800b0ef5`
- `RPCRT4!RpcBindingVectorFree` at `0x1800b0ef5`
- `RPCRT4!RpcMgmtStopServerListening` at `0x1800b0ead`
- `RPCRT4!RpcMgmtStopServerListening` at `0x1800b0ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b128b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b128b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0e32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b0e32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0e14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0e14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0e54`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0e54`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0ddd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0ddd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800b104a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800b104a`
- `ntdll!NtQueryInformationThread` at `0x1800b1176`
- `ntdll!NtQueryInformationThread` at `0x1800b1176`
- `ntdll!EtwUnregisterTraceGuids` at `0x1800b1486`
- `ntdll!EtwUnregisterTraceGuids` at `0x1800b1486`

## string_xrefs

- `0x1800b0f49`: `hDirNotifyThread`
- `0x1800b0f72`: `hDirAuditThread`
- `0x1800b0f9b`: `hReplNotifyThread`
- `0x1800b0fc4`: `hAsyncSchemaUpdateThread`
- `0x1800b1016`: `hMailReceiveThread`

## pseudocode

```c
NTSTATUS __fastcall DsaWaitShutdownForStartupPhase2(int a1, int a2)
{
  int v4; // r14d
  int v5; // esi
  int v6; // ebx
  DWORD v7; // edx
  int i; // ebx
  DWORD v9; // r14d
  DWORD v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  NTSTATUS result; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r9
  BOOL v20; // r15d
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // r9
  BOOL v28; // r15d
  int v29; // edx
  int v30; // r8d
  int v31; // r9d
  BOOL v32; // ecx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // r8
  __int64 v38; // r9
  BOOL v39; // r14d
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // r8
  __int64 v45; // r9
  BOOL v46; // r14d
  int v47; // [rsp+30h] [rbp-128h]
  int v48; // [rsp+38h] [rbp-120h]
  _QWORD ThreadInformation[7]; // [rsp+58h] [rbp-100h] BYREF
  _QWORD v50[10]; // [rsp+90h] [rbp-C8h] BYREF
  HANDLE Handles[10]; // [rsp+E0h] [rbp-78h] BYREF

  memset_0(Handles, 0, sizeof(Handles));
  memset_0(v50, 0, sizeof(v50));
  DsWaitUntilDelayedStartupIsDone();
  WaitLdapStop();
  if ( dword_18051CE68 )
  {
    dword_18051CE68 = 0;
    FreeLibrary(hLibModule);
    *(_OWORD *)&hLibModule = 0;
    xmmword_18051CE80 = 0;
    qword_18051CE90 = 0;
  }
  v4 = gdwStopControl;
  if ( gbSsiInitialized )
  {
    EnterCriticalSection(&gcsGlobalSsiHandleCount);
    v5 = 1;
    gbSsiShutdownInProgress = 1;
    v6 = glGlobalSsiHandleCount;
    LeaveCriticalSection(&gcsGlobalSsiHandleCount);
    if ( v6 )
    {
      v7 = 5000;
      if ( v4 != 5 )
        v7 = 20000;
      if ( WaitForSingleObject(ghShutdownDoneEvent, v7) )
        GetLastError();
    }
  }
  else
  {
    v5 = 1;
  }
  if ( *(_DWORD *)gfADAM )
    UnRegisterBackupServices((unsigned int)gdwStopControl);
  if ( gRODCWriteReferralDC )
  {
    DSFreeAux(gRODCWriteReferralDC, 51725636);
    gRODCWriteReferralDC = 0;
  }
  if ( !a1 && !a2 && !RpcMgmtStopServerListening(0) )
    gRpcListening = 0;
  for ( i = 0; i < gNumRpcNsExportedInterfaces; ++i )
    MSRPC_UnregisterEndpoints((RPC_IF_HANDLE)gRpcNsExportedInterface[i]);
  if ( gpRpcBindingVector )
  {
    RpcBindingVectorFree(&gpRpcBindingVector);
    gpRpcBindingVector = 0;
  }
  if ( gfRunningInsideLsa || *(_DWORD *)gfADAM )
    KccUnInitializeWait(60000);
  v9 = 0;
  if ( hDirNotifyThread )
  {
    Handles[0] = (HANDLE)hDirNotifyThread;
    v50[0] = "hDirNotifyThread";
    v9 = 1;
  }
  if ( hDirAuditThread )
  {
    Handles[v9] = (HANDLE)hDirAuditThread;
    v50[v9++] = "hDirAuditThread";
  }
  if ( hReplNotifyThread )
  {
    Handles[v9] = hReplNotifyThread;
    v50[v9++] = "hReplNotifyThread";
  }
  if ( hAsyncSchemaUpdateThread )
  {
    Handles[v9] = hAsyncSchemaUpdateThread;
    v50[v9++] = "hAsyncSchemaUpdateThread";
  }
  if ( hevSDPropagatorDead )
  {
    Handles[v9] = hevSDPropagatorDead;
    v50[v9++] = "hevSDPropagatorDead";
  }
  if ( hMailReceiveThread )
  {
    Handles[v9] = (HANDLE)hMailReceiveThread;
    v50[v9++] = "hMailReceiveThread";
  }
  v10 = WaitForMultipleObjects(v9, Handles, 1, a2 != 0 ? -1 : 5000);
  if ( v10 == 258 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v14, v13)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
      || (result = gfTraceToSecondProvider) != 0
      && ((unsigned int)THStateCheckForTraceOverride(v14, v13)
       || (result = ThStateCheckIfTraceToSecondProvier(v14, v13, v16, v17)) != 0
       && (result = CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) != 0) )
    {
      v20 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v14, v13)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v14, v13, v18, v19)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
      if ( (unsigned int)THStateCheckForTraceOverride(v14, v13)
        || (v21 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
      {
        v21 = 1;
      }
      result = WPP_SF_(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 50334031,
                 3,
                 3,
                 v21,
                 v20,
                 23,
                 &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
    }
    while ( (int)v9 > 0 )
    {
      memset(ThreadInformation, 0, 44);
      result = NtQueryInformationThread((HANDLE)v50[v9 + 9], ThreadBasicInformation, ThreadInformation, 0x30u, 0);
      if ( result >= 0
        && LODWORD(ThreadInformation[0]) == 259
        && ((unsigned int)IncrementWPPPerfCountersForLevel(3)
         || (unsigned int)THStateCheckForTraceOverride(v23, v22)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
         || (result = gfTraceToSecondProvider) != 0
         && ((unsigned int)THStateCheckForTraceOverride(v23, v22)
          || (result = ThStateCheckIfTraceToSecondProvier(v23, v22, v24, v25)) != 0
          && (result = CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) != 0)) )
      {
        v28 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v23, v22)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v23, v22, v26, v27)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
        v32 = (unsigned int)THStateCheckForTraceOverride(v23, v22)
           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3);
        result = WPP_SF_is(
                   *((_QWORD *)WPP_GLOBAL_Control + 2),
                   v29,
                   v30,
                   v31,
                   v32,
                   v28,
                   v47,
                   v48,
                   ThreadInformation[3],
                   ThreadInformation[v9 + 6]);
      }
      --v9;
    }
  }
  else if ( v10 == -1 )
  {
    GetLastError();
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v34, v33)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
      || (result = gfTraceToSecondProvider) != 0
      && ((unsigned int)THStateCheckForTraceOverride(v34, v33)
       || (result = ThStateCheckIfTraceToSecondProvier(v34, v33, v35, v36)) != 0
       && (result = CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) != 0) )
    {
      v39 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v34, v33)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v34, v33, v37, v38)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v34, v33)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
      {
        v5 = 0;
      }
      result = WPP_SF__ATTRTYP_LOG_(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 50334051,
                 2,
                 3,
                 v5,
                 v39,
                 25,
                 (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
    }
  }
  else if ( (unsigned int)THStateCheckForTraceOverride(v12, v11)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3)
         || (result = gfTraceToSecondProvider) != 0
         && ((unsigned int)THStateCheckForTraceOverride(v41, v40)
          || (result = ThStateCheckIfTraceToSecondProvier(v41, v40, v42, v43)) != 0
          && (result = CheckWPPLevelFlagsEnabledForProvider(1, 5, 3)) != 0) )
  {
    v46 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v41, v40)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v41, v40, v44, v45)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3));
    if ( !(unsigned int)THStateCheckForTraceOverride(v41, v40)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3) )
    {
      v5 = 0;
    }
    result = WPP_SF_(
               *((_QWORD *)WPP_GLOBAL_Control + 2),
               50334055,
               5,
               3,
               v5,
               v46,
               26,
               &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
  }
  if ( DsTraceRegistrationHandle )
    return EtwUnregisterTraceGuids();
  return result;
}

```

## disassembly

```asm
0x1800b0d60  mov     r11, rsp
0x1800b0d63  mov     [r11+8], rbx
0x1800b0d67  mov     [r11+18h], rsi
0x1800b0d6b  mov     [rsp+arg_8], edx
0x1800b0d6f  push    r12
0x1800b0d71  push    r14
0x1800b0d73  push    r15
0x1800b0d75  sub     rsp, 140h
0x1800b0d7c  mov     rax, cs:__security_cookie
0x1800b0d83  xor     rax, rsp
0x1800b0d86  mov     [rsp+158h+var_28], rax
0x1800b0d8e  mov     r15d, edx
0x1800b0d91  mov     r12d, ecx
0x1800b0d94  mov     ebx, 50h ; 'P'
0x1800b0d99  mov     r8d, ebx; Size
0x1800b0d9c  xor     edx, edx; Val
0x1800b0d9e  lea     rcx, [r11-78h]; void *
0x1800b0da2  call    memset_0
0x1800b0da7  mov     r8d, ebx; Size
0x1800b0daa  xor     edx, edx; Val
0x1800b0dac  lea     rcx, [rsp+158h+var_C8]; void *
0x1800b0db4  call    memset_0
0x1800b0db9  call    DsWaitUntilDelayedStartupIsDone
0x1800b0dbe  call    WaitLdapStop
0x1800b0dc3  cmp     cs:dword_18051CE68, 0
0x1800b0dca  jz      short loc_1800B0DFD
0x1800b0dcc  mov     cs:dword_18051CE68, 0
0x1800b0dd6  mov     rcx, qword ptr cs:hLibModule; hLibModule
0x1800b0ddd  call    cs:__imp_FreeLibrary
0x1800b0de3  xorps   xmm0, xmm0
0x1800b0de6  xor     eax, eax
0x1800b0de8  movups  cs:hLibModule, xmm0
0x1800b0def  movups  cs:xmmword_18051CE80, xmm0
0x1800b0df6  mov     cs:qword_18051CE90, rax
0x1800b0dfd  mov     r14d, cs:gdwStopControl
0x1800b0e04  cmp     cs:gbSsiInitialized, 0
0x1800b0e0b  jz      short loc_1800B0E66
0x1800b0e0d  lea     rcx, gcsGlobalSsiHandleCount; lpCriticalSection
0x1800b0e14  call    cs:__imp_EnterCriticalSection
0x1800b0e1a  mov     esi, 1
0x1800b0e1f  mov     cs:gbSsiShutdownInProgress, esi
0x1800b0e25  mov     ebx, cs:glGlobalSsiHandleCount
0x1800b0e2b  lea     rcx, gcsGlobalSsiHandleCount; lpCriticalSection
0x1800b0e32  call    cs:__imp_LeaveCriticalSection
0x1800b0e38  test    ebx, ebx
0x1800b0e3a  jz      short loc_1800B0E6B
0x1800b0e3c  mov     edx, 1388h
0x1800b0e41  mov     eax, 4E20h
0x1800b0e46  cmp     r14d, 5
0x1800b0e4a  cmovnz  edx, eax; dwMilliseconds
0x1800b0e4d  mov     rcx, cs:ghShutdownDoneEvent; hHandle
0x1800b0e54  call    cs:__imp_WaitForSingleObject
0x1800b0e5a  test    eax, eax
0x1800b0e5c  jz      short loc_1800B0E6B
0x1800b0e5e  call    cs:__imp_GetLastError
0x1800b0e64  jmp     short loc_1800B0E6B
0x1800b0e66  mov     esi, 1
0x1800b0e6b  cmp     cs:gfADAM, 0
0x1800b0e72  jz      short loc_1800B0E80
0x1800b0e74  mov     ecx, cs:gdwStopControl
0x1800b0e7a  call    cs:__imp_UnRegisterBackupServices
0x1800b0e80  mov     rcx, cs:gRODCWriteReferralDC
0x1800b0e87  test    rcx, rcx
0x1800b0e8a  jz      short loc_1800B0EA1
0x1800b0e8c  mov     edx, 3154544h
0x1800b0e91  call    DSFreeAux
0x1800b0e96  mov     cs:gRODCWriteReferralDC, 0
0x1800b0ea1  test    r12d, r12d
0x1800b0ea4  jnz     short loc_1800B0EBD
0x1800b0ea6  test    r15d, r15d
0x1800b0ea9  jnz     short loc_1800B0EBD
0x1800b0eab  xor     ecx, ecx; Binding
0x1800b0ead  call    cs:__imp_RpcMgmtStopServerListening
0x1800b0eb3  test    eax, eax
0x1800b0eb5  jnz     short loc_1800B0EBD
0x1800b0eb7  mov     cs:gRpcListening, eax
0x1800b0ebd  xor     ebx, ebx
0x1800b0ebf  cmp     cs:gNumRpcNsExportedInterfaces, ebx
0x1800b0ec5  jle     short loc_1800B0EE4
0x1800b0ec7  movsxd  rcx, ebx
0x1800b0eca  lea     rax, gRpcNsExportedInterface
0x1800b0ed1  mov     rcx, [rax+rcx*8]; IfSpec
0x1800b0ed5  call    MSRPC_UnregisterEndpoints
0x1800b0eda  add     ebx, esi
0x1800b0edc  cmp     ebx, cs:gNumRpcNsExportedInterfaces
0x1800b0ee2  jl      short loc_1800B0EC7
0x1800b0ee4  cmp     cs:gpRpcBindingVector, 0
0x1800b0eec  jz      short loc_1800B0F06
0x1800b0eee  lea     rcx, gpRpcBindingVector; BindingVector
0x1800b0ef5  call    cs:__imp_RpcBindingVectorFree
0x1800b0efb  mov     cs:gpRpcBindingVector, 0
0x1800b0f06  cmp     cs:gfRunningInsideLsa, 0
0x1800b0f0d  jnz     short loc_1800B0F18
0x1800b0f0f  cmp     cs:gfADAM, 0
0x1800b0f16  jz      short loc_1800B0F32
0x1800b0f18  mov     ecx, 0EA60h
0x1800b0f1d  call    cs:__imp_KccUnInitializeWait
0x1800b0f23  jmp     short loc_1800B0F32
0x1800b0f25  mov     esi, 1
0x1800b0f2a  mov     r15d, [rsp+158h+arg_8]
0x1800b0f32  xor     r14d, r14d
0x1800b0f35  mov     rax, cs:hDirNotifyThread
0x1800b0f3c  test    rax, rax
0x1800b0f3f  jz      short loc_1800B0F5B
0x1800b0f41  mov     [rsp+158h+Handles], rax
0x1800b0f49  lea     rax, aHdirnotifythre; "hDirNotifyThread"
0x1800b0f50  mov     [rsp+158h+var_C8], rax
0x1800b0f58  mov     r14d, esi
0x1800b0f5b  mov     rcx, cs:hDirAuditThread
0x1800b0f62  test    rcx, rcx
0x1800b0f65  jz      short loc_1800B0F84
0x1800b0f67  mov     eax, r14d
0x1800b0f6a  mov     [rsp+rax*8+158h+Handles], rcx
0x1800b0f72  lea     rcx, aHdirauditthrea; "hDirAuditThread"
0x1800b0f79  mov     [rsp+rax*8+158h+var_C8], rcx
0x1800b0f81  add     r14d, esi
0x1800b0f84  mov     rcx, cs:hReplNotifyThread
0x1800b0f8b  test    rcx, rcx
0x1800b0f8e  jz      short loc_1800B0FAD
0x1800b0f90  mov     eax, r14d
0x1800b0f93  mov     [rsp+rax*8+158h+Handles], rcx
0x1800b0f9b  lea     rcx, aHreplnotifythr; "hReplNotifyThread"
0x1800b0fa2  mov     [rsp+rax*8+158h+var_C8], rcx
0x1800b0faa  add     r14d, esi
0x1800b0fad  mov     rcx, cs:hAsyncSchemaUpdateThread
0x1800b0fb4  test    rcx, rcx
0x1800b0fb7  jz      short loc_1800B0FD6
0x1800b0fb9  mov     eax, r14d
0x1800b0fbc  mov     [rsp+rax*8+158h+Handles], rcx
0x1800b0fc4  lea     rcx, aHasyncschemaup; "hAsyncSchemaUpdateThread"
0x1800b0fcb  mov     [rsp+rax*8+158h+var_C8], rcx
0x1800b0fd3  add     r14d, esi
0x1800b0fd6  mov     rcx, cs:hevSDPropagatorDead
0x1800b0fdd  test    rcx, rcx
0x1800b0fe0  jz      short loc_1800B0FFF
0x1800b0fe2  mov     eax, r14d
0x1800b0fe5  mov     [rsp+rax*8+158h+Handles], rcx
0x1800b0fed  lea     rcx, aHevsdpropagato; "hevSDPropagatorDead"
0x1800b0ff4  mov     [rsp+rax*8+158h+var_C8], rcx
0x1800b0ffc  add     r14d, esi
0x1800b0fff  mov     rcx, cs:hMailReceiveThread
0x1800b1006  test    rcx, rcx
0x1800b1009  jz      short loc_1800B1028
0x1800b100b  mov     eax, r14d
0x1800b100e  mov     [rsp+rax*8+158h+Handles], rcx
0x1800b1016  lea     rcx, aHmailreceiveth; "hMailReceiveThread"
0x1800b101d  mov     [rsp+rax*8+158h+var_C8], rcx
0x1800b1025  add     r14d, esi
0x1800b1028  neg     r15d
0x1800b102b  sbb     r9d, r9d
0x1800b102e  and     r9d, 0FFFFEC77h
0x1800b1035  add     r9d, 1388h; dwMilliseconds
0x1800b103c  mov     r8d, esi; bWaitAll
0x1800b103f  lea     rdx, [rsp+158h+Handles]; lpHandles
0x1800b1047  mov     ecx, r14d; nCount
0x1800b104a  call    cs:__imp_WaitForMultipleObjects
0x1800b1050  cmp     eax, 102h
0x1800b1055  jnz     loc_1800B1282
0x1800b105b  mov     ebx, 3
0x1800b1060  mov     ecx, ebx
0x1800b1062  call    IncrementWPPPerfCountersForLevel
0x1800b1067  test    eax, eax
0x1800b1069  jnz     short loc_1800B10BC
0x1800b106b  call    THStateCheckForTraceOverride
0x1800b1070  test    eax, eax
0x1800b1072  jnz     short loc_1800B10BC
0x1800b1074  mov     r8d, ebx
0x1800b1077  mov     edx, ebx
0x1800b1079  xor     ecx, ecx
0x1800b107b  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b1080  test    eax, eax
0x1800b1082  jnz     short loc_1800B10BC
0x1800b1084  mov     eax, cs:gfTraceToSecondProvider
0x1800b108a  test    eax, eax
0x1800b108c  jz      loc_1800B1274
0x1800b1092  call    THStateCheckForTraceOverride
0x1800b1097  test    eax, eax
0x1800b1099  jnz     short loc_1800B10BC
0x1800b109b  call    ThStateCheckIfTraceToSecondProvier
0x1800b10a0  test    eax, eax
0x1800b10a2  jz      loc_1800B1274
0x1800b10a8  mov     r8d, ebx
0x1800b10ab  mov     edx, ebx
0x1800b10ad  mov     ecx, esi
0x1800b10af  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b10b4  test    eax, eax
0x1800b10b6  jz      loc_1800B1274
0x1800b10bc  mov     eax, cs:gfTraceToSecondProvider
0x1800b10c2  test    eax, eax
0x1800b10c4  jz      short loc_1800B10ED
0x1800b10c6  call    THStateCheckForTraceOverride
0x1800b10cb  test    eax, eax
0x1800b10cd  jnz     short loc_1800B10E8
0x1800b10cf  call    ThStateCheckIfTraceToSecondProvier
0x1800b10d4  test    eax, eax
0x1800b10d6  jz      short loc_1800B10ED
0x1800b10d8  mov     r8d, ebx
0x1800b10db  mov     edx, ebx
0x1800b10dd  mov     ecx, esi
0x1800b10df  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b10e4  test    eax, eax
0x1800b10e6  jz      short loc_1800B10ED
0x1800b10e8  mov     r15d, esi
0x1800b10eb  jmp     short loc_1800B10F0
0x1800b10ed  xor     r15d, r15d
0x1800b10f0  call    THStateCheckForTraceOverride
0x1800b10f5  test    eax, eax
0x1800b10f7  jnz     short loc_1800B1109
0x1800b10f9  mov     r8d, ebx
0x1800b10fc  mov     edx, ebx
0x1800b10fe  xor     ecx, ecx
0x1800b1100  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b1105  test    eax, eax
0x1800b1107  jz      short loc_1800B110B
0x1800b1109  mov     eax, esi
0x1800b110b  lea     rcx, WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids
0x1800b1112  mov     [rsp+158h+var_120], rcx; LPCGUID
0x1800b1117  mov     [rsp+158h+var_128], 17h; __int16
0x1800b111e  mov     [rsp+158h+var_130], r15d; int
0x1800b1123  mov     dword ptr [rsp+158h+ReturnLength], eax; int
0x1800b1127  mov     r9d, ebx; int
0x1800b112a  mov     r8d, ebx; int
0x1800b112d  mov     edx, 300094Fh; int
0x1800b1132  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1139  mov     rcx, [rcx+10h]; int
0x1800b113d  call    WPP_SF_
0x1800b1142  jmp     loc_1800B1274
0x1800b1147  xor     eax, eax
0x1800b1149  xorps   xmm0, xmm0
0x1800b114c  movups  [rsp+158h+ThreadInformation], xmm0
0x1800b1151  movups  xmmword ptr [rsp+158h+var_F0], xmm0
0x1800b1156  movups  xmmword ptr [rsp+158h+var_F0+0Ch], xmm0
0x1800b115b  mov     r12d, r14d
0x1800b115e  mov     [rsp+158h+ReturnLength], rax; ReturnLength
0x1800b1163  lea     r9d, [rax+30h]; ThreadInformationLength
0x1800b1167  lea     r8, [rsp+158h+ThreadInformation]; ThreadInformation
0x1800b116c  xor     edx, edx; ThreadInformationClass
0x1800b116e  mov     rcx, [rsp+r12*8+158h+ThreadHandle]; ThreadHandle
0x1800b1176  call    cs:__imp_NtQueryInformationThread
0x1800b117c  test    eax, eax
0x1800b117e  js      loc_1800B1271
0x1800b1184  cmp     dword ptr [rsp+158h+ThreadInformation], 103h
0x1800b118c  jnz     loc_1800B1271
0x1800b1192  mov     ecx, ebx
0x1800b1194  call    IncrementWPPPerfCountersForLevel
0x1800b1199  test    eax, eax
0x1800b119b  jnz     short loc_1800B11EE
0x1800b119d  call    THStateCheckForTraceOverride
0x1800b11a2  test    eax, eax
0x1800b11a4  jnz     short loc_1800B11EE
0x1800b11a6  mov     r8d, ebx
0x1800b11a9  mov     edx, ebx
0x1800b11ab  xor     ecx, ecx
0x1800b11ad  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b11b2  test    eax, eax
0x1800b11b4  jnz     short loc_1800B11EE
0x1800b11b6  mov     eax, cs:gfTraceToSecondProvider
0x1800b11bc  test    eax, eax
0x1800b11be  jz      loc_1800B1271
0x1800b11c4  call    THStateCheckForTraceOverride
0x1800b11c9  test    eax, eax
0x1800b11cb  jnz     short loc_1800B11EE
0x1800b11cd  call    ThStateCheckIfTraceToSecondProvier
0x1800b11d2  test    eax, eax
0x1800b11d4  jz      loc_1800B1271
0x1800b11da  mov     r8d, ebx
0x1800b11dd  mov     edx, ebx
0x1800b11df  mov     ecx, esi
0x1800b11e1  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b11e6  test    eax, eax
0x1800b11e8  jz      loc_1800B1271
0x1800b11ee  mov     eax, cs:gfTraceToSecondProvider
0x1800b11f4  test    eax, eax
0x1800b11f6  jz      short loc_1800B121F
0x1800b11f8  call    THStateCheckForTraceOverride
0x1800b11fd  test    eax, eax
0x1800b11ff  jnz     short loc_1800B121A
0x1800b1201  call    ThStateCheckIfTraceToSecondProvier
0x1800b1206  test    eax, eax
0x1800b1208  jz      short loc_1800B121F
0x1800b120a  mov     r8d, ebx
0x1800b120d  mov     edx, ebx
0x1800b120f  mov     ecx, esi
0x1800b1211  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b1216  test    eax, eax
0x1800b1218  jz      short loc_1800B121F
0x1800b121a  mov     r15d, esi
0x1800b121d  jmp     short loc_1800B1222
0x1800b121f  xor     r15d, r15d
0x1800b1222  call    THStateCheckForTraceOverride
0x1800b1227  test    eax, eax
0x1800b1229  jnz     short loc_1800B123F
0x1800b122b  mov     r8d, ebx
0x1800b122e  mov     edx, ebx
0x1800b1230  xor     ecx, ecx
0x1800b1232  call    CheckWPPLevelFlagsEnabledForProvider
0x1800b1237  test    eax, eax
0x1800b1239  jnz     short loc_1800B123F
0x1800b123b  xor     ecx, ecx
0x1800b123d  jmp     short loc_1800B1241
  ... truncated ...
```
