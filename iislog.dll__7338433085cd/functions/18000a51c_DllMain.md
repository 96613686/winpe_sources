# DllMain

- ea: `0x18000a51c`
- end: `0x18000a6b0`
- name: `DllMain`
- size: `404`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001314`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000a51c`

## import_xrefs

- `ATL!__imp_AtlModuleInit` at `0x18000a5a6`
- `ATL!__imp_AtlModuleInit` at `0x18000a5a6`
- `ATL!__imp_AtlModuleTerm` at `0x18000a686`
- `ATL!__imp_AtlModuleTerm` at `0x18000a686`
- `IisRTL!PuDbgPrint` at `0x18000a633`
- `IisRTL!PuDbgPrint` at `0x18000a633`
- `IisRTL!IISGetPlatformType` at `0x18000a53a`
- `IisRTL!IISGetPlatformType` at `0x18000a639`
- `IisRTL!IISGetPlatformType` at `0x18000a53a`
- `IisRTL!IISGetPlatformType` at `0x18000a639`
- `IisRTL!PuCreateDebugPrintsObject` at `0x18000a54c`
- `IisRTL!PuCreateDebugPrintsObject` at `0x18000a54c`
- `IisRTL!PuLoadDebugFlagsFromRegStr` at `0x18000a574`
- `IisRTL!PuLoadDebugFlagsFromRegStr` at `0x18000a574`
- `IisRTL!??0EVENT_LOG@@QEAA@PEBD@Z` at `0x18000a5d5`
- `IisRTL!??0EVENT_LOG@@QEAA@PEBD@Z` at `0x18000a5d5`
- `IisRTL!PuDeleteDebugPrintsObject` at `0x18000a693`
- `IisRTL!PuDeleteDebugPrintsObject` at `0x18000a693`
- `IisRTL!??1EVENT_LOG@@QEAA@XZ` at `0x18000a659`
- `IisRTL!??1EVENT_LOG@@QEAA@XZ` at `0x18000a659`
- `KERNEL32!GetLastError` at `0x18000a5fd`
- `KERNEL32!GetLastError` at `0x18000a5fd`
- `KERNEL32!InitializeCriticalSection` at `0x18000a5b3`
- `KERNEL32!InitializeCriticalSection` at `0x18000a5b3`
- `KERNEL32!DeleteCriticalSection` at `0x18000a679`
- `KERNEL32!DeleteCriticalSection` at `0x18000a679`
- `KERNEL32!OutputDebugStringA` at `0x18000a565`
- `KERNEL32!OutputDebugStringA` at `0x18000a565`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000a642`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000a642`

## string_xrefs

