# SAXReader::putProperty(ushort const *,tagVARIANT)

- ea: `0x100ecbd0`
- end: `0x100ecef3`
- name: `?putProperty@SAXReader@@UAGJPBGUtagVARIANT@@@Z`
- size: `803`
- prototype: `HRESULT __stdcall(SAXReader *this, const wchar_t *pwhName, tagVARIANT varValue)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callees

- `0x1003fba3`
- `0x1004fc3e`
- `0x1005064c`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x100eb59a`
- `0x100ecbd0`
- `0x10128ed1`
- `0x101299f3`
- `0x101689df`
- `0x10168a1f`
- `0x10169a80`
- `0x101711a8`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x100ece1e`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100ece1e`

## pseudocode

```c
HRESULT __stdcall SAXReader::putProperty(SAXReader *this, const wchar_t *pwhName, tagVARIANT varValue)
{
  TLSDATA *v4; // eax
  HRESULT SAXSchemaProxy; // edi
  TLSDATA *v6; // esi
  size_t v7; // eax
  ISAXDeclHandler *v8; // eax
  ISAXLexicalHandler *v9; // ebx
  SAXSchemaProxy *p; // ecx
  DTSReader *v11; // ecx
  _reference<IMXSchemaDeclHandler> *p_pDeclHandler; // ecx
  DTSReader *v13; // ecx
  IMXSchemaDeclHandler *v14; // edx
  SAXReader *v15; // ecx
  SAXSchemaProxy *v16; // esi
  bool v17; // al
  HRESULT v18; // eax
  const struct _GUID *v19; // [esp+0h] [ebp-44h]
  int v20; // [esp+4h] [ebp-40h]
  EnsureTls _EnsureTls; // [esp+14h] [ebp-30h] BYREF
  SchemaCache *pSchemaCache; // [esp+18h] [ebp-2Ch]
  IMXSchemaDeclHandler *pSchemaDeclHandler; // [esp+1Ch] [ebp-28h]
  ISAXLexicalHandler *pLexicalHandler; // [esp+20h] [ebp-24h]
  ISAXDeclHandler *pDeclHandler; // [esp+24h] [ebp-20h]
  HRESULT hr; // [esp+28h] [ebp-1Ch]
  CPPEH_RECORD ms_exc; // [esp+2Ch] [ebp-18h]

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( !_EnsureTls._tlsdata )
    return -2147467259;
  v4 = 0;
  SAXSchemaProxy = 0;
  pDeclHandler = 0;
  pLexicalHandler = 0;
  pSchemaDeclHandler = 0;
  pSchemaCache = 0;
  ms_exc.registration.TryLevel = 0;
  if ( pwhName )
    v4 = (TLSDATA *)xstrlenw(pwhName, 0x7FFFFFFFu);
  v6 = v4;
  _EnsureTls._tlsdata = v4;
  v7 = 2 * (_DWORD)v4;
  if ( _EnsureTls._tlsdata == (TLSDATA *)CodeStringPtr::declarationHandler.n )
  {
    if ( !memcmp(pwhName, CodeStringPtr::declarationHandler.pwh, v7) )
    {
      v8 = (ISAXDeclHandler *)Variant::QIForIID(&varValue, &IID_ISAXDeclHandler);
      v9 = (ISAXLexicalHandler *)v8;
      pDeclHandler = v8;
      p = this->_pSchemaProxy._p;
      if ( p )
        assign(&p->_pDeclHandler._p, v8);
      else
        Reader::SetDeclHandler(this, v8);
      v11 = this->_pDtsReader._p;
      if ( !v11 )
        goto LABEL_45;
      p_pDeclHandler = (_reference<IMXSchemaDeclHandler> *)&v11->_pDeclHandler;
      goto LABEL_17;
    }
    v7 = 2 * (_DWORD)v6;
  }
  if ( v6 != (TLSDATA *)CodeStringPtr::lexicalHandler.n || memcmp(pwhName, CodeStringPtr::lexicalHandler.pwh, v7) )
  {
    if ( v6 == (TLSDATA *)CodeStringPtr::schemaDeclarationHandler.n
      && !memcmp(pwhName, CodeStringPtr::schemaDeclarationHandler.pwh, 2 * (_DWORD)v6) )
    {
      if ( !this->_pSchemaProxy._p )
      {
        SAXSchemaProxy = SAXReader::CreateSAXSchemaProxy(this, &this->_pSchemaProxy._p);
        hr = SAXSchemaProxy;
        if ( SAXSchemaProxy < 0 )
          goto LABEL_45;
      }
      v14 = (IMXSchemaDeclHandler *)Variant::QIForIID(&varValue, &IID_IMXSchemaDeclHandler);
      pSchemaDeclHandler = v14;
      p_pDeclHandler = &this->_pSchemaProxy._p->_pSchemaDeclHandler;
      goto LABEL_23;
    }
    if ( v6 == (TLSDATA *)CodeStringPtr::schemas.n && !memcmp(pwhName, CodeStringPtr::schemas.pwh, 2 * (_DWORD)v6) )
    {
      v15 = this;
      if ( !this->_fBusy )
      {
        if ( this->_pSchemaProxy._p
          || (SAXSchemaProxy = SAXReader::CreateSAXSchemaProxy(this, &this->_pSchemaProxy._p),
              hr = SAXSchemaProxy,
              SAXSchemaProxy >= 0) )
        {
          pSchemaCache = (SchemaCache *)ObjectFromVariant((const _GUID *)v15, (HRESULT)v15, v19, v20);
          v16 = this->_pSchemaProxy._p;
          assign(&v16->_pSchemaCache._p, pSchemaCache);
          v17 = v16->_fValidation && (v16->_pSchemaCache._p || v16->_fUseInlineSchema || v16->_fUseSchemaLocation);
          v16->_fDoValidation = v17;
        }
        goto LABEL_45;
      }
    }
    else if ( v6 != (TLSDATA *)CodeStringPtr::domNode.n || memcmp(pwhName, CodeStringPtr::domNode.pwh, 2 * (_DWORD)v6) )
    {
      if ( v6 == (TLSDATA *)CodeStringPtr::inputSource.n
        && !memcmp(pwhName, CodeStringPtr::inputSource.pwh, 2 * (_DWORD)v6) )
      {
        v18 = VariantCopy(&this->_varInput, &varValue);
      }
      else
      {
        v18 = Reader::putProperty(this, pwhName, varValue);
      }
      SAXSchemaProxy = v18;
      goto LABEL_44;
    }
    SAXSchemaProxy = -2147467259;
LABEL_44:
    hr = SAXSchemaProxy;
    goto LABEL_45;
  }
  v9 = (ISAXLexicalHandler *)Variant::QIForIID(&varValue, &IID_ISAXLexicalHandler);
  pLexicalHandler = v9;
  Reader::SetLexicalHandler(this, v9);
  v13 = this->_pDtsReader._p;
  if ( v13 )
  {
    p_pDeclHandler = (_reference<IMXSchemaDeclHandler> *)&v13->_pLexicalHandler;
LABEL_17:
    v14 = (IMXSchemaDeclHandler *)v9;
LABEL_23:
    assign(&p_pDeclHandler->_p, v14);
  }
LABEL_45:
  ms_exc.registration.TryLevel = -2;
  if ( pDeclHandler )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISAXDeclHandler *))pDeclHandler->Release)(
      pDeclHandler->Release,
      pDeclHandler);
  if ( pLexicalHandler )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISAXLexicalHandler *))pLexicalHandler->Release)(
      pLexicalHandler->Release,
      pLexicalHandler);
  if ( pSchemaDeclHandler )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IDispatch *), IMXSchemaDeclHandler *))pSchemaDeclHandler->Release)(
      pSchemaDeclHandler->Release,
      pSchemaDeclHandler);
  if ( pSchemaCache )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), SchemaCache *))pSchemaCache->Release)(
      pSchemaCache->Release,
      pSchemaCache);
  return SAXSchemaProxy;
}

```

