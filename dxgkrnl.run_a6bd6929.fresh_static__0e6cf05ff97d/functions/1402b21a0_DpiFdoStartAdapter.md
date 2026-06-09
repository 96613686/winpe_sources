# DpiFdoStartAdapter

- ea: `0x1402b21a0`
- end: `0x1402b4289`
- name: `DpiFdoStartAdapter`
- size: `8425`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, char, void *, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *, unsigned int, unsigned __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `78`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1402b4b80`
- `0x1402c2e28`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x14001b9c0`
- `0x14001d214`
- `0x14001d884`
- `0x140047a70`
- `0x140047b0c`
- `0x14004b3c0`
- `0x14004bf5c`
- `0x140053cc8`
- `0x140055744`
- `0x14005af08`
- `0x140062140`
- `0x1400621b0`
- `0x140062200`
- `0x14007fd3c`
- `0x1400801b0`
- `0x140080410`
- `0x140080788`
- `0x140080998`
- `0x140080b94`
- `0x140080cd0`
- `0x140080dac`
- `0x140080e3c`
- `0x140081688`
- `0x1400816e0`
- `0x1400817a8`
- `0x140081e40`
- `0x140089fd4`
- `0x14008a388`
- `0x1400a0970`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401cda84`
- `0x1401e4628`
- `0x1401f0c10`
- `0x1401ff7e0`
- `0x1401ffaf8`
- `0x14020bbb4`
- `0x14020bcb0`
- `0x14020bef0`
- `0x140242e7c`
- `0x14026a69c`
- `0x14026a840`
- `0x14026aeec`
- `0x1402a3460`
- `0x1402a3b10`
- `0x1402a931c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402b2dd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b2ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b3137`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b3fe0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b4182`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b424f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b2dd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b2ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b3137`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b3fe0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b4182`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b424f`
- `ntoskrnl!ExAllocatePool2` at `0x1402b275b`
- `ntoskrnl!ExAllocatePool2` at `0x1402b30ab`
- `ntoskrnl!ExAllocatePool2` at `0x1402b40e9`
- `ntoskrnl!ExAllocatePool2` at `0x1402b41d7`
- `ntoskrnl!ExAllocatePool2` at `0x1402b275b`
- `ntoskrnl!ExAllocatePool2` at `0x1402b30ab`
- `ntoskrnl!ExAllocatePool2` at `0x1402b40e9`
- `ntoskrnl!ExAllocatePool2` at `0x1402b41d7`
- `ntoskrnl!PoFxUnregisterDevice` at `0x1402b3dd1`
- `ntoskrnl!PoFxUnregisterDevice` at `0x1402b3dd1`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1402b2600`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1402b2600`
- `ntoskrnl!KeDelayExecutionThread` at `0x1402b25ce`
- `ntoskrnl!KeDelayExecutionThread` at `0x1402b25ce`
- `ntoskrnl!ZwClose` at `0x1402b364e`
- `ntoskrnl!ZwClose` at `0x1402b364e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402b3604`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402b3604`
- `ntoskrnl!ExUuidCreate` at `0x1402b25e6`
- `ntoskrnl!ExUuidCreate` at `0x1402b25e6`
- `ntoskrnl!IoAllocateWorkItem` at `0x1402b3811`
- `ntoskrnl!IoAllocateWorkItem` at `0x1402b3811`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3876`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b39f4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3a99`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3ceb`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3d07`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3876`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b39f4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3a99`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3ceb`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402b3d07`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1402b3c8c`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1402b3c8c`
- `HAL!x86BiosCall` at `0x1402b253d`
- `HAL!x86BiosCall` at `0x1402b253d`
- `watchdog!WdDiagNotifyUser` at `0x1402b2eb8`
- `watchdog!WdDiagNotifyUser` at `0x1402b2eb8`
- `watchdog!WdLogSingleEntry2` at `0x1402b23e1`
- `watchdog!WdLogSingleEntry2` at `0x1402b2e16`
- `watchdog!WdLogSingleEntry2` at `0x1402b347d`
- `watchdog!WdLogSingleEntry2` at `0x1402b405b`
- `watchdog!WdLogSingleEntry2` at `0x1402b40c3`
- `watchdog!WdLogSingleEntry2` at `0x1402b23e1`
- `watchdog!WdLogSingleEntry2` at `0x1402b2e16`
- `watchdog!WdLogSingleEntry2` at `0x1402b347d`
- `watchdog!WdLogSingleEntry2` at `0x1402b405b`
- `watchdog!WdLogSingleEntry2` at `0x1402b40c3`
- `watchdog!WdLogSingleEntry5` at `0x1402b2f1f`
- `watchdog!WdLogSingleEntry5` at `0x1402b2f1f`
- `watchdog!WdLogSingleEntry1` at `0x1402b243a`
- `watchdog!WdLogSingleEntry1` at `0x1402b245e`
- `watchdog!WdLogSingleEntry1` at `0x1402b261b`
- `watchdog!WdLogSingleEntry1` at `0x1402b2643`
- `watchdog!WdLogSingleEntry1` at `0x1402b2689`
- `watchdog!WdLogSingleEntry1` at `0x1402b26d0`
- `watchdog!WdLogSingleEntry1` at `0x1402b26fa`
- `watchdog!WdLogSingleEntry1` at `0x1402b2727`
- `watchdog!WdLogSingleEntry1` at `0x1402b277c`
- `watchdog!WdLogSingleEntry1` at `0x1402b2e8a`
- `watchdog!WdLogSingleEntry1` at `0x1402b2fa4`
- `watchdog!WdLogSingleEntry1` at `0x1402b2fed`
- `watchdog!WdLogSingleEntry1` at `0x1402b3041`
- `watchdog!WdLogSingleEntry1` at `0x1402b30ce`
- `watchdog!WdLogSingleEntry1` at `0x1402b3115`
- `watchdog!WdLogSingleEntry1` at `0x1402b3190`
- `watchdog!WdLogSingleEntry1` at `0x1402b320b`
- `watchdog!WdLogSingleEntry1` at `0x1402b324a`
- `watchdog!WdLogSingleEntry1` at `0x1402b3297`
- `watchdog!WdLogSingleEntry1` at `0x1402b33eb`
- `watchdog!WdLogSingleEntry1` at `0x1402b34bd`
- `watchdog!WdLogSingleEntry1` at `0x1402b350f`
- `watchdog!WdLogSingleEntry1` at `0x1402b358f`
- `watchdog!WdLogSingleEntry1` at `0x1402b35e1`
- `watchdog!WdLogSingleEntry1` at `0x1402b3634`
- `watchdog!WdLogSingleEntry1` at `0x1402b3743`
- `watchdog!WdLogSingleEntry1` at `0x1402b3833`
- `watchdog!WdLogSingleEntry1` at `0x1402b3891`
- `watchdog!WdLogSingleEntry1` at `0x1402b38ef`
- `watchdog!WdLogSingleEntry1` at `0x1402b39a5`
- `watchdog!WdLogSingleEntry1` at `0x1402b3a3f`
- `watchdog!WdLogSingleEntry1` at `0x1402b3ae2`
- `watchdog!WdLogSingleEntry1` at `0x1402b243a`
- `watchdog!WdLogSingleEntry1` at `0x1402b245e`
- `watchdog!WdLogSingleEntry1` at `0x1402b261b`
- `watchdog!WdLogSingleEntry1` at `0x1402b2643`
- `watchdog!WdLogSingleEntry1` at `0x1402b2689`
- `watchdog!WdLogSingleEntry1` at `0x1402b26d0`
- `watchdog!WdLogSingleEntry1` at `0x1402b26fa`
- `watchdog!WdLogSingleEntry1` at `0x1402b2727`
- `watchdog!WdLogSingleEntry1` at `0x1402b277c`
- `watchdog!WdLogSingleEntry1` at `0x1402b2e8a`
- `watchdog!WdLogSingleEntry1` at `0x1402b2fa4`
- `watchdog!WdLogSingleEntry1` at `0x1402b2fed`
- `watchdog!WdLogSingleEntry1` at `0x1402b3041`
- `watchdog!WdLogSingleEntry1` at `0x1402b30ce`
- `watchdog!WdLogSingleEntry1` at `0x1402b3115`
- `watchdog!WdLogSingleEntry1` at `0x1402b3190`
- `watchdog!WdLogSingleEntry1` at `0x1402b320b`
- `watchdog!WdLogSingleEntry1` at `0x1402b324a`
- `watchdog!WdLogSingleEntry1` at `0x1402b3297`
- `watchdog!WdLogSingleEntry1` at `0x1402b33eb`
- `watchdog!WdLogSingleEntry1` at `0x1402b34bd`
- `watchdog!WdLogSingleEntry1` at `0x1402b350f`
- `watchdog!WdLogSingleEntry1` at `0x1402b358f`
- `watchdog!WdLogSingleEntry1` at `0x1402b35e1`
- `watchdog!WdLogSingleEntry1` at `0x1402b3634`
- `watchdog!WdLogSingleEntry1` at `0x1402b3743`
- `watchdog!WdLogSingleEntry1` at `0x1402b3833`
- `watchdog!WdLogSingleEntry1` at `0x1402b3891`
- `watchdog!WdLogSingleEntry1` at `0x1402b38ef`
- `watchdog!WdLogSingleEntry1` at `0x1402b39a5`
- `watchdog!WdLogSingleEntry1` at `0x1402b3a3f`
- `watchdog!WdLogSingleEntry1` at `0x1402b3ae2`

## string_xrefs

- `0x1402b3b2c`: `Adapter StartDevice has completed with status %1`

## pseudocode

