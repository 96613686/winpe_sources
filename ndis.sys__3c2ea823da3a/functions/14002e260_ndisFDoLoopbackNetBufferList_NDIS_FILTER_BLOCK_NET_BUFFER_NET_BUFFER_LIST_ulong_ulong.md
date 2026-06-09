# ndisFDoLoopbackNetBufferList(_NDIS_FILTER_BLOCK *,_NET_BUFFER *,_NET_BUFFER_LIST *,ulong,ulong)

- ea: `0x14002e260`
- end: `0x14002e6f7`
- name: `?ndisFDoLoopbackNetBufferList@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER@@PEAU_NET_BUFFER_LIST@@KK@Z`
- size: `1175`
- prototype: `void __fastcall(struct _NDIS_FILTER_BLOCK *, struct _NET_BUFFER *, struct _NET_BUFFER_LIST *, unsigned int, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x14002df40`

## callees

- `0x140009e70`
- `0x14000de20`
- `0x14002e260`
- `0x14002eed0`
- `0x140032aa0`
- `0x1400e6240`
- `0x1400e62c0`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14002e51a`
- `ntoskrnl!DbgPrint` at `0x14002e6a9`
- `ntoskrnl!DbgPrint` at `0x14002e51a`
- `ntoskrnl!DbgPrint` at `0x14002e6a9`
- `ntoskrnl!MmSizeOfMdl` at `0x14002e287`
- `ntoskrnl!MmSizeOfMdl` at `0x14002e287`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e617`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e649`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e67b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e617`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e649`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e67b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002e343`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002e343`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002e6c1`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002e6e6`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002e6c1`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002e6e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e3f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e4c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e691`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e3f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e4c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e691`
- `ntoskrnl!ExAllocatePool2` at `0x14002e2c4`
- `ntoskrnl!ExAllocatePool2` at `0x14002e2c4`

## pseudocode

