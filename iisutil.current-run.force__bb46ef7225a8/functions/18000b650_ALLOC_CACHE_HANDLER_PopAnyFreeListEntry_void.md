# ALLOC_CACHE_HANDLER::PopAnyFreeListEntry(void)

- ea: `0x18000b650`
- end: `0x18000b69a`
- name: `?PopAnyFreeListEntry@ALLOC_CACHE_HANDLER@@AEAAPEAXXZ`
- size: `74`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008000`
- `0x18000b450`

## callees

- `0x18000b650`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000b688`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000b688`

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
0x18000b650  push    rbx
0x18000b652  sub     rsp, 20h
0x18000b656  mov     rbx, [rcx+18h]
0x18000b65a  xor     eax, eax
0x18000b65c  test    rbx, rbx
0x18000b65f  jz      short loc_18000B673
0x18000b661  mov     [rsp+28h+arg_0], rdi
0x18000b666  xor     edi, edi
0x18000b668  cmp     [rbx+10h], rax
0x18000b66c  ja      short loc_18000B679
0x18000b66e  mov     rdi, [rsp+28h+arg_0]
0x18000b673  add     rsp, 20h
0x18000b677  pop     rbx
0x18000b678  retn
0x18000b679  test    rax, rax
0x18000b67c  jnz     short loc_18000B68E
0x18000b67e  mov     ecx, edi
0x18000b680  imul    rcx, [rbx+8]
0x18000b685  add     rcx, [rbx]; ListHead
0x18000b688  call    cs:__imp_InterlockedPopEntrySList
0x18000b68e  inc     edi
0x18000b690  mov     ecx, edi
0x18000b692  cmp     rcx, [rbx+10h]
0x18000b696  jb      short loc_18000B679
0x18000b698  jmp     short loc_18000B66E
```
