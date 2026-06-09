# IISCacheEvents::FILE_CACHE_ACCESS_END::RaiseEvent(IHttpTraceContext *,_GUID const *,int,int,int,int,int,ulong,char const *)

- ea: `0x18001f09c`
- end: `0x18001f2c2`
- name: `?RaiseEvent@FILE_CACHE_ACCESS_END@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@HHHHHKPEBD@Z`
- size: `550`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, int, int, char, int, int, char, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800115b0`

## callees

- `0x18001f09c`
- `0x180037790`
- `0x180038010`

## string_xrefs

- `0x18001f0fd`: `FILE_CACHE_ACCESS_END`
- `0x18001f13c`: `FileFromCache`
- `0x18001f152`: `FileAddedToCache`

## pseudocode

```c
__int64 __fastcall IISCacheEvents::FILE_CACHE_ACCESS_END::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3,
        int a4,
        char a5,
        int a6,
        int a7,
        char a8,
        const char *a9)
{
  int v9; // eax
  __int64 v10; // rax
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v14[5]; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+5Ch] [rbp-A4h]
  __int128 v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+74h] [rbp-8Ch]
  int v20; // [rsp+78h] [rbp-88h]
  _QWORD v21[2]; // [rsp+7Ch] [rbp-84h] BYREF
  const wchar_t *v22; // [rsp+90h] [rbp-70h] BYREF
  int v23; // [rsp+98h] [rbp-68h]
  const struct _GUID *v24; // [rsp+A0h] [rbp-60h]
  int v25; // [rsp+A8h] [rbp-58h]
  __int64 v26; // [rsp+B0h] [rbp-50h]
  const wchar_t *v27; // [rsp+B8h] [rbp-48h]
  int v28; // [rsp+C0h] [rbp-40h]
  int *v29; // [rsp+C8h] [rbp-38h]
  int v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  const wchar_t *v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E8h] [rbp-18h]
  int *v34; // [rsp+F0h] [rbp-10h]
  int v35; // [rsp+F8h] [rbp-8h]
  __int64 v36; // [rsp+100h] [rbp+0h]
  const wchar_t *v37; // [rsp+108h] [rbp+8h]
  int v38; // [rsp+110h] [rbp+10h]
  char *v39; // [rsp+118h] [rbp+18h]
  int v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]
  const wchar_t *v42; // [rsp+130h] [rbp+30h]
  int v43; // [rsp+138h] [rbp+38h]
  int *v44; // [rsp+140h] [rbp+40h]
  int v45; // [rsp+148h] [rbp+48h]
  __int64 v46; // [rsp+150h] [rbp+50h]
  const wchar_t *v47; // [rsp+158h] [rbp+58h]
  int v48; // [rsp+160h] [rbp+60h]
  int *v49; // [rsp+168h] [rbp+68h]
  int v50; // [rsp+170h] [rbp+70h]
  __int64 v51; // [rsp+178h] [rbp+78h]
  const wchar_t *v52; // [rsp+180h] [rbp+80h]
  int v53; // [rsp+188h] [rbp+88h]
  char *v54; // [rsp+190h] [rbp+90h]
  int v55; // [rsp+198h] [rbp+98h]
  __int64 v56; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v57; // [rsp+1A8h] [rbp+A8h]
  int v58; // [rsp+1B0h] [rbp+B0h]
  const char *v59; // [rsp+1B8h] [rbp+B8h]
  int v60; // [rsp+1C0h] [rbp+C0h]
  __int64 v61; // [rsp+1C8h] [rbp+C8h]
  int v62; // [rsp+200h] [rbp+100h] BYREF
  int v63; // [rsp+208h] [rbp+108h] BYREF

  v63 = a4;
  v62 = a3;
  v24 = a2;
  memset(v21, 0, 12);
  v14[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v14[2] = &`IISCacheEvents::GetAreaGuid'::`2'::AreaGuid;
  v14[4] = L"FILE_CACHE_ACCESS_END";
  v13 = 1;
  v12 = 1;
  v22 = L"ContextId";
  v27 = L"Successful";
  v29 = &v62;
  v32 = L"FileFromCache";
  v34 = &v63;
  v37 = L"FileAddedToCache";
  v39 = &a5;
  v42 = L"FileDirmoned";
  v44 = &v12;
  v47 = L"LastModCheckErrorIgnored";
  v49 = &v13;
  v52 = L"ErrorCode";
  v54 = &a8;
  v57 = L"LastModifiedTime";
  v14[1] = 128;
  v14[3] = 11;
  v15 = 1;
  v16 = 4;
  v20 = 8;
  v17 = 0;
  v18 = 0;
  v19 = 1;
  v23 = 72;
  v25 = 16;
  v26 = 0;
  v28 = 11;
  v30 = 4;
  v31 = 0;
  v33 = 11;
  v35 = 4;
  v36 = 0;
  v38 = 11;
  v40 = 4;
  v41 = 0;
  v43 = 11;
  v45 = 4;
  v46 = 0;
  v48 = 11;
  v50 = 4;
  v51 = 0;
  v53 = 19;
  v55 = 4;
  v56 = 0;
  v58 = 30;
  v59 = a9;
  if ( a9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a9[v10] );
    v9 = v10 + 1;
  }
  else
  {
    v9 = 0;
  }
  v60 = v9;
  v61 = 0;
  *(_QWORD *)((char *)v21 + 4) = &v22;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v14);
  return 0;
}

