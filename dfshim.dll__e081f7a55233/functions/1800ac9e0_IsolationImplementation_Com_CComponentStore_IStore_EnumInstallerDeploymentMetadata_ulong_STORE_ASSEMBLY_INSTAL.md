# IsolationImplementation::Com::CComponentStore::IStore_EnumInstallerDeploymentMetadata(ulong,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,IReferenceAppId *,_GUID const &,IUnknown * *)

- ea: `0x1800ac9e0`
- end: `0x1800ad1ae`
- name: `?IStore_EnumInstallerDeploymentMetadata@CComponentStore@Com@IsolationImplementation@@IEAAJKPEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@PEAUIReferenceAppId@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `1998`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *, struct IReferenceAppId *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800aa0a0`

## callees

- `0x180006991`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012538`
- `0x180012acc`
- `0x180012b1c`
- `0x180012b38`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800307e0`
- `0x180031b3c`
- `0x180037464`
- `0x180039c1c`
- `0x18004f2dc`
- `0x1800ac9e0`
- `0x18010b460`
- `0x18010bb84`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aca7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800acad0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800acb24`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800acd04`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aca7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800acad0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800acb24`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800acd04`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aca44`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800acd60`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800acef9`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aca44`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800acd60`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800acef9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acc19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acc73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acdf1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ace4b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acf8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acfe4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad0f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad14f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acc19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acc73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acdf1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ace4b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acf8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800acfe4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad0f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad14f`

## string_xrefs

