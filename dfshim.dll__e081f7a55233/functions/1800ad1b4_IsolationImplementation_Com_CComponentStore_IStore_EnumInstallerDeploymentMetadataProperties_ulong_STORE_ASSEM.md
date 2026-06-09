# IsolationImplementation::Com::CComponentStore::IStore_EnumInstallerDeploymentMetadataProperties(ulong,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,IDefinitionAppId *,_GUID const &,IUnknown * *)

- ea: `0x1800ad1b4`
- end: `0x1800ad86f`
- name: `?IStore_EnumInstallerDeploymentMetadataProperties@CComponentStore@Com@IsolationImplementation@@IEAAJKPEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@PEAUIDefinitionAppId@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `1723`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *, struct IDefinitionAppId *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800aa0b0`

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
- `0x180030508`
- `0x180031b3c`
- `0x180039c1c`
- `0x18003eb10`
- `0x18004f2dc`
- `0x1800ad1b4`
- `0x18010b314`
- `0x18010bcb8`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad26d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad2be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad825`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad26d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad2be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad825`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad217`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad44b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad57e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad217`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad44b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad57e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad3c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad4e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad618`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad721`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad7fe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad3c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad4e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad618`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad721`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ad7fe`

## string_xrefs

- `0x1800ad37b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ad49f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ad5d2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ad6db`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ad7b4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ad1d7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ad341`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ad454`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ad587`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ad6a1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_EnumInstallerDeploymentMetadataProperties(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *a3,
        struct IDefinitionAppId *a4,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  int v10; // eax
  const struct Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ **v11; // r9
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // ebx
  HANDLE v15; // rbx
  HANDLE v16; // rbx
  int v17; // eax
  struct Windows::Isolation::Rtl::_DEFINITION_APPID *v18; // r8
  int v19; // r9d
  __int64 v20; // r10
  unsigned int *v21; // r11
  signed int v22; // ecx
  void (__fastcall *v23)(LPVOID *); // rax
  HANDLE v24; // rax
  LPVOID *v25; // rdi
  int v26; // eax
  int v27; // ecx
  unsigned int v28; // ebx
  int v29; // edx
  __int64 v30; // r10
  unsigned int *v31; // r11
  signed int v32; // ecx
  void (__fastcall *v33)(LPVOID *); // rax
  HANDLE v34; // rax
  LPVOID *v35; // rdi
  int v36; // eax
  unsigned int v37; // ebx
  int v38; // edx
  __int64 v39; // r10
  unsigned int *v40; // r11
  signed int v41; // ecx
  void (__fastcall *v42)(LPVOID *); // rax
  HANDLE v43; // rax
  LPVOID *v44; // rdi
  int v45; // eax
  int v46; // r9d
  __int64 v47; // r10
  unsigned int *v48; // r11
  signed int v49; // ecx
  void (__fastcall *v50)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v52; // rdi
  __int64 v53; // r10
  unsigned int *v54; // r11
  signed int v55; // ecx
  HANDLE v56; // rdi
  unsigned int v58; // [rsp+20h] [rbp-A9h]
  unsigned int v59; // [rsp+20h] [rbp-A9h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v61; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v62[2]; // [rsp+48h] [rbp-81h] BYREF
  const char *v63; // [rsp+50h] [rbp-79h] BYREF
  int v64; // [rsp+58h] [rbp-71h]
  unsigned int v65; // [rsp+60h] [rbp-69h]
  HANDLE hMutex; // [rsp+70h] [rbp-59h] BYREF
  __int16 v67; // [rsp+78h] [rbp-51h]
  _BYTE v68[64]; // [rsp+80h] [rbp-49h] BYREF
  _QWORD v69[10]; // [rsp+C0h] [rbp-9h] BYREF

  v65 = -2147023537;
  v63 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v68);
  hMutex = 0;
  v67 = 0;
  v10 = StoreLock::Lock((StoreLock *)&hMutex);
  v12 = v10;
  if ( v10 >= 0 )
  {
    if ( a6 )
      *a6 = 0;
    if ( a2 )
    {
      v15 = hMutex;
      v64 = 1353;
      if ( hMutex )
      {
        if ( (_BYTE)v67 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v67) = 0;
        }
        CloseHandle_0(v15);
        hMutex = 0;
      }
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v68);
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v63);
    }
    else
    {
      if ( a3 )
      {
        if ( a4 )
        {
          if ( a6 )
          {
            *(_QWORD *)v62 = 0;
            lpMem[1] = lpMem;
            v69[0] = 0;
            lpMem[0] = lpMem;
            v61 = 0;
            v17 = IsolationImplementation::Com::ConvertIn(
                    (IsolationImplementation::Com *)lpMem,
                    a3,
                    (const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *)v69,
                    v11);
            v14 = v17;
            if ( v17 >= 0 )
            {
              v26 = IsolationImplementation::Com::ConvertIn(a4, (struct IDefinitionAppId *)&v61, v18);
              v28 = v26;
              if ( v26 >= 0 )
              {
                v36 = RtlEnumerateComponentStoreMetadataDeploymentProperties(
                        v27,
                        *((_QWORD *)this + 2),
                        v69[0],
                        v61,
                        (__int64)v62);
                v37 = v36;
                if ( v36 >= 0 )
                {
                  v45 = IsolationImplementation::Com::CopyOut(*(_QWORD *)v62, a5, a6);
                  v14 = v45;
                  if ( v45 >= 0 )
                  {
                    v14 = 0;
                    if ( v61 )
                    {
                      RtlCloseDefinitionAppIdHandle();
                      v61 = 0;
                    }
                    if ( *(_QWORD *)v62 )
                    {
                      v65 = -1073741595;
                      v63 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
                        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v62) )
                      {
                        (*((void (__fastcall **)(_QWORD, __int64))v54 + 4))(*v54, v53);
                        v55 = 0;
                      }
                      else
                      {
                        v64 = 292;
                        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v63);
                        v55 = v65;
                      }
                      if ( v55 < 0 )
                        RaiseException(v55, 1u, 0, 0);
                      *(_QWORD *)v62 = 0;
                    }
                    Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
                  }
                  else
                  {
                    Windows::ErrorHandling::COM::ReportErrorPropagation(
                      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                      (const char *)0x55E,
                      v45,
                      v46);
                    if ( v61 )
                    {
                      RtlCloseDefinitionAppIdHandle();
                      v61 = 0;
                    }
                    if ( *(_QWORD *)v62 )
                    {
                      v65 = -1073741595;
                      v63 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
                        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v62) )
                      {
                        (*((void (__fastcall **)(_QWORD, __int64))v48 + 4))(*v48, v47);
                        v49 = 0;
                      }
                      else
                      {
                        v64 = 292;
                        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v63);
                        v49 = v65;
                      }
                      if ( v49 < 0 )
                        RaiseException(v49, 1u, 0, 0);
                      *(_QWORD *)v62 = 0;
                    }
                    while ( 1 )
                    {
                      v52 = (LPVOID *)lpMem[0];
                      lpMem[0] = *(LPVOID *)lpMem[0];
                      *((_QWORD *)lpMem[0] + 1) = lpMem;
                      if ( v52 == lpMem )
                        break;
                      v50 = (void (__fastcall *)(LPVOID *))v52[2];
                      if ( v50 )
                        v50(v52 + 3);
                      ProcessHeap_0 = GetProcessHeap_0();
                      HeapFree_0(ProcessHeap_0, 0, v52);
                    }
                  }
                }
                else
                {
                  if ( v36 == g_NTSTATUS_to_break_on_propagate )
                    DebugBreak();
                  Windows::ErrorHandling::COM::ReportError(
                    (Windows::ErrorHandling::COM *)"Status propagated",
                    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                    (const char *)0x55C,
                    v37,
                    v59);
                  v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v37, v38);
                  if ( v61 )
                  {
                    RtlCloseDefinitionAppIdHandle();
                    v61 = 0;
                  }
                  if ( *(_QWORD *)v62 )
                  {
                    v65 = -1073741595;
                    v63 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
                      && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v62) )
                    {
                      (*((void (__fastcall **)(_QWORD, __int64))v40 + 4))(*v40, v39);
                      v41 = 0;
                    }
                    else
                    {
                      v64 = 292;
                      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v63);
                      v41 = v65;
                    }
                    if ( v41 < 0 )
                      RaiseException(v41, 1u, 0, 0);
                    *(_QWORD *)v62 = 0;
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
                }
              }
              else
              {
                if ( v26 == g_NTSTATUS_to_break_on_propagate )
                  DebugBreak();
                Windows::ErrorHandling::COM::ReportError(
                  (Windows::ErrorHandling::COM *)"Status propagated",
                  "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                  (const char *)0x555,
                  v28,
                  v58);
                v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v28, v29);
                if ( v61 )
                {
                  RtlCloseDefinitionAppIdHandle();
                  v61 = 0;
                }
                if ( *(_QWORD *)v62 )
                {
                  v65 = -1073741595;
                  v63 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                  if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
                    && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v62) )
                  {
                    (*((void (__fastcall **)(_QWORD, __int64))v31 + 4))(*v31, v30);
                    v32 = 0;
                  }
                  else
                  {
                    v64 = 292;
                    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v63);
                    v32 = v65;
                  }
                  if ( v32 < 0 )
                    RaiseException(v32, 1u, 0, 0);
                  *(_QWORD *)v62 = 0;
                }
                while ( 1 )
                {
                  v35 = (LPVOID *)lpMem[0];
                  lpMem[0] = *(LPVOID *)lpMem[0];
                  *((_QWORD *)lpMem[0] + 1) = lpMem;
                  if ( v35 == lpMem )
                    break;
                  v33 = (void (__fastcall *)(LPVOID *))v35[2];
                  if ( v33 )
                    v33(v35 + 3);
                  v34 = GetProcessHeap_0();
                  HeapFree_0(v34, 0, v35);
                }
              }
            }
            else
            {
              Windows::ErrorHandling::COM::ReportErrorPropagation(
                (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
                (const char *)0x554,
                v17,
                v19);
              if ( v61 )
              {
                RtlCloseDefinitionAppIdHandle();
                v61 = 0;
              }
              if ( *(_QWORD *)v62 )
              {
                v65 = -1073741595;
                v63 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
                  && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v62) )
                {
                  (*((void (__fastcall **)(_QWORD, __int64))v21 + 4))(*v21, v20);
                  v22 = 0;
                }
                else
                {
                  v64 = 292;
                  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v63);
                  v22 = v65;
                }
                if ( v22 < 0 )
                  RaiseException(v22, 1u, 0, 0);
                *(_QWORD *)v62 = 0;
              }
              while ( 1 )
              {
                v25 = (LPVOID *)lpMem[0];
                lpMem[0] = *(LPVOID *)lpMem[0];
                *((_QWORD *)lpMem[0] + 1) = lpMem;
                if ( v25 == lpMem )
                  break;
                v23 = (void (__fastcall *)(LPVOID *))v25[2];
                if ( v23 )
                  v23(v25 + 3);
                v24 = GetProcessHeap_0();
                HeapFree_0(v24, 0, v25);
              }
            }
            goto LABEL_103;
          }
          v64 = 1356;
        }
        else
        {
          v64 = 1355;
        }
      }
      else
      {
        v64 = 1354;
      }
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v63);
      v16 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v67 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v67) = 0;
        }
        CloseHandle_0(v16);
        hMutex = 0;
      }
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v68);
    }
    return v65;
  }
  if ( v10 == g_NTSTATUS_to_break_on_propagate )
    DebugBreak();
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"Status propagated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
    (const char *)0x543,
    v12,
    v58);
  v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
