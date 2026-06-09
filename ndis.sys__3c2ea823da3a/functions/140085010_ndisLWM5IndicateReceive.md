# ndisLWM5IndicateReceive

- ea: `0x140085010`
- end: `0x1400854c0`
- name: `ndisLWM5IndicateReceive`
- size: `1200`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006a480`

## callees

- `0x140007d80`
- `0x1400082b0`
- `0x140064c90`
- `0x1400837ac`
- `0x140085010`
- `0x1400e6240`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400850cc`
- `ntoskrnl!MmSizeOfMdl` at `0x140085118`
- `ntoskrnl!MmSizeOfMdl` at `0x1400850cc`
- `ntoskrnl!MmSizeOfMdl` at `0x140085118`
- `ntoskrnl!MmMapLockedPages` at `0x14008525b`
- `ntoskrnl!MmMapLockedPages` at `0x14008525b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14008518a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14008518a`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008545a`
- `ntoskrnl!MmUnmapLockedPages` at `0x14008545a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085471`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140085471`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400850a6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400850a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085484`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085484`
- `ntoskrnl!ExAllocatePool2` at `0x1400850f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400850f9`
- `ntoskrnl!IoFreeMdl` at `0x14008534c`
- `ntoskrnl!IoFreeMdl` at `0x14008534c`

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
0x140085010  test    rcx, rcx
0x140085013  jz      locret_1400854B3
0x140085019  push    rbp
0x14008501a  push    rbx
0x14008501b  push    rsi
0x14008501c  push    r14
0x14008501e  push    r15
0x140085020  mov     rbp, rsp
0x140085023  sub     rsp, 70h
0x140085027  xor     ebx, ebx
0x140085029  mov     [rsp+70h+arg_18], r13
0x140085031  mov     r13, [rcx+128h]
0x140085038  mov     r15, rdx
0x14008503b  mov     r10, rcx
0x14008503e  mov     esi, r9d
0x140085041  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x140085044  mov     [rbp+Status], ebx
0x140085047  mov     edx, 20000000h; unsigned int
0x14008504c  mov     [rbp+Packet], rbx
0x140085050  mov     r14, r8
0x140085053  mov     [rbp+var_8], r13
0x140085057  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14008505c  test    al, al
0x14008505e  jz      loc_1400854A0
0x140085064  mov     rcx, [r10+128h]; struct _NDIS_MINIPORT_BLOCK *
0x14008506b  mov     edx, 40000h; unsigned int
0x140085070  mov     [rsp+70h+arg_8], rdi
0x140085078  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14008507d  mov     eax, dword ptr [rbp+Size]
0x140085080  lea     edi, [rsi+rax]
0x140085083  cmp     edi, eax
0x140085085  jb      loc_140085498
0x14008508b  mov     [rsp+70h+arg_10], r12
0x140085093  cmp     edi, 64h ; 'd'
0x140085096  jnb     short loc_1400850B4
0x140085098  lea     rbx, ?ndisRcv100BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST ndisRcv100BytesLL
0x14008509f  mov     rcx, rbx; Lookaside
0x1400850a2  mov     [rbp+Lookaside], rbx
0x1400850a6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400850ad  nop     dword ptr [rax+rax+00h]
0x1400850b2  jmp     short loc_140085105
0x1400850b4  cmp     edi, 5EAh
0x1400850ba  jnb     short loc_1400850C5
0x1400850bc  lea     rbx, ?ndisRcv1514BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; _NPAGED_LOOKASIDE_LIST ndisRcv1514BytesLL
0x1400850c3  jmp     short loc_14008509F
0x1400850c5  mov     edx, edi; Length
0x1400850c7  mov     ecx, 0FFFh; Base
0x1400850cc  call    cs:__imp_MmSizeOfMdl
0x1400850d3  nop     dword ptr [rax+rax+00h]
0x1400850d8  lea     ecx, [rax+7]
0x1400850db  and     ecx, 0FFFFFFF8h
0x1400850de  add     ecx, edi
0x1400850e0  cmp     ecx, edi
0x1400850e2  jb      loc_140085490
0x1400850e8  mov     edx, ecx
0x1400850ea  mov     r8d, 7254444Eh
0x1400850f0  mov     ecx, 42h ; 'B'
0x1400850f5  mov     [rbp+Lookaside], rbx
0x1400850f9  call    cs:__imp_ExAllocatePool2
0x140085100  nop     dword ptr [rax+rax+00h]
0x140085105  mov     r12, rax
0x140085108  test    rax, rax
0x14008510b  jz      loc_140085490
0x140085111  mov     edx, edi; Length
0x140085113  mov     ecx, 0FFFh; Base
0x140085118  call    cs:__imp_MmSizeOfMdl
0x14008511f  nop     dword ptr [rax+rax+00h]
0x140085124  lea     rcx, [rdi+0FFFh]
0x14008512b  mov     qword ptr [r12], 0
0x140085133  mov     [r12+28h], edi
0x140085138  lea     r8, [rax+7]
0x14008513c  and     r8, 0FFFFFFFFFFFFFFF8h
0x140085140  add     r8, r12
0x140085143  mov     edx, r8d
0x140085146  mov     [rbp+Buffer], r8
0x14008514a  mov     eax, edx
0x14008514c  and     edx, 0FFFh
0x140085152  and     eax, 0FFFh
0x140085157  mov     [r12+2Ch], edx
0x14008515c  add     rcx, rax
0x14008515f  xor     eax, eax
0x140085161  shr     rcx, 0Ch
0x140085165  add     cx, 6
0x140085169  mov     [r12+0Ah], ax
0x14008516f  shl     cx, 3
0x140085173  mov     rax, r8
0x140085176  mov     [r12+8], cx
0x14008517c  and     rax, 0FFFFFFFFFFFFF000h
0x140085182  mov     rcx, r12; MemoryDescriptorList
0x140085185  mov     [r12+20h], rax
0x14008518a  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140085191  nop     dword ptr [rax+rax+00h]
0x140085196  mov     r8, cs:?ndisRecvPacketPool@@3PEAU_NDIS_PKT_POOL@@EA; PoolHandle
0x14008519d  lea     rdx, [rbp+Packet]; Packet
0x1400851a1  lea     rcx, [rbp+Status]; Status
0x1400851a5  call    NdisAllocatePacket
0x1400851aa  mov     edi, [rbp+Status]
0x1400851ad  test    edi, edi
0x1400851af  jnz     loc_140085428
0x1400851b5  mov     rax, [rbp+Packet]
0x1400851b9  mov     rbx, [rbp+Lookaside]
0x1400851bd  mov     [rbp+Status], edi
0x1400851c0  mov     edi, dword ptr [rbp+Size]
0x1400851c3  mov     [rax+8], r12
0x1400851c7  mov     rax, [rbp+Packet]
0x1400851cb  mov     [rax+10h], r12
0x1400851cf  mov     rax, [rbp+Packet]
0x1400851d3  mov     [rax+30h], rbx
0x1400851d7  mov     rax, [rbp+Packet]
0x1400851db  or      dword ptr [rax-10h], 1
0x1400851df  cmp     edi, [rbp+arg_28]
0x1400851e2  ja      short loc_14008520E
0x1400851e4  mov     r8, rsi; Size
0x1400851e7  mov     rbx, rsi
0x1400851ea  mov     rsi, [rbp+Buffer]
0x1400851ee  mov     rdx, r14; Src
0x1400851f1  mov     rcx, rsi; void *
0x1400851f4  call    memmove
0x1400851f9  mov     rdx, [rbp+Src]; Src
0x1400851fd  lea     rcx, [rbx+rsi]; void *
0x140085201  mov     r8d, edi; Size
0x140085204  call    memmove
0x140085209  jmp     loc_1400853B6
0x14008520e  mov     rax, [rbp+Packet]
0x140085212  mov     [rbp+var_30], 0
0x140085219  mov     [rbp+Buffer], 0
0x140085221  inc     dword ptr [rax-8]
0x140085224  mov     eax, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x14008522a  mov     r13, [rbp+Packet]
0x14008522e  lea     ecx, [rax+rax*2]
0x140085231  mov     edx, [r13-8]
0x140085235  cmp     edx, ecx
0x140085237  jb      short loc_140085245
0x140085239  lea     eax, [rdx-1]
0x14008523c  mov     [r13-8], eax
0x140085240  jmp     loc_140085434
0x140085245  mov     r13, [r13+8]
0x140085249  test    byte ptr [r13+0Ah], 5
0x14008524e  jz      short loc_140085256
0x140085250  mov     rax, [r13+18h]
0x140085254  jmp     short loc_140085267
0x140085256  xor     edx, edx; AccessMode
0x140085258  mov     rcx, r13; MemoryDescriptorList
0x14008525b  call    cs:__imp_MmMapLockedPages
0x140085262  nop     dword ptr [rax+rax+00h]
0x140085267  mov     edi, [r13+28h]
0x14008526b  mov     r8, rsi; Size
0x14008526e  mov     rdx, r14; Src
0x140085271  mov     [rbp+var_18], rax
0x140085275  mov     rcx, rax; void *
0x140085278  call    memmove
0x14008527d  mov     r9, [rbp+var_18]
0x140085281  lea     rdx, [rbp+Buffer]; Buffer
0x140085285  sub     edi, esi
0x140085287  lea     rcx, [rbp+Status]; Status
0x14008528b  add     r9, rsi; VirtualAddress
0x14008528e  mov     [rsp+70h+Length], edi; Length
0x140085292  xor     r8d, r8d; PoolHandle
0x140085295  call    NdisAllocateBuffer
0x14008529a  mov     edi, [rbp+Status]
0x14008529d  test    edi, edi
0x14008529f  jnz     loc_140085428
0x1400852a5  mov     rax, [r13+0]
0x1400852a9  mov     rcx, [rbp+Buffer]
0x1400852ad  mov     [rcx], rax
0x1400852b0  mov     rax, [rbp+Packet]
0x1400852b4  mov     [rax+8], rcx
0x1400852b8  mov     rax, [rbp+Packet]
0x1400852bc  mov     [rax+60h], r13
0x1400852c0  mov     r9d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400852c7  mov     r10, [rbp+Packet]
0x1400852cb  lea     eax, [r9+r9*2]
0x1400852cf  mov     ecx, [r10-8]
0x1400852d3  cmp     ecx, eax
0x1400852d5  jnb     short loc_1400852FF
0x1400852d7  mov     eax, 0AAAAAAABh
0x1400852dc  mul     ecx
0x1400852de  shr     edx, 1
0x1400852e0  mov     r8d, edx
0x1400852e3  lea     eax, [rdx+rdx*2]
0x1400852e6  sub     ecx, eax
0x1400852e8  sub     r8, r9
0x1400852eb  lea     rax, [r8+r8*2]
0x1400852ef  lea     rcx, [rcx+rax*2]
0x1400852f3  mov     qword ptr [r10+rcx*8], 0
0x1400852fb  mov     r10, [rbp+Packet]
0x1400852ff  mov     r13, [rbp+var_8]
0x140085303  mov     r9, r15
0x140085306  mov     edx, dword ptr [rbp+Size]
0x140085309  mov     rcx, r10
0x14008530c  mov     [rsp+70h+var_48], edx
0x140085310  lea     rdx, [rbp+var_30]
0x140085314  mov     [rsp+70h+Length], 0
0x14008531c  mov     rax, [r13+0EB0h]
0x140085323  mov     r8, [r13+18h]
0x140085327  mov     rax, [rax+0D8h]
0x14008532e  call    _guard_dispatch_icall
0x140085333  mov     edi, eax
0x140085335  cmp     eax, 103h
0x14008533a  jz      loc_140085428
0x140085340  mov     rcx, [rbp+Packet]
0x140085344  mov     rbx, [rcx+60h]
0x140085348  mov     rcx, [rcx+8]; Mdl
0x14008534c  call    cs:__imp_IoFreeMdl
0x140085353  nop     dword ptr [rax+rax+00h]
0x140085358  mov     rcx, [rbp+Packet]
0x14008535c  mov     [rcx+8], rbx
0x140085360  mov     rcx, [rbp+Packet]
0x140085364  mov     qword ptr [rcx+60h], 0
0x14008536c  mov     r11d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x140085373  mov     r9, [rbp+Packet]
0x140085377  lea     ecx, [r11+r11*2]
0x14008537b  mov     r10d, [r9-8]
0x14008537f  cmp     r10d, ecx
0x140085382  jnb     short loc_1400853AE
0x140085384  mov     eax, 0AAAAAAABh
0x140085389  mul     r10d
0x14008538c  shr     edx, 1
0x14008538e  mov     r8d, edx
0x140085391  lea     eax, [rdx+rdx*2]
0x140085394  sub     r10d, eax
0x140085397  sub     r8, r11
0x14008539a  lea     rax, [r8+r8*2]
0x14008539e  lea     rcx, [r10+rax*2]
0x1400853a2  mov     qword ptr [r9+rcx*8], 0
0x1400853aa  mov     r9, [rbp+Packet]
0x1400853ae  dec     dword ptr [r9-8]
0x1400853b2  test    edi, edi
0x1400853b4  jnz     short loc_140085428
0x1400853b6  mov     rcx, [rbp+Packet]
0x1400853ba  movzx   eax, word ptr [rcx+2Ah]
0x1400853be  mov     dword ptr [rax+rcx+20h], 0
0x1400853c6  cmp     dword ptr [r13+1D0h], 0
0x1400853ce  jnz     short loc_1400853E2
0x1400853d0  mov     r8, [rbp+Packet]
0x1400853d4  movzx   eax, word ptr [r8+2Ah]
0x1400853d9  mov     dword ptr [rax+r8+10h], 0Eh
0x1400853e2  mov     rax, [r13+1B0h]
0x1400853e9  lea     rdx, [rbp+Packet]
0x1400853ed  mov     r8d, 1
0x1400853f3  mov     rcx, r13
0x1400853f6  call    _guard_dispatch_icall
0x1400853fb  mov     edx, 40000h; unsigned int
0x140085400  mov     rcx, r13; struct _NDIS_MINIPORT_BLOCK *
0x140085403  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140085408  test    al, al
0x14008540a  jnz     loc_140085490
0x140085410  mov     rcx, [rbp+Packet]
0x140085414  movzx   eax, word ptr [rcx+2Ah]
0x140085418  cmp     dword ptr [rax+rcx+20h], 103h
0x140085420  jz      short loc_140085490
0x140085422  mov     rbx, [rbp+Lookaside]
0x140085426  jmp     short loc_140085438
0x140085428  cmp     edi, 103h
0x14008542e  jz      short loc_140085490
0x140085430  mov     rbx, [rbp+Lookaside]
0x140085434  mov     rcx, [rbp+Packet]
0x140085438  test    rcx, rcx
0x14008543b  jz      short loc_14008544A
0x14008543d  and     dword ptr [rcx-10h], 0FFFFFFFEh
0x140085441  mov     rcx, [rbp+Packet]; Packet
0x140085445  call    NdisFreePacket
0x14008544a  test    byte ptr [r12+0Ah], 20h
0x140085450  jz      short loc_140085466
0x140085452  mov     rcx, [r12+18h]; BaseAddress
0x140085457  mov     rdx, r12; MemoryDescriptorList
0x14008545a  call    cs:__imp_MmUnmapLockedPages
0x140085461  nop     dword ptr [rax+rax+00h]
0x140085466  test    rbx, rbx
0x140085469  jz      short loc_14008547F
0x14008546b  mov     rdx, r12; Entry
0x14008546e  mov     rcx, rbx; Lookaside
0x140085471  call    cs:__imp_ExFreeToNPagedLookasideList
0x140085478  nop     dword ptr [rax+rax+00h]
0x14008547d  jmp     short loc_140085490
0x14008547f  xor     edx, edx; Tag
0x140085481  mov     rcx, r12; P
0x140085484  call    cs:__imp_ExFreePoolWithTag
0x14008548b  nop     dword ptr [rax+rax+00h]
0x140085490  mov     r12, [rsp+70h+arg_10]
0x140085498  mov     rdi, [rsp+70h+arg_8]
0x1400854a0  mov     r13, [rsp+70h+arg_18]
0x1400854a8  add     rsp, 70h
0x1400854ac  pop     r15
0x1400854ae  pop     r14
0x1400854b0  pop     rsi
0x1400854b1  pop     rbx
0x1400854b2  pop     rbp
0x1400854b3  retn
```
