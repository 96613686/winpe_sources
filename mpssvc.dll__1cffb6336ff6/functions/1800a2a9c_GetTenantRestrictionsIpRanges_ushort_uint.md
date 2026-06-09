# GetTenantRestrictionsIpRanges(ushort * * *,uint *)

- ea: `0x1800a2a9c`
- end: `0x1800a320a`
- name: `?GetTenantRestrictionsIpRanges@@YAJPEAPEAPEAGPEAI@Z`
- size: `1902`
- prototype: `__int64 __fastcall(unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a4ba8`

## callees

- `0x18000cae0`
- `0x1800110d0`
- `0x1800111b0`
- `0x1800554cc`
- `0x18006e81c`
- `0x18006ec88`
- `0x18006f520`
- `0x18006ff98`
- `0x18006ffc8`
- `0x1800a2698`
- `0x1800a2874`
- `0x1800a29f0`
- `0x1800a2a9c`
- `0x1800a32c4`
- `0x1800a32f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2c2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2d97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2e54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2ee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2f16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2f9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2fe1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a30b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a316b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2c2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2d97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2e54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2ee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2f16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2f9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a2fe1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a3053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a30b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a316b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2dce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2dce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2b16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2d47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2b16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2d47`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2b7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2bf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2e04`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2eaa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2b7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2bf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2e04`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2eaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a30f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a3015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a30f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall GetTenantRestrictionsIpRanges(unsigned __int16 ***a1, unsigned int *a2)
{
  unsigned int *v2; // r12
  unsigned __int64 v4; // r14
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int ValueW; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  PVOID v12; // rcx
  _WORD *i; // rbx
  _QWORD *v14; // r8
  __int64 v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // ebx
  PVOID v18; // rcx
  LSTATUS Value; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  PVOID v22; // rcx
  PVOID v23; // rcx
  _WORD *v24; // rbx
  _QWORD *v25; // r8
  __int64 v26; // rax
  unsigned __int16 **v27; // rdi
  unsigned int v28; // esi
  PVOID v29; // rcx
  _QWORD *v30; // r15
  _QWORD *v31; // rbx
  PVOID v32; // rcx
  wchar_t *v33; // rax
  unsigned __int16 *v34; // r12
  unsigned __int64 j; // rbx
  unsigned __int16 *v36; // rcx
  const wchar_t *v37; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-108h]
  unsigned int phkResulta; // [rsp+20h] [rbp-108h]
  unsigned int phkResultb; // [rsp+20h] [rbp-108h]
  unsigned int phkResultc; // [rsp+20h] [rbp-108h]
  unsigned int phkResultd; // [rsp+20h] [rbp-108h]
  unsigned int phkResulte; // [rsp+20h] [rbp-108h]
  rsize_t N; // [rsp+40h] [rbp-E8h]
  rsize_t N1[2]; // [rsp+48h] [rbp-E0h] BYREF
  unsigned int *v46; // [rsp+58h] [rbp-D0h]
  DWORD pcbData; // [rsp+60h] [rbp-C8h] BYREF
  PVOID hMem; // [rsp+68h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-B0h] BYREF
  PVOID pvData; // [rsp+80h] [rbp-A8h] BYREF
  wchar_t *S2[2]; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+98h] [rbp-90h]
  unsigned __int64 v54; // [rsp+A0h] [rbp-88h]
  int v55; // [rsp+B0h] [rbp-78h] BYREF
  _QWORD *v56; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-68h]
  _BYTE v58[24]; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v59; // [rsp+E0h] [rbp-48h]
  __int64 v60; // [rsp+E8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v2 = a2;
  v46 = a2;
  v4 = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
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
  wil::make_unique_hlocal<unsigned short [0]>(&hMem);
  v10 = RegGetValueW(hkey, 0, L"IpRanges", 0x20u, 0, hMem, &pcbData);
  if ( !v10 )
  {
    memset_0(&v55, 0, 0x40u);
    v55 = 0;
    v56 = 0;
    v57 = 0;
    std::list<std::wstring>::_Alloc_sentinel_and_proxy(&v56);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v58);
    v59 = 7;
    v60 = 8;
    v55 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
      v58,
      16,
      v56);
    for ( i = hMem; *i; i += v15 + 1 )
    {
      v14 = (_QWORD *)NormalizeIpRangeValue(S2, i);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        (float *)&v55,
        (__int64)N1,
        v14);
      std::wstring::~wstring((void **)S2);
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
      v17 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xC0,
              (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
              (const char *)v16,
              phkResultc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>((__int64)&v55);
      v18 = hMem;
      hMem = 0;
      if ( v18 )
LABEL_39:
        LocalFree(v18);
LABEL_40:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v17;
    }
    Value = RegQueryValueExW(hKey, L"ipRanges", 0, 0, 0, 0);
    v17 = Value;
    if ( Value )
    {
      if ( Value != 2 )
      {
        if ( Value > 0 )
          v17 = (unsigned __int16)Value | 0x80070000;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>((__int64)&v55);
        v18 = hMem;
        hMem = 0;
        if ( !v18 )
          goto LABEL_40;
        goto LABEL_39;
      }
    }
    else
    {
      pcbData = 0;
      v20 = RegGetValueW(hKey, 0, L"ipRanges", 0x20u, 0, 0, &pcbData);
      if ( v20 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xD4,
                (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
                (const char *)v20,
                phkResultd);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>((__int64)&v55);
        v18 = hMem;
        hMem = 0;
        if ( v18 )
          goto LABEL_39;
        goto LABEL_40;
      }
      wil::make_unique_hlocal<unsigned short [0]>(&pvData);
      v21 = RegGetValueW(hKey, 0, L"ipRanges", 0x20u, 0, pvData, &pcbData);
      if ( v21 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xDF,
                (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
                (const char *)v21,
                phkResulte);
        v22 = pvData;
        pvData = 0;
        if ( v22 )
          LocalFree(v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>((__int64)&v55);
        v18 = hMem;
        hMem = 0;
        if ( !v18 )
          goto LABEL_40;
        goto LABEL_39;
      }
      v23 = pvData;
      v24 = pvData;
      while ( *v24 )
      {
        v25 = (_QWORD *)NormalizeIpRangeValue(S2, v24);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
          (float *)&v55,
          (__int64)N1,
          v25);
        std::wstring::~wstring((void **)S2);
        v26 = -1;
        do
          ++v26;
        while ( v24[v26] );
        v24 += v26 + 1;
        v23 = pvData;
      }
      pvData = 0;
      if ( v23 )
        LocalFree(v23);
    }
    v27 = 0;
    pvData = 0;
    v28 = v57;
    if ( !(_DWORD)v57 || (v27 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (unsigned int)v57), (pvData = v27) != 0) )
    {
      v30 = v56;
      v31 = (_QWORD *)*v56;
      while ( 1 )
      {
        if ( v31 == v30 )
        {
          *a1 = v27;
          *v2 = v28;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>((__int64)&v55);
          v32 = hMem;
          hMem = 0;
          if ( v32 )
            LocalFree(v32);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          return 0;
        }
        std::wstring::wstring(S2, v31 + 2);
        N = v53 + 1;
        N1[0] = 2 * (v53 + 1);
        v33 = (wchar_t *)CoTaskMemAlloc(N1[0]);
        v34 = v33;
        if ( !v33 )
          break;
        v37 = (const wchar_t *)S2;
        if ( v54 > 7 )
          v37 = S2[0];
        o_wmemcpy_s_0(v33, N1[0], v37, N);
        v27[v4++] = v34;
        std::wstring::~wstring((void **)S2);
        v31 = (_QWORD *)*v31;
        v2 = v46;
      }
      for ( j = 0; j < v4; ++j )
      {
        v36 = v27[j];
        if ( v36 )
          CoTaskMemFree(v36);
      }
      std::wstring::~wstring((void **)S2);
      if ( v27 )
        CoTaskMemFree(v27);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>((__int64)&v55);
      v29 = hMem;
      hMem = 0;
      if ( !v29 )
        goto LABEL_45;
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>((__int64)&v55);
      v29 = hMem;
      hMem = 0;
      if ( !v29 )
      {
LABEL_45:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return 2147942414LL;
      }
    }
    LocalFree(v29);
    goto LABEL_45;
  }
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xAC,
          (unsigned int)"onecoreuap\\internal\\ds\\inc\\TenantRestrictions.h",
          (const char *)v10,
          phkResultb);
  v12 = hMem;
  hMem = 0;
  if ( v12 )
    LocalFree(v12);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v11;
}

