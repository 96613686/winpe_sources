# SubmitPresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN const *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,CWin32kLocks *,int,_LARGE_INTEGER *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,char const *)

- ea: `0x14038fb34`
- end: `0x140391551`
- name: `?SubmitPresentHistoryToken@@YAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCWin32kLocks@@HPEAT_LARGE_INTEGER@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEBD@Z`
- size: `6685`
- prototype: `int(const struct _D3DKMT_PRESENTHISTORYTOKEN *, struct COREDEVICEACCESS *, struct DXGADAPTERSTOPRESETLOCKSHARED *, struct CWin32kLocks *, int, union _LARGE_INTEGER *, struct DXGK_PRESENT_PARAMS *, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT *, struct _PRESENT_REDIRECTED_PARAMS *, const char *)`
- caller_count: `9`
- callee_count: `56`
- tags: ``

## callers

- `0x140254210`
- `0x140256830`
- `0x14031d764`
- `0x14032c648`
- `0x140385120`
- `0x14038e0b0`
- `0x14038f680`
- `0x140398fc0`
- `0x14039aac0`

## callees

- `0x14000d9c0`
- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x140015a70`
- `0x140015f7c`
- `0x140016388`
- `0x1400169f0`
- `0x14001a38c`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001d9cc`
- `0x14001e254`
- `0x14001f2f0`
- `0x14002dbc0`
- `0x14002dc10`
- `0x14002e330`
- `0x14002e3b0`
- `0x14002ff90`
- `0x140030a30`
- `0x140033da4`
- `0x140034080`
- `0x140034910`
- `0x140037ef0`
- `0x1400438dc`
- `0x1400461e8`
- `0x140048a5c`
- `0x140049424`
- `0x140059738`
- `0x140060238`
- `0x14006e1e8`
- `0x140075f74`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x14018b340`
- `0x140194bbc`
- `0x1402557c4`
- `0x14031a444`
- `0x140329ff0`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x1403345d0`
- `0x14033464c`
- `0x14035f384`
- `0x14037aab4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140390da6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140390f84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140391193`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140390da6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140390f84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140391193`
- `ntoskrnl!ExFreePoolWithTag` at `0x140390c0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140390d69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140390c0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140390d69`
- `ntoskrnl!ExAllocatePool2` at `0x140390add`
- `ntoskrnl!ExAllocatePool2` at `0x140390add`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140390d9a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140390f78`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140391187`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140390d9a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140390f78`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140391187`
- `ntoskrnl!ObfDereferenceObject` at `0x14038fda7`
- `ntoskrnl!ObfDereferenceObject` at `0x140390117`
- `ntoskrnl!ObfDereferenceObject` at `0x14039023a`
- `ntoskrnl!ObfDereferenceObject` at `0x140391429`
- `ntoskrnl!ObfDereferenceObject` at `0x1403914c5`
- `ntoskrnl!ObfDereferenceObject` at `0x14038fda7`
- `ntoskrnl!ObfDereferenceObject` at `0x140390117`
- `ntoskrnl!ObfDereferenceObject` at `0x14039023a`
- `ntoskrnl!ObfDereferenceObject` at `0x140391429`
- `ntoskrnl!ObfDereferenceObject` at `0x1403914c5`
- `ntoskrnl!ObfReferenceObject` at `0x14038fce0`
- `ntoskrnl!ObfReferenceObject` at `0x14038fce0`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14038fd67`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14039005e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14038fd67`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14039005e`
- `ntoskrnl!KeReleaseSemaphore` at `0x140390155`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403901d7`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403902d9`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403912e2`
- `ntoskrnl!KeReleaseSemaphore` at `0x140391410`
- `ntoskrnl!KeReleaseSemaphore` at `0x140391463`
- `ntoskrnl!KeReleaseSemaphore` at `0x140390155`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403901d7`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403902d9`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403912e2`
- `ntoskrnl!KeReleaseSemaphore` at `0x140391410`
- `ntoskrnl!KeReleaseSemaphore` at `0x140391463`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1403902bd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1403902bd`
- `watchdog!WdIsDebuggerPresent` at `0x14038fe55`
- `watchdog!WdIsDebuggerPresent` at `0x14038fe55`
- `watchdog!WdLogSingleEntry2` at `0x140390dc8`
- `watchdog!WdLogSingleEntry2` at `0x140390faa`
- `watchdog!WdLogSingleEntry2` at `0x14039147a`
- `watchdog!WdLogSingleEntry2` at `0x140390dc8`
- `watchdog!WdLogSingleEntry2` at `0x140390faa`
- `watchdog!WdLogSingleEntry2` at `0x14039147a`
- `watchdog!WdLogSingleEntry0` at `0x14038fc32`
- `watchdog!WdLogSingleEntry0` at `0x14038fff3`
- `watchdog!WdLogSingleEntry0` at `0x1403901e6`
- `watchdog!WdLogSingleEntry0` at `0x140390cf0`
- `watchdog!WdLogSingleEntry0` at `0x140390e63`
- `watchdog!WdLogSingleEntry0` at `0x140390f17`
- `watchdog!WdLogSingleEntry0` at `0x140391111`
- `watchdog!WdLogSingleEntry0` at `0x14038fc32`
- `watchdog!WdLogSingleEntry0` at `0x14038fff3`
- `watchdog!WdLogSingleEntry0` at `0x1403901e6`
- `watchdog!WdLogSingleEntry0` at `0x140390cf0`
- `watchdog!WdLogSingleEntry0` at `0x140390e63`
- `watchdog!WdLogSingleEntry0` at `0x140390f17`
- `watchdog!WdLogSingleEntry0` at `0x140391111`
- `watchdog!WdLogSingleEntry1` at `0x14038fbc7`
- `watchdog!WdLogSingleEntry1` at `0x14038fcba`
- `watchdog!WdLogSingleEntry1` at `0x14038fd7d`
- `watchdog!WdLogSingleEntry1` at `0x140390078`
- `watchdog!WdLogSingleEntry1` at `0x1403900c2`
- `watchdog!WdLogSingleEntry1` at `0x1403900f8`
- `watchdog!WdLogSingleEntry1` at `0x140390169`
- `watchdog!WdLogSingleEntry1` at `0x1403902f2`
- `watchdog!WdLogSingleEntry1` at `0x1403903bc`
- `watchdog!WdLogSingleEntry1` at `0x140390a4f`
- `watchdog!WdLogSingleEntry1` at `0x1403913ed`
- `watchdog!WdLogSingleEntry1` at `0x1403914e5`
- `watchdog!WdLogSingleEntry1` at `0x14038fbc7`
- `watchdog!WdLogSingleEntry1` at `0x14038fcba`
- `watchdog!WdLogSingleEntry1` at `0x14038fd7d`
- `watchdog!WdLogSingleEntry1` at `0x140390078`
- `watchdog!WdLogSingleEntry1` at `0x1403900c2`
- `watchdog!WdLogSingleEntry1` at `0x1403900f8`
- `watchdog!WdLogSingleEntry1` at `0x140390169`
- `watchdog!WdLogSingleEntry1` at `0x1403902f2`
- `watchdog!WdLogSingleEntry1` at `0x1403903bc`
- `watchdog!WdLogSingleEntry1` at `0x140390a4f`
- `watchdog!WdLogSingleEntry1` at `0x1403913ed`
- `watchdog!WdLogSingleEntry1` at `0x1403914e5`

## string_xrefs

- `0x1403903d9`: `Failed to read private driver data. Returning 0x%I64x`
- `0x140390a6c`: `Failed to create present sync object. Returning 0x%I64x`
- `0x140390004`: `Present token is not submitted due to default semaphore timeout of 20 seconds`
- `0x140391497`: `Present token is not submitted due to no memory, PresentHistoryTokenQueue: 0x%I64x, returning 0x%I64x`

## pseudocode

```c

```
