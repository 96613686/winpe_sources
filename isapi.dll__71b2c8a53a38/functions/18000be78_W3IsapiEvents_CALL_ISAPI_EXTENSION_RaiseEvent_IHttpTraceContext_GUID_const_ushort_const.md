# W3IsapiEvents::CALL_ISAPI_EXTENSION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)

- ea: `0x18000be78`
- end: `0x18000bf5d`
- name: `?RaiseEvent@CALL_ISAPI_EXTENSION@W3IsapiEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z`
- size: `229`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b3d0`

## callees

- `0x18000be78`
- `0x180013010`

## string_xrefs

- `0x18000beb7`: `CALL_ISAPI_EXTENSION`
- `0x18000bed5`: `DllName`

## pseudocode

```c
__int64 __fastcall W3IsapiEvents::CALL_ISAPI_EXTENSION::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  __int64 v4; // rax
  _QWORD v6[6]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v7; // [rsp+50h] [rbp-29h]
  int v8; // [rsp+60h] [rbp-19h]
  int v9; // [rsp+64h] [rbp-15h]
  int v10; // [rsp+68h] [rbp-11h]
  _QWORD v11[2]; // [rsp+6Ch] [rbp-Dh] BYREF
  const wchar_t *v12; // [rsp+80h] [rbp+7h] BYREF
  int v13; // [rsp+88h] [rbp+Fh]
  __int64 v14; // [rsp+90h] [rbp+17h]
  int v15; // [rsp+98h] [rbp+1Fh]
  __int64 v16; // [rsp+A0h] [rbp+27h]
  const wchar_t *v17; // [rsp+A8h] [rbp+2Fh]
  int v18; // [rsp+B0h] [rbp+37h]
  const unsigned __int16 *v19; // [rsp+B8h] [rbp+3Fh]
  int v20; // [rsp+C0h] [rbp+47h]
  __int64 v21; // [rsp+C8h] [rbp+4Fh]

  v6[3] = 1;
  v6[1] = 0;
  memset(v11, 0, 12);
  v6[0] = &`WWWIsapiExtensionTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v6[2] = &`W3IsapiEvents::GetAreaGuid'::`2'::AreaGuid;
  v6[4] = L"CALL_ISAPI_EXTENSION";
  v12 = L"ContextId";
  v6[5] = 1;
  v17 = L"DllName";
  v10 = 2;
  v7 = 0;
  v8 = 0;
  v9 = 1;
  v13 = 72;
  v14 = 0;
  v15 = 16;
  v16 = 0;
  v18 = 31;
  v19 = a3;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v3 = 2 * v4 + 2;
  }
  else
  {
    v3 = 0;
  }
  v20 = v3;
  v21 = 0;
  *(_QWORD *)((char *)v11 + 4) = &v12;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v6);
  return 0;
}

```

## disassembly

```asm
0x18000be78  push    rbp
0x18000be7a  lea     rbp, [rsp-57h]
0x18000be7f  sub     rsp, 0D0h
0x18000be86  xor     eax, eax
0x18000be88  mov     [rbp+57h+var_98], 1
0x18000be90  mov     [rbp+57h+var_A8], rax
0x18000be94  xor     r9d, r9d
0x18000be97  mov     [rbp+57h+var_64], rax
0x18000be9b  xorps   xmm0, xmm0
0x18000be9e  mov     [rbp+57h+var_5C], eax
0x18000bea1  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWIsapiExtensionTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWIsapiExtensionTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000bea8  mov     [rbp+57h+var_B0], rax
0x18000beac  lea     rax, ?AreaGuid@?1??GetAreaGuid@W3IsapiEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `W3IsapiEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000beb3  mov     [rbp+57h+var_A0], rax
0x18000beb7  lea     rax, aCallIsapiExten; "CALL_ISAPI_EXTENSION"
0x18000bebe  mov     [rbp+57h+var_90], rax
0x18000bec2  lea     rax, aContextid; "ContextId"
0x18000bec9  mov     [rbp+57h+var_50], rax
0x18000becd  lea     edx, [r9+1]
0x18000bed1  mov     [rbp+57h+var_88], rdx
0x18000bed5  lea     rax, aDllname; "DllName"
0x18000bedc  mov     [rbp+57h+var_28], rax
0x18000bee0  mov     [rbp+57h+var_68], 2
0x18000bee7  movdqa  [rbp+57h+var_80], xmm0
0x18000beec  mov     [rbp+57h+var_70], r9d
0x18000bef0  mov     [rbp+57h+var_6C], edx
0x18000bef3  mov     [rbp+57h+var_48], 48h ; 'H'
0x18000befa  mov     [rbp+57h+var_40], r9
0x18000befe  mov     [rbp+57h+var_38], 10h
0x18000bf05  mov     [rbp+57h+var_30], r9
0x18000bf09  mov     [rbp+57h+var_20], 1Fh
0x18000bf10  mov     [rbp+57h+var_18], r8
0x18000bf14  test    r8, r8
0x18000bf17  jnz     short loc_18000BF1E
0x18000bf19  mov     eax, r9d
0x18000bf1c  jmp     short loc_18000BF33
0x18000bf1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bf22  inc     rax
0x18000bf25  cmp     [r8+rax*2], r9w
0x18000bf2a  jnz     short loc_18000BF22
0x18000bf2c  lea     eax, ds:2[rax*2]
0x18000bf33  mov     [rbp+57h+var_10], eax
0x18000bf36  lea     rdx, [rbp+57h+var_B0]
0x18000bf3a  lea     rax, [rbp+57h+var_50]
0x18000bf3e  mov     [rbp+57h+var_8], r9
0x18000bf42  mov     [rbp+57h+var_64+4], rax
0x18000bf46  mov     rax, [rcx]
0x18000bf49  mov     rax, [rax+10h]
0x18000bf4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf52  xor     eax, eax
0x18000bf54  add     rsp, 0D0h
0x18000bf5b  pop     rbp
0x18000bf5c  retn
```
