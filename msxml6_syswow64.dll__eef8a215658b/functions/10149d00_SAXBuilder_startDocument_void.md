# SAXBuilder::startDocument(void)

- ea: `0x10149d00`
- end: `0x1014a0e9`
- name: `?startDocument@SAXBuilder@@UAGJXZ`
- size: `1001`
- prototype: `HRESULT __stdcall(SAXBuilder *this)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1014a0f0`
- `0x1014a100`

## callees

- `0x1003c996`
- `0x1003f4b8`
- `0x1003fb13`
- `0x1003fd72`
- `0x10040b56`
- `0x10040bb4`
- `0x1004fbae`
- `0x100505bc`
- `0x1005649d`
- `0x10064c31`
- `0x1006740f`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100781cb`
- `0x1008b6e9`
- `0x1008c4bb`
- `0x1014916d`
- `0x10149d00`
- `0x1014a8ba`
- `0x1014b10c`

## import_xrefs

- `OLEAUT32!__imp__VariantClear@4` at `0x10149f29`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149fa5`
- `OLEAUT32!__imp__VariantClear@4` at `0x1014a029`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149f29`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149fa5`
- `OLEAUT32!__imp__VariantClear@4` at `0x1014a029`

## string_xrefs

- `0x10149f3b`: `xmldecl-encoding`
- `0x10149e7b`: `xmldecl-version`
- `0x10149fbf`: `xmldecl-standalone`

## pseudocode

