# SubmitPresentHistoryTokenPreparation(DXGADAPTERSTOPRESETLOCKSHARED *,COREDEVICEACCESS *,DXGADAPTER *,_D3DKMT_PRESENTHISTORYTOKEN *,void *,bool)

- ea: `0x1403900b4`
- end: `0x14039048b`
- name: `?SubmitPresentHistoryTokenPreparation@@YAJPEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAVCOREDEVICEACCESS@@PEAVDXGADAPTER@@PEAU_D3DKMT_PRESENTHISTORYTOKEN@@PEAX_N@Z`
- size: `983`
- prototype: `__int64 __usercall@<rax>(struct DXGADAPTERSTOPRESETLOCKSHARED *this@<rcx>, struct COREDEVICEACCESS *@<rdx>, struct DXGADAPTER *@<r8>, struct _D3DKMT_PRESENTHISTORYTOKEN *@<r9>, void *, bool)`
- caller_count: `4`
- callee_count: `19`
- tags: ``

## callers

- `0x140342930`
- `0x14038efe0`
- `0x1403981e0`
- `0x140399ce0`

## callees

- `0x14001039c`
- `0x140012380`
- `0x1400158b0`
- `0x140015dbc`
- `0x140016830`
- `0x14001a2ec`
- `0x14001ab20`
- `0x14001b890`
- `0x14001d070`
- `0x14001f120`
- `0x140033bd4`
- `0x140034740`
- `0x140047790`
- `0x14004885c`
- `0x140186824`
- `0x140323854`
- `0x1403900b4`
- `0x140390494`
- `0x140390524`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140390103`
- `ntoskrnl!PsGetCurrentProcess` at `0x140390103`
- `ntoskrnl!ObfDereferenceObject` at `0x140390272`
- `ntoskrnl!ObfDereferenceObject` at `0x1403902cf`
- `ntoskrnl!ObfDereferenceObject` at `0x140390389`
- `ntoskrnl!ObfDereferenceObject` at `0x1403903b3`
- `ntoskrnl!ObfDereferenceObject` at `0x140390272`
- `ntoskrnl!ObfDereferenceObject` at `0x1403902cf`
- `ntoskrnl!ObfDereferenceObject` at `0x140390389`
- `ntoskrnl!ObfDereferenceObject` at `0x1403903b3`
- `ntoskrnl!PsGetProcessSessionId` at `0x140390112`
- `ntoskrnl!PsGetProcessSessionId` at `0x140390112`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14039022f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14039031c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14039022f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14039031c`
- `ntoskrnl!ExSemaphoreObjectType` at `0x1403902f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140390373`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403903a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140390373`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403903a4`
- `watchdog!WdLogSingleEntry1` at `0x140390337`
- `watchdog!WdLogSingleEntry1` at `0x1403903dc`
- `watchdog!WdLogSingleEntry1` at `0x140390411`
- `watchdog!WdLogSingleEntry1` at `0x140390470`
- `watchdog!WdLogSingleEntry1` at `0x140390337`
- `watchdog!WdLogSingleEntry1` at `0x1403903dc`
- `watchdog!WdLogSingleEntry1` at `0x140390411`
- `watchdog!WdLogSingleEntry1` at `0x140390470`

## pseudocode

```c

```
