# DsSamUninitializeCritSecs

- ea: `0x180400980`
- end: `0x180400b21`
- name: `DsSamUninitializeCritSecs`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800acb74`

## callees

- `0x180400980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400997`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1804009b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1804009cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1804009e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a03`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a54`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400aa5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400ac0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400adb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400af6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400997`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1804009b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1804009cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1804009e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a03`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a54`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400a8a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400aa5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400ac0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400adb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180400af6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180400b0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180400b0e`

## pseudocode

```c
void DsSamUninitializeCritSecs()
{
  if ( SampDsExpensiveGroupLock_initialized )
  {
    DeleteCriticalSection(&SampDsExpensiveGroupLock);
    SampDsExpensiveGroupLock_initialized = 0;
  }
  if ( SampBGQueueLock_initialized )
  {
    DeleteCriticalSection(&SampBGQueueLock);
    SampBGQueueLock_initialized = 0;
  }
  if ( SampReplicateQueueLock_initialized )
  {
    DeleteCriticalSection(&SampReplicateQueueLock);
    SampReplicateQueueLock_initialized = 0;
  }
  if ( SampDsGroupLock_initialized )
  {
    DeleteCriticalSection(&SampDsGroupLock);
    SampDsGroupLock_initialized = 0;
  }
  if ( SampAccountNameTableCriticalSection_initialized )
  {
    DeleteCriticalSection(&SampAccountNameTableCriticalSection);
    SampAccountNameTableCriticalSection_initialized = 0;
  }
  if ( SampSiteInfoLock_initialized )
  {
    DeleteCriticalSection(&SampSiteInfoLock);
    SampSiteInfoLock_initialized = 0;
  }
  if ( RidMgrCriticalSection_initialized )
  {
    DeleteCriticalSection(&RidMgrCriticalSection);
    RidMgrCriticalSection_initialized = 0;
  }
  if ( RidCacheCriticalSection_initialized )
  {
    DeleteCriticalSection(&RidCacheCriticalSection);
    RidCacheCriticalSection_initialized = 0;
  }
  if ( SampWKContainterTableLock_initialized )
  {
    DeleteCriticalSection(&SampWKContainterTableLock);
    SampWKContainterTableLock_initialized = 0;
  }
  if ( csCachedClaimConfig_initialized )
  {
    DeleteCriticalSection(&csCachedClaimConfig);
    csCachedClaimConfig_initialized = 0;
  }
  if ( csMappedGroupsOidList_initialized )
  {
    DeleteCriticalSection(&csMappedGroupsOidList);
    csMappedGroupsOidList_initialized = 0;
  }
  if ( csFineGrainedPasswordPolicyPresent_initialized )
  {
    DeleteCriticalSection(&csFineGrainedPasswordPolicyPresent);
    csFineGrainedPasswordPolicyPresent_initialized = 0;
  }
  if ( csAPSCache_initialized )
  {
    DeleteCriticalSection(&csAPSCache);
    csAPSCache_initialized = 0;
  }
  if ( gNtdsaKdcAcctChNotifLock_initialized )
  {
    DeleteCriticalSection(&gNtdsaKdcAcctChNotifLock);
    gNtdsaKdcAcctChNotifLock_initialized = 0;
  }
  if ( ghNtdsaKdcAcctChNotif )
  {
    CloseHandle(ghNtdsaKdcAcctChNotif);
    ghNtdsaKdcAcctChNotif = 0;
  }
}

