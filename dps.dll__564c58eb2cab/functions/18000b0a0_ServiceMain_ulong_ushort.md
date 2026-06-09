# ServiceMain(ulong,ushort * *)

- ea: `0x18000b0a0`
- end: `0x18000b2a9`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `521`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001768`
- `0x180001e88`
- `0x180006188`
- `0x1800072cc`
- `0x180009090`
- `0x18000b0a0`
- `0x18000f774`
- `0x18000f940`
- `0x180011274`
- `0x180017840`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b205`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b205`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000b284`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000b284`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b16f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b16f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b266`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b266`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b0e2`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b0e2`

## string_xrefs

- `0x18000b117`: `ServiceMain`
- `0x18000b24a`: `ServiceMain`

## pseudocode

```c
void __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  unsigned __int16 v2; // bx
  int Args; // eax
  int v4; // eax
  HRESULT v5; // eax
  int SetupInformation; // eax
  int v7; // r8d

  v2 = 0;
  g_sSvcStatus.dwServiceType = 32;
  *(_QWORD *)&g_sSvcStatus.dwCheckPoint = 0;
  *(_OWORD *)&g_sSvcStatus.dwCurrentState = 0;
  g_fControl = 0;
  if ( a1 )
  {
    hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, DpspSvcHandlerEx, 0);
    if ( hServiceStatus )
    {
      Args = WdipETWRegister();
      v2 = Args;
      if ( Args < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dps.cpp",
          (int)L"ServiceMain",
          264,
          (int)L"Error = %d",
          Args);
        goto LABEL_25;
      }
      v4 = DpsNotifySvc(3, 2, 1, 0, 0);
      v2 = v4;
      if ( v4 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dps.cpp",
          (int)L"ServiceMain",
          273,
          (int)L"Error = %d",
          v4);
        goto LABEL_25;
      }
      DpspRaisePerformanceEvent(&WDI_DPS_EVENT_BOOT_PERF_START);
      v5 = CoInitializeEx(0, 0);
      v2 = v5;
      if ( v5 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dps.cpp",
          (int)L"ServiceMain",
          279,
          (int)L"Error = %d",
          v5);
        goto LABEL_25;
      }
      SetupInformation = DpspInitializeCriticalSections();
      v2 = SetupInformation;
      if ( SetupInformation >= 0 )
      {
        SetupInformation = DpspLoadSetupInformation();
        v2 = SetupInformation;
        if ( SetupInformation >= 0 )
        {
          SetupInformation = DpsNotifySvc(3, 2, 2, 0, 0);
          v2 = SetupInformation;
          if ( SetupInformation >= 0 )
          {
            SetupInformation = DpspLaunchCommunicationServer();
            v2 = SetupInformation;
            if ( SetupInformation >= 0 )
            {
              DpsRun();
              _InterlockedOr(&g_fControl, 1u);
              while ( (g_fControl & 2) != 0 )
                Sleep(0x64u);
              SetupInformation = DpsNotifySvc(15, 3, 1, 5000, 0);
              v2 = SetupInformation;
              if ( SetupInformation >= 0 )
                goto LABEL_24;
              v7 = 320;
            }
            else
            {
              v7 = 299;
            }
          }
          else
          {
            v7 = 296;
          }
        }
        else
        {
          v7 = 287;
        }
      }
      else
      {
        v7 = 284;
      }
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dps.cpp",
        (int)L"ServiceMain",
        v7,
        (int)L"Error = %d",
        SetupInformation);
LABEL_24:
      DpspFreeStateInformation();
      CoUninitialize();
    }
  }
LABEL_25:
  DpspRaisePerformanceEvent(&WDI_DPS_EVENT_SHUTDOWN_PERF_END);
  if ( g_hETW )
    EventUnregister(g_hETW);
  DpsNotifySvc(9, 1, 0, 0, v2);
}

