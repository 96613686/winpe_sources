# DriverEntry

- ea: `0x18005cec8`
- end: `0x18005d3a1`
- name: `DriverEntry`
- size: `1241`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d6010`

## callees

- `0x18000743c`
- `0x18001bd90`
- `0x180024a34`
- `0x180033dbc`
- `0x180033e6c`
- `0x180046308`
- `0x18004c380`
- `0x180056138`
- `0x18005cdac`
- `0x18005cec8`
- `0x18005d3a8`
- `0x18005daa8`
- `0x18005f0e8`
- `0x180063b80`
- `0x180063cf0`
- `0x18009d820`
- `0x1800a23cc`
- `0x1800a2460`
- `0x1800a3148`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x18005d394`
- `ntoskrnl!KeBugCheckEx` at `0x18005d394`
- `ntoskrnl!SkQuerySecureKernelInformation` at `0x18005d185`
- `ntoskrnl!SkQuerySecureKernelInformation` at `0x18005d185`
- `ntoskrnl!PsGetHostSilo` at `0x18005d0d6`
- `ntoskrnl!PsGetHostSilo` at `0x18005d0d6`
- `ntoskrnl!IoDeleteDevice` at `0x18005d33f`
- `ntoskrnl!IoDeleteDevice` at `0x18005d33f`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18005d36e`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18005d36e`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x18005cfee`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x18005cfee`
- `ntoskrnl!ExRegisterExtension` at `0x18005d2e4`
- `ntoskrnl!ExRegisterExtension` at `0x18005d2e4`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18005cfb5`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18005cfb5`
- `ntoskrnl!PsStartSiloMonitor` at `0x18005d007`
- `ntoskrnl!PsStartSiloMonitor` at `0x18005d007`
- `ntoskrnl!IoCreateDevice` at `0x18005d0b9`
- `ntoskrnl!IoCreateDevice` at `0x18005d0b9`
- `ntoskrnl!KeInitializeEvent` at `0x18005d16a`
- `ntoskrnl!KeInitializeEvent` at `0x18005d16a`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18005d277`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x18005d277`

## string_xrefs

