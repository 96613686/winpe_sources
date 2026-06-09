# RtlAcquireWriteLockAtDpcLevel

- ea: `0x140007e10`
- end: `0x140007e33`
- name: `RtlAcquireWriteLockAtDpcLevel`
- size: `35`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x14000bcb4`
- `0x14000cce0`
- `0x14000d284`
- `0x14000e91c`
- `0x14000e9fc`

## callees

- `0x140007e10`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140007e19`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140007e19`

## pseudocode

```c
__int64 __fastcall RtlAcquireWriteLockAtDpcLevel(__int64 a1, struct _KLOCK_QUEUE_HANDLE *a2)
{
  __int64 result; // rax

  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)a1, a2);
  do
    result = *(unsigned int *)(a1 + 8);
  while ( (_DWORD)result );
  return result;
}

```

## disassembly

```asm
0x140007e10  push    rbx
0x140007e12  sub     rsp, 20h
0x140007e16  mov     rbx, rcx
0x140007e19  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140007e20  nop     dword ptr [rax+rax+00h]
0x140007e25  mov     eax, [rbx+8]
0x140007e28  test    eax, eax
0x140007e2a  jnz     short loc_140007E25
0x140007e2c  add     rsp, 20h
0x140007e30  pop     rbx
0x140007e31  retn
```