```

## disassembly

```asm
0x18000b0a0  push    rbx
0x18000b0a2  sub     rsp, 30h
0x18000b0a6  xor     ebx, ebx
0x18000b0a8  mov     cs:g_sSvcStatus.dwServiceType, 20h ; ' '
0x18000b0b2  mov     qword ptr cs:g_sSvcStatus.dwCheckPoint, rbx
0x18000b0b9  xorps   xmm0, xmm0
0x18000b0bc  mov     rax, rdx
0x18000b0bf  movdqu  xmmword ptr cs:g_sSvcStatus.dwCurrentState, xmm0
0x18000b0c7  mov     cs:g_fControl, ebx
0x18000b0cd  test    ecx, ecx
0x18000b0cf  jz      loc_18000B26C
0x18000b0d5  mov     rcx, [rax]; lpServiceName
0x18000b0d8  lea     rdx, ?DpspSvcHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x18000b0df  xor     r8d, r8d; lpContext
0x18000b0e2  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000b0e8  mov     cs:hServiceStatus, rax
0x18000b0ef  test    rax, rax
0x18000b0f2  jz      loc_18000B26C
0x18000b0f8  call    WdipETWRegister
0x18000b0fd  mov     ebx, eax
0x18000b0ff  test    eax, eax
0x18000b101  jns     short loc_18000B12F
0x18000b103  movzx   ecx, ax
0x18000b106  mov     r8d, 108h; int
0x18000b10c  mov     dword ptr [rsp+38h+Args], ecx; Args
0x18000b110  lea     r9, aErrorD; "Error = %d"
0x18000b117  lea     rdx, aServicemain_0; "ServiceMain"
0x18000b11e  lea     rcx, aClientcoreBase_3; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b125  call    WdipTraceError
0x18000b12a  jmp     loc_18000B26C
0x18000b12f  xor     r9d, r9d
0x18000b132  mov     dword ptr [rsp+38h+Args], 0
0x18000b13a  lea     edx, [r9+2]
0x18000b13e  lea     ecx, [rdx+1]
0x18000b141  lea     r8d, [r9+1]
0x18000b145  call    DpsNotifySvc
0x18000b14a  mov     ebx, eax
0x18000b14c  test    eax, eax
0x18000b14e  jns     short loc_18000B15F
0x18000b150  movzx   eax, ax
0x18000b153  mov     r8d, 111h
0x18000b159  mov     dword ptr [rsp+38h+Args], eax
0x18000b15d  jmp     short loc_18000B110
0x18000b15f  lea     rcx, WDI_DPS_EVENT_BOOT_PERF_START; EventDescriptor
0x18000b166  call    DpspRaisePerformanceEvent
0x18000b16b  xor     edx, edx; dwCoInit
0x18000b16d  xor     ecx, ecx; pvReserved
0x18000b16f  call    cs:__imp_CoInitializeEx
0x18000b175  mov     ebx, eax
0x18000b177  test    eax, eax
0x18000b179  jns     short loc_18000B18A
0x18000b17b  movzx   eax, ax
0x18000b17e  mov     r8d, 117h
0x18000b184  mov     dword ptr [rsp+38h+Args], eax
0x18000b188  jmp     short loc_18000B110
0x18000b18a  call    DpspInitializeCriticalSections
0x18000b18f  mov     ebx, eax
0x18000b191  test    eax, eax
0x18000b193  jns     short loc_18000B1A0
0x18000b195  mov     r8d, 11Ch
0x18000b19b  jmp     loc_18000B240
0x18000b1a0  call    DpspLoadSetupInformation
0x18000b1a5  mov     ebx, eax
0x18000b1a7  test    eax, eax
0x18000b1a9  jns     short loc_18000B1B6
0x18000b1ab  mov     r8d, 11Fh
0x18000b1b1  jmp     loc_18000B240
0x18000b1b6  xor     r9d, r9d
0x18000b1b9  mov     dword ptr [rsp+38h+Args], 0
0x18000b1c1  lea     edx, [r9+2]
0x18000b1c5  lea     ecx, [rdx+1]
0x18000b1c8  mov     r8d, edx
0x18000b1cb  call    DpsNotifySvc
0x18000b1d0  mov     ebx, eax
0x18000b1d2  test    eax, eax
0x18000b1d4  jns     short loc_18000B1DE
0x18000b1d6  mov     r8d, 128h
0x18000b1dc  jmp     short loc_18000B240
0x18000b1de  call    DpspLaunchCommunicationServer
0x18000b1e3  mov     ebx, eax
0x18000b1e5  test    eax, eax
0x18000b1e7  jns     short loc_18000B1F1
0x18000b1e9  mov     r8d, 12Bh
0x18000b1ef  jmp     short loc_18000B240
0x18000b1f1  call    DpsRun
0x18000b1f6  lock or cs:g_fControl, 1
0x18000b1fe  jmp     short loc_18000B20B
0x18000b200  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000b205  call    cs:__imp_Sleep
0x18000b20b  mov     eax, cs:g_fControl
0x18000b211  test    al, 2
0x18000b213  jnz     short loc_18000B200
0x18000b215  mov     edx, 3
0x18000b21a  mov     dword ptr [rsp+38h+Args], 0
0x18000b222  mov     r9d, 1388h
0x18000b228  lea     ecx, [rdx+0Ch]
0x18000b22b  lea     r8d, [rdx-2]
0x18000b22f  call    DpsNotifySvc
0x18000b234  mov     ebx, eax
0x18000b236  test    eax, eax
0x18000b238  jns     short loc_18000B261
0x18000b23a  mov     r8d, 140h; int
0x18000b240  movzx   eax, ax
0x18000b243  lea     r9, aErrorD; "Error = %d"
0x18000b24a  lea     rdx, aServicemain_0; "ServiceMain"
0x18000b251  mov     dword ptr [rsp+38h+Args], eax; Args
0x18000b255  lea     rcx, aClientcoreBase_3; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b25c  call    WdipTraceError
0x18000b261  call    DpspFreeStateInformation
0x18000b266  call    cs:__imp_CoUninitialize
0x18000b26c  lea     rcx, WDI_DPS_EVENT_SHUTDOWN_PERF_END; EventDescriptor
0x18000b273  call    DpspRaisePerformanceEvent
0x18000b278  mov     rcx, cs:g_hETW; RegHandle
0x18000b27f  test    rcx, rcx
0x18000b282  jz      short loc_18000B28A
0x18000b284  call    cs:__imp_EventUnregister
0x18000b28a  xor     r9d, r9d
0x18000b28d  movzx   eax, bx
0x18000b290  xor     r8d, r8d
0x18000b293  mov     dword ptr [rsp+38h+Args], eax
0x18000b297  lea     edx, [r9+1]
0x18000b29b  lea     ecx, [rdx+8]
0x18000b29e  call    DpsNotifySvc
0x18000b2a3  add     rsp, 30h
0x18000b2a7  pop     rbx
0x18000b2a8  retn
```
