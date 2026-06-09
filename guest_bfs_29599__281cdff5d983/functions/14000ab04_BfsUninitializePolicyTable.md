# BfsUninitializePolicyTable

- ea: `0x14000ab04`
- end: `0x14000abd9`
- name: `BfsUninitializePolicyTable`
- size: `213`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001e020`
- `0x14001f078`

## callees

- `0x1400061d0`
- `0x14000ab04`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14000abac`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000abac`
- `ntoskrnl!ExDeleteTimer` at `0x14000ab3f`
- `ntoskrnl!ExDeleteTimer` at `0x14000ab3f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000ab61`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14000ab61`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000ab82`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14000ab82`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000ab9c`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14000ab9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000abbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000abbe`

## pseudocode

```c
void __fastcall BfsUninitializePolicyTable(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v5; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v6; // rax
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+30h] [rbp-38h]
  _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+38h] [rbp-30h] BYREF

  v4 = *(_QWORD *)(a1 + 32);
  v8 = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  v7 = 0;
  if ( v4 )
  {
    LOBYTE(a3) = 1;
    LOBYTE(a2) = 1;
    ((void (__fastcall *)(__int64, __int64, __int64, __int128 *))ExDeleteTimer)(v4, a2, a3, &v7);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v5 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8);
  if ( v5 )
  {
    RtlInitEnumerationHashTable(v5, &Enumerator);
    while ( 1 )
    {
      v6 = RtlEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), &Enumerator);
      if ( !v6 )
        break;
      BfsDereferencePolicyEntryEx(v6);
    }
    RtlEndEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), &Enumerator);
    RtlDeleteHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8));
    ExFreePoolWithTag(*(PVOID *)(a1 + 8), 0);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x14000ab04  push    rbx
0x14000ab06  sub     rsp, 60h
0x14000ab0a  xor     eax, eax
0x14000ab0c  xorps   xmm0, xmm0
0x14000ab0f  mov     rbx, rcx
0x14000ab12  mov     qword ptr [rsp+68h+Enumerator.BucketIndex], rax
0x14000ab17  mov     rcx, [rcx+20h]
0x14000ab1b  mov     [rsp+68h+var_38], rax
0x14000ab20  movups  xmmword ptr [rsp+68h+Enumerator], xmm0
0x14000ab25  movups  xmmword ptr [rsp+68h+Enumerator+10h], xmm0
0x14000ab2a  movups  [rsp+68h+var_48], xmm0
0x14000ab2f  test    rcx, rcx
0x14000ab32  jz      short loc_14000AB53
0x14000ab34  mov     r8b, 1
0x14000ab37  lea     r9, [rsp+68h+var_48]
0x14000ab3c  mov     dl, r8b
0x14000ab3f  call    cs:__imp_ExDeleteTimer
0x14000ab46  nop     dword ptr [rax+rax+00h]
0x14000ab4b  mov     qword ptr [rbx+20h], 0
0x14000ab53  mov     rcx, [rbx+8]; HashTable
0x14000ab57  test    rcx, rcx
0x14000ab5a  jz      short loc_14000ABD2
0x14000ab5c  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x14000ab61  call    cs:__imp_RtlInitEnumerationHashTable
0x14000ab68  nop     dword ptr [rax+rax+00h]
0x14000ab6d  jmp     short loc_14000AB79
0x14000ab6f  mov     dl, 1
0x14000ab71  mov     rcx, rax; P
0x14000ab74  call    BfsDereferencePolicyEntryEx
0x14000ab79  mov     rcx, [rbx+8]; HashTable
0x14000ab7d  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x14000ab82  call    cs:__imp_RtlEnumerateEntryHashTable
0x14000ab89  nop     dword ptr [rax+rax+00h]
0x14000ab8e  test    rax, rax
0x14000ab91  jnz     short loc_14000AB6F
0x14000ab93  mov     rcx, [rbx+8]; HashTable
0x14000ab97  lea     rdx, [rsp+68h+Enumerator]; Enumerator
0x14000ab9c  call    cs:__imp_RtlEndEnumerationHashTable
0x14000aba3  nop     dword ptr [rax+rax+00h]
0x14000aba8  mov     rcx, [rbx+8]; HashTable
0x14000abac  call    cs:__imp_RtlDeleteHashTable
0x14000abb3  nop     dword ptr [rax+rax+00h]
0x14000abb8  mov     rcx, [rbx+8]; P
0x14000abbc  xor     edx, edx; Tag
0x14000abbe  call    cs:__imp_ExFreePoolWithTag
0x14000abc5  nop     dword ptr [rax+rax+00h]
0x14000abca  mov     qword ptr [rbx+8], 0
0x14000abd2  add     rsp, 60h
0x14000abd6  pop     rbx
0x14000abd7  retn
```
