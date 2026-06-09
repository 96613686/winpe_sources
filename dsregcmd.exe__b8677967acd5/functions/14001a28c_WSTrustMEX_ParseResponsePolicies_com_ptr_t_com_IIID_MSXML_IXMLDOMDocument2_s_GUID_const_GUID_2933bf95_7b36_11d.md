# WSTrustMEX::ParseResponsePolicies(_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> const &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>> &)

- ea: `0x14001a28c`
- end: `0x14001b3e8`
- name: `?ParseResponsePolicies@WSTrustMEX@@AEAAXAEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@@Z`
- size: `4444`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140019e24`

## callees

- `0x140001cdc`
- `0x140001d44`
- `0x1400020ac`
- `0x1400054e8`
- `0x140005c58`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x140008c34`
- `0x140008ce8`
- `0x140009818`
- `0x14000c8cc`
- `0x14000f208`
- `0x14000f6b0`
- `0x140018d0c`
- `0x140018d98`
- `0x1400193b4`
- `0x140019990`
- `0x140019a5c`
- `0x140019af4`
- `0x140019b8c`
- `0x14001a28c`
- `0x14001b3f0`
- `0x14001b9fc`
- `0x14001c130`
- `0x14001c1b8`
- `0x14001c244`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a68b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a6cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a773`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a68b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a6cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001a773`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14001ad46`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14001ad46`

## string_xrefs

