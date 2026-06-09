# HTTP_COMPRESSION::SetupDynamicCompression(IHttpContext *,COMPRESS_META_STORED_CONTEXT *,COMPRESSION_CONTEXT * *)

- ea: `0x180001eb0`
- end: `0x1800024be`
- name: `?SetupDynamicCompression@HTTP_COMPRESSION@@CAJPEAVIHttpContext@@PEAVCOMPRESS_META_STORED_CONTEXT@@PEAPEAVCOMPRESSION_CONTEXT@@@Z`
- size: `1550`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct COMPRESS_META_STORED_CONTEXT *, struct COMPRESSION_CONTEXT **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180001a60`

## callees

- `0x180001eb0`
- `0x1800024d0`
- `0x180002690`
- `0x180002f20`
- `0x180004c10`
- `0x1800066e8`
- `0x180006af4`
- `0x180006bb0`
- `0x180006c9c`
- `0x180006d58`
- `0x180008010`

## import_xrefs

- `msvcrt!strchr` at `0x18000552c`
- `msvcrt!strchr` at `0x18000552c`
- `msvcrt!_stricmp` at `0x180005504`
- `msvcrt!_stricmp` at `0x180005504`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002019`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000247f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002019`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000247f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800021d3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000237c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180005547`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800055ae`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800021d3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000237c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180005547`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800055ae`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001f4b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001f4b`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800021b6`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800021b6`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180002392`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000555b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000559f`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180002392`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000555b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000559f`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180002261`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180002261`

## string_xrefs

- `0x180002089`: `IIS_EnableDynamicCompression`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::SetupDynamicCompression(
        struct IHttpContext *a1,
        struct COMPRESS_META_STORED_CONTEXT *a2,
        struct COMPRESSION_CONTEXT **a3)
{
  __int64 v3; // rax
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  struct IHttpRequest *v9; // rdi
  __int64 v10; // r12
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int (__fastcall ***v13)(_QWORD, GUID **); // rax
  int v14; // edi
  int (__fastcall ***v15)(_QWORD, GUID **); // rax
  __int16 v17; // cx
  const char *v18; // rax
  const char *v19; // rax
  const char *v20; // rsi
  int v21; // r13d
  __int16 v22; // ax
  char *Str; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r12
  __int64 v27; // rax
  __int64 v28; // rax
  struct COMPRESSION_SCHEME * near *v29; // rdx
  const char *v30; // rax
  __int64 v31; // rsi
  __int64 v32; // rdi
  __int64 v33; // rax
  int (__fastcall ***v34)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v35; // rax
  const struct _GUID *v36; // rdx
  char *v37; // rax
  STRA *v38; // rcx
  const char *v39; // rax
  __int64 (__fastcall *v40)(__int64, _QWORD, char *, _QWORD, _DWORD); // rsi
  unsigned __int16 CCH; // di
  char *v42; // rax
  struct IHttpTraceContext *v43; // rax
  const struct _GUID *v44; // rdx
  struct IHttpTraceContext *v45; // rax
  const struct _GUID *v46; // rdx
  struct IHttpTraceContext *v47; // rax
  const struct _GUID *v48; // rdx
  int v49; // [rsp+30h] [rbp-D0h] BYREF
  GUID *v50; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v51; // [rsp+40h] [rbp-C0h]
  int v52; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v53; // [rsp+58h] [rbp-A8h] BYREF
  struct COMPRESSION_CONTEXT **v54; // [rsp+60h] [rbp-A0h]
  _BYTE v55[56]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v56[100]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v57[2]; // [rsp+230h] [rbp+130h] BYREF
  char v58[512]; // [rsp+240h] [rbp+140h] BYREF

