# BfsInsertEntryHashTable

- ea: `0x140012ca0`
- end: `0x140012ccd`
- name: `BfsInsertEntryHashTable`
- size: `45`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007a20`
- `0x140007cf0`
- `0x140007fec`
- `0x140008728`
- `0x14000b654`
- `0x14000c0f4`
- `0x14000d9dc`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140012cb0`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140012cb0`

## pseudocode

```c
__int64 __fastcall BfsInsertEntryHashTable(
        struct _RTL_DYNAMIC_HASH_TABLE *a1,
        ULONG_PTR a2,
        struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *a3)
{
  return RtlInsertEntryHashTable(a1, a3, a2, 0) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x140012ca0  sub     rsp, 28h
0x140012ca4  mov     rax, r8
0x140012ca7  xor     r9d, r9d; Context
0x140012caa  mov     r8, rdx; Signature
0x140012cad  mov     rdx, rax; Entry
0x140012cb0  call    cs:__imp_RtlInsertEntryHashTable
0x140012cb7  nop     dword ptr [rax+rax+00h]
0x140012cbc  neg     al
0x140012cbe  sbb     eax, eax
0x140012cc0  not     eax
0x140012cc2  and     eax, 0C0000001h
0x140012cc7  add     rsp, 28h
0x140012ccb  retn
```
