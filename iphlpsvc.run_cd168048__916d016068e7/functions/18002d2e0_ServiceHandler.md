# ServiceHandler

- ea: `0x18002d2e0`
- end: `0x18002d684`
- name: `ServiceHandler`
- size: `932`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004f50`
- `0x180009000`
- `0x18000d7b0`
- `0x1800159c4`
- `0x18002d2e0`
- `0x18002d68c`
- `0x18002d7b8`
- `0x18002d82c`
- `0x18003b300`
- `0x18003e154`
- `0x1800530ec`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d505`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d601`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d505`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d601`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d434`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d461`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d434`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d610`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d610`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d4d9`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d5d5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d4d9`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d5d5`

## string_xrefs

- `0x18002d410`: `ServiceHandler: Got a SERVICE_CONTROL_INTERROGATE control`
- `0x18002d440`: `onecoreuap\net\netio\iphlpsvc\service\svcmain.c`
- `0x18002d48f`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18002d58f`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18002d628`: `ServiceHandler: Got a SERVICE_CONTROL_STOP control`
- `0x18002d56d`: `ServiceHandler: Got a SERVICE_CONTROL_SHUTDOWN control`
- `0x18002d557`: `ServiceHandler: Got a SERVICE_CONTROL_PARAMCHANGE control`
- `0x18002d546`: `ServiceHandler: Got unknown control code %d.`

## pseudocode

```c
__int64 __fastcall ServiceHandler(__int64 dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v5; // edi
  unsigned int v6; // ebx
  HANDLE v8; // r14
  HANDLE v9; // rbp
  __int64 v10; // [rsp+28h] [rbp-30h]

  v5 = dwEventType;
  v6 = dwControl;
  switch ( (_DWORD)dwControl )
  {
    case 0xE:
      if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
          L"Entered: OnSessionChange");
      if ( v5 == 5 )
        JUMPOUT(0x18002D651LL);
      _InterlockedExchange(&g_DaSiteMgrIsUserActive, DaSiteMgrDoesActiveWTSSessionExist(dwControl));
      if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
        McTemplateU0z_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
          L"Leaving: OnSessionChange");
      goto LABEL_12;
    case 0xD:
      switch ( (_DWORD)dwEventType )
      {
        case 4:
          OnPowerSuspend(dwControl, dwEventType, lpEventData, lpContext);
          break;
        case 0x12:
          OnPowerResume(dwControl, dwEventType, lpEventData, lpContext);
          break;
        case 0x8013:
          OnPowerSettingChange(dwControl, dwEventType, lpEventData, lpContext);
          break;
      }
      goto LABEL_12;
    case 1:
      SetStopServiceEvent(0);
      EventWrite0(0x40000, L"ServiceHandler: Got a SERVICE_CONTROL_STOP control");
      goto LABEL_12;
  }
  if ( (_DWORD)dwControl != 4 )
  {
    if ( (_DWORD)dwControl == 5 )
    {
      EventWrite0(0x40000, L"ServiceHandler: Got a SERVICE_CONTROL_SHUTDOWN control", lpEventData, lpContext);
    }
    else if ( (_DWORD)dwControl == 6 )
    {
      EventWrite0(0x40000, L"ServiceHandler: Got a SERVICE_CONTROL_PARAMCHANGE control", lpEventData, lpContext);
      OnConfigChange();
    }
    else
    {
      EventWrite0(0x40000, L"ServiceHandler: Got unknown control code %d.", (unsigned int)dwControl, lpContext);
    }
    goto LABEL_12;
  }
  EventWrite0(0x40000, L"ServiceHandler: Got a SERVICE_CONTROL_INTERROGATE control", lpEventData, lpContext);
  v8 = OpenEventW(2u, 1, L"Global\\TeredoQueryStateEvent");
  if ( v8 )
  {
    EventWrite0(
      0x40000,
      L"ReferenceService: ++%u (%hs) @ %ls:%u",
      ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
      "TeredoQueryGlobals",
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\svcmain.c",
      466);
    if ( (unsigned __int8)RoReferenceEx(&g_Reference) )
    {
      if ( TrySubmitThreadpoolCallback(TeredoQueryGlobals, v8, &CallbackEnvironment) )
        goto LABEL_22;
      DereferenceServiceEx("TeredoQueryGlobals", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\svcmain.c", 468);
    }
    SetEvent(v8);
    CloseHandle(v8);
  }
LABEL_22:
  v9 = OpenEventW(2u, 1, L"Global\\IpTlsQueryStateEvent");
  if ( v9 )
  {
    LODWORD(v10) = 490;
    EventWrite0(
      0x40000,
      L"ReferenceService: ++%u (%hs) @ %ls:%u",
      ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
      "IpTlsQueryGlobals",
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\svcmain.c",
      v10);
    if ( (unsigned __int8)RoReferenceEx(&g_Reference) )
    {
      if ( !TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)IpTlsQueryGlobals, v9, &CallbackEnvironment) )
      {
        DereferenceServiceEx("IpTlsQueryGlobals", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\svcmain.c", 492);
        SetEvent(v9);
        CloseHandle(v9);
      }
    }
  }
