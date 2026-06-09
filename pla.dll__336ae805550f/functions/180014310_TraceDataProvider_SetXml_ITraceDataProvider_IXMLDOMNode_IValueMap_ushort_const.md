# TraceDataProvider::SetXml(ITraceDataProvider *,IXMLDOMNode *,IValueMap *,ushort const *)

- ea: `0x180014310`
- end: `0x180014fa1`
- name: `?SetXml@TraceDataProvider@@SAJPEAUITraceDataProvider@@PEAUIXMLDOMNode@@PEAUIValueMap@@PEBG@Z`
- size: `3217`
- prototype: `__int64 __fastcall(struct ITraceDataProvider *, struct IXMLDOMNode *, struct IValueMap *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180014fa8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18000e61c`
- `0x180014310`
- `0x1800157bc`
- `0x1800174c0`
- `0x180026850`
- `0x180045608`
- `0x1800b7124`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180014374`
- `OLEAUT32!__imp_VariantInit` at `0x180014374`
- `OLEAUT32!__imp_VariantClear` at `0x180014382`
- `OLEAUT32!__imp_VariantClear` at `0x180014f3c`
- `OLEAUT32!__imp_VariantClear` at `0x180014382`
- `OLEAUT32!__imp_VariantClear` at `0x180014f3c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014f61`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180014f61`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180014d84`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180014d84`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180014f4f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180014f4f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180014cf6`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180014cf6`

## string_xrefs

- `0x180014473`: `TraceDataProvider::SetXml`

## pseudocode

