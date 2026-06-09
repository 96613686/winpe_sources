# helium::Container::Start(void *,helium::ContainerType,helium::HeliumSystemConfiguration const &)

- ea: `0x180071bec`
- end: `0x180072519`
- name: `?Start@Container@helium@@AEAAXPEAXW4ContainerType@2@AEBUHeliumSystemConfiguration@2@@Z`
- size: `2349`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800706c4`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18000ae88`
- `0x1800125f4`
- `0x180013510`
- `0x1800136dc`
- `0x1800164f8`
- `0x180016b98`
- `0x1800190e0`
- `0x18001f808`
- `0x18002109c`
- `0x180025980`
- `0x18002bab4`
- `0x18002d4f0`
- `0x18002d56c`
- `0x18002e8b0`
- `0x180034148`
- `0x1800356dc`
- `0x180035ff0`
- `0x180038214`
- `0x18004abe8`
- `0x1800545a0`
- `0x18006e8ac`
- `0x18006ecd4`
- `0x18006f0a0`
- `0x18006ff94`
- `0x18007087c`
- `0x180070960`
- `0x180071bec`
- `0x180072520`
- `0x1800764dc`
- `0x1800b1b68`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071c90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007225f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071c90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007225f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071ea4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180072434`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180071ea4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180072434`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007220e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007220e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800721ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ede`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072453`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071ede`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072453`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180072410`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180072410`
- `ntdll!EtwEventUnregister` at `0x1800721b4`
- `ntdll!EtwEventUnregister` at `0x1800721b4`
- `ntdll!EtwEventWrite` at `0x1800721a3`
- `ntdll!EtwEventWrite` at `0x1800721a3`
- `ntdll!EtwEventRegister` at `0x18007217b`
- `ntdll!EtwEventRegister` at `0x18007217b`
- `container!WcRegisterForContainerTerminationNotification` at `0x180072231`
- `container!WcRegisterForContainerTerminationNotification` at `0x180072231`
- `container!WcReleaseContainerTerminationNotification` at `0x180072200`
- `container!WcReleaseContainerTerminationNotification` at `0x180072200`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800720ca`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800720ca`

## string_xrefs

- `0x180071f6c`: `ConfigureVfs`
- `0x1800721cf`: `onecore\base\appmodel\execmodel\desktopappx\lib\ManifestedETWHelpers.h`
- `0x180071c45`: `CreateContainer`
- `0x1800724e8`: `onecore\internal\com\inc\combase\ComGuid.hpp`

## pseudocode

