# DpiPdoDispatchInternalIoctl

- ea: `0x1403fcc70`
- end: `0x1403fdd59`
- name: `DpiPdoDispatchInternalIoctl`
- size: `4329`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140021fe0`
- `0x140022264`
- `0x14002fe84`
- `0x140036e58`
- `0x140037128`
- `0x1400589f8`
- `0x14005c690`
- `0x140080cc0`
- `0x14008d9d0`
- `0x14008da28`
- `0x14008dae8`
- `0x1400a01e0`
- `0x14018c3fc`
- `0x14018fc68`
- `0x14018fd6c`
- `0x14018ffd8`
- `0x140191264`
- `0x1402b553c`
- `0x14033b734`
- `0x14033b9b0`
- `0x140365c64`
- `0x1403668f8`
- `0x140367514`
- `0x1403676e0`
- `0x140368514`
- `0x14038244c`
- `0x1403844d8`
- `0x1403a9970`
- `0x1403fcc70`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403fd2fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403fd2fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403fd364`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403fd364`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403fd323`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403fd323`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403fd358`
- `ntoskrnl!ExReleaseResourceLite` at `0x1403fd358`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403fdb66`
- `ntoskrnl!KeDelayExecutionThread` at `0x1403fdb66`
- `ntoskrnl!IofCompleteRequest` at `0x1403fcd10`
- `ntoskrnl!IofCompleteRequest` at `0x1403fcd10`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fce99`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fd0fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fda29`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fce99`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fd0fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403fda29`
- `ntoskrnl!KeReleaseMutex` at `0x1403fcfc4`
- `ntoskrnl!KeReleaseMutex` at `0x1403fd226`
- `ntoskrnl!KeReleaseMutex` at `0x1403fdc87`
- `ntoskrnl!KeReleaseMutex` at `0x1403fcfc4`
- `ntoskrnl!KeReleaseMutex` at `0x1403fd226`
- `ntoskrnl!KeReleaseMutex` at `0x1403fdc87`
- `ntoskrnl!IoGetRequestorSessionId` at `0x1403fcca7`
- `ntoskrnl!IoGetRequestorSessionId` at `0x1403fcca7`
- `watchdog!WdLogSingleEntry2` at `0x1403fd60c`
- `watchdog!WdLogSingleEntry2` at `0x1403fd890`
- `watchdog!WdLogSingleEntry2` at `0x1403fd60c`
- `watchdog!WdLogSingleEntry2` at `0x1403fd890`
- `watchdog!WdLogSingleEntry3` at `0x1403fcce9`
- `watchdog!WdLogSingleEntry3` at `0x1403fcce9`
- `watchdog!WdLogSingleEntry0` at `0x1403fd540`
- `watchdog!WdLogSingleEntry0` at `0x1403fd565`
- `watchdog!WdLogSingleEntry0` at `0x1403fd7ee`
- `watchdog!WdLogSingleEntry0` at `0x1403fd813`
- `watchdog!WdLogSingleEntry0` at `0x1403fd540`
- `watchdog!WdLogSingleEntry0` at `0x1403fd565`
- `watchdog!WdLogSingleEntry0` at `0x1403fd7ee`
- `watchdog!WdLogSingleEntry0` at `0x1403fd813`
- `watchdog!WdLogSingleEntry1` at `0x1403fcdd7`
- `watchdog!WdLogSingleEntry1` at `0x1403fce05`
- `watchdog!WdLogSingleEntry1` at `0x1403fce35`
- `watchdog!WdLogSingleEntry1` at `0x1403fcff2`
- `watchdog!WdLogSingleEntry1` at `0x1403fd026`
- `watchdog!WdLogSingleEntry1` at `0x1403fd067`
- `watchdog!WdLogSingleEntry1` at `0x1403fd095`
- `watchdog!WdLogSingleEntry1` at `0x1403fd258`
- `watchdog!WdLogSingleEntry1` at `0x1403fd284`
- `watchdog!WdLogSingleEntry1` at `0x1403fd2b4`
- `watchdog!WdLogSingleEntry1` at `0x1403fd2e2`
- `watchdog!WdLogSingleEntry1` at `0x1403fd391`
- `watchdog!WdLogSingleEntry1` at `0x1403fd3bf`
- `watchdog!WdLogSingleEntry1` at `0x1403fd479`
- `watchdog!WdLogSingleEntry1` at `0x1403fd591`
- `watchdog!WdLogSingleEntry1` at `0x1403fd5ba`
- `watchdog!WdLogSingleEntry1` at `0x1403fd689`
- `watchdog!WdLogSingleEntry1` at `0x1403fd722`
- `watchdog!WdLogSingleEntry1` at `0x1403fd779`
- `watchdog!WdLogSingleEntry1` at `0x1403fd83f`
- `watchdog!WdLogSingleEntry1` at `0x1403fd955`
- `watchdog!WdLogSingleEntry1` at `0x1403fd984`
- `watchdog!WdLogSingleEntry1` at `0x1403fd9b4`
- `watchdog!WdLogSingleEntry1` at `0x1403fdb81`
- `watchdog!WdLogSingleEntry1` at `0x1403fdcb5`
- `watchdog!WdLogSingleEntry1` at `0x1403fdce9`
- `watchdog!WdLogSingleEntry1` at `0x1403fdd15`
- `watchdog!WdLogSingleEntry1` at `0x1403fcdd7`
- `watchdog!WdLogSingleEntry1` at `0x1403fce05`
- `watchdog!WdLogSingleEntry1` at `0x1403fce35`
- `watchdog!WdLogSingleEntry1` at `0x1403fcff2`
- `watchdog!WdLogSingleEntry1` at `0x1403fd026`
- `watchdog!WdLogSingleEntry1` at `0x1403fd067`
- `watchdog!WdLogSingleEntry1` at `0x1403fd095`
- `watchdog!WdLogSingleEntry1` at `0x1403fd258`
- `watchdog!WdLogSingleEntry1` at `0x1403fd284`
- `watchdog!WdLogSingleEntry1` at `0x1403fd2b4`
- `watchdog!WdLogSingleEntry1` at `0x1403fd2e2`
- `watchdog!WdLogSingleEntry1` at `0x1403fd391`
- `watchdog!WdLogSingleEntry1` at `0x1403fd3bf`
- `watchdog!WdLogSingleEntry1` at `0x1403fd479`
- `watchdog!WdLogSingleEntry1` at `0x1403fd591`
- `watchdog!WdLogSingleEntry1` at `0x1403fd5ba`
- `watchdog!WdLogSingleEntry1` at `0x1403fd689`
- `watchdog!WdLogSingleEntry1` at `0x1403fd722`
- `watchdog!WdLogSingleEntry1` at `0x1403fd779`
- `watchdog!WdLogSingleEntry1` at `0x1403fd83f`
- `watchdog!WdLogSingleEntry1` at `0x1403fd955`
- `watchdog!WdLogSingleEntry1` at `0x1403fd984`
- `watchdog!WdLogSingleEntry1` at `0x1403fd9b4`
- `watchdog!WdLogSingleEntry1` at `0x1403fdb81`
- `watchdog!WdLogSingleEntry1` at `0x1403fdcb5`
- `watchdog!WdLogSingleEntry1` at `0x1403fdce9`
- `watchdog!WdLogSingleEntry1` at `0x1403fdd15`

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
          if ( !*((_QWORD *)v53 + 404) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2831;
          }
          v56 = *(MONITOR_MGR **)(*((_QWORD *)v53 + 404) + 112LL);
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
          if ( !*((_QWORD *)v48 + 404) )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2831;
          }
          v50 = *(MONITOR_MGR **)(*((_QWORD *)v48 + 404) + 112LL);
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
0x1403fcc70  mov     [rsp-8+Irp], rdx
0x1403fcc75  push    rbp
0x1403fcc76  push    rbx
0x1403fcc77  push    rsi
0x1403fcc78  push    rdi
0x1403fcc79  push    r12
0x1403fcc7b  push    r13
0x1403fcc7d  push    r14
0x1403fcc7f  push    r15
0x1403fcc81  lea     rbp, [rsp-1Fh]
0x1403fcc86  sub     rsp, 0D8h
0x1403fcc8d  xor     eax, eax
0x1403fcc8f  mov     rbx, rdx
0x1403fcc92  mov     r15, rcx
0x1403fcc95  mov     [rbp+57h+var_90], rax
0x1403fcc99  mov     rcx, rbx; Irp
0x1403fcc9c  mov     [rbp+57h+var_88], rax
0x1403fcca0  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x1403fcca4  mov     [rbp+57h+pSessionId], eax
0x1403fcca7  call    cs:__imp_IoGetRequestorSessionId
0x1403fccae  nop     dword ptr [rax+rax+00h]
0x1403fccb3  mov     r14, [rbx+0B8h]
0x1403fccba  mov     r12, 0FFFFFFFFC00000BBh
0x1403fccc1  mov     rdi, [r15+40h]
0x1403fccc5  mov     ebx, r12d
0x1403fccc8  mov     eax, [r14+18h]
0x1403fcccc  movsxd  rcx, dword ptr [rdi+1F0h]
0x1403fccd3  mov     [rbp+57h+var_80], eax
0x1403fccd6  cmp     ecx, 1
0x1403fccd9  jz      short loc_1403FCD24
0x1403fccdb  mov     r8, rcx
0x1403fccde  mov     r9d, eax
0x1403fcce1  mov     ecx, 2
0x1403fcce6  mov     rdx, r12
0x1403fcce9  call    cs:__imp_WdLogSingleEntry3
0x1403fccf0  nop     dword ptr [rax+rax+00h]
0x1403fccf5  mov     cs:WdLogGlobalForLineNumber, 4F6h
0x1403fccff  mov     rdi, [rbp+57h+var_90]
0x1403fcd03  mov     rcx, [rbp+57h+Irp]; Irp
0x1403fcd07  mov     dl, 1; PriorityBoost
0x1403fcd09  mov     [rcx+30h], ebx
0x1403fcd0c  mov     [rcx+38h], rdi
0x1403fcd10  call    cs:__imp_IofCompleteRequest
0x1403fcd17  nop     dword ptr [rax+rax+00h]
0x1403fcd1c  mov     eax, ebx
0x1403fcd1e  jmp     loc_1403FDD45
0x1403fcd24  mov     ecx, [r14+8]
0x1403fcd28  mov     r9d, 232493h
0x1403fcd2e  mov     edx, [r14+10h]
0x1403fcd32  mov     r8, [rdi+20h]
0x1403fcd36  mov     r13, [rbp+57h+Irp]
0x1403fcd3a  mov     r14, [r14+20h]
0x1403fcd3e  mov     [rbp+57h+arg_0], ecx
0x1403fcd41  mov     rsi, [r8+40h]
0x1403fcd45  mov     r13, [r13+70h]
0x1403fcd49  mov     [rbp+57h+var_7C], edx
0x1403fcd4c  cmp     eax, r9d
0x1403fcd4f  ja      loc_1403FD4A7
0x1403fcd55  jz      short loc_1403FCD96
0x1403fcd57  sub     eax, 232407h
0x1403fcd5c  jz      loc_1403FD375
0x1403fcd62  sub     eax, 28h ; '('
0x1403fcd65  jz      loc_1403FD29F
0x1403fcd6b  sub     eax, 8
0x1403fcd6e  jz      short loc_1403FCCFF
0x1403fcd70  sub     eax, 0Ch
0x1403fcd73  jz      loc_1403FD041
0x1403fcd79  sub     eax, 4
0x1403fcd7c  jz      short loc_1403FCDB1
0x1403fcd7e  sub     eax, 3Ch ; '<'
0x1403fcd81  jz      short loc_1403FCD96
0x1403fcd83  sub     eax, 4
0x1403fcd86  jz      short loc_1403FCD96
0x1403fcd88  sub     eax, 4
0x1403fcd8b  jz      short loc_1403FCD96
0x1403fcd8d  cmp     eax, 4
0x1403fcd90  jnz     loc_1403FD4FA
0x1403fcd96  mov     rdx, [rbp+57h+Irp]
0x1403fcd9a  mov     rcx, r15
0x1403fcd9d  call    DpiPdoHandleOpmIoctls
0x1403fcda2  mov     rcx, [rbp+57h+Irp]
0x1403fcda6  mov     ebx, eax
0x1403fcda8  mov     rdi, [rcx+38h]
0x1403fcdac  jmp     loc_1403FCD07
0x1403fcdb1  xor     r12d, r12d
0x1403fcdb4  cmp     [rsi+0C40h], r12
0x1403fcdbb  jz      loc_1403FCCFF
0x1403fcdc1  test    r14, r14
0x1403fcdc4  jnz     short loc_1403FCDF2
0x1403fcdc6  mov     ebx, 0C000000Dh
0x1403fcdcb  mov     rdx, 0FFFFFFFFC000000Dh
0x1403fcdd2  lea     ecx, [r12+2]
0x1403fcdd7  call    cs:__imp_WdLogSingleEntry1
0x1403fcdde  nop     dword ptr [rax+rax+00h]
0x1403fcde3  mov     cs:WdLogGlobalForLineNumber, 5BDh
0x1403fcded  jmp     loc_1403FCCFF
0x1403fcdf2  cmp     edx, 8
0x1403fcdf5  jnb     short loc_1403FCE20
0x1403fcdf7  mov     rdx, 0FFFFFFFFC0000023h
0x1403fcdfe  mov     ebx, edx
0x1403fce00  mov     ecx, 2
0x1403fce05  call    cs:__imp_WdLogSingleEntry1
0x1403fce0c  nop     dword ptr [rax+rax+00h]
0x1403fce11  mov     cs:WdLogGlobalForLineNumber, 5C8h
0x1403fce1b  jmp     loc_1403FCCFF
0x1403fce20  test    r13, r13
0x1403fce23  jnz     short loc_1403FCE50
0x1403fce25  mov     ebx, 0C000000Dh
0x1403fce2a  mov     rdx, 0FFFFFFFFC000000Dh
0x1403fce31  lea     ecx, [r13+2]
0x1403fce35  call    cs:__imp_WdLogSingleEntry1
0x1403fce3c  nop     dword ptr [rax+rax+00h]
0x1403fce41  mov     cs:WdLogGlobalForLineNumber, 5D3h
0x1403fce4b  jmp     loc_1403FCCFF
0x1403fce50  lea     eax, [rcx-1]
0x1403fce53  cmp     eax, 3Fh ; '?'
0x1403fce56  ja      loc_1403FD015
0x1403fce5c  xor     edx, edx
0x1403fce5e  mov     rcx, r15
0x1403fce61  call    DpiAcquireCoreSyncAccessSafe
0x1403fce66  mov     ebx, eax
0x1403fce68  test    eax, eax
0x1403fce6a  js      loc_1403FCCFF
0x1403fce70  mov     rcx, [rsi+0FC0h]
0x1403fce77  call    DxgkAcquireAdapterOpmI2CSync
0x1403fce7c  test    rdi, rdi
0x1403fce7f  jz      short loc_1403FCEA5
0x1403fce81  mov     rcx, [rdi+3A8h]
0x1403fce88  xor     r9d, r9d; Alertable
0x1403fce8b  xor     r8d, r8d; WaitMode
0x1403fce8e  mov     [rsp+110h+Timeout], r12; Timeout
0x1403fce93  xor     edx, edx; WaitReason
0x1403fce95  mov     rcx, [rcx+48h]; Object
0x1403fce99  call    cs:__imp_KeWaitForSingleObject
0x1403fcea0  nop     dword ptr [rax+rax+00h]
0x1403fcea5  mov     rcx, [rsi+0FC0h]
0x1403fceac  mov     edx, 1
0x1403fceb1  call    DxgkAcquireAdapterDdiSync
0x1403fceb6  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fcebb  test    eax, eax
0x1403fcebd  jz      short loc_1403FCF07
0x1403fcebf  cmp     cs:bTracingEnabled, r12b
0x1403fcec6  jz      short loc_1403FCF07
0x1403fcec8  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fcecf  jz      short loc_1403FCF07
0x1403fced1  mov     eax, [rsi+0C10h]
0x1403fced7  mov     r9, [rdi+30h]
0x1403fcedb  mov     dword ptr [rsp+110h+var_D0], r12d
0x1403fcee0  mov     [rsp+110h+var_D8], 232447h
0x1403fcee8  mov     dword ptr [rsp+110h+var_E0], eax
0x1403fceec  mov     eax, [rdi+1F8h]
0x1403fcef2  mov     dword ptr [rsp+110h+var_E8], eax
0x1403fcef6  mov     rax, [rsi+0A88h]
0x1403fcefd  mov     [rsp+110h+Timeout], rax
0x1403fcf02  call    McTemplateK0pxqqqq_EtwWriteTransfer
0x1403fcf07  mov     r12d, [rbp+57h+arg_0]
0x1403fcf0b  mov     rax, [rsi+0C40h]
0x1403fcf12  mov     r9d, [r14+4]
0x1403fcf16  mov     r8d, [r14]
0x1403fcf19  mov     edx, [rdi+1F8h]
0x1403fcf1f  mov     rcx, [rdi+30h]
0x1403fcf23  mov     [rsp+110h+var_E8], r13
0x1403fcf28  mov     dword ptr [rsp+110h+Timeout], r12d
0x1403fcf2d  call    _guard_dispatch_icall
0x1403fcf32  movsxd  rbx, eax
0x1403fcf35  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fcf3a  xor     r14d, r14d
0x1403fcf3d  test    eax, eax
0x1403fcf3f  jz      short loc_1403FCFA6
0x1403fcf41  cmp     cs:bTracingEnabled, r14b
0x1403fcf48  jz      short loc_1403FCFA6
0x1403fcf4a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fcf51  jz      short loc_1403FCFA6
0x1403fcf53  mov     eax, [rsi+0C10h]
0x1403fcf59  mov     r9, [rdi+30h]
0x1403fcf5d  mov     qword ptr [rsp+110h+var_A0], r13
0x1403fcf62  mov     [rsp+110h+var_A8], r14
0x1403fcf67  mov     [rsp+110h+var_B0], r13
0x1403fcf6c  mov     [rsp+110h+var_B8], r14
0x1403fcf71  mov     [rsp+110h+var_C0], r12d
0x1403fcf76  mov     [rsp+110h+var_C8], r14d
0x1403fcf7b  mov     dword ptr [rsp+110h+var_D0], ebx
0x1403fcf7f  mov     [rsp+110h+var_D8], 232447h
0x1403fcf87  mov     dword ptr [rsp+110h+var_E0], eax
0x1403fcf8b  mov     eax, [rdi+1F8h]
0x1403fcf91  mov     dword ptr [rsp+110h+var_E8], eax
0x1403fcf95  mov     rax, [rsi+0A88h]
0x1403fcf9c  mov     [rsp+110h+Timeout], rax
0x1403fcfa1  call    McTemplateK0pxqqqqqqbr6br7pp_EtwWriteTransfer
0x1403fcfa6  mov     rcx, [rsi+0FC0h]
0x1403fcfad  call    DxgkReleaseAdapterDdiSync
0x1403fcfb2  test    rdi, rdi
0x1403fcfb5  jz      short loc_1403FCFD0
0x1403fcfb7  mov     rcx, [rdi+3A8h]
0x1403fcfbe  xor     edx, edx; Wait
0x1403fcfc0  mov     rcx, [rcx+48h]; Mutex
0x1403fcfc4  call    cs:__imp_KeReleaseMutex
0x1403fcfcb  nop     dword ptr [rax+rax+00h]
0x1403fcfd0  mov     rcx, [rsi+0FC0h]
0x1403fcfd7  call    DxgkReleaseAdapterOpmI2CSync
0x1403fcfdc  xor     edx, edx
0x1403fcfde  mov     rcx, r15
0x1403fcfe1  call    DpiReleaseCoreSyncAccessSafe
0x1403fcfe6  test    ebx, ebx
0x1403fcfe8  jns     short loc_1403FD00D
0x1403fcfea  mov     rdx, rbx
0x1403fcfed  mov     ecx, 3
0x1403fcff2  call    cs:__imp_WdLogSingleEntry1
0x1403fcff9  nop     dword ptr [rax+rax+00h]
0x1403fcffe  mov     cs:WdLogGlobalForLineNumber, 617h
0x1403fd008  jmp     loc_1403FCCFF
0x1403fd00d  mov     rdi, r12
0x1403fd010  jmp     loc_1403FCD03
0x1403fd015  mov     ebx, 0C000000Dh
0x1403fd01a  mov     rdx, 0FFFFFFFFC000000Dh
0x1403fd021  mov     ecx, 2
0x1403fd026  call    cs:__imp_WdLogSingleEntry1
0x1403fd02d  nop     dword ptr [rax+rax+00h]
0x1403fd032  mov     cs:WdLogGlobalForLineNumber, 5DFh
0x1403fd03c  jmp     loc_1403FCCFF
0x1403fd041  xor     r12d, r12d
0x1403fd044  cmp     [rsi+0C38h], r12
0x1403fd04b  jz      loc_1403FCCFF
0x1403fd051  test    r14, r14
0x1403fd054  jnz     short loc_1403FD082
0x1403fd056  mov     ebx, 0C000000Dh
0x1403fd05b  mov     rdx, 0FFFFFFFFC000000Dh
0x1403fd062  lea     ecx, [r12+2]
0x1403fd067  call    cs:__imp_WdLogSingleEntry1
0x1403fd06e  nop     dword ptr [rax+rax+00h]
0x1403fd073  mov     cs:WdLogGlobalForLineNumber, 558h
0x1403fd07d  jmp     loc_1403FCCFF
0x1403fd082  cmp     edx, 10h
0x1403fd085  jnb     short loc_1403FD0B0
0x1403fd087  mov     rdx, 0FFFFFFFFC0000023h
0x1403fd08e  mov     ebx, edx
0x1403fd090  mov     ecx, 2
0x1403fd095  call    cs:__imp_WdLogSingleEntry1
0x1403fd09c  nop     dword ptr [rax+rax+00h]
0x1403fd0a1  mov     cs:WdLogGlobalForLineNumber, 563h
0x1403fd0ab  jmp     loc_1403FCCFF
0x1403fd0b0  mov     eax, [r14+4]
0x1403fd0b4  dec     eax
0x1403fd0b6  cmp     eax, 3Fh ; '?'
0x1403fd0b9  ja      loc_1403FD273
0x1403fd0bf  xor     edx, edx
0x1403fd0c1  mov     rcx, r15
0x1403fd0c4  call    DpiAcquireCoreSyncAccessSafe
0x1403fd0c9  mov     ebx, eax
0x1403fd0cb  test    eax, eax
0x1403fd0cd  js      loc_1403FCCFF
0x1403fd0d3  mov     rcx, [rsi+0FC0h]
0x1403fd0da  call    DxgkAcquireAdapterOpmI2CSync
0x1403fd0df  test    rdi, rdi
0x1403fd0e2  jz      short loc_1403FD108
0x1403fd0e4  mov     rcx, [rdi+3A8h]
0x1403fd0eb  xor     r9d, r9d; Alertable
0x1403fd0ee  xor     r8d, r8d; WaitMode
0x1403fd0f1  mov     [rsp+110h+Timeout], r12; Timeout
0x1403fd0f6  xor     edx, edx; WaitReason
0x1403fd0f8  mov     rcx, [rcx+48h]; Object
0x1403fd0fc  call    cs:__imp_KeWaitForSingleObject
0x1403fd103  nop     dword ptr [rax+rax+00h]
0x1403fd108  mov     rcx, [rsi+0FC0h]
0x1403fd10f  mov     edx, 1
0x1403fd114  call    DxgkAcquireAdapterDdiSync
0x1403fd119  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fd11e  test    eax, eax
0x1403fd120  jz      short loc_1403FD16A
0x1403fd122  cmp     cs:bTracingEnabled, r12b
0x1403fd129  jz      short loc_1403FD16A
0x1403fd12b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fd132  jz      short loc_1403FD16A
0x1403fd134  mov     eax, [rsi+0C10h]
0x1403fd13a  mov     r9, [rdi+30h]
0x1403fd13e  mov     dword ptr [rsp+110h+var_D0], r12d
0x1403fd143  mov     [rsp+110h+var_D8], 232447h
0x1403fd14b  mov     dword ptr [rsp+110h+var_E0], eax
0x1403fd14f  mov     eax, [rdi+1F8h]
0x1403fd155  mov     dword ptr [rsp+110h+var_E8], eax
0x1403fd159  mov     rax, [rsi+0A88h]
0x1403fd160  mov     [rsp+110h+Timeout], rax
0x1403fd165  call    McTemplateK0pxqqqq_EtwWriteTransfer
0x1403fd16a  mov     rcx, [r14+8]
0x1403fd16e  mov     rax, [rsi+0C38h]
0x1403fd175  mov     r9d, [r14+4]
0x1403fd179  mov     r8d, [r14]
0x1403fd17c  mov     edx, [rdi+1F8h]
0x1403fd182  mov     [rsp+110h+Timeout], rcx
0x1403fd187  mov     rcx, [rdi+30h]
0x1403fd18b  call    _guard_dispatch_icall
0x1403fd190  movsxd  rbx, eax
0x1403fd193  call    Feature_I2CManifestPerfLogging__private_IsEnabledDeviceUsageNoInline
0x1403fd198  test    eax, eax
0x1403fd19a  jz      short loc_1403FD208
0x1403fd19c  cmp     cs:bTracingEnabled, r12b
0x1403fd1a3  jz      short loc_1403FD208
0x1403fd1a5  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403fd1ac  jz      short loc_1403FD208
0x1403fd1ae  mov     rax, [r14+8]
  ... truncated ...
```
