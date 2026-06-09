# W3IsapiEvents::NOTIFY_ISAPI_COMPLETION::RaiseEvent(IHttpTraceContext *,_GUID const *)

- ea: `0x18000c208`
- end: `0x18000c2ae`
- name: `?RaiseEvent@NOTIFY_ISAPI_COMPLETION@W3IsapiEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bd8c`

## callees

- `0x180013010`

## string_xrefs

- `0x18000c246`: `NOTIFY_ISAPI_COMPLETION`

## pseudocode

```c
__int64 __fastcall W3IsapiEvents::NOTIFY_ISAPI_COMPLETION::RaiseEvent(
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

  v5[3] = 3;
  v5[1] = 0;
  v9 = 0;
  v5[0] = &`WWWIsapiExtensionTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v15 = 0;
  v5[2] = &`W3IsapiEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"NOTIFY_ISAPI_COMPLETION";
  v6 = 1;
  v10 = 1;
  v13 = L"ContextId";
  v12 = &v13;
  v2 = *(_QWORD *)a1;
  v17 = 0;
  v11 = 1;
  v7 = 4;
  v3 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v2 + 16);
  v8 = 0;
  v14 = 72;
  v16 = 16;
  v3(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x18000c208  push    rbp
0x18000c20a  lea     rbp, [rsp-57h]
0x18000c20f  sub     rsp, 0B0h
0x18000c216  xor     eax, eax
0x18000c218  mov     [rbp+57h+var_78], 3
0x18000c220  mov     [rbp+57h+var_88], rax
0x18000c224  xor     edx, edx
0x18000c226  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWIsapiExtensionTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWIsapiExtensionTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c22d  mov     [rbp+57h+var_50], edx
0x18000c230  mov     [rbp+57h+var_90], rax
0x18000c234  xorps   xmm0, xmm0
0x18000c237  lea     rax, ?AreaGuid@?1??GetAreaGuid@W3IsapiEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `W3IsapiEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000c23e  mov     [rbp+57h+var_20], rdx
0x18000c242  mov     [rbp+57h+var_80], rax
0x18000c246  lea     rax, aNotifyIsapiCom; "NOTIFY_ISAPI_COMPLETION"
0x18000c24d  mov     [rbp+57h+var_70], rax
0x18000c251  lea     eax, [rdx+1]
0x18000c254  mov     [rbp+57h+var_68], eax
0x18000c257  mov     [rbp+57h+var_4C], eax
0x18000c25a  lea     rax, aContextid; "ContextId"
0x18000c261  mov     [rbp+57h+var_30], rax
0x18000c265  lea     rax, [rbp+57h+var_30]
0x18000c269  mov     [rbp+57h+var_40], rax
0x18000c26d  mov     rax, [rcx]
0x18000c270  mov     [rbp+57h+var_10], rdx
0x18000c274  lea     rdx, [rbp+57h+var_90]
0x18000c278  mov     [rbp+57h+var_48], 1
0x18000c280  mov     [rbp+57h+var_64], 4
0x18000c287  mov     rax, [rax+10h]
0x18000c28b  movdqa  [rbp+57h+var_60], xmm0
0x18000c290  mov     [rbp+57h+var_28], 48h ; 'H'
0x18000c297  mov     [rbp+57h+var_18], 10h
0x18000c29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a3  xor     eax, eax
0x18000c2a5  add     rsp, 0B0h
0x18000c2ac  pop     rbp
0x18000c2ad  retn
```
