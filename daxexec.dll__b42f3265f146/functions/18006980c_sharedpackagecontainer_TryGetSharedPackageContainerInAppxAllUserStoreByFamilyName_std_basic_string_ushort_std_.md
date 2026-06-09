# sharedpackagecontainer::TryGetSharedPackageContainerInAppxAllUserStoreByFamilyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18006980c`
- end: `0x180069de6`
- name: `?TryGetSharedPackageContainerInAppxAllUserStoreByFamilyName@sharedpackagecontainer@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `1498`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180052d0c`

## callees

- `0x180004f70`
- `0x180012fb8`
- `0x180013510`
- `0x1800136dc`
- `0x180014e74`
- `0x1800164f8`
- `0x180016b98`
- `0x1800190e0`
- `0x18001f624`
- `0x18001f808`
- `0x180020140`
- `0x18002bab4`
- `0x1800360e0`
- `0x18005db00`
- `0x18005de64`
- `0x1800688c0`
- `0x180068b50`
- `0x180068c2c`
- `0x18006980c`
- `0x180069dec`
- `0x180069e8c`
- `0x18006a114`
- `0x18006a728`
- `0x18006cd90`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069caa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069caa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069cc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069cc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069c7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069c7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069c4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069c4d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180069ad1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180069ad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069926`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069926`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d5f`
- `AppXAllUserStore!DeleteAllContainersFromContainerArray` at `0x180069d21`
- `AppXAllUserStore!DeleteAllContainersFromContainerArray` at `0x180069d21`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x18006996f`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x18006996f`

## string_xrefs

- `0x180069ca3`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall sharedpackagecontainer::TryGetSharedPackageContainerInAppxAllUserStoreByFamilyName(
        __int64 a1,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rbx
  __m128i si128; // xmm6
  sharedpackagecontainer *v6; // rcx
  unsigned int v7; // eax
  char v8; // r12
  unsigned int v9; // r14d
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  HKEY v15; // rdx
  __int64 v16; // rax
  const unsigned __int16 *v17; // rax
  __int64 v18; // r9
  const WCHAR *v19; // r8
  const WCHAR *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  BOOL v24; // r15d
  volatile signed __int32 *v25; // rbx
  __int64 v26; // r14
  char *v27; // rbx
  _DWORD *v28; // rbx
  struct _RTL_CRITICAL_SECTION *v29; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned int phkResult; // [rsp+28h] [rbp-E0h]
  __int64 v37; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  HKEY v41; // [rsp+60h] [rbp-A8h]
  LPVOID pv[2]; // [rsp+68h] [rbp-A0h] BYREF
  void **v43; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v44[3]; // [rsp+80h] [rbp-88h] BYREF
  int v45; // [rsp+98h] [rbp-70h]
  __int64 v46; // [rsp+A0h] [rbp-68h]
  char v47; // [rsp+A8h] [rbp-60h]
  LPVOID v48; // [rsp+B0h] [rbp-58h]
  __int64 v49; // [rsp+B8h] [rbp-50h]
  __int128 v50; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v51; // [rsp+D0h] [rbp-38h]
  _OWORD v52[2]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v53[42]; // [rsp+108h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B0h] [rbp+1A8h]

  v49 = a1;
  LODWORD(v37) = 1;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const unsigned __int16 **)a2;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v53,
    "TryGetSharedPackageContainerFromAppxAllUserStore");
  v53[0] = &DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::`vftable';
  DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::StartActivity(
    (DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore *)v53,
    v4);
  v52[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v52[1] = si128;
  LOWORD(v52[0]) = 0;
  *(_OWORD *)hKey_8 = 0;
  v41 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::GetImpl'::`2'::impl)
    && !sharedpackagecontainer::IsSharedPackageFeatureBeingUsed(v6) )
  {
    std::wstring::wstring(a1, v52);
    std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(a1 + 32, hKey_8);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
    goto LABEL_69;
  }
  v38 = 0;
  LODWORD(v37) = 0;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
  if ( v7 )
  {
    if ( v7 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\sharedpackagecontainerutility.cpp",
        (const char *)v7,
        phkResult);
    std::wstring::wstring(a1, v52);
    std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(a1 + 32, hKey_8);
    goto LABEL_67;
  }
  if ( (int)GetProvisionedSharedPackageContainersFromRegistryStore(hKey, &v38, &v37) < 0 )
    goto LABEL_66;
  v8 = 0;
  v9 = 0;
  v10 = (unsigned int)v37;
  v11 = v38;
  if ( !(_DWORD)v37 )
    goto LABEL_64;
  do
  {
    v12 = 0;
    if ( !*(_DWORD *)(v11 + 24LL * v9 + 16) )
      goto LABEL_24;
    do
    {
      if ( v8 )
      {
        v13 = **(_QWORD **)(*(_QWORD *)(v11 + 24LL * v9 + 8) + 8LL * v12);
        v50 = 0;
        v51 = 0;
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(v13 + 2 * v14) );
        std::wstring::_Construct<1,unsigned short const *>(&v50, v13, v14);
        v15 = hKey_8[1];
        if ( hKey_8[1] == v41 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(hKey_8, hKey_8[1], &v50);
        }
        else
        {
          *(_OWORD *)hKey_8[1] = v50;
          *((__m128i *)v15 + 1) = v51;
          v51 = si128;
          LOWORD(v50) = 0;
          hKey_8[1] += 8;
        }
        std::wstring::~wstring(&v50);
LABEL_20:
        ++v12;
        goto LABEL_21;
      }
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v17 = a2;
      else
        v17 = *(const unsigned __int16 **)a2;
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v19 = a2;
      else
        v19 = *(const WCHAR **)a2;
      v20 = **(const WCHAR ***)(*(_QWORD *)(v11 + 24LL * v9 + 8) + 8LL * v12);
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      if ( CompareStringOrdinal(v20, v21, v19, v18, 1) != 2 )
        goto LABEL_20;
      v8 = 1;
      v22 = *(_QWORD *)(v38 + 24LL * v9);
      v50 = 0;
      v51 = 0;
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(v22 + 2 * v23) );
      std::wstring::_Construct<1,unsigned short const *>(&v50, v22, v23);
      std::wstring::operator=(v52, &v50);
      std::wstring::~wstring(&v50);
      v12 = 0;
