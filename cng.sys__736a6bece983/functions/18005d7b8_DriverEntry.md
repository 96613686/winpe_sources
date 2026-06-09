# DriverEntry

- ea: `0x18005d7b8`
- end: `0x18005dc91`
- name: `DriverEntry`
- size: `1241`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d9010`

## callees

- `0x18000743c`
- `0x180018e40`
- `0x180021af4`
- `0x1800348bc`
- `0x18003496c`
- `0x180046d98`
- `0x18004cbc0`
- `0x180056a28`
- `0x18005d69c`
- `0x18005d7b8`
- `0x18005dc98`
- `0x18005e398`
- `0x18005f9d8`
- `0x180064500`
- `0x180064670`
- `0x18009f650`
- `0x1800a41fc`
- `0x1800a4290`
- `0x1800a4f78`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x18005dc84`
- `ntoskrnl!KeBugCheckEx` at `0x18005dc84`
- `ntoskrnl!SkQuerySecureKernelInformation` at `0x18005da75`
- `ntoskrnl!SkQuerySecureKernelInformation` at `0x18005da75`
- `ntoskrnl!PsGetHostSilo` at `0x18005d9c6`
- `ntoskrnl!PsGetHostSilo` at `0x18005d9c6`
- `ntoskrnl!IoDeleteDevice` at `0x18005dc2f`
- `ntoskrnl!IoDeleteDevice` at `0x18005dc2f`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18005dc5e`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18005dc5e`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x18005d8de`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x18005d8de`
- `ntoskrnl!ExRegisterExtension` at `0x18005dbd4`
- `ntoskrnl!ExRegisterExtension` at `0x18005dbd4`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18005d8a5`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18005d8a5`
- `ntoskrnl!PsStartSiloMonitor` at `0x18005d8f7`
- `ntoskrnl!PsStartSiloMonitor` at `0x18005d8f7`
- `ntoskrnl!IoCreateDevice` at `0x18005d9a9`
- `ntoskrnl!IoCreateDevice` at `0x18005d9a9`
- `ntoskrnl!KeInitializeEvent` at `0x18005da5a`
- `ntoskrnl!KeInitializeEvent` at `0x18005da5a`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18005db67`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18005db67`

## string_xrefs

