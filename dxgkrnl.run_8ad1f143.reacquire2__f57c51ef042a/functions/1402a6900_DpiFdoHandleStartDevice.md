# DpiFdoHandleStartDevice

- ea: `0x1402a6900`
- end: `0x1402a72d6`
- name: `DpiFdoHandleStartDevice`
- size: `2518`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140022264`
- `0x1400406a8`
- `0x1400406ec`
- `0x14004790c`
- `0x1400554d4`
- `0x1400893d4`
- `0x14009bddc`
- `0x1400a0240`
- `0x140192114`
- `0x1402a6900`
- `0x1402b121c`
- `0x1402b19d8`
- `0x1403676e0`
- `0x1403cf9a0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a693d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a693d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a7287`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a7287`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6df3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6e63`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6e75`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a70fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6df3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6e63`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6e75`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a70fe`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6d6f`
- `ntoskrnl!ExAllocatePool2` at `0x1402a7031`
- `ntoskrnl!ExAllocatePool2` at `0x1402a6d6f`
- `ntoskrnl!ExAllocatePool2` at `0x1402a7031`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a6968`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a6968`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a727b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a727b`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402a6a61`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402a6a61`
- `ntoskrnl!PsCreateSystemThread` at `0x1402a70c5`
- `ntoskrnl!PsCreateSystemThread` at `0x1402a70c5`
- `ntoskrnl!ZwClose` at `0x1402a7117`
- `ntoskrnl!ZwClose` at `0x1402a7117`
- `ntoskrnl!KeClearEvent` at `0x1402a6b1c`
- `ntoskrnl!KeClearEvent` at `0x1402a6b1c`
- `ntoskrnl!RtlCompareMemory` at `0x1402a6cef`
- `ntoskrnl!RtlCompareMemory` at `0x1402a6cef`
- `ntoskrnl!IofCompleteRequest` at `0x1402a71a3`
- `ntoskrnl!IofCompleteRequest` at `0x1402a7200`
- `ntoskrnl!IofCompleteRequest` at `0x1402a72a0`
- `ntoskrnl!IofCompleteRequest` at `0x1402a71a3`
- `ntoskrnl!IofCompleteRequest` at `0x1402a7200`
- `ntoskrnl!IofCompleteRequest` at `0x1402a72a0`
- `ntoskrnl!KeSetEvent` at `0x1402a6f0b`
- `ntoskrnl!KeSetEvent` at `0x1402a7243`
- `ntoskrnl!KeSetEvent` at `0x1402a6f0b`
- `ntoskrnl!KeSetEvent` at `0x1402a7243`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402a7178`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402a71d5`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402a7178`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402a71d5`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1402a71b6`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1402a71b6`
- `ntoskrnl!PoSetPowerState` at `0x1402a713d`
- `ntoskrnl!PoSetPowerState` at `0x1402a713d`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1402a6c57`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1402a6c57`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402a6af5`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402a7222`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402a6af5`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402a7222`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402a6b2f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402a7256`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402a6b2f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402a7256`
- `watchdog!WdLogSingleEntry5` at `0x1402a6cab`
- `watchdog!WdLogSingleEntry5` at `0x1402a6cab`
- `watchdog!WdLogSingleEntry1` at `0x1402a6995`
- `watchdog!WdLogSingleEntry1` at `0x1402a69bb`
- `watchdog!WdLogSingleEntry1` at `0x1402a6aaf`
- `watchdog!WdLogSingleEntry1` at `0x1402a6bc9`
- `watchdog!WdLogSingleEntry1` at `0x1402a6c2f`
- `watchdog!WdLogSingleEntry1` at `0x1402a6d2a`
- `watchdog!WdLogSingleEntry1` at `0x1402a6d97`
- `watchdog!WdLogSingleEntry1` at `0x1402a6fdf`
- `watchdog!WdLogSingleEntry1` at `0x1402a7051`
- `watchdog!WdLogSingleEntry1` at `0x1402a70e0`
- `watchdog!WdLogSingleEntry1` at `0x1402a6995`
- `watchdog!WdLogSingleEntry1` at `0x1402a69bb`
- `watchdog!WdLogSingleEntry1` at `0x1402a6aaf`
- `watchdog!WdLogSingleEntry1` at `0x1402a6bc9`
- `watchdog!WdLogSingleEntry1` at `0x1402a6c2f`
- `watchdog!WdLogSingleEntry1` at `0x1402a6d2a`
- `watchdog!WdLogSingleEntry1` at `0x1402a6d97`
- `watchdog!WdLogSingleEntry1` at `0x1402a6fdf`
- `watchdog!WdLogSingleEntry1` at `0x1402a7051`
- `watchdog!WdLogSingleEntry1` at `0x1402a70e0`

## pseudocode

```c
__int64 __fastcall DpiFdoHandleStartDevice(PDEVICE_OBJECT DeviceObject, IRP *a2)
{
  int *DeviceExtension; // rdi
  char v3; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  __int64 v6; // rcx
  int v7; // esi
  NTSTATUS v8; // esi
  PIO_SECURITY_CONTEXT SecurityContext; // rdx
  __int64 v11; // r9
  struct _UNICODE_STRING *v12; // rax
  __int64 v13; // rcx
  PIRP v14; // rsi
  IO_STATUS_BLOCK *p_IoStatus; // r14
  __int64 Status; // r12
  PUNICODE_STRING v17; // rcx
  size_t v18; // r12
  void *Pool2; // rax
  int v20; // eax
  void *v21; // rcx
  int v22; // eax
  _WORD *StartContext; // r15
  bool v24; // zf
  int v25; // eax
  void *v26; // rdx
  PIRP v27; // rax
  void *v28; // rdx
  PIRP v29; // rax
  IRP *v30; // r15
  int StartRoutine; // [rsp+28h] [rbp-F0h]
  char v33; // [rsp+40h] [rbp-D8h]
  int v34; // [rsp+44h] [rbp-D4h] BYREF
  size_t Size; // [rsp+48h] [rbp-D0h] BYREF
  struct _UNICODE_STRING *v36; // [rsp+50h] [rbp-C8h] BYREF
  ULONG_PTR v37; // [rsp+58h] [rbp-C0h]
  struct _UNICODE_STRING *FileName; // [rsp+60h] [rbp-B8h]
  __int64 v39; // [rsp+70h] [rbp-A8h] BYREF
  int v40; // [rsp+78h] [rbp-A0h]
  const wchar_t *v41; // [rsp+80h] [rbp-98h]
  int *v42; // [rsp+88h] [rbp-90h]
  int v43; // [rsp+90h] [rbp-88h]
  int *v44; // [rsp+98h] [rbp-80h]
  int v45; // [rsp+A0h] [rbp-78h]
  __int64 v46; // [rsp+A8h] [rbp-70h]
  int v47; // [rsp+B0h] [rbp-68h]
  __int64 v48; // [rsp+B8h] [rbp-60h]
  __int128 v49; // [rsp+C0h] [rbp-58h]
  __int128 v50; // [rsp+D0h] [rbp-48h]
  int v51; // [rsp+120h] [rbp+8h] BYREF
  PIRP Irp; // [rsp+128h] [rbp+10h]
  void *ThreadHandle; // [rsp+130h] [rbp+18h] BYREF
  ULONG_PTR v54; // [rsp+138h] [rbp+20h] BYREF

  Irp = a2;
  DeviceExtension = (int *)DeviceObject->DeviceExtension;
  v3 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v33 = 0;
  LODWORD(Size) = 0;
  v51 = 0;
  AcquireMiniportListMutex();
  KeEnterCriticalRegion();
  if ( *((_BYTE *)DeviceExtension + 484) )
    DpiCheckForOutstandingD3Requests(DeviceExtension);
  ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
  if ( (int)WindowsQueryLicenseDWORD(v6, &v51) < 0 )
  {
    v7 = 1;
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 7288;
  }
  else
  {
    v7 = v51;
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 7275;
  }
  v34 = 1;
  v39 = 0;
  v41 = L"MultiMonSupport";
  v40 = 288;
  v43 = 67108868;
  v42 = &v34;
  v45 = 4;
  v44 = &v34;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v39, 0, 0);
  if ( !v34 )
    v7 = 0;
  if ( !v7
    && DeviceExtension[4] == 1953656900
    && DeviceExtension[5] == 2
    && !(unsigned __int8)DpiFdoIsPostDevice(DeviceObject)
    && !*((_BYTE *)DeviceExtension + 480) )
  {
    v3 = 1;
    v8 = -1071774664;
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 7335;
LABEL_40:
    if ( DeviceExtension[59] == 1 )
    {
      v20 = DeviceExtension[60];
      --DeviceExtension[69];
      DeviceExtension[59] = v20;
      DeviceExtension[60] = DeviceExtension[(DeviceExtension[69] & 7) + 61];
    }
    v21 = (void *)*((_QWORD *)DeviceExtension + 164);
    if ( v21 )
    {
      ExFreePoolWithTag(v21, 0);
      *((_QWORD *)DeviceExtension + 164) = 0;
    }
    if ( !v3 )
    {
      LOBYTE(StartRoutine) = 0;
      DxgCreateLiveDumpWithWdLogs(403, 2050, v8, DeviceExtension[59], DeviceExtension[60], StartRoutine);
    }
    v30 = Irp;
    p_IoStatus = &Irp->IoStatus;
    goto LABEL_95;
  }
  LOBYTE(ThreadHandle) = 0;
  LOBYTE(v51) = 0;
  v37 = 0;
  FileName = 0;
  if ( *((_BYTE *)DeviceExtension + 1158) )
  {
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(&dword_14015F3E8);
    if ( !dword_14015F420++ )
      KeClearEvent(&stru_14015F428);
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(&dword_14015F3E8);
    v33 = 1;
  }
  DeviceExtension[678] = v7;
  if ( *((_BYTE *)DeviceExtension + 1155) == 1 )
  {
    SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
    v54 = 0;
    v36 = 0;
    if ( SecurityContext )
    {
      FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
      v37 = (ULONG_PTR)SecurityContext;
      DpiFilterOutVgaResources(DeviceExtension, SecurityContext, &v54, 0);
      LOBYTE(v11) = 1;
      DpiFilterOutVgaResources(DeviceExtension, CurrentStackLocation->Parameters.QueryDirectory.FileName, &v36, v11);
      if ( v54 )
      {
        v12 = v36;
        if ( v36 )
        {
          CurrentStackLocation->Parameters.WMI.ProviderId = v54;
          CurrentStackLocation->Parameters.QueryDirectory.FileName = v12;
          LOBYTE(ThreadHandle) = 1;
        }
      }
    }
    else
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 7403;
    }
  }
  if ( !(unsigned __int8)DpiFdoIsPostDevice(DeviceObject) && DeviceExtension[4] == 1953656900 && DeviceExtension[5] == 2 )
  {
    LODWORD(v54) = 0;
    if ( (int)DpiReadPnpRegistryValue(v13, L"DisableNonPOSTDevice", &v54, 4, 2) >= 0 )
    {
      if ( (_DWORD)v54 )
      {
        v8 = -1073741823;
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 7452;
        goto LABEL_40;
      }
    }
    else
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 7439;
    }
  }
  v14 = Irp;
  IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)DeviceExtension + 20), Irp);
  p_IoStatus = &v14->IoStatus;
  Status = v14->IoStatus.Status;
  v8 = Status;
  if ( (int)Status < 0 )
  {
    WdLogSingleEntry5(
      2,
      (unsigned int)DeviceExtension[136],
      Status,
      (unsigned int)DeviceExtension[281],
      (unsigned int)DeviceExtension[282],
      *(_QWORD *)(*((_QWORD *)DeviceExtension + 5) + 152LL));
    WdLogGlobalForLineNumber = 7477;
    if ( (_DWORD)Status == -1073741810
      && *(_BYTE *)(*((_QWORD *)DeviceExtension + 5) + 134LL)
      && RtlCompareMemory(DeviceExtension + 136, &GUID_BUS_TYPE_USB, 0x10u) == 16 )
    {
      v3 = 1;
      goto LABEL_40;
    }
LABEL_39:
    v3 = v51;
    goto LABEL_40;
  }
  v17 = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  v3 = 0;
  if ( v17 )
  {
    DpiDetermineResourceListSize(v17, &Size);
    v18 = (unsigned int)Size;
    Pool2 = (void *)ExAllocatePool2(256, (unsigned int)Size, 1953656900);
    *((_QWORD *)DeviceExtension + 164) = Pool2;
    if ( !Pool2 )
    {
      v8 = -1073741801;
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 7523;
      goto LABEL_39;
    }
    memmove(Pool2, CurrentStackLocation->Parameters.QueryDirectory.FileName, v18);
    if ( (_BYTE)ThreadHandle == 1 )
    {
      ExFreePoolWithTag(CurrentStackLocation->Parameters.Create.SecurityContext, 0);
      ExFreePoolWithTag(CurrentStackLocation->Parameters.QueryDirectory.FileName, 0);
      CurrentStackLocation->Parameters.WMI.ProviderId = v37;
      CurrentStackLocation->Parameters.QueryDirectory.FileName = FileName;
    }
    v3 = 0;
  }
  DeviceExtension[(DeviceExtension[69] & 7) + 61] = DeviceExtension[60];
  v22 = DeviceExtension[59];
  ++DeviceExtension[69];
  DeviceExtension[60] = v22;
  DeviceExtension[59] = 1;
  if ( DeviceExtension[4] != 1953656900 || DeviceExtension[5] != 2 )
  {
LABEL_54:
    if ( !(_BYTE)word_14015EE20 )
      goto LABEL_57;
    goto LABEL_55;
  }
  if ( !*((_BYTE *)DeviceExtension + 2717) )
  {
    HIBYTE(word_14015EE20) = 1;
    goto LABEL_54;
  }
  LOBYTE(word_14015EE20) = 1;
