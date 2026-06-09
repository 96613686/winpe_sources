# IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x1800040e8`
- end: `0x180004216`
- name: `?RaiseEvent@OUTPUT_CACHE_LOOKUP_END@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `302`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001280`

## callees

- `0x1800040e8`
- `0x180009010`

## string_xrefs

- `0x180004130`: `OUTPUT_CACHE_LOOKUP_END`

## pseudocode

```c
__int64 __fastcall IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3)
{
  int v3; // r8d
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  const wchar_t *v7; // rax
  _QWORD v9[5]; // [rsp+20h] [rbp-59h] BYREF
  int v10; // [rsp+48h] [rbp-31h]
  int v11; // [rsp+4Ch] [rbp-2Dh]
  __int128 v12; // [rsp+50h] [rbp-29h]
  int v13; // [rsp+60h] [rbp-19h]
  int v14; // [rsp+64h] [rbp-15h]
  __int64 v15; // [rsp+68h] [rbp-11h]
  const wchar_t **v16; // [rsp+70h] [rbp-9h]
  const wchar_t *v17; // [rsp+80h] [rbp+7h] BYREF
  int v18; // [rsp+88h] [rbp+Fh]
  __int64 v19; // [rsp+90h] [rbp+17h]
  int v20; // [rsp+98h] [rbp+1Fh]
  __int64 v21; // [rsp+A0h] [rbp+27h]
  const wchar_t *v22; // [rsp+A8h] [rbp+2Fh]
  int v23; // [rsp+B0h] [rbp+37h]
  int *v24; // [rsp+B8h] [rbp+3Fh]
  int v25; // [rsp+C0h] [rbp+47h]
  const wchar_t *v26; // [rsp+C8h] [rbp+4Fh]
  int v27; // [rsp+F0h] [rbp+77h] BYREF

  v27 = a3;
  v9[1] = 128;
  v9[3] = 16;
  v15 = 2;
  v9[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v9[2] = &`IISCacheEvents::GetAreaGuid'::`2'::AreaGuid;
  v9[4] = L"OUTPUT_CACHE_LOOKUP_END";
  v10 = 1;
  v14 = 1;
  v17 = L"ContextId";
  v22 = L"Result";
  v24 = &v27;
  v11 = 4;
  v12 = 0;
  v13 = 0;
  v18 = 72;
  v19 = 0;
  v20 = 16;
  v21 = 0;
  v23 = 19;
  v25 = 4;
  if ( a3 )
  {
    v3 = a3 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            if ( v6 == 1 )
              v7 = L"CONDITIONAL_HEADERS_PRESENT";
            else
              v7 = 0;
          }
          else
          {
            v7 = L"CACHING_DISABLED";
          }
        }
        else
        {
          v7 = L"ACCEPT_ENCODING_NOT_MATCH";
        }
      }
      else
      {
        v7 = L"ACCEPT_NOT_MATCH";
      }
    }
    else
    {
      v7 = L"FOUND";
    }
  }
  else
  {
    v7 = L"NOT_FOUND";
  }
  v26 = v7;
  v16 = &v17;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v9);
  return 0;
}

```

## disassembly

```asm
0x1800040e8  mov     [rsp-8+arg_10], r8d
0x1800040ed  push    rbp
0x1800040ee  lea     rbp, [rsp-57h]
0x1800040f3  sub     rsp, 0D0h
0x1800040fa  xor     r10d, r10d
0x1800040fd  mov     [rbp+57h+var_A8], 80h
0x180004105  mov     [rbp+57h+var_98], 10h
0x18000410d  mov     edx, 10h
0x180004112  mov     [rbp+57h+var_68], 2
0x18000411a  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004121  mov     [rbp+57h+var_B0], rax
0x180004125  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCacheEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCacheEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000412c  mov     [rbp+57h+var_A0], rax
0x180004130  lea     rax, aOutputCacheLoo; "OUTPUT_CACHE_LOOKUP_END"
0x180004137  mov     [rbp+57h+var_90], rax
0x18000413b  lea     eax, [rdx-0Fh]
0x18000413e  mov     [rbp+57h+var_88], eax
0x180004141  lea     r9d, [rdx-0Ch]
0x180004145  mov     [rbp+57h+var_6C], eax
0x180004148  lea     rax, aContextid; "ContextId"
0x18000414f  mov     [rbp+57h+var_50], rax
0x180004153  lea     rax, aResult; "Result"
0x18000415a  mov     [rbp+57h+var_28], rax
0x18000415e  lea     rax, [rbp+57h+arg_10]
0x180004162  mov     [rbp+57h+var_18], rax
0x180004166  xorps   xmm0, xmm0
0x180004169  mov     [rbp+57h+var_84], r9d
0x18000416d  movdqa  [rbp+57h+var_80], xmm0
0x180004172  mov     [rbp+57h+var_70], r10d
0x180004176  mov     [rbp+57h+var_48], 48h ; 'H'
0x18000417d  mov     [rbp+57h+var_40], r10
0x180004181  mov     [rbp+57h+var_38], edx
0x180004184  mov     [rbp+57h+var_30], r10
0x180004188  mov     [rbp+57h+var_20], 13h
0x18000418f  mov     [rbp+57h+var_10], r9d
0x180004193  test    r8d, r8d
0x180004196  jz      short loc_1800041E8
0x180004198  sub     r8d, 1
0x18000419c  jz      short loc_1800041DF
0x18000419e  sub     r8d, 1
0x1800041a2  jz      short loc_1800041D6
0x1800041a4  sub     r8d, 1
0x1800041a8  jz      short loc_1800041CD
0x1800041aa  sub     r8d, 1
0x1800041ae  jz      short loc_1800041C4
0x1800041b0  cmp     r8d, 1
0x1800041b4  jz      short loc_1800041BB
0x1800041b6  mov     eax, r10d
0x1800041b9  jmp     short loc_1800041EF
0x1800041bb  lea     rax, aConditionalHea; "CONDITIONAL_HEADERS_PRESENT"
0x1800041c2  jmp     short loc_1800041EF
0x1800041c4  lea     rax, aCachingDisable; "CACHING_DISABLED"
0x1800041cb  jmp     short loc_1800041EF
0x1800041cd  lea     rax, aAcceptEncoding; "ACCEPT_ENCODING_NOT_MATCH"
0x1800041d4  jmp     short loc_1800041EF
0x1800041d6  lea     rax, aAcceptNotMatch; "ACCEPT_NOT_MATCH"
0x1800041dd  jmp     short loc_1800041EF
0x1800041df  lea     rax, aFound; "FOUND"
0x1800041e6  jmp     short loc_1800041EF
0x1800041e8  lea     rax, aNotFound; "NOT_FOUND"
0x1800041ef  mov     [rbp+57h+var_8], rax
0x1800041f3  lea     rdx, [rbp+57h+var_B0]
0x1800041f7  lea     rax, [rbp+57h+var_50]
0x1800041fb  mov     [rbp+57h+var_60], rax
0x1800041ff  mov     rax, [rcx]
0x180004202  mov     rax, [rax+10h]
0x180004206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420b  xor     eax, eax
0x18000420d  add     rsp, 0D0h
0x180004214  pop     rbp
0x180004215  retn
```
