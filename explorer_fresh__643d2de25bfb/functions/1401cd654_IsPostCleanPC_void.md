# IsPostCleanPC(void)

- ea: `0x1401cd654`
- end: `0x1401cd8e3`
- name: `?IsPostCleanPC@@YAHXZ`
- size: `655`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140108624`

## callees

- `0x140047f0c`
- `0x14007bf4c`
- `0x14010e160`
- `0x14010ed90`
- `0x1401cd654`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd6a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd743`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd7f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd845`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd6a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd743`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd7f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401cd845`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cd80b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1401cd80b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401cd6f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401cd795`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401cd88d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401cd6f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401cd795`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1401cd88d`

## string_xrefs

- `0x1401cd6e1`: `InstallType`
- `0x1401cd863`: `AfterCleanPCProvisioningStatusCompleted`

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
0x1401cd654  push    rbp
0x1401cd656  push    rbx
0x1401cd657  push    rdi
0x1401cd658  push    r12
0x1401cd65a  lea     rbp, [rsp-198h]
0x1401cd662  sub     rsp, 298h
0x1401cd669  mov     rax, cs:__security_cookie
0x1401cd670  xor     rax, rsp
0x1401cd673  mov     [rbp+1B0h+var_30], rax
0x1401cd67a  xor     ebx, ebx
0x1401cd67c  lea     rcx, [rsp+2B0h+hKey]
0x1401cd681  mov     [rsp+2B0h+hKey], rbx
0x1401cd686  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401cd68b  mov     r12, 0FFFFFFFF80000002h
0x1401cd692  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1401cd697  mov     rcx, r12; hKey
0x1401cd69a  lea     r9d, [rbx+1]; samDesired
0x1401cd69e  xor     r8d, r8d; ulOptions
0x1401cd6a1  lea     rdx, aSoftwareMicros_64; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401cd6a8  call    cs:__imp_RegOpenKeyExW
0x1401cd6af  nop     dword ptr [rax+rax+00h]
0x1401cd6b4  test    eax, eax
0x1401cd6b6  jnz     loc_1401CD8BA
0x1401cd6bc  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1401cd6c1  lea     rax, [rsp+2B0h+cbData]
0x1401cd6c6  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1401cd6cb  lea     r9, [rsp+2B0h+Type]; lpType
0x1401cd6d0  lea     rax, [rsp+2B0h+Data]
0x1401cd6d5  mov     [rsp+2B0h+Type], ebx
0x1401cd6d9  xor     r8d, r8d; lpReserved
0x1401cd6dc  mov     [rsp+2B0h+phkResult], rax; lpData
0x1401cd6e1  lea     rdx, aInstalltype; "InstallType"
0x1401cd6e8  mov     dword ptr [rsp+2B0h+Data], ebx
0x1401cd6ec  mov     [rsp+2B0h+cbData], 4
0x1401cd6f4  call    cs:__imp_RegQueryValueExW
0x1401cd6fb  nop     dword ptr [rax+rax+00h]
0x1401cd700  test    eax, eax
0x1401cd702  jnz     loc_1401CD8BA
0x1401cd708  cmp     [rsp+2B0h+Type], 4
0x1401cd70d  jnz     loc_1401CD8BA
0x1401cd713  cmp     dword ptr [rsp+2B0h+Data], 10h
0x1401cd718  jnz     loc_1401CD8BA
0x1401cd71e  lea     rcx, [rsp+2B0h+var_250]
0x1401cd723  mov     [rsp+2B0h+var_250], rbx
0x1401cd728  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401cd72d  lea     r9d, [rbx+1]; samDesired
0x1401cd731  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1401cd736  xor     r8d, r8d; ulOptions
0x1401cd739  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Provisioning\\Pers"...
0x1401cd740  mov     rcx, r12; hKey
0x1401cd743  call    cs:__imp_RegOpenKeyExW
0x1401cd74a  nop     dword ptr [rax+rax+00h]
0x1401cd74f  test    eax, eax
0x1401cd751  jnz     loc_1401CD8B0
0x1401cd757  mov     edi, 208h
0x1401cd75c  lea     rcx, [rsp+2B0h+var_240]; void *
0x1401cd761  mov     r8d, edi; Size
0x1401cd764  xor     edx, edx; Val
0x1401cd766  call    memset_0
0x1401cd76b  mov     rcx, [rsp+2B0h+var_250]; hKey
0x1401cd770  lea     rax, [rsp+2B0h+var_264]
0x1401cd775  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1401cd77a  lea     rdx, aProvisioningpa; "ProvisioningPackageID"
0x1401cd781  lea     rax, [rsp+2B0h+var_240]
0x1401cd786  mov     [rsp+2B0h+var_264], edi
0x1401cd78a  xor     r9d, r9d; lpType
0x1401cd78d  mov     [rsp+2B0h+phkResult], rax; lpData
0x1401cd792  xor     r8d, r8d; lpReserved
0x1401cd795  call    cs:__imp_RegQueryValueExW
0x1401cd79c  nop     dword ptr [rax+rax+00h]
0x1401cd7a1  test    eax, eax
0x1401cd7a3  jnz     loc_1401CD8B0
0x1401cd7a9  lea     rcx, [rsp+2B0h+var_258]
0x1401cd7ae  mov     [rsp+2B0h+var_258], 0
0x1401cd7b7  lea     ebx, [rax+1]
0x1401cd7ba  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1401cd7bf  cmp     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1401cd7c6  mov     rdi, rax
0x1401cd7c9  jnz     short loc_1401CD81D
0x1401cd7cb  lea     rax, [rsp+2B0h+var_270]
0x1401cd7d0  mov     [rsp+2B0h+var_270], 0
0x1401cd7d9  mov     r9d, 20119h; samDesired
0x1401cd7df  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1401cd7e4  xor     r8d, r8d; ulOptions
0x1401cd7e7  lea     rdx, aSoftwareMicros_65; "Software\\Microsoft\\Provisioning\\Stat"...
0x1401cd7ee  mov     rcx, r12; hKey
0x1401cd7f1  call    cs:__imp_RegOpenKeyExW
0x1401cd7f8  nop     dword ptr [rax+rax+00h]
0x1401cd7fd  mov     rcx, [rsp+2B0h+var_270]; hKey
0x1401cd802  test    eax, eax
0x1401cd804  setz    cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1401cd80b  call    cs:__imp_RegCloseKey
0x1401cd812  nop     dword ptr [rax+rax+00h]
0x1401cd817  mov     cs:?s_HasRun@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA, bl; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1401cd81d  mov     cl, cs:?s_Redirection@?1??ProvIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ProvIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1401cd823  lea     rax, aSoftwareMicros_141; "SOFTWARE\\Microsoft\\Provisioning\\OOBE"...
0x1401cd82a  test    cl, cl
0x1401cd82c  mov     [rsp+2B0h+phkResult], rdi; phkResult
0x1401cd831  lea     rdx, aOsdataSoftware_1; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1401cd838  mov     r9d, ebx; samDesired
0x1401cd83b  cmovz   rdx, rax; lpSubKey
0x1401cd83f  mov     rcx, r12; hKey
0x1401cd842  xor     r8d, r8d; ulOptions
0x1401cd845  call    cs:__imp_RegOpenKeyExW
0x1401cd84c  nop     dword ptr [rax+rax+00h]
0x1401cd851  test    eax, eax
0x1401cd853  jnz     short loc_1401CD8A6
0x1401cd855  mov     rcx, [rsp+2B0h+var_258]; hKey
0x1401cd85a  lea     r9, [rsp+2B0h+var_270]; lpType
0x1401cd85f  mov     dword ptr [rsp+2B0h+var_270], eax
0x1401cd863  lea     rdx, aAftercleanpcpr; "AfterCleanPCProvisioningStatusCompleted"
0x1401cd86a  mov     dword ptr [rsp+2B0h+var_278], eax
0x1401cd86e  xor     r8d, r8d; lpReserved
0x1401cd871  lea     rax, [rsp+2B0h+var_260]
0x1401cd876  mov     [rsp+2B0h+var_260], 4
0x1401cd87e  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1401cd883  lea     rax, [rsp+2B0h+var_278]
0x1401cd888  mov     [rsp+2B0h+phkResult], rax; lpData
0x1401cd88d  call    cs:__imp_RegQueryValueExW
0x1401cd894  nop     dword ptr [rax+rax+00h]
0x1401cd899  test    eax, eax
0x1401cd89b  jnz     short loc_1401CD8A6
0x1401cd89d  xor     ecx, ecx
0x1401cd89f  cmp     dword ptr [rsp+2B0h+var_278], ebx
0x1401cd8a3  cmovz   ebx, ecx
0x1401cd8a6  lea     rcx, [rsp+2B0h+var_258]
0x1401cd8ab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401cd8b0  lea     rcx, [rsp+2B0h+var_250]
0x1401cd8b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401cd8ba  lea     rcx, [rsp+2B0h+hKey]
0x1401cd8bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401cd8c4  mov     eax, ebx
0x1401cd8c6  mov     rcx, [rbp+1B0h+var_30]
0x1401cd8cd  xor     rcx, rsp; StackCookie
0x1401cd8d0  call    __security_check_cookie
0x1401cd8d5  add     rsp, 298h
0x1401cd8dc  pop     r12
0x1401cd8de  pop     rdi
0x1401cd8df  pop     rbx
0x1401cd8e0  pop     rbp
0x1401cd8e1  retn
```
