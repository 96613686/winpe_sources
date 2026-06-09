# UL_RESPONSE_CACHE::CacheFlushByFileChange(UL_RESPONSE_CACHE_ENTRY *,void *)

- ea: `0x1800063f0`
- end: `0x180006421`
- name: `?CacheFlushByFileChange@UL_RESPONSE_CACHE@@SA?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z`
- size: `49`
- prototype: `static enum LK_PREDICATE __high(struct UL_RESPONSE_CACHE_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800063f0`
- `0x180008bca`

## pseudocode

```c
__int64 __fastcall UL_RESPONSE_CACHE::CacheFlushByFileChange(__int64 a1, const wchar_t *a2)
{
  size_t v2; // r8

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  return 3 - (unsigned int)(wcsncmp_0(a2, *(const wchar_t **)(a1 + 416), v2) != 0);
}

```

## disassembly

```asm
0x1800063f0  sub     rsp, 28h
0x1800063f4  mov     rax, rdx
0x1800063f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800063fb  inc     r8; MaxCount
0x1800063fe  cmp     word ptr [rdx+r8*2], 0
0x180006404  jnz     short loc_1800063FB
0x180006406  mov     rdx, [rcx+1A0h]; String2
0x18000640d  mov     rcx, rax; String1
0x180006410  call    wcsncmp_0
0x180006415  neg     eax
0x180006417  sbb     eax, eax
0x180006419  add     eax, 3
0x18000641c  add     rsp, 28h
0x180006420  retn
```
