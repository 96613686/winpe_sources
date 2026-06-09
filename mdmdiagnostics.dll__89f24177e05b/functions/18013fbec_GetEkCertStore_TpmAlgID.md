# GetEkCertStore(TpmAlgID)

- ea: `0x18013fbec`
- end: `0x18013fe93`
- name: `?GetEkCertStore@@YAPEAXW4TpmAlgID@@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18013fe9c`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e61cc`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f7bdc`
- `0x180127dbc`
- `0x18013e304`
- `0x18013f300`
- `0x18013fbec`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18013fc6b`
- `ntdll!RtlGetPersistedStateLocation` at `0x18013fc6b`
- `CRYPT32!CertOpenStore` at `0x18013fceb`
- `CRYPT32!CertOpenStore` at `0x18013fdc8`
- `CRYPT32!CertOpenStore` at `0x18013fceb`
- `CRYPT32!CertOpenStore` at `0x18013fdc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013fd40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013fd40`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013fcc0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013fd96`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013fcc0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013fd96`

## string_xrefs

- `0x18013fc62`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetEkCertStore()
{
  __int64 v0; // rax
  LSTATUS v1; // eax
  bool v2; // sf
  const char *v3; // r9
  __int64 v4; // rbx
  HKEY v5; // rbx
  LSTATUS v6; // eax
  bool v7; // sf
  const char *v8; // r9
  unsigned int v10; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HCERTSTORE v13; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v16[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  std::wstring::wstring(v16, L"TPMCoreProvisioningEKCertificates");
  memset_0(SubKey, 0, 0x208u);
  v15 = 520;
  v0 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
  RtlGetPersistedStateLocation(
    v0,
    0,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement\\EKCertStore",
    0,
    SubKey,
    520,
    &v15);
  v14 = 0;
  hKey = 0;
  v1 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( v2 )
  {
    v5 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
      RegCloseKey(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
    }
    hKey = 0;
    v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, &hKey, 0);
    v7 = v6 < 0;
    if ( v6 > 0 )
      v7 = 1;
    if ( v7 )
    {
      v10 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        (const char *)v10,
        dwOptions);
    }
    v13 = CertOpenStore((LPCSTR)4, 0, 0, 0x8000u, hKey);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v14,
      &v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
    v4 = v14;
    if ( !v14 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v8);
  }
  else
  {
    v13 = CertOpenStore((LPCSTR)4, 0, 0, 0, hKey);
    __4__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAAAEAV01___QEAV01__Z(
      &v14,
      &v13);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
    v4 = v14;
    if ( !v14 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v3);
  }
  v14 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
  std::wstring::_Tidy_deallocate(v16);
  return v4;
}

```

## disassembly

