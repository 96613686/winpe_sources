# DllMain

- ea: `0x18000d9d8`
- end: `0x18000dae1`
- name: `DllMain`
- size: `265`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003864`

## callees

- `0x180001008`
- `0x18000d9d8`
- `0x18000dc18`
- `0x18000dc3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000d9e9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000d9e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da53`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000da81`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000daa3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000dad1`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000da81`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000daa3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000dad1`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  REGHANDLE v5; // rcx
  REGHANDLE v6; // rcx
  REGHANDLE v7; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      McGenEventRegister_EventRegister(MDM_PUSHROUTER, v3, MDM_PUSHROUTER_Context, MDM_PUSHROUTER_Context);
      McGenEventRegister_EventRegister(
        MDM_ENTERPRISE_DIAGNOSTICS,
        v4,
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        MDM_ENTERPRISE_DIAGNOSTICS_Context);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180050120);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800500E8);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180050060);
    }
  }
  else
  {
    DeleteCriticalSection(&g_csPushRouter);
    McGenEventUnregister_EventUnregister(MDM_PUSHROUTER_Context);
    v5 = RegHandle;
    dword_180050120 = 0;
    RegHandle = 0;
    EventUnregister(v5);
    v6 = qword_180050108;
    dword_1800500E8 = 0;
    qword_180050108 = 0;
    EventUnregister(v6);
    McGenEventUnregister_EventUnregister(MDM_ENTERPRISE_DIAGNOSTICS_Context);
    v7 = qword_180050080;
    dword_180050060 = 0;
    qword_180050080 = 0;
    EventUnregister(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18000d9d8  sub     rsp, 28h
0x18000d9dc  test    edx, edx
0x18000d9de  jz      short loc_18000DA4C
0x18000d9e0  cmp     edx, 1
0x18000d9e3  jnz     loc_18000DAD7
0x18000d9e9  call    cs:__imp_DisableThreadLibraryCalls
0x18000d9ef  lea     r9, MDM_PUSHROUTER_Context
0x18000d9f6  lea     r8, MDM_PUSHROUTER_Context
0x18000d9fd  lea     rcx, MDM_PUSHROUTER
0x18000da04  call    McGenEventRegister_EventRegister
0x18000da09  lea     r9, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18000da10  lea     r8, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18000da17  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS
0x18000da1e  call    McGenEventRegister_EventRegister
0x18000da23  lea     rcx, dword_180050120; CallbackContext
0x18000da2a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000da2f  lea     rcx, dword_1800500E8; CallbackContext
0x18000da36  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000da3b  lea     rcx, dword_180050060; CallbackContext
0x18000da42  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000da47  jmp     loc_18000DAD7
0x18000da4c  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000da53  call    cs:__imp_DeleteCriticalSection
0x18000da59  lea     rcx, MDM_PUSHROUTER_Context
0x18000da60  call    McGenEventUnregister_EventUnregister
0x18000da65  mov     rcx, cs:RegHandle; RegHandle
0x18000da6c  mov     cs:dword_180050120, 0
0x18000da76  mov     cs:RegHandle, 0
0x18000da81  call    cs:__imp_EventUnregister
0x18000da87  mov     rcx, cs:qword_180050108; RegHandle
0x18000da8e  mov     cs:dword_1800500E8, 0
0x18000da98  mov     cs:qword_180050108, 0
0x18000daa3  call    cs:__imp_EventUnregister
0x18000daa9  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18000dab0  call    McGenEventUnregister_EventUnregister
0x18000dab5  mov     rcx, cs:qword_180050080; RegHandle
0x18000dabc  mov     cs:dword_180050060, 0
0x18000dac6  mov     cs:qword_180050080, 0
0x18000dad1  call    cs:__imp_EventUnregister
0x18000dad7  mov     eax, 1
0x18000dadc  add     rsp, 28h
0x18000dae0  retn
```
