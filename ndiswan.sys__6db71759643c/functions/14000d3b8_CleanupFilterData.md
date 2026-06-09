# CleanupFilterData

- ea: `0x14000d3b8`
- end: `0x14000d42b`
- name: `CleanupFilterData`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d770`

## callees

- `0x14000d3b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d418`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d418`
- `NDIS!NdisReleaseRWLock` at `0x14000d402`
- `NDIS!NdisReleaseRWLock` at `0x14000d402`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000d3d8`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000d3d8`

## pseudocode

```c
void CleanupFilterData()
{
  PVOID v0; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(NdisWanPacketCapFilterLock, &LockState, 0);
  v0 = NDISWanPacketCapRules;
  NDISWanPacketCapRules = 0;
  NdisReleaseRWLock(NdisWanPacketCapFilterLock, &LockState);
  if ( v0 )
    ExFreePoolWithTag(v0, 0);
}

```

## disassembly

```asm
0x14000d3b8  push    rbx
0x14000d3ba  sub     rsp, 20h
0x14000d3be  mov     rcx, cs:NdisWanPacketCapFilterLock; Lock
0x14000d3c5  lea     rdx, [rsp+28h+LockState]; LockState
0x14000d3ca  xor     eax, eax
0x14000d3cc  xor     r8d, r8d; Flags
0x14000d3cf  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000d3d4  mov     [rsp+28h+LockState.Flags], al
0x14000d3d8  call    cs:__imp_NdisAcquireRWLockWrite
0x14000d3df  nop     dword ptr [rax+rax+00h]
0x14000d3e4  mov     rbx, cs:NDISWanPacketCapRules
0x14000d3eb  lea     rdx, [rsp+28h+LockState]; LockState
0x14000d3f0  mov     rcx, cs:NdisWanPacketCapFilterLock; Lock
0x14000d3f7  mov     cs:NDISWanPacketCapRules, 0
0x14000d402  call    cs:__imp_NdisReleaseRWLock
0x14000d409  nop     dword ptr [rax+rax+00h]
0x14000d40e  test    rbx, rbx
0x14000d411  jz      short loc_14000D424
0x14000d413  xor     edx, edx; Tag
0x14000d415  mov     rcx, rbx; P
0x14000d418  call    cs:__imp_ExFreePoolWithTag
0x14000d41f  nop     dword ptr [rax+rax+00h]
0x14000d424  add     rsp, 20h
0x14000d428  pop     rbx
0x14000d429  retn
```
