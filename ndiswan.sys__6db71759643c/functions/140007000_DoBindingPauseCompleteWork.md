# DoBindingPauseCompleteWork

- ea: `0x140007000`
- end: `0x14000701d`
- name: `DoBindingPauseCompleteWork`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x14000700b`
- `NDIS!NdisSetEvent` at `0x14000700b`

## pseudocode

```c
void __fastcall DoBindingPauseCompleteWork(__int64 a1)
{
  NdisSetEvent((PNDIS_EVENT)(a1 + 496));
}

```

## disassembly

```asm
0x140007000  sub     rsp, 28h
0x140007004  add     rcx, 1F0h; Event
0x14000700b  call    cs:__imp_NdisSetEvent
0x140007012  nop     dword ptr [rax+rax+00h]
0x140007017  add     rsp, 28h
0x14000701b  retn
```
