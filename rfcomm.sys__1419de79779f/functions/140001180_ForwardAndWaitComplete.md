# ForwardAndWaitComplete

- ea: `0x140001180`
- end: `0x1400011a3`
- name: `ForwardAndWaitComplete`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000118c`
- `ntoskrnl!KeSetEvent` at `0x14000118c`

## pseudocode

```c
__int64 __fastcall ForwardAndWaitComplete(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001180  sub     rsp, 28h
0x140001184  mov     rcx, r8; Event
0x140001187  xor     edx, edx; Increment
0x140001189  xor     r8d, r8d; Wait
0x14000118c  call    cs:__imp_KeSetEvent
0x140001193  nop     dword ptr [rax+rax+00h]
0x140001198  mov     eax, 0C0000016h
0x14000119d  add     rsp, 28h
0x1400011a1  retn
```
