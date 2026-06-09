# WSTrustMEX::CheckPolicy(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> const &)

- ea: `0x1400196f4`
- end: `0x140019988`
- name: `?CheckPolicy@WSTrustMEX@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `660`
- prototype: `void **__fastcall(__int64, void **, struct IUnknown **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001b3f0`
- `0x14001b9fc`

## callees

- `0x1400054e8`
- `0x140005c80`
- `0x1400061dc`
- `0x140018d0c`
- `0x1400193b4`
- `0x1400196f4`
- `0x140019a5c`
- `0x14001c130`
- `0x14001c244`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void **__fastcall WSTrustMEX::CheckPolicy(__int64 a1, void **a2, struct IUnknown **a3)
{
  struct IUnknown *v5; // rsi
  struct IUnknown *v6; // rsi
  __int64 *v7; // rax
  __int64 v8; // rcx
  void **result; // rax
  struct IUnknown *v10; // rdi
  int v11; // eax
  struct IUnknown *v12; // rdi
  __int64 *v13; // rax
  __int64 v14; // rdx
  struct IUnknown *v15; // rbx
  struct IUnknown v16; // rcx
  __int64 v17; // [rsp+28h] [rbp-40h]
  _BYTE v18[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+38h] [rbp-30h] BYREF
  const COMException *v20; // [rsp+40h] [rbp-28h] BYREF
  __int64 v23; // [rsp+80h] [rbp+18h] BYREF
  struct IUnknown *v24; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    v5 = *a3;
    if ( !*a3 )
      _com_issue_error(-2147467261);
    _bstr_t::_bstr_t((_bstr_t *)v18, L"wsp:ExactlyOne/wsp:All/sp:TransportBinding");
    MSXML::IXMLDOMNode::selectSingleNode(v5);
    if ( v23 )
      goto LABEL_16;
    v6 = *a3;
    if ( !*a3 )
      _com_issue_error(-2147467261);
    _bstr_t::_bstr_t((_bstr_t *)&v24, L"wsp:ExactlyOne/wsp:All/sp2005:TransportBinding");
    v7 = (__int64 *)MSXML::IXMLDOMNode::selectSingleNode(v6);
    v8 = v23;
    if ( v23 != *v7 )
    {
      v23 = *v7;
      *v7 = 0;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v23 )
    {
LABEL_16:
      v10 = *a3;
      if ( !v10 )
        _com_issue_error(-2147467261);
      v24 = 0;
      v11 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v10->lpVtbl[5].Release)(v10, &v24);
      if ( v11 < 0 )
        _com_issue_errorex(v11, v10, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
      v12 = v24;
      if ( !v24 )
        _com_issue_error(-2147467261);
      _bstr_t::_bstr_t((_bstr_t *)&v19, L"wsu:Id");
      MSXML::IXMLDOMNamedNodeMap::getNamedItem(v12);
      ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->Release)(v12);
      if ( !v17 )
        _com_issue_error(-2147467261);
      v13 = *(__int64 **)MSXML::IXMLDOMNode::Gettext(v17, &v24);
      if ( v13 )
        v14 = *v13;
      else
        v14 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        a2,
        v14);
      _bstr_t::~_bstr_t((_bstr_t *)&v24);
      (*(void (__fastcall **)())(*(_QWORD *)v17 + 16LL))();
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      result = a2;
    }
    else
    {
      *a2 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
              a2,
              (__int64)&dword_14003353C) )
        ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &dword_14003353C, 0);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      result = a2;
    }
  }
  catch ( const COMException *v20 )
  {
    v15 = (struct IUnknown *)(*(__int64 (__fastcall **)(const COMException *, __int64 *))(*(_QWORD *)v20 + 8LL))(
                               v20,
                               &v23);
    v24 = v15;
    Log::WarnInternal(*(_QWORD *)(a1 + 40), 2326331425LL, 1252917272);
    v16.lpVtbl = v15->lpVtbl;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v15->lpVtbl[-1].Release, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(HRESULT (__stdcall *)(IUnknown *, const IID *const, void **), struct IUnknownVtbl *))(*(_QWORD *)v16.lpVtbl[-1].QueryInterface + 8LL))(
        v16.lpVtbl[-1].QueryInterface,
        v16.lpVtbl - 1);
    *a2 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
            a2,
            (__int64)&dword_14003353C) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &dword_14003353C, 0);
    return a2;
  }
  v5 = *a3;
}

```

## disassembly

```asm
0x1400196f4  mov     [rsp+arg_8], rdx
0x1400196f9  mov     [rsp+arg_0], rcx
0x1400196fe  push    rbx
0x1400196ff  push    rsi
0x140019700  push    rdi
0x140019701  sub     rsp, 50h
0x140019705  mov     rdi, r8
0x140019708  mov     rbx, rdx
0x14001970b  mov     rsi, [r8]
0x14001970e  test    rsi, rsi
0x140019711  jz      loc_14001997C
0x140019717  lea     rdx, aWspExactlyoneW; "wsp:ExactlyOne/wsp:All/sp:TransportBind"...
0x14001971e  lea     rcx, [rsp+68h+var_38]; this
0x140019723  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140019728  mov     r8, rax
0x14001972b  lea     rdx, [rsp+68h+arg_10]
0x140019733  mov     rcx, rsi; struct IUnknown *
0x140019736  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x14001973b  nop
0x14001973c  cmp     [rsp+68h+arg_10], 0
0x140019745  jnz     loc_140019835
0x14001974b  mov     rsi, [rdi]
0x14001974e  test    rsi, rsi
0x140019751  jz      loc_14001993F
0x140019757  lea     rdx, aWspExactlyoneW_0; "wsp:ExactlyOne/wsp:All/sp2005:Transport"...
0x14001975e  lea     rcx, [rsp+68h+arg_18]; this
0x140019766  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14001976b  mov     r8, rax
0x14001976e  lea     rdx, [rsp+68h+var_30]
0x140019773  mov     rcx, rsi; struct IUnknown *
0x140019776  call    ?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)
0x14001977b  nop
0x14001977c  mov     rdx, [rax]
0x14001977f  mov     rcx, [rsp+68h+arg_10]
0x140019787  cmp     rcx, rdx
0x14001978a  jz      short loc_1400197AD
0x14001978c  mov     [rsp+68h+arg_10], rdx
0x140019794  mov     qword ptr [rax], 0
0x14001979b  test    rcx, rcx
0x14001979e  jz      short loc_1400197AD
0x1400197a0  mov     rax, [rcx]
0x1400197a3  mov     rax, [rax+10h]
0x1400197a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400197ac  nop
0x1400197ad  mov     rcx, [rsp+68h+var_30]
0x1400197b2  test    rcx, rcx
0x1400197b5  jz      short loc_1400197C4
0x1400197b7  mov     rax, [rcx]
0x1400197ba  mov     rax, [rax+10h]
0x1400197be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400197c3  nop
0x1400197c4  cmp     [rsp+68h+arg_10], 0
0x1400197cd  jnz     short loc_140019835
0x1400197cf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400197d6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400197dd  mov     rax, [rax+18h]
0x1400197e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400197e6  add     rax, 18h
0x1400197ea  mov     [rbx], rax
0x1400197ed  lea     rdx, dword_14003353C
0x1400197f4  mov     rcx, rbx
0x1400197f7  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1400197fc  test    al, al
0x1400197fe  jnz     short loc_140019813
0x140019800  xor     r8d, r8d
0x140019803  lea     rdx, dword_14003353C
0x14001980a  mov     rcx, rbx
0x14001980d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140019812  nop
0x140019813  mov     rcx, [rsp+68h+arg_10]
0x14001981b  test    rcx, rcx
0x14001981e  jz      short loc_14001982D
0x140019820  mov     rax, [rcx]
0x140019823  mov     rax, [rax+10h]
0x140019827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001982c  nop
0x14001982d  mov     rax, rbx
0x140019830  jmp     loc_140019937
0x140019835  mov     rdi, [rdi]
0x140019838  test    rdi, rdi
0x14001983b  jz      loc_140019971
0x140019841  mov     [rsp+68h+arg_18], 0
0x14001984d  mov     rax, [rdi]
0x140019850  lea     rdx, [rsp+68h+arg_18]
0x140019858  mov     rcx, rdi
0x14001985b  mov     rax, [rax+88h]
0x140019862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019867  test    eax, eax
0x140019869  js      loc_140019949
0x14001986f  mov     rdi, [rsp+68h+arg_18]
0x140019877  mov     [rsp+68h+arg_18], rdi
0x14001987f  test    rdi, rdi
0x140019882  jz      loc_140019966
0x140019888  lea     rdx, aWsuId; "wsu:Id"
0x14001988f  lea     rcx, [rsp+68h+var_30]; this
0x140019894  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140019899  mov     r8, rax
0x14001989c  lea     rdx, [rsp+68h+var_40]
0x1400198a1  mov     rcx, rdi; struct IUnknown *
0x1400198a4  call    ?getNamedItem@IXMLDOMNamedNodeMap@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNamedNodeMap::getNamedItem(_bstr_t)
0x1400198a9  nop
0x1400198aa  mov     rax, [rdi]
0x1400198ad  mov     rcx, rdi
0x1400198b0  mov     rax, [rax+10h]
0x1400198b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400198b9  nop
0x1400198ba  mov     rcx, [rsp+68h+var_40]
0x1400198bf  test    rcx, rcx
0x1400198c2  jz      loc_14001995B
0x1400198c8  lea     rdx, [rsp+68h+arg_18]
0x1400198d0  call    ?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ; MSXML::IXMLDOMNode::Gettext(void)
0x1400198d5  nop
0x1400198d6  mov     rax, [rax]
0x1400198d9  test    rax, rax
0x1400198dc  jz      short loc_1400198E3
0x1400198de  mov     rdx, [rax]
0x1400198e1  jmp     short loc_1400198E5
0x1400198e3  xor     edx, edx
0x1400198e5  mov     rcx, rbx
0x1400198e8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400198ed  nop
0x1400198ee  lea     rcx, [rsp+68h+arg_18]; this
0x1400198f6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400198fb  nop
0x1400198fc  mov     rcx, [rsp+68h+var_40]
0x140019901  test    rcx, rcx
0x140019904  jz      short loc_140019913
0x140019906  mov     rax, [rcx]
0x140019909  mov     rax, [rax+10h]
0x14001990d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019912  nop
0x140019913  mov     rcx, [rsp+68h+arg_10]
0x14001991b  test    rcx, rcx
0x14001991e  jz      short loc_14001992D
0x140019920  mov     rax, [rcx]
0x140019923  mov     rax, [rax+10h]
0x140019927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001992c  nop
0x14001992d  mov     rax, rbx
0x140019930  jmp     short loc_140019937
0x140019932  mov     rax, [rsp+68h+arg_8]
0x140019937  add     rsp, 50h
0x14001993b  pop     rdi
0x14001993c  pop     rsi
0x14001993d  pop     rbx
0x14001993e  retn
0x14001993f  mov     ecx, 80004003h; int
0x140019944  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140019949  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x140019950  mov     rdx, rdi; struct IUnknown *
0x140019953  mov     ecx, eax; int
0x140019955  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14001995b  mov     ecx, 80004003h; int
0x140019960  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140019966  mov     ecx, 80004003h; int
0x14001996b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140019971  mov     ecx, 80004003h; int
0x140019976  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14001997c  mov     ecx, 80004003h; int
0x140019981  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
