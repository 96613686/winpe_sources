# HIDSM_CompletingPnPEventOnSurpriseRemove

- ea: `0x180019430`
- end: `0x18001945e`
- name: `HIDSM_CompletingPnPEventOnSurpriseRemove`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x180019447`
- `ntoskrnl!KeSetEvent` at `0x180019447`

## pseudocode

```c
__int64 __fastcall HIDSM_CompletingPnPEventOnSurpriseRemove(__int64 a1)
{
  KeSetEvent((PRKEVENT)(*(_QWORD *)(a1 + 960) + 1832LL), 0, 0);
  return 2013;
}

```

## disassembly

```asm
0x180019430  sub     rsp, 28h
0x180019434  mov     rcx, [rcx+3C0h]
0x18001943b  xor     r8d, r8d; Wait
0x18001943e  add     rcx, 728h; Event
0x180019445  xor     edx, edx; Increment
0x180019447  call    cs:__imp_KeSetEvent
0x18001944e  nop     dword ptr [rax+rax+00h]
0x180019453  mov     eax, 7DDh
0x180019458  add     rsp, 28h
0x18001945c  retn
```
