# IsolationImplementation::Com::CAppContext::IActContext_ApplicationBasePath(ulong,ushort * *)

- ea: `0x1800a33fc`
- end: `0x1800a3d03`
- name: `?IActContext_ApplicationBasePath@CAppContext@Com@IsolationImplementation@@IEAAJKPEAPEAG@Z`
- size: `2311`
- prototype: `int(IsolationImplementation::Com::CAppContext *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800a2e00`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012538`
- `0x180012820`
- `0x180012910`
- `0x180012b1c`
- `0x180016f8c`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18001b05c`
- `0x1800237b8`
- `0x18002decc`
- `0x18003bef0`
- `0x18003c39c`
- `0x18004f2dc`
- `0x1800a33fc`
- `0x1800f96b8`
- `0x1800fa2a4`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a34a3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a35c7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3aea`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3bb8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a34a3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a35c7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3aea`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3bb8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3523`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3647`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a37e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3a1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3a76`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3b68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3c36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3523`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3647`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a37e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3a1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3a76`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3b68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a3c36`

## string_xrefs

- `0x1800a34db`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a35ff`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a3783`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a3934`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a3991`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a3b22`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a3bf0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a3435`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\appcontext.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CAppContext::IActContext_ApplicationBasePath(
        IsolationImplementation::Com::CAppContext *this,
        __int64 a2,
        unsigned __int16 **a3)
{
  void **v3; // rsi
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // edi
  int v11; // edx
  unsigned int v12; // esi
  void (__fastcall *v13)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v15; // rbx
  int ApplicationContextComponentStore; // eax
  unsigned int v17; // edi
  int v18; // edx
  __int64 v19; // r10
  unsigned int *v20; // r11
  signed int v21; // ecx
  void *v22; // rcx
  void (__fastcall *v23)(LPVOID *); // rax
  HANDLE v24; // rax
  LPVOID *v25; // rbx
  int AllocationListMemory; // edi
  __int64 v27; // rcx
  int v28; // edi
  __int64 v29; // rcx
  int DirectIsolatedFilesystem; // edi
  int v31; // ecx
  char *v32; // r14
  int v33; // edx
  unsigned __int64 v34; // rcx
  __int64 v35; // r10
  unsigned int *v36; // r11
  signed int v37; // ecx
  __int64 v38; // r10
  unsigned int *v39; // r11
  char *v40; // rdi
  __int64 v41; // rcx
  int ComponentStoreLockIdentifier; // ebx
  int v43; // r8d
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rbx
  void *v47; // xmm1_8
  int v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // edi
  int v51; // edx
  unsigned int *v52; // r10
  void *v53; // xmm3_8
  __int128 v54; // xmm2
  unsigned int *v55; // r10
  int v56; // ecx
  __int64 v57; // r10
  unsigned int *v58; // r11
  int v59; // ecx
  void *v60; // rcx
  int v61; // edx
  void *v62; // rcx
  int v63; // edx
  __int64 v64; // r10
  unsigned int *v65; // r11
  int v66; // ecx
  void *v67; // rcx
  void (__fastcall *v68)(LPVOID *); // rax
  HANDLE v69; // rax
  LPVOID *v70; // rbx
  int v71; // eax
  int v72; // r9d
  unsigned int v74; // [rsp+20h] [rbp-A9h]
  const char *v75; // [rsp+30h] [rbp-99h] BYREF
  int v76; // [rsp+38h] [rbp-91h]
  unsigned int v77; // [rsp+40h] [rbp-89h]
  int v78[2]; // [rsp+48h] [rbp-81h] BYREF
  __int128 v79; // [rsp+50h] [rbp-79h] BYREF
  void *v80; // [rsp+60h] [rbp-69h]
  LPVOID lpMem[2]; // [rsp+68h] [rbp-61h] BYREF
  int v82[2]; // [rsp+78h] [rbp-51h] BYREF
  const char *v83; // [rsp+80h] [rbp-49h] BYREF
  int v84; // [rsp+88h] [rbp-41h]
  DWORD dwExceptionCode; // [rsp+90h] [rbp-39h]
  int v86[2]; // [rsp+98h] [rbp-31h] BYREF
  __int64 v87; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v88[2]; // [rsp+A8h] [rbp-21h] BYREF
  int v89; // [rsp+B8h] [rbp-11h]
  __int64 v90; // [rsp+C0h] [rbp-9h]
  __int64 v91; // [rsp+C8h] [rbp-1h] BYREF
  __int128 v92; // [rsp+D0h] [rbp+7h] BYREF

  v3 = (void **)((char *)this + 24);
  v77 = -2147023537;
  v75 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp";
  if ( *((_QWORD *)this + 3) )
    goto LABEL_108;
  v6 = *((_QWORD *)this + 2);
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  v79 = 0u;
  v80 = 0;
  *(_QWORD *)v78 = 0;
  *(_QWORD *)v82 = 0;
  v91 = 24;
  v92 = 0;
  v7 = RtlQueryInformationApplicationContext(this, v6, &v91);
  v10 = v7;
  if ( v7 < 0 )
  {
    if ( v7 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
      (const char *)0x170,
      v10,
      v74);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v11);
    while ( 1 )
    {
      v15 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v15 == lpMem )
        break;
      v13 = (void (__fastcall *)(LPVOID *))v15[2];
      if ( v13 )
        v13(v15 + 3);
      ProcessHeap_0 = GetProcessHeap_0();
      HeapFree_0(ProcessHeap_0, 0, v15);
    }
    return v12;
  }
  ApplicationContextComponentStore = RtlGetApplicationContextComponentStore(v8, *((_QWORD *)this + 2), v9, v78);
  v17 = ApplicationContextComponentStore;
  if ( ApplicationContextComponentStore < 0 )
  {
    if ( ApplicationContextComponentStore == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
      (const char *)0x177,
      v17,
      v74);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v17, v18);
    if ( *(_QWORD *)v78 )
    {
      v77 = -1073741595;
      v75 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v78) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v20 + 4))(*v20, v19);
        v21 = 0;
      }
      else
      {
        v76 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v75);
        v21 = v77;
      }
      if ( v21 < 0 )
        RaiseException(v21, 1u, 0, 0);
      *(_QWORD *)v78 = 0;
    }
    v22 = v80;
    if ( v80 )
    {
      v79 = 0u;
      v80 = 0;
      IsolationFreeStringRoutine(v22);
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
    return v12;
  }
  *(_QWORD *)v86 = 0;
  AllocationListMemory = RtlAllocateAllocationListMemory(
                           lpMem,
                           40,
                           Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                           v86);
  if ( AllocationListMemory >= 0 )
  {
    v87 = 0;
    v28 = RtlAllocateAllocationListMemory(
            lpMem,
            64,
            Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
            &v87);
    if ( v28 < 0 )
    {
      if ( v28 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
        (const char *)0x17A,
        v28,
        v74);
      v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v28, v61);
      if ( !*(_QWORD *)v78 )
        goto LABEL_87;
      dwExceptionCode = -1073741595;
      v83 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v78) )
      {
        v84 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v83);
        v31 = dwExceptionCode;
        goto LABEL_84;
      }
      goto LABEL_83;
    }
    DirectIsolatedFilesystem = RtlCreateDirectIsolatedFilesystem(v27, v82);
    if ( DirectIsolatedFilesystem < 0 )
    {
      v76 = 380;
LABEL_36:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(
        v29,
        &v75,
        (unsigned int)DirectIsolatedFilesystem);
      v34 = (unsigned int)DirectIsolatedFilesystem;
      goto LABEL_37;
    }
    v32 = (char *)this + 48;
    DirectIsolatedFilesystem = RtlGenerateComponentStoreLockIdentifier(v29, (char *)this + 48);
    if ( DirectIsolatedFilesystem < 0 )
    {
      v76 = 381;
      goto LABEL_36;
    }
    v40 = (char *)this + 80;
    ComponentStoreLockIdentifier = RtlGenerateComponentStoreLockIdentifier(v29, (char *)this + 80);
    if ( ComponentStoreLockIdentifier < 0 )
    {
      v76 = 382;
LABEL_51:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(
        v41,
        &v75,
        (unsigned int)ComponentStoreLockIdentifier);
      v34 = (unsigned int)ComponentStoreLockIdentifier;
LABEL_37:
      v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v34, v33);
      if ( !*(_QWORD *)v82 )
        goto LABEL_44;
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v75 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      v77 = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v82) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v36 + 4))(*v36, v35);
LABEL_41:
        v37 = 0;
        goto LABEL_42;
      }
      goto LABEL_48;
    }
    ComponentStoreLockIdentifier = RtlGuessComponentStoreApplicationPaths(
                                     v41,
                                     v78[0],
                                     v43,
                                     (unsigned int)&v92 + 8,
                                     (__int64)&v79);
    if ( ComponentStoreLockIdentifier < 0 )
    {
      v76 = 389;
      goto LABEL_51;
    }
    v44 = v87;
    v45 = *(_QWORD *)v86;
    v46 = *(_QWORD *)v82;
    **(_QWORD **)v86 = 40;
    *(_QWORD *)(v45 + 8) = *((_QWORD *)&v92 + 1);
    *(_QWORD *)(v45 + 16) = v32;
    *(_QWORD *)v44 = 64;
    *(_QWORD *)(v44 + 32) = v32;
    *(_QWORD *)(v44 + 40) = v40;
    v47 = v80;
    *(_OWORD *)(v44 + 8) = v79;
    *(_QWORD *)(v44 + 24) = v47;
    v90 = v44;
    v88[1] = v45;
    LODWORD(v88[0]) = 13;
    v89 = 15;
    v48 = RtlTransactComponentStore(v45, v46, v78[0], 2, (__int64)v88, 0);
    v50 = v48;
    if ( v48 < 0 )
    {
      v76 = 413;
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(
        v49,
        &v75,
        (unsigned int)v48);
      v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v50, v51);
      if ( !v46 )
        goto LABEL_44;
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v77 = -1073741595;
      v75 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v46) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v52 + 4))(*v52, v46);
        goto LABEL_41;
      }
LABEL_48:
      v76 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v75);
      v37 = v77;
LABEL_42:
      if ( v37 < 0 )
        RaiseException(v37, 1u, 0, 0);
LABEL_44:
      if ( !*(_QWORD *)v78 )
      {
LABEL_87:
        v62 = v80;
        if ( v80 )
        {
          v80 = 0;
          v79 = 0u;
          IsolationFreeStringRoutine(v62);
        }
        Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
        return v12;
      }
      v77 = -1073741595;
      v75 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
        || !(unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v78) )
      {
        v76 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v75);
        v31 = v77;
LABEL_84:
        if ( v31 < 0 )
          RaiseException(v31, 1u, 0, 0);
        *(_QWORD *)v78 = 0;
        goto LABEL_87;
      }
LABEL_83:
      (*((void (__fastcall **)(_QWORD, __int64))v39 + 4))(*v39, v38);
      v31 = 0;
      goto LABEL_84;
    }
    v53 = v80;
    v80 = v3[2];
    v54 = v79;
    v79 = *(_OWORD *)v3;
    *(_OWORD *)v3 = v54;
    v3[2] = v53;
    if ( v46 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      dwExceptionCode = -1073741595;
      v83 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v46) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v55 + 4))(*v55, v46);
        v56 = 0;
      }
      else
      {
        v84 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v83);
        v56 = dwExceptionCode;
      }
      if ( v56 < 0 )
        RaiseException(v56, 1u, 0, 0);
    }
    if ( *(_QWORD *)v78 )
    {
      dwExceptionCode = -1073741595;
      v83 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v78) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v58 + 4))(*v58, v57);
        v59 = 0;
      }
      else
      {
        v84 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v83);
        v59 = dwExceptionCode;
      }
      if ( v59 < 0 )
        RaiseException(v59, 1u, 0, 0);
      *(_QWORD *)v78 = 0;
    }
    v60 = v80;
    if ( v80 )
    {
      v79 = 0u;
      v80 = 0;
      IsolationFreeStringRoutine(v60);
    }
    Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
    if ( !*v3 )
    {
      v76 = 418;
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
        &v75,
        &v75);
      return v77;
    }
LABEL_108:
    v71 = IsolationImplementation::Com::CopyOutPath(
            (IsolationImplementation::Com *)v3,
            (const struct _LUNICODE_STRING *)a3,
            a3);
    v12 = v71;
    if ( v71 >= 0 )
      return 0;
    else
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
        (const char *)0x1A4,
        v71,
        v72);
    return v12;
  }
  if ( AllocationListMemory == g_NTSTATUS_to_break_on_propagate )
    DebugBreak();
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"Status propagated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
    (const char *)0x179,
    AllocationListMemory,
    v74);
  v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
          (Windows::ErrorHandling::COM *)(unsigned int)AllocationListMemory,
          v63);
  if ( *(_QWORD *)v78 )
  {
    dwExceptionCode = -1073741595;
    v83 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v78) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v65 + 4))(*v65, v64);
      v66 = 0;
    }
    else
    {
      v84 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v83);
      v66 = dwExceptionCode;
    }
    if ( v66 < 0 )
      RaiseException(v66, 1u, 0, 0);
    *(_QWORD *)v78 = 0;
  }
  v67 = v80;
  if ( v80 )
  {
    v79 = 0u;
    v80 = 0;
    IsolationFreeStringRoutine(v67);
  }
  while ( 1 )
  {
    v70 = (LPVOID *)lpMem[0];
    lpMem[0] = *(LPVOID *)lpMem[0];
    *((_QWORD *)lpMem[0] + 1) = lpMem;
    if ( v70 == lpMem )
      break;
    v68 = (void (__fastcall *)(LPVOID *))v70[2];
    if ( v68 )
      v68(v70 + 3);
    v69 = GetProcessHeap_0();
    HeapFree_0(v69, 0, v70);
  }
  return v12;
}

```

