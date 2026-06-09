# SAXReader::getProperty(ushort const *,tagVARIANT *)

- ea: `0x180092740`
- end: `0x180092a51`
- name: `?getProperty@SAXReader@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `785`
- prototype: `HRESULT __fastcall(SAXReader *this, const wchar_t *pwhName, tagVARIANT *pvarValue)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180082690`
- `0x180092740`
- `0x18009fefc`
- `0x1800a3c08`
- `0x18012e530`
- `0x180173de0`
- `0x180173e34`
- `0x18017c1cc`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18009278c`
- `OLEAUT32!__imp_VariantInit` at `0x18009278c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800929e5`
- `OLEAUT32!__imp_VariantCopy` at `0x1800929e5`

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
  ISAXDeclHandler *DeclHandler; // rax
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
        DeclHandler = v14->_pDeclHandler._p;
      }
      else
      {
        DeclHandler = Reader::GetDeclHandler(this);
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
            DeclHandler = (ISAXDeclHandler *)v17->_pSchemaDeclHandler._p;
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
            DeclHandler = (ISAXDeclHandler *)v19->_pSchemaCache._p;
            goto LABEL_26;
          }
        }
        pvarValue->llVal = 0;
        return Property;
      }
      Property = 0;
      pvarValue->vt = 13;
      DeclHandler = (ISAXDeclHandler *)Reader::GetLexicalHandler(this);
    }
LABEL_26:
    pvarValue->llVal = (__int64)DeclHandler;
  }
  return Property;
}

