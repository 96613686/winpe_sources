# PluginEnumerator::EnumeratePlugins(__MIDL___MIDL_itf_provisioningplugineng_0000_0000_0005,std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>,std::allocator<Microsoft::WRL::ComPtr<IProvisioningPlugin>>> *)

- ea: `0x1800b78b0`
- end: `0x1800b7bca`
- name: `?EnumeratePlugins@PluginEnumerator@@UEAAJW4__MIDL___MIDL_itf_provisioningplugineng_0000_0000_0005@@PEAV?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x18000592c`
- `0x180007bbc`
- `0x180008544`
- `0x18001e9a4`
- `0x18001ea00`
- `0x180023574`
- `0x1800235c8`
- `0x180047300`
- `0x1800b746c`
- `0x1800b76a0`
- `0x1800b7850`
- `0x1800b78b0`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b791c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b791c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b79f8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b79f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b7ac5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b7ac5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b7a88`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b7a88`

## string_xrefs

- `0x1800b790e`: `SOFTWARE\Microsoft\Provisioning\Plugin\Providers`
- `0x1800b7931`: `onecoreuap\admin\prov\plugineng\core\pluginenumerator.cpp`
- `0x1800b7996`: `onecoreuap\admin\prov\plugineng\core\pluginenumerator.cpp`
- `0x1800b7a3b`: `onecoreuap\admin\prov\plugineng\core\pluginenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PluginEnumerator::EnumeratePlugins(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  DWORD v8; // r14d
  BYTE *lpData; // rbx
  const char *v10; // r9
  unsigned int v11; // eax
  unsigned int v12; // ebx
  LPVOID v13; // rdi
  int (__fastcall *v14)(LPVOID, __int64 *); // rbx
  LPVOID v15; // rcx
  _QWORD *v16; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-298h]
  LPVOID ppv; // [rsp+40h] [rbp-278h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-270h] BYREF
  DWORD cchValueName; // [rsp+50h] [rbp-268h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-264h] BYREF
  BYTE *v22; // [rsp+58h] [rbp-260h] BYREF
  __int64 v23; // [rsp+60h] [rbp-258h] BYREF
  LPVOID v24; // [rsp+68h] [rbp-250h] BYREF
  GUID pclsid; // [rsp+70h] [rbp-248h] BYREF
  WCHAR ValueName[264]; // [rsp+80h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  hKey = 0;
  std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::clear(a3);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\Plugin\\Providers", 0, 0x20019u, &hKey);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x27,
           (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
           (const char *)v5,
           phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v6;
  }
  v8 = 0;
  try
  {
    while ( 1 )
    {
      cchValueName = 261;
      cbData = 78;
      lpData = (BYTE *)operator new[](0x4Eu, (const struct std::nothrow_t *)&std::nothrow);
      v22 = lpData;
      if ( !lpData )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
          (const char *)0x8007000ELL,
          phkResult);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942414LL;
      }
      v11 = RegEnumValueW(hKey, v8, ValueName, &cchValueName, 0, 0, lpData, &cbData);
      if ( v11 == 259 )
      {
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      if ( v11 != 234 )
      {
        if ( v11 )
        {
          v12 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x4C,
                  (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
                  (const char *)v11,
                  phkResult);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v22);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v12;
        }
        *(_WORD *)&lpData[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
        pclsid = 0;
        if ( CLSIDFromString((LPCOLESTR)lpData, &pclsid) >= 0 )
        {
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          if ( CoCreateInstance(&pclsid, 0, 0x17u, &GUID_f3bef5d5_b02a_43b5_9316_94aed0171a72, &ppv) >= 0
            && (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, a2) >= 0 )
          {
            v23 = 0;
            v13 = ppv;
            v14 = *(int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v23,
              0);
            if ( v14(v13, &v23) >= 0 )
            {
              v15 = ppv;
              ppv = 0;
              v24 = v15;
              v16 = *(_QWORD **)(a3 + 8);
              if ( v16 == *(_QWORD **)(a3 + 16) )
              {
                std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::_Emplace_reallocate<IProvisioningPlugin *>(
                  a3,
                  v16,
                  &v24);
              }
              else
              {
                *v16 = v15;
                if ( v15 )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 8LL))(v15);
                *(_QWORD *)(a3 + 8) += 8LL;
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        }
      }
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v22);
      ++v8;
    }
  }
  catch ( ... )
  {
    cchValueName = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x78,
                     (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\pluginenumerator.cpp",
                     v10);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return cchValueName;
  }
  return result;
}

```

## disassembly

