# WcmCommon::Xml::Document::AddSchema(std::shared_ptr<WcmCommon::Xml::Document> const &)

- ea: `0x180047e5c`
- end: `0x18004818e`
- name: `?AddSchema@Document@Xml@WcmCommon@@QEAAXAEBV?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@@Z`
- size: `818`
- prototype: `void __fastcall(WcmCommon::Xml::Document *this, const std::shared_ptr<WcmCommon::Xml::Document> *SchemaDoc)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b480`

## callees

- `0x180002790`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x1800471bc`
- `0x1800471d0`
- `0x18004733c`
- `0x180047b74`
- `0x180047c9c`
- `0x180047dac`
- `0x180047e5c`
- `0x180048fc8`
- `0x180049150`
- `0x180049524`
- `0x180049a8c`
- `0x18004a2b0`
- `0x18004a428`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180047f4d`
- `OLEAUT32!__imp_VariantInit` at `0x180047f4d`
- `OLEAUT32!__imp_VariantClear` at `0x180048051`
- `OLEAUT32!__imp_VariantClear` at `0x1800480fa`
- `OLEAUT32!__imp_VariantClear` at `0x180048109`
- `OLEAUT32!__imp_VariantClear` at `0x180048051`
- `OLEAUT32!__imp_VariantClear` at `0x1800480fa`
- `OLEAUT32!__imp_VariantClear` at `0x180048109`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047fdf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047fdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall WcmCommon::Xml::Document::AddSchema(
        WcmCommon::Xml::Document *this,
        const std::shared_ptr<WcmCommon::Xml::Document> *SchemaDoc)
{
  MSXML2::IXMLDOMDocument *v4; // rax
  _com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *v5; // rax
  MSXML2::IXMLDOMNode *v6; // rax
  _com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *v7; // rax
  MSXML2::IXMLDOMNamedNodeMap *v8; // rbx
  _bstr_t v9; // rax
  MSXML2::IXMLDOMParseError *v10; // rbx
  HRESULT v11; // eax
  int Instance; // eax
  MSXML2::IXMLDOMParseError *v13; // rbx
  bool v14; // r8
  HRESULT v15; // eax
  bool v16; // r8
  HRESULT v17; // eax
  MSXML2::IXMLDOMSchemaCollection *m_pInterface; // rbx
  MSXML2::IXMLDOMNode *v19; // rax
  _bstr_t *v20; // rax
  _bstr_t v21; // [rsp+30h] [rbp-98h] BYREF
  _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60> > targetNsNode; // [rsp+38h] [rbp-90h] BYREF
  _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60> > result; // [rsp+40h] [rbp-88h] BYREF
  _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNamedNodeMap,&_GUID_2933bf83_7b36_11d2_b20e_00c04f983e60> > v24; // [rsp+48h] [rbp-80h] BYREF
  _variant_t var; // [rsp+60h] [rbp-68h] BYREF
  _com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&_GUID_373984c8_b845_449b_91e7_45ac83036ade> > schemas; // [rsp+80h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-40h] BYREF
  _variant_t varSchemas; // [rsp+A0h] [rbp-28h] BYREF

  targetNsNode.m_pInterface = 0;
  v4 = (MSXML2::IXMLDOMDocument *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)SchemaDoc->_Ptr->m_details._Ptr);
  v5 = (_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)MSXML2::IXMLDOMDocument::GetdocumentElement(v4, &result);
  v6 = (MSXML2::IXMLDOMNode *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(v5);
  v7 = (_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)MSXML2::IXMLDOMNode::Getattributes(v6, &v24);
  v8 = (MSXML2::IXMLDOMNamedNodeMap *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(v7);
  _bstr_t::_bstr_t(&v21, L"targetNamespace");
  MSXML2::IXMLDOMNamedNodeMap::getNamedItem(v8, &targetNsNode, v9);
  if ( v24.m_pInterface )
    v24.m_pInterface->Release(v24.m_pInterface);
  if ( result.m_pInterface )
    result.m_pInterface->Release(result.m_pInterface);
  schemas.m_pInterface = 0;
  v10 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)this->m_details._Ptr);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v11 = v10->__vftable[5].get_errorCode(v10, (int *)&pvarg);
  if ( v11 < 0 )
    _com_issue_errorex(v11, v10, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60);
  varSchemas = (_variant_t)pvarg;
  if ( (unsigned __int16)_mm_cvtsi128_si32((__m128i)pvarg.0) == 1 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&schemas);
    schemas.m_pInterface = 0;
    Instance = CoCreateInstance(
                 &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
                 0,
                 0x17u,
                 &GUID_373984c8_b845_449b_91e7_45ac83036ade,
                 (LPVOID *)&schemas.m_pInterface);
    if ( Instance < 0 )
      _com_raise_error(Instance, 0);
    v13 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)this->m_details._Ptr);
    _variant_t::_variant_t((_variant_t *)&pvarg, schemas.m_pInterface, v14);
    var = (_variant_t)pvarg;
    v15 = v13->__vftable[5].get_url(v13, (wchar_t **)&var);
    if ( v15 < 0 )
      _com_issue_errorex(v15, v13, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60);
    VariantClear(&pvarg);
  }
  else
  {
    v21.m_Data = 0;
    v17 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&__s_GUID const _GUID_373984c8_b845_449b_91e7_45ac83036ade>>::QueryStdInterfaces(
            (_com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&_GUID_373984c8_b845_449b_91e7_45ac83036ade> > *)&v21,
            &varSchemas);
    if ( (int)(v17 + 0x80000000) >= 0 && v17 != -2147467262 )
      _com_issue_error(v17);
    _com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&__s_GUID const _GUID_373984c8_b845_449b_91e7_45ac83036ade>>::operator=(
      &schemas,
      (_com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&_GUID_373984c8_b845_449b_91e7_45ac83036ade> > *)&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&v21);
  }
  try
  {
    m_pInterface = schemas.m_pInterface;
    if ( !schemas.m_pInterface )
      _com_issue_error(-2147467261);
    _variant_t::_variant_t(&var, SchemaDoc->_Ptr->m_details._Ptr->Impl.m_pInterface, v16);
    v19 = (MSXML2::IXMLDOMNode *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)&targetNsNode);
    v20 = MSXML2::IXMLDOMNode::Gettext(v19, (_bstr_t *)&result);
    MSXML2::IXMLDOMSchemaCollection::add(m_pInterface, (_bstr_t)v20, &var);
  }
  catch ( _com_error )
  {
    throw;
  }
  VariantClear(&var);
  VariantClear(&varSchemas);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&schemas);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&targetNsNode);
}

