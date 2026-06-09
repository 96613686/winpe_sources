# HTTP_COMPRESSION::DoStaticFileCompression(IHttpContext *,IMapHandlerProvider *,INativeSectionException * *)

- ea: `0x180001310`
- end: `0x180001af1`
- name: `?DoStaticFileCompression@HTTP_COMPRESSION@@SAJPEAVIHttpContext@@PEAVIMapHandlerProvider@@PEAPEAVINativeSectionException@@@Z`
- size: `2017`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IMapHandlerProvider *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800010b0`

## callees

- `0x180001020`
- `0x180001310`
- `0x180001b00`
- `0x180001cd0`
- `0x180001d80`
- `0x180001f80`
- `0x180002090`
- `0x1800027f0`
- `0x1800028a0`
- `0x1800033c0`
- `0x180004be0`
- `0x180005460`
- `0x180005f52`
- `0x180005f90`
- `0x180008568`
- `0x180008624`
- `0x180008710`
- `0x1800087cc`
- `0x180009010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001359`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800015dc`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001359`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800015dc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800014aa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001654`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000165f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001a3d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800065b6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800065ca`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800014aa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001654`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000165f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001a3d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800065b6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800065ca`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000162f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800017ab`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000162f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800017ab`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001980`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800066d9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000671d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800067e1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001980`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800066d9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000671d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800067e1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000180e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000180e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000178f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000178f`

## string_xrefs

