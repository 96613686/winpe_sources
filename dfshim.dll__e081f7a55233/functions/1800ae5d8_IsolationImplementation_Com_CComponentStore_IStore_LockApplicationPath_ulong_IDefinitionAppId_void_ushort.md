# IsolationImplementation::Com::CComponentStore::IStore_LockApplicationPath(ulong,IDefinitionAppId *,void * *,ushort * *)

- ea: `0x1800ae5d8`
- end: `0x1800aed65`
- name: `?IStore_LockApplicationPath@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIDefinitionAppId@@PEAPEAXPEAPEAG@Z`
- size: `1933`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IDefinitionAppId *, void **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x1800b01c0`

## callees

- `0x180006991`
- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012538`
- `0x180012820`
- `0x180012acc`
- `0x180012b1c`
- `0x180012b38`
- `0x180016f8c`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18001b05c`
- `0x1800237b8`
- `0x18002decc`
- `0x180030508`
- `0x180037464`
- `0x180039c1c`
- `0x18003eb10`
- `0x180042f10`
- `0x18004f2dc`
- `0x1800ae5d8`
- `0x1800f96b8`
- `0x1800fa2a4`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae69d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae6f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aed30`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae69d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ae6f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800aed30`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae63c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae884`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aebcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aec7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae63c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ae884`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aebcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800aec7b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aeb73`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aeb73`

## string_xrefs

- `0x1800ae942`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800aeb0c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ae5fc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ae77e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ae890`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aeac7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aeae4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aebd4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800aec84`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_LockApplicationPath(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IDefinitionAppId *a3,
        void **a4,
        unsigned __int16 **a5)
{
  int v9; // eax
  struct Windows::Isolation::Rtl::_DEFINITION_APPID *v10; // r8
  unsigned int v11; // ebx
  int v12; // edx
  unsigned int v13; // edi
  HANDLE v14; // rbx
  HANDLE v15; // rbx
  int v16; // eax
  int v17; // r9d
  void *v18; // rcx
  void (__fastcall *v19)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v21; // rbx
  int AllocationListMemory; // ebx
  int v23; // ebx
  HANDLE v24; // rax
  __int64 v25; // rcx
  char *v26; // rsi
  int v27; // edx
  void *v28; // rcx
  __int64 v29; // rcx
  int DirectIsolatedFilesystem; // ebx
  int v31; // edx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r10
  unsigned int *v35; // r11
  int v36; // r8d
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rbx
  void *v41; // xmm1_8
  __int64 v42; // r8
  int v43; // eax
  __int64 v44; // rcx
  unsigned __int16 **v45; // r8
  int v46; // r9d
  unsigned int v47; // edi
  int v48; // edx
  __int64 v49; // rdx
  __int64 v50; // rcx
  int v51; // eax
  int v52; // r9d
  unsigned int *v53; // r10
  int v54; // ecx
  void *v55; // rcx
  int v56; // edx
  void *v57; // rcx
  void (__fastcall *v58)(LPVOID *); // rax
  HANDLE v59; // rax
  LPVOID *v60; // rbx
  int v61; // edx
  void *v62; // rcx
  void (__fastcall *v63)(LPVOID *); // rax
  HANDLE v64; // rax
  LPVOID *v65; // rbx
  HANDLE v66; // rbx
  unsigned int v68; // [rsp+20h] [rbp-E0h]
  __int64 v69; // [rsp+30h] [rbp-D0h] BYREF
  const char *v70; // [rsp+38h] [rbp-C8h] BYREF
  int v71; // [rsp+40h] [rbp-C0h]
  DWORD dwExceptionCode; // [rsp+48h] [rbp-B8h]
  __int128 v73; // [rsp+50h] [rbp-B0h] BYREF
  void *v74; // [rsp+60h] [rbp-A0h]
  LPVOID lpMem[2]; // [rsp+68h] [rbp-98h] BYREF
  int v76[2]; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hMutex; // [rsp+80h] [rbp-80h] BYREF
  __int16 v78; // [rsp+88h] [rbp-78h]
  _BYTE v79[64]; // [rsp+90h] [rbp-70h] BYREF
  int v80[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v81; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v82[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v83; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v84[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v85; // [rsp+100h] [rbp+0h]
  __int64 v86; // [rsp+108h] [rbp+8h]

  dwExceptionCode = -2147023537;
  v70 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v79);
  hMutex = 0;
  v78 = 0;
  v9 = StoreLock::Lock((StoreLock *)&hMutex);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x473,
      v11,
      v68);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v11, v12);
LABEL_102:
    v66 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v78 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v78) = 0;
      }
      CloseHandle_0(v66);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v79);
    return v13;
  }
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a2 )
  {
    v14 = hMutex;
    v71 = 1145;
    if ( hMutex )
    {
      if ( (_BYTE)v78 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v78) = 0;
      }
      CloseHandle_0(v14);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v79);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v70);
    return dwExceptionCode;
  }
  if ( !a3 )
  {
    v71 = 1146;
LABEL_17:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v70);
    v15 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v78 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v78) = 0;
      }
      CloseHandle_0(v15);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v79);
    return dwExceptionCode;
  }
  if ( !a4 )
  {
    v71 = 1147;
    goto LABEL_17;
  }
  if ( !a5 )
  {
    v71 = 1148;
    goto LABEL_17;
  }
  lpMem[1] = lpMem;
  v73 = 0u;
  lpMem[0] = lpMem;
  v74 = 0;
  v69 = 0;
  *(_QWORD *)v76 = 0;
  v16 = IsolationImplementation::Com::ConvertIn(a3, (struct IDefinitionAppId *)&v69, v10);
  v13 = v16;
  if ( v16 < 0 )
  {
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x48B,
      v16,
      v17);
    if ( v69 )
    {
      RtlCloseDefinitionAppIdHandle();
      v69 = 0;
    }
    v18 = v74;
    if ( v74 )
    {
      v73 = 0u;
      v74 = 0;
      IsolationFreeStringRoutine(v18);
    }
    while ( 1 )
    {
      v21 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v21 == lpMem )
        break;
      v19 = (void (__fastcall *)(LPVOID *))v21[2];
      if ( v19 )
        v19(v21 + 3);
      ProcessHeap_0 = GetProcessHeap_0();
      HeapFree_0(ProcessHeap_0, 0, v21);
    }
    goto LABEL_102;
  }
  *(_QWORD *)v80 = 0;
  AllocationListMemory = RtlAllocateAllocationListMemory(
                           lpMem,
                           40,
                           Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                           v80);
  if ( AllocationListMemory < 0 )
  {
    if ( AllocationListMemory == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x48C,
      AllocationListMemory,
      v68);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
            (Windows::ErrorHandling::COM *)(unsigned int)AllocationListMemory,
            v61);
    if ( v69 )
    {
      RtlCloseDefinitionAppIdHandle();
      v69 = 0;
    }
    v62 = v74;
    if ( v74 )
    {
      v73 = 0u;
      v74 = 0;
      IsolationFreeStringRoutine(v62);
    }
    while ( 1 )
    {
      v65 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v65 == lpMem )
        break;
      v63 = (void (__fastcall *)(LPVOID *))v65[2];
      if ( v63 )
        v63(v65 + 3);
      v64 = GetProcessHeap_0();
      HeapFree_0(v64, 0, v65);
    }
    goto LABEL_102;
  }
  v81 = 0;
  v23 = RtlAllocateAllocationListMemory(
          lpMem,
          64,
          Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
          &v81);
  if ( v23 < 0 )
  {
    if ( v23 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x48D,
      v23,
      v68);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v23, v56);
    if ( v69 )
    {
      RtlCloseDefinitionAppIdHandle();
      v69 = 0;
    }
    v57 = v74;
    if ( v74 )
    {
      v73 = 0u;
      v74 = 0;
      IsolationFreeStringRoutine(v57);
    }
    while ( 1 )
    {
      v60 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v60 == lpMem )
        break;
      v58 = (void (__fastcall *)(LPVOID *))v60[2];
      if ( v58 )
        v58(v60 + 3);
      v59 = GetProcessHeap_0();
      HeapFree_0(v59, 0, v60);
    }
    goto LABEL_102;
  }
  v24 = GetProcessHeap_0();
  v26 = (char *)HeapAlloc_0(v24, 0, 0x48u);
  if ( !v26 )
  {
    if ( g_NTSTATUS_to_break_on_propagate == -1073741801 )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x48E,
      -1073741801,
      v68);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)0xC0000017LL, v27);
    if ( v69 )
    {
      RtlCloseDefinitionAppIdHandle();
      v69 = 0;
    }
    v28 = v74;
    if ( v74 )
    {
      v73 = 0u;
      v74 = 0;
      IsolationFreeStringRoutine(v28);
    }
    Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
    goto LABEL_102;
  }
  DirectIsolatedFilesystem = RtlCreateDirectIsolatedFilesystem(v25, v76);
  if ( DirectIsolatedFilesystem < 0 )
  {
    v71 = 1171;
    goto LABEL_49;
  }
  DirectIsolatedFilesystem = RtlGenerateComponentStoreLockIdentifier(v29, v26);
  if ( DirectIsolatedFilesystem < 0 )
  {
    v71 = 1172;
    goto LABEL_49;
  }
  DirectIsolatedFilesystem = RtlGenerateComponentStoreLockIdentifier(v29, v26 + 32);
  if ( DirectIsolatedFilesystem < 0 )
  {
    v71 = 1173;
    goto LABEL_49;
  }
  v37 = *((_QWORD *)this + 2);
  v83 = v69;
  DirectIsolatedFilesystem = RtlGuessComponentStoreApplicationPaths(v29, v37, v36, (unsigned int)&v83, (__int64)&v73);
  if ( DirectIsolatedFilesystem < 0 )
  {
    v71 = 1181;
LABEL_49:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(
      v29,
      &v70,
      (unsigned int)DirectIsolatedFilesystem);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
            (Windows::ErrorHandling::COM *)(unsigned int)DirectIsolatedFilesystem,
            v31);
    RtlFreeHeap(v33, v32, v26);
    if ( *(_QWORD *)v76 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      v70 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      dwExceptionCode = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v76) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v35 + 4))(*v35, v34);
LABEL_72:
        v54 = 0;
        goto LABEL_74;
      }
      goto LABEL_73;
    }
    goto LABEL_76;
  }
  v38 = v81;
  v39 = *(_QWORD *)v80;
  v40 = *(_QWORD *)v76;
  **(_QWORD **)v80 = 40;
  *(_QWORD *)(v39 + 8) = v69;
  *(_QWORD *)(v39 + 16) = v26;
  *(_QWORD *)v38 = 64;
  *(_QWORD *)(v38 + 32) = v26;
  *(_QWORD *)(v38 + 40) = v26 + 32;
  v41 = v74;
  *(_OWORD *)(v38 + 8) = v73;
  *(_QWORD *)(v38 + 24) = v41;
  v42 = *((_QWORD *)this + 2);
  v86 = v38;
  v84[1] = v39;
  LODWORD(v84[0]) = 13;
  v85 = 15;
  v43 = RtlTransactComponentStore(v39, v40, v42, 2, (__int64)v84, v82);
  v47 = v43;
  if ( v43 < 0 )
  {
    v71 = 1205;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(
      v44,
      &v70,
      (unsigned int)v43);
    v13 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v47, v48);
LABEL_67:
    RtlFreeHeap(v50, v49, v26);
    goto LABEL_68;
  }
  if ( v82[0] != 1 || v82[1] != 1 )
  {
    v13 = -2147467259;
    Windows::ErrorHandling::COM::ReportErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x4BF,
      -2147467259,
      v46);
    goto LABEL_67;
  }
  *a4 = v26;
  v51 = IsolationImplementation::Com::CopyOutPath(
          (IsolationImplementation::Com *)&v73,
          (const struct _LUNICODE_STRING *)a5,
          v45);
  v13 = v51;
  if ( v51 >= 0 )
    v13 = 0;
  else
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x4BB,
      v51,
      v52);
LABEL_68:
  if ( v40 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v70 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    dwExceptionCode = -1073741595;
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v40) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v53 + 4))(*v53, v40);
      goto LABEL_72;
    }
LABEL_73:
    v71 = 292;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v70);
    v54 = dwExceptionCode;
LABEL_74:
    if ( v54 < 0 )
      RaiseException(v54, 1u, 0, 0);
  }
LABEL_76:
  if ( v69 )
  {
    RtlCloseDefinitionAppIdHandle();
    v69 = 0;
  }
  v55 = v74;
  if ( v74 )
  {
    v74 = 0;
    v73 = 0u;
    IsolationFreeStringRoutine(v55);
  }
  Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
  StoreLock::~StoreLock((StoreLock *)&hMutex);
  return v13;
}

```

