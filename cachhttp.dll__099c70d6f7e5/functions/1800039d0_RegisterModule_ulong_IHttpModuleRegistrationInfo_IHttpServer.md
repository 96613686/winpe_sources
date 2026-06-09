# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x1800039d0`
- end: `0x180003c9d`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x1800039d0`
- `0x18000516c`
- `0x1800052b4`
- `0x1800052dc`
- `0x180005314`
- `0x18000563c`
- `0x180005748`
- `0x180005a0c`
- `0x180005a4c`
- `0x1800063bc`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c0a`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003b7b`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003b7b`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x180003bb9`
- `iisutil!??0TREE_HASH_TABLE@@QEAA@H@Z` at `0x180003bb9`

## string_xrefs

- `0x180003b5a`: `UL_RESPONSE_CACHE`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 v3; // rax
  _QWORD *v5; // rax
  __int64 result; // rax
  _QWORD *v7; // rax
  int v8; // edi
  CLKRHashTable *v9; // rax
  unsigned int v10; // edx
  CLKRHashTable *v11; // rbx
  signed int v12; // ebx
  VARY_BY_CACHE *v13; // rcx
  unsigned int v14; // edx
  unsigned int v15; // edx
  UL_RESPONSE_CACHE *v16; // rcx
  TREE_HASH_TABLE *v17; // rax
  TREE_HASH_TABLE *v18; // rbx
  VARY_BY_CACHE *v19; // rcx
  OUTPUT_CACHE *v20; // rax
  _QWORD *v21; // rax

  v3 = *(_QWORD *)a2;
  g_pGlobalInfo = a3;
  g_pModuleId = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(v3 + 8))(a2);
  v5 = operator new(8u);
  if ( !v5 )
    return 2147942408LL;
  *v5 = &CIISGlobalModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
             a2,
             v5,
             196);
  if ( (int)result >= 0 )
  {
    v7 = operator new(0x10u);
    if ( !v7 )
      return 2147942408LL;
    *v7 = &CIISModuleFactory::`vftable';
    v7[1] = &CIISHttpModule::`vftable';
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
               a2,
               v7,
               134218249,
               0);
    if ( (int)result >= 0 )
    {
      v8 = 0;
      v9 = (CLKRHashTable *)operator new(0x50u);
      v11 = v9;
      if ( v9 )
      {
        CLKRHashTable::CLKRHashTable(
          v9,
          "UL_RESPONSE_CACHE",
          (unsigned __int64 (*)(const void *))CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_ExtractKey,
          (unsigned int (*)(unsigned __int64))CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash,
          (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_EqualKeys,
          (void (*)(const void *, int))CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_AddRefRecord,
          4.0,
          1u,
          0,
          0);
        *((_QWORD *)v11 + 9) = 0;
        g_pUlCache = v11;
        v12 = UL_RESPONSE_CACHE::Initialize(v16);
        if ( v12 < 0 )
          goto LABEL_10;
        v17 = (TREE_HASH_TABLE *)operator new(0x30u);
        v18 = v17;
        if ( v17 )
        {
          TREE_HASH_TABLE::TREE_HASH_TABLE(v17, 1);
          *((_QWORD *)v18 + 5) = 0;
          *(_QWORD *)v18 = &VARY_BY_CACHE::`vftable';
          g_pVaryByCache = v18;
          v12 = VARY_BY_CACHE::Initialize(v19);
          if ( v12 < 0 )
            goto LABEL_10;
          v20 = (OUTPUT_CACHE *)operator new(0x80u);
          if ( v20 )
          {
            g_pOutputCache = OUTPUT_CACHE::OUTPUT_CACHE(v20);
            if ( g_pOutputCache )
            {
              RESPONSE_ENTRY::sm_hHeap = GetProcessHeap();
              v21 = operator new(8u);
              if ( v21 )
              {
                g_pMonitorStoredContext = v21;
                *v21 = &MonitorStoredContext::`vftable';
                return 0;
              }
              g_pMonitorStoredContext = 0;
              v8 = 1;
            }
          }
          else
          {
            g_pOutputCache = 0;
          }
        }
        else
        {
          g_pVaryByCache = 0;
        }
      }
      else
      {
        g_pUlCache = 0;
      }
      v12 = -2147024888;
LABEL_10:
      if ( g_pMonitorStoredContext )
      {
        operator delete(g_pMonitorStoredContext);
        g_pMonitorStoredContext = 0;
      }
      if ( v8 )
        RESPONSE_ENTRY::sm_hHeap = 0;
      v13 = (VARY_BY_CACHE *)g_pOutputCache;
      if ( g_pOutputCache )
      {
        OUTPUT_CACHE::`scalar deleting destructor'((OUTPUT_CACHE *)g_pOutputCache, v10);
        g_pOutputCache = 0;
      }
      if ( g_pVaryByCache )
      {
        VARY_BY_CACHE::Terminate(v13);
        v13 = (VARY_BY_CACHE *)g_pVaryByCache;
        if ( g_pVaryByCache )
          VARY_BY_CACHE::`scalar deleting destructor'((VARY_BY_CACHE *)g_pVaryByCache, v14);
        g_pVaryByCache = 0;
      }
      if ( g_pUlCache )
      {
        UL_RESPONSE_CACHE::Terminate(v13);
        if ( g_pUlCache )
          OUTPUT_CACHE::`scalar deleting destructor'((OUTPUT_CACHE *)g_pUlCache, v15);
        g_pUlCache = 0;
      }
      return (unsigned int)v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800039d0  mov     [rsp+arg_0], rbx
0x1800039d5  mov     [rsp+arg_8], rsi
0x1800039da  push    rdi
0x1800039db  sub     rsp, 50h
0x1800039df  mov     rax, [rdx]
0x1800039e2  mov     rcx, rdx
0x1800039e5  mov     rbx, rdx
0x1800039e8  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, r8; IHttpServer * g_pGlobalInfo
0x1800039ef  mov     rax, [rax+8]
0x1800039f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f8  mov     ecx, 8; Size
0x1800039fd  mov     cs:?g_pModuleId@@3PEAXEA, rax; void * g_pModuleId
0x180003a04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a09  xor     esi, esi
0x180003a0b  mov     rdx, rax
0x180003a0e  test    rax, rax
0x180003a11  jnz     short loc_180003A28
0x180003a13  mov     eax, 80070008h
0x180003a18  mov     rbx, [rsp+58h+arg_0]
0x180003a1d  mov     rsi, [rsp+58h+arg_8]
0x180003a22  add     rsp, 50h
0x180003a26  pop     rdi
0x180003a27  retn
0x180003a28  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180003a2f  mov     r8d, 0C4h
0x180003a35  mov     [rdx], rax
0x180003a38  mov     rcx, [rbx]
0x180003a3b  mov     rax, [rcx+18h]
0x180003a3f  mov     rcx, rbx
0x180003a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a47  test    eax, eax
0x180003a49  js      short loc_180003A18
0x180003a4b  mov     ecx, 10h; Size
0x180003a50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a55  mov     rdx, rax
0x180003a58  test    rax, rax
0x180003a5b  jz      short loc_180003A13
0x180003a5d  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180003a64  xor     r9d, r9d
0x180003a67  mov     [rdx], rax
0x180003a6a  mov     r8d, 8000209h
0x180003a70  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180003a77  mov     [rdx+8], rax
0x180003a7b  mov     rcx, [rbx]
0x180003a7e  mov     rax, [rcx+10h]
0x180003a82  mov     rcx, rbx
0x180003a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a8a  test    eax, eax
0x180003a8c  js      short loc_180003A18
0x180003a8e  mov     ecx, 50h ; 'P'; Size
0x180003a93  mov     edi, esi
0x180003a95  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a9a  mov     rbx, rax
0x180003a9d  test    rax, rax
0x180003aa0  jnz     loc_180003B2C
0x180003aa6  mov     cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA, rsi; UL_RESPONSE_CACHE * g_pUlCache
0x180003aad  mov     ebx, 80070008h
0x180003ab2  mov     rcx, cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA; Block
0x180003ab9  test    rcx, rcx
0x180003abc  jnz     loc_180003C35
0x180003ac2  test    edi, edi
0x180003ac4  jnz     loc_180003C76
0x180003aca  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; this
0x180003ad1  test    rcx, rcx
0x180003ad4  jnz     loc_180003C82
0x180003ada  cmp     cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA, rsi; VARY_BY_CACHE * g_pVaryByCache
0x180003ae1  jz      short loc_180003AFF
0x180003ae3  call    ?Terminate@VARY_BY_CACHE@@QEAAXXZ; VARY_BY_CACHE::Terminate(void)
0x180003ae8  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; this
0x180003aef  test    rcx, rcx
0x180003af2  jnz     loc_180003C93
0x180003af8  mov     cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA, rsi; VARY_BY_CACHE * g_pVaryByCache
0x180003aff  cmp     cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA, rsi; UL_RESPONSE_CACHE * g_pUlCache
0x180003b06  jz      short loc_180003B25
0x180003b08  call    ?Terminate@UL_RESPONSE_CACHE@@QEAAXXZ; UL_RESPONSE_CACHE::Terminate(void)
0x180003b0d  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; this
0x180003b14  test    rcx, rcx
0x180003b17  jz      short loc_180003B1E
0x180003b19  call    ??_GOUTPUT_CACHE@@QEAAPEAXI@Z; OUTPUT_CACHE::`scalar deleting destructor'(uint)
0x180003b1e  mov     cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA, rsi; UL_RESPONSE_CACHE * g_pUlCache
0x180003b25  mov     eax, ebx
0x180003b27  jmp     loc_180003A18
0x180003b2c  movsd   xmm0, cs:__real@4010000000000000
0x180003b34  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180003b3b  mov     [rsp+58h+var_10], sil
0x180003b40  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180003b47  mov     [rsp+58h+var_18], esi
0x180003b4b  lea     r8, ?_ExtractKey@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_ExtractKey(void const *)
0x180003b52  mov     [rsp+58h+var_20], 1
0x180003b5a  lea     rdx, aUlResponseCach_0; "UL_RESPONSE_CACHE"
0x180003b61  movsd   [rsp+58h+var_28], xmm0
0x180003b67  mov     rcx, rbx
0x180003b6a  mov     [rsp+58h+var_30], rax
0x180003b6f  lea     rax, ?_EqualKeys@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180003b76  mov     [rsp+58h+var_38], rax
0x180003b7b  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180003b81  mov     [rbx+48h], rsi
0x180003b85  mov     cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA, rbx; UL_RESPONSE_CACHE * g_pUlCache
0x180003b8c  call    ?Initialize@UL_RESPONSE_CACHE@@QEAAJXZ; UL_RESPONSE_CACHE::Initialize(void)
0x180003b91  mov     ebx, eax
0x180003b93  test    eax, eax
0x180003b95  js      loc_180003AB2
0x180003b9b  mov     ecx, 30h ; '0'; Size
0x180003ba0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ba5  mov     rbx, rax
0x180003ba8  test    rax, rax
0x180003bab  jz      loc_180003C6A
0x180003bb1  mov     edx, 1
0x180003bb6  mov     rcx, rax
0x180003bb9  call    cs:__imp_??0TREE_HASH_TABLE@@QEAA@H@Z; TREE_HASH_TABLE::TREE_HASH_TABLE(int)
0x180003bbf  lea     rax, ??_7VARY_BY_CACHE@@6B@; const VARY_BY_CACHE::`vftable'
0x180003bc6  mov     [rbx+28h], rsi
0x180003bca  mov     [rbx], rax
0x180003bcd  mov     cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA, rbx; VARY_BY_CACHE * g_pVaryByCache
0x180003bd4  call    ?Initialize@VARY_BY_CACHE@@QEAAJXZ; VARY_BY_CACHE::Initialize(void)
0x180003bd9  mov     ebx, eax
0x180003bdb  test    eax, eax
0x180003bdd  js      loc_180003AB2
0x180003be3  mov     ecx, 80h; Size
0x180003be8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003bed  test    rax, rax
0x180003bf0  jz      short loc_180003C5E
0x180003bf2  mov     rcx, rax; this
0x180003bf5  call    ??0OUTPUT_CACHE@@QEAA@XZ; OUTPUT_CACHE::OUTPUT_CACHE(void)
0x180003bfa  mov     cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA, rax; OUTPUT_CACHE * g_pOutputCache
0x180003c01  test    rax, rax
0x180003c04  jz      loc_180003AAD
0x180003c0a  call    cs:__imp_GetProcessHeap
0x180003c10  mov     ecx, 8; Size
0x180003c15  mov     cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA, rax; void * RESPONSE_ENTRY::sm_hHeap
0x180003c1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c21  test    rax, rax
0x180003c24  jnz     short loc_180003C46
0x180003c26  mov     cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA, rsi; MonitorStoredContext * g_pMonitorStoredContext
0x180003c2d  lea     edi, [rax+1]
0x180003c30  jmp     loc_180003AAD
0x180003c35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003c3a  mov     cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA, rsi; MonitorStoredContext * g_pMonitorStoredContext
0x180003c41  jmp     loc_180003AC2
0x180003c46  lea     rcx, ??_7MonitorStoredContext@@6B@; const MonitorStoredContext::`vftable'
0x180003c4d  mov     cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA, rax; MonitorStoredContext * g_pMonitorStoredContext
0x180003c54  mov     [rax], rcx
0x180003c57  xor     eax, eax
0x180003c59  jmp     loc_180003A18
0x180003c5e  mov     cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA, rsi; OUTPUT_CACHE * g_pOutputCache
0x180003c65  jmp     loc_180003AAD
0x180003c6a  mov     cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA, rsi; VARY_BY_CACHE * g_pVaryByCache
0x180003c71  jmp     loc_180003AAD
0x180003c76  mov     cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA, rsi; void * RESPONSE_ENTRY::sm_hHeap
0x180003c7d  jmp     loc_180003ACA
0x180003c82  call    ??_GOUTPUT_CACHE@@QEAAPEAXI@Z; OUTPUT_CACHE::`scalar deleting destructor'(uint)
0x180003c87  mov     cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA, rsi; OUTPUT_CACHE * g_pOutputCache
0x180003c8e  jmp     loc_180003ADA
0x180003c93  call    ??_GVARY_BY_CACHE@@QEAAPEAXI@Z; VARY_BY_CACHE::`scalar deleting destructor'(uint)
0x180003c98  jmp     loc_180003AF8
```
