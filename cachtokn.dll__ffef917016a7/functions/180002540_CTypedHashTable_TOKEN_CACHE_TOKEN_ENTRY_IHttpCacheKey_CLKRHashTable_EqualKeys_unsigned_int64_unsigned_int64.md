# CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x180002540`
- end: `0x18000254c`
- name: `?_EqualKeys@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CA_N_K0@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003010`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_EqualKeys(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
}

```

## disassembly

```asm
0x180002540  mov     rax, [rcx]
0x180002543  mov     rax, [rax+10h]
0x180002547  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
