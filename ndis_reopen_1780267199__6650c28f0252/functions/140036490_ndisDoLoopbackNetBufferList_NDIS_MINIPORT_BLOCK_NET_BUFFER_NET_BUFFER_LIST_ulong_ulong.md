# ndisDoLoopbackNetBufferList(_NDIS_MINIPORT_BLOCK *,_NET_BUFFER *,_NET_BUFFER_LIST *,ulong,ulong)

- ea: `0x140036490`
- end: `0x140036be1`
- name: `?ndisDoLoopbackNetBufferList@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NET_BUFFER@@PEAU_NET_BUFFER_LIST@@KK@Z`
- size: `1873`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NET_BUFFER *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140036190`

## callees

- `0x140010ff0`
- `0x1400231d0`
- `0x1400260b0`
- `0x140036490`
- `0x140036bf0`
- `0x140037380`
- `0x140037bb0`
- `0x1400eb4c0`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400367c0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036a1d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400367c0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036a1d`
- `ntoskrnl!DbgPrint` at `0x140036862`
- `ntoskrnl!DbgPrint` at `0x140036b93`
- `ntoskrnl!DbgPrint` at `0x140036862`
- `ntoskrnl!DbgPrint` at `0x140036b93`
- `ntoskrnl!MmSizeOfMdl` at `0x1400364b4`
- `ntoskrnl!MmSizeOfMdl` at `0x1400364b4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036b01`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036b33`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036b65`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036b01`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036b33`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140036b65`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140036574`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140036574`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036bab`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036bd0`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036bab`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036bd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036627`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003668b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036b7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036627`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003668b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036b7b`
- `ntoskrnl!ExAllocatePool2` at `0x1400364f1`
- `ntoskrnl!ExAllocatePool2` at `0x1400364f1`

## pseudocode

```c
void __fastcall ndisDoLoopbackNetBufferList(
        struct _NDIS_MINIPORT_BLOCK *a1,
        struct _NET_BUFFER *a2,
        struct _NET_BUFFER_LIST *a3,
        unsigned int a4,
        char a5)
{
  SIZE_T DataLength; // rsi
  SIZE_T v7; // rbx
  struct _MDL *Pool2; // rax
  struct _MDL *v9; // r14
  unsigned __int64 v10; // r8
  NDIS_HANDLE v11; // r15
  __int64 v12; // rax
  struct _NET_BUFFER_LIST *v13; // rdi
  unsigned __int64 v14; // rbx
  unsigned int v15; // ecx
  struct _MDL *v16; // rax
  ULONG ByteCount; // edx
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r15
  __int64 v21; // r12
  char v22; // r13
  struct _NET_BUFFER_LIST *v23; // rsi
  char v24; // r14
  unsigned __int64 v25; // rbx
  __int64 v26; // rax
  unsigned __int64 v27; // r15
  KIRQL v28; // al
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rbx
  __int64 v31; // rdx
  __int64 v32; // rcx
  char *v33; // r12
  _MDL *CurrentMdl; // r15
  char *MappedSystemVa; // r8
  __int64 CurrentMdlOffset; // rdx
  unsigned int v37; // eax
  __int64 v38; // rbx
  ULONG v39; // esi
  struct _MDL *Next; // r15
  char *i; // r12
  bool v42; // zf
  struct _NET_BUFFER_LIST *v43; // rdx
  __int64 v44; // r12
  __int64 v45; // r15
  char v46; // r13
  struct _NET_BUFFER_LIST *Alignment; // rsi
  char v48; // r14
  unsigned __int64 v49; // rbx
  __int64 v50; // rax
  unsigned __int64 v51; // r15
  unsigned __int64 v52; // rdx
  __int64 v53; // rcx
  KIRQL CurrentIrql; // al
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // rbx
  __int64 v57; // rdx
  PVOID v58; // rax
  ULONG v59; // ecx
  __int64 v60; // rbx
  struct _MDL *P; // [rsp+40h] [rbp-48h]
  int v63; // [rsp+98h] [rbp+10h] BYREF
  struct _NET_BUFFER_LIST *v64; // [rsp+A0h] [rbp+18h]
  unsigned int v65; // [rsp+A8h] [rbp+20h]

  v65 = a4;
  v64 = a3;
  DataLength = a2->DataLength;
  v7 = (MmSizeOfMdl((PVOID)0xFFF, DataLength) + 7) & 0xFFFFFFF8;
  if ( (DataLength + v7) >> 32 )
    return;
  Pool2 = (struct _MDL *)ExAllocatePool2(64, (unsigned int)(DataLength + v7), 1886143566);
  P = Pool2;
  v9 = Pool2;
  if ( !Pool2 )
    return;
  v10 = (unsigned __int64)Pool2 + v7;
  if ( (struct _MDL *)((char *)Pool2 + v7) < Pool2 )
  {
    ExFreePoolWithTag(Pool2, 0);
    return;
  }
  Pool2->ByteCount = DataLength;
  Pool2->Next = 0;
  Pool2->Size = 8 * (((DataLength + (v10 & 0xFFF) + 4095) >> 12) + 6);
  Pool2->MdlFlags = 0;
  Pool2->StartVa = (PVOID)(v10 & 0xFFFFFFFFFFFFF000uLL);
  Pool2->ByteOffset = v10 & 0xFFF;
  MmBuildMdlForNonPagedPool(Pool2);
  v11 = ndisNetBufferListPool;
  v63 = 0;
  if ( !ndisNetBufferListPool )
  {
    DbgPrint("NdisAllocateNetBufferAndNetBufferList: Pool is NULL\n");
    goto LABEL_12;
  }
  if ( (*((_DWORD *)ndisNetBufferListPool + 11) & 5) != 1 )
  {
    DbgPrint("NdisAllocateNetBufferAndNetBufferList: Pool %p wrong pool type.\n", ndisNetBufferListPool);
LABEL_12:
    if ( (v9->MdlFlags & 0x20) != 0 )
      MmUnmapLockedPages(v9->MappedSystemVa, v9);
    ExFreePoolWithTag(v9, 0);
    return;
  }
  v12 = ndisAllocateNetBufferListInternal(ndisNetBufferListPool, 0, 0, &v63);
  v13 = (struct _NET_BUFFER_LIST *)v12;
  if ( v12 )
  {
    v14 = v12 + 384;
    memset((void *)(v12 + 384), 0, 0xB0u);
    v15 = 0;
    *(_QWORD *)(v14 + 32) = v9;
    v16 = v9;
    *(_DWORD *)(v14 + 24) = DataLength;
    *(_QWORD *)(v14 + 56) = v11;
    do
    {
      ByteCount = v16->ByteCount;
      if ( v15 < ByteCount )
        break;
      v16 = v16->Next;
      v15 -= ByteCount;
    }
    while ( v16 );
    *(_QWORD *)(v14 + 8) = v16;
    *(_DWORD *)(v14 + 16) = v15;
    v13->Link.Region = v14;
    if ( *(int *)ndisNblTrackerMode >= 3 )
      ndisNblTrackerRecordEventInternal(v13, 0, 3u, 0, 0);
  }
  if ( !v13 )
    goto LABEL_12;
  v32 = *(_QWORD *)(v13->Link.Region + 32);
  if ( (*(_BYTE *)(v32 + 10) & 5) != 0 )
    v33 = *(char **)(v32 + 24);
  else
    v33 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v32, 0, MmCached, 0, 0, 0x40000000u);
  if ( !v33
    || ((CurrentMdl = a2->CurrentMdl, (CurrentMdl->MdlFlags & 5) == 0)
      ? (MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u))
      : (MappedSystemVa = (char *)CurrentMdl->MappedSystemVa),
        !MappedSystemVa) )
  {
    NdisFreeNetBufferList(v13);
    goto LABEL_12;
  }
  CurrentMdlOffset = a2->CurrentMdlOffset;
  v37 = DataLength;
  if ( CurrentMdl->ByteCount - (int)CurrentMdlOffset <= (unsigned int)DataLength )
    v37 = CurrentMdl->ByteCount - CurrentMdlOffset;
  v38 = v37;
  v39 = DataLength - v37;
  memmove(v33, &MappedSystemVa[CurrentMdlOffset], v37);
  Next = CurrentMdl->Next;
  for ( i = &v33[v38]; Next; i += v60 )
  {
    if ( !v39 )
      break;
    v58 = (Next->MdlFlags & 5) != 0
        ? Next->MappedSystemVa
        : MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000000u);
    if ( !v58 )
      break;
    v59 = v39;
    if ( v39 >= Next->ByteCount )
      v59 = Next->ByteCount;
    v60 = v59;
    v39 -= v59;
    memmove(i, v58, v59);
    Next = Next->Next;
  }
  v13->Flags |= 0x80u;
  v13->NblFlags |= 0x8000u;
  v42 = (a5 & 2) == 0;
  v43 = v64;
  v13->SourceHandle = v64->SourceHandle;
  v13->NetBufferListInfo[5] = v43->SourceHandle;
  if ( !v42 )
    v13->Flags |= 0x200u;
  if ( *(_DWORD *)ndisNblTrackerMode )
  {
    v44 = 0;
    v45 = 0;
    v46 = 0;
    if ( *(int *)ndisNblTrackerMode >= 3 )
      ndisNblTrackerRecordEventInternal(v13, (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA8, 0x9Bu, 0, 0);
    Alignment = v13;
    v48 = 0;
    while ( 1 )
    {
      v49 = (unsigned __int64)Alignment->NetBufferListInfo[27];
      while ( Alignment->NetBufferListInfo[27] == (void *)v49 )
      {
        if ( v49 )
        {
          if ( (v49 & 4) != 0 )
            goto LABEL_98;
        }
        else if ( !Alignment->SourceHandle )
        {
          Alignment->SourceHandle = (void *)ndisSourceHandleFromOwner(168);
        }
        if ( ndisNblTrackerCanNblBeTracked(Alignment) )
        {
          if ( Alignment->SourceHandle || Alignment->ParentNetBufferList )
          {
            ++v44;
            v50 = 0;
          }
          else
          {
            ++v44;
            v50 = 24;
          }
          goto LABEL_73;
        }
LABEL_98:
        v50 = 4;
LABEL_73:
        Alignment->NetBufferListInfo[27] = (void *)v50;
        Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
        if ( !Alignment )
          break;
      }
      if ( (v49 & 1) == 0 )
        goto LABEL_79;
      v51 = v45 - v44;
      if ( !v51 )
        goto LABEL_79;
      if ( v46 || v48 )
      {
        v52 = (v49 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v49 >> 1) & 1) + 3);
        if ( !v46 )
          goto LABEL_84;
        goto LABEL_78;
      }
      v48 = 1;
      CurrentIrql = KeGetCurrentIrql();
      v55 = v49;
      v56 = v49 & 0xFFFFFFFFFFFFFFF8uLL;
      v57 = 16 * (((v55 >> 1) & 1) + 3);
      if ( CurrentIrql == 2 )
      {
        v46 = 1;
        v52 = v56 + v57;
LABEL_78:
        v53 = KeGetPcr()->Prcb.Number << 12;
        *(_QWORD *)(v53 + *(_QWORD *)v52) += v51;
        goto LABEL_79;
      }
      v46 = 0;
      v52 = v56 + v57;
LABEL_84:
      _InterlockedAdd64((volatile signed __int64 *)(v52 + 8), v51);
LABEL_79:
      v45 = v44;
      if ( !Alignment )
      {
        v9 = P;
        break;
      }
    }
  }
  ndisInvokeNextReceiveHandler(
    v13,
    v65,
    1,
    2,
    (struct _NDIS_FILTER_BLOCK *)a1->Next.IndicateNetBufferListsObject,
    a1->Next.IndicateNetBufferListsContext,
    (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))a1->Next.IndicateNetBufferListsHandler);
  if ( *(_DWORD *)ndisNblTrackerMode )
  {
    v21 = 0;
    v20 = 0;
    v22 = 0;
    if ( *(int *)ndisNblTrackerMode >= 3 )
      ndisNblTrackerRecordEventInternal(v13, 0, 0x9Cu, (void *)0xA8, 0);
    v23 = v13;
    v24 = 0;
    while ( 1 )
    {
      v25 = (unsigned __int64)v23->NetBufferListInfo[27];
      while ( v23->NetBufferListInfo[27] == (void *)v25 )
      {
        if ( v25 )
        {
          if ( (v25 & 4) != 0 )
            goto LABEL_47;
        }
        else if ( !v23->SourceHandle )
        {
          v23->SourceHandle = (void *)ndisSourceHandleFromOwner(0);
        }
        if ( ndisNblTrackerCanNblBeTracked(v23) )
        {
          if ( v23->SourceHandle != (void *)168 || v23->ParentNetBufferList )
          {
            ++v21;
            v26 = 168;
          }
          else
          {
            ++v21;
            v26 = 24;
          }
          goto LABEL_34;
        }
LABEL_47:
        v26 = 172;
LABEL_34:
        v23->NetBufferListInfo[27] = (void *)v26;
        v23 = (struct _NET_BUFFER_LIST *)v23->Link.Alignment;
        if ( !v23 )
          break;
      }
      if ( (v25 & 1) == 0 )
        goto LABEL_17;
      v27 = v20 - v21;
      if ( !v27 )
        goto LABEL_17;
      if ( v22 || v24 )
      {
        v18 = (v25 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v25 >> 1) & 1) + 3);
        if ( !v22 )
          goto LABEL_41;
        goto LABEL_16;
      }
      v24 = 1;
      v28 = KeGetCurrentIrql();
      v29 = v25;
      v30 = v25 & 0xFFFFFFFFFFFFFFF8uLL;
      v31 = 16 * (((v29 >> 1) & 1) + 3);
      if ( v28 == 2 )
      {
        v22 = 1;
        v18 = v30 + v31;
LABEL_16:
        v19 = KeGetPcr()->Prcb.Number << 12;
        *(_QWORD *)(v19 + *(_QWORD *)v18) += v27;
        goto LABEL_17;
      }
      v18 = v30 + v31;