LABEL_55:
  if ( HIBYTE(word_14015EE20) )
    KeSetEvent(&stru_14015EE28, 0, 0);
LABEL_57:
  LOBYTE(ThreadHandle) = 0;
  LOBYTE(v54) = 0;
  if ( !*((_BYTE *)DeviceExtension + 2716)
    && (int)DpiFdoIsMdmDeviceAndOwnsMux(DeviceObject, &ThreadHandle, &v54) >= 0
    && (_BYTE)ThreadHandle )
  {
    if ( !(_BYTE)v54 )
      goto LABEL_71;
    goto LABEL_67;
  }
  if ( !qword_14015F128 )
  {
    if ( DeviceExtension[4] == 1953656900 && DeviceExtension[5] == 2 )
    {
      if ( (unsigned __int8)DpiFdoIsPostDevice(DeviceObject) || *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL) )
LABEL_67:
        qword_14015F128 = (__int64)DeviceObject;
    }
    else if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL) && *((_QWORD *)DeviceExtension + 354) )
    {
      qword_14015F128 = *((_QWORD *)DeviceExtension + 354);
    }
  }
LABEL_71:
  if ( !*((_BYTE *)DeviceExtension + 480)
    && *((_BYTE *)DeviceExtension + 1153)
    && !(unsigned __int8)DpiFdoIsMsBddAnchoredDevice(DeviceObject) )
  {
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 7654;
    v3 = 1;
    v8 = -1071774664;
    goto LABEL_40;
  }
  if ( byte_14015EE22 && !*((_BYTE *)DeviceExtension + 1158) )
  {
    ThreadHandle = 0;
    StartContext = (_WORD *)ExAllocatePool2(256, 1552, 1953656900);
    if ( !StartContext )
    {
      v8 = -1073741801;
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 7698;
      goto LABEL_39;
    }
    if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL)
      || (v24 = (unsigned __int8)DpiFdoIsMsBddAnchoredDevice(DeviceObject) == 0, v25 = 0, !v24) )
    {
      v25 = 2;
    }
    *(_DWORD *)StartContext = v25;
    StartContext[2] = 0;
    *((_DWORD *)StartContext + 131) = 0;
    v8 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, DpiFdoStartAdapterThread, StartContext);
    if ( v8 < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 7729;
      ExFreePoolWithTag(StartContext, 0x74727044u);
      goto LABEL_39;
    }
    ZwClose(ThreadHandle);
  }
  DeviceExtension[71] = 1;
  DeviceExtension[70] = 1;
  PoSetPowerState(DeviceObject, DevicePowerState, (POWER_STATE)1);
  if ( v8 < 0 )
    goto LABEL_40;
  if ( DeviceExtension[4] == 1953656900 && DeviceExtension[5] == 2 )
  {
    v26 = (void *)*((_QWORD *)DeviceExtension + 686);
    if ( v26 )
    {
      v27 = IoCsqRemoveNextIrp((PIO_CSQ)(DeviceExtension + 1350), v26);
      *((_QWORD *)DeviceExtension + 686) = 0;
      if ( v27 )
      {
        *((_BYTE *)DeviceExtension + 5516) = 1;
        v27->IoStatus.Status = 0;
        v27->IoStatus.Information = 0;
        IofCompleteRequest(v27, 0);
        IoInvalidateDeviceState(*((PDEVICE_OBJECT *)DeviceExtension + 19));
      }
    }
    v28 = (void *)*((_QWORD *)DeviceExtension + 690);
    if ( v28 )
    {
      v29 = IoCsqRemoveNextIrp((PIO_CSQ)(DeviceExtension + 1350), v28);
      *((_QWORD *)DeviceExtension + 690) = 0;
      if ( v29 )
      {
        *((_BYTE *)DeviceExtension + 5548) = 1;
        v29->IoStatus.Status = 0;
        v29->IoStatus.Information = 0;
        IofCompleteRequest(v29, 0);
      }
    }
  }
  v30 = Irp;
