# CFontCollectionBuilder::_MakeFacePidlFromFmsId(uint,ushort const *,_ITEMIDLIST * *)

- ea: `0x18000f6b8`
- end: `0x18000fc37`
- name: `?_MakeFacePidlFromFmsId@CFontCollectionBuilder@@AEAAJIPEBGPEAPEFAU_ITEMIDLIST@@@Z`
- size: `1407`
- prototype: `__int64 __fastcall(CFontCollectionBuilder *__hidden this, unsigned int, const unsigned __int16 *, struct _ITEMIDLIST **)`
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000db98`
- `0x18000f548`

## callees

- `0x180006668`
- `0x180008aec`
- `0x180008fe0`
- `0x180009064`
- `0x18000abd8`
- `0x18000ae20`
- `0x18000d7f4`
- `0x18000d9c8`
- `0x18000e920`
- `0x18000ebbc`
- `0x18000ebf8`
- `0x18000ec84`
- `0x18000ed04`
- `0x18000f198`
- `0x18000f518`
- `0x18000f6b8`
- `0x1800217ac`
- `0x180021834`
- `0x18002186c`
- `0x180021954`
- `0x180021bc0`
- `0x18002a5d4`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000fa83`
- `SHLWAPI!PathFindFileNameW` at `0x18000fa83`
- `fms!FmsGetFontProperty` at `0x18000f80d`
- `fms!FmsGetFontProperty` at `0x18000f906`
- `fms!FmsGetFontProperty` at `0x18000f938`
- `fms!FmsGetFontProperty` at `0x18000f9f8`
- `fms!FmsGetFontProperty` at `0x18000fac4`
- `fms!FmsGetFontProperty` at `0x18000fb27`
- `fms!FmsGetFontProperty` at `0x18000f80d`
- `fms!FmsGetFontProperty` at `0x18000f906`
- `fms!FmsGetFontProperty` at `0x18000f938`
- `fms!FmsGetFontProperty` at `0x18000f9f8`
- `fms!FmsGetFontProperty` at `0x18000fac4`
- `fms!FmsGetFontProperty` at `0x18000fb27`

## string_xrefs

- `0x18000f6eb`: `_MakeFacePidlFromFmsId`
- `0x18000f719`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000f875`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000f8cd`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000fad7`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000fb69`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000fbe5`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::_MakeFacePidlFromFmsId(
        CFontCollectionBuilder *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _ITEMIDLIST **a4)
{
  CFontIdListBuilder *v8; // rdi
  __int64 v9; // rcx
  int FontProperty; // eax
  unsigned int v11; // r8d
  int v12; // ebx
  __int64 v13; // rdx
  CFontCollectionBuilder *v14; // rcx
  int inited; // eax
  unsigned __int64 FontSize; // rax
  const struct _tagpropertykey *v17; // rdx
  __int64 v18; // rcx
  const unsigned __int16 *FileNameW; // rax
  __int64 v20; // rcx
  int v21; // eax
  CFontCollectionBuilder *v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  int IdList; // eax
  unsigned int v28; // edx
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  unsigned int v34; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v35; // [rsp+48h] [rbp-B8h] BYREF
  int v36; // [rsp+50h] [rbp-B0h]
  int v37; // [rsp+54h] [rbp-ACh] BYREF
  int v38; // [rsp+58h] [rbp-A8h] BYREF
  int v39; // [rsp+5Ch] [rbp-A4h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  int v43[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v44[42]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v45[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v46[128]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v48[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v49[384]; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v50[768]; // [rsp+980h] [rbp+880h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CD8h] [rbp+BD8h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v44,
    "_MakeFacePidlFromFmsId");
  v44[0] = &FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::`vftable';
  FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::StartActivity((FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId *)v44);
  if ( !*(_QWORD *)this )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80004003LL,
      v30);
  if ( !a3 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80070057LL,
      v30);
  if ( !a4 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80070057LL,
      v30);
  memset_0(pszPath, 0, 0x208u);
  memset_0(v48, 0, 0x208u);
  v8 = 0;
  v35 = 0;
  memset_0(v50, 0, sizeof(v50));
  v38 = 768;
  memset_0(v46, 0, sizeof(v46));
  v39 = 128;
  memset_0(v49, 0, sizeof(v49));
  v9 = *(_QWORD *)this;
  v31 = v49;
  v37 = 768;
  FontProperty = FmsGetFontProperty(v9, a2, 4, &v37);
  v12 = FontProperty;
  if ( FontProperty >= 0 )
  {
    FontProperty = CFontCollectionBuilder::_GetFilePathsFromFmsId(this, a2, v11, pszPath, (unsigned int)v49, v48);
    v12 = FontProperty;
    if ( FontProperty >= 0 )
    {
      v34 = 0;
      FontProperty = CFontCollectionBuilder::_GetFontType(this, a2, &v34);
      v12 = FontProperty;
      if ( FontProperty >= 0 )
      {
        inited = CFontCollectionBuilder::_InitPidlBuilderObject(
                   v14,
                   v34,
                   v49,
                   a3,
                   pszPath,
                   v48,
                   (struct CFontIdListBuilder **)&v35);
        v8 = (CFontIdListBuilder *)v35;
        v12 = inited;
        if ( inited >= 0 )
          goto LABEL_16;
        goto LABEL_15;
      }
      v13 = 558;
    }
    else
    {
      v13 = 553;
    }
  }
  else
  {
    v13 = 546;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
    (const char *)(unsigned int)FontProperty,
    (int)v31);
