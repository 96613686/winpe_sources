# CModernShareCommand::GetState(IShellItemArray *,int,ulong *)

- ea: `0x18001f880`
- end: `0x18002064d`
- name: `?GetState@CModernShareCommand@@UEAAJPEAUIShellItemArray@@HPEAK@Z`
- size: `3533`
- prototype: `__int64 __fastcall(CModernShareCommand *__hidden this, struct IShellItemArray *, int, unsigned int *)`
- caller_count: `2`
- callee_count: `46`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e6d0`
- `0x180045360`

## callees

- `0x180008750`
- `0x180008900`
- `0x180013f20`
- `0x180015f30`
- `0x18001ade4`
- `0x18001bfd8`
- `0x18001d18c`
- `0x18001efc4`
- `0x18001f880`
- `0x180020c64`
- `0x180020f6c`
- `0x180020fb8`
- `0x1800210dc`
- `0x1800214cc`
- `0x180021a88`
- `0x180021bf8`
- `0x180021f98`
- `0x1800222cc`
- `0x1800223bc`
- `0x1800230a4`
- `0x1800254e0`
- `0x18002bfe8`
- `0x18002cdd0`
- `0x180030e10`
- `0x180031020`
- `0x180038d6c`
- `0x18003a124`
- `0x18003a2ac`
- `0x18003a538`
- `0x18003a678`
- `0x18003b1a4`
- `0x18003c3c0`
- `0x18003d2b8`
- `0x18003d674`
- `0x180041d64`
- `0x1800452f8`
- `0x180047a58`
- `0x180048f44`
- `0x18004f1c4`
- `0x18004f394`
- `0x1800513b8`
- `0x180051598`
- `0x180051740`
- `0x180052930`
- `0x1800531dc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800204ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002051b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800204ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002051b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fd62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fd62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020359`
- `SHCORE!IUnknown_QueryService` at `0x180020579`
- `SHCORE!IUnknown_QueryService` at `0x180020579`

## string_xrefs

- `0x18001f978`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18001fac0`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18001fb9d`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18001fd46`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18001fe86`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18001ffbe`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18002009a`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CModernShareCommand::GetState(
        CModernShareCommand *this,
        struct IShellItemArray *a2,
        unsigned int a3,
        unsigned int *a4)
{
  void *v8; // r12
  __int64 v9; // rdx
  CModernShareCommand *v10; // rcx
  int StorageProviderShareLinkSource; // eax
  const char *v12; // r9
  __int64 result; // rax
  __int64 v14; // rdx
  int v15; // eax
  struct IUnknown *v16; // rdx
  unsigned int v17; // ebx
  void *v18; // rbx
  struct IUnknown *v19; // rdx
  int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  __int64 v23; // rdx
  volatile signed __int32 *v24; // rbx
  int RemotePropertyStoreFromShellItemArray; // eax
  unsigned int v26; // ebx
  __int64 v27; // rax
  unsigned int v28; // ebx
  __int64 v29; // rax
  int v30; // eax
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rax
  int v33; // eax
  volatile signed __int32 *v34; // rbx
  const unsigned __int16 (*v35)[29]; // rdx
  _QWORD *v36; // rax
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  volatile signed __int32 *v40; // rbx
  volatile signed __int32 *v41; // rbx
  unsigned int i; // ebx
  unsigned int v43; // ebx
  void *v44; // rcx
  unsigned int v45; // ebx
  int v46; // [rsp+20h] [rbp-148h]
  char v47[8]; // [rsp+30h] [rbp-138h] BYREF
  void *v48; // [rsp+38h] [rbp-130h] BYREF
  void *v49; // [rsp+40h] [rbp-128h] BYREF
  LPVOID v50[2]; // [rsp+48h] [rbp-120h] BYREF
  LPVOID v51; // [rsp+58h] [rbp-110h] BYREF
  struct IPropertyStore *v52; // [rsp+60h] [rbp-108h] BYREF
  unsigned int v53; // [rsp+68h] [rbp-100h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-F8h] BYREF
  char v55; // [rsp+78h] [rbp-F0h]
  struct IExplorerCommand *v56; // [rsp+80h] [rbp-E8h] BYREF
  void *ppvOut; // [rsp+88h] [rbp-E0h] BYREF
  _BYTE v58[56]; // [rsp+90h] [rbp-D8h] BYREF
  volatile signed __int32 *v59; // [rsp+C8h] [rbp-A0h]
  _QWORD v60[2]; // [rsp+D0h] [rbp-98h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-88h]
  HSTRING string[2]; // [rsp+F0h] [rbp-78h] BYREF
  int v63; // [rsp+100h] [rbp-68h]
  unsigned __int64 v64; // [rsp+108h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  try
  {
    *a4 = 2;
    v8 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl'::`2'::impl)
      || !(unsigned __int8)IsAnyItemCloudPlaceholder(a2)
      || (LOBYTE(v9) = a3 != 0, !(unsigned __int8)AllItemsAreBackedBySameSameStorageProvider(a2, v9)) )
    {
LABEL_20:
      if ( a2 )
      {
        v53 = 0;
        v20 = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v53);
        v21 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x916,
            (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
            (const char *)(unsigned int)v20,
            v46);
          return v21;
        }
        v22 = v53;
        if ( v53 == 1 )
        {
          if ( IsRemoteFileFromShellItemArray(a2, 0) )
          {
            v50[0] = 0;
            tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::start_and_watch_errors(
              v50,
              v58);
            wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>,wil::err_returncode_policy>(v50);
            if ( !a3 )
            {
              v24 = v59;
              v50[0] = (LPVOID)v59;
              if ( v59 )
                _InterlockedIncrement(v59 + 70);
              tip2::details::shared_data<0,0,0>::begin_update(v24 + 2);
              *((_BYTE *)v24 + 272) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v50);
              tip2::details::shared_data<0,0,0>::complete_without_lock(v59 + 2);
              tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v58);
              return 2147483658LL;
            }
            v52 = 0;
            RemotePropertyStoreFromShellItemArray = TryGetRemotePropertyStoreFromShellItemArray(a2, v23, &v52);
            v26 = RemotePropertyStoreFromShellItemArray;
            if ( RemotePropertyStoreFromShellItemArray < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x92B,
                (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                (const char *)(unsigned int)RemotePropertyStoreFromShellItemArray,
                v46);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v52);
              tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v58);
              return v26;
            }
            wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)&v48, v52);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_SharedBackend>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FE_SharedBackend>::GetImpl'::`2'::impl) )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl'::`2'::impl) )
              {
                pv = 0;
                v27 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
                *(_OWORD *)string = PKEY_StorageProviderFullyQualifiedId;
                v63 = 119;
                if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v48, string, v27) >= 0 )
                {
                  v56 = 0;
                  if ( (int)CModernShareCommand::GetCloudProviderShareHandlerFromId(
                              this,
                              (const unsigned __int16 *)pv,
                              &v56) >= 0 )
                  {
                    v28 = ((__int64 (__fastcall *)(struct IExplorerCommand *, struct IShellItemArray *, _QWORD, unsigned int *))v56->lpVtbl->GetState)(
                            v56,
                            a2,
                            a3,
                            a4);
                    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v56);
                    if ( pv )
                      CoTaskMemFree(pv);
LABEL_74:
                    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v48);
                    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v52);
                    tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v58);
                    return v28;
                  }
                  wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v56);
                }
                if ( pv )
                  CoTaskMemFree(pv);
              }
              v50[0] = 0;
              v29 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v50);
              *(_OWORD *)string = PKEY_Home_ListItemUniqueId;
              v63 = 13;
              v30 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v48, string, v29);
              v28 = v30;
              if ( v30 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x93F,
                  (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                  (const char *)(unsigned int)v30,
                  v46);
                if ( v50[0] )
                  CoTaskMemFree(v50[0]);
                goto LABEL_74;
              }
              if ( !v50[0] || !*(_WORD *)v50[0] )
              {
                *a4 = 2;
                v31 = v59;
                pv = (LPVOID)v59;
                if ( v59 )
                  _InterlockedIncrement(v59 + 70);
                tip2::details::shared_data<0,0,0>::begin_update(v31 + 2);
                *((_BYTE *)v31 + 276) = 0;
                tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(&pv);
                tip2::details::shared_data<0,0,0>::complete_without_lock(v59 + 2);
                if ( v50[0] )
                  CoTaskMemFree(v50[0]);
                goto LABEL_52;
              }
              CoTaskMemFree(v50[0]);
            }
            v51 = 0;
            v32 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v51);
            *(_OWORD *)string = PKEY_Home_UserOneDriveCid;
            v63 = 18;
            v33 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v48, string, v32);
            v28 = v33;
            if ( v33 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x94B,
                (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                (const char *)(unsigned int)v33,
                v46);
              if ( v51 )
                CoTaskMemFree(v51);
              goto LABEL_74;
            }
            CModernShareCommand::TryGetShareCmdStateFromCache(this, v50, v51);
            if ( BYTE4(v50[0]) )
            {
              *a4 = (unsigned int)v50[0];
              v34 = v59;
              v50[0] = (LPVOID)v59;
              if ( v59 )
                _InterlockedIncrement(v59 + 70);
              tip2::details::shared_data<0,0,0>::begin_update(v34 + 2);
              *((_BYTE *)v34 + 273) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v50);
              tip2::details::shared_data<0,0,0>::complete_without_lock(v59 + 2);
              if ( v51 )
                CoTaskMemFree(v51);
