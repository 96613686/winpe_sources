# VidMmiClosePartition(VIDMM_PARTITION *)

- ea: `0x140102a4c`
- end: `0x140102ad0`
- name: `?VidMmiClosePartition@@YAXPEAUVIDMM_PARTITION@@@Z`
- size: `132`
- prototype: `void __fastcall(struct VIDMM_PARTITION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140102390`
- `0x140123a74`

## callees

- `0x140048b2c`
- `0x140102a4c`

## import_xrefs

- `ntoskrnl!RtlAvlRemoveNode` at `0x140102ab5`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140102ab5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140102a55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140102a55`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140102a6a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140102a6a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140102a8c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140102a8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140102a98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140102a98`

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
0x140102a4c  push    rbx
0x140102a4e  sub     rsp, 20h
0x140102a52  mov     rbx, rcx
0x140102a55  call    cs:__imp_KeEnterCriticalRegion
0x140102a5c  nop     dword ptr [rax+rax+00h]
0x140102a61  xor     edx, edx
0x140102a63  lea     rcx, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK VIDMM_PARTITION::_PartitionLock
0x140102a6a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140102a71  nop     dword ptr [rax+rax+00h]
0x140102a76  or      eax, 0FFFFFFFFh
0x140102a79  lock xadd [rbx+24h], eax
0x140102a7e  cmp     eax, 1
0x140102a81  jz      short loc_140102AAB
0x140102a83  xor     edx, edx
0x140102a85  lea     rcx, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK VIDMM_PARTITION::_PartitionLock
0x140102a8c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140102a93  nop     dword ptr [rax+rax+00h]
0x140102a98  call    cs:__imp_KeLeaveCriticalRegion
0x140102a9f  nop     dword ptr [rax+rax+00h]
0x140102aa4  add     rsp, 20h
0x140102aa8  pop     rbx
0x140102aa9  retn
0x140102aab  mov     rdx, rbx
0x140102aae  lea     rcx, ?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x140102ab5  call    cs:__imp_RtlAvlRemoveNode
0x140102abc  nop     dword ptr [rax+rax+00h]
0x140102ac1  test    rbx, rbx
0x140102ac4  jz      short loc_140102A83
0x140102ac6  mov     rcx, rbx; this
0x140102ac9  call    ??_GVIDMM_PARTITION@@QEAAPEAXI@Z; VIDMM_PARTITION::`scalar deleting destructor'(uint)
0x140102ace  jmp     short loc_140102A83
```