```c
__int64 __fastcall TraceDataProvider::SetXml(
        struct ITraceDataProvider *a1,
        struct IXMLDOMNode *a2,
        struct IValueMap *a3,
        const unsigned __int16 *a4)
{
  SAFEARRAY *v5; // r12
  int v9; // eax
  int v10; // eax
  ULONG v11; // ebx
  __int64 v12; // rax
  ULONG *p_cElements; // r9
  ULONG *v14; // rcx
  signed int v15; // eax
  __int64 v16; // rax
  signed int XmlValueMap; // eax
  __int64 v18; // rax
  signed int v19; // eax
  __int64 v20; // rax
  signed int v21; // eax
  __int64 v22; // rax
  signed int v23; // eax
  __int64 v24; // rax
  signed int v25; // eax
  __int64 v26; // rax
  signed int v27; // eax
  __int64 v28; // rax
  signed int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  signed int v32; // eax
  __int64 v33; // rax
  const unsigned __int16 *v34; // rcx
  int v35; // eax
  signed int v36; // eax
  __int64 v37; // rax
  struct ITraceDataProviderVtbl *lpVtbl; // rax
  int v39; // eax
  signed int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rax
  SAFEARRAY *Vector; // rax
  __int64 v44; // rax
  HRESULT v45; // eax
  __int64 v46; // rax
  signed int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  signed int v50; // eax
  __int64 v51; // rax
  ULONG cElements; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+78h] [rbp-88h] BYREF
  struct IValueMap *v55; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  void *ppvData; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID v58; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v59; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v60[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v61[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v62[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v63[64]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v64[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v65[64]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v66[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v67[64]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v68[64]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v69[64]; // [rsp+550h] [rbp+450h] BYREF
  unsigned __int16 v70[64]; // [rsp+5D0h] [rbp+4D0h] BYREF
  unsigned __int16 v71[64]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v72[64]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v73[64]; // [rsp+750h] [rbp+650h] BYREF
  unsigned __int16 v74[64]; // [rsp+7D0h] [rbp+6D0h] BYREF
  unsigned __int16 v75[64]; // [rsp+850h] [rbp+750h] BYREF
  unsigned __int16 v76[64]; // [rsp+8D0h] [rbp+7D0h] BYREF

  cElements = 0;
  ppvData = 0;
  v55 = 0;
  v59 = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"DisplayName", 8, a2, &pvarg) < 0
    || (v9 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, LONGLONG))a1->lpVtbl->put_DisplayName)(
               a1,
               pvarg.llVal)) == 0
    || (v10 = PlaiAddValidation(a3, a4, L"DisplayName", v9), v11 = v10, v10 >= 0) )
  {
    v15 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_Level)(a1, &v55);
    v11 = v15;
    if ( v15 < 0 )
    {
      v54 = 0;
      cElements = v15;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v61, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v61[v16] );
      goto LABEL_17;
    }
    XmlValueMap = PlaiReadXmlValueMap(L"Level", v55, a2, a3, a4);
    v11 = XmlValueMap;
    if ( XmlValueMap < 0 )
    {
      v54 = 0;
      cElements = XmlValueMap;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v62, 0x4000000000000800uLL);
      v18 = -1;
      do
        ++v18;
      while ( v62[v18] );
      goto LABEL_17;
    }
    if ( v55 )
    {
      ((void (__fastcall *)(struct IValueMap *))v55->lpVtbl->Release)(v55);
      v55 = 0;
    }
    v19 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_KeywordsAny)(
            a1,
            &v55);
    v11 = v19;
    if ( v19 < 0 )
    {
      v54 = 0;
      cElements = v19;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v63, 0x4000000000000800uLL);
      v20 = -1;
      do
        ++v20;
      while ( v63[v20] );
      goto LABEL_17;
    }
    v21 = PlaiReadXmlValueMap(L"KeywordsAny", v55, a2, a3, a4);
    v11 = v21;
    if ( v21 < 0 )
    {
      v54 = 0;
      cElements = v21;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v64, 0x4000000000000800uLL);
      v22 = -1;
      do
        ++v22;
      while ( v64[v22] );
      goto LABEL_17;
    }
    if ( v55 )
    {
      ((void (__fastcall *)(struct IValueMap *))v55->lpVtbl->Release)(v55);
      v55 = 0;
    }
    v23 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_KeywordsAll)(
            a1,
            &v55);
    v11 = v23;
    if ( v23 < 0 )
    {
      v54 = 0;
      cElements = v23;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v65, 0x4000000000000800uLL);
      v24 = -1;
      do
        ++v24;
      while ( v65[v24] );
      goto LABEL_17;
    }
    v25 = PlaiReadXmlValueMap(L"KeywordsAll", v55, a2, a3, a4);
    v11 = v25;
    if ( v25 < 0 )
    {
      v54 = 0;
      cElements = v25;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v66, 0x4000000000000800uLL);
      v26 = -1;
      do
        ++v26;
      while ( v66[v26] );
      goto LABEL_17;
    }
    if ( v55 )
    {
      ((void (__fastcall *)(struct IValueMap *))v55->lpVtbl->Release)(v55);
      v55 = 0;
    }
    v27 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct IValueMap **))a1->lpVtbl->get_Properties)(
            a1,
            &v55);
    v11 = v27;
    if ( v27 < 0 )
    {
      v54 = 0;
      cElements = v27;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v67, 0x4000000000000800uLL);
      v28 = -1;
      do
        ++v28;
      while ( v67[v28] );
      goto LABEL_17;
    }
    v29 = PlaiReadXmlValueMap(L"Properties", v55, a2, a3, a4);
    v11 = v29;
    if ( v29 < 0 )
    {
      v54 = 0;
      cElements = v29;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_139;
      }
      PlaiWhoAmI(v68, 0x4000000000000800uLL);
      v30 = -1;
      do
        ++v30;
      while ( v68[v30] );
      goto LABEL_17;
    }
    PlaiVariantClear(&pvarg);
    if ( (int)PlaiReadXmlElement(L"FilterEnabled", 11, a2, &pvarg) >= 0 )
    {
      v31 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, _QWORD))a1->lpVtbl->put_FilterEnabled)(
              a1,
              pvarg.uiVal);
      if ( v31 )
      {
        v32 = PlaiAddValidation(a3, a4, L"FilterEnabled", v31);
        v11 = v32;
        if ( v32 < 0 )
        {
          v54 = 0;
          cElements = v32;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_139;
          }
          PlaiWhoAmI(v69, 0x4000000000000800uLL);
          v33 = -1;
          do
            ++v33;
          while ( v69[v33] );
          goto LABEL_17;
        }
      }
    }
    PlaiVariantClear(&pvarg);
    if ( (int)PlaiReadXmlElement(L"FilterType", 19, a2, &pvarg) >= 0 )
    {
      v35 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, _QWORD))a1->lpVtbl->put_FilterType)(
              a1,
              pvarg.cyVal.Lo);
      if ( v35 )
      {
        v36 = PlaiAddValidation(a3, a4, L"FilterType", v35);
        v11 = v36;
        if ( v36 < 0 )
        {
          v54 = 0;
          cElements = v36;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_139;
          }
          PlaiWhoAmI(v70, 0x4000000000000800uLL);
          v37 = -1;
          do
            ++v37;
          while ( v70[v37] );
          goto LABEL_17;
        }
      }
    }
    if ( PlaiReadXmlGuid(v34, a2, &v59) >= 0 )
    {
      lpVtbl = a1->lpVtbl;
      v58 = v59;
      v39 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, struct _GUID *))lpVtbl->put_Guid)(a1, &v58);
      if ( v39 < 0 )
      {
        v40 = PlaiAddValidation(a3, a4, L"Guid", v39);
        v11 = v40;
        if ( v40 < 0 )
        {
          v54 = 0;
          cElements = v40;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_139;
          }
          PlaiWhoAmI(v71, 0x4000000000000800uLL);
          v41 = -1;
          do
            ++v41;
          while ( v71[v41] );
          goto LABEL_17;
        }
      }
    }
    PlaiVariantClear(&pvarg);
    if ( (int)PlaiReadXmlElement(L"FilterData", 8, a2, &pvarg) >= 0 )
    {
      v11 = PlaiBase64Decode(pvarg.bstrVal, 0, 0, &cElements);
      if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024774 )
      {
        v54 = 0;
        cElements = v11;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_139;
        }
        PlaiWhoAmI(v72, 0x4000000000000800uLL);
        v42 = -1;
        do
          ++v42;
        while ( v72[v42] );
        goto LABEL_17;
      }
      Vector = SafeArrayCreateVector(0x11u, 0, cElements);
      v5 = Vector;
      if ( !Vector )
      {
        v11 = -2147024882;
        cElements = -2147024882;
        v54 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_139;
        }
        PlaiWhoAmI(v73, 0x4000000000000800uLL);
        v44 = -1;
        do
          ++v44;
        while ( v73[v44] );
        goto LABEL_17;
      }
      v45 = SafeArrayAccessData(Vector, &ppvData);
      v11 = v45;
      if ( v45 < 0 )
      {
        v54 = 0;
        cElements = v45;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_139;
        }
        PlaiWhoAmI(v74, 0x4000000000000800uLL);
        v46 = -1;
        do
          ++v46;
        while ( v74[v46] );
        goto LABEL_17;
      }
      v47 = PlaiBase64Decode(pvarg.bstrVal, (unsigned __int8 *)ppvData, cElements, &cElements);
      v11 = v47;
      if ( v47 < 0 )
      {
        v54 = 0;
        cElements = v47;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_139;
        }
        PlaiWhoAmI(v75, 0x4000000000000800uLL);
        v48 = -1;
        do
          ++v48;
        while ( v75[v48] );
        goto LABEL_17;
      }
      v49 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, SAFEARRAY *))a1->lpVtbl->put_FilterData)(a1, v5);
      if ( v49 )
      {
        v50 = PlaiAddValidation(a3, a4, L"FilterData", v49);
        v11 = v50;
        if ( v50 < 0 )
        {
          v54 = 0;
          cElements = v50;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_139;
          }
          PlaiWhoAmI(v76, 0x4000000000000800uLL);
          v51 = -1;
          do
            ++v51;
          while ( v76[v51] );
LABEL_17:
          p_cElements = &cElements;
          v14 = (ULONG *)&v54;
LABEL_10:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, p_cElements, 4, byte_180147320, 1, v14, 4);
          goto LABEL_139;
        }
      }
    }
    v11 = 0;
    goto LABEL_139;
  }
  cElements = 0;
  v54 = v10;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v60, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v60[v12] );
    p_cElements = (ULONG *)&v54;
    v14 = &cElements;
    goto LABEL_10;
  }
LABEL_139:
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( ppvData )
  {
    SafeArrayUnaccessData(v5);
    ppvData = 0;
  }
  if ( v5 )
    SafeArrayDestroy(v5);
  if ( v55 )
    ((void (__fastcall *)(struct IValueMap *))v55->lpVtbl->Release)(v55);
  return v11;
}

```