LABEL_12:
  if ( dword_1800C8578 )
    ((void (__fastcall *)(_QWORD, _QWORD, LPVOID))qword_1800C8560)(v6, v5, lpEventData);
  if ( dword_1800C85C0 )
    ((void (__fastcall *)(_QWORD, _QWORD, LPVOID))qword_1800C85A8)(v6, v5, lpEventData);
  return 0;
}

```

## disassembly

```asm
0x18002d2e0  push    rbx
0x18002d2e2  push    rsi
0x18002d2e3  push    rdi
0x18002d2e4  sub     rsp, 40h
0x18002d2e8  mov     [rsp+58h+arg_18], rbp
0x18002d2ed  mov     rsi, r8
0x18002d2f0  mov     [rsp+58h+var_28], r15
0x18002d2f5  mov     edi, edx
0x18002d2f7  mov     ebx, ecx
0x18002d2f9  cmp     ecx, 0Eh
0x18002d2fc  jnz     short loc_18002D352
0x18002d2fe  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18002d305  jnz     loc_18002D3CB
0x18002d30b  lea     eax, [rdi-1]; switch 9 cases
0x18002d30e  cmp     eax, 8
0x18002d311  jbe     loc_18002D63E
0x18002d317  call    DaSiteMgrDoesActiveWTSSessionExist; jumptable 000000018002D64F default case, cases 1-4,6-9
0x18002d31c  mov     ebp, eax
0x18002d31e  xchg    ebp, cs:g_DaSiteMgrIsUserActive
0x18002d324  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18002d32b  jz      short loc_18002D37A
0x18002d32d  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x18002d334  jge     short loc_18002D37A
0x18002d336  lea     r8, aLeavingOnsessi; "Leaving: OnSessionChange"
0x18002d33d  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18002d344  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002d34b  call    McTemplateU0z_EventWriteTransfer
0x18002d350  jmp     short loc_18002D37A
0x18002d352  cmp     ebx, 0Dh
0x18002d355  jnz     loc_18002D3F7
0x18002d35b  cmp     edi, 4
0x18002d35e  jz      loc_18002D52F
0x18002d364  cmp     edi, 12h
0x18002d367  jz      loc_18002D525
0x18002d36d  cmp     edi, 8013h
0x18002d373  jnz     short loc_18002D37A
0x18002d375  call    OnPowerSettingChange
0x18002d37a  cmp     cs:dword_1800C8578, 0
0x18002d381  mov     r15, [rsp+58h+var_28]
0x18002d386  mov     rbp, [rsp+58h+arg_18]
0x18002d38b  jnz     short loc_18002D3A1
0x18002d38d  cmp     cs:dword_1800C85C0, 0
0x18002d394  jnz     short loc_18002D3B6
0x18002d396  xor     eax, eax
0x18002d398  add     rsp, 40h
0x18002d39c  pop     rdi
0x18002d39d  pop     rsi
0x18002d39e  pop     rbx
0x18002d39f  retn
0x18002d3a1  mov     rax, cs:qword_1800C8560
0x18002d3a8  mov     r8, rsi
0x18002d3ab  mov     edx, edi
0x18002d3ad  mov     ecx, ebx
0x18002d3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3b4  jmp     short loc_18002D38D
0x18002d3b6  mov     rax, cs:qword_1800C85A8
0x18002d3bd  mov     r8, rsi
0x18002d3c0  mov     edx, edi
0x18002d3c2  mov     ecx, ebx
0x18002d3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3c9  jmp     short loc_18002D396
0x18002d3cb  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x18002d3d2  jge     loc_18002D30B
0x18002d3d8  lea     r8, aEnteredOnsessi; "Entered: OnSessionChange"
0x18002d3df  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18002d3e6  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002d3ed  call    McTemplateU0z_EventWriteTransfer
0x18002d3f2  jmp     loc_18002D30B
0x18002d3f7  mov     eax, ebx
0x18002d3f9  sub     eax, 1
0x18002d3fc  jz      loc_18002D621
0x18002d402  mov     ecx, 40000h
0x18002d407  sub     eax, 3
0x18002d40a  jnz     loc_18002D539
0x18002d410  lea     rdx, aServicehandler; "ServiceHandler: Got a SERVICE_CONTROL_I"...
0x18002d417  mov     [rsp+58h+var_20], r14
0x18002d41c  call    EventWrite0
0x18002d421  mov     ebp, 1
0x18002d426  lea     r8, Name; "Global\\TeredoQueryStateEvent"
0x18002d42d  mov     edx, ebp; bInheritHandle
0x18002d42f  mov     ecx, 2; dwDesiredAccess
0x18002d434  call    cs:__imp_OpenEventW
0x18002d43b  nop     dword ptr [rax+rax+00h]
0x18002d440  lea     r15, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002d447  mov     r14, rax
0x18002d44a  test    rax, rax
0x18002d44d  jnz     loc_18002D57E
0x18002d453  lea     r8, aGlobalIptlsque; "Global\\IpTlsQueryStateEvent"
0x18002d45a  mov     edx, ebp; bInheritHandle
0x18002d45c  mov     ecx, 2; dwDesiredAccess
0x18002d461  call    cs:__imp_OpenEventW
0x18002d468  nop     dword ptr [rax+rax+00h]
0x18002d46d  mov     r14, [rsp+58h+var_20]
0x18002d472  mov     rbp, rax
0x18002d475  test    rax, rax
0x18002d478  jz      loc_18002D37A
0x18002d47e  mov     r8d, cs:g_Reference
0x18002d485  lea     r9, aIptlsqueryglob; "IpTlsQueryGlobals"
0x18002d48c  shr     r8d, 1
0x18002d48f  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18002d496  and     r8d, 3FFFFFFFh
0x18002d49d  mov     dword ptr [rsp+58h+var_30], 1EAh
0x18002d4a5  mov     ecx, 40000h
0x18002d4aa  mov     [rsp+58h+var_38], r15
0x18002d4af  call    EventWrite0
0x18002d4b4  lea     rcx, g_Reference
0x18002d4bb  call    RoReferenceEx
0x18002d4c0  test    al, al
0x18002d4c2  jz      loc_18002D37A
0x18002d4c8  lea     r8, CallbackEnvironment; pcbe
0x18002d4cf  mov     rdx, rbp; pv
0x18002d4d2  lea     rcx, IpTlsQueryGlobals; pfns
0x18002d4d9  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002d4e0  nop     dword ptr [rax+rax+00h]
0x18002d4e5  test    eax, eax
0x18002d4e7  jnz     loc_18002D37A
0x18002d4ed  mov     r8d, 1ECh
0x18002d4f3  lea     rcx, aIptlsqueryglob; "IpTlsQueryGlobals"
0x18002d4fa  mov     rdx, r15
0x18002d4fd  call    DereferenceServiceEx
0x18002d502  mov     rcx, rbp; hEvent
0x18002d505  call    cs:__imp_SetEvent
0x18002d50c  nop     dword ptr [rax+rax+00h]
0x18002d511  mov     rcx, rbp; hObject
0x18002d514  call    cs:__imp_CloseHandle
0x18002d51b  nop     dword ptr [rax+rax+00h]
0x18002d520  jmp     loc_18002D37A
0x18002d525  call    OnPowerResume
0x18002d52a  jmp     loc_18002D37A
0x18002d52f  call    OnPowerSuspend
0x18002d534  jmp     loc_18002D37A
0x18002d539  sub     eax, 1
0x18002d53c  jz      short loc_18002D56D
0x18002d53e  cmp     eax, 1
0x18002d541  jz      short loc_18002D557
0x18002d543  mov     r8d, ebx
0x18002d546  lea     rdx, aServicehandler_3; "ServiceHandler: Got unknown control cod"...
0x18002d54d  call    EventWrite0
0x18002d552  jmp     loc_18002D37A
0x18002d557  lea     rdx, aServicehandler_1; "ServiceHandler: Got a SERVICE_CONTROL_P"...
0x18002d55e  call    EventWrite0
0x18002d563  call    OnConfigChange
0x18002d568  jmp     loc_18002D37A
0x18002d56d  lea     rdx, aServicehandler_2; "ServiceHandler: Got a SERVICE_CONTROL_S"...
0x18002d574  call    EventWrite0
0x18002d579  jmp     loc_18002D37A
0x18002d57e  mov     r8d, cs:g_Reference
0x18002d585  lea     r9, aTeredoqueryglo; "TeredoQueryGlobals"
0x18002d58c  shr     r8d, 1
0x18002d58f  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18002d596  and     r8d, 3FFFFFFFh
0x18002d59d  mov     dword ptr [rsp+58h+var_30], 1D2h
0x18002d5a5  mov     ecx, 40000h
0x18002d5aa  mov     [rsp+58h+var_38], r15
0x18002d5af  call    EventWrite0
0x18002d5b4  lea     rcx, g_Reference
0x18002d5bb  call    RoReferenceEx
0x18002d5c0  test    al, al
0x18002d5c2  jz      short loc_18002D5FE
0x18002d5c4  lea     r8, CallbackEnvironment; pcbe
0x18002d5cb  mov     rdx, r14; pv
0x18002d5ce  lea     rcx, TeredoQueryGlobals; pfns
0x18002d5d5  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002d5dc  nop     dword ptr [rax+rax+00h]
0x18002d5e1  test    eax, eax
0x18002d5e3  jnz     loc_18002D453
0x18002d5e9  mov     r8d, 1D4h
0x18002d5ef  lea     rcx, aTeredoqueryglo; "TeredoQueryGlobals"
0x18002d5f6  mov     rdx, r15
0x18002d5f9  call    DereferenceServiceEx
0x18002d5fe  mov     rcx, r14; hEvent
0x18002d601  call    cs:__imp_SetEvent
0x18002d608  nop     dword ptr [rax+rax+00h]
0x18002d60d  mov     rcx, r14; hObject
0x18002d610  call    cs:__imp_CloseHandle
0x18002d617  nop     dword ptr [rax+rax+00h]
0x18002d61c  jmp     loc_18002D453
0x18002d621  xor     ecx, ecx
0x18002d623  call    SetStopServiceEvent
0x18002d628  lea     rdx, aServicehandler_0; "ServiceHandler: Got a SERVICE_CONTROL_S"...
0x18002d62f  mov     ecx, 40000h
0x18002d634  call    EventWrite0
0x18002d639  jmp     loc_18002D37A
0x18002d63e  lea     rcx, __ImageBase
0x18002d645  mov     eax, ds:(jpt_18002D64F - 180000000h)[rcx+rax*4]
0x18002d64c  add     rax, rcx
0x18002d64f  jmp     rax; switch jump
0x18002d655  mov     ebp, 1; jumptable 000000018002D64F case 5
0x18002d65a  jmp     loc_18002D31E
```
