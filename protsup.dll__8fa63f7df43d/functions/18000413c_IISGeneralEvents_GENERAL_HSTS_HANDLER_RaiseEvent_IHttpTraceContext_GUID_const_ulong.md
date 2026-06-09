# IISGeneralEvents::GENERAL_HSTS_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)

- ea: `0x18000413c`
- end: `0x180004229`
- name: `?RaiseEvent@GENERAL_HSTS_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001580`

## callees

- `0x18000413c`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall IISGeneralEvents::GENERAL_HSTS_HANDLER::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3)
{
  const wchar_t *v3; // rax
  _QWORD v5[6]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v6; // [rsp+50h] [rbp-29h]
  int v7; // [rsp+60h] [rbp-19h]
  int v8; // [rsp+64h] [rbp-15h]
  __int64 v9; // [rsp+68h] [rbp-11h]
  const wchar_t **v10; // [rsp+70h] [rbp-9h]
  const wchar_t *v11; // [rsp+80h] [rbp+7h] BYREF
  int v12; // [rsp+88h] [rbp+Fh]
  __int64 v13; // [rsp+90h] [rbp+17h]
  int v14; // [rsp+98h] [rbp+1Fh]
  __int64 v15; // [rsp+A0h] [rbp+27h]
  const wchar_t *v16; // [rsp+A8h] [rbp+2Fh]
  int v17; // [rsp+B0h] [rbp+37h]
  int *v18; // [rsp+B8h] [rbp+3Fh]
  int v19; // [rsp+C0h] [rbp+47h]
  const wchar_t *v20; // [rsp+C8h] [rbp+4Fh]
  int v21; // [rsp+F0h] [rbp+77h] BYREF

  v21 = a3;
  v5[3] = 18;
  v5[1] = 0;
  v9 = 2;
  v5[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v5[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
  v5[4] = L"GENERAL_HSTS_HANDLER";
  v11 = L"ContextId";
  v16 = L"HstsOperation";
  v18 = &v21;
  v5[5] = 1;
  v6 = 0;
  v7 = 0;
  v8 = 1;
  v12 = 72;
  v13 = 0;
  v14 = 16;
  v15 = 0;
  v17 = 19;
  v19 = 4;
  if ( a3 )
  {
    if ( a3 == 1 )
      v3 = L"HSTS_ADD_HSTS_RESPONSE_HEADER";
    else
      v3 = 0;
  }
  else
  {
    v3 = L"HSTS_REDIRECT_HTTP_TO_HTTPS";
  }
  v20 = v3;
  v10 = &v11;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v5);
  return 0;
}

```

## disassembly

```asm
0x18000413c  mov     [rsp-8+arg_10], r8d
0x180004141  push    rbp
0x180004142  lea     rbp, [rsp-57h]
0x180004147  sub     rsp, 0D0h
0x18000414e  xor     eax, eax
0x180004150  mov     [rbp+57h+var_98], 12h
0x180004158  mov     [rbp+57h+var_A8], rax
0x18000415c  xor     edx, edx
0x18000415e  mov     [rbp+57h+var_68], 2
0x180004166  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000416d  mov     [rbp+57h+var_B0], rax
0x180004171  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180004178  mov     [rbp+57h+var_A0], rax
0x18000417c  lea     rax, aGeneralHstsHan; "GENERAL_HSTS_HANDLER"
0x180004183  mov     [rbp+57h+var_90], rax
0x180004187  lea     rax, aContextid; "ContextId"
0x18000418e  mov     [rbp+57h+var_50], rax
0x180004192  lea     rax, aHstsoperation; "HstsOperation"
0x180004199  mov     [rbp+57h+var_28], rax
0x18000419d  lea     rax, [rbp+57h+arg_10]
0x1800041a1  mov     [rbp+57h+var_18], rax
0x1800041a5  xorps   xmm0, xmm0
0x1800041a8  mov     [rbp+57h+var_88], 1
0x1800041b0  movdqa  [rbp+57h+var_80], xmm0
0x1800041b5  mov     [rbp+57h+var_70], edx
0x1800041b8  mov     [rbp+57h+var_6C], 1
0x1800041bf  mov     [rbp+57h+var_48], 48h ; 'H'
0x1800041c6  mov     [rbp+57h+var_40], rdx
0x1800041ca  mov     [rbp+57h+var_38], 10h
0x1800041d1  mov     [rbp+57h+var_30], rdx
0x1800041d5  mov     [rbp+57h+var_20], 13h
0x1800041dc  mov     [rbp+57h+var_10], 4
0x1800041e3  test    r8d, r8d
0x1800041e6  jz      short loc_1800041FB
0x1800041e8  cmp     r8d, 1
0x1800041ec  jz      short loc_1800041F2
0x1800041ee  mov     eax, edx
0x1800041f0  jmp     short loc_180004202
0x1800041f2  lea     rax, aHstsAddHstsRes; "HSTS_ADD_HSTS_RESPONSE_HEADER"
0x1800041f9  jmp     short loc_180004202
0x1800041fb  lea     rax, aHstsRedirectHt; "HSTS_REDIRECT_HTTP_TO_HTTPS"
0x180004202  mov     [rbp+57h+var_8], rax
0x180004206  lea     rdx, [rbp+57h+var_B0]
0x18000420a  lea     rax, [rbp+57h+var_50]
0x18000420e  mov     [rbp+57h+var_60], rax
0x180004212  mov     rax, [rcx]
0x180004215  mov     rax, [rax+10h]
0x180004219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000421e  xor     eax, eax
0x180004220  add     rsp, 0D0h
0x180004227  pop     rbp
0x180004228  retn
```
