# NlSiteTerminate(void)

- ea: `0x180049dac`
- end: `0x180049fac`
- name: `?NlSiteTerminate@@YAXXZ`
- size: `512`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180029d5c`

## callees

- `0x18000b790`
- `0x180018f38`
- `0x180049dac`
- `0x18004cff8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049ea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049ea0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049ddf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049ddf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180049e34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180049e34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180049e47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180049e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049eb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049eb8`

## pseudocode

```c
void NlSiteTerminate(void)
{
  struct _TP_CLEANUP_GROUP *v0; // rax
  __int64 v1; // rdx
  __int64 v2; // r8
  ScannerInfoNameMappings *v3; // rcx

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
  AcquireSRWLockExclusive(&gNlSiteBackgroundLock);
  v0 = gNlSiteTPCleanupGroup;
  if ( gNlSiteTPCleanupGroup )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
      v0 = gNlSiteTPCleanupGroup;
    }
    CloseThreadpoolCleanupGroupMembers(v0, 1, 0);
    CloseThreadpoolCleanupGroup(gNlSiteTPCleanupGroup);
    gNlSiteTPCleanupGroup = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
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
      WPP_SF_(*((_QWORD *)v3 + 2), 148, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids);
  }
}

```

## disassembly

```asm
0x180049dac  sub     rsp, 68h
0x180049db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180049db7  test    byte ptr [rcx+1Ch], 20h
0x180049dbb  jz      short loc_180049DD8
0x180049dbd  cmp     byte ptr [rcx+19h], 4
0x180049dc1  jb      short loc_180049DD8
0x180049dc3  mov     rcx, [rcx+10h]
0x180049dc7  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x180049dce  mov     edx, 90h
0x180049dd3  call    WPP_SF_
0x180049dd8  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180049ddf  call    cs:__imp_AcquireSRWLockExclusive
0x180049de6  nop     dword ptr [rax+rax+00h]
0x180049deb  mov     rax, cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180049df2  test    rax, rax
0x180049df5  jz      loc_180049E86
0x180049dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e02  test    byte ptr [rcx+1Ch], 20h
0x180049e06  jz      short loc_180049E2A
0x180049e08  cmp     byte ptr [rcx+19h], 4
0x180049e0c  jb      short loc_180049E2A
0x180049e0e  mov     rcx, [rcx+10h]
0x180049e12  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x180049e19  mov     edx, 91h
0x180049e1e  call    WPP_SF_
0x180049e23  mov     rax, cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180049e2a  xor     r8d, r8d; pvCleanupContext
0x180049e2d  mov     rcx, rax; ptpcg
0x180049e30  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180049e34  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180049e3b  nop     dword ptr [rax+rax+00h]
0x180049e40  mov     rcx, cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180049e47  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180049e4e  nop     dword ptr [rax+rax+00h]
0x180049e53  mov     cs:?gNlSiteTPCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, 0; _TP_CLEANUP_GROUP * gNlSiteTPCleanupGroup
0x180049e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e65  test    byte ptr [rcx+1Ch], 20h
0x180049e69  jz      short loc_180049E86
0x180049e6b  cmp     byte ptr [rcx+19h], 4
0x180049e6f  jb      short loc_180049E86
0x180049e71  mov     rcx, [rcx+10h]
0x180049e75  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x180049e7c  mov     edx, 92h
0x180049e81  call    WPP_SF_
0x180049e86  cmp     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, 0; int gNlSiteTPCallbackEnvInitialized
0x180049e8d  jz      short loc_180049E99
0x180049e8f  mov     cs:?gNlSiteTPCallbackEnvInitialized@@3HA, 0; int gNlSiteTPCallbackEnvInitialized
0x180049e99  lea     rcx, ?gNlSiteBackgroundLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180049ea0  call    cs:__imp_ReleaseSRWLockExclusive
0x180049ea7  nop     dword ptr [rax+rax+00h]
0x180049eac  mov     rcx, cs:?ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent@@3PEAXEA; hObject
0x180049eb3  test    rcx, rcx
0x180049eb6  jz      short loc_180049ECF
0x180049eb8  call    cs:__imp_CloseHandle
0x180049ebf  nop     dword ptr [rax+rax+00h]
0x180049ec4  mov     cs:?ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent@@3PEAXEA, 0; void * ghNlInitialSitesAndSubnetsLoadCompletedWaitEvent
0x180049ecf  mov     rcx, cs:?gpNlSitesAndSubnetsCache@@3PEAVCNlSitesAndSubnetsCache@@EA; this
0x180049ed6  mov     cs:?gfNlInitialSitesAndSubnetsLoadCompleted@@3HA, 0; int gfNlInitialSitesAndSubnetsLoadCompleted
0x180049ee0  test    rcx, rcx
0x180049ee3  jz      short loc_180049EF5
0x180049ee5  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x180049eea  mov     cs:?gpNlSitesAndSubnetsCache@@3PEAVCNlSitesAndSubnetsCache@@EA, 0; CNlSitesAndSubnetsCache * gpNlSitesAndSubnetsCache
0x180049ef5  mov     rcx, cs:?gpNlGlobalSiteNameCache@@3PEAVCNlGlobalSiteNameCache@@EA; this
0x180049efc  test    rcx, rcx
0x180049eff  jz      short loc_180049F11
0x180049f01  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x180049f06  mov     cs:?gpNlGlobalSiteNameCache@@3PEAVCNlGlobalSiteNameCache@@EA, 0; CNlGlobalSiteNameCache * gpNlGlobalSiteNameCache
0x180049f11  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f18  test    byte ptr [rcx+1Ch], 20h
0x180049f1c  jz      loc_180049FA6
0x180049f22  cmp     byte ptr [rcx+19h], 4
0x180049f26  jb      short loc_180049F85
0x180049f28  mov     eax, cs:?s_ObjectCount@CNlSitesAndSubnetsCache@@0KA; ulong CNlSitesAndSubnetsCache::s_ObjectCount
0x180049f2e  mov     r9d, cs:?NlSiteEntryCount@@3KA; ulong NlSiteEntryCount
0x180049f35  mov     rcx, [rcx+10h]
0x180049f39  mov     [rsp+68h+var_18], eax
0x180049f3d  mov     eax, cs:?s_ObjectCount@CNlSubnetTable@@0KA; ulong CNlSubnetTable::s_ObjectCount
0x180049f43  mov     [rsp+68h+var_20], eax
0x180049f47  mov     eax, cs:?s_ObjectCount@CNlSiteTable@@0KA; ulong CNlSiteTable::s_ObjectCount
0x180049f4d  mov     [rsp+68h+var_28], eax
0x180049f51  mov     eax, cs:?s_ObjectCount@CNlNextClosestSiteInfo@@0KA; ulong CNlNextClosestSiteInfo::s_ObjectCount
0x180049f57  mov     [rsp+68h+var_30], eax
0x180049f5b  mov     eax, cs:?s_ObjectCount@CNlIsmSiteNameIndexCache@@0KA; ulong CNlIsmSiteNameIndexCache::s_ObjectCount
0x180049f61  mov     [rsp+68h+var_38], eax
0x180049f65  mov     eax, cs:?s_ObjectCount@CNlGlobalSiteNameCache@@0KA; ulong CNlGlobalSiteNameCache::s_ObjectCount
0x180049f6b  mov     [rsp+68h+var_40], eax
0x180049f6f  mov     eax, cs:?NlSubnetCount@@3KA; ulong NlSubnetCount
0x180049f75  mov     [rsp+68h+var_48], eax
0x180049f79  call    WPP_SF_dddddddd
0x180049f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f85  test    byte ptr [rcx+1Ch], 20h
0x180049f89  jz      short loc_180049FA6
0x180049f8b  cmp     byte ptr [rcx+19h], 4
0x180049f8f  jb      short loc_180049FA6
0x180049f91  mov     rcx, [rcx+10h]
0x180049f95  lea     r8, WPP_3a1a29a145c231fea9997a63a013ec64_Traceguids
0x180049f9c  mov     edx, 94h
0x180049fa1  call    WPP_SF_
0x180049fa6  add     rsp, 68h
0x180049faa  retn
```
