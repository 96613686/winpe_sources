# CmsVolume::~CmsVolume(void)

- ea: `0x1c0050544`
- end: `0x1c0050a8d`
- name: `??1CmsVolume@@MEAA@XZ`
- size: `1353`
- prototype: `void __fastcall(CmsVolume *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c004fb70`

## callees

- `0x1c002357c`
- `0x1c002d170`
- `0x1c0035848`
- `0x1c004fbb0`
- `0x1c004ff6c`
- `0x1c0050544`
- `0x1c0050a94`
- `0x1c0052050`
- `0x1c0052098`
- `0x1c0052374`
- `0x1c005239c`
- `0x1c0053290`
- `0x1c005332c`
- `0x1c0053430`
- `0x1c00537c0`
- `0x1c0053bf8`
- `0x1c0053c30`
- `0x1c00b5968`
- `0x1c00b59b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c00505f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c005067f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00506aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c005077c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00507ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00508a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00509b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00509f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0050a05`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087b47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087b6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087bb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087bc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087c01`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00505f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c005067f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00506aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c005077c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00507ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00508a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00509b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00509f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0050a05`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087b47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087b6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087bb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087bc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0087c01`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c00507e0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c0050881`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c0050a18`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c00507e0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c0050881`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c0050a18`
- `ntoskrnl!ExFreeAutoExpandPushLock` at `0x1c00508e5`
- `ntoskrnl!ExFreeAutoExpandPushLock` at `0x1c0050904`
- `ntoskrnl!ExFreeAutoExpandPushLock` at `0x1c0050974`
- `ntoskrnl!ExFreeAutoExpandPushLock` at `0x1c00508e5`
- `ntoskrnl!ExFreeAutoExpandPushLock` at `0x1c0050904`
- `ntoskrnl!ExFreeAutoExpandPushLock` at `0x1c0050974`

## pseudocode

```c
void __fastcall CmsVolume::~CmsVolume(CmsVolume *this, struct CmsTransactionCore *a2)
{
  bool v2; // zf
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rdi
  CmsReferenced *v11; // rcx
  CmsReferenced *v12; // rcx
  CmsReferenced *v13; // rcx
  CmsRangeMap *v14; // rcx
  PVOID *v15; // rcx
  CmsContainerRangeMap *v16; // rcx
  unsigned int i; // esi
  struct CmsTransactionCore *v18; // rdx
  struct _SmsCheckpointState *CheckpointState; // rdi
  CmsContainerRangeMap *v20; // rcx
  CmsContainerRangeMap *v21; // rcx
  CmsContainerRangeMap *v22; // rcx
  CmsContainerRangeMap *v23; // rcx
  unsigned int v24; // edi
  _QWORD *v25; // rsi
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  CmsRangeMap *v31; // rcx
  CmsRangeMap *v32; // rcx
  CmsRangeMap *v33; // rcx
  CmsRangeMap *v34; // rcx
  __int64 v35; // rcx
  void *v36; // rcx
  CmsReferenced *v37; // rcx
  void *v38; // rcx
  PVOID v39; // rcx
  _QWORD *v40; // rdi
  void *v41; // rcx
  _QWORD *v42; // rcx

  v2 = (*((_DWORD *)this + 779) & 0x10000) == 0;
  *(_QWORD *)this = &CmsVolume::`vftable';
  if ( v2 )
  {
    v4 = (void *)*((_QWORD *)this + 254);
    if ( v4 )
    {
      CmsThinProvisioning::`scalar deleting destructor'(v4, (unsigned int)a2);
      *((_QWORD *)this + 254) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 387);
    if ( v5 )
    {
      ExFreePoolWithTag(v5, 0);
      *((_QWORD *)this + 387) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 384);
    if ( v6 )
    {
      CmsBlockRefcount::`scalar deleting destructor'(v6, (unsigned int)a2);
      *((_QWORD *)this + 384) = 0;
    }
    v7 = (void *)*((_QWORD *)this + 383);
    if ( v7 )
    {
      CmsVolumeAnalyzer::`scalar deleting destructor'(v7, (unsigned int)a2);
      *((_QWORD *)this + 383) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 381);
    if ( v8 )
    {
      CmsVolumeContainer::`scalar deleting destructor'(v8, (unsigned int)a2);
      *((_QWORD *)this + 381) = 0;
    }
    v9 = (void *)*((_QWORD *)this + 382);
    if ( v9 )
    {
      CmsIntegrityState::`scalar deleting destructor'(v9, (unsigned int)a2);
      *((_QWORD *)this + 382) = 0;
    }
    v10 = (void *)*((_QWORD *)this + 388);
    if ( v10 )
    {
      CmsSchemaTable::~CmsSchemaTable(*((CmsSchemaTable **)this + 388));
      ExFreePoolWithTag(v10, 0);
      *((_QWORD *)this + 388) = 0;
    }
    v11 = (CmsReferenced *)*((_QWORD *)this + 380);
    if ( v11 )
    {
      CmsReferenced::Release(v11);
      *((_QWORD *)this + 380) = 0;
    }
    v12 = (CmsReferenced *)*((_QWORD *)this + 379);
    if ( v12 )
    {
      CmsReferenced::Release(v12);
      *((_QWORD *)this + 379) = 0;
    }
    v13 = (CmsReferenced *)*((_QWORD *)this + 378);
    if ( v13 )
    {
      CmsReferenced::Release(v13);
      *((_QWORD *)this + 378) = 0;
    }
    v14 = (CmsRangeMap *)*((_QWORD *)this + 255);
    if ( v14 )
    {
      if ( *((_QWORD *)v14 + 3) )
      {
        CmsRangeMap::DeleteAll(v14, a2);
        v14 = (CmsRangeMap *)*((_QWORD *)this + 255);
      }
      if ( v14 )
        CmsRangeMap::`scalar deleting destructor'(v14, (unsigned int)a2);
      *((_QWORD *)this + 255) = 0;
    }
    v15 = (PVOID *)*((_QWORD *)this + 300);
    if ( v15 )
    {
      if ( *v15 )
      {
        ExFreePoolWithTag(*v15, 0);
        **((_QWORD **)this + 300) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[1] )
      {
        ExFreePoolWithTag(v15[1], 0);
        *(_QWORD *)(*((_QWORD *)this + 300) + 8LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[2] )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v15[2], (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 300) + 16LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[3] )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v15[3], (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 300) + 24LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[4] )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v15[4], (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 300) + 32LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[9] )
      {
        ExFreePoolWithTag(v15[9], 0);
        *(_QWORD *)(*((_QWORD *)this + 300) + 72LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[11] )
      {
        ExFreePoolWithTag(v15[11], 0);
        *(_QWORD *)(*((_QWORD *)this + 300) + 88LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[5] )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v15[5], (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 300) + 40LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[7] )
      {
        ExFreePoolWithTag(v15[7], 0);
        *(_QWORD *)(*((_QWORD *)this + 300) + 56LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15[8] )
      {
        MsAllocator::SmrStrategy::State::`scalar deleting destructor'(v15[8], (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 300) + 64LL) = 0;
        v15 = (PVOID *)*((_QWORD *)this + 300);
      }
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      *((_QWORD *)this + 300) = 0;
    }
    v16 = (CmsContainerRangeMap *)*((_QWORD *)this + 240);
    if ( v16 )
    {
      CmsContainerRangeMap::`scalar deleting destructor'(v16, (unsigned int)a2);
      *((_QWORD *)this + 240) = 0;
    }
    ExDeleteResourceLite((PERESOURCE)((char *)this + 1016));
    for ( i = 0; i < 5; ++i )
    {
      CheckpointState = CmsVolume::GetCheckpointState(this, i);
      if ( *(_QWORD *)CheckpointState )
      {
        CmsContainerRangeMap::DeleteAll(*(CmsContainerRangeMap **)CheckpointState);
        if ( *(_QWORD *)CheckpointState )
          CmsContainerRangeMap::`scalar deleting destructor'(
            *(CmsContainerRangeMap **)CheckpointState,
            (unsigned int)v18);
        *(_QWORD *)CheckpointState = 0;
      }
      v20 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
      if ( v20 )
      {
        CmsContainerRangeMap::DeleteAll(v20);
        v21 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
        if ( v21 )
          CmsContainerRangeMap::`scalar deleting destructor'(v21, (unsigned int)v18);
        *((_QWORD *)CheckpointState + 1) = 0;
      }
      v22 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
      if ( v22 )
      {
        CmsContainerRangeMap::DeleteAll(v22);
        v23 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
        if ( v23 )
          CmsContainerRangeMap::`scalar deleting destructor'(v23, (unsigned int)v18);
        *((_QWORD *)CheckpointState + 2) = 0;
      }
    }
    v24 = 0;
    v25 = (_QWORD *)((char *)this + 1560);
    do
    {
      if ( *v25 )
        ExDeleteResourceLite((PERESOURCE)((char *)this + 192 * v24 + 1120));
      ++v24;
      v25 += 13;
    }
    while ( v24 < 2 );
    v26 = (void *)*((_QWORD *)this + 193);
    if ( v26 )
    {
      ExFreePoolWithTag(v26, 0);
      *((_QWORD *)this + 193) = 0;
    }
    v27 = (void *)*((_QWORD *)this + 235);
    if ( v27 )
      ExFreePoolWithTag(v27, 0);
    v28 = (void *)*((_QWORD *)this + 238);
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    v29 = *((_QWORD *)this + 428);
    if ( v29 )
    {
      ExFreeAutoExpandPushLock(v29, v18);
      *((_QWORD *)this + 428) = 0;
    }
    v30 = *((_QWORD *)this + 429);
    if ( v30 )
    {
      ExFreeAutoExpandPushLock(v30, v18);
      *((_QWORD *)this + 429) = 0;
    }
    while ( *((_QWORD *)this + 75) )
    {
      v42 = (_QWORD *)*((_QWORD *)this + 75);
      *((_QWORD *)this + 75) = v42[7];
      v42[7] = 0;
      CmsBPlusTable::ReleaseTreeIoBatch(v42, 1u);
      --*((_DWORD *)this + 148);
    }
    v31 = (CmsRangeMap *)*((_QWORD *)this + 430);
    if ( v31 )
    {
      CmsRangeMap::DeleteAll(v31, v18);
      v32 = (CmsRangeMap *)*((_QWORD *)this + 430);
      if ( v32 )
        CmsRangeMap::`scalar deleting destructor'(v32, (unsigned int)v18);
    }
    v33 = (CmsRangeMap *)*((_QWORD *)this + 437);
    if ( v33 )
    {
      CmsRangeMap::DeleteAll(v33, v18);
      v34 = (CmsRangeMap *)*((_QWORD *)this + 437);
      if ( v34 )
        CmsRangeMap::`scalar deleting destructor'(v34, (unsigned int)v18);
    }
    v35 = *((_QWORD *)this + 439);
    if ( v35 )
      ExFreeAutoExpandPushLock(v35, v18);
    v36 = (void *)*((_QWORD *)this + 324);
    if ( v36 )
    {
      CmsCachedRuns::`scalar deleting destructor'(v36, (unsigned int)v18);
      *((_QWORD *)this + 324) = 0;
    }
    v37 = (CmsReferenced *)*((_QWORD *)this + 325);
    if ( v37 )
    {
      CmsReferenced::Release(v37);
      *((_QWORD *)this + 325) = 0;
    }
    v38 = (void *)*((_QWORD *)this + 392);
    if ( v38 )
    {
      ExFreePoolWithTag(v38, 0);
      *((_QWORD *)this + 392) = 0;
    }
    v39 = (PVOID)*((_QWORD *)this + 390);
    if ( v39 != FirstUpcaseTable && (*((_DWORD *)this + 779) & 0x20000) != 0 )
    {
      if ( v39 )
        ExFreePoolWithTag(v39, 0);
      *((_QWORD *)this + 390) = 0;
    }
    v40 = (_QWORD *)*((_QWORD *)this + 377);
    if ( v40 )
    {
      v41 = (void *)v40[3];
      if ( v41 )
        ExFreePoolWithTag(v41, 0);
      ExFreePoolWithTag(v40, 0);
    }
    ExDeleteResourceLite((PERESOURCE)((char *)this + 3160));
  }
  CmsBlockCache::~CmsBlockCache((CmsVolume *)((char *)this + 448));
  CmsBlockCache::~CmsBlockCache((CmsVolume *)((char *)this + 352));
  CmsReservedPools::~CmsReservedPools((CmsVolume *)((char *)this + 88));
  *(_QWORD *)this = &CmsReferenced::`vftable';
}

