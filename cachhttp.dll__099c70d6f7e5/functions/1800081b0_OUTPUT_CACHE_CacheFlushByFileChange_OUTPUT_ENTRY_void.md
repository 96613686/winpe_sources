# OUTPUT_CACHE::CacheFlushByFileChange(OUTPUT_ENTRY *,void *)

- ea: `0x1800081b0`
- end: `0x1800081e1`
- name: `?CacheFlushByFileChange@OUTPUT_CACHE@@SA?AW4LK_PREDICATE@@PEAVOUTPUT_ENTRY@@PEAX@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800081b0`
- `0x180008bca`

## pseudocode

```c
__int64 __fastcall OUTPUT_CACHE::CacheFlushByFileChange(__int64 a1, const wchar_t *a2)
{
  size_t v2; // r8

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  return 3 - (unsigned int)(wcsncmp_0(a2, *(const wchar_t **)(a1 + 528), v2) != 0);
}

```

## disassembly

```asm
0x1800081b0  sub     rsp, 28h
0x1800081b4  mov     rax, rdx
0x1800081b7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800081bb  inc     r8; MaxCount
0x1800081be  cmp     word ptr [rdx+r8*2], 0
0x1800081c4  jnz     short loc_1800081BB
0x1800081c6  mov     rdx, [rcx+210h]; String2
0x1800081cd  mov     rcx, rax; String1
0x1800081d0  call    wcsncmp_0
0x1800081d5  neg     eax
0x1800081d7  sbb     eax, eax
0x1800081d9  add     eax, 3
0x1800081dc  add     rsp, 28h
0x1800081e0  retn
```
