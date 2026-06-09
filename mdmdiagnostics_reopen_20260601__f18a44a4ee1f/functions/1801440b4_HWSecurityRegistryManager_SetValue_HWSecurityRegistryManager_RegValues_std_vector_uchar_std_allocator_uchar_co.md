# HWSecurityRegistryManager::SetValue(HWSecurityRegistryManager::RegValues,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1801440b4`
- end: `0x1801443c1`
- name: `?SetValue@HWSecurityRegistryManager@@SAJW4RegValues@1@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180143fb0`

## callees

- `0x180019080`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x180105294`
- `0x1801433fc`
- `0x180143454`
- `0x180143508`
- `0x180143800`
- `0x180143b10`
- `0x180143f88`
- `0x1801440b4`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180144358`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18014436b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18014437f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180144392`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180144358`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18014436b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18014437f`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180144392`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801442d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801442d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180144166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180144166`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801441e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801441e3`

## string_xrefs

- `0x18014420a`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`
- `0x180144307`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::SetValue(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // r10d
  HKEY v6; // rdi
  REGSAM samDesired; // edi
  DWORD v8; // r14d
  __int64 KeyPath; // rax
  const WCHAR *v10; // rax
  unsigned int v11; // edi
  __int64 v12; // rcx
  unsigned int v13; // ebx
  const BYTE *v15; // rdi
  DWORD v16; // esi
  __int64 v17; // rcx
  __int64 v18; // r10
  DWORD v19; // ebx
  __int64 ValueName; // rax
  const WCHAR *v21; // rax
  LSTATUS v22; // eax
  unsigned int v23; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-148h]
  int dwOptionsa; // [rsp+20h] [rbp-148h]
  unsigned int v26; // [rsp+50h] [rbp-118h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-110h] BYREF
  _BYTE v28[16]; // [rsp+60h] [rbp-108h] BYREF
  __int64 v29; // [rsp+70h] [rbp-F8h]
  _BYTE v30[32]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v31[96]; // [rsp+A0h] [rbp-C8h] BYREF
  DWORD v32; // [rsp+100h] [rbp-68h]
  REGSAM v33; // [rsp+104h] [rbp-64h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v3 = a1;
  hKey = 0;
  v26 = a1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
    goto LABEL_21;
  v26 = *(_DWORD *)(v29 + 40);
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    v4,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v5 < *(_DWORD *)(v29 + 32) )
  {
LABEL_20:
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_21:
    std::_Xout_of_range("invalid map<K, T> key");
    return v26;
  }
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v31,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v29 + 40));
  v6 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
    RegCloseKey(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
  }
  hKey = 0;
  samDesired = v33;
  v8 = v32;
  KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v31, v28);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, v8, samDesired, 0, &hKey, 0);
  std::wstring::_Tidy_deallocate(v28);
  if ( v11 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x27A,
            (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
            (const char *)v11,
            dwOptions);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v13;
  }
  v15 = *(const BYTE **)a2;
  v16 = *(_DWORD *)(a2 + 8) - *(_QWORD *)a2;
  v26 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v12,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
  {
LABEL_19:
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_20;
  }
  v26 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v17,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_19;
  }
  v19 = *(_DWORD *)(v18 + 80);
  ValueName = HWSecurityRegistryManager::RegistryValueEntry::GetValueName(v29 + 40, v30);
  v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ValueName);
  v22 = RegSetValueExW(hKey, v21, 0, v19, v15, v16);
  v23 = v22;
  if ( v22 > 0 )
    v23 = (unsigned __int16)v22 | 0x80070000;
  std::wstring::_Tidy_deallocate(v30);
  if ( (v23 & 0x80000000) == 0 )
  {
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
      (const char *)v23,
      dwOptionsa);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v23;
  }
}

```

## disassembly

