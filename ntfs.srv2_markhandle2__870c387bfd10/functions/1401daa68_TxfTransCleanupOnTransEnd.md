# TxfTransCleanupOnTransEnd

- ea: `0x1401daa68`
- end: `0x1401db15c`
- name: `TxfTransCleanupOnTransEnd`
- size: `1780`
- prototype: ``
- caller_count: `5`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400bbf04`
- `0x140133f30`
- `0x1401d2f50`
- `0x1401d60b8`
- `0x1401da21c`

## callees

- `0x140010be0`
- `0x140037120`
- `0x140038f8c`
- `0x14004173c`
- `0x1400f86cc`
- `0x140140f5c`
- `0x1401c2ae8`
- `0x1401d4f40`
- `0x1401d9484`
- `0x1401d9690`
- `0x1401d96c4`
- `0x1401d973c`
- `0x1401daa68`
- `0x1401db164`
- `0x1401db588`
- `0x1401dbdd4`
- `0x14028a9c0`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402cd5a6`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402cd5a6`
- `ntoskrnl!qsort` at `0x1401dab36`
- `ntoskrnl!qsort` at `0x1401dab36`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401daf83`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dafdc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401db031`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cd535`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401daf83`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401dafdc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401db031`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cd535`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401dab8f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd555`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd5ff`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401dab8f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd555`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402cd5ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401dac54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db051`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db08e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401dac54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db051`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401db08e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401daae7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401db0d9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402cd5d5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401daae7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401db0d9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402cd5d5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dab05`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dab63`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dab05`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401dab63`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401daf15`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401daf15`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401daf30`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401daf30`

## pseudocode

