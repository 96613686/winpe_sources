# DllMain

- ea: `0x180004ba8`
- end: `0x180004c85`
- name: `DllMain`
- size: `221`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x18000b274`

## callees

- `0x180004ba8`
- `0x180004c8c`
- `0x1800050c4`
- `0x180005114`
- `0x180005130`
- `0x1800052ac`
- `0x180005368`
- `0x1800053cc`
- `0x1800053f0`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  CTelemetryHelper *v7; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      McGenEventRegister_EventRegister(
        Direct3D12EtwProviderGuid,
        McGenControlCallbackV2,
        Direct3D12EtwProviderGuid_Context,
        Direct3D12EtwProviderGuid_Context);
      McGenEventRegister_EventRegister(
        PIX_ETW_PROVIDER,
        PixMcGenControlCallbackV2,
        PIX_ETW_PROVIDER_Context,
        PIX_ETW_PROVIDER_Context);
      CD3D12TelemetryHelper::Register((CD3D12TelemetryHelper *)&g_Telemetry);
      CTelemetryHelper::LogDllAttachEvent(v7);
    }
    else if ( fdwReason == 3 )
    {
      CleanupPixEtwThread();
    }
  }
  else
  {
    wil::details::g_pfnLoggingCallback = 0;
    TraceLoggingUnregister_EventUnregister(off_18001C110);
    McGenEventUnregister_EventUnregister(PIX_ETW_PROVIDER_Context);
    McGenEventUnregister_EventUnregister(Direct3D12EtwProviderGuid_Context);
    PEvtStopService();
  }
  return CModule::DllMain((CModule *)hinstDLL, hinstDLL, fdwReason, lpvReserved);
}

```

## disassembly

```asm
0x180004ba8  mov     [rsp+arg_0], rbx
0x180004bad  mov     [rsp+arg_8], rsi
0x180004bb2  push    rdi
0x180004bb3  sub     rsp, 20h
0x180004bb7  mov     rdi, r8
0x180004bba  mov     ebx, edx
0x180004bbc  mov     rsi, rcx
0x180004bbf  mov     eax, edx
0x180004bc1  test    edx, edx
0x180004bc3  jz      loc_180004C4C
0x180004bc9  sub     eax, 1
0x180004bcc  jz      short loc_180004BF7
0x180004bce  cmp     eax, 2
0x180004bd1  jz      short loc_180004BF0
0x180004bd3  mov     r9, rdi; void *
0x180004bd6  mov     r8d, ebx; unsigned int
0x180004bd9  mov     rdx, rsi; HINSTANCE
0x180004bdc  mov     rbx, [rsp+28h+arg_0]
0x180004be1  mov     rsi, [rsp+28h+arg_8]
0x180004be6  add     rsp, 20h
0x180004bea  pop     rdi
0x180004beb  jmp     ?DllMain@CModule@@QEAAHPEAUHINSTANCE__@@KPEAX@Z; CModule::DllMain(HINSTANCE__ *,ulong,void *)
0x180004bf0  call    ?CleanupPixEtwThread@@YAXXZ; CleanupPixEtwThread(void)
0x180004bf5  jmp     short loc_180004BD3
0x180004bf7  lea     r9, Direct3D12EtwProviderGuid_Context
0x180004bfe  lea     r8, Direct3D12EtwProviderGuid_Context
0x180004c05  lea     rdx, McGenControlCallbackV2
0x180004c0c  lea     rcx, Direct3D12EtwProviderGuid
0x180004c13  call    McGenEventRegister_EventRegister
0x180004c18  lea     r9, PIX_ETW_PROVIDER_Context
0x180004c1f  lea     r8, PIX_ETW_PROVIDER_Context
0x180004c26  lea     rdx, PixMcGenControlCallbackV2
0x180004c2d  lea     rcx, PIX_ETW_PROVIDER
0x180004c34  call    McGenEventRegister_EventRegister
0x180004c39  lea     rcx, ?g_Telemetry@@3VCD3D12TelemetryHelper@@A; this
0x180004c40  call    ?Register@CD3D12TelemetryHelper@@UEAAJXZ; CD3D12TelemetryHelper::Register(void)
0x180004c45  call    ?LogDllAttachEvent@CTelemetryHelper@@QEAAXXZ; CTelemetryHelper::LogDllAttachEvent(void)
0x180004c4a  jmp     short loc_180004BD3
0x180004c4c  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x180004c57  mov     rcx, cs:off_18001C110
0x180004c5e  call    TraceLoggingUnregister_EventUnregister
0x180004c63  lea     rcx, PIX_ETW_PROVIDER_Context
0x180004c6a  call    McGenEventUnregister_EventUnregister
0x180004c6f  lea     rcx, Direct3D12EtwProviderGuid_Context
0x180004c76  call    McGenEventUnregister_EventUnregister
0x180004c7b  call    ?PEvtStopService@@YAJXZ; PEvtStopService(void)
0x180004c80  jmp     loc_180004BD3
```
