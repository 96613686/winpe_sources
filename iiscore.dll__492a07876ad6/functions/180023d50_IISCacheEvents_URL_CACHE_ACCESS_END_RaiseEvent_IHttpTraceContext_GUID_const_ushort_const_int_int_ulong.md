# IISCacheEvents::URL_CACHE_ACCESS_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,int,int,ulong)

- ea: `0x180023d50`
- end: `0x180023ebc`
- name: `?RaiseEvent@URL_CACHE_ACCESS_END@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGHHK@Z`
- size: `364`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *, int, char, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d260`

## callees

- `0x180037790`
- `0x180038010`

## string_xrefs

- `0x180023da4`: `URL_CACHE_ACCESS_END`
- `0x180023dfd`: `URLInfoFromCache`
- `0x180023e13`: `URLInfoAddedToCache`
- `0x180023de7`: `PhysicalPath`

## pseudocode

```c
__int64 __fastcall IISCacheEvents::URL_CACHE_ACCESS_END::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  void (__fastcall *v7)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v9[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+4Ch] [rbp-B4h]
  __int128 v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+60h] [rbp-A0h]
  int v14; // [rsp+64h] [rbp-9Ch]
  __int64 v15; // [rsp+68h] [rbp-98h]
  const wchar_t **v16; // [rsp+70h] [rbp-90h]
  const wchar_t *v17; // [rsp+80h] [rbp-80h] BYREF
  int v18; // [rsp+88h] [rbp-78h]
  const struct _GUID *v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+98h] [rbp-68h]
  __int64 v21; // [rsp+A0h] [rbp-60h]
  const wchar_t *v22; // [rsp+A8h] [rbp-58h]
  int v23; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v24; // [rsp+B8h] [rbp-48h]
  int v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  const wchar_t *v27; // [rsp+D0h] [rbp-30h]
  int v28; // [rsp+D8h] [rbp-28h]
  int *v29; // [rsp+E0h] [rbp-20h]
  int v30; // [rsp+E8h] [rbp-18h]
  __int64 v31; // [rsp+F0h] [rbp-10h]
  const wchar_t *v32; // [rsp+F8h] [rbp-8h]
  int v33; // [rsp+100h] [rbp+0h]
  char *v34; // [rsp+108h] [rbp+8h]
  int v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  const wchar_t *v37; // [rsp+120h] [rbp+20h]
  int v38; // [rsp+128h] [rbp+28h]
  char *v39; // [rsp+130h] [rbp+30h]
  int v40; // [rsp+138h] [rbp+38h]
  __int64 v41; // [rsp+140h] [rbp+40h]
  int v42; // [rsp+188h] [rbp+88h] BYREF

  v42 = a4;
  v19 = a2;
  v9[1] = 128;
  v9[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v9[3] = 13;
  v9[2] = &`IISCacheEvents::GetAreaGuid'::`2'::AreaGuid;
  v9[4] = L"URL_CACHE_ACCESS_END";
  v10 = 1;
  v14 = 1;
  v15 = 5;
  v12 = 0;
  v11 = 4;
  v28 = 11;
  v17 = L"ContextId";
  v22 = L"PhysicalPath";
  v24 = &dword_18003C134;
  v27 = L"URLInfoFromCache";
  v29 = &v42;
  v32 = L"URLInfoAddedToCache";
  v34 = &a5;
  v37 = L"ErrorCode";
  v39 = &a6;
  v16 = &v17;
  v6 = *(_QWORD *)a1;
  v33 = 11;
  v13 = 0;
  v18 = 72;
  v7 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v6 + 16);
  v20 = 16;
  v21 = 0;
  v23 = 31;
  v25 = 2;
  v26 = 0;
  v30 = 4;
  v31 = 0;
  v35 = 4;
  v36 = 0;
  v38 = 19;
  v40 = 4;
  v41 = 0;
  v7(a1, v9);
  return 0;
}