```

## disassembly

```asm
0x180400980  push    rbx
0x180400982  sub     rsp, 20h
0x180400986  xor     ebx, ebx
0x180400988  cmp     cs:?SampDsExpensiveGroupLock_initialized@@3HA, ebx; int SampDsExpensiveGroupLock_initialized
0x18040098e  jz      short loc_1804009A3
0x180400990  lea     rcx, ?SampDsExpensiveGroupLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400997  call    cs:__imp_DeleteCriticalSection
0x18040099d  mov     cs:?SampDsExpensiveGroupLock_initialized@@3HA, ebx; int SampDsExpensiveGroupLock_initialized
0x1804009a3  cmp     cs:?SampBGQueueLock_initialized@@3HA, ebx; int SampBGQueueLock_initialized
0x1804009a9  jz      short loc_1804009BE
0x1804009ab  lea     rcx, ?SampBGQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1804009b2  call    cs:__imp_DeleteCriticalSection
0x1804009b8  mov     cs:?SampBGQueueLock_initialized@@3HA, ebx; int SampBGQueueLock_initialized
0x1804009be  cmp     cs:?SampReplicateQueueLock_initialized@@3HA, ebx; int SampReplicateQueueLock_initialized
0x1804009c4  jz      short loc_1804009D9
0x1804009c6  lea     rcx, ?SampReplicateQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1804009cd  call    cs:__imp_DeleteCriticalSection
0x1804009d3  mov     cs:?SampReplicateQueueLock_initialized@@3HA, ebx; int SampReplicateQueueLock_initialized
0x1804009d9  cmp     cs:?SampDsGroupLock_initialized@@3HA, ebx; int SampDsGroupLock_initialized
0x1804009df  jz      short loc_1804009F4
0x1804009e1  lea     rcx, ?SampDsGroupLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1804009e8  call    cs:__imp_DeleteCriticalSection
0x1804009ee  mov     cs:?SampDsGroupLock_initialized@@3HA, ebx; int SampDsGroupLock_initialized
0x1804009f4  cmp     cs:?SampAccountNameTableCriticalSection_initialized@@3HA, ebx; int SampAccountNameTableCriticalSection_initialized
0x1804009fa  jz      short loc_180400A0F
0x1804009fc  lea     rcx, ?SampAccountNameTableCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400a03  call    cs:__imp_DeleteCriticalSection
0x180400a09  mov     cs:?SampAccountNameTableCriticalSection_initialized@@3HA, ebx; int SampAccountNameTableCriticalSection_initialized
0x180400a0f  cmp     cs:?SampSiteInfoLock_initialized@@3HA, ebx; int SampSiteInfoLock_initialized
0x180400a15  jz      short loc_180400A2A
0x180400a17  lea     rcx, ?SampSiteInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400a1e  call    cs:__imp_DeleteCriticalSection
0x180400a24  mov     cs:?SampSiteInfoLock_initialized@@3HA, ebx; int SampSiteInfoLock_initialized
0x180400a2a  cmp     cs:?RidMgrCriticalSection_initialized@@3HA, ebx; int RidMgrCriticalSection_initialized
0x180400a30  jz      short loc_180400A45
0x180400a32  lea     rcx, RidMgrCriticalSection; lpCriticalSection
0x180400a39  call    cs:__imp_DeleteCriticalSection
0x180400a3f  mov     cs:?RidMgrCriticalSection_initialized@@3HA, ebx; int RidMgrCriticalSection_initialized
0x180400a45  cmp     cs:?RidCacheCriticalSection_initialized@@3HA, ebx; int RidCacheCriticalSection_initialized
0x180400a4b  jz      short loc_180400A60
0x180400a4d  lea     rcx, ?RidCacheCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400a54  call    cs:__imp_DeleteCriticalSection
0x180400a5a  mov     cs:?RidCacheCriticalSection_initialized@@3HA, ebx; int RidCacheCriticalSection_initialized
0x180400a60  cmp     cs:?SampWKContainterTableLock_initialized@@3HA, ebx; int SampWKContainterTableLock_initialized
0x180400a66  jz      short loc_180400A7B
0x180400a68  lea     rcx, ?SampWKContainterTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400a6f  call    cs:__imp_DeleteCriticalSection
0x180400a75  mov     cs:?SampWKContainterTableLock_initialized@@3HA, ebx; int SampWKContainterTableLock_initialized
0x180400a7b  cmp     cs:?csCachedClaimConfig_initialized@@3HA, ebx; int csCachedClaimConfig_initialized
0x180400a81  jz      short loc_180400A96
0x180400a83  lea     rcx, ?csCachedClaimConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400a8a  call    cs:__imp_DeleteCriticalSection
0x180400a90  mov     cs:?csCachedClaimConfig_initialized@@3HA, ebx; int csCachedClaimConfig_initialized
0x180400a96  cmp     cs:?csMappedGroupsOidList_initialized@@3HA, ebx; int csMappedGroupsOidList_initialized
0x180400a9c  jz      short loc_180400AB1
0x180400a9e  lea     rcx, ?csMappedGroupsOidList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400aa5  call    cs:__imp_DeleteCriticalSection
0x180400aab  mov     cs:?csMappedGroupsOidList_initialized@@3HA, ebx; int csMappedGroupsOidList_initialized
0x180400ab1  cmp     cs:?csFineGrainedPasswordPolicyPresent_initialized@@3HA, ebx; int csFineGrainedPasswordPolicyPresent_initialized
0x180400ab7  jz      short loc_180400ACC
0x180400ab9  lea     rcx, ?csFineGrainedPasswordPolicyPresent@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400ac0  call    cs:__imp_DeleteCriticalSection
0x180400ac6  mov     cs:?csFineGrainedPasswordPolicyPresent_initialized@@3HA, ebx; int csFineGrainedPasswordPolicyPresent_initialized
0x180400acc  cmp     cs:?csAPSCache_initialized@@3HA, ebx; int csAPSCache_initialized
0x180400ad2  jz      short loc_180400AE7
0x180400ad4  lea     rcx, ?csAPSCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400adb  call    cs:__imp_DeleteCriticalSection
0x180400ae1  mov     cs:?csAPSCache_initialized@@3HA, ebx; int csAPSCache_initialized
0x180400ae7  cmp     cs:?gNtdsaKdcAcctChNotifLock_initialized@@3HA, ebx; int gNtdsaKdcAcctChNotifLock_initialized
0x180400aed  jz      short loc_180400B02
0x180400aef  lea     rcx, ?gNtdsaKdcAcctChNotifLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180400af6  call    cs:__imp_DeleteCriticalSection
0x180400afc  mov     cs:?gNtdsaKdcAcctChNotifLock_initialized@@3HA, ebx; int gNtdsaKdcAcctChNotifLock_initialized
0x180400b02  mov     rcx, cs:?ghNtdsaKdcAcctChNotif@@3PEAXEA; hObject
0x180400b09  test    rcx, rcx
0x180400b0c  jz      short loc_180400B1B
0x180400b0e  call    cs:__imp_CloseHandle
0x180400b14  mov     cs:?ghNtdsaKdcAcctChNotif@@3PEAXEA, rbx; void * ghNtdsaKdcAcctChNotif
0x180400b1b  add     rsp, 20h
0x180400b1f  pop     rbx
0x180400b20  retn
```
