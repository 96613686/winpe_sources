# CNodeChangeSetBuilder::EnumerateCacheEntries(IConfigSession2 *,ushort const *,ushort const *,int *,std::function<long (ushort *,ushort *,tagVARIANT *,ConfigDataType)> &&)

- ea: `0x18005ce1c`
- end: `0x18005d99b`
- name: `?EnumerateCacheEntries@CNodeChangeSetBuilder@@QEAAJPEAUIConfigSession2@@PEBG1PEAH$$QEAV?$function@$$A6AJPEAG0PEAUtagVARIANT@@W4ConfigDataType@@@Z@std@@@Z`
- size: `2943`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c628`
- `0x18005c930`

## callees

- `0x180008de0`
- `0x18000caf4`
- `0x18000d4b4`
- `0x18000d4d4`
- `0x180015888`
- `0x180019b34`
- `0x180019fd8`
- `0x180025a9c`
- `0x18002dc94`
- `0x180057030`
- `0x18005a370`
- `0x18005a654`
- `0x18005b06c`
- `0x18005b0c8`
- `0x18005b144`
- `0x18005b1a0`
- `0x18005be64`
- `0x18005c0b8`
- `0x18005c1e0`
- `0x18005ce1c`
- `0x18005d9a4`
- `0x18005e334`
- `0x18005ee38`
- `0x18005eed4`
- `0x180060030`
- `0x1800600e4`
- `0x180107010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005d65c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005d65c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005d456`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005d456`
- `OLEAUT32!__imp_VariantInit` at `0x18005d2df`
- `OLEAUT32!__imp_VariantInit` at `0x18005d2df`
- `OLEAUT32!__imp_VariantClear` at `0x18005d3ab`
- `OLEAUT32!__imp_VariantClear` at `0x18005d506`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6d3`
- `OLEAUT32!__imp_VariantClear` at `0x18005d773`
- `OLEAUT32!__imp_VariantClear` at `0x18005d3ab`
- `OLEAUT32!__imp_VariantClear` at `0x18005d506`
- `OLEAUT32!__imp_VariantClear` at `0x18005d6d3`
- `OLEAUT32!__imp_VariantClear` at `0x18005d773`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005cea2`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005d317`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005d471`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005d806`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005cea2`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005d317`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005d471`
- `api-ms-win-core-realtime-l1-1-1!QueryUnbiasedInterruptTimePrecise` at `0x18005d806`
- `CRYPTSP!CryptAcquireContextW` at `0x18005d1b0`
- `CRYPTSP!CryptAcquireContextW` at `0x18005d1b0`

## string_xrefs

