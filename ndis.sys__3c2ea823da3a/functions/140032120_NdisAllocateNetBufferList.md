# NdisAllocateNetBufferList

- ea: `0x140032120`
- end: `0x140032a93`
- name: `NdisAllocateNetBufferList`
- size: `2419`
- prototype: `PNET_BUFFER_LIST __stdcall(NDIS_HANDLE PoolHandle, USHORT ContextSize, USHORT ContextBackFill)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140030bc0`
- `0x140031090`

## callees

- `0x140030450`
- `0x140032120`
- `0x140032aa0`
- `0x140064680`
- `0x140083a40`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400326e6`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400326e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032919`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e98bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032919`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e98bc`
- `ntoskrnl!ExAllocatePool2` at `0x14003284e`
- `ntoskrnl!ExAllocatePool2` at `0x14003296f`
- `ntoskrnl!ExAllocatePool2` at `0x1400329ed`
- `ntoskrnl!ExAllocatePool2` at `0x14003284e`
- `ntoskrnl!ExAllocatePool2` at `0x14003296f`
- `ntoskrnl!ExAllocatePool2` at `0x1400329ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003223f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400327dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400328ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003223f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400327dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400328ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400321c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400327a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003287b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400321c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400327a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003287b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140032221`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140032221`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032256`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400327ef`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032819`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032256`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400327ef`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140032819`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140032463`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140032463`
- `ntoskrnl!ExQueryDepthSList` at `0x14003241d`
- `ntoskrnl!ExQueryDepthSList` at `0x140032448`
- `ntoskrnl!ExQueryDepthSList` at `0x1400329c4`
- `ntoskrnl!ExQueryDepthSList` at `0x14003241d`
- `ntoskrnl!ExQueryDepthSList` at `0x140032448`
- `ntoskrnl!ExQueryDepthSList` at `0x1400329c4`
- `NETIO!WfpNblInfoCleanup` at `0x1400323ae`
- `NETIO!WfpNblInfoCleanup` at `0x1400323ae`

## pseudocode

```c
PNET_BUFFER_LIST __stdcall NdisAllocateNetBufferList(
        NDIS_HANDLE PoolHandle,
        USHORT ContextSize,
        USHORT ContextBackFill)
{
  int v3; // r13d
  unsigned int Number; // r12d
  unsigned __int64 v6; // rbx
  char *v7; // rdi
  KIRQL v8; // r15
  PSLIST_ENTRY v9; // rbx
  unsigned int v10; // r15d
  __int16 v11; // di
  _QWORD *p_Next; // rdx
  unsigned int v13; // ecx
  __int64 v14; // rax
  int v15; // eax
  bool v16; // zf
  _SLIST_ENTRY *v17; // rax
  struct _NET_BUFFER_LIST *v18; // rdi
  char *v19; // rcx
  _SLIST_ENTRY *v20; // rdx
  _SLIST_ENTRY *v21; // r13
  unsigned int *v22; // rcx
  unsigned __int64 v23; // rax
  char *v24; // rdi
  union _SLIST_HEADER *v25; // r12
  _SLIST_ENTRY *v26; // r13
  USHORT v27; // di
  union _SLIST_HEADER *v28; // rcx
  unsigned __int64 *p_Region; // rcx
  __int64 v30; // rax
  struct _MDL *v31; // r14
  _NET_BUFFER *FirstNetBuffer; // rcx
  unsigned int v33; // eax
  _SLIST_ENTRY *i; // rcx
  __int64 v36; // rax
  unsigned int v37; // edx
  unsigned __int64 v38; // rax
  unsigned int v39; // r9d
  _SLIST_ENTRY *Next; // rcx
  _SLIST_ENTRY *v41; // r8
  int v42; // edx
  PSLIST_ENTRY v43; // rax
  int v44; // edx
  __int64 v45; // r9
  unsigned __int64 v46; // r8
  __int16 v47; // dx
  int v48; // edx
  unsigned __int64 v49; // rax
  unsigned __int16 v50; // ax
  KIRQL v51; // al
  __int64 v52; // rdx
  unsigned __int64 v53; // rax
  struct _SLIST_ENTRY *v54; // rax
  KIRQL v55; // al
  __int64 v56; // rdx
  _QWORD *v57; // rcx
  KIRQL v58; // r8
  _QWORD *v59; // rax
  unsigned __int16 v60; // r12
  __int64 v61; // rax
  struct _SLIST_ENTRY *Pool2; // rax
  unsigned int v63; // [rsp+80h] [rbp+8h]
  unsigned int v64; // [rsp+80h] [rbp+8h]

  v3 = ContextSize;
  if ( !PoolHandle || (ContextSize & 7) != 0 || (ContextBackFill & 7) != 0 )
    return 0;
  if ( (*((_DWORD *)PoolHandle + 1) & 1) != 0 )
  {
    v49 = *((unsigned int *)PoolHandle + 8);
    v63 = 0;
    if ( v49 + 32 >= v49 )
    {
      Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(0x100000042LL, v49 + 32, *((unsigned int *)PoolHandle + 9));
      if ( Pool2 )
      {
        Pool2->Next = (_SLIST_ENTRY *)PoolHandle;
        v9 = Pool2 + 2;
      }
      else
      {
        v9 = 0;
      }
    }
    else
    {
      v9 = 0;
    }
    goto LABEL_11;
  }
  Number = KeGetPcr()->Prcb.Number;
  v63 = 1;
  if ( ndisMaxNumberOfProcessors != 1 )
  {
    v6 = (unsigned __int64)Number << 8;
    v7 = (char *)PoolHandle + v6 + 384;
    if ( !v7[216] )
    {
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 26);
      if ( !v7[216] )
      {
        ExInitializeLookasideListEx(
          (PLOOKASIDE_LIST_EX)v7,
          ndisAllocateFromNPagedPool,
          *(PFREE_FUNCTION_EX *)&v7[-v6 - 200],
          NonPagedPoolNx,
          0,
          *(unsigned int *)&v7[-v6 - 212],
          *(_DWORD *)&v7[-v6 - 216],
          0x400u);
        v7[216] = 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)v7 + 26, v8);
    }
    _InterlockedIncrement((volatile signed __int32 *)v7 + 5);
    v9 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v7 + 24));
    if ( v9 )
      goto LABEL_11;
    if ( ExQueryDepthSList(*((PSLIST_HEADER *)v7 + 25)) >= 0xAu )
    {
      v51 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 26);
      v52 = *((_QWORD *)v7 + 24);
      *((_QWORD *)v7 + 24) = *((_QWORD *)v7 + 25);
      *((_QWORD *)v7 + 25) = v52;
      KeReleaseSpinLock((PKSPIN_LOCK)v7 + 26, v51);
      v9 = ExpInterlockedPopEntrySList(*((PSLIST_HEADER *)v7 + 24));
      if ( v9 )
        goto LABEL_11;
    }
    _InterlockedIncrement((volatile signed __int32 *)v7 + 6);
  }
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 37);
  v9 = ExpInterlockedPopEntrySList((PSLIST_HEADER)PoolHandle + 8);
  if ( v9 )
  {
LABEL_105:
    *((_DWORD *)&v9[-1].Next + 2) = Number;
    goto LABEL_11;
  }
  _InterlockedIncrement((volatile signed __int32 *)PoolHandle + 38);
  v53 = *((unsigned int *)PoolHandle + 43);
  if ( v53 + 32 >= v53
    && (v54 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, v53 + 32, *((unsigned int *)PoolHandle + 42))) != 0 )
  {
    v9 = v54 + 2;
    v54->Next = 0;
    if ( v54 != (struct _SLIST_ENTRY *)-32LL )
    {
      v54->Next = (_SLIST_ENTRY *)PoolHandle;
      v55 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)PoolHandle + 1);
      v56 = *((_QWORD *)PoolHandle + 2);
      v57 = (char *)PoolHandle + 16;
      v58 = v55;
      if ( *(NDIS_HANDLE *)(v56 + 8) != (char *)PoolHandle + 16 )
        __fastfail(3u);
      v59 = &v9[-2].Next + 1;
      *v59 = v56;
      v59[1] = v57;
      *(_QWORD *)(v56 + 8) = (char *)v9 - 24;
      *v57 = (char *)v9 - 24;
      KeReleaseSpinLock((PKSPIN_LOCK)PoolHandle + 1, v58);
      v63 = 0;
      goto LABEL_105;
    }
  }
  else
  {
    v9 = 0;
  }
  v63 = 0;
