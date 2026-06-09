# DpiPdoDispatchInternalIoctl

- ea: `0x1403fa6d0`
- end: `0x1403fb7b9`
- name: `DpiPdoDispatchInternalIoctl`
- size: `4329`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400221b0`
- `0x140022434`
- `0x140030054`
- `0x140037028`
- `0x1400372f8`
- `0x140058c68`
- `0x14005ca20`
- `0x140081630`
- `0x14008e3f0`
- `0x14008e448`
- `0x14008e508`
- `0x1400a0cb0`
- `0x1401903fc`
- `0x140193c68`
- `0x140193d6c`
- `0x140193fd8`
- `0x140195264`
- `0x1402bbeec`
- `0x140348d14`
- `0x140348f90`
- `0x1403495cc`
- `0x14034b658`
- `0x140365ca4`
- `0x140366938`
- `0x140367554`
- `0x140367720`
- `0x140368554`
- `0x1403aa750`
- `0x1403fa6d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403fad5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403fad5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403fadc4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403fadc4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403fad83`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403fad83`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403fadb8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403fadb8`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403fb5c6`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403fb5c6`
- `ntoskrnl!IofCompleteRequest` at `0x1403fa770`
- `ntoskrnl!IofCompleteRequest` at `0x1403fa770`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fa8f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fab5c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb489`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fa8f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fab5c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fb489`
- `ntoskrnl!KeReleaseMutex` at `0x1403faa24`
- `ntoskrnl!KeReleaseMutex` at `0x1403fac86`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb6e7`
- `ntoskrnl!KeReleaseMutex` at `0x1403faa24`
- `ntoskrnl!KeReleaseMutex` at `0x1403fac86`
- `ntoskrnl!KeReleaseMutex` at `0x1403fb6e7`
- `ntoskrnl!IoGetRequestorSessionId` at `0x1403fa707`
- `ntoskrnl!IoGetRequestorSessionId` at `0x1403fa707`
- `watchdog!WdLogSingleEntry2` at `0x1403fb06c`
- `watchdog!WdLogSingleEntry2` at `0x1403fb2f0`
- `watchdog!WdLogSingleEntry2` at `0x1403fb06c`
- `watchdog!WdLogSingleEntry2` at `0x1403fb2f0`
- `watchdog!WdLogSingleEntry3` at `0x1403fa749`
- `watchdog!WdLogSingleEntry3` at `0x1403fa749`
- `watchdog!WdLogSingleEntry0` at `0x1403fafa0`
- `watchdog!WdLogSingleEntry0` at `0x1403fafc5`
- `watchdog!WdLogSingleEntry0` at `0x1403fb24e`
- `watchdog!WdLogSingleEntry0` at `0x1403fb273`
- `watchdog!WdLogSingleEntry0` at `0x1403fafa0`
- `watchdog!WdLogSingleEntry0` at `0x1403fafc5`
- `watchdog!WdLogSingleEntry0` at `0x1403fb24e`
- `watchdog!WdLogSingleEntry0` at `0x1403fb273`
- `watchdog!WdLogSingleEntry1` at `0x1403fa837`
- `watchdog!WdLogSingleEntry1` at `0x1403fa865`
- `watchdog!WdLogSingleEntry1` at `0x1403fa895`
- `watchdog!WdLogSingleEntry1` at `0x1403faa52`
- `watchdog!WdLogSingleEntry1` at `0x1403faa86`
- `watchdog!WdLogSingleEntry1` at `0x1403faac7`
- `watchdog!WdLogSingleEntry1` at `0x1403faaf5`
- `watchdog!WdLogSingleEntry1` at `0x1403facb8`
- `watchdog!WdLogSingleEntry1` at `0x1403face4`
- `watchdog!WdLogSingleEntry1` at `0x1403fad14`
- `watchdog!WdLogSingleEntry1` at `0x1403fad42`
- `watchdog!WdLogSingleEntry1` at `0x1403fadf1`
- `watchdog!WdLogSingleEntry1` at `0x1403fae1f`
- `watchdog!WdLogSingleEntry1` at `0x1403faed9`
- `watchdog!WdLogSingleEntry1` at `0x1403faff1`
- `watchdog!WdLogSingleEntry1` at `0x1403fb01a`
- `watchdog!WdLogSingleEntry1` at `0x1403fb0e9`
- `watchdog!WdLogSingleEntry1` at `0x1403fb182`
- `watchdog!WdLogSingleEntry1` at `0x1403fb1d9`
- `watchdog!WdLogSingleEntry1` at `0x1403fb29f`
- `watchdog!WdLogSingleEntry1` at `0x1403fb3b5`
- `watchdog!WdLogSingleEntry1` at `0x1403fb3e4`
- `watchdog!WdLogSingleEntry1` at `0x1403fb414`
- `watchdog!WdLogSingleEntry1` at `0x1403fb5e1`
- `watchdog!WdLogSingleEntry1` at `0x1403fb715`
- `watchdog!WdLogSingleEntry1` at `0x1403fb749`
- `watchdog!WdLogSingleEntry1` at `0x1403fb775`
- `watchdog!WdLogSingleEntry1` at `0x1403fa837`
- `watchdog!WdLogSingleEntry1` at `0x1403fa865`
- `watchdog!WdLogSingleEntry1` at `0x1403fa895`
- `watchdog!WdLogSingleEntry1` at `0x1403faa52`
- `watchdog!WdLogSingleEntry1` at `0x1403faa86`
- `watchdog!WdLogSingleEntry1` at `0x1403faac7`
- `watchdog!WdLogSingleEntry1` at `0x1403faaf5`
- `watchdog!WdLogSingleEntry1` at `0x1403facb8`
- `watchdog!WdLogSingleEntry1` at `0x1403face4`
- `watchdog!WdLogSingleEntry1` at `0x1403fad14`
- `watchdog!WdLogSingleEntry1` at `0x1403fad42`
- `watchdog!WdLogSingleEntry1` at `0x1403fadf1`
- `watchdog!WdLogSingleEntry1` at `0x1403fae1f`
- `watchdog!WdLogSingleEntry1` at `0x1403faed9`
- `watchdog!WdLogSingleEntry1` at `0x1403faff1`
- `watchdog!WdLogSingleEntry1` at `0x1403fb01a`
- `watchdog!WdLogSingleEntry1` at `0x1403fb0e9`
- `watchdog!WdLogSingleEntry1` at `0x1403fb182`
- `watchdog!WdLogSingleEntry1` at `0x1403fb1d9`
- `watchdog!WdLogSingleEntry1` at `0x1403fb29f`
- `watchdog!WdLogSingleEntry1` at `0x1403fb3b5`
- `watchdog!WdLogSingleEntry1` at `0x1403fb3e4`
- `watchdog!WdLogSingleEntry1` at `0x1403fb414`
- `watchdog!WdLogSingleEntry1` at `0x1403fb5e1`
- `watchdog!WdLogSingleEntry1` at `0x1403fb715`
- `watchdog!WdLogSingleEntry1` at `0x1403fb749`
- `watchdog!WdLogSingleEntry1` at `0x1403fb775`

