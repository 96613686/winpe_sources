# CMFCRibbonInfo::Read(uchar *,uint)

- ea: `0x180110600`
- end: `0x180110cf7`
- name: `?Read@CMFCRibbonInfo@@UEAAHPEAEI@Z`
- size: `1783`
- prototype: `int __fastcall(CMFCRibbonInfo *this, unsigned __int8 *lpBuffer, unsigned int nSize)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x18000ddc0`
- `0x18000df50`
- `0x18000e0e0`
- `0x180102240`
- `0x18010d8a4`
- `0x18010f4b0`
- `0x180110600`
- `0x1802bbce0`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1801106e9`
- `KERNEL32!GlobalAlloc` at `0x1801106e9`
- `KERNEL32!GlobalLock` at `0x180110702`
- `KERNEL32!GlobalLock` at `0x180110702`
- `KERNEL32!GlobalUnlock` at `0x180110723`
- `KERNEL32!GlobalUnlock` at `0x180110723`
- `KERNEL32!GlobalFree` at `0x180110b4a`
- `KERNEL32!GlobalFree` at `0x180110b4a`
- `VCRUNTIME140!memmove` at `0x180110a22`
- `VCRUNTIME140!memmove` at `0x180110a22`
- `VCRUNTIME140!memset` at `0x180110a51`
- `VCRUNTIME140!memset` at `0x180110a51`
- `VCRUNTIME140!memcpy` at `0x18011071a`
- `VCRUNTIME140!memcpy` at `0x180110a47`
- `VCRUNTIME140!memcpy` at `0x18011071a`
- `VCRUNTIME140!memcpy` at `0x180110a47`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180110a63`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180110a63`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180110a02`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180110a57`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180110a02`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180110a57`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18011099e`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18011099e`
- `ole32!CoUninitialize` at `0x180110c7c`
- `ole32!CoUninitialize` at `0x180110c7c`
- `ole32!CreateStreamOnHGlobal` at `0x180110736`
- `ole32!CreateStreamOnHGlobal` at `0x180110736`
- `OLEAUT32!__imp_SysAllocString` at `0x1801108ff`
- `OLEAUT32!__imp_SysAllocString` at `0x180110916`
- `OLEAUT32!__imp_SysAllocString` at `0x1801108ff`
- `OLEAUT32!__imp_SysAllocString` at `0x180110916`
- `OLEAUT32!__imp_SysFreeString` at `0x180110952`
- `OLEAUT32!__imp_SysFreeString` at `0x180110acf`
- `OLEAUT32!__imp_SysFreeString` at `0x180110952`
- `OLEAUT32!__imp_SysFreeString` at `0x180110acf`
- `OLEAUT32!__imp_VariantClear` at `0x1801107e1`
- `OLEAUT32!__imp_VariantClear` at `0x18011095c`
- `OLEAUT32!__imp_VariantClear` at `0x1801107e1`
- `OLEAUT32!__imp_VariantClear` at `0x18011095c`

## string_xrefs

- `0x18011090f`: `XPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CMFCRibbonInfo::Read(CMFCRibbonInfo *this, unsigned __int8 *lpBuffer, unsigned int nSize)
{
  void *m_pszData; // r15
  CMFCRibbonInfo::XInfoError *p_m_Error; // r14
  HRESULT v7; // edi
  HGLOBAL v8; // rax
  void *v9; // r15
  void *v10; // rax
  LPSTREAM v11; // rbx
  IXMLDOMDocument_vtbl *v12; // rax
  wchar_t *v13; // r12
  ATL::CStringData *v14; // r14
  wchar_t *v15; // rbx
  HINSTANCE__ *StringResourceHandle; // rax
  wchar_t *v17; // rbx
  __int64 (__fastcall *v18)(wchar_t *, wchar_t *, VARIANTARG *); // rax
  int v19; // eax
  int v20; // esi
  unsigned __int64 nDataLength; // r13
  unsigned __int64 v22; // r15
  unsigned __int64 v23; // r14
  wchar_t *v24; // rdx
  size_t v25; // r8
  wchar_t *v26; // rdx
  CMFCRibbonInfo::XRibbonInfoParser *v27; // rbx
  ATL::CStringData *v28; // rbx
  unsigned int v29; // edi
  wchar_t *v30; // rdx
  __int64 v32; // [rsp+30h] [rbp-89h] BYREF
  CXMLParserRoot document; // [rsp+38h] [rbp-81h] BYREF
  wchar_t *String; // [rsp+68h] [rbp-51h] BYREF
  LPSTREAM ppstm; // [rsp+70h] [rbp-49h] BYREF
  CMFCRibbonInfo::XInfoError *v36; // [rsp+78h] [rbp-41h]
  VARIANTARG v37; // [rsp+80h] [rbp-39h] BYREF
  HGLOBAL v38; // [rsp+A0h] [rbp-19h]
  VARIANTARG pvarg; // [rsp+A8h] [rbp-11h] BYREF
  VARIANTARG v40; // [rsp+C0h] [rbp+7h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strName; // [rsp+120h] [rbp+67h] BYREF
  CMFCRibbonInfo::XRibbonInfoParser *pParserRoot; // [rsp+128h] [rbp+6Fh] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > v43; // [rsp+138h] [rbp+7Fh] BYREF

  strName.m_pszData = (wchar_t *)this;
  m_pszData = this;
  p_m_Error = &this->m_Error;
  v36 = &this->m_Error;
  this->m_Error.m_Error = e_ErrorFirst;
  this->m_Error.m_nLine = -1;
  this->m_Error.m_nLinePos = -1;
  ATL::CSimpleStringT<wchar_t,1>::Empty(&this->m_Error.m_strDescription);
  if ( !lpBuffer || !nSize )
    return 0;
  document.__vftable = (CXMLParserRoot_vtbl *)CXMLParserRoot::`vftable';
  document.m_document.m_pNode.p = 0;
  document.m_document.__vftable = (ATL::CXMLDocument_vtbl *)ATL::CXMLDocument::`vftable';
  document.m_document.m_strErrorReason.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  ATL::CSimpleStringT<wchar_t,1>::Empty(&document.m_document.m_strErrorReason);
  document.m_document.m_nErrorLine = -1;
  document.m_document.m_nErrorLinePos = -1;
  document.m_document.m_bComInitialized = 0;
  ATL::CSimpleStringT<wchar_t,1>::Empty(&document.m_document.m_strErrorReason);
  document.m_document.m_nErrorLine = -1;
  document.m_document.m_nErrorLinePos = -1;
  v7 = ATL::CXMLDocument::Initialize(&document.m_document);
  if ( !v7 )
  {
    if ( !document.m_document.m_pNode.p )
      goto LABEL_66;
    v7 = -2147467259;
    v8 = GlobalAlloc(0x42u, nSize);
    v9 = v8;
    v38 = v8;
    if ( !v8 )
      goto LABEL_66;
    v10 = GlobalLock(v8);
    if ( !v10 )
      goto LABEL_64;
    memcpy(v10, lpBuffer, nSize);
    GlobalUnlock(v9);
    ppstm = 0;
    if ( CreateStreamOnHGlobal(v9, 0, &ppstm) < 0 )
      goto LABEL_62;
    v11 = ppstm;
    ATL::CSimpleStringT<wchar_t,1>::Empty(&document.m_document.m_strErrorReason);
    document.m_document.m_nErrorLine = -1;
    document.m_document.m_nErrorLinePos = -1;
    if ( !v11 )
    {
      v7 = -2147024809;
      goto LABEL_62;
    }
    v7 = ATL::CXMLDocument::Initialize(&document.m_document);
    if ( v7 )
      goto LABEL_62;
    if ( !document.m_document.m_pNode.p )
    {
LABEL_12:
      v7 = -2147467261;
      goto LABEL_62;
    }
    LOWORD(pParserRoot) = 0;
    pvarg.vt = 13;
    pvarg.llVal = (__int64)v11;
    v11->AddRef(v11);
    v12 = document.m_document.m_pNode.p->__vftable;
    v37 = pvarg;
    v7 = ((__int64 (__fastcall *)(IXMLDOMDocument *, VARIANTARG *, CMFCRibbonInfo::XRibbonInfoParser **))v12->load)(
           document.m_document.m_pNode.p,
           &v37,
           &pParserRoot);
    VariantClear(&pvarg);
    if ( !v7 )
    {
      if ( (_WORD)pParserRoot )
      {
        if ( document.m_document.m_pNode.p )
        {
          v43.m_pszData = 0;
          v7 = document.m_document.m_pNode.p->QueryInterface(
                 document.m_document.m_pNode.p,
                 &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
                 (void **)&v43);
          if ( v7 )
          {
            if ( v43.m_pszData )
              (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v43.m_pszData + 16LL))(v43.m_pszData);
          }
          else
          {
            v17 = SysAllocString(L"SelectionLanguage");
            v37.vt = 8;
            v37.llVal = (__int64)SysAllocString(L"XPath");
            v18 = *(__int64 (__fastcall **)(wchar_t *, wchar_t *, VARIANTARG *))(*(_QWORD *)v43.m_pszData + 640LL);
            v40 = v37;
            v7 = v18(v43.m_pszData, v17, &v40);
            SysFreeString(v17);
            VariantClear(&v37);
            if ( v43.m_pszData )
              (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v43.m_pszData + 16LL))(v43.m_pszData);
          }
          goto LABEL_62;
        }
        goto LABEL_12;
      }
      v7 = 1;
    }
    if ( !document.m_document.m_pNode.p )
    {
LABEL_62:
      if ( ppstm )
        ppstm->Release(ppstm);
LABEL_64:
      GlobalFree(v9);
      m_pszData = strName.m_pszData;
      goto LABEL_65;
    }
    ATL::CSimpleStringT<wchar_t,1>::Empty(&document.m_document.m_strErrorReason);
    document.m_document.m_nErrorLine = -1;
    document.m_document.m_nErrorLinePos = -1;
    v32 = 0;
    if ( document.m_document.m_pNode.p->get_parseError(document.m_document.m_pNode.p, (IXMLDOMParseError **)&v32) )
    {
LABEL_60:
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      goto LABEL_62;
    }
    String = 0;
    if ( (*(int (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v32 + 72LL))(v32, &String) < 0 )
    {
LABEL_54:
      if ( String )
        SysFreeString(String);
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 88LL))(v32, &document.m_document.m_nErrorLine) < 0 )
        document.m_document.m_nErrorLine = 1;
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 96LL))(v32, &document.m_document.m_nErrorLinePos) < 0 )
        document.m_document.m_nErrorLinePos = 1;
      goto LABEL_60;
    }
    v13 = String;
    v14 = afxStringManager.GetNilString(&afxStringManager);
    v15 = (wchar_t *)&v14[1];
    v43.m_pszData = (wchar_t *)&v14[1];
    if ( !v13 )
      goto LABEL_49;
    if ( (unsigned __int64)v13 < 0x10000 )
    {
      StringResourceHandle = AfxFindStringResourceHandle((unsigned __int16)v13);
      if ( StringResourceHandle )
      {
        ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
          &v43,
          StringResourceHandle,
          (unsigned __int16)v13);
LABEL_50:
        v15 = v43.m_pszData;
      }
