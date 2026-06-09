# I_NgcGetContainerDecryptionKeyName(ushort const *,ushort * *)

- ea: `0x18001734c`
- end: `0x180017506`
- name: `?I_NgcGetContainerDecryptionKeyName@@YAJPEBGPEAPEAG@Z`
- size: `442`
- prototype: `__int64 __fastcall(LPCWSTR pszScope, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a8a0`
- `0x18003a318`

## callees

- `0x180006538`
- `0x18000e930`
- `0x18000f238`
- `0x180016538`
- `0x18001734c`
- `0x180018790`
- `0x18002d0d8`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001741d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001741d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001743b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001743b`
- `ncrypt!NCryptOpenStorageProvider` at `0x180017388`
- `ncrypt!NCryptOpenStorageProvider` at `0x180017388`
- `ncrypt!NCryptEnumKeys` at `0x1800173d8`
- `ncrypt!NCryptEnumKeys` at `0x1800173d8`

## string_xrefs

- `0x18001739b`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800173eb`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180017470`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall I_NgcGetContainerDecryptionKeyName(LPCWSTR pszScope, unsigned __int16 **a2)
{
  SECURITY_STATUS v4; // eax
  unsigned int v5; // ebx
  SECURITY_STATUS v6; // eax
  int LastError; // eax
  int v8; // eax
  _QWORD *v9; // r9
  unsigned __int16 *v11; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-30h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-30h]
  PVOID ppEnumState; // [rsp+30h] [rbp-20h] BYREF
  NCryptKeyName *v15; // [rsp+38h] [rbp-18h] BYREF
  void **v16; // [rsp+40h] [rbp-10h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned __int16 *v19; // [rsp+80h] [rbp+30h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+88h] [rbp+38h] BYREF

  v16 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
  phProvider = 0;
  v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5AD,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v4,
      dwFlags);
LABEL_11:
    v16 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v16);
    return v5;
  }
  ppKeyName = 0;
  ppEnumState = 0;
  v6 = NCryptEnumKeys(phProvider, pszScope, &ppKeyName, &ppEnumState, 0);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BA,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v6,
      dwFlagsa);
    v16 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
    if ( !phProvider || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::InternalClose(&v16) )
      return v5;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
  }
  v15 = ppKeyName;
  ppKeyName = (NCryptKeyName *)ppEnumState;
  v8 = StringCchLengthW(v15->pszName, 0x433u, (unsigned __int64 *)&ppEnumState);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C4,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v8,
      dwFlagsa);
    std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(&ppKeyName);
    std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(&v15);
    goto LABEL_11;
  }
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v19,
    *v9,
    -1);
  v11 = v19;
  v19 = 0;
  *a2 = v11;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v19);
  std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(&ppKeyName);
  std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(&v15);
  v16 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v16);
  return 0;
}

```

## disassembly

