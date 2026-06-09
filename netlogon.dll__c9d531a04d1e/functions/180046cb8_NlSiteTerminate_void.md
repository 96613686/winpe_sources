# NlSiteTerminate(void)

- ea: `0x180046cb8`
- end: `0x180046e95`
- name: `?NlSiteTerminate@@YAXXZ`
- size: `477`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028834`

## callees

- `0x18000b790`
- `0x180018414`
- `0x180046cb8`
- `0x180049d04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046d96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046d96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046ceb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046ceb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180046d36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180046d36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180046d43`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180046d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046da8`

## pseudocode

```c
void NlSiteTerminate(void)
{
  struct _TP_CLEANUP_GROUP *v0; // rax
  __int64 v1; // rdx
  __int64 v2; // r8
  ScannerInfoNameMappings *v3; // rcx

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids);
  AcquireSRWLockExclusive(&gNlSiteBackgroundLock);
  v0 = gNlSiteTPCleanupGroup;
  if ( gNlSiteTPCleanupGroup )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids);
      v0 = gNlSiteTPCleanupGroup;
    }
    CloseThreadpoolCleanupGroupMembers(v0, 1, 0);
    CloseThreadpoolCleanupGroup(gNlSiteTPCleanupGroup);
    gNlSiteTPCleanupGroup = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids);
  }
  if ( gNlSiteTPCallbackEnvInitialized )
    gNlSiteTPCallbackEnvInitialized = 0;
  ReleaseSRWLockExclusive(&gNlSiteBackgroundLock);
  if ( ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent )
  {
    CloseHandle(ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent);
    ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent = 0;
  }
  gfNlInitialSitesAndSubnetsLoadCompleted = 0;
  if ( gpNlSitesAndSubnetsCache )
  {
    NLRefcountableObject::ReleaseReference((NLRefcountableObject *)gpNlSitesAndSubnetsCache);
    gpNlSitesAndSubnetsCache = 0;
  }
  if ( gpNlGlobalSiteNameCache )
  {
    NLRefcountableObject::ReleaseReference(gpNlGlobalSiteNameCache);
    gpNlGlobalSiteNameCache = 0;
  }
  v3 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dddddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v1,
        v2,
        NlSiteEntryCount,
        NlSubnetCount,
        CNlGlobalSiteNameCache::s_ObjectCount,
        CNlIsmSiteNameIndexCache::s_ObjectCount,
        CNlNextClosestSiteInfo::s_ObjectCount,
        CNlSiteTable::s_ObjectCount,
        CNlSubnetTable::s_ObjectCount,
        CNlSitesAndSubnetsCache::s_ObjectCount);
      v3 = WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)v3 + 28) & 0x20) != 0 && *((_BYTE *)v3 + 25) >= 4u )
      WPP_SF_(*((_QWORD *)v3 + 2), 148, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids);
  }
}

```

## disassembly

