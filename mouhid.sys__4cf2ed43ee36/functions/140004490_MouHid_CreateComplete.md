# MouHid_CreateComplete

- ea: `0x140004490`
- end: `0x1400044b3`
- name: `MouHid_CreateComplete`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000449c`
- `ntoskrnl!KeSetEvent` at `0x14000449c`

## pseudocode

```c
__int64 __fastcall MouHid_CreateComplete(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140004490  sub     rsp, 28h
0x140004494  mov     rcx, r8; Event
0x140004497  xor     edx, edx; Increment
0x140004499  xor     r8d, r8d; Wait
0x14000449c  call    cs:__imp_KeSetEvent
0x1400044a3  nop     dword ptr [rax+rax+00h]
0x1400044a8  mov     eax, 0C0000016h
0x1400044ad  add     rsp, 28h
0x1400044b1  retn
```
