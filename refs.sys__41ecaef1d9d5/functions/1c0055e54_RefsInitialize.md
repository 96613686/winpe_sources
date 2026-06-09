# RefsInitialize

- ea: `0x1c0055e54`
- end: `0x1c005654e`
- name: `RefsInitialize`
- size: `1786`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c01d7324`

## callees

- `0x1c0054b90`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c0056278`
- `ntoskrnl!CcMapData` at `0x1c0055fb4`
- `ntoskrnl!CcPreparePinWrite` at `0x1c0055fbf`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0056031`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1c0056132`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c005603c`
- `ntoskrnl!DbgPrintEx` at `0x1c005652e`
- `ntoskrnl!DbgPrintEx` at `0x1c005652e`
- `ntoskrnl!CcUnpinData` at `0x1c0055fca`
- `ntoskrnl!CcUnmapFileOffsetFromSystemCache` at `0x1c0055fd5`
- `ntoskrnl!CcAddDirtyPagesToExternalCache` at `0x1c00562b0`
- `ntoskrnl!CcDeductDirtyPagesFromExternalCache` at `0x1c00562be`
- `ntoskrnl!CcRegisterExternalCache` at `0x1c00562cc`
- `ntoskrnl!CcUnregisterExternalCache` at `0x1c00562da`

## pseudocode

```c
__int64 RefsInitialize()
{
  unsigned int v0; // ebx
  _QWORD v2[128]; // [rsp+20h] [rbp-E0h] BYREF

  memset(v2, 0, sizeof(v2));
  HIDWORD(v2[0]) = RefsRotationIOGranularityInBytes;
  LOBYTE(v2[1]) = RefsDisableFlushAndTrimOnRotation;
  BYTE4(v2[3]) = RefsEnableLargeWorkingSetTrim;
  LODWORD(v2[4]) = RefsNumberOfChunksToTrim;
  BYTE5(v2[3]) = RefsEnableInlineTrim;
  BYTE2(v2[3]) = RefsDisableCachedPins;
  BYTE3(v2[3]) = RefsDisableContainersCompaction;
  BYTE1(v2[1]) = RefsEnableSMRSimulation;
  HIDWORD(v2[1]) = RefsBandSizeOnSimulatedSMR;
  LODWORD(v2[2]) = RefsCMRRegionOnSimulatedSMR;
  BYTE4(v2[2]) = RefsMakeAllFilesSMRBlob;
  HIBYTE(v2[2]) = RefsDisableRedoLogReplay;
  BYTE4(v2[4]) = RefsDisableUserDataTriage;
  BYTE5(v2[2]) = RefsFailUnorderedSMRIO;
  BYTE6(v2[2]) = RefsDeferSMRWriteHeadQuery;
  BYTE5(v2[4]) = RefsFullBandAllocationOnTieredVolume;
  BYTE6(v2[4]) = RefsEnableParallelContainerRotation;
  v2[5] = __PAIR64__(RefsContainerRotationQueueSizeLimit, RefsContainerRotationThreadCount);
  LOBYTE(v2[6]) = RefsReallocateAllDataWrites;
  BYTE1(v2[6]) = RefsDisableWriteCombining;
  BYTE2(v2[6]) = RefsEnableTrimOnAllMediaTypes;
  v2[7] = MsKmeLockPages;
  v2[8] = MsKmeUnlockPages;
  v2[9] = MsKmeCreateCacheContext;
  v2[10] = MsKmeReleaseCacheContext;
  v2[11] = MsKmeInitializeCache;
  v2[12] = MsKmeUninitializeCache;
  v2[13] = MsKmeReferenceObject;
  v2[14] = MsKmeDereferenceObject;
  v2[15] = CcMapData;
  v2[16] = CcPreparePinWrite;
  v2[17] = CcUnpinData;
  v2[18] = CcUnmapFileOffsetFromSystemCache;
  v2[19] = MsKmeSetCacheFileSizes;
  v2[20] = MsKmeFlushCache;
  v2[21] = &MsKmePurgeCache;
  LODWORD(v2[0]) = 9;
  LOWORD(v2[3]) = 257;
  v2[22] = MsKmePrefetchPages;
  v2[23] = MsKmeGetCurrentCheckSumTypes;
  v2[24] = MsKmeSetCurrentCheckSumTypes;
  v2[25] = IoGetTopLevelIrp;
  v2[26] = IoSetTopLevelIrp;
  v2[27] = MsKmeIncrementCloseCount;
  v2[28] = MsKmeDecrementCloseCount;
  v2[31] = MsKmeSynchronousRead;
  v2[32] = MsKmeSynchronousWrite;
  v2[45] = MsKmeInitializeSMRSim;
  v2[46] = MsKmeResetSMRSimBand;
  v2[47] = MsKmeGetSMRBandWriteHead;
  v2[48] = MsKmeGetSMRBandSize;
  v2[49] = MsKmeZeroSMRRegion;
  v2[33] = MsKmeSynchronousReadCopy;
  v2[34] = MsKmeSynchronousRepairFromCopy;
  v2[35] = MsKmeSynchronousScrubPickingWinners;
  v2[36] = MsKmeReturnNumberDataCopies;
  v2[37] = MsKmeReturnPowerProtectedMode;
  v2[38] = MsKmeQueryRangeInDrt;
  v2[39] = MsKmeQueryTopologyId;
  v2[40] = MsKmeUntrim;
  v2[41] = MsKmeGetRowSizeAndOffset;
  v2[42] = MsKmeFlushDisk;
  v2[43] = MsKmeQueryAllocationHint;
  v2[44] = KeExpandKernelStackAndCalloutEx;
  HIDWORD(v2[96]) = RefsLazyWriterAggresiveBindableThreshold;
  v2[97] = __PAIR64__(RefsLazyWriterLogWorkersPerVolume, RefsLazyWriterWorkersPerVolume);
  v2[98] = __PAIR64__(RefsLazyWriterLogWorkersTotal, RefsLazyWriterWorkersTotal);
  LODWORD(v2[99]) = RefsLazyWriterScanThresholdPerVolume;
  v2[100] = __PAIR64__(RefsProcessedDeleteQueueThresholdBindable, RefsProcessedDeleteQueueThresholdCheckpoint);
  v2[105] = __PAIR64__(RefsBlockRefcountColdDelay, RefsBlockRefcountScanPeriod);
  v2[106] = __PAIR64__(RefsBlockRefcountCacheHighWaterMark, RefsBlockRefcountEmptyColdDelay);
  v2[107] = MsKmeAllocateIoRequest;
  v2[109] = MsKmeAllocateIoRun;
  v2[110] = MsKmeSetIoRun;
  v2[108] = MsKmeReleaseIoRequest;
  v2[111] = MsKmeSubmitIoRequest;
  v2[112] = MsKmeWaitIoRequest;
  v2[113] = MsKmeResetIoRequest;
  v2[117] = MsKmeSetCallbackIoRequest;
  v2[118] = MsKmeGetCallbackIoRequest;
  v2[114] = MsKmeGetRun;
  v2[115] = MsKmeGetRunCount;
  v2[116] = MsKmeGetAvailableRunCount;
  v2[50] = FsRtlIsNtstatusExpected;
  v2[51] = MsKmeGetObjectRecordPayload;
  v2[52] = MsKmeUpdateBootSector;
  v2[60] = MsKmeTrimRangesSync;
  v2[55] = CcAddDirtyPagesToExternalCache;
  v2[56] = CcDeductDirtyPagesFromExternalCache;
  v2[53] = CcRegisterExternalCache;
  v2[54] = CcUnregisterExternalCache;
  v2[57] = MsKmeChecksumEventNotification;
  v2[59] = MsKmeMetadataEventNotification;
  v2[58] = MsKmeLogEventNotification;
  v2[65] = MsKmeQueryStorageSeekPenalty;
  v2[66] = MsKmeQueryStorageSSDOrNVMe;
  v2[67] = MsKmeQueryStorageSMR;
  v2[68] = MsKmeQueryStorageClasses;
  v2[69] = MsKmeQueryStorageTier;
  v2[70] = MsKmeGenericSpacesRequest;
  v2[71] = MsKmeTierMoveEventNotification;
  v2[72] = MsKmeTelemetry;
  v2[73] = MsKmeTraceInitFail;
  v2[74] = MsKmeTraceFastTierFullRatio;
  v2[75] = MsKmeQueryStreamsParameters;
  v2[78] = MsKmeSetStreamIdForMetadata;
  v2[79] = MsKmeSetStreamIdForLog;
  v2[76] = MsKmeQueryStreamIdForMetadata;
  v2[77] = MsKmeQueryStreamIdForLog;
  v2[80] = MsKmeQueryAndCacheSmrBandInfoForRange;
  v2[81] = MsKmeGetSMRBandWriteHeadFromCache;
  v2[82] = MsKmeClearSmrBandInfoCache;
  v2[83] = MsKmeGetNumberOfMappedPages;
  LOBYTE(v2[84]) = RefsEnableRefcountRangeLock;
  v2[85] = FsLibInitializeRangeLock;
  v2[86] = FsLibUninitializeRangeLock;
  v2[87] = FsLibLockRange;
  v2[88] = FsLibUnlockRange;
  v2[89] = FsLibUnlockRangeExclusive;
  v2[90] = FsLibUnlockRangeShared;
  v2[91] = MsKmeAcquireRangeLock;
  v2[92] = MsKmeReleaseRangeLock;
  v2[93] = MsKmeQueryCpuInformation;
  v2[94] = MsKmeFailIncompleteLogRedo;
  v2[119] = MsKmeMapRange;
  v2[120] = &MsKmeUnmapRanges;
  v2[121] = MsKmeQueryMapAllocations;
  v2[122] = MsKmeQueryThinProvisioning;
  v2[124] = MsKmeCreateBaseAddressFromTuple;
  v2[125] = CmsFailoverBPlusTable::DefaultCleanup;
  v2[126] = &MsKmeFreeBaseAddressFromTuple;
  v0 = MsInitializeLibrary(v2);
  DbgPrintEx(0x65u, 0, "refs.sys loaded.\n");
  return v0;
}

