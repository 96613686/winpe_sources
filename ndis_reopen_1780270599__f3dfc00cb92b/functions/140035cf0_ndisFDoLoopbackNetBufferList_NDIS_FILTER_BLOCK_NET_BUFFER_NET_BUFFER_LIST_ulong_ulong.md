# ndisFDoLoopbackNetBufferList(_NDIS_FILTER_BLOCK *,_NET_BUFFER *,_NET_BUFFER_LIST *,ulong,ulong)

- ea: `0x140035cf0`
- end: `0x140036187`
- name: `?ndisFDoLoopbackNetBufferList@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER@@PEAU_NET_BUFFER_LIST@@KK@Z`
- size: `1175`
- prototype: `void __fastcall(struct _NDIS_FILTER_BLOCK *, struct _NET_BUFFER *, struct _NET_BUFFER_LIST *, unsigned int, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x140035540`

## callees

- `0x1400231d0`
- `0x140025d30`
- `0x1400260b0`
- `0x140035cf0`
- `0x140036bf0`
- `0x1400eb460`
- `0x1400eb4c0`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140035faa`
- `ntoskrnl!DbgPrint` at `0x140036139`
- `ntoskrnl!DbgPrint` at `0x140035faa`
- `ntoskrnl!DbgPrint` at `0x140036139`
- `ntoskrnl!MmSizeOfMdl` at `0x140035d17`
- `ntoskrnl!MmSizeOfMdl` at `0x140035d17`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400360a7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400360d9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003610b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400360a7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400360d9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003610b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140035dd3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140035dd3`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036151`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036176`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036151`
- `ntoskrnl!MmUnmapLockedPages` at `0x140036176`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035f50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036121`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035f50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036121`
- `ntoskrnl!ExAllocatePool2` at `0x140035d54`
- `ntoskrnl!ExAllocatePool2` at `0x140035d54`

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
0x140035cf0  mov     [rsp+arg_18], r9d
0x140035cf5  mov     [rsp+arg_10], r8
0x140035cfa  mov     [rsp+arg_0], rcx
0x140035cff  push    rbx
0x140035d00  push    r13
0x140035d02  push    r14
0x140035d04  sub     rsp, 50h
0x140035d08  mov     r14d, [rdx+18h]
0x140035d0c  mov     r13, rdx
0x140035d0f  mov     edx, r14d; Length
0x140035d12  mov     ecx, 0FFFh; Base
0x140035d17  call    cs:__imp_MmSizeOfMdl
0x140035d1e  nop     dword ptr [rax+rax+00h]
0x140035d23  lea     rbx, [rax+7]
0x140035d27  mov     eax, 0FFFFFFF8h
0x140035d2c  and     rbx, rax
0x140035d2f  lea     rax, [r14+rbx]
0x140035d33  mov     rcx, rax
0x140035d36  shr     rcx, 20h
0x140035d3a  test    ecx, ecx
0x140035d3c  jnz     loc_140035F78
0x140035d42  mov     edx, eax
0x140035d44  mov     ecx, 40h ; '@'
0x140035d49  mov     r8d, 706C444Eh
0x140035d4f  mov     [rsp+68h+var_20], rsi
0x140035d54  call    cs:__imp_ExAllocatePool2
0x140035d5b  nop     dword ptr [rax+rax+00h]
0x140035d60  mov     rsi, rax
0x140035d63  test    rax, rax
0x140035d66  jz      loc_140035F73
0x140035d6c  lea     r8, [rbx+rax]
0x140035d70  cmp     r8, rax
0x140035d73  jb      loc_14003611C
0x140035d79  mov     edx, r8d
0x140035d7c  mov     [rsp+68h+var_28], rdi
0x140035d81  mov     ecx, edx
0x140035d83  mov     [rsp+68h+var_30], r12
0x140035d88  and     ecx, 0FFFh
0x140035d8e  mov     [rsp+68h+var_38], r15
0x140035d93  add     rcx, 0FFFh
0x140035d9a  mov     [rax+28h], r14d
0x140035d9e  add     rcx, r14
0x140035da1  xor     r12d, r12d
0x140035da4  shr     rcx, 0Ch
0x140035da8  and     r8, 0FFFFFFFFFFFFF000h
0x140035daf  add     cx, 6
0x140035db3  mov     [rax], r12
0x140035db6  shl     cx, 3
0x140035dba  and     edx, 0FFFh
0x140035dc0  mov     [rax+8], cx
0x140035dc4  mov     rcx, rax; MemoryDescriptorList
0x140035dc7  mov     [rax+0Ah], r12w
0x140035dcc  mov     [rax+20h], r8
0x140035dd0  mov     [rax+2Ch], edx
0x140035dd3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140035dda  nop     dword ptr [rax+rax+00h]
0x140035ddf  mov     r15, cs:?ndisNetBufferListPool@@3PEAXEA; void * ndisNetBufferListPool
0x140035de6  mov     [rsp+68h+arg_8], r12d
0x140035deb  test    r15, r15
0x140035dee  jz      loc_140036132
0x140035df4  mov     eax, [r15+2Ch]
0x140035df8  and     al, 5
0x140035dfa  cmp     al, 1
0x140035dfc  jnz     loc_140035FA0
0x140035e02  xor     r8d, r8d
0x140035e05  lea     r9, [rsp+68h+arg_8]
0x140035e0a  xor     edx, edx
0x140035e0c  mov     rcx, r15
0x140035e0f  call    ndisAllocateNetBufferListInternal
0x140035e14  mov     rbx, rax
0x140035e17  test    rax, rax
0x140035e1a  jz      short loc_140035E68
0x140035e1c  lea     rdi, [rax+180h]
0x140035e23  xor     edx, edx; Val
0x140035e25  mov     rcx, rdi; void *
0x140035e28  mov     r8d, 0B0h; Size
0x140035e2e  call    memset
0x140035e33  mov     ecx, r12d
0x140035e36  mov     [rdi+20h], rsi
0x140035e3a  mov     rax, rsi
0x140035e3d  mov     [rdi+18h], r14d
0x140035e41  mov     [rdi+38h], r15
0x140035e45  mov     edx, [rax+28h]
0x140035e48  cmp     ecx, edx
0x140035e4a  jnb     loc_140035FBB
0x140035e50  mov     [rdi+8], rax
0x140035e54  mov     [rdi+10h], ecx
0x140035e57  mov     [rbx+8], rdi
0x140035e5b  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 3; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140035e62  jge     loc_140035F83
0x140035e68  test    rbx, rbx
0x140035e6b  jnz     loc_140035FCE
0x140035e71  test    byte ptr [rsi+0Ah], 20h
0x140035e75  jnz     loc_14003616F
0x140035e7b  xor     edx, edx; Tag
0x140035e7d  mov     rcx, rsi; P
0x140035e80  call    cs:__imp_ExFreePoolWithTag
0x140035e87  nop     dword ptr [rax+rax+00h]
0x140035e8c  jmp     loc_140035F64
0x140035e91  or      dword ptr [rbx+88h], 80h
0x140035e9b  or      dword ptr [rbx+80h], 8000h
0x140035ea5  test    [rsp+68h+arg_20], 2
0x140035ead  mov     rax, [rsp+68h+arg_10]
0x140035eb5  mov     rax, [rax+78h]
0x140035eb9  mov     [rbx+78h], rax
0x140035ebd  jz      short loc_140035EC9
0x140035ebf  or      dword ptr [rbx+88h], 200h
0x140035ec9  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140035ed0  jz      short loc_140035EF0
0x140035ed2  mov     r9d, 9Bh; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x140035ed8  mov     [rsp+68h+BugCheckOnFailure], 0; unsigned int
0x140035ee0  xor     r8d, r8d; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140035ee3  mov     edx, 0A8h; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140035ee8  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x140035eeb  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x140035ef0  mov     rcx, [rsp+68h+arg_0]
0x140035ef5  mov     r9d, 1
0x140035efb  mov     r8d, [rsp+68h+arg_18]
0x140035f03  mov     rdx, rbx
0x140035f06  mov     [rsp+68h+BugCheckOnFailure], 2
0x140035f0e  mov     rax, [rcx+278h]
0x140035f15  call    _guard_dispatch_icall
0x140035f1a  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x140035f21  jz      short loc_140035F41
0x140035f23  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140035f25  mov     [rsp+68h+BugCheckOnFailure], 0; unsigned int
0x140035f2d  mov     r9d, 9Ch; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x140035f33  mov     r8d, 0A8h; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140035f39  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x140035f3c  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x140035f41  test    byte ptr [rsi+0Ah], 20h
0x140035f45  jnz     loc_14003614A
0x140035f4b  xor     edx, edx; Tag
0x140035f4d  mov     rcx, rsi; P
0x140035f50  call    cs:__imp_ExFreePoolWithTag
0x140035f57  nop     dword ptr [rax+rax+00h]
0x140035f5c  mov     rcx, rbx; NetBufferList
0x140035f5f  call    NdisFreeNetBufferList
0x140035f64  mov     r12, [rsp+68h+var_30]
0x140035f69  mov     rdi, [rsp+68h+var_28]
0x140035f6e  mov     r15, [rsp+68h+var_38]
0x140035f73  mov     rsi, [rsp+68h+var_20]
0x140035f78  add     rsp, 50h
0x140035f7c  pop     r14
0x140035f7e  pop     r13
0x140035f80  pop     rbx
0x140035f81  retn
0x140035f83  xor     r9d, r9d; void *
0x140035f86  mov     [rsp+68h+BugCheckOnFailure], r12d; unsigned int
0x140035f8b  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x140035f8d  mov     r8d, 3; unsigned int
0x140035f93  mov     rcx, rbx; struct _NET_BUFFER_LIST *
0x140035f96  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140035f9b  jmp     loc_140035E68
0x140035fa0  mov     rdx, r15
0x140035fa3  lea     rcx, aNdisallocatene_0; "NdisAllocateNetBufferAndNetBufferList: "...
0x140035faa  call    cs:__imp_DbgPrint
0x140035fb1  nop     dword ptr [rax+rax+00h]
0x140035fb6  jmp     loc_140035E71
0x140035fbb  mov     rax, [rax]
0x140035fbe  sub     ecx, edx
0x140035fc0  test    rax, rax
0x140035fc3  jnz     loc_140035E45
0x140035fc9  jmp     loc_140035E50
0x140035fce  mov     rax, [rbx+8]
0x140035fd2  mov     rcx, [rax+20h]; MemoryDescriptorList
0x140035fd6  test    byte ptr [rcx+0Ah], 5
0x140035fda  jz      loc_14003608F
0x140035fe0  mov     r12, [rcx+18h]
0x140035fe4  test    r12, r12
0x140035fe7  jz      loc_140036162
0x140035fed  mov     r15, [r13+8]
0x140035ff1  test    byte ptr [r15+0Ah], 5
0x140035ff6  jz      loc_1400360BB
0x140035ffc  mov     r8, [r15+18h]
0x140036000  test    r8, r8
0x140036003  jz      loc_140036162
0x140036009  mov     edx, [r13+10h]
0x14003600d  mov     eax, r14d
0x140036010  mov     ecx, [r15+28h]
0x140036014  sub     ecx, edx
0x140036016  cmp     ecx, r14d
0x140036019  cmovbe  eax, ecx
0x14003601c  add     rdx, r8; Src
0x14003601f  mov     r8d, eax; Size
0x140036022  mov     rcx, r12; void *
0x140036025  mov     edi, eax
0x140036027  sub     r14d, eax
0x14003602a  call    memmove
0x14003602f  mov     r15, [r15]
0x140036032  add     r12, rdi
0x140036035  test    r15, r15
0x140036038  jz      loc_140035E91
0x14003603e  test    r14d, r14d
0x140036041  jz      loc_140035E91
0x140036047  test    byte ptr [r15+0Ah], 5
0x14003604c  jz      loc_1400360ED
0x140036052  mov     rax, [r15+18h]
0x140036056  test    rax, rax
0x140036059  jz      loc_140035E91
0x14003605f  mov     edx, [r15+28h]
0x140036063  mov     ecx, r14d
0x140036066  cmp     r14d, edx
0x140036069  cmovnb  ecx, edx
0x14003606c  mov     rdx, rax; Src
0x14003606f  mov     edi, ecx
0x140036071  sub     r14d, ecx
0x140036074  mov     r8d, ecx; Size
0x140036077  mov     rcx, r12; void *
0x14003607a  call    memmove
0x14003607f  mov     r15, [r15]
0x140036082  add     r12, rdi
0x140036085  test    r15, r15
0x140036088  jnz     short loc_14003603E
0x14003608a  jmp     loc_140035E91
0x14003608f  mov     [rsp+68h+Priority], 40000000h; Priority
0x140036097  xor     r9d, r9d; RequestedAddress
0x14003609a  xor     edx, edx; AccessMode
0x14003609c  mov     [rsp+68h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x1400360a1  mov     r8d, 1; CacheType
0x1400360a7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400360ae  nop     dword ptr [rax+rax+00h]
0x1400360b3  mov     r12, rax
0x1400360b6  jmp     loc_140035FE4
0x1400360bb  mov     [rsp+68h+Priority], 40000000h; Priority
0x1400360c3  xor     r9d, r9d; RequestedAddress
0x1400360c6  xor     edx, edx; AccessMode
0x1400360c8  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400360d0  mov     r8d, 1; CacheType
0x1400360d6  mov     rcx, r15; MemoryDescriptorList
0x1400360d9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400360e0  nop     dword ptr [rax+rax+00h]
0x1400360e5  mov     r8, rax
0x1400360e8  jmp     loc_140036000
0x1400360ed  mov     [rsp+68h+Priority], 40000000h; Priority
0x1400360f5  xor     r9d, r9d; RequestedAddress
0x1400360f8  xor     edx, edx; AccessMode
0x1400360fa  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140036102  mov     r8d, 1; CacheType
0x140036108  mov     rcx, r15; MemoryDescriptorList
0x14003610b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140036112  nop     dword ptr [rax+rax+00h]
0x140036117  jmp     loc_140036056
0x14003611c  xor     edx, edx; Tag
0x14003611e  mov     rcx, rsi; P
0x140036121  call    cs:__imp_ExFreePoolWithTag
0x140036128  nop     dword ptr [rax+rax+00h]
0x14003612d  jmp     loc_140035F73
0x140036132  lea     rcx, aNdisallocatene_2; "NdisAllocateNetBufferAndNetBufferList: "...
0x140036139  call    cs:__imp_DbgPrint
0x140036140  nop     dword ptr [rax+rax+00h]
0x140036145  jmp     loc_140035E71
0x14003614a  mov     rcx, [rsi+18h]; BaseAddress
0x14003614e  mov     rdx, rsi; MemoryDescriptorList
0x140036151  call    cs:__imp_MmUnmapLockedPages
0x140036158  nop     dword ptr [rax+rax+00h]
0x14003615d  jmp     loc_140035F4B
0x140036162  mov     rcx, rbx; NetBufferList
0x140036165  call    NdisFreeNetBufferList
0x14003616a  jmp     loc_140035E71
0x14003616f  mov     rcx, [rsi+18h]; BaseAddress
0x140036173  mov     rdx, rsi; MemoryDescriptorList
0x140036176  call    cs:__imp_MmUnmapLockedPages
0x14003617d  nop     dword ptr [rax+rax+00h]
0x140036182  jmp     loc_140035E7B
```