- `0x1800acbaf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800acd8d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800acf26`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ad098`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800aca04`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800acb9a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800acd69`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800acf02`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ad07e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_EnumInstallerDeploymentMetadata(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *a3,
        struct IReferenceAppId *a4,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  int v10; // eax
  const struct Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ **v11; // r9
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // eax
  HANDLE v15; // rbx
  unsigned int v16; // r14d
  HANDLE v17; // rbx
  HANDLE v18; // rbx
  int v19; // eax
  struct Windows::Isolation::Rtl::_REFERENCE_APPID *v20; // r8
  int v21; // r9d
  __int64 v22; // r10
  unsigned int *v23; // r11
  signed int v24; // ecx
  __int64 v25; // r10
  unsigned int *v26; // r11
  signed int v27; // ecx
  void (__fastcall *v28)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v30; // rbx
  HANDLE v31; // rbx
  int v32; // esi
  int v33; // eax
  unsigned int v34; // edi
  int v35; // edx
  __int64 v36; // r10
  unsigned int *v37; // r11
  signed int v38; // ecx
  __int64 v39; // r10
  unsigned int *v40; // r11
  signed int v41; // ecx
  void (__fastcall *v42)(LPVOID *); // rax
  HANDLE v43; // rax
  LPVOID *v44; // rbx
  int v45; // eax
  unsigned int v46; // edi
  int v47; // edx
  __int64 v48; // r10
  unsigned int *v49; // r11
  signed int v50; // ecx
  __int64 v51; // r10
  unsigned int *v52; // r11
  signed int v53; // ecx
  void (__fastcall *v54)(LPVOID *); // rax
  HANDLE v55; // rax
  LPVOID *v56; // rbx
  int v57; // eax
  int v58; // r9d
  __int64 v59; // r10
  unsigned int *v60; // r11
  signed int v61; // ecx
  __int64 v62; // r10
  unsigned int *v63; // r11
  signed int v64; // ecx
  unsigned int v66; // [rsp+20h] [rbp-A9h]
  unsigned int v67; // [rsp+20h] [rbp-A9h]
  const char *v68; // [rsp+30h] [rbp-99h] BYREF
  int v69; // [rsp+38h] [rbp-91h]
  unsigned int v70; // [rsp+40h] [rbp-89h]
  LPVOID lpMem[2]; // [rsp+48h] [rbp-81h] BYREF
  struct IReferenceAppId *v72; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v73[2]; // [rsp+60h] [rbp-69h] BYREF
  HANDLE hMutex; // [rsp+70h] [rbp-59h] BYREF
  __int16 v75; // [rsp+78h] [rbp-51h]
  _BYTE v76[64]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v77[10]; // [rsp+C0h] [rbp-9h] BYREF

  v70 = -2147023537;
  v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
  hMutex = 0;
  v75 = 0;
  v10 = StoreLock::Lock((StoreLock *)&hMutex);
  v12 = v10;
  if ( v10 < 0 )
  {
    if ( v10 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x508,
      v12,
      v66);
    v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
    v15 = hMutex;
    v16 = v14;
    if ( hMutex )
    {
      if ( (_BYTE)v75 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v75) = 0;
      }
      CloseHandle_0(v15);
      hMutex = 0;
    }
LABEL_8:
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
    return v16;
  }
  if ( a6 )
    *a6 = 0;
  if ( (a2 & 0xFFFFFFFC) != 0 )
  {
    v17 = hMutex;
    v69 = 1296;
    if ( hMutex )
    {
      if ( (_BYTE)v75 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v75) = 0;
      }
      CloseHandle_0(v17);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v68);
    return v70;
  }
  if ( !a3 )
  {
    v69 = 1297;
LABEL_19:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v68);
    v18 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v75 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v75) = 0;
      }
      CloseHandle_0(v18);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
    return v70;
  }
  if ( !a6 )
  {
    v69 = 1298;
    goto LABEL_19;
  }
  *(_QWORD *)v73 = 0;
  lpMem[1] = lpMem;
  v77[0] = 0;
  lpMem[0] = lpMem;
  v72 = 0;
  v19 = IsolationImplementation::Com::ConvertIn(
          (IsolationImplementation::Com *)lpMem,
          a3,
          (const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *)v77,
          v11);
  v16 = v19;
  if ( v19 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x51A,
      v19,
      v21);
    a4 = 0;
    if ( v72 )
    {
      v70 = -1073741595;
      v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppId,CRefAppIdCD,CRefAppIdTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v72) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v23 + 4))(*v23, v22);
        v24 = 0;
      }
      else
      {
        v69 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
        v24 = v70;
      }
      if ( v24 < 0 )
        RaiseException(v24, 1u, 0, 0);
      v72 = 0;
    }
    if ( *(_QWORD *)v73 )
    {
      v70 = -1073741595;
      v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v73) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v26 + 4))(*v26, v25);
        v27 = 0;
      }
      else
      {
        v69 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
        v27 = v70;
      }
      if ( v27 < 0 )
        RaiseException(v27, 1u, 0, 0);
      *(_QWORD *)v73 = 0;
    }
    while ( 1 )
    {
      v30 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v30 == lpMem )
        break;
      v28 = (void (__fastcall *)(LPVOID *))v30[2];
      if ( v28 )
        v28(v30 + 3);
      ProcessHeap_0 = GetProcessHeap_0();
      HeapFree_0(ProcessHeap_0, 0, v30);
    }
