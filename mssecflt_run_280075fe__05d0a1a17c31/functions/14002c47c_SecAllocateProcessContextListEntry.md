# SecAllocateProcessContextListEntry

- ea: `0x14002c47c`
- end: `0x14002c4f4`
- name: `SecAllocateProcessContextListEntry`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d504`

## callees

- `0x140011610`
- `0x14002c47c`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002c49d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14002c49d`

## pseudocode

```c
__int64 __fastcall SecAllocateProcessContextListEntry(PSLIST_ENTRY *a1)
{
  char *v2; // rbx
  union _SLIST_HEADER *v3; // rcx
  PSLIST_ENTRY v4; // rax
  __int64 v5; // rdx
  __int64 (__fastcall *v6)(__int64, __int64, __int64); // rax
  __int64 v7; // r8
  __int64 v8; // rcx

  v2 = (char *)SecProcessTable + 192;
  v3 = (union _SLIST_HEADER *)((char *)SecProcessTable + 192);
  ++*((_DWORD *)SecProcessTable + 53);
  v4 = ExpInterlockedPopEntrySList(v3);
  if ( !v4 )
  {
    v5 = *((unsigned int *)v2 + 11);
    v6 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v2 + 6);
    v7 = *((unsigned int *)v2 + 10);
    v8 = *((unsigned int *)v2 + 9);
    ++*((_DWORD *)v2 + 6);
    v4 = (PSLIST_ENTRY)v6(v8, v5, v7);
    if ( !v4 )
      return 3221225626LL;
  }
  *v4 = 0;
  v4[1].Next = 0;
  LODWORD(v4->Next) = 1632775;
  *a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x14002c47c  mov     [rsp+arg_0], rbx
0x14002c481  push    rdi
0x14002c482  sub     rsp, 20h
0x14002c486  mov     rbx, cs:SecProcessTable
0x14002c48d  mov     rdi, rcx
0x14002c490  add     rbx, 0C0h
0x14002c497  mov     rcx, rbx; ListHead
0x14002c49a  inc     dword ptr [rbx+14h]
0x14002c49d  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002c4a4  nop     dword ptr [rax+rax+00h]
0x14002c4a9  test    rax, rax
0x14002c4ac  jnz     short loc_14002C4D1
0x14002c4ae  mov     edx, [rbx+2Ch]
0x14002c4b1  mov     rax, [rbx+30h]
0x14002c4b5  mov     r8d, [rbx+28h]
0x14002c4b9  mov     ecx, [rbx+24h]
0x14002c4bc  inc     dword ptr [rbx+18h]
0x14002c4bf  call    cs:__guard_dispatch_icall_fptr
0x14002c4c5  test    rax, rax
0x14002c4c8  jnz     short loc_14002C4D1
0x14002c4ca  mov     eax, 0C000009Ah
0x14002c4cf  jmp     short loc_14002C4E8
0x14002c4d1  xor     ecx, ecx
0x14002c4d3  xorps   xmm0, xmm0
0x14002c4d6  movups  xmmword ptr [rax], xmm0
0x14002c4d9  mov     [rax+10h], rcx
0x14002c4dd  mov     dword ptr [rax], 18EA07h
0x14002c4e3  mov     [rdi], rax
0x14002c4e6  xor     eax, eax
0x14002c4e8  mov     rbx, [rsp+28h+arg_0]
0x14002c4ed  add     rsp, 20h
0x14002c4f1  pop     rdi
0x14002c4f2  retn
```
