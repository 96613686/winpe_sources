# sharedpackagecontainer::TryGetSharedPackageContainerInAppxAllUserStoreByFamilyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180067e48`
- end: `0x180068443`
- name: `?TryGetSharedPackageContainerInAppxAllUserStoreByFamilyName@sharedpackagecontainer@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `1531`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005120c`

## callees

- `0x1800053a0`
- `0x180011300`
- `0x180011820`
- `0x180011a64`
- `0x180013100`
- `0x1800148e8`
- `0x180014f4c`
- `0x180015d18`
- `0x18001748c`
- `0x18001ead0`
- `0x18001ec94`
- `0x18002b240`
- `0x180034460`
- `0x18005c0fc`
- `0x18005c5c0`
- `0x180066e00`
- `0x180067118`
- `0x1800671ec`
- `0x180067e48`
- `0x18006844c`
- `0x1800684ec`
- `0x1800686ec`
- `0x180068c70`
- `0x18006b41c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068331`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068331`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180068314`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180068314`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800682e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800682e9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068122`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800683c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800683c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067f60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067f60`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x180067fa9`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x180067fa9`
- `AppXAllUserStore!DeleteAllContainersFromContainerArray` at `0x180068383`
- `AppXAllUserStore!DeleteAllContainersFromContainerArray` at `0x180068383`

## string_xrefs

- `0x18006830d`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char *__fastcall sharedpackagecontainer::TryGetSharedPackageContainerInAppxAllUserStoreByFamilyName(
        char *a1,
        const unsigned __int16 *a2)
{
  char *v3; // rsi
  const unsigned __int16 *v4; // rbx
  sharedpackagecontainer *v5; // rcx
  unsigned int v6; // eax
  char v7; // r13
  unsigned int v8; // r15d
  __int64 v9; // rcx
  __int64 v10; // rdx
  _OWORD *v11; // rbx
  unsigned int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  const unsigned __int16 *v16; // rax
  __int64 v17; // r9
  const WCHAR *v18; // r8
  const WCHAR *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  BOOL v23; // r15d
  _DWORD *v24; // rdi
  __int64 v25; // r14
  char *v26; // rbx
  _DWORD *v27; // rbx
  struct _RTL_CRITICAL_SECTION *v28; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v37; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD *v38; // [rsp+60h] [rbp-A0h]
  void **v39; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v40[3]; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+88h] [rbp-78h]
  __int64 v42; // [rsp+90h] [rbp-70h]
  LPVOID v43; // [rsp+98h] [rbp-68h]
  char *v44; // [rsp+A0h] [rbp-60h]
  char v45[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v46; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v47; // [rsp+C8h] [rbp-38h]
  _OWORD v48[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v49; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v50; // [rsp+108h] [rbp+8h]
  __int64 v51; // [rsp+110h] [rbp+10h]
  _BYTE v52[40]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v53[42]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v3 = a1;
  pv = a1;
  v44 = a1;
  v33 = 1;
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v4 = *(const unsigned __int16 **)a2;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v53,
    "TryGetSharedPackageContainerFromAppxAllUserStore");
  v53[0] = &DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::`vftable';
  DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::StartActivity(
    (DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore *)v53,
    v4);
  v48[0] = 0;
  v48[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v48[0]) = 0;
  v37 = 0;
  v38 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::GetImpl'::`2'::impl)
    && !sharedpackagecontainer::IsSharedPackageFeatureBeingUsed(v5) )
  {
    std::wstring::wstring(v3, v48);
    std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(v3 + 32, &v37);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
    goto LABEL_66;
  }
  v34 = 0;
  v33 = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
  if ( v6 )
  {
    if ( v6 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\sharedpackagecontainerutility.cpp",
        (const char *)v6,
        phkResult);
    std::wstring::wstring(v3, v48);
    std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(v3 + 32, &v37);
    goto LABEL_64;
  }
  if ( (int)GetProvisionedSharedPackageContainersFromRegistryStore(hKey, &v34, &v33) < 0 )
    goto LABEL_63;
  v7 = 0;
  v8 = 0;
  v9 = v33;
  v10 = v34;
  if ( !v33 )
    goto LABEL_61;
  v11 = (_OWORD *)*((_QWORD *)&v37 + 1);
  do
  {
    v12 = 0;
    if ( !*(_DWORD *)(v10 + 24LL * v8 + 16) )
      goto LABEL_36;
    do
    {
      if ( v7 )
      {
        v13 = **(_QWORD **)(*(_QWORD *)(v10 + 24LL * v8 + 8) + 8LL * v12);
        v46 = 0;
        v47 = 0u;
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(v13 + 2 * v14) );
        std::wstring::_Construct<1,unsigned short const *>(&v46, v13, v14);
        if ( v11 == v38 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v37, v11, &v46);
          v11 = (_OWORD *)*((_QWORD *)&v37 + 1);
        }
        else
        {
          *v11 = v46;
          v11[1] = v47;
          *(_QWORD *)&v47 = 0;
          *((_QWORD *)&v47 + 1) = 7;
          LOWORD(v46) = 0;
          v11 += 2;
          *((_QWORD *)&v37 + 1) = v11;
        }
        std::wstring::~wstring(&v46);
LABEL_20:
        ++v12;
        goto LABEL_21;
      }
      v16 = a2;
      if ( *((_QWORD *)a2 + 3) > 7u )
        v16 = *(const unsigned __int16 **)a2;
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      v18 = a2;
      if ( *((_QWORD *)a2 + 3) > 7u )
        v18 = *(const WCHAR **)a2;
      v19 = **(const WCHAR ***)(*(_QWORD *)(v10 + 24LL * v8 + 8) + 8LL * v12);
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      if ( CompareStringOrdinal(v19, v20, v18, v17, 1) != 2 )
        goto LABEL_20;
      v7 = 1;
      v21 = *(_QWORD *)(v34 + 24LL * v8);
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
      std::wstring::_Construct<1,unsigned short const *>(&v49, v21, v22);
      std::wstring::operator=(v48, &v49);
      std::wstring::~wstring(&v49);
      v12 = 0;
