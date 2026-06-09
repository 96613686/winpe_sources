# SendHeaderComplete

- ea: `0x1400174b0`
- end: `0x1400174e4`
- name: `SendHeaderComplete`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001c6d0`

## callees

- `0x1400174b0`
- `0x14001b830`

## import_xrefs

- `NDIS!NdisFreeNetBufferList` at `0x1400174c4`
- `NDIS!NdisFreeNetBufferList` at `0x1400174c4`

## pseudocode

```c
void __fastcall SendHeaderComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx

  v3 = *(_QWORD *)(a3 + 144);
  NdisFreeNetBufferList(*(PNET_BUFFER_LIST *)(a3 + 128));
  if ( v3 )
    DereferenceCall(v3);
}

```

## disassembly

```asm
0x1400174b0  push    rbx
0x1400174b2  sub     rsp, 20h
0x1400174b6  mov     rcx, [r8+80h]; NetBufferList
0x1400174bd  mov     rbx, [r8+90h]
0x1400174c4  call    cs:__imp_NdisFreeNetBufferList
0x1400174cb  nop     dword ptr [rax+rax+00h]
0x1400174d0  test    rbx, rbx
0x1400174d3  jz      short loc_1400174DD
0x1400174d5  mov     rcx, rbx
0x1400174d8  call    DereferenceCall
0x1400174dd  add     rsp, 20h
0x1400174e1  pop     rbx
0x1400174e2  retn
```
