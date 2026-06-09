# CComCat::GetCategoryDesc(_GUID const &,ulong,ushort * *)

- ea: `0x1800a89c0`
- end: `0x1800a8c46`
- name: `?GetCategoryDesc@CComCat@@UEAAJAEBU_GUID@@KPEAPEAG@Z`
- size: `646`
- prototype: `HRESULT __fastcall(CComCat *this, const _GUID *rcatid, unsigned int lcid, wchar_t **ppszDesc)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001a0d0`
- `0x18001c1d0`
- `0x180036488`
- `0x180052390`
- `0x180052a30`
- `0x1800a867c`
- `0x1800a89c0`
- `0x1800a8c4c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8b5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8bad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8bd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8b5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8bad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8bd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a8b51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a8b51`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a8ad0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a8b32`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a8ad0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800a8b32`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a8a2e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800a8a2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8a7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8bb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8a7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8bb7`

## string_xrefs

- `0x1800a8a64`: `Component Categories`

## pseudocode

```c
__int64 __fastcall CComCat::GetCategoryDesc(CComCat *this, const _GUID *rcatid, unsigned int lcid, wchar_t **ppszDesc)
{
  CComCat *v4; // r15
  const IID *v10; // rcx
  int CategoryDesc; // ebx
  int cbMultiByte; // r8d
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  IUnknown *m_punkOuter; // rcx
  IUnknown *v18; // rcx
  wchar_t *pCLSID; // [rsp+40h] [rbp+0h] BYREF
  int usedDefaultChar; // [rsp+48h] [rbp+8h] BYREF
  HKEY__ *hKey1; // [rsp+50h] [rbp+10h] BYREF
  HKEY__ *hKey2; // [rsp+58h] [rbp+18h] BYREF

  v4 = (CComCat *)((char *)this - 8);
  if ( !IsValidPtrOut(&this[-1]._comCatalog, 0x68u) )
    return 2147500035LL;
  if ( !IsValidReadPtrIn(rcatid, 0x10u) )
    return 2147942487LL;
  pCLSID = 0;
  if ( StringFromCLSID(v10, &pCLSID) < 0 )
    return 2147942414LL;
  if ( !ppszDesc )
    return 2147942487LL;
  hKey1 = 0;
  hKey2 = 0;
  CategoryDesc = OpenClassesRootKeyExW(L"Component Categories", 0x2000000u, &hKey1);
  if ( CategoryDesc )
  {
    CoTaskMemFree(pCLSID);
    if ( CategoryDesc > 0 )
      return (unsigned __int16)CategoryDesc | 0x80070000;
    return (unsigned int)CategoryDesc;
  }
  usedDefaultChar = 0;
  cbMultiByte = WideCharToMultiByte(0, 0x400u, pCLSID, -1, 0, 0, "?", &usedDefaultChar) + 1;
  v13 = cbMultiByte + 15LL;
  if ( v13 <= cbMultiByte )
    v13 = 0xFFFFFFFFFFFFFF0LL;
  v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
  v15 = alloca(v14);
  v16 = alloca(v14);
  WideCharToMultiByte(0, 0x400u, pCLSID, -1, (LPSTR)&pCLSID, cbMultiByte, "?", &usedDefaultChar);
  if ( RegOpenKeyExA(hKey1, (LPCSTR)&pCLSID, 0, 0x20019u, &hKey2) )
  {
    RegCloseKey(hKey1);
    CoTaskMemFree(pCLSID);
    if ( HIDWORD(this->m_csCatInfoInit.SpinCount) && !this->m_punkOuter )
      CComCat::GetCsCatInfo(v4);
    m_punkOuter = this->m_punkOuter;
    if ( !m_punkOuter
      || ((int (__fastcall *)(IUnknown *, const _GUID *, _QWORD, wchar_t **))m_punkOuter->lpVtbl[1].AddRef)(
           m_punkOuter,
           rcatid,
           lcid,
           ppszDesc) < 0 )
    {
      return 2147746144LL;
    }
  }
  else
  {
    RegCloseKey(hKey1);
    CoTaskMemFree(pCLSID);
    CategoryDesc = CComCat::GetCategoryDesc(hKey2, lcid, ppszDesc, 0);
    RegCloseKey(hKey2);
    if ( CategoryDesc >= 0 )
      return (unsigned int)CategoryDesc;
    if ( HIDWORD(this->m_csCatInfoInit.SpinCount) && !this->m_punkOuter )
      CComCat::GetCsCatInfo(v4);
    v18 = this->m_punkOuter;
    if ( !v18
      || ((int (__fastcall *)(IUnknown *, const _GUID *, _QWORD, wchar_t **))v18->lpVtbl[1].AddRef)(
           v18,
           rcatid,
           lcid,
           ppszDesc) < 0 )
    {
      return (unsigned int)CategoryDesc;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a89c0  push    rbp
0x1800a89c2  push    rbx
0x1800a89c3  push    rsi
0x1800a89c4  push    rdi
0x1800a89c5  push    r12
0x1800a89c7  push    r14
0x1800a89c9  push    r15
0x1800a89cb  sub     rsp, 70h
0x1800a89cf  lea     rbp, [rsp+40h]
0x1800a89d4  mov     rax, cs:__security_cookie
0x1800a89db  xor     rax, rbp
0x1800a89de  mov     [rbp+60h+var_40], rax
0x1800a89e2  lea     r15, [this-8]
0x1800a89e6  mov     rsi, rcatid
0x1800a89e9  mov     rdi, this
0x1800a89ec  mov     edx, 68h ; 'h'; cb
0x1800a89f1  mov     this, r15; pv
0x1800a89f4  mov     r14, ppszDesc
0x1800a89f7  mov     r12d, lcid
0x1800a89fa  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800a89ff  test    eax, eax
0x1800a8a01  jnz     short loc_1800A8A0D
0x1800a8a03  mov     eax, 80004003h
0x1800a8a08  jmp     loc_1800A8C2B
0x1800a8a0d  mov     edx, 10h; cb
0x1800a8a12  mov     this, rsi; pv
0x1800a8a15  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800a8a1a  test    eax, eax
0x1800a8a1c  jz      loc_1800A8C26
0x1800a8a22  lea     rcatid, [rbp+60h+pCLSID]; lplpsz
0x1800a8a26  mov     [rbp+60h+pCLSID], 0
0x1800a8a2e  call    cs:__imp_StringFromCLSID
0x1800a8a34  test    eax, eax
0x1800a8a36  jns     short loc_1800A8A42
0x1800a8a38  mov     eax, 8007000Eh
0x1800a8a3d  jmp     loc_1800A8C2B
0x1800a8a42  test    r14, r14
0x1800a8a45  jz      loc_1800A8C26
0x1800a8a4b  lea     r8, [rbp+60h+hKey1]; phkResult
0x1800a8a4f  mov     [rbp+60h+hKey1], 0
0x1800a8a57  mov     edx, 2000000h; samDesired
0x1800a8a5c  mov     [rbp+60h+hKey2], 0
0x1800a8a64  lea     this, aComponentCateg; "Component Categories"
0x1800a8a6b  call    OpenClassesRootKeyExW
0x1800a8a70  mov     ebx, eax
0x1800a8a72  test    eax, eax
0x1800a8a74  jz      short loc_1800A8A94
0x1800a8a76  mov     this, [rbp+60h+pCLSID]; pv
0x1800a8a7a  call    cs:__imp_CoTaskMemFree
0x1800a8a80  test    ebx, ebx
0x1800a8a82  jle     short loc_1800A8A8D
0x1800a8a84  movzx   ebx, bx
0x1800a8a87  or      ebx, 80070000h
0x1800a8a8d  mov     eax, ebx
0x1800a8a8f  jmp     loc_1800A8C2B
0x1800a8a94  mov     r8, [rbp+60h+pCLSID]; lpWideCharStr
0x1800a8a98  lea     rax, [rbp+60h+usedDefaultChar]
0x1800a8a9c  mov     [rsp+0A0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800a8aa1  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800a8aa5  lea     rax, DefaultChar; "?"
0x1800a8aac  mov     [rbp+60h+usedDefaultChar], 0
0x1800a8ab3  mov     [rsp+0A0h+lpDefaultChar], rax; lpDefaultChar
0x1800a8ab8  mov     edx, 400h; dwFlags
0x1800a8abd  mov     [rsp+0A0h+cbMultiByte], 0; cbMultiByte
0x1800a8ac5  xor     ecx, ecx; CodePage
0x1800a8ac7  mov     [rsp+0A0h+lpMultiByteStr], 0; lpMultiByteStr
0x1800a8ad0  call    cs:__imp_WideCharToMultiByte
0x1800a8ad6  lea     lcid, [rax+1]
0x1800a8ada  movsxd  rax, lcid
0x1800a8add  lea     this, [rax+0Fh]
0x1800a8ae1  cmp     this, rax
0x1800a8ae4  ja      short loc_1800A8AF0
0x1800a8ae6  mov     this, 0FFFFFFFFFFFFFF0h
0x1800a8af0  and     this, 0FFFFFFFFFFFFFFF0h
0x1800a8af4  mov     rax, this
0x1800a8af7  call    _alloca_probe
0x1800a8afc  sub     rsp, this
0x1800a8aff  lea     rax, [rbp+60h+usedDefaultChar]
0x1800a8b03  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800a8b07  mov     edx, 400h; dwFlags
0x1800a8b0c  xor     ecx, ecx; CodePage
0x1800a8b0e  mov     [rsp+0A0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800a8b13  lea     rbx, [rsp+0A0h+pCLSID]
0x1800a8b18  lea     rax, DefaultChar; "?"
0x1800a8b1f  mov     [rsp+0A0h+lpDefaultChar], rax; lpDefaultChar
0x1800a8b24  mov     [rsp+0A0h+cbMultiByte], lcid; cbMultiByte
0x1800a8b29  mov     r8, [rbp+60h+pCLSID]; lpWideCharStr
0x1800a8b2d  mov     [rsp+0A0h+lpMultiByteStr], rbx; lpMultiByteStr
0x1800a8b32  call    cs:__imp_WideCharToMultiByte
0x1800a8b38  mov     this, [rbp+60h+hKey1]; hKey
0x1800a8b3c  lea     rax, [rbp+60h+hKey2]
0x1800a8b40  mov     r9d, 20019h; samDesired
0x1800a8b46  mov     [rsp+0A0h+lpMultiByteStr], rax; phkResult
0x1800a8b4b  xor     lcid, lcid; ulOptions
0x1800a8b4e  mov     rcatid, rbx; lpSubKey
0x1800a8b51  call    cs:__imp_RegOpenKeyExA
0x1800a8b57  mov     this, [rbp+60h+hKey1]; hKey
0x1800a8b5b  test    eax, eax
0x1800a8b5d  jz      short loc_1800A8BAD
0x1800a8b5f  call    cs:__imp_RegCloseKey
0x1800a8b65  mov     this, [rbp+60h+pCLSID]; pv
0x1800a8b69  call    cs:__imp_CoTaskMemFree
0x1800a8b6f  cmp     dword ptr [rdi+4Ch], 0
0x1800a8b73  jz      short loc_1800A8B84
0x1800a8b75  cmp     qword ptr [rdi+18h], 0
0x1800a8b7a  jnz     short loc_1800A8B84
0x1800a8b7c  mov     this, r15; this
0x1800a8b7f  call    ?GetCsCatInfo@CComCat@@AEAAJXZ; CComCat::GetCsCatInfo(void)
0x1800a8b84  mov     this, [rdi+18h]
0x1800a8b88  test    this, this
0x1800a8b8b  jz      short loc_1800A8BA6
0x1800a8b8d  mov     rax, [this]
0x1800a8b90  mov     ppszDesc, r14
0x1800a8b93  mov     lcid, r12d
0x1800a8b96  mov     rcatid, rsi
0x1800a8b99  mov     rax, [rax+20h]
0x1800a8b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8ba2  test    eax, eax
0x1800a8ba4  jns     short loc_1800A8C22
0x1800a8ba6  mov     eax, 80040160h
0x1800a8bab  jmp     short loc_1800A8C2B
0x1800a8bad  call    cs:__imp_RegCloseKey
0x1800a8bb3  mov     this, [rbp+60h+pCLSID]; pv
0x1800a8bb7  call    cs:__imp_CoTaskMemFree
0x1800a8bbd  mov     this, [rbp+60h+hKey2]; hKey
0x1800a8bc1  xor     r9d, r9d; plcid
0x1800a8bc4  mov     r8, r14; ppszDesc
0x1800a8bc7  mov     edx, r12d; lcid
0x1800a8bca  call    ?GetCategoryDesc@CComCat@@SAJPEAUHKEY__@@KPEAPEAGPEAK@Z; CComCat::GetCategoryDesc(HKEY__ *,ulong,ushort * *,ulong *)
0x1800a8bcf  mov     this, [rbp+60h+hKey2]; hKey
0x1800a8bd3  mov     ebx, eax
0x1800a8bd5  call    cs:__imp_RegCloseKey
0x1800a8bdb  test    ebx, ebx
0x1800a8bdd  jns     loc_1800A8A8D
0x1800a8be3  cmp     dword ptr [rdi+4Ch], 0
0x1800a8be7  jz      short loc_1800A8BF8
0x1800a8be9  cmp     qword ptr [rdi+18h], 0
0x1800a8bee  jnz     short loc_1800A8BF8
0x1800a8bf0  mov     this, r15; this
0x1800a8bf3  call    ?GetCsCatInfo@CComCat@@AEAAJXZ; CComCat::GetCsCatInfo(void)
0x1800a8bf8  mov     this, [rdi+18h]
0x1800a8bfc  test    this, this
0x1800a8bff  jz      loc_1800A8A8D
0x1800a8c05  mov     rax, [this]
0x1800a8c08  mov     ppszDesc, r14
0x1800a8c0b  mov     lcid, r12d
0x1800a8c0e  mov     rcatid, rsi
0x1800a8c11  mov     rax, [rax+20h]
0x1800a8c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8c1a  test    eax, eax
0x1800a8c1c  js      loc_1800A8A8D
0x1800a8c22  xor     eax, eax
0x1800a8c24  jmp     short loc_1800A8C2B
0x1800a8c26  mov     eax, 80070057h
0x1800a8c2b  mov     this, [rbp+60h+var_40]
0x1800a8c2f  xor     this, rbp; StackCookie
0x1800a8c32  call    __security_check_cookie
0x1800a8c37  lea     rsp, [rbp+30h]
0x1800a8c3b  pop     r15
0x1800a8c3d  pop     r14
0x1800a8c3f  pop     r12
0x1800a8c41  pop     rdi
0x1800a8c42  pop     rsi
0x1800a8c43  pop     rbx
0x1800a8c44  pop     rbp
0x1800a8c45  retn
```