LABEL_51:
      ATL::CSimpleStringT<wchar_t,1>::operator=(
        &document.m_document.m_strErrorReason,
        (const ATL::CSimpleStringT<wchar_t,0> *)&v43);
      if ( _InterlockedDecrement((volatile signed __int32 *)v15 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
      p_m_Error = v36;
      goto LABEL_54;
    }
    v19 = wcslen(v13);
    v20 = v19;
    if ( !v19 )
    {
LABEL_49:
      ATL::CSimpleStringT<wchar_t,1>::Empty(&v43);
      goto LABEL_50;
    }
    nDataLength = (unsigned int)v14->nDataLength;
    v22 = v13 - v15;
    if ( v19 < 0 )
LABEL_82:
      ATL::AtlThrowImpl(-2147024809);
    if ( ((1 - v14->nRefs) | (v14->nAllocLength - v19)) < 0 )
    {
      ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&v43, v19);
      v15 = v43.m_pszData;
    }
    v23 = 2LL * v20;
    if ( v22 > nDataLength )
    {
      v25 = 2LL * *((int *)v15 - 3);
      if ( !v23 )
        goto LABEL_47;
      if ( v25 >= v23 )
      {
        memcpy(v15, v13, 2LL * v20);
        goto LABEL_47;
      }
      memset(v15, 0, v25);
    }
    else
    {
      v24 = &v15[v22];
      if ( !v23 )
        goto LABEL_47;
      if ( !v24 )
      {
        *_errno() = 22;
LABEL_46:
        _invalid_parameter_noinfo();
LABEL_47:
        if ( v20 <= *((_DWORD *)v15 - 3) )
        {
          *((_DWORD *)v15 - 4) = v20;
          v15[v23 / 2] = 0;
          v9 = v38;
          goto LABEL_51;
        }
        goto LABEL_82;
      }
      if ( 2LL * *((int *)v15 - 3) >= v23 )
      {
        memmove(v15, v24, 2LL * v20);
        goto LABEL_47;
      }
    }
    *_errno() = 34;
    goto LABEL_46;
  }