  v3 = *(_QWORD *)a1;
  v54 = a3;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 32))(a1);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  v8 = *(_QWORD *)a1;
  v57[0] = v7;
  v9 = (struct IHttpRequest *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 24))(a1);
  v10 = (*(__int64 (__fastcall **)(struct IHttpRequest *))(*(_QWORD *)v9 + 8LL))(v9);
  v11 = 6;
  STRA::STRA((STRA *)v55, v58, 0x200u);
  v12 = *(_QWORD *)a1;
  v53 = 0;
  v52 = 0;
  v13 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(v12 + 272))(a1);
  v50 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v51 = 0;
  if ( (**v13)(v13, &v50) >= 0 && DWORD2(v51) && DWORD1(v51) >= 4 && ((_DWORD)v51 == 64 || (v51 & 0x40) != 0) )
  {
    v35 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    IISCompressionEvents::DYNAMIC_COMPRESSION_START::RaiseEvent(v35, v36);
  }
  if ( HTTP_COMPRESSION::sm_InitStatus != 5 )
    goto LABEL_6;
  if ( HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu || !HTTP_COMPRESSION::sm_fDoDynamicCompression )
    goto LABEL_5;
  v17 = *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 8);
  if ( v17 != 200 && (unsigned __int16)(v17 - 206) > 1u )
  {
    v11 = 9;
    goto LABEL_6;
  }
  if ( (*(int (__fastcall **)(struct IHttpContext *, const char *, _WORD **, int *))(*(_QWORD *)a1 + 128LL))(
         a1,
         "IIS_EnableDynamicCompression",
         &v53,
         &v52) < 0 )
  {
    if ( *((_DWORD *)a2 + 3) )
      goto LABEL_14;
LABEL_5:
    v11 = 2;
LABEL_6:
    v14 = 0;
    goto LABEL_7;
  }
  if ( *v53 == 48 && !v53[1] )
    goto LABEL_5;
