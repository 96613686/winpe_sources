# InitializeIISUtilProcessAttach

- ea: `0x18000c770`
- end: `0x18000cbda`
- name: `InitializeIISUtilProcessAttach`
- size: `1130`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e5a0`

## callees

- `0x180007300`
- `0x18000c770`
- `0x180013e70`
- `0x180014240`
- `0x180014b10`
- `0x1800183f8`
- `0x18001f280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca63`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c875`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c899`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c8bd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c925`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c9c5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c875`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c899`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c8bd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c925`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000c9c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cbc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cbc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000cb92`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000cb92`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000caf1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000caf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb43`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ca2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c7fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ca2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000c7a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000c7a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caab`

## string_xrefs

- `0x18000c793`: `System\CurrentControlSet\Services\W3SVC\Parameters\IisUtil`
- `0x18000c7f5`: `kernel32.dll`
- `0x18000ca24`: `verifier.dll`
- `0x18000cb0b`: `SwitchToThread`
- `0x18000cade`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

## pseudocode

```c
__int64 InitializeIISUtilProcessAttach()
{
  int DebugFlagsFromReg; // ebx
  HMODULE ModuleHandleW; // rax
  HMODULE v2; // rbx
  unsigned int (*ProcAddress)(struct _RTL_CRITICAL_SECTION *, unsigned int); // rax
  DWORD dwNumberOfProcessors; // eax
  int v5; // eax
  ALLOC_CACHE_HANDLER *v6; // rax
  struct _PEB *v8; // rax
  signed int LastError; // eax
  bool v10; // sf
  char v11; // [rsp+28h] [rbp-50h]
  _DWORD v12[4]; // [rsp+30h] [rbp-48h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

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
      v11);
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
      dwNumberOfProcessors = `NumProcessors'::`2'::s_nCPUs;
      if ( !`NumProcessors'::`2'::s_nCPUs )
      {
        memset(&SystemInfo, 0, sizeof(SystemInfo));
        GetSystemInfo(&SystemInfo);
        dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
        `NumProcessors'::`2'::s_nCPUs = SystemInfo.dwNumberOfProcessors;
      }
      g_cProcessors = dwNumberOfProcessors;
      _InterlockedExchange(&g_fLocksInitialized, 1);
    }
    _InterlockedExchange((volatile __int32 *)&g_lckInit, 0);
  }
  dword_18004D98C = 2;
  if ( InitializeCriticalSectionAndSpinCount(&CriticalSection, 0x80000000) )
  {
    dword_18004D98C = 3;
    if ( InitializeCriticalSectionAndSpinCount(&g_SchedulerCritSec, 0x80000000) )
    {
      dword_18004D98C = 4;
      if ( InitializeCriticalSectionAndSpinCount(&g_csTimerWrap, 0x800003E8) )
      {
        g_fInitCsTimerWrap = 1;
        dword_18004D98C = 5;
        if ( dword_18004E67C )
        {
          v5 = dword_18004E678;
        }
        else
        {
          if ( GetModuleHandleW(L"verifier.dll") )
          {
            v5 = 1;
          }
          else
          {
            v8 = NtCurrentPeb();
            if ( v8 )
              v5 = (v8->NtGlobalFlag >> 25) & 1;
            else
              v5 = 0;
          }
          dword_18004E678 = v5;
          dword_18004E67C = 1;
        }
        ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled = v5;
        ALLOC_CACHE_HANDLER::sm_hHeap = GetProcessHeap();
        qword_18004D9C8 = (__int64)&ALLOC_CACHE_HANDLER::sm_lItemsHead;
        ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink = &ALLOC_CACHE_HANDLER::sm_lItemsHead;
        if ( InitializeCriticalSectionAndSpinCount(&ALLOC_CACHE_HANDLER::sm_csItems, 0x800003E8) )
        {
          ALLOC_CACHE_HANDLER::sm_fInitCsItems = 1;
          dword_18004D98C = 6;
          if ( (unsigned __int8)LKRHashTableInit() )
          {
            dword_18004D98C = 7;
            v12[0] = 1;
            v12[1] = 1000;
            v12[2] = 416;
            v6 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
            if ( v6 )
            {
              BIG_REF_TRACE::sm_pachBigRefTrace = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                                    v6,
                                                    "BIG_REF_TRACE_ENTRY",
                                                    (const struct ALLOC_CACHE_CONFIGURATION *)v12,
                                                    1);
              if ( BIG_REF_TRACE::sm_pachBigRefTrace )
              {
                dword_18004D98C = 8;
                if ( InitializeCriticalSectionAndSpinCount(&EVENT_LOG::sm_csLock, 0x3E8u) )
                {
                  EVENT_LOG::sm_fLockInitialized = 1;
LABEL_31:
                  dword_18004D98C = 9;
                  return 1;
                }
                LastError = GetLastError();
                v10 = LastError < 0;
                if ( LastError > 0 )
                  v10 = 1;
                if ( !v10 )
                  goto LABEL_31;
              }
            }
            else
            {
              BIG_REF_TRACE::sm_pachBigRefTrace = 0;
            }
          }
        }
        else if ( ALLOC_CACHE_HANDLER::sm_fInitCsItems )
        {
          DeleteCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
          ALLOC_CACHE_HANDLER::sm_fInitCsItems = 0;
        }
      }
    }
  }
  TerminateIISUtilProcessDetach();
  return 0;
}

