# PreFetchJobLruCacheHashUrlId(_CRYPTOAPI_BLOB *)

- ea: `0x18000b9a0`
- end: `0x18000b9a7`
- name: `?PreFetchJobLruCacheHashUrlId@@YAKPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `7`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall PreFetchJobLruCacheHashUrlId(struct _CRYPTOAPI_BLOB *a1)
{
  return *(unsigned int *)a1->pbData;
}

```

## disassembly

```asm
0x18000b9a0  mov     rax, [rcx+8]
0x18000b9a4  mov     eax, [rax]
0x18000b9a6  retn
```
