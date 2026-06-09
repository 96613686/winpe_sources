# CryptXmlAddSecurityTokenReference

- ea: `0x180043f64`
- end: `0x1800447a7`
- name: `CryptXmlAddSecurityTokenReference`
- size: `2115`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180043ad8`

## callees

- `0x180007040`
- `0x18000e508`
- `0x18000efc4`
- `0x1800206a8`
- `0x18002e570`
- `0x1800434d0`
- `0x180043544`
- `0x180043f64`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043ff2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043ff2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800440ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800441aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18004424b`
- `OLEAUT32!__imp_SysFreeString` at `0x180044326`
- `OLEAUT32!__imp_SysFreeString` at `0x180044374`
- `OLEAUT32!__imp_SysFreeString` at `0x180044446`
- `OLEAUT32!__imp_SysFreeString` at `0x180044494`
- `OLEAUT32!__imp_SysFreeString` at `0x18004456f`
- `OLEAUT32!__imp_SysFreeString` at `0x180044633`
- `OLEAUT32!__imp_SysFreeString` at `0x18004473d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800440ea`
- `OLEAUT32!__imp_SysFreeString` at `0x1800441aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18004424b`
- `OLEAUT32!__imp_SysFreeString` at `0x180044326`
- `OLEAUT32!__imp_SysFreeString` at `0x180044374`
- `OLEAUT32!__imp_SysFreeString` at `0x180044446`
- `OLEAUT32!__imp_SysFreeString` at `0x180044494`
- `OLEAUT32!__imp_SysFreeString` at `0x18004456f`
- `OLEAUT32!__imp_SysFreeString` at `0x180044633`
- `OLEAUT32!__imp_SysFreeString` at `0x18004473d`
- `OLEAUT32!__imp_SysStringLen` at `0x180044719`
- `OLEAUT32!__imp_SysStringLen` at `0x180044719`
- `OLEAUT32!__imp_VariantInit` at `0x180043fbc`
- `OLEAUT32!__imp_VariantInit` at `0x180043fbc`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800446f2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800446f2`

## string_xrefs

- `0x1800442b1`: `wsse:SecurityTokenReference`
- `0x180044290`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd`
- `0x1800443b0`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd`
- `0x1800445ba`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509`
- `0x180044131`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' `

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CryptXmlAddSecurityTokenReference(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  HRESULT v6; // ebx
  LPVOID v7; // rbx
  __int64 (__fastcall *v8)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v9; // rax
  __int64 v10; // rdx
  BSTR *v11; // rdi
  BSTR v12; // rcx
  LPVOID v13; // rbx
  __int64 (__fastcall *v14)(LPVOID, __int64, VARIANTARG *); // rdi
  _variant_t *v15; // rax
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  BSTR *v20; // rdi
  BSTR v21; // rcx
  LPVOID v22; // rbx
  __int64 (__fastcall *v23)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  BSTR *v26; // rdi
  BSTR v27; // rcx
  LPVOID v28; // rdi
  __int64 (__fastcall *v29)(LPVOID, VARIANTARG *, __int64, __int64, __int64 *); // rsi
  _bstr_t *v30; // rax
  __int64 v31; // rbx
  _bstr_t *v32; // rax
  __int64 v33; // r8
  BSTR *v34; // rdi
  BSTR v35; // rcx
  BSTR *v36; // rdi
  BSTR v37; // rcx
  LPVOID v38; // rdi
  __int64 (__fastcall *v39)(LPVOID, VARIANTARG *, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rsi
  _bstr_t *v40; // rax
  __int64 v41; // rbx
  _bstr_t *v42; // rax
  __int64 v43; // r8
  BSTR *v44; // rdi
  BSTR v45; // rcx
  BSTR *v46; // rdi
  BSTR v47; // rcx
  __int64 v48; // rbx
  __int64 (__fastcall *v49)(__int64, __int64, VARIANTARG *); // rdi
  _variant_t *v50; // rax
  __int128 v51; // xmm6
  IRecordInfo *v52; // xmm7_8
  _bstr_t *v53; // rax
  __int64 v54; // rdx
  BSTR *v55; // rdi
  BSTR v56; // rcx
  __int64 v57; // rbx
  __int64 (__fastcall *v58)(__int64, __int64, VARIANTARG *); // rdi
  _variant_t *v59; // rax
  __int128 v60; // xmm6
  IRecordInfo *v61; // xmm7_8
  _bstr_t *v62; // rax
  __int64 v63; // rdx
  BSTR *v64; // rdi
  BSTR v65; // rcx
  UINT v66; // eax
  unsigned __int16 *v67; // rax
  const unsigned __int16 *v68; // rbx
  UINT v69; // eax
  void *Block; // [rsp+38h] [rbp-89h] BYREF
  __int64 v72; // [rsp+40h] [rbp-81h] BYREF
  BSTR bstr; // [rsp+48h] [rbp-79h] BYREF
  __int64 v74; // [rsp+50h] [rbp-71h] BYREF
  VARIANTARG v75; // [rsp+58h] [rbp-69h] BYREF
  __int64 v76; // [rsp+78h] [rbp-49h] BYREF
  __int64 (__fastcall ***v77)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-41h] BYREF
  __int64 v78; // [rsp+88h] [rbp-39h] BYREF
  void *v79; // [rsp+90h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-29h] BYREF
  VARIANTARG v81[2]; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v82; // [rsp+138h] [rbp+77h] BYREF
  LPVOID ppv; // [rsp+140h] [rbp+7Fh] BYREF

  v82 = a3;
  ppv = 0;
  v78 = 0;
  v74 = 0;
  v77 = 0;
  v72 = 0;
  v76 = 0;
  bstr = 0;
  LOWORD(v82) = 0;
  VariantInit(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = 1;
  *a4 = 0;
  v6 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 576LL))(ppv, 0xFFFFFFFFLL);
          if ( v6 >= 0 )
          {
            v7 = ppv;
            v8 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 520LL);
            v9 = _bstr_t::_bstr_t((_bstr_t *)&Block, a1);
            if ( *(_QWORD *)v9 )
              v10 = **(_QWORD **)v9;
            else
              v10 = 0;
            v6 = v8(v7, v10, &v82);
            v11 = (BSTR *)Block;
            if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v11 )
            {
              if ( *v11 )
              {
                SysFreeString(*v11);
                *v11 = 0;
              }
              v12 = v11[1];
              if ( v12 )
              {
                operator delete(v12);
                v11[1] = 0;
              }
              operator delete(v11);
            }
            if ( v6 >= 0 && (_WORD)v82 == 0xFFFF )
            {
              v13 = ppv;
              v14 = *(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)ppv + 640LL);
              v15 = _variant_t::_variant_t(
                      (_variant_t *)v81,
                      L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.or"
                       "g/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addr"
                       "essing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.x"
                       "sd' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' ");
              v16 = *(_OWORD *)v15;
              v17 = (IRecordInfo *)*((_QWORD *)v15 + 2);
              v18 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"SelectionNamespaces");
              if ( *(_QWORD *)v18 )
                v19 = **(_QWORD **)v18;
              else
                v19 = 0;
              *(_OWORD *)&v75.vt = v16;
              v75.pRecInfo = v17;
              v6 = v14(v13, v19, &v75);
              v20 = (BSTR *)Block;
              if ( Block )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v20 )
                {
                  if ( *v20 )
                  {
                    SysFreeString(*v20);
                    *v20 = 0;
                  }
                  v21 = v20[1];
                  if ( v21 )
                  {
                    operator delete(v21);
                    v20[1] = 0;
                  }
                  operator delete(v20);
                }
                Block = 0;
              }
              _variant_t::~_variant_t(v81);
              if ( v6 >= 0 )
              {
                v22 = ppv;
                v23 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 296LL);
                v24 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"//ds:KeyInfo");
                if ( *(_QWORD *)v24 )
                  v25 = **(_QWORD **)v24;
                else
                  v25 = 0;
                v6 = v23(v22, v25, &v78);
                v26 = (BSTR *)Block;
                if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v26 )
                {
                  if ( *v26 )
                  {
                    SysFreeString(*v26);
                    *v26 = 0;
                  }
                  v27 = v26[1];
                  if ( v27 )
                  {
                    operator delete(v27);
                    v26[1] = 0;
                  }
                  operator delete(v26);
                }
                if ( v6 >= 0 && v6 != 1 )
                {
                  v28 = ppv;
                  v29 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int64, __int64, __int64 *))(*(_QWORD *)ppv + 448LL);
                  v30 = _bstr_t::_bstr_t(
                          (_bstr_t *)&v79,
                          L"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd");
                  if ( *(_QWORD *)v30 )
                    v31 = **(_QWORD **)v30;
                  else
                    v31 = 0;
                  v32 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"wsse:SecurityTokenReference");
                  if ( *(_QWORD *)v32 )
                    v33 = **(_QWORD **)v32;
                  else
                    v33 = 0;
                  v75 = pvarg;
                  v6 = v29(v28, &v75, v33, v31, &v74);
                  v34 = (BSTR *)Block;
                  if ( Block )
                  {
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v34 )
                    {
                      if ( *v34 )
                      {
                        SysFreeString(*v34);
                        *v34 = 0;
                      }
                      v35 = v34[1];
                      if ( v35 )
                      {
                        operator delete(v35);
                        v34[1] = 0;
                      }
                      operator delete(v34);
                    }
                    Block = 0;
                  }
                  v36 = (BSTR *)v79;
                  if ( v79 && _InterlockedExchangeAdd((volatile signed __int32 *)v79 + 4, 0xFFFFFFFF) == 1 && v36 )
                  {
                    if ( *v36 )
                    {
                      SysFreeString(*v36);
                      *v36 = 0;
                    }
                    v37 = v36[1];
                    if ( v37 )
                    {
                      operator delete(v37);
                      v36[1] = 0;
                    }
                    operator delete(v36);
                  }
                  if ( v6 >= 0 )
                  {
                    v38 = ppv;
                    v39 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)ppv + 448LL);
                    v40 = _bstr_t::_bstr_t(
                            (_bstr_t *)&v79,
                            L"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd");
                    if ( *(_QWORD *)v40 )
                      v41 = **(_QWORD **)v40;
                    else
                      v41 = 0;
                    v42 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"wsse:Reference");
                    if ( *(_QWORD *)v42 )
                      v43 = **(_QWORD **)v42;
                    else
                      v43 = 0;
                    v75 = pvarg;
                    v6 = v39(v38, &v75, v43, v41, &v77);
                    v44 = (BSTR *)Block;
                    if ( Block )
                    {
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v44 )
                      {
                        if ( *v44 )
                        {
                          SysFreeString(*v44);
                          *v44 = 0;
                        }
                        v45 = v44[1];
                        if ( v45 )
                        {
                          operator delete(v45);
                          v44[1] = 0;
                        }
                        operator delete(v44);
                      }
                      Block = 0;
                    }
                    v46 = (BSTR *)v79;
                    if ( v79 && _InterlockedExchangeAdd((volatile signed __int32 *)v79 + 4, 0xFFFFFFFF) == 1 && v46 )
                    {
                      if ( *v46 )
                      {
                        SysFreeString(*v46);
                        *v46 = 0;
                      }
                      v47 = v46[1];
                      if ( v47 )
                      {
                        operator delete(v47);
                        v46[1] = 0;
                      }
                      operator delete(v46);
                    }
                    if ( v6 >= 0 )
                    {
                      v6 = (**v77)(v77, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v72);
                      if ( v6 >= 0 )
                      {
                        v48 = v72;
                        v49 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v72 + 360LL);
                        v50 = _variant_t::_variant_t((_variant_t *)v81, L"uuid-29801C2F-F26B-46AD-984B-AFAEFB545FF8");
                        v51 = *(_OWORD *)v50;
                        v52 = (IRecordInfo *)*((_QWORD *)v50 + 2);
                        v53 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"URI");
                        if ( *(_QWORD *)v53 )
                          v54 = **(_QWORD **)v53;
                        else
                          v54 = 0;
                        *(_OWORD *)&v75.vt = v51;
                        v75.pRecInfo = v52;
                        v6 = v49(v48, v54, &v75);
                        v55 = (BSTR *)Block;
                        if ( Block )
                        {
                          if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v55 )
                          {
                            if ( *v55 )
                            {
                              SysFreeString(*v55);
                              *v55 = 0;
                            }
                            v56 = v55[1];
                            if ( v56 )
                            {
                              operator delete(v56);
                              v55[1] = 0;
                            }
                            operator delete(v55);
                          }
                          Block = 0;
                        }
                        _variant_t::~_variant_t(v81);
                        if ( v6 >= 0 )
                        {
                          v57 = v72;
                          v58 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v72 + 360LL);
                          v59 = _variant_t::_variant_t(
                                  (_variant_t *)v81,
                                  L"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509");
                          v60 = *(_OWORD *)v59;
                          v61 = (IRecordInfo *)*((_QWORD *)v59 + 2);
                          v62 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"ValueType");
                          if ( *(_QWORD *)v62 )
                            v63 = **(_QWORD **)v62;
                          else
                            v63 = 0;
                          *(_OWORD *)&v75.vt = v60;
                          v75.pRecInfo = v61;
                          v6 = v58(v57, v63, &v75);
                          v64 = (BSTR *)Block;
                          if ( Block )
                          {
                            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v64 )
                            {
                              if ( *v64 )
                              {
                                SysFreeString(*v64);
                                *v64 = 0;
                              }
                              v65 = v64[1];
                              if ( v65 )
                              {
                                operator delete(v65);
                                v64[1] = 0;
                              }
                              operator delete(v64);
                            }
                            Block = 0;
                          }
                          _variant_t::~_variant_t(v81);
                          if ( v6 >= 0 )
                          {
                            v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v74 + 168LL))(
                                   v74,
                                   v72,
                                   0);
                            if ( v6 >= 0 )
                            {
                              v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v78 + 168LL))(
                                     v78,
                                     v74,
                                     0);
                              if ( v6 >= 0 )
                              {
                                v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v76);
                                if ( v6 >= 0 )
                                {
                                  v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v76 + 272LL))(v76, &bstr);
                                  if ( v6 >= 0 )
                                  {
                                    v66 = SysStringByteLen(bstr);
                                    v67 = (unsigned __int16 *)SafeHeapAlloc(v66 + 2LL);
                                    *a4 = v67;
                                    if ( v67 )
                                    {
                                      v68 = bstr;
                                      v69 = SysStringLen(bstr);
                                      v6 = StringCchCopyW(*a4, v69 + 1, v68);
                                    }
                                    else
                                    {
                                      v6 = -2147024882;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  _variant_t::~_variant_t(&pvarg);
  SysFreeString(bstr);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v76);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v72);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v77);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v74);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v78);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180043f64  mov     rax, rsp
