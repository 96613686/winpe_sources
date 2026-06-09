# AsyncIoCompletion

- ea: `0x140001240`
- end: `0x140001262`
- name: `AsyncIoCompletion`
- size: `34`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001250`
- `ntoskrnl!KeSetEvent` at `0x140001250`

## pseudocode

```c
void __fastcall AsyncIoCompletion(PFLT_CALLBACK_DATA CallbackData, char *Context)
{
  KeSetEvent((PRKEVENT)(Context + 152), 0, 0);
}

```

## disassembly

```asm
0x140001240  sub     rsp, 28h
0x140001244  lea     rcx, [rdx+98h]; Event
0x14000124b  xor     r8d, r8d; Wait
0x14000124e  xor     edx, edx; Increment
0x140001250  call    cs:__imp_KeSetEvent
0x140001257  nop     dword ptr [rax+rax+00h]
0x14000125c  add     rsp, 28h
0x140001260  retn
```
