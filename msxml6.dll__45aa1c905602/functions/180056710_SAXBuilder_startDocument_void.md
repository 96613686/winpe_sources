# SAXBuilder::startDocument(void)

- ea: `0x180056710`
- end: `0x180056cac`
- name: `?startDocument@SAXBuilder@@UEAAJXZ`
- size: `1436`
- prototype: `HRESULT __fastcall(SAXBuilder *this)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180166c10`
- `0x180166c20`

## callees

- `0x180015a80`
- `0x1800199ec`
- `0x180019cd0`
- `0x180019e20`
- `0x18001aff8`
- `0x180030768`
- `0x180031f60`
- `0x180032de8`
- `0x180032e04`
- `0x18003446c`
- `0x180056710`
- `0x180056cb4`
- `0x180058e94`
- `0x18009fefc`
- `0x1800a3c08`
- `0x1800bcbac`
- `0x1800bda40`
- `0x1800c55c8`
- `0x1800d82c0`
- `0x180165ea0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056781`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056781`
- `OLEAUT32!__imp_VariantClear` at `0x180056a50`
- `OLEAUT32!__imp_VariantClear` at `0x180056b0e`
- `OLEAUT32!__imp_VariantClear` at `0x180056bd6`
- `OLEAUT32!__imp_VariantClear` at `0x180056a50`
- `OLEAUT32!__imp_VariantClear` at `0x180056b0e`
- `OLEAUT32!__imp_VariantClear` at `0x180056bd6`

## string_xrefs

- `0x18005694b`: `xmldecl-version`
- `0x180056b34`: `xmldecl-standalone`
- `0x180056a6c`: `xmldecl-encoding`

## pseudocode

```c
__int64 __fastcall SAXBuilder::startDocument(SAXBuilder *this)
{
  Document *p; // rdi
  _reference<NamespaceMgr> *p_pNSMgr; // r14
  NodeBuilder *v5; // rax
  NodeBuilder *v6; // rax
  StringBuffer *v7; // rax
  StringBuffer *v8; // rax
  IMXRAttributes *v9; // rcx
  ISAXLocator *v10; // rcx
  ISAXLocator *v11; // rcx
  HRESULT v12; // eax
  const wchar_t *v13; // rax
  int v14; // edx
  unsigned __int64 v15; // rcx
  String *v16; // rbx
  NameDef *NameDef; // rax
  NameDef *v18; // rdi
  String *v19; // rbx
  NamespaceMgr *v20; // rbx
  Name *v21; // rax
  NameDef *v22; // rdi
  String *v23; // rbx
  NamespaceMgr *v24; // rbx
  Name *v25; // rax
  NameDef *v26; // rdi
  String *v27; // rbx
  _weakreference<Node> pNewNode; // [rsp+40h] [rbp-88h] BYREF
  const wchar_t *pwszUrl; // [rsp+48h] [rbp-80h] BYREF
  _weakreference<Node> pEncNode; // [rsp+50h] [rbp-78h] BYREF
  _weakreference<Node> pStdNode; // [rsp+58h] [rbp-70h] BYREF
  const wchar_t *v32; // [rsp+60h] [rbp-68h]
  unsigned __int64 v33; // [rsp+68h] [rbp-60h]
  tagVARIANT v; // [rsp+70h] [rbp-58h] BYREF
  _reference<String> s; // [rsp+D8h] [rbp+10h] BYREF
  _weakreference<Node> pXmlDecl; // [rsp+E0h] [rbp+18h] BYREF
  ISAXXMLReader *pReader; // [rsp+E8h] [rbp+20h] BYREF

  if ( !(__int64)g_pfnEntry() )
    return 2147500037LL;
  s._p = 0;
  p = this->_pDocument._p;
  this->_fFirstElementReached = 0;
  p_pNSMgr = &this->_pNSMgr;
  assign(&this->_pNSMgr._p, p->_pNamespaceMgr._p);
  v5 = (NodeBuilder *)HeapAlloc(g_hMsxmlHeap, 0xCu, 0xC0u);
  if ( !v5 )
  {
    failure_tracing::record();
    Exception::throw_E_OUTOFMEMORY();
  }
  NodeBuilder::NodeBuilder(v5, p);
  this->_pBuilder = v6;
  NodeBuilder::startDocument(v6, &this->NodeBuilder::ParserCallbacks);
  weakAssign(&this->_pParentNode._p, p->_pDocNode._p);
  v7 = this->_pCDATABuffer._p;
  if ( v7 )
    v7->_length = 0;
  v8 = this->_pDocTypeSubsetBuffer._p;
  if ( v8 )
    v8->_length = 0;
  this->_fError = 0;
  this->_eState = SAXBuilder_Document;
  this->_nEntityDepth = 0;
  v9 = this->_pMXRAttrs._p;
  if ( v9 )
  {
    this->_pMXRAttrs._p = 0;
    v9->Release(v9);
  }
  v10 = this->_pLocator._p;
  if ( v10 )
    v10->QueryInterface(v10, &IID_IMXRAttributes, (void **)&this->_pMXRAttrs._p);
  v11 = this->_pLocator._p;
  if ( v11 )
  {
    pwszUrl = 0;
    v12 = v11->getSystemId(v11, &pwszUrl);
    checkhr(v12);
    v13 = pwszUrl;
    v32 = pwszUrl;
    v14 = 0;
    v33 = 0;
    v15 = 0;
    if ( pwszUrl )
    {
      while ( v15 < 0x7FFFFFFF && *v13 )
      {
        v32 = ++v13;
        v14 = v15 + 1;
        v33 = ++v15;
      }
    }
    if ( v14 )
      v16 = String::newString(pwszUrl, v14);
    else
      v16 = 0;
    release(&s._p);
    s._p = v16;
    assign(&p->_pResolvedURLdoc._p, v16);
    if ( !p->_pURLdoc._p )
      assign(&p->_pURLdoc._p, v16);
    pReader = 0;
    if ( ((__int64 (__fastcall *)(ISAXLocator *, GUID *, ISAXXMLReader **))this->_pLocator._p->QueryInterface)(
           this->_pLocator._p,
           &IID_ISAXXMLReader,
           &pReader) >= 0 )
    {
      memset(&v, 0, sizeof(v));
      v.vt = 1;
      if ( pReader->getProperty(pReader, L"xmldecl-version", &v) >= 0 && v.llVal )
      {
        pXmlDecl._p = 0;
        pNewNode._p = 0;
        if ( XMLNames::names._p->_length <= 5
          || (NameDef = NamespaceMgr::createNameDef(p_pNSMgr->_p, (Name *)XMLNames::names._p[2].__vftable, 0),
              Node::newNode((Node::NodeType)18, NameDef, p->_pDocNode._p, 0, 0, 0, this->_pDocument._p, &pXmlDecl._p),
              XMLNames::names._p->_length <= 2) )
        {
          Exception::throw_E_INVALIDARG();
        }
        v18 = NamespaceMgr::createNameDef(p_pNSMgr->_p, (Name *)XMLNames::names._p[1]._refs, 0);
        v19 = String::newString(v.bstrVal);
        release(&s._p);
        s._p = v19;
        Node::newNode(ANY|MIXED|0x8, v18, pXmlDecl._p, v19, 0, 0, this->_pDocument._p, &pNewNode._p);
        VariantClear(&v);
        if ( pReader->getProperty(pReader, L"xmldecl-encoding", &v) >= 0 && v.llVal )
        {
          v20 = p_pNSMgr->_p;
          v21 = XMLNames::name(3);
          v22 = NamespaceMgr::createNameDef(v20, v21, 0);
          pEncNode._p = 0;
          v23 = String::newString(v.bstrVal);
          release(&s._p);
          s._p = v23;
          Node::newNode(ANY|MIXED|0x8, v22, pXmlDecl._p, v23, 0, 0, this->_pDocument._p, &pEncNode._p);
          VariantClear(&v);
          weakRelease(&pEncNode._p);
        }
        if ( pReader->getProperty(pReader, L"xmldecl-standalone", &v) >= 0 )
        {
          if ( v.llVal )
          {
            v24 = p_pNSMgr->_p;
            v25 = XMLNames::name(6);
            v26 = NamespaceMgr::createNameDef(v24, v25, 0);
            pStdNode._p = 0;
            v27 = String::newString(v.bstrVal);
            release(&s._p);
            s._p = v27;
            Node::newNode(ANY|MIXED|0x8, v26, pXmlDecl._p, v27, 0, 0, this->_pDocument._p, &pStdNode._p);
            VariantClear(&v);
            weakRelease(&pStdNode._p);
          }
        }
        weakRelease(&pNewNode._p);
        weakRelease(&pXmlDecl._p);
      }
      pReader->Release(pReader);
    }
  }
  release(&s._p);
  return 0;
}

