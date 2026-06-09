# FatMountVolume

- ea: `0x140040674`
- end: `0x1400412a2`
- name: `FatMountVolume`
- size: `3118`
- prototype: `__int64 __fastcall(int, PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, installer_update`

## callers

- `0x14003ec78`

## callees

- `0x1400016f8`
- `0x14000178c`
- `0x140001858`
- `0x140001bb4`
- `0x140002b30`
- `0x140005924`
- `0x140005e48`
- `0x140006350`
- `0x140006dbc`
- `0x14000c230`
- `0x14000c680`
- `0x14000cba0`
- `0x140023380`
- `0x14002e4b0`
- `0x14002e5c4`
- `0x140032e98`
- `0x14003fff4`
- `0x140040674`
- `0x140042740`
- `0x140047960`
- `0x140047e34`
- `0x140048848`
- `0x140048ed0`
- `0x1400497f4`
- `0x14004d144`
- `0x14004d2a8`

## import_xrefs

- `ntoskrnl!CcSetAdditionalCacheAttributesEx` at `0x14004126c`
- `ntoskrnl!CcSetAdditionalCacheAttributesEx` at `0x14004126c`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140040777`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140040777`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140041280`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140041280`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140040db6`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140040db6`
- `ntoskrnl!ObfReferenceObject` at `0x14004112d`
- `ntoskrnl!ObfReferenceObject` at `0x14004112d`
- `ntoskrnl!IoCreateDevice` at `0x14004095e`
- `ntoskrnl!IoCreateDevice` at `0x14004095e`
- `ntoskrnl!IoDeleteDevice` at `0x14004122a`
- `ntoskrnl!IoDeleteDevice` at `0x14005eeeb`
- `ntoskrnl!IoDeleteDevice` at `0x14004122a`
- `ntoskrnl!IoDeleteDevice` at `0x14005eeeb`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400409c4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400409c4`
- `ntoskrnl!IoVolumeDeviceToGuid` at `0x140040a6a`
- `ntoskrnl!IoVolumeDeviceToGuid` at `0x140040a6a`
- `ntoskrnl!FsRtlVolumeDeviceToCorrelationId` at `0x140040aa9`
- `ntoskrnl!FsRtlVolumeDeviceToCorrelationId` at `0x140040aa9`
- `ntoskrnl!IoVolumeDeviceToGuidPath` at `0x140040aff`
- `ntoskrnl!IoVolumeDeviceToGuidPath` at `0x140040aff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140040874`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140040874`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004124a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ef36`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004124a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ef36`
- `ntoskrnl!CcUnpinData` at `0x1400411ef`
- `ntoskrnl!CcUnpinData` at `0x14005eea0`
- `ntoskrnl!CcUnpinData` at `0x1400411ef`
- `ntoskrnl!CcUnpinData` at `0x14005eea0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c84`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040ad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040c84`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ee80`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400408d7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140040c35`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400408d7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140040c35`
- `ntoskrnl!ExRaiseStatus` at `0x140040785`
- `ntoskrnl!ExRaiseStatus` at `0x1400411ad`
- `ntoskrnl!ExRaiseStatus` at `0x140040785`
- `ntoskrnl!ExRaiseStatus` at `0x1400411ad`
- `ntoskrnl!ObfDereferenceObject` at `0x14004113c`
- `ntoskrnl!ObfDereferenceObject` at `0x14004128f`
- `ntoskrnl!ObfDereferenceObject` at `0x14004113c`
- `ntoskrnl!ObfDereferenceObject` at `0x14004128f`

## pseudocode

