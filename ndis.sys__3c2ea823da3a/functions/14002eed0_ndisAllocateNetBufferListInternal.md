# ndisAllocateNetBufferListInternal

- ea: `0x14002eed0`
- end: `0x14002f655`
- name: `ndisAllocateNetBufferListInternal`
- size: `1925`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002e260`
- `0x14002ea00`

## callees

- `0x14002eed0`
- `0x140030450`
- `0x140032aa0`
- `0x140064680`
- `0x140083a40`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e970e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e970e`
- `ntoskrnl!ExAllocatePool2` at `0x14002f314`
- `ntoskrnl!ExAllocatePool2` at `0x14002f404`
- `ntoskrnl!ExAllocatePool2` at `0x14002f5a5`
- `ntoskrnl!ExAllocatePool2` at `0x14002f314`
- `ntoskrnl!ExAllocatePool2` at `0x14002f404`
- `ntoskrnl!ExAllocatePool2` at `0x14002f5a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002efdd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f2a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f382`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002efdd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f2a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f382`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ef63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f270`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f343`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ef63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f270`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f343`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002efbf`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14002efbf`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002eff4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002f2b5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002f2df`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002eff4`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002f2b5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002f2df`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f515`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f515`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f4d9`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f4fe`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f57c`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f4d9`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f4fe`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f57c`
- `NETIO!WfpNblInfoCleanup` at `0x14002f46f`
- `NETIO!WfpNblInfoCleanup` at `0x14002f46f`

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
          v25 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
          if ( v25 + 1 < v25 )
            v25 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
          *((_QWORD *)&i[15].Next + 1) = v25;
        }
      }
    }
    else
    {
      p_Next = &v13->Next;
      v18 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
      if ( v18 + 1 < v18 )
        v18 = _InterlockedExchangeAdd(&dword_14011AE28, 1u);
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
0x14002eed0  mov     [rsp+arg_8], rbx
0x14002eed5  mov     [rsp+arg_10], r8w
0x14002eedb  push    rbp
0x14002eedc  push    rsi
0x14002eedd  push    rdi
0x14002eede  push    r12
0x14002eee0  push    r13
0x14002eee2  push    r14
0x14002eee4  push    r15
0x14002eee6  sub     rsp, 40h
0x14002eeea  movzx   r13d, dx
0x14002eeee  mov     r12, r9
0x14002eef1  movzx   r14d, r8w
0x14002eef5  mov     rsi, rcx
0x14002eef8  test    r13w, 7
0x14002eefe  jnz     loc_14002F64E
0x14002ef04  test    r8w, 7
0x14002ef0a  jnz     loc_14002F64E
0x14002ef10  mov     eax, [rcx+4]
0x14002ef13  mov     r15d, 400h
0x14002ef19  test    al, 1
0x14002ef1b  jnz     loc_14002F192
0x14002ef21  mov     r15d, gs:1A4h
0x14002ef2a  cmp     cs:?ndisMaxNumberOfProcessors@@3KA, 1; ulong ndisMaxNumberOfProcessors
0x14002ef31  mov     dword ptr [r9], 1
0x14002ef38  jz      loc_14002F2D1
0x14002ef3e  mov     ebx, r15d
0x14002ef41  lea     rdi, [rcx+180h]
0x14002ef48  shl     rbx, 8
0x14002ef4c  add     rdi, rbx
0x14002ef4f  cmp     byte ptr [rdi+0D8h], 0
0x14002ef56  jnz     loc_14002EFE9
0x14002ef5c  lea     rcx, [rdi+0D0h]; SpinLock
0x14002ef63  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ef6a  nop     dword ptr [rax+rax+00h]
0x14002ef6f  cmp     byte ptr [rdi+0D8h], 0
0x14002ef76  movzx   r14d, al
0x14002ef7a  jnz     short loc_14002EFD2
0x14002ef7c  mov     [rsp+78h+Depth], 400h; Depth
0x14002ef83  mov     r8, rdi
0x14002ef86  sub     r8, rbx
0x14002ef89  mov     r9d, 200h; PoolType
0x14002ef8f  mov     edx, [r8-0D4h]
0x14002ef96  mov     ecx, [r8-0D8h]
0x14002ef9d  mov     r8, [r8-0C8h]; Free
0x14002efa4  mov     [rsp+78h+Tag], ecx; Tag
0x14002efa8  mov     rcx, rdi; Lookaside
0x14002efab  mov     [rsp+78h+Size], rdx; Size
0x14002efb0  lea     rdx, ndisAllocateFromNPagedPool; Allocate
0x14002efb7  mov     [rsp+78h+Flags], 0; Flags
0x14002efbf  call    cs:__imp_ExInitializeLookasideListEx
0x14002efc6  nop     dword ptr [rax+rax+00h]
0x14002efcb  mov     byte ptr [rdi+0D8h], 1
0x14002efd2  movzx   edx, r14b; NewIrql
0x14002efd6  lea     rcx, [rdi+0D0h]; SpinLock
0x14002efdd  call    cs:__imp_KeReleaseSpinLock
0x14002efe4  nop     dword ptr [rax+rax+00h]
0x14002efe9  lock inc dword ptr [rdi+14h]
0x14002efed  mov     rcx, [rdi+0C0h]; ListHead
0x14002eff4  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002effb  nop     dword ptr [rax+rax+00h]
0x14002f000  mov     rbx, rax
0x14002f003  test    rax, rax
0x14002f006  jz      loc_14002F575
0x14002f00c  movzx   r14d, [rsp+78h+arg_10]
0x14002f015  mov     r15d, 400h
0x14002f01b  test    rbx, rbx
0x14002f01e  jz      loc_14002F64E
0x14002f024  mov     edi, [r12]
0x14002f028  mov     eax, 178h
0x14002f02d  movzx   ebp, word ptr [rbx+3Ah]
0x14002f031  test    edi, edi
0x14002f033  mov     r8d, 170h
0x14002f039  mov     rcx, rbx; void *
0x14002f03c  cmovz   r8d, eax; Size
0x14002f040  xor     edx, edx; Val
0x14002f042  call    memset
0x14002f047  mov     [rbx+20h], rsi
0x14002f04b  mov     dword ptr [rbx+88h], 100h
0x14002f055  test    edi, edi
0x14002f057  jz      short loc_14002F05D
0x14002f059  mov     [rbx+3Ah], bp
0x14002f05d  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002f063  test    eax, eax
0x14002f065  jz      short loc_14002F0B5
0x14002f067  mov     rax, [rbx+0F8h]
0x14002f06e  test    rax, rax
0x14002f071  jnz     loc_14002F12B
0x14002f077  mov     rdx, rbx
0x14002f07a  mov     ecx, 1
0x14002f07f  lock xadd cs:dword_14011AE28, ecx
0x14002f087  lea     eax, [rcx+1]
0x14002f08a  cmp     eax, ecx
0x14002f08c  jb      loc_14002F5E2
0x14002f092  mov     rax, [rdx+0F8h]
0x14002f099  test    rax, rax
0x14002f09c  jnz     loc_14002F178
0x14002f0a2  mov     eax, ecx
0x14002f0a4  inc     ecx
0x14002f0a6  mov     [rdx+0F8h], rax
0x14002f0ad  mov     rdx, [rdx]
0x14002f0b0  test    rdx, rdx
0x14002f0b3  jnz     short loc_14002F092
0x14002f0b5  movzx   eax, byte ptr [rsi+28h]
0x14002f0b9  mov     [rbx+0C8h], al
0x14002f0bf  mov     eax, [rsi+2Ch]
0x14002f0c2  test    al, 2
0x14002f0c4  jz      loc_14002F183
0x14002f0ca  test    al, 1
0x14002f0cc  lea     rax, [rbx+230h]
0x14002f0d3  jnz     short loc_14002F0DC
0x14002f0d5  lea     rax, [rbx+180h]
0x14002f0dc  mov     [rbx+10h], rax
0x14002f0e0  mov     qword ptr [rax], 0
0x14002f0e7  mov     rcx, [rbx+10h]
0x14002f0eb  movzx   eax, word ptr [rsi+2Ah]
0x14002f0ef  mov     [rcx+8], ax
0x14002f0f3  mov     rcx, [rbx+10h]
0x14002f0f7  movzx   eax, word ptr [rsi+2Ah]
0x14002f0fb  mov     [rcx+0Ah], ax
0x14002f0ff  cmp     [rsi+2Ah], r13w
0x14002f104  jb      short loc_14002F183
0x14002f106  mov     rax, [rbx+10h]
0x14002f10a  sub     [rax+0Ah], r13w
0x14002f10f  mov     rax, rbx
0x14002f112  mov     rbx, [rsp+78h+arg_8]
0x14002f11a  add     rsp, 40h
0x14002f11e  pop     r15
0x14002f120  pop     r14
0x14002f122  pop     r13
0x14002f124  pop     r12
0x14002f126  pop     rdi
0x14002f127  pop     rsi
0x14002f128  pop     rbp
0x14002f129  retn
0x14002f12b  js      loc_14002F077
0x14002f131  mov     rcx, [rbx]
0x14002f134  test    rcx, rcx
0x14002f137  jz      loc_14002F0B5
0x14002f13d  mov     rax, [rcx+0F8h]
0x14002f144  test    rax, rax
0x14002f147  jnz     short loc_14002F18E
0x14002f149  mov     edx, 1
0x14002f14e  lock xadd cs:dword_14011AE28, edx
0x14002f156  lea     eax, [rdx+1]
0x14002f159  cmp     eax, edx
0x14002f15b  jb      loc_14002F5D0
0x14002f161  mov     eax, edx
0x14002f163  mov     [rcx+0F8h], rax
0x14002f16a  mov     rcx, [rcx]
0x14002f16d  test    rcx, rcx
0x14002f170  jz      loc_14002F0B5
0x14002f176  jmp     short loc_14002F13D
0x14002f178  js      loc_14002F0A2
0x14002f17e  jmp     loc_14002F0AD
0x14002f183  test    r13w, r13w
0x14002f187  jnz     short loc_14002F1B0
0x14002f189  mov     rax, rbx
0x14002f18c  jmp     short loc_14002F112
0x14002f18e  jns     short loc_14002F16A
0x14002f190  jmp     short loc_14002F149
0x14002f192  mov     eax, [rcx+20h]
0x14002f195  mov     dword ptr [r9], 0
0x14002f19c  lea     rdx, [rax+20h]
0x14002f1a0  cmp     rdx, rax
0x14002f1a3  jnb     loc_14002F597
0x14002f1a9  xor     ebx, ebx
0x14002f1ab  jmp     loc_14002F01B
0x14002f1b0  mov     rax, [rbx+20h]
0x14002f1b4  mov     esi, [rsi+24h]
0x14002f1b7  mov     rcx, [rbx+10h]
0x14002f1bb  mov     r8, [rbx+170h]
0x14002f1c2  mov     edx, [rax+2Ch]
0x14002f1c5  test    dl, 2
0x14002f1c8  jz      short loc_14002F1E2
0x14002f1ca  lea     rax, [rbx+230h]
0x14002f1d1  test    dl, 1
0x14002f1d4  jnz     short loc_14002F1DD
0x14002f1d6  lea     rax, [rbx+180h]
0x14002f1dd  cmp     rcx, rax
0x14002f1e0  jz      short loc_14002F204
0x14002f1e2  add     [rbx+38h], r13w
0x14002f1e7  movzx   edx, word ptr [rbx+38h]
0x14002f1eb  cmp     edx, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x14002f1f1  jg      short loc_14002F20B
0x14002f1f3  movzx   eax, word ptr [rbx+3Ah]
0x14002f1f7  cmp     dx, ax
0x14002f1fa  cmovbe  dx, ax
0x14002f1fe  mov     [rbx+3Ah], dx
0x14002f202  jmp     short loc_14002F20B
0x14002f204  cmp     [rcx+0Ah], r13w
0x14002f209  jb      short loc_14002F1E2
0x14002f20b  test    rcx, rcx
0x14002f20e  jz      short loc_14002F22E
0x14002f210  movzx   eax, word ptr [rcx+0Ah]
0x14002f214  cmp     ax, r13w
0x14002f218  jb      short loc_14002F22E
0x14002f21a  sub     ax, r13w
0x14002f21e  mov     [rcx+0Ah], ax
0x14002f222  or      [rbx+88h], r15d
0x14002f229  jmp     loc_14002F189
0x14002f22e  test    r8, r8
0x14002f231  jz      loc_14002F39B
0x14002f237  cmp     [r8+8], r13w
0x14002f23c  jb      loc_14002F39B
0x14002f242  sub     [r8+0Ah], r13w
0x14002f247  mov     rax, [rbx+10h]
0x14002f24b  mov     [r8], rax
0x14002f24e  or      [rbx+88h], r15d
0x14002f255  mov     [rbx+10h], r8
0x14002f259  mov     qword ptr [rbx+170h], 0
0x14002f264  jmp     loc_14002F189
0x14002f269  lea     rcx, [rdi+0D0h]; SpinLock
0x14002f270  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f277  nop     dword ptr [rax+rax+00h]
0x14002f27c  mov     rdx, [rdi+0C8h]
0x14002f283  lea     rcx, [rdi+0D0h]; SpinLock
0x14002f28a  mov     r8, [rdi+0C0h]
0x14002f291  mov     [rdi+0C0h], rdx
0x14002f298  movzx   edx, al; NewIrql
0x14002f29b  mov     [rdi+0C8h], r8
0x14002f2a2  call    cs:__imp_KeReleaseSpinLock
0x14002f2a9  nop     dword ptr [rax+rax+00h]
0x14002f2ae  mov     rcx, [rdi+0C0h]; ListHead
0x14002f2b5  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002f2bc  nop     dword ptr [rax+rax+00h]
0x14002f2c1  mov     rbx, rax
0x14002f2c4  test    rax, rax
0x14002f2c7  jnz     loc_14002F00C
0x14002f2cd  lock inc dword ptr [rdi+18h]
0x14002f2d1  lea     rdi, [rsi+80h]
0x14002f2d8  lock inc dword ptr [rdi+14h]
0x14002f2dc  mov     rcx, rdi; ListHead
0x14002f2df  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002f2e6  nop     dword ptr [rax+rax+00h]
0x14002f2eb  mov     rbx, rax
0x14002f2ee  test    rax, rax
0x14002f2f1  jnz     loc_14002F392
0x14002f2f7  lock inc dword ptr [rdi+18h]
0x14002f2fb  mov     eax, [rdi+2Ch]
0x14002f2fe  lea     rdx, [rax+20h]
0x14002f302  cmp     rdx, rax
0x14002f305  jb      loc_14002F5C1
0x14002f30b  mov     r8d, [rdi+28h]
0x14002f30f  mov     ecx, 42h ; 'B'
0x14002f314  call    cs:__imp_ExAllocatePool2
0x14002f31b  nop     dword ptr [rax+rax+00h]
0x14002f320  test    rax, rax
0x14002f323  jz      loc_14002F5C1
0x14002f329  xor     ebp, ebp
0x14002f32b  lea     rbx, [rax+20h]
0x14002f32f  mov     [rax], rbp
0x14002f332  test    rbx, rbx
0x14002f335  jz      loc_14002F56C
0x14002f33b  lea     rcx, [rsi+8]; SpinLock
0x14002f33f  mov     [rbx-20h], rsi
0x14002f343  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f34a  nop     dword ptr [rax+rax+00h]
0x14002f34f  mov     rdx, [rsi+10h]
0x14002f353  lea     rcx, [rsi+10h]
0x14002f357  movzx   r8d, al
0x14002f35b  cmp     [rdx+8], rcx
0x14002f35f  jz      short loc_14002F368
0x14002f361  mov     ecx, 3
0x14002f366  int     29h; Win8: RtlFailFast(ecx)
0x14002f368  lea     rax, [rbx-18h]
0x14002f36c  mov     [rax], rdx
0x14002f36f  mov     [rax+8], rcx
0x14002f373  mov     [rdx+8], rax
0x14002f377  movzx   edx, r8b; NewIrql
0x14002f37b  mov     [rcx], rax
0x14002f37e  lea     rcx, [rsi+8]; SpinLock
0x14002f382  call    cs:__imp_KeReleaseSpinLock
0x14002f389  nop     dword ptr [rax+rax+00h]
0x14002f38e  mov     [r12], ebp
0x14002f392  mov     [rbx-8], r15d
0x14002f396  jmp     loc_14002F00C
0x14002f39b  movzx   eax, word ptr [rbx+38h]
0x14002f39f  lea     edi, [r14+r13]
0x14002f3a3  cmp     eax, cs:?ndisMaxCachedNblContextSize@@3JA; long ndisMaxCachedNblContextSize
0x14002f3a9  jg      short loc_14002F3F5
0x14002f3ab  test    r8, r8
0x14002f3ae  jz      short loc_14002F3CC
0x14002f3b0  xor     edx, edx; Tag
0x14002f3b2  mov     qword ptr [rbx+170h], 0
0x14002f3bd  mov     rcx, r8; P
0x14002f3c0  call    cs:__imp_ExFreePoolWithTag
0x14002f3c7  nop     dword ptr [rax+rax+00h]
0x14002f3cc  movzx   eax, word ptr [rbx+38h]
0x14002f3d0  movzx   edx, word ptr [rbx+3Ah]
0x14002f3d4  sub     edx, eax
0x14002f3d6  movzx   eax, di
0x14002f3d9  add     edx, r13d
0x14002f3dc  cmp     eax, edx
0x14002f3de  movzx   eax, r14w
0x14002f3e2  cmovle  di, dx
0x14002f3e6  add     eax, r13d
0x14002f3e9  movzx   edi, di
0x14002f3ec  cmp     edi, eax
0x14002f3ee  jbe     short loc_14002F3F5
  ... truncated ...
```
