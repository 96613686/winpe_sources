# SAXReader::getProperty(ushort const *,tagVARIANT *)

- ea: `0x100ec300`
- end: `0x100ec5ad`
- name: `?getProperty@SAXReader@@UAGJPBGPAUtagVARIANT@@@Z`
- size: `685`
- prototype: `HRESULT __stdcall(SAXReader *this, const wchar_t *pwhName, tagVARIANT *pvarValue)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x1004fbae`
- `0x100505bc`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100ec300`
- `0x100f410a`
- `0x10164df3`
- `0x10164e39`
- `0x10169070`
- `0x10171298`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x100ec33a`
- `OLEAUT32!__imp__VariantInit@4` at `0x100ec33a`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100ec53f`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100ec53f`

## pseudocode

```c
HRESULT __stdcall SAXReader::getProperty(SAXReader *this, const wchar_t *pwhName, tagVARIANT *pvarValue)
{
  HRESULT Property; // edi
  DTSReader *p; // ecx
  TLSDATA *v6; // esi
  size_t v7; // eax
  TLSDATA *tlsdata; // ecx
  HRESULT hrSystemException; // edx
  ISAXLexicalHandler *DeclHandler; // eax
  TLSDATA *v11; // eax
  unsigned int dwTID; // ecx
  TLSDATA *v13; // eax
  ScopedAllocator *pRegexAlloc; // ecx
  HRESULT v15; // eax
  EnsureTls _EnsureTls; // [esp+14h] [ebp-20h] BYREF
  HRESULT hr; // [esp+18h] [ebp-1Ch]
  CPPEH_RECORD ms_exc; // [esp+1Ch] [ebp-18h]

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( !_EnsureTls._tlsdata )
    return -2147467259;
  Property = -2147024809;
  if ( !pvarValue )
    return -2147024809;
  VariantInit(pvarValue);
  ms_exc.registration.TryLevel = 0;
  p = this->_pDtsReader._p;
  if ( p )
  {
    Property = DTSReader::getProperty(p, pwhName, pvarValue);
    hr = Property;
  }
  if ( Property == -2147024809 )
  {
    _EnsureTls._tlsdata = 0;
    if ( pwhName )
      v6 = (TLSDATA *)xstrlenw(pwhName, 0x7FFFFFFFu);
    else
      v6 = 0;
    _EnsureTls._tlsdata = v6;
    v7 = 2 * (_DWORD)v6;
    if ( v6 == (TLSDATA *)CodeStringPtr::declarationHandler.n )
    {
      if ( !memcmp(pwhName, CodeStringPtr::declarationHandler.pwh, 2 * (_DWORD)v6) )
      {
        Property = 0;
        hr = 0;
        pvarValue->vt = 13;
        tlsdata = (TLSDATA *)this->_pSchemaProxy._p;
        _EnsureTls._tlsdata = tlsdata;
        if ( tlsdata )
        {
          hrSystemException = tlsdata[1]._hrSystemException;
          if ( hrSystemException )
          {
            (*(void (__thiscall **)(_DWORD, HRESULT))(*(_DWORD *)hrSystemException + 4))(
              *(_DWORD *)(*(_DWORD *)hrSystemException + 4),
              tlsdata[1]._hrSystemException);
            tlsdata = _EnsureTls._tlsdata;
          }
          DeclHandler = (ISAXLexicalHandler *)tlsdata[1]._hrSystemException;
        }
        else
        {
          DeclHandler = (ISAXLexicalHandler *)Reader::GetDeclHandler(this);
        }
        goto LABEL_22;
      }
      v7 = 2 * (_DWORD)v6;
    }
    if ( v6 != (TLSDATA *)CodeStringPtr::lexicalHandler.n || memcmp(pwhName, CodeStringPtr::lexicalHandler.pwh, v7) )
    {
      if ( v6 == (TLSDATA *)CodeStringPtr::schemaDeclarationHandler.n
        && !memcmp(pwhName, CodeStringPtr::schemaDeclarationHandler.pwh, 2 * (_DWORD)v6) )
      {
        Property = 0;
        hr = 0;
        pvarValue->vt = 13;
        v11 = (TLSDATA *)this->_pSchemaProxy._p;
        _EnsureTls._tlsdata = v11;
        if ( v11 )
        {
          dwTID = v11[1]._dwTID;
          if ( dwTID )
          {
            (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)dwTID + 4))(
              *(_DWORD *)(*(_DWORD *)dwTID + 4),
              dwTID);
            v11 = _EnsureTls._tlsdata;
          }
          DeclHandler = (ISAXLexicalHandler *)v11[1]._dwTID;
          goto LABEL_22;
        }
      }
      else
      {
        if ( v6 != (TLSDATA *)CodeStringPtr::schemas.n || memcmp(pwhName, CodeStringPtr::schemas.pwh, 2 * (_DWORD)v6) )
        {
          if ( v6 == (TLSDATA *)CodeStringPtr::domNode.n && !memcmp(pwhName, CodeStringPtr::domNode.pwh, 2 * (_DWORD)v6) )
          {
            Property = -2147467259;
          }
          else
          {
            if ( v6 == (TLSDATA *)CodeStringPtr::inputSource.n
              && !memcmp(pwhName, CodeStringPtr::inputSource.pwh, 2 * (_DWORD)v6) )
            {
              v15 = VariantCopy(pvarValue, &this->_varInput);
            }
            else
            {
              v15 = Reader::getProperty(this, pwhName, pvarValue);
            }
            Property = v15;
          }
          hr = Property;
          return Property;
        }
        Property = 0;
        hr = 0;
        pvarValue->vt = 9;
        v13 = (TLSDATA *)this->_pSchemaProxy._p;
        _EnsureTls._tlsdata = v13;
        if ( v13 )
        {
          pRegexAlloc = v13[1]._pRegexAlloc;
          if ( pRegexAlloc )
          {
            (*(void (__thiscall **)(_DWORD, ScopedAllocator *))(*(_DWORD *)pRegexAlloc->_buffer + 4))(
              *(_DWORD *)(*(_DWORD *)pRegexAlloc->_buffer + 4),
              pRegexAlloc);
            v13 = _EnsureTls._tlsdata;
          }
          DeclHandler = (ISAXLexicalHandler *)v13[1]._pRegexAlloc;
          goto LABEL_22;
        }
      }
      pvarValue->decVal.Lo32 = 0;
      return Property;
    }
    Property = 0;
    hr = 0;
    pvarValue->vt = 13;
    DeclHandler = Reader::GetLexicalHandler(this);
LABEL_22:
    pvarValue->decVal.Lo32 = (unsigned int)DeclHandler;
  }
  return Property;
}

```