## pseudocode

```c
__int64 __fastcall DpiPdoDispatchInternalIoctl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v5; // rdi
  NTSTATUS SourceConnectedToTargetInClientVidPn; // ebx
  unsigned int LowPart; // eax
  __int64 v8; // rcx
  unsigned __int64 Information; // rdi
  PIRP v10; // rcx
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY Length; // ecx
  unsigned int Options; // edx
  struct _DEVICE_OBJECT *v14; // r8
  union _LARGE_INTEGER *Parameters; // r14
  char *DeviceExtension; // rsi
  _BYTE *UserBuffer; // r13
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  NTSTATUS v26; // eax
  int v27; // edx
  int v28; // ecx
  int v29; // r8d
  unsigned __int64 v30; // r12
  int v31; // edx
  int v32; // ecx
  int v33; // r8d
  int v34; // edx
  int v35; // ecx
  int v36; // r8d
  int v37; // edx
  int v38; // ecx
  int v39; // r8d
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  DXGADAPTER *v48; // rbx
  __int64 v49; // rsi
  MONITOR_MGR *v50; // rdi
  unsigned int v51; // edx
  void *v52; // rcx
  DXGADAPTER *v53; // rbx
  __int64 v54; // rsi
  ULONG v55; // r12d
  MONITOR_MGR *v56; // rdi
  bool v57; // zf
  int v58; // edx
  int v59; // ecx
  int v60; // r8d
  _DWORD *v61; // r12
  __int64 (__fastcall *v62)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD); // rax
  __int64 HighPart; // r9
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // rdx
  NTSTATUS v67; // eax
  __int64 (__fastcall *v68)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  __int64 v69; // r9
  __int64 v70; // r8
  __int64 v71; // rcx
  __int64 v72; // rdx
  int v73; // edx
  int v74; // ecx
  int v75; // r8d
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v76; // r13d
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-99h]
  PLARGE_INTEGER Timeouta; // [rsp+20h] [rbp-99h]
  DWORD v79; // [rsp+28h] [rbp-91h]
  LONG v80; // [rsp+30h] [rbp-89h]
  __int64 v81; // [rsp+60h] [rbp-59h]
  char v82; // [rsp+70h] [rbp-49h]
  unsigned __int64 v83; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v84; // [rsp+90h] [rbp-29h]
  unsigned int v85; // [rsp+94h] [rbp-25h]
  union _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE v86[4]; // [rsp+98h] [rbp-21h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+A8h] [rbp-11h] BYREF
  DXGMONITOR *v88[12]; // [rsp+B0h] [rbp-9h] BYREF
  enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY v89; // [rsp+120h] [rbp+67h] BYREF
  PIRP Irp; // [rsp+128h] [rbp+6Fh]
  __int64 *v91; // [rsp+130h] [rbp+77h] BYREF
  ULONG pSessionId; // [rsp+138h] [rbp+7Fh] BYREF

  Irp = a2;
  v83 = 0;
  pSessionId = 0;
  IoGetRequestorSessionId(a2, &pSessionId);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = *(_QWORD *)(a1 + 64);
  SourceConnectedToTargetInClientVidPn = -1073741637;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v8 = *(int *)(v5 + 496);
  v84 = LowPart;
  if ( (_DWORD)v8 != 1 )
  {
    WdLogSingleEntry3(2, -1073741637, v8, LowPart);
    WdLogGlobalForLineNumber = 1270;
    goto LABEL_3;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v14 = *(struct _DEVICE_OBJECT **)(v5 + 32);
  Parameters = (union _LARGE_INTEGER *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
  v89 = Length;
  DeviceExtension = (char *)v14->DeviceExtension;
  UserBuffer = Irp->UserBuffer;
  v85 = Options;
  if ( LowPart > 0x232493 )
  {
    v40 = LowPart - 2303127;
    if ( !v40 )
      goto LABEL_17;
    v41 = v40 - 4;
    if ( !v41 )
      goto LABEL_17;
    v42 = v41 - 4;
    if ( !v42 )
      goto LABEL_17;
    v43 = v42 - 4;
    if ( !v43 )
      goto LABEL_17;
    v44 = v43 - 56;
    if ( !v44 )
    {
      SourceConnectedToTargetInClientVidPn = DpiBrightnessSetUncalibratedBrightness3Fallback(v14, *(_DWORD *)(v5 + 504));
      goto LABEL_3;
    }
    v45 = v44 - 4;
    if ( v45 )
    {
      v46 = v45 - 4;
      if ( v46 )
      {
        v47 = v46 - 4;
        if ( v47 )
        {
          if ( v47 != 28 )
            goto LABEL_91;
        }
      }
      if ( !(unsigned int)Feature_HdrBrightnessPolicy__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_3;
      SourceConnectedToTargetInClientVidPn = DpiAcquireCoreSyncAccessSafe(a1, 0);
      if ( SourceConnectedToTargetInClientVidPn < 0 )
        goto LABEL_3;
      v51 = *(_DWORD *)(v5 + 504);
      v52 = (void *)*((_QWORD *)DeviceExtension + 504);
      LODWORD(v91) = 0;
      Interval.LowPart = 0;
      SourceConnectedToTargetInClientVidPn = DmmGetSourceConnectedToTargetInClientVidPn(
                                               v52,
                                               v51,
                                               (unsigned int *)&Interval);
      if ( SourceConnectedToTargetInClientVidPn < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1859;
LABEL_116:
        DpiReleaseCoreSyncAccessSafe(a1, 0);
        goto LABEL_3;
      }
      SourceConnectedToTargetInClientVidPn = DmmGetCurrentWireFormatAndColorSpace(
                                               *((void **)DeviceExtension + 504),
                                               Interval.LowPart,
                                               *(_DWORD *)(v5 + 504),
                                               v86,
                                               (enum _D3DDDI_OUTPUT_WIRE_COLOR_SPACE_TYPE *)&v91);
      if ( SourceConnectedToTargetInClientVidPn < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1872;
        goto LABEL_116;
      }
      if ( (_DWORD)v91 != 12 && (_DWORD)v91 != 32 )
      {
        Information = 0;
        if ( v84 == 2303203 )
        {
          *UserBuffer = 0;
          SourceConnectedToTargetInClientVidPn = 0;
        }
        else
        {
          SourceConnectedToTargetInClientVidPn = -1073741637;
        }
        goto LABEL_102;
      }
      v53 = (DXGADAPTER *)*((_QWORD *)DeviceExtension + 504);
      if ( v53 )
      {
        v54 = *(unsigned int *)(v5 + 504);
        if ( (_DWORD)v54 != -1 )
        {
          v55 = pSessionId;
          if ( !DXGADAPTER::IsCoreResourceSharedOwner(v53) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2830;
          }
          if ( !*((_QWORD *)v53 + 406) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2831;
          }
          v56 = *(MONITOR_MGR **)(*((_QWORD *)v53 + 406) + 112LL);
          if ( v56 )
          {
            MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR((MONITOR_REF_ACCESSOR *)v86, 0);
            SourceConnectedToTargetInClientVidPn = MONITOR_MGR::_GetMonitorInstance(
                                                     v56,
                                                     v54,
                                                     1u,
                                                     (struct MONITOR_REF_ACCESSOR *)v86);
            if ( SourceConnectedToTargetInClientVidPn >= 0 )
            {
              MONITOR_REF_LOCK_ACCESSOR::MONITOR_REF_LOCK_ACCESSOR(
                (MONITOR_REF_LOCK_ACCESSOR *)v88,
                (const struct MONITOR_REF_ACCESSOR *)v86);
              SourceConnectedToTargetInClientVidPn = DXGMONITOR::_DispatchInternalIOCtrl(
                                                       v88[0],
                                                       v84,
                                                       v85,
                                                       Parameters,
                                                       v89,
                                                       UserBuffer,
                                                       &v83,
                                                       v55);
              MONITOR_REF_LOCK_ACCESSOR::~MONITOR_REF_LOCK_ACCESSOR((MONITOR_REF_LOCK_ACCESSOR *)v88);
              MONITOR_REF_ACCESSOR::Release((MONITOR_REF_ACCESSOR *)v86);
              Information = v83;
              goto LABEL_102;
            }
            WdLogSingleEntry2(7, v54);
            WdLogGlobalForLineNumber = 2859;
            MONITOR_REF_ACCESSOR::Release((MONITOR_REF_ACCESSOR *)v86);
            goto LABEL_133;
          }
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 2841;
        }
      }
      SourceConnectedToTargetInClientVidPn = -1073741811;
LABEL_133:
      Information = 0;
      goto LABEL_102;
    }
    if ( (unsigned int)Feature_I2CInterface_V2__private_IsEnabledDeviceUsageNoInline()
      && *((_DWORD *)DeviceExtension + 772) == 2 )
    {
      v57 = *((_QWORD *)DeviceExtension + 393) == 0;
    }
    else
    {
      if ( !*((_QWORD *)DeviceExtension + 392) )
        goto LABEL_3;
      v57 = *((_QWORD *)DeviceExtension + 391) == 0;
    }
    if ( v57 )
      goto LABEL_3;
    if ( !Parameters )
    {
      SourceConnectedToTargetInClientVidPn = -1073741811;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1592;
      goto LABEL_3;
    }
    if ( v85 < 0x20 )
    {
      SourceConnectedToTargetInClientVidPn = -1073741789;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1600;
      goto LABEL_3;
    }
    if ( !UserBuffer )
    {
      SourceConnectedToTargetInClientVidPn = -1073741811;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1608;
      goto LABEL_3;
    }
    if ( (unsigned int)(v89 - 1) > 0x3F )
    {
      SourceConnectedToTargetInClientVidPn = -1073741811;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1616;
      goto LABEL_3;
    }
    if ( (unsigned int)(Parameters->HighPart - 1) > 0x3F )
    {
      SourceConnectedToTargetInClientVidPn = -1073741811;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1624;
      goto LABEL_3;
    }
    SourceConnectedToTargetInClientVidPn = DpiAcquireCoreSyncAccessSafe(a1, 0);
    if ( SourceConnectedToTargetInClientVidPn < 0 )
      goto LABEL_3;
    DxgkAcquireAdapterOpmI2CSync(*((_QWORD *)DeviceExtension + 504));
    if ( v5 )
      KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v5 + 936) + 72LL), Executive, 0, 0, 0);
    DxgkAcquireAdapterDdiSync(*((_QWORD *)DeviceExtension + 504), 1);
    if ( (unsigned int)Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline()
      && bTracingEnabled
      && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    {
      McTemplateK0pxqqqq_EtwWriteTransfer(
        v59,
        v58,
        v60,
        *(_QWORD *)(v5 + 48),
        *((_QWORD *)DeviceExtension + 337),
        *(_DWORD *)(v5 + 504),
        *((_DWORD *)DeviceExtension + 772),
        223,
        0);
    }
    v61 = DeviceExtension + 3088;
    if ( (unsigned int)Feature_I2CInterface_V2__private_IsEnabledDeviceUsageNoInline() && *v61 == 2 )
    {
      v62 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD))*((_QWORD *)DeviceExtension + 393);
      HighPart = (unsigned int)Parameters->HighPart;
      v80 = Parameters[2].HighPart;
      v79 = Parameters[2].LowPart;
      Timeout = (PLARGE_INTEGER)Parameters[1].QuadPart;
      v64 = *(_QWORD *)(v5 + 48);
      v91 = (__int64 *)&Parameters[1];
      v65 = Parameters->LowPart;
      v83 = v5 + 504;
      v66 = *(unsigned int *)(v5 + 504);
      *(_QWORD *)&v86[0].0 = v5 + 48;
      v67 = v62(v64, v66, v65, HighPart, Timeout, v79, v80, v89, UserBuffer);
    }
    else
    {
      v68 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)DeviceExtension + 391);
      v69 = (unsigned int)Parameters->HighPart;
      v70 = Parameters->LowPart;
      v91 = (__int64 *)&Parameters[1];
      Timeouta = (PLARGE_INTEGER)Parameters[1].QuadPart;
      v71 = *(_QWORD *)(v5 + 48);
      v83 = v5 + 504;
      v72 = *(unsigned int *)(v5 + 504);
      *(_QWORD *)&v86[0].0 = v5 + 48;
      SourceConnectedToTargetInClientVidPn = v68(v71, v72, v70, v69, Timeouta);
      if ( SourceConnectedToTargetInClientVidPn < 0 )
      {
        v83 = v5 + 504;
        *(_QWORD *)&v86[0].0 = v5 + 48;
        v91 = (__int64 *)&Parameters[1];
LABEL_168:
        if ( (unsigned int)Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline()
          && bTracingEnabled
          && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
        {
          v82 = (char)UserBuffer;
          v81 = (__int64)UserBuffer;
          v76 = v89;
          McTemplateK0pxqqqqqqbr6br7pp_EtwWriteTransfer(
            v74,
            v73,
            v75,
            **(_QWORD **)&v86[0].0,
            *((_QWORD *)DeviceExtension + 337),
            *(_DWORD *)v83,
            *v61,
            223,
            SourceConnectedToTargetInClientVidPn,
            Parameters->HighPart,
            v89,
            *v91,
            v81,
            *v91,
            v82);
        }
        else
        {
          v76 = v89;
        }
        DxgkReleaseAdapterDdiSync(*((_QWORD *)DeviceExtension + 504));
        if ( v5 )
          KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v5 + 936) + 72LL), 0);
        DxgkReleaseAdapterOpmI2CSync(*((_QWORD *)DeviceExtension + 504));
        DpiReleaseCoreSyncAccessSafe(a1, 0);
        if ( SourceConnectedToTargetInClientVidPn >= 0 )
        {
          Information = (unsigned int)v76;
          goto LABEL_4;
        }
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1728;
        goto LABEL_3;
      }
      if ( (unsigned int)Feature_I2CInterface_AtomicTransactions__private_IsEnabledDeviceUsageNoInline() )
      {
        Interval = Parameters[3];
        SourceConnectedToTargetInClientVidPn = KeDelayExecutionThread(0, 0, &Interval);
        if ( SourceConnectedToTargetInClientVidPn < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 1693;
          goto LABEL_3;
        }
      }
      v67 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, _BYTE *))DeviceExtension
             + 392))(
              *(_QWORD *)(v5 + 48),
              *(unsigned int *)(v5 + 504),
              Parameters[2].LowPart,
              (unsigned int)Parameters[2].HighPart,
              v89,
              UserBuffer);
    }
    SourceConnectedToTargetInClientVidPn = v67;
    goto LABEL_168;
  }
  if ( LowPart == 2303123 )
  {
LABEL_17:
    v26 = DpiPdoHandleOpmIoctls(a1, Irp);
    v10 = Irp;
    SourceConnectedToTargetInClientVidPn = v26;
    Information = Irp->IoStatus.Information;
    goto LABEL_5;
  }
  v18 = LowPart - 2302983;
  if ( !v18 )
  {
    v89 = D3DKMDT_VOT_HD15;
    if ( UserBuffer )
    {
      if ( (unsigned int)Length >= 0x28 )
      {
        SourceConnectedToTargetInClientVidPn = DpiAcquireCoreSyncAccessSafe(a1, 0);
        if ( SourceConnectedToTargetInClientVidPn >= 0 )
        {
          *(_QWORD *)UserBuffer = *((_QWORD *)DeviceExtension + 504);
          *((_QWORD *)UserBuffer + 1) = *((_QWORD *)DeviceExtension + 337);
          *((_DWORD *)UserBuffer + 4) = *(_DWORD *)(v5 + 504);
          *((_DWORD *)UserBuffer + 6) = *(_DWORD *)(*(_QWORD *)(v5 + 936) + 68LL);
          UserBuffer[28] = *(_BYTE *)(*(_QWORD *)(v5 + 936) + 66LL);
          *((_DWORD *)UserBuffer + 8) = *((_DWORD *)UserBuffer + 8) & 0xFFFFFFFE
                                      | (*(_DWORD *)(*((_QWORD *)DeviceExtension + 5) + 28LL) >= 0x7006u);
          SourceConnectedToTargetInClientVidPn = DmmGetVideoOutputTechnology(
                                                   *((void *const *)DeviceExtension + 504),
                                                   *(_DWORD *)(v5 + 504),
                                                   &v89,
                                                   0);
          DpiReleaseCoreSyncAccessSafe(a1, 0);
          if ( SourceConnectedToTargetInClientVidPn >= 0 )
          {
            Information = 40;
            *((_DWORD *)UserBuffer + 5) = v89;
            SourceConnectedToTargetInClientVidPn = 0;
            goto LABEL_4;
          }
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1340;
        }
      }
      else
      {
        SourceConnectedToTargetInClientVidPn = -1073741789;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1299;
      }
    }
    else
    {
      SourceConnectedToTargetInClientVidPn = -1073741811;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1288;
    }
    goto LABEL_3;
  }
  v19 = v18 - 40;
  if ( !v19 )
  {
    if ( Parameters )
    {
      if ( Options >= 4 )
      {
        KeEnterCriticalRegion();
        if ( *(_BYTE *)(v5 + 484) )
          DpiCheckForOutstandingD3Requests(v5);
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v5 + 168), 1u);
        SourceConnectedToTargetInClientVidPn = DpiPdoSetDevicePower(a1, Parameters->LowPart, 0);
        if ( *(_BYTE *)(v5 + 484) )
          DpiEnableD3Requests(*(_QWORD *)(v5 + 24));
        ExReleaseResourceLite(*(PERESOURCE *)(v5 + 168));
        KeLeaveCriticalRegion();
      }
      else
      {
        SourceConnectedToTargetInClientVidPn = -1073741789;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1783;
      }
    }
    else
    {
      SourceConnectedToTargetInClientVidPn = -1073741811;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1772;
    }
    goto LABEL_3;
  }
  v20 = v19 - 8;
  if ( v20 )
  {
    v21 = v20 - 12;
    if ( !v21 )
    {
      if ( *((_QWORD *)DeviceExtension + 391) )
      {
        if ( Parameters )
        {
          if ( Options >= 0x10 )
          {
            if ( (unsigned int)(Parameters->HighPart - 1) > 0x3F )
            {
              SourceConnectedToTargetInClientVidPn = -1073741811;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 1391;
            }
            else
            {
              SourceConnectedToTargetInClientVidPn = DpiAcquireCoreSyncAccessSafe(a1, 0);
              if ( SourceConnectedToTargetInClientVidPn >= 0 )
              {
                DxgkAcquireAdapterOpmI2CSync(*((_QWORD *)DeviceExtension + 504));
                if ( v5 )
                  KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v5 + 936) + 72LL), Executive, 0, 0, 0);
                DxgkAcquireAdapterDdiSync(*((_QWORD *)DeviceExtension + 504), 1);
                if ( (unsigned int)Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline()
                  && bTracingEnabled
                  && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                {
                  McTemplateK0pxqqqq_EtwWriteTransfer(
                    v35,
                    v34,
                    v36,
                    *(_QWORD *)(v5 + 48),
                    *((_QWORD *)DeviceExtension + 337),
                    *(_DWORD *)(v5 + 504),
                    *((_DWORD *)DeviceExtension + 772),
                    71,
                    0);
                }
                SourceConnectedToTargetInClientVidPn = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, union _LARGE_INTEGER))DeviceExtension
                                                        + 391))(
                                                         *(_QWORD *)(v5 + 48),
                                                         *(unsigned int *)(v5 + 504),
                                                         Parameters->LowPart,
                                                         (unsigned int)Parameters->HighPart,
                                                         Parameters[1]);
                if ( (unsigned int)Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline()
                  && bTracingEnabled
                  && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                {
                  McTemplateK0pxqqqqqqbr6br7pp_EtwWriteTransfer(
                    v38,
                    v37,
                    v39,
                    *(_QWORD *)(v5 + 48),
                    *((_QWORD *)DeviceExtension + 337),
                    *(_DWORD *)(v5 + 504),
                    *((_DWORD *)DeviceExtension + 772),
                    67,
                    SourceConnectedToTargetInClientVidPn,
                    Parameters->HighPart,
                    0,
                    Parameters[1].QuadPart,
                    0,
                    Parameters[1].QuadPart,
                    0);
                }
                DxgkReleaseAdapterDdiSync(*((_QWORD *)DeviceExtension + 504));
                if ( v5 )
                  KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v5 + 936) + 72LL), 0);
                DxgkReleaseAdapterOpmI2CSync(*((_QWORD *)DeviceExtension + 504));
                DpiReleaseCoreSyncAccessSafe(a1, 0);
                if ( SourceConnectedToTargetInClientVidPn < 0 )
                {
                  WdLogSingleEntry1(3);
                  WdLogGlobalForLineNumber = 1446;
                }
              }
            }
          }
          else
          {
            SourceConnectedToTargetInClientVidPn = -1073741789;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1379;
          }
        }
        else
        {
          SourceConnectedToTargetInClientVidPn = -1073741811;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1368;
        }
      }
      goto LABEL_3;
    }
    v22 = v21 - 4;
    if ( v22 )
    {
      v23 = v22 - 60;
      if ( !v23 )
        goto LABEL_17;
      v24 = v23 - 4;
      if ( !v24 )
        goto LABEL_17;
      v25 = v24 - 4;
      if ( !v25 || v25 == 4 )
        goto LABEL_17;
LABEL_91:
      SourceConnectedToTargetInClientVidPn = DpiAcquireCoreSyncAccessSafe(a1, 0);
      if ( SourceConnectedToTargetInClientVidPn < 0 )
        goto LABEL_3;
      v48 = (DXGADAPTER *)*((_QWORD *)DeviceExtension + 504);
      if ( v48 )
      {
        v49 = *(unsigned int *)(v5 + 504);
        if ( (_DWORD)v49 != -1 )
        {
          LODWORD(v91) = pSessionId;
          if ( !DXGADAPTER::IsCoreResourceSharedOwner(v48) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2830;
          }
          if ( !*((_QWORD *)v48 + 406) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2831;
          }
          v50 = *(MONITOR_MGR **)(*((_QWORD *)v48 + 406) + 112LL);
          if ( v50 )
          {
            MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR((MONITOR_REF_ACCESSOR *)v86, 0);
            SourceConnectedToTargetInClientVidPn = MONITOR_MGR::_GetMonitorInstance(
                                                     v50,
                                                     v49,
                                                     1u,
                                                     (struct MONITOR_REF_ACCESSOR *)v86);
            if ( SourceConnectedToTargetInClientVidPn >= 0 )
            {
              MONITOR_REF_LOCK_ACCESSOR::MONITOR_REF_LOCK_ACCESSOR(
                (MONITOR_REF_LOCK_ACCESSOR *)v88,
                (const struct MONITOR_REF_ACCESSOR *)v86);
              SourceConnectedToTargetInClientVidPn = DXGMONITOR::_DispatchInternalIOCtrl(
                                                       v88[0],
                                                       v84,
                                                       v85,
                                                       Parameters,
                                                       v89,
                                                       UserBuffer,
                                                       &v83,
                                                       (unsigned int)v91);
              MONITOR_REF_LOCK_ACCESSOR::~MONITOR_REF_LOCK_ACCESSOR((MONITOR_REF_LOCK_ACCESSOR *)v88);
              Information = v83;
            }
            else
            {
              WdLogSingleEntry2(7, v49);
              Information = 0;
              WdLogGlobalForLineNumber = 2859;
            }
            MONITOR_REF_ACCESSOR::Release((MONITOR_REF_ACCESSOR *)v86);
            if ( SourceConnectedToTargetInClientVidPn == -1073741637 )
            {
              WdLogSingleEntry1(3);
              WdLogGlobalForLineNumber = 1939;
              goto LABEL_102;
            }
            if ( SourceConnectedToTargetInClientVidPn >= 0
              || SourceConnectedToTargetInClientVidPn == -1073741789
              || SourceConnectedToTargetInClientVidPn == -2147483643 )
            {
              goto LABEL_102;
            }
LABEL_101:
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 1947;
LABEL_102:
            DpiReleaseCoreSyncAccessSafe(a1, 0);
            goto LABEL_4;
          }
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 2841;
        }
      }
      Information = 0;
      SourceConnectedToTargetInClientVidPn = -1073741811;
      goto LABEL_101;
    }
    if ( *((_QWORD *)DeviceExtension + 392) )
    {
      if ( Parameters )
      {
        if ( Options >= 8 )
        {
          if ( UserBuffer )
          {
            if ( (unsigned int)(Length - 1) > 0x3F )
            {
              SourceConnectedToTargetInClientVidPn = -1073741811;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 1503;
            }
            else
            {
              SourceConnectedToTargetInClientVidPn = DpiAcquireCoreSyncAccessSafe(a1, 0);
              if ( SourceConnectedToTargetInClientVidPn >= 0 )
              {
                DxgkAcquireAdapterOpmI2CSync(*((_QWORD *)DeviceExtension + 504));
                if ( v5 )
                  KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v5 + 936) + 72LL), Executive, 0, 0, 0);
                DxgkAcquireAdapterDdiSync(*((_QWORD *)DeviceExtension + 504), 1);
                if ( (unsigned int)Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline()
                  && bTracingEnabled
                  && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                {
                  McTemplateK0pxqqqq_EtwWriteTransfer(
                    v28,
                    v27,
                    v29,
                    *(_QWORD *)(v5 + 48),
                    *((_QWORD *)DeviceExtension + 337),
                    *(_DWORD *)(v5 + 504),
                    *((_DWORD *)DeviceExtension + 772),
                    71,
                    0);
                }
                v30 = (unsigned int)v89;
                SourceConnectedToTargetInClientVidPn = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, _BYTE *))DeviceExtension
                                                        + 392))(
                                                         *(_QWORD *)(v5 + 48),
                                                         *(unsigned int *)(v5 + 504),
                                                         Parameters->LowPart,
                                                         (unsigned int)Parameters->HighPart,
                                                         v89,
                                                         UserBuffer);
                if ( (unsigned int)Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline()
                  && bTracingEnabled
                  && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                {
                  McTemplateK0pxqqqqqqbr6br7pp_EtwWriteTransfer(
                    v32,
                    v31,
                    v33,
                    *(_QWORD *)(v5 + 48),
                    *((_QWORD *)DeviceExtension + 337),
                    *(_DWORD *)(v5 + 504),
                    *((_DWORD *)DeviceExtension + 772),
                    71,
                    SourceConnectedToTargetInClientVidPn,
                    0,
                    v30,
                    0,
                    (__int64)UserBuffer,
                    0,
                    (char)UserBuffer);
                }
                DxgkReleaseAdapterDdiSync(*((_QWORD *)DeviceExtension + 504));
                if ( v5 )
                  KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v5 + 936) + 72LL), 0);
                DxgkReleaseAdapterOpmI2CSync(*((_QWORD *)DeviceExtension + 504));
                DpiReleaseCoreSyncAccessSafe(a1, 0);
                if ( SourceConnectedToTargetInClientVidPn >= 0 )
                {
                  Information = v30;
                  goto LABEL_4;
                }
                WdLogSingleEntry1(3);
                WdLogGlobalForLineNumber = 1559;
              }
            }
          }
          else
          {
            SourceConnectedToTargetInClientVidPn = -1073741811;
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1491;
          }
        }
        else
        {
          SourceConnectedToTargetInClientVidPn = -1073741789;
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1480;
        }
      }
      else
      {
        SourceConnectedToTargetInClientVidPn = -1073741811;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1469;
      }
    }
  }
LABEL_3:
  Information = 0;
LABEL_4:
  v10 = Irp;
LABEL_5:
  v10->IoStatus.Status = SourceConnectedToTargetInClientVidPn;
  v10->IoStatus.Information = Information;
  IofCompleteRequest(v10, 1);
  return (unsigned int)SourceConnectedToTargetInClientVidPn;
}

```