- `0x18005ce5a`: `EnumerateCacheEntriesActivity`
- `0x18005cf14`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005cf8d`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005d094`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005d225`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005d391`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005d4de`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005d6ab`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005d8ef`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CNodeChangeSetBuilder::EnumerateCacheEntries(
        __int64 a1,
        struct IConfigSession2 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        _DWORD *a5,
        __int64 a6)
{
  unsigned __int64 v9; // r15
  unsigned int v10; // esi
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  __int64 result; // rax
  CNodeChangeSetBuilder *v16; // rcx
  int PolicyRootNode; // eax
  unsigned int v18; // ebx
  struct IConfigNode *v19; // rdi
  __int64 (__fastcall *v20)(struct IConfigNode *, unsigned __int16 **); // rbx
  int v21; // eax
  unsigned int v22; // ebx
  struct IConfigNode *v23; // rdi
  int (__fastcall *v24)(struct IConfigNode *, __int64 *); // rbx
  const char *v25; // r9
  unsigned int v26; // r14d
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64, struct IConfigNode **, int *); // rbx
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // eax
  unsigned int v32; // ebx
  struct IConfigNode *v33; // rdi
  __int64 (__fastcall *v34)(struct IConfigNode *, unsigned __int64 *); // rbx
  int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // rcx
  int v38; // eax
  unsigned int v39; // ebx
  unsigned int LastError; // ebx
  int dwFlags; // [rsp+20h] [rbp-2A8h]
  int dwFlagsa; // [rsp+20h] [rbp-2A8h]
  unsigned __int64 *dwFlagsb; // [rsp+20h] [rbp-2A8h]
  struct IConfigManager2 *v44; // [rsp+40h] [rbp-288h] BYREF
  struct IConfigNode *v45; // [rsp+48h] [rbp-280h] BYREF
  struct IConfigNode *v46; // [rsp+50h] [rbp-278h] BYREF
  struct IConfigNode *v47; // [rsp+58h] [rbp-270h] BYREF
  unsigned __int16 *v48; // [rsp+60h] [rbp-268h] BYREF
  __int64 v49; // [rsp+68h] [rbp-260h] BYREF
  wchar_t *Str; // [rsp+70h] [rbp-258h] BYREF
  unsigned __int64 v51; // [rsp+78h] [rbp-250h] BYREF
  unsigned __int64 v52; // [rsp+80h] [rbp-248h] BYREF
  HCRYPTPROV phProv; // [rsp+88h] [rbp-240h] BYREF
  __int128 v54; // [rsp+90h] [rbp-238h] BYREF
  int v55; // [rsp+A0h] [rbp-228h] BYREF
  int v56; // [rsp+A4h] [rbp-224h] BYREF
  int v57; // [rsp+A8h] [rbp-220h] BYREF
  int v58; // [rsp+ACh] [rbp-21Ch] BYREF
  unsigned __int64 v59; // [rsp+B0h] [rbp-218h] BYREF
  VARIANTARG *p_pvarg; // [rsp+B8h] [rbp-210h] BYREF
  unsigned __int64 v61; // [rsp+C0h] [rbp-208h] BYREF
  unsigned __int64 v62; // [rsp+C8h] [rbp-200h] BYREF
  unsigned __int64 UnbiasedInterruptTimePrecise; // [rsp+D0h] [rbp-1F8h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-1F0h] BYREF
  wchar_t *v65; // [rsp+F0h] [rbp-1D8h] BYREF
  _BYTE v66[16]; // [rsp+F8h] [rbp-1D0h] BYREF
  _BYTE v67[40]; // [rsp+108h] [rbp-1C0h] BYREF
  _QWORD v68[42]; // [rsp+130h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v68);
  v68[0] = &NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::`vftable';
  NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::StartActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
  v9 = 0;
  *a5 = 0;
  UnbiasedInterruptTimePrecise = 0;
  QueryUnbiasedInterruptTimePrecise(&UnbiasedInterruptTimePrecise);
  try
  {
    v10 = 0;
    v58 = 0;
    v54 = 0;
    v11 = std::_Allocate<16,std::_Default_allocate_traits>(64);
    *(_QWORD *)v11 = v11;
    *(_QWORD *)(v11 + 8) = v11;
    *(_QWORD *)(v11 + 16) = v11;
    *(_WORD *)(v11 + 24) = 257;
    *(_QWORD *)&v54 = v11;
    v44 = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
    v12 = CreateConfigManagerFromSession(a2, &v44);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v45 = 0;
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
      PolicyRootNode = CNodeChangeSetBuilder::FindPolicyRootNode(v16, v44, a3, a4, &v45);
      v18 = PolicyRootNode;
      if ( PolicyRootNode >= 0 )
      {
        v46 = 0;
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
        if ( GetCspNodeFromUri(v44, v45, L"Nodes", &v46) >= 0 )
        {
          v48 = 0;
          v19 = v45;
          v20 = *(__int64 (__fastcall **)(struct IConfigNode *, unsigned __int16 **))(*(_QWORD *)v45 + 112LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v48,
            0);
          v21 = v20(v19, &v48);
          v22 = v21;
          if ( v21 >= 0 )
          {
            v49 = 0;
            v23 = v46;
            v24 = *(int (__fastcall **)(struct IConfigNode *, __int64 *))(*(_QWORD *)v46 + 192LL);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
            if ( v24(v23, &v49) >= 0 )
            {
              phProv = 0;
              if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000040) )
              {
                v26 = 0;
                while ( 1 )
                {
                  v47 = 0;
                  v55 = 0;
                  v27 = v49;
                  v28 = *(__int64 (__fastcall **)(__int64, __int64, struct IConfigNode **, int *))(*(_QWORD *)v49 + 24LL);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v47);
                  v29 = v28(v27, 1, &v47, &v55);
                  v30 = v29;
                  if ( v29 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x211,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                      (const char *)(unsigned int)v29,
                      (int)dwFlagsb);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v47);
                    __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
                    NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
                    return v30;
                  }
                  if ( !v47 || v55 != 1 )
                    break;
                  v58 = ++v10;
                  v56 = 0;
                  Str = 0;
                  VariantInit(&pvarg);
                  v57 = 10;
                  v62 = 0;
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppNodeCacheLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppNodeCacheLogging>::GetImpl'::`2'::impl) )
                    QueryUnbiasedInterruptTimePrecise(&v62);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &Str,
                    0);
                  v31 = CNodeChangeSetBuilder::ProcessCacheEntry(
                          v44,
                          v47,
                          v48,
                          phProv,
                          &v56,
                          &Str,
                          &pvarg,
                          (enum ConfigDataType *)&v57);
                  v32 = v31;
                  if ( v31 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x22F,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                      (const char *)(unsigned int)v31,
                      (int)dwFlagsb);
                    VariantClear(&pvarg);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v47);
                    __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
                    NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
                    return v32;
                  }
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppNodeCacheLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppNodeCacheLogging>::GetImpl'::`2'::impl)
                    && Str
                    && wcsstr(Str, L"EnterpriseModernAppManagement") )
                  {
                    v51 = 0;
                    QueryUnbiasedInterruptTimePrecise(&v51);
                    v9 += v51 - v62;
                    ++v26;
                  }
                  v52 = 0;
                  v33 = v47;
                  v34 = *(__int64 (__fastcall **)(struct IConfigNode *, unsigned __int64 *))(*(_QWORD *)v47 + 128LL);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &v52,
                    0);
                  v35 = v34(v33, &v52);
                  v36 = v35;
                  if ( v35 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x23F,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                      (const char *)(unsigned int)v35,
                      (int)dwFlagsb);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
                    VariantClear(&pvarg);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v47);
                    __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
                    NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
                    return v36;
                  }
                  v51 = v52;
                  p_pvarg = (VARIANTARG *)Str;
                  NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::NodeProcessingEvent<unsigned short *,unsigned short *>(
                    v68,
                    &p_pvarg,
                    &v51);
                  if ( v56 )
                  {
                    *a5 = 1;
                    std::wstring::wstring(v67, v52);
                    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                      &v54,
                      v66,
                      v67);
                    std::wstring::_Tidy_deallocate(v67);
                    LODWORD(v51) = v57;
                    v65 = Str;
                    v61 = v52;
                    p_pvarg = &pvarg;
                    v37 = *(_QWORD *)(a6 + 56);
                    if ( !v37 )
                      std::_Xbad_function_call();
                    dwFlagsb = &v51;
                    v38 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, wchar_t **, VARIANTARG **))(*(_QWORD *)v37 + 16LL))(
                            v37,
                            &v61,
                            &v65,
                            &p_pvarg);
                    v39 = v38;
                    if ( v38 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x248,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                        (const char *)(unsigned int)v38,
                        (int)&v51);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
                      VariantClear(&pvarg);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v47);
                      __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
                      NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
                      return v39;
                    }
                  }
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
                  VariantClear(&pvarg);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v47);
                }
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v47);
                wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v68);
                __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                v59 = 0;
                QueryUnbiasedInterruptTimePrecise(&v59);
                v59 -= UnbiasedInterruptTimePrecise;
                v61 = v59 / 0x989680;
                if ( v59 / 0x989680 >= 0x3C )
                {
                  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x8000) != 0 )
                    McTemplateU0qq_EventWriteTransfer(
                      MDM_ENTERPRISE_DIAGNOSTICS_Context,
                      NodeCacheEnumerationAlert,
                      (unsigned int)(v59 / 0x989680),
                      v10);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppNodeCacheLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppNodeCacheLogging>::GetImpl'::`2'::impl)
                    && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x8000) != 0 )
                  {
                    McTemplateU0qq_EventWriteTransfer(
                      MDM_ENTERPRISE_DIAGNOSTICS_Context,
                      NodeCacheAppAlert,
                      (unsigned int)(v9 / 0x989680),
                      v26);
                  }
                }
                NodeChangeSetBuilderProvider::NodeCount<unsigned long &>(&v58);
                NodeChangeSetBuilderProvider::NodeProcessingTime<unsigned __int64 &>(&v61);
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
                NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
                result = 0;
              }
              else
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x20A,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                              v25);
                __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
                NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
                result = LastError;
              }
            }
            else
            {
              wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v68);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
              NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
              result = 0;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1FD,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
              (const char *)(unsigned int)v21,
              dwFlagsa);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
            NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
            result = v22;
          }
        }
        else
        {
          wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v68);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
          NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
          result = 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
          (const char *)(unsigned int)PolicyRootNode,
          dwFlagsa);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
        NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
        result = v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
        (const char *)(unsigned int)v12,
        dwFlags);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v54);
      NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
      result = v13;
    }
  }
  catch ( ... )
  {
    LODWORD(v51) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x26F,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                     v14);
    NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity((NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity *)v68);
    return (unsigned int)v51;
  }
  return result;
}