LABEL_52:
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v48);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v52);
              tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v58);
              return 0;
            }
            std::wstring::wstring(v60, v51);
            v49 = 0;
            v36 = (_QWORD *)Windows::Internal::StringReference::StringReference(string, v35);
            v37 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                    *v36,
                    &v49);
            v28 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x95B,
                (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                (const char *)(unsigned int)v37,
                v46);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v49);
              if ( si128.m128i_i64[1] > 7uLL )
                std::_Deallocate<16>(v60[0], 2 * si128.m128i_i64[1] + 2);
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v60[0]) = 0;
              if ( v51 )
                CoTaskMemFree(v51);
              goto LABEL_74;
            }
            v50[0] = v51;
            v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(string, v50);
            v39 = AddStringToJSON(L"CID", *(_QWORD *)(v38 + 24), &v49);
            v28 = v39;
            if ( v39 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x95C,
                (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                (const char *)(unsigned int)v39,
                v46);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v49);
              if ( si128.m128i_i64[1] > 7uLL )
                std::_Deallocate<16>(v60[0], 2 * si128.m128i_i64[1] + 2);
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v60[0]) = 0;
              if ( v51 )
                CoTaskMemFree(v51);
              goto LABEL_74;
            }
            if ( (int)CModernShareCommand::OneDriveInvoke(this, L"IsShareAvailable", &v49) < 0 )
            {
              *a4 = 2;
              v47[0] = 0;
              std::pair<std::wstring const,bool>::pair<std::wstring const,bool>(string, v60, v47);
              std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::insert<0,0>(
                (char *)this + 216,
                v50,
                string);
              if ( v64 > 7 )
                std::_Deallocate<16>(string[0], 2 * v64 + 2);
              v41 = v59;
              v50[0] = (LPVOID)v59;
              if ( v59 )
                _InterlockedIncrement(v59 + 70);
              tip2::details::shared_data<0,0,0>::begin_update(v41 + 2);
              *((_BYTE *)v41 + 275) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v50);
              tip2::details::shared_data<0,0,0>::complete_without_lock(v59 + 2);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v49);
              if ( si128.m128i_i64[1] > 7uLL )
                std::_Deallocate<16>(v60[0], 2 * si128.m128i_i64[1] + 2);
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v60[0]) = 0;
              if ( v51 )
                CoTaskMemFree(v51);
            }
            else
            {
              *a4 = 0;
              v47[0] = 1;
              std::pair<std::wstring const,bool>::pair<std::wstring const,bool>(string, v60, v47);
              std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::insert<0,0>(
                (char *)this + 216,
                v50,
                string);
              if ( v64 > 7 )
                std::_Deallocate<16>(string[0], 2 * v64 + 2);
              v40 = v59;
              v50[0] = (LPVOID)v59;
              if ( v59 )
                _InterlockedIncrement(v59 + 70);
              tip2::details::shared_data<0,0,0>::begin_update(v40 + 2);
              *((_BYTE *)v40 + 274) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v50);
              tip2::details::shared_data<0,0,0>::complete_without_lock(v59 + 2);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v49);
              if ( si128.m128i_i64[1] > 7uLL )
                std::_Deallocate<16>(v60[0], 2 * si128.m128i_i64[1] + 2);
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v60[0]) = 0;
              if ( v51 )
                CoTaskMemFree(v51);
            }
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v48);
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v52);
            tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(v58);
            return 0;
          }
        }
        else if ( v53 > 1 )
        {
          for ( i = 0; i < v22; ++i )
          {
            if ( IsRemoteFileFromShellItemArray(a2, i) )
            {
              *a4 = 2;
              return 0;
            }
            v22 = v53;
          }
        }
      }
      if ( (unsigned __int8)IsAnyItemCloudPlaceholder(a2) )
      {
        v50[0] = 0;
        if ( (int)CModernShareCommand::GetCloudProviderShareHandler(this, a2, v50) >= 0 )
        {
          v43 = (*(__int64 (__fastcall **)(LPVOID, struct IShellItemArray *, _QWORD, unsigned int *))(*(_QWORD *)v50[0] + 56LL))(
                  v50[0],
                  a2,
                  a3,
                  a4);
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v50);
          return v43;
        }
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v50);
      }
      else if ( a2 )
      {
        v49 = 0;
        if ( (unsigned __int8)AllItemsAreBackedBySameSameStorageProvider(a2, 0) )
        {
          v44 = v49;
          v49 = 0;
          if ( v44 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v44 + 16LL))(v44);
          if ( (int)CreateIdentityShellItemArray(a2, 0, &v49) >= 0 )
          {
            v50[0] = 0;
            if ( (int)CModernShareCommand::GetCloudProviderShareHandler(this, v49, v50) >= 0 )
            {
              v45 = (*(__int64 (__fastcall **)(LPVOID, void *, _QWORD, unsigned int *))(*(_QWORD *)v50[0] + 56LL))(
                      v50[0],
                      v49,
                      a3,
                      a4);
              Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v50);
              wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v49);
              return v45;
            }
            AcquireSRWLockExclusive((PSRWLOCK)this + 24);
            pv = (char *)this + 192;
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease((char *)this + 200);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              (char *)this + 208,
              0);
            CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)&pv);
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v50);
          }
        }
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v49);
      }
      else
      {
        AcquireSRWLockExclusive((PSRWLOCK)this + 24);
        v50[0] = (char *)this + 192;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease((char *)this + 200);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (char *)this + 208,
          0);
        CAutoSRWExclusiveLock::~CAutoSRWExclusiveLock((CAutoSRWExclusiveLock *)v50);
      }
      ppvOut = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
      if ( IUnknown_QueryService(
             *((IUnknown **)this + 5),
             &GUID_9ea5491c_89c8_4bef_93d3_7f665fb82a33,
             &GUID_42f85136_db7e_439c_85f1_e4075d135fc8,
             &ppvOut) < 0 )
      {
        *a4 = 2;
        v53 = 0;
        if ( a2 )
        {
          if ( ((int (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v53) >= 0 )
          {
            if ( v53 )
            {
              LODWORD(v52) = 0;
              if ( ((int (__fastcall *)(struct IShellItemArray *, __int64, __int64, struct IPropertyStore **))a2->lpVtbl->GetAttributes)(
                     a2,
                     1,
                     0x400000,
                     &v52) >= 0
                && (_DWORD)v52 == 0x400000 )
              {
                *a4 = 0;
                LODWORD(v48) = 0;
                if ( (int)_GetSyncRootItemTypes(*((IUnknown **)this + 5), a2, 0, (enum SyncRootItemType *)&v48) >= 0
                  && ((unsigned __int8)v48 & 4) != 0 )
                {
                  *a4 = 2;
                }
              }
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppvOut);
      return 0;
    }
    v51 = 0;
    StorageProviderShareLinkSource = CModernShareCommand::TryGetStorageProviderShareLinkSource(
                                       v10,
                                       a2,
                                       a3,
                                       (struct winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource *)&v51);
    if ( StorageProviderShareLinkSource == 1 )
    {
      if ( !a3 )
      {
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v51);
        return 2147483658LL;
      }
    }
    else if ( StorageProviderShareLinkSource < 0 )
    {
LABEL_19:
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v51);
      goto LABEL_20;
    }
    v50[0] = 0;
    if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v51, v50) )
    {
      v49 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(&v49);
      v15 = CreateStorageItemVectorViewFromShellItemArray(a2, v14, &v49);
      v17 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x902,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v15,
          v46);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(&v49);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v51);
        return v17;
      }
      v48 = 0;
      v18 = v49;
      if ( v49 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 8LL))(v49);
        *winrt::put_abi((winrt *)&v48, v19) = v18;
        v8 = v48;
      }
      pv = 0;
      v55 = 0;
      *winrt::put_abi((winrt *)&pv, v16) = v8;
      winrt::impl::consume_Windows_Storage_Provider_IStorageProviderShareLinkSource<winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource>::GetState(
        &v51,
        v50,
        &pv);
      if ( !v55 )
        pv = 0;
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&pv);
      if ( !(unsigned int)winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Storage::Provider::StorageProviderShareLinkState>>(v50) )
      {
        *a4 = 0;
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v50);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v48);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(&v49);
        winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v51);
        return 0;
      }
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)v50);
      winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v48);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(&v49);
    }
    goto LABEL_19;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9CB,
                           (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18001f880  push    rbx
0x18001f882  push    rdi
0x18001f883  push    r12
0x18001f885  push    r13
0x18001f887  push    r14
0x18001f889  push    r15
0x18001f88b  sub     rsp, 138h
0x18001f892  mov     rax, cs:__security_cookie
0x18001f899  xor     rax, rsp
0x18001f89c  mov     [rsp+168h+var_48], rax
0x18001f8a4  mov     r14, r9
0x18001f8a7  mov     r13d, r8d
0x18001f8aa  mov     rdi, rdx
0x18001f8ad  mov     r15, rcx
0x18001f8b0  mov     dword ptr [r9], 2
0x18001f8b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SCFTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SCFTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest> `wil::Feature<__WilFeatureTraits_Feature_SCFTest>::GetImpl(void)'::`2'::impl
0x18001f8be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SCFTest@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCFTest>::__private_IsEnabled(void)
0x18001f8c3  xor     r12d, r12d
0x18001f8c6  test    al, al
0x18001f8c8  jz      loc_18001FA8D
0x18001f8ce  mov     rcx, rdi
0x18001f8d1  call    _IsAnyItemCloudPlaceholder
0x18001f8d6  test    al, al
0x18001f8d8  jz      loc_18001FA8D
0x18001f8de  test    r13d, r13d
0x18001f8e1  setnz   dl
0x18001f8e4  mov     rcx, rdi
0x18001f8e7  call    AllItemsAreBackedBySameSameStorageProvider
0x18001f8ec  test    al, al
0x18001f8ee  jz      loc_18001FA8D
0x18001f8f4  mov     [rsp+168h+var_110], r12
0x18001f8f9  lea     r9, [rsp+168h+var_110]; struct winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource *
0x18001f8fe  mov     r8d, r13d; int
0x18001f901  mov     rdx, rdi; struct IShellItemArray *
0x18001f904  call    ?TryGetStorageProviderShareLinkSource@CModernShareCommand@@AEAAJPEAUIShellItemArray@@HAEAUIStorageProviderShareLinkSource@Provider@Storage@Windows@winrt@@@Z; CModernShareCommand::TryGetStorageProviderShareLinkSource(IShellItemArray *,int,winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource &)
0x18001f909  cmp     eax, 1
0x18001f90c  jnz     short loc_18001F927
0x18001f90e  test    r13d, r13d
0x18001f911  jnz     short loc_18001F92F
0x18001f913  lea     rcx, [rsp+168h+var_110]; this
0x18001f918  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f91d  mov     eax, 8000000Ah
0x18001f922  jmp     loc_18002062A
0x18001f927  test    eax, eax
0x18001f929  js      loc_18001FA83
0x18001f92f  mov     [rsp+168h+var_120], r12
0x18001f934  lea     rdx, [rsp+168h+var_120]
0x18001f939  lea     rcx, [rsp+168h+var_110]
0x18001f93e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001f943  test    al, al
0x18001f945  jnz     loc_18001FA83
0x18001f94b  mov     [rsp+168h+var_128], r12
0x18001f950  lea     rcx, [rsp+168h+var_128]
0x18001f955  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(void)
0x18001f95a  lea     r8, [rsp+168h+var_128]
0x18001f95f  mov     rcx, rdi
0x18001f962  call    ?CreateStorageItemVectorViewFromShellItemArray@@YAJPEAUIShellItemArray@@PEBGPEAPEAU?$IVectorView@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Z; CreateStorageItemVectorViewFromShellItemArray(IShellItemArray *,ushort const *,Windows::Foundation::Collections::IVectorView<Windows::Storage::IStorageItem *> * *)
0x18001f967  mov     ebx, eax
0x18001f969  test    eax, eax
0x18001f96b  jns     short loc_18001F9A6
0x18001f96d  mov     rcx, [rsp+168h]; this
0x18001f975  mov     r9d, eax; char *
0x18001f978  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18001f97f  mov     edx, 902h; void *
0x18001f984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f989  nop
0x18001f98a  lea     rcx, [rsp+168h+var_128]
0x18001f98f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(void)
0x18001f994  nop
0x18001f995  lea     rcx, [rsp+168h+var_110]; this
0x18001f99a  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001f99f  mov     eax, ebx
0x18001f9a1  jmp     loc_18002062A
0x18001f9a6  mov     [rsp+168h+var_130], r12
0x18001f9ab  mov     rbx, [rsp+168h+var_128]
0x18001f9b0  test    rbx, rbx
0x18001f9b3  jz      short loc_18001F9D6
0x18001f9b5  mov     rax, [rbx]
0x18001f9b8  mov     rcx, rbx
0x18001f9bb  mov     rax, [rax+8]
0x18001f9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9c4  lea     rcx, [rsp+168h+var_130]; this
0x18001f9c9  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18001f9ce  mov     [rax], rbx
0x18001f9d1  mov     r12, [rsp+168h+var_130]
0x18001f9d6  mov     [rsp+168h+pv], 0
0x18001f9df  mov     [rsp+168h+var_F0], 0
0x18001f9e4  lea     rcx, [rsp+168h+pv]; this
0x18001f9e9  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18001f9ee  mov     [rax], r12
0x18001f9f1  lea     r8, [rsp+168h+pv]
0x18001f9f6  lea     rdx, [rsp+168h+var_120]
0x18001f9fb  lea     rcx, [rsp+168h+var_110]
0x18001fa00  call    ?GetState@?$consume_Windows_Storage_Provider_IStorageProviderShareLinkSource@UIStorageProviderShareLinkSource@Provider@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBU?$async_vector_view@UIStorageItem@Storage@Windows@winrt@@@param@3@@Z; winrt::impl::consume_Windows_Storage_Provider_IStorageProviderShareLinkSource<winrt::Windows::Storage::Provider::IStorageProviderShareLinkSource>::GetState(winrt::param::async_vector_view<winrt::Windows::Storage::IStorageItem> const &)
0x18001fa05  nop
0x18001fa06  xor     r12d, r12d
0x18001fa09  cmp     [rsp+168h+var_F0], r12b
0x18001fa0e  jnz     short loc_18001FA15
0x18001fa10  mov     [rsp+168h+pv], r12
0x18001fa15  lea     rcx, [rsp+168h+pv]; this
0x18001fa1a  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fa1f  lea     rcx, [rsp+168h+var_120]
0x18001fa24  call    ??$wait_get@U?$IAsyncOperation@W4StorageProviderShareLinkState@Provider@Storage@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@W4StorageProviderShareLinkState@Provider@Storage@Windows@winrt@@@Foundation@Windows@1@@Z
0x18001fa29  test    eax, eax
0x18001fa2b  jnz     short loc_18001FA62
0x18001fa2d  mov     [r14], r12d
0x18001fa30  lea     rcx, [rsp+168h+var_120]; this
0x18001fa35  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fa3a  nop
0x18001fa3b  lea     rcx, [rsp+168h+var_130]; this
0x18001fa40  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fa45  nop
0x18001fa46  lea     rcx, [rsp+168h+var_128]
0x18001fa4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(void)
0x18001fa50  nop
0x18001fa51  lea     rcx, [rsp+168h+var_110]; this
0x18001fa56  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fa5b  xor     eax, eax
0x18001fa5d  jmp     loc_18002062A
0x18001fa62  lea     rcx, [rsp+168h+var_120]; this
0x18001fa67  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fa6c  nop
0x18001fa6d  lea     rcx, [rsp+168h+var_130]; this
0x18001fa72  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fa77  nop
0x18001fa78  lea     rcx, [rsp+168h+var_128]
0x18001fa7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(void)
0x18001fa82  nop
0x18001fa83  lea     rcx, [rsp+168h+var_110]; this
0x18001fa88  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18001fa8d  test    rdi, rdi
0x18001fa90  jz      loc_1800203B7
0x18001fa96  mov     [rsp+168h+var_100], r12d
0x18001fa9b  mov     rax, [rdi]
0x18001fa9e  lea     rdx, [rsp+168h+var_100]
0x18001faa3  mov     rcx, rdi
0x18001faa6  mov     rax, [rax+38h]
0x18001faaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faaf  mov     ebx, eax
0x18001fab1  test    eax, eax
0x18001fab3  jns     short loc_18001FAD8
0x18001fab5  mov     rcx, [rsp+168h]; this
0x18001fabd  mov     r9d, eax; char *
0x18001fac0  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18001fac7  mov     edx, 916h; void *
0x18001facc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fad1  mov     eax, ebx
0x18001fad3  jmp     loc_18002062A
0x18001fad8  mov     eax, [rsp+168h+var_100]
0x18001fadc  cmp     eax, 1
0x18001fadf  jnz     loc_18002038A
0x18001fae5  xor     edx, edx; unsigned int
0x18001fae7  mov     rcx, rdi; struct IShellItemArray *
0x18001faea  call    ?IsRemoteFileFromShellItemArray@@YA_NPEAUIShellItemArray@@K@Z; IsRemoteFileFromShellItemArray(IShellItemArray *,ulong)
0x18001faef  test    al, al
0x18001faf1  jz      loc_1800203B7
0x18001faf7  mov     [rsp+168h+var_120], r12
0x18001fafc  lea     rdx, [rsp+168h+var_D8]
0x18001fb04  lea     rcx, [rsp+168h+var_120]
0x18001fb09  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_FileExplorerOneDriveShareIconVisibility@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_FileExplorerOneDriveShareIconVisibility@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::start_and_watch_errors(void)
0x18001fb0e  lea     rcx, [rsp+168h+var_120]
0x18001fb13  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FileExplorerOneDriveShareIconVisibility@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>,wil::err_returncode_policy>(void)
0x18001fb18  nop
0x18001fb19  test    r13d, r13d
0x18001fb1c  jnz     short loc_18001FB7A
0x18001fb1e  mov     rbx, [rsp+168h+var_A0]
0x18001fb26  mov     [rsp+168h+var_120], rbx
0x18001fb2b  test    rbx, rbx
0x18001fb2e  jz      short loc_18001FB37
0x18001fb30  lock inc dword ptr [rbx+118h]
0x18001fb37  lea     rcx, [rbx+8]
0x18001fb3b  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18001fb40  mov     byte ptr [rbx+110h], 1
0x18001fb47  lea     rcx, [rsp+168h+var_120]
0x18001fb4c  call    ??1?$test_data_control@V?$merged_data@U_tip_FileExplorerOneDriveShareIconVisibility@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_data_control<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(void)
0x18001fb51  mov     rcx, [rsp+168h+var_A0]
0x18001fb59  add     rcx, 8
0x18001fb5d  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18001fb62  nop
0x18001fb63  lea     rcx, [rsp+168h+var_D8]
0x18001fb6b  call    ??1?$test_watcher@V?$merged_data@U_tip_FileExplorerOneDriveShareIconVisibility@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(void)
0x18001fb70  mov     eax, 8000000Ah
0x18001fb75  jmp     loc_18002062A
0x18001fb7a  mov     [rsp+168h+var_108], r12
0x18001fb7f  lea     r8, [rsp+168h+var_108]
0x18001fb84  mov     rcx, rdi
0x18001fb87  call    ?TryGetRemotePropertyStoreFromShellItemArray@@YAJPEAUIShellItemArray@@KAEAV?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@Z; TryGetRemotePropertyStoreFromShellItemArray(IShellItemArray *,ulong,Microsoft::WRL::ComPtr<IPropertyStore> &)
0x18001fb8c  mov     ebx, eax
0x18001fb8e  test    eax, eax
0x18001fb90  jns     short loc_18001FBCE
0x18001fb92  mov     rcx, [rsp+168h]; this
0x18001fb9a  mov     r9d, eax; char *
0x18001fb9d  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18001fba4  mov     edx, 92Bh; void *
0x18001fba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fbae  nop
0x18001fbaf  lea     rcx, [rsp+168h+var_108]
0x18001fbb4  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001fbb9  nop
0x18001fbba  lea     rcx, [rsp+168h+var_D8]
0x18001fbc2  call    ??1?$test_watcher@V?$merged_data@U_tip_FileExplorerOneDriveShareIconVisibility@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(void)
0x18001fbc7  mov     eax, ebx
0x18001fbc9  jmp     loc_18002062A
0x18001fbce  mov     rdx, [rsp+168h+var_108]; struct IPropertyStore *
0x18001fbd3  lea     rcx, [rsp+168h+var_130]; this
0x18001fbd8  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x18001fbdd  nop
0x18001fbde  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FE_SharedBackend@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FE_SharedBackend@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_SharedBackend> `wil::Feature<__WilFeatureTraits_Feature_FE_SharedBackend>::GetImpl(void)'::`2'::impl
0x18001fbe5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FE_SharedBackend@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FE_SharedBackend>::__private_IsEnabled(void)
0x18001fbea  test    al, al
0x18001fbec  jz      loc_18001FE35
0x18001fbf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56314744@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744> `wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl(void)'::`2'::impl
0x18001fbf9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(wil::ReportingKind)
0x18001fbfe  test    al, al
0x18001fc00  jz      loc_18001FCF5
0x18001fc06  mov     [rsp+168h+pv], r12
0x18001fc0b  lea     rcx, [rsp+168h+pv]
0x18001fc10  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18001fc15  movups  xmm0, cs:PKEY_StorageProviderFullyQualifiedId
0x18001fc1c  movaps  xmmword ptr [rsp+168h+string], xmm0
0x18001fc24  mov     ecx, cs:dword_180082CC8
0x18001fc2a  mov     [rsp+168h+var_68], ecx
0x18001fc31  mov     r8, rax
0x18001fc34  lea     rdx, [rsp+168h+string]
0x18001fc3c  lea     rcx, [rsp+168h+var_130]
0x18001fc41  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18001fc46  test    eax, eax
0x18001fc48  js      loc_18001FCE5
0x18001fc4e  mov     [rsp+168h+var_E8], r12
0x18001fc56  lea     r8, [rsp+168h+var_E8]; struct IExplorerCommand **
0x18001fc5e  mov     rdx, [rsp+168h+pv]; unsigned __int16 *
0x18001fc63  mov     rcx, r15; this
0x18001fc66  call    ?GetCloudProviderShareHandlerFromId@CModernShareCommand@@QEAAJPEBGPEAPEAUIExplorerCommand@@@Z; CModernShareCommand::GetCloudProviderShareHandlerFromId(ushort const *,IExplorerCommand * *)
0x18001fc6b  test    eax, eax
0x18001fc6d  js      short loc_18001FCD7
0x18001fc6f  mov     rcx, [rsp+168h+var_E8]
0x18001fc77  mov     rax, [rcx]
0x18001fc7a  mov     r9, r14
0x18001fc7d  mov     r8d, r13d
0x18001fc80  mov     rdx, rdi
0x18001fc83  mov     rax, [rax+38h]
0x18001fc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc8c  mov     ebx, eax
0x18001fc8e  lea     rcx, [rsp+168h+var_E8]
0x18001fc96  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18001fc9b  nop
0x18001fc9c  mov     rcx, [rsp+168h+pv]; pv
0x18001fca1  test    rcx, rcx
0x18001fca4  jz      short loc_18001FCAD
0x18001fca6  call    cs:__imp_CoTaskMemFree
0x18001fcac  nop
0x18001fcad  lea     rcx, [rsp+168h+var_130]
0x18001fcb2  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001fcb7  nop
0x18001fcb8  lea     rcx, [rsp+168h+var_108]
0x18001fcbd  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001fcc2  nop
0x18001fcc3  lea     rcx, [rsp+168h+var_D8]
0x18001fccb  call    ??1?$test_watcher@V?$merged_data@U_tip_FileExplorerOneDriveShareIconVisibility@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>::~test_watcher<tip2::details::merged_data<_tip_FileExplorerOneDriveShareIconVisibility,_tip_FileExplorerOneDriveShareIconVisibility>>(void)
0x18001fcd0  mov     eax, ebx
0x18001fcd2  jmp     loc_18002062A
0x18001fcd7  lea     rcx, [rsp+168h+var_E8]
0x18001fcdf  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18001fce4  nop
0x18001fce5  mov     rcx, [rsp+168h+pv]; pv
0x18001fcea  test    rcx, rcx
0x18001fced  jz      short loc_18001FCF5
0x18001fcef  call    cs:__imp_CoTaskMemFree
0x18001fcf5  mov     [rsp+168h+var_120], r12
0x18001fcfa  lea     rcx, [rsp+168h+var_120]
0x18001fcff  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18001fd04  movups  xmm0, cs:PKEY_Home_ListItemUniqueId
0x18001fd0b  movaps  xmmword ptr [rsp+168h+string], xmm0
0x18001fd13  mov     ecx, cs:dword_18007E820
0x18001fd19  mov     [rsp+168h+var_68], ecx
0x18001fd20  mov     r8, rax
0x18001fd23  lea     rdx, [rsp+168h+string]
0x18001fd2b  lea     rcx, [rsp+168h+var_130]
0x18001fd30  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18001fd35  mov     ebx, eax
0x18001fd37  test    eax, eax
0x18001fd39  jns     short loc_18001FD93
0x18001fd3b  mov     rcx, [rsp+168h]; this
0x18001fd43  mov     r9d, eax; char *
0x18001fd46  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18001fd4d  mov     edx, 93Fh; void *
0x18001fd52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd57  nop
0x18001fd58  mov     rcx, [rsp+168h+var_120]; pv
0x18001fd5d  test    rcx, rcx
0x18001fd60  jz      short loc_18001FD69
0x18001fd62  call    cs:__imp_CoTaskMemFree
0x18001fd68  nop
0x18001fd69  lea     rcx, [rsp+168h+var_130]
0x18001fd6e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001fd73  nop
0x18001fd74  lea     rcx, [rsp+168h+var_108]
0x18001fd79  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001fd7e  nop
0x18001fd7f  lea     rcx, [rsp+168h+var_D8]
  ... truncated ...
```
