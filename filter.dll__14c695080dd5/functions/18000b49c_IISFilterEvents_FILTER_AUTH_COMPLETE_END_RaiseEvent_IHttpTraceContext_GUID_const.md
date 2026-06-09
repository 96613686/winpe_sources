# IISFilterEvents::FILTER_AUTH_COMPLETE_END::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x18000b49c`
- end: `0x18000b546`
- name: `?RaiseEvent@FILTER_AUTH_COMPLETE_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004440`

## callees

- `0x18000d010`

## string_xrefs

- `0x18000b4d4`: `FILTER_AUTH_COMPLETE_END`

## pseudocode

```c
__int64 __fastcall IISFilterEvents::FILTER_AUTH_COMPLETE_END::RaiseEvent(
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

  v5[1] = 8;
  v9 = 0;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = 0;
  v5[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"FILTER_AUTH_COMPLETE_END";
  v6 = 1;
  v10 = 1;
  v13 = L"ContextId";
  v12 = &v13;
  v2 = *(_QWORD *)a1;
  v17 = 0;
  v5[3] = 20;
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
0x18000b49c  push    rbp
0x18000b49e  lea     rbp, [rsp-57h]
0x18000b4a3  sub     rsp, 0B0h
0x18000b4aa  xor     edx, edx
0x18000b4ac  mov     [rbp+57h+var_88], 8
0x18000b4b4  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000b4bb  mov     [rbp+57h+var_50], edx
0x18000b4be  mov     [rbp+57h+var_90], rax
0x18000b4c2  xorps   xmm0, xmm0
0x18000b4c5  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000b4cc  mov     [rbp+57h+var_20], rdx
0x18000b4d0  mov     [rbp+57h+var_80], rax
0x18000b4d4  lea     rax, aFilterAuthComp_0; "FILTER_AUTH_COMPLETE_END"
0x18000b4db  mov     [rbp+57h+var_70], rax
0x18000b4df  mov     eax, 1
0x18000b4e4  mov     [rbp+57h+var_68], eax
0x18000b4e7  mov     [rbp+57h+var_4C], eax
0x18000b4ea  lea     rax, aContextid; "ContextId"
0x18000b4f1  mov     [rbp+57h+var_30], rax
0x18000b4f5  lea     rax, [rbp+57h+var_30]
0x18000b4f9  mov     [rbp+57h+var_40], rax
0x18000b4fd  mov     rax, [rcx]
0x18000b500  mov     [rbp+57h+var_10], rdx
0x18000b504  lea     rdx, [rbp+57h+var_90]
0x18000b508  mov     [rbp+57h+var_78], 14h
0x18000b510  mov     [rbp+57h+var_48], 1
0x18000b518  mov     rax, [rax+10h]
0x18000b51c  mov     [rbp+57h+var_64], 4
0x18000b523  movdqa  [rbp+57h+var_60], xmm0
0x18000b528  mov     [rbp+57h+var_28], 48h ; 'H'
0x18000b52f  mov     [rbp+57h+var_18], 10h
0x18000b536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b53b  xor     eax, eax
0x18000b53d  add     rsp, 0B0h
0x18000b544  pop     rbp
0x18000b545  retn
```
