# NdisAllocateNetBufferList

- ea: `0x1400253b0`
- end: `0x140025d23`
- name: `NdisAllocateNetBufferList`
- size: `2419`
- prototype: `PNET_BUFFER_LIST __stdcall(NDIS_HANDLE PoolHandle, USHORT ContextSize, USHORT ContextBackFill)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140030860`
- `0x140031590`

## callees

- `0x1400253b0`
- `0x1400260b0`
- `0x140032cb0`
- `0x140069dc0`
- `0x140088cc0`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140025976`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140025976`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025ba9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ee6fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025ba9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ee6fa`
- `ntoskrnl!ExAllocatePool2` at `0x140025ade`
- `ntoskrnl!ExAllocatePool2` at `0x140025bff`
- `ntoskrnl!ExAllocatePool2` at `0x140025c7d`
- `ntoskrnl!ExAllocatePool2` at `0x140025ade`
- `ntoskrnl!ExAllocatePool2` at `0x140025bff`
- `ntoskrnl!ExAllocatePool2` at `0x140025c7d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400254cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025a6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025b4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400254cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025a6c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025b4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025459`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025a35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025b0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025459`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025a35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025b0b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400254b1`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400254b1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400254e6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025a7f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025aa9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400254e6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025a7f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025aa9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400256f3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400256f3`
- `ntoskrnl!ExQueryDepthSList` at `0x1400256ad`
- `ntoskrnl!ExQueryDepthSList` at `0x1400256d8`
- `ntoskrnl!ExQueryDepthSList` at `0x140025c54`
- `ntoskrnl!ExQueryDepthSList` at `0x1400256ad`
- `ntoskrnl!ExQueryDepthSList` at `0x1400256d8`
- `ntoskrnl!ExQueryDepthSList` at `0x140025c54`
- `NETIO!WfpNblInfoCleanup` at `0x14002563e`
- `NETIO!WfpNblInfoCleanup` at `0x14002563e`

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
          v37 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
          if ( v37 + 1 < v37 )
            v37 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
          *((_QWORD *)&i[15].Next + 1) = v37;
        }
      }
    }
    else
    {
      p_Next = &v9->Next;
      v13 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
      if ( v13 + 1 < v13 )
        v13 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
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
0x1400253b0  mov     [rsp+arg_8], rbx
0x1400253b5  mov     [rsp+arg_10], r8w
0x1400253bb  push    rbp
0x1400253bc  push    rsi
0x1400253bd  push    rdi
0x1400253be  push    r12
0x1400253c0  push    r13
0x1400253c2  push    r14
0x1400253c4  push    r15
0x1400253c6  sub     rsp, 40h
0x1400253ca  movzx   r13d, dx
0x1400253ce  mov     rbp, rcx
0x1400253d1  test    rcx, rcx
0x1400253d4  jz      loc_14002588C
0x1400253da  movzx   eax, r13w
0x1400253de  and     ax, 7
0x1400253e2  mov     word ptr [rsp+78h+arg_0], ax
0x1400253ea  jnz     loc_14002588C
0x1400253f0  movzx   eax, r8w
0x1400253f4  and     ax, 7
0x1400253f8  mov     word ptr [rsp+78h+arg_0], ax
0x140025400  jnz     loc_14002588C
0x140025406  mov     eax, [rcx+4]
0x140025409  xor     esi, esi
0x14002540b  test    al, 1
0x14002540d  jnz     loc_140025987
0x140025413  mov     r12d, gs:1A4h
0x14002541c  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x140025423  mov     [rsp+78h+arg_0], 1
0x14002542e  jz      loc_140025A9B
0x140025434  mov     ebx, r12d
0x140025437  lea     rdi, [rcx+180h]
0x14002543e  shl     rbx, 8
0x140025442  add     rdi, rbx
0x140025445  cmp     [rdi+0D8h], sil
0x14002544c  jnz     loc_1400254DB
0x140025452  lea     rcx, [rdi+0D0h]; SpinLock
0x140025459  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025460  nop     dword ptr [rax+rax+00h]
0x140025465  movzx   r15d, al
0x140025469  cmp     [rdi+0D8h], sil
0x140025470  jnz     short loc_1400254C4
0x140025472  mov     [rsp+78h+Depth], 400h; Depth
0x140025479  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140025480  mov     r8, rdi
0x140025483  mov     r9d, 200h; PoolType
0x140025489  sub     r8, rbx
0x14002548c  mov     ecx, [r8-0D4h]
0x140025493  mov     eax, [r8-0D8h]
0x14002549a  mov     r8, [r8-0C8h]; Free
0x1400254a1  mov     [rsp+78h+Tag], eax; Tag
0x1400254a5  mov     [rsp+78h+Size], rcx; Size
0x1400254aa  mov     rcx, rdi; Lookaside
0x1400254ad  mov     [rsp+78h+Flags], esi; Flags
0x1400254b1  call    cs:__imp_ExInitializeLookasideListEx
0x1400254b8  nop     dword ptr [rax+rax+00h]
0x1400254bd  mov     byte ptr [rdi+0D8h], 1
0x1400254c4  movzx   edx, r15b; NewIrql
0x1400254c8  lea     rcx, [rdi+0D0h]; SpinLock
0x1400254cf  call    cs:__imp_KeReleaseSpinLock
0x1400254d6  nop     dword ptr [rax+rax+00h]
0x1400254db  lock inc dword ptr [rdi+14h]
0x1400254df  mov     rcx, [rdi+0C0h]; ListHead
0x1400254e6  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400254ed  nop     dword ptr [rax+rax+00h]
0x1400254f2  mov     rbx, rax
0x1400254f5  test    rax, rax
0x1400254f8  jz      loc_140025C4D
0x1400254fe  test    rbx, rbx
0x140025501  jz      loc_14002588E
0x140025507  mov     r15d, [rsp+78h+arg_0]
0x14002550f  xor     edx, edx; Val
0x140025511  movzx   edi, word ptr [rbx+3Ah]
0x140025515  mov     r8d, r15d
0x140025518  xor     r8, 1
0x14002551c  mov     rcx, rbx; void *
0x14002551f  lea     r8, ds:170h[r8*8]; Size
0x140025527  call    memset
0x14002552c  mov     [rbx+20h], rbp
0x140025530  mov     dword ptr [rbx+88h], 100h
0x14002553a  test    r15d, r15d
0x14002553d  jz      short loc_140025543
0x14002553f  mov     [rbx+3Ah], di
0x140025543  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140025549  test    eax, eax
0x14002554b  jz      short loc_14002559B
0x14002554d  mov     rax, [rbx+0F8h]
0x140025554  test    rax, rax
0x140025557  jnz     loc_1400257E3
0x14002555d  mov     rdx, rbx
0x140025560  mov     ecx, 1
0x140025565  lock xadd cs:dword_140120E28, ecx
0x14002556d  lea     eax, [rcx+1]
0x140025570  cmp     eax, ecx
0x140025572  jb      loc_140025CBB
0x140025578  mov     rax, [rdx+0F8h]
0x14002557f  test    rax, rax
0x140025582  jnz     loc_140025834
0x140025588  mov     eax, ecx
0x14002558a  inc     ecx
0x14002558c  mov     [rdx+0F8h], rax
0x140025593  mov     rdx, [rdx]
0x140025596  test    rdx, rdx
0x140025599  jnz     short loc_140025578
0x14002559b  movzx   eax, byte ptr [rbp+28h]
0x14002559f  mov     [rbx+0C8h], al
0x1400255a5  mov     eax, [rbp+2Ch]
0x1400255a8  test    al, 2
0x1400255aa  jz      loc_140025896
0x1400255b0  test    al, 1
0x1400255b2  lea     rax, [rbx+230h]
0x1400255b9  jnz     short loc_1400255C2
0x1400255bb  lea     rax, [rbx+180h]
0x1400255c2  mov     [rbx+10h], rax
0x1400255c6  mov     [rax], rsi
0x1400255c9  mov     rcx, [rbx+10h]
0x1400255cd  movzx   eax, word ptr [rbp+2Ah]
0x1400255d1  mov     [rcx+8], ax
0x1400255d5  mov     rcx, [rbx+10h]
0x1400255d9  movzx   eax, word ptr [rbp+2Ah]
0x1400255dd  mov     [rcx+0Ah], ax
0x1400255e1  cmp     [rbp+2Ah], r13w
0x1400255e6  jb      loc_140025896
0x1400255ec  mov     rax, [rbx+10h]
0x1400255f0  mov     rdi, rbx
0x1400255f3  mov     rcx, rbx
0x1400255f6  sub     [rax+0Ah], r13w
0x1400255fb  jmp     loc_140025711
0x140025600  sub     [rbx+38h], r13w
0x140025605  mov     rdx, [rbx+10h]
0x140025609  mov     r13, [rbx+20h]
0x14002560d  test    rdx, rdx
0x140025610  jz      short loc_140025622
0x140025612  test    dword ptr [rbx+88h], 400h
0x14002561c  jnz     loc_140025C35
0x140025622  and     dword ptr [rbx+88h], 0FFFFFEFFh
0x14002562c  test    qword ptr [rbx+0E0h], 0FFFFFFFFFFFFFFFCh
0x140025637  jz      short loc_14002564A
0x140025639  mov     dl, 1
0x14002563b  mov     rcx, rbx
0x14002563e  call    cs:__imp_WfpNblInfoCleanup
0x140025645  nop     dword ptr [rax+rax+00h]
0x14002564a  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140025651  jge     loc_140025CCD
0x140025657  mov     eax, [r13+4]
0x14002565b  lea     rcx, [rbx-20h]; P
0x14002565f  test    al, 1
0x140025661  jnz     loc_140025CE9
0x140025667  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x14002566e  jz      short loc_1400256C7
0x140025670  mov     eax, [rcx+18h]
0x140025673  shl     rax, 8
0x140025677  lea     rdi, [rax+180h]
0x14002567e  add     rdi, r13
0x140025681  cmp     byte ptr [rdi+0D8h], 0
0x140025688  jz      loc_140025D09
0x14002568e  mov     eax, gs:1A4h
0x140025696  cmp     [rbx-8], eax
0x140025699  jz      loc_140025A11
0x14002569f  mov     r12, [rdi+0C8h]
0x1400256a6  lock inc dword ptr [rdi+1Ch]
0x1400256aa  mov     rcx, r12; SListHead
0x1400256ad  call    cs:__imp_ExQueryDepthSList
0x1400256b4  nop     dword ptr [rax+rax+00h]
0x1400256b9  cmp     ax, [rdi+10h]
0x1400256bd  jb      loc_140025A1D
0x1400256c3  lock inc dword ptr [rdi+20h]
0x1400256c7  sub     r13, 0FFFFFFFFFFFFFF80h
0x1400256cb  lock inc dword ptr [r13+1Ch]
0x1400256d0  movzx   edi, word ptr [r13+10h]
0x1400256d5  mov     rcx, r13; SListHead
0x1400256d8  call    cs:__imp_ExQueryDepthSList
0x1400256df  nop     dword ptr [rax+rax+00h]
0x1400256e4  cmp     ax, di
0x1400256e7  jnb     loc_140025B66
0x1400256ed  mov     rcx, r13; ListHead
0x1400256f0  mov     rdx, rbx; ListEntry
0x1400256f3  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400256fa  nop     dword ptr [rax+rax+00h]
0x1400256ff  mov     rdi, rsi
0x140025702  mov     rbx, rdi
0x140025705  test    rdi, rdi
0x140025708  jz      loc_1400257C7
0x14002570e  mov     rcx, rdi
0x140025711  mov     eax, [rbp+2Ch]
0x140025714  test    al, 1
0x140025716  jz      loc_140025A25
0x14002571c  lea     rcx, [rdi+8]
0x140025720  lea     rax, [rdi+180h]
0x140025727  mov     [rcx], rax
0x14002572a  mov     eax, [rbp+2Ch]
0x14002572d  test    al, 4
0x14002572f  jz      loc_14002583F
0x140025735  movzx   eax, word ptr [rbp+2Ah]
0x140025739  test    ax, ax
0x14002573c  jz      loc_140025916
0x140025742  lea     r14, [rax+240h]
0x140025749  add     r14, rdi
0x14002574c  test    r15d, r15d
0x14002574f  jz      loc_140025922
0x140025755  mov     eax, [rbp+58h]
0x140025758  mov     [r14+28h], eax
0x14002575c  mov     [r14], rsi
0x14002575f  mov     rcx, [rdi+8]
0x140025763  test    rcx, rcx
0x140025766  jz      short loc_1400257A7
0x140025768  mov     eax, [rbp+58h]
0x14002576b  mov     [rcx], rsi
0x14002576e  mov     [rcx+38h], rbp
0x140025772  mov     [rcx+8], r14
0x140025776  mov     [rcx+10h], eax
0x140025779  mov     [rcx+20h], r14
0x14002577d  mov     [rcx+28h], eax
0x140025780  mov     [rcx+18h], esi
0x140025783  mov     dword ptr [rcx+30h], 0
0x14002578a  mov     [rcx+48h], rsi
0x14002578e  mov     [rcx+40h], rsi
0x140025792  mov     [rcx+88h], rsi
0x140025799  mov     [rcx+80h], rsi
0x1400257a0  mov     [rcx+0A8h], rsi
0x1400257a7  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x1400257ae  jl      short loc_1400257C7
0x1400257b0  xor     r9d, r9d; void *
0x1400257b3  mov     [rsp+78h+Flags], esi; unsigned int
0x1400257b7  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x1400257b9  mov     r8d, 2; unsigned int
0x1400257bf  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x1400257c2  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x1400257c7  mov     rax, rbx
0x1400257ca  mov     rbx, [rsp+78h+arg_8]
0x1400257d2  add     rsp, 40h
0x1400257d6  pop     r15
0x1400257d8  pop     r14
0x1400257da  pop     r13
0x1400257dc  pop     r12
0x1400257de  pop     rdi
0x1400257df  pop     rsi
0x1400257e0  pop     rbp
0x1400257e1  retn
0x1400257e3  js      loc_14002555D
0x1400257e9  mov     rcx, [rbx]
0x1400257ec  test    rcx, rcx
0x1400257ef  jz      loc_14002559B
0x1400257f5  mov     rax, [rcx+0F8h]
0x1400257fc  test    rax, rax
0x1400257ff  jnz     loc_14002590B
0x140025805  mov     edx, 1
0x14002580a  lock xadd cs:dword_140120E28, edx
0x140025812  lea     eax, [rdx+1]
0x140025815  cmp     eax, edx
0x140025817  jb      loc_140025CA9
0x14002581d  mov     eax, edx
0x14002581f  mov     [rcx+0F8h], rax
0x140025826  mov     rcx, [rcx]
0x140025829  test    rcx, rcx
0x14002582c  jz      loc_14002559B
0x140025832  jmp     short loc_1400257F5
0x140025834  js      loc_140025588
0x14002583a  jmp     loc_140025593
0x14002583f  mov     rax, [rcx]
0x140025842  test    rax, rax
0x140025845  jz      loc_1400257A7
0x14002584b  mov     [rax], rsi
0x14002584e  mov     [rax+38h], rbp
0x140025852  mov     [rax+8], rsi
0x140025856  mov     [rax+10h], esi
0x140025859  mov     [rax+20h], rsi
0x14002585d  mov     [rax+28h], esi
0x140025860  mov     [rax+18h], esi
0x140025863  mov     dword ptr [rax+30h], 0
0x14002586a  mov     [rax+48h], rsi
0x14002586e  mov     [rax+40h], rsi
0x140025872  mov     [rax+88h], rsi
0x140025879  mov     [rax+80h], rsi
0x140025880  mov     [rax+0A8h], rsi
0x140025887  jmp     loc_1400257A7
0x14002588c  xor     esi, esi
0x14002588e  mov     rbx, rsi
0x140025891  jmp     loc_1400257C7
0x140025896  mov     rdi, rbx
0x140025899  test    r13w, r13w
0x14002589d  jz      loc_140025702
0x1400258a3  mov     rax, [rbx+20h]
0x1400258a7  mov     r9d, [rbp+24h]
0x1400258ab  mov     rcx, [rbx+10h]
0x1400258af  mov     r8, [rbx+170h]
0x1400258b6  mov     edx, [rax+2Ch]
0x1400258b9  mov     [rsp+78h+arg_0], r9d
0x1400258c1  test    dl, 2
0x1400258c4  jz      short loc_1400258E2
0x1400258c6  lea     rax, [rbx+230h]
0x1400258cd  test    dl, 1
0x1400258d0  jnz     short loc_1400258D9
0x1400258d2  lea     rax, [rbx+180h]
0x1400258d9  cmp     rcx, rax
0x1400258dc  jz      loc_1400259A6
0x1400258e2  add     [rbx+38h], r13w
0x1400258e7  movzx   edx, word ptr [rbx+38h]
0x1400258eb  cmp     edx, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x1400258f1  jg      loc_1400259B1
  ... truncated ...
```
