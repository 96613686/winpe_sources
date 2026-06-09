# InitializeIISUtilProcessAttach

- ea: `0x18000d770`
- end: `0x18000dc0d`
- name: `InitializeIISUtilProcessAttach`
- size: `1181`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f740`

## callees

- `0x180008000`
- `0x18000d770`
- `0x1800148c0`
- `0x180014ca0`
- `0x180015654`
- `0x180016554`
- `0x180019230`
- `0x180020510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da9e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d879`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d8a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d8cd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d941`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d9e7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d879`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d8a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d8cd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d941`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d9e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dbf6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dbf6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000db32`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000db32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db96`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d803`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000da60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d803`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000da60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d90d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d90d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000d7a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000d7a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dae9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dae9`

## string_xrefs

- `0x18000d794`: `System\CurrentControlSet\Services\W3SVC\Parameters\IisUtil`
- `0x18000d7fc`: `kernel32.dll`
- `0x18000da59`: `verifier.dll`
- `0x18000db52`: `SwitchToThread`
- `0x18000db1f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

## pseudocode

```c
__int64 InitializeIISUtilProcessAttach()
{
  int DebugFlagsFromReg; // ebx
  HMODULE ModuleHandleW; // rax
  HMODULE v2; // rbx
  unsigned int (*ProcAddress)(struct _RTL_CRITICAL_SECTION *, unsigned int); // rax
  int v4; // eax
  ALLOC_CACHE_HANDLER *v5; // rax
  struct _PEB *v7; // rax
  signed int LastError; // eax
  bool v9; // sf
  char v10; // [rsp+28h] [rbp-20h]
  _DWORD v11[6]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  DebugFlagsFromReg = 8;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\IisUtil",
          0,
          0x20019u,
          &hKey) )
  {
    DebugFlagsFromReg = PuLoadDebugFlagsFromReg(hKey, 8);
    RegCloseKey(hKey);
    hKey = 0;
  }
  g_dwDebugFlagsIISUtil = DebugFlagsFromReg;
  if ( (DebugFlagsFromReg & 3) != 0 && (DebugFlagsFromReg & 4) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
      0x92u,
      "InitializeIISUtilProcessAttach",
      "InitializeIISUtilProcessAttach\n",
      v10);
  if ( !g_fLocksInitialized )
  {
    while ( _InterlockedExchange((volatile __int32 *)&g_lckInit, 1) )
      Sleep(0);
    if ( !g_fLocksInitialized )
    {
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      v2 = ModuleHandleW;
      if ( ModuleHandleW )
      {
        g_pfnSwitchToThread = (int (*)(void))GetProcAddress(ModuleHandleW, "SwitchToThread");
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))GetProcAddress(v2, "TryEnterCriticalSection");
        ProcAddress = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))GetProcAddress(
                                                                                        v2,
                                                                                        "SetCriticalSectionSpinCount");
        g_pfnSetCSSpinCount = ProcAddress;
      }
      else
      {
        ProcAddress = g_pfnSetCSSpinCount;
      }
      if ( !g_pfnSwitchToThread )
        g_pfnSwitchToThread = (int (*)(void))MULTI_IPM::Initialize;
      if ( !g_pfnTryEnterCritSec )
        g_pfnTryEnterCritSec = (int (*)(struct _RTL_CRITICAL_SECTION *))MULTI_IPM::Initialize;
      if ( !ProcAddress )
        g_pfnSetCSSpinCount = (unsigned int (*)(struct _RTL_CRITICAL_SECTION *, unsigned int))MULTI_IPM::Initialize;
      g_cProcessors = NumProcessors();
      _InterlockedExchange(&g_fLocksInitialized, 1);
    }
    _InterlockedExchange((volatile __int32 *)&g_lckInit, 0);
  }
  dword_18004F98C = 2;
  if ( !InitializeCriticalSectionAndSpinCount(&CriticalSection, 0x80000000) )
    goto LABEL_32;
  dword_18004F98C = 3;
  if ( !InitializeCriticalSectionAndSpinCount(&g_SchedulerCritSec, 0x80000000) )
    goto LABEL_32;
  dword_18004F98C = 4;
  if ( !InitializeCriticalSectionAndSpinCount(&g_csTimerWrap, 0x800003E8) )
    goto LABEL_32;
  g_fInitCsTimerWrap = 1;
  dword_18004F98C = 5;
  if ( dword_18005066C )
  {
    v4 = dword_180050668;
  }
  else
  {
    if ( GetModuleHandleW(L"verifier.dll") )
    {
      v4 = 1;
    }
    else
    {
      v7 = NtCurrentPeb();
      if ( v7 )
        v4 = (v7->NtGlobalFlag >> 25) & 1;
      else
        v4 = 0;
    }
    dword_180050668 = v4;
    dword_18005066C = 1;
  }
  ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled = v4;
  ALLOC_CACHE_HANDLER::sm_hHeap = GetProcessHeap();
  qword_18004F9C8 = (__int64)&ALLOC_CACHE_HANDLER::sm_lItemsHead;
  ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink = &ALLOC_CACHE_HANDLER::sm_lItemsHead;
  if ( !InitializeCriticalSectionAndSpinCount(&ALLOC_CACHE_HANDLER::sm_csItems, 0x800003E8) )
  {
    if ( ALLOC_CACHE_HANDLER::sm_fInitCsItems )
    {
      DeleteCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
      ALLOC_CACHE_HANDLER::sm_fInitCsItems = 0;
    }
    goto LABEL_32;
  }
  ALLOC_CACHE_HANDLER::sm_fInitCsItems = 1;
  dword_18004F98C = 6;
  if ( !(unsigned __int8)LKRHashTableInit() )
  {
LABEL_32:
    TerminateIISUtilProcessDetach();
    return 0;
  }
  dword_18004F98C = 7;
  v11[0] = 1;
  v11[1] = 1000;
  v11[2] = 416;
  v5 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v5 )
  {
    BIG_REF_TRACE::sm_pachBigRefTrace = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                          v5,
                                          "BIG_REF_TRACE_ENTRY",
                                          (const struct ALLOC_CACHE_CONFIGURATION *)v11,
                                          1);
    if ( BIG_REF_TRACE::sm_pachBigRefTrace )
    {
      dword_18004F98C = 8;
      if ( InitializeCriticalSectionAndSpinCount(&EVENT_LOG::sm_csLock, 0x3E8u) )
      {
        EVENT_LOG::sm_fLockInitialized = 1;
LABEL_29:
        dword_18004F98C = 9;
        return 1;
      }
      LastError = GetLastError();
      v9 = LastError < 0;
      if ( LastError > 0 )
        v9 = 1;
      if ( !v9 )
        goto LABEL_29;
    }
    goto LABEL_32;
  }
  BIG_REF_TRACE::sm_pachBigRefTrace = 0;
  TerminateIISUtilProcessDetach();
  return 0;
}

```