```asm
0x18013fbec  mov     [rsp-8+arg_0], rbx
0x18013fbf1  push    rbp
0x18013fbf2  lea     rbp, [rsp-1B0h]
0x18013fbfa  sub     rsp, 2B0h
0x18013fc01  mov     rax, cs:__security_cookie
0x18013fc08  xor     rax, rsp
0x18013fc0b  mov     [rbp+1B0h+var_10], rax
0x18013fc12  lea     rdx, aTpmcoreprovisi_0; "TPMCoreProvisioningEKCertificates"
0x18013fc19  lea     rcx, [rsp+2B0h+var_240]
0x18013fc1e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013fc23  nop
0x18013fc24  mov     ebx, 208h
0x18013fc29  mov     r8d, ebx; Size
0x18013fc2c  xor     edx, edx; Val
0x18013fc2e  lea     rcx, [rbp+1B0h+SubKey]; void *
0x18013fc32  call    memset_0
0x18013fc37  mov     [rsp+2B0h+var_248], ebx
0x18013fc3b  lea     rcx, [rsp+2B0h+var_240]
0x18013fc40  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013fc45  mov     rcx, rax
0x18013fc48  lea     rax, [rsp+2B0h+var_248]
0x18013fc4d  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x18013fc52  mov     [rsp+2B0h+samDesired], ebx
0x18013fc56  lea     rax, [rbp+1B0h+SubKey]
0x18013fc5a  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x18013fc5f  xor     r9d, r9d
0x18013fc62  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\TP"...
0x18013fc69  xor     edx, edx
0x18013fc6b  call    cs:__imp_RtlGetPersistedStateLocation
0x18013fc71  mov     [rsp+2B0h+var_250], 0
0x18013fc7a  mov     [rsp+2B0h+hKey], 0
0x18013fc83  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18013fc8c  lea     rax, [rsp+2B0h+hKey]
0x18013fc91  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18013fc96  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18013fc9f  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x18013fca7  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x18013fcaf  xor     r9d, r9d; lpClass
0x18013fcb2  xor     r8d, r8d; Reserved
0x18013fcb5  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18013fcb9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013fcc0  call    cs:__imp_RegCreateKeyExW
0x18013fcc6  test    eax, eax
0x18013fcc8  jle     short loc_18013FCD4
0x18013fcca  movzx   eax, ax
0x18013fccd  or      eax, 80070000h
0x18013fcd2  test    eax, eax
0x18013fcd4  js      short loc_18013FD29
0x18013fcd6  mov     rax, [rsp+2B0h+hKey]
0x18013fcdb  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x18013fce0  xor     r9d, r9d; dwFlags
0x18013fce3  xor     r8d, r8d; hCryptProv
0x18013fce6  xor     edx, edx; dwEncodingType
0x18013fce8  lea     ecx, [rdx+4]; lpszStoreProvider
0x18013fceb  call    cs:__imp_CertOpenStore
0x18013fcf1  mov     [rsp+2B0h+var_258], rax
0x18013fcf6  lea     rdx, [rsp+2B0h+var_258]
0x18013fcfb  lea     rcx, [rsp+2B0h+var_250]
0x18013fd00  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18013fd05  lea     rcx, [rsp+2B0h+var_258]
0x18013fd0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18013fd0f  mov     rcx, [rbp+1B8h]; this
0x18013fd16  mov     rbx, [rsp+2B0h+var_250]
0x18013fd1b  test    rbx, rbx
0x18013fd1e  jz      loc_18013FE5B
0x18013fd24  jmp     loc_18013FDFD
0x18013fd29  mov     rbx, [rsp+2B0h+hKey]
0x18013fd2e  test    rbx, rbx
0x18013fd31  jz      short loc_18013FD50
0x18013fd33  lea     rcx, [rsp+2B0h+var_258]; this
0x18013fd38  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18013fd3d  mov     rcx, rbx; hKey
0x18013fd40  call    cs:__imp_RegCloseKey
0x18013fd46  lea     rcx, [rsp+2B0h+var_258]; this
0x18013fd4b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18013fd50  mov     [rsp+2B0h+hKey], 0
0x18013fd59  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x18013fd62  lea     rax, [rsp+2B0h+hKey]
0x18013fd67  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18013fd6c  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18013fd75  mov     [rsp+2B0h+samDesired], 20019h; samDesired
0x18013fd7d  mov     [rsp+2B0h+dwOptions], 0; int
0x18013fd85  xor     r9d, r9d; lpClass
0x18013fd88  xor     r8d, r8d; Reserved
0x18013fd8b  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x18013fd8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013fd96  call    cs:__imp_RegCreateKeyExW
0x18013fd9c  test    eax, eax
0x18013fd9e  jle     short loc_18013FDAA
0x18013fda0  movzx   eax, ax
0x18013fda3  or      eax, 80070000h
0x18013fda8  test    eax, eax
0x18013fdaa  js      loc_18013FE6D
0x18013fdb0  mov     rax, [rsp+2B0h+hKey]
0x18013fdb5  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x18013fdba  mov     r9d, 8000h; dwFlags
0x18013fdc0  xor     r8d, r8d; hCryptProv
0x18013fdc3  xor     edx, edx; dwEncodingType
0x18013fdc5  lea     ecx, [rdx+4]; lpszStoreProvider
0x18013fdc8  call    cs:__imp_CertOpenStore
0x18013fdce  mov     [rsp+2B0h+var_258], rax
0x18013fdd3  lea     rdx, [rsp+2B0h+var_258]
0x18013fdd8  lea     rcx, [rsp+2B0h+var_250]
0x18013fddd  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18013fde2  lea     rcx, [rsp+2B0h+var_258]
0x18013fde7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18013fdec  mov     rcx, [rbp+1B8h]; this
0x18013fdf3  mov     rbx, [rsp+2B0h+var_250]
0x18013fdf8  test    rbx, rbx
0x18013fdfb  jz      short loc_18013FE49
0x18013fdfd  mov     [rsp+2B0h+var_250], 0
0x18013fe06  lea     rcx, [rsp+2B0h+hKey]
0x18013fe0b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013fe10  nop
0x18013fe11  lea     rcx, [rsp+2B0h+var_250]
0x18013fe16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18013fe1b  nop
0x18013fe1c  lea     rcx, [rsp+2B0h+var_240]
0x18013fe21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013fe26  mov     rax, rbx
0x18013fe29  mov     rcx, [rbp+1B0h+var_10]
0x18013fe30  xor     rcx, rsp; StackCookie
0x18013fe33  call    __security_check_cookie
0x18013fe38  mov     rbx, [rsp+2B0h+arg_0]
0x18013fe40  add     rsp, 2B0h
0x18013fe47  pop     rbp
0x18013fe48  retn
0x18013fe49  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18013fe50  mov     edx, 0C8h; void *
0x18013fe55  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18013fe5b  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18013fe62  mov     edx, 0B3h; void *
0x18013fe67  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18013fe6d  mov     ecx, 80070005h
0x18013fe72  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18013fe77  mov     r9d, eax; char *
0x18013fe7a  mov     rcx, [rbp+1B8h]; this
0x18013fe81  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18013fe88  mov     edx, 0CDh; void *
0x18013fe8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
