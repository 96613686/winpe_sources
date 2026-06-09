# DriverEntry

- ea: `0x140018078`
- end: `0x1400188e9`
- name: `DriverEntry`
- size: `2161`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140018010`

## callees

- `0x14000374c`
- `0x140003920`
- `0x140003d80`
- `0x14000d5cc`
- `0x14000e370`
- `0x14000ec10`
- `0x140010050`
- `0x140010f10`
- `0x140014940`
- `0x1400166b4`
- `0x140018078`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x1400186c1`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1400186c1`
- `ntoskrnl!EtwRegister` at `0x1400186f6`
- `ntoskrnl!EtwRegister` at `0x1400186f6`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001866e`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001866e`
- `ntoskrnl!PfFileInfoNotify` at `0x14001878b`
- `ntoskrnl!PfFileInfoNotify` at `0x14001881c`
- `ntoskrnl!PfFileInfoNotify` at `0x14001878b`
- `ntoskrnl!PfFileInfoNotify` at `0x14001881c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018686`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018686`
- `ntoskrnl!ExAllocateTimer` at `0x140018853`
- `ntoskrnl!ExAllocateTimer` at `0x140018853`
- `ntoskrnl!ExSetTimer` at `0x1400188c0`
- `ntoskrnl!ExSetTimer` at `0x1400188c0`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140018754`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140018754`
- `FLTMGR!FltStartFiltering` at `0x1400188d3`
- `FLTMGR!FltStartFiltering` at `0x1400188d3`
- `FLTMGR!FltRegisterFilter` at `0x14001871f`
- `FLTMGR!FltRegisterFilter` at `0x14001871f`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v3; // rdx
  NTSTATUS started; // edi
  __int64 v5; // r8
  ULONG v6; // edx
  ULONG v7; // r9d
  __int64 Timer; // rax
  ULONG Tag; // [rsp+20h] [rbp-3E8h]
  BOOLEAN v11; // [rsp+28h] [rbp-3E0h]
  const UNICODE_STRING *v12; // [rsp+30h] [rbp-3D8h]
  const GUID *v13; // [rsp+38h] [rbp-3D0h]
  _BYTE v14[24]; // [rsp+50h] [rbp-3B8h] BYREF
  unsigned __int64 v15; // [rsp+68h] [rbp-3A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-398h] BYREF
  FLT_REGISTRATION Registration; // [rsp+80h] [rbp-388h] BYREF
  __int64 v18; // [rsp+E8h] [rbp-320h]
  char v19; // [rsp+F0h] [rbp-318h] BYREF
  int v20; // [rsp+F4h] [rbp-314h]
  __int64 (__fastcall *v21)(); // [rsp+F8h] [rbp-310h]
  __int64 (__fastcall *v22)(PFLT_CALLBACK_DATA); // [rsp+100h] [rbp-308h]
  __int64 v23; // [rsp+108h] [rbp-300h]
  char v24; // [rsp+110h] [rbp-2F8h]
  int v25; // [rsp+114h] [rbp-2F4h]
  __int64 (__fastcall *v26)(); // [rsp+118h] [rbp-2F0h]
  __int64 (__fastcall *v27)(); // [rsp+120h] [rbp-2E8h]
  __int64 v28; // [rsp+128h] [rbp-2E0h]
  char v29; // [rsp+130h] [rbp-2D8h]
  int v30; // [rsp+134h] [rbp-2D4h]
  __int64 (__fastcall *v31)(); // [rsp+138h] [rbp-2D0h]
  __int64 (__fastcall *v32)(); // [rsp+140h] [rbp-2C8h]
  __int64 v33; // [rsp+148h] [rbp-2C0h]
  char v34; // [rsp+150h] [rbp-2B8h]
  int v35; // [rsp+154h] [rbp-2B4h]
  __int64 (__fastcall *v36)(); // [rsp+158h] [rbp-2B0h]
  __int64 (__fastcall *v37)(); // [rsp+160h] [rbp-2A8h]
  __int64 v38; // [rsp+168h] [rbp-2A0h]
  char v39; // [rsp+170h] [rbp-298h]
  int v40; // [rsp+174h] [rbp-294h]
  __int64 (__fastcall *v41)(); // [rsp+178h] [rbp-290h]
  __int64 (__fastcall *v42)(); // [rsp+180h] [rbp-288h]
  __int64 v43; // [rsp+188h] [rbp-280h]
  char v44; // [rsp+190h] [rbp-278h]
  int v45; // [rsp+194h] [rbp-274h]
  __int64 (__fastcall *v46)(); // [rsp+198h] [rbp-270h]
  FLT_POSTOP_CALLBACK_STATUS (__stdcall *v47)(PFLT_CALLBACK_DATA, PCFLT_RELATED_OBJECTS, PVOID, FLT_POST_OPERATION_FLAGS); // [rsp+1A0h] [rbp-268h]
  __int64 v48; // [rsp+1A8h] [rbp-260h]
  char v49; // [rsp+1B0h] [rbp-258h]
  int v50; // [rsp+1B4h] [rbp-254h]
  __int64 (__fastcall *v51)(); // [rsp+1B8h] [rbp-250h]
  FLT_POSTOP_CALLBACK_STATUS (__stdcall *v52)(PFLT_CALLBACK_DATA, PCFLT_RELATED_OBJECTS, PVOID, FLT_POST_OPERATION_FLAGS); // [rsp+1C0h] [rbp-248h]
  __int64 v53; // [rsp+1C8h] [rbp-240h]
  char v54; // [rsp+1D0h] [rbp-238h]
  int v55; // [rsp+1D4h] [rbp-234h]
  __int64 (__fastcall *v56)(); // [rsp+1D8h] [rbp-230h]
  __int64 (__fastcall *v57)(); // [rsp+1E0h] [rbp-228h]
  __int64 v58; // [rsp+1E8h] [rbp-220h]
  char v59; // [rsp+1F0h] [rbp-218h]
  int v60; // [rsp+1F4h] [rbp-214h]
  __int64 (__fastcall *v61)(); // [rsp+1F8h] [rbp-210h]
  __int64 (__fastcall *v62)(); // [rsp+200h] [rbp-208h]
  __int64 v63; // [rsp+208h] [rbp-200h]
  char v64; // [rsp+210h] [rbp-1F8h]
  int v65; // [rsp+214h] [rbp-1F4h]
  __int64 (__fastcall *v66)(); // [rsp+218h] [rbp-1F0h]
  __int64 (__fastcall *v67)(); // [rsp+220h] [rbp-1E8h]
  __int64 v68; // [rsp+228h] [rbp-1E0h]
  char v69; // [rsp+230h] [rbp-1D8h]
  int v70; // [rsp+234h] [rbp-1D4h]
  __int64 (__fastcall *v71)(); // [rsp+238h] [rbp-1D0h]
  __int64 (__fastcall *v72)(); // [rsp+240h] [rbp-1C8h]
  __int64 v73; // [rsp+248h] [rbp-1C0h]
  char v74; // [rsp+250h] [rbp-1B8h]
  int v75; // [rsp+254h] [rbp-1B4h]
  __int64 (__fastcall *v76)(); // [rsp+258h] [rbp-1B0h]
  __int64 (__fastcall *v77)(); // [rsp+260h] [rbp-1A8h]
  __int64 v78; // [rsp+268h] [rbp-1A0h]
  char v79; // [rsp+270h] [rbp-198h]
  int v80; // [rsp+274h] [rbp-194h]
  __int64 (__fastcall *v81)(); // [rsp+278h] [rbp-190h]
  __int64 (__fastcall *v82)(); // [rsp+280h] [rbp-188h]
  __int64 v83; // [rsp+288h] [rbp-180h]
  char v84; // [rsp+290h] [rbp-178h]
  int v85; // [rsp+294h] [rbp-174h]
  __int64 (__fastcall *v86)(); // [rsp+298h] [rbp-170h]
  __int64 (__fastcall *v87)(); // [rsp+2A0h] [rbp-168h]
  __int64 v88; // [rsp+2A8h] [rbp-160h]
  char v89; // [rsp+2B0h] [rbp-158h]
  int v90; // [rsp+2B4h] [rbp-154h]
  __int64 (__fastcall *v91)(); // [rsp+2B8h] [rbp-150h]
  __int64 (__fastcall *v92)(); // [rsp+2C0h] [rbp-148h]
  __int64 v93; // [rsp+2C8h] [rbp-140h]
  char v94; // [rsp+2D0h] [rbp-138h]
  int v95; // [rsp+2D4h] [rbp-134h]
  __int64 (__fastcall *v96)(); // [rsp+2D8h] [rbp-130h]
  __int64 (__fastcall *v97)(); // [rsp+2E0h] [rbp-128h]
  __int64 v98; // [rsp+2E8h] [rbp-120h]
  char v99; // [rsp+2F0h] [rbp-118h]
  int v100; // [rsp+2F4h] [rbp-114h]
  __int64 (__fastcall *v101)(); // [rsp+2F8h] [rbp-110h]
  __int64 (__fastcall *v102)(); // [rsp+300h] [rbp-108h]
  __int64 v103; // [rsp+308h] [rbp-100h]
  char v104; // [rsp+310h] [rbp-F8h]
  _BYTE v105[28]; // [rsp+314h] [rbp-F4h] BYREF
  int v106; // [rsp+330h] [rbp-D8h] BYREF
  __int64 (__fastcall *v107)(); // [rsp+338h] [rbp-D0h]
  __int64 v108; // [rsp+340h] [rbp-C8h]
  int v109; // [rsp+348h] [rbp-C0h]
  __int128 v110; // [rsp+350h] [rbp-B8h]
  __int64 v111; // [rsp+360h] [rbp-A8h]
  int v112; // [rsp+368h] [rbp-A0h]
  __int64 (__fastcall *v113)(); // [rsp+370h] [rbp-98h]
  __int64 v114; // [rsp+378h] [rbp-90h]
  int v115; // [rsp+380h] [rbp-88h]
  __int128 v116; // [rsp+388h] [rbp-80h]
  __int64 v117; // [rsp+398h] [rbp-70h]
  __int16 v118; // [rsp+3A0h] [rbp-68h]
  __int128 v119; // [rsp+3A2h] [rbp-66h]
  __int128 v120; // [rsp+3B2h] [rbp-56h]
  _BYTE v121[22]; // [rsp+3C2h] [rbp-46h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = FIPreCreateCallback;
  v15 = 0;
  v22 = FIPostCreateCallback;
  v23 = 0;
  v24 = 18;
  v25 = 0;
  v26 = FIPreCleanupCallback;
  v27 = FIPostCleanupCallback;
  v28 = 0;
  v29 = 2;
  v30 = 0;
  v31 = FIPreCloseCallback;
  v33 = 0;
  v32 = FIPostOperationCommonCallback;
  v34 = 3;
  v35 = 0;
  v38 = 0;
  v36 = FIPreReadWriteCallback;
  v37 = FIPostReadWriteCallback;
  v39 = 4;
  v40 = 0;
  v43 = 0;
  v41 = FIPreReadWriteCallback;
  v42 = FIPostReadWriteCallback;
  v44 = 6;
  v45 = 0;
  v46 = FIPreSetInformationCallback;
  v47 = FIPostSetInformationCallback;
  v48 = 0;
  v49 = 13;
  v50 = 0;
  v51 = FIPreFSControlCallback;
  v52 = FIPostFSControlCallback;
  v53 = 0;
  v54 = 9;
  v55 = 0;
  v56 = FIPreFlushBuffersCallback;
  v58 = 0;
  v57 = FIPostOperationCommonCallback;
  v59 = 12;
  v60 = 0;
  v61 = FIPreDirectoryControlCallback;
  v63 = 0;
  v62 = FIPostOperationCommonCallback;
  v64 = 5;
  v65 = 0;
  v66 = FIPreQueryInformationCallback;
  DestinationString = 0;
  v67 = FIPostOperationCommonCallback;
  memset(v14, 0, sizeof(v14));
  v108 = 80;
  v68 = 0;
  v69 = 27;
  v70 = 0;
  v71 = FIPrePnpCallback;
  v72 = FIPostPnpCallback;
  v73 = 0;
  v74 = -15;
  v75 = 0;
  v76 = FIPreMdlOperationCallback;
  v77 = FIPostOperationCommonCallback;
  v78 = 0;
  v79 = -18;
  v80 = 0;
  v81 = FIPreMdlOperationCallback;
  v82 = FIPostOperationCommonCallback;
  v83 = 0;
  v84 = 21;
  v85 = 0;
  v86 = FIPreSetSecurityCallback;
  v87 = FIPostOperationCommonCallback;
  v88 = 0;
  v89 = 20;
  v90 = 0;
  v91 = FIPreQuerySecurityCallback;
  v92 = FIPostOperationCommonCallback;
  v93 = 0;
  v94 = 8;
  v95 = 0;
  v96 = FIPreSetEACallback;
  v97 = FIPostOperationCommonCallback;
  v98 = 0;
  v99 = 7;
  v100 = 0;
  v101 = FIPreQueryEACallback;
  v102 = FIPostOperationCommonCallback;
  v103 = 0;
  v107 = FIStreamCleanup;
  v106 = 8;
  v109 = 1935886662;
  v110 = 0;
  v111 = 0;
  v113 = FIVolumeCleanup;
  v112 = 2;
  v114 = 512;
  v115 = 1986218310;
  v117 = 0;
  v118 = -1;
  memset(v121, 0, sizeof(v121));
  *(_DWORD *)&Registration.Size = 33751152;
  Registration.Flags = 12;
  Registration.ContextRegistration = (const FLT_CONTEXT_REGISTRATION *)&v106;
  memset(v105, 0, sizeof(v105));
  v104 = 0x80;
  v116 = 0;
  v119 = 0;
  v120 = 0;
  Registration.OperationRegistration = (const FLT_OPERATION_REGISTRATION *)&v19;
  Registration.FilterUnloadCallback = (PFLT_FILTER_UNLOAD_CALLBACK)FIUnload;
  memset(&Registration.InstanceSetupCallback, 0, 72);
  v18 = 0;
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  memset(&FIGlobals, 0, 0x740u);
  qword_140009510 = 0;
  qword_140009398 = (__int64)&qword_140009390;
  qword_140009390 = (__int64)&qword_140009390;
  FIPfOpenAttemptsInitialize(&qword_140009518);
  FIPfOpenAttemptsInitialize(&qword_140009548);
  qword_140009578 = 0;
  qword_140009588 = (__int64)&qword_140009580;
  qword_140009580 = (__int64)&qword_140009580;
  qword_140009760 = 0;
  qword_140009770 = (__int64)&qword_140009768;
  qword_140009768 = (__int64)&qword_140009768;
  qword_140009648 = 0;
  dword_140009650 = 0;
  *(__int64 *)((char *)&qword_140009654 + 4) = (__int64)qword_140009660;
  LODWORD(qword_140009654) = 1024;
  memset64(qword_140009660, (unsigned __int64)&dword_140009650 + 1, 0x20u);
  qword_140009A78 = 0;
  qword_140009A00 = (__int64)qword_140009A08;
  qword_140009940 = 0;
  xmmword_140009948 = 0u;
  qword_1400099D0 = 0;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&FIControlDispatch;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&FIControlDispatch;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&FIControlDispatch;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&FIControlDispatch;
  DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)&FIControlDispatch;
  started = FIGetRegistryParameters(&dword_1400093D0);
  if ( started >= 0 )
  {
    started = FIQueryPhysicalMemorySize(&v15);
    if ( started >= 0 )
    {
      if ( v15 >= 0x3E800000 )
        FIFileInfoStateChange(1, 3);
      KeInitializeSemaphore(&Semaphore, Count, Count);
      RtlInitUnicodeString(&DestinationString, L"\\Device\\FileInfo");
      started = WdmlibIoCreateDeviceSecure(DriverObject, v6, &DestinationString, v7, Tag, v11, v12, v13, &DeviceObject);
      if ( started >= 0 )
      {
        started = IoWMIRegistrationControl(DeviceObject, 0x410001u);
        if ( started >= 0 )
        {
          dword_1400093C0 |= 4u;
          if ( EtwRegister(&FileInfoEventProvider, FIEtwEnableCallback, 0, &qword_140009A28) < 0 )
            qword_140009A28 = 0;
          started = FltRegisterFilter(DriverObject, &Registration, (PFLT_FILTER *)&FIGlobals);
          if ( started >= 0 )
          {
            FltInitExtraCreateParameterLookasideList((PFLT_FILTER)FIGlobals, qword_1400095C0, 0, 0x10u, 0x70634946u);
            dword_1400093C0 |= 1u;
            *(_QWORD *)&v14[12] = 0;
            *(_QWORD *)v14 = 0xC0000000FLL;
            *(_DWORD *)&v14[20] = 0;
            *(_DWORD *)&v14[8] = 8;
            if ( (int)PfFileInfoNotify(v14) < 0 )
              FIPfDisableUntilTickMsSet(&qword_140009598, (unsigned int)dword_1400093D4, &qword_140009510);
            *(_QWORD *)&v14[8] = 8;
            *(_QWORD *)&v14[16] = &qword_1400094E8;
            *(_QWORD *)v14 = 0xA0000000FLL;
            qword_1400094E8 = (__int64)FIPfInterfaceOpen;
            qword_1400094F0 = (__int64)FIPfInterfaceClose;
            qword_1400094F8 = (__int64)&FIPfInterfaceQueryFile;
            qword_140009500 = (__int64)&FIPfInterfaceQueryVolume;
            qword_140009508 = (__int64)FIPfRegisterGlobalBlockNotify;
            if ( (int)PfFileInfoNotify(v14) >= 0 )
              dword_1400093C0 |= 2u;
            qword_140009960 = MEMORY[0xFFFFF78000000014];
            Timer = ExAllocateTimer(FIPfConflictTelemetryPublishTimerCallback, 0, 8);
            qword_1400099C0 = Timer;
            if ( Timer )
            {
              ExSetTimer(Timer, -216000000000LL, 216000000000LL, 0);
              started = FltStartFiltering((PFLT_FILTER)FIGlobals);
              if ( started >= 0 )
                return 0;
            }
            else
            {
              started = -1073741670;
            }
          }
        }
      }
    }
  }
  FIUnload(1, v3, v5);
  return started;
}

