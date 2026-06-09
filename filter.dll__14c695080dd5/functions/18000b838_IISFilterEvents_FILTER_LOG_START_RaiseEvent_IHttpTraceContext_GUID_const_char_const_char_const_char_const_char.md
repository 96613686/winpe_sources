# IISFilterEvents::FILTER_LOG_START::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,ulong)

- ea: `0x18000b838`
- end: `0x18000baeb`
- name: `?RaiseEvent@FILTER_LOG_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD22222KK@Z`
- size: `691`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const char *, const char *, const char *, const char *, const char *, const char *, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f80`

## callees

- `0x18000b838`
- `0x18000c970`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall IISFilterEvents::FILTER_LOG_START::RaiseEvent(
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
  __int64 v11; // rax
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
  v26[3] = 25;
  v26[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v28 = 4;
  v26[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
  v32 = 9;
  v26[4] = L"FILTER_LOG_START";
  v27 = 1;
  v31 = 1;
  v34 = L"ContextId";
  v39 = L"OrigClientHostName";
  v11 = -1;
  v29 = 0;
  v30 = 0;
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
  v44 = L"OrigClientUserName";
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
  v49 = L"OrigServerName";
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
  v54 = L"OrigOperation";
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
  v59 = L"OrigTarget";
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
  v64 = L"OrigParameters";
  v63 = 0;
  v65 = 30;
  v66 = a8;
  if ( a8 )
  {
    do
      ++v11;
    while ( a8[v11] );
    v22 = v11 + 1;
  }
  else
  {
    v22 = 0;
  }
  v67 = v22;
  v68 = 0;
  v70 = 19;
  v69 = L"OrigHttpStatus";
  v71 = &a9;
  v74 = L"OrigWin32Status";
  v76 = &a10;
  *(_QWORD *)((char *)v33 + 4) = &v34;
  v23 = *(_QWORD *)a1;
  v75 = 19;
  v72 = 4;
  v73 = 0;
  v24 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v23 + 16);
  v77 = 4;
  v78 = 0;
  v24(a1, v26);
  return 0;
}

```

## disassembly

