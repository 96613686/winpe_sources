# SAXBuilder::startDocument(void)

- ea: `0x10149bf0`
- end: `0x10149fd9`
- name: `?startDocument@SAXBuilder@@UAGJXZ`
- size: `1001`
- prototype: `HRESULT __stdcall(SAXBuilder *this)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10149fe0`
- `0x10149ff0`

## callees

- `0x1003ca26`
- `0x1003f548`
- `0x1003fba3`
- `0x1003fe02`
- `0x10040be6`
- `0x10040c44`
- `0x1004fc3e`
- `0x1005064c`
- `0x1005652d`
- `0x10064cd1`
- `0x100674af`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x1007818b`
- `0x1008b6a9`
- `0x1008c47b`
- `0x1014905d`
- `0x10149bf0`
- `0x1014a7aa`
- `0x1014affc`

## import_xrefs

- `OLEAUT32!__imp__VariantClear@4` at `0x10149e19`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149e95`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149f19`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149e19`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149e95`
- `OLEAUT32!__imp__VariantClear@4` at `0x10149f19`

## string_xrefs

- `0x10149d6b`: `xmldecl-version`
- `0x10149eaf`: `xmldecl-standalone`
- `0x10149e2b`: `xmldecl-encoding`

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
  int v10; // eax
  String *v11; // esi
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
    v3 = (NodeBuilder *)_MemAlloc(0x70u, 12);
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
0x10149bf0  push    38h
0x10149bf2  push    offset stru_1017D330
0x10149bf7  call    __SEH_prolog4
0x10149bfc  lea     ecx, [ebp+_EnsureTls]; this
0x10149bff  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x10149c04  cmp     [ebp+_EnsureTls._tlsdata], 0
0x10149c08  jnz     short loc_10149C14
0x10149c0a  mov     eax, 80004005h
0x10149c0f  jmp     loc_10149FC7
0x10149c14  xor     eax, eax
0x10149c16  mov     [ebp+_EnsureTls._tlsdata], eax
0x10149c19  mov     [ebp+s._p], eax
0x10149c1c  mov     [ebp+ms_exc.registration.TryLevel], eax
0x10149c1f  mov     ebx, [ebp+this]
0x10149c22  mov     edi, [ebx+28h]
0x10149c25  mov     [ebx+56h], al
0x10149c28  lea     ecx, [ebx+34h]; ppref
0x10149c2b  mov     edx, [edi+6Ch]; pref
0x10149c2e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149c33  push    0Ch
0x10149c35  pop     edx; dwFlags
0x10149c36  push    70h ; 'p'
0x10149c38  pop     ecx; cb
0x10149c39  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x10149c3e  push    edi; pDoc
0x10149c3f  mov     ecx, eax; this
0x10149c41  call    ??0NodeBuilder@@QAE@PAVDocument@@@Z; NodeBuilder::NodeBuilder(Document *)
0x10149c46  mov     ecx, eax; this
0x10149c48  mov     [ebx+38h], ecx
0x10149c4b  lea     eax, [ebx+24h]
0x10149c4e  push    eax; pCallback
0x10149c4f  call    ?startDocument@NodeBuilder@@QAEXPAVParserCallbacks@1@@Z; NodeBuilder::startDocument(NodeBuilder::ParserCallbacks *)
0x10149c54  lea     ecx, [ebx+3Ch]; ppref
0x10149c57  mov     edx, [edi+70h]; pref
0x10149c5a  call    ?weakAssign@@YGXPAPAVObject@@PAX@Z; weakAssign(Object * *,void *)
0x10149c5f  mov     eax, [ebx+40h]
0x10149c62  test    eax, eax
0x10149c64  jz      short loc_10149C6D
0x10149c66  mov     dword ptr [eax+8], 0
0x10149c6d  mov     eax, [ebx+44h]
0x10149c70  test    eax, eax
0x10149c72  jz      short loc_10149C7B
0x10149c74  mov     dword ptr [eax+8], 0
0x10149c7b  mov     byte ptr [ebx+54h], 0
0x10149c7f  mov     dword ptr [ebx+50h], 2
0x10149c86  mov     dword ptr [ebx+4Ch], 0
0x10149c8d  lea     ecx, [ebx+30h]; ppref
0x10149c90  xor     edx, edx; pref
0x10149c92  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149c97  mov     ecx, [ebx+2Ch]
0x10149c9a  test    ecx, ecx
0x10149c9c  jz      short loc_10149CB6
0x10149c9e  mov     eax, [ecx]
0x10149ca0  mov     esi, [eax]
0x10149ca2  lea     eax, [ebx+30h]
0x10149ca5  push    eax
0x10149ca6  push    offset _IID_IMXRAttributes
0x10149cab  push    ecx
0x10149cac  mov     ecx, esi; this
0x10149cae  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149cb4  call    esi
0x10149cb6  mov     ecx, [ebx+2Ch]
0x10149cb9  test    ecx, ecx
0x10149cbb  jz      loc_10149FB5
0x10149cc1  mov     [ebp+pwszUrl], 0
0x10149cc8  mov     eax, [ecx]
0x10149cca  mov     esi, [eax+18h]
0x10149ccd  lea     eax, [ebp+pwszUrl]
0x10149cd0  push    eax
0x10149cd1  push    ecx
0x10149cd2  mov     ecx, esi; this
0x10149cd4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149cda  call    esi
0x10149cdc  mov     ecx, eax; hr
0x10149cde  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x10149ce3  mov     edx, 7FFFFFFFh; cchMax
0x10149ce8  mov     ecx, [ebp+pwszUrl]; psz
0x10149ceb  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x10149cf0  test    eax, eax
0x10149cf2  jz      short loc_10149D02
0x10149cf4  mov     edx, eax; length
0x10149cf6  mov     ecx, [ebp+pwszUrl]; c
0x10149cf9  call    ?newString@String@@SGPAV1@PBGH@Z; String::newString(ushort const *,int)
0x10149cfe  mov     esi, eax
0x10149d00  jmp     short loc_10149D04
0x10149d02  xor     esi, esi
0x10149d04  lea     ecx, [ebp+s]; ppref
0x10149d07  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10149d0c  mov     [ebp+s._p], esi
0x10149d0f  lea     ecx, [edi+8Ch]; ppref
0x10149d15  mov     edx, esi; pref
0x10149d17  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149d1c  lea     ecx, [edi+88h]; ppref
0x10149d22  cmp     dword ptr [ecx], 0
0x10149d25  jnz     short loc_10149D2E
0x10149d27  mov     edx, esi; pref
0x10149d29  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10149d2e  mov     [ebp+pReader], 0
0x10149d35  mov     ecx, [ebx+2Ch]
0x10149d38  mov     eax, [ecx]
0x10149d3a  mov     esi, [eax]
0x10149d3c  lea     eax, [ebp+pReader]
0x10149d3f  push    eax
0x10149d40  push    offset _IID_ISAXXMLReader
0x10149d45  push    ecx
0x10149d46  mov     ecx, esi; this
0x10149d48  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149d4e  call    esi
0x10149d50  test    eax, eax
0x10149d52  js      loc_10149FB5
0x10149d58  xor     eax, eax
0x10149d5a  inc     eax
0x10149d5b  mov     word ptr [ebp+v.___u0], ax
0x10149d5f  mov     ecx, [ebp+pReader]
0x10149d62  mov     eax, [ecx]
0x10149d64  mov     esi, [eax+14h]
0x10149d67  lea     eax, [ebp+v]
0x10149d6a  push    eax
0x10149d6b  push    offset aXmldeclVersion; "xmldecl-version"
0x10149d70  push    ecx
0x10149d71  mov     ecx, esi; this
0x10149d73  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149d79  call    esi
0x10149d7b  test    eax, eax
0x10149d7d  js      loc_10149F3E
0x10149d83  cmp     dword ptr [ebp+v.___u0+8], 0
0x10149d87  jz      loc_10149F3E
0x10149d8d  mov     [ebp+pXmlDecl._p], 0
0x10149d94  mov     [ebp+pNewNode._p], 0
0x10149d9b  mov     [ebp+ms_exc.registration.TryLevel], 1
0x10149da2  mov     esi, [ebx+34h]
0x10149da5  push    5
0x10149da7  pop     ecx; i
0x10149da8  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149dad  push    0; pPrefix
0x10149daf  push    eax; name
0x10149db0  mov     ecx, esi; this
0x10149db2  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149db7  lea     ecx, [ebp+pXmlDecl]
0x10149dba  push    ecx; ppNode
0x10149dbb  push    dword ptr [ebx+28h]; pDoc
0x10149dbe  xor     ecx, ecx
0x10149dc0  push    ecx; ulContentLen
0x10149dc1  push    ecx; pwcContext
0x10149dc2  push    ecx; pText
0x10149dc3  push    dword ptr [edi+70h]; pParent
0x10149dc6  mov     edx, eax; pName
0x10149dc8  push    12h
0x10149dca  pop     ecx; type
0x10149dcb  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x10149dd0  mov     esi, [ebx+34h]
0x10149dd3  push    2
0x10149dd5  pop     ecx; i
0x10149dd6  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149ddb  push    0; pPrefix
0x10149ddd  push    eax; name
0x10149dde  mov     ecx, esi; this
0x10149de0  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149de5  mov     edi, eax
0x10149de7  mov     ecx, dword ptr [ebp+v.___u0+8]; c
0x10149dea  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x10149def  mov     esi, eax
0x10149df1  lea     ecx, [ebp+s]; ppref
0x10149df4  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10149df9  mov     [ebp+s._p], esi
0x10149dfc  lea     eax, [ebp+pNewNode]
0x10149dff  push    eax; ppNode
0x10149e00  push    dword ptr [ebx+28h]; pDoc
0x10149e03  push    0; ulContentLen
0x10149e05  push    0; pwcContext
0x10149e07  push    esi; pText
0x10149e08  push    [ebp+pXmlDecl._p]; pParent
0x10149e0b  mov     edx, edi; pName
0x10149e0d  push    0Fh
0x10149e0f  pop     ecx; type
0x10149e10  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x10149e15  lea     eax, [ebp+v]
0x10149e18  push    eax; pvarg
0x10149e19  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10149e1f  mov     ecx, [ebp+pReader]
0x10149e22  mov     eax, [ecx]
0x10149e24  mov     esi, [eax+14h]
0x10149e27  lea     eax, [ebp+v]
0x10149e2a  push    eax
0x10149e2b  push    offset aXmldeclEncodin; "xmldecl-encoding"
0x10149e30  push    ecx
0x10149e31  mov     ecx, esi; this
0x10149e33  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149e39  call    esi
0x10149e3b  test    eax, eax
0x10149e3d  js      short loc_10149EA3
0x10149e3f  cmp     dword ptr [ebp+v.___u0+8], 0
0x10149e43  jz      short loc_10149EA3
0x10149e45  mov     esi, [ebx+34h]
0x10149e48  push    3
0x10149e4a  pop     ecx; i
0x10149e4b  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149e50  push    0; pPrefix
0x10149e52  push    eax; name
0x10149e53  mov     ecx, esi; this
0x10149e55  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149e5a  mov     edi, eax
0x10149e5c  mov     [ebp+pEncNode._p], 0
0x10149e63  mov     ecx, dword ptr [ebp+v.___u0+8]; c
0x10149e66  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x10149e6b  mov     esi, eax
0x10149e6d  lea     ecx, [ebp+s]; ppref
0x10149e70  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10149e75  mov     [ebp+s._p], esi
0x10149e78  lea     eax, [ebp+pEncNode]
0x10149e7b  push    eax; ppNode
0x10149e7c  push    dword ptr [ebx+28h]; pDoc
0x10149e7f  push    0; ulContentLen
0x10149e81  push    0; pwcContext
0x10149e83  push    esi; pText
0x10149e84  push    [ebp+pXmlDecl._p]; pParent
0x10149e87  mov     edx, edi; pName
0x10149e89  push    0Fh
0x10149e8b  pop     ecx; type
0x10149e8c  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x10149e91  lea     eax, [ebp+v]
0x10149e94  push    eax; pvarg
0x10149e95  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10149e9b  lea     ecx, [ebp+pEncNode]; ppref
0x10149e9e  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x10149ea3  mov     ecx, [ebp+pReader]
0x10149ea6  mov     eax, [ecx]
0x10149ea8  mov     esi, [eax+14h]
0x10149eab  lea     eax, [ebp+v]
0x10149eae  push    eax
0x10149eaf  push    offset aXmldeclStandal; "xmldecl-standalone"
0x10149eb4  push    ecx
0x10149eb5  mov     ecx, esi; this
0x10149eb7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149ebd  call    esi
0x10149ebf  test    eax, eax
0x10149ec1  js      short loc_10149F27
0x10149ec3  cmp     dword ptr [ebp+v.___u0+8], 0
0x10149ec7  jz      short loc_10149F27
0x10149ec9  mov     esi, [ebx+34h]
0x10149ecc  push    6
0x10149ece  pop     ecx; i
0x10149ecf  call    ?name@XMLNames@@SGPAVName@@H@Z; XMLNames::name(int)
0x10149ed4  push    0; pPrefix
0x10149ed6  push    eax; name
0x10149ed7  mov     ecx, esi; this
0x10149ed9  call    ?createNameDef@NamespaceMgr@@QAEPAVNameDef@@PAVName@@PAVAtom@@@Z; NamespaceMgr::createNameDef(Name *,Atom *)
0x10149ede  mov     edi, eax
0x10149ee0  mov     [ebp+pStdNode._p], 0
0x10149ee7  mov     ecx, dword ptr [ebp+v.___u0+8]; c
0x10149eea  call    ?newString@String@@SGPAV1@PBG@Z; String::newString(ushort const *)
0x10149eef  mov     esi, eax
0x10149ef1  lea     ecx, [ebp+s]; ppref
0x10149ef4  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10149ef9  mov     [ebp+s._p], esi
0x10149efc  lea     eax, [ebp+pStdNode]
0x10149eff  push    eax; ppNode
0x10149f00  push    dword ptr [ebx+28h]; pDoc
0x10149f03  push    0; ulContentLen
0x10149f05  push    0; pwcContext
0x10149f07  push    esi; pText
0x10149f08  push    [ebp+pXmlDecl._p]; pParent
0x10149f0b  mov     edx, edi; pName
0x10149f0d  push    0Fh
0x10149f0f  pop     ecx; type
0x10149f10  call    ?newNode@Node@@KGXW4NodeType@1@PAVNameDef@@PAV1@PAVString@@PBGKPAVDocument@@PAPAV1@@Z; Node::newNode(Node::NodeType,NameDef *,Node *,String *,ushort const *,ulong,Document *,Node * *)
0x10149f15  lea     eax, [ebp+v]
0x10149f18  push    eax; pvarg
0x10149f19  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10149f1f  lea     ecx, [ebp+pStdNode]; ppref
0x10149f22  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x10149f27  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10149f2e  lea     ecx, [ebp+pNewNode]; ppref
0x10149f31  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x10149f36  lea     ecx, [ebp+pXmlDecl]; ppref
0x10149f39  call    ?weakRelease@@YGXPAPAVObject@@@Z; weakRelease(Object * *)
0x10149f3e  mov     eax, [ebp+pReader]
0x10149f41  mov     ecx, [eax]
0x10149f43  push    eax
0x10149f44  mov     esi, [ecx+8]
0x10149f47  mov     ecx, esi; this
0x10149f49  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10149f4f  call    esi
0x10149f51  jmp     short loc_10149FB5
0x10149f53  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10149f56  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x10149f5b  retn
0x10149f5c  mov     esp, [ebp+ms_exc.old_esp]
0x10149f5f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10149f64  cmp     [ebp+pXmlDecl._p], 0
0x10149f68  jz      short loc_10149F74
0x10149f6a  xor     edx, edx; pref
0x10149f6c  lea     ecx, [ebp+pXmlDecl]; ppref
0x10149f6f  call    ?weakAssign@@YGXPAPAVObject@@PAX@Z; weakAssign(Object * *,void *)
0x10149f74  cmp     [ebp+pNewNode._p], 0
0x10149f78  jz      short loc_10149F84
0x10149f7a  xor     edx, edx; pref
0x10149f7c  lea     ecx, [ebp+pNewNode]; ppref
0x10149f7f  call    ?weakAssign@@YGXPAPAVObject@@PAX@Z; weakAssign(Object * *,void *)
0x10149f84  call    ?throwAgain@Exception@@SGXXZ; Exception::throwAgain(void)
  ... truncated ...
```
