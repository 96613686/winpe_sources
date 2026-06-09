# DOMDocumentWrapper::put_onreadystatechange(tagVARIANT)

- ea: `0x100964a0`
- end: `0x10096548`
- name: `?put_onreadystatechange@DOMDocumentWrapper@@UAGJUtagVARIANT@@@Z`
- size: `168`
- prototype: `HRESULT __stdcall(DOMDocumentWrapper *this, tagVARIANT varFn)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x100505bc`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x1008d2ad`
- `0x10091433`
- `0x100964a0`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x100964c5`
- `OLEAUT32!__imp__VariantInit@4` at `0x100964c5`
- `OLEAUT32!__imp__VariantClear@4` at `0x1009652e`
- `OLEAUT32!__imp__VariantClear@4` at `0x1009652e`
- `OLEAUT32!__imp__VariantChangeType@16` at `0x100964de`
- `OLEAUT32!__imp__VariantChangeType@16` at `0x100964de`

## string_xrefs

- `0x10096514`: `onreadystatechange`

## pseudocode

```c
HRESULT __stdcall DOMDocumentWrapper::put_onreadystatechange(DOMDocumentWrapper *this, tagVARIANT varFn)
{
  int v3; // esi
  tagVARIANT varTemp; // [esp+10h] [ebp-30h] BYREF
  HRESULT hr; // [esp+20h] [ebp-20h]
  EnsureTls _EnsureTls; // [esp+24h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+28h] [ebp-18h]

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( _EnsureTls._tlsdata )
  {
    VariantInit(&varTemp);
    ms_exc.registration.TryLevel = 0;
    v3 = VariantChangeType(&varTemp, &varFn, 1u, 9u);
    hr = v3;
    if ( v3 >= 0 )
      _gitpointer<IDispatch,&_GUID const IID_IDispatch>::setPointer(
        (_gitpointer<IDispatch,&IID_IDispatch> *)&this->_pWrapped._p[55],
        varTemp.pdispVal);
    ms_exc.registration.TryLevel = -2;
    VariantClear(&varTemp);
    return v3;
  }
  else
  {
    return -2147467259;
  }
}

```

## disassembly

```asm
0x100964a0  push    20h
0x100964a2  push    offset stru_10175740
0x100964a7  call    __SEH_prolog4
0x100964ac  lea     ecx, [ebp+_EnsureTls]; this
0x100964af  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100964b4  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100964b8  jnz     short loc_100964C1
0x100964ba  mov     eax, 80004005h
0x100964bf  jmp     short loc_10096536
0x100964c1  lea     eax, [ebp+varTemp]
0x100964c4  push    eax; pvarg
0x100964c5  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100964cb  mov     [ebp+ms_exc.registration.TryLevel], 0
0x100964d2  push    9; vt
0x100964d4  push    1; wFlags
0x100964d6  lea     eax, [ebp+varFn]
0x100964d9  push    eax; pvarSrc
0x100964da  lea     eax, [ebp+varTemp]
0x100964dd  push    eax; pvargDest
0x100964de  call    ds:__imp__VariantChangeType@16; VariantChangeType(x,x,x,x)
0x100964e4  mov     esi, eax
0x100964e6  mov     [ebp+hr], esi
0x100964e9  test    esi, esi
0x100964eb  js      short loc_10096523
0x100964ed  mov     ecx, [ebp+this]
0x100964f0  mov     ecx, [ecx+18h]
0x100964f3  add     ecx, 0DCh; this
0x100964f9  push    dword ptr [ebp+varTemp.___u0+8]; ptr
0x100964fc  call    ?setPointer@?$_gitpointer@UIDispatch@@$1?IID_IDispatch@@3U_GUID@@B@@QAEXPAUIDispatch@@@Z; _gitpointer<IDispatch,&_GUID const IID_IDispatch>::setPointer(IDispatch *)
0x10096501  jmp     short loc_10096523
0x10096503  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10096506  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1009650b  retn
0x1009650c  mov     esp, [ebp+ms_exc.old_esp]
0x1009650f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10096514  mov     ecx, offset aOnreadystatech; "onreadystatechange"
0x10096519  call    ?BadEventSinkException@@YGJPBG@Z; BadEventSinkException(ushort const *)
0x1009651e  mov     esi, eax
0x10096520  mov     [ebp+hr], esi
0x10096523  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1009652a  lea     eax, [ebp+varTemp]
0x1009652d  push    eax; pvarg
0x1009652e  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10096534  mov     eax, esi
0x10096536  mov     ecx, [ebp+ms_exc.registration.Next]
0x10096539  mov     large fs:0, ecx
0x10096540  pop     ecx
0x10096541  pop     edi
0x10096542  pop     esi
0x10096543  pop     ebx
0x10096544  leave
0x10096545  retn    14h
```