```

## disassembly

```asm
0x140018078  mov     r11, rsp
0x14001807b  mov     [r11+10h], rbx
0x14001807f  mov     [r11+18h], rsi
0x140018083  push    rdi
0x140018084  push    r14
0x140018086  push    r15
0x140018088  sub     rsp, 3F0h
0x14001808f  mov     rax, cs:__security_cookie
0x140018096  xor     rax, rsp
0x140018099  mov     [rsp+408h+var_28], rax
0x1400180a1  xor     eax, eax
0x1400180a3  lea     rdi, FIPostOperationCommonCallback
0x1400180aa  mov     [rsp+408h+var_3A8], rax
0x1400180af  lea     rdx, FIPreReadWriteCallback
0x1400180b6  xor     esi, esi
0x1400180b8  lea     rax, FIPreCreateCallback
0x1400180bf  mov     [rsp+408h+var_318], sil
0x1400180c7  mov     rbx, rcx
0x1400180ca  mov     [rsp+408h+var_314], esi
0x1400180d1  lea     rcx, FIPostReadWriteCallback
0x1400180d8  mov     [r11-310h], rax
0x1400180df  xorps   xmm0, xmm0
0x1400180e2  lea     rax, FIPostCreateCallback
0x1400180e9  mov     [rsp+408h+var_3A0], rsi
0x1400180ee  mov     [r11-308h], rax
0x1400180f5  lea     r15d, [rsi+2]
0x1400180f9  xor     eax, eax
0x1400180fb  xorps   xmm1, xmm1
0x1400180fe  mov     [r11-300h], rax
0x140018105  lea     rax, FIPreCleanupCallback
0x14001810c  mov     [rsp+408h+var_2F8], 12h
0x140018114  mov     [rsp+408h+var_2F4], esi
0x14001811b  mov     [r11-2F0h], rax
0x140018122  lea     rax, FIPostCleanupCallback
0x140018129  mov     [r11-2E8h], rax
0x140018130  xor     eax, eax
0x140018132  mov     [r11-2E0h], rax
0x140018139  lea     rax, FIPreCloseCallback
0x140018140  mov     [r11-2D8h], r15b
0x140018147  mov     [rsp+408h+var_2D4], esi
0x14001814e  mov     [r11-2D0h], rax
0x140018155  xor     eax, eax
0x140018157  mov     [r11-2C0h], rax
0x14001815e  mov     [r11-2C8h], rdi
0x140018165  mov     [rsp+408h+var_2B8], 3
0x14001816d  mov     [rsp+408h+var_2B4], esi
0x140018174  mov     [r11-2A0h], rax
0x14001817b  mov     [r11-2B0h], rdx
0x140018182  mov     [r11-2A8h], rcx
0x140018189  mov     [rsp+408h+var_298], 4
0x140018191  mov     [rsp+408h+var_294], esi
0x140018198  mov     [r11-280h], rax
0x14001819f  lea     rax, FIPreSetInformationCallback
0x1400181a6  mov     [r11-290h], rdx
0x1400181ad  mov     [r11-288h], rcx
0x1400181b4  mov     [rsp+408h+var_278], 6
0x1400181bc  mov     [rsp+408h+var_274], esi
0x1400181c3  mov     [r11-270h], rax
0x1400181ca  lea     rax, FIPostSetInformationCallback
0x1400181d1  mov     [r11-268h], rax
0x1400181d8  xor     eax, eax
0x1400181da  mov     [r11-260h], rax
0x1400181e1  lea     rax, FIPreFSControlCallback
0x1400181e8  mov     [rsp+408h+var_258], 0Dh
0x1400181f0  mov     [rsp+408h+var_254], esi
0x1400181f7  mov     [r11-250h], rax
0x1400181fe  lea     rax, FIPostFSControlCallback
0x140018205  mov     [r11-248h], rax
0x14001820c  xor     eax, eax
0x14001820e  mov     [r11-240h], rax
0x140018215  lea     rax, FIPreFlushBuffersCallback
0x14001821c  mov     [rsp+408h+var_238], 9
0x140018224  mov     [rsp+408h+var_234], esi
0x14001822b  mov     [r11-230h], rax
0x140018232  xor     eax, eax
0x140018234  mov     [r11-220h], rax
0x14001823b  lea     rax, FIPreDirectoryControlCallback
0x140018242  mov     [r11-228h], rdi
0x140018249  mov     [rsp+408h+var_218], 0Ch
0x140018251  mov     [rsp+408h+var_214], esi
0x140018258  mov     [r11-210h], rax
0x14001825f  xor     eax, eax
0x140018261  mov     [r11-200h], rax
0x140018268  lea     rax, FIPreQueryInformationCallback
0x14001826f  mov     [r11-208h], rdi
0x140018276  mov     [rsp+408h+var_1F8], 5
0x14001827e  mov     [rsp+408h+var_1F4], esi
0x140018285  mov     [r11-1F0h], rax
0x14001828c  movups  xmmword ptr [rsp+408h+DestinationString.Length], xmm0
0x140018291  mov     [r11-1E8h], rdi
0x140018298  movups  [rsp+408h+var_3B8], xmm1
0x14001829d  xor     eax, eax
0x14001829f  mov     qword ptr [r11-0C8h], 50h ; 'P'
0x1400182aa  mov     [r11-1E0h], rax
0x1400182b1  lea     rcx, FIPreMdlOperationCallback
0x1400182b8  mov     [rsp+408h+var_1D8], 1Bh
0x1400182c0  lea     rax, FIPrePnpCallback
0x1400182c7  mov     [rsp+408h+var_1D4], esi
0x1400182ce  lea     r14d, [rsi+8]
0x1400182d2  mov     [r11-1D0h], rax
0x1400182d9  lea     rax, FIPostPnpCallback
0x1400182e0  mov     [r11-1C8h], rax
0x1400182e7  xor     eax, eax
0x1400182e9  mov     [r11-1C0h], rax
0x1400182f0  mov     [rsp+408h+var_1B8], 0F1h
0x1400182f8  mov     [rsp+408h+var_1B4], esi
0x1400182ff  mov     [r11-1B0h], rcx
0x140018306  mov     [r11-1A8h], rdi
0x14001830d  mov     [r11-1A0h], rax
0x140018314  mov     [rsp+408h+var_198], 0EEh
0x14001831c  mov     [rsp+408h+var_194], esi
0x140018323  mov     [r11-190h], rcx
0x14001832a  mov     [r11-188h], rdi
0x140018331  mov     [r11-180h], rax
0x140018338  lea     rax, FIPreSetSecurityCallback
0x14001833f  mov     [rsp+408h+var_178], 15h
0x140018347  mov     [rsp+408h+var_174], esi
0x14001834e  mov     [r11-170h], rax
0x140018355  xor     eax, eax
0x140018357  mov     [r11-168h], rdi
0x14001835e  mov     [r11-160h], rax
0x140018365  lea     rax, FIPreQuerySecurityCallback
0x14001836c  mov     [rsp+408h+var_158], 14h
0x140018374  mov     [rsp+408h+var_154], esi
0x14001837b  mov     [r11-150h], rax
0x140018382  xor     eax, eax
0x140018384  mov     [r11-148h], rdi
0x14001838b  mov     [r11-140h], rax
0x140018392  lea     rax, FIPreSetEACallback
0x140018399  mov     [r11-138h], r14b
0x1400183a0  mov     [rsp+408h+var_134], esi
0x1400183a7  mov     [r11-130h], rax
0x1400183ae  xor     eax, eax
0x1400183b0  mov     [r11-128h], rdi
0x1400183b7  mov     [r11-120h], rax
0x1400183be  lea     rax, FIPreQueryEACallback
0x1400183c5  mov     [rsp+408h+var_118], 7
0x1400183cd  mov     [rsp+408h+var_114], esi
0x1400183d4  mov     [r11-110h], rax
0x1400183db  xor     eax, eax
0x1400183dd  mov     [r11-108h], rdi
0x1400183e4  mov     [r11-100h], rax
0x1400183eb  lea     rax, FIStreamCleanup
0x1400183f2  mov     [r11-0D0h], rax
0x1400183f9  xor     eax, eax
0x1400183fb  mov     [r11-0D8h], r14d
0x140018402  mov     [rsp+408h+var_C0], 73634946h
0x14001840d  movups  [rsp+408h+var_B8], xmm0
0x140018415  mov     [r11-0A8h], rax
0x14001841c  lea     rax, FIVolumeCleanup
0x140018423  mov     [r11-98h], rax
0x14001842a  xor     eax, eax
0x14001842c  mov     [r11-0A0h], r15d
0x140018433  mov     qword ptr [r11-90h], 200h
0x14001843e  mov     [rsp+408h+var_88], 76634946h
0x140018449  mov     [r11-70h], rax
0x14001844d  mov     eax, 0FFFFh
0x140018452  mov     [r11-68h], ax
0x140018457  xor     eax, eax
0x140018459  movups  xmmword ptr [r11-46h], xmm0
0x14001845e  mov     [r11-38h], rax
0x140018462  lea     rax, [r11-0D8h]
0x140018469  mov     dword ptr [rsp+408h+Registration.Size], 2030070h
0x140018474  mov     [rsp+408h+Registration.Flags], 0Ch
0x14001847f  mov     [r11-380h], rax
0x140018486  lea     rax, [r11-318h]
0x14001848d  movups  xmmword ptr [rsp+408h+var_F4], xmm0
0x140018495  mov     [rsp+408h+var_F8], 80h
0x14001849d  movups  xmmword ptr [rsp+408h+var_F4+0Ch], xmm0
0x1400184a5  movups  xmmword ptr [r11-80h], xmm0
0x1400184aa  movups  xmmword ptr [r11-66h], xmm0
0x1400184af  movups  xmmword ptr [r11-56h], xmm0
0x1400184b4  mov     [r11-378h], rax
0x1400184bb  lea     rax, FIUnload
0x1400184c2  mov     [r11-370h], rax
0x1400184c9  xor     eax, eax
0x1400184cb  mov     [r11-368h], rsi
0x1400184d2  mov     [r11-360h], rsi
0x1400184d9  mov     [r11-358h], rsi
0x1400184e0  mov     [r11-350h], rsi
0x1400184e7  mov     [r11-348h], rsi
0x1400184ee  mov     [r11-340h], rsi
0x1400184f5  mov     [r11-338h], rsi
0x1400184fc  movups  xmmword ptr [rsp+408h+Registration.TransactionNotificationCallback], xmm0
0x140018504  mov     [r11-320h], rax
0x14001850b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140018510  xor     edx, edx; Val
0x140018512  lea     rcx, FIGlobals; void *
0x140018519  mov     r8d, 740h; Size
0x14001851f  call    memset
0x140018524  lea     rax, qword_140009390
0x14001852b  mov     cs:qword_140009510, rsi
0x140018532  lea     rcx, qword_140009518
0x140018539  mov     cs:qword_140009398, rax
0x140018540  mov     cs:qword_140009390, rax
0x140018547  call    FIPfOpenAttemptsInitialize
0x14001854c  lea     rcx, qword_140009548
0x140018553  call    FIPfOpenAttemptsInitialize
0x140018558  mov     cs:qword_140009578, rsi
0x14001855f  lea     rax, qword_140009580
0x140018566  mov     cs:qword_140009588, rax
0x14001856d  lea     rdi, qword_140009660
0x140018574  mov     cs:qword_140009580, rax
0x14001857b  lea     ecx, [rsi+20h]
0x14001857e  mov     cs:qword_140009760, rsi
0x140018585  lea     rax, qword_140009768
0x14001858c  mov     cs:qword_140009770, rax
0x140018593  mov     cs:qword_140009768, rax
0x14001859a  lea     rax, dword_140009650
0x1400185a1  mov     cs:qword_140009648, rsi
0x1400185a8  or      rax, 1
0x1400185ac  mov     cs:dword_140009650, esi
0x1400185b2  mov     cs:qword_140009654+4, rdi
0x1400185b9  mov     dword ptr cs:qword_140009654, 400h
0x1400185c3  rep stosq
0x1400185c6  mov     cs:qword_140009A78, rsi
0x1400185cd  lea     rax, qword_140009A08
0x1400185d4  mov     cs:qword_140009A00, rax
0x1400185db  lea     rcx, dword_1400093D0
0x1400185e2  lea     rax, FIControlDispatch
0x1400185e9  mov     cs:qword_140009940, rsi
0x1400185f0  mov     qword ptr cs:xmmword_140009948, rsi
0x1400185f7  mov     qword ptr cs:xmmword_140009948+8, rsi
0x1400185fe  mov     cs:qword_1400099D0, rsi
0x140018605  mov     [rbx+70h], rax
0x140018609  mov     [rbx+100h], rax
0x140018610  mov     [rbx+80h], rax
0x140018617  mov     [rbx+0E0h], rax
0x14001861e  mov     [rbx+128h], rax
0x140018625  call    FIGetRegistryParameters
0x14001862a  mov     edi, eax
0x14001862c  test    eax, eax
0x14001862e  js      loc_140018870
0x140018634  lea     rcx, [rsp+408h+var_3A0]
0x140018639  call    FIQueryPhysicalMemorySize
0x14001863e  mov     edi, eax
0x140018640  test    eax, eax
0x140018642  js      loc_140018870
0x140018648  cmp     [rsp+408h+var_3A0], 3E800000h
0x140018651  jb      short loc_14001865E
0x140018653  lea     edx, [rsi+3]
0x140018656  lea     ecx, [rsi+1]
0x140018659  call    FIFileInfoStateChange
0x14001865e  mov     edx, cs:Count; Count
0x140018664  lea     rcx, Semaphore; Semaphore
0x14001866b  mov     r8d, edx; Limit
0x14001866e  call    cs:__imp_KeInitializeSemaphore
0x140018675  nop     dword ptr [rax+rax+00h]
0x14001867a  lea     rdx, aDeviceFileinfo; "\\Device\\FileInfo"
0x140018681  lea     rcx, [rsp+408h+DestinationString]; DestinationString
0x140018686  call    cs:__imp_RtlInitUnicodeString
0x14001868d  nop     dword ptr [rax+rax+00h]
0x140018692  lea     rax, DeviceObject
0x140018699  mov     rcx, rbx; DriverObject
0x14001869c  lea     r8, [rsp+408h+DestinationString]; DeviceName
0x1400186a1  mov     [rsp+408h+DeviceObject], rax; DeviceObject
0x1400186a6  call    WdmlibIoCreateDeviceSecure
0x1400186ab  mov     edi, eax
0x1400186ad  test    eax, eax
0x1400186af  js      loc_140018870
0x1400186b5  mov     rcx, cs:DeviceObject; DeviceObject
0x1400186bc  mov     edx, 410001h; Action
0x1400186c1  call    cs:__imp_IoWMIRegistrationControl
0x1400186c8  nop     dword ptr [rax+rax+00h]
0x1400186cd  mov     edi, eax
0x1400186cf  test    eax, eax
0x1400186d1  js      loc_140018870
0x1400186d7  or      cs:dword_1400093C0, 4
0x1400186de  lea     r9, qword_140009A28; RegHandle
0x1400186e5  xor     r8d, r8d; CallbackContext
0x1400186e8  lea     rdx, FIEtwEnableCallback; EnableCallback
0x1400186ef  lea     rcx, FileInfoEventProvider; ProviderId
0x1400186f6  call    cs:__imp_EtwRegister
0x1400186fd  nop     dword ptr [rax+rax+00h]
0x140018702  test    eax, eax
0x140018704  jns     short loc_14001870D
0x140018706  mov     cs:qword_140009A28, rsi
0x14001870d  lea     r8, FIGlobals; RetFilter
0x140018714  mov     rcx, rbx; Driver
0x140018717  lea     rdx, [rsp+408h+Registration]; Registration
0x14001871f  call    cs:__imp_FltRegisterFilter
0x140018726  nop     dword ptr [rax+rax+00h]
0x14001872b  mov     edi, eax
0x14001872d  test    eax, eax
0x14001872f  js      loc_140018870
0x140018735  mov     rcx, cs:FIGlobals; Filter
0x14001873c  lea     rdx, qword_1400095C0; Lookaside
0x140018743  mov     r9d, 10h; Size
0x140018749  mov     [rsp+408h+Tag], 70634946h; Tag
0x140018751  xor     r8d, r8d; Flags
0x140018754  call    cs:__imp_FltInitExtraCreateParameterLookasideList
0x14001875b  nop     dword ptr [rax+rax+00h]
0x140018760  or      cs:dword_1400093C0, 1
0x140018767  lea     rcx, [rsp+408h+var_3B8]
0x14001876c  mov     edi, 0Fh
0x140018771  mov     qword ptr [rsp+408h+var_3B8+0Ch], rsi
0x140018776  mov     dword ptr [rsp+408h+var_3B8], edi
0x14001877a  mov     dword ptr [rsp+408h+var_3A8+4], esi
0x14001877e  mov     dword ptr [rsp+408h+var_3B8+8], r14d
0x140018783  mov     dword ptr [rsp+408h+var_3B8+4], 0Ch
  ... truncated ...
```
