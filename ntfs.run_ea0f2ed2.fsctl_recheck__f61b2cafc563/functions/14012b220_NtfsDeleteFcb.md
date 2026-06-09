# NtfsDeleteFcb

- ea: `0x14012b220`
- end: `0x14012ba69`
- name: `NtfsDeleteFcb`
- size: `2121`
- prototype: ``
- caller_count: `11`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140029d80`
- `0x140107fdc`
- `0x14012a0f0`
- `0x140195b14`
- `0x14019616c`
- `0x1401ff460`
- `0x140256294`
- `0x14025649c`
- `0x1402565ac`
- `0x140256640`
- `0x1402682f8`

## callees

- `0x140021910`
- `0x140025b70`
- `0x140025df0`
- `0x140029140`
- `0x1400b84ec`
- `0x140129fb0`
- `0x14012b220`
- `0x14012baf8`
- `0x140140ab0`
- `0x140140f5c`
- `0x140196e30`
- `0x14025120c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012b287`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14012b287`
- `ntoskrnl!CcUnmapFileOffsetFromSystemCache` at `0x14012b79c`
- `ntoskrnl!CcUnmapFileOffsetFromSystemCache` at `0x14012b79c`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b42b`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b712`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b42b`
- `ntoskrnl!ExReinitializeResourceLite` at `0x14012b712`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x14012b659`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x14012b659`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14012b2bc`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14012b2bc`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402c762b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402c762b`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b2f6`
- `ntoskrnl!ExReleasePushLockEx` at `0x14012b2f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b44a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b690`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b7b4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b9f7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b44a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b690`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b7b4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012b9f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b5ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b6ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b823`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b861`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b96e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b9c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b5ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b6ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b823`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b861`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b96e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012b9c2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012b809`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14012b809`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012b83d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c765e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14012b83d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c765e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b4fd`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b98a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b4fd`
- `ntoskrnl!ExAcquireFastMutex` at `0x14012b98a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b570`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b765`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b915`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b570`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b765`
- `ntoskrnl!ExReleaseFastMutex` at `0x14012b915`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1402c7610`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1402c7610`

## pseudocode