## disassembly

```asm
0x1800a33fc  mov     [rsp-8+arg_8], rbx
0x1800a3401  push    rbp
0x1800a3402  push    rsi
0x1800a3403  push    rdi
0x1800a3404  push    r12
0x1800a3406  push    r13
0x1800a3408  push    r14
0x1800a340a  push    r15
0x1800a340c  lea     rbp, [rsp-27h]
0x1800a3411  sub     rsp, 0F0h
0x1800a3418  mov     rax, cs:__security_cookie
0x1800a341f  xor     rax, rsp
0x1800a3422  mov     [rbp+57h+var_40], rax
0x1800a3426  lea     rsi, [rcx+18h]
0x1800a342a  mov     [rsp+120h+var_E0], 8007054Fh
0x1800a3432  xor     r12d, r12d
0x1800a3435  lea     r13, aOnecoreComNetf_59; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a343c  mov     r15, r8
0x1800a343f  mov     rbx, rcx
0x1800a3442  mov     [rsp+120h+var_F0], r13
0x1800a3447  cmp     [rsi], r12
0x1800a344a  jnz     loc_1800A3CB4
0x1800a3450  mov     rdx, [rcx+10h]
0x1800a3454  lea     rax, [rbp+57h+lpMem]
0x1800a3458  mov     [rbp+57h+var_B0], rax
0x1800a345c  lea     r8, [rbp+57h+var_58]
0x1800a3460  lea     rax, [rbp+57h+lpMem]
0x1800a3464  mov     qword ptr [rbp+57h+var_D0+8], r12
0x1800a3468  xorps   xmm0, xmm0
0x1800a346b  mov     [rbp+57h+lpMem], rax
0x1800a346f  mov     qword ptr [rbp+57h+var_D0], r12
0x1800a3473  mov     [rbp+57h+var_C0], r12
0x1800a3477  mov     qword ptr [rsp+120h+var_D8], r12
0x1800a347c  mov     qword ptr [rbp+57h+var_A8], r12
0x1800a3480  mov     [rbp+57h+var_58], 18h
0x1800a3488  movups  [rbp+57h+var_50], xmm0
0x1800a348c  call    RtlQueryInformationApplicationContext
0x1800a3491  mov     edi, eax
0x1800a3493  test    eax, eax
0x1800a3495  jns     loc_1800A35A7
0x1800a349b  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a34a1  jnz     short loc_1800A34A9
0x1800a34a3  call    cs:__imp_DebugBreak
0x1800a34a9  mov     r9d, edi; int
0x1800a34ac  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a34b3  mov     r8d, 170h; char *
0x1800a34b9  mov     rdx, r13; char *
0x1800a34bc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a34c1  mov     ecx, edi; this
0x1800a34c3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a34c8  mov     r10, qword ptr [rsp+120h+var_D8]
0x1800a34cd  mov     esi, eax
0x1800a34cf  test    r10, r10
0x1800a34d2  jz      short loc_1800A352E
0x1800a34d4  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a34db  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a34e2  mov     [rsp+120h+var_E0], 0C00000E5h
0x1800a34ea  mov     [rsp+120h+var_F0], rdi
0x1800a34ef  test    r11, r11
0x1800a34f2  jz      short loc_1800A354A
0x1800a34f4  mov     rdx, r11
0x1800a34f7  mov     rcx, r10
0x1800a34fa  call    RtlIsTypeSafeHandleValid
0x1800a34ff  test    al, al
0x1800a3501  jz      short loc_1800A354A
0x1800a3503  mov     ecx, [r11]
0x1800a3506  mov     rdx, r10
0x1800a3509  mov     rax, [r11+20h]
0x1800a350d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3512  mov     ecx, r12d; dwExceptionCode
0x1800a3515  test    ecx, ecx
0x1800a3517  jns     short loc_1800A3529
0x1800a3519  xor     r9d, r9d; lpArguments
0x1800a351c  xor     r8d, r8d; nNumberOfArguments
0x1800a351f  lea     edx, [r9+1]; dwExceptionFlags
0x1800a3523  call    cs:__imp_RaiseException
0x1800a3529  mov     qword ptr [rsp+120h+var_D8], r12
0x1800a352e  mov     rcx, [rbp+57h+var_C0]; lpMem
0x1800a3532  test    rcx, rcx
0x1800a3535  jz      short loc_1800A3586
0x1800a3537  mov     qword ptr [rbp+57h+var_D0+8], r12
0x1800a353b  mov     qword ptr [rbp+57h+var_D0], r12
0x1800a353f  mov     [rbp+57h+var_C0], r12
0x1800a3543  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800a3548  jmp     short loc_1800A3586
0x1800a354a  mov     [rsp+120h+var_E8], 124h
0x1800a3552  lea     rcx, [rsp+120h+var_F0]
0x1800a3557  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a355c  mov     ecx, [rsp+120h+var_E0]
0x1800a3560  jmp     short loc_1800A3515
0x1800a3562  mov     rax, [rbx+10h]
0x1800a3566  test    rax, rax
0x1800a3569  jz      short loc_1800A3574
0x1800a356b  lea     rcx, [rbx+18h]
0x1800a356f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3574  call    GetProcessHeap_0
0x1800a3579  mov     r8, rbx; lpMem
0x1800a357c  xor     edx, edx; dwFlags
0x1800a357e  mov     rcx, rax; hHeap
0x1800a3581  call    HeapFree_0
0x1800a3586  mov     rbx, [rbp+57h+lpMem]
0x1800a358a  lea     rcx, [rbp+57h+lpMem]
0x1800a358e  mov     rax, [rbx]
0x1800a3591  mov     [rbp+57h+lpMem], rax
0x1800a3595  mov     [rax+8], rcx
0x1800a3599  lea     rax, [rbp+57h+lpMem]
0x1800a359d  cmp     rbx, rax
0x1800a35a0  jnz     short loc_1800A3562
0x1800a35a2  jmp     loc_1800A3CDA
0x1800a35a7  mov     rdx, [rbx+10h]
0x1800a35ab  lea     r9, [rsp+120h+var_D8]
0x1800a35b0  call    RtlGetApplicationContextComponentStore
0x1800a35b5  mov     edi, eax
0x1800a35b7  test    eax, eax
0x1800a35b9  jns     loc_1800A36CB
0x1800a35bf  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a35c5  jnz     short loc_1800A35CD
0x1800a35c7  call    cs:__imp_DebugBreak
0x1800a35cd  mov     r9d, edi; int
0x1800a35d0  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a35d7  mov     r8d, 177h; char *
0x1800a35dd  mov     rdx, r13; char *
0x1800a35e0  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a35e5  mov     ecx, edi; this
0x1800a35e7  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a35ec  mov     r10, qword ptr [rsp+120h+var_D8]
0x1800a35f1  mov     esi, eax
0x1800a35f3  test    r10, r10
0x1800a35f6  jz      short loc_1800A3652
0x1800a35f8  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a35ff  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a3606  mov     [rsp+120h+var_E0], 0C00000E5h
0x1800a360e  mov     [rsp+120h+var_F0], rdi
0x1800a3613  test    r11, r11
0x1800a3616  jz      short loc_1800A366E
0x1800a3618  mov     rdx, r11
0x1800a361b  mov     rcx, r10
0x1800a361e  call    RtlIsTypeSafeHandleValid
0x1800a3623  test    al, al
0x1800a3625  jz      short loc_1800A366E
0x1800a3627  mov     ecx, [r11]
0x1800a362a  mov     rdx, r10
0x1800a362d  mov     rax, [r11+20h]
0x1800a3631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3636  mov     ecx, r12d; dwExceptionCode
0x1800a3639  test    ecx, ecx
0x1800a363b  jns     short loc_1800A364D
0x1800a363d  xor     r9d, r9d; lpArguments
0x1800a3640  xor     r8d, r8d; nNumberOfArguments
0x1800a3643  lea     edx, [r9+1]; dwExceptionFlags
0x1800a3647  call    cs:__imp_RaiseException
0x1800a364d  mov     qword ptr [rsp+120h+var_D8], r12
0x1800a3652  mov     rcx, [rbp+57h+var_C0]; lpMem
0x1800a3656  test    rcx, rcx
0x1800a3659  jz      short loc_1800A36AA
0x1800a365b  mov     qword ptr [rbp+57h+var_D0+8], r12
0x1800a365f  mov     qword ptr [rbp+57h+var_D0], r12
0x1800a3663  mov     [rbp+57h+var_C0], r12
0x1800a3667  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800a366c  jmp     short loc_1800A36AA
0x1800a366e  mov     [rsp+120h+var_E8], 124h
0x1800a3676  lea     rcx, [rsp+120h+var_F0]
0x1800a367b  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a3680  mov     ecx, [rsp+120h+var_E0]
0x1800a3684  jmp     short loc_1800A3639
0x1800a3686  mov     rax, [rbx+10h]
0x1800a368a  test    rax, rax
0x1800a368d  jz      short loc_1800A3698
0x1800a368f  lea     rcx, [rbx+18h]
0x1800a3693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3698  call    GetProcessHeap_0
0x1800a369d  mov     r8, rbx; lpMem
0x1800a36a0  xor     edx, edx; dwFlags
0x1800a36a2  mov     rcx, rax; hHeap
0x1800a36a5  call    HeapFree_0
0x1800a36aa  mov     rbx, [rbp+57h+lpMem]
0x1800a36ae  lea     rcx, [rbp+57h+lpMem]
0x1800a36b2  mov     rax, [rbx]
0x1800a36b5  mov     [rbp+57h+lpMem], rax
0x1800a36b9  mov     [rax+8], rcx
0x1800a36bd  lea     rax, [rbp+57h+lpMem]
0x1800a36c1  cmp     rbx, rax
0x1800a36c4  jnz     short loc_1800A3686
0x1800a36c6  jmp     loc_1800A3CDA
0x1800a36cb  lea     r9, [rbp+57h+var_88]
0x1800a36cf  mov     qword ptr [rbp+57h+var_88], r12
0x1800a36d3  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800a36da  mov     edx, 28h ; '('
0x1800a36df  lea     rcx, [rbp+57h+lpMem]
0x1800a36e3  call    RtlAllocateAllocationListMemory
0x1800a36e8  mov     edi, eax
0x1800a36ea  test    eax, eax
0x1800a36ec  js      loc_1800A3BB0
0x1800a36f2  lea     r9, [rbp+57h+var_80]
0x1800a36f6  mov     [rbp+57h+var_80], r12
0x1800a36fa  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800a3701  mov     edx, 40h ; '@'
0x1800a3706  lea     rcx, [rbp+57h+lpMem]
0x1800a370a  call    RtlAllocateAllocationListMemory
0x1800a370f  mov     edi, eax
0x1800a3711  test    eax, eax
0x1800a3713  js      loc_1800A3AE2
0x1800a3719  lea     rdx, [rbp+57h+var_A8]
0x1800a371d  call    RtlCreateDirectIsolatedFilesystem
0x1800a3722  mov     edi, eax
0x1800a3724  test    eax, eax
0x1800a3726  jns     short loc_1800A374D
0x1800a3728  mov     [rsp+120h+var_E8], 17Ch
0x1800a3730  jmp     short loc_1800A376B
0x1800a3732  mov     [rsp+120h+var_E8], 124h
0x1800a373a  lea     rcx, [rsp+120h+var_F0]
0x1800a373f  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a3744  mov     ecx, [rsp+120h+var_E0]
0x1800a3748  jmp     loc_1800A3B5A
0x1800a374d  lea     r14, [rbx+30h]
0x1800a3751  mov     rdx, r14
0x1800a3754  call    RtlGenerateComponentStoreLockIdentifier
0x1800a3759  mov     edi, eax
0x1800a375b  test    eax, eax
0x1800a375d  jns     loc_1800A3846
0x1800a3763  mov     [rsp+120h+var_E8], 17Dh
0x1800a376b  mov     r8d, edi
0x1800a376e  lea     rdx, [rsp+120h+var_F0]
0x1800a3773  call    ?FrameReportNtStatusErrorPropagation@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(Windows::ErrorHandling::CCallSite const &,long)
0x1800a3778  mov     ecx, edi; this
0x1800a377a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a377f  mov     r10, qword ptr [rbp+57h+var_A8]
0x1800a3783  lea     rdi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a378a  mov     esi, eax
0x1800a378c  test    r10, r10
0x1800a378f  jz      short loc_1800A37EB
0x1800a3791  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800a3798  mov     [rsp+120h+var_F0], rdi
0x1800a379d  mov     [rsp+120h+var_E0], 0C00000E5h
0x1800a37a5  test    r10, r10
0x1800a37a8  jz      short loc_1800A37D4
0x1800a37aa  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800a37b1  test    r11, r11
0x1800a37b4  jz      short loc_1800A382E
0x1800a37b6  mov     rdx, r11
0x1800a37b9  mov     rcx, r10
0x1800a37bc  call    RtlIsTypeSafeHandleValid
0x1800a37c1  test    al, al
0x1800a37c3  jz      short loc_1800A382E
0x1800a37c5  mov     ecx, [r11]
0x1800a37c8  mov     rdx, r10
0x1800a37cb  mov     rax, [r11+20h]
0x1800a37cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a37d4  mov     ecx, r12d; dwExceptionCode
0x1800a37d7  test    ecx, ecx
0x1800a37d9  jns     short loc_1800A37EB
0x1800a37db  xor     r9d, r9d; lpArguments
0x1800a37de  xor     r8d, r8d; nNumberOfArguments
0x1800a37e1  lea     edx, [r9+1]; dwExceptionFlags
0x1800a37e5  call    cs:__imp_RaiseException
0x1800a37eb  mov     r10, qword ptr [rsp+120h+var_D8]
0x1800a37f0  test    r10, r10
0x1800a37f3  jz      loc_1800A3B73
0x1800a37f9  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a3800  mov     [rsp+120h+var_E0], 0C00000E5h
0x1800a3808  mov     [rsp+120h+var_F0], rdi
0x1800a380d  test    r11, r11
0x1800a3810  jz      loc_1800A3732
0x1800a3816  mov     rdx, r11
0x1800a3819  mov     rcx, r10
0x1800a381c  call    RtlIsTypeSafeHandleValid
0x1800a3821  test    al, al
0x1800a3823  jz      loc_1800A3732
0x1800a3829  jmp     loc_1800A3B48
0x1800a382e  mov     [rsp+120h+var_E8], 124h
0x1800a3836  lea     rcx, [rsp+120h+var_F0]
0x1800a383b  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a3840  mov     ecx, [rsp+120h+var_E0]
0x1800a3844  jmp     short loc_1800A37D7
0x1800a3846  lea     rdi, [rbx+50h]
0x1800a384a  mov     rdx, rdi
0x1800a384d  call    RtlGenerateComponentStoreLockIdentifier
0x1800a3852  mov     ebx, eax
0x1800a3854  test    eax, eax
0x1800a3856  jns     short loc_1800A3874
0x1800a3858  mov     [rsp+120h+var_E8], 17Eh
0x1800a3860  mov     r8d, ebx
0x1800a3863  lea     rdx, [rsp+120h+var_F0]
0x1800a3868  call    ?FrameReportNtStatusErrorPropagation@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(Windows::ErrorHandling::CCallSite const &,long)
0x1800a386d  mov     ecx, ebx
0x1800a386f  jmp     loc_1800A377A
0x1800a3874  mov     rdx, qword ptr [rsp+120h+var_D8]
0x1800a3879  lea     rax, [rbp+57h+var_D0]
0x1800a387d  lea     r9, [rbp+57h+var_50+8]
0x1800a3881  mov     [rsp+120h+var_100], rax
0x1800a3886  call    RtlGuessComponentStoreApplicationPaths
0x1800a388b  mov     ebx, eax
0x1800a388d  test    eax, eax
0x1800a388f  jns     short loc_1800A389B
0x1800a3891  mov     [rsp+120h+var_E8], 185h
0x1800a3899  jmp     short loc_1800A3860
0x1800a389b  mov     rdx, [rbp+57h+var_80]
0x1800a389f  mov     r9d, 2; int
0x1800a38a5  mov     rcx, qword ptr [rbp+57h+var_88]; int
0x1800a38a9  mov     rbx, qword ptr [rbp+57h+var_A8]
  ... truncated ...
```
