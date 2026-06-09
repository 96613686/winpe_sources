# IISCacheEvents::OUTPUT_CACHE_UPDATE_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x180007080`
- end: `0x18000715c`
- name: `?RaiseEvent@OUTPUT_CACHE_UPDATE_END@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001280`

## callees

- `0x1800073b4`
- `0x180009010`

## string_xrefs

- `0x1800070c7`: `OUTPUT_CACHE_UPDATE_END`

## pseudocode

```c
__int64 __fastcall IISCacheEvents::OUTPUT_CACHE_UPDATE_END::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        unsigned int a3)
{
  __int64 v3; // r9
  _QWORD v5[5]; // [rsp+20h] [rbp-59h] BYREF
  int v6; // [rsp+48h] [rbp-31h]
  int v7; // [rsp+4Ch] [rbp-2Dh]
  __int128 v8; // [rsp+50h] [rbp-29h]
  int v9; // [rsp+60h] [rbp-19h]
  int v10; // [rsp+64h] [rbp-15h]
  __int64 v11; // [rsp+68h] [rbp-11h]
  const wchar_t **v12; // [rsp+70h] [rbp-9h]
  const wchar_t *v13; // [rsp+80h] [rbp+7h] BYREF
  int v14; // [rsp+88h] [rbp+Fh]
  __int64 v15; // [rsp+90h] [rbp+17h]
  int v16; // [rsp+98h] [rbp+1Fh]
  __int64 v17; // [rsp+A0h] [rbp+27h]
  const wchar_t *v18; // [rsp+A8h] [rbp+2Fh]
  int v19; // [rsp+B0h] [rbp+37h]
  unsigned int *v20; // [rsp+B8h] [rbp+3Fh]
  int v21; // [rsp+C0h] [rbp+47h]
  const wchar_t *v22; // [rsp+C8h] [rbp+4Fh]
  unsigned int v23; // [rsp+F0h] [rbp+77h] BYREF

  v23 = a3;
  v5[1] = 128;
  v5[3] = 18;
  v9 = 0;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = 0;
  v5[2] = &`IISCacheEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"OUTPUT_CACHE_UPDATE_END";
  v6 = 1;
  v10 = 1;
  v17 = 0;
  v11 = 2;
  v7 = 4;
  v13 = L"ContextId";
  v18 = L"Result";
  v20 = &v23;
  v8 = 0;
  v14 = 72;
  v16 = 16;
  v19 = 19;
  v21 = 4;
  v22 = IISCacheEvents::OUTPUT_CACHE_UPDATE_END::TranslateEnumResultToString(a3);
  v12 = &v13;
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v3 + 16LL))(v3, v5);
  return 0;
}

```

## disassembly

```asm
0x180007080  mov     [rsp-8+arg_10], r8d
0x180007085  push    rbp
0x180007086  lea     rbp, [rsp-57h]
0x18000708b  sub     rsp, 0D0h
0x180007092  mov     r9, rcx
0x180007095  mov     [rbp+57h+var_A8], 80h
0x18000709d  xor     ecx, ecx
0x18000709f  mov     [rbp+57h+var_98], 12h
0x1800070a7  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800070ae  mov     [rbp+57h+var_70], ecx
0x1800070b1  mov     [rbp+57h+var_B0], rax
0x1800070b5  xorps   xmm0, xmm0
0x1800070b8  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCacheEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCacheEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800070bf  mov     [rbp+57h+var_40], rcx
0x1800070c3  mov     [rbp+57h+var_A0], rax
0x1800070c7  lea     rax, aOutputCacheUpd_0; "OUTPUT_CACHE_UPDATE_END"
0x1800070ce  mov     [rbp+57h+var_90], rax
0x1800070d2  mov     eax, 1
0x1800070d7  mov     [rbp+57h+var_88], eax
0x1800070da  mov     [rbp+57h+var_6C], eax
0x1800070dd  mov     [rbp+57h+var_30], rcx
0x1800070e1  mov     ecx, r8d
0x1800070e4  lea     edx, [rax+3]
0x1800070e7  mov     [rbp+57h+var_68], 2
0x1800070ef  lea     rax, aContextid; "ContextId"
0x1800070f6  mov     [rbp+57h+var_84], edx
0x1800070f9  mov     [rbp+57h+var_50], rax
0x1800070fd  lea     rax, aResult; "Result"
0x180007104  mov     [rbp+57h+var_28], rax
0x180007108  lea     rax, [rbp+57h+arg_10]
0x18000710c  mov     [rbp+57h+var_18], rax
0x180007110  movdqa  [rbp+57h+var_80], xmm0
0x180007115  mov     [rbp+57h+var_48], 48h ; 'H'
0x18000711c  mov     [rbp+57h+var_38], 10h
0x180007123  mov     [rbp+57h+var_20], 13h
0x18000712a  mov     [rbp+57h+var_10], edx
0x18000712d  call    ?TranslateEnumResultToString@OUTPUT_CACHE_UPDATE_END@IISCacheEvents@@SAPEBGW4enumResult@12@@Z; IISCacheEvents::OUTPUT_CACHE_UPDATE_END::TranslateEnumResultToString(IISCacheEvents::OUTPUT_CACHE_UPDATE_END::enumResult)
0x180007132  mov     [rbp+57h+var_8], rax
0x180007136  lea     rdx, [rbp+57h+var_B0]
0x18000713a  lea     rax, [rbp+57h+var_50]
0x18000713e  mov     rcx, r9
0x180007141  mov     [rbp+57h+var_60], rax
0x180007145  mov     rax, [r9]
0x180007148  mov     rax, [rax+10h]
0x18000714c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007151  xor     eax, eax
0x180007153  add     rsp, 0D0h
0x18000715a  pop     rbp
0x18000715b  retn
```
