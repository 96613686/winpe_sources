# NlInitializeDomainNameMapper(void)

- ea: `0x18001a1d4`
- end: `0x18001a479`
- name: `?NlInitializeDomainNameMapper@@YAXXZ`
- size: `677`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077610`

## callees

- `0x18000b790`
- `0x18000e910`
- `0x18000f3e4`
- `0x180017a44`
- `0x1800189e8`
- `0x180018ed8`
- `0x18001a1d4`
- `0x18001ab40`
- `0x18001d6a4`
- `0x18001edd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a444`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a444`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a20d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a20d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a3e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001a3e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a356`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a356`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a418`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a418`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a3f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001a3f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a31c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001a31c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001a2df`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001a2df`

## pseudocode

```c
void NlInitializeDomainNameMapper(void)
{
  unsigned int v0; // eax
  NLRefcountableObject *v1; // rbx
  NLRefcountableObject *v2; // rax
  unsigned int v3; // eax
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
      if ( !dword_1800F829C && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v9, (unsigned int)MailslotDiscoveryEnabled, v10, 1, (__int64)v14);
      if ( (unsigned int)NlRunningOnDomainController()
        && !dword_1800F828C
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
0x18001a1d4  mov     [rsp-8+arg_0], rbx
0x18001a1d9  mov     [rsp-8+arg_8], rdi
0x18001a1de  push    rbp
0x18001a1df  mov     rbp, rsp
0x18001a1e2  sub     rsp, 50h
0x18001a1e6  mov     rax, cs:__security_cookie
0x18001a1ed  xor     rax, rsp
0x18001a1f0  mov     [rbp+var_8], rax
0x18001a1f4  xor     edi, edi
0x18001a1f6  cmp     cs:?gfInitialized@@3HA, edi; int gfInitialized
0x18001a1fc  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rdi
0x18001a200  jnz     loc_18001A450
0x18001a206  lea     rcx, ?gsrwDomainNameMapperLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001a20d  call    cs:__imp_AcquireSRWLockExclusive
0x18001a214  nop     dword ptr [rax+rax+00h]
0x18001a219  cmp     cs:?gfInitialized@@3HA, edi; int gfInitialized
0x18001a21f  jnz     loc_18001A43D
0x18001a225  lea     rcx, [rbp+var_18]; struct AdminConfiguredNameMappings **
0x18001a229  mov     [rbp+var_18], rdi
0x18001a22d  call    ?StaticLoadFromDiskCache@AdminConfiguredNameMappings@@CAKPEAPEAV1@@Z; AdminConfiguredNameMappings::StaticLoadFromDiskCache(AdminConfiguredNameMappings * *)
0x18001a232  mov     rbx, [rbp+var_18]
0x18001a236  test    eax, eax
0x18001a238  jnz     short loc_18001A24F
0x18001a23a  mov     rcx, rbx; struct AdminConfiguredNameMappings *
0x18001a23d  call    ?StaticSetCurrentMappings@AdminConfiguredNameMappings@@CAPEAV1@PEAV1@@Z; AdminConfiguredNameMappings::StaticSetCurrentMappings(AdminConfiguredNameMappings *)
0x18001a242  test    rax, rax
0x18001a245  jz      short loc_18001A24F
0x18001a247  mov     rcx, rax; this
0x18001a24a  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18001a24f  test    rbx, rbx
0x18001a252  jz      short loc_18001A25C
0x18001a254  mov     rcx, rbx; this
0x18001a257  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18001a25c  lea     rcx, [rbp+var_18]; struct ScannerInfoNameMappings **
0x18001a260  mov     [rbp+var_18], rdi
0x18001a264  call    ?StaticLoadFromDiskCache@ScannerInfoNameMappings@@CAKPEAPEAV1@@Z; ScannerInfoNameMappings::StaticLoadFromDiskCache(ScannerInfoNameMappings * *)
0x18001a269  mov     rbx, [rbp+var_18]
0x18001a26d  test    eax, eax
0x18001a26f  jnz     short loc_18001A286
0x18001a271  mov     rcx, rbx; struct ScannerInfoNameMappings *
0x18001a274  call    ?StaticSetCurrentMappings@ScannerInfoNameMappings@@CAPEAV1@PEAV1@@Z; ScannerInfoNameMappings::StaticSetCurrentMappings(ScannerInfoNameMappings *)
0x18001a279  test    rax, rax
0x18001a27c  jz      short loc_18001A286
0x18001a27e  mov     rcx, rax; this
0x18001a281  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18001a286  test    rbx, rbx
0x18001a289  jz      short loc_18001A293
0x18001a28b  mov     rcx, rbx; this
0x18001a28e  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x18001a293  xorps   xmm0, xmm0
0x18001a296  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2a0  mov     ebx, 1
0x18001a2a5  movdqa  xmmword ptr cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2ad  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebx; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2b3  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2ba  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2c1  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2c8  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2cf  mov     dword ptr cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, edi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2d5  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a2df  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001a2e6  nop     dword ptr [rax+rax+00h]
0x18001a2eb  mov     cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * _gpTPCleanupGroup
0x18001a2f2  mov     rcx, rax
0x18001a2f5  test    rax, rax
0x18001a2f8  jz      loc_18001A3CA
0x18001a2fe  lea     r8, ?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001a305  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a30c  xor     edx, edx; pv
0x18001a30e  mov     cs:?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 _gTPCallbackEnv ...
0x18001a315  lea     rcx, ?NlDomainNameMapperPeriodicTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001a31c  call    cs:__imp_CreateThreadpoolTimer
0x18001a323  nop     dword ptr [rax+rax+00h]
0x18001a328  mov     cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * gpTPTimer
0x18001a32f  test    rax, rax
0x18001a332  jz      loc_18001A46D
0x18001a338  xor     r9d, r9d; msWindowLength
0x18001a33b  mov     [rbp+pftDueTime.dwHighDateTime], 0FFFFFF9Bh
0x18001a342  mov     r8d, 0DBBA0h; msPeriod
0x18001a348  mov     [rbp+pftDueTime.dwLowDateTime], 6ACB2000h
0x18001a34f  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18001a353  mov     rcx, rax; pti
0x18001a356  call    cs:__imp_SetThreadpoolTimer
0x18001a35d  nop     dword ptr [rax+rax+00h]
0x18001a362  cmp     cs:dword_1800F829C, edi
0x18001a368  jnz     short loc_18001A38B
0x18001a36a  test    cs:Microsoft_Windows_Security_NetlogonEnableBits, 8
0x18001a371  jz      short loc_18001A38B
0x18001a373  lea     rax, [rbp+var_18]
0x18001a377  mov     r9d, ebx
0x18001a37a  lea     rdx, MailslotDiscoveryEnabled
0x18001a381  mov     [rsp+50h+var_30], rax
0x18001a386  call    McGenEventWrite_EtwEventWriteTransfer
0x18001a38b  call    ?NlRunningOnDomainController@@YAHXZ; NlRunningOnDomainController(void)
0x18001a390  test    eax, eax
0x18001a392  jz      short loc_18001A3BD
0x18001a394  cmp     cs:dword_1800F828C, edi
0x18001a39a  jnz     short loc_18001A3BD
0x18001a39c  test    cs:Microsoft_Windows_Security_NetlogonEnableBits, 8
0x18001a3a3  jz      short loc_18001A3BD
0x18001a3a5  lea     rax, [rbp+var_18]
0x18001a3a9  mov     r9d, ebx
0x18001a3ac  lea     rdx, DCListeningOnMailslots
0x18001a3b3  mov     [rsp+50h+var_30], rax
0x18001a3b8  call    McGenEventWrite_EtwEventWriteTransfer
0x18001a3bd  mov     rcx, cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x18001a3c4  mov     cs:?gfInitialized@@3HA, ebx; int gfInitialized
0x18001a3ca  mov     rax, cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA; _TP_TIMER * gpTPTimer
0x18001a3d1  cmp     cs:?gfInitialized@@3HA, edi; int gfInitialized
0x18001a3d7  jnz     short loc_18001A43D
0x18001a3d9  test    rcx, rcx
0x18001a3dc  jz      short loc_18001A410
0x18001a3de  xor     r8d, r8d; pvCleanupContext
0x18001a3e1  mov     edx, ebx; fCancelPendingCallbacks
0x18001a3e3  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001a3ea  nop     dword ptr [rax+rax+00h]
0x18001a3ef  mov     rcx, cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x18001a3f6  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001a3fd  nop     dword ptr [rax+rax+00h]
0x18001a402  mov     rax, cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA; _TP_TIMER * gpTPTimer
0x18001a409  mov     cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rdi; _TP_CLEANUP_GROUP * _gpTPCleanupGroup
0x18001a410  test    rax, rax
0x18001a413  jz      short loc_18001A42B
0x18001a415  mov     rcx, rax; pti
0x18001a418  call    cs:__imp_CloseThreadpoolTimer
0x18001a41f  nop     dword ptr [rax+rax+00h]
0x18001a424  mov     cs:?gpTPTimer@@3PEAU_TP_TIMER@@EA, rdi; _TP_TIMER * gpTPTimer
0x18001a42b  xor     edx, edx; Val
0x18001a42d  lea     rcx, ?_gTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; void *
0x18001a434  lea     r8d, [rdx+48h]; Size
0x18001a438  call    memset_0
0x18001a43d  lea     rcx, ?gsrwDomainNameMapperLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001a444  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a44b  nop     dword ptr [rax+rax+00h]
0x18001a450  mov     rcx, [rbp+var_8]
0x18001a454  xor     rcx, rsp; StackCookie
0x18001a457  call    __security_check_cookie
0x18001a45c  mov     rbx, [rsp+50h+arg_0]
0x18001a461  mov     rdi, [rsp+50h+arg_8]
0x18001a466  add     rsp, 50h
0x18001a46a  pop     rbp
0x18001a46b  retn
0x18001a46d  mov     rcx, cs:?_gpTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * _gpTPCleanupGroup
0x18001a474  jmp     loc_18001A3D1
```
