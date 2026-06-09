# DllMain

- ea: `0x18000a3e8`
- end: `0x18000a500`
- name: `DllMain`
- size: `280`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800032e4`

## callees

- `0x18000a3e8`
- `0x18000a618`
- `0x18000a63c`
- `0x1800b8670`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a402`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a402`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4e1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a40f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a41c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a40f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a41c`
- `ntdll!WinSqmStartSession` at `0x18000a480`
- `ntdll!WinSqmStartSession` at `0x18000a480`
- `ntdll!WinSqmEndSession` at `0x18000a4b3`
- `ntdll!WinSqmEndSession` at `0x18000a4b3`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      InitializeCriticalSection(&g_csDll);
      InitializeCriticalSection(&RtfToHtmlConverter::_cs);
      RtfToHtmlConverter::_fCSInited = 1;
      g_hInst = hinstDLL;
      McGenEventRegister_EventRegister(
        Microsoft_Windows_OOBE_Machine_Plugins,
        v4,
        Microsoft_Windows_OOBE_Machine_Plugins_Context,
        Microsoft_Windows_OOBE_Machine_Plugins_Context);
      McGenEventRegister_EventRegister(
        Microsoft_Windows_Shell_Core_Provider,
        v5,
        Microsoft_Windows_Shell_Core_Provider_Context,
        Microsoft_Windows_Shell_Core_Provider_Context);
      if ( !*(_QWORD *)&g_hSQMSession.Data1 )
        *(_QWORD *)&g_hSQMSession.Data1 = WinSqmStartSession(&GUID_OOBESQMSession, 1);
    }
  }
  else
  {
    McGenEventUnregister_EventUnregister(Microsoft_Windows_OOBE_Machine_Plugins_Context, fdwReason, lpvReserved);
    McGenEventUnregister_EventUnregister(Microsoft_Windows_Shell_Core_Provider_Context, v6, v7);
    if ( *(_QWORD *)&g_hSQMSession.Data1 )
    {
      WinSqmEndSession();
      *(_QWORD *)&g_hSQMSession.Data1 = 0;
    }
    DeleteCriticalSection(&g_csDll);
    if ( RtfToHtmlConverter::_fCSInited )
      DeleteCriticalSection(&RtfToHtmlConverter::_cs);
    if ( g_fLogInitialized )
      UnattendFinalizeLog();
  }
  return 1;
}

```

## disassembly

```asm
0x18000a3e8  push    rbx
0x18000a3ea  sub     rsp, 20h
0x18000a3ee  mov     rbx, rcx
0x18000a3f1  test    edx, edx
0x18000a3f3  jz      loc_18000A48F
0x18000a3f9  cmp     edx, 1
0x18000a3fc  jnz     loc_18000A4F5
0x18000a402  call    cs:__imp_DisableThreadLibraryCalls
0x18000a408  lea     rcx, g_csDll; lpCriticalSection
0x18000a40f  call    cs:__imp_InitializeCriticalSection
0x18000a415  lea     rcx, ?_cs@RtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a41c  call    cs:__imp_InitializeCriticalSection
0x18000a422  lea     r9, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x18000a429  mov     cs:?_fCSInited@RtfToHtmlConverter@@0_NA, 1; bool RtfToHtmlConverter::_fCSInited
0x18000a430  lea     r8, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x18000a437  mov     cs:g_hInst, rbx
0x18000a43e  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins
0x18000a445  call    McGenEventRegister_EventRegister
0x18000a44a  lea     r9, Microsoft_Windows_Shell_Core_Provider_Context
0x18000a451  lea     r8, Microsoft_Windows_Shell_Core_Provider_Context
0x18000a458  lea     rcx, Microsoft_Windows_Shell_Core_Provider
0x18000a45f  call    McGenEventRegister_EventRegister
0x18000a464  cmp     qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data1, 0; _GUID * g_hSQMSession ...
0x18000a46c  jnz     loc_18000A4F5
0x18000a472  xor     r8d, r8d
0x18000a475  lea     rcx, GUID_OOBESQMSession
0x18000a47c  lea     edx, [r8+1]
0x18000a480  call    cs:__imp_WinSqmStartSession
0x18000a486  mov     qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data1, rax; _GUID * g_hSQMSession ...
0x18000a48d  jmp     short loc_18000A4F5
0x18000a48f  lea     rcx, Microsoft_Windows_OOBE_Machine_Plugins_Context
0x18000a496  call    McGenEventUnregister_EventUnregister
0x18000a49b  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x18000a4a2  call    McGenEventUnregister_EventUnregister
0x18000a4a7  mov     rcx, qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data1; _GUID * g_hSQMSession ...
0x18000a4ae  test    rcx, rcx
0x18000a4b1  jz      short loc_18000A4C4
0x18000a4b3  call    cs:__imp_WinSqmEndSession
0x18000a4b9  mov     qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data1, 0; _GUID * g_hSQMSession ...
0x18000a4c4  lea     rcx, g_csDll; lpCriticalSection
0x18000a4cb  call    cs:__imp_DeleteCriticalSection
0x18000a4d1  cmp     cs:?_fCSInited@RtfToHtmlConverter@@0_NA, 0; bool RtfToHtmlConverter::_fCSInited
0x18000a4d8  jz      short loc_18000A4E7
0x18000a4da  lea     rcx, ?_cs@RtfToHtmlConverter@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a4e1  call    cs:__imp_DeleteCriticalSection
0x18000a4e7  cmp     cs:?g_fLogInitialized@@3_NA, 0; bool g_fLogInitialized
0x18000a4ee  jz      short loc_18000A4F5
0x18000a4f0  call    UnattendFinalizeLog
0x18000a4f5  mov     eax, 1
0x18000a4fa  add     rsp, 20h
0x18000a4fe  pop     rbx
0x18000a4ff  retn
```