```c
HRESULT __stdcall SAXBuilder::startDocument(SAXBuilder *this)
{
  Document *p; // edi
  NodeBuilder *v3; // eax
  NodeBuilder *v4; // eax
  StringBuffer *v5; // eax
  StringBuffer *v6; // eax
  ISAXLocator *v7; // ecx
  ISAXLocator *v8; // ecx
  HRESULT v9; // eax
  unsigned int v10; // eax
  ArrayString *v11; // esi
  NamespaceMgr *v12; // esi
  Name *v13; // eax
  NameDef *NameDef; // eax
  NamespaceMgr *v15; // esi
  Name *v16; // eax
  NameDef *v17; // edi
  String *v18; // esi
  NamespaceMgr *v19; // esi
  Name *v20; // eax
  NameDef *v21; // edi
  String *v22; // esi
  NamespaceMgr *v23; // esi
  Name *v24; // eax
  NameDef *v25; // edi
  String *v26; // esi
  tagVARIANT v; // [esp+10h] [ebp-48h] BYREF
  EnsureTls _EnsureTls; // [esp+20h] [ebp-38h] BYREF
  _weakreference<Node> pStdNode; // [esp+24h] [ebp-34h] BYREF
  _weakreference<Node> pEncNode; // [esp+28h] [ebp-30h] BYREF
  const wchar_t *pwszUrl; // [esp+2Ch] [ebp-2Ch] BYREF
  _weakreference<Node> pNewNode; // [esp+30h] [ebp-28h] BYREF
  ISAXXMLReader *pReader; // [esp+34h] [ebp-24h] BYREF
  _weakreference<Node> pXmlDecl; // [esp+38h] [ebp-20h] BYREF
  _reference<String> s; // [esp+3Ch] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+40h] [ebp-18h]

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( _EnsureTls._tlsdata )
  {
    _EnsureTls._tlsdata = 0;
    s._p = 0;
    ms_exc.registration.TryLevel = 0;
    p = this->_pDocument._p;
    this->_fFirstElementReached = 0;
    assign(&this->_pNSMgr._p, p->_pNamespaceMgr._p);
    v3 = (NodeBuilder *)_MemAlloc(0x70u, 0xCu);
    v4 = NodeBuilder::NodeBuilder(v3, p);
    this->_pBuilder = v4;
    NodeBuilder::startDocument(v4, &this->NodeBuilder::ParserCallbacks);
    weakAssign(&this->_pParentNode._p, p->_pDocNode._p);
    v5 = this->_pCDATABuffer._p;
    if ( v5 )
      v5->_length = 0;
    v6 = this->_pDocTypeSubsetBuffer._p;
    if ( v6 )
      v6->_length = 0;
    this->_fError = 0;
    this->_eState = SAXBuilder_Document;
    this->_nEntityDepth = 0;
    assign(&this->_pMXRAttrs._p, 0);
    v7 = this->_pLocator._p;
    if ( v7 )
      ((void (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), ISAXLocator *, GUID *, _reference<IMXRAttributes> *))v7->QueryInterface)(
        v7->QueryInterface,
        v7,
        &IID_IMXRAttributes,
        &this->_pMXRAttrs);
    v8 = this->_pLocator._p;
    if ( v8 )
    {
      pwszUrl = 0;
      v9 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXLocator *, const wchar_t **), ISAXLocator *, const wchar_t **))v8->getSystemId)(
             v8->getSystemId,
             v8,
             &pwszUrl);
      checkhr(v9);
      v10 = xstrlenw(pwszUrl, 0x7FFFFFFFu);
      if ( v10 )
        v11 = String::newString(pwszUrl, v10);
      else
        v11 = 0;
      release(&s._p);
      s._p = v11;
      assign(&p->_pResolvedURLdoc._p, v11);
      if ( !p->_pURLdoc._p )
        assign(&p->_pURLdoc._p, v11);
      pReader = 0;
      if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), ISAXLocator *, GUID *, ISAXXMLReader **))this->_pLocator._p->QueryInterface)(
             this->_pLocator._p->QueryInterface,
             this->_pLocator._p,
             &IID_ISAXXMLReader,
             &pReader) >= 0 )
      {
        v.vt = 1;
        if ( ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXXMLReader *, const wchar_t *, tagVARIANT *), ISAXXMLReader *, const wchar_t *, tagVARIANT *))pReader->getProperty)(
               pReader->getProperty,
               pReader,
               L"xmldecl-version",
               &v) >= 0
          && v.decVal.Lo32 )
        {
          pXmlDecl._p = 0;
          pNewNode._p = 0;
          ms_exc.registration.TryLevel = 1;
          v12 = this->_pNSMgr._p;
          v13 = XMLNames::name(5);
          NameDef = NamespaceMgr::createNameDef(v12, v13, 0);
          Node::newNode(XMLDECL, NameDef, p->_pDocNode._p, 0, 0, 0, this->_pDocument._p, &pXmlDecl._p);
          v15 = this->_pNSMgr._p;
          v16 = XMLNames::name(2);
          v17 = NamespaceMgr::createNameDef(v15, v16, 0);
          v18 = String::newString(v.bstrVal);
          release(&s._p);
          s._p = v18;
          Node::newNode(ATTRIBUTE, v17, pXmlDecl._p, v18, 0, 0, this->_pDocument._p, &pNewNode._p);
          VariantClear(&v);
          if ( ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXXMLReader *, const wchar_t *, tagVARIANT *), ISAXXMLReader *, const wchar_t *, tagVARIANT *))pReader->getProperty)(
                 pReader->getProperty,
                 pReader,
                 L"xmldecl-encoding",
                 &v) >= 0
            && v.decVal.Lo32 )
          {
            v19 = this->_pNSMgr._p;
            v20 = XMLNames::name(3);
            v21 = NamespaceMgr::createNameDef(v19, v20, 0);
            pEncNode._p = 0;
            v22 = String::newString(v.bstrVal);
            release(&s._p);
            s._p = v22;
            Node::newNode(ATTRIBUTE, v21, pXmlDecl._p, v22, 0, 0, this->_pDocument._p, &pEncNode._p);
            VariantClear(&v);
            weakRelease(&pEncNode._p);
          }
          if ( ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXXMLReader *, const wchar_t *, tagVARIANT *), ISAXXMLReader *, const wchar_t *, tagVARIANT *))pReader->getProperty)(
                 pReader->getProperty,
                 pReader,
                 L"xmldecl-standalone",
                 &v) >= 0 )
          {
            if ( v.decVal.Lo32 )
            {
              v23 = this->_pNSMgr._p;
              v24 = XMLNames::name(6);
              v25 = NamespaceMgr::createNameDef(v23, v24, 0);
              pStdNode._p = 0;
              v26 = String::newString(v.bstrVal);
              release(&s._p);
              s._p = v26;
              Node::newNode(ATTRIBUTE, v25, pXmlDecl._p, v26, 0, 0, this->_pDocument._p, &pStdNode._p);
              VariantClear(&v);
              weakRelease(&pStdNode._p);
            }
          }
          ms_exc.registration.TryLevel = 0;
          weakRelease(&pNewNode._p);
          weakRelease(&pXmlDecl._p);
        }
        ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISAXXMLReader *))pReader->Release)(
          pReader->Release,
          pReader);
      }
    }
    ms_exc.registration.TryLevel = -2;
    release(&s._p);
    return (HRESULT)_EnsureTls._tlsdata;
  }
  else
  {
    return -2147467259;
  }
}

```