```asm
0x180046cb8  sub     rsp, 68h
0x180046cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180046cc3  test    byte ptr [rcx+1Ch], 20h
0x180046cc7  jz      short loc_180046CE4
0x180046cc9  cmp     byte ptr [rcx+19h], 4
0x180046ccd  jb      short loc_180046CE4
0x180046ccf  mov     rcx, [rcx+10h]
0x180046cd3  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180046cda  mov     edx, 90h
0x180046cdf  call    WPP_SF_
0x180046ce4  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180046ceb  call    cs:__imp_AcquireSRWLockExclusive
0x180046cf1  mov     rax, cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180046cf8  test    rax, rax
0x180046cfb  jz      short loc_180046D7C
0x180046cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d04  test    byte ptr [rcx+1Ch], 20h
0x180046d08  jz      short loc_180046D2C
0x180046d0a  cmp     byte ptr [rcx+19h], 4
0x180046d0e  jb      short loc_180046D2C
0x180046d10  mov     rcx, [rcx+10h]
0x180046d14  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180046d1b  mov     edx, 91h
0x180046d20  call    WPP_SF_
0x180046d25  mov     rax, cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180046d2c  xor     r8d, r8d; pvCleanupContext
0x180046d2f  mov     rcx, rax; ptpcg
0x180046d32  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180046d36  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180046d3c  mov     rcx, cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180046d43  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180046d49  mov     cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, 0; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180046d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d5b  test    byte ptr [rcx+1Ch], 20h
0x180046d5f  jz      short loc_180046D7C
0x180046d61  cmp     byte ptr [rcx+19h], 4
0x180046d65  jb      short loc_180046D7C
0x180046d67  mov     rcx, [rcx+10h]
0x180046d6b  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180046d72  mov     edx, 92h
0x180046d77  call    WPP_SF_
0x180046d7c  cmp     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, 0; int gNlSiteTPCallbackEnvInitialized
0x180046d83  jz      short loc_180046D8F
0x180046d85  mov     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, 0; int gNlSiteTPCallbackEnvInitialized
0x180046d8f  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180046d96  call    cs:__imp_ReleaseSRWLockExclusive
0x180046d9c  mov     rcx, cs:?ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent@@3PEAXEA; hObject
0x180046da3  test    rcx, rcx
0x180046da6  jz      short loc_180046DB9
0x180046da8  call    cs:__imp_CloseHandle
0x180046dae  mov     cs:?ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent@@3PEAXEA, 0; void * ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent
0x180046db9  mov     rcx, cs:?gpNlSitesAndSubnetsCache@@3PEAVCNlSitesAndSubnetsCache@@EA; this
0x180046dc0  mov     cs:?gfNlInitialSitesAndSubnetsLoadCompleted@@3HA, 0; int gfNlInitialSitesAndSubnetsLoadCompleted
0x180046dca  test    rcx, rcx
0x180046dcd  jz      short loc_180046DDF
0x180046dcf  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x180046dd4  mov     cs:?gpNlSitesAndSubnetsCache@@3PEAVCNlSitesAndSubnetsCache@@EA, 0; CNlSitesAndSubnetsCache * gpNlSitesAndSubnetsCache
0x180046ddf  mov     rcx, cs:?gpNlGlobalSiteNameCache@@3PEAVCNlGlobalSiteNameCache@@EA; this
0x180046de6  test    rcx, rcx
0x180046de9  jz      short loc_180046DFB
0x180046deb  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x180046df0  mov     cs:?gpNlGlobalSiteNameCache@@3PEAVCNlGlobalSiteNameCache@@EA, 0; CNlGlobalSiteNameCache * gpNlGlobalSiteNameCache
0x180046dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e02  test    byte ptr [rcx+1Ch], 20h
0x180046e06  jz      loc_180046E90
0x180046e0c  cmp     byte ptr [rcx+19h], 4
0x180046e10  jb      short loc_180046E6F
0x180046e12  mov     eax, cs:?s_ObjectCount@CNlSitesAndSubnetsCache@@0KA; ulong CNlSitesAndSubnetsCache::s_ObjectCount
0x180046e18  mov     r9d, cs:?NlSiteEntryCount@@3KA; ulong NlSiteEntryCount
0x180046e1f  mov     rcx, [rcx+10h]
0x180046e23  mov     [rsp+68h+var_18], eax
0x180046e27  mov     eax, cs:?s_ObjectCount@CNlSubnetTable@@0KA; ulong CNlSubnetTable::s_ObjectCount
0x180046e2d  mov     [rsp+68h+var_20], eax
0x180046e31  mov     eax, cs:?s_ObjectCount@CNlSiteTable@@0KA; ulong CNlSiteTable::s_ObjectCount
0x180046e37  mov     [rsp+68h+var_28], eax
0x180046e3b  mov     eax, cs:?s_ObjectCount@CNlNextClosestSiteInfo@@0KA; ulong CNlNextClosestSiteInfo::s_ObjectCount
0x180046e41  mov     [rsp+68h+var_30], eax
0x180046e45  mov     eax, cs:?s_ObjectCount@CNlIsmSiteNameIndexCache@@0KA; ulong CNlIsmSiteNameIndexCache::s_ObjectCount
0x180046e4b  mov     [rsp+68h+var_38], eax
0x180046e4f  mov     eax, cs:?s_ObjectCount@CNlGlobalSiteNameCache@@0KA; ulong CNlGlobalSiteNameCache::s_ObjectCount
0x180046e55  mov     [rsp+68h+var_40], eax
0x180046e59  mov     eax, cs:?NlSubnetCount@@3KA; ulong NlSubnetCount
0x180046e5f  mov     [rsp+68h+var_48], eax
0x180046e63  call    WPP_SF_dddddddd
0x180046e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e6f  test    byte ptr [rcx+1Ch], 20h
0x180046e73  jz      short loc_180046E90
0x180046e75  cmp     byte ptr [rcx+19h], 4
0x180046e79  jb      short loc_180046E90
0x180046e7b  mov     rcx, [rcx+10h]
0x180046e7f  lea     r8, WPP_413690e391cd30eb0a32e926f9ccbd77_Traceguids
0x180046e86  mov     edx, 94h
0x180046e8b  call    WPP_SF_
0x180046e90  add     rsp, 68h
0x180046e94  retn
```
