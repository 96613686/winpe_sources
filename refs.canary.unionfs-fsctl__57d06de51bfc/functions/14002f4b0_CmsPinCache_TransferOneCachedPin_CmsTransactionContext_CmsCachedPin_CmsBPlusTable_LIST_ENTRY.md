# CmsPinCache::TransferOneCachedPin(CmsTransactionContext *,CmsCachedPin *,CmsBPlusTable *,_LIST_ENTRY *)

- ea: `0x14002f4b0`
- end: `0x14002fccd`
- name: `?TransferOneCachedPin@CmsPinCache@@QEAAEPEAVCmsTransactionContext@@PEAVCmsCachedPin@@PEAVCmsBPlusTable@@PEAU_LIST_ENTRY@@@Z`
- size: `2077`
- prototype: `unsigned __int8(CmsPinCache *__hidden this, struct CmsTransactionContext *, struct CmsCachedPin *, struct CmsBPlusTable *, struct _LIST_ENTRY *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002fce0`
- `0x1400325d0`
- `0x1400340e0`
- `0x14005f694`

## callees

- `0x1400169c0`
- `0x14002f250`
- `0x14002f3e0`
- `0x14002f4b0`
- `0x140031cf0`
- `0x14008fa30`
- `0x140093410`
- `0x14009a230`
- `0x14009e1f0`
- `0x1400c7a44`
- `0x1400c8574`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f99e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002f99e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002fbd0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002fc1f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002fbd0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002fc1f`
- `ntoskrnl!ExAllocatePool2` at `0x14002f7f1`
- `ntoskrnl!ExAllocatePool2` at `0x14002f8bb`
- `ntoskrnl!ExAllocatePool2` at `0x14002f7f1`
- `ntoskrnl!ExAllocatePool2` at `0x14002f8bb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002f7ae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002f876`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002f7ae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002f876`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f17ed`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f17ff`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f17ed`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f17ff`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002fa30`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002fa30`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401f1761`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1401f1761`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14002fc9f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f17b7`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f17db`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f18b9`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14002fc9f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f17b7`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f17db`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401f18b9`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x14002fa63`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x14002fa63`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1818`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1818`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002fbed`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002fc3c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002fbed`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002fc3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002fc78`

## string_xrefs

- `0x1401f1834`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
bool __fastcall CmsPinCache::TransferOneCachedPin(
        CmsPinCache *this,
        struct CmsTransactionContext *a2,
        struct CmsCachedPin *a3,
        struct CmsBPlusTable *a4,
        struct _LIST_ENTRY *a5)
{
  struct CmsCachedPin *v6; // rdi
  CmsPinCache *v8; // r13
  __int64 v9; // rdx
  __int64 v10; // rcx
  CmsPinCache *v11; // r15
  char *v12; // r12
  __int64 v13; // rcx
  char *v14; // rbx
  int v15; // ebp
  unsigned int v16; // r8d
  __int64 v17; // r13
  __int64 v18; // rcx
  CmsPinCache *v19; // rcx
  __int64 v20; // rdx
  unsigned int v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 Pool2; // rax
  _QWORD *v26; // r13
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rax
  const void *v30; // rdx
  __int64 v31; // rcx
  unsigned int v32; // eax
  struct _SLIST_ENTRY *v33; // r8
  __int64 v34; // rcx
  int v35; // ecx
  int v36; // ecx
  unsigned int v37; // r8d
  char *v38; // rcx
  char *v39; // rax
  CmsPinCache *v40; // rcx
  CmsPinCache **v41; // rdx
  char **v42; // rdx
  __int64 v43; // r13
  struct _NPAGED_LOOKASIDE_LIST *v44; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v45; // rcx
  _QWORD *v46; // rax
  __int64 v47; // rdx
  CmsCachedPin *v48; // rcx
  struct CmsCachedPin *v49; // rcx
  unsigned int v50; // r8d
  struct _LIST_ENTRY **v51; // r9
  unsigned __int64 v52; // rax
  __int64 v53; // rax
  unsigned int v54; // [rsp+20h] [rbp-68h]
  int v55; // [rsp+28h] [rbp-60h]
  __int64 v56; // [rsp+28h] [rbp-60h]
  unsigned int Size; // [rsp+30h] [rbp-58h]
  __int64 v58; // [rsp+38h] [rbp-50h]
  void *Src; // [rsp+40h] [rbp-48h]
  unsigned __int8 v61; // [rsp+A8h] [rbp+20h]

  v6 = a3;
  v8 = this;
  if ( !qword_140267160 )
    return 0;
  if ( !qword_140267158 )
    return 0;
  if ( CmsCachedPin::GlobalCachedPinPageCount >= qword_140267158 )
    return 0;
  if ( _bittest64((const signed __int64 *)a2, 0x31u) )
    return 0;
  if ( (*((_DWORD *)a3 + 26) & 2) != 0 )
    return 0;
  if ( (*((_DWORD *)a3 + 18) & 4) != 0 )
    return 0;
  v9 = *((_QWORD *)a3 + 4);
  if ( *((_DWORD *)a3 + 22) != *(_DWORD *)(v9 + 368) || *((_DWORD *)a3 + 23) != *(_DWORD *)(*((_QWORD *)a3 + 5) + 184LL) )
    return 0;
  v10 = *(_QWORD *)(v9 + 96);
  if ( *(_QWORD *)(v10 + 64) != v10 )
  {
    while ( (*(_BYTE *)(v10 + 15) & 8) == 0 )
    {
      if ( *(char *)(v10 + 12) >= 0 )
      {
        v10 = *(_QWORD *)(v10 + 64);
        if ( *(_QWORD *)(v10 + 64) != v10 )
          continue;
      }
      goto LABEL_10;
    }
    return 0;
  }
LABEL_10:
  if ( (*(_BYTE *)(v10 + 15) & 8) != 0
    || *(char *)(v10 + 12) < 0
    || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 24) + 72LL) + 3460LL) & 0x20000000) != 0 )
  {
    return 0;
  }
  v11 = (CmsPinCache *)(*((_QWORD *)a4 + 5) + 88LL);
  if ( *(_QWORD *)(v9 + 664) )
  {
    if ( (*(_DWORD *)(v9 + 552) & 0x80000) == 0 )
      return 0;
    v12 = (char *)a4 + 32;
    ExAcquireAutoExpandPushLockExclusive(*(_QWORD *)(*((_QWORD *)a4 + 4) + 40LL), 2);
    _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)v6 + 4) + 552LL), 0xFFF7FFFF);
    v48 = *(CmsCachedPin **)(*((_QWORD *)v6 + 4) + 664LL);
    if ( v48 )
    {
      if ( !CmsCachedPin::ShouldDoomCachedPin(v48) )
      {
        CmsPinCache::PromoteCachedPin(v11, v49, v50);
        ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)v12 + 40LL), 2);
        return 0;
      }
      CmsPinCache::DoomCachedPin(v11, v49, a5, v51);
    }
    ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)v12 + 40LL), 2);
  }
  else
  {
    v12 = (char *)a4 + 32;
  }
  v13 = *((_QWORD *)v6 + 5);
  if ( !*(_DWORD *)(v13 + 124) && (int)CmsBPlusTable::EnqueueTreeUpdate(v13, a2, 0) < 0 )
    return 0;
  if ( (*((_DWORD *)v6 + 26) & 8) == 0 )
  {
    v14 = 0;
    goto LABEL_81;
  }
  if ( v11 == (struct CmsTransactionContext *)((char *)a2 + 824) )
  {
    v61 = 1;
    if ( !*((_BYTE *)a2 + 135) )
    {
      v14 = (char *)a2 + 2656;
      v15 = 0;
      if ( a2 == (struct CmsTransactionContext *)-2656LL )
      {
        v14 = 0;
      }
      else
      {
        *(_QWORD *)v14 = 0;
        *((_QWORD *)a2 + 333) = 0;
        *((_DWORD *)a2 + 682) |= 3u;
        *((_QWORD *)a2 + 338) = 0;
        *((_QWORD *)a2 + 339) = 0;
        *((_QWORD *)a2 + 340) = 0;
        *((_DWORD *)a2 + 690) = 0;
        *((_QWORD *)a2 + 349) = 0;
        *((_QWORD *)a2 + 335) = (char *)a2 + 2672;
        *((_QWORD *)a2 + 334) = (char *)a2 + 2672;
        *((_QWORD *)a2 + 333) = 0;
        *(_QWORD *)v14 = 0;
        *(_QWORD *)((char *)a2 + 2804) = 0;
      }
      *((_DWORD *)v14 + 26) |= 8u;
      *((_BYTE *)a2 + 135) = 1;
      *((_QWORD *)v14 + 17) = a2;
      goto LABEL_22;
    }
  }
  else
  {
    v61 = 0;
  }
  v15 = 0;
  v23 = qword_140262438 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( *(_DWORD *)v23 < 0xC0u )
  {
    v23 = 0;
    v24 = 208;
LABEL_39:
    Pool2 = ExAllocatePool2(66, v24, 1766871885);
    if ( (Pool2 & 0xF) != 0 )
      goto LABEL_131;
    if ( !Pool2 )
      return 0;
    goto LABEL_99;
  }
  if ( !*(_BYTE *)(v23 + 8) )
  {
    if ( (int)*(_QWORD *)(v23 + 88) > (int)HIDWORD(*(_QWORD *)(v23 + 88)) )
    {
      v36 = _InterlockedDecrement((volatile signed __int32 *)(v23 + 88));
      if ( v36 >= *(_DWORD *)(v23 + 92) && v36 >= 0 )
      {
        Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v23 + 64));
        goto LABEL_98;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v23 + 88));
    }
LABEL_78:
    v24 = *(unsigned int *)(v23 + 4);
    goto LABEL_39;
  }
  v44 = (struct _NPAGED_LOOKASIDE_LIST *)(v23 + 64);
  if ( *(_BYTE *)(v23 + 9) )
    Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v44);
  else
    Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v44);
LABEL_98:
  if ( !Pool2 )
    goto LABEL_78;
LABEL_99:
  v43 = Pool2 + 16;
  *(_QWORD *)Pool2 = v23;
  if ( Pool2 == -16 )
    return 0;
  memset((void *)(Pool2 + 16), 0, 0xC0u);
  v14 = (char *)(v43 + 32);
  *(_BYTE *)(v43 + 26) = 32;
  if ( v43 == -32 )
  {
    v14 = 0;
  }
  else
  {
    *(_DWORD *)(v43 + 104) |= 3u;
    *(_QWORD *)(v43 + 56) = v43 + 48;
    *(_QWORD *)(v43 + 48) = v43 + 48;
    *(_QWORD *)(v43 + 180) = 0;
  }
  *((_QWORD *)v14 + 16) = v43;
LABEL_22:
  if ( !v14 )
    return 0;
  v16 = *((_DWORD *)v14 + 26);
  v54 = v16;
  if ( *((_QWORD *)v14 + 6) )
  {
    CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)(v14 + 48));
    v16 = v54;
  }
  *((_OWORD *)v14 + 3) = 0;
  *((_OWORD *)v14 + 4) = 0;
  *((_DWORD *)v14 + 18) |= 3u;
  v17 = *((unsigned int *)v6 + 14);
  Size = v17;
  if ( !(_DWORD)v17 )
    goto LABEL_26;
  Src = (void *)*((_QWORD *)v6 + 6);
  if ( !*((_BYTE *)a2 + 129) && (unsigned int)v17 <= 0x60 )
  {
    *((_BYTE *)a2 + 129) = 1;
    v26 = (_QWORD *)((char *)a2 + 2560);
    v55 = 96;
    v15 = 8;
    goto LABEL_57;
  }
  v27 = qword_140262420 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v56 = v27;
  if ( (unsigned int)v17 > *(_DWORD *)v27 )
  {
    v56 = 0;
    v28 = v17 + 16;
    goto LABEL_51;
  }
  if ( *(_BYTE *)(v27 + 8) )
  {
    v45 = (struct _NPAGED_LOOKASIDE_LIST *)(v27 + 64);
    if ( *(_BYTE *)(v27 + 9) )
      v46 = ExAllocateFromNPagedLookasideList(v45);
    else
      v46 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v45);
    goto LABEL_54;
  }
  if ( (int)*(_QWORD *)(v27 + 88) > (int)HIDWORD(*(_QWORD *)(v27 + 88)) )
  {
    v35 = _InterlockedDecrement((volatile signed __int32 *)(v27 + 88));
    if ( v35 >= *(_DWORD *)(v27 + 92) && v35 >= 0 )
    {
      v46 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v27 + 64));
LABEL_54:
      v26 = v46;
      if ( v46 )
      {
LABEL_55:
        *v26 = v56;
        v26 += 2;
        goto LABEL_56;
      }
      v27 = v56;
      goto LABEL_73;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v27 + 88));
  }
LABEL_73:
  v28 = *(unsigned int *)(v27 + 4);
LABEL_51:
  v29 = ExAllocatePool2(66, v28, 1766871885);
  v26 = (_QWORD *)v29;
  if ( (v29 & 0xF) != 0 )
LABEL_131:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v29 )
    goto LABEL_55;
LABEL_56:
  v55 = Size;
LABEL_57:
  if ( !v26 )
  {
    CmsCachedPin::Destroy((struct CmsCachedPin *)v14);
    return 0;
  }
  v30 = (const void *)*((_QWORD *)v14 + 6);
  if ( v30 )
  {
    memmove(v26, v30, *((unsigned int *)v14 + 14));
    v31 = *((_QWORD *)v14 + 6);
    if ( (*((_DWORD *)v14 + 18) & 8) != 0 )
    {
      *(_BYTE *)(v31 - 2431) = 0;
      *((_DWORD *)v14 + 18) &= ~8u;
    }
    else if ( v31 )
    {
      v33 = (struct _SLIST_ENTRY *)(v31 - 16);
      v34 = *(_QWORD *)(v31 - 16);
      v58 = v34;
      if ( !v34 )
        goto LABEL_117;
      if ( *(_BYTE *)(v34 + 8) )
      {
        if ( *(_BYTE *)(v34 + 9) )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v34 + 64), v33);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v34 + 64), v33);
        goto LABEL_61;
      }
      v47 = *(_QWORD *)(v34 + 88);
      if ( (int)v47 < *(_DWORD *)(v34 + 80) || SHIDWORD(v47) >= (int)v47 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v34 + 64), v33);
        _InterlockedIncrement((volatile signed __int32 *)(v58 + 88));
      }
      else
      {
LABEL_117:
        ExFreePoolWithTag(v33, 0);
      }
    }
  }
LABEL_61:
  v32 = *((_DWORD *)v14 + 18) & 0xFFFFFFF7;
  *((_QWORD *)v14 + 6) = v26;
  *((_DWORD *)v14 + 18) = v15 | v32;
  *((_DWORD *)v14 + 14) = v55;
  if ( Src )
    memmove(v26, Src, Size);
  v16 = v54;
LABEL_26:
  *((_DWORD *)v14 + 15) = *((_DWORD *)v6 + 15);
  *((_DWORD *)v14 + 16) = *((_DWORD *)v6 + 16);
  *((_WORD *)v14 + 34) = *((_WORD *)v6 + 34);
  *((_WORD *)v14 + 35) = *((_WORD *)v6 + 35);
  *((_DWORD *)v14 + 18) = *((_DWORD *)v6 + 18) ^ (*((_DWORD *)v14 + 18) ^ *((_DWORD *)v6 + 18)) & 8;
  v18 = *((_QWORD *)v6 + 4);
  *((_QWORD *)v14 + 4) = v18;
  *((_QWORD *)v14 + 5) = *((_QWORD *)v6 + 5);
  *((_QWORD *)v14 + 10) = *((_QWORD *)v6 + 10);
  *((_DWORD *)v14 + 22) = *((_DWORD *)v6 + 22);
  *((_DWORD *)v14 + 23) = *((_DWORD *)v6 + 23);
  *((_QWORD *)v14 + 12) = *((_QWORD *)v6 + 12);
  *((_QWORD *)v14 + 14) = *((_QWORD *)v6 + 14);
  *((_QWORD *)v14 + 15) = *((_QWORD *)v6 + 15);
  v14[144] = *((_BYTE *)v6 + 144);
  _InterlockedIncrement((volatile signed __int32 *)(v18 + 380));
  if ( v61 )
  {
    v19 = v11;
    if ( *((_BYTE *)v6 + 144) )
      v19 = (CmsPinCache *)((char *)v11 + 16);
    v20 = *(_QWORD *)v19;
    if ( *(CmsPinCache **)(*(_QWORD *)v19 + 8LL) != v19 )
      goto LABEL_30;
    *((_QWORD *)v14 + 2) = v20;
    *((_QWORD *)v14 + 3) = v19;
    *(_QWORD *)(v20 + 8) = v14 + 16;
    *(_QWORD *)v19 = v14 + 16;
    if ( *((_BYTE *)v6 + 144) )
      ++*((_DWORD *)v11 + 9);
    else
      ++*((_DWORD *)v11 + 8);
  }
  v12 = (char *)a4 + 32;
  v8 = this;
  v22 = *((_DWORD *)v6 + 26) & 0xFFFFFFFD;
  v6 = (struct CmsCachedPin *)v14;
  *((_DWORD *)v14 + 26) = (v22 | (2 * v61))
                        & 0xFFFFFFEB
                        ^ (((unsigned __int8)v22 | (unsigned __int8)(2 * v61))
                         & 0xEB
                         ^ (unsigned __int8)(8 * (v16 >> 3)))
                        & 8;
LABEL_81:
  if ( (int)CmsKeyRange::EnsureBuffersAreNotTransactionPrivate((struct CmsCachedPin *)((char *)v6 + 48)) < 0 )
    goto LABEL_120;
  if ( !(unsigned __int8)ExTryAcquireAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)v12 + 40LL), 2) )
  {
    _InterlockedIncrement(&dword_140261EEC);
    goto LABEL_120;
  }
  _InterlockedIncrement(&dword_140261EE8);
  if ( CmsCachedPin::ShouldDoomCachedPin(v6) || *(_QWORD *)(*((_QWORD *)v6 + 4) + 664LL) )
  {
    ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)v12 + 40LL), 2);
LABEL_120:
    if ( v14 )
    {
      CmsCachedPin::Unpin((CmsCachedPin *)v14, a2);
      CmsCachedPin::Destroy((struct CmsCachedPin *)v14);
    }
    return 0;
  }
  v38 = (char *)*((_QWORD *)v6 + 2);
  v39 = (char *)v6 + 16;
  if ( v38 != (char *)v6 + 16 )
  {
    if ( *((char **)v38 + 1) != v39 )
      goto LABEL_30;
    v42 = (char **)*((_QWORD *)v6 + 3);
    if ( *v42 != v39 )
      goto LABEL_30;
    *v42 = v38;
    *((_QWORD *)v38 + 1) = v42;
    if ( *((_BYTE *)v6 + 144) )
      --*((_DWORD *)v8 + 9);
    else
      --*((_DWORD *)v8 + 8);
  }
  v40 = v11;
  *(_QWORD *)(*((_QWORD *)v6 + 4) + 664LL) = v6;
  if ( *((_BYTE *)v6 + 144) )
    v40 = (CmsPinCache *)((char *)v11 + 16);
  v41 = (CmsPinCache **)*((_QWORD *)v40 + 1);
  if ( *v41 != v40 )
LABEL_30:
    __fastfail(3u);
  *((_QWORD *)v6 + 2) = v40;
  *((_QWORD *)v6 + 3) = v41;
  *v41 = (struct CmsCachedPin *)((char *)v6 + 16);
  *((_QWORD *)v40 + 1) = (char *)v6 + 16;
  if ( *((_BYTE *)v6 + 144) )
    ++*((_DWORD *)v11 + 9);
  else
    ++*((_DWORD *)v11 + 8);
  CmsPinCache::PromoteCachedPin(v11, v6, v37);
  _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)v6 + 4) + 552LL), 0xFFF7FFFF);
  v52 = *(_DWORD *)(*((_QWORD *)a2 + 1) + 3396LL) >> 12;
  *((_DWORD *)v6 + 38) = v52;
  _InterlockedAdd64(&CmsCachedPin::GlobalCachedPinPageCount, v52);
  v53 = *((_QWORD *)v6 + 4);
  *((_DWORD *)v6 + 26) |= 0x10u;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v53 + 96) + 108LL));
  CmsPinCache::InsertCachedPinIntoIndex(v11, a2, v6, a5);
  ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(*((_QWORD *)a4 + 4) + 40LL), 2);
  return !v14;
}

```

