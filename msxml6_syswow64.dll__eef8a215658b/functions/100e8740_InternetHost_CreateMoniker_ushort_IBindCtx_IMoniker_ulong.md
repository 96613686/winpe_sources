# InternetHost::CreateMoniker(ushort *,IBindCtx *,IMoniker * *,ulong)

- ea: `0x100e8740`
- end: `0x100e882c`
- name: `?CreateMoniker@InternetHost@@UAGJPAGPAUIBindCtx@@PAPAUIMoniker@@K@Z`
- size: `236`
- prototype: `HRESULT __stdcall(InternetHost *this, wchar_t *szName, IBindCtx *pBC, IMoniker **ppmk, unsigned int dwReserved)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x100505bc`
- `0x10067b20`
- `0x1006bff0`
- `0x100779f5`
- `0x10077a4b`
- `0x100e8740`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x100e87c9`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x100e87c9`
- `urlmon!CreateURLMonikerEx` at `0x100e87a8`
- `urlmon!CreateURLMonikerEx` at `0x100e87be`
- `urlmon!CreateURLMonikerEx` at `0x100e87a8`
- `urlmon!CreateURLMonikerEx` at `0x100e87be`

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
0x100e8740  push    14h
0x100e8742  push    offset stru_101798B8
0x100e8747  call    __SEH_prolog4
0x100e874c  mov     esi, [ebp+ppmk]
0x100e874f  test    esi, esi
0x100e8751  jnz     short loc_100E875D
0x100e8753  mov     eax, 80004003h
0x100e8758  jmp     loc_100E881A
0x100e875d  xor     edi, edi
0x100e875f  mov     [esi], edi
0x100e8761  mov     [ebp+pmkBase], edi
0x100e8764  mov     ebx, [ebp+szName]
0x100e8767  test    ebx, ebx
0x100e8769  jnz     short loc_100E8775
0x100e876b  mov     eax, 80070057h
0x100e8770  jmp     loc_100E881A
0x100e8775  lea     ecx, [ebp+_EnsureTls]; this
0x100e8778  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100e877d  cmp     [ebp+_EnsureTls._tlsdata], edi
0x100e8780  jnz     short loc_100E878C
0x100e8782  mov     eax, 80004005h
0x100e8787  jmp     loc_100E881A
0x100e878c  mov     [ebp+ms_exc.registration.TryLevel], edi
0x100e878f  mov     eax, [ebp+this]
0x100e8792  mov     eax, [eax+14h]
0x100e8795  test    eax, eax
0x100e8797  jz      short loc_100E87C8
0x100e8799  cmp     [eax+8], edi
0x100e879c  jz      short loc_100E87C8
0x100e879e  push    1; dwFlags
0x100e87a0  lea     ecx, [ebp+pmkBase]
0x100e87a3  push    ecx; ppmk
0x100e87a4  push    dword ptr [eax+0Ch]; szURL
0x100e87a7  push    edi; pMkCtx
0x100e87a8  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x100e87ae  mov     edi, eax
0x100e87b0  mov     [ebp+hr], edi
0x100e87b3  test    edi, edi
0x100e87b5  js      short loc_100E87FA
0x100e87b7  push    1; dwFlags
0x100e87b9  push    esi; ppmk
0x100e87ba  push    ebx; szURL
0x100e87bb  push    [ebp+pmkBase]; pMkCtx
0x100e87be  call    ds:__imp__CreateURLMonikerEx@16; CreateURLMonikerEx(x,x,x,x)
0x100e87c4  mov     edi, eax
0x100e87c6  jmp     short loc_100E87F7
0x100e87c8  push    ebx; pszPath
0x100e87c9  call    ds:__imp__PathIsURLW@4; PathIsURLW(x)
0x100e87cf  test    eax, eax
0x100e87d1  jz      short loc_100E87DA
0x100e87d3  push    1
0x100e87d5  push    esi
0x100e87d6  push    ebx
0x100e87d7  push    edi
0x100e87d8  jmp     short loc_100E87BE
0x100e87da  mov     edi, 80070057h
0x100e87df  jmp     short loc_100E87F7
0x100e87e1  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100e87e4  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100e87e9  retn
0x100e87ea  mov     esp, [ebp+ms_exc.old_esp]
0x100e87ed  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100e87f2  mov     edi, 80004005h
0x100e87f7  mov     [ebp+hr], edi
0x100e87fa  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100e8801  mov     ecx, [ebp+pmkBase]
0x100e8804  test    ecx, ecx
0x100e8806  jz      short loc_100E8818
0x100e8808  mov     eax, [ecx]
0x100e880a  push    ecx
0x100e880b  mov     esi, [eax+8]
0x100e880e  mov     ecx, esi; this
0x100e8810  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100e8816  call    esi
0x100e8818  mov     eax, edi
0x100e881a  mov     ecx, [ebp+ms_exc.registration.Next]
0x100e881d  mov     large fs:0, ecx
0x100e8824  pop     ecx
0x100e8825  pop     edi
0x100e8826  pop     esi
0x100e8827  pop     ebx
0x100e8828  leave
0x100e8829  retn    14h
```
