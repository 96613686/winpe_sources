# GetTenantRestrictionsIpRanges(ushort * * *,uint *)

- ea: `0x1800a82a0`
- end: `0x1800a8b1a`
- name: `?GetTenantRestrictionsIpRanges@@YAJPEAPEAPEAGPEAI@Z`
- size: `2170`
- prototype: `__int64 __fastcall(unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800aa54c`

## callees

- `0x18000c390`
- `0x18001275c`
- `0x180012840`
- `0x18005a5d4`
- `0x180071c74`
- `0x1800720f8`
- `0x1800729c0`
- `0x180073458`
- `0x180073488`
- `0x1800a7e9c`
- `0x1800a807c`
- `0x1800a81f0`
- `0x1800a82a0`
- `0x1800a8bd4`
- `0x1800a8c00`
- `0x1800a90fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8456`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a85de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a86b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a879a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8829`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8874`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8919`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a89a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8a6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8456`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a85de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a86b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a879a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8829`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8874`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8919`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a89a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8a6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8621`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8621`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8324`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8585`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8324`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a8585`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8398`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8419`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8660`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a871b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8398`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8419`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a8660`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a871b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a88b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a89e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a88b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a89e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall GetTenantRestrictionsIpRanges(unsigned __int16 ***a1, unsigned int *a2)
{
  unsigned int *v2; // r13
  unsigned __int16 ***v3; // r12
  unsigned __int64 v4; // r14
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int ValueW; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  PVOID v12; // rcx
  _WORD *i; // rbx
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned int v16; // eax
  LSTATUS Value; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  PVOID v20; // rcx
  PVOID v21; // rcx
  _WORD *v22; // rbx
  __int64 v23; // r8
  __int64 v24; // rax
  unsigned __int16 **v25; // rdi
  unsigned int v26; // esi
  LPVOID v27; // rax
  PVOID v28; // rcx
  _QWORD *v29; // r15
  _QWORD *v30; // rbx
  PVOID v31; // rcx
  __int64 v32; // r13
  wchar_t *v33; // rax
  wchar_t *v34; // r12
  unsigned __int64 j; // rbx
  unsigned __int16 *v36; // rcx
  const wchar_t *v37; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-118h]
  unsigned int phkResulta; // [rsp+20h] [rbp-118h]
  unsigned int phkResultb; // [rsp+20h] [rbp-118h]
  unsigned int phkResultc; // [rsp+20h] [rbp-118h]
  unsigned int phkResultd; // [rsp+20h] [rbp-118h]
  unsigned int phkResulte; // [rsp+20h] [rbp-118h]
  _BYTE v46[32]; // [rsp+50h] [rbp-E8h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-C8h] BYREF
  PVOID hMem; // [rsp+78h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+80h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-B0h] BYREF
  PVOID pvData[2]; // [rsp+90h] [rbp-A8h] BYREF
  int v52; // [rsp+A0h] [rbp-98h] BYREF
  _QWORD *v53; // [rsp+A8h] [rbp-90h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-88h]
  _BYTE v55[24]; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-68h]
  __int64 v57; // [rsp+D8h] [rbp-60h]
  wchar_t *S2[2]; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-48h]
  unsigned __int64 v60; // [rsp+F8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v2 = a2;
  v3 = a1;
  v4 = 0;
  if ( a1 && a2 )
  {
    *a1 = 0;
    *a2 = 0;
    hkey = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\TenantRestrictions\\TenantRestrictionsList",
           0,
           0x20119u,
           &hkey);
    if ( v5 )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x96,
             (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
             (const char *)v5,
             phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v6;
    }
    pcbData = 0;
    ValueW = RegGetValueW(hkey, 0, L"IpRanges", 0x20u, 0, 0, &pcbData);
    if ( ValueW )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA1,
             (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
             (const char *)ValueW,
             phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v9;
    }
    wil::make_unique_hlocal<unsigned short [0]>(&hMem, (unsigned __int64)pcbData >> 1);
    v10 = RegGetValueW(hkey, 0, L"IpRanges", 0x20u, 0, hMem, &pcbData);
    if ( v10 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xAC,
              (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
              (const char *)v10,
              phkResultb);
      v12 = hMem;
      hMem = 0;
      if ( v12 )
LABEL_38:
        LocalFree(v12);
LABEL_39:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v11;
    }
    memset_0(&v52, 0, 0x40u);
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::list<std::wstring>::_Alloc_sentinel_and_proxy(&v53);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v55);
    v56 = 7;
    v57 = 8;
    v52 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
      v55,
      16,
      v53);
    for ( i = hMem; *i; i += v15 + 1 )
    {
      v14 = NormalizeIpRangeValue(S2, i);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        &v52,
        pvData,
        v14);
      std::wstring::~wstring(S2);
      v15 = -1;
      do
        ++v15;
      while ( i[v15] );
    }
    hKey = 0;
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\Windows\\TenantRestrictions\\Payload",
            0,
            0x20119u,
            &hKey);
    if ( v16 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xC0,
              (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
              (const char *)v16,
              phkResultc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
      v12 = hMem;
      hMem = 0;
      if ( v12 )
        goto LABEL_38;
      goto LABEL_39;
    }
    Value = RegQueryValueExW(hKey, L"ipRanges", 0, 0, 0, 0);
    v11 = Value;
    if ( Value )
    {
      if ( Value != 2 )
      {
        if ( Value > 0 )
          v11 = (unsigned __int16)Value | 0x80070000;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
        v12 = hMem;
        hMem = 0;
        if ( !v12 )
          goto LABEL_39;
        goto LABEL_38;
      }
    }
    else
    {
      pcbData = 0;
      v18 = RegGetValueW(hKey, 0, L"ipRanges", 0x20u, 0, 0, &pcbData);
      if ( v18 )
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xD4,
                (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
                (const char *)v18,
                phkResultd);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
        v12 = hMem;
        hMem = 0;
        if ( v12 )
          goto LABEL_38;
        goto LABEL_39;
      }
      wil::make_unique_hlocal<unsigned short [0]>(pvData, (unsigned __int64)pcbData >> 1);
      v19 = RegGetValueW(hKey, 0, L"ipRanges", 0x20u, 0, pvData[0], &pcbData);
      if ( v19 )
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xDF,
                (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
                (const char *)v19,
                phkResulte);
        v20 = pvData[0];
        pvData[0] = 0;
        if ( v20 )
          LocalFree(v20);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
        v12 = hMem;
        hMem = 0;
        if ( !v12 )
          goto LABEL_39;
        goto LABEL_38;
      }
      v21 = pvData[0];
      v22 = pvData[0];
      while ( *v22 )
      {
        v23 = NormalizeIpRangeValue(v46, v22);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
          &v52,
          S2,
          v23);
        std::wstring::~wstring(v46);
        v24 = -1;
        do
          ++v24;
        while ( v22[v24] );
        v22 += v24 + 1;
        v21 = pvData[0];
      }
      pvData[0] = 0;
      if ( v21 )
        LocalFree(v21);
    }
    v25 = 0;
    pvData[0] = 0;
    v26 = v54;
    if ( !(_DWORD)v54
      || (v27 = CoTaskMemAlloc(8LL * (unsigned int)v54),
          wistd::unique_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            pvData,
            v27),
          (v25 = (unsigned __int16 **)pvData[0]) != 0) )
    {
      v29 = v53;
      v30 = (_QWORD *)*v53;
      while ( 1 )
      {
        if ( v30 == v29 )
        {
          pvData[0] = 0;
          *v3 = v25;
          *v2 = v26;
          wistd::unique_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            pvData,
            0);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
          v31 = hMem;
          hMem = 0;
          if ( v31 )
            LocalFree(v31);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          return 0;
        }
        std::wstring::wstring(S2, v30 + 2);
        v32 = v59;
        v33 = (wchar_t *)CoTaskMemAlloc(2 * v59 + 2);
        v34 = v33;
        if ( !v33 )
          break;
        v37 = (const wchar_t *)S2;
        if ( v60 > 7 )
          v37 = S2[0];
        o_wmemcpy_s_0(v33, 2 * v32 + 2, v37, v32 + 1);
        v25[v4++] = v34;
        std::wstring::~wstring(S2);
        v30 = (_QWORD *)*v30;
        v3 = a1;
        v2 = a2;
      }
      for ( j = 0; j < v4; ++j )
      {
        v36 = v25[j];
        if ( v36 )
          CoTaskMemFree(v36);
      }
      std::wstring::~wstring(S2);
      wistd::unique_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        pvData,
        0);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
      v28 = hMem;
      hMem = 0;
      if ( !v28 )
        goto LABEL_44;
    }
    else
    {
      wistd::unique_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        pvData,
        0);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v52);
      v28 = hMem;
      hMem = 0;
      if ( !v28 )
      {
LABEL_44:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return 2147942414LL;
      }
    }
    LocalFree(v28);
    goto LABEL_44;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800a82a0  mov     r11, rsp
0x1800a82a3  mov     [r11+18h], rbx
0x1800a82a7  mov     [r11+20h], rsi
0x1800a82ab  push    rdi
0x1800a82ac  push    r12
0x1800a82ae  push    r13
0x1800a82b0  push    r14
0x1800a82b2  push    r15
0x1800a82b4  sub     rsp, 110h
0x1800a82bb  mov     rax, cs:__security_cookie
0x1800a82c2  xor     rax, rsp
0x1800a82c5  mov     [rsp+138h+var_38], rax
0x1800a82cd  mov     r13, rdx
0x1800a82d0  mov     [rsp+138h+var_F0], rdx
0x1800a82d5  mov     r12, rcx
0x1800a82d8  mov     [rsp+138h+var_F8], rcx
0x1800a82dd  xor     r14d, r14d
0x1800a82e0  test    rcx, rcx
0x1800a82e3  jz      loc_1800A8AE0
0x1800a82e9  test    rdx, rdx
0x1800a82ec  jz      loc_1800A8AE0
0x1800a82f2  mov     [rcx], r14
0x1800a82f5  mov     [rdx], r14d
0x1800a82f8  mov     [r11-0B8h], r14
0x1800a82ff  lea     rax, [r11-0B8h]
0x1800a8306  mov     [rsp+138h+phkResult], rax; unsigned int
0x1800a830b  mov     edi, 20119h
0x1800a8310  mov     r9d, edi; samDesired
0x1800a8313  xor     r8d, r8d; ulOptions
0x1800a8316  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\TenantRes"...
0x1800a831d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a8324  call    cs:__imp_RegOpenKeyExW
0x1800a832b  nop     dword ptr [rax+rax+00h]
0x1800a8330  test    eax, eax
0x1800a8332  jz      short loc_1800A8366
0x1800a8334  mov     rcx, [rsp+138h]; this
0x1800a833c  mov     r9d, eax; char *
0x1800a833f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a8346  mov     edx, 96h; void *
0x1800a834b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a8350  mov     ebx, eax
0x1800a8352  lea     rcx, [rsp+138h+hkey]
0x1800a835a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a835f  mov     eax, ebx
0x1800a8361  jmp     loc_1800A8AEC
0x1800a8366  mov     [rsp+138h+var_C8], r14d
0x1800a836b  lea     rax, [rsp+138h+var_C8]
0x1800a8370  mov     [rsp+138h+pcbData], rax; pcbData
0x1800a8375  mov     [rsp+138h+pvData], r14; pvData
0x1800a837a  mov     [rsp+138h+phkResult], r14; unsigned int
0x1800a837f  mov     esi, 20h ; ' '
0x1800a8384  mov     r9d, esi; dwFlags
0x1800a8387  lea     r8, aIpranges; "IpRanges"
0x1800a838e  xor     edx, edx; lpSubKey
0x1800a8390  mov     rcx, [rsp+138h+hkey]; hkey
0x1800a8398  call    cs:__imp_RegGetValueW
0x1800a839f  nop     dword ptr [rax+rax+00h]
0x1800a83a4  test    eax, eax
0x1800a83a6  jz      short loc_1800A83DA
0x1800a83a8  mov     rcx, [rsp+138h]; this
0x1800a83b0  mov     r9d, eax; char *
0x1800a83b3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a83ba  mov     edx, 0A1h; void *
0x1800a83bf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a83c4  mov     ebx, eax
0x1800a83c6  lea     rcx, [rsp+138h+hkey]
0x1800a83ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a83d3  mov     eax, ebx
0x1800a83d5  jmp     loc_1800A8AEC
0x1800a83da  mov     edx, [rsp+138h+var_C8]
0x1800a83de  shr     rdx, 1
0x1800a83e1  lea     rcx, [rsp+138h+hMem]
0x1800a83e6  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a83eb  nop
0x1800a83ec  mov     rax, [rsp+138h+hMem]
0x1800a83f1  lea     rcx, [rsp+138h+var_C8]
0x1800a83f6  mov     [rsp+138h+pcbData], rcx; pcbData
0x1800a83fb  mov     [rsp+138h+pvData], rax; pvData
0x1800a8400  mov     [rsp+138h+phkResult], r14; unsigned int
0x1800a8405  mov     r9d, esi; dwFlags
0x1800a8408  lea     r8, aIpranges; "IpRanges"
0x1800a840f  xor     edx, edx; lpSubKey
0x1800a8411  mov     rcx, [rsp+138h+hkey]; hkey
0x1800a8419  call    cs:__imp_RegGetValueW
0x1800a8420  nop     dword ptr [rax+rax+00h]
0x1800a8425  test    eax, eax
0x1800a8427  jz      short loc_1800A8477
0x1800a8429  mov     rcx, [rsp+138h]; this
0x1800a8431  mov     r9d, eax; char *
0x1800a8434  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a843b  mov     edx, 0ACh; void *
0x1800a8440  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a8445  mov     ebx, eax
0x1800a8447  mov     rcx, [rsp+138h+hMem]; hMem
0x1800a844c  mov     [rsp+138h+hMem], r14
0x1800a8451  test    rcx, rcx
0x1800a8454  jz      short loc_1800A8463
0x1800a8456  call    cs:__imp_LocalFree
0x1800a845d  nop     dword ptr [rax+rax+00h]
0x1800a8462  nop
0x1800a8463  lea     rcx, [rsp+138h+hkey]
0x1800a846b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a8470  mov     eax, ebx
0x1800a8472  jmp     loc_1800A8AEC
0x1800a8477  xor     edx, edx; Val
0x1800a8479  lea     r8d, [rdx+40h]; Size
0x1800a847d  lea     rcx, [rsp+138h+var_98]; void *
0x1800a8485  call    memset_0
0x1800a848a  mov     [rsp+138h+var_98], 0
0x1800a8495  mov     [rsp+138h+var_90], r14
0x1800a849d  mov     [rsp+138h+var_88], r14
0x1800a84a5  lea     rcx, [rsp+138h+var_90]
0x1800a84ad  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x1800a84b2  nop
0x1800a84b3  lea     rcx, [rsp+138h+var_80]
0x1800a84bb  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x1800a84c0  nop
0x1800a84c1  mov     [rsp+138h+var_68], 7
0x1800a84cd  mov     [rsp+138h+var_60], 8
0x1800a84d9  mov     [rsp+138h+var_98], 3F800000h
0x1800a84e4  mov     r8, [rsp+138h+var_90]
0x1800a84ec  mov     edx, 10h
0x1800a84f1  lea     rcx, [rsp+138h+var_80]
0x1800a84f9  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x1800a84fe  nop
0x1800a84ff  mov     rbx, [rsp+138h+hMem]
0x1800a8504  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800a8508  cmp     [rbx], r14w
0x1800a850c  jz      short loc_1800A855C
0x1800a850e  mov     rdx, rbx
0x1800a8511  lea     rcx, [rsp+138h+S2]
0x1800a8519  call    ?NormalizeIpRangeValue@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; NormalizeIpRangeValue(ushort const *)
0x1800a851e  nop
0x1800a851f  mov     r8, rax
0x1800a8522  lea     rdx, [rsp+138h+var_A8]
0x1800a852a  lea     rcx, [rsp+138h+var_98]
0x1800a8532  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1800a8537  nop
0x1800a8538  lea     rcx, [rsp+138h+S2]; void *
0x1800a8540  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a8545  mov     rax, r15
0x1800a8548  inc     rax
0x1800a854b  cmp     [rbx+rax*2], r14w
0x1800a8550  jnz     short loc_1800A8548
0x1800a8552  lea     rbx, [rbx+rax*2]
0x1800a8556  add     rbx, 2
0x1800a855a  jmp     short loc_1800A8508
0x1800a855c  mov     [rsp+138h+hKey], r14
0x1800a8564  lea     rax, [rsp+138h+hKey]
0x1800a856c  mov     [rsp+138h+phkResult], rax; unsigned int
0x1800a8571  mov     r9d, edi; samDesired
0x1800a8574  xor     r8d, r8d; ulOptions
0x1800a8577  lea     rdx, aSoftwarePolici_3; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800a857e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a8585  call    cs:__imp_RegOpenKeyExW
0x1800a858c  nop     dword ptr [rax+rax+00h]
0x1800a8591  test    eax, eax
0x1800a8593  jz      short loc_1800A85FF
0x1800a8595  mov     rcx, [rsp+138h]; this
0x1800a859d  mov     r9d, eax; char *
0x1800a85a0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a85a7  mov     edx, 0C0h; void *
0x1800a85ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a85b1  mov     ebx, eax
0x1800a85b3  lea     rcx, [rsp+138h+hKey]
0x1800a85bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a85c0  nop
0x1800a85c1  lea     rcx, [rsp+138h+var_98]
0x1800a85c9  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800a85ce  nop
0x1800a85cf  mov     rcx, [rsp+138h+hMem]; hMem
0x1800a85d4  mov     [rsp+138h+hMem], r14
0x1800a85d9  test    rcx, rcx
0x1800a85dc  jz      short loc_1800A85EB
0x1800a85de  call    cs:__imp_LocalFree
0x1800a85e5  nop     dword ptr [rax+rax+00h]
0x1800a85ea  nop
0x1800a85eb  lea     rcx, [rsp+138h+hkey]
0x1800a85f3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a85f8  mov     eax, ebx
0x1800a85fa  jmp     loc_1800A8AEC
0x1800a85ff  mov     [rsp+138h+pvData], r14; lpcbData
0x1800a8604  mov     [rsp+138h+phkResult], r14; lpData
0x1800a8609  xor     r9d, r9d; lpType
0x1800a860c  xor     r8d, r8d; lpReserved
0x1800a860f  lea     rdi, aIpranges_0; "ipRanges"
0x1800a8616  mov     rdx, rdi; lpValueName
0x1800a8619  mov     rcx, [rsp+138h+hKey]; hKey
0x1800a8621  call    cs:__imp_RegQueryValueExW
0x1800a8628  nop     dword ptr [rax+rax+00h]
0x1800a862d  mov     ebx, eax
0x1800a862f  test    eax, eax
0x1800a8631  jnz     loc_1800A8837
0x1800a8637  mov     [rsp+138h+var_C8], r14d
0x1800a863c  lea     rax, [rsp+138h+var_C8]
0x1800a8641  mov     [rsp+138h+pcbData], rax; pcbData
0x1800a8646  mov     [rsp+138h+pvData], r14; pvData
0x1800a864b  mov     [rsp+138h+phkResult], r14; unsigned int
0x1800a8650  mov     r9d, esi; dwFlags
0x1800a8653  mov     r8, rdi; lpValue
0x1800a8656  xor     edx, edx; lpSubKey
0x1800a8658  mov     rcx, [rsp+138h+hKey]; hkey
0x1800a8660  call    cs:__imp_RegGetValueW
0x1800a8667  nop     dword ptr [rax+rax+00h]
0x1800a866c  test    eax, eax
0x1800a866e  jz      short loc_1800A86DA
0x1800a8670  mov     rcx, [rsp+138h]; this
0x1800a8678  mov     r9d, eax; char *
0x1800a867b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a8682  mov     edx, 0D4h; void *
0x1800a8687  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a868c  mov     ebx, eax
0x1800a868e  lea     rcx, [rsp+138h+hKey]
0x1800a8696  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a869b  nop
0x1800a869c  lea     rcx, [rsp+138h+var_98]
0x1800a86a4  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800a86a9  nop
0x1800a86aa  mov     rcx, [rsp+138h+hMem]; hMem
0x1800a86af  mov     [rsp+138h+hMem], r14
0x1800a86b4  test    rcx, rcx
0x1800a86b7  jz      short loc_1800A86C6
0x1800a86b9  call    cs:__imp_LocalFree
0x1800a86c0  nop     dword ptr [rax+rax+00h]
0x1800a86c5  nop
0x1800a86c6  lea     rcx, [rsp+138h+hkey]
0x1800a86ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a86d3  mov     eax, ebx
0x1800a86d5  jmp     loc_1800A8AEC
0x1800a86da  mov     edx, [rsp+138h+var_C8]
0x1800a86de  shr     rdx, 1
0x1800a86e1  lea     rcx, [rsp+138h+var_A8]
0x1800a86e9  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a86ee  nop
0x1800a86ef  mov     rax, [rsp+138h+var_A8]
0x1800a86f7  lea     rcx, [rsp+138h+var_C8]
0x1800a86fc  mov     [rsp+138h+pcbData], rcx; pcbData
0x1800a8701  mov     [rsp+138h+pvData], rax; pvData
0x1800a8706  mov     [rsp+138h+phkResult], r14; unsigned int
0x1800a870b  mov     r9d, esi; dwFlags
0x1800a870e  mov     r8, rdi; lpValue
0x1800a8711  xor     edx, edx; lpSubKey
0x1800a8713  mov     rcx, [rsp+138h+hKey]; hkey
0x1800a871b  call    cs:__imp_RegGetValueW
0x1800a8722  nop     dword ptr [rax+rax+00h]
0x1800a8727  test    eax, eax
0x1800a8729  jz      loc_1800A87BB
0x1800a872f  mov     rcx, [rsp+138h]; this
0x1800a8737  mov     r9d, eax; char *
0x1800a873a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a8741  mov     edx, 0DFh; void *
0x1800a8746  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a874b  mov     ebx, eax
0x1800a874d  mov     rcx, [rsp+138h+var_A8]; hMem
0x1800a8755  mov     [rsp+138h+var_A8], r14
0x1800a875d  test    rcx, rcx
0x1800a8760  jz      short loc_1800A876F
0x1800a8762  call    cs:__imp_LocalFree
0x1800a8769  nop     dword ptr [rax+rax+00h]
0x1800a876e  nop
0x1800a876f  lea     rcx, [rsp+138h+hKey]
0x1800a8777  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a877c  nop
0x1800a877d  lea     rcx, [rsp+138h+var_98]
0x1800a8785  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800a878a  nop
0x1800a878b  mov     rcx, [rsp+138h+hMem]; hMem
0x1800a8790  mov     [rsp+138h+hMem], r14
0x1800a8795  test    rcx, rcx
0x1800a8798  jz      short loc_1800A87A7
0x1800a879a  call    cs:__imp_LocalFree
0x1800a87a1  nop     dword ptr [rax+rax+00h]
0x1800a87a6  nop
0x1800a87a7  lea     rcx, [rsp+138h+hkey]
0x1800a87af  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a87b4  mov     eax, ebx
0x1800a87b6  jmp     loc_1800A8AEC
0x1800a87bb  mov     rcx, [rsp+138h+var_A8]; hMem
0x1800a87c3  mov     rbx, rcx
0x1800a87c6  cmp     [rbx], r14w
0x1800a87ca  jz      short loc_1800A881C
0x1800a87cc  mov     rdx, rbx
0x1800a87cf  lea     rcx, [rsp+138h+var_E8]
0x1800a87d4  call    ?NormalizeIpRangeValue@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; NormalizeIpRangeValue(ushort const *)
0x1800a87d9  nop
0x1800a87da  mov     r8, rax
0x1800a87dd  lea     rdx, [rsp+138h+S2]
0x1800a87e5  lea     rcx, [rsp+138h+var_98]
0x1800a87ed  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1800a87f2  nop
0x1800a87f3  lea     rcx, [rsp+138h+var_E8]; void *
0x1800a87f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a87fd  mov     rax, r15
0x1800a8800  inc     rax
0x1800a8803  cmp     [rbx+rax*2], r14w
0x1800a8808  jnz     short loc_1800A8800
0x1800a880a  lea     rbx, [rbx+rax*2]
0x1800a880e  add     rbx, 2
0x1800a8812  mov     rcx, [rsp+138h+var_A8]
0x1800a881a  jmp     short loc_1800A87C6
  ... truncated ...
```
