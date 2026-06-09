# EapLm::Peer::ThirdPartyEapMethodConfig::ConfigBlob2Xml(uint,ConstBuffer const &,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x18001e8b0`
- end: `0x18001eb26`
- name: `?ConfigBlob2Xml@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAA_NIAEBUConstBuffer@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z`
- size: `630`
- prototype: `bool __fastcall(const struct _EAP_METHOD_TYPE *, unsigned int, __int64 *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000d098`
- `0x18000d0e8`
- `0x18000d184`
- `0x18000eb94`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800162d4`
- `0x180016400`
- `0x1800177bc`
- `0x18001b328`
- `0x18001e8b0`
- `0x18001ecf8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eaeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eaeb`

## string_xrefs

- `0x18001e9cf`: `ConfigBlob2Xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::ConfigBlob2Xml(
        const struct _EAP_METHOD_TYPE *a1,
        unsigned int a2,
        __int64 *a3,
        struct IUnknown **a4)
{
  LPVOID *v8; // rax
  LPVOID v9; // rsi
  __int64 (__fastcall *v10)(LPVOID, const struct _EAP_METHOD_TYPE *, _QWORD, _QWORD, __int64, LPVOID *, __int16 *, struct _EAP_ERROR **); // rdi
  __int64 v11; // rbx
  unsigned int v12; // eax
  signed int v13; // ebx
  const wchar_t *v15; // rdx
  struct IUnknown **v16; // rax
  bool v17; // bl
  __int16 v18; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  struct _EAP_ERROR *v20; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h]
  _BYTE v24[96]; // [rsp+90h] [rbp-70h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dP(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, a2, a3[1]);
  v20 = 0;
  pv = 0;
  v18 = 0;
  v8 = EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(a1, &ppv);
  v9 = *v8;
  v10 = *(__int64 (__fastcall **)(LPVOID, const struct _EAP_METHOD_TYPE *, _QWORD, _QWORD, __int64, LPVOID *, __int16 *, struct _EAP_ERROR **))(*(_QWORD *)*v8 + 96LL);
  v11 = *a3;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a3[1]);
  v13 = v10(v9, a1 + 1, a2, v12, v11, &pv, &v18, &v20);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&ppv);
  if ( v13 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v24, v20, v13);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v24);
  }
  if ( v18 == -1 )
  {
    v15 = &qword_18003A720;
    if ( pv )
      v15 = (const wchar_t *)pv;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
      (__int64)v22,
      (__int64)v15);
    v16 = (struct IUnknown **)EapHost::BaseXmlHelper::String2Document(&ppv, (__int64)v22);
    if ( *a4 != *v16 )
      ATL::AtlComPtrAssign(a4, *v16);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&ppv);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dP(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids,
        v18 == -1,
        v23);
    v17 = v18 == -1;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v22);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v20);
    return v17;
  }
  else
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, PeerFunctionNotSupportedInfo, "ConfigBlob2Xml");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v20);
    return 0;
  }
}