```c
__int64 __fastcall DpiFdoStartAdapter(
        struct _DEVICE_OBJECT *a1,
        char a2,
        void *a3,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a4,
        unsigned int a5,
        unsigned __int64 a6,
        _QWORD *a7)
{
  __int64 v7; // r13
  char v8; // bl
  char *v9; // rsi
  char *DeviceExtension; // r15
  __int64 v11; // r12
  int MiniportInterface; // r14d
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(_QWORD, _QWORD); // rax
  int v19; // eax
  __int64 v20; // r14
  unsigned int v21; // edi
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r8
  unsigned int v27; // eax
  bool v28; // cf
  bool v29; // zf
  NTSTATUS v30; // eax
  NTSTATUS LocallyUniqueId; // eax
  int v32; // eax
  int SavedAdapterState; // eax
  int v34; // eax
  int started; // eax
  _DWORD *Pool2; // rax
  _DWORD *v37; // rbx
  unsigned int v38; // ecx
  int v39; // eax
  int v40; // edx
  __int64 (__fastcall *v41)(); // rcx
  __int64 (__fastcall *v42)(); // rdx
  __int64 (__fastcall *v43)(); // r8
  __int64 (__fastcall *v44)(); // r9
  __int64 (__fastcall *v45)(); // r10
  __int64 (__fastcall *v46)(); // r11
  __int64 (__fastcall *v47)(); // r14
  __int64 (__fastcall *v48)(); // rdi
  __int64 (__fastcall *v49)(); // r13
  __int64 (__fastcall *v50)(); // rax
  __int128 v51; // xmm0
  int DevicePropertyString; // eax
  unsigned int v53; // eax
  int v54; // eax
  int v55; // eax
  struct _LUID *v56; // rdx
  unsigned int v57; // eax
  void *v58; // rax
  __int64 v59; // rcx
  int v60; // eax
  char v61; // cl
  int *v62; // rbx
  bool v63; // cc
  _BYTE *v64; // rbx
  char v65; // dl
  _BYTE *v66; // rax
  char v67; // cl
  _QWORD *v68; // rcx
  __int64 v69; // r8
  __int64 v70; // rdx
  int v71; // eax
  int v72; // eax
  PVOID v73; // rdi
  int RelatedObjects; // eax
  __int64 v75; // rdx
  __int64 v76; // rdx
  int Caps; // eax
  int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // rax
  __int64 v82; // rcx
  __int64 v83; // rax
  int v84; // eax
  __int64 v85; // rcx
  PIO_WORKITEM WorkItem; // rax
  NTSTATUS v87; // eax
  int v88; // eax
  __int64 v89; // rdx
  __int64 v90; // rcx
  int v91; // eax
  int v92; // eax
  BOOLEAN v93; // dl
  NTSTATUS v94; // eax
  int v95; // eax
  BOOLEAN v96; // dl
  NTSTATUS v97; // eax
  int v98; // eax
  __int64 v99; // rcx
  __int64 v100; // rcx
  char IsPostDevice; // al
  int v102; // ecx
  unsigned int v103; // r8d
  unsigned int v104; // ebx
  int v105; // eax
  int v106; // r8d
  unsigned int v107; // ebx
  int v108; // r9d
  struct _DEVICE_OBJECT *v109; // rcx
  int v110; // eax
  __int64 v111; // rcx
  __int64 v112; // r9
  int v113; // edi
  unsigned int *v114; // r12
  void (__fastcall *v115)(_QWORD); // rax
  __int64 v116; // rcx
  char v117; // cl
  __int64 DiagnosticInfoArgs; // rax
  __int64 v119; // rdi
  __int64 v120; // rcx
  unsigned __int64 v121; // rcx
  __int64 v122; // rax
  __int64 v123; // rdi
  __int64 v124; // rcx
  __int64 (__fastcall *v125)(__int64, _QWORD); // rax
  int v126; // eax
  __int64 (__fastcall *v127)(__int64, __int128 *); // rax
  __int64 v128; // rcx
  int v129; // eax
  _DWORD *v130; // rax
  _DWORD *v131; // r12
  __int64 v132; // rax
  int v133; // eax
  unsigned __int64 v134; // rdx
  __int64 v135; // rax
  _DWORD *v136; // rax
  _DWORD *v137; // rbx
  int v138; // eax
  int v140; // [rsp+28h] [rbp-D8h]
  char v141; // [rsp+50h] [rbp-B0h]
  char v142; // [rsp+51h] [rbp-AFh]
  char v143; // [rsp+52h] [rbp-AEh]
  bool v144; // [rsp+52h] [rbp-AEh]
  char v145; // [rsp+53h] [rbp-ADh]
  char v146; // [rsp+54h] [rbp-ACh]
  char v147; // [rsp+55h] [rbp-ABh]
  union _LARGE_INTEGER Interval; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v150; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v151; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v153; // [rsp+78h] [rbp-88h]
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall *v155)(); // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v156)(); // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v157)(); // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v158)(); // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v159)(); // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v160)(); // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v161)(); // [rsp+B8h] [rbp-48h]
  PDEVICE_OBJECT DeviceObject; // [rsp+C0h] [rbp-40h]
  __int64 v163; // [rsp+C8h] [rbp-38h]
  __int64 v164; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v165; // [rsp+D8h] [rbp-28h]
  void *v166; // [rsp+E0h] [rbp-20h]
  _QWORD *v167; // [rsp+E8h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v169[10]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v170; // [rsp+150h] [rbp+50h] BYREF
  __int64 v171; // [rsp+160h] [rbp+60h]
  _OWORD v172[2]; // [rsp+168h] [rbp+68h] BYREF
  _OWORD v173[2]; // [rsp+188h] [rbp+88h] BYREF

  v7 = (__int64)a1;
  DeviceObject = a1;
  v8 = a2;
  memset(v172, 0, 28);
  v151 = a6;
  v167 = a7;
  Handle = 0;
  v9 = 0;
  DestinationString = 0;
  DeviceExtension = (char *)a1->DeviceExtension;
  v153 = a4;
  v166 = a3;
  v29 = *((_DWORD *)DeviceExtension + 4) == 1953656900;
  v11 = *((_QWORD *)DeviceExtension + 5);
  v163 = v11;
  v143 = 0;
  v147 = 0;
  v142 = 0;
  v141 = 0;
  v145 = 0;
  v146 = 0;
  P = 0;
  v164 = MEMORY[0xFFFFF78000000320];
  v165 = 3;
  if ( v29 && *((_DWORD *)DeviceExtension + 5) == 2 )
  {
    v9 = DeviceExtension;
    if ( *(_BYTE *)(v11 + 134) )
    {
      MiniportInterface = DpiQueryMiniportInterface(
                            *((_QWORD *)DeviceExtension + 3),
                            (unsigned int)&GUID_DEVINTERFACE_INDIRECT_DISP_KMD,
                            112,
                            3);
      if ( MiniportInterface >= 0 )
      {
        if ( v151 )
        {
          v18 = (__int64 (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)DeviceExtension + 131);
          if ( v18 )
          {
            v19 = v18(*((_QWORD *)DeviceExtension + 126), a5);
            LODWORD(v20) = v19;
            if ( v19 < 0 )
            {
              WdLogSingleEntry2(2, *((_QWORD *)DeviceExtension + 131), v19);
              WdLogGlobalForLineNumber = 15206;
              v21 = 25;
              goto LABEL_249;
            }
            goto LABEL_7;
          }
        }
      }
      else
      {
        memset(DeviceExtension + 1000, 0, 0x70u);
      }
      if ( MiniportInterface >= 0 )
      {
LABEL_7:
        memset(v169, 0, sizeof(v169));
        if ( (int)DpiQueryMiniportInterface(
                    *((_QWORD *)DeviceExtension + 3),
                    (unsigned int)&GUID_DEVINTERFACE_DOD_EXTENDED,
                    80,
                    1) >= 0
          && LODWORD(v169[0]) == 65616 )
        {
          if ( v169[4] )
          {
            v13 = v169[5];
            if ( v169[5] )
            {
              v14 = v169[6];
              if ( v169[6] )
              {
                v15 = v169[7];
                if ( v169[7] )
                {
                  v16 = v169[8];
                  if ( v169[8] )
                  {
                    v17 = v169[9];
                    if ( v169[9] )
                    {
                      *(_QWORD *)(v11 + 1008) = v169[4];
                      *(_QWORD *)(v11 + 1088) = v13;
                      *(_QWORD *)(v11 + 1128) = v14;
                      *(_QWORD *)(v11 + 1136) = v15;
                      *(_QWORD *)(v11 + 1312) = v16;
                      *(_QWORD *)(v11 + 1096) = v17;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      memset(DeviceExtension + 1000, 0, 0x70u);
    }
    v8 = a2;
    *((_DWORD *)DeviceExtension + 1030) = 0;
  }
  v22 = DpiFdoConnectInterrupt(v7);
  LODWORD(v20) = v22;
  if ( v22 == -1073741275 )
  {
    WdLogSingleEntry1(4, v7);
    WdLogGlobalForLineNumber = 15280;
  }
  else
  {
    if ( v22 < 0 )
    {
      WdLogSingleEntry1(2, v22);
      WdLogGlobalForLineNumber = 15293;
      v21 = 10;
      goto LABEL_249;
    }
    v143 = 1;
  }
  if ( (unsigned __int8)DpiFdoIsPostDevice(v7) )
  {
    if ( DeviceExtension[1155] == 1
      && v8
      && byte_140162E56
      && !(unsigned __int8)DpiFdoIsCompatibleWithHighResolutionBoot() )
    {
      LODWORD(v170) = -1;
      *((_QWORD *)&v170 + 1) = 0;
      if ( (qword_1401604F0 & 2) != 0 )
      {
        LOBYTE(v171) = 1;
        LODWORD(v170) = 8006;
        if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v23, EventProfilerEnter, v24, 8006);
      }
      else
      {
        LOBYTE(v171) = 0;
      }
      DXGETWPROFILER_BASE::PushProfilerEntry(&v170, 8006);
      memset(v173, 0, sizeof(v173));
      LODWORD(v173[0]) = 18;
      x86BiosCall(16, v173);
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v170);
      if ( (_BYTE)v171 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v25, EventProfilerExit, v26, (unsigned int)v170);
    }
    if ( v9 )
    {
      v27 = *(_DWORD *)(v11 + 28);
      if ( byte_140162E56 )
      {
        v28 = v27 < 0x300E;
        v29 = v27 == 12302;
      }
      else
      {
        v28 = v27 < 0x2005;
        v29 = v27 == 8197;
      }
      v9[4040] = v9[4040] & 0xFB | (4 * (!v28 && !v29));
    }
  }
  for ( Interval.QuadPart = 0; ; Interval.QuadPart = 0 )
  {
    v30 = ExUuidCreate((UUID *)(DeviceExtension + 2680));
    LODWORD(v20) = v30;
    if ( v30 >= 0 )
      break;
    if ( v30 != -1073741267 )
    {
      WdLogSingleEntry1(2, v30);
      WdLogGlobalForLineNumber = 15367;
      v21 = 8;
      goto LABEL_249;
    }
    Interval.QuadPart = -10000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  LocallyUniqueId = ZwAllocateLocallyUniqueId((PLUID)DeviceExtension + 337);
  LODWORD(v20) = LocallyUniqueId;
  if ( LocallyUniqueId < 0 )
  {
    WdLogSingleEntry1(2, LocallyUniqueId);
    WdLogGlobalForLineNumber = 15393;
    v21 = 7;
    goto LABEL_249;
  }
  if ( v9 )
  {
    if ( (unsigned __int8)DpiKsrIsSoftBoot() )
    {
      v32 = DpiKsrRestoreAdapterDriverState((struct _FDO_CONTEXT *)v9);
      if ( v32 >= 0 )
      {
        LODWORD(v150) = 0;
        v151 = 0;
        SavedAdapterState = DpiKsrGetSavedAdapterState(v7, &v150, &v151);
        if ( SavedAdapterState < 0 )
        {
          WdLogSingleEntry1(2, SavedAdapterState);
          WdLogGlobalForLineNumber = 15428;
        }
      }
      else
      {
        WdLogSingleEntry1(2, v32);
        WdLogGlobalForLineNumber = 15414;
      }
    }
    v34 = DpiFdoSetAdapterLuid((struct _FDO_CONTEXT *)v9);
    if ( v34 < 0 )
    {
      WdLogSingleEntry1(2, v34);
      WdLogGlobalForLineNumber = 15442;
    }
    started = DpiFeatureStartDevice(v7);
    LODWORD(v20) = started;
    if ( started < 0 )
    {
      WdLogSingleEntry1(2, started);
      WdLogGlobalForLineNumber = 15454;
      v21 = 12;
      goto LABEL_249;
    }
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, 576, 1953656900);
  v37 = Pool2;
  if ( !Pool2 )
  {
    LODWORD(v20) = -1073741670;
    WdLogSingleEntry1(6, -1073741670);
    WdLogGlobalForLineNumber = 15471;
    v21 = 9;
    goto LABEL_249;
  }
  memset(Pool2, 0, 0x240u);
  v38 = *(_DWORD *)(v11 + 28);
  if ( v38 >= 0xD001 )
  {
    *v37 = 576;
LABEL_67:
    v39 = *((_DWORD *)DeviceExtension + 687);
    goto LABEL_86;
  }
  v39 = 40971;
  if ( v38 > 0xA00B )
  {
    *v37 = 480;
    goto LABEL_67;
  }
  v40 = 36870;
  if ( v38 <= 0x9006 )
  {
    v39 = 32769;
    if ( v38 <= 0x8001 )
    {
      v40 = 28682;
      if ( v38 > 0x700A )
      {
        *v37 = 368;
        goto LABEL_86;
      }
      v39 = 24579;
      if ( v38 <= 0x6003 )
      {
        v40 = 20515;
        if ( v38 > 0x5023 )
        {
          *v37 = 328;
          goto LABEL_86;
        }
        v39 = 16387;
        if ( v38 <= 0x4003 )
        {
          v40 = 12302;
          if ( v38 > 0x300E )
          {
            *v37 = 264;
            goto LABEL_86;
          }
          v39 = 8197;
          if ( v38 <= 0x2005 )
          {
            *v37 = 184;
            goto LABEL_86;
          }
          *v37 = 256;
        }
        else
        {
          *v37 = 312;
        }
      }
      else
      {
        *v37 = 360;
      }
    }
    else
    {
      *v37 = 456;
    }
    v39 = v40;
    goto LABEL_86;
  }
  *v37 = 464;
LABEL_86:
  v37[1] = v39;
  *((_QWORD *)v37 + 2) = DpEvalAcpiMethod;
  *((_QWORD *)v37 + 3) = &DpGetDeviceInformation;
  *((_QWORD *)v37 + 4) = DpIndicateChildStatus;
  *((_QWORD *)v37 + 5) = &DpMapMemory;
  *((_QWORD *)v37 + 6) = DpQueueDpc;
  *((_QWORD *)v37 + 7) = DpQueryServices;
  *((_QWORD *)v37 + 8) = &DpReadDeviceSpace;
  *((_QWORD *)v37 + 9) = &DpSynchronizeExecution;
  *((_QWORD *)v37 + 10) = DpUnmapMemory;
  *((_QWORD *)v37 + 11) = &DpWriteDeviceSpace;
  *((_QWORD *)v37 + 12) = DpIsDevicePresent;
  *((_QWORD *)v37 + 13) = DxgGetHandleDataCB;
  *((_QWORD *)v37 + 14) = DxgGetHandleParentCB;
  *((_QWORD *)v37 + 15) = DxgEnumHandleChildrenCB;
  *((_QWORD *)v37 + 16) = &DxgNotifyInterruptCB;
  *((_QWORD *)v37 + 17) = DxgNotifyDpcCB;
  *((_QWORD *)v37 + 18) = DxgMiniportQueryVidPnInterfaceCB;
  *((_QWORD *)v37 + 19) = DxgMiniportQueryMonitorInterfaceCB;
  *((_QWORD *)v37 + 20) = DxgGetCaptureAddressCB;
  *((_QWORD *)v37 + 21) = DxgLogEtwEventCb;
  *((_QWORD *)v37 + 22) = DpExcludeAdapterAccess;
  *((_QWORD *)v37 + 23) = DxgCreateContextAllocationCB;
  *((_QWORD *)v37 + 24) = DxgDestroyContextAllocationCB;
  *((_QWORD *)v37 + 25) = &DxgSetPowerComponentActiveCB;
  *((_QWORD *)v37 + 26) = &DxgSetPowerComponentIdleCB;
  *((_QWORD *)v37 + 28) = DxgkPowerRuntimeControlRequestCB;
  *((_QWORD *)v37 + 29) = &DxgkSetPowerComponentLatencyCB;
  *((_QWORD *)v37 + 30) = &DxgkSetPowerComponentResidencyCB;
  *((_QWORD *)v37 + 31) = &DxgkCompleteFStateTransitionCB;
  *((_QWORD *)v37 + 32) = &DxgkCompletePStateTransitionCB;
  *((_QWORD *)v37 + 27) = DpAcquirePostDisplayOwnership;
  *((_QWORD *)v37 + 33) = DxgkMapContextAllocationCB;
  *((_QWORD *)v37 + 34) = DxgkUpdateContextAllocationCB;
  *((_QWORD *)v37 + 35) = DxgkReserveGpuVirtualAddressRangeCB;
  *((_QWORD *)v37 + 36) = DxgkAcquireHandleDataCB;
  *((_QWORD *)v37 + 37) = DxgkReleaseHandleDataCB;
  *((_QWORD *)v37 + 38) = &DxgkHardwareContentProtectionTeardownCB;
  *((_QWORD *)v37 + 39) = &DxgkMultiPlaneOverlayDisabledCB;
  *((_QWORD *)v37 + 40) = DxgkMitigatedRangeUpdateCB;
  *((_QWORD *)v37 + 1) = v7;
  *((_QWORD *)v37 + 42) = DpIndicateConnectorChange;
  *((_QWORD *)v37 + 43) = &DxgkUnblockUEFIFrameBufferRangesCB;
  *((_QWORD *)v37 + 44) = DpAcquirePostDisplayOwnership2;
  *((_QWORD *)v37 + 45) = DxgkSetProtectedSessionStatusCB;
  *((_QWORD *)v37 + 56) = &DxgkCbReportDiagnostic;
  *((_QWORD *)v37 + 41) = DxgkInvalidateHwContextCB;
  *((_QWORD *)v37 + 57) = DxgkSignalEventCB;
  *((_QWORD *)v37 + 58) = DpIsFeatureEnabled;
  *((_QWORD *)v37 + 59) = DpSaveMemoryForHotUpdateCB;
  *((_QWORD *)v37 + 60) = DxgkNotifyCursorSupportChangeCB;
  *((_QWORD *)v37 + 61) = DpQueryFeatureSupport;
  if ( (unsigned int)Feature_IommuIrqlValidation__private_IsEnabledDeviceUsageNoInline()
    && *((_DWORD *)DeviceExtension + 4) == 1953656900
    && *((_DWORD *)DeviceExtension + 5) == 2
    && *(_DWORD *)(v11 + 28) >= 0x11005u
    && *((int *)v9 + 1461) >= 12800 )
  {
    v151 = (unsigned __int64)DxgkDestroyPhysicalMemoryObjectCB_32;
    v41 = DxgkPinFrameBufferForSave2CB_32;
    v161 = DxgkUnmapMdlFromIoMmuCB_32;
    v42 = DxgkClosePhysicalMemoryObjectCB_32;
    v160 = DxgkFreePagesFromMdlCB_32;
    v43 = DxgkOpenPhysicalMemoryObjectCB_32;
    v159 = DxgkAllocatePagesForMdlCB_32;
    v44 = DxgkFreeAdlCB_32;
    v158 = DxgkFreePagesFromMdlCB_32;
    v45 = DxgkAllocateAdlCB_32;
    v157 = DxgkAllocateContiguousMemoryCB_32;
    v46 = DxgkUnmapPhysicalMemoryCB_32;
    v156 = DxgkUnmapFrameBufferPointerCB_32;
    v47 = DxgkMapPhysicalMemoryCB_32;
    v155 = DxgkMapFrameBufferPointerCB_32;
    v48 = DxgkCreatePhysicalMemoryObjectCB_32;
    v150 = (__int64)DxgkUnpinFrameBufferForSaveCB_32;
    v49 = DxgkMapMdlToIoMmuCB_32;
    v50 = DxgkPinFrameBufferForSaveCB_32;
  }
  else
  {
    v151 = (unsigned __int64)DxgkDestroyPhysicalMemoryObjectCB;
    v41 = DxgkPinFrameBufferForSave2CB;
    v161 = DxgkUnmapMdlFromIoMmuCB;
    v42 = DxgkClosePhysicalMemoryObjectCB;
    v160 = DxgkFreePagesFromMdlCB;
    v43 = DxgkOpenPhysicalMemoryObjectCB;
    v159 = DxgkAllocatePagesForMdlCB;
    v44 = DxgkFreeAdlCB;
    v158 = DxgkFreePagesFromMdlCB;
    v45 = DxgkAllocateAdlCB;
    v157 = DxgkAllocateContiguousMemoryCB;
    v46 = DxgkUnmapPhysicalMemoryCB;
    v156 = DxgkUnmapFrameBufferPointerCB;
    v47 = DxgkMapPhysicalMemoryCB;
    v155 = DxgkMapFrameBufferPointerCB;
    v48 = DxgkCreatePhysicalMemoryObjectCB;
    v150 = (__int64)DxgkUnpinFrameBufferForSaveCB;
    v49 = DxgkMapMdlToIoMmuCB;
    v50 = DxgkPinFrameBufferForSaveCB;
  }
  Interval.QuadPart = (LONGLONG)v50;
  *((_QWORD *)v37 + 50) = v50;
  *((_QWORD *)v37 + 51) = v150;
  *((_QWORD *)v37 + 52) = v155;
  *((_QWORD *)v37 + 53) = v156;
  *((_QWORD *)v37 + 46) = v157;
  *((_QWORD *)v37 + 47) = v158;
  *((_QWORD *)v37 + 48) = v159;
  *((_QWORD *)v37 + 49) = v160;
  v11 = v163;
  *((_QWORD *)v37 + 54) = v49;
  *((_QWORD *)v37 + 55) = v161;
  v7 = (__int64)DeviceObject;
  *((_QWORD *)v37 + 62) = v48;
  *((_QWORD *)v37 + 63) = v151;
  *((_QWORD *)v37 + 64) = v47;
  *((_QWORD *)v37 + 65) = v46;
  *((_QWORD *)v37 + 66) = v45;
  *((_QWORD *)v37 + 67) = v44;
  *((_QWORD *)v37 + 68) = v43;
  *((_QWORD *)v37 + 69) = v42;
  *((_QWORD *)v37 + 70) = v41;
  LODWORD(v172[0]) = 32;
  v51 = *(_OWORD *)(DeviceExtension + 2680);
  *((_QWORD *)v37 + 71) = DxgkDisconnectDoorbellCB;
  *(_OWORD *)((char *)v172 + 4) = v51;
  *(_QWORD *)((char *)&v172[1] + 4) = *((_QWORD *)DeviceExtension + 337);
  qword_140163258 = (__int64)KeGetCurrentThread();
  qword_140163260 = v7;
  v20 = (int)DpiDxgkDdiStartDevice(
               v11,
               *((_QWORD *)DeviceExtension + 6),
               (unsigned int)v172,
               (_DWORD)v37,
               (__int64)(DeviceExtension + 2708),
               (__int64)(DeviceExtension + 2704));
  ExFreePoolWithTag(v37, 0x74727044u);
  v21 = v165;
  qword_140163260 = 0;
  qword_140163258 = 0;
  if ( (int)v20 >= 0 )
  {
    if ( (unsigned __int8)DpiFdoIsMsBddAnchoredDevice(v7) )
    {
      xmmword_1401631C0 = 0;
      DWORD2(xmmword_1401631C0) = -1;
      xmmword_1401631B0 = 0;
      memset(&xmmword_1401631D0, 0, 0x80u);
      dword_140163250 = v21;
    }
    if ( !*((_DWORD *)DeviceExtension + 678) )
    {
      v53 = *((_DWORD *)DeviceExtension + 677);
      if ( v53 > 1 )
      {
        WdLogSingleEntry1(v21, v53);
        WdLogGlobalForLineNumber = 15819;
        *((_DWORD *)DeviceExtension + 677) = 1;
      }
    }
    v147 = 1;
    if ( !v9 )
    {
      v73 = P;
LABEL_226:
      v88 = DpiFdoOpenDeviceFileObjectIfNeeded(DeviceExtension);
      v20 = v88;
      if ( v88 >= 0 )
      {
        DxgkMiracastQueryMiracastSupportInternal(0);
        v90 = *((_DWORD *)DeviceExtension + 69) & 7;
        *(_DWORD *)&DeviceExtension[4 * v90 + 244] = *((_DWORD *)DeviceExtension + 60);
        v91 = *((_DWORD *)DeviceExtension + 59);
        ++*((_DWORD *)DeviceExtension + 69);
        *((_DWORD *)DeviceExtension + 60) = v91;
        *((_DWORD *)DeviceExtension + 59) = 2;
        if ( v9 && v73 && (LOBYTE(v90) = v9[2847], (int)DxgkCommitGdiViewIds(v90, *((_QWORD *)v9 + 736)) < 0) )
        {
          v92 = *((_DWORD *)DeviceExtension + 60);
          --*((_DWORD *)DeviceExtension + 69);
          *((_DWORD *)DeviceExtension + 59) = v92;
          *((_DWORD *)DeviceExtension + 60) = *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7)
                                                                        + 244];
          WdLogSingleEntry1(2, v20);
          WdLogGlobalForLineNumber = 16533;
          v21 = 21;
        }
        else
        {
          v21 = 0;
          DxgkInvalidateQdcCache(v90, v89);
          if ( v9 )
          {
            v93 = !v9[1153] || !v9[480];
            v94 = IoSetDeviceInterfaceState((PUNICODE_STRING)v9 + 178, v93);
            v20 = v94;
            if ( v94 >= 0 )
            {
              v145 = 1;
              if ( (v9[4041] & 0x20) == 0 && *((_QWORD *)v9 + 359) )
              {
                v96 = !v9[1153] || !v9[480];
                v97 = IoSetDeviceInterfaceState((PUNICODE_STRING)v9 + 179, v96);
                v20 = v97;
                if ( v97 >= 0 )
                {
                  v146 = 1;
                }
                else
                {
                  v98 = *((_DWORD *)DeviceExtension + 60);
                  --*((_DWORD *)DeviceExtension + 69);
                  *((_DWORD *)DeviceExtension + 59) = v98;
                  *((_DWORD *)DeviceExtension + 60) = *(_DWORD *)&DeviceExtension[4
                                                                                * (*((_DWORD *)DeviceExtension + 69) & 7)
                                                                                + 244];
                  WdLogSingleEntry1(2, v20);
                  WdLogGlobalForLineNumber = 16580;
                  v21 = 24;
                }
              }
            }
            else
            {
              *((_DWORD *)DeviceExtension + 59) = *((_DWORD *)DeviceExtension + 60);
              v95 = *((_DWORD *)DeviceExtension + 69) - 1;
              *((_DWORD *)DeviceExtension + 69) = v95;
              *((_DWORD *)DeviceExtension + 60) = *(_DWORD *)&DeviceExtension[4 * (v95 & 7) + 244];
              WdLogSingleEntry1(2, v20);
              WdLogGlobalForLineNumber = 16563;
              v21 = 23;
            }
          }
        }
      }
      else
      {
        WdLogSingleEntry1(2, v88);
        WdLogGlobalForLineNumber = 16494;
        v21 = 6;
      }
      v141 = v142;
      goto LABEL_249;
    }
    if ( *((_DWORD *)v9 + 676) )
    {
      v54 = DpiFdoEnumChildDevices(v7);
      LODWORD(v20) = v54;
      if ( v54 < 0 )
      {
        WdLogSingleEntry1(2, v54);
        WdLogGlobalForLineNumber = 15849;
        v21 = 15;
        goto LABEL_249;
      }
    }
    v55 = DxgkAddAdapter((struct _DEVICE_OBJECT *)v7, v166, (struct _DXGK_ADAPTER_CAPS *)(v9 + 4040), v153);
    LODWORD(v20) = v55;
    if ( v55 < 0 )
    {
      WdLogSingleEntry1(2, v55);
      WdLogGlobalForLineNumber = 15871;
      goto LABEL_249;
    }
    DxgkAcquireAdapterFdoReference(*((_QWORD *)v9 + 504));
    v142 = 1;
    v9[2847] = DXGADAPTER::IsAdapterSessionized(*((DXGADAPTER **)v9 + 504), v56, 0, (unsigned __int64 *)v9 + 736);
    v57 = *((_DWORD *)v9 + 677);
    if ( v57 )
    {
      v58 = (void *)ExAllocatePool2(256, 4LL * v57, 1953656900);
      P = v58;
      if ( !v58 )
      {
        LODWORD(v20) = -1073741670;
        WdLogSingleEntry1(6, -1073741670);
        WdLogGlobalForLineNumber = 15911;
        v21 = 16;
        goto LABEL_249;
      }
      LOBYTE(v59) = v9[2847];
      v60 = DxgkAcquireGdiViewIds(v59, *((_QWORD *)v9 + 736), v9 + 2708, v58);
      LODWORD(v20) = v60;
      if ( v60 < 0 )
      {
        WdLogSingleEntry1(2, v60);
        WdLogGlobalForLineNumber = 15925;
        v21 = 17;
        ExFreePoolWithTag(P, 0);
        P = 0;
        goto LABEL_249;
      }
    }
    v61 = v9[4041] ^ (v9[4041] ^ (2 * v9[4041])) & 8;
    v9[4041] = v61;
    if ( (v61 & 4) != 0 && (!*(_QWORD *)(v11 + 1128) || !*(_QWORD *)(v11 + 1136)) )
    {
      WdLogSingleEntry1(2, (unsigned int)v20);
      WdLogGlobalForLineNumber = 15947;
      v9[4041] &= ~8u;
      v61 = v9[4041];
    }
    v62 = (int *)(v9 + 4048);
    if ( (v9[4040] & 1) != 0 && *v62 >= 0x2000 && !v9[1158] )
    {
      if ( (v61 & 8) != 0 )
        goto LABEL_133;
      Feature_LegacyHPDFiltering__private_IsEnabledPreCheck();
      v9[4041] |= 0x10u;
      v61 = v9[4041];
    }
    if ( (v61 & 8) == 0 && !*(_QWORD *)(v11 + 208) )
    {
      LODWORD(v20) = -1073741735;
      WdLogSingleEntry1(2, -1073741735);
      WdLogGlobalForLineNumber = 15980;
      v21 = 18;
      goto LABEL_249;
    }
LABEL_133:
    if ( v9[2721] && (v61 & 0x20) == 0 )
    {
      LODWORD(v20) = -1073741735;
      WdLogSingleEntry1(2, -1073741735);
      WdLogGlobalForLineNumber = 15997;
      v21 = 26;
      goto LABEL_249;
    }
    v63 = *v62 < 12800;
    v64 = v9 + 4040;
    if ( !v63 && (*v64 & 1) != 0 && !*(_QWORD *)(v11 + 1008) )
    {
      LODWORD(v20) = -1073741735;
      WdLogSingleEntry1(2, -1073741735);
      WdLogGlobalForLineNumber = 16015;
      v21 = 19;
      goto LABEL_249;
    }
    if ( qword_140162E70 )
    {
      v66 = v9 + 2716;
      if ( v9[2716] && (v61 & 1) != 0 && !(_BYTE)word_140162E5D )
        qword_140162E70 = v7;
    }
    else
    {
      if ( (v61 & 1) != 0
        || (unsigned __int8)DpiHybridInternalPanelOverride()
        && (*v64 & 0x20) != 0
        && (unsigned __int8)DpiFdoIsPostDevice(v7)
        && (v65 & 0x40) == 0 )
      {
        qword_140162E70 = v7;
      }
      v66 = v9 + 2716;
    }
    if ( (*v64 & 0x40) != 0 )
    {
      if ( qword_140162E68 && qword_140162E68 != v7 )
      {
        if ( !*v66 || (_BYTE)word_140162E5D )
        {
          *v64 &= ~0x40u;
          goto LABEL_159;
        }
        *(_BYTE *)(*(_QWORD *)(qword_140162E68 + 64) + 4040LL) &= ~0x40u;
      }
      qword_140162E68 = v7;
      HIBYTE(word_140162E5D) = (v9[4041] & 2) != 0;
    }
LABEL_159:
    if ( !qword_140162E70 || !qword_140162E68 || (_BYTE)word_140162E5D )
      goto LABEL_165;
    v67 = *(_BYTE *)(*(_QWORD *)(qword_140162E70 + 64) + 2716LL);
    if ( *(_BYTE *)(*(_QWORD *)(qword_140162E68 + 64) + 2716LL) )
    {
      if ( !v67 )
        goto LABEL_164;
    }
    else if ( v67 )
    {
LABEL_164:
      LOBYTE(word_140162E5D) = 0;
LABEL_165:
      v68 = v167;
      if ( v167 )
      {
        *v167 = *(_QWORD *)v64;
        *((_DWORD *)v68 + 2) = *((_DWORD *)v9 + 1012);
      }
      if ( (unsigned __int8)DpiFdoIsPostDevice(v7) && (*v64 & 1) == 0 && !DeviceExtension[2719] )
      {
        LODWORD(v20) = -1071775740;
        WdLogSingleEntry1(2, -1071775740);
        WdLogGlobalForLineNumber = 16151;
        v21 = 20;
        goto LABEL_249;
      }
      DpiMdmProcessStartAdapter();
      if ( *((_DWORD *)v9 + 904) )
      {
        v69 = *((_QWORD *)v9 + 6);
        v70 = *((_QWORD *)v9 + 5);
        v170 = 0;
        LODWORD(v170) = 67108861;
        v171 = 0;
        v71 = DpiDxgkDdiDisplayDetectControl(v9, v70, v69, &v170);
        LODWORD(v20) = v71;
        if ( v71 < 0 )
        {
          WdLogSingleEntry2(2, *(_QWORD *)(v11 + 1128), v71);
          WdLogGlobalForLineNumber = 16184;
          v21 = 4;
          goto LABEL_249;
        }
      }
      if ( (unsigned int)Feature_PanelBufferControl__private_IsEnabledDeviceUsageNoInline() )
      {
        v72 = DpiFdoInitializePanelBufferControl((struct _DEVICE_OBJECT *)v7);
        LODWORD(v20) = v72;
        if ( v72 < 0 )
        {
          WdLogSingleEntry1(2, v72);
          WdLogGlobalForLineNumber = 16202;
          v21 = 27;
          goto LABEL_249;
        }
      }
      DpiFdoInitializeMipiDsi(v7);
      v73 = P;
      RelatedObjects = DpiFdoCreateRelatedObjects(v7, *((unsigned int *)v9 + 677), P, v153);
      LODWORD(v20) = RelatedObjects;
      if ( RelatedObjects < 0 )
      {
        WdLogSingleEntry1(2, RelatedObjects);
        WdLogGlobalForLineNumber = 16229;
        v21 = 11;
        goto LABEL_249;
      }
      if ( (*v64 & 1) != 0 )
      {
        LOBYTE(v75) = 1;
        if ( (int)DpiAcquireCoreSyncAccessSafe(v7, v75) >= 0 )
        {
          MonitorInitializeAdapterDone(*((DXGADAPTER **)v9 + 504), v153);
          LOBYTE(v76) = 1;
          DpiReleaseCoreSyncAccessSafe(v7, v76);
        }
      }
      v141 = 1;
      if ( *((_DWORD *)v9 + 840) != -1 )
      {
        Caps = DpiMiracastDdiMiracastQueryCaps(v9, v75, v9 + 3352);
        if ( Caps < 0 )
        {
          WdLogSingleEntry1(4, Caps);
          WdLogGlobalForLineNumber = 16269;
          *((_DWORD *)v9 + 840) = -1;
          memset(v9 + 3288, 0, 0x40u);
        }
      }
      v78 = DpiOpenPnpRegistryKey(v7, 2, 131097, &Handle);
      if ( v78 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"MiracastDriverName");
        if ( (int)DxgkRetrieveStringFromRegistry(Handle, &DestinationString) < 0 )
        {
          WdLogSingleEntry1(4, DxgkRetrieveStringFromRegistry);
          WdLogGlobalForLineNumber = 16315;
        }
        ZwClose(Handle);
      }
      else
      {
        WdLogSingleEntry1(4, v78);
        WdLogGlobalForLineNumber = 16290;
      }
      v81 = *((_QWORD *)v9 + 626);
      if ( v81 )
      {
        if ( *(_QWORD *)(v81 + 48) && *(_BYTE *)v81 )
        {
          v29 = bTracingEnabled == 0;
          *(_BYTE *)v81 = 0;
          if ( !v29 && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
            McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventDpiFdoThermalActiveCooling, v80, v7);
          v82 = *((_QWORD *)v9 + 626);
          LOBYTE(v79) = *(_BYTE *)(v82 + 2);
          (*(void (__fastcall **)(_QWORD, __int64))(v82 + 48))(*(_QWORD *)(v82 + 16), v79);
        }
        v83 = *((_QWORD *)v9 + 626);
        if ( *(_QWORD *)(v83 + 56) && *(_BYTE *)(v83 + 1) )
        {
          v29 = bTracingEnabled == 0;
          *(_BYTE *)(v83 + 1) = 0;
          if ( !v29 && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
            McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, EventDpiFdoThermalPassiveCooling, v80, v7);
          (*(void (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)v9 + 626) + 56LL))(
            *(_QWORD *)(*((_QWORD *)v9 + 626) + 16LL),
            *(unsigned int *)(*((_QWORD *)v9 + 626) + 4LL));
        }
      }
      v84 = DpiFdoInitializeGpuVirtualization(v7);
      LODWORD(v20) = v84;
      if ( v84 < 0 )
      {
        WdLogSingleEntry1(2, v84);
        WdLogGlobalForLineNumber = 16370;
        v21 = 5;
        goto LABEL_249;
      }
      if ( v9[482] )
      {
        Feature_SupportWaitWakeForPowerRuntimeD3__private_IsEnabledPreCheck(v85);
        if ( *(_DWORD *)(*((_QWORD *)v9 + 5) + 28LL) >= 0x11008u
          && (*((_DWORD *)v9 + 331) & 0x2000) != 0
          && *((int *)v9 + 342) >= 4
          && (int)DpiQueryMiniportInterface(v7, (unsigned int)&GUID_WDDM_INTERFACE_WAITWAKE, 48, 1) >= 0
          && *((_WORD *)v9 + 1392) == 48
          && *((_WORD *)v9 + 1393) == 1
          && *((_QWORD *)v9 + 352)
          && *((_QWORD *)v9 + 353) )
        {
          v29 = *((_QWORD *)v9 + 346) == 0;
          *((_DWORD *)v9 + 694) = 0;
          if ( !v29 || (WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)v7), (*((_QWORD *)v9 + 346) = WorkItem) != 0) )
          {
            v9[2726] = 1;
          }
          else
          {
            WdLogSingleEntry1(6, -1073741670);
            WdLogGlobalForLineNumber = 16432;
          }
        }
        DXGADAPTER::StartRuntimePowerManagement(*((DXGADAPTER **)v9 + 504));
        if ( v9[5816] )
        {
          v87 = IoSetDeviceInterfaceState((PUNICODE_STRING)(v9 + 5800), 1u);
          LODWORD(v20) = v87;
          if ( v87 < 0 )
          {
            WdLogSingleEntry1(2, v87);
            WdLogGlobalForLineNumber = 16454;
            v21 = 22;
            goto LABEL_249;
          }
        }
      }
      DpiBrightnessStartDevice((struct _DEVICE_OBJECT *)v7);
      DpiMdmProcessAdapterBrightness(v7);
      DpiFdoInitializeDP(v7);
      DpiFdoInitializeDisplayDiagnostics(v7);
      goto LABEL_226;
    }
    LOBYTE(word_140162E5D) = 1;
    *((_BYTE *)DXGGLOBAL::GetGlobal() + 929) = 1;
    goto LABEL_165;
  }
  WdLogSingleEntry2(2, *(_QWORD *)(v11 + 152), v20);
  WdLogGlobalForLineNumber = 15726;
  if ( (_DWORD)v20 == -1071775735 )
  {
    Interval.QuadPart = 0;
    if ( !(unsigned __int8)DpiFdoIsPostDevice(v7) )
    {
      v21 = 14;
      goto LABEL_249;
    }
    DevicePropertyString = DpiGetDevicePropertyString(
                             *((PDEVICE_OBJECT *)DeviceExtension + 19),
                             DevicePropertyHardwareID,
                             (__int64)&v150);
    if ( DevicePropertyString < 0 )
    {
      WdLogSingleEntry1(2, DevicePropertyString);
      WdLogGlobalForLineNumber = 15767;
      v21 = 13;
      goto LABEL_249;
    }
    WdDiagNotifyUser(8, 5, 1, &Interval);
    if ( Interval.QuadPart )
    {
      ExFreePoolWithTag((PVOID)Interval.QuadPart, 0);
      Interval.QuadPart = 0;
    }
  }
  else if ( (_DWORD)v20 == -1071774944 && (unsigned __int8)DpiFdoIsPostDevice(v7) )
  {
    WdLogSingleEntry5(0, 275, 26, v11, (unsigned __int8)byte_140162E56, 0);
    WdLogGlobalForLineNumber = 15791;
  }
  v21 = 1;
LABEL_249:
  v151 = (int)v20;
  if ( v9 )
    v99 = *((_QWORD *)v9 + 504);
  else
    LODWORD(v99) = 0;
  DxgkLogInternalTriageEvent(
    v99,
    131076,
    -1,
    (unsigned int)L"Adapter StartDevice has completed with status %1",
    (int)v20,
    0,
    0,
    0,
    0);
  if ( v9 )
  {
    v100 = *((_QWORD *)v9 + 504);
    if ( !v100 || v21 )
      LogAdapterStartTelemetry(v9, v153, (unsigned int)v20, v21);
    else
      DXGADAPTER::AdapterTelemetry(v100, 2, v153, (unsigned int)v20, 0);
    IsPostDevice = DpiFdoIsPostDevice(v7);
    v102 = *((_DWORD *)v9 + 126) != 0 ? 4 : 0;
    v104 = v9[480] & 1
         | (2
          * ((2 * (v9[2716] & 1 | (4 * (v103 & 0xFFFFFF84 | v9[4041] & 1 | (2 * (v103 & 0x38 | v102 | v9[1158] & 1))))))
           | IsPostDevice & 1));
    v105 = v103 & 1;
    v106 = (v103 >> 1) & 0x21;
    v107 = v106 | (2 * (v105 | (2 * v104)));
    if ( (int)v20 >= 0 )
      goto LABEL_318;
  }
  else
  {
    if ( (int)v20 >= 0 )
    {
      v107 = 0;
      goto LABEL_318;
    }
    MicrosoftTelemetryAssertTriggeredMsgKM("DpiFdoStartAdapter failed and FdoContext is null");
    v107 = 0;
  }
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x80000000LL) != 0 )
  {
    if ( v9 )
      v108 = *((_DWORD *)v9 + 281);
    else
      v108 = 0;
    McTemplateK0qqq_EtwWriteTransfer(v102, (unsigned int)DpiFdoStartAdapterFailed, v106, v108, v20, v21);
  }
  v109 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 19);
  DeviceExtension[232] = 1;
  IoInvalidateDeviceState(v109);
  if ( *((_DWORD *)DeviceExtension + 59) == 2 )
  {
    v110 = *((_DWORD *)DeviceExtension + 60);
    --*((_DWORD *)DeviceExtension + 69);
    *((_DWORD *)DeviceExtension + 59) = v110;
    *((_DWORD *)DeviceExtension + 60) = *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244];
  }
  if ( v9 )
  {
    if ( v145 == 1 )
      IoSetDeviceInterfaceState((PUNICODE_STRING)v9 + 178, 0);
    if ( v146 == 1 )
      IoSetDeviceInterfaceState((PUNICODE_STRING)v9 + 179, 0);
    DpiFdoCleanupFeatureDatabase((struct _FDO_CONTEXT *)v9);
    DpiFdoCleanupGpuVirtualization(v9);
    DpiFdoCleanupMipiDsi(v9);
    DpiFdoCleanupDP(v9);
    DpiFdoCleanupDisplayDiagnostics(v9);
    if ( v141 == 1 )
      DpiFdoDestroyRelatedObjects(v7, v153);
    if ( P )
    {
      v113 = *((_DWORD *)v9 + 677);
      if ( v113 )
      {
        v114 = (unsigned int *)P;
        do
        {
          --v113;
          LOBYTE(v111) = v9[2847];
          LOBYTE(v112) = 1;
          DxgkReleaseGdiViewId(v111, *((_QWORD *)v9 + 736), v114[v113], v112);
        }
        while ( v113 );
        v7 = (__int64)DeviceObject;
        v11 = v163;
      }
    }
    if ( qword_140162E68 == v7 )
    {
      qword_140162E68 = 0;
      word_140162E5D = 0;
    }
    if ( qword_140162E70 == v7 )
    {
      LOBYTE(word_140162E5D) = 0;
      qword_140162E70 = 0;
    }
    if ( v142 == 1 )
    {
      if ( *((_QWORD *)DeviceExtension + 61) )
      {
        PoFxUnregisterDevice();
        *(_QWORD *)(*((_QWORD *)v9 + 504) + 3360LL) = 0;
        *((_QWORD *)DeviceExtension + 61) = 0;
      }
      DpiRemoveAdapter(v153, 0);
      DxgkReleaseAdapterFdoReference(*((DXGADAPTER **)v9 + 504));
      *((_QWORD *)v9 + 504) = 0;
    }
    DpiFdoRemoveChildDescriptors(v7);
    v115 = (void (__fastcall *)(_QWORD))*((_QWORD *)v9 + 351);
    if ( v115 )
    {
      v115(*((_QWORD *)v9 + 349));
      *((_OWORD *)v9 + 174) = 0;
      *((_OWORD *)v9 + 175) = 0;
      *((_OWORD *)v9 + 176) = 0;
    }
  }
  if ( v147 == 1 && v11 )
  {
    if ( !(unsigned __int8)DpiFdoIsMsBddAnchoredDevice(v7) && !(unsigned __int8)DpiFdoIsPostDevice(v116)
      || (int)DpiFdoStopDeviceAndReleasePostDisplayOwnership(v7, 1) < 0 )
    {
      DpiDxgkDdiStopDevice(v11, *((_QWORD *)DeviceExtension + 6));
    }
    if ( v9 )
      v9[4040] &= ~4u;
  }
  if ( v143 == 1 )
    DpiFdoDisconnectInterrupt(v7);
  v117 = DeviceExtension[1162];
  v144 = v117 == 0;
  if ( (unsigned int)(v20 + 1071774208) > 1 && !v117 )
  {
    if ( v147 )
      goto LABEL_313;
    if ( !*(_QWORD *)(v11 + 1344) )
      goto LABEL_313;
    DiagnosticInfoArgs = DxgAllocateDiagnosticInfoArgs(2);
    v119 = DiagnosticInfoArgs;
    if ( !DiagnosticInfoArgs )
      goto LABEL_313;
    *(_QWORD *)DiagnosticInfoArgs = *((_QWORD *)DeviceExtension + 6);
    v120 = *((_QWORD *)DeviceExtension + 19);
    LODWORD(v150) = *(_DWORD *)(DiagnosticInfoArgs + 216);
    if ( (*(int (__fastcall **)(__int64, __int64))(v11 + 1344))(v120, DiagnosticInfoArgs) >= 0 )
    {
      if ( *(_DWORD *)(v119 + 220) > (unsigned int)v150 )
        *(_DWORD *)(v119 + 220) = 0;
      if ( v11 )
        v121 = *(_QWORD *)(v11 + 152);
      else
        v121 = 0;
      DxgCreateLiveDumpWithDriverBlob(
        *((struct _DEVICE_OBJECT **)DeviceExtension + 19),
        0x1B0u,
        *(int *)(v119 + 8),
        v151,
        v107,
        v121,
        (struct _DXGKARG_COLLECTDIAGNOSTICINFO *)v119);
      v144 = 0;
    }
    DxgFreeDiagnosticInfoArgs((struct _DXGKARG_COLLECTDIAGNOSTICINFO *)v119);
    if ( v144 )
    {
LABEL_313:
      if ( v11 )
        v122 = *(_QWORD *)(v11 + 152);
      else
        v122 = 0;
      LOBYTE(v140) = 1;
      DxgCreateLiveDumpWithWdLogs(403, 2052, v151, v107, v122, v140);
    }
  }
LABEL_318:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( DeviceExtension[1153] && (unsigned __int8)DpiFdoIsPostDevice(v7) )
    NotifyUserMSBDAIfApplicable();
  if ( v9 )
  {
    v123 = 0;
    LODWORD(v150) = 0;
    if ( DeviceExtension[1158] )
    {
      v124 = *((_QWORD *)v9 + 126);
      if ( v124 )
      {
        v125 = (__int64 (__fastcall *)(__int64, _QWORD))*((_QWORD *)v9 + 133);
        if ( v125 )
        {
          v126 = v125(v124, (unsigned int)v20);
          if ( v126 < 0 )
          {
            WdLogSingleEntry2(2, *((_QWORD *)v9 + 133), v126);
            WdLogGlobalForLineNumber = 16902;
          }
        }
        v127 = (__int64 (__fastcall *)(__int64, __int128 *))*((_QWORD *)v9 + 135);
        if ( v127 )
        {
          v171 = 0;
          v128 = *((_QWORD *)v9 + 126);
          v170 = 0;
          v129 = v127(v128, &v170);
          if ( v129 < 0 )
          {
            WdLogSingleEntry2(2, *((_QWORD *)v9 + 135), v129);
            WdLogGlobalForLineNumber = 16922;
          }
          else
          {
            v123 = *((_QWORD *)&v170 + 1);
            *((_DWORD *)v9 + 291) = DWORD1(v170);
            LODWORD(v150) = v171;
          }
        }
      }
    }
    v130 = (_DWORD *)ExAllocatePool2(256, 96, 1953656900);
    v131 = v130;
    if ( v130 )
    {
      memset(v130, 0, 0x60u);
      v132 = *((_QWORD *)DeviceExtension + 337);
      *v131 = 41;
      v131[13] = v7 & 0xFFFF00;
      v131[1] = 96;
      v131[12] = v20;
      *((_QWORD *)v131 + 7) = v132;
      v133 = DxgkDiagCalcDuration1us(&v164);
      v134 = *((_QWORD *)v9 + 736);
      v131[16] = v133;
      v131[17] = *((_DWORD *)v9 + 1012);
      v131[22] = v150;
      v131[18] = v107;
      *((_QWORD *)v131 + 10) = v123;
      DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v131, v134);
      ExFreePoolWithTag(v131, 0x74727044u);
    }
    if ( qword_1401630F8 == v7 )
    {
      v135 = *((_QWORD *)v9 + 5);
      if ( v135 )
      {
        if ( *(_QWORD *)(v135 + 408) )
          SendBDDDiagTelemetry(v9);
      }
    }
  }
  else
  {
    v136 = (_DWORD *)ExAllocatePool2(256, 64, 1953656900);
    v137 = v136;
    if ( v136 )
    {
      memset(v136, 0, 0x40u);
      v138 = DxgkDiagCalcDuration1us(&v164);
      *v137 = 6;
      v137[1] = 64;
      v137[10] = 0;
      *((_QWORD *)v137 + 4) = 0;
      *((_QWORD *)v137 + 1) = 0;
      *((_OWORD *)v137 + 1) = 0;
      v137[12] = 35;
      v137[13] = v7 & 0xFFFF00;
      v137[14] = v138;
      v137[15] = v20;
      DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v137, 0x200000000uLL);
      ExFreePoolWithTag(v137, 0x74727044u);
    }
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1402b21a0  mov     [rsp-8+arg_8], rbx
0x1402b21a5  push    rbp
0x1402b21a6  push    rsi
0x1402b21a7  push    rdi
0x1402b21a8  push    r12
0x1402b21aa  push    r13
0x1402b21ac  push    r14
0x1402b21ae  push    r15
0x1402b21b0  lea     rbp, [rsp-0B0h]
0x1402b21b8  sub     rsp, 1B0h
0x1402b21bf  mov     rax, cs:__security_cookie
0x1402b21c6  xor     rax, rsp
0x1402b21c9  mov     [rbp+0E0h+var_38], rax
0x1402b21d0  mov     rax, [rbp+0E0h+arg_28]
0x1402b21d7  mov     r13, rcx
0x1402b21da  xorps   xmm0, xmm0
0x1402b21dd  mov     [rbp+0E0h+DeviceObject], rcx
0x1402b21e1  mov     rcx, [rbp+0E0h+arg_30]
0x1402b21e8  mov     bl, dl
0x1402b21ea  movups  [rbp+0E0h+var_78], xmm0
0x1402b21ee  mov     [rsp+1E0h+var_178], rax
0x1402b21f3  mov     rax, 0FFFFF78000000320h
0x1402b21fd  movups  [rbp+0E0h+var_78+0Ch], xmm0
0x1402b2201  mov     [rbp+0E0h+var_F8], rcx
0x1402b2205  xor     ecx, ecx
0x1402b2207  mov     [rbp+0E0h+Handle], rcx
0x1402b220b  mov     esi, ecx
0x1402b220d  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x1402b2211  mov     rax, [rax]
0x1402b2214  mov     r15, [r13+40h]
0x1402b2218  lea     edi, [rcx+3]
0x1402b221b  mov     [rsp+1E0h+var_168], r9
0x1402b2220  mov     [rbp+0E0h+var_100], r8
0x1402b2224  mov     [rsp+1E0h+var_18A], dl
0x1402b2228  cmp     dword ptr [r15+10h], 74727044h
0x1402b2230  mov     r12, [r15+28h]
0x1402b2234  mov     [rbp+0E0h+var_118], r12
0x1402b2238  mov     [rsp+1E0h+var_18E], cl
0x1402b223c  mov     [rsp+1E0h+var_18B], cl
0x1402b2240  mov     [rsp+1E0h+var_18F], cl
0x1402b2244  mov     [rsp+1E0h+var_190], cl
0x1402b2248  mov     [rsp+1E0h+var_18D], cl
0x1402b224c  mov     [rsp+1E0h+var_18C], cl
0x1402b2250  mov     [rsp+1E0h+P], rcx
0x1402b2255  mov     [rbp+0E0h+var_110], rax
0x1402b2259  mov     [rbp+0E0h+var_108], rdi
0x1402b225d  jnz     loc_1402B241E
0x1402b2263  cmp     dword ptr [r15+14h], 2
0x1402b2268  jnz     loc_1402B241E
0x1402b226e  lea     rbx, [r15+3E8h]
0x1402b2275  mov     rsi, r15
0x1402b2278  cmp     [r12+86h], cl
0x1402b2280  jz      loc_1402B2401
0x1402b2286  lea     r8d, [rcx+70h]
0x1402b228a  mov     [rsp+1E0h+var_1B8], rbx
0x1402b228f  mov     rcx, [r15+18h]
0x1402b2293  lea     rdx, GUID_DEVINTERFACE_INDIRECT_DISP_KMD
0x1402b229a  mov     r9d, edi
0x1402b229d  call    DpiQueryMiniportInterface
0x1402b22a2  mov     r14d, eax
0x1402b22a5  test    eax, eax
0x1402b22a7  jns     loc_1402B2397
0x1402b22ad  xor     edx, edx; Val
0x1402b22af  lea     r8d, [rdi+6Dh]; Size
0x1402b22b3  mov     rcx, rbx; void *
0x1402b22b6  call    memset
0x1402b22bb  test    r14d, r14d
0x1402b22be  js      loc_1402B240F
0x1402b22c4  mov     ebx, 50h ; 'P'
0x1402b22c9  lea     rcx, [rbp+0E0h+var_E0]; void *
0x1402b22cd  mov     r8d, ebx; Size
0x1402b22d0  xor     edx, edx; Val
0x1402b22d2  call    memset
0x1402b22d7  mov     rcx, [r15+18h]
0x1402b22db  lea     rax, [rbp+0E0h+var_E0]
0x1402b22df  lea     r14d, [rbx-4Fh]
0x1402b22e3  mov     [rsp+1E0h+var_1B8], rax
0x1402b22e8  mov     r9d, r14d
0x1402b22eb  lea     rdx, GUID_DEVINTERFACE_DOD_EXTENDED
0x1402b22f2  mov     r8d, ebx
0x1402b22f5  call    DpiQueryMiniportInterface
0x1402b22fa  test    eax, eax
0x1402b22fc  js      loc_1402B240F
0x1402b2302  cmp     word ptr [rbp+0E0h+var_E0], bx
0x1402b2306  jnz     loc_1402B240F
0x1402b230c  cmp     word ptr [rbp+0E0h+var_E0+2], r14w
0x1402b2311  jnz     loc_1402B240F
0x1402b2317  mov     r10, [rbp+0E0h+var_C0]
0x1402b231b  test    r10, r10
0x1402b231e  jz      loc_1402B240F
0x1402b2324  mov     r9, [rbp+0E0h+var_B8]
0x1402b2328  test    r9, r9
0x1402b232b  jz      loc_1402B240F
0x1402b2331  mov     r8, [rbp+0E0h+var_B0]
0x1402b2335  test    r8, r8
0x1402b2338  jz      loc_1402B240F
0x1402b233e  mov     rdx, [rbp+0E0h+var_A8]
0x1402b2342  test    rdx, rdx
0x1402b2345  jz      loc_1402B240F
0x1402b234b  mov     rcx, [rbp+0E0h+var_A0]
0x1402b234f  test    rcx, rcx
0x1402b2352  jz      loc_1402B240F
0x1402b2358  mov     rax, [rbp+0E0h+var_98]
0x1402b235c  test    rax, rax
0x1402b235f  jz      loc_1402B240F
0x1402b2365  mov     [r12+3F0h], r10
0x1402b236d  mov     [r12+440h], r9
0x1402b2375  mov     [r12+468h], r8
0x1402b237d  mov     [r12+470h], rdx
0x1402b2385  mov     [r12+520h], rcx
0x1402b238d  mov     [r12+448h], rax
0x1402b2395  jmp     short loc_1402B240F
0x1402b2397  mov     r8, [rsp+1E0h+var_178]
0x1402b239c  test    r8, r8
0x1402b239f  jz      loc_1402B22BB
0x1402b23a5  mov     rax, [r15+418h]
0x1402b23ac  test    rax, rax
0x1402b23af  jz      loc_1402B22BB
0x1402b23b5  mov     edx, [rbp+0E0h+arg_20]
0x1402b23bb  mov     rcx, [r15+3F0h]
0x1402b23c2  call    _guard_dispatch_icall
0x1402b23c7  movsxd  r14, eax
0x1402b23ca  test    eax, eax
0x1402b23cc  jns     loc_1402B22C4
0x1402b23d2  mov     rdx, [r15+418h]
0x1402b23d9  mov     r8, r14
0x1402b23dc  mov     ecx, 2
0x1402b23e1  call    cs:__imp_WdLogSingleEntry2
0x1402b23e8  nop     dword ptr [rax+rax+00h]
0x1402b23ed  mov     cs:WdLogGlobalForLineNumber, 3B66h
0x1402b23f7  mov     edi, 19h
0x1402b23fc  jmp     loc_1402B3B0B
0x1402b2401  xor     edx, edx; Val
0x1402b2403  mov     rcx, rbx; void *
0x1402b2406  lea     r8d, [rdx+70h]; Size
0x1402b240a  call    memset
0x1402b240f  mov     bl, [rsp+1E0h+var_18A]
0x1402b2413  mov     dword ptr [r15+1018h], 0
0x1402b241e  mov     rcx, r13
0x1402b2421  call    DpiFdoConnectInterrupt
0x1402b2426  movsxd  r14, eax
0x1402b2429  cmp     r14d, 0C0000225h
0x1402b2430  jnz     short loc_1402B2452
0x1402b2432  mov     rdx, r13
0x1402b2435  mov     ecx, 4
0x1402b243a  call    cs:__imp_WdLogSingleEntry1
0x1402b2441  nop     dword ptr [rax+rax+00h]
0x1402b2446  mov     cs:WdLogGlobalForLineNumber, 3BB0h
0x1402b2450  jmp     short loc_1402B2483
0x1402b2452  test    eax, eax
0x1402b2454  jns     short loc_1402B247E
0x1402b2456  mov     rdx, r14
0x1402b2459  mov     ecx, 2
0x1402b245e  call    cs:__imp_WdLogSingleEntry1
0x1402b2465  nop     dword ptr [rax+rax+00h]
0x1402b246a  mov     cs:WdLogGlobalForLineNumber, 3BBDh
0x1402b2474  mov     edi, 0Ah
0x1402b2479  jmp     loc_1402B3B0B
0x1402b247e  mov     [rsp+1E0h+var_18E], 1
0x1402b2483  mov     rcx, r13
0x1402b2486  call    DpiFdoIsPostDevice
0x1402b248b  xor     r14d, r14d
0x1402b248e  test    al, al
0x1402b2490  jz      loc_1402B25A5
0x1402b2496  cmp     byte ptr [r15+483h], 1
0x1402b249e  jnz     loc_1402B2570
0x1402b24a4  test    bl, bl
0x1402b24a6  jz      loc_1402B2570
0x1402b24ac  cmp     cs:byte_140162E56, r14b
0x1402b24b3  jz      loc_1402B2570
0x1402b24b9  call    DpiFdoIsCompatibleWithHighResolutionBoot
0x1402b24be  test    al, al
0x1402b24c0  jnz     loc_1402B2570
0x1402b24c6  test    byte ptr cs:qword_1401604F0, 2
0x1402b24cd  lea     ebx, [r14+1]
0x1402b24d1  mov     dword ptr [rbp+0E0h+var_90], 0FFFFFFFFh
0x1402b24d8  mov     qword ptr [rbp+0E0h+var_90+8], r14
0x1402b24dc  jz      short loc_1402B2504
0x1402b24de  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x1402b24e4  mov     byte ptr [rbp+0E0h+var_80], bl
0x1402b24e7  mov     dword ptr [rbp+0E0h+var_90], 1F46h
0x1402b24ee  jz      short loc_1402B2508
0x1402b24f0  mov     r9d, 1F46h
0x1402b24f6  lea     rdx, EventProfilerEnter
0x1402b24fd  call    McTemplateK0q_EtwWriteTransfer
0x1402b2502  jmp     short loc_1402B2508
0x1402b2504  mov     byte ptr [rbp+0E0h+var_80], r14b
0x1402b2508  mov     edx, 1F46h
0x1402b250d  lea     rcx, [rbp+0E0h+var_90]
0x1402b2511  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1402b2516  xorps   xmm0, xmm0
0x1402b2519  lea     rdx, [rbp+0E0h+var_58]
0x1402b2520  movups  [rbp+0E0h+var_58], xmm0
0x1402b2527  mov     ecx, 10h
0x1402b252c  mov     dword ptr [rbp+0E0h+var_58], 12h
0x1402b2536  movups  [rbp+0E0h+var_48], xmm0
0x1402b253d  call    cs:__imp_x86BiosCall
0x1402b2544  nop     dword ptr [rax+rax+00h]
0x1402b2549  lea     rcx, [rbp+0E0h+var_90]; this
0x1402b254d  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1402b2552  cmp     byte ptr [rbp+0E0h+var_80], r14b
0x1402b2556  jz      short loc_1402B2570
0x1402b2558  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x1402b255e  jz      short loc_1402B2570
0x1402b2560  mov     r9d, dword ptr [rbp+0E0h+var_90]
0x1402b2564  lea     rdx, EventProfilerExit
0x1402b256b  call    McTemplateK0q_EtwWriteTransfer
0x1402b2570  test    rsi, rsi
0x1402b2573  jz      short loc_1402B25A5
0x1402b2575  cmp     cs:byte_140162E56, r14b
0x1402b257c  mov     eax, [r12+1Ch]
0x1402b2581  jz      short loc_1402B258A
0x1402b2583  cmp     eax, 300Eh
0x1402b2588  jmp     short loc_1402B258F
0x1402b258a  cmp     eax, 2005h
0x1402b258f  mov     al, [rsi+0FC8h]
0x1402b2595  setnbe  cl
0x1402b2598  shl     cl, 2
0x1402b259b  and     al, 0FBh
0x1402b259d  or      cl, al
0x1402b259f  mov     [rsi+0FC8h], cl
0x1402b25a5  mov     qword ptr [rsp+1E0h+Interval], r14
0x1402b25aa  lea     rbx, [r15+0A78h]
0x1402b25b1  jmp     short loc_1402B25E3
0x1402b25b3  cmp     r14d, 0C000022Dh
0x1402b25ba  jnz     short loc_1402B263B
0x1402b25bc  lea     r8, [rsp+1E0h+Interval]; Interval
0x1402b25c1  mov     qword ptr [rsp+1E0h+Interval], 0FFFFFFFFFFFFD8F0h
0x1402b25ca  xor     edx, edx; Alertable
0x1402b25cc  xor     ecx, ecx; WaitMode
0x1402b25ce  call    cs:__imp_KeDelayExecutionThread
0x1402b25d5  nop     dword ptr [rax+rax+00h]
0x1402b25da  mov     qword ptr [rsp+1E0h+Interval], 0
0x1402b25e3  mov     rcx, rbx; Uuid
0x1402b25e6  call    cs:__imp_ExUuidCreate
0x1402b25ed  nop     dword ptr [rax+rax+00h]
0x1402b25f2  mov     r14d, eax
0x1402b25f5  test    eax, eax
0x1402b25f7  js      short loc_1402B25B3
0x1402b25f9  lea     rcx, [r15+0A88h]; Luid
0x1402b2600  call    cs:__imp_ZwAllocateLocallyUniqueId
0x1402b2607  nop     dword ptr [rax+rax+00h]
0x1402b260c  movsxd  r14, eax
0x1402b260f  test    eax, eax
0x1402b2611  jns     short loc_1402B2663
0x1402b2613  mov     rdx, r14
0x1402b2616  mov     ecx, 2
0x1402b261b  call    cs:__imp_WdLogSingleEntry1
0x1402b2622  nop     dword ptr [rax+rax+00h]
0x1402b2627  mov     cs:WdLogGlobalForLineNumber, 3C21h
0x1402b2631  mov     edi, 7
0x1402b2636  jmp     loc_1402B3B0B
0x1402b263b  movsxd  rdx, r14d
0x1402b263e  mov     ecx, 2
0x1402b2643  call    cs:__imp_WdLogSingleEntry1
0x1402b264a  nop     dword ptr [rax+rax+00h]
0x1402b264f  mov     cs:WdLogGlobalForLineNumber, 3C07h
0x1402b2659  mov     edi, 8
0x1402b265e  jmp     loc_1402B3B0B
0x1402b2663  test    rsi, rsi
0x1402b2666  jz      loc_1402B2747
0x1402b266c  call    DpiKsrIsSoftBoot
0x1402b2671  test    al, al
0x1402b2673  jz      short loc_1402B26E6
0x1402b2675  mov     rcx, rsi; struct _FDO_CONTEXT *
0x1402b2678  call    DpiKsrRestoreAdapterDriverState
0x1402b267d  test    eax, eax
0x1402b267f  jns     short loc_1402B26A1
0x1402b2681  movsxd  rdx, eax
0x1402b2684  mov     ecx, 2
0x1402b2689  call    cs:__imp_WdLogSingleEntry1
0x1402b2690  nop     dword ptr [rax+rax+00h]
0x1402b2695  mov     cs:WdLogGlobalForLineNumber, 3C36h
0x1402b269f  jmp     short loc_1402B26E6
0x1402b26a1  lea     r8, [rsp+1E0h+var_178]
0x1402b26a6  mov     dword ptr [rsp+1E0h+var_180], 0
0x1402b26ae  lea     rdx, [rsp+1E0h+var_180]
0x1402b26b3  mov     [rsp+1E0h+var_178], 0
0x1402b26bc  mov     rcx, r13
0x1402b26bf  call    DpiKsrGetSavedAdapterState
0x1402b26c4  test    eax, eax
0x1402b26c6  jns     short loc_1402B26E6
0x1402b26c8  movsxd  rdx, eax
0x1402b26cb  mov     ecx, 2
0x1402b26d0  call    cs:__imp_WdLogSingleEntry1
0x1402b26d7  nop     dword ptr [rax+rax+00h]
0x1402b26dc  mov     cs:WdLogGlobalForLineNumber, 3C44h
0x1402b26e6  mov     rcx, rsi; struct _FDO_CONTEXT *
0x1402b26e9  call    ?DpiFdoSetAdapterLuid@@YAJPEAU_FDO_CONTEXT@@@Z; DpiFdoSetAdapterLuid(_FDO_CONTEXT *)
0x1402b26ee  test    eax, eax
0x1402b26f0  jns     short loc_1402B2710
0x1402b26f2  movsxd  rdx, eax
0x1402b26f5  mov     ecx, 2
0x1402b26fa  call    cs:__imp_WdLogSingleEntry1
0x1402b2701  nop     dword ptr [rax+rax+00h]
0x1402b2706  mov     cs:WdLogGlobalForLineNumber, 3C52h
0x1402b2710  mov     rcx, r13
0x1402b2713  call    DpiFeatureStartDevice
0x1402b2718  movsxd  r14, eax
0x1402b271b  test    eax, eax
  ... truncated ...
```
