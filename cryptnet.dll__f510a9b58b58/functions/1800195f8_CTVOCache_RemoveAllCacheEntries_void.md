# CTVOCache::RemoveAllCacheEntries(void)

- ea: `0x1800195f8`
- end: `0x180019614`
- name: `?RemoveAllCacheEntries@CTVOCache@@QEAAXXZ`
- size: `28`
- prototype: `void __fastcall(CTVOCache *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019584`
- `0x18001dd5c`

## callees

- `0x1800195f8`

## import_xrefs

- `CRYPT32!I_CryptFlushLruCache` at `0x180019609`
- `CRYPT32!I_CryptFlushLruCache` at `0x180019609`

## pseudocode

```c
void __fastcall CTVOCache::RemoveAllCacheEntries(CTVOCache *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    I_CryptFlushLruCache(v1, 0, 0);
}

```

## disassembly

```asm
0x1800195f8  sub     rsp, 28h
0x1800195fc  mov     rcx, [rcx]
0x1800195ff  test    rcx, rcx
0x180019602  jz      short loc_18001960F
0x180019604  xor     r8d, r8d
0x180019607  xor     edx, edx
0x180019609  call    cs:__imp_I_CryptFlushLruCache
0x18001960f  add     rsp, 28h
0x180019613  retn
```
