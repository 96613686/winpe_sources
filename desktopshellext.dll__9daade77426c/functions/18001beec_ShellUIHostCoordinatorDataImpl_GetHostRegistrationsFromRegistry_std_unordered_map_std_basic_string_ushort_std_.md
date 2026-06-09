# ShellUIHostCoordinatorDataImpl::GetHostRegistrationsFromRegistry(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<ShellUIHostRegistration>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<ShellUIHostRegistration>>>> &)

- ea: `0x18001beec`
- end: `0x18001c105`
- name: `?GetHostRegistrationsFromRegistry@ShellUIHostCoordinatorDataImpl@@AEAAXAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VShellUIHostRegistration@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VShellUIHostRegistration@@@2@@std@@@2@@std@@@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014960`

## callees

- `0x180009c00`
- `0x18000bdf0`
- `0x18000c444`
- `0x18000dbf0`
- `0x1800108cc`
- `0x18001beec`
- `0x18001c10c`
- `0x18001c15c`
- `0x18001c608`
- `0x18001d1b4`
- `0x18002a3d0`
- `0x180077f9c`
- `0x180079928`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001bf9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001bf9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c0d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c0d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bf48`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c01b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c01b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LSTATUS __fastcall ShellUIHostCoordinatorDataImpl::GetHostRegistrationsFromRegistry(__int64 a1, __int64 a2)
{
  HKEY *phkResult; // rax
  LSTATUS result; // eax
  const char *v6; // r9
  __int64 v7; // rbx
  DWORD i; // r14d
  LPWSTR v9; // rdi
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-59h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-55h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-49h] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp-41h] BYREF
  __int64 v15; // [rsp+80h] [rbp-39h] BYREF
  __int64 v16; // [rsp+88h] [rbp-31h] BYREF
  std::_Ref_count_base *v17; // [rsp+90h] [rbp-29h]
  _BYTE v18[32]; // [rsp+98h] [rbp-21h] BYREF
  _BYTE v19[32]; // [rsp+B8h] [rbp-1h] BYREF

  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Shell\\ShellUIHosts\\",
             0,
             0x20019u,
             phkResult);
  if ( !result )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    result = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !result )
    {
      tip2::tip_test<tip2::details::merged_data<_tip_GetHostRegistrationsTest,_tip_GetHostRegistrationsTest>>::data(
        a1 + 488,
        &v15);
      v7 = v15;
      *(_BYTE *)(v15 + 272) = 1;
      for ( i = 0; i < cSubKeys; ++i )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpName,
          0,
          cbMaxSubKeyLen + 1,
          v6);
        cchName = cbMaxSubKeyLen + 1;
        v9 = lpName;
        if ( lpName && !RegEnumKeyExW(hKey, i, lpName, &cchName, 0, 0, 0, 0) )
        {
          std::wstring::wstring(v18, v9);
          std::vector<std::wstring>::push_back(v7 + 280, v18);
          std::wstring::~wstring(v18);
          ShellUIHostRegistration::CreateHostRegistration(&v16, &lpName, a1 + 48);
          if ( v16 )
          {
            std::wstring::wstring(v19, *(_QWORD *)(v16 + 8));
            std::vector<std::wstring>::push_back(v7 + 304, v19);
            std::wstring::~wstring(v19);
            TryAddHostRegistrationToList(a2, &v16);
          }
          if ( v17 )
            std::_Ref_count_base::_Decref(v17);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&lpName);
      }
      result = tip2::test_data_control<tip2::details::merged_data<_tip_GetHostRegistrationsTest,_tip_GetHostRegistrationsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetHostRegistrationsTest,_tip_GetHostRegistrationsTest>>(&v15);
    }
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18001beec  mov     [rsp-8+arg_10], rbx
0x18001bef1  push    rbp
0x18001bef2  push    rsi
0x18001bef3  push    rdi
0x18001bef4  push    r12
0x18001bef6  push    r13
0x18001bef8  push    r14
0x18001befa  push    r15
0x18001befc  lea     rbp, [rsp-27h]
0x18001bf01  sub     rsp, 0E0h
0x18001bf08  mov     rax, cs:__security_cookie
0x18001bf0f  xor     rax, rsp
0x18001bf12  mov     [rbp+57h+var_38], rax
0x18001bf16  mov     r12, rdx
0x18001bf19  mov     r15, rcx
0x18001bf1c  xor     r13d, r13d
0x18001bf1f  mov     [rbp+57h+hKey], r13
0x18001bf23  lea     rcx, [rbp+57h+hKey]
0x18001bf27  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001bf2c  mov     [rsp+110h+phkResult], rax; phkResult
0x18001bf31  mov     r9d, 20019h; samDesired
0x18001bf37  xor     r8d, r8d; ulOptions
0x18001bf3a  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001bf41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bf48  call    cs:__imp_RegOpenKeyExW
0x18001bf4e  test    eax, eax
0x18001bf50  jnz     loc_18001C0CF
0x18001bf56  mov     [rbp+57h+cSubKeys], r13d
0x18001bf5a  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18001bf5e  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18001bf63  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18001bf68  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18001bf6d  mov     [rsp+110h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18001bf72  mov     [rsp+110h+lpcValues], r13; lpcValues
0x18001bf77  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18001bf7c  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18001bf80  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001bf85  lea     rax, [rbp+57h+cSubKeys]
0x18001bf89  mov     [rsp+110h+phkResult], rax; lpcSubKeys
0x18001bf8e  xor     r9d, r9d; lpReserved
0x18001bf91  xor     r8d, r8d; lpcchClass
0x18001bf94  xor     edx, edx; lpClass
0x18001bf96  mov     rcx, [rbp+57h+hKey]; hKey
0x18001bf9a  call    cs:__imp_RegQueryInfoKeyW
0x18001bfa0  test    eax, eax
0x18001bfa2  jnz     loc_18001C0CF
0x18001bfa8  lea     rcx, [r15+1E8h]
0x18001bfaf  lea     rdx, [rbp+57h+var_90]
0x18001bfb3  call    ?data@?$tip_test@V?$merged_data@U_tip_GetHostRegistrationsTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_GetHostRegistrationsTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_GetHostRegistrationsTest,_tip_GetHostRegistrationsTest>>::data(void)
0x18001bfb8  nop
0x18001bfb9  mov     rbx, [rbp+57h+var_90]
0x18001bfbd  mov     byte ptr [rbx+110h], 1
0x18001bfc4  mov     r14d, r13d
0x18001bfc7  cmp     [rbp+57h+cSubKeys], r13d
0x18001bfcb  jbe     loc_18001C0C5
0x18001bfd1  mov     r8d, [rbp+57h+cbMaxSubKeyLen]
0x18001bfd5  inc     r8d
0x18001bfd8  xor     edx, edx
0x18001bfda  lea     rcx, [rbp+57h+lpName]
0x18001bfde  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001bfe3  nop
0x18001bfe4  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18001bfe7  inc     eax
0x18001bfe9  mov     [rbp+57h+cchName], eax
0x18001bfec  mov     rdi, [rbp+57h+lpName]
0x18001bff0  test    rdi, rdi
0x18001bff3  jz      loc_18001C0AF
0x18001bff9  mov     [rsp+110h+lpcValues], r13; lpftLastWriteTime
0x18001bffe  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcchClass
0x18001c003  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpClass
0x18001c008  mov     [rsp+110h+phkResult], r13; lpReserved
0x18001c00d  lea     r9, [rbp+57h+cchName]; lpcchName
0x18001c011  mov     r8, rdi; lpName
0x18001c014  mov     edx, r14d; dwIndex
0x18001c017  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c01b  call    cs:__imp_RegEnumKeyExW
0x18001c021  test    eax, eax
0x18001c023  jnz     loc_18001C0AF
0x18001c029  mov     rdx, rdi
0x18001c02c  lea     rcx, [rbp+57h+var_78]
0x18001c030  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001c035  nop
0x18001c036  lea     rdx, [rbp+57h+var_78]
0x18001c03a  lea     rcx, [rbx+118h]
0x18001c041  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18001c046  nop
0x18001c047  lea     rcx, [rbp+57h+var_78]
0x18001c04b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c050  lea     r8, [r15+30h]
0x18001c054  lea     rdx, [rbp+57h+lpName]
0x18001c058  lea     rcx, [rbp+57h+var_88]
0x18001c05c  call    ?CreateHostRegistration@ShellUIHostRegistration@@SA?AV?$shared_ptr@VShellUIHostRegistration@@@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UIApplicationActivationManagerPriv@@Uerr_exception_policy@wil@@@5@@Z; ShellUIHostRegistration::CreateHostRegistration(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy> &)
0x18001c061  nop
0x18001c062  mov     rdx, [rbp+57h+var_88]
0x18001c066  test    rdx, rdx
0x18001c069  jz      short loc_18001C0A0
0x18001c06b  mov     rdx, [rdx+8]
0x18001c06f  lea     rcx, [rbp+57h+var_58]
0x18001c073  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001c078  nop
0x18001c079  lea     rdx, [rbp+57h+var_58]
0x18001c07d  lea     rcx, [rbx+130h]
0x18001c084  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18001c089  nop
0x18001c08a  lea     rcx, [rbp+57h+var_58]
0x18001c08e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c093  lea     rdx, [rbp+57h+var_88]
0x18001c097  mov     rcx, r12
0x18001c09a  call    ?TryAddHostRegistrationToList@@YAXAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VShellUIHostRegistration@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VShellUIHostRegistration@@@2@@std@@@2@@std@@AEAV?$shared_ptr@VShellUIHostRegistration@@@2@@Z; TryAddHostRegistrationToList(std::unordered_map<std::wstring,std::shared_ptr<ShellUIHostRegistration>> &,std::shared_ptr<ShellUIHostRegistration> &)
0x18001c09f  nop
0x18001c0a0  mov     rcx, [rbp+57h+var_80]; this
0x18001c0a4  test    rcx, rcx
0x18001c0a7  jz      short loc_18001C0AF
0x18001c0a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c0ae  nop
0x18001c0af  lea     rcx, [rbp+57h+lpName]
0x18001c0b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001c0b8  inc     r14d
0x18001c0bb  cmp     r14d, [rbp+57h+cSubKeys]
0x18001c0bf  jb      loc_18001BFD1
0x18001c0c5  lea     rcx, [rbp+57h+var_90]
0x18001c0c9  call    ??1?$test_data_control@V?$merged_data@U_tip_GetHostRegistrationsTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_GetHostRegistrationsTest,_tip_GetHostRegistrationsTest>>::~test_data_control<tip2::details::merged_data<_tip_GetHostRegistrationsTest,_tip_GetHostRegistrationsTest>>(void)
0x18001c0ce  nop
0x18001c0cf  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c0d3  test    rcx, rcx
0x18001c0d6  jz      short loc_18001C0DE
0x18001c0d8  call    cs:__imp_RegCloseKey
0x18001c0de  mov     rcx, [rbp+57h+var_38]
0x18001c0e2  xor     rcx, rsp; StackCookie
0x18001c0e5  call    __security_check_cookie
0x18001c0ea  mov     rbx, [rsp+110h+arg_10]
0x18001c0f2  add     rsp, 0E0h
0x18001c0f9  pop     r15
0x18001c0fb  pop     r14
0x18001c0fd  pop     r13
0x18001c0ff  pop     r12
0x18001c101  pop     rdi
0x18001c102  pop     rsi
0x18001c103  pop     rbp
0x18001c104  retn
```
