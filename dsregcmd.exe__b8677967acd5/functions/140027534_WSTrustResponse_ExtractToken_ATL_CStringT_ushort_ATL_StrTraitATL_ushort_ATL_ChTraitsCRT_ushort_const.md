# WSTrustResponse::ExtractToken(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140027534`
- end: `0x140027745`
- name: `?ExtractToken@WSTrustResponse@@QEBA?AVCSecureString@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `529`
- prototype: `_QWORD *__fastcall(const unsigned __int16 **, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140026f30`

## callees

- `0x14000579c`
- `0x140007bf8`
- `0x140018d0c`
- `0x14001c1b8`
- `0x140027534`
- `0x14002774c`
- `0x140028040`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## string_xrefs

- `0x140027583`: `xmlns:S='http://www.w3.org/2003/05/soap-envelope' xmlns:trust='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:trust2005='http://schemas.xmlsoap.org/ws/2005/02/trust' `
- `0x1400275a4`: `S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse/trust:TokenType`
- `0x140027602`: `/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse/trust2005:TokenType`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall WSTrustResponse::ExtractToken(const unsigned __int16 **a1, _QWORD *a2, __int64 a3)
{
  struct IUnknown *v6; // rbx
  struct IUnknown *v7; // rdi
  int v8; // eax
  struct IUnknown *v9; // rbx
  struct IUnknown **v10; // rax
  struct IUnknown *v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  struct IUnknown *v16; // [rsp+28h] [rbp-28h] BYREF
  struct IUnknown *v17; // [rsp+30h] [rbp-20h]
  _BYTE v18[8]; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-10h] BYREF
  struct IUnknown *v20; // [rsp+88h] [rbp+38h] BYREF

  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  MSXML::Create(
    &v16,
    *a1,
    L"xmlns:S='http://www.w3.org/2003/05/soap-envelope' xmlns:trust='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xml"
     "ns:trust2005='http://schemas.xmlsoap.org/ws/2005/02/trust' ");
  v6 = v16;
  if ( !v16 )
    _com_issue_error(-2147467261);
  _bstr_t::_bstr_t(
    (_bstr_t *)v18,
    L"S:Envelope/S:Body/trust:RequestSecurityTokenResponseCollection/trust:RequestSecurityTokenResponse/trust:TokenType");
  MSXML::IXMLDOMNode::selectNodes(v6);
  v7 = v17;
  if ( !v17 )
    goto LABEL_5;
  LODWORD(v20) = 0;
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v17->lpVtbl[2].Release)(v17, &v20);
  if ( v8 < 0 )
    _com_issue_errorex(v8, v7, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
  if ( !(_DWORD)v20 )
  {
LABEL_5:
    v9 = v16;
    if ( !v16 )
      _com_issue_error(-2147467261);
    _bstr_t::_bstr_t((_bstr_t *)&v20, L"/S:Envelope/S:Body/trust2005:RequestSecurityTokenResponse/trust2005:TokenType");
    v10 = (struct IUnknown **)MSXML::IXMLDOMNode::selectNodes(v9);
    if ( v7 != *v10 )
    {
      v11 = v7;
      v7 = *v10;
      v17 = *v10;
      *v10 = 0;
      if ( v11 )
        ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
    }
    if ( v19[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
  }
  if ( v7 )
  {
    LODWORD(v20) = 0;
    v12 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v7->lpVtbl[2].Release)(v7, &v20);
    if ( v12 < 0 )
      _com_issue_errorex(v12, v7, &GUID_2933bf82_7b36_11d2_b20e_00c04f983e60);
    if ( (int)v20 > 0 )
    {
      v20 = v7;
      ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->AddRef)(v7);
      v14 = (_QWORD *)WSTrustResponse::ExtractTokenFromXmlNodes(v13, v19, &v20, a3, 1);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        a2,
        v14);
      CSecureString::~CSecureString((CSecureString *)v19);
    }
  }
  if ( v7 )
    ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
  if ( v16 )
    ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
  return a2;
}