```

## disassembly

```asm
0x180092740  push    rbx
0x180092742  push    rsi
0x180092743  push    rdi
0x180092744  push    r12
0x180092746  push    r14
0x180092748  push    r15
0x18009274a  sub     rsp, 48h
0x18009274e  mov     rdi, pvarValue
0x180092751  mov     rsi, pwhName
0x180092754  mov     r15, this
0x180092757  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18009275e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092763  xor     r12d, r12d
0x180092766  test    rax, rax
0x180092769  jnz     short loc_180092775
0x18009276b  mov     eax, 80004005h
0x180092770  jmp     loc_180092A42
0x180092775  test    rdi, rdi
0x180092778  jnz     short loc_180092784
0x18009277a  mov     eax, 80070057h
0x18009277f  jmp     loc_180092A42
0x180092784  mov     ebx, 80070057h
0x180092789  mov     this, rdi; pvarg
0x18009278c  call    cs:__imp_VariantInit
0x180092793  nop     dword ptr [rax+rax+00h]
0x180092798  nop
0x180092799  mov     this, [r15+0A08h]; this
0x1800927a0  test    this, this
0x1800927a3  jz      short loc_1800927B6
0x1800927a5  mov     pvarValue, rdi; pvarValue
0x1800927a8  mov     pwhName, rsi; pwhName
0x1800927ab  call    ?getProperty@DTSReader@@QEAAJPEBGPEAUtagVARIANT@@@Z; DTSReader::getProperty(ushort const *,tagVARIANT *)
0x1800927b0  mov     ebx, eax
0x1800927b2  mov     [rsp+78h+hr], eax
0x1800927b6  cmp     ebx, 80070057h
0x1800927bc  jnz     loc_180092A07
0x1800927c2  mov     [rsp+78h+name.pwh], r12
0x1800927c7  mov     [rsp+78h+name.n], r12d
0x1800927cc  mov     [rsp+78h+name.pwh], rsi
0x1800927d1  test    rsi, rsi
0x1800927d4  jz      short loc_180092815
0x1800927d6  mov     rax, rsi
0x1800927d9  mov     [rsp+78h+var_50], rax
0x1800927de  mov     rbx, r12
0x1800927e1  mov     [rsp+78h+arg_18], rbx
0x1800927e9  mov     this, r12
0x1800927ec  cmp     this, 7FFFFFFFh
0x1800927f3  jnb     short loc_180092818
0x1800927f5  cmp     [rax], r12w
0x1800927f9  jz      short loc_180092818
0x1800927fb  add     rax, 2
0x1800927ff  mov     [rsp+78h+var_50], rax
0x180092804  lea     rbx, [this+1]
0x180092808  mov     [rsp+78h+arg_18], rbx
0x180092810  mov     this, rbx
0x180092813  jmp     short loc_1800927EC
0x180092815  mov     ebx, r12d
0x180092818  mov     [rsp+78h+name.n], ebx
0x18009281c  movsxd  r14, ebx
0x18009281f  add     r14, r14
0x180092822  cmp     ebx, cs:?declarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::declarationHandler ...
0x180092828  jnz     short loc_180092842
0x18009282a  mov     pvarValue, r14; Size
0x18009282d  mov     pwhName, cs:?declarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x180092834  mov     this, rsi; Buf1
0x180092837  call    memcmp_0
0x18009283c  test    eax, eax
0x18009283e  mov     al, 1
0x180092840  jz      short loc_180092845
0x180092842  mov     al, r12b
0x180092845  test    al, al
0x180092847  jz      short loc_180092889
0x180092849  mov     ebx, r12d
0x18009284c  mov     [rsp+78h+hr], ebx
0x180092850  mov     eax, 0Dh
0x180092855  mov     [rdi], ax
0x180092858  mov     rsi, [r15+0A10h]
0x18009285f  test    rsi, rsi
0x180092862  jz      short loc_18009287F
0x180092864  mov     this, [rsi+60h]
0x180092868  test    this, this
0x18009286b  jz      short loc_180092879
0x18009286d  mov     rax, [this]
0x180092870  mov     rax, [rax+8]
0x180092874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092879  mov     rax, [rsi+60h]
0x18009287d  jmp     short loc_1800928BE
0x18009287f  mov     this, r15; this
0x180092882  call    ?GetDeclHandler@Reader@@QEAAPEAUISAXDeclHandler@@XZ; Reader::GetDeclHandler(void)
0x180092887  jmp     short loc_1800928BE
0x180092889  cmp     ebx, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::lexicalHandler ...
0x18009288f  jnz     short loc_1800928C7
0x180092891  mov     pvarValue, r14; Size
0x180092894  mov     pwhName, cs:?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x18009289b  mov     this, rsi; Buf1
0x18009289e  call    memcmp_0
0x1800928a3  test    eax, eax
0x1800928a5  jnz     short loc_1800928C7
0x1800928a7  mov     ebx, r12d
0x1800928aa  mov     [rsp+78h+hr], ebx
0x1800928ae  mov     eax, 0Dh
0x1800928b3  mov     [rdi], ax
0x1800928b6  mov     this, r15; this
0x1800928b9  call    ?GetLexicalHandler@Reader@@QEAAPEAUISAXLexicalHandler@@XZ; Reader::GetLexicalHandler(void)
0x1800928be  mov     [rdi+8], rax
0x1800928c2  jmp     loc_180092A07
0x1800928c7  cmp     ebx, cs:?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemaDeclarationHandler ...
0x1800928cd  jnz     short loc_180092928
0x1800928cf  movsxd  pvarValue, ebx
0x1800928d2  add     pvarValue, pvarValue; Size
0x1800928d5  mov     pwhName, cs:?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1800928dc  mov     this, rsi; Buf1
0x1800928df  call    memcmp_0
0x1800928e4  test    eax, eax
0x1800928e6  jnz     short loc_180092928
0x1800928e8  mov     ebx, r12d
0x1800928eb  mov     [rsp+78h+hr], ebx
0x1800928ef  mov     eax, 0Dh
0x1800928f4  mov     [rdi], ax
0x1800928f7  mov     rsi, [r15+0A10h]
0x1800928fe  test    rsi, rsi
0x180092901  jz      loc_180092988
0x180092907  mov     this, [rsi+80h]
0x18009290e  test    this, this
0x180092911  jz      short loc_18009291F
0x180092913  mov     rax, [this]
0x180092916  mov     rax, [rax+8]
0x18009291a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009291f  mov     rax, [rsi+80h]
0x180092926  jmp     short loc_1800928BE
0x180092928  cmp     ebx, cs:?schemas@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemas ...
0x18009292e  jnz     short loc_18009298E
0x180092930  movsxd  pvarValue, ebx
0x180092933  add     pvarValue, pvarValue; Size
0x180092936  mov     pwhName, cs:?schemas@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x18009293d  mov     this, rsi; Buf1
0x180092940  call    memcmp_0
0x180092945  test    eax, eax
0x180092947  jnz     short loc_18009298E
0x180092949  mov     ebx, r12d
0x18009294c  mov     [rsp+78h+hr], ebx
0x180092950  mov     eax, 9
0x180092955  mov     [rdi], ax
0x180092958  mov     rsi, [r15+0A10h]
0x18009295f  test    rsi, rsi
0x180092962  jz      short loc_180092988
0x180092964  mov     this, [rsi+88h]
0x18009296b  test    this, this
0x18009296e  jz      short loc_18009297C
0x180092970  mov     rax, [this]
0x180092973  mov     rax, [rax+8]
0x180092977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009297c  mov     rax, [rsi+88h]
0x180092983  jmp     loc_1800928BE
0x180092988  mov     [rdi+8], r12
0x18009298c  jmp     short loc_180092A07
0x18009298e  cmp     ebx, cs:?domNode@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::domNode ...
0x180092994  jnz     short loc_1800929BA
0x180092996  movsxd  pvarValue, ebx
0x180092999  add     pvarValue, pvarValue; Size
0x18009299c  mov     pwhName, cs:?domNode@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1800929a3  mov     this, rsi; Buf1
0x1800929a6  call    memcmp_0
0x1800929ab  test    eax, eax
0x1800929ad  jnz     short loc_1800929BA
0x1800929af  mov     ebx, 80004005h
0x1800929b4  mov     [rsp+78h+hr], ebx
0x1800929b8  jmp     short loc_180092A07
0x1800929ba  cmp     ebx, cs:?inputSource@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::inputSource ...
0x1800929c0  jnz     short loc_1800929F3
0x1800929c2  movsxd  pvarValue, ebx
0x1800929c5  add     pvarValue, pvarValue; Size
0x1800929c8  mov     pwhName, cs:?inputSource@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x1800929cf  mov     this, rsi; Buf1
0x1800929d2  call    memcmp_0
0x1800929d7  test    eax, eax
0x1800929d9  jnz     short loc_1800929F3
0x1800929db  lea     pwhName, [r15+0A18h]; pvargSrc
0x1800929e2  mov     this, rdi; pvargDest
0x1800929e5  call    cs:__imp_VariantCopy
0x1800929ec  nop     dword ptr [rax+rax+00h]
0x1800929f1  jmp     short loc_180092A01
0x1800929f3  mov     pvarValue, rdi; pvarValue
0x1800929f6  mov     pwhName, rsi; pwhName
0x1800929f9  mov     this, r15; this
0x1800929fc  call    ?getProperty@Reader@@UEAAJPEBGPEAUtagVARIANT@@@Z; Reader::getProperty(ushort const *,tagVARIANT *)
0x180092a01  mov     [rsp+78h+hr], eax
0x180092a05  mov     ebx, eax
0x180092a07  jmp     short loc_180092A40
0x180092a09  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180092a0e  mov     ecx, cs:_tls_index
0x180092a14  mov     rax, gs:58h
0x180092a1d  mov     edx, 8
0x180092a22  mov     rax, [rax+this*8]
0x180092a26  mov     this, [rax+pwhName]
0x180092a2a  mov     this, [this+8]
0x180092a2e  mov     rax, [this]
0x180092a31  mov     rax, [rax+68h]
0x180092a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a3a  mov     ebx, eax
0x180092a3c  mov     [rsp+78h+hr], eax
0x180092a40  mov     eax, ebx
0x180092a42  add     rsp, 48h
0x180092a46  pop     r15
0x180092a48  pop     r14
0x180092a4a  pop     r12
0x180092a4c  pop     rdi
0x180092a4d  pop     rsi
0x180092a4e  pop     rbx
0x180092a4f  retn
0x180180faf  push    rbp
0x180180fb1  sub     rsp, 20h
0x180180fb5  mov     rbp, rdx
0x180180fb8  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x180180fbd  nop
0x180180fbe  add     rsp, 20h
0x180180fc2  pop     rbp
0x180180fc3  retn
```