```

## disassembly

```asm
0x180023d50  mov     [rsp-8+arg_18], r9d
0x180023d55  push    rbp
0x180023d56  lea     rbp, [rsp-60h]
0x180023d5b  sub     rsp, 160h
0x180023d62  mov     rax, cs:__security_cookie
0x180023d69  xor     rax, rsp
0x180023d6c  mov     [rbp+60h+var_10], rax
0x180023d70  xor     r8d, r8d
0x180023d73  mov     [rbp+60h+var_D0], rdx
0x180023d77  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180023d7e  mov     [rsp+160h+var_138], 80h
0x180023d87  mov     [rsp+160h+var_140], rax
0x180023d8c  xorps   xmm0, xmm0
0x180023d8f  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCacheEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCacheEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180023d96  mov     [rsp+160h+var_128], 0Dh
0x180023d9f  mov     [rsp+160h+var_130], rax
0x180023da4  lea     rax, aUrlCacheAccess_0; "URL_CACHE_ACCESS_END"
0x180023dab  mov     [rsp+160h+var_120], rax
0x180023db0  mov     eax, 1
0x180023db5  mov     [rsp+160h+var_118], eax
0x180023db9  mov     [rsp+160h+var_FC], eax
0x180023dbd  mov     [rsp+160h+var_F8], 5
0x180023dc6  lea     r9d, [rax+3]
0x180023dca  movdqa  [rsp+160h+var_110], xmm0
0x180023dd0  lea     edx, [r9+7]
0x180023dd4  mov     [rsp+160h+var_114], r9d
0x180023dd9  lea     rax, aContextid; "ContextId"
0x180023de0  mov     [rbp+60h+var_88], edx
0x180023de3  mov     [rbp+60h+var_E0], rax
0x180023de7  lea     rax, aPhysicalpath; "PhysicalPath"
0x180023dee  mov     [rbp+60h+var_B8], rax
0x180023df2  lea     rax, dword_18003C134
0x180023df9  mov     [rbp+60h+var_A8], rax
0x180023dfd  lea     rax, aUrlinfofromcac; "URLInfoFromCache"
0x180023e04  mov     [rbp+60h+var_90], rax
0x180023e08  lea     rax, [rbp+60h+arg_18]
0x180023e0f  mov     [rbp+60h+var_80], rax
0x180023e13  lea     rax, aUrlinfoaddedto; "URLInfoAddedToCache"
0x180023e1a  mov     [rbp+60h+var_68], rax
0x180023e1e  lea     rax, [rbp+60h+arg_20]
0x180023e25  mov     [rbp+60h+var_58], rax
0x180023e29  lea     rax, aErrorcode; "ErrorCode"
0x180023e30  mov     [rbp+60h+var_40], rax
0x180023e34  lea     rax, [rbp+60h+arg_28]
0x180023e3b  mov     [rbp+60h+var_30], rax
0x180023e3f  lea     rax, [rbp+60h+var_E0]
0x180023e43  mov     [rsp+160h+var_F0], rax
0x180023e48  mov     rax, [rcx]
0x180023e4b  mov     [rbp+60h+var_60], edx
0x180023e4e  lea     rdx, [rsp+160h+var_140]
0x180023e53  mov     [rsp+160h+var_100], r8d
0x180023e58  mov     [rbp+60h+var_D8], 48h ; 'H'
0x180023e5f  mov     rax, [rax+10h]
0x180023e63  mov     [rbp+60h+var_C8], 10h
0x180023e6a  mov     [rbp+60h+var_C0], r8
0x180023e6e  mov     [rbp+60h+var_B0], 1Fh
0x180023e75  mov     [rbp+60h+var_A0], 2
0x180023e7c  mov     [rbp+60h+var_98], r8
0x180023e80  mov     [rbp+60h+var_78], r9d
0x180023e84  mov     [rbp+60h+var_70], r8
0x180023e88  mov     [rbp+60h+var_50], r9d
0x180023e8c  mov     [rbp+60h+var_48], r8
0x180023e90  mov     [rbp+60h+var_38], 13h
0x180023e97  mov     [rbp+60h+var_28], r9d
0x180023e9b  mov     [rbp+60h+var_20], r8
0x180023e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ea4  xor     eax, eax
0x180023ea6  mov     rcx, [rbp+60h+var_10]
0x180023eaa  xor     rcx, rsp; StackCookie
0x180023ead  call    __security_check_cookie
0x180023eb2  add     rsp, 160h
0x180023eb9  pop     rbp
0x180023eba  retn
```
