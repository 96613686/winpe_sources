# IISCGIEvents::CGI_LAUNCH::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ulong,ulong)

- ea: `0x1800057b0`
- end: `0x18000590c`
- name: `?RaiseEvent@CGI_LAUNCH@IISCGIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGKK@Z`
- size: `348`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *, unsigned int, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000337c`

## callees

- `0x1800057b0`
- `0x180006e90`
- `0x180008010`

## string_xrefs

- `0x18000583e`: `CommandLine`
- `0x1800058b1`: `ProcessId`

## pseudocode

```c
__int64 __fastcall IISCGIEvents::CGI_LAUNCH::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4,
        char a5)
{
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rax
  void (__fastcall *v8)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v10[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v11; // [rsp+48h] [rbp-B8h]
  int v12; // [rsp+4Ch] [rbp-B4h]
  __int128 v13; // [rsp+50h] [rbp-B0h]
  int v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+64h] [rbp-9Ch]
  int v16; // [rsp+68h] [rbp-98h]
  _QWORD v17[2]; // [rsp+6Ch] [rbp-94h] BYREF
  const wchar_t *v18; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+88h] [rbp-78h]
  __int64 v20; // [rsp+90h] [rbp-70h]
  int v21; // [rsp+98h] [rbp-68h]
  __int64 v22; // [rsp+A0h] [rbp-60h]
  const wchar_t *v23; // [rsp+A8h] [rbp-58h]
  int v24; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v25; // [rsp+B8h] [rbp-48h]
  int v26; // [rsp+C0h] [rbp-40h]
  __int64 v27; // [rsp+C8h] [rbp-38h]
  const wchar_t *v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D8h] [rbp-28h]
  int *v30; // [rsp+E0h] [rbp-20h]
  int v31; // [rsp+E8h] [rbp-18h]
  __int64 v32; // [rsp+F0h] [rbp-10h]
  const wchar_t *v33; // [rsp+F8h] [rbp-8h]
  int v34; // [rsp+100h] [rbp+0h]
  char *v35; // [rsp+108h] [rbp+8h]
  int v36; // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]
  int v38; // [rsp+158h] [rbp+58h] BYREF

  v38 = a4;
  v10[1] = 32;
  memset(v17, 0, 12);
  v10[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v10[2] = &`IISCGIEvents::GetAreaGuid'::`2'::AreaGuid;
  v10[4] = L"CGI_LAUNCH";
  v11 = 1;
  v15 = 1;
  v10[3] = 3;
  v13 = 0;
  v12 = 4;
  v18 = L"ContextId";
  v23 = L"CommandLine";
  v16 = 4;
  v14 = 0;
  v19 = 72;
  v20 = 0;
  v21 = 16;
  v22 = 0;
  v24 = 31;
  v25 = a3;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v5 = 2 * v6 + 2;
  }
  else
  {
    v5 = 0;
  }
  v26 = v5;
  v29 = 19;
  v28 = L"ErrorCode";
  v30 = &v38;
  v33 = L"ProcessId";
  v35 = &a5;
  *(_QWORD *)((char *)v17 + 4) = &v18;
  v7 = *(_QWORD *)a1;
  v34 = 19;
  v27 = 0;
  v31 = 4;
  v8 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v7 + 16);
  v32 = 0;
  v36 = 4;
  v37 = 0;
  v8(a1, v10);
  return 0;
}

