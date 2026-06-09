# PplpGenericAllocateFunction

- ea: `0x140012350`
- end: `0x14001236a`
- name: `PplpGenericAllocateFunction`
- size: `26`
- prototype: `ALLOCATE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012358`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012358`

## pseudocode

```c
PVOID __fastcall PplpGenericAllocateFunction(
        POOL_TYPE PoolType,
        SIZE_T NumberOfBytes,
        ULONG Tag,
        PLOOKASIDE_LIST_EX Lookaside)
{
  return ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)Lookaside[1].L.ListHead.Alignment);
}

```

## disassembly

```asm
0x140012350  sub     rsp, 28h
0x140012354  mov     rcx, [r9+60h]; Lookaside
0x140012358  call    cs:__imp_ExAllocateFromLookasideListEx
0x14001235f  nop     dword ptr [rax+rax+00h]
0x140012364  add     rsp, 28h
0x140012368  retn
```