```asm
0x1800b78b0  mov     [rsp+arg_0], rbx
0x1800b78b5  mov     [rsp+arg_18], rsi
0x1800b78ba  push    rdi
0x1800b78bb  push    r14
0x1800b78bd  push    r15
0x1800b78bf  sub     rsp, 2A0h
0x1800b78c6  mov     rax, cs:__security_cookie
0x1800b78cd  xor     rax, rsp
0x1800b78d0  mov     [rsp+2B8h+var_28], rax
0x1800b78d8  mov     rsi, r8
0x1800b78db  mov     r15d, edx
0x1800b78de  mov     [rsp+2B8h+hKey], 0
0x1800b78e7  mov     rcx, r8
0x1800b78ea  call    ?clear@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::clear(void)
0x1800b78ef  xor     edx, edx
0x1800b78f1  lea     rcx, [rsp+2B8h+hKey]
0x1800b78f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b78fb  lea     rax, [rsp+2B8h+hKey]
0x1800b7900  mov     [rsp+2B8h+phkResult], rax; int
0x1800b7905  mov     r9d, 20019h; samDesired
0x1800b790b  xor     r8d, r8d; ulOptions
0x1800b790e  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Provisioning\\Plug"...
0x1800b7915  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b791c  call    cs:__imp_RegOpenKeyExW
0x1800b7922  test    eax, eax
0x1800b7924  jz      short loc_1800B7955
0x1800b7926  mov     rcx, [rsp+2B8h]; this
0x1800b792e  mov     r9d, eax; char *
0x1800b7931  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b7938  mov     edx, 27h ; '''; void *
0x1800b793d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b7942  mov     ebx, eax
0x1800b7944  lea     rcx, [rsp+2B8h+hKey]
0x1800b7949  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b794e  mov     eax, ebx
0x1800b7950  jmp     loc_1800B7BA1
0x1800b7955  xor     r14d, r14d
0x1800b7958  mov     [rsp+2B8h+cchValueName], 105h
0x1800b7960  mov     [rsp+2B8h+cbData], 4Eh ; 'N'
0x1800b7968  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b796f  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x1800b7974  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b7979  mov     rbx, rax
0x1800b797c  mov     [rsp+2B8h+var_260], rax
0x1800b7981  test    rax, rax
0x1800b7984  jnz     short loc_1800B79C2
0x1800b7986  mov     rcx, [rsp+2B8h]; this
0x1800b798e  mov     ebx, 8007000Eh
0x1800b7993  mov     r9d, ebx; char *
0x1800b7996  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b799d  lea     edx, [rax+31h]; void *
0x1800b79a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b79a5  nop
0x1800b79a6  lea     rcx, [rsp+2B8h+var_260]
0x1800b79ab  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b79b0  nop
0x1800b79b1  lea     rcx, [rsp+2B8h+hKey]
0x1800b79b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b79bb  mov     eax, ebx
0x1800b79bd  jmp     loc_1800B7BA1
0x1800b79c2  lea     rax, [rsp+2B8h+cbData]
0x1800b79c7  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x1800b79cc  mov     [rsp+2B8h+lpData], rbx; lpData
0x1800b79d1  mov     [rsp+2B8h+lpType], 0; lpType
0x1800b79da  mov     [rsp+2B8h+phkResult], 0; unsigned int
0x1800b79e3  lea     r9, [rsp+2B8h+cchValueName]; lpcchValueName
0x1800b79e8  lea     r8, [rsp+2B8h+ValueName]; lpValueName
0x1800b79f0  mov     edx, r14d; dwIndex
0x1800b79f3  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1800b79f8  call    cs:__imp_RegEnumValueW
0x1800b79fe  cmp     eax, 103h
0x1800b7a03  jnz     short loc_1800B7A21
0x1800b7a05  lea     rcx, [rsp+2B8h+var_260]
0x1800b7a0a  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b7a0f  nop
0x1800b7a10  lea     rcx, [rsp+2B8h+hKey]
0x1800b7a15  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b7a1a  xor     eax, eax
0x1800b7a1c  jmp     loc_1800B7BA1
0x1800b7a21  cmp     eax, 0EAh
0x1800b7a26  jz      loc_1800B7B81
0x1800b7a2c  test    eax, eax
0x1800b7a2e  jz      short loc_1800B7A6A
0x1800b7a30  mov     rcx, [rsp+2B8h]; this
0x1800b7a38  mov     r9d, eax; char *
0x1800b7a3b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b7a42  mov     edx, 4Ch ; 'L'; void *
0x1800b7a47  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b7a4c  mov     ebx, eax
0x1800b7a4e  lea     rcx, [rsp+2B8h+var_260]
0x1800b7a53  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b7a58  nop
0x1800b7a59  lea     rcx, [rsp+2B8h+hKey]
0x1800b7a5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b7a63  mov     eax, ebx
0x1800b7a65  jmp     loc_1800B7BA1
0x1800b7a6a  mov     edx, [rsp+2B8h+cbData]
0x1800b7a6e  shr     rdx, 1
0x1800b7a71  xor     eax, eax
0x1800b7a73  mov     [rbx+rdx*2-2], ax
0x1800b7a78  xorps   xmm0, xmm0
0x1800b7a7b  movups  xmmword ptr [rsp+2B8h+pclsid.Data1], xmm0
0x1800b7a80  lea     rdx, [rsp+2B8h+pclsid]; pclsid
0x1800b7a85  mov     rcx, rbx; lpsz
0x1800b7a88  call    cs:__imp_CLSIDFromString
0x1800b7a8e  test    eax, eax
0x1800b7a90  js      loc_1800B7B81
0x1800b7a96  mov     [rsp+2B8h+ppv], 0
0x1800b7a9f  lea     rcx, [rsp+2B8h+ppv]
0x1800b7aa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7aa9  lea     rax, [rsp+2B8h+ppv]
0x1800b7aae  mov     [rsp+2B8h+phkResult], rax; ppv
0x1800b7ab3  lea     r9, _GUID_f3bef5d5_b02a_43b5_9316_94aed0171a72; riid
0x1800b7aba  xor     edx, edx; pUnkOuter
0x1800b7abc  lea     r8d, [rdx+17h]; dwClsContext
0x1800b7ac0  lea     rcx, [rsp+2B8h+pclsid]; rclsid
0x1800b7ac5  call    cs:__imp_CoCreateInstance
0x1800b7acb  test    eax, eax
0x1800b7acd  js      loc_1800B7B76
0x1800b7ad3  mov     rcx, [rsp+2B8h+ppv]
0x1800b7ad8  mov     rax, [rcx]
0x1800b7adb  mov     edx, r15d
0x1800b7ade  mov     rax, [rax+38h]
0x1800b7ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ae7  test    eax, eax
0x1800b7ae9  js      loc_1800B7B76
0x1800b7aef  mov     [rsp+2B8h+var_258], 0
0x1800b7af8  mov     rdi, [rsp+2B8h+ppv]
0x1800b7afd  mov     rax, [rdi]
0x1800b7b00  mov     rbx, [rax+18h]
0x1800b7b04  xor     edx, edx
0x1800b7b06  lea     rcx, [rsp+2B8h+var_258]
0x1800b7b0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b7b10  lea     rdx, [rsp+2B8h+var_258]
0x1800b7b15  mov     rcx, rdi
0x1800b7b18  mov     rax, rbx
0x1800b7b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7b20  test    eax, eax
0x1800b7b22  js      short loc_1800B7B6B
0x1800b7b24  mov     rcx, [rsp+2B8h+ppv]
0x1800b7b29  mov     [rsp+2B8h+ppv], 0
0x1800b7b32  mov     [rsp+2B8h+var_250], rcx
0x1800b7b37  mov     rdx, [rsi+8]
0x1800b7b3b  cmp     rdx, [rsi+10h]
0x1800b7b3f  jz      short loc_1800B7B5D
0x1800b7b41  mov     [rdx], rcx
0x1800b7b44  test    rcx, rcx
0x1800b7b47  jz      short loc_1800B7B56
0x1800b7b49  mov     rax, [rcx]
0x1800b7b4c  mov     rax, [rax+8]
0x1800b7b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7b55  nop
0x1800b7b56  add     qword ptr [rsi+8], 8
0x1800b7b5b  jmp     short loc_1800B7B6B
0x1800b7b5d  lea     r8, [rsp+2B8h+var_250]
0x1800b7b62  mov     rcx, rsi
0x1800b7b65  call    ??$_Emplace_reallocate@PEAUIProvisioningPlugin@@@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@QEAV234@$$QEAPEAUIProvisioningPlugin@@@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::_Emplace_reallocate<IProvisioningPlugin *>(Microsoft::WRL::ComPtr<IProvisioningPlugin> * const,IProvisioningPlugin * &&)
0x1800b7b6a  nop
0x1800b7b6b  lea     rcx, [rsp+2B8h+var_258]
0x1800b7b70  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b7b75  nop
0x1800b7b76  lea     rcx, [rsp+2B8h+ppv]
0x1800b7b7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b7b80  nop
0x1800b7b81  lea     rcx, [rsp+2B8h+var_260]
0x1800b7b86  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b7b8b  inc     r14d
0x1800b7b8e  jmp     loc_1800B7958
0x1800b7b93  lea     rcx, [rsp+2B8h+hKey]
0x1800b7b98  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b7b9d  mov     eax, [rsp+2B8h+cchValueName]
0x1800b7ba1  mov     rcx, [rsp+2B8h+var_28]
0x1800b7ba9  xor     rcx, rsp; StackCookie
0x1800b7bac  call    __security_check_cookie
0x1800b7bb1  lea     r11, [rsp+2B8h+var_18]
0x1800b7bb9  mov     rbx, [r11+20h]
0x1800b7bbd  mov     rsi, [r11+38h]
0x1800b7bc1  mov     rsp, r11
0x1800b7bc4  pop     r15
0x1800b7bc6  pop     r14
0x1800b7bc8  pop     rdi
0x1800b7bc9  retn
```
