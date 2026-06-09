# StorageWriter::ReadFeatureUsageSubscription(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,uint,ushort const *)

- ea: `0x18007ba90`
- end: `0x18007bc2d`
- name: `?ReadFeatureUsageSubscription@StorageWriter@@CA?AU_RTL_FEATURE_USAGE_SUBSCRIPTION_DETAILS@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@IPEBG@Z`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18007bc34`

## callees

- `0x180003220`
- `0x180016698`
- `0x180019768`
- `0x18001e820`
- `0x18007ba90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007bb39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007bb8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007bbdf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007bb39`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007bb8a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007bbdf`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18007bad5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18007bad5`

## string_xrefs

- `0x18007bae6`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007bb4a`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007bb9b`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`
- `0x18007bbf0`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\storagewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall StorageWriter::ReadFeatureUsageSubscription(_OWORD *a1, HKEY *a2, __int64 a3, const WCHAR *a4)
{
  int v5; // r14d
  unsigned int v8; // eax
  unsigned int ValueW; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-50h]
  DWORD pcbData; // [rsp+40h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-28h] BYREF
  __int128 pvData; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v5 = a3;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0,
    a3);
  v8 = RegOpenKeyW(*a2, a4, &phkResult);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)v8,
      pdwType);
  pvData = 0;
  LODWORD(pvData) = v5;
  pcbData = 4;
  ValueW = RegGetValueW(phkResult, 0, L"ReportingKind", 0x10u, 0, (char *)&pvData + 4, &pcbData);
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)ValueW,
      pdwTypea);
  pcbData = 4;
  v10 = RegGetValueW(phkResult, 0, L"ReportingOptions", 0x10u, 0, (char *)&pvData + 6, &pcbData);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)v10,
      pdwTypeb);
  pcbData = 8;
  v11 = RegGetValueW(phkResult, 0, L"ReportingTarget", 8u, 0, (char *)&pvData + 8, &pcbData);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\storagewriter.cpp",
      (const char *)v11,
      pdwTypec);
  *a1 = pvData;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return a1;
}

