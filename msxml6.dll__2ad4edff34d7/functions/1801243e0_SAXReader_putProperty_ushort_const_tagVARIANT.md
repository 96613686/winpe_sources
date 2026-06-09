# SAXReader::putProperty(ushort const *,tagVARIANT)

- ea: `0x1801243e0`
- end: `0x1801247ab`
- name: `?putProperty@SAXReader@@UEAAJPEBGUtagVARIANT@@@Z`
- size: `971`
- prototype: `__int64 __fastcall(SAXReader *this, wchar_t *pwhName, tagVARIANT *varValue)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180009490`
- `0x1800502b0`
- `0x180056bdc`
- `0x1800746f0`
- `0x180074b1c`
- `0x180074c84`
- `0x180074cd4`
- `0x18009f718`
- `0x1800a3e04`
- `0x180123008`
- `0x1801243e0`
- `0x18014d9dc`
- `0x18017851c`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x1801246c2`
- `OLEAUT32!__imp_VariantCopy` at `0x1801246c2`

## pseudocode

```c
__int64 __fastcall SAXReader::putProperty(SAXReader *this, wchar_t *pwhName, tagVARIANT *varValue)
{
  int SAXSchemaProxy; // edi
  ISAXDeclHandler *v7; // r13
  int v8; // esi
  SAXSchemaProxy *p; // rcx
  DTSReader *v11; // rcx
  _reference<IMXSchemaDeclHandler> *p_pDeclHandler; // rcx
  void *v13; // rdx
  ISAXLexicalHandler *v14; // rsi
  DTSReader *v15; // rcx
  const _GUID *v16; // rdx
  const _GUID *v17; // r8
  HRESULT v18; // r9d
  SAXSchemaProxy *v19; // rsi
  bool v20; // al
  int v21; // eax
  ISAXLexicalHandler *pLexicalHandler; // [rsp+30h] [rbp-78h]
  IMXSchemaDeclHandler *pSchemaDeclHandler; // [rsp+38h] [rbp-70h]
  SchemaCache *pSchemaCache; // [rsp+40h] [rbp-68h]
  tagVARIANT v25; // [rsp+60h] [rbp-48h] BYREF
  EnsureTls _EnsureTls; // [rsp+C8h] [rbp+20h] BYREF

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( !_EnsureTls._tlsdata )
    return 2147500037LL;
  SAXSchemaProxy = 0;
  v7 = 0;
  pLexicalHandler = 0;
  pSchemaDeclHandler = 0;
  pSchemaCache = 0;
  if ( pwhName )
    v8 = xstrlenw(pwhName, 0x7FFFFFFFu);
  else
    v8 = 0;
  if ( v8 == CodeStringPtr::declarationHandler.n && !memcmp_0(pwhName, CodeStringPtr::declarationHandler.pwh, 2LL * v8) )
  {
    v7 = (ISAXDeclHandler *)Variant::QIForIID(varValue, &IID_ISAXDeclHandler);
    p = this->_pSchemaProxy._p;
    if ( p )
      assign(&p->_pDeclHandler._p, v7);
    else
      Reader::SetDeclHandler(this, v7);
    v11 = this->_pDtsReader._p;
    if ( !v11 )
      goto $CleanUp_283;
    p_pDeclHandler = (_reference<IMXSchemaDeclHandler> *)&v11->_pDeclHandler;
    v13 = v7;
    goto LABEL_25;
  }
  if ( v8 == CodeStringPtr::lexicalHandler.n && !memcmp_0(pwhName, CodeStringPtr::lexicalHandler.pwh, 2LL * v8) )
  {
    v14 = (ISAXLexicalHandler *)Variant::QIForIID(varValue, &IID_ISAXLexicalHandler);
    pLexicalHandler = v14;
    Reader::SetLexicalHandler(this, v14);
    v15 = this->_pDtsReader._p;
    if ( v15 )
    {
      p_pDeclHandler = (_reference<IMXSchemaDeclHandler> *)&v15->_pLexicalHandler;
      v13 = v14;
LABEL_25:
      assign(&p_pDeclHandler->_p, v13);
    }
  }
  else
  {
    if ( v8 != CodeStringPtr::schemaDeclarationHandler.n
      || memcmp_0(pwhName, CodeStringPtr::schemaDeclarationHandler.pwh, 2LL * v8) )
    {
      if ( v8 == CodeStringPtr::schemas.n && !memcmp_0(pwhName, CodeStringPtr::schemas.pwh, 2LL * v8) )
      {
        if ( this->_fBusy )
        {
          SAXSchemaProxy = -2147467259;
        }
        else if ( this->_pSchemaProxy._p
               || (SAXSchemaProxy = SAXReader::CreateSAXSchemaProxy(this, &this->_pSchemaProxy._p), SAXSchemaProxy >= 0) )
        {
          pSchemaCache = (SchemaCache *)ObjectFromVariant(varValue, v16, v17, v18);
          v19 = this->_pSchemaProxy._p;
          assign(&v19->_pSchemaCache._p, pSchemaCache);
          v20 = v19->_fValidation && (v19->_pSchemaCache._p || v19->_fUseInlineSchema || v19->_fUseSchemaLocation);
          v19->_fDoValidation = v20;
        }
      }
      else if ( v8 == CodeStringPtr::domNode.n && !memcmp_0(pwhName, CodeStringPtr::domNode.pwh, 2LL * v8) )
      {
        SAXSchemaProxy = -2147467259;
      }
      else
      {
        if ( v8 == CodeStringPtr::inputSource.n && !memcmp_0(pwhName, CodeStringPtr::inputSource.pwh, 2LL * v8) )
        {
          v21 = VariantCopy(&this->_varInput, varValue);
        }
        else
        {
          v25 = *varValue;
          v21 = Reader::putProperty(this, pwhName, &v25);
        }
        SAXSchemaProxy = v21;
      }
      goto $CleanUp_283;
    }
    if ( this->_pSchemaProxy._p
      || (SAXSchemaProxy = SAXReader::CreateSAXSchemaProxy(this, &this->_pSchemaProxy._p), SAXSchemaProxy >= 0) )
    {
      pSchemaDeclHandler = (IMXSchemaDeclHandler *)Variant::QIForIID(varValue, &IID_IMXSchemaDeclHandler);
      p_pDeclHandler = &this->_pSchemaProxy._p->_pSchemaDeclHandler;
      v13 = pSchemaDeclHandler;
      goto LABEL_25;
    }
  }
$CleanUp_283:
  if ( v7 )
    v7->Release(v7);
  if ( pLexicalHandler )
    pLexicalHandler->Release(pLexicalHandler);
  if ( pSchemaDeclHandler )
    pSchemaDeclHandler->Release(pSchemaDeclHandler);
  if ( pSchemaCache )
    pSchemaCache->Release(pSchemaCache);
  return (unsigned int)SAXSchemaProxy;
}

