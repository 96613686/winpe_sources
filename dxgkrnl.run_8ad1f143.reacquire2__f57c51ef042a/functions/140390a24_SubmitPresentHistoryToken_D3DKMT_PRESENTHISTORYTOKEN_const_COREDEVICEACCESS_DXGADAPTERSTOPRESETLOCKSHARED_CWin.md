# SubmitPresentHistoryToken(_D3DKMT_PRESENTHISTORYTOKEN const *,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,CWin32kLocks *,int,_LARGE_INTEGER *,DXGK_PRESENT_PARAMS *,VIDSCH_SUBMIT_DATA_BASE *,DXGCONTEXT *,_PRESENT_REDIRECTED_PARAMS *,char const *)

- ea: `0x140390a24`
- end: `0x140392453`
- name: `?SubmitPresentHistoryToken@@YAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCWin32kLocks@@HPEAT_LARGE_INTEGER@@PEAUDXGK_PRESENT_PARAMS@@PEAUVIDSCH_SUBMIT_DATA_BASE@@PEAVDXGCONTEXT@@PEAU_PRESENT_REDIRECTED_PARAMS@@PEBD@Z`
- size: `6703`
- prototype: `int(const struct _D3DKMT_PRESENTHISTORYTOKEN *, struct COREDEVICEACCESS *, struct DXGADAPTERSTOPRESETLOCKSHARED *, struct CWin32kLocks *, int, union _LARGE_INTEGER *, struct DXGK_PRESENT_PARAMS *, struct VIDSCH_SUBMIT_DATA_BASE *, struct DXGCONTEXT *, struct _PRESENT_REDIRECTED_PARAMS *, const char *)`
- caller_count: `8`
- callee_count: `54`
- tags: ``

## callers

- `0x140250c30`
- `0x1403169f4`
- `0x1403258d8`
- `0x140342930`
- `0x14038efe0`
- `0x140390570`
- `0x1403981e0`
- `0x140399ce0`

## callees