```c
void __fastcall ndisFDoLoopbackNetBufferList(
        struct _NDIS_FILTER_BLOCK *a1,
        struct _NET_BUFFER *a2,
        struct _NET_BUFFER_LIST *a3,
        unsigned int a4,
        char a5)
{
  SIZE_T DataLength; // r14
  SIZE_T v7; // rbx
  struct _MDL *Pool2; // rax
  struct _MDL *v9; // rsi
  unsigned __int64 v10; // r8
  NDIS_HANDLE v11; // r15
  PSLIST_ENTRY v12; // rax
  struct _NET_BUFFER_LIST *v13; // rbx
  PSLIST_ENTRY v14; // rdi
  unsigned int v15; // ecx
  struct _MDL *v16; // rax
  ULONG ByteCount; // edx
  bool v18; // zf
  __int64 v19; // rcx
  char *v20; // r12
  _MDL *CurrentMdl; // r15
  char *MappedSystemVa; // r8
  __int64 CurrentMdlOffset; // rdx
  unsigned int v24; // eax
  __int64 v25; // rdi
  ULONG v26; // r14d
  struct _MDL *Next; // r15
  char *i; // r12
  PVOID v29; // rax
  ULONG v30; // ecx
  __int64 v31; // rdi
  int v33; // [rsp+78h] [rbp+10h] BYREF
  struct _NET_BUFFER_LIST *v34; // [rsp+80h] [rbp+18h]
  unsigned int v35; // [rsp+88h] [rbp+20h]

  v35 = a4;
  v34 = a3;
  DataLength = a2->DataLength;
  v7 = (MmSizeOfMdl((PVOID)0xFFF, DataLength) + 7) & 0xFFFFFFF8;
  if ( (DataLength + v7) >> 32 )
    return;
  Pool2 = (struct _MDL *)ExAllocatePool2(64, (unsigned int)(DataLength + v7), 1886143566);
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
  v33 = 0;
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
  v12 = ndisAllocateNetBufferListInternal((__int64)ndisNetBufferListPool, 0, 0, &v33);
  v13 = (struct _NET_BUFFER_LIST *)v12;
  if ( v12 )
  {
    v14 = v12 + 24;
    memset(&v12[24], 0, 0xB0u);
    v15 = 0;
    v14[2].Next = (_SLIST_ENTRY *)v9;
    v16 = v9;
    *((_DWORD *)&v14[1].Next + 2) = DataLength;
    *((_QWORD *)&v14[3].Next + 1) = v11;
    do
    {
      ByteCount = v16->ByteCount;
      if ( v15 < ByteCount )
        break;
      v16 = v16->Next;
      v15 -= ByteCount;
    }
    while ( v16 );
    *((_QWORD *)&v14->Next + 1) = v16;
    LODWORD(v14[1].Next) = v15;
    v13->Link.Region = (unsigned __int64)v14;
    if ( *(int *)ndisNblTrackerMode >= 3 )
      ndisNblTrackerRecordEventInternal(v13, 0, 3u, 0, 0);
  }
  if ( !v13 )
    goto LABEL_12;
  v19 = *(_QWORD *)(v13->Link.Region + 32);
  if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
    v20 = *(char **)(v19 + 24);
  else
    v20 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000000u);
  if ( !v20
    || ((CurrentMdl = a2->CurrentMdl, (CurrentMdl->MdlFlags & 5) == 0)
      ? (MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u))
      : (MappedSystemVa = (char *)CurrentMdl->MappedSystemVa),
        !MappedSystemVa) )
  {
    NdisFreeNetBufferList(v13);
    goto LABEL_12;
  }
  CurrentMdlOffset = a2->CurrentMdlOffset;
  v24 = DataLength;
  if ( CurrentMdl->ByteCount - (int)CurrentMdlOffset <= (unsigned int)DataLength )
    v24 = CurrentMdl->ByteCount - CurrentMdlOffset;
  v25 = v24;
  v26 = DataLength - v24;
  memmove(v20, &MappedSystemVa[CurrentMdlOffset], v24);
  Next = CurrentMdl->Next;
  for ( i = &v20[v25]; Next; i += v31 )
  {
    if ( !v26 )
      break;
    v29 = (Next->MdlFlags & 5) != 0
        ? Next->MappedSystemVa
        : MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000000u);
    if ( !v29 )
      break;
    v30 = v26;
    if ( v26 >= Next->ByteCount )
      v30 = Next->ByteCount;
    v31 = v30;
    v26 -= v30;
    memmove(i, v29, v30);
    Next = Next->Next;
  }
  v13->Flags |= 0x80u;
  v13->NblFlags |= 0x8000u;
  v18 = (a5 & 2) == 0;
  v13->SourceHandle = v34->SourceHandle;
  if ( !v18 )
    v13->Flags |= 0x200u;
  if ( *(_DWORD *)ndisNblTrackerMode )
    ndisNblTrackerTransferOwnershipInternal(
      v13,
      (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA8,
      0,
      NdisNblTrackerEvent_LoopbackIndicated,
      0);
  a1->FilterIndicateReceiveNetBufferListsHandler(a1, v13, v35, 1u, 2u);
  if ( *(_DWORD *)ndisNblTrackerMode )
    ndisNblTrackerTransferOwnershipInternal(
      v13,
      0,
      (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA8,
      NdisNblTrackerEvent_LoopbackReturned,
      0);
  if ( (v9->MdlFlags & 0x20) != 0 )
    MmUnmapLockedPages(v9->MappedSystemVa, v9);
  ExFreePoolWithTag(v9, 0);
  NdisFreeNetBufferList(v13);
}

```

## disassembly