- `0x18000a545`: `iislog.dll`
- `0x18000a55e`: `Unable to Create Debug Print Object \n`
- `0x18000a56d`: `System\CurrentControlSet\Services\InetInfo\Parameters`
- `0x18000a61c`: `Unable to create eventlog[%s] object[err %d]\n`
- `0x18000a60a`: `DllMain`
- `0x18000a615`: `inetsrv\iis\svcs\infocomm\log\plugin\plugin1.cpp`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int DebugFlagsFromRegStr; // eax
  EVENT_LOG *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  DWORD LastError; // eax
  void *v10; // rbx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      IISGetPlatformType(hinstDLL, fdwReason, lpvReserved);
      g_pDebug = PuCreateDebugPrintsObject("iislog.dll", 1);
      if ( !g_pDebug )
        OutputDebugStringA("Unable to Create Debug Print Object \n");
      DebugFlagsFromRegStr = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\InetInfo\\Parameters", 0);
      _Module = 176;
      g_dwDebugFlags = DebugFlagsFromRegStr;
      qword_180017B00 = 0;
      AtlModuleInit(&_Module, &off_180017000, hinstDLL);
      InitializeCriticalSection(&g_csGlobalLoggingProperties);
      v5 = (EVENT_LOG *)operator new(0x10u);
      if ( v5 )
      {
        g_eventLog = EVENT_LOG::EVENT_LOG(v5, "IISLOG");
        if ( g_eventLog )
        {
LABEL_11:
          IISGetPlatformType(v7, v6, v8);
          DisableThreadLibraryCalls(hinstDLL);
          return 1;
        }
      }
      else
      {
        g_eventLog = 0;
      }
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LastError = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\plugin1.cpp",
          78,
          "DllMain",
          "Unable to create eventlog[%s] object[err %d]\n",
          "IISLOG",
          LastError);
      }
      goto LABEL_11;
    }
  }
  else
  {
    v10 = g_eventLog;
    if ( g_eventLog )
    {
      EVENT_LOG::~EVENT_LOG((EVENT_LOG *)g_eventLog);
      operator delete(v10);
      g_eventLog = 0;
    }
    DeleteCriticalSection(&g_csGlobalLoggingProperties);
    AtlModuleTerm(&_Module);
    g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a51c  mov     [rsp+arg_0], rbx
0x18000a521  push    rbp
0x18000a522  sub     rsp, 40h
0x18000a526  mov     rbx, rcx
0x18000a529  test    edx, edx
0x18000a52b  jz      loc_18000A64A
0x18000a531  cmp     edx, 1
0x18000a534  jnz     loc_18000A6A0
0x18000a53a  call    cs:__imp_IISGetPlatformType
0x18000a540  mov     edx, 1
0x18000a545  lea     rcx, aIislogDll_1; "iislog.dll"
0x18000a54c  call    cs:__imp_PuCreateDebugPrintsObject
0x18000a552  mov     cs:g_pDebug, rax
0x18000a559  test    rax, rax
0x18000a55c  jnz     short loc_18000A56B
0x18000a55e  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x18000a565  call    cs:__imp_OutputDebugStringA
0x18000a56b  xor     edx, edx
0x18000a56d  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\In"...
0x18000a574  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x18000a57a  mov     r8, rbx
0x18000a57d  mov     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18000a587  lea     rdx, off_180017000
0x18000a58e  mov     cs:g_dwDebugFlags, eax
0x18000a594  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000a59b  mov     cs:qword_180017B00, 0
0x18000a5a6  call    cs:__imp_AtlModuleInit
0x18000a5ac  lea     rcx, ?g_csGlobalLoggingProperties@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a5b3  call    cs:__imp_InitializeCriticalSection
0x18000a5b9  mov     ecx, 10h; Size
0x18000a5be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a5c3  lea     rbp, aIislog; "IISLOG"
0x18000a5ca  test    rax, rax
0x18000a5cd  jz      short loc_18000A5E9
0x18000a5cf  mov     rdx, rbp
0x18000a5d2  mov     rcx, rax
0x18000a5d5  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBD@Z; EVENT_LOG::EVENT_LOG(char const *)
0x18000a5db  mov     cs:?g_eventLog@@3PEAVEVENT_LOG@@EA, rax; EVENT_LOG * g_eventLog
0x18000a5e2  test    rax, rax
0x18000a5e5  jnz     short loc_18000A639
0x18000a5e7  jmp     short loc_18000A5F4
0x18000a5e9  mov     cs:?g_eventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_eventLog
0x18000a5f4  test    byte ptr cs:g_dwDebugFlags, 3
0x18000a5fb  jz      short loc_18000A639
0x18000a5fd  call    cs:__imp_GetLastError
0x18000a603  mov     rcx, cs:g_pDebug
0x18000a60a  lea     r9, aDllmain; "DllMain"
0x18000a611  mov     [rsp+48h+var_18], eax
0x18000a615  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000a61c  lea     rax, aUnableToCreate_0; "Unable to create eventlog[%s] object[er"...
0x18000a623  mov     [rsp+48h+var_20], rbp
0x18000a628  mov     r8d, 4Eh ; 'N'
0x18000a62e  mov     [rsp+48h+var_28], rax
0x18000a633  call    cs:__imp_PuDbgPrint
0x18000a639  call    cs:__imp_IISGetPlatformType
0x18000a63f  mov     rcx, rbx; hLibModule
0x18000a642  call    cs:__imp_DisableThreadLibraryCalls
0x18000a648  jmp     short loc_18000A6A0
0x18000a64a  mov     rbx, cs:?g_eventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_eventLog
0x18000a651  test    rbx, rbx
0x18000a654  jz      short loc_18000A672
0x18000a656  mov     rcx, rbx
0x18000a659  call    cs:__imp_??1EVENT_LOG@@QEAA@XZ; EVENT_LOG::~EVENT_LOG(void)
0x18000a65f  mov     rcx, rbx; Block
0x18000a662  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a667  mov     cs:?g_eventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_eventLog
0x18000a672  lea     rcx, ?g_csGlobalLoggingProperties@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a679  call    cs:__imp_DeleteCriticalSection
0x18000a67f  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000a686  call    cs:__imp_AtlModuleTerm
0x18000a68c  mov     rcx, cs:g_pDebug
0x18000a693  call    cs:__imp_PuDeleteDebugPrintsObject
0x18000a699  mov     cs:g_pDebug, rax
0x18000a6a0  mov     rbx, [rsp+48h+arg_0]
0x18000a6a5  mov     eax, 1
0x18000a6aa  add     rsp, 40h
0x18000a6ae  pop     rbp
0x18000a6af  retn
```
