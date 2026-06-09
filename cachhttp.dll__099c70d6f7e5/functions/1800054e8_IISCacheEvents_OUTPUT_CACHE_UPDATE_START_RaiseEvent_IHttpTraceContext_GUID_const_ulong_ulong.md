# IISCacheEvents::OUTPUT_CACHE_UPDATE_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)

- ea: `0x1800054e8`
- end: `0x180005633`
- name: `?RaiseEvent@OUTPUT_CACHE_UPDATE_START@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z`
- size: `331`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180001280`

## callees

- `0x1800054e8`
- `0x180008bf0`
- `0x180009010`

## string_xrefs

- `0x1800055d8`: `NO_CACHE`
- `0x180005539`: `OUTPUT_CACHE_UPDATE_START`
- `0x180005578`: `CachePolicy`

## pseudocode

```c
__int64 __fastcall IISCacheEvents::OUTPUT_CACHE_UPDATE_START::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3,
        int a4)
{
  int v4; // r8d
  const wchar_t *v5; // rax
  __int64 v6; // rax
  _QWORD v8[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+4Ch] [rbp-B4h]
  __int128 v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+64h] [rbp-9Ch]
  __int64 v14; // [rsp+68h] [rbp-98h]
  const wchar_t **v15; // [rsp+70h] [rbp-90h]
  const wchar_t *v16; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+90h] [rbp-70h]
  int v19; // [rsp+98h] [rbp-68h]
  __int64 v20; // [rsp+A0h] [rbp-60h]
  const wchar_t *v21; // [rsp+A8h] [rbp-58h]
  int v22; // [rsp+B0h] [rbp-50h]
  int *v23; // [rsp+B8h] [rbp-48h]
  int v24; // [rsp+C0h] [rbp-40h]
  const wchar_t *v25; // [rsp+C8h] [rbp-38h]
  const wchar_t *v26; // [rsp+D0h] [rbp-30h]
  int v27; // [rsp+D8h] [rbp-28h]
  int *v28; // [rsp+E0h] [rbp-20h]
  int v29; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+130h] [rbp+30h] BYREF
  int v32; // [rsp+138h] [rbp+38h] BYREF

  v32 = a4;
  v31 = a3;
  v8[1] = 128;
  v8[3] = 17;
  v8[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v8[2] = &`IISCacheEvents::GetAreaGuid'::`2'::AreaGuid;
  v8[4] = L"OUTPUT_CACHE_UPDATE_START";
  v9 = 1;
  v13 = 1;
  v14 = 3;
  v11 = 0;
  v10 = 4;
  v16 = L"ContextId";
  v21 = L"CachePolicy";
  v23 = &v31;
  v12 = 0;
  v17 = 72;
  v18 = 0;
  v19 = 16;
  v20 = 0;
  v22 = 19;
  v24 = 4;
  if ( a3 )
  {
    v4 = a3 - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
        v5 = L"TIME_TO_LIVE";
      else
        v5 = 0;
    }
    else
    {
      v5 = L"USER_INVALIDATES";
    }
  }
  else
  {
    v5 = L"NO_CACHE";
  }
  v25 = v5;
  v26 = L"TimeToLive";
  v28 = &v32;
  v15 = &v16;
  v6 = *(_QWORD *)a1;
  v30 = 0;
  v27 = 19;
  v29 = 4;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v6 + 16))(a1, v8);
  return 0;
}

```

## disassembly

```asm
0x1800054e8  mov     [rsp-8+arg_18], r9d
0x1800054ed  mov     [rsp-8+arg_10], r8d
0x1800054f2  push    rbp
0x1800054f3  lea     rbp, [rsp-10h]
0x1800054f8  sub     rsp, 110h
0x1800054ff  mov     rax, cs:__security_cookie
0x180005506  xor     rax, rsp
0x180005509  mov     [rbp+10h+var_10], rax
0x18000550d  xor     edx, edx
0x18000550f  mov     [rsp+110h+var_E8], 80h
0x180005518  mov     [rsp+110h+var_D8], 11h
0x180005521  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180005528  mov     [rsp+110h+var_F0], rax
0x18000552d  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCacheEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCacheEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180005534  mov     [rsp+110h+var_E0], rax
0x180005539  lea     rax, aOutputCacheUpd; "OUTPUT_CACHE_UPDATE_START"
0x180005540  mov     [rsp+110h+var_D0], rax
0x180005545  mov     eax, 1
0x18000554a  mov     [rsp+110h+var_C8], eax
0x18000554e  xorps   xmm0, xmm0
0x180005551  mov     [rsp+110h+var_AC], eax
0x180005555  mov     [rsp+110h+var_A8], 3
0x18000555e  movdqa  [rsp+110h+var_C0], xmm0
0x180005564  lea     r9d, [rax+3]
0x180005568  mov     [rsp+110h+var_C4], r9d
0x18000556d  lea     rax, aContextid; "ContextId"
0x180005574  mov     [rbp+10h+var_90], rax
0x180005578  lea     rax, aCachepolicy; "CachePolicy"
0x18000557f  mov     [rbp+10h+var_68], rax
0x180005583  lea     rax, [rbp+10h+arg_10]
0x180005587  mov     [rbp+10h+var_58], rax
0x18000558b  lea     r10d, [r9+0Fh]
0x18000558f  mov     [rsp+110h+var_B0], edx
0x180005593  mov     [rbp+10h+var_88], 48h ; 'H'
0x18000559a  mov     [rbp+10h+var_80], rdx
0x18000559e  mov     [rbp+10h+var_78], 10h
0x1800055a5  mov     [rbp+10h+var_70], rdx
0x1800055a9  mov     [rbp+10h+var_60], r10d
0x1800055ad  mov     [rbp+10h+var_50], r9d
0x1800055b1  test    r8d, r8d
0x1800055b4  jz      short loc_1800055D8
0x1800055b6  sub     r8d, 1
0x1800055ba  jz      short loc_1800055CF
0x1800055bc  cmp     r8d, 1
0x1800055c0  jz      short loc_1800055C6
0x1800055c2  mov     eax, edx
0x1800055c4  jmp     short loc_1800055DF
0x1800055c6  lea     rax, aTimeToLive; "TIME_TO_LIVE"
0x1800055cd  jmp     short loc_1800055DF
0x1800055cf  lea     rax, aUserInvalidate; "USER_INVALIDATES"
0x1800055d6  jmp     short loc_1800055DF
0x1800055d8  lea     rax, aNoCache_0; "NO_CACHE"
0x1800055df  mov     [rbp+10h+var_48], rax
0x1800055e3  lea     rax, aTimetolive; "TimeToLive"
0x1800055ea  mov     [rbp+10h+var_40], rax
0x1800055ee  lea     rax, [rbp+10h+arg_18]
0x1800055f2  mov     [rbp+10h+var_30], rax
0x1800055f6  lea     rax, [rbp+10h+var_90]
0x1800055fa  mov     [rsp+110h+var_A0], rax
0x1800055ff  mov     rax, [rcx]
0x180005602  mov     [rbp+10h+var_20], rdx
0x180005606  lea     rdx, [rsp+110h+var_F0]
0x18000560b  mov     [rbp+10h+var_38], r10d
0x18000560f  mov     [rbp+10h+var_28], r9d
0x180005613  mov     rax, [rax+10h]
0x180005617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561c  xor     eax, eax
0x18000561e  mov     rcx, [rbp+10h+var_10]
0x180005622  xor     rcx, rsp; StackCookie
0x180005625  call    __security_check_cookie
0x18000562a  add     rsp, 110h
0x180005631  pop     rbp
0x180005632  retn
```