- `0x14001b20d`: `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
- `0x14001b22a`: `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
- `0x14001b183`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue`
- `0x14001b1a0`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue`
- `0x14001a2d0`: `wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp:SignedEncryptedSupportingTokens/wsp:Policy/sp:UsernameToken/wsp:Policy/sp:WssUsernameToken10`
- `0x14001a30d`: `wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp2005:SignedSupportingTokens/wsp:Policy/sp2005:UsernameToken/wsp:Policy/sp2005:WssUsernameToken10`
- `0x14001b297`: `http://schemas.xmlsoap.org/soap/http`
- `0x14001b2b4`: `http://schemas.xmlsoap.org/soap/http`
- `0x14001abdd`: `wsdl:definitions/wsdl:service/wsdl:port`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
__int64 __fastcall WSTrustMEX::ParseResponsePolicies(__int64 a1, struct IUnknown **a2, __int64 *a3)
{
  __int64 *v3; // r14
  struct IUnknown **v4; // rdi
  __int64 v5; // rsi
  unsigned int v6; // r13d
  struct IUnknown *v7; // rbx
  __int64 v8; // rax
  struct IUnknown *v9; // rbx
  __int64 v10; // rax
  struct IUnknown *v11; // rbx
  struct IUnknown *v12; // rbx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  struct IUnknown *v16; // rbx
  int v17; // eax
  struct IUnknown *v18; // rdi
  int v19; // r13d
  _bstr_t *v20; // rax
  struct IUnknown *v21; // r15
  unsigned __int16 ***v22; // rax
  unsigned __int16 *v23; // rdx
  unsigned __int16 *Node; // rdi
  int v25; // eax
  struct IUnknown *v26; // rdi
  int v27; // eax
  struct IUnknown *v28; // rsi
  int v29; // r13d
  _bstr_t *v30; // rax
  struct IUnknown *v31; // r12
  __int64 v32; // rsi
  struct IUnknown *v33; // r14
  _QWORD *v34; // rdx
  int v35; // esi
  _QWORD *v36; // rax
  _QWORD *v37; // rdx
  char v38; // si
  struct IUnknown *v39; // rsi
  _QWORD *v40; // rdx
  int v41; // r13d
  int v42; // eax
  __int64 *v43; // r13
  __int64 v44; // r13
  __int64 v45; // rax
  const char *v46; // r8
  struct IUnknown *v47; // rsi
  struct IUnknown *v48; // rsi
  struct IUnknown *v49; // rsi
  struct IUnknown *v50; // rdi
  struct IUnknown *v51; // rbx
  struct IUnknown *v52; // r14
  int v53; // eax
  unsigned int v54; // r12d
  int v55; // r13d
  int v56; // eax
  struct IUnknown *v57; // rbx
  int v58; // eax
  struct IUnknown *v59; // rdi
  _bstr_t *v60; // rax
  struct IUnknown *v61; // rdi
  _QWORD *v62; // rdx
  int v63; // eax
  wchar_t *v64; // r8
  __int64 v65; // r8
  unsigned __int16 *v66; // rdx
  __int64 v67; // rax
  __int64 v68; // r15
  struct IUnknown *v69; // rsi
  _QWORD *v70; // rdx
  struct IUnknown *v71; // r15
  _QWORD *v72; // rdx
  wchar_t *v73; // rdx
  _QWORD *v74; // rdx
  wchar_t *v75; // rdx
  struct IUnknown *v76; // rsi
  wchar_t *v77; // rdx
  struct IUnknown *v78; // rdi
  __int64 result; // rax
  __int64 v80; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v82; // [rsp+40h] [rbp-C0h]
  __int64 v83; // [rsp+48h] [rbp-B8h] BYREF
  int v84; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v85; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v86; // [rsp+60h] [rbp-A0h]
  struct IUnknown *v87; // [rsp+68h] [rbp-98h] BYREF
  __int64 v88; // [rsp+70h] [rbp-90h] BYREF
  __int64 v89; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown *v90; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v91; // [rsp+88h] [rbp-78h] BYREF
  __int64 v92; // [rsp+90h] [rbp-70h] BYREF
  __int64 v93; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v94; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v95; // [rsp+A8h] [rbp-58h] BYREF
  struct IUnknown *v96; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v97; // [rsp+B8h] [rbp-48h] BYREF
  void *v98[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v99; // [rsp+D0h] [rbp-30h]
  int v100; // [rsp+D4h] [rbp-2Ch]
  int v101; // [rsp+D8h] [rbp-28h]
  int v102; // [rsp+DCh] [rbp-24h]
  __int64 v103; // [rsp+E0h] [rbp-20h]
  __int64 v104; // [rsp+E8h] [rbp-18h]
  int v105; // [rsp+F0h] [rbp-10h]
  int v106; // [rsp+F4h] [rbp-Ch]
  __int64 v107; // [rsp+F8h] [rbp-8h]
  __int64 v108; // [rsp+100h] [rbp+0h]
  struct IUnknown *v109; // [rsp+110h] [rbp+10h]
  _BYTE v110[8]; // [rsp+118h] [rbp+18h] BYREF
  struct IUnknown *v111; // [rsp+120h] [rbp+20h] BYREF
  __int64 v112; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v113[8]; // [rsp+130h] [rbp+30h] BYREF
  struct IUnknown *v114; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v115[8]; // [rsp+140h] [rbp+40h] BYREF
  struct IUnknown *v116; // [rsp+148h] [rbp+48h]
  struct IUnknown *v117; // [rsp+150h] [rbp+50h]
  struct IUnknown *v121; // [rsp+1C8h] [rbp+C8h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = 0;
  v82 = 0;
  v7 = *a2;
  if ( !*a2 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t(
    (_bstr_t *)&v121,
    L"wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp:SignedEncryptedSupportingTokens/wsp:Policy/sp:UsernameToken/ws"
     "p:Policy/sp:WssUsernameToken10");
  v8 = MSXML::IXMLDOMNode::selectNodes(v7);
  WSTrustMEX::ProcessPolicyNodes(v5, v8, v3);
  v9 = *v4;
  if ( !*v4 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t(
    (_bstr_t *)&v121,
    L"wsdl:definitions/wsp:Policy/wsp:ExactlyOne/wsp:All/sp2005:SignedSupportingTokens/wsp:Policy/sp2005:UsernameToken/wsp"
     ":Policy/sp2005:WssUsernameToken10");
  v10 = MSXML::IXMLDOMNode::selectNodes(v9);
  WSTrustMEX::ProcessPolicyNodes(v5, v10, v3);
  WSTrustMEX::SelectWindowsAuthPolicies(v5, v4, v3);
  v11 = *v4;
  if ( !*v4 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t((_bstr_t *)&v121, L"wsdl:definitions/wsdl:binding/wsp:PolicyReference");
  MSXML::IXMLDOMNode::selectNodes(v11);
  v98[0] = 0;
  v98[1] = 0;
  v99 = 17;
  v103 = 0xFFFFFFFFLL;
  v104 = 0;
  v105 = 0;
  v106 = 10;
  v107 = 0;
  v108 = 0;
  v100 = 1061158912;
  v101 = 1048576000;
  v102 = 1074790400;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(v98);
  v12 = v109;
  v86 = v109;
  if ( !v109 )
    _com_issue_error(-2147467261);
  LODWORD(v121) = 0;
  v13 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v109->lpVtbl[2].Release)(v109, &v121);
  if ( v13 < 0 )
    _com_issue_errorex(v13, v12, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  v14 = 0;
  LODWORD(Str) = 0;
  v84 = (int)v121;
  if ( (int)v121 > 0 )
  {
    while ( 1 )
    {
      v121 = 0;
      v15 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v12->lpVtbl[2].AddRef)(
              v12,
              (unsigned int)v14,
              &v121);
      if ( v15 < 0 )
        _com_issue_errorex(v15, v12, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
      v16 = v121;
      v116 = v121;
      if ( !v121 )
        _com_issue_error(-2147467261);
      v121 = 0;
      v17 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v16->lpVtbl[5].Release)(v16, &v121);
      if ( v17 < 0 )
        _com_issue_errorex(v17, v16, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v18 = v121;
      if ( !v121 )
        _com_issue_error(-2147467261);
      v19 = v6 | 6;
      v82 = v19;
      v20 = _bstr_t::_bstr_t((_bstr_t *)v110, L"URI");
      MSXML::IXMLDOMNamedNodeMap::getNamedItem(v18, &v111, v20);
      ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
      v21 = v111;
      if ( v111 )
      {
        v22 = (unsigned __int16 ***)MSXML::IXMLDOMNode::Gettext(v111, &v112);
        if ( *v22 )
          v23 = **v22;
        else
          v23 = 0;
        LODWORD(v80) = 0;
        LODWORD(v121) = 0;
        v85 = 0;
        Node = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(
                 v3,
                 v23,
                 &v80,
                 (unsigned int *)&v121,
                 &v85);
        v85 = Node;
        _bstr_t::~_bstr_t((_bstr_t *)&v112);
        if ( Node )
        {
          v121 = 0;
          v25 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v16->lpVtbl[3].Release)(v16, &v121);
          if ( v25 < 0 )
            _com_issue_errorex(v25, v16, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
          v26 = v121;
          v117 = v121;
          if ( !v121 )
            _com_issue_error(-2147467261);
          v121 = 0;
          v27 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v26->lpVtbl[5].Release)(v26, &v121);
          if ( v27 < 0 )
            _com_issue_errorex(v27, v26, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
          v28 = v121;
          if ( !v121 )
            _com_issue_error(-2147467261);
          v29 = v19 | 0x18;
          v82 = v29;
          v30 = _bstr_t::_bstr_t((_bstr_t *)v113, L"name");
          MSXML::IXMLDOMNamedNodeMap::getNamedItem(v28, &v114, v30);
          ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
          v31 = v114;
          if ( !v114 )
          {
            v49 = (struct IUnknown *)MSXML::IXMLDOMNode::Getxml(v26, &v96);
            v121 = v49;
            Log::WarnInternal(*(_QWORD *)(a1 + 40), 2326331433LL, 1252917273);
            _bstr_t::~_bstr_t((_bstr_t *)v49);
            ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
            ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
            ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
            goto LABEL_67;
          }
          v32 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v83 = v32;
          if ( dword_140047478 > *(_DWORD *)(v32 + 4) )
          {
            Init_thread_header(&dword_140047478);
            if ( dword_140047478 == -1 )
            {
              qword_140047480 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
              if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                      (void *const *)&qword_140047480,
                      (__int64)L"http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue") )
                ATL::CSimpleStringT<unsigned short,0>::SetString(
                  &qword_140047480,
                  L"http://docs.oasis-open.org/ws-sx/ws-trust/200512/RST/Issue",
                  58);
              atexit(WSTrustMEX::ParseResponsePolicies_::_10_::_dynamic_atexit_destructor_for__RSTIssue__);
              Init_thread_footer(&dword_140047478);
            }
          }
          if ( dword_140047488 > *(_DWORD *)(v32 + 4) )
          {
            Init_thread_header(&dword_140047488);
            if ( dword_140047488 == -1 )
            {
              qword_140047490 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
              if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                      (void *const *)&qword_140047490,
                      (__int64)L"http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue") )
                ATL::CSimpleStringT<unsigned short,0>::SetString(
                  &qword_140047490,
                  L"http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue",
                  53);
              atexit(WSTrustMEX::ParseResponsePolicies_::_10_::_dynamic_atexit_destructor_for__RSTIssue2005__);
              Init_thread_footer(&dword_140047488);
            }
          }
          _bstr_t::_bstr_t((_bstr_t *)v115, L"wsdl:operation/soap12:operation/@soapAction");
          MSXML::IXMLDOMNode::selectSingleNode(v26);
          v33 = v87;
          if ( !v87 )
          {
            v48 = (struct IUnknown *)MSXML::IXMLDOMNode::Getxml(v26, &v95);
            v121 = v48;
            Log::WarnInternal(*(_QWORD *)(a1 + 40), 2326331432LL, 1252917273);
            _bstr_t::~_bstr_t((_bstr_t *)v48);
            ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
            ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
            ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
            ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
            goto LABEL_67;
          }
          v34 = (_QWORD *)*MSXML::IXMLDOMNode::Gettext(v87, &v88);
          if ( v34 )
            v34 = (_QWORD *)*v34;
          v35 = _o__wcsicmp(qword_140047480, v34);
          LODWORD(v80) = v35;
          _bstr_t::~_bstr_t((_bstr_t *)&v88);
          if ( !v35 )
            goto LABEL_31;
          v36 = MSXML::IXMLDOMNode::Gettext(v33, &v89);
          v29 |= 1u;
          v82 = v29;
          v37 = (_QWORD *)*v36;
          if ( *v36 )
            v37 = (_QWORD *)*v37;
          if ( (unsigned int)_o__wcsicmp(qword_140047490, v37) )
LABEL_31:
            v38 = 0;
          else
            v38 = 1;
          LOBYTE(v121) = v38;
          if ( (v29 & 1) != 0 )
          {
            v82 = v29 & 0xFFFFFFFE;
            _bstr_t::~_bstr_t((_bstr_t *)&v89);
          }
          if ( !(_DWORD)v80 || v38 )
          {
            if ( dword_140047498 > *(_DWORD *)(v83 + 4) )
            {
              Init_thread_header(&dword_140047498);
              if ( dword_140047498 == -1 )
              {
                qword_1400474A0 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
                if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                        (void *const *)&qword_1400474A0,
                        (__int64)L"http://schemas.xmlsoap.org/soap/http") )
                  ATL::CSimpleStringT<unsigned short,0>::SetString(
                    &qword_1400474A0,
                    L"http://schemas.xmlsoap.org/soap/http",
                    36);
                atexit(WSTrustMEX::ParseResponsePolicies_::_19_::_dynamic_atexit_destructor_for__HTTPTransport__);
                Init_thread_footer(&dword_140047498);
              }
            }
            _bstr_t::_bstr_t((_bstr_t *)&v90, L"soap12:binding/@transport");
            MSXML::IXMLDOMNode::selectSingleNode(v26);
            v39 = v91;
            if ( !v91 )
            {
              v47 = (struct IUnknown *)MSXML::IXMLDOMNode::Getxml(v26, &v94);
              v121 = v47;
              Log::WarnInternal(*(_QWORD *)(a1 + 40), 2326331431LL, 1252917273);
              _bstr_t::~_bstr_t((_bstr_t *)v47);
              ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
              ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
              ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
              ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
              ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
              goto LABEL_67;
            }
            v40 = (_QWORD *)*MSXML::IXMLDOMNode::Gettext(v91, &v92);
            if ( v40 )
              v40 = (_QWORD *)*v40;
            v41 = _o__wcsicmp(qword_1400474A0, v40);
            _bstr_t::~_bstr_t((_bstr_t *)&v92);
            if ( v41 )
            {
LABEL_41:
              ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
              ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
              ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
              ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
              ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
              ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
              goto LABEL_67;
            }
            if ( (_DWORD)v80 )
            {
              if ( !(_BYTE)v121 )
                goto LABEL_41;
              v42 = 1;
            }
            else
            {
              v42 = 2;
            }
            *((_DWORD *)v85 + 7) = v42;
            if ( !v31 )
              _com_issue_error(-2147467261);
            v43 = (__int64 *)*MSXML::IXMLDOMNode::Gettext(v31, &v93);
            if ( v43 )
              v44 = *v43;
            else
              v44 = 0;
            LODWORD(v80) = 0;
            LODWORD(v121) = 0;
            v83 = 0;
            v45 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *>>::GetNode(
                    (unsigned int)v98,
                    v44,
                    (unsigned int)&v80,
                    (unsigned int)&v121,
                    (__int64)&v83);
            if ( !v45 )
            {
              if ( !v98[0] )
              {
                LOBYTE(v46) = 1;
                if ( !ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::InitHashTable(
                        v98,
                        v99,
                        v46) )
                  ATL::AtlThrowImpl(0x8007000E);
              }
              v45 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *>>::NewNode(
                      v98,
                      v44,
                      (unsigned int)v80,
                      (unsigned int)v121);
            }
            *(_QWORD *)(v45 + 8) = v85;
            _bstr_t::~_bstr_t((_bstr_t *)&v93);
            if ( v39 )
              ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
          }
          if ( v33 )
            ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
          ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
          ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->Release)(v26);
        }
        if ( v21 )
          ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
      }
      else
      {
        v50 = (struct IUnknown *)MSXML::IXMLDOMNode::Getxml(v16, &v97);
        v121 = v50;
        Log::WarnInternal(*(_QWORD *)(v5 + 40), 2326331434LL, 1252917273);
        _bstr_t::~_bstr_t((_bstr_t *)v50);
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
      }