## disassembly

```asm
0x10149d00  push    38h
0x10149d02  push    offset stru_1017D420
0x10149d07  call    __SEH_prolog4
0x10149d0c  lea     ecx, [ebp+_EnsureTls]; this
0x10149d0f  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x10149d14  cmp     [ebp+_EnsureTls._tlsdata], 0
0x10149d18  jnz     short loc_10149D24
0x10149d1a  mov     eax, 80004005h
0x10149d1f  jmp     loc_1014A0D7
0x10149d24  xor     eax, eax
0x10149d26  mov     [ebp+_EnsureTls._tlsdata], eax
0x10149d29  mov     [ebp+s._p], eax
0x10149d2c  mov     [ebp+ms_exc.registration.TryLevel], eax
0x10149d2f  mov     ebx, [ebp+this]
0x10149d32  mov     edi, [ebx+28h]
0x10149d35  mov     [ebx+56h], al
0x10149d38  lea     ecx, [ebx+34h]; ppref
0x10149d3b  mov     edx, [edi+6Ch]; pref
0x10149d3e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149d43  push    0Ch
0x10149d45  pop     edx; dwFlags
0x10149d46  push    70h ; 'p'
0x10149d48  pop     ecx; cb
0x10149d49  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10149d4e  push    edi; pDoc
0x10149d4f  mov     ecx, eax; this
0x10149d51  call    ??0NodeBuilder@@QAE@PAVDocument@@@Z; NodeBuilder::NodeBuilder(Document *)
0x10149d56  mov     ecx, eax; this
0x10149d58  mov     [ebx+38h], ecx
0x10149d5b  lea     eax, [ebx+24h]
0x10149d5e  push    eax; pCallback
0x10149d5f  call    ?startDocument@NodeBuilder@@QAEXPAVParserCallbacks@1@@Z; NodeBuilder::startDocument(NodeBuilder::ParserCallbacks *)
0x10149d64  lea     ecx, [ebx+3Ch]; ppref
0x10149d67  mov     edx, [edi+70h]; pref
0x10149d6a  call    ?weakAssign@@YGXPAPAVObject@@PAX@Z; weakAssign(Object * *,void *)
0x10149d6f  mov     eax, [ebx+40h]
0x10149d72  test    eax, eax
0x10149d74  jz      short loc_10149D7D
0x10149d76  mov     dword ptr [eax+8], 0
0x10149d7d  mov     eax, [ebx+44h]
0x10149d80  test    eax, eax
0x10149d82  jz      short loc_10149D8B
0x10149d84  mov     dword ptr [eax+8], 0
0x10149d8b  mov     byte ptr [ebx+54h], 0
0x10149d8f  mov     dword ptr [ebx+50h], 2
0x10149d96  mov     dword ptr [ebx+4Ch], 0
0x10149d9d  lea     ecx, [ebx+30h]; ppref
0x10149da0  xor     edx, edx; pref
0x10149da2  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149da7  mov     ecx, [ebx+2Ch]
0x10149daa  test    ecx, ecx
0x10149dac  jz      short loc_10149DC6
0x10149dae  mov     eax, [ecx]
0x10149db0  mov     esi, [eax]
0x10149db2  lea     eax, [ebx+30h]
0x10149db5  push    eax
0x10149db6  push    offset _IID_IMXRAttributes
0x10149dbb  push    ecx
0x10149dbc  mov     ecx, esi; this
0x10149dbe  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149dc4  call    esi
0x10149dc6  mov     ecx, [ebx+2Ch]
0x10149dc9  test    ecx, ecx
0x10149dcb  jz      loc_1014A0C5
0x10149dd1  mov     [ebp+pwszUrl], 0
0x10149dd8  mov     eax, [ecx]
0x10149dda  mov     esi, [eax+18h]
0x10149ddd  lea     eax, [ebp+pwszUrl]
0x10149de0  push    eax
0x10149de1  push    ecx
0x10149de2  mov     ecx, esi; this
0x10149de4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149dea  call    esi
0x10149dec  mov     ecx, eax; hr
0x10149dee  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x10149df3  mov     edx, 7FFFFFFFh; cchMax
0x10149df8  mov     ecx, [ebp+pwszUrl]; psz
0x10149dfb  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x10149e00  test    eax, eax
0x10149e02  jz      short loc_10149E12
0x10149e04  mov     edx, eax; length
0x10149e06  mov     ecx, [ebp+pwszUrl]; c
0x10149e09  call    ?newString@String@@SGPAV1@PBGH@Z; String::newString(ushort const *,int)
0x10149e0e  mov     esi, eax
0x10149e10  jmp     short loc_10149E14
0x10149e12  xor     esi, esi
0x10149e14  lea     ecx, [ebp+s]; ppref
0x10149e17  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10149e1c  mov     [ebp+s._p], esi
0x10149e1f  lea     ecx, [edi+8Ch]; ppref
0x10149e25  mov     edx, esi; pref
0x10149e27  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149e2c  lea     ecx, [edi+88h]; ppref
0x10149e32  cmp     dword ptr [ecx], 0
0x10149e35  jnz     short loc_10149E3E
0x10149e37  mov     edx, esi; pref
0x10149e39  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149e3e  mov     [ebp+pReader], 0
0x10149e45  mov     ecx, [ebx+2Ch]
0x10149e48  mov     eax, [ecx]
0x10149e4a  mov     esi, [eax]
0x10149e4c  lea     eax, [ebp+pReader]
0x10149e4f  push    eax
0x10149e50  push    offset _IID_ISAXXMLReader
0x10149e55  push    ecx
0x10149e56  mov     ecx, esi; this
0x10149e58  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149e5e  call    esi
0x10149e60  test    eax, eax
0x10149e62  js      loc_1014A0C5
0x10149e68  xor     eax, eax
0x10149e6a  inc     eax
0x10149e6b  mov     word ptr [ebp+v.___u0], ax
0x10149e6f  mov     ecx, [ebp+pReader]
0x10149e72  mov     eax, [ecx]
0x10149e74  mov     esi, [eax+14h]
0x10149e77  lea     eax, [ebp+v]
0x10149e7a  push    eax
0x10149e7b  push    offset aXmldeclVersion; "xmldecl-version"
0x10149e80  push    ecx
0x10149e81  mov     ecx, esi; this
0x10149e83  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149e89  call    esi
0x10149e8b  test    eax, eax
0x10149e8d  js      loc_1014A04E
0x10149e93  cmp     dword ptr [ebp+v.___u0+8], 0
0x10149e97  jz      loc_1014A04E
0x10149e9d  mov     [ebp+pXmlDecl._p], 0
0x10149ea4  mov     [ebp+pNewNode._p], 0
0x10149eab  mov     [ebp+ms_exc.registration.TryLevel], 1
0x10149eb2  mov     esi, [ebx+34h]
0x10149eb5  push    5
0x10149eb7  pop     ecx; i
0x10149eb8  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149ebd  push    0; pPrefix
0x10149ebf  push    eax; name
0x10149ec0  mov     ecx, esi; this
0x10149ec2  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149ec7  lea     ecx, [ebp+pXmlDecl]
0x10149eca  push    ecx; ppNode
0x10149ecb  push    dword ptr [ebx+28h]; pDoc
0x10149ece  xor     ecx, ecx
0x10149ed0  push    ecx; ulContentLen
0x10149ed1  push    ecx; pwcContext
0x10149ed2  push    ecx; pText
0x10149ed3  push    dword ptr [edi+70h]; pParent
0x10149ed6  mov     edx, eax; pName
0x10149ed8  push    12h
0x10149eda  pop     ecx; type
0x10149edb  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x10149ee0  mov     esi, [ebx+34h]
0x10149ee3  push    2
0x10149ee5  pop     ecx; i
0x10149ee6  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149eeb  push    0; pPrefix
0x10149eed  push    eax; name
0x10149eee  mov     ecx, esi; this
0x10149ef0  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149ef5  mov     edi, eax
0x10149ef7  mov     ecx, dword ptr [ebp+v.___u0+8]; c
0x10149efa  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x10149eff  mov     esi, eax
0x10149f01  lea     ecx, [ebp+s]; ppref
0x10149f04  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10149f09  mov     [ebp+s._p], esi
0x10149f0c  lea     eax, [ebp+pNewNode]
0x10149f0f  push    eax; ppNode
0x10149f10  push    dword ptr [ebx+28h]; pDoc
0x10149f13  push    0; ulContentLen
0x10149f15  push    0; pwcContext
0x10149f17  push    esi; pText
0x10149f18  push    [ebp+pXmlDecl._p]; pParent
0x10149f1b  mov     edx, edi; pName
0x10149f1d  push    0Fh
0x10149f1f  pop     ecx; type
0x10149f20  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x10149f25  lea     eax, [ebp+v]
0x10149f28  push    eax; pvarg
0x10149f29  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10149f2f  mov     ecx, [ebp+pReader]
0x10149f32  mov     eax, [ecx]
0x10149f34  mov     esi, [eax+14h]
0x10149f37  lea     eax, [ebp+v]
0x10149f3a  push    eax
0x10149f3b  push    offset aXmldeclEncodin; "xmldecl-encoding"
0x10149f40  push    ecx
0x10149f41  mov     ecx, esi; this
0x10149f43  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149f49  call    esi
0x10149f4b  test    eax, eax
0x10149f4d  js      short loc_10149FB3
0x10149f4f  cmp     dword ptr [ebp+v.___u0+8], 0
0x10149f53  jz      short loc_10149FB3
0x10149f55  mov     esi, [ebx+34h]
0x10149f58  push    3
0x10149f5a  pop     ecx; i
0x10149f5b  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149f60  push    0; pPrefix
0x10149f62  push    eax; name
0x10149f63  mov     ecx, esi; this
0x10149f65  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149f6a  mov     edi, eax
0x10149f6c  mov     [ebp+pEncNode._p], 0
0x10149f73  mov     ecx, dword ptr [ebp+v.___u0+8]; c
0x10149f76  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x10149f7b  mov     esi, eax
0x10149f7d  lea     ecx, [ebp+s]; ppref
0x10149f80  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10149f85  mov     [ebp+s._p], esi
0x10149f88  lea     eax, [ebp+pEncNode]
0x10149f8b  push    eax; ppNode
0x10149f8c  push    dword ptr [ebx+28h]; pDoc
0x10149f8f  push    0; ulContentLen
0x10149f91  push    0; pwcContext
0x10149f93  push    esi; pText
0x10149f94  push    [ebp+pXmlDecl._p]; pParent
0x10149f97  mov     edx, edi; pName
0x10149f99  push    0Fh
0x10149f9b  pop     ecx; type
0x10149f9c  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x10149fa1  lea     eax, [ebp+v]
0x10149fa4  push    eax; pvarg
0x10149fa5  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10149fab  lea     ecx, [ebp+pEncNode]; ppref
0x10149fae  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x10149fb3  mov     ecx, [ebp+pReader]
0x10149fb6  mov     eax, [ecx]
0x10149fb8  mov     esi, [eax+14h]
0x10149fbb  lea     eax, [ebp+v]
0x10149fbe  push    eax
0x10149fbf  push    offset aXmldeclStandal; "xmldecl-standalone"
0x10149fc4  push    ecx
0x10149fc5  mov     ecx, esi; this
0x10149fc7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149fcd  call    esi
0x10149fcf  test    eax, eax
0x10149fd1  js      short loc_1014A037
0x10149fd3  cmp     dword ptr [ebp+v.___u0+8], 0
0x10149fd7  jz      short loc_1014A037
0x10149fd9  mov     esi, [ebx+34h]
0x10149fdc  push    6
0x10149fde  pop     ecx; i
0x10149fdf  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149fe4  push    0; pPrefix
0x10149fe6  push    eax; name
0x10149fe7  mov     ecx, esi; this
0x10149fe9  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149fee  mov     edi, eax
0x10149ff0  mov     [ebp+pStdNode._p], 0
0x10149ff7  mov     ecx, dword ptr [ebp+v.___u0+8]; c
0x10149ffa  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x10149fff  mov     esi, eax
0x1014a001  lea     ecx, [ebp+s]; ppref
0x1014a004  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1014a009  mov     [ebp+s._p], esi
0x1014a00c  lea     eax, [ebp+pStdNode]
0x1014a00f  push    eax; ppNode
0x1014a010  push    dword ptr [ebx+28h]; pDoc
0x1014a013  push    0; ulContentLen
0x1014a015  push    0; pwcContext
0x1014a017  push    esi; pText
0x1014a018  push    [ebp+pXmlDecl._p]; pParent
0x1014a01b  mov     edx, edi; pName
0x1014a01d  push    0Fh
0x1014a01f  pop     ecx; type
0x1014a020  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x1014a025  lea     eax, [ebp+v]
0x1014a028  push    eax; pvarg
0x1014a029  call    ds:__imp__VariantClear@4; VariantClear(x)
0x1014a02f  lea     ecx, [ebp+pStdNode]; ppref
0x1014a032  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x1014a037  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1014a03e  lea     ecx, [ebp+pNewNode]; ppref
0x1014a041  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x1014a046  lea     ecx, [ebp+pXmlDecl]; ppref
0x1014a049  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x1014a04e  mov     eax, [ebp+pReader]
0x1014a051  mov     ecx, [eax]
0x1014a053  push    eax
0x1014a054  mov     esi, [ecx+8]
0x1014a057  mov     ecx, esi; this
0x1014a059  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1014a05f  call    esi
0x1014a061  jmp     short loc_1014A0C5
0x1014a063  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x1014a066  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1014a06b  retn
0x1014a06c  mov     esp, [ebp+ms_exc.old_esp]
0x1014a06f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1014a074  cmp     [ebp+pXmlDecl._p], 0
0x1014a078  jz      short loc_1014A084
0x1014a07a  xor     edx, edx; pref
0x1014a07c  lea     ecx, [ebp+pXmlDecl]; ppref
0x1014a07f  call    ?weakAssign@@YGXPAPAVObject@@PAX@Z; weakAssign(Object * *,void *)
0x1014a084  cmp     [ebp+pNewNode._p], 0
0x1014a088  jz      short loc_1014A094
0x1014a08a  xor     edx, edx; pref
0x1014a08c  lea     ecx, [ebp+pNewNode]; ppref
0x1014a08f  call    ?weakAssign@@YGXPAPAVObject@@PAX@Z; weakAssign(Object * *,void *)
0x1014a094  call    ?throwAgain@Exception@@SGXXZ; Exception::throwAgain(void)
  ... truncated ...
```
