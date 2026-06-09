# ndisLWM5IndicateReceive

- ea: `0x14008a290`
- end: `0x14008a740`
- name: `ndisLWM5IndicateReceive`
- size: `1200`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006fe00`

## callees

- `0x140029eb0`
- `0x14002a5b0`
- `0x14006a3d0`
- `0x140088a2c`
- `0x14008a290`
- `0x1400eb460`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14008a34c`
- `ntoskrnl!MmSizeOfMdl` at `0x14008a398`
- `ntoskrnl!MmSizeOfMdl` at `0x14008a34c`
- `ntoskrnl!MmSizeOfMdl` at `0x14008a398`
- `ntoskrnl!MmMapLockedPages` at `0x14008a4db`
- `ntoskrnl!MmMapLockedPages` at `0x14008a4db`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14008a40a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14008a40a`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008a6da`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008a6da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a6f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008a6f1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a326`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a326`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a704`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a704`
- `ntoskrnl!ExAllocatePool2` at `0x14008a379`
- `ntoskrnl!ExAllocatePool2` at `0x14008a379`
- `ntoskrnl!IoFreeMdl` at `0x14008a5cc`
- `ntoskrnl!IoFreeMdl` at `0x14008a5cc`

## pseudocode

```c
void __fastcall ndisLWM5IndicateReceive(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4,
        void *Src,
        unsigned int a6,
        size_t Size)
{
  __int64 v7; // r13
  size_t v9; // rsi
  __int64 v11; // r10
  __int64 v12; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v13; // rbx
  struct _MDL *Pool2; // rax
  unsigned int v15; // ecx
  struct _MDL *v16; // r12
  SIZE_T v17; // rax
  MDL *v18; // r8
  int v19; // edi
  struct _NPAGED_LOOKASIDE_LIST *v20; // rbx
  unsigned int v21; // edi
  size_t v22; // r8
  size_t v23; // rbx
  PNDIS_BUFFER v24; // rsi
  unsigned int v25; // edx
  _MDL *Head; // r13
  char *v27; // rax
  ULONG ByteCount; // edi
  _MDL *v29; // rcx
  PNDIS_PACKET v30; // r10
  unsigned int v31; // ecx
  _MDL *v32; // rbx
  PNDIS_PACKET v33; // r9
  unsigned int v34; // r10d
  PNDIS_PACKET v35; // rcx
  int v36; // [rsp+40h] [rbp-30h] BYREF
  PNDIS_PACKET Packet; // [rsp+48h] [rbp-28h] BYREF
  PNPAGED_LOOKASIDE_LIST Lookaside; // [rsp+50h] [rbp-20h]
  char *v39; // [rsp+58h] [rbp-18h]
  PNDIS_BUFFER Buffer; // [rsp+60h] [rbp-10h] BYREF
  __int64 v41; // [rsp+68h] [rbp-8h]
  int Status; // [rsp+A0h] [rbp+30h] BYREF

  if ( !a1 )
    return;
  v7 = *(_QWORD *)(a1 + 296);
  v9 = a4;
  Status = 0;
  Packet = 0;
  v41 = v7;
  if ( !MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v7, 0x20000000u) )
    return;
  MINIPORT_TEST_FLAG(*(const struct _NDIS_MINIPORT_BLOCK **)(v11 + 296), 0x40000u);
  v12 = (unsigned int)(v9 + Size);
  if ( (unsigned int)v12 < (unsigned int)Size )
    return;
  if ( (unsigned int)v12 >= 0x64 )
  {
    if ( (unsigned int)v12 >= 0x5EA )
    {
      v15 = v12 + ((MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v12) + 7) & 0xFFFFFFF8);
      if ( v15 < (unsigned int)v12 )
        return;
      Lookaside = 0;
      Pool2 = (struct _MDL *)ExAllocatePool2(66, v15, 1918125134);
      goto LABEL_11;
    }
    v13 = &ndisRcv1514BytesLL;
  }
  else
  {
    v13 = &ndisRcv100BytesLL;
  }
  Lookaside = v13;
  Pool2 = (struct _MDL *)ExAllocateFromNPagedLookasideList(v13);
LABEL_11:
  v16 = Pool2;
  if ( !Pool2 )
    return;
  v17 = MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v12);
  v16->Next = 0;
  v16->ByteCount = v12;
  v18 = (struct _MDL *)((char *)v16 + ((v17 + 7) & 0xFFFFFFFFFFFFFFF8uLL));
  Buffer = v18;
  LOWORD(v17) = (_WORD)v16 + ((v17 + 7) & 0xFFF8);
  v16->ByteOffset = v17 & 0xFFF;
  v16->MdlFlags = 0;
  v16->Size = 8 * ((((v17 & 0xFFF) + v12 + 4095) >> 12) + 6);
  v16->StartVa = (PVOID)((unsigned __int64)v18 & 0xFFFFFFFFFFFFF000uLL);
  MmBuildMdlForNonPagedPool(v16);
  NdisAllocatePacket(&Status, &Packet, ndisRecvPacketPool);
  v19 = Status;
  if ( Status )
    goto LABEL_32;
  v20 = Lookaside;
  Status = 0;
  v21 = Size;
  Packet->Private.Head = v16;
  Packet->Private.Tail = v16;
  *(_QWORD *)Packet->MiniportReserved = v20;
  LODWORD(Packet[-1].Reserved[1]) |= 1u;
  if ( v21 <= a6 )
  {
    v22 = v9;
    v23 = v9;
    v24 = Buffer;
    memmove(Buffer, a3, v22);
    memmove((char *)v24 + v23, Src, v21);
    goto LABEL_27;
  }
  v36 = 0;
  Buffer = 0;
  v25 = ++*(_DWORD *)Packet[-1].ProtocolReserved;
  if ( v25 >= 3 * ndisPacketStackSize )
  {
    *(_DWORD *)Packet[-1].ProtocolReserved = v25 - 1;
LABEL_34:
    v35 = Packet;
    goto LABEL_35;
  }
  Head = Packet->Private.Head;
  v27 = (char *)((Head->MdlFlags & 5) != 0 ? Head->MappedSystemVa : MmMapLockedPages(Head, 0));
  ByteCount = Head->ByteCount;
  v39 = v27;
  memmove(v27, a3, v9);
  NdisAllocateBuffer(&Status, &Buffer, 0, &v39[v9], ByteCount - v9);
  v19 = Status;
  if ( Status )
    goto LABEL_32;
  v29 = Buffer;
  Buffer->Next = Head->Next;
  Packet->Private.Head = v29;
  *(_QWORD *)Packet->ProtocolReserved = Head;
  v30 = Packet;
  v31 = *(_DWORD *)Packet[-1].ProtocolReserved;
  if ( v31 < 3 * ndisPacketStackSize )
  {
    *((_QWORD *)&Packet->Private.PhysicalCount + 6 * (v31 / 3 - (unsigned __int64)ndisPacketStackSize) + v31 % 3) = 0;
    v30 = Packet;
  }
  v7 = v41;
  v19 = (*(__int64 (__fastcall **)(PNDIS_PACKET, int *, _QWORD, __int64, _DWORD, _DWORD))(*(_QWORD *)(v41 + 3760) + 216LL))(
          v30,
          &v36,
          *(_QWORD *)(v41 + 24),
          a2,
          0,
          Size);
  if ( v19 == 259 )
    goto LABEL_32;
  v32 = *(_MDL **)Packet->ProtocolReserved;
  IoFreeMdl(Packet->Private.Head);
  Packet->Private.Head = v32;
  *(_QWORD *)Packet->ProtocolReserved = 0;
  v33 = Packet;
  v34 = *(_DWORD *)Packet[-1].ProtocolReserved;
  if ( v34 < 3 * ndisPacketStackSize )
  {
    *((_QWORD *)&Packet->Private.PhysicalCount + 6 * (v34 / 3 - (unsigned __int64)ndisPacketStackSize) + v34 % 3) = 0;
    v33 = Packet;
  }
  --*(_DWORD *)v33[-1].ProtocolReserved;
  if ( v19 )
  {
LABEL_32:
    if ( v19 == 259 )
      return;
    v20 = Lookaside;
    goto LABEL_34;
  }
LABEL_27:
  *(unsigned int *)((char *)&Packet->Private.Count + Packet->Private.NdisPacketOobOffset) = 0;
  if ( !*(_DWORD *)(v7 + 464) )
    *(_DWORD *)((char *)&Packet->Private.Tail + Packet->Private.NdisPacketOobOffset) = 14;
  (*(void (__fastcall **)(__int64, PNDIS_PACKET *, __int64))(v7 + 432))(v7, &Packet, 1);
  if ( !MINIPORT_TEST_FLAG((const struct _NDIS_MINIPORT_BLOCK *)v7, 0x40000u) )
  {
    v35 = Packet;
    if ( *(unsigned int *)((char *)&Packet->Private.Count + Packet->Private.NdisPacketOobOffset) != 259 )
    {
      v20 = Lookaside;
LABEL_35:
      if ( v35 )
      {
        LODWORD(v35[-1].Reserved[1]) &= ~1u;
        NdisFreePacket(Packet);
      }
      if ( (v16->MdlFlags & 0x20) != 0 )
        MmUnmapLockedPages(v16->MappedSystemVa, v16);
      if ( v20 )
        ExFreeToNPagedLookasideList(v20, v16);
      else
        ExFreePoolWithTag(v16, 0);
    }
  }
}

```

