# IISFilterEvents::FILTER_LOG_END::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,ulong)

- ea: `0x1800048a0`
- end: `0x180004b6d`
- name: `?RaiseEvent@FILTER_LOG_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD22222KK@Z`
- size: `717`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const char *, const char *, const char *, const char *, const char *, const char *, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004440`

## callees

- `0x1800048a0`
- `0x18000c970`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall IISFilterEvents::FILTER_LOG_END::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const char *a3,
        const char *a4,
        const char *a5,
        const char *a6,
        const char *a7,
        const char *a8,
        char a9,
        char a10)
{
  __int64 v10; // rax
  int v12; // ecx
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v15; // rcx
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // ecx
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  void (__fastcall *v24)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v26[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  int v28; // [rsp+4Ch] [rbp-B4h]
  __int128 v29; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  int v32; // [rsp+68h] [rbp-98h]
  _QWORD v33[2]; // [rsp+6Ch] [rbp-94h] BYREF
  const wchar_t *v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h]
  const wchar_t *v39; // [rsp+A8h] [rbp-58h]
  int v40; // [rsp+B0h] [rbp-50h]
  const char *v41; // [rsp+B8h] [rbp-48h]
  int v42; // [rsp+C0h] [rbp-40h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  const wchar_t *v44; // [rsp+D0h] [rbp-30h]
  int v45; // [rsp+D8h] [rbp-28h]
  const char *v46; // [rsp+E0h] [rbp-20h]
  int v47; // [rsp+E8h] [rbp-18h]
  __int64 v48; // [rsp+F0h] [rbp-10h]
  const wchar_t *v49; // [rsp+F8h] [rbp-8h]
  int v50; // [rsp+100h] [rbp+0h]
  const char *v51; // [rsp+108h] [rbp+8h]
  int v52; // [rsp+110h] [rbp+10h]
  __int64 v53; // [rsp+118h] [rbp+18h]
  const wchar_t *v54; // [rsp+120h] [rbp+20h]
  int v55; // [rsp+128h] [rbp+28h]
  const char *v56; // [rsp+130h] [rbp+30h]
  int v57; // [rsp+138h] [rbp+38h]
  __int64 v58; // [rsp+140h] [rbp+40h]
  const wchar_t *v59; // [rsp+148h] [rbp+48h]
  int v60; // [rsp+150h] [rbp+50h]
  const char *v61; // [rsp+158h] [rbp+58h]
  int v62; // [rsp+160h] [rbp+60h]
  __int64 v63; // [rsp+168h] [rbp+68h]
  const wchar_t *v64; // [rsp+170h] [rbp+70h]
  int v65; // [rsp+178h] [rbp+78h]
  const char *v66; // [rsp+180h] [rbp+80h]
  int v67; // [rsp+188h] [rbp+88h]
  __int64 v68; // [rsp+190h] [rbp+90h]
  const wchar_t *v69; // [rsp+198h] [rbp+98h]
  int v70; // [rsp+1A0h] [rbp+A0h]
  char *v71; // [rsp+1A8h] [rbp+A8h]
  int v72; // [rsp+1B0h] [rbp+B0h]
  __int64 v73; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v74; // [rsp+1C0h] [rbp+C0h]
  int v75; // [rsp+1C8h] [rbp+C8h]
  char *v76; // [rsp+1D0h] [rbp+D0h]
  int v77; // [rsp+1D8h] [rbp+D8h]
  __int64 v78; // [rsp+1E0h] [rbp+E0h]

  v26[1] = 8;
  memset(v33, 0, 12);
  v26[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v26[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
  v26[4] = L"FILTER_LOG_END";
  v34 = L"ContextId";
  v39 = L"FinalClientHostName";
  v26[3] = 26;
  v10 = -1;
  v27 = 1;
  v28 = 4;
  v32 = 9;
  v29 = 0;
  v30 = 0;
  v31 = 1;
  v35 = 72;
  v36 = 0;
  v37 = 16;
  v38 = 0;
  v40 = 30;
  v41 = a3;
  if ( a3 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    v12 = v13 + 1;
  }
  else
  {
    v12 = 0;
  }
  v42 = v12;
  v44 = L"FinalClientUserName";
  v43 = 0;
  v45 = 30;
  v46 = a4;
  if ( a4 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a4[v15] );
    v14 = v15 + 1;
  }
  else
  {
    v14 = 0;
  }
  v47 = v14;
  v49 = L"FinalServerName";
  v48 = 0;
  v50 = 30;
  v51 = a5;
  if ( a5 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a5[v17] );
    v16 = v17 + 1;
  }
  else
  {
    v16 = 0;
  }
  v52 = v16;
  v54 = L"FinalOperation";
  v53 = 0;
  v55 = 30;
  v56 = a6;
  if ( a6 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a6[v19] );
    v18 = v19 + 1;
  }
  else
  {
    v18 = 0;
  }
  v57 = v18;
  v59 = L"FinalTarget";
  v58 = 0;
  v60 = 30;
  v61 = a7;
  if ( a7 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a7[v21] );
    v20 = v21 + 1;
  }
  else
  {
    v20 = 0;
  }
  v62 = v20;
  v64 = L"FinalParameters";
  v63 = 0;
  v65 = 30;
  v66 = a8;
  if ( a8 )
  {
    do
      ++v10;
    while ( a8[v10] );
    v22 = v10 + 1;
  }
  else
  {
    v22 = 0;
  }
  v67 = v22;
  v68 = 0;
  v69 = L"FinalHttpStatus";
  v70 = 19;
  v71 = &a9;
  v74 = L"FinalWin32Status";
  v76 = &a10;
  *(_QWORD *)((char *)v33 + 4) = &v34;
  v23 = *(_QWORD *)a1;
  v72 = 4;
  v73 = 0;
  v75 = 19;
  v24 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v23 + 16);
  v77 = 4;
  v78 = 0;
  v24(a1, v26);
  return 0;
}

```