- `0x14000d800`
- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400158b0`
- `0x140015dbc`
- `0x1400161c8`
- `0x140016830`
- `0x14001a2ec`
- `0x14001ab20`
- `0x14001b890`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001d7fc`
- `0x14001e084`
- `0x14001f120`
- `0x14002d9f0`
- `0x14002da40`
- `0x14002e160`
- `0x14002e1e0`
- `0x14002fdc0`
- `0x140030860`
- `0x140033bd4`
- `0x140033eb0`
- `0x140034740`
- `0x140037d20`
- `0x14004367c`
- `0x140045f88`
- `0x14004885c`
- `0x140049224`
- `0x1400594c8`
- `0x14005fe88`
- `0x1400758d4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x140187340`
- `0x140190bbc`
- `0x1403136d4`
- `0x140323280`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x14032d860`
- `0x14032d8dc`
- `0x14035eed4`
- `0x140388a64`
- `0x140389e1c`
- `0x140390a24`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140391cb0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140391ea7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403920ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140391cb0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140391ea7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403920ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140391b25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140391c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140391b25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140391c73`
- `ntoskrnl!ExAllocatePool2` at `0x1403919f6`
- `ntoskrnl!ExAllocatePool2` at `0x1403919f6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140391ca4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140391e9b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403920a1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140391ca4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140391e9b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403920a1`
- `ntoskrnl!ObfDereferenceObject` at `0x140390caf`
- `ntoskrnl!ObfDereferenceObject` at `0x14039101f`
- `ntoskrnl!ObfDereferenceObject` at `0x140391142`
- `ntoskrnl!ObfDereferenceObject` at `0x14039232b`
- `ntoskrnl!ObfDereferenceObject` at `0x1403923c7`
- `ntoskrnl!ObfDereferenceObject` at `0x140390caf`
- `ntoskrnl!ObfDereferenceObject` at `0x14039101f`
- `ntoskrnl!ObfDereferenceObject` at `0x140391142`
- `ntoskrnl!ObfDereferenceObject` at `0x14039232b`
- `ntoskrnl!ObfDereferenceObject` at `0x1403923c7`
- `ntoskrnl!ObfReferenceObject` at `0x140390be8`
- `ntoskrnl!ObfReferenceObject` at `0x140390be8`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140390c6f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140390f66`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140390c6f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140390f66`
- `ntoskrnl!KeReleaseSemaphore` at `0x14039105d`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403910df`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403911e1`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403921e4`
- `ntoskrnl!KeReleaseSemaphore` at `0x140392312`
- `ntoskrnl!KeReleaseSemaphore` at `0x140392365`
- `ntoskrnl!KeReleaseSemaphore` at `0x14039105d`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403910df`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403911e1`
- `ntoskrnl!KeReleaseSemaphore` at `0x1403921e4`
- `ntoskrnl!KeReleaseSemaphore` at `0x140392312`
- `ntoskrnl!KeReleaseSemaphore` at `0x140392365`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1403911c5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1403911c5`
- `watchdog!WdIsDebuggerPresent` at `0x140390d5d`
- `watchdog!WdIsDebuggerPresent` at `0x140390d5d`
- `watchdog!WdLogSingleEntry2` at `0x140391cd2`
- `watchdog!WdLogSingleEntry2` at `0x140391ecd`
- `watchdog!WdLogSingleEntry2` at `0x14039237c`
- `watchdog!WdLogSingleEntry2` at `0x140391cd2`
- `watchdog!WdLogSingleEntry2` at `0x140391ecd`
- `watchdog!WdLogSingleEntry2` at `0x14039237c`
- `watchdog!WdLogSingleEntry0` at `0x140390b37`
- `watchdog!WdLogSingleEntry0` at `0x140390efb`
- `watchdog!WdLogSingleEntry0` at `0x1403910ee`
- `watchdog!WdLogSingleEntry0` at `0x140391bfb`
- `watchdog!WdLogSingleEntry0` at `0x140391d6f`
- `watchdog!WdLogSingleEntry0` at `0x140391e30`
- `watchdog!WdLogSingleEntry0` at `0x14039202c`
- `watchdog!WdLogSingleEntry0` at `0x140390b37`
- `watchdog!WdLogSingleEntry0` at `0x140390efb`
- `watchdog!WdLogSingleEntry0` at `0x1403910ee`
- `watchdog!WdLogSingleEntry0` at `0x140391bfb`
- `watchdog!WdLogSingleEntry0` at `0x140391d6f`
- `watchdog!WdLogSingleEntry0` at `0x140391e30`
- `watchdog!WdLogSingleEntry0` at `0x14039202c`
- `watchdog!WdLogSingleEntry1` at `0x140390ab7`
- `watchdog!WdLogSingleEntry1` at `0x140390bc2`
- `watchdog!WdLogSingleEntry1` at `0x140390c85`
- `watchdog!WdLogSingleEntry1` at `0x140390f80`
- `watchdog!WdLogSingleEntry1` at `0x140390fca`
- `watchdog!WdLogSingleEntry1` at `0x140391000`
- `watchdog!WdLogSingleEntry1` at `0x140391071`
- `watchdog!WdLogSingleEntry1` at `0x1403911fa`
- `watchdog!WdLogSingleEntry1` at `0x1403912d5`
- `watchdog!WdLogSingleEntry1` at `0x14039195a`
- `watchdog!WdLogSingleEntry1` at `0x1403922ef`
- `watchdog!WdLogSingleEntry1` at `0x1403923e7`
- `watchdog!WdLogSingleEntry1` at `0x140390ab7`
- `watchdog!WdLogSingleEntry1` at `0x140390bc2`
- `watchdog!WdLogSingleEntry1` at `0x140390c85`
- `watchdog!WdLogSingleEntry1` at `0x140390f80`
- `watchdog!WdLogSingleEntry1` at `0x140390fca`
- `watchdog!WdLogSingleEntry1` at `0x140391000`
- `watchdog!WdLogSingleEntry1` at `0x140391071`
- `watchdog!WdLogSingleEntry1` at `0x1403911fa`
- `watchdog!WdLogSingleEntry1` at `0x1403912d5`
- `watchdog!WdLogSingleEntry1` at `0x14039195a`
- `watchdog!WdLogSingleEntry1` at `0x1403922ef`
- `watchdog!WdLogSingleEntry1` at `0x1403923e7`

## string_xrefs

- `0x1403912ea`: `Failed to read private driver data. Returning 0x%I64x`
- `0x14039196f`: `Failed to create present sync object. Returning 0x%I64x`
- `0x140390f0c`: `Present token is not submitted due to default semaphore timeout of 20 seconds`
- `0x140392399`: `Present token is not submitted due to no memory, PresentHistoryTokenQueue: 0x%I64x, returning 0x%I64x`

## pseudocode

```c

```
