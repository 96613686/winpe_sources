# VmbusTlCommonOppositeEndpointDisconnectRequest

- ea: `0x14000483c`
- end: `0x140004890`
- name: `VmbusTlCommonOppositeEndpointDisconnectRequest`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000309c`
- `0x140007b00`

## callees

- `0x1400049a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004852`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004852`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004873`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004873`

## pseudocode

```c
void __fastcall VmbusTlCommonOppositeEndpointDisconnectRequest(__int64 a1)
{
  KIRQL v2; // bl
  __int64 v3; // r8
  __int64 v4; // r9

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  VmbusTlTransitionDisconnectState(a1, 17, v3, v4);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), v2);
}

```

## disassembly

```asm
0x14000483c  mov     [rsp+arg_0], rbx
0x140004841  mov     [rsp+arg_8], rsi
0x140004846  push    rdi
0x140004847  sub     rsp, 20h
0x14000484b  mov     rdi, rcx
0x14000484e  add     rcx, 48h ; 'H'; SpinLock
0x140004852  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004859  nop     dword ptr [rax+rax+00h]
0x14000485e  mov     edx, 11h
0x140004863  mov     rcx, rdi
0x140004866  mov     bl, al
0x140004868  call    VmbusTlTransitionDisconnectState
0x14000486d  mov     dl, bl; NewIrql
0x14000486f  lea     rcx, [rdi+48h]; SpinLock
0x140004873  call    cs:__imp_KeReleaseSpinLock
0x14000487a  nop     dword ptr [rax+rax+00h]
0x14000487f  mov     rbx, [rsp+28h+arg_0]
0x140004884  mov     rsi, [rsp+28h+arg_8]
0x140004889  add     rsp, 20h
0x14000488d  pop     rdi
0x14000488e  retn
```
