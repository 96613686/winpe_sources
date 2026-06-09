# PcpFilterDecrementPauseCount

- ea: `0x14000298c`
- end: `0x1400029be`
- name: `PcpFilterDecrementPauseCount`
- size: `50`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x140008440`
- `0x1400085c0`
- `0x140020810`

## callees

- `0x14000298c`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x1400029a9`
- `NDIS!NdisSetEvent` at `0x1400029a9`

## pseudocode

```c
__int64 __fastcall PcpFilterDecrementPauseCount(__int64 a1, int a2)
{
  unsigned int v2; // ebx

  v2 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 128), -a2) - a2;
  if ( !v2 )
    NdisSetEvent((PNDIS_EVENT)(a1 + 136));
  return v2;
}

```

## disassembly

```asm
0x14000298c  push    rbx
0x14000298e  sub     rsp, 20h
0x140002992  neg     edx
0x140002994  mov     ebx, edx
0x140002996  lock xadd [rcx+80h], ebx
0x14000299e  add     ebx, edx
0x1400029a0  jnz     short loc_1400029B5
0x1400029a2  add     rcx, 88h; Event
0x1400029a9  call    cs:__imp_NdisSetEvent
0x1400029b0  nop     dword ptr [rax+rax+00h]
0x1400029b5  mov     eax, ebx
0x1400029b7  add     rsp, 20h
0x1400029bb  pop     rbx
0x1400029bc  retn
```
