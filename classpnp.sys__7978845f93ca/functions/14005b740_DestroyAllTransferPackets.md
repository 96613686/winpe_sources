# DestroyAllTransferPackets

- ea: `0x14005b740`
- end: `0x14005b8b2`
- name: `DestroyAllTransferPackets`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400231f0`

## callees

- `0x140016070`
- `0x14005b740`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005b891`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b891`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14005b763`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14005b763`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005b7bb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005b823`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005b7bb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005b823`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14005b7dc`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14005b7dc`
- `ntoskrnl!KeCancelTimer` at `0x14005b86b`
- `ntoskrnl!KeCancelTimer` at `0x14005b86b`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14005b877`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14005b877`

## pseudocode

```c
void __fastcall DestroyAllTransferPackets(__int64 a1)
{
  __int64 v1; // rbx
  ULONG v2; // edi
  ULONG MaximumProcessorCount; // ebp
  unsigned __int64 v4; // rsi
  PSLIST_ENTRY v5; // rax
  USHORT HighestNodeNumber; // ax
  unsigned int v7; // edi
  unsigned int v8; // ebp
  unsigned __int64 v9; // rsi
  PSLIST_ENTRY v10; // rax
  __int64 v11; // rcx
  void *v12; // rcx

  v1 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 1144LL);
  if ( *(_QWORD *)(v1 + 680) )
  {
    v2 = 0;
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    if ( MaximumProcessorCount )
    {
      do
      {
        v4 = (unsigned __int64)v2 << 6;
        while ( 1 )
        {
          v5 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v4 + *(_QWORD *)(v1 + 680)));
          if ( !v5 )
            break;
          v5->Next = 0;
          _InterlockedDecrement((volatile signed __int32 *)(v4 + *(_QWORD *)(v1 + 680) + 16));
          _InterlockedDecrement((volatile signed __int32 *)(((unsigned __int64)*((unsigned int *)&v5[22].Next + 3) << 6)
                                                          + *(_QWORD *)(v1 + 1536)
                                                          + 16));
          DestroyTransferPacket(&v5[-1]);
        }
        ++v2;
      }
      while ( v2 < MaximumProcessorCount );
    }
  }
  if ( *(_QWORD *)(v1 + 1536) )
  {
    HighestNodeNumber = KeQueryHighestNodeNumber();
    v7 = 0;
    v8 = HighestNodeNumber + 1;
    if ( HighestNodeNumber != -1 )
    {
      do
      {
        v9 = (unsigned __int64)v7 << 6;
        while ( 1 )
        {
          v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v9 + *(_QWORD *)(v1 + 1536)));
          if ( !v10 )
            break;
          v10->Next = 0;
          _InterlockedDecrement((volatile signed __int32 *)(v9 + *(_QWORD *)(v1 + 1536) + 16));
          DestroyTransferPacket(&v10[-1]);
        }
        ++v7;
      }
      while ( v7 < v8 );
    }
  }
  v11 = *(_QWORD *)(v1 + 488);
  if ( v11 )
  {
    *(_QWORD *)(v1 + 488) = 0;
    DestroyTransferPacket((PVOID)(v11 - 16));
  }
  if ( (*(_DWORD *)(v1 + 664) & 8) != 0 )
  {
    KeCancelTimer((PKTIMER)(v1 + 496));
    KeFlushQueuedDpcs();
  }
  v12 = *(void **)(v1 + 688);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0);
    *(_QWORD *)(v1 + 688) = 0;
  }
}

