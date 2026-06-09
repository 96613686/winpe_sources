# NetiopRemoveFlowFromHashTables

- ea: `0x14002c6f0`
- end: `0x14002c79d`
- name: `NetiopRemoveFlowFromHashTables`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002bac0`

## callees

- `0x14002c6f0`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002c736`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002c75b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002c780`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002c736`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002c75b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14002c780`

## pseudocode

```c
char __fastcall NetiopRemoveFlowFromHashTables(__int64 a1, __int64 a2)
{
  int v4; // eax

  if ( (*(_DWORD *)(a2 + 16) & 8) != 0 )
  {
    RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 80), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 80), 0);
    *(_DWORD *)(a2 + 16) &= ~8u;
    _InterlockedAdd((volatile signed __int32 *)(a2 + 176), 0xFFFFFFFE);
  }
  if ( (*(_DWORD *)(a2 + 16) & 0x10) != 0 )
  {
    RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 80), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 104), 0);
    *(_DWORD *)(a2 + 16) &= ~0x10u;
    _InterlockedAdd((volatile signed __int32 *)(a2 + 176), 0xFFFFFFFE);
  }
  v4 = *(_DWORD *)(a2 + 16);
  if ( (v4 & 4) != 0 )
  {
    LOBYTE(v4) = RtlRemoveEntryHashTable(
                   (PRTL_DYNAMIC_HASH_TABLE)(a1 + 16),
                   (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 56),
                   0);
    *(_DWORD *)(a2 + 16) &= ~4u;
    _InterlockedAdd((volatile signed __int32 *)(a2 + 176), 0xFFFFFFFE);
  }
  return v4;
}

```

## disassembly

```asm
0x14002c6f0  mov     [rsp+arg_0], rbx
0x14002c6f5  mov     [rsp+arg_8], rsi
0x14002c6fa  push    rdi
0x14002c6fb  sub     rsp, 20h
0x14002c6ff  mov     eax, [rdx+10h]
0x14002c702  mov     rbx, rdx
0x14002c705  mov     rsi, rcx
0x14002c708  test    al, 8
0x14002c70a  jnz     short loc_14002C750
0x14002c70c  mov     eax, [rbx+10h]
0x14002c70f  test    al, 10h
0x14002c711  jnz     short loc_14002C775
0x14002c713  mov     eax, [rbx+10h]
0x14002c716  test    al, 4
0x14002c718  jnz     short loc_14002C72B
0x14002c71a  mov     rbx, [rsp+28h+arg_0]
0x14002c71f  mov     rsi, [rsp+28h+arg_8]
0x14002c724  add     rsp, 20h
0x14002c728  pop     rdi
0x14002c729  retn
0x14002c72b  lea     rdx, [rbx+38h]; Entry
0x14002c72f  xor     r8d, r8d; Context
0x14002c732  lea     rcx, [rsi+10h]; HashTable
0x14002c736  call    cs:__imp_RtlRemoveEntryHashTable
0x14002c73d  nop     dword ptr [rax+rax+00h]
0x14002c742  and     dword ptr [rbx+10h], 0FFFFFFFBh
0x14002c746  lock add dword ptr [rbx+0B0h], 0FFFFFFFEh
0x14002c74e  jmp     short loc_14002C71A
0x14002c750  mov     rcx, [rcx+50h]; HashTable
0x14002c754  add     rdx, 50h ; 'P'; Entry
0x14002c758  xor     r8d, r8d; Context
0x14002c75b  call    cs:__imp_RtlRemoveEntryHashTable
0x14002c762  nop     dword ptr [rax+rax+00h]
0x14002c767  and     dword ptr [rbx+10h], 0FFFFFFF7h
0x14002c76b  lock add dword ptr [rbx+0B0h], 0FFFFFFFEh
0x14002c773  jmp     short loc_14002C70C
0x14002c775  mov     rcx, [rsi+50h]; HashTable
0x14002c779  lea     rdx, [rbx+68h]; Entry
0x14002c77d  xor     r8d, r8d; Context
0x14002c780  call    cs:__imp_RtlRemoveEntryHashTable
0x14002c787  nop     dword ptr [rax+rax+00h]
0x14002c78c  and     dword ptr [rbx+10h], 0FFFFFFEFh
0x14002c790  lock add dword ptr [rbx+0B0h], 0FFFFFFFEh
0x14002c798  jmp     loc_14002C713
```
