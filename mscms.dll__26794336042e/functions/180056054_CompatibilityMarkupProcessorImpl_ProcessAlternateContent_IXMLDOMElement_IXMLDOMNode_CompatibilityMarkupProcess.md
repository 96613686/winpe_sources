# CompatibilityMarkupProcessorImpl::ProcessAlternateContent(IXMLDOMElement *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *)

- ea: `0x180056054`
- end: `0x1800567f7`
- name: `?ProcessAlternateContent@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@PEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@@Z`
- size: `1955`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000feb0`

## callees

- `0x18000fe54`
- `0x180010670`
- `0x180011a94`
- `0x180012620`
- `0x1800126c8`
- `0x18001277c`
- `0x1800127cc`
- `0x18001e34c`
- `0x18002b4f4`
- `0x18005561c`
- `0x180056054`
- `0x180056800`
- `0x18005695c`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800562a5`
- `OLEAUT32!__imp_SysFreeString` at `0x180056483`
- `OLEAUT32!__imp_SysFreeString` at `0x1800564f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005651a`
- `OLEAUT32!__imp_SysFreeString` at `0x180056525`
- `OLEAUT32!__imp_SysFreeString` at `0x180056544`
- `OLEAUT32!__imp_SysFreeString` at `0x18005654f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800565a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800565b0`
- `OLEAUT32!__imp_SysFreeString` at `0x180056614`
- `OLEAUT32!__imp_SysFreeString` at `0x1800562a5`
- `OLEAUT32!__imp_SysFreeString` at `0x180056483`
- `OLEAUT32!__imp_SysFreeString` at `0x1800564f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005651a`
- `OLEAUT32!__imp_SysFreeString` at `0x180056525`
- `OLEAUT32!__imp_SysFreeString` at `0x180056544`
- `OLEAUT32!__imp_SysFreeString` at `0x18005654f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800565a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800565b0`
- `OLEAUT32!__imp_SysFreeString` at `0x180056614`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CompatibilityMarkupProcessorImpl::ProcessAlternateContent(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        void *a5,
        void *a6)
{
  char v10; // r13
  int v11; // ebx
  void *v12; // rdi
  void *v13; // rsi
  char *v14; // rbx
  void *v15; // rbx
  void *v16; // rbx
  int v17; // r12d
  int v18; // esi
  int v19; // r14d
  int i; // edi
  int v21; // eax
  BSTR v22; // rdx
  BSTR v23; // rax
  int v24; // ecx
  int v25; // r8d
  OLECHAR *v26; // rcx
  BSTR v27; // rax
  int v28; // edx
  int v29; // r8d
  BSTR v30; // rax
  int v31; // edx
  int v32; // r8d
  int v33; // eax
  int v34; // ecx
  CompatibilityMarkupProcessorImpl *v35; // rcx
  __int64 v37; // [rsp+58h] [rbp-79h] BYREF
  __int64 v38; // [rsp+60h] [rbp-71h] BYREF
  void *v39; // [rsp+68h] [rbp-69h] BYREF
  void *v40; // [rsp+70h] [rbp-61h] BYREF
  char *v41; // [rsp+78h] [rbp-59h] BYREF
  void (__fastcall ***v42)(_QWORD, GUID *, _QWORD *); // [rsp+80h] [rbp-51h] BYREF
  __int64 v43; // [rsp+88h] [rbp-49h] BYREF
  BSTR v44; // [rsp+90h] [rbp-41h] BYREF
  int v45; // [rsp+98h] [rbp-39h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-31h] BYREF
  int v47; // [rsp+A8h] [rbp-29h] BYREF
  void *v48; // [rsp+B0h] [rbp-21h] BYREF
  void *v49; // [rsp+B8h] [rbp-19h] BYREF
  char *v50; // [rsp+C0h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp-9h] BYREF
  struct IXMLDOMNamedNodeMap *v52; // [rsp+D0h] [rbp-1h] BYREF
  void (__fastcall ***v53[8])(_QWORD, GUID *, _QWORD *); // [rsp+D8h] [rbp+7h] BYREF
  char v54; // [rsp+130h] [rbp+5Fh] BYREF
  __int64 v55; // [rsp+138h] [rbp+67h]
  char *v56; // [rsp+140h] [rbp+6Fh]

  v56 = a4;
  v55 = a3;
  v10 = 0;
  v46 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 128LL))(a2, &v46);
  if ( v11 < 0 )
    goto LABEL_80;
  v53[0] = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a3 + 160LL))(a3, a2, v53);
  if ( v11 < 0 )
    goto LABEL_79;
  ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>(
    &v37,
    v53[0]);
  if ( !v37 )
    goto LABEL_4;
  v50 = a4;
  v12 = a5;
  v48 = a5;
  v13 = a6;
  v49 = a6;
  v11 = CompatibilityMarkupProcessorImpl::ProcessAttributes(a1, v37, &v50, &v48, &v49, 1);
  if ( v11 < 0 )
    goto LABEL_78;
  v41 = 0;
  v14 = v50;
  if ( v50 != a4 )
  {
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
    v41 = v14;
  }
  v40 = 0;
  v15 = v48;
  if ( v48 != v12 )
  {
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
    v40 = v15;
  }
  v39 = 0;
  v16 = v49;
  if ( v49 != v13 )
  {
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
    v39 = v16;
  }
  v38 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 96LL))(v37, &v38);
  if ( v11 < 0 )
    goto LABEL_77;
  if ( !v38 )
  {
    v11 = -2147467259;
    goto LABEL_77;
  }
  v45 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 64LL))(v38, &v45);
  if ( v11 < 0 )
  {
LABEL_77:
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
    NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
LABEL_78:
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
    goto LABEL_79;
  }
  v17 = 0;
  v18 = -1;
  v19 = -1;
  for ( i = 0; i < v45; ++i )
  {
    v42 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v38 + 56LL))(v38, (unsigned int)i, &v42);
    if ( v11 < 0 )
      goto LABEL_59;
    if ( !v42 )
    {
      v11 = -2147467259;
      goto LABEL_59;
    }
    v47 = 0;
    v11 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), int *))(*v42)[10])(v42, &v47);
    if ( v11 < 0 )
      goto LABEL_59;
    if ( v47 == 1 )
    {
      ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>(
        &v43,
        v42);
      if ( !v43 )
      {
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v42);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
        NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
        NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
        NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
LABEL_4:
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
        v11 = -2147467262;
        goto LABEL_79;
      }
      v44 = 0;
      v21 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), BSTR *))(*v42)[39])(v42, &v44);
      v11 = v21;
      if ( v21 < 0 )
        goto LABEL_58;
      if ( v21 == 1 )
      {
        ATL::CComBSTR::operator=(&v44, &word_1800884E0);
        v22 = v44;
        if ( !v44 )
        {
          SysFreeString(0);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v42);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
          v11 = -2147024882;
          goto LABEL_79;
        }
      }
      else
      {
        v22 = v44;
      }
      v23 = v22;
      do
      {
        v24 = *(BSTR)((char *)v23 + a1[29] - (_QWORD)v22);
        v25 = *v23 - v24;
        if ( v25 )
          break;
        ++v23;
      }
      while ( v24 );
      if ( v25 )
      {
        v33 = CompatibilityMarkupProcessorImpl::EvaluateNamespaceURI(a1, v22, v48);
        if ( (v33 & 0xFFFFFFFD) == 0 )
        {
          SysFreeString(v44);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v42);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
          NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
          v11 = -2147221494;
          goto LABEL_79;
        }
        if ( v33 == 1 )
        {
          v11 = CompatibilityMarkupProcessorImpl::ProcessIgnoredElement(
                  v34,
                  v43,
                  v37,
                  (_DWORD)v50,
                  (__int64)v56,
                  (__int64)v49);
          if ( v11 < 0 )
            goto LABEL_58;
          v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 64LL))(v38, &v45);
          if ( v11 < 0 )
            goto LABEL_58;
          --i;
        }
      }
      else
      {
        bstrString = 0;
        v11 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), BSTR *))(*v42)[41])(
                v42,
                &bstrString);
        v26 = bstrString;
        if ( v11 < 0 )
          goto LABEL_57;
        if ( !bstrString || !*bstrString )
        {
          v11 = -2147467259;
          goto LABEL_57;
        }
        v27 = bstrString;
        do
        {
          v28 = *(BSTR)((char *)v27 + a1[31] - (_QWORD)bstrString);
          v29 = *v27 - v28;
          if ( v29 )
            break;
          ++v27;
        }
        while ( v28 );
        if ( v29 )
        {
          v30 = bstrString;
          do
          {
            v31 = *(BSTR)((char *)v30 + a1[32] - (_QWORD)bstrString);
            v32 = *v30 - v31;
            if ( v32 )
              break;
            ++v30;
          }
          while ( v31 );
          if ( v32 )
          {
            SysFreeString(bstrString);
            SysFreeString(v44);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v42);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
            NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
            NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
            NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
            v11 = -2147221493;
            goto LABEL_79;
          }
          if ( v18 != -1 )
          {
            SysFreeString(bstrString);
            SysFreeString(v44);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v42);
