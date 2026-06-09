# W3_CONNECTION::Initialize(void)

- ea: `0x180018b50`
- end: `0x180018c6d`
- name: `?Initialize@W3_CONNECTION@@SAJXZ`
- size: `285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013690`

## callees

- `0x180018b50`
- `0x180019558`
- `0x1800343f0`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180018c2b`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180018c2b`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180018bb0`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180018bb0`

## pseudocode

```c
__int64 W3_CONNECTION::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  CLKRHashTable *v1; // rax
  CLKRHashTable *v2; // rbx
  _DWORD v4[4]; // [rsp+50h] [rbp-28h] BYREF

  W3_CONNECTION::sm_pTraceLog = 0;
  v4[0] = 1;
  v4[1] = 100;
  v4[2] = 128;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( !v0 )
  {
    W3_CONNECTION::sm_pachW3Connections = 0;
    return 2147942408LL;
  }
  W3_CONNECTION::sm_pachW3Connections = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                          v0,
                                          "W3_CONNECTION",
                                          (const struct ALLOC_CACHE_CONFIGURATION *)v4,
                                          1);
  if ( !W3_CONNECTION::sm_pachW3Connections )
    return 2147942408LL;
  v1 = (CLKRHashTable *)operator new(0x48u);
  v2 = v1;
  if ( v1 )
    CLKRHashTable::CLKRHashTable(
      v1,
      "W3_CONNECTION_HASH",
      (unsigned __int64 (*)(const void *))W3_FILE_INFO::GetCacheKey,
      (unsigned int (*)(unsigned __int64))CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_CalcKeyHash,
      (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_EqualKeys,
      (void (*)(const void *, int))CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_AddRefRecord,
      4.0,
      1u,
      0,
      0);
  else
    v2 = 0;
  W3_CONNECTION::sm_pConnectionTable = v2;
  return v2 == 0 ? 0x80070008 : 0;
}

```

## disassembly

```asm
0x180018b50  push    rbx
0x180018b52  sub     rsp, 70h
0x180018b56  mov     rax, cs:__security_cookie
0x180018b5d  xor     rax, rsp
0x180018b60  mov     [rsp+78h+var_18], rax
0x180018b65  mov     ecx, 100h; Size
0x180018b6a  mov     cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x180018b75  mov     [rsp+78h+var_28], 1
0x180018b7d  mov     [rsp+78h+var_24], 64h ; 'd'
0x180018b85  mov     [rsp+78h+var_20], 80h
0x180018b8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018b92  test    rax, rax
0x180018b95  jz      loc_180018C4A
0x180018b9b  mov     r9d, 1
0x180018ba1  lea     r8, [rsp+78h+var_28]
0x180018ba6  lea     rdx, aW3Connection; "W3_CONNECTION"
0x180018bad  mov     rcx, rax
0x180018bb0  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180018bb6  mov     cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x180018bbd  test    rax, rax
0x180018bc0  jz      loc_180018C55
0x180018bc6  mov     ecx, 48h ; 'H'; Size
0x180018bcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018bd0  mov     rbx, rax
0x180018bd3  test    rax, rax
0x180018bd6  jz      short loc_180018C33
0x180018bd8  movsd   xmm0, cs:__real@4010000000000000
0x180018be0  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180018be7  mov     [rsp+78h+var_30], 0
0x180018bec  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180018bf3  mov     [rsp+78h+var_38], 0
0x180018bfb  lea     r8, ?GetCacheKey@W3_FILE_INFO@@UEBAPEAVIHttpCacheKey@@XZ; W3_FILE_INFO::GetCacheKey(void)
0x180018c02  mov     [rsp+78h+var_40], 1
0x180018c0a  lea     rdx, aW3ConnectionHa; "W3_CONNECTION_HASH"
0x180018c11  movsd   [rsp+78h+var_48], xmm0
0x180018c17  mov     rcx, rbx
0x180018c1a  mov     [rsp+78h+var_50], rax
0x180018c1f  lea     rax, ?_EqualKeys@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180018c26  mov     [rsp+78h+var_58], rax
0x180018c2b  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180018c31  jmp     short loc_180018C35
0x180018c33  xor     ebx, ebx
0x180018c35  mov     cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA, rbx; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x180018c3c  neg     rbx
0x180018c3f  sbb     eax, eax
0x180018c41  not     eax
0x180018c43  and     eax, 80070008h
0x180018c48  jmp     short loc_180018C5A
0x180018c4a  mov     cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x180018c55  mov     eax, 80070008h
0x180018c5a  mov     rcx, [rsp+78h+var_18]
0x180018c5f  xor     rcx, rsp; StackCookie
0x180018c62  call    __security_check_cookie
0x180018c67  add     rsp, 70h
0x180018c6b  pop     rbx
0x180018c6c  retn
```
