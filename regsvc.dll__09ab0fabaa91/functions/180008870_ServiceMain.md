# ServiceMain

- ea: `0x180008870`
- end: `0x180008a51`
- name: `ServiceMain`
- size: `481`
- prototype: `ULONG __fastcall(__int64, LPCWSTR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008600`
- `0x180008694`
- `0x180008870`
- `0x180008af0`
- `0x180017688`
- `0x1800176d8`
- `0x180017728`
- `0x18001f010`

## import_xrefs

- `ntdll!DbgPrint` at `0x180008a4a`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000896f`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180008984`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000896f`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180008984`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800088d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800088d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a13`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800088a4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800088a4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800089f6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800089f6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008949`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008949`

## string_xrefs

- `0x1800089a3`: `RemoteRegistry`
- `0x180008a3f`: `RegisterServiceCtrlHandler failed!  %d\n`

## pseudocode

```c
ULONG __fastcall ServiceMain(__int64 a1, LPCWSTR *a2)
{
  __int64 v2; // rcx
  DWORD LastError; // eax

  qword_18002BFB4 = 0;
  g_status = 32;
  xmmword_18002BFA4 = 0;
  g_hStatus = (__int64)RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
  if ( g_hStatus )
  {
    UpdateServiceStatus(2, 0, 3000);
    g_hEventTerminated = CreateEventW(0, 0, 0, 0);
    if ( g_hEventTerminated )
    {
      RestrictedHandlesQuota = 0;
      if ( (int)OpenMachineKey(&RestrictedMachineHandle) >= 0
        && (int)OpenUserKey(&RestrictedUserHandle) >= 0
        && (unsigned int)InitializeRemoteSecurity()
        && (unsigned int)StartWinregRPCServer() )
      {
        if ( EventRegister(&MS_Windows_Kernel_AppCompat_Provider, 0, 0, &RegSvcEtwHandle) )
        {
          RegSvcEtwHandle = 0;
        }
        else
        {
          if ( !RpcServerRegisterAuthInfoW(0, 0xAu, 0, 0)
            && !RpcServerRegisterAuthInfoW(0, 9u, 0, 0)
            && !(*(unsigned int (__fastcall **)(HANDLE *, const wchar_t *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(g_svcsGlobalData + 192))(
                  &g_hRegisteredWait,
                  L"RemoteRegistry",
                  g_hEventTerminated,
                  StopService,
                  0,
                  8) )
          {
            DWORD1(xmmword_18002BFA4) = 1;
            v2 = 4;
            return UpdateServiceStatus(v2, 0, 0);
          }
          ShutdownWinreg();
        }
      }
    }
    if ( g_hRegisteredWait )
    {
      UnregisterWaitEx(g_hRegisteredWait, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      g_hRegisteredWait = 0;
    }
    if ( g_hEventTerminated )
    {
      CloseHandle(g_hEventTerminated);
      g_hEventTerminated = 0;
    }
    v2 = 1;
    return UpdateServiceStatus(v2, 0, 0);
  }
  LastError = GetLastError();
  return DbgPrint("RegisterServiceCtrlHandler failed!  %d\n", LastError);
}

```

## disassembly

```asm
0x180008870  sub     rsp, 48h
0x180008874  mov     rax, rdx
0x180008877  mov     cs:qword_18002BFB4, 0
0x180008882  xorps   xmm0, xmm0
0x180008885  mov     cs:g_status, 20h ; ' '
0x18000888f  movdqu  cs:xmmword_18002BFA4, xmm0
0x180008897  xor     r8d, r8d; lpContext
0x18000889a  lea     rdx, ServiceHandler; lpHandlerProc
0x1800088a1  mov     rcx, [rax]; lpServiceName
0x1800088a4  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800088aa  mov     cs:g_hStatus, rax
0x1800088b1  test    rax, rax
0x1800088b4  jz      loc_180008A37
0x1800088ba  xor     edx, edx
0x1800088bc  mov     r8d, 0BB8h
0x1800088c2  lea     ecx, [rdx+2]
0x1800088c5  call    UpdateServiceStatus
0x1800088ca  xor     r9d, r9d; lpName
0x1800088cd  xor     r8d, r8d; bInitialState
0x1800088d0  xor     edx, edx; bManualReset
0x1800088d2  xor     ecx, ecx; lpEventAttributes
0x1800088d4  call    cs:__imp_CreateEventW
0x1800088da  mov     cs:g_hEventTerminated, rax
0x1800088e1  test    rax, rax
0x1800088e4  jz      loc_1800089E6
0x1800088ea  lea     rcx, RestrictedMachineHandle
0x1800088f1  mov     cs:RestrictedHandlesQuota, 0
0x1800088fb  call    OpenMachineKey
0x180008900  test    eax, eax
0x180008902  js      loc_1800089E6
0x180008908  lea     rcx, RestrictedUserHandle
0x18000890f  call    OpenUserKey
0x180008914  test    eax, eax
0x180008916  js      loc_1800089E6
0x18000891c  call    InitializeRemoteSecurity
0x180008921  test    eax, eax
0x180008923  jz      loc_1800089E6
0x180008929  call    StartWinregRPCServer
0x18000892e  test    eax, eax
0x180008930  jz      loc_1800089E6
0x180008936  lea     r9, RegSvcEtwHandle; RegHandle
0x18000893d  xor     r8d, r8d; CallbackContext
0x180008940  xor     edx, edx; EnableCallback
0x180008942  lea     rcx, MS_Windows_Kernel_AppCompat_Provider; ProviderId
0x180008949  call    cs:__imp_EventRegister
0x18000894f  test    eax, eax
0x180008951  jz      short loc_180008963
0x180008953  mov     cs:RegSvcEtwHandle, 0
0x18000895e  jmp     loc_1800089E6
0x180008963  xor     r9d, r9d; Arg
0x180008966  xor     r8d, r8d; GetKeyFn
0x180008969  xor     ecx, ecx; ServerPrincName
0x18000896b  lea     edx, [r9+0Ah]; AuthnSvc
0x18000896f  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180008975  test    eax, eax
0x180008977  jnz     short loc_1800089E1
0x180008979  xor     r9d, r9d; Arg
0x18000897c  lea     edx, [rax+9]; AuthnSvc
0x18000897f  xor     r8d, r8d; GetKeyFn
0x180008982  xor     ecx, ecx; ServerPrincName
0x180008984  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18000898a  test    eax, eax
0x18000898c  jnz     short loc_1800089E1
0x18000898e  mov     rax, cs:g_svcsGlobalData
0x180008995  lea     r9, StopService
0x18000899c  mov     r8, cs:g_hEventTerminated
0x1800089a3  lea     rdx, aRemoteregistry; "RemoteRegistry"
0x1800089aa  mov     [rsp+48h+var_20], 8
0x1800089b2  lea     rcx, g_hRegisteredWait
0x1800089b9  mov     [rsp+48h+var_28], 0
0x1800089c2  mov     rax, [rax+0C0h]
0x1800089c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ce  test    eax, eax
0x1800089d0  jnz     short loc_1800089E1
0x1800089d2  mov     dword ptr cs:xmmword_18002BFA4+4, 1
0x1800089dc  lea     ecx, [rax+4]
0x1800089df  jmp     short loc_180008A29
0x1800089e1  call    ShutdownWinreg
0x1800089e6  mov     rcx, cs:g_hRegisteredWait; WaitHandle
0x1800089ed  test    rcx, rcx
0x1800089f0  jz      short loc_180008A07
0x1800089f2  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800089f6  call    cs:__imp_UnregisterWaitEx
0x1800089fc  mov     cs:g_hRegisteredWait, 0
0x180008a07  mov     rcx, cs:g_hEventTerminated; hObject
0x180008a0e  test    rcx, rcx
0x180008a11  jz      short loc_180008A24
0x180008a13  call    cs:__imp_CloseHandle
0x180008a19  mov     cs:g_hEventTerminated, 0
0x180008a24  mov     ecx, 1
0x180008a29  xor     r8d, r8d
0x180008a2c  xor     edx, edx
0x180008a2e  add     rsp, 48h
0x180008a32  jmp     UpdateServiceStatus
0x180008a37  call    cs:__imp_GetLastError
0x180008a3d  mov     edx, eax
0x180008a3f  lea     rcx, aRegisterservic; "RegisterServiceCtrlHandler failed!  %d"...
0x180008a46  add     rsp, 48h
0x180008a4a  jmp     cs:__imp_DbgPrint
```
