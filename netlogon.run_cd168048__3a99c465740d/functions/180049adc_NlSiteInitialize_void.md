# NlSiteInitialize(void)

- ea: `0x180049adc`
- end: `0x180049da6`
- name: `?NlSiteInitialize@@YAKXZ`
- size: `714`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800747cc`

## callees

- `0x180018f38`
- `0x180018f68`
- `0x1800190d4`
- `0x18004955c`
- `0x1800496b4`
- `0x180049924`
- `0x180049adc`
- `0x18004fd98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049c2e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049c2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049cde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180049cc6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180049cc6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049b4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049b67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049b4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049b67`

## pseudocode

```c
__int64 NlSiteInitialize(void)
{
  struct CNlGlobalSiteNameCache **v0; // rcx
  unsigned int LastError; // eax
  unsigned int v2; // ebx
  ScannerInfoNameMappings *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
  gNlSiteCacheLock.Ptr = 0;
  gNlSiteNameLock.Ptr = 0;
  gNlSiteCoverageParameterLock.Ptr = 0;
  gNlSiteSiteClientTrackingEventLock.Ptr = 0;
  gNlSiteBackgroundLock.Ptr = 0;
  NlGlobalNextClosestSiteRetrieved = 0;
  NlGlobalNoClientSiteCount = 0;
  GetSystemTimeAsFileTime(&NlGlobalNoClientSiteEventTime);
  NlGlobalPartialClientSiteMappingCount = 0;
  GetSystemTimeAsFileTime(&NlGlobalPartialClientSiteMappingEventTime);
  gNlSiteReloadSitesAndSubnetsRequested = 0;
  gNlSiteReloadSitesAndSubnetsWorkerRunning = 0;
  LastError = CNlGlobalSiteNameCache::StaticCreate(v0);
  v2 = LastError;
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 137;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids, LastError);
      return v2;
    }
    return v2;
  }
  if ( NlGlobalMemberWorkstation )
  {
    v5 = NlSetSiteName(qword_1800F81F0, 0);
    v2 = v5;
    if ( v5 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          138,
          (unsigned int)WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids,
          (_DWORD)qword_1800F81F0,
          v5);
      return v2;
    }
    goto LABEL_30;
  }
  gfNlInitialSitesAndSubnetsLoadCompleted = 0;
  ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent = CreateEventW(0, 1, 0, 0);
  if ( ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent )
  {
    gNlSiteTPCallbackEnv.Version = 3;
    *(_OWORD *)&gNlSiteTPCallbackEnv.RaceDll = 0;
    gNlSiteTPCallbackEnv.Pool = 0;
    gNlSiteTPCallbackEnv.CleanupGroup = 0;
    gNlSiteTPCallbackEnv.CleanupGroupCancelCallback = 0;
    gNlSiteTPCallbackEnv.FinalizationCallback = 0;
    gNlSiteTPCallbackEnv.u.Flags = 0;
    gNlSiteTPCallbackEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    gNlSiteTPCallbackEnv.Size = 72;
    gNlSiteTPCallbackEnvInitialized = 1;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    gNlSiteTPCleanupGroup = ThreadpoolCleanupGroup;
    if ( !ThreadpoolCleanupGroup )
    {
      LastError = GetLastError();
      v2 = LastError;
      v3 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = 140;
        goto LABEL_8;
      }
      return v2;
    }
    gNlSiteTPCallbackEnv.CleanupGroup = ThreadpoolCleanupGroup;
    gNlSiteTPCallbackEnv.CleanupGroupCancelCallback = 0;
    LastError = NlSetDCSiteName();
    v2 = LastError;
    if ( LastError )
    {
      v3 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = 141;
        goto LABEL_8;
      }
      return v2;
    }
    LastError = NlRequestSitesAndSubnetsCacheRebuild();
    v2 = LastError;
    if ( LastError )
    {
      v3 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = 142;
        goto LABEL_8;
      }
      return v2;
    }
LABEL_30:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
    return v2;
  }
  LastError = GetLastError();
  v2 = LastError;
  v3 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = 139;
    goto LABEL_8;
  }
  return v2;
}

