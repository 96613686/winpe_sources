# DOMDocumentWrapper::put_onreadystatechange(tagVARIANT)

- ea: `0x100963e0`
- end: `0x10096488`
- name: `?put_onreadystatechange@DOMDocumentWrapper@@UAGJUtagVARIANT@@@Z`
- size: `168`
- prototype: `HRESULT __stdcall(DOMDocumentWrapper *this, tagVARIANT varFn)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1005064c`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x1008d26d`
- `0x10091363`
- `0x100963e0`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x10096405`
- `OLEAUT32!__imp__VariantInit@4` at `0x10096405`
- `OLEAUT32!__imp__VariantClear@4` at `0x1009646e`
- `OLEAUT32!__imp__VariantClear@4` at `0x1009646e`
- `OLEAUT32!__imp__VariantChangeType@16` at `0x1009641e`
- `OLEAUT32!__imp__VariantChangeType@16` at `0x1009641e`

## string_xrefs

- `0x10096454`: `onreadystatechange`

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
0x100963e0  push    20h
0x100963e2  push    offset stru_10175650
0x100963e7  call    __SEH_prolog4
0x100963ec  lea     ecx, [ebp+_EnsureTls]; this
0x100963ef  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100963f4  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100963f8  jnz     short loc_10096401
0x100963fa  mov     eax, 80004005h
0x100963ff  jmp     short loc_10096476
0x10096401  lea     eax, [ebp+varTemp]
0x10096404  push    eax; pvarg
0x10096405  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1009640b  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10096412  push    9; vt
0x10096414  push    1; wFlags
0x10096416  lea     eax, [ebp+varFn]
0x10096419  push    eax; pvarSrc
0x1009641a  lea     eax, [ebp+varTemp]
0x1009641d  push    eax; pvargDest
0x1009641e  call    ds:__imp__VariantChangeType@16; VariantChangeType(x,x,x,x)
0x10096424  mov     esi, eax
0x10096426  mov     [ebp+hr], esi
0x10096429  test    esi, esi
0x1009642b  js      short loc_10096463
0x1009642d  mov     ecx, [ebp+this]
0x10096430  mov     ecx, [ecx+18h]
0x10096433  add     ecx, 0DCh; this
0x10096439  push    dword ptr [ebp+varTemp.___u0+8]; ptr
0x1009643c  call    ?setPointer@?$_gitpointer@UIDispatch@@$1?IID_IDispatch@@3U_GUID@@B@@QAEXPAUIDispatch@@@Z; _gitpointer<IDispatch,&_GUID const IID_IDispatch>::setPointer(IDispatch *)
0x10096441  jmp     short loc_10096463
0x10096443  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10096446  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x1009644b  retn
0x1009644c  mov     esp, [ebp+ms_exc.old_esp]
0x1009644f  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10096454  mov     ecx, offset aOnreadystatech; "onreadystatechange"
0x10096459  call    ?BadEventSinkException@@YGJPBG@Z; BadEventSinkException(ushort const *)
0x1009645e  mov     esi, eax
0x10096460  mov     [ebp+hr], esi
0x10096463  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1009646a  lea     eax, [ebp+varTemp]
0x1009646d  push    eax; pvarg
0x1009646e  call    ds:__imp__VariantClear@4; VariantClear(x)
0x10096474  mov     eax, esi
0x10096476  mov     ecx, [ebp+ms_exc.registration.Next]
0x10096479  mov     large fs:0, ecx
0x10096480  pop     ecx
0x10096481  pop     edi
0x10096482  pop     esi
0x10096483  pop     ebx
0x10096484  leave
0x10096485  retn    14h
```
