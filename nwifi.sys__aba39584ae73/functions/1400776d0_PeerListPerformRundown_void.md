# PeerListPerformRundown(void *)

- ea: `0x1400776d0`
- end: `0x14007780a`
- name: `?PeerListPerformRundown@@YAXPEAX@Z`
- size: `314`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000d21c`
- `0x140023214`
- `0x1400776d0`
- `0x14009bbf0`

## import_xrefs

- `NDIS!NdisAcquireRWLockWrite` at `0x140077735`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400777a4`
- `NDIS!NdisAcquireRWLockWrite` at `0x140077735`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400777a4`
- `NDIS!NdisReleaseRWLock` at `0x14007776f`
- `NDIS!NdisReleaseRWLock` at `0x1400777d2`
- `NDIS!NdisReleaseRWLock` at `0x14007776f`
- `NDIS!NdisReleaseRWLock` at `0x1400777d2`

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
0x1400776d0  push    rbx
0x1400776d2  push    rsi
0x1400776d3  push    rdi
0x1400776d4  push    r14
0x1400776d6  sub     rsp, 28h
0x1400776da  xor     eax, eax
0x1400776dc  mov     [rsp+48h+LockState.OldIrql], 0
0x1400776e1  mov     word ptr [rsp+48h+LockState.LockState], ax
0x1400776e6  mov     rbx, rcx
0x1400776e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400776f0  lea     r14, WPP_GLOBAL_Control
0x1400776f7  cmp     rcx, r14
0x1400776fa  jz      short loc_14007770F
0x1400776fc  mov     rcx, [rcx+18h]
0x140077700  lea     edx, [rax+22h]
0x140077703  lea     r8, WPP_143d7e9099d53a97c245021a6e328668_Traceguids
0x14007770a  call    WPP_SF_
0x14007770f  mov     edx, 7530h; unsigned int
0x140077714  mov     rcx, rbx; void *
0x140077717  call    ?PeerListWaitForZeroPeers@@YAXPEAXK@Z; PeerListWaitForZeroPeers(void *,ulong)
0x14007771c  mov     rax, [rbx+10h]
0x140077720  lea     rdx, [rsp+48h+LockState]; LockState
0x140077725  xor     r8d, r8d; Flags
0x140077728  mov     rcx, [rax]
0x14007772b  mov     rcx, [rcx]
0x14007772e  mov     rcx, [rcx+90h]; Lock
0x140077735  call    cs:__imp_NdisAcquireRWLockWrite
0x14007773c  nop     dword ptr [rax+rax+00h]
0x140077741  mov     rdx, [rbx+10h]
0x140077745  mov     rdi, [rbx+48h]
0x140077749  mov     rsi, [rbx+50h]
0x14007774d  mov     qword ptr [rbx+48h], 0
0x140077755  mov     qword ptr [rbx+50h], 0
0x14007775d  mov     r8, [rdx]
0x140077760  lea     rdx, [rsp+48h+LockState]; LockState
0x140077765  mov     rcx, [r8]
0x140077768  mov     rcx, [rcx+90h]; Lock
0x14007776f  call    cs:__imp_NdisReleaseRWLock
0x140077776  nop     dword ptr [rax+rax+00h]
0x14007777b  test    rdi, rdi
0x14007777e  jz      short loc_14007778B
0x140077780  mov     rcx, rsi
0x140077783  mov     rax, rdi
0x140077786  call    _guard_dispatch_icall
0x14007778b  mov     rax, [rbx+10h]
0x14007778f  lea     rdx, [rsp+48h+LockState]; LockState
0x140077794  xor     r8d, r8d; Flags
0x140077797  mov     rcx, [rax]
0x14007779a  mov     rcx, [rcx]
0x14007779d  mov     rcx, [rcx+90h]; Lock
0x1400777a4  call    cs:__imp_NdisAcquireRWLockWrite
0x1400777ab  nop     dword ptr [rax+rax+00h]
0x1400777b0  mov     dword ptr [rbx+40h], 0
0x1400777b7  lock or [rsp+48h+var_48], 0
0x1400777bc  mov     rax, [rbx+10h]
0x1400777c0  lea     rdx, [rsp+48h+LockState]; LockState
0x1400777c5  mov     rcx, [rax]
0x1400777c8  mov     rcx, [rcx]
0x1400777cb  mov     rcx, [rcx+90h]; Lock
0x1400777d2  call    cs:__imp_NdisReleaseRWLock
0x1400777d9  nop     dword ptr [rax+rax+00h]
0x1400777de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400777e5  cmp     rcx, r14
0x1400777e8  jz      short loc_1400777FF
0x1400777ea  mov     rcx, [rcx+18h]
0x1400777ee  lea     r8, WPP_143d7e9099d53a97c245021a6e328668_Traceguids
0x1400777f5  mov     edx, 23h ; '#'
0x1400777fa  call    WPP_SF_
0x1400777ff  add     rsp, 28h
0x140077803  pop     r14
0x140077805  pop     rdi
0x140077806  pop     rsi
0x140077807  pop     rbx
0x140077808  retn
```