LABEL_21:
      v10 = v34;
      v15 = *(unsigned int *)(v34 + 24LL * v8 + 16);
    }
    while ( v12 < (unsigned int)v15 );
    v3 = (char *)pv;
    if ( v7 )
    {
      v23 = v15 != (__int64)((__int64)v11 - v37) >> 5;
      pv = 0;
      tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(
        &pv,
        v45);
      v39 = &tip2::test_watcher<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::`vftable';
      v40[0] = 0;
      v40[1] = &v39;
      v40[2] = 0;
      v41 = 0;
      v42 = 0;
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v40);
      v43 = pv;
      if ( pv )
      {
        _InterlockedIncrement((volatile signed __int32 *)pv + 76);
        if ( pv )
          tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(pv);
      }
      v24 = v43;
      if ( v43 )
        _InterlockedIncrement((volatile signed __int32 *)v43 + 76);
      tip2::details::shared_data<1,0,0>::begin_update(v24 + 2);
      v24[66] = v23;
      tip2::details::shared_data<1,0,0>::end_update(v24 + 2);
      if ( v24 )
        tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v24);
      v25 = std::wstring::wstring(v52, a2);
      v26 = (char *)v43;
      if ( v43 )
        _InterlockedIncrement((volatile signed __int32 *)v43 + 76);
      tip2::details::shared_data<1,0,0>::begin_update(v26 + 8);
      std::wstring::operator=(v26 + 272, v25);
      if ( v26 )
      {
        tip2::details::shared_data<1,0,0>::end_update(v26 + 8);
        tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v26);
      }
      std::wstring::~wstring(v52);
      v27 = v43;
      v28 = (struct _RTL_CRITICAL_SECTION *)((char *)v43 + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)v43 + 5);
      v27[18] |= 0x300u;
      if ( *((_QWORD *)v27 + 30) )
        tip2::details::shared_data<1,0,0>::complete_helper(v27 + 2, 2);
      if ( v28 )
        LeaveCriticalSection(v28);
      ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
      if ( `TestControlReporting'::`2'::s_pfnTestControlReporting )
        goto LABEL_57;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestControlReporting");
      `TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_57:
        ((void (__fastcall *)(_QWORD))ProcAddress)(0);
      if ( v43 )
        tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v43);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
      v10 = v34;
      v9 = v33;
      break;
    }
    v9 = v33;
LABEL_36:
    ++v8;
  }
  while ( v8 < (unsigned int)v9 );
LABEL_61:
  if ( v10 )
    DeleteAllContainersFromContainerArray(v9, &v34);
LABEL_63:
  std::wstring::wstring(v3, v48);
  std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(v3 + 32, &v37);
LABEL_64:
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_66:
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v37);
  std::wstring::~wstring(v48);
  v53[0] = &DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::`vftable';
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v53);
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v53);
  return v3;
}