LABEL_11:
  if ( !v9 )
    return 0;
  v10 = v63;
  v11 = *((_WORD *)&v9[3].Next + 5);
  memset(v9, 0, 8 * (v63 ^ 1LL) + 368);
  v9[2].Next = (_SLIST_ENTRY *)PoolHandle;
  *((_DWORD *)&v9[8].Next + 2) = 256;
  if ( v63 )
    *((_WORD *)&v9[3].Next + 5) = v11;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    if ( *((__int64 *)&v9[15].Next + 1) > 0 )
    {
      for ( i = v9->Next; i; i = i->Next )
      {
        v36 = *((_QWORD *)&i[15].Next + 1);
        if ( !v36 || v36 < 0 )
        {
          v37 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
          if ( v37 + 1 < v37 )
            v37 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
          *((_QWORD *)&i[15].Next + 1) = v37;
        }
      }
    }
    else
    {
      p_Next = &v9->Next;
      v13 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
      if ( v13 + 1 < v13 )
        v13 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
      do
      {
        if ( (__int64)p_Next[31] <= 0 )
        {
          v14 = v13++;
          p_Next[31] = v14;
        }
        p_Next = (_QWORD *)*p_Next;
      }
      while ( p_Next );
    }
  }
  *((_BYTE *)&v9[12].Next + 8) = *((_BYTE *)PoolHandle + 40);
  v15 = *((_DWORD *)PoolHandle + 11);
  if ( (v15 & 2) != 0 )
  {
    v16 = (v15 & 1) == 0;
    v17 = v9 + 35;
    if ( v16 )
      v17 = v9 + 24;
    v9[1].Next = v17;
    v17->Next = 0;
    *((_WORD *)&v9[1].Next->Next + 4) = *((_WORD *)PoolHandle + 21);
    *((_WORD *)&v9[1].Next->Next + 5) = *((_WORD *)PoolHandle + 21);
    if ( *((_WORD *)PoolHandle + 21) >= (unsigned __int16)v3 )
    {
      v18 = (struct _NET_BUFFER_LIST *)v9;
      v19 = (char *)v9;
      *((_WORD *)&v9[1].Next->Next + 5) -= v3;
      goto LABEL_47;
    }
  }
  v18 = (struct _NET_BUFFER_LIST *)v9;
  if ( (_WORD)v3 )
  {
    v39 = *((_DWORD *)PoolHandle + 9);
    Next = v9[1].Next;
    v41 = v9[23].Next;
    v42 = *((_DWORD *)&v9[2].Next[2].Next + 3);
    v64 = v39;
    if ( (v42 & 2) == 0 )
      goto LABEL_75;
    v43 = v9 + 35;
    if ( (v42 & 1) == 0 )
      v43 = v9 + 24;
    if ( Next != v43 || *((_WORD *)&Next->Next + 5) < (unsigned __int16)v3 )
    {
LABEL_75:
      *((_WORD *)&v9[3].Next + 4) += v3;
      v44 = *((unsigned __int16 *)&v9[3].Next + 4);
      if ( v44 <= ndisMaxCachedNblContextSize )
      {
        if ( (unsigned __int16)v44 <= *((_WORD *)&v9[3].Next + 5) )
          LOWORD(v44) = *((_WORD *)&v9[3].Next + 5);
        *((_WORD *)&v9[3].Next + 5) = v44;
      }
    }
    if ( Next )
    {
      v50 = *((_WORD *)&Next->Next + 5);
      if ( v50 >= (unsigned __int16)v3 )
      {
        *((_WORD *)&Next->Next + 5) = v50 - v3;
LABEL_89:
        *((_DWORD *)&v9[8].Next + 2) |= 0x400u;
        goto LABEL_45;
      }
    }
    if ( v41 && *((_WORD *)&v41->Next + 4) >= (unsigned __int16)v3 )
    {
      *((_WORD *)&v41->Next + 5) -= v3;
      v41->Next = v9[1].Next;
      *((_DWORD *)&v9[8].Next + 2) |= 0x400u;
      v9[1].Next = v41;
      v9[23].Next = 0;
      goto LABEL_45;
    }
    v60 = ContextBackFill + v3;
    if ( *((unsigned __int16 *)&v9[3].Next + 4) <= ndisMaxCachedNblContextSize )
    {
      if ( v41 )
      {
        v9[23].Next = 0;
        ExFreePoolWithTag(v41, 0);
        v39 = v64;
      }
      if ( v60 <= v3 + *((unsigned __int16 *)&v9[3].Next + 5) - *((unsigned __int16 *)&v9[3].Next + 4) )
        v60 = v3 + *((_WORD *)&v9[3].Next + 5) - *((_WORD *)&v9[3].Next + 4);
      if ( v60 > v3 + (unsigned int)ContextBackFill )
        v39 = 1668170830;
    }
    v61 = ExAllocatePool2(64, v60 + 16LL, v39);
    if ( v61 )
    {
      *(_WORD *)(v61 + 8) = v60;
      *(_WORD *)(v61 + 10) = v60 - v3;
      *(_QWORD *)v61 = v9[1].Next;
      v9[1].Next = (_SLIST_ENTRY *)v61;
      goto LABEL_89;
    }
    *((_WORD *)&v9[3].Next + 4) -= v3;
    v20 = v9[1].Next;
    v21 = v9[2].Next;
    if ( v20 && (*(_DWORD *)(&v9[8].Next + 1) & 0x400) != 0 )
      NdisFreeNetBufferListContext((PNET_BUFFER_LIST)v9, *((_WORD *)&v20->Next + 4) - *((_WORD *)&v20->Next + 5));
    *((_DWORD *)&v9[8].Next + 2) &= ~0x100u;
    if ( ((unsigned __int64)v9[14].Next & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    {
      LOBYTE(v20) = 1;
      WfpNblInfoCleanup(v9, v20);
    }
    if ( *(int *)ndisNblTrackerMode >= 3 )
      ndisNblTrackerRecordEventInternal((struct _NET_BUFFER_LIST *)v9, 0, 4u, 0, 0);
    v22 = (unsigned int *)&v9[-2];
    if ( (HIDWORD(v21->Next) & 1) != 0 )
    {
      if ( (unsigned __int64)v9 < 0x20 )
        ndisBugCheckEx(0x31u, 3u, (ULONG_PTR)v9, 0);
      ExFreePoolWithTag(v22, 0);
      goto LABEL_44;
    }
    if ( ndisMaxNumberOfProcessors != 1 )
    {
      v23 = (unsigned __int64)v22[6] << 8;
      v24 = (char *)&v21[24] + v23;
      if ( !v24[216] )
        ndisPplLazyInitializeLookaside((PLOOKASIDE_LIST_EX)((char *)&v21[24] + v23));
      if ( *((_DWORD *)&v9[-1].Next + 2) == KeGetPcr()->Prcb.Number )
        v25 = (union _SLIST_HEADER *)*((_QWORD *)v24 + 24);
      else
        v25 = (union _SLIST_HEADER *)*((_QWORD *)v24 + 25);
      _InterlockedIncrement((volatile signed __int32 *)v24 + 7);
      if ( ExQueryDepthSList(v25) < *((_WORD *)v24 + 8) )
      {
        v28 = v25;
        goto LABEL_43;
      }
      _InterlockedIncrement((volatile signed __int32 *)v24 + 8);
    }
    v26 = v21 + 8;
    _InterlockedIncrement((volatile signed __int32 *)&v26[1].Next + 3);
    v27 = (USHORT)v26[1].Next;
    if ( ExQueryDepthSList((PSLIST_HEADER)v26) >= v27 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v26[2]);
      (*((void (__fastcall **)(PSLIST_ENTRY, _SLIST_ENTRY *))&v26[3].Next + 1))(v9, v26);
      goto LABEL_44;
    }
    v28 = (union _SLIST_HEADER *)v26;
LABEL_43:
    ExpInterlockedPushEntrySList(v28, v9);
LABEL_44:
    v18 = 0;
  }
LABEL_45:
  v9 = (PSLIST_ENTRY)v18;
  if ( !v18 )
    return (PNET_BUFFER_LIST)v9;
  v19 = (char *)v18;
LABEL_47:
  if ( (*((_DWORD *)PoolHandle + 11) & 1) != 0 )
  {
    p_Region = &v18->Link.Region;
    v18->Link.Region = (unsigned __int64)&v18[1];
  }
  else
  {
    p_Region = (unsigned __int64 *)(v19 + 8);
  }
  if ( (*((_DWORD *)PoolHandle + 11) & 4) != 0 )
  {
    v30 = *((unsigned __int16 *)PoolHandle + 21);
    if ( (_WORD)v30 )
      v31 = (struct _MDL *)((char *)&v18[1].NetBufferListInfo[6] + v30);
    else
      v31 = (struct _MDL *)&v18[1].NetBufferListInfo[4];
    if ( v10 )
    {
      v31->ByteCount = *((_DWORD *)PoolHandle + 22);
      v31->Next = 0;
    }
    else
    {
      v45 = *((unsigned int *)PoolHandle + 22);
      v46 = (unsigned __int64)v31 + *((unsigned int *)PoolHandle + 23);
      v47 = (_WORD)v31 + *((_DWORD *)PoolHandle + 23);
      v31->Next = 0;
      v31->MdlFlags = 0;
      v31->ByteCount = v45;
      v31->StartVa = (PVOID)(v46 & 0xFFFFFFFFFFFFF000uLL);
      v48 = v47 & 0xFFF;
      v31->ByteOffset = v48;
      v31->Size = 8 * ((((unsigned __int64)(unsigned __int16)v48 + v45 + 4095) >> 12) + 6);
      MmBuildMdlForNonPagedPool(v31);
    }
    FirstNetBuffer = v18->FirstNetBuffer;
    if ( FirstNetBuffer )
    {
      v33 = *((_DWORD *)PoolHandle + 22);
      FirstNetBuffer->Link.Alignment = 0;
      FirstNetBuffer->NdisPoolHandle = PoolHandle;
      FirstNetBuffer->Link.Region = (unsigned __int64)v31;
      FirstNetBuffer->CurrentMdlOffset = v33;
      FirstNetBuffer->MdlChain = v31;
      FirstNetBuffer->DataOffset = v33;
      FirstNetBuffer->DataLength = 0;
      *(_DWORD *)&FirstNetBuffer->ChecksumBias = 0;
      FirstNetBuffer->NdisReserved[1] = 0;
      FirstNetBuffer->NdisReserved[0] = 0;
      FirstNetBuffer->MiniportReserved[1] = 0;
      FirstNetBuffer->MiniportReserved[0] = 0;
      FirstNetBuffer->SharedMemoryInfo = 0;
    }
  }
  else
  {
    v38 = *p_Region;
    if ( *p_Region )
    {
      *(_QWORD *)v38 = 0;
      *(_QWORD *)(v38 + 56) = PoolHandle;
      *(_QWORD *)(v38 + 8) = 0;
      *(_DWORD *)(v38 + 16) = 0;
      *(_QWORD *)(v38 + 32) = 0;
      *(_DWORD *)(v38 + 40) = 0;
      *(_DWORD *)(v38 + 24) = 0;
      *(_DWORD *)(v38 + 48) = 0;
      *(_QWORD *)(v38 + 72) = 0;
      *(_QWORD *)(v38 + 64) = 0;
      *(_QWORD *)(v38 + 136) = 0;
      *(_QWORD *)(v38 + 128) = 0;
      *(_QWORD *)(v38 + 168) = 0;
    }
  }
  if ( *(int *)ndisNblTrackerMode >= 3 )
    ndisNblTrackerRecordEventInternal(v18, 0, 2u, 0, 0);
  return (PNET_BUFFER_LIST)v9;
}