LABEL_95:
  if ( v33 )
  {
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(&dword_14015F3E8);
    if ( !--dword_14015F420 )
      KeSetEvent(&stru_14015F428, 0, 0);
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(&dword_14015F3E8);
  }
  if ( *((_BYTE *)DeviceExtension + 484) )
    DpiEnableD3Requests(*((_QWORD *)DeviceExtension + 3));
  ExReleaseResourceLite(*((PERESOURCE *)DeviceExtension + 21));
  KeLeaveCriticalRegion();
  ReleaseMiniportListMutex();
  p_IoStatus->Status = v8;
  IofCompleteRequest(v30, 1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1402a6900  mov     rax, rsp
0x1402a6903  mov     [rax+10h], rdx
0x1402a6907  push    rbx
0x1402a6908  push    rsi
0x1402a6909  push    rdi
0x1402a690a  push    r12
0x1402a690c  push    r13
0x1402a690e  push    r14
0x1402a6910  push    r15
0x1402a6912  sub     rsp, 0E0h
0x1402a6919  mov     rdi, [rcx+40h]
0x1402a691d  xor     r12d, r12d
0x1402a6920  mov     r15, [rdx+0B8h]
0x1402a6927  mov     r13, rcx
0x1402a692a  mov     [rsp+118h+var_D8], r12b
0x1402a692f  mov     dword ptr [rsp+118h+Size], r12d
0x1402a6934  mov     [rax+8], r12d
0x1402a6938  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402a693d  call    cs:__imp_KeEnterCriticalRegion
0x1402a6944  nop     dword ptr [rax+rax+00h]
0x1402a6949  cmp     [rdi+1E4h], r12b
0x1402a6950  jz      short loc_1402A695A
0x1402a6952  mov     rcx, rdi
0x1402a6955  call    DpiCheckForOutstandingD3Requests
0x1402a695a  mov     rcx, [rdi+0A8h]; Resource
0x1402a6961  mov     ebx, 1
0x1402a6966  mov     dl, bl; Wait
0x1402a6968  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402a696f  nop     dword ptr [rax+rax+00h]
0x1402a6974  lea     rdx, [rsp+118h+arg_0]
0x1402a697c  call    WindowsQueryLicenseDWORD
0x1402a6981  test    eax, eax
0x1402a6983  js      short loc_1402A69AD
0x1402a6985  mov     esi, [rsp+118h+arg_0]
0x1402a698c  lea     r14d, [rbx+3]
0x1402a6990  mov     edx, esi
0x1402a6992  mov     ecx, r14d
0x1402a6995  call    cs:__imp_WdLogSingleEntry1
0x1402a699c  nop     dword ptr [rax+rax+00h]
0x1402a69a1  mov     cs:WdLogGlobalForLineNumber, 1C6Bh
0x1402a69ab  jmp     short loc_1402A69D1
0x1402a69ad  mov     esi, ebx
0x1402a69af  mov     r14d, 4
0x1402a69b5  movsxd  rdx, eax
0x1402a69b8  mov     ecx, r14d
0x1402a69bb  call    cs:__imp_WdLogSingleEntry1
0x1402a69c2  nop     dword ptr [rax+rax+00h]
0x1402a69c7  mov     cs:WdLogGlobalForLineNumber, 1C78h
0x1402a69d1  xorps   xmm0, xmm0
0x1402a69d4  mov     [rsp+118h+var_D4], ebx
0x1402a69d8  lea     rax, aMultimonsuppor; "MultiMonSupport"
0x1402a69df  mov     [rsp+118h+var_A8], r12
0x1402a69e4  mov     [rsp+118h+var_98], rax
0x1402a69ec  lea     r8, [rsp+118h+var_A8]
0x1402a69f1  xor     r9d, r9d
0x1402a69f4  mov     [rsp+118h+var_A0], 120h
0x1402a69fc  lea     rax, [rsp+118h+var_D4]
0x1402a6a01  mov     [rsp+118h+var_88], 4000004h
0x1402a6a0c  mov     [rsp+118h+var_90], rax
0x1402a6a14  lea     rdx, Path; "GraphicsDrivers"
0x1402a6a1b  lea     rax, [rsp+118h+var_D4]
0x1402a6a20  mov     [rsp+118h+var_78], r14d
0x1402a6a28  lea     ecx, [r9+2]
0x1402a6a2c  mov     [rsp+118h+var_80], rax
0x1402a6a34  mov     [rsp+118h+var_70], r12
0x1402a6a3c  mov     [rsp+118h+var_68], r12d
0x1402a6a44  mov     [rsp+118h+var_60], r12
0x1402a6a4c  movups  [rsp+118h+var_58], xmm0
0x1402a6a54  mov     [rsp+118h+ClientId], r12
0x1402a6a59  movups  [rsp+118h+var_48], xmm0
0x1402a6a61  call    cs:__imp_RtlQueryRegistryValuesEx
0x1402a6a68  nop     dword ptr [rax+rax+00h]
0x1402a6a6d  cmp     [rsp+118h+var_D4], r12d
0x1402a6a72  cmovz   esi, r12d
0x1402a6a76  test    esi, esi
0x1402a6a78  jnz     short loc_1402A6ACA
0x1402a6a7a  cmp     dword ptr [rdi+10h], 74727044h
0x1402a6a81  jnz     short loc_1402A6ACA
0x1402a6a83  cmp     dword ptr [rdi+14h], 2
0x1402a6a87  jnz     short loc_1402A6ACA
0x1402a6a89  mov     rcx, r13
0x1402a6a8c  call    DpiFdoIsPostDevice
0x1402a6a91  test    al, al
0x1402a6a93  jnz     short loc_1402A6ACA
0x1402a6a95  cmp     [rdi+1E0h], r12b
0x1402a6a9c  jnz     short loc_1402A6ACA
0x1402a6a9e  mov     r12b, bl
0x1402a6aa1  mov     esi, 0C01E0438h
0x1402a6aa6  mov     rdx, [rdi+18h]
0x1402a6aaa  mov     ecx, 3
0x1402a6aaf  call    cs:__imp_WdLogSingleEntry1
0x1402a6ab6  nop     dword ptr [rax+rax+00h]
0x1402a6abb  mov     cs:WdLogGlobalForLineNumber, 1CA7h
0x1402a6ac5  jmp     loc_1402A6DB5
0x1402a6aca  xor     eax, eax
0x1402a6acc  mov     byte ptr [rsp+118h+ThreadHandle], r12b
0x1402a6ad4  mov     byte ptr [rsp+118h+arg_0], r12b
0x1402a6adc  mov     [rsp+118h+var_C0], rax
0x1402a6ae1  mov     [rsp+118h+var_B8], rax
0x1402a6ae6  cmp     [rdi+486h], al
0x1402a6aec  jz      short loc_1402A6B3F
0x1402a6aee  lea     rcx, dword_14015F3E8
0x1402a6af5  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1402a6afc  nop     dword ptr [rax+rax+00h]
0x1402a6b01  mov     eax, cs:dword_14015F420
0x1402a6b07  mov     ecx, eax
0x1402a6b09  add     eax, ebx
0x1402a6b0b  mov     cs:dword_14015F420, eax
0x1402a6b11  test    ecx, ecx
0x1402a6b13  jnz     short loc_1402A6B28
0x1402a6b15  lea     rcx, stru_14015F428; Event
0x1402a6b1c  call    cs:__imp_KeClearEvent
0x1402a6b23  nop     dword ptr [rax+rax+00h]
0x1402a6b28  lea     rcx, dword_14015F3E8
0x1402a6b2f  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1402a6b36  nop     dword ptr [rax+rax+00h]
0x1402a6b3b  mov     [rsp+118h+var_D8], bl
0x1402a6b3f  mov     [rdi+0A98h], esi
0x1402a6b45  cmp     [rdi+483h], bl
0x1402a6b4b  jnz     loc_1402A6BDF
0x1402a6b51  mov     rdx, [r15+8]
0x1402a6b55  mov     [rsp+118h+arg_18], r12
0x1402a6b5d  mov     [rsp+118h+var_C8], r12
0x1402a6b62  test    rdx, rdx
0x1402a6b65  jz      short loc_1402A6BC4
0x1402a6b67  mov     rax, [r15+10h]
0x1402a6b6b  lea     r8, [rsp+118h+arg_18]
0x1402a6b73  xor     r9d, r9d
0x1402a6b76  mov     [rsp+118h+var_B8], rax
0x1402a6b7b  mov     rcx, rdi
0x1402a6b7e  mov     [rsp+118h+var_C0], rdx
0x1402a6b83  call    DpiFilterOutVgaResources
0x1402a6b88  mov     rdx, [r15+10h]
0x1402a6b8c  lea     r8, [rsp+118h+var_C8]
0x1402a6b91  mov     r9b, bl
0x1402a6b94  mov     rcx, rdi
0x1402a6b97  call    DpiFilterOutVgaResources
0x1402a6b9c  mov     rcx, [rsp+118h+arg_18]
0x1402a6ba4  test    rcx, rcx
0x1402a6ba7  jz      short loc_1402A6BDF
0x1402a6ba9  mov     rax, [rsp+118h+var_C8]
0x1402a6bae  test    rax, rax
0x1402a6bb1  jz      short loc_1402A6BDF
0x1402a6bb3  mov     [r15+8], rcx
0x1402a6bb7  mov     [r15+10h], rax
0x1402a6bbb  mov     byte ptr [rsp+118h+ThreadHandle], bl
0x1402a6bc2  jmp     short loc_1402A6BDF
0x1402a6bc4  mov     ecx, 2
0x1402a6bc9  call    cs:__imp_WdLogSingleEntry1
0x1402a6bd0  nop     dword ptr [rax+rax+00h]
0x1402a6bd5  mov     cs:WdLogGlobalForLineNumber, 1CEBh
0x1402a6bdf  mov     rcx, r13
0x1402a6be2  call    DpiFdoIsPostDevice
0x1402a6be7  test    al, al
0x1402a6be9  jnz     short loc_1402A6C45
0x1402a6beb  cmp     dword ptr [rdi+10h], 74727044h
0x1402a6bf2  jnz     short loc_1402A6C45
0x1402a6bf4  cmp     dword ptr [rdi+14h], 2
0x1402a6bf8  jnz     short loc_1402A6C45
0x1402a6bfa  mov     r9d, r14d
0x1402a6bfd  mov     dword ptr [rsp+118h+arg_18], r12d
0x1402a6c05  lea     r8, [rsp+118h+arg_18]
0x1402a6c0d  mov     dword ptr [rsp+118h+ClientId], 2
0x1402a6c15  lea     rdx, aDisablenonpost; "DisableNonPOSTDevice"
0x1402a6c1c  call    DpiReadPnpRegistryValue
0x1402a6c21  test    eax, eax
0x1402a6c23  jns     loc_1402A6D0D
0x1402a6c29  movsxd  rdx, eax
0x1402a6c2c  mov     ecx, r14d
0x1402a6c2f  call    cs:__imp_WdLogSingleEntry1
0x1402a6c36  nop     dword ptr [rax+rax+00h]
0x1402a6c3b  mov     cs:WdLogGlobalForLineNumber, 1D0Fh
0x1402a6c45  mov     rsi, [rsp+118h+Irp]
0x1402a6c4d  mov     rcx, [rdi+0A0h]; DeviceObject
0x1402a6c54  mov     rdx, rsi; Irp
0x1402a6c57  call    cs:__imp_IoForwardIrpSynchronously
0x1402a6c5e  nop     dword ptr [rax+rax+00h]
0x1402a6c63  lea     r14, [rsi+30h]
0x1402a6c67  movsxd  r12, dword ptr [r14]
0x1402a6c6a  mov     esi, r12d
0x1402a6c6d  test    r12d, r12d
0x1402a6c70  jns     loc_1402A6D42
0x1402a6c76  mov     rax, [rdi+28h]
0x1402a6c7a  lea     r14, [rdi+220h]
0x1402a6c81  mov     r10d, [rdi+468h]
0x1402a6c88  mov     r8, r12
0x1402a6c8b  mov     r9d, [rdi+464h]
0x1402a6c92  mov     ecx, 2
0x1402a6c97  mov     edx, [r14]
0x1402a6c9a  mov     rax, [rax+98h]
0x1402a6ca1  mov     [rsp+118h+StartRoutine], rax
0x1402a6ca6  mov     [rsp+118h+ClientId], r10
0x1402a6cab  call    cs:__imp_WdLogSingleEntry5
0x1402a6cb2  nop     dword ptr [rax+rax+00h]
0x1402a6cb7  mov     cs:WdLogGlobalForLineNumber, 1D35h
0x1402a6cc1  cmp     r12d, 0C000000Eh
0x1402a6cc8  jnz     loc_1402A6DAD
0x1402a6cce  mov     rax, [rdi+28h]
0x1402a6cd2  cmp     byte ptr [rax+86h], 0
0x1402a6cd9  jz      loc_1402A6DAD
0x1402a6cdf  mov     r8d, 10h; Length
0x1402a6ce5  lea     rdx, GUID_BUS_TYPE_USB; Source2
0x1402a6cec  mov     rcx, r14; Source1
0x1402a6cef  call    cs:__imp_RtlCompareMemory
0x1402a6cf6  nop     dword ptr [rax+rax+00h]
0x1402a6cfb  cmp     rax, 10h
0x1402a6cff  jnz     loc_1402A6DAD
0x1402a6d05  mov     r12b, bl
0x1402a6d08  jmp     loc_1402A6DB5
0x1402a6d0d  cmp     dword ptr [rsp+118h+arg_18], r12d
0x1402a6d15  jz      loc_1402A6C45
0x1402a6d1b  mov     rsi, 0FFFFFFFFC0000001h
0x1402a6d22  mov     rdx, rsi
0x1402a6d25  mov     ecx, 2
0x1402a6d2a  call    cs:__imp_WdLogSingleEntry1
0x1402a6d31  nop     dword ptr [rax+rax+00h]
0x1402a6d36  mov     cs:WdLogGlobalForLineNumber, 1D1Ch
0x1402a6d40  jmp     short loc_1402A6DB5
0x1402a6d42  mov     rcx, [r15+10h]
0x1402a6d46  xor     r12d, r12d
0x1402a6d49  test    rcx, rcx
0x1402a6d4c  jz      loc_1402A6E96
0x1402a6d52  lea     rdx, [rsp+118h+Size]
0x1402a6d57  call    DpiDetermineResourceListSize
0x1402a6d5c  mov     r12d, dword ptr [rsp+118h+Size]
0x1402a6d61  mov     r8d, 74727044h
0x1402a6d67  mov     edx, r12d
0x1402a6d6a  mov     ecx, 100h
0x1402a6d6f  call    cs:__imp_ExAllocatePool2
0x1402a6d76  nop     dword ptr [rax+rax+00h]
0x1402a6d7b  mov     [rdi+520h], rax
0x1402a6d82  test    rax, rax
0x1402a6d85  jnz     loc_1402A6E45
0x1402a6d8b  mov     rdx, 0FFFFFFFFC0000017h
0x1402a6d92  mov     esi, edx
0x1402a6d94  lea     ecx, [rax+6]
0x1402a6d97  call    cs:__imp_WdLogSingleEntry1
0x1402a6d9e  nop     dword ptr [rax+rax+00h]
0x1402a6da3  mov     cs:WdLogGlobalForLineNumber, 1D63h
0x1402a6dad  mov     r12b, byte ptr [rsp+118h+arg_0]
0x1402a6db5  cmp     [rdi+0ECh], ebx
0x1402a6dbb  jnz     short loc_1402A6DE5
0x1402a6dbd  mov     eax, [rdi+0F0h]
0x1402a6dc3  dec     dword ptr [rdi+114h]
0x1402a6dc9  mov     [rdi+0ECh], eax
0x1402a6dcf  mov     eax, [rdi+114h]
0x1402a6dd5  and     eax, 7
0x1402a6dd8  mov     eax, [rdi+rax*4+0F4h]
0x1402a6ddf  mov     [rdi+0F0h], eax
0x1402a6de5  mov     rcx, [rdi+520h]; P
0x1402a6dec  test    rcx, rcx
0x1402a6def  jz      short loc_1402A6E0A
0x1402a6df1  xor     edx, edx; Tag
0x1402a6df3  call    cs:__imp_ExFreePoolWithTag
0x1402a6dfa  nop     dword ptr [rax+rax+00h]
0x1402a6dff  mov     qword ptr [rdi+520h], 0
0x1402a6e0a  test    r12b, r12b
0x1402a6e0d  jnz     loc_1402A72C2
0x1402a6e13  movsxd  rcx, dword ptr [rdi+0F0h]
0x1402a6e1a  xor     r12d, r12d
0x1402a6e1d  movsxd  r9, dword ptr [rdi+0ECh]
0x1402a6e24  mov     edx, 802h
0x1402a6e29  mov     byte ptr [rsp+118h+StartRoutine], r12b
0x1402a6e2e  mov     [rsp+118h+ClientId], rcx
0x1402a6e33  mov     ecx, 193h
0x1402a6e38  movsxd  r8, esi
0x1402a6e3b  call    ?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x1402a6e40  jmp     loc_1402A72C5
0x1402a6e45  mov     rdx, [r15+10h]; Src
0x1402a6e49  mov     r8, r12; Size
0x1402a6e4c  mov     rcx, rax; void *
0x1402a6e4f  call    memmove
0x1402a6e54  cmp     byte ptr [rsp+118h+ThreadHandle], bl
0x1402a6e5b  jnz     short loc_1402A6E93
0x1402a6e5d  mov     rcx, [r15+8]; P
0x1402a6e61  xor     edx, edx; Tag
0x1402a6e63  call    cs:__imp_ExFreePoolWithTag
0x1402a6e6a  nop     dword ptr [rax+rax+00h]
0x1402a6e6f  mov     rcx, [r15+10h]; P
0x1402a6e73  xor     edx, edx; Tag
0x1402a6e75  call    cs:__imp_ExFreePoolWithTag
0x1402a6e7c  nop     dword ptr [rax+rax+00h]
0x1402a6e81  mov     rax, [rsp+118h+var_C0]
0x1402a6e86  mov     [r15+8], rax
0x1402a6e8a  mov     rax, [rsp+118h+var_B8]
0x1402a6e8f  mov     [r15+10h], rax
0x1402a6e93  xor     r12d, r12d
0x1402a6e96  mov     ecx, [rdi+114h]
0x1402a6e9c  mov     r15d, 74727044h
0x1402a6ea2  mov     eax, [rdi+0F0h]
0x1402a6ea8  and     ecx, 7
0x1402a6eab  mov     [rdi+rcx*4+0F4h], eax
0x1402a6eb2  mov     eax, [rdi+0ECh]
0x1402a6eb8  add     [rdi+114h], ebx
0x1402a6ebe  mov     [rdi+0F0h], eax
0x1402a6ec4  mov     [rdi+0ECh], ebx
0x1402a6eca  cmp     [rdi+10h], r15d
0x1402a6ece  jnz     short loc_1402A6EED
0x1402a6ed0  cmp     dword ptr [rdi+14h], 2
0x1402a6ed4  jnz     short loc_1402A6EED
  ... truncated ...
```
