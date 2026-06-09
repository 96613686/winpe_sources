# DriverEntry

- ea: `0x180067098`
- end: `0x180067571`
- name: `DriverEntry`
- size: `1241`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800df010`

## callees

- `0x18001155c`
- `0x180025ec0`
- `0x18002eb64`
- `0x18003de2c`
- `0x18003dedc`
- `0x1800503f8`
- `0x180056480`
- `0x180060308`
- `0x180066f7c`
- `0x180067098`
- `0x180067578`
- `0x180067c78`
- `0x1800692b8`
- `0x18006dd20`
- `0x18006de90`
- `0x1800a4260`
- `0x1800a916c`
- `0x1800a9200`
- `0x1800a9ee8`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x180067564`
- `ntoskrnl!KeBugCheckEx` at `0x180067564`
- `ntoskrnl!SkQuerySecureKernelInformation` at `0x180067355`
- `ntoskrnl!SkQuerySecureKernelInformation` at `0x180067355`
- `ntoskrnl!PsGetHostSilo` at `0x1800672a6`
- `ntoskrnl!PsGetHostSilo` at `0x1800672a6`
- `ntoskrnl!IoDeleteDevice` at `0x18006750f`
- `ntoskrnl!IoDeleteDevice` at `0x18006750f`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18006753e`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18006753e`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1800671be`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1800671be`
- `ntoskrnl!ExRegisterExtension` at `0x1800674b4`
- `ntoskrnl!ExRegisterExtension` at `0x1800674b4`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x180067185`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x180067185`
- `ntoskrnl!PsStartSiloMonitor` at `0x1800671d7`
- `ntoskrnl!PsStartSiloMonitor` at `0x1800671d7`
- `ntoskrnl!IoCreateDevice` at `0x180067289`
- `ntoskrnl!IoCreateDevice` at `0x180067289`
- `ntoskrnl!KeInitializeEvent` at `0x18006733a`
- `ntoskrnl!KeInitializeEvent` at `0x18006733a`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x180067447`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x180067447`

## string_xrefs