- `0x18000153a`: `IIS_EnableStaticCompression`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::DoStaticFileCompression(
        struct IHttpContext *a1,
        struct IMapHandlerProvider *a2,
        struct INativeSectionException **a3)
{
  struct IMapHandlerProvider *v4; // r13
  __int64 v6; // rax
  __int64 v7; // r15
  unsigned int v8; // r12d
  __int64 (__fastcall *v9)(struct IHttpContext *); // rax
  int (__fastcall ***v10)(_QWORD, GUID **); // rax
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // edi
  int (__fastcall ***v14)(_QWORD, GUID **); // rax
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rsi
  struct IHttpFileInfo *v19; // r14
  __int64 (__fastcall ***v20)(_QWORD, void *); // rax
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rax
  int v23; // edi
  const char *Str; // rax
  struct IHttpRequest *v25; // rdi
  const char *v26; // rax
  const char *v27; // rsi
  char *v28; // rax
  __int64 v29; // rdx
  unsigned int v30; // esi
  __int64 v31; // r13
  struct COMPRESSION_SCHEME *v32; // r12
  __int64 (__fastcall *v33)(struct IHttpContext *, _QWORD); // rax
  const unsigned __int16 *v34; // rax
  struct IHttpTraceContext *v35; // rax
  int v36; // eax
  __int64 v37; // rdx
  struct IHttpTraceContext *v38; // rax
  _QWORD *v39; // rax
  _QWORD *v40; // rsi
  struct IHttpFileInfo *v41; // rdi
  __int64 v42; // rax
  struct COMPRESSION_SCHEME *v43; // r14
  COMPRESSION_CONTEXT *v44; // rax
  COMPRESSION_CONTEXT *v45; // rsi
  __int64 v46; // rax
  __int64 v47; // rax
  char *v48; // rax
  int v49; // r9d
  void (__fastcall ***v50)(_QWORD); // r15
  struct IHttpTraceContext *v51; // rax
  const struct _GUID *v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rdx
  struct COMPRESSION_SCHEME * near **v57; // rdi
  __int64 v58; // rax
  __int64 v59; // rax
  struct IHttpTraceContext *v60; // rax
  const struct _GUID *v61; // rdx
  struct IHttpTraceContext *v62; // rax
  const struct _GUID *v63; // rdx
  __int64 v64; // rax
  _DWORD *v65; // rax
  struct IHttpTraceContext *v66; // rax
  const struct _GUID *v67; // rdx
  struct IHttpTraceContext *v68; // rax
  const struct _GUID *v69; // rdx
  int *v70; // [rsp+20h] [rbp-E0h]
  int v71; // [rsp+30h] [rbp-D0h] BYREF
  struct IHttpFileInfo *v72; // [rsp+38h] [rbp-C8h] BYREF
  int v73[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v74; // [rsp+48h] [rbp-B8h] BYREF
  GUID *v75; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v76; // [rsp+58h] [rbp-A8h]
  _WORD *v77; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v78; // [rsp+70h] [rbp-90h] BYREF
  struct IMapHandlerProvider *v79; // [rsp+78h] [rbp-88h]
  _BYTE v80[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v81[56]; // [rsp+B8h] [rbp-48h] BYREF
  _DWORD v82[100]; // [rsp+F0h] [rbp-10h] BYREF
  char v83[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v84[256]; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v85[512]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v79 = a2;
  v4 = a2;
  STRA::STRA((STRA *)v81, v85, 0x200u);
  v6 = *(_QWORD *)a1;
  v7 = 0;
  v8 = 6;
  v72 = 0;
  v71 = 6;
  v77 = 0;
  v9 = *(__int64 (__fastcall **)(struct IHttpContext *))(v6 + 272);
  v74 = 0;
  v10 = (int (__fastcall ***)(_QWORD, GUID **))v9(a1);
  v75 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v76 = 0;
  if ( (**v10)(v10, &v75) >= 0 && DWORD2(v76) && DWORD1(v76) >= 4 && ((_DWORD)v76 == 64 || (v76 & 0x40) != 0) )
  {
    v51 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    IISCompressionEvents::STATIC_COMPRESSION_START::RaiseEvent(v51, v52);
  }
  if ( HTTP_COMPRESSION::sm_InitStatus != 5 )
  {
    v13 = 0;
    goto LABEL_8;
  }
  if ( !HTTP_COMPRESSION::sm_fDoStaticCompression )
  {
    v8 = 2;
    v13 = 0;
    goto LABEL_8;
  }
  if ( !HTTP_COMPRESSION::sm_fStaticCompressionIgnoreHitFrequency )
  {
    v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 152LL))(a1);
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) )
    {
      v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 112LL))(v12, 23);
      v8 = 14;
      v13 = 0;
      goto LABEL_8;
    }
  }
  v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
  v18 = (**(__int64 (__fastcall ***)(__int64, void *))v17)(v17, g_pModuleContext);
  if ( !v18 )
  {
    v48 = (char *)operator new(0x60u);
    v50 = (void (__fastcall ***)(_QWORD))v48;
    if ( !v48 )
    {
      v13 = -2147024888;
LABEL_8:
      v14 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      v75 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v76 = 0;
      if ( (**v14)(v14, &v75) >= 0 && DWORD2(v76) && DWORD1(v76) >= 4 && ((_DWORD)v76 == 64 || (v76 & 0x40) != 0) )
      {
        v66 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
        IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::RaiseEvent(v66, v67, v8);
        v68 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
        IISCompressionEvents::STATIC_COMPRESSION_END::RaiseEvent(v68, v69);
      }
      STRA::~STRA((STRA *)v81);
      return (unsigned int)v13;
    }
    *((_DWORD *)v48 + 10) = 0;
    *((_QWORD *)v48 + 4) = v48 + 24;
    *(_QWORD *)v48 = &COMPRESS_META_STORED_CONTEXT::`vftable';
    *((_QWORD *)v48 + 3) = v48 + 24;
    *((_QWORD *)v48 + 9) = &MIME_MAP::`vftable';
    *((_DWORD *)v48 + 16) = 0;
    *((_QWORD *)v48 + 7) = v48 + 48;
    *((_QWORD *)v48 + 6) = v48 + 48;
    *((_QWORD *)v48 + 11) = 0;
    v13 = COMPRESS_META_STORED_CONTEXT::Initialize((COMPRESS_META_STORED_CONTEXT *)v48, a1, a3, v49);
    if ( v13 < 0 )
    {
      (**v50)(v50);
      goto LABEL_8;
    }
    v18 = (__int64)v50;
    v13 = (*(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD), void *))(*(_QWORD *)v17 + 8LL))(
            v17,
            v50,
            g_pModuleContext);
    if ( v13 < 0 && (v18 = 0, (**v50)(v50), v13 == -2147024811) )
    {
      v7 = 0;
      v18 = (**(__int64 (__fastcall ***)(__int64, void *))v17)(v17, g_pModuleContext);
      v13 = 0;
    }
    else
    {
      v7 = 0;
    }
    if ( v13 < 0 )
      goto LABEL_8;
  }
  if ( (*(int (__fastcall **)(struct IHttpContext *, const char *, _WORD **, int *))(*(_QWORD *)a1 + 128LL))(
         a1,
         "IIS_EnableStaticCompression",
         &v77,
         &v74) >= 0 )
  {
    if ( *v77 == 48 && !v77[1] )
    {
      v8 = 2;
      v13 = 0;
      goto LABEL_8;
    }
  }
  else if ( !*(_DWORD *)(v18 + 8) )
  {
    v8 = 2;
    v13 = 0;
    goto LABEL_8;
  }
  if ( *(_DWORD *)(v18 + 16) )
  {
    v8 = 13;
    v13 = 0;
    goto LABEL_8;
  }
  v19 = (struct IHttpFileInfo *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 208LL))(a1);
  if ( !(*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v19 + 152LL))(v19)
    || (v20 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v19 + 152LL))(v19),
        (v7 = (**v20)(v20, g_pModuleContext)) == 0) )
  {
    STRA::STRA((STRA *)v80, v83, 0x40u);
    v21 = *(_QWORD *)a1;
    v73[0] = 0;
    v22 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(v21 + 184))(a1, 0);
    v13 = MIME_MAP_TABLE::SelectMimeMappingForFileExt(*(MIME_MAP_TABLE **)(v18 + 88), v22, (struct STRA *)v80, v73, v70);
    if ( v13 < 0 )
    {
      STRA::~STRA((STRA *)v80);
      goto LABEL_8;
    }
    if ( !v73[0]
      || (v23 = *(_DWORD *)(v18 + 40),
          Str = STRA::QueryStr((STRA *)v80),
          !(unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsContentTypeAllowed(Str, (struct _LIST_ENTRY *)(v18 + 24), v23)) )
    {
      v13 = 0;
      v8 = 12;
      STRA::~STRA((STRA *)v80);
      goto LABEL_8;
    }
    STRA::~STRA((STRA *)v80);
  }
  v25 = (struct IHttpRequest *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v26 = (const char *)(*(__int64 (__fastcall **)(struct IHttpRequest *, __int64, _QWORD))(*(_QWORD *)v25 + 16LL))(
                        v25,
                        22,
                        0);
  v27 = v26;
  if ( !v26 || !*v26 )
  {
    v64 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    v65 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
    *v65 |= 1u;
    v13 = 0;
    goto LABEL_8;
  }
  if ( HTTP_COMPRESSION::sm_fNoCompressionForHttp10
    && (!*(_WORD *)((*(__int64 (__fastcall **)(struct IHttpRequest *))(*(_QWORD *)v25 + 8LL))(v25) + 32)
     || *(_WORD *)((*(__int64 (__fastcall **)(struct IHttpRequest *))(*(_QWORD *)v25 + 8LL))(v25) + 32) == 1
     && !*(_WORD *)((*(__int64 (__fastcall **)(struct IHttpRequest *))(*(_QWORD *)v25 + 8LL))(v25) + 34)) )
  {
    v53 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 112LL))(v53, 3);
    v13 = 0;
    v8 = 3;
    goto LABEL_8;
  }
  if ( HTTP_COMPRESSION::sm_fNoCompressionForProxies && (unsigned int)IsProxyRequest(v25) )
  {
    v54 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 112LL))(v54, 3);
    v13 = 0;
    v8 = 4;
    goto LABEL_8;
  }
  if ( HTTP_COMPRESSION::sm_fNoCompressionForRange
    && (*(__int64 (__fastcall **)(struct IHttpRequest *, __int64, _QWORD))(*(_QWORD *)v25 + 16LL))(v25, 37, 0) )
  {
    v13 = 0;
    v8 = 7;
    goto LABEL_8;
  }
  v78 = 0;
  (*(void (__fastcall **)(struct IHttpFileInfo *, unsigned __int64 *))(*(_QWORD *)v19 + 64LL))(v19, &v78);
  if ( v78 < HTTP_COMPRESSION::sm_dwMinFileSizeForCompression )
  {
    v13 = 0;
    v8 = 8;
    goto LABEL_8;
  }
  if ( ((*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v19 + 56LL))(v19) & 0x4000) != 0 )
  {
    v13 = 0;
    v8 = 9;
    goto LABEL_8;
  }
  v13 = STRA::Copy((STRA *)v81, v27);
  if ( v13 < 0 )
    goto LABEL_8;
  v73[0] = 0;
  v28 = STRA::QueryStr((STRA *)v81);
  HTTP_COMPRESSION::FindMatchingSchemes(v28, v29, v82, v73);
  v30 = v73[0];
  if ( !v73[0] )
  {
    v55 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 112LL))(v55, 3);
    v13 = 0;
    v8 = 5;
    goto LABEL_8;
  }
  if ( v7 )
  {
    v56 = 0;
    while ( 1 )
    {
      v57 = &(&HTTP_COMPRESSION::sm_pCompressionSchemes)[v82[v56]];
      if ( *v57 == *(struct COMPRESSION_SCHEME * near **)(v7 + 8) )
        break;
      v56 = (unsigned int)(v56 + 1);
      if ( (unsigned int)v56 >= v73[0] )
        goto LABEL_38;
    }
    v72 = *(struct IHttpFileInfo **)(v7 + 16);
    (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v72 + 8LL))(v72);
    v43 = (struct COMPRESSION_SCHEME *)*v57;
  }
  else
  {
LABEL_38:
    v31 = 0;
    while ( 1 )
    {
      memset_0(v84, 0, sizeof(v84));
      STRU::STRU((STRU *)v80, v84, 0x100u);
      v33 = *(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a1 + 184LL);
      *(_QWORD *)v73 = (&HTTP_COMPRESSION::sm_pCompressionSchemes)[v82[v31]];
      v32 = *(struct COMPRESSION_SCHEME **)v73;
      v34 = (const unsigned __int16 *)v33(a1, 0);
      v13 = HTTP_COMPRESSION::ConvertPhysicalPathToCompressedPath(v32, v34, (struct STRU *)v80);
      if ( v13 < 0 )
      {
        STRU::~STRU((STRU *)v80);
        v8 = v71;
        goto LABEL_8;
      }
      v35 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      if ( (unsigned int)HTTP_COMPRESSION::CheckForExistenceOfCompressedFile(
                           v19,
                           (struct STRU *)v80,
                           &v72,
                           (enum IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::enumReason *)&v71,
                           v35) )
        break;
      if ( !HTTP_COMPRESSION::sm_fStaticCompressionDisabledDueToHighCpu )
      {
        v36 = HTTP_COMPRESSION::CompressFile(v32, v19);
        v37 = *(_QWORD *)a1;
        if ( v36 < 0 )
        {
          v58 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v37 + 32))(a1);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 112LL))(v58, 3);
          v8 = 15;
          STRU::~STRU((STRU *)v80);
          goto LABEL_8;
        }
        v38 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v37 + 272))(a1);
        if ( (unsigned int)HTTP_COMPRESSION::CheckForExistenceOfCompressedFile(
                             v19,
                             (struct STRU *)v80,
                             &v72,
                             (enum IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::enumReason *)&v71,
                             v38) )
          break;
      }
      STRU::~STRU((STRU *)v80);
      v31 = (unsigned int)(v31 + 1);
      if ( (unsigned int)v31 >= v30 )
      {
        v8 = v71;
        v59 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v59 + 112LL))(v59, 3);
        v13 = 0;
        goto LABEL_8;
      }
    }
    if ( !v7 )
    {
      if ( (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v19 + 152LL))(v19) )
      {
        if ( (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v72 + 72LL))(v72) )
        {
          v39 = operator new(0x18u);
          v40 = v39;
          if ( v39 )
          {
            v41 = v72;
            *v39 = &COMP_FILE_CONTEXT::`vftable';
            v39[1] = v32;
            (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v41 + 8LL))(v41);
            v40[2] = v41;
            v42 = (*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v19 + 152LL))(v19);
            if ( (*(int (__fastcall **)(__int64, _QWORD *, void *))(*(_QWORD *)v42 + 8LL))(v42, v40, g_pModuleContext) < 0 )
              (*(void (__fastcall **)(_QWORD *))*v40)(v40);
          }
        }
      }
    }
    STRU::~STRU((STRU *)v80);
    v8 = v71;
    v43 = *(struct COMPRESSION_SCHEME **)v73;
    v4 = v79;
  }
  v44 = (COMPRESSION_CONTEXT *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a1 + 144LL))(
                                 a1,
                                 168);
  if ( !v44 || (v45 = COMPRESSION_CONTEXT::COMPRESSION_CONTEXT(v44)) == 0 )
  {
    v13 = -2147024888;
    goto LABEL_95;
  }
  v46 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 56LL))(a1);
  v13 = (*(__int64 (__fastcall **)(__int64, COMPRESSION_CONTEXT *, void *))(*(_QWORD *)v46 + 8LL))(
          v46,
          v45,
          g_pModuleContext);
  if ( v13 < 0 )
  {
    (**(void (__fastcall ***)(COMPRESSION_CONTEXT *))v45)(v45);
LABEL_95:
    (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
    goto LABEL_8;
  }
  *((_QWORD *)v45 + 1) = v43;
  (*(void (__fastcall **)(struct IMapHandlerProvider *, struct IHttpFileInfo *))(*(_QWORD *)v4 + 24LL))(v4, v72);
  v47 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v47) )
  {
    v60 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    IISCompressionEvents::STATIC_COMPRESSION_SUCCESS::RaiseEvent(v60, v61);
    v62 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    IISCompressionEvents::STATIC_COMPRESSION_END::RaiseEvent(v62, v63);
  }
  STRA::~STRA((STRA *)v81);
  return 0;
}

```

## disassembly

```asm
0x180001310  push    rbp
0x180001312  push    rbx
0x180001313  push    rdi
0x180001314  push    r12
0x180001316  push    r13
0x180001318  push    r15
0x18000131a  lea     rbp, [rsp-5D8h]
0x180001322  sub     rsp, 6D8h
0x180001329  mov     rax, cs:__security_cookie
0x180001330  xor     rax, rsp
0x180001333  mov     [rbp+600h+var_40], rax
0x18000133a  mov     rdi, r8
0x18000133d  mov     [rsp+700h+var_688], rdx
0x180001342  mov     r13, rdx
0x180001345  mov     rbx, rcx
0x180001348  mov     r8d, 200h
0x18000134e  lea     rdx, [rbp+600h+var_240]
0x180001355  lea     rcx, [rbp+600h+var_648]
0x180001359  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000135f  mov     rax, [rbx]
0x180001362  xor     r15d, r15d
0x180001365  mov     r12d, 6
0x18000136b  mov     [rsp+700h+var_6C8], r15
0x180001370  mov     rcx, rbx
0x180001373  mov     [rsp+700h+var_6D0], r12d
0x180001378  mov     [rsp+700h+var_698], r15
0x18000137d  mov     rax, [rax+110h]
0x180001384  mov     [rsp+700h+var_6B8], r15d
0x180001389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000138e  mov     r8, rax
0x180001391  lea     rdx, [rsp+700h+var_6B0]
0x180001396  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000139d  xorps   xmm0, xmm0
0x1800013a0  mov     [rsp+700h+var_6B0], rax
0x1800013a5  movdqu  [rsp+700h+var_6A8], xmm0
0x1800013ab  mov     rcx, [r8]
0x1800013ae  mov     rax, [rcx]
0x1800013b1  mov     rcx, r8
0x1800013b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013b9  test    eax, eax
0x1800013bb  js      short loc_1800013C8
0x1800013bd  cmp     dword ptr [rsp+700h+var_6A8+8], r15d
0x1800013c2  jnz     loc_1800064CC
0x1800013c8  cmp     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 5; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x1800013cf  mov     [rsp+700h+arg_18], rsi
0x1800013d7  mov     [rsp+700h+var_30], r14
0x1800013df  jnz     loc_180006509
0x1800013e5  cmp     cs:?sm_fDoStaticCompression@HTTP_COMPRESSION@@2HA, r15d; int HTTP_COMPRESSION::sm_fDoStaticCompression
0x1800013ec  jz      loc_180006511
0x1800013f2  cmp     cs:?sm_fStaticCompressionIgnoreHitFrequency@HTTP_COMPRESSION@@0HA, r15d; int HTTP_COMPRESSION::sm_fStaticCompressionIgnoreHitFrequency
0x1800013f9  jnz     loc_1800014E2
0x1800013ff  mov     rax, [rbx]
0x180001402  mov     rcx, rbx
0x180001405  mov     rax, [rax+98h]
0x18000140c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001411  mov     rdx, rax
0x180001414  mov     rcx, [rax]
0x180001417  mov     rax, [rcx+8]
0x18000141b  mov     rcx, rdx
0x18000141e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001423  test    eax, eax
0x180001425  jnz     loc_1800014E2
0x18000142b  mov     rax, [rbx]
0x18000142e  mov     rcx, rbx
0x180001431  mov     rax, [rax+20h]
0x180001435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000143a  mov     r8, rax
0x18000143d  mov     edx, 17h
0x180001442  mov     rcx, [rax]
0x180001445  mov     rax, [rcx+70h]
0x180001449  mov     rcx, r8
0x18000144c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001451  mov     r12d, 0Eh
0x180001457  mov     edi, r15d
0x18000145a  mov     rax, [rbx]
0x18000145d  mov     rcx, rbx
0x180001460  mov     rax, [rax+110h]
0x180001467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000146c  mov     r8, rax
0x18000146f  lea     rdx, [rsp+700h+var_6B0]
0x180001474  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000147b  xorps   xmm0, xmm0
0x18000147e  mov     [rsp+700h+var_6B0], rax
0x180001483  movdqu  [rsp+700h+var_6A8], xmm0
0x180001489  mov     rcx, [r8]
0x18000148c  mov     rax, [rcx]
0x18000148f  mov     rcx, r8
0x180001492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001497  test    eax, eax
0x180001499  js      short loc_1800014A6
0x18000149b  cmp     dword ptr [rsp+700h+var_6A8+8], 0
0x1800014a0  jnz     loc_180006826
0x1800014a6  lea     rcx, [rbp+600h+var_648]
0x1800014aa  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800014b0  mov     eax, edi
0x1800014b2  mov     r14, [rsp+700h+var_30]
0x1800014ba  mov     rsi, [rsp+700h+arg_18]
0x1800014c2  mov     rcx, [rbp+600h+var_40]
0x1800014c9  xor     rcx, rsp; StackCookie
0x1800014cc  call    __security_check_cookie
0x1800014d1  add     rsp, 6D8h
0x1800014d8  pop     r15
0x1800014da  pop     r13
0x1800014dc  pop     r12
0x1800014de  pop     rdi
0x1800014df  pop     rbx
0x1800014e0  pop     rbp
0x1800014e1  retn
0x1800014e2  mov     rax, [rbx]
0x1800014e5  mov     rcx, rbx
0x1800014e8  mov     rax, [rax+0A0h]
0x1800014ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014f4  mov     rdx, rax
0x1800014f7  mov     rcx, [rax]
0x1800014fa  mov     rax, [rcx+18h]
0x1800014fe  mov     rcx, rdx
0x180001501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001506  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x18000150d  mov     r14, rax
0x180001510  mov     rcx, [rax]
0x180001513  mov     rax, [rcx]
0x180001516  mov     rcx, r14
0x180001519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000151e  mov     rsi, rax
0x180001521  test    rax, rax
0x180001524  jz      loc_180001A4A
0x18000152a  mov     rax, [rbx]
0x18000152d  lea     r9, [rsp+700h+var_6B8]
0x180001532  lea     r8, [rsp+700h+var_698]
0x180001537  mov     rcx, rbx
0x18000153a  lea     rdx, aIisEnablestati; "IIS_EnableStaticCompression"
0x180001541  mov     rax, [rax+80h]
0x180001548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000154d  test    eax, eax
0x18000154f  jns     loc_180006572
0x180001555  cmp     dword ptr [rsi+8], 0
0x180001559  jz      loc_18000659A
0x18000155f  cmp     dword ptr [rsi+10h], 0
0x180001563  jnz     loc_1800065A8
0x180001569  mov     rax, [rbx]
0x18000156c  mov     rcx, rbx
0x18000156f  mov     rax, [rax+0D0h]
0x180001576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000157b  mov     r14, rax
0x18000157e  mov     rcx, [rax]
0x180001581  mov     rax, [rcx+98h]
0x180001588  mov     rcx, r14
0x18000158b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001590  test    rax, rax
0x180001593  jz      short loc_1800015CB
0x180001595  mov     rcx, [r14]
0x180001598  mov     rax, [rcx+98h]
0x18000159f  mov     rcx, r14
0x1800015a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015a7  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x1800015ae  mov     r8, rax
0x1800015b1  mov     rcx, [rax]
0x1800015b4  mov     rax, [rcx]
0x1800015b7  mov     rcx, r8
0x1800015ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015bf  mov     r15, rax
0x1800015c2  test    rax, rax
0x1800015c5  jnz     loc_180001665
0x1800015cb  mov     r8d, 40h ; '@'
0x1800015d1  lea     rdx, [rbp+600h+var_480]
0x1800015d8  lea     rcx, [rbp+600h+var_680]
0x1800015dc  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800015e2  mov     rcx, [rbx]
0x1800015e5  xor     edx, edx
0x1800015e7  mov     [rsp+700h+var_6C0], 0
0x1800015ef  mov     rax, [rcx+0B8h]
0x1800015f6  mov     rcx, rbx
0x1800015f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015fe  mov     rcx, [rsi+58h]; this
0x180001602  lea     r9, [rsp+700h+var_6C0]; int *
0x180001607  lea     r8, [rbp+600h+var_680]; struct STRA *
0x18000160b  mov     rdx, rax; unsigned __int16 *
0x18000160e  call    ?SelectMimeMappingForFileExt@MIME_MAP_TABLE@@QEAAJPEBGPEAVSTRA@@PEAH2@Z; MIME_MAP_TABLE::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)
0x180001613  lea     rcx, [rbp+600h+var_680]
0x180001617  mov     edi, eax
0x180001619  test    eax, eax
0x18000161b  js      loc_1800065B6
0x180001621  cmp     [rsp+700h+var_6C0], 0
0x180001626  jz      loc_1800065C2
0x18000162c  mov     edi, [rsi+28h]
0x18000162f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180001635  lea     rdx, [rsi+18h]; struct _LIST_ENTRY *
0x180001639  mov     r8d, edi; int
0x18000163c  mov     rcx, rax; Str
0x18000163f  call    ?IsContentTypeAllowed@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDPEAU_LIST_ENTRY@@H@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsContentTypeAllowed(char const *,_LIST_ENTRY *,int)
0x180001644  lea     rcx, [rbp+600h+var_680]
0x180001648  test    eax, eax
0x18000164a  jnz     short loc_18000165F
0x18000164c  xor     edi, edi
0x18000164e  mov     r12d, 0Ch
0x180001654  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000165a  jmp     loc_18000145A
0x18000165f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001665  mov     rax, [rbx]
0x180001668  mov     rcx, rbx
0x18000166b  mov     rax, [rax+18h]
0x18000166f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001674  mov     rdi, rax
0x180001677  xor     r8d, r8d
0x18000167a  mov     edx, 16h
0x18000167f  mov     rcx, [rax]
0x180001682  mov     rax, [rcx+10h]
0x180001686  mov     rcx, rdi
0x180001689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000168e  mov     rsi, rax
0x180001691  test    rax, rax
0x180001694  jz      loc_1800067F1
0x18000169a  cmp     byte ptr [rax], 0
0x18000169d  jz      loc_1800067F1
0x1800016a3  cmp     cs:?sm_fNoCompressionForHttp10@HTTP_COMPRESSION@@0HA, 0; int HTTP_COMPRESSION::sm_fNoCompressionForHttp10
0x1800016aa  jz      short loc_1800016F6
0x1800016ac  mov     rcx, [rdi]
0x1800016af  mov     rax, [rcx+8]
0x1800016b3  mov     rcx, rdi
0x1800016b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016bb  cmp     word ptr [rax+20h], 0
0x1800016c0  jz      loc_1800065D6
0x1800016c6  mov     rax, [rdi]
0x1800016c9  mov     rcx, rdi
0x1800016cc  mov     rax, [rax+8]
0x1800016d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d5  cmp     word ptr [rax+20h], 1
0x1800016da  jnz     short loc_1800016F6
0x1800016dc  mov     rax, [rdi]
0x1800016df  mov     rcx, rdi
0x1800016e2  mov     rax, [rax+8]
0x1800016e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016eb  cmp     word ptr [rax+22h], 0
0x1800016f0  jz      loc_1800065D6
0x1800016f6  cmp     cs:?sm_fNoCompressionForProxies@HTTP_COMPRESSION@@0HA, 0; int HTTP_COMPRESSION::sm_fNoCompressionForProxies
0x1800016fd  jz      short loc_18000170F
0x1800016ff  mov     rcx, rdi; struct IHttpRequest *
0x180001702  call    ?IsProxyRequest@@YAHPEAVIHttpRequest@@@Z; IsProxyRequest(IHttpRequest *)
0x180001707  test    eax, eax
0x180001709  jnz     loc_180006609
0x18000170f  cmp     cs:?sm_fNoCompressionForRange@HTTP_COMPRESSION@@0HA, 0; int HTTP_COMPRESSION::sm_fNoCompressionForRange
0x180001716  jz      short loc_180001738
0x180001718  mov     rax, [rdi]
0x18000171b  xor     r8d, r8d
0x18000171e  mov     edx, 25h ; '%'
0x180001723  mov     rcx, rdi
0x180001726  mov     rax, [rax+10h]
0x18000172a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000172f  test    rax, rax
0x180001732  jnz     loc_18000663C
0x180001738  mov     [rsp+700h+var_690], 0
0x180001741  lea     rdx, [rsp+700h+var_690]
0x180001746  mov     rax, [r14]
0x180001749  mov     rcx, r14
0x18000174c  mov     rax, [rax+40h]
0x180001750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001755  mov     eax, cs:?sm_dwMinFileSizeForCompression@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwMinFileSizeForCompression
0x18000175b  cmp     [rsp+700h+var_690], rax
0x180001760  jnb     short loc_18000176F
0x180001762  xor     edi, edi
0x180001764  mov     r12d, 8
0x18000176a  jmp     loc_18000145A
0x18000176f  mov     rax, [r14]
0x180001772  mov     rcx, r14
0x180001775  mov     rax, [rax+38h]
0x180001779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000177e  bt      eax, 0Eh
0x180001782  jb      loc_180006649
0x180001788  mov     rdx, rsi
0x18000178b  lea     rcx, [rbp+600h+var_648]
0x18000178f  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180001795  mov     edi, eax
0x180001797  test    eax, eax
0x180001799  js      loc_18000145A
0x18000179f  lea     rcx, [rbp+600h+var_648]
0x1800017a3  mov     [rsp+700h+var_6C0], 0
0x1800017ab  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800017b1  mov     rcx, rax
0x1800017b4  lea     r9, [rsp+700h+var_6C0]
0x1800017b9  lea     r8, [rbp+600h+var_610]
0x1800017bd  call    ?FindMatchingSchemes@HTTP_COMPRESSION@@CAXPEADW4COMPRESSION_TO_PERFORM@@QEAKPEAK@Z; HTTP_COMPRESSION::FindMatchingSchemes(char *,COMPRESSION_TO_PERFORM,ulong * const,ulong *)
0x1800017c2  mov     esi, [rsp+700h+var_6C0]
0x1800017c6  test    esi, esi
0x1800017c8  jz      loc_180006656
0x1800017ce  lea     rdi, ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes
0x1800017d5  test    r15, r15
0x1800017d8  jnz     loc_180006689
0x1800017de  xor     r13d, r13d
0x1800017e1  test    esi, esi
0x1800017e3  jz      loc_18000672E
0x1800017e9  xor     edx, edx; Val
0x1800017eb  lea     rcx, [rbp+600h+var_440]; void *
0x1800017f2  mov     r8d, 200h; Size
0x1800017f8  call    memset_0
0x1800017fd  mov     r8d, 100h
0x180001803  lea     rdx, [rbp+600h+var_440]
0x18000180a  lea     rcx, [rbp+600h+var_680]
0x18000180e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001814  mov     ecx, [rbp+r13*4+600h+var_610]
0x180001819  xor     edx, edx
  ... truncated ...
```
