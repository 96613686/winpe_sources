# DpiFdoHandleStartDevice

- ea: `0x1402ad2b0`
- end: `0x1402adc86`
- name: `DpiFdoHandleStartDevice`
- size: `2518`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140022434`
- `0x140040908`
- `0x14004094c`
- `0x140047b0c`
- `0x140055744`
- `0x140089d94`
- `0x14009c8ac`
- `0x1400a0d00`
- `0x140196118`
- `0x1402ad2b0`
- `0x1402b7bcc`
- `0x1402b8388`
- `0x140367720`
- `0x1403cfdc0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402ad2ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402ad2ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402adc37`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402adc37`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad7a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad813`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad825`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402adaae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad7a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad813`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad825`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402adaae`
- `ntoskrnl!ExAllocatePool2` at `0x1402ad71f`
- `ntoskrnl!ExAllocatePool2` at `0x1402ad9e1`
- `ntoskrnl!ExAllocatePool2` at `0x1402ad71f`
- `ntoskrnl!ExAllocatePool2` at `0x1402ad9e1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402ad318`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402ad318`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402adc2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402adc2b`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402ad411`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402ad411`
- `ntoskrnl!PsCreateSystemThread` at `0x1402ada75`
- `ntoskrnl!PsCreateSystemThread` at `0x1402ada75`
- `ntoskrnl!ZwClose` at `0x1402adac7`
- `ntoskrnl!ZwClose` at `0x1402adac7`
- `ntoskrnl!KeClearEvent` at `0x1402ad4cc`
- `ntoskrnl!KeClearEvent` at `0x1402ad4cc`
- `ntoskrnl!RtlCompareMemory` at `0x1402ad69f`
- `ntoskrnl!RtlCompareMemory` at `0x1402ad69f`
- `ntoskrnl!IofCompleteRequest` at `0x1402adb53`
- `ntoskrnl!IofCompleteRequest` at `0x1402adbb0`
- `ntoskrnl!IofCompleteRequest` at `0x1402adc50`
- `ntoskrnl!IofCompleteRequest` at `0x1402adb53`
- `ntoskrnl!IofCompleteRequest` at `0x1402adbb0`
- `ntoskrnl!IofCompleteRequest` at `0x1402adc50`
- `ntoskrnl!KeSetEvent` at `0x1402ad8bb`
- `ntoskrnl!KeSetEvent` at `0x1402adbf3`
- `ntoskrnl!KeSetEvent` at `0x1402ad8bb`
- `ntoskrnl!KeSetEvent` at `0x1402adbf3`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402adb28`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402adb85`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402adb28`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1402adb85`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1402adb66`
- `ntoskrnl!IoInvalidateDeviceState` at `0x1402adb66`
- `ntoskrnl!PoSetPowerState` at `0x1402adaed`
- `ntoskrnl!PoSetPowerState` at `0x1402adaed`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1402ad607`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1402ad607`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402ad4a5`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402adbd2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402ad4a5`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402adbd2`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402ad4df`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402adc06`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402ad4df`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402adc06`
- `watchdog!WdLogSingleEntry5` at `0x1402ad65b`
- `watchdog!WdLogSingleEntry5` at `0x1402ad65b`
- `watchdog!WdLogSingleEntry1` at `0x1402ad345`
- `watchdog!WdLogSingleEntry1` at `0x1402ad36b`
- `watchdog!WdLogSingleEntry1` at `0x1402ad45f`
- `watchdog!WdLogSingleEntry1` at `0x1402ad579`
- `watchdog!WdLogSingleEntry1` at `0x1402ad5df`
- `watchdog!WdLogSingleEntry1` at `0x1402ad6da`
- `watchdog!WdLogSingleEntry1` at `0x1402ad747`
- `watchdog!WdLogSingleEntry1` at `0x1402ad98f`
- `watchdog!WdLogSingleEntry1` at `0x1402ada01`
- `watchdog!WdLogSingleEntry1` at `0x1402ada90`
- `watchdog!WdLogSingleEntry1` at `0x1402ad345`
- `watchdog!WdLogSingleEntry1` at `0x1402ad36b`
- `watchdog!WdLogSingleEntry1` at `0x1402ad45f`
- `watchdog!WdLogSingleEntry1` at `0x1402ad579`
- `watchdog!WdLogSingleEntry1` at `0x1402ad5df`
- `watchdog!WdLogSingleEntry1` at `0x1402ad6da`
- `watchdog!WdLogSingleEntry1` at `0x1402ad747`
- `watchdog!WdLogSingleEntry1` at `0x1402ad98f`
- `watchdog!WdLogSingleEntry1` at `0x1402ada01`
- `watchdog!WdLogSingleEntry1` at `0x1402ada90`

## pseudocode

```c
__int64 __fastcall DpiFdoHandleStartDevice(PDEVICE_OBJECT DeviceObject, IRP *a2)
{
  int *DeviceExtension; // rdi
  char v3; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  __int64 v6; // rcx
  int v7; // eax
  int v8; // esi
  int v9; // esi
  PIO_SECURITY_CONTEXT SecurityContext; // rdx
  __int64 v12; // r9
  struct _UNICODE_STRING *v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  PIRP v16; // rsi
  IO_STATUS_BLOCK *p_IoStatus; // r14
  __int64 Status; // r12
  PUNICODE_STRING v19; // rcx
  size_t v20; // r12
  void *Pool2; // rax
  int v22; // eax
  void *v23; // rcx
  int v24; // eax
  _WORD *StartContext; // r15
  bool v26; // zf
  int v27; // eax
  NTSTATUS v28; // eax
  void *v29; // rdx
  PIRP v30; // rax
  void *v31; // rdx
  PIRP v32; // rax
  IRP *v33; // r15
  PCLIENT_ID ClientId; // [rsp+20h] [rbp-F8h]
  PCLIENT_ID ClientIda; // [rsp+20h] [rbp-F8h]
  int StartRoutine; // [rsp+28h] [rbp-F0h]
  char v38; // [rsp+40h] [rbp-D8h]
  int v39; // [rsp+44h] [rbp-D4h] BYREF
  size_t Size; // [rsp+48h] [rbp-D0h] BYREF
  struct _UNICODE_STRING *v41; // [rsp+50h] [rbp-C8h] BYREF
  ULONG_PTR v42; // [rsp+58h] [rbp-C0h]
  struct _UNICODE_STRING *FileName; // [rsp+60h] [rbp-B8h]
  __int64 v44; // [rsp+70h] [rbp-A8h] BYREF
  int v45; // [rsp+78h] [rbp-A0h]
  const wchar_t *v46; // [rsp+80h] [rbp-98h]
  int *v47; // [rsp+88h] [rbp-90h]
  int v48; // [rsp+90h] [rbp-88h]
  int *v49; // [rsp+98h] [rbp-80h]
  int v50; // [rsp+A0h] [rbp-78h]
  __int64 v51; // [rsp+A8h] [rbp-70h]
  int v52; // [rsp+B0h] [rbp-68h]
  __int64 v53; // [rsp+B8h] [rbp-60h]
  __int128 v54; // [rsp+C0h] [rbp-58h]
  __int128 v55; // [rsp+D0h] [rbp-48h]
  unsigned int v56; // [rsp+120h] [rbp+8h] BYREF
  PIRP Irp; // [rsp+128h] [rbp+10h]
  void *ThreadHandle; // [rsp+130h] [rbp+18h] BYREF
  ULONG_PTR v59; // [rsp+138h] [rbp+20h] BYREF

  Irp = a2;
  DeviceExtension = (int *)DeviceObject->DeviceExtension;
  v3 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v38 = 0;
  LODWORD(Size) = 0;
  v56 = 0;
  AcquireMiniportListMutex();
  KeEnterCriticalRegion();
  if ( *((_BYTE *)DeviceExtension + 484) )
    DpiCheckForOutstandingD3Requests(DeviceExtension);
  ExAcquireResourceExclusiveLite(*((PERESOURCE *)DeviceExtension + 21), 1u);
  v7 = WindowsQueryLicenseDWORD(v6, &v56);
  if ( v7 < 0 )
  {
    v8 = 1;
    WdLogSingleEntry1(4, v7);
    WdLogGlobalForLineNumber = 7346;
  }
  else
  {
    v8 = v56;
    WdLogSingleEntry1(4, v56);
    WdLogGlobalForLineNumber = 7333;
  }
  v39 = 1;
  v44 = 0;
  v46 = L"MultiMonSupport";
  v45 = 288;
  v48 = 67108868;
  v47 = &v39;
  v50 = 4;
  v49 = &v39;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  HIDWORD(ClientId) = 0;
  v55 = 0;
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", &v44);
  if ( !v39 )
    v8 = 0;
  if ( !v8
    && DeviceExtension[4] == 1953656900
    && DeviceExtension[5] == 2
    && !(unsigned __int8)DpiFdoIsPostDevice(DeviceObject)
    && !*((_BYTE *)DeviceExtension + 480) )
  {
    v3 = 1;
    v9 = -1071774664;
    WdLogSingleEntry1(3, *((_QWORD *)DeviceExtension + 3));
    WdLogGlobalForLineNumber = 7393;
LABEL_40:
    if ( DeviceExtension[59] == 1 )
    {
      v22 = DeviceExtension[60];
      --DeviceExtension[69];
      DeviceExtension[59] = v22;
      DeviceExtension[60] = DeviceExtension[(DeviceExtension[69] & 7) + 61];
    }
    v23 = (void *)*((_QWORD *)DeviceExtension + 164);
    if ( v23 )
    {
      ExFreePoolWithTag(v23, 0);
      *((_QWORD *)DeviceExtension + 164) = 0;
    }
    if ( !v3 )
    {
      LOBYTE(StartRoutine) = 0;
      DxgCreateLiveDumpWithWdLogs(403, 2050, v9, DeviceExtension[59], DeviceExtension[60], StartRoutine);
    }
    v33 = Irp;
    p_IoStatus = &Irp->IoStatus;
    goto LABEL_95;
  }
  LOBYTE(ThreadHandle) = 0;
  LOBYTE(v56) = 0;
  v42 = 0;
  FileName = 0;
  if ( *((_BYTE *)DeviceExtension + 1158) )
  {
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(&dword_140163468);
    if ( !dword_1401634A0++ )
      KeClearEvent(&stru_1401634A8);
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(&dword_140163468);
    v38 = 1;
  }
  DeviceExtension[678] = v8;
  if ( *((_BYTE *)DeviceExtension + 1155) == 1 )
  {
    SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
    v59 = 0;
    v41 = 0;
    if ( SecurityContext )
    {
      FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
      v42 = (ULONG_PTR)SecurityContext;
      DpiFilterOutVgaResources(DeviceExtension, SecurityContext, &v59, 0, 0);
      LOBYTE(v12) = 1;
      DpiFilterOutVgaResources(
        DeviceExtension,
        CurrentStackLocation->Parameters.QueryDirectory.FileName,
        &v41,
        v12,
        ClientIda);
      if ( v59 )
      {
        v13 = v41;
        if ( v41 )
        {
          CurrentStackLocation->Parameters.WMI.ProviderId = v59;
          CurrentStackLocation->Parameters.QueryDirectory.FileName = v13;
          LOBYTE(ThreadHandle) = 1;
        }
      }
    }
    else
    {
      WdLogSingleEntry1(2, 0);
      WdLogGlobalForLineNumber = 7461;
    }
  }
  if ( !(unsigned __int8)DpiFdoIsPostDevice(DeviceObject) && DeviceExtension[4] == 1953656900 && DeviceExtension[5] == 2 )
  {
    LODWORD(v59) = 0;
    LODWORD(ClientId) = 2;
    v15 = DpiReadPnpRegistryValue(v14, L"DisableNonPOSTDevice", &v59, 4, ClientId);
    if ( v15 >= 0 )
    {
      if ( (_DWORD)v59 )
      {
        v9 = -1073741823;
        WdLogSingleEntry1(2, -1073741823);
        WdLogGlobalForLineNumber = 7510;
        goto LABEL_40;
      }
    }
    else
    {
      WdLogSingleEntry1(4, v15);
      WdLogGlobalForLineNumber = 7497;
    }
  }
  v16 = Irp;
  IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)DeviceExtension + 20), Irp);
  p_IoStatus = &v16->IoStatus;
  Status = v16->IoStatus.Status;
  v9 = Status;
  if ( (int)Status < 0 )
  {
    WdLogSingleEntry5(
      2,
      (unsigned int)DeviceExtension[136],
      Status,
      (unsigned int)DeviceExtension[281],
      (unsigned int)DeviceExtension[282],
      *(_QWORD *)(*((_QWORD *)DeviceExtension + 5) + 152LL));
    WdLogGlobalForLineNumber = 7535;
    if ( (_DWORD)Status == -1073741810
      && *(_BYTE *)(*((_QWORD *)DeviceExtension + 5) + 134LL)
      && RtlCompareMemory(DeviceExtension + 136, &GUID_BUS_TYPE_USB, 0x10u) == 16 )
    {
      v3 = 1;
      goto LABEL_40;
    }
LABEL_39:
    v3 = v56;
    goto LABEL_40;
  }
  v19 = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  v3 = 0;
  if ( v19 )
  {
    DpiDetermineResourceListSize(v19, &Size);
    v20 = (unsigned int)Size;
    Pool2 = (void *)ExAllocatePool2(256, (unsigned int)Size, 1953656900);
    *((_QWORD *)DeviceExtension + 164) = Pool2;
    if ( !Pool2 )
    {
      v9 = -1073741801;
      WdLogSingleEntry1(6, -1073741801);
      WdLogGlobalForLineNumber = 7581;
      goto LABEL_39;
    }
    memmove(Pool2, CurrentStackLocation->Parameters.QueryDirectory.FileName, v20);
    if ( (_BYTE)ThreadHandle == 1 )
    {
      ExFreePoolWithTag(CurrentStackLocation->Parameters.Create.SecurityContext, 0);
      ExFreePoolWithTag(CurrentStackLocation->Parameters.QueryDirectory.FileName, 0);
      CurrentStackLocation->Parameters.WMI.ProviderId = v42;
      CurrentStackLocation->Parameters.QueryDirectory.FileName = FileName;
    }
    v3 = 0;
  }
  DeviceExtension[(DeviceExtension[69] & 7) + 61] = DeviceExtension[60];
  v24 = DeviceExtension[59];
  ++DeviceExtension[69];
  DeviceExtension[60] = v24;
  DeviceExtension[59] = 1;
  if ( DeviceExtension[4] != 1953656900 || DeviceExtension[5] != 2 )
  {
LABEL_54:
    if ( !(_BYTE)word_140162EA0 )
      goto LABEL_57;
    goto LABEL_55;
  }
  if ( !*((_BYTE *)DeviceExtension + 2717) )
  {
    HIBYTE(word_140162EA0) = 1;
    goto LABEL_54;
  }
  LOBYTE(word_140162EA0) = 1;
