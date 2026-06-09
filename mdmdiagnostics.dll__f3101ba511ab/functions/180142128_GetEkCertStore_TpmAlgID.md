# GetEkCertStore(TpmAlgID)

- ea: `0x180142128`
- end: `0x1801423f4`
- name: `?GetEkCertStore@@YAPEAXW4TpmAlgID@@@Z`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1801423fc`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e63dc`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f8abc`
- `0x1801298ac`
- `0x180140720`
- `0x18014181c`
- `0x180142128`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x1801421a7`
- `ntdll!RtlGetPersistedStateLocation` at `0x1801421a7`
- `CRYPT32!CertOpenStore` at `0x180142233`
- `CRYPT32!CertOpenStore` at `0x180142322`
- `CRYPT32!CertOpenStore` at `0x180142233`
- `CRYPT32!CertOpenStore` at `0x180142322`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014228e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014228e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180142202`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801422ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180142202`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801422ea`

## string_xrefs

- `0x18014219e`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement\EKCertStore`

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
0x180142128  mov     [rsp-8+arg_0], rbx
0x18014212d  push    rbp
0x18014212e  lea     rbp, [rsp-1B0h]
0x180142136  sub     rsp, 2B0h
0x18014213d  mov     rax, cs:__security_cookie
0x180142144  xor     rax, rsp
0x180142147  mov     [rbp+1B0h+var_10], rax
0x18014214e  lea     rdx, aTpmcoreprovisi_0; "TPMCoreProvisioningEKCertificates"
0x180142155  lea     rcx, [rsp+2B0h+var_240]
0x18014215a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18014215f  nop
0x180142160  mov     ebx, 208h
0x180142165  mov     r8d, ebx; Size
0x180142168  xor     edx, edx; Val
0x18014216a  lea     rcx, [rbp+1B0h+SubKey]; void *
0x18014216e  call    memset_0
0x180142173  mov     [rsp+2B0h+var_248], ebx
0x180142177  lea     rcx, [rsp+2B0h+var_240]
0x18014217c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180142181  mov     rcx, rax
0x180142184  lea     rax, [rsp+2B0h+var_248]
0x180142189  mov     [rsp+2B0h+lpSecurityAttributes], rax
0x18014218e  mov     [rsp+2B0h+samDesired], ebx
0x180142192  lea     rax, [rbp+1B0h+SubKey]
0x180142196  mov     qword ptr [rsp+2B0h+dwOptions], rax
0x18014219b  xor     r9d, r9d
0x18014219e  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\TP"...
0x1801421a5  xor     edx, edx
0x1801421a7  call    cs:__imp_RtlGetPersistedStateLocation
0x1801421ae  nop     dword ptr [rax+rax+00h]
0x1801421b3  mov     [rsp+2B0h+var_250], 0
0x1801421bc  mov     [rsp+2B0h+hKey], 0
0x1801421c5  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x1801421ce  lea     rax, [rsp+2B0h+hKey]
0x1801421d3  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1801421d8  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801421e1  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x1801421e9  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x1801421f1  xor     r9d, r9d; lpClass
0x1801421f4  xor     r8d, r8d; Reserved
0x1801421f7  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1801421fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180142202  call    cs:__imp_RegCreateKeyExW
0x180142209  nop     dword ptr [rax+rax+00h]
0x18014220e  test    eax, eax
0x180142210  jle     short loc_18014221C
0x180142212  movzx   eax, ax
0x180142215  or      eax, 80070000h
0x18014221a  test    eax, eax
0x18014221c  js      short loc_180142277
0x18014221e  mov     rax, [rsp+2B0h+hKey]
0x180142223  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x180142228  xor     r9d, r9d; dwFlags
0x18014222b  xor     r8d, r8d; hCryptProv
0x18014222e  xor     edx, edx; dwEncodingType
0x180142230  lea     ecx, [rdx+4]; lpszStoreProvider
0x180142233  call    cs:__imp_CertOpenStore
0x18014223a  nop     dword ptr [rax+rax+00h]
0x18014223f  mov     [rsp+2B0h+var_258], rax
0x180142244  lea     rdx, [rsp+2B0h+var_258]
0x180142249  lea     rcx, [rsp+2B0h+var_250]
0x18014224e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180142253  lea     rcx, [rsp+2B0h+var_258]
0x180142258  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014225d  mov     rcx, [rbp+1B8h]; this
0x180142264  mov     rbx, [rsp+2B0h+var_250]
0x180142269  test    rbx, rbx
0x18014226c  jz      loc_1801423BC
0x180142272  jmp     loc_18014235D
0x180142277  mov     rbx, [rsp+2B0h+hKey]
0x18014227c  test    rbx, rbx
0x18014227f  jz      short loc_1801422A4
0x180142281  lea     rcx, [rsp+2B0h+var_258]; this
0x180142286  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18014228b  mov     rcx, rbx; hKey
0x18014228e  call    cs:__imp_RegCloseKey
0x180142295  nop     dword ptr [rax+rax+00h]
0x18014229a  lea     rcx, [rsp+2B0h+var_258]; this
0x18014229f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801422a4  mov     [rsp+2B0h+hKey], 0
0x1801422ad  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x1801422b6  lea     rax, [rsp+2B0h+hKey]
0x1801422bb  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1801422c0  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801422c9  mov     [rsp+2B0h+samDesired], 20019h; samDesired
0x1801422d1  mov     [rsp+2B0h+dwOptions], 0; int
0x1801422d9  xor     r9d, r9d; lpClass
0x1801422dc  xor     r8d, r8d; Reserved
0x1801422df  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1801422e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801422ea  call    cs:__imp_RegCreateKeyExW
0x1801422f1  nop     dword ptr [rax+rax+00h]
0x1801422f6  test    eax, eax
0x1801422f8  jle     short loc_180142304
0x1801422fa  movzx   eax, ax
0x1801422fd  or      eax, 80070000h
0x180142302  test    eax, eax
0x180142304  js      loc_1801423CE
0x18014230a  mov     rax, [rsp+2B0h+hKey]
0x18014230f  mov     qword ptr [rsp+2B0h+dwOptions], rax; pvPara
0x180142314  mov     r9d, 8000h; dwFlags
0x18014231a  xor     r8d, r8d; hCryptProv
0x18014231d  xor     edx, edx; dwEncodingType
0x18014231f  lea     ecx, [rdx+4]; lpszStoreProvider
0x180142322  call    cs:__imp_CertOpenStore
0x180142329  nop     dword ptr [rax+rax+00h]
0x18014232e  mov     [rsp+2B0h+var_258], rax
0x180142333  lea     rdx, [rsp+2B0h+var_258]
0x180142338  lea     rcx, [rsp+2B0h+var_250]
0x18014233d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180142342  lea     rcx, [rsp+2B0h+var_258]
0x180142347  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014234c  mov     rcx, [rbp+1B8h]; this
0x180142353  mov     rbx, [rsp+2B0h+var_250]
0x180142358  test    rbx, rbx
0x18014235b  jz      short loc_1801423AA
0x18014235d  mov     [rsp+2B0h+var_250], 0
0x180142366  lea     rcx, [rsp+2B0h+hKey]
0x18014236b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180142370  nop
0x180142371  lea     rcx, [rsp+2B0h+var_250]
0x180142376  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18014237b  nop
0x18014237c  lea     rcx, [rsp+2B0h+var_240]
0x180142381  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180142386  mov     rax, rbx
0x180142389  mov     rcx, [rbp+1B0h+var_10]
0x180142390  xor     rcx, rsp; StackCookie
0x180142393  call    __security_check_cookie
0x180142398  mov     rbx, [rsp+2B0h+arg_0]
0x1801423a0  add     rsp, 2B0h
0x1801423a7  pop     rbp
0x1801423a8  retn
0x1801423aa  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x1801423b1  mov     edx, 0C8h; void *
0x1801423b6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801423bc  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x1801423c3  mov     edx, 0B3h; void *
0x1801423c8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1801423ce  mov     ecx, 80070005h
0x1801423d3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1801423d8  mov     r9d, eax; char *
0x1801423db  mov     rcx, [rbp+1B8h]; this
0x1801423e2  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x1801423e9  mov     edx, 0CDh; void *
0x1801423ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
