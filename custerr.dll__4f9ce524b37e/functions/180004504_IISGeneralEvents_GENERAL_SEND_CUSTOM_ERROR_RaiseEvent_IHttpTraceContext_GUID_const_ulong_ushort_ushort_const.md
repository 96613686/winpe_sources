# IISGeneralEvents::GENERAL_SEND_CUSTOM_ERROR::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ushort,ushort const *)

- ea: `0x180004504`
- end: `0x180004664`
- name: `?RaiseEvent@GENERAL_SEND_CUSTOM_ERROR@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KGPEBG@Z`
- size: `352`
- prototype: `__int64 __fastcall(struct IHttpTraceContext *, const struct _GUID *, unsigned int, unsigned __int16, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800012c0`

## callees

- `0x180004504`
- `0x180007870`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall IISGeneralEvents::GENERAL_SEND_CUSTOM_ERROR::RaiseEvent(
        struct IHttpTraceContext *a1,
        const struct _GUID *a2,
        int a3,
        __int16 a4,
        const unsigned __int16 *a5)
{
  int v5; // eax
  __int64 v6; // rax
  _QWORD v8[6]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v9; // [rsp+50h] [rbp-B0h]
  int v10; // [rsp+60h] [rbp-A0h]
  int v11; // [rsp+64h] [rbp-9Ch]
  int v12; // [rsp+68h] [rbp-98h]
  _QWORD v13[2]; // [rsp+6Ch] [rbp-94h] BYREF
  const wchar_t *v14; // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+88h] [rbp-78h]
  __int64 v16; // [rsp+90h] [rbp-70h]
  int v17; // [rsp+98h] [rbp-68h]
  __int64 v18; // [rsp+A0h] [rbp-60h]
  const wchar_t *v19; // [rsp+A8h] [rbp-58h]
  int v20; // [rsp+B0h] [rbp-50h]
  int *v21; // [rsp+B8h] [rbp-48h]
  int v22; // [rsp+C0h] [rbp-40h]
  __int64 v23; // [rsp+C8h] [rbp-38h]
  const wchar_t *v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+D8h] [rbp-28h]
  __int16 *v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E8h] [rbp-18h]
  __int64 v28; // [rsp+F0h] [rbp-10h]
  const wchar_t *v29; // [rsp+F8h] [rbp-8h]
  int v30; // [rsp+100h] [rbp+0h]
  const unsigned __int16 *v31; // [rsp+108h] [rbp+8h]
  int v32; // [rsp+110h] [rbp+10h]
  __int64 v33; // [rsp+118h] [rbp+18h]
  int v34; // [rsp+150h] [rbp+50h] BYREF
  __int16 v35; // [rsp+158h] [rbp+58h] BYREF

  v35 = a4;
  v34 = a3;
  v8[3] = 33;
  v8[1] = 0;
  memset(v13, 0, 12);
  v8[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v8[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
  v8[4] = L"GENERAL_SEND_CUSTOM_ERROR";
  v8[5] = 1;
  v11 = 1;
  v14 = L"ContextId";
  v19 = L"HttpStatus";
  v21 = &v34;
  v24 = L"HttpSubStatus";
  v12 = 4;
  v22 = 4;
  v26 = &v35;
  v29 = L"FileNameOrURL";
  v9 = 0;
  v10 = 0;
  v15 = 72;
  v16 = 0;
  v17 = 16;
  v18 = 0;
  v20 = 19;
  v23 = 0;
  v25 = 18;
  v27 = 2;
  v28 = 0;
  v30 = 31;
  v31 = a5;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v5 = 2 * v6 + 2;
  }
  else
  {
    v5 = 0;
  }
  v32 = v5;
  v33 = 0;
  *(_QWORD *)((char *)v13 + 4) = &v14;
  (*(void (__fastcall **)(struct IHttpTraceContext *, _QWORD *))(*(_QWORD *)a1 + 16LL))(a1, v8);
  return 0;
}

