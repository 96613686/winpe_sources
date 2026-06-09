# IISSecurityEvents::SECURITY_DENIED_BY_ISAPI_RESTRICTION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)

- ea: `0x180012278`
- end: `0x180012367`
- name: `?RaiseEvent@SECURITY_DENIED_BY_ISAPI_RESTRICTION@IISSecurityEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z`
- size: `239`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012188`

## callees

- `0x180012278`
- `0x180013010`

## string_xrefs

- `0x1800122b0`: `SECURITY_DENIED_BY_ISAPI_RESTRICTION`

## pseudocode

```c
__int64 __fastcall IISSecurityEvents::SECURITY_DENIED_BY_ISAPI_RESTRICTION::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  __int64 v4; // rax
  _QWORD v6[5]; // [rsp+20h] [rbp-59h] BYREF
  int v7; // [rsp+48h] [rbp-31h]
  int v8; // [rsp+4Ch] [rbp-2Dh]
  __int128 v9; // [rsp+50h] [rbp-29h]
  int v10; // [rsp+60h] [rbp-19h]
  int v11; // [rsp+64h] [rbp-15h]
  int v12; // [rsp+68h] [rbp-11h]
  _QWORD v13[2]; // [rsp+6Ch] [rbp-Dh] BYREF
  const wchar_t *v14; // [rsp+80h] [rbp+7h] BYREF
  int v15; // [rsp+88h] [rbp+Fh]
  __int64 v16; // [rsp+90h] [rbp+17h]
  int v17; // [rsp+98h] [rbp+1Fh]
  __int64 v18; // [rsp+A0h] [rbp+27h]
  const wchar_t *v19; // [rsp+A8h] [rbp+2Fh]
  int v20; // [rsp+B0h] [rbp+37h]
  const unsigned __int16 *v21; // [rsp+B8h] [rbp+3Fh]
  int v22; // [rsp+C0h] [rbp+47h]
  __int64 v23; // [rsp+C8h] [rbp+4Fh]

  v6[1] = 4;
  memset(v13, 0, 12);
  v6[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v6[2] = &`IISSecurityEvents::GetAreaGuid'::`2'::AreaGuid;
  v6[4] = L"SECURITY_DENIED_BY_ISAPI_RESTRICTION";
  v6[3] = 16;
  v8 = 3;
  v12 = 2;
  v9 = 0;
  v7 = 1;
  v11 = 1;
  v14 = L"ContextId";
  v19 = L"ImageName";
  v10 = 0;
  v15 = 72;
  v16 = 0;
  v17 = 16;
  v18 = 0;
  v20 = 31;
  v21 = a3;
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
  v22 = v3;
  v23 = 0;
  *(_QWORD *)((char *)v13 + 4) = &v14;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v6);
  return 0;
}

```

## disassembly

```asm
0x180012278  push    rbp
0x18001227a  lea     rbp, [rsp-57h]
0x18001227f  sub     rsp, 0D0h
0x180012286  xor     eax, eax
0x180012288  mov     [rbp+57h+var_A8], 4
0x180012290  mov     [rbp+57h+var_64], rax
0x180012294  xor     r9d, r9d
0x180012297  mov     [rbp+57h+var_5C], eax
0x18001229a  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800122a1  mov     [rbp+57h+var_B0], rax
0x1800122a5  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISSecurityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISSecurityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800122ac  mov     [rbp+57h+var_A0], rax
0x1800122b0  lea     rax, aSecurityDenied; "SECURITY_DENIED_BY_ISAPI_RESTRICTION"
0x1800122b7  mov     [rbp+57h+var_90], rax
0x1800122bb  mov     edx, 10h
0x1800122c0  mov     [rbp+57h+var_98], 10h
0x1800122c8  xorps   xmm0, xmm0
0x1800122cb  mov     [rbp+57h+var_84], 3
0x1800122d2  mov     [rbp+57h+var_68], 2
0x1800122d9  movdqa  [rbp+57h+var_80], xmm0
0x1800122de  lea     eax, [rdx-0Fh]
0x1800122e1  mov     [rbp+57h+var_88], eax
0x1800122e4  mov     [rbp+57h+var_6C], eax
0x1800122e7  lea     rax, aContextid; "ContextId"
0x1800122ee  mov     [rbp+57h+var_50], rax
0x1800122f2  lea     rax, aImagename; "ImageName"
0x1800122f9  mov     [rbp+57h+var_28], rax
0x1800122fd  mov     [rbp+57h+var_70], r9d
0x180012301  mov     [rbp+57h+var_48], 48h ; 'H'
0x180012308  mov     [rbp+57h+var_40], r9
0x18001230c  mov     [rbp+57h+var_38], edx
0x18001230f  mov     [rbp+57h+var_30], r9
0x180012313  mov     [rbp+57h+var_20], 1Fh
0x18001231a  mov     [rbp+57h+var_18], r8
0x18001231e  test    r8, r8
0x180012321  jnz     short loc_180012328
0x180012323  mov     eax, r9d
0x180012326  jmp     short loc_18001233D
0x180012328  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001232c  inc     rax
0x18001232f  cmp     [r8+rax*2], r9w
0x180012334  jnz     short loc_18001232C
0x180012336  lea     eax, ds:2[rax*2]
0x18001233d  mov     [rbp+57h+var_10], eax
0x180012340  lea     rdx, [rbp+57h+var_B0]
0x180012344  lea     rax, [rbp+57h+var_50]
0x180012348  mov     [rbp+57h+var_8], r9
0x18001234c  mov     [rbp+57h+var_64+4], rax
0x180012350  mov     rax, [rcx]
0x180012353  mov     rax, [rax+10h]
0x180012357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001235c  xor     eax, eax
0x18001235e  add     rsp, 0D0h
0x180012365  pop     rbp
0x180012366  retn
```
