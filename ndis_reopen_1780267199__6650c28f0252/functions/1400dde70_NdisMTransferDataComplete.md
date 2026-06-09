# NdisMTransferDataComplete

- ea: `0x1400dde70`
- end: `0x1400de0ad`
- name: `NdisMTransferDataComplete`
- size: `573`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140029eb0`
- `0x140088a2c`
- `0x1400dde70`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x1400de093`
- `ntoskrnl!KeLowerIrql` at `0x1400de093`
- `ntoskrnl!MmSizeOfMdl` at `0x1400de00d`
- `ntoskrnl!MmSizeOfMdl` at `0x1400de00d`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400ddfe0`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400ddfe0`
- `ntoskrnl!KfRaiseIrql` at `0x1400de056`
- `ntoskrnl!KfRaiseIrql` at `0x1400de056`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ddff7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ddff7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400de01e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400de01e`
- `ntoskrnl!IoFreeMdl` at `0x1400ddefe`
- `ntoskrnl!IoFreeMdl` at `0x1400ddefe`

## pseudocode

```c
void __fastcall NdisMTransferDataComplete(
        struct _NDIS_MINIPORT_BLOCK *a1,
        struct _NDIS_PACKET *a2,
        unsigned int a3,
        unsigned int a4)
{
  PNDIS_PACKET v7; // r10
  unsigned int v8; // ecx
  unsigned __int64 v9; // rcx
  __int64 v10; // rdi
  int v11; // ecx
  _MDL *v12; // rbx
  PNDIS_PACKET v13; // r10
  unsigned int v14; // r9d
  _MDL *Head; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v16; // rdi
  SIZE_T ByteCount; // rsi
  KIRQL v18; // bl
  PNDIS_PACKET Packet; // [rsp+78h] [rbp+40h] BYREF

  Packet = a2;
  MINIPORT_TEST_FLAG(a1, 0x40000u);
  v7 = Packet;
  v8 = *(_DWORD *)Packet[-1].ProtocolReserved;
  if ( v8 >= 3 * ndisPacketStackSize )
  {
    v10 = 0;
  }
  else
  {
    v9 = v8 % 3 + 6 * (v8 / 3 - (unsigned __int64)ndisPacketStackSize);
    v10 = *((_QWORD *)&Packet->Private.PhysicalCount + v9);
    *((_QWORD *)&Packet->Private.PhysicalCount + v9) = 0;
    v7 = Packet;
  }
  v11 = *(_DWORD *)v7[-1].ProtocolReserved;
  if ( v11 || (v7[-1].Reserved[1] & 1) == 0 )
  {
    if ( v10 )
    {
      *(_DWORD *)v7[-1].ProtocolReserved = v11 - 1;
      v18 = 0;
      if ( MINIPORT_TEST_FLAG(a1, 0x40000u) )
        v18 = KfRaiseIrql(2u);
      (*(void (__fastcall **)(_QWORD, PNDIS_PACKET, _QWORD, _QWORD))(v10 + 120))(*(_QWORD *)(v10 + 32), Packet, a3, a4);
      if ( MINIPORT_TEST_FLAG(a1, 0x40000u) && v18 != 2 )
        KeLowerIrql(v18);
    }
  }
  else
  {
    v12 = *(_MDL **)v7->ProtocolReserved;
    IoFreeMdl(v7->Private.Head);
    Packet->Private.Head = v12;
    *(_QWORD *)Packet->ProtocolReserved = 0;
    v13 = Packet;
    v14 = *(_DWORD *)Packet[-1].ProtocolReserved;
    if ( v14 < 3 * ndisPacketStackSize )
    {
      *((_QWORD *)&Packet->Private.PhysicalCount + 6 * (v14 / 3 - (unsigned __int64)ndisPacketStackSize) + v14 % 3) = 0;
      v13 = Packet;
    }
    --*(_DWORD *)v13[-1].ProtocolReserved;
    *(unsigned int *)((char *)&Packet->Private.Count + Packet->Private.NdisPacketOobOffset) = 0;
    *(_DWORD *)((char *)&Packet->Private.Tail + Packet->Private.NdisPacketOobOffset) = 14;
    a1->PacketIndicateHandler(a1, &Packet, 1u);
    if ( !MINIPORT_TEST_FLAG(a1, 0x40000u)
      && *(unsigned int *)((char *)&Packet->Private.Count + Packet->Private.NdisPacketOobOffset) != 259 )
    {
      Head = Packet->Private.Head;
      v16 = *(struct _NPAGED_LOOKASIDE_LIST **)Packet->MiniportReserved;
      ByteCount = Head->ByteCount;
      if ( (Head->MdlFlags & 0x20) != 0 )
        MmUnmapLockedPages(Head->MappedSystemVa, Head);
      if ( v16 )
      {
        ExFreeToNPagedLookasideList(v16, Head);
      }
      else
      {
        MmSizeOfMdl((PVOID)0xFFF, ByteCount);
        ExFreePoolWithTag(Head, 0);
      }
      NdisFreePacket(Packet);
    }
  }
}

