# BwcDereferenceQoSPolicy

- ea: `0x140013b68`
- end: `0x140013bbe`
- name: `BwcDereferenceQoSPolicy`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140005494`
- `0x140011064`
- `0x140011940`

## callees

- `0x1400035f0`

## import_xrefs

- `NDIS!NdisReleaseReadWriteLock` at `0x140013bab`
- `NDIS!NdisReleaseReadWriteLock` at `0x140013bab`
- `NDIS!NdisAcquireReadWriteLock` at `0x140013b8a`
- `NDIS!NdisAcquireReadWriteLock` at `0x140013b8a`

## pseudocode

```c
void __fastcall BwcDereferenceQoSPolicy(__int64 a1)
{
  struct _LOCK_STATE LockState; // [rsp+38h] [rbp+10h] BYREF

  LockState = 0;
  NdisAcquireReadWriteLock(&QoSPoliciesHashTableRWLock, 1u, &LockState);
  DereferenceRefCount(a1 + 24);
  NdisReleaseReadWriteLock(&QoSPoliciesHashTableRWLock, &LockState);
}

```

## disassembly

```asm
0x140013b68  mov     dword ptr [rsp+LockState.LockState], edx
0x140013b6c  push    rbx
0x140013b6d  sub     rsp, 20h
0x140013b71  mov     rbx, rcx
0x140013b74  mov     dword ptr [rsp+28h+LockState.LockState], 0
0x140013b7c  lea     rcx, QoSPoliciesHashTableRWLock; Lock
0x140013b83  mov     dl, 1; fWrite
0x140013b85  lea     r8, [rsp+28h+LockState]; LockState
0x140013b8a  call    cs:__imp_NdisAcquireReadWriteLock
0x140013b91  nop     dword ptr [rax+rax+00h]
0x140013b96  lea     rcx, [rbx+18h]
0x140013b9a  call    DereferenceRefCount
0x140013b9f  lea     rdx, [rsp+28h+LockState]; LockState
0x140013ba4  lea     rcx, QoSPoliciesHashTableRWLock; Lock
0x140013bab  call    cs:__imp_NdisReleaseReadWriteLock
0x140013bb2  nop     dword ptr [rax+rax+00h]
0x140013bb7  add     rsp, 20h
0x140013bbb  pop     rbx
0x140013bbc  retn
```
