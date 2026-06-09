# IISCompressionEvents::DYNAMIC_COMPRESSION_SUCCESS::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180006d58`
- end: `0x180006e0b`
- name: `?RaiseEvent@DYNAMIC_COMPRESSION_SUCCESS@IISCompressionEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001eb0`

## callees

- `0x180008010`

## string_xrefs

- `0x180006d98`: `DYNAMIC_COMPRESSION_SUCCESS`

## pseudocode

```c
__int64 __fastcall IISCompressionEvents::DYNAMIC_COMPRESSION_SUCCESS::RaiseEvent(
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
  v5[3] = 7;
  v11 = 1;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v5[2] = &`IISCompressionEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"DYNAMIC_COMPRESSION_SUCCESS";
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
0x180006d58  mov     r11, rsp
0x180006d5b  sub     rsp, 0B8h
0x180006d62  mov     [rsp+0B8h+var_90], 40h ; '@'
0x180006d6b  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180006d72  mov     qword ptr [r11-80h], 7
0x180006d7a  xor     edx, edx
0x180006d7c  mov     qword ptr [r11-50h], 1
0x180006d84  xorps   xmm0, xmm0
0x180006d87  mov     [rsp+0B8h+var_98], rax
0x180006d8c  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCompressionEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCompressionEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180006d93  mov     [rsp+0B8h+var_88], rax
0x180006d98  lea     rax, aDynamicCompres_2; "DYNAMIC_COMPRESSION_SUCCESS"
0x180006d9f  mov     [r11-78h], rax
0x180006da3  lea     rax, aContextid; "ContextId"
0x180006daa  mov     [r11-38h], rax
0x180006dae  lea     rax, [r11-38h]
0x180006db2  mov     [rsp+0B8h+var_58], edx
0x180006db6  mov     [rsp+0B8h+var_70], 1
0x180006dbe  mov     [rsp+0B8h+var_6C], 4
0x180006dc6  movdqa  [rsp+0B8h+var_68], xmm0
0x180006dcc  mov     [rsp+0B8h+var_54], 1
0x180006dd4  mov     [r11-48h], rax
0x180006dd8  mov     rax, [rcx]
0x180006ddb  mov     [r11-28h], rdx
0x180006ddf  mov     [r11-18h], rdx
0x180006de3  lea     rdx, [rsp+0B8h+var_98]
0x180006de8  mov     dword ptr [r11-30h], 48h ; 'H'
0x180006df0  mov     rax, [rax+10h]
0x180006df4  mov     dword ptr [r11-20h], 10h
0x180006dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e01  xor     eax, eax
0x180006e03  add     rsp, 0B8h
0x180006e0a  retn
```
