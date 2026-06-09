# lldpDereferencePacketPool

- ea: `0x140010aa8`
- end: `0x140010ae5`
- name: `lldpDereferencePacketPool`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a20`
- `0x14000e670`
- `0x140010a50`

## callees

- `0x140010aa8`

## import_xrefs

- `NDIS!NdisFreeNetBufferListPool` at `0x140010ac8`
- `NDIS!NdisFreeNetBufferListPool` at `0x140010ac8`

## pseudocode

```c
void lldpDereferencePacketPool()
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&WPP_MAIN_CB.Dpc.DpcListEntry, 0xFFFFFFFF) == 1 )
  {
    if ( WPP_MAIN_CB.Dpc.SystemArgument1 )
    {
      NdisFreeNetBufferListPool(WPP_MAIN_CB.Dpc.SystemArgument1);
      WPP_MAIN_CB.Dpc.SystemArgument1 = 0;
    }
  }
}

```

## disassembly

```asm
0x140010aa8  sub     rsp, 28h
0x140010aac  or      eax, 0FFFFFFFFh
0x140010aaf  lock xadd dword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, eax
0x140010ab7  cmp     eax, 1
0x140010aba  jnz     short loc_140010ADF
0x140010abc  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; PoolHandle
0x140010ac3  test    rcx, rcx
0x140010ac6  jz      short loc_140010ADF
0x140010ac8  call    cs:__imp_NdisFreeNetBufferListPool
0x140010acf  nop     dword ptr [rax+rax+00h]
0x140010ad4  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument1, 0
0x140010adf  add     rsp, 28h
0x140010ae3  retn
```