LABEL_14:
  v18 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v6 + 64LL))(v6, 12, 0);
  if ( !v18
    || !(unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsContentTypeAllowed(
                        v18,
                        (struct _LIST_ENTRY *)a2 + 3,
                        *((_DWORD *)a2 + 16)) )
  {
    v11 = 12;
    goto LABEL_6;
  }
  v19 = (const char *)(*(__int64 (__fastcall **)(struct IHttpRequest *, __int64, _QWORD))(*(_QWORD *)v9 + 16LL))(
                        v9,
                        22,
                        0);
  v20 = v19;
  if ( !v19 || !*v19 )
  {
    v11 = 1;
    goto LABEL_6;
  }
  v21 = *(_DWORD *)(v10 + 36);
  if ( v21 == 9 )
  {
    v14 = 0;
    goto LABEL_7;
  }
  if ( HTTP_COMPRESSION::sm_fNoCompressionForHttp10 )
  {
    v22 = *(_WORD *)(v10 + 32);
    if ( !v22 || v22 == 1 && !*(_WORD *)(v10 + 34) )
    {
      v11 = 3;
      v14 = 0;
      goto LABEL_7;
    }
  }
  if ( HTTP_COMPRESSION::sm_fNoCompressionForProxies && (unsigned int)IsProxyRequest(v9) )
  {
    v11 = 4;
    v14 = 0;
    goto LABEL_7;
  }
  if ( HTTP_COMPRESSION::sm_fNoCompressionForRange
    && (*(__int64 (__fastcall **)(struct IHttpRequest *, __int64, _QWORD))(*(_QWORD *)v9 + 16LL))(v9, 37, 0) )
  {
    v11 = 11;
    v14 = 0;
    goto LABEL_7;
  }
  if ( (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v6 + 64LL))(v6, 13, 0) )
  {
    v11 = 10;
    v14 = 0;
    goto LABEL_7;
  }
  v14 = STRA::Copy((STRA *)v55, v20);
  if ( v14 < 0 )
    goto LABEL_7;
  v49 = 0;
  Str = STRA::QueryStr((STRA *)v55);
  HTTP_COMPRESSION::FindMatchingSchemes(Str, v24, v56, &v49);
  if ( !v49 )
  {
    v11 = 5;
    v14 = 0;
    goto LABEL_7;
  }
  v25 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 240LL))(a1);
  v26 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 144LL))(v25, 168);
  if ( !v26 )
  {
    v14 = -2147024888;
LABEL_7:
    v15 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    v50 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v51 = 0;
    if ( (**v15)(v15, &v50) >= 0 && DWORD2(v51) && DWORD1(v51) >= 4 && ((_DWORD)v51 == 64 || (v51 & 0x40) != 0) )
    {
      v45 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      IISCompressionEvents::DYNAMIC_COMPRESSION_NOT_SUCCESS::RaiseEvent(v45, v46, v11);
      v47 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      IISCompressionEvents::DYNAMIC_COMPRESSION_END::RaiseEvent(v47, v48);
    }
    STRA::~STRA((STRA *)v55);
    return (unsigned int)v14;
  }
  *(_QWORD *)(v26 + 8) = 0;
  *(_QWORD *)v26 = &COMPRESSION_CONTEXT::`vftable';
  *(_QWORD *)(v26 + 16) = 0;
  *(_DWORD *)(v26 + 24) = 0;
  *(_QWORD *)(v26 + 32) = 0;
  BUFFER::BUFFER((BUFFER *)(v26 + 40));
  *(_QWORD *)(v26 + 120) = 0;
  *(_QWORD *)(v26 + 152) = v26 + 144;
  *(_QWORD *)(v26 + 144) = v26 + 144;
  *(_QWORD *)(v26 + 128) = 0;
  *(_QWORD *)(v26 + 136) = 0;
  *(_DWORD *)(v26 + 160) = 0;
  *(_DWORD *)(v26 + 164) = 1;
  v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 240LL))(a1);
  v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 56LL))(v27);
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v28 + 8LL))(v28, v26, g_pModuleContext);
  if ( v14 < 0 )
  {
    (**(void (__fastcall ***)(__int64))v26)(v26);
    goto LABEL_7;
  }
  v29 = (&HTTP_COMPRESSION::sm_pCompressionSchemes)[v56[0]];
  *(_QWORD *)(v26 + 8) = v29;
  v14 = ((__int64 (__fastcall *)(__int64, _QWORD))v29[24])(v26 + 32, *((unsigned int *)v29 + 58));
  if ( v14 < 0 )
    goto LABEL_7;
  v30 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v6 + 64LL))(v6, 6, 0);
  if ( v30 && !_stricmp(v30, "chunked") )
    *(_DWORD *)(v26 + 16) = 1;
  v31 = v57[0];
  *(_QWORD *)(v57[0] + 240LL) = 0;
  *(_WORD *)(v31 + 232) = 0;
  *(_QWORD *)(v31 + 160) = 0;
  *(_WORD *)(v31 + 152) = 0;
  *(_QWORD *)(v31 + 272) = STRA::QueryStr((STRA *)(*(_QWORD *)(v26 + 8) + 56LL));
  *(_WORD *)(v31 + 264) = STRA::QueryCCH((STRA *)(*(_QWORD *)(v26 + 8) + 56LL));
  v32 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
  strcpy((char *)v57, "Accept-Encoding");
  if ( *(_WORD *)(v33 + 504) != 1 || !strchr(*(const char **)(v33 + 512), 42) )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, __int64, _DWORD))(*(_QWORD *)v32 + 32LL))(
            v32,
            28,
            v57,
            15,
            0);
    if ( v14 < 0 )
      goto LABEL_7;
  }
  if ( HTTP_COMPRESSION::sm_fSendCacheHeaders )
  {
    v37 = STRA::QueryStr((STRA *)HTTP_COMPRESSION::sm_pstrExpiresHeader);
    v38 = (STRA *)HTTP_COMPRESSION::sm_pstrExpiresHeader;
    *(_QWORD *)(v31 + 352) = v37;
    *(_WORD *)(v31 + 344) = STRA::QueryCCH(v38);
    v39 = (const char *)(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 64LL))(v6, 0, 0);
    if ( !v39 || (unsigned int)DoesCacheControlNeedMaxAge(v39) )
    {
      v40 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, _QWORD, _DWORD))(*(_QWORD *)v6 + 32LL);
      CCH = STRA::QueryCCH((STRA *)HTTP_COMPRESSION::sm_pstrCacheControlHeader);
      v42 = STRA::QueryStr((STRA *)HTTP_COMPRESSION::sm_pstrCacheControlHeader);
      v14 = v40(v6, 0, v42, CCH, 0);
      if ( v14 < 0 )
        goto LABEL_7;
    }
  }
  if ( v21 == 5 )
    *(_DWORD *)(v26 + 160) = 1;
  v34 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  v50 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v51 = 0;
  if ( (**v34)(v34, &v50) >= 0 && DWORD2(v51) && DWORD1(v51) >= 4 && ((_DWORD)v51 == 64 || (v51 & 0x40) != 0) )
  {
    v43 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    IISCompressionEvents::DYNAMIC_COMPRESSION_SUCCESS::RaiseEvent(v43, v44);
  }
  *v54 = (struct COMPRESSION_CONTEXT *)v26;
  STRA::~STRA((STRA *)v55);
  return 0;
}

```

