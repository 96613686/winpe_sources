# SAXReader::getProperty(ushort const *,tagVARIANT *)

- ea: `0x1800920a0`
- end: `0x1800923a4`
- name: `?getProperty@SAXReader@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `772`
- prototype: `HRESULT __fastcall(SAXReader *this, const wchar_t *pwhName, tagVARIANT *pvarValue)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180082f30`
- `0x1800920a0`
- `0x18009f718`
- `0x1800a3e04`
- `0x18012b848`
- `0x18017020c`
- `0x180170260`
- `0x18017851c`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800920ec`
- `OLEAUT32!__imp_VariantInit` at `0x1800920ec`
- `OLEAUT32!__imp_VariantCopy` at `0x18009233f`
- `OLEAUT32!__imp_VariantCopy` at `0x18009233f`

## pseudocode

```c
__int64 __fastcall SAXReader::getProperty(SAXReader *this, const wchar_t *pwhName, tagVARIANT *pvarValue)
{
  unsigned int Property; // ebx
  DTSReader *p; // rcx
  const wchar_t *v9; // rax
  int v10; // ebx
  unsigned __int64 i; // rcx
  bool v12; // zf
  char v13; // al
  SAXSchemaProxy *v14; // rsi
  ISAXDeclHandler *v15; // rcx
  ISAXLexicalHandler *DeclHandler; // rax
  SAXSchemaProxy *v17; // rsi
  IMXSchemaDeclHandler *v18; // rcx
  SAXSchemaProxy *v19; // rsi
  SchemaCache *v20; // rcx

  if ( !(__int64)g_pfnEntry() )
    return 2147500037LL;
  if ( !pvarValue )
    return 2147942487LL;
  Property = -2147024809;
  VariantInit(pvarValue);
  p = this->_pDtsReader._p;
  if ( p )
    Property = DTSReader::getProperty(p, pwhName, pvarValue);
  if ( Property == -2147024809 )
  {
    if ( pwhName )
    {
      v9 = pwhName;
      v10 = 0;
      for ( i = 0; i < 0x7FFFFFFF && *v9; ++i )
      {
        ++v9;
        v10 = i + 1;
      }
    }
    else
    {
      v10 = 0;
    }
    if ( v10 != CodeStringPtr::declarationHandler.n
      || (v12 = memcmp_0(pwhName, CodeStringPtr::declarationHandler.pwh, 2LL * v10) == 0, v13 = 1, !v12) )
    {
      v13 = 0;
    }
    if ( v13 )
    {
      Property = 0;
      pvarValue->vt = 13;
      v14 = this->_pSchemaProxy._p;
      if ( v14 )
      {
        v15 = v14->_pDeclHandler._p;
        if ( v15 )
          v15->AddRef(v15);
        DeclHandler = (ISAXLexicalHandler *)v14->_pDeclHandler._p;
      }
      else
      {
        DeclHandler = (ISAXLexicalHandler *)Reader::GetDeclHandler(this);
      }
    }
    else
    {
      if ( v10 != CodeStringPtr::lexicalHandler.n || memcmp_0(pwhName, CodeStringPtr::lexicalHandler.pwh, 2LL * v10) )
      {
        if ( v10 == CodeStringPtr::schemaDeclarationHandler.n
          && !memcmp_0(pwhName, CodeStringPtr::schemaDeclarationHandler.pwh, 2LL * v10) )
        {
          Property = 0;
          pvarValue->vt = 13;
          v17 = this->_pSchemaProxy._p;
          if ( v17 )
          {
            v18 = v17->_pSchemaDeclHandler._p;
            if ( v18 )
              v18->AddRef(v18);
            DeclHandler = (ISAXLexicalHandler *)v17->_pSchemaDeclHandler._p;
            goto LABEL_26;
          }
        }
        else
        {
          if ( v10 != CodeStringPtr::schemas.n || memcmp_0(pwhName, CodeStringPtr::schemas.pwh, 2LL * v10) )
          {
            if ( v10 == CodeStringPtr::domNode.n && !memcmp_0(pwhName, CodeStringPtr::domNode.pwh, 2LL * v10) )
            {
              return (unsigned int)-2147467259;
            }
            else if ( v10 == CodeStringPtr::inputSource.n
                   && !memcmp_0(pwhName, CodeStringPtr::inputSource.pwh, 2LL * v10) )
            {
              return (unsigned int)VariantCopy(pvarValue, &this->_varInput);
            }
            else
            {
              return (unsigned int)Reader::getProperty(this, pwhName, pvarValue);
            }
          }
          Property = 0;
          pvarValue->vt = 9;
          v19 = this->_pSchemaProxy._p;
          if ( v19 )
          {
            v20 = v19->_pSchemaCache._p;
            if ( v20 )
              v20->AddRef(v20);
            DeclHandler = (ISAXLexicalHandler *)v19->_pSchemaCache._p;
            goto LABEL_26;
          }
        }
        pvarValue->llVal = 0;
        return Property;
      }
      Property = 0;
      pvarValue->vt = 13;
      DeclHandler = Reader::GetLexicalHandler(this);
    }
LABEL_26:
    pvarValue->llVal = (__int64)DeclHandler;
  }
  return Property;
}

```