```

## disassembly

```asm
0x18001f09c  mov     [rsp-8+arg_18], r9d
0x18001f0a1  mov     [rsp-8+arg_10], r8d
0x18001f0a6  push    rbp
0x18001f0a7  lea     rbp, [rsp-0E0h]
0x18001f0af  sub     rsp, 1E0h
0x18001f0b6  mov     rax, cs:__security_cookie
0x18001f0bd  xor     rax, rsp
0x18001f0c0  mov     [rbp+0E0h+var_10], rax
0x18001f0c7  xor     eax, eax
0x18001f0c9  mov     [rbp+0E0h+var_140], rdx
0x18001f0cd  mov     rdx, [rbp+0E0h+arg_40]
0x18001f0d4  xor     r11d, r11d
0x18001f0d7  mov     [rsp+1E0h+var_164], rax
0x18001f0dc  mov     r8d, 1
0x18001f0e2  mov     [rbp+0E0h+var_15C], eax
0x18001f0e5  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18001f0ec  mov     [rsp+1E0h+var_1B0], rax
0x18001f0f1  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCacheEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCacheEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001f0f8  mov     [rsp+1E0h+var_1A0], rax
0x18001f0fd  lea     rax, aFileCacheAcces_0; "FILE_CACHE_ACCESS_END"
0x18001f104  mov     [rsp+1E0h+var_190], rax
0x18001f109  lea     r10d, [r8+3]
0x18001f10d  mov     [rsp+1E0h+var_1B8], r8d
0x18001f112  lea     r9d, [r8+0Ah]
0x18001f116  mov     [rsp+1E0h+var_1C0], r8d
0x18001f11b  lea     rax, aContextid; "ContextId"
0x18001f122  mov     [rbp+0E0h+var_150], rax
0x18001f126  lea     rax, aSuccessful; "Successful"
0x18001f12d  mov     [rbp+0E0h+var_128], rax
0x18001f131  lea     rax, [rbp+0E0h+arg_10]
0x18001f138  mov     [rbp+0E0h+var_118], rax
0x18001f13c  lea     rax, aFilefromcache; "FileFromCache"
0x18001f143  mov     [rbp+0E0h+var_100], rax
0x18001f147  lea     rax, [rbp+0E0h+arg_18]
0x18001f14e  mov     [rbp+0E0h+var_F0], rax
0x18001f152  lea     rax, aFileaddedtocac; "FileAddedToCache"
0x18001f159  mov     [rbp+0E0h+var_D8], rax
0x18001f15d  lea     rax, [rbp+0E0h+arg_20]
0x18001f164  mov     [rbp+0E0h+var_C8], rax
0x18001f168  lea     rax, aFiledirmoned; "FileDirmoned"
0x18001f16f  mov     [rbp+0E0h+var_B0], rax
0x18001f173  lea     rax, [rsp+1E0h+var_1C0]
0x18001f178  mov     [rbp+0E0h+var_A0], rax
0x18001f17c  lea     rax, aLastmodchecker; "LastModCheckErrorIgnored"
0x18001f183  mov     [rbp+0E0h+var_88], rax
0x18001f187  lea     rax, [rsp+1E0h+var_1B8]
0x18001f18c  mov     [rbp+0E0h+var_78], rax
0x18001f190  lea     rax, aErrorcode; "ErrorCode"
0x18001f197  mov     [rbp+0E0h+var_60], rax
0x18001f19e  lea     rax, [rbp+0E0h+arg_38]
0x18001f1a5  mov     [rbp+0E0h+var_50], rax
0x18001f1ac  lea     rax, aLastmodifiedti; "LastModifiedTime"
0x18001f1b3  mov     [rbp+0E0h+var_38], rax
0x18001f1ba  xorps   xmm0, xmm0
0x18001f1bd  mov     [rsp+1E0h+var_1A8], 80h
0x18001f1c6  mov     [rsp+1E0h+var_198], 0Bh
0x18001f1cf  mov     [rsp+1E0h+var_188], r8d
0x18001f1d4  mov     [rsp+1E0h+var_184], r10d
0x18001f1d9  mov     [rsp+1E0h+var_168], 8
0x18001f1e1  movdqa  [rsp+1E0h+var_180], xmm0
0x18001f1e7  mov     [rsp+1E0h+var_170], r11d
0x18001f1ec  mov     [rsp+1E0h+var_16C], r8d
0x18001f1f1  mov     [rbp+0E0h+var_148], 48h ; 'H'
0x18001f1f8  mov     [rbp+0E0h+var_138], 10h
0x18001f1ff  mov     [rbp+0E0h+var_130], r11
0x18001f203  mov     [rbp+0E0h+var_120], r9d
0x18001f207  mov     [rbp+0E0h+var_110], r10d
0x18001f20b  mov     [rbp+0E0h+var_108], r11
0x18001f20f  mov     [rbp+0E0h+var_F8], r9d
0x18001f213  mov     [rbp+0E0h+var_E8], r10d
0x18001f217  mov     [rbp+0E0h+var_E0], r11
0x18001f21b  mov     [rbp+0E0h+var_D0], r9d
0x18001f21f  mov     [rbp+0E0h+var_C0], r10d
0x18001f223  mov     [rbp+0E0h+var_B8], r11
0x18001f227  mov     [rbp+0E0h+var_A8], r9d
0x18001f22b  mov     [rbp+0E0h+var_98], r10d
0x18001f22f  mov     [rbp+0E0h+var_90], r11
0x18001f233  mov     [rbp+0E0h+var_80], r9d
0x18001f237  mov     [rbp+0E0h+var_70], r10d
0x18001f23b  mov     [rbp+0E0h+var_68], r11
0x18001f23f  mov     [rbp+0E0h+var_58], 13h
0x18001f249  mov     [rbp+0E0h+var_48], r10d
0x18001f250  mov     [rbp+0E0h+var_40], r11
0x18001f257  mov     [rbp+0E0h+var_30], 1Eh
0x18001f261  mov     [rbp+0E0h+var_28], rdx
0x18001f268  test    rdx, rdx
0x18001f26b  jnz     short loc_18001F272
0x18001f26d  mov     eax, r11d
0x18001f270  jmp     short loc_18001F281
0x18001f272  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f276  inc     rax
0x18001f279  cmp     [rdx+rax], r11b
0x18001f27d  jnz     short loc_18001F276
0x18001f27f  inc     eax
0x18001f281  mov     [rbp+0E0h+var_20], eax
0x18001f287  lea     rdx, [rsp+1E0h+var_1B0]
0x18001f28c  lea     rax, [rbp+0E0h+var_150]
0x18001f290  mov     [rbp+0E0h+var_18], r11
0x18001f297  mov     [rbp+0E0h+var_164+4], rax
0x18001f29b  mov     rax, [rcx]
0x18001f29e  mov     rax, [rax+10h]
0x18001f2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2a7  xor     eax, eax
0x18001f2a9  mov     rcx, [rbp+0E0h+var_10]
0x18001f2b0  xor     rcx, rsp; StackCookie
0x18001f2b3  call    __security_check_cookie
0x18001f2b8  add     rsp, 1E0h
0x18001f2bf  pop     rbp
0x18001f2c0  retn
```
