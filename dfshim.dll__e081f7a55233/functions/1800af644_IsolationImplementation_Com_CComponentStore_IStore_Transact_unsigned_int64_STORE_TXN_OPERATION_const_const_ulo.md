# IsolationImplementation::Com::CComponentStore::IStore_Transact(unsigned __int64,_STORE_TXN_OPERATION const * const,ulong *,long *)

- ea: `0x1800af644`
- end: `0x1800afe68`
- name: `?IStore_Transact@CComponentStore@Com@IsolationImplementation@@IEAAJ_KQEBU_STORE_TXN_OPERATION@@PEAKPEAJ@Z`
- size: `2084`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned __int64, const struct _STORE_TXN_OPERATION *const, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x1800b0530`

## callees

- `0x180006991`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012538`
- `0x180012820`
- `0x180012910`
- `0x180012acc`
- `0x180012b38`
- `0x180016f8c`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18002dde4`
- `0x180031cec`
- `0x180031ea0`
- `0x180032084`
- `0x180032214`
- `0x1800324fc`
- `0x1800326e4`
- `0x180032918`
- `0x180032acc`
- `0x180039c1c`
- `0x1800a9868`
- `0x1800af644`
- `0x18012a020`
- `0x18012a030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af735`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af77a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800afaca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800afb08`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800afe33`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af735`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af77a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800afaca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800afb08`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800afe33`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af6a8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800afd41`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800afdb8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af6a8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800afd41`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800afdb8`

## string_xrefs

- `0x1800af661`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af8a9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af8da`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af90b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af93c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af96d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af99a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800af9c7`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800afce1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800afd4a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_Transact(
        IsolationImplementation::Com::CComponentStore *this,
        unsigned __int64 a2,
        const struct _STORE_TXN_OPERATION *const a3,
        unsigned int *a4,
        int *a5)
{
  __int64 v8; // r14
  int v9; // eax
  unsigned int v10; // edi
  int v11; // edx
  unsigned int v12; // edi
  int *v13; // rdi
  unsigned __int64 i; // rcx
  HANDLE v15; // rdi
  HANDLE v16; // rdi
  int AllocationListArray; // edi
  const struct Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *v18; // r13
  int v19; // edi
  struct Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *v20; // r9
  const struct _STORE_PIN_DEPLOYMENT *v21; // r8
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  unsigned int *v31; // rdi
  int v32; // esi
  __int64 v33; // rcx
  int v34; // edx
  void (__fastcall *v35)(LPVOID *); // rax
  HANDLE v36; // rax
  LPVOID *v37; // rbx
  HANDLE v38; // rbx
  HANDLE v39; // rdi
  void (__fastcall *v40)(LPVOID *); // rax
  HANDLE v41; // rax
  LPVOID *v42; // rbx
  void (__fastcall *v43)(LPVOID *); // rax
  HANDLE v44; // rax
  LPVOID *v45; // rbx
  void (__fastcall *v46)(LPVOID *); // rax
  HANDLE v47; // rax
  LPVOID *v48; // rbx
  void (__fastcall *v49)(LPVOID *); // rax
  HANDLE v50; // rax
  LPVOID *v51; // rbx
  void (__fastcall *v52)(LPVOID *); // rax
  HANDLE v53; // rax
  LPVOID *v54; // rbx
  void (__fastcall *v55)(LPVOID *); // rax
  HANDLE v56; // rax
  LPVOID *v57; // rbx
  void (__fastcall *v58)(LPVOID *); // rax
  HANDLE v59; // rax
  LPVOID *v60; // rbx
  int v61; // edx
  void (__fastcall *v62)(LPVOID *); // rax
  HANDLE v63; // rax
  LPVOID *v64; // rbx
  int v65; // edx
  void (__fastcall *v66)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v68; // rbx
  unsigned int v70; // [rsp+20h] [rbp-81h]
  unsigned int v71; // [rsp+20h] [rbp-81h]
  unsigned int v72; // [rsp+20h] [rbp-81h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-71h] BYREF
  HANDLE hMutex; // [rsp+40h] [rbp-61h] BYREF
  __int16 v75; // [rsp+48h] [rbp-59h]
  _BYTE v76[64]; // [rsp+50h] [rbp-51h] BYREF
  const char *v77; // [rsp+90h] [rbp-11h] BYREF
  int v78; // [rsp+98h] [rbp-9h]
  unsigned int v79; // [rsp+A0h] [rbp-1h]
  struct Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *v80[9]; // [rsp+A8h] [rbp+7h] BYREF

  v79 = -2147023537;
  v77 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
  v8 = 0;
  hMutex = 0;
  v75 = 0;
  v9 = StoreLock::Lock((StoreLock *)&hMutex);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x140,
      v10,
      v70);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v11);
    goto LABEL_125;
  }
  if ( a4 && a2 )
    memset_thunk_772440563353939046(a4, 0, 4 * a2);
  if ( !a5 )
  {
    if ( a2 )
      goto LABEL_13;
LABEL_22:
    v16 = hMutex;
    v78 = 334;
    if ( hMutex )
    {
      if ( (_BYTE)v75 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v75) = 0;
      }
      CloseHandle_0(v16);
      hMutex = 0;
    }
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v77);
    return v79;
  }
  if ( !a2 )
    goto LABEL_22;
  v13 = a5;
  for ( i = a2; i; --i )
    *v13++ = 1;
LABEL_13:
  if ( !a3 )
  {
    v78 = 335;
LABEL_15:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v77);
    v15 = hMutex;
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
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
    return v79;
  }
  if ( !a4 )
  {
    v78 = 336;
    goto LABEL_15;
  }
  if ( !a5 )
  {
    v78 = 337;
    goto LABEL_15;
  }
  v80[0] = 0;
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  AllocationListArray = RtlAllocateAllocationListArray(
                          (unsigned int)lpMem,
                          a2,
                          16,
                          (unsigned int)Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                          (__int64)v80);
  if ( AllocationListArray < 0 )
  {
    if ( AllocationListArray == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x157,
      AllocationListArray,
      v71);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
            (Windows::ErrorHandling::COM *)(unsigned int)AllocationListArray,
            v65);
    while ( 1 )
    {
      v68 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v68 == lpMem )
        break;
      v66 = (void (__fastcall *)(LPVOID *))v68[2];
      if ( v66 )
        v66(v68 + 3);
      ProcessHeap_0 = GetProcessHeap_0();
      HeapFree_0(ProcessHeap_0, 0, v68);
    }
LABEL_125:
    v38 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v75 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v75) = 0;
      }
      goto LABEL_128;
    }
    goto LABEL_129;
  }
  v18 = v80[0];
  v80[0] = 0;
  v19 = RtlAllocateAllocationListArray(
          (unsigned int)lpMem,
          a2,
          4,
          (unsigned int)Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
          (__int64)v80);
  if ( v19 < 0 )
  {
    if ( v19 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x158,
      v19,
      v72);
    v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v19, v61);
    while ( 1 )
    {
      v64 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v64 == lpMem )
        break;
      v62 = (void (__fastcall *)(LPVOID *))v64[2];
      if ( v62 )
        v62(v64 + 3);
      v63 = GetProcessHeap_0();
      HeapFree_0(v63, 0, v64);
    }
    goto LABEL_125;
  }
  while ( 1 )
  {
    v21 = (const struct Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)((char *)v18 + 16 * v8);
    if ( *((_DWORD *)a3 + 4 * v8) == 20 )
      break;
    switch ( *((_DWORD *)a3 + 4 * v8) )
    {
      case 0x15:
        v29 = IsolationImplementation::Com::ConvertIn(
                (IsolationImplementation::Com *)lpMem,
                *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
                v21,
                v20);
        v12 = v29;
        if ( v29 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x16E,
            v29,
            (int)v20);
          while ( 1 )
          {
            v57 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v57 == lpMem )
              break;
            v55 = (void (__fastcall *)(LPVOID *))v57[2];
            if ( v55 )
              v55(v57 + 3);
            v56 = GetProcessHeap_0();
            HeapFree_0(v56, 0, v57);
          }
          goto LABEL_64;
        }
        break;
      case 0x16:
        v28 = IsolationImplementation::Com::ConvertIn(
                (IsolationImplementation::Com *)lpMem,
                *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
                v21,
                v20);
        v12 = v28;
        if ( v28 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x172,
            v28,
            (int)v20);
          while ( 1 )
          {
            v54 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v54 == lpMem )
              break;
            v52 = (void (__fastcall *)(LPVOID *))v54[2];
            if ( v52 )
              v52(v54 + 3);
            v53 = GetProcessHeap_0();
            HeapFree_0(v53, 0, v54);
          }
          goto LABEL_64;
        }
        break;
      case 0x17:
        v27 = IsolationImplementation::Com::ConvertIn(
                (IsolationImplementation::Com *)lpMem,
                *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
                v21,
                v20);
        v12 = v27;
        if ( v27 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x16A,
            v27,
            (int)v20);
          while ( 1 )
          {
            v51 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v51 == lpMem )
              break;
            v49 = (void (__fastcall *)(LPVOID *))v51[2];
            if ( v49 )
              v49(v51 + 3);
            v50 = GetProcessHeap_0();
            HeapFree_0(v50, 0, v51);
          }
          goto LABEL_64;
        }
        break;
      case 0x18:
        v26 = IsolationImplementation::Com::ConvertIn(
                (IsolationImplementation::Com *)lpMem,
                *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
                v21,
                v20);
        v12 = v26;
        if ( v26 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x176,
            v26,
            (int)v20);
          while ( 1 )
          {
            v48 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v48 == lpMem )
              break;
            v46 = (void (__fastcall *)(LPVOID *))v48[2];
            if ( v46 )
              v46(v48 + 3);
            v47 = GetProcessHeap_0();
            HeapFree_0(v47, 0, v48);
          }
          goto LABEL_64;
        }
        break;
      case 0x19:
        v25 = IsolationImplementation::Com::ConvertIn(
                (IsolationImplementation::Com *)lpMem,
                *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
                v21,
                v20);
        v12 = v25;
        if ( v25 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x17A,
            v25,
            (int)v20);
          while ( 1 )
          {
            v45 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v45 == lpMem )
              break;
            v43 = (void (__fastcall *)(LPVOID *))v45[2];
            if ( v43 )
              v43(v45 + 3);
            v44 = GetProcessHeap_0();
            HeapFree_0(v44, 0, v45);
          }
          goto LABEL_64;
        }
        break;
      case 0x1A:
        v24 = IsolationImplementation::Com::ConvertIn(
                (IsolationImplementation::Com *)lpMem,
                *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
                v21,
                v20);
        v12 = v24;
        if ( v24 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x17E,
            v24,
            (int)v20);
          while ( 1 )
          {
            v42 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v42 == lpMem )
              break;
            v40 = (void (__fastcall *)(LPVOID *))v42[2];
            if ( v40 )
              v40(v42 + 3);
            v41 = GetProcessHeap_0();
            HeapFree_0(v41, 0, v42);
          }
          goto LABEL_64;
        }
        break;
      case 0x1B:
        v22 = IsolationImplementation::Com::ConvertIn(
                (IsolationImplementation::Com *)lpMem,
                *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
                v21,
                v20);
        v12 = v22;
        if ( v22 < 0 )
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x182,
            v22,
            (int)v20);
          while ( 1 )
          {
            v37 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v37 == lpMem )
              break;
            v35 = (void (__fastcall *)(LPVOID *))v37[2];
            if ( v35 )
              v35(v37 + 3);
            v36 = GetProcessHeap_0();
            HeapFree_0(v36, 0, v37);
          }
          goto LABEL_64;
        }
        break;
      default:
        v78 = 390;
        Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
        v39 = hMutex;
        if ( hMutex )
        {
          if ( (_BYTE)v75 )
          {
            ReleaseMutex(hMutex);
            LOBYTE(v75) = 0;
          }
          CloseHandle_0(v39);
          hMutex = 0;
        }
        BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
        Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
          &v77,
          &v77);
        return v79;
    }
LABEL_56:
    if ( ++v8 >= a2 )
    {
      v31 = (unsigned int *)v80[0];
      v32 = RtlTransactComponentStore(v23, *((_QWORD *)this + 3), *((_QWORD *)this + 2), a2, (__int64)v18, v80[0]);
      ConvertDispositions(a2, v18, v31, a4, a5, v32);
      if ( v32 >= 0 )
      {
        v12 = 0;
      }
      else
      {
        v78 = 409;
        Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(
          v33,
          &v77,
          (unsigned int)v32);
        v12 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                (Windows::ErrorHandling::COM *)(unsigned int)v32,
                v34);
      }
      Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
      goto LABEL_125;
    }
  }
  v30 = IsolationImplementation::Com::ConvertIn(
          (IsolationImplementation::Com *)lpMem,
          *((struct _RTL_ALLOCATION_LIST **)a3 + 2 * v8 + 1),
          v21,
          v20);
  v12 = v30;
  if ( v30 >= 0 )
    goto LABEL_56;
  Windows::ErrorHandling::COM::ReportErrorPropagation(
    (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
    (const char *)0x166,
    v30,
    (int)v20);
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
LABEL_64:
  v38 = hMutex;
  if ( !hMutex )
    goto LABEL_129;
  if ( (_BYTE)v75 )
  {
    ReleaseMutex(hMutex);
    LOBYTE(v75) = 0;
  }
LABEL_128:
  CloseHandle_0(v38);
  hMutex = 0;
LABEL_129:
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v76);
  return v12;
}

```