LABEL_61:
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
            NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
            NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
            NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
            v11 = -2147221492;
            goto LABEL_79;
          }
          v11 = CompatibilityMarkupProcessorImpl::ProcessFallbackElement(
                  (_DWORD)a1,
                  v43,
                  v55,
                  v46,
                  (__int64)v50,
                  (__int64)v56,
                  (__int64)v48,
                  (__int64)v49,
                  v10);
          if ( v11 < 0 )
          {
LABEL_56:
            v26 = bstrString;
LABEL_57:
            SysFreeString(v26);
LABEL_58:
            SysFreeString(v44);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
LABEL_59:
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v42);
            goto LABEL_77;
          }
          v18 = i;
        }
        else
        {
          v54 = 0;
          v11 = CompatibilityMarkupProcessorImpl::ProcessChoiceElement(
                  (_DWORD)a1,
                  v43,
                  v55,
                  v46,
                  (__int64)v50,
                  (__int64)v56,
                  (__int64)v48,
                  (__int64)v49,
                  v10,
                  (__int64)&v54);
          if ( v11 < 0 )
            goto LABEL_56;
          ++v17;
          if ( !v10 )
            v10 = v54 != 0;
        }
        SysFreeString(bstrString);
        v19 = i;
      }
      SysFreeString(v44);
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
    }
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v42);
  }
  if ( v17 )
  {
    if ( v18 != -1 && v18 != v19 )
      goto LABEL_61;
    v52 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNamedNodeMap **))(*(_QWORD *)v37 + 136LL))(v37, &v52);
    if ( v11 >= 0 )
    {
      v11 = CompatibilityMarkupProcessorImpl::CheckRemainingAttributes(v35, v52);
      if ( v11 >= 0 )
      {
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v52);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
        NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
        NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
        NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v53);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v46);
        return 0;
      }
    }
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v52);
    goto LABEL_77;
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v38);
  NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(&v39);
  NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(&v40);
  NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(&v41);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v37);
  v11 = -2147221491;
