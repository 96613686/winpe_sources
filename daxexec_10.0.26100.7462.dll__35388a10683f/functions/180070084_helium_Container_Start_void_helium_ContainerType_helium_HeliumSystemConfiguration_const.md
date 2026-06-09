# helium::Container::Start(void *,helium::ContainerType,helium::HeliumSystemConfiguration const &)

- ea: `0x180070084`
- end: `0x180070bd9`
- name: `?Start@Container@helium@@AEAAXPEAXW4ContainerType@2@AEBUHeliumSystemConfiguration@2@@Z`
- size: `2901`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ed60`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180009338`
- `0x180010a84`
- `0x180011820`
- `0x180011a64`
- `0x1800148e8`
- `0x180014f4c`
- `0x180015314`
- `0x180015400`
- `0x18001748c`
- `0x18001ec94`
- `0x1800202bc`
- `0x18002031c`
- `0x180020338`
- `0x180024fdc`
- `0x18002b240`
- `0x18002c9c8`
- `0x18002ca40`
- `0x18002dcac`
- `0x180032564`
- `0x180033bbc`
- `0x180034378`
- `0x180048f40`
- `0x180052880`
- `0x180052af8`
- `0x18006cfe8`
- `0x18006d418`
- `0x18006d80c`
- `0x18006e6a4`
- `0x18006ef14`
- `0x180070084`
- `0x180070be0`
- `0x180074d70`
- `0x180096668`
- `0x180096968`
- `0x1800af978`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007012f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800708cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007012f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800708cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007035e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070aca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007035e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180070aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007085e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007085e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007087d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007087d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070ae9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070535`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070ae9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180070aa6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180070aa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800704f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800704f4`
- `ntdll!NtCreateJobObject` at `0x1800704b2`
- `ntdll!NtCreateJobObject` at `0x1800704b2`
- `ntdll!EtwEventUnregister` at `0x180070822`
- `ntdll!EtwEventUnregister` at `0x180070822`
- `ntdll!EtwEventWrite` at `0x180070811`
- `ntdll!EtwEventWrite` at `0x180070811`
- `ntdll!EtwEventRegister` at `0x1800707e9`
- `ntdll!EtwEventRegister` at `0x1800707e9`
- `ntdll!RtlInitUnicodeString` at `0x1800703a9`
- `ntdll!RtlInitUnicodeString` at `0x1800703a9`
- `container!WcRegisterForContainerTerminationNotification` at `0x1800708a4`
- `container!WcRegisterForContainerTerminationNotification` at `0x1800708a4`
- `container!WcReleaseContainerTerminationNotification` at `0x18007086f`
- `container!WcReleaseContainerTerminationNotification` at `0x18007086f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180070745`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180070745`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800703f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800703f4`

## string_xrefs

