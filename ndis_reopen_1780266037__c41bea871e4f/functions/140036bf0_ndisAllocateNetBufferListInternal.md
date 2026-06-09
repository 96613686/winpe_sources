# ndisAllocateNetBufferListInternal

- ea: `0x140036bf0`
- end: `0x140037375`
- name: `ndisAllocateNetBufferListInternal`
- size: `1925`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140035cf0`
- `0x140036490`

## callees

- `0x1400260b0`
- `0x140032cb0`
- `0x140036bf0`
- `0x140069dc0`
- `0x140088cc0`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400370e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eee02`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eee02`
- `ntoskrnl!ExAllocatePool2` at `0x140037034`
- `ntoskrnl!ExAllocatePool2` at `0x140037124`
- `ntoskrnl!ExAllocatePool2` at `0x1400372c5`
- `ntoskrnl!ExAllocatePool2` at `0x140037034`
- `ntoskrnl!ExAllocatePool2` at `0x140037124`
- `ntoskrnl!ExAllocatePool2` at `0x1400372c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036cfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036fc2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400370a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036cfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140036fc2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400370a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036c83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036f90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140037063`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036c83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140036f90`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140037063`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140036cdf`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140036cdf`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036d14`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036fd5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036fff`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036d14`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036fd5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036fff`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140037235`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140037235`
- `ntoskrnl!ExQueryDepthSList` at `0x1400371f9`
- `ntoskrnl!ExQueryDepthSList` at `0x14003721e`
- `ntoskrnl!ExQueryDepthSList` at `0x14003729c`
- `ntoskrnl!ExQueryDepthSList` at `0x1400371f9`
- `ntoskrnl!ExQueryDepthSList` at `0x14003721e`
- `ntoskrnl!ExQueryDepthSList` at `0x14003729c`
- `NETIO!WfpNblInfoCleanup` at `0x14003718f`
- `NETIO!WfpNblInfoCleanup` at `0x14003718f`

## pseudocode

```c
PSLIST_ENTRY __fastcall ndisAllocateNetBufferListInternal(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        int *a4)
{
  int v4; // r13d
  unsigned __int16 v6; // r14
  unsigned int Number; // r15d
  bool v9; // zf
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rdi
  KIRQL v12; // r14
  PSLIST_ENTRY v13; // rbx
  int v14; // edi
  __int16 v15; // bp
  size_t v16; // r8
  _QWORD *p_Next; // rdx
  unsigned int v18; // ecx
  __int64 v19; // rax
  int v20; // eax
  _SLIST_ENTRY *v21; // rax
  _SLIST_ENTRY *i; // rcx
  __int64 v24; // rax
  unsigned int v25; // edx
  unsigned __int64 v26; // rax
  unsigned int v27; // esi
  _SLIST_ENTRY *Next; // rcx
  _SLIST_ENTRY *v29; // r8
  int v30; // edx
  PSLIST_ENTRY v31; // rax
  int v32; // edx
  unsigned __int16 v33; // ax
  KIRQL v34; // al
  __int64 v35; // r8
  unsigned __int64 v36; // rax
  struct _SLIST_ENTRY *Pool2; // rax
  KIRQL v38; // al
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  KIRQL v41; // r8
  _QWORD *v42; // rax
  unsigned __int16 v43; // di
  __int64 v44; // rax
  _SLIST_ENTRY *v45; // rdx
  _SLIST_ENTRY *v46; // rsi
  unsigned int *v47; // rcx
  unsigned __int64 v48; // rax
  char *v49; // rdi
  union _SLIST_HEADER *v50; // rbp
  _SLIST_ENTRY *v51; // rsi
  USHORT v52; // di
  union _SLIST_HEADER *v53; // rcx
  struct _SLIST_ENTRY *v54; // rax

  v4 = a2;
  v6 = a3;
  if ( (a2 & 7) != 0 || (a3 & 7) != 0 )
    return 0;
  if ( (*(_DWORD *)(a1 + 4) & 1) == 0 )
  {
    Number = KeGetPcr()->Prcb.Number;
    v9 = ndisMaxNumberOfProcessors == 1;
    *a4 = 1;
    if ( !v9 )
    {
      v10 = (unsigned __int64)Number << 8;
      v11 = v10 + a1 + 384;
      if ( !*(_BYTE *)(v11 + 216) )
      {
        v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 208));
        if ( !*(_BYTE *)(v11 + 216) )
        {
          ExInitializeLookasideListEx(
            (PLOOKASIDE_LIST_EX)v11,
            ndisAllocateFromNPagedPool,
            *(PFREE_FUNCTION_EX *)(v11 - v10 - 200),
            NonPagedPoolNx,
            0,
            *(unsigned int *)(v11 - v10 - 212),
            *(_DWORD *)(v11 - v10 - 216),
            0x400u);
          *(_BYTE *)(v11 + 216) = 1;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 208), v12);
      }
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 20));
      v13 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(v11 + 192));
      if ( v13 )
        goto LABEL_10;
      if ( ExQueryDepthSList(*(PSLIST_HEADER *)(v11 + 200)) >= 0xAu )
      {
        v34 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 208));
        v35 = *(_QWORD *)(v11 + 192);
        *(_QWORD *)(v11 + 192) = *(_QWORD *)(v11 + 200);
        *(_QWORD *)(v11 + 200) = v35;
        KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 208), v34);
        v13 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(v11 + 192));
        if ( v13 )
          goto LABEL_10;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 24));
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 148));
    v13 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(a1 + 128));
    if ( !v13 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 152));
      v36 = *(unsigned int *)(a1 + 172);
      if ( v36 + 32 < v36
        || (Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, v36 + 32, *(unsigned int *)(a1 + 168))) == 0 )
      {
        *a4 = 0;
        v13 = 0;
        goto LABEL_10;
      }
      v13 = Pool2 + 2;
      Pool2->Next = 0;
      if ( Pool2 == (struct _SLIST_ENTRY *)-32LL )
      {
        *a4 = 0;
        goto LABEL_10;
      }
      Pool2->Next = (_SLIST_ENTRY *)a1;
      v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
      v39 = *(_QWORD *)(a1 + 16);
      v40 = (_QWORD *)(a1 + 16);
      v41 = v38;
      if ( *(_QWORD *)(v39 + 8) != a1 + 16 )
        __fastfail(3u);
      v42 = &v13[-2].Next + 1;
      *v42 = v39;
      v42[1] = v40;
      *(_QWORD *)(v39 + 8) = (char *)v13 - 24;
      *v40 = (char *)v13 - 24;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v41);
      *a4 = 0;
    }
    *((_DWORD *)&v13[-1].Next + 2) = Number;