## disassembly

```asm
0x180014310  push    rbp
0x180014312  push    rbx
0x180014313  push    rsi
0x180014314  push    rdi
0x180014315  push    r12
0x180014317  push    r13
0x180014319  push    r14
0x18001431b  push    r15
0x18001431d  lea     rbp, [rsp-868h]
0x180014325  sub     rsp, 968h
0x18001432c  mov     rax, cs:__security_cookie
0x180014333  xor     rax, rsp
0x180014336  mov     [rbp+8A0h+var_50], rax
0x18001433d  xor     r13d, r13d
0x180014340  mov     rdi, rcx
0x180014343  xorps   xmm0, xmm0
0x180014346  mov     [rsp+9A0h+cElements], r13d
0x18001434b  xorps   xmm1, xmm1
0x18001434e  mov     [rbp+8A0h+ppvData], r13
0x180014352  xor     eax, eax
0x180014354  mov     [rbp+8A0h+var_920], r13
0x180014358  lea     rcx, [rbp+8A0h+pvarg]; pvarg
0x18001435c  mov     qword ptr [rbp+8A0h+pvarg+10h], rax
0x180014360  movups  xmmword ptr [rbp+8A0h+var_8E0.Data1], xmm0
0x180014364  mov     r12d, r13d
0x180014367  mov     r14, r9
0x18001436a  movups  xmmword ptr [rbp+8A0h+pvarg], xmm1
0x18001436e  mov     rsi, r8
0x180014371  mov     r15, rdx
0x180014374  call    cs:__imp_VariantInit
0x18001437a  lea     rcx, [rbp+8A0h+pvarg]; pvarg
0x18001437e  mov     qword ptr [rbp+8A0h+pvarg+8], r13
0x180014382  call    cs:__imp_VariantClear
0x180014388  lea     edx, [r13+8]; unsigned __int16
0x18001438c  mov     qword ptr [rbp+8A0h+pvarg+8], r13
0x180014390  lea     r9, [rbp+8A0h+pvarg]; struct tagVARIANT *
0x180014394  mov     r8, r15; struct IXMLDOMNode *
0x180014397  lea     rcx, aDisplayname; "DisplayName"
0x18001439e  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x1800143a3  test    eax, eax
0x1800143a5  js      loc_1800144BD
0x1800143ab  mov     rax, [rdi]
0x1800143ae  mov     rcx, rdi
0x1800143b1  mov     rdx, qword ptr [rbp+8A0h+pvarg+8]
0x1800143b5  mov     rax, [rax+40h]
0x1800143b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143be  test    eax, eax
0x1800143c0  jz      loc_1800144BD
0x1800143c6  mov     r9d, eax; int
0x1800143c9  lea     r8, aDisplayname; "DisplayName"
0x1800143d0  mov     rdx, r14; unsigned __int16 *
0x1800143d3  mov     rcx, rsi; struct IValueMap *
0x1800143d6  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x1800143db  mov     ebx, eax
0x1800143dd  test    eax, eax
0x1800143df  jns     loc_1800144BD
0x1800143e5  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800143ec  mov     [rsp+9A0h+cElements], r13d
0x1800143f1  mov     [rsp+9A0h+var_928], eax
0x1800143f5  jz      loc_180014F38
0x1800143fb  mov     rdx, 4000000000000800h; unsigned __int64
0x180014405  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001440c  jz      loc_180014F38
0x180014412  mov     rax, cs:qword_180169748
0x180014419  and     rax, rdx
0x18001441c  cmp     cs:qword_180169748, rax
0x180014423  jnz     loc_180014F38
0x180014429  lea     rcx, [rbp+8A0h+var_8D0]; unsigned __int16 *
0x18001442d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180014432  lea     rcx, [rbp+8A0h+var_8D0]
0x180014436  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001443a  inc     rax
0x18001443d  cmp     [rcx+rax*2], r13w
0x180014442  jnz     short loc_18001443A
0x180014444  lea     ecx, [rax+rax]
0x180014447  add     rcx, 2
0x18001444b  lea     rax, [rbp+8A0h+var_8D0]
0x18001444f  mov     [rsp+9A0h+var_940], rcx
0x180014454  lea     r9, [rsp+9A0h+var_928]
0x180014459  lea     rcx, [rsp+9A0h+cElements]
0x18001445e  mov     [rsp+9A0h+var_948], rax
0x180014463  lea     rdx, PLA_EVENT_ERROR
0x18001446a  mov     [rsp+9A0h+var_950], 1Ah
0x180014473  lea     rax, aTracedataprovi_14; "TraceDataProvider::SetXml"
0x18001447a  mov     [rsp+9A0h+var_958], rax
0x18001447f  mov     eax, 4
0x180014484  mov     [rsp+9A0h+var_960], rax
0x180014489  mov     [rsp+9A0h+var_968], rcx
0x18001448e  lea     rcx, byte_180147320
0x180014495  mov     [rsp+9A0h+var_970], 1
0x18001449e  mov     [rsp+9A0h+var_978], rcx
0x1800144a3  lea     r8d, [rax+1]
0x1800144a7  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800144ae  mov     [rsp+9A0h+var_980], rax
0x1800144b3  call    EventingWriteEvent
0x1800144b8  jmp     loc_180014F38
0x1800144bd  mov     rcx, [rbp+8A0h+var_920]
0x1800144c1  test    rcx, rcx
0x1800144c4  jz      short loc_1800144D6
0x1800144c6  mov     rax, [rcx]
0x1800144c9  mov     rax, [rax+10h]
0x1800144cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144d2  mov     [rbp+8A0h+var_920], r13
0x1800144d6  mov     rax, [rdi]
0x1800144d9  lea     rdx, [rbp+8A0h+var_920]
0x1800144dd  mov     rcx, rdi
0x1800144e0  mov     rax, [rax+58h]
0x1800144e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144e9  mov     ebx, eax
0x1800144eb  test    eax, eax
0x1800144ed  jns     short loc_18001456D
0x1800144ef  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800144f6  mov     [rsp+9A0h+var_928], r13d
0x1800144fb  mov     [rsp+9A0h+cElements], eax
0x1800144ff  jz      loc_180014F38
0x180014505  mov     rdx, 4000000000000800h; unsigned __int64
0x18001450f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180014516  jz      loc_180014F38
0x18001451c  mov     rax, cs:qword_180169748
0x180014523  and     rax, rdx
0x180014526  cmp     cs:qword_180169748, rax
0x18001452d  jnz     loc_180014F38
0x180014533  lea     rcx, [rbp+8A0h+var_850]; unsigned __int16 *
0x180014537  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001453c  lea     rcx, [rbp+8A0h+var_850]
0x180014540  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014544  inc     rax
0x180014547  cmp     [rcx+rax*2], r13w
0x18001454c  jnz     short loc_180014544
0x18001454e  lea     ecx, [rax+rax]
0x180014551  lea     rax, [rbp+8A0h+var_850]
0x180014555  add     rcx, 2
0x180014559  lea     r9, [rsp+9A0h+cElements]
0x18001455e  mov     [rsp+9A0h+var_940], rcx
0x180014563  lea     rcx, [rsp+9A0h+var_928]
0x180014568  jmp     loc_18001445E
0x18001456d  mov     rdx, [rbp+8A0h+var_920]; struct IValueMap *
0x180014571  lea     rcx, aLevel_0; "Level"
0x180014578  mov     r9, rsi; struct IValueMap *
0x18001457b  mov     [rsp+9A0h+var_980], r14; unsigned __int16 *
0x180014580  mov     r8, r15; struct IXMLDOMNode *
0x180014583  call    ?PlaiReadXmlValueMap@@YAJPEBGPEAUIValueMap@@PEAUIXMLDOMNode@@10@Z; PlaiReadXmlValueMap(ushort const *,IValueMap *,IXMLDOMNode *,IValueMap *,ushort const *)
0x180014588  mov     ebx, eax
0x18001458a  test    eax, eax
0x18001458c  jns     short loc_180014602
0x18001458e  cmp     dword ptr cs:xmmword_180169738, r13d
0x180014595  mov     [rsp+9A0h+var_928], r13d
0x18001459a  mov     [rsp+9A0h+cElements], eax
0x18001459e  jz      loc_180014F38
0x1800145a4  mov     rdx, 4000000000000800h; unsigned __int64
0x1800145ae  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800145b5  jz      loc_180014F38
0x1800145bb  mov     rax, cs:qword_180169748
0x1800145c2  and     rax, rdx
0x1800145c5  cmp     cs:qword_180169748, rax
0x1800145cc  jnz     loc_180014F38
0x1800145d2  lea     rcx, [rbp+8A0h+var_7D0]; unsigned __int16 *
0x1800145d9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800145de  lea     rcx, [rbp+8A0h+var_7D0]
0x1800145e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800145e9  inc     rax
0x1800145ec  cmp     [rcx+rax*2], r13w
0x1800145f1  jnz     short loc_1800145E9
0x1800145f3  lea     ecx, [rax+rax]
0x1800145f6  lea     rax, [rbp+8A0h+var_7D0]
0x1800145fd  jmp     loc_180014555
0x180014602  mov     rcx, [rbp+8A0h+var_920]
0x180014606  test    rcx, rcx
0x180014609  jz      short loc_18001461B
0x18001460b  mov     rax, [rcx]
0x18001460e  mov     rax, [rax+10h]
0x180014612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014617  mov     [rbp+8A0h+var_920], r13
0x18001461b  mov     rax, [rdi]
0x18001461e  lea     rdx, [rbp+8A0h+var_920]
0x180014622  mov     rcx, rdi
0x180014625  mov     rax, [rax+60h]
0x180014629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001462e  mov     ebx, eax
0x180014630  test    eax, eax
0x180014632  jns     short loc_1800146A8
0x180014634  cmp     dword ptr cs:xmmword_180169738, r13d
0x18001463b  mov     [rsp+9A0h+var_928], r13d
0x180014640  mov     [rsp+9A0h+cElements], eax
0x180014644  jz      loc_180014F38
0x18001464a  mov     rdx, 4000000000000800h; unsigned __int64
0x180014654  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001465b  jz      loc_180014F38
0x180014661  mov     rax, cs:qword_180169748
0x180014668  and     rax, rdx
0x18001466b  cmp     cs:qword_180169748, rax
0x180014672  jnz     loc_180014F38
0x180014678  lea     rcx, [rbp+8A0h+var_750]; unsigned __int16 *
0x18001467f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180014684  lea     rcx, [rbp+8A0h+var_750]
0x18001468b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001468f  inc     rax
0x180014692  cmp     [rcx+rax*2], r13w
0x180014697  jnz     short loc_18001468F
0x180014699  lea     ecx, [rax+rax]
0x18001469c  lea     rax, [rbp+8A0h+var_750]
0x1800146a3  jmp     loc_180014555
0x1800146a8  mov     rdx, [rbp+8A0h+var_920]; struct IValueMap *
0x1800146ac  lea     rcx, aKeywordsany; "KeywordsAny"
0x1800146b3  mov     r9, rsi; struct IValueMap *
0x1800146b6  mov     [rsp+9A0h+var_980], r14; unsigned __int16 *
0x1800146bb  mov     r8, r15; struct IXMLDOMNode *
0x1800146be  call    ?PlaiReadXmlValueMap@@YAJPEBGPEAUIValueMap@@PEAUIXMLDOMNode@@10@Z; PlaiReadXmlValueMap(ushort const *,IValueMap *,IXMLDOMNode *,IValueMap *,ushort const *)
0x1800146c3  mov     ebx, eax
0x1800146c5  test    eax, eax
0x1800146c7  jns     short loc_18001473D
0x1800146c9  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800146d0  mov     [rsp+9A0h+var_928], r13d
0x1800146d5  mov     [rsp+9A0h+cElements], eax
0x1800146d9  jz      loc_180014F38
0x1800146df  mov     rdx, 4000000000000800h; unsigned __int64
0x1800146e9  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800146f0  jz      loc_180014F38
0x1800146f6  mov     rax, cs:qword_180169748
0x1800146fd  and     rax, rdx
0x180014700  cmp     cs:qword_180169748, rax
0x180014707  jnz     loc_180014F38
0x18001470d  lea     rcx, [rbp+8A0h+var_6D0]; unsigned __int16 *
0x180014714  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180014719  lea     rcx, [rbp+8A0h+var_6D0]
0x180014720  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014724  inc     rax
0x180014727  cmp     [rcx+rax*2], r13w
0x18001472c  jnz     short loc_180014724
0x18001472e  lea     ecx, [rax+rax]
0x180014731  lea     rax, [rbp+8A0h+var_6D0]
0x180014738  jmp     loc_180014555
0x18001473d  mov     rcx, [rbp+8A0h+var_920]
0x180014741  test    rcx, rcx
0x180014744  jz      short loc_180014756
0x180014746  mov     rax, [rcx]
0x180014749  mov     rax, [rax+10h]
0x18001474d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014752  mov     [rbp+8A0h+var_920], r13
0x180014756  mov     rax, [rdi]
0x180014759  lea     rdx, [rbp+8A0h+var_920]
0x18001475d  mov     rcx, rdi
0x180014760  mov     rax, [rax+68h]
0x180014764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014769  mov     ebx, eax
0x18001476b  test    eax, eax
0x18001476d  jns     short loc_1800147E3
0x18001476f  cmp     dword ptr cs:xmmword_180169738, r13d
0x180014776  mov     [rsp+9A0h+var_928], r13d
0x18001477b  mov     [rsp+9A0h+cElements], eax
0x18001477f  jz      loc_180014F38
0x180014785  mov     rdx, 4000000000000800h; unsigned __int64
0x18001478f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180014796  jz      loc_180014F38
0x18001479c  mov     rax, cs:qword_180169748
0x1800147a3  and     rax, rdx
0x1800147a6  cmp     cs:qword_180169748, rax
0x1800147ad  jnz     loc_180014F38
0x1800147b3  lea     rcx, [rbp+8A0h+var_650]; unsigned __int16 *
0x1800147ba  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800147bf  lea     rcx, [rbp+8A0h+var_650]
0x1800147c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800147ca  inc     rax
0x1800147cd  cmp     [rcx+rax*2], r13w
0x1800147d2  jnz     short loc_1800147CA
0x1800147d4  lea     ecx, [rax+rax]
0x1800147d7  lea     rax, [rbp+8A0h+var_650]
0x1800147de  jmp     loc_180014555
0x1800147e3  mov     rdx, [rbp+8A0h+var_920]; struct IValueMap *
0x1800147e7  lea     rcx, aKeywordsall; "KeywordsAll"
0x1800147ee  mov     r9, rsi; struct IValueMap *
0x1800147f1  mov     [rsp+9A0h+var_980], r14; unsigned __int16 *
0x1800147f6  mov     r8, r15; struct IXMLDOMNode *
0x1800147f9  call    ?PlaiReadXmlValueMap@@YAJPEBGPEAUIValueMap@@PEAUIXMLDOMNode@@10@Z; PlaiReadXmlValueMap(ushort const *,IValueMap *,IXMLDOMNode *,IValueMap *,ushort const *)
0x1800147fe  mov     ebx, eax
0x180014800  test    eax, eax
0x180014802  jns     short loc_180014878
0x180014804  cmp     dword ptr cs:xmmword_180169738, r13d
0x18001480b  mov     [rsp+9A0h+var_928], r13d
0x180014810  mov     [rsp+9A0h+cElements], eax
0x180014814  jz      loc_180014F38
0x18001481a  mov     rdx, 4000000000000800h; unsigned __int64
0x180014824  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001482b  jz      loc_180014F38
0x180014831  mov     rax, cs:qword_180169748
0x180014838  and     rax, rdx
0x18001483b  cmp     cs:qword_180169748, rax
0x180014842  jnz     loc_180014F38
0x180014848  lea     rcx, [rbp+8A0h+var_5D0]; unsigned __int16 *
0x18001484f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180014854  lea     rcx, [rbp+8A0h+var_5D0]
0x18001485b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001485f  inc     rax
0x180014862  cmp     [rcx+rax*2], r13w
0x180014867  jnz     short loc_18001485F
0x180014869  lea     ecx, [rax+rax]
0x18001486c  lea     rax, [rbp+8A0h+var_5D0]
0x180014873  jmp     loc_180014555
0x180014878  mov     rcx, [rbp+8A0h+var_920]
0x18001487c  test    rcx, rcx
  ... truncated ...
```
