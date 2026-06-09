# CdSyncCompletionRoutine

- ea: `0x140001ce0`
- end: `0x140001d03`
- name: `CdSyncCompletionRoutine`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001cec`
- `ntoskrnl!KeSetEvent` at `0x140001cec`

## pseudocode

```c
__int64 __fastcall CdSyncCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001ce0  sub     rsp, 28h
0x140001ce4  mov     rcx, r8; Event
0x140001ce7  xor     edx, edx; Increment
0x140001ce9  xor     r8d, r8d; Wait
0x140001cec  call    cs:__imp_KeSetEvent
0x140001cf3  nop     dword ptr [rax+rax+00h]
0x140001cf8  mov     eax, 0C0000016h
0x140001cfd  add     rsp, 28h
0x140001d01  retn
```