```

## disassembly

```asm
0x180056710  mov     [rsp+arg_0], this
0x180056715  push    rbx
0x180056716  push    rsi
0x180056717  push    rdi
0x180056718  push    r12
0x18005671a  push    r14
0x18005671c  push    r15
0x18005671e  sub     rsp, 98h
0x180056725  mov     rsi, this
0x180056728  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18005672f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056734  xor     r12d, r12d
0x180056737  test    rax, rax
0x18005673a  jnz     short loc_180056746
0x18005673c  mov     eax, 80004005h
0x180056741  jmp     loc_180056C9A
0x180056746  mov     r15d, r12d
0x180056749  mov     [rsp+0C8h+s._p], r12
0x180056751  mov     rdi, [rsi+50h]
0x180056755  mov     [rsi+0A2h], r12b
0x18005675c  lea     r14, [rsi+68h]
0x180056760  mov     rdx, [rdi+0C0h]; pref
0x180056767  mov     this, r14; ppref
0x18005676a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18005676f  mov     edx, 0Ch; dwFlags
0x180056774  mov     r8d, 0C0h; dwBytes
0x18005677a  mov     this, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x180056781  call    cs:__imp_HeapAlloc
0x180056788  nop     dword ptr [rax+rax+00h]
0x18005678d  test    rax, rax
0x180056790  jnz     short loc_18005679D
0x180056792  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x180056797  call    ?throw_E_OUTOFMEMORY@Exception@@SAXXZ; Exception::throw_E_OUTOFMEMORY(void)
0x18005679d  mov     rdx, rdi; pDoc
0x1800567a0  mov     this, rax; this
0x1800567a3  call    ??0NodeBuilder@@QEAA@PEAVDocument@@@Z; NodeBuilder::NodeBuilder(Document *)
0x1800567a8  mov     [rsi+70h], rax
0x1800567ac  lea     rdx, [rsi+48h]; pCallback
0x1800567b0  mov     this, rax; this
0x1800567b3  call    ?startDocument@NodeBuilder@@QEAAXPEAVParserCallbacks@1@@Z; NodeBuilder::startDocument(NodeBuilder::ParserCallbacks *)
0x1800567b8  lea     this, [rsi+78h]; ppref
0x1800567bc  mov     rdx, [rdi+0C8h]; pref
0x1800567c3  call    ?weakAssign@@YAXPEAPEAVObject@@PEAX@Z; weakAssign(Object * *,void *)
0x1800567c8  mov     rax, [rsi+80h]
0x1800567cf  test    rax, rax
0x1800567d2  jz      short loc_1800567D8
0x1800567d4  mov     [rax+10h], r12d
0x1800567d8  mov     rax, [rsi+88h]
0x1800567df  test    rax, rax
0x1800567e2  jz      short loc_1800567E8
0x1800567e4  mov     [rax+10h], r12d
0x1800567e8  mov     [rsi+0A0h], r12b
0x1800567ef  mov     dword ptr [rsi+9Ch], 2
0x1800567f9  mov     [rsi+98h], r12d
0x180056800  lea     rbx, [rsi+60h]
0x180056804  mov     this, [rbx]
0x180056807  test    this, this
0x18005680a  jz      short loc_18005681B
0x18005680c  mov     [rbx], r12
0x18005680f  mov     rax, [this]
0x180056812  mov     rax, [rax+10h]
0x180056816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005681b  mov     this, [rsi+58h]
0x18005681f  test    this, this
0x180056822  jz      short loc_180056839
0x180056824  mov     rax, [this]
0x180056827  mov     r8, rbx
0x18005682a  lea     rdx, IID_IMXRAttributes
0x180056831  mov     rax, [rax]
0x180056834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056839  mov     this, [rsi+58h]
0x18005683d  test    this, this
0x180056840  jz      loc_180056C59
0x180056846  mov     [rsp+0C8h+pwszUrl], r12
0x18005684b  mov     rax, [this]
0x18005684e  lea     rdx, [rsp+0C8h+pwszUrl]
0x180056853  mov     rax, [rax+30h]
0x180056857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005685c  mov     ecx, eax; hr
0x18005685e  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x180056863  mov     rax, [rsp+0C8h+pwszUrl]
0x180056868  mov     [rsp+0C8h+var_68], rax
0x18005686d  mov     rdx, r12; length
0x180056870  mov     [rsp+0C8h+var_60], rdx
0x180056875  mov     this, r12
0x180056878  test    rax, rax
0x18005687b  jz      short loc_1800568A3
0x18005687d  cmp     this, 7FFFFFFFh
0x180056884  jnb     short loc_1800568A3
0x180056886  cmp     [rax], r12w
0x18005688a  jz      short loc_1800568A3
0x18005688c  add     rax, 2
0x180056890  mov     [rsp+0C8h+var_68], rax
0x180056895  lea     rdx, [this+1]
0x180056899  mov     [rsp+0C8h+var_60], rdx
0x18005689e  mov     this, rdx
0x1800568a1  jmp     short loc_18005687D
0x1800568a3  test    edx, edx
0x1800568a5  jz      short loc_1800568B6
0x1800568a7  mov     this, [rsp+0C8h+pwszUrl]; c
0x1800568ac  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x1800568b1  mov     rbx, rax
0x1800568b4  jmp     short loc_1800568B9
0x1800568b6  mov     rbx, r12
0x1800568b9  lea     this, [rsp+0C8h+s]; ppref
0x1800568c1  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800568c6  mov     [rsp+0C8h+s._p], rbx
0x1800568ce  lea     this, [rdi+100h]; ppref
0x1800568d5  mov     rdx, rbx; pref
0x1800568d8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800568dd  lea     this, [rdi+0F8h]; ppref
0x1800568e4  cmp     [this], r12
0x1800568e7  jnz     short loc_1800568F1
0x1800568e9  mov     rdx, rbx; pref
0x1800568ec  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800568f1  mov     [rsp+0C8h+pReader], r12
0x1800568f9  mov     this, [rsi+58h]
0x1800568fd  mov     rax, [this]
0x180056900  lea     r8, [rsp+0C8h+pReader]
0x180056908  lea     rdx, IID_ISAXXMLReader
0x18005690f  mov     rax, [rax]
0x180056912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056917  test    eax, eax
0x180056919  js      loc_180056C59
0x18005691f  xorps   xmm0, xmm0
0x180056922  xor     eax, eax
0x180056924  movups  xmmword ptr [rsp+0C8h+v.___u0], xmm0
0x180056929  mov     [rsp+0C8h+v.pRecInfo], rax
0x180056931  mov     eax, 1
0x180056936  mov     word ptr [rsp+0C8h+v.___u0], ax
0x18005693b  mov     this, [rsp+0C8h+pReader]
0x180056943  mov     rax, [this]
0x180056946  lea     r8, [rsp+0C8h+v]
0x18005694b  lea     rdx, aXmldeclVersion; "xmldecl-version"
0x180056952  mov     rax, [rax+28h]
0x180056956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005695b  test    eax, eax
0x18005695d  js      loc_180056C45
0x180056963  cmp     qword ptr [rsp+0C8h+v.___u0+8], r12
0x180056968  jz      loc_180056C45
0x18005696e  mov     [rsp+0C8h+pXmlDecl._p], r12
0x180056976  mov     [rsp+0C8h+pNewNode._p], r12
0x18005697b  mov     rdx, cs:?names@XMLNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A._p; _reference<_array<_reference<Name>>> XMLNames::names ...
0x180056982  cmp     dword ptr [rdx+10h], 5
0x180056986  jle     loc_180056C06
0x18005698c  xor     r8d, r8d; pPrefix
0x18005698f  mov     rdx, [rdx+40h]; name
0x180056993  mov     this, [r14]; this
0x180056996  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x18005699b  lea     this, [rsp+0C8h+pXmlDecl]
0x1800569a3  mov     [rsp+0C8h+ppNode], this; ppNode
0x1800569a8  mov     this, [rsi+50h]
0x1800569ac  mov     [rsp+0C8h+pDoc], this; pDoc
0x1800569b1  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x1800569b6  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x1800569bb  xor     r9d, r9d; pText
0x1800569be  mov     r8, [rdi+0C8h]; pParent
0x1800569c5  mov     rdx, rax; pName
0x1800569c8  lea     ecx, [r9+12h]; type
0x1800569cc  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x1800569d1  mov     rdx, cs:?names@XMLNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A._p; _reference<_array<_reference<Name>>> XMLNames::names ...
0x1800569d8  cmp     dword ptr [rdx+10h], 2
0x1800569dc  jle     loc_180056C06
0x1800569e2  xor     r8d, r8d; pPrefix
0x1800569e5  mov     rdx, [rdx+28h]; name
0x1800569e9  mov     this, [r14]; this
0x1800569ec  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x1800569f1  mov     rdi, rax
0x1800569f4  mov     this, qword ptr [rsp+0C8h+v.___u0+8]; c
0x1800569f9  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800569fe  mov     rbx, rax
0x180056a01  lea     this, [rsp+0C8h+s]; ppref
0x180056a09  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180056a0e  mov     [rsp+0C8h+s._p], rbx
0x180056a16  lea     rax, [rsp+0C8h+pNewNode]
0x180056a1b  mov     [rsp+0C8h+ppNode], rax; ppNode
0x180056a20  mov     this, [rsi+50h]
0x180056a24  mov     [rsp+0C8h+pDoc], this; pDoc
0x180056a29  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x180056a2e  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x180056a33  mov     r9, rbx; pText
0x180056a36  mov     r8, [rsp+0C8h+pXmlDecl._p]; pParent
0x180056a3e  mov     rdx, rdi; pName
0x180056a41  mov     ecx, 0Fh; type
0x180056a46  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x180056a4b  lea     this, [rsp+0C8h+v]; pvarg
0x180056a50  call    cs:__imp_VariantClear
0x180056a57  nop     dword ptr [rax+rax+00h]
0x180056a5c  mov     this, [rsp+0C8h+pReader]
0x180056a64  mov     rax, [this]
0x180056a67  lea     r8, [rsp+0C8h+v]
0x180056a6c  lea     rdx, aXmldeclEncodin; "xmldecl-encoding"
0x180056a73  mov     rax, [rax+28h]
0x180056a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a7c  test    eax, eax
0x180056a7e  js      loc_180056B24
0x180056a84  cmp     qword ptr [rsp+0C8h+v.___u0+8], r12
0x180056a89  jz      loc_180056B24
0x180056a8f  mov     rbx, [r14]
0x180056a92  mov     ecx, 3; i
0x180056a97  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x180056a9c  xor     r8d, r8d; pPrefix
0x180056a9f  mov     rdx, rax; name
0x180056aa2  mov     this, rbx; this
0x180056aa5  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x180056aaa  mov     rdi, rax
0x180056aad  mov     [rsp+0C8h+pEncNode._p], r12
0x180056ab2  mov     this, qword ptr [rsp+0C8h+v.___u0+8]; c
0x180056ab7  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180056abc  mov     rbx, rax
0x180056abf  lea     this, [rsp+0C8h+s]; ppref
0x180056ac7  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180056acc  mov     [rsp+0C8h+s._p], rbx
0x180056ad4  lea     rax, [rsp+0C8h+pEncNode]
0x180056ad9  mov     [rsp+0C8h+ppNode], rax; ppNode
0x180056ade  mov     this, [rsi+50h]
0x180056ae2  mov     [rsp+0C8h+pDoc], this; pDoc
0x180056ae7  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x180056aec  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x180056af1  mov     r9, rbx; pText
0x180056af4  mov     r8, [rsp+0C8h+pXmlDecl._p]; pParent
0x180056afc  mov     rdx, rdi; pName
0x180056aff  mov     ecx, 0Fh; type
0x180056b04  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x180056b09  lea     this, [rsp+0C8h+v]; pvarg
0x180056b0e  call    cs:__imp_VariantClear
0x180056b15  nop     dword ptr [rax+rax+00h]
0x180056b1a  lea     this, [rsp+0C8h+pEncNode]; ppref
0x180056b1f  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180056b24  mov     this, [rsp+0C8h+pReader]
0x180056b2c  mov     rax, [this]
0x180056b2f  lea     r8, [rsp+0C8h+v]
0x180056b34  lea     rdx, aXmldeclStandal; "xmldecl-standalone"
0x180056b3b  mov     rax, [rax+28h]
0x180056b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b44  test    eax, eax
0x180056b46  js      loc_180056BED
0x180056b4c  cmp     qword ptr [rsp+0C8h+v.___u0+8], r12
0x180056b51  jz      loc_180056BED
0x180056b57  mov     rbx, [r14]
0x180056b5a  mov     ecx, 6; i
0x180056b5f  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x180056b64  xor     r8d, r8d; pPrefix
0x180056b67  mov     rdx, rax; name
0x180056b6a  mov     this, rbx; this
0x180056b6d  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x180056b72  mov     rdi, rax
0x180056b75  mov     [rsp+0C8h+pStdNode._p], r12
0x180056b7a  mov     this, qword ptr [rsp+0C8h+v.___u0+8]; c
0x180056b7f  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180056b84  mov     rbx, rax
0x180056b87  lea     this, [rsp+0C8h+s]; ppref
0x180056b8f  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180056b94  mov     [rsp+0C8h+s._p], rbx
0x180056b9c  lea     rax, [rsp+0C8h+pStdNode]
0x180056ba1  mov     [rsp+0C8h+ppNode], rax; ppNode
0x180056ba6  mov     rdx, [rsi+50h]
0x180056baa  mov     [rsp+0C8h+pDoc], rdx; pDoc
0x180056baf  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x180056bb4  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x180056bb9  mov     r9, rbx; pText
0x180056bbc  mov     r8, [rsp+0C8h+pXmlDecl._p]; pParent
0x180056bc4  mov     rdx, rdi; pName
0x180056bc7  mov     ecx, 0Fh; type
0x180056bcc  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x180056bd1  lea     this, [rsp+0C8h+v]; pvarg
0x180056bd6  call    cs:__imp_VariantClear
0x180056bdd  nop     dword ptr [rax+rax+00h]
0x180056be2  lea     this, [rsp+0C8h+pStdNode]; ppref
0x180056be7  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180056bec  nop
0x180056bed  lea     this, [rsp+0C8h+pNewNode]; ppref
0x180056bf2  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180056bf7  lea     this, [rsp+0C8h+pXmlDecl]; ppref
0x180056bff  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180056c04  jmp     short loc_180056C45
0x180056c06  call    ?throw_E_INVALIDARG@Exception@@SAXXZ; Exception::throw_E_INVALIDARG(void)
0x180056c0c  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180056c11  cmp     [rsp+0C8h+pXmlDecl._p], 0
0x180056c1a  jz      short loc_180056C2B
0x180056c1c  xor     edx, edx; pref
0x180056c1e  lea     this, [rsp+0C8h+pXmlDecl]; ppref
0x180056c26  call    ?weakAssign@@YAXPEAPEAVObject@@PEAX@Z; weakAssign(Object * *,void *)
0x180056c2b  cmp     [rsp+0C8h+pNewNode._p], 0
0x180056c31  jz      short loc_180056C3F
0x180056c33  xor     edx, edx; pref
0x180056c35  lea     this, [rsp+0C8h+pNewNode]; ppref
0x180056c3a  call    ?weakAssign@@YAXPEAPEAVObject@@PEAX@Z; weakAssign(Object * *,void *)
0x180056c3f  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180056c45  mov     this, [rsp+0C8h+pReader]
0x180056c4d  mov     rax, [this]
0x180056c50  mov     rax, [rax+10h]
0x180056c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c59  jmp     short loc_180056C8A
0x180056c5b  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180056c60  cmp     [rsp+0C8h+s._p], 0
0x180056c69  jz      short loc_180056C7A
0x180056c6b  xor     edx, edx; pref
0x180056c6d  lea     this, [rsp+0C8h+s]; ppref
0x180056c75  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
  ... truncated ...
```
