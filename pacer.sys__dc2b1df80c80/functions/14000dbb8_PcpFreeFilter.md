# PcpFreeFilter

- ea: `0x14000dbb8`
- end: `0x14000dc36`
- name: `PcpFreeFilter`
- size: `126`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d284`
- `0x14000d708`
- `0x14001d708`
- `0x14001d7cc`

## callees

- `0x14000dbb8`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000dc0d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000dc0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc1e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000dbe5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000dbe5`
- `NETIO!HfFreeHandle32` at `0x14000dbfc`
- `NETIO!HfFreeHandle32` at `0x14000dbfc`

## pseudocode

```c
void __fastcall PcpFreeFilter(_DWORD *P)
{
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P[10] )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, &LockHandle);
    HfFreeHandle32(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement, P + 10);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000dbb8  mov     [rsp+arg_0], rbx
0x14000dbbd  push    rdi
0x14000dbbe  sub     rsp, 40h
0x14000dbc2  xor     eax, eax
0x14000dbc4  xorps   xmm0, xmm0
0x14000dbc7  mov     rbx, rcx
0x14000dbca  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x14000dbcf  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14000dbd4  cmp     [rcx+28h], eax
0x14000dbd7  jz      short loc_14000DC19
0x14000dbd9  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14000dbde  lea     rcx, WPP_MAIN_CB.Queue+40h; SpinLock
0x14000dbe5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000dbec  nop     dword ptr [rax+rax+00h]
0x14000dbf1  mov     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x14000dbf8  lea     rdx, [rbx+28h]
0x14000dbfc  call    cs:__imp_HfFreeHandle32
0x14000dc03  nop     dword ptr [rax+rax+00h]
0x14000dc08  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14000dc0d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000dc14  nop     dword ptr [rax+rax+00h]
0x14000dc19  xor     edx, edx; Tag
0x14000dc1b  mov     rcx, rbx; P
0x14000dc1e  call    cs:__imp_ExFreePoolWithTag
0x14000dc25  nop     dword ptr [rax+rax+00h]
0x14000dc2a  mov     rbx, [rsp+48h+arg_0]
0x14000dc2f  add     rsp, 40h
0x14000dc33  pop     rdi
0x14000dc34  retn
```