```

## disassembly

```asm
0x18005ce1c  push    rbx
0x18005ce1e  push    rsi
0x18005ce1f  push    rdi
0x18005ce20  push    r12
0x18005ce22  push    r13
0x18005ce24  push    r14
0x18005ce26  push    r15
0x18005ce28  sub     rsp, 290h
0x18005ce2f  mov     rax, cs:__security_cookie
0x18005ce36  xor     rax, rsp
0x18005ce39  mov     [rsp+2C8h+var_48], rax
0x18005ce41  mov     r14, r9
0x18005ce44  mov     rdi, r8
0x18005ce47  mov     rbx, rdx
0x18005ce4a  mov     r12, [rsp+2C8h+arg_20]
0x18005ce52  mov     r13, [rsp+2C8h+arg_28]
0x18005ce5a  lea     rdx, aEnumeratecache; "EnumerateCacheEntriesActivity"
0x18005ce61  lea     rcx, [rsp+2C8h+var_198]; struct wil::details::IFailureCallback *
0x18005ce69  call    ??0?$ActivityBase@VNodeCacheProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005ce6e  lea     rax, ??_7EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@6B@; const NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::`vftable'
0x18005ce75  mov     [rsp+2C8h+var_198], rax
0x18005ce7d  lea     rcx, [rsp+2C8h+var_198]; this
0x18005ce85  call    ?StartActivity@EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@QEAAXXZ; NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::StartActivity(void)
0x18005ce8a  nop
0x18005ce8b  xor     r15d, r15d
0x18005ce8e  mov     [r12], r15d
0x18005ce92  mov     [rsp+2C8h+UnbiasedInterruptTimePrecise], r15
0x18005ce9a  lea     rcx, [rsp+2C8h+UnbiasedInterruptTimePrecise]; lpUnbiasedInterruptTimePrecise
0x18005cea2  call    cs:__imp_QueryUnbiasedInterruptTimePrecise
0x18005cea9  nop     dword ptr [rax+rax+00h]
0x18005ceae  mov     esi, r15d
0x18005ceb1  mov     [rsp+2C8h+var_21C], r15d
0x18005ceb9  xorps   xmm0, xmm0
0x18005cebc  movdqu  [rsp+2C8h+var_238], xmm0
0x18005cec5  lea     ecx, [r15+40h]
0x18005cec9  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005cece  mov     [rax], rax
0x18005ced1  mov     [rax+8], rax
0x18005ced5  mov     [rax+10h], rax
0x18005ced9  mov     word ptr [rax+18h], 101h
0x18005cedf  mov     qword ptr [rsp+2C8h+var_238], rax
0x18005cee7  mov     [rsp+2C8h+var_288], r15
0x18005ceec  lea     rcx, [rsp+2C8h+var_288]
0x18005cef1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cef6  lea     rdx, [rsp+2C8h+var_288]; struct IConfigManager2 **
0x18005cefb  mov     rcx, rbx; struct IConfigSession2 *
0x18005cefe  call    ?CreateConfigManagerFromSession@@YAJPEAUIConfigSession2@@PEAPEAUIConfigManager2@@@Z; CreateConfigManagerFromSession(IConfigSession2 *,IConfigManager2 * *)
0x18005cf03  mov     ebx, eax
0x18005cf05  test    eax, eax
0x18005cf07  jns     short loc_18005CF53
0x18005cf09  mov     rcx, [rsp+2C8h]; this
0x18005cf11  mov     r9d, eax; char *
0x18005cf14  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005cf1b  mov     edx, 1ECh; void *
0x18005cf20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cf25  nop
0x18005cf26  lea     rcx, [rsp+2C8h+var_288]
0x18005cf2b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cf30  nop
0x18005cf31  lea     rcx, [rsp+2C8h+var_238]
0x18005cf39  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18005cf3e  nop
0x18005cf3f  lea     rcx, [rsp+2C8h+var_198]; this
0x18005cf47  call    ??1EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@QEAA@XZ; NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity(void)
0x18005cf4c  mov     eax, ebx
0x18005cf4e  jmp     loc_18005D977
0x18005cf53  mov     [rsp+2C8h+var_280], r15
0x18005cf58  lea     rcx, [rsp+2C8h+var_280]
0x18005cf5d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cf62  lea     rax, [rsp+2C8h+var_280]
0x18005cf67  mov     qword ptr [rsp+2C8h+dwFlags], rax; int
0x18005cf6c  mov     r9, r14; unsigned __int16 *
0x18005cf6f  mov     r8, rdi; unsigned __int16 *
0x18005cf72  mov     rdx, [rsp+2C8h+var_288]; struct IConfigManager2 *
0x18005cf77  call    ?FindPolicyRootNode@CNodeChangeSetBuilder@@QEAAJPEAUIConfigManager2@@PEBG1PEAPEAUIConfigNode@@@Z; CNodeChangeSetBuilder::FindPolicyRootNode(IConfigManager2 *,ushort const *,ushort const *,IConfigNode * *)
0x18005cf7c  mov     ebx, eax
0x18005cf7e  test    eax, eax
0x18005cf80  jns     short loc_18005CFD7
0x18005cf82  mov     rcx, [rsp+2C8h]; this
0x18005cf8a  mov     r9d, eax; char *
0x18005cf8d  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005cf94  mov     edx, 1EFh; void *
0x18005cf99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cf9e  nop
0x18005cf9f  lea     rcx, [rsp+2C8h+var_280]
0x18005cfa4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cfa9  nop
0x18005cfaa  lea     rcx, [rsp+2C8h+var_288]
0x18005cfaf  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cfb4  nop
0x18005cfb5  lea     rcx, [rsp+2C8h+var_238]
0x18005cfbd  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18005cfc2  nop
0x18005cfc3  lea     rcx, [rsp+2C8h+var_198]; this
0x18005cfcb  call    ??1EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@QEAA@XZ; NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity(void)
0x18005cfd0  mov     eax, ebx
0x18005cfd2  jmp     loc_18005D977
0x18005cfd7  mov     [rsp+2C8h+var_278], r15
0x18005cfdc  lea     rcx, [rsp+2C8h+var_278]
0x18005cfe1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cfe6  lea     r9, [rsp+2C8h+var_278]; struct IConfigNode **
0x18005cfeb  lea     r8, ?c_szCacheEntries@CNodeChangeSetBuilder@@2QBGB; "Nodes"
0x18005cff2  mov     rdx, [rsp+2C8h+var_280]; struct IConfigNode *
0x18005cff7  mov     rcx, [rsp+2C8h+var_288]; struct IConfigManager2 *
0x18005cffc  call    ?GetCspNodeFromUri@@YAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGPEAPEAU2@@Z; GetCspNodeFromUri(IConfigManager2 *,IConfigNode *,ushort const *,IConfigNode * *)
0x18005d001  test    eax, eax
0x18005d003  jns     short loc_18005D056
0x18005d005  lea     rcx, [rsp+2C8h+var_198]
0x18005d00d  call    ?Stop@?$ActivityBase@VNodeCacheProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005d012  nop
0x18005d013  lea     rcx, [rsp+2C8h+var_278]
0x18005d018  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d01d  nop
0x18005d01e  lea     rcx, [rsp+2C8h+var_280]
0x18005d023  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d028  nop
0x18005d029  lea     rcx, [rsp+2C8h+var_288]
0x18005d02e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d033  nop
0x18005d034  lea     rcx, [rsp+2C8h+var_238]
0x18005d03c  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18005d041  nop
0x18005d042  lea     rcx, [rsp+2C8h+var_198]; this
0x18005d04a  call    ??1EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@QEAA@XZ; NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity(void)
0x18005d04f  xor     eax, eax
0x18005d051  jmp     loc_18005D977
0x18005d056  mov     [rsp+2C8h+var_268], r15
0x18005d05b  mov     rdi, [rsp+2C8h+var_280]
0x18005d060  mov     rax, [rdi]
0x18005d063  mov     rbx, [rax+70h]
0x18005d067  xor     edx, edx
0x18005d069  lea     rcx, [rsp+2C8h+var_268]
0x18005d06e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005d073  lea     rdx, [rsp+2C8h+var_268]
0x18005d078  mov     rcx, rdi
0x18005d07b  mov     rax, rbx
0x18005d07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d083  mov     ebx, eax
0x18005d085  test    eax, eax
0x18005d087  jns     short loc_18005D0F4
0x18005d089  mov     rcx, [rsp+2C8h]; this
0x18005d091  mov     r9d, eax; char *
0x18005d094  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005d09b  mov     edx, 1FDh; void *
0x18005d0a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d0a5  nop
0x18005d0a6  lea     rcx, [rsp+2C8h+var_268]
0x18005d0ab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d0b0  nop
0x18005d0b1  lea     rcx, [rsp+2C8h+var_278]
0x18005d0b6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d0bb  nop
0x18005d0bc  lea     rcx, [rsp+2C8h+var_280]
0x18005d0c1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d0c6  nop
0x18005d0c7  lea     rcx, [rsp+2C8h+var_288]
0x18005d0cc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d0d1  nop
0x18005d0d2  lea     rcx, [rsp+2C8h+var_238]
0x18005d0da  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18005d0df  nop
0x18005d0e0  lea     rcx, [rsp+2C8h+var_198]; this
0x18005d0e8  call    ??1EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@QEAA@XZ; NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity(void)
0x18005d0ed  mov     eax, ebx
0x18005d0ef  jmp     loc_18005D977
0x18005d0f4  mov     [rsp+2C8h+var_260], r15
0x18005d0f9  mov     rdi, [rsp+2C8h+var_278]
0x18005d0fe  mov     rax, [rdi]
0x18005d101  mov     rbx, [rax+0C0h]
0x18005d108  lea     rcx, [rsp+2C8h+var_260]
0x18005d10d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d112  lea     rdx, [rsp+2C8h+var_260]
0x18005d117  mov     rcx, rdi
0x18005d11a  mov     rax, rbx
0x18005d11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d122  test    eax, eax
0x18005d124  jns     short loc_18005D18D
0x18005d126  lea     rcx, [rsp+2C8h+var_198]
0x18005d12e  call    ?Stop@?$ActivityBase@VNodeCacheProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005d133  nop
0x18005d134  lea     rcx, [rsp+2C8h+var_260]
0x18005d139  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d13e  nop
0x18005d13f  lea     rcx, [rsp+2C8h+var_268]
0x18005d144  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d149  nop
0x18005d14a  lea     rcx, [rsp+2C8h+var_278]
0x18005d14f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d154  nop
0x18005d155  lea     rcx, [rsp+2C8h+var_280]
0x18005d15a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d15f  nop
0x18005d160  lea     rcx, [rsp+2C8h+var_288]
0x18005d165  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d16a  nop
0x18005d16b  lea     rcx, [rsp+2C8h+var_238]
0x18005d173  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18005d178  nop
0x18005d179  lea     rcx, [rsp+2C8h+var_198]; this
0x18005d181  call    ??1EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@QEAA@XZ; NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity(void)
0x18005d186  xor     eax, eax
0x18005d188  jmp     loc_18005D977
0x18005d18d  mov     [rsp+2C8h+phProv], r15
0x18005d195  mov     [rsp+2C8h+dwFlags], 0F0000040h; int
0x18005d19d  mov     r9d, 18h; dwProvType
0x18005d1a3  xor     r8d, r8d; szProvider
0x18005d1a6  xor     edx, edx; szContainer
0x18005d1a8  lea     rcx, [rsp+2C8h+phProv]; phProv
0x18005d1b0  call    cs:__imp_CryptAcquireContextW
0x18005d1b7  nop     dword ptr [rax+rax+00h]
0x18005d1bc  test    eax, eax
0x18005d1be  jz      loc_18005D8E7
0x18005d1c4  mov     r14d, r15d
0x18005d1c7  mov     [rsp+2C8h+var_270], 0
0x18005d1d0  mov     [rsp+2C8h+var_228], 0
0x18005d1db  mov     rdi, [rsp+2C8h+var_260]
0x18005d1e0  mov     rax, [rdi]
0x18005d1e3  mov     rbx, [rax+18h]
0x18005d1e7  lea     rcx, [rsp+2C8h+var_270]
0x18005d1ec  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d1f1  lea     r9, [rsp+2C8h+var_228]
0x18005d1f9  lea     r8, [rsp+2C8h+var_270]
0x18005d1fe  mov     edx, 1
0x18005d203  mov     rcx, rdi
0x18005d206  mov     rax, rbx
0x18005d209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d20e  mov     ebx, eax
0x18005d210  xor     edi, edi
0x18005d212  test    eax, eax
0x18005d214  jns     loc_18005D2A9
0x18005d21a  mov     rcx, [rsp+2C8h]; this
0x18005d222  mov     r9d, eax; char *
0x18005d225  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005d22c  mov     edx, 211h; void *
0x18005d231  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d236  nop
0x18005d237  lea     rcx, [rsp+2C8h+var_270]
0x18005d23c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d241  nop
0x18005d242  lea     rcx, [rsp+2C8h+phProv]
0x18005d24a  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005d24f  nop
0x18005d250  lea     rcx, [rsp+2C8h+var_260]
0x18005d255  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d25a  nop
0x18005d25b  lea     rcx, [rsp+2C8h+var_268]
0x18005d260  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d265  nop
0x18005d266  lea     rcx, [rsp+2C8h+var_278]
0x18005d26b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d270  nop
0x18005d271  lea     rcx, [rsp+2C8h+var_280]
0x18005d276  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d27b  nop
0x18005d27c  lea     rcx, [rsp+2C8h+var_288]
0x18005d281  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005d286  nop
0x18005d287  lea     rcx, [rsp+2C8h+var_238]
0x18005d28f  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18005d294  nop
0x18005d295  lea     rcx, [rsp+2C8h+var_198]; this
0x18005d29d  call    ??1EnumerateCacheEntriesActivity@NodeChangeSetBuilderProvider@@QEAA@XZ; NodeChangeSetBuilderProvider::EnumerateCacheEntriesActivity::~EnumerateCacheEntriesActivity(void)
0x18005d2a2  mov     eax, ebx
0x18005d2a4  jmp     loc_18005D977
0x18005d2a9  cmp     [rsp+2C8h+var_270], rdi
0x18005d2ae  jz      loc_18005D79A
0x18005d2b4  cmp     [rsp+2C8h+var_228], 1
0x18005d2bc  jnz     loc_18005D79A
0x18005d2c2  inc     esi
0x18005d2c4  mov     [rsp+2C8h+var_21C], esi
0x18005d2cb  mov     [rsp+2C8h+var_224], edi
0x18005d2d2  mov     [rsp+2C8h+Str], rdi
0x18005d2d7  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x18005d2df  call    cs:__imp_VariantInit
0x18005d2e6  nop     dword ptr [rax+rax+00h]
0x18005d2eb  nop
0x18005d2ec  mov     [rsp+2C8h+var_220], 0Ah
0x18005d2f7  mov     [rsp+2C8h+var_200], rdi
0x18005d2ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppNodeCacheLogging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppNodeCacheLogging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppNodeCacheLogging> `wil::Feature<__WilFeatureTraits_Feature_AppNodeCacheLogging>::GetImpl(void)'::`2'::impl
0x18005d306  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppNodeCacheLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppNodeCacheLogging>::__private_IsEnabled(void)
0x18005d30b  test    al, al
0x18005d30d  jz      short loc_18005D323
0x18005d30f  lea     rcx, [rsp+2C8h+var_200]; lpUnbiasedInterruptTimePrecise
0x18005d317  call    cs:__imp_QueryUnbiasedInterruptTimePrecise
0x18005d31e  nop     dword ptr [rax+rax+00h]
0x18005d323  xor     edx, edx
0x18005d325  lea     rcx, [rsp+2C8h+Str]
0x18005d32a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005d32f  lea     rax, [rsp+2C8h+var_220]
0x18005d337  mov     [rsp+2C8h+var_290], rax; enum ConfigDataType *
0x18005d33c  lea     rax, [rsp+2C8h+pvarg]
0x18005d344  mov     [rsp+2C8h+var_298], rax; struct tagVARIANT *
0x18005d349  lea     rax, [rsp+2C8h+Str]
0x18005d34e  mov     [rsp+2C8h+var_2A0], rax; unsigned __int16 **
0x18005d353  lea     rax, [rsp+2C8h+var_224]
0x18005d35b  mov     qword ptr [rsp+2C8h+dwFlags], rax; int
0x18005d360  mov     r9, [rsp+2C8h+phProv]; unsigned __int64
0x18005d368  mov     r8, [rsp+2C8h+var_268]; unsigned __int16 *
0x18005d36d  mov     rdx, [rsp+2C8h+var_270]; struct IConfigNode *
0x18005d372  mov     rcx, [rsp+2C8h+var_288]; struct IConfigManager2 *
  ... truncated ...
```