```asm
0x18000b838  mov     [rsp-8+arg_8], rbx
0x18000b83d  push    rbp
0x18000b83e  lea     rbp, [rsp-100h]
0x18000b846  sub     rsp, 200h
0x18000b84d  mov     rax, cs:__security_cookie
0x18000b854  xor     rax, rsp
0x18000b857  mov     [rbp+100h+var_10], rax
0x18000b85e  xor     eax, eax
0x18000b860  mov     [rsp+200h+var_1D8], 8
0x18000b869  mov     [rsp+200h+var_194], rax
0x18000b86e  xor     r11d, r11d
0x18000b871  mov     [rsp+200h+var_18C], eax
0x18000b875  xorps   xmm0, xmm0
0x18000b878  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000b87f  mov     [rsp+200h+var_1C8], 19h
0x18000b888  mov     [rsp+200h+var_1E0], rax
0x18000b88d  mov     r10, rcx
0x18000b890  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000b897  mov     [rsp+200h+var_1B4], 4
0x18000b89f  mov     [rsp+200h+var_1D0], rax
0x18000b8a4  lea     ebx, [r11+1Eh]
0x18000b8a8  lea     rax, aFilterLogStart; "FILTER_LOG_START"
0x18000b8af  mov     [rsp+200h+var_198], 9
0x18000b8b7  mov     [rsp+200h+var_1C0], rax
0x18000b8bc  mov     eax, 1
0x18000b8c1  mov     [rsp+200h+var_1B8], eax
0x18000b8c5  mov     [rsp+200h+var_19C], eax
0x18000b8c9  lea     rax, aContextid; "ContextId"
0x18000b8d0  mov     [rbp+100h+var_180], rax
0x18000b8d4  lea     rax, aOrigclienthost; "OrigClientHostName"
0x18000b8db  mov     [rbp+100h+var_158], rax
0x18000b8df  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b8e3  movdqa  [rsp+200h+var_1B0], xmm0
0x18000b8e9  mov     [rsp+200h+var_1A0], r11d
0x18000b8ee  mov     [rbp+100h+var_178], 48h ; 'H'
0x18000b8f5  mov     [rbp+100h+var_170], r11
0x18000b8f9  mov     [rbp+100h+var_168], 10h
0x18000b900  mov     [rbp+100h+var_160], r11
0x18000b904  mov     [rbp+100h+var_150], ebx
0x18000b907  mov     [rbp+100h+var_148], r8
0x18000b90b  test    r8, r8
0x18000b90e  jnz     short loc_18000B915
0x18000b910  mov     ecx, r11d
0x18000b913  jmp     short loc_18000B923
0x18000b915  mov     rcx, rax
0x18000b918  inc     rcx
0x18000b91b  cmp     [r8+rcx], r11b
0x18000b91f  jnz     short loc_18000B918
0x18000b921  inc     ecx
0x18000b923  mov     [rbp+100h+var_140], ecx
0x18000b926  lea     rcx, aOrigclientuser; "OrigClientUserName"
0x18000b92d  mov     [rbp+100h+var_130], rcx
0x18000b931  mov     [rbp+100h+var_138], r11
0x18000b935  mov     [rbp+100h+var_128], ebx
0x18000b938  mov     [rbp+100h+var_120], r9
0x18000b93c  test    r9, r9
0x18000b93f  jnz     short loc_18000B946
0x18000b941  mov     ecx, r11d
0x18000b944  jmp     short loc_18000B954
0x18000b946  mov     rcx, rax
0x18000b949  inc     rcx
0x18000b94c  cmp     [r9+rcx], r11b
0x18000b950  jnz     short loc_18000B949
0x18000b952  inc     ecx
0x18000b954  mov     rdx, [rbp+100h+arg_20]
0x18000b95b  mov     [rbp+100h+var_118], ecx
0x18000b95e  lea     rcx, aOrigservername; "OrigServerName"
0x18000b965  mov     [rbp+100h+var_108], rcx
0x18000b969  mov     [rbp+100h+var_110], r11
0x18000b96d  mov     [rbp+100h+var_100], ebx
0x18000b970  mov     [rbp+100h+var_F8], rdx
0x18000b974  test    rdx, rdx
0x18000b977  jnz     short loc_18000B97E
0x18000b979  mov     ecx, r11d
0x18000b97c  jmp     short loc_18000B98C
0x18000b97e  mov     rcx, rax
0x18000b981  inc     rcx
0x18000b984  cmp     [rdx+rcx], r11b
0x18000b988  jnz     short loc_18000B981
0x18000b98a  inc     ecx
0x18000b98c  mov     rdx, [rbp+100h+arg_28]
0x18000b993  mov     [rbp+100h+var_F0], ecx
0x18000b996  lea     rcx, aOrigoperation; "OrigOperation"
0x18000b99d  mov     [rbp+100h+var_E0], rcx
0x18000b9a1  mov     [rbp+100h+var_E8], r11
0x18000b9a5  mov     [rbp+100h+var_D8], ebx
0x18000b9a8  mov     [rbp+100h+var_D0], rdx
0x18000b9ac  test    rdx, rdx
0x18000b9af  jnz     short loc_18000B9B6
0x18000b9b1  mov     ecx, r11d
0x18000b9b4  jmp     short loc_18000B9C4
0x18000b9b6  mov     rcx, rax
0x18000b9b9  inc     rcx
0x18000b9bc  cmp     [rdx+rcx], r11b
0x18000b9c0  jnz     short loc_18000B9B9
0x18000b9c2  inc     ecx
0x18000b9c4  mov     rdx, [rbp+100h+arg_30]
0x18000b9cb  mov     [rbp+100h+var_C8], ecx
0x18000b9ce  lea     rcx, aOrigtarget; "OrigTarget"
0x18000b9d5  mov     [rbp+100h+var_B8], rcx
0x18000b9d9  mov     [rbp+100h+var_C0], r11
0x18000b9dd  mov     [rbp+100h+var_B0], ebx
0x18000b9e0  mov     [rbp+100h+var_A8], rdx
0x18000b9e4  test    rdx, rdx
0x18000b9e7  jnz     short loc_18000B9EE
0x18000b9e9  mov     ecx, r11d
0x18000b9ec  jmp     short loc_18000B9FC
0x18000b9ee  mov     rcx, rax
0x18000b9f1  inc     rcx
0x18000b9f4  cmp     [rdx+rcx], r11b
0x18000b9f8  jnz     short loc_18000B9F1
0x18000b9fa  inc     ecx
0x18000b9fc  mov     [rbp+100h+var_A0], ecx
0x18000b9ff  lea     rcx, aOrigparameters; "OrigParameters"
0x18000ba06  mov     [rbp+100h+var_90], rcx
0x18000ba0a  mov     rcx, [rbp+100h+arg_38]
0x18000ba11  mov     [rbp+100h+var_98], r11
0x18000ba15  mov     [rbp+100h+var_88], ebx
0x18000ba18  mov     [rbp+100h+var_80], rcx
0x18000ba1f  test    rcx, rcx
0x18000ba22  jnz     short loc_18000BA29
0x18000ba24  mov     eax, r11d
0x18000ba27  jmp     short loc_18000BA34
0x18000ba29  inc     rax
0x18000ba2c  cmp     [rcx+rax], r11b
0x18000ba30  jnz     short loc_18000BA29
0x18000ba32  inc     eax
0x18000ba34  mov     [rbp+100h+var_78], eax
0x18000ba3a  lea     rdx, [rsp+200h+var_1E0]
0x18000ba3f  mov     ecx, 13h
0x18000ba44  mov     [rbp+100h+var_70], r11
0x18000ba4b  lea     rax, aOrighttpstatus; "OrigHttpStatus"
0x18000ba52  mov     [rbp+100h+var_60], ecx
0x18000ba58  mov     [rbp+100h+var_68], rax
0x18000ba5f  lea     rax, [rbp+100h+arg_40]
0x18000ba66  mov     [rbp+100h+var_58], rax
0x18000ba6d  lea     rax, aOrigwin32statu; "OrigWin32Status"
0x18000ba74  mov     [rbp+100h+var_40], rax
0x18000ba7b  lea     rax, [rbp+100h+arg_48]
0x18000ba82  mov     [rbp+100h+var_30], rax
0x18000ba89  lea     rax, [rbp+100h+var_180]
0x18000ba8d  mov     [rsp+200h+var_194+4], rax
0x18000ba92  mov     rax, [r10]
0x18000ba95  mov     [rbp+100h+var_38], ecx
0x18000ba9b  mov     rcx, r10
0x18000ba9e  mov     [rbp+100h+var_50], 4
0x18000baa8  mov     [rbp+100h+var_48], r11
0x18000baaf  mov     rax, [rax+10h]
0x18000bab3  mov     [rbp+100h+var_28], 4
0x18000babd  mov     [rbp+100h+var_20], r11
0x18000bac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac9  xor     eax, eax
0x18000bacb  mov     rcx, [rbp+100h+var_10]
0x18000bad2  xor     rcx, rsp; StackCookie
0x18000bad5  call    __security_check_cookie
0x18000bada  mov     rbx, [rsp+200h+arg_8]
0x18000bae2  add     rsp, 200h
0x18000bae9  pop     rbp
0x18000baea  retn
```