- `0x18005d8bd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18005dad7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18005dc13`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char TrustedEnvironment; // al
  int v5; // ebx
  NTSTATUS started; // eax
  __int64 v7; // r9
  struct _EJOB *HostSilo; // rax
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rcx
  char v12; // al
  int v13; // eax
  __int64 i; // rsi
  _QWORD *v15; // r15
  __int64 j; // rdi
  char *v17; // r14
  char v18; // al
  NTSTATUS ProcessNotifyRoutine; // eax
  __int64 v20; // r8
  char v22; // al
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-79h] BYREF
  __int128 v24; // [rsp+48h] [rbp-71h] BYREF
  __int128 v25; // [rsp+58h] [rbp-61h]
  __int64 v26; // [rsp+68h] [rbp-51h] BYREF
  __int128 v27; // [rsp+70h] [rbp-49h] BYREF
  __int128 v28; // [rsp+80h] [rbp-39h]
  _OWORD v29[3]; // [rsp+90h] [rbp-29h] BYREF
  char v30; // [rsp+C0h] [rbp+7h]

  DeviceObject = 0;
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  ExecuteHotpatchTestRuntimeFunction();
  v26 = 49;
  v30 = 0;
  TrustedEnvironment = g_TrustedEnvironment;
  memset(v29, 0, sizeof(v29));
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 2) == 0 )
  {
    *(_QWORD *)&DeviceName.Length = 1572886;
    DeviceName.Buffer = L"\\Device\\CNG";
    *(_DWORD *)((char *)&v27 + 1) = 0;
    *((_QWORD *)&v27 + 1) = &DriverObject->DriverName;
    *(_WORD *)((char *)&v27 + 5) = 0;
    *(_QWORD *)&v28 = CngSiloCreateNotify;
    *((_QWORD *)&v28 + 1) = CngSiloTerminateNotify;
    BYTE7(v27) = 0;
    LOBYTE(v27) = 1;
    started = PsRegisterSiloMonitor(&v27, &CngSiloMonitor);
    v5 = started;
    if ( started >= 0 )
    {
      g_SiloSlot = PsGetSiloMonitorContextSlot(CngSiloMonitor);
      started = PsStartSiloMonitor(CngSiloMonitor);
      v5 = started;
      if ( started >= 0 )
      {
        *(_QWORD *)&WPP_MAIN_CB.Type = 0;
        WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CNGTraceControlGuid;
        WPP_MAIN_CB.NextDevice = 0;
        WPP_MAIN_CB.CurrentIrp = 0;
        WPP_MAIN_CB.Timer = (PIO_TIMER)1;
        WppLoadTracingSupport();
        WPP_MAIN_CB.CurrentIrp = 0;
        WppInitKm();
        DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)CngDispatch;
        DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)CngDispatch;
        DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)CngDispatch;
        DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)CngDispatch;
        DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)CngDispatch;
        DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)CngDispatch;
        DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)CngDispatch;
        started = IoCreateDevice(DriverObject, 0, &DeviceName, 0x3Fu, 0x100u, 0, &DeviceObject);
        v5 = started;
        if ( started >= 0 )
        {
          HostSilo = (struct _EJOB *)PsGetHostSilo();
          v9 = InitializeTlsConfig(HostSilo);
          v5 = v9;
          if ( v9 >= 0 )
          {
            if ( !byte_1800CD7A8 )
              byte_1800CD7A8 = (unsigned int)TlgRegisterAggregateProvider() == 0;
            v9 = CngSetDeviceSecurity(DeviceObject);
            v5 = v9;
            if ( v9 >= 0 )
              goto LABEL_21;
            v10 = 514;
          }
          else
          {
            v10 = 505;
          }
LABEL_16:
          v11 = (unsigned int)v9;
LABEL_48:
          DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx", v10);
LABEL_49:
          if ( DeviceObject )
            IoDeleteDevice(DeviceObject);
LABEL_51:
          if ( CngSiloMonitor )
          {
            v22 = g_TrustedEnvironment;
            if ( !g_TrustedEnvironment )
              v22 = GetTrustedEnvironment();
            if ( (v22 & 2) == 0 )
            {
              PsUnregisterSiloMonitor(CngSiloMonitor);
              CngSiloMonitor = 0;
            }
          }
          KeBugCheckEx(0x121u, v5, 0, 0, 0);
        }
        v7 = 498;
      }
      else
      {
        v7 = 453;
      }
    }
    else
    {
      v7 = 440;
    }
    DebugTraceError(
      (unsigned int)started,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
      v7);
    goto LABEL_51;
  }
  if ( DriverObject || RegistryPath )
  {
    v5 = 0;
    goto LABEL_51;
  }
