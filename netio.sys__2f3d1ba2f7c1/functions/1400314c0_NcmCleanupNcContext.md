# NcmCleanupNcContext

- ea: `0x1400314c0`
- end: `0x140031596`
- name: `NcmCleanupNcContext`
- size: `214`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140031270`

## callees

- `0x1400314c0`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140031520`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140031550`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140031520`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140031550`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031531`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031561`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031572`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031531`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031561`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031572`

## pseudocode

```c
void __fastcall NcmCleanupNcContext(volatile signed __int32 *P)
{
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v2; // rsi
  _QWORD *v3; // rdx
  PVOID *v4; // rax
  struct _LIST_ENTRY *Blink; // rdi

  _InterlockedDecrement(P + 58);
  v2 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)*((_QWORD *)P + 6);
  *((_QWORD *)P + 6) = 0;
  v3 = *(_QWORD **)P;
  if ( *(volatile signed __int32 **)(*(_QWORD *)P + 8LL) != P || (v4 = (PVOID *)*((_QWORD *)P + 1), *v4 != P) )
    __fastfail(3u);
  *v4 = v3;
  v3[1] = v4;
  if ( (ULONG_PTR *)v2[1].Signature == &v2[1].Signature )
  {
    Blink = v2[1].Linkage.Blink;
    RtlRemoveEntryHashTable(&stru_14009B030, v2, 0);
    ExFreePoolWithTag(v2, 0);
    if ( LODWORD(Blink[1].Blink)-- == 1 )
    {
      RtlRemoveEntryHashTable(&stru_14009B008, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Blink, 0);
      ExFreePoolWithTag(Blink, 0);
    }
  }
  ExFreePoolWithTag((PVOID)P, 0);
}

```

## disassembly

```asm
0x1400314c0  mov     [rsp+arg_8], rbx
0x1400314c5  mov     [rsp+arg_10], rsi
0x1400314ca  push    rdi
0x1400314cb  sub     rsp, 20h
0x1400314cf  lock dec dword ptr [rcx+0E8h]
0x1400314d6  mov     rbx, rcx
0x1400314d9  mov     rsi, [rcx+30h]
0x1400314dd  mov     qword ptr [rcx+30h], 0
0x1400314e5  mov     rdx, [rcx]
0x1400314e8  cmp     [rdx+8], rcx
0x1400314ec  jnz     loc_14003158F
0x1400314f2  mov     rax, [rcx+8]
0x1400314f6  cmp     [rax], rcx
0x1400314f9  jnz     loc_14003158F
0x1400314ff  mov     [rax], rdx
0x140031502  mov     [rdx+8], rax
0x140031506  lea     rax, [rsi+28h]
0x14003150a  cmp     [rax], rax
0x14003150d  jnz     short loc_14003156D
0x14003150f  mov     rdi, [rsi+20h]
0x140031513  lea     rcx, stru_14009B030; HashTable
0x14003151a  xor     r8d, r8d; Context
0x14003151d  mov     rdx, rsi; Entry
0x140031520  call    cs:__imp_RtlRemoveEntryHashTable
0x140031527  nop     dword ptr [rax+rax+00h]
0x14003152c  xor     edx, edx; Tag
0x14003152e  mov     rcx, rsi; P
0x140031531  call    cs:__imp_ExFreePoolWithTag
0x140031538  nop     dword ptr [rax+rax+00h]
0x14003153d  sub     dword ptr [rdi+18h], 1
0x140031541  jnz     short loc_14003156D
0x140031543  xor     r8d, r8d; Context
0x140031546  lea     rcx, stru_14009B008; HashTable
0x14003154d  mov     rdx, rdi; Entry
0x140031550  call    cs:__imp_RtlRemoveEntryHashTable
0x140031557  nop     dword ptr [rax+rax+00h]
0x14003155c  xor     edx, edx; Tag
0x14003155e  mov     rcx, rdi; P
0x140031561  call    cs:__imp_ExFreePoolWithTag
0x140031568  nop     dword ptr [rax+rax+00h]
0x14003156d  xor     edx, edx; Tag
0x14003156f  mov     rcx, rbx; P
0x140031572  call    cs:__imp_ExFreePoolWithTag
0x140031579  nop     dword ptr [rax+rax+00h]
0x14003157e  mov     rbx, [rsp+28h+arg_8]
0x140031583  mov     rsi, [rsp+28h+arg_10]
0x140031588  add     rsp, 20h
0x14003158c  pop     rdi
0x14003158d  retn
0x14003158f  mov     ecx, 3
0x140031594  int     29h; Win8: RtlFailFast(ecx)
```
