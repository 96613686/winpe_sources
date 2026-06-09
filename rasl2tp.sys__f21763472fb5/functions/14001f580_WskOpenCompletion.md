# WskOpenCompletion

- ea: `0x14001f580`
- end: `0x14001f5a5`
- name: `WskOpenCompletion`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001f58e`
- `ntoskrnl!KeSetEvent` at `0x14001f58e`

## pseudocode

```c
__int64 __fastcall WskOpenCompletion(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 2, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001f580  sub     rsp, 28h
0x14001f584  mov     rcx, r8; Event
0x14001f587  xor     r8d, r8d; Wait
0x14001f58a  lea     edx, [r8+2]; Increment
0x14001f58e  call    cs:__imp_KeSetEvent
0x14001f595  nop     dword ptr [rax+rax+00h]
0x14001f59a  mov     eax, 0C0000016h
0x14001f59f  add     rsp, 28h
0x14001f5a3  retn
```
