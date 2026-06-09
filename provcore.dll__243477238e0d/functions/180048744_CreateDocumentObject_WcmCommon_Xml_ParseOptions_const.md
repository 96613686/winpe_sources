# CreateDocumentObject(WcmCommon::Xml::ParseOptions const &)

- ea: `0x180048744`
- end: `0x180048934`
- name: `?CreateDocumentObject@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument3@MSXML2@@$1?_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEBUParseOptions@Xml@WcmCommon@@@Z`
- size: `496`
- prototype: `_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument3,&_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60> > *__fastcall(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument3,&_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60> > *result, const WcmCommon::Xml::ParseOptions *Options)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049634`
- `0x18004977c`
- `0x180049910`
- `0x180049f04`

## callees

- `0x18000b1e4`
- `0x18000b2f4`
- `0x1800471d0`
- `0x18004733c`
- `0x180047dac`
- `0x180048744`
- `0x18004a83c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180048839`
- `OLEAUT32!__imp_VariantClear` at `0x18004887e`
- `OLEAUT32!__imp_VariantClear` at `0x1800488e9`
- `OLEAUT32!__imp_VariantClear` at `0x180048839`
- `OLEAUT32!__imp_VariantClear` at `0x18004887e`
- `OLEAUT32!__imp_VariantClear` at `0x1800488e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004879a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004879a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *__fastcall CreateDocumentObject(
        ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *result,
        const WcmCommon::Xml::ParseOptions *Options)
{
  int Instance; // eax
  MSXML2::IXMLDOMParseError *v5; // rbx
  HRESULT v6; // eax
  MSXML2::IXMLDOMParseError *v7; // rbx
  HRESULT v8; // eax
  MSXML2::IXMLDOMDocument2 *v9; // rbx
  _bstr_t v10; // rax
  MSXML2::IXMLDOMDocument2 *v11; // rbx
  _bstr_t v12; // rax
  MSXML2::IXMLDOMParseError *v13; // rax
  MSXML2::IXMLDOMDocument2 *v14; // rbx
  _bstr_t v15; // rax
  _variant_t value; // [rsp+38h] [rbp-18h] BYREF
  _bstr_t v18; // [rsp+90h] [rbp+40h] BYREF

  result->p = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(result);
  result->p = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               0x17u,
               &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
               (LPVOID *)&result->p);
  if ( Instance < 0 )
    _com_raise_error(Instance, 0);
  v5 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)result);
  v6 = v5->__vftable[4].get_errorCode(v5, 0);
  if ( v6 < 0 )
    _com_issue_errorex(v6, v5, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v7 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)result);
  v8 = v7->__vftable[4].get_linepos(v7, 0);
  if ( v8 < 0 )
    _com_issue_errorex(v8, v7, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v9 = (MSXML2::IXMLDOMDocument2 *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)result);
  value.vt = 2;
  value.iVal = -1;
  _bstr_t::_bstr_t(&v18, L"NewParser");
  MSXML2::IXMLDOMDocument2::setProperty(v9, v10, &value);
  VariantClear(&value);
  if ( !Options->ProhibitDTD )
  {
    v11 = (MSXML2::IXMLDOMDocument2 *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)result);
    value.vt = 2;
    value.iVal = 0;
    _bstr_t::_bstr_t(&v18, L"ProhibitDTD");
    MSXML2::IXMLDOMDocument2::setProperty(v11, v12, &value);
    VariantClear(&value);
  }
  if ( Options->PreserveWhitespace )
  {
    v13 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)result);
    ((void (__fastcall *)(MSXML2::IXMLDOMParseError *, __int64))v13->__vftable[5].Release)(v13, 0xFFFFFFFFLL);
  }
  if ( Options->PopulateDefaultElementValues )
  {
    v14 = (MSXML2::IXMLDOMDocument2 *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->((_com_ptr_t<_com_IIID<MSXML2::IXMLDOMParseError,&_GUID_3efaa426_272f_11d2_836f_0000f87a7782> > *)result);
    value.vt = 2;
    value.iVal = -1;
    _bstr_t::_bstr_t(&v18, L"PopulateElementDefaultValues");
    MSXML2::IXMLDOMDocument2::setProperty(v14, v15, &value);
    VariantClear(&value);
  }
  return result;
}

```

## disassembly