## disassembly

```asm
0x1403fa6d0  mov     [rsp-8+Irp], rdx
0x1403fa6d5  push    rbp
0x1403fa6d6  push    rbx
0x1403fa6d7  push    rsi
0x1403fa6d8  push    rdi
0x1403fa6d9  push    r12
0x1403fa6db  push    r13
0x1403fa6dd  push    r14
0x1403fa6df  push    r15
0x1403fa6e1  lea     rbp, [rsp-1Fh]
0x1403fa6e6  sub     rsp, 0D8h
0x1403fa6ed  xor     eax, eax
0x1403fa6ef  mov     rbx, rdx
0x1403fa6f2  mov     r15, rcx
0x1403fa6f5  mov     [rbp+57h+var_90], rax
0x1403fa6f9  mov     rcx, rbx; Irp
0x1403fa6fc  mov     [rbp+57h+var_88], rax
0x1403fa700  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x1403fa704  mov     [rbp+57h+pSessionId], eax
0x1403fa707  call    cs:__imp_IoGetRequestorSessionId
0x1403fa70e  nop     dword ptr [rax+rax+00h]
0x1403fa713  mov     r14, [rbx+0B8h]
0x1403fa71a  mov     r12, 0FFFFFFFFC00000BBh
0x1403fa721  mov     rdi, [r15+40h]
0x1403fa725  mov     ebx, r12d
0x1403fa728  mov     eax, [r14+18h]
0x1403fa72c  movsxd  rcx, dword ptr [rdi+1F0h]
0x1403fa733  mov     [rbp+57h+var_80], eax
0x1403fa736  cmp     ecx, 1
0x1403fa739  jz      short loc_1403FA784
0x1403fa73b  mov     r8, rcx
0x1403fa73e  mov     r9d, eax
0x1403fa741  mov     ecx, 2
0x1403fa746  mov     rdx, r12
0x1403fa749  call    cs:__imp_WdLogSingleEntry3
0x1403fa750  nop     dword ptr [rax+rax+00h]
0x1403fa755  mov     cs:WdLogGlobalForLineNumber, 4F6h
0x1403fa75f  mov     rdi, [rbp+57h+var_90]
0x1403fa763  mov     rcx, [rbp+57h+Irp]; Irp
0x1403fa767  mov     dl, 1; PriorityBoost
0x1403fa769  mov     [rcx+30h], ebx
0x1403fa76c  mov     [rcx+38h], rdi
0x1403fa770  call    cs:__imp_IofCompleteRequest
0x1403fa777  nop     dword ptr [rax+rax+00h]
0x1403fa77c  mov     eax, ebx
0x1403fa77e  jmp     loc_1403FB7A5
0x1403fa784  mov     ecx, [r14+8]
0x1403fa788  mov     r9d, 232493h
0x1403fa78e  mov     edx, [r14+10h]
0x1403fa792  mov     r8, [rdi+20h]
0x1403fa796  mov     r13, [rbp+57h+Irp]
0x1403fa79a  mov     r14, [r14+20h]
0x1403fa79e  mov     [rbp+57h+arg_0], ecx
0x1403fa7a1  mov     rsi, [r8+40h]
0x1403fa7a5  mov     r13, [r13+70h]
0x1403fa7a9  mov     [rbp+57h+var_7C], edx
0x1403fa7ac  cmp     eax, r9d
0x1403fa7af  ja      loc_1403FAF07
0x1403fa7b5  jz      short loc_1403FA7F6
0x1403fa7b7  sub     eax, 232407h
0x1403fa7bc  jz      loc_1403FADD5
0x1403fa7c2  sub     eax, 28h ; '('
0x1403fa7c5  jz      loc_1403FACFF
0x1403fa7cb  sub     eax, 8
0x1403fa7ce  jz      short loc_1403FA75F
0x1403fa7d0  sub     eax, 0Ch
0x1403fa7d3  jz      loc_1403FAAA1
0x1403fa7d9  sub     eax, 4
0x1403fa7dc  jz      short loc_1403FA811
0x1403fa7de  sub     eax, 3Ch ; '<'
0x1403fa7e1  jz      short loc_1403FA7F6
0x1403fa7e3  sub     eax, 4
0x1403fa7e6  jz      short loc_1403FA7F6
0x1403fa7e8  sub     eax, 4
0x1403fa7eb  jz      short loc_1403FA7F6
0x1403fa7ed  cmp     eax, 4
0x1403fa7f0  jnz     loc_1403FAF5A
0x1403fa7f6  mov     rdx, [rbp+57h+Irp]
0x1403fa7fa  mov     rcx, r15
0x1403fa7fd  call    DpiPdoHandleOpmIoctls
0x1403fa802  mov     rcx, [rbp+57h+Irp]
0x1403fa806  mov     ebx, eax
0x1403fa808  mov     rdi, [rcx+38h]
0x1403fa80c  jmp     loc_1403FA767
0x1403fa811  xor     r12d, r12d
0x1403fa814  cmp     [rsi+0C40h], r12
0x1403fa81b  jz      loc_1403FA75F
0x1403fa821  test    r14, r14
0x1403fa824  jnz     short loc_1403FA852
0x1403fa826  mov     ebx, 0C000000Dh
0x1403fa82b  mov     rdx, 0FFFFFFFFC000000Dh
0x1403fa832  lea     ecx, [r12+2]
0x1403fa837  call    cs:__imp_WdLogSingleEntry1
0x1403fa83e  nop     dword ptr [rax+rax+00h]
0x1403fa843  mov     cs:WdLogGlobalForLineNumber, 5BDh
0x1403fa84d  jmp     loc_1403FA75F
0x1403fa852  cmp     edx, 8
0x1403fa855  jnb     short loc_1403FA880
0x1403fa857  mov     rdx, 0FFFFFFFFC0000023h
0x1403fa85e  mov     ebx, edx
0x1403fa860  mov     ecx, 2
0x1403fa865  call    cs:__imp_WdLogSingleEntry1
0x1403fa86c  nop     dword ptr [rax+rax+00h]
0x1403fa871  mov     cs:WdLogGlobalForLineNumber, 5C8h
0x1403fa87b  jmp     loc_1403FA75F
0x1403fa880  test    r13, r13
0x1403fa883  jnz     short loc_1403FA8B0
0x1403fa885  mov     ebx, 0C000000Dh
0x1403fa88a  mov     rdx, 0FFFFFFFFC000000Dh
0x1403fa891  lea     ecx, [r13+2]
0x1403fa895  call    cs:__imp_WdLogSingleEntry1
0x1403fa89c  nop     dword ptr [rax+rax+00h]
0x1403fa8a1  mov     cs:WdLogGlobalForLineNumber, 5D3h
0x1403fa8ab  jmp     loc_1403FA75F
0x1403fa8b0  lea     eax, [rcx-1]
0x1403fa8b3  cmp     eax, 3Fh ; '?'
0x1403fa8b6  ja      loc_1403FAA75
0x1403fa8bc  xor     edx, edx
0x1403fa8be  mov     rcx, r15
0x1403fa8c1  call    DpiAcquireCoreSyncAccessSafe
0x1403fa8c6  mov     ebx, eax
0x1403fa8c8  test    eax, eax
0x1403fa8ca  js      loc_1403FA75F
0x1403fa8d0  mov     rcx, [rsi+0FC0h]
0x1403fa8d7  call    DxgkAcquireAdapterOpmI2CSync
0x1403fa8dc  test    rdi, rdi
0x1403fa8df  jz      short loc_1403FA905
0x1403fa8e1  mov     rcx, [rdi+3A8h]
0x1403fa8e8  xor     r9d, r9d; Alertable
0x1403fa8eb  xor     r8d, r8d; WaitMode
0x1403fa8ee  mov     [rsp+110h+Timeout], r12; Timeout
0x1403fa8f3  xor     edx, edx; WaitReason
0x1403fa8f5  mov     rcx, [rcx+48h]; Object
0x1403fa8f9  call    cs:__imp_KeWaitForSingleObject
0x1403fa900  nop     dword ptr [rax+rax+00h]
0x1403fa905  mov     rcx, [rsi+0FC0h]
0x1403fa90c  mov     edx, 1
0x1403fa911  call    DxgkAcquireAdapterDdiSync
0x1403fa916  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fa91b  test    eax, eax
0x1403fa91d  jz      short loc_1403FA967
0x1403fa91f  cmp     cs:bTracingEnabled, r12b
0x1403fa926  jz      short loc_1403FA967
0x1403fa928  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fa92f  jz      short loc_1403FA967
0x1403fa931  mov     eax, [rsi+0C10h]
0x1403fa937  mov     r9, [rdi+30h]
0x1403fa93b  mov     dword ptr [rsp+110h+var_D0], r12d
0x1403fa940  mov     [rsp+110h+var_D8], 232447h
0x1403fa948  mov     dword ptr [rsp+110h+var_E0], eax
0x1403fa94c  mov     eax, [rdi+1F8h]
0x1403fa952  mov     dword ptr [rsp+110h+var_E8], eax
0x1403fa956  mov     rax, [rsi+0A88h]
0x1403fa95d  mov     [rsp+110h+Timeout], rax
0x1403fa962  call    McTemplateK0pxqqqq_EtwWriteTransfer
0x1403fa967  mov     r12d, [rbp+57h+arg_0]
0x1403fa96b  mov     rax, [rsi+0C40h]
0x1403fa972  mov     r9d, [r14+4]
0x1403fa976  mov     r8d, [r14]
0x1403fa979  mov     edx, [rdi+1F8h]
0x1403fa97f  mov     rcx, [rdi+30h]
0x1403fa983  mov     [rsp+110h+var_E8], r13
0x1403fa988  mov     dword ptr [rsp+110h+Timeout], r12d
0x1403fa98d  call    _guard_dispatch_icall
0x1403fa992  movsxd  rbx, eax
0x1403fa995  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fa99a  xor     r14d, r14d
0x1403fa99d  test    eax, eax
0x1403fa99f  jz      short loc_1403FAA06
0x1403fa9a1  cmp     cs:bTracingEnabled, r14b
0x1403fa9a8  jz      short loc_1403FAA06
0x1403fa9aa  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fa9b1  jz      short loc_1403FAA06
0x1403fa9b3  mov     eax, [rsi+0C10h]
0x1403fa9b9  mov     r9, [rdi+30h]
0x1403fa9bd  mov     qword ptr [rsp+110h+var_A0], r13
0x1403fa9c2  mov     [rsp+110h+var_A8], r14
0x1403fa9c7  mov     [rsp+110h+var_B0], r13
0x1403fa9cc  mov     [rsp+110h+var_B8], r14
0x1403fa9d1  mov     [rsp+110h+var_C0], r12d
0x1403fa9d6  mov     [rsp+110h+var_C8], r14d
0x1403fa9db  mov     dword ptr [rsp+110h+var_D0], ebx
0x1403fa9df  mov     [rsp+110h+var_D8], 232447h
0x1403fa9e7  mov     dword ptr [rsp+110h+var_E0], eax
0x1403fa9eb  mov     eax, [rdi+1F8h]
0x1403fa9f1  mov     dword ptr [rsp+110h+var_E8], eax
0x1403fa9f5  mov     rax, [rsi+0A88h]
0x1403fa9fc  mov     [rsp+110h+Timeout], rax
0x1403faa01  call    McTemplateK0pxqqqqqqbr6br7pp_EtwWriteTransfer
0x1403faa06  mov     rcx, [rsi+0FC0h]
0x1403faa0d  call    DxgkReleaseAdapterDdiSync
0x1403faa12  test    rdi, rdi
0x1403faa15  jz      short loc_1403FAA30
0x1403faa17  mov     rcx, [rdi+3A8h]
0x1403faa1e  xor     edx, edx; Wait
0x1403faa20  mov     rcx, [rcx+48h]; Mutex
0x1403faa24  call    cs:__imp_KeReleaseMutex
0x1403faa2b  nop     dword ptr [rax+rax+00h]
0x1403faa30  mov     rcx, [rsi+0FC0h]
0x1403faa37  call    DxgkReleaseAdapterOpmI2CSync
0x1403faa3c  xor     edx, edx
0x1403faa3e  mov     rcx, r15
0x1403faa41  call    DpiReleaseCoreSyncAccessSafe
0x1403faa46  test    ebx, ebx
0x1403faa48  jns     short loc_1403FAA6D
0x1403faa4a  mov     rdx, rbx
0x1403faa4d  mov     ecx, 3
0x1403faa52  call    cs:__imp_WdLogSingleEntry1
0x1403faa59  nop     dword ptr [rax+rax+00h]
0x1403faa5e  mov     cs:WdLogGlobalForLineNumber, 617h
0x1403faa68  jmp     loc_1403FA75F
0x1403faa6d  mov     rdi, r12
0x1403faa70  jmp     loc_1403FA763
0x1403faa75  mov     ebx, 0C000000Dh
0x1403faa7a  mov     rdx, 0FFFFFFFFC000000Dh
0x1403faa81  mov     ecx, 2
0x1403faa86  call    cs:__imp_WdLogSingleEntry1
0x1403faa8d  nop     dword ptr [rax+rax+00h]
0x1403faa92  mov     cs:WdLogGlobalForLineNumber, 5DFh
0x1403faa9c  jmp     loc_1403FA75F
0x1403faaa1  xor     r12d, r12d
0x1403faaa4  cmp     [rsi+0C38h], r12
0x1403faaab  jz      loc_1403FA75F
0x1403faab1  test    r14, r14
0x1403faab4  jnz     short loc_1403FAAE2
0x1403faab6  mov     ebx, 0C000000Dh
0x1403faabb  mov     rdx, 0FFFFFFFFC000000Dh
0x1403faac2  lea     ecx, [r12+2]
0x1403faac7  call    cs:__imp_WdLogSingleEntry1
0x1403faace  nop     dword ptr [rax+rax+00h]
0x1403faad3  mov     cs:WdLogGlobalForLineNumber, 558h
0x1403faadd  jmp     loc_1403FA75F
0x1403faae2  cmp     edx, 10h
0x1403faae5  jnb     short loc_1403FAB10
0x1403faae7  mov     rdx, 0FFFFFFFFC0000023h
0x1403faaee  mov     ebx, edx
0x1403faaf0  mov     ecx, 2
0x1403faaf5  call    cs:__imp_WdLogSingleEntry1
0x1403faafc  nop     dword ptr [rax+rax+00h]
0x1403fab01  mov     cs:WdLogGlobalForLineNumber, 563h
0x1403fab0b  jmp     loc_1403FA75F
0x1403fab10  mov     eax, [r14+4]
0x1403fab14  dec     eax
0x1403fab16  cmp     eax, 3Fh ; '?'
0x1403fab19  ja      loc_1403FACD3
0x1403fab1f  xor     edx, edx
0x1403fab21  mov     rcx, r15
0x1403fab24  call    DpiAcquireCoreSyncAccessSafe
0x1403fab29  mov     ebx, eax
0x1403fab2b  test    eax, eax
0x1403fab2d  js      loc_1403FA75F
0x1403fab33  mov     rcx, [rsi+0FC0h]
0x1403fab3a  call    DxgkAcquireAdapterOpmI2CSync
0x1403fab3f  test    rdi, rdi
0x1403fab42  jz      short loc_1403FAB68
0x1403fab44  mov     rcx, [rdi+3A8h]
0x1403fab4b  xor     r9d, r9d; Alertable
0x1403fab4e  xor     r8d, r8d; WaitMode
0x1403fab51  mov     [rsp+110h+Timeout], r12; Timeout
0x1403fab56  xor     edx, edx; WaitReason
0x1403fab58  mov     rcx, [rcx+48h]; Object
0x1403fab5c  call    cs:__imp_KeWaitForSingleObject
0x1403fab63  nop     dword ptr [rax+rax+00h]
0x1403fab68  mov     rcx, [rsi+0FC0h]
0x1403fab6f  mov     edx, 1
0x1403fab74  call    DxgkAcquireAdapterDdiSync
0x1403fab79  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fab7e  test    eax, eax
0x1403fab80  jz      short loc_1403FABCA
0x1403fab82  cmp     cs:bTracingEnabled, r12b
0x1403fab89  jz      short loc_1403FABCA
0x1403fab8b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fab92  jz      short loc_1403FABCA
0x1403fab94  mov     eax, [rsi+0C10h]
0x1403fab9a  mov     r9, [rdi+30h]
0x1403fab9e  mov     dword ptr [rsp+110h+var_D0], r12d
0x1403faba3  mov     [rsp+110h+var_D8], 232447h
0x1403fabab  mov     dword ptr [rsp+110h+var_E0], eax
0x1403fabaf  mov     eax, [rdi+1F8h]
0x1403fabb5  mov     dword ptr [rsp+110h+var_E8], eax
0x1403fabb9  mov     rax, [rsi+0A88h]
0x1403fabc0  mov     [rsp+110h+Timeout], rax
0x1403fabc5  call    McTemplateK0pxqqqq_EtwWriteTransfer
0x1403fabca  mov     rcx, [r14+8]
0x1403fabce  mov     rax, [rsi+0C38h]
0x1403fabd5  mov     r9d, [r14+4]
0x1403fabd9  mov     r8d, [r14]
0x1403fabdc  mov     edx, [rdi+1F8h]
0x1403fabe2  mov     [rsp+110h+Timeout], rcx
0x1403fabe7  mov     rcx, [rdi+30h]
0x1403fabeb  call    _guard_dispatch_icall
0x1403fabf0  movsxd  rbx, eax
0x1403fabf3  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fabf8  test    eax, eax
0x1403fabfa  jz      short loc_1403FAC68
0x1403fabfc  cmp     cs:bTracingEnabled, r12b
0x1403fac03  jz      short loc_1403FAC68
0x1403fac05  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fac0c  jz      short loc_1403FAC68
0x1403fac0e  mov     rax, [r14+8]
  ... truncated ...
```
