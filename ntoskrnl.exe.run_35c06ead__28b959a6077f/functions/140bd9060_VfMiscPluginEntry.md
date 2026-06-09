# VfMiscPluginEntry

- ea: `0x140bd9060`
- end: `0x140bd9d40`
- name: `VfMiscPluginEntry`
- size: `3296`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140538640`
- `0x1406345bc`
- `0x14063c6ac`
- `0x1406d9d70`
- `0x140bd61f4`
- `0x140bd9060`
- `0x140bdbc04`

## string_xrefs

- `0x140bd927b`: `ExDeleteNPagedLookasideList`
- `0x140bd91da`: `ExDeletePagedLookasideList`
- `0x140bd9297`: `ExDeleteLookasideListEx`
- `0x140bd916e`: `ExInitializeLookasideListEx`
- `0x140bd91b0`: `ExInitializePagedLookasideList`
- `0x140bd918f`: `ExInitializeNPagedLookasideList`
- `0x140bd958f`: `KeRemoveQueueDpc`
- `0x140bd9369`: `ObGetObjectSecurity`
- `0x140bd9a86`: `ExReleaseResourceForThreadLite`
- `0x140bd9780`: `ExDeleteResourceLite`

## pseudocode

```c

```

## disassembly

```asm
0x140bd9060  push    rbp
0x140bd9062  push    rbx
0x140bd9063  push    rsi
0x140bd9064  push    rdi
0x140bd9065  lea     rbp, [rsp-7F8h]
0x140bd906d  sub     rsp, 8F8h
0x140bd9074  mov     rax, cs:__security_cookie
0x140bd907b  xor     rax, rsp
0x140bd907e  mov     [rbp+810h+var_30], rax
0x140bd9085  xor     esi, esi
0x140bd9087  mov     [rsp+910h+var_8E8], 0EEh
0x140bd908f  lea     rax, VfMiscPluginUnload
0x140bd9096  mov     [rsp+910h+var_8D8], rsi
0x140bd909b  mov     cs:qword_140EF2168, rax
0x140bd90a2  lea     rax, aMmallocatecont_2; "MmAllocateContiguousMemory"
0x140bd90a9  mov     [rsp+910h+var_8F0], rax
0x140bd90ae  lea     rax, VfMiscMmAllocateContiguousMemory_Entry
0x140bd90b5  mov     [rsp+910h+var_8E0], rax
0x140bd90ba  lea     rax, aMmallocatecont_1; "MmAllocateContiguousMemoryEx"
0x140bd90c1  mov     [rsp+910h+var_8D0], rax
0x140bd90c6  lea     rax, VfMiscMmAllocateContiguousMemoryEx_Entry
0x140bd90cd  mov     [rsp+910h+var_8C0], rax
0x140bd90d2  lea     rax, aKereleasequeue_0; "KeReleaseQueuedSpinLock"
0x140bd90d9  mov     [rsp+910h+var_8B0], rax
0x140bd90de  lea     rax, VfMiscKeReleaseQueuedSpinLock_Entry
0x140bd90e5  mov     [rsp+910h+var_8A0], rax
0x140bd90ea  lea     rax, aKeinitializeev_0; "KeInitializeEvent"
0x140bd90f1  mov     [rbp+810h+var_890], rax
0x140bd90f5  lea     rax, VfMiscKeInitializeEvent_Entry
0x140bd90fc  mov     [rbp+810h+var_880], rax
0x140bd9100  lea     rax, aKeinitializemu_1; "KeInitializeMutant"
0x140bd9107  mov     [rbp+810h+var_870], rax
0x140bd910b  lea     rax, VfMiscKeInitializeMutant_Entry
0x140bd9112  mov     [rbp+810h+var_860], rax
0x140bd9116  lea     rax, aKeinitializemu_2; "KeInitializeMutex"
0x140bd911d  mov     [rbp+810h+var_850], rax
0x140bd9121  lea     rax, VfMiscKeInitializeMutant_Entry
0x140bd9128  mov     [rbp+810h+var_840], rax
0x140bd912c  lea     rax, aKeinitializeti_1; "KeInitializeTimerEx"
0x140bd9133  mov     [rbp+810h+var_830], rax
0x140bd9137  lea     rax, VfMiscKeInitializeTimerEx_Entry
0x140bd913e  mov     [rbp+810h+var_820], rax
0x140bd9142  lea     rax, aKewaitforsingl; "KeWaitForSingleObject"
0x140bd9149  mov     [rbp+810h+var_810], rax
0x140bd914d  lea     rax, VfMiscKeWaitForSingleObject_Entry
0x140bd9154  mov     [rbp+810h+var_800], rax
0x140bd9158  lea     rax, aKewaitformulti; "KeWaitForMultipleObjects"
0x140bd915f  mov     [rbp+810h+var_7F0], rax
0x140bd9163  lea     rax, VfMiscKeWaitForMultipleObjects_Entry
0x140bd916a  mov     [rbp+810h+var_7E0], rax
0x140bd916e  lea     rax, aExinitializelo_0; "ExInitializeLookasideListEx"
0x140bd9175  mov     [rbp+810h+var_7D0], rax
0x140bd9179  lea     rax, VfMiscExInitializeLookasideListEx_Entry
0x140bd9180  mov     [rbp+810h+var_7C0], rax
0x140bd9184  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bd918b  mov     [rbp+810h+var_7B8], rax
0x140bd918f  lea     rax, aExinitializenp; "ExInitializeNPagedLookasideList"
0x140bd9196  mov     [rbp+810h+var_7B0], rax
0x140bd919a  lea     rax, VfMiscExInitializeNPagedLookasideList_Entry
0x140bd91a1  mov     [rbp+810h+var_7A0], rax
0x140bd91a5  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bd91ac  mov     [rbp+810h+var_798], rax
0x140bd91b0  lea     rax, aExinitializepa_0; "ExInitializePagedLookasideList"
0x140bd91b7  mov     [rbp+810h+var_790], rax
0x140bd91be  lea     rax, VfMiscExInitializeNPagedLookasideList_Entry
0x140bd91c5  mov     [rbp+810h+var_780], rax
0x140bd91cc  lea     rax, VfMiscExInitializePagedLookasideList_Exit
0x140bd91d3  mov     [rbp+810h+var_778], rax
0x140bd91da  lea     rax, aExdeletepagedl_0; "ExDeletePagedLookasideList"
0x140bd91e1  mov     [rbp+810h+var_770], rax
0x140bd91e8  mov     [rsp+910h+var_8C8], 0EDh
0x140bd91f0  mov     [rsp+910h+var_8B8], rsi
0x140bd91f5  mov     [rsp+910h+var_8A8], 104h
0x140bd91fd  mov     [rsp+910h+var_898], rsi
0x140bd9202  mov     [rbp+810h+var_888], 11Ch
0x140bd9209  mov     [rbp+810h+var_878], rsi
0x140bd920d  mov     [rbp+810h+var_868], 11Bh
0x140bd9214  mov     [rbp+810h+var_858], rsi
0x140bd9218  mov     [rbp+810h+var_848], 11Ah
0x140bd921f  mov     [rbp+810h+var_838], rsi
0x140bd9223  mov     [rbp+810h+var_828], 117h
0x140bd922a  mov     [rbp+810h+var_818], rsi
0x140bd922e  mov     [rbp+810h+var_808], 0F0h
0x140bd9235  mov     [rbp+810h+var_7F8], rsi
0x140bd9239  mov     [rbp+810h+var_7E8], 0F1h
0x140bd9240  mov     [rbp+810h+var_7D8], rsi
0x140bd9244  mov     [rbp+810h+var_7C8], 18Fh
0x140bd924b  mov     [rbp+810h+var_7A8], 18Eh
0x140bd9252  mov     [rbp+810h+var_788], 18Dh
0x140bd925c  mov     [rbp+810h+var_768], 198h
0x140bd9266  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bd926d  mov     [rbp+810h+var_758], rsi
0x140bd9274  mov     [rbp+810h+var_760], rax
0x140bd927b  lea     rax, aExdeletenpaged_0; "ExDeleteNPagedLookasideList"
0x140bd9282  mov     [rbp+810h+var_750], rax
0x140bd9289  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bd9290  mov     [rbp+810h+var_740], rax
0x140bd9297  lea     rax, aExdeletelookas_0; "ExDeleteLookasideListEx"
0x140bd929e  mov     [rbp+810h+var_730], rax
0x140bd92a5  lea     rax, VfMiscExDeleteLookasideListEx_Entry
0x140bd92ac  mov     [rbp+810h+var_720], rax
0x140bd92b3  lea     rax, aObreferenceobj_5; "ObReferenceObjectByPointer"
0x140bd92ba  mov     [rbp+810h+var_710], rax
0x140bd92c1  lea     rax, VfMiscObReferenceObjectByPointer_Entry
0x140bd92c8  mov     [rbp+810h+var_700], rax
0x140bd92cf  lea     rax, aObreferenceobj_1; "ObReferenceObjectByHandle"
0x140bd92d6  mov     [rbp+810h+var_6F0], rax
0x140bd92dd  lea     rax, VfMiscObReferenceObjectByHandle_Exit
0x140bd92e4  mov     [rbp+810h+var_6D8], rax
0x140bd92eb  lea     rax, aObfreferenceob_0; "ObfReferenceObject"
0x140bd92f2  mov     [rbp+810h+var_6D0], rax
0x140bd92f9  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bd9300  mov     [rbp+810h+var_6C0], rax
0x140bd9307  lea     rax, VfMiscObfReferenceObject_Exit
0x140bd930e  mov     [rbp+810h+var_6B8], rax
0x140bd9315  lea     rax, aObfreferenceob; "ObfReferenceObjectWithTag"
0x140bd931c  mov     [rbp+810h+var_6B0], rax
0x140bd9323  lea     rax, VfMiscObfReferenceObjectWithTag_Entry
0x140bd932a  mov     [rbp+810h+var_6A0], rax
0x140bd9331  lea     rax, aObfdereference_0; "ObfDereferenceObject"
0x140bd9338  mov     [rbp+810h+var_690], rax
0x140bd933f  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bd9346  mov     [rbp+810h+var_680], rax
0x140bd934d  lea     rax, aObfdereference_2; "ObfDereferenceObjectWithTag"
0x140bd9354  mov     [rbp+810h+var_670], rax
0x140bd935b  lea     rax, VfMiscObfReferenceObjectWithTag_Entry
0x140bd9362  mov     [rbp+810h+var_660], rax
0x140bd9369  lea     rax, aObgetobjectsec_0; "ObGetObjectSecurity"
0x140bd9370  mov     [rbp+810h+var_650], rax
0x140bd9377  lea     rax, VfMiscObGetObjectSecurity_Entry
0x140bd937e  mov     [rbp+810h+var_640], rax
0x140bd9385  lea     rax, aObreferenceobj; "ObReferenceObjectByPointerWithTag"
0x140bd938c  mov     [rbp+810h+var_630], rax
0x140bd9393  lea     rax, VfMiscObReferenceObjectByPointerWithTag_Entry
0x140bd939a  mov     [rbp+810h+var_620], rax
0x140bd93a1  lea     rax, aKereleasespinl_1; "KeReleaseSpinLock"
0x140bd93a8  mov     [rbp+810h+var_610], rax
0x140bd93af  lea     rax, VfMiscKeReleaseSpinLock_Entry
0x140bd93b6  mov     [rbp+810h+var_600], rax
0x140bd93bd  lea     rax, aKeacquirespinl_4; "KeAcquireSpinLockAtDpcLevel"
0x140bd93c4  mov     [rbp+810h+var_5F0], rax
0x140bd93cb  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bd93d2  mov     [rbp+810h+var_5E0], rax
0x140bd93d9  lea     rax, aKereleasespinl_2; "KeReleaseSpinLockFromDpcLevel"
0x140bd93e0  mov     [rbp+810h+var_5D0], rax
0x140bd93e7  lea     rax, VfMiscObfDereferenceObject_Entry
0x140bd93ee  mov     [rbp+810h+var_5C0], rax
0x140bd93f5  mov     [rbp+810h+var_748], 199h
0x140bd93ff  mov     [rbp+810h+var_738], rsi
0x140bd9406  mov     [rbp+810h+var_728], 19Ah
0x140bd9410  mov     [rbp+810h+var_718], rsi
0x140bd9417  mov     [rbp+810h+var_708], 0C9h
0x140bd9421  mov     [rbp+810h+var_6F8], rsi
0x140bd9428  mov     [rbp+810h+var_6E8], 0CAh
0x140bd9432  mov     [rbp+810h+var_6E0], rsi
0x140bd9439  mov     [rbp+810h+var_6C8], 0C4h
0x140bd9443  mov     [rbp+810h+var_6A8], 0C3h
0x140bd944d  mov     [rbp+810h+var_698], rsi
0x140bd9454  mov     [rbp+810h+var_688], 0C6h
0x140bd945e  mov     [rbp+810h+var_678], rsi
0x140bd9465  mov     [rbp+810h+var_668], 0C5h
0x140bd946f  mov     [rbp+810h+var_658], rsi
0x140bd9476  mov     [rbp+810h+var_648], 0CBh
0x140bd9480  mov     [rbp+810h+var_638], rsi
0x140bd9487  mov     [rbp+810h+var_628], 0C8h
0x140bd9491  mov     [rbp+810h+var_618], rsi
0x140bd9498  mov     [rbp+810h+var_608], 103h
0x140bd94a2  mov     [rbp+810h+var_5F8], rsi
0x140bd94a9  mov     [rbp+810h+var_5E8], 125h
0x140bd94b3  mov     [rbp+810h+var_5D8], rsi
0x140bd94ba  mov     [rbp+810h+var_5C8], 102h
0x140bd94c4  lea     rax, aKeacquirespinl_2; "KeAcquireSpinLockRaiseToDpc"
0x140bd94cb  mov     [rbp+810h+var_5B8], rsi
0x140bd94d2  mov     [rbp+810h+var_5B0], rax
0x140bd94d9  lea     rax, VfMiscKeAcquireSpinLockRaiseToDpc_Entry
0x140bd94e0  mov     [rbp+810h+var_5A0], rax
0x140bd94e7  lea     rax, aIoconnectinter; "IoConnectInterrupt"
0x140bd94ee  mov     [rbp+810h+var_590], rax
0x140bd94f5  lea     rax, ViSpIoAllocateIrp_Exit
0x140bd94fc  mov     [rbp+810h+var_580], rax
0x140bd9503  lea     rax, aIodisconnectin_1; "IoDisconnectInterrupt"
0x140bd950a  mov     [rbp+810h+var_570], rax
0x140bd9511  lea     rax, ViSpIoAllocateIrp_Exit
0x140bd9518  mov     [rbp+810h+var_560], rax
0x140bd951f  lea     rax, aIoconnectinter_2; "IoConnectInterruptEx"
0x140bd9526  mov     [rbp+810h+var_550], rax
0x140bd952d  lea     rax, ViSpIoAllocateIrp_Exit
0x140bd9534  mov     [rbp+810h+var_540], rax
0x140bd953b  lea     rax, aIodisconnectin_0; "IoDisconnectInterruptEx"
0x140bd9542  mov     [rbp+810h+var_530], rax
0x140bd9549  lea     rax, ViSpIoAllocateIrp_Exit
0x140bd9550  mov     [rbp+810h+var_520], rax
0x140bd9557  lea     rax, aKereleasemutex_0; "KeReleaseMutex"
0x140bd955e  mov     [rbp+810h+var_510], rax
0x140bd9565  lea     rax, VfMiscKeReleaseMutant_Entry
0x140bd956c  mov     [rbp+810h+var_500], rax
0x140bd9573  lea     rax, aKeinsertqueued; "KeInsertQueueDpc"
0x140bd957a  mov     [rbp+810h+var_4F0], rax
0x140bd9581  lea     rax, VfMiscKeInsertQueueDpc_Entry
0x140bd9588  mov     [rbp+810h+var_4E0], rax
0x140bd958f  lea     rax, aKeremovequeued; "KeRemoveQueueDpc"
0x140bd9596  mov     [rbp+810h+var_4D0], rax
0x140bd959d  lea     rax, VfMiscKeRemoveQueueDpc_Entry
0x140bd95a4  mov     [rbp+810h+var_4C0], rax
0x140bd95ab  lea     rax, aKetrytoacquire_5; "KeTryToAcquireSpinLockAtDpcLevel"
0x140bd95b2  mov     [rbp+810h+var_4B0], rax
0x140bd95b9  lea     rax, VfMiscKeTryToAcquireSpinLockAtDpcLevel_Entry
0x140bd95c0  mov     [rbp+810h+var_4A0], rax
0x140bd95c7  lea     rax, aKetrytoacquire_4; "KeTryToAcquireInStackQueuedSpinLockAtDp"...
0x140bd95ce  mov     [rbp+810h+var_490], rax
0x140bd95d5  lea     rax, VfMiscKeTryToAcquireInStackQueuedSpinLockAtDpcLevel_Entry
0x140bd95dc  mov     [rbp+810h+var_480], rax
0x140bd95e3  lea     rax, aKeacquireinsta_6; "KeAcquireInStackQueuedSpinLockAtDpcLeve"...
0x140bd95ea  mov     [rbp+810h+var_470], rax
0x140bd95f1  lea     rax, VfMiscKeAcquireInStackQueuedSpinLockAtDpcLevel_Entry
0x140bd95f8  mov     [rbp+810h+var_460], rax
0x140bd95ff  lea     rax, aKeacquireinsta_5; "KeAcquireInStackQueuedSpinLockForDpc"
0x140bd9606  mov     [rbp+810h+var_450], rax
0x140bd960d  lea     rax, VfMiscKeAcquireInStackQueuedSpinLockForDpc_Entry
0x140bd9614  mov     [rbp+810h+var_440], rax
0x140bd961b  lea     rax, aKesetevent_0; "KeSetEvent"
0x140bd9622  mov     [rbp+810h+var_430], rax
0x140bd9629  lea     rax, VfMiscKeSetEvent_Entry
0x140bd9630  mov     [rbp+810h+var_420], rax
0x140bd9637  lea     rax, aIofreemdl_0; "IoFreeMdl"
0x140bd963e  mov     [rbp+810h+var_410], rax
0x140bd9645  mov     [rbp+810h+var_5A8], 124h
0x140bd964f  mov     [rbp+810h+var_598], rsi
0x140bd9656  mov     [rbp+810h+var_588], 166h
0x140bd9660  mov     [rbp+810h+var_578], rsi
0x140bd9667  mov     [rbp+810h+var_568], 157h
0x140bd9671  mov     [rbp+810h+var_558], rsi
0x140bd9678  mov     [rbp+810h+var_548], 165h
0x140bd9682  mov     [rbp+810h+var_538], rsi
0x140bd9689  mov     [rbp+810h+var_528], 156h
0x140bd9693  mov     [rbp+810h+var_518], rsi
0x140bd969a  mov     [rbp+810h+var_508], 105h
0x140bd96a4  mov     [rbp+810h+var_4F8], rsi
0x140bd96ab  mov     [rbp+810h+var_4E8], 114h
0x140bd96b5  mov     [rbp+810h+var_4D8], rsi
0x140bd96bc  mov     [rbp+810h+var_4C8], 0FEh
0x140bd96c6  mov     [rbp+810h+var_4B8], rsi
0x140bd96cd  mov     [rbp+810h+var_4A8], 0F2h
0x140bd96d7  mov     [rbp+810h+var_498], rsi
0x140bd96de  mov     [rbp+810h+var_488], 0F5h
0x140bd96e8  mov     [rbp+810h+var_478], rsi
0x140bd96ef  mov     [rbp+810h+var_468], 12Ah
0x140bd96f9  mov     [rbp+810h+var_458], rsi
0x140bd9700  mov     [rbp+810h+var_448], 129h
0x140bd970a  mov     [rbp+810h+var_438], rsi
0x140bd9711  mov     [rbp+810h+var_428], 0FAh
0x140bd971b  mov     [rbp+810h+var_418], rsi
0x140bd9722  lea     rax, VfMiscIoFreeMdl_Entry
0x140bd9729  mov     [rbp+810h+var_408], 153h
0x140bd9733  mov     [rbp+810h+var_400], rax
0x140bd973a  lea     rax, aIoinitializewo; "IoInitializeWorkItem"
0x140bd9741  mov     [rbp+810h+var_3F0], rax
0x140bd9748  lea     rax, VfMiscIoInitializeWorkItem_Entry
0x140bd974f  mov     [rbp+810h+var_3E0], rax
0x140bd9756  lea     rax, aExinitializere_0; "ExInitializeResourceLite"
0x140bd975d  mov     [rbp+810h+var_3D0], rax
0x140bd9764  lea     rax, VfMiscExInitializeResourceLite_Entry
0x140bd976b  mov     [rbp+810h+var_3C0], rax
0x140bd9772  lea     rax, VfMiscExInitializeResourceLite_Exit
0x140bd9779  mov     [rbp+810h+var_3B8], rax
0x140bd9780  lea     rax, aExdeleteresour; "ExDeleteResourceLite"
0x140bd9787  mov     [rbp+810h+var_3B0], rax
0x140bd978e  lea     rax, VfMiscExDeleteResourceLite_Entry
0x140bd9795  mov     [rbp+810h+var_3A0], rax
0x140bd979c  lea     rax, VfMiscExDeleteResourceLite_Exit
0x140bd97a3  mov     [rbp+810h+var_398], rax
0x140bd97aa  lea     rax, aExreleasefastm_1; "ExReleaseFastMutex"
0x140bd97b1  mov     [rbp+810h+var_390], rax
0x140bd97b8  lea     rax, VfMiscExReleaseFastMutex_Entry
0x140bd97bf  mov     [rbp+810h+var_380], rax
0x140bd97c6  lea     rax, aExacquirefastm; "ExAcquireFastMutexUnsafe"
0x140bd97cd  mov     [rbp+810h+var_370], rax
0x140bd97d4  lea     rax, VfMiscExAcquireFastMutexUnsafe_Entry
0x140bd97db  mov     [rbp+810h+var_360], rax
0x140bd97e2  lea     rax, aExreleasefastm_0; "ExReleaseFastMutexUnsafe"
0x140bd97e9  mov     [rbp+810h+var_350], rax
0x140bd97f0  lea     rax, VfMiscExReleaseFastMutexUnsafe_Entry
0x140bd97f7  mov     [rbp+810h+var_340], rax
0x140bd97fe  lea     rax, aExfacquirepush; "ExfAcquirePushLockExclusive"
0x140bd9805  mov     [rbp+810h+var_330], rax
0x140bd980c  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bd9813  mov     [rbp+810h+var_320], rax
0x140bd981a  lea     rax, aExfacquirepush_1; "ExfAcquirePushLockShared"
0x140bd9821  mov     [rbp+810h+var_310], rax
0x140bd9828  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bd982f  mov     [rbp+810h+var_300], rax
0x140bd9836  lea     rax, aExftryacquirep_0; "ExfTryAcquirePushLockShared"
0x140bd983d  mov     [rbp+810h+var_2F0], rax
0x140bd9844  lea     rax, VfMiscExfAcquirePushLockExclusive_Entry
0x140bd984b  mov     [rbp+810h+var_2E0], rax
0x140bd9852  lea     rax, aExfreleasepush_1; "ExfReleasePushLock"
0x140bd9859  mov     [rbp+810h+var_2D0], rax
0x140bd9860  lea     rax, VfMiscExfReleasePushLockShared_Entry
0x140bd9867  mov     [rbp+810h+var_2C0], rax
0x140bd986e  lea     rax, aExftrytowakepu; "ExfTryToWakePushLock"
  ... truncated ...
```
