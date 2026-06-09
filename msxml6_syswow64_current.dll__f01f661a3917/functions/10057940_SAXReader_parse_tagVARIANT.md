# SAXReader::parse(tagVARIANT)

- ea: `0x10057940`
- end: `0x10057b5b`
- name: `?parse@SAXReader@@UAGJUtagVARIANT@@@Z`
- size: `539`
- prototype: `HRESULT __stdcall(SAXReader *this, tagVARIANT varInput)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1003fba3`
- `0x1004e820`
- `0x1005064c`
- `0x10057940`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x100eb3d3`
- `0x1012bf38`

## import_xrefs

- `OLEAUT32!__imp__VariantClear@4` at `0x10057b41`
- `OLEAUT32!__imp__VariantClear@4` at `0x10057b41`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100579c2`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100579c2`

## pseudocode

```c
HRESULT __stdcall SAXReader::parse(SAXReader *this, tagVARIANT varInput)
{
  int DTSReader; // esi
  tagVARIANT *p_varInput; // ecx
  IUnknown *punkVal; // esi
  unsigned int vt; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  IUnknown **ppunkVal; // eax
  Object *ObjectFromIUnk; // eax
  TLSDATA *v11; // eax
  EnsureTls _EnsureTls; // [esp+18h] [ebp-24h] BYREF
  HRESULT hr; // [esp+1Ch] [ebp-20h]
  bool fClearVariant; // [esp+23h] [ebp-19h]
  CPPEH_RECORD ms_exc; // [esp+24h] [ebp-18h]

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( !_EnsureTls._tlsdata )
    return -2147467259;
  _EnsureTls._tlsdata = 0;
  fClearVariant = 0;
  ms_exc.registration.TryLevel = 0;
  if ( this->_fBusy )
  {
    DTSReader = -2147467259;
  }
  else
  {
    if ( this->_securitySetting != AllowNone )
    {
      if ( varInput.vt < 2u || varInput.vt == 10 )
      {
        DTSReader = VariantCopy(&varInput, &this->_varInput);
        hr = DTSReader;
        if ( DTSReader < 0 )
          goto LABEL_6;
        fClearVariant = 1;
      }
      p_varInput = &varInput;
      punkVal = 0;
      while ( p_varInput )
      {
        vt = p_varInput->vt;
        if ( vt <= 0xD )
        {
          if ( vt == 13 || p_varInput->vt && vt == 9 )
            punkVal = p_varInput->punkVal;
          break;
        }
        v7 = vt - 16393;
        if ( !v7 )
          goto LABEL_23;
        v8 = v7 - 3;
        if ( v8 )
        {
          if ( v8 != 1 )
            break;
LABEL_23:
          ppunkVal = p_varInput->ppunkVal;
          if ( ppunkVal )
            punkVal = *ppunkVal;
          break;
        }
        p_varInput = p_varInput->pvarVal;
      }
      if ( punkVal )
      {
        ObjectFromIUnk = Object::getObjectFromIUnk(punkVal, &IID_Document, 0);
        if ( ObjectFromIUnk )
          v11 = (TLSDATA *)ObjectFromIUnk[28].__vftable;
        else
          v11 = (TLSDATA *)Object::getObjectFromIUnk(punkVal, &IID_Node, 0);
        _EnsureTls._tlsdata = v11;
      }
      else
      {
        v11 = 0;
      }
      if ( v11 )
      {
        assign(&this->_pDtsReader._p, 0);
        DTSReader = SAXReader::CreateDTSReader(this, &this->_pDtsReader._p);
        hr = DTSReader;
        if ( DTSReader < 0 )
          goto LABEL_6;
        this->_fBusy = 1;
        DTSReader = this->_pDtsReader._p->traverse(this->_pDtsReader._p, (Node *)_EnsureTls._tlsdata);
        hr = DTSReader;
        assign(&this->_pDtsReader._p, 0);
      }
      else
      {
        this->_fBusy = 1;
        DTSReader = Reader::parse(this, varInput);
        hr = DTSReader;
      }
      ms_exc.registration.TryLevel = -2;
      this->_fBusy = 0;
      goto CleanUp_29;
    }
    DTSReader = -2147024891;
  }
  hr = DTSReader;
LABEL_6:
  ms_exc.registration.TryLevel = -2;
CleanUp_29:
  if ( fClearVariant )
    VariantClear(&varInput);
  return DTSReader;
}

