# Dot11PacketConverterReturnPacket

- ea: `0x140016e00`
- end: `0x140016ecc`
- name: `Dot11PacketConverterReturnPacket`
- size: `204`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferList)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400127ac`
- `0x1400130b8`

## callees

- `0x140016e00`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016e9e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016e9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016eaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016eaf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016e43`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140016e43`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140016e80`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140016e80`

## pseudocode

```c
void __fastcall Dot11PacketConverterReturnPacket(PNET_BUFFER_LIST NetBufferList, __int64 a2, __int64 a3)
{
  ULONG v4; // ebp
  __int64 v7; // rcx
  _DWORD *v8; // rax

  v4 = *(_DWORD *)(a3 + 16);
  v7 = *(_QWORD *)(NetBufferList->Link.Region + 32);
  if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
    v8 = *(_DWORD **)(v7 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000000u);
  *(_QWORD *)v8 = *(_QWORD *)a3;
  v8[2] = *(_DWORD *)(a3 + 8);
  *((_WORD *)v8 + 6) = *(_WORD *)(a3 + 12);
  NdisRetreatNetBufferListDataStart(NetBufferList, v4, 0, Dot11AllocateRecvMdlAndMemForNdis6, ManufacturingShutdown);
  if ( *(_QWORD *)(a3 - 16) )
    ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a3 - 16), (PVOID)(a3 - 16));
  else
    ExFreePoolWithTag((PVOID)(a3 - 16), *(_DWORD *)(a3 - 16 + 8));
  _InterlockedDecrement((volatile signed __int32 *)(a2 + 4960));
}

```

## disassembly

```asm
0x140016e00  push    rbx
0x140016e02  push    rbp
0x140016e03  push    rsi
0x140016e04  push    rdi
0x140016e05  sub     rsp, 38h
0x140016e09  mov     rax, [rcx+8]
0x140016e0d  mov     rsi, rcx
0x140016e10  mov     ebp, [r8+10h]
0x140016e14  mov     rdi, r8
0x140016e17  mov     rbx, rdx
0x140016e1a  mov     rcx, [rax+20h]; MemoryDescriptorList
0x140016e1e  test    byte ptr [rcx+0Ah], 5
0x140016e22  jz      short loc_140016E2A
0x140016e24  mov     rax, [rcx+18h]
0x140016e28  jmp     short loc_140016E4F
0x140016e2a  xor     r9d, r9d; RequestedAddress
0x140016e2d  mov     [rsp+58h+Priority], 40000000h; Priority
0x140016e35  xor     edx, edx; AccessMode
0x140016e37  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140016e3f  lea     r8d, [r9+1]; CacheType
0x140016e43  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140016e4a  nop     dword ptr [rax+rax+00h]
0x140016e4f  movsd   xmm0, qword ptr [rdi]
0x140016e53  lea     r9, ?Dot11AllocateRecvMdlAndMemForNdis6@@YAPEAU_MDL@@PEAK@Z; AllocateMdlHandler
0x140016e5a  movsd   qword ptr [rax], xmm0
0x140016e5e  xor     r8d, r8d; DataBackFill
0x140016e61  mov     ecx, [rdi+8]
0x140016e64  mov     edx, ebp; DataOffsetDelta
0x140016e66  mov     [rax+8], ecx
0x140016e69  movzx   ecx, word ptr [rdi+0Ch]
0x140016e6d  mov     [rax+0Ch], cx
0x140016e71  lea     rax, ?ManufacturingShutdown@@YAXPEAUMANUFACTURING_VELAN@@@Z; ManufacturingShutdown(MANUFACTURING_VELAN *)
0x140016e78  mov     rcx, rsi; NetBufferList
0x140016e7b  mov     qword ptr [rsp+58h+BugCheckOnFailure], rax; FreeMdlHandler
0x140016e80  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140016e87  nop     dword ptr [rax+rax+00h]
0x140016e8c  lea     rcx, [rdi-10h]; P
0x140016e90  mov     rax, [rcx]
0x140016e93  test    rax, rax
0x140016e96  jz      short loc_140016EAC
0x140016e98  mov     rdx, rcx; Entry
0x140016e9b  mov     rcx, rax; Lookaside
0x140016e9e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140016ea5  nop     dword ptr [rax+rax+00h]
0x140016eaa  jmp     short loc_140016EBB
0x140016eac  mov     edx, [rcx+8]; Tag
0x140016eaf  call    cs:__imp_ExFreePoolWithTag
0x140016eb6  nop     dword ptr [rax+rax+00h]
0x140016ebb  lock dec dword ptr [rbx+1360h]
0x140016ec2  add     rsp, 38h
0x140016ec6  pop     rdi
0x140016ec7  pop     rsi
0x140016ec8  pop     rbp
0x140016ec9  pop     rbx
0x140016eca  retn
```