```asm
0x14002e260  mov     [rsp+arg_18], r9d
0x14002e265  mov     [rsp+arg_10], r8
0x14002e26a  mov     [rsp+arg_0], rcx
0x14002e26f  push    rbx
0x14002e270  push    r13
0x14002e272  push    r14
0x14002e274  sub     rsp, 50h
0x14002e278  mov     r14d, [rdx+18h]
0x14002e27c  mov     r13, rdx
0x14002e27f  mov     edx, r14d; Length
0x14002e282  mov     ecx, 0FFFh; Base
0x14002e287  call    cs:__imp_MmSizeOfMdl
0x14002e28e  nop     dword ptr [rax+rax+00h]
0x14002e293  lea     rbx, [rax+7]
0x14002e297  mov     eax, 0FFFFFFF8h
0x14002e29c  and     rbx, rax
0x14002e29f  lea     rax, [r14+rbx]
0x14002e2a3  mov     rcx, rax
0x14002e2a6  shr     rcx, 20h
0x14002e2aa  test    ecx, ecx
0x14002e2ac  jnz     loc_14002E4E8
0x14002e2b2  mov     edx, eax
0x14002e2b4  mov     ecx, 40h ; '@'
0x14002e2b9  mov     r8d, 706C444Eh
0x14002e2bf  mov     [rsp+68h+var_20], rsi
0x14002e2c4  call    cs:__imp_ExAllocatePool2
0x14002e2cb  nop     dword ptr [rax+rax+00h]
0x14002e2d0  mov     rsi, rax
0x14002e2d3  test    rax, rax
0x14002e2d6  jz      loc_14002E4E3
0x14002e2dc  lea     r8, [rbx+rax]
0x14002e2e0  cmp     r8, rax
0x14002e2e3  jb      loc_14002E68C
0x14002e2e9  mov     edx, r8d
0x14002e2ec  mov     [rsp+68h+var_28], rdi
0x14002e2f1  mov     ecx, edx
0x14002e2f3  mov     [rsp+68h+var_30], r12
0x14002e2f8  and     ecx, 0FFFh
0x14002e2fe  mov     [rsp+68h+var_38], r15
0x14002e303  add     rcx, 0FFFh
0x14002e30a  mov     [rax+28h], r14d
0x14002e30e  add     rcx, r14
0x14002e311  xor     r12d, r12d
0x14002e314  shr     rcx, 0Ch
0x14002e318  and     r8, 0FFFFFFFFFFFFF000h
0x14002e31f  add     cx, 6
0x14002e323  mov     [rax], r12
0x14002e326  shl     cx, 3
0x14002e32a  and     edx, 0FFFh
0x14002e330  mov     [rax+8], cx
0x14002e334  mov     rcx, rax; MemoryDescriptorList
0x14002e337  mov     [rax+0Ah], r12w
0x14002e33c  mov     [rax+20h], r8
0x14002e340  mov     [rax+2Ch], edx
0x14002e343  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14002e34a  nop     dword ptr [rax+rax+00h]
0x14002e34f  mov     r15, cs:?ndisNetBufferListPool@@3PEAXEA; void * ndisNetBufferListPool
0x14002e356  mov     [rsp+68h+arg_8], r12d
0x14002e35b  test    r15, r15
0x14002e35e  jz      loc_14002E6A2
0x14002e364  mov     eax, [r15+2Ch]
0x14002e368  and     al, 5
0x14002e36a  cmp     al, 1
0x14002e36c  jnz     loc_14002E510
0x14002e372  xor     r8d, r8d
0x14002e375  lea     r9, [rsp+68h+arg_8]
0x14002e37a  xor     edx, edx
0x14002e37c  mov     rcx, r15
0x14002e37f  call    ndisAllocateNetBufferListInternal
0x14002e384  mov     rbx, rax
0x14002e387  test    rax, rax
0x14002e38a  jz      short loc_14002E3D8
0x14002e38c  lea     rdi, [rax+180h]
0x14002e393  xor     edx, edx; Val
0x14002e395  mov     rcx, rdi; void *
0x14002e398  mov     r8d, 0B0h; Size
0x14002e39e  call    memset
0x14002e3a3  mov     ecx, r12d
0x14002e3a6  mov     [rdi+20h], rsi
0x14002e3aa  mov     rax, rsi
0x14002e3ad  mov     [rdi+18h], r14d
0x14002e3b1  mov     [rdi+38h], r15
0x14002e3b5  mov     edx, [rax+28h]
0x14002e3b8  cmp     ecx, edx
0x14002e3ba  jnb     loc_14002E52B
0x14002e3c0  mov     [rdi+8], rax
0x14002e3c4  mov     [rdi+10h], ecx
0x14002e3c7  mov     [rbx+8], rdi
0x14002e3cb  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002e3d2  jge     loc_14002E4F3
0x14002e3d8  test    rbx, rbx
0x14002e3db  jnz     loc_14002E53E
0x14002e3e1  test    byte ptr [rsi+0Ah], 20h
0x14002e3e5  jnz     loc_14002E6DF
0x14002e3eb  xor     edx, edx; Tag
0x14002e3ed  mov     rcx, rsi; P
0x14002e3f0  call    cs:__imp_ExFreePoolWithTag
0x14002e3f7  nop     dword ptr [rax+rax+00h]
0x14002e3fc  jmp     loc_14002E4D4
0x14002e401  or      dword ptr [rbx+88h], 80h
0x14002e40b  or      dword ptr [rbx+80h], 8000h
0x14002e415  test    [rsp+68h+arg_20], 2
0x14002e41d  mov     rax, [rsp+68h+arg_10]
0x14002e425  mov     rax, [rax+78h]
0x14002e429  mov     [rbx+78h], rax
0x14002e42d  jz      short loc_14002E439
0x14002e42f  or      dword ptr [rbx+88h], 200h
0x14002e439  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002e440  jz      short loc_14002E460
0x14002e442  mov     r9d, 9Bh; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14002e448  mov     [rsp+68h+BugCheckOnFailure], 0; unsigned int
0x14002e450  xor     r8d, r8d; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002e453  mov     edx, 0A8h; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002e458  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x14002e45b  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14002e460  mov     rcx, [rsp+68h+arg_0]
0x14002e465  mov     r9d, 1
0x14002e46b  mov     r8d, [rsp+68h+arg_18]
0x14002e473  mov     rdx, rbx
0x14002e476  mov     [rsp+68h+BugCheckOnFailure], 2
0x14002e47e  mov     rax, [rcx+278h]
0x14002e485  call    _guard_dispatch_icall
0x14002e48a  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002e491  jz      short loc_14002E4B1
0x14002e493  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002e495  mov     [rsp+68h+BugCheckOnFailure], 0; unsigned int
0x14002e49d  mov     r9d, 9Ch; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14002e4a3  mov     r8d, 0A8h; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002e4a9  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x14002e4ac  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14002e4b1  test    byte ptr [rsi+0Ah], 20h
0x14002e4b5  jnz     loc_14002E6BA
0x14002e4bb  xor     edx, edx; Tag
0x14002e4bd  mov     rcx, rsi; P
0x14002e4c0  call    cs:__imp_ExFreePoolWithTag
0x14002e4c7  nop     dword ptr [rax+rax+00h]
0x14002e4cc  mov     rcx, rbx; NetBufferList
0x14002e4cf  call    NdisFreeNetBufferList
0x14002e4d4  mov     r12, [rsp+68h+var_30]
0x14002e4d9  mov     rdi, [rsp+68h+var_28]
0x14002e4de  mov     r15, [rsp+68h+var_38]
0x14002e4e3  mov     rsi, [rsp+68h+var_20]
0x14002e4e8  add     rsp, 50h
0x14002e4ec  pop     r14
0x14002e4ee  pop     r13
0x14002e4f0  pop     rbx
0x14002e4f1  retn
0x14002e4f3  xor     r9d, r9d; void *
0x14002e4f6  mov     [rsp+68h+BugCheckOnFailure], r12d; unsigned int
0x14002e4fb  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002e4fd  mov     r8d, 3; unsigned int
0x14002e503  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x14002e506  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x14002e50b  jmp     loc_14002E3D8
0x14002e510  mov     rdx, r15
0x14002e513  lea     rcx, Format; "NdisAllocateNetBufferAndNetBufferList: "...
0x14002e51a  call    cs:__imp_DbgPrint
0x14002e521  nop     dword ptr [rax+rax+00h]
0x14002e526  jmp     loc_14002E3E1
0x14002e52b  mov     rax, [rax]
0x14002e52e  sub     ecx, edx
0x14002e530  test    rax, rax
0x14002e533  jnz     loc_14002E3B5
0x14002e539  jmp     loc_14002E3C0
0x14002e53e  mov     rax, [rbx+8]
0x14002e542  mov     rcx, [rax+20h]; MemoryDescriptorList
0x14002e546  test    byte ptr [rcx+0Ah], 5
0x14002e54a  jz      loc_14002E5FF
0x14002e550  mov     r12, [rcx+18h]
0x14002e554  test    r12, r12
0x14002e557  jz      loc_14002E6D2
0x14002e55d  mov     r15, [r13+8]
0x14002e561  test    byte ptr [r15+0Ah], 5
0x14002e566  jz      loc_14002E62B
0x14002e56c  mov     r8, [r15+18h]
0x14002e570  test    r8, r8
0x14002e573  jz      loc_14002E6D2
0x14002e579  mov     edx, [r13+10h]
0x14002e57d  mov     eax, r14d
0x14002e580  mov     ecx, [r15+28h]
0x14002e584  sub     ecx, edx
0x14002e586  cmp     ecx, r14d
0x14002e589  cmovbe  eax, ecx
0x14002e58c  add     rdx, r8; Src
0x14002e58f  mov     r8d, eax; Size
0x14002e592  mov     rcx, r12; void *
0x14002e595  mov     edi, eax
0x14002e597  sub     r14d, eax
0x14002e59a  call    memmove
0x14002e59f  mov     r15, [r15]
0x14002e5a2  add     r12, rdi
0x14002e5a5  test    r15, r15
0x14002e5a8  jz      loc_14002E401
0x14002e5ae  test    r14d, r14d
0x14002e5b1  jz      loc_14002E401
0x14002e5b7  test    byte ptr [r15+0Ah], 5
0x14002e5bc  jz      loc_14002E65D
0x14002e5c2  mov     rax, [r15+18h]
0x14002e5c6  test    rax, rax
0x14002e5c9  jz      loc_14002E401
0x14002e5cf  mov     edx, [r15+28h]
0x14002e5d3  mov     ecx, r14d
0x14002e5d6  cmp     r14d, edx
0x14002e5d9  cmovnb  ecx, edx
0x14002e5dc  mov     rdx, rax; Src
0x14002e5df  mov     edi, ecx
0x14002e5e1  sub     r14d, ecx
0x14002e5e4  mov     r8d, ecx; Size
0x14002e5e7  mov     rcx, r12; void *
0x14002e5ea  call    memmove
0x14002e5ef  mov     r15, [r15]
0x14002e5f2  add     r12, rdi
0x14002e5f5  test    r15, r15
0x14002e5f8  jnz     short loc_14002E5AE
0x14002e5fa  jmp     loc_14002E401
0x14002e5ff  mov     [rsp+68h+Priority], 40000000h; Priority
0x14002e607  xor     r9d, r9d; RequestedAddress
0x14002e60a  xor     edx, edx; AccessMode
0x14002e60c  mov     [rsp+68h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14002e611  mov     r8d, 1; CacheType
0x14002e617  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002e61e  nop     dword ptr [rax+rax+00h]
0x14002e623  mov     r12, rax
0x14002e626  jmp     loc_14002E554
0x14002e62b  mov     [rsp+68h+Priority], 40000000h; Priority
0x14002e633  xor     r9d, r9d; RequestedAddress
0x14002e636  xor     edx, edx; AccessMode
0x14002e638  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002e640  mov     r8d, 1; CacheType
0x14002e646  mov     rcx, r15; MemoryDescriptorList
0x14002e649  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002e650  nop     dword ptr [rax+rax+00h]
0x14002e655  mov     r8, rax
0x14002e658  jmp     loc_14002E570
0x14002e65d  mov     [rsp+68h+Priority], 40000000h; Priority
0x14002e665  xor     r9d, r9d; RequestedAddress
0x14002e668  xor     edx, edx; AccessMode
0x14002e66a  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002e672  mov     r8d, 1; CacheType
0x14002e678  mov     rcx, r15; MemoryDescriptorList
0x14002e67b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002e682  nop     dword ptr [rax+rax+00h]
0x14002e687  jmp     loc_14002E5C6
0x14002e68c  xor     edx, edx; Tag
0x14002e68e  mov     rcx, rsi; P
0x14002e691  call    cs:__imp_ExFreePoolWithTag
0x14002e698  nop     dword ptr [rax+rax+00h]
0x14002e69d  jmp     loc_14002E4E3
0x14002e6a2  lea     rcx, aNdisallocatene_2; "NdisAllocateNetBufferAndNetBufferList: "...
0x14002e6a9  call    cs:__imp_DbgPrint
0x14002e6b0  nop     dword ptr [rax+rax+00h]
0x14002e6b5  jmp     loc_14002E3E1
0x14002e6ba  mov     rcx, [rsi+18h]; BaseAddress
0x14002e6be  mov     rdx, rsi; MemoryDescriptorList
0x14002e6c1  call    cs:__imp_MmUnmapLockedPages
0x14002e6c8  nop     dword ptr [rax+rax+00h]
0x14002e6cd  jmp     loc_14002E4BB
0x14002e6d2  mov     rcx, rbx; NetBufferList
0x14002e6d5  call    NdisFreeNetBufferList
0x14002e6da  jmp     loc_14002E3E1
0x14002e6df  mov     rcx, [rsi+18h]; BaseAddress
0x14002e6e3  mov     rdx, rsi; MemoryDescriptorList
0x14002e6e6  call    cs:__imp_MmUnmapLockedPages
0x14002e6ed  nop     dword ptr [rax+rax+00h]
0x14002e6f2  jmp     loc_14002E3EB
```
