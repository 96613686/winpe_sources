# CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_Pred(void const *,void *)

- ea: `0x180002560`
- end: `0x18000256c`
- name: `?_Pred@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003010`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_Pred(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, _QWORD))a2)(a1, *(_QWORD *)(a2 + 16));
}

```

## disassembly

```asm
0x180002560  mov     rax, [rdx]
0x180002563  mov     rdx, [rdx+10h]
0x180002567  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