```c
__int64 __fastcall helium::Container::Start(__int64 *a1, __int64 *a2, int a3, __int64 a4)
{
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rbx
  __int64 *v7; // rsi
  _QWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edx
  void *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  const wchar_t *v15; // rsi
  const wchar_t *v16; // rcx
  const wchar_t *v17; // rdx
  size_t v18; // r8
  int v19; // ecx
  __int64 *v20; // rdx
  __int64 v21; // rcx
  __int64 Job; // rax
  struct _GUID **v23; // r12
  _QWORD *v24; // r15
  __int64 *v25; // rbx
  struct _GUID *v26; // r14
  __int64 *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  void *v32; // r8
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  const char *v34; // r9
  int v35; // ecx
  const wchar_t *v36; // rax
  int v37; // ecx
  __int64 *v38; // rax
  unsigned int v39; // eax
  __int64 v40; // r15
  DWORD LastError; // ebx
  int v42; // eax
  __int64 v43; // rcx
  __int64 inserted; // rbx
  __int64 v45; // rcx
  __int64 v46; // r15
  __int64 *v47; // r14
  size_t v48; // r8
  const wchar_t *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 result; // rax
  const char *v54; // r9
  int v55; // eax
  unsigned int v56[2]; // [rsp+20h] [rbp-718h]
  int v57; // [rsp+28h] [rbp-710h]
  int v58; // [rsp+30h] [rbp-708h]
  __int64 v59; // [rsp+38h] [rbp-700h]
  int v60; // [rsp+40h] [rbp-6F8h]
  HANDLE hObject[2]; // [rsp+50h] [rbp-6E8h] BYREF
  __int64 v62; // [rsp+60h] [rbp-6D8h]
  void (__fastcall ***v63)(_QWORD, __int64); // [rsp+70h] [rbp-6C8h] BYREF
  __int64 *v64; // [rsp+78h] [rbp-6C0h] BYREF
  __int64 *v65; // [rsp+80h] [rbp-6B8h]
  __int128 v66; // [rsp+90h] [rbp-6A8h] BYREF
  __int64 *v67; // [rsp+A0h] [rbp-698h] BYREF
  __int64 *v68; // [rsp+A8h] [rbp-690h]
  __int64 v69; // [rsp+B0h] [rbp-688h]
  __int64 *v70; // [rsp+B8h] [rbp-680h]
  _BYTE v71[32]; // [rsp+C0h] [rbp-678h] BYREF
  char v72; // [rsp+E0h] [rbp-658h]
  RTL_SRWLOCK *v73; // [rsp+E8h] [rbp-650h] BYREF
  _BYTE v74[32]; // [rsp+100h] [rbp-638h] BYREF
  __int64 v75; // [rsp+120h] [rbp-618h]
  int v76; // [rsp+128h] [rbp-610h]
  char v77; // [rsp+13Ch] [rbp-5FCh]
  __int64 v78; // [rsp+140h] [rbp-5F8h]
  __int64 v79; // [rsp+148h] [rbp-5F0h]
  char v80; // [rsp+164h] [rbp-5D4h]
  OLECHAR sz[40]; // [rsp+170h] [rbp-5C8h] BYREF
  _QWORD v82[42]; // [rsp+1C0h] [rbp-578h] BYREF
  _QWORD v83[42]; // [rsp+310h] [rbp-428h] BYREF
  _BYTE v84[600]; // [rsp+460h] [rbp-2D8h] BYREF
  HANDLE v85; // [rsp+6B8h] [rbp-80h]
  const wchar_t *v86; // [rsp+6C0h] [rbp-78h] BYREF
  int v87; // [rsp+6C8h] [rbp-70h]
  int v88; // [rsp+6CCh] [rbp-6Ch]
  __int64 *v89; // [rsp+6D0h] [rbp-68h]
  int v90; // [rsp+6D8h] [rbp-60h]
  int v91; // [rsp+6DCh] [rbp-5Ch]
  OLECHAR *v92; // [rsp+6E0h] [rbp-58h]
  __int64 v93; // [rsp+6E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+738h] [rbp+0h]

  *(_QWORD *)&v66 = a4;
  LODWORD(v63) = a3;
  v64 = a2;
  v70 = a1;
  LODWORD(hObject[0]) = 0;
  if ( (unsigned __int64)a1[3] <= 7 )
    v5 = (const unsigned __int16 *)a1;
  else
    v5 = (const unsigned __int16 *)*a1;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v83,
    "CreateContainer");
  v83[0] = &DesktopAppXProvider::CreateContainer::`vftable';
  DesktopAppXProvider::CreateContainer::StartActivity((DesktopAppXProvider::CreateContainer *)v83, v5);
  v72 = 0;
  AcquireSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
  v73 = &helium::Container::s_lockInstanceAndDiagnosticMaps;
  v6 = helium::Container::s_mapCurrentInstancesByContainerName;
  v67 = &helium::Container::s_mapCurrentInstancesByContainerName;
  v68 = 0;
  try
  {
    v7 = (__int64 *)operator new(0x48u);
    v68 = v7;
    std::wstring::wstring(v7 + 4, a1);
    v7[8] = (__int64)a1;
    *v7 = v6;
    v7[1] = v6;
    v7[2] = v6;
    *((_WORD *)v7 + 12) = 0;
    v8 = *(_QWORD **)(helium::Container::s_mapCurrentInstancesByContainerName + 8);
    v9 = 0;
    v10 = 0;
    hObject[0] = 0;
    if ( *((_BYTE *)v8 + 25) )
    {
      v11 = v8;
    }
    else
    {
      do
      {
        v11 = v8;
        if ( (unsigned __int8)std::operator<<unsigned short>(v7 + 4, v8 + 4) )
        {
          v9 = 1;
          v8 = (_QWORD *)*v8;
        }
        else
        {
          v9 = 0;
          v8 = (_QWORD *)v8[2];
        }
      }
      while ( !*((_BYTE *)v8 + 25) );
      v10 = (unsigned int)hObject[0];
    }
    if ( qword_18010A228 == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    hObject[0] = v11;
    hObject[1] = (HANDLE)__PAIR64__(v10, v9);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>>>::_Insert_node(
      &helium::Container::s_mapCurrentInstancesByContainerName,
      hObject,
      v7);
    std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Find_lower_bound<helium::Container::DiagnosticInformationKey>(
      v12,
      &v67,
      a1 + 9);
    v13 = v69;
    v15 = (const wchar_t *)(a1 + 4);
    if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Lower_bound_duplicate<helium::Container::DiagnosticInformationKey>(
                             v14,
                             v69,
                             a1 + 9)
      || v13 == helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName )
    {
      *((_DWORD *)a1 + 34) = 0;
      std::wstring::wstring(v74, a1 + 4);
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::emplace<helium::Container::DiagnosticInformationKey const &,helium::Container::DiagnosticInformation>(
        v21,
        &v67,
        a1 + 9,
        v74);
      std::wstring::~wstring(v74);
    }
    else
    {
      v16 = (const wchar_t *)(v13 + 96);
      if ( (unsigned __int64)a1[7] <= 7 )
        v17 = (const wchar_t *)(a1 + 4);
      else
        v17 = *(const wchar_t **)v15;
      v18 = *(_QWORD *)(v13 + 112);
      if ( *(_QWORD *)(v13 + 120) > 7u )
        v16 = *(const wchar_t **)v16;
      if ( v18 == a1[6] && (!v18 || !wmemcmp(v16, v17, v18)) )
      {
        v19 = *(_DWORD *)(v13 + 128);
      }
      else
      {
        v20 = a1 + 4;
        if ( v72 )
        {
          std::wstring::operator=(v71, v20);
        }
        else
        {
          std::wstring::wstring(v71, v20);
          v72 = 1;
        }
        v19 = 0;
      }
      *((_DWORD *)a1 + 34) = v19;
    }
    ReleaseSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
    Job = helium::Container::CreateJob(hObject, a1);
    v23 = (struct _GUID **)(a1 + 18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a1 + 18,
      Job);
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    v67 = a1;
    LOBYTE(v68) = 1;
    v24 = (_QWORD *)v66;
    v59 = v66 + 240;
    v58 = (int)v63;
    LOBYTE(v57) = *((_BYTE *)a1 + 64);
    *(_QWORD *)v56 = v66 + 48;
    v25 = v64;
    helium::GenerateDescription(v84, v64, a1, a1 + 4);
    helium::Container::CreateHeliumContainer(*v23, (const struct helium::ContainerDescription *)v84);
    v60 = 3;
    v26 = *v23;
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v82,
      "ConfigureVfs");
    v82[0] = &DesktopAppXProvider::ConfigureVfs::`vftable';
    DesktopAppXProvider::ConfigureVfs::StartActivity((DesktopAppXProvider::ConfigureVfs *)v82);
    *(_QWORD *)&v66 = 0;
    LODWORD(hObject[0]) = 1;
    if ( *v24 == v24[1] )
    {
      v28 = 0;
    }
    else
    {
      v27 = (__int64 *)DesktopAppXVFS::VfsProvider::ApplyMappings(
                         &v63,
                         v26,
                         v24,
                         v25,
                         *(_QWORD *)v56,
                         (_BYTE)v57,
                         v58,
                         v59,
                         3);
      v28 = *v27;
      *v27 = 0;
      *(_QWORD *)&v66 = v28;
      if ( v63 )
        (**v63)(v63, 1);
    }
    if ( v24[3] != v24[4] )
    {
      DesktopAppXVFS::VfsProvider::ApplyMappings(&v64, v26, v24 + 3, v64, *(_QWORD *)v56, v57, v58, v59, v60);
      if ( v64 )
        (*(void (__fastcall **)(__int64 *, __int64))*v64)(v64, 1);
    }
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v82, 0);
    v82[0] = &DesktopAppXProvider::ConfigureVfs::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v82, v29, v30, v31);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v82);
    v33 = (void (__fastcall ***)(_QWORD, __int64))a1[22];
    a1[22] = v28;
    if ( v33 )
      (**v33)(v33, 1);
    *((struct _GUID *)a1 + 10) = *helium::GetContainerIdentifier((helium *)&v73, *v23, v32);
    if ( StringFromGUID2((const GUID *const)a1 + 10, sz, 39) != 39 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecore\\internal\\com\\inc\\combase\\ComGuid.hpp",
        v34);
    v35 = 2 * *((_DWORD *)a1 + 12) + 2;
    if ( (unsigned __int64)a1[7] <= 7 )
      v36 = (const wchar_t *)(a1 + 4);
    else
      v36 = *(const wchar_t **)v15;
    v86 = v36;
    v87 = v35;
    v88 = 0;
    v37 = 2 * *((_DWORD *)a1 + 4) + 2;
    if ( (unsigned __int64)a1[3] <= 7 )
      v38 = a1;
    else
      v38 = (__int64 *)*a1;
    v89 = v38;
    v90 = v37;
    v91 = 0;
    v92 = sz;
    v93 = 78;
    hObject[0] = 0;
    if ( !(unsigned int)EtwEventRegister(AppModelRuntimeProviderId, 0, 0, hObject) )
    {
      EtwEventWrite(hObject[0], AppModelDesktopAppXContainerCreateSuccess, 3, &v86);
      v39 = EtwEventUnregister(hObject[0]);
      if ( v39 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\ManifestedETWHelpers.h",
          (const char *)v39,
          v56[0]);
    }
    v40 = a1[19];
    if ( v40 )
    {
      LastError = GetLastError();
      WcReleaseContainerTerminationNotification(v40);
      SetLastError(LastError);
    }
    a1[19] = 0;
    v42 = WcRegisterForContainerTerminationNotification(*v23, &helium::TerminationCallback, a1, a1 + 19);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E1,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
        (const char *)(unsigned int)v42,
        v56[0]);
    LOBYTE(v68) = 0;
    AcquireSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
    v73 = &helium::Container::s_lockInstanceAndDiagnosticMaps;
    std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Find_lower_bound<helium::Container::DiagnosticInformationKey>(
      v43,
      hObject,
      a1 + 9);
    inserted = v62;
    if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Lower_bound_duplicate<helium::Container::DiagnosticInformationKey>(
                             v45,
                             v62,
                             a1 + 9) )
    {
      if ( qword_18010A238 == 0x147AE147AE147AELL )
        std::_Throw_tree_length_error();
      v46 = helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName;
      v64 = &helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName;
      v65 = 0;
      v47 = (__int64 *)operator new(0xC8u);
      v65 = v47;
      *(_QWORD *)&v66 = v47 + 4;
      std::wstring::wstring(v47 + 4, a1 + 9);
      std::wstring::wstring(v47 + 8, a1 + 13);
      memset_0(v47 + 12, 0, 0x68u);
      v47[15] = 7;
      *v47 = v46;
      v47[1] = v46;
      v47[2] = v46;
      *((_WORD *)v47 + 12) = 0;
      v66 = *(_OWORD *)hObject;
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>>>::_Insert_node(
                   &helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName,
                   &v66,
                   v47);
    }
    if ( v72 )
    {
      std::wstring::operator=(inserted + 96, v71);
    }
    else
    {
      if ( (unsigned __int64)a1[7] > 7 )
        v15 = *(const wchar_t **)v15;
      v48 = *(_QWORD *)(inserted + 112);
      if ( *(_QWORD *)(inserted + 120) <= 7u )
        v49 = (const wchar_t *)(inserted + 96);
      else
        v49 = *(const wchar_t **)(inserted + 96);
      if ( v48 != a1[6] || v48 && wmemcmp(v49, v15, v48) || *(_DWORD *)(inserted + 128) != *((_DWORD *)a1 + 34) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v49);
    }
    *(_DWORD *)(inserted + 128) = *((_DWORD *)a1 + 34) + 1;
    *(_QWORD *)(inserted + 132) = 0;
    *(_OWORD *)(inserted + 140) = *((_OWORD *)a1 + 10);
    if ( !*(_BYTE *)(inserted + 156) )
      *(_BYTE *)(inserted + 156) = 1;
    *(_QWORD *)(inserted + 160) = GetTickCount64();
    *(_QWORD *)(inserted + 168) = 0;
    *(_BYTE *)(inserted + 196) = 0;
    ReleaseSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
    if ( (char *)v85 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v85);
    Schema::Containers::Definition::Namespace::~Namespace((Schema::Containers::Definition::Namespace *)v84);
    if ( v72 )
      std::wstring::~wstring(v71);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v83, 0);
    v83[0] = &DesktopAppXProvider::CreateContainer::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v83, v50, v51, v52);
    result = wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v83);
  }
  catch ( ... )
  {
    v55 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x311,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
            v54);
    *((_DWORD *)v70 + 46) = v55;
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180071bec  push    rbx
0x180071bee  push    rsi
0x180071bef  push    rdi
0x180071bf0  push    r12
0x180071bf2  push    r13
0x180071bf4  push    r14
0x180071bf6  push    r15
0x180071bf8  sub     rsp, 700h
0x180071bff  mov     rax, cs:__security_cookie
0x180071c06  xor     rax, rsp
0x180071c09  mov     [rsp+738h+var_48], rax
0x180071c11  mov     qword ptr [rsp+738h+var_6A8], r9
0x180071c19  mov     dword ptr [rsp+738h+var_6C8], r8d
0x180071c1e  mov     [rsp+738h+var_6C0], rdx
0x180071c23  mov     rdi, rcx
0x180071c26  mov     [rsp+738h+var_680], rcx
0x180071c2e  xor     r12d, r12d
0x180071c31  mov     dword ptr [rsp+738h+hObject], r12d
0x180071c36  cmp     qword ptr [rcx+18h], 7
0x180071c3b  jbe     short loc_180071C42
0x180071c3d  mov     rbx, [rcx]
0x180071c40  jmp     short loc_180071C45
0x180071c42  mov     rbx, rdi
0x180071c45  lea     rdx, aCreatecontaine; "CreateContainer"
0x180071c4c  lea     rcx, [rsp+738h+var_428]
0x180071c54  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180071c59  lea     rax, ??_7CreateContainer@DesktopAppXProvider@@6B@; const DesktopAppXProvider::CreateContainer::`vftable'
0x180071c60  mov     [rsp+738h+var_428], rax
0x180071c68  mov     rdx, rbx; unsigned __int16 *
0x180071c6b  lea     rcx, [rsp+738h+var_428]; this
0x180071c73  call    ?StartActivity@CreateContainer@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::CreateContainer::StartActivity(ushort const *)
0x180071c78  nop
0x180071c79  mov     [rsp+738h+var_6F8], r12d
0x180071c7e  mov     [rsp+738h+var_658], r12b
0x180071c86  lea     rbx, ?s_lockInstanceAndDiagnosticMaps@Container@helium@@0Vsrwlock@wil@@A; wil::srwlock helium::Container::s_lockInstanceAndDiagnosticMaps
0x180071c8d  mov     rcx, rbx; SRWLock
0x180071c90  call    cs:__imp_AcquireSRWLockExclusive
0x180071c97  nop     dword ptr [rax+rax+00h]
0x180071c9c  mov     [rsp+738h+var_650], rbx
0x180071ca4  mov     rbx, cs:?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x180071cab  lea     rax, ?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x180071cb2  mov     [rsp+738h+var_698], rax
0x180071cba  mov     [rsp+738h+var_690], r12
0x180071cc2  mov     ecx, 48h ; 'H'; Size
0x180071cc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180071ccc  mov     rsi, rax
0x180071ccf  mov     [rsp+738h+var_690], rax
0x180071cd7  mov     rdx, rdi
0x180071cda  lea     rcx, [rax+20h]
0x180071cde  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180071ce3  mov     [rsi+40h], rdi
0x180071ce7  mov     [rsi], rbx
0x180071cea  mov     [rsi+8], rbx
0x180071cee  mov     [rsi+10h], rbx
0x180071cf2  mov     [rsi+18h], r12w
0x180071cf7  mov     rax, cs:?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x180071cfe  mov     rbx, [rax+8]
0x180071d02  mov     eax, r12d
0x180071d05  xor     edx, edx
0x180071d07  mov     [rsp+738h+hObject], rdx
0x180071d0c  lea     r13d, [rdx+1]
0x180071d10  cmp     [rbx+19h], r12b
0x180071d14  jnz     short loc_180071D46
0x180071d16  mov     r15, rbx
0x180071d19  lea     rdx, [rbx+20h]
0x180071d1d  lea     rcx, [rsi+20h]
0x180071d21  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180071d26  test    al, al
0x180071d28  jz      short loc_180071D32
0x180071d2a  mov     eax, r13d
0x180071d2d  mov     rbx, [rbx]
0x180071d30  jmp     short loc_180071D39
0x180071d32  mov     eax, r12d
0x180071d35  mov     rbx, [rbx+10h]
0x180071d39  cmp     [rbx+19h], r12b
0x180071d3d  jz      short loc_180071D16
0x180071d3f  mov     rdx, [rsp+738h+hObject]
0x180071d44  jmp     short loc_180071D49
0x180071d46  mov     r15, rbx
0x180071d49  mov     rcx, 38E38E38E38E38Eh
0x180071d53  cmp     cs:qword_18010A228, rcx
0x180071d5a  jz      loc_1800724E2
0x180071d60  mov     [rsp+738h+hObject], r15
0x180071d65  mov     dword ptr [rsp+738h+hObject+8], eax
0x180071d69  mov     dword ptr [rsp+738h+hObject+0Ch], edx
0x180071d6d  mov     r8, rsi
0x180071d70  lea     rdx, [rsp+738h+hObject]
0x180071d75  lea     rcx, ?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x180071d7c  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VClmPackageData@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VClmPackageData@@@WRL@Microsoft@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VClmPackageData@@@WRL@Microsoft@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>,void *> *>,std::_Tree_node<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>,void *> * const)
0x180071d81  lea     r14, [rdi+48h]
0x180071d85  mov     r8, r14
0x180071d88  lea     rdx, [rsp+738h+var_698]
0x180071d90  call    ??$_Find_lower_bound@UDiagnosticInformationKey@Container@helium@@@?$_Tree@V?$_Tmap_traits@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@PEAX@std@@@1@AEBUDiagnosticInformationKey@Container@helium@@@Z; std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Find_lower_bound<helium::Container::DiagnosticInformationKey>(helium::Container::DiagnosticInformationKey const &)
0x180071d95  mov     r8, r14
0x180071d98  mov     rbx, [rsp+738h+var_688]
0x180071da0  mov     rdx, rbx
0x180071da3  call    ??$_Lower_bound_duplicate@UDiagnosticInformationKey@Container@helium@@@?$_Tree@V?$_Tmap_traits@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@PEAX@1@AEBUDiagnosticInformationKey@Container@helium@@@Z; std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Lower_bound_duplicate<helium::Container::DiagnosticInformationKey>(std::_Tree_node<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>,void *> * const,helium::Container::DiagnosticInformationKey const &)
0x180071da8  lea     rsi, [rdi+20h]
0x180071dac  test    al, al
0x180071dae  jz      short loc_180071E2F
0x180071db0  cmp     rbx, cs:?s_mapDiagnosticInformationByUserSidAndContainerFamilyName@Container@helium@@0V?$map@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@@std@@A; std::map<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation> helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName
0x180071db7  jz      short loc_180071E2F
0x180071db9  lea     rcx, [rbx+60h]
0x180071dbd  cmp     qword ptr [rsi+18h], 7
0x180071dc2  jbe     short loc_180071DC9
0x180071dc4  mov     rdx, [rsi]
0x180071dc7  jmp     short loc_180071DCC
0x180071dc9  mov     rdx, rsi; S2
0x180071dcc  mov     r8, [rcx+10h]; N
0x180071dd0  cmp     qword ptr [rcx+18h], 7
0x180071dd5  jbe     short loc_180071DDA
0x180071dd7  mov     rcx, [rcx]; S1
0x180071dda  cmp     r8, [rsi+10h]
0x180071dde  jnz     short loc_180071DF6
0x180071de0  test    r8, r8
0x180071de3  jz      short loc_180071DEE
0x180071de5  call    wmemcmp
0x180071dea  test    eax, eax
0x180071dec  jnz     short loc_180071DF6
0x180071dee  mov     ecx, [rbx+80h]
0x180071df4  jmp     short loc_180071E22
0x180071df6  mov     rdx, rsi
0x180071df9  lea     rcx, [rsp+738h+var_678]
0x180071e01  cmp     [rsp+738h+var_658], r12b
0x180071e09  jz      short loc_180071E12
0x180071e0b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180071e10  jmp     short loc_180071E1F
0x180071e12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180071e17  mov     [rsp+738h+var_658], r13b
0x180071e1f  mov     ecx, r12d
0x180071e22  mov     eax, 88h
0x180071e27  mov     rdx, rdi
0x180071e2a  mov     [rax+rdx], ecx
0x180071e2d  jmp     short loc_180071E9D
0x180071e2f  mov     [rdi+88h], r12d
0x180071e36  mov     rdx, rsi
0x180071e39  lea     rcx, [rsp+738h+var_638]
0x180071e41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180071e46  mov     [rsp+738h+var_618], r12
0x180071e4e  mov     [rsp+738h+var_610], r12d
0x180071e56  mov     [rsp+738h+var_5FC], r12b
0x180071e5e  mov     [rsp+738h+var_5F8], r12
0x180071e66  mov     [rsp+738h+var_5F0], r12
0x180071e6e  mov     [rsp+738h+var_5D4], r12b
0x180071e76  lea     r9, [rsp+738h+var_638]
0x180071e7e  mov     r8, r14
0x180071e81  lea     rdx, [rsp+738h+var_698]
0x180071e89  call    ??$emplace@AEBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@?$_Tree@V?$_Tmap_traits@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@std@@@std@@@std@@_N@1@AEBUDiagnosticInformationKey@Container@helium@@$$QEAUDiagnosticInformation@45@@Z; std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::emplace<helium::Container::DiagnosticInformationKey const &,helium::Container::DiagnosticInformation>(helium::Container::DiagnosticInformationKey const &,helium::Container::DiagnosticInformation &&)
0x180071e8e  nop
0x180071e8f  lea     rcx, [rsp+738h+var_638]; void *
0x180071e97  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180071e9c  nop
0x180071e9d  lea     rcx, ?s_lockInstanceAndDiagnosticMaps@Container@helium@@0Vsrwlock@wil@@A; SRWLock
0x180071ea4  call    cs:__imp_ReleaseSRWLockExclusive
0x180071eab  nop     dword ptr [rax+rax+00h]
0x180071eb0  mov     rdx, rdi
0x180071eb3  lea     rcx, [rsp+738h+hObject]
0x180071eb8  call    ?CreateJob@Container@helium@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; helium::Container::CreateJob(std::wstring const &)
0x180071ebd  lea     r12, [rdi+90h]
0x180071ec4  mov     rdx, rax
0x180071ec7  mov     rcx, r12
0x180071eca  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180071ecf  mov     rcx, [rsp+738h+hObject]; hObject
0x180071ed4  lea     rax, [rcx-1]
0x180071ed8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180071edc  ja      short loc_180071EEA
0x180071ede  call    cs:__imp_CloseHandle
0x180071ee5  nop     dword ptr [rax+rax+00h]
0x180071eea  mov     [rsp+738h+var_698], rdi
0x180071ef2  mov     byte ptr [rsp+738h+var_690], r13b
0x180071efa  mov     [rsp+738h+var_6F8], r13d
0x180071eff  mov     r15, qword ptr [rsp+738h+var_6A8]
0x180071f07  lea     rax, [r15+0F0h]
0x180071f0e  lea     rcx, [r15+30h]
0x180071f12  mov     [rsp+738h+var_700], rax
0x180071f17  mov     eax, dword ptr [rsp+738h+var_6C8]
0x180071f1b  mov     [rsp+738h+var_708], eax
0x180071f1f  mov     al, [rdi+40h]
0x180071f22  mov     [rsp+738h+var_710], al
0x180071f26  mov     qword ptr [rsp+738h+var_718], rcx; int
0x180071f2b  mov     r9, rsi
0x180071f2e  mov     r8, rdi
0x180071f31  mov     rbx, [rsp+738h+var_6C0]
0x180071f36  mov     rdx, rbx
0x180071f39  lea     rcx, [rsp+738h+var_2D8]
0x180071f41  call    ?GenerateDescription@helium@@YA?AUContainerDescription@1@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBUHivePaths@OfflineRegistry@@_NW4ContainerType@1@AEBV?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@4@@Z; helium::GenerateDescription(void *,std::wstring const &,std::wstring const &,OfflineRegistry::HivePaths const &,bool,helium::ContainerType,std::vector<WriteVirtualization::RegistryExclusion> const &)
0x180071f46  nop
0x180071f47  mov     [rsp+738h+var_6F8], 2
0x180071f4f  lea     rdx, [rsp+738h+var_2D8]; struct helium::ContainerDescription *
0x180071f57  mov     rcx, [r12]; retstr
0x180071f5b  call    ?CreateHeliumContainer@Container@helium@@CAXPEAXAEBUContainerDescription@2@@Z; helium::Container::CreateHeliumContainer(void *,helium::ContainerDescription const &)
0x180071f60  mov     [rsp+738h+var_6F8], 3
0x180071f68  mov     r14, [r12]
0x180071f6c  lea     rdx, aConfigurevfs; "ConfigureVfs"
0x180071f73  lea     rcx, [rsp+738h+var_578]
0x180071f7b  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180071f80  lea     rax, ??_7ConfigureVfs@DesktopAppXProvider@@6B@; const DesktopAppXProvider::ConfigureVfs::`vftable'
0x180071f87  mov     [rsp+738h+var_578], rax
0x180071f8f  lea     rcx, [rsp+738h+var_578]; this
0x180071f97  call    ?StartActivity@ConfigureVfs@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::ConfigureVfs::StartActivity(void)
0x180071f9c  nop
0x180071f9d  mov     qword ptr [rsp+738h+var_6A8], 0
0x180071fa9  mov     dword ptr [rsp+738h+hObject], r13d
0x180071fae  mov     rax, [r15+8]
0x180071fb2  cmp     [r15], rax
0x180071fb5  jz      short loc_180071FF6
0x180071fb7  mov     r9, rbx
0x180071fba  mov     r8, r15
0x180071fbd  mov     rdx, r14
0x180071fc0  lea     rcx, [rsp+738h+var_6C8]
0x180071fc5  call    ?ApplyMappings@VfsProvider@DesktopAppXVFS@@SA?AV12@PEAXAEBV?$vector@UMapping@DesktopAppXVFS@@V?$allocator@UMapping@DesktopAppXVFS@@@std@@@std@@0@Z; DesktopAppXVFS::VfsProvider::ApplyMappings(void *,std::vector<DesktopAppXVFS::Mapping> const &,void *)
0x180071fca  mov     rbx, [rax]
0x180071fcd  mov     qword ptr [rax], 0
0x180071fd4  mov     qword ptr [rsp+738h+var_6A8], rbx
0x180071fdc  mov     rcx, [rsp+738h+var_6C8]
0x180071fe1  test    rcx, rcx
0x180071fe4  jz      short loc_180071FF8
0x180071fe6  mov     rax, [rcx]
0x180071fe9  mov     edx, r13d
0x180071fec  mov     rax, [rax]
0x180071fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ff4  jmp     short loc_180071FF8
0x180071ff6  xor     ebx, ebx
0x180071ff8  lea     r8, [r15+18h]
0x180071ffc  mov     rax, [r8+8]
0x180072000  cmp     [r8], rax
0x180072003  jz      short loc_18007202F
0x180072005  mov     r9, [rsp+738h+var_6C0]
0x18007200a  mov     rdx, r14
0x18007200d  lea     rcx, [rsp+738h+var_6C0]
0x180072012  call    ?ApplyMappings@VfsProvider@DesktopAppXVFS@@SA?AV12@PEAXAEBV?$vector@UMapping@DesktopAppXVFS@@V?$allocator@UMapping@DesktopAppXVFS@@@std@@@std@@0@Z; DesktopAppXVFS::VfsProvider::ApplyMappings(void *,std::vector<DesktopAppXVFS::Mapping> const &,void *)
0x180072017  mov     rcx, [rsp+738h+var_6C0]
0x18007201c  test    rcx, rcx
0x18007201f  jz      short loc_18007202F
0x180072021  mov     rax, [rcx]
0x180072024  mov     edx, r13d
0x180072027  mov     rax, [rax]
0x18007202a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007202f  xor     edx, edx
0x180072031  lea     rcx, [rsp+738h+var_578]
0x180072039  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18007203e  nop
0x18007203f  lea     rax, ??_7ConfigureVfs@DesktopAppXProvider@@6B@; const DesktopAppXProvider::ConfigureVfs::`vftable'
0x180072046  mov     [rsp+738h+var_578], rax
0x18007204e  lea     rcx, [rsp+738h+var_578]
0x180072056  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18007205b  lea     rcx, [rsp+738h+var_578]
0x180072063  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180072068  mov     rcx, [rdi+0B0h]
0x18007206f  mov     [rdi+0B0h], rbx
0x180072076  test    rcx, rcx
0x180072079  jz      short loc_18007208A
0x18007207b  mov     rax, [rcx]
0x18007207e  mov     edx, r13d
0x180072081  mov     rax, [rax]
0x180072084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072089  nop
0x18007208a  mov     [rsp+738h+var_6F8], 4
0x180072092  mov     rdx, [r12]; retstr
0x180072096  lea     rcx, [rsp+738h+var_650]; this
0x18007209e  call    ?GetContainerIdentifier@helium@@YA?AU_GUID@@PEAX@Z; helium::GetContainerIdentifier(void *)
0x1800720a3  movups  xmm0, xmmword ptr [rax]
0x1800720a6  lea     rax, [rdi+0A0h]
0x1800720ad  movdqu  xmmword ptr [rax], xmm0
0x1800720b1  mov     rbx, [rsp+738h]
0x1800720b9  mov     r8d, 27h ; '''; cchMax
0x1800720bf  lea     rdx, [rsp+738h+sz]; lpsz
0x1800720c7  mov     rcx, rax; rguid
0x1800720ca  call    cs:__imp_StringFromGUID2
0x1800720d1  nop     dword ptr [rax+rax+00h]
0x1800720d6  cmp     eax, 27h ; '''
0x1800720d9  jnz     loc_1800724E8
0x1800720df  mov     eax, [rsi+10h]
0x1800720e2  lea     ecx, ds:2[rax*2]
0x1800720e9  cmp     qword ptr [rsi+18h], 7
0x1800720ee  jbe     short loc_1800720F5
0x1800720f0  mov     rax, [rsi]
0x1800720f3  jmp     short loc_1800720F8
0x1800720f5  mov     rax, rsi
0x1800720f8  mov     [rsp+738h+var_78], rax
0x180072100  mov     [rsp+738h+var_70], ecx
0x180072107  mov     [rsp+738h+var_6C], 0
0x180072112  mov     eax, [rdi+10h]
0x180072115  lea     ecx, ds:2[rax*2]
0x18007211c  cmp     qword ptr [rdi+18h], 7
0x180072121  jbe     short loc_180072128
0x180072123  mov     rax, [rdi]
0x180072126  jmp     short loc_18007212B
0x180072128  mov     rax, rdi
0x18007212b  mov     [rsp+738h+var_68], rax
0x180072133  mov     [rsp+738h+var_60], ecx
0x18007213a  mov     [rsp+738h+var_5C], 0
0x180072145  lea     rax, [rsp+738h+sz]
0x18007214d  mov     [rsp+738h+var_58], rax
0x180072155  mov     [rsp+738h+var_50], 4Eh ; 'N'
0x180072161  mov     [rsp+738h+hObject], 0
0x18007216a  lea     r9, [rsp+738h+hObject]
0x18007216f  xor     r8d, r8d
0x180072172  xor     edx, edx
0x180072174  lea     rcx, AppModelRuntimeProviderId
  ... truncated ...
```
