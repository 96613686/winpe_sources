# IISSecurityEvents::SECURITY_REJECTED_IP::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)

- ea: `0x18000401c`
- end: `0x180004109`
- name: `?RaiseEvent@SECURITY_REJECTED_IP@IISSecurityEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000369c`

## callees

- `0x18000401c`
- `0x180005010`

## string_xrefs

- `0x180004053`: `SECURITY_REJECTED_IP`

## pseudocode

```c
__int64 __fastcall IISSecurityEvents::SECURITY_REJECTED_IP::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rax
  _QWORD v7[5]; // [rsp+20h] [rbp-59h] BYREF
  int v8; // [rsp+48h] [rbp-31h]
  int v9; // [rsp+4Ch] [rbp-2Dh]
  __int128 v10; // [rsp+50h] [rbp-29h]
  int v11; // [rsp+60h] [rbp-19h]
  int v12; // [rsp+64h] [rbp-15h]
  int v13; // [rsp+68h] [rbp-11h]
  _QWORD v14[2]; // [rsp+6Ch] [rbp-Dh] BYREF
  const wchar_t *v15; // [rsp+80h] [rbp+7h] BYREF
  int v16; // [rsp+88h] [rbp+Fh]
  __int64 v17; // [rsp+90h] [rbp+17h]
  int v18; // [rsp+98h] [rbp+1Fh]
  __int64 v19; // [rsp+A0h] [rbp+27h]
  const wchar_t *v20; // [rsp+A8h] [rbp+2Fh]
  int v21; // [rsp+B0h] [rbp+37h]
  const unsigned __int16 *v22; // [rsp+B8h] [rbp+3Fh]
  int v23; // [rsp+C0h] [rbp+47h]
  __int64 v24; // [rsp+C8h] [rbp+4Fh]

  v7[1] = 4;
  memset(v14, 0, 12);
  v7[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v7[2] = &`IISSecurityEvents::GetAreaGuid'::`2'::AreaGuid;
  v7[4] = L"SECURITY_REJECTED_IP";
  v8 = 1;
  v12 = 1;
  v15 = L"ContextId";
  v20 = L"IPAddress";
  v7[3] = 11;
  v9 = 3;
  v13 = 2;
  v10 = 0;
  v11 = 0;
  v16 = 72;
  v17 = 0;
  v18 = 16;
  v19 = 0;
  v21 = 31;
  v22 = a3;
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
  v23 = v3;
  *(_QWORD *)((char *)v14 + 4) = &v15;
  v5 = *(_QWORD *)a1;
  v24 = 0;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v5 + 16))(a1, v7);
  return 0;
}

```

## disassembly

```asm
0x18000401c  push    rbp
0x18000401e  lea     rbp, [rsp-57h]
0x180004023  sub     rsp, 0D0h
0x18000402a  xor     eax, eax
0x18000402c  mov     [rbp+57h+var_A8], 4
0x180004034  mov     [rbp+57h+var_64], rax
0x180004038  xor     edx, edx
0x18000403a  mov     [rbp+57h+var_5C], eax
0x18000403d  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004044  mov     [rbp+57h+var_B0], rax
0x180004048  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISSecurityEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISSecurityEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000404f  mov     [rbp+57h+var_A0], rax
0x180004053  lea     rax, aSecurityReject; "SECURITY_REJECTED_IP"
0x18000405a  mov     [rbp+57h+var_90], rax
0x18000405e  mov     eax, 1
0x180004063  mov     [rbp+57h+var_88], eax
0x180004066  xorps   xmm0, xmm0
0x180004069  mov     [rbp+57h+var_6C], eax
0x18000406c  lea     rax, aContextid; "ContextId"
0x180004073  mov     [rbp+57h+var_50], rax
0x180004077  lea     rax, aIpaddress; "IPAddress"
0x18000407e  mov     [rbp+57h+var_28], rax
0x180004082  mov     [rbp+57h+var_98], 0Bh
0x18000408a  mov     [rbp+57h+var_84], 3
0x180004091  mov     [rbp+57h+var_68], 2
0x180004098  movdqa  [rbp+57h+var_80], xmm0
0x18000409d  mov     [rbp+57h+var_70], edx
0x1800040a0  mov     [rbp+57h+var_48], 48h ; 'H'
0x1800040a7  mov     [rbp+57h+var_40], rdx
0x1800040ab  mov     [rbp+57h+var_38], 10h
0x1800040b2  mov     [rbp+57h+var_30], rdx
0x1800040b6  mov     [rbp+57h+var_20], 1Fh
0x1800040bd  mov     [rbp+57h+var_18], r8
0x1800040c1  test    r8, r8
0x1800040c4  jnz     short loc_1800040CA
0x1800040c6  mov     eax, edx
0x1800040c8  jmp     short loc_1800040DF
0x1800040ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800040ce  inc     rax
0x1800040d1  cmp     [r8+rax*2], dx
0x1800040d6  jnz     short loc_1800040CE
0x1800040d8  lea     eax, ds:2[rax*2]
0x1800040df  mov     [rbp+57h+var_10], eax
0x1800040e2  lea     rax, [rbp+57h+var_50]
0x1800040e6  mov     [rbp+57h+var_64+4], rax
0x1800040ea  mov     rax, [rcx]
0x1800040ed  mov     [rbp+57h+var_8], rdx
0x1800040f1  lea     rdx, [rbp+57h+var_B0]
0x1800040f5  mov     rax, [rax+10h]
0x1800040f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040fe  xor     eax, eax
0x180004100  add     rsp, 0D0h
0x180004107  pop     rbp
0x180004108  retn
```
