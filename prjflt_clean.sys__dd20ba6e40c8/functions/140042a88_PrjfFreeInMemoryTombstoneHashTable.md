# PrjfFreeInMemoryTombstoneHashTable

- ea: `0x140042a88`
- end: `0x140042b65`
- name: `PrjfFreeInMemoryTombstoneHashTable`
- size: `221`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400211e0`

## callees

- `0x140042a88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042ae5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042b0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042ae5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042b0e`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140042b3e`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140042b3e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140042acb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140042acb`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140042b22`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140042b22`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140042ab7`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140042ab7`
- `ntoskrnl!RtlDeleteHashTable` at `0x140042b4d`
- `ntoskrnl!RtlDeleteHashTable` at `0x140042b4d`
- `FLTMGR!FltReleaseContext` at `0x140042afa`
- `FLTMGR!FltReleaseContext` at `0x140042afa`

## pseudocode

```c
void __fastcall PrjfFreeInMemoryTombstoneHashTable(PRTL_DYNAMIC_HASH_TABLE HashTable)
{
  void *Signature; // rcx
  struct _LIST_ENTRY *Flink; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v4; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v5; // rdi
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-38h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( HashTable->NumEntries )
  {
    RtlInitEnumerationHashTable(HashTable, &Enumerator);
    while ( 1 )
    {
      v4 = RtlEnumerateEntryHashTable(HashTable, &Enumerator);
      v5 = v4;
      if ( !v4 )
        break;
      RtlRemoveEntryHashTable(HashTable, v4, 0);
      Signature = (void *)v5[1].Signature;
      if ( Signature )
        ExFreePoolWithTag(Signature, 0x6E664A50u);
      Flink = v5[2].Linkage.Flink;
      if ( Flink )
        FltReleaseContext(Flink);
      ExFreePoolWithTag(v5, 0x74684A50u);
    }
    RtlEndEnumerationHashTable(HashTable, &Enumerator);
  }
  RtlDeleteHashTable(HashTable);
}

```

## disassembly

```asm
0x140042a88  mov     [rsp+arg_0], rbx
0x140042a8d  push    rdi
0x140042a8e  sub     rsp, 50h
0x140042a92  xor     eax, eax
0x140042a94  xorps   xmm0, xmm0
0x140042a97  mov     rbx, rcx
0x140042a9a  mov     qword ptr [rsp+58h+Enumerator.BucketIndex], rax
0x140042a9f  movups  xmmword ptr [rsp+58h+Enumerator], xmm0
0x140042aa4  movups  xmmword ptr [rsp+58h+Enumerator+10h], xmm0
0x140042aa9  cmp     [rcx+14h], eax
0x140042aac  jz      loc_140042B4A
0x140042ab2  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140042ab7  call    cs:__imp_RtlInitEnumerationHashTable
0x140042abe  nop     dword ptr [rax+rax+00h]
0x140042ac3  jmp     short loc_140042B1A
0x140042ac5  xor     r8d, r8d; Context
0x140042ac8  mov     rdx, rdi; Entry
0x140042acb  call    cs:__imp_RtlRemoveEntryHashTable
0x140042ad2  nop     dword ptr [rax+rax+00h]
0x140042ad7  mov     rcx, [rdi+28h]; P
0x140042adb  test    rcx, rcx
0x140042ade  jz      short loc_140042AF1
0x140042ae0  mov     edx, 6E664A50h; Tag
0x140042ae5  call    cs:__imp_ExFreePoolWithTag
0x140042aec  nop     dword ptr [rax+rax+00h]
0x140042af1  mov     rcx, [rdi+30h]; Context
0x140042af5  test    rcx, rcx
0x140042af8  jz      short loc_140042B06
0x140042afa  call    cs:__imp_FltReleaseContext
0x140042b01  nop     dword ptr [rax+rax+00h]
0x140042b06  mov     edx, 74684A50h; Tag
0x140042b0b  mov     rcx, rdi; P
0x140042b0e  call    cs:__imp_ExFreePoolWithTag
0x140042b15  nop     dword ptr [rax+rax+00h]
0x140042b1a  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140042b1f  mov     rcx, rbx; HashTable
0x140042b22  call    cs:__imp_RtlEnumerateEntryHashTable
0x140042b29  nop     dword ptr [rax+rax+00h]
0x140042b2e  mov     rdi, rax
0x140042b31  mov     rcx, rbx; HashTable
0x140042b34  test    rax, rax
0x140042b37  jnz     short loc_140042AC5
0x140042b39  lea     rdx, [rsp+58h+Enumerator]; Enumerator
0x140042b3e  call    cs:__imp_RtlEndEnumerationHashTable
0x140042b45  nop     dword ptr [rax+rax+00h]
0x140042b4a  mov     rcx, rbx; HashTable
0x140042b4d  call    cs:__imp_RtlDeleteHashTable
0x140042b54  nop     dword ptr [rax+rax+00h]
0x140042b59  mov     rbx, [rsp+58h+arg_0]
0x140042b5e  add     rsp, 50h
0x140042b62  pop     rdi
0x140042b63  retn
```