## disassembly

```asm
0x14002f4b0  mov     [rsp+arg_8], rbx
0x14002f4b5  mov     [rsp+arg_0], rcx
0x14002f4ba  push    rbp
0x14002f4bb  push    rsi
0x14002f4bc  push    rdi
0x14002f4bd  push    r12
0x14002f4bf  push    r13
0x14002f4c1  push    r14
0x14002f4c3  push    r15
0x14002f4c5  sub     rsp, 50h
0x14002f4c9  cmp     cs:qword_140267160, 0
0x14002f4d1  mov     r14, r9
0x14002f4d4  mov     rdi, r8
0x14002f4d7  mov     rsi, rdx
0x14002f4da  mov     r13, rcx
0x14002f4dd  jz      loc_14002F72D
0x14002f4e3  mov     rax, cs:qword_140267158
0x14002f4ea  test    rax, rax
0x14002f4ed  jz      loc_14002F72D
0x14002f4f3  cmp     cs:?GlobalCachedPinPageCount@CmsCachedPin@@2_JA, rax; __int64 CmsCachedPin::GlobalCachedPinPageCount
0x14002f4fa  jge     loc_14002F72D
0x14002f500  bt      qword ptr [rdx], 31h ; '1'
0x14002f505  jb      loc_14002F72D
0x14002f50b  mov     eax, [r8+68h]
0x14002f50f  test    al, 2
0x14002f511  jnz     loc_14002F72D
0x14002f517  mov     eax, [r8+48h]
0x14002f51b  test    al, 4
0x14002f51d  jnz     loc_14002F72D
0x14002f523  mov     rdx, [r8+20h]
0x14002f527  mov     eax, [rdx+170h]
0x14002f52d  cmp     [r8+58h], eax
0x14002f531  jnz     loc_14002F72D
0x14002f537  mov     rax, [r8+28h]
0x14002f53b  mov     ecx, [rax+0B8h]
0x14002f541  cmp     [r8+5Ch], ecx
0x14002f545  jnz     loc_14002F72D
0x14002f54b  mov     rcx, [rdx+60h]
0x14002f54f  cmp     [rcx+40h], rcx
0x14002f553  jnz     loc_14002F850
0x14002f559  test    byte ptr [rcx+0Fh], 8
0x14002f55d  jnz     loc_14002F72D
0x14002f563  cmp     byte ptr [rcx+0Ch], 0
0x14002f567  jl      loc_14002F72D
0x14002f56d  mov     rax, [rcx+18h]
0x14002f571  mov     rcx, [rax+48h]
0x14002f575  test    dword ptr [rcx+0D84h], 20000000h
0x14002f57f  jnz     loc_14002F72D
0x14002f585  mov     r15, [r9+28h]
0x14002f589  add     r15, 58h ; 'X'
0x14002f58d  cmp     qword ptr [rdx+298h], 0
0x14002f595  jnz     loc_1401F1740
0x14002f59b  lea     r12, [r9+20h]
0x14002f59f  mov     rcx, [rdi+28h]
0x14002f5a3  cmp     dword ptr [rcx+7Ch], 0
0x14002f5a7  jz      loc_14002FBAA
0x14002f5ad  mov     eax, [rdi+68h]
0x14002f5b0  test    al, 8
0x14002f5b2  jz      loc_14002FA41
0x14002f5b8  lea     rax, [rsi+338h]
0x14002f5bf  cmp     r15, rax
0x14002f5c2  jnz     loc_14002F7A4
0x14002f5c8  cmp     byte ptr [rsi+87h], 0
0x14002f5cf  mov     [rsp+88h+arg_18], 1
0x14002f5d7  jnz     loc_14002F7AC
0x14002f5dd  lea     rbx, [rsi+0A60h]
0x14002f5e4  xor     ebp, ebp
0x14002f5e6  test    rbx, rbx
0x14002f5e9  jz      loc_14002FAF5
0x14002f5ef  mov     [rbx], rbp
0x14002f5f2  lea     rax, [rbx+10h]
0x14002f5f6  mov     [rbx+8], rbp
0x14002f5fa  or      dword ptr [rbx+48h], 3
0x14002f5fe  mov     [rbx+30h], rbp
0x14002f602  mov     [rbx+38h], rbp
0x14002f606  mov     [rbx+40h], rbp
0x14002f60a  mov     [rbx+68h], ebp
0x14002f60d  mov     [rbx+88h], rbp
0x14002f614  mov     [rax+8], rax
0x14002f618  mov     [rax], rax
0x14002f61b  mov     [rbx+8], rbp
0x14002f61f  mov     [rbx], rbp
0x14002f622  mov     [rbx+94h], rbp
0x14002f629  or      dword ptr [rbx+68h], 8
0x14002f62d  mov     byte ptr [rsi+87h], 1
0x14002f634  mov     [rbx+88h], rsi
0x14002f63b  test    rbx, rbx
0x14002f63e  jz      loc_14002F72D
0x14002f644  cmp     qword ptr [rbx+30h], 0
0x14002f649  mov     r8d, [rbx+68h]
0x14002f64d  mov     [rsp+88h+var_68], r8d
0x14002f652  jnz     loc_14002FBFE
0x14002f658  xorps   xmm0, xmm0
0x14002f65b  movups  xmmword ptr [rbx+30h], xmm0
0x14002f65f  movups  xmmword ptr [rbx+40h], xmm0
0x14002f663  or      dword ptr [rbx+48h], 3
0x14002f667  mov     r13d, [rdi+38h]
0x14002f66b  mov     dword ptr [rsp+88h+Size], r13d
0x14002f670  test    r13d, r13d
0x14002f673  jnz     loc_14002F813
0x14002f679  mov     eax, [rdi+3Ch]
0x14002f67c  mov     [rbx+3Ch], eax
0x14002f67f  mov     eax, [rdi+40h]
0x14002f682  mov     [rbx+40h], eax
0x14002f685  movzx   eax, word ptr [rdi+44h]
0x14002f689  mov     [rbx+44h], ax
0x14002f68d  movzx   eax, word ptr [rdi+46h]
0x14002f691  mov     [rbx+46h], ax
0x14002f695  mov     eax, [rdi+48h]
0x14002f698  mov     ecx, eax
0x14002f69a  xor     ecx, [rbx+48h]
0x14002f69d  and     ecx, 8
0x14002f6a0  xor     ecx, eax
0x14002f6a2  mov     [rbx+48h], ecx
0x14002f6a5  mov     rcx, [rdi+20h]
0x14002f6a9  mov     [rbx+20h], rcx
0x14002f6ad  mov     rax, [rdi+28h]
0x14002f6b1  mov     [rbx+28h], rax
0x14002f6b5  mov     rax, [rdi+50h]
0x14002f6b9  mov     [rbx+50h], rax
0x14002f6bd  mov     eax, [rdi+58h]
0x14002f6c0  mov     [rbx+58h], eax
0x14002f6c3  mov     eax, [rdi+5Ch]
0x14002f6c6  mov     [rbx+5Ch], eax
0x14002f6c9  mov     rax, [rdi+60h]
0x14002f6cd  mov     [rbx+60h], rax
0x14002f6d1  mov     rax, [rdi+70h]
0x14002f6d5  mov     [rbx+70h], rax
0x14002f6d9  mov     rax, [rdi+78h]
0x14002f6dd  mov     [rbx+78h], rax
0x14002f6e1  movzx   eax, byte ptr [rdi+90h]
0x14002f6e8  mov     [rbx+90h], al
0x14002f6ee  nop
0x14002f6ef  lock inc dword ptr [rcx+17Ch]
0x14002f6f6  movzx   r9d, [rsp+88h+arg_18]
0x14002f6ff  nop
0x14002f700  test    r9b, r9b
0x14002f703  jz      short loc_14002F76B
0x14002f705  cmp     byte ptr [rdi+90h], 0
0x14002f70c  mov     rcx, r15
0x14002f70f  jz      short loc_14002F715
0x14002f711  lea     rcx, [r15+10h]
0x14002f715  mov     rdx, [rcx]
0x14002f718  cmp     [rdx+8], rcx
0x14002f71c  jz      short loc_14002F748
0x14002f71e  mov     ecx, 3
0x14002f723  int     29h; Win8: RtlFailFast(ecx)
0x14002f725  mov     rcx, rbx; struct CmsCachedPin *
0x14002f728  call    ?Destroy@CmsCachedPin@@SAXPEAV1@@Z; CmsCachedPin::Destroy(CmsCachedPin *)
0x14002f72d  xor     al, al
0x14002f72f  mov     rbx, [rsp+88h+arg_8]
0x14002f737  add     rsp, 50h
0x14002f73b  pop     r15
0x14002f73d  pop     r14
0x14002f73f  pop     r13
0x14002f741  pop     r12
0x14002f743  pop     rdi
0x14002f744  pop     rsi
0x14002f745  pop     rbp
0x14002f746  retn
0x14002f748  lea     rax, [rbx+10h]
0x14002f74c  mov     [rax], rdx
0x14002f74f  mov     [rax+8], rcx
0x14002f753  mov     [rdx+8], rax
0x14002f757  mov     [rcx], rax
0x14002f75a  cmp     byte ptr [rdi+90h], 0
0x14002f761  jnz     loc_14002FC89
0x14002f767  inc     dword ptr [r15+20h]
0x14002f76b  mov     eax, [rdi+68h]
0x14002f76e  lea     r12, [r14+20h]
0x14002f772  mov     r13, [rsp+88h+arg_0]
0x14002f77a  and     eax, 0FFFFFFFDh
0x14002f77d  shr     r8d, 3
0x14002f781  mov     ecx, r9d
0x14002f784  add     ecx, ecx
0x14002f786  mov     rdi, rbx
0x14002f789  or      ecx, eax
0x14002f78b  movzx   eax, r8b
0x14002f78f  shl     eax, 3
0x14002f792  and     ecx, 0FFFFFFEBh
0x14002f795  xor     eax, ecx
0x14002f797  and     eax, 8
0x14002f79a  xor     eax, ecx
0x14002f79c  mov     [rbx+68h], eax
0x14002f79f  jmp     loc_14002FA45
0x14002f7a4  mov     [rsp+88h+arg_18], 0
0x14002f7ac  xor     ecx, ecx; ProcNumber
0x14002f7ae  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002f7b5  nop     dword ptr [rax+rax+00h]
0x14002f7ba  xor     edx, edx
0x14002f7bc  xor     ebp, ebp
0x14002f7be  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14002f7c4  lea     rbx, [rdx+rdx*2]
0x14002f7c8  shl     rbx, 6
0x14002f7cc  add     rbx, cs:qword_140262438
0x14002f7d3  cmp     dword ptr [rbx], 0C0h
0x14002f7d9  jnb     loc_14002F9EC
0x14002f7df  mov     ebx, ebp
0x14002f7e1  mov     edx, 0D0h
0x14002f7e6  mov     ecx, 42h ; 'B'
0x14002f7eb  mov     r8d, 6950534Dh
0x14002f7f1  call    cs:__imp_ExAllocatePool2
0x14002f7f8  nop     dword ptr [rax+rax+00h]
0x14002f7fd  test    al, 0Fh
0x14002f7ff  jnz     loc_1401F1834
0x14002f805  test    rax, rax
0x14002f808  jz      loc_14002F72D
0x14002f80e  jmp     loc_14002FB55
0x14002f813  cmp     byte ptr [rsi+81h], 0
0x14002f81a  mov     rax, [rdi+30h]
0x14002f81e  mov     [rsp+88h+Src], rax
0x14002f823  jnz     short loc_14002F874
0x14002f825  cmp     r13d, 60h ; '`'
0x14002f829  ja      short loc_14002F874
0x14002f82b  mov     byte ptr [rsi+81h], 1
0x14002f832  lea     r13, [rsi+0A00h]
0x14002f839  mov     dword ptr [rsp+88h+var_60], 60h ; '`'
0x14002f841  mov     ebp, 8
0x14002f846  jmp     loc_14002F8FA
0x14002f850  test    byte ptr [rcx+0Fh], 8
0x14002f854  jnz     loc_14002F72D
0x14002f85a  cmp     byte ptr [rcx+0Ch], 0
0x14002f85e  jl      loc_14002F559
0x14002f864  mov     rcx, [rcx+40h]
0x14002f868  cmp     [rcx+40h], rcx
0x14002f86c  jz      loc_14002F559
0x14002f872  jmp     short loc_14002F850
0x14002f874  xor     ecx, ecx; ProcNumber
0x14002f876  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002f87d  nop     dword ptr [rax+rax+00h]
0x14002f882  xor     edx, edx
0x14002f884  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14002f88a  lea     rdx, [rdx+rdx*2]
0x14002f88e  shl     rdx, 6
0x14002f892  add     rdx, cs:qword_140262420
0x14002f899  mov     [rsp+88h+var_60], rdx
0x14002f89e  cmp     r13d, [rdx]
0x14002f8a1  jbe     loc_14002F9AC
0x14002f8a7  mov     [rsp+88h+var_60], rbp
0x14002f8ac  lea     rdx, [r13+10h]
0x14002f8b0  mov     ecx, 42h ; 'B'
0x14002f8b5  mov     r8d, 6950534Dh
0x14002f8bb  call    cs:__imp_ExAllocatePool2
0x14002f8c2  nop     dword ptr [rax+rax+00h]
0x14002f8c7  mov     r13, rax
0x14002f8ca  test    al, 0Fh
0x14002f8cc  jnz     loc_1401F1834
0x14002f8d2  test    rax, rax
0x14002f8d5  jz      short loc_14002F8F2
0x14002f8d7  jmp     short loc_14002F8E5
0x14002f8d9  mov     r13, rax
0x14002f8dc  test    rax, rax
0x14002f8df  jz      loc_14002FC4D
0x14002f8e5  mov     rax, [rsp+88h+var_60]
0x14002f8ea  mov     [r13+0], rax
0x14002f8ee  add     r13, 10h
0x14002f8f2  mov     eax, dword ptr [rsp+88h+Size]
0x14002f8f6  mov     dword ptr [rsp+88h+var_60], eax
0x14002f8fa  test    r13, r13
0x14002f8fd  jz      loc_14002F725
0x14002f903  mov     rdx, [rbx+30h]; Src
0x14002f907  test    rdx, rdx
0x14002f90a  jz      short loc_14002F92E
0x14002f90c  mov     r8d, [rbx+38h]; Size
0x14002f910  mov     rcx, r13; void *
0x14002f913  call    memmove
0x14002f918  mov     eax, [rbx+48h]
0x14002f91b  mov     rcx, [rbx+30h]
0x14002f91f  test    al, 8
0x14002f921  jz      short loc_14002F968
0x14002f923  mov     byte ptr [rcx-97Fh], 0
0x14002f92a  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x14002f92e  mov     eax, [rbx+48h]
0x14002f931  and     eax, 0FFFFFFF7h
0x14002f934  mov     [rbx+30h], r13
0x14002f938  or      eax, ebp
0x14002f93a  mov     [rbx+48h], eax
0x14002f93d  mov     eax, dword ptr [rsp+88h+var_60]
0x14002f941  mov     [rbx+38h], eax
0x14002f944  mov     rax, [rsp+88h+Src]
0x14002f949  test    rax, rax
0x14002f94c  jz      short loc_14002F95E
0x14002f94e  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x14002f953  mov     rdx, rax; Src
0x14002f956  mov     rcx, r13; void *
0x14002f959  call    memmove
0x14002f95e  mov     r8d, [rsp+88h+var_68]
0x14002f963  jmp     loc_14002F679
0x14002f968  test    rcx, rcx
0x14002f96b  jz      short loc_14002F92E
0x14002f96d  lea     r8, [rcx-10h]
0x14002f971  mov     rcx, [rcx-10h]
0x14002f975  mov     [rsp+88h+var_50], rcx
0x14002f97a  test    rcx, rcx
0x14002f97d  jz      loc_14002FC73
0x14002f983  cmp     byte ptr [rcx+8], 0
0x14002f987  jz      loc_14002FC57
0x14002f98d  cmp     byte ptr [rcx+9], 0
0x14002f991  mov     rdx, r8; Entry
0x14002f994  jz      loc_14002FA2C
  ... truncated ...
```