LABEL_15:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x236,
    (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
    (const char *)(unsigned int)v12,
    v32);
  if ( v12 < 0 )
  {
LABEL_36:
    v25 = (unsigned int)v12;
    v26 = 657;
LABEL_40:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)v25,
      v33);
    goto LABEL_41;
  }
LABEL_16:
  if ( (int)FmsGetFontProperty(*(_QWORD *)this, a2, 5, &v38) >= 0 )
    *((_QWORD *)v8 + 5) = v50;
  if ( (int)FmsGetFontProperty(*(_QWORD *)this, a2, 38, &v39) >= 0 )
    *((_QWORD *)v8 + 7) = v46;
  v35 = 0;
  if ( CFontCollectionBuilder::_GetFmsDateModifiedWithFallBack(this, a2, pszPath, &v35) >= 0 )
    CFontIdListBuilder::AddFileTimeProperty(v8, &PKEY_DateModified, &v35);
  if ( (int)CFontCollectionBuilder::_GetFontDateProperty(this, a2, 27, &v35) >= 0 )
    CFontIdListBuilder::AddFileTimeProperty(v8, &PKEY_DateCreated, &v35);
  FontSize = CFontCollectionBuilder::_GetFontSize(this, pszPath, v48);
  CFontIdListBuilder::AddIntProperty(v8, v17, FontSize);
  v18 = *(_QWORD *)this;
  v36 = 0;
  v40 = 4;
  if ( (int)FmsGetFontProperty(v18, a2, 26, &v40) >= 0 )
    CFontIdListBuilder::SetActivationStatus(v8, v36 == 0);
  CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(this, a2, 9, PKEY_Fonts_Styles, v8);
  CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(this, a2, 29, PKEY_Fonts_DesignedFor, v8);
  CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(this, a2, 19, PKEY_Fonts_Vendors, v8);
  if ( (unsigned int)IsPathTTC(pszPath) )
  {
    FileNameW = PathFindFileNameW(pszPath);
    CFontIdListBuilder::AddStringProperty(v8, &PKEY_Fonts_CollectionName, FileNameW);
  }
  v20 = *(_QWORD *)this;
  LOWORD(v34) = 0;
  v41 = 2;
  v21 = FmsGetFontProperty(v20, a2, 35, &v41);
  v12 = v21;
  if ( v21 >= 0 )
    CFontCollectionBuilder::_AddEmbeddingRightsToPidlBuilder(v22, v34, v8);
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x27B,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)(unsigned int)v21,
      (int)&v34);
  v23 = *(_QWORD *)this;
  v42 = 8;
  *(_QWORD *)v43 = 0;
  if ( (int)FmsGetFontProperty(v23, a2, 25, &v42) >= 0 )
  {
    *(_OWORD *)v45 = 0;
    v24 = StringCchPrintfW(v45, 8u, L"%.2f", *(_QWORD *)v43);
    v12 = v24;
    if ( v24 >= 0 )
      CFontIdListBuilder::AddStringProperty(v8, &PKEY_Fonts_Version, v45);
    else
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x287,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)v24,
        (int)v43);
  }
  CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(this, a2, 20, PKEY_Fonts_Category, v8);
  if ( v12 < 0 )
    goto LABEL_36;
  if ( !v8 )
    goto LABEL_43;
  IdList = CFontIdListBuilder::MakeIdList(v8, a4);
  v12 = IdList;
  if ( IdList < 0 )
  {
    v25 = (unsigned int)IdList;
    v26 = 660;
    goto LABEL_40;
  }
