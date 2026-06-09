# CreatePreFetchJobLruCache

- ea: `0x18000fc78`
- end: `0x18000fcd0`
- name: `CreatePreFetchJobLruCache`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d548`

## callees

- `0x18000fc78`

## import_xrefs

- `CRYPT32!I_CryptCreateLruCache` at `0x18000fcc5`
- `CRYPT32!I_CryptCreateLruCache` at `0x18000fcc5`

## pseudocode

```c
__int64 CreatePreFetchJobLruCache()
{
  int v1; // [rsp+20h] [rbp-38h] BYREF
  __int64 v2; // [rsp+24h] [rbp-34h]
  int v3; // [rsp+2Ch] [rbp-2Ch]
  __int64 (__fastcall *v4)(struct _CRYPTOAPI_BLOB *); // [rsp+30h] [rbp-28h]
  __int64 v5; // [rsp+38h] [rbp-20h]
  __int64 v6; // [rsp+40h] [rbp-18h]

  if ( hPreFetchJobLruCache )
    return 1;
  v2 = 0;
  v3 = 0;
  v5 = 0;
  v4 = PreFetchJobLruCacheHashUrlId;
  v6 = 127;
  v1 = 3;
  return I_CryptCreateLruCache(&v1, &hPreFetchJobLruCache);
}

```

## disassembly

```asm
0x18000fc78  sub     rsp, 58h
0x18000fc7c  xor     eax, eax
0x18000fc7e  cmp     cs:?hPreFetchJobLruCache@@3PEAXEA, rax; void * hPreFetchJobLruCache
0x18000fc85  jz      short loc_18000FC8E
0x18000fc87  mov     eax, 1
0x18000fc8c  jmp     short loc_18000FCCB
0x18000fc8e  mov     [rsp+58h+var_34], rax
0x18000fc93  lea     rdx, ?hPreFetchJobLruCache@@3PEAXEA; void * hPreFetchJobLruCache
0x18000fc9a  mov     [rsp+58h+var_2C], eax
0x18000fc9e  lea     rcx, [rsp+58h+var_38]
0x18000fca3  mov     [rsp+58h+var_20], rax
0x18000fca8  lea     rax, ?PreFetchJobLruCacheHashUrlId@@YAKPEAU_CRYPTOAPI_BLOB@@@Z; PreFetchJobLruCacheHashUrlId(_CRYPTOAPI_BLOB *)
0x18000fcaf  mov     [rsp+58h+var_28], rax
0x18000fcb4  mov     [rsp+58h+var_18], 7Fh
0x18000fcbd  mov     [rsp+58h+var_38], 3
0x18000fcc5  call    cs:__imp_I_CryptCreateLruCache
0x18000fccb  add     rsp, 58h
0x18000fccf  retn
```