```asm
0x18001734c  mov     [rsp-18h+arg_0], rbx
0x180017351  mov     [rsp-18h+arg_8], rsi
0x180017356  push    rbp
0x180017357  push    rdi
0x180017358  push    r15
0x18001735a  mov     rbp, rsp
0x18001735d  sub     rsp, 50h
0x180017361  mov     rsi, rdx
0x180017364  mov     rdi, rcx
0x180017367  lea     r15, ??_7?$HandleT@UNCryptProvHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable'
0x18001736e  mov     [rbp+var_10], r15
0x180017372  mov     [rbp+phProvider], 0
0x18001737a  xor     r8d, r8d; dwFlags
0x18001737d  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180017384  lea     rcx, [rbp+phProvider]; phProvider
0x180017388  call    cs:__imp_NCryptOpenStorageProvider
0x18001738e  mov     ebx, eax
0x180017390  test    eax, eax
0x180017392  jns     short loc_1800173B1
0x180017394  mov     rcx, [rbp+18h]; this
0x180017398  mov     r9d, eax; char *
0x18001739b  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800173a2  mov     edx, 5ADh; void *
0x1800173a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173ac  jmp     loc_180017496
0x1800173b1  mov     [rbp+ppKeyName], 0
0x1800173b9  mov     [rbp+ppEnumState], 0
0x1800173c1  mov     [rsp+50h+dwFlags], 0; int
0x1800173c9  lea     r9, [rbp+ppEnumState]; ppEnumState
0x1800173cd  lea     r8, [rbp+ppKeyName]; ppKeyName
0x1800173d1  mov     rdx, rdi; pszScope
0x1800173d4  mov     rcx, [rbp+phProvider]; hProvider
0x1800173d8  call    cs:__imp_NCryptEnumKeys
0x1800173de  mov     ebx, eax
0x1800173e0  test    eax, eax
0x1800173e2  jns     short loc_180017442
0x1800173e4  mov     rcx, [rbp+18h]; this
0x1800173e8  mov     r9d, eax; char *
0x1800173eb  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800173f2  mov     edx, 5BAh; void *
0x1800173f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173fc  nop
0x1800173fd  mov     [rbp+var_10], r15
0x180017401  cmp     [rbp+phProvider], 0
0x180017406  jz      loc_1800174A3
0x18001740c  lea     rcx, [rbp+var_10]
0x180017410  call    ?InternalClose@?$HandleT@UNCryptProvHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::InternalClose(void)
0x180017415  test    al, al
0x180017417  jnz     loc_1800174A3
0x18001741d  call    cs:__imp_GetLastError
0x180017423  test    eax, eax
0x180017425  jle     short loc_18001742F
0x180017427  movzx   eax, ax
0x18001742a  or      eax, 80070000h
0x18001742f  xor     r9d, r9d; lpArguments
0x180017432  xor     r8d, r8d; nNumberOfArguments
0x180017435  lea     edx, [r9+1]; dwExceptionFlags
0x180017439  mov     ecx, eax; dwExceptionCode
0x18001743b  call    cs:__imp_RaiseException
0x180017441  nop
0x180017442  mov     r9, [rbp+ppKeyName]
0x180017446  mov     [rbp+var_18], r9
0x18001744a  mov     rax, [rbp+ppEnumState]
0x18001744e  mov     [rbp+ppKeyName], rax
0x180017452  lea     r8, [rbp+ppEnumState]; unsigned __int64 *
0x180017456  mov     edx, 433h; unsigned __int64
0x18001745b  mov     rcx, [r9]; unsigned __int16 *
0x18001745e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180017463  mov     ebx, eax
0x180017465  test    eax, eax
0x180017467  jns     short loc_1800174A7
0x180017469  mov     rcx, [rbp+18h]; this
0x18001746d  mov     r9d, eax; char *
0x180017470  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180017477  mov     edx, 5C4h; void *
0x18001747c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017481  nop
0x180017482  lea     rcx, [rbp+ppKeyName]
0x180017486  call    ??1?$unique_ptr@XU?$cngmem_delete@X@@@std@@QEAA@XZ; std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(void)
0x18001748b  nop
0x18001748c  lea     rcx, [rbp+var_18]
0x180017490  call    ??1?$unique_ptr@XU?$cngmem_delete@X@@@std@@QEAA@XZ; std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(void)
0x180017495  nop
0x180017496  mov     [rbp+var_10], r15
0x18001749a  lea     rcx, [rbp+var_10]
0x18001749e  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x1800174a3  mov     eax, ebx
0x1800174a5  jmp     short loc_1800174F3
0x1800174a7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800174ab  mov     rdx, [r9]
0x1800174ae  lea     rcx, [rbp+arg_10]
0x1800174b2  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800174b7  mov     rax, [rbp+arg_10]
0x1800174bb  mov     [rbp+arg_10], 0
0x1800174c3  mov     [rsi], rax
0x1800174c6  lea     rcx, [rbp+arg_10]; void *
0x1800174ca  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800174cf  nop
0x1800174d0  lea     rcx, [rbp+ppKeyName]
0x1800174d4  call    ??1?$unique_ptr@XU?$cngmem_delete@X@@@std@@QEAA@XZ; std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(void)
0x1800174d9  nop
0x1800174da  lea     rcx, [rbp+var_18]
0x1800174de  call    ??1?$unique_ptr@XU?$cngmem_delete@X@@@std@@QEAA@XZ; std::unique_ptr<void,cngmem_delete<void>>::~unique_ptr<void,cngmem_delete<void>>(void)
0x1800174e3  nop
0x1800174e4  mov     [rbp+var_10], r15
0x1800174e8  lea     rcx, [rbp+var_10]
0x1800174ec  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x1800174f1  xor     eax, eax
0x1800174f3  mov     rbx, [rsp+50h+arg_0]
0x1800174f8  mov     rsi, [rsp+50h+arg_8]
0x1800174fd  add     rsp, 50h
0x180017501  pop     r15
0x180017503  pop     rdi
0x180017504  pop     rbp
0x180017505  retn
```