```

## disassembly

```asm
0x1800057b0  mov     [rsp-8+arg_18], r9d
0x1800057b5  push    rbp
0x1800057b6  lea     rbp, [rsp-30h]
0x1800057bb  sub     rsp, 130h
0x1800057c2  mov     rax, cs:__security_cookie
0x1800057c9  xor     rax, rsp
0x1800057cc  mov     [rbp+30h+var_10], rax
0x1800057d0  xor     eax, eax
0x1800057d2  mov     [rsp+130h+var_108], 20h ; ' '
0x1800057db  mov     [rsp+130h+var_C4], rax
0x1800057e0  xor     r9d, r9d
0x1800057e3  mov     [rsp+130h+var_BC], eax
0x1800057e7  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800057ee  mov     [rsp+130h+var_110], rax
0x1800057f3  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800057fa  mov     [rsp+130h+var_100], rax
0x1800057ff  lea     rax, aCgiLaunch; "CGI_LAUNCH"
0x180005806  mov     [rsp+130h+var_F0], rax
0x18000580b  mov     eax, 1
0x180005810  mov     [rsp+130h+var_E8], eax
0x180005814  xorps   xmm0, xmm0
0x180005817  mov     [rsp+130h+var_CC], eax
0x18000581b  mov     [rsp+130h+var_F8], 3
0x180005824  movdqa  [rsp+130h+var_E0], xmm0
0x18000582a  lea     r10d, [rax+3]
0x18000582e  mov     [rsp+130h+var_E4], r10d
0x180005833  lea     rax, aContextid; "ContextId"
0x18000583a  mov     [rbp+30h+var_B0], rax
0x18000583e  lea     rax, aCommandline; "CommandLine"
0x180005845  mov     [rbp+30h+var_88], rax
0x180005849  mov     [rsp+130h+var_C8], r10d
0x18000584e  mov     [rsp+130h+var_D0], r9d
0x180005853  mov     [rbp+30h+var_A8], 48h ; 'H'
0x18000585a  mov     [rbp+30h+var_A0], r9
0x18000585e  mov     [rbp+30h+var_98], 10h
0x180005865  mov     [rbp+30h+var_90], r9
0x180005869  mov     [rbp+30h+var_80], 1Fh
0x180005870  mov     [rbp+30h+var_78], r8
0x180005874  test    r8, r8
0x180005877  jnz     short loc_18000587E
0x180005879  mov     eax, r9d
0x18000587c  jmp     short loc_180005893
0x18000587e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005882  inc     rax
0x180005885  cmp     [r8+rax*2], r9w
0x18000588a  jnz     short loc_180005882
0x18000588c  lea     eax, ds:2[rax*2]
0x180005893  mov     [rbp+30h+var_70], eax
0x180005896  mov     edx, 13h
0x18000589b  lea     rax, aErrorcode; "ErrorCode"
0x1800058a2  mov     [rbp+30h+var_58], edx
0x1800058a5  mov     [rbp+30h+var_60], rax
0x1800058a9  lea     rax, [rbp+30h+arg_18]
0x1800058ad  mov     [rbp+30h+var_50], rax
0x1800058b1  lea     rax, aProcessid; "ProcessId"
0x1800058b8  mov     [rbp+30h+var_38], rax
0x1800058bc  lea     rax, [rbp+30h+arg_20]
0x1800058c0  mov     [rbp+30h+var_28], rax
0x1800058c4  lea     rax, [rbp+30h+var_B0]
0x1800058c8  mov     [rsp+130h+var_C4+4], rax
0x1800058cd  mov     rax, [rcx]
0x1800058d0  mov     [rbp+30h+var_30], edx
0x1800058d3  lea     rdx, [rsp+130h+var_110]
0x1800058d8  mov     [rbp+30h+var_68], r9
0x1800058dc  mov     [rbp+30h+var_48], r10d
0x1800058e0  mov     rax, [rax+10h]
0x1800058e4  mov     [rbp+30h+var_40], r9
0x1800058e8  mov     [rbp+30h+var_20], r10d
0x1800058ec  mov     [rbp+30h+var_18], r9
0x1800058f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f5  xor     eax, eax
0x1800058f7  mov     rcx, [rbp+30h+var_10]
0x1800058fb  xor     rcx, rsp; StackCookie
0x1800058fe  call    __security_check_cookie
0x180005903  add     rsp, 130h
0x18000590a  pop     rbp
0x18000590b  retn
```