## disassembly

```asm
0x1800920a0  push    rbx
0x1800920a2  push    rsi
0x1800920a3  push    rdi
0x1800920a4  push    r12
0x1800920a6  push    r14
0x1800920a8  push    r15
0x1800920aa  sub     rsp, 48h
0x1800920ae  mov     rdi, pvarValue
0x1800920b1  mov     rsi, pwhName
0x1800920b4  mov     r15, this
0x1800920b7  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x1800920be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800920c3  xor     r12d, r12d
0x1800920c6  test    rax, rax
0x1800920c9  jnz     short loc_1800920D5
0x1800920cb  mov     eax, 80004005h
0x1800920d0  jmp     loc_180092396
0x1800920d5  test    rdi, rdi
0x1800920d8  jnz     short loc_1800920E4
0x1800920da  mov     eax, 80070057h
0x1800920df  jmp     loc_180092396
0x1800920e4  mov     ebx, 80070057h
0x1800920e9  mov     this, rdi; pvarg
0x1800920ec  call    cs:__imp_VariantInit
0x1800920f2  nop
0x1800920f3  mov     this, [r15+0A08h]; this
0x1800920fa  test    this, this
0x1800920fd  jz      short loc_180092110
0x1800920ff  mov     pvarValue, rdi; pvarValue
0x180092102  mov     pwhName, rsi; pwhName
0x180092105  call    ?getProperty@DTSReader@@QEAAJPEBGPEAUtagVARIANT@@@Z; DTSReader::getProperty(ushort const *,tagVARIANT *)
0x18009210a  mov     ebx, eax
0x18009210c  mov     [rsp+78h+hr], eax
0x180092110  cmp     ebx, 80070057h
0x180092116  jnz     loc_18009235B
0x18009211c  mov     [rsp+78h+name.pwh], r12
0x180092121  mov     [rsp+78h+name.n], r12d
0x180092126  mov     [rsp+78h+name.pwh], rsi
0x18009212b  test    rsi, rsi
0x18009212e  jz      short loc_18009216F
0x180092130  mov     rax, rsi
0x180092133  mov     [rsp+78h+var_50], rax
0x180092138  mov     rbx, r12
0x18009213b  mov     [rsp+78h+arg_18], rbx
0x180092143  mov     this, r12
0x180092146  cmp     this, 7FFFFFFFh
0x18009214d  jnb     short loc_180092172
0x18009214f  cmp     [rax], r12w
0x180092153  jz      short loc_180092172
0x180092155  add     rax, 2
0x180092159  mov     [rsp+78h+var_50], rax
0x18009215e  lea     rbx, [this+1]
0x180092162  mov     [rsp+78h+arg_18], rbx
0x18009216a  mov     this, rbx
0x18009216d  jmp     short loc_180092146
0x18009216f  mov     ebx, r12d
0x180092172  mov     [rsp+78h+name.n], ebx
0x180092176  movsxd  r14, ebx
0x180092179  add     r14, r14
0x18009217c  cmp     ebx, cs:?declarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::declarationHandler ...
0x180092182  jnz     short loc_18009219C
0x180092184  mov     pvarValue, r14; Size
0x180092187  mov     pwhName, cs:?declarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x18009218e  mov     this, rsi; Buf1
0x180092191  call    memcmp_0
0x180092196  test    eax, eax
0x180092198  mov     al, 1
0x18009219a  jz      short loc_18009219F
0x18009219c  mov     al, r12b
0x18009219f  test    al, al
0x1800921a1  jz      short loc_1800921E3
0x1800921a3  mov     ebx, r12d
0x1800921a6  mov     [rsp+78h+hr], ebx
0x1800921aa  mov     eax, 0Dh
0x1800921af  mov     [rdi], ax
0x1800921b2  mov     rsi, [r15+0A10h]
0x1800921b9  test    rsi, rsi
0x1800921bc  jz      short loc_1800921D9
0x1800921be  mov     this, [rsi+60h]
0x1800921c2  test    this, this
0x1800921c5  jz      short loc_1800921D3
0x1800921c7  mov     rax, [this]
0x1800921ca  mov     rax, [rax+8]
0x1800921ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800921d3  mov     rax, [rsi+60h]
0x1800921d7  jmp     short loc_180092218
0x1800921d9  mov     this, r15; this
0x1800921dc  call    ?GetDeclHandler@Reader@@QEAAPEAUISAXDeclHandler@@XZ; Reader::GetDeclHandler(void)
0x1800921e1  jmp     short loc_180092218
0x1800921e3  cmp     ebx, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::lexicalHandler ...
0x1800921e9  jnz     short loc_180092221
0x1800921eb  mov     pvarValue, r14; Size
0x1800921ee  mov     pwhName, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1800921f5  mov     this, rsi; Buf1
0x1800921f8  call    memcmp_0
0x1800921fd  test    eax, eax
0x1800921ff  jnz     short loc_180092221
0x180092201  mov     ebx, r12d
0x180092204  mov     [rsp+78h+hr], ebx
0x180092208  mov     eax, 0Dh
0x18009220d  mov     [rdi], ax
0x180092210  mov     this, r15; this
0x180092213  call    ?GetLexicalHandler@Reader@@QEAAPEAUISAXLexicalHandler@@XZ; Reader::GetLexicalHandler(void)
0x180092218  mov     [rdi+8], rax
0x18009221c  jmp     loc_18009235B
0x180092221  cmp     ebx, cs:?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemaDeclarationHandler ...
0x180092227  jnz     short loc_180092282
0x180092229  movsxd  pvarValue, ebx
0x18009222c  add     pvarValue, pvarValue; Size
0x18009222f  mov     pwhName, cs:?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x180092236  mov     this, rsi; Buf1
0x180092239  call    memcmp_0
0x18009223e  test    eax, eax
0x180092240  jnz     short loc_180092282
0x180092242  mov     ebx, r12d
0x180092245  mov     [rsp+78h+hr], ebx
0x180092249  mov     eax, 0Dh
0x18009224e  mov     [rdi], ax
0x180092251  mov     rsi, [r15+0A10h]
0x180092258  test    rsi, rsi
0x18009225b  jz      loc_1800922E2
0x180092261  mov     this, [rsi+80h]
0x180092268  test    this, this
0x18009226b  jz      short loc_180092279
0x18009226d  mov     rax, [this]
0x180092270  mov     rax, [rax+8]
0x180092274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092279  mov     rax, [rsi+80h]
0x180092280  jmp     short loc_180092218
0x180092282  cmp     ebx, cs:?schemas@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemas ...
0x180092288  jnz     short loc_1800922E8
0x18009228a  movsxd  pvarValue, ebx
0x18009228d  add     pvarValue, pvarValue; Size
0x180092290  mov     pwhName, cs:?schemas@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x180092297  mov     this, rsi; Buf1
0x18009229a  call    memcmp_0
0x18009229f  test    eax, eax
0x1800922a1  jnz     short loc_1800922E8
0x1800922a3  mov     ebx, r12d
0x1800922a6  mov     [rsp+78h+hr], ebx
0x1800922aa  mov     eax, 9
0x1800922af  mov     [rdi], ax
0x1800922b2  mov     rsi, [r15+0A10h]
0x1800922b9  test    rsi, rsi
0x1800922bc  jz      short loc_1800922E2
0x1800922be  mov     this, [rsi+88h]
0x1800922c5  test    this, this
0x1800922c8  jz      short loc_1800922D6
0x1800922ca  mov     rax, [this]
0x1800922cd  mov     rax, [rax+8]
0x1800922d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800922d6  mov     rax, [rsi+88h]
0x1800922dd  jmp     loc_180092218
0x1800922e2  mov     [rdi+8], r12
0x1800922e6  jmp     short loc_18009235B
0x1800922e8  cmp     ebx, cs:?domNode@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::domNode ...
0x1800922ee  jnz     short loc_180092314
0x1800922f0  movsxd  pvarValue, ebx
0x1800922f3  add     pvarValue, pvarValue; Size
0x1800922f6  mov     pwhName, cs:?domNode@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1800922fd  mov     this, rsi; Buf1
0x180092300  call    memcmp_0
0x180092305  test    eax, eax
0x180092307  jnz     short loc_180092314
0x180092309  mov     ebx, 80004005h
0x18009230e  mov     [rsp+78h+hr], ebx
0x180092312  jmp     short loc_18009235B
0x180092314  cmp     ebx, cs:?inputSource@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::inputSource ...
0x18009231a  jnz     short loc_180092347
0x18009231c  movsxd  pvarValue, ebx
0x18009231f  add     pvarValue, pvarValue; Size
0x180092322  mov     pwhName, cs:?inputSource@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x180092329  mov     this, rsi; Buf1
0x18009232c  call    memcmp_0
0x180092331  test    eax, eax
0x180092333  jnz     short loc_180092347
0x180092335  lea     pwhName, [r15+0A18h]; pvargSrc
0x18009233c  mov     this, rdi; pvargDest
0x18009233f  call    cs:__imp_VariantCopy
0x180092345  jmp     short loc_180092355
0x180092347  mov     pvarValue, rdi; pvarValue
0x18009234a  mov     pwhName, rsi; pwhName
0x18009234d  mov     this, r15; this
0x180092350  call    ?getProperty@Reader@@UEAAJPEBGPEAUtagVARIANT@@@Z; Reader::getProperty(ushort const *,tagVARIANT *)
0x180092355  mov     [rsp+78h+hr], eax
0x180092359  mov     ebx, eax
0x18009235b  jmp     short loc_180092394
0x18009235d  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180092362  mov     ecx, cs:_tls_index
0x180092368  mov     rax, gs:58h
0x180092371  mov     edx, 8
0x180092376  mov     rax, [rax+this*8]
0x18009237a  mov     this, [rax+pwhName]
0x18009237e  mov     this, [this+8]
0x180092382  mov     rax, [this]
0x180092385  mov     rax, [rax+68h]
0x180092389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009238e  mov     ebx, eax
0x180092390  mov     [rsp+78h+hr], eax
0x180092394  mov     eax, ebx
0x180092396  add     rsp, 48h
0x18009239a  pop     r15
0x18009239c  pop     r14
0x18009239e  pop     r12
0x1800923a0  pop     rdi
0x1800923a1  pop     rsi
0x1800923a2  pop     rbx
0x1800923a3  retn
0x18017d471  push    rbp
0x18017d473  sub     rsp, 20h
0x18017d477  mov     rbp, rdx
0x18017d47a  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x18017d47f  nop
0x18017d480  add     rsp, 20h
0x18017d484  pop     rbp
0x18017d485  retn
```
