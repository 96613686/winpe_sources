# InitializeService(ulong,ushort * * const)

- ea: `0x1800060b0`
- end: `0x180006207`
- name: `?InitializeService@@YAJKQEAPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008390`

## callees

- `0x180001cf0`
- `0x1800060b0`
- `0x180007b9c`
- `0x180009418`
- `0x18000a850`
- `0x18000bb94`
- `0x18000c120`
- `0x18000c164`
- `0x18000e83c`
- `0x18000e8a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800060f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800060f9`
- `DeclaredConfigurationAPI!InitOrchestratorEngine` at `0x180006150`
- `DeclaredConfigurationAPI!InitOrchestratorEngine` at `0x180006150`

## pseudocode

```c
__int64 __fastcall InitializeService(__int64 a1, unsigned __int16 **const a2)
{
  CDeclaredConfigurationLogger *Logger; // rax
  DcSvcStopStart *v3; // rcx
  __int64 v4; // r8
  unsigned int v5; // edx
  DcSvcStopStart *v6; // rcx
  int inited; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 *v11; // rdx
  int v13; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-28h] BYREF
  int *v15; // [rsp+48h] [rbp-18h]
  __int64 v16; // [rsp+50h] [rbp-10h]

  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogServiceStart(Logger);
  if ( !DcSvcStopStart::g_hTimer )
  {
    DcSvcStopStart::g_IdleStopPeriod = DcSvcStopStart::GetDmWapIdleWaitTime(v3);
    DcSvcStopStart::g_hTimer = CreateThreadpoolTimer(DcSvcStopStart::TimerCallback, 0, 0);
    DcSvcStopStart::SetTimerCountToRegistry((DcSvcStopStart *)1, v5);
    DcSvcStopStart::SetShutdownTimer(v6);
  }
  if ( (byte_18001B741 & 4) != 0 )
  {
    v13 = 0;
    v15 = &v13;
    v16 = 4;
    McGenEventWrite_EventWriteTransfer(v3, EnterpriseDiagnosticsDcSvcStartSuccess, v4, 2, v14);
  }
  inited = InitOrchestratorEngine();
  v10 = inited;
  if ( inited < 0 )
  {
    if ( (byte_18001B741 & 2) != 0 )
    {
      v11 = EnterpriseDiagnosticsDMOrchestratorStartServiceError;
LABEL_11:
      v13 = inited;
      v16 = 4;
      v15 = &v13;
      McGenEventWrite_EventWriteTransfer(v8, v11, v9, 2, v14);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  inited = RegisterRPCInterface();
  v10 = inited;
  if ( inited < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
    {
      v11 = EnterpriseDiagnosticsDcSvcEngRegisterRPCInterfaceFailure;
      goto LABEL_11;
    }
LABEL_12:
    SvcEngUninitialize(v8);
    return v10;
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
  {
    v13 = inited;
    v16 = 4;
    v15 = &v13;
    McGenEventWrite_EventWriteTransfer(v8, EnterpriseDiagnosticsDcSvcEngRegisterRPCInterfaceSuccess, v9, 2, v14);
  }
  return v10;
}

```

## disassembly

