# IsPostCleanPC(void)

- ea: `0x1401ce774`
- end: `0x1401ce9d2`
- name: `?IsPostCleanPC@@YAHXZ`
- size: `606`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400ff93c`

## callees

- `0x140076e00`
- `0x140078078`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401ce774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ce90d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401ce90d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce7c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce857`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce8f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce941`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce7c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce857`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce8f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401ce941`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401ce80e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401ce8a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401ce983`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401ce80e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401ce8a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401ce983`

## string_xrefs

- `0x1401ce7fb`: `InstallType`
- `0x1401ce959`: `AfterCleanPCProvisioningStatusCompleted`

## pseudocode

```c
__int64 IsPostCleanPC(void)
{
  unsigned int v0; // ebx
  HKEY *phkResult; // rax
  HKEY *v2; // rax
  HKEY *v3; // rdi
  const WCHAR *v4; // rdx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v8[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v9; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v12; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v13; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v14; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE v16[528]; // [rsp+70h] [rbp-90h] BYREF

  v0 = 0;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
          0,
          1u,
          phkResult) )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"InstallType", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data == 16 )
    {
      v14 = 0;
      v2 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v14);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Provisioning\\PersistentState\\CleanPCCSP",
              0,
              1u,
              v2) )
      {
        memset_0(v16, 0, 0x208u);
        lpcbData = 520;
        if ( !RegQueryValueExW(v14, L"ProvisioningPackageID", 0, 0, v16, &lpcbData) )
        {
          v13 = 0;
          v0 = 1;
          v3 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v13);
          if ( !`ProvIsStateSeparationEnabled'::`2'::s_HasRun )
          {
            v9 = 0;
            `ProvIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                                   HKEY_LOCAL_MACHINE,
                                                                   L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                                   0,
                                                                   0x20119u,
                                                                   &v9) == 0;
            RegCloseKey(v9);
            `ProvIsStateSeparationEnabled'::`2'::s_HasRun = 1;
          }
          v4 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\OOBEPackage";
          if ( !`ProvIsStateSeparationEnabled'::`2'::s_Redirection )
            v4 = L"SOFTWARE\\Microsoft\\Provisioning\\OOBEPackage";
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 1u, v3) )
          {
            LODWORD(v9) = 0;
            *(_DWORD *)v8 = 0;
            v12 = 4;
            if ( !RegQueryValueExW(v13, L"AfterCleanPCProvisioningStatusCompleted", 0, (LPDWORD)&v9, v8, &v12)
              && *(_DWORD *)v8 == 1 )
            {
              v0 = 0;
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v0;
}

```

## disassembly

```asm
0x1401ce774  push    rbp
0x1401ce776  push    rbx
0x1401ce777  push    rdi
0x1401ce778  push    r12
0x1401ce77a  lea     rbp, [rsp-198h]
0x1401ce782  sub     rsp, 298h
0x1401ce789  mov     rax, cs:__security_cookie
0x1401ce790  xor     rax, rsp
0x1401ce793  mov     [rbp+1B0h+var_30], rax
0x1401ce79a  xor     ebx, ebx
0x1401ce79c  lea     rcx, [rsp+2B0h+hKey]
0x1401ce7a1  mov     [rsp+2B0h+hKey], rbx
0x1401ce7a6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401ce7ab  mov     r12, 0FFFFFFFF80000002h
0x1401ce7b2  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1401ce7b7  mov     rcx, r12; hKey
0x1401ce7ba  lea     r9d, [rbx+1]; samDesired
0x1401ce7be  xor     r8d, r8d; ulOptions
0x1401ce7c1  lea     rdx, aSoftwareMicros_64; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401ce7c8  call    cs:__imp_RegOpenKeyExW
0x1401ce7ce  test    eax, eax
0x1401ce7d0  jnz     loc_1401CE9AA
0x1401ce7d6  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1401ce7db  lea     rax, [rsp+2B0h+cbData]
0x1401ce7e0  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1401ce7e5  lea     r9, [rsp+2B0h+Type]; lpType
0x1401ce7ea  lea     rax, [rsp+2B0h+Data]
0x1401ce7ef  mov     [rsp+2B0h+Type], ebx
0x1401ce7f3  xor     r8d, r8d; lpReserved
0x1401ce7f6  mov     [rsp+2B0h+phkResult], rax; lpData
0x1401ce7fb  lea     rdx, aInstalltype; "InstallType"
0x1401ce802  mov     dword ptr [rsp+2B0h+Data], ebx
0x1401ce806  mov     [rsp+2B0h+cbData], 4
0x1401ce80e  call    cs:__imp_RegQueryValueExW
0x1401ce814  test    eax, eax
0x1401ce816  jnz     loc_1401CE9AA
0x1401ce81c  cmp     [rsp+2B0h+Type], 4
0x1401ce821  jnz     loc_1401CE9AA
0x1401ce827  cmp     dword ptr [rsp+2B0h+Data], 10h
0x1401ce82c  jnz     loc_1401CE9AA
0x1401ce832  lea     rcx, [rsp+2B0h+var_250]
0x1401ce837  mov     [rsp+2B0h+var_250], rbx
0x1401ce83c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401ce841  lea     r9d, [rbx+1]; samDesired
0x1401ce845  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1401ce84a  xor     r8d, r8d; ulOptions
0x1401ce84d  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Provisioning\\Pers"...
0x1401ce854  mov     rcx, r12; hKey
0x1401ce857  call    cs:__imp_RegOpenKeyExW
0x1401ce85d  test    eax, eax
0x1401ce85f  jnz     loc_1401CE9A0
0x1401ce865  mov     edi, 208h
0x1401ce86a  lea     rcx, [rsp+2B0h+var_240]; void *
0x1401ce86f  mov     r8d, edi; Size
0x1401ce872  xor     edx, edx; Val
0x1401ce874  call    memset_0
0x1401ce879  mov     rcx, [rsp+2B0h+var_250]; hKey
0x1401ce87e  lea     rax, [rsp+2B0h+var_264]
0x1401ce883  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1401ce888  lea     rdx, aProvisioningpa; "ProvisioningPackageID"
0x1401ce88f  lea     rax, [rsp+2B0h+var_240]
0x1401ce894  mov     [rsp+2B0h+var_264], edi
0x1401ce898  xor     r9d, r9d; lpType
0x1401ce89b  mov     [rsp+2B0h+phkResult], rax; lpData
0x1401ce8a0  xor     r8d, r8d; lpReserved
0x1401ce8a3  call    cs:__imp_RegQueryValueExW
0x1401ce8a9  test    eax, eax
0x1401ce8ab  jnz     loc_1401CE9A0
0x1401ce8b1  lea     rcx, [rsp+2B0h+var_258]
0x1401ce8b6  mov     [rsp+2B0h+var_258], 0
0x1401ce8bf  lea     ebx, [rax+1]
0x1401ce8c2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401ce8c7  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1401ce8ce  mov     rdi, rax
0x1401ce8d1  jnz     short loc_1401CE919
0x1401ce8d3  lea     rax, [rsp+2B0h+var_270]
0x1401ce8d8  mov     [rsp+2B0h+var_270], 0
0x1401ce8e1  mov     r9d, 20119h; samDesired
0x1401ce8e7  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1401ce8ec  xor     r8d, r8d; ulOptions
0x1401ce8ef  lea     rdx, aSoftwareMicros_65; "Software\\Microsoft\\Provisioning\\Stat"...
0x1401ce8f6  mov     rcx, r12; hKey
0x1401ce8f9  call    cs:__imp_RegOpenKeyExW
0x1401ce8ff  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1401ce904  test    eax, eax
0x1401ce906  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1401ce90d  call    cs:__imp_RegCloseKey
0x1401ce913  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, bl; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1401ce919  mov     cl, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1401ce91f  lea     rax, aSoftwareMicros_140; "SOFTWARE\\Microsoft\\Provisioning\\OOBE"...
0x1401ce926  test    cl, cl
0x1401ce928  mov     [rsp+2B0h+phkResult], rdi; phkResult
0x1401ce92d  lea     rdx, aOsdataSoftware_1; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1401ce934  mov     r9d, ebx; samDesired
0x1401ce937  cmovz   rdx, rax; lpSubKey
0x1401ce93b  mov     rcx, r12; hKey
0x1401ce93e  xor     r8d, r8d; ulOptions
0x1401ce941  call    cs:__imp_RegOpenKeyExW
0x1401ce947  test    eax, eax
0x1401ce949  jnz     short loc_1401CE996
0x1401ce94b  mov     rcx, [rsp+2B0h+var_258]; hKey
0x1401ce950  lea     r9, [rsp+2B0h+var_270]; lpType
0x1401ce955  mov     dword ptr [rsp+2B0h+var_270], eax
0x1401ce959  lea     rdx, aAftercleanpcpr; "AfterCleanPCProvisioningStatusCompleted"
0x1401ce960  mov     dword ptr [rsp+2B0h+var_278], eax
0x1401ce964  xor     r8d, r8d; lpReserved
0x1401ce967  lea     rax, [rsp+2B0h+var_260]
0x1401ce96c  mov     [rsp+2B0h+var_260], 4
0x1401ce974  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1401ce979  lea     rax, [rsp+2B0h+var_278]
0x1401ce97e  mov     [rsp+2B0h+phkResult], rax; lpData
0x1401ce983  call    cs:__imp_RegQueryValueExW
0x1401ce989  test    eax, eax
0x1401ce98b  jnz     short loc_1401CE996
0x1401ce98d  xor     ecx, ecx
0x1401ce98f  cmp     dword ptr [rsp+2B0h+var_278], ebx
0x1401ce993  cmovz   ebx, ecx
0x1401ce996  lea     rcx, [rsp+2B0h+var_258]
0x1401ce99b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401ce9a0  lea     rcx, [rsp+2B0h+var_250]
0x1401ce9a5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401ce9aa  lea     rcx, [rsp+2B0h+hKey]
0x1401ce9af  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401ce9b4  mov     eax, ebx
0x1401ce9b6  mov     rcx, [rbp+1B0h+var_30]
0x1401ce9bd  xor     rcx, rsp; StackCookie
0x1401ce9c0  call    __security_check_cookie
0x1401ce9c5  add     rsp, 298h
0x1401ce9cc  pop     r12
0x1401ce9ce  pop     rdi
0x1401ce9cf  pop     rbx
0x1401ce9d0  pop     rbp
0x1401ce9d1  retn
```
