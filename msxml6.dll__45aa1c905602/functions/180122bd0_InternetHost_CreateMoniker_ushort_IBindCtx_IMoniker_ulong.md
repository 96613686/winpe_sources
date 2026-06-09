# InternetHost::CreateMoniker(ushort *,IBindCtx *,IMoniker * *,ulong)

- ea: `0x180122bd0`
- end: `0x180122ce6`
- name: `?CreateMoniker@InternetHost@@UEAAJPEAGPEAUIBindCtx@@PEAPEAUIMoniker@@K@Z`
- size: `278`
- prototype: `HRESULT __fastcall(InternetHost *this, wchar_t *szName, IBindCtx *pBC, IMoniker **ppmk, unsigned int dwReserved)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180058ef4`
- `0x18009fefc`
- `0x1800a3c08`
- `0x180122bd0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180122c72`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180122c72`
- `urlmon!CreateURLMonikerEx` at `0x180122c52`
- `urlmon!CreateURLMonikerEx` at `0x180122c90`
- `urlmon!CreateURLMonikerEx` at `0x180122c52`
- `urlmon!CreateURLMonikerEx` at `0x180122c90`

## pseudocode

```c
__int64 __fastcall InternetHost::CreateMoniker(InternetHost *this, wchar_t *szName, IBindCtx *pBC, IMoniker **ppmk)
{
  HostSecurityMgrWrapper *p; // rdx
  HRESULT URLMoniker; // ebx
  IMoniker *v10; // rcx
  EnsureTls _EnsureTls; // [rsp+28h] [rbp-10h] BYREF
  IMoniker *pmkBase; // [rsp+58h] [rbp+20h] BYREF

  if ( !ppmk )
    return 2147500035LL;
  *ppmk = 0;
  pmkBase = 0;
  if ( !szName )
    return 2147942487LL;
  EnsureTls::EnsureTls(&_EnsureTls);
  if ( !_EnsureTls._tlsdata )
    return 2147500037LL;
  p = this->_pIHostSecMgr._p;
  if ( !p || !p->_lRefs )
  {
    if ( !PathIsURLW(szName) )
    {
      URLMoniker = -2147024809;
      goto $Cleanup_19;
    }
    v10 = 0;
    goto LABEL_13;
  }
  URLMoniker = CreateURLMonikerEx(0, (LPCWSTR)p->_riid, &pmkBase, 1u);
  if ( URLMoniker >= 0 )
  {
    v10 = pmkBase;
LABEL_13:
    URLMoniker = CreateURLMonikerEx(v10, szName, ppmk, 1u);
  }
$Cleanup_19:
  if ( pmkBase )
    pmkBase->Release(pmkBase);
  return (unsigned int)URLMoniker;
}

```

## disassembly

```asm
0x180122bd0  mov     [rsp+arg_0], rbx
0x180122bd5  mov     [rsp+arg_8], rsi
0x180122bda  push    rdi
0x180122bdb  sub     rsp, 30h
0x180122bdf  mov     rsi, ppmk
0x180122be2  mov     rdi, szName
0x180122be5  mov     rbx, this
0x180122be8  test    ppmk, ppmk
0x180122beb  jnz     short loc_180122BF7
0x180122bed  mov     eax, 80004003h
0x180122bf2  jmp     loc_180122CD5
0x180122bf7  mov     qword ptr [ppmk], 0
0x180122bfe  mov     [rsp+38h+pmkBase], 0
0x180122c07  test    rdi, rdi
0x180122c0a  jnz     short loc_180122C16
0x180122c0c  mov     eax, 80070057h
0x180122c11  jmp     loc_180122CD5
0x180122c16  lea     this, [rsp+38h+_EnsureTls]; this
0x180122c1b  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180122c20  cmp     [rsp+38h+_EnsureTls._tlsdata], 0
0x180122c26  jnz     short loc_180122C32
0x180122c28  mov     eax, 80004005h
0x180122c2d  jmp     loc_180122CD5
0x180122c32  mov     szName, [rbx+28h]
0x180122c36  test    szName, szName
0x180122c39  jz      short loc_180122C6F
0x180122c3b  cmp     dword ptr [szName+10h], 0
0x180122c3f  jz      short loc_180122C6F
0x180122c41  mov     r9d, 1; dwFlags
0x180122c47  lea     pBC, [rsp+38h+pmkBase]; ppmk
0x180122c4c  mov     szName, [szName+18h]; szURL
0x180122c50  xor     ecx, ecx; pMkCtx
0x180122c52  call    cs:__imp_CreateURLMonikerEx
0x180122c59  nop     dword ptr [rax+rax+00h]
0x180122c5e  mov     ebx, eax
0x180122c60  mov     [rsp+38h+hr], eax
0x180122c64  test    eax, eax
0x180122c66  js      short $Cleanup_19
0x180122c68  mov     this, [rsp+38h+pmkBase]
0x180122c6d  jmp     short loc_180122C84
0x180122c6f  mov     this, rdi; pszPath
0x180122c72  call    cs:__imp_PathIsURLW
0x180122c79  nop     dword ptr [rax+rax+00h]
0x180122c7e  test    eax, eax
0x180122c80  jz      short loc_180122CA4
0x180122c82  xor     ecx, ecx; pMkCtx
0x180122c84  mov     szName, rdi; szURL
0x180122c87  mov     pBC, rsi; ppmk
0x180122c8a  mov     r9d, 1; dwFlags
0x180122c90  call    cs:__imp_CreateURLMonikerEx
0x180122c97  nop     dword ptr [rax+rax+00h]
0x180122c9c  mov     ebx, eax
0x180122c9e  mov     [rsp+38h+hr], eax
0x180122ca2  jmp     short loc_180122CAD
0x180122ca4  mov     ebx, 80070057h
0x180122ca9  mov     [rsp+38h+hr], ebx
0x180122cad  jmp     short $Cleanup_19
0x180122caf  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180122cb4  mov     ebx, 80004005h
0x180122cb9  mov     [rsp+38h+hr], ebx
0x180122cbd  mov     this, [rsp+38h+pmkBase]
0x180122cc2  test    this, this
0x180122cc5  jz      short loc_180122CD3
0x180122cc7  mov     rax, [this]
0x180122cca  mov     rax, [rax+10h]
0x180122cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122cd3  mov     eax, ebx
0x180122cd5  mov     rbx, [rsp+38h+arg_0]
0x180122cda  mov     rsi, [rsp+38h+arg_8]
0x180122cdf  add     rsp, 30h
0x180122ce3  pop     rdi
0x180122ce4  retn
0x18018197e  push    rbp
0x180181980  sub     rsp, 20h
0x180181984  mov     rbp, rdx
0x180181987  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18018198c  nop
0x18018198d  add     rsp, 20h
0x180181991  pop     rbp
0x180181992  retn
```
