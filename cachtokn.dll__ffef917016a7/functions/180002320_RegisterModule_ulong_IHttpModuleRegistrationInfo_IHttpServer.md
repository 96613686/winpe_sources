# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002320`
- end: `0x18000241c`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800015b0`
- `0x180001fd8`
- `0x180002320`
- `0x180003010`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800023cf`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800023cf`

## string_xrefs

- `0x1800023ae`: `TOKEN_CACHE`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v4; // rax
  __int64 result; // rax
  CLKRHashTable *v6; // rax
  CLKRHashTable *v7; // rbx
  TOKEN_CACHE *v8; // rcx

  v4 = operator new(8u);
  if ( v4 )
  {
    *v4 = &CIISGlobalModule::`vftable';
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
               a2,
               v4,
               20);
    if ( (int)result < 0 )
      return result;
    v6 = (CLKRHashTable *)operator new(0x68u);
    v7 = v6;
    if ( v6 )
    {
      CLKRHashTable::CLKRHashTable(
        v6,
        "TOKEN_CACHE",
        (unsigned __int64 (*)(const void *))CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_ExtractKey,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_ExtractKey,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      *((_QWORD *)v7 + 9) = 0;
      *((_QWORD *)v7 + 10) = 0;
      *((_QWORD *)v7 + 11) = 0;
      *((_QWORD *)v7 + 12) = 0;
      g_pTokenCache = v7;
      return TOKEN_CACHE::Initialize(v8);
    }
    g_pTokenCache = 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002320  push    rbx
0x180002322  sub     rsp, 50h
0x180002326  mov     ecx, 8; Size
0x18000232b  mov     rbx, rdx
0x18000232e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002333  mov     rdx, rax
0x180002336  test    rax, rax
0x180002339  jz      loc_180002411
0x18000233f  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180002346  mov     r8d, 14h
0x18000234c  mov     [rdx], rax
0x18000234f  mov     rcx, [rbx]
0x180002352  mov     rax, [rcx+18h]
0x180002356  mov     rcx, rbx
0x180002359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000235e  test    eax, eax
0x180002360  js      loc_180002416
0x180002366  mov     ecx, 68h ; 'h'; Size
0x18000236b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002370  mov     rbx, rax
0x180002373  test    rax, rax
0x180002376  jz      loc_180002406
0x18000237c  movsd   xmm0, cs:__real@4010000000000000
0x180002384  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18000238b  mov     [rsp+58h+var_10], 0
0x180002390  lea     r9, ?_ExtractKey@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_ExtractKey(void const *)
0x180002397  mov     [rsp+58h+var_18], 0
0x18000239f  lea     r8, ?_ExtractKey@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_ExtractKey(void const *)
0x1800023a6  mov     [rsp+58h+var_20], 1
0x1800023ae  lea     rdx, aTokenCache; "TOKEN_CACHE"
0x1800023b5  movsd   [rsp+58h+var_28], xmm0
0x1800023bb  mov     rcx, rbx
0x1800023be  mov     [rsp+58h+var_30], rax
0x1800023c3  lea     rax, ?_EqualKeys@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_ENTRY@@PEAVIHttpCacheKey@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_ENTRY,IHttpCacheKey *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800023ca  mov     [rsp+58h+var_38], rax
0x1800023cf  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800023d5  mov     qword ptr [rbx+48h], 0
0x1800023dd  mov     qword ptr [rbx+50h], 0
0x1800023e5  mov     qword ptr [rbx+58h], 0
0x1800023ed  mov     qword ptr [rbx+60h], 0
0x1800023f5  mov     cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA, rbx; TOKEN_CACHE * g_pTokenCache
0x1800023fc  add     rsp, 50h
0x180002400  pop     rbx
0x180002401  jmp     ?Initialize@TOKEN_CACHE@@QEAAJXZ; TOKEN_CACHE::Initialize(void)
0x180002406  mov     cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA, 0; TOKEN_CACHE * g_pTokenCache
0x180002411  mov     eax, 80070008h
0x180002416  add     rsp, 50h
0x18000241a  pop     rbx
0x18000241b  retn
```
