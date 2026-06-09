# CmsVolume::~CmsVolume(void)

- ea: `0x14011a204`
- end: `0x14011a7b4`
- name: `??1CmsVolume@@MEAA@XZ`
- size: `1456`
- prototype: `void __fastcall(CmsVolume *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140117c70`

## callees

- `0x14006f5c0`
- `0x140072970`
- `0x1400752b0`
- `0x14007dcf4`
- `0x14008ce80`
- `0x1400c90d4`
- `0x1400cd64c`
- `0x1400ce7c0`
- `0x140110fe8`
- `0x140117af8`
- `0x140117b18`
- `0x140117b38`
- `0x140117b98`
- `0x14011a090`
- `0x14011a0c0`
- `0x14011a190`
- `0x14011a204`
- `0x14011a7bc`
- `0x14011a7e8`
- `0x14011a898`
- `0x14011a8c0`
- `0x14011a8e8`
- `0x14011a910`
- `0x14011a93c`
- `0x14011a9a0`
- `0x14011a9c8`
- `0x14011a9f8`
- `0x14011aa20`

## import_xrefs

- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a689`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a69c`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a6c7`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a6da`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a778`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a78b`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a689`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a69c`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a6c7`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a6da`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a778`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011a78b`
- `ntoskrnl!ExDeleteFastResource` at `0x14011a49a`
- `ntoskrnl!ExDeleteFastResource` at `0x14011a5fe`
- `ntoskrnl!ExDeleteFastResource` at `0x14011a66d`
- `ntoskrnl!ExDeleteFastResource` at `0x14011a49a`
- `ntoskrnl!ExDeleteFastResource` at `0x14011a5fe`
- `ntoskrnl!ExDeleteFastResource` at `0x14011a66d`

## pseudocode