LABEL_103:
  v56 = hMutex;
  if ( hMutex )
  {
    if ( (_BYTE)v67 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v67) = 0;
    }
    CloseHandle_0(v56);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v68);
  return v14;
}

```

## disassembly

```asm
0x1800ad1b4  push    rbp
0x1800ad1b6  push    rbx
0x1800ad1b7  push    rsi
0x1800ad1b8  push    rdi
0x1800ad1b9  push    r12
0x1800ad1bb  push    r13
0x1800ad1bd  push    r14
0x1800ad1bf  push    r15
0x1800ad1c1  lea     rbp, [rsp-0Fh]
0x1800ad1c6  sub     rsp, 0D8h
0x1800ad1cd  mov     r13, rcx
0x1800ad1d0  mov     [rbp+47h+var_B0], 8007054Fh
0x1800ad1d7  lea     rdi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad1de  mov     rsi, r9
0x1800ad1e1  lea     rcx, [rbp+47h+var_90]; this
0x1800ad1e5  mov     [rbp+47h+var_C0], rdi
0x1800ad1e9  mov     r14, r8
0x1800ad1ec  mov     r15d, edx
0x1800ad1ef  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800ad1f4  xor     r12d, r12d
0x1800ad1f7  lea     rcx, [rbp+47h+hMutex]; this
0x1800ad1fb  mov     [rbp+47h+hMutex], r12
0x1800ad1ff  mov     [rbp+47h+var_98], r12w
0x1800ad204  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800ad209  mov     ebx, eax
0x1800ad20b  test    eax, eax
0x1800ad20d  jns     short loc_1800AD243
0x1800ad20f  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ad215  jnz     short loc_1800AD21D
0x1800ad217  call    cs:__imp_DebugBreak
0x1800ad21d  mov     r9d, ebx; int
0x1800ad220  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ad227  mov     r8d, 543h; char *
0x1800ad22d  mov     rdx, rdi; char *
0x1800ad230  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ad235  mov     ecx, ebx; this
0x1800ad237  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ad23c  mov     ebx, eax
0x1800ad23e  jmp     loc_1800AD813
0x1800ad243  mov     rdi, [rbp+47h+arg_28]
0x1800ad247  test    rdi, rdi
0x1800ad24a  jz      short loc_1800AD24F
0x1800ad24c  mov     [rdi], r12
0x1800ad24f  test    r15d, r15d
0x1800ad252  jz      short loc_1800AD297
0x1800ad254  mov     rbx, [rbp+47h+hMutex]
0x1800ad258  mov     [rbp+47h+var_B8], 549h
0x1800ad25f  test    rbx, rbx
0x1800ad262  jz      short loc_1800AD283
0x1800ad264  cmp     byte ptr [rbp+47h+var_98], r12b
0x1800ad268  jz      short loc_1800AD277
0x1800ad26a  mov     rcx, rbx; hMutex
0x1800ad26d  call    cs:__imp_ReleaseMutex
0x1800ad273  mov     byte ptr [rbp+47h+var_98], r12b
0x1800ad277  mov     rcx, rbx; hObject
0x1800ad27a  call    CloseHandle_0
0x1800ad27f  mov     [rbp+47h+hMutex], r12
0x1800ad283  lea     rcx, [rbp+47h+var_90]; this
0x1800ad287  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ad28c  lea     rcx, [rbp+47h+var_C0]
0x1800ad290  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ad295  jmp     short loc_1800AD2DD
0x1800ad297  test    r14, r14
0x1800ad29a  jnz     short loc_1800AD2E5
0x1800ad29c  mov     [rbp+47h+var_B8], 54Ah
0x1800ad2a3  lea     rcx, [rbp+47h+var_C0]
0x1800ad2a7  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800ad2ac  mov     rbx, [rbp+47h+hMutex]
0x1800ad2b0  test    rbx, rbx
0x1800ad2b3  jz      short loc_1800AD2D4
0x1800ad2b5  cmp     byte ptr [rbp+47h+var_98], r12b
0x1800ad2b9  jz      short loc_1800AD2C8
0x1800ad2bb  mov     rcx, rbx; hMutex
0x1800ad2be  call    cs:__imp_ReleaseMutex
0x1800ad2c4  mov     byte ptr [rbp+47h+var_98], r12b
0x1800ad2c8  mov     rcx, rbx; hObject
0x1800ad2cb  call    CloseHandle_0
0x1800ad2d0  mov     [rbp+47h+hMutex], r12
0x1800ad2d4  lea     rcx, [rbp+47h+var_90]; this
0x1800ad2d8  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ad2dd  mov     ebx, [rbp+47h+var_B0]
0x1800ad2e0  jmp     loc_1800AD844
0x1800ad2e5  test    rsi, rsi
0x1800ad2e8  jnz     short loc_1800AD2F3
0x1800ad2ea  mov     [rbp+47h+var_B8], 54Bh
0x1800ad2f1  jmp     short loc_1800AD2A3
0x1800ad2f3  test    rdi, rdi
0x1800ad2f6  jnz     short loc_1800AD301
0x1800ad2f8  mov     [rbp+47h+var_B8], 54Ch
0x1800ad2ff  jmp     short loc_1800AD2A3
0x1800ad301  lea     rax, [rsp+110h+lpMem]
0x1800ad306  mov     qword ptr [rsp+110h+var_C8], r12
0x1800ad30b  mov     [rsp+110h+var_D8], rax
0x1800ad310  lea     r8, [rbp+47h+var_50]; struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *
0x1800ad314  lea     rax, [rsp+110h+lpMem]
0x1800ad319  mov     [rbp+47h+var_50], r12
0x1800ad31d  mov     rdx, r14; struct _RTL_ALLOCATION_LIST *
0x1800ad320  mov     [rsp+110h+lpMem], rax
0x1800ad325  lea     rcx, [rsp+110h+lpMem]; this
0x1800ad32a  mov     [rsp+110h+var_D0], r12
0x1800ad32f  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@AEAPEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const * &)
0x1800ad334  mov     ebx, eax
0x1800ad336  test    eax, eax
0x1800ad338  jns     loc_1800AD42C
0x1800ad33e  mov     r8d, eax; int
0x1800ad341  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad348  mov     edx, 554h; char *
0x1800ad34d  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ad352  mov     rcx, [rsp+110h+var_D0]
0x1800ad357  test    rcx, rcx
0x1800ad35a  jz      short loc_1800AD366
0x1800ad35c  call    RtlCloseDefinitionAppIdHandle
0x1800ad361  mov     [rsp+110h+var_D0], r12
0x1800ad366  mov     r10, qword ptr [rsp+110h+var_C8]
0x1800ad36b  test    r10, r10
0x1800ad36e  jz      loc_1800AD407
0x1800ad374  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentPropertyEnumerator@@VCComponentStoreMetadataDeploymentPropertyEnumeratorCD@@VCComponentStoreMetadataDeploymentPropertyEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
0x1800ad37b  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad382  mov     [rbp+47h+var_B0], 0C00000E5h
0x1800ad389  mov     [rbp+47h+var_C0], rax
0x1800ad38d  test    r11, r11
0x1800ad390  jz      short loc_1800AD3CE
0x1800ad392  mov     rdx, r11
0x1800ad395  mov     rcx, r10
0x1800ad398  call    RtlIsTypeSafeHandleValid
0x1800ad39d  test    al, al
0x1800ad39f  jz      short loc_1800AD3CE
0x1800ad3a1  mov     ecx, [r11]
0x1800ad3a4  mov     rdx, r10
0x1800ad3a7  mov     rax, [r11+20h]
0x1800ad3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3b0  mov     ecx, r12d; dwExceptionCode
0x1800ad3b3  test    ecx, ecx
0x1800ad3b5  jns     short loc_1800AD3C7
0x1800ad3b7  xor     r9d, r9d; lpArguments
0x1800ad3ba  xor     r8d, r8d; nNumberOfArguments
0x1800ad3bd  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad3c1  call    cs:__imp_RaiseException
0x1800ad3c7  mov     qword ptr [rsp+110h+var_C8], r12
0x1800ad3cc  jmp     short loc_1800AD407
0x1800ad3ce  mov     [rbp+47h+var_B8], 124h
0x1800ad3d5  lea     rcx, [rbp+47h+var_C0]
0x1800ad3d9  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800ad3de  mov     ecx, [rbp+47h+var_B0]
0x1800ad3e1  jmp     short loc_1800AD3B3
0x1800ad3e3  mov     rax, [rdi+10h]
0x1800ad3e7  test    rax, rax
0x1800ad3ea  jz      short loc_1800AD3F5
0x1800ad3ec  lea     rcx, [rdi+18h]
0x1800ad3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3f5  call    GetProcessHeap_0
0x1800ad3fa  mov     r8, rdi; lpMem
0x1800ad3fd  xor     edx, edx; dwFlags
0x1800ad3ff  mov     rcx, rax; hHeap
0x1800ad402  call    HeapFree_0
0x1800ad407  mov     rdi, [rsp+110h+lpMem]
0x1800ad40c  lea     rcx, [rsp+110h+lpMem]
0x1800ad411  mov     rax, [rdi]
0x1800ad414  mov     [rsp+110h+lpMem], rax
0x1800ad419  mov     [rax+8], rcx
0x1800ad41d  lea     rax, [rsp+110h+lpMem]
0x1800ad422  cmp     rdi, rax
0x1800ad425  jnz     short loc_1800AD3E3
0x1800ad427  jmp     loc_1800AD813
0x1800ad42c  lea     rdx, [rsp+110h+var_D0]; struct IDefinitionAppId *
0x1800ad431  mov     rcx, rsi; this
0x1800ad434  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionAppId@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionAppId *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800ad439  mov     ebx, eax
0x1800ad43b  test    eax, eax
0x1800ad43d  jns     loc_1800AD550
0x1800ad443  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ad449  jnz     short loc_1800AD451
0x1800ad44b  call    cs:__imp_DebugBreak
0x1800ad451  mov     r9d, ebx; int
0x1800ad454  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad45b  mov     r8d, 555h; char *
0x1800ad461  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ad468  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ad46d  mov     ecx, ebx; this
0x1800ad46f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ad474  mov     rcx, [rsp+110h+var_D0]
0x1800ad479  mov     ebx, eax
0x1800ad47b  test    rcx, rcx
0x1800ad47e  jz      short loc_1800AD48A
0x1800ad480  call    RtlCloseDefinitionAppIdHandle
0x1800ad485  mov     [rsp+110h+var_D0], r12
0x1800ad48a  mov     r10, qword ptr [rsp+110h+var_C8]
0x1800ad48f  test    r10, r10
0x1800ad492  jz      loc_1800AD52B
0x1800ad498  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentPropertyEnumerator@@VCComponentStoreMetadataDeploymentPropertyEnumeratorCD@@VCComponentStoreMetadataDeploymentPropertyEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
0x1800ad49f  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad4a6  mov     [rbp+47h+var_B0], 0C00000E5h
0x1800ad4ad  mov     [rbp+47h+var_C0], rax
0x1800ad4b1  test    r11, r11
0x1800ad4b4  jz      short loc_1800AD4F2
0x1800ad4b6  mov     rdx, r11
0x1800ad4b9  mov     rcx, r10
0x1800ad4bc  call    RtlIsTypeSafeHandleValid
0x1800ad4c1  test    al, al
0x1800ad4c3  jz      short loc_1800AD4F2
0x1800ad4c5  mov     ecx, [r11]
0x1800ad4c8  mov     rdx, r10
0x1800ad4cb  mov     rax, [r11+20h]
0x1800ad4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad4d4  mov     ecx, r12d; dwExceptionCode
0x1800ad4d7  test    ecx, ecx
0x1800ad4d9  jns     short loc_1800AD4EB
0x1800ad4db  xor     r9d, r9d; lpArguments
0x1800ad4de  xor     r8d, r8d; nNumberOfArguments
0x1800ad4e1  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad4e5  call    cs:__imp_RaiseException
0x1800ad4eb  mov     qword ptr [rsp+110h+var_C8], r12
0x1800ad4f0  jmp     short loc_1800AD52B
0x1800ad4f2  mov     [rbp+47h+var_B8], 124h
0x1800ad4f9  lea     rcx, [rbp+47h+var_C0]
0x1800ad4fd  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800ad502  mov     ecx, [rbp+47h+var_B0]
0x1800ad505  jmp     short loc_1800AD4D7
0x1800ad507  mov     rax, [rdi+10h]
0x1800ad50b  test    rax, rax
0x1800ad50e  jz      short loc_1800AD519
0x1800ad510  lea     rcx, [rdi+18h]
0x1800ad514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad519  call    GetProcessHeap_0
0x1800ad51e  mov     r8, rdi; lpMem
0x1800ad521  xor     edx, edx; dwFlags
0x1800ad523  mov     rcx, rax; hHeap
0x1800ad526  call    HeapFree_0
0x1800ad52b  mov     rdi, [rsp+110h+lpMem]
0x1800ad530  lea     rcx, [rsp+110h+lpMem]
0x1800ad535  mov     rax, [rdi]
0x1800ad538  mov     [rsp+110h+lpMem], rax
0x1800ad53d  mov     [rax+8], rcx
0x1800ad541  lea     rax, [rsp+110h+lpMem]
0x1800ad546  cmp     rdi, rax
0x1800ad549  jnz     short loc_1800AD507
0x1800ad54b  jmp     loc_1800AD813
0x1800ad550  mov     r9, [rsp+110h+var_D0]
0x1800ad555  lea     rax, [rsp+110h+var_C8]
0x1800ad55a  mov     r8, [rbp+47h+var_50]
0x1800ad55e  mov     rdx, [r13+10h]
0x1800ad562  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x1800ad567  call    RtlEnumerateComponentStoreMetadataDeploymentProperties
0x1800ad56c  mov     ebx, eax
0x1800ad56e  test    eax, eax
0x1800ad570  jns     loc_1800AD683
0x1800ad576  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ad57c  jnz     short loc_1800AD584
0x1800ad57e  call    cs:__imp_DebugBreak
0x1800ad584  mov     r9d, ebx; int
0x1800ad587  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad58e  mov     r8d, 55Ch; char *
0x1800ad594  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ad59b  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ad5a0  mov     ecx, ebx; this
0x1800ad5a2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ad5a7  mov     rcx, [rsp+110h+var_D0]
0x1800ad5ac  mov     ebx, eax
0x1800ad5ae  test    rcx, rcx
0x1800ad5b1  jz      short loc_1800AD5BD
0x1800ad5b3  call    RtlCloseDefinitionAppIdHandle
0x1800ad5b8  mov     [rsp+110h+var_D0], r12
0x1800ad5bd  mov     r10, qword ptr [rsp+110h+var_C8]
0x1800ad5c2  test    r10, r10
0x1800ad5c5  jz      loc_1800AD65E
0x1800ad5cb  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentPropertyEnumerator@@VCComponentStoreMetadataDeploymentPropertyEnumeratorCD@@VCComponentStoreMetadataDeploymentPropertyEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
0x1800ad5d2  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad5d9  mov     [rbp+47h+var_B0], 0C00000E5h
0x1800ad5e0  mov     [rbp+47h+var_C0], rax
0x1800ad5e4  test    r11, r11
0x1800ad5e7  jz      short loc_1800AD625
0x1800ad5e9  mov     rdx, r11
0x1800ad5ec  mov     rcx, r10
0x1800ad5ef  call    RtlIsTypeSafeHandleValid
0x1800ad5f4  test    al, al
0x1800ad5f6  jz      short loc_1800AD625
0x1800ad5f8  mov     ecx, [r11]
0x1800ad5fb  mov     rdx, r10
0x1800ad5fe  mov     rax, [r11+20h]
0x1800ad602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad607  mov     ecx, r12d; dwExceptionCode
0x1800ad60a  test    ecx, ecx
0x1800ad60c  jns     short loc_1800AD61E
0x1800ad60e  xor     r9d, r9d; lpArguments
0x1800ad611  xor     r8d, r8d; nNumberOfArguments
0x1800ad614  lea     edx, [r9+1]; dwExceptionFlags
0x1800ad618  call    cs:__imp_RaiseException
0x1800ad61e  mov     qword ptr [rsp+110h+var_C8], r12
0x1800ad623  jmp     short loc_1800AD65E
0x1800ad625  mov     [rbp+47h+var_B8], 124h
0x1800ad62c  lea     rcx, [rbp+47h+var_C0]
0x1800ad630  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800ad635  mov     ecx, [rbp+47h+var_B0]
0x1800ad638  jmp     short loc_1800AD60A
0x1800ad63a  mov     rax, [rdi+10h]
0x1800ad63e  test    rax, rax
0x1800ad641  jz      short loc_1800AD64C
0x1800ad643  lea     rcx, [rdi+18h]
0x1800ad647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad64c  call    GetProcessHeap_0
  ... truncated ...
```