## disassembly

```asm
0x1800af644  mov     [rsp-8+arg_0], rcx
0x1800af649  push    rbp
0x1800af64a  push    rbx
0x1800af64b  push    rsi
0x1800af64c  push    rdi
0x1800af64d  push    r12
0x1800af64f  push    r13
0x1800af651  push    r14
0x1800af653  push    r15
0x1800af655  lea     rbp, [rsp-17h]
0x1800af65a  sub     rsp, 0B8h
0x1800af661  lea     r13, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af668  mov     [rbp+4Fh+var_50], 8007054Fh
0x1800af66f  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800af673  mov     [rbp+4Fh+var_60], r13
0x1800af677  mov     r12, r9
0x1800af67a  mov     rsi, r8
0x1800af67d  mov     rbx, rdx
0x1800af680  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800af685  xor     r14d, r14d
0x1800af688  lea     rcx, [rbp+4Fh+hMutex]; this
0x1800af68c  mov     [rbp+4Fh+hMutex], r14
0x1800af690  mov     [rbp+4Fh+var_A8], r14w
0x1800af695  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800af69a  mov     edi, eax
0x1800af69c  test    eax, eax
0x1800af69e  jns     short loc_1800AF6D4
0x1800af6a0  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800af6a6  jnz     short loc_1800AF6AE
0x1800af6a8  call    cs:__imp_DebugBreak
0x1800af6ae  mov     r9d, edi; int
0x1800af6b1  lea     rcx, aStatusPropagat; "Status propagated"
0x1800af6b8  mov     r8d, 140h; char *
0x1800af6be  mov     rdx, r13; char *
0x1800af6c1  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800af6c6  mov     ecx, edi; this
0x1800af6c8  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800af6cd  mov     edi, eax
0x1800af6cf  jmp     loc_1800AFE21
0x1800af6d4  test    r12, r12
0x1800af6d7  jz      short loc_1800AF6EF
0x1800af6d9  test    rbx, rbx
0x1800af6dc  jz      short loc_1800AF6EF
0x1800af6de  mov     r8, rbx
0x1800af6e1  xor     edx, edx; Val
0x1800af6e3  shl     r8, 2; Size
0x1800af6e7  mov     rcx, r12; void *
0x1800af6ea  call    memset$thunk$772440563353939046
0x1800af6ef  mov     r15, [rbp+4Fh+arg_20]
0x1800af6f3  test    r15, r15
0x1800af6f6  jz      short loc_1800AF75C
0x1800af6f8  test    rbx, rbx
0x1800af6fb  jz      short loc_1800AF761
0x1800af6fd  mov     rdi, r15
0x1800af700  mov     eax, 1
0x1800af705  mov     rcx, rbx
0x1800af708  rep stosd
0x1800af70a  test    rsi, rsi
0x1800af70d  jnz     loc_1800AF7A4
0x1800af713  mov     [rbp+4Fh+var_58], 14Fh
0x1800af71a  lea     rcx, [rbp+4Fh+var_60]
0x1800af71e  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800af723  mov     rdi, [rbp+4Fh+hMutex]
0x1800af727  test    rdi, rdi
0x1800af72a  jz      short loc_1800AF74B
0x1800af72c  cmp     byte ptr [rbp+4Fh+var_A8], r14b
0x1800af730  jz      short loc_1800AF73F
0x1800af732  mov     rcx, rdi; hMutex
0x1800af735  call    cs:__imp_ReleaseMutex
0x1800af73b  mov     byte ptr [rbp+4Fh+var_A8], r14b
0x1800af73f  mov     rcx, rdi; hObject
0x1800af742  call    CloseHandle_0
0x1800af747  mov     [rbp+4Fh+hMutex], r14
0x1800af74b  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800af74f  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800af754  mov     edi, [rbp+4Fh+var_50]
0x1800af757  jmp     loc_1800AFE52
0x1800af75c  test    rbx, rbx
0x1800af75f  jnz     short loc_1800AF70A
0x1800af761  mov     rdi, [rbp+4Fh+hMutex]
0x1800af765  mov     [rbp+4Fh+var_58], 14Eh
0x1800af76c  test    rdi, rdi
0x1800af76f  jz      short loc_1800AF790
0x1800af771  cmp     byte ptr [rbp+4Fh+var_A8], r14b
0x1800af775  jz      short loc_1800AF784
0x1800af777  mov     rcx, rdi; hMutex
0x1800af77a  call    cs:__imp_ReleaseMutex
0x1800af780  mov     byte ptr [rbp+4Fh+var_A8], r14b
0x1800af784  mov     rcx, rdi; hObject
0x1800af787  call    CloseHandle_0
0x1800af78c  mov     [rbp+4Fh+hMutex], r14
0x1800af790  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800af794  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800af799  lea     rcx, [rbp+4Fh+var_60]
0x1800af79d  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800af7a2  jmp     short loc_1800AF754
0x1800af7a4  test    r12, r12
0x1800af7a7  jnz     short loc_1800AF7B5
0x1800af7a9  mov     [rbp+4Fh+var_58], 150h
0x1800af7b0  jmp     loc_1800AF71A
0x1800af7b5  test    r15, r15
0x1800af7b8  jnz     short loc_1800AF7C6
0x1800af7ba  mov     [rbp+4Fh+var_58], 151h
0x1800af7c1  jmp     loc_1800AF71A
0x1800af7c6  lea     rax, [rbp+4Fh+lpMem]
0x1800af7ca  mov     [rbp+4Fh+var_48], r14
0x1800af7ce  mov     [rbp+4Fh+var_B8], rax
0x1800af7d2  lea     r9, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800af7d9  lea     rax, [rbp+4Fh+lpMem]
0x1800af7dd  mov     r8d, 10h
0x1800af7e3  mov     [rbp+4Fh+lpMem], rax
0x1800af7e7  lea     rcx, [rbp+4Fh+lpMem]
0x1800af7eb  lea     rax, [rbp+4Fh+var_48]
0x1800af7ef  mov     rdx, rbx
0x1800af7f2  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x1800af7f7  call    RtlAllocateAllocationListArray
0x1800af7fc  mov     edi, eax
0x1800af7fe  test    eax, eax
0x1800af800  js      loc_1800AFDB0
0x1800af806  mov     r13, [rbp+4Fh+var_48]
0x1800af80a  lea     rax, [rbp+4Fh+var_48]
0x1800af80e  lea     r9, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800af815  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x1800af81a  mov     r8d, 4
0x1800af820  mov     [rbp+4Fh+var_48], r14
0x1800af824  mov     rdx, rbx
0x1800af827  lea     rcx, [rbp+4Fh+lpMem]
0x1800af82b  call    RtlAllocateAllocationListArray
0x1800af830  mov     edi, eax
0x1800af832  test    eax, eax
0x1800af834  js      loc_1800AFD39
0x1800af83a  mov     rdx, r14
0x1800af83d  add     rdx, rdx
0x1800af840  mov     ecx, [rsi+rdx*8]
0x1800af843  lea     r8, ds:0[rdx*8]
0x1800af84b  add     r8, r13; struct _STORE_STAGE_COMPONENT *
0x1800af84e  sub     ecx, 14h
0x1800af851  jz      loc_1800AF9DD
0x1800af857  sub     ecx, 1
0x1800af85a  jz      loc_1800AF9B0
0x1800af860  sub     ecx, 1
0x1800af863  jz      loc_1800AF983
0x1800af869  sub     ecx, 1
0x1800af86c  jz      loc_1800AF952
0x1800af872  sub     ecx, 1
0x1800af875  jz      loc_1800AF921
0x1800af87b  sub     ecx, 1
0x1800af87e  jz      short loc_1800AF8F0
0x1800af880  sub     ecx, 1
0x1800af883  jz      short loc_1800AF8BF
0x1800af885  cmp     ecx, 1
0x1800af888  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af88c  jnz     loc_1800AFAE9
0x1800af892  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af897  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_SCAVENGE@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_SCAVENGE const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af89c  mov     edi, eax
0x1800af89e  test    eax, eax
0x1800af8a0  jns     loc_1800AF9F5
0x1800af8a6  mov     r8d, eax; int
0x1800af8a9  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af8b0  mov     edx, 182h; char *
0x1800af8b5  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800af8ba  jmp     loc_1800AFA98
0x1800af8bf  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af8c4  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af8c8  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_SET_DEPLOYMENT_METADATA@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_SET_DEPLOYMENT_METADATA const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af8cd  mov     edi, eax
0x1800af8cf  test    eax, eax
0x1800af8d1  jns     loc_1800AF9F5
0x1800af8d7  mov     r8d, eax; int
0x1800af8da  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af8e1  mov     edx, 17Eh; char *
0x1800af8e6  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800af8eb  jmp     loc_1800AFB5C
0x1800af8f0  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af8f5  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af8f9  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_UNINSTALL_DEPLOYMENT@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_UNINSTALL_DEPLOYMENT const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af8fe  mov     edi, eax
0x1800af900  test    eax, eax
0x1800af902  jns     loc_1800AF9F5
0x1800af908  mov     r8d, eax; int
0x1800af90b  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af912  mov     edx, 17Ah; char *
0x1800af917  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800af91c  jmp     loc_1800AFBA1
0x1800af921  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af926  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af92a  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_INSTALL_DEPLOYMENT@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_INSTALL_DEPLOYMENT const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af92f  mov     edi, eax
0x1800af931  test    eax, eax
0x1800af933  jns     loc_1800AF9F5
0x1800af939  mov     r8d, eax; int
0x1800af93c  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af943  mov     edx, 176h; char *
0x1800af948  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800af94d  jmp     loc_1800AFBE6
0x1800af952  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af957  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af95b  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_STAGE_COMPONENT_FILE@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_STAGE_COMPONENT_FILE const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af960  mov     edi, eax
0x1800af962  test    eax, eax
0x1800af964  jns     loc_1800AF9F5
0x1800af96a  mov     r8d, eax; int
0x1800af96d  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af974  mov     edx, 16Ah; char *
0x1800af979  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800af97e  jmp     loc_1800AFC2B
0x1800af983  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af988  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af98c  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_UNPIN_DEPLOYMENT@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_UNPIN_DEPLOYMENT const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af991  mov     edi, eax
0x1800af993  test    eax, eax
0x1800af995  jns     short loc_1800AF9F5
0x1800af997  mov     r8d, eax; int
0x1800af99a  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af9a1  mov     edx, 172h; char *
0x1800af9a6  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800af9ab  jmp     loc_1800AFC70
0x1800af9b0  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af9b5  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af9b9  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_PIN_DEPLOYMENT@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_PIN_DEPLOYMENT const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af9be  mov     edi, eax
0x1800af9c0  test    eax, eax
0x1800af9c2  jns     short loc_1800AF9F5
0x1800af9c4  mov     r8d, eax; int
0x1800af9c7  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af9ce  mov     edx, 16Eh; char *
0x1800af9d3  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800af9d8  jmp     loc_1800AFCB5
0x1800af9dd  mov     rdx, [rsi+rdx*8+8]; struct _RTL_ALLOCATION_LIST *
0x1800af9e2  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800af9e6  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_STAGE_COMPONENT@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_STAGE_COMPONENT const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)
0x1800af9eb  mov     edi, eax
0x1800af9ed  test    eax, eax
0x1800af9ef  js      loc_1800AFCDE
0x1800af9f5  inc     r14
0x1800af9f8  cmp     r14, rbx
0x1800af9fb  jb      loc_1800AF83A
0x1800afa01  mov     rax, [rbp+4Fh+arg_0]
0x1800afa05  mov     r9, rbx; int
0x1800afa08  mov     rdi, [rbp+4Fh+var_48]
0x1800afa0c  mov     [rsp+0F0h+var_C8], rdi; void *
0x1800afa11  mov     [rsp+0F0h+var_D0], r13; __int64
0x1800afa16  mov     r8, [rax+10h]; int
0x1800afa1a  mov     rdx, [rax+18h]; int
0x1800afa1e  call    RtlTransactComponentStore
0x1800afa23  mov     dword ptr [rsp+0F0h+var_C8], eax; int
0x1800afa27  mov     r9, r12; unsigned int *
0x1800afa2a  mov     r8, rdi; unsigned int *
0x1800afa2d  mov     [rsp+0F0h+var_D0], r15; int *
0x1800afa32  mov     rdx, r13; struct Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *
0x1800afa35  mov     rcx, rbx; unsigned __int64
0x1800afa38  mov     esi, eax
0x1800afa3a  call    ?ConvertDispositions@@YAX_KPEBU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@QEAK2QEAJJ@Z; ConvertDispositions(unsigned __int64,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ const *,ulong * const,ulong * const,long * const,long)
0x1800afa3f  xor     r14d, r14d
0x1800afa42  test    esi, esi
0x1800afa44  jns     loc_1800AFCD6
0x1800afa4a  mov     r8d, esi
0x1800afa4d  mov     [rbp+4Fh+var_58], 199h
0x1800afa54  lea     rdx, [rbp+4Fh+var_60]
0x1800afa58  call    ?FrameReportNtStatusErrorPropagation@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(Windows::ErrorHandling::CCallSite const &,long)
0x1800afa5d  mov     ecx, esi; this
0x1800afa5f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800afa64  mov     edi, eax
0x1800afa66  lea     rcx, [rbp+4Fh+lpMem]; this
0x1800afa6a  call    ??1CRTL_ALLOCATION_LIST@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST(void)
0x1800afa6f  jmp     loc_1800AFE21
0x1800afa74  mov     rax, [rbx+10h]
0x1800afa78  test    rax, rax
0x1800afa7b  jz      short loc_1800AFA86
0x1800afa7d  lea     rcx, [rbx+18h]
0x1800afa81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afa86  call    GetProcessHeap_0
0x1800afa8b  mov     r8, rbx; lpMem
0x1800afa8e  xor     edx, edx; dwFlags
0x1800afa90  mov     rcx, rax; hHeap
0x1800afa93  call    HeapFree_0
0x1800afa98  mov     rbx, [rbp+4Fh+lpMem]
0x1800afa9c  lea     rcx, [rbp+4Fh+lpMem]
0x1800afaa0  mov     rax, [rbx]
0x1800afaa3  mov     [rbp+4Fh+lpMem], rax
0x1800afaa7  mov     [rax+8], rcx
0x1800afaab  lea     rax, [rbp+4Fh+lpMem]
0x1800afaaf  cmp     rbx, rax
0x1800afab2  jnz     short loc_1800AFA74
0x1800afab4  mov     rbx, [rbp+4Fh+hMutex]
0x1800afab8  test    rbx, rbx
0x1800afabb  jz      loc_1800AFE49
0x1800afac1  cmp     byte ptr [rbp+4Fh+var_A8], 0
0x1800afac5  jz      short loc_1800AFAD4
0x1800afac7  mov     rcx, rbx; hMutex
0x1800afaca  call    cs:__imp_ReleaseMutex
0x1800afad0  mov     byte ptr [rbp+4Fh+var_A8], 0
0x1800afad4  mov     rcx, rbx; hObject
0x1800afad7  call    CloseHandle_0
0x1800afadc  mov     [rbp+4Fh+hMutex], 0
0x1800afae4  jmp     loc_1800AFE49
0x1800afae9  mov     [rbp+4Fh+var_58], 186h
0x1800afaf0  call    ??1CRTL_ALLOCATION_LIST@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST(void)
0x1800afaf5  mov     rdi, [rbp+4Fh+hMutex]
  ... truncated ...
```
