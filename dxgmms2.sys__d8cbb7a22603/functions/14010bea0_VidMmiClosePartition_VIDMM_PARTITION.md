# VidMmiClosePartition(VIDMM_PARTITION *)

- ea: `0x14010bea0`
- end: `0x14010bf24`
- name: `?VidMmiClosePartition@@YAXPEAUVIDMM_PARTITION@@@Z`
- size: `132`
- prototype: `void __fastcall(struct VIDMM_PARTITION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400fdc1c`
- `0x140128b9c`

## callees

- `0x1400490bc`
- `0x14010bea0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010bea9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010bea9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010bebe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010bebe`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010bee0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010bee0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010beec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010beec`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14010bf09`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14010bf09`

## pseudocode

```c
void __fastcall VidMmiClosePartition(struct VIDMM_PARTITION *this)
{
  unsigned int v2; // edx

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&VIDMM_PARTITION::_PartitionLock, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 9, 0xFFFFFFFF) == 1 )
  {
    RtlAvlRemoveNode(&VIDMM_PARTITION::_PartitionTree, this);
    if ( this )
      VIDMM_PARTITION::`scalar deleting destructor'(this, v2);
  }
  ExReleasePushLockExclusiveEx(&VIDMM_PARTITION::_PartitionLock, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14010bea0  push    rbx
0x14010bea2  sub     rsp, 20h
0x14010bea6  mov     rbx, rcx
0x14010bea9  call    cs:__imp_KeEnterCriticalRegion
0x14010beb0  nop     dword ptr [rax+rax+00h]
0x14010beb5  xor     edx, edx
0x14010beb7  lea     rcx, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK VIDMM_PARTITION::_PartitionLock
0x14010bebe  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14010bec5  nop     dword ptr [rax+rax+00h]
0x14010beca  or      eax, 0FFFFFFFFh
0x14010becd  lock xadd [rbx+24h], eax
0x14010bed2  cmp     eax, 1
0x14010bed5  jz      short loc_14010BEFF
0x14010bed7  xor     edx, edx
0x14010bed9  lea     rcx, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK VIDMM_PARTITION::_PartitionLock
0x14010bee0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14010bee7  nop     dword ptr [rax+rax+00h]
0x14010beec  call    cs:__imp_KeLeaveCriticalRegion
0x14010bef3  nop     dword ptr [rax+rax+00h]
0x14010bef8  add     rsp, 20h
0x14010befc  pop     rbx
0x14010befd  retn
0x14010beff  mov     rdx, rbx
0x14010bf02  lea     rcx, ?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x14010bf09  call    cs:__imp_RtlAvlRemoveNode
0x14010bf10  nop     dword ptr [rax+rax+00h]
0x14010bf15  test    rbx, rbx
0x14010bf18  jz      short loc_14010BED7
0x14010bf1a  mov     rcx, rbx; this
0x14010bf1d  call    ??_GVIDMM_PARTITION@@QEAAPEAXI@Z; VIDMM_PARTITION::`scalar deleting destructor'(uint)
0x14010bf22  jmp     short loc_14010BED7
```
