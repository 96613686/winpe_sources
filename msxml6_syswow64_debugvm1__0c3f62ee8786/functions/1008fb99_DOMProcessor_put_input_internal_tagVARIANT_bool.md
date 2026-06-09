# DOMProcessor::put_input_internal(tagVARIANT,bool)

- ea: `0x1008fb99`
- end: `0x1008fdb0`
- name: `?put_input_internal@DOMProcessor@@QAEJUtagVARIANT@@_N@Z`
- size: `535`
- prototype: `HRESULT __thiscall(DOMProcessor *this, tagVARIANT var, bool fInsideWinRT)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x10074320`
- `0x10074450`
- `0x1008fb70`

## callees

- `0x1003fba3`
- `0x1005064c`
- `0x10064cd1`
- `0x100676f8`
- `0x10067804`
- `0x10067bc0`
- `0x1006c080`
- `0x10076046`
- `0x100779c5`
- `0x10077a1b`
- `0x1007818b`
- `0x1008c499`
- `0x1008ed6c`
- `0x1008fb99`
- `0x1008ff20`
- `0x1009012c`
- `0x1009815b`
- `0x1012d274`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x1008fcfd`
- `OLEAUT32!__imp__VariantCopy@8` at `0x1008fcfd`

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
        JUMPOUT(0x1008FD9B);
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
0x1008fb99  push    20h
0x1008fb9b  push    offset stru_10175428
0x1008fba0  call    __SEH_prolog4
0x1008fba5  mov     edi, this
0x1008fba7  mov     [ebp+var_30], edi
0x1008fbaa  lea     this, [ebp+eData]; this
0x1008fbad  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x1008fbb2  cmp     [ebp+eData], 0
0x1008fbb6  jnz     short loc_1008FBC2
0x1008fbb8  mov     eax, 80004005h
0x1008fbbd  jmp     loc_1008FD84
0x1008fbc2  xor     ebx, ebx
0x1008fbc4  mov     [ebp+eData], ebx
0x1008fbc7  xor     esi, esi
0x1008fbc9  mov     [ebp+pDocTemp], esi
0x1008fbcc  mov     [ebp+ms_exc.registration.TryLevel], ebx
0x1008fbcf  lea     this, [ebp+var]; varObject
0x1008fbd2  call    ?getBaseType@Variant@@SGGPAUtagVARIANT@@@Z; Variant::getBaseType(tagVARIANT *)
0x1008fbd7  cmp     ax, 0Dh
0x1008fbdb  jz      short loc_1008FBF0
0x1008fbdd  cmp     ax, 9
0x1008fbe1  jz      short loc_1008FBF0
0x1008fbe3  xor     this, this
0x1008fbe5  inc     this
0x1008fbe6  cmp     ax, cx
0x1008fbe9  jz      short loc_1008FBF0
0x1008fbeb  test    ax, ax
0x1008fbee  jnz     short loc_1008FC24
0x1008fbf0  xor     dl, dl; fRequirePtrType
0x1008fbf2  lea     this, [ebp+var]; pVar
0x1008fbf5  call    ?getUnknown@Variant@@SGPAUIUnknown@@PAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x1008fbfa  test    eax, eax
0x1008fbfc  jz      loc_1008FCDC
0x1008fc02  lea     this, [ebp+eData]
0x1008fc05  push    this; e
0x1008fc06  mov     dl, [ebp+fInsideWinRT]; fInsideWinRT
0x1008fc09  mov     this, eax; p
0x1008fc0b  call    ?GetElement@@YGJPAUIUnknown@@_NPAPAVNode@@@Z; GetElement(IUnknown *,bool,Node * *)
0x1008fc10  xor     edx, edx
0x1008fc12  inc     edx
0x1008fc13  movzx   this, dl
0x1008fc16  xor     edx, edx
0x1008fc18  test    eax, eax
0x1008fc1a  cmovns  this, edx
0x1008fc1d  mov     al, cl
0x1008fc1f  mov     ebx, [ebp+eData]
0x1008fc22  jmp     short loc_1008FC27
0x1008fc24  xor     eax, eax
0x1008fc26  inc     eax
0x1008fc27  test    al, al
0x1008fc29  jz      loc_1008FCDC
0x1008fc2f  call    ?newDocument@Document@@SGPAV1@XZ; Document::newDocument(void)
0x1008fc34  mov     ebx, eax
0x1008fc36  mov     [ebp+pDocTemp], ebx
0x1008fc39  lea     this, [ebx+0Ch]; this
0x1008fc3c  push    0; fNewStrings
0x1008fc3e  mov     edx, [edi+24h]
0x1008fc41  add     edx, 1Ch
0x1008fc44  push    edx; saferoot
0x1008fc45  call    ?copySafeControlRoot@COMSafeControlRoot@@QAEXABV1@_N@Z; COMSafeControlRoot::copySafeControlRoot(COMSafeControlRoot const &,bool)
0x1008fc4a  mov     eax, [ebx+50h]
0x1008fc4d  and     eax, 0FFFFFFFDh
0x1008fc50  mov     [ebx+50h], eax
0x1008fc53  and     eax, 0FFFFFFBFh
0x1008fc56  mov     [ebx+50h], eax
0x1008fc59  and     eax, 0FFFFFFFBh
0x1008fc5c  mov     [ebx+50h], eax
0x1008fc5f  mov     eax, [ebx]
0x1008fc61  mov     esi, [eax]
0x1008fc63  lea     eax, [ebp+ppDOMDocument]
0x1008fc66  push    eax
0x1008fc67  push    offset _IID_IXMLDOMDocument
0x1008fc6c  push    ebx
0x1008fc6d  mov     this, esi; this
0x1008fc6f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fc75  call    esi
0x1008fc77  mov     this, eax; hr
0x1008fc79  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008fc7e  mov     this, [ebp+ppDOMDocument]
0x1008fc81  mov     eax, [this]
0x1008fc83  mov     ebx, [eax+0E8h]
0x1008fc89  lea     eax, [ebp+isSuccessful]
0x1008fc8c  push    eax
0x1008fc8d  sub     esp, 10h
0x1008fc90  lea     esi, [ebp+var]
0x1008fc93  mov     edi, esp
0x1008fc95  movsd
0x1008fc96  movsd
0x1008fc97  movsd
0x1008fc98  movsd
0x1008fc99  push    this
0x1008fc9a  mov     this, ebx; this
0x1008fc9c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fca2  call    ebx
0x1008fca4  mov     edi, eax
0x1008fca6  mov     [ebp+hr], edi
0x1008fca9  mov     this, [ebp+ppDOMDocument]
0x1008fcac  mov     edx, [this]
0x1008fcae  push    this
0x1008fcaf  mov     esi, [edx+8]
0x1008fcb2  mov     this, esi; this
0x1008fcb4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fcba  call    esi
0x1008fcbc  mov     esi, [ebp+pDocTemp]
0x1008fcbf  cmp     dword ptr [esi+80h], 0
0x1008fcc6  jnz     loc_1008FD96
0x1008fccc  mov     this, edi; hr
0x1008fcce  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008fcd3  mov     ebx, [esi+70h]
0x1008fcd6  mov     [ebp+eData], ebx
0x1008fcd9  mov     edi, [ebp+var_30]
0x1008fcdc  mov     this, edi; this
0x1008fcde  test    ebx, ebx
0x1008fce0  jz      short loc_1008FCE9
0x1008fce2  call    ?setLastRequiredEvent@DOMProcessor@@IAEXXZ; DOMProcessor::setLastRequiredEvent(void)
0x1008fce7  jmp     short loc_1008FCEE
0x1008fce9  call    ?clearRequiredEvent@DOMProcessor@@IAEXXZ; DOMProcessor::clearRequiredEvent(void)
0x1008fcee  mov     this, edi; this
0x1008fcf0  call    ?releaseInput@DOMProcessor@@IAEXXZ; DOMProcessor::releaseInput(void)
0x1008fcf5  lea     eax, [ebp+var]
0x1008fcf8  push    eax; pvargSrc
0x1008fcf9  lea     eax, [edi+58h]
0x1008fcfc  push    eax; pvargDest
0x1008fcfd  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x1008fd03  mov     [ebp+hr], eax
0x1008fd06  test    eax, eax
0x1008fd08  jns     short loc_1008FD19
0x1008fd0a  mov     this, edi; this
0x1008fd0c  call    ?clearRequiredEvent@DOMProcessor@@IAEXXZ; DOMProcessor::clearRequiredEvent(void)
0x1008fd11  mov     this, [ebp+hr]; hr
0x1008fd14  call    ?checkhr@@YGXJ@Z; checkhr(long)
0x1008fd19  lea     this, [edi+50h]; ppref
0x1008fd1c  mov     edx, ebx; pref
0x1008fd1e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1008fd23  xor     edi, edi
0x1008fd25  mov     [ebp+hr], edi
0x1008fd28  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1008fd2f  jmp     short loc_1008FD6E
0x1008fd31  mov     this, [ebp+ms_exc.exc_ptr]; ep
0x1008fd34  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1008fd39  retn
0x1008fd3a  mov     esp, [ebp+ms_exc.old_esp]
0x1008fd3d  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x1008fd42  mov     this, __tls_index
0x1008fd48  mov     eax, large fs:2Ch
0x1008fd4e  mov     eax, [eax+this*4]
0x1008fd51  mov     eax, [eax+4]
0x1008fd57  mov     this, [eax+8]; e
0x1008fd5a  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1008fd5f  mov     edi, eax
0x1008fd61  mov     [ebp+hr], edi
0x1008fd64  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1008fd6b  mov     esi, [ebp+pDocTemp]
0x1008fd6e  test    esi, esi
0x1008fd70  jz      short loc_1008FD82
0x1008fd72  mov     eax, [esi]
0x1008fd74  push    esi
0x1008fd75  mov     esi, [eax+8]
0x1008fd78  mov     this, esi; this
0x1008fd7a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1008fd80  call    esi
0x1008fd82  mov     eax, edi
0x1008fd84  mov     this, [ebp+ms_exc.registration.Next]
0x1008fd87  mov     large fs:0, this
0x1008fd8e  pop     this
0x1008fd8f  pop     edi
0x1008fd90  pop     esi
0x1008fd91  pop     ebx
0x1008fd92  leave
0x1008fd93  retn    14h
0x1008fd96  call    ?throwAgain@Exception@@SGXXZ; Exception::throwAgain(void)
```