```

## disassembly

```asm
0x1400dde70  mov     [rsp-30h+Packet], rdx
0x1400dde75  push    rbp
0x1400dde76  push    rbx
0x1400dde77  push    rsi
0x1400dde78  push    rdi
0x1400dde79  push    r14
0x1400dde7b  push    r15
0x1400dde7d  mov     rbp, rsp
0x1400dde80  sub     rsp, 38h
0x1400dde84  mov     edx, 40000h; unsigned int
0x1400dde89  mov     r14d, r9d
0x1400dde8c  mov     r15d, r8d
0x1400dde8f  mov     rsi, rcx
0x1400dde92  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400dde97  mov     r11d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400dde9e  mov     r10, [rbp+Packet]
0x1400ddea2  lea     eax, [r11+r11*2]
0x1400ddea6  mov     ecx, [r10-8]
0x1400ddeaa  cmp     ecx, eax
0x1400ddeac  jnb     short loc_1400DDEDC
0x1400ddeae  mov     eax, 0AAAAAAABh
0x1400ddeb3  mul     ecx
0x1400ddeb5  shr     edx, 1
0x1400ddeb7  mov     r8d, edx
0x1400ddeba  lea     eax, [rdx+rdx*2]
0x1400ddebd  sub     ecx, eax
0x1400ddebf  sub     r8, r11
0x1400ddec2  lea     rax, [r8+r8*2]
0x1400ddec6  lea     rcx, [rcx+rax*2]
0x1400ddeca  mov     rdi, [r10+rcx*8]
0x1400ddece  mov     qword ptr [r10+rcx*8], 0
0x1400dded6  mov     r10, [rbp+Packet]
0x1400ddeda  jmp     short loc_1400DDEDE
0x1400ddedc  xor     edi, edi
0x1400ddede  mov     ecx, [r10-8]
0x1400ddee2  test    ecx, ecx
0x1400ddee4  jnz     loc_1400DE035
0x1400ddeea  mov     eax, [r10-10h]
0x1400ddeee  test    al, 1
0x1400ddef0  jz      loc_1400DE035
0x1400ddef6  mov     rcx, [r10+8]; Mdl
0x1400ddefa  mov     rbx, [r10+60h]
0x1400ddefe  call    cs:__imp_IoFreeMdl
0x1400ddf05  nop     dword ptr [rax+rax+00h]
0x1400ddf0a  mov     rcx, [rbp+Packet]
0x1400ddf0e  mov     [rcx+8], rbx
0x1400ddf12  mov     rcx, [rbp+Packet]
0x1400ddf16  mov     qword ptr [rcx+60h], 0
0x1400ddf1e  mov     r11d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400ddf25  mov     r10, [rbp+Packet]
0x1400ddf29  lea     ecx, [r11+r11*2]
0x1400ddf2d  mov     r9d, [r10-8]
0x1400ddf31  cmp     r9d, ecx
0x1400ddf34  jnb     short loc_1400DDF60
0x1400ddf36  mov     eax, 0AAAAAAABh
0x1400ddf3b  mul     r9d
0x1400ddf3e  shr     edx, 1
0x1400ddf40  mov     r8d, edx
0x1400ddf43  lea     eax, [rdx+rdx*2]
0x1400ddf46  sub     r9d, eax
0x1400ddf49  sub     r8, r11
0x1400ddf4c  lea     rax, [r8+r8*2]
0x1400ddf50  lea     rcx, [r9+rax*2]
0x1400ddf54  mov     qword ptr [r10+rcx*8], 0
0x1400ddf5c  mov     r10, [rbp+Packet]
0x1400ddf60  dec     dword ptr [r10-8]
0x1400ddf64  lea     rdx, [rbp+Packet]
0x1400ddf68  mov     rcx, [rbp+Packet]
0x1400ddf6c  mov     r8d, 1
0x1400ddf72  movzx   eax, word ptr [rcx+2Ah]
0x1400ddf76  mov     dword ptr [rax+rcx+20h], 0
0x1400ddf7e  mov     rcx, [rbp+Packet]
0x1400ddf82  movzx   eax, word ptr [rcx+2Ah]
0x1400ddf86  mov     dword ptr [rax+rcx+10h], 0Eh
0x1400ddf8e  mov     rcx, rsi
0x1400ddf91  mov     rax, [rsi+1B0h]
0x1400ddf98  call    _guard_dispatch_icall
0x1400ddf9d  mov     edx, 40000h; unsigned int
0x1400ddfa2  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400ddfa5  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400ddfaa  test    al, al
0x1400ddfac  jnz     loc_1400DE09F
0x1400ddfb2  mov     rcx, [rbp+Packet]
0x1400ddfb6  movzx   eax, word ptr [rcx+2Ah]
0x1400ddfba  cmp     dword ptr [rax+rcx+20h], 103h
0x1400ddfc2  jz      loc_1400DE09F
0x1400ddfc8  mov     rbx, [rcx+8]
0x1400ddfcc  mov     rdi, [rcx+30h]
0x1400ddfd0  test    byte ptr [rbx+0Ah], 20h
0x1400ddfd4  mov     esi, [rbx+28h]
0x1400ddfd7  jz      short loc_1400DDFEC
0x1400ddfd9  mov     rcx, [rbx+18h]; BaseAddress
0x1400ddfdd  mov     rdx, rbx; MemoryDescriptorList
0x1400ddfe0  call    cs:__imp_MmUnmapLockedPages
0x1400ddfe7  nop     dword ptr [rax+rax+00h]
0x1400ddfec  test    rdi, rdi
0x1400ddfef  jz      short loc_1400DE005
0x1400ddff1  mov     rdx, rbx; Entry
0x1400ddff4  mov     rcx, rdi; Lookaside
0x1400ddff7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400ddffe  nop     dword ptr [rax+rax+00h]
0x1400de003  jmp     short loc_1400DE02A
0x1400de005  mov     rdx, rsi; Length
0x1400de008  mov     ecx, 0FFFh; Base
0x1400de00d  call    cs:__imp_MmSizeOfMdl
0x1400de014  nop     dword ptr [rax+rax+00h]
0x1400de019  xor     edx, edx; Tag
0x1400de01b  mov     rcx, rbx; P
0x1400de01e  call    cs:__imp_ExFreePoolWithTag
0x1400de025  nop     dword ptr [rax+rax+00h]
0x1400de02a  mov     rcx, [rbp+Packet]; Packet
0x1400de02e  call    NdisFreePacket
0x1400de033  jmp     short loc_1400DE09F
0x1400de035  test    rdi, rdi
0x1400de038  jz      short loc_1400DE09F
0x1400de03a  lea     eax, [rcx-1]
0x1400de03d  mov     edx, 40000h; unsigned int
0x1400de042  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400de045  mov     [r10-8], eax
0x1400de049  xor     bl, bl
0x1400de04b  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400de050  test    al, al
0x1400de052  jz      short loc_1400DE064
0x1400de054  mov     cl, 2; NewIrql
0x1400de056  call    cs:__imp_KfRaiseIrql
0x1400de05d  nop     dword ptr [rax+rax+00h]
0x1400de062  mov     bl, al
0x1400de064  mov     rax, [rdi+78h]
0x1400de068  mov     r9d, r14d
0x1400de06b  mov     rdx, [rbp+Packet]
0x1400de06f  mov     r8d, r15d
0x1400de072  mov     rcx, [rdi+20h]
0x1400de076  call    _guard_dispatch_icall
0x1400de07b  mov     edx, 40000h; unsigned int
0x1400de080  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400de083  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400de088  test    al, al
0x1400de08a  jz      short loc_1400DE09F
0x1400de08c  cmp     bl, 2
0x1400de08f  jz      short loc_1400DE09F
0x1400de091  mov     cl, bl; NewIrql
0x1400de093  call    cs:__imp_KeLowerIrql
0x1400de09a  nop     dword ptr [rax+rax+00h]
0x1400de09f  add     rsp, 38h
0x1400de0a3  pop     r15
0x1400de0a5  pop     r14
0x1400de0a7  pop     rdi
0x1400de0a8  pop     rsi
0x1400de0a9  pop     rbx
0x1400de0aa  pop     rbp
0x1400de0ab  retn
```