LABEL_67:
      v14 = (_DWORD)Str + 1;
      LODWORD(Str) = v14;
      v5 = a1;
      if ( v14 >= v84 )
      {
        v4 = a2;
        break;
      }
      v6 = v82;
      v12 = v86;
      v3 = a3;
    }
  }
  v51 = *v4;
  if ( !*v4 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t((_bstr_t *)&v97, L"wsdl:definitions/wsdl:service/wsdl:port");
  MSXML::IXMLDOMNode::selectNodes(v51);
  v52 = v96;
  if ( !v96 )
    _com_issue_error(-2147467261);
  LODWORD(v121) = 0;
  v53 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v96->lpVtbl[2].Release)(v96, &v121);
  if ( v53 < 0 )
    _com_issue_errorex(v53, v52, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  v54 = 0;
  v55 = (int)v121;
  if ( (int)v121 > 0 )
  {
    while ( 1 )
    {
      v121 = 0;
      v56 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v52->lpVtbl[2].AddRef)(
              v52,
              v54,
              &v121);
      if ( v56 < 0 )
        _com_issue_errorex(v56, v52, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
      v57 = v121;
      v117 = v121;
      if ( !v121 )
        _com_issue_error(-2147467261);
      v121 = 0;
      v58 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v57->lpVtbl[5].Release)(v57, &v121);
      if ( v58 < 0 )
        _com_issue_errorex(v58, v57, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v59 = v121;
      if ( !v121 )
        _com_issue_error(-2147467261);
      v60 = _bstr_t::_bstr_t((_bstr_t *)&v95, L"binding");
      MSXML::IXMLDOMNamedNodeMap::getNamedItem(v59, &v94, v60);
      ((void (__fastcall *)(struct IUnknown *))v59->lpVtbl->Release)(v59);
      v61 = v94;
      if ( !v94 )
      {
        v78 = (struct IUnknown *)MSXML::IXMLDOMNode::Getxml(v57, &v87);
        v121 = v78;
        Log::WarnInternal(*(_QWORD *)(v5 + 40), 2326331430LL, 1252917273);
        _bstr_t::~_bstr_t((_bstr_t *)v78);
        ((void (__fastcall *)(struct IUnknown *))v57->lpVtbl->Release)(v57);
        goto LABEL_108;
      }
      v62 = (_QWORD *)*MSXML::IXMLDOMNode::Gettext(v94, &v93);
      if ( v62 )
        v62 = (_QWORD *)*v62;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &Str,
        (__int64)v62);
      _bstr_t::~_bstr_t((_bstr_t *)&v93);
      v63 = (int)Str;
      if ( *((int *)Str - 4) >= 0 )
      {
        v64 = wcsstr(Str, L":");
        if ( !v64 )
          goto LABEL_86;
        v63 = (int)Str;
        v65 = v64 - Str;
        if ( (int)v65 >= 0 )
          break;
      }
LABEL_87:
      v84 = 0;
      LODWORD(v121) = 0;
      v92 = 0;
      v67 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *>>::GetNode(
              (unsigned int)v98,
              v63,
              (unsigned int)&v84,
              (unsigned int)&v121,
              (__int64)&v92);
      v68 = v67;
      if ( !v67 || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v67 + 8) + 16LL) - 16LL) )
        goto LABEL_101;
      _bstr_t::_bstr_t((_bstr_t *)&v91, L"wsa10:EndpointReference/wsa10:Address");
      MSXML::IXMLDOMNode::selectSingleNode(v57);
      v69 = v90;
      if ( !v90 )
      {
        v76 = (struct IUnknown *)MSXML::IXMLDOMNode::Getxml(v57, &v88);
        v121 = v76;
        Log::WarnInternal(*(_QWORD *)(a1 + 40), 2326331428LL, 1252917273);
        _bstr_t::~_bstr_t((_bstr_t *)v76);
        v77 = Str - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Str - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v77 + 8LL))(*(_QWORD *)v77);
        goto LABEL_106;
      }
      v70 = (_QWORD *)*MSXML::IXMLDOMNode::Gettext(v90, &v83);
      if ( v70 )
        v70 = (_QWORD *)*v70;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v80,
        (__int64)v70);
      _bstr_t::~_bstr_t((_bstr_t *)&v83);
      if ( (unsigned __int8)Url::IsValidAndSecure(&v80) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (_QWORD *)(*(_QWORD *)(v68 + 8) + 16LL),
          &v80);
        v74 = (_QWORD *)(v80 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v80 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v74 + 8LL))(*v74);
        ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