- `0x18005cfcd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18005d1e7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x18005d323`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

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
            if ( !byte_1800CB768 )
              byte_1800CB768 = (unsigned int)TlgRegisterAggregateProvider() == 0;
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
    SymCryptRngAesUninstantiate(qword_1800CA630);
    goto LABEL_49;
  }
  v18 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v18 = GetTrustedEnvironment();
  if ( (v18 & 2) == 0 )
  {
    ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutine(
                             (PCREATE_PROCESS_NOTIFY_ROUTINE)CngCreateProcessNotifyRoutine,
                             0);
    if ( ProcessNotifyRoutine < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 10, v20, (unsigned int)ProcessNotifyRoutine);
    }
    *(_QWORD *)&v24 = 0x24000000010003LL;
    *((_QWORD *)&v24 + 1) = off_1800A7220;
    *(_QWORD *)&v25 = 0;
    *((_QWORD *)&v25 + 1) = DriverObject;
    ExRegisterExtension(CngExtensionRegistration, 65537, &v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18005cec8  push    rbp
0x18005ceca  push    rbx
0x18005cecb  push    rsi
0x18005cecc  push    rdi
0x18005cecd  push    r12
0x18005cecf  push    r13
0x18005ced1  push    r14
0x18005ced3  push    r15
0x18005ced5  lea     rbp, [rsp-1Fh]
0x18005ceda  sub     rsp, 0D8h
0x18005cee1  mov     rax, cs:__security_cookie
0x18005cee8  xor     rax, rsp
0x18005ceeb  mov     [rbp+57h+var_48], rax
0x18005ceef  xorps   xmm0, xmm0
0x18005cef2  xorps   xmm1, xmm1
0x18005cef5  xor     r12d, r12d
0x18005cef8  mov     rbx, rdx
0x18005cefb  mov     [rbp+57h+var_D0], r12
0x18005ceff  mov     rdi, rcx
0x18005cf02  movups  [rbp+57h+var_C8], xmm0
0x18005cf06  movups  [rbp+57h+var_B8], xmm0
0x18005cf0a  movups  [rbp+57h+var_A0], xmm1
0x18005cf0e  movups  [rbp+57h+var_90], xmm1
0x18005cf12  call    ExecuteHotpatchTestRuntimeFunction
0x18005cf17  xor     eax, eax
0x18005cf19  mov     [rbp+57h+var_A8], 31h ; '1'
0x18005cf21  xorps   xmm0, xmm0
0x18005cf24  mov     [rbp+57h+var_50], al
0x18005cf27  mov     eax, cs:g_TrustedEnvironment
0x18005cf2d  movups  [rbp+57h+var_80], xmm0
0x18005cf31  movups  [rbp+57h+var_70], xmm0
0x18005cf35  movups  [rbp+57h+var_60], xmm0
0x18005cf39  test    eax, eax
0x18005cf3b  jnz     short loc_18005CF42
0x18005cf3d  call    GetTrustedEnvironment
0x18005cf42  mov     r13d, 1
0x18005cf48  test    al, 2
0x18005cf4a  jz      short loc_18005CF62
0x18005cf4c  test    rdi, rdi
0x18005cf4f  jnz     short loc_18005CF5A
0x18005cf51  test    rbx, rbx
0x18005cf54  jz      loc_18005D12D
0x18005cf5a  mov     ebx, r12d
0x18005cf5d  jmp     loc_18005D34B
0x18005cf62  lea     rax, aDeviceCng; "\\Device\\CNG"
0x18005cf69  mov     qword ptr cs:DeviceName.Length, 180016h
0x18005cf74  mov     cs:DeviceName.Buffer, rax
0x18005cf7b  lea     rdx, ?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005cf82  lea     rax, [rdi+38h]
0x18005cf86  mov     dword ptr [rbp+57h+var_A0+1], r12d
0x18005cf8a  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18005cf8e  lea     rcx, [rbp+57h+var_A0]
0x18005cf92  lea     rax, CngSiloCreateNotify
0x18005cf99  mov     word ptr [rbp+57h+var_A0+5], r12w
0x18005cf9e  mov     qword ptr [rbp+57h+var_90], rax
0x18005cfa2  lea     rax, CngSiloTerminateNotify
0x18005cfa9  mov     qword ptr [rbp+57h+var_90+8], rax
0x18005cfad  mov     byte ptr [rbp+57h+var_A0+7], r12b
0x18005cfb1  mov     byte ptr [rbp+57h+var_A0], r13b
0x18005cfb5  call    cs:__imp_PsRegisterSiloMonitor
0x18005cfbc  nop     dword ptr [rax+rax+00h]
0x18005cfc1  mov     ebx, eax
0x18005cfc3  test    eax, eax
0x18005cfc5  jns     short loc_18005CFE7
0x18005cfc7  mov     r9d, 1B8h
0x18005cfcd  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cfd4  mov     ecx, eax
0x18005cfd6  lea     rdx, aStatus; "Status"
0x18005cfdd  call    DebugTraceError
0x18005cfe2  jmp     loc_18005D34B
0x18005cfe7  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005cfee  call    cs:__imp_PsGetSiloMonitorContextSlot
0x18005cff5  nop     dword ptr [rax+rax+00h]
0x18005cffa  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005d001  mov     cs:g_SiloSlot, eax
0x18005d007  call    cs:__imp_PsStartSiloMonitor
0x18005d00e  nop     dword ptr [rax+rax+00h]
0x18005d013  mov     ebx, eax
0x18005d015  test    eax, eax
0x18005d017  jns     short loc_18005D021
0x18005d019  mov     r9d, 1C5h
0x18005d01f  jmp     short loc_18005CFCD
0x18005d021  lea     rax, WPP_ThisDir_CTLGUID_CNGTraceControlGuid
0x18005d028  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x18005d02f  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x18005d036  mov     cs:WPP_MAIN_CB.NextDevice, r12
0x18005d03d  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x18005d044  mov     cs:WPP_MAIN_CB.Timer, r13
0x18005d04b  call    WppLoadTracingSupport
0x18005d050  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x18005d057  call    WppInitKm
0x18005d05c  lea     rax, CngDispatch
0x18005d063  mov     r9d, 3Fh ; '?'; DeviceType
0x18005d069  mov     [rdi+70h], rax
0x18005d06d  lea     r8, DeviceName; DeviceName
0x18005d074  mov     [rdi+80h], rax
0x18005d07b  xor     edx, edx; DeviceExtensionSize
0x18005d07d  mov     [rdi+88h], rax
0x18005d084  mov     rcx, rdi; DriverObject
0x18005d087  mov     [rdi+90h], rax
0x18005d08e  mov     [rdi+98h], rax
0x18005d095  mov     [rdi+0C0h], rax
0x18005d09c  mov     [rdi+0E0h], rax
0x18005d0a3  lea     rax, [rbp+57h+var_D0]
0x18005d0a7  mov     [rsp+110h+DeviceObject], rax; DeviceObject
0x18005d0ac  mov     [rsp+110h+Exclusive], r12b; Exclusive
0x18005d0b1  mov     [rsp+110h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x18005d0b9  call    cs:__imp_IoCreateDevice
0x18005d0c0  nop     dword ptr [rax+rax+00h]
0x18005d0c5  mov     ebx, eax
0x18005d0c7  test    eax, eax
0x18005d0c9  jns     short loc_18005D0D6
0x18005d0cb  mov     r9d, 1F2h
0x18005d0d1  jmp     loc_18005CFCD
0x18005d0d6  call    cs:__imp_PsGetHostSilo
0x18005d0dd  nop     dword ptr [rax+rax+00h]
0x18005d0e2  mov     rcx, rax; struct _EJOB *
0x18005d0e5  call    InitializeTlsConfig
0x18005d0ea  mov     ebx, eax
0x18005d0ec  test    eax, eax
0x18005d0ee  jns     short loc_18005D0FD
0x18005d0f0  mov     r9d, 1F9h
0x18005d0f6  mov     ecx, eax
0x18005d0f8  jmp     loc_18005D323
0x18005d0fd  cmp     cs:byte_1800CB768, r12b
0x18005d104  jnz     short loc_18005D116
0x18005d106  call    TlgRegisterAggregateProvider
0x18005d10b  test    eax, eax
0x18005d10d  jnz     short loc_18005D116
0x18005d10f  mov     cs:byte_1800CB768, r13b
0x18005d116  mov     rcx, [rbp+57h+var_D0]
0x18005d11a  call    CngSetDeviceSecurity
0x18005d11f  mov     ebx, eax
0x18005d121  test    eax, eax
0x18005d123  jns     short loc_18005D12D
0x18005d125  mov     r9d, 202h
0x18005d12b  jmp     short loc_18005D0F6
0x18005d12d  call    SymCryptInitEnvWindowsKernelmodeWin8_1nLater
0x18005d132  mov     eax, cs:g_TrustedEnvironment
0x18005d138  test    eax, eax
0x18005d13a  jnz     short loc_18005D141
0x18005d13c  call    GetTrustedEnvironment
0x18005d141  test    al, 2
0x18005d143  jnz     short loc_18005D178
0x18005d145  xor     r8d, r8d; State
0x18005d148  mov     cs:CngEncryptMemMutex.Count, r13d
0x18005d14f  mov     edx, r13d; Type
0x18005d152  mov     cs:CngEncryptMemMutex.Owner, r12
0x18005d159  lea     rcx, CngEncryptMemMutex.Event; Event
0x18005d160  mov     cs:CngEncryptMemMutex.Contention, r12d
0x18005d167  mov     rbx, r12
0x18005d16a  call    cs:__imp_KeInitializeEvent
0x18005d171  nop     dword ptr [rax+rax+00h]
0x18005d176  jmp     short loc_18005D19D
0x18005d178  lea     r8, [rbp+57h+var_A8]
0x18005d17c  mov     ecx, 2
0x18005d181  lea     rdx, [rbp+57h+var_80]
0x18005d185  call    cs:__imp_SkQuerySecureKernelInformation
0x18005d18c  nop     dword ptr [rax+rax+00h]
0x18005d191  test    eax, eax
0x18005d193  js      loc_18005D313
0x18005d199  lea     rbx, [rbp+57h+var_80]
0x18005d19d  mov     cs:g_fSteEnabled, r13b
0x18005d1a4  mov     cs:g_fSelftest, r13b
0x18005d1ab  call    SymCryptRngAesInstantiateSelftest
0x18005d1b0  call    SymCryptRngAesReseedSelftest
0x18005d1b5  call    SymCryptRngAesGenerateSelftest
0x18005d1ba  mov     rdx, rbx
0x18005d1bd  mov     rcx, rdi; DriverObject
0x18005d1c0  call    InitializeMasterPrngSystem
0x18005d1c5  mov     ebx, eax
0x18005d1c7  test    eax, eax
0x18005d1c9  jns     short loc_18005D1D6
0x18005d1cb  mov     r9d, 25Bh
0x18005d1d1  jmp     loc_18005D0F6
0x18005d1d6  call    InitializeCNG
0x18005d1db  mov     ebx, eax
0x18005d1dd  test    eax, eax
0x18005d1df  jns     short loc_18005D257
0x18005d1e1  mov     r9d, 262h
0x18005d1e7  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d1ee  lea     rdx, aStatus; "Status"
0x18005d1f5  mov     ecx, eax
0x18005d1f7  call    DebugTraceError
0x18005d1fc  mov     rsi, r12
0x18005d1ff  lea     r15, g_AesStatesTable
0x18005d206  mov     r15, [r15+rsi*8]
0x18005d20a  test    r15, r15
0x18005d20d  jz      short loc_18005D23D
0x18005d20f  mov     rdi, r12
0x18005d212  mov     r14, [r15+rdi*8]
0x18005d216  test    r14, r14
0x18005d219  jz      short loc_18005D22C
0x18005d21b  lea     rcx, [r14+10h]
0x18005d21f  call    SymCryptRngAesUninstantiate
0x18005d224  mov     rcx, r14; P
0x18005d227  call    BCryptFree
0x18005d22c  add     rdi, r13
0x18005d22f  cmp     rdi, 40h ; '@'
0x18005d233  jnz     short loc_18005D212
0x18005d235  mov     rcx, r15; P
0x18005d238  call    BCryptFree
0x18005d23d  inc     rsi
0x18005d240  cmp     rsi, 40h ; '@'
0x18005d244  jnz     short loc_18005D1FF
0x18005d246  lea     rcx, qword_1800CA630
0x18005d24d  call    SymCryptRngAesUninstantiate
0x18005d252  jmp     loc_18005D336
0x18005d257  mov     eax, cs:g_TrustedEnvironment
0x18005d25d  test    eax, eax
0x18005d25f  jnz     short loc_18005D266
0x18005d261  call    GetTrustedEnvironment
0x18005d266  test    al, 2
0x18005d268  jnz     loc_18005D2F0
0x18005d26e  xor     edx, edx; Remove
0x18005d270  lea     rcx, CngCreateProcessNotifyRoutine; NotifyRoutine
0x18005d277  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x18005d27e  nop     dword ptr [rax+rax+00h]
0x18005d283  test    eax, eax
0x18005d285  jns     short loc_18005D2B3
0x18005d287  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d28e  lea     rdx, WPP_GLOBAL_Control
0x18005d295  cmp     rcx, rdx
0x18005d298  jz      short loc_18005D2B3
0x18005d29a  mov     edx, [rcx+2Ch]
0x18005d29d  test    dl, 2
0x18005d2a0  jz      short loc_18005D2B3
0x18005d2a2  mov     rcx, [rcx+18h]
0x18005d2a6  mov     edx, 0Ah
0x18005d2ab  mov     r9d, eax
0x18005d2ae  call    WPP_SF_D
0x18005d2b3  lea     rax, off_1800A7220
0x18005d2ba  mov     dword ptr [rbp+57h+var_C8], 10003h
0x18005d2c1  lea     r8, [rbp+57h+var_C8]
0x18005d2c5  mov     qword ptr [rbp+57h+var_C8+8], rax
0x18005d2c9  mov     edx, 10001h
0x18005d2ce  mov     dword ptr [rbp+57h+var_C8+4], 240000h
0x18005d2d5  lea     rcx, CngExtensionRegistration
0x18005d2dc  mov     qword ptr [rbp+57h+var_B8], r12
0x18005d2e0  mov     qword ptr [rbp+57h+var_B8+8], rdi
0x18005d2e4  call    cs:__imp_ExRegisterExtension
0x18005d2eb  nop     dword ptr [rax+rax+00h]
0x18005d2f0  xor     eax, eax
0x18005d2f2  mov     rcx, [rbp+57h+var_48]
0x18005d2f6  xor     rcx, rsp; StackCookie
0x18005d2f9  call    __security_check_cookie
0x18005d2fe  add     rsp, 0D8h
0x18005d305  pop     r15
0x18005d307  pop     r14
0x18005d309  pop     r13
0x18005d30b  pop     r12
0x18005d30d  pop     rdi
0x18005d30e  pop     rsi
0x18005d30f  pop     rbx
0x18005d310  pop     rbp
0x18005d311  retn
0x18005d313  mov     ebx, 0C00000E5h
0x18005d318  mov     r9d, 22Fh
0x18005d31e  mov     ecx, 0C00000E5h
0x18005d323  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d32a  lea     rdx, aStatus; "Status"
0x18005d331  call    DebugTraceError
0x18005d336  mov     rcx, [rbp+57h+var_D0]; DeviceObject
0x18005d33a  test    rcx, rcx
0x18005d33d  jz      short loc_18005D34B
0x18005d33f  call    cs:__imp_IoDeleteDevice
0x18005d346  nop     dword ptr [rax+rax+00h]
0x18005d34b  cmp     cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA, r12; _SILO_MONITOR * CngSiloMonitor
0x18005d352  jz      short loc_18005D381
0x18005d354  mov     eax, cs:g_TrustedEnvironment
0x18005d35a  test    eax, eax
0x18005d35c  jnz     short loc_18005D363
0x18005d35e  call    GetTrustedEnvironment
0x18005d363  test    al, 2
0x18005d365  jnz     short loc_18005D381
0x18005d367  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18005d36e  call    cs:__imp_PsUnregisterSiloMonitor
0x18005d375  nop     dword ptr [rax+rax+00h]
0x18005d37a  mov     cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA, r12; _SILO_MONITOR * CngSiloMonitor
0x18005d381  movsxd  rdx, ebx; BugCheckParameter1
0x18005d384  xor     r9d, r9d; BugCheckParameter3
0x18005d387  xor     r8d, r8d; BugCheckParameter2
0x18005d38a  mov     qword ptr [rsp+110h+DeviceCharacteristics], r12; BugCheckParameter4
0x18005d38f  mov     ecx, 121h; BugCheckCode
0x18005d394  call    cs:__imp_KeBugCheckEx
```
