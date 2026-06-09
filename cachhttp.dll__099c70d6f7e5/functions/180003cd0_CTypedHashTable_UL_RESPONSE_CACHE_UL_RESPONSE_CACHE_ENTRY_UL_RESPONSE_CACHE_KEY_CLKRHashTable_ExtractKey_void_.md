# CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_ExtractKey(void const *)

- ea: `0x180003cd0`
- end: `0x180003cd5`
- name: `?_ExtractKey@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_ExtractKey(
        __int64 a1)
{
  return a1 + 16;
}

```

## disassembly

```asm
0x180003cd0  lea     rax, [rcx+10h]
0x180003cd4  retn
```