```

## disassembly

```asm
0x1800a2a9c  mov     [rsp+arg_10], rbx
0x1800a2aa1  mov     [rsp+arg_18], rsi
0x1800a2aa6  push    rdi
0x1800a2aa7  push    r12
0x1800a2aa9  push    r13
0x1800a2aab  push    r14
0x1800a2aad  push    r15
0x1800a2aaf  sub     rsp, 100h
0x1800a2ab6  mov     rax, cs:__security_cookie
0x1800a2abd  xor     rax, rsp
0x1800a2ac0  mov     [rsp+128h+var_38], rax
0x1800a2ac8  mov     r12, rdx
0x1800a2acb  mov     [rsp+128h+var_D0], rdx
0x1800a2ad0  mov     r13, rcx
0x1800a2ad3  xor     r14d, r14d
0x1800a2ad6  test    rcx, rcx
0x1800a2ad9  jz      loc_1800A31D0
0x1800a2adf  test    rdx, rdx
0x1800a2ae2  jz      loc_1800A31D0
0x1800a2ae8  mov     [rcx], r14
0x1800a2aeb  mov     [rdx], r14d
0x1800a2aee  mov     [rsp+128h+hkey], r14
0x1800a2af3  lea     rax, [rsp+128h+hkey]
0x1800a2af8  mov     [rsp+128h+phkResult], rax; unsigned int
0x1800a2afd  mov     edi, 20119h
0x1800a2b02  mov     r9d, edi; samDesired
0x1800a2b05  xor     r8d, r8d; ulOptions
0x1800a2b08  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\TenantRes"...
0x1800a2b0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a2b16  call    cs:__imp_RegOpenKeyExW
0x1800a2b1c  test    eax, eax
0x1800a2b1e  jz      short loc_1800A2B4F
0x1800a2b20  mov     rcx, [rsp+128h]; this
0x1800a2b28  mov     r9d, eax; char *
0x1800a2b2b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a2b32  mov     edx, 96h; void *
0x1800a2b37  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2b3c  mov     ebx, eax
0x1800a2b3e  lea     rcx, [rsp+128h+hkey]
0x1800a2b43  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2b48  mov     eax, ebx
0x1800a2b4a  jmp     loc_1800A31DC
0x1800a2b4f  mov     [rsp+128h+var_C8], r14d
0x1800a2b54  lea     rax, [rsp+128h+var_C8]
0x1800a2b59  mov     [rsp+128h+pcbData], rax; pcbData
0x1800a2b5e  mov     [rsp+128h+pvData], r14; pvData
0x1800a2b63  mov     [rsp+128h+phkResult], r14; unsigned int
0x1800a2b68  mov     esi, 20h ; ' '
0x1800a2b6d  mov     r9d, esi; dwFlags
0x1800a2b70  lea     r8, aIpranges; "IpRanges"
0x1800a2b77  xor     edx, edx; lpSubKey
0x1800a2b79  mov     rcx, [rsp+128h+hkey]; hkey
0x1800a2b7e  call    cs:__imp_RegGetValueW
0x1800a2b84  test    eax, eax
0x1800a2b86  jz      short loc_1800A2BB7
0x1800a2b88  mov     rcx, [rsp+128h]; this
0x1800a2b90  mov     r9d, eax; char *
0x1800a2b93  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a2b9a  mov     edx, 0A1h; void *
0x1800a2b9f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2ba4  mov     ebx, eax
0x1800a2ba6  lea     rcx, [rsp+128h+hkey]
0x1800a2bab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2bb0  mov     eax, ebx
0x1800a2bb2  jmp     loc_1800A31DC
0x1800a2bb7  mov     edx, [rsp+128h+var_C8]
0x1800a2bbb  shr     rdx, 1
0x1800a2bbe  lea     rcx, [rsp+128h+hMem]
0x1800a2bc3  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a2bc8  nop
0x1800a2bc9  mov     rax, [rsp+128h+hMem]
0x1800a2bce  lea     rcx, [rsp+128h+var_C8]
0x1800a2bd3  mov     [rsp+128h+pcbData], rcx; pcbData
0x1800a2bd8  mov     [rsp+128h+pvData], rax; pvData
0x1800a2bdd  mov     [rsp+128h+phkResult], r14; unsigned int
0x1800a2be2  mov     r9d, esi; dwFlags
0x1800a2be5  lea     r8, aIpranges; "IpRanges"
0x1800a2bec  xor     edx, edx; lpSubKey
0x1800a2bee  mov     rcx, [rsp+128h+hkey]; hkey
0x1800a2bf3  call    cs:__imp_RegGetValueW
0x1800a2bf9  test    eax, eax
0x1800a2bfb  jz      short loc_1800A2C42
0x1800a2bfd  mov     rcx, [rsp+128h]; this
0x1800a2c05  mov     r9d, eax; char *
0x1800a2c08  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a2c0f  mov     edx, 0ACh; void *
0x1800a2c14  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2c19  mov     ebx, eax
0x1800a2c1b  mov     rcx, [rsp+128h+hMem]; hMem
0x1800a2c20  mov     [rsp+128h+hMem], r14
0x1800a2c25  test    rcx, rcx
0x1800a2c28  jz      short loc_1800A2C31
0x1800a2c2a  call    cs:__imp_LocalFree
0x1800a2c30  nop
0x1800a2c31  lea     rcx, [rsp+128h+hkey]
0x1800a2c36  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2c3b  mov     eax, ebx
0x1800a2c3d  jmp     loc_1800A31DC
0x1800a2c42  xor     edx, edx; Val
0x1800a2c44  lea     r8d, [rdx+40h]; Size
0x1800a2c48  lea     rcx, [rsp+128h+var_78]; void *
0x1800a2c50  call    memset_0
0x1800a2c55  mov     [rsp+128h+var_78], 0
0x1800a2c60  mov     [rsp+128h+var_70], r14
0x1800a2c68  mov     [rsp+128h+var_68], r14
0x1800a2c70  lea     rcx, [rsp+128h+var_70]
0x1800a2c78  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x1800a2c7d  nop
0x1800a2c7e  lea     rcx, [rsp+128h+var_60]
0x1800a2c86  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x1800a2c8b  nop
0x1800a2c8c  mov     [rsp+128h+var_48], 7
0x1800a2c98  mov     [rsp+128h+var_40], 8
0x1800a2ca4  mov     [rsp+128h+var_78], 3F800000h
0x1800a2caf  mov     r8, [rsp+128h+var_70]
0x1800a2cb7  mov     edx, 10h
0x1800a2cbc  lea     rcx, [rsp+128h+var_60]
0x1800a2cc4  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x1800a2cc9  nop
0x1800a2cca  mov     rbx, [rsp+128h+hMem]
0x1800a2ccf  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800a2cd3  cmp     [rbx], r14w
0x1800a2cd7  jz      short loc_1800A2D24
0x1800a2cd9  mov     rdx, rbx
0x1800a2cdc  lea     rcx, [rsp+128h+S2]
0x1800a2ce4  call    ?NormalizeIpRangeValue@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; NormalizeIpRangeValue(ushort const *)
0x1800a2ce9  nop
0x1800a2cea  mov     r8, rax
0x1800a2ced  lea     rdx, [rsp+128h+N1]
0x1800a2cf2  lea     rcx, [rsp+128h+var_78]
0x1800a2cfa  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1800a2cff  nop
0x1800a2d00  lea     rcx, [rsp+128h+S2]; void *
0x1800a2d08  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a2d0d  mov     rax, r15
0x1800a2d10  inc     rax
0x1800a2d13  cmp     [rbx+rax*2], r14w
0x1800a2d18  jnz     short loc_1800A2D10
0x1800a2d1a  lea     rbx, [rbx+rax*2]
0x1800a2d1e  add     rbx, 2
0x1800a2d22  jmp     short loc_1800A2CD3
0x1800a2d24  mov     [rsp+128h+hKey], r14
0x1800a2d29  lea     rax, [rsp+128h+hKey]
0x1800a2d2e  mov     [rsp+128h+phkResult], rax; unsigned int
0x1800a2d33  mov     r9d, edi; samDesired
0x1800a2d36  xor     r8d, r8d; ulOptions
0x1800a2d39  lea     rdx, aSoftwarePolici_3; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800a2d40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a2d47  call    cs:__imp_RegOpenKeyExW
0x1800a2d4d  test    eax, eax
0x1800a2d4f  jz      short loc_1800A2DAF
0x1800a2d51  mov     rcx, [rsp+128h]; this
0x1800a2d59  mov     r9d, eax; char *
0x1800a2d5c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a2d63  mov     edx, 0C0h; void *
0x1800a2d68  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2d6d  mov     ebx, eax
0x1800a2d6f  lea     rcx, [rsp+128h+hKey]
0x1800a2d74  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2d79  nop
0x1800a2d7a  lea     rcx, [rsp+128h+var_78]
0x1800a2d82  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800a2d87  nop
0x1800a2d88  mov     rcx, [rsp+128h+hMem]; hMem
0x1800a2d8d  mov     [rsp+128h+hMem], r14
0x1800a2d92  test    rcx, rcx
0x1800a2d95  jz      short loc_1800A2D9E
0x1800a2d97  call    cs:__imp_LocalFree
0x1800a2d9d  nop
0x1800a2d9e  lea     rcx, [rsp+128h+hkey]
0x1800a2da3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2da8  mov     eax, ebx
0x1800a2daa  jmp     loc_1800A31DC
0x1800a2daf  mov     [rsp+128h+pvData], r14; lpcbData
0x1800a2db4  mov     [rsp+128h+phkResult], r14; lpData
0x1800a2db9  xor     r9d, r9d; lpType
0x1800a2dbc  xor     r8d, r8d; lpReserved
0x1800a2dbf  lea     rdi, aIpranges_0; "ipRanges"
0x1800a2dc6  mov     rdx, rdi; lpValueName
0x1800a2dc9  mov     rcx, [rsp+128h+hKey]; hKey
0x1800a2dce  call    cs:__imp_RegQueryValueExW
0x1800a2dd4  mov     ebx, eax
0x1800a2dd6  test    eax, eax
0x1800a2dd8  jnz     loc_1800A2FA7
0x1800a2dde  mov     [rsp+128h+var_C8], r14d
0x1800a2de3  lea     rax, [rsp+128h+var_C8]
0x1800a2de8  mov     [rsp+128h+pcbData], rax; pcbData
0x1800a2ded  mov     [rsp+128h+pvData], r14; pvData
0x1800a2df2  mov     [rsp+128h+phkResult], r14; unsigned int
0x1800a2df7  mov     r9d, esi; dwFlags
0x1800a2dfa  mov     r8, rdi; lpValue
0x1800a2dfd  xor     edx, edx; lpSubKey
0x1800a2dff  mov     rcx, [rsp+128h+hKey]; hkey
0x1800a2e04  call    cs:__imp_RegGetValueW
0x1800a2e0a  test    eax, eax
0x1800a2e0c  jz      short loc_1800A2E6C
0x1800a2e0e  mov     rcx, [rsp+128h]; this
0x1800a2e16  mov     r9d, eax; char *
0x1800a2e19  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a2e20  mov     edx, 0D4h; void *
0x1800a2e25  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2e2a  mov     ebx, eax
0x1800a2e2c  lea     rcx, [rsp+128h+hKey]
0x1800a2e31  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2e36  nop
0x1800a2e37  lea     rcx, [rsp+128h+var_78]
0x1800a2e3f  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800a2e44  nop
0x1800a2e45  mov     rcx, [rsp+128h+hMem]; hMem
0x1800a2e4a  mov     [rsp+128h+hMem], r14
0x1800a2e4f  test    rcx, rcx
0x1800a2e52  jz      short loc_1800A2E5B
0x1800a2e54  call    cs:__imp_LocalFree
0x1800a2e5a  nop
0x1800a2e5b  lea     rcx, [rsp+128h+hkey]
0x1800a2e60  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2e65  mov     eax, ebx
0x1800a2e67  jmp     loc_1800A31DC
0x1800a2e6c  mov     edx, [rsp+128h+var_C8]
0x1800a2e70  shr     rdx, 1
0x1800a2e73  lea     rcx, [rsp+128h+var_A8]
0x1800a2e7b  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x1800a2e80  nop
0x1800a2e81  mov     rax, [rsp+128h+var_A8]
0x1800a2e89  lea     rcx, [rsp+128h+var_C8]
0x1800a2e8e  mov     [rsp+128h+pcbData], rcx; pcbData
0x1800a2e93  mov     [rsp+128h+pvData], rax; pvData
0x1800a2e98  mov     [rsp+128h+phkResult], r14; unsigned int
0x1800a2e9d  mov     r9d, esi; dwFlags
0x1800a2ea0  mov     r8, rdi; lpValue
0x1800a2ea3  xor     edx, edx; lpSubKey
0x1800a2ea5  mov     rcx, [rsp+128h+hKey]; hkey
0x1800a2eaa  call    cs:__imp_RegGetValueW
0x1800a2eb0  test    eax, eax
0x1800a2eb2  jz      short loc_1800A2F2E
0x1800a2eb4  mov     rcx, [rsp+128h]; this
0x1800a2ebc  mov     r9d, eax; char *
0x1800a2ebf  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\ds\\inc\\TenantRe"...
0x1800a2ec6  mov     edx, 0DFh; void *
0x1800a2ecb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2ed0  mov     ebx, eax
0x1800a2ed2  mov     rcx, [rsp+128h+var_A8]; hMem
0x1800a2eda  mov     [rsp+128h+var_A8], r14
0x1800a2ee2  test    rcx, rcx
0x1800a2ee5  jz      short loc_1800A2EEE
0x1800a2ee7  call    cs:__imp_LocalFree
0x1800a2eed  nop
0x1800a2eee  lea     rcx, [rsp+128h+hKey]
0x1800a2ef3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2ef8  nop
0x1800a2ef9  lea     rcx, [rsp+128h+var_78]
0x1800a2f01  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x1800a2f06  nop
0x1800a2f07  mov     rcx, [rsp+128h+hMem]; hMem
0x1800a2f0c  mov     [rsp+128h+hMem], r14
0x1800a2f11  test    rcx, rcx
0x1800a2f14  jz      short loc_1800A2F1D
0x1800a2f16  call    cs:__imp_LocalFree
0x1800a2f1c  nop
0x1800a2f1d  lea     rcx, [rsp+128h+hkey]
0x1800a2f22  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2f27  mov     eax, ebx
0x1800a2f29  jmp     loc_1800A31DC
0x1800a2f2e  mov     rcx, [rsp+128h+var_A8]; hMem
0x1800a2f36  mov     rbx, rcx
0x1800a2f39  cmp     [rbx], r14w
0x1800a2f3d  jz      short loc_1800A2F92
0x1800a2f3f  mov     rdx, rbx
0x1800a2f42  lea     rcx, [rsp+128h+S2]
0x1800a2f4a  call    ?NormalizeIpRangeValue@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; NormalizeIpRangeValue(ushort const *)
0x1800a2f4f  nop
0x1800a2f50  mov     r8, rax
0x1800a2f53  lea     rdx, [rsp+128h+N1]
0x1800a2f58  lea     rcx, [rsp+128h+var_78]
0x1800a2f60  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1800a2f65  nop
0x1800a2f66  lea     rcx, [rsp+128h+S2]; void *
0x1800a2f6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a2f73  mov     rax, r15
0x1800a2f76  inc     rax
0x1800a2f79  cmp     [rbx+rax*2], r14w
0x1800a2f7e  jnz     short loc_1800A2F76
0x1800a2f80  lea     rbx, [rbx+rax*2]
0x1800a2f84  add     rbx, 2
0x1800a2f88  mov     rcx, [rsp+128h+var_A8]
0x1800a2f90  jmp     short loc_1800A2F39
0x1800a2f92  mov     [rsp+128h+var_A8], r14
0x1800a2f9a  test    rcx, rcx
0x1800a2f9d  jz      short loc_1800A2FF9
0x1800a2f9f  call    cs:__imp_LocalFree
0x1800a2fa5  jmp     short loc_1800A2FF9
0x1800a2fa7  cmp     eax, 2
0x1800a2faa  jz      short loc_1800A2FF9
0x1800a2fac  test    eax, eax
0x1800a2fae  jle     short loc_1800A2FB9
0x1800a2fb0  movzx   ebx, ax
0x1800a2fb3  or      ebx, 80070000h
0x1800a2fb9  lea     rcx, [rsp+128h+hKey]
0x1800a2fbe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a2fc3  nop
  ... truncated ...
```
