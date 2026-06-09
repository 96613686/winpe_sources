# NlSiteInitialize(void)

- ea: `0x180046a0c`
- end: `0x180046cb1`
- name: `?NlSiteInitialize@@YAKXZ`
- size: `677`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006f490`

## callees

- `0x180018414`
- `0x18001843c`
- `0x18001858c`
- `0x18004651c`
- `0x180046630`
- `0x18004688c`
- `0x180046a0c`
- `0x18004c890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b52`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046bf0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180046bde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180046bde`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180046a7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180046a91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180046a7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180046a91`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids);
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
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids, LastError);
      return v2;
    }
    return v2;
  }
  if ( NlGlobalMemberWorkstation )
  {
    v5 = NlSetSiteName(qword_1800F11F0, 0);
    v2 = v5;
    if ( v5 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          138,
          (unsigned int)WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids,
          (_DWORD)qword_1800F11F0,
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids);
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
0x180046a0c  mov     [rsp+arg_0], rbx
0x180046a11  mov     [rsp+arg_8], rbp
0x180046a16  push    rdi
0x180046a17  sub     rsp, 30h
0x180046a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a22  lea     rbp, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180046a29  test    byte ptr [rcx+1Ch], 20h
0x180046a2d  jz      short loc_180046A46
0x180046a2f  cmp     byte ptr [rcx+19h], 4
0x180046a33  jb      short loc_180046A46
0x180046a35  mov     rcx, [rcx+10h]
0x180046a39  mov     edx, 88h
0x180046a3e  mov     r8, rbp
0x180046a41  call    WPP_SF_
0x180046a46  xor     edi, edi
0x180046a48  lea     rcx, ?NlGlobalNoClientSiteEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180046a4f  mov     cs:?gNlSiteCacheLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteCacheLock ...
0x180046a56  mov     cs:?gNlSiteNameLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteNameLock ...
0x180046a5d  mov     cs:?gNlSiteCoverageParameterLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteCoverageParameterLock ...
0x180046a64  mov     cs:?gNlSiteSiteClientTrackingEventLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteSiteClientTrackingEventLock ...
0x180046a6b  mov     cs:?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A.Ptr, rdi; _RTL_SRWLOCK gNlSiteBackgroundLock ...
0x180046a72  mov     cs:?NlGlobalNextClosestSiteRetrieved@@3HA, edi; int NlGlobalNextClosestSiteRetrieved
0x180046a78  mov     cs:?NlGlobalNoClientSiteCount@@3KA, edi; ulong NlGlobalNoClientSiteCount
0x180046a7e  call    cs:__imp_GetSystemTimeAsFileTime
0x180046a84  lea     rcx, ?NlGlobalPartialClientSiteMappingEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180046a8b  mov     cs:?NlGlobalPartialClientSiteMappingCount@@3KA, edi; ulong NlGlobalPartialClientSiteMappingCount
0x180046a91  call    cs:__imp_GetSystemTimeAsFileTime
0x180046a97  mov     cs:?gNlSiteReloadSitesAndSubnetsRequested@@3HA, edi; int gNlSiteReloadSitesAndSubnetsRequested
0x180046a9d  mov     cs:?gNlSiteReloadSitesAndSubnetsWorkerRunning@@3HA, edi; int gNlSiteReloadSitesAndSubnetsWorkerRunning
0x180046aa3  call    ?StaticCreate@CNlGlobalSiteNameCache@@SAKPEAPEAV1@@Z; CNlGlobalSiteNameCache::StaticCreate(CNlGlobalSiteNameCache * *)
0x180046aa8  mov     ebx, eax
0x180046aaa  test    eax, eax
0x180046aac  jz      short loc_180046AE2
0x180046aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ab5  test    byte ptr [rcx+1Ch], 20h
0x180046ab9  jz      loc_180046C9F
0x180046abf  cmp     byte ptr [rcx+19h], 2
0x180046ac3  jb      loc_180046C9F
0x180046ac9  mov     edx, 89h
0x180046ace  mov     rcx, [rcx+10h]
0x180046ad2  mov     r9d, eax
0x180046ad5  mov     r8, rbp
0x180046ad8  call    WPP_SF_d
0x180046add  jmp     loc_180046C9F
0x180046ae2  cmp     cs:?NlGlobalMemberWorkstation@@3HA, edi; int NlGlobalMemberWorkstation
0x180046ae8  jz      short loc_180046B3E
0x180046aea  mov     rcx, cs:qword_1800F11F0; unsigned __int16 *
0x180046af1  xor     edx, edx; int *
0x180046af3  call    ?NlSetSiteName@@YAKPEAGPEAH@Z; NlSetSiteName(ushort *,int *)
0x180046af8  mov     ebx, eax
0x180046afa  test    eax, eax
0x180046afc  jz      loc_180046C7B
0x180046b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b09  test    byte ptr [rcx+1Ch], 20h
0x180046b0d  jz      loc_180046C9F
0x180046b13  cmp     byte ptr [rcx+19h], 2
0x180046b17  jb      loc_180046C9F
0x180046b1d  mov     r9, cs:qword_1800F11F0
0x180046b24  mov     edx, 8Ah
0x180046b29  mov     rcx, [rcx+10h]
0x180046b2d  mov     r8, rbp
0x180046b30  mov     [rsp+38h+var_18], eax
0x180046b34  call    WPP_SF_Sd
0x180046b39  jmp     loc_180046C9F
0x180046b3e  xor     r9d, r9d; lpName
0x180046b41  mov     cs:?gfNlInitialSitesAndSubnetsLoadCompleted@@3HA, edi; int gfNlInitialSitesAndSubnetsLoadCompleted
0x180046b47  xor     r8d, r8d; bInitialState
0x180046b4a  xor     ecx, ecx; lpEventAttributes
0x180046b4c  lea     ebx, [r9+1]
0x180046b50  mov     edx, ebx; bManualReset
0x180046b52  call    cs:__imp_CreateEventW
0x180046b58  mov     cs:?ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent@@3PEAXEA, rax; void * ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent
0x180046b5f  test    rax, rax
0x180046b62  jnz     short loc_180046B91
0x180046b64  call    cs:__imp_GetLastError
0x180046b6a  mov     ebx, eax
0x180046b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b73  test    byte ptr [rcx+1Ch], 20h
0x180046b77  jz      loc_180046C9F
0x180046b7d  cmp     byte ptr [rcx+19h], 2
0x180046b81  jb      loc_180046C9F
0x180046b87  mov     edx, 8Bh
0x180046b8c  jmp     loc_180046ACE
0x180046b91  xorps   xmm0, xmm0
0x180046b94  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046b9e  movdqa  xmmword ptr cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046ba6  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046bad  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046bb4  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046bbb  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046bc2  mov     dword ptr cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, edi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046bc8  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebx; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046bce  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046bd8  mov     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, ebx; int gNlSiteTPCallbackEnvInitialized
0x180046bde  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180046be4  mov     cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180046beb  test    rax, rax
0x180046bee  jnz     short loc_180046C1D
0x180046bf0  call    cs:__imp_GetLastError
0x180046bf6  mov     ebx, eax
0x180046bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180046bff  test    byte ptr [rcx+1Ch], 20h
0x180046c03  jz      loc_180046C9F
0x180046c09  cmp     byte ptr [rcx+19h], 2
0x180046c0d  jb      loc_180046C9F
0x180046c13  mov     edx, 8Ch
0x180046c18  jmp     loc_180046ACE
0x180046c1d  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046c24  mov     cs:?gNlSiteTPCallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 gNlSiteTPCallbackEnv ...
0x180046c2b  call    ?NlSetDCSiteName@@YAKXZ; NlSetDCSiteName(void)
0x180046c30  mov     ebx, eax
0x180046c32  test    eax, eax
0x180046c34  jz      short loc_180046C53
0x180046c36  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c3d  test    byte ptr [rcx+1Ch], 20h
0x180046c41  jz      short loc_180046C9F
0x180046c43  cmp     byte ptr [rcx+19h], 2
0x180046c47  jb      short loc_180046C9F
0x180046c49  mov     edx, 8Dh
0x180046c4e  jmp     loc_180046ACE
0x180046c53  call    ?NlRequestSitesAndSubnetsCacheRebuild@@YAKXZ; NlRequestSitesAndSubnetsCacheRebuild(void)
0x180046c58  mov     ebx, eax
0x180046c5a  test    eax, eax
0x180046c5c  jz      short loc_180046C7B
0x180046c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c65  test    byte ptr [rcx+1Ch], 20h
0x180046c69  jz      short loc_180046C9F
0x180046c6b  cmp     byte ptr [rcx+19h], 2
0x180046c6f  jb      short loc_180046C9F
0x180046c71  mov     edx, 8Eh
0x180046c76  jmp     loc_180046ACE
0x180046c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c82  test    byte ptr [rcx+1Ch], 20h
0x180046c86  jz      short loc_180046C9F
0x180046c88  cmp     byte ptr [rcx+19h], 4
0x180046c8c  jb      short loc_180046C9F
0x180046c8e  mov     rcx, [rcx+10h]
0x180046c92  mov     edx, 8Fh
0x180046c97  mov     r8, rbp
0x180046c9a  call    WPP_SF_
0x180046c9f  mov     rbp, [rsp+38h+arg_8]
0x180046ca4  mov     eax, ebx
0x180046ca6  mov     rbx, [rsp+38h+arg_0]
0x180046cab  add     rsp, 30h
0x180046caf  pop     rdi
0x180046cb0  retn
```
