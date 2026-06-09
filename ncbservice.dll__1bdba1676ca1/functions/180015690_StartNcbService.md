# StartNcbService

- ea: `0x180015690`
- end: `0x18001591b`
- name: `StartNcbService`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180018300`

## callees

- `0x180009740`
- `0x18000a0a0`
- `0x180015690`
- `0x180015924`
- `0x1800159b8`
- `0x18001c0e4`
- `0x18001d8e0`
- `0x18001e368`
- `0x18001fce0`
- `0x180026a08`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015741`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800156f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001572f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800156f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001572f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015842`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001588a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800158c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001588a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800158c6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800158a9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800158a9`
- `WS2_32!__imp_WSAStartup` at `0x180015775`
- `WS2_32!__imp_WSAStartup` at `0x180015775`
- `WS2_32!__imp_WSACleanup` at `0x18001581f`
- `WS2_32!__imp_WSACleanup` at `0x18001581f`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStop` at `0x1800157b6`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStop` at `0x1800158d7`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStop` at `0x1800157b6`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStop` at `0x1800158d7`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStart` at `0x1800157ac`
- `ext-ms-win-networking-radiomonitor-l1-1-0!RadioDeviceStart` at `0x1800157ac`

## string_xrefs

- `0x1800157d1`: `NcbService`
- `0x1800156d5`: `StartNcbService: InitializeSocketBroker failed.`
- `0x18001571c`: `StartNcbService: Failed to create StopServiceEvent.`
- `0x180015756`: `StartNcbService: Failed to create StartServiceCompleteEvent.`
- `0x18001579e`: `StartNcbService: KAM failed to initialize`
- `0x180015872`: `StartNcbService: Failed WSAStartup`
- `0x18001580e`: `StartNcbService: Failed to register stop callback`
- `0x180015851`: `StartNcbService: Started successfully.`
- `0x1800158f4`: `StartNcbService: Failed to start service.`

## pseudocode

```c
__int64 StartNcbService()
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // ebx
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  DWORD v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  struct WSAData WSAData; // [rsp+40h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  v0 = InitializeSocketBroker();
  v3 = v0;
  if ( v0 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v2, v1, L"StartNcbService: InitializeSocketBroker failed.", v0);
    goto LABEL_27;
  }
  g_StopHandles = CreateEventW(0, 1, 0, 0);
  if ( !g_StopHandles )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v6, v5, L"StartNcbService: Failed to create StopServiceEvent.", LastError);
    goto LABEL_27;
  }
  hHandle = CreateEventW(0, 0, 0, 0);
  if ( !hHandle )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v9, v8, L"StartNcbService: Failed to create StartServiceCompleteEvent.", v7);
    goto LABEL_27;
  }
  SetNcbServiceStatus(2);
  if ( WSAStartup(2u, &WSAData) )
  {
    v3 = 1062;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v11, v10, L"StartNcbService: Failed WSAStartup");
    goto LABEL_27;
  }
  v12 = KamInitialize();
  v3 = v12;
  if ( v12 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v14, v13, L"StartNcbService: KAM failed to initialize", v12);
LABEL_21:
    WSACleanup();
LABEL_27:
    if ( g_StopHandles )
    {
      CloseHandle(g_StopHandles);
      g_StopHandles = 0;
    }
    if ( WaitHandle )
    {
      UnregisterWaitEx(WaitHandle, 0);
      WaitHandle = 0;
    }
    if ( hHandle )
    {
      CloseHandle(hHandle);
      hHandle = 0;
    }
    RadioDeviceStop();
    CleanupSocketBroker();
    g_ErrorCode = v3;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v22, v21, L"StartNcbService: Failed to start service.", v3);
    return v3;
  }
  if ( (int)RadioDeviceStart() < 0 )
    RadioDeviceStop();
  v15 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(g_NcbSvcHostGlobalData + 192))(
          &WaitHandle,
          L"NcbService",
          g_StopHandles,
          InitiateStopNcbService,
          0,
          24);
  v3 = v15;
  if ( v15 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v17, v16, L"StartNcbService: Failed to register stop callback", v15);
    KamUninitialize();
    goto LABEL_21;
  }
  g_ServiceStatus.dwControlsAccepted = 129;
  SetNcbServiceStatus(4);
  SetEvent(hHandle);
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v19, v18, L"StartNcbService: Started successfully.");
  return 0;
}

