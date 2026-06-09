# PcFilterPause

- ea: `0x140001010`
- end: `0x1400010cf`
- name: `PcFilterPause`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000287c`
- `0x14000298c`

## import_xrefs

- `NDIS!NdisWaitEvent` at `0x1400010b3`
- `NDIS!NdisWaitEvent` at `0x1400010b3`
- `NDIS!NdisReleaseRWLock` at `0x14000104c`
- `NDIS!NdisReleaseRWLock` at `0x14000104c`
- `NDIS!NdisAcquireRWLockWrite` at `0x140001030`
- `NDIS!NdisAcquireRWLockWrite` at `0x140001030`

## pseudocode

```c
__int64 __fastcall PcFilterPause(__int64 a1)
{
  struct _NDIS_RW_LOCK_EX *v2; // rcx
  struct _NDIS_RW_LOCK_EX *v3; // rcx
  __int64 v4; // r8
  __int64 result; // rax
  _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v2 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 32);
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v2, &LockState, 0);
  v3 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 32);
  *(_DWORD *)(a1 + 24) = 4;
  NdisReleaseRWLock(v3, &LockState);
  v4 = *(_QWORD *)(a1 + 160);
  PcpTraceLineUpDownEvent(
    v4 + 296,
    *(_DWORD *)(a1 + 16),
    *(_QWORD *)(v4 + 272),
    *(unsigned __int16 *)(v4 + 264),
    *(_QWORD *)(v4 + 288),
    *(unsigned __int16 *)(v4 + 280),
    18);
  PcpFilterDecrementPauseCount(a1, 1);
  NdisWaitEvent((PNDIS_EVENT)(a1 + 136), 0);
  result = 0;
  *(_DWORD *)(a1 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x140001010  push    rbx
0x140001012  sub     rsp, 40h
0x140001016  xor     eax, eax
0x140001018  lea     rdx, [rsp+48h+LockState]; LockState
0x14000101d  mov     rbx, rcx
0x140001020  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x140001025  mov     rcx, [rcx+20h]; Lock
0x140001029  xor     r8d, r8d; Flags
0x14000102c  mov     [rsp+48h+LockState.Flags], al
0x140001030  call    cs:__imp_NdisAcquireRWLockWrite
0x140001037  nop     dword ptr [rax+rax+00h]
0x14000103c  mov     rcx, [rbx+20h]; Lock
0x140001040  lea     rdx, [rsp+48h+LockState]; LockState
0x140001045  mov     dword ptr [rbx+18h], 4
0x14000104c  call    cs:__imp_NdisReleaseRWLock
0x140001053  nop     dword ptr [rax+rax+00h]
0x140001058  mov     r8, [rbx+0A0h]
0x14000105f  mov     edx, [rbx+10h]
0x140001062  mov     [rsp+48h+var_18], 12h
0x14000106a  movzx   eax, word ptr [r8+118h]
0x140001072  lea     rcx, [r8+128h]
0x140001079  movzx   r9d, word ptr [r8+108h]
0x140001081  mov     [rsp+48h+var_20], eax
0x140001085  mov     rax, [r8+120h]
0x14000108c  mov     r8, [r8+110h]
0x140001093  mov     [rsp+48h+var_28], rax
0x140001098  call    PcpTraceLineUpDownEvent
0x14000109d  mov     edx, 1
0x1400010a2  mov     rcx, rbx
0x1400010a5  call    PcpFilterDecrementPauseCount
0x1400010aa  lea     rcx, [rbx+88h]; Event
0x1400010b1  xor     edx, edx; MsToWait
0x1400010b3  call    cs:__imp_NdisWaitEvent
0x1400010ba  nop     dword ptr [rax+rax+00h]
0x1400010bf  xor     eax, eax
0x1400010c1  mov     dword ptr [rbx+18h], 1
0x1400010c8  add     rsp, 40h
0x1400010cc  pop     rbx
0x1400010cd  retn
```
