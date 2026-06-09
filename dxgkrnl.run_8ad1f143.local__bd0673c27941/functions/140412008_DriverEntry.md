# DriverEntry

- ea: `0x140412008`
- end: `0x1404127a8`
- name: `DriverEntry`
- size: `1952`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1404127b0`

## callees

- `0x1400061d0`
- `0x140009030`
- `0x14000d7d0`
- `0x140012b14`
- `0x140013860`
- `0x14001b890`
- `0x14001d0e4`
- `0x140062620`
- `0x140072bcc`
- `0x1400737c8`
- `0x14009fc94`
- `0x1402389c4`
- `0x14023c114`
- `0x14023c5dc`
- `0x140268414`
- `0x14026ab78`
- `0x1402a1a28`
- `0x1402a1af4`
- `0x1402e8628`
- `0x1402ee47c`
- `0x140307448`
- `0x140404050`
- `0x140412008`
- `0x140412818`
- `0x1404129c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1404122d5`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1404122d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140412484`
- `ntoskrnl!RtlInitUnicodeString` at `0x1404124eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140412484`
- `ntoskrnl!RtlInitUnicodeString` at `0x1404124eb`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14041271d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14041271d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14041216e`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14041216e`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14041237d`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14041237d`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140412243`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140412243`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1404120bc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1404120bc`
- `ntoskrnl!PsTlsAlloc` at `0x1404120d8`
- `ntoskrnl!PsTlsAlloc` at `0x1404120d8`
- `ntoskrnl!PsTlsFree` at `0x140412187`
- `ntoskrnl!PsTlsFree` at `0x14041270a`
- `ntoskrnl!PsTlsFree` at `0x140412187`
- `ntoskrnl!PsTlsFree` at `0x14041270a`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x1404121c9`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x1404121c9`
- `ntoskrnl!RtlGetSuiteMask` at `0x1404122f7`
- `ntoskrnl!RtlGetSuiteMask` at `0x1404122f7`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140412642`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x140412642`
- `ntoskrnl!IoDeleteDevice` at `0x1404126d0`
- `ntoskrnl!IoDeleteDevice` at `0x1404126d0`
- `watchdog!WdDiagInit` at `0x140412466`
- `watchdog!WdDiagInit` at `0x140412466`
- `watchdog!SMgrUnregisterSessionChangeCallout` at `0x1404126ae`
- `watchdog!SMgrUnregisterSessionChangeCallout` at `0x1404126ae`
- `watchdog!SMgrRegisterSessionChangeCallout` at `0x1404125d8`
- `watchdog!SMgrRegisterSessionChangeCallout` at `0x1404125d8`
- `watchdog!WdInitialize` at `0x14041231f`
- `watchdog!WdInitialize` at `0x14041231f`
- `watchdog!WdLogSingleEntry0` at `0x140412056`
- `watchdog!WdLogSingleEntry0` at `0x140412056`
- `watchdog!WdLogSingleEntry1` at `0x1404120f3`
- `watchdog!WdLogSingleEntry1` at `0x14041219b`
- `watchdog!WdLogSingleEntry1` at `0x1404121e4`
- `watchdog!WdLogSingleEntry1` at `0x140412398`
- `watchdog!WdLogSingleEntry1` at `0x140412544`
- `watchdog!WdLogSingleEntry1` at `0x140412573`
- `watchdog!WdLogSingleEntry1` at `0x1404125a2`
- `watchdog!WdLogSingleEntry1` at `0x1404125f3`
- `watchdog!WdLogSingleEntry1` at `0x140412661`
- `watchdog!WdLogSingleEntry1` at `0x1404120f3`
- `watchdog!WdLogSingleEntry1` at `0x14041219b`
- `watchdog!WdLogSingleEntry1` at `0x1404121e4`
- `watchdog!WdLogSingleEntry1` at `0x140412398`
- `watchdog!WdLogSingleEntry1` at `0x140412544`
- `watchdog!WdLogSingleEntry1` at `0x140412573`
- `watchdog!WdLogSingleEntry1` at `0x1404125a2`
- `watchdog!WdLogSingleEntry1` at `0x1404125f3`
- `watchdog!WdLogSingleEntry1` at `0x140412661`

## string_xrefs

- `0x1404120ff`: `Failed to allocate a PsTls slot for DxgkThread, returning 0x%I64x.`
- `0x140412067`: `Failed to allocate registry path buffer.`
- `0x1404121f5`: `PsSetCreateProcessNotifyRoutineEx failed 0x%I64x`
- `0x1404121a7`: `Failed to initialize the lookaside list for DXGTHREAD, returning 0x%I64x`
- `0x1404123a9`: `ExSubscribeWnfStateChange failed, returing 0x%I64x`

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
  int v17; // eax
  NTSTATUS v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // r8
  BOOLEAN Size; // [rsp+28h] [rbp-D8h]
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  char v26; // [rsp+60h] [rbp-A0h]
  _QWORD v27[2]; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING DefaultSDDLString; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-60h] BYREF
  int v31; // [rsp+A8h] [rbp-58h]
  const wchar_t *v32; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v33; // [rsp+B8h] [rbp-48h]
  int v34; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v35; // [rsp+C8h] [rbp-38h]
  int v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  int v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  __int128 v40; // [rsp+F0h] [rbp-10h]
  __int128 v41; // [rsp+100h] [rbp+0h]
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
    WdLogSingleEntry1(2);
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
    WdLogSingleEntry1(2);
    v7 = L"Failed to initialize the lookaside list for DXGTHREAD, returning 0x%I64x";
    WdLogGlobalForLineNumber = 334;
    goto LABEL_5;
  }
  ProcessNotifyRoutineEx2 = PsSetCreateProcessNotifyRoutineEx2(0, DxgkProcessNotify, 0);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v10 = ProcessNotifyRoutineEx2;
    WdLogSingleEntry1(2);
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
  v30 = 0;
  v31 = 288;
  v34 = 67108868;
  v32 = L"IsInternalRelease";
  v36 = 4;
  v33 = &g_IsInternalRelease;
  v35 = &g_IsInternalRelease;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v30, 0, 0);
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
          WdLogSingleEntry1(2);
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
        v24 = -1;
        v25 = 0;
        if ( (qword_14015C500 & 2) != 0 )
        {
          v26 = 1;
          v24 = 0;
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v15, EventProfilerEnter, v16, 0);
        }
        else
        {
          v26 = 0;
        }
        DXGETWPROFILER_BASE::PushProfilerEntry(&v24, 0);
        v27[0] = DxgkControlGuid;
        v27[1] = Dxgk_WDI_NotifyUser;
        WdDiagInit(v27);
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"\\Device\\DxgKrnl");
        DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&DxgkCreateClose;
        DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&DxgkCreateClose;
        DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&DxgkDeviceIoctl;
        DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)&DxgkInternalDeviceIoctl;
        DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&DxgkShutdown;
        DriverObject->DriverUnload = (PDRIVER_UNLOAD)DxgkUnload;
        DefaultSDDLString = 0;
        RtlInitUnicodeString(&DefaultSDDLString, L"D:P(A;;GRGW;;;S-1-5-83-0)");
        LODWORD(v6) = WdmlibIoCreateDeviceSecure(
                        DriverObject,
                        0,
                        &DestinationString,
                        0x22u,
                        0x100u,
                        Size,
                        &DefaultSDDLString,
                        &GUID_SD_DXGKRNL_DRIVER_OBJECT,
                        &g_pDeviceObject);
        if ( (int)v6 < 0 )
        {
          WdLogSingleEntry1(3);
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
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v24);
          if ( v26 )
          {
            if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
              McTemplateK0q_EtwWriteTransfer(v19, EventProfilerExit, v20, v24);
          }
          return v6;
        }
        LODWORD(v6) = DxgkInitialPower();
        if ( (int)v6 < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 521;
          goto LABEL_35;
        }
        LODWORD(v6) = MonitorInitializeGlobal();
        if ( (int)v6 < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 534;
          goto LABEL_35;
        }
        SysMmInitializeGlobal();
        DxgkInitTest();
        DxgDbgInit();
        TdrInit();
        v17 = SMgrRegisterSessionChangeCallout(DxgkNotifySessionStateChange);
        v6 = v17;
        if ( v17 < 0 )
        {
          WdLogSingleEntry1(2);
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
        v18 = IoRegisterShutdownNotification(g_pDeviceObject);
        v6 = v18;
        if ( v18 < 0 )
        {
          WdLogSingleEntry1(2);
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
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v24);
        if ( v26 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v21, EventProfilerExit, v22, v24);
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140412008  mov     [rsp-8+arg_8], rbx
0x14041200d  mov     [rsp-8+arg_10], rdi
0x140412012  push    rbp
0x140412013  push    r12
0x140412015  push    r13
0x140412017  lea     rbp, [rsp-10h]
0x14041201c  sub     rsp, 110h
0x140412023  mov     r13, rcx
0x140412026  mov     cs:?g_pDriverObject@@3PEAU_DRIVER_OBJECT@@EA, rcx; _DRIVER_OBJECT * g_pDriverObject
0x14041202d  movzx   ecx, word ptr [rdx+2]
0x140412031  mov     rbx, rdx
0x140412034  mov     edx, 4B677844h
0x140412039  mov     r8d, 100h
0x14041203f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140412044  xor     r12d, r12d
0x140412047  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.Buffer, rax; _UNICODE_STRING g_RegistryPath ...
0x14041204e  test    rax, rax
0x140412051  jnz     short loc_1404120A7
0x140412053  lea     ecx, [rax+2]
0x140412056  call    cs:__imp_WdLogSingleEntry0
0x14041205d  nop     dword ptr [rax+rax+00h]
0x140412062  mov     [rsp+120h+DeviceObject], r12
0x140412067  lea     r9, aFailedToAlloca_72; "Failed to allocate registry path buffer"...
0x14041206e  mov     qword ptr [rsp+120h+Depth], r12
0x140412073  mov     eax, 132h
0x140412078  mov     qword ptr [rsp+120h+Tag], r12
0x14041207d  or      r8d, 0FFFFFFFFh
0x140412081  mov     [rsp+120h+Size], r12
0x140412086  mov     edx, 40000h
0x14041208b  xor     ecx, ecx
0x14041208d  mov     qword ptr [rsp+120h+Flags], rax
0x140412092  mov     cs:WdLogGlobalForLineNumber, eax
0x140412098  call    DxgkLogInternalTriageEvent
0x14041209d  mov     eax, 0C0000017h
0x1404120a2  jmp     loc_14041278E
0x1404120a7  movzx   eax, word ptr [rbx+2]
0x1404120ab  lea     rcx, ?g_RegistryPath@@3U_UNICODE_STRING@@A; DestinationString
0x1404120b2  mov     rdx, rbx; SourceString
0x1404120b5  mov     cs:?g_RegistryPath@@3U_UNICODE_STRING@@A.MaximumLength, ax; _UNICODE_STRING g_RegistryPath ...
0x1404120bc  call    cs:__imp_RtlCopyUnicodeString
0x1404120c3  nop     dword ptr [rax+rax+00h]
0x1404120c8  lea     r8, ?g_DxgkThreadTlsId@@3KA; ulong g_DxgkThreadTlsId
0x1404120cf  xor     edx, edx
0x1404120d1  lea     rcx, ?DxgkThreadPsTslCallback@@YAXPEAX@Z; DxgkThreadPsTslCallback(void *)
0x1404120d8  call    cs:__imp_PsTlsAlloc
0x1404120df  nop     dword ptr [rax+rax+00h]
0x1404120e4  movsxd  rdi, eax
0x1404120e7  test    eax, eax
0x1404120e9  jns     short loc_140412140
0x1404120eb  mov     rdx, rdi
0x1404120ee  mov     ecx, 2
0x1404120f3  call    cs:__imp_WdLogSingleEntry1
0x1404120fa  nop     dword ptr [rax+rax+00h]
0x1404120ff  lea     r9, aFailedToAlloca_45; "Failed to allocate a PsTls slot for Dxg"...
0x140412106  mov     cs:WdLogGlobalForLineNumber, 13Fh
0x140412110  mov     [rsp+120h+DeviceObject], r12
0x140412115  or      r8d, 0FFFFFFFFh
0x140412119  mov     qword ptr [rsp+120h+Depth], r12
0x14041211e  mov     edx, 40000h
0x140412123  mov     qword ptr [rsp+120h+Tag], r12
0x140412128  xor     ecx, ecx
0x14041212a  mov     [rsp+120h+Size], r12
0x14041212f  mov     qword ptr [rsp+120h+Flags], rdi
0x140412134  call    DxgkLogInternalTriageEvent
0x140412139  mov     eax, edi
0x14041213b  jmp     loc_14041278E
0x140412140  mov     [rsp+120h+Depth], r12w; Depth
0x140412146  lea     rcx, ?g_DxgkThreadLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x14041214d  mov     [rsp+120h+Tag], 54677844h; Tag
0x140412155  mov     r9d, 200h; PoolType
0x14041215b  mov     [rsp+120h+Size], 38h ; '8'; Size
0x140412164  xor     r8d, r8d; Free
0x140412167  xor     edx, edx; Allocate
0x140412169  mov     [rsp+120h+Flags], r12d; Flags
0x14041216e  call    cs:__imp_ExInitializeLookasideListEx
0x140412175  nop     dword ptr [rax+rax+00h]
0x14041217a  movsxd  rdi, eax
0x14041217d  test    eax, eax
0x14041217f  jns     short loc_1404121BD
0x140412181  mov     ecx, cs:?g_DxgkThreadTlsId@@3KA; ulong g_DxgkThreadTlsId
0x140412187  call    cs:__imp_PsTlsFree
0x14041218e  nop     dword ptr [rax+rax+00h]
0x140412193  mov     rdx, rdi
0x140412196  mov     ecx, 2
0x14041219b  call    cs:__imp_WdLogSingleEntry1
0x1404121a2  nop     dword ptr [rax+rax+00h]
0x1404121a7  lea     r9, aFailedToInitia_12; "Failed to initialize the lookaside list"...
0x1404121ae  mov     cs:WdLogGlobalForLineNumber, 14Eh
0x1404121b8  jmp     loc_140412110
0x1404121bd  xor     r8d, r8d
0x1404121c0  lea     rdx, ?DxgkProcessNotify@@YAXPEAU_EPROCESS@@PEAXPEAU_PS_CREATE_NOTIFY_INFO@@@Z; DxgkProcessNotify(_EPROCESS *,void *,_PS_CREATE_NOTIFY_INFO *)
0x1404121c7  xor     ecx, ecx
0x1404121c9  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx2
0x1404121d0  nop     dword ptr [rax+rax+00h]
0x1404121d5  test    eax, eax
0x1404121d7  jns     short loc_14041222A
0x1404121d9  movsxd  rbx, eax
0x1404121dc  mov     ecx, 2
0x1404121e1  mov     rdx, rbx
0x1404121e4  call    cs:__imp_WdLogSingleEntry1
0x1404121eb  nop     dword ptr [rax+rax+00h]
0x1404121f0  mov     [rsp+120h+DeviceObject], r12
0x1404121f5  lea     r9, aPssetcreatepro; "PsSetCreateProcessNotifyRoutineEx faile"...
0x1404121fc  mov     qword ptr [rsp+120h+Depth], r12
0x140412201  or      r8d, 0FFFFFFFFh
0x140412205  mov     qword ptr [rsp+120h+Tag], r12
0x14041220a  mov     edx, 40000h
0x14041220f  mov     [rsp+120h+Size], r12
0x140412214  xor     ecx, ecx
0x140412216  mov     qword ptr [rsp+120h+Flags], rbx
0x14041221b  mov     cs:WdLogGlobalForLineNumber, 159h
0x140412225  call    DxgkLogInternalTriageEvent
0x14041222a  mov     r8d, 8; SystemInformationLength
0x140412230  mov     [rbp+20h+SystemInformation], r12
0x140412234  xor     r9d, r9d; ReturnLength
0x140412237  mov     dword ptr [rbp+20h+SystemInformation], r8d
0x14041223b  lea     rdx, [rbp+20h+SystemInformation]; SystemInformation
0x14041223f  lea     ecx, [r8+5Fh]; SystemInformationClass
0x140412243  call    cs:__imp_ZwQuerySystemInformation
0x14041224a  nop     dword ptr [rax+rax+00h]
0x14041224f  test    eax, eax
0x140412251  js      short loc_14041225B
0x140412253  test    byte ptr [rbp+20h+SystemInformation+4], 2
0x140412257  mov     al, 1
0x140412259  jnz     short loc_14041225E
0x14041225b  mov     al, r12b
0x14041225e  mov     cs:?g_OSTestSigningEnabled@@3EA, al; uchar g_OSTestSigningEnabled
0x140412264  call    Feature_DxgkrnlPrereleaseDiagnostic__private_IsEnabledDeviceUsageNoInline
0x140412269  test    eax, eax
0x14041226b  jz      short loc_140412274
0x14041226d  mov     cs:?g_IsInternalRelease@@3EA, 1; uchar g_IsInternalRelease
0x140412274  xorps   xmm0, xmm0
0x140412277  mov     [rbp+20h+var_80], r12
0x14041227b  xor     r9d, r9d
0x14041227e  mov     [rbp+20h+var_78], 120h
0x140412285  lea     rax, aIsinternalrele; "IsInternalRelease"
0x14041228c  mov     [rbp+20h+var_60], 4000004h
0x140412293  mov     [rbp+20h+var_70], rax
0x140412297  lea     r8, [rbp+20h+var_80]
0x14041229b  lea     rax, ?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1404122a2  mov     [rbp+20h+var_50], 4
0x1404122a9  lea     ecx, [r9+2]
0x1404122ad  mov     [rbp+20h+var_68], rax
0x1404122b1  lea     rdx, Path; "GraphicsDrivers"
0x1404122b8  mov     [rbp+20h+var_58], rax
0x1404122bc  mov     [rbp+20h+var_48], r12
0x1404122c0  mov     [rbp+20h+var_40], r12d
0x1404122c4  mov     [rbp+20h+var_38], r12
0x1404122c8  movups  [rbp+20h+var_30], xmm0
0x1404122cc  mov     qword ptr [rsp+120h+Flags], r12
0x1404122d1  movups  [rbp+20h+var_20], xmm0
0x1404122d5  call    cs:__imp_RtlQueryRegistryValuesEx
0x1404122dc  nop     dword ptr [rax+rax+00h]
0x1404122e1  cmp     cs:?g_IsInternalRelease@@3EA, r12b; uchar g_IsInternalRelease
0x1404122e8  setnz   al
0x1404122eb  mov     cs:?g_IsInternalRelease@@3EA, al; uchar g_IsInternalRelease
0x1404122f1  mov     cs:?g_IsInternalReleaseOrDbg@@3EA, al; uchar g_IsInternalReleaseOrDbg
0x1404122f7  call    cs:__imp_RtlGetSuiteMask
0x1404122fe  nop     dword ptr [rax+rax+00h]
0x140412303  and     eax, 110h
0x140412308  cmp     eax, 10h
0x14041230b  setz    cs:?g_bSkuSupportMultipleUsers@@3EA; uchar g_bSkuSupportMultipleUsers
0x140412312  call    wil_InitializeFeatureStaging
0x140412317  mov     rcx, r13
0x14041231a  call    InitializeTelemetryAssertsKMByDriverObject
0x14041231f  call    cs:__imp_WdInitialize
0x140412326  nop     dword ptr [rax+rax+00h]
0x14041232b  call    ?CreateGlobal@DXGGLOBAL@@SAJXZ; DXGGLOBAL::CreateGlobal(void)
0x140412330  test    eax, eax
0x140412332  js      loc_14041278E
0x140412338  call    DpiInitializeGlobalState
0x14041233d  test    eax, eax
0x14041233f  js      loc_14041278E
0x140412345  call    ?CreateGlobal@CCD_BTL@@SAJXZ; CCD_BTL::CreateGlobal(void)
0x14041234a  test    eax, eax
0x14041234c  js      loc_14041278E
0x140412352  call    ?DxgkInitializeTelemetry@@YAXXZ; DxgkInitializeTelemetry(void)
0x140412357  xor     r9d, r9d
0x14041235a  mov     [rsp+120h+Size], r12
0x14041235f  lea     rax, ?WnfScreenOnCallback@@YAJPEAU_EX_WNF_SUBSCRIPTION@@PEBU_WNF_STATE_NAME@@KKPEBU_WNF_TYPE_ID@@PEAX@Z; WnfScreenOnCallback(_EX_WNF_SUBSCRIPTION *,_WNF_STATE_NAME const *,ulong,ulong,_WNF_TYPE_ID const *,void *)
0x140412366  lea     rdx, WNF_SRUM_SCREENONSTUDY_SESSION
0x14041236d  mov     qword ptr [rsp+120h+Flags], rax
0x140412372  lea     rcx, ?gScreenStudyEventSubscription@@3PEAU_EX_WNF_SUBSCRIPTION@@EA; _EX_WNF_SUBSCRIPTION * gScreenStudyEventSubscription
0x140412379  lea     r8d, [r9+1]
0x14041237d  call    cs:__imp_ExSubscribeWnfStateChange
0x140412384  nop     dword ptr [rax+rax+00h]
0x140412389  test    eax, eax
0x14041238b  jns     short loc_1404123E5
0x14041238d  movsxd  rbx, eax
0x140412390  mov     ecx, 2
0x140412395  mov     rdx, rbx
0x140412398  call    cs:__imp_WdLogSingleEntry1
0x14041239f  nop     dword ptr [rax+rax+00h]
0x1404123a4  mov     [rsp+120h+DeviceObject], r12
0x1404123a9  lea     r9, aExsubscribewnf; "ExSubscribeWnfStateChange failed, retur"...
0x1404123b0  mov     qword ptr [rsp+120h+Depth], r12
0x1404123b5  or      r8d, 0FFFFFFFFh
0x1404123b9  mov     qword ptr [rsp+120h+Tag], r12
0x1404123be  mov     edx, 40000h
0x1404123c3  mov     [rsp+120h+Size], r12; Exclusive
0x1404123c8  xor     ecx, ecx
0x1404123ca  mov     qword ptr [rsp+120h+Flags], rbx
0x1404123cf  mov     cs:WdLogGlobalForLineNumber, 1C7h
0x1404123d9  call    DxgkLogInternalTriageEvent
0x1404123de  mov     cs:?gScreenStudyEventSubscription@@3PEAU_EX_WNF_SUBSCRIPTION@@EA, r12; _EX_WNF_SUBSCRIPTION * gScreenStudyEventSubscription
0x1404123e5  lea     r8, DxgkControlGuid_Context
0x1404123ec  mov     cs:bTracingEnabled, r12b
0x1404123f3  lea     rbx, DxgkControlGuid
0x1404123fa  mov     r9, r8
0x1404123fd  mov     rcx, rbx
0x140412400  call    McGenEventRegister_EtwRegister
0x140412405  test    byte ptr cs:qword_14015C500, 2
0x14041240c  mov     [rsp+120h+var_D0], 0FFFFFFFFh
0x140412414  mov     [rsp+120h+var_C8], r12
0x140412419  jz      short loc_14041243F
0x14041241b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140412422  mov     [rsp+120h+var_C0], 1
0x140412427  mov     [rsp+120h+var_D0], r12d
0x14041242c  jz      short loc_140412444
0x14041242e  xor     r9d, r9d
0x140412431  lea     rdx, EventProfilerEnter
0x140412438  call    McTemplateK0q_EtwWriteTransfer
0x14041243d  jmp     short loc_140412444
0x14041243f  mov     [rsp+120h+var_C0], r12b
0x140412444  xor     edx, edx
0x140412446  lea     rcx, [rsp+120h+var_D0]
0x14041244b  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140412450  lea     rax, Dxgk_WDI_NotifyUser
0x140412457  mov     [rsp+120h+var_B8], rbx
0x14041245c  lea     rcx, [rsp+120h+var_B8]
0x140412461  mov     [rsp+120h+var_B0], rax
0x140412466  call    cs:__imp_WdDiagInit
0x14041246d  nop     dword ptr [rax+rax+00h]
0x140412472  xorps   xmm0, xmm0
0x140412475  lea     rdx, aDeviceDxgkrnl_0; "\\Device\\DxgKrnl"
0x14041247c  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x140412480  movups  xmmword ptr [rbp+20h+DestinationString.Length], xmm0
0x140412484  call    cs:__imp_RtlInitUnicodeString
0x14041248b  nop     dword ptr [rax+rax+00h]
0x140412490  lea     rax, DxgkCreateClose
0x140412497  xorps   xmm0, xmm0
0x14041249a  mov     [r13+70h], rax
0x14041249e  lea     rdx, aDPAGrgwS15830; "D:P(A;;GRGW;;;S-1-5-83-0)"
0x1404124a5  mov     [r13+80h], rax
0x1404124ac  lea     rcx, [rsp+120h+DefaultSDDLString]; DestinationString
0x1404124b1  lea     rax, DxgkDeviceIoctl
0x1404124b8  mov     [r13+0E0h], rax
0x1404124bf  lea     rax, DxgkInternalDeviceIoctl
0x1404124c6  mov     [r13+0E8h], rax
0x1404124cd  lea     rax, DxgkShutdown
0x1404124d4  mov     [r13+0F0h], rax
0x1404124db  lea     rax, DxgkUnload
0x1404124e2  mov     [r13+68h], rax
0x1404124e6  movups  xmmword ptr [rsp+120h+DefaultSDDLString.Length], xmm0
0x1404124eb  call    cs:__imp_RtlInitUnicodeString
0x1404124f2  nop     dword ptr [rax+rax+00h]
0x1404124f7  lea     rax, ?g_pDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * g_pDeviceObject
0x1404124fe  mov     r9d, 22h ; '"'; DeviceType
0x140412504  mov     [rsp+120h+DeviceObject], rax; DeviceObject
0x140412509  lea     r8, [rbp+20h+DestinationString]; DeviceName
0x14041250d  lea     rax, GUID_SD_DXGKRNL_DRIVER_OBJECT
0x140412514  xor     edx, edx; DeviceExtensionSize
0x140412516  mov     qword ptr [rsp+120h+Depth], rax; DeviceClassGuid
0x14041251b  mov     rcx, r13; DriverObject
0x14041251e  lea     rax, [rsp+120h+DefaultSDDLString]
0x140412523  mov     qword ptr [rsp+120h+Tag], rax; DefaultSDDLString
0x140412528  mov     [rsp+120h+Flags], 100h; DeviceCharacteristics
0x140412530  call    WdmlibIoCreateDeviceSecure
0x140412535  movsxd  rdi, eax
0x140412538  test    eax, eax
0x14041253a  jns     short loc_14041255F
0x14041253c  mov     rdx, rdi
0x14041253f  mov     ecx, 3
0x140412544  call    cs:__imp_WdLogSingleEntry1
0x14041254b  nop     dword ptr [rax+rax+00h]
0x140412550  mov     cs:WdLogGlobalForLineNumber, 1FCh
0x14041255a  jmp     loc_1404126BA
0x14041255f  call    DxgkInitialPower
0x140412564  movsxd  rdi, eax
0x140412567  test    eax, eax
0x140412569  jns     short loc_14041258E
0x14041256b  mov     rdx, rdi
0x14041256e  mov     ecx, 3
0x140412573  call    cs:__imp_WdLogSingleEntry1
0x14041257a  nop     dword ptr [rax+rax+00h]
0x14041257f  mov     cs:WdLogGlobalForLineNumber, 209h
0x140412589  jmp     loc_1404126BA
0x14041258e  call    ?MonitorInitializeGlobal@@YAJXZ; MonitorInitializeGlobal(void)
0x140412593  movsxd  rdi, eax
0x140412596  test    eax, eax
0x140412598  jns     short loc_1404125BD
0x14041259a  mov     rdx, rdi
0x14041259d  mov     ecx, 3
0x1404125a2  call    cs:__imp_WdLogSingleEntry1
0x1404125a9  nop     dword ptr [rax+rax+00h]
0x1404125ae  mov     cs:WdLogGlobalForLineNumber, 216h
0x1404125b8  jmp     loc_1404126BA
0x1404125bd  call    ?SysMmInitializeGlobal@@YAXXZ; SysMmInitializeGlobal(void)
0x1404125c2  call    ?DxgkInitTest@@YAXXZ; DxgkInitTest(void)
0x1404125c7  call    ?DxgDbgInit@@YAXXZ; DxgDbgInit(void)
  ... truncated ...
```
