# CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_ExtractKey(void const *)

- ea: `0x180002520`
- end: `0x18000252b`
- name: `?_ExtractKey@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CA?B_KPEBX@Z`
- size: `11`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD))`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003010`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_ExtractKey(
        __int64 (__fastcall ***a1)(_QWORD))
{
  return (**a1)(a1);
}

```

## disassembly

```asm
0x180002520  mov     rax, [rcx]
0x180002523  mov     rax, [rax]
0x180002526  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
