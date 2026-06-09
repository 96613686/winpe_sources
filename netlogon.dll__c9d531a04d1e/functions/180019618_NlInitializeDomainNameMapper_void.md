# NlInitializeDomainNameMapper(void)

- ea: `0x180019618`
- end: `0x18001988c`
- name: `?NlInitializeDomainNameMapper@@YAXXZ`
- size: `628`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180072080`

## callees

- `0x18000b790`
- `0x18000e270`
- `0x18000ed34`
- `0x180016fbc`
- `0x180017ee4`
- `0x1800183bc`
- `0x180019618`
- `0x180019eb0`
- `0x18001c76c`
- `0x18001ddd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001985e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001985e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019651`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019651`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001980f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001980f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019788`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019788`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019838`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019838`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001981c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001981c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019754`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019754`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001971d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001971d`

## pseudocode

```c
void NlInitializeDomainNameMapper(void)
{
  int v0; // eax
  NLRefcountableObject *v1; // rbx
  NLRefcountableObject *v2; // rax
  int v3; // eax
  NLRefcountableObject *v4; // rbx
  NLRefcountableObject *v5; // rax
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  struct _TP_CLEANUP_GROUP *v7; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // ecx
  int v12; // r8d
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-20h] BYREF
  struct AdminConfiguredNameMappings *v14[2]; // [rsp+38h] [rbp-18h] BYREF

  pftDueTime = 0;
  if ( !gfInitialized )
  {
    AcquireSRWLockExclusive(&gsrwDomainNameMapperLock);
    if ( gfInitialized )
    {
LABEL_30:
      ReleaseSRWLockExclusive(&gsrwDomainNameMapperLock);
      return;
    }
    v14[0] = 0;
    v0 = AdminConfiguredNameMappings::StaticLoadFromDiskCache(v14);
    v1 = v14[0];
    if ( !v0 )
    {
      v2 = AdminConfiguredNameMappings::StaticSetCurrentMappings(v14[0]);
      if ( v2 )
        NLRefcountableObject::ReleaseReference(v2);
    }
    if ( v1 )
      NLRefcountableObject::ReleaseReference(v1);
    v14[0] = 0;
    v3 = ScannerInfoNameMappings::StaticLoadFromDiskCache(v14);
    v4 = v14[0];
    if ( !v3 )
    {
      v5 = ScannerInfoNameMappings::StaticSetCurrentMappings(v14[0]);
      if ( v5 )
        NLRefcountableObject::ReleaseReference(v5);
    }
    if ( v4 )
      NLRefcountableObject::ReleaseReference(v4);
    _gTPCallbackEnv.Version = 3;
    *(_OWORD *)&_gTPCallbackEnv.RaceDll = 0;
    _gTPCallbackEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    _gTPCallbackEnv.Pool = 0;
    _gTPCallbackEnv.CleanupGroup = 0;
    _gTPCallbackEnv.CleanupGroupCancelCallback = 0;
    _gTPCallbackEnv.FinalizationCallback = 0;
    _gTPCallbackEnv.u.Flags = 0;
    _gTPCallbackEnv.Size = 72;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    _gpTPCleanupGroup = ThreadpoolCleanupGroup;
    v7 = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      _gTPCallbackEnv.CleanupGroup = ThreadpoolCleanupGroup;
      _gTPCallbackEnv.CleanupGroupCancelCallback = 0;
      ThreadpoolTimer = CreateThreadpoolTimer(NlDomainNameMapperPeriodicTimerCallback, 0, &_gTPCallbackEnv);
      gpTPTimer = ThreadpoolTimer;
      if ( !ThreadpoolTimer )
      {
        v7 = _gpTPCleanupGroup;
LABEL_24:
        if ( !gfInitialized )
        {
          if ( v7 )
          {
            CloseThreadpoolCleanupGroupMembers(v7, 1, 0);
            CloseThreadpoolCleanupGroup(_gpTPCleanupGroup);
            ThreadpoolTimer = gpTPTimer;
            _gpTPCleanupGroup = 0;
          }
          if ( ThreadpoolTimer )
          {
            CloseThreadpoolTimer(ThreadpoolTimer);
            gpTPTimer = 0;
          }
          memset_0(&_gTPCallbackEnv, 0, sizeof(_gTPCallbackEnv));
        }
        goto LABEL_30;
      }
      pftDueTime.dwHighDateTime = -101;
      pftDueTime.dwLowDateTime = 1791696896;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0xDBBA0u, 0);
      if ( !dword_1800F129C && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v9, (unsigned int)MailslotDiscoveryEnabled, v10, 1, (__int64)v14);
      if ( (unsigned int)NlRunningOnDomainController()
        && !dword_1800F128C
        && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
      {
        McGenEventWrite_EtwEventWriteTransfer(v11, (unsigned int)DCListeningOnMailslots, v12, 1, (__int64)v14);
      }
      v7 = _gpTPCleanupGroup;
      gfInitialized = 1;
    }
    ThreadpoolTimer = gpTPTimer;
    goto LABEL_24;
  }
}