```

## disassembly

```asm
0x180047e5c  mov     [rsp+arg_10], rbx
0x180047e61  mov     [rsp+arg_18], rsi
0x180047e66  push    rdi
0x180047e67  sub     rsp, 0C0h
0x180047e6e  mov     rax, cs:__security_cookie
0x180047e75  xor     rax, rsp
0x180047e78  mov     [rsp+0C8h+var_10], rax
0x180047e80  mov     rsi, SchemaDoc
0x180047e83  mov     rdi, this
0x180047e86  mov     [rsp+0C8h+targetNsNode.m_pInterface], 0
0x180047e8f  mov     this, [SchemaDoc]
0x180047e92  mov     this, [this]; this
0x180047e95  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180047e9a  lea     SchemaDoc, [rsp+0C8h+result]; result
0x180047e9f  mov     this, rax; this
0x180047ea2  call    ?GetdocumentElement@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetdocumentElement(void)
0x180047ea7  nop
0x180047ea8  mov     this, rax; this
0x180047eab  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180047eb0  lea     SchemaDoc, [rsp+0C8h+var_80]; result
0x180047eb5  mov     this, rax; this
0x180047eb8  call    ?Getattributes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNamedNodeMap@MSXML2@@$1?_GUID_2933bf83_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMNode::Getattributes(void)
0x180047ebd  nop
0x180047ebe  mov     this, rax; this
0x180047ec1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180047ec6  mov     rbx, rax
0x180047ec9  lea     SchemaDoc, aTargetnamespac; "targetNamespace"
0x180047ed0  lea     this, [rsp+0C8h+var_98]; this
0x180047ed5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180047eda  mov     r8, rax; name
0x180047edd  lea     SchemaDoc, [rsp+0C8h+targetNsNode]; result
0x180047ee2  mov     this, rbx; this
0x180047ee5  call    ?getNamedItem@IXMLDOMNamedNodeMap@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML2::IXMLDOMNamedNodeMap::getNamedItem(_bstr_t)
0x180047eea  nop
0x180047eeb  mov     this, [rsp+0C8h+var_80.m_pInterface]
0x180047ef0  test    this, this
0x180047ef3  jz      short loc_180047F02
0x180047ef5  mov     rax, [this]
0x180047ef8  mov     rax, [rax+10h]
0x180047efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f01  nop
0x180047f02  mov     this, [rsp+0C8h+result.m_pInterface]
0x180047f07  test    this, this
0x180047f0a  jz      short loc_180047F19
0x180047f0c  mov     rax, [this]
0x180047f0f  mov     rax, [rax+10h]
0x180047f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f18  nop
0x180047f19  mov     [rsp+0C8h+schemas.m_pInterface], 0
0x180047f25  mov     this, [rdi]; this
0x180047f28  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180047f2d  mov     rbx, rax
0x180047f30  xorps   xmm0, xmm0
0x180047f33  xor     eax, eax
0x180047f35  movups  xmmword ptr [rsp+0C8h+pvarg.___u0], xmm0
0x180047f3d  mov     [rsp+0C8h+pvarg.pRecInfo], rax
0x180047f45  lea     this, [rsp+0C8h+pvarg]; pvarg
0x180047f4d  call    cs:__imp_VariantInit
0x180047f53  mov     this, [rbx]
0x180047f56  mov     rax, [this+268h]
0x180047f5d  lea     SchemaDoc, [rsp+0C8h+pvarg]
0x180047f65  mov     this, rbx
0x180047f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f6d  test    eax, eax
0x180047f6f  js      loc_180048158
0x180047f75  movups  xmm1, xmmword ptr [rsp+0C8h+pvarg.___u0]
0x180047f7d  movups  xmmword ptr [rsp+0C8h+varSchemas.___u0], xmm1
0x180047f85  movsd   xmm0, [rsp+0C8h+pvarg.pRecInfo]
0x180047f8e  movsd   [rsp+0C8h+varSchemas.pRecInfo], xmm0
0x180047f97  movd    eax, xmm1
0x180047f9b  cmp     ax, 1
0x180047f9f  jnz     loc_180048059
0x180047fa5  lea     this, [rsp+0C8h+schemas]; this
0x180047fad  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047fb2  mov     [rsp+0C8h+schemas.m_pInterface], 0
0x180047fbe  lea     rax, [rsp+0C8h+schemas]
0x180047fc6  mov     [rsp+0C8h+ppv], rax; ppv
0x180047fcb  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x180047fd2  xor     edx, edx; pUnkOuter
0x180047fd4  lea     r8d, [SchemaDoc+17h]; dwClsContext
0x180047fd8  lea     this, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x180047fdf  call    cs:__imp_CoCreateInstance
0x180047fe5  test    eax, eax
0x180047fe7  js      loc_18004816A
0x180047fed  mov     this, [rdi]; this
0x180047ff0  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180047ff5  mov     rbx, rax
0x180047ff8  mov     SchemaDoc, [rsp+0C8h+schemas.m_pInterface]; pSrc
0x180048000  lea     this, [rsp+0C8h+pvarg]; this
0x180048008  call    ??0_variant_t@@QEAA@PEAUIDispatch@@_N@Z; _variant_t::_variant_t(IDispatch *,bool)
0x18004800d  nop
0x18004800e  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg.___u0]
0x180048016  movaps  xmmword ptr [rsp+0C8h+var.___u0], xmm0
0x18004801b  movsd   xmm1, [rsp+0C8h+pvarg.pRecInfo]
0x180048024  movsd   [rsp+0C8h+var.pRecInfo], xmm1
0x18004802a  mov     this, [rbx]
0x18004802d  mov     rax, [this+270h]
0x180048034  lea     SchemaDoc, [rsp+0C8h+var]
0x180048039  mov     this, rbx
0x18004803c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048041  test    eax, eax
0x180048043  js      loc_180048174
0x180048049  lea     this, [rsp+0C8h+pvarg]; pvarg
0x180048051  call    cs:__imp_VariantClear
0x180048057  jmp     short loc_1800480A8
0x180048059  mov     [rsp+0C8h+var_98.m_Data], 0
0x180048062  lea     SchemaDoc, [rsp+0C8h+varSchemas]; varSrc
0x18004806a  lea     this, [rsp+0C8h+var_98]; this
0x18004806f  call    ?QueryStdInterfaces@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMSchemaCollection@MSXML2@@$1?_GUID_373984c8_b845_449b_91e7_45ac83036ade@@3U__s_GUID@@B@@@@AEAAJAEBV_variant_t@@@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&__s_GUID const _GUID_373984c8_b845_449b_91e7_45ac83036ade>>::QueryStdInterfaces(_variant_t const &)
0x180048074  mov     edx, 80000000h
0x180048079  lea     ecx, [rax+SchemaDoc]
0x18004807c  test    edx, ecx
0x18004807e  jnz     short loc_18004808B
0x180048080  cmp     eax, 80004002h
0x180048085  jnz     loc_180048186
0x18004808b  lea     SchemaDoc, [rsp+0C8h+var_98]; cp
0x180048090  lea     this, [rsp+0C8h+schemas]; this
0x180048098  call    ??4?$_com_ptr_t@V?$_com_IIID@UIXMLDOMSchemaCollection@MSXML2@@$1?_GUID_373984c8_b845_449b_91e7_45ac83036ade@@3U__s_GUID@@B@@@@QEAAAEAV0@$$QEAV0@@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&__s_GUID const _GUID_373984c8_b845_449b_91e7_45ac83036ade>>::operator=(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMSchemaCollection,&__s_GUID const _GUID_373984c8_b845_449b_91e7_45ac83036ade>> &&)
0x18004809d  lea     this, [rsp+0C8h+var_98]; this
0x1800480a2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800480a7  nop
0x1800480a8  mov     rbx, [rsp+0C8h+schemas.m_pInterface]
0x1800480b0  test    rbx, rbx
0x1800480b3  jz      loc_18004814D
0x1800480b9  mov     rax, [rsi]
0x1800480bc  mov     SchemaDoc, [rax]
0x1800480bf  mov     SchemaDoc, [SchemaDoc]; pSrc
0x1800480c2  lea     this, [rsp+0C8h+var]; this
0x1800480c7  call    ??0_variant_t@@QEAA@PEAUIDispatch@@_N@Z; _variant_t::_variant_t(IDispatch *,bool)
0x1800480cc  nop
0x1800480cd  lea     this, [rsp+0C8h+targetNsNode]; this
0x1800480d2  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800480d7  lea     SchemaDoc, [rsp+0C8h+result]; result
0x1800480dc  mov     this, rax; this
0x1800480df  call    ?Gettext@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Gettext(void)
0x1800480e4  lea     r8, [rsp+0C8h+var]; var
0x1800480e9  mov     SchemaDoc, rax; namespaceURI
0x1800480ec  mov     this, rbx; this
0x1800480ef  call    ?add@IXMLDOMSchemaCollection@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMSchemaCollection::add(_bstr_t,_variant_t const &)
0x1800480f4  nop
0x1800480f5  lea     this, [rsp+0C8h+var]; pvarg
0x1800480fa  call    cs:__imp_VariantClear
0x180048100  nop
0x180048101  lea     this, [rsp+0C8h+varSchemas]; pvarg
0x180048109  call    cs:__imp_VariantClear
0x18004810f  nop
0x180048110  lea     this, [rsp+0C8h+schemas]; this
0x180048118  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004811d  nop
0x18004811e  lea     this, [rsp+0C8h+targetNsNode]; this
0x180048123  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048128  mov     this, [rsp+0C8h+var_10]
0x180048130  xor     this, rsp; StackCookie
0x180048133  call    __security_check_cookie
0x180048138  lea     r11, [rsp+0C8h+var_8]
0x180048140  mov     rbx, [r11+20h]
0x180048144  mov     rsi, [r11+28h]
0x180048148  mov     rsp, r11
0x18004814b  pop     rdi
0x18004814c  retn
0x18004814d  mov     ecx, 80004003h; hr
0x180048152  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180048158  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18004815f  mov     SchemaDoc, rbx; punk
0x180048162  mov     ecx, eax; hr
0x180048164  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18004816a  xor     edx, edx; perrinfo
0x18004816c  mov     ecx, eax; hr
0x18004816e  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180048174  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18004817b  mov     SchemaDoc, rbx; punk
0x18004817e  mov     ecx, eax; hr
0x180048180  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180048186  mov     ecx, eax; hr
0x180048188  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
