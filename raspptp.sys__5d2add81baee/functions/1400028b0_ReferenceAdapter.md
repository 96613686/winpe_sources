# ReferenceAdapter

- ea: `0x1400028b0`
- end: `0x1400028e0`
- name: `ReferenceAdapter`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006810`
- `0x140011920`
- `0x14001af90`

## callees

- `0x1400028b0`

## import_xrefs

- `NDIS!NdisResetEvent` at `0x1400028d2`
- `NDIS!NdisResetEvent` at `0x1400028d2`

## pseudocode

```c
void __fastcall ReferenceAdapter(struct _NDIS_EVENT *a1)
{
  if ( _InterlockedIncrement(&a1[1].Event.Header.Lock) == 1 )
    NdisResetEvent(a1 + 7);
}

```

## disassembly

```asm
0x1400028b0  sub     rsp, 28h
0x1400028b4  mov     eax, 1
0x1400028b9  lock xadd [rcx+18h], eax
0x1400028be  inc     eax
0x1400028c0  cmp     eax, 1
0x1400028c3  jz      short loc_1400028CB
0x1400028c5  add     rsp, 28h
0x1400028c9  retn
0x1400028cb  add     rcx, 0A8h; Event
0x1400028d2  call    cs:__imp_NdisResetEvent
0x1400028d9  nop     dword ptr [rax+rax+00h]
0x1400028de  jmp     short loc_1400028C5
```
