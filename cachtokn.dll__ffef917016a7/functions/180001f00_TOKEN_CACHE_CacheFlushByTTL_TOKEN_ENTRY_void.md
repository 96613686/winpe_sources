# TOKEN_CACHE::CacheFlushByTTL(TOKEN_ENTRY *,void *)

- ea: `0x180001f00`
- end: `0x180001f2f`
- name: `?CacheFlushByTTL@TOKEN_CACHE@@CA?AW4LK_PREDICATE@@PEAVTOKEN_ENTRY@@PEAX@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003010`

## pseudocode

```c
__int64 __fastcall TOKEN_CACHE::CacheFlushByTTL(__int64 *a1)
{
  __int64 v1; // rax
  int v3; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  v3 = 0;
  (*(void (__fastcall **)(__int64 *, int *))(v1 + 32))(a1, &v3);
  return (unsigned int)(v3 != 0) + 2;
}

```

## disassembly

```asm
0x180001f00  sub     rsp, 28h
0x180001f04  mov     rax, [rcx]
0x180001f07  lea     rdx, [rsp+28h+arg_0]
0x180001f0c  mov     [rsp+28h+arg_0], 0
0x180001f14  mov     rax, [rax+20h]
0x180001f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f1d  mov     eax, [rsp+28h+arg_0]
0x180001f21  neg     eax
0x180001f23  sbb     eax, eax
0x180001f25  neg     eax
0x180001f27  add     eax, 2
0x180001f2a  add     rsp, 28h
0x180001f2e  retn
```