```

## disassembly

```asm
0x1c0055e54  mov     [rsp-8+arg_0], rbx
0x1c0055e59  push    rbp
0x1c0055e5a  lea     rbp, [rsp-320h]
0x1c0055e62  sub     rsp, 420h
0x1c0055e69  xor     edx, edx; Val
0x1c0055e6b  lea     rcx, [rsp+420h+var_400]; void *
0x1c0055e70  mov     r8d, 400h; Size
0x1c0055e76  call    memset
0x1c0055e7b  mov     eax, cs:RefsRotationIOGranularityInBytes
0x1c0055e81  mov     [rsp+420h+var_3FC], eax
0x1c0055e85  mov     al, cs:RefsDisableFlushAndTrimOnRotation
0x1c0055e8b  mov     [rsp+420h+var_3F8], al
0x1c0055e8f  mov     al, cs:RefsEnableLargeWorkingSetTrim
0x1c0055e95  mov     [rsp+420h+var_3E4], al
0x1c0055e99  mov     eax, cs:RefsNumberOfChunksToTrim
0x1c0055e9f  mov     [rsp+420h+var_3E0], eax
0x1c0055ea3  mov     al, cs:RefsEnableInlineTrim
0x1c0055ea9  mov     [rsp+420h+var_3E3], al
0x1c0055ead  mov     al, cs:RefsDisableCachedPins
0x1c0055eb3  mov     [rsp+420h+var_3E6], al
0x1c0055eb7  mov     al, cs:RefsDisableContainersCompaction
0x1c0055ebd  mov     [rsp+420h+var_3E5], al
0x1c0055ec1  mov     al, cs:RefsEnableSMRSimulation
0x1c0055ec7  mov     [rsp+420h+var_3F7], al
0x1c0055ecb  mov     eax, cs:RefsBandSizeOnSimulatedSMR
0x1c0055ed1  mov     [rsp+420h+var_3F4], eax
0x1c0055ed5  mov     eax, cs:RefsCMRRegionOnSimulatedSMR
0x1c0055edb  mov     [rsp+420h+var_3F0], eax
0x1c0055edf  mov     al, cs:RefsMakeAllFilesSMRBlob
0x1c0055ee5  mov     [rsp+420h+var_3EC], al
0x1c0055ee9  mov     al, cs:RefsDisableRedoLogReplay
0x1c0055eef  mov     [rsp+420h+var_3E9], al
0x1c0055ef3  mov     al, cs:RefsDisableUserDataTriage
0x1c0055ef9  mov     [rsp+420h+var_3DC], al
0x1c0055efd  mov     al, cs:RefsFailUnorderedSMRIO
0x1c0055f03  mov     [rsp+420h+var_3EB], al
0x1c0055f07  mov     al, cs:RefsDeferSMRWriteHeadQuery
0x1c0055f0d  mov     [rsp+420h+var_3EA], al
0x1c0055f11  mov     al, cs:RefsFullBandAllocationOnTieredVolume
0x1c0055f17  mov     [rsp+420h+var_3DB], al
0x1c0055f1b  mov     al, cs:RefsEnableParallelContainerRotation
0x1c0055f21  mov     [rsp+420h+var_3DA], al
0x1c0055f25  mov     eax, cs:RefsContainerRotationThreadCount
0x1c0055f2b  mov     [rsp+420h+var_3D8], eax
0x1c0055f2f  mov     eax, cs:RefsContainerRotationQueueSizeLimit
0x1c0055f35  mov     [rsp+420h+var_3D4], eax
0x1c0055f39  mov     al, cs:RefsReallocateAllDataWrites
0x1c0055f3f  mov     [rsp+420h+var_3D0], al
0x1c0055f43  mov     al, cs:RefsDisableWriteCombining
0x1c0055f49  mov     [rsp+420h+var_3CF], al
0x1c0055f4d  mov     al, cs:RefsEnableTrimOnAllMediaTypes
0x1c0055f53  mov     [rsp+420h+var_3CE], al
0x1c0055f57  lea     rax, MsKmeLockPages
0x1c0055f5e  mov     [rsp+420h+var_3C8], rax
0x1c0055f63  lea     rax, MsKmeUnlockPages
0x1c0055f6a  mov     [rsp+420h+var_3C0], rax
0x1c0055f6f  lea     rax, MsKmeCreateCacheContext
0x1c0055f76  mov     [rsp+420h+var_3B8], rax
0x1c0055f7b  lea     rax, MsKmeReleaseCacheContext
0x1c0055f82  mov     [rsp+420h+var_3B0], rax
0x1c0055f87  lea     rax, MsKmeInitializeCache
0x1c0055f8e  mov     [rsp+420h+var_3A8], rax
0x1c0055f93  lea     rax, MsKmeUninitializeCache
0x1c0055f9a  mov     [rbp+320h+var_3A0], rax
0x1c0055f9e  lea     rax, MsKmeReferenceObject
0x1c0055fa5  mov     [rbp+320h+var_398], rax
0x1c0055fa9  lea     rax, MsKmeDereferenceObject
0x1c0055fb0  mov     [rbp+320h+var_390], rax
0x1c0055fb4  mov     rax, cs:__imp_CcMapData
0x1c0055fbb  mov     [rbp+320h+var_388], rax
0x1c0055fbf  mov     rax, cs:__imp_CcPreparePinWrite
0x1c0055fc6  mov     [rbp+320h+var_380], rax
0x1c0055fca  mov     rax, cs:__imp_CcUnpinData
0x1c0055fd1  mov     [rbp+320h+var_378], rax
0x1c0055fd5  mov     rax, cs:__imp_CcUnmapFileOffsetFromSystemCache
0x1c0055fdc  mov     [rbp+320h+var_370], rax
0x1c0055fe0  lea     rax, MsKmeSetCacheFileSizes
0x1c0055fe7  mov     [rbp+320h+var_368], rax
0x1c0055feb  lea     rax, MsKmeFlushCache
0x1c0055ff2  mov     [rbp+320h+var_360], rax
0x1c0055ff6  lea     rax, MsKmePurgeCache
0x1c0055ffd  mov     [rbp+320h+var_358], rax
0x1c0056001  lea     rax, MsKmePrefetchPages
0x1c0056008  mov     [rsp+420h+var_400], 9
0x1c0056010  mov     [rsp+420h+var_3E8], 101h
0x1c0056017  mov     [rbp+320h+var_350], rax
0x1c005601b  lea     rax, MsKmeGetCurrentCheckSumTypes
0x1c0056022  mov     [rbp+320h+var_348], rax
0x1c0056026  lea     rax, MsKmeSetCurrentCheckSumTypes
0x1c005602d  mov     [rbp+320h+var_340], rax
0x1c0056031  mov     rax, cs:__imp_IoGetTopLevelIrp
0x1c0056038  mov     [rbp+320h+var_338], rax
0x1c005603c  mov     rax, cs:__imp_IoSetTopLevelIrp
0x1c0056043  mov     [rbp+320h+var_330], rax
0x1c0056047  lea     rax, MsKmeIncrementCloseCount
0x1c005604e  mov     [rbp+320h+var_328], rax
0x1c0056052  lea     rax, MsKmeDecrementCloseCount
0x1c0056059  mov     [rbp+320h+var_320], rax
0x1c005605d  lea     rax, MsKmeSynchronousRead
0x1c0056064  mov     [rbp+320h+var_308], rax
0x1c0056068  lea     rax, MsKmeSynchronousWrite
0x1c005606f  mov     [rbp+320h+var_300], rax
0x1c0056073  lea     rax, MsKmeInitializeSMRSim
0x1c005607a  mov     [rbp+320h+var_298], rax
0x1c0056081  lea     rax, MsKmeResetSMRSimBand
0x1c0056088  mov     [rbp+320h+var_290], rax
0x1c005608f  lea     rax, MsKmeGetSMRBandWriteHead
0x1c0056096  mov     [rbp+320h+var_288], rax
0x1c005609d  lea     rax, MsKmeGetSMRBandSize
0x1c00560a4  mov     [rbp+320h+var_280], rax
0x1c00560ab  lea     rax, MsKmeZeroSMRRegion
0x1c00560b2  mov     [rbp+320h+var_278], rax
0x1c00560b9  lea     rax, MsKmeSynchronousReadCopy
0x1c00560c0  mov     [rbp+320h+var_2F8], rax
0x1c00560c4  lea     rax, MsKmeSynchronousRepairFromCopy
0x1c00560cb  mov     [rbp+320h+var_2F0], rax
0x1c00560cf  lea     rax, MsKmeSynchronousScrubPickingWinners
0x1c00560d6  mov     [rbp+320h+var_2E8], rax
0x1c00560da  lea     rax, MsKmeReturnNumberDataCopies
0x1c00560e1  mov     [rbp+320h+var_2E0], rax
0x1c00560e5  lea     rax, MsKmeReturnPowerProtectedMode
0x1c00560ec  mov     [rbp+320h+var_2D8], rax
0x1c00560f0  lea     rax, MsKmeQueryRangeInDrt
0x1c00560f7  mov     [rbp+320h+var_2D0], rax
0x1c00560fb  lea     rax, MsKmeQueryTopologyId
0x1c0056102  mov     [rbp+320h+var_2C8], rax
0x1c0056106  lea     rax, MsKmeUntrim
0x1c005610d  mov     [rbp+320h+var_2C0], rax
0x1c0056111  lea     rax, MsKmeGetRowSizeAndOffset
0x1c0056118  mov     [rbp+320h+var_2B8], rax
0x1c005611c  lea     rax, MsKmeFlushDisk
0x1c0056123  mov     [rbp+320h+var_2B0], rax
0x1c0056127  lea     rax, MsKmeQueryAllocationHint
0x1c005612e  mov     [rbp+320h+var_2A8], rax
0x1c0056132  mov     rax, cs:__imp_KeExpandKernelStackAndCalloutEx
0x1c0056139  mov     [rbp+320h+var_2A0], rax
0x1c0056140  mov     eax, cs:RefsLazyWriterAggresiveBindableThreshold
0x1c0056146  mov     [rbp+320h+var_FC], eax
0x1c005614c  mov     eax, cs:RefsLazyWriterWorkersPerVolume
0x1c0056152  mov     [rbp+320h+var_F8], eax
0x1c0056158  mov     eax, cs:RefsLazyWriterLogWorkersPerVolume
0x1c005615e  mov     [rbp+320h+var_F4], eax
0x1c0056164  mov     eax, cs:RefsLazyWriterWorkersTotal
0x1c005616a  mov     [rbp+320h+var_F0], eax
0x1c0056170  mov     eax, cs:RefsLazyWriterLogWorkersTotal
0x1c0056176  mov     [rbp+320h+var_EC], eax
0x1c005617c  mov     eax, cs:RefsLazyWriterScanThresholdPerVolume
0x1c0056182  mov     [rbp+320h+var_E8], eax
0x1c0056188  mov     eax, cs:RefsProcessedDeleteQueueThresholdCheckpoint
0x1c005618e  mov     [rbp+320h+var_E0], eax
0x1c0056194  mov     eax, cs:RefsProcessedDeleteQueueThresholdBindable
0x1c005619a  mov     [rbp+320h+var_DC], eax
0x1c00561a0  mov     eax, cs:RefsBlockRefcountScanPeriod
0x1c00561a6  mov     [rbp+320h+var_B8], eax
0x1c00561ac  mov     eax, cs:RefsBlockRefcountColdDelay
0x1c00561b2  mov     [rbp+320h+var_B4], eax
0x1c00561b8  mov     eax, cs:RefsBlockRefcountEmptyColdDelay
0x1c00561be  mov     [rbp+320h+var_B0], eax
0x1c00561c4  mov     eax, cs:RefsBlockRefcountCacheHighWaterMark
0x1c00561ca  mov     [rbp+320h+var_AC], eax
0x1c00561d0  lea     rax, MsKmeAllocateIoRequest
0x1c00561d7  mov     [rbp+320h+var_A8], rax
0x1c00561de  lea     rax, MsKmeAllocateIoRun
0x1c00561e5  mov     [rbp+320h+var_98], rax
0x1c00561ec  lea     rax, MsKmeSetIoRun
0x1c00561f3  mov     [rbp+320h+var_90], rax
0x1c00561fa  lea     rax, MsKmeReleaseIoRequest
0x1c0056201  mov     [rbp+320h+var_A0], rax
0x1c0056208  lea     rax, MsKmeSubmitIoRequest
0x1c005620f  mov     [rbp+320h+var_88], rax
0x1c0056216  lea     rax, MsKmeWaitIoRequest
0x1c005621d  mov     [rbp+320h+var_80], rax
0x1c0056224  lea     rax, MsKmeResetIoRequest
0x1c005622b  mov     [rbp+320h+var_78], rax
0x1c0056232  lea     rax, MsKmeSetCallbackIoRequest
0x1c0056239  mov     [rbp+320h+var_58], rax
0x1c0056240  lea     rax, MsKmeGetCallbackIoRequest
0x1c0056247  mov     [rbp+320h+var_50], rax
0x1c005624e  lea     rax, MsKmeGetRun
0x1c0056255  mov     [rbp+320h+var_70], rax
0x1c005625c  lea     rax, MsKmeGetRunCount
0x1c0056263  mov     [rbp+320h+var_68], rax
0x1c005626a  lea     rax, MsKmeGetAvailableRunCount
0x1c0056271  mov     [rbp+320h+var_60], rax
0x1c0056278  mov     rax, cs:__imp_FsRtlIsNtstatusExpected
0x1c005627f  mov     [rbp+320h+var_270], rax
0x1c0056286  lea     rax, MsKmeGetObjectRecordPayload
0x1c005628d  mov     [rbp+320h+var_268], rax
0x1c0056294  lea     rax, MsKmeUpdateBootSector
0x1c005629b  mov     [rbp+320h+var_260], rax
0x1c00562a2  lea     rax, MsKmeTrimRangesSync
0x1c00562a9  mov     [rbp+320h+var_220], rax
0x1c00562b0  mov     rax, cs:__imp_CcAddDirtyPagesToExternalCache
0x1c00562b7  mov     [rbp+320h+var_248], rax
0x1c00562be  mov     rax, cs:__imp_CcDeductDirtyPagesFromExternalCache
0x1c00562c5  mov     [rbp+320h+var_240], rax
0x1c00562cc  mov     rax, cs:__imp_CcRegisterExternalCache
0x1c00562d3  mov     [rbp+320h+var_258], rax
0x1c00562da  mov     rax, cs:__imp_CcUnregisterExternalCache
0x1c00562e1  mov     [rbp+320h+var_250], rax
0x1c00562e8  lea     rax, MsKmeChecksumEventNotification
0x1c00562ef  mov     [rbp+320h+var_238], rax
0x1c00562f6  lea     rax, MsKmeMetadataEventNotification
0x1c00562fd  mov     [rbp+320h+var_228], rax
0x1c0056304  lea     rax, MsKmeLogEventNotification
0x1c005630b  mov     [rbp+320h+var_230], rax
0x1c0056312  lea     rax, MsKmeQueryStorageSeekPenalty
0x1c0056319  mov     [rbp+320h+var_1F8], rax
0x1c0056320  lea     rax, MsKmeQueryStorageSSDOrNVMe
0x1c0056327  mov     [rbp+320h+var_1F0], rax
0x1c005632e  lea     rax, MsKmeQueryStorageSMR
0x1c0056335  mov     [rbp+320h+var_1E8], rax
0x1c005633c  lea     rax, MsKmeQueryStorageClasses
0x1c0056343  mov     [rbp+320h+var_1E0], rax
0x1c005634a  lea     rax, MsKmeQueryStorageTier
0x1c0056351  mov     [rbp+320h+var_1D8], rax
0x1c0056358  lea     rax, MsKmeGenericSpacesRequest
0x1c005635f  mov     [rbp+320h+var_1D0], rax
0x1c0056366  lea     rax, MsKmeTierMoveEventNotification
0x1c005636d  mov     [rbp+320h+var_1C8], rax
0x1c0056374  lea     rax, MsKmeTelemetry
0x1c005637b  mov     [rbp+320h+var_1C0], rax
0x1c0056382  lea     rax, MsKmeTraceInitFail
0x1c0056389  mov     [rbp+320h+var_1B8], rax
0x1c0056390  lea     rax, MsKmeTraceFastTierFullRatio
0x1c0056397  mov     [rbp+320h+var_1B0], rax
0x1c005639e  lea     rax, MsKmeQueryStreamsParameters
0x1c00563a5  mov     [rbp+320h+var_1A8], rax
0x1c00563ac  lea     rax, MsKmeSetStreamIdForMetadata
0x1c00563b3  mov     [rbp+320h+var_190], rax
0x1c00563ba  lea     rax, MsKmeSetStreamIdForLog
0x1c00563c1  mov     [rbp+320h+var_188], rax
0x1c00563c8  lea     rax, MsKmeQueryStreamIdForMetadata
0x1c00563cf  mov     [rbp+320h+var_1A0], rax
0x1c00563d6  lea     rax, MsKmeQueryStreamIdForLog
0x1c00563dd  mov     [rbp+320h+var_198], rax
0x1c00563e4  lea     rax, MsKmeQueryAndCacheSmrBandInfoForRange
0x1c00563eb  mov     [rbp+320h+var_180], rax
0x1c00563f2  lea     rax, MsKmeGetSMRBandWriteHeadFromCache
0x1c00563f9  mov     [rbp+320h+var_178], rax
0x1c0056400  lea     rax, MsKmeClearSmrBandInfoCache
0x1c0056407  mov     [rbp+320h+var_170], rax
0x1c005640e  lea     rax, MsKmeGetNumberOfMappedPages
0x1c0056415  mov     [rbp+320h+var_168], rax
0x1c005641c  mov     al, cs:RefsEnableRefcountRangeLock
0x1c0056422  mov     [rbp+320h+var_160], al
0x1c0056428  lea     rax, FsLibInitializeRangeLock
0x1c005642f  mov     [rbp+320h+var_158], rax
0x1c0056436  lea     rcx, [rsp+420h+var_400]
0x1c005643b  lea     rax, FsLibUninitializeRangeLock
0x1c0056442  mov     [rbp+320h+var_150], rax
0x1c0056449  lea     rax, FsLibLockRange
0x1c0056450  mov     [rbp+320h+var_148], rax
0x1c0056457  lea     rax, FsLibUnlockRange
0x1c005645e  mov     [rbp+320h+var_140], rax
0x1c0056465  lea     rax, FsLibUnlockRangeExclusive
0x1c005646c  mov     [rbp+320h+var_138], rax
0x1c0056473  lea     rax, FsLibUnlockRangeShared
0x1c005647a  mov     [rbp+320h+var_130], rax
0x1c0056481  lea     rax, MsKmeAcquireRangeLock
0x1c0056488  mov     [rbp+320h+var_128], rax
0x1c005648f  lea     rax, MsKmeReleaseRangeLock
0x1c0056496  mov     [rbp+320h+var_120], rax
0x1c005649d  lea     rax, MsKmeQueryCpuInformation
0x1c00564a4  mov     [rbp+320h+var_118], rax
0x1c00564ab  lea     rax, MsKmeFailIncompleteLogRedo
0x1c00564b2  mov     [rbp+320h+var_110], rax
0x1c00564b9  lea     rax, MsKmeMapRange
0x1c00564c0  mov     [rbp+320h+var_48], rax
0x1c00564c7  lea     rax, MsKmeUnmapRanges
0x1c00564ce  mov     [rbp+320h+var_40], rax
0x1c00564d5  lea     rax, MsKmeQueryMapAllocations
0x1c00564dc  mov     [rbp+320h+var_38], rax
0x1c00564e3  lea     rax, MsKmeQueryThinProvisioning
0x1c00564ea  mov     [rbp+320h+var_30], rax
0x1c00564f1  lea     rax, MsKmeCreateBaseAddressFromTuple
0x1c00564f8  mov     [rbp+320h+var_20], rax
0x1c00564ff  lea     rax, ?DefaultCleanup@CmsFailoverBPlusTable@@AEAAXPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAU_MS_FAILOVER_INTERNAL_PARAMETER@1@@Z; CmsFailoverBPlusTable::DefaultCleanup(CmsTransactionContext *,CmsBPlusTable *,CmsFailoverBPlusTable::_MS_FAILOVER_INTERNAL_PARAMETER *)
0x1c0056506  mov     [rbp+320h+var_18], rax
0x1c005650d  lea     rax, MsKmeFreeBaseAddressFromTuple
0x1c0056514  mov     [rbp+320h+var_10], rax
0x1c005651b  call    MsInitializeLibrary
0x1c0056520  xor     edx, edx; Level
0x1c0056522  lea     r8, aRefsSysLoaded; "refs.sys loaded.\n"
0x1c0056529  mov     ebx, eax
0x1c005652b  lea     ecx, [rdx+65h]; ComponentId
0x1c005652e  call    cs:__imp_DbgPrintEx
0x1c0056535  nop     dword ptr [rax+rax+00h]
0x1c005653a  mov     eax, ebx
0x1c005653c  mov     rbx, [rsp+420h+arg_0]
0x1c0056544  add     rsp, 420h
0x1c005654b  pop     rbp
0x1c005654c  retn
```