- `0x1800705c8`: `ConfigureVfs`
- `0x18007083d`: `onecore\base\appmodel\execmodel\desktopappx\lib\ManifestedETWHelpers.h`
- `0x1800700e4`: `CreateContainer`
- `0x180070ba8`: `onecore\internal\com\inc\combase\ComGuid.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall helium::Container::Start(__int64 a1, RTL_SRWLOCK *a2, int a3, _QWORD *a4)
{
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rdi
  __int64 *v7; // r14
  __int64 *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  char v11; // al
  __int64 v12; // r9
  const WCHAR *v13; // r14
  char *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  char *v17; // rcx
  __int64 v18; // r8
  signed __int64 v19; // rcx
  int v20; // eax
  const WCHAR *p_SourceString; // rdx
  const char *v22; // r9
  int v23; // r13d
  NTSTATUS v24; // eax
  struct _GUID **v25; // r12
  unsigned int v26; // r13d
  struct _GUID *v27; // rdi
  void *v28; // r13
  void *v29; // r12
  void *v30; // rdi
  void **v31; // rax
  void *v32; // r8
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  const char *v34; // r9
  int v35; // ecx
  const WCHAR *v36; // rax
  unsigned int v37; // ecx
  const unsigned __int16 *v38; // rax
  unsigned int v39; // eax
  __int64 v40; // r13
  DWORD LastError; // edi
  int v42; // eax
  __int64 v43; // rcx
  __int64 inserted; // rdi
  __int64 v45; // rcx
  __int64 v46; // r13
  __int64 *v47; // r12
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 result; // rax
  const char *v51; // r9
  int v52; // eax
  int v53; // [rsp+20h] [rbp-768h]
  unsigned int v54; // [rsp+20h] [rbp-768h]
  RTL_SRWLOCK *v55; // [rsp+48h] [rbp-740h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-738h] BYREF
  int v57; // [rsp+58h] [rbp-730h]
  HLOCAL hMem; // [rsp+60h] [rbp-728h] BYREF
  __int64 *v59; // [rsp+68h] [rbp-720h]
  _QWORD *v60; // [rsp+70h] [rbp-718h]
  _OWORD v61[2]; // [rsp+80h] [rbp-708h] BYREF
  int v62; // [rsp+A0h] [rbp-6E8h]
  struct _GUID *v63; // [rsp+A8h] [rbp-6E0h]
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-6D8h] BYREF
  void *JobHandle[2]; // [rsp+C0h] [rbp-6C8h] BYREF
  __int64 v66; // [rsp+D0h] [rbp-6B8h]
  __int64 v67; // [rsp+D8h] [rbp-6B0h]
  _BYTE v68[32]; // [rsp+E0h] [rbp-6A8h] BYREF
  char v69; // [rsp+100h] [rbp-688h]
  HLOCAL *p_hMem; // [rsp+108h] [rbp-680h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+110h] [rbp-678h] BYREF
  char v72; // [rsp+118h] [rbp-670h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+120h] [rbp-668h] BYREF
  _BYTE v74[32]; // [rsp+150h] [rbp-638h] BYREF
  __int64 v75; // [rsp+170h] [rbp-618h]
  int v76; // [rsp+178h] [rbp-610h]
  char v77; // [rsp+18Ch] [rbp-5FCh]
  __int64 v78; // [rsp+190h] [rbp-5F8h]
  __int64 v79; // [rsp+198h] [rbp-5F0h]
  char v80; // [rsp+1B4h] [rbp-5D4h]
  OLECHAR sz[40]; // [rsp+1C0h] [rbp-5C8h] BYREF
  _QWORD v82[42]; // [rsp+210h] [rbp-578h] BYREF
  _QWORD v83[42]; // [rsp+360h] [rbp-428h] BYREF
  _BYTE v84[600]; // [rsp+4B0h] [rbp-2D8h] BYREF
  HANDLE v85; // [rsp+708h] [rbp-80h]
  PCWSTR SourceString; // [rsp+710h] [rbp-78h] BYREF
  int v87; // [rsp+718h] [rbp-70h]
  int v88; // [rsp+71Ch] [rbp-6Ch]
  const unsigned __int16 *v89; // [rsp+720h] [rbp-68h]
  unsigned __int64 v90; // [rsp+728h] [rbp-60h]
  OLECHAR *v91; // [rsp+730h] [rbp-58h]
  __int64 v92; // [rsp+738h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v60 = a4;
  LODWORD(v63) = a3;
  v55 = a2;
  v67 = a1;
  v62 = 0;
  v57 = 0;
  v5 = (const unsigned __int16 *)a1;
  if ( *(_QWORD *)(a1 + 24) > 7u )
    v5 = *(const unsigned __int16 **)a1;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v83,
    "CreateContainer");
  v83[0] = &DesktopAppXProvider::CreateContainer::`vftable';
  DesktopAppXProvider::CreateContainer::StartActivity((DesktopAppXProvider::CreateContainer *)v83, v5);
  v69 = 0;
  AcquireSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
  hObject = &helium::Container::s_lockInstanceAndDiagnosticMaps;
  v6 = helium::Container::s_mapCurrentInstancesByContainerName;
  hMem = &helium::Container::s_mapCurrentInstancesByContainerName;
  v59 = 0;
  try
  {
    v7 = (__int64 *)operator new(0x48u);
    v59 = v7;
    std::wstring::wstring(v7 + 4, a1);
    v7[8] = a1;
    *v7 = v6;
    v7[1] = v6;
    v7[2] = v6;
    *((_WORD *)v7 + 12) = 0;
    v8 = *(__int64 **)(helium::Container::s_mapCurrentInstancesByContainerName + 8);
    v61[0] = (unsigned __int64)v8;
    while ( !*((_BYTE *)v8 + 25) )
    {
      *(_QWORD *)&v61[0] = v8;
      if ( (unsigned __int8)std::operator<<unsigned short>(v7 + 4, v8 + 4) )
      {
        DWORD2(v61[0]) = 1;
        v8 = (__int64 *)*v8;
      }
      else
      {
        DWORD2(v61[0]) = 0;
        v8 = (__int64 *)v8[2];
      }
    }
    if ( qword_1801086B0 == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    DestinationString = (struct _UNICODE_STRING)v61[0];
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>>>::_Insert_node(
      &helium::Container::s_mapCurrentInstancesByContainerName,
      &DestinationString,
      v7);
    std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Find_lower_bound<helium::Container::DiagnosticInformationKey>(
      v9,
      JobHandle,
      a1 + 72);
    v11 = std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Lower_bound_duplicate<helium::Container::DiagnosticInformationKey>(
            v10,
            v66,
            a1 + 72);
    v12 = helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName;
    if ( v11 )
      v12 = v66;
    v13 = (const WCHAR *)(a1 + 32);
    v14 = (char *)(a1 + 32);
    if ( v12 == helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName )
    {
      *(_DWORD *)(a1 + 136) = 0;
      std::wstring::wstring(v74, v14);
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::emplace<helium::Container::DiagnosticInformationKey const &,helium::Container::DiagnosticInformation>(
        v15,
        v61,
        a1 + 72,
        v74);
      std::wstring::~wstring(v74);
      v16 = a1 + 32;
      goto LABEL_28;
    }
    v17 = (char *)(v12 + 96);
    if ( *(_QWORD *)(a1 + 56) > 7u )
      v14 = *(char **)v13;
    v18 = *(_QWORD *)(v12 + 112);
    if ( *(_QWORD *)(v12 + 120) > 7u )
      v17 = *(char **)v17;
    v16 = a1 + 32;
    if ( v18 == *(_QWORD *)(a1 + 48) )
    {
      if ( !v18 )
      {
LABEL_22:
        v20 = *(_DWORD *)(v12 + 128);
LABEL_27:
        *(_DWORD *)(a1 + 136) = v20;
LABEL_28:
        if ( &helium::Container::s_lockInstanceAndDiagnosticMaps )
          ReleaseSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
        helium::ContainerPath(&SourceString, (void *)a1);
        DestinationString = 0;
        p_SourceString = (const WCHAR *)&SourceString;
        if ( v90 > 7 )
          p_SourceString = SourceString;
        RtlInitUnicodeString(&DestinationString, p_SourceString);
        hMem = 0;
        p_hMem = &hMem;
        SecurityDescriptor = 0;
        v72 = 1;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                L"O:SYG:SYD:(A;;0x001F003F;;;SY)(A;;0x00120004;;;BA)(A;;4;;;S-1-5-80-979556362-403687129-3954533659-233514"
                 "1334-1547273080)",
                1u,
                &SecurityDescriptor,
                0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xC2,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
            v22);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hMem);
        *(_QWORD *)&ObjectAttributes.Length = 48;
        *(_QWORD *)&ObjectAttributes.Attributes = 16;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.SecurityDescriptor = hMem;
        ObjectAttributes.SecurityQualityOfService = 0;
        hObject = 0;
        v23 = v62 | 1;
        v57 = v62 | 1;
        ScopedPrivileges::Take(v61);
        JobHandle[0] = &hObject;
        JobHandle[1] = 0;
        LOBYTE(v66) = 1;
        v24 = NtCreateJobObject(&JobHandle[1], 0x1F003Fu, &ObjectAttributes);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0xCF,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
            (const char *)(unsigned int)v24,
            v53);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(JobHandle);
        ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v61);
        if ( hMem )
          LocalFree(hMem);
        std::wstring::~wstring(&SourceString);
        v25 = (struct _GUID **)(a1 + 144);
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          a1 + 144,
          &hObject);
        v26 = v23 & 0xFFFFFFFE;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        *(_QWORD *)&DestinationString.Length = a1;
        LOBYTE(DestinationString.Buffer) = 1;
        helium::GenerateDescription(
          (__int64)v84,
          v55,
          a1,
          v16,
          v60 + 6,
          *(_BYTE *)(a1 + 64),
          (int)v63,
          (__int64)(v60 + 30));
        helium::Container::CreateHeliumContainer(*v25, (const struct helium::ContainerDescription *)v84);
        v27 = *v25;
        v63 = *v25;
        wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
          v82,
          "ConfigureVfs");
        v82[0] = &DesktopAppXProvider::ConfigureVfs::`vftable';
        DesktopAppXProvider::ConfigureVfs::StartActivity((DesktopAppXProvider::ConfigureVfs *)v82);
        hObject = 0;
        v57 = v26 | 2;
        if ( *v60 == v60[1] )
        {
          v28 = 0;
          v29 = 0;
          v30 = 0;
        }
        else
        {
          v31 = (void **)DesktopAppXVFS::VfsProvider::ApplyMappings(&hMem, v27, v60, v55);
          v30 = *v31;
          *v31 = 0;
          hObject = v30;
          v28 = v30;
          v29 = v30;
          if ( hMem )
            (**(void (__fastcall ***)(HLOCAL, __int64))hMem)(hMem, 1);
        }
        if ( v60[3] != v60[4] )
        {
          DesktopAppXVFS::VfsProvider::ApplyMappings(&v55, v63, v60 + 3, v55);
          v29 = v28;
          if ( v55 )
          {
            (*(void (__fastcall **)(RTL_SRWLOCK *, __int64))v55->Ptr)(v55, 1);
            v29 = v30;
          }
        }
        wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v82, 0);
        v82[0] = &DesktopAppXProvider::ConfigureVfs::`vftable';
        wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v82);
        wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v82);
        v33 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 176);
        *(_QWORD *)(a1 + 176) = v29;
        if ( v33 )
          (**v33)(v33, 1);
        *(struct _GUID *)(a1 + 160) = *helium::GetContainerIdentifier((helium *)v61, *(struct _GUID **)(a1 + 144), v32);
        if ( StringFromGUID2((const GUID *const)(a1 + 160), sz, 39) != 39 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x19,
            (unsigned int)"onecore\\internal\\com\\inc\\combase\\ComGuid.hpp",
            v34);
        v35 = 2 * *(_DWORD *)(a1 + 48) + 2;
        v36 = (const WCHAR *)(a1 + 32);
        if ( *(_QWORD *)(a1 + 56) > 7u )
          v36 = *(const WCHAR **)v13;
        SourceString = v36;
        v87 = v35;
        v88 = 0;
        v37 = 2 * *(_DWORD *)(a1 + 16) + 2;
        v38 = (const unsigned __int16 *)a1;
        if ( *(_QWORD *)(a1 + 24) > 7u )
          v38 = *(const unsigned __int16 **)a1;
        v89 = v38;
        v90 = v37;
        v91 = sz;
        v92 = 78;
        v55 = 0;
        if ( !(unsigned int)EtwEventRegister(&AppModelRuntimeProviderId, 0, 0, &v55) )
        {
          EtwEventWrite(v55, &AppModelDesktopAppXContainerCreateSuccess, 3, &SourceString);
          v39 = EtwEventUnregister(v55);
          if ( v39 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x64,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\ManifestedETWHelpers.h",
              (const char *)v39,
              v54);
        }
        v40 = *(_QWORD *)(a1 + 152);
        if ( v40 )
        {
          LastError = GetLastError();
          WcReleaseContainerTerminationNotification(v40);
          SetLastError(LastError);
        }
        *(_QWORD *)(a1 + 152) = 0;
        v42 = WcRegisterForContainerTerminationNotification(
                *(_QWORD *)(a1 + 144),
                &helium::TerminationCallback,
                a1,
                a1 + 152);
        if ( v42 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2E1,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
            (const char *)(unsigned int)v42,
            v54);
        LOBYTE(DestinationString.Buffer) = 0;
        AcquireSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
        v55 = &helium::Container::s_lockInstanceAndDiagnosticMaps;
        std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Find_lower_bound<helium::Container::DiagnosticInformationKey>(
          v43,
          JobHandle,
          a1 + 72);
        inserted = v66;
        if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Lower_bound_duplicate<helium::Container::DiagnosticInformationKey>(
                                 v45,
                                 v66,
                                 a1 + 72) )
        {
          if ( qword_1801086C0 == 0x147AE147AE147AELL )
            std::_Throw_tree_length_error();
          v46 = helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName;
          hMem = &helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName;
          v59 = 0;
          v47 = (__int64 *)operator new(0xC8u);
          v59 = v47;
          hObject = v47 + 4;
          std::wstring::wstring(v47 + 4, a1 + 72);
          std::wstring::wstring(v47 + 8, a1 + 104);
          memset_0(v47 + 12, 0, 0x68u);
          *((_OWORD *)v47 + 6) = 0;
          v47[14] = 0;
          v47[15] = 7;
          *((_WORD *)v47 + 48) = 0;
          v47[16] = 0;
          *((_DWORD *)v47 + 34) = 0;
          *((_BYTE *)v47 + 156) = 0;
          v47[20] = 0;
          v47[21] = 0;
          *((_BYTE *)v47 + 196) = 0;
          *v47 = v46;
          v47[1] = v46;
          v47[2] = v46;
          *((_WORD *)v47 + 12) = 0;
          v61[0] = *(_OWORD *)JobHandle;
          inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>>>::_Insert_node(
                       &helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName,
                       v61,
                       v47);
        }
        if ( v69 )
        {
          std::wstring::operator=(inserted + 96, v68);
LABEL_74:
          *(_DWORD *)(inserted + 128) = *(_DWORD *)(a1 + 136) + 1;
          *(_QWORD *)(inserted + 132) = 0;
          *(_OWORD *)(inserted + 140) = *(_OWORD *)(a1 + 160);
          if ( !*(_BYTE *)(inserted + 156) )
            *(_BYTE *)(inserted + 156) = 1;
          *(_QWORD *)(inserted + 160) = GetTickCount64();
          *(_QWORD *)(inserted + 168) = 0;
          *(_BYTE *)(inserted + 196) = 0;
          ReleaseSRWLockExclusive(&helium::Container::s_lockInstanceAndDiagnosticMaps);
          if ( (char *)v85 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(v85);
          Schema::Containers::Definition::Namespace::~Namespace((Schema::Containers::Definition::Namespace *)v84);
          if ( v69 )
            std::wstring::~wstring(v68);
          wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v83, 0);
          v83[0] = &DesktopAppXProvider::CreateContainer::`vftable';
          wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v83);
          return wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v83);
        }
        if ( *(_QWORD *)(a1 + 56) > 7u )
          v13 = *(const WCHAR **)v13;
        v48 = *(_QWORD *)(inserted + 112);
        v49 = inserted + 96;
        if ( *(_QWORD *)(inserted + 120) > 7u )
          v49 = *(_QWORD *)(inserted + 96);
        if ( v48 == *(_QWORD *)(a1 + 48) )
        {
          if ( v48 )
          {
            v49 -= (__int64)v13;
            while ( *(const WCHAR *)((char *)v13 + v49) == *v13 )
            {
              ++v13;
              if ( !--v48 )
                goto LABEL_72;
            }
          }
          else
          {
LABEL_72:
            if ( *(_DWORD *)(inserted + 128) == *(_DWORD *)(a1 + 136) )
              goto LABEL_74;
          }
        }
        MicrosoftTelemetryAssertTriggeredNoArgs(v48, v49);
        goto LABEL_74;
      }
      v19 = v17 - v14;
      while ( *(_WORD *)&v14[v19] == *(_WORD *)v14 )
      {
        v14 += 2;
        if ( !--v18 )
          goto LABEL_22;
      }
    }
    if ( v69 )
    {
      std::wstring::operator=(v68);
    }
    else
    {
      std::wstring::wstring(v68, v13);
      v69 = 1;
    }
    v20 = 0;
    goto LABEL_27;
  }
  catch ( ... )
  {
    v52 = wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x311,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumcontainer.cpp",
            v51);
    *(_DWORD *)(v67 + 184) = v52;
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180070084  push    rbx
0x180070086  push    rsi
0x180070087  push    rdi
0x180070088  push    r12
0x18007008a  push    r13
0x18007008c  push    r14
0x18007008e  push    r15
0x180070090  sub     rsp, 750h
0x180070097  mov     rax, cs:__security_cookie
0x18007009e  xor     rax, rsp
0x1800700a1  mov     [rsp+788h+var_48], rax
0x1800700a9  mov     [rsp+788h+var_718], r9
0x1800700ae  mov     dword ptr [rsp+788h+var_6E0], r8d
0x1800700b6  mov     [rsp+788h+var_740], rdx
0x1800700bb  mov     rsi, rcx
0x1800700be  mov     [rsp+788h+var_6B0], rcx
0x1800700c6  xor     r12d, r12d
0x1800700c9  mov     eax, r12d
0x1800700cc  mov     [rsp+788h+var_6E8], eax
0x1800700d3  mov     [rsp+788h+var_730], eax
0x1800700d7  mov     rbx, rcx
0x1800700da  cmp     qword ptr [rcx+18h], 7
0x1800700df  jbe     short loc_1800700E4
0x1800700e1  mov     rbx, [rcx]
0x1800700e4  lea     rdx, aCreatecontaine; "CreateContainer"
0x1800700eb  lea     rcx, [rsp+788h+var_428]
0x1800700f3  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800700f8  lea     rax, ??_7CreateContainer@DesktopAppXProvider@@6B@; const DesktopAppXProvider::CreateContainer::`vftable'
0x1800700ff  mov     [rsp+788h+var_428], rax
0x180070107  mov     rdx, rbx; unsigned __int16 *
0x18007010a  lea     rcx, [rsp+788h+var_428]; this
0x180070112  call    ?StartActivity@CreateContainer@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::CreateContainer::StartActivity(ushort const *)
0x180070117  nop
0x180070118  mov     [rsp+788h+var_748], r12d
0x18007011d  mov     [rsp+788h+var_688], r12b
0x180070125  lea     rbx, ?s_lockInstanceAndDiagnosticMaps@Container@helium@@0Vsrwlock@wil@@A; wil::srwlock helium::Container::s_lockInstanceAndDiagnosticMaps
0x18007012c  mov     rcx, rbx; SRWLock
0x18007012f  call    cs:__imp_AcquireSRWLockExclusive
0x180070136  nop     dword ptr [rax+rax+00h]
0x18007013b  mov     [rsp+788h+hObject], rbx
0x180070140  mov     rdi, cs:?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x180070147  lea     rax, ?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x18007014e  mov     [rsp+788h+hMem], rax
0x180070153  mov     [rsp+788h+var_720], r12
0x180070158  mov     ecx, 48h ; 'H'; Size
0x18007015d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070162  mov     r14, rax
0x180070165  mov     [rsp+788h+var_720], rax
0x18007016a  mov     rdx, rsi
0x18007016d  lea     rcx, [rax+20h]
0x180070171  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180070176  mov     [r14+40h], rsi
0x18007017a  mov     [r14], rdi
0x18007017d  mov     [r14+8], rdi
0x180070181  mov     [r14+10h], rdi
0x180070185  mov     [r14+18h], r12w
0x18007018a  mov     rax, cs:?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x180070191  mov     rdi, [rax+8]
0x180070195  mov     qword ptr [rsp+788h+var_708], rdi
0x18007019d  mov     qword ptr [rsp+788h+var_708+8], r12
0x1800701a5  mov     r15d, 1
0x1800701ab  cmp     [rdi+19h], r12b
0x1800701af  jnz     short loc_1800701E5
0x1800701b1  mov     qword ptr [rsp+788h+var_708], rdi
0x1800701b9  lea     rdx, [rdi+20h]
0x1800701bd  lea     rcx, [r14+20h]
0x1800701c1  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800701c6  test    al, al
0x1800701c8  jz      short loc_1800701D7
0x1800701ca  mov     dword ptr [rsp+788h+var_708+8], r15d
0x1800701d2  mov     rdi, [rdi]
0x1800701d5  jmp     short loc_1800701AB
0x1800701d7  mov     dword ptr [rsp+788h+var_708+8], r12d
0x1800701df  mov     rdi, [rdi+10h]
0x1800701e3  jmp     short loc_1800701AB
0x1800701e5  mov     rax, 38E38E38E38E38Eh
0x1800701ef  cmp     cs:qword_1801086B0, rax
0x1800701f6  jz      loc_180070B78
0x1800701fc  movups  xmm0, [rsp+788h+var_708]
0x180070204  movdqu  xmmword ptr [rsp+788h+DestinationString.Length], xmm0
0x18007020d  mov     r8, r14
0x180070210  lea     rdx, [rsp+788h+DestinationString]
0x180070218  lea     rcx, ?s_mapCurrentInstancesByContainerName@Container@helium@@0V?$multimap@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVContainer@helium@@@std@@@2@@std@@A; std::multimap<std::wstring,helium::Container *> helium::Container::s_mapCurrentInstancesByContainerName
0x18007021f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VClmPackageData@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VClmPackageData@@@WRL@Microsoft@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@VClmPackageData@@@WRL@Microsoft@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>,void *> *>,std::_Tree_node<std::pair<std::wstring const,Microsoft::WRL::ComPtr<ClmPackageData>>,void *> * const)
0x180070224  lea     rdi, [rsi+48h]
0x180070228  mov     r8, rdi
0x18007022b  lea     rdx, [rsp+788h+JobHandle]
0x180070233  call    ??$_Find_lower_bound@UDiagnosticInformationKey@Container@helium@@@?$_Tree@V?$_Tmap_traits@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@PEAX@std@@@1@AEBUDiagnosticInformationKey@Container@helium@@@Z; std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Find_lower_bound<helium::Container::DiagnosticInformationKey>(helium::Container::DiagnosticInformationKey const &)
0x180070238  mov     r8, rdi
0x18007023b  mov     rdx, [rsp+788h+var_6B8]
0x180070243  call    ??$_Lower_bound_duplicate@UDiagnosticInformationKey@Container@helium@@@?$_Tree@V?$_Tmap_traits@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@PEAX@1@AEBUDiagnosticInformationKey@Container@helium@@@Z; std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::_Lower_bound_duplicate<helium::Container::DiagnosticInformationKey>(std::_Tree_node<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>,void *> * const,helium::Container::DiagnosticInformationKey const &)
0x180070248  mov     r9, cs:?s_mapDiagnosticInformationByUserSidAndContainerFamilyName@Container@helium@@0V?$map@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@@std@@A; std::map<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation> helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName
0x18007024f  test    al, al
0x180070251  cmovnz  r9, [rsp+788h+var_6B8]
0x18007025a  lea     r14, [rsi+20h]
0x18007025e  mov     rdx, r14
0x180070261  cmp     r9, cs:?s_mapDiagnosticInformationByUserSidAndContainerFamilyName@Container@helium@@0V?$map@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@@std@@A; std::map<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation> helium::Container::s_mapDiagnosticInformationByUserSidAndContainerFamilyName
0x180070268  jnz     short loc_1800702D9
0x18007026a  mov     [rsi+88h], r12d
0x180070271  lea     rcx, [rsp+788h+var_638]
0x180070279  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007027e  mov     [rsp+788h+var_618], r12
0x180070286  mov     [rsp+788h+var_610], r12d
0x18007028e  mov     [rsp+788h+var_5FC], r12b
0x180070296  mov     [rsp+788h+var_5F8], r12
0x18007029e  mov     [rsp+788h+var_5F0], r12
0x1800702a6  mov     [rsp+788h+var_5D4], r12b
0x1800702ae  lea     r9, [rsp+788h+var_638]
0x1800702b6  mov     r8, rdi
0x1800702b9  lea     rdx, [rsp+788h+var_708]
0x1800702c1  call    ??$emplace@AEBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@?$_Tree@V?$_Tmap_traits@UDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@U?$less@UDiagnosticInformationKey@Container@helium@@@std@@V?$allocator@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUDiagnosticInformationKey@Container@helium@@UDiagnosticInformation@23@@std@@@std@@@std@@@std@@_N@1@AEBUDiagnosticInformationKey@Container@helium@@$$QEAUDiagnosticInformation@45@@Z; std::_Tree<std::_Tmap_traits<helium::Container::DiagnosticInformationKey,helium::Container::DiagnosticInformation,std::less<helium::Container::DiagnosticInformationKey>,std::allocator<std::pair<helium::Container::DiagnosticInformationKey const,helium::Container::DiagnosticInformation>>,0>>::emplace<helium::Container::DiagnosticInformationKey const &,helium::Container::DiagnosticInformation>(helium::Container::DiagnosticInformationKey const &,helium::Container::DiagnosticInformation &&)
0x1800702c6  nop
0x1800702c7  lea     rcx, [rsp+788h+var_638]; void *
0x1800702cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800702d4  mov     rdi, r14
0x1800702d7  jmp     short loc_180070356
0x1800702d9  lea     rcx, [r9+60h]
0x1800702dd  cmp     qword ptr [r14+18h], 7
0x1800702e2  jbe     short loc_1800702E7
0x1800702e4  mov     rdx, [r14]
0x1800702e7  mov     r8, [rcx+10h]
0x1800702eb  cmp     qword ptr [rcx+18h], 7
0x1800702f0  jbe     short loc_1800702F5
0x1800702f2  mov     rcx, [rcx]
0x1800702f5  mov     rdi, r14
0x1800702f8  cmp     r8, [r14+10h]
0x1800702fc  jnz     short loc_180070321
0x1800702fe  test    r8, r8
0x180070301  jz      short loc_180070318
0x180070303  sub     rcx, rdx
0x180070306  movzx   eax, word ptr [rcx+rdx]
0x18007030a  cmp     ax, [rdx]
0x18007030d  jnz     short loc_180070321
0x18007030f  add     rdx, 2
0x180070313  sub     r8, r15
0x180070316  jnz     short loc_180070306
0x180070318  mov     eax, [r9+80h]
0x18007031f  jmp     short loc_18007034D
0x180070321  mov     rdx, rdi
0x180070324  lea     rcx, [rsp+788h+var_6A8]; void *
0x18007032c  cmp     [rsp+788h+var_688], r12b
0x180070334  jz      short loc_18007033D
0x180070336  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007033b  jmp     short loc_18007034A
0x18007033d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180070342  mov     [rsp+788h+var_688], r15b
0x18007034a  mov     eax, r12d
0x18007034d  mov     rcx, rsi
0x180070350  mov     [rcx+88h], eax
0x180070356  test    rbx, rbx
0x180070359  jz      short loc_18007036B
0x18007035b  mov     rcx, rbx; SRWLock
0x18007035e  call    cs:__imp_ReleaseSRWLockExclusive
0x180070365  nop     dword ptr [rax+rax+00h]
0x18007036a  nop
0x18007036b  mov     rdx, rsi; Src
0x18007036e  lea     rcx, [rsp+788h+SourceString]; void *
0x180070376  call    ?ContainerPath@helium@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; helium::ContainerPath(std::wstring const &)
0x18007037b  nop
0x18007037c  xorps   xmm0, xmm0
0x18007037f  movups  xmmword ptr [rsp+788h+DestinationString.Length], xmm0
0x180070387  lea     rdx, [rsp+788h+SourceString]
0x18007038f  cmp     [rsp+788h+var_60], 7
0x180070398  cmova   rdx, [rsp+788h+SourceString]; SourceString
0x1800703a1  lea     rcx, [rsp+788h+DestinationString]; DestinationString
0x1800703a9  call    cs:__imp_RtlInitUnicodeString
0x1800703b0  nop     dword ptr [rax+rax+00h]
0x1800703b5  mov     [rsp+788h+hMem], r12
0x1800703ba  lea     rax, [rsp+788h+hMem]
0x1800703bf  mov     [rsp+788h+var_680], rax
0x1800703c7  mov     [rsp+788h+SecurityDescriptor], r12
0x1800703cf  mov     [rsp+788h+var_670], r15b
0x1800703d7  mov     r12, [rsp+788h]
0x1800703df  xor     r9d, r9d; SecurityDescriptorSize
0x1800703e2  lea     r8, [rsp+788h+SecurityDescriptor]; SecurityDescriptor
0x1800703ea  mov     edx, r15d; StringSDRevision
0x1800703ed  lea     rcx, aOSygSydA0x001f; "O:SYG:SYD:(A;;0x001F003F;;;SY)(A;;0x001"...
0x1800703f4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800703fb  nop     dword ptr [rax+rax+00h]
0x180070400  test    eax, eax
0x180070402  jz      loc_180070B7E
0x180070408  lea     rcx, [rsp+788h+var_680]
0x180070410  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180070415  xor     r12d, r12d
0x180070418  mov     qword ptr [rsp+788h+ObjectAttributes.Length], 30h ; '0'
0x180070424  mov     qword ptr [rsp+788h+ObjectAttributes.Attributes], 10h
0x180070430  mov     [rsp+788h+ObjectAttributes.RootDirectory], r12
0x180070438  lea     rax, [rsp+788h+DestinationString]
0x180070440  mov     [rsp+788h+ObjectAttributes.ObjectName], rax
0x180070448  mov     rax, [rsp+788h+hMem]
0x18007044d  mov     [rsp+788h+ObjectAttributes.SecurityDescriptor], rax
0x180070455  mov     [rsp+788h+ObjectAttributes.SecurityQualityOfService], r12
0x18007045d  mov     [rsp+788h+hObject], r12
0x180070462  mov     r13d, [rsp+788h+var_6E8]
0x18007046a  or      r13d, r15d
0x18007046d  mov     [rsp+788h+var_730], r13d
0x180070472  lea     rcx, [rsp+788h+var_708]
0x18007047a  call    ?Take@ScopedPrivileges@@SA?AU1@K@Z; ScopedPrivileges::Take(ulong)
0x18007047f  nop
0x180070480  lea     rax, [rsp+788h+hObject]
0x180070485  mov     [rsp+788h+JobHandle], rax
0x18007048d  mov     [rsp+788h+JobHandle+8], r12
0x180070495  mov     byte ptr [rsp+788h+var_6B8], r15b
0x18007049d  lea     r8, [rsp+788h+ObjectAttributes]; ObjectAttributes
0x1800704a5  mov     edx, 1F003Fh; DesiredAccess
0x1800704aa  lea     rcx, [rsp+788h+JobHandle+8]; JobHandle
0x1800704b2  call    cs:__imp_NtCreateJobObject
0x1800704b9  nop     dword ptr [rax+rax+00h]
0x1800704be  mov     rcx, [rsp+788h]; this
0x1800704c6  test    eax, eax
0x1800704c8  js      loc_180070B93
0x1800704ce  lea     rcx, [rsp+788h+JobHandle]
0x1800704d6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800704db  nop
0x1800704dc  lea     rcx, [rsp+788h+var_708]; this
0x1800704e4  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x1800704e9  nop
0x1800704ea  mov     rcx, [rsp+788h+hMem]; hMem
0x1800704ef  test    rcx, rcx
0x1800704f2  jz      short loc_180070501
0x1800704f4  call    cs:__imp_LocalFree
0x1800704fb  nop     dword ptr [rax+rax+00h]
0x180070500  nop
0x180070501  lea     rcx, [rsp+788h+SourceString]; void *
0x180070509  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007050e  lea     r12, [rsi+90h]
0x180070515  lea     rdx, [rsp+788h+hObject]
0x18007051a  mov     rcx, r12
0x18007051d  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180070522  and     r13d, 0FFFFFFFEh
0x180070526  mov     rcx, [rsp+788h+hObject]; hObject
0x18007052b  lea     rax, [rcx-1]
0x18007052f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180070533  ja      short loc_180070541
0x180070535  call    cs:__imp_CloseHandle
0x18007053c  nop     dword ptr [rax+rax+00h]
0x180070541  mov     qword ptr [rsp+788h+DestinationString.Length], rsi
0x180070549  mov     byte ptr [rsp+788h+DestinationString.Buffer], r15b
0x180070551  mov     [rsp+788h+var_748], r15d
0x180070556  mov     rcx, [rsp+788h+var_718]
0x18007055b  lea     rax, [rcx+0F0h]
0x180070562  add     rcx, 30h ; '0'
0x180070566  mov     [rsp+788h+var_750], rax
0x18007056b  mov     eax, dword ptr [rsp+788h+var_6E0]
0x180070572  mov     [rsp+788h+var_758], eax
0x180070576  mov     al, [rsi+40h]
0x180070579  mov     [rsp+788h+var_760], al
0x18007057d  mov     qword ptr [rsp+788h+var_768], rcx; int
0x180070582  mov     r9, rdi
0x180070585  mov     r8, rsi
0x180070588  mov     rdx, [rsp+788h+var_740]
0x18007058d  lea     rcx, [rsp+788h+var_2D8]
0x180070595  call    ?GenerateDescription@helium@@YA?AUContainerDescription@1@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBUHivePaths@OfflineRegistry@@_NW4ContainerType@1@AEBV?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@4@@Z; helium::GenerateDescription(void *,std::wstring const &,std::wstring const &,OfflineRegistry::HivePaths const &,bool,helium::ContainerType,std::vector<WriteVirtualization::RegistryExclusion> const &)
0x18007059a  nop
0x18007059b  mov     [rsp+788h+var_748], 2
0x1800705a3  lea     rdx, [rsp+788h+var_2D8]; struct helium::ContainerDescription *
0x1800705ab  mov     rcx, [r12]; retstr
0x1800705af  call    ?CreateHeliumContainer@Container@helium@@CAXPEAXAEBUContainerDescription@2@@Z; helium::Container::CreateHeliumContainer(void *,helium::ContainerDescription const &)
0x1800705b4  mov     [rsp+788h+var_748], 3
0x1800705bc  mov     rdi, [r12]
0x1800705c0  mov     [rsp+788h+var_6E0], rdi
0x1800705c8  lea     rdx, aConfigurevfs; "ConfigureVfs"
0x1800705cf  lea     rcx, [rsp+788h+var_578]
0x1800705d7  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800705dc  lea     rax, ??_7ConfigureVfs@DesktopAppXProvider@@6B@; const DesktopAppXProvider::ConfigureVfs::`vftable'
0x1800705e3  mov     [rsp+788h+var_578], rax
0x1800705eb  lea     rcx, [rsp+788h+var_578]; this
0x1800705f3  call    ?StartActivity@ConfigureVfs@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::ConfigureVfs::StartActivity(void)
0x1800705f8  nop
0x1800705f9  and     [rsp+788h+hObject], 0
0x1800705ff  or      r13d, 2
0x180070603  mov     [rsp+788h+var_730], r13d
0x180070608  mov     rcx, [rsp+788h+var_718]
0x18007060d  mov     rax, [rcx+8]
0x180070611  cmp     [rcx], rax
0x180070614  jnz     short loc_180070620
0x180070616  xor     r13d, r13d
0x180070619  xor     r12d, r12d
0x18007061c  xor     edi, edi
0x18007061e  jmp     short loc_18007065F
0x180070620  mov     r9, [rsp+788h+var_740]
0x180070625  mov     r8, rcx
0x180070628  mov     rdx, rdi
0x18007062b  lea     rcx, [rsp+788h+hMem]
0x180070630  call    ?ApplyMappings@VfsProvider@DesktopAppXVFS@@SA?AV12@PEAXAEBV?$vector@UMapping@DesktopAppXVFS@@V?$allocator@UMapping@DesktopAppXVFS@@@std@@@std@@0@Z; DesktopAppXVFS::VfsProvider::ApplyMappings(void *,std::vector<DesktopAppXVFS::Mapping> const &,void *)
0x180070635  mov     rdi, [rax]
0x180070638  and     qword ptr [rax], 0
0x18007063c  mov     [rsp+788h+hObject], rdi
0x180070641  mov     r13, rdi
0x180070644  mov     r12, rdi
0x180070647  mov     rcx, [rsp+788h+hMem]
0x18007064c  test    rcx, rcx
0x18007064f  jz      short loc_18007065F
0x180070651  mov     rax, [rcx]
0x180070654  mov     edx, r15d
0x180070657  mov     rax, [rax]
0x18007065a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007065f  mov     rcx, [rsp+788h+var_718]
0x180070664  mov     rax, [rcx+20h]
0x180070668  cmp     [rcx+18h], rax
  ... truncated ...
```
