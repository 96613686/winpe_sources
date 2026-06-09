# ndisDoLoopbackNetBufferList(_NDIS_MINIPORT_BLOCK *,_NET_BUFFER *,_NET_BUFFER_LIST *,ulong,ulong)

- ea: `0x14002ea00`
- end: `0x14002eec4`
- name: `?ndisDoLoopbackNetBufferList@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NET_BUFFER@@PEAU_NET_BUFFER_LIST@@KK@Z`
- size: `1220`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NET_BUFFER *, struct _NET_BUFFER_LIST *, unsigned int, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x14002e700`

## callees

- `0x140009e70`
- `0x14000de20`
- `0x14002ea00`
- `0x14002eed0`
- `0x14002f660`
- `0x140032aa0`
- `0x1400e62c0`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14002eda8`
- `ntoskrnl!DbgPrint` at `0x14002ee76`
- `ntoskrnl!DbgPrint` at `0x14002eda8`
- `ntoskrnl!DbgPrint` at `0x14002ee76`
- `ntoskrnl!MmSizeOfMdl` at `0x14002ea27`
- `ntoskrnl!MmSizeOfMdl` at `0x14002ea27`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002ede4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002ee16`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002ee48`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002ede4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002ee16`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002ee48`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002eae3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002eae3`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002ee8e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002eeb3`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002ee8e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002eeb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002eb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ecfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002eb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ecfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee5e`
- `ntoskrnl!ExAllocatePool2` at `0x14002ea64`
- `ntoskrnl!ExAllocatePool2` at `0x14002ea64`

## pseudocode

```c
void __fastcall ndisDoLoopbackNetBufferList(
        struct _NDIS_MINIPORT_BLOCK *a1,
        struct _NET_BUFFER *a2,
        struct _NET_BUFFER_LIST *a3,
        unsigned int a4,
        char a5)
{
  SIZE_T DataLength; // r14
  SIZE_T v7; // rdi
  struct _MDL *Pool2; // rax
  struct _MDL *v9; // rbx
  unsigned __int64 v10; // r8
  NDIS_HANDLE v11; // r15
  PSLIST_ENTRY v12; // rax
  struct _NET_BUFFER_LIST *v13; // rsi
  PSLIST_ENTRY v14; // rdi
  unsigned int v15; // ecx
  struct _MDL *v16; // rax
  ULONG ByteCount; // edx
  __int64 v18; // rcx
  char *v19; // r12
  _MDL *CurrentMdl; // r15
  char *MappedSystemVa; // r8
  __int64 CurrentMdlOffset; // rdx
  unsigned int v23; // eax
  __int64 v24; // rdi
  ULONG v25; // r14d
  struct _MDL *Next; // r15
  char *i; // r12
  bool v28; // zf
  struct _NET_BUFFER_LIST *v29; // rdx
  PVOID v30; // rax
  ULONG v31; // ecx
  __int64 v32; // rdi
  int v34; // [rsp+88h] [rbp+10h] BYREF
  struct _NET_BUFFER_LIST *v35; // [rsp+90h] [rbp+18h]
  unsigned int v36; // [rsp+98h] [rbp+20h]

  v36 = a4;
  v35 = a3;
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
  v34 = 0;
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
  v12 = ndisAllocateNetBufferListInternal((__int64)ndisNetBufferListPool, 0, 0, &v34);
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
  v18 = *(_QWORD *)(v13->Link.Region + 32);
  if ( (*(_BYTE *)(v18 + 10) & 5) != 0 )
    v19 = *(char **)(v18 + 24);
  else
    v19 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v18, 0, MmCached, 0, 0, 0x40000000u);
  if ( !v19
    || ((CurrentMdl = a2->CurrentMdl, (CurrentMdl->MdlFlags & 5) == 0)
      ? (MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u))
      : (MappedSystemVa = (char *)CurrentMdl->MappedSystemVa),
        !MappedSystemVa) )
  {
    NdisFreeNetBufferList(v13);
    goto LABEL_12;
  }
  CurrentMdlOffset = a2->CurrentMdlOffset;
  v23 = DataLength;
  if ( CurrentMdl->ByteCount - (int)CurrentMdlOffset <= (unsigned int)DataLength )
    v23 = CurrentMdl->ByteCount - CurrentMdlOffset;
  v24 = v23;
  v25 = DataLength - v23;
  memmove(v19, &MappedSystemVa[CurrentMdlOffset], v23);
  Next = CurrentMdl->Next;
  for ( i = &v19[v24]; Next; i += v32 )
  {
    if ( !v25 )
      break;
    v30 = (Next->MdlFlags & 5) != 0
        ? Next->MappedSystemVa
        : MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000000u);
    if ( !v30 )
      break;
    v31 = v25;
    if ( v25 >= Next->ByteCount )
      v31 = Next->ByteCount;
    v32 = v31;
    v25 -= v31;
    memmove(i, v30, v31);
    Next = Next->Next;
  }
  v13->Flags |= 0x80u;
  v13->NblFlags |= 0x8000u;
  v28 = (a5 & 2) == 0;
  v29 = v35;
  v13->SourceHandle = v35->SourceHandle;
  v13->NetBufferListInfo[5] = v29->SourceHandle;
  if ( !v28 )
    v13->Flags |= 0x200u;
  if ( *(_DWORD *)ndisNblTrackerMode )
    ndisNblTrackerTransferOwnershipInternal(
      v13,
      (struct NDIS_NBL_TRACKER_HANDLE__ *)0xA8,
      0,
      NdisNblTrackerEvent_LoopbackIndicated,
      0);
  ndisInvokeNextReceiveHandler(
    v13,
    v36,
    1,
    2,
    (struct _NDIS_FILTER_BLOCK *)a1->Next.IndicateNetBufferListsObject,
    a1->Next.IndicateNetBufferListsContext,
    (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))a1->Next.IndicateNetBufferListsHandler);
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
0x14002ea00  mov     [rsp+arg_18], r9d
0x14002ea05  mov     [rsp+arg_10], r8
0x14002ea0a  mov     [rsp+arg_0], rcx
0x14002ea0f  push    rdi
0x14002ea10  push    r13
0x14002ea12  push    r14
0x14002ea14  sub     rsp, 60h
0x14002ea18  mov     r14d, [rdx+18h]
0x14002ea1c  mov     r13, rdx
0x14002ea1f  mov     edx, r14d; Length
0x14002ea22  mov     ecx, 0FFFh; Base
0x14002ea27  call    cs:__imp_MmSizeOfMdl
0x14002ea2e  nop     dword ptr [rax+rax+00h]
0x14002ea33  lea     rdi, [rax+7]
0x14002ea37  mov     eax, 0FFFFFFF8h
0x14002ea3c  and     rdi, rax
0x14002ea3f  lea     rax, [r14+rdi]
0x14002ea43  mov     rcx, rax
0x14002ea46  shr     rcx, 20h
0x14002ea4a  test    ecx, ecx
0x14002ea4c  jnz     loc_14002ED22
0x14002ea52  mov     edx, eax
0x14002ea54  mov     ecx, 40h ; '@'
0x14002ea59  mov     r8d, 706C444Eh
0x14002ea5f  mov     [rsp+78h+var_20], rbx
0x14002ea64  call    cs:__imp_ExAllocatePool2
0x14002ea6b  nop     dword ptr [rax+rax+00h]
0x14002ea70  mov     rbx, rax
0x14002ea73  test    rax, rax
0x14002ea76  jz      loc_14002ED1D
0x14002ea7c  lea     r8, [rdi+rax]
0x14002ea80  cmp     r8, rax
0x14002ea83  jb      loc_14002EE59
0x14002ea89  mov     edx, r8d
0x14002ea8c  mov     [rsp+78h+var_28], rsi
0x14002ea91  mov     ecx, edx
0x14002ea93  mov     [rsp+78h+var_30], r12
0x14002ea98  and     ecx, 0FFFh
0x14002ea9e  mov     [rsp+78h+var_38], r15
0x14002eaa3  add     rcx, 0FFFh
0x14002eaaa  mov     [rax+28h], r14d
0x14002eaae  add     rcx, r14
0x14002eab1  xor     r12d, r12d
0x14002eab4  shr     rcx, 0Ch
0x14002eab8  and     r8, 0FFFFFFFFFFFFF000h
0x14002eabf  add     cx, 6
0x14002eac3  mov     [rax], r12
0x14002eac6  shl     cx, 3
0x14002eaca  and     edx, 0FFFh
0x14002ead0  mov     [rax+8], cx
0x14002ead4  mov     rcx, rax; MemoryDescriptorList
0x14002ead7  mov     [rax+0Ah], r12w
0x14002eadc  mov     [rax+20h], r8
0x14002eae0  mov     [rax+2Ch], edx
0x14002eae3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14002eaea  nop     dword ptr [rax+rax+00h]
0x14002eaef  mov     r15, cs:?ndisNetBufferListPool@@3PEAXEA; void * ndisNetBufferListPool
0x14002eaf6  mov     [rsp+78h+arg_8], r12d
0x14002eafe  test    r15, r15
0x14002eb01  jz      loc_14002EE6F
0x14002eb07  mov     eax, [r15+2Ch]
0x14002eb0b  and     al, 5
0x14002eb0d  cmp     al, 1
0x14002eb0f  jnz     loc_14002ED9E
0x14002eb15  xor     r8d, r8d
0x14002eb18  lea     r9, [rsp+78h+arg_8]
0x14002eb20  xor     edx, edx
0x14002eb22  mov     rcx, r15
0x14002eb25  call    ndisAllocateNetBufferListInternal
0x14002eb2a  mov     rsi, rax
0x14002eb2d  test    rax, rax
0x14002eb30  jz      short loc_14002EB7E
0x14002eb32  lea     rdi, [rax+180h]
0x14002eb39  xor     edx, edx; Val
0x14002eb3b  mov     rcx, rdi; void *
0x14002eb3e  mov     r8d, 0B0h; Size
0x14002eb44  call    memset
0x14002eb49  mov     ecx, r12d
0x14002eb4c  mov     [rdi+20h], rbx
0x14002eb50  mov     rax, rbx
0x14002eb53  mov     [rdi+18h], r14d
0x14002eb57  mov     [rdi+38h], r15
0x14002eb5b  mov     edx, [rax+28h]
0x14002eb5e  cmp     ecx, edx
0x14002eb60  jnb     loc_14002EDB9
0x14002eb66  mov     [rdi+8], rax
0x14002eb6a  mov     [rdi+10h], ecx
0x14002eb6d  mov     [rsi+8], rdi
0x14002eb71  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002eb78  jge     loc_14002ED81
0x14002eb7e  test    rsi, rsi
0x14002eb81  jnz     short loc_14002EBA3
0x14002eb83  test    byte ptr [rbx+0Ah], 20h
0x14002eb87  jnz     loc_14002EEAC
0x14002eb8d  xor     edx, edx; Tag
0x14002eb8f  mov     rcx, rbx; P
0x14002eb92  call    cs:__imp_ExFreePoolWithTag
0x14002eb99  nop     dword ptr [rax+rax+00h]
0x14002eb9e  jmp     loc_14002ED0E
0x14002eba3  mov     rax, [rsi+8]
0x14002eba7  mov     rcx, [rax+20h]; MemoryDescriptorList
0x14002ebab  test    byte ptr [rcx+0Ah], 5
0x14002ebaf  jz      loc_14002EDCC
0x14002ebb5  mov     r12, [rcx+18h]
0x14002ebb9  test    r12, r12
0x14002ebbc  jz      loc_14002EE9F
0x14002ebc2  mov     r15, [r13+8]
0x14002ebc6  test    byte ptr [r15+0Ah], 5
0x14002ebcb  jz      loc_14002EDF8
0x14002ebd1  mov     r8, [r15+18h]
0x14002ebd5  test    r8, r8
0x14002ebd8  jz      loc_14002EE9F
0x14002ebde  mov     edx, [r13+10h]
0x14002ebe2  mov     eax, r14d
0x14002ebe5  mov     ecx, [r15+28h]
0x14002ebe9  sub     ecx, edx
0x14002ebeb  cmp     ecx, r14d
0x14002ebee  cmovbe  eax, ecx
0x14002ebf1  add     rdx, r8; Src
0x14002ebf4  mov     r8d, eax; Size
0x14002ebf7  mov     rcx, r12; void *
0x14002ebfa  mov     edi, eax
0x14002ebfc  sub     r14d, eax
0x14002ebff  call    memmove
0x14002ec04  mov     r15, [r15]
0x14002ec07  add     r12, rdi
0x14002ec0a  test    r15, r15
0x14002ec0d  jnz     loc_14002ED30
0x14002ec13  or      dword ptr [rsi+88h], 80h
0x14002ec1d  or      dword ptr [rsi+80h], 8000h
0x14002ec27  test    [rsp+78h+arg_20], 2
0x14002ec2f  mov     rdx, [rsp+78h+arg_10]
0x14002ec37  mov     rax, [rdx+78h]
0x14002ec3b  mov     [rsi+78h], rax
0x14002ec3f  mov     rax, [rdx+78h]
0x14002ec43  mov     [rsi+0B8h], rax
0x14002ec4a  jz      short loc_14002EC56
0x14002ec4c  or      dword ptr [rsi+88h], 200h
0x14002ec56  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002ec5d  jz      short loc_14002EC7D
0x14002ec5f  mov     r9d, 9Bh; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14002ec65  mov     [rsp+78h+BugCheckOnFailure], 0; unsigned int
0x14002ec6d  xor     r8d, r8d; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002ec70  mov     edx, 0A8h; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002ec75  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14002ec78  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14002ec7d  mov     rcx, [rsp+78h+arg_0]
0x14002ec85  mov     r9d, 2; unsigned int
0x14002ec8b  mov     edx, [rsp+78h+arg_18]; unsigned int
0x14002ec92  mov     r8d, 1; unsigned int
0x14002ec98  mov     rax, [rcx+0A40h]
0x14002ec9f  mov     [rsp+78h+var_48], rax; void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)
0x14002eca4  mov     rax, [rcx+9C0h]
0x14002ecab  mov     qword ptr [rsp+78h+Priority], rax; void *
0x14002ecb0  mov     rax, [rcx+9D0h]
0x14002ecb7  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14002ecba  mov     qword ptr [rsp+78h+BugCheckOnFailure], rax; struct _NDIS_OBJECT_HEADER *
0x14002ecbf  call    ?ndisInvokeNextReceiveHandler@@YAXPEAU_NET_BUFFER_LIST@@KKKPEAU_NDIS_OBJECT_HEADER@@PEAXP6AX20KKK@Z@Z; ndisInvokeNextReceiveHandler(_NET_BUFFER_LIST *,ulong,ulong,ulong,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong))
0x14002ecc4  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002eccb  jz      short loc_14002ECEB
0x14002eccd  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002eccf  mov     [rsp+78h+BugCheckOnFailure], 0; unsigned int
0x14002ecd7  mov     r9d, 9Ch; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14002ecdd  mov     r8d, 0A8h; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002ece3  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14002ece6  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14002eceb  test    byte ptr [rbx+0Ah], 20h
0x14002ecef  jnz     loc_14002EE87
0x14002ecf5  xor     edx, edx; Tag
0x14002ecf7  mov     rcx, rbx; P
0x14002ecfa  call    cs:__imp_ExFreePoolWithTag
0x14002ed01  nop     dword ptr [rax+rax+00h]
0x14002ed06  mov     rcx, rsi; NetBufferList
0x14002ed09  call    NdisFreeNetBufferList
0x14002ed0e  mov     r12, [rsp+78h+var_30]
0x14002ed13  mov     rsi, [rsp+78h+var_28]
0x14002ed18  mov     r15, [rsp+78h+var_38]
0x14002ed1d  mov     rbx, [rsp+78h+var_20]
0x14002ed22  add     rsp, 60h
0x14002ed26  pop     r14
0x14002ed28  pop     r13
0x14002ed2a  pop     rdi
0x14002ed2b  retn
0x14002ed30  test    r14d, r14d
0x14002ed33  jz      loc_14002EC13
0x14002ed39  test    byte ptr [r15+0Ah], 5
0x14002ed3e  jz      loc_14002EE2A
0x14002ed44  mov     rax, [r15+18h]
0x14002ed48  test    rax, rax
0x14002ed4b  jz      loc_14002EC13
0x14002ed51  mov     edx, [r15+28h]
0x14002ed55  mov     ecx, r14d
0x14002ed58  cmp     r14d, edx
0x14002ed5b  cmovnb  ecx, edx
0x14002ed5e  mov     rdx, rax; Src
0x14002ed61  mov     edi, ecx
0x14002ed63  sub     r14d, ecx
0x14002ed66  mov     r8d, ecx; Size
0x14002ed69  mov     rcx, r12; void *
0x14002ed6c  call    memmove
0x14002ed71  mov     r15, [r15]
0x14002ed74  add     r12, rdi
0x14002ed77  test    r15, r15
0x14002ed7a  jnz     short loc_14002ED30
0x14002ed7c  jmp     loc_14002EC13
0x14002ed81  xor     r9d, r9d; void *
0x14002ed84  mov     [rsp+78h+BugCheckOnFailure], r12d; unsigned int
0x14002ed89  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002ed8b  mov     r8d, 3; unsigned int
0x14002ed91  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14002ed94  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x14002ed99  jmp     loc_14002EB7E
0x14002ed9e  mov     rdx, r15
0x14002eda1  lea     rcx, Format; "NdisAllocateNetBufferAndNetBufferList: "...
0x14002eda8  call    cs:__imp_DbgPrint
0x14002edaf  nop     dword ptr [rax+rax+00h]
0x14002edb4  jmp     loc_14002EB83
0x14002edb9  mov     rax, [rax]
0x14002edbc  sub     ecx, edx
0x14002edbe  test    rax, rax
0x14002edc1  jnz     loc_14002EB5B
0x14002edc7  jmp     loc_14002EB66
0x14002edcc  mov     [rsp+78h+Priority], 40000000h; Priority
0x14002edd4  xor     r9d, r9d; RequestedAddress
0x14002edd7  xor     edx, edx; AccessMode
0x14002edd9  mov     [rsp+78h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x14002edde  mov     r8d, 1; CacheType
0x14002ede4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002edeb  nop     dword ptr [rax+rax+00h]
0x14002edf0  mov     r12, rax
0x14002edf3  jmp     loc_14002EBB9
0x14002edf8  mov     [rsp+78h+Priority], 40000000h; Priority
0x14002ee00  xor     r9d, r9d; RequestedAddress
0x14002ee03  xor     edx, edx; AccessMode
0x14002ee05  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002ee0d  mov     r8d, 1; CacheType
0x14002ee13  mov     rcx, r15; MemoryDescriptorList
0x14002ee16  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002ee1d  nop     dword ptr [rax+rax+00h]
0x14002ee22  mov     r8, rax
0x14002ee25  jmp     loc_14002EBD5
0x14002ee2a  mov     [rsp+78h+Priority], 40000000h; Priority
0x14002ee32  xor     r9d, r9d; RequestedAddress
0x14002ee35  xor     edx, edx; AccessMode
0x14002ee37  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002ee3f  mov     r8d, 1; CacheType
0x14002ee45  mov     rcx, r15; MemoryDescriptorList
0x14002ee48  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002ee4f  nop     dword ptr [rax+rax+00h]
0x14002ee54  jmp     loc_14002ED48
0x14002ee59  xor     edx, edx; Tag
0x14002ee5b  mov     rcx, rbx; P
0x14002ee5e  call    cs:__imp_ExFreePoolWithTag
0x14002ee65  nop     dword ptr [rax+rax+00h]
0x14002ee6a  jmp     loc_14002ED1D
0x14002ee6f  lea     rcx, aNdisallocatene_2; "NdisAllocateNetBufferAndNetBufferList: "...
0x14002ee76  call    cs:__imp_DbgPrint
0x14002ee7d  nop     dword ptr [rax+rax+00h]
0x14002ee82  jmp     loc_14002EB83
0x14002ee87  mov     rcx, [rbx+18h]; BaseAddress
0x14002ee8b  mov     rdx, rbx; MemoryDescriptorList
0x14002ee8e  call    cs:__imp_MmUnmapLockedPages
0x14002ee95  nop     dword ptr [rax+rax+00h]
0x14002ee9a  jmp     loc_14002ECF5
0x14002ee9f  mov     rcx, rsi; NetBufferList
0x14002eea2  call    NdisFreeNetBufferList
0x14002eea7  jmp     loc_14002EB83
0x14002eeac  mov     rcx, [rbx+18h]; BaseAddress
0x14002eeb0  mov     rdx, rbx; MemoryDescriptorList
0x14002eeb3  call    cs:__imp_MmUnmapLockedPages
0x14002eeba  nop     dword ptr [rax+rax+00h]
0x14002eebf  jmp     loc_14002EB8D
```
