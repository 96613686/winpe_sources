# IISFilterEvents::FILTER_ACCESS_DENIED_START::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,ulong)

- ea: `0x1800077a0`
- end: `0x18000791c`
- name: `?RaiseEvent@FILTER_ACCESS_DENIED_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2K@Z`
- size: `380`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const char *, const char *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x1800077a0`
- `0x18000c970`
- `0x18000d010`

## string_xrefs

- `0x18000788e`: `PhysicalPath`
- `0x1800077ea`: `FILTER_ACCESS_DENIED_START`

## pseudocode

```c
__int64 __fastcall IISFilterEvents::FILTER_ACCESS_DENIED_START::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const char *a3,
        const char *a4,
        char a5)
{
  __int64 v5; // rax
  int v7; // ecx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  _QWORD v12[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+48h] [rbp-B8h]
  int v14; // [rsp+4Ch] [rbp-B4h]
  __int128 v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+64h] [rbp-9Ch]
  int v18; // [rsp+68h] [rbp-98h]
  _QWORD v19[2]; // [rsp+6Ch] [rbp-94h] BYREF
  const wchar_t *v20; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+88h] [rbp-78h]
  __int64 v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+98h] [rbp-68h]
  __int64 v24; // [rsp+A0h] [rbp-60h]
  const wchar_t *v25; // [rsp+A8h] [rbp-58h]
  int v26; // [rsp+B0h] [rbp-50h]
  const char *v27; // [rsp+B8h] [rbp-48h]
  int v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  const wchar_t *v30; // [rsp+D0h] [rbp-30h]
  int v31; // [rsp+D8h] [rbp-28h]
  const char *v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+E8h] [rbp-18h]
  __int64 v34; // [rsp+F0h] [rbp-10h]
  const wchar_t *v35; // [rsp+F8h] [rbp-8h]
  int v36; // [rsp+100h] [rbp+0h]
  char *v37; // [rsp+108h] [rbp+8h]
  int v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]

  v12[1] = 8;
  memset(v19, 0, 12);
  v12[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v12[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
  v12[4] = L"FILTER_ACCESS_DENIED_START";
  v20 = L"ContextId";
  v25 = L"RequestedURL";
  v12[3] = 29;
  v5 = -1;
  v13 = 1;
  v14 = 4;
  v18 = 4;
  v15 = 0;
  v16 = 0;
  v17 = 1;
  v21 = 72;
  v22 = 0;
  v23 = 16;
  v24 = 0;
  v26 = 30;
  v27 = a3;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v7 = v8 + 1;
  }
  else
  {
    v7 = 0;
  }
  v28 = v7;
  v30 = L"PhysicalPath";
  v29 = 0;
  v31 = 30;
  v32 = a4;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v9 = v5 + 1;
  }
  else
  {
    v9 = 0;
  }
  v33 = v9;
  v34 = 0;
  v35 = L"DenialReason";
  v37 = &a5;
  *(_QWORD *)((char *)v19 + 4) = &v20;
  v10 = *(_QWORD *)a1;
  v39 = 0;
  v36 = 19;
  v38 = 4;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v10 + 16))(a1, v12);
  return 0;
}

