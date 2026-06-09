# IISFastCGIEvents::FASTCGI_ASSIGN_PROCESS::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,int,ulong,ulong)

- ea: `0x18000dc5c`
- end: `0x18000dde3`
- name: `?RaiseEvent@FASTCGI_ASSIGN_PROCESS@IISFastCGIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGHKK@Z`
- size: `391`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, const unsigned __int16 *, int, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cb30`

## callees

- `0x18000dc5c`
- `0x18000ee10`
- `0x180010010`

## string_xrefs

- `0x18000dcd3`: `CommandLine`
- `0x18000dd5d`: `ProcessId`

## pseudocode

```c
__int64 __fastcall IISFastCGIEvents::FASTCGI_ASSIGN_PROCESS::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4,
        char a5,
        char a6)
{
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  void (__fastcall *v9)(struct IHttpTraceContext *, _QWORD *); // rax
  _QWORD v11[6]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+60h] [rbp-A0h]
  int v14; // [rsp+64h] [rbp-9Ch]
  int v15; // [rsp+68h] [rbp-98h]
  _QWORD v16[2]; // [rsp+6Ch] [rbp-94h] BYREF
  const wchar_t *v17; // [rsp+80h] [rbp-80h] BYREF
  int v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+98h] [rbp-68h]
  __int64 v21; // [rsp+A0h] [rbp-60h]
  const wchar_t *v22; // [rsp+A8h] [rbp-58h]
  int v23; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v24; // [rsp+B8h] [rbp-48h]
  int v25; // [rsp+C0h] [rbp-40h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  const wchar_t *v27; // [rsp+D0h] [rbp-30h]
  int v28; // [rsp+D8h] [rbp-28h]
  int *v29; // [rsp+E0h] [rbp-20h]
  int v30; // [rsp+E8h] [rbp-18h]
  __int64 v31; // [rsp+F0h] [rbp-10h]
  const wchar_t *v32; // [rsp+F8h] [rbp-8h]
  int v33; // [rsp+100h] [rbp+0h]
  char *v34; // [rsp+108h] [rbp+8h]
  int v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  const wchar_t *v37; // [rsp+120h] [rbp+20h]
  int v38; // [rsp+128h] [rbp+28h]
  char *v39; // [rsp+130h] [rbp+30h]
  int v40; // [rsp+138h] [rbp+38h]
  __int64 v41; // [rsp+140h] [rbp+40h]
  int v42; // [rsp+188h] [rbp+88h] BYREF

  v42 = a4;
  v11[1] = 4096;
  memset(v16, 0, 12);
  v11[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v11[2] = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
  v11[4] = L"FASTCGI_ASSIGN_PROCESS";
  v11[5] = 1;
  v14 = 1;
  v17 = L"ContextId";
  v22 = L"CommandLine";
  v11[3] = 17;
  v15 = 5;
  v12 = 0;
  v13 = 0;
  v18 = 72;
  v19 = 0;
  v20 = 16;
  v21 = 0;
  v23 = 31;
  v24 = a3;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v6 = 2 * v7 + 2;
  }
  else
  {
    v6 = 0;
  }
  v25 = v6;
  v26 = 0;
  v27 = L"IsNewProcess";
  v29 = &v42;
  v32 = L"ProcessId";
  v33 = 19;
  v34 = &a5;
  v37 = L"RequestNumber";
  v39 = &a6;
  *(_QWORD *)((char *)v16 + 4) = &v17;
  v8 = *(_QWORD *)a1;
  v38 = 19;
  v28 = 11;
  v30 = 4;
  v9 = *(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(v8 + 16);
  v31 = 0;
  v35 = 4;
  v36 = 0;
  v40 = 4;
  v41 = 0;
  v9(a1, v11);
  return 0;
}

