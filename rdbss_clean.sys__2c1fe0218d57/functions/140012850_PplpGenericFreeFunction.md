# PplpGenericFreeFunction

- ea: `0x140012850`
- end: `0x140012870`
- name: `PplpGenericFreeFunction`
- size: `32`
- prototype: `FREE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001285e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001285e`

## pseudocode

```c
void __fastcall PplpGenericFreeFunction(PVOID Buffer, PLOOKASIDE_LIST_EX Lookaside)
{
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)Lookaside[1].L.ListHead.Alignment, Buffer);
}

```

## disassembly

```asm
0x140012850  sub     rsp, 28h
0x140012854  mov     rax, rdx
0x140012857  mov     rdx, rcx; Entry
0x14001285a  mov     rcx, [rax+60h]; Lookaside
0x14001285e  call    cs:__imp_ExFreeToLookasideListEx
0x140012865  nop     dword ptr [rax+rax+00h]
0x14001286a  add     rsp, 28h
0x14001286e  retn
```