```

## disassembly

```asm
0x1801243e0  mov     rax, rsp
0x1801243e3  mov     [rax+8], rsi
0x1801243e7  mov     [rax+18h], varValue
0x1801243eb  push    rdi
0x1801243ec  push    r12
0x1801243ee  push    r13
0x1801243f0  push    r14
0x1801243f2  push    r15
0x1801243f4  sub     rsp, 80h
0x1801243fb  mov     r15, pwhName
0x1801243fe  mov     r14, this
0x180124401  lea     this, [rax+20h]; this
0x180124405  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x18012440a  cmp     [rsp+0A8h+_EnsureTls._tlsdata], 0
0x180124413  jnz     short loc_18012441F
0x180124415  mov     eax, 80004005h
0x18012441a  jmp     loc_180124792
0x18012441f  xor     edi, edi
0x180124421  xor     r13d, r13d
0x180124424  mov     [rsp+0A8h+pDeclHandler], r13
0x180124429  mov     [rsp+0A8h+pLexicalHandler], rdi
0x18012442e  mov     [rsp+0A8h+pSchemaDeclHandler], rdi
0x180124433  mov     [rsp+0A8h+pSchemaCache], rdi
0x180124438  mov     [rsp+0A8h+name.pwh], r15
0x18012443d  test    r15, r15
0x180124440  jz      short loc_180124453
0x180124442  mov     edx, 7FFFFFFFh; cchMax
0x180124447  mov     this, r15; psz
0x18012444a  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x18012444f  mov     esi, eax
0x180124451  jmp     short loc_180124455
0x180124453  xor     esi, esi
0x180124455  mov     [rsp+0A8h+name.n], esi
0x180124459  movsxd  r12, esi
0x18012445c  add     r12, r12
0x18012445f  cmp     esi, cs:?declarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::declarationHandler ...
0x180124465  jnz     short loc_180124481
0x180124467  mov     varValue, r12; Size
0x18012446a  mov     pwhName, cs:?declarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x180124471  mov     this, r15; Buf1
0x180124474  call    memcmp_0
0x180124479  test    eax, eax
0x18012447b  jnz     short loc_180124481
0x18012447d  mov     al, 1
0x18012447f  jmp     short loc_180124483
0x180124481  xor     al, al
0x180124483  test    al, al
0x180124485  jz      short loc_1801244E1
0x180124487  lea     pwhName, IID_ISAXDeclHandler; piid
0x18012448e  mov     this, [rsp+0A8h+pVar]; pVar
0x180124496  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x18012449b  mov     r13, rax
0x18012449e  mov     [rsp+0A8h+pDeclHandler], rax
0x1801244a3  mov     this, [r14+0A10h]
0x1801244aa  mov     pwhName, rax; pDeclHandler
0x1801244ad  test    this, this
0x1801244b0  jz      short loc_1801244BD
0x1801244b2  add     this, 60h ; '`'; ppref
0x1801244b6  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801244bb  jmp     short loc_1801244C5
0x1801244bd  mov     this, r14; this
0x1801244c0  call    ?SetDeclHandler@Reader@@QEAAXPEAUISAXDeclHandler@@@Z; Reader::SetDeclHandler(ISAXDeclHandler *)
0x1801244c5  mov     this, [r14+0A08h]
0x1801244cc  test    this, this
0x1801244cf  jz      loc_1801246FB
0x1801244d5  add     this, 68h ; 'h'
0x1801244d9  mov     pwhName, r13
0x1801244dc  jmp     loc_1801245A9
0x1801244e1  cmp     esi, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::lexicalHandler ...
0x1801244e7  jnz     short loc_18012453F
0x1801244e9  mov     varValue, r12; Size
0x1801244ec  mov     pwhName, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1801244f3  mov     this, r15; Buf1
0x1801244f6  call    memcmp_0
0x1801244fb  test    eax, eax
0x1801244fd  jnz     short loc_18012453F
0x1801244ff  lea     pwhName, IID_ISAXLexicalHandler; piid
0x180124506  mov     this, [rsp+0A8h+pVar]; pVar
0x18012450e  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x180124513  mov     rsi, rax
0x180124516  mov     [rsp+0A8h+pLexicalHandler], rax
0x18012451b  mov     pwhName, rax; pLexicalHandler
0x18012451e  mov     this, r14; this
0x180124521  call    ?SetLexicalHandler@Reader@@QEAAXPEAUISAXLexicalHandler@@@Z; Reader::SetLexicalHandler(ISAXLexicalHandler *)
0x180124526  mov     this, [r14+0A08h]
0x18012452d  test    this, this
0x180124530  jz      loc_1801246FB
0x180124536  add     this, 70h ; 'p'
0x18012453a  mov     pwhName, rsi
0x18012453d  jmp     short loc_1801245A9
0x18012453f  cmp     esi, cs:?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemaDeclarationHandler ...
0x180124545  jnz     short loc_1801245B3
0x180124547  movsxd  varValue, esi
0x18012454a  add     varValue, varValue; Size
0x18012454d  mov     pwhName, cs:?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x180124554  mov     this, r15; Buf1
0x180124557  call    memcmp_0
0x18012455c  test    eax, eax
0x18012455e  jnz     short loc_1801245B3
0x180124560  lea     rsi, [r14+0A10h]
0x180124567  cmp     qword ptr [rsi], 0
0x18012456b  jnz     short loc_180124586
0x18012456d  mov     pwhName, rsi; ppSchemaProxy
0x180124570  mov     this, r14; this
0x180124573  call    ?CreateSAXSchemaProxy@SAXReader@@IEAAJPEAPEAVSAXSchemaProxy@@@Z; SAXReader::CreateSAXSchemaProxy(SAXSchemaProxy * *)
0x180124578  mov     edi, eax
0x18012457a  mov     [rsp+0A8h+hr], eax
0x18012457e  test    eax, eax
0x180124580  js      $CleanUp_283
0x180124586  lea     pwhName, IID_IMXSchemaDeclHandler; piid
0x18012458d  mov     this, [rsp+0A8h+pVar]; pVar
0x180124595  call    ?QIForIID@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@PEBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x18012459a  mov     [rsp+0A8h+pSchemaDeclHandler], rax
0x18012459f  mov     this, [rsi]
0x1801245a2  sub     this, 0FFFFFFFFFFFFFF80h; ppref
0x1801245a6  mov     pwhName, rax; pref
0x1801245a9  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801245ae  jmp     loc_1801246FB
0x1801245b3  cmp     esi, cs:?schemas@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemas ...
0x1801245b9  jnz     loc_180124666
0x1801245bf  movsxd  varValue, esi
0x1801245c2  add     varValue, varValue; Size
0x1801245c5  mov     pwhName, cs:?schemas@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1801245cc  mov     this, r15; Buf1
0x1801245cf  call    memcmp_0
0x1801245d4  test    eax, eax
0x1801245d6  jnz     loc_180124666
0x1801245dc  cmp     [r14+0A00h], al
0x1801245e3  jz      short loc_1801245F3
0x1801245e5  mov     edi, 80004005h
0x1801245ea  mov     [rsp+0A8h+hr], edi
0x1801245ee  jmp     $CleanUp_283
0x1801245f3  lea     rsi, [r14+0A10h]
0x1801245fa  cmp     qword ptr [rsi], 0
0x1801245fe  jnz     short loc_180124619
0x180124600  mov     pwhName, rsi; ppSchemaProxy
0x180124603  mov     this, r14; this
0x180124606  call    ?CreateSAXSchemaProxy@SAXReader@@IEAAJPEAPEAVSAXSchemaProxy@@@Z; SAXReader::CreateSAXSchemaProxy(SAXSchemaProxy * *)
0x18012460b  mov     edi, eax
0x18012460d  mov     [rsp+0A8h+hr], eax
0x180124611  test    eax, eax
0x180124613  js      $CleanUp_283
0x180124619  mov     this, [rsp+0A8h+pVar]; pVar
0x180124621  call    ?ObjectFromVariant@@YAPEAXPEAUtagVARIANT@@AEBU_GUID@@1J@Z; ObjectFromVariant(tagVARIANT *,_GUID const &,_GUID const &,long)
0x180124626  mov     [rsp+0A8h+pSchemaCache], rax
0x18012462b  mov     rsi, [rsi]
0x18012462e  lea     r14, [rsi+88h]
0x180124635  mov     pwhName, rax; pref
0x180124638  mov     this, r14; ppref
0x18012463b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180124640  cmp     byte ptr [rsi+79h], 0
0x180124644  jz      short loc_18012465C
0x180124646  cmp     qword ptr [r14], 0
0x18012464a  jnz     short loc_180124658
0x18012464c  cmp     byte ptr [rsi+7Ch], 0
0x180124650  jnz     short loc_180124658
0x180124652  cmp     byte ptr [rsi+7Dh], 0
0x180124656  jz      short loc_18012465C
0x180124658  mov     al, 1
0x18012465a  jmp     short loc_18012465E
0x18012465c  xor     al, al
0x18012465e  mov     [rsi+78h], al
0x180124661  jmp     loc_1801246FB
0x180124666  cmp     esi, cs:?domNode@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::domNode ...
0x18012466c  jnz     short loc_180124692
0x18012466e  movsxd  varValue, esi
0x180124671  add     varValue, varValue; Size
0x180124674  mov     pwhName, cs:?domNode@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x18012467b  mov     this, r15; Buf1
0x18012467e  call    memcmp_0
0x180124683  test    eax, eax
0x180124685  jnz     short loc_180124692
0x180124687  mov     edi, 80004005h
0x18012468c  mov     [rsp+0A8h+hr], edi
0x180124690  jmp     short loc_1801246FB
0x180124692  cmp     esi, cs:?inputSource@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::inputSource ...
0x180124698  jnz     short loc_1801246CA
0x18012469a  movsxd  varValue, esi
0x18012469d  add     varValue, varValue; Size
0x1801246a0  mov     pwhName, cs:?inputSource@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1801246a7  mov     this, r15; Buf1
0x1801246aa  call    memcmp_0
0x1801246af  test    eax, eax
0x1801246b1  jnz     short loc_1801246CA
0x1801246b3  lea     this, [r14+0A18h]; pvargDest
0x1801246ba  mov     pwhName, [rsp+0A8h+pVar]; pvargSrc
0x1801246c2  call    cs:__imp_VariantCopy
0x1801246c8  jmp     short loc_1801246F5
0x1801246ca  mov     rax, [rsp+0A8h+pVar]
0x1801246d2  movups  xmm0, xmmword ptr [rax]
0x1801246d5  movaps  [rsp+0A8h+var_48], xmm0
0x1801246da  movsd   xmm1, qword ptr [rax+10h]
0x1801246df  movsd   [rsp+0A8h+var_38], xmm1
0x1801246e5  lea     varValue, [rsp+0A8h+var_48]
0x1801246ea  mov     pwhName, r15
0x1801246ed  mov     this, r14
0x1801246f0  call    ?putProperty@Reader@@UEAAJPEBGUtagVARIANT@@@Z; Reader::putProperty(ushort const *,tagVARIANT)
0x1801246f5  mov     [rsp+0A8h+hr], eax
0x1801246f9  mov     edi, eax
0x1801246fb  jmp     short $CleanUp_283
0x1801246fd  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180124702  mov     ecx, cs:_tls_index
0x180124708  mov     rax, gs:58h
0x180124711  mov     edx, 8
0x180124716  mov     rax, [rax+this*8]
0x18012471a  mov     this, [rax+pwhName]
0x18012471e  mov     this, [this+8]
0x180124722  mov     rax, [this]
0x180124725  mov     rax, [rax+68h]
0x180124729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012472e  mov     edi, eax
0x180124730  mov     [rsp+0A8h+hr], eax
0x180124734  mov     r13, [rsp+0A8h+pDeclHandler]
0x180124739  test    r13, r13
0x18012473c  jz      short loc_18012474E
0x18012473e  mov     rax, [r13+0]
0x180124742  mov     this, r13
0x180124745  mov     rax, [rax+10h]
0x180124749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012474e  mov     this, [rsp+0A8h+pLexicalHandler]
0x180124753  test    this, this
0x180124756  jz      short loc_180124764
0x180124758  mov     rax, [this]
0x18012475b  mov     rax, [rax+10h]
0x18012475f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124764  mov     this, [rsp+0A8h+pSchemaDeclHandler]
0x180124769  test    this, this
0x18012476c  jz      short loc_18012477A
0x18012476e  mov     rax, [this]
0x180124771  mov     rax, [rax+10h]
0x180124775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012477a  mov     this, [rsp+0A8h+pSchemaCache]
0x18012477f  test    this, this
0x180124782  jz      short loc_180124790
0x180124784  mov     rax, [this]
0x180124787  mov     rax, [rax+10h]
0x18012478b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124790  mov     eax, edi
0x180124792  mov     rsi, [rsp+0A8h+arg_0]
0x18012479a  add     rsp, 80h
0x1801247a1  pop     r15
0x1801247a3  pop     r14
0x1801247a5  pop     r13
0x1801247a7  pop     r12
0x1801247a9  pop     rdi
0x1801247aa  retn
0x18017de3a  push    rbp
0x18017de3c  sub     rsp, 20h
0x18017de40  mov     rbp, rdx
0x18017de43  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18017de48  nop
0x18017de49  add     rsp, 20h
0x18017de4d  pop     rbp
0x18017de4e  retn
```