```asm
0x1801440b4  push    rbx
0x1801440b6  push    rsi
0x1801440b7  push    rdi
0x1801440b8  push    r14
0x1801440ba  sub     rsp, 148h
0x1801440c1  mov     rax, cs:__security_cookie
0x1801440c8  xor     rax, rsp
0x1801440cb  mov     [rsp+168h+var_38], rax
0x1801440d3  mov     rsi, rdx
0x1801440d6  mov     ebx, ecx
0x1801440d8  mov     [rsp+168h+hKey], 0
0x1801440e1  mov     [rsp+168h+var_118], ecx
0x1801440e5  lea     r8, [rsp+168h+var_118]
0x1801440ea  lea     rdx, [rsp+168h+var_108]
0x1801440ef  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x1801440f4  mov     rdx, [rsp+168h+var_F8]
0x1801440f9  cmp     byte ptr [rdx+19h], 0
0x1801440fd  jnz     loc_18014438B
0x180144103  cmp     ebx, [rdx+20h]
0x180144106  jb      loc_18014438B
0x18014410c  mov     r10d, [rdx+28h]
0x180144110  mov     [rsp+168h+var_118], r10d
0x180144115  lea     r8, [rsp+168h+var_118]
0x18014411a  lea     rdx, [rsp+168h+var_108]
0x18014411f  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x180144124  mov     rdx, [rsp+168h+var_F8]
0x180144129  cmp     byte ptr [rdx+19h], 0
0x18014412d  jnz     loc_180144378
0x180144133  cmp     r10d, [rdx+20h]
0x180144137  jb      loc_180144378
0x18014413d  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x180144141  lea     rcx, [rsp+168h+var_C8]; this
0x180144149  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18014414e  nop
0x18014414f  mov     rdi, [rsp+168h+hKey]
0x180144154  test    rdi, rdi
0x180144157  jz      short loc_18014417C
0x180144159  lea     rcx, [rsp+168h+var_118]; this
0x18014415e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180144163  mov     rcx, rdi; hKey
0x180144166  call    cs:__imp_RegCloseKey
0x18014416d  nop     dword ptr [rax+rax+00h]
0x180144172  lea     rcx, [rsp+168h+var_118]; this
0x180144177  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18014417c  mov     [rsp+168h+hKey], 0
0x180144185  mov     edi, [rsp+168h+var_64]
0x18014418c  mov     r14d, [rsp+168h+var_68]
0x180144194  lea     rdx, [rsp+168h+var_108]
0x180144199  lea     rcx, [rsp+168h+var_C8]
0x1801441a1  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x1801441a6  mov     rcx, rax
0x1801441a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801441ae  mov     [rsp+168h+lpdwDisposition], 0; lpdwDisposition
0x1801441b7  lea     rcx, [rsp+168h+hKey]
0x1801441bc  mov     [rsp+168h+phkResult], rcx; phkResult
0x1801441c1  mov     [rsp+168h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801441ca  mov     [rsp+168h+samDesired], edi; samDesired
0x1801441ce  mov     [rsp+168h+dwOptions], r14d; unsigned int
0x1801441d3  xor     r9d, r9d; lpClass
0x1801441d6  xor     r8d, r8d; Reserved
0x1801441d9  mov     rdx, rax; lpSubKey
0x1801441dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801441e3  call    cs:__imp_RegCreateKeyExW
0x1801441ea  nop     dword ptr [rax+rax+00h]
0x1801441ef  mov     edi, eax
0x1801441f1  lea     rcx, [rsp+168h+var_108]
0x1801441f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801441fb  test    edi, edi
0x1801441fd  jz      short loc_18014423C
0x1801441ff  mov     rcx, [rsp+168h]; this
0x180144207  mov     r9d, edi; char *
0x18014420a  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x180144211  mov     edx, 27Ah; void *
0x180144216  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18014421b  mov     ebx, eax
0x18014421d  lea     rcx, [rsp+168h+var_C8]; this
0x180144225  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18014422a  nop
0x18014422b  lea     rcx, [rsp+168h+hKey]
0x180144230  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180144235  mov     eax, ebx
0x180144237  jmp     loc_1801443A3
0x18014423c  mov     rdi, [rsi]
0x18014423f  mov     esi, [rsi+8]
0x180144242  sub     esi, edi
0x180144244  mov     [rsp+168h+var_118], ebx
0x180144248  lea     r8, [rsp+168h+var_118]
0x18014424d  lea     rdx, [rsp+168h+var_108]
0x180144252  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180144257  mov     r10, [rsp+168h+var_F8]
0x18014425c  cmp     byte ptr [r10+19h], 0
0x180144261  jnz     loc_180144364
0x180144267  cmp     ebx, [r10+20h]
0x18014426b  jb      loc_180144364
0x180144271  mov     [rsp+168h+var_118], ebx
0x180144275  lea     r8, [rsp+168h+var_118]
0x18014427a  lea     rdx, [rsp+168h+var_108]
0x18014427f  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180144284  mov     rcx, [rsp+168h+var_F8]
0x180144289  cmp     byte ptr [rcx+19h], 0
0x18014428d  jnz     loc_180144351
0x180144293  cmp     ebx, [rcx+20h]
0x180144296  jb      loc_180144351
0x18014429c  mov     ebx, [r10+50h]
0x1801442a0  add     rcx, 28h ; '('
0x1801442a4  lea     rdx, [rsp+168h+var_E8]
0x1801442ac  call    ?GetValueName@RegistryValueEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryValueEntry::GetValueName(void)
0x1801442b1  mov     rcx, rax
0x1801442b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801442b9  mov     [rsp+168h+samDesired], esi; cbData
0x1801442bd  mov     qword ptr [rsp+168h+dwOptions], rdi; int
0x1801442c2  mov     r9d, ebx; dwType
0x1801442c5  xor     r8d, r8d; Reserved
0x1801442c8  mov     rdx, rax; lpValueName
0x1801442cb  mov     rcx, [rsp+168h+hKey]; hKey
0x1801442d0  call    cs:__imp_RegSetValueExW
0x1801442d7  nop     dword ptr [rax+rax+00h]
0x1801442dc  mov     ebx, eax
0x1801442de  test    eax, eax
0x1801442e0  jle     short loc_1801442EB
0x1801442e2  movzx   ebx, ax
0x1801442e5  or      ebx, 80070000h
0x1801442eb  lea     rcx, [rsp+168h+var_E8]
0x1801442f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801442f8  test    ebx, ebx
0x1801442fa  jns     short loc_180144335
0x1801442fc  mov     rcx, [rsp+168h]; this
0x180144304  mov     r9d, ebx; char *
0x180144307  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x18014430e  mov     edx, 283h; void *
0x180144313  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144318  nop
0x180144319  lea     rcx, [rsp+168h+var_C8]; this
0x180144321  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180144326  nop
0x180144327  lea     rcx, [rsp+168h+hKey]
0x18014432c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180144331  mov     eax, ebx
0x180144333  jmp     short loc_1801443A3
0x180144335  lea     rcx, [rsp+168h+var_C8]; this
0x18014433d  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180144342  nop
0x180144343  lea     rcx, [rsp+168h+hKey]
0x180144348  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014434d  xor     eax, eax
0x18014434f  jmp     short loc_1801443A3
0x180144351  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180144358  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18014435f  nop     dword ptr [rax+rax+00h]
0x180144364  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18014436b  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180144372  nop     dword ptr [rax+rax+00h]
0x180144377  nop
0x180144378  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18014437f  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180144386  nop     dword ptr [rax+rax+00h]
0x18014438b  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180144392  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180144399  nop     dword ptr [rax+rax+00h]
0x18014439e  nop
0x18014439f  mov     eax, [rsp+168h+var_118]
0x1801443a3  mov     rcx, [rsp+168h+var_38]
0x1801443ab  xor     rcx, rsp; StackCookie
0x1801443ae  call    __security_check_cookie
0x1801443b3  add     rsp, 148h
0x1801443ba  pop     r14
0x1801443bc  pop     rdi
0x1801443bd  pop     rsi
0x1801443be  pop     rbx
0x1801443bf  retn
```
