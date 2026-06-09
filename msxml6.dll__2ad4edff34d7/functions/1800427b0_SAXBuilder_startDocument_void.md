# SAXBuilder::startDocument(void)

- ea: `0x1800427b0`
- end: `0x180042d33`
- name: `?startDocument@SAXBuilder@@UEAAJXZ`
- size: `1411`
- prototype: `HRESULT __fastcall(SAXBuilder *this)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180163150`
- `0x180163160`

## callees

- `0x180009490`
- `0x18000d3ac`
- `0x18000d688`
- `0x18000d7d0`
- `0x18000e984`
- `0x18003d048`
- `0x18003e814`
- `0x18003f690`
- `0x18003f6ac`
- `0x180040ce4`
- `0x1800427b0`
- `0x18005250c`
- `0x180056994`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800bb5fc`
- `0x1800bc3e8`
- `0x1800c3c0c`
- `0x1800d65dc`
- `0x180162380`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042821`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042821`
- `OLEAUT32!__imp_VariantClear` at `0x180042aea`
- `OLEAUT32!__imp_VariantClear` at `0x180042ba2`
- `OLEAUT32!__imp_VariantClear` at `0x180042c64`
- `OLEAUT32!__imp_VariantClear` at `0x180042aea`
- `OLEAUT32!__imp_VariantClear` at `0x180042ba2`
- `OLEAUT32!__imp_VariantClear` at `0x180042c64`

## string_xrefs

- `0x1800429e5`: `xmldecl-version`
- `0x180042bc2`: `xmldecl-standalone`
- `0x180042b00`: `xmldecl-encoding`

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
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  _CodebaseString *v16; // rbx
  NameDef *NameDef; // rax
  NameDef *v18; // rdi
  _CodebaseString *v19; // rbx
  NamespaceMgr *v20; // rbx
  Name *v21; // rax
  NameDef *v22; // rdi
  _CodebaseString *v23; // rbx
  NamespaceMgr *v24; // rbx
  Name *v25; // rax
  NameDef *v26; // rdi
  _CodebaseString *v27; // rbx
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
    if ( (_DWORD)v14 )
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
              Node::newNode(XMLDECL, NameDef, p->_pDocNode._p, 0, 0, 0, this->_pDocument._p, &pXmlDecl._p),
              XMLNames::names._p->_length <= 2) )
        {
          Exception::throw_E_INVALIDARG();
        }
        v18 = NamespaceMgr::createNameDef(p_pNSMgr->_p, (Name *)XMLNames::names._p[1]._refs, 0);
        v19 = (_CodebaseString *)String::newString(v.bstrVal);
        release(&s._p);
        s._p = v19;
        Node::newNode(ATTRIBUTE, v18, pXmlDecl._p, v19, 0, 0, this->_pDocument._p, &pNewNode._p);
        VariantClear(&v);
        if ( pReader->getProperty(pReader, L"xmldecl-encoding", &v) >= 0 && v.llVal )
        {
          v20 = p_pNSMgr->_p;
          v21 = XMLNames::name(3);
          v22 = NamespaceMgr::createNameDef(v20, v21, 0);
          pEncNode._p = 0;
          v23 = (_CodebaseString *)String::newString(v.bstrVal);
          release(&s._p);
          s._p = v23;
          Node::newNode(ATTRIBUTE, v22, pXmlDecl._p, v23, 0, 0, this->_pDocument._p, &pEncNode._p);
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
            v27 = (_CodebaseString *)String::newString(v.bstrVal);
            release(&s._p);
            s._p = v27;
            Node::newNode(ATTRIBUTE, v26, pXmlDecl._p, v27, 0, 0, this->_pDocument._p, &pStdNode._p);
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
0x1800427b0  mov     [rsp+arg_0], this
0x1800427b5  push    rbx
0x1800427b6  push    rsi
0x1800427b7  push    rdi
0x1800427b8  push    r12
0x1800427ba  push    r14
0x1800427bc  push    r15
0x1800427be  sub     rsp, 98h
0x1800427c5  mov     rsi, this
0x1800427c8  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x1800427cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427d4  xor     r12d, r12d
0x1800427d7  test    rax, rax
0x1800427da  jnz     short loc_1800427E6
0x1800427dc  mov     eax, 80004005h
0x1800427e1  jmp     loc_180042D22
0x1800427e6  mov     r15d, r12d
0x1800427e9  mov     [rsp+0C8h+s._p], r12
0x1800427f1  mov     rdi, [rsi+50h]
0x1800427f5  mov     [rsi+0A2h], r12b
0x1800427fc  lea     r14, [rsi+68h]
0x180042800  mov     rdx, [rdi+0C0h]; pref
0x180042807  mov     this, r14; ppref
0x18004280a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18004280f  mov     edx, 0Ch; dwFlags
0x180042814  mov     r8d, 0C0h; dwBytes
0x18004281a  mov     this, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x180042821  call    cs:__imp_HeapAlloc
0x180042827  test    rax, rax
0x18004282a  jnz     short loc_180042837
0x18004282c  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x180042831  call    ?throw_E_OUTOFMEMORY@Exception@@SAXXZ; Exception::throw_E_OUTOFMEMORY(void)
0x180042837  mov     rdx, rdi; pDoc
0x18004283a  mov     this, rax; this
0x18004283d  call    ??0NodeBuilder@@QEAA@PEAVDocument@@@Z; NodeBuilder::NodeBuilder(Document *)
0x180042842  mov     [rsi+70h], rax
0x180042846  lea     rdx, [rsi+48h]; pCallback
0x18004284a  mov     this, rax; this
0x18004284d  call    ?startDocument@NodeBuilder@@QEAAXPEAVParserCallbacks@1@@Z; NodeBuilder::startDocument(NodeBuilder::ParserCallbacks *)
0x180042852  lea     this, [rsi+78h]; ppref
0x180042856  mov     rdx, [rdi+0C8h]; pref
0x18004285d  call    ?weakAssign@@YAXPEAPEAVObject@@PEAX@Z; weakAssign(Object * *,void *)
0x180042862  mov     rax, [rsi+80h]
0x180042869  test    rax, rax
0x18004286c  jz      short loc_180042872
0x18004286e  mov     [rax+10h], r12d
0x180042872  mov     rax, [rsi+88h]
0x180042879  test    rax, rax
0x18004287c  jz      short loc_180042882
0x18004287e  mov     [rax+10h], r12d
0x180042882  mov     [rsi+0A0h], r12b
0x180042889  mov     dword ptr [rsi+9Ch], 2
0x180042893  mov     [rsi+98h], r12d
0x18004289a  lea     rbx, [rsi+60h]
0x18004289e  mov     this, [rbx]
0x1800428a1  test    this, this
0x1800428a4  jz      short loc_1800428B5
0x1800428a6  mov     [rbx], r12
0x1800428a9  mov     rax, [this]
0x1800428ac  mov     rax, [rax+10h]
0x1800428b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428b5  mov     this, [rsi+58h]
0x1800428b9  test    this, this
0x1800428bc  jz      short loc_1800428D3
0x1800428be  mov     rax, [this]
0x1800428c1  mov     r8, rbx
0x1800428c4  lea     rdx, IID_IMXRAttributes
0x1800428cb  mov     rax, [rax]
0x1800428ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428d3  mov     this, [rsi+58h]
0x1800428d7  test    this, this
0x1800428da  jz      loc_180042CE1
0x1800428e0  mov     [rsp+0C8h+pwszUrl], r12
0x1800428e5  mov     rax, [this]
0x1800428e8  lea     rdx, [rsp+0C8h+pwszUrl]
0x1800428ed  mov     rax, [rax+30h]
0x1800428f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428f6  mov     ecx, eax; hr
0x1800428f8  call    ?checkhr@@YAXJ@Z; checkhr(long)
0x1800428fd  mov     rax, [rsp+0C8h+pwszUrl]
0x180042902  mov     [rsp+0C8h+var_68], rax
0x180042907  mov     rdx, r12; length
0x18004290a  mov     [rsp+0C8h+var_60], rdx
0x18004290f  mov     this, r12
0x180042912  test    rax, rax
0x180042915  jz      short loc_18004293D
0x180042917  cmp     this, 7FFFFFFFh
0x18004291e  jnb     short loc_18004293D
0x180042920  cmp     [rax], r12w
0x180042924  jz      short loc_18004293D
0x180042926  add     rax, 2
0x18004292a  mov     [rsp+0C8h+var_68], rax
0x18004292f  lea     rdx, [this+1]
0x180042933  mov     [rsp+0C8h+var_60], rdx
0x180042938  mov     this, rdx
0x18004293b  jmp     short loc_180042917
0x18004293d  test    edx, edx
0x18004293f  jz      short loc_180042950
0x180042941  mov     this, [rsp+0C8h+pwszUrl]; c
0x180042946  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x18004294b  mov     rbx, rax
0x18004294e  jmp     short loc_180042953
0x180042950  mov     rbx, r12
0x180042953  lea     this, [rsp+0C8h+s]; ppref
0x18004295b  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180042960  mov     [rsp+0C8h+s._p], rbx
0x180042968  lea     this, [rdi+100h]; ppref
0x18004296f  mov     rdx, rbx; pref
0x180042972  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180042977  lea     this, [rdi+0F8h]; ppref
0x18004297e  cmp     [this], r12
0x180042981  jnz     short loc_18004298B
0x180042983  mov     rdx, rbx; pref
0x180042986  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18004298b  mov     [rsp+0C8h+pReader], r12
0x180042993  mov     this, [rsi+58h]
0x180042997  mov     rax, [this]
0x18004299a  lea     r8, [rsp+0C8h+pReader]
0x1800429a2  lea     rdx, IID_ISAXXMLReader
0x1800429a9  mov     rax, [rax]
0x1800429ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429b1  test    eax, eax
0x1800429b3  js      loc_180042CE1
0x1800429b9  xorps   xmm0, xmm0
0x1800429bc  xor     eax, eax
0x1800429be  movups  xmmword ptr [rsp+0C8h+v.___u0], xmm0
0x1800429c3  mov     [rsp+0C8h+v.pRecInfo], rax
0x1800429cb  mov     eax, 1
0x1800429d0  mov     word ptr [rsp+0C8h+v.___u0], ax
0x1800429d5  mov     this, [rsp+0C8h+pReader]
0x1800429dd  mov     rax, [this]
0x1800429e0  lea     r8, [rsp+0C8h+v]
0x1800429e5  lea     rdx, aXmldeclVersion; "xmldecl-version"
0x1800429ec  mov     rax, [rax+28h]
0x1800429f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429f5  test    eax, eax
0x1800429f7  js      loc_180042CCD
0x1800429fd  cmp     qword ptr [rsp+0C8h+v.___u0+8], r12
0x180042a02  jz      loc_180042CCD
0x180042a08  mov     [rsp+0C8h+pXmlDecl._p], r12
0x180042a10  mov     [rsp+0C8h+pNewNode._p], r12
0x180042a15  mov     rdx, cs:?names@XMLNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A._p; _reference<_array<_reference<Name>>> XMLNames::names ...
0x180042a1c  cmp     dword ptr [rdx+10h], 5
0x180042a20  jle     loc_180042C8E
0x180042a26  xor     r8d, r8d; pPrefix
0x180042a29  mov     rdx, [rdx+40h]; name
0x180042a2d  mov     this, [r14]; this
0x180042a30  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x180042a35  lea     this, [rsp+0C8h+pXmlDecl]
0x180042a3d  mov     [rsp+0C8h+ppNode], this; ppNode
0x180042a42  mov     this, [rsi+50h]
0x180042a46  mov     [rsp+0C8h+pDoc], this; pDoc
0x180042a4b  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x180042a50  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x180042a55  xor     r9d, r9d; pText
0x180042a58  mov     r8, [rdi+0C8h]; pParent
0x180042a5f  mov     rdx, rax; pName
0x180042a62  lea     ecx, [r9+12h]; type
0x180042a66  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x180042a6b  mov     rdx, cs:?names@XMLNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A._p; _reference<_array<_reference<Name>>> XMLNames::names ...
0x180042a72  cmp     dword ptr [rdx+10h], 2
0x180042a76  jle     loc_180042C8E
0x180042a7c  xor     r8d, r8d; pPrefix
0x180042a7f  mov     rdx, [rdx+28h]; name
0x180042a83  mov     this, [r14]; this
0x180042a86  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x180042a8b  mov     rdi, rax
0x180042a8e  mov     this, qword ptr [rsp+0C8h+v.___u0+8]; c
0x180042a93  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180042a98  mov     rbx, rax
0x180042a9b  lea     this, [rsp+0C8h+s]; ppref
0x180042aa3  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180042aa8  mov     [rsp+0C8h+s._p], rbx
0x180042ab0  lea     rax, [rsp+0C8h+pNewNode]
0x180042ab5  mov     [rsp+0C8h+ppNode], rax; ppNode
0x180042aba  mov     this, [rsi+50h]
0x180042abe  mov     [rsp+0C8h+pDoc], this; pDoc
0x180042ac3  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x180042ac8  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x180042acd  mov     r9, rbx; pText
0x180042ad0  mov     r8, [rsp+0C8h+pXmlDecl._p]; pParent
0x180042ad8  mov     rdx, rdi; pName
0x180042adb  mov     ecx, 0Fh; type
0x180042ae0  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x180042ae5  lea     this, [rsp+0C8h+v]; pvarg
0x180042aea  call    cs:__imp_VariantClear
0x180042af0  mov     this, [rsp+0C8h+pReader]
0x180042af8  mov     rax, [this]
0x180042afb  lea     r8, [rsp+0C8h+v]
0x180042b00  lea     rdx, aXmldeclEncodin; "xmldecl-encoding"
0x180042b07  mov     rax, [rax+28h]
0x180042b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b10  test    eax, eax
0x180042b12  js      loc_180042BB2
0x180042b18  cmp     qword ptr [rsp+0C8h+v.___u0+8], r12
0x180042b1d  jz      loc_180042BB2
0x180042b23  mov     rbx, [r14]
0x180042b26  mov     ecx, 3; i
0x180042b2b  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x180042b30  xor     r8d, r8d; pPrefix
0x180042b33  mov     rdx, rax; name
0x180042b36  mov     this, rbx; this
0x180042b39  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x180042b3e  mov     rdi, rax
0x180042b41  mov     [rsp+0C8h+pEncNode._p], r12
0x180042b46  mov     this, qword ptr [rsp+0C8h+v.___u0+8]; c
0x180042b4b  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180042b50  mov     rbx, rax
0x180042b53  lea     this, [rsp+0C8h+s]; ppref
0x180042b5b  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180042b60  mov     [rsp+0C8h+s._p], rbx
0x180042b68  lea     rax, [rsp+0C8h+pEncNode]
0x180042b6d  mov     [rsp+0C8h+ppNode], rax; ppNode
0x180042b72  mov     this, [rsi+50h]
0x180042b76  mov     [rsp+0C8h+pDoc], this; pDoc
0x180042b7b  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x180042b80  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x180042b85  mov     r9, rbx; pText
0x180042b88  mov     r8, [rsp+0C8h+pXmlDecl._p]; pParent
0x180042b90  mov     rdx, rdi; pName
0x180042b93  mov     ecx, 0Fh; type
0x180042b98  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x180042b9d  lea     this, [rsp+0C8h+v]; pvarg
0x180042ba2  call    cs:__imp_VariantClear
0x180042ba8  lea     this, [rsp+0C8h+pEncNode]; ppref
0x180042bad  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180042bb2  mov     this, [rsp+0C8h+pReader]
0x180042bba  mov     rax, [this]
0x180042bbd  lea     r8, [rsp+0C8h+v]
0x180042bc2  lea     rdx, aXmldeclStandal; "xmldecl-standalone"
0x180042bc9  mov     rax, [rax+28h]
0x180042bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bd2  test    eax, eax
0x180042bd4  js      loc_180042C75
0x180042bda  cmp     qword ptr [rsp+0C8h+v.___u0+8], r12
0x180042bdf  jz      loc_180042C75
0x180042be5  mov     rbx, [r14]
0x180042be8  mov     ecx, 6; i
0x180042bed  call    ?name@XMLNames@@SAPEAVName@@H@Z; XMLNames::name(int)
0x180042bf2  xor     r8d, r8d; pPrefix
0x180042bf5  mov     rdx, rax; name
0x180042bf8  mov     this, rbx; this
0x180042bfb  call    ?createNameDef@NamespaceMgr@@QEAAPEAVNameDef@@PEAVName@@PEAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x180042c00  mov     rdi, rax
0x180042c03  mov     [rsp+0C8h+pStdNode._p], r12
0x180042c08  mov     this, qword ptr [rsp+0C8h+v.___u0+8]; c
0x180042c0d  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x180042c12  mov     rbx, rax
0x180042c15  lea     this, [rsp+0C8h+s]; ppref
0x180042c1d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180042c22  mov     [rsp+0C8h+s._p], rbx
0x180042c2a  lea     rax, [rsp+0C8h+pStdNode]
0x180042c2f  mov     [rsp+0C8h+ppNode], rax; ppNode
0x180042c34  mov     rdx, [rsi+50h]
0x180042c38  mov     [rsp+0C8h+pDoc], rdx; pDoc
0x180042c3d  mov     [rsp+0C8h+ulContentLen], r12d; ulContentLen
0x180042c42  mov     [rsp+0C8h+pwcContext], r12; pwcContext
0x180042c47  mov     r9, rbx; pText
0x180042c4a  mov     r8, [rsp+0C8h+pXmlDecl._p]; pParent
0x180042c52  mov     rdx, rdi; pName
0x180042c55  mov     ecx, 0Fh; type
0x180042c5a  call    ?newNode@Node@@KAXW4NodeType@1@PEAVNameDef@@PEAV1@PEAVString@@PEBGKPEAVDocument@@PEAPEAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x180042c5f  lea     this, [rsp+0C8h+v]; pvarg
0x180042c64  call    cs:__imp_VariantClear
0x180042c6a  lea     this, [rsp+0C8h+pStdNode]; ppref
0x180042c6f  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180042c74  nop
0x180042c75  lea     this, [rsp+0C8h+pNewNode]; ppref
0x180042c7a  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180042c7f  lea     this, [rsp+0C8h+pXmlDecl]; ppref
0x180042c87  call    ?weakRelease@@YAXPEAPEAVObject@@@Z; weakRelease(Object * *)
0x180042c8c  jmp     short loc_180042CCD
0x180042c8e  call    ?throw_E_INVALIDARG@Exception@@SAXXZ; Exception::throw_E_INVALIDARG(void)
0x180042c94  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180042c99  cmp     [rsp+0C8h+pXmlDecl._p], 0
0x180042ca2  jz      short loc_180042CB3
0x180042ca4  xor     edx, edx; pref
0x180042ca6  lea     this, [rsp+0C8h+pXmlDecl]; ppref
0x180042cae  call    ?weakAssign@@YAXPEAPEAVObject@@PEAX@Z; weakAssign(Object * *,void *)
0x180042cb3  cmp     [rsp+0C8h+pNewNode._p], 0
0x180042cb9  jz      short loc_180042CC7
0x180042cbb  xor     edx, edx; pref
0x180042cbd  lea     this, [rsp+0C8h+pNewNode]; ppref
0x180042cc2  call    ?weakAssign@@YAXPEAPEAVObject@@PEAX@Z; weakAssign(Object * *,void *)
0x180042cc7  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180042ccd  mov     this, [rsp+0C8h+pReader]
0x180042cd5  mov     rax, [this]
0x180042cd8  mov     rax, [rax+10h]
0x180042cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ce1  jmp     short loc_180042D12
0x180042ce3  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180042ce8  cmp     [rsp+0C8h+s._p], 0
0x180042cf1  jz      short loc_180042D02
0x180042cf3  xor     edx, edx; pref
0x180042cf5  lea     this, [rsp+0C8h+s]; ppref
0x180042cfd  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180042d02  mov     this, [rsp+0C8h+arg_0]; this
0x180042d0a  call    ?handleException@SAXBuilder@@IEAAJXZ; SAXBuilder::handleException(void)
0x180042d0f  mov     r15d, eax
0x180042d12  lea     this, [rsp+0C8h+s]; ppref
  ... truncated ...
```
