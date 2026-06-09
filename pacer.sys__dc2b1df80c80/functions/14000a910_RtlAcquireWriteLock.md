# RtlAcquireWriteLock

- ea: `0x14000a910`
- end: `0x14000a933`
- name: `RtlAcquireWriteLock`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ab0`
- `0x14000d708`
- `0x14000d8b8`
- `0x1400101c0`
- `0x140010b68`

## callees

- `0x14000a910`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a919`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a919`

## pseudocode

```c
__int64 __fastcall RtlAcquireWriteLock(__int64 a1, struct _KLOCK_QUEUE_HANDLE *a2)
{
  __int64 result; // rax

  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1, a2);
  do
    result = *(unsigned int *)(a1 + 8);
  while ( (_DWORD)result );
  return result;
}

```

## disassembly

```asm
0x14000a910  push    rbx
0x14000a912  sub     rsp, 20h
0x14000a916  mov     rbx, rcx
0x14000a919  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000a920  nop     dword ptr [rax+rax+00h]
0x14000a925  mov     eax, [rbx+8]
0x14000a928  test    eax, eax
0x14000a92a  jnz     short loc_14000A925
0x14000a92c  add     rsp, 20h
0x14000a930  pop     rbx
0x14000a931  retn
```
