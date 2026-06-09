# WfpHashtableDestroy

- ea: `0x14006bac8`
- end: `0x14006bb79`
- name: `WfpHashtableDestroy`
- size: `177`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140041b48`
- `0x140061e80`
- `0x14006c620`

## callees

- `0x14006bac8`
- `0x14006bb80`
- `0x140078080`

## import_xrefs

- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14006bb4d`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14006bb4d`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14006bb17`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14006bb17`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14006bafb`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14006bafb`
- `ntoskrnl!RtlDeleteHashTable` at `0x14006bb5c`
- `ntoskrnl!RtlDeleteHashTable` at `0x14006bb5c`

## pseudocode

```c
void __fastcall WfpHashtableDestroy(
        PRTL_DYNAMIC_HASH_TABLE HashTable,
        void (__fastcall *a2)(PRTL_DYNAMIC_HASH_TABLE_ENTRY *))
{
  __int128 HashTablea; // [rsp+20h] [rbp-30h] BYREF
  __int128 Enumerator_8; // [rsp+30h] [rbp-20h]
  __int128 Enumerator_24; // [rsp+40h] [rbp-10h]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+60h] [rbp+10h] BYREF

  Entry = 0;
  HashTablea = 0;
  Enumerator_8 = 0;
  Enumerator_24 = 0;
  RtlInitEnumerationHashTable(HashTable, (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)((char *)&HashTablea + 8));
  *(_QWORD *)&HashTablea = HashTable;
  while ( (unsigned int)WfpHashtableIteratorGetNext(&HashTablea, &Entry) )
  {
    RtlRemoveEntryHashTable(HashTable, Entry, 0);
    if ( a2 )
      a2(&Entry);
  }
  RtlEndEnumerationHashTable(
    (PRTL_DYNAMIC_HASH_TABLE)HashTablea,
    (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)((char *)&HashTablea + 8));
  RtlDeleteHashTable(HashTable);
}

```

## disassembly

```asm
0x14006bac8  mov     [rsp-8+arg_8], rbx
0x14006bacd  mov     [rsp-8+arg_10], rdi
0x14006bad2  push    rbp
0x14006bad3  mov     rbp, rsp
0x14006bad6  sub     rsp, 50h
0x14006bada  xorps   xmm0, xmm0
0x14006badd  mov     [rbp+Entry], 0
0x14006bae5  mov     rdi, rdx
0x14006bae8  mov     rbx, rcx
0x14006baeb  lea     rdx, [rbp+Enumerator]; Enumerator
0x14006baef  movups  xmmword ptr [rbp-30h], xmm0
0x14006baf3  movups  xmmword ptr [rbp+Enumerator+8], xmm0
0x14006baf7  movups  xmmword ptr [rbp+Enumerator.ChainHead], xmm0
0x14006bafb  call    cs:__imp_RtlInitEnumerationHashTable
0x14006bb02  nop     dword ptr [rax+rax+00h]
0x14006bb07  mov     [rbp+HashTable], rbx
0x14006bb0b  jmp     short loc_14006BB34
0x14006bb0d  mov     rdx, [rbp+Entry]; Entry
0x14006bb11  xor     r8d, r8d; Context
0x14006bb14  mov     rcx, rbx; HashTable
0x14006bb17  call    cs:__imp_RtlRemoveEntryHashTable
0x14006bb1e  nop     dword ptr [rax+rax+00h]
0x14006bb23  test    rdi, rdi
0x14006bb26  jz      short loc_14006BB34
0x14006bb28  lea     rcx, [rbp+Entry]
0x14006bb2c  mov     rax, rdi
0x14006bb2f  call    _guard_dispatch_icall
0x14006bb34  lea     rdx, [rbp+Entry]
0x14006bb38  lea     rcx, [rbp+HashTable]
0x14006bb3c  call    WfpHashtableIteratorGetNext
0x14006bb41  test    eax, eax
0x14006bb43  jnz     short loc_14006BB0D
0x14006bb45  mov     rcx, [rbp+HashTable]; HashTable
0x14006bb49  lea     rdx, [rbp+Enumerator]; Enumerator
0x14006bb4d  call    cs:__imp_RtlEndEnumerationHashTable
0x14006bb54  nop     dword ptr [rax+rax+00h]
0x14006bb59  mov     rcx, rbx; HashTable
0x14006bb5c  call    cs:__imp_RtlDeleteHashTable
0x14006bb63  nop     dword ptr [rax+rax+00h]
0x14006bb68  mov     rbx, [rsp+50h+arg_8]
0x14006bb6d  mov     rdi, [rsp+50h+arg_10]
0x14006bb72  add     rsp, 50h
0x14006bb76  pop     rbp
0x14006bb77  retn
```