```c
void __fastcall TxfTransCleanupOnTransEnd(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  __int64 v5; // r14
  unsigned int v6; // ebp
  int v7; // r13d
  void *v10; // rcx
  _QWORD **v11; // r15
  _QWORD *i; // rbx
  _QWORD *v13; // rsi
  __int64 v14; // rbx
  unsigned int j; // ebx
  __int64 v16; // rcx
  _QWORD *v17; // r12
  _QWORD *v18; // rsi
  int v19; // r15d
  _DWORD *v20; // rax
  _QWORD *v21; // rdx
  void *v22; // rcx
  __int64 v23; // rbp
  __int64 v24; // r12
  int v25; // eax
  __int64 k; // rbx
  __int64 v27; // rax
  __int64 v28; // rbx
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rbp
  _QWORD *v32; // rcx
  _QWORD *v33; // r8
  _QWORD *v34; // rdx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  _QWORD **v37; // rbx
  _QWORD *v38; // rdx
  int v39; // r8d
  _QWORD **v40; // rdi
  __int64 v41; // rax
  __int64 v42; // rax
  _QWORD *v43; // rcx
  __int64 v44; // rcx
  _QWORD *v45; // rax
  _QWORD *v46; // rbx
  _QWORD *v47; // rax
  void *v48; // rcx
  _QWORD *v49; // rbx
  __int64 v50; // r8
  void *v51; // r15
  _QWORD *v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rdx
  void *v55; // rbx
  struct _FAST_MUTEX *v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // [rsp+20h] [rbp-58h]
  _QWORD *v61; // [rsp+30h] [rbp-48h]
  __int64 v63; // [rsp+88h] [rbp+10h]

  v5 = *(_QWORD *)(a2 + 208);
  v6 = 0;
  v63 = 0;
  v60 = 0;
  v7 = a3;
  if ( (_DWORD)a3 || a4 )
    TxfTransCleanupTxfWriterInformation(a1, a2, 1);
  v10 = *(void **)(a2 + 400);
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0);
    *(_QWORD *)(a2 + 400) = 0;
    *(_WORD *)(a2 + 412) = 0;
    *(_WORD *)(a2 + 408) = 0;
  }
  LOBYTE(a3) = 1;
  TxfCloseHandlesForTransaction(a1, a2, a3);
  TxfCleanupNoRenameListAtEndOfTrans(a2);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 24) + 96LL));
  v11 = (_QWORD **)(a2 + 192);
  for ( i = *(_QWORD **)(a2 + 192); i != v11; i = (_QWORD *)*i )
    ExAcquireResourceExclusiveLite((PERESOURCE)i[8], 1u);
  v13 = (_QWORD *)(a2 + 144);
  qsort(*(void **)(a2 + 144), *(unsigned int *)(a2 + 152), 0x10u, TxfCompareTxfScbPtrForDirNotify);
  if ( *(_DWORD *)(a2 + 152) )
  {
    do
    {
      v14 = *(_QWORD *)(*v13 + 16LL * v6);
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v14 + 64) + 136LL), 1u);
      TxfDeleteIsoNamesForTransaction(a1, v14, a2);
      ++v6;
    }
    while ( v6 < *(_DWORD *)(a2 + 152) );
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 24) + 96LL));
  for ( j = 0; j < *(_DWORD *)(a2 + 152); ++j )
    TxfDereferenceTxfScb(*(PVOID *)(*v13 + 16LL * j));
  TxfSortedArrayDeallocate(a2 + 144);
  v17 = *v11;
  v61 = *v11;
  if ( *v11 != v11 )
  {
    do
    {
      v18 = v17 - 9;
      v19 = *((_DWORD *)v17 - 17);
      *((_DWORD *)v18 + 5) = 0;
      *((_DWORD *)v18 + 1) = v19 & 0xE9F80603;
      if ( v7 )
      {
        if ( (v19 & 0x200000) == 0 && (v19 & 0x80000) != 0 )
        {
          *((_DWORD *)v18 + 1) = v19 & 0xE9F00603;
          *(_QWORD *)(v18[6] + 48LL) = 0;
        }
      }
      else
      {
        v49 = v18 + 6;
        if ( (v19 & 0x100000) != 0 )
        {
          ExFreePoolWithTag(*(PVOID *)(*v49 + 56LL), 0);
          *(_OWORD *)(*v49 + 48LL) = 0;
        }
        if ( (*((_DWORD *)v18 + 1) & 0x80000) != 0 )
          *(_QWORD *)(*v49 + 48LL) = 0;
        *((_DWORD *)v18 + 1) &= 0xFFE7FFFF;
      }
      if ( v18[8] )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 16) + 6312LL));
        while ( 1 )
        {
          v52 = (_QWORD *)v18[8];
          if ( !v52 )
            break;
          if ( *v52 )
          {
            LOBYTE(v50) = 1;
            *(_QWORD *)(*v52 + 16LL) -= v52[1];
            TxfDereferenceTxfQuotaControlBlock(*(_QWORD *)(v5 + 16), *v52, v50);
          }
          v18[8] = v52[2];
          ExFreeToLookasideListEx(&TxfFcbQuotaInfoLookasideList, v52);
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 16) + 6312LL));
      }
      v20 = (_DWORD *)v18[6];
      if ( v20 )
      {
        *v20 = 0;
        *(CLFS_LSN *)(v18[6] + 40LL) = CLFS_LSN_INVALID_EXT;
      }
      TxfDeleteSavedDeletedLinkList(v17 - 9);
      if ( (v19 & 8) != 0 )
      {
        v21 = (_QWORD *)v18[11];
        if ( !*((_WORD *)v21 + 38) )
        {
          v44 = *v21;
          if ( *(_QWORD **)(*v21 + 8LL) != v21 )
            goto LABEL_72;
          v45 = (_QWORD *)v21[1];
          if ( (_QWORD *)*v45 != v21 )
            goto LABEL_72;
          *v45 = v44;
          *(_QWORD *)(v44 + 8) = v45;
          ExFreeToLookasideListEx(&TxfFcbInfoLookasideList, v21);
        }
      }
      v22 = (void *)v18[19];
      *((_DWORD *)v18 + 37) = 0;
      if ( v22 )
      {
        ExFreePoolWithTag(v22, 0);
        v18[19] = 0;
      }
      v23 = v18[4];
      if ( v23 )
      {
        v24 = v63;
        do
        {
          v25 = *(_DWORD *)(v23 + 24);
          if ( (v25 & 0x4000) == 0 )
            *(_DWORD *)(v23 + 36) = 0;
          if ( (v25 & 2) != 0 || !v7 && !a4 && (v19 & 0x100) == 0 && *(_DWORD *)(v23 + 4) == 128 && (v25 & 1) != 0 )
            *(_DWORD *)(v23 + 24) = v25 & 0xFFFFFFF9 | 4;
          for ( k = *(_QWORD *)(v23 + 56); k; k = *(_QWORD *)(k + 32) )
          {
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFFEB);
            if ( (*(_DWORD *)(k + 8) & 2) == 0 )
              break;
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFFFD);
            _InterlockedOr((volatile signed __int32 *)(k + 8), 1u);
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFF7F);
            if ( !v7 )
              _InterlockedOr((volatile signed __int32 *)(k + 8), 0x40u);
            _InterlockedAnd((volatile signed __int32 *)(k + 8), 0xFFFFFBFF);
            _InterlockedOr((volatile signed __int32 *)(k + 8), 0x200u);
            *(_QWORD *)(k + 280) = *(_QWORD *)(a2 + 40);
            if ( !v7 )
            {
              ExAcquireFastMutex(*(PFAST_MUTEX *)(k + 256));
              _InterlockedOr((volatile signed __int32 *)(k + 8), 0x800u);
              ExReleaseFastMutex(*(PFAST_MUTEX *)(k + 256));
            }
            if ( !*(_WORD *)(k + 304) )
            {
              if ( v7 && _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 132), 4, 4) == 2 )
                ++*(_DWORD *)(v23 + 40);
              *(_QWORD *)(k + 64) = v24;
              v24 = k;
              *(_QWORD *)(k + 72) = *(_QWORD *)(v23 + 56);
              v27 = v60;
              if ( !v60 )
                v27 = k;
              v60 = v27;
              break;
            }
            _InterlockedDecrement((volatile signed __int32 *)(k + 4));
            _InterlockedOr((volatile signed __int32 *)(k + 8), 0x2000u);
          }
          v28 = *(_QWORD *)(v23 + 72);
          if ( v7 )
          {
            v41 = *(_QWORD *)(v23 + 112);
            if ( v41 )
            {
              if ( *(_QWORD *)(*(_QWORD *)v41 + 16LL) )
                *(_DWORD *)(v23 + 24) |= 0x1000u;
            }
          }
          v29 = *(_DWORD *)(v23 + 24);
          *(_DWORD *)(v23 + 24) = v29 & 0xFFFFF246;
          if ( (v29 & 0x100) != 0 )
            TxfDereferenceTxfScb((PVOID)v23);
          v23 = v28;
        }
        while ( v28 );
        v63 = v24;
        v17 = v61;
      }
      v30 = v18[6];
      if ( v30 )
      {
        v31 = *(_QWORD *)(v30 + 8);
        if ( v31 )
        {
          v51 = *(void **)(v30 + 16);
          *(_QWORD *)(v30 + 16) = 0;
          *(_QWORD *)(v18[6] + 8LL) = 0;
          do
          {
            v53 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 328) + 48LL) + 32LL);
            if ( v53 )
              *(_QWORD *)(v53 + 16) = *(_QWORD *)(a2 + 40);
            v54 = *(_QWORD *)(*(_QWORD *)(v31 + 328) + 48LL);
            v31 = *(_QWORD *)(v54 + 8);
            v55 = *(void **)(v54 + 16);
            NtfsPurgeFileRecordCache(a1);
            *(_DWORD *)(a1 + 4) |= 0x200u;
            ObDereferenceObjectDeferDelete(v51);
            *(_DWORD *)(a1 + 4) &= ~0x200u;
            v51 = v55;
          }
          while ( v31 );
        }
      }
      *((_DWORD *)v18 + 1) &= ~1u;
      v18[3] = 0;
      v32 = (_QWORD *)*v17;
      if ( *(_QWORD **)(*v17 + 8LL) != v17 || (v33 = v17 + 1, v34 = (_QWORD *)v17[1], (_QWORD *)*v34 != v17) )
LABEL_72:
        __fastfail(3u);
      *v34 = v32;
      v35 = v17;
      v32[1] = v34;
      v17 = v32;
      v61 = v32;
      *v33 = v35;
      *v35 = v35;
      TxfDereferenceTxfFcb(v18);
    }
    while ( v17 != (_QWORD *)(a2 + 192) );
  }
  *(_DWORD *)(a2 + 372) = 0;
  TxfRemoveViewIndexEntriesForTransaction(v16, *(_QWORD *)(v5 + 16) + 5864LL, a2);
  TxfRemoveViewIndexEntriesForTransaction(v36, *(_QWORD *)(v5 + 16) + 5968LL, a2);
  if ( *(_QWORD *)(a2 + 336) )
    TxfReleaseTempTxLock();
  if ( *(_QWORD *)(a2 + 344) )
    TxfReleaseTempTxLock();
  v37 = (_QWORD **)(a2 + 320);
  while ( 1 )
  {
    v38 = *v37;
    if ( *v37 == v37 )
      break;
    v42 = *v38;
    if ( *(_QWORD **)(*v38 + 8LL) != v38 )
      goto LABEL_72;
    v43 = (_QWORD *)v38[1];
    if ( (_QWORD *)*v43 != v38 )
      goto LABEL_72;
    *v43 = v42;
    *(_QWORD *)(v42 + 8) = v43;
    ExFreeToLookasideListEx(&TxfSavepointLookasideList, v38 - 4);
  }
  if ( v7 || (v39 = a4) != 0 )
  {
    if ( *(__int64 *)(a2 + 360) > 0 )
      TxfReleaseSpaceForAbortPriv(*(_QWORD *)(a2 + 208), a2);
    v39 = a4;
  }
  v40 = (_QWORD **)(a2 + 176);
  if ( *v40 != v40 )
  {
    if ( v39 )
    {
      while ( 1 )
      {
        v46 = *v40;
        if ( *v40 == v40 )
          break;
        if ( (_QWORD **)v46[1] != v40 )
          goto LABEL_72;
        v47 = (_QWORD *)*v46;
        if ( *(_QWORD **)(*v46 + 8LL) != v46 )
          goto LABEL_72;
        *v40 = v47;
        v47[1] = v40;
        v48 = (void *)v46[4];
        if ( v48 )
          TxfDereferenceTxfFcb(v48);
        ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v46);
      }
    }
    else
    {
      TxfPostDeletedLinks(v5, v40);
    }
  }
  if ( v63 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v5 + 24) + 800LL));
    *(_QWORD *)(v60 + 64) = *(_QWORD *)(v5 + 704);
    v56 = (struct _FAST_MUTEX *)(*(_QWORD *)(v5 + 24) + 800LL);
    *(_QWORD *)(v5 + 704) = v63;
    ExReleaseFastMutexUnsafe(v56);
    if ( a5 )
    {
      TxfProcessTxfVscbDereferencesForEOT(v5);
    }
    else
    {
      _InterlockedOr((volatile signed __int32 *)(v5 + 136), 0x80u);
      TxfQueueDelayedRmWorkItem(v5, v57, v58, v59);
    }
  }
}

```

