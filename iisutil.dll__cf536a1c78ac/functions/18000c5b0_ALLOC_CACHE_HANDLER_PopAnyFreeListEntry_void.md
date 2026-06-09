# ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)

- ea: `0x18000c5b0`
- end: `0x18000c601`
- name: `?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ`
- size: `81`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008d30`
- `0x18000c3a0`

## callees

- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000c5e9`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000c5e9`

## pseudocode

```c
PSLIST_ENTRY __fastcall ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(ALLOC_CACHE_HANDLER *this)
{
  _QWORD *v1; // rbx
  PSLIST_ENTRY result; // rax
  unsigned int i; // edi

  v1 = (_QWORD *)*((_QWORD *)this + 3);
  result = 0;
  if ( v1 )
  {
    for ( i = 0; (unsigned __int64)i < v1[2]; ++i )
    {
      if ( !result )
        result = InterlockedPopEntrySList((PSLIST_HEADER)(*v1 + v1[1] * i));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c5b0  push    rbx
0x18000c5b2  sub     rsp, 20h
0x18000c5b6  mov     rbx, [rcx+18h]
0x18000c5ba  xor     eax, eax
0x18000c5bc  test    rbx, rbx
0x18000c5bf  jz      short loc_18000C5D3
0x18000c5c1  mov     [rsp+28h+arg_0], rdi
0x18000c5c6  xor     edi, edi
0x18000c5c8  cmp     [rbx+10h], rax
0x18000c5cc  ja      short loc_18000C5DA
0x18000c5ce  mov     rdi, [rsp+28h+arg_0]
0x18000c5d3  add     rsp, 20h
0x18000c5d7  pop     rbx
0x18000c5d8  retn
0x18000c5da  test    rax, rax
0x18000c5dd  jnz     short loc_18000C5F5
0x18000c5df  mov     ecx, edi
0x18000c5e1  imul    rcx, [rbx+8]
0x18000c5e6  add     rcx, [rbx]; ListHead
0x18000c5e9  call    cs:__imp_InterlockedPopEntrySList
0x18000c5f0  nop     dword ptr [rax+rax+00h]
0x18000c5f5  inc     edi
0x18000c5f7  mov     ecx, edi
0x18000c5f9  cmp     rcx, [rbx+10h]
0x18000c5fd  jb      short loc_18000C5DA
0x18000c5ff  jmp     short loc_18000C5CE
```