```

## disassembly

```asm
0x180015690  push    rbx
0x180015692  sub     rsp, 1F0h
0x180015699  mov     rax, cs:__security_cookie
0x1800156a0  xor     rax, rsp
0x1800156a3  mov     [rsp+1F8h+var_18], rax
0x1800156ab  xor     edx, edx; Val
0x1800156ad  lea     rcx, [rsp+1F8h+WSAData]; void *
0x1800156b2  mov     r8d, 198h; Size
0x1800156b8  call    memset_0
0x1800156bd  call    InitializeSocketBroker
0x1800156c2  mov     ebx, eax
0x1800156c4  test    eax, eax
0x1800156c6  jz      short loc_1800156E9
0x1800156c8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800156cf  jz      loc_18001587E
0x1800156d5  lea     r8, aStartncbservic; "StartNcbService: InitializeSocketBroker"...
0x1800156dc  mov     r9d, eax
0x1800156df  call    McTemplateU0zq_EventWriteTransfer
0x1800156e4  jmp     loc_18001587E
0x1800156e9  xor     r9d, r9d; lpName
0x1800156ec  xor     r8d, r8d; bInitialState
0x1800156ef  xor     ecx, ecx; lpEventAttributes
0x1800156f1  lea     edx, [r9+1]; bManualReset
0x1800156f5  call    cs:__imp_CreateEventW
0x1800156fb  mov     cs:g_StopHandles, rax
0x180015702  test    rax, rax
0x180015705  jnz     short loc_180015725
0x180015707  call    cs:__imp_GetLastError
0x18001570d  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180015714  mov     ebx, eax
0x180015716  jz      loc_18001587E
0x18001571c  lea     r8, aStartncbservic_1; "StartNcbService: Failed to create StopS"...
0x180015723  jmp     short loc_1800156DC
0x180015725  xor     r9d, r9d; lpName
0x180015728  xor     r8d, r8d; bInitialState
0x18001572b  xor     edx, edx; bManualReset
0x18001572d  xor     ecx, ecx; lpEventAttributes
0x18001572f  call    cs:__imp_CreateEventW
0x180015735  mov     cs:hHandle, rax
0x18001573c  test    rax, rax
0x18001573f  jnz     short loc_180015762
0x180015741  call    cs:__imp_GetLastError
0x180015747  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001574e  mov     ebx, eax
0x180015750  jz      loc_18001587E
0x180015756  lea     r8, aStartncbservic_3; "StartNcbService: Failed to create Start"...
0x18001575d  jmp     loc_1800156DC
0x180015762  xor     edx, edx
0x180015764  lea     ebx, [rdx+2]
0x180015767  mov     ecx, ebx
0x180015769  call    SetNcbServiceStatus
0x18001576e  mov     ecx, ebx; wVersionRequested
0x180015770  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x180015775  call    cs:__imp_WSAStartup
0x18001577b  test    eax, eax
0x18001577d  jnz     loc_180015864
0x180015783  call    KamInitialize
0x180015788  mov     ebx, eax
0x18001578a  test    eax, eax
0x18001578c  jz      short loc_1800157AC
0x18001578e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180015795  jz      loc_18001581F
0x18001579b  mov     r9d, eax
0x18001579e  lea     r8, aStartncbservic_4; "StartNcbService: KAM failed to initiali"...
0x1800157a5  call    McTemplateU0zq_EventWriteTransfer
0x1800157aa  jmp     short loc_18001581F
0x1800157ac  call    cs:__imp_RadioDeviceStart
0x1800157b2  test    eax, eax
0x1800157b4  jns     short loc_1800157BC
0x1800157b6  call    cs:__imp_RadioDeviceStop
0x1800157bc  mov     rax, cs:g_NcbSvcHostGlobalData
0x1800157c3  lea     r9, InitiateStopNcbService
0x1800157ca  mov     r8, cs:g_StopHandles
0x1800157d1  lea     rdx, ServiceName; "NcbService"
0x1800157d8  mov     [rsp+1F8h+var_1D0], 18h
0x1800157e0  lea     rcx, WaitHandle
0x1800157e7  mov     [rsp+1F8h+var_1D8], 0
0x1800157f0  mov     rax, [rax+0C0h]
0x1800157f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157fc  mov     ebx, eax
0x1800157fe  test    eax, eax
0x180015800  jz      short loc_180015827
0x180015802  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180015809  jz      short loc_18001581A
0x18001580b  mov     r9d, eax
0x18001580e  lea     r8, aStartncbservic_5; "StartNcbService: Failed to register sto"...
0x180015815  call    McTemplateU0zq_EventWriteTransfer
0x18001581a  call    KamUninitialize
0x18001581f  call    cs:__imp_WSACleanup
0x180015825  jmp     short loc_18001587E
0x180015827  xor     edx, edx
0x180015829  mov     cs:g_ServiceStatus.dwControlsAccepted, 81h
0x180015833  lea     ecx, [rdx+4]
0x180015836  call    SetNcbServiceStatus
0x18001583b  mov     rcx, cs:hHandle; hEvent
0x180015842  call    cs:__imp_SetEvent
0x180015848  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001584f  jz      short loc_18001585D
0x180015851  lea     r8, aStartncbservic_6; "StartNcbService: Started successfully."
0x180015858  call    McTemplateU0z_EventWriteTransfer
0x18001585d  xor     eax, eax
0x18001585f  jmp     loc_180015902
0x180015864  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001586b  mov     ebx, 426h
0x180015870  jz      short loc_18001587E
0x180015872  lea     r8, aStartncbservic_0; "StartNcbService: Failed WSAStartup"
0x180015879  call    McTemplateU0z_EventWriteTransfer
0x18001587e  mov     rcx, cs:g_StopHandles; hObject
0x180015885  test    rcx, rcx
0x180015888  jz      short loc_18001589B
0x18001588a  call    cs:__imp_CloseHandle
0x180015890  mov     cs:g_StopHandles, 0
0x18001589b  mov     rcx, cs:WaitHandle; WaitHandle
0x1800158a2  test    rcx, rcx
0x1800158a5  jz      short loc_1800158BA
0x1800158a7  xor     edx, edx; CompletionEvent
0x1800158a9  call    cs:__imp_UnregisterWaitEx
0x1800158af  mov     cs:WaitHandle, 0
0x1800158ba  mov     rcx, cs:hHandle; hObject
0x1800158c1  test    rcx, rcx
0x1800158c4  jz      short loc_1800158D7
0x1800158c6  call    cs:__imp_CloseHandle
0x1800158cc  mov     cs:hHandle, 0
0x1800158d7  call    cs:__imp_RadioDeviceStop
0x1800158dd  call    CleanupSocketBroker
0x1800158e2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800158e9  mov     cs:g_ErrorCode, ebx
0x1800158ef  jz      short loc_180015900
0x1800158f1  mov     r9d, ebx
0x1800158f4  lea     r8, aStartncbservic_2; "StartNcbService: Failed to start servic"...
0x1800158fb  call    McTemplateU0zq_EventWriteTransfer
0x180015900  mov     eax, ebx
0x180015902  mov     rcx, [rsp+1F8h+var_18]
0x18001590a  xor     rcx, rsp; StackCookie
0x18001590d  call    __security_check_cookie
0x180015912  add     rsp, 1F0h
0x180015919  pop     rbx
0x18001591a  retn
```
