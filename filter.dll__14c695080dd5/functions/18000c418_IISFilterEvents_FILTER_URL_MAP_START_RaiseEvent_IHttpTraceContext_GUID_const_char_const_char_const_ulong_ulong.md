# IISFilterEvents::FILTER_URL_MAP_START::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,ulong,ulong,ulong,char const *)

- ea: `0x18000c418`
- end: `0x18000c60b`
- name: `?RaiseEvent@FILTER_URL_MAP_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2KKK2@Z`
- size: `499`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const char *, const char *, char, char, char, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003f80`

## callees

- `0x18000c418`
- `0x18000c970`
- `0x18000d010`

## string_xrefs

- `0x18000c503`: `OrigPath`
- `0x18000c536`: `AccessPerms`
- `0x18000c550`: `MatchingPath`

## pseudocode

```c
__int64 __fastcall IISFilterEvents::FILTER_URL_MAP_START::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const char *a3,
        const char *a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v8; // rax
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rax
  void (__fastcall *v13)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v15[5]; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+48h] [rbp-B8h]
  int v17; // [rsp+4Ch] [rbp-B4h]
  __int128 v18; // [rsp+50h] [rbp-B0h]
  int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+68h] [rbp-98h]
  _QWORD v22[2]; // [rsp+6Ch] [rbp-94h] BYREF
  const wchar_t *v23; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+88h] [rbp-78h]
  __int64 v25; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h]
  __int64 v27; // [rsp+A0h] [rbp-60h]
  const wchar_t *v28; // [rsp+A8h] [rbp-58h]
  int v29; // [rsp+B0h] [rbp-50h]
  const char *v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  const wchar_t *v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  const char *v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+E8h] [rbp-18h]
  __int64 v37; // [rsp+F0h] [rbp-10h]
  const wchar_t *v38; // [rsp+F8h] [rbp-8h]
  int v39; // [rsp+100h] [rbp+0h]
  char *v40; // [rsp+108h] [rbp+8h]
  int v41; // [rsp+110h] [rbp+10h]
  __int64 v42; // [rsp+118h] [rbp+18h]
  const wchar_t *v43; // [rsp+120h] [rbp+20h]
  int v44; // [rsp+128h] [rbp+28h]
  char *v45; // [rsp+130h] [rbp+30h]
  int v46; // [rsp+138h] [rbp+38h]
  __int64 v47; // [rsp+140h] [rbp+40h]
  const wchar_t *v48; // [rsp+148h] [rbp+48h]
  int v49; // [rsp+150h] [rbp+50h]
  char *v50; // [rsp+158h] [rbp+58h]
  int v51; // [rsp+160h] [rbp+60h]
  __int64 v52; // [rsp+168h] [rbp+68h]
  const wchar_t *v53; // [rsp+170h] [rbp+70h]
  int v54; // [rsp+178h] [rbp+78h]
  __int64 *v55; // [rsp+180h] [rbp+80h]
  int v56; // [rsp+188h] [rbp+88h]
  __int64 v57; // [rsp+190h] [rbp+90h]

  v15[1] = 8;
  memset(v22, 0, 12);
  v15[3] = 15;
  v15[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v16 = 1;
  v15[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
  v17 = 4;
  v15[4] = L"FILTER_URL_MAP_START";
  v23 = L"ContextId";
  v28 = L"OrigURL";
  v8 = -1;
  v21 = 7;
  v18 = 0;
  v19 = 0;
  v20 = 1;
  v24 = 72;
  v25 = 0;
  v26 = 16;
  v27 = 0;
  v29 = 30;
  v30 = a3;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v9 = v10 + 1;
  }
  else
  {
    v9 = 0;
  }
  v31 = v9;
  v33 = L"OrigPath";
  v32 = 0;
  v34 = 30;
  v35 = a4;
  if ( a4 )
  {
    do
      ++v8;
    while ( a4[v8] );
    v11 = v8 + 1;
  }
  else
  {
    v11 = 0;
  }
  v36 = v11;
  v37 = 0;
  v38 = L"AccessPerms";
  v40 = &a5;
  v43 = L"MatchingPath";
  v45 = &a6;
  v48 = L"MatchingURL";
  v50 = &a7;
  v53 = L"ScriptMapEntry";
  v55 = &qword_18000EE70;
  *(_QWORD *)((char *)v22 + 4) = &v23;
  v12 = *(_QWORD *)a1;
  v39 = 19;
  v42 = 0;
  v44 = 19;
  v13 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v12 + 16);
  v47 = 0;
  v49 = 19;
  v52 = 0;
  v57 = 0;
  v41 = 4;
  v46 = 4;
  v51 = 4;
  v54 = 30;
  v56 = 1;
  v13(a1, v15);
  return 0;
}

