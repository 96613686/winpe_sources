# DllMain

- ea: `0x18000bec0`
- end: `0x18000bfbf`
- name: `DllMain`
- size: `255`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ce24`

## callees

- `0x180008e60`
- `0x180008f90`
- `0x180009900`
- `0x18000bec0`
- `0x18000bfc8`
- `0x18000d81c`
- `0x180010ed4`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x18000bf74`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000bf74`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  _QWORD *v4; // rdi
  TRACEHANDLE v5; // rcx

  if ( fdwReason == 1 )
  {
    McGenEventRegister_EventRegister(
      FH_CORE_PROVIDER_GUID,
      fdwReason,
      FH_CORE_PROVIDER_GUID_Context,
      FH_CORE_PROVIDER_GUID_Context);
    McGenEventRegister_EventRegister(
      FH_SERVICE_PROVIDER_GUID,
      v3,
      FH_SERVICE_PROVIDER_GUID_Context,
      FH_SERVICE_PROVIDER_GUID_Context);
    StartTracingSession();
    qword_180019868 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
    qword_180019860 = 0;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    WriteTraceHeader();
  }
  else if ( !fdwReason )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v4 )
      {
        v5 = v4[1];
        if ( v5 )
        {
          UnregisterTraceGuids(v5);
          v4[1] = 0;
        }
        v4 = (_QWORD *)*v4;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    StopTracingSession();
    McGenEventUnregister_EventUnregister(FH_CORE_PROVIDER_GUID_Context);
    McGenEventUnregister_EventUnregister(FH_SERVICE_PROVIDER_GUID_Context);
  }
  return 1;
}

```

## disassembly

```asm
0x18000bec0  mov     [rsp+arg_0], rbx
0x18000bec5  mov     [rsp+arg_8], rsi
0x18000beca  push    rdi
0x18000becb  sub     rsp, 20h
0x18000becf  cmp     edx, 1
0x18000bed2  jnz     short loc_18000BF50
0x18000bed4  lea     r9, FH_CORE_PROVIDER_GUID_Context
0x18000bedb  lea     r8, FH_CORE_PROVIDER_GUID_Context
0x18000bee2  lea     rcx, FH_CORE_PROVIDER_GUID
0x18000bee9  call    McGenEventRegister_EventRegister
0x18000beee  lea     r9, FH_SERVICE_PROVIDER_GUID_Context
0x18000bef5  lea     r8, FH_SERVICE_PROVIDER_GUID_Context
0x18000befc  lea     rcx, FH_SERVICE_PROVIDER_GUID
0x18000bf03  call    McGenEventRegister_EventRegister
0x18000bf08  call    ?StartTracingSession@@YAXXZ; StartTracingSession(void)
0x18000bf0d  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x18000bf14  mov     cs:qword_180019868, 1
0x18000bf1f  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000bf26  xor     ebx, ebx
0x18000bf28  lea     rax, WPP_MAIN_CB
0x18000bf2f  mov     cs:qword_180019860, rbx
0x18000bf36  mov     cs:WPP_GLOBAL_Control, rax
0x18000bf3d  mov     cs:WPP_MAIN_CB, rbx
0x18000bf44  call    WppInitUm
0x18000bf49  call    ?WriteTraceHeader@@YAXXZ; WriteTraceHeader(void)
0x18000bf4e  jmp     short loc_18000BFAA
0x18000bf50  xor     ebx, ebx
0x18000bf52  test    edx, edx
0x18000bf54  jnz     short loc_18000BFAA
0x18000bf56  mov     rdi, cs:WPP_GLOBAL_Control
0x18000bf5d  lea     rsi, WPP_GLOBAL_Control
0x18000bf64  cmp     rdi, rsi
0x18000bf67  jz      short loc_18000BF8D
0x18000bf69  jmp     short loc_18000BF81
0x18000bf6b  mov     rcx, [rdi+8]; RegistrationHandle
0x18000bf6f  test    rcx, rcx
0x18000bf72  jz      short loc_18000BF7E
0x18000bf74  call    cs:__imp_UnregisterTraceGuids
0x18000bf7a  mov     [rdi+8], rbx
0x18000bf7e  mov     rdi, [rdi]
0x18000bf81  test    rdi, rdi
0x18000bf84  jnz     short loc_18000BF6B
0x18000bf86  mov     cs:WPP_GLOBAL_Control, rsi
0x18000bf8d  call    ?StopTracingSession@@YAXXZ; StopTracingSession(void)
0x18000bf92  lea     rcx, FH_CORE_PROVIDER_GUID_Context
0x18000bf99  call    McGenEventUnregister_EventUnregister
0x18000bf9e  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x18000bfa5  call    McGenEventUnregister_EventUnregister
0x18000bfaa  mov     rbx, [rsp+28h+arg_0]
0x18000bfaf  mov     eax, 1
0x18000bfb4  mov     rsi, [rsp+28h+arg_8]
0x18000bfb9  add     rsp, 20h
0x18000bfbd  pop     rdi
0x18000bfbe  retn
```