LABEL_65:
  if ( v7 )
  {
LABEL_66:
    CMFCRibbonInfo::XInfoError::SetError(
      p_m_Error,
      e_ErrorFile,
      &document.m_document.m_strErrorReason,
      document.m_document.m_nErrorLine,
      document.m_document.m_nErrorLinePos);
    goto LABEL_72;
  }
  pParserRoot = 0;
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strName,
    L"AFX_RIBBON");
  CXMLParserRoot::GetRoot(&document, &strName, &pParserRoot);
  v26 = strName.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strName.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26);
  v27 = pParserRoot;
  if ( pParserRoot )
  {
    v29 = (*(__int64 (__fastcall **)(void *, CMFCRibbonInfo::XRibbonInfoParser *))(*(_QWORD *)m_pszData + 8LL))(
            m_pszData,
            pParserRoot);
    ((void (__fastcall *)(CMFCRibbonInfo::XRibbonInfoParser *, __int64))v27->~CMFCRibbonInfo::XRibbonInfoParser)(v27, 1);
    goto LABEL_74;
  }
  v28 = afxStringManager.GetNilString(&afxStringManager);
  strName.m_pszData = (wchar_t *)&v28[1];
  CMFCRibbonInfo::XInfoError::SetError(p_m_Error, e_ErrorInvalidRoot, &strName, -1, -1);
  if ( _InterlockedDecrement(&v28->nRefs) <= 0 )
    v28->pStringMgr->Free(v28->pStringMgr, v28);
