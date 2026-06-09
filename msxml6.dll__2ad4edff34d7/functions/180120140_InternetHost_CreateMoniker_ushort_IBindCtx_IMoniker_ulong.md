# InternetHost::CreateMoniker(ushort *,IBindCtx *,IMoniker * *,ulong)

- ea: `0x180120140`
- end: `0x180120243`
- name: `?CreateMoniker@InternetHost@@UEAAJPEAGPEAUIBindCtx@@PEAPEAUIMoniker@@K@Z`
- size: `259`
- prototype: `__int64 __fastcall(InternetHost *this, wchar_t *szName, IBindCtx *pBC, IMoniker **ppmk)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180056bdc`
- `0x18009f718`
- `0x1800a3e04`
- `0x180120140`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1801201dc`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1801201dc`
- `urlmon!CreateURLMonikerEx` at `0x1801201c2`
- `urlmon!CreateURLMonikerEx` at `0x1801201f4`
- `urlmon!CreateURLMonikerEx` at `0x1801201c2`
- `urlmon!CreateURLMonikerEx` at `0x1801201f4`

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
      goto $Cleanup_18;
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
$Cleanup_18:
  if ( pmkBase )
    pmkBase->Release(pmkBase);
  return (unsigned int)URLMoniker;
}

```

## disassembly

```asm
0x180120140  mov     [rsp+arg_0], rbx
0x180120145  mov     [rsp+arg_8], rsi
0x18012014a  push    rdi
0x18012014b  sub     rsp, 30h
0x18012014f  mov     rsi, ppmk
0x180120152  mov     rdi, szName
0x180120155  mov     rbx, this
0x180120158  test    ppmk, ppmk
0x18012015b  jnz     short loc_180120167
0x18012015d  mov     eax, 80004003h
0x180120162  jmp     loc_180120233
0x180120167  mov     qword ptr [ppmk], 0
0x18012016e  mov     [rsp+38h+pmkBase], 0
0x180120177  test    rdi, rdi
0x18012017a  jnz     short loc_180120186
0x18012017c  mov     eax, 80070057h
0x180120181  jmp     loc_180120233
0x180120186  lea     this, [rsp+38h+_EnsureTls]; this
0x18012018b  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x180120190  cmp     [rsp+38h+_EnsureTls._tlsdata], 0
0x180120196  jnz     short loc_1801201A2
0x180120198  mov     eax, 80004005h
0x18012019d  jmp     loc_180120233
0x1801201a2  mov     szName, [rbx+28h]
0x1801201a6  test    szName, szName
0x1801201a9  jz      short loc_1801201D9
0x1801201ab  cmp     dword ptr [szName+10h], 0
0x1801201af  jz      short loc_1801201D9
0x1801201b1  mov     r9d, 1; dwFlags
0x1801201b7  lea     pBC, [rsp+38h+pmkBase]; ppmk
0x1801201bc  mov     szName, [szName+18h]; szURL
0x1801201c0  xor     ecx, ecx; pMkCtx
0x1801201c2  call    cs:__imp_CreateURLMonikerEx
0x1801201c8  mov     ebx, eax
0x1801201ca  mov     [rsp+38h+hr], eax
0x1801201ce  test    eax, eax
0x1801201d0  js      short $Cleanup_18
0x1801201d2  mov     this, [rsp+38h+pmkBase]
0x1801201d7  jmp     short loc_1801201E8
0x1801201d9  mov     this, rdi; pszPath
0x1801201dc  call    cs:__imp_PathIsURLW
0x1801201e2  test    eax, eax
0x1801201e4  jz      short loc_180120202
0x1801201e6  xor     ecx, ecx; pMkCtx
0x1801201e8  mov     szName, rdi; szURL
0x1801201eb  mov     pBC, rsi; ppmk
0x1801201ee  mov     r9d, 1; dwFlags
0x1801201f4  call    cs:__imp_CreateURLMonikerEx
0x1801201fa  mov     ebx, eax
0x1801201fc  mov     [rsp+38h+hr], eax
0x180120200  jmp     short loc_18012020B
0x180120202  mov     ebx, 80070057h
0x180120207  mov     [rsp+38h+hr], ebx
0x18012020b  jmp     short $Cleanup_18
0x18012020d  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x180120212  mov     ebx, 80004005h
0x180120217  mov     [rsp+38h+hr], ebx
0x18012021b  mov     this, [rsp+38h+pmkBase]
0x180120220  test    this, this
0x180120223  jz      short loc_180120231
0x180120225  mov     rax, [this]
0x180120228  mov     rax, [rax+10h]
0x18012022c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120231  mov     eax, ebx
0x180120233  mov     rbx, [rsp+38h+arg_0]
0x180120238  mov     rsi, [rsp+38h+arg_8]
0x18012023d  add     rsp, 30h
0x180120241  pop     rdi
0x180120242  retn
0x18017de3a  push    rbp
0x18017de3c  sub     rsp, 20h
0x18017de40  mov     rbp, rdx
0x18017de43  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18017de48  nop
0x18017de49  add     rsp, 20h
0x18017de4d  pop     rbp
0x18017de4e  retn
```