LABEL_10:
    v6 = a3;
    goto LABEL_11;
  }
  v26 = *(unsigned int *)(a1 + 32);
  *a4 = 0;
  if ( v26 + 32 >= v26 )
  {
    v54 = (struct _SLIST_ENTRY *)ExAllocatePool2(0x100000042LL, v26 + 32, *(unsigned int *)(a1 + 36));
    if ( v54 )
    {
      v54->Next = (_SLIST_ENTRY *)a1;
      v13 = v54 + 2;
    }
    else
    {
      v13 = 0;
    }
  }
  else
  {
    v13 = 0;
  }
LABEL_11:
  if ( !v13 )
    return 0;
  v14 = *a4;
  v15 = *((_WORD *)&v13[3].Next + 5);
  v16 = 368;
  if ( !*a4 )
    v16 = 376;
  memset(v13, 0, v16);
  v13[2].Next = (_SLIST_ENTRY *)a1;
  *((_DWORD *)&v13[8].Next + 2) = 256;
  if ( v14 )
    *((_WORD *)&v13[3].Next + 5) = v15;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    if ( *((__int64 *)&v13[15].Next + 1) > 0 )
    {
      for ( i = v13->Next; i; i = i->Next )
      {
        v24 = *((_QWORD *)&i[15].Next + 1);
        if ( !v24 || v24 < 0 )
        {
          v25 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
          if ( v25 + 1 < v25 )
            v25 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
          *((_QWORD *)&i[15].Next + 1) = v25;
        }
      }
    }
    else
    {
      p_Next = &v13->Next;
      v18 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
      if ( v18 + 1 < v18 )
        v18 = _InterlockedExchangeAdd(&dword_140120E28, 1u);
      do
      {
        if ( (__int64)p_Next[31] <= 0 )
        {
          v19 = v18++;
          p_Next[31] = v19;
        }
        p_Next = (_QWORD *)*p_Next;
      }
      while ( p_Next );
    }
  }
  *((_BYTE *)&v13[12].Next + 8) = *(_BYTE *)(a1 + 40);
  v20 = *(_DWORD *)(a1 + 44);
  if ( (v20 & 2) != 0 )
  {
    v9 = (v20 & 1) == 0;
    v21 = v13 + 35;
    if ( v9 )
      v21 = v13 + 24;
    v13[1].Next = v21;
    v21->Next = 0;
    *((_WORD *)&v13[1].Next->Next + 4) = *(_WORD *)(a1 + 42);
    *((_WORD *)&v13[1].Next->Next + 5) = *(_WORD *)(a1 + 42);
    if ( *(_WORD *)(a1 + 42) >= (unsigned __int16)v4 )
    {
      *((_WORD *)&v13[1].Next->Next + 5) -= v4;
      return v13;
    }
  }
  if ( !(_WORD)v4 )
    return v13;
  v27 = *(_DWORD *)(a1 + 36);
  Next = v13[1].Next;
  v29 = v13[23].Next;
  v30 = *((_DWORD *)&v13[2].Next[2].Next + 3);
  if ( (v30 & 2) == 0 )
    goto LABEL_46;
  v31 = v13 + 35;
  if ( (v30 & 1) == 0 )
    v31 = v13 + 24;
  if ( Next != v31 || *((_WORD *)&Next->Next + 5) < (unsigned __int16)v4 )
  {
LABEL_46:
    *((_WORD *)&v13[3].Next + 4) += v4;
    v32 = *((unsigned __int16 *)&v13[3].Next + 4);
    if ( v32 <= ndisMaxCachedNblContextSize )
    {
      if ( (unsigned __int16)v32 <= *((_WORD *)&v13[3].Next + 5) )
        LOWORD(v32) = *((_WORD *)&v13[3].Next + 5);
      *((_WORD *)&v13[3].Next + 5) = v32;
    }
  }
  if ( Next )
  {
    v33 = *((_WORD *)&Next->Next + 5);
    if ( v33 >= (unsigned __int16)v4 )
    {
      *((_WORD *)&Next->Next + 5) = v33 - v4;
LABEL_54:
      *((_DWORD *)&v13[8].Next + 2) |= 0x400u;
      return v13;
    }
  }
  if ( v29 && *((_WORD *)&v29->Next + 4) >= (unsigned __int16)v4 )
  {
    *((_WORD *)&v29->Next + 5) -= v4;
    v29->Next = v13[1].Next;
    *((_DWORD *)&v13[8].Next + 2) |= 0x400u;
    v13[1].Next = v29;
    v13[23].Next = 0;
    return v13;
  }
  v43 = v6 + v4;
  if ( *((unsigned __int16 *)&v13[3].Next + 4) <= ndisMaxCachedNblContextSize )
  {
    if ( v29 )
    {
      v13[23].Next = 0;
      ExFreePoolWithTag(v29, 0);
    }
    if ( v43 <= v4 + *((unsigned __int16 *)&v13[3].Next + 5) - *((unsigned __int16 *)&v13[3].Next + 4) )
      v43 = v4 + *((_WORD *)&v13[3].Next + 5) - *((_WORD *)&v13[3].Next + 4);
    if ( v43 > v4 + (unsigned int)v6 )
      v27 = 1668170830;
  }
  v44 = ExAllocatePool2(64, v43 + 16LL, v27);
  if ( v44 )
  {
    *(_WORD *)(v44 + 8) = v43;
    *(_WORD *)(v44 + 10) = v43 - v4;
    *(_QWORD *)v44 = v13[1].Next;
    v13[1].Next = (_SLIST_ENTRY *)v44;
    goto LABEL_54;
  }
  *((_WORD *)&v13[3].Next + 4) -= v4;
  v45 = v13[1].Next;
  v46 = v13[2].Next;
  if ( v45 && (*(_DWORD *)(&v13[8].Next + 1) & 0x400) != 0 )
    NdisFreeNetBufferListContext((PNET_BUFFER_LIST)v13, *((_WORD *)&v45->Next + 4) - *((_WORD *)&v45->Next + 5));
  *((_DWORD *)&v13[8].Next + 2) &= ~0x100u;
  if ( ((unsigned __int64)v13[14].Next & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
  {
    LOBYTE(v45) = 1;
    WfpNblInfoCleanup(v13, v45);
  }
  if ( *(int *)ndisNblTrackerMode >= 3 )
    ndisNblTrackerRecordEventInternal((struct _NET_BUFFER_LIST *)v13, 0, 4u, 0, 0);
  v47 = (unsigned int *)&v13[-2];
  if ( (HIDWORD(v46->Next) & 1) != 0 )
  {
    if ( (unsigned __int64)v13 < 0x20 )
      ndisBugCheckEx(0x31u, 3u, (ULONG_PTR)v13, 0);
    ExFreePoolWithTag(v47, 0);
    return 0;
  }
  if ( ndisMaxNumberOfProcessors != 1 )
  {
    v48 = (unsigned __int64)v47[6] << 8;
    v49 = (char *)&v46[24] + v48;
    if ( !v49[216] )
      ndisPplLazyInitializeLookaside((PLOOKASIDE_LIST_EX)((char *)&v46[24] + v48));
    if ( *((_DWORD *)&v13[-1].Next + 2) == KeGetPcr()->Prcb.Number )
      v50 = (union _SLIST_HEADER *)*((_QWORD *)v49 + 24);
    else
      v50 = (union _SLIST_HEADER *)*((_QWORD *)v49 + 25);
    _InterlockedIncrement((volatile signed __int32 *)v49 + 7);
    if ( ExQueryDepthSList(v50) < *((_WORD *)v49 + 8) )
    {
      v53 = v50;
      goto LABEL_94;
    }
    _InterlockedIncrement((volatile signed __int32 *)v49 + 8);
  }
  v51 = v46 + 8;
  _InterlockedIncrement((volatile signed __int32 *)&v51[1].Next + 3);
  v52 = (USHORT)v51[1].Next;
  if ( ExQueryDepthSList((PSLIST_HEADER)v51) < v52 )
  {
    v53 = (union _SLIST_HEADER *)v51;
LABEL_94:
    ExpInterlockedPushEntrySList(v53, v13);
    return 0;
  }
  _InterlockedIncrement((volatile signed __int32 *)&v51[2]);
  (*((void (__fastcall **)(PSLIST_ENTRY, _SLIST_ENTRY *))&v51[3].Next + 1))(v13, v51);
  return 0;
}

```

## disassembly

```asm
0x140036bf0  mov     [rsp+arg_8], rbx
0x140036bf5  mov     [rsp+arg_10], r8w
0x140036bfb  push    rbp
0x140036bfc  push    rsi
0x140036bfd  push    rdi
0x140036bfe  push    r12
0x140036c00  push    r13
0x140036c02  push    r14
0x140036c04  push    r15
0x140036c06  sub     rsp, 40h
0x140036c0a  movzx   r13d, dx
0x140036c0e  mov     r12, r9
0x140036c11  movzx   r14d, r8w
0x140036c15  mov     rsi, rcx
0x140036c18  test    r13w, 7
0x140036c1e  jnz     loc_14003736E
0x140036c24  test    r8w, 7
0x140036c2a  jnz     loc_14003736E
0x140036c30  mov     eax, [rcx+4]
0x140036c33  mov     r15d, 400h
0x140036c39  test    al, 1
0x140036c3b  jnz     loc_140036EB2
0x140036c41  mov     r15d, gs:1A4h
0x140036c4a  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x140036c51  mov     dword ptr [r9], 1
0x140036c58  jz      loc_140036FF1
0x140036c5e  mov     ebx, r15d
0x140036c61  lea     rdi, [rcx+180h]
0x140036c68  shl     rbx, 8
0x140036c6c  add     rdi, rbx
0x140036c6f  cmp     byte ptr [rdi+0D8h], 0
0x140036c76  jnz     loc_140036D09
0x140036c7c  lea     rcx, [rdi+0D0h]; SpinLock
0x140036c83  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140036c8a  nop     dword ptr [rax+rax+00h]
0x140036c8f  cmp     byte ptr [rdi+0D8h], 0
0x140036c96  movzx   r14d, al
0x140036c9a  jnz     short loc_140036CF2
0x140036c9c  mov     [rsp+78h+Depth], 400h; Depth
0x140036ca3  mov     r8, rdi
0x140036ca6  sub     r8, rbx
0x140036ca9  mov     r9d, 200h; PoolType
0x140036caf  mov     edx, [r8-0D4h]
0x140036cb6  mov     ecx, [r8-0D8h]
0x140036cbd  mov     r8, [r8-0C8h]; Free
0x140036cc4  mov     [rsp+78h+Tag], ecx; Tag
0x140036cc8  mov     rcx, rdi; Lookaside
0x140036ccb  mov     [rsp+78h+Size], rdx; Size
0x140036cd0  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x140036cd7  mov     [rsp+78h+Flags], 0; Flags
0x140036cdf  call    cs:__imp_ExInitializeLookasideListEx
0x140036ce6  nop     dword ptr [rax+rax+00h]
0x140036ceb  mov     byte ptr [rdi+0D8h], 1
0x140036cf2  movzx   edx, r14b; NewIrql
0x140036cf6  lea     rcx, [rdi+0D0h]; SpinLock
0x140036cfd  call    cs:__imp_KeReleaseSpinLock
0x140036d04  nop     dword ptr [rax+rax+00h]
0x140036d09  lock inc dword ptr [rdi+14h]
0x140036d0d  mov     rcx, [rdi+0C0h]; ListHead
0x140036d14  call    cs:__imp_ExpInterlockedPopEntrySList
0x140036d1b  nop     dword ptr [rax+rax+00h]
0x140036d20  mov     rbx, rax
0x140036d23  test    rax, rax
0x140036d26  jz      loc_140037295
0x140036d2c  movzx   r14d, [rsp+78h+arg_10]
0x140036d35  mov     r15d, 400h
0x140036d3b  test    rbx, rbx
0x140036d3e  jz      loc_14003736E
0x140036d44  mov     edi, [r12]
0x140036d48  mov     eax, 178h
0x140036d4d  movzx   ebp, word ptr [rbx+3Ah]
0x140036d51  test    edi, edi
0x140036d53  mov     r8d, 170h
0x140036d59  mov     rcx, rbx; void *
0x140036d5c  cmovz   r8d, eax; Size
0x140036d60  xor     edx, edx; Val
0x140036d62  call    memset
0x140036d67  mov     [rbx+20h], rsi
0x140036d6b  mov     dword ptr [rbx+88h], 100h
0x140036d75  test    edi, edi
0x140036d77  jz      short loc_140036D7D
0x140036d79  mov     [rbx+3Ah], bp
0x140036d7d  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140036d83  test    eax, eax
0x140036d85  jz      short loc_140036DD5
0x140036d87  mov     rax, [rbx+0F8h]
0x140036d8e  test    rax, rax
0x140036d91  jnz     loc_140036E4B
0x140036d97  mov     rdx, rbx
0x140036d9a  mov     ecx, 1
0x140036d9f  lock xadd cs:dword_140120E28, ecx
0x140036da7  lea     eax, [rcx+1]
0x140036daa  cmp     eax, ecx
0x140036dac  jb      loc_140037302
0x140036db2  mov     rax, [rdx+0F8h]
0x140036db9  test    rax, rax
0x140036dbc  jnz     loc_140036E98
0x140036dc2  mov     eax, ecx
0x140036dc4  inc     ecx
0x140036dc6  mov     [rdx+0F8h], rax
0x140036dcd  mov     rdx, [rdx]
0x140036dd0  test    rdx, rdx
0x140036dd3  jnz     short loc_140036DB2
0x140036dd5  movzx   eax, byte ptr [rsi+28h]
0x140036dd9  mov     [rbx+0C8h], al
0x140036ddf  mov     eax, [rsi+2Ch]
0x140036de2  test    al, 2
0x140036de4  jz      loc_140036EA3
0x140036dea  test    al, 1
0x140036dec  lea     rax, [rbx+230h]
0x140036df3  jnz     short loc_140036DFC
0x140036df5  lea     rax, [rbx+180h]
0x140036dfc  mov     [rbx+10h], rax
0x140036e00  mov     qword ptr [rax], 0
0x140036e07  mov     rcx, [rbx+10h]
0x140036e0b  movzx   eax, word ptr [rsi+2Ah]
0x140036e0f  mov     [rcx+8], ax
0x140036e13  mov     rcx, [rbx+10h]
0x140036e17  movzx   eax, word ptr [rsi+2Ah]
0x140036e1b  mov     [rcx+0Ah], ax
0x140036e1f  cmp     [rsi+2Ah], r13w
0x140036e24  jb      short loc_140036EA3
0x140036e26  mov     rax, [rbx+10h]
0x140036e2a  sub     [rax+0Ah], r13w
0x140036e2f  mov     rax, rbx
0x140036e32  mov     rbx, [rsp+78h+arg_8]
0x140036e3a  add     rsp, 40h
0x140036e3e  pop     r15
0x140036e40  pop     r14
0x140036e42  pop     r13
0x140036e44  pop     r12
0x140036e46  pop     rdi
0x140036e47  pop     rsi
0x140036e48  pop     rbp
0x140036e49  retn
0x140036e4b  js      loc_140036D97
0x140036e51  mov     rcx, [rbx]
0x140036e54  test    rcx, rcx
0x140036e57  jz      loc_140036DD5
0x140036e5d  mov     rax, [rcx+0F8h]
0x140036e64  test    rax, rax
0x140036e67  jnz     short loc_140036EAE
0x140036e69  mov     edx, 1
0x140036e6e  lock xadd cs:dword_140120E28, edx
0x140036e76  lea     eax, [rdx+1]
0x140036e79  cmp     eax, edx
0x140036e7b  jb      loc_1400372F0
0x140036e81  mov     eax, edx
0x140036e83  mov     [rcx+0F8h], rax
0x140036e8a  mov     rcx, [rcx]
0x140036e8d  test    rcx, rcx
0x140036e90  jz      loc_140036DD5
0x140036e96  jmp     short loc_140036E5D
0x140036e98  js      loc_140036DC2
0x140036e9e  jmp     loc_140036DCD
0x140036ea3  test    r13w, r13w
0x140036ea7  jnz     short loc_140036ED0
0x140036ea9  mov     rax, rbx
0x140036eac  jmp     short loc_140036E32
0x140036eae  jns     short loc_140036E8A
0x140036eb0  jmp     short loc_140036E69
0x140036eb2  mov     eax, [rcx+20h]
0x140036eb5  mov     dword ptr [r9], 0
0x140036ebc  lea     rdx, [rax+20h]
0x140036ec0  cmp     rdx, rax
0x140036ec3  jnb     loc_1400372B7
0x140036ec9  xor     ebx, ebx
0x140036ecb  jmp     loc_140036D3B
0x140036ed0  mov     rax, [rbx+20h]
0x140036ed4  mov     esi, [rsi+24h]
0x140036ed7  mov     rcx, [rbx+10h]
0x140036edb  mov     r8, [rbx+170h]
0x140036ee2  mov     edx, [rax+2Ch]
0x140036ee5  test    dl, 2
0x140036ee8  jz      short loc_140036F02
0x140036eea  lea     rax, [rbx+230h]
0x140036ef1  test    dl, 1
0x140036ef4  jnz     short loc_140036EFD
0x140036ef6  lea     rax, [rbx+180h]
0x140036efd  cmp     rcx, rax
0x140036f00  jz      short loc_140036F24
0x140036f02  add     [rbx+38h], r13w
0x140036f07  movzx   edx, word ptr [rbx+38h]
0x140036f0b  cmp     edx, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x140036f11  jg      short loc_140036F2B
0x140036f13  movzx   eax, word ptr [rbx+3Ah]
0x140036f17  cmp     dx, ax
0x140036f1a  cmovbe  dx, ax
0x140036f1e  mov     [rbx+3Ah], dx
0x140036f22  jmp     short loc_140036F2B
0x140036f24  cmp     [rcx+0Ah], r13w
0x140036f29  jb      short loc_140036F02
0x140036f2b  test    rcx, rcx
0x140036f2e  jz      short loc_140036F4E
0x140036f30  movzx   eax, word ptr [rcx+0Ah]
0x140036f34  cmp     ax, r13w
0x140036f38  jb      short loc_140036F4E
0x140036f3a  sub     ax, r13w
0x140036f3e  mov     [rcx+0Ah], ax
0x140036f42  or      [rbx+88h], r15d
0x140036f49  jmp     loc_140036EA9
0x140036f4e  test    r8, r8
0x140036f51  jz      loc_1400370BB
0x140036f57  cmp     [r8+8], r13w
0x140036f5c  jb      loc_1400370BB
0x140036f62  sub     [r8+0Ah], r13w
0x140036f67  mov     rax, [rbx+10h]
0x140036f6b  mov     [r8], rax
0x140036f6e  or      [rbx+88h], r15d
0x140036f75  mov     [rbx+10h], r8
0x140036f79  mov     qword ptr [rbx+170h], 0
0x140036f84  jmp     loc_140036EA9
0x140036f89  lea     rcx, [rdi+0D0h]; SpinLock
0x140036f90  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140036f97  nop     dword ptr [rax+rax+00h]
0x140036f9c  mov     rdx, [rdi+0C8h]
0x140036fa3  lea     rcx, [rdi+0D0h]; SpinLock
0x140036faa  mov     r8, [rdi+0C0h]
0x140036fb1  mov     [rdi+0C0h], rdx
0x140036fb8  movzx   edx, al; NewIrql
0x140036fbb  mov     [rdi+0C8h], r8
0x140036fc2  call    cs:__imp_KeReleaseSpinLock
0x140036fc9  nop     dword ptr [rax+rax+00h]
0x140036fce  mov     rcx, [rdi+0C0h]; ListHead
0x140036fd5  call    cs:__imp_ExpInterlockedPopEntrySList
0x140036fdc  nop     dword ptr [rax+rax+00h]
0x140036fe1  mov     rbx, rax
0x140036fe4  test    rax, rax
0x140036fe7  jnz     loc_140036D2C
0x140036fed  lock inc dword ptr [rdi+18h]
0x140036ff1  lea     rdi, [rsi+80h]
0x140036ff8  lock inc dword ptr [rdi+14h]
0x140036ffc  mov     rcx, rdi; ListHead
0x140036fff  call    cs:__imp_ExpInterlockedPopEntrySList
0x140037006  nop     dword ptr [rax+rax+00h]
0x14003700b  mov     rbx, rax
0x14003700e  test    rax, rax
0x140037011  jnz     loc_1400370B2
0x140037017  lock inc dword ptr [rdi+18h]
0x14003701b  mov     eax, [rdi+2Ch]
0x14003701e  lea     rdx, [rax+20h]
0x140037022  cmp     rdx, rax
0x140037025  jb      loc_1400372E1
0x14003702b  mov     r8d, [rdi+28h]
0x14003702f  mov     ecx, 42h ; 'B'
0x140037034  call    cs:__imp_ExAllocatePool2
0x14003703b  nop     dword ptr [rax+rax+00h]
0x140037040  test    rax, rax
0x140037043  jz      loc_1400372E1
0x140037049  xor     ebp, ebp
0x14003704b  lea     rbx, [rax+20h]
0x14003704f  mov     [rax], rbp
0x140037052  test    rbx, rbx
0x140037055  jz      loc_14003728C
0x14003705b  lea     rcx, [rsi+8]; SpinLock
0x14003705f  mov     [rbx-20h], rsi
0x140037063  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003706a  nop     dword ptr [rax+rax+00h]
0x14003706f  mov     rdx, [rsi+10h]
0x140037073  lea     rcx, [rsi+10h]
0x140037077  movzx   r8d, al
0x14003707b  cmp     [rdx+8], rcx
0x14003707f  jz      short loc_140037088
0x140037081  mov     ecx, 3
0x140037086  int     29h; Win8: RtlFailFast(ecx)
0x140037088  lea     rax, [rbx-18h]
0x14003708c  mov     [rax], rdx
0x14003708f  mov     [rax+8], rcx
0x140037093  mov     [rdx+8], rax
0x140037097  movzx   edx, r8b; NewIrql
0x14003709b  mov     [rcx], rax
0x14003709e  lea     rcx, [rsi+8]; SpinLock
0x1400370a2  call    cs:__imp_KeReleaseSpinLock
0x1400370a9  nop     dword ptr [rax+rax+00h]
0x1400370ae  mov     [r12], ebp
0x1400370b2  mov     [rbx-8], r15d
0x1400370b6  jmp     loc_140036D2C
0x1400370bb  movzx   eax, word ptr [rbx+38h]
0x1400370bf  lea     edi, [r14+r13]
0x1400370c3  cmp     eax, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x1400370c9  jg      short loc_140037115
0x1400370cb  test    r8, r8
0x1400370ce  jz      short loc_1400370EC
0x1400370d0  xor     edx, edx; Tag
0x1400370d2  mov     qword ptr [rbx+170h], 0
0x1400370dd  mov     rcx, r8; P
0x1400370e0  call    cs:__imp_ExFreePoolWithTag
0x1400370e7  nop     dword ptr [rax+rax+00h]
0x1400370ec  movzx   eax, word ptr [rbx+38h]
0x1400370f0  movzx   edx, word ptr [rbx+3Ah]
0x1400370f4  sub     edx, eax
0x1400370f6  movzx   eax, di
0x1400370f9  add     edx, r13d
0x1400370fc  cmp     eax, edx
0x1400370fe  movzx   eax, r14w
0x140037102  cmovle  di, dx
0x140037106  add     eax, r13d
0x140037109  movzx   edi, di
0x14003710c  cmp     edi, eax
0x14003710e  jbe     short loc_140037115
  ... truncated ...
```