```c
void __fastcall CmsVolume::~CmsVolume(CmsVolume *this, struct CmsTransactionCore *a2)
{
  bool v2; // zf
  void *v4; // rdi
  void *v5; // rcx
  CmsBlockRefcount *v6; // rcx
  CmsVolumeAnalyzer *v7; // rcx
  void *v8; // rcx
  CmsIntegrityState *v9; // rcx
  CmsSchemaTable *v10; // rcx
  CmsRangeMap *v11; // rcx
  CmsRangeMap *v12; // rcx
  void **v13; // rax
  void *v14; // rcx
  MsAllocator::RangeArrayStrategy::State *v15; // rcx
  MsAllocator::RangeArrayStrategy::State *v16; // rcx
  MsAllocator::RangeArrayStrategy::State *v17; // rcx
  __int64 v18; // rax
  void *v19; // rdi
  void *v20; // rcx
  void *v21; // rcx
  MsAllocator::RangeArrayStrategy::State *v22; // rcx
  void *v23; // rcx
  MsAllocator::SmrStrategy::State *v24; // rcx
  unsigned int i; // esi
  struct CmsTransactionCore *v26; // rdx
  struct SmsCheckpointState *CheckpointState; // rdi
  CmsContainerRangeMap *v28; // rcx
  CmsContainerRangeMap *v29; // rcx
  CmsContainerRangeMap *v30; // rcx
  CmsContainerRangeMap *v31; // rcx
  char *v32; // rsi
  void *v33; // rcx
  void *v34; // rcx
  CmsRangeMap *v35; // rcx
  CmsRangeMap *v36; // rcx
  CmsRangeMap *v37; // rcx
  CmsRangeMap *v38; // rcx
  CmsRangeMap *v39; // rcx
  CmsRangeMap *v40; // rcx
  void *v41; // rcx
  CmsCachedRuns *v42; // rcx
  char *v43; // rdi
  void *v44; // rcx
  void *v45; // rdi

  v2 = (*((_DWORD *)this + 865) & 0x10000) == 0;
  *(_QWORD *)this = &CmsVolume::`vftable';
  if ( v2 )
  {
    v4 = (void *)*((_QWORD *)this + 289);
    if ( v4 )
    {
      CmsThinProvisioning::~CmsThinProvisioning(*((CmsThinProvisioning **)this + 289));
      operator delete(v4);
      *((_QWORD *)this + 289) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 426);
    if ( v5 )
    {
      operator delete(v5);
      *((_QWORD *)this + 426) = 0;
    }
    v6 = (CmsBlockRefcount *)*((_QWORD *)this + 421);
    if ( v6 )
    {
      CmsBlockRefcount::`scalar deleting destructor'(v6, (unsigned int)a2);
      *((_QWORD *)this + 421) = 0;
    }
    v7 = (CmsVolumeAnalyzer *)*((_QWORD *)this + 419);
    if ( v7 )
    {
      CmsVolumeAnalyzer::`scalar deleting destructor'(v7, (unsigned int)a2);
      *((_QWORD *)this + 419) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 417);
    if ( v8 )
    {
      CmsVolumeContainer::`scalar deleting destructor'(v8, (unsigned int)a2);
      *((_QWORD *)this + 417) = 0;
    }
    v9 = (CmsIntegrityState *)*((_QWORD *)this + 418);
    if ( v9 )
    {
      CmsIntegrityState::`scalar deleting destructor'(v9, (unsigned int)a2);
      *((_QWORD *)this + 418) = 0;
    }
    v10 = (CmsSchemaTable *)*((_QWORD *)this + 431);
    if ( v10 )
    {
      CmsSchemaTable::`scalar deleting destructor'(v10, (unsigned int)a2);
      *((_QWORD *)this + 431) = 0;
    }
    v11 = (CmsRangeMap *)*((_QWORD *)this + 290);
    if ( v11 )
    {
      if ( *((_QWORD *)v11 + 3) )
        CmsRangeMap::DeleteAll(v11, a2);
      v12 = (CmsRangeMap *)*((_QWORD *)this + 290);
      if ( v12 )
        CmsRangeMap::`scalar deleting destructor'(v12, (unsigned int)a2);
      *((_QWORD *)this + 290) = 0;
    }
    v13 = (void **)*((_QWORD *)this + 335);
    if ( v13 )
    {
      if ( *v13 )
      {
        operator delete(*v13);
        **((_QWORD **)this + 335) = 0;
      }
      v14 = *(void **)(*((_QWORD *)this + 335) + 8LL);
      if ( v14 )
      {
        operator delete(v14);
        *(_QWORD *)(*((_QWORD *)this + 335) + 8LL) = 0;
      }
      v15 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 335) + 16LL);
      if ( v15 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v15, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 335) + 16LL) = 0;
      }
      v16 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 335) + 24LL);
      if ( v16 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v16, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 335) + 24LL) = 0;
      }
      v17 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 335) + 32LL);
      if ( v17 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v17, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 335) + 32LL) = 0;
      }
      v18 = *((_QWORD *)this + 335);
      v19 = *(void **)(v18 + 40);
      if ( v19 )
      {
        MsAllocator::RemoteZonesShardingStrategy::State::~State(*(MsAllocator::RemoteZonesShardingStrategy::State **)(v18 + 40));
        operator delete(v19);
        *(_QWORD *)(*((_QWORD *)this + 335) + 40LL) = 0;
      }
      v20 = *(void **)(*((_QWORD *)this + 335) + 80LL);
      if ( v20 )
      {
        operator delete(v20);
        *(_QWORD *)(*((_QWORD *)this + 335) + 80LL) = 0;
      }
      v21 = *(void **)(*((_QWORD *)this + 335) + 96LL);
      if ( v21 )
      {
        operator delete(v21);
        *(_QWORD *)(*((_QWORD *)this + 335) + 96LL) = 0;
      }
      v22 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 335) + 48LL);
      if ( v22 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v22, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 335) + 48LL) = 0;
      }
      v23 = *(void **)(*((_QWORD *)this + 335) + 64LL);
      if ( v23 )
      {
        operator delete(v23);
        *(_QWORD *)(*((_QWORD *)this + 335) + 64LL) = 0;
      }
      v24 = *(MsAllocator::SmrStrategy::State **)(*((_QWORD *)this + 335) + 72LL);
      if ( v24 )
      {
        MsAllocator::SmrStrategy::State::`scalar deleting destructor'(v24, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 335) + 72LL) = 0;
      }
      operator delete(*((void **)this + 335));
      *((_QWORD *)this + 335) = 0;
    }
    ExDeleteFastResource((char *)this + 1224);
    for ( i = 0; i < 5; ++i )
    {
      CheckpointState = CmsVolume::GetCheckpointState(this, i);
      if ( *(_QWORD *)CheckpointState )
      {
        CmsContainerRangeMap::DeleteAll(*(CmsContainerRangeMap **)CheckpointState, 0);
        if ( *(_QWORD *)CheckpointState )
          CmsContainerRangeMap::`scalar deleting destructor'(
            *(CmsContainerRangeMap **)CheckpointState,
            (unsigned int)v26);
        *(_QWORD *)CheckpointState = 0;
      }
      v28 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
      if ( v28 )
      {
        CmsContainerRangeMap::DeleteAll(v28, 0);
        v29 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
        if ( v29 )
          CmsContainerRangeMap::`scalar deleting destructor'(v29, (unsigned int)v26);
        *((_QWORD *)CheckpointState + 1) = 0;
      }
      v30 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
      if ( v30 )
      {
        CmsContainerRangeMap::DeleteAll(v30, 0);
        v31 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
        if ( v31 )
          CmsContainerRangeMap::`scalar deleting destructor'(v31, (unsigned int)v26);
        *((_QWORD *)CheckpointState + 2) = 0;
      }
    }
    v32 = (char *)this + 1712;
    v33 = (void *)*((_QWORD *)this + 214);
    *((_QWORD *)this + 214) = 0;
    if ( v33 )
      operator delete(v33);
    v34 = (void *)*((_QWORD *)this + 273);
    if ( v34 )
      operator delete(v34);
    if ( *((_QWORD *)this + 70) )
      MspCleanupIoBatchLookaside(this);
    v35 = (CmsRangeMap *)*((_QWORD *)this + 499);
    if ( v35 )
    {
      CmsRangeMap::DeleteAll(v35, v26);
      v36 = (CmsRangeMap *)*((_QWORD *)this + 499);
      if ( v36 )
        CmsRangeMap::`scalar deleting destructor'(v36, (unsigned int)v26);
    }
    v37 = (CmsRangeMap *)*((_QWORD *)this + 500);
    if ( v37 )
    {
      CmsRangeMap::DeleteAll(v37, v26);
      v38 = (CmsRangeMap *)*((_QWORD *)this + 500);
      if ( v38 )
        CmsRangeMap::`scalar deleting destructor'(v38, (unsigned int)v26);
      *((_QWORD *)this + 500) = 0;
    }
    v39 = (CmsRangeMap *)*((_QWORD *)this + 503);
    if ( v39 )
    {
      CmsRangeMap::DeleteAll(v39, v26);
      v40 = (CmsRangeMap *)*((_QWORD *)this + 503);
      if ( v40 )
        CmsRangeMap::`scalar deleting destructor'(v40, (unsigned int)v26);
    }
    v41 = (void *)*((_QWORD *)this + 505);
    if ( v41 )
      operator delete(v41);
    v42 = (CmsCachedRuns *)*((_QWORD *)this + 359);
    if ( v42 )
    {
      CmsCachedRuns::`scalar deleting destructor'(v42, (unsigned int)v26);
      *((_QWORD *)this + 359) = 0;
    }
    v43 = (char *)*((_QWORD *)this + 434);
    if ( v43 )
    {
      ExDeleteFastResource(v43 + 24);
      operator delete(v43);
      *((_QWORD *)this + 434) = 0;
    }
    v44 = (void *)*((_QWORD *)this + 437);
    if ( v44 != qword_140267190 )
    {
      operator delete(v44);
      *((_QWORD *)this + 437) = 0;
    }
    v45 = (void *)*((_QWORD *)this + 410);
    if ( v45 )
    {
      CmsAllocationZones::~CmsAllocationZones(*((CmsAllocationZones **)this + 410));
      operator delete(v45);
    }
    *((_QWORD *)this + 416) = 0;
    *((_QWORD *)this + 414) = 0;
    *((_QWORD *)this + 415) = 0;
    ExDeleteFastResource((char *)this + 3504);
  }
  else
  {
    v32 = (char *)this + 1712;
  }
  ExCleanupAutoExpandPushLock((char *)this + 4056);
  ExCleanupAutoExpandPushLock((char *)this + 3960);
  utl::unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>::~unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>((char *)this + 3680);
  SmsChecksumObjects::~SmsChecksumObjects((CmsVolume *)((char *)this + 3608));
  ExCleanupAutoExpandPushLock((char *)this + 3432);
  ExCleanupAutoExpandPushLock((char *)this + 3416);
  `vector destructor iterator'(
    (char *)this + 3288,
    8u,
    3u,
    utl::unique_ptr<CmsAllocator,utl::default_delete<CmsAllocator>>::~unique_ptr<CmsAllocator,utl::default_delete<CmsAllocator>>);
  CmsVolume::SmsTrim::~SmsTrim((CmsVolume *)((char *)this + 2200));
  utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit((char *)this + 2152);
  `vector destructor iterator'(
    (char *)this + 2040,
    0x18u,
    3u,
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::~vector<enum utl::byte,utl::allocator<enum utl::byte>>);
  __1__unique_ptr_V__CmsChecksumBase_V__CmsSimpleChecksum__MP6AKPEBX_KK_Z1_Crc32C_ClMulIntrinsic__YAK01K_Z__U__PARITY_ENCODER_VFAST_FINITE_FIELD__K____U__default_delete_V__CmsChecksumBase_V__CmsSimpleChecksum__MP6AKPEBX_KK_Z1_Crc32C_ClMulIntrinsic__YAK01K_Z__U__PARITY_ENCODER_VFAST_FINITE_FIELD__K_____utl___utl__QEAA_XZ(v32);
  `vector destructor iterator'(
    (char *)this + 1328,
    0xB0u,
    2u,
    (void (*)(void *))SmsCheckpointContext::~SmsCheckpointContext);
  utl::unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>::~unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>((char *)this + 1208);
  utl::unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>::~unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>((char *)this + 1200);
  ExCleanupAutoExpandPushLock((char *)this + 432);
  ExCleanupAutoExpandPushLock((char *)this + 328);
  CmsVolume::_unnamed_type_ReservedPools_::__unnamed_type_ReservedPools_((CmsVolume *)((char *)this + 96));
  *(_QWORD *)this = &CmsReferenced::`vftable';
}

