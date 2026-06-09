# DestroyClientSideSslProvCache(void)

- ea: `0x14000ab4c`
- end: `0x14000abb9`
- name: `?DestroyClientSideSslProvCache@@YAJXZ`
- size: `109`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140021cfc`

## callees

- `0x14000aaac`
- `0x14000ab4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab74`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000ab5c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000ab5c`

## pseudocode

```c
__int64 DestroyClientSideSslProvCache(void)
{
  if ( g_pSslProvCacheRWLock )
  {
    ExDeleteResourceLite(g_pSslProvCacheRWLock);
    ExFreePoolWithTag(g_pSslProvCacheRWLock, 0x436C7353u);
  }
  DestroyCachedProviderArray(&unk_140019100, &dword_1400190F8);
  g_pSslProvCacheRWLock = 0;
  DestroyCachedProviderArray(&g_rgCachedPagedSslProvs, &g_cCachedPagedSslProvs);
  return 0;
}

```

## disassembly

```asm
0x14000ab4c  sub     rsp, 28h
0x14000ab50  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA; Resource
0x14000ab57  test    rcx, rcx
0x14000ab5a  jz      short loc_14000AB80
0x14000ab5c  call    cs:__imp_ExDeleteResourceLite
0x14000ab63  nop     dword ptr [rax+rax+00h]
0x14000ab68  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA; P
0x14000ab6f  mov     edx, 436C7353h; Tag
0x14000ab74  call    cs:__imp_ExFreePoolWithTag
0x14000ab7b  nop     dword ptr [rax+rax+00h]
0x14000ab80  lea     rdx, dword_1400190F8
0x14000ab87  lea     rcx, unk_140019100
0x14000ab8e  call    DestroyCachedProviderArray
0x14000ab93  lea     rdx, ?g_cCachedPagedSslProvs@@3KA; ulong g_cCachedPagedSslProvs
0x14000ab9a  mov     cs:?g_pSslProvCacheRWLock@@3PEAU_ERESOURCE@@EA, 0; _ERESOURCE * g_pSslProvCacheRWLock
0x14000aba5  lea     rcx, ?g_rgCachedPagedSslProvs@@3PAUCACHED_SSL_PROVIDER@@A; CACHED_SSL_PROVIDER near * g_rgCachedPagedSslProvs
0x14000abac  call    DestroyCachedProviderArray
0x14000abb1  xor     eax, eax
0x14000abb3  add     rsp, 28h
0x14000abb7  retn
```