## disassembly

```asm
0x1401daa68  mov     [rsp+arg_10], rbx
0x1401daa6d  mov     [rsp+arg_18], r9d
0x1401daa72  mov     [rsp+arg_0], rcx
0x1401daa77  push    rbp
0x1401daa78  push    rsi
0x1401daa79  push    rdi
0x1401daa7a  push    r12
0x1401daa7c  push    r13
0x1401daa7e  push    r14
0x1401daa80  push    r15
0x1401daa82  sub     rsp, 40h
0x1401daa86  mov     r14, [rdx+0D0h]
0x1401daa8d  xor     ebp, ebp
0x1401daa8f  mov     [rsp+78h+arg_8], rbp
0x1401daa97  mov     eax, r9d
0x1401daa9a  mov     [rsp+78h+var_58], rbp
0x1401daa9f  mov     r13d, r8d
0x1401daaa2  mov     rdi, rdx
0x1401daaa5  mov     r12, rcx
0x1401daaa8  test    r8d, r8d
0x1401daaab  jnz     loc_1401DB03F
0x1401daab1  test    eax, eax
0x1401daab3  jnz     loc_1401DB03F
0x1401daab9  mov     rcx, [rdi+190h]; P
0x1401daac0  test    rcx, rcx
0x1401daac3  jnz     loc_1401DB04F
0x1401daac9  mov     r8b, 1
0x1401daacc  mov     rdx, rdi
0x1401daacf  mov     rcx, r12
0x1401daad2  call    TxfCloseHandlesForTransaction
0x1401daad7  mov     rcx, rdi
0x1401daada  call    TxfCleanupNoRenameListAtEndOfTrans
0x1401daadf  mov     rcx, [r14+18h]
0x1401daae3  add     rcx, 60h ; '`'; FastMutex
0x1401daae7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1401daaee  nop     dword ptr [rax+rax+00h]
0x1401daaf3  lea     r15, [rdi+0C0h]
0x1401daafa  mov     rbx, [r15]
0x1401daafd  jmp     short loc_1401DAB14
0x1401daaff  mov     rcx, [rbx+40h]; Resource
0x1401dab03  mov     dl, 1; Wait
0x1401dab05  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401dab0c  nop     dword ptr [rax+rax+00h]
0x1401dab11  mov     rbx, [rbx]
0x1401dab14  cmp     rbx, r15
0x1401dab17  jnz     short loc_1401DAAFF
0x1401dab19  mov     edx, [rdi+98h]; NumOfElements
0x1401dab1f  lea     rsi, [rdi+90h]
0x1401dab26  mov     rcx, [rsi]; Base
0x1401dab29  lea     r9, TxfCompareTxfScbPtrForDirNotify; PtFuncCompare
0x1401dab30  mov     r8d, 10h; SizeOfElements
0x1401dab36  call    cs:__imp_qsort
0x1401dab3d  nop     dword ptr [rax+rax+00h]
0x1401dab42  cmp     [rdi+98h], ebp
0x1401dab48  jbe     short loc_1401DAB87
0x1401dab4a  mov     rax, [rsi]
0x1401dab4d  mov     dl, 1; Wait
0x1401dab4f  mov     ecx, ebp
0x1401dab51  add     rcx, rcx
0x1401dab54  mov     rbx, [rax+rcx*8]
0x1401dab58  mov     rcx, [rbx+40h]
0x1401dab5c  mov     rcx, [rcx+88h]; Resource
0x1401dab63  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401dab6a  nop     dword ptr [rax+rax+00h]
0x1401dab6f  mov     r8, rdi
0x1401dab72  mov     rdx, rbx
0x1401dab75  mov     rcx, r12
0x1401dab78  call    TxfDeleteIsoNamesForTransaction
0x1401dab7d  inc     ebp
0x1401dab7f  cmp     ebp, [rdi+98h]
0x1401dab85  jb      short loc_1401DAB4A
0x1401dab87  mov     rcx, [r14+18h]
0x1401dab8b  add     rcx, 60h ; '`'; FastMutex
0x1401dab8f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1401dab96  nop     dword ptr [rax+rax+00h]
0x1401dab9b  xor     ebp, ebp
0x1401dab9d  mov     ebx, ebp
0x1401dab9f  cmp     [rdi+98h], ebp
0x1401daba5  jbe     short loc_1401DABC4
0x1401daba7  mov     rcx, [rsi]
0x1401dabaa  mov     dl, 1
0x1401dabac  mov     eax, ebx
0x1401dabae  add     rax, rax
0x1401dabb1  mov     rcx, [rcx+rax*8]
0x1401dabb5  call    TxfDereferenceTxfScb
0x1401dabba  inc     ebx
0x1401dabbc  cmp     ebx, [rdi+98h]
0x1401dabc2  jb      short loc_1401DABA7
0x1401dabc4  mov     rcx, rsi
0x1401dabc7  call    TxfSortedArrayDeallocate
0x1401dabcc  mov     r12, [r15]
0x1401dabcf  mov     [rsp+78h+var_48], r12
0x1401dabd4  cmp     r12, r15
0x1401dabd7  jz      loc_1401DAE01
0x1401dabdd  lea     rsi, [r12-48h]
0x1401dabe2  mov     r15d, [rsi+4]
0x1401dabe6  mov     eax, r15d
0x1401dabe9  and     eax, 0E9F80603h
0x1401dabee  mov     [rsp+78h+var_50], rsi
0x1401dabf3  mov     [rsi+14h], ebp
0x1401dabf6  mov     [rsi+4], eax
0x1401dabf9  test    r13d, r13d
0x1401dabfc  jz      loc_1401DB077
0x1401dac02  bt      r15d, 15h
0x1401dac07  jnb     loc_1401DB0A9
0x1401dac0d  cmp     [rsi+40h], rbp
0x1401dac11  jnz     loc_1401DB0CE
0x1401dac17  mov     rax, [rsi+30h]
0x1401dac1b  test    rax, rax
0x1401dac1e  jnz     loc_1401DB0EB
0x1401dac24  mov     rcx, rsi
0x1401dac27  call    TxfDeleteSavedDeletedLinkList
0x1401dac2c  test    r15b, 8
0x1401dac30  jz      short loc_1401DAC40
0x1401dac32  mov     rdx, [rsi+58h]; Entry
0x1401dac36  cmp     [rdx+4Ch], bp
0x1401dac3a  jz      loc_1401DAFBC
0x1401dac40  mov     rcx, [rsi+98h]; P
0x1401dac47  mov     [rsi+94h], ebp
0x1401dac4d  test    rcx, rcx
0x1401dac50  jz      short loc_1401DAC67
0x1401dac52  xor     edx, edx; Tag
0x1401dac54  call    cs:__imp_ExFreePoolWithTag
0x1401dac5b  nop     dword ptr [rax+rax+00h]
0x1401dac60  mov     [rsi+98h], rbp
0x1401dac67  mov     rbp, [rsi+20h]
0x1401dac6b  xor     ecx, ecx
0x1401dac6d  test    rbp, rbp
0x1401dac70  jz      loc_1401DAD8B
0x1401dac76  mov     esi, [rsp+78h+arg_18]
0x1401dac7d  mov     r12, [rsp+78h+arg_8]
0x1401dac85  mov     eax, [rbp+18h]
0x1401dac88  bt      eax, 0Eh
0x1401dac8c  jb      short loc_1401DAC91
0x1401dac8e  mov     [rbp+24h], ecx
0x1401dac91  test    al, 2
0x1401dac93  jnz     loc_1401DAEDC
0x1401dac99  test    r13d, r13d
0x1401dac9c  jz      loc_1401DAEB4
0x1401daca2  mov     rbx, [rbp+38h]
0x1401daca6  test    rbx, rbx
0x1401daca9  jz      loc_1401DAD49
0x1401dacaf  lock and dword ptr [rbx+8], 0FFFFFFEBh
0x1401dacb4  mov     eax, [rbx+8]
0x1401dacb7  test    al, 2
0x1401dacb9  jz      loc_1401DAD49
0x1401dacbf  lock and dword ptr [rbx+8], 0FFFFFFFDh
0x1401dacc4  lock or dword ptr [rbx+8], 1
0x1401dacc9  lock and dword ptr [rbx+8], 0FFFFFF7Fh
0x1401dacd1  test    r13d, r13d
0x1401dacd4  jnz     short loc_1401DACDB
0x1401dacd6  lock or dword ptr [rbx+8], 40h
0x1401dacdb  lock and dword ptr [rbx+8], 0FFFFFBFFh
0x1401dace3  lock or dword ptr [rbx+8], 200h
0x1401daceb  mov     rax, [rdi+28h]
0x1401dacef  mov     [rbx+118h], rax
0x1401dacf6  test    r13d, r13d
0x1401dacf9  jz      loc_1401DAF0E
0x1401dacff  cmp     [rbx+130h], cx
0x1401dad06  jnz     loc_1401DAF43
0x1401dad0c  test    r13d, r13d
0x1401dad0f  jz      short loc_1401DAD29
0x1401dad11  mov     edx, 4
0x1401dad16  mov     eax, edx
0x1401dad18  lock cmpxchg [r14+84h], edx
0x1401dad21  cmp     eax, 2
0x1401dad24  jnz     short loc_1401DAD29
0x1401dad26  inc     dword ptr [rbp+28h]
0x1401dad29  mov     [rbx+40h], r12
0x1401dad2d  mov     r12, rbx
0x1401dad30  mov     rax, [rbp+38h]
0x1401dad34  mov     [rbx+48h], rax
0x1401dad38  mov     rax, [rsp+78h+var_58]
0x1401dad3d  test    rax, rax
0x1401dad40  cmovz   rax, rbx
0x1401dad44  mov     [rsp+78h+var_58], rax
0x1401dad49  mov     rbx, [rbp+48h]
0x1401dad4d  test    r13d, r13d
0x1401dad50  jnz     loc_1401DAEEA
0x1401dad56  mov     edx, [rbp+18h]
0x1401dad59  mov     eax, edx
0x1401dad5b  and     eax, 0FFFFF246h
0x1401dad60  mov     [rbp+18h], eax
0x1401dad63  bt      edx, 8
0x1401dad67  jb      loc_1401DB101
0x1401dad6d  mov     rbp, rbx
0x1401dad70  test    rbx, rbx
0x1401dad73  jnz     loc_1401DAC85
0x1401dad79  mov     rsi, [rsp+78h+var_50]
0x1401dad7e  mov     [rsp+78h+arg_8], r12
0x1401dad86  mov     r12, [rsp+78h+var_48]
0x1401dad8b  mov     rax, [rsi+30h]
0x1401dad8f  xor     ebp, ebp
0x1401dad91  test    rax, rax
0x1401dad94  jz      short loc_1401DADA8
0x1401dad96  mov     rbp, [rax+8]
0x1401dad9a  xor     r8d, r8d
0x1401dad9d  test    rbp, rbp
0x1401dada0  jnz     loc_1401DB112
0x1401dada6  xor     ebp, ebp
0x1401dada8  and     dword ptr [rsi+4], 0FFFFFFFEh
0x1401dadac  mov     [rsi+18h], rbp
0x1401dadb0  mov     rcx, [r12]
0x1401dadb4  cmp     [rcx+8], r12
0x1401dadb8  jnz     loc_1401DAF58
0x1401dadbe  lea     r8, [r12+8]
0x1401dadc3  mov     rdx, [r8]
0x1401dadc6  cmp     [rdx], r12
0x1401dadc9  jnz     loc_1401DAF58
0x1401dadcf  mov     [rdx], rcx
0x1401dadd2  mov     rax, r12
0x1401dadd5  mov     [rcx+8], rdx
0x1401dadd9  mov     r12, rcx
0x1401daddc  mov     [rsp+78h+var_48], rcx
0x1401dade1  mov     dl, 1
0x1401dade3  mov     rcx, rsi
0x1401dade6  mov     [r8], rax
0x1401dade9  mov     [rax], rax
0x1401dadec  call    TxfDereferenceTxfFcb
0x1401dadf1  lea     rax, [rdi+0C0h]
0x1401dadf8  cmp     r12, rax
0x1401dadfb  jnz     loc_1401DABDD
0x1401dae01  mov     [rdi+174h], ebp
0x1401dae07  mov     r8, rdi
0x1401dae0a  mov     rdx, [r14+10h]
0x1401dae0e  add     rdx, 16E8h
0x1401dae15  call    TxfRemoveViewIndexEntriesForTransaction
0x1401dae1a  mov     rdx, [r14+10h]
0x1401dae1e  mov     r8, rdi
0x1401dae21  add     rdx, 1750h
0x1401dae28  call    TxfRemoveViewIndexEntriesForTransaction
0x1401dae2d  lea     rcx, [rdi+150h]
0x1401dae34  cmp     [rcx], rbp
0x1401dae37  jnz     loc_1401DB12F
0x1401dae3d  lea     rcx, [rdi+158h]
0x1401dae44  cmp     [rcx], rbp
0x1401dae47  jnz     loc_1401DB139
0x1401dae4d  lea     rbx, [rdi+140h]
0x1401dae54  mov     rdx, [rbx]
0x1401dae57  cmp     rdx, rbx
0x1401dae5a  jnz     loc_1401DAF5F
0x1401dae60  test    r13d, r13d
0x1401dae63  jnz     loc_1401DAF94
0x1401dae69  mov     r8d, [rsp+78h+arg_18]
0x1401dae71  test    r8d, r8d
0x1401dae74  jnz     loc_1401DAF94
0x1401dae7a  add     rdi, 0B0h
0x1401dae81  cmp     [rdi], rdi
0x1401dae84  jnz     loc_1401DB143
0x1401dae8a  mov     rbx, [rsp+78h+arg_8]
0x1401dae92  test    rbx, rbx
0x1401dae95  jnz     loc_1402CD5C9
0x1401dae9b  mov     rbx, [rsp+78h+arg_10]
0x1401daea3  add     rsp, 40h
0x1401daea7  pop     r15
0x1401daea9  pop     r14
0x1401daeab  pop     r13
0x1401daead  pop     r12
0x1401daeaf  pop     rdi
0x1401daeb0  pop     rsi
0x1401daeb1  pop     rbp
0x1401daeb2  retn
0x1401daeb4  test    esi, esi
0x1401daeb6  jnz     loc_1401DACA2
0x1401daebc  bt      r15d, 8
0x1401daec1  jb      loc_1401DACA2
0x1401daec7  cmp     dword ptr [rbp+4], 80h
0x1401daece  jnz     loc_1401DACA2
0x1401daed4  test    al, 1
0x1401daed6  jz      loc_1401DACA2
0x1401daedc  and     eax, 0FFFFFFFDh
0x1401daedf  or      eax, 4
0x1401daee2  mov     [rbp+18h], eax
0x1401daee5  jmp     loc_1401DACA2
0x1401daeea  mov     rax, [rbp+70h]
0x1401daeee  test    rax, rax
0x1401daef1  jz      loc_1401DAD56
0x1401daef7  mov     rax, [rax]
0x1401daefa  cmp     [rax+10h], rcx
0x1401daefe  jz      loc_1401DAD56
0x1401daf04  bts     dword ptr [rbp+18h], 0Ch
0x1401daf09  jmp     loc_1401DAD56
0x1401daf0e  mov     rcx, [rbx+100h]; FastMutex
0x1401daf15  call    cs:__imp_ExAcquireFastMutex
0x1401daf1c  nop     dword ptr [rax+rax+00h]
0x1401daf21  lock or dword ptr [rbx+8], 800h
0x1401daf29  mov     rcx, [rbx+100h]; FastMutex
0x1401daf30  call    cs:__imp_ExReleaseFastMutex
0x1401daf37  nop     dword ptr [rax+rax+00h]
0x1401daf3c  xor     ecx, ecx
0x1401daf3e  jmp     loc_1401DACFF
0x1401daf43  lock dec dword ptr [rbx+4]
0x1401daf47  lock or dword ptr [rbx+8], 2000h
0x1401daf4f  mov     rbx, [rbx+20h]
0x1401daf53  jmp     loc_1401DACA6
0x1401daf58  mov     ecx, 3
0x1401daf5d  int     29h; Win8: RtlFailFast(ecx)
0x1401daf5f  mov     rax, [rdx]
0x1401daf62  cmp     [rax+8], rdx
0x1401daf66  jnz     short loc_1401DAF58
  ... truncated ...
```