LABEL_48:
    v31 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v75 != (_BYTE)a4 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v75) = (_BYTE)a4;
      }
      CloseHandle_0(v31);
      hMutex = a4;
    }
    goto LABEL_8;
  }
  v32 = a2 & 1 | 2;
  if ( (a2 & 2) == 0 )
    v32 = a2 & 1;
  if ( a4 )
  {
    v33 = IsolationImplementation::Com::ConvertIn(a4, (struct IReferenceAppId *)&v72, v20);
    a4 = 0;
    v34 = v33;
    if ( v33 < 0 )
    {
      if ( v33 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x524,
        v34,
        v66);
      v16 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v34, v35);
      if ( v72 )
      {
        v70 = -1073741595;
        v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppId,CRefAppIdCD,CRefAppIdTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v72) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v37 + 4))(*v37, v36);
          v38 = 0;
        }
        else
        {
          v69 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
          v38 = v70;
        }
        if ( v38 < 0 )
          RaiseException(v38, 1u, 0, 0);
        v72 = 0;
      }
      if ( *(_QWORD *)v73 )
      {
        v70 = -1073741595;
        v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v73) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v40 + 4))(*v40, v39);
          v41 = 0;
        }
        else
        {
          v69 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
          v41 = v70;
        }
        if ( v41 < 0 )
          RaiseException(v41, 1u, 0, 0);
        *(_QWORD *)v73 = 0;
      }
      while ( 1 )
      {
        v44 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v44 == lpMem )
          break;
        v42 = (void (__fastcall *)(LPVOID *))v44[2];
        if ( v42 )
          v42(v44 + 3);
        v43 = GetProcessHeap_0();
        HeapFree_0(v43, 0, v44);
      }
      goto LABEL_48;
    }
  }
  v45 = RtlEnumerateComponentStoreMetadataDeployments(v32, *((_QWORD *)this + 2), v77[0], (_DWORD)v72, (__int64)v73);
  v46 = v45;
  if ( v45 < 0 )
  {
    if ( v45 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x530,
      v46,
      v67);
    v16 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v46, v47);
    if ( v72 )
    {
      v70 = -1073741595;
      v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppId,CRefAppIdCD,CRefAppIdTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v72) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v49 + 4))(*v49, v48);
        v50 = (int)a4;
      }
      else
      {
        v69 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
        v50 = v70;
      }
      if ( v50 < 0 )
        RaiseException(v50, 1u, 0, 0);
      v72 = a4;
    }
    if ( *(_QWORD *)v73 )
    {
      v70 = -1073741595;
      v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v73) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v52 + 4))(*v52, v51);
        v53 = (int)a4;
      }
      else
      {
        v69 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
        v53 = v70;
      }
      if ( v53 < 0 )
        RaiseException(v53, 1u, 0, 0);
      *(_QWORD *)v73 = a4;
    }
    while ( 1 )
    {
      v56 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v56 == lpMem )
        break;
      v54 = (void (__fastcall *)(LPVOID *))v56[2];
      if ( v54 )
        v54(v56 + 3);
      v55 = GetProcessHeap_0();
      HeapFree_0(v55, 0, v56);
    }
    goto LABEL_48;
  }
  v57 = IsolationImplementation::Com::CopyOut(*(_QWORD *)v73, a5, a6);
  v16 = v57;
  if ( v57 >= 0 )
    v16 = (unsigned int)a4;
  else
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x532,
      v57,
      v58);
  if ( v72 )
  {
    v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    v70 = -1073741595;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppId,CRefAppIdCD,CRefAppIdTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v72) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v60 + 4))(*v60, v59);
      v61 = (int)a4;
    }
    else
    {
      v69 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
      v61 = v70;
    }
    if ( v61 < 0 )
      RaiseException(v61, 1u, 0, 0);
    v72 = a4;
  }
  if ( *(_QWORD *)v73 )
  {
    v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    v70 = -1073741595;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v73) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v63 + 4))(*v63, v62);
      v64 = (int)a4;
    }
    else
    {
      v69 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
      v64 = v70;
    }
    if ( v64 < 0 )
      RaiseException(v64, 1u, 0, 0);
    *(_QWORD *)v73 = a4;
  }
  Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
  StoreLock::~StoreLock((StoreLock *)&hMutex);
  return v16;
}

