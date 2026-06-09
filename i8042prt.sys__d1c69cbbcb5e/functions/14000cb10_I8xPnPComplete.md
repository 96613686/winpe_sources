# I8xPnPComplete

- ea: `0x14000cb10`
- end: `0x14000cb33`
- name: `I8xPnPComplete`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000cb1c`
- `ntoskrnl!KeSetEvent` at `0x14000cb1c`

## pseudocode

```c
__int64 __fastcall I8xPnPComplete(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000cb10  sub     rsp, 28h
0x14000cb14  mov     rcx, r8; Event
0x14000cb17  xor     edx, edx; Increment
0x14000cb19  xor     r8d, r8d; Wait
0x14000cb1c  call    cs:__imp_KeSetEvent
0x14000cb23  nop     dword ptr [rax+rax+00h]
0x14000cb28  mov     eax, 0C0000016h
0x14000cb2d  add     rsp, 28h
0x14000cb31  retn
```
