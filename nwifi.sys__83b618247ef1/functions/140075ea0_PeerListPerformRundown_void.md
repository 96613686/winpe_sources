# PeerListPerformRundown(void *)

- ea: `0x140075ea0`
- end: `0x140075fda`
- name: `?PeerListPerformRundown@@YAXPEAX@Z`
- size: `314`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000d22c`
- `0x140023214`
- `0x140075ea0`
- `0x14009a410`

## import_xrefs

- `NDIS!NdisAcquireRWLockWrite` at `0x140075f05`
- `NDIS!NdisAcquireRWLockWrite` at `0x140075f74`
- `NDIS!NdisAcquireRWLockWrite` at `0x140075f05`
- `NDIS!NdisAcquireRWLockWrite` at `0x140075f74`
- `NDIS!NdisReleaseRWLock` at `0x140075f3f`
- `NDIS!NdisReleaseRWLock` at `0x140075fa2`
- `NDIS!NdisReleaseRWLock` at `0x140075f3f`
- `NDIS!NdisReleaseRWLock` at `0x140075fa2`

## pseudocode

```c
void __fastcall PeerListPerformRundown(void (__fastcall **a1)(__int64))
{
  void (__fastcall *v2)(__int64); // rdx
  void (__fastcall *v3)(__int64); // rdi
  void (__fastcall *v4)(__int64); // rsi
  signed __int32 v5[18]; // [rsp+0h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_143d7e9099d53a97c245021a6e328668_Traceguids);
  PeerListWaitForZeroPeers(a1, 0x7530u);
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(**(_QWORD **)a1[2] + 144LL), &LockState, 0);
  v2 = a1[2];
  v3 = a1[9];
  v4 = a1[10];
  a1[9] = 0;
  a1[10] = 0;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(**(_QWORD **)v2 + 144LL), &LockState);
  if ( v3 )
    v3((__int64)v4);
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(**(_QWORD **)a1[2] + 144LL), &LockState, 0);
  *((_DWORD *)a1 + 16) = 0;
  _InterlockedOr(v5, 0);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(**(_QWORD **)a1[2] + 144LL), &LockState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_143d7e9099d53a97c245021a6e328668_Traceguids);
}

```

## disassembly

```asm
0x140075ea0  push    rbx
0x140075ea2  push    rsi
0x140075ea3  push    rdi
0x140075ea4  push    r14
0x140075ea6  sub     rsp, 28h
0x140075eaa  xor     eax, eax
0x140075eac  mov     [rsp+48h+LockState.OldIrql], 0
0x140075eb1  mov     word ptr [rsp+48h+LockState.LockState], ax
0x140075eb6  mov     rbx, rcx
0x140075eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140075ec0  lea     r14, WPP_GLOBAL_Control
0x140075ec7  cmp     rcx, r14
0x140075eca  jz      short loc_140075EDF
0x140075ecc  mov     rcx, [rcx+18h]
0x140075ed0  lea     edx, [rax+22h]
0x140075ed3  lea     r8, WPP_143d7e9099d53a97c245021a6e328668_Traceguids
0x140075eda  call    WPP_SF_
0x140075edf  mov     edx, 7530h; unsigned int
0x140075ee4  mov     rcx, rbx; void *
0x140075ee7  call    ?PeerListWaitForZeroPeers@@YAXPEAXK@Z; PeerListWaitForZeroPeers(void *,ulong)
0x140075eec  mov     rax, [rbx+10h]
0x140075ef0  lea     rdx, [rsp+48h+LockState]; LockState
0x140075ef5  xor     r8d, r8d; Flags
0x140075ef8  mov     rcx, [rax]
0x140075efb  mov     rcx, [rcx]
0x140075efe  mov     rcx, [rcx+90h]; Lock
0x140075f05  call    cs:__imp_NdisAcquireRWLockWrite
0x140075f0c  nop     dword ptr [rax+rax+00h]
0x140075f11  mov     rdx, [rbx+10h]
0x140075f15  mov     rdi, [rbx+48h]
0x140075f19  mov     rsi, [rbx+50h]
0x140075f1d  mov     qword ptr [rbx+48h], 0
0x140075f25  mov     qword ptr [rbx+50h], 0
0x140075f2d  mov     r8, [rdx]
0x140075f30  lea     rdx, [rsp+48h+LockState]; LockState
0x140075f35  mov     rcx, [r8]
0x140075f38  mov     rcx, [rcx+90h]; Lock
0x140075f3f  call    cs:__imp_NdisReleaseRWLock
0x140075f46  nop     dword ptr [rax+rax+00h]
0x140075f4b  test    rdi, rdi
0x140075f4e  jz      short loc_140075F5B
0x140075f50  mov     rcx, rsi
0x140075f53  mov     rax, rdi
0x140075f56  call    _guard_dispatch_icall
0x140075f5b  mov     rax, [rbx+10h]
0x140075f5f  lea     rdx, [rsp+48h+LockState]; LockState
0x140075f64  xor     r8d, r8d; Flags
0x140075f67  mov     rcx, [rax]
0x140075f6a  mov     rcx, [rcx]
0x140075f6d  mov     rcx, [rcx+90h]; Lock
0x140075f74  call    cs:__imp_NdisAcquireRWLockWrite
0x140075f7b  nop     dword ptr [rax+rax+00h]
0x140075f80  mov     dword ptr [rbx+40h], 0
0x140075f87  lock or [rsp+48h+var_48], 0
0x140075f8c  mov     rax, [rbx+10h]
0x140075f90  lea     rdx, [rsp+48h+LockState]; LockState
0x140075f95  mov     rcx, [rax]
0x140075f98  mov     rcx, [rcx]
0x140075f9b  mov     rcx, [rcx+90h]; Lock
0x140075fa2  call    cs:__imp_NdisReleaseRWLock
0x140075fa9  nop     dword ptr [rax+rax+00h]
0x140075fae  mov     rcx, cs:WPP_GLOBAL_Control
0x140075fb5  cmp     rcx, r14
0x140075fb8  jz      short loc_140075FCF
0x140075fba  mov     rcx, [rcx+18h]
0x140075fbe  lea     r8, WPP_143d7e9099d53a97c245021a6e328668_Traceguids
0x140075fc5  mov     edx, 23h ; '#'
0x140075fca  call    WPP_SF_
0x140075fcf  add     rsp, 28h
0x140075fd3  pop     r14
0x140075fd5  pop     rdi
0x140075fd6  pop     rsi
0x140075fd7  pop     rbx
0x140075fd8  retn
```
