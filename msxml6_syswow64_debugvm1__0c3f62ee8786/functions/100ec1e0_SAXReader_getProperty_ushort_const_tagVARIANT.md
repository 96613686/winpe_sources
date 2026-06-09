# SAXReader::getProperty(ushort const *,tagVARIANT *)

- ea: `0x100ec1e0`
- end: `0x100ec48d`
- name: `?getProperty@SAXReader@@UAGJPBGPAUtagVARIANT@@@Z`
- size: `685`
- prototype: `HRESULT __stdcall(SAXReader *this, const wchar_t *pwhName, tagVARIANT *pvarValue)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x1004fc3e`
- `0x1005064c`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x100ec1e0`
- `0x100f3fe9`
- `0x10164cf3`
- `0x10164d39`
- `0x10168f80`
- `0x101711a8`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x100ec21a`
- `OLEAUT32!__imp__VariantInit@4` at `0x100ec21a`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100ec41f`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100ec41f`

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
  ISAXDeclHandler *DeclHandler; // eax
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
          DeclHandler = (ISAXDeclHandler *)tlsdata[1]._hrSystemException;
        }
        else
        {
          DeclHandler = Reader::GetDeclHandler(this);
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
          DeclHandler = (ISAXDeclHandler *)v11[1]._dwTID;
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
          DeclHandler = (ISAXDeclHandler *)v13[1]._pRegexAlloc;
          goto LABEL_22;
        }
      }
      pvarValue->decVal.Lo32 = 0;
      return Property;
    }
    Property = 0;
    hr = 0;
    pvarValue->vt = 13;
    DeclHandler = (ISAXDeclHandler *)Reader::GetLexicalHandler(this);
LABEL_22:
    pvarValue->decVal.Lo32 = (unsigned int)DeclHandler;
  }
  return Property;
}