LABEL_41:
      _InterlockedAdd64((volatile signed __int64 *)(v18 + 8), v27);
LABEL_17:
      v20 = v21;
      if ( !v23 )
      {
        v9 = P;
        break;
      }
    }
  }
  if ( (v9->MdlFlags & 0x20) != 0 )
    MmUnmapLockedPages(v9->MappedSystemVa, v9);
  ExFreePoolWithTag(v9, 0);
  NdisFreeNetBufferList(v13);
}

```

## disassembly

```asm
0x140036490  mov     [rsp+arg_18], r9d
0x140036495  mov     [rsp+arg_10], r8
0x14003649a  mov     [rsp+arg_0], rcx
0x14003649f  push    rbx
0x1400364a0  push    rsi
0x1400364a1  push    r13
0x1400364a3  sub     rsp, 70h
0x1400364a7  mov     esi, [rdx+18h]
0x1400364aa  mov     r13, rdx
0x1400364ad  mov     edx, esi; Length
0x1400364af  mov     ecx, 0FFFh; Base
0x1400364b4  call    cs:__imp_MmSizeOfMdl
0x1400364bb  nop     dword ptr [rax+rax+00h]
0x1400364c0  lea     rbx, [rax+7]
0x1400364c4  mov     eax, 0FFFFFFF8h
0x1400364c9  and     rbx, rax
0x1400364cc  lea     rax, [rsi+rbx]
0x1400364d0  mov     rcx, rax
0x1400364d3  shr     rcx, 20h
0x1400364d7  test    ecx, ecx
0x1400364d9  jnz     loc_1400366B3
0x1400364df  mov     edx, eax
0x1400364e1  mov     ecx, 40h ; '@'
0x1400364e6  mov     r8d, 706C444Eh
0x1400364ec  mov     [rsp+88h+var_30], r14
0x1400364f1  call    cs:__imp_ExAllocatePool2
0x1400364f8  nop     dword ptr [rax+rax+00h]
0x1400364fd  mov     [rsp+88h+P], rax
0x140036502  mov     r14, rax
0x140036505  test    rax, rax
0x140036508  jz      loc_1400366AE
0x14003650e  lea     r8, [rax+rbx]
0x140036512  cmp     r8, rax
0x140036515  jb      loc_140036B76
0x14003651b  mov     edx, r8d
0x14003651e  mov     [rsp+88h+var_20], rdi
0x140036523  mov     ecx, edx
0x140036525  mov     [rsp+88h+var_28], r12
0x14003652a  and     ecx, 0FFFh
0x140036530  mov     [rsp+88h+var_38], r15
0x140036535  add     rcx, 0FFFh
0x14003653c  mov     [rax+28h], esi
0x14003653f  add     rcx, rsi
0x140036542  xor     r12d, r12d
0x140036545  shr     rcx, 0Ch
0x140036549  and     r8, 0FFFFFFFFFFFFF000h
0x140036550  add     cx, 6
0x140036554  mov     [rax], r12
0x140036557  shl     cx, 3
0x14003655b  and     edx, 0FFFh
0x140036561  mov     [rax+8], cx
0x140036565  mov     rcx, rax; MemoryDescriptorList
0x140036568  mov     [rax+0Ah], r12w
0x14003656d  mov     [rax+20h], r8
0x140036571  mov     [rax+2Ch], edx
0x140036574  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003657b  nop     dword ptr [rax+rax+00h]
0x140036580  mov     r15, cs:?ndisNetBufferListPool@@3PEAXEA; void * ndisNetBufferListPool
0x140036587  mov     [rsp+88h+arg_8], r12d
0x14003658f  test    r15, r15
0x140036592  jz      loc_140036B8C
0x140036598  mov     eax, [r15+2Ch]
0x14003659c  and     al, 5
0x14003659e  cmp     al, 1
0x1400365a0  jnz     loc_140036858
0x1400365a6  xor     r8d, r8d
0x1400365a9  lea     r9, [rsp+88h+arg_8]
0x1400365b1  xor     edx, edx
0x1400365b3  mov     rcx, r15
0x1400365b6  call    ndisAllocateNetBufferListInternal
0x1400365bb  mov     rdi, rax
0x1400365be  test    rax, rax
0x1400365c1  jz      short loc_14003660E
0x1400365c3  lea     rbx, [rax+180h]
0x1400365ca  xor     edx, edx; Val
0x1400365cc  mov     rcx, rbx; void *
0x1400365cf  mov     r8d, 0B0h; Size
0x1400365d5  call    memset
0x1400365da  mov     ecx, r12d
0x1400365dd  mov     [rbx+20h], r14
0x1400365e1  mov     rax, r14
0x1400365e4  mov     [rbx+18h], esi
0x1400365e7  mov     [rbx+38h], r15
0x1400365eb  mov     edx, [rax+28h]
0x1400365ee  cmp     ecx, edx
0x1400365f0  jnb     loc_140036873
0x1400365f6  mov     [rbx+8], rax
0x1400365fa  mov     [rbx+10h], ecx
0x1400365fd  mov     [rdi+8], rbx
0x140036601  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140036608  jge     loc_14003683B
0x14003660e  test    rdi, rdi
0x140036611  jnz     loc_140036886
0x140036617  test    byte ptr [r14+0Ah], 20h
0x14003661c  jnz     loc_140036BC9
0x140036622  xor     edx, edx; Tag
0x140036624  mov     rcx, r14; P
0x140036627  call    cs:__imp_ExFreePoolWithTag
0x14003662e  nop     dword ptr [rax+rax+00h]
0x140036633  jmp     short loc_14003669F
0x140036635  mov     rdx, rbx
0x140036638  and     rbx, 0FFFFFFFFFFFFFFF8h
0x14003663c  shr     rdx, 1
0x14003663f  and     edx, 1
0x140036642  add     rdx, 3
0x140036646  shl     rdx, 4
0x14003664a  add     rdx, rbx
0x14003664d  test    r13b, r13b
0x140036650  jz      loc_1400367E8
0x140036656  mov     eax, gs:1A4h
0x14003665e  shl     eax, 0Ch
0x140036661  mov     ecx, eax
0x140036663  mov     rax, [rdx]
0x140036666  add     [rcx+rax], r15
0x14003666a  mov     r15, r12
0x14003666d  test    rsi, rsi
0x140036670  jnz     loc_140036746
0x140036676  mov     r14, [rsp+88h+P]
0x14003667b  test    byte ptr [r14+0Ah], 20h
0x140036680  jnz     loc_140036BA4
0x140036686  xor     edx, edx; Tag
0x140036688  mov     rcx, r14; P
0x14003668b  call    cs:__imp_ExFreePoolWithTag
0x140036692  nop     dword ptr [rax+rax+00h]
0x140036697  mov     rcx, rdi; NetBufferList
0x14003669a  call    NdisFreeNetBufferList
0x14003669f  mov     rdi, [rsp+88h+var_20]
0x1400366a4  mov     r12, [rsp+88h+var_28]
0x1400366a9  mov     r15, [rsp+88h+var_38]
0x1400366ae  mov     r14, [rsp+88h+var_30]
0x1400366b3  add     rsp, 70h
0x1400366b7  pop     r13
0x1400366b9  pop     rsi
0x1400366ba  pop     rbx
0x1400366bb  retn
0x1400366bd  mov     r14, [rsp+88h+P]
0x1400366c2  mov     rcx, [rsp+88h+arg_0]
0x1400366ca  mov     r9d, 2; unsigned int
0x1400366d0  mov     edx, [rsp+88h+arg_18]; unsigned int
0x1400366d7  mov     r8d, 1; unsigned int
0x1400366dd  mov     rax, [rcx+0A40h]
0x1400366e4  mov     [rsp+88h+var_58], rax; void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)
0x1400366e9  mov     rax, [rcx+9C0h]
0x1400366f0  mov     qword ptr [rsp+88h+Priority], rax; void *
0x1400366f5  mov     rax, [rcx+9D0h]
0x1400366fc  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x1400366ff  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax; struct _NDIS_OBJECT_HEADER *
0x140036704  call    ?ndisInvokeNextReceiveHandler@@YAXPEAU_NET_BUFFER_LIST@@KKKPEAU_NDIS_OBJECT_HEADER@@PEAXP6AX20KKK@Z@Z; ndisInvokeNextReceiveHandler(_NET_BUFFER_LIST *,ulong,ulong,ulong,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong))
0x140036709  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14003670f  test    eax, eax
0x140036711  jz      loc_14003667B
0x140036717  xor     r12d, r12d
0x14003671a  xor     r15d, r15d
0x14003671d  xor     r13b, r13b
0x140036720  cmp     eax, 3
0x140036723  jl      short loc_140036740
0x140036725  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140036727  mov     [rsp+88h+BugCheckOnFailure], r12d; unsigned int
0x14003672c  mov     r9d, 0A8h; void *
0x140036732  mov     r8d, 9Ch; unsigned int
0x140036738  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x14003673b  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140036740  mov     rsi, rdi
0x140036743  xor     r14b, r14b
0x140036746  mov     rbx, [rsi+168h]
0x14003674d  cmp     [rsi+168h], rbx
0x140036754  jnz     short loc_140036799
0x140036756  test    rbx, rbx
0x140036759  jz      loc_140036816
0x14003675f  test    bl, 4
0x140036762  jnz     loc_140036831
0x140036768  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14003676b  call    ?ndisNblTrackerCanNblBeTracked@@YA_NPEAU_NET_BUFFER_LIST@@@Z; ndisNblTrackerCanNblBeTracked(_NET_BUFFER_LIST *)
0x140036770  test    al, al
0x140036772  jz      loc_140036831
0x140036778  cmp     qword ptr [rsi+78h], 0A8h
0x140036780  jz      short loc_1400367FE
0x140036782  inc     r12
0x140036785  mov     eax, 0A8h
0x14003678a  mov     [rsi+168h], rax
0x140036791  mov     rsi, [rsi]
0x140036794  test    rsi, rsi
0x140036797  jnz     short loc_14003674D
0x140036799  test    bl, 1
0x14003679c  jz      loc_14003666A
0x1400367a2  sub     r15, r12
0x1400367a5  jz      loc_14003666A
0x1400367ab  test    r13b, r13b
0x1400367ae  jnz     loc_140036635
0x1400367b4  test    r14b, r14b
0x1400367b7  jnz     loc_140036635
0x1400367bd  mov     r14b, 1
0x1400367c0  call    cs:__imp_KeGetCurrentIrql
0x1400367c7  nop     dword ptr [rax+rax+00h]
0x1400367cc  mov     rdx, rbx
0x1400367cf  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1400367d3  shr     rdx, 1
0x1400367d6  and     edx, 1
0x1400367d9  add     rdx, 3
0x1400367dd  shl     rdx, 4
0x1400367e1  cmp     al, 2
0x1400367e3  jz      short loc_1400367F2
0x1400367e5  add     rdx, rbx
0x1400367e8  lock add [rdx+8], r15
0x1400367ed  jmp     loc_14003666A
0x1400367f2  movzx   r13d, r14b
0x1400367f6  add     rdx, rbx
0x1400367f9  jmp     loc_140036656
0x1400367fe  cmp     qword ptr [rsi+18h], 0
0x140036803  jnz     loc_140036782
0x140036809  inc     r12
0x14003680c  mov     eax, 18h
0x140036811  jmp     loc_14003678A
0x140036816  cmp     qword ptr [rsi+78h], 0
0x14003681b  jnz     loc_140036768
0x140036821  xor     ecx, ecx
0x140036823  call    ?ndisSourceHandleFromOwner@@YAPEAXT_NDIS_NBL_TRACKER_OWNER@@@Z; ndisSourceHandleFromOwner(_NDIS_NBL_TRACKER_OWNER)
0x140036828  mov     [rsi+78h], rax
0x14003682c  jmp     loc_140036768
0x140036831  mov     eax, 0ACh
0x140036836  jmp     loc_14003678A
0x14003683b  xor     r9d, r9d; void *
0x14003683e  mov     [rsp+88h+BugCheckOnFailure], r12d; unsigned int
0x140036843  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140036845  mov     r8d, 3; unsigned int
0x14003684b  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x14003684e  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140036853  jmp     loc_14003660E
0x140036858  mov     rdx, r15
0x14003685b  lea     rcx, aNdisallocatene_0; "NdisAllocateNetBufferAndNetBufferList: "...
0x140036862  call    cs:__imp_DbgPrint
0x140036869  nop     dword ptr [rax+rax+00h]
0x14003686e  jmp     loc_140036617
0x140036873  mov     rax, [rax]
0x140036876  sub     ecx, edx
0x140036878  test    rax, rax
0x14003687b  jnz     loc_1400365EB
0x140036881  jmp     loc_1400365F6
0x140036886  mov     rax, [rdi+8]
0x14003688a  mov     rcx, [rax+20h]; MemoryDescriptorList
0x14003688e  test    byte ptr [rcx+0Ah], 5
0x140036892  jz      loc_140036AE9
0x140036898  mov     r12, [rcx+18h]
0x14003689c  test    r12, r12
0x14003689f  jz      loc_140036BBC
0x1400368a5  mov     r15, [r13+8]
0x1400368a9  test    byte ptr [r15+0Ah], 5
0x1400368ae  jz      loc_140036B15
0x1400368b4  mov     r8, [r15+18h]
0x1400368b8  test    r8, r8
0x1400368bb  jz      loc_140036BBC
0x1400368c1  mov     edx, [r13+10h]
0x1400368c5  mov     eax, esi
0x1400368c7  mov     ecx, [r15+28h]
0x1400368cb  sub     ecx, edx
0x1400368cd  cmp     ecx, esi
0x1400368cf  cmovbe  eax, ecx
0x1400368d2  add     rdx, r8; Src
0x1400368d5  mov     r8d, eax; Size
0x1400368d8  mov     rcx, r12; void *
0x1400368db  mov     ebx, eax
0x1400368dd  sub     esi, eax
0x1400368df  call    memmove
0x1400368e4  mov     r15, [r15]
0x1400368e7  add     r12, rbx
0x1400368ea  test    r15, r15
0x1400368ed  jnz     loc_140036A50
0x1400368f3  or      dword ptr [rdi+88h], 80h
0x1400368fd  or      dword ptr [rdi+80h], 8000h
0x140036907  test    byte ptr [rsp+88h+arg_20], 2
0x14003690f  mov     rdx, [rsp+88h+arg_10]
0x140036917  mov     rax, [rdx+78h]
0x14003691b  mov     [rdi+78h], rax
0x14003691f  mov     rax, [rdx+78h]
0x140036923  mov     [rdi+0B8h], rax
0x14003692a  jz      short loc_140036936
0x14003692c  or      dword ptr [rdi+88h], 200h
0x140036936  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14003693c  test    eax, eax
0x14003693e  jz      loc_1400366C2
0x140036944  xor     r12d, r12d
0x140036947  xor     r15d, r15d
0x14003694a  xor     r13b, r13b
0x14003694d  cmp     eax, 3
0x140036950  jl      short loc_14003696D
0x140036952  xor     r9d, r9d; void *
0x140036955  mov     [rsp+88h+BugCheckOnFailure], r12d; unsigned int
0x14003695a  mov     edx, 0A8h; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14003695f  mov     r8d, 9Bh; unsigned int
0x140036965  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x140036968  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x14003696d  mov     rsi, rdi
0x140036970  xor     r14b, r14b
0x140036973  mov     rbx, [rsi+168h]
0x14003697a  cmp     [rsi+168h], rbx
0x140036981  jnz     short loc_1400369C4
0x140036983  test    rbx, rbx
0x140036986  jz      loc_140036AC1
0x14003698c  test    bl, 4
0x14003698f  jnz     loc_140036ADF
  ... truncated ...
```
