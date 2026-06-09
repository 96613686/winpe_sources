# DsRoleShutDownEx

- ea: `0x180009ee0`
- end: `0x180009fd1`
- name: `DsRoleShutDownEx`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180009cf0`

## callees

- `0x180009ee0`
- `0x18000a0b0`
- `0x180015574`
- `0x180020dbc`
- `0x180021278`
- `0x18002aeb4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009fab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009fab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f4c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009f6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009f6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f5e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f5e`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180009f19`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180009f19`
- `LSASRV!LsapDssetupInitializeGetPrimaryDomainInformationOpState` at `0x180009f2b`
- `LSASRV!LsapDssetupInitializeGetPrimaryDomainInformationOpState` at `0x180009f2b`

## string_xrefs

- `0x180009ee9`: `DS Role Server Service shutting down\n`

## pseudocode

```c
__int64 __fastcall DsRoleShutDownEx(__int64 a1)
{
  DsRolepLogPrintRoutine(4, "DS Role Server Service shutting down\n");
  DsRoleState = 0;
  if ( gRPCServerInitialized && !RpcServerUnregisterIfEx(qword_18002FB70, 0, 0) )
    gRPCServerInitialized = 0;
  LsapDssetupInitializeGetPrimaryDomainInformationOpState(0);
  DsRolepCancel(0);
  if ( DsRoleNotificationTimer )
  {
    SetThreadpoolTimer(DsRoleNotificationTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(DsRoleNotificationTimer, 1);
    CloseThreadpoolTimer(DsRoleNotificationTimer);
    DsRoleNotificationTimer = 0;
  }
  if ( !g_DsRoleRegistrationHandle || !(unsigned int)CEventUnregister() )
    g_DsRoleRegistrationHandle = 0;
  DsRolepFreeInterfaceSDs();
  if ( DsRoleStopEvent )
  {
    CloseHandle(DsRoleStopEvent);
    DsRoleStopEvent = 0;
  }
  if ( !a1 )
    UpdateStatus(1);
  return 0;
}

```

## disassembly

```asm
0x180009ee0  push    rbx
0x180009ee2  sub     rsp, 20h
0x180009ee6  mov     rbx, rcx
0x180009ee9  lea     rdx, aDsRoleServerSe_0; "DS Role Server Service shutting down\n"
0x180009ef0  mov     ecx, 4
0x180009ef5  call    DsRolepLogPrintRoutine
0x180009efa  cmp     cs:gRPCServerInitialized, 0
0x180009f01  mov     cs:DsRoleState, 0
0x180009f0b  jz      short loc_180009F29
0x180009f0d  xor     r8d, r8d; RundownContextHandles
0x180009f10  lea     rcx, qword_18002FB70; IfSpec
0x180009f17  xor     edx, edx; MgrTypeUuid
0x180009f19  call    cs:__imp_RpcServerUnregisterIfEx
0x180009f1f  test    eax, eax
0x180009f21  jnz     short loc_180009F29
0x180009f23  mov     cs:gRPCServerInitialized, al
0x180009f29  xor     ecx, ecx
0x180009f2b  call    cs:__imp_LsapDssetupInitializeGetPrimaryDomainInformationOpState
0x180009f31  xor     ecx, ecx
0x180009f33  call    DsRolepCancel
0x180009f38  mov     rcx, cs:DsRoleNotificationTimer; pti
0x180009f3f  test    rcx, rcx
0x180009f42  jz      short loc_180009F7C
0x180009f44  xor     r9d, r9d; msWindowLength
0x180009f47  xor     r8d, r8d; msPeriod
0x180009f4a  xor     edx, edx; pftDueTime
0x180009f4c  call    cs:__imp_SetThreadpoolTimer
0x180009f52  mov     rcx, cs:DsRoleNotificationTimer; pti
0x180009f59  mov     edx, 1; fCancelPendingCallbacks
0x180009f5e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009f64  mov     rcx, cs:DsRoleNotificationTimer; pti
0x180009f6b  call    cs:__imp_CloseThreadpoolTimer
0x180009f71  mov     cs:DsRoleNotificationTimer, 0
0x180009f7c  cmp     cs:?g_DsRoleRegistrationHandle@@3_KA, 0; unsigned __int64 g_DsRoleRegistrationHandle
0x180009f84  jz      short loc_180009F8F
0x180009f86  call    CEventUnregister
0x180009f8b  test    eax, eax
0x180009f8d  jnz     short loc_180009F9A
0x180009f8f  mov     cs:?g_DsRoleRegistrationHandle@@3_KA, 0; unsigned __int64 g_DsRoleRegistrationHandle
0x180009f9a  call    DsRolepFreeInterfaceSDs
0x180009f9f  mov     rcx, cs:DsRoleStopEvent; hObject
0x180009fa6  test    rcx, rcx
0x180009fa9  jz      short loc_180009FBC
0x180009fab  call    cs:__imp_CloseHandle
0x180009fb1  mov     cs:DsRoleStopEvent, 0
0x180009fbc  test    rbx, rbx
0x180009fbf  jnz     short loc_180009FC9
0x180009fc1  lea     ecx, [rbx+1]
0x180009fc4  call    UpdateStatus
0x180009fc9  xor     eax, eax
0x180009fcb  add     rsp, 20h
0x180009fcf  pop     rbx
0x180009fd0  retn
```