```

## disassembly

```asm
0x100ec1e0  push    14h
0x100ec1e2  push    offset stru_10179AC8
0x100ec1e7  call    __SEH_prolog4
0x100ec1ec  lea     ecx, [ebp+_EnsureTls]; this
0x100ec1ef  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100ec1f4  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100ec1f8  jnz     short loc_100EC204
0x100ec1fa  mov     eax, 80004005h
0x100ec1ff  jmp     loc_100EC47B
0x100ec204  mov     esi, 80070057h
0x100ec209  mov     edi, esi
0x100ec20b  mov     ebx, [ebp+pvarValue]
0x100ec20e  test    ebx, ebx
0x100ec210  jnz     short loc_100EC219
0x100ec212  mov     eax, esi
0x100ec214  jmp     loc_100EC47B
0x100ec219  push    ebx; pvarg
0x100ec21a  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100ec220  mov     [ebp+ms_exc.registration.TryLevel], 0
0x100ec227  mov     eax, [ebp+this]
0x100ec22a  mov     ecx, [eax+574h]; this
0x100ec230  test    ecx, ecx
0x100ec232  jz      short loc_100EC242
0x100ec234  push    ebx; pvarValue
0x100ec235  push    [ebp+pwhName]; pwhName
0x100ec238  call    ?getProperty@DTSReader@@QAEJPBGPAUtagVARIANT@@@Z; DTSReader::getProperty(ushort const *,tagVARIANT *)
0x100ec23d  mov     edi, eax
0x100ec23f  mov     [ebp+hr], edi
0x100ec242  cmp     edi, esi
0x100ec244  jnz     loc_100EC472
0x100ec24a  mov     [ebp+var_24], 0
0x100ec251  mov     [ebp+_EnsureTls._tlsdata], 0
0x100ec258  mov     edi, [ebp+pwhName]
0x100ec25b  mov     [ebp+var_24], edi
0x100ec25e  test    edi, edi
0x100ec260  jz      short loc_100EC272
0x100ec262  mov     edx, 7FFFFFFFh; cchMax
0x100ec267  mov     ecx, edi; psz
0x100ec269  call    ?xstrlenw@@YGHPBGI@Z; xstrlenw(ushort const *,uint)
0x100ec26e  mov     esi, eax
0x100ec270  jmp     short loc_100EC274
0x100ec272  xor     esi, esi
0x100ec274  mov     [ebp+_EnsureTls._tlsdata], esi
0x100ec277  lea     eax, [esi+esi]
0x100ec27a  cmp     esi, ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::declarationHandler ...
0x100ec280  jnz     short loc_100EC2DC
0x100ec282  push    eax; Size
0x100ec283  push    ?declarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec289  push    edi; Buf1
0x100ec28a  call    _memcmp
0x100ec28f  add     esp, 0Ch
0x100ec292  test    eax, eax
0x100ec294  jnz     short loc_100EC2D9
0x100ec296  xor     edi, edi
0x100ec298  mov     [ebp+hr], edi
0x100ec29b  push    0Dh
0x100ec29d  pop     eax
0x100ec29e  mov     [ebx], ax
0x100ec2a1  mov     eax, [ebp+this]
0x100ec2a4  mov     ecx, [eax+578h]
0x100ec2aa  mov     [ebp+_EnsureTls._tlsdata], ecx
0x100ec2ad  test    ecx, ecx
0x100ec2af  jz      short loc_100EC2D0
0x100ec2b1  mov     edx, [ecx+30h]
0x100ec2b4  test    edx, edx
0x100ec2b6  jz      short loc_100EC2CB
0x100ec2b8  mov     eax, [edx]
0x100ec2ba  push    edx
0x100ec2bb  mov     esi, [eax+4]
0x100ec2be  mov     ecx, esi; this
0x100ec2c0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec2c6  call    esi
0x100ec2c8  mov     ecx, [ebp+_EnsureTls._tlsdata]
0x100ec2cb  mov     eax, [ecx+30h]
0x100ec2ce  jmp     short loc_100EC30B
0x100ec2d0  mov     ecx, eax; this
0x100ec2d2  call    ?GetDeclHandler@Reader@@QAEPAUISAXDeclHandler@@XZ; Reader::GetDeclHandler(void)
0x100ec2d7  jmp     short loc_100EC30B
0x100ec2d9  lea     eax, [esi+esi]
0x100ec2dc  cmp     esi, ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::lexicalHandler ...
0x100ec2e2  jnz     short loc_100EC313
0x100ec2e4  push    eax; Size
0x100ec2e5  push    ?lexicalHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec2eb  push    edi; Buf1
0x100ec2ec  call    _memcmp
0x100ec2f1  add     esp, 0Ch
0x100ec2f4  test    eax, eax
0x100ec2f6  jnz     short loc_100EC313
0x100ec2f8  xor     edi, edi
0x100ec2fa  mov     [ebp+hr], edi
0x100ec2fd  push    0Dh
0x100ec2ff  pop     eax
0x100ec300  mov     [ebx], ax
0x100ec303  mov     ecx, [ebp+this]; this
0x100ec306  call    ?GetLexicalHandler@Reader@@QAEPAUISAXLexicalHandler@@XZ; Reader::GetLexicalHandler(void)
0x100ec30b  mov     [ebx+8], eax
0x100ec30e  jmp     loc_100EC472
0x100ec313  cmp     esi, ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemaDeclarationHandler ...
0x100ec319  jnz     short loc_100EC36C
0x100ec31b  lea     eax, [esi+esi]
0x100ec31e  push    eax; Size
0x100ec31f  push    ?schemaDeclarationHandler@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec325  push    edi; Buf1
0x100ec326  call    _memcmp
0x100ec32b  add     esp, 0Ch
0x100ec32e  test    eax, eax
0x100ec330  jnz     short loc_100EC36C
0x100ec332  xor     edi, edi
0x100ec334  mov     [ebp+hr], edi
0x100ec337  push    0Dh
0x100ec339  pop     eax
0x100ec33a  mov     [ebx], ax
0x100ec33d  mov     eax, [ebp+this]
0x100ec340  mov     eax, [eax+578h]
0x100ec346  mov     [ebp+_EnsureTls._tlsdata], eax
0x100ec349  test    eax, eax
0x100ec34b  jz      short loc_100EC3C8
0x100ec34d  mov     ecx, [eax+44h]
0x100ec350  test    ecx, ecx
0x100ec352  jz      short loc_100EC367
0x100ec354  mov     eax, [ecx]
0x100ec356  push    ecx
0x100ec357  mov     esi, [eax+4]
0x100ec35a  mov     ecx, esi; this
0x100ec35c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec362  call    esi
0x100ec364  mov     eax, [ebp+_EnsureTls._tlsdata]
0x100ec367  mov     eax, [eax+44h]
0x100ec36a  jmp     short loc_100EC30B
0x100ec36c  cmp     esi, ?schemas@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::schemas ...
0x100ec372  jnz     short loc_100EC3D0
0x100ec374  lea     eax, [esi+esi]
0x100ec377  push    eax; Size
0x100ec378  push    ?schemas@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec37e  push    edi; Buf1
0x100ec37f  call    _memcmp
0x100ec384  add     esp, 0Ch
0x100ec387  test    eax, eax
0x100ec389  jnz     short loc_100EC3D0
0x100ec38b  xor     edi, edi
0x100ec38d  mov     [ebp+hr], edi
0x100ec390  push    9
0x100ec392  pop     eax
0x100ec393  mov     [ebx], ax
0x100ec396  mov     eax, [ebp+this]
0x100ec399  mov     eax, [eax+578h]
0x100ec39f  mov     [ebp+_EnsureTls._tlsdata], eax
0x100ec3a2  test    eax, eax
0x100ec3a4  jz      short loc_100EC3C8
0x100ec3a6  mov     ecx, [eax+48h]
0x100ec3a9  test    ecx, ecx
0x100ec3ab  jz      short loc_100EC3C0
0x100ec3ad  mov     eax, [ecx]
0x100ec3af  push    ecx
0x100ec3b0  mov     esi, [eax+4]
0x100ec3b3  mov     ecx, esi; this
0x100ec3b5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec3bb  call    esi
0x100ec3bd  mov     eax, [ebp+_EnsureTls._tlsdata]
0x100ec3c0  mov     eax, [eax+48h]
0x100ec3c3  jmp     loc_100EC30B
0x100ec3c8  mov     [ebx+8], edi
0x100ec3cb  jmp     loc_100EC472
0x100ec3d0  cmp     esi, ?domNode@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::domNode ...
0x100ec3d6  jnz     short loc_100EC3F6
0x100ec3d8  lea     eax, [esi+esi]
0x100ec3db  push    eax; Size
0x100ec3dc  push    ?domNode@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec3e2  push    edi; Buf1
0x100ec3e3  call    _memcmp
0x100ec3e8  add     esp, 0Ch
0x100ec3eb  test    eax, eax
0x100ec3ed  jnz     short loc_100EC3F6
0x100ec3ef  mov     edi, 80004005h
0x100ec3f4  jmp     short loc_100EC46F
0x100ec3f6  cmp     esi, ?inputSource@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::inputSource ...
0x100ec3fc  jnz     short loc_100EC427
0x100ec3fe  lea     eax, [esi+esi]
0x100ec401  push    eax; Size
0x100ec402  push    ?inputSource@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x100ec408  push    edi; Buf1
0x100ec409  call    _memcmp
0x100ec40e  add     esp, 0Ch
0x100ec411  test    eax, eax
0x100ec413  jnz     short loc_100EC427
0x100ec415  mov     eax, [ebp+this]
0x100ec418  add     eax, 580h
0x100ec41d  push    eax; pvargSrc
0x100ec41e  push    ebx; pvargDest
0x100ec41f  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100ec425  jmp     short loc_100EC46D
0x100ec427  push    ebx; pvarValue
0x100ec428  push    edi; pwhName
0x100ec429  push    [ebp+this]; this
0x100ec42c  call    ?getProperty@Reader@@UAGJPBGPAUtagVARIANT@@@Z; Reader::getProperty(ushort const *,tagVARIANT *)
0x100ec431  jmp     short loc_100EC46D
0x100ec433  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100ec436  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100ec43b  retn
0x100ec43c  mov     esp, [ebp+ms_exc.old_esp]
0x100ec43f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100ec444  mov     ecx, __tls_index
0x100ec44a  mov     eax, large fs:2Ch
0x100ec450  mov     eax, [eax+ecx*4]
0x100ec453  mov     eax, [eax+4]
0x100ec459  mov     edi, [eax+8]
0x100ec45c  mov     eax, [edi]
0x100ec45e  mov     esi, [eax+34h]
0x100ec461  mov     ecx, esi; this
0x100ec463  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ec469  mov     ecx, edi
0x100ec46b  call    esi
0x100ec46d  mov     edi, eax
0x100ec46f  mov     [ebp+hr], edi
0x100ec472  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100ec479  mov     eax, edi
0x100ec47b  mov     ecx, [ebp+ms_exc.registration.Next]
0x100ec47e  mov     large fs:0, ecx
0x100ec485  pop     ecx
0x100ec486  pop     edi
0x100ec487  pop     esi
0x100ec488  pop     ebx
0x100ec489  leave
0x100ec48a  retn    0Ch
```