```

## disassembly

```asm
0x14005b740  push    rbx
0x14005b742  push    rbp
0x14005b743  push    rsi
0x14005b744  push    rdi
0x14005b745  sub     rsp, 28h
0x14005b749  mov     rax, [rcx+40h]
0x14005b74d  mov     rbx, [rax+478h]
0x14005b754  cmp     qword ptr [rbx+2A8h], 0
0x14005b75c  jz      short loc_14005B7D2
0x14005b75e  mov     ecx, 0FFFFh; GroupNumber
0x14005b763  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14005b76a  nop     dword ptr [rax+rax+00h]
0x14005b76f  xor     edi, edi
0x14005b771  mov     ebp, eax
0x14005b773  test    eax, eax
0x14005b775  jz      short loc_14005B7D2
0x14005b777  mov     esi, edi
0x14005b779  shl     rsi, 6
0x14005b77d  jmp     short loc_14005B7B1
0x14005b77f  mov     qword ptr [rax], 0
0x14005b786  lea     rcx, [rax-10h]; P
0x14005b78a  mov     rax, [rbx+2A8h]
0x14005b791  lock dec dword ptr [rsi+rax+10h]
0x14005b796  mov     edx, [rcx+17Ch]
0x14005b79c  mov     rax, [rbx+600h]
0x14005b7a3  shl     rdx, 6
0x14005b7a7  lock dec dword ptr [rdx+rax+10h]
0x14005b7ac  call    DestroyTransferPacket
0x14005b7b1  mov     rcx, [rbx+2A8h]
0x14005b7b8  add     rcx, rsi; ListHead
0x14005b7bb  call    cs:__imp_ExpInterlockedPopEntrySList
0x14005b7c2  nop     dword ptr [rax+rax+00h]
0x14005b7c7  test    rax, rax
0x14005b7ca  jnz     short loc_14005B77F
0x14005b7cc  inc     edi
0x14005b7ce  cmp     edi, ebp
0x14005b7d0  jb      short loc_14005B777
0x14005b7d2  cmp     qword ptr [rbx+600h], 0
0x14005b7da  jz      short loc_14005B83A
0x14005b7dc  call    cs:__imp_KeQueryHighestNodeNumber
0x14005b7e3  nop     dword ptr [rax+rax+00h]
0x14005b7e8  movzx   ebp, ax
0x14005b7eb  mov     edi, 0
0x14005b7f0  add     ebp, 1
0x14005b7f3  jz      short loc_14005B83A
0x14005b7f5  mov     esi, edi
0x14005b7f7  shl     rsi, 6
0x14005b7fb  jmp     short loc_14005B819
0x14005b7fd  mov     qword ptr [rax], 0
0x14005b804  mov     rcx, [rbx+600h]
0x14005b80b  lock dec dword ptr [rsi+rcx+10h]
0x14005b810  lea     rcx, [rax-10h]; P
0x14005b814  call    DestroyTransferPacket
0x14005b819  mov     rcx, [rbx+600h]
0x14005b820  add     rcx, rsi; ListHead
0x14005b823  call    cs:__imp_ExpInterlockedPopEntrySList
0x14005b82a  nop     dword ptr [rax+rax+00h]
0x14005b82f  test    rax, rax
0x14005b832  jnz     short loc_14005B7FD
0x14005b834  inc     edi
0x14005b836  cmp     edi, ebp
0x14005b838  jb      short loc_14005B7F5
0x14005b83a  mov     rcx, [rbx+1E8h]
0x14005b841  test    rcx, rcx
0x14005b844  jz      short loc_14005B85A
0x14005b846  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14005b84a  mov     qword ptr [rbx+1E8h], 0
0x14005b855  call    DestroyTransferPacket
0x14005b85a  mov     eax, [rbx+298h]
0x14005b860  test    al, 8
0x14005b862  jz      short loc_14005B883
0x14005b864  lea     rcx, [rbx+1F0h]; PKTIMER
0x14005b86b  call    cs:__imp_KeCancelTimer
0x14005b872  nop     dword ptr [rax+rax+00h]
0x14005b877  call    cs:__imp_KeFlushQueuedDpcs
0x14005b87e  nop     dword ptr [rax+rax+00h]
0x14005b883  mov     rcx, [rbx+2B0h]; P
0x14005b88a  test    rcx, rcx
0x14005b88d  jz      short loc_14005B8A8
0x14005b88f  xor     edx, edx; Tag
0x14005b891  call    cs:__imp_ExFreePoolWithTag
0x14005b898  nop     dword ptr [rax+rax+00h]
0x14005b89d  mov     qword ptr [rbx+2B0h], 0
0x14005b8a8  add     rsp, 28h
0x14005b8ac  pop     rdi
0x14005b8ad  pop     rsi
0x14005b8ae  pop     rbp
0x14005b8af  pop     rbx
0x14005b8b0  retn
```