```

## disassembly

```asm
0x14011a204  push    rbx
0x14011a206  push    rbp
0x14011a207  push    rsi
0x14011a208  push    rdi
0x14011a209  sub     rsp, 28h
0x14011a20d  test    dword ptr [rcx+0D84h], 10000h
0x14011a217  lea     rax, ??_7CmsVolume@@6B@; const CmsVolume::`vftable'
0x14011a21e  mov     [rcx], rax
0x14011a221  mov     rbx, rcx
0x14011a224  jnz     loc_14011A67B
0x14011a22a  mov     rdi, [rcx+908h]
0x14011a231  xor     ebp, ebp
0x14011a233  test    rdi, rdi
0x14011a236  jz      short loc_14011A24F
0x14011a238  mov     rcx, rdi; this
0x14011a23b  call    ??1CmsThinProvisioning@@QEAA@XZ; CmsThinProvisioning::~CmsThinProvisioning(void)
0x14011a240  mov     rcx, rdi; void *
0x14011a243  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a248  mov     [rbx+908h], rbp
0x14011a24f  mov     rcx, [rbx+0D50h]; void *
0x14011a256  test    rcx, rcx
0x14011a259  jz      short loc_14011A267
0x14011a25b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a260  mov     [rbx+0D50h], rbp
0x14011a267  mov     rcx, [rbx+0D28h]; this
0x14011a26e  test    rcx, rcx
0x14011a271  jz      short loc_14011A27F
0x14011a273  call    ??_GCmsBlockRefcount@@QEAAPEAXI@Z; CmsBlockRefcount::`scalar deleting destructor'(uint)
0x14011a278  mov     [rbx+0D28h], rbp
0x14011a27f  mov     rcx, [rbx+0D18h]; this
0x14011a286  test    rcx, rcx
0x14011a289  jz      short loc_14011A297
0x14011a28b  call    ??_GCmsVolumeAnalyzer@@QEAAPEAXI@Z; CmsVolumeAnalyzer::`scalar deleting destructor'(uint)
0x14011a290  mov     [rbx+0D18h], rbp
0x14011a297  mov     rcx, [rbx+0D08h]; P
0x14011a29e  test    rcx, rcx
0x14011a2a1  jz      short loc_14011A2AF
0x14011a2a3  call    ??_GCmsVolumeContainer@@QEAAPEAXI@Z; CmsVolumeContainer::`scalar deleting destructor'(uint)
0x14011a2a8  mov     [rbx+0D08h], rbp
0x14011a2af  mov     rcx, [rbx+0D10h]; this
0x14011a2b6  test    rcx, rcx
0x14011a2b9  jz      short loc_14011A2C7
0x14011a2bb  call    ??_GCmsIntegrityState@@QEAAPEAXI@Z; CmsIntegrityState::`scalar deleting destructor'(uint)
0x14011a2c0  mov     [rbx+0D10h], rbp
0x14011a2c7  mov     rcx, [rbx+0D78h]; this
0x14011a2ce  test    rcx, rcx
0x14011a2d1  jz      short loc_14011A2DF
0x14011a2d3  call    ??_GCmsSchemaTable@@QEAAPEAXI@Z; CmsSchemaTable::`scalar deleting destructor'(uint)
0x14011a2d8  mov     [rbx+0D78h], rbp
0x14011a2df  mov     rcx, [rbx+910h]; this
0x14011a2e6  test    rcx, rcx
0x14011a2e9  jz      short loc_14011A30E
0x14011a2eb  cmp     [rcx+18h], rbp
0x14011a2ef  jz      short loc_14011A2F6
0x14011a2f1  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011a2f6  mov     rcx, [rbx+910h]; this
0x14011a2fd  test    rcx, rcx
0x14011a300  jz      short loc_14011A307
0x14011a302  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011a307  mov     [rbx+910h], rbp
0x14011a30e  mov     rax, [rbx+0A78h]
0x14011a315  test    rax, rax
0x14011a318  jz      loc_14011A493
0x14011a31e  mov     rcx, [rax]; void *
0x14011a321  test    rcx, rcx
0x14011a324  jz      short loc_14011A335
0x14011a326  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a32b  mov     rax, [rbx+0A78h]
0x14011a332  mov     [rax], rbp
0x14011a335  mov     rax, [rbx+0A78h]
0x14011a33c  mov     rcx, [rax+8]; void *
0x14011a340  test    rcx, rcx
0x14011a343  jz      short loc_14011A355
0x14011a345  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a34a  mov     rax, [rbx+0A78h]
0x14011a351  mov     [rax+8], rbp
0x14011a355  mov     rax, [rbx+0A78h]
0x14011a35c  mov     rcx, [rax+10h]; this
0x14011a360  test    rcx, rcx
0x14011a363  jz      short loc_14011A375
0x14011a365  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011a36a  mov     rax, [rbx+0A78h]
0x14011a371  mov     [rax+10h], rbp
0x14011a375  mov     rax, [rbx+0A78h]
0x14011a37c  mov     rcx, [rax+18h]; this
0x14011a380  test    rcx, rcx
0x14011a383  jz      short loc_14011A395
0x14011a385  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011a38a  mov     rax, [rbx+0A78h]
0x14011a391  mov     [rax+18h], rbp
0x14011a395  mov     rax, [rbx+0A78h]
0x14011a39c  mov     rcx, [rax+20h]; this
0x14011a3a0  test    rcx, rcx
0x14011a3a3  jz      short loc_14011A3B5
0x14011a3a5  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011a3aa  mov     rax, [rbx+0A78h]
0x14011a3b1  mov     [rax+20h], rbp
0x14011a3b5  mov     rax, [rbx+0A78h]
0x14011a3bc  mov     rdi, [rax+28h]
0x14011a3c0  test    rdi, rdi
0x14011a3c3  jz      short loc_14011A3E0
0x14011a3c5  mov     rcx, rdi; this
0x14011a3c8  call    ??1State@RemoteZonesShardingStrategy@MsAllocator@@QEAA@XZ; MsAllocator::RemoteZonesShardingStrategy::State::~State(void)
0x14011a3cd  mov     rcx, rdi; void *
0x14011a3d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a3d5  mov     rax, [rbx+0A78h]
0x14011a3dc  mov     [rax+28h], rbp
0x14011a3e0  mov     rax, [rbx+0A78h]
0x14011a3e7  mov     rcx, [rax+50h]; void *
0x14011a3eb  test    rcx, rcx
0x14011a3ee  jz      short loc_14011A400
0x14011a3f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a3f5  mov     rax, [rbx+0A78h]
0x14011a3fc  mov     [rax+50h], rbp
0x14011a400  mov     rax, [rbx+0A78h]
0x14011a407  mov     rcx, [rax+60h]; void *
0x14011a40b  test    rcx, rcx
0x14011a40e  jz      short loc_14011A420
0x14011a410  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a415  mov     rax, [rbx+0A78h]
0x14011a41c  mov     [rax+60h], rbp
0x14011a420  mov     rax, [rbx+0A78h]
0x14011a427  mov     rcx, [rax+30h]; this
0x14011a42b  test    rcx, rcx
0x14011a42e  jz      short loc_14011A440
0x14011a430  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011a435  mov     rax, [rbx+0A78h]
0x14011a43c  mov     [rax+30h], rbp
0x14011a440  mov     rax, [rbx+0A78h]
0x14011a447  mov     rcx, [rax+40h]; void *
0x14011a44b  test    rcx, rcx
0x14011a44e  jz      short loc_14011A460
0x14011a450  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a455  mov     rax, [rbx+0A78h]
0x14011a45c  mov     [rax+40h], rbp
0x14011a460  mov     rax, [rbx+0A78h]
0x14011a467  mov     rcx, [rax+48h]; this
0x14011a46b  test    rcx, rcx
0x14011a46e  jz      short loc_14011A480
0x14011a470  call    ??_GState@SmrStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::SmrStrategy::State::`scalar deleting destructor'(uint)
0x14011a475  mov     rax, [rbx+0A78h]
0x14011a47c  mov     [rax+48h], rbp
0x14011a480  mov     rcx, [rbx+0A78h]; void *
0x14011a487  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a48c  mov     [rbx+0A78h], rbp
0x14011a493  lea     rcx, [rbx+4C8h]
0x14011a49a  call    cs:__imp_ExDeleteFastResource
0x14011a4a1  nop     dword ptr [rax+rax+00h]
0x14011a4a6  mov     esi, ebp
0x14011a4a8  mov     edx, esi; unsigned int
0x14011a4aa  mov     rcx, rbx; this
0x14011a4ad  call    ?GetCheckpointState@CmsVolume@@AEAAPEAUSmsCheckpointState@@K@Z; CmsVolume::GetCheckpointState(ulong)
0x14011a4b2  mov     rdi, rax
0x14011a4b5  mov     rcx, [rax]; this
0x14011a4b8  test    rcx, rcx
0x14011a4bb  jz      short loc_14011A4D4
0x14011a4bd  xor     edx, edx; unsigned __int8
0x14011a4bf  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14011a4c4  mov     rcx, [rdi]; this
0x14011a4c7  test    rcx, rcx
0x14011a4ca  jz      short loc_14011A4D1
0x14011a4cc  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14011a4d1  mov     [rdi], rbp
0x14011a4d4  mov     rcx, [rdi+8]; this
0x14011a4d8  test    rcx, rcx
0x14011a4db  jz      short loc_14011A4F6
0x14011a4dd  xor     edx, edx; unsigned __int8
0x14011a4df  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14011a4e4  mov     rcx, [rdi+8]; this
0x14011a4e8  test    rcx, rcx
0x14011a4eb  jz      short loc_14011A4F2
0x14011a4ed  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14011a4f2  mov     [rdi+8], rbp
0x14011a4f6  mov     rcx, [rdi+10h]; this
0x14011a4fa  test    rcx, rcx
0x14011a4fd  jz      short loc_14011A518
0x14011a4ff  xor     edx, edx; unsigned __int8
0x14011a501  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14011a506  mov     rcx, [rdi+10h]; this
0x14011a50a  test    rcx, rcx
0x14011a50d  jz      short loc_14011A514
0x14011a50f  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14011a514  mov     [rdi+10h], rbp
0x14011a518  inc     esi
0x14011a51a  cmp     esi, 5
0x14011a51d  jb      short loc_14011A4A8
0x14011a51f  lea     rsi, [rbx+6B0h]
0x14011a526  mov     rcx, [rsi]; void *
0x14011a529  mov     [rsi], rbp
0x14011a52c  test    rcx, rcx
0x14011a52f  jz      short loc_14011A536
0x14011a531  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a536  mov     rcx, [rbx+888h]; void *
0x14011a53d  test    rcx, rcx
0x14011a540  jz      short loc_14011A547
0x14011a542  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a547  cmp     [rbx+230h], rbp
0x14011a54e  jz      short loc_14011A558
0x14011a550  mov     rcx, rbx; struct CmsVolume *
0x14011a553  call    ?MspCleanupIoBatchLookaside@@YAXPEAVCmsVolume@@@Z; MspCleanupIoBatchLookaside(CmsVolume *)
0x14011a558  mov     rcx, [rbx+0F98h]; this
0x14011a55f  test    rcx, rcx
0x14011a562  jz      short loc_14011A57A
0x14011a564  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011a569  mov     rcx, [rbx+0F98h]; this
0x14011a570  test    rcx, rcx
0x14011a573  jz      short loc_14011A57A
0x14011a575  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011a57a  mov     rcx, [rbx+0FA0h]; this
0x14011a581  test    rcx, rcx
0x14011a584  jz      short loc_14011A5A3
0x14011a586  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011a58b  mov     rcx, [rbx+0FA0h]; this
0x14011a592  test    rcx, rcx
0x14011a595  jz      short loc_14011A59C
0x14011a597  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011a59c  mov     [rbx+0FA0h], rbp
0x14011a5a3  mov     rcx, [rbx+0FB8h]; this
0x14011a5aa  test    rcx, rcx
0x14011a5ad  jz      short loc_14011A5C5
0x14011a5af  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011a5b4  mov     rcx, [rbx+0FB8h]; this
0x14011a5bb  test    rcx, rcx
0x14011a5be  jz      short loc_14011A5C5
0x14011a5c0  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011a5c5  mov     rcx, [rbx+0FC8h]; void *
0x14011a5cc  test    rcx, rcx
0x14011a5cf  jz      short loc_14011A5D6
0x14011a5d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a5d6  mov     rcx, [rbx+0B38h]; this
0x14011a5dd  test    rcx, rcx
0x14011a5e0  jz      short loc_14011A5EE
0x14011a5e2  call    ??_GCmsCachedRuns@@QEAAPEAXI@Z; CmsCachedRuns::`scalar deleting destructor'(uint)
0x14011a5e7  mov     [rbx+0B38h], rbp
0x14011a5ee  mov     rdi, [rbx+0D90h]
0x14011a5f5  test    rdi, rdi
0x14011a5f8  jz      short loc_14011A619
0x14011a5fa  lea     rcx, [rdi+18h]
0x14011a5fe  call    cs:__imp_ExDeleteFastResource
0x14011a605  nop     dword ptr [rax+rax+00h]
0x14011a60a  mov     rcx, rdi; void *
0x14011a60d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a612  mov     [rbx+0D90h], rbp
0x14011a619  mov     rcx, [rbx+0DA8h]; void *
0x14011a620  cmp     rcx, cs:qword_140267190
0x14011a627  jz      short loc_14011A635
0x14011a629  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a62e  mov     [rbx+0DA8h], rbp
0x14011a635  mov     rdi, [rbx+0CD0h]
0x14011a63c  test    rdi, rdi
0x14011a63f  jz      short loc_14011A651
0x14011a641  mov     rcx, rdi; this
0x14011a644  call    ??1CmsAllocationZones@@QEAA@XZ; CmsAllocationZones::~CmsAllocationZones(void)
0x14011a649  mov     rcx, rdi; void *
0x14011a64c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011a651  lea     rcx, [rbx+0DB0h]
0x14011a658  mov     [rbx+0D00h], rbp
0x14011a65f  mov     [rbx+0CF0h], rbp
0x14011a666  mov     [rbx+0CF8h], rbp
0x14011a66d  call    cs:__imp_ExDeleteFastResource
0x14011a674  nop     dword ptr [rax+rax+00h]
0x14011a679  jmp     short loc_14011A682
0x14011a67b  lea     rsi, [rcx+6B0h]
0x14011a682  lea     rcx, [rbx+0FD8h]
0x14011a689  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011a690  nop     dword ptr [rax+rax+00h]
0x14011a695  lea     rcx, [rbx+0F78h]
0x14011a69c  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011a6a3  nop     dword ptr [rax+rax+00h]
0x14011a6a8  lea     rcx, [rbx+0E60h]
0x14011a6af  call    ??1?$unique_ptr@VCmsHmac@@U?$default_delete@VCmsHmac@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>::~unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>(void)
0x14011a6b4  lea     rcx, [rbx+0E18h]; this
0x14011a6bb  call    ??1SmsChecksumObjects@@QEAA@XZ; SmsChecksumObjects::~SmsChecksumObjects(void)
0x14011a6c0  lea     rcx, [rbx+0D68h]
0x14011a6c7  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011a6ce  nop     dword ptr [rax+rax+00h]
0x14011a6d3  lea     rcx, [rbx+0D58h]
0x14011a6da  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011a6e1  nop     dword ptr [rax+rax+00h]
0x14011a6e6  mov     edi, 3
0x14011a6eb  lea     rcx, [rbx+0CD8h]; void *
0x14011a6f2  lea     r9, ??1?$unique_ptr@VCmsAllocator@@U?$default_delete@VCmsAllocator@@@utl@@@utl@@QEAA@XZ; void (*)(void *)
0x14011a6f9  mov     r8d, edi; unsigned __int64
0x14011a6fc  lea     edx, [rdi+5]; unsigned __int64
0x14011a6ff  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14011a704  lea     rcx, [rbx+898h]; this
0x14011a70b  call    ??1SmsTrim@CmsVolume@@QEAA@XZ; CmsVolume::SmsTrim::~SmsTrim(void)
0x14011a710  lea     rcx, [rbx+868h]
0x14011a717  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x14011a71c  lea     rcx, [rbx+7F8h]; void *
0x14011a723  mov     r8d, edi; unsigned __int64
0x14011a726  lea     r9, ??1?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@QEAA@XZ; void (*)(void *)
0x14011a72d  lea     edx, [rdi+15h]; unsigned __int64
0x14011a730  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14011a735  mov     rcx, rsi; void *
0x14011a738  call    ??1?$unique_ptr@V?$CmsChecksumBase@V?$CmsSimpleChecksum@$MP6AKPEBX_KK@Z1?Crc32C_ClMulIntrinsic@@YAK01K@Z@@U?$PARITY_ENCODER@VFAST_FINITE_FIELD@@K@@@@U?$default_delete@V?$CmsChecksumBase@V?$CmsSimpleChecksum@$MP6AKPEBX_KK@Z1?Crc32C_ClMulIntrinsic@@YAK01K@Z@@U?$PARITY_ENCODER@VFAST_FINITE_FIELD@@K@@@@@utl@@@utl@@QEAA@XZ
0x14011a73d  lea     rcx, [rbx+530h]; void *
0x14011a744  mov     edx, 0B0h; unsigned __int64
0x14011a749  lea     r9, ??1SmsCheckpointContext@@QEAA@XZ; void (*)(void *)
0x14011a750  lea     r8d, [rdi-1]; unsigned __int64
  ... truncated ...
```