LABEL_101:
        v75 = Str - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)Str - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v75 + 8LL))(*(_QWORD *)v75);
        goto LABEL_106;
      }
      v71 = (struct IUnknown *)MSXML::IXMLDOMNode::Getxml(v57, &v89);
      v121 = v71;
      Log::WarnInternal(*(_QWORD *)(a1 + 40), 2326331429LL, 1252917273);
      _bstr_t::~_bstr_t((_bstr_t *)v71);
      v72 = (_QWORD *)(v80 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v80 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v72 + 8LL))(*v72);
      ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
      v73 = Str - 12;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)Str - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v73 + 8LL))(*(_QWORD *)v73);
LABEL_106:
      ((void (__fastcall *)(struct IUnknown *))v61->lpVtbl->Release)(v61);
      ((void (__fastcall *)(struct IUnknown *))v57->lpVtbl->Release)(v57);
      v5 = a1;
LABEL_108:
      if ( (int)++v54 >= v55 )
        goto LABEL_109;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      &Str,
      &v85,
      (unsigned int)(v65 + 1),
      (unsigned int)(*((_DWORD *)Str - 4) - (v65 + 1)));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &Str,
      &v85);
    v66 = v85 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v85 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v66 + 8LL))(*(_QWORD *)v66);
LABEL_86:
    v63 = (int)Str;
    goto LABEL_87;
  }