```

## disassembly

```asm
0x180049adc  mov     [rsp+arg_0], rbx
0x180049ae1  mov     [rsp+arg_8], rbp
0x180049ae6  push    rdi
0x180049ae7  sub     rsp, 30h
0x180049aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180049af2  lea     rbp, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x180049af9  test    byte ptr [rcx+1Ch], 20h
0x180049afd  jz      short loc_180049B16
0x180049aff  cmp     byte ptr [rcx+19h], 4
0x180049b03  jb      short loc_180049B16
0x180049b05  mov     rcx, [rcx+10h]
0x180049b09  mov     edx, 88h
0x180049b0e  mov     r8, rbp
0x180049b11  call    WPP_SF_
0x180049b16  xor     edi, edi
0x180049b18  lea     rcx, ?NlGlobalNoClientSiteEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180049b1f  mov     cs:?gNlSiteCacheLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteCacheLock ...
0x180049b26  mov     cs:?gNlSiteNameLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteNameLock ...
0x180049b2d  mov     cs:?gNlSiteCoverageParameterLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteCoverageParameterLock ...
0x180049b34  mov     cs:?gNlSiteSiteClientTrackingEventLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteSiteClientTrackingEventLock ...
0x180049b3b  mov     cs:?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteBackgroundLock ...
0x180049b42  mov     cs:?NlGlobalNextClosestSiteRetrieved@@3HA, edi; int NlGlobalNextClosestSiteRetrieved
0x180049b48  mov     cs:?NlGlobalNoClientSiteCount@@3KA, edi; ulong NlGlobalNoClientSiteCount
0x180049b4e  call    cs:__imp_GetSystemTimeAsFileTime
0x180049b55  nop     dword ptr [rax+rax+00h]
0x180049b5a  lea     rcx, ?NlGlobalPartialClientSiteMappingEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180049b61  mov     cs:?NlGlobalPartialClientSiteMappingCount@@3KA, edi; ulong NlGlobalPartialClientSiteMappingCount
0x180049b67  call    cs:__imp_GetSystemTimeAsFileTime
0x180049b6e  nop     dword ptr [rax+rax+00h]
0x180049b73  mov     cs:?gNlSiteReloadSitesAndSubnetsRequested@@3HA, edi; int gNlSiteReloadSitesAndSubnetsRequested
0x180049b79  mov     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, edi; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x180049b7f  call    ?StaticCreate@CNlGlobalSiteNameCache@@SAKPEAPEAV1@@Z; CNlGlobalSiteNameCache::StaticCreate(CNlGlobalSiteNameCache * *)
0x180049b84  mov     ebx, eax
0x180049b86  test    eax, eax
0x180049b88  jz      short loc_180049BBE
0x180049b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b91  test    byte ptr [rcx+1Ch], 20h
0x180049b95  jz      loc_180049D93
0x180049b9b  cmp     byte ptr [rcx+19h], 2
0x180049b9f  jb      loc_180049D93
0x180049ba5  mov     edx, 89h
0x180049baa  mov     rcx, [rcx+10h]
0x180049bae  mov     r9d, eax
0x180049bb1  mov     r8, rbp
0x180049bb4  call    WPP_SF_d
0x180049bb9  jmp     loc_180049D93
0x180049bbe  cmp     cs:?NlGlobalMemberWorkstation@@3HA, edi; int NlGlobalMemberWorkstation
0x180049bc4  jz      short loc_180049C1A
0x180049bc6  mov     rcx, cs:qword_1800F81F0; unsigned __int16 *
0x180049bcd  xor     edx, edx; int *
0x180049bcf  call    ?NlSetSiteName@@YAKPEAGPEAH@Z; NlSetSiteName(ushort *,int *)
0x180049bd4  mov     ebx, eax
0x180049bd6  test    eax, eax
0x180049bd8  jz      loc_180049D6F
0x180049bde  mov     rcx, cs:WPP_GLOBAL_Control
0x180049be5  test    byte ptr [rcx+1Ch], 20h
0x180049be9  jz      loc_180049D93
0x180049bef  cmp     byte ptr [rcx+19h], 2
0x180049bf3  jb      loc_180049D93
0x180049bf9  mov     r9, cs:qword_1800F81F0
0x180049c00  mov     edx, 8Ah
0x180049c05  mov     rcx, [rcx+10h]
0x180049c09  mov     r8, rbp
0x180049c0c  mov     [rsp+38h+var_18], eax
0x180049c10  call    WPP_SF_Sd
0x180049c15  jmp     loc_180049D93
0x180049c1a  xor     r9d, r9d; lpName
0x180049c1d  mov     cs:?gfNlInitialSitesAndSubnetsLoadCompleted@@3HA, edi; int gfNlInitialSitesAndSubnetsLoadCompleted
0x180049c23  xor     r8d, r8d; bInitialState
0x180049c26  xor     ecx, ecx; lpEventAttributes
0x180049c28  lea     ebx, [r9+1]
0x180049c2c  mov     edx, ebx; bManualReset
0x180049c2e  call    cs:__imp_CreateEventW
0x180049c35  nop     dword ptr [rax+rax+00h]
0x180049c3a  mov     cs:?ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent@@3PEAXEA, rax; void * ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent
0x180049c41  test    rax, rax
0x180049c44  jnz     short loc_180049C79
0x180049c46  call    cs:__imp_GetLastError
0x180049c4d  nop     dword ptr [rax+rax+00h]
0x180049c52  mov     ebx, eax
0x180049c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c5b  test    byte ptr [rcx+1Ch], 20h
0x180049c5f  jz      loc_180049D93
0x180049c65  cmp     byte ptr [rcx+19h], 2
0x180049c69  jb      loc_180049D93
0x180049c6f  mov     edx, 8Bh
0x180049c74  jmp     loc_180049BAA
0x180049c79  xorps   xmm0, xmm0
0x180049c7c  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049c86  movdqa  xmmword ptr cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049c8e  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049c95  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049c9c  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049ca3  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049caa  mov     dword ptr cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, edi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049cb0  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebx; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049cb6  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049cc0  mov     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, ebx; int gNlSiteTPCallbackEnvInitialized
0x180049cc6  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180049ccd  nop     dword ptr [rax+rax+00h]
0x180049cd2  mov     cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180049cd9  test    rax, rax
0x180049cdc  jnz     short loc_180049D11
0x180049cde  call    cs:__imp_GetLastError
0x180049ce5  nop     dword ptr [rax+rax+00h]
0x180049cea  mov     ebx, eax
0x180049cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cf3  test    byte ptr [rcx+1Ch], 20h
0x180049cf7  jz      loc_180049D93
0x180049cfd  cmp     byte ptr [rcx+19h], 2
0x180049d01  jb      loc_180049D93
0x180049d07  mov     edx, 8Ch
0x180049d0c  jmp     loc_180049BAA
0x180049d11  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049d18  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180049d1f  call    ?NlSetDCSiteName@@YAKXZ; NlSetDCSiteName(void)
0x180049d24  mov     ebx, eax
0x180049d26  test    eax, eax
0x180049d28  jz      short loc_180049D47
0x180049d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d31  test    byte ptr [rcx+1Ch], 20h
0x180049d35  jz      short loc_180049D93
0x180049d37  cmp     byte ptr [rcx+19h], 2
0x180049d3b  jb      short loc_180049D93
0x180049d3d  mov     edx, 8Dh
0x180049d42  jmp     loc_180049BAA
0x180049d47  call    ?NlRequestSitesAndSubnetsCacheRebuild@@YAKXZ; NlRequestSitesAndSubnetsCacheRebuild(void)
0x180049d4c  mov     ebx, eax
0x180049d4e  test    eax, eax
0x180049d50  jz      short loc_180049D6F
0x180049d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d59  test    byte ptr [rcx+1Ch], 20h
0x180049d5d  jz      short loc_180049D93
0x180049d5f  cmp     byte ptr [rcx+19h], 2
0x180049d63  jb      short loc_180049D93
0x180049d65  mov     edx, 8Eh
0x180049d6a  jmp     loc_180049BAA
0x180049d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d76  test    byte ptr [rcx+1Ch], 20h
0x180049d7a  jz      short loc_180049D93
0x180049d7c  cmp     byte ptr [rcx+19h], 4
0x180049d80  jb      short loc_180049D93
0x180049d82  mov     rcx, [rcx+10h]
0x180049d86  mov     edx, 8Fh
0x180049d8b  mov     r8, rbp
0x180049d8e  call    WPP_SF_
0x180049d93  mov     rbp, [rsp+38h+arg_8]
0x180049d98  mov     eax, ebx
0x180049d9a  mov     rbx, [rsp+38h+arg_0]
0x180049d9f  add     rsp, 30h
0x180049da3  pop     rdi
0x180049da4  retn
```