LABEL_21:
  SymCryptInitEnvWindowsKernelmodeWin8_1nLater();
  v12 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v12 = GetTrustedEnvironment();
  if ( (v12 & 2) != 0 )
  {
    if ( (int)SkQuerySecureKernelInformation(2, v29, &v26) < 0 )
    {
      v5 = -1073741595;
      v10 = 559;
      v11 = 3221225701LL;
      goto LABEL_48;
    }
  }
  else
  {
    CngEncryptMemMutex.Count = 1;
    CngEncryptMemMutex.Owner = 0;
    CngEncryptMemMutex.Contention = 0;
    KeInitializeEvent(&CngEncryptMemMutex.Event, SynchronizationEvent, 0);
  }
  g_fSteEnabled = 1;
  g_fSelftest = 1;
  SymCryptRngAesInstantiateSelftest();
  SymCryptRngAesReseedSelftest();
  SymCryptRngAesGenerateSelftest();
  v9 = InitializeMasterPrngSystem(DriverObject);
  v5 = v9;
  if ( v9 < 0 )
  {
    v10 = 603;
    goto LABEL_16;
  }
  v13 = InitializeCNG();
  v5 = v13;
  if ( v13 < 0 )
  {
    DebugTraceError(
      (unsigned int)v13,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
      610);
    for ( i = 0; i != 64; ++i )
    {
      v15 = (_QWORD *)g_AesStatesTable[i];
      if ( v15 )
      {
        for ( j = 0; j != 64; ++j )
        {
          v17 = (char *)v15[j];
          if ( v17 )
          {
            SymCryptRngAesUninstantiate(v17 + 16);
            BCryptFree(v17);
          }
        }
        BCryptFree(v15);
      }
    }
    SymCryptRngAesUninstantiate(qword_1800CC670);
    goto LABEL_49;
  }
  v18 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v18 = GetTrustedEnvironment();
  if ( (v18 & 2) == 0 )
  {
    ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutine(CngCreateProcessNotifyRoutine, 0);
    if ( ProcessNotifyRoutine < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, v20, (unsigned int)ProcessNotifyRoutine);
    }
    *(_QWORD *)&v24 = 0x24000000010003LL;
    *((_QWORD *)&v24 + 1) = off_1800A9220;
    *(_QWORD *)&v25 = 0;
    *((_QWORD *)&v25 + 1) = DriverObject;
    ExRegisterExtension(CngExtensionRegistration, 65537, &v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18005d7b8  push    rbp
0x18005d7ba  push    rbx
0x18005d7bb  push    rsi
0x18005d7bc  push    rdi
0x18005d7bd  push    r12
0x18005d7bf  push    r13
0x18005d7c1  push    r14
0x18005d7c3  push    r15
0x18005d7c5  lea     rbp, [rsp-1Fh]
0x18005d7ca  sub     rsp, 0D8h
0x18005d7d1  mov     rax, cs:__security_cookie
0x18005d7d8  xor     rax, rsp
0x18005d7db  mov     [rbp+57h+var_48], rax
0x18005d7df  xorps   xmm0, xmm0
0x18005d7e2  xorps   xmm1, xmm1
0x18005d7e5  xor     r12d, r12d
0x18005d7e8  mov     rbx, rdx
0x18005d7eb  mov     [rbp+57h+var_D0], r12
0x18005d7ef  mov     rdi, rcx
0x18005d7f2  movups  [rbp+57h+var_C8], xmm0
0x18005d7f6  movups  [rbp+57h+var_B8], xmm0
0x18005d7fa  movups  [rbp+57h+var_A0], xmm1
0x18005d7fe  movups  [rbp+57h+var_90], xmm1
0x18005d802  call    ExecuteHotpatchTestRuntimeFunction
0x18005d807  xor     eax, eax
0x18005d809  mov     [rbp+57h+var_A8], 31h ; '1'
0x18005d811  xorps   xmm0, xmm0
0x18005d814  mov     [rbp+57h+var_50], al
0x18005d817  mov     eax, cs:g_TrustedEnvironment
0x18005d81d  movups  [rbp+57h+var_80], xmm0
0x18005d821  movups  [rbp+57h+var_70], xmm0
0x18005d825  movups  [rbp+57h+var_60], xmm0
0x18005d829  test    eax, eax
0x18005d82b  jnz     short loc_18005D832
0x18005d82d  call    GetTrustedEnvironment
0x18005d832  mov     r13d, 1
0x18005d838  test    al, 2
0x18005d83a  jz      short loc_18005D852
0x18005d83c  test    rdi, rdi
0x18005d83f  jnz     short loc_18005D84A
0x18005d841  test    rbx, rbx
0x18005d844  jz      loc_18005DA1D
0x18005d84a  mov     ebx, r12d
0x18005d84d  jmp     loc_18005DC3B
0x18005d852  lea     rax, aDeviceCng; "\\Device\\CNG"
0x18005d859  mov     qword ptr cs:DeviceName.Length, 180016h
0x18005d864  mov     cs:DeviceName.Buffer, rax
0x18005d86b  lea     rdx, ?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005d872  lea     rax, [rdi+38h]
0x18005d876  mov     dword ptr [rbp+57h+var_A0+1], r12d
0x18005d87a  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18005d87e  lea     rcx, [rbp+57h+var_A0]
0x18005d882  lea     rax, CngSiloCreateNotify
0x18005d889  mov     word ptr [rbp+57h+var_A0+5], r12w
0x18005d88e  mov     qword ptr [rbp+57h+var_90], rax
0x18005d892  lea     rax, CngSiloTerminateNotify
0x18005d899  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005d89d  mov     byte ptr [rbp+57h+var_A0+7], r12b
0x18005d8a1  mov     byte ptr [rbp+57h+var_A0], r13b
0x18005d8a5  call    cs:__imp_PsRegisterSiloMonitor
0x18005d8ac  nop     dword ptr [rax+rax+00h]
0x18005d8b1  mov     ebx, eax
0x18005d8b3  test    eax, eax
0x18005d8b5  jns     short loc_18005D8D7
0x18005d8b7  mov     r9d, 1B8h
0x18005d8bd  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d8c4  mov     ecx, eax
0x18005d8c6  lea     rdx, aStatus; "Status"
0x18005d8cd  call    DebugTraceError
0x18005d8d2  jmp     loc_18005DC3B
0x18005d8d7  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005d8de  call    cs:__imp_PsGetSiloMonitorContextSlot
0x18005d8e5  nop     dword ptr [rax+rax+00h]
0x18005d8ea  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005d8f1  mov     cs:g_SiloSlot, eax
0x18005d8f7  call    cs:__imp_PsStartSiloMonitor
0x18005d8fe  nop     dword ptr [rax+rax+00h]
0x18005d903  mov     ebx, eax
0x18005d905  test    eax, eax
0x18005d907  jns     short loc_18005D911
0x18005d909  mov     r9d, 1C5h
0x18005d90f  jmp     short loc_18005D8BD
0x18005d911  lea     rax, WPP_ThisDir_CTLGUID_CNGTraceControlGuid
0x18005d918  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x18005d91f  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x18005d926  mov     cs:WPP_MAIN_CB.NextDevice, r12
0x18005d92d  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x18005d934  mov     cs:WPP_MAIN_CB.Timer, r13
0x18005d93b  call    WppLoadTracingSupport
0x18005d940  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x18005d947  call    WppInitKm
0x18005d94c  lea     rax, CngDispatch
0x18005d953  mov     r9d, 3Fh ; '?'; DeviceType
0x18005d959  mov     [rdi+70h], rax
0x18005d95d  lea     r8, DeviceName; DeviceName
0x18005d964  mov     [rdi+80h], rax
0x18005d96b  xor     edx, edx; DeviceExtensionSize
0x18005d96d  mov     [rdi+88h], rax
0x18005d974  mov     rcx, rdi; DriverObject
0x18005d977  mov     [rdi+90h], rax
0x18005d97e  mov     [rdi+98h], rax
0x18005d985  mov     [rdi+0C0h], rax
0x18005d98c  mov     [rdi+0E0h], rax
0x18005d993  lea     rax, [rbp+57h+var_D0]
0x18005d997  mov     [rsp+110h+DeviceObject], rax; DeviceObject
0x18005d99c  mov     [rsp+110h+Exclusive], r12b; Exclusive
0x18005d9a1  mov     [rsp+110h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x18005d9a9  call    cs:__imp_IoCreateDevice
0x18005d9b0  nop     dword ptr [rax+rax+00h]
0x18005d9b5  mov     ebx, eax
0x18005d9b7  test    eax, eax
0x18005d9b9  jns     short loc_18005D9C6
0x18005d9bb  mov     r9d, 1F2h
0x18005d9c1  jmp     loc_18005D8BD
0x18005d9c6  call    cs:__imp_PsGetHostSilo
0x18005d9cd  nop     dword ptr [rax+rax+00h]
0x18005d9d2  mov     rcx, rax; struct _EJOB *
0x18005d9d5  call    InitializeTlsConfig
0x18005d9da  mov     ebx, eax
0x18005d9dc  test    eax, eax
0x18005d9de  jns     short loc_18005D9ED
0x18005d9e0  mov     r9d, 1F9h
0x18005d9e6  mov     ecx, eax
0x18005d9e8  jmp     loc_18005DC13
0x18005d9ed  cmp     cs:byte_1800CD7A8, r12b
0x18005d9f4  jnz     short loc_18005DA06
0x18005d9f6  call    TlgRegisterAggregateProvider
0x18005d9fb  test    eax, eax
0x18005d9fd  jnz     short loc_18005DA06
0x18005d9ff  mov     cs:byte_1800CD7A8, r13b
0x18005da06  mov     rcx, [rbp+57h+var_D0]
0x18005da0a  call    CngSetDeviceSecurity
0x18005da0f  mov     ebx, eax
0x18005da11  test    eax, eax
0x18005da13  jns     short loc_18005DA1D
0x18005da15  mov     r9d, 202h
0x18005da1b  jmp     short loc_18005D9E6
0x18005da1d  call    SymCryptInitEnvWindowsKernelmodeWin8_1nLater
0x18005da22  mov     eax, cs:g_TrustedEnvironment
0x18005da28  test    eax, eax
0x18005da2a  jnz     short loc_18005DA31
0x18005da2c  call    GetTrustedEnvironment
0x18005da31  test    al, 2
0x18005da33  jnz     short loc_18005DA68
0x18005da35  xor     r8d, r8d; State
0x18005da38  mov     cs:CngEncryptMemMutex.Count, r13d
0x18005da3f  mov     edx, r13d; Type
0x18005da42  mov     cs:CngEncryptMemMutex.Owner, r12
0x18005da49  lea     rcx, CngEncryptMemMutex.Event; Event
0x18005da50  mov     cs:CngEncryptMemMutex.Contention, r12d
0x18005da57  mov     rbx, r12
0x18005da5a  call    cs:__imp_KeInitializeEvent
0x18005da61  nop     dword ptr [rax+rax+00h]
0x18005da66  jmp     short loc_18005DA8D
0x18005da68  lea     r8, [rbp+57h+var_A8]
0x18005da6c  mov     ecx, 2
0x18005da71  lea     rdx, [rbp+57h+var_80]
0x18005da75  call    cs:__imp_SkQuerySecureKernelInformation
0x18005da7c  nop     dword ptr [rax+rax+00h]
0x18005da81  test    eax, eax
0x18005da83  js      loc_18005DC03
0x18005da89  lea     rbx, [rbp+57h+var_80]
0x18005da8d  mov     cs:g_fSteEnabled, r13b
0x18005da94  mov     cs:g_fSelftest, r13b
0x18005da9b  call    SymCryptRngAesInstantiateSelftest
0x18005daa0  call    SymCryptRngAesReseedSelftest
0x18005daa5  call    SymCryptRngAesGenerateSelftest
0x18005daaa  mov     rdx, rbx
0x18005daad  mov     rcx, rdi; DriverObject
0x18005dab0  call    InitializeMasterPrngSystem
0x18005dab5  mov     ebx, eax
0x18005dab7  test    eax, eax
0x18005dab9  jns     short loc_18005DAC6
0x18005dabb  mov     r9d, 25Bh
0x18005dac1  jmp     loc_18005D9E6
0x18005dac6  call    InitializeCNG
0x18005dacb  mov     ebx, eax
0x18005dacd  test    eax, eax
0x18005dacf  jns     short loc_18005DB47
0x18005dad1  mov     r9d, 262h
0x18005dad7  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005dade  lea     rdx, aStatus; "Status"
0x18005dae5  mov     ecx, eax
0x18005dae7  call    DebugTraceError
0x18005daec  mov     rsi, r12
0x18005daef  lea     r15, g_AesStatesTable
0x18005daf6  mov     r15, [r15+rsi*8]
0x18005dafa  test    r15, r15
0x18005dafd  jz      short loc_18005DB2D
0x18005daff  mov     rdi, r12
0x18005db02  mov     r14, [r15+rdi*8]
0x18005db06  test    r14, r14
0x18005db09  jz      short loc_18005DB1C
0x18005db0b  lea     rcx, [r14+10h]
0x18005db0f  call    SymCryptRngAesUninstantiate
0x18005db14  mov     rcx, r14; P
0x18005db17  call    BCryptFree
0x18005db1c  add     rdi, r13
0x18005db1f  cmp     rdi, 40h ; '@'
0x18005db23  jnz     short loc_18005DB02
0x18005db25  mov     rcx, r15; P
0x18005db28  call    BCryptFree
0x18005db2d  inc     rsi
0x18005db30  cmp     rsi, 40h ; '@'
0x18005db34  jnz     short loc_18005DAEF
0x18005db36  lea     rcx, qword_1800CC670
0x18005db3d  call    SymCryptRngAesUninstantiate
0x18005db42  jmp     loc_18005DC26
0x18005db47  mov     eax, cs:g_TrustedEnvironment
0x18005db4d  test    eax, eax
0x18005db4f  jnz     short loc_18005DB56
0x18005db51  call    GetTrustedEnvironment
0x18005db56  test    al, 2
0x18005db58  jnz     loc_18005DBE0
0x18005db5e  xor     edx, edx; Remove
0x18005db60  lea     rcx, CngCreateProcessNotifyRoutine; NotifyRoutine
0x18005db67  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x18005db6e  nop     dword ptr [rax+rax+00h]
0x18005db73  test    eax, eax
0x18005db75  jns     short loc_18005DBA3
0x18005db77  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db7e  lea     rdx, WPP_GLOBAL_Control
0x18005db85  cmp     rcx, rdx
0x18005db88  jz      short loc_18005DBA3
0x18005db8a  mov     edx, [rcx+2Ch]
0x18005db8d  test    dl, 2
0x18005db90  jz      short loc_18005DBA3
0x18005db92  mov     rcx, [rcx+18h]
0x18005db96  mov     edx, 0Ah
0x18005db9b  mov     r9d, eax
0x18005db9e  call    WPP_SF_D
0x18005dba3  lea     rax, off_1800A9220
0x18005dbaa  mov     dword ptr [rbp+57h+var_C8], 10003h
0x18005dbb1  lea     r8, [rbp+57h+var_C8]
0x18005dbb5  mov     qword ptr [rbp+57h+var_C8+8], rax
0x18005dbb9  mov     edx, 10001h
0x18005dbbe  mov     dword ptr [rbp+57h+var_C8+4], 240000h
0x18005dbc5  lea     rcx, CngExtensionRegistration
0x18005dbcc  mov     qword ptr [rbp+57h+var_B8], r12
0x18005dbd0  mov     qword ptr [rbp+57h+var_B8+8], rdi
0x18005dbd4  call    cs:__imp_ExRegisterExtension
0x18005dbdb  nop     dword ptr [rax+rax+00h]
0x18005dbe0  xor     eax, eax
0x18005dbe2  mov     rcx, [rbp+57h+var_48]
0x18005dbe6  xor     rcx, rsp; StackCookie
0x18005dbe9  call    __security_check_cookie
0x18005dbee  add     rsp, 0D8h
0x18005dbf5  pop     r15
0x18005dbf7  pop     r14
0x18005dbf9  pop     r13
0x18005dbfb  pop     r12
0x18005dbfd  pop     rdi
0x18005dbfe  pop     rsi
0x18005dbff  pop     rbx
0x18005dc00  pop     rbp
0x18005dc01  retn
0x18005dc03  mov     ebx, 0C00000E5h
0x18005dc08  mov     r9d, 22Fh
0x18005dc0e  mov     ecx, 0C00000E5h
0x18005dc13  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005dc1a  lea     rdx, aStatus; "Status"
0x18005dc21  call    DebugTraceError
0x18005dc26  mov     rcx, [rbp+57h+var_D0]; DeviceObject
0x18005dc2a  test    rcx, rcx
0x18005dc2d  jz      short loc_18005DC3B
0x18005dc2f  call    cs:__imp_IoDeleteDevice
0x18005dc36  nop     dword ptr [rax+rax+00h]
0x18005dc3b  cmp     cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA, r12; _SILO_MONITOR * CngSiloMonitor
0x18005dc42  jz      short loc_18005DC71
0x18005dc44  mov     eax, cs:g_TrustedEnvironment
0x18005dc4a  test    eax, eax
0x18005dc4c  jnz     short loc_18005DC53
0x18005dc4e  call    GetTrustedEnvironment
0x18005dc53  test    al, 2
0x18005dc55  jnz     short loc_18005DC71
0x18005dc57  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005dc5e  call    cs:__imp_PsUnregisterSiloMonitor
0x18005dc65  nop     dword ptr [rax+rax+00h]
0x18005dc6a  mov     cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA, r12; _SILO_MONITOR * CngSiloMonitor
0x18005dc71  movsxd  rdx, ebx; BugCheckParameter1
0x18005dc74  xor     r9d, r9d; BugCheckParameter3
0x18005dc77  xor     r8d, r8d; BugCheckParameter2
0x18005dc7a  mov     qword ptr [rsp+110h+DeviceCharacteristics], r12; BugCheckParameter4
0x18005dc7f  mov     ecx, 121h; BugCheckCode
0x18005dc84  call    cs:__imp_KeBugCheckEx
```
