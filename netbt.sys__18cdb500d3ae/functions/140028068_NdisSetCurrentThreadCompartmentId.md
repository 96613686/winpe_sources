# NdisSetCurrentThreadCompartmentId

- ea: `0x140028068`
- end: `0x140028089`
- name: `NdisSetCurrentThreadCompartmentId`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014500`
- `0x140014564`
- `0x14004c1a4`

## import_xrefs

- `NDIS!NdisSetThreadObjectCompartmentId` at `0x140028077`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x140028077`

## pseudocode

```c
__int64 __fastcall NdisSetCurrentThreadCompartmentId(unsigned int a1)
{
  return NdisSetThreadObjectCompartmentId(KeGetCurrentThread(), a1);
}

```

## disassembly

```asm
0x140028068  sub     rsp, 28h
0x14002806c  mov     edx, ecx
0x14002806e  mov     rcx, gs:188h
0x140028077  call    cs:__imp_NdisSetThreadObjectCompartmentId
0x14002807e  nop     dword ptr [rax+rax+00h]
0x140028083  add     rsp, 28h
0x140028087  retn
```
