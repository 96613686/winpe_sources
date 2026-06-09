# IsolationImplementation::Com::CComponentStore::IStore_ReleaseApplicationPath(void *)

- ea: `0x1800af0d8`
- end: `0x1800af63b`
- name: `?IStore_ReleaseApplicationPath@CComponentStore@Com@IsolationImplementation@@IEAAJPEAX@Z`
- size: `1379`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, void *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800b03f0`

## callees

- `0x180006991`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012538`
- `0x180012b1c`
- `0x180012b38`
- `0x180016f8c`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x1800237b8`
- `0x18002decc`
- `0x180039c1c`
- `0x180042f10`
- `0x18004f2dc`
- `0x1800af0d8`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af18d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af5fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af18d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800af5fe`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af13a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af22e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af383`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af4fe`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af571`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af13a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af22e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af383`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af4fe`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800af571`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800af2bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800af41c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800af4da`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800af2bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800af41c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800af4da`

## string_xrefs

- `0x1800af269`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800af3ba`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800af478`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800af100`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_ReleaseApplicationPath(
        IsolationImplementation::Com::CComponentStore *this,
        char *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // edx
  DWORD v7; // edi
  HANDLE v8; // rbx
  int v9; // ebx
  __int64 v10; // rcx
  int AllocationListMemory; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // edx
  __int64 v15; // r10
  unsigned int *v16; // r11
  int v17; // ecx
  void (__fastcall *v18)(LPVOID *); // rax
  HANDLE v19; // rax
  LPVOID *v20; // rbx
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // r8
  int v25; // eax
  unsigned int v26; // edi
  int v27; // edx
  unsigned int *v28; // r10
  int v29; // ecx
  void (__fastcall *v30)(LPVOID *); // rax
  HANDLE v31; // rax
  LPVOID *v32; // rbx
  unsigned int *v33; // r10
  int v34; // ecx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // edx
  void (__fastcall *v38)(LPVOID *); // rax
  HANDLE v39; // rax
  LPVOID *v40; // rbx
  int v41; // edx
  void (__fastcall *v42)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v44; // rbx
  HANDLE v45; // rax
  HANDLE v46; // rbx
  unsigned int v48; // [rsp+20h] [rbp-89h]
  unsigned int v49; // [rsp+20h] [rbp-89h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-79h] BYREF
  const char *v51; // [rsp+40h] [rbp-69h] BYREF
  int v52; // [rsp+48h] [rbp-61h]
  DWORD dwExceptionCode; // [rsp+50h] [rbp-59h]
  HANDLE hMutex; // [rsp+60h] [rbp-49h] BYREF
  __int16 v55; // [rsp+68h] [rbp-41h]
  _BYTE v56[64]; // [rsp+70h] [rbp-39h] BYREF
  int v57[2]; // [rsp+B0h] [rbp+7h] BYREF
  unsigned int v58; // [rsp+B8h] [rbp+Fh] BYREF
  _QWORD *v59; // [rsp+C0h] [rbp+17h]
  int v60; // [rsp+C8h] [rbp+1Fh]
  _QWORD *v61; // [rsp+D0h] [rbp+27h]
  __int64 v62; // [rsp+120h] [rbp+77h] BYREF
  _QWORD *v63; // [rsp+128h] [rbp+7Fh] BYREF

  dwExceptionCode = -2147023537;
  v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v56);
  hMutex = 0;
  v55 = 0;
  v4 = StoreLock::Lock((StoreLock *)&hMutex);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( v4 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x4CD,
      v5,
      v48);
    v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v5, v6);
    goto LABEL_67;
  }
  if ( a2 )
  {
    v62 = 0;
    lpMem[1] = lpMem;
    v63 = 0;
    lpMem[0] = lpMem;
    v9 = RtlAllocateAllocationListMemory(
           lpMem,
           32,
           Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
           &v63);
    if ( v9 < 0 )
    {
      if ( v9 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x4DD,
        v9,
        v48);
      v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v9, v41);
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
        ProcessHeap_0 = GetProcessHeap_0();
        HeapFree_0(ProcessHeap_0, 0, v44);
      }
    }
    else
    {
      *(_QWORD *)v57 = 0;
      AllocationListMemory = RtlAllocateAllocationListMemory(
                               lpMem,
                               32,
                               Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                               v57);
      if ( AllocationListMemory < 0 )
      {
        if ( AllocationListMemory == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x4DE,
          AllocationListMemory,
          v48);
        v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
               (Windows::ErrorHandling::COM *)(unsigned int)AllocationListMemory,
               v37);
        while ( 1 )
        {
          v40 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v40 == lpMem )
            break;
          v38 = (void (__fastcall *)(LPVOID *))v40[2];
          if ( v38 )
            v38(v40 + 3);
          v39 = GetProcessHeap_0();
          HeapFree_0(v39, 0, v40);
        }
      }
      else
      {
        v12 = RtlCreateDirectIsolatedFilesystem(v10, &v62);
        v13 = v12;
        if ( v12 >= 0 )
        {
          v21 = v63;
          v22 = *(_QWORD **)v57;
          v23 = v62;
          *v63 = 32;
          v21[1] = a2;
          v22[1] = a2 + 32;
          *v22 = 32;
          v24 = *((_QWORD *)this + 2);
          v61 = v21;
          v59 = v22;
          v58 = 16;
          v60 = 14;
          v25 = RtlTransactComponentStore((int)v22, v23, v24, 2, (__int64)&v58, 0);
          v26 = v25;
          if ( v25 >= 0 )
          {
            v7 = 0;
            if ( v23 )
            {
              ++g_nRtlCloseIsolatedFilesystemHandle;
              dwExceptionCode = -1073741595;
              v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v33 + 4))(*v33, v23);
                v34 = 0;
              }
              else
              {
                v52 = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
                v34 = dwExceptionCode;
              }
              if ( v34 < 0 )
                RaiseException(v34, 1u, 0, 0);
            }
            Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST((Windows::Rtl::CRTL_ALLOCATION_LIST *)lpMem);
            RtlFreeHeap(v36, v35, a2);
LABEL_67:
            v46 = hMutex;
            if ( hMutex )
            {
              if ( (_BYTE)v55 )
              {
                ReleaseMutex(hMutex);
                LOBYTE(v55) = 0;
              }
              CloseHandle_0(v46);
LABEL_71:
              hMutex = 0;
              goto LABEL_72;
            }
            goto LABEL_72;
          }
          if ( v25 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x4F8,
            v26,
            v49);
          v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v26, v27);
          if ( v23 )
          {
            ++g_nRtlCloseIsolatedFilesystemHandle;
            dwExceptionCode = -1073741595;
            v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v28 + 4))(*v28, v23);
              v29 = 0;
            }
            else
            {
              v52 = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
              v29 = dwExceptionCode;
            }
            if ( v29 < 0 )
              RaiseException(v29, 1u, 0, 0);
          }
          while ( 1 )
          {
            v32 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v32 == lpMem )
              break;
            v30 = (void (__fastcall *)(LPVOID *))v32[2];
            if ( v30 )
              v30(v32 + 3);
            v31 = GetProcessHeap_0();
            HeapFree_0(v31, 0, v32);
          }
        }
        else
        {
          if ( v12 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x4E3,
            v13,
            v48);
          v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v13, v14);
          if ( v62 )
          {
            ++g_nRtlCloseIsolatedFilesystemHandle;
            dwExceptionCode = -1073741595;
            v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v62) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
              v17 = 0;
            }
            else
            {
              v52 = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
              v17 = dwExceptionCode;
            }
            if ( v17 < 0 )
              RaiseException(v17, 1u, 0, 0);
          }
          while ( 1 )
          {
            v20 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v20 == lpMem )
              break;
            v18 = (void (__fastcall *)(LPVOID *))v20[2];
            if ( v18 )
              v18(v20 + 3);
            v19 = GetProcessHeap_0();
            HeapFree_0(v19, 0, v20);
          }
        }
      }
    }
    v45 = GetProcessHeap_0();
    HeapFree_0(v45, 0, a2);
    goto LABEL_67;
  }
  v52 = 1231;
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v51);
  v8 = hMutex;
  if ( hMutex )
  {
    if ( (_BYTE)v55 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v55) = 0;
    }
    CloseHandle_0(v8);
    v7 = dwExceptionCode;
    goto LABEL_71;
  }
  v7 = dwExceptionCode;
LABEL_72:
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v56);
  return v7;
}

```

