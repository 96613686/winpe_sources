# HidpSynchronousCallCompletion

- ea: `0x180012010`
- end: `0x180012033`
- name: `HidpSynchronousCallCompletion`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x18001201c`
- `ntoskrnl!KeSetEvent` at `0x18001201c`

## pseudocode

```c
__int64 __fastcall HidpSynchronousCallCompletion(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x180012010  sub     rsp, 28h
0x180012014  mov     rcx, r8; Event
0x180012017  xor     edx, edx; Increment
0x180012019  xor     r8d, r8d; Wait
0x18001201c  call    cs:__imp_KeSetEvent
0x180012023  nop     dword ptr [rax+rax+00h]
0x180012028  mov     eax, 0C0000016h
0x18001202d  add     rsp, 28h
0x180012031  retn
```
