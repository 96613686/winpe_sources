# PcpFilterDecrementIntercept

- ea: `0x14000b584`
- end: `0x14000b5d7`
- name: `PcpFilterDecrementIntercept`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140003ab0`
- `0x140005578`
- `0x14000d708`
- `0x14000df98`
- `0x14000e024`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x14000b5c4`
- `NDIS!NdisReleaseRWLock` at `0x14000b5c4`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b5a6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b5a6`

## pseudocode

```c
void __fastcall PcpFilterDecrementIntercept(int a1)
{
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(PcgFilterDriverContext, &LockState, 0);
  dword_140018838 -= a1;
  NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
}

```

## disassembly

```asm
0x14000b584  push    rbx
0x14000b586  sub     rsp, 20h
0x14000b58a  xor     eax, eax
0x14000b58c  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b591  mov     ebx, ecx
0x14000b593  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000b598  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b59f  xor     r8d, r8d; Flags
0x14000b5a2  mov     [rsp+28h+LockState.Flags], al
0x14000b5a6  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b5ad  nop     dword ptr [rax+rax+00h]
0x14000b5b2  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b5b9  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b5be  sub     cs:dword_140018838, ebx
0x14000b5c4  call    cs:__imp_NdisReleaseRWLock
0x14000b5cb  nop     dword ptr [rax+rax+00h]
0x14000b5d0  add     rsp, 20h
0x14000b5d4  pop     rbx
0x14000b5d5  retn
```
