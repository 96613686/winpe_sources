# lldpDeleteNeighborOnPort

- ea: `0x140004a90`
- end: `0x140004ad9`
- name: `lldpDeleteNeighborOnPort`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002fe0`
- `0x1400049a0`
- `0x140010aec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004ab3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004ab3`
- `ntoskrnl!KeCancelTimer` at `0x140004ac6`
- `ntoskrnl!KeCancelTimer` at `0x140004ac6`

## pseudocode

```c
BOOLEAN __fastcall lldpDeleteNeighborOnPort(__int64 a1)
{
  _BYTE *v2; // rcx

  v2 = *(_BYTE **)(a1 + 968);
  *(_QWORD *)(a1 + 968) = 0;
  *v2 = 0;
  ExFreePoolWithTag(v2, 0x50444C4Cu);
  return KeCancelTimer((PKTIMER)(a1 + 312));
}

```

## disassembly

```asm
0x140004a90  push    rbx
0x140004a92  sub     rsp, 20h
0x140004a96  mov     rbx, rcx
0x140004a99  mov     edx, 50444C4Ch; Tag
0x140004a9e  mov     rcx, [rcx+3C8h]; P
0x140004aa5  mov     qword ptr [rbx+3C8h], 0
0x140004ab0  mov     byte ptr [rcx], 0
0x140004ab3  call    cs:__imp_ExFreePoolWithTag
0x140004aba  nop     dword ptr [rax+rax+00h]
0x140004abf  lea     rcx, [rbx+138h]; PKTIMER
0x140004ac6  call    cs:__imp_KeCancelTimer
0x140004acd  nop     dword ptr [rax+rax+00h]
0x140004ad2  add     rsp, 20h
0x140004ad6  pop     rbx
0x140004ad7  retn
```
