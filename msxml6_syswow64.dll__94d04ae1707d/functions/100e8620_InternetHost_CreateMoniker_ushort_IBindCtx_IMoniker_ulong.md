# InternetHost::CreateMoniker(ushort *,IBindCtx *,IMoniker * *,ulong)

- ea: `0x100e8620`
- end: `0x100e870c`
- name: `?CreateMoniker@InternetHost@@UAGJPAGPAUIBindCtx@@PAPAUIMoniker@@K@Z`
- size: `236`
- prototype: `HRESULT __stdcall(InternetHost *this, wchar_t *szName, IBindCtx *pBC, IMoniker **ppmk, unsigned int dwReserved)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1005064c`
- `0x10067bc0`
- `0x1006c080`
- `0x100779c5`
- `0x10077a1b`
- `0x100e8620`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x100e86a9`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x100e86a9`
- `urlmon!CreateURLMonikerEx` at `0x100e8688`
- `urlmon!CreateURLMonikerEx` at `0x100e869e`
- `urlmon!CreateURLMonikerEx` at `0x100e8688`
- `urlmon!CreateURLMonikerEx` at `0x100e869e`

## pseudocode

```c
HRESULT __stdcall InternetHost::CreateMoniker(
        InternetHost *this,
        wchar_t *szName,
        IBindCtx *pBC,
        IMoniker **ppmk,
        unsigned int dwReserved)
{
  HostSecurityMgrWrapper *p; // eax
  int v7; // edi
  HRESULT URLMoniker; // eax
  EnsureTls _EnsureTls; // [esp+10h] [ebp-24h] BYREF
  IMoniker *pmkBase; // [esp+14h] [ebp-20h] BYREF
  HRESULT hr; // [esp+18h] [ebp-1Ch]
  CPPEH_RECORD ms_exc; // [esp+1Ch] [ebp-18h]

  if ( !ppmk )
    return -2147467261;
  *ppmk = 0;
  pmkBase = 0;
  if ( !szName )
    return -2147024809;
  EnsureTls::EnsureTls(&_EnsureTls);
  if ( !_EnsureTls._tlsdata )
    return -2147467259;
  ms_exc.registration.TryLevel = 0;
  p = this->_pIHostSecMgr._p;
  if ( !p || !p->_lRefs )
  {
    if ( !PathIsURLW(szName) )
    {
      v7 = -2147024809;
      goto LABEL_15;
    }
    URLMoniker = CreateURLMonikerEx(0, szName, ppmk, 1u);
LABEL_11:
    v7 = URLMoniker;
LABEL_15:
    hr = v7;
    goto LABEL_16;
  }
  v7 = CreateURLMonikerEx(0, (LPCWSTR)p->_riid, &pmkBase, 1u);
  hr = v7;
  if ( v7 >= 0 )
  {
    URLMoniker = CreateURLMonikerEx(pmkBase, szName, ppmk, 1u);
    goto LABEL_11;
  }
LABEL_16:
  ms_exc.registration.TryLevel = -2;
  if ( pmkBase )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMoniker *))pmkBase->Release)(
      pmkBase->Release,
      pmkBase);
  return v7;
}

```

## disassembly

```asm
0x100e8620  push    14h
0x100e8622  push    offset stru_101797C8
0x100e8627  call    __SEH_prolog4
0x100e862c  mov     esi, [ebp+ppmk]
0x100e862f  test    esi, esi
0x100e8631  jnz     short loc_100E863D
0x100e8633  mov     eax, 80004003h
0x100e8638  jmp     loc_100E86FA
0x100e863d  xor     edi, edi
0x100e863f  mov     [esi], edi
0x100e8641  mov     [ebp+pmkBase], edi
0x100e8644  mov     ebx, [ebp+szName]
0x100e8647  test    ebx, ebx
0x100e8649  jnz     short loc_100E8655
0x100e864b  mov     eax, 80070057h
0x100e8650  jmp     loc_100E86FA
0x100e8655  lea     ecx, [ebp+_EnsureTls]; this
0x100e8658  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100e865d  cmp     [ebp+_EnsureTls._tlsdata], edi
0x100e8660  jnz     short loc_100E866C
0x100e8662  mov     eax, 80004005h
0x100e8667  jmp     loc_100E86FA
0x100e866c  mov     [ebp+ms_exc.registration.TryLevel], edi
0x100e866f  mov     eax, [ebp+this]
0x100e8672  mov     eax, [eax+14h]
0x100e8675  test    eax, eax
0x100e8677  jz      short loc_100E86A8
0x100e8679  cmp     [eax+8], edi
0x100e867c  jz      short loc_100E86A8
0x100e867e  push    1; dwFlags
0x100e8680  lea     ecx, [ebp+pmkBase]
0x100e8683  push    ecx; ppmk
0x100e8684  push    dword ptr [eax+0Ch]; szURL
0x100e8687  push    edi; pMkCtx
0x100e8688  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x100e868e  mov     edi, eax
0x100e8690  mov     [ebp+hr], edi
0x100e8693  test    edi, edi
0x100e8695  js      short loc_100E86DA
0x100e8697  push    1; dwFlags
0x100e8699  push    esi; ppmk
0x100e869a  push    ebx; szURL
0x100e869b  push    [ebp+pmkBase]; pMkCtx
0x100e869e  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x100e86a4  mov     edi, eax
0x100e86a6  jmp     short loc_100E86D7
0x100e86a8  push    ebx; pszPath
0x100e86a9  call    ds:__imp__PathIsURLW@4; PathIsURLW(x)
0x100e86af  test    eax, eax
0x100e86b1  jz      short loc_100E86BA
0x100e86b3  push    1
0x100e86b5  push    esi
0x100e86b6  push    ebx
0x100e86b7  push    edi
0x100e86b8  jmp     short loc_100E869E
0x100e86ba  mov     edi, 80070057h
0x100e86bf  jmp     short loc_100E86D7
0x100e86c1  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100e86c4  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100e86c9  retn
0x100e86ca  mov     esp, [ebp+ms_exc.old_esp]
0x100e86cd  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100e86d2  mov     edi, 80004005h
0x100e86d7  mov     [ebp+hr], edi
0x100e86da  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100e86e1  mov     ecx, [ebp+pmkBase]
0x100e86e4  test    ecx, ecx
0x100e86e6  jz      short loc_100E86F8
0x100e86e8  mov     eax, [ecx]
0x100e86ea  push    ecx
0x100e86eb  mov     esi, [eax+8]
0x100e86ee  mov     ecx, esi; this
0x100e86f0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e86f6  call    esi
0x100e86f8  mov     eax, edi
0x100e86fa  mov     ecx, [ebp+ms_exc.registration.Next]
0x100e86fd  mov     large fs:0, ecx
0x100e8704  pop     ecx
0x100e8705  pop     edi
0x100e8706  pop     esi
0x100e8707  pop     ebx
0x100e8708  leave
0x100e8709  retn    14h
```