```

## disassembly

```asm
0x18000dc5c  mov     [rsp-8+arg_18], r9d
0x18000dc61  push    rbp
0x18000dc62  lea     rbp, [rsp-60h]
0x18000dc67  sub     rsp, 160h
0x18000dc6e  mov     rax, cs:__security_cookie
0x18000dc75  xor     rax, rsp
0x18000dc78  mov     [rbp+60h+var_10], rax
0x18000dc7c  xor     eax, eax
0x18000dc7e  mov     [rsp+160h+var_138], 1000h
0x18000dc87  mov     [rsp+160h+var_F4], rax
0x18000dc8c  xor     r9d, r9d
0x18000dc8f  mov     [rsp+160h+var_EC], eax
0x18000dc93  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000dc9a  mov     [rsp+160h+var_140], rax
0x18000dc9f  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000dca6  mov     [rsp+160h+var_130], rax
0x18000dcab  lea     rax, aFastcgiAssignP; "FASTCGI_ASSIGN_PROCESS"
0x18000dcb2  mov     [rsp+160h+var_120], rax
0x18000dcb7  mov     eax, 1
0x18000dcbc  mov     [rsp+160h+var_118], rax
0x18000dcc1  xorps   xmm0, xmm0
0x18000dcc4  mov     [rsp+160h+var_FC], eax
0x18000dcc8  lea     rax, aContextid; "ContextId"
0x18000dccf  mov     [rbp+60h+var_E0], rax
0x18000dcd3  lea     rax, aCommandline; "CommandLine"
0x18000dcda  mov     [rbp+60h+var_B8], rax
0x18000dcde  mov     [rsp+160h+var_128], 11h
0x18000dce7  mov     [rsp+160h+var_F8], 5
0x18000dcef  movdqa  [rsp+160h+var_110], xmm0
0x18000dcf5  mov     [rsp+160h+var_100], r9d
0x18000dcfa  mov     [rbp+60h+var_D8], 48h ; 'H'
0x18000dd01  mov     [rbp+60h+var_D0], r9
0x18000dd05  mov     [rbp+60h+var_C8], 10h
0x18000dd0c  mov     [rbp+60h+var_C0], r9
0x18000dd10  mov     [rbp+60h+var_B0], 1Fh
0x18000dd17  mov     [rbp+60h+var_A8], r8
0x18000dd1b  test    r8, r8
0x18000dd1e  jnz     short loc_18000DD25
0x18000dd20  mov     eax, r9d
0x18000dd23  jmp     short loc_18000DD3A
0x18000dd25  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dd29  inc     rax
0x18000dd2c  cmp     [r8+rax*2], r9w
0x18000dd31  jnz     short loc_18000DD29
0x18000dd33  lea     eax, ds:2[rax*2]
0x18000dd3a  mov     [rbp+60h+var_A0], eax
0x18000dd3d  mov     r8d, 4
0x18000dd43  lea     rax, aIsnewprocess; "IsNewProcess"
0x18000dd4a  mov     [rbp+60h+var_98], r9
0x18000dd4e  mov     [rbp+60h+var_90], rax
0x18000dd52  lea     rax, [rbp+60h+arg_18]
0x18000dd59  mov     [rbp+60h+var_80], rax
0x18000dd5d  lea     rax, aProcessid; "ProcessId"
0x18000dd64  mov     [rbp+60h+var_68], rax
0x18000dd68  lea     edx, [r8+0Fh]
0x18000dd6c  lea     rax, [rbp+60h+arg_20]
0x18000dd73  mov     [rbp+60h+var_60], edx
0x18000dd76  mov     [rbp+60h+var_58], rax
0x18000dd7a  lea     rax, aRequestnumber; "RequestNumber"
0x18000dd81  mov     [rbp+60h+var_40], rax
0x18000dd85  lea     rax, [rbp+60h+arg_28]
0x18000dd8c  mov     [rbp+60h+var_30], rax
0x18000dd90  lea     rax, [rbp+60h+var_E0]
0x18000dd94  mov     [rsp+160h+var_F4+4], rax
0x18000dd99  mov     rax, [rcx]
0x18000dd9c  mov     [rbp+60h+var_38], edx
0x18000dd9f  lea     rdx, [rsp+160h+var_140]
0x18000dda4  mov     [rbp+60h+var_88], 0Bh
0x18000ddab  mov     [rbp+60h+var_78], r8d
0x18000ddaf  mov     rax, [rax+10h]
0x18000ddb3  mov     [rbp+60h+var_70], r9
0x18000ddb7  mov     [rbp+60h+var_50], r8d
0x18000ddbb  mov     [rbp+60h+var_48], r9
0x18000ddbf  mov     [rbp+60h+var_28], r8d
0x18000ddc3  mov     [rbp+60h+var_20], r9
0x18000ddc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddcc  xor     eax, eax
0x18000ddce  mov     rcx, [rbp+60h+var_10]
0x18000ddd2  xor     rcx, rsp; StackCookie
0x18000ddd5  call    __security_check_cookie
0x18000ddda  add     rsp, 160h
0x18000dde1  pop     rbp
0x18000dde2  retn
```
