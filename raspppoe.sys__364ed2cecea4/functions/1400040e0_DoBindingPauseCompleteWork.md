# DoBindingPauseCompleteWork

- ea: `0x1400040e0`
- end: `0x1400040fa`
- name: `DoBindingPauseCompleteWork`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x1400040e8`
- `NDIS!NdisSetEvent` at `0x1400040e8`

## pseudocode

```c
void __fastcall DoBindingPauseCompleteWork(__int64 a1)
{
  NdisSetEvent((PNDIS_EVENT)(a1 + 16));
}

```

## disassembly

```asm
0x1400040e0  sub     rsp, 28h
0x1400040e4  add     rcx, 10h; Event
0x1400040e8  call    cs:__imp_NdisSetEvent
0x1400040ef  nop     dword ptr [rax+rax+00h]
0x1400040f4  add     rsp, 28h
0x1400040f8  retn
```