## disassembly

```asm
0x18000d770  mov     [rsp+arg_8], rbx
0x18000d775  push    rdi
0x18000d776  sub     rsp, 40h
0x18000d77a  lea     rax, [rsp+48h+hKey]
0x18000d77f  xor     edi, edi
0x18000d781  mov     r9d, 20019h; samDesired
0x18000d787  mov     [rsp+48h+hKey], rdi
0x18000d78c  xor     r8d, r8d; ulOptions
0x18000d78f  mov     [rsp+48h+phkResult], rax; phkResult
0x18000d794  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\W3"...
0x18000d79b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d7a2  mov     ebx, 8
0x18000d7a7  call    cs:__imp_RegOpenKeyExA
0x18000d7ae  nop     dword ptr [rax+rax+00h]
0x18000d7b3  test    eax, eax
0x18000d7b5  jz      loc_18000DAD6
0x18000d7bb  test    bl, 3
0x18000d7be  mov     cs:g_dwDebugFlagsIISUtil, ebx
0x18000d7c4  setnz   cl
0x18000d7c7  test    bl, 4
0x18000d7ca  setnz   al
0x18000d7cd  test    al, cl
0x18000d7cf  jnz     loc_18000DAFF
0x18000d7d5  cmp     cs:?g_fLocksInitialized@@3HA, edi; int g_fLocksInitialized
0x18000d7db  jnz     loc_18000D863
0x18000d7e1  mov     eax, 1
0x18000d7e6  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18000d7ec  test    eax, eax
0x18000d7ee  jnz     loc_18000DB30
0x18000d7f4  cmp     cs:?g_fLocksInitialized@@3HA, edi; int g_fLocksInitialized
0x18000d7fa  jnz     short loc_18000D85B
0x18000d7fc  lea     rcx, ModuleName; "kernel32.dll"
0x18000d803  call    cs:__imp_GetModuleHandleW
0x18000d80a  nop     dword ptr [rax+rax+00h]
0x18000d80f  mov     rbx, rax
0x18000d812  test    rax, rax
0x18000d815  jnz     loc_18000DB52
0x18000d81b  mov     rax, cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18000d822  cmp     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rdi; int (*g_pfnSwitchToThread)(void)
0x18000d829  jz      loc_18000DBAE
0x18000d82f  cmp     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rdi; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18000d836  jz      loc_18000DBC1
0x18000d83c  test    rax, rax
0x18000d83f  jz      loc_18000DAC3
0x18000d845  call    NumProcessors
0x18000d84a  mov     cs:?g_cProcessors@@3KA, eax; ulong g_cProcessors
0x18000d850  mov     eax, 1
0x18000d855  xchg    eax, cs:?g_fLocksInitialized@@3HA; int g_fLocksInitialized
0x18000d85b  mov     eax, edi
0x18000d85d  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18000d863  mov     edx, 80000000h; dwSpinCount
0x18000d868  mov     cs:dword_18004F98C, 2
0x18000d872  lea     rcx, CriticalSection; lpCriticalSection
0x18000d879  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d880  nop     dword ptr [rax+rax+00h]
0x18000d885  test    eax, eax
0x18000d887  jz      loc_18000DA2C
0x18000d88d  mov     edx, 80000000h; dwSpinCount
0x18000d892  mov     cs:dword_18004F98C, 3
0x18000d89c  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d8a3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d8aa  nop     dword ptr [rax+rax+00h]
0x18000d8af  test    eax, eax
0x18000d8b1  jz      loc_18000DA2C
0x18000d8b7  mov     edx, 800003E8h; dwSpinCount
0x18000d8bc  mov     cs:dword_18004F98C, 4
0x18000d8c6  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d8cd  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d8d4  nop     dword ptr [rax+rax+00h]
0x18000d8d9  test    eax, eax
0x18000d8db  jz      loc_18000DA2C
0x18000d8e1  cmp     cs:dword_18005066C, edi
0x18000d8e7  mov     cs:?g_fInitCsTimerWrap@@3HA, 1; int g_fInitCsTimerWrap
0x18000d8f1  mov     cs:dword_18004F98C, 5
0x18000d8fb  jz      loc_18000DA59
0x18000d901  mov     eax, cs:dword_180050668
0x18000d907  mov     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x18000d90d  call    cs:__imp_GetProcessHeap
0x18000d914  nop     dword ptr [rax+rax+00h]
0x18000d919  mov     cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA, rax; void * ALLOC_CACHE_HANDLER::sm_hHeap
0x18000d920  mov     edx, 800003E8h; dwSpinCount
0x18000d925  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d92c  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18000d933  mov     cs:qword_18004F9C8, rax
0x18000d93a  mov     cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18000d941  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d948  nop     dword ptr [rax+rax+00h]
0x18000d94d  test    eax, eax
0x18000d94f  jz      loc_18000DA20
0x18000d955  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 1; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18000d95f  mov     cs:dword_18004F98C, 6
0x18000d969  call    LKRHashTableInit
0x18000d96e  test    al, al
0x18000d970  jz      loc_18000DA2C
0x18000d976  mov     ecx, 100h; Size
0x18000d97b  mov     cs:dword_18004F98C, 7
0x18000d985  mov     [rsp+48h+var_18], 1
0x18000d98d  mov     [rsp+48h+var_14], 3E8h
0x18000d995  mov     [rsp+48h+var_10], 1A0h
0x18000d99d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d9a2  test    rax, rax
0x18000d9a5  jz      loc_18000DA3F
0x18000d9ab  mov     r9d, 1; int
0x18000d9b1  lea     r8, [rsp+48h+var_18]; struct ALLOC_CACHE_CONFIGURATION *
0x18000d9b6  lea     rdx, aBigRefTraceEnt; "BIG_REF_TRACE_ENTRY"
0x18000d9bd  mov     rcx, rax; this
0x18000d9c0  call    ??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000d9c5  mov     cs:?sm_pachBigRefTrace@BIG_REF_TRACE@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * BIG_REF_TRACE::sm_pachBigRefTrace
0x18000d9cc  test    rax, rax
0x18000d9cf  jz      short loc_18000DA2C
0x18000d9d1  mov     edx, 3E8h; dwSpinCount
0x18000d9d6  mov     cs:dword_18004F98C, 8
0x18000d9e0  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d9e7  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d9ee  nop     dword ptr [rax+rax+00h]
0x18000d9f3  test    eax, eax
0x18000d9f5  jz      loc_18000DA9E
0x18000d9fb  mov     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 1; int EVENT_LOG::sm_fLockInitialized
0x18000da05  mov     cs:dword_18004F98C, 9
0x18000da0f  mov     eax, 1
0x18000da14  mov     rbx, [rsp+48h+arg_8]
0x18000da19  add     rsp, 40h
0x18000da1d  pop     rdi
0x18000da1e  retn
0x18000da20  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, edi; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18000da26  jnz     loc_18000DBEF
0x18000da2c  call    TerminateIISUtilProcessDetach
0x18000da31  xor     eax, eax
0x18000da33  mov     rbx, [rsp+48h+arg_8]
0x18000da38  add     rsp, 40h
0x18000da3c  pop     rdi
0x18000da3d  retn
0x18000da3f  mov     cs:?sm_pachBigRefTrace@BIG_REF_TRACE@@0PEAVALLOC_CACHE_HANDLER@@EA, rdi; ALLOC_CACHE_HANDLER * BIG_REF_TRACE::sm_pachBigRefTrace
0x18000da46  call    TerminateIISUtilProcessDetach
0x18000da4b  mov     rbx, [rsp+48h+arg_8]
0x18000da50  xor     eax, eax
0x18000da52  add     rsp, 40h
0x18000da56  pop     rdi
0x18000da57  retn
0x18000da59  lea     rcx, aVerifierDll; "verifier.dll"
0x18000da60  call    cs:__imp_GetModuleHandleW
0x18000da67  nop     dword ptr [rax+rax+00h]
0x18000da6c  test    rax, rax
0x18000da6f  jnz     loc_18000DBD4
0x18000da75  mov     rax, gs:60h
0x18000da7e  test    rax, rax
0x18000da81  jnz     loc_18000DBDE
0x18000da87  mov     eax, edi
0x18000da89  mov     cs:dword_180050668, eax
0x18000da8f  mov     cs:dword_18005066C, 1
0x18000da99  jmp     loc_18000D907
0x18000da9e  call    cs:__imp_GetLastError
0x18000daa5  nop     dword ptr [rax+rax+00h]
0x18000daaa  test    eax, eax
0x18000daac  jle     short loc_18000DAB8
0x18000daae  movzx   eax, ax
0x18000dab1  or      eax, 80070000h
0x18000dab6  test    eax, eax
0x18000dab8  jns     loc_18000DA05
0x18000dabe  jmp     loc_18000DA2C
0x18000dac3  lea     rax, ?Initialize@MULTI_IPM@@QEAAJXZ; MULTI_IPM::Initialize(void)
0x18000daca  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18000dad1  jmp     loc_18000D845
0x18000dad6  mov     rcx, [rsp+48h+hKey]
0x18000dadb  mov     edx, ebx
0x18000dadd  call    PuLoadDebugFlagsFromReg
0x18000dae2  mov     rcx, [rsp+48h+hKey]; hKey
0x18000dae7  mov     ebx, eax
0x18000dae9  call    cs:__imp_RegCloseKey
0x18000daf0  nop     dword ptr [rax+rax+00h]
0x18000daf5  mov     [rsp+48h+hKey], rdi
0x18000dafa  jmp     loc_18000D7BB
0x18000daff  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000db06  lea     rax, aInitializeiisu_1; "InitializeIISUtilProcessAttach\n"
0x18000db0d  lea     r9, aInitializeiisu_0; "InitializeIISUtilProcessAttach"
0x18000db14  mov     [rsp+48h+phkResult], rax; char *
0x18000db19  mov     r8d, 92h; unsigned int
0x18000db1f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000db26  call    PuDbgPrint
0x18000db2b  jmp     loc_18000D7D5
0x18000db30  xor     ecx, ecx; dwMilliseconds
0x18000db32  call    cs:__imp_Sleep
0x18000db39  nop     dword ptr [rax+rax+00h]
0x18000db3e  mov     eax, 1
0x18000db43  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18000db49  test    eax, eax
0x18000db4b  jnz     short loc_18000DB30
0x18000db4d  jmp     loc_18000D7F4
0x18000db52  lea     rdx, ProcName; "SwitchToThread"
0x18000db59  mov     rcx, rbx; hModule
0x18000db5c  call    cs:__imp_GetProcAddress
0x18000db63  nop     dword ptr [rax+rax+00h]
0x18000db68  lea     rdx, aTryentercritic; "TryEnterCriticalSection"
0x18000db6f  mov     rcx, rbx; hModule
0x18000db72  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rax; int (*g_pfnSwitchToThread)(void)
0x18000db79  call    cs:__imp_GetProcAddress
0x18000db80  nop     dword ptr [rax+rax+00h]
0x18000db85  lea     rdx, aSetcriticalsec; "SetCriticalSectionSpinCount"
0x18000db8c  mov     rcx, rbx; hModule
0x18000db8f  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rax; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18000db96  call    cs:__imp_GetProcAddress
0x18000db9d  nop     dword ptr [rax+rax+00h]
0x18000dba2  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18000dba9  jmp     loc_18000D822
0x18000dbae  lea     rcx, ?Initialize@MULTI_IPM@@QEAAJXZ; MULTI_IPM::Initialize(void)
0x18000dbb5  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rcx; int (*g_pfnSwitchToThread)(void)
0x18000dbbc  jmp     loc_18000D82F
0x18000dbc1  lea     rcx, ?Initialize@MULTI_IPM@@QEAAJXZ; MULTI_IPM::Initialize(void)
0x18000dbc8  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rcx; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18000dbcf  jmp     loc_18000D83C
0x18000dbd4  mov     eax, 1
0x18000dbd9  jmp     loc_18000DA89
0x18000dbde  mov     eax, [rax+0BCh]
0x18000dbe4  shr     eax, 19h
0x18000dbe7  and     eax, 1
0x18000dbea  jmp     loc_18000DA89
0x18000dbef  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dbf6  call    cs:__imp_DeleteCriticalSection
0x18000dbfd  nop     dword ptr [rax+rax+00h]
0x18000dc02  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, edi; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18000dc08  jmp     loc_18000DA2C
```