## disassembly

```asm
0x1800af0d8  mov     [rsp-8+arg_0], rbx
0x1800af0dd  mov     [rsp-8+arg_8], rsi
0x1800af0e2  push    rbp
0x1800af0e3  push    rdi
0x1800af0e4  push    r12
0x1800af0e6  push    r14
0x1800af0e8  push    r15
0x1800af0ea  lea     rbp, [rsp-37h]
0x1800af0ef  sub     rsp, 0E0h
0x1800af0f6  mov     rdi, rcx
0x1800af0f9  mov     [rbp+57h+dwExceptionCode], 8007054Fh
0x1800af100  lea     r15, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af107  mov     rsi, rdx
0x1800af10a  lea     rcx, [rbp+57h+var_90]; this
0x1800af10e  mov     [rbp+57h+var_C0], r15
0x1800af112  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800af117  xor     r14d, r14d
0x1800af11a  lea     rcx, [rbp+57h+hMutex]; this
0x1800af11e  mov     [rbp+57h+hMutex], r14
0x1800af122  mov     [rbp+57h+var_98], r14w
0x1800af127  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800af12c  mov     ebx, eax
0x1800af12e  test    eax, eax
0x1800af130  jns     short loc_1800AF166
0x1800af132  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800af138  jnz     short loc_1800AF140
0x1800af13a  call    cs:__imp_DebugBreak
0x1800af140  mov     r9d, ebx; int
0x1800af143  lea     rcx, aStatusPropagat; "Status propagated"
0x1800af14a  mov     r8d, 4CDh; char *
0x1800af150  mov     rdx, r15; char *
0x1800af153  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800af158  mov     ecx, ebx; this
0x1800af15a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800af15f  mov     edi, eax
0x1800af161  jmp     loc_1800AF5EC
0x1800af166  test    rsi, rsi
0x1800af169  jnz     short loc_1800AF1AF
0x1800af16b  lea     rcx, [rbp+57h+var_C0]
0x1800af16f  mov     [rbp+57h+var_B8], 4CFh
0x1800af176  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800af17b  mov     rbx, [rbp+57h+hMutex]
0x1800af17f  test    rbx, rbx
0x1800af182  jz      short loc_1800AF1A7
0x1800af184  cmp     byte ptr [rbp+57h+var_98], r14b
0x1800af188  jz      short loc_1800AF197
0x1800af18a  mov     rcx, rbx; hMutex
0x1800af18d  call    cs:__imp_ReleaseMutex
0x1800af193  mov     byte ptr [rbp+57h+var_98], r14b
0x1800af197  mov     rcx, rbx; hObject
0x1800af19a  call    CloseHandle_0
0x1800af19f  mov     edi, [rbp+57h+dwExceptionCode]
0x1800af1a2  jmp     loc_1800AF610
0x1800af1a7  mov     edi, [rbp+57h+dwExceptionCode]
0x1800af1aa  jmp     loc_1800AF614
0x1800af1af  lea     rax, [rbp+57h+lpMem]
0x1800af1b3  mov     [rbp+57h+arg_10], r14
0x1800af1b7  mov     [rbp+57h+var_C8], rax
0x1800af1bb  lea     r9, [rbp+57h+arg_18]
0x1800af1bf  lea     rax, [rbp+57h+lpMem]
0x1800af1c3  mov     [rbp+57h+arg_18], r14
0x1800af1c7  mov     r12d, 20h ; ' '
0x1800af1cd  mov     [rbp+57h+lpMem], rax
0x1800af1d1  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800af1d8  mov     edx, r12d
0x1800af1db  lea     rcx, [rbp+57h+lpMem]
0x1800af1df  call    RtlAllocateAllocationListMemory
0x1800af1e4  mov     ebx, eax
0x1800af1e6  test    eax, eax
0x1800af1e8  js      loc_1800AF569
0x1800af1ee  lea     r9, [rbp+57h+var_50]
0x1800af1f2  mov     qword ptr [rbp+57h+var_50], r14
0x1800af1f6  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800af1fd  mov     edx, r12d
0x1800af200  lea     rcx, [rbp+57h+lpMem]
0x1800af204  call    RtlAllocateAllocationListMemory
0x1800af209  mov     ebx, eax
0x1800af20b  test    eax, eax
0x1800af20d  js      loc_1800AF4F6
0x1800af213  lea     rdx, [rbp+57h+arg_10]
0x1800af217  call    RtlCreateDirectIsolatedFilesystem
0x1800af21c  mov     ebx, eax
0x1800af21e  test    eax, eax
0x1800af220  jns     loc_1800AF31D
0x1800af226  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800af22c  jnz     short loc_1800AF234
0x1800af22e  call    cs:__imp_DebugBreak
0x1800af234  mov     r9d, ebx; int
0x1800af237  lea     rcx, aStatusPropagat; "Status propagated"
0x1800af23e  mov     r8d, 4E3h; char *
0x1800af244  mov     rdx, r15; char *
0x1800af247  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800af24c  mov     ecx, ebx; this
0x1800af24e  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800af253  mov     r10, [rbp+57h+arg_10]
0x1800af257  mov     edi, eax
0x1800af259  test    r10, r10
0x1800af25c  jz      loc_1800AF2FC
0x1800af262  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800af269  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af270  mov     [rbp+57h+dwExceptionCode], 0C00000E5h
0x1800af277  mov     [rbp+57h+var_C0], rax
0x1800af27b  test    r10, r10
0x1800af27e  jz      short loc_1800AF2AA
0x1800af280  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800af287  test    r11, r11
0x1800af28a  jz      short loc_1800AF2C3
0x1800af28c  mov     rdx, r11
0x1800af28f  mov     rcx, r10
0x1800af292  call    RtlIsTypeSafeHandleValid
0x1800af297  test    al, al
0x1800af299  jz      short loc_1800AF2C3
0x1800af29b  mov     ecx, [r11]
0x1800af29e  mov     rdx, r10
0x1800af2a1  mov     rax, [r11+20h]
0x1800af2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af2aa  mov     ecx, r14d; dwExceptionCode
0x1800af2ad  test    ecx, ecx
0x1800af2af  jns     short loc_1800AF2FC
0x1800af2b1  xor     r9d, r9d; lpArguments
0x1800af2b4  xor     r8d, r8d; nNumberOfArguments
0x1800af2b7  lea     edx, [r9+1]; dwExceptionFlags
0x1800af2bb  call    cs:__imp_RaiseException
0x1800af2c1  jmp     short loc_1800AF2FC
0x1800af2c3  mov     [rbp+57h+var_B8], 124h
0x1800af2ca  lea     rcx, [rbp+57h+var_C0]
0x1800af2ce  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800af2d3  mov     ecx, [rbp+57h+dwExceptionCode]
0x1800af2d6  jmp     short loc_1800AF2AD
0x1800af2d8  mov     rax, [rbx+10h]
0x1800af2dc  test    rax, rax
0x1800af2df  jz      short loc_1800AF2EA
0x1800af2e1  lea     rcx, [rbx+18h]
0x1800af2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af2ea  call    GetProcessHeap_0
0x1800af2ef  mov     r8, rbx; lpMem
0x1800af2f2  xor     edx, edx; dwFlags
0x1800af2f4  mov     rcx, rax; hHeap
0x1800af2f7  call    HeapFree_0
0x1800af2fc  mov     rbx, [rbp+57h+lpMem]
0x1800af300  lea     rcx, [rbp+57h+lpMem]
0x1800af304  mov     rax, [rbx]
0x1800af307  mov     [rbp+57h+lpMem], rax
0x1800af30b  mov     [rax+8], rcx
0x1800af30f  lea     rax, [rbp+57h+lpMem]
0x1800af313  cmp     rbx, rax
0x1800af316  jnz     short loc_1800AF2D8
0x1800af318  jmp     loc_1800AF5DA
0x1800af31d  mov     rdx, [rbp+57h+arg_18]
0x1800af321  lea     rax, [rsi+20h]
0x1800af325  mov     rcx, qword ptr [rbp+57h+var_50]; int
0x1800af329  mov     r9d, 2; int
0x1800af32f  mov     rbx, [rbp+57h+arg_10]
0x1800af333  mov     [rsp+100h+var_D8], r14; void *
0x1800af338  mov     [rdx], r12
0x1800af33b  mov     [rdx+8], rsi
0x1800af33f  mov     [rcx+8], rax
0x1800af343  lea     rax, [rbp+57h+var_48]
0x1800af347  mov     [rcx], r12
0x1800af34a  mov     r8, [rdi+10h]; int
0x1800af34e  mov     [rbp+57h+var_30], rdx
0x1800af352  mov     rdx, rbx; int
0x1800af355  mov     qword ptr [rsp+100h+var_E0], rax; unsigned int
0x1800af35a  mov     [rbp+57h+var_40], rcx
0x1800af35e  mov     [rbp+57h+var_48], 10h
0x1800af365  mov     [rbp+57h+var_38], 0Eh
0x1800af36c  call    RtlTransactComponentStore
0x1800af371  mov     edi, eax
0x1800af373  test    eax, eax
0x1800af375  jns     loc_1800AF469
0x1800af37b  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800af381  jnz     short loc_1800AF389
0x1800af383  call    cs:__imp_DebugBreak
0x1800af389  mov     r9d, edi; int
0x1800af38c  lea     rcx, aStatusPropagat; "Status propagated"
0x1800af393  mov     r8d, 4F8h; char *
0x1800af399  mov     rdx, r15; char *
0x1800af39c  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800af3a1  mov     ecx, edi; this
0x1800af3a3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800af3a8  mov     edi, eax
0x1800af3aa  test    rbx, rbx
0x1800af3ad  jz      loc_1800AF448
0x1800af3b3  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800af3ba  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af3c1  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800af3c8  mov     [rbp+57h+dwExceptionCode], 0C00000E5h
0x1800af3cf  mov     [rbp+57h+var_C0], rax
0x1800af3d3  test    r10, r10
0x1800af3d6  jz      short loc_1800AF3FB
0x1800af3d8  mov     rdx, r10
0x1800af3db  mov     rcx, rbx
0x1800af3de  call    RtlIsTypeSafeHandleValid
0x1800af3e3  test    al, al
0x1800af3e5  jz      short loc_1800AF3FB
0x1800af3e7  mov     ecx, [r10]
0x1800af3ea  mov     rdx, rbx
0x1800af3ed  mov     rax, [r10+20h]
0x1800af3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af3f6  mov     ecx, r14d
0x1800af3f9  jmp     short loc_1800AF40E
0x1800af3fb  mov     [rbp+57h+var_B8], 124h
0x1800af402  lea     rcx, [rbp+57h+var_C0]
0x1800af406  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800af40b  mov     ecx, [rbp+57h+dwExceptionCode]; dwExceptionCode
0x1800af40e  test    ecx, ecx
0x1800af410  jns     short loc_1800AF448
0x1800af412  xor     r9d, r9d; lpArguments
0x1800af415  xor     r8d, r8d; nNumberOfArguments
0x1800af418  lea     edx, [r9+1]; dwExceptionFlags
0x1800af41c  call    cs:__imp_RaiseException
0x1800af422  jmp     short loc_1800AF448
0x1800af424  mov     rax, [rbx+10h]
0x1800af428  test    rax, rax
0x1800af42b  jz      short loc_1800AF436
0x1800af42d  lea     rcx, [rbx+18h]
0x1800af431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af436  call    GetProcessHeap_0
0x1800af43b  mov     r8, rbx; lpMem
0x1800af43e  xor     edx, edx; dwFlags
0x1800af440  mov     rcx, rax; hHeap
0x1800af443  call    HeapFree_0
0x1800af448  mov     rbx, [rbp+57h+lpMem]
0x1800af44c  lea     rcx, [rbp+57h+lpMem]
0x1800af450  mov     rax, [rbx]
0x1800af453  mov     [rbp+57h+lpMem], rax
0x1800af457  mov     [rax+8], rcx
0x1800af45b  lea     rax, [rbp+57h+lpMem]
0x1800af45f  cmp     rbx, rax
0x1800af462  jnz     short loc_1800AF424
0x1800af464  jmp     loc_1800AF5DA
0x1800af469  mov     edi, r14d
0x1800af46c  test    rbx, rbx
0x1800af46f  jz      short loc_1800AF4E0
0x1800af471  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800af478  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800af47f  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800af486  mov     [rbp+57h+dwExceptionCode], 0C00000E5h
0x1800af48d  mov     [rbp+57h+var_C0], rax
0x1800af491  test    r10, r10
0x1800af494  jz      short loc_1800AF4B9
0x1800af496  mov     rdx, r10
0x1800af499  mov     rcx, rbx
0x1800af49c  call    RtlIsTypeSafeHandleValid
0x1800af4a1  test    al, al
0x1800af4a3  jz      short loc_1800AF4B9
0x1800af4a5  mov     ecx, [r10]
0x1800af4a8  mov     rdx, rbx
0x1800af4ab  mov     rax, [r10+20h]
0x1800af4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af4b4  mov     ecx, r14d
0x1800af4b7  jmp     short loc_1800AF4CC
0x1800af4b9  mov     [rbp+57h+var_B8], 124h
0x1800af4c0  lea     rcx, [rbp+57h+var_C0]
0x1800af4c4  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800af4c9  mov     ecx, [rbp+57h+dwExceptionCode]; dwExceptionCode
0x1800af4cc  test    ecx, ecx
0x1800af4ce  jns     short loc_1800AF4E0
0x1800af4d0  xor     r9d, r9d; lpArguments
0x1800af4d3  xor     r8d, r8d; nNumberOfArguments
0x1800af4d6  lea     edx, [r9+1]; dwExceptionFlags
0x1800af4da  call    cs:__imp_RaiseException
0x1800af4e0  lea     rcx, [rbp+57h+lpMem]; this
0x1800af4e4  call    ??1CRTL_ALLOCATION_LIST@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CRTL_ALLOCATION_LIST::~CRTL_ALLOCATION_LIST(void)
0x1800af4e9  mov     r8, rsi
0x1800af4ec  call    RtlFreeHeap
0x1800af4f1  jmp     loc_1800AF5EC
0x1800af4f6  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800af4fc  jnz     short loc_1800AF504
0x1800af4fe  call    cs:__imp_DebugBreak
0x1800af504  mov     r9d, ebx; int
0x1800af507  lea     rcx, aStatusPropagat; "Status propagated"
0x1800af50e  mov     r8d, 4DEh; char *
0x1800af514  mov     rdx, r15; char *
0x1800af517  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800af51c  mov     ecx, ebx; this
0x1800af51e  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800af523  mov     edi, eax
0x1800af525  jmp     short loc_1800AF54B
0x1800af527  mov     rax, [rbx+10h]
0x1800af52b  test    rax, rax
0x1800af52e  jz      short loc_1800AF539
0x1800af530  lea     rcx, [rbx+18h]
0x1800af534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af539  call    GetProcessHeap_0
0x1800af53e  mov     r8, rbx; lpMem
0x1800af541  xor     edx, edx; dwFlags
0x1800af543  mov     rcx, rax; hHeap
0x1800af546  call    HeapFree_0
0x1800af54b  mov     rbx, [rbp+57h+lpMem]
0x1800af54f  lea     rcx, [rbp+57h+lpMem]
0x1800af553  mov     rax, [rbx]
0x1800af556  mov     [rbp+57h+lpMem], rax
0x1800af55a  mov     [rax+8], rcx
0x1800af55e  lea     rax, [rbp+57h+lpMem]
0x1800af562  cmp     rbx, rax
0x1800af565  jnz     short loc_1800AF527
0x1800af567  jmp     short loc_1800AF5DA
0x1800af569  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800af56f  jnz     short loc_1800AF577
  ... truncated ...
```
