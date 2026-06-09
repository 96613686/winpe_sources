# KbdHid_CreateComplete

- ea: `0x140003e00`
- end: `0x140003e23`
- name: `KbdHid_CreateComplete`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140003e0c`
- `ntoskrnl!KeSetEvent` at `0x140003e0c`

## pseudocode

```c
__int64 __fastcall KbdHid_CreateComplete(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140003e00  sub     rsp, 28h
0x140003e04  mov     rcx, r8; Event
0x140003e07  xor     edx, edx; Increment
0x140003e09  xor     r8d, r8d; Wait
0x140003e0c  call    cs:__imp_KeSetEvent
0x140003e13  nop     dword ptr [rax+rax+00h]
0x140003e18  mov     eax, 0C0000016h
0x140003e1d  add     rsp, 28h
0x140003e21  retn
```
