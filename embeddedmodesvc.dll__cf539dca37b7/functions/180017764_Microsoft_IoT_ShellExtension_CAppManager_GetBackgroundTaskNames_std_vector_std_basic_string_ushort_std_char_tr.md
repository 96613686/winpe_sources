# Microsoft::IoT::ShellExtension::CAppManager::GetBackgroundTaskNames(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180017764`
- end: `0x180017ab1`
- name: `?GetBackgroundTaskNames@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011c34`

## callees

- `0x180002b10`
- `0x18000430c`
- `0x180004580`
- `0x180005fc4`
- `0x180009f7c`
- `0x18000a730`
- `0x18000fffc`
- `0x180010558`
- `0x180014f58`
- `0x180014f78`
- `0x180017764`
- `0x180017ab8`
- `0x180017adc`
- `0x180017cf4`
- `0x180017d74`
- `0x180017da4`
- `0x180017ddc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800179e7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800179e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017922`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800177d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800177d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017819`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017819`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::IoT::ShellExtension::CAppManager::GetBackgroundTaskNames(__int64 a1)
{
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  unsigned int v6; // eax
  unsigned int v7; // r8d
  DWORD i; // ebx
  unsigned int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  int phkResult; // [rsp+20h] [rbp-D8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-D8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-D8h]
  DWORD cchValueName; // [rsp+60h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-90h] BYREF
  _WORD v17[2]; // [rsp+70h] [rbp-88h] BYREF
  DWORD cValues; // [rsp+74h] [rbp-84h] BYREF
  LPWSTR lpValueName[2]; // [rsp+78h] [rbp-80h] BYREF
  __int64 v20; // [rsp+88h] [rbp-70h]
  DWORD cbMaxValueNameLen; // [rsp+90h] [rbp-68h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-58h]
  _BYTE v23[32]; // [rsp+A8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v22 = a1;
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(lpValueName);
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  std::vector<std::wstring>::clear(a1);
  hKey = 0;
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180026650);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 == 2 )
    {
      if ( lpValueName[0] )
      {
        std::_Deallocate<16>(lpValueName[0], 2 * ((signed __int64)(v20 - (unsigned __int64)lpValueName[0]) >> 1));
        *(_OWORD *)lpValueName = 0;
        v20 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\iotappmanager.cpp",
        (const char *)v4,
        phkResult);
    if ( lpValueName[0] )
    {
      std::_Deallocate<16>(lpValueName[0], 2 * ((signed __int64)(v20 - (unsigned __int64)lpValueName[0]) >> 1));
      *(_OWORD *)lpValueName = 0;
      v20 = 0;
    }
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v6 )
  {
    v4 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xCD, v7, (const char *)v6, phkResulta);
    if ( lpValueName[0] )
    {
      std::_Deallocate<16>(lpValueName[0], 2 * ((signed __int64)(v20 - (unsigned __int64)lpValueName[0]) >> 1));
      *(_OWORD *)lpValueName = 0;
      v20 = 0;
    }
    goto LABEL_12;
  }
  std::vector<std::wstring>::reserve(a1, cValues);
  for ( i = 0; i < cValues; ++i )
  {
    cchValueName = cbMaxValueNameLen + 1;
    v17[0] = 0;
    std::vector<unsigned short>::assign(lpValueName, cbMaxValueNameLen + 1, v17);
    v9 = RegEnumValueW(hKey, i, lpValueName[0], &cchValueName, 0, 0, 0, 0);
    if ( v9 && v9 != 259 )
      wil::details::in1diag3::Throw_Win32(retaddr, v10, v11, (const char *)v9, phkResultb);
    std::wstring::wstring(v23, lpValueName[0]);
    std::vector<std::wstring>::push_back(a1, v23);
    std::wstring::_Tidy_deallocate(v23);
  }
  if ( lpValueName[0] )
  {
    std::_Deallocate<16>(lpValueName[0], 2 * ((signed __int64)(v20 - (unsigned __int64)lpValueName[0]) >> 1));
    *(_OWORD *)lpValueName = 0;
    v20 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180017764  push    rbx
0x180017766  push    rsi
0x180017767  push    rdi
0x180017768  push    r14
0x18001776a  sub     rsp, 0D8h
0x180017771  mov     rax, cs:__security_cookie
0x180017778  xor     rax, rsp
0x18001777b  mov     [rsp+0F8h+var_30], rax
0x180017783  mov     rdi, rcx
0x180017786  mov     [rsp+0F8h+var_58], rcx
0x18001778e  xor     r14d, r14d
0x180017791  mov     esi, r14d
0x180017794  mov     [rsp+0F8h+hKey], r14
0x180017799  lea     rcx, [rsp+0F8h+lpValueName]
0x18001779e  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x1800177a3  nop
0x1800177a4  mov     [rsp+0F8h+cValues], r14d
0x1800177a9  mov     [rsp+0F8h+cbMaxValueNameLen], r14d
0x1800177b1  mov     [rsp+0F8h+cchValueName], r14d
0x1800177b6  mov     rcx, rdi
0x1800177b9  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x1800177be  mov     rbx, [rsp+0F8h+hKey]
0x1800177c3  test    rbx, rbx
0x1800177c6  jz      short loc_1800177EB
0x1800177c8  lea     rcx, [rsp+0F8h+var_60]; this
0x1800177d0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800177d5  mov     rcx, rbx; hKey
0x1800177d8  call    cs:__imp_RegCloseKey
0x1800177de  lea     rcx, [rsp+0F8h+var_60]; this
0x1800177e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800177eb  mov     [rsp+0F8h+hKey], r14
0x1800177f0  lea     rcx, qword_180026650
0x1800177f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800177fc  mov     rdx, rax; lpSubKey
0x1800177ff  lea     rax, [rsp+0F8h+hKey]
0x180017804  mov     [rsp+0F8h+phkResult], rax; int
0x180017809  mov     r9d, 20019h; samDesired
0x18001780f  xor     r8d, r8d; ulOptions
0x180017812  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017819  call    cs:__imp_RegOpenKeyExW
0x18001781f  mov     ebx, eax
0x180017821  test    eax, eax
0x180017823  jz      loc_1800178E0
0x180017829  cmp     eax, 2
0x18001782c  jnz     short loc_180017870
0x18001782e  mov     rcx, [rsp+0F8h+lpValueName]
0x180017833  test    rcx, rcx
0x180017836  jz      short loc_18001785F
0x180017838  mov     rdx, [rsp+0F8h+var_70]
0x180017840  sub     rdx, rcx
0x180017843  sar     rdx, 1
0x180017846  add     rdx, rdx
0x180017849  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001784e  xorps   xmm0, xmm0
0x180017851  movdqu  xmmword ptr [rsp+0F8h+lpValueName], xmm0
0x180017857  mov     [rsp+0F8h+var_70], r14
0x18001785f  lea     rcx, [rsp+0F8h+hKey]
0x180017864  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017869  xor     eax, eax
0x18001786b  jmp     loc_180017A93
0x180017870  test    eax, eax
0x180017872  jle     short loc_18001787D
0x180017874  movzx   ebx, ax
0x180017877  or      ebx, 80070000h
0x18001787d  test    ebx, ebx
0x18001787f  jns     short loc_18001789E
0x180017881  mov     rcx, [rsp+0F8h]; this
0x180017889  mov     r9d, ebx; char *
0x18001788c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180017893  mov     edx, 0CBh; void *
0x180017898  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001789d  nop
0x18001789e  mov     rcx, [rsp+0F8h+lpValueName]
0x1800178a3  test    rcx, rcx
0x1800178a6  jz      short loc_1800178CF
0x1800178a8  mov     rdx, [rsp+0F8h+var_70]
0x1800178b0  sub     rdx, rcx
0x1800178b3  sar     rdx, 1
0x1800178b6  add     rdx, rdx
0x1800178b9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800178be  xorps   xmm0, xmm0
0x1800178c1  movdqu  xmmword ptr [rsp+0F8h+lpValueName], xmm0
0x1800178c7  mov     [rsp+0F8h+var_70], r14
0x1800178cf  lea     rcx, [rsp+0F8h+hKey]
0x1800178d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800178d9  mov     eax, ebx
0x1800178db  jmp     loc_180017A93
0x1800178e0  mov     [rsp+0F8h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800178e5  mov     [rsp+0F8h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800178ea  mov     [rsp+0F8h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800178ef  lea     rax, [rsp+0F8h+cbMaxValueNameLen]
0x1800178f7  mov     [rsp+0F8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800178fc  lea     rax, [rsp+0F8h+cValues]
0x180017901  mov     [rsp+0F8h+lpcValues], rax; lpcValues
0x180017906  mov     [rsp+0F8h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18001790b  mov     [rsp+0F8h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180017910  mov     [rsp+0F8h+phkResult], r14; unsigned int
0x180017915  xor     r9d, r9d; lpReserved
0x180017918  xor     r8d, r8d; lpcchClass
0x18001791b  xor     edx, edx; lpClass
0x18001791d  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180017922  call    cs:__imp_RegQueryInfoKeyW
0x180017928  test    eax, eax
0x18001792a  jz      short loc_180017985
0x18001792c  mov     rcx, [rsp+0F8h]; this
0x180017934  mov     r9d, eax; char *
0x180017937  mov     edx, 0CDh; void *
0x18001793c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017941  mov     ebx, eax
0x180017943  mov     rcx, [rsp+0F8h+lpValueName]
0x180017948  test    rcx, rcx
0x18001794b  jz      short loc_180017974
0x18001794d  mov     rdx, [rsp+0F8h+var_70]
0x180017955  sub     rdx, rcx
0x180017958  sar     rdx, 1
0x18001795b  add     rdx, rdx
0x18001795e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017963  xorps   xmm0, xmm0
0x180017966  movdqu  xmmword ptr [rsp+0F8h+lpValueName], xmm0
0x18001796c  mov     [rsp+0F8h+var_70], r14
0x180017974  lea     rcx, [rsp+0F8h+hKey]
0x180017979  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001797e  mov     eax, ebx
0x180017980  jmp     loc_180017A93
0x180017985  mov     edx, [rsp+0F8h+cValues]
0x180017989  mov     rcx, rdi
0x18001798c  call    ?reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::wstring>::reserve(unsigned __int64)
0x180017991  mov     ebx, r14d
0x180017994  cmp     ebx, [rsp+0F8h+cValues]
0x180017998  jnb     loc_180017A40
0x18001799e  mov     ecx, [rsp+0F8h+cbMaxValueNameLen]
0x1800179a5  inc     ecx
0x1800179a7  mov     [rsp+0F8h+cchValueName], ecx
0x1800179ab  mov     [rsp+0F8h+var_88], r14w
0x1800179b1  mov     edx, ecx
0x1800179b3  lea     r8, [rsp+0F8h+var_88]
0x1800179b8  lea     rcx, [rsp+0F8h+lpValueName]
0x1800179bd  call    ?assign@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KAEBG@Z; std::vector<ushort>::assign(unsigned __int64,ushort const &)
0x1800179c2  mov     [rsp+0F8h+lpcValues], r14; lpcbData
0x1800179c7  mov     [rsp+0F8h+lpcbMaxClassLen], r14; lpData
0x1800179cc  mov     [rsp+0F8h+lpcbMaxSubKeyLen], r14; lpType
0x1800179d1  mov     [rsp+0F8h+phkResult], r14; unsigned int
0x1800179d6  lea     r9, [rsp+0F8h+cchValueName]; lpcchValueName
0x1800179db  mov     r8, [rsp+0F8h+lpValueName]; lpValueName
0x1800179e0  mov     edx, ebx; dwIndex
0x1800179e2  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800179e7  call    cs:__imp_RegEnumValueW
0x1800179ed  test    eax, eax
0x1800179ef  jz      short loc_180017A08
0x1800179f1  cmp     eax, 103h
0x1800179f6  jz      short loc_180017A08
0x1800179f8  mov     rcx, [rsp+0F8h]; this
0x180017a00  mov     r9d, eax; char *
0x180017a03  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180017a08  mov     rdx, [rsp+0F8h+lpValueName]
0x180017a0d  lea     rcx, [rsp+0F8h+var_50]
0x180017a15  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180017a1a  nop
0x180017a1b  lea     rdx, [rsp+0F8h+var_50]
0x180017a23  mov     rcx, rdi
0x180017a26  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180017a2b  nop
0x180017a2c  lea     rcx, [rsp+0F8h+var_50]
0x180017a34  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017a39  inc     ebx
0x180017a3b  jmp     loc_180017994
0x180017a40  mov     rcx, [rsp+0F8h+lpValueName]
0x180017a45  test    rcx, rcx
0x180017a48  jz      short loc_180017A71
0x180017a4a  mov     rdx, [rsp+0F8h+var_70]
0x180017a52  sub     rdx, rcx
0x180017a55  sar     rdx, 1
0x180017a58  add     rdx, rdx
0x180017a5b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017a60  xorps   xmm0, xmm0
0x180017a63  movdqu  xmmword ptr [rsp+0F8h+lpValueName], xmm0
0x180017a69  mov     [rsp+0F8h+var_70], r14
0x180017a71  lea     rcx, [rsp+0F8h+hKey]
0x180017a76  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017a7b  nop
0x180017a7c  jmp     short loc_180017A91
0x180017a7e  jmp     short $+2
0x180017a80  mov     rcx, [rsp+0F8h+var_58]
0x180017a88  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180017a8d  mov     esi, [rsp+0F8h+cchValueName]
0x180017a91  mov     eax, esi
0x180017a93  mov     rcx, [rsp+0F8h+var_30]
0x180017a9b  xor     rcx, rsp; StackCookie
0x180017a9e  call    __security_check_cookie
0x180017aa3  add     rsp, 0D8h
0x180017aaa  pop     r14
0x180017aac  pop     rdi
0x180017aad  pop     rsi
0x180017aae  pop     rbx
0x180017aaf  retn
```
