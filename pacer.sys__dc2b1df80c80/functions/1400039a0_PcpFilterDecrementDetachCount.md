# PcpFilterDecrementDetachCount

- ea: `0x1400039a0`
- end: `0x1400039d0`
- name: `PcpFilterDecrementDetachCount`
- size: `48`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400029d0`
- `0x140003770`
- `0x1400057d0`
- `0x140005c10`
- `0x140009240`
- `0x14000b5e0`
- `0x1400209b4`

## callees

- `0x1400039a0`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x1400039c2`
- `NDIS!NdisSetEvent` at `0x1400039c2`

## pseudocode

```c
__int64 __fastcall PcpFilterDecrementDetachCount(__int64 a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 100));
  if ( !v1 )
    NdisSetEvent((PNDIS_EVENT)(a1 + 104));
  return v1;
}

```

## disassembly

```asm
0x1400039a0  push    rbx
0x1400039a2  sub     rsp, 20h
0x1400039a6  mov     ebx, 0FFFFFFFFh
0x1400039ab  lock xadd [rcx+64h], ebx
0x1400039b0  sub     ebx, 1
0x1400039b3  jz      short loc_1400039BE
0x1400039b5  mov     eax, ebx
0x1400039b7  add     rsp, 20h
0x1400039bb  pop     rbx
0x1400039bc  retn
0x1400039be  add     rcx, 68h ; 'h'; Event
0x1400039c2  call    cs:__imp_NdisSetEvent
0x1400039c9  nop     dword ptr [rax+rax+00h]
0x1400039ce  jmp     short loc_1400039B5
```
