# ServiceHandler

- ea: `0x18002d2f0`
- end: `0x18002d694`
- name: `ServiceHandler`
- size: `932`
- prototype: `__int64 __fastcall(__int64 dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004f60`
- `0x180009010`
- `0x18000d7c0`
- `0x1800159d4`
- `0x18002d2f0`
- `0x18002d69c`
- `0x18002d7c8`
- `0x18002d83c`
- `0x18003b310`
- `0x18003e110`
- `0x1800530ac`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d515`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d611`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d515`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d611`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d444`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d471`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d444`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002d471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d524`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d620`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d524`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d620`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d4e9`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d5e5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d4e9`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002d5e5`

## string_xrefs

- `0x18002d420`: `ServiceHandler: Got a SERVICE_CONTROL_INTERROGATE control`
- `0x18002d450`: `onecoreuap\net\netio\iphlpsvc\service\svcmain.c`
- `0x18002d49f`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18002d59f`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18002d638`: `ServiceHandler: Got a SERVICE_CONTROL_STOP control`
- `0x18002d57d`: `ServiceHandler: Got a SERVICE_CONTROL_SHUTDOWN control`
- `0x18002d567`: `ServiceHandler: Got a SERVICE_CONTROL_PARAMCHANGE control`
- `0x18002d556`: `ServiceHandler: Got unknown control code %d.`

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
        JUMPOUT(0x18002D661LL);
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
      SetStopServiceEvent(0, dwEventType, lpEventData, lpContext);
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
      if ( TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)TeredoQueryGlobals, v8, &CallbackEnvironment) )
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
0x18002d2f0  push    rbx
0x18002d2f2  push    rsi
0x18002d2f3  push    rdi
0x18002d2f4  sub     rsp, 40h
0x18002d2f8  mov     [rsp+58h+arg_18], rbp
0x18002d2fd  mov     rsi, r8
0x18002d300  mov     [rsp+58h+var_28], r15
0x18002d305  mov     edi, edx
0x18002d307  mov     ebx, ecx
0x18002d309  cmp     ecx, 0Eh
0x18002d30c  jnz     short loc_18002D362
0x18002d30e  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18002d315  jnz     loc_18002D3DB
0x18002d31b  lea     eax, [rdi-1]; switch 9 cases
0x18002d31e  cmp     eax, 8
0x18002d321  jbe     loc_18002D64E
0x18002d327  call    DaSiteMgrDoesActiveWTSSessionExist; jumptable 000000018002D65F default case, cases 1-4,6-9
0x18002d32c  mov     ebp, eax
0x18002d32e  xchg    ebp, cs:g_DaSiteMgrIsUserActive
0x18002d334  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18002d33b  jz      short loc_18002D38A
0x18002d33d  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x18002d344  jge     short loc_18002D38A
0x18002d346  lea     r8, aLeavingOnsessi; "Leaving: OnSessionChange"
0x18002d34d  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18002d354  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002d35b  call    McTemplateU0z_EventWriteTransfer
0x18002d360  jmp     short loc_18002D38A
0x18002d362  cmp     ebx, 0Dh
0x18002d365  jnz     loc_18002D407
0x18002d36b  cmp     edi, 4
0x18002d36e  jz      loc_18002D53F
0x18002d374  cmp     edi, 12h
0x18002d377  jz      loc_18002D535
0x18002d37d  cmp     edi, 8013h
0x18002d383  jnz     short loc_18002D38A
0x18002d385  call    OnPowerSettingChange
0x18002d38a  cmp     cs:dword_1800C8578, 0
0x18002d391  mov     r15, [rsp+58h+var_28]
0x18002d396  mov     rbp, [rsp+58h+arg_18]
0x18002d39b  jnz     short loc_18002D3B1
0x18002d39d  cmp     cs:dword_1800C85C0, 0
0x18002d3a4  jnz     short loc_18002D3C6
0x18002d3a6  xor     eax, eax
0x18002d3a8  add     rsp, 40h
0x18002d3ac  pop     rdi
0x18002d3ad  pop     rsi
0x18002d3ae  pop     rbx
0x18002d3af  retn
0x18002d3b1  mov     rax, cs:qword_1800C8560
0x18002d3b8  mov     r8, rsi
0x18002d3bb  mov     edx, edi
0x18002d3bd  mov     ecx, ebx
0x18002d3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3c4  jmp     short loc_18002D39D
0x18002d3c6  mov     rax, cs:qword_1800C85A8
0x18002d3cd  mov     r8, rsi
0x18002d3d0  mov     edx, edi
0x18002d3d2  mov     ecx, ebx
0x18002d3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3d9  jmp     short loc_18002D3A6
0x18002d3db  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x18002d3e2  jge     loc_18002D31B
0x18002d3e8  lea     r8, aEnteredOnsessi; "Entered: OnSessionChange"
0x18002d3ef  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18002d3f6  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002d3fd  call    McTemplateU0z_EventWriteTransfer
0x18002d402  jmp     loc_18002D31B
0x18002d407  mov     eax, ebx
0x18002d409  sub     eax, 1
0x18002d40c  jz      loc_18002D631
0x18002d412  mov     ecx, 40000h
0x18002d417  sub     eax, 3
0x18002d41a  jnz     loc_18002D549
0x18002d420  lea     rdx, aServicehandler; "ServiceHandler: Got a SERVICE_CONTROL_I"...
0x18002d427  mov     [rsp+58h+var_20], r14
0x18002d42c  call    EventWrite0
0x18002d431  mov     ebp, 1
0x18002d436  lea     r8, Name; "Global\\TeredoQueryStateEvent"
0x18002d43d  mov     edx, ebp; bInheritHandle
0x18002d43f  mov     ecx, 2; dwDesiredAccess
0x18002d444  call    cs:__imp_OpenEventW
0x18002d44b  nop     dword ptr [rax+rax+00h]
0x18002d450  lea     r15, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002d457  mov     r14, rax
0x18002d45a  test    rax, rax
0x18002d45d  jnz     loc_18002D58E
0x18002d463  lea     r8, aGlobalIptlsque; "Global\\IpTlsQueryStateEvent"
0x18002d46a  mov     edx, ebp; bInheritHandle
0x18002d46c  mov     ecx, 2; dwDesiredAccess
0x18002d471  call    cs:__imp_OpenEventW
0x18002d478  nop     dword ptr [rax+rax+00h]
0x18002d47d  mov     r14, [rsp+58h+var_20]
0x18002d482  mov     rbp, rax
0x18002d485  test    rax, rax
0x18002d488  jz      loc_18002D38A
0x18002d48e  mov     r8d, cs:g_Reference
0x18002d495  lea     r9, aIptlsqueryglob; "IpTlsQueryGlobals"
0x18002d49c  shr     r8d, 1
0x18002d49f  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18002d4a6  and     r8d, 3FFFFFFFh
0x18002d4ad  mov     dword ptr [rsp+58h+var_30], 1EAh
0x18002d4b5  mov     ecx, 40000h
0x18002d4ba  mov     [rsp+58h+var_38], r15
0x18002d4bf  call    EventWrite0
0x18002d4c4  lea     rcx, g_Reference
0x18002d4cb  call    RoReferenceEx
0x18002d4d0  test    al, al
0x18002d4d2  jz      loc_18002D38A
0x18002d4d8  lea     r8, CallbackEnvironment; pcbe
0x18002d4df  mov     rdx, rbp; pv
0x18002d4e2  lea     rcx, IpTlsQueryGlobals; pfns
0x18002d4e9  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002d4f0  nop     dword ptr [rax+rax+00h]
0x18002d4f5  test    eax, eax
0x18002d4f7  jnz     loc_18002D38A
0x18002d4fd  mov     r8d, 1ECh
0x18002d503  lea     rcx, aIptlsqueryglob; "IpTlsQueryGlobals"
0x18002d50a  mov     rdx, r15
0x18002d50d  call    DereferenceServiceEx
0x18002d512  mov     rcx, rbp; hEvent
0x18002d515  call    cs:__imp_SetEvent
0x18002d51c  nop     dword ptr [rax+rax+00h]
0x18002d521  mov     rcx, rbp; hObject
0x18002d524  call    cs:__imp_CloseHandle
0x18002d52b  nop     dword ptr [rax+rax+00h]
0x18002d530  jmp     loc_18002D38A
0x18002d535  call    OnPowerResume
0x18002d53a  jmp     loc_18002D38A
0x18002d53f  call    OnPowerSuspend
0x18002d544  jmp     loc_18002D38A
0x18002d549  sub     eax, 1
0x18002d54c  jz      short loc_18002D57D
0x18002d54e  cmp     eax, 1
0x18002d551  jz      short loc_18002D567
0x18002d553  mov     r8d, ebx
0x18002d556  lea     rdx, aServicehandler_3; "ServiceHandler: Got unknown control cod"...
0x18002d55d  call    EventWrite0
0x18002d562  jmp     loc_18002D38A
0x18002d567  lea     rdx, aServicehandler_1; "ServiceHandler: Got a SERVICE_CONTROL_P"...
0x18002d56e  call    EventWrite0
0x18002d573  call    OnConfigChange
0x18002d578  jmp     loc_18002D38A
0x18002d57d  lea     rdx, aServicehandler_2; "ServiceHandler: Got a SERVICE_CONTROL_S"...
0x18002d584  call    EventWrite0
0x18002d589  jmp     loc_18002D38A
0x18002d58e  mov     r8d, cs:g_Reference
0x18002d595  lea     r9, aTeredoqueryglo; "TeredoQueryGlobals"
0x18002d59c  shr     r8d, 1
0x18002d59f  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18002d5a6  and     r8d, 3FFFFFFFh
0x18002d5ad  mov     dword ptr [rsp+58h+var_30], 1D2h
0x18002d5b5  mov     ecx, 40000h
0x18002d5ba  mov     [rsp+58h+var_38], r15
0x18002d5bf  call    EventWrite0
0x18002d5c4  lea     rcx, g_Reference
0x18002d5cb  call    RoReferenceEx
0x18002d5d0  test    al, al
0x18002d5d2  jz      short loc_18002D60E
0x18002d5d4  lea     r8, CallbackEnvironment; pcbe
0x18002d5db  mov     rdx, r14; pv
0x18002d5de  lea     rcx, TeredoQueryGlobals; pfns
0x18002d5e5  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002d5ec  nop     dword ptr [rax+rax+00h]
0x18002d5f1  test    eax, eax
0x18002d5f3  jnz     loc_18002D463
0x18002d5f9  mov     r8d, 1D4h
0x18002d5ff  lea     rcx, aTeredoqueryglo; "TeredoQueryGlobals"
0x18002d606  mov     rdx, r15
0x18002d609  call    DereferenceServiceEx
0x18002d60e  mov     rcx, r14; hEvent
0x18002d611  call    cs:__imp_SetEvent
0x18002d618  nop     dword ptr [rax+rax+00h]
0x18002d61d  mov     rcx, r14; hObject
0x18002d620  call    cs:__imp_CloseHandle
0x18002d627  nop     dword ptr [rax+rax+00h]
0x18002d62c  jmp     loc_18002D463
0x18002d631  xor     ecx, ecx
0x18002d633  call    SetStopServiceEvent
0x18002d638  lea     rdx, aServicehandler_0; "ServiceHandler: Got a SERVICE_CONTROL_S"...
0x18002d63f  mov     ecx, 40000h
0x18002d644  call    EventWrite0
0x18002d649  jmp     loc_18002D38A
0x18002d64e  lea     rcx, __ImageBase
0x18002d655  mov     eax, ds:(jpt_18002D65F - 180000000h)[rcx+rax*4]
0x18002d65c  add     rax, rcx
0x18002d65f  jmp     rax; switch jump
0x18002d665  mov     ebp, 1; jumptable 000000018002D65F case 5
0x18002d66a  jmp     loc_18002D32E
```