```

## disassembly

```asm
0x1800ac9e0  push    rbp
0x1800ac9e2  push    rbx
0x1800ac9e3  push    rsi
0x1800ac9e4  push    rdi
0x1800ac9e5  push    r12
0x1800ac9e7  push    r13
0x1800ac9e9  push    r14
0x1800ac9eb  push    r15
0x1800ac9ed  lea     rbp, [rsp-0Fh]
0x1800ac9f2  sub     rsp, 0D8h
0x1800ac9f9  mov     r13, rcx
0x1800ac9fc  mov     [rsp+110h+var_D0], 8007054Fh
0x1800aca04  lea     r14, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800aca0b  mov     r12, r9
0x1800aca0e  lea     rcx, [rbp+47h+var_90]; this
0x1800aca12  mov     [rsp+110h+var_E0], r14
0x1800aca17  mov     rsi, r8
0x1800aca1a  mov     edi, edx
0x1800aca1c  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800aca21  xor     r15d, r15d
0x1800aca24  lea     rcx, [rbp+47h+hMutex]; this
0x1800aca28  mov     [rbp+47h+hMutex], r15
0x1800aca2c  mov     [rbp+47h+var_98], r15w
0x1800aca31  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800aca36  mov     ebx, eax
0x1800aca38  test    eax, eax
0x1800aca3a  jns     short loc_1800ACAA2
0x1800aca3c  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800aca42  jnz     short loc_1800ACA4A
0x1800aca44  call    cs:__imp_DebugBreak
0x1800aca4a  mov     r9d, ebx; int
0x1800aca4d  lea     rcx, aStatusPropagat; "Status propagated"
0x1800aca54  mov     r8d, 508h; char *
0x1800aca5a  mov     rdx, r14; char *
0x1800aca5d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800aca62  mov     ecx, ebx; this
0x1800aca64  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800aca69  mov     rbx, [rbp+47h+hMutex]
0x1800aca6d  mov     r14d, eax
0x1800aca70  test    rbx, rbx
0x1800aca73  jz      short loc_1800ACA94
0x1800aca75  cmp     byte ptr [rbp+47h+var_98], r15b
0x1800aca79  jz      short loc_1800ACA88
0x1800aca7b  mov     rcx, rbx; hMutex
0x1800aca7e  call    cs:__imp_ReleaseMutex
0x1800aca84  mov     byte ptr [rbp+47h+var_98], r15b
0x1800aca88  mov     rcx, rbx; hObject
0x1800aca8b  call    CloseHandle_0
0x1800aca90  mov     [rbp+47h+hMutex], r15
0x1800aca94  lea     rcx, [rbp+47h+var_90]; this
0x1800aca98  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800aca9d  jmp     loc_1800AD16C
0x1800acaa2  mov     rbx, [rbp+47h+arg_28]
0x1800acaa6  test    rbx, rbx
0x1800acaa9  jz      short loc_1800ACAAE
0x1800acaab  mov     [rbx], r15
0x1800acaae  test    edi, 0FFFFFFFCh
0x1800acab4  jz      short loc_1800ACAFB
0x1800acab6  mov     rbx, [rbp+47h+hMutex]
0x1800acaba  mov     [rsp+110h+var_D8], 510h
0x1800acac2  test    rbx, rbx
0x1800acac5  jz      short loc_1800ACAE6
0x1800acac7  cmp     byte ptr [rbp+47h+var_98], r15b
0x1800acacb  jz      short loc_1800ACADA
0x1800acacd  mov     rcx, rbx; hMutex
0x1800acad0  call    cs:__imp_ReleaseMutex
0x1800acad6  mov     byte ptr [rbp+47h+var_98], r15b
0x1800acada  mov     rcx, rbx; hObject
0x1800acadd  call    CloseHandle_0
0x1800acae2  mov     [rbp+47h+hMutex], r15
0x1800acae6  lea     rcx, [rbp+47h+var_90]; this
0x1800acaea  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800acaef  lea     rcx, [rsp+110h+var_E0]
0x1800acaf4  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800acaf9  jmp     short loc_1800ACB43
0x1800acafb  test    rsi, rsi
0x1800acafe  jnz     short loc_1800ACB4D
0x1800acb00  mov     [rsp+110h+var_D8], 511h
0x1800acb08  lea     rcx, [rsp+110h+var_E0]
0x1800acb0d  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800acb12  mov     rbx, [rbp+47h+hMutex]
0x1800acb16  test    rbx, rbx
0x1800acb19  jz      short loc_1800ACB3A
0x1800acb1b  cmp     byte ptr [rbp+47h+var_98], r15b
0x1800acb1f  jz      short loc_1800ACB2E
0x1800acb21  mov     rcx, rbx; hMutex
0x1800acb24  call    cs:__imp_ReleaseMutex
0x1800acb2a  mov     byte ptr [rbp+47h+var_98], r15b
0x1800acb2e  mov     rcx, rbx; hObject
0x1800acb31  call    CloseHandle_0
0x1800acb36  mov     [rbp+47h+hMutex], r15
0x1800acb3a  lea     rcx, [rbp+47h+var_90]; this
0x1800acb3e  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800acb43  mov     r14d, [rsp+110h+var_D0]
0x1800acb48  jmp     loc_1800AD16C
0x1800acb4d  test    rbx, rbx
0x1800acb50  jnz     short loc_1800ACB5C
0x1800acb52  mov     [rsp+110h+var_D8], 512h
0x1800acb5a  jmp     short loc_1800ACB08
0x1800acb5c  lea     rax, [rsp+110h+lpMem]
0x1800acb61  mov     qword ptr [rbp+47h+var_B0], r15
0x1800acb65  mov     [rbp+47h+var_C0], rax
0x1800acb69  lea     r8, [rbp+47h+var_50]; struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *
0x1800acb6d  lea     rax, [rsp+110h+lpMem]
0x1800acb72  mov     [rbp+47h+var_50], r15
0x1800acb76  mov     rdx, rsi; struct _RTL_ALLOCATION_LIST *
0x1800acb79  mov     [rsp+110h+lpMem], rax
0x1800acb7e  lea     rcx, [rsp+110h+lpMem]; this
0x1800acb83  mov     [rbp+47h+var_B8], r15
0x1800acb87  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@AEAPEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const * &)
0x1800acb8c  mov     r14d, eax
0x1800acb8f  test    eax, eax
0x1800acb91  jns     loc_1800ACD1F
0x1800acb97  mov     r8d, eax; int
0x1800acb9a  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800acba1  mov     edx, 51Ah; char *
0x1800acba6  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800acbab  mov     r10, [rbp+47h+var_B8]
0x1800acbaf  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800acbb6  xor     r12d, r12d
0x1800acbb9  mov     ebx, 0C00000E5h
0x1800acbbe  mov     esi, 124h
0x1800acbc3  mov     r15d, 1
0x1800acbc9  test    r10, r10
0x1800acbcc  jz      short loc_1800ACC23
0x1800acbce  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_REFERENCE_APPID@Rtl@Isolation@Windows@@VCRefAppId@@VCRefAppIdCD@@VCRefAppIdTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppId,CRefAppIdCD,CRefAppIdTraits>::ms_ptti
0x1800acbd5  mov     [rsp+110h+var_D0], ebx
0x1800acbd9  mov     [rsp+110h+var_E0], rdi
0x1800acbde  test    r11, r11
0x1800acbe1  jz      loc_1800ACC7F
0x1800acbe7  mov     rdx, r11
0x1800acbea  mov     rcx, r10
0x1800acbed  call    RtlIsTypeSafeHandleValid
0x1800acbf2  test    al, al
0x1800acbf4  jz      loc_1800ACC7F
0x1800acbfa  mov     ecx, [r11]
0x1800acbfd  mov     rdx, r10
0x1800acc00  mov     rax, [r11+20h]
0x1800acc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc09  mov     ecx, r12d; dwExceptionCode
0x1800acc0c  test    ecx, ecx
0x1800acc0e  jns     short loc_1800ACC1F
0x1800acc10  xor     r9d, r9d; lpArguments
0x1800acc13  xor     r8d, r8d; nNumberOfArguments
0x1800acc16  mov     edx, r15d; dwExceptionFlags
0x1800acc19  call    cs:__imp_RaiseException
0x1800acc1f  mov     [rbp+47h+var_B8], r12
0x1800acc23  mov     r10, qword ptr [rbp+47h+var_B0]
0x1800acc27  test    r10, r10
0x1800acc2a  jz      loc_1800ACCCE
0x1800acc30  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentEnumerator@@VCComponentStoreMetadataDeploymentEnumeratorCD@@VCComponentStoreMetadataDeploymentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
0x1800acc37  mov     [rsp+110h+var_D0], ebx
0x1800acc3b  mov     [rsp+110h+var_E0], rdi
0x1800acc40  test    r11, r11
0x1800acc43  jz      short loc_1800ACC96
0x1800acc45  mov     rdx, r11
0x1800acc48  mov     rcx, r10
0x1800acc4b  call    RtlIsTypeSafeHandleValid
0x1800acc50  test    al, al
0x1800acc52  jz      short loc_1800ACC96
0x1800acc54  mov     ecx, [r11]
0x1800acc57  mov     rdx, r10
0x1800acc5a  mov     rax, [r11+20h]
0x1800acc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc63  mov     ecx, r12d; dwExceptionCode
0x1800acc66  test    ecx, ecx
0x1800acc68  jns     short loc_1800ACC79
0x1800acc6a  xor     r9d, r9d; lpArguments
0x1800acc6d  xor     r8d, r8d; nNumberOfArguments
0x1800acc70  mov     edx, r15d; dwExceptionFlags
0x1800acc73  call    cs:__imp_RaiseException
0x1800acc79  mov     qword ptr [rbp+47h+var_B0], r12
0x1800acc7d  jmp     short loc_1800ACCCE
0x1800acc7f  mov     [rsp+110h+var_D8], esi
0x1800acc83  lea     rcx, [rsp+110h+var_E0]
0x1800acc88  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800acc8d  mov     ecx, [rsp+110h+var_D0]
0x1800acc91  jmp     loc_1800ACC0C
0x1800acc96  mov     [rsp+110h+var_D8], esi
0x1800acc9a  lea     rcx, [rsp+110h+var_E0]
0x1800acc9f  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800acca4  mov     ecx, [rsp+110h+var_D0]
0x1800acca8  jmp     short loc_1800ACC66
0x1800accaa  mov     rax, [rbx+10h]
0x1800accae  test    rax, rax
0x1800accb1  jz      short loc_1800ACCBC
0x1800accb3  lea     rcx, [rbx+18h]
0x1800accb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800accbc  call    GetProcessHeap_0
0x1800accc1  mov     r8, rbx; lpMem
0x1800accc4  xor     edx, edx; dwFlags
0x1800accc6  mov     rcx, rax; hHeap
0x1800accc9  call    HeapFree_0
0x1800accce  mov     rbx, [rsp+110h+lpMem]
0x1800accd3  lea     rcx, [rsp+110h+lpMem]
0x1800accd8  mov     rax, [rbx]
0x1800accdb  mov     [rsp+110h+lpMem], rax
0x1800acce0  mov     [rax+8], rcx
0x1800acce4  lea     rax, [rsp+110h+lpMem]
0x1800acce9  cmp     rbx, rax
0x1800accec  jnz     short loc_1800ACCAA
0x1800accee  mov     rbx, [rbp+47h+hMutex]
0x1800accf2  test    rbx, rbx
0x1800accf5  jz      loc_1800ACA94
0x1800accfb  cmp     byte ptr [rbp+47h+var_98], r12b
0x1800accff  jz      short loc_1800ACD0E
0x1800acd01  mov     rcx, rbx; hMutex
0x1800acd04  call    cs:__imp_ReleaseMutex
0x1800acd0a  mov     byte ptr [rbp+47h+var_98], r12b
0x1800acd0e  mov     rcx, rbx; hObject
0x1800acd11  call    CloseHandle_0
0x1800acd16  mov     [rbp+47h+hMutex], r12
0x1800acd1a  jmp     loc_1800ACA94
0x1800acd1f  mov     eax, edi
0x1800acd21  mov     r15d, 1
0x1800acd27  and     eax, r15d
0x1800acd2a  mov     esi, eax
0x1800acd2c  or      esi, 2
0x1800acd2f  test    dil, 2
0x1800acd33  cmovz   esi, eax
0x1800acd36  test    r12, r12
0x1800acd39  jz      loc_1800ACECB
0x1800acd3f  lea     rdx, [rbp+47h+var_B8]; struct IReferenceAppId *
0x1800acd43  mov     rcx, r12; this
0x1800acd46  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIReferenceAppId@@PEAU_REFERENCE_APPID@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IReferenceAppId *,Windows::Isolation::Rtl::_REFERENCE_APPID *)
0x1800acd4b  xor     r12d, r12d
0x1800acd4e  mov     edi, eax
0x1800acd50  test    eax, eax
0x1800acd52  jns     loc_1800ACECB
0x1800acd58  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800acd5e  jnz     short loc_1800ACD66
0x1800acd60  call    cs:__imp_DebugBreak
0x1800acd66  mov     r9d, edi; int
0x1800acd69  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800acd70  mov     r8d, 524h; char *
0x1800acd76  lea     rcx, aStatusPropagat; "Status propagated"
0x1800acd7d  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800acd82  mov     ecx, edi; this
0x1800acd84  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800acd89  mov     r10, [rbp+47h+var_B8]
0x1800acd8d  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800acd94  mov     r14d, eax
0x1800acd97  mov     ebx, 0C00000E5h
0x1800acd9c  mov     esi, 124h
0x1800acda1  test    r10, r10
0x1800acda4  jz      short loc_1800ACDFB
0x1800acda6  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_REFERENCE_APPID@Rtl@Isolation@Windows@@VCRefAppId@@VCRefAppIdCD@@VCRefAppIdTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_REFERENCE_APPID,CRefAppId,CRefAppIdCD,CRefAppIdTraits>::ms_ptti
0x1800acdad  mov     [rsp+110h+var_D0], ebx
0x1800acdb1  mov     [rsp+110h+var_E0], rdi
0x1800acdb6  test    r11, r11
0x1800acdb9  jz      loc_1800ACE57
0x1800acdbf  mov     rdx, r11
0x1800acdc2  mov     rcx, r10
0x1800acdc5  call    RtlIsTypeSafeHandleValid
0x1800acdca  test    al, al
0x1800acdcc  jz      loc_1800ACE57
0x1800acdd2  mov     ecx, [r11]
0x1800acdd5  mov     rdx, r10
0x1800acdd8  mov     rax, [r11+20h]
0x1800acddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acde1  mov     ecx, r12d; dwExceptionCode
0x1800acde4  test    ecx, ecx
0x1800acde6  jns     short loc_1800ACDF7
0x1800acde8  xor     r9d, r9d; lpArguments
0x1800acdeb  xor     r8d, r8d; nNumberOfArguments
0x1800acdee  mov     edx, r15d; dwExceptionFlags
0x1800acdf1  call    cs:__imp_RaiseException
0x1800acdf7  mov     [rbp+47h+var_B8], r12
0x1800acdfb  mov     r10, qword ptr [rbp+47h+var_B0]
0x1800acdff  test    r10, r10
0x1800ace02  jz      loc_1800ACEA6
0x1800ace08  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentEnumerator@@VCComponentStoreMetadataDeploymentEnumeratorCD@@VCComponentStoreMetadataDeploymentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
0x1800ace0f  mov     [rsp+110h+var_D0], ebx
0x1800ace13  mov     [rsp+110h+var_E0], rdi
0x1800ace18  test    r11, r11
0x1800ace1b  jz      short loc_1800ACE6E
0x1800ace1d  mov     rdx, r11
0x1800ace20  mov     rcx, r10
0x1800ace23  call    RtlIsTypeSafeHandleValid
0x1800ace28  test    al, al
0x1800ace2a  jz      short loc_1800ACE6E
0x1800ace2c  mov     ecx, [r11]
0x1800ace2f  mov     rdx, r10
0x1800ace32  mov     rax, [r11+20h]
0x1800ace36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace3b  mov     ecx, r12d; dwExceptionCode
0x1800ace3e  test    ecx, ecx
0x1800ace40  jns     short loc_1800ACE51
0x1800ace42  xor     r9d, r9d; lpArguments
0x1800ace45  xor     r8d, r8d; nNumberOfArguments
0x1800ace48  mov     edx, r15d; dwExceptionFlags
0x1800ace4b  call    cs:__imp_RaiseException
0x1800ace51  mov     qword ptr [rbp+47h+var_B0], r12
0x1800ace55  jmp     short loc_1800ACEA6
0x1800ace57  mov     [rsp+110h+var_D8], esi
0x1800ace5b  lea     rcx, [rsp+110h+var_E0]
0x1800ace60  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800ace65  mov     ecx, [rsp+110h+var_D0]
0x1800ace69  jmp     loc_1800ACDE4
0x1800ace6e  mov     [rsp+110h+var_D8], esi
  ... truncated ...
```
