# NdisGetCurrentThreadCompartmentId

- ea: `0x1400248f8`
- end: `0x140024917`
- name: `NdisGetCurrentThreadCompartmentId`
- size: `31`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000e31c`
- `0x140014564`
- `0x1400203d0`
- `0x14004c1a4`
- `0x14004f224`

## import_xrefs

- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140024905`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140024905`

## pseudocode

```c
__int64 NdisGetCurrentThreadCompartmentId()
{
  return NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
}

```

## disassembly

```asm
0x1400248f8  sub     rsp, 28h
0x1400248fc  mov     rcx, gs:188h
0x140024905  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14002490c  nop     dword ptr [rax+rax+00h]
0x140024911  add     rsp, 28h
0x140024915  retn
```
