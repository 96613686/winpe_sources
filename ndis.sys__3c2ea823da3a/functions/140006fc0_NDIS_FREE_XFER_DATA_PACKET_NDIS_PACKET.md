# NDIS_FREE_XFER_DATA_PACKET(_NDIS_PACKET *)

- ea: `0x140006fc0`
- end: `0x140007073`
- name: `?NDIS_FREE_XFER_DATA_PACKET@@YAXPEAU_NDIS_PACKET@@@Z`
- size: `179`
- prototype: `void __fastcall(PNDIS_PACKET Packet)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140003ba0`
- `0x1400555b0`
- `0x140083650`
- `0x1400987d0`
- `0x1400af540`
- `0x1400af6b0`
- `0x1400d3bc0`
- `0x1400d3ea0`
- `0x1400d40e0`

## callees

- `0x140006fc0`
- `0x1400082b0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140007054`
- `ntoskrnl!MmSizeOfMdl` at `0x140007054`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000703e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000703e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006fee`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007029`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006fee`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007029`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007065`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007065`

## pseudocode

```c
void __fastcall NDIS_FREE_XFER_DATA_PACKET(PNDIS_PACKET Packet)
{
  _MDL *Head; // rdi
  SIZE_T ByteCount; // rsi

  Head = Packet->Private.Head;
  ByteCount = Head->ByteCount;
  if ( (Head->MdlFlags & 0x20) != 0 )
    MmUnmapLockedPages(Head->MappedSystemVa, Head);
  if ( (unsigned int)ByteCount >= 0x64 )
  {
    if ( (unsigned int)ByteCount >= 0x5EA )
    {
      MmSizeOfMdl((PVOID)0xFFF, ByteCount);
      ExFreePoolWithTag(Head, 0);
    }
    else
    {
      ExFreeToNPagedLookasideList(&ndisRcv1514BytesLL, Head);
    }
  }
  else
  {
    ExFreeToNPagedLookasideList(&ndisRcv100BytesLL, Head);
  }
  LODWORD(Packet[-1].Reserved[1]) &= ~1u;
  NdisFreePacket(Packet);
}

```

## disassembly

```asm
0x140006fc0  mov     [rsp+arg_0], rbx
0x140006fc5  mov     [rsp+arg_8], rsi
0x140006fca  push    rdi
0x140006fcb  sub     rsp, 20h
0x140006fcf  mov     rdi, [rcx+8]
0x140006fd3  mov     rbx, rcx
0x140006fd6  test    byte ptr [rdi+0Ah], 20h
0x140006fda  mov     esi, [rdi+28h]
0x140006fdd  jnz     short loc_140007037
0x140006fdf  cmp     esi, 64h ; 'd'
0x140006fe2  jnb     short loc_140007017
0x140006fe4  mov     rdx, rdi; Entry
0x140006fe7  lea     rcx, ?ndisRcv100BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140006fee  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006ff5  nop     dword ptr [rax+rax+00h]
0x140006ffa  and     dword ptr [rbx-10h], 0FFFFFFFEh
0x140006ffe  mov     rcx, rbx; Packet
0x140007001  call    NdisFreePacket
0x140007006  mov     rbx, [rsp+28h+arg_0]
0x14000700b  mov     rsi, [rsp+28h+arg_8]
0x140007010  add     rsp, 20h
0x140007014  pop     rdi
0x140007015  retn
0x140007017  cmp     esi, 5EAh
0x14000701d  jnb     short loc_14000704C
0x14000701f  mov     rdx, rdi; Entry
0x140007022  lea     rcx, ?ndisRcv1514BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140007029  call    cs:__imp_ExFreeToNPagedLookasideList
0x140007030  nop     dword ptr [rax+rax+00h]
0x140007035  jmp     short loc_140006FFA
0x140007037  mov     rcx, [rdi+18h]; BaseAddress
0x14000703b  mov     rdx, rdi; MemoryDescriptorList
0x14000703e  call    cs:__imp_MmUnmapLockedPages
0x140007045  nop     dword ptr [rax+rax+00h]
0x14000704a  jmp     short loc_140006FDF
0x14000704c  mov     rdx, rsi; Length
0x14000704f  mov     ecx, 0FFFh; Base
0x140007054  call    cs:__imp_MmSizeOfMdl
0x14000705b  nop     dword ptr [rax+rax+00h]
0x140007060  xor     edx, edx; Tag
0x140007062  mov     rcx, rdi; P
0x140007065  call    cs:__imp_ExFreePoolWithTag
0x14000706c  nop     dword ptr [rax+rax+00h]
0x140007071  jmp     short loc_140006FFA
```