```c
void __fastcall NtfsDeleteFcb(__int64 a1, _QWORD *a2, unsigned __int64 *a3)
{
  __int64 v5; // rbp
  __int64 v6; // rcx
  char v7; // r12
  __int64 v8; // r13
  unsigned __int64 *v9; // r14
  __int64 v10; // rdi
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // rdx
  _QWORD *v18; // r14
  __int64 v19; // rax
  __int64 v20; // r13
  __int64 v21; // rcx
  __int64 v22; // rcx
  void *v23; // rcx
  char *v24; // rdi
  struct _LOOKASIDE_LIST_EX *v25; // rcx
  char *v26; // r8
  _QWORD *v27; // r9
  char *i; // rcx
  __int64 v29; // rdi
  __int64 v30; // rcx
  __int64 v31; // rax
  void *v32; // rcx
  unsigned int *v33; // rbp
  __int64 v34; // r14
  __int64 v35; // rcx
  __int16 *v36; // r8
  __int16 v37; // cx
  volatile signed __int32 *v38; // rcx
  signed __int32 v39; // eax
  bool v40; // cc
  signed __int32 v41; // eax
  _QWORD *v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  _BYTE *v47; // rcx
  _DWORD *v48; // rcx
  int v49; // eax
  void *v50; // rdx
  __int64 v51; // rcx
  _DWORD *v52; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  void *v56; // rcx
  int v57; // ebp
  __int64 v58; // r15
  __int64 v59; // rcx
  _QWORD *v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  _QWORD *v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rcx
  struct _ERESOURCE *v70; // rcx
  unsigned int v71; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v72; // [rsp+78h] [rbp+10h] BYREF
  __int64 v73; // [rsp+80h] [rbp+18h]
  __int64 v74; // [rsp+88h] [rbp+20h]

  v74 = *(_QWORD *)(a1 + 16);
  if ( (v74 & 0x20) == 0 )
  {
    v5 = *a2;
    v6 = *a2;
LABEL_3:
    v7 = 0;
    goto LABEL_4;
  }
  v6 = *a2;
  v5 = *a2;
  if ( (*(_DWORD *)(*a2 + 4LL) & 0x2000000) == 0 )
    goto LABEL_3;
  v7 = 1;
LABEL_4:
  v8 = *(_QWORD *)(v6 + 96);
  v9 = &v72;
  LOBYTE(v72) = 0;
  LOBYTE(v71) = 0;
  if ( a3 )
    v9 = a3;
  v73 = v8;
  if ( !*(_BYTE *)v9 )
  {
    ExAcquirePushLockExclusiveEx(v8 + 656, 0);
    *(_BYTE *)v9 = 1;
    v5 = *a2;
  }
  if ( !v7 && (*(_DWORD *)(v5 + 4) & 0x40) != 0 )
  {
    v10 = *(_QWORD *)(v5 + 96);
    RtlAvlRemoveNode(v10 + 1344, *(_QWORD *)(v5 + 104) + 256LL);
    --*(_DWORD *)(v10 + 1352);
    *(_DWORD *)(v5 + 4) &= ~0x40u;
    LOBYTE(v71) = 1;
  }
  v11 = *(_QWORD *)(*a2 + 328LL);
  if ( v11 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v11 + 136), 1u);
    v56 = *(void **)(v11 + 152);
    if ( v56 )
    {
      ExFreePoolWithTag(v56, 0);
      *(_QWORD *)(v11 + 152) = 0;
    }
    ExReleaseResourceLite(*(PERESOURCE *)(v11 + 136));
  }
  ExReleasePushLockEx(v8 + 656, 0);
  *(_BYTE *)v9 = 0;
  NtfsFreeSnapshotsForFcb(a1, *a2);
  v12 = *a2;
  if ( (*(_DWORD *)(*a2 + 4LL) & 0x800000) != 0 )
    TxfSearchingForSystemRoot = 1;
  if ( !v7 )
  {
    v13 = v12 + 80;
    v14 = *(_QWORD *)(v12 + 80);
    if ( v14 )
    {
      if ( *(_QWORD *)(v14 + 8) != v13 )
        goto LABEL_94;
      v15 = *(_QWORD **)(v13 + 8);
      if ( *v15 != v13 )
        goto LABEL_94;
      *v15 = v14;
      *(_QWORD *)(v14 + 8) = v15;
      *(_QWORD *)(*a2 + 80LL) = 0;
    }
  }
  v16 = a1;
  v17 = 1805;
  do
  {
    v18 = *(_QWORD **)(v16 + 40);
    if ( v18 )
    {
      v57 = *(unsigned __int16 *)(v16 + 34);
      v58 = *a2;
      if ( v57 == 1 )
        v18 = (_QWORD *)(v16 + 40);
      do
      {
        v59 = *v18;
        if ( *v18 && v59 == v58 )
        {
          if ( *(_WORD *)v59 == 1805 )
          {
            NtfsReleaseQuotaControl(v16, *v18);
          }
          else
          {
            if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v59 + 104) + 64LL))
              && ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*v18 + 104LL) + 64LL)) == 1 )
            {
              NtfsFreeSnapshotsForFcb(v16, *v18);
            }
            v69 = *v18;
            if ( *(_WORD *)*v18 == 1794 )
              v70 = (struct _ERESOURCE *)(*(_QWORD *)(v69 + 104) + 64LL);
            else
              v70 = *(struct _ERESOURCE **)(v69 + 8);
            ExReleaseResourceLite(v70);
          }
          *v18 = 0;
          v17 = 1805;
          if ( *(_WORD *)(v16 + 34) == 1 )
            *(_WORD *)(v16 + 34) = 0;
        }
        ++v18;
        --v57;
      }
      while ( v57 );
    }
    v19 = *(_QWORD *)(v16 + 144);
    if ( v16 == v19 )
      break;
    v16 = *(_QWORD *)(v16 + 144);
  }
  while ( v19 );
  v20 = v73;
  if ( *(int *)(*a2 + 176LL) < 0 )
    *(_DWORD *)(a1 + 436) &= ~0x8000u;
  if ( !v7 )
  {
    if ( *(_QWORD *)(a1 + 48) == *a2 )
      *(_QWORD *)(a1 + 48) = 0;
    if ( *(_QWORD *)(a1 + 56) == *a2 )
      *(_QWORD *)(a1 + 56) = 0;
    v21 = *(_QWORD *)(a1 + 144);
    if ( v21 )
    {
      if ( *(_QWORD *)(v21 + 48) == *a2 )
        *(_QWORD *)(v21 + 48) = 0;
      v22 = *(_QWORD *)(a1 + 144);
      if ( *(_QWORD *)(v22 + 56) == *a2 )
        *(_QWORD *)(v22 + 56) = 0;
    }
    if ( **(_WORD **)(*a2 + 104LL) == 1861 )
    {
      v23 = *(void **)(*a2 + 112LL);
      if ( v23 )
      {
        NtfsFreeEresource(v23);
        *(_QWORD *)(*a2 + 112LL) = 0;
      }
    }
    v24 = *(char **)(*a2 + 104LL);
    ExReinitializeResourceLite((PERESOURCE)(v24 + 64));
    if ( *(_WORD *)v24 == 1861 )
    {
      v25 = &NtfsFcbNonpagedIndexLookasideList;
    }
    else
    {
      ExReinitializeResourceLite((PERESOURCE)(v24 + 280));
      v25 = &NtfsFcbNonpagedDataLookasideList;
    }
    ExFreeToLookasideListEx(v25, v24);
    *(_QWORD *)(*a2 + 104LL) = 0;
  }
  if ( *(_QWORD *)(*a2 + 296LL) )
  {
    v26 = (char *)(a1 + 232);
    v27 = 0;
    for ( i = (char *)(a1 + 232); *((_QWORD *)i + 1) != *a2; i = *(char **)i )
    {
      v17 = *(_QWORD *)i;
      if ( !*(_QWORD *)i )
        goto LABEL_44;
      v27 = i;
    }
    if ( i == v26 )
    {
      *(_OWORD *)(i + 8) = 0;
      *(_OWORD *)(i + 24) = 0;
    }
    else
    {
      *v27 = *(_QWORD *)i;
      ExFreePoolWithTag(i, 0);
    }
LABEL_44:
    if ( !*(_QWORD *)(*(_QWORD *)(*a2 + 296LL) + 32LL) )
      goto LABEL_45;
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*a2 + 96LL) + 1992LL));
    v65 = *(_QWORD *)(*a2 + 296LL);
    v66 = *(_QWORD *)(v65 + 32);
    v67 = v65 + 32;
    if ( !v66 )
      goto LABEL_115;
    if ( *(_QWORD *)(v66 + 8) != v67 )
      goto LABEL_94;
    v60 = *(_QWORD **)(v67 + 8);
    if ( *v60 != v67 )
      goto LABEL_94;
    *v60 = v66;
    *(_QWORD *)(v66 + 8) = v60;
    v61 = *(_QWORD *)(*a2 + 296LL);
    v62 = *(_QWORD *)(v61 + 16);
    v63 = v61 + 16;
    if ( !v62 )
    {
LABEL_115:
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*a2 + 96LL) + 1992LL));
LABEL_45:
      v29 = *a2;
      --*(_DWORD *)(*(_QWORD *)(*a2 + 296LL) + 4LL);
      v30 = *(_QWORD *)(v29 + 296);
      if ( !*(_DWORD *)(v30 + 4) )
      {
        v51 = *(_QWORD *)(v30 + 48);
        if ( v51 )
        {
          if ( (*(_DWORD *)(v51 + 144) & 1) != 0 )
            FsLibRangeTrackUninitialize(v51, v17, v26, v27);
          v52 = *(_DWORD **)(*(_QWORD *)(v29 + 296) + 48LL);
          if ( (v52[36] & 8) == 0 )
            ExFreePoolWithTag(v52, 0);
        }
        ExFreePoolWithTag(*(PVOID *)(v29 + 296), 0);
        *(_QWORD *)(v29 + 296) = 0;
      }
      *(_QWORD *)(*a2 + 296LL) = 0;
      goto LABEL_47;
    }
    if ( *(_QWORD *)(v62 + 8) == v63 )
    {
      v64 = *(_QWORD **)(v63 + 8);
      if ( *v64 == v63 )
      {
        *v64 = v62;
        *(_QWORD *)(v62 + 8) = v64;
        *(_QWORD *)(*(_QWORD *)(*a2 + 296LL) + 16LL) = 0;
        goto LABEL_115;
      }
    }
LABEL_94:
    __fastfail(3u);
  }
LABEL_47:
  v31 = *a2;
  v32 = *(void **)(*a2 + 328LL);
  if ( v32 )
  {
    TxfDereferenceTxfFcb(v32);
    *(_QWORD *)(*a2 + 328LL) = 0;
    v31 = *a2;
  }
  if ( (_BYTE)v71 )
  {
    v71 = 0;
    v33 = (unsigned int *)(v31 + 8);
    LODWORD(v72) = 0;
    ExAcquireFastMutex((PFAST_MUTEX)(v20 + 7400));
    NtfsGetArrayAndCounterIdx(v20 + 7400, v33, &v71, &v72);
    if ( v71 != -1
      && (_DWORD)v72 != -1
      && (v34 = *(_QWORD *)(v20 + 7480) + 16LL * v71, (v35 = *(_QWORD *)(v34 + 8)) != 0)
      && (v36 = (__int16 *)(v35 + 2LL * (unsigned int)v72), (v37 = *v36) != 0)
      && (*v36 = v37 - 1, v37 == 1) )
    {
      if ( (v74 & 0x8000) != 0 )
      {
        v72 = (unsigned __int64)*v33 << *(_BYTE *)(v20 + 492);
        if ( (*(_WORD *)v34)-- == 1 )
        {
          ExFreeToLookasideListEx(&NtfsMftViewReferenceLookasideList, *(PVOID *)(v34 + 8));
          *(_QWORD *)(v34 + 8) = 0;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(v20 + 7400));
        v54 = *(_QWORD *)(v20 + 48);
        if ( v54 )
        {
          v55 = *(_QWORD *)(v54 + 280);
          if ( v55 )
            CcUnmapFileOffsetFromSystemCache(v55, &v72, 0x40000, 0);
        }
      }
      else
      {
        --*(_WORD *)v34;
        NtfsMftViewAddToDelayedUnmap(v20, v33);
      }
    }
    else
    {
      ExReleaseFastMutex((PFAST_MUTEX)(v20 + 7400));
    }
  }
  v38 = *(volatile signed __int32 **)(*a2 + 208LL);
  if ( v38 )
  {
    *(_QWORD *)(*a2 + 208LL) = 0;
    v39 = _InterlockedExchangeAdd(v38, 0xFFFFFFFF);
    v40 = v39 <= 1;
    v41 = v39 - 1;
    if ( v40 )
    {
      if ( v41 )
        __fastfail(0xEu);
      ExFreePoolWithTag((PVOID)v38, 0);
    }
  }
  v42 = (_QWORD *)(*a2 + 120LL);
  if ( *v42 )
    NtfsDereferenceQuotaControlBlock(v20, v42, 0);
  v43 = NtfsAddStructToRollbackList(a1, 1827, *a2, 0);
  if ( v43 )
    NtfsProcessRollbackStruct(a1, v43, 16);
  v44 = *(_QWORD *)(a1 + 144);
  if ( a1 != v44 )
  {
    v68 = NtfsAddStructToRollbackList(v44, 1827, *a2, 0);
    if ( v68 )
      NtfsProcessRollbackStruct(*(_QWORD *)(a1 + 144), v68, 16);
  }
  v45 = *a2;
  v46 = *(_QWORD *)(*a2 + 320LL);
  if ( v46 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v46 + 36));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(*a2 + 320LL) + 64LL), 0xFFFFFFFF) == 1 )
      TxfDeleteTxfRmcb(*(char **)(*a2 + 320LL));
    *(_QWORD *)(*a2 + 320LL) = 0;
    v45 = *a2;
  }
  if ( !v7 )
  {
    v47 = *(_BYTE **)(v45 + 304);
    if ( v47 )
      *v47 = 1;
  }
  if ( (*(_DWORD *)(*a2 + 4LL) & 4) == 0 )
    FsRtlTeardownPerFileContexts((PVOID *)(*a2 + 336LL));
  v48 = (_DWORD *)*a2;
  v49 = *(_DWORD *)(*a2 + 4LL);
  if ( v7 )
  {
    v48[1] = v49 | 0x4000000;
  }
  else if ( (v49 & 2) != 0 )
  {
    ExFreePoolWithTag(v48, 0);
  }
  else
  {
    v50 = (void *)*a2;
    if ( (v49 & 0x400) != 0 )
      ExFreeToLookasideListEx(&NtfsFcbIndexLookasideList, v50);
    else
      ExFreeToLookasideListEx(&NtfsFcbDataLookasideList, v50);
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x14012b220  push    rbx
0x14012b222  push    rbp
0x14012b223  push    rsi
0x14012b224  push    rdi
0x14012b225  push    r12
0x14012b227  push    r13
0x14012b229  push    r14
0x14012b22b  push    r15
0x14012b22d  sub     rsp, 28h
0x14012b231  mov     r15, [rcx+10h]
0x14012b235  mov     rbx, rdx
0x14012b238  mov     [rsp+68h+arg_18], r15
0x14012b240  mov     rsi, rcx
0x14012b243  test    r15b, 20h
0x14012b247  jnz     loc_14012B7E5
0x14012b24d  mov     rbp, [rdx]
0x14012b250  mov     rcx, rbp
0x14012b253  xor     r12b, r12b
0x14012b256  mov     r13, [rcx+60h]
0x14012b25a  lea     r14, [rsp+68h+arg_8]
0x14012b25f  test    r8, r8
0x14012b262  mov     byte ptr [rsp+68h+arg_8], 0
0x14012b267  mov     byte ptr [rsp+68h+arg_0], 0
0x14012b26c  cmovnz  r14, r8
0x14012b270  mov     [rsp+68h+arg_10], r13
0x14012b278  cmp     byte ptr [r14], 0
0x14012b27c  jnz     short loc_14012B29A
0x14012b27e  lea     rcx, [r13+290h]
0x14012b285  xor     edx, edx
0x14012b287  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012b28e  nop     dword ptr [rax+rax+00h]
0x14012b293  mov     byte ptr [r14], 1
0x14012b297  mov     rbp, [rbx]
0x14012b29a  test    r12b, r12b
0x14012b29d  jnz     short loc_14012B2D7
0x14012b29f  mov     eax, [rbp+4]
0x14012b2a2  test    al, 40h
0x14012b2a4  jz      short loc_14012B2D7
0x14012b2a6  mov     rdi, [rbp+60h]
0x14012b2aa  mov     rdx, [rbp+68h]
0x14012b2ae  add     rdx, 100h
0x14012b2b5  lea     rcx, [rdi+540h]
0x14012b2bc  call    cs:__imp_RtlAvlRemoveNode
0x14012b2c3  nop     dword ptr [rax+rax+00h]
0x14012b2c8  dec     dword ptr [rdi+548h]
0x14012b2ce  and     dword ptr [rbp+4], 0FFFFFFBFh
0x14012b2d2  mov     byte ptr [rsp+68h+arg_0], 1
0x14012b2d7  mov     rax, [rbx]
0x14012b2da  xor     r15d, r15d
0x14012b2dd  mov     rdi, [rax+148h]
0x14012b2e4  test    rdi, rdi
0x14012b2e7  jnz     loc_14012B800
0x14012b2ed  lea     rcx, [r13+290h]
0x14012b2f4  xor     edx, edx
0x14012b2f6  call    cs:__imp_ExReleasePushLockEx
0x14012b2fd  nop     dword ptr [rax+rax+00h]
0x14012b302  mov     [r14], r15b
0x14012b305  mov     rcx, rsi
0x14012b308  mov     rdx, [rbx]
0x14012b30b  call    NtfsFreeSnapshotsForFcb
0x14012b310  mov     rcx, [rbx]
0x14012b313  test    dword ptr [rcx+4], 800000h
0x14012b31a  jz      short loc_14012B323
0x14012b31c  mov     cs:TxfSearchingForSystemRoot, 1
0x14012b323  test    r12b, r12b
0x14012b326  jnz     short loc_14012B35A
0x14012b328  lea     rax, [rcx+50h]
0x14012b32c  mov     rcx, [rcx+50h]
0x14012b330  test    rcx, rcx
0x14012b333  jz      short loc_14012B35A
0x14012b335  cmp     [rcx+8], rax
0x14012b339  jnz     loc_14012B7DE
0x14012b33f  mov     rdx, [rax+8]
0x14012b343  cmp     [rdx], rax
0x14012b346  jnz     loc_14012B7DE
0x14012b34c  mov     [rdx], rcx
0x14012b34f  mov     [rcx+8], rdx
0x14012b353  mov     rax, [rbx]
0x14012b356  mov     [rax+50h], r15
0x14012b35a  mov     rdi, rsi
0x14012b35d  mov     edx, 70Dh
0x14012b362  mov     r13d, 702h
0x14012b368  mov     r14, [rdi+28h]
0x14012b36c  lea     rax, [rdi+28h]
0x14012b370  test    r14, r14
0x14012b373  jnz     loc_14012B87E
0x14012b379  mov     rax, [rdi+90h]
0x14012b380  cmp     rdi, rax
0x14012b383  jnz     loc_14012B84E
0x14012b389  mov     rax, [rbx]
0x14012b38c  mov     r13, [rsp+68h+arg_10]
0x14012b394  cmp     dword ptr [rax+0B0h], 0
0x14012b39b  jge     short loc_14012B3A7
0x14012b39d  and     dword ptr [rsi+1B4h], 0FFFF7FFFh
0x14012b3a7  xor     r15d, r15d
0x14012b3aa  test    r12b, r12b
0x14012b3ad  jnz     loc_14012B45D
0x14012b3b3  mov     rax, [rbx]
0x14012b3b6  cmp     [rsi+30h], rax
0x14012b3ba  jnz     short loc_14012B3C0
0x14012b3bc  mov     [rsi+30h], r15
0x14012b3c0  mov     rax, [rbx]
0x14012b3c3  cmp     [rsi+38h], rax
0x14012b3c7  jnz     short loc_14012B3CD
0x14012b3c9  mov     [rsi+38h], r15
0x14012b3cd  mov     rcx, [rsi+90h]
0x14012b3d4  test    rcx, rcx
0x14012b3d7  jz      short loc_14012B3FA
0x14012b3d9  mov     rax, [rbx]
0x14012b3dc  cmp     [rcx+30h], rax
0x14012b3e0  jnz     short loc_14012B3E6
0x14012b3e2  mov     [rcx+30h], r15
0x14012b3e6  mov     rcx, [rsi+90h]
0x14012b3ed  mov     rax, [rbx]
0x14012b3f0  cmp     [rcx+38h], rax
0x14012b3f4  jz      loc_14012B949
0x14012b3fa  mov     rcx, [rbx]
0x14012b3fd  mov     ebp, 745h
0x14012b402  mov     rax, [rcx+68h]
0x14012b406  cmp     [rax], bp
0x14012b409  jnz     short loc_14012B420
0x14012b40b  mov     rcx, [rcx+70h]; P
0x14012b40f  test    rcx, rcx
0x14012b412  jz      short loc_14012B420
0x14012b414  call    NtfsFreeEresource
0x14012b419  mov     rax, [rbx]
0x14012b41c  mov     [rax+70h], r15
0x14012b420  mov     rax, [rbx]
0x14012b423  mov     rdi, [rax+68h]
0x14012b427  lea     rcx, [rdi+40h]; Resource
0x14012b42b  call    cs:__imp_ExReinitializeResourceLite
0x14012b432  nop     dword ptr [rax+rax+00h]
0x14012b437  cmp     [rdi], bp
0x14012b43a  jnz     loc_14012B70B
0x14012b440  lea     rcx, NtfsFcbNonpagedIndexLookasideList; Lookaside
0x14012b447  mov     rdx, rdi; Entry
0x14012b44a  call    cs:__imp_ExFreeToLookasideListEx
0x14012b451  nop     dword ptr [rax+rax+00h]
0x14012b456  mov     rax, [rbx]
0x14012b459  mov     [rax+68h], r15
0x14012b45d  mov     rax, [rbx]
0x14012b460  cmp     qword ptr [rax+128h], 0
0x14012b468  jz      short loc_14012B4CA
0x14012b46a  lea     r8, [rsi+0E8h]
0x14012b471  mov     r9, r15
0x14012b474  mov     rcx, r8; P
0x14012b477  cmp     [rcx+8], rax
0x14012b47b  jz      loc_14012B95D
0x14012b481  mov     rdx, [rcx]
0x14012b484  test    rdx, rdx
0x14012b487  jnz     loc_14012B952
0x14012b48d  mov     rcx, [rbx]
0x14012b490  mov     rax, [rcx+128h]
0x14012b497  cmp     qword ptr [rax+20h], 0
0x14012b49c  jnz     loc_14012B97F
0x14012b4a2  mov     rdi, [rbx]
0x14012b4a5  mov     rax, [rdi+128h]
0x14012b4ac  dec     dword ptr [rax+4]
0x14012b4af  mov     rcx, [rdi+128h]
0x14012b4b6  cmp     dword ptr [rcx+4], 0
0x14012b4ba  jz      loc_14012B6B1
0x14012b4c0  mov     rax, [rbx]
0x14012b4c3  mov     [rax+128h], r15
0x14012b4ca  mov     rax, [rbx]
0x14012b4cd  mov     rcx, [rax+148h]
0x14012b4d4  test    rcx, rcx
0x14012b4d7  jnz     loc_14012B7C5
0x14012b4dd  cmp     byte ptr [rsp+68h+arg_0], 0
0x14012b4e2  jz      loc_14012B57C
0x14012b4e8  lea     rcx, [r13+1CE8h]; FastMutex
0x14012b4ef  mov     [rsp+68h+arg_0], r15d
0x14012b4f4  lea     rbp, [rax+8]
0x14012b4f8  mov     dword ptr [rsp+68h+arg_8], r15d
0x14012b4fd  call    cs:__imp_ExAcquireFastMutex
0x14012b504  nop     dword ptr [rax+rax+00h]
0x14012b509  lea     r9, [rsp+68h+arg_8]
0x14012b50e  mov     rdx, rbp
0x14012b511  lea     r8, [rsp+68h+arg_0]
0x14012b516  lea     rcx, [r13+1CE8h]
0x14012b51d  call    NtfsGetArrayAndCounterIdx
0x14012b522  mov     ecx, [rsp+68h+arg_0]
0x14012b526  cmp     ecx, 0FFFFFFFFh
0x14012b529  jz      short loc_14012B569
0x14012b52b  mov     edx, dword ptr [rsp+68h+arg_8]
0x14012b52f  cmp     edx, 0FFFFFFFFh
0x14012b532  jz      short loc_14012B569
0x14012b534  mov     r14d, ecx
0x14012b537  shl     r14, 4
0x14012b53b  add     r14, [r13+1D38h]
0x14012b542  mov     rcx, [r14+8]
0x14012b546  test    rcx, rcx
0x14012b549  jz      short loc_14012B569
0x14012b54b  lea     r8, [rcx+rdx*2]
0x14012b54f  movzx   ecx, word ptr [rcx+rdx*2]
0x14012b553  test    cx, cx
0x14012b556  jz      short loc_14012B569
0x14012b558  lea     eax, [rcx-1]
0x14012b55b  mov     [r8], ax
0x14012b55f  cmp     cx, 1
0x14012b563  jz      loc_14012B72A
0x14012b569  lea     rcx, [r13+1CE8h]; FastMutex
0x14012b570  call    cs:__imp_ExReleaseFastMutex
0x14012b577  nop     dword ptr [rax+rax+00h]
0x14012b57c  mov     rax, [rbx]
0x14012b57f  mov     edi, 0FFFFFFFFh
0x14012b584  mov     rcx, [rax+0D0h]; P
0x14012b58b  test    rcx, rcx
0x14012b58e  jz      short loc_14012B5B8
0x14012b590  mov     [rax+0D0h], r15
0x14012b597  mov     eax, edi
0x14012b599  lock xadd [rcx], eax
0x14012b59d  sub     eax, 1
0x14012b5a0  jg      short loc_14012B5B8
0x14012b5a2  test    eax, eax
0x14012b5a4  jnz     loc_14012B872
0x14012b5aa  xor     edx, edx; Tag
0x14012b5ac  call    cs:__imp_ExFreePoolWithTag
0x14012b5b3  nop     dword ptr [rax+rax+00h]
0x14012b5b8  mov     rdx, [rbx]
0x14012b5bb  add     rdx, 78h ; 'x'
0x14012b5bf  cmp     qword ptr [rdx], 0
0x14012b5c3  jz      short loc_14012B5D0
0x14012b5c5  xor     r8d, r8d
0x14012b5c8  mov     rcx, r13
0x14012b5cb  call    NtfsDereferenceQuotaControlBlock
0x14012b5d0  mov     r8, [rbx]
0x14012b5d3  mov     edx, 723h
0x14012b5d8  xor     r9d, r9d
0x14012b5db  mov     rcx, rsi
0x14012b5de  call    NtfsAddStructToRollbackList
0x14012b5e3  test    rax, rax
0x14012b5e6  jnz     loc_14012BA0C
0x14012b5ec  mov     rcx, [rsi+90h]
0x14012b5f3  cmp     rsi, rcx
0x14012b5f6  jnz     loc_14012BA22
0x14012b5fc  mov     rax, [rbx]
0x14012b5ff  mov     rcx, [rax+140h]
0x14012b606  test    rcx, rcx
0x14012b609  jz      short loc_14012B634
0x14012b60b  lock dec dword ptr [rcx+24h]
0x14012b60f  mov     rax, [rbx]
0x14012b612  mov     rcx, [rax+140h]
0x14012b619  lock xadd [rcx+40h], edi
0x14012b61e  cmp     edi, 1
0x14012b621  jz      loc_14012BA55
0x14012b627  mov     rax, [rbx]
0x14012b62a  mov     [rax+140h], r15
0x14012b631  mov     rax, [rbx]
0x14012b634  test    r12b, r12b
0x14012b637  jnz     short loc_14012B648
0x14012b639  mov     rcx, [rax+130h]
0x14012b640  test    rcx, rcx
0x14012b643  jz      short loc_14012B648
0x14012b645  mov     byte ptr [rcx], 1
0x14012b648  mov     rcx, [rbx]
0x14012b64b  mov     eax, [rcx+4]
0x14012b64e  test    al, 4
0x14012b650  jnz     short loc_14012B665
0x14012b652  add     rcx, 150h; PerFileContextPointer
0x14012b659  call    cs:__imp_FsRtlTeardownPerFileContexts
0x14012b660  nop     dword ptr [rax+rax+00h]
0x14012b665  mov     rcx, [rbx]; P
0x14012b668  mov     eax, [rcx+4]
0x14012b66b  test    r12b, r12b
0x14012b66e  jnz     loc_14012B702
0x14012b674  test    al, 2
0x14012b676  jnz     loc_14012B85F
0x14012b67c  mov     rdx, rcx; Entry
0x14012b67f  bt      eax, 0Ah
0x14012b683  jnb     loc_14012B7AD
0x14012b689  lea     rcx, NtfsFcbIndexLookasideList; Lookaside
0x14012b690  call    cs:__imp_ExFreeToLookasideListEx
0x14012b697  nop     dword ptr [rax+rax+00h]
0x14012b69c  mov     [rbx], r15
0x14012b69f  add     rsp, 28h
0x14012b6a3  pop     r15
0x14012b6a5  pop     r14
0x14012b6a7  pop     r13
0x14012b6a9  pop     r12
0x14012b6ab  pop     rdi
0x14012b6ac  pop     rsi
0x14012b6ad  pop     rbp
0x14012b6ae  pop     rbx
0x14012b6af  retn
0x14012b6b1  mov     rcx, [rcx+30h]
0x14012b6b5  test    rcx, rcx
0x14012b6b8  jz      short loc_14012B6E1
0x14012b6ba  mov     eax, [rcx+90h]
0x14012b6c0  test    al, 1
0x14012b6c2  jnz     loc_14012B9B6
0x14012b6c8  mov     rax, [rdi+128h]
0x14012b6cf  mov     rcx, [rax+30h]; P
0x14012b6d3  mov     eax, [rcx+90h]
0x14012b6d9  test    al, 8
0x14012b6db  jz      loc_14012B9C0
0x14012b6e1  mov     rcx, [rdi+128h]; P
0x14012b6e8  xor     edx, edx; Tag
0x14012b6ea  call    cs:__imp_ExFreePoolWithTag
0x14012b6f1  nop     dword ptr [rax+rax+00h]
0x14012b6f6  mov     [rdi+128h], r15
  ... truncated ...
```