```

## disassembly

```asm
0x10057940  push    1Ch
0x10057942  push    offset stru_10173BC8
0x10057947  call    __SEH_prolog4
0x1005794c  lea     ecx, [ebp+_EnsureTls]; this
0x1005794f  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x10057954  cmp     [ebp+_EnsureTls._tlsdata], 0
0x10057958  jnz     short loc_10057964
0x1005795a  mov     eax, 80004005h
0x1005795f  jmp     loc_10057B49
0x10057964  xor     ebx, ebx
0x10057966  mov     eax, ebx
0x10057968  mov     [ebp+_EnsureTls._tlsdata], eax
0x1005796b  mov     [ebp+fClearVariant], bl
0x1005796e  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x10057971  mov     edi, [ebp+this]
0x10057974  cmp     [edi+570h], bl
0x1005797a  jz      short loc_10057990
0x1005797c  mov     esi, 80004005h
0x10057981  mov     [ebp+hr], esi
0x10057984  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1005798b  jmp     CleanUp_29
0x10057990  cmp     dword ptr [edi+544h], 2
0x10057997  jnz     short loc_100579A0
0x10057999  mov     esi, 80070005h
0x1005799e  jmp     short loc_10057981
0x100579a0  mov     ax, word ptr [ebp+varInput.___u0]
0x100579a4  xor     ecx, ecx
0x100579a6  inc     ecx
0x100579a7  cmp     ax, cx
0x100579aa  jz      short loc_100579B7
0x100579ac  test    ax, ax
0x100579af  jz      short loc_100579B7
0x100579b1  cmp     ax, 0Ah
0x100579b5  jnz     short loc_100579D5
0x100579b7  lea     eax, [edi+580h]
0x100579bd  push    eax; pvargSrc
0x100579be  lea     eax, [ebp+varInput]
0x100579c1  push    eax; pvargDest
0x100579c2  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100579c8  mov     esi, eax
0x100579ca  mov     [ebp+hr], esi
0x100579cd  test    esi, esi
0x100579cf  js      short loc_10057984
0x100579d1  mov     [ebp+fClearVariant], 1
0x100579d5  lea     ecx, [ebp+varInput]
0x100579d8  mov     esi, ebx
0x100579da  mov     [ebp+var_28], esi
0x100579dd  test    ecx, ecx
0x100579df  jz      short loc_10057A1B
0x100579e1  movzx   eax, word ptr [ecx]
0x100579e4  cmp     eax, 0Dh
0x100579e7  ja      short loc_100579FE
0x100579e9  jz      short loc_100579F9
0x100579eb  sub     eax, ebx
0x100579ed  jz      short loc_10057A1B
0x100579ef  sub     eax, 1
0x100579f2  jz      short loc_10057A1B
0x100579f4  sub     eax, 8
0x100579f7  jnz     short loc_10057A1B
0x100579f9  mov     esi, [ecx+8]
0x100579fc  jmp     short loc_10057A18
0x100579fe  sub     eax, 4009h
0x10057a03  jz      short loc_10057A0F
0x10057a05  sub     eax, 3
0x10057a08  jz      short loc_10057A38
0x10057a0a  sub     eax, 1
0x10057a0d  jnz     short loc_10057A1B
0x10057a0f  mov     eax, [ecx+8]
0x10057a12  test    eax, eax
0x10057a14  jz      short loc_10057A1B
0x10057a16  mov     esi, [eax]
0x10057a18  mov     [ebp+var_28], esi
0x10057a1b  test    esi, esi
0x10057a1d  jz      short loc_10057A4C
0x10057a1f  push    ebx; fInsideWinRT
0x10057a20  mov     edx, offset ?IID_Document@@3U_GUID@@B; iid
0x10057a25  mov     ecx, esi; pUnk
0x10057a27  call    ?getObjectFromIUnk@Object@@SGPAV1@PAUIUnknown@@ABU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x10057a2c  test    eax, eax
0x10057a2e  jz      short loc_10057A3D
0x10057a30  mov     eax, [eax+70h]
0x10057a33  mov     [ebp+_EnsureTls._tlsdata], eax
0x10057a36  jmp     short loc_10057A4E
0x10057a38  mov     ecx, [ecx+8]
0x10057a3b  jmp     short loc_100579DD
0x10057a3d  push    ebx; fInsideWinRT
0x10057a3e  mov     edx, offset ?IID_Node@@3U_GUID@@B; iid
0x10057a43  mov     ecx, esi; pUnk
0x10057a45  call    ?getObjectFromIUnk@Object@@SGPAV1@PAUIUnknown@@ABU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x10057a4a  jmp     short loc_10057A33
0x10057a4c  mov     eax, ebx
0x10057a4e  test    eax, eax
0x10057a50  jz      short loc_10057AAC
0x10057a52  lea     esi, [edi+574h]
0x10057a58  mov     [ebp+ppref], esi
0x10057a5b  xor     edx, edx; pref
0x10057a5d  mov     ecx, esi; ppref
0x10057a5f  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10057a64  push    esi; ppDtsReader
0x10057a65  mov     ecx, edi; this
0x10057a67  call    ?CreateDTSReader@SAXReader@@IAEJPAPAVDTSReader@@@Z; SAXReader::CreateDTSReader(DTSReader * *)
0x10057a6c  mov     esi, eax
0x10057a6e  mov     [ebp+hr], esi
0x10057a71  test    esi, esi
0x10057a73  js      loc_10057984
0x10057a79  mov     byte ptr [edi+570h], 1
0x10057a80  mov     edi, [edi+574h]
0x10057a86  mov     eax, [edi]
0x10057a88  mov     esi, [eax+10h]
0x10057a8b  mov     eax, [ebp+_EnsureTls._tlsdata]
0x10057a8e  push    eax
0x10057a8f  mov     ecx, esi; this
0x10057a91  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10057a97  mov     ecx, edi
0x10057a99  call    esi
0x10057a9b  mov     esi, eax
0x10057a9d  mov     [ebp+hr], esi
0x10057aa0  xor     edx, edx; pref
0x10057aa2  mov     ecx, [ebp+ppref]; ppref
0x10057aa5  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10057aaa  jmp     short loc_10057ACD
0x10057aac  mov     byte ptr [edi+570h], 1
0x10057ab3  sub     esp, 10h
0x10057ab6  lea     esi, [ebp+varInput]
0x10057ab9  mov     edi, esp
0x10057abb  movsd
0x10057abc  movsd
0x10057abd  movsd
0x10057abe  movsd
0x10057abf  mov     ecx, [ebp+this]
0x10057ac2  push    ecx; this
0x10057ac3  call    ?parse@Reader@@UAGJUtagVARIANT@@@Z; Reader::parse(tagVARIANT)
0x10057ac8  mov     esi, eax
0x10057aca  mov     [ebp+hr], esi
0x10057acd  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10057ad4  jmp     short loc_10057B2E
0x10057ad6  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10057ad9  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x10057ade  retn
0x10057adf  mov     esp, [ebp+ms_exc.old_esp]
0x10057ae2  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10057ae7  mov     ecx, [ebp+this]
0x10057aea  add     ecx, 574h; ppref
0x10057af0  xor     edx, edx; pref
0x10057af2  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10057af7  mov     ecx, __tls_index
0x10057afd  mov     eax, large fs:2Ch
0x10057b03  mov     eax, [eax+ecx*4]
0x10057b06  mov     eax, [eax+4]
0x10057b0c  mov     edi, [eax+8]
0x10057b0f  mov     eax, [edi]
0x10057b11  mov     esi, [eax+34h]
0x10057b14  mov     ecx, esi; this
0x10057b16  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10057b1c  mov     ecx, edi
0x10057b1e  call    esi
0x10057b20  mov     esi, eax
0x10057b22  mov     [ebp+hr], esi
0x10057b25  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10057b2c  xor     ebx, ebx
0x10057b2e  mov     eax, [ebp+this]
0x10057b31  mov     [eax+570h], bl
0x10057b37  cmp     [ebp+fClearVariant], 0
0x10057b3b  jz      short loc_10057B47
0x10057b3d  lea     eax, [ebp+varInput]
0x10057b40  push    eax; pvarg
0x10057b41  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10057b47  mov     eax, esi
0x10057b49  mov     ecx, [ebp+ms_exc.registration.Next]
0x10057b4c  mov     large fs:0, ecx
0x10057b53  pop     ecx
0x10057b54  pop     edi
0x10057b55  pop     esi
0x10057b56  pop     ebx
0x10057b57  leave
0x10057b58  retn    14h
```