```asm
0x180048744  mov     [rsp-28h+arg_8], rbx
0x180048749  mov     [rsp-28h+spDoc], rcx
0x18004874e  push    rbp
0x18004874f  push    rsi
0x180048750  push    rdi
0x180048751  push    r12
0x180048753  push    r15
0x180048755  mov     rbp, rsp
0x180048758  sub     rsp, 50h
0x18004875c  mov     rsi, Options
0x18004875f  mov     rdi, rcx
0x180048762  mov     [rbp+var_20], 0
0x180048769  xor     eax, eax
0x18004876b  mov     [rcx], rax
0x18004876e  mov     [rbp+var_20], 1
0x180048775  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004877a  mov     qword ptr [rdi], 0
0x180048781  mov     [rsp+50h+ppv], rdi; ppv
0x180048786  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x18004878d  xor     edx, edx; pUnkOuter
0x18004878f  lea     r8d, [Options+17h]; dwClsContext
0x180048793  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18004879a  call    cs:__imp_CoCreateInstance
0x1800487a0  test    eax, eax
0x1800487a2  js      loc_180048918
0x1800487a8  mov     rcx, rdi; this
0x1800487ab  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800487b0  mov     rbx, rax
0x1800487b3  mov     rcx, [rax]
0x1800487b6  xor     edx, edx
0x1800487b8  mov     rax, [rcx+1F8h]
0x1800487bf  mov     rcx, rbx
0x1800487c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487c7  test    eax, eax
0x1800487c9  js      loc_180048922
0x1800487cf  mov     rcx, rdi; this
0x1800487d2  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800487d7  mov     rbx, rax
0x1800487da  mov     rcx, [rax]
0x1800487dd  xor     edx, edx
0x1800487df  mov     rax, [rcx+220h]
0x1800487e6  mov     rcx, rbx
0x1800487e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487ee  test    eax, eax
0x1800487f0  js      loc_180048906
0x1800487f6  mov     rcx, rdi; this
0x1800487f9  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800487fe  mov     rbx, rax
0x180048801  mov     r12d, 2
0x180048807  mov     word ptr [rbp+value.___u0], r12w
0x18004880c  or      r15d, 0FFFFFFFFh
0x180048810  mov     word ptr [rbp+value.___u0+8], r15w
0x180048815  lea     Options, aNewparser; "NewParser"
0x18004881c  lea     rcx, [rbp+arg_10]; this
0x180048820  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180048825  lea     r8, [rbp+value]; value
0x180048829  mov     Options, rax; name
0x18004882c  mov     rcx, rbx; this
0x18004882f  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x180048834  nop
0x180048835  lea     rcx, [rbp+value]; pvarg
0x180048839  call    cs:__imp_VariantClear
0x18004883f  cmp     byte ptr [rsi], 0
0x180048842  jnz     short loc_180048884
0x180048844  mov     rcx, rdi; this
0x180048847  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004884c  mov     rbx, rax
0x18004884f  mov     word ptr [rbp+value.___u0], r12w
0x180048854  xor     ecx, ecx
0x180048856  mov     word ptr [rbp+value.___u0+8], cx
0x18004885a  lea     Options, aProhibitdtd; "ProhibitDTD"
0x180048861  lea     rcx, [rbp+arg_10]; this
0x180048865  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004886a  lea     r8, [rbp+value]; value
0x18004886e  mov     Options, rax; name
0x180048871  mov     rcx, rbx; this
0x180048874  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x180048879  nop
0x18004887a  lea     rcx, [rbp+value]; pvarg
0x18004887e  call    cs:__imp_VariantClear
0x180048884  cmp     byte ptr [rsi+1], 0
0x180048888  jz      short loc_1800488AA
0x18004888a  mov     rcx, rdi; this
0x18004888d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180048892  mov     r8, rax
0x180048895  mov     rcx, [rax]
0x180048898  mov     edx, r15d
0x18004889b  mov     rax, [rcx+240h]
0x1800488a2  mov     rcx, r8
0x1800488a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488aa  cmp     byte ptr [rsi+2], 0
0x1800488ae  jz      short loc_1800488EF
0x1800488b0  mov     rcx, rdi; this
0x1800488b3  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMNodeList@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x1800488b8  mov     rbx, rax
0x1800488bb  mov     word ptr [rbp+value.___u0], r12w
0x1800488c0  mov     word ptr [rbp+value.___u0+8], r15w
0x1800488c5  lea     Options, aPopulateelemen; "PopulateElementDefaultValues"
0x1800488cc  lea     rcx, [rbp+arg_10]; this
0x1800488d0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800488d5  lea     r8, [rbp+value]; value
0x1800488d9  mov     Options, rax; name
0x1800488dc  mov     rcx, rbx; this
0x1800488df  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x1800488e4  nop
0x1800488e5  lea     rcx, [rbp+value]; pvarg
0x1800488e9  call    cs:__imp_VariantClear
0x1800488ef  mov     rax, rdi
0x1800488f2  mov     rbx, [rsp+50h+arg_8]
0x1800488fa  add     rsp, 50h
0x1800488fe  pop     r15
0x180048900  pop     r12
0x180048902  pop     rdi
0x180048903  pop     rsi
0x180048904  pop     rbp
0x180048905  retn
0x180048906  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18004890d  mov     Options, rbx; punk
0x180048910  mov     ecx, eax; hr
0x180048912  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180048918  xor     edx, edx; perrinfo
0x18004891a  mov     ecx, eax; hr
0x18004891c  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180048922  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180048929  mov     Options, rbx; punk
0x18004892c  mov     ecx, eax; hr
0x18004892e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
