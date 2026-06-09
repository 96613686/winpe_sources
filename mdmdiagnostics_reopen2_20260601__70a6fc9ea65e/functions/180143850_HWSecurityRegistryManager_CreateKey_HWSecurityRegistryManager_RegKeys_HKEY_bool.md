# HWSecurityRegistryManager::CreateKey(HWSecurityRegistryManager::RegKeys,HKEY__ * *,bool *)

- ea: `0x180143850`
- end: `0x180143a32`
- name: `?CreateKey@HWSecurityRegistryManager@@SAJW4RegKeys@1@PEAPEAUHKEY__@@PEA_N@Z`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801419e4`

## callees

- `0x180019080`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1801433fc`
- `0x180143508`
- `0x180143800`
- `0x180143850`
- `0x180143b10`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1801439ff`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1801439ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801438d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801438d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180143955`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180143955`

## string_xrefs

- `0x1801439ae`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::CreateKey(__int64 a1)
{
  REGSAM samDesired; // ebx
  DWORD v2; // edi
  __int64 KeyPath; // rax
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-118h]
  DWORD dwDisposition; // [rsp+50h] [rbp-E8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-E0h] BYREF
  int v11; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE v12[16]; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+78h] [rbp-C0h]
  _BYTE v14[96]; // [rsp+90h] [rbp-A8h] BYREF
  DWORD v15; // [rsp+F0h] [rbp-48h]
  REGSAM v16; // [rsp+F4h] [rbp-44h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  hKey = 0;
  dwDisposition = 0;
  v11 = 8;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    a1,
    v12,
    &v11);
  if ( *(_BYTE *)(v13 + 25) || *(_DWORD *)(v13 + 32) > 8u )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    return dwDisposition;
  }
  else
  {
    HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
      (HWSecurityRegistryManager::RegistryKeyEntry *)v14,
      (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v13 + 40));
    hKey = 0;
    samDesired = v16;
    v2 = v15;
    KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v14, v12);
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, v2, samDesired, 0, &hKey, &dwDisposition);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    std::wstring::_Tidy_deallocate(v12);
    if ( (v6 & 0x80000000) == 0 )
    {
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
    else if ( v6 == -2147024894 )
    {
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147942402LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
        (const char *)v6,
        dwOptions);
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v6;
    }
  }
}

```

## disassembly

```asm
0x180143850  mov     [rsp+arg_0], rbx
0x180143855  push    rdi
0x180143856  sub     rsp, 130h
0x18014385d  mov     rax, cs:__security_cookie
0x180143864  xor     rax, rsp
0x180143867  mov     [rsp+138h+var_18], rax
0x18014386f  mov     [rsp+138h+hKey], 0
0x180143878  mov     [rsp+138h+dwDisposition], 0
0x180143880  mov     [rsp+138h+var_D8], 8
0x180143888  lea     r8, [rsp+138h+var_D8]
0x18014388d  lea     rdx, [rsp+138h+var_D0]
0x180143892  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x180143897  mov     rdx, [rsp+138h+var_C0]
0x18014389c  cmp     byte ptr [rdx+19h], 0
0x1801438a0  jnz     loc_1801439F8
0x1801438a6  cmp     dword ptr [rdx+20h], 8
0x1801438aa  ja      loc_1801439F8
0x1801438b0  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x1801438b4  lea     rcx, [rsp+138h+var_A8]; this
0x1801438bc  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1801438c1  nop
0x1801438c2  mov     rbx, [rsp+138h+hKey]
0x1801438c7  test    rbx, rbx
0x1801438ca  jz      short loc_1801438EF
0x1801438cc  lea     rcx, [rsp+138h+var_D8]; this
0x1801438d1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801438d6  mov     rcx, rbx; hKey
0x1801438d9  call    cs:__imp_RegCloseKey
0x1801438e0  nop     dword ptr [rax+rax+00h]
0x1801438e5  lea     rcx, [rsp+138h+var_D8]; this
0x1801438ea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801438ef  mov     [rsp+138h+hKey], 0
0x1801438f8  mov     ebx, [rsp+138h+var_44]
0x1801438ff  mov     edi, [rsp+138h+var_48]
0x180143906  lea     rdx, [rsp+138h+var_D0]
0x18014390b  lea     rcx, [rsp+138h+var_A8]
0x180143913  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x180143918  mov     rcx, rax
0x18014391b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180143920  lea     rcx, [rsp+138h+dwDisposition]
0x180143925  mov     [rsp+138h+lpdwDisposition], rcx; lpdwDisposition
0x18014392a  lea     rcx, [rsp+138h+hKey]
0x18014392f  mov     [rsp+138h+phkResult], rcx; phkResult
0x180143934  mov     [rsp+138h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18014393d  mov     [rsp+138h+samDesired], ebx; samDesired
0x180143941  mov     [rsp+138h+dwOptions], edi; int
0x180143945  xor     r9d, r9d; lpClass
0x180143948  xor     r8d, r8d; Reserved
0x18014394b  mov     rdx, rax; lpSubKey
0x18014394e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180143955  call    cs:__imp_RegCreateKeyExW
0x18014395c  nop     dword ptr [rax+rax+00h]
0x180143961  mov     ebx, eax
0x180143963  test    eax, eax
0x180143965  jle     short loc_180143970
0x180143967  movzx   ebx, ax
0x18014396a  or      ebx, 80070000h
0x180143970  lea     rcx, [rsp+138h+var_D0]
0x180143975  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014397a  test    ebx, ebx
0x18014397c  jns     short loc_1801439DC
0x18014397e  mov     edi, 80070002h
0x180143983  cmp     ebx, edi
0x180143985  jnz     short loc_1801439A3
0x180143987  lea     rcx, [rsp+138h+var_A8]; this
0x18014398f  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180143994  nop
0x180143995  lea     rcx, [rsp+138h+hKey]
0x18014399a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014399f  mov     eax, edi
0x1801439a1  jmp     short loc_180143A10
0x1801439a3  mov     rcx, [rsp+138h]; this
0x1801439ab  mov     r9d, ebx; char *
0x1801439ae  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x1801439b5  mov     edx, 189h; void *
0x1801439ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801439bf  nop
0x1801439c0  lea     rcx, [rsp+138h+var_A8]; this
0x1801439c8  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x1801439cd  nop
0x1801439ce  lea     rcx, [rsp+138h+hKey]
0x1801439d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801439d8  mov     eax, ebx
0x1801439da  jmp     short loc_180143A10
0x1801439dc  lea     rcx, [rsp+138h+var_A8]; this
0x1801439e4  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x1801439e9  nop
0x1801439ea  lea     rcx, [rsp+138h+hKey]
0x1801439ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801439f4  xor     eax, eax
0x1801439f6  jmp     short loc_180143A10
0x1801439f8  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1801439ff  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180143a06  nop     dword ptr [rax+rax+00h]
0x180143a0b  nop
0x180143a0c  mov     eax, [rsp+138h+dwDisposition]
0x180143a10  mov     rcx, [rsp+138h+var_18]
0x180143a18  xor     rcx, rsp; StackCookie
0x180143a1b  call    __security_check_cookie
0x180143a20  mov     rbx, [rsp+138h+arg_0]
0x180143a28  add     rsp, 130h
0x180143a2f  pop     rdi
0x180143a30  retn
```
