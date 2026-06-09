# W3_CONNECTION::Initialize(void)

- ea: `0x18001a07c`
- end: `0x18001a1a6`
- name: `?Initialize@W3_CONNECTION@@SAJXZ`
- size: `298`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800147d0`

## callees

- `0x18001a07c`
- `0x18001ab30`
- `0x180037790`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001a15d`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001a15d`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001a0dc`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001a0dc`

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
0x18001a07c  push    rbx
0x18001a07e  sub     rsp, 70h
0x18001a082  mov     rax, cs:__security_cookie
0x18001a089  xor     rax, rsp
0x18001a08c  mov     [rsp+78h+var_18], rax
0x18001a091  mov     ecx, 100h; Size
0x18001a096  mov     cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x18001a0a1  mov     [rsp+78h+var_28], 1
0x18001a0a9  mov     [rsp+78h+var_24], 64h ; 'd'
0x18001a0b1  mov     [rsp+78h+var_20], 80h
0x18001a0b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a0be  test    rax, rax
0x18001a0c1  jz      loc_18001A182
0x18001a0c7  mov     r9d, 1
0x18001a0cd  lea     r8, [rsp+78h+var_28]
0x18001a0d2  lea     rdx, aW3Connection; "W3_CONNECTION"
0x18001a0d9  mov     rcx, rax
0x18001a0dc  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18001a0e3  nop     dword ptr [rax+rax+00h]
0x18001a0e8  mov     cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x18001a0ef  test    rax, rax
0x18001a0f2  jz      loc_18001A18D
0x18001a0f8  mov     ecx, 48h ; 'H'; Size
0x18001a0fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a102  mov     rbx, rax
0x18001a105  test    rax, rax
0x18001a108  jz      short loc_18001A16B
0x18001a10a  movsd   xmm0, cs:__real@4010000000000000
0x18001a112  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18001a119  mov     [rsp+78h+var_30], 0
0x18001a11e  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18001a125  mov     [rsp+78h+var_38], 0
0x18001a12d  lea     r8, ?GetCacheKey@W3_FILE_INFO@@UEBAPEAVIHttpCacheKey@@XZ; W3_FILE_INFO::GetCacheKey(void)
0x18001a134  mov     [rsp+78h+var_40], 1
0x18001a13c  lea     rdx, aW3ConnectionHa; "W3_CONNECTION_HASH"
0x18001a143  movsd   [rsp+78h+var_48], xmm0
0x18001a149  mov     rcx, rbx
0x18001a14c  mov     [rsp+78h+var_50], rax
0x18001a151  lea     rax, ?_EqualKeys@?$CTypedHashTable@VW3_CONNECTION_HASH@@VW3_CONNECTION@@PEA_KVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<W3_CONNECTION_HASH,W3_CONNECTION,unsigned __int64 *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18001a158  mov     [rsp+78h+var_58], rax
0x18001a15d  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001a164  nop     dword ptr [rax+rax+00h]
0x18001a169  jmp     short loc_18001A16D
0x18001a16b  xor     ebx, ebx
0x18001a16d  mov     cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA, rbx; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x18001a174  neg     rbx
0x18001a177  sbb     eax, eax
0x18001a179  not     eax
0x18001a17b  and     eax, 80070008h
0x18001a180  jmp     short loc_18001A192
0x18001a182  mov     cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x18001a18d  mov     eax, 80070008h
0x18001a192  mov     rcx, [rsp+78h+var_18]
0x18001a197  xor     rcx, rsp; StackCookie
0x18001a19a  call    __security_check_cookie
0x18001a19f  add     rsp, 70h
0x18001a1a3  pop     rbx
0x18001a1a4  retn
```