```

## disassembly

```asm
0x18001e8b0  push    rbp
0x18001e8b2  push    rbx
0x18001e8b3  push    rsi
0x18001e8b4  push    rdi
0x18001e8b5  push    r12
0x18001e8b7  push    r13
0x18001e8b9  push    r14
0x18001e8bb  push    r15
0x18001e8bd  lea     rbp, [rsp-8]
0x18001e8c2  sub     rsp, 108h
0x18001e8c9  mov     rax, cs:__security_cookie
0x18001e8d0  xor     rax, rsp
0x18001e8d3  mov     [rbp+40h+var_50], rax
0x18001e8d7  mov     r14, r9
0x18001e8da  mov     r15, r8
0x18001e8dd  mov     r12d, edx
0x18001e8e0  mov     r13, rcx
0x18001e8e3  lea     rax, WPP_GLOBAL_Control
0x18001e8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8f1  cmp     rcx, rax
0x18001e8f4  jz      short loc_18001E91D
0x18001e8f6  test    byte ptr [rcx+1Ch], 4
0x18001e8fa  jz      short loc_18001E91D
0x18001e8fc  mov     edx, 1Ah
0x18001e901  mov     rax, [r8+8]
0x18001e905  mov     [rsp+140h+var_120], rax
0x18001e90a  mov     r9d, r12d
0x18001e90d  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001e914  mov     rcx, [rcx+10h]
0x18001e918  call    WPP_SF_dP
0x18001e91d  mov     [rsp+140h+var_E0], 0
0x18001e926  mov     [rsp+140h+pv], 0
0x18001e92f  xor     eax, eax
0x18001e931  mov     [rsp+140h+var_F0], ax
0x18001e936  lea     rdx, [rsp+140h+ppv]
0x18001e93b  mov     rcx, r13
0x18001e93e  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001e943  nop
0x18001e944  mov     rsi, [rax]
0x18001e947  mov     rax, [rsi]
0x18001e94a  mov     rdi, [rax+60h]
0x18001e94e  mov     rbx, [r15]
0x18001e951  mov     rcx, [r15+8]
0x18001e955  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001e95a  lea     rdx, [r13+10h]
0x18001e95e  lea     rcx, [rsp+140h+var_E0]
0x18001e963  mov     [rsp+140h+var_108], rcx
0x18001e968  lea     rcx, [rsp+140h+var_F0]
0x18001e96d  mov     [rsp+140h+var_110], rcx
0x18001e972  lea     rcx, [rsp+140h+pv]
0x18001e977  mov     [rsp+140h+var_118], rcx
0x18001e97c  mov     [rsp+140h+var_120], rbx
0x18001e981  mov     r9d, eax
0x18001e984  mov     r8d, r12d
0x18001e987  mov     rcx, rsi
0x18001e98a  mov     rax, rdi
0x18001e98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e992  mov     ebx, eax
0x18001e994  lea     rcx, [rsp+140h+ppv]
0x18001e999  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001e99e  test    ebx, ebx
0x18001e9a0  jns     short loc_18001E9BE
0x18001e9a2  mov     r8d, ebx; unsigned int
0x18001e9a5  mov     rdx, [rsp+140h+var_E0]; struct _EAP_ERROR *
0x18001e9aa  lea     rcx, [rbp+40h+var_B0]; this
0x18001e9ae  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001e9b3  nop
0x18001e9b4  lea     rcx, [rbp+40h+var_B0]; struct EapHost::EapError *
0x18001e9b8  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001e9be  cmp     [rsp+140h+var_F0], 0FFFFh
0x18001e9c4  jz      short loc_18001EA42
0x18001e9c6  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18001e9cd  jz      short loc_18001E9E9
0x18001e9cf  lea     r8, aConfigblob2xml; "ConfigBlob2Xml"
0x18001e9d6  lea     rdx, PeerFunctionNotSupportedInfo
0x18001e9dd  lea     rcx, eaphost_Context
0x18001e9e4  call    McTemplateU0s_EtwEventWriteTransfer
0x18001e9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9f0  lea     rax, WPP_GLOBAL_Control
0x18001e9f7  cmp     rcx, rax
0x18001e9fa  jz      short loc_18001EA18
0x18001e9fc  test    byte ptr [rcx+1Ch], 4
0x18001ea00  jz      short loc_18001EA18
0x18001ea02  mov     edx, 1Bh
0x18001ea07  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001ea0e  mov     rcx, [rcx+10h]
0x18001ea12  call    WPP_SF_
0x18001ea17  nop
0x18001ea18  mov     rcx, [rsp+140h+pv]; pv
0x18001ea1d  test    rcx, rcx
0x18001ea20  jz      short loc_18001EA31
0x18001ea22  call    cs:__imp_CoTaskMemFree
0x18001ea28  mov     [rsp+140h+pv], 0
0x18001ea31  lea     rcx, [rsp+140h+var_E0]
0x18001ea36  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001ea3b  xor     al, al
0x18001ea3d  jmp     loc_18001EB06
0x18001ea42  lea     rdx, qword_18003A720
0x18001ea49  mov     rax, [rsp+140h+pv]
0x18001ea4e  test    rax, rax
0x18001ea51  cmovnz  rdx, rax
0x18001ea55  lea     rcx, [rsp+140h+var_D0]
0x18001ea5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001ea5f  nop
0x18001ea60  lea     rdx, [rsp+140h+var_D0]
0x18001ea65  lea     rcx, [rsp+140h+ppv]; ppv
0x18001ea6a  call    ?String2Document@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapHost::BaseXmlHelper::String2Document(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001ea6f  mov     rdx, [rax]; struct IUnknown *
0x18001ea72  cmp     [r14], rdx
0x18001ea75  jz      short loc_18001EA7F
0x18001ea77  mov     rcx, r14; struct IUnknown **
0x18001ea7a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001ea7f  lea     rcx, [rsp+140h+ppv]
0x18001ea84  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001ea89  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea90  lea     rax, WPP_GLOBAL_Control
0x18001ea97  cmp     rcx, rax
0x18001ea9a  jz      short loc_18001EACD
0x18001ea9c  test    byte ptr [rcx+1Ch], 4
0x18001eaa0  jz      short loc_18001EACD
0x18001eaa2  mov     rax, [rbp+40h+var_C0]
0x18001eaa6  xor     r9d, r9d
0x18001eaa9  cmp     [rsp+140h+var_F0], 0FFFFh
0x18001eaaf  setz    r9b
0x18001eab3  mov     edx, 1Ch
0x18001eab8  mov     [rsp+140h+var_120], rax
0x18001eabd  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001eac4  mov     rcx, [rcx+10h]
0x18001eac8  call    WPP_SF_dP
0x18001eacd  cmp     [rsp+140h+var_F0], 0FFFFh
0x18001ead3  setz    bl
0x18001ead6  lea     rcx, [rsp+140h+var_D0]
0x18001eadb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001eae0  nop
0x18001eae1  mov     rcx, [rsp+140h+pv]; pv
0x18001eae6  test    rcx, rcx
0x18001eae9  jz      short loc_18001EAFA
0x18001eaeb  call    cs:__imp_CoTaskMemFree
0x18001eaf1  mov     [rsp+140h+pv], 0
0x18001eafa  lea     rcx, [rsp+140h+var_E0]
0x18001eaff  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001eb04  mov     al, bl
0x18001eb06  mov     rcx, [rbp+40h+var_50]
0x18001eb0a  xor     rcx, rsp; StackCookie
0x18001eb0d  call    __security_check_cookie
0x18001eb12  add     rsp, 108h
0x18001eb19  pop     r15
0x18001eb1b  pop     r14
0x18001eb1d  pop     r13
0x18001eb1f  pop     r12
0x18001eb21  pop     rdi
0x18001eb22  pop     rsi
0x18001eb23  pop     rbx
0x18001eb24  pop     rbp
0x18001eb25  retn
```
