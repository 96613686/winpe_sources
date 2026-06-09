# CIISGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x180001080`
- end: `0x180001094`
- name: `?OnGlobalCacheOperation@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001080`
- `0x1800010a0`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalCacheOperation(void *a1, __int64 *a2)
{
  if ( g_pUriCache )
    return W3_URL_INFO_CACHE::DoCacheOperation(a1, a2);
  else
    return 0;
}

```

## disassembly

```asm
0x180001080  cmp     cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA, 0; W3_URL_INFO_CACHE * g_pUriCache
0x180001088  jz      short loc_180001090
0x18000108a  jmp     ?DoCacheOperation@W3_URL_INFO_CACHE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z; W3_URL_INFO_CACHE::DoCacheOperation(ICacheProvider *)
0x18000108f  retn
0x180001090  xor     eax, eax
0x180001092  jmp     short locret_18000108F
```