LABEL_109:
  ((void (__fastcall *)(struct IUnknown *))v52->lpVtbl->Release)(v52);
  result = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *>>::~CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::CPair *>>(v98);
  if ( v86 )
    return ((__int64 (__fastcall *)(struct IUnknown *))v86->lpVtbl->Release)(v86);
  return result;
}

```

## disassembly

```asm
0x14001a28c  mov     [rsp-8+arg_10], r8
0x14001a291  mov     [rsp-8+arg_8], rdx
0x14001a296  mov     [rsp-8+arg_0], rcx
0x14001a29b  push    rbp
0x14001a29c  push    rbx
0x14001a29d  push    rsi
0x14001a29e  push    rdi
0x14001a29f  push    r12
0x14001a2a1  push    r13
0x14001a2a3  push    r14
0x14001a2a5  push    r15
0x14001a2a7  lea     rbp, [rsp-68h]
0x14001a2ac  sub     rsp, 168h
0x14001a2b3  mov     r14, r8
0x14001a2b6  mov     rdi, rdx
0x14001a2b9  mov     rsi, rcx
0x14001a2bc  xor     r13d, r13d
0x14001a2bf  mov     [rsp+1A0h+var_160], r13d
0x14001a2c4  mov     rbx, [rdx]
0x14001a2c7  test    rbx, rbx
0x14001a2ca  jz      loc_14001B12B
0x14001a2d0  lea     rdx, aWsdlDefinition; "wsdl:definitions/wsp:Policy/wsp:Exactly"...
0x14001a2d7  lea     rcx, [rbp+0A0h+arg_18]; this
0x14001a2de  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001a2e3  mov     r8, rax
0x14001a2e6  lea     rdx, [rsp+1A0h+var_140]
0x14001a2eb  mov     rcx, rbx; struct IUnknown *
0x14001a2ee  call    ?selectNodes@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectNodes(_bstr_t)
0x14001a2f3  mov     r8, r14
0x14001a2f6  mov     rdx, rax
0x14001a2f9  mov     rcx, rsi
0x14001a2fc  call    ?ProcessPolicyNodes@WSTrustMEX@@AEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@@Z; WSTrustMEX::ProcessPolicyNodes(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>> &)
0x14001a301  mov     rbx, [rdi]
0x14001a304  test    rbx, rbx
0x14001a307  jz      loc_14001B120
0x14001a30d  lea     rdx, aWsdlDefinition_1; "wsdl:definitions/wsp:Policy/wsp:Exactly"...
0x14001a314  lea     rcx, [rbp+0A0h+arg_18]; this
0x14001a31b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001a320  mov     r8, rax
0x14001a323  lea     rdx, [rsp+1A0h+var_140]
0x14001a328  mov     rcx, rbx; struct IUnknown *
0x14001a32b  call    ?selectNodes@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectNodes(_bstr_t)
0x14001a330  mov     r8, r14
0x14001a333  mov     rdx, rax
0x14001a336  mov     rcx, rsi
0x14001a339  call    ?ProcessPolicyNodes@WSTrustMEX@@AEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@@Z; WSTrustMEX::ProcessPolicyNodes(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>> &)
0x14001a33e  mov     r8, r14
0x14001a341  mov     rdx, rdi
0x14001a344  mov     rcx, rsi
0x14001a347  call    ?SelectWindowsAuthPolicies@WSTrustMEX@@AEAAXAEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@@Z; WSTrustMEX::SelectWindowsAuthPolicies(_com_ptr_t<_com_IIID<MSXML::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> const &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>> &)
0x14001a34c  mov     rbx, [rdi]
0x14001a34f  test    rbx, rbx
0x14001a352  jz      loc_14001B3DD
0x14001a358  lea     rdx, aWsdlDefinition_3; "wsdl:definitions/wsdl:binding/wsp:Polic"...
0x14001a35f  lea     rcx, [rbp+0A0h+arg_18]; this
0x14001a366  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001a36b  mov     r8, rax
0x14001a36e  lea     rdx, [rbp+0A0h+var_90]
0x14001a372  mov     rcx, rbx; struct IUnknown *
0x14001a375  call    ?selectNodes@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectNodes(_bstr_t)
0x14001a37a  nop
0x14001a37b  mov     [rbp+0A0h+var_E0], r13
0x14001a37f  mov     [rbp+0A0h+var_D8], r13
0x14001a383  mov     [rbp+0A0h+var_D0], 11h
0x14001a38a  mov     eax, 0FFFFFFFFh
0x14001a38f  mov     [rbp+0A0h+var_C0], rax
0x14001a393  mov     [rbp+0A0h+var_B8], r13
0x14001a397  mov     [rbp+0A0h+var_B0], r13d
0x14001a39b  mov     [rbp+0A0h+var_AC], 0Ah
0x14001a3a2  mov     [rbp+0A0h+var_A8], r13
0x14001a3a6  mov     [rbp+0A0h+var_A0], r13
0x14001a3aa  mov     [rbp+0A0h+var_CC], 3F400000h
0x14001a3b1  mov     [rbp+0A0h+var_C8], 3E800000h
0x14001a3b8  mov     [rbp+0A0h+var_C4], 40100000h
0x14001a3bf  lea     rcx, [rbp+0A0h+var_E0]
0x14001a3c3  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UPolicyInfo@WSTrustMEX@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@UPolicyInfo@WSTrustMEX@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,WSTrustMEX::PolicyInfo,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<WSTrustMEX::PolicyInfo>>::UpdateRehashThresholds(void)
0x14001a3c8  nop
0x14001a3c9  mov     rbx, [rbp+0A0h+var_90]
0x14001a3cd  mov     [rsp+1A0h+var_140], rbx
0x14001a3d2  test    rbx, rbx
0x14001a3d5  jz      loc_14001B3D2
0x14001a3db  mov     dword ptr [rbp+0A0h+arg_18], r13d
0x14001a3e2  mov     rax, [rbx]
0x14001a3e5  lea     rdx, [rbp+0A0h+arg_18]
0x14001a3ec  mov     rcx, rbx
0x14001a3ef  mov     rax, [rax+40h]
0x14001a3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3f8  test    eax, eax
0x14001a3fa  js      loc_14001B136
0x14001a400  xor     ecx, ecx
0x14001a402  mov     dword ptr [rsp+1A0h+Str], ecx
0x14001a406  mov     eax, dword ptr [rbp+0A0h+arg_18]
0x14001a40c  mov     [rsp+1A0h+var_150], eax
0x14001a410  test    eax, eax
0x14001a412  jle     loc_14001ABD1
0x14001a418  mov     [rbp+0A0h+arg_18], 0
0x14001a423  mov     rax, [rbx]
0x14001a426  lea     r8, [rbp+0A0h+arg_18]
0x14001a42d  mov     edx, ecx
0x14001a42f  mov     rcx, rbx
0x14001a432  mov     rax, [rax+38h]
0x14001a436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a43b  test    eax, eax
0x14001a43d  js      loc_14001B35E
0x14001a443  mov     rbx, [rbp+0A0h+arg_18]
0x14001a44a  mov     [rbp+0A0h+var_58], rbx
0x14001a44e  test    rbx, rbx
0x14001a451  jz      loc_14001B353
0x14001a457  mov     [rbp+0A0h+arg_18], 0
0x14001a462  mov     rax, [rbx]
0x14001a465  lea     rdx, [rbp+0A0h+arg_18]
0x14001a46c  mov     rcx, rbx
0x14001a46f  mov     rax, [rax+88h]
0x14001a476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a47b  test    eax, eax
0x14001a47d  js      loc_14001B341
0x14001a483  mov     rdi, [rbp+0A0h+arg_18]
0x14001a48a  mov     [rbp+0A0h+arg_18], rdi
0x14001a491  test    rdi, rdi
0x14001a494  jz      loc_14001B336
0x14001a49a  or      r13d, 6
0x14001a49e  mov     [rsp+1A0h+var_160], r13d
0x14001a4a3  lea     rdx, aUri; "URI"
0x14001a4aa  lea     rcx, [rbp+0A0h+var_88]; this
0x14001a4ae  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001a4b3  mov     r8, rax
0x14001a4b6  lea     rdx, [rbp+0A0h+var_80]
0x14001a4ba  mov     rcx, rdi; struct IUnknown *
0x14001a4bd  call    ?getNamedItem@IXMLDOMNamedNodeMap@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNamedNodeMap::getNamedItem(_bstr_t)
0x14001a4c2  nop
0x14001a4c3  mov     rax, [rdi]
0x14001a4c6  mov     rcx, rdi
0x14001a4c9  mov     rax, [rax+10h]
0x14001a4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a4d2  nop
0x14001a4d3  mov     r15, [rbp+0A0h+var_80]
0x14001a4d7  xor     r12d, r12d
0x14001a4da  test    r15, r15
0x14001a4dd  jz      loc_14001AB49
0x14001a4e3  lea     rdx, [rbp+0A0h+var_78]
0x14001a4e7  mov     rcx, r15
0x14001a4ea  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x14001a4ef  mov     rcx, [rax]
0x14001a4f2  test    rcx, rcx
0x14001a4f5  jz      short loc_14001A4FC
0x14001a4f7  mov     rdx, [rcx]
0x14001a4fa  jmp     short loc_14001A4FF
0x14001a4fc  mov     rdx, r12
0x14001a4ff  mov     dword ptr [rsp+1A0h+var_170], r12d
0x14001a504  mov     dword ptr [rbp+0A0h+arg_18], r12d
0x14001a50b  mov     [rsp+1A0h+var_148], r12
0x14001a510  lea     rax, [rsp+1A0h+var_148]
0x14001a515  mov     [rsp+1A0h+var_180], rax
0x14001a51a  lea     r9, [rbp+0A0h+arg_18]
0x14001a521  lea     r8, [rsp+1A0h+var_170]
0x14001a526  mov     rcx, r14
0x14001a529  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VItem@TokenCache@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VItem@TokenCache@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,TokenCache::Item,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<TokenCache::Item>>::CNode * &)
0x14001a52e  mov     rdi, rax
0x14001a531  mov     [rsp+1A0h+var_148], rax
0x14001a536  lea     rcx, [rbp+0A0h+var_78]; this
0x14001a53a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001a53f  test    rdi, rdi
0x14001a542  jz      loc_14001A90A
0x14001a548  mov     [rbp+0A0h+arg_18], r12
0x14001a54f  mov     rcx, [rbx]
0x14001a552  mov     rax, [rcx+58h]
0x14001a556  lea     rdx, [rbp+0A0h+arg_18]
0x14001a55d  mov     rcx, rbx
0x14001a560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a565  test    eax, eax
0x14001a567  js      loc_14001B324
0x14001a56d  mov     rdi, [rbp+0A0h+arg_18]
0x14001a574  mov     [rbp+0A0h+var_50], rdi
0x14001a578  test    rdi, rdi
0x14001a57b  jz      loc_14001B319
0x14001a581  mov     [rbp+0A0h+arg_18], r12
0x14001a588  mov     rax, [rdi]
0x14001a58b  lea     rdx, [rbp+0A0h+arg_18]
0x14001a592  mov     rcx, rdi
0x14001a595  mov     rax, [rax+88h]
0x14001a59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5a1  test    eax, eax
0x14001a5a3  js      loc_14001B307
0x14001a5a9  mov     rsi, [rbp+0A0h+arg_18]
0x14001a5b0  mov     [rbp+0A0h+arg_18], rsi
0x14001a5b7  test    rsi, rsi
0x14001a5ba  jz      loc_14001B2FC
0x14001a5c0  or      r13d, 18h
0x14001a5c4  mov     [rsp+1A0h+var_160], r13d
0x14001a5c9  lea     rdx, aName; "name"
0x14001a5d0  lea     rcx, [rbp+0A0h+var_70]; this
0x14001a5d4  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001a5d9  mov     r8, rax
0x14001a5dc  lea     rdx, [rbp+0A0h+var_68]
0x14001a5e0  mov     rcx, rsi; struct IUnknown *
0x14001a5e3  call    ?getNamedItem@IXMLDOMNamedNodeMap@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNamedNodeMap::getNamedItem(_bstr_t)
0x14001a5e8  nop
0x14001a5e9  mov     rax, [rsi]
0x14001a5ec  mov     rcx, rsi
0x14001a5ef  mov     rax, [rax+10h]
0x14001a5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5f8  nop
0x14001a5f9  mov     r12, [rbp+0A0h+var_68]
0x14001a5fd  test    r12, r12
0x14001a600  jz      loc_14001AACC
0x14001a606  mov     r14d, 4
0x14001a60c  mov     rax, gs:58h
0x14001a615  mov     rsi, [rax]
0x14001a618  mov     [rsp+1A0h+var_158], rsi
0x14001a61d  mov     eax, [r14+rsi]
0x14001a621  cmp     cs:dword_140047478, eax
0x14001a627  jg      loc_14001B148
0x14001a62d  mov     eax, [r14+rsi]
0x14001a631  cmp     cs:dword_140047488, eax
0x14001a637  jg      loc_14001B1D2
0x14001a63d  lea     rdx, aWsdlOperationS; "wsdl:operation/soap12:operation/@soapAc"...
0x14001a644  lea     rcx, [rbp+0A0h+var_60]; this
0x14001a648  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001a64d  mov     r8, rax
0x14001a650  lea     rdx, [rsp+1A0h+var_138]
0x14001a655  mov     rcx, rdi; struct IUnknown *
0x14001a658  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x14001a65d  nop
0x14001a65e  mov     r14, [rsp+1A0h+var_138]
0x14001a663  test    r14, r14
0x14001a666  jz      loc_14001AA3B
0x14001a66c  lea     rdx, [rsp+1A0h+var_130]
0x14001a671  mov     rcx, r14
0x14001a674  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x14001a679  mov     rdx, [rax]
0x14001a67c  test    rdx, rdx
0x14001a67f  jz      short loc_14001A684
0x14001a681  mov     rdx, [rdx]
0x14001a684  mov     rcx, cs:qword_140047480
0x14001a68b  call    cs:__imp__o__wcsicmp
0x14001a691  mov     esi, eax
0x14001a693  mov     dword ptr [rsp+1A0h+var_170], eax
0x14001a697  lea     rcx, [rsp+1A0h+var_130]; this
0x14001a69c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001a6a1  test    esi, esi
0x14001a6a3  jz      short loc_14001A6DC
0x14001a6a5  lea     rdx, [rsp+1A0h+var_128]
0x14001a6aa  mov     rcx, r14
0x14001a6ad  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x14001a6b2  or      r13d, 1
0x14001a6b6  mov     [rsp+1A0h+var_160], r13d
0x14001a6bb  mov     rdx, [rax]
0x14001a6be  test    rdx, rdx
0x14001a6c1  jz      short loc_14001A6C6
0x14001a6c3  mov     rdx, [rdx]
0x14001a6c6  mov     rcx, cs:qword_140047490
0x14001a6cd  call    cs:__imp__o__wcsicmp
0x14001a6d3  test    eax, eax
0x14001a6d5  jnz     short loc_14001A6DC
0x14001a6d7  mov     sil, 1
0x14001a6da  jmp     short loc_14001A6DF
0x14001a6dc  xor     sil, sil
0x14001a6df  mov     byte ptr [rbp+0A0h+arg_18], sil
0x14001a6e6  test    r13b, 1
0x14001a6ea  jz      short loc_14001A6FF
0x14001a6ec  and     r13d, 0FFFFFFFEh
0x14001a6f0  mov     [rsp+1A0h+var_160], r13d
0x14001a6f5  lea     rcx, [rsp+1A0h+var_128]; this
0x14001a6fa  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001a6ff  cmp     dword ptr [rsp+1A0h+var_170], 0
0x14001a704  jz      short loc_14001A70F
0x14001a706  test    sil, sil
0x14001a709  jz      loc_14001A8D4
0x14001a70f  mov     rax, [rsp+1A0h+var_158]
0x14001a714  mov     ecx, 4
0x14001a719  mov     eax, [rcx+rax]
0x14001a71c  cmp     cs:dword_140047498, eax
0x14001a722  jg      loc_14001B25C
0x14001a728  lea     rdx, aSoap12BindingT; "soap12:binding/@transport"
0x14001a72f  lea     rcx, [rbp+0A0h+var_120]; this
0x14001a733  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001a738  mov     r8, rax
0x14001a73b  lea     rdx, [rbp+0A0h+var_118]
0x14001a73f  mov     rcx, rdi; struct IUnknown *
0x14001a742  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x14001a747  nop
0x14001a748  mov     rsi, [rbp+0A0h+var_118]
0x14001a74c  test    rsi, rsi
0x14001a74f  jz      loc_14001A99A
0x14001a755  lea     rdx, [rbp+0A0h+var_110]
0x14001a759  mov     rcx, rsi
0x14001a75c  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x14001a761  mov     rdx, [rax]
0x14001a764  test    rdx, rdx
0x14001a767  jz      short loc_14001A76C
0x14001a769  mov     rdx, [rdx]
0x14001a76c  mov     rcx, cs:qword_1400474A0
0x14001a773  call    cs:__imp__o__wcsicmp
0x14001a779  mov     r13d, eax
0x14001a77c  lea     rcx, [rbp+0A0h+var_110]; this
0x14001a780  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001a785  test    r13d, r13d
0x14001a788  jz      short loc_14001A7F0
0x14001a78a  mov     rax, [rsi]
0x14001a78d  mov     rcx, rsi
  ... truncated ...
```