LABEL_21:
      v11 = v38;
      v16 = *(unsigned int *)(v38 + 24LL * v9 + 16);
    }
    while ( v12 < (unsigned int)v16 );
    if ( v8 )
    {
      v24 = v16 != ((char *)hKey_8[1] - (char *)hKey_8[0]) >> 5;
      pv[0] = 0;
      tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(
        pv,
        &v50);
      v43 = &tip2::test_watcher<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::`vftable';
      v44[0] = 0;
      v44[1] = &v43;
      v44[2] = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v44);
      v25 = (volatile signed __int32 *)pv[0];
      v48 = pv[0];
      if ( pv[0] )
      {
        _InterlockedIncrement((volatile signed __int32 *)pv[0] + 78);
        tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release((LPVOID)v25);
        v25 = (volatile signed __int32 *)v48;
      }
      if ( v25 )
        _InterlockedIncrement(v25 + 78);
      tip2::details::shared_data<1,0,0>::begin_update(v25 + 2);
      *((_DWORD *)v25 + 68) = v24;
      if ( v25 )
      {
        tip2::details::shared_data<1,0,0>::end_update(v25 + 2);
        tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release((LPVOID)v25);
      }
      v26 = std::wstring::wstring(&v50, a2);
      v27 = (char *)v48;
      if ( v48 )
        _InterlockedIncrement((volatile signed __int32 *)v48 + 78);
      tip2::details::shared_data<1,0,0>::begin_update(v27 + 8);
      std::wstring::operator=(v27 + 280, v26);
      if ( v27 )
      {
        tip2::details::shared_data<1,0,0>::end_update(v27 + 8);
        tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v27);
      }
      std::wstring::~wstring(&v50);
      v28 = v48;
      v29 = (struct _RTL_CRITICAL_SECTION *)((char *)v48 + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)v48 + 5);
      v28[18] |= 0x300u;
      if ( *((_QWORD *)v28 + 31) )
        tip2::details::shared_data<1,0,0>::complete_helper(v28 + 2, 2);
      if ( v29 )
        LeaveCriticalSection(v29);
      ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
      if ( `TestControlReporting'::`2'::s_pfnTestControlReporting )
        goto LABEL_58;
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestControlReporting");
      `TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_58:
        ((void (__fastcall *)(_QWORD))ProcAddress)(0);
      if ( v48 )
        tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v48);
      if ( v45 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v44);
      v11 = v38;
      v10 = (unsigned int)v37;
      break;
    }
    v10 = (unsigned int)v37;
LABEL_24:
    ++v9;
  }
  while ( v9 < (unsigned int)v10 );
LABEL_64:
  if ( v11 )
    DeleteAllContainersFromContainerArray(v10, &v38);
LABEL_66:
  std::wstring::wstring(a1, v52);
  std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(a1 + 32, hKey_8);
LABEL_67:
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_69:
  std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(hKey_8);
  std::wstring::~wstring(v52);
  v53[0] = &DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::`vftable';
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v53, v32, v33, v34);
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v53);
  return a1;
}

