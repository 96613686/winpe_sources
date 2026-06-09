# SubmitPresentHistoryTokenPreparation(DXGADAPTERSTOPRESETLOCKSHARED *,COREDEVICEACCESS *,DXGADAPTER *,_D3DKMT_PRESENTHISTORYTOKEN *,void *,bool)

- ea: `0x14038f1bc`
- end: `0x14038f593`
- name: `?SubmitPresentHistoryTokenPreparation@@YAJPEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTER@@PEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAX_N@Z`
- size: `983`
- prototype: `__int64 __fastcall(struct DXGADAPTERSTOPRESETLOCKSHARED *this, struct COREDEVICEACCESS *, struct DXGADAPTER *, struct _D3DKMT_PRESENTHISTORYTOKEN *, __int64 Handle, bool)`
- caller_count: `5`
- callee_count: `19`
- tags: ``

## callers

- `0x140256830`
- `0x140385120`
- `0x14038e0b0`
- `0x140398fc0`
- `0x14039aac0`

## callees

- `0x14001055c`
- `0x140012540`
- `0x140015a70`
- `0x140015f7c`
- `0x1400169f0`
- `0x14001a38c`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x14001f2f0`
- `0x140033da4`
- `0x140034910`
- `0x140047990`
- `0x140048a5c`
- `0x14018a824`
- `0x14032a5c4`
- `0x14038f1bc`
- `0x14038f59c`
- `0x14038f62c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14038f20b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14038f20b`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f37a`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f3d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f491`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f4bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f37a`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f3d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f491`
- `ntoskrnl!ObfDereferenceObject` at `0x14038f4bb`
- `ntoskrnl!PsGetProcessSessionId` at `0x14038f21a`
- `ntoskrnl!PsGetProcessSessionId` at `0x14038f21a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14038f337`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14038f424`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14038f337`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14038f424`
- `ntoskrnl!ExSemaphoreObjectType` at `0x14038f3fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14038f47b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14038f4ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x14038f47b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14038f4ac`
- `watchdog!WdLogSingleEntry1` at `0x14038f43f`
- `watchdog!WdLogSingleEntry1` at `0x14038f4e4`
- `watchdog!WdLogSingleEntry1` at `0x14038f519`
- `watchdog!WdLogSingleEntry1` at `0x14038f578`
- `watchdog!WdLogSingleEntry1` at `0x14038f43f`
- `watchdog!WdLogSingleEntry1` at `0x14038f4e4`
- `watchdog!WdLogSingleEntry1` at `0x14038f519`
- `watchdog!WdLogSingleEntry1` at `0x14038f578`

## pseudocode

```c

```
