# Process6to4ConfigurationChange

- ea: `0x180004ca0`
- end: `0x180004dd7`
- name: `Process6to4ConfigurationChange`
- size: `311`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d8d4`
- `0x180032ae0`
- `0x180051170`

## callees

- `0x180004ca0`
- `0x180004f60`
- `0x180005228`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d99`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004cd5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004da8`

## string_xrefs

- `0x180004dc1`: `Process6to4ConfigurationChange`
- `0x180004dba`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180004d0c`: `Entered: Queueing worker for Process6to4ConfigurationChange`
- `0x180004d51`: `Leaving: Queued worker for Process6to4ConfigurationChange`
- `0x180004d6f`: `Leaving: Failed to queue worker for Process6to4ConfigurationChange`

## pseudocode

```c
void __fastcall Process6to4ConfigurationChange(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  HANDLE EventW; // rbx
  char v3; // di
  const wchar_t *v4; // r8

  if ( g_StopServiceEventSet || !dword_1800C9754 )
    goto LABEL_21;
  EventW = 0;
  if ( Context )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      GetLastError();
      goto LABEL_21;
    }
  }
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: Queueing worker for Process6to4ConfigurationChange");
  if ( (unsigned int)QueueWorkItemForProtocolEvent(12, EventW, Process6to4ConfigurationHandler) )
  {
    v3 = 0;
    if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    {
      v4 = L"Leaving: Failed to queue worker for Process6to4ConfigurationChange";
      goto LABEL_16;
    }
  }
  else
  {
    v3 = 1;
    if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    {
      v4 = L"Leaving: Queued worker for Process6to4ConfigurationChange";
LABEL_16:
      McTemplateU0z_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
        v4);
    }
  }
  if ( EventW )
  {
    if ( v3 )
      WaitForSingleObject(EventW, 0xFFFFFFFF);
    CloseHandle(EventW);
  }
LABEL_21:
  DereferenceServiceEx("Process6to4ConfigurationChange", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c", 1015);
}

```

## disassembly

```asm
0x180004ca0  mov     [rsp+arg_0], rbx
0x180004ca5  push    rdi
0x180004ca6  sub     rsp, 20h
0x180004caa  cmp     cs:g_StopServiceEventSet, 0
0x180004cb1  jnz     loc_180004DB4
0x180004cb7  cmp     cs:dword_1800C9754, 0
0x180004cbe  jz      loc_180004DB4
0x180004cc4  xor     ebx, ebx
0x180004cc6  test    rdx, rdx
0x180004cc9  jz      short loc_180004CFA
0x180004ccb  xor     r9d, r9d; lpName
0x180004cce  xor     r8d, r8d; bInitialState
0x180004cd1  xor     edx, edx; bManualReset
0x180004cd3  xor     ecx, ecx; lpEventAttributes
0x180004cd5  call    cs:__imp_CreateEventW
0x180004cdc  nop     dword ptr [rax+rax+00h]
0x180004ce1  mov     rbx, rax
0x180004ce4  test    rax, rax
0x180004ce7  jnz     short loc_180004CFA
0x180004ce9  call    cs:__imp_GetLastError
0x180004cf0  nop     dword ptr [rax+rax+00h]
0x180004cf5  jmp     loc_180004DB4
0x180004cfa  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180004d01  jz      short loc_180004D26
0x180004d03  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180004d0a  jge     short loc_180004D26
0x180004d0c  lea     r8, aEnteredQueuein; "Entered: Queueing worker for Process6to"...
0x180004d13  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180004d1a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180004d21  call    McTemplateU0z_EventWriteTransfer
0x180004d26  lea     r8, Process6to4ConfigurationHandler
0x180004d2d  mov     rdx, rbx
0x180004d30  mov     ecx, 0Ch
0x180004d35  call    QueueWorkItemForProtocolEvent
0x180004d3a  test    eax, eax
0x180004d3c  jnz     short loc_180004D5A
0x180004d3e  cmp     cs:IpHlpSvcEtwEnabled, al
0x180004d44  mov     dil, 1
0x180004d47  jz      short loc_180004D89
0x180004d49  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, al
0x180004d4f  jge     short loc_180004D89
0x180004d51  lea     r8, aLeavingQueuedW_0; "Leaving: Queued worker for Process6to4C"...
0x180004d58  jmp     short loc_180004D76
0x180004d5a  xor     dil, dil
0x180004d5d  cmp     cs:IpHlpSvcEtwEnabled, dil
0x180004d64  jz      short loc_180004D89
0x180004d66  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 80h
0x180004d6d  jz      short loc_180004D89
0x180004d6f  lea     r8, aLeavingFailedT_1; "Leaving: Failed to queue worker for Pro"...
0x180004d76  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180004d7d  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180004d84  call    McTemplateU0z_EventWriteTransfer
0x180004d89  test    rbx, rbx
0x180004d8c  jz      short loc_180004DB4
0x180004d8e  test    dil, dil
0x180004d91  jz      short loc_180004DA5
0x180004d93  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004d96  mov     rcx, rbx; hHandle
0x180004d99  call    cs:__imp_WaitForSingleObject
0x180004da0  nop     dword ptr [rax+rax+00h]
0x180004da5  mov     rcx, rbx; hObject
0x180004da8  call    cs:__imp_CloseHandle
0x180004daf  nop     dword ptr [rax+rax+00h]
0x180004db4  mov     r8d, 3F7h
0x180004dba  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004dc1  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x180004dc8  mov     rbx, [rsp+28h+arg_0]
0x180004dcd  add     rsp, 20h
0x180004dd1  pop     rdi
0x180004dd2  jmp     DereferenceServiceEx
```