```asm
0x1800060b0  mov     [rsp-8+arg_0], rbx
0x1800060b5  push    rbp
0x1800060b6  mov     rbp, rsp
0x1800060b9  sub     rsp, 60h
0x1800060bd  mov     rax, cs:__security_cookie
0x1800060c4  xor     rax, rsp
0x1800060c7  mov     [rbp+var_8], rax
0x1800060cb  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800060d0  mov     rcx, rax; this
0x1800060d3  call    ?LogServiceStart@CDeclaredConfigurationLogger@@QEAAXXZ; CDeclaredConfigurationLogger::LogServiceStart(void)
0x1800060d8  cmp     cs:?g_hTimer@DcSvcStopStart@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * DcSvcStopStart::g_hTimer
0x1800060e0  jnz     short loc_180006115
0x1800060e2  call    ?GetDmWapIdleWaitTime@DcSvcStopStart@@YAKXZ; DcSvcStopStart::GetDmWapIdleWaitTime(void)
0x1800060e7  xor     r8d, r8d; pcbe
0x1800060ea  mov     cs:?g_IdleStopPeriod@DcSvcStopStart@@3KA, eax; ulong DcSvcStopStart::g_IdleStopPeriod
0x1800060f0  xor     edx, edx; pv
0x1800060f2  lea     rcx, ?TimerCallback@DcSvcStopStart@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800060f9  call    cs:__imp_CreateThreadpoolTimer
0x1800060ff  mov     ecx, 1; this
0x180006104  mov     cs:?g_hTimer@DcSvcStopStart@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * DcSvcStopStart::g_hTimer
0x18000610b  call    ?SetTimerCountToRegistry@DcSvcStopStart@@YAJK@Z; DcSvcStopStart::SetTimerCountToRegistry(ulong)
0x180006110  call    ?SetShutdownTimer@DcSvcStopStart@@YAHXZ; DcSvcStopStart::SetShutdownTimer(void)
0x180006115  test    cs:byte_18001B741, 4
0x18000611c  jz      short loc_180006150
0x18000611e  lea     rax, [rbp+var_30]
0x180006122  mov     [rbp+var_30], 0
0x180006129  mov     [rbp+var_18], rax
0x18000612d  lea     rdx, EnterpriseDiagnosticsDcSvcStartSuccess
0x180006134  lea     rax, [rbp+var_28]
0x180006138  mov     [rbp+var_10], 4
0x180006140  mov     r9d, 2
0x180006146  mov     [rsp+60h+var_40], rax
0x18000614b  call    McGenEventWrite_EventWriteTransfer
0x180006150  call    cs:__imp_InitOrchestratorEngine
0x180006156  mov     ebx, eax
0x180006158  test    eax, eax
0x18000615a  jns     short loc_18000616E
0x18000615c  test    cs:byte_18001B741, 2
0x180006163  jz      short loc_1800061B0
0x180006165  lea     rdx, EnterpriseDiagnosticsDMOrchestratorStartServiceError
0x18000616c  jmp     short loc_180006189
0x18000616e  call    ?RegisterRPCInterface@@YAJXZ; RegisterRPCInterface(void)
0x180006173  mov     ebx, eax
0x180006175  test    eax, eax
0x180006177  jns     short loc_1800061B7
0x180006179  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180006180  jz      short loc_1800061B0
0x180006182  lea     rdx, EnterpriseDiagnosticsDcSvcEngRegisterRPCInterfaceFailure
0x180006189  mov     [rbp+var_30], eax
0x18000618c  mov     r9d, 2
0x180006192  lea     rax, [rbp+var_30]
0x180006196  mov     [rbp+var_10], 4
0x18000619e  mov     [rbp+var_18], rax
0x1800061a2  lea     rax, [rbp+var_28]
0x1800061a6  mov     [rsp+60h+var_40], rax
0x1800061ab  call    McGenEventWrite_EventWriteTransfer
0x1800061b0  call    ?SvcEngUninitialize@@YAJJ@Z; SvcEngUninitialize(long)
0x1800061b5  jmp     short loc_1800061EE
0x1800061b7  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x1800061be  jz      short loc_1800061EE
0x1800061c0  mov     [rbp+var_30], eax
0x1800061c3  lea     rdx, EnterpriseDiagnosticsDcSvcEngRegisterRPCInterfaceSuccess
0x1800061ca  lea     rax, [rbp+var_30]
0x1800061ce  mov     [rbp+var_10], 4
0x1800061d6  mov     [rbp+var_18], rax
0x1800061da  mov     r9d, 2
0x1800061e0  lea     rax, [rbp+var_28]
0x1800061e4  mov     [rsp+60h+var_40], rax
0x1800061e9  call    McGenEventWrite_EventWriteTransfer
0x1800061ee  mov     eax, ebx
0x1800061f0  mov     rcx, [rbp+var_8]
0x1800061f4  xor     rcx, rsp; StackCookie
0x1800061f7  call    __security_check_cookie
0x1800061fc  mov     rbx, [rsp+60h+arg_0]
0x180006201  add     rsp, 60h
0x180006205  pop     rbp
0x180006206  retn
```