## disassembly

```asm
0x100ec300  push    14h
0x100ec302  push    offset stru_10179BB8
0x100ec307  call    __SEH_prolog4
0x100ec30c  lea     ecx, [ebp+_EnsureTls]; this
0x100ec30f  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100ec314  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100ec318  jnz     short loc_100EC324
0x100ec31a  mov     eax, 80004005h
0x100ec31f  jmp     loc_100EC59B
0x100ec324  mov     esi, 80070057h
0x100ec329  mov     edi, esi
0x100ec32b  mov     ebx, [ebp+pvarValue]
0x100ec32e  test    ebx, ebx
0x100ec330  jnz     short loc_100EC339
0x100ec332  mov     eax, esi
0x100ec334  jmp     loc_100EC59B
0x100ec339  push    ebx; pvarg
0x100ec33a  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100ec340  mov     [ebp+ms_exc.registration.TryLevel], 0
0x100ec347  mov     eax, [ebp+this]
0x100ec34a  mov     ecx, [eax+574h]; this
0x100ec350  test    ecx, ecx
0x100ec352  jz      short loc_100EC362
0x100ec354  push    ebx; pvarValue
0x100ec355  push    [ebp+pwhName]; pwhName
0x100ec358  call    ?getProperty@DTSReader@@QAEJPBGPAUtagVARIANT@@@Z; DTSReader::getProperty(ushort const *,tagVARIANT *)
0x100ec35d  mov     edi, eax
0x100ec35f  mov     [ebp+hr], edi
0x100ec362  cmp     edi, esi
0x100ec364  jnz     loc_100EC592
0x100ec36a  mov     [ebp+var_24], 0
0x100ec371  mov     [ebp+_EnsureTls._tlsdata], 0
0x100ec378  mov     edi, [ebp+pwhName]
0x100ec37b  mov     [ebp+var_24], edi
0x100ec37e  test    edi, edi
0x100ec380  jz      short loc_100EC392
0x100ec382  mov     edx, 7FFFFFFFh; cchMax
0x100ec387  mov     ecx, edi; psz
0x100ec389  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x100ec38e  mov     esi, eax
0x100ec390  jmp     short loc_100EC394
0x100ec392  xor     esi, esi
0x100ec394  mov     [ebp+_EnsureTls._tlsdata], esi
0x100ec397  lea     eax, [esi+esi]
0x100ec39a  cmp     esi, ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::declarationHandler ...
0x100ec3a0  jnz     short loc_100EC3FC
0x100ec3a2  push    eax; Size
0x100ec3a3  push    ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec3a9  push    edi; Buf1
0x100ec3aa  call    _memcmp
0x100ec3af  add     esp, 0Ch
0x100ec3b2  test    eax, eax
0x100ec3b4  jnz     short loc_100EC3F9
0x100ec3b6  xor     edi, edi
0x100ec3b8  mov     [ebp+hr], edi
0x100ec3bb  push    0Dh
0x100ec3bd  pop     eax
0x100ec3be  mov     [ebx], ax
0x100ec3c1  mov     eax, [ebp+this]
0x100ec3c4  mov     ecx, [eax+578h]
0x100ec3ca  mov     [ebp+_EnsureTls._tlsdata], ecx
0x100ec3cd  test    ecx, ecx
0x100ec3cf  jz      short loc_100EC3F0
0x100ec3d1  mov     edx, [ecx+30h]
0x100ec3d4  test    edx, edx
0x100ec3d6  jz      short loc_100EC3EB
0x100ec3d8  mov     eax, [edx]
0x100ec3da  push    edx
0x100ec3db  mov     esi, [eax+4]
0x100ec3de  mov     ecx, esi; this
0x100ec3e0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec3e6  call    esi
0x100ec3e8  mov     ecx, [ebp+_EnsureTls._tlsdata]
0x100ec3eb  mov     eax, [ecx+30h]
0x100ec3ee  jmp     short loc_100EC42B
0x100ec3f0  mov     ecx, eax; this
0x100ec3f2  call    ?GetDeclHandler@Reader@@QAEPAUISAXDeclHandler@@XZ; Reader::GetDeclHandler(void)
0x100ec3f7  jmp     short loc_100EC42B
0x100ec3f9  lea     eax, [esi+esi]
0x100ec3fc  cmp     esi, ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::lexicalHandler ...
0x100ec402  jnz     short loc_100EC433
0x100ec404  push    eax; Size
0x100ec405  push    ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec40b  push    edi; Buf1
0x100ec40c  call    _memcmp
0x100ec411  add     esp, 0Ch
0x100ec414  test    eax, eax
0x100ec416  jnz     short loc_100EC433
0x100ec418  xor     edi, edi
0x100ec41a  mov     [ebp+hr], edi
0x100ec41d  push    0Dh
0x100ec41f  pop     eax
0x100ec420  mov     [ebx], ax
0x100ec423  mov     ecx, [ebp+this]; this
0x100ec426  call    ?GetLexicalHandler@Reader@@QAEPAUISAXLexicalHandler@@XZ; Reader::GetLexicalHandler(void)
0x100ec42b  mov     [ebx+8], eax
0x100ec42e  jmp     loc_100EC592
0x100ec433  cmp     esi, ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemaDeclarationHandler ...
0x100ec439  jnz     short loc_100EC48C
0x100ec43b  lea     eax, [esi+esi]
0x100ec43e  push    eax; Size
0x100ec43f  push    ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec445  push    edi; Buf1
0x100ec446  call    _memcmp
0x100ec44b  add     esp, 0Ch
0x100ec44e  test    eax, eax
0x100ec450  jnz     short loc_100EC48C
0x100ec452  xor     edi, edi
0x100ec454  mov     [ebp+hr], edi
0x100ec457  push    0Dh
0x100ec459  pop     eax
0x100ec45a  mov     [ebx], ax
0x100ec45d  mov     eax, [ebp+this]
0x100ec460  mov     eax, [eax+578h]
0x100ec466  mov     [ebp+_EnsureTls._tlsdata], eax
0x100ec469  test    eax, eax
0x100ec46b  jz      short loc_100EC4E8
0x100ec46d  mov     ecx, [eax+44h]
0x100ec470  test    ecx, ecx
0x100ec472  jz      short loc_100EC487
0x100ec474  mov     eax, [ecx]
0x100ec476  push    ecx
0x100ec477  mov     esi, [eax+4]
0x100ec47a  mov     ecx, esi; this
0x100ec47c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec482  call    esi
0x100ec484  mov     eax, [ebp+_EnsureTls._tlsdata]
0x100ec487  mov     eax, [eax+44h]
0x100ec48a  jmp     short loc_100EC42B
0x100ec48c  cmp     esi, ?schemas@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemas ...
0x100ec492  jnz     short loc_100EC4F0
0x100ec494  lea     eax, [esi+esi]
0x100ec497  push    eax; Size
0x100ec498  push    ?schemas@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec49e  push    edi; Buf1
0x100ec49f  call    _memcmp
0x100ec4a4  add     esp, 0Ch
0x100ec4a7  test    eax, eax
0x100ec4a9  jnz     short loc_100EC4F0
0x100ec4ab  xor     edi, edi
0x100ec4ad  mov     [ebp+hr], edi
0x100ec4b0  push    9
0x100ec4b2  pop     eax
0x100ec4b3  mov     [ebx], ax
0x100ec4b6  mov     eax, [ebp+this]
0x100ec4b9  mov     eax, [eax+578h]
0x100ec4bf  mov     [ebp+_EnsureTls._tlsdata], eax
0x100ec4c2  test    eax, eax
0x100ec4c4  jz      short loc_100EC4E8
0x100ec4c6  mov     ecx, [eax+48h]
0x100ec4c9  test    ecx, ecx
0x100ec4cb  jz      short loc_100EC4E0
0x100ec4cd  mov     eax, [ecx]
0x100ec4cf  push    ecx
0x100ec4d0  mov     esi, [eax+4]
0x100ec4d3  mov     ecx, esi; this
0x100ec4d5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec4db  call    esi
0x100ec4dd  mov     eax, [ebp+_EnsureTls._tlsdata]
0x100ec4e0  mov     eax, [eax+48h]
0x100ec4e3  jmp     loc_100EC42B
0x100ec4e8  mov     [ebx+8], edi
0x100ec4eb  jmp     loc_100EC592
0x100ec4f0  cmp     esi, ?domNode@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::domNode ...
0x100ec4f6  jnz     short loc_100EC516
0x100ec4f8  lea     eax, [esi+esi]
0x100ec4fb  push    eax; Size
0x100ec4fc  push    ?domNode@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec502  push    edi; Buf1
0x100ec503  call    _memcmp
0x100ec508  add     esp, 0Ch
0x100ec50b  test    eax, eax
0x100ec50d  jnz     short loc_100EC516
0x100ec50f  mov     edi, 80004005h
0x100ec514  jmp     short loc_100EC58F
0x100ec516  cmp     esi, ?inputSource@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::inputSource ...
0x100ec51c  jnz     short loc_100EC547
0x100ec51e  lea     eax, [esi+esi]
0x100ec521  push    eax; Size
0x100ec522  push    ?inputSource@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec528  push    edi; Buf1
0x100ec529  call    _memcmp
0x100ec52e  add     esp, 0Ch
0x100ec531  test    eax, eax
0x100ec533  jnz     short loc_100EC547
0x100ec535  mov     eax, [ebp+this]
0x100ec538  add     eax, 580h
0x100ec53d  push    eax; pvargSrc
0x100ec53e  push    ebx; pvargDest
0x100ec53f  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100ec545  jmp     short loc_100EC58D
0x100ec547  push    ebx; pvarValue
0x100ec548  push    edi; pwhName
0x100ec549  push    [ebp+this]; this
0x100ec54c  call    ?getProperty@Reader@@UAGJPBGPAUtagVARIANT@@@Z; Reader::getProperty(ushort const *,tagVARIANT *)
0x100ec551  jmp     short loc_100EC58D
0x100ec553  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100ec556  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100ec55b  retn
0x100ec55c  mov     esp, [ebp+ms_exc.old_esp]
0x100ec55f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100ec564  mov     ecx, __tls_index
0x100ec56a  mov     eax, large fs:2Ch
0x100ec570  mov     eax, [eax+ecx*4]
0x100ec573  mov     eax, [eax+4]
0x100ec579  mov     edi, [eax+8]
0x100ec57c  mov     eax, [edi]
0x100ec57e  mov     esi, [eax+34h]
0x100ec581  mov     ecx, esi; this
0x100ec583  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec589  mov     ecx, edi
0x100ec58b  call    esi
0x100ec58d  mov     edi, eax
0x100ec58f  mov     [ebp+hr], edi
0x100ec592  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100ec599  mov     eax, edi
0x100ec59b  mov     ecx, [ebp+ms_exc.registration.Next]
0x100ec59e  mov     large fs:0, ecx
0x100ec5a5  pop     ecx
0x100ec5a6  pop     edi
0x100ec5a7  pop     esi
0x100ec5a8  pop     ebx
0x100ec5a9  leave
0x100ec5aa  retn    0Ch
```