- `0x18006719d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800673b7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`
- `0x1800674f3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

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
        DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&CngDispatch;
        DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&CngDispatch;
        DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)&CngDispatch;
        DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&CngDispatch;
        DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)&CngDispatch;
        DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)&CngDispatch;
        DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&CngDispatch;
        started = IoCreateDevice(DriverObject, 0, &DeviceName, 0x3Fu, 0x100u, 0, &DeviceObject);
        v5 = started;
        if ( started >= 0 )
        {
          HostSilo = (struct _EJOB *)PsGetHostSilo();
          v9 = InitializeTlsConfig(HostSilo);
          v5 = v9;
          if ( v9 >= 0 )
          {
            if ( !byte_1800D37A8 )
              byte_1800D37A8 = (unsigned int)TlgRegisterAggregateProvider() == 0;
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
    SymCryptRngAesUninstantiate(qword_1800D2670);
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
    *((_QWORD *)&v24 + 1) = off_1800AE810;
    *(_QWORD *)&v25 = 0;
    *((_QWORD *)&v25 + 1) = DriverObject;
    ExRegisterExtension(CngExtensionRegistration, 65537, &v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180067098  push    rbp
0x18006709a  push    rbx
0x18006709b  push    rsi
0x18006709c  push    rdi
0x18006709d  push    r12
0x18006709f  push    r13
0x1800670a1  push    r14
0x1800670a3  push    r15
0x1800670a5  lea     rbp, [rsp-1Fh]
0x1800670aa  sub     rsp, 0D8h
0x1800670b1  mov     rax, cs:__security_cookie
0x1800670b8  xor     rax, rsp
0x1800670bb  mov     [rbp+57h+var_48], rax
0x1800670bf  xorps   xmm0, xmm0
0x1800670c2  xorps   xmm1, xmm1
0x1800670c5  xor     r12d, r12d
0x1800670c8  mov     rbx, rdx
0x1800670cb  mov     [rbp+57h+var_D0], r12
0x1800670cf  mov     rdi, rcx
0x1800670d2  movups  [rbp+57h+var_C8], xmm0
0x1800670d6  movups  [rbp+57h+var_B8], xmm0
0x1800670da  movups  [rbp+57h+var_A0], xmm1
0x1800670de  movups  [rbp+57h+var_90], xmm1
0x1800670e2  call    ExecuteHotpatchTestRuntimeFunction
0x1800670e7  xor     eax, eax
0x1800670e9  mov     [rbp+57h+var_A8], 31h ; '1'
0x1800670f1  xorps   xmm0, xmm0
0x1800670f4  mov     [rbp+57h+var_50], al
0x1800670f7  mov     eax, cs:g_TrustedEnvironment
0x1800670fd  movups  [rbp+57h+var_80], xmm0
0x180067101  movups  [rbp+57h+var_70], xmm0
0x180067105  movups  [rbp+57h+var_60], xmm0
0x180067109  test    eax, eax
0x18006710b  jnz     short loc_180067112
0x18006710d  call    GetTrustedEnvironment
0x180067112  mov     r13d, 1
0x180067118  test    al, 2
0x18006711a  jz      short loc_180067132
0x18006711c  test    rdi, rdi
0x18006711f  jnz     short loc_18006712A
0x180067121  test    rbx, rbx
0x180067124  jz      loc_1800672FD
0x18006712a  mov     ebx, r12d
0x18006712d  jmp     loc_18006751B
0x180067132  lea     rax, aDeviceCng; "\\Device\\CNG"
0x180067139  mov     qword ptr cs:DeviceName.Length, 180016h
0x180067144  mov     cs:DeviceName.Buffer, rax
0x18006714b  lea     rdx, ?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x180067152  lea     rax, [rdi+38h]
0x180067156  mov     dword ptr [rbp+57h+var_A0+1], r12d
0x18006715a  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18006715e  lea     rcx, [rbp+57h+var_A0]
0x180067162  lea     rax, CngSiloCreateNotify
0x180067169  mov     word ptr [rbp+57h+var_A0+5], r12w
0x18006716e  mov     qword ptr [rbp+57h+var_90], rax
0x180067172  lea     rax, CngSiloTerminateNotify
0x180067179  mov     qword ptr [rbp+57h+var_90+8], rax
0x18006717d  mov     byte ptr [rbp+57h+var_A0+7], r12b
0x180067181  mov     byte ptr [rbp+57h+var_A0], r13b
0x180067185  call    cs:__imp_PsRegisterSiloMonitor
0x18006718c  nop     dword ptr [rax+rax+00h]
0x180067191  mov     ebx, eax
0x180067193  test    eax, eax
0x180067195  jns     short loc_1800671B7
0x180067197  mov     r9d, 1B8h
0x18006719d  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800671a4  mov     ecx, eax
0x1800671a6  lea     rdx, aStatus; "Status"
0x1800671ad  call    DebugTraceError
0x1800671b2  jmp     loc_18006751B
0x1800671b7  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x1800671be  call    cs:__imp_PsGetSiloMonitorContextSlot
0x1800671c5  nop     dword ptr [rax+rax+00h]
0x1800671ca  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x1800671d1  mov     cs:g_SiloSlot, eax
0x1800671d7  call    cs:__imp_PsStartSiloMonitor
0x1800671de  nop     dword ptr [rax+rax+00h]
0x1800671e3  mov     ebx, eax
0x1800671e5  test    eax, eax
0x1800671e7  jns     short loc_1800671F1
0x1800671e9  mov     r9d, 1C5h
0x1800671ef  jmp     short loc_18006719D
0x1800671f1  lea     rax, WPP_ThisDir_CTLGUID_CNGTraceControlGuid
0x1800671f8  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x1800671ff  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x180067206  mov     cs:WPP_MAIN_CB.NextDevice, r12
0x18006720d  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x180067214  mov     cs:WPP_MAIN_CB.Timer, r13
0x18006721b  call    WppLoadTracingSupport
0x180067220  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x180067227  call    WppInitKm
0x18006722c  lea     rax, CngDispatch
0x180067233  mov     r9d, 3Fh ; '?'; DeviceType
0x180067239  mov     [rdi+70h], rax
0x18006723d  lea     r8, DeviceName; DeviceName
0x180067244  mov     [rdi+80h], rax
0x18006724b  xor     edx, edx; DeviceExtensionSize
0x18006724d  mov     [rdi+88h], rax
0x180067254  mov     rcx, rdi; DriverObject
0x180067257  mov     [rdi+90h], rax
0x18006725e  mov     [rdi+98h], rax
0x180067265  mov     [rdi+0C0h], rax
0x18006726c  mov     [rdi+0E0h], rax
0x180067273  lea     rax, [rbp+57h+var_D0]
0x180067277  mov     [rsp+110h+DeviceObject], rax; DeviceObject
0x18006727c  mov     [rsp+110h+Exclusive], r12b; Exclusive
0x180067281  mov     [rsp+110h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x180067289  call    cs:__imp_IoCreateDevice
0x180067290  nop     dword ptr [rax+rax+00h]
0x180067295  mov     ebx, eax
0x180067297  test    eax, eax
0x180067299  jns     short loc_1800672A6
0x18006729b  mov     r9d, 1F2h
0x1800672a1  jmp     loc_18006719D
0x1800672a6  call    cs:__imp_PsGetHostSilo
0x1800672ad  nop     dword ptr [rax+rax+00h]
0x1800672b2  mov     rcx, rax; struct _EJOB *
0x1800672b5  call    InitializeTlsConfig
0x1800672ba  mov     ebx, eax
0x1800672bc  test    eax, eax
0x1800672be  jns     short loc_1800672CD
0x1800672c0  mov     r9d, 1F9h
0x1800672c6  mov     ecx, eax
0x1800672c8  jmp     loc_1800674F3
0x1800672cd  cmp     cs:byte_1800D37A8, r12b
0x1800672d4  jnz     short loc_1800672E6
0x1800672d6  call    TlgRegisterAggregateProvider
0x1800672db  test    eax, eax
0x1800672dd  jnz     short loc_1800672E6
0x1800672df  mov     cs:byte_1800D37A8, r13b
0x1800672e6  mov     rcx, [rbp+57h+var_D0]
0x1800672ea  call    CngSetDeviceSecurity
0x1800672ef  mov     ebx, eax
0x1800672f1  test    eax, eax
0x1800672f3  jns     short loc_1800672FD
0x1800672f5  mov     r9d, 202h
0x1800672fb  jmp     short loc_1800672C6
0x1800672fd  call    SymCryptInitEnvWindowsKernelmodeWin8_1nLater
0x180067302  mov     eax, cs:g_TrustedEnvironment
0x180067308  test    eax, eax
0x18006730a  jnz     short loc_180067311
0x18006730c  call    GetTrustedEnvironment
0x180067311  test    al, 2
0x180067313  jnz     short loc_180067348
0x180067315  xor     r8d, r8d; State
0x180067318  mov     cs:CngEncryptMemMutex.Count, r13d
0x18006731f  mov     edx, r13d; Type
0x180067322  mov     cs:CngEncryptMemMutex.Owner, r12
0x180067329  lea     rcx, CngEncryptMemMutex.Event; Event
0x180067330  mov     cs:CngEncryptMemMutex.Contention, r12d
0x180067337  mov     rbx, r12
0x18006733a  call    cs:__imp_KeInitializeEvent
0x180067341  nop     dword ptr [rax+rax+00h]
0x180067346  jmp     short loc_18006736D
0x180067348  lea     r8, [rbp+57h+var_A8]
0x18006734c  mov     ecx, 2
0x180067351  lea     rdx, [rbp+57h+var_80]
0x180067355  call    cs:__imp_SkQuerySecureKernelInformation
0x18006735c  nop     dword ptr [rax+rax+00h]
0x180067361  test    eax, eax
0x180067363  js      loc_1800674E3
0x180067369  lea     rbx, [rbp+57h+var_80]
0x18006736d  mov     cs:g_fSteEnabled, r13b
0x180067374  mov     cs:g_fSelftest, r13b
0x18006737b  call    SymCryptRngAesInstantiateSelftest
0x180067380  call    SymCryptRngAesReseedSelftest
0x180067385  call    SymCryptRngAesGenerateSelftest
0x18006738a  mov     rdx, rbx
0x18006738d  mov     rcx, rdi; DriverObject
0x180067390  call    InitializeMasterPrngSystem
0x180067395  mov     ebx, eax
0x180067397  test    eax, eax
0x180067399  jns     short loc_1800673A6
0x18006739b  mov     r9d, 25Bh
0x1800673a1  jmp     loc_1800672C6
0x1800673a6  call    InitializeCNG
0x1800673ab  mov     ebx, eax
0x1800673ad  test    eax, eax
0x1800673af  jns     short loc_180067427
0x1800673b1  mov     r9d, 262h
0x1800673b7  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800673be  lea     rdx, aStatus; "Status"
0x1800673c5  mov     ecx, eax
0x1800673c7  call    DebugTraceError
0x1800673cc  mov     rsi, r12
0x1800673cf  lea     r15, g_AesStatesTable
0x1800673d6  mov     r15, [r15+rsi*8]
0x1800673da  test    r15, r15
0x1800673dd  jz      short loc_18006740D
0x1800673df  mov     rdi, r12
0x1800673e2  mov     r14, [r15+rdi*8]
0x1800673e6  test    r14, r14
0x1800673e9  jz      short loc_1800673FC
0x1800673eb  lea     rcx, [r14+10h]
0x1800673ef  call    SymCryptRngAesUninstantiate
0x1800673f4  mov     rcx, r14; P
0x1800673f7  call    BCryptFree
0x1800673fc  add     rdi, r13
0x1800673ff  cmp     rdi, 40h ; '@'
0x180067403  jnz     short loc_1800673E2
0x180067405  mov     rcx, r15; P
0x180067408  call    BCryptFree
0x18006740d  inc     rsi
0x180067410  cmp     rsi, 40h ; '@'
0x180067414  jnz     short loc_1800673CF
0x180067416  lea     rcx, qword_1800D2670
0x18006741d  call    SymCryptRngAesUninstantiate
0x180067422  jmp     loc_180067506
0x180067427  mov     eax, cs:g_TrustedEnvironment
0x18006742d  test    eax, eax
0x18006742f  jnz     short loc_180067436
0x180067431  call    GetTrustedEnvironment
0x180067436  test    al, 2
0x180067438  jnz     loc_1800674C0
0x18006743e  xor     edx, edx; Remove
0x180067440  lea     rcx, CngCreateProcessNotifyRoutine; NotifyRoutine
0x180067447  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x18006744e  nop     dword ptr [rax+rax+00h]
0x180067453  test    eax, eax
0x180067455  jns     short loc_180067483
0x180067457  mov     rcx, cs:WPP_GLOBAL_Control
0x18006745e  lea     rdx, WPP_GLOBAL_Control
0x180067465  cmp     rcx, rdx
0x180067468  jz      short loc_180067483
0x18006746a  mov     edx, [rcx+2Ch]
0x18006746d  test    dl, 2
0x180067470  jz      short loc_180067483
0x180067472  mov     rcx, [rcx+18h]
0x180067476  mov     edx, 0Ah
0x18006747b  mov     r9d, eax
0x18006747e  call    WPP_SF_D
0x180067483  lea     rax, off_1800AE810
0x18006748a  mov     dword ptr [rbp+57h+var_C8], 10003h
0x180067491  lea     r8, [rbp+57h+var_C8]
0x180067495  mov     qword ptr [rbp+57h+var_C8+8], rax
0x180067499  mov     edx, 10001h
0x18006749e  mov     dword ptr [rbp+57h+var_C8+4], 240000h
0x1800674a5  lea     rcx, CngExtensionRegistration
0x1800674ac  mov     qword ptr [rbp+57h+var_B8], r12
0x1800674b0  mov     qword ptr [rbp+57h+var_B8+8], rdi
0x1800674b4  call    cs:__imp_ExRegisterExtension
0x1800674bb  nop     dword ptr [rax+rax+00h]
0x1800674c0  xor     eax, eax
0x1800674c2  mov     rcx, [rbp+57h+var_48]
0x1800674c6  xor     rcx, rsp; StackCookie
0x1800674c9  call    __security_check_cookie
0x1800674ce  add     rsp, 0D8h
0x1800674d5  pop     r15
0x1800674d7  pop     r14
0x1800674d9  pop     r13
0x1800674db  pop     r12
0x1800674dd  pop     rdi
0x1800674de  pop     rsi
0x1800674df  pop     rbx
0x1800674e0  pop     rbp
0x1800674e1  retn
0x1800674e3  mov     ebx, 0C00000E5h
0x1800674e8  mov     r9d, 22Fh
0x1800674ee  mov     ecx, 0C00000E5h
0x1800674f3  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800674fa  lea     rdx, aStatus; "Status"
0x180067501  call    DebugTraceError
0x180067506  mov     rcx, [rbp+57h+var_D0]; DeviceObject
0x18006750a  test    rcx, rcx
0x18006750d  jz      short loc_18006751B
0x18006750f  call    cs:__imp_IoDeleteDevice
0x180067516  nop     dword ptr [rax+rax+00h]
0x18006751b  cmp     cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA, r12; _SILO_MONITOR * CngSiloMonitor
0x180067522  jz      short loc_180067551
0x180067524  mov     eax, cs:g_TrustedEnvironment
0x18006752a  test    eax, eax
0x18006752c  jnz     short loc_180067533
0x18006752e  call    GetTrustedEnvironment
0x180067533  test    al, 2
0x180067535  jnz     short loc_180067551
0x180067537  mov     rcx, cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * CngSiloMonitor
0x18006753e  call    cs:__imp_PsUnregisterSiloMonitor
0x180067545  nop     dword ptr [rax+rax+00h]
0x18006754a  mov     cs:?CngSiloMonitor@@3PEAU_SILO_MONITOR@@EA, r12; _SILO_MONITOR * CngSiloMonitor
0x180067551  movsxd  rdx, ebx; BugCheckParameter1
0x180067554  xor     r9d, r9d; BugCheckParameter3
0x180067557  xor     r8d, r8d; BugCheckParameter2
0x18006755a  mov     qword ptr [rsp+110h+DeviceCharacteristics], r12; BugCheckParameter4
0x18006755f  mov     ecx, 121h; BugCheckCode
0x180067564  call    cs:__imp_KeBugCheckEx
```