## disassembly

```asm
0x1800048a0  push    rbp
0x1800048a2  lea     rbp, [rsp-100h]
0x1800048aa  sub     rsp, 200h
0x1800048b1  mov     rax, cs:__security_cookie
0x1800048b8  xor     rax, rsp
0x1800048bb  mov     [rbp+100h+var_10], rax
0x1800048c2  xor     eax, eax
0x1800048c4  mov     [rsp+200h+var_1D8], 8
0x1800048cd  mov     [rsp+200h+var_194], rax
0x1800048d2  xor     r11d, r11d
0x1800048d5  mov     [rsp+200h+var_18C], eax
0x1800048d9  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800048e0  mov     [rsp+200h+var_1E0], rax
0x1800048e5  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800048ec  mov     [rsp+200h+var_1D0], rax
0x1800048f1  lea     rax, aFilterLogEnd; "FILTER_LOG_END"
0x1800048f8  mov     [rsp+200h+var_1C0], rax
0x1800048fd  lea     rax, aContextid; "ContextId"
0x180004904  mov     [rbp+100h+var_180], rax
0x180004908  lea     rax, aFinalclienthos; "FinalClientHostName"
0x18000490f  mov     [rbp+100h+var_158], rax
0x180004913  xorps   xmm0, xmm0
0x180004916  mov     [rsp+200h+var_1C8], 1Ah
0x18000491f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004926  mov     [rsp+200h+var_1B8], 1
0x18000492e  mov     r10, rcx
0x180004931  mov     [rsp+200h+var_1B4], 4
0x180004939  mov     [rsp+200h+var_198], 9
0x180004941  movdqa  [rsp+200h+var_1B0], xmm0
0x180004947  mov     [rsp+200h+var_1A0], r11d
0x18000494c  mov     [rsp+200h+var_19C], 1
0x180004954  mov     [rbp+100h+var_178], 48h ; 'H'
0x18000495b  mov     [rbp+100h+var_170], r11
0x18000495f  mov     [rbp+100h+var_168], 10h
0x180004966  mov     [rbp+100h+var_160], r11
0x18000496a  mov     [rbp+100h+var_150], 1Eh
0x180004971  mov     [rbp+100h+var_148], r8
0x180004975  test    r8, r8
0x180004978  jnz     short loc_18000497F
0x18000497a  mov     ecx, r11d
0x18000497d  jmp     short loc_18000498D
0x18000497f  mov     rcx, rax
0x180004982  inc     rcx
0x180004985  cmp     [r8+rcx], r11b
0x180004989  jnz     short loc_180004982
0x18000498b  inc     ecx
0x18000498d  mov     [rbp+100h+var_140], ecx
0x180004990  lea     rcx, aFinalclientuse; "FinalClientUserName"
0x180004997  mov     [rbp+100h+var_130], rcx
0x18000499b  mov     [rbp+100h+var_138], r11
0x18000499f  mov     [rbp+100h+var_128], 1Eh
0x1800049a6  mov     [rbp+100h+var_120], r9
0x1800049aa  test    r9, r9
0x1800049ad  jnz     short loc_1800049B4
0x1800049af  mov     ecx, r11d
0x1800049b2  jmp     short loc_1800049C2
0x1800049b4  mov     rcx, rax
0x1800049b7  inc     rcx
0x1800049ba  cmp     [r9+rcx], r11b
0x1800049be  jnz     short loc_1800049B7
0x1800049c0  inc     ecx
0x1800049c2  mov     rdx, [rbp+100h+arg_20]
0x1800049c9  mov     [rbp+100h+var_118], ecx
0x1800049cc  lea     rcx, aFinalservernam; "FinalServerName"
0x1800049d3  mov     [rbp+100h+var_108], rcx
0x1800049d7  mov     [rbp+100h+var_110], r11
0x1800049db  mov     [rbp+100h+var_100], 1Eh
0x1800049e2  mov     [rbp+100h+var_F8], rdx
0x1800049e6  test    rdx, rdx
0x1800049e9  jnz     short loc_1800049F0
0x1800049eb  mov     ecx, r11d
0x1800049ee  jmp     short loc_1800049FE
0x1800049f0  mov     rcx, rax
0x1800049f3  inc     rcx
0x1800049f6  cmp     [rdx+rcx], r11b
0x1800049fa  jnz     short loc_1800049F3
0x1800049fc  inc     ecx
0x1800049fe  mov     rdx, [rbp+100h+arg_28]
0x180004a05  mov     [rbp+100h+var_F0], ecx
0x180004a08  lea     rcx, aFinaloperation; "FinalOperation"
0x180004a0f  mov     [rbp+100h+var_E0], rcx
0x180004a13  mov     [rbp+100h+var_E8], r11
0x180004a17  mov     [rbp+100h+var_D8], 1Eh
0x180004a1e  mov     [rbp+100h+var_D0], rdx
0x180004a22  test    rdx, rdx
0x180004a25  jnz     short loc_180004A2C
0x180004a27  mov     ecx, r11d
0x180004a2a  jmp     short loc_180004A3B
0x180004a2c  mov     rcx, rax
0x180004a2f  nop
0x180004a30  inc     rcx
0x180004a33  cmp     [rdx+rcx], r11b
0x180004a37  jnz     short loc_180004A30
0x180004a39  inc     ecx
0x180004a3b  mov     rdx, [rbp+100h+arg_30]
0x180004a42  mov     [rbp+100h+var_C8], ecx
0x180004a45  lea     rcx, aFinaltarget; "FinalTarget"
0x180004a4c  mov     [rbp+100h+var_B8], rcx
0x180004a50  mov     [rbp+100h+var_C0], r11
0x180004a54  mov     [rbp+100h+var_B0], 1Eh
0x180004a5b  mov     [rbp+100h+var_A8], rdx
0x180004a5f  test    rdx, rdx
0x180004a62  jnz     short loc_180004A69
0x180004a64  mov     ecx, r11d
0x180004a67  jmp     short loc_180004A7B
0x180004a69  mov     rcx, rax
0x180004a6c  nop     dword ptr [rax+00h]
0x180004a70  inc     rcx
0x180004a73  cmp     [rdx+rcx], r11b
0x180004a77  jnz     short loc_180004A70
0x180004a79  inc     ecx
0x180004a7b  mov     [rbp+100h+var_A0], ecx
0x180004a7e  lea     rcx, aFinalparameter; "FinalParameters"
0x180004a85  mov     [rbp+100h+var_90], rcx
0x180004a89  mov     rcx, [rbp+100h+arg_38]
0x180004a90  mov     [rbp+100h+var_98], r11
0x180004a94  mov     [rbp+100h+var_88], 1Eh
0x180004a9b  mov     [rbp+100h+var_80], rcx
0x180004aa2  test    rcx, rcx
0x180004aa5  jnz     short loc_180004AB0
0x180004aa7  mov     eax, r11d
0x180004aaa  jmp     short loc_180004ABB
0x180004ab0  inc     rax
0x180004ab3  cmp     [rcx+rax], r11b
0x180004ab7  jnz     short loc_180004AB0
0x180004ab9  inc     eax
0x180004abb  mov     [rbp+100h+var_78], eax
0x180004ac1  lea     rdx, [rsp+200h+var_1E0]
0x180004ac6  lea     rax, aFinalhttpstatu; "FinalHttpStatus"
0x180004acd  mov     [rbp+100h+var_70], r11
0x180004ad4  mov     [rbp+100h+var_68], rax
0x180004adb  mov     rcx, r10
0x180004ade  lea     rax, [rbp+100h+arg_40]
0x180004ae5  mov     [rbp+100h+var_60], 13h
0x180004aef  mov     [rbp+100h+var_58], rax
0x180004af6  lea     rax, aFinalwin32stat; "FinalWin32Status"
0x180004afd  mov     [rbp+100h+var_40], rax
0x180004b04  lea     rax, [rbp+100h+arg_48]
0x180004b0b  mov     [rbp+100h+var_30], rax
0x180004b12  lea     rax, [rbp+100h+var_180]
0x180004b16  mov     [rsp+200h+var_194+4], rax
0x180004b1b  mov     rax, [r10]
0x180004b1e  mov     [rbp+100h+var_50], 4
0x180004b28  mov     [rbp+100h+var_48], r11
0x180004b2f  mov     [rbp+100h+var_38], 13h
0x180004b39  mov     rax, [rax+10h]
0x180004b3d  mov     [rbp+100h+var_28], 4
0x180004b47  mov     [rbp+100h+var_20], r11
0x180004b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b53  xor     eax, eax
0x180004b55  mov     rcx, [rbp+100h+var_10]
0x180004b5c  xor     rcx, rsp; StackCookie
0x180004b5f  call    __security_check_cookie
0x180004b64  add     rsp, 200h
0x180004b6b  pop     rbp
0x180004b6c  retn
```