LABEL_72:
  v29 = 0;
LABEL_74:
  document.__vftable = (CXMLParserRoot_vtbl *)CXMLParserRoot::`vftable';
  document.m_document.__vftable = (ATL::CXMLDocument_vtbl *)ATL::CXMLDocument::`vftable';
  if ( document.m_document.m_bComInitialized )
    CoUninitialize();
  v30 = document.m_document.m_strErrorReason.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)document.m_document.m_strErrorReason.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30);
  document.m_document.__vftable = (ATL::CXMLDocument_vtbl *)ATL::CXMLNode<IXMLDOMDocument>::`vftable';
  if ( document.m_document.m_pNode.p )
    document.m_document.m_pNode.p->Release(document.m_document.m_pNode.p);
  return v29;
}

```

## disassembly

```asm
0x180110600  mov     [rsp-8+arg_10], rbx
0x180110605  mov     [rsp-8+strName.m_pszData], this
0x18011060a  push    rbp
0x18011060b  push    rsi
0x18011060c  push    rdi
0x18011060d  push    r12
0x18011060f  push    r13
0x180110611  push    r14
0x180110613  push    r15
0x180110615  lea     rbp, [rsp-27h]
0x18011061a  sub     rsp, 0E0h
0x180110621  mov     ebx, nSize
0x180110624  mov     rsi, lpBuffer
0x180110627  mov     r15, this
0x18011062a  lea     r14, [this+4D0h]
0x180110631  mov     [rbp+57h+var_98], r14
0x180110635  xor     r13d, r13d
0x180110638  mov     [r14], r13d
0x18011063b  or      r12d, 0FFFFFFFFh
0x18011063f  mov     [r14+10h], r12d
0x180110643  mov     [r14+14h], r12d
0x180110647  lea     this, [r14+8]; this
0x18011064b  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180110650  test    rsi, rsi
0x180110653  jz      loc_180110CCF
0x180110659  test    ebx, ebx
0x18011065b  jz      loc_180110CCF
0x180110661  lea     rax, ??_7CXMLParserRoot@@6B@; const CXMLParserRoot::`vftable'
0x180110668  mov     [rsp+110h+document.__vftable], rax
0x18011066d  mov     [rbp+57h+document.m_document.m_pNode.p], r13
0x180110671  lea     rax, ??_7CXMLDocument@ATL@@6B@; const ATL::CXMLDocument::`vftable'
0x180110678  mov     [rbp+57h+document.m_document.__vftable], rax
0x18011067c  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x180110683  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18011068a  mov     rax, [rax+18h]
0x18011068e  call    cs:__guard_dispatch_icall_fptr
0x180110694  add     rax, 18h
0x180110698  mov     [rbp+57h+document.m_document.m_strErrorReason.m_pszData], rax
0x18011069c  lea     this, [rbp+57h+document.m_document.m_strErrorReason]; this
0x1801106a0  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x1801106a5  mov     [rbp+57h+document.m_document.m_nErrorLine], r12d
0x1801106a9  mov     [rbp+57h+document.m_document.m_nErrorLinePos], r12d
0x1801106ad  mov     [rbp+57h+document.m_document.m_bComInitialized], r13d
0x1801106b1  lea     this, [rbp+57h+document.m_document.m_strErrorReason]; this
0x1801106b5  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x1801106ba  mov     [rbp+57h+document.m_document.m_nErrorLine], r12d
0x1801106be  mov     [rbp+57h+document.m_document.m_nErrorLinePos], r12d
0x1801106c2  lea     this, [rbp+57h+document.m_document]; this
0x1801106c6  call    ?Initialize@CXMLDocument@ATL@@IEAAJXZ; ATL::CXMLDocument::Initialize(void)
0x1801106cb  mov     edi, eax
0x1801106cd  test    eax, eax
0x1801106cf  jnz     loc_180110B54
0x1801106d5  cmp     [rbp+57h+document.m_document.m_pNode.p], r13
0x1801106d9  jz      loc_180110B58
0x1801106df  mov     edi, 80004005h
0x1801106e4  mov     edx, ebx; dwBytes
0x1801106e6  lea     ecx, [rax+42h]; uFlags
0x1801106e9  call    cs:__imp_GlobalAlloc
0x1801106ef  mov     r15, rax
0x1801106f2  mov     [rbp+57h+var_70], rax
0x1801106f6  test    rax, rax
0x1801106f9  jz      loc_180110B58
0x1801106ff  mov     this, rax; hMem
0x180110702  call    cs:__imp_GlobalLock
0x180110708  test    rax, rax
0x18011070b  jz      loc_180110B47
0x180110711  mov     nSize, ebx; Size
0x180110714  mov     lpBuffer, rsi; Src
0x180110717  mov     this, rax; void *
0x18011071a  call    cs:__imp_memcpy
0x180110720  mov     this, r15; hMem
0x180110723  call    cs:__imp_GlobalUnlock
0x180110729  mov     [rbp+57h+ppstm], r13
0x18011072d  lea     r8, [rbp+57h+ppstm]; ppstm
0x180110731  xor     edx, edx; fDeleteOnRelease
0x180110733  mov     this, r15; hGlobal
0x180110736  call    cs:__imp_CreateStreamOnHGlobal
0x18011073c  test    eax, eax
0x18011073e  js      loc_180110B31
0x180110744  mov     rbx, [rbp+57h+ppstm]
0x180110748  lea     this, [rbp+57h+document.m_document.m_strErrorReason]; this
0x18011074c  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180110751  mov     [rbp+57h+document.m_document.m_nErrorLine], r12d
0x180110755  mov     [rbp+57h+document.m_document.m_nErrorLinePos], r12d
0x180110759  test    rbx, rbx
0x18011075c  jnz     short loc_180110768
0x18011075e  mov     edi, 80070057h
0x180110763  jmp     loc_180110B31
0x180110768  lea     this, [rbp+57h+document.m_document]; this
0x18011076c  call    ?Initialize@CXMLDocument@ATL@@IEAAJXZ; ATL::CXMLDocument::Initialize(void)
0x180110771  mov     edi, eax
0x180110773  test    eax, eax
0x180110775  jnz     loc_180110B31
0x18011077b  cmp     [rbp+57h+document.m_document.m_pNode.p], r13
0x18011077f  jnz     short loc_18011078B
0x180110781  mov     edi, 80004003h
0x180110786  jmp     loc_180110B31
0x18011078b  mov     word ptr [rbp+57h+pParserRoot], r13w
0x180110790  mov     eax, 0Dh
0x180110795  mov     word ptr [rbp+57h+pvarg.___u0], ax
0x180110799  mov     qword ptr [rbp+57h+pvarg.___u0+8], rbx
0x18011079d  mov     rax, [rbx]
0x1801107a0  mov     this, rbx
0x1801107a3  mov     rax, [rax+8]
0x1801107a7  call    cs:__guard_dispatch_icall_fptr
0x1801107ad  mov     this, [rbp+57h+document.m_document.m_pNode.p]
0x1801107b1  mov     rax, [this]
0x1801107b4  movups  xmm0, xmmword ptr [rbp+57h+pvarg.___u0]
0x1801107b8  movaps  xmmword ptr [rbp+57h+var_90.___u0], xmm0
0x1801107bc  movsd   xmm1, [rbp+57h+pvarg.pRecInfo]
0x1801107c1  movsd   [rbp+57h+var_90.pRecInfo], xmm1
0x1801107c6  lea     r8, [rbp+57h+pParserRoot]
0x1801107ca  lea     lpBuffer, [rbp+57h+var_90]
0x1801107ce  mov     rax, [rax+1D0h]
0x1801107d5  call    cs:__guard_dispatch_icall_fptr
0x1801107db  mov     edi, eax
0x1801107dd  lea     this, [rbp+57h+pvarg]; pvarg
0x1801107e1  call    cs:__imp_VariantClear
0x1801107e7  test    edi, edi
0x1801107e9  js      short loc_1801107FD
0x1801107eb  jnz     short loc_1801107FD
0x1801107ed  cmp     word ptr [rbp+57h+pParserRoot], r13w
0x1801107f2  jnz     loc_1801108C6
0x1801107f8  mov     edi, 1
0x1801107fd  cmp     [rbp+57h+document.m_document.m_pNode.p], r13
0x180110801  jz      loc_180110B31
0x180110807  lea     this, [rbp+57h+document.m_document.m_strErrorReason]; this
0x18011080b  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180110810  mov     [rbp+57h+document.m_document.m_nErrorLine], r12d
0x180110814  mov     [rbp+57h+document.m_document.m_nErrorLinePos], r12d
0x180110818  mov     [rsp+110h+var_E0], r13
0x18011081d  mov     this, [rbp+57h+document.m_document.m_pNode.p]
0x180110821  mov     rax, [this]
0x180110824  lea     lpBuffer, [rsp+110h+var_E0]
0x180110829  mov     rax, [rax+1E0h]
0x180110830  call    cs:__guard_dispatch_icall_fptr
0x180110836  test    eax, eax
0x180110838  jnz     loc_180110B19
0x18011083e  mov     [rbp+57h+String], r13
0x180110842  mov     this, [rsp+110h+var_E0]
0x180110847  mov     rax, [this]
0x18011084a  lea     lpBuffer, [rbp+57h+String]
0x18011084e  mov     rax, [rax+48h]
0x180110852  call    cs:__guard_dispatch_icall_fptr
0x180110858  test    eax, eax
0x18011085a  js      loc_180110AC6
0x180110860  mov     r12, [rbp+57h+String]
0x180110864  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18011086b  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x180110872  mov     rax, [rax+18h]
0x180110876  call    cs:__guard_dispatch_icall_fptr
0x18011087c  mov     r14, rax
0x18011087f  lea     rbx, [rax+18h]
0x180110883  mov     [rbp+57h+arg_18.m_pszData], rbx
0x180110887  test    r12, r12
0x18011088a  jz      loc_180110A80
0x180110890  cmp     r12, 10000h
0x180110897  jnb     loc_18011099B
0x18011089d  movzx   esi, r12w
0x1801108a1  mov     ecx, esi; nID
0x1801108a3  call    ?AfxFindStringResourceHandle@@YAPEAUHINSTANCE__@@I@Z; AfxFindStringResourceHandle(uint)
0x1801108a8  nop
0x1801108a9  test    rax, rax
0x1801108ac  jz      loc_180110A8D
0x1801108b2  mov     nSize, esi; nID
0x1801108b5  mov     lpBuffer, rax; hInstance
0x1801108b8  lea     this, [rbp+57h+arg_18]; this
0x1801108bc  call    ?LoadStringW@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x1801108c1  jmp     loc_180110A89
0x1801108c6  mov     this, [rbp+57h+document.m_document.m_pNode.p]
0x1801108ca  test    this, this
0x1801108cd  jz      loc_180110781
0x1801108d3  mov     [rbp+57h+arg_18.m_pszData], r13
0x1801108d7  mov     rax, [this]
0x1801108da  lea     r8, [rbp+57h+arg_18]
0x1801108de  lea     lpBuffer, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x1801108e5  mov     rax, [rax]
0x1801108e8  call    cs:__guard_dispatch_icall_fptr
0x1801108ee  mov     edi, eax
0x1801108f0  test    eax, eax
0x1801108f2  jnz     loc_18011097F
0x1801108f8  lea     this, aSelectionlangu; "SelectionLanguage"
0x1801108ff  call    cs:__imp_SysAllocString
0x180110905  mov     rbx, rax
0x180110908  lea     eax, [rdi+8]
0x18011090b  mov     word ptr [rbp+57h+var_90.___u0], ax
0x18011090f  lea     this, aXpath; "XPath"
0x180110916  call    cs:__imp_SysAllocString
0x18011091c  mov     qword ptr [rbp+57h+var_90.___u0+8], rax
0x180110920  mov     this, [rbp+57h+arg_18.m_pszData]
0x180110924  mov     lpBuffer, [this]
0x180110927  mov     rax, [lpBuffer+280h]
0x18011092e  movups  xmm0, xmmword ptr [rbp+57h+var_90.___u0]
0x180110932  movaps  [rbp+57h+var_50], xmm0
0x180110936  movsd   xmm1, [rbp+57h+var_90.pRecInfo]
0x18011093b  movsd   [rbp+57h+var_40], xmm1
0x180110940  lea     r8, [rbp+57h+var_50]
0x180110944  mov     lpBuffer, rbx
0x180110947  call    cs:__guard_dispatch_icall_fptr
0x18011094d  mov     edi, eax
0x18011094f  mov     this, rbx; bstrString
0x180110952  call    cs:__imp_SysFreeString
0x180110958  lea     this, [rbp+57h+var_90]; pvarg
0x18011095c  call    cs:__imp_VariantClear
0x180110962  nop
0x180110963  mov     this, [rbp+57h+arg_18.m_pszData]
0x180110967  test    this, this
0x18011096a  jz      short loc_18011097A
0x18011096c  mov     rax, [this]
0x18011096f  mov     rax, [rax+10h]
0x180110973  call    cs:__guard_dispatch_icall_fptr
0x180110979  nop
0x18011097a  jmp     loc_180110B31
0x18011097f  mov     this, [rbp+57h+arg_18.m_pszData]
0x180110983  test    this, this
0x180110986  jz      short loc_180110996
0x180110988  mov     rax, [this]
0x18011098b  mov     rax, [rax+10h]
0x18011098f  call    cs:__guard_dispatch_icall_fptr
0x180110995  nop
0x180110996  jmp     loc_180110B31
0x18011099b  mov     this, r12; String
0x18011099e  call    cs:__imp_wcslen
0x1801109a4  mov     rsi, rax
0x1801109a7  test    eax, eax
0x1801109a9  jz      loc_180110A80
0x1801109af  mov     r13d, [rbx-10h]
0x1801109b3  mov     r15, r12
0x1801109b6  sub     r15, rbx
0x1801109b9  sar     r15, 1
0x1801109bc  test    esi, esi
0x1801109be  js      loc_180110CEC
0x1801109c4  mov     ecx, 1
0x1801109c9  sub     ecx, [r14+10h]
0x1801109cd  mov     eax, [r14+0Ch]
0x1801109d1  sub     eax, esi
0x1801109d3  or      eax, ecx
0x1801109d5  jge     short loc_1801109E6
0x1801109d7  mov     edx, esi; nLength
0x1801109d9  lea     this, [rbp+57h+arg_18]; this
0x1801109dd  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1801109e2  mov     rbx, [rbp+57h+arg_18.m_pszData]
0x1801109e6  movsxd  r14, esi
0x1801109e9  add     r14, r14
0x1801109ec  cmp     r15, r13
0x1801109ef  ja      short loc_180110A2A
0x1801109f1  lea     lpBuffer, [rbx+r15*2]; Src
0x1801109f5  xor     r13d, r13d
0x1801109f8  test    r14, r14
0x1801109fb  jz      short loc_180110A69
0x1801109fd  test    lpBuffer, lpBuffer
0x180110a00  jnz     short loc_180110A10
0x180110a02  call    cs:__imp__errno
0x180110a08  mov     dword ptr [rax], 16h
0x180110a0e  jmp     short loc_180110A63
0x180110a10  movsxd  rax, dword ptr [rbx-0Ch]
0x180110a14  add     rax, rax
0x180110a17  cmp     rax, r14
0x180110a1a  jb      short loc_180110A57
0x180110a1c  mov     r8, r14; Size
0x180110a1f  mov     this, rbx; void *
0x180110a22  call    cs:__imp_memmove
0x180110a28  jmp     short loc_180110A69
0x180110a2a  movsxd  r8, dword ptr [rbx-0Ch]
0x180110a2e  add     r8, r8; Size
0x180110a31  xor     r13d, r13d
0x180110a34  test    r14, r14
0x180110a37  jz      short loc_180110A69
0x180110a39  mov     this, rbx; void *
0x180110a3c  cmp     r8, r14
0x180110a3f  jb      short loc_180110A4F
0x180110a41  mov     r8, r14; Size
0x180110a44  mov     lpBuffer, r12; Src
0x180110a47  call    cs:__imp_memcpy
0x180110a4d  jmp     short loc_180110A69
0x180110a4f  xor     edx, edx; Val
0x180110a51  call    cs:__imp_memset
0x180110a57  call    cs:__imp__errno
0x180110a5d  mov     dword ptr [rax], 22h ; '"'
0x180110a63  call    cs:__imp__invalid_parameter_noinfo
0x180110a69  cmp     esi, [rbx-0Ch]
0x180110a6c  jg      loc_180110CEC
0x180110a72  mov     [rbx-10h], esi
0x180110a75  mov     [r14+rbx], r13w
0x180110a7a  mov     r15, [rbp+57h+var_70]
0x180110a7e  jmp     short loc_180110A8D
0x180110a80  lea     this, [rbp+57h+arg_18]; this
0x180110a84  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180110a89  mov     rbx, [rbp+57h+arg_18.m_pszData]
0x180110a8d  lea     lpBuffer, [rbp+57h+arg_18]; strSrc
0x180110a91  lea     this, [rbp+57h+document.m_document.m_strErrorReason]; this
0x180110a95  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x180110a9a  nop
0x180110a9b  lea     lpBuffer, [rbx-18h]
0x180110a9f  or      r12d, 0FFFFFFFFh
0x180110aa3  mov     eax, r12d
0x180110aa6  lock xadd [lpBuffer+10h], eax
0x180110aab  add     eax, r12d
0x180110aae  test    eax, eax
0x180110ab0  jg      short loc_180110AC2
  ... truncated ...
```
