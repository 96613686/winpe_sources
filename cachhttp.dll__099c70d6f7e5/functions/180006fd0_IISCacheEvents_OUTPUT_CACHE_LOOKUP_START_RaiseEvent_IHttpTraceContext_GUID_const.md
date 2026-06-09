# IISCacheEvents::OUTPUT_CACHE_LOOKUP_START::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180006fd0`
- end: `0x18000707a`
- name: `?RaiseEvent@OUTPUT_CACHE_LOOKUP_START@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001280`

## callees

- `0x180009010`

## string_xrefs

- `0x180007008`: `OUTPUT_CACHE_LOOKUP_START`

## pseudocode

```c
__int64 __fastcall IISCacheEvents::OUTPUT_CACHE_LOOKUP_START::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2)
{
  __int64 v2; // rax
  void (__fastcall *v3)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v5[5]; // [rsp+20h] [rbp-39h] BYREF
  int v6; // [rsp+48h] [rbp-11h]
  int v7; // [rsp+4Ch] [rbp-Dh]
  __int128 v8; // [rsp+50h] [rbp-9h]
  int v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+64h] [rbp+Bh]
  __int64 v11; // [rsp+68h] [rbp+Fh]
  const wchar_t **v12; // [rsp+70h] [rbp+17h]
  const wchar_t *v13; // [rsp+80h] [rbp+27h] BYREF
  int v14; // [rsp+88h] [rbp+2Fh]
  __int64 v15; // [rsp+90h] [rbp+37h]
  int v16; // [rsp+98h] [rbp+3Fh]
  __int64 v17; // [rsp+A0h] [rbp+47h]

  v5[1] = 128;
  v9 = 0;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = 0;
  v5[2] = &`IISCacheEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"OUTPUT_CACHE_LOOKUP_START";
  v6 = 1;
  v10 = 1;
  v13 = L"ContextId";
  v12 = &v13;
  v2 = *(_QWORD *)a1;
  v17 = 0;
  v5[3] = 15;
  v11 = 1;
  v3 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16);
  v7 = 4;
  v8 = 0;
  v14 = 72;
  v16 = 16;
  v3(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x180006fd0  push    rbp
0x180006fd2  lea     rbp, [rsp-57h]
0x180006fd7  sub     rsp, 0B0h
0x180006fde  xor     edx, edx
0x180006fe0  mov     [rbp+57h+var_88], 80h
0x180006fe8  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006fef  mov     [rbp+57h+var_50], edx
0x180006ff2  mov     [rbp+57h+var_90], rax
0x180006ff6  xorps   xmm0, xmm0
0x180006ff9  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCacheEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCacheEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180007000  mov     [rbp+57h+var_20], rdx
0x180007004  mov     [rbp+57h+var_80], rax
0x180007008  lea     rax, aOutputCacheLoo_0; "OUTPUT_CACHE_LOOKUP_START"
0x18000700f  mov     [rbp+57h+var_70], rax
0x180007013  mov     eax, 1
0x180007018  mov     [rbp+57h+var_68], eax
0x18000701b  mov     [rbp+57h+var_4C], eax
0x18000701e  lea     rax, aContextid; "ContextId"
0x180007025  mov     [rbp+57h+var_30], rax
0x180007029  lea     rax, [rbp+57h+var_30]
0x18000702d  mov     [rbp+57h+var_40], rax
0x180007031  mov     rax, [rcx]
0x180007034  mov     [rbp+57h+var_10], rdx
0x180007038  lea     rdx, [rbp+57h+var_90]
0x18000703c  mov     [rbp+57h+var_78], 0Fh
0x180007044  mov     [rbp+57h+var_48], 1
0x18000704c  mov     rax, [rax+10h]
0x180007050  mov     [rbp+57h+var_64], 4
0x180007057  movdqa  [rbp+57h+var_60], xmm0
0x18000705c  mov     [rbp+57h+var_28], 48h ; 'H'
0x180007063  mov     [rbp+57h+var_18], 10h
0x18000706a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000706f  xor     eax, eax
0x180007071  add     rsp, 0B0h
0x180007078  pop     rbp
0x180007079  retn
```