```

## disassembly

```asm
0x180019618  mov     [rsp-8+arg_0], rbx
0x18001961d  mov     [rsp-8+arg_8], rdi
0x180019622  push    rbp
0x180019623  mov     rbp, rsp
0x180019626  sub     rsp, 50h
0x18001962a  mov     rax, cs:__security_cookie
0x180019631  xor     rax, rsp
0x180019634  mov     [rbp+var_8], rax
0x180019638  xor     edi, edi
0x18001963a  cmp     cs:?gfInitialized@@3HA, edi; int gfInitialized
0x180019640  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rdi
0x180019644  jnz     loc_180019864
0x18001964a  lea     rcx, ?gsrwDomainNameMapperLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180019651  call    cs:__imp_AcquireSRWLockExclusive
0x180019657  cmp     cs:?gfInitialized@@3HA, edi; int gfInitialized
0x18001965d  jnz     loc_180019857
0x180019663  lea     rcx, [rbp+var_18]; struct AdminConfiguredNameMappings **
0x180019667  mov     [rbp+var_18], rdi
0x18001966b  call    ?StaticLoadFromDiskCache@AdminConfiguredNameMappings@@CAKPEAPEAV1@@Z; AdminConfiguredNameMappings::StaticLoadFromDiskCache(AdminConfiguredNameMappings * *)
0x180019670  mov     rbx, [rbp+var_18]
0x180019674  test    eax, eax
0x180019676  jnz     short loc_18001968D
0x180019678  mov     rcx, rbx; struct AdminConfiguredNameMappings *
0x18001967b  call    ?StaticSetCurrentMappings@AdminConfiguredNameMappings@@CAPEAV1@PEAV1@@Z; AdminConfiguredNameMappings::StaticSetCurrentMappings(AdminConfiguredNameMappings *)
0x180019680  test    rax, rax
0x180019683  jz      short loc_18001968D
0x180019685  mov     rcx, rax; this
0x180019688  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18001968d  test    rbx, rbx
0x180019690  jz      short loc_18001969A
0x180019692  mov     rcx, rbx; this
0x180019695  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18001969a  lea     rcx, [rbp+var_18]; struct ScannerInfoNameMappings **
0x18001969e  mov     [rbp+var_18], rdi
0x1800196a2  call    ?StaticLoadFromDiskCache@ScannerInfoNameMappings@@CAKPEAPEAV1@@Z; ScannerInfoNameMappings::StaticLoadFromDiskCache(ScannerInfoNameMappings * *)
0x1800196a7  mov     rbx, [rbp+var_18]
0x1800196ab  test    eax, eax
0x1800196ad  jnz     short loc_1800196C4
0x1800196af  mov     rcx, rbx; struct ScannerInfoNameMappings *
0x1800196b2  call    ?StaticSetCurrentMappings@ScannerInfoNameMappings@@CAPEAV1@PEAV1@@Z; ScannerInfoNameMappings::StaticSetCurrentMappings(ScannerInfoNameMappings *)
0x1800196b7  test    rax, rax
0x1800196ba  jz      short loc_1800196C4
0x1800196bc  mov     rcx, rax; this
0x1800196bf  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x1800196c4  test    rbx, rbx
0x1800196c7  jz      short loc_1800196D1
0x1800196c9  mov     rcx, rbx; this
0x1800196cc  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x1800196d1  xorps   xmm0, xmm0
0x1800196d4  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x1800196de  mov     ebx, 1
0x1800196e3  movdqa  xmmword ptr cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x1800196eb  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebx; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x1800196f1  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x1800196f8  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x1800196ff  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x180019706  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001970d  mov     dword ptr cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, edi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x180019713  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001971d  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180019723  mov     cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * _gpTPCleanupGroup
0x18001972a  mov     rcx, rax
0x18001972d  test    rax, rax
0x180019730  jz      loc_1800197F6
0x180019736  lea     r8, ?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001973d  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x180019744  xor     edx, edx; pv
0x180019746  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001974d  lea     rcx, ?NlDomainNameMapperPeriodicTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019754  call    cs:__imp_CreateThreadpoolTimer
0x18001975a  mov     cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * gpTPTimer
0x180019761  test    rax, rax
0x180019764  jz      loc_180019880
0x18001976a  xor     r9d, r9d; msWindowLength
0x18001976d  mov     [rbp+pftDueTime.dwHighDateTime], 0FFFFFF9Bh
0x180019774  mov     r8d, 0DBBA0h; msPeriod
0x18001977a  mov     [rbp+pftDueTime.dwLowDateTime], 6ACB2000h
0x180019781  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180019785  mov     rcx, rax; pti
0x180019788  call    cs:__imp_SetThreadpoolTimer
0x18001978e  cmp     cs:dword_1800F129C, edi
0x180019794  jnz     short loc_1800197B7
0x180019796  test    cs:Microsoft_Windows_Security_NetlogonEnableBits, 8
0x18001979d  jz      short loc_1800197B7
0x18001979f  lea     rax, [rbp+var_18]
0x1800197a3  mov     r9d, ebx
0x1800197a6  lea     rdx, MailslotDiscoveryEnabled
0x1800197ad  mov     [rsp+50h+var_30], rax
0x1800197b2  call    McGenEventWrite_EtwEventWriteTransfer
0x1800197b7  call    ?NlRunningOnDomainController@@YAHXZ; NlRunningOnDomainController(void)
0x1800197bc  test    eax, eax
0x1800197be  jz      short loc_1800197E9
0x1800197c0  cmp     cs:dword_1800F128C, edi
0x1800197c6  jnz     short loc_1800197E9
0x1800197c8  test    cs:Microsoft_Windows_Security_NetlogonEnableBits, 8
0x1800197cf  jz      short loc_1800197E9
0x1800197d1  lea     rax, [rbp+var_18]
0x1800197d5  mov     r9d, ebx
0x1800197d8  lea     rdx, DCListeningOnMailslots
0x1800197df  mov     [rsp+50h+var_30], rax
0x1800197e4  call    McGenEventWrite_EtwEventWriteTransfer
0x1800197e9  mov     rcx, cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x1800197f0  mov     cs:?gfInitialized@@3HA, ebx; int gfInitialized
0x1800197f6  mov     rax, cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA; _TP_TIMER * gpTPTimer
0x1800197fd  cmp     cs:?gfInitialized@@3HA, edi; int gfInitialized
0x180019803  jnz     short loc_180019857
0x180019805  test    rcx, rcx
0x180019808  jz      short loc_180019830
0x18001980a  xor     r8d, r8d; pvCleanupContext
0x18001980d  mov     edx, ebx; fCancelPendingCallbacks
0x18001980f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180019815  mov     rcx, cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x18001981c  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180019822  mov     rax, cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA; _TP_TIMER * gpTPTimer
0x180019829  mov     cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rdi; _TP_CLEANUP_GROUP * _gpTPCleanupGroup
0x180019830  test    rax, rax
0x180019833  jz      short loc_180019845
0x180019835  mov     rcx, rax; pti
0x180019838  call    cs:__imp_CloseThreadpoolTimer
0x18001983e  mov     cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA, rdi; _TP_TIMER * gpTPTimer
0x180019845  xor     edx, edx; Val
0x180019847  lea     rcx, ?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; void *
0x18001984e  lea     r8d, [rdx+48h]; Size
0x180019852  call    memset_0
0x180019857  lea     rcx, ?gsrwDomainNameMapperLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001985e  call    cs:__imp_ReleaseSRWLockExclusive
0x180019864  mov     rcx, [rbp+var_8]
0x180019868  xor     rcx, rsp; StackCookie
0x18001986b  call    __security_check_cookie
0x180019870  mov     rbx, [rsp+50h+arg_0]
0x180019875  mov     rdi, [rsp+50h+arg_8]
0x18001987a  add     rsp, 50h
0x18001987e  pop     rbp
0x18001987f  retn
0x180019880  mov     rcx, cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * _gpTPCleanupGroup
0x180019887  jmp     loc_1800197FD
```
