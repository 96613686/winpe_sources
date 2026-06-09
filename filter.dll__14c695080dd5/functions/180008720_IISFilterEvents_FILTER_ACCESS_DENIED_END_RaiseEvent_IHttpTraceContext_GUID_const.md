# IISFilterEvents::FILTER_ACCESS_DENIED_END::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x180008720`
- end: `0x1800087d3`
- name: `?RaiseEvent@FILTER_ACCESS_DENIED_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004440`

## callees

- `0x18000d010`

## string_xrefs

- `0x180008760`: `FILTER_ACCESS_DENIED_END`

## pseudocode

```c
__int64 __fastcall IISFilterEvents::FILTER_ACCESS_DENIED_END::RaiseEvent(
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

  v5[1] = 8;
  v5[3] = 30;
  v11 = 1;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v5[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"FILTER_ACCESS_DENIED_END";
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
0x180008720  mov     r11, rsp
0x180008723  sub     rsp, 0B8h
0x18000872a  mov     [rsp+0B8h+var_90], 8
0x180008733  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000873a  mov     qword ptr [r11-80h], 1Eh
0x180008742  xor     edx, edx
0x180008744  mov     qword ptr [r11-50h], 1
0x18000874c  xorps   xmm0, xmm0
0x18000874f  mov     [rsp+0B8h+var_98], rax
0x180008754  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000875b  mov     [rsp+0B8h+var_88], rax
0x180008760  lea     rax, aFilterAccessDe; "FILTER_ACCESS_DENIED_END"
0x180008767  mov     [r11-78h], rax
0x18000876b  lea     rax, aContextid; "ContextId"
0x180008772  mov     [r11-38h], rax
0x180008776  lea     rax, [r11-38h]
0x18000877a  mov     [rsp+0B8h+var_58], edx
0x18000877e  mov     [rsp+0B8h+var_70], 1
0x180008786  mov     [rsp+0B8h+var_6C], 4
0x18000878e  movdqa  [rsp+0B8h+var_68], xmm0
0x180008794  mov     [rsp+0B8h+var_54], 1
0x18000879c  mov     [r11-48h], rax
0x1800087a0  mov     rax, [rcx]
0x1800087a3  mov     [r11-28h], rdx
0x1800087a7  mov     [r11-18h], rdx
0x1800087ab  lea     rdx, [rsp+0B8h+var_98]
0x1800087b0  mov     dword ptr [r11-30h], 48h ; 'H'
0x1800087b8  mov     rax, [rax+10h]
0x1800087bc  mov     dword ptr [r11-20h], 10h
0x1800087c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c9  xor     eax, eax
0x1800087cb  add     rsp, 0B8h
0x1800087d2  retn
```
