# DereferenceAdapter

- ea: `0x140002a30`
- end: `0x140002a5c`
- name: `DereferenceAdapter`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400047b0`
- `0x1400051f0`
- `0x140005d00`
- `0x14001af90`

## callees

- `0x140002a30`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x140002a4a`
- `NDIS!NdisSetEvent` at `0x140002a4a`

## pseudocode

```c
void __fastcall DereferenceAdapter(struct _NDIS_EVENT *a1)
{
  if ( _InterlockedExchangeAdd(&a1[1].Event.Header.Lock, 0xFFFFFFFF) == 1 )
    NdisSetEvent(a1 + 7);
}

```

## disassembly

```asm
0x140002a30  sub     rsp, 28h
0x140002a34  mov     eax, 0FFFFFFFFh
0x140002a39  lock xadd [rcx+18h], eax
0x140002a3e  cmp     eax, 1
0x140002a41  jnz     short loc_140002A56
0x140002a43  add     rcx, 0A8h; Event
0x140002a4a  call    cs:__imp_NdisSetEvent
0x140002a51  nop     dword ptr [rax+rax+00h]
0x140002a56  add     rsp, 28h
0x140002a5a  retn
```