```

## disassembly

```asm
0x18000c418  push    rbp
0x18000c41a  lea     rbp, [rsp-0B0h]
0x18000c422  sub     rsp, 1B0h
0x18000c429  mov     rax, cs:__security_cookie
0x18000c430  xor     rax, rsp
0x18000c433  mov     [rbp+0B0h+var_10], rax
0x18000c43a  xor     eax, eax
0x18000c43c  mov     [rsp+1B0h+var_188], 8
0x18000c445  mov     [rsp+1B0h+var_144], rax
0x18000c44a  xor     edx, edx
0x18000c44c  mov     [rsp+1B0h+var_13C], eax
0x18000c450  xorps   xmm0, xmm0
0x18000c453  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c45a  mov     [rsp+1B0h+var_178], 0Fh
0x18000c463  mov     [rsp+1B0h+var_190], rax
0x18000c468  mov     r10, rcx
0x18000c46b  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000c472  mov     [rsp+1B0h+var_168], 1
0x18000c47a  mov     [rsp+1B0h+var_180], rax
0x18000c47f  lea     r11d, [rdx+1Eh]
0x18000c483  lea     rax, aFilterUrlMapSt; "FILTER_URL_MAP_START"
0x18000c48a  mov     [rsp+1B0h+var_164], 4
0x18000c492  mov     [rsp+1B0h+var_170], rax
0x18000c497  lea     rax, aContextid; "ContextId"
0x18000c49e  mov     [rbp+0B0h+var_130], rax
0x18000c4a2  lea     rax, aOrigurl; "OrigURL"
0x18000c4a9  mov     [rbp+0B0h+var_108], rax
0x18000c4ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c4b1  mov     [rsp+1B0h+var_148], 7
0x18000c4b9  movdqa  [rsp+1B0h+var_160], xmm0
0x18000c4bf  mov     [rsp+1B0h+var_150], edx
0x18000c4c3  mov     [rsp+1B0h+var_14C], 1
0x18000c4cb  mov     [rbp+0B0h+var_128], 48h ; 'H'
0x18000c4d2  mov     [rbp+0B0h+var_120], rdx
0x18000c4d6  mov     [rbp+0B0h+var_118], 10h
0x18000c4dd  mov     [rbp+0B0h+var_110], rdx
0x18000c4e1  mov     [rbp+0B0h+var_100], r11d
0x18000c4e5  mov     [rbp+0B0h+var_F8], r8
0x18000c4e9  test    r8, r8
0x18000c4ec  jnz     short loc_18000C4F2
0x18000c4ee  mov     ecx, edx
0x18000c4f0  jmp     short loc_18000C500
0x18000c4f2  mov     rcx, rax
0x18000c4f5  inc     rcx
0x18000c4f8  cmp     [r8+rcx], dl
0x18000c4fc  jnz     short loc_18000C4F5
0x18000c4fe  inc     ecx
0x18000c500  mov     [rbp+0B0h+var_F0], ecx
0x18000c503  lea     rcx, aOrigpath; "OrigPath"
0x18000c50a  mov     [rbp+0B0h+var_E0], rcx
0x18000c50e  mov     [rbp+0B0h+var_E8], rdx
0x18000c512  mov     [rbp+0B0h+var_D8], r11d
0x18000c516  mov     [rbp+0B0h+var_D0], r9
0x18000c51a  test    r9, r9
0x18000c51d  jnz     short loc_18000C523
0x18000c51f  mov     eax, edx
0x18000c521  jmp     short loc_18000C52E
0x18000c523  inc     rax
0x18000c526  cmp     [r9+rax], dl
0x18000c52a  jnz     short loc_18000C523
0x18000c52c  inc     eax
0x18000c52e  mov     [rbp+0B0h+var_C8], eax
0x18000c531  mov     ecx, 13h
0x18000c536  lea     rax, aAccessperms; "AccessPerms"
0x18000c53d  mov     [rbp+0B0h+var_C0], rdx
0x18000c541  mov     [rbp+0B0h+var_B8], rax
0x18000c545  lea     rax, [rbp+0B0h+arg_20]
0x18000c54c  mov     [rbp+0B0h+var_A8], rax
0x18000c550  lea     rax, aMatchingpath; "MatchingPath"
0x18000c557  mov     [rbp+0B0h+var_90], rax
0x18000c55b  lea     rax, [rbp+0B0h+arg_28]
0x18000c562  mov     [rbp+0B0h+var_80], rax
0x18000c566  lea     rax, aMatchingurl; "MatchingURL"
0x18000c56d  mov     [rbp+0B0h+var_68], rax
0x18000c571  lea     rax, [rbp+0B0h+arg_30]
0x18000c578  mov     [rbp+0B0h+var_58], rax
0x18000c57c  lea     rax, aScriptmapentry; "ScriptMapEntry"
0x18000c583  mov     [rbp+0B0h+var_40], rax
0x18000c587  lea     rax, qword_18000EE70
0x18000c58e  mov     [rbp+0B0h+var_30], rax
0x18000c595  lea     rax, [rbp+0B0h+var_130]
0x18000c599  mov     [rsp+1B0h+var_144+4], rax
0x18000c59e  mov     rax, [r10]
0x18000c5a1  mov     [rbp+0B0h+var_B0], ecx
0x18000c5a4  mov     [rbp+0B0h+var_98], rdx
0x18000c5a8  mov     [rbp+0B0h+var_88], ecx
0x18000c5ab  mov     rax, [rax+10h]
0x18000c5af  mov     [rbp+0B0h+var_70], rdx
0x18000c5b3  mov     [rbp+0B0h+var_60], ecx
0x18000c5b6  mov     rcx, r10
0x18000c5b9  mov     [rbp+0B0h+var_48], rdx
0x18000c5bd  mov     [rbp+0B0h+var_20], rdx
0x18000c5c4  lea     rdx, [rsp+1B0h+var_190]
0x18000c5c9  mov     [rbp+0B0h+var_A0], 4
0x18000c5d0  mov     [rbp+0B0h+var_78], 4
0x18000c5d7  mov     [rbp+0B0h+var_50], 4
0x18000c5de  mov     [rbp+0B0h+var_38], r11d
0x18000c5e2  mov     [rbp+0B0h+var_28], 1
0x18000c5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5f1  xor     eax, eax
0x18000c5f3  mov     rcx, [rbp+0B0h+var_10]
0x18000c5fa  xor     rcx, rsp; StackCookie
0x18000c5fd  call    __security_check_cookie
0x18000c602  add     rsp, 1B0h
0x18000c609  pop     rbp
0x18000c60a  retn
```
