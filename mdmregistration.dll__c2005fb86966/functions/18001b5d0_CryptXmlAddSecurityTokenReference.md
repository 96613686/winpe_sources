# CryptXmlAddSecurityTokenReference

- ea: `0x18001b5d0`
- end: `0x18001bcea`
- name: `CryptXmlAddSecurityTokenReference`
- size: `1818`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b098`

## callees

- `0x18000bd08`
- `0x18001ad94`
- `0x18001ae84`
- `0x18001b5d0`
- `0x18004b694`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bb9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bb9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b682`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b682`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b77a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b9c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba61`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b77a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b9c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba61`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bbf4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bbf4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bbbc`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bbbc`
- `OLEAUT32!__imp_VariantInit` at `0x18001b641`
- `OLEAUT32!__imp_VariantInit` at `0x18001b641`
- `OLEAUT32!__imp_VariantClear` at `0x18001b7ef`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba37`
- `OLEAUT32!__imp_VariantClear` at `0x18001bad0`
- `OLEAUT32!__imp_VariantClear` at `0x18001bbdc`
- `OLEAUT32!__imp_VariantClear` at `0x18001b7ef`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba37`
- `OLEAUT32!__imp_VariantClear` at `0x18001bad0`
- `OLEAUT32!__imp_VariantClear` at `0x18001bbdc`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001bb76`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001bb76`

## string_xrefs

- `0x18001b872`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd`
- `0x18001b90b`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd`
- `0x18001b892`: `wsse:SecurityTokenReference`
- `0x18001ba5a`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509`
- `0x18001b773`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addressing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' `

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CryptXmlAddSecurityTokenReference(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  HRESULT v6; // ebx
  LPVOID v7; // rbx
  __int64 (__fastcall *v8)(LPVOID, _QWORD *, __int64 *); // rdi
  _QWORD *v9; // rdx
  LPVOID v10; // rbx
  __int64 v11; // rdi
  BSTR v12; // rax
  __int128 v13; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v15; // rdx
  HRESULT v16; // eax
  LPVOID v17; // rbx
  __int64 (__fastcall *v18)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  LPVOID v21; // rdi
  __int64 (__fastcall *v22)(LPVOID, VARIANTARG *, __int64, __int64, __int64 *); // rsi
  _bstr_t *v23; // rax
  __int64 v24; // rbx
  _bstr_t *v25; // rax
  __int64 v26; // r8
  LPVOID v27; // rdi
  __int64 (__fastcall *v28)(LPVOID, VARIANTARG *, __int64, __int64, __int64 *); // rsi
  _bstr_t *v29; // rax
  __int64 v30; // rbx
  _bstr_t *v31; // rax
  __int64 v32; // r8
  __int64 *v33; // rbx
  __int64 v34; // rdi
  BSTR v35; // rax
  __int128 v36; // xmm6
  IRecordInfo *v37; // xmm7_8
  _QWORD *v38; // rdx
  HRESULT v39; // eax
  __int64 *v40; // rbx
  __int64 v41; // rdi
  BSTR v42; // rax
  __int128 v43; // xmm6
  IRecordInfo *v44; // xmm7_8
  _QWORD *v45; // rdx
  HRESULT v46; // eax
  __int64 v47; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v49; // rax
  const unsigned __int16 *v50; // rbx
  UINT v51; // eax
  HRESULT v52; // eax
  _BYTE v54[8]; // [rsp+38h] [rbp-79h] BYREF
  _BYTE v55[8]; // [rsp+40h] [rbp-71h] BYREF
  BSTR bstr; // [rsp+48h] [rbp-69h] BYREF
  __int64 v57; // [rsp+50h] [rbp-61h] BYREF
  VARIANTARG v58; // [rsp+58h] [rbp-59h] BYREF
  VARIANTARG v59; // [rsp+78h] [rbp-39h] BYREF
  __int64 v60; // [rsp+98h] [rbp-19h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-1h] BYREF
  LPVOID ppv; // [rsp+120h] [rbp+6Fh] BYREF
  __int64 v65; // [rsp+128h] [rbp+77h] BYREF
  __int64 *v66; // [rsp+130h] [rbp+7Fh] BYREF

  v65 = a3;
  ppv = 0;
  v62 = 0;
  v57 = 0;
  v61 = 0;
  v66 = 0;
  v60 = 0;
  bstr = 0;
  LOWORD(v65) = 0;
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
            v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)ppv + 520LL);
            v9 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v54, a1);
            if ( v9 )
              v9 = (_QWORD *)*v9;
            v6 = v8(v7, v9, &v65);
            _bstr_t::~_bstr_t((_bstr_t *)v54);
            if ( v6 >= 0 && (_WORD)v65 == 0xFFFF )
            {
              v10 = ppv;
              v11 = *(_QWORD *)ppv;
              v12 = SysAllocString(
                      L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:wsse='http://docs.oasis-open.or"
                       "g/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd' xmlns:a='http://www.w3.org/2005/08/addr"
                       "essing' xmlns:u='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.x"
                       "sd' xmlns:ds='http://www.w3.org/2000/09/xmldsig#' ");
              if ( !v12 )
                _com_issue_error(-2147024882);
              v58.vt = 8;
              v58.llVal = (LONGLONG)v12;
              v13 = *(_OWORD *)&v58.vt;
              pRecInfo = v58.pRecInfo;
              v15 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v54, L"SelectionNamespaces");
              if ( v15 )
                v15 = (_QWORD *)*v15;
              *(_OWORD *)&v59.vt = v13;
              v59.pRecInfo = pRecInfo;
              v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, VARIANTARG *))(v11 + 640))(v10, v15, &v59);
              _bstr_t::~_bstr_t((_bstr_t *)v54);
              v16 = VariantClear(&v58);
              if ( v16 < 0 )
                _com_issue_error(v16);
              if ( v6 >= 0 )
              {
                v17 = ppv;
                v18 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 296LL);
                v19 = _bstr_t::_bstr_t((_bstr_t *)v54, L"//ds:KeyInfo");
                v20 = *(_QWORD *)v19 ? **(_QWORD **)v19 : 0LL;
                v6 = v18(v17, v20, &v62);
                _bstr_t::~_bstr_t((_bstr_t *)v54);
                if ( v6 >= 0 && v6 != 1 )
                {
                  v21 = ppv;
                  v22 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int64, __int64, __int64 *))(*(_QWORD *)ppv + 448LL);
                  v23 = _bstr_t::_bstr_t(
                          (_bstr_t *)v55,
                          L"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd");
                  v24 = *(_QWORD *)v23 ? **(_QWORD **)v23 : 0LL;
                  v25 = _bstr_t::_bstr_t((_bstr_t *)v54, L"wsse:SecurityTokenReference");
                  v26 = *(_QWORD *)v25 ? **(_QWORD **)v25 : 0LL;
                  v59 = pvarg;
                  v6 = v22(v21, &v59, v26, v24, &v57);
                  _bstr_t::~_bstr_t((_bstr_t *)v54);
                  _bstr_t::~_bstr_t((_bstr_t *)v55);
                  if ( v6 >= 0 )
                  {
                    v27 = ppv;
                    v28 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int64, __int64, __int64 *))(*(_QWORD *)ppv + 448LL);
                    v29 = _bstr_t::_bstr_t(
                            (_bstr_t *)v54,
                            L"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd");
                    v30 = *(_QWORD *)v29 ? **(_QWORD **)v29 : 0LL;
                    v31 = _bstr_t::_bstr_t((_bstr_t *)v55, L"wsse:Reference");
                    v32 = *(_QWORD *)v31 ? **(_QWORD **)v31 : 0LL;
                    v59 = pvarg;
                    v6 = v28(v27, &v59, v32, v30, &v61);
                    _bstr_t::~_bstr_t((_bstr_t *)v55);
                    _bstr_t::~_bstr_t((_bstr_t *)v54);
                    if ( v6 >= 0 )
                    {
                      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v61)(
                             v61,
                             &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                             &v66);
                      if ( v6 >= 0 )
                      {
                        v33 = v66;
                        v34 = *v66;
                        v35 = SysAllocString(L"uuid-29801C2F-F26B-46AD-984B-AFAEFB545FF8");
                        if ( !v35 )
                          _com_issue_error(-2147024882);
                        v58.vt = 8;
                        v58.llVal = (LONGLONG)v35;
                        v36 = *(_OWORD *)&v58.vt;
                        v37 = v58.pRecInfo;
                        v38 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v55, L"URI");
                        if ( v38 )
                          v38 = (_QWORD *)*v38;
                        *(_OWORD *)&v59.vt = v36;
                        v59.pRecInfo = v37;
                        v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, VARIANTARG *))(v34 + 360))(v33, v38, &v59);
                        _bstr_t::~_bstr_t((_bstr_t *)v55);
                        v39 = VariantClear(&v58);
                        if ( v39 < 0 )
                          _com_issue_error(v39);
                        if ( v6 >= 0 )
                        {
                          v40 = v66;
                          v41 = *v66;
                          v42 = SysAllocString(L"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509");
                          if ( !v42 )
                            _com_issue_error(-2147024882);
                          v58.vt = 8;
                          v58.llVal = (LONGLONG)v42;
                          v43 = *(_OWORD *)&v58.vt;
                          v44 = v58.pRecInfo;
                          v45 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v55, L"ValueType");
                          if ( v45 )
                            v45 = (_QWORD *)*v45;
                          *(_OWORD *)&v59.vt = v43;
                          v59.pRecInfo = v44;
                          v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, VARIANTARG *))(v41 + 360))(
                                 v40,
                                 v45,
                                 &v59);
                          _bstr_t::~_bstr_t((_bstr_t *)v55);
                          v46 = VariantClear(&v58);
                          if ( v46 < 0 )
                            _com_issue_error(v46);
                          if ( v6 >= 0 )
                          {
                            v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v57 + 168LL))(
                                   v57,
                                   v66,
                                   0);
                            if ( v6 >= 0 )
                            {
                              v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v62 + 168LL))(
                                     v62,
                                     v57,
                                     0);
                              if ( v6 >= 0 )
                              {
                                v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v60);
                                if ( v6 >= 0 )
                                {
                                  v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v60 + 272LL))(v60, &bstr);
                                  if ( v6 >= 0 )
                                  {
                                    v47 = SysStringByteLen(bstr);
                                    ProcessHeap = GetProcessHeap();
                                    v49 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v47 + 2);
                                    *a4 = v49;
                                    if ( v49 )
                                    {
                                      v50 = bstr;
                                      v51 = SysStringLen(bstr);
                                      v6 = StringCchCopyW(*a4, v51 + 1, v50);
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
  v52 = VariantClear(&pvarg);
  if ( v52 < 0 )
    _com_issue_error(v52);
  SysFreeString(bstr);
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v66 )
    (*(void (__fastcall **)(__int64 *))(*v66 + 16))(v66);
  if ( v61 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( v62 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b5d0  mov     rax, rsp
0x18001b5d3  mov     [rax+8], rbx
0x18001b5d7  mov     [rax+18h], r8
0x18001b5db  mov     [rax+10h], rdx
0x18001b5df  push    rbp
0x18001b5e0  push    rsi
0x18001b5e1  push    rdi
0x18001b5e2  push    r12
0x18001b5e4  push    r14
0x18001b5e6  lea     rbp, [rax-5Fh]
0x18001b5ea  sub     rsp, 0E0h
0x18001b5f1  movaps  xmmword ptr [rax-38h], xmm6
0x18001b5f5  movaps  xmmword ptr [rax-48h], xmm7
0x18001b5f9  mov     r14, r9
0x18001b5fc  mov     rsi, rcx
0x18001b5ff  mov     [rbp+57h+arg_8], 0
0x18001b607  mov     [rbp+57h+var_60], 0
0x18001b60f  mov     [rbp+57h+var_B8], 0
0x18001b617  mov     [rbp+57h+var_68], 0
0x18001b61f  mov     [rbp+57h+arg_18], 0
0x18001b627  mov     [rbp+57h+var_70], 0
0x18001b62f  mov     [rbp+57h+bstr], 0
0x18001b637  xor     eax, eax
0x18001b639  mov     word ptr [rbp+57h+arg_10], ax
0x18001b63d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001b641  call    cs:__imp_VariantInit
0x18001b648  nop     dword ptr [rax+rax+00h]
0x18001b64d  nop
0x18001b64e  mov     eax, 3
0x18001b653  mov     word ptr [rbp+57h+pvarg], ax
0x18001b657  mov     dword ptr [rbp+57h+pvarg+8], 1
0x18001b65e  mov     qword ptr [r14], 0
0x18001b665  lea     rax, [rbp+57h+arg_8]
0x18001b669  mov     [rsp+100h+ppv], rax; ppv
0x18001b66e  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18001b675  xor     edx, edx; pUnkOuter
0x18001b677  lea     r8d, [rdx+17h]; dwClsContext
0x18001b67b  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001b682  call    cs:__imp_CoCreateInstance
0x18001b689  nop     dword ptr [rax+rax+00h]
0x18001b68e  mov     ebx, eax
0x18001b690  test    eax, eax
0x18001b692  js      loc_18001BBD8
0x18001b698  mov     rcx, [rbp+57h+arg_8]
0x18001b69c  mov     rax, [rcx]
0x18001b69f  xor     edx, edx
0x18001b6a1  mov     rax, [rax+1F8h]
0x18001b6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6ad  mov     ebx, eax
0x18001b6af  test    eax, eax
0x18001b6b1  js      loc_18001BBD8
0x18001b6b7  mov     rcx, [rbp+57h+arg_8]
0x18001b6bb  mov     rax, [rcx]
0x18001b6be  xor     edx, edx
0x18001b6c0  mov     rax, [rax+220h]
0x18001b6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6cc  mov     ebx, eax
0x18001b6ce  test    eax, eax
0x18001b6d0  js      loc_18001BBD8
0x18001b6d6  mov     rcx, [rbp+57h+arg_8]
0x18001b6da  mov     rax, [rcx]
0x18001b6dd  xor     edx, edx
0x18001b6df  mov     rax, [rax+230h]
0x18001b6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6eb  mov     ebx, eax
0x18001b6ed  test    eax, eax
0x18001b6ef  js      loc_18001BBD8
0x18001b6f5  mov     rcx, [rbp+57h+arg_8]
0x18001b6f9  mov     rax, [rcx]
0x18001b6fc  or      r12d, 0FFFFFFFFh
0x18001b700  mov     edx, r12d
0x18001b703  mov     rax, [rax+240h]
0x18001b70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b70f  mov     ebx, eax
0x18001b711  test    eax, eax
0x18001b713  js      loc_18001BBD8
0x18001b719  mov     rbx, [rbp+57h+arg_8]
0x18001b71d  mov     rax, [rbx]
0x18001b720  mov     rdi, [rax+208h]
0x18001b727  mov     rdx, rsi; unsigned __int16 *
0x18001b72a  lea     rcx, [rbp+57h+var_D0]; this
0x18001b72e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b733  nop
0x18001b734  mov     rdx, [rax]
0x18001b737  test    rdx, rdx
0x18001b73a  jz      short loc_18001B73F
0x18001b73c  mov     rdx, [rdx]
0x18001b73f  lea     r8, [rbp+57h+arg_10]
0x18001b743  mov     rcx, rbx
0x18001b746  mov     rax, rdi
0x18001b749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b74e  mov     ebx, eax
0x18001b750  lea     rcx, [rbp+57h+var_D0]; this
0x18001b754  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b759  test    ebx, ebx
0x18001b75b  js      loc_18001BBD8
0x18001b761  cmp     r12w, word ptr [rbp+57h+arg_10]
0x18001b766  jnz     loc_18001BBD8
0x18001b76c  mov     rbx, [rbp+57h+arg_8]
0x18001b770  mov     rdi, [rbx]
0x18001b773  lea     rcx, aXmlnsWstHttpDo_1; "xmlns:wst='http://docs.oasis-open.org/w"...
0x18001b77a  call    cs:__imp_SysAllocString
0x18001b781  nop     dword ptr [rax+rax+00h]
0x18001b786  test    rax, rax
0x18001b789  jz      loc_18001BCB1
0x18001b78f  mov     r12d, 8
0x18001b795  mov     word ptr [rbp+57h+var_B0], r12w
0x18001b79a  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18001b79e  movups  xmm6, xmmword ptr [rbp+57h+var_B0]
0x18001b7a2  movsd   xmm7, qword ptr [rbp+57h+var_B0+10h]
0x18001b7a7  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18001b7ae  lea     rcx, [rbp+57h+var_D0]; this
0x18001b7b2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b7b7  nop
0x18001b7b8  mov     rdx, [rax]
0x18001b7bb  test    rdx, rdx
0x18001b7be  jz      short loc_18001B7C3
0x18001b7c0  mov     rdx, [rdx]
0x18001b7c3  movaps  [rbp+57h+var_90], xmm6
0x18001b7c7  movsd   [rbp+57h+var_80], xmm7
0x18001b7cc  lea     r8, [rbp+57h+var_90]
0x18001b7d0  mov     rcx, rbx
0x18001b7d3  mov     rax, [rdi+280h]
0x18001b7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7df  mov     ebx, eax
0x18001b7e1  lea     rcx, [rbp+57h+var_D0]; this
0x18001b7e5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b7ea  nop
0x18001b7eb  lea     rcx, [rbp+57h+var_B0]; pvarg
0x18001b7ef  call    cs:__imp_VariantClear
0x18001b7f6  nop     dword ptr [rax+rax+00h]
0x18001b7fb  test    eax, eax
0x18001b7fd  js      loc_18001BCBC
0x18001b803  test    ebx, ebx
0x18001b805  js      loc_18001BBD8
0x18001b80b  mov     rbx, [rbp+57h+arg_8]
0x18001b80f  mov     rax, [rbx]
0x18001b812  mov     rdi, [rax+128h]
0x18001b819  lea     rdx, aDsKeyinfo; "//ds:KeyInfo"
0x18001b820  lea     rcx, [rbp+57h+var_D0]; this
0x18001b824  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b829  nop
0x18001b82a  mov     rcx, [rax]
0x18001b82d  test    rcx, rcx
0x18001b830  jz      short loc_18001B837
0x18001b832  mov     rdx, [rcx]
0x18001b835  jmp     short loc_18001B839
0x18001b837  xor     edx, edx
0x18001b839  lea     r8, [rbp+57h+var_60]
0x18001b83d  mov     rcx, rbx
0x18001b840  mov     rax, rdi
0x18001b843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b848  mov     ebx, eax
0x18001b84a  lea     rcx, [rbp+57h+var_D0]; this
0x18001b84e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b853  test    ebx, ebx
0x18001b855  js      loc_18001BBD8
0x18001b85b  cmp     ebx, 1
0x18001b85e  jz      loc_18001BBD8
0x18001b864  mov     rdi, [rbp+57h+arg_8]
0x18001b868  mov     rax, [rdi]
0x18001b86b  mov     rsi, [rax+1C0h]
0x18001b872  lea     rdx, aHttpDocsOasisO_0; "http://docs.oasis-open.org/wss/2004/01/"...
0x18001b879  lea     rcx, [rbp+57h+var_C8]; this
0x18001b87d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b882  nop
0x18001b883  mov     rcx, [rax]
0x18001b886  test    rcx, rcx
0x18001b889  jz      short loc_18001B890
0x18001b88b  mov     rbx, [rcx]
0x18001b88e  jmp     short loc_18001B892
0x18001b890  xor     ebx, ebx
0x18001b892  lea     rdx, aWsseSecurityto; "wsse:SecurityTokenReference"
0x18001b899  lea     rcx, [rbp+57h+var_D0]; this
0x18001b89d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b8a2  nop
0x18001b8a3  mov     rcx, [rax]
0x18001b8a6  test    rcx, rcx
0x18001b8a9  jz      short loc_18001B8B0
0x18001b8ab  mov     r8, [rcx]
0x18001b8ae  jmp     short loc_18001B8B3
0x18001b8b0  xor     r8d, r8d
0x18001b8b3  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18001b8b7  movaps  [rbp+57h+var_90], xmm0
0x18001b8bb  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18001b8c0  movsd   [rbp+57h+var_80], xmm1
0x18001b8c5  lea     rax, [rbp+57h+var_B8]
0x18001b8c9  mov     [rsp+100h+ppv], rax
0x18001b8ce  mov     r9, rbx
0x18001b8d1  lea     rdx, [rbp+57h+var_90]
0x18001b8d5  mov     rcx, rdi
0x18001b8d8  mov     rax, rsi
0x18001b8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8e0  mov     ebx, eax
0x18001b8e2  lea     rcx, [rbp+57h+var_D0]; this
0x18001b8e6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b8eb  nop
0x18001b8ec  lea     rcx, [rbp+57h+var_C8]; this
0x18001b8f0  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b8f5  test    ebx, ebx
0x18001b8f7  js      loc_18001BBD8
0x18001b8fd  mov     rdi, [rbp+57h+arg_8]
0x18001b901  mov     rax, [rdi]
0x18001b904  mov     rsi, [rax+1C0h]
0x18001b90b  lea     rdx, aHttpDocsOasisO_0; "http://docs.oasis-open.org/wss/2004/01/"...
0x18001b912  lea     rcx, [rbp+57h+var_D0]; this
0x18001b916  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b91b  nop
0x18001b91c  mov     rcx, [rax]
0x18001b91f  test    rcx, rcx
0x18001b922  jz      short loc_18001B929
0x18001b924  mov     rbx, [rcx]
0x18001b927  jmp     short loc_18001B92B
0x18001b929  xor     ebx, ebx
0x18001b92b  lea     rdx, aWsseReference; "wsse:Reference"
0x18001b932  lea     rcx, [rbp+57h+var_C8]; this
0x18001b936  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b93b  nop
0x18001b93c  mov     rcx, [rax]
0x18001b93f  test    rcx, rcx
0x18001b942  jz      short loc_18001B949
0x18001b944  mov     r8, [rcx]
0x18001b947  jmp     short loc_18001B94C
0x18001b949  xor     r8d, r8d
0x18001b94c  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18001b950  movaps  [rbp+57h+var_90], xmm0
0x18001b954  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18001b959  movsd   [rbp+57h+var_80], xmm1
0x18001b95e  lea     rax, [rbp+57h+var_68]
0x18001b962  mov     [rsp+100h+ppv], rax
0x18001b967  mov     r9, rbx
0x18001b96a  lea     rdx, [rbp+57h+var_90]
0x18001b96e  mov     rcx, rdi
0x18001b971  mov     rax, rsi
0x18001b974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b979  mov     ebx, eax
0x18001b97b  lea     rcx, [rbp+57h+var_C8]; this
0x18001b97f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b984  nop
0x18001b985  lea     rcx, [rbp+57h+var_D0]; this
0x18001b989  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b98e  test    ebx, ebx
0x18001b990  js      loc_18001BBD8
0x18001b996  mov     rcx, [rbp+57h+var_68]
0x18001b99a  mov     rax, [rcx]
0x18001b99d  lea     r8, [rbp+57h+arg_18]
0x18001b9a1  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18001b9a8  mov     rax, [rax]
0x18001b9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b0  mov     ebx, eax
0x18001b9b2  test    eax, eax
0x18001b9b4  js      loc_18001BBD8
0x18001b9ba  mov     rbx, [rbp+57h+arg_18]
0x18001b9be  mov     rdi, [rbx]
0x18001b9c1  lea     rcx, aUuid29801c2fF2; "uuid-29801C2F-F26B-46AD-984B-AFAEFB545F"...
0x18001b9c8  call    cs:__imp_SysAllocString
0x18001b9cf  nop     dword ptr [rax+rax+00h]
0x18001b9d4  test    rax, rax
0x18001b9d7  jz      loc_18001BCC4
0x18001b9dd  mov     word ptr [rbp+57h+var_B0], r12w
0x18001b9e2  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18001b9e6  movups  xmm6, xmmword ptr [rbp+57h+var_B0]
0x18001b9ea  movsd   xmm7, qword ptr [rbp+57h+var_B0+10h]
0x18001b9ef  lea     rdx, aUri; "URI"
0x18001b9f6  lea     rcx, [rbp+57h+var_C8]; this
0x18001b9fa  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001b9ff  nop
0x18001ba00  mov     rdx, [rax]
0x18001ba03  test    rdx, rdx
0x18001ba06  jz      short loc_18001BA0B
0x18001ba08  mov     rdx, [rdx]
0x18001ba0b  movaps  [rbp+57h+var_90], xmm6
0x18001ba0f  movsd   [rbp+57h+var_80], xmm7
0x18001ba14  lea     r8, [rbp+57h+var_90]
0x18001ba18  mov     rcx, rbx
0x18001ba1b  mov     rax, [rdi+168h]
0x18001ba22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba27  mov     ebx, eax
0x18001ba29  lea     rcx, [rbp+57h+var_C8]; this
0x18001ba2d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001ba32  nop
0x18001ba33  lea     rcx, [rbp+57h+var_B0]; pvarg
0x18001ba37  call    cs:__imp_VariantClear
0x18001ba3e  nop     dword ptr [rax+rax+00h]
0x18001ba43  test    eax, eax
0x18001ba45  js      loc_18001BCCF
0x18001ba4b  test    ebx, ebx
0x18001ba4d  js      loc_18001BBD8
0x18001ba53  mov     rbx, [rbp+57h+arg_18]
0x18001ba57  mov     rdi, [rbx]
0x18001ba5a  lea     rcx, aHttpDocsOasisO_2; "http://docs.oasis-open.org/wss/2004/01/"...
0x18001ba61  call    cs:__imp_SysAllocString
0x18001ba68  nop     dword ptr [rax+rax+00h]
0x18001ba6d  test    rax, rax
0x18001ba70  jz      loc_18001BCD7
0x18001ba76  mov     word ptr [rbp+57h+var_B0], r12w
0x18001ba7b  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18001ba7f  movups  xmm6, xmmword ptr [rbp+57h+var_B0]
0x18001ba83  movsd   xmm7, qword ptr [rbp+57h+var_B0+10h]
0x18001ba88  lea     rdx, aValuetype; "ValueType"
  ... truncated ...
```
