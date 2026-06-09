# Process6to4ConfigurationChange

- ea: `0x180004c90`
- end: `0x180004dc7`
- name: `Process6to4ConfigurationChange`
- size: `311`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d8c4`
- `0x180032ad0`
- `0x1800511b0`

## callees

- `0x180004c90`
- `0x180004f50`
- `0x180005218`
- `0x180009000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004d89`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004cc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d98`

## string_xrefs

- `0x180004db1`: `Process6to4ConfigurationChange`
- `0x180004daa`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180004cfc`: `Entered: Queueing worker for Process6to4ConfigurationChange`
- `0x180004d41`: `Leaving: Queued worker for Process6to4ConfigurationChange`
- `0x180004d5f`: `Leaving: Failed to queue worker for Process6to4ConfigurationChange`

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
0x180004c90  mov     [rsp+arg_0], rbx
0x180004c95  push    rdi
0x180004c96  sub     rsp, 20h
0x180004c9a  cmp     cs:g_StopServiceEventSet, 0
0x180004ca1  jnz     loc_180004DA4
0x180004ca7  cmp     cs:dword_1800C9754, 0
0x180004cae  jz      loc_180004DA4
0x180004cb4  xor     ebx, ebx
0x180004cb6  test    rdx, rdx
0x180004cb9  jz      short loc_180004CEA
0x180004cbb  xor     r9d, r9d; lpName
0x180004cbe  xor     r8d, r8d; bInitialState
0x180004cc1  xor     edx, edx; bManualReset
0x180004cc3  xor     ecx, ecx; lpEventAttributes
0x180004cc5  call    cs:__imp_CreateEventW
0x180004ccc  nop     dword ptr [rax+rax+00h]
0x180004cd1  mov     rbx, rax
0x180004cd4  test    rax, rax
0x180004cd7  jnz     short loc_180004CEA
0x180004cd9  call    cs:__imp_GetLastError
0x180004ce0  nop     dword ptr [rax+rax+00h]
0x180004ce5  jmp     loc_180004DA4
0x180004cea  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180004cf1  jz      short loc_180004D16
0x180004cf3  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x180004cfa  jge     short loc_180004D16
0x180004cfc  lea     r8, aEnteredQueuein; "Entered: Queueing worker for Process6to"...
0x180004d03  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180004d0a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180004d11  call    McTemplateU0z_EventWriteTransfer
0x180004d16  lea     r8, Process6to4ConfigurationHandler
0x180004d1d  mov     rdx, rbx
0x180004d20  mov     ecx, 0Ch
0x180004d25  call    QueueWorkItemForProtocolEvent
0x180004d2a  test    eax, eax
0x180004d2c  jnz     short loc_180004D4A
0x180004d2e  cmp     cs:IpHlpSvcEtwEnabled, al
0x180004d34  mov     dil, 1
0x180004d37  jz      short loc_180004D79
0x180004d39  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, al
0x180004d3f  jge     short loc_180004D79
0x180004d41  lea     r8, aLeavingQueuedW_0; "Leaving: Queued worker for Process6to4C"...
0x180004d48  jmp     short loc_180004D66
0x180004d4a  xor     dil, dil
0x180004d4d  cmp     cs:IpHlpSvcEtwEnabled, dil
0x180004d54  jz      short loc_180004D79
0x180004d56  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 80h
0x180004d5d  jz      short loc_180004D79
0x180004d5f  lea     r8, aLeavingFailedT_1; "Leaving: Failed to queue worker for Pro"...
0x180004d66  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x180004d6d  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180004d74  call    McTemplateU0z_EventWriteTransfer
0x180004d79  test    rbx, rbx
0x180004d7c  jz      short loc_180004DA4
0x180004d7e  test    dil, dil
0x180004d81  jz      short loc_180004D95
0x180004d83  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004d86  mov     rcx, rbx; hHandle
0x180004d89  call    cs:__imp_WaitForSingleObject
0x180004d90  nop     dword ptr [rax+rax+00h]
0x180004d95  mov     rcx, rbx; hObject
0x180004d98  call    cs:__imp_CloseHandle
0x180004d9f  nop     dword ptr [rax+rax+00h]
0x180004da4  mov     r8d, 3F7h
0x180004daa  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180004db1  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x180004db8  mov     rbx, [rsp+28h+arg_0]
0x180004dbd  add     rsp, 20h
0x180004dc1  pop     rdi
0x180004dc2  jmp     DereferenceServiceEx
```
