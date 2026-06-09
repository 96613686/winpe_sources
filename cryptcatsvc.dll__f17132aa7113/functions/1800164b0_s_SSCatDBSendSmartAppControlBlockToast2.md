# s_SSCatDBSendSmartAppControlBlockToast2

- ea: `0x1800164b0`
- end: `0x180016ba4`
- name: `s_SSCatDBSendSmartAppControlBlockToast2`
- size: `1780`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, _WORD *, const WCHAR *, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000ad10`
- `0x18000b5ec`
- `0x18000be40`
- `0x180013cc4`
- `0x180013e40`
- `0x180013f48`
- `0x180014050`
- `0x180014098`
- `0x1800140e0`
- `0x180014190`
- `0x1800144b4`
- `0x1800144f0`
- `0x180014540`
- `0x1800145d8`
- `0x180014690`
- `0x1800151b4`
- `0x180015388`
- `0x180016248`
- `0x1800162a0`
- `0x180016380`
- `0x18001642c`
- `0x1800164b0`
- `0x1800215e0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016695`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016695`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016651`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016651`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016547`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016547`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166a3`
- `RPCRT4!RpcRevertToSelf` at `0x180016a29`
- `RPCRT4!RpcRevertToSelf` at `0x180016a29`
- `RPCRT4!RpcImpersonateClient` at `0x1800166e0`
- `RPCRT4!RpcImpersonateClient` at `0x1800166e0`
- `SHLWAPI!PathFindFileNameW` at `0x180016755`
- `SHLWAPI!PathFindFileNameW` at `0x180016755`

## string_xrefs

- `0x18001664a`: `wldp.dll`

## pseudocode

```c
__int64 __fastcall s_SSCatDBSendSmartAppControlBlockToast2(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        _WORD *a3,
        const WCHAR *a4,
        unsigned int a5,
        _DWORD *a6)
{
  __int64 v9; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rbx
  HMODULE Library; // rax
  wil *v16; // rcx
  unsigned int v17; // r13d
  FARPROC ProcAddress; // r15
  LPWSTR FileNameW; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 LocalisedAppDescription; // rax
  unsigned __int64 v23; // rdx
  void **v24; // rdi
  __int64 v25; // rbx
  _QWORD *v26; // rdx
  void **v27; // rcx
  int v28; // ebx
  __int64 v29; // rdi
  __int64 v30; // rdi
  __int64 v31; // rax
  HMODULE *v33; // rax
  unsigned __int64 v34; // r12
  unsigned int v35; // r15d
  HMODULE v36; // rbx
  __int128 v37; // rdi
  LPCWSTR *v38; // rax
  LPCWSTR v39; // rax
  unsigned __int64 v40; // r9
  unsigned __int64 v41; // r9
  wil *v42; // rcx
  wil *v43; // rcx
  DWORD LastError; // [rsp+20h] [rbp-148h]
  char v45; // [rsp+24h] [rbp-144h]
  RTL_SRWLOCK *v46; // [rsp+28h] [rbp-140h] BYREF
  HMODULE v47; // [rsp+30h] [rbp-138h] BYREF
  LPCWSTR pszPath; // [rsp+38h] [rbp-130h] BYREF
  unsigned __int64 SystemTimeAsUInt64; // [rsp+40h] [rbp-128h]
  _QWORD v50[2]; // [rsp+48h] [rbp-120h] BYREF
  _BYTE v51[16]; // [rsp+58h] [rbp-110h] BYREF
  _BYTE v52[32]; // [rsp+68h] [rbp-100h] BYREF
  __int64 v53; // [rsp+88h] [rbp-E0h]
  __int128 v54; // [rsp+90h] [rbp-D8h]
  _BYTE v55[32]; // [rsp+A8h] [rbp-C0h] BYREF
  void *v56[2]; // [rsp+C8h] [rbp-A0h] BYREF
  unsigned __int64 v57; // [rsp+D8h] [rbp-90h]
  unsigned __int64 v58; // [rsp+E0h] [rbp-88h]
  _QWORD v59[4]; // [rsp+E8h] [rbp-80h] BYREF
  _QWORD v60[3]; // [rsp+108h] [rbp-60h] BYREF
  unsigned __int64 v61; // [rsp+120h] [rbp-48h]

  v53 = -2;
  pszPath = a4;
  LastError = 0;
  SystemTimeAsUInt64 = 0;
  v54 = 0;
  v45 = 0;
  if ( !BindingHandle || !a2 || !a4 )
    return 160;
  SystemTimeAsUInt64 = GetSystemTimeAsUInt64();
  AcquireSRWLockExclusive(&srwToastTimeLock);
  try
  {
    v46 = &srwToastTimeLock;
    v9 = g_lastToastTime;
    if ( !g_lastToastTime )
    {
      v10 = (__int64 *)std::make_unique<std::map<std::wstring,std::map<std::wstring,unsigned __int64>>,,0>(&v47);
      v11 = *v10;
      *v10 = 0;
      v12 = g_lastToastTime;
      g_lastToastTime = v11;
      if ( v12 )
        std::default_delete<std::map<std::wstring,std::map<std::wstring,unsigned __int64>>>::operator()();
      __1__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___2__std___2__std__QEAA_XZ(&v47);
      v9 = g_lastToastTime;
    }
    std::wstring::wstring(v59, a2);
    v13 = *(_QWORD *)std::map<std::wstring,std::map<std::wstring,unsigned __int64>>::_Try_emplace<std::wstring,>(
                       v9,
                       v51,
                       v59);
    std::wstring::wstring(v60, pszPath);
    v14 = *(_QWORD *)(*(_QWORD *)std::map<std::wstring,unsigned __int64>::_Try_emplace<std::wstring,>(
                                   v13 + 64,
                                   v50,
                                   v60)
                    + 64LL);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v59);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v46,
      0);
    if ( v14 && SystemTimeAsUInt64 - v14 <= 0x861C46800LL )
    {
      *a6 = 1;
LABEL_45:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
      v17 = LastError;
      goto LABEL_80;
    }
    Library = LoadLibraryExW(L"wldp.dll", 0, 0x800u);
    v47 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "WldpSendSmartAppControlBlockToast2");
      if ( ProcAddress )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetImpl'::`2'::impl) )
        {
          if ( RpcImpersonateClient(BindingHandle) )
          {
            LastError = 50;
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v47);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
            v17 = 50;
            goto LABEL_80;
          }
          v45 = 1;
        }
        std::wstring::wstring(v59, a2);
        *(_OWORD *)v56 = 0;
        v57 = 0;
        v58 = 7;
        LOWORD(v56[0]) = 0;
        FileNameW = PathFindFileNameW(pszPath);
        std::wstring::wstring(v60, FileNameW);
        v20 = ConvertDevicePathToDosPath(v52, v59);
        std::wstring::operator=(v59, v20);
        std::wstring::_Tidy_deallocate(v52);
        if ( std::wstring::find(v59) )
        {
          LocalisedAppDescription = GetLocalisedAppDescription(v52, v59);
          std::wstring::operator=(v56, LocalisedAppDescription);
          std::wstring::_Tidy_deallocate(v52);
        }
        if ( v57 )
          goto LABEL_35;
        if ( !a3 )
          goto LABEL_31;
        v23 = -1;
        do
          ++v23;
        while ( a3[v23] );
        if ( v23 > v58 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v56,
            v23,
            v21,
            a3);
        }
        else
        {
          v24 = v56;
          if ( v58 > 7 )
            v24 = (void **)v56[0];
          v57 = v23;
          v25 = 2 * v23;
          memmove_0(v24, a3, 2 * v23);
          *(_WORD *)((char *)v24 + v25) = 0;
        }
        if ( v57 )
        {
LABEL_35:
          v26 = v60;
          if ( v61 > 7 )
            v26 = (_QWORD *)v60[0];
          v27 = v56;
          if ( v58 > 7 )
            v27 = (void **)v56[0];
        }
        else
        {
LABEL_31:
          v26 = v60;
          if ( v61 > 7 )
            v26 = (_QWORD *)v60[0];
          v27 = (void **)v59;
          if ( v59[3] > 7u )
            v27 = (void **)v59[0];
        }
        v28 = ((__int64 (__fastcall *)(void **, _QWORD *, _QWORD))ProcAddress)(v27, v26, a5);
        if ( v28 >= 0 )
        {
          AcquireSRWLockExclusive(&srwToastTimeLock);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
            &v46,
            &srwToastTimeLock);
          v50[0] = 0;
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v50);
          v29 = g_lastToastTime;
          std::wstring::wstring(v52, a2);
          v30 = *(_QWORD *)std::map<std::wstring,std::map<std::wstring,unsigned __int64>>::_Try_emplace<std::wstring,>(
                             v29,
                             v51,
                             v52);
          std::wstring::wstring(v55, pszPath);
          v31 = std::map<std::wstring,unsigned __int64>::_Try_emplace<std::wstring,>(v30 + 64, v50, v55);
          *(_QWORD *)(*(_QWORD *)v31 + 64LL) = SystemTimeAsUInt64;
          std::wstring::_Tidy_deallocate(v55);
          std::wstring::_Tidy_deallocate(v52);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
            &v46,
            0);
        }
        std::wstring::_Tidy_deallocate(v60);
        std::wstring::_Tidy_deallocate(v56);
        std::wstring::_Tidy_deallocate(v59);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v47);
        if ( v28 < 0 )
        {
          if ( (v28 & 0x1FFF0000) == 0x70000 )
            v28 = (unsigned __int16)v28;
          LastError = v28;
        }
        goto LABEL_45;
      }
    }
    LastError = GetLastError();
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v47);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
    v17 = LastError;
  }
  catch ( ... )
  {
    if ( (int)wil::ResultFromCaughtException(v16) < 0 )
    {
      if ( (wil::ResultFromCaughtException(v42) & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)wil::ResultFromCaughtException(v43);
      else
        LastError = wil::ResultFromCaughtException(v43);
    }
    else
    {
      LastError = 0;
    }
    v17 = LastError;
  }
LABEL_80:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetImpl'::`2'::impl)
    && v45 )
  {
    RpcRevertToSelf();
  }
  AcquireSRWLockExclusive(&srwToastTimeLock);
  v46 = &srwToastTimeLock;
  v33 = (HMODULE *)g_lastToastTime;
  if ( g_lastToastTime )
  {
    v34 = 0x7FFFFFFFFFFFFFFFLL;
    v35 = 0;
    v36 = **(HMODULE **)g_lastToastTime;
    v37 = v54;
LABEL_52:
    v47 = v36;
    while ( v36 != *v33 )
    {
      v38 = (LPCWSTR *)*((_QWORD *)v36 + 8);
LABEL_55:
      v39 = *v38;
      pszPath = v39;
      while ( v39 != *((LPCWSTR *)v36 + 8) )
      {
        v40 = *((_QWORD *)v39 + 8);
        if ( SystemTimeAsUInt64 - v40 > 0x861C46800LL )
        {
          v38 = (LPCWSTR *)std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned __int64>>>>,0>(
                             v36 + 16,
                             v50,
                             v39);
          goto LABEL_55;
        }
        ++v35;
        if ( v40 < v34 )
        {
          *(_QWORD *)&v37 = v36;
          *((_QWORD *)&v37 + 1) = v39;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::map<std::wstring,unsigned __int64>>>>,std::_Iterator_base0>::operator++(&pszPath);
        if ( v41 >= v34 )
          v41 = v34;
        v34 = v41;
        v39 = pszPath;
      }
      if ( !*((_QWORD *)v36 + 9) )
      {
        v36 = *(HMODULE *)___erase_V___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___std___std___std___0A_____Tree_V___Tmap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___2__0A__std___std__QEAA_AV___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___std___std___1_V21__Z(
                            g_lastToastTime,
                            v51,
                            v36);
        v33 = (HMODULE *)g_lastToastTime;
        goto LABEL_52;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::map<std::wstring,unsigned __int64>>>>,std::_Iterator_base0>::operator++(&v47);
      v33 = (HMODULE *)g_lastToastTime;
      v36 = v47;
    }
    if ( v35 > 0x40 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned __int64>>>>,0>(
        v37 + 64,
        v51,
        *((_QWORD *)&v37 + 1));
      if ( !*(_QWORD *)(v37 + 72) )
        ___erase_V___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___std___std___std___0A_____Tree_V___Tmap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___2__0A__std___std__QEAA_AV___Tree_iterator_V___Tree_val_U___Tree_simple_types_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___KU__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___K_std___2__2__std___std___std___1_V21__Z(
          g_lastToastTime,
          v51,
          v37);
    }
    v17 = LastError;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
    &v46,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
  return v17;
}

```

## disassembly

```asm
0x1800164b0  push    rbx
0x1800164b2  push    rsi
0x1800164b3  push    rdi
0x1800164b4  push    r12
0x1800164b6  push    r13
0x1800164b8  push    r14
0x1800164ba  push    r15
0x1800164bc  sub     rsp, 130h
0x1800164c3  mov     [rsp+168h+var_E0], 0FFFFFFFFFFFFFFFEh
0x1800164cf  mov     rax, cs:__security_cookie
0x1800164d6  xor     rax, rsp
0x1800164d9  mov     [rsp+168h+var_40], rax
0x1800164e1  mov     rax, r9
0x1800164e4  mov     [rsp+168h+pszPath], rax
0x1800164e9  mov     r12, r8
0x1800164ec  mov     r13, rdx
0x1800164ef  mov     rdi, rcx
0x1800164f2  mov     r15, [rsp+168h+arg_28]
0x1800164fa  xor     r14d, r14d
0x1800164fd  mov     [rsp+168h+var_148], r14d
0x180016502  mov     [rsp+168h+var_128], r14
0x180016507  xorps   xmm0, xmm0
0x18001650a  movdqu  [rsp+168h+var_D8], xmm0
0x180016513  mov     [rsp+168h+var_144], r14b
0x180016518  test    rcx, rcx
0x18001651b  jz      loc_1800169F4
0x180016521  test    rdx, rdx
0x180016524  jz      loc_1800169F4
0x18001652a  test    rax, rax
0x18001652d  jz      loc_1800169F4
0x180016533  call    ?GetSystemTimeAsUInt64@@YA_KXZ; GetSystemTimeAsUInt64(void)
0x180016538  mov     [rsp+168h+var_128], rax
0x18001653d  lea     rsi, ?srwToastTimeLock@@3Vsrwlock@wil@@A; wil::srwlock srwToastTimeLock
0x180016544  mov     rcx, rsi; SRWLock
0x180016547  call    cs:__imp_AcquireSRWLockExclusive
0x18001654d  mov     [rsp+168h+var_140], rsi
0x180016552  mov     rbx, cs:?g_lastToastTime@@3V?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@2@@std@@A
0x180016559  test    rbx, rbx
0x18001655c  jnz     short loc_18001659A
0x18001655e  lea     rcx, [rsp+168h+var_138]
0x180016563  call    ??$make_unique@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@$$V$0A@@std@@YA?AV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@2@@0@XZ
0x180016568  mov     rcx, rax
0x18001656b  mov     rax, [rax]
0x18001656e  mov     [rcx], r14
0x180016571  mov     rdx, cs:?g_lastToastTime@@3V?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@2@@std@@A
0x180016578  mov     cs:?g_lastToastTime@@3V?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@2@@std@@A, rax
0x18001657f  test    rdx, rdx
0x180016582  jz      short loc_180016589
0x180016584  call    ??R?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@std@@QEBAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@1@@Z
0x180016589  lea     rcx, [rsp+168h+var_138]
0x18001658e  call    ??1?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@2@@std@@QEAA@XZ
0x180016593  mov     rbx, cs:?g_lastToastTime@@3V?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@2@@std@@A
0x18001659a  mov     rdx, r13
0x18001659d  lea     rcx, [rsp+168h+var_80]
0x1800165a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800165aa  nop
0x1800165ab  lea     r8, [rsp+168h+var_80]
0x1800165b3  lea     rdx, [rsp+168h+var_110]
0x1800165b8  mov     rcx, rbx
0x1800165bb  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,unsigned __int64>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800165c0  mov     rbx, [rax]
0x1800165c3  mov     rdx, [rsp+168h+pszPath]
0x1800165c8  lea     rcx, [rsp+168h+var_60]
0x1800165d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800165d5  nop
0x1800165d6  lea     r8, [rsp+168h+var_60]
0x1800165de  lea     rdx, [rsp+168h+var_120]
0x1800165e3  lea     rcx, [rbx+40h]
0x1800165e7  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,unsigned __int64>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800165ec  mov     rax, [rax]
0x1800165ef  mov     rbx, [rax+40h]
0x1800165f3  lea     rcx, [rsp+168h+var_60]
0x1800165fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016600  nop
0x180016601  lea     rcx, [rsp+168h+var_80]
0x180016609  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001660e  xor     edx, edx
0x180016610  lea     rcx, [rsp+168h+var_140]
0x180016615  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001661a  test    rbx, rbx
0x18001661d  jz      short loc_180016642
0x18001661f  mov     rax, [rsp+168h+var_128]
0x180016624  sub     rax, rbx
0x180016627  mov     rbx, 861C46800h
0x180016631  cmp     rax, rbx
0x180016634  ja      short loc_180016642
0x180016636  mov     dword ptr [r15], 1
0x18001663d  jmp     loc_1800169E2
0x180016642  xor     edx, edx; hFile
0x180016644  mov     r8d, 800h; dwFlags
0x18001664a  lea     rcx, aWldpDll; "wldp.dll"
0x180016651  call    cs:__imp_LoadLibraryExW
0x180016657  mov     [rsp+168h+var_138], rax
0x18001665c  test    rax, rax
0x18001665f  jnz     short loc_18001668B
0x180016661  call    cs:__imp_GetLastError
0x180016667  mov     [rsp+168h+var_148], eax
0x18001666b  lea     rcx, [rsp+168h+var_138]
0x180016670  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180016675  nop
0x180016676  lea     rcx, [rsp+168h+var_140]
0x18001667b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016680  nop
0x180016681  mov     r13d, [rsp+168h+var_148]
0x180016686  jmp     loc_180016A12
0x18001668b  lea     rdx, aWldpsendsmarta_0; "WldpSendSmartAppControlBlockToast2"
0x180016692  mov     rcx, rax; hModule
0x180016695  call    cs:__imp_GetProcAddress
0x18001669b  mov     r15, rax
0x18001669e  test    rax, rax
0x1800166a1  jnz     short loc_1800166CD
0x1800166a3  call    cs:__imp_GetLastError
0x1800166a9  mov     [rsp+168h+var_148], eax
0x1800166ad  lea     rcx, [rsp+168h+var_138]
0x1800166b2  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800166b7  nop
0x1800166b8  lea     rcx, [rsp+168h+var_140]
0x1800166bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800166c2  nop
0x1800166c3  mov     r13d, [rsp+168h+var_148]
0x1800166c8  jmp     loc_180016A12
0x1800166cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation> `wil::Feature<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetImpl(void)'::`2'::impl
0x1800166d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::__private_IsEnabled(void)
0x1800166d9  test    al, al
0x1800166db  jz      short loc_180016717
0x1800166dd  mov     rcx, rdi; BindingHandle
0x1800166e0  call    cs:__imp_RpcImpersonateClient
0x1800166e6  test    eax, eax
0x1800166e8  jz      short loc_180016712
0x1800166ea  mov     [rsp+168h+var_148], 32h ; '2'
0x1800166f2  lea     rcx, [rsp+168h+var_138]
0x1800166f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800166fc  nop
0x1800166fd  lea     rcx, [rsp+168h+var_140]
0x180016702  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016707  nop
0x180016708  mov     r13d, [rsp+168h+var_148]
0x18001670d  jmp     loc_180016A12
0x180016712  mov     [rsp+168h+var_144], 1
0x180016717  mov     rdx, r13
0x18001671a  lea     rcx, [rsp+168h+var_80]
0x180016722  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016727  nop
0x180016728  xorps   xmm0, xmm0
0x18001672b  movups  xmmword ptr [rsp+168h+var_A0], xmm0
0x180016733  mov     [rsp+168h+var_90], r14
0x18001673b  mov     [rsp+168h+var_88], 7
0x180016747  mov     word ptr [rsp+168h+var_A0], r14w
0x180016750  mov     rcx, [rsp+168h+pszPath]; pszPath
0x180016755  call    cs:__imp_PathFindFileNameW
0x18001675b  mov     rdx, rax
0x18001675e  lea     rcx, [rsp+168h+var_60]
0x180016766  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001676b  nop
0x18001676c  lea     rdx, [rsp+168h+var_80]
0x180016774  lea     rcx, [rsp+168h+var_100]
0x180016779  call    ?ConvertDevicePathToDosPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; ConvertDevicePathToDosPath(std::wstring &)
0x18001677e  mov     rdx, rax
0x180016781  lea     rcx, [rsp+168h+var_80]
0x180016789  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001678e  lea     rcx, [rsp+168h+var_100]
0x180016793  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016798  lea     rcx, [rsp+168h+var_80]
0x1800167a0  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800167a5  test    rax, rax
0x1800167a8  jz      short loc_1800167D6
0x1800167aa  lea     rdx, [rsp+168h+var_80]
0x1800167b2  lea     rcx, [rsp+168h+var_100]
0x1800167b7  call    ?GetLocalisedAppDescription@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetLocalisedAppDescription(std::wstring &)
0x1800167bc  mov     rdx, rax
0x1800167bf  lea     rcx, [rsp+168h+var_A0]
0x1800167c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800167cc  lea     rcx, [rsp+168h+var_100]
0x1800167d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800167d6  cmp     [rsp+168h+var_90], r14
0x1800167de  jnz     loc_18001689E
0x1800167e4  test    r12, r12
0x1800167e7  jz      short loc_180016856
0x1800167e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800167ed  inc     rdx
0x1800167f0  cmp     [r12+rdx*2], r14w
0x1800167f5  jnz     short loc_1800167ED
0x1800167f7  cmp     rdx, [rsp+168h+var_88]
0x1800167ff  ja      short loc_18001683C
0x180016801  lea     rdi, [rsp+168h+var_A0]
0x180016809  cmp     [rsp+168h+var_88], 7
0x180016812  cmova   rdi, [rsp+168h+var_A0]
0x18001681b  mov     [rsp+168h+var_90], rdx
0x180016823  lea     rbx, [rdx+rdx]
0x180016827  mov     r8, rbx; Size
0x18001682a  mov     rdx, r12; Src
0x18001682d  mov     rcx, rdi; void *
0x180016830  call    memmove_0
0x180016835  mov     [rbx+rdi], r14w
0x18001683a  jmp     short loc_18001684C
0x18001683c  mov     r9, r12
0x18001683f  lea     rcx, [rsp+168h+var_A0]
0x180016847  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001684c  cmp     [rsp+168h+var_90], r14
0x180016854  jnz     short loc_18001689E
0x180016856  lea     rdx, [rsp+168h+var_60]
0x18001685e  cmp     [rsp+168h+var_48], 7
0x180016867  cmova   rdx, [rsp+168h+var_60]
0x180016870  lea     rcx, [rsp+168h+var_80]
0x180016878  cmp     [rsp+168h+var_68], 7
0x180016881  cmova   rcx, [rsp+168h+var_80]
0x18001688a  mov     r8d, [rsp+168h+arg_20]
0x180016892  mov     rax, r15
0x180016895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001689a  mov     ebx, eax
0x18001689c  jmp     short loc_1800168E4
0x18001689e  lea     rdx, [rsp+168h+var_60]
0x1800168a6  cmp     [rsp+168h+var_48], 7
0x1800168af  cmova   rdx, [rsp+168h+var_60]
0x1800168b8  lea     rcx, [rsp+168h+var_A0]
0x1800168c0  cmp     [rsp+168h+var_88], 7
0x1800168c9  cmova   rcx, [rsp+168h+var_A0]
0x1800168d2  mov     r8d, [rsp+168h+arg_20]
0x1800168da  mov     rax, r15
0x1800168dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e2  mov     ebx, eax
0x1800168e4  test    ebx, ebx
0x1800168e6  js      loc_180016995
0x1800168ec  mov     rcx, rsi; SRWLock
0x1800168ef  call    cs:__imp_AcquireSRWLockExclusive
0x1800168f5  mov     rdx, rsi
0x1800168f8  lea     rcx, [rsp+168h+var_140]
0x1800168fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180016902  mov     [rsp+168h+var_120], r14
0x180016907  lea     rcx, [rsp+168h+var_120]
0x18001690c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016911  mov     rdi, cs:?g_lastToastTime@@3V?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@@2@@std@@A
0x180016918  mov     rdx, r13
0x18001691b  lea     rcx, [rsp+168h+var_100]
0x180016920  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016925  nop
0x180016926  lea     r8, [rsp+168h+var_100]
0x18001692b  lea     rdx, [rsp+168h+var_110]
0x180016930  mov     rcx, rdi
0x180016933  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::map<std::wstring,unsigned __int64>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x180016938  mov     rdi, [rax]
0x18001693b  mov     rdx, [rsp+168h+pszPath]
0x180016940  lea     rcx, [rsp+168h+var_C0]
0x180016948  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001694d  nop
0x18001694e  lea     r8, [rsp+168h+var_C0]
0x180016956  lea     rdx, [rsp+168h+var_120]
0x18001695b  lea     rcx, [rdi+40h]
0x18001695f  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,unsigned __int64>::_Try_emplace<std::wstring,>(std::wstring &&)
0x180016964  mov     rax, [rax]
0x180016967  mov     rcx, [rsp+168h+var_128]
0x18001696c  mov     [rax+40h], rcx
0x180016970  lea     rcx, [rsp+168h+var_C0]
0x180016978  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001697d  nop
0x18001697e  lea     rcx, [rsp+168h+var_100]
0x180016983  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016988  xor     edx, edx
0x18001698a  lea     rcx, [rsp+168h+var_140]
0x18001698f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180016994  nop
0x180016995  lea     rcx, [rsp+168h+var_60]
0x18001699d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800169a2  nop
0x1800169a3  lea     rcx, [rsp+168h+var_A0]
0x1800169ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800169b0  nop
0x1800169b1  lea     rcx, [rsp+168h+var_80]
0x1800169b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800169be  nop
0x1800169bf  lea     rcx, [rsp+168h+var_138]
0x1800169c4  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800169c9  test    ebx, ebx
0x1800169cb  jns     short loc_1800169E2
0x1800169cd  mov     eax, ebx
0x1800169cf  and     eax, 1FFF0000h
0x1800169d4  cmp     eax, 70000h
0x1800169d9  jnz     short loc_1800169DE
0x1800169db  movzx   ebx, bx
0x1800169de  mov     [rsp+168h+var_148], ebx
0x1800169e2  lea     rcx, [rsp+168h+var_140]
0x1800169e7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800169ec  nop
0x1800169ed  mov     r13d, [rsp+168h+var_148]
0x1800169f2  jmp     short loc_180016A12
0x1800169f4  mov     eax, 0A0h
0x1800169f9  jmp     loc_180016B80
0x1800169fe  xor     r14d, r14d
0x180016a01  lea     rsi, ?srwToastTimeLock@@3Vsrwlock@wil@@A; wil::srwlock srwToastTimeLock
0x180016a08  mov     r13d, [rsp+168h+var_148]
0x180016a0d  mov     [rsp+168h+var_148], r13d
0x180016a12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation> `wil::Feature<__WilFeatureTraits_Feature_BlockToastImpersonation>::GetImpl(void)'::`2'::impl
0x180016a19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BlockToastImpersonation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockToastImpersonation>::__private_IsEnabled(void)
0x180016a1e  test    al, al
0x180016a20  jz      short loc_180016A2F
0x180016a22  cmp     [rsp+168h+var_144], r14b
0x180016a27  jz      short loc_180016A2F
0x180016a29  call    cs:__imp_RpcRevertToSelf
0x180016a2f  mov     rcx, rsi; SRWLock
0x180016a32  call    cs:__imp_AcquireSRWLockExclusive
  ... truncated ...
```
