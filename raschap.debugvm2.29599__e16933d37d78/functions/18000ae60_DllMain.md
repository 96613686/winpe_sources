# DllMain

- ea: `0x18000ae60`
- end: `0x18000afeb`
- name: `DllMain`
- size: `395`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180013994`

## callees

- `0x18000ae60`
- `0x18000b000`
- `0x18000b040`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ae92`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ae92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afcc`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000af18`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000af18`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000af8d`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000af8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000afb2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000afb2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae82`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ae82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000afc2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000afc2`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v4; // rdi
  const GUID **v5; // rsi
  const GUID *v6; // r8
  _QWORD *v8; // rdi
  TRACEHANDLE v9; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason == 1 )
  {
    InitializeCriticalSection(&g_criticalSection);
    g_hInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    qword_1800337D0 = 1;
    qword_1800337C8 = 0;
    v4 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_EapHostCtlGuid;
    v5 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    do
    {
      v6 = *v5;
      TraceGuidReg.Guid = v6;
      ++v5;
      TraceGuidReg.RegHandle = 0;
      v4[4] = (ULONG64)v6;
      RegisterTraceGuidsW(WppControlCallback, v4, v6, 1u, &TraceGuidReg, 0, 0, v4 + 1);
      v4 = (ULONG64 *)*v4;
    }
    while ( v4 );
    McGenEventRegister_EventRegister();
  }
  else if ( !fdwReason )
  {
    EnterCriticalSection(&g_EapCredThreadState);
    if ( hObject )
    {
      if ( WaitForSingleObject(hObject, 0xFFFFFFFF) )
        GetLastError();
      CloseHandle(hObject);
      hObject = 0;
    }
    LeaveCriticalSection(&g_EapCredThreadState);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( WPP_GLOBAL_Control )
      {
        do
        {
          v9 = v8[1];
          if ( v9 )
          {
            UnregisterTraceGuids(v9);
            v8[1] = 0;
          }
          v8 = (_QWORD *)*v8;
        }
        while ( v8 );
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    McGenEventUnregister_EventUnregister();
    DeleteCriticalSection(&g_criticalSection);
  }
  return 1;
}

```

## disassembly

```asm
0x18000ae60  mov     [rsp+arg_0], rbx
0x18000ae65  mov     [rsp+arg_8], rsi
0x18000ae6a  push    rdi
0x18000ae6b  sub     rsp, 50h
0x18000ae6f  mov     rbx, rcx
0x18000ae72  cmp     edx, 1
0x18000ae75  jnz     loc_18000AF40
0x18000ae7b  lea     rcx, g_criticalSection; lpCriticalSection
0x18000ae82  call    cs:__imp_InitializeCriticalSection
0x18000ae88  mov     rcx, rbx; hLibModule
0x18000ae8b  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInstance
0x18000ae92  call    cs:__imp_DisableThreadLibraryCalls
0x18000ae98  xor     ebx, ebx
0x18000ae9a  mov     cs:qword_1800337D0, 1
0x18000aea5  lea     rax, WPP_ThisDir_CTLGUID_EapHostCtlGuid
0x18000aeac  mov     cs:qword_1800337C8, rbx
0x18000aeb3  lea     rdi, WPP_MAIN_CB
0x18000aeba  mov     cs:WPP_MAIN_CB, rbx
0x18000aec1  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000aec8  lea     rsi, WPP_REGISTRATION_GUIDS
0x18000aecf  mov     cs:WPP_GLOBAL_Control, rdi
0x18000aed6  mov     r8, [rsi]; ControlGuid
0x18000aed9  lea     rax, [rdi+8]
0x18000aedd  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x18000aee2  lea     rcx, WppControlCallback; RequestAddress
0x18000aee9  mov     [rsp+58h+MofResourceName], rbx; MofResourceName
0x18000aeee  lea     rax, [rsp+58h+var_18]
0x18000aef3  mov     [rsp+58h+var_18.Guid], r8
0x18000aef8  lea     rsi, [rsi+8]
0x18000aefc  mov     [rsp+58h+var_18.RegHandle], rbx
0x18000af01  mov     r9d, 1; GuidCount
0x18000af07  mov     [rsp+58h+MofImagePath], rbx; MofImagePath
0x18000af0c  mov     rdx, rdi; RequestContext
0x18000af0f  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x18000af14  mov     [rdi+20h], r8
0x18000af18  call    cs:__imp_RegisterTraceGuidsW
0x18000af1e  mov     rdi, [rdi]
0x18000af21  test    rdi, rdi
0x18000af24  jnz     short loc_18000AED6
0x18000af26  call    McGenEventRegister_EventRegister
0x18000af2b  mov     rbx, [rsp+58h+arg_0]
0x18000af30  mov     eax, 1
0x18000af35  mov     rsi, [rsp+58h+arg_8]
0x18000af3a  add     rsp, 50h
0x18000af3e  pop     rdi
0x18000af3f  retn
0x18000af40  test    edx, edx
0x18000af42  jnz     short loc_18000AF2B
0x18000af44  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; lpCriticalSection
0x18000af4b  call    cs:__imp_EnterCriticalSection
0x18000af51  mov     rcx, cs:hObject; hHandle
0x18000af58  xor     ebx, ebx
0x18000af5a  test    rcx, rcx
0x18000af5d  jnz     short loc_18000AFBD
0x18000af5f  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; lpCriticalSection
0x18000af66  call    cs:__imp_LeaveCriticalSection
0x18000af6c  mov     rdi, cs:WPP_GLOBAL_Control
0x18000af73  lea     rsi, WPP_GLOBAL_Control
0x18000af7a  cmp     rdi, rsi
0x18000af7d  jz      short loc_18000AFA6
0x18000af7f  test    rdi, rdi
0x18000af82  jz      short loc_18000AF9F
0x18000af84  mov     rcx, [rdi+8]; RegistrationHandle
0x18000af88  test    rcx, rcx
0x18000af8b  jz      short loc_18000AF97
0x18000af8d  call    cs:__imp_UnregisterTraceGuids
0x18000af93  mov     [rdi+8], rbx
0x18000af97  mov     rdi, [rdi]
0x18000af9a  test    rdi, rdi
0x18000af9d  jnz     short loc_18000AF84
0x18000af9f  mov     cs:WPP_GLOBAL_Control, rsi
0x18000afa6  call    McGenEventUnregister_EventUnregister
0x18000afab  lea     rcx, g_criticalSection; lpCriticalSection
0x18000afb2  call    cs:__imp_DeleteCriticalSection
0x18000afb8  jmp     loc_18000AF2B
0x18000afbd  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000afc2  call    cs:__imp_WaitForSingleObject
0x18000afc8  test    eax, eax
0x18000afca  jz      short loc_18000AFD2
0x18000afcc  call    cs:__imp_GetLastError
0x18000afd2  mov     rcx, cs:hObject; hObject
0x18000afd9  call    cs:__imp_CloseHandle
0x18000afdf  mov     cs:hObject, rbx
0x18000afe6  jmp     loc_18000AF5F
```