```

## disassembly

```asm
0x180067e48  mov     [rsp-8+arg_10], rbx
0x180067e4d  push    rbp
0x180067e4e  push    rsi
0x180067e4f  push    rdi
0x180067e50  push    r12
0x180067e52  push    r13
0x180067e54  push    r14
0x180067e56  push    r15
0x180067e58  lea     rbp, [rsp-1A0h]
0x180067e60  sub     rsp, 2A0h
0x180067e67  mov     rax, cs:__security_cookie
0x180067e6e  xor     rax, rsp
0x180067e71  mov     [rbp+1D0h+var_40], rax
0x180067e78  mov     r14, rdx
0x180067e7b  mov     rsi, rcx
0x180067e7e  mov     [rsp+2D0h+pv], rcx
0x180067e83  mov     [rbp+1D0h+var_230], rcx
0x180067e87  mov     [rsp+2D0h+var_2A0], 1
0x180067e8f  mov     rbx, rdx
0x180067e92  cmp     qword ptr [rdx+18h], 7
0x180067e97  jbe     short loc_180067E9C
0x180067e99  mov     rbx, [rdx]
0x180067e9c  lea     rdx, aTrygetsharedpa; "TryGetSharedPackageContainerFromAppxAll"...
0x180067ea3  lea     rcx, [rbp+1D0h+var_190]
0x180067ea7  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180067eac  lea     rdi, ??_7TryGetSharedPackageContainerFromAppxAllUserStore@DesktopAppXProvider@@6B@; const DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::`vftable'
0x180067eb3  mov     [rbp+1D0h+var_190], rdi
0x180067eb7  mov     rdx, rbx; unsigned __int16 *
0x180067eba  lea     rcx, [rbp+1D0h+var_190]; this
0x180067ebe  call    ?StartActivity@TryGetSharedPackageContainerFromAppxAllUserStore@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::StartActivity(ushort const *)
0x180067ec3  nop
0x180067ec4  xorps   xmm0, xmm0
0x180067ec7  movups  [rbp+1D0h+var_1F8], xmm0
0x180067ecb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180067ed3  movdqu  [rbp+1D0h+var_1E8], xmm1
0x180067ed8  xor     r12d, r12d
0x180067edb  mov     word ptr [rbp+1D0h+var_1F8], r12w
0x180067ee0  movdqu  [rsp+2D0h+var_280], xmm0
0x180067ee6  mov     [rsp+2D0h+var_270], r12
0x180067eeb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppXLaunchPerformanceCache@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppXLaunchPerformanceCache@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache> `wil::Feature<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::GetImpl(void)'::`2'::impl
0x180067ef2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppXLaunchPerformanceCache@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::__private_IsEnabled(void)
0x180067ef7  test    al, al
0x180067ef9  jz      short loc_180067F30
0x180067efb  call    ?IsSharedPackageFeatureBeingUsed@sharedpackagecontainer@@YA_NXZ; sharedpackagecontainer::IsSharedPackageFeatureBeingUsed(void)
0x180067f00  test    al, al
0x180067f02  jnz     short loc_180067F30
0x180067f04  lea     rdx, [rbp+1D0h+var_1F8]
0x180067f08  mov     rcx, rsi
0x180067f0b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180067f10  nop
0x180067f11  lea     rcx, [rsi+20h]
0x180067f15  lea     rdx, [rsp+2D0h+var_280]
0x180067f1a  call    ??0?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(std::vector<WriteVirtualization::RegistryExclusion> const &)
0x180067f1f  nop
0x180067f20  xor     edx, edx
0x180067f22  lea     rcx, [rbp+1D0h+var_190]
0x180067f26  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180067f2b  jmp     loc_1800683CE
0x180067f30  mov     [rsp+2D0h+var_298], r12
0x180067f35  mov     [rsp+2D0h+var_2A0], r12d
0x180067f3a  mov     [rsp+2D0h+hKey], r12
0x180067f3f  lea     rax, [rsp+2D0h+hKey]
0x180067f44  mov     qword ptr [rsp+2D0h+phkResult], rax; unsigned int
0x180067f49  mov     r9d, 20019h; samDesired
0x180067f4f  xor     r8d, r8d; ulOptions
0x180067f52  lea     rdx, aSoftware_1; "Software"
0x180067f59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180067f60  call    cs:__imp_RegOpenKeyExW
0x180067f67  nop     dword ptr [rax+rax+00h]
0x180067f6c  test    eax, eax
0x180067f6e  jz      short loc_180067F9A
0x180067f70  cmp     eax, 2
0x180067f73  jnz     loc_180068427
0x180067f79  lea     rdx, [rbp+1D0h+var_1F8]
0x180067f7d  mov     rcx, rsi
0x180067f80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180067f85  nop
0x180067f86  lea     rcx, [rsi+20h]
0x180067f8a  lea     rdx, [rsp+2D0h+var_280]
0x180067f8f  call    ??0?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(std::vector<WriteVirtualization::RegistryExclusion> const &)
0x180067f94  nop
0x180067f95  jmp     loc_1800683AB
0x180067f9a  lea     r8, [rsp+2D0h+var_2A0]
0x180067f9f  lea     rdx, [rsp+2D0h+var_298]
0x180067fa4  mov     rcx, [rsp+2D0h+hKey]
0x180067fa9  call    cs:__imp_GetProvisionedSharedPackageContainersFromRegistryStore
0x180067fb0  nop     dword ptr [rax+rax+00h]
0x180067fb5  test    eax, eax
0x180067fb7  jns     short loc_180067FDA
0x180067fb9  lea     rdx, [rbp+1D0h+var_1F8]
0x180067fbd  mov     rcx, rsi
0x180067fc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180067fc5  nop
0x180067fc6  lea     rcx, [rsi+20h]
0x180067fca  lea     rdx, [rsp+2D0h+var_280]
0x180067fcf  call    ??0?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(std::vector<WriteVirtualization::RegistryExclusion> const &)
0x180067fd4  nop
0x180067fd5  jmp     loc_1800683AB
0x180067fda  mov     r13b, r12b
0x180067fdd  mov     r15d, r12d
0x180067fe0  mov     ecx, [rsp+2D0h+var_2A0]
0x180067fe4  mov     rdx, [rsp+2D0h+var_298]
0x180067fe9  test    ecx, ecx
0x180067feb  jz      loc_180068379
0x180067ff1  mov     rbx, qword ptr [rsp+2D0h+var_280+8]
0x180067ff6  mov     edi, r12d
0x180067ff9  mov     eax, r15d
0x180067ffc  lea     r12, [rax+rax*2]
0x180068000  xor     r10d, r10d
0x180068003  cmp     [rdx+r12*8+10h], r10d
0x180068008  jbe     loc_18006818C
0x18006800e  mov     esi, r15d
0x180068011  test    r13b, r13b
0x180068014  jz      loc_1800680D6
0x18006801a  lea     rax, [rsi+rsi*2]
0x18006801e  mov     ecx, edi
0x180068020  mov     rax, [rdx+rax*8+8]
0x180068025  mov     rcx, [rax+rcx*8]
0x180068029  mov     rdx, [rcx]
0x18006802c  xorps   xmm0, xmm0
0x18006802f  movups  [rbp+1D0h+var_218], xmm0
0x180068033  mov     qword ptr [rbp+1D0h+var_208], r10
0x180068037  mov     qword ptr [rbp+1D0h+var_208+8], r10
0x18006803b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006803f  inc     r8
0x180068042  cmp     [rdx+r8*2], r10w
0x180068047  jnz     short loc_18006803F
0x180068049  lea     rcx, [rbp+1D0h+var_218]
0x18006804d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180068052  nop
0x180068053  cmp     rbx, [rsp+2D0h+var_270]
0x180068058  jz      short loc_180068086
0x18006805a  xor     eax, eax
0x18006805c  movups  xmm0, [rbp+1D0h+var_218]
0x180068060  movups  xmmword ptr [rbx], xmm0
0x180068063  movups  xmm1, [rbp+1D0h+var_208]
0x180068067  movups  xmmword ptr [rbx+10h], xmm1
0x18006806b  mov     qword ptr [rbp+1D0h+var_208], rax
0x18006806f  mov     qword ptr [rbp+1D0h+var_208+8], 7
0x180068077  mov     word ptr [rbp+1D0h+var_218], ax
0x18006807b  add     rbx, 20h ; ' '
0x18006807f  mov     qword ptr [rsp+2D0h+var_280+8], rbx
0x180068084  jmp     short loc_18006809C
0x180068086  lea     r8, [rbp+1D0h+var_218]
0x18006808a  mov     rdx, rbx
0x18006808d  lea     rcx, [rsp+2D0h+var_280]
0x180068092  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180068097  mov     rbx, qword ptr [rsp+2D0h+var_280+8]
0x18006809c  lea     rcx, [rbp+1D0h+var_218]; void *
0x1800680a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800680a5  inc     edi
0x1800680a7  xor     r10d, r10d
0x1800680aa  mov     rdx, [rsp+2D0h+var_298]
0x1800680af  mov     eax, [rdx+r12*8+10h]
0x1800680b4  cmp     edi, eax
0x1800680b6  jb      loc_180068011
0x1800680bc  mov     rsi, [rsp+2D0h+pv]
0x1800680c1  xor     r12d, r12d
0x1800680c4  test    r13b, r13b
0x1800680c7  jnz     loc_1800681A0
0x1800680cd  mov     ecx, [rsp+2D0h+var_2A0]
0x1800680d1  jmp     loc_18006818F
0x1800680d6  mov     rax, r14
0x1800680d9  cmp     qword ptr [r14+18h], 7
0x1800680de  jbe     short loc_1800680E3
0x1800680e0  mov     rax, [r14]
0x1800680e3  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800680e7  inc     r9; cchCount2
0x1800680ea  cmp     [rax+r9*2], r10w
0x1800680ef  jnz     short loc_1800680E7
0x1800680f1  mov     r8, r14
0x1800680f4  cmp     qword ptr [r14+18h], 7
0x1800680f9  jbe     short loc_1800680FE
0x1800680fb  mov     r8, [r14]; lpString2
0x1800680fe  mov     ecx, edi
0x180068100  mov     rax, [rdx+r12*8+8]
0x180068105  mov     rcx, [rax+rcx*8]
0x180068109  mov     rcx, [rcx]; lpString1
0x18006810c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180068110  inc     rdx; cchCount1
0x180068113  cmp     [rcx+rdx*2], r10w
0x180068118  jnz     short loc_180068110
0x18006811a  mov     [rsp+2D0h+phkResult], 1; bIgnoreCase
0x180068122  call    cs:__imp_CompareStringOrdinal
0x180068129  nop     dword ptr [rax+rax+00h]
0x18006812e  cmp     eax, 2
0x180068131  jnz     loc_1800680A5
0x180068137  mov     r13b, 1
0x18006813a  mov     rax, [rsp+2D0h+var_298]
0x18006813f  mov     rdx, [rax+r12*8]
0x180068143  xorps   xmm0, xmm0
0x180068146  movups  [rbp+1D0h+var_1D8], xmm0
0x18006814a  xor     eax, eax
0x18006814c  mov     [rbp+1D0h+var_1C8], rax
0x180068150  mov     [rbp+1D0h+var_1C0], rax
0x180068154  or      r8, 0FFFFFFFFFFFFFFFFh
0x180068158  inc     r8
0x18006815b  cmp     [rdx+r8*2], ax
0x180068160  jnz     short loc_180068158
0x180068162  lea     rcx, [rbp+1D0h+var_1D8]
0x180068166  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006816b  lea     rdx, [rbp+1D0h+var_1D8]
0x18006816f  lea     rcx, [rbp+1D0h+var_1F8]
0x180068173  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180068178  lea     rcx, [rbp+1D0h+var_1D8]; void *
0x18006817c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180068181  xor     r10d, r10d
0x180068184  mov     edi, r10d
0x180068187  jmp     loc_1800680AA
0x18006818c  xor     r12d, r12d
0x18006818f  inc     r15d
0x180068192  cmp     r15d, ecx
0x180068195  jb      loc_180067FF6
0x18006819b  jmp     loc_180068372
0x1800681a0  sub     rbx, qword ptr [rsp+2D0h+var_280]
0x1800681a5  sar     rbx, 5
0x1800681a9  mov     r15d, r12d
0x1800681ac  cmp     rax, rbx
0x1800681af  setnz   r15b
0x1800681b3  mov     [rsp+2D0h+pv], r12
0x1800681b8  lea     rdx, [rbp+1D0h+var_228]
0x1800681bc  lea     rcx, [rsp+2D0h+pv]
0x1800681c1  call    ?start@?$tip_test@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(void)
0x1800681c6  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::`vftable'
0x1800681cd  mov     [rsp+2D0h+var_268], rax
0x1800681d2  mov     [rsp+2D0h+var_260], r12
0x1800681d7  lea     rax, [rsp+2D0h+var_268]
0x1800681dc  mov     [rsp+2D0h+var_258], rax
0x1800681e1  mov     [rbp+1D0h+var_250], r12
0x1800681e5  mov     [rbp+1D0h+var_248], r12d
0x1800681e9  mov     [rbp+1D0h+var_240], r12
0x1800681ed  lea     rcx, [rsp+2D0h+var_260]; this
0x1800681f2  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800681f7  nop
0x1800681f8  mov     rcx, [rsp+2D0h+pv]
0x1800681fd  mov     [rbp+1D0h+var_238], rcx
0x180068201  test    rcx, rcx
0x180068204  jz      short loc_18006821D
0x180068206  lock inc dword ptr [rcx+130h]
0x18006820d  mov     rcx, [rsp+2D0h+pv]; pv
0x180068212  test    rcx, rcx
0x180068215  jz      short loc_18006821D
0x180068217  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x18006821c  nop
0x18006821d  mov     rdi, [rbp+1D0h+var_238]
0x180068221  test    rdi, rdi
0x180068224  jz      short loc_18006822D
0x180068226  lock inc dword ptr [rdi+130h]
0x18006822d  lea     rcx, [rdi+8]
0x180068231  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180068236  mov     [rdi+108h], r15d
0x18006823d  lea     rcx, [rdi+8]
0x180068241  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x180068246  test    rdi, rdi
0x180068249  jz      short loc_180068253
0x18006824b  mov     rcx, rdi; pv
0x18006824e  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x180068253  mov     rdx, r14
0x180068256  lea     rcx, [rbp+1D0h+var_1B8]
0x18006825a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006825f  mov     r14, rax
0x180068262  mov     rbx, [rbp+1D0h+var_238]
0x180068266  test    rbx, rbx
0x180068269  jz      short loc_180068272
0x18006826b  lock inc dword ptr [rbx+130h]
0x180068272  lea     rcx, [rbx+8]
0x180068276  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18006827b  lea     rcx, [rbx+110h]
0x180068282  mov     rdx, r14
0x180068285  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006828a  test    rbx, rbx
0x18006828d  jz      short loc_1800682A0
0x18006828f  lea     rcx, [rbx+8]
0x180068293  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x180068298  mov     rcx, rbx; pv
0x18006829b  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x1800682a0  lea     rcx, [rbp+1D0h+var_1B8]; void *
0x1800682a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800682a9  mov     rbx, [rbp+1D0h+var_238]
0x1800682ad  lea     rdi, [rbx+0C8h]
0x1800682b4  mov     rcx, rdi; lpCriticalSection
0x1800682b7  call    cs:__imp_EnterCriticalSection
0x1800682be  nop     dword ptr [rax+rax+00h]
0x1800682c3  or      dword ptr [rbx+48h], 300h
0x1800682ca  cmp     [rbx+0F0h], r12
0x1800682d1  jz      short loc_1800682E1
0x1800682d3  mov     edx, 2
0x1800682d8  lea     rcx, [rbx+8]
0x1800682dc  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x1800682e1  test    rdi, rdi
0x1800682e4  jz      short loc_1800682F5
0x1800682e6  mov     rcx, rdi; lpCriticalSection
0x1800682e9  call    cs:__imp_LeaveCriticalSection
0x1800682f0  nop     dword ptr [rax+rax+00h]
0x1800682f5  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x1800682fc  test    rax, rax
0x1800682ff  jnz     short loc_180068349
0x180068301  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180068308  test    rax, rax
0x18006830b  jnz     short loc_180068327
  ... truncated ...
```
