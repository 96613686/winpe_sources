# IISCacheEvents::HTTPSYS_CACHEABLE::RaiseEvent(IHttpTraceContext *,_GUID const *,int,ulong,ulong,ulong)

- ea: `0x1800256ec`
- end: `0x180025895`
- name: `?RaiseEvent@HTTPSYS_CACHEABLE@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@HKKK@Z`
- size: `425`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, int, unsigned int, unsigned int, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003ca0`

## callees

- `0x1800256ec`
- `0x18002639c`
- `0x1800343f0`
- `0x180035010`

## string_xrefs

- `0x18002574c`: `HTTPSYS_CACHEABLE`
- `0x180025795`: `HttpsysCacheable`
- `0x1800257ec`: `CachePolicy`
- `0x180025834`: `NO_CACHE`

## pseudocode

```c
__int64 __fastcall IISCacheEvents::HTTPSYS_CACHEABLE::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        char a6)
{
  __int64 v6; // rdx
  __int64 *v7; // r8
  int v8; // r10d
  int v9; // r11d
  const wchar_t *v10; // rax
  __int64 v11; // rax
  _QWORD v13[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+4Ch] [rbp-B4h]
  __int128 v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+64h] [rbp-9Ch]
  __int64 v19; // [rsp+68h] [rbp-98h]
  const wchar_t **v20; // [rsp+70h] [rbp-90h]
  const wchar_t *v21; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  int v24; // [rsp+98h] [rbp-68h]
  __int64 v25; // [rsp+A0h] [rbp-60h]
  const wchar_t *v26; // [rsp+A8h] [rbp-58h]
  int v27; // [rsp+B0h] [rbp-50h]
  int *v28; // [rsp+B8h] [rbp-48h]
  int v29; // [rsp+C0h] [rbp-40h]
  __int64 v30; // [rsp+C8h] [rbp-38h]
  const wchar_t *v31; // [rsp+D0h] [rbp-30h]
  int v32; // [rsp+D8h] [rbp-28h]
  unsigned int *v33; // [rsp+E0h] [rbp-20h]
  int v34; // [rsp+E8h] [rbp-18h]
  const wchar_t *v35; // [rsp+F0h] [rbp-10h]
  const wchar_t *v36; // [rsp+F8h] [rbp-8h]
  int v37; // [rsp+100h] [rbp+0h]
  unsigned int *v38; // [rsp+108h] [rbp+8h]
  int v39; // [rsp+110h] [rbp+10h]
  const wchar_t *v40; // [rsp+118h] [rbp+18h]
  const wchar_t *v41; // [rsp+120h] [rbp+20h]
  int v42; // [rsp+128h] [rbp+28h]
  char *v43; // [rsp+130h] [rbp+30h]
  int v44; // [rsp+138h] [rbp+38h]
  __int64 v45; // [rsp+140h] [rbp+40h]
  int v46; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v47; // [rsp+188h] [rbp+88h] BYREF

  v47 = a4;
  v46 = a3;
  v13[1] = 128;
  v13[3] = 14;
  v13[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v19 = 5;
  v13[2] = &`IISCacheEvents::GetAreaGuid'::`2'::AreaGuid;
  v16 = 0;
  v13[4] = L"HTTPSYS_CACHEABLE";
  v17 = 0;
  v14 = 1;
  v18 = 1;
  v22 = 72;
  v23 = 0;
  v15 = 4;
  v21 = L"ContextId";
  v24 = 16;
  v26 = L"HttpsysCacheable";
  v28 = &v46;
  v31 = L"Reason";
  v33 = &v47;
  v25 = 0;
  v27 = 11;
  v29 = 4;
  v30 = 0;
  v32 = 19;
  v34 = 4;
  v35 = IISCacheEvents::HTTPSYS_CACHEABLE::TranslateEnumReasonToString(a4);
  v36 = L"CachePolicy";
  v38 = &a5;
  v37 = v9;
  v39 = v8;
  if ( a5 )
  {
    if ( a5 == 1 )
    {
      v10 = L"USER_INVALIDATES";
    }
    else if ( a5 == 2 )
    {
      v10 = L"TIME_TO_LIVE";
    }
    else
    {
      v10 = (const wchar_t *)(unsigned int)v6;
    }
  }
  else
  {
    v10 = L"NO_CACHE";
  }
  v40 = v10;
  v45 = v6;
  v41 = L"TimeToLive";
  v42 = v9;
  v43 = &a6;
  v20 = &v21;
  v11 = *v7;
  v44 = v8;
  (*(void (__fastcall **)(__int64 *, _QWORD *))(v11 + 16))(v7, v13);
  return 0;
}

