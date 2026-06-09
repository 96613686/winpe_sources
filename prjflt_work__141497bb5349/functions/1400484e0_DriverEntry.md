# DriverEntry

- ea: `0x1400484e0`
- end: `0x1400489eb`
- name: `DriverEntry`
- size: `1291`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140048010`

## callees

- `0x140009988`
- `0x140009a00`
- `0x140009a44`
- `0x140009b2c`
- `0x14000d128`
- `0x140036f5c`
- `0x140048078`
- `0x1400484e0`
- `0x1400489f4`
- `0x140048d4c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400486b8`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400486b8`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400486db`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400486db`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140048959`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140048959`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004879a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400487cd`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400487fc`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004882f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140048863`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140048892`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400488c1`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400488f0`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140048923`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004879a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400487cd`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400487fc`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004882f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140048863`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140048892`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400488c1`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400488f0`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140048923`
- `ntoskrnl!KeInitializeEvent` at `0x140048530`
- `ntoskrnl!KeInitializeEvent` at `0x140048530`
- `FLTMGR!FltGetRoutineAddress` at `0x1400485bb`
- `FLTMGR!FltGetRoutineAddress` at `0x1400485bb`
- `FLTMGR!FltUnregisterFilter` at `0x14004869b`
- `FLTMGR!FltUnregisterFilter` at `0x14004869b`
- `FLTMGR!FltCloseCommunicationPort` at `0x140048683`
- `FLTMGR!FltCloseCommunicationPort` at `0x140048683`
- `FLTMGR!FltStartFiltering` at `0x14004896c`
- `FLTMGR!FltStartFiltering` at `0x14004896c`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x14004873e`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140048767`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x14004873e`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140048767`
- `FLTMGR!FltRegisterFilter` at `0x1400485eb`
- `FLTMGR!FltRegisterFilter` at `0x1400485eb`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // eax
  int v5; // edx
  int v6; // r8d
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  NTSTATUS inited; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  NTSTATUS started; // eax

  wil_InitializeFeatureStaging();
  PrjfTelemetryAndTracingInit((__int64)DriverObject, (__int64)RegistryPath);
  FastMutex.Owner = 0;
  FastMutex.Count = 1;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  v4 = PrjfSetConfiguration(RegistryPath);
  if ( v4 < 0 && ((xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
  {
    LOBYTE(v5) = xmmword_14001A3D0 & 2;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      513,
      v5,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      1,
      35,
      (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
      152,
      v4);
  }
  PrjfFltQueryInformationByName = (__int64)FltGetRoutineAddress("FltQueryInformationByName");
  if ( !PrjfFltQueryInformationByName )
    byte_14001ABCD = 1;
  v7 = FltRegisterFilter(DriverObject, &FilterRegistration, &Globals);
  inited = v7;
  if ( v7 < 0 )
  {
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = xmmword_14001A3D0 & 2;
    if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        513,
        v8,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        1,
        36,
        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        171,
        v7);
    goto LABEL_11;
  }
  McGenEventRegister_EtwRegister();
  inited = PrjfInitCommunicationPort(v14, v13);
  if ( inited < 0 )
  {
LABEL_11:
    if ( (Microsoft_Windows_ProjFS_FilterEnableBits & 1) != 0 )
      McTemplateK0d_EtwWriteTransfer(v9, v8, v10, (unsigned int)inited);
    if ( ServerPort )
      FltCloseCommunicationPort(ServerPort);
    if ( Globals )
      FltUnregisterFilter(Globals);
    PrjfTelemetryAndTracingCleanup();
    if ( g_wil_details_featureChangeNotification )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      g_wil_details_featureChangeNotification = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
    return inited;
  }
  FltInitExtraCreateParameterLookasideList(Globals, qword_14001A640, 0, 0x10u, 0x6F724A50u);
  FltInitExtraCreateParameterLookasideList(Globals, qword_14001A5C0, 0, 0x58u, 0x6F724A50u);
  ExInitializePagedLookasideList(&stru_14001A6C0, 0, 0, 0, 0x30u, 0x62724A50u, 0);
  ExInitializePagedLookasideList(&stru_14001A740, 0, 0, 0, 0x40u, 0x65634A50u, 0);
  ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0x58u, 0x65724A50u, 0);
  ExInitializePagedLookasideList(&stru_14001A840, 0, 0, 0, 0x48u, 0x6C634A50u, 0);
  ExInitializePagedLookasideList(&stru_14001A8C0, 0, 0, 0, 0x50u, 0x6E654A50u, 0);
  ExInitializePagedLookasideList(&stru_14001A940, 0, 0, 0, 0x27Cu, 0x6E654A50u, 0);
  ExInitializePagedLookasideList(&stru_14001A9C0, 0, 0, 0, 0x1014u, 0x6E654A50u, 0);
  ExInitializePagedLookasideList(&stru_14001AA40, 0, 0, 0, 0x10014u, 0x6E654A50u, 0);
  ExInitializePagedLookasideList(&stru_14001AAC0, 0, 0, 0, 0x790u, 0x62634A50u, 0);
  ExInitializeNPagedLookasideList(&stru_14001AB40, 0, 0, 0x200u, 0x130u, 0x63654A50u, 0);
  started = FltStartFiltering(Globals);
  inited = started;
  if ( started < 0 )
  {
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v8) = xmmword_14001A3D0 & 2;
    if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        513,
        v8,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        1,
        37,
        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        32,
        started);
    goto LABEL_11;
  }
  if ( (Microsoft_Windows_ProjFS_FilterEnableBits & 2) != 0 )
    McTemplateK0_EtwWriteTransfer(v9, ProjFsDriverEntrySuccess);
  return inited;
}

