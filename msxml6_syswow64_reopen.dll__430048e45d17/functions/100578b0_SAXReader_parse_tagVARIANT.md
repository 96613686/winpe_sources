# SAXReader::parse(tagVARIANT)

- ea: `0x100578b0`
- end: `0x10057acb`
- name: `?parse@SAXReader@@UAGJUtagVARIANT@@@Z`
- size: `539`
- prototype: `HRESULT __stdcall(SAXReader *this, tagVARIANT varInput)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1003fb13`
- `0x1004e790`
- `0x100505bc`
- `0x100578b0`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100eb4f3`
- `0x1012c04a`

## import_xrefs

- `OLEAUT32!__imp__VariantClear@4` at `0x10057ab1`
- `OLEAUT32!__imp__VariantClear@4` at `0x10057ab1`
- `OLEAUT32!__imp__VariantCopy@8` at `0x10057932`
- `OLEAUT32!__imp__VariantCopy@8` at `0x10057932`

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
0x100578b0  push    1Ch
0x100578b2  push    offset stru_10173CB8
0x100578b7  call    __SEH_prolog4
0x100578bc  lea     ecx, [ebp+_EnsureTls]; this
0x100578bf  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100578c4  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100578c8  jnz     short loc_100578D4
0x100578ca  mov     eax, 80004005h
0x100578cf  jmp     loc_10057AB9
0x100578d4  xor     ebx, ebx
0x100578d6  mov     eax, ebx
0x100578d8  mov     [ebp+_EnsureTls._tlsdata], eax
0x100578db  mov     [ebp+fClearVariant], bl
0x100578de  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x100578e1  mov     edi, [ebp+this]
0x100578e4  cmp     [edi+570h], bl
0x100578ea  jz      short loc_10057900
0x100578ec  mov     esi, 80004005h
0x100578f1  mov     [ebp+hr], esi
0x100578f4  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100578fb  jmp     CleanUp_29
0x10057900  cmp     dword ptr [edi+544h], 2
0x10057907  jnz     short loc_10057910
0x10057909  mov     esi, 80070005h
0x1005790e  jmp     short loc_100578F1
0x10057910  mov     ax, word ptr [ebp+varInput.___u0]
0x10057914  xor     ecx, ecx
0x10057916  inc     ecx
0x10057917  cmp     ax, cx
0x1005791a  jz      short loc_10057927
0x1005791c  test    ax, ax
0x1005791f  jz      short loc_10057927
0x10057921  cmp     ax, 0Ah
0x10057925  jnz     short loc_10057945
0x10057927  lea     eax, [edi+580h]
0x1005792d  push    eax; pvargSrc
0x1005792e  lea     eax, [ebp+varInput]
0x10057931  push    eax; pvargDest
0x10057932  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x10057938  mov     esi, eax
0x1005793a  mov     [ebp+hr], esi
0x1005793d  test    esi, esi
0x1005793f  js      short loc_100578F4
0x10057941  mov     [ebp+fClearVariant], 1
0x10057945  lea     ecx, [ebp+varInput]
0x10057948  mov     esi, ebx
0x1005794a  mov     [ebp+var_28], esi
0x1005794d  test    ecx, ecx
0x1005794f  jz      short loc_1005798B
0x10057951  movzx   eax, word ptr [ecx]
0x10057954  cmp     eax, 0Dh
0x10057957  ja      short loc_1005796E
0x10057959  jz      short loc_10057969
0x1005795b  sub     eax, ebx
0x1005795d  jz      short loc_1005798B
0x1005795f  sub     eax, 1
0x10057962  jz      short loc_1005798B
0x10057964  sub     eax, 8
0x10057967  jnz     short loc_1005798B
0x10057969  mov     esi, [ecx+8]
0x1005796c  jmp     short loc_10057988
0x1005796e  sub     eax, 4009h
0x10057973  jz      short loc_1005797F
0x10057975  sub     eax, 3
0x10057978  jz      short loc_100579A8
0x1005797a  sub     eax, 1
0x1005797d  jnz     short loc_1005798B
0x1005797f  mov     eax, [ecx+8]
0x10057982  test    eax, eax
0x10057984  jz      short loc_1005798B
0x10057986  mov     esi, [eax]
0x10057988  mov     [ebp+var_28], esi
0x1005798b  test    esi, esi
0x1005798d  jz      short loc_100579BC
0x1005798f  push    ebx; fInsideWinRT
0x10057990  mov     edx, offset ?IID_Document@@3U_GUID@@B; iid
0x10057995  mov     ecx, esi; pUnk
0x10057997  call    ?getObjectFromIUnk@Object@@SGPAV1@PAUIUnknown@@ABU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x1005799c  test    eax, eax
0x1005799e  jz      short loc_100579AD
0x100579a0  mov     eax, [eax+70h]
0x100579a3  mov     [ebp+_EnsureTls._tlsdata], eax
0x100579a6  jmp     short loc_100579BE
0x100579a8  mov     ecx, [ecx+8]
0x100579ab  jmp     short loc_1005794D
0x100579ad  push    ebx; fInsideWinRT
0x100579ae  mov     edx, offset ?IID_Node@@3U_GUID@@B; iid
0x100579b3  mov     ecx, esi; pUnk
0x100579b5  call    ?getObjectFromIUnk@Object@@SGPAV1@PAUIUnknown@@ABU_GUID@@_N@Z; Object::getObjectFromIUnk(IUnknown *,_GUID const &,bool)
0x100579ba  jmp     short loc_100579A3
0x100579bc  mov     eax, ebx
0x100579be  test    eax, eax
0x100579c0  jz      short loc_10057A1C
0x100579c2  lea     esi, [edi+574h]
0x100579c8  mov     [ebp+ppref], esi
0x100579cb  xor     edx, edx; pref
0x100579cd  mov     ecx, esi; ppref
0x100579cf  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x100579d4  push    esi; ppDtsReader
0x100579d5  mov     ecx, edi; this
0x100579d7  call    ?CreateDTSReader@SAXReader@@IAEJPAPAVDTSReader@@@Z; SAXReader::CreateDTSReader(DTSReader * *)
0x100579dc  mov     esi, eax
0x100579de  mov     [ebp+hr], esi
0x100579e1  test    esi, esi
0x100579e3  js      loc_100578F4
0x100579e9  mov     byte ptr [edi+570h], 1
0x100579f0  mov     edi, [edi+574h]
0x100579f6  mov     eax, [edi]
0x100579f8  mov     esi, [eax+10h]
0x100579fb  mov     eax, [ebp+_EnsureTls._tlsdata]
0x100579fe  push    eax
0x100579ff  mov     ecx, esi; this
0x10057a01  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10057a07  mov     ecx, edi
0x10057a09  call    esi
0x10057a0b  mov     esi, eax
0x10057a0d  mov     [ebp+hr], esi
0x10057a10  xor     edx, edx; pref
0x10057a12  mov     ecx, [ebp+ppref]; ppref
0x10057a15  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10057a1a  jmp     short loc_10057A3D
0x10057a1c  mov     byte ptr [edi+570h], 1
0x10057a23  sub     esp, 10h
0x10057a26  lea     esi, [ebp+varInput]
0x10057a29  mov     edi, esp
0x10057a2b  movsd
0x10057a2c  movsd
0x10057a2d  movsd
0x10057a2e  movsd
0x10057a2f  mov     ecx, [ebp+this]
0x10057a32  push    ecx; this
0x10057a33  call    ?parse@Reader@@UAGJUtagVARIANT@@@Z; Reader::parse(tagVARIANT)
0x10057a38  mov     esi, eax
0x10057a3a  mov     [ebp+hr], esi
0x10057a3d  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10057a44  jmp     short loc_10057A9E
0x10057a46  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10057a49  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x10057a4e  retn
0x10057a4f  mov     esp, [ebp+ms_exc.old_esp]
0x10057a52  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10057a57  mov     ecx, [ebp+this]
0x10057a5a  add     ecx, 574h; ppref
0x10057a60  xor     edx, edx; pref
0x10057a62  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10057a67  mov     ecx, __tls_index
0x10057a6d  mov     eax, large fs:2Ch
0x10057a73  mov     eax, [eax+ecx*4]
0x10057a76  mov     eax, [eax+4]
0x10057a7c  mov     edi, [eax+8]
0x10057a7f  mov     eax, [edi]
0x10057a81  mov     esi, [eax+34h]
0x10057a84  mov     ecx, esi; this
0x10057a86  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10057a8c  mov     ecx, edi
0x10057a8e  call    esi
0x10057a90  mov     esi, eax
0x10057a92  mov     [ebp+hr], esi
0x10057a95  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10057a9c  xor     ebx, ebx
0x10057a9e  mov     eax, [ebp+this]
0x10057aa1  mov     [eax+570h], bl
0x10057aa7  cmp     [ebp+fClearVariant], 0
0x10057aab  jz      short loc_10057AB7
0x10057aad  lea     eax, [ebp+varInput]
0x10057ab0  push    eax; pvarg
0x10057ab1  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10057ab7  mov     eax, esi
0x10057ab9  mov     ecx, [ebp+ms_exc.registration.Next]
0x10057abc  mov     large fs:0, ecx
0x10057ac3  pop     ecx
0x10057ac4  pop     edi
0x10057ac5  pop     esi
0x10057ac6  pop     ebx
0x10057ac7  leave
0x10057ac8  retn    14h
```