```

## disassembly

```asm
0x18007ba90  push    rbp
0x18007ba92  push    rbx
0x18007ba93  push    rsi
0x18007ba94  push    rdi
0x18007ba95  push    r14
0x18007ba97  mov     rbp, rsp
0x18007ba9a  sub     rsp, 70h
0x18007ba9e  mov     rax, cs:__security_cookie
0x18007baa5  xor     rax, rsp
0x18007baa8  mov     [rbp+var_10], rax
0x18007baac  mov     rdi, r9
0x18007baaf  mov     r14d, r8d
0x18007bab2  mov     rbx, rdx
0x18007bab5  mov     rsi, rcx
0x18007bab8  mov     [rbp+phkResult], 0
0x18007bac0  xor     edx, edx
0x18007bac2  lea     rcx, [rbp+phkResult]
0x18007bac6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007bacb  lea     r8, [rbp+phkResult]; phkResult
0x18007bacf  mov     rdx, rdi; lpSubKey
0x18007bad2  mov     rcx, [rbx]; hKey
0x18007bad5  call    cs:__imp_RegOpenKeyW
0x18007badb  mov     rcx, [rbp+28h]; this
0x18007badf  test    eax, eax
0x18007bae1  jz      short loc_18007BAF8
0x18007bae3  mov     r9d, eax; char *
0x18007bae6  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007baed  mov     edx, 188h; void *
0x18007baf2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007baf8  xorps   xmm0, xmm0
0x18007bafb  movups  [rbp+var_20], xmm0
0x18007baff  mov     dword ptr [rbp+var_20], r14d
0x18007bb03  mov     ebx, 4
0x18007bb08  mov     [rbp+var_30], ebx
0x18007bb0b  lea     rax, [rbp+var_30]
0x18007bb0f  mov     [rsp+70h+pcbData], rax; pcbData
0x18007bb14  lea     rax, [rbp+var_20+4]
0x18007bb18  mov     [rsp+70h+pvData], rax; pvData
0x18007bb1d  mov     [rsp+70h+pdwType], 0; unsigned int
0x18007bb26  lea     edi, [rbx+0Ch]
0x18007bb29  mov     r9d, edi; dwFlags
0x18007bb2c  lea     r8, aReportingkind; "ReportingKind"
0x18007bb33  xor     edx, edx; lpSubKey
0x18007bb35  mov     rcx, [rbp+phkResult]; hkey
0x18007bb39  call    cs:__imp_RegGetValueW
0x18007bb3f  mov     rcx, [rbp+28h]; this
0x18007bb43  test    eax, eax
0x18007bb45  jz      short loc_18007BB5C
0x18007bb47  mov     r9d, eax; char *
0x18007bb4a  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007bb51  mov     edx, 18Eh; void *
0x18007bb56  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007bb5c  mov     [rbp+var_30], ebx
0x18007bb5f  lea     rax, [rbp+var_30]
0x18007bb63  mov     [rsp+70h+pcbData], rax; pcbData
0x18007bb68  lea     rax, [rbp+var_20+6]
0x18007bb6c  mov     [rsp+70h+pvData], rax; pvData
0x18007bb71  mov     [rsp+70h+pdwType], 0; unsigned int
0x18007bb7a  mov     r9d, edi; dwFlags
0x18007bb7d  lea     r8, aReportingoptio; "ReportingOptions"
0x18007bb84  xor     edx, edx; lpSubKey
0x18007bb86  mov     rcx, [rbp+phkResult]; hkey
0x18007bb8a  call    cs:__imp_RegGetValueW
0x18007bb90  mov     rcx, [rbp+28h]; this
0x18007bb94  test    eax, eax
0x18007bb96  jz      short loc_18007BBAD
0x18007bb98  mov     r9d, eax; char *
0x18007bb9b  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007bba2  mov     edx, 191h; void *
0x18007bba7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007bbad  mov     r9d, 8; dwFlags
0x18007bbb3  mov     [rbp+var_30], r9d
0x18007bbb7  lea     rax, [rbp+var_30]
0x18007bbbb  mov     [rsp+70h+pcbData], rax; pcbData
0x18007bbc0  lea     rax, [rbp+var_20+8]
0x18007bbc4  mov     [rsp+70h+pvData], rax; pvData
0x18007bbc9  mov     [rsp+70h+pdwType], 0; unsigned int
0x18007bbd2  lea     r8, aReportingtarge; "ReportingTarget"
0x18007bbd9  xor     edx, edx; lpSubKey
0x18007bbdb  mov     rcx, [rbp+phkResult]; hkey
0x18007bbdf  call    cs:__imp_RegGetValueW
0x18007bbe5  mov     rcx, [rbp+28h]; this
0x18007bbe9  test    eax, eax
0x18007bbeb  jz      short loc_18007BC02
0x18007bbed  mov     r9d, eax; char *
0x18007bbf0  lea     r8, aOnecoreBaseFli_21; "onecore\\base\\flighting\\featuremanage"...
0x18007bbf7  mov     edx, 194h; void *
0x18007bbfc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18007bc02  movups  xmm0, [rbp+var_20]
0x18007bc06  movdqu  xmmword ptr [rsi], xmm0
0x18007bc0a  lea     rcx, [rbp+phkResult]
0x18007bc0e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007bc13  mov     rax, rsi
0x18007bc16  mov     rcx, [rbp+var_10]
0x18007bc1a  xor     rcx, rsp; StackCookie
0x18007bc1d  call    __security_check_cookie
0x18007bc22  add     rsp, 70h
0x18007bc26  pop     r14
0x18007bc28  pop     rdi
0x18007bc29  pop     rsi
0x18007bc2a  pop     rbx
0x18007bc2b  pop     rbp
0x18007bc2c  retn
```
