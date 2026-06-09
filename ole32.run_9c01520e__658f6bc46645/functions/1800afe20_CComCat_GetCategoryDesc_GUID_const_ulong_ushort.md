# CComCat::GetCategoryDesc(_GUID const &,ulong,ushort * *)

- ea: `0x1800afe20`
- end: `0x1800b00ee`
- name: `?GetCategoryDesc@CComCat@@UEAAJAEBU_GUID@@KPEAPEAG@Z`
- size: `718`
- prototype: `HRESULT __fastcall(CComCat *this, const _GUID *rcatid, unsigned int lcid, wchar_t **ppszDesc)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f660`
- `0x18001d110`
- `0x18003a394`
- `0x180046460`
- `0x180046de0`
- `0x1800afa78`
- `0x1800afe20`
- `0x1800b00f4`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800affc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800affc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800affd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0037`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b006b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800affd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0037`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b006b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800aff35`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800aff9d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800aff35`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800aff9d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800afe96`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800afe96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800affe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800affe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0047`

## string_xrefs

- `0x1800afec7`: `Component Categories`

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
0x1800afe20  push    rbp
0x1800afe22  push    r14
0x1800afe24  push    r15
0x1800afe26  sub     rsp, 70h
0x1800afe2a  lea     rbp, [rsp+40h]
0x1800afe2f  mov     [rbp+40h+arg_0], rbx
0x1800afe33  mov     [rbp+40h+arg_8], rsi
0x1800afe37  mov     [rbp+40h+arg_10], rdi
0x1800afe3b  mov     [rbp+40h+arg_18], r12
0x1800afe3f  mov     rax, cs:__security_cookie
0x1800afe46  xor     rax, rbp
0x1800afe49  mov     [rbp+40h+var_20], rax
0x1800afe4d  lea     r15, [this-8]
0x1800afe51  mov     rsi, rcatid
0x1800afe54  mov     rdi, this
0x1800afe57  mov     edx, 68h ; 'h'; cb
0x1800afe5c  mov     this, r15; pv
0x1800afe5f  mov     r14, ppszDesc
0x1800afe62  mov     r12d, lcid
0x1800afe65  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x1800afe6a  test    eax, eax
0x1800afe6c  jnz     short loc_1800AFE78
0x1800afe6e  mov     eax, 80004003h
0x1800afe73  jmp     loc_1800B00C7
0x1800afe78  mov     edx, 10h; cb
0x1800afe7d  mov     this, rsi; pv
0x1800afe80  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800afe85  test    eax, eax
0x1800afe87  jz      loc_1800B00C2
0x1800afe8d  and     [rbp+40h+pCLSID], 0
0x1800afe92  lea     rcatid, [rbp+40h+pCLSID]; lplpsz
0x1800afe96  call    cs:__imp_StringFromCLSID
0x1800afe9d  nop     dword ptr [rax+rax+00h]
0x1800afea2  test    eax, eax
0x1800afea4  jns     short loc_1800AFEB0
0x1800afea6  mov     eax, 8007000Eh
0x1800afeab  jmp     loc_1800B00C7
0x1800afeb0  test    r14, r14
0x1800afeb3  jz      loc_1800B00C2
0x1800afeb9  and     [rbp+40h+hKey1], 0
0x1800afebe  lea     r8, [rbp+40h+hKey1]; phkResult
0x1800afec2  and     [rbp+40h+hKey2], 0
0x1800afec7  lea     this, aComponentCateg; "Component Categories"
0x1800afece  mov     edx, 2000000h; samDesired
0x1800afed3  call    OpenClassesRootKeyExW
0x1800afed8  mov     ebx, eax
0x1800afeda  test    eax, eax
0x1800afedc  jz      short loc_1800AFF02
0x1800afede  mov     this, [rbp+40h+pCLSID]; pv
0x1800afee2  call    cs:__imp_CoTaskMemFree
0x1800afee9  nop     dword ptr [rax+rax+00h]
0x1800afeee  test    ebx, ebx
0x1800afef0  jle     short loc_1800AFEFB
0x1800afef2  movzx   ebx, bx
0x1800afef5  or      ebx, 80070000h
0x1800afefb  mov     eax, ebx
0x1800afefd  jmp     loc_1800B00C7
0x1800aff02  mov     r8, [rbp+40h+pCLSID]; lpWideCharStr
0x1800aff06  lea     rax, [rbp+40h+usedDefaultChar]
0x1800aff0a  and     [rbp+40h+usedDefaultChar], 0
0x1800aff0e  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800aff12  mov     [rsp+80h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800aff17  mov     edx, 400h; dwFlags
0x1800aff1c  lea     rax, DefaultChar; "?"
0x1800aff23  xor     ecx, ecx; CodePage
0x1800aff25  mov     [rsp+80h+lpDefaultChar], rax; lpDefaultChar
0x1800aff2a  and     [rsp+80h+cbMultiByte], 0
0x1800aff2f  and     [rsp+80h+lpMultiByteStr], 0
0x1800aff35  call    cs:__imp_WideCharToMultiByte
0x1800aff3c  nop     dword ptr [rax+rax+00h]
0x1800aff41  lea     lcid, [rax+1]
0x1800aff45  movsxd  rax, lcid
0x1800aff48  lea     this, [rax+0Fh]
0x1800aff4c  cmp     this, rax
0x1800aff4f  ja      short loc_1800AFF5B
0x1800aff51  mov     this, 0FFFFFFFFFFFFFF0h
0x1800aff5b  and     this, 0FFFFFFFFFFFFFFF0h
0x1800aff5f  mov     rax, this
0x1800aff62  call    _alloca_probe
0x1800aff67  sub     rsp, this
0x1800aff6a  lea     rax, [rbp+40h+usedDefaultChar]
0x1800aff6e  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800aff72  mov     edx, 400h; dwFlags
0x1800aff77  xor     ecx, ecx; CodePage
0x1800aff79  mov     [rsp+80h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800aff7e  lea     rbx, [rsp+80h+pCLSID]
0x1800aff83  lea     rax, DefaultChar; "?"
0x1800aff8a  mov     [rsp+80h+lpDefaultChar], rax; lpDefaultChar
0x1800aff8f  mov     [rsp+80h+cbMultiByte], lcid; cbMultiByte
0x1800aff94  mov     r8, [rbp+40h+pCLSID]; lpWideCharStr
0x1800aff98  mov     [rsp+80h+lpMultiByteStr], rbx; lpMultiByteStr
0x1800aff9d  call    cs:__imp_WideCharToMultiByte
0x1800affa4  nop     dword ptr [rax+rax+00h]
0x1800affa9  mov     this, [rbp+40h+hKey1]; hKey
0x1800affad  lea     rax, [rbp+40h+hKey2]
0x1800affb1  mov     r9d, 20019h; samDesired
0x1800affb7  mov     [rsp+80h+lpMultiByteStr], rax; phkResult
0x1800affbc  xor     lcid, lcid; ulOptions
0x1800affbf  mov     rcatid, rbx; lpSubKey
0x1800affc2  call    cs:__imp_RegOpenKeyExA
0x1800affc9  nop     dword ptr [rax+rax+00h]
0x1800affce  mov     this, [rbp+40h+hKey1]; hKey
0x1800affd2  test    eax, eax
0x1800affd4  jz      short loc_1800B0037
0x1800affd6  call    cs:__imp_RegCloseKey
0x1800affdd  nop     dword ptr [rax+rax+00h]
0x1800affe2  mov     this, [rbp+40h+pCLSID]; pv
0x1800affe6  call    cs:__imp_CoTaskMemFree
0x1800affed  nop     dword ptr [rax+rax+00h]
0x1800afff2  cmp     dword ptr [rdi+4Ch], 0
0x1800afff6  jz      short loc_1800B0007
0x1800afff8  cmp     qword ptr [rdi+18h], 0
0x1800afffd  jnz     short loc_1800B0007
0x1800affff  mov     this, r15; this
0x1800b0002  call    ?GetCsCatInfo@CComCat@@AEAAJXZ; CComCat::GetCsCatInfo(void)
0x1800b0007  mov     this, [rdi+18h]
0x1800b000b  test    this, this
0x1800b000e  jz      short loc_1800B002D
0x1800b0010  mov     rax, [this]
0x1800b0013  mov     ppszDesc, r14
0x1800b0016  mov     lcid, r12d
0x1800b0019  mov     rcatid, rsi
0x1800b001c  mov     rax, [rax+20h]
0x1800b0020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0025  test    eax, eax
0x1800b0027  jns     loc_1800B00BE
0x1800b002d  mov     eax, 80040160h
0x1800b0032  jmp     loc_1800B00C7
0x1800b0037  call    cs:__imp_RegCloseKey
0x1800b003e  nop     dword ptr [rax+rax+00h]
0x1800b0043  mov     this, [rbp+40h+pCLSID]; pv
0x1800b0047  call    cs:__imp_CoTaskMemFree
0x1800b004e  nop     dword ptr [rax+rax+00h]
0x1800b0053  mov     this, [rbp+40h+hKey2]; hKey
0x1800b0057  xor     r9d, r9d; plcid
0x1800b005a  mov     r8, r14; ppszDesc
0x1800b005d  mov     edx, r12d; lcid
0x1800b0060  call    ?GetCategoryDesc@CComCat@@SAJPEAUHKEY__@@KPEAPEAGPEAK@Z; CComCat::GetCategoryDesc(HKEY__ *,ulong,ushort * *,ulong *)
0x1800b0065  mov     this, [rbp+40h+hKey2]; hKey
0x1800b0069  mov     ebx, eax
0x1800b006b  call    cs:__imp_RegCloseKey
0x1800b0072  nop     dword ptr [rax+rax+00h]
0x1800b0077  test    ebx, ebx
0x1800b0079  jns     loc_1800AFEFB
0x1800b007f  cmp     dword ptr [rdi+4Ch], 0
0x1800b0083  jz      short loc_1800B0094
0x1800b0085  cmp     qword ptr [rdi+18h], 0
0x1800b008a  jnz     short loc_1800B0094
0x1800b008c  mov     this, r15; this
0x1800b008f  call    ?GetCsCatInfo@CComCat@@AEAAJXZ; CComCat::GetCsCatInfo(void)
0x1800b0094  mov     this, [rdi+18h]
0x1800b0098  test    this, this
0x1800b009b  jz      loc_1800AFEFB
0x1800b00a1  mov     rax, [this]
0x1800b00a4  mov     ppszDesc, r14
0x1800b00a7  mov     lcid, r12d
0x1800b00aa  mov     rcatid, rsi
0x1800b00ad  mov     rax, [rax+20h]
0x1800b00b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b00b6  test    eax, eax
0x1800b00b8  js      loc_1800AFEFB
0x1800b00be  xor     eax, eax
0x1800b00c0  jmp     short loc_1800B00C7
0x1800b00c2  mov     eax, 80070057h
0x1800b00c7  mov     this, [rbp+40h+var_20]
0x1800b00cb  xor     this, rbp; StackCookie
0x1800b00ce  call    __security_check_cookie
0x1800b00d3  mov     rbx, [rbp+40h+arg_0]
0x1800b00d7  mov     rsi, [rbp+40h+arg_8]
0x1800b00db  mov     rdi, [rbp+40h+arg_10]
0x1800b00df  mov     r12, [rbp+40h+arg_18]
0x1800b00e3  lea     rsp, [rbp+30h]
0x1800b00e7  pop     r15
0x1800b00e9  pop     r14
0x1800b00eb  pop     rbp
0x1800b00ec  retn
```