0x180043f67  mov     [rax+8], rbx
0x180043f6b  mov     [rax+18h], r8
0x180043f6f  push    rbp
0x180043f70  push    rsi
0x180043f71  push    rdi
0x180043f72  push    r12
0x180043f74  push    r13
0x180043f76  push    r14
0x180043f78  push    r15
0x180043f7a  lea     rbp, [rax-5Fh]
0x180043f7e  sub     rsp, 0E0h
0x180043f85  movaps  xmmword ptr [rax-48h], xmm6
0x180043f89  movaps  xmmword ptr [rax-58h], xmm7
0x180043f8d  mov     r14, r9
0x180043f90  mov     rsi, rcx
0x180043f93  xor     r15d, r15d
0x180043f96  mov     [rbp+57h+arg_18], r15
0x180043f9a  mov     [rbp+57h+var_90], r15
0x180043f9e  mov     [rbp+57h+var_C8], r15
0x180043fa2  mov     [rbp+57h+var_98], r15
0x180043fa6  mov     [rsp+110h+var_D8], r15
0x180043fab  mov     [rbp+57h+var_A0], r15
0x180043faf  mov     [rbp+57h+bstr], r15
0x180043fb3  mov     word ptr [rbp+57h+arg_10], r15w
0x180043fb8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043fbc  call    cs:__imp_VariantInit
0x180043fc2  nop
0x180043fc3  lea     eax, [r15+3]
0x180043fc7  mov     word ptr [rbp+57h+pvarg], ax
0x180043fcb  mov     dword ptr [rbp+57h+pvarg+8], 1
0x180043fd2  mov     [r14], r15
0x180043fd5  lea     rax, [rbp+57h+arg_18]
0x180043fd9  mov     [rsp+110h+ppv], rax; ppv
0x180043fde  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180043fe5  xor     edx, edx; pUnkOuter
0x180043fe7  lea     r8d, [r15+17h]; dwClsContext
0x180043feb  lea     rcx, CLSID_DOMDocument60; rclsid
0x180043ff2  call    cs:__imp_CoCreateInstance
0x180043ff8  mov     ebx, eax
0x180043ffa  test    eax, eax
0x180043ffc  js      loc_18004472F
0x180044002  mov     rcx, [rbp+57h+arg_18]
0x180044006  mov     rax, [rcx]
0x180044009  xor     edx, edx
0x18004400b  mov     rax, [rax+1F8h]
0x180044012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044017  mov     ebx, eax
0x180044019  test    eax, eax
0x18004401b  js      loc_18004472F
0x180044021  mov     rcx, [rbp+57h+arg_18]
0x180044025  mov     rax, [rcx]
0x180044028  xor     edx, edx
0x18004402a  mov     rax, [rax+220h]
0x180044031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044036  mov     ebx, eax
0x180044038  test    eax, eax
0x18004403a  js      loc_18004472F
0x180044040  mov     rcx, [rbp+57h+arg_18]
0x180044044  mov     rax, [rcx]
0x180044047  xor     edx, edx
0x180044049  mov     rax, [rax+230h]
0x180044050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044055  mov     ebx, eax
0x180044057  test    eax, eax
0x180044059  js      loc_18004472F
0x18004405f  mov     rcx, [rbp+57h+arg_18]
0x180044063  mov     rax, [rcx]
0x180044066  or      r12d, 0FFFFFFFFh
0x18004406a  mov     edx, r12d
0x18004406d  mov     rax, [rax+240h]
0x180044074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044079  mov     ebx, eax
0x18004407b  test    eax, eax
0x18004407d  js      loc_18004472F
0x180044083  mov     rbx, [rbp+57h+arg_18]
0x180044087  mov     rax, [rbx]
0x18004408a  mov     rdi, [rax+208h]
0x180044091  mov     rdx, rsi; unsigned __int16 *
0x180044094  lea     rcx, [rsp+110h+Block]; this
0x180044099  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004409e  nop
0x18004409f  mov     rdx, [rax]
0x1800440a2  test    rdx, rdx
0x1800440a5  jz      short loc_1800440AC
0x1800440a7  mov     rdx, [rdx]
0x1800440aa  jmp     short loc_1800440AF
0x1800440ac  mov     rdx, r15
0x1800440af  lea     r8, [rbp+57h+arg_10]
0x1800440b3  mov     rcx, rbx
0x1800440b6  mov     rax, rdi
0x1800440b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440be  mov     ebx, eax
0x1800440c0  mov     r13d, 18h
0x1800440c6  mov     rdi, [rsp+110h+Block]
0x1800440cb  test    rdi, rdi
0x1800440ce  jz      short loc_180044110
0x1800440d0  mov     eax, r12d
0x1800440d3  lock xadd [rdi+10h], eax
0x1800440d8  add     eax, r12d
0x1800440db  jnz     short loc_180044110
0x1800440dd  test    rdi, rdi
0x1800440e0  jz      short loc_180044110
0x1800440e2  mov     rcx, [rdi]; bstrString
0x1800440e5  test    rcx, rcx
0x1800440e8  jz      short loc_1800440F3
0x1800440ea  call    cs:__imp_SysFreeString
0x1800440f0  mov     [rdi], r15
0x1800440f3  mov     rcx, [rdi+8]; Block
0x1800440f7  test    rcx, rcx
0x1800440fa  jz      short loc_180044105
0x1800440fc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180044101  mov     [rdi+8], r15
0x180044105  mov     rdx, r13
0x180044108  mov     rcx, rdi; Block
0x18004410b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180044110  test    ebx, ebx
0x180044112  js      loc_18004472F
0x180044118  cmp     r12w, word ptr [rbp+57h+arg_10]
0x18004411d  jnz     loc_18004472F
0x180044123  mov     rbx, [rbp+57h+arg_18]
0x180044127  mov     rax, [rbx]
0x18004412a  mov     rdi, [rax+280h]
0x180044131  lea     rdx, aXmlnsWstHttpDo_1; "xmlns:wst='http://docs.oasis-open.org/w"...
0x180044138  lea     rcx, [rbp+57h+var_68]; this
0x18004413c  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180044141  nop
0x180044142  movups  xmm6, xmmword ptr [rax]
0x180044145  movsd   xmm7, qword ptr [rax+10h]
0x18004414a  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180044151  lea     rcx, [rsp+110h+Block]; this
0x180044156  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004415b  nop
0x18004415c  mov     rdx, [rax]
0x18004415f  test    rdx, rdx
0x180044162  jz      short loc_180044169
0x180044164  mov     rdx, [rdx]
0x180044167  jmp     short loc_18004416C
0x180044169  mov     rdx, r15
0x18004416c  movaps  [rbp+57h+var_C0], xmm6
0x180044170  movsd   [rbp+57h+var_B0], xmm7
0x180044175  lea     r8, [rbp+57h+var_C0]
0x180044179  mov     rcx, rbx
0x18004417c  mov     rax, rdi
0x18004417f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044184  mov     ebx, eax
0x180044186  mov     rdi, [rsp+110h+Block]
0x18004418b  test    rdi, rdi
0x18004418e  jz      short loc_1800441D5
0x180044190  mov     eax, r12d
0x180044193  lock xadd [rdi+10h], eax
0x180044198  add     eax, r12d
0x18004419b  jnz     short loc_1800441D0
0x18004419d  test    rdi, rdi
0x1800441a0  jz      short loc_1800441D0
0x1800441a2  mov     rcx, [rdi]; bstrString
0x1800441a5  test    rcx, rcx
0x1800441a8  jz      short loc_1800441B3
0x1800441aa  call    cs:__imp_SysFreeString
0x1800441b0  mov     [rdi], r15
0x1800441b3  mov     rcx, [rdi+8]; Block
0x1800441b7  test    rcx, rcx
0x1800441ba  jz      short loc_1800441C5
0x1800441bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800441c1  mov     [rdi+8], r15
0x1800441c5  mov     rdx, r13
0x1800441c8  mov     rcx, rdi; Block
0x1800441cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800441d0  mov     [rsp+110h+Block], r15
0x1800441d5  lea     rcx, [rbp+57h+var_68]; this
0x1800441d9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800441de  test    ebx, ebx
0x1800441e0  js      loc_18004472F
0x1800441e6  mov     rbx, [rbp+57h+arg_18]
0x1800441ea  mov     rax, [rbx]
0x1800441ed  mov     rdi, [rax+128h]
0x1800441f4  lea     rdx, aDsKeyinfo; "//ds:KeyInfo"
0x1800441fb  lea     rcx, [rsp+110h+Block]; this
0x180044200  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180044205  nop
0x180044206  mov     rdx, [rax]
0x180044209  test    rdx, rdx
0x18004420c  jz      short loc_180044213
0x18004420e  mov     rdx, [rdx]
0x180044211  jmp     short loc_180044216
0x180044213  mov     rdx, r15
0x180044216  lea     r8, [rbp+57h+var_90]
0x18004421a  mov     rcx, rbx
0x18004421d  mov     rax, rdi
0x180044220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044225  mov     ebx, eax
0x180044227  mov     rdi, [rsp+110h+Block]
0x18004422c  test    rdi, rdi
0x18004422f  jz      short loc_180044271
0x180044231  mov     eax, r12d
0x180044234  lock xadd [rdi+10h], eax
0x180044239  add     eax, r12d
0x18004423c  jnz     short loc_180044271
0x18004423e  test    rdi, rdi
0x180044241  jz      short loc_180044271
0x180044243  mov     rcx, [rdi]; bstrString
0x180044246  test    rcx, rcx
0x180044249  jz      short loc_180044254
0x18004424b  call    cs:__imp_SysFreeString
0x180044251  mov     [rdi], r15
0x180044254  mov     rcx, [rdi+8]; Block
0x180044258  test    rcx, rcx
0x18004425b  jz      short loc_180044266
0x18004425d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180044262  mov     [rdi+8], r15
0x180044266  mov     rdx, r13
0x180044269  mov     rcx, rdi; Block
0x18004426c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180044271  test    ebx, ebx
0x180044273  js      loc_18004472F
0x180044279  cmp     ebx, 1
0x18004427c  jz      loc_18004472F
0x180044282  mov     rdi, [rbp+57h+arg_18]
0x180044286  mov     rax, [rdi]
0x180044289  mov     rsi, [rax+1C0h]
0x180044290  lea     rdx, aHttpDocsOasisO_0; "http://docs.oasis-open.org/wss/2004/01/"...
0x180044297  lea     rcx, [rbp+57h+var_88]; this
0x18004429b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800442a0  nop
0x1800442a1  mov     rcx, [rax]
0x1800442a4  test    rcx, rcx
0x1800442a7  jz      short loc_1800442AE
0x1800442a9  mov     rbx, [rcx]
0x1800442ac  jmp     short loc_1800442B1
0x1800442ae  mov     rbx, r15
0x1800442b1  lea     rdx, aWsseSecurityto; "wsse:SecurityTokenReference"
0x1800442b8  lea     rcx, [rsp+110h+Block]; this
0x1800442bd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800442c2  nop
0x1800442c3  mov     rcx, [rax]
0x1800442c6  test    rcx, rcx
0x1800442c9  jz      short loc_1800442D0
0x1800442cb  mov     r8, [rcx]
0x1800442ce  jmp     short loc_1800442D3
0x1800442d0  mov     r8, r15
0x1800442d3  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800442d7  movaps  [rbp+57h+var_C0], xmm0
0x1800442db  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800442e0  movsd   [rbp+57h+var_B0], xmm1
0x1800442e5  lea     rax, [rbp+57h+var_C8]
0x1800442e9  mov     [rsp+110h+ppv], rax
0x1800442ee  mov     r9, rbx
0x1800442f1  lea     rdx, [rbp+57h+var_C0]
0x1800442f5  mov     rcx, rdi
0x1800442f8  mov     rax, rsi
0x1800442fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044300  mov     ebx, eax
0x180044302  mov     rdi, [rsp+110h+Block]
0x180044307  test    rdi, rdi
0x18004430a  jz      short loc_180044351
0x18004430c  mov     eax, r12d
0x18004430f  lock xadd [rdi+10h], eax
0x180044314  add     eax, r12d
0x180044317  jnz     short loc_18004434C
0x180044319  test    rdi, rdi
0x18004431c  jz      short loc_18004434C
0x18004431e  mov     rcx, [rdi]; bstrString
0x180044321  test    rcx, rcx
0x180044324  jz      short loc_18004432F
0x180044326  call    cs:__imp_SysFreeString
0x18004432c  mov     [rdi], r15
0x18004432f  mov     rcx, [rdi+8]; Block
0x180044333  test    rcx, rcx
0x180044336  jz      short loc_180044341
0x180044338  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004433d  mov     [rdi+8], r15
0x180044341  mov     rdx, r13
0x180044344  mov     rcx, rdi; Block
0x180044347  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004434c  mov     [rsp+110h+Block], r15
0x180044351  mov     rdi, [rbp+57h+var_88]
0x180044355  test    rdi, rdi
0x180044358  jz      short loc_18004439A
0x18004435a  mov     eax, r12d
0x18004435d  lock xadd [rdi+10h], eax
0x180044362  add     eax, r12d
0x180044365  jnz     short loc_18004439A
0x180044367  test    rdi, rdi
0x18004436a  jz      short loc_18004439A
0x18004436c  mov     rcx, [rdi]; bstrString
0x18004436f  test    rcx, rcx
0x180044372  jz      short loc_18004437D
0x180044374  call    cs:__imp_SysFreeString
0x18004437a  mov     [rdi], r15
0x18004437d  mov     rcx, [rdi+8]; Block
0x180044381  test    rcx, rcx
0x180044384  jz      short loc_18004438F
0x180044386  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004438b  mov     [rdi+8], r15
0x18004438f  mov     rdx, r13
0x180044392  mov     rcx, rdi; Block
0x180044395  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004439a  test    ebx, ebx
0x18004439c  js      loc_18004472F
0x1800443a2  mov     rdi, [rbp+57h+arg_18]
  ... truncated ...
```
