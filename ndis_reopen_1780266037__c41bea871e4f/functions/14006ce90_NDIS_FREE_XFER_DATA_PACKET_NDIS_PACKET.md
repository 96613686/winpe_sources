# NDIS_FREE_XFER_DATA_PACKET(_NDIS_PACKET *)

- ea: `0x14006ce90`
- end: `0x14006cf43`
- name: `?NDIS_FREE_XFER_DATA_PACKET@@YAXPEAU_NDIS_PACKET@@@Z`
- size: `179`
- prototype: `void __fastcall(PNDIS_PACKET Packet)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140039140`
- `0x140066a00`
- `0x1400888d0`
- `0x14009da50`
- `0x1400b4970`
- `0x1400b4ae0`
- `0x1400d8d70`
- `0x1400d9050`
- `0x1400d9290`

## callees

- `0x140029eb0`
- `0x14006ce90`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14006cf24`
- `ntoskrnl!MmSizeOfMdl` at `0x14006cf24`
- `ntoskrnl!MmUnmapLockedPages` at `0x14006cf0e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14006cf0e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006cebe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006cef9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006cebe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006cef9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cf35`

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
0x14006ce90  mov     [rsp+arg_0], rbx
0x14006ce95  mov     [rsp+arg_8], rsi
0x14006ce9a  push    rdi
0x14006ce9b  sub     rsp, 20h
0x14006ce9f  mov     rdi, [rcx+8]
0x14006cea3  mov     rbx, rcx
0x14006cea6  test    byte ptr [rdi+0Ah], 20h
0x14006ceaa  mov     esi, [rdi+28h]
0x14006cead  jnz     short loc_14006CF07
0x14006ceaf  cmp     esi, 64h ; 'd'
0x14006ceb2  jnb     short loc_14006CEE7
0x14006ceb4  mov     rdx, rdi; Entry
0x14006ceb7  lea     rcx, ?ndisRcv100BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14006cebe  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006cec5  nop     dword ptr [rax+rax+00h]
0x14006ceca  and     dword ptr [rbx-10h], 0FFFFFFFEh
0x14006cece  mov     rcx, rbx; Packet
0x14006ced1  call    NdisFreePacket
0x14006ced6  mov     rbx, [rsp+28h+arg_0]
0x14006cedb  mov     rsi, [rsp+28h+arg_8]
0x14006cee0  add     rsp, 20h
0x14006cee4  pop     rdi
0x14006cee5  retn
0x14006cee7  cmp     esi, 5EAh
0x14006ceed  jnb     short loc_14006CF1C
0x14006ceef  mov     rdx, rdi; Entry
0x14006cef2  lea     rcx, ?ndisRcv1514BytesLL@@3U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14006cef9  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006cf00  nop     dword ptr [rax+rax+00h]
0x14006cf05  jmp     short loc_14006CECA
0x14006cf07  mov     rcx, [rdi+18h]; BaseAddress
0x14006cf0b  mov     rdx, rdi; MemoryDescriptorList
0x14006cf0e  call    cs:__imp_MmUnmapLockedPages
0x14006cf15  nop     dword ptr [rax+rax+00h]
0x14006cf1a  jmp     short loc_14006CEAF
0x14006cf1c  mov     rdx, rsi; Length
0x14006cf1f  mov     ecx, 0FFFh; Base
0x14006cf24  call    cs:__imp_MmSizeOfMdl
0x14006cf2b  nop     dword ptr [rax+rax+00h]
0x14006cf30  xor     edx, edx; Tag
0x14006cf32  mov     rcx, rdi; P
0x14006cf35  call    cs:__imp_ExFreePoolWithTag
0x14006cf3c  nop     dword ptr [rax+rax+00h]
0x14006cf41  jmp     short loc_14006CECA
```