```

## disassembly

```asm
0x140027534  mov     [rsp-18h+arg_0], rbx
0x140027539  mov     [rsp-18h+arg_10], rsi
0x14002753e  mov     [rsp-18h+arg_8], rdx
0x140027543  push    rbp
0x140027544  push    rdi
0x140027545  push    r14
0x140027547  mov     rbp, rsp
0x14002754a  sub     rsp, 50h
0x14002754e  mov     r14, r8
0x140027551  mov     rsi, rdx
0x140027554  mov     rbx, rcx
0x140027557  mov     [rbp+var_30], 0
0x14002755e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140027565  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002756c  mov     rax, [rax+18h]
0x140027570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027575  add     rax, 18h
0x140027579  mov     [rsi], rax
0x14002757c  mov     [rbp+var_30], 1
0x140027583  lea     r8, aXmlnsSHttpWwwW; "xmlns:S='http://www.w3.org/2003/05/soap"...
0x14002758a  mov     rdx, [rbx]
0x14002758d  lea     rcx, [rbp+var_28]
0x140027591  call    ?Create@MSXML@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG0@Z; MSXML::Create(ushort const *,ushort const *)
0x140027596  nop
0x140027597  mov     rbx, [rbp+var_28]
0x14002759b  test    rbx, rbx
0x14002759e  jz      loc_140027716
0x1400275a4  lea     rdx, aSEnvelopeSBody_2; "S:Envelope/S:Body/trust:RequestSecurity"...
0x1400275ab  lea     rcx, [rbp+var_18]; this
0x1400275af  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1400275b4  mov     r8, rax
0x1400275b7  lea     rdx, [rbp+var_20]
0x1400275bb  mov     rcx, rbx; struct IUnknown *
0x1400275be  call    ?selectNodes@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectNodes(_bstr_t)
0x1400275c3  nop
0x1400275c4  mov     rdi, [rbp+var_20]
0x1400275c8  test    rdi, rdi
0x1400275cb  jz      short loc_1400275F5
0x1400275cd  mov     dword ptr [rbp+arg_18], 0
0x1400275d4  mov     rax, [rdi]
0x1400275d7  lea     rdx, [rbp+arg_18]
0x1400275db  mov     rcx, rdi
0x1400275de  mov     rax, [rax+40h]
0x1400275e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400275e7  test    eax, eax
0x1400275e9  js      loc_140027721
0x1400275ef  cmp     dword ptr [rbp+arg_18], 0
0x1400275f3  jnz     short loc_140027660
0x1400275f5  mov     rbx, [rbp+var_28]
0x1400275f9  test    rbx, rbx
0x1400275fc  jz      loc_14002770B
0x140027602  lea     rdx, aSEnvelopeSBody_1; "/S:Envelope/S:Body/trust2005:RequestSec"...
0x140027609  lea     rcx, [rbp+arg_18]; this
0x14002760d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140027612  mov     r8, rax
0x140027615  lea     rdx, [rbp+var_10]
0x140027619  mov     rcx, rbx; struct IUnknown *
0x14002761c  call    ?selectNodes@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z; MSXML::IXMLDOMNode::selectNodes(_bstr_t)
0x140027621  nop
0x140027622  cmp     rdi, [rax]
0x140027625  jz      short loc_14002764A
0x140027627  mov     rcx, rdi
0x14002762a  mov     rdi, [rax]
0x14002762d  mov     [rbp+var_20], rdi
0x140027631  mov     qword ptr [rax], 0
0x140027638  test    rcx, rcx
0x14002763b  jz      short loc_14002764A
0x14002763d  mov     rax, [rcx]
0x140027640  mov     rax, [rax+10h]
0x140027644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027649  nop
0x14002764a  mov     rcx, [rbp+var_10]
0x14002764e  test    rcx, rcx
0x140027651  jz      short loc_140027660
0x140027653  mov     rax, [rcx]
0x140027656  mov     rax, [rax+10h]
0x14002765a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002765f  nop
0x140027660  test    rdi, rdi
0x140027663  jz      short loc_1400276C8
0x140027665  mov     dword ptr [rbp+arg_18], 0
0x14002766c  mov     rax, [rdi]
0x14002766f  lea     rdx, [rbp+arg_18]
0x140027673  mov     rcx, rdi
0x140027676  mov     rax, [rax+40h]
0x14002767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002767f  test    eax, eax
0x140027681  js      loc_140027733
0x140027687  cmp     dword ptr [rbp+arg_18], 0
0x14002768b  jle     short loc_1400276C8
0x14002768d  mov     [rbp+arg_18], rdi
0x140027691  mov     rax, [rdi]
0x140027694  mov     rcx, rdi
0x140027697  mov     rax, [rax+8]
0x14002769b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400276a0  nop
0x1400276a1  mov     r9, r14
0x1400276a4  lea     r8, [rbp+arg_18]
0x1400276a8  lea     rdx, [rbp+var_10]
0x1400276ac  call    ?ExtractTokenFromXmlNodes@WSTrustResponse@@AEBA?AVCSecureString@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WSTrustResponse::ExtractTokenFromXmlNodes(_com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400276b1  nop
0x1400276b2  mov     rdx, rax
0x1400276b5  mov     rcx, rsi
0x1400276b8  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400276bd  nop
0x1400276be  lea     rcx, [rbp+var_10]; this
0x1400276c2  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400276c7  nop
0x1400276c8  test    rdi, rdi
0x1400276cb  jz      short loc_1400276DD
0x1400276cd  mov     rax, [rdi]
0x1400276d0  mov     rcx, rdi
0x1400276d3  mov     rax, [rax+10h]
0x1400276d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400276dc  nop
0x1400276dd  mov     rcx, [rbp+var_28]
0x1400276e1  test    rcx, rcx
0x1400276e4  jz      short loc_1400276F3
0x1400276e6  mov     rax, [rcx]
0x1400276e9  mov     rax, [rax+10h]
0x1400276ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400276f2  nop
0x1400276f3  mov     rax, rsi
0x1400276f6  lea     r11, [rsp+50h+var_s0]
0x1400276fb  mov     rbx, [r11+20h]
0x1400276ff  mov     rsi, [r11+30h]
0x140027703  mov     rsp, r11
0x140027706  pop     r14
0x140027708  pop     rdi
0x140027709  pop     rbp
0x14002770a  retn
0x14002770b  mov     ecx, 80004003h; int
0x140027710  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140027716  mov     ecx, 80004003h; int
0x14002771b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140027721  lea     r8, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x140027728  mov     rdx, rdi; struct IUnknown *
0x14002772b  mov     ecx, eax; int
0x14002772d  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x140027733  lea     r8, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14002773a  mov     rdx, rdi; struct IUnknown *
0x14002773d  mov     ecx, eax; int
0x14002773f  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