LABEL_79:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v53);
LABEL_80:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v46);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180056054  mov     rax, rsp
0x180056057  mov     [rax+8], rbx
0x18005605b  mov     [rax+20h], r9
0x18005605f  mov     [rax+18h], r8
0x180056063  push    rbp
0x180056064  push    rsi
0x180056065  push    rdi
0x180056066  push    r12
0x180056068  push    r13
0x18005606a  push    r14
0x18005606c  push    r15
0x18005606e  lea     rbp, [rax-4Fh]
0x180056072  sub     rsp, 0E0h
0x180056079  mov     r14, r9
0x18005607c  mov     rsi, r8
0x18005607f  mov     rdi, rdx
0x180056082  mov     r15, rcx
0x180056085  xor     r13d, r13d
0x180056088  mov     [rbp+47h+var_78], r13
0x18005608c  mov     rax, [rdx]
0x18005608f  lea     rdx, [rbp+47h+var_78]
0x180056093  mov     rcx, rdi
0x180056096  mov     rax, [rax+80h]
0x18005609d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560a2  mov     ebx, eax
0x1800560a4  test    eax, eax
0x1800560a6  js      loc_1800567D1
0x1800560ac  mov     [rbp+47h+var_40], r13
0x1800560b0  mov     rax, [rsi]
0x1800560b3  lea     r8, [rbp+47h+var_40]
0x1800560b7  mov     rdx, rdi
0x1800560ba  mov     rcx, rsi
0x1800560bd  mov     rax, [rax+0A0h]
0x1800560c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560c9  mov     ebx, eax
0x1800560cb  test    eax, eax
0x1800560cd  js      loc_1800567C7
0x1800560d3  mov     rdx, [rbp+47h+var_40]
0x1800560d7  lea     rcx, [rbp+47h+var_C0]
0x1800560db  call    ??0?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>(IUnknown *)
0x1800560e0  nop
0x1800560e1  mov     rdx, [rbp+47h+var_C0]
0x1800560e5  test    rdx, rdx
0x1800560e8  jnz     short loc_1800560FD
0x1800560ea  lea     rcx, [rbp+47h+var_C0]
0x1800560ee  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800560f3  mov     ebx, 80004002h
0x1800560f8  jmp     loc_1800567C7
0x1800560fd  mov     [rbp+47h+var_58], r14
0x180056101  mov     rdi, [rbp+47h+arg_20]
0x180056105  mov     [rbp+47h+var_68], rdi
0x180056109  mov     rsi, [rbp+47h+arg_28]
0x18005610d  mov     [rbp+47h+var_60], rsi
0x180056111  mov     byte ptr [rsp+110h+var_E8], 1
0x180056116  lea     rax, [rbp+47h+var_60]
0x18005611a  mov     [rsp+110h+var_F0], rax
0x18005611f  lea     r9, [rbp+47h+var_68]
0x180056123  lea     r8, [rbp+47h+var_58]
0x180056127  mov     rcx, r15
0x18005612a  call    ?ProcessAttributes@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAPEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@PEAPEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAPEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@_N@Z; CompatibilityMarkupProcessorImpl::ProcessAttributes(IXMLDOMElement *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> * *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> * *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> * *,bool)
0x18005612f  mov     ebx, eax
0x180056131  test    eax, eax
0x180056133  js      loc_1800567BD
0x180056139  mov     [rbp+47h+var_A0], r13
0x18005613d  mov     rbx, [rbp+47h+var_58]
0x180056141  cmp     rbx, r14
0x180056144  jz      short loc_180056153
0x180056146  lea     rcx, [rbp+47h+var_A0]
0x18005614a  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(void)
0x18005614f  mov     [rbp+47h+var_A0], rbx
0x180056153  mov     [rbp+47h+var_A8], r13
0x180056157  mov     rbx, [rbp+47h+var_68]
0x18005615b  cmp     rbx, rdi
0x18005615e  jz      short loc_18005616D
0x180056160  lea     rcx, [rbp+47h+var_A8]
0x180056164  call    ?Reset@?$TGenericSP@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(void)
0x180056169  mov     [rbp+47h+var_A8], rbx
0x18005616d  mov     [rbp+47h+var_B0], r13
0x180056171  mov     rbx, [rbp+47h+var_60]
0x180056175  cmp     rbx, rsi
0x180056178  jz      short loc_180056187
0x18005617a  lea     rcx, [rbp+47h+var_B0]
0x18005617e  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(void)
0x180056183  mov     [rbp+47h+var_B0], rbx
0x180056187  mov     [rbp+47h+var_B8], r13
0x18005618b  mov     rcx, [rbp+47h+var_C0]
0x18005618f  mov     rax, [rcx]
0x180056192  lea     rdx, [rbp+47h+var_B8]
0x180056196  mov     rax, [rax+60h]
0x18005619a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005619f  mov     ebx, eax
0x1800561a1  test    eax, eax
0x1800561a3  js      loc_180056795
0x1800561a9  mov     rcx, [rbp+47h+var_B8]
0x1800561ad  test    rcx, rcx
0x1800561b0  jz      loc_180056790
0x1800561b6  mov     [rbp+47h+var_80], r13d
0x1800561ba  mov     rax, [rcx]
0x1800561bd  lea     rdx, [rbp+47h+var_80]
0x1800561c1  mov     rax, [rax+40h]
0x1800561c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561ca  mov     ebx, eax
0x1800561cc  test    eax, eax
0x1800561ce  js      loc_180056795
0x1800561d4  mov     r12d, r13d
0x1800561d7  or      ecx, 0FFFFFFFFh
0x1800561da  mov     esi, ecx
0x1800561dc  mov     r14d, ecx
0x1800561df  xor     eax, eax
0x1800561e1  mov     edi, eax
0x1800561e3  cmp     edi, [rbp+47h+var_80]
0x1800561e6  jge     loc_1800566B4
0x1800561ec  mov     [rbp+47h+var_98], rax
0x1800561f0  mov     rcx, [rbp+47h+var_B8]
0x1800561f4  mov     rax, [rcx]
0x1800561f7  lea     r8, [rbp+47h+var_98]
0x1800561fb  mov     edx, edi
0x1800561fd  mov     rax, [rax+38h]
0x180056201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056206  mov     ebx, eax
0x180056208  xor     eax, eax
0x18005620a  test    ebx, ebx
0x18005620c  js      loc_180056536
0x180056212  mov     rcx, [rbp+47h+var_98]
0x180056216  test    rcx, rcx
0x180056219  jz      loc_1800566AA
0x18005621f  mov     [rbp+47h+var_70], eax
0x180056222  mov     rax, [rcx]
0x180056225  lea     rdx, [rbp+47h+var_70]
0x180056229  mov     rax, [rax+50h]
0x18005622d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056232  mov     ebx, eax
0x180056234  test    eax, eax
0x180056236  js      loc_180056536
0x18005623c  cmp     [rbp+47h+var_70], 1
0x180056240  jnz     loc_180056504
0x180056246  mov     rdx, [rbp+47h+var_98]
0x18005624a  lea     rcx, [rbp+47h+var_90]
0x18005624e  call    ??0?$CComQIPtr@UIXMLDOMElement@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>::CComQIPtr<IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>(IUnknown *)
0x180056253  nop
0x180056254  xor     eax, eax
0x180056256  cmp     [rbp+47h+var_90], rax
0x18005625a  jz      loc_18005666A
0x180056260  mov     [rbp+47h+var_88], rax
0x180056264  mov     rcx, [rbp+47h+var_98]
0x180056268  mov     rax, [rcx]
0x18005626b  lea     rdx, [rbp+47h+var_88]
0x18005626f  mov     rax, [rax+138h]
0x180056276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005627b  mov     ebx, eax
0x18005627d  test    eax, eax
0x18005627f  js      loc_180056521
0x180056285  cmp     eax, 1
0x180056288  jnz     short loc_1800562FB
0x18005628a  lea     rdx, word_1800884E0
0x180056291  lea     rcx, [rbp+47h+var_88]
0x180056295  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18005629a  mov     rdx, [rbp+47h+var_88]
0x18005629e  test    rdx, rdx
0x1800562a1  jnz     short loc_1800562FF
0x1800562a3  xor     ecx, ecx; bstrString
0x1800562a5  call    cs:__imp_SysFreeString
0x1800562ab  nop
0x1800562ac  lea     rcx, [rbp+47h+var_90]
0x1800562b0  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800562b5  nop
0x1800562b6  lea     rcx, [rbp+47h+var_98]
0x1800562ba  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800562bf  nop
0x1800562c0  lea     rcx, [rbp+47h+var_B8]
0x1800562c4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800562c9  nop
0x1800562ca  lea     rcx, [rbp+47h+var_B0]
0x1800562ce  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> const *>::Reset(void)
0x1800562d3  nop
0x1800562d4  lea     rcx, [rbp+47h+var_A8]
0x1800562d8  call    ?Reset@?$TGenericSP@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Vector@VCComBSTR@ATL@@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *>::Reset(void)
0x1800562dd  nop
0x1800562de  lea     rcx, [rbp+47h+var_A0]
0x1800562e2  call    ?Reset@?$TGenericSP@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@V?$TAutoPtr@U?$Map@VCComBSTR@ATL@@V12@$0BJ@@CompatibilityMarkupProcessorImpl@@@NCoreLibrary@@PEAU12@$0A@PEBU12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>,NCoreLibrary::TAutoPtr<CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25>>,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,0,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> const *>::Reset(void)
0x1800562e7  nop
0x1800562e8  lea     rcx, [rbp+47h+var_C0]
0x1800562ec  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800562f1  mov     ebx, 8007000Eh
0x1800562f6  jmp     loc_1800567C7
0x1800562fb  mov     rdx, [rbp+47h+var_88]
0x1800562ff  mov     rax, rdx
0x180056302  mov     r9, [r15+0E8h]
0x180056309  sub     r9, rdx
0x18005630c  movzx   r8d, word ptr [rax]
0x180056310  movzx   ecx, word ptr [rax+r9]
0x180056315  sub     r8d, ecx
0x180056318  jnz     short loc_180056322
0x18005631a  add     rax, 2
0x18005631e  test    ecx, ecx
0x180056320  jnz     short loc_18005630C
0x180056322  test    r8d, r8d
0x180056325  jnz     loc_18005648E
0x18005632b  xor     r14d, r14d
0x18005632e  mov     [rbp+47h+bstrString], r14
0x180056332  mov     rcx, [rbp+47h+var_98]
0x180056336  mov     rax, [rcx]
0x180056339  lea     rdx, [rbp+47h+bstrString]
0x18005633d  mov     rax, [rax+148h]
0x180056344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056349  mov     ebx, eax
0x18005634b  mov     rcx, [rbp+47h+bstrString]; bstrString
0x18005634f  test    eax, eax
0x180056351  js      loc_18005660B
0x180056357  test    rcx, rcx
0x18005635a  jz      loc_180056606
0x180056360  cmp     [rcx], r14w
0x180056364  jz      loc_180056606
0x18005636a  mov     rax, rcx
0x18005636d  mov     r9, [r15+0F8h]
0x180056374  sub     r9, rcx
0x180056377  movzx   r8d, word ptr [rax]
0x18005637b  movzx   edx, word ptr [rax+r9]
0x180056380  sub     r8d, edx
0x180056383  jnz     short loc_18005638D
0x180056385  add     rax, 2
0x180056389  test    edx, edx
0x18005638b  jnz     short loc_180056377
0x18005638d  test    r8d, r8d
0x180056390  jnz     short loc_180056401
0x180056392  mov     [rbp+47h+arg_8], r14b
0x180056396  mov     rax, [rbp+47h+var_60]
0x18005639a  mov     rcx, [rbp+47h+var_68]
0x18005639e  mov     r8, [rbp+47h+var_58]
0x1800563a2  lea     rdx, [rbp+47h+arg_8]
0x1800563a6  mov     [rsp+48h], rdx
0x1800563ab  mov     byte ptr [rsp+110h+var_D0], r13b
0x1800563b0  mov     qword ptr [rsp+110h+var_D8], rax
0x1800563b5  mov     [rsp+110h+var_E0], rcx
0x1800563ba  mov     rax, [rbp+47h+arg_18]
0x1800563be  mov     [rsp+110h+var_E8], rax
0x1800563c3  mov     [rsp+110h+var_F0], r8
0x1800563c8  mov     r9, [rbp+47h+var_78]
0x1800563cc  mov     r8, [rbp+47h+arg_10]
0x1800563d0  mov     rdx, [rbp+47h+var_90]
0x1800563d4  mov     rcx, r15
0x1800563d7  call    ?ProcessChoiceElement@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@1PEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@2PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@_NPEA_N@Z; CompatibilityMarkupProcessorImpl::ProcessChoiceElement(IXMLDOMElement *,IXMLDOMNode *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,bool,bool *)
0x1800563dc  mov     ebx, eax
0x1800563de  test    eax, eax
0x1800563e0  js      loc_180056516
0x1800563e6  inc     r12d
0x1800563e9  test    r13b, r13b
0x1800563ec  jnz     loc_18005647F
0x1800563f2  cmp     [rbp+47h+arg_8], r14b
0x1800563f6  jz      loc_18005647F
0x1800563fc  mov     r13b, 1
0x1800563ff  jmp     short loc_18005647F
0x180056401  mov     rax, rcx
0x180056404  mov     r9, [r15+100h]
0x18005640b  sub     r9, rcx
0x18005640e  movzx   r8d, word ptr [rax]
0x180056412  movzx   edx, word ptr [rax+r9]
0x180056417  sub     r8d, edx
0x18005641a  jnz     short loc_180056424
0x18005641c  add     rax, 2
0x180056420  test    edx, edx
0x180056422  jnz     short loc_18005640E
0x180056424  test    r8d, r8d
0x180056427  jnz     loc_1800565A5
0x18005642d  cmp     esi, 0FFFFFFFFh
0x180056430  jnz     loc_180056544
0x180056436  mov     rax, [rbp+47h+var_60]
0x18005643a  mov     rcx, [rbp+47h+var_68]
0x18005643e  mov     r8, [rbp+47h+var_58]
0x180056442  mov     byte ptr [rsp+110h+var_D0], r13b
0x180056447  mov     qword ptr [rsp+110h+var_D8], rax
0x18005644c  mov     [rsp+110h+var_E0], rcx
0x180056451  mov     rax, [rbp+47h+arg_18]
0x180056455  mov     [rsp+110h+var_E8], rax
0x18005645a  mov     [rsp+110h+var_F0], r8
0x18005645f  mov     r9, [rbp+47h+var_78]
0x180056463  mov     r8, [rbp+47h+arg_10]
0x180056467  mov     rdx, [rbp+47h+var_90]
0x18005646b  mov     rcx, r15
0x18005646e  call    ?ProcessFallbackElement@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMNode@@1PEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@2PEAU?$Vector@VCComBSTR@ATL@@$0BJ@@1@PEAU?$Map@VCComBSTR@ATL@@U?$Vector@VCComBSTR@ATL@@$0DC@@CompatibilityMarkupProcessorImpl@@$0BJ@@1@_N@Z; CompatibilityMarkupProcessorImpl::ProcessFallbackElement(IXMLDOMElement *,IXMLDOMNode *,IXMLDOMNode *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,50>,25> *,bool)
0x180056473  mov     ebx, eax
0x180056475  test    eax, eax
0x180056477  js      loc_180056516
0x18005647d  mov     esi, edi
0x18005647f  mov     rcx, [rbp+47h+bstrString]; bstrString
0x180056483  call    cs:__imp_SysFreeString
0x180056489  mov     r14d, edi
0x18005648c  jmp     short loc_1800564EF
0x18005648e  mov     r8, [rbp+47h+var_68]
0x180056492  mov     rcx, r15
0x180056495  call    ?EvaluateNamespaceURI@CompatibilityMarkupProcessorImpl@@AEAA?AW4Enum@NodeDisposition@@PEAGPEBU?$Vector@VCComBSTR@ATL@@$0BJ@@1@@Z; CompatibilityMarkupProcessorImpl::EvaluateNamespaceURI(ushort *,CompatibilityMarkupProcessorImpl::Vector<ATL::CComBSTR,25> const *)
0x18005649a  test    eax, 0FFFFFFFDh
0x18005649f  jz      loc_180056610
0x1800564a5  cmp     eax, 1
0x1800564a8  jnz     short loc_1800564EF
0x1800564aa  mov     rax, [rbp+47h+var_60]
0x1800564ae  mov     [rsp+110h+var_E8], rax
0x1800564b3  mov     rax, [rbp+47h+arg_18]
0x1800564b7  mov     [rsp+110h+var_F0], rax
0x1800564bc  mov     r9, [rbp+47h+var_58]
  ... truncated ...
```
