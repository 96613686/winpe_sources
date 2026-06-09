# VfMiscPluginEntry

- ea: `0x140bdc060`
- end: `0x140bdcd40`
- name: `VfMiscPluginEntry`
- size: `3296`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14053fcf0`
- `0x14063a0ac`
- `0x14064219c`
- `0x1406dc8c0`
- `0x140bd91f4`
- `0x140bdc060`
- `0x140bdec04`

## string_xrefs

- `0x140bdc18f`: `ExInitializeNPagedLookasideList`
- `0x140bdc1b0`: `ExInitializePagedLookasideList`
- `0x140bdc1da`: `ExDeletePagedLookasideList`
- `0x140bdc27b`: `ExDeleteNPagedLookasideList`
- `0x140bdc16e`: `ExInitializeLookasideListEx`
- `0x140bdc58f`: `KeRemoveQueueDpc`
- `0x140bdc369`: `ObGetObjectSecurity`
- `0x140bdc297`: `ExDeleteLookasideListEx`
- `0x140bdca86`: `ExReleaseResourceForThreadLite`
- `0x140bdc780`: `ExDeleteResourceLite`

## pseudocode

```c

```

## disassembly

```asm
0x140bdc060  push    rbp
0x140bdc062  push    rbx
0x140bdc063  push    rsi
0x140bdc064  push    rdi
0x140bdc065  lea     rbp, [rsp-7F8h]
0x140bdc06d  sub     rsp, 8F8h
0x140bdc074  mov     rax, cs:__security_cookie
0x140bdc07b  xor     rax, rsp
0x140bdc07e  mov     [rbp+810h+var_30], rax
0x140bdc085  xor     esi, esi
0x140bdc087  mov     [rsp+910h+var_8E8], 0EEh
0x140bdc08f  lea     rax, VfMiscPluginUnload
0x140bdc096  mov     [rsp+910h+var_8D8], rsi
0x140bdc09b  mov     cs:qword_140EF2048, rax
0x140bdc0a2  lea     rax, aMmallocatecont_2; "MmAllocateContiguousMemory"
0x140bdc0a9  mov     [rsp+910h+var_8F0], rax
0x140bdc0ae  lea     rax, VfMiscMmAllocateContiguousMemory_Entry
0x140bdc0b5  mov     [rsp+910h+var_8E0], rax
0x140bdc0ba  lea     rax, aMmallocatecont_1; "MmAllocateContiguousMemoryEx"
0x140bdc0c1  mov     [rsp+910h+var_8D0], rax
0x140bdc0c6  lea     rax, VfMiscMmAllocateContiguousMemoryEx_Entry
0x140bdc0cd  mov     [rsp+910h+var_8C0], rax
0x140bdc0d2  lea     rax, aKereleasequeue_0; "KeReleaseQueuedSpinLock"
0x140bdc0d9  mov     [rsp+910h+var_8B0], rax
0x140bdc0de  lea     rax, VfMiscKeReleaseQueuedSpinLock_Entry
0x140bdc0e5  mov     [rsp+910h+var_8A0], rax
0x140bdc0ea  lea     rax, aKeinitializeev_0; "KeInitializeEvent"
0x140bdc0f1  mov     [rbp+810h+var_890], rax
0x140bdc0f5  lea     rax, VfMiscKeInitializeEvent_Entry
0x140bdc0fc  mov     [rbp+810h+var_880], rax
0x140bdc100  lea     rax, aKeinitializemu_1; "KeInitializeMutant"
0x140bdc107  mov     [rbp+810h+var_870], rax
0x140bdc10b  lea     rax, VfMiscKeInitializeMutant_Entry
0x140bdc112  mov     [rbp+810h+var_860], rax
0x140bdc116  lea     rax, aKeinitializemu_2; "KeInitializeMutex"
0x140bdc11d  mov     [rbp+810h+var_850], rax
0x140bdc121  lea     rax, VfMiscKeInitializeMutant_Entry
0x140bdc128  mov     [rbp+810h+var_840], rax
0x140bdc12c  lea     rax, aKeinitializeti_1; "KeInitializeTimerEx"
0x140bdc133  mov     [rbp+810h+var_830], rax
0x140bdc137  lea     rax, VfMiscKeInitializeTimerEx_Entry
0x140bdc13e  mov     [rbp+810h+var_820], rax
0x140bdc142  lea     rax, aKewaitforsingl; "KeWaitForSingleObject"
0x140bdc149  mov     [rbp+810h+var_810], rax
0x140bdc14d  lea     rax, VfMiscKeWaitForSingleObject_Entry
0x140bdc154  mov     [rbp+810h+var_800], rax
0x140bdc158  lea     rax, aKewaitformulti; "KeWaitForMultipleObjects"
0x140bdc15f  mov     [rbp+810h+var_7F0], rax
0x140bdc163  lea     rax, VfMiscKeWaitForMultipleObjects_Entry
0x140bdc16a  mov     [rbp+810h+var_7E0], rax
0x140bdc16e  lea     rax, aExinitializelo_0; "ExInitializeLookasideListEx"
0x140bdc175  mov     [rbp+810h+var_7D0], rax
0x140bdc179  lea     rax, VfMiscExInitializeLookasideListEx_Entry
0x140bdc180  mov     [rbp+810h+var_7C0], rax
0x140bdc184  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bdc18b  mov     [rbp+810h+var_7B8], rax
0x140bdc18f  lea     rax, aExinitializenp; "ExInitializeNPagedLookasideList"
0x140bdc196  mov     [rbp+810h+var_7B0], rax
0x140bdc19a  lea     rax, VfMiscExInitializeNPagedLookasideList_Entry
0x140bdc1a1  mov     [rbp+810h+var_7A0], rax
0x140bdc1a5  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bdc1ac  mov     [rbp+810h+var_798], rax
0x140bdc1b0  lea     rax, aExinitializepa_0; "ExInitializePagedLookasideList"
0x140bdc1b7  mov     [rbp+810h+var_790], rax
0x140bdc1be  lea     rax, VfMiscExInitializeNPagedLookasideList_Entry
0x140bdc1c5  mov     [rbp+810h+var_780], rax
0x140bdc1cc  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bdc1d3  mov     [rbp+810h+var_778], rax
0x140bdc1da  lea     rax, aExdeletepagedl_0; "ExDeletePagedLookasideList"
0x140bdc1e1  mov     [rbp+810h+var_770], rax
0x140bdc1e8  mov     [rsp+910h+var_8C8], 0EDh
0x140bdc1f0  mov     [rsp+910h+var_8B8], rsi
0x140bdc1f5  mov     [rsp+910h+var_8A8], 104h
0x140bdc1fd  mov     [rsp+910h+var_898], rsi
0x140bdc202  mov     [rbp+810h+var_888], 11Ch
0x140bdc209  mov     [rbp+810h+var_878], rsi
0x140bdc20d  mov     [rbp+810h+var_868], 11Bh
0x140bdc214  mov     [rbp+810h+var_858], rsi
0x140bdc218  mov     [rbp+810h+var_848], 11Ah
0x140bdc21f  mov     [rbp+810h+var_838], rsi
0x140bdc223  mov     [rbp+810h+var_828], 117h
0x140bdc22a  mov     [rbp+810h+var_818], rsi
0x140bdc22e  mov     [rbp+810h+var_808], 0F0h
0x140bdc235  mov     [rbp+810h+var_7F8], rsi
0x140bdc239  mov     [rbp+810h+var_7E8], 0F1h
0x140bdc240  mov     [rbp+810h+var_7D8], rsi
0x140bdc244  mov     [rbp+810h+var_7C8], 18Fh
0x140bdc24b  mov     [rbp+810h+var_7A8], 18Eh
0x140bdc252  mov     [rbp+810h+var_788], 18Dh
0x140bdc25c  mov     [rbp+810h+var_768], 198h
0x140bdc266  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bdc26d  mov     [rbp+810h+var_758], rsi
0x140bdc274  mov     [rbp+810h+var_760], rax
0x140bdc27b  lea     rax, aExdeletenpaged_0; "ExDeleteNPagedLookasideList"
0x140bdc282  mov     [rbp+810h+var_750], rax
0x140bdc289  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bdc290  mov     [rbp+810h+var_740], rax
0x140bdc297  lea     rax, aExdeletelookas_0; "ExDeleteLookasideListEx"
0x140bdc29e  mov     [rbp+810h+var_730], rax
0x140bdc2a5  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bdc2ac  mov     [rbp+810h+var_720], rax
0x140bdc2b3  lea     rax, aObreferenceobj_5; "ObReferenceObjectByPointer"
0x140bdc2ba  mov     [rbp+810h+var_710], rax
0x140bdc2c1  lea     rax, VfMiscObReferenceObjectByPointer_Entry
0x140bdc2c8  mov     [rbp+810h+var_700], rax
0x140bdc2cf  lea     rax, aObreferenceobj_1; "ObReferenceObjectByHandle"
0x140bdc2d6  mov     [rbp+810h+var_6F0], rax
0x140bdc2dd  lea     rax, VfMiscObReferenceObjectByHandle_Exit
0x140bdc2e4  mov     [rbp+810h+var_6D8], rax
0x140bdc2eb  lea     rax, aObfreferenceob_0; "ObfReferenceObject"
0x140bdc2f2  mov     [rbp+810h+var_6D0], rax
0x140bdc2f9  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc300  mov     [rbp+810h+var_6C0], rax
0x140bdc307  lea     rax, VfMiscObfReferenceObject_Exit
0x140bdc30e  mov     [rbp+810h+var_6B8], rax
0x140bdc315  lea     rax, aObfreferenceob; "ObfReferenceObjectWithTag"
0x140bdc31c  mov     [rbp+810h+var_6B0], rax
0x140bdc323  lea     rax, VfMiscObfReferenceObjectWithTag_Entry
0x140bdc32a  mov     [rbp+810h+var_6A0], rax
0x140bdc331  lea     rax, aObfdereference_0; "ObfDereferenceObject"
0x140bdc338  mov     [rbp+810h+var_690], rax
0x140bdc33f  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc346  mov     [rbp+810h+var_680], rax
0x140bdc34d  lea     rax, aObfdereference_2; "ObfDereferenceObjectWithTag"
0x140bdc354  mov     [rbp+810h+var_670], rax
0x140bdc35b  lea     rax, VfMiscObfReferenceObjectWithTag_Entry
0x140bdc362  mov     [rbp+810h+var_660], rax
0x140bdc369  lea     rax, aObgetobjectsec_0; "ObGetObjectSecurity"
0x140bdc370  mov     [rbp+810h+var_650], rax
0x140bdc377  lea     rax, VfMiscObGetObjectSecurity_Entry
0x140bdc37e  mov     [rbp+810h+var_640], rax
0x140bdc385  lea     rax, aObreferenceobj; "ObReferenceObjectByPointerWithTag"
0x140bdc38c  mov     [rbp+810h+var_630], rax
0x140bdc393  lea     rax, VfMiscObReferenceObjectByPointerWithTag_Entry
0x140bdc39a  mov     [rbp+810h+var_620], rax
0x140bdc3a1  lea     rax, aKereleasespinl_1; "KeReleaseSpinLock"
0x140bdc3a8  mov     [rbp+810h+var_610], rax
0x140bdc3af  lea     rax, VfMiscKeReleaseSpinLock_Entry
0x140bdc3b6  mov     [rbp+810h+var_600], rax
0x140bdc3bd  lea     rax, aKeacquirespinl_4; "KeAcquireSpinLockAtDpcLevel"
0x140bdc3c4  mov     [rbp+810h+var_5F0], rax
0x140bdc3cb  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc3d2  mov     [rbp+810h+var_5E0], rax
0x140bdc3d9  lea     rax, aKereleasespinl_2; "KeReleaseSpinLockFromDpcLevel"
0x140bdc3e0  mov     [rbp+810h+var_5D0], rax
0x140bdc3e7  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bdc3ee  mov     [rbp+810h+var_5C0], rax
0x140bdc3f5  mov     [rbp+810h+var_748], 199h
0x140bdc3ff  mov     [rbp+810h+var_738], rsi
0x140bdc406  mov     [rbp+810h+var_728], 19Ah
0x140bdc410  mov     [rbp+810h+var_718], rsi
0x140bdc417  mov     [rbp+810h+var_708], 0C9h
0x140bdc421  mov     [rbp+810h+var_6F8], rsi
0x140bdc428  mov     [rbp+810h+var_6E8], 0CAh
0x140bdc432  mov     [rbp+810h+var_6E0], rsi
0x140bdc439  mov     [rbp+810h+var_6C8], 0C4h
0x140bdc443  mov     [rbp+810h+var_6A8], 0C3h
0x140bdc44d  mov     [rbp+810h+var_698], rsi
0x140bdc454  mov     [rbp+810h+var_688], 0C6h
0x140bdc45e  mov     [rbp+810h+var_678], rsi
0x140bdc465  mov     [rbp+810h+var_668], 0C5h
0x140bdc46f  mov     [rbp+810h+var_658], rsi
0x140bdc476  mov     [rbp+810h+var_648], 0CBh
0x140bdc480  mov     [rbp+810h+var_638], rsi
0x140bdc487  mov     [rbp+810h+var_628], 0C8h
0x140bdc491  mov     [rbp+810h+var_618], rsi
0x140bdc498  mov     [rbp+810h+var_608], 103h
0x140bdc4a2  mov     [rbp+810h+var_5F8], rsi
0x140bdc4a9  mov     [rbp+810h+var_5E8], 125h
0x140bdc4b3  mov     [rbp+810h+var_5D8], rsi
0x140bdc4ba  mov     [rbp+810h+var_5C8], 102h
0x140bdc4c4  lea     rax, aKeacquirespinl_2; "KeAcquireSpinLockRaiseToDpc"
0x140bdc4cb  mov     [rbp+810h+var_5B8], rsi
0x140bdc4d2  mov     [rbp+810h+var_5B0], rax
0x140bdc4d9  lea     rax, VfMiscKeAcquireSpinLockRaiseToDpc_Entry
0x140bdc4e0  mov     [rbp+810h+var_5A0], rax
0x140bdc4e7  lea     rax, aIoconnectinter; "IoConnectInterrupt"
0x140bdc4ee  mov     [rbp+810h+var_590], rax
0x140bdc4f5  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc4fc  mov     [rbp+810h+var_580], rax
0x140bdc503  lea     rax, aIodisconnectin_1; "IoDisconnectInterrupt"
0x140bdc50a  mov     [rbp+810h+var_570], rax
0x140bdc511  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc518  mov     [rbp+810h+var_560], rax
0x140bdc51f  lea     rax, aIoconnectinter_2; "IoConnectInterruptEx"
0x140bdc526  mov     [rbp+810h+var_550], rax
0x140bdc52d  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc534  mov     [rbp+810h+var_540], rax
0x140bdc53b  lea     rax, aIodisconnectin_0; "IoDisconnectInterruptEx"
0x140bdc542  mov     [rbp+810h+var_530], rax
0x140bdc549  lea     rax, ViSpIoAllocateIrp_Exit
0x140bdc550  mov     [rbp+810h+var_520], rax
0x140bdc557  lea     rax, aKereleasemutex_0; "KeReleaseMutex"
0x140bdc55e  mov     [rbp+810h+var_510], rax
0x140bdc565  lea     rax, VfMiscKeReleaseMutant_Entry
0x140bdc56c  mov     [rbp+810h+var_500], rax
0x140bdc573  lea     rax, aKeinsertqueued; "KeInsertQueueDpc"
0x140bdc57a  mov     [rbp+810h+var_4F0], rax
0x140bdc581  lea     rax, VfMiscKeInsertQueueDpc_Entry
0x140bdc588  mov     [rbp+810h+var_4E0], rax
0x140bdc58f  lea     rax, aKeremovequeued; "KeRemoveQueueDpc"
0x140bdc596  mov     [rbp+810h+var_4D0], rax
0x140bdc59d  lea     rax, VfMiscKeRemoveQueueDpc_Entry
0x140bdc5a4  mov     [rbp+810h+var_4C0], rax
0x140bdc5ab  lea     rax, aKetrytoacquire_5; "KeTryToAcquireSpinLockAtDpcLevel"
0x140bdc5b2  mov     [rbp+810h+var_4B0], rax
0x140bdc5b9  lea     rax, VfMiscKeTryToAcquireSpinLockAtDpcLevel_Entry
0x140bdc5c0  mov     [rbp+810h+var_4A0], rax
0x140bdc5c7  lea     rax, aKetrytoacquire_4; "KeTryToAcquireInStackQueuedSpinLockAtDp"...
0x140bdc5ce  mov     [rbp+810h+var_490], rax
0x140bdc5d5  lea     rax, VfMiscKeTryToAcquireInStackQueuedSpinLockAtDpcLevel_Entry
0x140bdc5dc  mov     [rbp+810h+var_480], rax
0x140bdc5e3  lea     rax, aKeacquireinsta_6; "KeAcquireInStackQueuedSpinLockAtDpcLeve"...
0x140bdc5ea  mov     [rbp+810h+var_470], rax
0x140bdc5f1  lea     rax, VfMiscKeAcquireInStackQueuedSpinLockAtDpcLevel_Entry
0x140bdc5f8  mov     [rbp+810h+var_460], rax
0x140bdc5ff  lea     rax, aKeacquireinsta_5; "KeAcquireInStackQueuedSpinLockForDpc"
0x140bdc606  mov     [rbp+810h+var_450], rax
0x140bdc60d  lea     rax, VfMiscKeAcquireInStackQueuedSpinLockForDpc_Entry
0x140bdc614  mov     [rbp+810h+var_440], rax
0x140bdc61b  lea     rax, aKesetevent_0; "KeSetEvent"
0x140bdc622  mov     [rbp+810h+var_430], rax
0x140bdc629  lea     rax, VfMiscKeSetEvent_Entry
0x140bdc630  mov     [rbp+810h+var_420], rax
0x140bdc637  lea     rax, aIofreemdl_0; "IoFreeMdl"
0x140bdc63e  mov     [rbp+810h+var_410], rax
0x140bdc645  mov     [rbp+810h+var_5A8], 124h
0x140bdc64f  mov     [rbp+810h+var_598], rsi
0x140bdc656  mov     [rbp+810h+var_588], 166h
0x140bdc660  mov     [rbp+810h+var_578], rsi
0x140bdc667  mov     [rbp+810h+var_568], 157h
0x140bdc671  mov     [rbp+810h+var_558], rsi
0x140bdc678  mov     [rbp+810h+var_548], 165h
0x140bdc682  mov     [rbp+810h+var_538], rsi
0x140bdc689  mov     [rbp+810h+var_528], 156h
0x140bdc693  mov     [rbp+810h+var_518], rsi
0x140bdc69a  mov     [rbp+810h+var_508], 105h
0x140bdc6a4  mov     [rbp+810h+var_4F8], rsi
0x140bdc6ab  mov     [rbp+810h+var_4E8], 114h
0x140bdc6b5  mov     [rbp+810h+var_4D8], rsi
0x140bdc6bc  mov     [rbp+810h+var_4C8], 0FEh
0x140bdc6c6  mov     [rbp+810h+var_4B8], rsi
0x140bdc6cd  mov     [rbp+810h+var_4A8], 0F2h
0x140bdc6d7  mov     [rbp+810h+var_498], rsi
0x140bdc6de  mov     [rbp+810h+var_488], 0F5h
0x140bdc6e8  mov     [rbp+810h+var_478], rsi
0x140bdc6ef  mov     [rbp+810h+var_468], 12Ah
0x140bdc6f9  mov     [rbp+810h+var_458], rsi
0x140bdc700  mov     [rbp+810h+var_448], 129h
0x140bdc70a  mov     [rbp+810h+var_438], rsi
0x140bdc711  mov     [rbp+810h+var_428], 0FAh
0x140bdc71b  mov     [rbp+810h+var_418], rsi
0x140bdc722  lea     rax, VfMiscIoFreeMdl_Entry
0x140bdc729  mov     [rbp+810h+var_408], 153h
0x140bdc733  mov     [rbp+810h+var_400], rax
0x140bdc73a  lea     rax, aIoinitializewo; "IoInitializeWorkItem"
0x140bdc741  mov     [rbp+810h+var_3F0], rax
0x140bdc748  lea     rax, VfMiscIoInitializeWorkItem_Entry
0x140bdc74f  mov     [rbp+810h+var_3E0], rax
0x140bdc756  lea     rax, aExinitializere_0; "ExInitializeResourceLite"
0x140bdc75d  mov     [rbp+810h+var_3D0], rax
0x140bdc764  lea     rax, VfMiscExInitializeResourceLite_Entry
0x140bdc76b  mov     [rbp+810h+var_3C0], rax
0x140bdc772  lea     rax, VfMiscExInitializeResourceLite_Exit
0x140bdc779  mov     [rbp+810h+var_3B8], rax
0x140bdc780  lea     rax, aExdeleteresour; "ExDeleteResourceLite"
0x140bdc787  mov     [rbp+810h+var_3B0], rax
0x140bdc78e  lea     rax, VfMiscExDeleteResourceLite_Entry
0x140bdc795  mov     [rbp+810h+var_3A0], rax
0x140bdc79c  lea     rax, VfMiscExDeleteResourceLite_Exit
0x140bdc7a3  mov     [rbp+810h+var_398], rax
0x140bdc7aa  lea     rax, aExreleasefastm_1; "ExReleaseFastMutex"
0x140bdc7b1  mov     [rbp+810h+var_390], rax
0x140bdc7b8  lea     rax, VfMiscExReleaseFastMutex_Entry
0x140bdc7bf  mov     [rbp+810h+var_380], rax
0x140bdc7c6  lea     rax, aExacquirefastm; "ExAcquireFastMutexUnsafe"
0x140bdc7cd  mov     [rbp+810h+var_370], rax
0x140bdc7d4  lea     rax, VfMiscExAcquireFastMutexUnsafe_Entry
0x140bdc7db  mov     [rbp+810h+var_360], rax
0x140bdc7e2  lea     rax, aExreleasefastm_0; "ExReleaseFastMutexUnsafe"
0x140bdc7e9  mov     [rbp+810h+var_350], rax
0x140bdc7f0  lea     rax, VfMiscExReleaseFastMutexUnsafe_Entry
0x140bdc7f7  mov     [rbp+810h+var_340], rax
0x140bdc7fe  lea     rax, aExfacquirepush; "ExfAcquirePushLockExclusive"
0x140bdc805  mov     [rbp+810h+var_330], rax
0x140bdc80c  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bdc813  mov     [rbp+810h+var_320], rax
0x140bdc81a  lea     rax, aExfacquirepush_1; "ExfAcquirePushLockShared"
0x140bdc821  mov     [rbp+810h+var_310], rax
0x140bdc828  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bdc82f  mov     [rbp+810h+var_300], rax
0x140bdc836  lea     rax, aExftryacquirep_0; "ExfTryAcquirePushLockShared"
0x140bdc83d  mov     [rbp+810h+var_2F0], rax
0x140bdc844  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bdc84b  mov     [rbp+810h+var_2E0], rax
0x140bdc852  lea     rax, aExfreleasepush_1; "ExfReleasePushLock"
0x140bdc859  mov     [rbp+810h+var_2D0], rax
0x140bdc860  lea     rax, VfMiscExfReleasePushLockShared_Entry
0x140bdc867  mov     [rbp+810h+var_2C0], rax
0x140bdc86e  lea     rax, aExftrytowakepu; "ExfTryToWakePushLock"
  ... truncated ...
```
