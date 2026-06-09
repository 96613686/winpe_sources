# IISCompressionEvents::STATIC_COMPRESSION_END::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180008568`
- end: `0x18000861b`
- name: `?RaiseEvent@STATIC_COMPRESSION_END@IISCompressionEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001310`

## callees

- `0x180009010`

## string_xrefs

- `0x1800085a8`: `STATIC_COMPRESSION_END`

## pseudocode

```c
__int64 __fastcall IISCompressionEvents::STATIC_COMPRESSION_END::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2)
{
  __int64 v2; // rax
  void (__fastcall *v3)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v5[5]; // [rsp+20h] [rbp-98h] BYREF
  int v6; // [rsp+48h] [rbp-70h]
  int v7; // [rsp+4Ch] [rbp-6Ch]
  __int128 v8; // [rsp+50h] [rbp-68h]
  int v9; // [rsp+60h] [rbp-58h]
  int v10; // [rsp+64h] [rbp-54h]
  __int64 v11; // [rsp+68h] [rbp-50h]
  const wchar_t **v12; // [rsp+70h] [rbp-48h]
  const wchar_t *v13; // [rsp+80h] [rbp-38h] BYREF
  int v14; // [rsp+88h] [rbp-30h]
  __int64 v15; // [rsp+90h] [rbp-28h]
  int v16; // [rsp+98h] [rbp-20h]
  __int64 v17; // [rsp+A0h] [rbp-18h]

  v5[1] = 64;
  v5[3] = 11;
  v11 = 1;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v5[2] = &`IISCompressionEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"STATIC_COMPRESSION_END";
  v13 = L"ContextId";
  v9 = 0;
  v6 = 1;
  v7 = 4;
  v8 = 0;
  v10 = 1;
  v12 = &v13;
  v2 = *(_QWORD *)a1;
  v15 = 0;
  v17 = 0;
  v14 = 72;
  v3 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16);
  v16 = 16;
  v3(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x180008568  mov     r11, rsp
0x18000856b  sub     rsp, 0B8h
0x180008572  mov     [rsp+0B8h+var_90], 40h ; '@'
0x18000857b  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180008582  mov     qword ptr [r11-80h], 0Bh
0x18000858a  xor     edx, edx
0x18000858c  mov     qword ptr [r11-50h], 1
0x180008594  xorps   xmm0, xmm0
0x180008597  mov     [rsp+0B8h+var_98], rax
0x18000859c  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCompressionEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCompressionEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800085a3  mov     [rsp+0B8h+var_88], rax
0x1800085a8  lea     rax, aStaticCompress_1; "STATIC_COMPRESSION_END"
0x1800085af  mov     [r11-78h], rax
0x1800085b3  lea     rax, aContextid; "ContextId"
0x1800085ba  mov     [r11-38h], rax
0x1800085be  lea     rax, [r11-38h]
0x1800085c2  mov     [rsp+0B8h+var_58], edx
0x1800085c6  mov     [rsp+0B8h+var_70], 1
0x1800085ce  mov     [rsp+0B8h+var_6C], 4
0x1800085d6  movdqa  [rsp+0B8h+var_68], xmm0
0x1800085dc  mov     [rsp+0B8h+var_54], 1
0x1800085e4  mov     [r11-48h], rax
0x1800085e8  mov     rax, [rcx]
0x1800085eb  mov     [r11-28h], rdx
0x1800085ef  mov     [r11-18h], rdx
0x1800085f3  lea     rdx, [rsp+0B8h+var_98]
0x1800085f8  mov     dword ptr [r11-30h], 48h ; 'H'
0x180008600  mov     rax, [rax+10h]
0x180008604  mov     dword ptr [r11-20h], 10h
0x18000860c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008611  xor     eax, eax
0x180008613  add     rsp, 0B8h
0x18000861a  retn
```