```

## disassembly

```asm
0x18000c770  mov     r11, rsp
0x18000c773  mov     [r11+10h], rbx
0x18000c777  push    rdi
0x18000c778  sub     rsp, 70h
0x18000c77c  lea     rax, [r11+8]
0x18000c780  xor     edi, edi
0x18000c782  mov     r9d, 20019h; samDesired
0x18000c788  mov     [r11+8], rdi
0x18000c78c  xor     r8d, r8d; ulOptions
0x18000c78f  mov     [r11-58h], rax
0x18000c793  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\W3"...
0x18000c79a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c7a1  mov     ebx, 8
0x18000c7a6  call    cs:__imp_RegOpenKeyExA
0x18000c7ac  test    eax, eax
0x18000c7ae  jz      loc_18000CA92
0x18000c7b4  test    bl, 3
0x18000c7b7  mov     cs:g_dwDebugFlagsIISUtil, ebx
0x18000c7bd  setnz   cl
0x18000c7c0  test    bl, 4
0x18000c7c3  setnz   al
0x18000c7c6  test    al, cl
0x18000c7c8  jnz     loc_18000CABE
0x18000c7ce  cmp     cs:?g_fLocksInitialized@@3HA, edi; int g_fLocksInitialized
0x18000c7d4  jnz     loc_18000C85F
0x18000c7da  mov     eax, 1
0x18000c7df  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18000c7e5  test    eax, eax
0x18000c7e7  jnz     loc_18000CAEF
0x18000c7ed  cmp     cs:?g_fLocksInitialized@@3HA, edi; int g_fLocksInitialized
0x18000c7f3  jnz     short loc_18000C857
0x18000c7f5  lea     rcx, ModuleName; "kernel32.dll"
0x18000c7fc  call    cs:__imp_GetModuleHandleW
0x18000c802  mov     rbx, rax
0x18000c805  test    rax, rax
0x18000c808  jnz     loc_18000CB0B
0x18000c80e  mov     rax, cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18000c815  cmp     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rdi; int (*g_pfnSwitchToThread)(void)
0x18000c81c  jz      loc_18000CB55
0x18000c822  cmp     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rdi; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18000c829  jz      loc_18000CB68
0x18000c82f  test    rax, rax
0x18000c832  jz      loc_18000CA7F
0x18000c838  mov     eax, cs:?s_nCPUs@?1??NumProcessors@@9@4HA; int `NumProcessors'::`2'::s_nCPUs
0x18000c83e  test    eax, eax
0x18000c840  jz      loc_18000CB7B
0x18000c846  mov     cs:?g_cProcessors@@3KA, eax; ulong g_cProcessors
0x18000c84c  mov     eax, 1
0x18000c851  xchg    eax, cs:?g_fLocksInitialized@@3HA; int g_fLocksInitialized
0x18000c857  mov     eax, edi
0x18000c859  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18000c85f  mov     edx, 80000000h; dwSpinCount
0x18000c864  mov     cs:dword_18004D98C, 2
0x18000c86e  lea     rcx, CriticalSection; lpCriticalSection
0x18000c875  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c87b  test    eax, eax
0x18000c87d  jz      loc_18000CA06
0x18000c883  mov     edx, 80000000h; dwSpinCount
0x18000c888  mov     cs:dword_18004D98C, 3
0x18000c892  lea     rcx, ?g_SchedulerCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c899  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c89f  test    eax, eax
0x18000c8a1  jz      loc_18000CA06
0x18000c8a7  mov     edx, 800003E8h; dwSpinCount
0x18000c8ac  mov     cs:dword_18004D98C, 4
0x18000c8b6  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c8bd  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c8c3  test    eax, eax
0x18000c8c5  jz      loc_18000CA06
0x18000c8cb  cmp     cs:dword_18004E67C, edi
0x18000c8d1  mov     cs:?g_fInitCsTimerWrap@@3HA, 1; int g_fInitCsTimerWrap
0x18000c8db  mov     cs:dword_18004D98C, 5
0x18000c8e5  jz      loc_18000CA24
0x18000c8eb  mov     eax, cs:dword_18004E678
0x18000c8f1  mov     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x18000c8f7  call    cs:__imp_GetProcessHeap
0x18000c8fd  mov     cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA, rax; void * ALLOC_CACHE_HANDLER::sm_hHeap
0x18000c904  mov     edx, 800003E8h; dwSpinCount
0x18000c909  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c910  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18000c917  mov     cs:qword_18004D9C8, rax
0x18000c91e  mov     cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18000c925  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c92b  test    eax, eax
0x18000c92d  jz      loc_18000C9FA
0x18000c933  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 1; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18000c93d  mov     cs:dword_18004D98C, 6
0x18000c947  call    LKRHashTableInit
0x18000c94c  test    al, al
0x18000c94e  jz      loc_18000CA06
0x18000c954  mov     ecx, 100h; Size
0x18000c959  mov     cs:dword_18004D98C, 7
0x18000c963  mov     [rsp+78h+var_48], 1
0x18000c96b  mov     [rsp+78h+var_44], 3E8h
0x18000c973  mov     [rsp+78h+var_40], 1A0h
0x18000c97b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c980  test    rax, rax
0x18000c983  jz      loc_18000CA1B
0x18000c989  mov     r9d, 1; int
0x18000c98f  lea     r8, [rsp+78h+var_48]; struct ALLOC_CACHE_CONFIGURATION *
0x18000c994  lea     rdx, aBigRefTraceEnt; "BIG_REF_TRACE_ENTRY"
0x18000c99b  mov     rcx, rax; this
0x18000c99e  call    ??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000c9a3  mov     cs:?sm_pachBigRefTrace@BIG_REF_TRACE@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * BIG_REF_TRACE::sm_pachBigRefTrace
0x18000c9aa  test    rax, rax
0x18000c9ad  jz      short loc_18000CA06
0x18000c9af  mov     edx, 3E8h; dwSpinCount
0x18000c9b4  mov     cs:dword_18004D98C, 8
0x18000c9be  lea     rcx, ?sm_csLock@EVENT_LOG@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c9c5  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000c9cb  test    eax, eax
0x18000c9cd  jz      loc_18000CA63
0x18000c9d3  mov     cs:?sm_fLockInitialized@EVENT_LOG@@0HA, 1; int EVENT_LOG::sm_fLockInitialized
0x18000c9dd  mov     cs:dword_18004D98C, 9
0x18000c9e7  mov     eax, 1
0x18000c9ec  mov     rbx, [rsp+78h+arg_8]
0x18000c9f4  add     rsp, 70h
0x18000c9f8  pop     rdi
0x18000c9f9  retn
0x18000c9fa  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, edi; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18000ca00  jnz     loc_18000CBC2
0x18000ca06  call    TerminateIISUtilProcessDetach
0x18000ca0b  mov     rbx, [rsp+78h+arg_8]
0x18000ca13  xor     eax, eax
0x18000ca15  add     rsp, 70h
0x18000ca19  pop     rdi
0x18000ca1a  retn
0x18000ca1b  mov     cs:?sm_pachBigRefTrace@BIG_REF_TRACE@@0PEAVALLOC_CACHE_HANDLER@@EA, rdi; ALLOC_CACHE_HANDLER * BIG_REF_TRACE::sm_pachBigRefTrace
0x18000ca22  jmp     short loc_18000CA06
0x18000ca24  lea     rcx, aVerifierDll; "verifier.dll"
0x18000ca2b  call    cs:__imp_GetModuleHandleW
0x18000ca31  test    rax, rax
0x18000ca34  jnz     loc_18000CBA7
0x18000ca3a  mov     rax, gs:60h
0x18000ca43  test    rax, rax
0x18000ca46  jnz     loc_18000CBB1
0x18000ca4c  mov     eax, edi
0x18000ca4e  mov     cs:dword_18004E678, eax
0x18000ca54  mov     cs:dword_18004E67C, 1
0x18000ca5e  jmp     loc_18000C8F1
0x18000ca63  call    cs:__imp_GetLastError
0x18000ca69  test    eax, eax
0x18000ca6b  jle     short loc_18000CA77
0x18000ca6d  movzx   eax, ax
0x18000ca70  or      eax, 80070000h
0x18000ca75  test    eax, eax
0x18000ca77  jns     loc_18000C9DD
0x18000ca7d  jmp     short loc_18000CA06
0x18000ca7f  lea     rax, ?Initialize@MULTI_IPM@@QEAAJXZ; MULTI_IPM::Initialize(void)
0x18000ca86  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18000ca8d  jmp     loc_18000C838
0x18000ca92  mov     rcx, [rsp+78h+hKey]
0x18000ca9a  mov     edx, ebx
0x18000ca9c  call    PuLoadDebugFlagsFromReg
0x18000caa1  mov     rcx, [rsp+78h+hKey]; hKey
0x18000caa9  mov     ebx, eax
0x18000caab  call    cs:__imp_RegCloseKey
0x18000cab1  mov     [rsp+78h+hKey], rdi
0x18000cab9  jmp     loc_18000C7B4
0x18000cabe  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000cac5  lea     rax, aInitializeiisu_1; "InitializeIISUtilProcessAttach\n"
0x18000cacc  lea     r9, aInitializeiisu_0; "InitializeIISUtilProcessAttach"
0x18000cad3  mov     [rsp+78h+var_58], rax; char *
0x18000cad8  mov     r8d, 92h; unsigned int
0x18000cade  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000cae5  call    PuDbgPrint
0x18000caea  jmp     loc_18000C7CE
0x18000caef  xor     ecx, ecx; dwMilliseconds
0x18000caf1  call    cs:__imp_Sleep
0x18000caf7  mov     eax, 1
0x18000cafc  xchg    eax, cs:?g_lckInit@@3VCSimpleLock@@A; CSimpleLock g_lckInit
0x18000cb02  test    eax, eax
0x18000cb04  jnz     short loc_18000CAEF
0x18000cb06  jmp     loc_18000C7ED
0x18000cb0b  lea     rdx, ProcName; "SwitchToThread"
0x18000cb12  mov     rcx, rbx; hModule
0x18000cb15  call    cs:__imp_GetProcAddress
0x18000cb1b  lea     rdx, aTryentercritic; "TryEnterCriticalSection"
0x18000cb22  mov     rcx, rbx; hModule
0x18000cb25  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rax; int (*g_pfnSwitchToThread)(void)
0x18000cb2c  call    cs:__imp_GetProcAddress
0x18000cb32  lea     rdx, aSetcriticalsec; "SetCriticalSectionSpinCount"
0x18000cb39  mov     rcx, rbx; hModule
0x18000cb3c  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rax; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18000cb43  call    cs:__imp_GetProcAddress
0x18000cb49  mov     cs:?g_pfnSetCSSpinCount@@3P6AKPEAU_RTL_CRITICAL_SECTION@@K@ZEA, rax; ulong (*g_pfnSetCSSpinCount)(_RTL_CRITICAL_SECTION *,ulong)
0x18000cb50  jmp     loc_18000C815
0x18000cb55  lea     rcx, ?Initialize@MULTI_IPM@@QEAAJXZ; MULTI_IPM::Initialize(void)
0x18000cb5c  mov     cs:?g_pfnSwitchToThread@@3P6AHXZEA, rcx; int (*g_pfnSwitchToThread)(void)
0x18000cb63  jmp     loc_18000C822
0x18000cb68  lea     rcx, ?Initialize@MULTI_IPM@@QEAAJXZ; MULTI_IPM::Initialize(void)
0x18000cb6f  mov     cs:?g_pfnTryEnterCritSec@@3P6AHPEAU_RTL_CRITICAL_SECTION@@@ZEA, rcx; int (*g_pfnTryEnterCritSec)(_RTL_CRITICAL_SECTION *)
0x18000cb76  jmp     loc_18000C82F
0x18000cb7b  xorps   xmm0, xmm0
0x18000cb7e  lea     rcx, [rsp+78h+SystemInfo]; lpSystemInfo
0x18000cb83  movups  xmmword ptr [rsp+78h+SystemInfo], xmm0
0x18000cb88  movups  xmmword ptr [rsp+78h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000cb8d  movups  xmmword ptr [rsp+78h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000cb92  call    cs:__imp_GetSystemInfo
0x18000cb98  mov     eax, [rsp+78h+SystemInfo.dwNumberOfProcessors]
0x18000cb9c  mov     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, eax; int `NumProcessors'::`2'::s_nCPUs
0x18000cba2  jmp     loc_18000C846
0x18000cba7  mov     eax, 1
0x18000cbac  jmp     loc_18000CA4E
0x18000cbb1  mov     eax, [rax+0BCh]
0x18000cbb7  shr     eax, 19h
0x18000cbba  and     eax, 1
0x18000cbbd  jmp     loc_18000CA4E
0x18000cbc2  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000cbc9  call    cs:__imp_DeleteCriticalSection
0x18000cbcf  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, edi; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x18000cbd5  jmp     loc_18000CA06
```