```c
__int64 __fastcall FatMountVolume(__int64 a1, PDEVICE_OBJECT DeviceObject, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 result; // rax
  NTSTATUS v9; // eax
  char *v10; // rsi
  struct _FILE_OBJECT *DeferredRoutine; // r14
  union _DEVICE_OBJECT::$3ABEFC84562B0417329DFE2AD83813CB *p_Queue; // rbx
  __int64 v13; // rcx
  NTSTATUS v14; // edi
  __int64 v15; // r8
  ULONG v16; // r14d
  SIZE_T v17; // rdi
  char *PoolWithTag; // rax
  ULONG AlignmentRequirement; // ecx
  PDEVICE_OBJECT v20; // rax
  struct _DRIVER_OBJECT **p_DriverObject; // rax
  __int64 v22; // rdi
  int v23; // eax
  PDRIVER_CONTROL DeviceRoutine; // rcx
  int v25; // edx
  __int16 v26; // cx
  _OWORD *v27; // rax
  unsigned __int16 v28; // dx
  __int64 *i; // rcx
  __int64 *v30; // rdi
  __int64 v31; // r14
  unsigned __int16 v32; // ax
  int v33; // r8d
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 Fcb; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r12
  __int64 v41; // rcx
  char v42; // [rsp+50h] [rbp-1E8h]
  char v43; // [rsp+51h] [rbp-1E7h]
  PDEVICE_OBJECT v44; // [rsp+58h] [rbp-1E0h] BYREF
  __int64 v45; // [rsp+60h] [rbp-1D8h]
  ULONG v46; // [rsp+68h] [rbp-1D0h]
  struct _FILE_OBJECT *v47; // [rsp+70h] [rbp-1C8h]
  PVOID Bcb; // [rsp+78h] [rbp-1C0h]
  STRING SourceString; // [rsp+80h] [rbp-1B8h] BYREF
  char *v50; // [rsp+90h] [rbp-1A8h]
  int v51; // [rsp+98h] [rbp-1A0h]
  union _DEVICE_OBJECT::$3ABEFC84562B0417329DFE2AD83813CB *v52; // [rsp+A0h] [rbp-198h]
  __int64 v53; // [rsp+A8h] [rbp-190h]
  CHAR *v54; // [rsp+B0h] [rbp-188h]
  __int64 *v55; // [rsp+B8h] [rbp-180h]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-178h] BYREF
  __int128 v57; // [rsp+D0h] [rbp-168h]
  __int64 v58; // [rsp+E0h] [rbp-158h]
  _DWORD v59[36]; // [rsp+F0h] [rbp-148h] BYREF
  _OWORD v60[2]; // [rsp+180h] [rbp-B8h] BYREF
  __int64 v61; // [rsp+1A0h] [rbp-98h]
  int v62[4]; // [rsp+1A8h] [rbp-90h] BYREF
  __int64 v63; // [rsp+1B8h] [rbp-80h]
  __int128 v64; // [rsp+1C0h] [rbp-78h] BYREF
  _OWORD v65[2]; // [rsp+1D0h] [rbp-68h] BYREF

  v53 = a1;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 184LL);
  Bcb = 0;
  v54 = 0;
  *(_DWORD *)&SourceString.Length = 0;
  v44 = 0;
  v57 = 0;
  v46 = 0;
  v61 = 0;
  memset(v59, 0, sizeof(v59));
  memset(v60, 0, sizeof(v60));
  v64 = 0;
  if ( (DeviceObject->Characteristics & 1) != 0 )
  {
    result = FatPerformDevIoCtrl(v7, 477184, DeviceObject);
    if ( (int)result < 0 )
    {
      if ( (*(_BYTE *)(v6 + 2) & 1) == 0 && *(_DWORD *)(*(_QWORD *)(a3 + 16) + 72LL) == 7 )
      {
        *(_DWORD *)(a1 + 72) = result;
        v9 = FsRtlNormalizeNtstatus(result, -1073741591);
        ExRaiseStatus(v9);
      }
      return result;
    }
  }
  if ( *((_QWORD *)&v57 + 1) != 4 )
    v46 = 0;
  if ( DeviceObject->DeviceType == 2 && !(unsigned __int8)FatScanForDataTrack(v7, DeviceObject) )
    return 3221225807LL;
  v10 = 0;
  v50 = 0;
  v43 = 0;
  v55 = 0;
  v45 = 0;
  DeferredRoutine = 0;
  v47 = 0;
  v51 = FatPerformDevIoCtrl(v7, 458824, DeviceObject);
  *(_DWORD *)(a1 + 68) |= 2u;
  FatScanForDismountedVcb(a1);
  Bcb = 0;
  p_Queue = 0;
  v52 = 0;
  v44 = 0;
  v42 = 0;
  ExAcquireResourceExclusiveLite(&Resource, (*(_DWORD *)(a1 + 68) & 2) != 0);
  v14 = FatPerformDevIoCtrl(v13, 458752, DeviceObject);
  if ( v14 < 0 )
    goto LABEL_88;
  v16 = WORD2(v61);
  v17 = (WORD2(v61) + 4095) & 0xFFFFF000;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1552, v17, 0x74626146u);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v17);
  v50 = v10;
  if ( (unsigned __int8)FatReadBootSector(DeviceObject, v16, v10) && (unsigned __int8)FatIsBootSectorFat(v10) )
  {
    v14 = IoCreateDevice(DriverObject, 0x5A0u, 0, 8u, 0, 0, &v44);
    if ( v14 < 0 )
      goto LABEL_87;
    AlignmentRequirement = DeviceObject->AlignmentRequirement;
    v20 = v44;
    if ( AlignmentRequirement > v44->AlignmentRequirement )
    {
      v44->AlignmentRequirement = AlignmentRequirement;
      v20 = v44;
    }
    v20[1].ReferenceCount = 0;
    p_DriverObject = &v44[1].DriverObject;
    v44[1].NextDevice = (PDEVICE_OBJECT)((char *)v44 + 344);
    *p_DriverObject = (struct _DRIVER_OBJECT *)p_DriverObject;
    *(_DWORD *)&v44[1].Type = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)&v44[1].AttachedDevice);
    v44->StackSize = DeviceObject->StackSize + 1;
    v44->SectorSize = WORD2(v61);
    v44->Flags &= ~0x80u;
    *(_QWORD *)(a3 + 8) = v44;
    v22 = *(_QWORD *)(a3 + 16);
    v45 = v22;
    v23 = *(_DWORD *)(v22 + 48);
    if ( (v23 & 2) != 0 )
    {
      *(_DWORD *)(v22 + 48) = v23 & 0xFFFFFFFD;
      v43 = 1;
    }
    FatInitializeVcb(a1, &v44[1].Queue, DeviceObject, a3);
    p_Queue = &v44[1].Queue;
    v52 = &v44[1].Queue;
    if ( (int)IoVolumeDeviceToGuid(v44[1].Dpc.ProcessorHistory, v60) >= 0 )
    {
      *(_OWORD *)((char *)&p_Queue[17].Wcb.DeviceRoutine + 4) = v60[0];
      p_Queue[2].ListEntry = (LIST_ENTRY)v60[0];
    }
    if ( (int)FsRtlVolumeDeviceToCorrelationId(p_Queue[1].Wcb.BufferChainingDpc, &v64) >= 0 )
      *(_OWORD *)&p_Queue[2].Wcb.DeviceContext = v64;
    DeviceRoutine = p_Queue[2].Wcb.DeviceRoutine;
    if ( DeviceRoutine )
    {
      ExFreePoolWithTag(DeviceRoutine, 0);
      p_Queue[2].Wcb.DeviceRoutine = 0;
      p_Queue[2].Wcb.WaitQueueEntry.SortKey = 0;
    }
    IoVolumeDeviceToGuidPath(p_Queue[1].Wcb.BufferChainingDpc, &p_Queue[2].Wcb.NumberOfChannels);
    v25 = *(unsigned __int16 *)(v10 + 11);
    LOWORD(p_Queue[4].ListEntry.Flink) = v25;
    BYTE2(p_Queue[4].Wcb.DmaWaitEntry.Flink) = v10[13];
    WORD2(p_Queue[4].Wcb.DmaWaitEntry.Flink) = *((_WORD *)v10 + 7);
    BYTE6(p_Queue[4].Wcb.DmaWaitEntry.Flink) = v10[16];
    LOWORD(p_Queue[4].Wcb.DmaWaitEntry.Blink) = *(_WORD *)(v10 + 17);
    v26 = *(_WORD *)(v10 + 19);
    WORD1(p_Queue[4].Wcb.DmaWaitEntry.Blink) = v26;
    BYTE4(p_Queue[4].Wcb.DmaWaitEntry.Blink) = v10[21];
    HIWORD(p_Queue[4].Wcb.DmaWaitEntry.Blink) = *((_WORD *)v10 + 11);
    LOWORD(p_Queue[4].Wcb.NumberOfChannels) = *((_WORD *)v10 + 12);
    HIWORD(p_Queue[4].Wcb.NumberOfChannels) = *((_WORD *)v10 + 13);
    *((_DWORD *)&p_Queue[4].Wcb.1 + 5) = *((_DWORD *)v10 + 7);
    LODWORD(p_Queue[4].Wcb.DeviceRoutine) = *((_DWORD *)v10 + 8);
    HIDWORD(p_Queue[4].Wcb.DeviceRoutine) = *((_DWORD *)v10 + 9);
    LOWORD(p_Queue[4].Wcb.DeviceContext) = *((_WORD *)v10 + 20);
    WORD2(p_Queue[4].Wcb.DeviceContext) = *((_WORD *)v10 + 21);
    p_Queue[4].Wcb.NumberOfMapRegisters = *((_DWORD *)v10 + 11);
    *((_WORD *)&p_Queue[4].Wcb.NumberOfMapRegisters + 2) = *((_WORD *)v10 + 24);
    *((_WORD *)&p_Queue[4].Wcb.NumberOfMapRegisters + 3) = *((_WORD *)v10 + 25);
    if ( (v51 < 0 || v59[0] || LOBYTE(v59[8]) != 10 || (unsigned __int16)(v26 - 1) > 0x7Eu) && HIDWORD(v61) == v25 )
    {
      if ( v26 )
        LODWORD(p_Queue[4].Wcb.DeviceRoutine) = 0;
      if ( *((_WORD *)v10 + 11) )
      {
        *(_DWORD *)(a3 + 24) = *(_DWORD *)(v10 + 39);
        v27 = ExAllocatePoolWithTag((POOL_TYPE)1041, 0x24u, 0x53746146u);
        if ( !ExPoolZeroingNativelySupported && v27 )
        {
          *v27 = 0;
          v27[1] = 0;
          *((_DWORD *)v27 + 8) = 0;
        }
        p_Queue[4].Wcb.DeviceObject = v27;
        *v27 = *(_OWORD *)v10;
        v27[1] = *((_OWORD *)v10 + 1);
        *((_DWORD *)v27 + 8) = *((_DWORD *)v10 + 8);
      }
      else
      {
        *(_DWORD *)(a3 + 24) = *(_DWORD *)(v10 + 67);
      }
      ExFreePoolWithTag(v10, 0x74626146u);
      v10 = 0;
      v50 = 0;
      FatSetupAllocationSupport(a1, (int)p_Queue);
      if ( LOBYTE(p_Queue[5].Wcb.NumberOfChannels) == 32 )
      {
        if ( *((_WORD *)&p_Queue[4].Wcb.NumberOfMapRegisters + 2) >= WORD2(p_Queue[4].Wcb.DmaWaitEntry.Flink) )
          *((_WORD *)&p_Queue[4].Wcb.NumberOfMapRegisters + 2) = 0;
        *((_BYTE *)&p_Queue[17].Wcb.NumberOfMapRegisters + 6) = 1;
      }
      _InterlockedAnd((volatile signed __int32 *)&p_Queue[2].Wcb.CurrentIrp, 0xFFBFFFFF);
      if ( (byte_140017D4D & 2) != 0 && LOBYTE(p_Queue[5].Wcb.NumberOfChannels) != 12 )
        _InterlockedOr((volatile signed __int32 *)&p_Queue[2].Wcb.CurrentIrp, 0x400000u);
      FatCreateRootDcb(a1, p_Queue);
      FatLocateVolumeLabel(a1, (__int64)&SourceString);
      if ( !v54 )
      {
        *(_WORD *)(a3 + 6) = 0;
LABEL_58:
        p_Queue[15].Wcb.NumberOfMapRegisters = v46;
        for ( i = (__int64 *)qword_140017CB0; ; i = (__int64 *)*i )
        {
          *(_QWORD *)&SourceString.Length = i;
          if ( i == &qword_140017CB0 )
            break;
          v30 = i - 15;
          v55 = i - 15;
          v31 = i[9];
          v58 = v31;
          if ( v31 != a3
            && *(_DWORD *)(v31 + 24) == *(_DWORD *)(a3 + 24)
            && *((_DWORD *)v30 + 51) == 2
            && *(_QWORD *)(v31 + 16) == v45 )
          {
            v32 = *(_WORD *)(a3 + 6);
            if ( *(_WORD *)(v31 + 6) == v32 )
            {
              if ( !memcmp((const void *)(v31 + 32), (const void *)(a3 + 32), v32)
                && !memcmp(
                      v30 + 36,
                      &p_Queue[4],
                      (-(__int64)(HIWORD(p_Queue[4].Wcb.DmaWaitEntry.Blink) != 0) & 0xFFFFFFFFFFFFFFECuLL) + 48) )
              {
                p_Queue[1].Wcb.BufferChainingDpc = (PKDPC)v30[17];
                v30[17] = (__int64)DeviceObject;
                *((_DWORD *)v30 + 51) = 1;
                *(_QWORD *)(v31 + 16) = *(_QWORD *)(a3 + 16);
                _InterlockedAnd((volatile signed __int32 *)v30 + 50, 0xFFFDFFFF);
                *(_QWORD *)(*(_QWORD *)(v31 + 16) + 56LL) = v31;
                *((_DWORD *)v30 + 280) = p_Queue[15].Wcb.NumberOfMapRegisters;
                v34 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 184LL);
                if ( *(_QWORD *)(v34 + 8) == a3 )
                  *(_QWORD *)(v34 + 8) = v31;
                _InterlockedOr((volatile signed __int32 *)&p_Queue[2].Wcb.CurrentIrp, 0x40000u);
                HIDWORD(p_Queue[2].Wcb.CurrentIrp) = 3;
                *(_QWORD *)&v62[2] = 266240;
                *(_QWORD *)v62 = 266240;
                v63 = FatMaxLarge;
                LOBYTE(v33) = 1;
                FatInitializeCacheMap(v30[91], (int)v62, v33, (int)&qword_140017DB0, p_Queue);
                FatSetupAllocationSupport(a1, (int)v30);
                FatCheckDirtyBit(a1, v30);
                if ( (unsigned __int8)FatIsMediaWriteProtected(v35, DeviceObject) )
                  _InterlockedOr((volatile signed __int32 *)v30 + 50, 0x4000u);
                else
                  _InterlockedAnd((volatile signed __int32 *)v30 + 50, 0xFFFFBFFF);
                v14 = 0;
                goto LABEL_87;
              }
              i = *(__int64 **)&SourceString.Length;
            }
          }
        }
        if ( LOBYTE(p_Queue[5].Wcb.NumberOfChannels) != 32 )
        {
          v65[1] = 0;
          v65[0] = *(unsigned __int64 *)"EA DATA  SF";
          *(_DWORD *)((char *)v65 + 7) = *(_DWORD *)"  SF";
          Fcb = FatCreateFcb(
                  (_DWORD)i,
                  (_DWORD)p_Queue,
                  p_Queue[2].Wcb.BufferChainingDpc,
                  0,
                  0,
                  (__int64)v65,
                  0,
                  0,
                  0,
                  1);
          *(_DWORD *)(Fcb + 192) |= 0x80u;
          p_Queue[10].Wcb.BufferChainingDpc = (PKDPC)Fcb;
        }
        FatCheckDirtyBit(a1, p_Queue);
        *((_BYTE *)&p_Queue[17].Wcb.NumberOfMapRegisters + 4) = ((__int64)p_Queue[2].Wcb.CurrentIrp & 0x10) != 0;
        if ( (unsigned __int8)FatIsMediaWriteProtected(v37, DeviceObject) )
          _InterlockedOr((volatile signed __int32 *)&p_Queue[2].Wcb.CurrentIrp, 0x4000u);
        else
          _InterlockedAnd((volatile signed __int32 *)&p_Queue[2].Wcb.CurrentIrp, 0xFFFFBFFF);
        *((_BYTE *)&p_Queue[17].Wcb.NumberOfMapRegisters + 5) = ((__int64)p_Queue[2].Wcb.CurrentIrp & 0x4000) != 0;
        v40 = v45;
        if ( (*(_DWORD *)(v45 + 48) & 0x100) != 0 )
        {
          _InterlockedOr((volatile signed __int32 *)&p_Queue[2].Wcb.CurrentIrp, 0x800u);
          if ( ((__int64)p_Queue[2].Wcb.CurrentIrp & 2) != 0 )
          {
            LOBYTE(v39) = 1;
            FatToggleMediaEjectDisable(v38, p_Queue, v39);
          }
        }
        FatSqmVolumeInfo(v38, p_Queue);
        p_Queue[18].Wcb.DeviceContext = (PVOID)MEMORY[0xFFFFF78000000014];
        if ( (unsigned __int8)FatTelemetryGuard(p_Queue) )
          FatTelemetryMount(v41, p_Queue);
        v42 = 1;
        v14 = 0;
        DeferredRoutine = (struct _FILE_OBJECT *)p_Queue[2].Wcb.BufferChainingDpc[5].DeferredRoutine;
        ObfReferenceObject(DeferredRoutine);
        ObfDereferenceObject(DeviceObject);
        goto LABEL_89;
      }
      *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
      DestinationString = 0;
      SourceString.Buffer = v54;
      v28 = 11;
      *(_DWORD *)&SourceString.Length = 720907;
      while ( v28 && (v54[v28 - 1] & 0xDF) == 0 )
        SourceString.Length = --v28;
      DestinationString.MaximumLength = 64;
      DestinationString.Buffer = (PWSTR)((char *)p_Queue[2].Wcb.DeviceObject + 32);
      v14 = RtlOemStringToCountedUnicodeString(&DestinationString, &SourceString, 0);
      if ( v14 >= 0 )
      {
        *(_WORD *)(a3 + 6) = DestinationString.Length;
        goto LABEL_58;
      }
      goto LABEL_87;
    }
  }
  v14 = -1073741489;
LABEL_87:
  DeferredRoutine = v47;
LABEL_88:
  v40 = v45;
LABEL_89:
  if ( v10 )
    ExFreePoolWithTag(v10, 0x74626146u);
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( !v42 )
  {
    if ( p_Queue )
    {
      LOBYTE(v15) = 1;
      FatCheckForDismount(a1, p_Queue, v15);
      *(_QWORD *)(a1 + 56) = 0;
    }
    else if ( v44 )
    {
      IoDeleteDevice(v44);
    }
  }
  if ( v43 == 1 )
    *(_DWORD *)(v40 + 48) |= 2u;
  ExReleaseResourceLite(&Resource);
  if ( DeferredRoutine )
  {
    if ( FatDiskAccountingEnabled )
      CcSetAdditionalCacheAttributesEx(DeferredRoutine, 16);
    FsRtlNotifyVolumeEvent(DeferredRoutine, 6u);
    ObfDereferenceObject(DeferredRoutine);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140040674  push    rbx
0x140040676  push    rsi
0x140040677  push    rdi
0x140040678  push    r12
0x14004067a  push    r13
0x14004067c  push    r14
0x14004067e  push    r15
0x140040680  sub     rsp, 200h
0x140040687  mov     rax, cs:__security_cookie
0x14004068e  xor     rax, rsp
0x140040691  mov     [rsp+238h+var_48], rax
0x140040699  mov     r12, r8
0x14004069c  mov     r13, rdx
0x14004069f  mov     r15, rcx
0x1400406a2  mov     [rsp+238h+var_190], rcx
0x1400406aa  mov     rax, [rcx+28h]
0x1400406ae  mov     rbx, [rax+0B8h]
0x1400406b5  xor     edi, edi
0x1400406b7  mov     [rsp+238h+Bcb], rdi
0x1400406bc  mov     [rsp+238h+var_188], rdi
0x1400406c4  mov     dword ptr [rsp+238h+SourceString.Length], edi
0x1400406cb  mov     [rsp+238h+var_1E0], rdi
0x1400406d0  xorps   xmm0, xmm0
0x1400406d3  movups  [rsp+238h+var_168], xmm0
0x1400406db  mov     [rsp+238h+var_1D0], edi
0x1400406df  xorps   xmm1, xmm1
0x1400406e2  xor     eax, eax
0x1400406e4  movups  [rsp+238h+var_A8], xmm1
0x1400406ec  mov     [rsp+238h+var_98], rax
0x1400406f4  xor     edx, edx; Val
0x1400406f6  mov     r8d, 90h; Size
0x1400406fc  lea     rcx, [rsp+238h+var_148]; void *
0x140040704  call    memset
0x140040709  xorps   xmm0, xmm0
0x14004070c  movups  [rsp+238h+var_B8], xmm0
0x140040714  xorps   xmm1, xmm1
0x140040717  movups  [rsp+238h+var_78], xmm1
0x14004071f  mov     eax, [r13+34h]
0x140040723  lea     esi, [rdi+1]
0x140040726  test    sil, al
0x140040729  jz      short loc_140040792
0x14004072b  lea     rax, [rsp+238h+var_168]
0x140040733  mov     [rsp+238h+var_1F0], rax
0x140040738  mov     dword ptr [rsp+238h+DeviceObject], 4
0x140040740  lea     rax, [rsp+238h+var_1D0]
0x140040745  mov     qword ptr [rsp+238h+Exclusive], rax
0x14004074a  mov     r8, r13
0x14004074d  mov     edx, 74800h
0x140040752  call    FatPerformDevIoCtrl
0x140040757  test    eax, eax
0x140040759  jns     short loc_140040792
0x14004075b  test    [rbx+2], sil
0x14004075f  jnz     short loc_1400407B9
0x140040761  mov     rcx, [r12+10h]
0x140040766  cmp     dword ptr [rcx+48h], 7
0x14004076a  jnz     short loc_1400407B9
0x14004076c  mov     [r15+48h], eax
0x140040770  mov     edx, 0C00000E9h; GenericException
0x140040775  mov     ecx, eax; Exception
0x140040777  call    cs:__imp_FsRtlNormalizeNtstatus
0x14004077e  nop     dword ptr [rax+rax+00h]
0x140040783  mov     ecx, eax; Status
0x140040785  call    cs:__imp_ExRaiseStatus
0x140040792  cmp     qword ptr [rsp+238h+var_168+8], 4
0x14004079b  jz      short loc_1400407A1
0x14004079d  mov     [rsp+238h+var_1D0], edi
0x1400407a1  cmp     dword ptr [r13+48h], 2
0x1400407a6  jnz     short loc_1400407DD
0x1400407a8  mov     rdx, r13
0x1400407ab  call    FatScanForDataTrack
0x1400407b0  test    al, al
0x1400407b2  jnz     short loc_1400407DD
0x1400407b4  mov     eax, 0C000014Fh
0x1400407b9  mov     rcx, [rsp+238h+var_48]
0x1400407c1  xor     rcx, rsp; StackCookie
0x1400407c4  call    __security_check_cookie
0x1400407c9  add     rsp, 200h
0x1400407d0  pop     r15
0x1400407d2  pop     r14
0x1400407d4  pop     r13
0x1400407d6  pop     r12
0x1400407d8  pop     rdi
0x1400407d9  pop     rsi
0x1400407da  pop     rbx
0x1400407db  retn
0x1400407dd  mov     rsi, rdi
0x1400407e0  mov     [rsp+238h+var_1A8], rdi
0x1400407e8  mov     [rsp+238h+var_1E7], dil
0x1400407ed  mov     [rsp+238h+var_1E6], dil
0x1400407f2  mov     [rsp+238h+var_180], rdi
0x1400407fa  mov     [rsp+238h+var_1D8], rdi
0x1400407ff  mov     r14, rdi
0x140040802  mov     [rsp+238h+var_1C8], rdi
0x140040807  lea     rax, [rsp+238h+var_168]
0x14004080f  mov     [rsp+238h+var_1F0], rax
0x140040814  mov     dword ptr [rsp+238h+DeviceObject], 90h
0x14004081c  lea     rax, [rsp+238h+var_148]
0x140040824  mov     qword ptr [rsp+238h+Exclusive], rax
0x140040829  mov     r8, r13
0x14004082c  mov     edx, 70048h
0x140040831  call    FatPerformDevIoCtrl
0x140040836  mov     [rsp+238h+var_1A0], eax
0x14004083d  or      dword ptr [r15+44h], 2
0x140040842  mov     rcx, r15
0x140040845  call    FatScanForDismountedVcb
0x14004084a  mov     [rsp+238h+Bcb], rdi
0x14004084f  mov     rbx, rdi
0x140040852  mov     [rsp+238h+var_198], rbx
0x14004085a  mov     [rsp+238h+var_1E0], rdi
0x14004085f  mov     [rsp+238h+var_1E8], dil
0x140040864  mov     edx, [r15+44h]
0x140040868  shr     edx, 1
0x14004086a  and     dl, 1; Wait
0x14004086d  lea     rcx, Resource; Resource
0x140040874  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004087b  nop     dword ptr [rax+rax+00h]
0x140040880  mov     [rsp+238h+var_1F0], rdi
0x140040885  mov     dword ptr [rsp+238h+DeviceObject], 18h
0x14004088d  lea     rax, [rsp+238h+var_A8]
0x140040895  mov     qword ptr [rsp+238h+Exclusive], rax
0x14004089a  mov     r8, r13
0x14004089d  mov     edx, 70000h
0x1400408a2  call    FatPerformDevIoCtrl
0x1400408a7  mov     edi, eax
0x1400408a9  test    eax, eax
0x1400408ab  js      loc_1400411BA
0x1400408b1  movzx   r14d, word ptr [rsp+238h+var_98+4]
0x1400408ba  lea     edi, [r14+0FFFh]
0x1400408c1  mov     eax, 0FFFFF000h
0x1400408c6  and     rdi, rax
0x1400408c9  mov     r8d, 74626146h; Tag
0x1400408cf  mov     rdx, rdi; NumberOfBytes
0x1400408d2  mov     ecx, 610h; PoolType
0x1400408d7  call    cs:__imp_ExAllocatePoolWithTag
0x1400408de  nop     dword ptr [rax+rax+00h]
0x1400408e3  mov     rsi, rax
0x1400408e6  xor     ecx, ecx
0x1400408e8  cmp     cs:ExPoolZeroingNativelySupported, cl
0x1400408ee  jnz     short loc_140040902
0x1400408f0  test    rax, rax
0x1400408f3  jz      short loc_140040902
0x1400408f5  mov     r8, rdi; Size
0x1400408f8  xor     edx, edx; Val
0x1400408fa  mov     rcx, rax; void *
0x1400408fd  call    memset
0x140040902  mov     [rsp+238h+var_1A8], rsi
0x14004090a  mov     r8, rsi; Buffer
0x14004090d  mov     edx, r14d; Length
0x140040910  mov     rcx, r13; DeviceObject
0x140040913  call    FatReadBootSector
0x140040918  xor     r14d, r14d
0x14004091b  test    al, al
0x14004091d  jnz     short loc_140040929
0x14004091f  mov     edi, 0C000014Fh
0x140040924  jmp     loc_1400411BF
0x140040929  mov     rcx, rsi
0x14004092c  call    FatIsBootSectorFat
0x140040931  test    al, al
0x140040933  jz      short loc_14004091F
0x140040935  lea     rax, [rsp+238h+var_1E0]
0x14004093a  mov     [rsp+238h+DeviceObject], rax; DeviceObject
0x14004093f  mov     [rsp+238h+Exclusive], r14b; Exclusive
0x140040944  mov     [rsp+238h+DeviceCharacteristics], r14d; DeviceCharacteristics
0x140040949  mov     r9d, 8; DeviceType
0x14004094f  xor     r8d, r8d; DeviceName
0x140040952  mov     edx, 5A0h; DeviceExtensionSize
0x140040957  mov     rcx, cs:DriverObject; DriverObject
0x14004095e  call    cs:__imp_IoCreateDevice
0x140040965  nop     dword ptr [rax+rax+00h]
0x14004096a  mov     edi, eax
0x14004096c  test    eax, eax
0x14004096e  js      loc_1400411BF
0x140040974  mov     ecx, [r13+98h]
0x14004097b  mov     rax, [rsp+238h+var_1E0]
0x140040980  cmp     ecx, [rax+98h]
0x140040986  jbe     short loc_140040993
0x140040988  mov     [rax+98h], ecx
0x14004098e  mov     rax, [rsp+238h+var_1E0]
0x140040993  mov     [rax+154h], r14d
0x14004099a  mov     rax, [rsp+238h+var_1E0]
0x14004099f  add     rax, 158h
0x1400409a5  mov     [rax+8], rax
0x1400409a9  mov     [rax], rax
0x1400409ac  mov     rax, [rsp+238h+var_1E0]
0x1400409b1  mov     [rax+150h], r14d
0x1400409b8  mov     rcx, [rsp+238h+var_1E0]
0x1400409bd  add     rcx, 168h; SpinLock
0x1400409c4  call    cs:__imp_KeInitializeSpinLock
0x1400409cb  nop     dword ptr [rax+rax+00h]
0x1400409d0  mov     cl, [r13+4Ch]
0x1400409d4  inc     cl
0x1400409d6  mov     rax, [rsp+238h+var_1E0]
0x1400409db  mov     [rax+4Ch], cl
0x1400409de  mov     ecx, dword ptr [rsp+238h+var_98+4]
0x1400409e5  mov     rax, [rsp+238h+var_1E0]
0x1400409ea  mov     [rax+130h], cx
0x1400409f1  mov     rax, [rsp+238h+var_1E0]
0x1400409f6  btr     dword ptr [rax+30h], 7
0x1400409fb  mov     rax, [rsp+238h+var_1E0]
0x140040a00  mov     [r12+8], rax
0x140040a05  mov     rdi, [r12+10h]
0x140040a0a  mov     [rsp+238h+var_1D8], rdi
0x140040a0f  mov     eax, [rdi+30h]
0x140040a12  test    al, 2
0x140040a14  jz      short loc_140040A28
0x140040a16  and     eax, 0FFFFFFFDh
0x140040a19  mov     [rdi+30h], eax
0x140040a1c  mov     edi, 1
0x140040a21  mov     [rsp+238h+var_1E7], dil
0x140040a26  jmp     short loc_140040A2D
0x140040a28  mov     edi, 1
0x140040a2d  mov     rdx, [rsp+238h+var_1E0]
0x140040a32  add     rdx, 1A0h
0x140040a39  mov     r9, r12
0x140040a3c  mov     r8, r13
0x140040a3f  mov     rcx, r15
0x140040a42  call    FatInitializeVcb
0x140040a47  mov     rbx, [rsp+238h+var_1E0]
0x140040a4c  add     rbx, 1A0h
0x140040a53  mov     [rsp+238h+var_198], rbx
0x140040a5b  lea     rdx, [rsp+238h+var_B8]
0x140040a63  mov     rcx, [rbx+88h]
0x140040a6a  call    cs:__imp_IoVolumeDeviceToGuid
0x140040a71  nop     dword ptr [rax+rax+00h]
0x140040a76  test    eax, eax
0x140040a78  js      short loc_140040A9A
0x140040a7a  movups  xmm0, [rsp+238h+var_B8]
0x140040a82  movdqu  xmmword ptr [rbx+4E4h], xmm0
0x140040a8a  movups  xmm1, [rsp+238h+var_B8]
0x140040a92  movdqu  xmmword ptr [rbx+90h], xmm1
0x140040a9a  lea     rdx, [rsp+238h+var_78]
0x140040aa2  mov     rcx, [rbx+88h]
0x140040aa9  call    cs:__imp_FsRtlVolumeDeviceToCorrelationId
0x140040ab0  nop     dword ptr [rax+rax+00h]
0x140040ab5  test    eax, eax
0x140040ab7  js      short loc_140040AC9
0x140040ab9  movups  xmm0, [rsp+238h+var_78]
0x140040ac1  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x140040ac9  mov     rcx, [rbx+0A8h]; P
0x140040ad0  test    rcx, rcx
0x140040ad3  jz      short loc_140040AF1
0x140040ad5  xor     edx, edx; Tag
0x140040ad7  call    cs:__imp_ExFreePoolWithTag
0x140040ade  nop     dword ptr [rax+rax+00h]
0x140040ae3  mov     [rbx+0A8h], r14
0x140040aea  mov     [rbx+0A0h], r14d
0x140040af1  lea     rdx, [rbx+0A0h]
0x140040af8  mov     rcx, [rbx+88h]
0x140040aff  call    cs:__imp_IoVolumeDeviceToGuidPath
0x140040b06  nop     dword ptr [rax+rax+00h]
0x140040b0b  movzx   edx, word ptr [rsi+0Bh]
0x140040b0f  mov     [rbx+120h], dx
0x140040b16  mov     al, [rsi+0Dh]
0x140040b19  mov     [rbx+122h], al
0x140040b1f  movzx   eax, word ptr [rsi+0Eh]
0x140040b23  mov     [rbx+124h], ax
0x140040b2a  mov     al, [rsi+10h]
0x140040b2d  mov     [rbx+126h], al
0x140040b33  movzx   eax, word ptr [rsi+11h]
0x140040b37  mov     [rbx+128h], ax
0x140040b3e  movzx   ecx, word ptr [rsi+13h]
0x140040b42  mov     [rbx+12Ah], cx
0x140040b49  mov     al, [rsi+15h]
0x140040b4c  mov     [rbx+12Ch], al
0x140040b52  movzx   eax, word ptr [rsi+16h]
0x140040b56  mov     [rbx+12Eh], ax
0x140040b5d  movzx   eax, word ptr [rsi+18h]
0x140040b61  mov     [rbx+130h], ax
0x140040b68  movzx   eax, word ptr [rsi+1Ah]
0x140040b6c  mov     [rbx+132h], ax
0x140040b73  mov     eax, [rsi+1Ch]
0x140040b76  mov     [rbx+134h], eax
0x140040b7c  mov     eax, [rsi+20h]
0x140040b7f  mov     [rbx+138h], eax
0x140040b85  mov     eax, [rsi+24h]
0x140040b88  mov     [rbx+13Ch], eax
0x140040b8e  movzx   eax, word ptr [rsi+28h]
0x140040b92  mov     [rbx+140h], ax
0x140040b99  movzx   eax, word ptr [rsi+2Ah]
0x140040b9d  mov     [rbx+144h], ax
0x140040ba4  mov     eax, [rsi+2Ch]
0x140040ba7  mov     [rbx+148h], eax
0x140040bad  movzx   eax, word ptr [rsi+30h]
0x140040bb1  mov     [rbx+14Ch], ax
0x140040bb8  movzx   eax, word ptr [rsi+32h]
0x140040bbc  mov     [rbx+14Eh], ax
0x140040bc3  cmp     [rsp+238h+var_1A0], r14d
0x140040bcb  jl      short loc_140040BF1
0x140040bcd  cmp     [rsp+238h+var_148], r14d
0x140040bd5  jnz     short loc_140040BF1
0x140040bd7  cmp     [rsp+238h+var_128], 0Ah
0x140040bdf  jnz     short loc_140040BF1
0x140040be1  movzx   eax, cx
0x140040be4  sub     ax, di
0x140040be7  cmp     ax, 7Eh ; '~'
0x140040beb  jbe     loc_14004091F
0x140040bf1  mov     eax, edx
0x140040bf3  cmp     dword ptr [rsp+238h+var_98+4], edx
0x140040bfa  jnz     loc_14004091F
0x140040c00  test    cx, cx
  ... truncated ...
```
