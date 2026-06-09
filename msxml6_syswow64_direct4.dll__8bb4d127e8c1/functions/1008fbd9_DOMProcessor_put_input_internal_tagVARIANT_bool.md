# DOMProcessor::put_input_internal(tagVARIANT,bool)

- ea: `0x1008fbd9`
- end: `0x1008fdf0`
- name: `?put_input_internal@DOMProcessor@@QAEJUtagVARIANT@@_N@Z`
- size: `535`
- prototype: `HRESULT __thiscall(DOMProcessor *this, tagVARIANT var, bool fInsideWinRT)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x10074350`
- `0x10074480`
- `0x1008fbb0`

## callees

- `0x1003fb13`
- `0x100505bc`
- `0x10064c31`
- `0x10067658`
- `0x10067764`
- `0x10067b20`
- `0x1006bff0`
- `0x10076076`
- `0x100779f5`
- `0x10077a4b`
- `0x100781cb`
- `0x1008c4d9`
- `0x1008edac`
- `0x1008fbd9`
- `0x1008ff60`
- `0x1009016c`
- `0x1009821b`
- `0x1012d384`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1008fd3d`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008fd3d`

## pseudocode

```c
HRESULT __thiscall DOMProcessor::put_input_internal(DOMProcessor *this, tagVARIANT var, bool fInsideWinRT)
{
  DOMProcessor *v3; // edi
  Node *p; // ebx
  Document *v6; // esi
  unsigned __int16 BaseType; // ax
  IUnknown *Unknown; // eax
  bool v9; // al
  Document *v10; // ebx
  unsigned int v11; // eax
  HRESULT v12; // eax
  HRESULT v13; // edi
  IXMLDOMDocument *ppDOMDocument; // [esp+14h] [ebp-2Ch] BYREF
  Document *pDocTemp; // [esp+18h] [ebp-28h]
  Node *eData; // [esp+1Ch] [ebp-24h] BYREF
  HRESULT hr; // [esp+20h] [ebp-20h]
  __int16 isSuccessful; // [esp+24h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+28h] [ebp-18h]

  v3 = this;
  EnsureTls::EnsureTls((EnsureTls *)&eData);
  if ( !eData )
    return -2147467259;
  p = 0;
  eData = 0;
  v6 = 0;
  pDocTemp = 0;
  ms_exc.registration.TryLevel = 0;
  BaseType = Variant::getBaseType(&var);
  if ( BaseType != 13 && BaseType != 9 && BaseType > 1u )
  {
    v9 = 1;
LABEL_9:
    if ( v9 )
    {
      v10 = Document::newDocument();
      pDocTemp = v10;
      COMSafeControlRoot::copySafeControlRoot(&v10->COMSafeControlRoot, &v3->_pTemplate._p->COMSafeControlRoot, 0);
      v11 = v10->_dwFlags & 0xFFFFFFFD;
      v10->_dwFlags = v11;
      v11 &= ~0x40u;
      v10->_dwFlags = v11;
      v10->_dwFlags = v11 & 0xFFFFFFFB;
      v12 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), Document *, GUID *, IXMLDOMDocument **))v10->QueryInterface)(
              v10->QueryInterface,
              v10,
              &IID_IXMLDOMDocument,
              &ppDOMDocument);
      checkhr(v12);
      v13 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLDOMDocument *, tagVARIANT, __int16 *), IXMLDOMDocument *, _DWORD, unsigned int, unsigned int, unsigned int, __int16 *))ppDOMDocument->load)(
              ppDOMDocument->load,
              ppDOMDocument,
              *(_DWORD *)&var.vt,
              var.decVal.Hi32,
              var.decVal.Lo32,
              var.decVal.Mid32,
              &isSuccessful);
      hr = v13;
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IXMLDOMDocument *))ppDOMDocument->Release)(
        ppDOMDocument->Release,
        ppDOMDocument);
      v6 = pDocTemp;
      if ( pDocTemp->_pParseError._p )
      {
        Exception::throwAgain();
        JUMPOUT(0x1008FDDB);
      }
      checkhr(v13);
      p = v6->_pDocNode._p;
      eData = p;
      v3 = this;
    }
    goto LABEL_12;
  }
  Unknown = Variant::getUnknown(&var, 0);
  if ( Unknown )
  {
    v9 = GetElement(Unknown, fInsideWinRT, &eData) < 0;
    p = eData;
    goto LABEL_9;
  }
LABEL_12:
  if ( p )
    DOMProcessor::setLastRequiredEvent(v3);
  else
    DOMProcessor::clearRequiredEvent(v3);
  DOMProcessor::releaseInput(v3);
  hr = VariantCopy(&v3->_varInput, &var);
  if ( hr < 0 )
  {
    DOMProcessor::clearRequiredEvent(v3);
    checkhr(hr);
  }
  assign(&v3->_eInput._p, p);
  hr = 0;
  ms_exc.registration.TryLevel = -2;
  if ( v6 )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), Document *))v6->Release)(v6->Release, v6);
  return 0;
}

```

