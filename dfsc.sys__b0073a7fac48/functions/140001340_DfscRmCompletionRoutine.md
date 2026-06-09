# DfscRmCompletionRoutine

- ea: `0x140001340`
- end: `0x140001363`
- name: `DfscRmCompletionRoutine`
- size: `35`
- prototype: `__int64 __fastcall(__int64, __int64, struct _KEVENT *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000134c`
- `ntoskrnl!KeSetEvent` at `0x14000134c`

## pseudocode

```c
__int64 __fastcall DfscRmCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001340  sub     rsp, 28h
0x140001344  mov     rcx, r8; Event
0x140001347  xor     edx, edx; Increment
0x140001349  xor     r8d, r8d; Wait
0x14000134c  call    cs:__imp_KeSetEvent
0x140001353  nop     dword ptr [rax+rax+00h]
0x140001358  mov     eax, 0C0000016h
0x14000135d  add     rsp, 28h
0x140001361  retn
```