## disassembly

```asm
0x180001eb0  mov     [rsp-8+arg_18], rbx
0x180001eb5  push    rbp
0x180001eb6  push    rsi
0x180001eb7  push    rdi
0x180001eb8  push    r12
0x180001eba  push    r13
0x180001ebc  push    r14
0x180001ebe  push    r15
0x180001ec0  lea     rbp, [rsp-350h]
0x180001ec8  sub     rsp, 450h
0x180001ecf  mov     rax, cs:__security_cookie
0x180001ed6  xor     rax, rsp
0x180001ed9  mov     [rbp+380h+var_40], rax
0x180001ee0  mov     rax, [rcx]
0x180001ee3  mov     rsi, rdx
0x180001ee6  mov     [rsp+480h+var_420], r8
0x180001eeb  mov     r14, rcx
0x180001eee  mov     rax, [rax+20h]
0x180001ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef7  mov     r15, rax
0x180001efa  mov     rcx, [rax]
0x180001efd  mov     rax, [rcx+8]
0x180001f01  mov     rcx, r15
0x180001f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f09  mov     rcx, [r14]
0x180001f0c  mov     qword ptr [rbp+380h+var_250], rax
0x180001f13  mov     rax, [rcx+18h]
0x180001f17  mov     rcx, r14
0x180001f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f1f  mov     rdi, rax
0x180001f22  mov     rcx, [rax]
0x180001f25  mov     rax, [rcx+8]
0x180001f29  mov     rcx, rdi
0x180001f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f31  mov     r8d, 200h
0x180001f37  lea     rdx, [rbp+380h+var_240]
0x180001f3e  lea     rcx, [rsp+480h+var_418]
0x180001f43  mov     r12, rax
0x180001f46  mov     ebx, 6
0x180001f4b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001f51  mov     rcx, [r14]
0x180001f54  xor     r13d, r13d
0x180001f57  mov     [rsp+480h+var_428], r13
0x180001f5c  mov     [rsp+480h+var_430], r13d
0x180001f61  mov     rax, [rcx+110h]
0x180001f68  mov     rcx, r14
0x180001f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f70  mov     r8, rax
0x180001f73  lea     rdx, [rsp+480h+var_448]
0x180001f78  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001f7f  xorps   xmm0, xmm0
0x180001f82  mov     [rsp+480h+var_448], rax
0x180001f87  movdqu  [rsp+480h+var_440], xmm0
0x180001f8d  mov     rcx, [r8]
0x180001f90  mov     rax, [rcx]
0x180001f93  mov     rcx, r8
0x180001f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f9b  test    eax, eax
0x180001f9d  js      short loc_180001FAA
0x180001f9f  cmp     dword ptr [rsp+480h+var_440+8], r13d
0x180001fa4  jnz     loc_180005452
0x180001faa  cmp     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 5; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180001fb1  jnz     short loc_180001FC5
0x180001fb3  cmp     cs:?sm_fDynamicCompressionDisabledDueToHighCpu@HTTP_COMPRESSION@@0HA, r13d; int HTTP_COMPRESSION::sm_fDynamicCompressionDisabledDueToHighCpu
0x180001fba  jz      loc_18000204B
0x180001fc0  mov     ebx, 2
0x180001fc5  mov     edi, r13d
0x180001fc8  mov     rax, [r14]
0x180001fcb  mov     rcx, r14
0x180001fce  mov     rax, [rax+110h]
0x180001fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fda  mov     r8, rax
0x180001fdd  lea     rdx, [rsp+480h+var_448]
0x180001fe2  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001fe9  xorps   xmm0, xmm0
0x180001fec  mov     [rsp+480h+var_448], rax
0x180001ff1  movdqu  [rsp+480h+var_440], xmm0
0x180001ff7  mov     rcx, [r8]
0x180001ffa  mov     rax, [rcx]
0x180001ffd  mov     rcx, r8
0x180002000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002005  test    eax, eax
0x180002007  js      short loc_180002014
0x180002009  cmp     dword ptr [rsp+480h+var_440+8], 0
0x18000200e  jnz     loc_180005641
0x180002014  lea     rcx, [rsp+480h+var_418]
0x180002019  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000201f  mov     eax, edi
0x180002021  mov     rcx, [rbp+380h+var_40]
0x180002028  xor     rcx, rsp; StackCookie
0x18000202b  call    __security_check_cookie
0x180002030  mov     rbx, [rsp+480h+arg_18]
0x180002038  add     rsp, 450h
0x18000203f  pop     r15
0x180002041  pop     r14
0x180002043  pop     r13
0x180002045  pop     r12
0x180002047  pop     rdi
0x180002048  pop     rsi
0x180002049  pop     rbp
0x18000204a  retn
0x18000204b  cmp     cs:?sm_fDoDynamicCompression@HTTP_COMPRESSION@@2HA, r13d; int HTTP_COMPRESSION::sm_fDoDynamicCompression
0x180002052  jz      loc_180001FC0
0x180002058  mov     rax, [r15]
0x18000205b  mov     rcx, r15
0x18000205e  mov     rax, [rax+8]
0x180002062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002067  movzx   ecx, word ptr [rax+8]
0x18000206b  mov     eax, 0C8h
0x180002070  cmp     cx, ax
0x180002073  jnz     loc_180002496
0x180002079  mov     rax, [r14]
0x18000207c  lea     r9, [rsp+480h+var_430]
0x180002081  lea     r8, [rsp+480h+var_428]
0x180002086  mov     rcx, r14
0x180002089  lea     rdx, aIisEnabledynam; "IIS_EnableDynamicCompression"
0x180002090  mov     rax, [rax+80h]
0x180002097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000209c  test    eax, eax
0x18000209e  jns     loc_18000548F
0x1800020a4  cmp     [rsi+0Ch], r13d
0x1800020a8  jz      loc_180001FC0
0x1800020ae  mov     rax, [r15]
0x1800020b1  xor     r8d, r8d
0x1800020b4  mov     edx, 0Ch
0x1800020b9  mov     rcx, r15
0x1800020bc  mov     rax, [rax+40h]
0x1800020c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c5  test    rax, rax
0x1800020c8  jz      loc_18000248C
0x1800020ce  mov     r8d, [rsi+40h]; int
0x1800020d2  lea     rdx, [rsi+30h]; struct _LIST_ENTRY *
0x1800020d6  mov     rcx, rax; Str
0x1800020d9  call    ?IsContentTypeAllowed@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDPEAU_LIST_ENTRY@@H@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsContentTypeAllowed(char const *,_LIST_ENTRY *,int)
0x1800020de  test    eax, eax
0x1800020e0  jz      loc_18000248C
0x1800020e6  mov     rax, [rdi]
0x1800020e9  xor     r8d, r8d
0x1800020ec  mov     edx, 16h
0x1800020f1  mov     rcx, rdi
0x1800020f4  mov     rax, [rax+10h]
0x1800020f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020fd  mov     rsi, rax
0x180002100  test    rax, rax
0x180002103  jz      loc_180005637
0x180002109  cmp     [rax], r13b
0x18000210c  jz      loc_180005637
0x180002112  mov     r13d, [r12+24h]
0x180002117  cmp     r13d, 9
0x18000211b  jz      loc_1800054AE
0x180002121  cmp     cs:?sm_fNoCompressionForHttp10@HTTP_COMPRESSION@@0HA, 0; int HTTP_COMPRESSION::sm_fNoCompressionForHttp10
0x180002128  jz      short loc_18000214C
0x18000212a  movzx   eax, word ptr [r12+20h]
0x180002130  test    ax, ax
0x180002133  jz      loc_1800054B5
0x180002139  cmp     ax, 1
0x18000213d  jnz     short loc_18000214C
0x18000213f  cmp     word ptr [r12+22h], 0
0x180002146  jz      loc_1800054B5
0x18000214c  cmp     cs:?sm_fNoCompressionForProxies@HTTP_COMPRESSION@@0HA, 0; int HTTP_COMPRESSION::sm_fNoCompressionForProxies
0x180002153  jz      short loc_180002165
0x180002155  mov     rcx, rdi; struct IHttpRequest *
0x180002158  call    ?IsProxyRequest@@YAHPEAVIHttpRequest@@@Z; IsProxyRequest(IHttpRequest *)
0x18000215d  test    eax, eax
0x18000215f  jnz     loc_1800054C1
0x180002165  cmp     cs:?sm_fNoCompressionForRange@HTTP_COMPRESSION@@0HA, 0; int HTTP_COMPRESSION::sm_fNoCompressionForRange
0x18000216c  jz      short loc_18000218E
0x18000216e  mov     rax, [rdi]
0x180002171  xor     r8d, r8d
0x180002174  mov     edx, 25h ; '%'
0x180002179  mov     rcx, rdi
0x18000217c  mov     rax, [rax+10h]
0x180002180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002185  test    rax, rax
0x180002188  jnz     loc_1800054CD
0x18000218e  mov     rax, [r15]
0x180002191  xor     r8d, r8d
0x180002194  mov     edx, 0Dh
0x180002199  mov     rcx, r15
0x18000219c  mov     rax, [rax+40h]
0x1800021a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a5  test    rax, rax
0x1800021a8  jnz     loc_1800024B2
0x1800021ae  mov     rdx, rsi
0x1800021b1  lea     rcx, [rsp+480h+var_418]
0x1800021b6  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800021bc  mov     edi, eax
0x1800021be  test    eax, eax
0x1800021c0  js      loc_180001FC8
0x1800021c6  lea     rcx, [rsp+480h+var_418]
0x1800021cb  mov     [rsp+480h+var_450], 0
0x1800021d3  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800021d9  mov     rcx, rax
0x1800021dc  lea     r9, [rsp+480h+var_450]
0x1800021e1  lea     r8, [rbp+380h+var_3E0]
0x1800021e5  call    ?FindMatchingSchemes@HTTP_COMPRESSION@@CAXPEADW4COMPRESSION_TO_PERFORM@@QEAKPEAK@Z; HTTP_COMPRESSION::FindMatchingSchemes(char *,COMPRESSION_TO_PERFORM,ulong * const,ulong *)
0x1800021ea  cmp     [rsp+480h+var_450], 0
0x1800021ef  jz      loc_1800054D9
0x1800021f5  mov     rax, [r14]
0x1800021f8  mov     rcx, r14
0x1800021fb  mov     rax, [rax+0F0h]
0x180002202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002207  mov     r8, rax
0x18000220a  mov     edx, 0A8h
0x18000220f  mov     rcx, [rax]
0x180002212  mov     rax, [rcx+90h]
0x180002219  mov     rcx, r8
0x18000221c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002221  mov     r12, rax
0x180002224  test    rax, rax
0x180002227  jz      loc_18000562D
0x18000222d  lea     rax, ??_7COMPRESSION_CONTEXT@@6B@; const COMPRESSION_CONTEXT::`vftable'
0x180002234  mov     qword ptr [r12+8], 0
0x18000223d  lea     rcx, [r12+28h]
0x180002242  mov     [r12], rax
0x180002246  mov     qword ptr [r12+10h], 0
0x18000224f  mov     dword ptr [r12+18h], 0
0x180002258  mov     qword ptr [r12+20h], 0
0x180002261  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180002267  lea     rax, [r12+90h]
0x18000226f  mov     qword ptr [r12+78h], 0
0x180002278  mov     [rax+8], rax
0x18000227c  mov     rcx, r14
0x18000227f  mov     [rax], rax
0x180002282  mov     qword ptr [r12+80h], 0
0x18000228e  mov     qword ptr [r12+88h], 0
0x18000229a  mov     dword ptr [r12+0A0h], 0
0x1800022a6  mov     dword ptr [r12+0A4h], 1
0x1800022b2  mov     rax, [r14]
0x1800022b5  mov     rax, [rax+0F0h]
0x1800022bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c1  mov     rdx, rax
0x1800022c4  mov     rcx, [rax]
0x1800022c7  mov     rax, [rcx+38h]
0x1800022cb  mov     rcx, rdx
0x1800022ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022d3  mov     r8, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x1800022da  mov     r9, rax
0x1800022dd  mov     rdx, r12
0x1800022e0  mov     rcx, [rax]
0x1800022e3  mov     rax, [rcx+8]
0x1800022e7  mov     rcx, r9
0x1800022ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ef  mov     edi, eax
0x1800022f1  test    eax, eax
0x1800022f3  js      loc_1800054E5
0x1800022f9  mov     eax, [rbp+380h+var_3E0]
0x1800022fc  lea     rdx, ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes
0x180002303  lea     rcx, [r12+20h]
0x180002308  mov     rdx, [rdx+rax*8]
0x18000230c  mov     [r12+8], rdx
0x180002311  mov     rax, [rdx+0C0h]
0x180002318  mov     edx, [rdx+0E8h]
0x18000231e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002323  mov     edi, eax
0x180002325  test    eax, eax
0x180002327  js      loc_180001FC8
0x18000232d  mov     rax, [r15]
0x180002330  xor     r8d, r8d
0x180002333  mov     edx, ebx
0x180002335  mov     rcx, r15
0x180002338  mov     rax, [rax+40h]
0x18000233c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002341  test    rax, rax
0x180002344  jnz     loc_1800054FA
0x18000234a  mov     rsi, qword ptr [rbp+380h+var_250]
0x180002351  xor     eax, eax
0x180002353  mov     qword ptr [rsi+0F0h], 0
0x18000235e  mov     [rsi+0E8h], ax
0x180002365  mov     [rsi+0A0h], rax
0x18000236c  mov     [rsi+98h], ax
0x180002373  mov     rcx, [r12+8]
0x180002378  add     rcx, 38h ; '8'
0x18000237c  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180002382  mov     [rsi+110h], rax
0x180002389  mov     rcx, [r12+8]
0x18000238e  add     rcx, 38h ; '8'
0x180002392  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180002398  mov     [rsi+108h], ax
0x18000239f  mov     rcx, r14
0x1800023a2  mov     rax, [r14]
0x1800023a5  mov     rax, [rax+20h]
0x1800023a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ae  mov     rdi, rax
0x1800023b1  mov     rcx, [rax]
0x1800023b4  mov     rax, [rcx+8]
0x1800023b8  mov     rcx, rdi
0x1800023bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c0  movups  xmm0, xmmword ptr cs:aAcceptEncoding; "Accept-Encoding"
0x1800023c7  movups  [rbp+380h+var_250], xmm0
0x1800023ce  cmp     word ptr [rax+1F8h], 1
0x1800023d6  jz      loc_180005520
0x1800023dc  mov     rax, [rdi]
0x1800023df  lea     r8, [rbp+380h+var_250]
0x1800023e6  mov     r9d, 0Fh
0x1800023ec  mov     [rsp+480h+var_460], 0
0x1800023f4  mov     edx, 1Ch
0x1800023f9  mov     rcx, rdi
0x1800023fc  mov     rax, [rax+20h]
0x180002400  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