```

## disassembly

```asm
0x180004504  mov     [rsp-8+arg_18], r9w
0x18000450a  mov     [rsp-8+arg_10], r8d
0x18000450f  push    rbp
0x180004510  lea     rbp, [rsp-30h]
0x180004515  sub     rsp, 130h
0x18000451c  mov     rax, cs:__security_cookie
0x180004523  xor     rax, rsp
0x180004526  mov     [rbp+30h+var_10], rax
0x18000452a  xor     eax, eax
0x18000452c  mov     [rsp+130h+var_F8], 21h ; '!'
0x180004535  mov     [rsp+130h+var_108], rax
0x18000453a  xor     r8d, r8d
0x18000453d  mov     [rsp+130h+var_C4], rax
0x180004542  xorps   xmm0, xmm0
0x180004545  mov     [rsp+130h+var_BC], eax
0x180004549  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004550  mov     [rsp+130h+var_110], rax
0x180004555  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000455c  mov     [rsp+130h+var_100], rax
0x180004561  lea     rax, aGeneralSendCus; "GENERAL_SEND_CUSTOM_ERROR"
0x180004568  mov     [rsp+130h+var_F0], rax
0x18000456d  lea     eax, [r8+1]
0x180004571  lea     edx, [rax+3]
0x180004574  mov     [rsp+130h+var_E8], rax
0x180004579  mov     [rsp+130h+var_CC], eax
0x18000457d  lea     rax, aContextid; "ContextId"
0x180004584  mov     [rbp+30h+var_B0], rax
0x180004588  lea     rax, aHttpstatus; "HttpStatus"
0x18000458f  mov     [rbp+30h+var_88], rax
0x180004593  lea     rax, [rbp+30h+arg_10]
0x180004597  mov     [rbp+30h+var_78], rax
0x18000459b  lea     rax, aHttpsubstatus; "HttpSubStatus"
0x1800045a2  mov     [rbp+30h+var_60], rax
0x1800045a6  lea     rax, [rbp+30h+arg_18]
0x1800045aa  mov     [rsp+130h+var_C8], edx
0x1800045ae  mov     [rbp+30h+var_70], edx
0x1800045b1  mov     rdx, [rbp+30h+arg_20]
0x1800045b5  mov     [rbp+30h+var_50], rax
0x1800045b9  lea     rax, aFilenameorurl; "FileNameOrURL"
0x1800045c0  mov     [rbp+30h+var_38], rax
0x1800045c4  movdqa  [rsp+130h+var_E0], xmm0
0x1800045ca  mov     [rsp+130h+var_D0], r8d
0x1800045cf  mov     [rbp+30h+var_A8], 48h ; 'H'
0x1800045d6  mov     [rbp+30h+var_A0], r8
0x1800045da  mov     [rbp+30h+var_98], 10h
0x1800045e1  mov     [rbp+30h+var_90], r8
0x1800045e5  mov     [rbp+30h+var_80], 13h
0x1800045ec  mov     [rbp+30h+var_68], r8
0x1800045f0  mov     [rbp+30h+var_58], 12h
0x1800045f7  mov     [rbp+30h+var_48], 2
0x1800045fe  mov     [rbp+30h+var_40], r8
0x180004602  mov     [rbp+30h+var_30], 1Fh
0x180004609  mov     [rbp+30h+var_28], rdx
0x18000460d  test    rdx, rdx
0x180004610  jnz     short loc_180004617
0x180004612  mov     eax, r8d
0x180004615  jmp     short loc_18000462C
0x180004617  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000461b  inc     rax
0x18000461e  cmp     [rdx+rax*2], r8w
0x180004623  jnz     short loc_18000461B
0x180004625  lea     eax, ds:2[rax*2]
0x18000462c  mov     [rbp+30h+var_20], eax
0x18000462f  lea     rdx, [rsp+130h+var_110]
0x180004634  lea     rax, [rbp+30h+var_B0]
0x180004638  mov     [rbp+30h+var_18], r8
0x18000463c  mov     [rsp+130h+var_C4+4], rax
0x180004641  mov     rax, [rcx]
0x180004644  mov     rax, [rax+10h]
0x180004648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000464d  xor     eax, eax
0x18000464f  mov     rcx, [rbp+30h+var_10]
0x180004653  xor     rcx, rsp; StackCookie
0x180004656  call    __security_check_cookie
0x18000465b  add     rsp, 130h
0x180004662  pop     rbp
0x180004663  retn
```