```

## disassembly

```asm
0x1400484e0  push    rbx
0x1400484e2  push    rdi
0x1400484e3  push    r12
0x1400484e5  push    r15
0x1400484e7  sub     rsp, 68h
0x1400484eb  mov     rbx, rdx
0x1400484ee  mov     rdi, rcx
0x1400484f1  call    wil_InitializeFeatureStaging
0x1400484f6  mov     rdx, rbx
0x1400484f9  mov     rcx, rdi
0x1400484fc  call    PrjfTelemetryAndTracingInit
0x140048501  mov     r15d, 1
0x140048507  mov     cs:FastMutex.Owner, 0
0x140048512  mov     edx, r15d; Type
0x140048515  mov     cs:FastMutex.Count, r15d
0x14004851c  xor     r8d, r8d; State
0x14004851f  mov     cs:FastMutex.Contention, 0
0x140048529  lea     rcx, FastMutex.Event; Event
0x140048530  call    cs:__imp_KeInitializeEvent
0x140048537  nop     dword ptr [rax+rax+00h]
0x14004853c  mov     rcx, rbx
0x14004853f  call    PrjfSetConfiguration
0x140048544  lea     r12, WPP_RECORDER_INITIALIZED
0x14004854b  lea     r10, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140048552  lea     r11, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140048559  test    eax, eax
0x14004855b  jns     short loc_1400485B4
0x14004855d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140048564  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14004856a  setnz   r8b
0x14004856e  and     dl, 2
0x140048571  jnz     short loc_140048578
0x140048573  test    r8b, r8b
0x140048576  jz      short loc_1400485B4
0x140048578  mov     r9, cs:WPP_GLOBAL_Control
0x14004857f  mov     ecx, 201h
0x140048584  mov     [rsp+88h+var_38], eax
0x140048588  mov     [rsp+88h+var_40], 598h
0x140048590  mov     [rsp+88h+var_48], r10
0x140048595  mov     r9, [r9+40h]
0x140048599  mov     [rsp+88h+var_50], r11
0x14004859e  mov     [rsp+88h+Depth], 23h ; '#'
0x1400485a5  mov     [rsp+88h+var_60], r15d
0x1400485aa  mov     byte ptr [rsp+88h+Tag], 2
0x1400485af  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400485b4  lea     rcx, FltMgrRoutineName; "FltQueryInformationByName"
0x1400485bb  call    cs:__imp_FltGetRoutineAddress
0x1400485c2  nop     dword ptr [rax+rax+00h]
0x1400485c7  mov     cs:PrjfFltQueryInformationByName, rax
0x1400485ce  test    rax, rax
0x1400485d1  jnz     short loc_1400485DA
0x1400485d3  mov     cs:byte_14001ABCD, r15b
0x1400485da  lea     r8, Globals; RetFilter
0x1400485e1  mov     rcx, rdi; Driver
0x1400485e4  lea     rdx, FilterRegistration; Registration
0x1400485eb  call    cs:__imp_FltRegisterFilter
0x1400485f2  nop     dword ptr [rax+rax+00h]
0x1400485f7  mov     ebx, eax
0x1400485f9  test    eax, eax
0x1400485fb  jns     loc_14004870A
0x140048601  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140048608  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14004860e  setnz   r8b
0x140048612  and     dl, 2
0x140048615  jnz     short loc_14004861C
0x140048617  test    r8b, r8b
0x14004861a  jz      short loc_140048666
0x14004861c  mov     [rsp+88h+var_38], eax
0x140048620  lea     r9, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140048627  mov     [rsp+88h+var_40], 5ABh
0x14004862f  mov     [rsp+88h+var_48], r9
0x140048634  lea     r9, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14004863b  mov     [rsp+88h+var_50], r9
0x140048640  mov     [rsp+88h+Depth], 24h ; '$'
0x140048647  mov     r9, cs:WPP_GLOBAL_Control
0x14004864e  mov     ecx, 201h
0x140048653  mov     [rsp+88h+var_60], r15d
0x140048658  mov     byte ptr [rsp+88h+Tag], 2
0x14004865d  mov     r9, [r9+40h]
0x140048661  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140048666  test    cs:Microsoft_Windows_ProjFS_FilterEnableBits, r15b
0x14004866d  jz      short loc_140048677
0x14004866f  mov     r9d, ebx
0x140048672  call    McTemplateK0d_EtwWriteTransfer
0x140048677  mov     rcx, cs:ServerPort; ServerPort
0x14004867e  test    rcx, rcx
0x140048681  jz      short loc_14004868F
0x140048683  call    cs:__imp_FltCloseCommunicationPort
0x14004868a  nop     dword ptr [rax+rax+00h]
0x14004868f  mov     rcx, cs:Globals; Filter
0x140048696  test    rcx, rcx
0x140048699  jz      short loc_1400486A7
0x14004869b  call    cs:__imp_FltUnregisterFilter
0x1400486a2  nop     dword ptr [rax+rax+00h]
0x1400486a7  call    PrjfTelemetryAndTracingCleanup
0x1400486ac  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400486b3  test    rcx, rcx
0x1400486b6  jz      short loc_1400486CF
0x1400486b8  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400486bf  nop     dword ptr [rax+rax+00h]
0x1400486c4  mov     cs:g_wil_details_featureChangeNotification, 0
0x1400486cf  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400486d6  test    rcx, rcx
0x1400486d9  jz      short loc_1400486F2
0x1400486db  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400486e2  nop     dword ptr [rax+rax+00h]
0x1400486e7  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400486f2  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400486fc  mov     eax, ebx
0x1400486fe  add     rsp, 68h
0x140048702  pop     r15
0x140048704  pop     r12
0x140048706  pop     rdi
0x140048707  pop     rbx
0x140048708  retn
0x14004870a  call    McGenEventRegister_EtwRegister
0x14004870f  call    PrjfInitCommunicationPort
0x140048714  mov     ebx, eax
0x140048716  test    eax, eax
0x140048718  js      loc_140048666
0x14004871e  mov     rcx, cs:Globals; Filter
0x140048725  lea     rdx, qword_14001A640; Lookaside
0x14004872c  mov     ebx, 6F724A50h
0x140048731  mov     r9d, 10h; Size
0x140048737  xor     r8d, r8d; Flags
0x14004873a  mov     [rsp+88h+Tag], ebx; Tag
0x14004873e  call    cs:__imp_FltInitExtraCreateParameterLookasideList
0x140048745  nop     dword ptr [rax+rax+00h]
0x14004874a  mov     rcx, cs:Globals; Filter
0x140048751  lea     rdx, qword_14001A5C0; Lookaside
0x140048758  mov     [rsp+88h+Tag], ebx; Tag
0x14004875c  xor     r8d, r8d; Flags
0x14004875f  mov     ebx, 58h ; 'X'
0x140048764  mov     r9d, ebx; Size
0x140048767  call    cs:__imp_FltInitExtraCreateParameterLookasideList
0x14004876e  nop     dword ptr [rax+rax+00h]
0x140048773  xor     eax, eax
0x140048775  lea     rcx, stru_14001A6C0; Lookaside
0x14004877c  mov     [rsp+88h+Depth], ax; Depth
0x140048781  xor     r9d, r9d; Flags
0x140048784  mov     [rsp+88h+var_60], 62724A50h; Tag
0x14004878c  xor     r8d, r8d; Free
0x14004878f  xor     edx, edx; Allocate
0x140048791  mov     qword ptr [rsp+88h+Tag], 30h ; '0'; Size
0x14004879a  call    cs:__imp_ExInitializePagedLookasideList
0x1400487a1  nop     dword ptr [rax+rax+00h]
0x1400487a6  xor     eax, eax
0x1400487a8  lea     rcx, stru_14001A740; Lookaside
0x1400487af  mov     [rsp+88h+Depth], ax; Depth
0x1400487b4  xor     r9d, r9d; Flags
0x1400487b7  mov     [rsp+88h+var_60], 65634A50h; Tag
0x1400487bf  xor     r8d, r8d; Free
0x1400487c2  xor     edx, edx; Allocate
0x1400487c4  mov     qword ptr [rsp+88h+Tag], 40h ; '@'; Size
0x1400487cd  call    cs:__imp_ExInitializePagedLookasideList
0x1400487d4  nop     dword ptr [rax+rax+00h]
0x1400487d9  xor     eax, eax
0x1400487db  lea     rcx, Lookaside; Lookaside
0x1400487e2  mov     [rsp+88h+Depth], ax; Depth
0x1400487e7  xor     r9d, r9d; Flags
0x1400487ea  mov     [rsp+88h+var_60], 65724A50h; Tag
0x1400487f2  xor     r8d, r8d; Free
0x1400487f5  xor     edx, edx; Allocate
0x1400487f7  mov     qword ptr [rsp+88h+Tag], rbx; Size
0x1400487fc  call    cs:__imp_ExInitializePagedLookasideList
0x140048803  nop     dword ptr [rax+rax+00h]
0x140048808  xor     eax, eax
0x14004880a  lea     rcx, stru_14001A840; Lookaside
0x140048811  mov     [rsp+88h+Depth], ax; Depth
0x140048816  xor     r9d, r9d; Flags
0x140048819  mov     [rsp+88h+var_60], 6C634A50h; Tag
0x140048821  xor     r8d, r8d; Free
0x140048824  xor     edx, edx; Allocate
0x140048826  mov     qword ptr [rsp+88h+Tag], 48h ; 'H'; Size
0x14004882f  call    cs:__imp_ExInitializePagedLookasideList
0x140048836  nop     dword ptr [rax+rax+00h]
0x14004883b  xor     eax, eax
0x14004883d  lea     rcx, stru_14001A8C0; Lookaside
0x140048844  mov     [rsp+88h+Depth], ax; Depth
0x140048849  mov     ebx, 6E654A50h
0x14004884e  mov     [rsp+88h+var_60], ebx; Tag
0x140048852  xor     r9d, r9d; Flags
0x140048855  xor     r8d, r8d; Free
0x140048858  mov     qword ptr [rsp+88h+Tag], 50h ; 'P'; Size
0x140048861  xor     edx, edx; Allocate
0x140048863  call    cs:__imp_ExInitializePagedLookasideList
0x14004886a  nop     dword ptr [rax+rax+00h]
0x14004886f  xor     eax, eax
0x140048871  lea     rcx, stru_14001A940; Lookaside
0x140048878  mov     [rsp+88h+Depth], ax; Depth
0x14004887d  xor     r9d, r9d; Flags
0x140048880  mov     [rsp+88h+var_60], ebx; Tag
0x140048884  xor     r8d, r8d; Free
0x140048887  xor     edx, edx; Allocate
0x140048889  mov     qword ptr [rsp+88h+Tag], 27Ch; Size
0x140048892  call    cs:__imp_ExInitializePagedLookasideList
0x140048899  nop     dword ptr [rax+rax+00h]
0x14004889e  xor     eax, eax
0x1400488a0  lea     rcx, stru_14001A9C0; Lookaside
0x1400488a7  mov     [rsp+88h+Depth], ax; Depth
0x1400488ac  xor     r9d, r9d; Flags
0x1400488af  mov     [rsp+88h+var_60], ebx; Tag
0x1400488b3  xor     r8d, r8d; Free
0x1400488b6  xor     edx, edx; Allocate
0x1400488b8  mov     qword ptr [rsp+88h+Tag], 1014h; Size
0x1400488c1  call    cs:__imp_ExInitializePagedLookasideList
0x1400488c8  nop     dword ptr [rax+rax+00h]
0x1400488cd  xor     eax, eax
0x1400488cf  mov     [rsp+88h+Depth], ax; Depth
0x1400488d4  mov     [rsp+88h+var_60], ebx; Tag
0x1400488d8  xor     r9d, r9d; Flags
0x1400488db  mov     qword ptr [rsp+88h+Tag], 10014h; Size
0x1400488e4  xor     r8d, r8d; Free
0x1400488e7  lea     rcx, stru_14001AA40; Lookaside
0x1400488ee  xor     edx, edx; Allocate
0x1400488f0  call    cs:__imp_ExInitializePagedLookasideList
0x1400488f7  nop     dword ptr [rax+rax+00h]
0x1400488fc  xor     eax, eax
0x1400488fe  lea     rcx, stru_14001AAC0; Lookaside
0x140048905  mov     [rsp+88h+Depth], ax; Depth
0x14004890a  xor     r9d, r9d; Flags
0x14004890d  mov     [rsp+88h+var_60], 62634A50h; Tag
0x140048915  xor     r8d, r8d; Free
0x140048918  xor     edx, edx; Allocate
0x14004891a  mov     qword ptr [rsp+88h+Tag], 790h; Size
0x140048923  call    cs:__imp_ExInitializePagedLookasideList
0x14004892a  nop     dword ptr [rax+rax+00h]
0x14004892f  xor     eax, eax
0x140048931  lea     rcx, stru_14001AB40; Lookaside
0x140048938  mov     [rsp+88h+Depth], ax; Depth
0x14004893d  mov     r9d, 200h; Flags
0x140048943  mov     [rsp+88h+var_60], 63654A50h; Tag
0x14004894b  xor     r8d, r8d; Free
0x14004894e  xor     edx, edx; Allocate
0x140048950  mov     qword ptr [rsp+88h+Tag], 130h; Size
0x140048959  call    cs:__imp_ExInitializeNPagedLookasideList
0x140048960  nop     dword ptr [rax+rax+00h]
0x140048965  mov     rcx, cs:Globals; Filter
0x14004896c  call    cs:__imp_FltStartFiltering
0x140048973  nop     dword ptr [rax+rax+00h]
0x140048978  mov     ebx, eax
0x14004897a  test    eax, eax
0x14004897c  jns     short loc_1400489CD
0x14004897e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140048985  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14004898b  setnz   r8b
0x14004898f  and     dl, 2
0x140048992  jnz     short loc_14004899D
0x140048994  test    r8b, r8b
0x140048997  jz      loc_140048666
0x14004899d  mov     [rsp+88h+var_38], eax
0x1400489a1  lea     r9, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400489a8  mov     [rsp+88h+var_40], 620h
0x1400489b0  mov     [rsp+88h+var_48], r9
0x1400489b5  lea     r9, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x1400489bc  mov     [rsp+88h+var_50], r9
0x1400489c1  mov     [rsp+88h+Depth], 25h ; '%'
0x1400489c8  jmp     loc_140048647
0x1400489cd  test    cs:Microsoft_Windows_ProjFS_FilterEnableBits, 2
0x1400489d4  jz      loc_1400486FC
0x1400489da  lea     rdx, ProjFsDriverEntrySuccess
0x1400489e1  call    McTemplateK0_EtwWriteTransfer
0x1400489e6  jmp     loc_1400486FC
```
