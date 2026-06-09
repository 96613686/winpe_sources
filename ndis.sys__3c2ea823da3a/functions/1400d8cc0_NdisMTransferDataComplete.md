# NdisMTransferDataComplete

- ea: `0x1400d8cc0`
- end: `0x1400d8efd`
- name: `NdisMTransferDataComplete`
- size: `573`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400082b0`
- `0x1400837ac`
- `0x1400d8cc0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400d8ea6`
- `ntoskrnl!KfRaiseIrql` at `0x1400d8ea6`
- `ntoskrnl!KeLowerIrql` at `0x1400d8ee3`
- `ntoskrnl!KeLowerIrql` at `0x1400d8ee3`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8e5d`
- `ntoskrnl!MmSizeOfMdl` at `0x1400d8e5d`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d8e30`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400d8e30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d8e47`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d8e47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d8e6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d8e6e`
- `ntoskrnl!IoFreeMdl` at `0x1400d8d4e`
- `ntoskrnl!IoFreeMdl` at `0x1400d8d4e`

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
0x1400d8cc0  mov     [rsp-30h+Packet], rdx
0x1400d8cc5  push    rbp
0x1400d8cc6  push    rbx
0x1400d8cc7  push    rsi
0x1400d8cc8  push    rdi
0x1400d8cc9  push    r14
0x1400d8ccb  push    r15
0x1400d8ccd  mov     rbp, rsp
0x1400d8cd0  sub     rsp, 38h
0x1400d8cd4  mov     edx, 40000h; unsigned int
0x1400d8cd9  mov     r14d, r9d
0x1400d8cdc  mov     r15d, r8d
0x1400d8cdf  mov     rsi, rcx
0x1400d8ce2  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400d8ce7  mov     r11d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400d8cee  mov     r10, [rbp+Packet]
0x1400d8cf2  lea     eax, [r11+r11*2]
0x1400d8cf6  mov     ecx, [r10-8]
0x1400d8cfa  cmp     ecx, eax
0x1400d8cfc  jnb     short loc_1400D8D2C
0x1400d8cfe  mov     eax, 0AAAAAAABh
0x1400d8d03  mul     ecx
0x1400d8d05  shr     edx, 1
0x1400d8d07  mov     r8d, edx
0x1400d8d0a  lea     eax, [rdx+rdx*2]
0x1400d8d0d  sub     ecx, eax
0x1400d8d0f  sub     r8, r11
0x1400d8d12  lea     rax, [r8+r8*2]
0x1400d8d16  lea     rcx, [rcx+rax*2]
0x1400d8d1a  mov     rdi, [r10+rcx*8]
0x1400d8d1e  mov     qword ptr [r10+rcx*8], 0
0x1400d8d26  mov     r10, [rbp+Packet]
0x1400d8d2a  jmp     short loc_1400D8D2E
0x1400d8d2c  xor     edi, edi
0x1400d8d2e  mov     ecx, [r10-8]
0x1400d8d32  test    ecx, ecx
0x1400d8d34  jnz     loc_1400D8E85
0x1400d8d3a  mov     eax, [r10-10h]
0x1400d8d3e  test    al, 1
0x1400d8d40  jz      loc_1400D8E85
0x1400d8d46  mov     rcx, [r10+8]; Mdl
0x1400d8d4a  mov     rbx, [r10+60h]
0x1400d8d4e  call    cs:__imp_IoFreeMdl
0x1400d8d55  nop     dword ptr [rax+rax+00h]
0x1400d8d5a  mov     rcx, [rbp+Packet]
0x1400d8d5e  mov     [rcx+8], rbx
0x1400d8d62  mov     rcx, [rbp+Packet]
0x1400d8d66  mov     qword ptr [rcx+60h], 0
0x1400d8d6e  mov     r11d, cs:?ndisPacketStackSize@@3IA; uint ndisPacketStackSize
0x1400d8d75  mov     r10, [rbp+Packet]
0x1400d8d79  lea     ecx, [r11+r11*2]
0x1400d8d7d  mov     r9d, [r10-8]
0x1400d8d81  cmp     r9d, ecx
0x1400d8d84  jnb     short loc_1400D8DB0
0x1400d8d86  mov     eax, 0AAAAAAABh
0x1400d8d8b  mul     r9d
0x1400d8d8e  shr     edx, 1
0x1400d8d90  mov     r8d, edx
0x1400d8d93  lea     eax, [rdx+rdx*2]
0x1400d8d96  sub     r9d, eax
0x1400d8d99  sub     r8, r11
0x1400d8d9c  lea     rax, [r8+r8*2]
0x1400d8da0  lea     rcx, [r9+rax*2]
0x1400d8da4  mov     qword ptr [r10+rcx*8], 0
0x1400d8dac  mov     r10, [rbp+Packet]
0x1400d8db0  dec     dword ptr [r10-8]
0x1400d8db4  lea     rdx, [rbp+Packet]
0x1400d8db8  mov     rcx, [rbp+Packet]
0x1400d8dbc  mov     r8d, 1
0x1400d8dc2  movzx   eax, word ptr [rcx+2Ah]
0x1400d8dc6  mov     dword ptr [rax+rcx+20h], 0
0x1400d8dce  mov     rcx, [rbp+Packet]
0x1400d8dd2  movzx   eax, word ptr [rcx+2Ah]
0x1400d8dd6  mov     dword ptr [rax+rcx+10h], 0Eh
0x1400d8dde  mov     rcx, rsi
0x1400d8de1  mov     rax, [rsi+1B0h]
0x1400d8de8  call    _guard_dispatch_icall
0x1400d8ded  mov     edx, 40000h; unsigned int
0x1400d8df2  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400d8df5  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400d8dfa  test    al, al
0x1400d8dfc  jnz     loc_1400D8EEF
0x1400d8e02  mov     rcx, [rbp+Packet]
0x1400d8e06  movzx   eax, word ptr [rcx+2Ah]
0x1400d8e0a  cmp     dword ptr [rax+rcx+20h], 103h
0x1400d8e12  jz      loc_1400D8EEF
0x1400d8e18  mov     rbx, [rcx+8]
0x1400d8e1c  mov     rdi, [rcx+30h]
0x1400d8e20  test    byte ptr [rbx+0Ah], 20h
0x1400d8e24  mov     esi, [rbx+28h]
0x1400d8e27  jz      short loc_1400D8E3C
0x1400d8e29  mov     rcx, [rbx+18h]; BaseAddress
0x1400d8e2d  mov     rdx, rbx; MemoryDescriptorList
0x1400d8e30  call    cs:__imp_MmUnmapLockedPages
0x1400d8e37  nop     dword ptr [rax+rax+00h]
0x1400d8e3c  test    rdi, rdi
0x1400d8e3f  jz      short loc_1400D8E55
0x1400d8e41  mov     rdx, rbx; Entry
0x1400d8e44  mov     rcx, rdi; Lookaside
0x1400d8e47  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d8e4e  nop     dword ptr [rax+rax+00h]
0x1400d8e53  jmp     short loc_1400D8E7A
0x1400d8e55  mov     rdx, rsi; Length
0x1400d8e58  mov     ecx, 0FFFh; Base
0x1400d8e5d  call    cs:__imp_MmSizeOfMdl
0x1400d8e64  nop     dword ptr [rax+rax+00h]
0x1400d8e69  xor     edx, edx; Tag
0x1400d8e6b  mov     rcx, rbx; P
0x1400d8e6e  call    cs:__imp_ExFreePoolWithTag
0x1400d8e75  nop     dword ptr [rax+rax+00h]
0x1400d8e7a  mov     rcx, [rbp+Packet]; Packet
0x1400d8e7e  call    NdisFreePacket
0x1400d8e83  jmp     short loc_1400D8EEF
0x1400d8e85  test    rdi, rdi
0x1400d8e88  jz      short loc_1400D8EEF
0x1400d8e8a  lea     eax, [rcx-1]
0x1400d8e8d  mov     edx, 40000h; unsigned int
0x1400d8e92  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400d8e95  mov     [r10-8], eax
0x1400d8e99  xor     bl, bl
0x1400d8e9b  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400d8ea0  test    al, al
0x1400d8ea2  jz      short loc_1400D8EB4
0x1400d8ea4  mov     cl, 2; NewIrql
0x1400d8ea6  call    cs:__imp_KfRaiseIrql
0x1400d8ead  nop     dword ptr [rax+rax+00h]
0x1400d8eb2  mov     bl, al
0x1400d8eb4  mov     rax, [rdi+78h]
0x1400d8eb8  mov     r9d, r14d
0x1400d8ebb  mov     rdx, [rbp+Packet]
0x1400d8ebf  mov     r8d, r15d
0x1400d8ec2  mov     rcx, [rdi+20h]
0x1400d8ec6  call    _guard_dispatch_icall
0x1400d8ecb  mov     edx, 40000h; unsigned int
0x1400d8ed0  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400d8ed3  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400d8ed8  test    al, al
0x1400d8eda  jz      short loc_1400D8EEF
0x1400d8edc  cmp     bl, 2
0x1400d8edf  jz      short loc_1400D8EEF
0x1400d8ee1  mov     cl, bl; NewIrql
0x1400d8ee3  call    cs:__imp_KeLowerIrql
0x1400d8eea  nop     dword ptr [rax+rax+00h]
0x1400d8eef  add     rsp, 38h
0x1400d8ef3  pop     r15
0x1400d8ef5  pop     r14
0x1400d8ef7  pop     rdi
0x1400d8ef8  pop     rsi
0x1400d8ef9  pop     rbx
0x1400d8efa  pop     rbp
0x1400d8efb  retn
```