LABEL_55:
  if ( HIBYTE(word_140162EA0) )
    KeSetEvent(&stru_140162EA8, 0, 0);
LABEL_57:
  LOBYTE(ThreadHandle) = 0;
  LOBYTE(v59) = 0;
  if ( !*((_BYTE *)DeviceExtension + 2716)
    && (int)DpiFdoIsMdmDeviceAndOwnsMux(DeviceObject, &ThreadHandle, &v59) >= 0
    && (_BYTE)ThreadHandle )
  {
    if ( !(_BYTE)v59 )
      goto LABEL_71;
    goto LABEL_67;
  }
  if ( !qword_1401631A8 )
  {
    if ( DeviceExtension[4] == 1953656900 && DeviceExtension[5] == 2 )
    {
      if ( (unsigned __int8)DpiFdoIsPostDevice(DeviceObject) || *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL) )
LABEL_67:
        qword_1401631A8 = (__int64)DeviceObject;
    }
    else if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL) && *((_QWORD *)DeviceExtension + 354) )
    {
      qword_1401631A8 = *((_QWORD *)DeviceExtension + 354);
    }
  }
LABEL_71:
  if ( !*((_BYTE *)DeviceExtension + 480)
    && *((_BYTE *)DeviceExtension + 1153)
    && !(unsigned __int8)DpiFdoIsMsBddAnchoredDevice(DeviceObject) )
  {
    WdLogSingleEntry1(4, DeviceObject);
    WdLogGlobalForLineNumber = 7712;
    v3 = 1;
    v9 = -1071774664;
    goto LABEL_40;
  }
  if ( byte_140162EA2 && !*((_BYTE *)DeviceExtension + 1158) )
  {
    ThreadHandle = 0;
    StartContext = (_WORD *)ExAllocatePool2(256, 1552, 1953656900);
    if ( !StartContext )
    {
      v9 = -1073741801;
      WdLogSingleEntry1(6, -1073741801);
      WdLogGlobalForLineNumber = 7756;
      goto LABEL_39;
    }
    if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 21) + 108LL)
      || (v26 = (unsigned __int8)DpiFdoIsMsBddAnchoredDevice(DeviceObject) == 0, v27 = 0, !v26) )
    {
      v27 = 2;
    }
    *(_DWORD *)StartContext = v27;
    StartContext[2] = 0;
    *((_DWORD *)StartContext + 131) = 0;
    v28 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, DpiFdoStartAdapterThread, StartContext);
    v9 = v28;
    if ( v28 < 0 )
    {
      WdLogSingleEntry1(2, v28);
      WdLogGlobalForLineNumber = 7787;
      ExFreePoolWithTag(StartContext, 0x74727044u);
      goto LABEL_39;
    }
    ZwClose(ThreadHandle);
  }
  DeviceExtension[71] = 1;
  DeviceExtension[70] = 1;
  PoSetPowerState(DeviceObject, DevicePowerState, (POWER_STATE)1);
  if ( v9 < 0 )
    goto LABEL_40;
  if ( DeviceExtension[4] == 1953656900 && DeviceExtension[5] == 2 )
  {
    v29 = (void *)*((_QWORD *)DeviceExtension + 686);
    if ( v29 )
    {
      v30 = IoCsqRemoveNextIrp((PIO_CSQ)(DeviceExtension + 1350), v29);
      *((_QWORD *)DeviceExtension + 686) = 0;
      if ( v30 )
      {
        *((_BYTE *)DeviceExtension + 5516) = 1;
        v30->IoStatus.Status = 0;
        v30->IoStatus.Information = 0;
        IofCompleteRequest(v30, 0);
        IoInvalidateDeviceState(*((PDEVICE_OBJECT *)DeviceExtension + 19));
      }
    }
    v31 = (void *)*((_QWORD *)DeviceExtension + 690);
    if ( v31 )
    {
      v32 = IoCsqRemoveNextIrp((PIO_CSQ)(DeviceExtension + 1350), v31);
      *((_QWORD *)DeviceExtension + 690) = 0;
      if ( v32 )
      {
        *((_BYTE *)DeviceExtension + 5548) = 1;
        v32->IoStatus.Status = 0;
        v32->IoStatus.Information = 0;
        IofCompleteRequest(v32, 0);
      }
    }
  }
  v33 = Irp;
