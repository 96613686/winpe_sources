# SAXReader::putProperty(ushort const *,tagVARIANT)

- ea: `0x100eccf0`
- end: `0x100ed013`
- name: `?putProperty@SAXReader@@UAGJPBGUtagVARIANT@@@Z`
- size: `803`
- prototype: `HRESULT __stdcall(SAXReader *this, const wchar_t *pwhName, tagVARIANT varValue)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callees

- `0x1003fb13`
- `0x1004fbae`
- `0x100505bc`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100eb6ba`
- `0x100eccf0`
- `0x10128fe1`
- `0x10129b03`
- `0x10168adf`
- `0x10168b1f`
- `0x10169b70`
- `0x10171298`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x100ecf3e`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100ecf3e`

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
0x100eccf0  push    24h
0x100eccf2  push    offset stru_10179B98
0x100eccf7  call    __SEH_prolog4
0x100eccfc  lea     ecx, [ebp+_EnsureTls]; this
0x100eccff  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100ecd04  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100ecd08  jnz     short loc_100ECD14
0x100ecd0a  mov     eax, 80004005h
0x100ecd0f  jmp     loc_100ED001
0x100ecd14  xor     eax, eax
0x100ecd16  mov     edi, eax
0x100ecd18  mov     [ebp+pDeclHandler], eax
0x100ecd1b  mov     [ebp+pLexicalHandler], eax
0x100ecd1e  mov     [ebp+pSchemaDeclHandler], eax
0x100ecd21  mov     [ebp+pSchemaCache], eax
0x100ecd24  mov     [ebp+ms_exc.registration.TryLevel], eax
0x100ecd27  mov     ebx, [ebp+pwhName]
0x100ecd2a  mov     [ebp+var_34], ebx
0x100ecd2d  test    ebx, ebx
0x100ecd2f  jz      short loc_100ECD3D
0x100ecd31  mov     edx, 7FFFFFFFh; cchMax
0x100ecd36  mov     ecx, ebx; psz
0x100ecd38  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x100ecd3d  mov     esi, eax
0x100ecd3f  mov     [ebp+_EnsureTls._tlsdata], esi
0x100ecd42  lea     eax, [esi+esi]
0x100ecd45  cmp     esi, ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::declarationHandler ...
0x100ecd4b  jnz     short loc_100ECDAA
0x100ecd4d  push    eax; Size
0x100ecd4e  push    ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecd54  push    ebx; Buf1
0x100ecd55  call    _memcmp
0x100ecd5a  add     esp, 0Ch
0x100ecd5d  test    eax, eax
0x100ecd5f  jnz     short loc_100ECDA7
0x100ecd61  mov     edx, offset _IID_ISAXDeclHandler; piid
0x100ecd66  lea     ecx, [ebp+varValue]; pVar
0x100ecd69  call    ?QIForIID@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@PBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100ecd6e  mov     ebx, eax
0x100ecd70  mov     [ebp+pDeclHandler], ebx
0x100ecd73  mov     esi, [ebp+this]
0x100ecd76  mov     ecx, [esi+578h]
0x100ecd7c  test    ecx, ecx
0x100ecd7e  jz      short loc_100ECD8C
0x100ecd80  add     ecx, 30h ; '0'; ppref
0x100ecd83  mov     edx, ebx; pref
0x100ecd85  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100ecd8a  jmp     short loc_100ECD94
0x100ecd8c  push    ebx; pDeclHandler
0x100ecd8d  mov     ecx, esi; this
0x100ecd8f  call    ?SetDeclHandler@Reader@@QAEXPAUISAXDeclHandler@@@Z; Reader::SetDeclHandler(ISAXDeclHandler *)
0x100ecd94  mov     ecx, [esi+574h]
0x100ecd9a  test    ecx, ecx
0x100ecd9c  jz      loc_100ECF9C
0x100ecda2  add     ecx, 34h ; '4'
0x100ecda5  jmp     short loc_100ECDF4
0x100ecda7  lea     eax, [esi+esi]
0x100ecdaa  cmp     esi, ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::lexicalHandler ...
0x100ecdb0  jnz     short loc_100ECDF8
0x100ecdb2  push    eax; Size
0x100ecdb3  push    ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecdb9  push    ebx; Buf1
0x100ecdba  call    _memcmp
0x100ecdbf  add     esp, 0Ch
0x100ecdc2  test    eax, eax
0x100ecdc4  jnz     short loc_100ECDF8
0x100ecdc6  mov     edx, offset _IID_ISAXLexicalHandler; piid
0x100ecdcb  lea     ecx, [ebp+varValue]; pVar
0x100ecdce  call    ?QIForIID@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@PBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100ecdd3  mov     ebx, eax
0x100ecdd5  mov     [ebp+pLexicalHandler], ebx
0x100ecdd8  push    ebx; pLexicalHandler
0x100ecdd9  mov     esi, [ebp+this]
0x100ecddc  mov     ecx, esi; this
0x100ecdde  call    ?SetLexicalHandler@Reader@@QAEXPAUISAXLexicalHandler@@@Z; Reader::SetLexicalHandler(ISAXLexicalHandler *)
0x100ecde3  mov     ecx, [esi+574h]
0x100ecde9  test    ecx, ecx
0x100ecdeb  jz      loc_100ECF9C
0x100ecdf1  add     ecx, 38h ; '8'
0x100ecdf4  mov     edx, ebx
0x100ecdf6  jmp     short loc_100ECE4E
0x100ecdf8  cmp     esi, ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemaDeclarationHandler ...
0x100ecdfe  jnz     short loc_100ECE58
0x100ece00  lea     eax, [esi+esi]
0x100ece03  push    eax; Size
0x100ece04  push    ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ece0a  push    ebx; Buf1
0x100ece0b  call    _memcmp
0x100ece10  add     esp, 0Ch
0x100ece13  test    eax, eax
0x100ece15  jnz     short loc_100ECE58
0x100ece17  mov     ecx, [ebp+this]; this
0x100ece1a  lea     esi, [ecx+578h]
0x100ece20  cmp     [esi], eax
0x100ece22  jnz     short loc_100ECE37
0x100ece24  push    esi; ppSchemaProxy
0x100ece25  call    ?CreateSAXSchemaProxy@SAXReader@@IAEJPAPAVSAXSchemaProxy@@@Z; SAXReader::CreateSAXSchemaProxy(SAXSchemaProxy * *)
0x100ece2a  mov     edi, eax
0x100ece2c  mov     [ebp+hr], edi
0x100ece2f  test    edi, edi
0x100ece31  js      loc_100ECF9C
0x100ece37  mov     edx, offset _IID_IMXSchemaDeclHandler; piid
0x100ece3c  lea     ecx, [ebp+varValue]; pVar
0x100ece3f  call    ?QIForIID@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@PBU_GUID@@@Z; Variant::QIForIID(tagVARIANT *,_GUID const *)
0x100ece44  mov     edx, eax; pref
0x100ece46  mov     [ebp+pSchemaDeclHandler], edx
0x100ece49  mov     ecx, [esi]
0x100ece4b  add     ecx, 44h ; 'D'; ppref
0x100ece4e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100ece53  jmp     loc_100ECF9C
0x100ece58  cmp     esi, ?schemas@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemas ...
0x100ece5e  jnz     loc_100ECEEF
0x100ece64  lea     eax, [esi+esi]
0x100ece67  push    eax; Size
0x100ece68  push    ?schemas@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ece6e  push    ebx; Buf1
0x100ece6f  call    _memcmp
0x100ece74  add     esp, 0Ch
0x100ece77  test    eax, eax
0x100ece79  jnz     short loc_100ECEEF
0x100ece7b  mov     ecx, [ebp+this]; this
0x100ece7e  cmp     [ecx+570h], al
0x100ece84  jz      short loc_100ECE90
0x100ece86  mov     edi, 80004005h
0x100ece8b  jmp     loc_100ECF99
0x100ece90  lea     esi, [ecx+578h]
0x100ece96  cmp     dword ptr [esi], 0
0x100ece99  jnz     short loc_100ECEAE
0x100ece9b  push    esi; ppSchemaProxy
0x100ece9c  call    ?CreateSAXSchemaProxy@SAXReader@@IAEJPAPAVSAXSchemaProxy@@@Z; SAXReader::CreateSAXSchemaProxy(SAXSchemaProxy * *)
0x100ecea1  mov     edi, eax
0x100ecea3  mov     [ebp+hr], edi
0x100ecea6  test    edi, edi
0x100ecea8  js      loc_100ECF9C
0x100eceae  push    ecx; iidExternal
0x100eceaf  push    ecx; iidInternal
0x100eceb0  lea     ecx, [ebp+varValue]; pVar
0x100eceb3  call    ?ObjectFromVariant@@YGPAXPAUtagVARIANT@@ABU_GUID@@1J@Z; ObjectFromVariant(tagVARIANT *,_GUID const &,_GUID const &,long)
0x100eceb8  mov     ecx, eax
0x100eceba  mov     [ebp+pSchemaCache], ecx
0x100ecebd  mov     esi, [esi]
0x100ecebf  mov     edx, ecx; pref
0x100ecec1  lea     ecx, [esi+48h]; ppref
0x100ecec4  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100ecec9  cmp     byte ptr [esi+3Dh], 0
0x100ececd  jz      short loc_100ECEE5
0x100ececf  cmp     dword ptr [esi+48h], 0
0x100eced3  jnz     short loc_100ECEE1
0x100eced5  cmp     byte ptr [esi+40h], 0
0x100eced9  jnz     short loc_100ECEE1
0x100ecedb  cmp     byte ptr [esi+41h], 0
0x100ecedf  jz      short loc_100ECEE5
0x100ecee1  mov     al, 1
0x100ecee3  jmp     short loc_100ECEE7
0x100ecee5  xor     al, al
0x100ecee7  mov     [esi+3Ch], al
0x100eceea  jmp     loc_100ECF9C
0x100eceef  cmp     esi, ?domNode@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::domNode ...
0x100ecef5  jnz     short loc_100ECF12
0x100ecef7  lea     eax, [esi+esi]
0x100ecefa  push    eax; Size
0x100ecefb  push    ?domNode@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecf01  push    ebx; Buf1
0x100ecf02  call    _memcmp
0x100ecf07  add     esp, 0Ch
0x100ecf0a  test    eax, eax
0x100ecf0c  jz      loc_100ECE86
0x100ecf12  cmp     esi, ?inputSource@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::inputSource ...
0x100ecf18  jnz     short loc_100ECF46
0x100ecf1a  lea     eax, [esi+esi]
0x100ecf1d  push    eax; Size
0x100ecf1e  push    ?inputSource@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ecf24  push    ebx; Buf1
0x100ecf25  call    _memcmp
0x100ecf2a  add     esp, 0Ch
0x100ecf2d  test    eax, eax
0x100ecf2f  jnz     short loc_100ECF46
0x100ecf31  lea     eax, [ebp+varValue]
0x100ecf34  push    eax; pvargSrc
0x100ecf35  mov     eax, [ebp+this]
0x100ecf38  add     eax, 580h
0x100ecf3d  push    eax; pvargDest
0x100ecf3e  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100ecf44  jmp     short loc_100ECF97
0x100ecf46  sub     esp, 10h
0x100ecf49  lea     esi, [ebp+varValue]
0x100ecf4c  mov     edi, esp
0x100ecf4e  movsd
0x100ecf4f  movsd
0x100ecf50  movsd
0x100ecf51  movsd
0x100ecf52  push    ebx; pwhName
0x100ecf53  push    [ebp+this]; this
0x100ecf56  call    ?putProperty@Reader@@UAGJPBGUtagVARIANT@@@Z; Reader::putProperty(ushort const *,tagVARIANT)
0x100ecf5b  jmp     short loc_100ECF97
0x100ecf5d  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100ecf60  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100ecf65  retn
0x100ecf66  mov     esp, [ebp+ms_exc.old_esp]
0x100ecf69  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100ecf6e  mov     ecx, __tls_index
0x100ecf74  mov     eax, large fs:2Ch
0x100ecf7a  mov     eax, [eax+ecx*4]
0x100ecf7d  mov     eax, [eax+4]
0x100ecf83  mov     edi, [eax+8]
0x100ecf86  mov     eax, [edi]
0x100ecf88  mov     esi, [eax+34h]
0x100ecf8b  mov     ecx, esi; this
0x100ecf8d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ecf93  mov     ecx, edi
0x100ecf95  call    esi
0x100ecf97  mov     edi, eax
0x100ecf99  mov     [ebp+hr], edi
0x100ecf9c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100ecfa3  mov     ecx, [ebp+pDeclHandler]
0x100ecfa6  test    ecx, ecx
0x100ecfa8  jz      short loc_100ECFBA
0x100ecfaa  mov     eax, [ecx]
0x100ecfac  push    ecx
0x100ecfad  mov     esi, [eax+8]
0x100ecfb0  mov     ecx, esi; this
0x100ecfb2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ecfb8  call    esi
0x100ecfba  mov     ecx, [ebp+pLexicalHandler]
0x100ecfbd  test    ecx, ecx
0x100ecfbf  jz      short loc_100ECFD1
0x100ecfc1  mov     eax, [ecx]
0x100ecfc3  push    ecx
0x100ecfc4  mov     esi, [eax+8]
0x100ecfc7  mov     ecx, esi; this
0x100ecfc9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ecfcf  call    esi
0x100ecfd1  mov     edx, [ebp+pSchemaDeclHandler]
0x100ecfd4  test    edx, edx
0x100ecfd6  jz      short loc_100ECFE8
0x100ecfd8  mov     eax, [edx]
0x100ecfda  push    edx
0x100ecfdb  mov     esi, [eax+8]
0x100ecfde  mov     ecx, esi; this
0x100ecfe0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ecfe6  call    esi
0x100ecfe8  mov     ecx, [ebp+pSchemaCache]
0x100ecfeb  test    ecx, ecx
0x100ecfed  jz      short loc_100ECFFF
0x100ecfef  mov     eax, [ecx]
0x100ecff1  push    ecx
0x100ecff2  mov     esi, [eax+8]
0x100ecff5  mov     ecx, esi; this
0x100ecff7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ecffd  call    esi
0x100ecfff  mov     eax, edi
0x100ed001  mov     ecx, [ebp+ms_exc.registration.Next]
0x100ed004  mov     large fs:0, ecx
0x100ed00b  pop     ecx
0x100ed00c  pop     edi
0x100ed00d  pop     esi
0x100ed00e  pop     ebx
0x100ed00f  leave
0x100ed010  retn    18h
```