```

## disassembly

```asm
0x1800256ec  mov     [rsp-8+arg_18], r9d
0x1800256f1  mov     [rsp-8+arg_10], r8d
0x1800256f6  push    rbp
0x1800256f7  lea     rbp, [rsp-60h]
0x1800256fc  sub     rsp, 160h
0x180025703  mov     rax, cs:__security_cookie
0x18002570a  xor     rax, rsp
0x18002570d  mov     [rbp+60h+var_10], rax
0x180025711  xor     edx, edx
0x180025713  mov     [rsp+160h+var_138], 80h
0x18002571c  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180025723  mov     [rsp+160h+var_128], 0Eh
0x18002572c  mov     [rsp+160h+var_140], rax
0x180025731  mov     r8, rcx
0x180025734  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCacheEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCacheEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18002573b  mov     [rsp+160h+var_F8], 5
0x180025744  mov     [rsp+160h+var_130], rax
0x180025749  xorps   xmm0, xmm0
0x18002574c  lea     rax, aHttpsysCacheab; "HTTPSYS_CACHEABLE"
0x180025753  movdqa  [rsp+160h+var_110], xmm0
0x180025759  mov     [rsp+160h+var_120], rax
0x18002575e  mov     ecx, r9d
0x180025761  mov     eax, 1
0x180025766  mov     [rsp+160h+var_100], edx
0x18002576a  mov     [rsp+160h+var_118], eax
0x18002576e  mov     [rsp+160h+var_FC], eax
0x180025772  mov     [rbp+60h+var_D8], 48h ; 'H'
0x180025779  lea     r10d, [rax+3]
0x18002577d  mov     [rbp+60h+var_D0], rdx
0x180025781  lea     rax, aContextid; "ContextId"
0x180025788  mov     [rsp+160h+var_114], r10d
0x18002578d  mov     [rbp+60h+var_E0], rax
0x180025791  lea     r11d, [r10+0Fh]
0x180025795  lea     rax, aHttpsyscacheab; "HttpsysCacheable"
0x18002579c  mov     [rbp+60h+var_C8], 10h
0x1800257a3  mov     [rbp+60h+var_B8], rax
0x1800257a7  lea     rax, [rbp+60h+arg_10]
0x1800257ae  mov     [rbp+60h+var_A8], rax
0x1800257b2  lea     rax, aReason; "Reason"
0x1800257b9  mov     [rbp+60h+var_90], rax
0x1800257bd  lea     rax, [rbp+60h+arg_18]
0x1800257c4  mov     [rbp+60h+var_80], rax
0x1800257c8  mov     [rbp+60h+var_C0], rdx
0x1800257cc  mov     [rbp+60h+var_B0], 0Bh
0x1800257d3  mov     [rbp+60h+var_A0], r10d
0x1800257d7  mov     [rbp+60h+var_98], rdx
0x1800257db  mov     [rbp+60h+var_88], r11d
0x1800257df  mov     [rbp+60h+var_78], r10d
0x1800257e3  call    ?TranslateEnumReasonToString@HTTPSYS_CACHEABLE@IISCacheEvents@@SAPEBGW4enumReason@12@@Z; IISCacheEvents::HTTPSYS_CACHEABLE::TranslateEnumReasonToString(IISCacheEvents::HTTPSYS_CACHEABLE::enumReason)
0x1800257e8  mov     [rbp+60h+var_70], rax
0x1800257ec  lea     rax, aCachepolicy; "CachePolicy"
0x1800257f3  mov     [rbp+60h+var_68], rax
0x1800257f7  lea     rax, [rbp+60h+arg_20]
0x1800257fe  mov     [rbp+60h+var_58], rax
0x180025802  mov     eax, [rbp+60h+arg_20]
0x180025808  mov     [rbp+60h+var_60], r11d
0x18002580c  mov     [rbp+60h+var_50], r10d
0x180025810  test    eax, eax
0x180025812  jz      short loc_180025834
0x180025814  sub     eax, 1
0x180025817  jz      short loc_18002582B
0x180025819  cmp     eax, 1
0x18002581c  jz      short loc_180025822
0x18002581e  mov     eax, edx
0x180025820  jmp     short loc_18002583B
0x180025822  lea     rax, aTimeToLive; "TIME_TO_LIVE"
0x180025829  jmp     short loc_18002583B
0x18002582b  lea     rax, aUserInvalidate; "USER_INVALIDATES"
0x180025832  jmp     short loc_18002583B
0x180025834  lea     rax, aNoCache; "NO_CACHE"
0x18002583b  mov     [rbp+60h+var_48], rax
0x18002583f  mov     rcx, r8
0x180025842  lea     rax, aTimetolive; "TimeToLive"
0x180025849  mov     [rbp+60h+var_20], rdx
0x18002584d  mov     [rbp+60h+var_40], rax
0x180025851  lea     rdx, [rsp+160h+var_140]
0x180025856  lea     rax, [rbp+60h+arg_28]
0x18002585d  mov     [rbp+60h+var_38], r11d
0x180025861  mov     [rbp+60h+var_30], rax
0x180025865  lea     rax, [rbp+60h+var_E0]
0x180025869  mov     [rsp+160h+var_F0], rax
0x18002586e  mov     rax, [r8]
0x180025871  mov     [rbp+60h+var_28], r10d
0x180025875  mov     rax, [rax+10h]
0x180025879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002587e  xor     eax, eax
0x180025880  mov     rcx, [rbp+60h+var_10]
0x180025884  xor     rcx, rsp; StackCookie
0x180025887  call    __security_check_cookie
0x18002588c  add     rsp, 160h
0x180025893  pop     rbp
0x180025894  retn
```