LABEL_95:
  if ( v38 )
  {
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(&dword_140163468);
    if ( !--dword_1401634A0 )
      KeSetEvent(&stru_1401634A8, 0, 0);
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(&dword_140163468);
  }
  if ( *((_BYTE *)DeviceExtension + 484) )
    DpiEnableD3Requests(*((_QWORD *)DeviceExtension + 3));
  ExReleaseResourceLite(*((PERESOURCE *)DeviceExtension + 21));
  KeLeaveCriticalRegion();
  ReleaseMiniportListMutex();
  p_IoStatus->Status = v9;
  IofCompleteRequest(v33, 1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1402ad2b0  mov     rax, rsp
0x1402ad2b3  mov     [rax+10h], rdx
0x1402ad2b7  push    rbx
0x1402ad2b8  push    rsi
0x1402ad2b9  push    rdi
0x1402ad2ba  push    r12
0x1402ad2bc  push    r13
0x1402ad2be  push    r14
0x1402ad2c0  push    r15
0x1402ad2c2  sub     rsp, 0E0h
0x1402ad2c9  mov     rdi, [rcx+40h]
0x1402ad2cd  xor     r12d, r12d
0x1402ad2d0  mov     r15, [rdx+0B8h]
0x1402ad2d7  mov     r13, rcx
0x1402ad2da  mov     [rsp+118h+var_D8], r12b
0x1402ad2df  mov     dword ptr [rsp+118h+Size], r12d
0x1402ad2e4  mov     [rax+8], r12d
0x1402ad2e8  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402ad2ed  call    cs:__imp_KeEnterCriticalRegion
0x1402ad2f4  nop     dword ptr [rax+rax+00h]
0x1402ad2f9  cmp     [rdi+1E4h], r12b
0x1402ad300  jz      short loc_1402AD30A
0x1402ad302  mov     rcx, rdi
0x1402ad305  call    DpiCheckForOutstandingD3Requests
0x1402ad30a  mov     rcx, [rdi+0A8h]; Resource
0x1402ad311  mov     ebx, 1
0x1402ad316  mov     dl, bl; Wait
0x1402ad318  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402ad31f  nop     dword ptr [rax+rax+00h]
0x1402ad324  lea     rdx, [rsp+118h+arg_0]
0x1402ad32c  call    WindowsQueryLicenseDWORD
0x1402ad331  test    eax, eax
0x1402ad333  js      short loc_1402AD35D
0x1402ad335  mov     esi, [rsp+118h+arg_0]
0x1402ad33c  lea     r14d, [rbx+3]
0x1402ad340  mov     edx, esi
0x1402ad342  mov     ecx, r14d
0x1402ad345  call    cs:__imp_WdLogSingleEntry1
0x1402ad34c  nop     dword ptr [rax+rax+00h]
0x1402ad351  mov     cs:WdLogGlobalForLineNumber, 1CA5h
0x1402ad35b  jmp     short loc_1402AD381
0x1402ad35d  mov     esi, ebx
0x1402ad35f  mov     r14d, 4
0x1402ad365  movsxd  rdx, eax
0x1402ad368  mov     ecx, r14d
0x1402ad36b  call    cs:__imp_WdLogSingleEntry1
0x1402ad372  nop     dword ptr [rax+rax+00h]
0x1402ad377  mov     cs:WdLogGlobalForLineNumber, 1CB2h
0x1402ad381  xorps   xmm0, xmm0
0x1402ad384  mov     [rsp+118h+var_D4], ebx
0x1402ad388  lea     rax, aMultimonsuppor; "MultiMonSupport"
0x1402ad38f  mov     [rsp+118h+var_A8], r12
0x1402ad394  mov     [rsp+118h+var_98], rax
0x1402ad39c  lea     r8, [rsp+118h+var_A8]
0x1402ad3a1  xor     r9d, r9d
0x1402ad3a4  mov     [rsp+118h+var_A0], 120h
0x1402ad3ac  lea     rax, [rsp+118h+var_D4]
0x1402ad3b1  mov     [rsp+118h+var_88], 4000004h
0x1402ad3bc  mov     [rsp+118h+var_90], rax
0x1402ad3c4  lea     rdx, Path; "GraphicsDrivers"
0x1402ad3cb  lea     rax, [rsp+118h+var_D4]
0x1402ad3d0  mov     [rsp+118h+var_78], r14d
0x1402ad3d8  lea     ecx, [r9+2]
0x1402ad3dc  mov     [rsp+118h+var_80], rax
0x1402ad3e4  mov     [rsp+118h+var_70], r12
0x1402ad3ec  mov     [rsp+118h+var_68], r12d
0x1402ad3f4  mov     [rsp+118h+var_60], r12
0x1402ad3fc  movups  [rsp+118h+var_58], xmm0
0x1402ad404  mov     [rsp+118h+ClientId], r12
0x1402ad409  movups  [rsp+118h+var_48], xmm0
0x1402ad411  call    cs:__imp_RtlQueryRegistryValuesEx
0x1402ad418  nop     dword ptr [rax+rax+00h]
0x1402ad41d  cmp     [rsp+118h+var_D4], r12d
0x1402ad422  cmovz   esi, r12d
0x1402ad426  test    esi, esi
0x1402ad428  jnz     short loc_1402AD47A
0x1402ad42a  cmp     dword ptr [rdi+10h], 74727044h
0x1402ad431  jnz     short loc_1402AD47A
0x1402ad433  cmp     dword ptr [rdi+14h], 2
0x1402ad437  jnz     short loc_1402AD47A
0x1402ad439  mov     rcx, r13
0x1402ad43c  call    DpiFdoIsPostDevice
0x1402ad441  test    al, al
0x1402ad443  jnz     short loc_1402AD47A
0x1402ad445  cmp     [rdi+1E0h], r12b
0x1402ad44c  jnz     short loc_1402AD47A
0x1402ad44e  mov     r12b, bl
0x1402ad451  mov     esi, 0C01E0438h
0x1402ad456  mov     rdx, [rdi+18h]
0x1402ad45a  mov     ecx, 3
0x1402ad45f  call    cs:__imp_WdLogSingleEntry1
0x1402ad466  nop     dword ptr [rax+rax+00h]
0x1402ad46b  mov     cs:WdLogGlobalForLineNumber, 1CE1h
0x1402ad475  jmp     loc_1402AD765
0x1402ad47a  xor     eax, eax
0x1402ad47c  mov     byte ptr [rsp+118h+ThreadHandle], r12b
0x1402ad484  mov     byte ptr [rsp+118h+arg_0], r12b
0x1402ad48c  mov     [rsp+118h+var_C0], rax
0x1402ad491  mov     [rsp+118h+var_B8], rax
0x1402ad496  cmp     [rdi+486h], al
0x1402ad49c  jz      short loc_1402AD4EF
0x1402ad49e  lea     rcx, dword_140163468
0x1402ad4a5  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1402ad4ac  nop     dword ptr [rax+rax+00h]
0x1402ad4b1  mov     eax, cs:dword_1401634A0
0x1402ad4b7  mov     ecx, eax
0x1402ad4b9  add     eax, ebx
0x1402ad4bb  mov     cs:dword_1401634A0, eax
0x1402ad4c1  test    ecx, ecx
0x1402ad4c3  jnz     short loc_1402AD4D8
0x1402ad4c5  lea     rcx, stru_1401634A8; Event
0x1402ad4cc  call    cs:__imp_KeClearEvent
0x1402ad4d3  nop     dword ptr [rax+rax+00h]
0x1402ad4d8  lea     rcx, dword_140163468
0x1402ad4df  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1402ad4e6  nop     dword ptr [rax+rax+00h]
0x1402ad4eb  mov     [rsp+118h+var_D8], bl
0x1402ad4ef  mov     [rdi+0A98h], esi
0x1402ad4f5  cmp     [rdi+483h], bl
0x1402ad4fb  jnz     loc_1402AD58F
0x1402ad501  mov     rdx, [r15+8]
0x1402ad505  mov     [rsp+118h+arg_18], r12
0x1402ad50d  mov     [rsp+118h+var_C8], r12
0x1402ad512  test    rdx, rdx
0x1402ad515  jz      short loc_1402AD574
0x1402ad517  mov     rax, [r15+10h]
0x1402ad51b  lea     r8, [rsp+118h+arg_18]
0x1402ad523  xor     r9d, r9d
0x1402ad526  mov     [rsp+118h+var_B8], rax
0x1402ad52b  mov     rcx, rdi
0x1402ad52e  mov     [rsp+118h+var_C0], rdx
0x1402ad533  call    DpiFilterOutVgaResources
0x1402ad538  mov     rdx, [r15+10h]
0x1402ad53c  lea     r8, [rsp+118h+var_C8]
0x1402ad541  mov     r9b, bl
0x1402ad544  mov     rcx, rdi
0x1402ad547  call    DpiFilterOutVgaResources
0x1402ad54c  mov     rcx, [rsp+118h+arg_18]
0x1402ad554  test    rcx, rcx
0x1402ad557  jz      short loc_1402AD58F
0x1402ad559  mov     rax, [rsp+118h+var_C8]
0x1402ad55e  test    rax, rax
0x1402ad561  jz      short loc_1402AD58F
0x1402ad563  mov     [r15+8], rcx
0x1402ad567  mov     [r15+10h], rax
0x1402ad56b  mov     byte ptr [rsp+118h+ThreadHandle], bl
0x1402ad572  jmp     short loc_1402AD58F
0x1402ad574  mov     ecx, 2
0x1402ad579  call    cs:__imp_WdLogSingleEntry1
0x1402ad580  nop     dword ptr [rax+rax+00h]
0x1402ad585  mov     cs:WdLogGlobalForLineNumber, 1D25h
0x1402ad58f  mov     rcx, r13
0x1402ad592  call    DpiFdoIsPostDevice
0x1402ad597  test    al, al
0x1402ad599  jnz     short loc_1402AD5F5
0x1402ad59b  cmp     dword ptr [rdi+10h], 74727044h
0x1402ad5a2  jnz     short loc_1402AD5F5
0x1402ad5a4  cmp     dword ptr [rdi+14h], 2
0x1402ad5a8  jnz     short loc_1402AD5F5
0x1402ad5aa  mov     r9d, r14d
0x1402ad5ad  mov     dword ptr [rsp+118h+arg_18], r12d
0x1402ad5b5  lea     r8, [rsp+118h+arg_18]
0x1402ad5bd  mov     dword ptr [rsp+118h+ClientId], 2
0x1402ad5c5  lea     rdx, aDisablenonpost; "DisableNonPOSTDevice"
0x1402ad5cc  call    DpiReadPnpRegistryValue
0x1402ad5d1  test    eax, eax
0x1402ad5d3  jns     loc_1402AD6BD
0x1402ad5d9  movsxd  rdx, eax
0x1402ad5dc  mov     ecx, r14d
0x1402ad5df  call    cs:__imp_WdLogSingleEntry1
0x1402ad5e6  nop     dword ptr [rax+rax+00h]
0x1402ad5eb  mov     cs:WdLogGlobalForLineNumber, 1D49h
0x1402ad5f5  mov     rsi, [rsp+118h+Irp]
0x1402ad5fd  mov     rcx, [rdi+0A0h]; DeviceObject
0x1402ad604  mov     rdx, rsi; Irp
0x1402ad607  call    cs:__imp_IoForwardIrpSynchronously
0x1402ad60e  nop     dword ptr [rax+rax+00h]
0x1402ad613  lea     r14, [rsi+30h]
0x1402ad617  movsxd  r12, dword ptr [r14]
0x1402ad61a  mov     esi, r12d
0x1402ad61d  test    r12d, r12d
0x1402ad620  jns     loc_1402AD6F2
0x1402ad626  mov     rax, [rdi+28h]
0x1402ad62a  lea     r14, [rdi+220h]
0x1402ad631  mov     r10d, [rdi+468h]
0x1402ad638  mov     r8, r12
0x1402ad63b  mov     r9d, [rdi+464h]
0x1402ad642  mov     ecx, 2
0x1402ad647  mov     edx, [r14]
0x1402ad64a  mov     rax, [rax+98h]
0x1402ad651  mov     [rsp+118h+StartRoutine], rax
0x1402ad656  mov     [rsp+118h+ClientId], r10
0x1402ad65b  call    cs:__imp_WdLogSingleEntry5
0x1402ad662  nop     dword ptr [rax+rax+00h]
0x1402ad667  mov     cs:WdLogGlobalForLineNumber, 1D6Fh
0x1402ad671  cmp     r12d, 0C000000Eh
0x1402ad678  jnz     loc_1402AD75D
0x1402ad67e  mov     rax, [rdi+28h]
0x1402ad682  cmp     byte ptr [rax+86h], 0
0x1402ad689  jz      loc_1402AD75D
0x1402ad68f  mov     r8d, 10h; Length
0x1402ad695  lea     rdx, GUID_BUS_TYPE_USB; Source2
0x1402ad69c  mov     rcx, r14; Source1
0x1402ad69f  call    cs:__imp_RtlCompareMemory
0x1402ad6a6  nop     dword ptr [rax+rax+00h]
0x1402ad6ab  cmp     rax, 10h
0x1402ad6af  jnz     loc_1402AD75D
0x1402ad6b5  mov     r12b, bl
0x1402ad6b8  jmp     loc_1402AD765
0x1402ad6bd  cmp     dword ptr [rsp+118h+arg_18], r12d
0x1402ad6c5  jz      loc_1402AD5F5
0x1402ad6cb  mov     rsi, 0FFFFFFFFC0000001h
0x1402ad6d2  mov     rdx, rsi
0x1402ad6d5  mov     ecx, 2
0x1402ad6da  call    cs:__imp_WdLogSingleEntry1
0x1402ad6e1  nop     dword ptr [rax+rax+00h]
0x1402ad6e6  mov     cs:WdLogGlobalForLineNumber, 1D56h
0x1402ad6f0  jmp     short loc_1402AD765
0x1402ad6f2  mov     rcx, [r15+10h]
0x1402ad6f6  xor     r12d, r12d
0x1402ad6f9  test    rcx, rcx
0x1402ad6fc  jz      loc_1402AD846
0x1402ad702  lea     rdx, [rsp+118h+Size]
0x1402ad707  call    DpiDetermineResourceListSize
0x1402ad70c  mov     r12d, dword ptr [rsp+118h+Size]
0x1402ad711  mov     r8d, 74727044h
0x1402ad717  mov     edx, r12d
0x1402ad71a  mov     ecx, 100h
0x1402ad71f  call    cs:__imp_ExAllocatePool2
0x1402ad726  nop     dword ptr [rax+rax+00h]
0x1402ad72b  mov     [rdi+520h], rax
0x1402ad732  test    rax, rax
0x1402ad735  jnz     loc_1402AD7F5
0x1402ad73b  mov     rdx, 0FFFFFFFFC0000017h
0x1402ad742  mov     esi, edx
0x1402ad744  lea     ecx, [rax+6]
0x1402ad747  call    cs:__imp_WdLogSingleEntry1
0x1402ad74e  nop     dword ptr [rax+rax+00h]
0x1402ad753  mov     cs:WdLogGlobalForLineNumber, 1D9Dh
0x1402ad75d  mov     r12b, byte ptr [rsp+118h+arg_0]
0x1402ad765  cmp     [rdi+0ECh], ebx
0x1402ad76b  jnz     short loc_1402AD795
0x1402ad76d  mov     eax, [rdi+0F0h]
0x1402ad773  dec     dword ptr [rdi+114h]
0x1402ad779  mov     [rdi+0ECh], eax
0x1402ad77f  mov     eax, [rdi+114h]
0x1402ad785  and     eax, 7
0x1402ad788  mov     eax, [rdi+rax*4+0F4h]
0x1402ad78f  mov     [rdi+0F0h], eax
0x1402ad795  mov     rcx, [rdi+520h]; P
0x1402ad79c  test    rcx, rcx
0x1402ad79f  jz      short loc_1402AD7BA
0x1402ad7a1  xor     edx, edx; Tag
0x1402ad7a3  call    cs:__imp_ExFreePoolWithTag
0x1402ad7aa  nop     dword ptr [rax+rax+00h]
0x1402ad7af  mov     qword ptr [rdi+520h], 0
0x1402ad7ba  test    r12b, r12b
0x1402ad7bd  jnz     loc_1402ADC72
0x1402ad7c3  movsxd  rcx, dword ptr [rdi+0F0h]
0x1402ad7ca  xor     r12d, r12d
0x1402ad7cd  movsxd  r9, dword ptr [rdi+0ECh]
0x1402ad7d4  mov     edx, 802h
0x1402ad7d9  mov     byte ptr [rsp+118h+StartRoutine], r12b
0x1402ad7de  mov     [rsp+118h+ClientId], rcx
0x1402ad7e3  mov     ecx, 193h
0x1402ad7e8  movsxd  r8, esi
0x1402ad7eb  call    ?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x1402ad7f0  jmp     loc_1402ADC75
0x1402ad7f5  mov     rdx, [r15+10h]; Src
0x1402ad7f9  mov     r8, r12; Size
0x1402ad7fc  mov     rcx, rax; void *
0x1402ad7ff  call    memmove
0x1402ad804  cmp     byte ptr [rsp+118h+ThreadHandle], bl
0x1402ad80b  jnz     short loc_1402AD843
0x1402ad80d  mov     rcx, [r15+8]; P
0x1402ad811  xor     edx, edx; Tag
0x1402ad813  call    cs:__imp_ExFreePoolWithTag
0x1402ad81a  nop     dword ptr [rax+rax+00h]
0x1402ad81f  mov     rcx, [r15+10h]; P
0x1402ad823  xor     edx, edx; Tag
0x1402ad825  call    cs:__imp_ExFreePoolWithTag
0x1402ad82c  nop     dword ptr [rax+rax+00h]
0x1402ad831  mov     rax, [rsp+118h+var_C0]
0x1402ad836  mov     [r15+8], rax
0x1402ad83a  mov     rax, [rsp+118h+var_B8]
0x1402ad83f  mov     [r15+10h], rax
0x1402ad843  xor     r12d, r12d
0x1402ad846  mov     ecx, [rdi+114h]
0x1402ad84c  mov     r15d, 74727044h
0x1402ad852  mov     eax, [rdi+0F0h]
0x1402ad858  and     ecx, 7
0x1402ad85b  mov     [rdi+rcx*4+0F4h], eax
0x1402ad862  mov     eax, [rdi+0ECh]
0x1402ad868  add     [rdi+114h], ebx
0x1402ad86e  mov     [rdi+0F0h], eax
0x1402ad874  mov     [rdi+0ECh], ebx
0x1402ad87a  cmp     [rdi+10h], r15d
0x1402ad87e  jnz     short loc_1402AD89D
0x1402ad880  cmp     dword ptr [rdi+14h], 2
0x1402ad884  jnz     short loc_1402AD89D
  ... truncated ...
```