```

## disassembly

```asm
0x1c0050544  mov     [rsp+arg_0], rbx
0x1c0050549  mov     [rsp+arg_8], rbp
0x1c005054e  mov     [rsp+arg_10], rsi
0x1c0050553  push    rdi
0x1c0050554  sub     rsp, 20h
0x1c0050558  test    dword ptr [rcx+0C2Ch], 10000h
0x1c0050562  lea     rax, ??_7CmsVolume@@6B@; const CmsVolume::`vftable'
0x1c0050569  mov     [rcx], rax
0x1c005056c  mov     rbx, rcx
0x1c005056f  jnz     loc_1C0050A24
0x1c0050575  mov     rcx, [rcx+7F0h]; P
0x1c005057c  xor     ebp, ebp
0x1c005057e  test    rcx, rcx
0x1c0050581  jz      short loc_1C005058F
0x1c0050583  call    ??_GCmsThinProvisioning@@QEAAPEAXI@Z; CmsThinProvisioning::`scalar deleting destructor'(uint)
0x1c0050588  mov     [rbx+7F0h], rbp
0x1c005058f  mov     rcx, [rbx+0C18h]; P
0x1c0050596  test    rcx, rcx
0x1c0050599  jnz     loc_1C0087AA0
0x1c005059f  mov     rcx, [rbx+0C00h]; P
0x1c00505a6  test    rcx, rcx
0x1c00505a9  jnz     loc_1C0087ABA
0x1c00505af  mov     rcx, [rbx+0BF8h]; P
0x1c00505b6  test    rcx, rcx
0x1c00505b9  jnz     loc_1C0087ACB
0x1c00505bf  mov     rcx, [rbx+0BE8h]; P
0x1c00505c6  test    rcx, rcx
0x1c00505c9  jnz     loc_1C0087ADC
0x1c00505cf  mov     rcx, [rbx+0BF0h]; P
0x1c00505d6  test    rcx, rcx
0x1c00505d9  jnz     loc_1C0087AED
0x1c00505df  mov     rdi, [rbx+0C20h]
0x1c00505e6  test    rdi, rdi
0x1c00505e9  jz      short loc_1C005060B
0x1c00505eb  mov     rcx, rdi; this
0x1c00505ee  call    ??1CmsSchemaTable@@QEAA@XZ; CmsSchemaTable::~CmsSchemaTable(void)
0x1c00505f3  xor     edx, edx; Tag
0x1c00505f5  mov     rcx, rdi; P
0x1c00505f8  call    cs:__imp_ExFreePoolWithTag
0x1c00505ff  nop     dword ptr [rax+rax+00h]
0x1c0050604  mov     [rbx+0C20h], rbp
0x1c005060b  mov     rcx, [rbx+0BE0h]; this
0x1c0050612  test    rcx, rcx
0x1c0050615  jnz     loc_1C0087AFE
0x1c005061b  mov     rcx, [rbx+0BD8h]; this
0x1c0050622  test    rcx, rcx
0x1c0050625  jnz     loc_1C0087B0F
0x1c005062b  mov     rcx, [rbx+0BD0h]; this
0x1c0050632  test    rcx, rcx
0x1c0050635  jnz     loc_1C0087B20
0x1c005063b  mov     rcx, [rbx+7F8h]; this
0x1c0050642  test    rcx, rcx
0x1c0050645  jz      short loc_1C0050662
0x1c0050647  cmp     [rcx+18h], rbp
0x1c005064b  jnz     loc_1C0087B31
0x1c0050651  test    rcx, rcx
0x1c0050654  jz      short loc_1C005065B
0x1c0050656  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x1c005065b  mov     [rbx+7F8h], rbp
0x1c0050662  mov     rcx, [rbx+960h]
0x1c0050669  test    rcx, rcx
0x1c005066c  jz      loc_1C00507C1
0x1c0050672  mov     rax, [rcx]
0x1c0050675  test    rax, rax
0x1c0050678  jz      short loc_1C005069C
0x1c005067a  xor     edx, edx; Tag
0x1c005067c  mov     rcx, rax; P
0x1c005067f  call    cs:__imp_ExFreePoolWithTag
0x1c0050686  nop     dword ptr [rax+rax+00h]
0x1c005068b  mov     rax, [rbx+960h]
0x1c0050692  mov     [rax], rbp
0x1c0050695  mov     rcx, [rbx+960h]
0x1c005069c  mov     rax, [rcx+8]
0x1c00506a0  test    rax, rax
0x1c00506a3  jz      short loc_1C00506C8
0x1c00506a5  xor     edx, edx; Tag
0x1c00506a7  mov     rcx, rax; P
0x1c00506aa  call    cs:__imp_ExFreePoolWithTag
0x1c00506b1  nop     dword ptr [rax+rax+00h]
0x1c00506b6  mov     rax, [rbx+960h]
0x1c00506bd  mov     [rax+8], rbp
0x1c00506c1  mov     rcx, [rbx+960h]
0x1c00506c8  mov     rax, [rcx+10h]
0x1c00506cc  test    rax, rax
0x1c00506cf  jz      short loc_1C00506EB
0x1c00506d1  mov     rcx, rax; P
0x1c00506d4  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x1c00506d9  mov     rax, [rbx+960h]
0x1c00506e0  mov     [rax+10h], rbp
0x1c00506e4  mov     rcx, [rbx+960h]
0x1c00506eb  mov     rax, [rcx+18h]
0x1c00506ef  test    rax, rax
0x1c00506f2  jz      short loc_1C005070E
0x1c00506f4  mov     rcx, rax; P
0x1c00506f7  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x1c00506fc  mov     rax, [rbx+960h]
0x1c0050703  mov     [rax+18h], rbp
0x1c0050707  mov     rcx, [rbx+960h]
0x1c005070e  mov     rax, [rcx+20h]
0x1c0050712  test    rax, rax
0x1c0050715  jz      short loc_1C0050731
0x1c0050717  mov     rcx, rax; P
0x1c005071a  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x1c005071f  mov     rax, [rbx+960h]
0x1c0050726  mov     [rax+20h], rbp
0x1c005072a  mov     rcx, [rbx+960h]
0x1c0050731  mov     rax, [rcx+48h]
0x1c0050735  test    rax, rax
0x1c0050738  jnz     loc_1C0087B42
0x1c005073e  mov     rax, [rcx+58h]
0x1c0050742  test    rax, rax
0x1c0050745  jnz     loc_1C0087B6A
0x1c005074b  mov     rax, [rcx+28h]
0x1c005074f  test    rax, rax
0x1c0050752  jz      short loc_1C005076E
0x1c0050754  mov     rcx, rax; P
0x1c0050757  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x1c005075c  mov     rax, [rbx+960h]
0x1c0050763  mov     [rax+28h], rbp
0x1c0050767  mov     rcx, [rbx+960h]
0x1c005076e  mov     rax, [rcx+38h]
0x1c0050772  test    rax, rax
0x1c0050775  jz      short loc_1C005079A
0x1c0050777  xor     edx, edx; Tag
0x1c0050779  mov     rcx, rax; P
0x1c005077c  call    cs:__imp_ExFreePoolWithTag
0x1c0050783  nop     dword ptr [rax+rax+00h]
0x1c0050788  mov     rax, [rbx+960h]
0x1c005078f  mov     [rax+38h], rbp
0x1c0050793  mov     rcx, [rbx+960h]; P
0x1c005079a  mov     rax, [rcx+40h]
0x1c005079e  test    rax, rax
0x1c00507a1  jnz     loc_1C0087B92
0x1c00507a7  test    rcx, rcx
0x1c00507aa  jz      short loc_1C00507BA
0x1c00507ac  xor     edx, edx; Tag
0x1c00507ae  call    cs:__imp_ExFreePoolWithTag
0x1c00507b5  nop     dword ptr [rax+rax+00h]
0x1c00507ba  mov     [rbx+960h], rbp
0x1c00507c1  mov     rcx, [rbx+780h]; this
0x1c00507c8  test    rcx, rcx
0x1c00507cb  jz      short loc_1C00507D9
0x1c00507cd  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x1c00507d2  mov     [rbx+780h], rbp
0x1c00507d9  lea     rcx, [rbx+3F8h]; Resource
0x1c00507e0  call    cs:__imp_ExDeleteResourceLite
0x1c00507e7  nop     dword ptr [rax+rax+00h]
0x1c00507ec  mov     esi, ebp
0x1c00507ee  mov     edx, esi; unsigned int
0x1c00507f0  mov     rcx, rbx; this
0x1c00507f3  call    ?GetCheckpointState@CmsVolume@@AEAAPEAU_SmsCheckpointState@@K@Z; CmsVolume::GetCheckpointState(ulong)
0x1c00507f8  mov     rdi, rax
0x1c00507fb  mov     rcx, [rax]; this
0x1c00507fe  test    rcx, rcx
0x1c0050801  jz      short loc_1C0050818
0x1c0050803  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXXZ; CmsContainerRangeMap::DeleteAll(void)
0x1c0050808  mov     rcx, [rdi]; this
0x1c005080b  test    rcx, rcx
0x1c005080e  jz      short loc_1C0050815
0x1c0050810  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x1c0050815  mov     [rdi], rbp
0x1c0050818  mov     rcx, [rdi+8]; this
0x1c005081c  test    rcx, rcx
0x1c005081f  jz      short loc_1C0050838
0x1c0050821  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXXZ; CmsContainerRangeMap::DeleteAll(void)
0x1c0050826  mov     rcx, [rdi+8]; this
0x1c005082a  test    rcx, rcx
0x1c005082d  jz      short loc_1C0050834
0x1c005082f  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x1c0050834  mov     [rdi+8], rbp
0x1c0050838  mov     rcx, [rdi+10h]; this
0x1c005083c  test    rcx, rcx
0x1c005083f  jz      short loc_1C0050858
0x1c0050841  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXXZ; CmsContainerRangeMap::DeleteAll(void)
0x1c0050846  mov     rcx, [rdi+10h]; this
0x1c005084a  test    rcx, rcx
0x1c005084d  jz      short loc_1C0050854
0x1c005084f  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x1c0050854  mov     [rdi+10h], rbp
0x1c0050858  inc     esi
0x1c005085a  cmp     esi, 5
0x1c005085d  jb      short loc_1C00507EE
0x1c005085f  mov     edi, ebp
0x1c0050861  lea     rsi, [rbx+618h]
0x1c0050868  cmp     [rsi], rbp
0x1c005086b  jz      short loc_1C005088D
0x1c005086d  mov     eax, edi
0x1c005086f  lea     rcx, [rax+rax*2]
0x1c0050873  shl     rcx, 6
0x1c0050877  add     rcx, 460h
0x1c005087e  add     rcx, rbx; Resource
0x1c0050881  call    cs:__imp_ExDeleteResourceLite
0x1c0050888  nop     dword ptr [rax+rax+00h]
0x1c005088d  inc     edi
0x1c005088f  add     rsi, 68h ; 'h'
0x1c0050893  cmp     edi, 2
0x1c0050896  jb      short loc_1C0050868
0x1c0050898  mov     rcx, [rbx+608h]; P
0x1c005089f  test    rcx, rcx
0x1c00508a2  jz      short loc_1C00508B9
0x1c00508a4  xor     edx, edx; Tag
0x1c00508a6  call    cs:__imp_ExFreePoolWithTag
0x1c00508ad  nop     dword ptr [rax+rax+00h]
0x1c00508b2  mov     [rbx+608h], rbp
0x1c00508b9  mov     rcx, [rbx+758h]; P
0x1c00508c0  test    rcx, rcx
0x1c00508c3  jnz     loc_1C0087BB1
0x1c00508c9  mov     rcx, [rbx+770h]; P
0x1c00508d0  test    rcx, rcx
0x1c00508d3  jnz     loc_1C0087BC5
0x1c00508d9  mov     rcx, [rbx+0D60h]
0x1c00508e0  test    rcx, rcx
0x1c00508e3  jz      short loc_1C00508F8
0x1c00508e5  call    cs:__imp_ExFreeAutoExpandPushLock
0x1c00508ec  nop     dword ptr [rax+rax+00h]
0x1c00508f1  mov     [rbx+0D60h], rbp
0x1c00508f8  mov     rcx, [rbx+0D68h]
0x1c00508ff  test    rcx, rcx
0x1c0050902  jz      short loc_1C0050917
0x1c0050904  call    cs:__imp_ExFreeAutoExpandPushLock
0x1c005090b  nop     dword ptr [rax+rax+00h]
0x1c0050910  mov     [rbx+0D68h], rbp
0x1c0050917  cmp     [rbx+258h], rbp
0x1c005091e  jnz     loc_1C0050A65
0x1c0050924  mov     rcx, [rbx+0D70h]; this
0x1c005092b  test    rcx, rcx
0x1c005092e  jz      short loc_1C0050946
0x1c0050930  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x1c0050935  mov     rcx, [rbx+0D70h]; this
0x1c005093c  test    rcx, rcx
0x1c005093f  jz      short loc_1C0050946
0x1c0050941  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x1c0050946  mov     rcx, [rbx+0DA8h]; this
0x1c005094d  test    rcx, rcx
0x1c0050950  jz      short loc_1C0050968
0x1c0050952  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x1c0050957  mov     rcx, [rbx+0DA8h]; this
0x1c005095e  test    rcx, rcx
0x1c0050961  jz      short loc_1C0050968
0x1c0050963  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x1c0050968  mov     rcx, [rbx+0DB8h]
0x1c005096f  test    rcx, rcx
0x1c0050972  jz      short loc_1C0050980
0x1c0050974  call    cs:__imp_ExFreeAutoExpandPushLock
0x1c005097b  nop     dword ptr [rax+rax+00h]
0x1c0050980  mov     rcx, [rbx+0A20h]; P
0x1c0050987  test    rcx, rcx
0x1c005098a  jz      short loc_1C0050998
0x1c005098c  call    ??_GCmsCachedRuns@@QEAAPEAXI@Z; CmsCachedRuns::`scalar deleting destructor'(uint)
0x1c0050991  mov     [rbx+0A20h], rbp
0x1c0050998  mov     rcx, [rbx+0A28h]; this
0x1c005099f  test    rcx, rcx
0x1c00509a2  jnz     loc_1C0087BD9
0x1c00509a8  mov     rcx, [rbx+0C40h]; P
0x1c00509af  test    rcx, rcx
0x1c00509b2  jz      short loc_1C00509C9
0x1c00509b4  xor     edx, edx; Tag
0x1c00509b6  call    cs:__imp_ExFreePoolWithTag
0x1c00509bd  nop     dword ptr [rax+rax+00h]
0x1c00509c2  mov     [rbx+0C40h], rbp
0x1c00509c9  mov     rcx, [rbx+0C30h]; P
0x1c00509d0  cmp     rcx, cs:?FirstUpcaseTable@@3PEAGEA; ushort * FirstUpcaseTable
0x1c00509d7  jnz     loc_1C0087BEA
0x1c00509dd  mov     rdi, [rbx+0BC8h]
0x1c00509e4  test    rdi, rdi
0x1c00509e7  jz      short loc_1C0050A11
0x1c00509e9  mov     rcx, [rdi+18h]; P
0x1c00509ed  test    rcx, rcx
0x1c00509f0  jz      short loc_1C0050A00
0x1c00509f2  xor     edx, edx; Tag
0x1c00509f4  call    cs:__imp_ExFreePoolWithTag
0x1c00509fb  nop     dword ptr [rax+rax+00h]
0x1c0050a00  xor     edx, edx; Tag
0x1c0050a02  mov     rcx, rdi; P
0x1c0050a05  call    cs:__imp_ExFreePoolWithTag
0x1c0050a0c  nop     dword ptr [rax+rax+00h]
0x1c0050a11  lea     rcx, [rbx+0C58h]; Resource
0x1c0050a18  call    cs:__imp_ExDeleteResourceLite
0x1c0050a1f  nop     dword ptr [rax+rax+00h]
0x1c0050a24  lea     rcx, [rbx+1C0h]; this
0x1c0050a2b  call    ??1CmsBlockCache@@QEAA@XZ; CmsBlockCache::~CmsBlockCache(void)
0x1c0050a30  lea     rcx, [rbx+160h]; this
0x1c0050a37  call    ??1CmsBlockCache@@QEAA@XZ; CmsBlockCache::~CmsBlockCache(void)
0x1c0050a3c  lea     rcx, [rbx+58h]; this
0x1c0050a40  call    ??1CmsReservedPools@@QEAA@XZ; CmsReservedPools::~CmsReservedPools(void)
0x1c0050a45  mov     rbp, [rsp+28h+arg_8]
0x1c0050a4a  lea     rax, ??_7CmsReferenced@@6B@; const CmsReferenced::`vftable'
0x1c0050a51  mov     rsi, [rsp+28h+arg_10]
0x1c0050a56  mov     [rbx], rax
0x1c0050a59  mov     rbx, [rsp+28h+arg_0]
0x1c0050a5e  add     rsp, 20h
0x1c0050a62  pop     rdi
0x1c0050a63  retn
0x1c0050a65  mov     rcx, [rbx+258h]; P
0x1c0050a6c  mov     dl, 1; unsigned __int8
0x1c0050a6e  mov     rax, [rcx+38h]
0x1c0050a72  mov     [rbx+258h], rax
0x1c0050a79  mov     [rcx+38h], rbp
0x1c0050a7d  call    ?ReleaseTreeIoBatch@CmsBPlusTable@@SAXPEAU_SmsIoBatch@@E@Z; CmsBPlusTable::ReleaseTreeIoBatch(_SmsIoBatch *,uchar)
0x1c0050a82  dec     dword ptr [rbx+250h]
  ... truncated ...
```