```

## disassembly

```asm
0x140032120  mov     [rsp+arg_8], rbx
0x140032125  mov     [rsp+arg_10], r8w
0x14003212b  push    rbp
0x14003212c  push    rsi
0x14003212d  push    rdi
0x14003212e  push    r12
0x140032130  push    r13
0x140032132  push    r14
0x140032134  push    r15
0x140032136  sub     rsp, 40h
0x14003213a  movzx   r13d, dx
0x14003213e  mov     rbp, rcx
0x140032141  test    rcx, rcx
0x140032144  jz      loc_1400325FC
0x14003214a  movzx   eax, r13w
0x14003214e  and     ax, 7
0x140032152  mov     word ptr [rsp+78h+arg_0], ax
0x14003215a  jnz     loc_1400325FC
0x140032160  movzx   eax, r8w
0x140032164  and     ax, 7
0x140032168  mov     word ptr [rsp+78h+arg_0], ax
0x140032170  jnz     loc_1400325FC
0x140032176  mov     eax, [rcx+4]
0x140032179  xor     esi, esi
0x14003217b  test    al, 1
0x14003217d  jnz     loc_1400326F7
0x140032183  mov     r12d, gs:1A4h
0x14003218c  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x140032193  mov     [rsp+78h+arg_0], 1
0x14003219e  jz      loc_14003280B
0x1400321a4  mov     ebx, r12d
0x1400321a7  lea     rdi, [rcx+180h]
0x1400321ae  shl     rbx, 8
0x1400321b2  add     rdi, rbx
0x1400321b5  cmp     [rdi+0D8h], sil
0x1400321bc  jnz     loc_14003224B
0x1400321c2  lea     rcx, [rdi+0D0h]; SpinLock
0x1400321c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400321d0  nop     dword ptr [rax+rax+00h]
0x1400321d5  movzx   r15d, al
0x1400321d9  cmp     [rdi+0D8h], sil
0x1400321e0  jnz     short loc_140032234
0x1400321e2  mov     [rsp+78h+Depth], 400h; Depth
0x1400321e9  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x1400321f0  mov     r8, rdi
0x1400321f3  mov     r9d, 200h; PoolType
0x1400321f9  sub     r8, rbx
0x1400321fc  mov     ecx, [r8-0D4h]
0x140032203  mov     eax, [r8-0D8h]
0x14003220a  mov     r8, [r8-0C8h]; Free
0x140032211  mov     [rsp+78h+Tag], eax; Tag
0x140032215  mov     [rsp+78h+Size], rcx; Size
0x14003221a  mov     rcx, rdi; Lookaside
0x14003221d  mov     [rsp+78h+Flags], esi; Flags
0x140032221  call    cs:__imp_ExInitializeLookasideListEx
0x140032228  nop     dword ptr [rax+rax+00h]
0x14003222d  mov     byte ptr [rdi+0D8h], 1
0x140032234  movzx   edx, r15b; NewIrql
0x140032238  lea     rcx, [rdi+0D0h]; SpinLock
0x14003223f  call    cs:__imp_KeReleaseSpinLock
0x140032246  nop     dword ptr [rax+rax+00h]
0x14003224b  lock inc dword ptr [rdi+14h]
0x14003224f  mov     rcx, [rdi+0C0h]; ListHead
0x140032256  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003225d  nop     dword ptr [rax+rax+00h]
0x140032262  mov     rbx, rax
0x140032265  test    rax, rax
0x140032268  jz      loc_1400329BD
0x14003226e  test    rbx, rbx
0x140032271  jz      loc_1400325FE
0x140032277  mov     r15d, [rsp+78h+arg_0]
0x14003227f  xor     edx, edx; Val
0x140032281  movzx   edi, word ptr [rbx+3Ah]
0x140032285  mov     r8d, r15d
0x140032288  xor     r8, 1
0x14003228c  mov     rcx, rbx; void *
0x14003228f  lea     r8, ds:170h[r8*8]; Size
0x140032297  call    memset
0x14003229c  mov     [rbx+20h], rbp
0x1400322a0  mov     dword ptr [rbx+88h], 100h
0x1400322aa  test    r15d, r15d
0x1400322ad  jz      short loc_1400322B3
0x1400322af  mov     [rbx+3Ah], di
0x1400322b3  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400322b9  test    eax, eax
0x1400322bb  jz      short loc_14003230B
0x1400322bd  mov     rax, [rbx+0F8h]
0x1400322c4  test    rax, rax
0x1400322c7  jnz     loc_140032553
0x1400322cd  mov     rdx, rbx
0x1400322d0  mov     ecx, 1
0x1400322d5  lock xadd cs:dword_14011AE28, ecx
0x1400322dd  lea     eax, [rcx+1]
0x1400322e0  cmp     eax, ecx
0x1400322e2  jb      loc_140032A2B
0x1400322e8  mov     rax, [rdx+0F8h]
0x1400322ef  test    rax, rax
0x1400322f2  jnz     loc_1400325A4
0x1400322f8  mov     eax, ecx
0x1400322fa  inc     ecx
0x1400322fc  mov     [rdx+0F8h], rax
0x140032303  mov     rdx, [rdx]
0x140032306  test    rdx, rdx
0x140032309  jnz     short loc_1400322E8
0x14003230b  movzx   eax, byte ptr [rbp+28h]
0x14003230f  mov     [rbx+0C8h], al
0x140032315  mov     eax, [rbp+2Ch]
0x140032318  test    al, 2
0x14003231a  jz      loc_140032606
0x140032320  test    al, 1
0x140032322  lea     rax, [rbx+230h]
0x140032329  jnz     short loc_140032332
0x14003232b  lea     rax, [rbx+180h]
0x140032332  mov     [rbx+10h], rax
0x140032336  mov     [rax], rsi
0x140032339  mov     rcx, [rbx+10h]
0x14003233d  movzx   eax, word ptr [rbp+2Ah]
0x140032341  mov     [rcx+8], ax
0x140032345  mov     rcx, [rbx+10h]
0x140032349  movzx   eax, word ptr [rbp+2Ah]
0x14003234d  mov     [rcx+0Ah], ax
0x140032351  cmp     [rbp+2Ah], r13w
0x140032356  jb      loc_140032606
0x14003235c  mov     rax, [rbx+10h]
0x140032360  mov     rdi, rbx
0x140032363  mov     rcx, rbx
0x140032366  sub     [rax+0Ah], r13w
0x14003236b  jmp     loc_140032481
0x140032370  sub     [rbx+38h], r13w
0x140032375  mov     rdx, [rbx+10h]
0x140032379  mov     r13, [rbx+20h]
0x14003237d  test    rdx, rdx
0x140032380  jz      short loc_140032392
0x140032382  test    dword ptr [rbx+88h], 400h
0x14003238c  jnz     loc_1400329A5
0x140032392  and     dword ptr [rbx+88h], 0FFFFFEFFh
0x14003239c  test    qword ptr [rbx+0E0h], 0FFFFFFFFFFFFFFFCh
0x1400323a7  jz      short loc_1400323BA
0x1400323a9  mov     dl, 1
0x1400323ab  mov     rcx, rbx
0x1400323ae  call    cs:__imp_WfpNblInfoCleanup
0x1400323b5  nop     dword ptr [rax+rax+00h]
0x1400323ba  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x1400323c1  jge     loc_140032A3D
0x1400323c7  mov     eax, [r13+4]
0x1400323cb  lea     rcx, [rbx-20h]; P
0x1400323cf  test    al, 1
0x1400323d1  jnz     loc_140032A59
0x1400323d7  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x1400323de  jz      short loc_140032437
0x1400323e0  mov     eax, [rcx+18h]
0x1400323e3  shl     rax, 8
0x1400323e7  lea     rdi, [rax+180h]
0x1400323ee  add     rdi, r13
0x1400323f1  cmp     byte ptr [rdi+0D8h], 0
0x1400323f8  jz      loc_140032A79
0x1400323fe  mov     eax, gs:1A4h
0x140032406  cmp     [rbx-8], eax
0x140032409  jz      loc_140032781
0x14003240f  mov     r12, [rdi+0C8h]
0x140032416  lock inc dword ptr [rdi+1Ch]
0x14003241a  mov     rcx, r12; SListHead
0x14003241d  call    cs:__imp_ExQueryDepthSList
0x140032424  nop     dword ptr [rax+rax+00h]
0x140032429  cmp     ax, [rdi+10h]
0x14003242d  jb      loc_14003278D
0x140032433  lock inc dword ptr [rdi+20h]
0x140032437  sub     r13, 0FFFFFFFFFFFFFF80h
0x14003243b  lock inc dword ptr [r13+1Ch]
0x140032440  movzx   edi, word ptr [r13+10h]
0x140032445  mov     rcx, r13; SListHead
0x140032448  call    cs:__imp_ExQueryDepthSList
0x14003244f  nop     dword ptr [rax+rax+00h]
0x140032454  cmp     ax, di
0x140032457  jnb     loc_1400328D6
0x14003245d  mov     rcx, r13; ListHead
0x140032460  mov     rdx, rbx; ListEntry
0x140032463  call    cs:__imp_ExpInterlockedPushEntrySList
0x14003246a  nop     dword ptr [rax+rax+00h]
0x14003246f  mov     rdi, rsi
0x140032472  mov     rbx, rdi
0x140032475  test    rdi, rdi
0x140032478  jz      loc_140032537
0x14003247e  mov     rcx, rdi
0x140032481  mov     eax, [rbp+2Ch]
0x140032484  test    al, 1
0x140032486  jz      loc_140032795
0x14003248c  lea     rcx, [rdi+8]
0x140032490  lea     rax, [rdi+180h]
0x140032497  mov     [rcx], rax
0x14003249a  mov     eax, [rbp+2Ch]
0x14003249d  test    al, 4
0x14003249f  jz      loc_1400325AF
0x1400324a5  movzx   eax, word ptr [rbp+2Ah]
0x1400324a9  test    ax, ax
0x1400324ac  jz      loc_140032686
0x1400324b2  lea     r14, [rax+240h]
0x1400324b9  add     r14, rdi
0x1400324bc  test    r15d, r15d
0x1400324bf  jz      loc_140032692
0x1400324c5  mov     eax, [rbp+58h]
0x1400324c8  mov     [r14+28h], eax
0x1400324cc  mov     [r14], rsi
0x1400324cf  mov     rcx, [rdi+8]
0x1400324d3  test    rcx, rcx
0x1400324d6  jz      short loc_140032517
0x1400324d8  mov     eax, [rbp+58h]
0x1400324db  mov     [rcx], rsi
0x1400324de  mov     [rcx+38h], rbp
0x1400324e2  mov     [rcx+8], r14
0x1400324e6  mov     [rcx+10h], eax
0x1400324e9  mov     [rcx+20h], r14
0x1400324ed  mov     [rcx+28h], eax
0x1400324f0  mov     [rcx+18h], esi
0x1400324f3  mov     dword ptr [rcx+30h], 0
0x1400324fa  mov     [rcx+48h], rsi
0x1400324fe  mov     [rcx+40h], rsi
0x140032502  mov     [rcx+88h], rsi
0x140032509  mov     [rcx+80h], rsi
0x140032510  mov     [rcx+0A8h], rsi
0x140032517  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14003251e  jl      short loc_140032537
0x140032520  xor     r9d, r9d; void *
0x140032523  mov     [rsp+78h+Flags], esi; unsigned int
0x140032527  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140032529  mov     r8d, 2; unsigned int
0x14003252f  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x140032532  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140032537  mov     rax, rbx
0x14003253a  mov     rbx, [rsp+78h+arg_8]
0x140032542  add     rsp, 40h
0x140032546  pop     r15
0x140032548  pop     r14
0x14003254a  pop     r13
0x14003254c  pop     r12
0x14003254e  pop     rdi
0x14003254f  pop     rsi
0x140032550  pop     rbp
0x140032551  retn
0x140032553  js      loc_1400322CD
0x140032559  mov     rcx, [rbx]
0x14003255c  test    rcx, rcx
0x14003255f  jz      loc_14003230B
0x140032565  mov     rax, [rcx+0F8h]
0x14003256c  test    rax, rax
0x14003256f  jnz     loc_14003267B
0x140032575  mov     edx, 1
0x14003257a  lock xadd cs:dword_14011AE28, edx
0x140032582  lea     eax, [rdx+1]
0x140032585  cmp     eax, edx
0x140032587  jb      loc_140032A19
0x14003258d  mov     eax, edx
0x14003258f  mov     [rcx+0F8h], rax
0x140032596  mov     rcx, [rcx]
0x140032599  test    rcx, rcx
0x14003259c  jz      loc_14003230B
0x1400325a2  jmp     short loc_140032565
0x1400325a4  js      loc_1400322F8
0x1400325aa  jmp     loc_140032303
0x1400325af  mov     rax, [rcx]
0x1400325b2  test    rax, rax
0x1400325b5  jz      loc_140032517
0x1400325bb  mov     [rax], rsi
0x1400325be  mov     [rax+38h], rbp
0x1400325c2  mov     [rax+8], rsi
0x1400325c6  mov     [rax+10h], esi
0x1400325c9  mov     [rax+20h], rsi
0x1400325cd  mov     [rax+28h], esi
0x1400325d0  mov     [rax+18h], esi
0x1400325d3  mov     dword ptr [rax+30h], 0
0x1400325da  mov     [rax+48h], rsi
0x1400325de  mov     [rax+40h], rsi
0x1400325e2  mov     [rax+88h], rsi
0x1400325e9  mov     [rax+80h], rsi
0x1400325f0  mov     [rax+0A8h], rsi
0x1400325f7  jmp     loc_140032517
0x1400325fc  xor     esi, esi
0x1400325fe  mov     rbx, rsi
0x140032601  jmp     loc_140032537
0x140032606  mov     rdi, rbx
0x140032609  test    r13w, r13w
0x14003260d  jz      loc_140032472
0x140032613  mov     rax, [rbx+20h]
0x140032617  mov     r9d, [rbp+24h]
0x14003261b  mov     rcx, [rbx+10h]
0x14003261f  mov     r8, [rbx+170h]
0x140032626  mov     edx, [rax+2Ch]
0x140032629  mov     [rsp+78h+arg_0], r9d
0x140032631  test    dl, 2
0x140032634  jz      short loc_140032652
0x140032636  lea     rax, [rbx+230h]
0x14003263d  test    dl, 1
0x140032640  jnz     short loc_140032649
0x140032642  lea     rax, [rbx+180h]
0x140032649  cmp     rcx, rax
0x14003264c  jz      loc_140032716
0x140032652  add     [rbx+38h], r13w
0x140032657  movzx   edx, word ptr [rbx+38h]
0x14003265b  cmp     edx, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x140032661  jg      loc_140032721
  ... truncated ...
```