```

## disassembly

```asm
0x1800077a0  push    rbp
0x1800077a2  lea     rbp, [rsp-30h]
0x1800077a7  sub     rsp, 130h
0x1800077ae  mov     rax, cs:__security_cookie
0x1800077b5  xor     rax, rsp
0x1800077b8  mov     [rbp+30h+var_10], rax
0x1800077bc  xor     eax, eax
0x1800077be  mov     [rsp+130h+var_108], 8
0x1800077c7  mov     [rsp+130h+var_C4], rax
0x1800077cc  xor     edx, edx
0x1800077ce  mov     [rsp+130h+var_BC], eax
0x1800077d2  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800077d9  mov     [rsp+130h+var_110], rax
0x1800077de  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800077e5  mov     [rsp+130h+var_100], rax
0x1800077ea  lea     rax, aFilterAccessDe_0; "FILTER_ACCESS_DENIED_START"
0x1800077f1  mov     [rsp+130h+var_F0], rax
0x1800077f6  lea     rax, aContextid; "ContextId"
0x1800077fd  mov     [rbp+30h+var_B0], rax
0x180007801  lea     rax, aRequestedurl; "RequestedURL"
0x180007808  mov     [rbp+30h+var_88], rax
0x18000780c  xorps   xmm0, xmm0
0x18000780f  mov     [rsp+130h+var_F8], 1Dh
0x180007818  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000781f  mov     [rsp+130h+var_E8], 1
0x180007827  mov     r10, rcx
0x18000782a  mov     [rsp+130h+var_E4], 4
0x180007832  mov     [rsp+130h+var_C8], 4
0x18000783a  movdqa  [rsp+130h+var_E0], xmm0
0x180007840  mov     [rsp+130h+var_D0], edx
0x180007844  mov     [rsp+130h+var_CC], 1
0x18000784c  mov     [rbp+30h+var_A8], 48h ; 'H'
0x180007853  mov     [rbp+30h+var_A0], rdx
0x180007857  mov     [rbp+30h+var_98], 10h
0x18000785e  mov     [rbp+30h+var_90], rdx
0x180007862  mov     [rbp+30h+var_80], 1Eh
0x180007869  mov     [rbp+30h+var_78], r8
0x18000786d  test    r8, r8
0x180007870  jnz     short loc_180007876
0x180007872  mov     ecx, edx
0x180007874  jmp     short loc_18000788B
0x180007876  mov     rcx, rax
0x180007879  nop     dword ptr [rax+00000000h]
0x180007880  inc     rcx
0x180007883  cmp     [r8+rcx], dl
0x180007887  jnz     short loc_180007880
0x180007889  inc     ecx
0x18000788b  mov     [rbp+30h+var_70], ecx
0x18000788e  lea     rcx, aPhysicalpath; "PhysicalPath"
0x180007895  mov     [rbp+30h+var_60], rcx
0x180007899  mov     [rbp+30h+var_68], rdx
0x18000789d  mov     [rbp+30h+var_58], 1Eh
0x1800078a4  mov     [rbp+30h+var_50], r9
0x1800078a8  test    r9, r9
0x1800078ab  jnz     short loc_1800078B1
0x1800078ad  mov     eax, edx
0x1800078af  jmp     short loc_1800078BC
0x1800078b1  inc     rax
0x1800078b4  cmp     [r9+rax], dl
0x1800078b8  jnz     short loc_1800078B1
0x1800078ba  inc     eax
0x1800078bc  mov     [rbp+30h+var_48], eax
0x1800078bf  mov     rcx, r10
0x1800078c2  lea     rax, aDenialreason; "DenialReason"
0x1800078c9  mov     [rbp+30h+var_40], rdx
0x1800078cd  mov     [rbp+30h+var_38], rax
0x1800078d1  lea     rax, [rbp+30h+arg_20]
0x1800078d5  mov     [rbp+30h+var_28], rax
0x1800078d9  lea     rax, [rbp+30h+var_B0]
0x1800078dd  mov     [rsp+130h+var_C4+4], rax
0x1800078e2  mov     rax, [r10]
0x1800078e5  mov     [rbp+30h+var_18], rdx
0x1800078e9  lea     rdx, [rsp+130h+var_110]
0x1800078ee  mov     [rbp+30h+var_30], 13h
0x1800078f5  mov     [rbp+30h+var_20], 4
0x1800078fc  mov     rax, [rax+10h]
0x180007900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007905  xor     eax, eax
0x180007907  mov     rcx, [rbp+30h+var_10]
0x18000790b  xor     rcx, rsp; StackCookie
0x18000790e  call    __security_check_cookie
0x180007913  add     rsp, 130h
0x18000791a  pop     rbp
0x18000791b  retn
```