```

## disassembly

```asm
0x18006980c  mov     rax, rsp
0x18006980f  mov     [rax+18h], rbx
0x180069813  push    rbp
0x180069814  push    rsi
0x180069815  push    rdi
0x180069816  push    r12
0x180069818  push    r13
0x18006981a  push    r14
0x18006981c  push    r15
0x18006981e  lea     rbp, [rax-1A8h]
0x180069825  sub     rsp, 270h
0x18006982c  movaps  xmmword ptr [rax-48h], xmm6
0x180069830  mov     rax, cs:__security_cookie
0x180069837  xor     rax, rsp
0x18006983a  mov     [rbp+1A0h+var_50], rax
0x180069841  mov     rsi, rdx
0x180069844  mov     rdi, rcx
0x180069847  mov     [rbp+1A0h+var_1F0], rcx
0x18006984b  mov     dword ptr [rsp+2A0h+var_270], 1
0x180069853  cmp     qword ptr [rdx+18h], 7
0x180069858  jbe     short loc_18006985F
0x18006985a  mov     rbx, [rdx]
0x18006985d  jmp     short loc_180069862
0x18006985f  mov     rbx, rsi
0x180069862  lea     rdx, aTrygetsharedpa; "TryGetSharedPackageContainerFromAppxAll"...
0x180069869  lea     rcx, [rbp+1A0h+var_1A0]
0x18006986d  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180069872  lea     r15, ??_7TryGetSharedPackageContainerFromAppxAllUserStore@DesktopAppXProvider@@6B@; const DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::`vftable'
0x180069879  mov     [rbp+1A0h+var_1A0], r15
0x18006987d  mov     rdx, rbx; unsigned __int16 *
0x180069880  lea     rcx, [rbp+1A0h+var_1A0]; this
0x180069884  call    ?StartActivity@TryGetSharedPackageContainerFromAppxAllUserStore@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::TryGetSharedPackageContainerFromAppxAllUserStore::StartActivity(ushort const *)
0x180069889  nop
0x18006988a  xorps   xmm0, xmm0
0x18006988d  movups  [rbp+1A0h+var_1C8], xmm0
0x180069891  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180069899  movdqu  [rbp+1A0h+var_1B8], xmm6
0x18006989e  xor     r13d, r13d
0x1800698a1  mov     word ptr [rbp+1A0h+var_1C8], r13w
0x1800698a6  movdqu  xmmword ptr [rsp+2A0h+hKey+8], xmm0
0x1800698ac  mov     [rsp+2A0h+var_248], r13
0x1800698b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppXLaunchPerformanceCache@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppXLaunchPerformanceCache@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache> `wil::Feature<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::GetImpl(void)'::`2'::impl
0x1800698b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppXLaunchPerformanceCache@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppXLaunchPerformanceCache>::__private_IsEnabled(void)
0x1800698bd  test    al, al
0x1800698bf  jz      short loc_1800698F6
0x1800698c1  call    ?IsSharedPackageFeatureBeingUsed@sharedpackagecontainer@@YA_NXZ; sharedpackagecontainer::IsSharedPackageFeatureBeingUsed(void)
0x1800698c6  test    al, al
0x1800698c8  jnz     short loc_1800698F6
0x1800698ca  lea     rdx, [rbp+1A0h+var_1C8]
0x1800698ce  mov     rcx, rdi
0x1800698d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800698d6  nop
0x1800698d7  lea     rcx, [rdi+20h]
0x1800698db  lea     rdx, [rsp+2A0h+hKey+8]
0x1800698e0  call    ??0?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(std::vector<WriteVirtualization::RegistryExclusion> const &)
0x1800698e5  nop
0x1800698e6  xor     edx, edx
0x1800698e8  lea     rcx, [rbp+1A0h+var_1A0]
0x1800698ec  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800698f1  jmp     loc_180069D6C
0x1800698f6  mov     [rsp+2A0h+var_268], r13
0x1800698fb  mov     dword ptr [rsp+2A0h+var_270], r13d
0x180069900  mov     [rsp+2A0h+hKey], r13
0x180069905  lea     rax, [rsp+2A0h+hKey]
0x18006990a  mov     qword ptr [rsp+2A0h+phkResult], rax; unsigned int
0x18006990f  mov     r9d, 20019h; samDesired
0x180069915  xor     r8d, r8d; ulOptions
0x180069918  lea     rdx, aSoftware_1; "Software"
0x18006991f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180069926  call    cs:__imp_RegOpenKeyExW
0x18006992d  nop     dword ptr [rax+rax+00h]
0x180069932  test    eax, eax
0x180069934  jz      short loc_180069960
0x180069936  cmp     eax, 2
0x180069939  jnz     loc_180069DCA
0x18006993f  lea     rdx, [rbp+1A0h+var_1C8]
0x180069943  mov     rcx, rdi
0x180069946  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006994b  nop
0x18006994c  lea     rcx, [rdi+20h]
0x180069950  lea     rdx, [rsp+2A0h+hKey+8]
0x180069955  call    ??0?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(std::vector<WriteVirtualization::RegistryExclusion> const &)
0x18006995a  nop
0x18006995b  jmp     loc_180069D49
0x180069960  lea     r8, [rsp+2A0h+var_270]
0x180069965  lea     rdx, [rsp+2A0h+var_268]
0x18006996a  mov     rcx, [rsp+2A0h+hKey]
0x18006996f  call    cs:__imp_GetProvisionedSharedPackageContainersFromRegistryStore
0x180069976  nop     dword ptr [rax+rax+00h]
0x18006997b  test    eax, eax
0x18006997d  jns     short loc_1800699A0
0x18006997f  lea     rdx, [rbp+1A0h+var_1C8]
0x180069983  mov     rcx, rdi
0x180069986  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006998b  nop
0x18006998c  lea     rcx, [rdi+20h]
0x180069990  lea     rdx, [rsp+2A0h+hKey+8]
0x180069995  call    ??0?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<WriteVirtualization::RegistryExclusion>::vector<WriteVirtualization::RegistryExclusion>(std::vector<WriteVirtualization::RegistryExclusion> const &)
0x18006999a  nop
0x18006999b  jmp     loc_180069D49
0x1800699a0  mov     r12b, r13b
0x1800699a3  mov     r14d, r13d
0x1800699a6  mov     ecx, dword ptr [rsp+2A0h+var_270]
0x1800699aa  mov     rdx, [rsp+2A0h+var_268]
0x1800699af  test    ecx, ecx
0x1800699b1  jz      loc_180069D17
0x1800699b7  mov     ebx, r13d
0x1800699ba  mov     eax, r14d
0x1800699bd  lea     r15, [rax+rax*2]
0x1800699c1  cmp     [rdx+r15*8+10h], r13d
0x1800699c6  jbe     loc_180069A70
0x1800699cc  test    r12b, r12b
0x1800699cf  jz      loc_180069A81
0x1800699d5  mov     ecx, ebx
0x1800699d7  mov     rax, [rdx+r15*8+8]
0x1800699dc  mov     rcx, [rax+rcx*8]
0x1800699e0  mov     rdx, [rcx]
0x1800699e3  xorps   xmm0, xmm0
0x1800699e6  movups  [rbp+1A0h+var_1E8], xmm0
0x1800699ea  xorps   xmm1, xmm1
0x1800699ed  movdqu  [rbp+1A0h+var_1D8], xmm1
0x1800699f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800699f6  inc     r8
0x1800699f9  cmp     [rdx+r8*2], r13w
0x1800699fe  jnz     short loc_1800699F6
0x180069a00  lea     rcx, [rbp+1A0h+var_1E8]
0x180069a04  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180069a09  nop
0x180069a0a  mov     rdx, [rsp+2A0h+var_250]
0x180069a0f  cmp     rdx, [rsp+2A0h+var_248]
0x180069a14  jz      short loc_180069A37
0x180069a16  movups  xmm0, [rbp+1A0h+var_1E8]
0x180069a1a  movups  xmmword ptr [rdx], xmm0
0x180069a1d  movups  xmm1, [rbp+1A0h+var_1D8]
0x180069a21  movups  xmmword ptr [rdx+10h], xmm1
0x180069a25  movdqu  [rbp+1A0h+var_1D8], xmm6
0x180069a2a  mov     word ptr [rbp+1A0h+var_1E8], r13w
0x180069a2f  add     [rsp+2A0h+var_250], 20h ; ' '
0x180069a35  jmp     short loc_180069A46
0x180069a37  lea     r8, [rbp+1A0h+var_1E8]
0x180069a3b  lea     rcx, [rsp+2A0h+hKey+8]
0x180069a40  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180069a45  nop
0x180069a46  lea     rcx, [rbp+1A0h+var_1E8]; void *
0x180069a4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069a4f  inc     ebx
0x180069a51  mov     rdx, [rsp+2A0h+var_268]
0x180069a56  mov     eax, [rdx+r15*8+10h]
0x180069a5b  cmp     ebx, eax
0x180069a5d  jb      loc_1800699CC
0x180069a63  test    r12b, r12b
0x180069a66  jnz     loc_180069B36
0x180069a6c  mov     ecx, dword ptr [rsp+2A0h+var_270]
0x180069a70  inc     r14d
0x180069a73  cmp     r14d, ecx
0x180069a76  jb      loc_1800699B7
0x180069a7c  jmp     loc_180069D10
0x180069a81  cmp     qword ptr [rsi+18h], 7
0x180069a86  jbe     short loc_180069A8D
0x180069a88  mov     rax, [rsi]
0x180069a8b  jmp     short loc_180069A90
0x180069a8d  mov     rax, rsi
0x180069a90  or      r9, 0FFFFFFFFFFFFFFFFh
0x180069a94  inc     r9; cchCount2
0x180069a97  cmp     [rax+r9*2], r13w
0x180069a9c  jnz     short loc_180069A94
0x180069a9e  cmp     qword ptr [rsi+18h], 7
0x180069aa3  jbe     short loc_180069AAA
0x180069aa5  mov     r8, [rsi]
0x180069aa8  jmp     short loc_180069AAD
0x180069aaa  mov     r8, rsi; lpString2
0x180069aad  mov     ecx, ebx
0x180069aaf  mov     rax, [rdx+r15*8+8]
0x180069ab4  mov     rcx, [rax+rcx*8]
0x180069ab8  mov     rcx, [rcx]; lpString1
0x180069abb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180069abf  inc     rdx; cchCount1
0x180069ac2  cmp     [rcx+rdx*2], r13w
0x180069ac7  jnz     short loc_180069ABF
0x180069ac9  mov     [rsp+2A0h+phkResult], 1; bIgnoreCase
0x180069ad1  call    cs:__imp_CompareStringOrdinal
0x180069ad8  nop     dword ptr [rax+rax+00h]
0x180069add  cmp     eax, 2
0x180069ae0  jnz     loc_180069A4F
0x180069ae6  mov     r12b, 1
0x180069ae9  mov     rax, [rsp+2A0h+var_268]
0x180069aee  mov     rdx, [rax+r15*8]
0x180069af2  xorps   xmm0, xmm0
0x180069af5  movups  [rbp+1A0h+var_1E8], xmm0
0x180069af9  xorps   xmm1, xmm1
0x180069afc  movdqu  [rbp+1A0h+var_1D8], xmm1
0x180069b01  or      r8, 0FFFFFFFFFFFFFFFFh
0x180069b05  inc     r8
0x180069b08  cmp     [rdx+r8*2], r13w
0x180069b0d  jnz     short loc_180069B05
0x180069b0f  lea     rcx, [rbp+1A0h+var_1E8]
0x180069b13  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180069b18  lea     rdx, [rbp+1A0h+var_1E8]
0x180069b1c  lea     rcx, [rbp+1A0h+var_1C8]
0x180069b20  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180069b25  lea     rcx, [rbp+1A0h+var_1E8]; void *
0x180069b29  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069b2e  mov     ebx, r13d
0x180069b31  jmp     loc_180069A51
0x180069b36  mov     rcx, [rsp+2A0h+var_250]
0x180069b3b  sub     rcx, [rsp+2A0h+hKey+8]
0x180069b40  sar     rcx, 5
0x180069b44  mov     r15d, r13d
0x180069b47  cmp     rax, rcx
0x180069b4a  setnz   r15b
0x180069b4e  mov     [rsp+2A0h+pv], r13
0x180069b53  lea     rdx, [rbp+1A0h+var_1E8]
0x180069b57  lea     rcx, [rsp+2A0h+pv]
0x180069b5c  call    ?start@?$tip_test@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(void)
0x180069b61  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::`vftable'
0x180069b68  mov     [rsp+2A0h+var_230], rax
0x180069b6d  mov     [rsp+2A0h+var_228], r13
0x180069b72  lea     rax, [rsp+2A0h+var_230]
0x180069b77  mov     [rbp+1A0h+var_220], rax
0x180069b7b  mov     [rbp+1A0h+var_218], r13
0x180069b7f  mov     [rbp+1A0h+var_210], r13d
0x180069b83  mov     [rbp+1A0h+var_208], r13
0x180069b87  mov     [rbp+1A0h+var_200], r13b
0x180069b8b  lea     rcx, [rsp+2A0h+var_228]; this
0x180069b90  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180069b95  nop
0x180069b96  mov     rbx, [rsp+2A0h+pv]
0x180069b9b  mov     [rbp+1A0h+var_1F8], rbx
0x180069b9f  test    rbx, rbx
0x180069ba2  jz      short loc_180069BB7
0x180069ba4  lock inc dword ptr [rbx+138h]
0x180069bab  mov     rcx, rbx; pv
0x180069bae  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x180069bb3  mov     rbx, [rbp+1A0h+var_1F8]
0x180069bb7  test    rbx, rbx
0x180069bba  jz      short loc_180069BC3
0x180069bbc  lock inc dword ptr [rbx+138h]
0x180069bc3  lea     rcx, [rbx+8]
0x180069bc7  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180069bcc  mov     [rbx+110h], r15d
0x180069bd3  test    rbx, rbx
0x180069bd6  jz      short loc_180069BE9
0x180069bd8  lea     rcx, [rbx+8]
0x180069bdc  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x180069be1  mov     rcx, rbx; pv
0x180069be4  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x180069be9  mov     rdx, rsi
0x180069bec  lea     rcx, [rbp+1A0h+var_1E8]
0x180069bf0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180069bf5  mov     r14, rax
0x180069bf8  mov     rbx, [rbp+1A0h+var_1F8]
0x180069bfc  test    rbx, rbx
0x180069bff  jz      short loc_180069C08
0x180069c01  lock inc dword ptr [rbx+138h]
0x180069c08  lea     rcx, [rbx+8]
0x180069c0c  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180069c11  lea     rcx, [rbx+118h]
0x180069c18  mov     rdx, r14
0x180069c1b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180069c20  test    rbx, rbx
0x180069c23  jz      short loc_180069C36
0x180069c25  lea     rcx, [rbx+8]
0x180069c29  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x180069c2e  mov     rcx, rbx; pv
0x180069c31  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x180069c36  lea     rcx, [rbp+1A0h+var_1E8]; void *
0x180069c3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069c3f  mov     rbx, [rbp+1A0h+var_1F8]
0x180069c43  lea     rsi, [rbx+0C8h]
0x180069c4a  mov     rcx, rsi; lpCriticalSection
0x180069c4d  call    cs:__imp_EnterCriticalSection
0x180069c54  nop     dword ptr [rax+rax+00h]
0x180069c59  or      dword ptr [rbx+48h], 300h
0x180069c60  cmp     [rbx+0F8h], r13
0x180069c67  jz      short loc_180069C77
0x180069c69  mov     edx, 2
0x180069c6e  lea     rcx, [rbx+8]
0x180069c72  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180069c77  test    rsi, rsi
0x180069c7a  jz      short loc_180069C8B
0x180069c7c  mov     rcx, rsi; lpCriticalSection
0x180069c7f  call    cs:__imp_LeaveCriticalSection
0x180069c86  nop     dword ptr [rax+rax+00h]
0x180069c8b  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x180069c92  test    rax, rax
0x180069c95  jnz     short loc_180069CDF
0x180069c97  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180069c9e  test    rax, rax
0x180069ca1  jnz     short loc_180069CBD
0x180069ca3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180069caa  call    cs:__imp_GetModuleHandleW
0x180069cb1  nop     dword ptr [rax+rax+00h]
0x180069cb6  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180069cbd  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x180069cc4  mov     rcx, rax; hModule
0x180069cc7  call    cs:__imp_GetProcAddress
0x180069cce  nop     dword ptr [rax+rax+00h]
0x180069cd3  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x180069cda  test    rax, rax
0x180069cdd  jz      short loc_180069CE7
  ... truncated ...
```