## disassembly

```asm
0x100ecbd0  push    24h
0x100ecbd2  push    offset stru_10179AA8
0x100ecbd7  call    __SEH_prolog4
0x100ecbdc  lea     ecx, [ebp+_EnsureTls]; this
0x100ecbdf  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100ecbe4  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100ecbe8  jnz     short loc_100ECBF4
0x100ecbea  mov     eax, 80004005h
0x100ecbef  jmp     loc_100ECEE1
0x100ecbf4  xor     eax, eax
0x100ecbf6  mov     edi, eax
0x100ecbf8  mov     [ebp+pDeclHandler], eax
0x100ecbfb  mov     [ebp+pLexicalHandler], eax
0x100ecbfe  mov     [ebp+pSchemaDeclHandler], eax
0x100ecc01  mov     [ebp+pSchemaCache], eax
0x100ecc04  mov     [ebp+ms_exc.registration.TryLevel], eax
0x100ecc07  mov     ebx, [ebp+pwhName]
0x100ecc0a  mov     [ebp+var_34], ebx
0x100ecc0d  test    ebx, ebx
0x100ecc0f  jz      short loc_100ECC1D
0x100ecc11  mov     edx, 7FFFFFFFh; cchMax
0x100ecc16  mov     ecx, ebx; psz
0x100ecc18  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x100ecc1d  mov     esi, eax
0x100ecc1f  mov     [ebp+_EnsureTls._tlsdata], esi
0x100ecc22  lea     eax, [esi+esi]
0x100ecc25  cmp     esi, ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::declarationHandler ...
0x100ecc2b  jnz     short loc_100ECC8A
0x100ecc2d  push    eax; Size
0x100ecc2e  push    ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecc34  push    ebx; Buf1
0x100ecc35  call    _memcmp
0x100ecc3a  add     esp, 0Ch
0x100ecc3d  test    eax, eax
0x100ecc3f  jnz     short loc_100ECC87
0x100ecc41  mov     edx, offset _IID_ISAXDeclHandler; piid
0x100ecc46  lea     ecx, [ebp+varValue]; pVar
0x100ecc49  call    ?QIForIID@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@PBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100ecc4e  mov     ebx, eax
0x100ecc50  mov     [ebp+pDeclHandler], ebx
0x100ecc53  mov     esi, [ebp+this]
0x100ecc56  mov     ecx, [esi+578h]
0x100ecc5c  test    ecx, ecx
0x100ecc5e  jz      short loc_100ECC6C
0x100ecc60  add     ecx, 30h ; '0'; ppref
0x100ecc63  mov     edx, ebx; pref
0x100ecc65  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100ecc6a  jmp     short loc_100ECC74
0x100ecc6c  push    ebx; pDeclHandler
0x100ecc6d  mov     ecx, esi; this
0x100ecc6f  call    ?SetDeclHandler@Reader@@QAEXPAUISAXDeclHandler@@@Z; Reader::SetDeclHandler(ISAXDeclHandler *)
0x100ecc74  mov     ecx, [esi+574h]
0x100ecc7a  test    ecx, ecx
0x100ecc7c  jz      loc_100ECE7C
0x100ecc82  add     ecx, 34h ; '4'
0x100ecc85  jmp     short loc_100ECCD4
0x100ecc87  lea     eax, [esi+esi]
0x100ecc8a  cmp     esi, ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::lexicalHandler ...
0x100ecc90  jnz     short loc_100ECCD8
0x100ecc92  push    eax; Size
0x100ecc93  push    ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecc99  push    ebx; Buf1
0x100ecc9a  call    _memcmp
0x100ecc9f  add     esp, 0Ch
0x100ecca2  test    eax, eax
0x100ecca4  jnz     short loc_100ECCD8
0x100ecca6  mov     edx, offset _IID_ISAXLexicalHandler; piid
0x100eccab  lea     ecx, [ebp+varValue]; pVar
0x100eccae  call    ?QIForIID@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@PBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100eccb3  mov     ebx, eax
0x100eccb5  mov     [ebp+pLexicalHandler], ebx
0x100eccb8  push    ebx; pLexicalHandler
0x100eccb9  mov     esi, [ebp+this]
0x100eccbc  mov     ecx, esi; this
0x100eccbe  call    ?SetLexicalHandler@Reader@@QAEXPAUISAXLexicalHandler@@@Z; Reader::SetLexicalHandler(ISAXLexicalHandler *)
0x100eccc3  mov     ecx, [esi+574h]
0x100eccc9  test    ecx, ecx
0x100ecccb  jz      loc_100ECE7C
0x100eccd1  add     ecx, 38h ; '8'
0x100eccd4  mov     edx, ebx
0x100eccd6  jmp     short loc_100ECD2E
0x100eccd8  cmp     esi, ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemaDeclarationHandler ...
0x100eccde  jnz     short loc_100ECD38
0x100ecce0  lea     eax, [esi+esi]
0x100ecce3  push    eax; Size
0x100ecce4  push    ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100eccea  push    ebx; Buf1
0x100ecceb  call    _memcmp
0x100eccf0  add     esp, 0Ch
0x100eccf3  test    eax, eax
0x100eccf5  jnz     short loc_100ECD38
0x100eccf7  mov     ecx, [ebp+this]; this
0x100eccfa  lea     esi, [ecx+578h]
0x100ecd00  cmp     [esi], eax
0x100ecd02  jnz     short loc_100ECD17
0x100ecd04  push    esi; ppSchemaProxy
0x100ecd05  call    ?CreateSAXSchemaProxy@SAXReader@@IAEJPAPAVSAXSchemaProxy@@@Z; SAXReader::CreateSAXSchemaProxy(SAXSchemaProxy * *)
0x100ecd0a  mov     edi, eax
0x100ecd0c  mov     [ebp+hr], edi
0x100ecd0f  test    edi, edi
0x100ecd11  js      loc_100ECE7C
0x100ecd17  mov     edx, offset _IID_IMXSchemaDeclHandler; piid
0x100ecd1c  lea     ecx, [ebp+varValue]; pVar
0x100ecd1f  call    ?QIForIID@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@PBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100ecd24  mov     edx, eax; pref
0x100ecd26  mov     [ebp+pSchemaDeclHandler], edx
0x100ecd29  mov     ecx, [esi]
0x100ecd2b  add     ecx, 44h ; 'D'; ppref
0x100ecd2e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100ecd33  jmp     loc_100ECE7C
0x100ecd38  cmp     esi, ?schemas@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemas ...
0x100ecd3e  jnz     loc_100ECDCF
0x100ecd44  lea     eax, [esi+esi]
0x100ecd47  push    eax; Size
0x100ecd48  push    ?schemas@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecd4e  push    ebx; Buf1
0x100ecd4f  call    _memcmp
0x100ecd54  add     esp, 0Ch
0x100ecd57  test    eax, eax
0x100ecd59  jnz     short loc_100ECDCF
0x100ecd5b  mov     ecx, [ebp+this]; this
0x100ecd5e  cmp     [ecx+570h], al
0x100ecd64  jz      short loc_100ECD70
0x100ecd66  mov     edi, 80004005h
0x100ecd6b  jmp     loc_100ECE79
0x100ecd70  lea     esi, [ecx+578h]
0x100ecd76  cmp     dword ptr [esi], 0
0x100ecd79  jnz     short loc_100ECD8E
0x100ecd7b  push    esi; ppSchemaProxy
0x100ecd7c  call    ?CreateSAXSchemaProxy@SAXReader@@IAEJPAPAVSAXSchemaProxy@@@Z; SAXReader::CreateSAXSchemaProxy(SAXSchemaProxy * *)
0x100ecd81  mov     edi, eax
0x100ecd83  mov     [ebp+hr], edi
0x100ecd86  test    edi, edi
0x100ecd88  js      loc_100ECE7C
0x100ecd8e  push    ecx; iidExternal
0x100ecd8f  push    ecx; iidInternal
0x100ecd90  lea     ecx, [ebp+varValue]; pVar
0x100ecd93  call    ?ObjectFromVariant@@YGPAXPAUtagVARIANT@@ABU_GUID@@1J@Z; ObjectFromVariant(tagVARIANT *,_GUID const &,_GUID const &,long)
0x100ecd98  mov     ecx, eax
0x100ecd9a  mov     [ebp+pSchemaCache], ecx
0x100ecd9d  mov     esi, [esi]
0x100ecd9f  mov     edx, ecx; pref
0x100ecda1  lea     ecx, [esi+48h]; ppref
0x100ecda4  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100ecda9  cmp     byte ptr [esi+3Dh], 0
0x100ecdad  jz      short loc_100ECDC5
0x100ecdaf  cmp     dword ptr [esi+48h], 0
0x100ecdb3  jnz     short loc_100ECDC1
0x100ecdb5  cmp     byte ptr [esi+40h], 0
0x100ecdb9  jnz     short loc_100ECDC1
0x100ecdbb  cmp     byte ptr [esi+41h], 0
0x100ecdbf  jz      short loc_100ECDC5
0x100ecdc1  mov     al, 1
0x100ecdc3  jmp     short loc_100ECDC7
0x100ecdc5  xor     al, al
0x100ecdc7  mov     [esi+3Ch], al
0x100ecdca  jmp     loc_100ECE7C
0x100ecdcf  cmp     esi, ?domNode@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::domNode ...
0x100ecdd5  jnz     short loc_100ECDF2
0x100ecdd7  lea     eax, [esi+esi]
0x100ecdda  push    eax; Size
0x100ecddb  push    ?domNode@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecde1  push    ebx; Buf1
0x100ecde2  call    _memcmp
0x100ecde7  add     esp, 0Ch
0x100ecdea  test    eax, eax
0x100ecdec  jz      loc_100ECD66
0x100ecdf2  cmp     esi, ?inputSource@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::inputSource ...
0x100ecdf8  jnz     short loc_100ECE26
0x100ecdfa  lea     eax, [esi+esi]
0x100ecdfd  push    eax; Size
0x100ecdfe  push    ?inputSource@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ece04  push    ebx; Buf1
0x100ece05  call    _memcmp
0x100ece0a  add     esp, 0Ch
0x100ece0d  test    eax, eax
0x100ece0f  jnz     short loc_100ECE26
0x100ece11  lea     eax, [ebp+varValue]
0x100ece14  push    eax; pvargSrc
0x100ece15  mov     eax, [ebp+this]
0x100ece18  add     eax, 580h
0x100ece1d  push    eax; pvargDest
0x100ece1e  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100ece24  jmp     short loc_100ECE77
0x100ece26  sub     esp, 10h
0x100ece29  lea     esi, [ebp+varValue]
0x100ece2c  mov     edi, esp
0x100ece2e  movsd
0x100ece2f  movsd
0x100ece30  movsd
0x100ece31  movsd
0x100ece32  push    ebx; pwhName
0x100ece33  push    [ebp+this]; this
0x100ece36  call    ?putProperty@Reader@@UAGJPBGUtagVARIANT@@@Z; Reader::putProperty(ushort const *,tagVARIANT)
0x100ece3b  jmp     short loc_100ECE77
0x100ece3d  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100ece40  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100ece45  retn
0x100ece46  mov     esp, [ebp+ms_exc.old_esp]
0x100ece49  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100ece4e  mov     ecx, __tls_index
0x100ece54  mov     eax, large fs:2Ch
0x100ece5a  mov     eax, [eax+ecx*4]
0x100ece5d  mov     eax, [eax+4]
0x100ece63  mov     edi, [eax+8]
0x100ece66  mov     eax, [edi]
0x100ece68  mov     esi, [eax+34h]
0x100ece6b  mov     ecx, esi; this
0x100ece6d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ece73  mov     ecx, edi
0x100ece75  call    esi
0x100ece77  mov     edi, eax
0x100ece79  mov     [ebp+hr], edi
0x100ece7c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100ece83  mov     ecx, [ebp+pDeclHandler]
0x100ece86  test    ecx, ecx
0x100ece88  jz      short loc_100ECE9A
0x100ece8a  mov     eax, [ecx]
0x100ece8c  push    ecx
0x100ece8d  mov     esi, [eax+8]
0x100ece90  mov     ecx, esi; this
0x100ece92  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ece98  call    esi
0x100ece9a  mov     ecx, [ebp+pLexicalHandler]
0x100ece9d  test    ecx, ecx
0x100ece9f  jz      short loc_100ECEB1
0x100ecea1  mov     eax, [ecx]
0x100ecea3  push    ecx
0x100ecea4  mov     esi, [eax+8]
0x100ecea7  mov     ecx, esi; this
0x100ecea9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100eceaf  call    esi
0x100eceb1  mov     edx, [ebp+pSchemaDeclHandler]
0x100eceb4  test    edx, edx
0x100eceb6  jz      short loc_100ECEC8
0x100eceb8  mov     eax, [edx]
0x100eceba  push    edx
0x100ecebb  mov     esi, [eax+8]
0x100ecebe  mov     ecx, esi; this
0x100ecec0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ecec6  call    esi
0x100ecec8  mov     ecx, [ebp+pSchemaCache]
0x100ececb  test    ecx, ecx
0x100ececd  jz      short loc_100ECEDF
0x100ececf  mov     eax, [ecx]
0x100eced1  push    ecx
0x100eced2  mov     esi, [eax+8]
0x100eced5  mov     ecx, esi; this
0x100eced7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ecedd  call    esi
0x100ecedf  mov     eax, edi
0x100ecee1  mov     ecx, [ebp+ms_exc.registration.Next]
0x100ecee4  mov     large fs:0, ecx
0x100eceeb  pop     ecx
0x100eceec  pop     edi
0x100eceed  pop     esi
0x100eceee  pop     ebx
0x100eceef  leave
0x100ecef0  retn    18h
```
