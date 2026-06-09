# RtlAcquireWriteLockAtDpcLevel

- ea: `0x140013a04`
- end: `0x140013a27`
- name: `RtlAcquireWriteLockAtDpcLevel`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002974`
- `0x140012480`
- `0x140013080`

## callees

- `0x140013a04`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140013a0d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140013a0d`

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
0x140013a04  push    rbx
0x140013a06  sub     rsp, 20h
0x140013a0a  mov     rbx, rcx
0x140013a0d  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140013a14  nop     dword ptr [rax+rax+00h]
0x140013a19  mov     eax, [rbx+8]
0x140013a1c  test    eax, eax
0x140013a1e  jnz     short loc_140013A19
0x140013a20  add     rsp, 20h
0x140013a24  pop     rbx
0x140013a25  retn
```