## disassembly

```asm
0x14008a290  test    rcx, rcx
0x14008a293  jz      locret_14008A733
0x14008a299  push    rbp
0x14008a29a  push    rbx
0x14008a29b  push    rsi
0x14008a29c  push    r14
0x14008a29e  push    r15
0x14008a2a0  mov     rbp, rsp
0x14008a2a3  sub     rsp, 70h
0x14008a2a7  xor     ebx, ebx
0x14008a2a9  mov     [rsp+70h+arg_18], r13
0x14008a2b1  mov     r13, [rcx+128h]
0x14008a2b8  mov     r15, rdx
0x14008a2bb  mov     r10, rcx
0x14008a2be  mov     esi, r9d
0x14008a2c1  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x14008a2c4  mov     [rbp+Status], ebx
0x14008a2c7  mov     edx, 20000000h; unsigned int
0x14008a2cc  mov     [rbp+Packet], rbx
0x14008a2d0  mov     r14, r8
0x14008a2d3  mov     [rbp+var_8], r13
0x14008a2d7  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14008a2dc  test    al, al
0x14008a2de  jz      loc_14008A720
0x14008a2e4  mov     rcx, [r10+128h]; struct _NDIS_MINIPORT_BLOCK *
0x14008a2eb  mov     edx, 40000h; unsigned int
0x14008a2f0  mov     [rsp+70h+arg_8], rdi
0x14008a2f8  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14008a2fd  mov     eax, dword ptr [rbp+Size]
0x14008a300  lea     edi, [rsi+rax]
0x14008a303  cmp     edi, eax
0x14008a305  jb      loc_14008A718
0x14008a30b  mov     [rsp+70h+arg_10], r12
0x14008a313  cmp     edi, 64h ; 'd'
0x14008a316  jnb     short loc_14008A334
0x14008a318  lea     rbx, ?ndisRcv100BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST ndisRcv100BytesLL
0x14008a31f  mov     rcx, rbx; Lookaside
0x14008a322  mov     [rbp+Lookaside], rbx
0x14008a326  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008a32d  nop     dword ptr [rax+rax+00h]
0x14008a332  jmp     short loc_14008A385
0x14008a334  cmp     edi, 5EAh
0x14008a33a  jnb     short loc_14008A345
0x14008a33c  lea     rbx, ?ndisRcv1514BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST ndisRcv1514BytesLL
0x14008a343  jmp     short loc_14008A31F
0x14008a345  mov     edx, edi; Length
0x14008a347  mov     ecx, 0FFFh; Base
0x14008a34c  call    cs:__imp_MmSizeOfMdl
0x14008a353  nop     dword ptr [rax+rax+00h]
0x14008a358  lea     ecx, [rax+7]
0x14008a35b  and     ecx, 0FFFFFFF8h
0x14008a35e  add     ecx, edi
0x14008a360  cmp     ecx, edi
0x14008a362  jb      loc_14008A710
0x14008a368  mov     edx, ecx
0x14008a36a  mov     r8d, 7254444Eh
0x14008a370  mov     ecx, 42h ; 'B'
0x14008a375  mov     [rbp+Lookaside], rbx
0x14008a379  call    cs:__imp_ExAllocatePool2
0x14008a380  nop     dword ptr [rax+rax+00h]
0x14008a385  mov     r12, rax
0x14008a388  test    rax, rax
0x14008a38b  jz      loc_14008A710
0x14008a391  mov     edx, edi; Length
0x14008a393  mov     ecx, 0FFFh; Base
0x14008a398  call    cs:__imp_MmSizeOfMdl
0x14008a39f  nop     dword ptr [rax+rax+00h]
0x14008a3a4  lea     rcx, [rdi+0FFFh]
0x14008a3ab  mov     qword ptr [r12], 0
0x14008a3b3  mov     [r12+28h], edi
0x14008a3b8  lea     r8, [rax+7]
0x14008a3bc  and     r8, 0FFFFFFFFFFFFFFF8h
0x14008a3c0  add     r8, r12
0x14008a3c3  mov     edx, r8d
0x14008a3c6  mov     [rbp+Buffer], r8
0x14008a3ca  mov     eax, edx
0x14008a3cc  and     edx, 0FFFh
0x14008a3d2  and     eax, 0FFFh
0x14008a3d7  mov     [r12+2Ch], edx
0x14008a3dc  add     rcx, rax
0x14008a3df  xor     eax, eax
0x14008a3e1  shr     rcx, 0Ch
0x14008a3e5  add     cx, 6
0x14008a3e9  mov     [r12+0Ah], ax
0x14008a3ef  shl     cx, 3
0x14008a3f3  mov     rax, r8
0x14008a3f6  mov     [r12+8], cx
0x14008a3fc  and     rax, 0FFFFFFFFFFFFF000h
0x14008a402  mov     rcx, r12; MemoryDescriptorList
0x14008a405  mov     [r12+20h], rax
0x14008a40a  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14008a411  nop     dword ptr [rax+rax+00h]
0x14008a416  mov     r8, cs:?ndisRecvPacketPool@@3PEAU_NDIS_PKT_POOL@@EA; PoolHandle
0x14008a41d  lea     rdx, [rbp+Packet]; Packet
0x14008a421  lea     rcx, [rbp+Status]; Status
0x14008a425  call    NdisAllocatePacket
0x14008a42a  mov     edi, [rbp+Status]
0x14008a42d  test    edi, edi
0x14008a42f  jnz     loc_14008A6A8
0x14008a435  mov     rax, [rbp+Packet]
0x14008a439  mov     rbx, [rbp+Lookaside]
0x14008a43d  mov     [rbp+Status], edi
0x14008a440  mov     edi, dword ptr [rbp+Size]
0x14008a443  mov     [rax+8], r12
0x14008a447  mov     rax, [rbp+Packet]
0x14008a44b  mov     [rax+10h], r12
0x14008a44f  mov     rax, [rbp+Packet]
0x14008a453  mov     [rax+30h], rbx
0x14008a457  mov     rax, [rbp+Packet]
0x14008a45b  or      dword ptr [rax-10h], 1
0x14008a45f  cmp     edi, [rbp+arg_28]
0x14008a462  ja      short loc_14008A48E
0x14008a464  mov     r8, rsi; Size
0x14008a467  mov     rbx, rsi
0x14008a46a  mov     rsi, [rbp+Buffer]
0x14008a46e  mov     rdx, r14; Src
0x14008a471  mov     rcx, rsi; void *
0x14008a474  call    memmove
0x14008a479  mov     rdx, [rbp+Src]; Src
0x14008a47d  lea     rcx, [rbx+rsi]; void *
0x14008a481  mov     r8d, edi; Size
0x14008a484  call    memmove
0x14008a489  jmp     loc_14008A636
0x14008a48e  mov     rax, [rbp+Packet]
0x14008a492  mov     [rbp+var_30], 0
0x14008a499  mov     [rbp+Buffer], 0
0x14008a4a1  inc     dword ptr [rax-8]
0x14008a4a4  mov     eax, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14008a4aa  mov     r13, [rbp+Packet]
0x14008a4ae  lea     ecx, [rax+rax*2]
0x14008a4b1  mov     edx, [r13-8]
0x14008a4b5  cmp     edx, ecx
0x14008a4b7  jb      short loc_14008A4C5
0x14008a4b9  lea     eax, [rdx-1]
0x14008a4bc  mov     [r13-8], eax
0x14008a4c0  jmp     loc_14008A6B4
0x14008a4c5  mov     r13, [r13+8]
0x14008a4c9  test    byte ptr [r13+0Ah], 5
0x14008a4ce  jz      short loc_14008A4D6
0x14008a4d0  mov     rax, [r13+18h]
0x14008a4d4  jmp     short loc_14008A4E7
0x14008a4d6  xor     edx, edx; AccessMode
0x14008a4d8  mov     rcx, r13; MemoryDescriptorList
0x14008a4db  call    cs:__imp_MmMapLockedPages
0x14008a4e2  nop     dword ptr [rax+rax+00h]
0x14008a4e7  mov     edi, [r13+28h]
0x14008a4eb  mov     r8, rsi; Size
0x14008a4ee  mov     rdx, r14; Src
0x14008a4f1  mov     [rbp+var_18], rax
0x14008a4f5  mov     rcx, rax; void *
0x14008a4f8  call    memmove
0x14008a4fd  mov     r9, [rbp+var_18]
0x14008a501  lea     rdx, [rbp+Buffer]; Buffer
0x14008a505  sub     edi, esi
0x14008a507  lea     rcx, [rbp+Status]; Status
0x14008a50b  add     r9, rsi; VirtualAddress
0x14008a50e  mov     [rsp+70h+Length], edi; Length
0x14008a512  xor     r8d, r8d; PoolHandle
0x14008a515  call    NdisAllocateBuffer
0x14008a51a  mov     edi, [rbp+Status]
0x14008a51d  test    edi, edi
0x14008a51f  jnz     loc_14008A6A8
0x14008a525  mov     rax, [r13+0]
0x14008a529  mov     rcx, [rbp+Buffer]
0x14008a52d  mov     [rcx], rax
0x14008a530  mov     rax, [rbp+Packet]
0x14008a534  mov     [rax+8], rcx
0x14008a538  mov     rax, [rbp+Packet]
0x14008a53c  mov     [rax+60h], r13
0x14008a540  mov     r9d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14008a547  mov     r10, [rbp+Packet]
0x14008a54b  lea     eax, [r9+r9*2]
0x14008a54f  mov     ecx, [r10-8]
0x14008a553  cmp     ecx, eax
0x14008a555  jnb     short loc_14008A57F
0x14008a557  mov     eax, 0AAAAAAABh
0x14008a55c  mul     ecx
0x14008a55e  shr     edx, 1
0x14008a560  mov     r8d, edx
0x14008a563  lea     eax, [rdx+rdx*2]
0x14008a566  sub     ecx, eax
0x14008a568  sub     r8, r9
0x14008a56b  lea     rax, [r8+r8*2]
0x14008a56f  lea     rcx, [rcx+rax*2]
0x14008a573  mov     qword ptr [r10+rcx*8], 0
0x14008a57b  mov     r10, [rbp+Packet]
0x14008a57f  mov     r13, [rbp+var_8]
0x14008a583  mov     r9, r15
0x14008a586  mov     edx, dword ptr [rbp+Size]
0x14008a589  mov     rcx, r10
0x14008a58c  mov     [rsp+70h+var_48], edx
0x14008a590  lea     rdx, [rbp+var_30]
0x14008a594  mov     [rsp+70h+Length], 0
0x14008a59c  mov     rax, [r13+0EB0h]
0x14008a5a3  mov     r8, [r13+18h]
0x14008a5a7  mov     rax, [rax+0D8h]
0x14008a5ae  call    _guard_dispatch_icall
0x14008a5b3  mov     edi, eax
0x14008a5b5  cmp     eax, 103h
0x14008a5ba  jz      loc_14008A6A8
0x14008a5c0  mov     rcx, [rbp+Packet]
0x14008a5c4  mov     rbx, [rcx+60h]
0x14008a5c8  mov     rcx, [rcx+8]; Mdl
0x14008a5cc  call    cs:__imp_IoFreeMdl
0x14008a5d3  nop     dword ptr [rax+rax+00h]
0x14008a5d8  mov     rcx, [rbp+Packet]
0x14008a5dc  mov     [rcx+8], rbx
0x14008a5e0  mov     rcx, [rbp+Packet]
0x14008a5e4  mov     qword ptr [rcx+60h], 0
0x14008a5ec  mov     r11d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14008a5f3  mov     r9, [rbp+Packet]
0x14008a5f7  lea     ecx, [r11+r11*2]
0x14008a5fb  mov     r10d, [r9-8]
0x14008a5ff  cmp     r10d, ecx
0x14008a602  jnb     short loc_14008A62E
0x14008a604  mov     eax, 0AAAAAAABh
0x14008a609  mul     r10d
0x14008a60c  shr     edx, 1
0x14008a60e  mov     r8d, edx
0x14008a611  lea     eax, [rdx+rdx*2]
0x14008a614  sub     r10d, eax
0x14008a617  sub     r8, r11
0x14008a61a  lea     rax, [r8+r8*2]
0x14008a61e  lea     rcx, [r10+rax*2]
0x14008a622  mov     qword ptr [r9+rcx*8], 0
0x14008a62a  mov     r9, [rbp+Packet]
0x14008a62e  dec     dword ptr [r9-8]
0x14008a632  test    edi, edi
0x14008a634  jnz     short loc_14008A6A8
0x14008a636  mov     rcx, [rbp+Packet]
0x14008a63a  movzx   eax, word ptr [rcx+2Ah]
0x14008a63e  mov     dword ptr [rax+rcx+20h], 0
0x14008a646  cmp     dword ptr [r13+1D0h], 0
0x14008a64e  jnz     short loc_14008A662
0x14008a650  mov     r8, [rbp+Packet]
0x14008a654  movzx   eax, word ptr [r8+2Ah]
0x14008a659  mov     dword ptr [rax+r8+10h], 0Eh
0x14008a662  mov     rax, [r13+1B0h]
0x14008a669  lea     rdx, [rbp+Packet]
0x14008a66d  mov     r8d, 1
0x14008a673  mov     rcx, r13
0x14008a676  call    _guard_dispatch_icall
0x14008a67b  mov     edx, 40000h; unsigned int
0x14008a680  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x14008a683  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14008a688  test    al, al
0x14008a68a  jnz     loc_14008A710
0x14008a690  mov     rcx, [rbp+Packet]
0x14008a694  movzx   eax, word ptr [rcx+2Ah]
0x14008a698  cmp     dword ptr [rax+rcx+20h], 103h
0x14008a6a0  jz      short loc_14008A710
0x14008a6a2  mov     rbx, [rbp+Lookaside]
0x14008a6a6  jmp     short loc_14008A6B8
0x14008a6a8  cmp     edi, 103h
0x14008a6ae  jz      short loc_14008A710
0x14008a6b0  mov     rbx, [rbp+Lookaside]
0x14008a6b4  mov     rcx, [rbp+Packet]
0x14008a6b8  test    rcx, rcx
0x14008a6bb  jz      short loc_14008A6CA
0x14008a6bd  and     dword ptr [rcx-10h], 0FFFFFFFEh
0x14008a6c1  mov     rcx, [rbp+Packet]; Packet
0x14008a6c5  call    NdisFreePacket
0x14008a6ca  test    byte ptr [r12+0Ah], 20h
0x14008a6d0  jz      short loc_14008A6E6
0x14008a6d2  mov     rcx, [r12+18h]; BaseAddress
0x14008a6d7  mov     rdx, r12; MemoryDescriptorList
0x14008a6da  call    cs:__imp_MmUnmapLockedPages
0x14008a6e1  nop     dword ptr [rax+rax+00h]
0x14008a6e6  test    rbx, rbx
0x14008a6e9  jz      short loc_14008A6FF
0x14008a6eb  mov     rdx, r12; Entry
0x14008a6ee  mov     rcx, rbx; Lookaside
0x14008a6f1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008a6f8  nop     dword ptr [rax+rax+00h]
0x14008a6fd  jmp     short loc_14008A710
0x14008a6ff  xor     edx, edx; Tag
0x14008a701  mov     rcx, r12; P
0x14008a704  call    cs:__imp_ExFreePoolWithTag
0x14008a70b  nop     dword ptr [rax+rax+00h]
0x14008a710  mov     r12, [rsp+70h+arg_10]
0x14008a718  mov     rdi, [rsp+70h+arg_8]
0x14008a720  mov     r13, [rsp+70h+arg_18]
0x14008a728  add     rsp, 70h
0x14008a72c  pop     r15
0x14008a72e  pop     r14
0x14008a730  pop     rsi
0x14008a731  pop     rbx
0x14008a732  pop     rbp
0x14008a733  retn
```