## disassembly

```asm
0x1800ae5d8  push    rbp
0x1800ae5da  push    rbx
0x1800ae5db  push    rsi
0x1800ae5dc  push    rdi
0x1800ae5dd  push    r12
0x1800ae5df  push    r13
0x1800ae5e1  push    r14
0x1800ae5e3  push    r15
0x1800ae5e5  lea     rbp, [rsp-18h]
0x1800ae5ea  sub     rsp, 118h
0x1800ae5f1  mov     r13, rcx
0x1800ae5f4  mov     [rsp+150h+dwExceptionCode], 8007054Fh
0x1800ae5fc  lea     r14, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae603  mov     r15, r9
0x1800ae606  lea     rcx, [rbp+50h+var_C0]; this
0x1800ae60a  mov     [rsp+150h+var_118], r14
0x1800ae60f  mov     rdi, r8
0x1800ae612  mov     esi, edx
0x1800ae614  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800ae619  xor     r12d, r12d
0x1800ae61c  lea     rcx, [rbp+50h+hMutex]; this
0x1800ae620  mov     [rbp+50h+hMutex], r12
0x1800ae624  mov     [rbp+50h+var_C8], r12w
0x1800ae629  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800ae62e  mov     ebx, eax
0x1800ae630  test    eax, eax
0x1800ae632  jns     short loc_1800AE668
0x1800ae634  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ae63a  jnz     short loc_1800AE642
0x1800ae63c  call    cs:__imp_DebugBreak
0x1800ae642  mov     r9d, ebx; int
0x1800ae645  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ae64c  mov     r8d, 473h; char *
0x1800ae652  mov     rdx, r14; char *
0x1800ae655  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ae65a  mov     ecx, ebx; this
0x1800ae65c  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae661  mov     edi, eax
0x1800ae663  jmp     loc_1800AED1E
0x1800ae668  test    r15, r15
0x1800ae66b  jz      short loc_1800AE670
0x1800ae66d  mov     [r15], r12
0x1800ae670  mov     r14, [rbp+50h+arg_20]
0x1800ae677  test    r14, r14
0x1800ae67a  jz      short loc_1800AE67F
0x1800ae67c  mov     [r14], r12
0x1800ae67f  test    esi, esi
0x1800ae681  jz      short loc_1800AE6C8
0x1800ae683  mov     rbx, [rbp+50h+hMutex]
0x1800ae687  mov     [rsp+150h+var_110], 479h
0x1800ae68f  test    rbx, rbx
0x1800ae692  jz      short loc_1800AE6B3
0x1800ae694  cmp     byte ptr [rbp+50h+var_C8], r12b
0x1800ae698  jz      short loc_1800AE6A7
0x1800ae69a  mov     rcx, rbx; hMutex
0x1800ae69d  call    cs:__imp_ReleaseMutex
0x1800ae6a3  mov     byte ptr [rbp+50h+var_C8], r12b
0x1800ae6a7  mov     rcx, rbx; hObject
0x1800ae6aa  call    CloseHandle_0
0x1800ae6af  mov     [rbp+50h+hMutex], r12
0x1800ae6b3  lea     rcx, [rbp+50h+var_C0]; this
0x1800ae6b7  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ae6bc  lea     rcx, [rsp+150h+var_118]
0x1800ae6c1  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ae6c6  jmp     short loc_1800AE710
0x1800ae6c8  test    rdi, rdi
0x1800ae6cb  jnz     short loc_1800AE719
0x1800ae6cd  mov     [rsp+150h+var_110], 47Ah
0x1800ae6d5  lea     rcx, [rsp+150h+var_118]
0x1800ae6da  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800ae6df  mov     rbx, [rbp+50h+hMutex]
0x1800ae6e3  test    rbx, rbx
0x1800ae6e6  jz      short loc_1800AE707
0x1800ae6e8  cmp     byte ptr [rbp+50h+var_C8], r12b
0x1800ae6ec  jz      short loc_1800AE6FB
0x1800ae6ee  mov     rcx, rbx; hMutex
0x1800ae6f1  call    cs:__imp_ReleaseMutex
0x1800ae6f7  mov     byte ptr [rbp+50h+var_C8], r12b
0x1800ae6fb  mov     rcx, rbx; hObject
0x1800ae6fe  call    CloseHandle_0
0x1800ae703  mov     [rbp+50h+hMutex], r12
0x1800ae707  lea     rcx, [rbp+50h+var_C0]; this
0x1800ae70b  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ae710  mov     edi, [rsp+150h+dwExceptionCode]
0x1800ae714  jmp     loc_1800AED4F
0x1800ae719  test    r15, r15
0x1800ae71c  jnz     short loc_1800AE728
0x1800ae71e  mov     [rsp+150h+var_110], 47Bh
0x1800ae726  jmp     short loc_1800AE6D5
0x1800ae728  test    r14, r14
0x1800ae72b  jnz     short loc_1800AE737
0x1800ae72d  mov     [rsp+150h+var_110], 47Ch
0x1800ae735  jmp     short loc_1800AE6D5
0x1800ae737  lea     rax, [rsp+150h+lpMem]
0x1800ae73c  mov     qword ptr [rsp+150h+var_100+8], r12
0x1800ae741  mov     [rsp+150h+var_E0], rax
0x1800ae746  lea     rdx, [rsp+150h+var_120]; struct IDefinitionAppId *
0x1800ae74b  lea     rax, [rsp+150h+lpMem]
0x1800ae750  mov     qword ptr [rsp+150h+var_100], r12
0x1800ae755  mov     rcx, rdi; this
0x1800ae758  mov     [rsp+150h+lpMem], rax
0x1800ae75d  mov     [rsp+150h+var_F0], r12
0x1800ae762  mov     [rsp+150h+var_120], r12
0x1800ae767  mov     qword ptr [rsp+150h+var_D8], r12
0x1800ae76c  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionAppId@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionAppId *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800ae771  mov     edi, eax
0x1800ae773  test    eax, eax
0x1800ae775  jns     loc_1800AE80C
0x1800ae77b  mov     r8d, eax; int
0x1800ae77e  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae785  mov     edx, 48Bh; char *
0x1800ae78a  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ae78f  mov     rcx, [rsp+150h+var_120]
0x1800ae794  test    rcx, rcx
0x1800ae797  jz      short loc_1800AE7A3
0x1800ae799  call    RtlCloseDefinitionAppIdHandle
0x1800ae79e  mov     [rsp+150h+var_120], r12
0x1800ae7a3  mov     rcx, [rsp+150h+var_F0]; lpMem
0x1800ae7a8  test    rcx, rcx
0x1800ae7ab  jz      short loc_1800AE7E7
0x1800ae7ad  mov     qword ptr [rsp+150h+var_100+8], r12
0x1800ae7b2  mov     qword ptr [rsp+150h+var_100], r12
0x1800ae7b7  mov     [rsp+150h+var_F0], r12
0x1800ae7bc  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800ae7c1  jmp     short loc_1800AE7E7
0x1800ae7c3  mov     rax, [rbx+10h]
0x1800ae7c7  test    rax, rax
0x1800ae7ca  jz      short loc_1800AE7D5
0x1800ae7cc  lea     rcx, [rbx+18h]
0x1800ae7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae7d5  call    GetProcessHeap_0
0x1800ae7da  mov     r8, rbx; lpMem
0x1800ae7dd  xor     edx, edx; dwFlags
0x1800ae7df  mov     rcx, rax; hHeap
0x1800ae7e2  call    HeapFree_0
0x1800ae7e7  mov     rbx, [rsp+150h+lpMem]
0x1800ae7ec  lea     rcx, [rsp+150h+lpMem]
0x1800ae7f1  mov     rax, [rbx]
0x1800ae7f4  mov     [rsp+150h+lpMem], rax
0x1800ae7f9  mov     [rax+8], rcx
0x1800ae7fd  lea     rax, [rsp+150h+lpMem]
0x1800ae802  cmp     rbx, rax
0x1800ae805  jnz     short loc_1800AE7C3
0x1800ae807  jmp     loc_1800AED1E
0x1800ae80c  lea     r9, [rbp+50h+var_80]
0x1800ae810  mov     qword ptr [rbp+50h+var_80], r12
0x1800ae814  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800ae81b  mov     edx, 28h ; '('
0x1800ae820  lea     rcx, [rsp+150h+lpMem]
0x1800ae825  call    RtlAllocateAllocationListMemory
0x1800ae82a  mov     ebx, eax
0x1800ae82c  test    eax, eax
0x1800ae82e  js      loc_1800AEC73
0x1800ae834  lea     r9, [rbp+50h+var_78]
0x1800ae838  mov     [rbp+50h+var_78], r12
0x1800ae83c  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800ae843  mov     edx, 40h ; '@'
0x1800ae848  lea     rcx, [rsp+150h+lpMem]
0x1800ae84d  call    RtlAllocateAllocationListMemory
0x1800ae852  mov     ebx, eax
0x1800ae854  test    eax, eax
0x1800ae856  js      loc_1800AEBC3
0x1800ae85c  call    GetProcessHeap_0
0x1800ae861  xor     edx, edx; dwFlags
0x1800ae863  mov     rcx, rax; hHeap
0x1800ae866  lea     r8d, [rdx+48h]; dwBytes
0x1800ae86a  call    HeapAlloc_0
0x1800ae86f  mov     rsi, rax
0x1800ae872  test    rax, rax
0x1800ae875  jnz     short loc_1800AE8F3
0x1800ae877  mov     ebx, 0C0000017h
0x1800ae87c  cmp     cs:g_NTSTATUS_to_break_on_propagate, ebx
0x1800ae882  jnz     short loc_1800AE88A
0x1800ae884  call    cs:__imp_DebugBreak
0x1800ae88a  mov     r9d, 0C0000017h; int
0x1800ae890  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae897  mov     r8d, 48Eh; char *
0x1800ae89d  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ae8a4  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ae8a9  mov     ecx, ebx; this
0x1800ae8ab  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae8b0  mov     rcx, [rsp+150h+var_120]
0x1800ae8b5  mov     edi, eax
0x1800ae8b7  test    rcx, rcx
0x1800ae8ba  jz      short loc_1800AE8C6
0x1800ae8bc  call    RtlCloseDefinitionAppIdHandle
0x1800ae8c1  mov     [rsp+150h+var_120], r12
0x1800ae8c6  mov     rcx, [rsp+150h+var_F0]; lpMem
0x1800ae8cb  test    rcx, rcx
0x1800ae8ce  jz      short loc_1800AE8E4
0x1800ae8d0  mov     qword ptr [rsp+150h+var_100+8], r12
0x1800ae8d5  mov     qword ptr [rsp+150h+var_100], r12
0x1800ae8da  mov     [rsp+150h+var_F0], r12
0x1800ae8df  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800ae8e4  lea     rcx, [rsp+150h+lpMem]; this
0x1800ae8e9  call    ??1CRTL_ALLOCATION_LIST@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST(void)
0x1800ae8ee  jmp     loc_1800AED1E
0x1800ae8f3  lea     rdx, [rsp+150h+var_D8]
0x1800ae8f8  call    RtlCreateDirectIsolatedFilesystem
0x1800ae8fd  mov     ebx, eax
0x1800ae8ff  test    eax, eax
0x1800ae901  jns     loc_1800AE991
0x1800ae907  mov     [rsp+150h+var_110], 493h
0x1800ae90f  mov     r8d, ebx
0x1800ae912  lea     rdx, [rsp+150h+var_118]
0x1800ae917  call    ?FrameReportNtStatusErrorPropagation@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(Windows::ErrorHandling::CCallSite const &,long)
0x1800ae91c  mov     ecx, ebx; this
0x1800ae91e  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ae923  mov     r8, rsi
0x1800ae926  mov     edi, eax
0x1800ae928  call    RtlFreeHeap
0x1800ae92d  mov     r10, qword ptr [rsp+150h+var_D8]
0x1800ae932  test    r10, r10
0x1800ae935  jz      loc_1800AEB79
0x1800ae93b  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800ae942  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ae949  mov     [rsp+150h+var_118], rax
0x1800ae94e  mov     [rsp+150h+dwExceptionCode], 0C00000E5h
0x1800ae956  test    r10, r10
0x1800ae959  jz      loc_1800AEB4A
0x1800ae95f  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800ae966  test    r11, r11
0x1800ae969  jz      loc_1800AEB4F
0x1800ae96f  mov     rdx, r11
0x1800ae972  mov     rcx, r10
0x1800ae975  call    RtlIsTypeSafeHandleValid
0x1800ae97a  test    al, al
0x1800ae97c  jz      loc_1800AEB4F
0x1800ae982  mov     ecx, [r11]
0x1800ae985  mov     rdx, r10
0x1800ae988  mov     rax, [r11+20h]
0x1800ae98c  jmp     loc_1800AEB45
0x1800ae991  mov     rdx, rsi
0x1800ae994  call    RtlGenerateComponentStoreLockIdentifier
0x1800ae999  mov     ebx, eax
0x1800ae99b  test    eax, eax
0x1800ae99d  jns     short loc_1800AE9AC
0x1800ae99f  mov     [rsp+150h+var_110], 494h
0x1800ae9a7  jmp     loc_1800AE90F
0x1800ae9ac  lea     rdi, [rsi+20h]
0x1800ae9b0  mov     rdx, rdi
0x1800ae9b3  call    RtlGenerateComponentStoreLockIdentifier
0x1800ae9b8  mov     ebx, eax
0x1800ae9ba  test    eax, eax
0x1800ae9bc  jns     short loc_1800AE9CB
0x1800ae9be  mov     [rsp+150h+var_110], 495h
0x1800ae9c6  jmp     loc_1800AE90F
0x1800ae9cb  mov     rax, [rsp+150h+var_120]
0x1800ae9d0  lea     r9, [rbp+50h+var_68]
0x1800ae9d4  mov     rdx, [r13+10h]
0x1800ae9d8  mov     [rbp+50h+var_68], rax
0x1800ae9dc  lea     rax, [rsp+150h+var_100]
0x1800ae9e1  mov     [rsp+150h+var_130], rax
0x1800ae9e6  call    RtlGuessComponentStoreApplicationPaths
0x1800ae9eb  mov     ebx, eax
0x1800ae9ed  test    eax, eax
0x1800ae9ef  jns     short loc_1800AE9FE
0x1800ae9f1  mov     [rsp+150h+var_110], 49Dh
0x1800ae9f9  jmp     loc_1800AE90F
0x1800ae9fe  mov     rdx, [rbp+50h+var_78]
0x1800aea02  mov     r9d, 2; int
0x1800aea08  mov     rcx, qword ptr [rbp+50h+var_80]; int
0x1800aea0c  mov     rbx, qword ptr [rsp+150h+var_D8]
0x1800aea11  mov     qword ptr [rcx], 28h ; '('
0x1800aea18  mov     rax, [rsp+150h+var_120]
0x1800aea1d  mov     [rcx+8], rax
0x1800aea21  lea     rax, [rbp+50h+var_70]
0x1800aea25  mov     [rcx+10h], rsi
0x1800aea29  mov     qword ptr [rdx], 40h ; '@'
0x1800aea30  mov     [rdx+20h], rsi
0x1800aea34  mov     [rdx+28h], rdi
0x1800aea38  movups  xmm0, [rsp+150h+var_100]
0x1800aea3d  mov     [rsp+150h+var_128], rax; void *
0x1800aea42  lea     rax, [rbp+50h+var_60]
0x1800aea46  movsd   xmm1, [rsp+150h+var_F0]
0x1800aea4c  movups  xmmword ptr [rdx+8], xmm0
0x1800aea50  mov     [rsp+150h+var_130], rax; __int64
0x1800aea55  movsd   qword ptr [rdx+18h], xmm1
0x1800aea5a  mov     r8, [r13+10h]; int
0x1800aea5e  mov     [rbp+50h+var_48], rdx
0x1800aea62  mov     rdx, rbx; int
0x1800aea65  mov     [rbp+50h+var_58], rcx
0x1800aea69  mov     dword ptr [rbp+50h+var_60], 0Dh
0x1800aea70  mov     [rbp+50h+var_50], 0Fh
0x1800aea77  call    RtlTransactComponentStore
0x1800aea7c  mov     edi, eax
0x1800aea7e  test    eax, eax
0x1800aea80  jns     short loc_1800AEAA2
0x1800aea82  mov     r8d, eax
0x1800aea85  mov     [rsp+150h+var_110], 4B5h
0x1800aea8d  lea     rdx, [rsp+150h+var_118]
0x1800aea92  call    ?FrameReportNtStatusErrorPropagation@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(Windows::ErrorHandling::CCallSite const &,long)
0x1800aea97  mov     ecx, edi; this
0x1800aea99  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800aea9e  mov     edi, eax
0x1800aeaa0  jmp     short loc_1800AEAF8
0x1800aeaa2  cmp     [rbp+50h+var_70], 1
0x1800aeaa6  jnz     short loc_1800AEADF
0x1800aeaa8  cmp     [rbp+50h+var_6C], 1
0x1800aeaac  jnz     short loc_1800AEADF
  ... truncated ...
```
