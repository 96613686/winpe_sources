# DriverEntry

- ea: `0x140419008`
- end: `0x1404197a8`
- name: `DriverEntry`
- size: `1952`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1404197b0`

## callees

- `0x140006270`
- `0x1400091f0`
- `0x14000d990`
- `0x140012cd4`
- `0x140013a20`
- `0x14001b9c0`
- `0x14001d214`
- `0x1400629d0`
- `0x14007320c`
- `0x140073e08`
- `0x1400a0764`
- `0x14023b524`
- `0x14023ec74`
- `0x14023f13c`
- `0x14026d9d4`
- `0x140270138`
- `0x1402a83d8`
- `0x1402a84a4`
- `0x1402ef0d8`
- `0x1402f4f2c`
- `0x14030e1b8`
- `0x140401d58`
- `0x140419008`
- `0x140419818`
- `0x1404199c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1404192d5`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1404192d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140419484`
- `ntoskrnl!RtlInitUnicodeString` at `0x1404194eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140419484`
- `ntoskrnl!RtlInitUnicodeString` at `0x1404194eb`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14041971d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14041971d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14041916e`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14041916e`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14041937d`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14041937d`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140419243`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140419243`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1404190bc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1404190bc`
- `ntoskrnl!PsTlsAlloc` at `0x1404190d8`
- `ntoskrnl!PsTlsAlloc` at `0x1404190d8`
- `ntoskrnl!PsTlsFree` at `0x140419187`
- `ntoskrnl!PsTlsFree` at `0x14041970a`
- `ntoskrnl!PsTlsFree` at `0x140419187`
- `ntoskrnl!PsTlsFree` at `0x14041970a`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x1404191c9`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x1404191c9`
- `ntoskrnl!RtlGetSuiteMask` at `0x1404192f7`
- `ntoskrnl!RtlGetSuiteMask` at `0x1404192f7`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140419642`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140419642`
- `ntoskrnl!IoDeleteDevice` at `0x1404196d0`
- `ntoskrnl!IoDeleteDevice` at `0x1404196d0`
- `watchdog!WdDiagInit` at `0x140419466`
- `watchdog!WdDiagInit` at `0x140419466`
- `watchdog!SMgrUnregisterSessionChangeCallout` at `0x1404196ae`
- `watchdog!SMgrUnregisterSessionChangeCallout` at `0x1404196ae`
- `watchdog!SMgrRegisterSessionChangeCallout` at `0x1404195d8`
- `watchdog!SMgrRegisterSessionChangeCallout` at `0x1404195d8`
- `watchdog!WdInitialize` at `0x14041931f`
- `watchdog!WdInitialize` at `0x14041931f`
- `watchdog!WdLogSingleEntry0` at `0x140419056`
- `watchdog!WdLogSingleEntry0` at `0x140419056`
- `watchdog!WdLogSingleEntry1` at `0x1404190f3`
- `watchdog!WdLogSingleEntry1` at `0x14041919b`
- `watchdog!WdLogSingleEntry1` at `0x1404191e4`
- `watchdog!WdLogSingleEntry1` at `0x140419398`
- `watchdog!WdLogSingleEntry1` at `0x140419544`
- `watchdog!WdLogSingleEntry1` at `0x140419573`
- `watchdog!WdLogSingleEntry1` at `0x1404195a2`
- `watchdog!WdLogSingleEntry1` at `0x1404195f3`
- `watchdog!WdLogSingleEntry1` at `0x140419661`
- `watchdog!WdLogSingleEntry1` at `0x1404190f3`
- `watchdog!WdLogSingleEntry1` at `0x14041919b`
- `watchdog!WdLogSingleEntry1` at `0x1404191e4`
- `watchdog!WdLogSingleEntry1` at `0x140419398`
- `watchdog!WdLogSingleEntry1` at `0x140419544`
- `watchdog!WdLogSingleEntry1` at `0x140419573`
- `watchdog!WdLogSingleEntry1` at `0x1404195a2`
- `watchdog!WdLogSingleEntry1` at `0x1404195f3`
- `watchdog!WdLogSingleEntry1` at `0x140419661`

## string_xrefs

- `0x140419067`: `Failed to allocate registry path buffer.`
- `0x1404191a7`: `Failed to initialize the lookaside list for DXGTHREAD, returning 0x%I64x`
- `0x1404190ff`: `Failed to allocate a PsTls slot for DxgkThread, returning 0x%I64x.`
- `0x1404191f5`: `PsSetCreateProcessNotifyRoutineEx failed 0x%I64x`
- `0x1404193a9`: `ExSubscribeWnfStateChange failed, returing 0x%I64x`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  int v5; // eax
  __int64 v6; // rdi
  const wchar_t *v7; // r9
  NTSTATUS v8; // eax
  int ProcessNotifyRoutineEx2; // eax
  __int64 v10; // rbx
  unsigned __int8 v11; // al
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // r8
  NTSTATUS v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  NTSTATUS v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // r8
  BOOLEAN Size; // [rsp+28h] [rbp-D8h]
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h]
  char v29; // [rsp+60h] [rbp-A0h]
  _QWORD v30[2]; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING DefaultSDDLString; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+A8h] [rbp-58h]
  const wchar_t *v35; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v36; // [rsp+B8h] [rbp-48h]
  int v37; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  int v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int128 v43; // [rsp+F0h] [rbp-10h]
  __int128 v44; // [rsp+100h] [rbp+0h]
  __int64 SystemInformation; // [rsp+130h] [rbp+30h] BYREF

  g_pDriverObject = (PDEVICE_OBJECT)DriverObject;
  g_RegistryPath.Buffer = (wchar_t *)operator new[](RegistryPath->MaximumLength, 1265072196, 256);
  if ( !g_RegistryPath.Buffer )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 306;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to allocate registry path buffer.",
      306,
      0,
      0,
      0,
      0);
    return -1073741801;
  }
  g_RegistryPath.MaximumLength = RegistryPath->MaximumLength;
  RtlCopyUnicodeString(&g_RegistryPath, RegistryPath);
  v5 = PsTlsAlloc(DxgkThreadPsTslCallback, 0, &g_DxgkThreadTlsId);
  v6 = v5;
  if ( v5 < 0 )
  {
    WdLogSingleEntry1(2, v5);
    v7 = L"Failed to allocate a PsTls slot for DxgkThread, returning 0x%I64x.";
    WdLogGlobalForLineNumber = 319;
LABEL_5:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v7, v6, 0, 0, 0, 0);
    return v6;
  }
  v8 = ExInitializeLookasideListEx(&g_DxgkThreadLookasideList, 0, 0, (POOL_TYPE)512, 0, 0x38u, 0x54677844u, 0);
  v6 = v8;
  if ( v8 < 0 )
  {
    PsTlsFree(g_DxgkThreadTlsId);
    WdLogSingleEntry1(2, v6);
    v7 = L"Failed to initialize the lookaside list for DXGTHREAD, returning 0x%I64x";
    WdLogGlobalForLineNumber = 334;
    goto LABEL_5;
  }
  ProcessNotifyRoutineEx2 = PsSetCreateProcessNotifyRoutineEx2(0, DxgkProcessNotify, 0);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v10 = ProcessNotifyRoutineEx2;
    WdLogSingleEntry1(2, ProcessNotifyRoutineEx2);
    WdLogGlobalForLineNumber = 345;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"PsSetCreateProcessNotifyRoutineEx failed 0x%I64x",
      v10,
      0,
      0,
      0,
      0);
  }
  SystemInformation = 8;
  if ( ZwQuerySystemInformation(MaxSystemInfoClass|SystemProcessInformation, &SystemInformation, 8u, 0) < 0
    || (v11 = 1, (SystemInformation & 0x200000000LL) == 0) )
  {
    v11 = 0;
  }
  g_OSTestSigningEnabled = v11;
  if ( (unsigned int)Feature_DxgkrnlPrereleaseDiagnostic__private_IsEnabledDeviceUsageNoInline() )
    g_IsInternalRelease = 1;
  v33 = 0;
  v34 = 288;
  v37 = 67108868;
  v35 = L"IsInternalRelease";
  v39 = 4;
  v36 = &g_IsInternalRelease;
  v38 = &g_IsInternalRelease;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v33, 0, 0);
  g_IsInternalRelease = g_IsInternalRelease != 0;
  g_IsInternalReleaseOrDbg = g_IsInternalRelease;
  g_bSkuSupportMultipleUsers = (RtlGetSuiteMask() & 0x110) == 16;
  wil_InitializeFeatureStaging();
  InitializeTelemetryAssertsKMByDriverObject(DriverObject);
  WdInitialize();
  result = DXGGLOBAL::CreateGlobal();
  if ( result >= 0 )
  {
    result = DpiInitializeGlobalState();
    if ( result >= 0 )
    {
      result = CCD_BTL::CreateGlobal();
      if ( result >= 0 )
      {
        DxgkInitializeTelemetry();
        Size = 0;
        v12 = ExSubscribeWnfStateChange(&gScreenStudyEventSubscription, &WNF_SRUM_SCREENONSTUDY_SESSION, 1);
        if ( v12 < 0 )
        {
          v14 = v12;
          WdLogSingleEntry1(2, v12);
          WdLogGlobalForLineNumber = 455;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"ExSubscribeWnfStateChange failed, returing 0x%I64x",
            v14,
            0,
            0,
            0,
            0);
          gScreenStudyEventSubscription = 0;
        }
        bTracingEnabled = 0;
        McGenEventRegister_EtwRegister(DxgkControlGuid, v13, &DxgkControlGuid_Context, &DxgkControlGuid_Context);
        v27 = -1;
        v28 = 0;
        if ( (qword_1401604F0 & 2) != 0 )
        {
          v29 = 1;
          v27 = 0;
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v15, EventProfilerEnter, v16, 0);
        }
        else
        {
          v29 = 0;
        }
        DXGETWPROFILER_BASE::PushProfilerEntry(&v27, 0);
        v30[0] = DxgkControlGuid;
        v30[1] = Dxgk_WDI_NotifyUser;
        WdDiagInit(v30);
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"\\Device\\DxgKrnl");
        DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&DxgkCreateClose;
        DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&DxgkCreateClose;
        DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)DxgkDeviceIoctl;
        DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)DxgkInternalDeviceIoctl;
        DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&DxgkShutdown;
        DriverObject->DriverUnload = (PDRIVER_UNLOAD)DxgkUnload;
        DefaultSDDLString = 0;
        RtlInitUnicodeString(&DefaultSDDLString, L"D:P(A;;GRGW;;;S-1-5-83-0)");
        v17 = WdmlibIoCreateDeviceSecure(
                DriverObject,
                0,
                &DestinationString,
                0x22u,
                0x100u,
                Size,
                &DefaultSDDLString,
                &GUID_SD_DXGKRNL_DRIVER_OBJECT,
                &g_pDeviceObject);
        LODWORD(v6) = v17;
        if ( v17 < 0 )
        {
          WdLogSingleEntry1(3, v17);
          WdLogGlobalForLineNumber = 508;
LABEL_35:
          DxgkCleanupPower();
          MonitorCleanupGlobal();
          if ( g_pDeviceObject )
          {
            IoDeleteDevice(g_pDeviceObject);
            g_pDeviceObject = 0;
          }
          if ( g_RegistryPath.Buffer )
          {
            DXGQUOTAALLOCATOR<256,1835156294>::operator delete(g_RegistryPath.Buffer);
            g_RegistryPath = 0;
          }
          DXGGLOBAL::DestroyGlobal();
          PsTlsFree(g_DxgkThreadTlsId);
          ExDeleteLookasideListEx(&g_DxgkThreadLookasideList);
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v27);
          if ( v29 )
          {
            if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
              McTemplateK0q_EtwWriteTransfer(v22, EventProfilerExit, v23, v27);
          }
          return v6;
        }
        v18 = DxgkInitialPower();
        LODWORD(v6) = v18;
        if ( v18 < 0 )
        {
          WdLogSingleEntry1(3, v18);
          WdLogGlobalForLineNumber = 521;
          goto LABEL_35;
        }
        v19 = MonitorInitializeGlobal();
        LODWORD(v6) = v19;
        if ( v19 < 0 )
        {
          WdLogSingleEntry1(3, v19);
          WdLogGlobalForLineNumber = 534;
          goto LABEL_35;
        }
        SysMmInitializeGlobal();
        DxgkInitTest();
        DxgDbgInit();
        TdrInit();
        v20 = SMgrRegisterSessionChangeCallout(DxgkNotifySessionStateChange);
        v6 = v20;
        if ( v20 < 0 )
        {
          WdLogSingleEntry1(2, v20);
          WdLogGlobalForLineNumber = 567;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Could not register session change callout with session manager, returning 0x%I64x.",
            v6,
            0,
            0,
            0,
            0);
          goto LABEL_35;
        }
        v21 = IoRegisterShutdownNotification(g_pDeviceObject);
        v6 = v21;
        if ( v21 < 0 )
        {
          WdLogSingleEntry1(2, v21);
          WdLogGlobalForLineNumber = 577;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Could not register for shutdown notification, returning 0x%I64x.",
            v6,
            0,
            0,
            0,
            0);
          SMgrUnregisterSessionChangeCallout(DxgkNotifySessionStateChange);
          goto LABEL_35;
        }
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v27);
        if ( v29 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v24, EventProfilerExit, v25, v27);
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140419008  mov     [rsp-8+arg_8], rbx
0x14041900d  mov     [rsp-8+arg_10], rdi
0x140419012  push    rbp
0x140419013  push    r12
0x140419015  push    r13
0x140419017  lea     rbp, [rsp-10h]
0x14041901c  sub     rsp, 110h
0x140419023  mov     r13, rcx
0x140419026  mov     cs:?g_pDriverObject@@3PEAU_DRIVER_OBJECT@@EA, rcx; _DRIVER_OBJECT * g_pDriverObject
0x14041902d  movzx   ecx, word ptr [rdx+2]
0x140419031  mov     rbx, rdx
0x140419034  mov     edx, 4B677844h
0x140419039  mov     r8d, 100h
0x14041903f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140419044  xor     r12d, r12d
0x140419047  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer, rax; _UNICODE_STRING g_RegistryPath ...
0x14041904e  test    rax, rax
0x140419051  jnz     short loc_1404190A7
0x140419053  lea     ecx, [rax+2]
0x140419056  call    cs:__imp_WdLogSingleEntry0
0x14041905d  nop     dword ptr [rax+rax+00h]
0x140419062  mov     [rsp+120h+DeviceObject], r12
0x140419067  lea     r9, aFailedToAlloca_72; "Failed to allocate registry path buffer"...
0x14041906e  mov     qword ptr [rsp+120h+Depth], r12
0x140419073  mov     eax, 132h
0x140419078  mov     qword ptr [rsp+120h+Tag], r12
0x14041907d  or      r8d, 0FFFFFFFFh
0x140419081  mov     [rsp+120h+Size], r12
0x140419086  mov     edx, 40000h
0x14041908b  xor     ecx, ecx
0x14041908d  mov     qword ptr [rsp+120h+Flags], rax
0x140419092  mov     cs:WdLogGlobalForLineNumber, eax
0x140419098  call    DxgkLogInternalTriageEvent
0x14041909d  mov     eax, 0C0000017h
0x1404190a2  jmp     loc_14041978E
0x1404190a7  movzx   eax, word ptr [rbx+2]
0x1404190ab  lea     rcx, ?g_RegistryPath@@3U_UNICODE_STRING@@A; DestinationString
0x1404190b2  mov     rdx, rbx; SourceString
0x1404190b5  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.MaximumLength, ax; _UNICODE_STRING g_RegistryPath ...
0x1404190bc  call    cs:__imp_RtlCopyUnicodeString
0x1404190c3  nop     dword ptr [rax+rax+00h]
0x1404190c8  lea     r8, ?g_DxgkThreadTlsId@@3KA; ulong g_DxgkThreadTlsId
0x1404190cf  xor     edx, edx
0x1404190d1  lea     rcx, ?DxgkThreadPsTslCallback@@YAXPEAX@Z; DxgkThreadPsTslCallback(void *)
0x1404190d8  call    cs:__imp_PsTlsAlloc
0x1404190df  nop     dword ptr [rax+rax+00h]
0x1404190e4  movsxd  rdi, eax
0x1404190e7  test    eax, eax
0x1404190e9  jns     short loc_140419140
0x1404190eb  mov     rdx, rdi
0x1404190ee  mov     ecx, 2
0x1404190f3  call    cs:__imp_WdLogSingleEntry1
0x1404190fa  nop     dword ptr [rax+rax+00h]
0x1404190ff  lea     r9, aFailedToAlloca_45; "Failed to allocate a PsTls slot for Dxg"...
0x140419106  mov     cs:WdLogGlobalForLineNumber, 13Fh
0x140419110  mov     [rsp+120h+DeviceObject], r12
0x140419115  or      r8d, 0FFFFFFFFh
0x140419119  mov     qword ptr [rsp+120h+Depth], r12
0x14041911e  mov     edx, 40000h
0x140419123  mov     qword ptr [rsp+120h+Tag], r12
0x140419128  xor     ecx, ecx
0x14041912a  mov     [rsp+120h+Size], r12
0x14041912f  mov     qword ptr [rsp+120h+Flags], rdi
0x140419134  call    DxgkLogInternalTriageEvent
0x140419139  mov     eax, edi
0x14041913b  jmp     loc_14041978E
0x140419140  mov     [rsp+120h+Depth], r12w; Depth
0x140419146  lea     rcx, ?g_DxgkThreadLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x14041914d  mov     [rsp+120h+Tag], 54677844h; Tag
0x140419155  mov     r9d, 200h; PoolType
0x14041915b  mov     [rsp+120h+Size], 38h ; '8'; Size
0x140419164  xor     r8d, r8d; Free
0x140419167  xor     edx, edx; Allocate
0x140419169  mov     [rsp+120h+Flags], r12d; Flags
0x14041916e  call    cs:__imp_ExInitializeLookasideListEx
0x140419175  nop     dword ptr [rax+rax+00h]
0x14041917a  movsxd  rdi, eax
0x14041917d  test    eax, eax
0x14041917f  jns     short loc_1404191BD
0x140419181  mov     ecx, cs:?g_DxgkThreadTlsId@@3KA; ulong g_DxgkThreadTlsId
0x140419187  call    cs:__imp_PsTlsFree
0x14041918e  nop     dword ptr [rax+rax+00h]
0x140419193  mov     rdx, rdi
0x140419196  mov     ecx, 2
0x14041919b  call    cs:__imp_WdLogSingleEntry1
0x1404191a2  nop     dword ptr [rax+rax+00h]
0x1404191a7  lea     r9, aFailedToInitia_12; "Failed to initialize the lookaside list"...
0x1404191ae  mov     cs:WdLogGlobalForLineNumber, 14Eh
0x1404191b8  jmp     loc_140419110
0x1404191bd  xor     r8d, r8d
0x1404191c0  lea     rdx, ?DxgkProcessNotify@@YAXPEAU_EPROCESS@@PEAXPEAU_PS_CREATE_NOTIFY_INFO@@@Z; DxgkProcessNotify(_EPROCESS *,void *,_PS_CREATE_NOTIFY_INFO *)
0x1404191c7  xor     ecx, ecx
0x1404191c9  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx2
0x1404191d0  nop     dword ptr [rax+rax+00h]
0x1404191d5  test    eax, eax
0x1404191d7  jns     short loc_14041922A
0x1404191d9  movsxd  rbx, eax
0x1404191dc  mov     ecx, 2
0x1404191e1  mov     rdx, rbx
0x1404191e4  call    cs:__imp_WdLogSingleEntry1
0x1404191eb  nop     dword ptr [rax+rax+00h]
0x1404191f0  mov     [rsp+120h+DeviceObject], r12
0x1404191f5  lea     r9, aPssetcreatepro; "PsSetCreateProcessNotifyRoutineEx faile"...
0x1404191fc  mov     qword ptr [rsp+120h+Depth], r12
0x140419201  or      r8d, 0FFFFFFFFh
0x140419205  mov     qword ptr [rsp+120h+Tag], r12
0x14041920a  mov     edx, 40000h
0x14041920f  mov     [rsp+120h+Size], r12
0x140419214  xor     ecx, ecx
0x140419216  mov     qword ptr [rsp+120h+Flags], rbx
0x14041921b  mov     cs:WdLogGlobalForLineNumber, 159h
0x140419225  call    DxgkLogInternalTriageEvent
0x14041922a  mov     r8d, 8; SystemInformationLength
0x140419230  mov     [rbp+20h+SystemInformation], r12
0x140419234  xor     r9d, r9d; ReturnLength
0x140419237  mov     dword ptr [rbp+20h+SystemInformation], r8d
0x14041923b  lea     rdx, [rbp+20h+SystemInformation]; SystemInformation
0x14041923f  lea     ecx, [r8+5Fh]; SystemInformationClass
0x140419243  call    cs:__imp_ZwQuerySystemInformation
0x14041924a  nop     dword ptr [rax+rax+00h]
0x14041924f  test    eax, eax
0x140419251  js      short loc_14041925B
0x140419253  test    byte ptr [rbp+20h+SystemInformation+4], 2
0x140419257  mov     al, 1
0x140419259  jnz     short loc_14041925E
0x14041925b  mov     al, r12b
0x14041925e  mov     cs:?g_OSTestSigningEnabled@@3EA, al; uchar g_OSTestSigningEnabled
0x140419264  call    Feature_DxgkrnlPrereleaseDiagnostic__private_IsEnabledDeviceUsageNoInline
0x140419269  test    eax, eax
0x14041926b  jz      short loc_140419274
0x14041926d  mov     cs:?g_IsInternalRelease@@3EA, 1; uchar g_IsInternalRelease
0x140419274  xorps   xmm0, xmm0
0x140419277  mov     [rbp+20h+var_80], r12
0x14041927b  xor     r9d, r9d
0x14041927e  mov     [rbp+20h+var_78], 120h
0x140419285  lea     rax, aIsinternalrele; "IsInternalRelease"
0x14041928c  mov     [rbp+20h+var_60], 4000004h
0x140419293  mov     [rbp+20h+var_70], rax
0x140419297  lea     r8, [rbp+20h+var_80]
0x14041929b  lea     rax, ?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1404192a2  mov     [rbp+20h+var_50], 4
0x1404192a9  lea     ecx, [r9+2]
0x1404192ad  mov     [rbp+20h+var_68], rax
0x1404192b1  lea     rdx, Path; "GraphicsDrivers"
0x1404192b8  mov     [rbp+20h+var_58], rax
0x1404192bc  mov     [rbp+20h+var_48], r12
0x1404192c0  mov     [rbp+20h+var_40], r12d
0x1404192c4  mov     [rbp+20h+var_38], r12
0x1404192c8  movups  [rbp+20h+var_30], xmm0
0x1404192cc  mov     qword ptr [rsp+120h+Flags], r12
0x1404192d1  movups  [rbp+20h+var_20], xmm0
0x1404192d5  call    cs:__imp_RtlQueryRegistryValuesEx
0x1404192dc  nop     dword ptr [rax+rax+00h]
0x1404192e1  cmp     cs:?g_IsInternalRelease@@3EA, r12b; uchar g_IsInternalRelease
0x1404192e8  setnz   al
0x1404192eb  mov     cs:?g_IsInternalRelease@@3EA, al; uchar g_IsInternalRelease
0x1404192f1  mov     cs:?g_IsInternalReleaseOrDbg@@3EA, al; uchar g_IsInternalReleaseOrDbg
0x1404192f7  call    cs:__imp_RtlGetSuiteMask
0x1404192fe  nop     dword ptr [rax+rax+00h]
0x140419303  and     eax, 110h
0x140419308  cmp     eax, 10h
0x14041930b  setz    cs:?g_bSkuSupportMultipleUsers@@3EA; uchar g_bSkuSupportMultipleUsers
0x140419312  call    wil_InitializeFeatureStaging
0x140419317  mov     rcx, r13
0x14041931a  call    InitializeTelemetryAssertsKMByDriverObject
0x14041931f  call    cs:__imp_WdInitialize
0x140419326  nop     dword ptr [rax+rax+00h]
0x14041932b  call    ?CreateGlobal@DXGGLOBAL@@SAJXZ; DXGGLOBAL::CreateGlobal(void)
0x140419330  test    eax, eax
0x140419332  js      loc_14041978E
0x140419338  call    DpiInitializeGlobalState
0x14041933d  test    eax, eax
0x14041933f  js      loc_14041978E
0x140419345  call    ?CreateGlobal@CCD_BTL@@SAJXZ; CCD_BTL::CreateGlobal(void)
0x14041934a  test    eax, eax
0x14041934c  js      loc_14041978E
0x140419352  call    ?DxgkInitializeTelemetry@@YAXXZ; DxgkInitializeTelemetry(void)
0x140419357  xor     r9d, r9d
0x14041935a  mov     [rsp+120h+Size], r12
0x14041935f  lea     rax, ?WnfScreenOnCallback@@YAJPEAU_EX_WNF_SUBSCRIPTION@@PEBU_WNF_STATE_NAME@@KKPEBU_WNF_TYPE_ID@@PEAX@Z; WnfScreenOnCallback(_EX_WNF_SUBSCRIPTION *,_WNF_STATE_NAME const *,ulong,ulong,_WNF_TYPE_ID const *,void *)
0x140419366  lea     rdx, WNF_SRUM_SCREENONSTUDY_SESSION
0x14041936d  mov     qword ptr [rsp+120h+Flags], rax
0x140419372  lea     rcx, ?gScreenStudyEventSubscription@@3PEAU_EX_WNF_SUBSCRIPTION@@EA; _EX_WNF_SUBSCRIPTION * gScreenStudyEventSubscription
0x140419379  lea     r8d, [r9+1]
0x14041937d  call    cs:__imp_ExSubscribeWnfStateChange
0x140419384  nop     dword ptr [rax+rax+00h]
0x140419389  test    eax, eax
0x14041938b  jns     short loc_1404193E5
0x14041938d  movsxd  rbx, eax
0x140419390  mov     ecx, 2
0x140419395  mov     rdx, rbx
0x140419398  call    cs:__imp_WdLogSingleEntry1
0x14041939f  nop     dword ptr [rax+rax+00h]
0x1404193a4  mov     [rsp+120h+DeviceObject], r12
0x1404193a9  lea     r9, aExsubscribewnf; "ExSubscribeWnfStateChange failed, retur"...
0x1404193b0  mov     qword ptr [rsp+120h+Depth], r12
0x1404193b5  or      r8d, 0FFFFFFFFh
0x1404193b9  mov     qword ptr [rsp+120h+Tag], r12
0x1404193be  mov     edx, 40000h
0x1404193c3  mov     [rsp+120h+Size], r12; Exclusive
0x1404193c8  xor     ecx, ecx
0x1404193ca  mov     qword ptr [rsp+120h+Flags], rbx
0x1404193cf  mov     cs:WdLogGlobalForLineNumber, 1C7h
0x1404193d9  call    DxgkLogInternalTriageEvent
0x1404193de  mov     cs:?gScreenStudyEventSubscription@@3PEAU_EX_WNF_SUBSCRIPTION@@EA, r12; _EX_WNF_SUBSCRIPTION * gScreenStudyEventSubscription
0x1404193e5  lea     r8, DxgkControlGuid_Context
0x1404193ec  mov     cs:bTracingEnabled, r12b
0x1404193f3  lea     rbx, DxgkControlGuid
0x1404193fa  mov     r9, r8
0x1404193fd  mov     rcx, rbx
0x140419400  call    McGenEventRegister_EtwRegister
0x140419405  test    byte ptr cs:qword_1401604F0, 2
0x14041940c  mov     [rsp+120h+var_D0], 0FFFFFFFFh
0x140419414  mov     [rsp+120h+var_C8], r12
0x140419419  jz      short loc_14041943F
0x14041941b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140419422  mov     [rsp+120h+var_C0], 1
0x140419427  mov     [rsp+120h+var_D0], r12d
0x14041942c  jz      short loc_140419444
0x14041942e  xor     r9d, r9d
0x140419431  lea     rdx, EventProfilerEnter
0x140419438  call    McTemplateK0q_EtwWriteTransfer
0x14041943d  jmp     short loc_140419444
0x14041943f  mov     [rsp+120h+var_C0], r12b
0x140419444  xor     edx, edx
0x140419446  lea     rcx, [rsp+120h+var_D0]
0x14041944b  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140419450  lea     rax, Dxgk_WDI_NotifyUser
0x140419457  mov     [rsp+120h+var_B8], rbx
0x14041945c  lea     rcx, [rsp+120h+var_B8]
0x140419461  mov     [rsp+120h+var_B0], rax
0x140419466  call    cs:__imp_WdDiagInit
0x14041946d  nop     dword ptr [rax+rax+00h]
0x140419472  xorps   xmm0, xmm0
0x140419475  lea     rdx, aDeviceDxgkrnl_0; "\\Device\\DxgKrnl"
0x14041947c  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x140419480  movups  xmmword ptr [rbp+20h+DestinationString.Length], xmm0
0x140419484  call    cs:__imp_RtlInitUnicodeString
0x14041948b  nop     dword ptr [rax+rax+00h]
0x140419490  lea     rax, DxgkCreateClose
0x140419497  xorps   xmm0, xmm0
0x14041949a  mov     [r13+70h], rax
0x14041949e  lea     rdx, aDPAGrgwS15830; "D:P(A;;GRGW;;;S-1-5-83-0)"
0x1404194a5  mov     [r13+80h], rax
0x1404194ac  lea     rcx, [rsp+120h+DefaultSDDLString]; DestinationString
0x1404194b1  lea     rax, DxgkDeviceIoctl
0x1404194b8  mov     [r13+0E0h], rax
0x1404194bf  lea     rax, DxgkInternalDeviceIoctl
0x1404194c6  mov     [r13+0E8h], rax
0x1404194cd  lea     rax, DxgkShutdown
0x1404194d4  mov     [r13+0F0h], rax
0x1404194db  lea     rax, DxgkUnload
0x1404194e2  mov     [r13+68h], rax
0x1404194e6  movups  xmmword ptr [rsp+120h+DefaultSDDLString.Length], xmm0
0x1404194eb  call    cs:__imp_RtlInitUnicodeString
0x1404194f2  nop     dword ptr [rax+rax+00h]
0x1404194f7  lea     rax, ?g_pDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * g_pDeviceObject
0x1404194fe  mov     r9d, 22h ; '"'; DeviceType
0x140419504  mov     [rsp+120h+DeviceObject], rax; DeviceObject
0x140419509  lea     r8, [rbp+20h+DestinationString]; DeviceName
0x14041950d  lea     rax, GUID_SD_DXGKRNL_DRIVER_OBJECT
0x140419514  xor     edx, edx; DeviceExtensionSize
0x140419516  mov     qword ptr [rsp+120h+Depth], rax; DeviceClassGuid
0x14041951b  mov     rcx, r13; DriverObject
0x14041951e  lea     rax, [rsp+120h+DefaultSDDLString]
0x140419523  mov     qword ptr [rsp+120h+Tag], rax; DefaultSDDLString
0x140419528  mov     [rsp+120h+Flags], 100h; DeviceCharacteristics
0x140419530  call    WdmlibIoCreateDeviceSecure
0x140419535  movsxd  rdi, eax
0x140419538  test    eax, eax
0x14041953a  jns     short loc_14041955F
0x14041953c  mov     rdx, rdi
0x14041953f  mov     ecx, 3
0x140419544  call    cs:__imp_WdLogSingleEntry1
0x14041954b  nop     dword ptr [rax+rax+00h]
0x140419550  mov     cs:WdLogGlobalForLineNumber, 1FCh
0x14041955a  jmp     loc_1404196BA
0x14041955f  call    DxgkInitialPower
0x140419564  movsxd  rdi, eax
0x140419567  test    eax, eax
0x140419569  jns     short loc_14041958E
0x14041956b  mov     rdx, rdi
0x14041956e  mov     ecx, 3
0x140419573  call    cs:__imp_WdLogSingleEntry1
0x14041957a  nop     dword ptr [rax+rax+00h]
0x14041957f  mov     cs:WdLogGlobalForLineNumber, 209h
0x140419589  jmp     loc_1404196BA
0x14041958e  call    ?MonitorInitializeGlobal@@YAJXZ; MonitorInitializeGlobal(void)
0x140419593  movsxd  rdi, eax
0x140419596  test    eax, eax
0x140419598  jns     short loc_1404195BD
0x14041959a  mov     rdx, rdi
0x14041959d  mov     ecx, 3
0x1404195a2  call    cs:__imp_WdLogSingleEntry1
0x1404195a9  nop     dword ptr [rax+rax+00h]
0x1404195ae  mov     cs:WdLogGlobalForLineNumber, 216h
0x1404195b8  jmp     loc_1404196BA
0x1404195bd  call    ?SysMmInitializeGlobal@@YAXXZ; SysMmInitializeGlobal(void)
0x1404195c2  call    ?DxgkInitTest@@YAXXZ; DxgkInitTest(void)
0x1404195c7  call    ?DxgDbgInit@@YAXXZ; DxgDbgInit(void)
  ... truncated ...
```