## disassembly

```asm
0x1008fbd9  push    20h
0x1008fbdb  push    offset stru_10175518
0x1008fbe0  call    __SEH_prolog4
0x1008fbe5  mov     edi, this
0x1008fbe7  mov     [ebp+var_30], edi
0x1008fbea  lea     this, [ebp+eData]; this
0x1008fbed  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x1008fbf2  cmp     [ebp+eData], 0
0x1008fbf6  jnz     short loc_1008FC02
0x1008fbf8  mov     eax, 80004005h
0x1008fbfd  jmp     loc_1008FDC4
0x1008fc02  xor     ebx, ebx
0x1008fc04  mov     [ebp+eData], ebx
0x1008fc07  xor     esi, esi
0x1008fc09  mov     [ebp+pDocTemp], esi
0x1008fc0c  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1008fc0f  lea     this, [ebp+var]; varObject
0x1008fc12  call    ?getBaseType@Variant@@SGGPAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1008fc17  cmp     ax, 0Dh
0x1008fc1b  jz      short loc_1008FC30
0x1008fc1d  cmp     ax, 9
0x1008fc21  jz      short loc_1008FC30
0x1008fc23  xor     this, this
0x1008fc25  inc     this
0x1008fc26  cmp     ax, cx
0x1008fc29  jz      short loc_1008FC30
0x1008fc2b  test    ax, ax
0x1008fc2e  jnz     short loc_1008FC64
0x1008fc30  xor     dl, dl; fRequirePtrType
0x1008fc32  lea     this, [ebp+var]; pVar
0x1008fc35  call    ?getUnknown@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x1008fc3a  test    eax, eax
0x1008fc3c  jz      loc_1008FD1C
0x1008fc42  lea     this, [ebp+eData]
0x1008fc45  push    this; e
0x1008fc46  mov     dl, [ebp+fInsideWinRT]; fInsideWinRT
0x1008fc49  mov     this, eax; p
0x1008fc4b  call    ?GetElement@@YGJPAUIUnknown@@_NPAPAVNode@@@Z; GetElement(IUnknown *,bool,Node * *)
0x1008fc50  xor     edx, edx
0x1008fc52  inc     edx
0x1008fc53  movzx   this, dl
0x1008fc56  xor     edx, edx
0x1008fc58  test    eax, eax
0x1008fc5a  cmovns  this, edx
0x1008fc5d  mov     al, cl
0x1008fc5f  mov     ebx, [ebp+eData]
0x1008fc62  jmp     short loc_1008FC67
0x1008fc64  xor     eax, eax
0x1008fc66  inc     eax
0x1008fc67  test    al, al
0x1008fc69  jz      loc_1008FD1C
0x1008fc6f  call    ?newDocument@Document@@SGPAV1@XZ; Document::newDocument(void)
0x1008fc74  mov     ebx, eax
0x1008fc76  mov     [ebp+pDocTemp], ebx
0x1008fc79  lea     this, [ebx+0Ch]; this
0x1008fc7c  push    0; fNewStrings
0x1008fc7e  mov     edx, [edi+24h]
0x1008fc81  add     edx, 1Ch
0x1008fc84  push    edx; saferoot
0x1008fc85  call    ?copySafeControlRoot@COMSafeControlRoot@@QAEXABV1@_N@Z; COMSafeControlRoot::copySafeControlRoot(COMSafeControlRoot const &,bool)
0x1008fc8a  mov     eax, [ebx+50h]
0x1008fc8d  and     eax, 0FFFFFFFDh
0x1008fc90  mov     [ebx+50h], eax
0x1008fc93  and     eax, 0FFFFFFBFh
0x1008fc96  mov     [ebx+50h], eax
0x1008fc99  and     eax, 0FFFFFFFBh
0x1008fc9c  mov     [ebx+50h], eax
0x1008fc9f  mov     eax, [ebx]
0x1008fca1  mov     esi, [eax]
0x1008fca3  lea     eax, [ebp+ppDOMDocument]
0x1008fca6  push    eax
0x1008fca7  push    offset _IID_IXMLDOMDocument
0x1008fcac  push    ebx
0x1008fcad  mov     this, esi; this
0x1008fcaf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fcb5  call    esi
0x1008fcb7  mov     this, eax; hr
0x1008fcb9  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008fcbe  mov     this, [ebp+ppDOMDocument]
0x1008fcc1  mov     eax, [this]
0x1008fcc3  mov     ebx, [eax+0E8h]
0x1008fcc9  lea     eax, [ebp+isSuccessful]
0x1008fccc  push    eax
0x1008fccd  sub     esp, 10h
0x1008fcd0  lea     esi, [ebp+var]
0x1008fcd3  mov     edi, esp
0x1008fcd5  movsd
0x1008fcd6  movsd
0x1008fcd7  movsd
0x1008fcd8  movsd
0x1008fcd9  push    this
0x1008fcda  mov     this, ebx; this
0x1008fcdc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fce2  call    ebx
0x1008fce4  mov     edi, eax
0x1008fce6  mov     [ebp+hr], edi
0x1008fce9  mov     this, [ebp+ppDOMDocument]
0x1008fcec  mov     edx, [this]
0x1008fcee  push    this
0x1008fcef  mov     esi, [edx+8]
0x1008fcf2  mov     this, esi; this
0x1008fcf4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fcfa  call    esi
0x1008fcfc  mov     esi, [ebp+pDocTemp]
0x1008fcff  cmp     dword ptr [esi+80h], 0
0x1008fd06  jnz     loc_1008FDD6
0x1008fd0c  mov     this, edi; hr
0x1008fd0e  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008fd13  mov     ebx, [esi+70h]
0x1008fd16  mov     [ebp+eData], ebx
0x1008fd19  mov     edi, [ebp+var_30]
0x1008fd1c  mov     this, edi; this
0x1008fd1e  test    ebx, ebx
0x1008fd20  jz      short loc_1008FD29
0x1008fd22  call    ?setLastRequiredEvent@DOMProcessor@@IAEXXZ; DOMProcessor::setLastRequiredEvent(void)
0x1008fd27  jmp     short loc_1008FD2E
0x1008fd29  call    ?clearRequiredEvent@DOMProcessor@@IAEXXZ; DOMProcessor::clearRequiredEvent(void)
0x1008fd2e  mov     this, edi; this
0x1008fd30  call    ?releaseInput@DOMProcessor@@IAEXXZ; DOMProcessor::releaseInput(void)
0x1008fd35  lea     eax, [ebp+var]
0x1008fd38  push    eax; pvargSrc
0x1008fd39  lea     eax, [edi+58h]
0x1008fd3c  push    eax; pvargDest
0x1008fd3d  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1008fd43  mov     [ebp+hr], eax
0x1008fd46  test    eax, eax
0x1008fd48  jns     short loc_1008FD59
0x1008fd4a  mov     this, edi; this
0x1008fd4c  call    ?clearRequiredEvent@DOMProcessor@@IAEXXZ; DOMProcessor::clearRequiredEvent(void)
0x1008fd51  mov     this, [ebp+hr]; hr
0x1008fd54  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008fd59  lea     this, [edi+50h]; ppref
0x1008fd5c  mov     edx, ebx; pref
0x1008fd5e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008fd63  xor     edi, edi
0x1008fd65  mov     [ebp+hr], edi
0x1008fd68  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1008fd6f  jmp     short loc_1008FDAE
0x1008fd71  mov     this, [ebp+ms_exc.exc_ptr]; ep
0x1008fd74  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1008fd79  retn
0x1008fd7a  mov     esp, [ebp+ms_exc.old_esp]
0x1008fd7d  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1008fd82  mov     this, __tls_index
0x1008fd88  mov     eax, large fs:2Ch
0x1008fd8e  mov     eax, [eax+this*4]
0x1008fd91  mov     eax, [eax+4]
0x1008fd97  mov     this, [eax+8]; e
0x1008fd9a  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1008fd9f  mov     edi, eax
0x1008fda1  mov     [ebp+hr], edi
0x1008fda4  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1008fdab  mov     esi, [ebp+pDocTemp]
0x1008fdae  test    esi, esi
0x1008fdb0  jz      short loc_1008FDC2
0x1008fdb2  mov     eax, [esi]
0x1008fdb4  push    esi
0x1008fdb5  mov     esi, [eax+8]
0x1008fdb8  mov     this, esi; this
0x1008fdba  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fdc0  call    esi
0x1008fdc2  mov     eax, edi
0x1008fdc4  mov     this, [ebp+ms_exc.registration.Next]
0x1008fdc7  mov     large fs:0, this
0x1008fdce  pop     this
0x1008fdcf  pop     edi
0x1008fdd0  pop     esi
0x1008fdd1  pop     ebx
0x1008fdd2  leave
0x1008fdd3  retn    14h
0x1008fdd6  call    ?throwAgain@Exception@@SGXXZ; Exception::throwAgain(void)
```