LABEL_41:
  if ( v8 )
    CFontIdListBuilder::`scalar deleting destructor'(v8, v28);
LABEL_43:
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44, (unsigned int)v12);
  FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::~_MakeFacePidlFromFmsId((FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId *)v44);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000f6b8  push    rbp
0x18000f6ba  push    rbx
0x18000f6bb  push    rsi
0x18000f6bc  push    rdi
0x18000f6bd  push    r12
0x18000f6bf  push    r13
0x18000f6c1  push    r14
0x18000f6c3  push    r15
0x18000f6c5  lea     rbp, [rsp-0B98h]
0x18000f6cd  sub     rsp, 0C98h
0x18000f6d4  mov     rax, cs:__security_cookie
0x18000f6db  xor     rax, rsp
0x18000f6de  mov     [rbp+0BD0h+var_50], rax
0x18000f6e5  mov     r14d, edx
0x18000f6e8  mov     rsi, rcx
0x18000f6eb  lea     rdx, aMakefacepidlfr; "_MakeFacePidlFromFmsId"
0x18000f6f2  mov     r12, r9
0x18000f6f5  lea     rcx, [rbp+0BD0h+var_C50]
0x18000f6f9  mov     r15, r8
0x18000f6fc  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f701  lea     rax, ??_7_MakeFacePidlFromFmsId@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::`vftable'
0x18000f708  lea     rcx, [rbp+0BD0h+var_C50]; this
0x18000f70c  mov     [rbp+0BD0h+var_C50], rax
0x18000f710  call    ?StartActivity@_MakeFacePidlFromFmsId@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_MakeFacePidlFromFmsId::StartActivity(void)
0x18000f715  cmp     qword ptr [rsi], 0
0x18000f719  lea     rbx, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000f720  jnz     short loc_18000F73C
0x18000f722  mov     rcx, [rbp+0BD8h]; this
0x18000f729  mov     r9d, 80004003h; char *
0x18000f72f  mov     r8, rbx; unsigned int
0x18000f732  mov     edx, 206h; void *
0x18000f737  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f73c  mov     edi, 80070057h
0x18000f741  test    r15, r15
0x18000f744  jnz     short loc_18000F75D
0x18000f746  mov     rcx, [rbp+0BD8h]; this
0x18000f74d  mov     r9d, edi; char *
0x18000f750  mov     r8, rbx; unsigned int
0x18000f753  mov     edx, 207h; void *
0x18000f758  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f75d  mov     r13d, 208h
0x18000f763  test    r12, r12
0x18000f766  jnz     short loc_18000F77D
0x18000f768  mov     rcx, [rbp+0BD8h]; this
0x18000f76f  mov     r9d, edi; char *
0x18000f772  mov     r8, rbx; unsigned int
0x18000f775  mov     edx, r13d; void *
0x18000f778  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f77d  mov     r8, r13; Size
0x18000f780  lea     rcx, [rbp+0BD0h+pszPath]; void *
0x18000f787  xor     edx, edx; Val
0x18000f789  call    memset_0
0x18000f78e  mov     r8, r13; Size
0x18000f791  lea     rcx, [rbp+0BD0h+var_860]; void *
0x18000f798  xor     edx, edx; Val
0x18000f79a  call    memset_0
0x18000f79f  mov     r13d, 300h
0x18000f7a5  lea     rcx, [rbp+0BD0h+var_350]; void *
0x18000f7ac  xor     edi, edi
0x18000f7ae  mov     r8d, r13d; Size
0x18000f7b1  xor     edx, edx; Val
0x18000f7b3  mov     qword ptr [rsp+0CD0h+var_C88.dwLowDateTime], rdi
0x18000f7b8  call    memset_0
0x18000f7bd  mov     ebx, 80h
0x18000f7c2  mov     [rsp+0CD0h+var_C78], r13d
0x18000f7c7  mov     r8d, ebx; Size
0x18000f7ca  lea     rcx, [rbp+0BD0h+var_AF0]; void *
0x18000f7d1  xor     edx, edx; Val
0x18000f7d3  call    memset_0
0x18000f7d8  mov     r8d, r13d; Size
0x18000f7db  mov     [rsp+0CD0h+var_C74], ebx
0x18000f7df  xor     edx, edx; Val
0x18000f7e1  lea     rcx, [rbp+0BD0h+var_650]; void *
0x18000f7e8  call    memset_0
0x18000f7ed  mov     rcx, [rsi]
0x18000f7f0  lea     rax, [rbp+0BD0h+var_650]
0x18000f7f7  lea     r9, [rsp+0CD0h+var_C7C]
0x18000f7fc  mov     [rsp+0CD0h+var_CB0], rax; int
0x18000f801  lea     r8d, [rdi+4]
0x18000f805  mov     [rsp+0CD0h+var_C7C], r13d
0x18000f80a  mov     edx, r14d
0x18000f80d  call    cs:__imp_FmsGetFontProperty
0x18000f813  xor     r13d, r13d
0x18000f816  mov     ebx, eax
0x18000f818  test    eax, eax
0x18000f81a  jns     short loc_18000F823
0x18000f81c  mov     edx, 222h
0x18000f821  jmp     short loc_18000F86E
0x18000f823  lea     rax, [rbp+0BD0h+var_860]
0x18000f82a  mov     edx, r14d; unsigned int
0x18000f82d  lea     r9, [rbp+0BD0h+pszPath]; unsigned __int16 *
0x18000f834  mov     [rsp+0CD0h+var_CA8], rax; unsigned __int16 *
0x18000f839  mov     rcx, rsi; this
0x18000f83c  call    ?_GetFilePathsFromFmsId@CFontCollectionBuilder@@AEAAJIIPEAGI0@Z; CFontCollectionBuilder::_GetFilePathsFromFmsId(uint,uint,ushort *,uint,ushort *)
0x18000f841  mov     ebx, eax
0x18000f843  test    eax, eax
0x18000f845  jns     short loc_18000F84E
0x18000f847  mov     edx, 229h
0x18000f84c  jmp     short loc_18000F86E
0x18000f84e  lea     r8, [rsp+0CD0h+var_C90]; unsigned int *
0x18000f853  mov     [rsp+0CD0h+var_C90], r13d
0x18000f858  mov     edx, r14d; unsigned int
0x18000f85b  mov     rcx, rsi; this
0x18000f85e  call    ?_GetFontType@CFontCollectionBuilder@@AEAAJIPEAK@Z; CFontCollectionBuilder::_GetFontType(uint,ulong *)
0x18000f863  mov     ebx, eax
0x18000f865  test    eax, eax
0x18000f867  jns     short loc_18000F886
0x18000f869  mov     edx, 22Eh; void *
0x18000f86e  mov     rcx, [rbp+0BD8h]; this
0x18000f875  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000f87c  mov     r9d, eax; char *
0x18000f87f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f884  jmp     short loc_18000F8C6
0x18000f886  mov     edx, [rsp+0CD0h+var_C90]; unsigned int
0x18000f88a  lea     rax, [rsp+0CD0h+var_C88]
0x18000f88f  mov     [rsp+0CD0h+var_CA0], rax; struct CFontIdListBuilder **
0x18000f894  lea     r8, [rbp+0BD0h+var_650]; unsigned __int16 *
0x18000f89b  lea     rax, [rbp+0BD0h+var_860]
0x18000f8a2  mov     r9, r15; unsigned __int16 *
0x18000f8a5  mov     [rsp+0CD0h+var_CA8], rax; unsigned __int16 *
0x18000f8aa  lea     rax, [rbp+0BD0h+pszPath]
0x18000f8b1  mov     [rsp+0CD0h+var_CB0], rax; int
0x18000f8b6  call    ?_InitPidlBuilderObject@CFontCollectionBuilder@@AEAAJKPEBG000PEAPEAVCFontIdListBuilder@@@Z; CFontCollectionBuilder::_InitPidlBuilderObject(ulong,ushort const *,ushort const *,ushort const *,ushort const *,CFontIdListBuilder * *)
0x18000f8bb  mov     rdi, qword ptr [rsp+0CD0h+var_C88.dwLowDateTime]
0x18000f8c0  mov     ebx, eax
0x18000f8c2  test    eax, eax
0x18000f8c4  jns     short loc_18000F8E9
0x18000f8c6  mov     rcx, [rbp+0BD8h]; this
0x18000f8cd  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000f8d4  mov     r9d, ebx; char *
0x18000f8d7  mov     edx, 236h; void *
0x18000f8dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f8e1  test    ebx, ebx
0x18000f8e3  js      loc_18000FBB6
0x18000f8e9  mov     rcx, [rsi]
0x18000f8ec  lea     rax, [rbp+0BD0h+var_350]
0x18000f8f3  lea     r9, [rsp+0CD0h+var_C78]
0x18000f8f8  mov     [rsp+0CD0h+var_CB0], rax
0x18000f8fd  mov     r8d, 5
0x18000f903  mov     edx, r14d
0x18000f906  call    cs:__imp_FmsGetFontProperty
0x18000f90c  test    eax, eax
0x18000f90e  js      short loc_18000F91B
0x18000f910  lea     rax, [rbp+0BD0h+var_350]
0x18000f917  mov     [rdi+28h], rax
0x18000f91b  mov     rcx, [rsi]
0x18000f91e  lea     rax, [rbp+0BD0h+var_AF0]
0x18000f925  lea     r9, [rsp+0CD0h+var_C74]
0x18000f92a  mov     [rsp+0CD0h+var_CB0], rax
0x18000f92f  mov     r8d, 26h ; '&'
0x18000f935  mov     edx, r14d
0x18000f938  call    cs:__imp_FmsGetFontProperty
0x18000f93e  test    eax, eax
0x18000f940  js      short loc_18000F94D
0x18000f942  lea     rax, [rbp+0BD0h+var_AF0]
0x18000f949  mov     [rdi+38h], rax
0x18000f94d  lea     r9, [rsp+0CD0h+var_C88]; struct _FILETIME *
0x18000f952  mov     qword ptr [rsp+0CD0h+var_C88.dwLowDateTime], r13
0x18000f957  lea     r8, [rbp+0BD0h+pszPath]; unsigned __int16 *
0x18000f95e  mov     edx, r14d; unsigned int
0x18000f961  mov     rcx, rsi; this
0x18000f964  call    ?_GetFmsDateModifiedWithFallBack@CFontCollectionBuilder@@AEAAJIPEBGPEAU_FILETIME@@@Z; CFontCollectionBuilder::_GetFmsDateModifiedWithFallBack(uint,ushort const *,_FILETIME *)
0x18000f969  test    eax, eax
0x18000f96b  js      short loc_18000F981
0x18000f96d  lea     r8, [rsp+0CD0h+var_C88]; struct _FILETIME *
0x18000f972  mov     rcx, rdi; this
0x18000f975  lea     rdx, PKEY_DateModified; struct _tagpropertykey *
0x18000f97c  call    ?AddFileTimeProperty@CFontIdListBuilder@@QEAAJPEBU_tagpropertykey@@PEBU_FILETIME@@@Z; CFontIdListBuilder::AddFileTimeProperty(_tagpropertykey const *,_FILETIME const *)
0x18000f981  lea     r9, [rsp+0CD0h+var_C88]
0x18000f986  mov     r8d, 1Bh
0x18000f98c  mov     edx, r14d
0x18000f98f  mov     rcx, rsi
0x18000f992  call    ?_GetFontDateProperty@CFontCollectionBuilder@@AEAAJIW4_FONT_PROPERTY_TYPE@@PEAU_FILETIME@@@Z; CFontCollectionBuilder::_GetFontDateProperty(uint,_FONT_PROPERTY_TYPE,_FILETIME *)
0x18000f997  test    eax, eax
0x18000f999  js      short loc_18000F9AF
0x18000f99b  lea     r8, [rsp+0CD0h+var_C88]; struct _FILETIME *
0x18000f9a0  mov     rcx, rdi; this
0x18000f9a3  lea     rdx, PKEY_DateCreated; struct _tagpropertykey *
0x18000f9aa  call    ?AddFileTimeProperty@CFontIdListBuilder@@QEAAJPEBU_tagpropertykey@@PEBU_FILETIME@@@Z; CFontIdListBuilder::AddFileTimeProperty(_tagpropertykey const *,_FILETIME const *)
0x18000f9af  lea     r8, [rbp+0BD0h+var_860]; unsigned __int16 *
0x18000f9b6  mov     rcx, rsi; this
0x18000f9b9  lea     rdx, [rbp+0BD0h+pszPath]; unsigned __int16 *
0x18000f9c0  call    ?_GetFontSize@CFontCollectionBuilder@@AEAA_KPEBG0@Z; CFontCollectionBuilder::_GetFontSize(ushort const *,ushort const *)
0x18000f9c5  mov     r8, rax; unsigned __int64
0x18000f9c8  mov     rcx, rdi; this
0x18000f9cb  call    ?AddIntProperty@CFontIdListBuilder@@QEAAJPEBU_tagpropertykey@@_K@Z; CFontIdListBuilder::AddIntProperty(_tagpropertykey const *,unsigned __int64)
0x18000f9d0  mov     rcx, [rsi]
0x18000f9d3  lea     rax, [rsp+0CD0h+var_C80]
0x18000f9d8  lea     r9, [rsp+0CD0h+var_C70]
0x18000f9dd  mov     [rsp+0CD0h+var_CB0], rax
0x18000f9e2  mov     r8d, 1Ah
0x18000f9e8  mov     [rsp+0CD0h+var_C80], r13d
0x18000f9ed  mov     edx, r14d
0x18000f9f0  mov     [rsp+0CD0h+var_C70], 4
0x18000f9f8  call    cs:__imp_FmsGetFontProperty
0x18000f9fe  test    eax, eax
0x18000fa00  js      short loc_18000FA15
0x18000fa02  cmp     [rsp+0CD0h+var_C80], r13d
0x18000fa07  mov     edx, r13d
0x18000fa0a  mov     rcx, rdi; this
0x18000fa0d  setz    dl; unsigned int
0x18000fa10  call    ?SetActivationStatus@CFontIdListBuilder@@QEAAJK@Z; CFontIdListBuilder::SetActivationStatus(ulong)
0x18000fa15  lea     r9, PKEY_Fonts_Styles
0x18000fa1c  mov     [rsp+0CD0h+var_CB0], rdi
0x18000fa21  mov     r8d, 9
0x18000fa27  mov     edx, r14d
0x18000fa2a  mov     rcx, rsi
0x18000fa2d  call    ?_AddSingleFmsStringToPidlBuilder@CFontCollectionBuilder@@AEAAXIW4_FONT_PROPERTY_TYPE@@PEBU_tagpropertykey@@PEAVCFontIdListBuilder@@@Z; CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(uint,_FONT_PROPERTY_TYPE,_tagpropertykey const *,CFontIdListBuilder *)
0x18000fa32  lea     r9, PKEY_Fonts_DesignedFor
0x18000fa39  mov     [rsp+0CD0h+var_CB0], rdi
0x18000fa3e  mov     r8d, 1Dh
0x18000fa44  mov     edx, r14d
0x18000fa47  mov     rcx, rsi
0x18000fa4a  call    ?_AddSingleFmsStringToPidlBuilder@CFontCollectionBuilder@@AEAAXIW4_FONT_PROPERTY_TYPE@@PEBU_tagpropertykey@@PEAVCFontIdListBuilder@@@Z; CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(uint,_FONT_PROPERTY_TYPE,_tagpropertykey const *,CFontIdListBuilder *)
0x18000fa4f  lea     r9, PKEY_Fonts_Vendors
0x18000fa56  mov     [rsp+0CD0h+var_CB0], rdi
0x18000fa5b  mov     r8d, 13h
0x18000fa61  mov     edx, r14d
0x18000fa64  mov     rcx, rsi
0x18000fa67  call    ?_AddSingleFmsStringToPidlBuilder@CFontCollectionBuilder@@AEAAXIW4_FONT_PROPERTY_TYPE@@PEBU_tagpropertykey@@PEAVCFontIdListBuilder@@@Z; CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(uint,_FONT_PROPERTY_TYPE,_tagpropertykey const *,CFontIdListBuilder *)
0x18000fa6c  lea     rcx, [rbp+0BD0h+pszPath]; unsigned __int16 *
0x18000fa73  call    ?IsPathTTC@@YAHPEBG@Z; IsPathTTC(ushort const *)
0x18000fa78  test    eax, eax
0x18000fa7a  jz      short loc_18000FA9B
0x18000fa7c  lea     rcx, [rbp+0BD0h+pszPath]; pszPath
0x18000fa83  call    cs:__imp_PathFindFileNameW
0x18000fa89  lea     rdx, PKEY_Fonts_CollectionName; struct _tagpropertykey *
0x18000fa90  mov     rcx, rdi; this
0x18000fa93  mov     r8, rax; unsigned __int16 *
0x18000fa96  call    ?AddStringProperty@CFontIdListBuilder@@QEAAJPEBU_tagpropertykey@@PEBG@Z; CFontIdListBuilder::AddStringProperty(_tagpropertykey const *,ushort const *)
0x18000fa9b  mov     rcx, [rsi]
0x18000fa9e  lea     rax, [rsp+0CD0h+var_C90]
0x18000faa3  lea     r9, [rsp+0CD0h+var_C6C]
0x18000faa8  mov     [rsp+0CD0h+var_CB0], rax; int
0x18000faad  mov     r8d, 23h ; '#'
0x18000fab3  mov     word ptr [rsp+0CD0h+var_C90], r13w
0x18000fab9  mov     edx, r14d
0x18000fabc  mov     [rsp+0CD0h+var_C6C], 2
0x18000fac4  call    cs:__imp_FmsGetFontProperty
0x18000faca  mov     ebx, eax
0x18000facc  test    eax, eax
0x18000face  jns     short loc_18000FAED
0x18000fad0  mov     rcx, [rbp+0BD8h]; this
0x18000fad7  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000fade  mov     r9d, eax; char *
0x18000fae1  mov     edx, 27Bh; void *
0x18000fae6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000faeb  jmp     short loc_18000FAFA
0x18000faed  movzx   edx, word ptr [rsp+0CD0h+var_C90]; unsigned __int16
0x18000faf2  mov     r8, rdi; struct CFontIdListBuilder *
0x18000faf5  call    ?_AddEmbeddingRightsToPidlBuilder@CFontCollectionBuilder@@AEAAXGPEAVCFontIdListBuilder@@@Z; CFontCollectionBuilder::_AddEmbeddingRightsToPidlBuilder(ushort,CFontIdListBuilder *)
0x18000fafa  mov     rcx, [rsi]
0x18000fafd  lea     rax, [rsp+0CD0h+var_C60]
0x18000fb02  mov     r15d, 8
0x18000fb08  mov     [rsp+0CD0h+var_CB0], rax; int
0x18000fb0d  xorps   xmm0, xmm0
0x18000fb10  mov     [rsp+0CD0h+var_C68], r15d
0x18000fb15  lea     r9, [rsp+0CD0h+var_C68]
0x18000fb1a  movsd   qword ptr [rsp+0CD0h+var_C60], xmm0
0x18000fb20  mov     edx, r14d
0x18000fb23  lea     r8d, [r15+11h]
0x18000fb27  call    cs:__imp_FmsGetFontProperty
0x18000fb2d  test    eax, eax
0x18000fb2f  js      short loc_18000FB95
0x18000fb31  movsd   xmm3, qword ptr [rsp+0CD0h+var_C60]
0x18000fb37  lea     r8, a2f; "%.2f"
0x18000fb3e  xorps   xmm0, xmm0
0x18000fb41  lea     rcx, [rbp+0BD0h+var_B00]; unsigned __int16 *
0x18000fb48  movq    r9, xmm3
0x18000fb4d  mov     edx, r15d; unsigned __int64
0x18000fb50  movups  xmmword ptr [rbp+0BD0h+var_B00], xmm0
0x18000fb57  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fb5c  mov     ebx, eax
0x18000fb5e  test    eax, eax
0x18000fb60  jns     short loc_18000FB7F
0x18000fb62  mov     rcx, [rbp+0BD8h]; this
0x18000fb69  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000fb70  mov     r9d, eax; char *
0x18000fb73  mov     edx, 287h; void *
0x18000fb78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fb7d  jmp     short loc_18000FB95
0x18000fb7f  lea     r8, [rbp+0BD0h+var_B00]; unsigned __int16 *
0x18000fb86  mov     rcx, rdi; this
0x18000fb89  lea     rdx, PKEY_Fonts_Version; struct _tagpropertykey *
0x18000fb90  call    ?AddStringProperty@CFontIdListBuilder@@QEAAJPEBU_tagpropertykey@@PEBG@Z; CFontIdListBuilder::AddStringProperty(_tagpropertykey const *,ushort const *)
0x18000fb95  lea     r9, PKEY_Fonts_Category
0x18000fb9c  mov     [rsp+0CD0h+var_CB0], rdi; int
0x18000fba1  mov     r8d, 14h
0x18000fba7  mov     edx, r14d
0x18000fbaa  mov     rcx, rsi
0x18000fbad  call    ?_AddSingleFmsStringToPidlBuilder@CFontCollectionBuilder@@AEAAXIW4_FONT_PROPERTY_TYPE@@PEBU_tagpropertykey@@PEAVCFontIdListBuilder@@@Z; CFontCollectionBuilder::_AddSingleFmsStringToPidlBuilder(uint,_FONT_PROPERTY_TYPE,_tagpropertykey const *,CFontIdListBuilder *)
0x18000fbb2  test    ebx, ebx
0x18000fbb4  jns     short loc_18000FBC0
0x18000fbb6  mov     r9d, ebx
0x18000fbb9  mov     edx, 291h
0x18000fbbe  jmp     short loc_18000FBDE
0x18000fbc0  test    rdi, rdi
0x18000fbc3  jz      short loc_18000FBFE
0x18000fbc5  mov     rdx, r12; struct _ITEMIDLIST **
0x18000fbc8  mov     rcx, rdi; this
  ... truncated ...
```
