# W3IsapiEvents::ISAPI_EXTENSION_DONE::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x18000c0b4`
- end: `0x18000c154`
- name: `?RaiseEvent@ISAPI_EXTENSION_DONE@W3IsapiEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f440`

## callees

- `0x180013010`

## string_xrefs

- `0x18000c0f2`: `ISAPI_EXTENSION_DONE`

## pseudocode

```c
__int64 __fastcall W3IsapiEvents::ISAPI_EXTENSION_DONE::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2)
{
  __int64 v2; // rax
  void (__fastcall *v3)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v5[6]; // [rsp+20h] [rbp-39h] BYREF
  __int128 v6; // [rsp+50h] [rbp-9h]
  int v7; // [rsp+60h] [rbp+7h]
  int v8; // [rsp+64h] [rbp+Bh]
  __int64 v9; // [rsp+68h] [rbp+Fh]
  const wchar_t **v10; // [rsp+70h] [rbp+17h]
  const wchar_t *v11; // [rsp+80h] [rbp+27h] BYREF
  int v12; // [rsp+88h] [rbp+2Fh]
  __int64 v13; // [rsp+90h] [rbp+37h]
  int v14; // [rsp+98h] [rbp+3Fh]
  __int64 v15; // [rsp+A0h] [rbp+47h]

  v5[3] = 2;
  v5[1] = 0;
  v7 = 0;
  v5[0] = &`WWWIsapiExtensionTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v13 = 0;
  v5[2] = &`W3IsapiEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"ISAPI_EXTENSION_DONE";
  v5[5] = 1;
  v8 = 1;
  v11 = L"ContextId";
  v10 = &v11;
  v2 = *(_QWORD *)a1;
  v15 = 0;
  v9 = 1;
  v6 = 0;
  v3 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16);
  v12 = 72;
  v14 = 16;
  v3(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x18000c0b4  push    rbp
0x18000c0b6  lea     rbp, [rsp-57h]
0x18000c0bb  sub     rsp, 0B0h
0x18000c0c2  xor     eax, eax
0x18000c0c4  mov     [rbp+57h+var_78], 2
0x18000c0cc  mov     [rbp+57h+var_88], rax
0x18000c0d0  xor     edx, edx
0x18000c0d2  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWIsapiExtensionTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWIsapiExtensionTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c0d9  mov     [rbp+57h+var_50], edx
0x18000c0dc  mov     [rbp+57h+var_90], rax
0x18000c0e0  xorps   xmm0, xmm0
0x18000c0e3  lea     rax, ?AreaGuid@?1??GetAreaGuid@W3IsapiEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `W3IsapiEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000c0ea  mov     [rbp+57h+var_20], rdx
0x18000c0ee  mov     [rbp+57h+var_80], rax
0x18000c0f2  lea     rax, aIsapiExtension; "ISAPI_EXTENSION_DONE"
0x18000c0f9  mov     [rbp+57h+var_70], rax
0x18000c0fd  lea     eax, [rdx+1]
0x18000c100  mov     [rbp+57h+var_68], rax
0x18000c104  mov     [rbp+57h+var_4C], eax
0x18000c107  lea     rax, aContextid; "ContextId"
0x18000c10e  mov     [rbp+57h+var_30], rax
0x18000c112  lea     rax, [rbp+57h+var_30]
0x18000c116  mov     [rbp+57h+var_40], rax
0x18000c11a  mov     rax, [rcx]
0x18000c11d  mov     [rbp+57h+var_10], rdx
0x18000c121  lea     rdx, [rbp+57h+var_90]
0x18000c125  mov     [rbp+57h+var_48], 1
0x18000c12d  movdqa  [rbp+57h+var_60], xmm0
0x18000c132  mov     rax, [rax+10h]
0x18000c136  mov     [rbp+57h+var_28], 48h ; 'H'
0x18000c13d  mov     [rbp+57h+var_18], 10h
0x18000c144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c149  xor     eax, eax
0x18000c14b  add     rsp, 0B0h
0x18000c152  pop     rbp
0x18000c153  retn
```
