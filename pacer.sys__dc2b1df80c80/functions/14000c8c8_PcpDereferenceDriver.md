# PcpDereferenceDriver

- ea: `0x14000c8c8`
- end: `0x14000c8f5`
- name: `PcpDereferenceDriver`
- size: `45`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cc50`
- `0x14000feb0`
- `0x14001db60`
- `0x14001deb0`
- `0x14001f580`

## callees

- `0x14000c8c8`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x14000c8e3`
- `NDIS!NdisSetEvent` at `0x14000c8e3`

## pseudocode

```c
void PcpDereferenceDriver()
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&WPP_MAIN_CB.DeviceQueue.Lock, 0xFFFFFFFF) == 1 )
    NdisSetEvent((PNDIS_EVENT)&WPP_MAIN_CB.DeviceQueue);
}

```

## disassembly

```asm
0x14000c8c8  sub     rsp, 28h
0x14000c8cc  or      eax, 0FFFFFFFFh
0x14000c8cf  lock xadd dword ptr cs:WPP_MAIN_CB.DeviceQueue.Lock, eax
0x14000c8d7  cmp     eax, 1
0x14000c8da  jnz     short loc_14000C8EF
0x14000c8dc  lea     rcx, WPP_MAIN_CB.DeviceQueue; Event
0x14000c8e3  call    cs:__imp_NdisSetEvent
0x14000c8ea  nop     dword ptr [rax+rax+00h]
0x14000c8ef  add     rsp, 28h
0x14000c8f3  retn
```
