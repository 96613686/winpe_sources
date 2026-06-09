# VfPoolTrackingEntry

- ea: `0x14063abc0`
- end: `0x14063b0c6`
- name: `VfPoolTrackingEntry`
- size: `1286`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14053fcf0`
- `0x14063abc0`
- `0x1406dc8c0`
- `0x140bca2e0`
- `0x140bca368`
- `0x140bca440`

## string_xrefs

- `0x14063ae77`: `MmFreeNonCachedMemory`
- `0x14063ae31`: `MmAllocateNonCachedMemory`
- `0x14063ae4d`: `MmCreateMdl`
- `0x14063aecb`: `MmAllocateContiguousMemorySpecifyCache`
- `0x14063aee7`: `MmAllocateContiguousMemorySpecifyCacheNode`

## pseudocode

```c

```

## disassembly

```asm
0x14063abc0  mov     [rsp-8+arg_0], rbx
0x14063abc5  mov     [rsp-8+arg_8], rdi
0x14063abca  push    rbp
0x14063abcb  lea     rbp, [rsp-290h]
0x14063abd3  sub     rsp, 390h
0x14063abda  mov     rax, cs:__security_cookie
0x14063abe1  xor     rax, rsp
0x14063abe4  mov     [rbp+290h+var_10], rax
0x14063abeb  xor     edi, edi
0x14063abed  mov     qword ptr cs:ViPtUnloadRundown.___u0, rdi
0x14063abf4  call    ViPtInitCircularPoolTrace
0x14063abf9  mov     ebx, eax
0x14063abfb  test    eax, eax
0x14063abfd  js      loc_14063B09A
0x14063ac03  test    cs:VfOptionFlags, 1000h
0x14063ac0d  jz      short loc_14063AC14
0x14063ac0f  call    ViPtInitAvlTrees
0x14063ac14  cmp     cs:VfDifRunningWithoutReboot, dil
0x14063ac1b  jnz     short loc_14063AC33
0x14063ac1d  test    cs:VfOptionFlags, 800h
0x14063ac27  jnz     short loc_14063AC33
0x14063ac29  mov     cs:MmTrackLockedPages, 1
0x14063ac33  lea     rax, ViPtPluginUnload
0x14063ac3a  mov     [rsp+390h+var_368], 19Dh
0x14063ac42  mov     cs:qword_140EF24C8, rax
0x14063ac49  lea     rax, aExallocatepool_0; "ExAllocatePool"
0x14063ac50  mov     [rsp+390h+var_370], rax
0x14063ac55  lea     rax, ViSpIoAllocateIrp_Exit
0x14063ac5c  mov     [rsp+390h+var_360], rax
0x14063ac61  lea     rax, aExallocatepool; "ExAllocatePool2"
0x14063ac68  mov     [rsp+390h+var_350], rax
0x14063ac6d  lea     rax, ViSpIoAllocateIrp_Exit
0x14063ac74  mov     [rsp+390h+var_340], rax
0x14063ac79  lea     rax, aExallocatepool_13; "ExAllocatePool3"
0x14063ac80  mov     [rsp+390h+var_330], rax
0x14063ac85  lea     rax, ViSpIoAllocateIrp_Exit
0x14063ac8c  mov     [rsp+390h+var_318], rax
0x14063ac91  lea     rax, aExallocatepool_1; "ExAllocatePoolWithTag"
0x14063ac98  mov     [rbp+290h+var_310], rax
0x14063ac9c  lea     rax, ViSpIoAllocateIrp_Exit
0x14063aca3  mov     [rbp+290h+var_300], rax
0x14063aca7  lea     rax, aExallocatepool_15; "ExAllocatePoolWithTagPriority"
0x14063acae  mov     [rbp+290h+var_2F0], rax
0x14063acb2  lea     rax, ViSpIoAllocateIrp_Exit
0x14063acb9  mov     [rbp+290h+var_2E0], rax
0x14063acbd  lea     rax, aExallocatepool_14; "ExAllocatePoolWithQuota"
0x14063acc4  mov     [rbp+290h+var_2D0], rax
0x14063acc8  lea     rax, ViSpIoAllocateIrp_Exit
0x14063accf  mov     [rbp+290h+var_2C0], rax
0x14063acd3  lea     rax, aExallocatepool_16; "ExAllocatePoolWithQuotaTag"
0x14063acda  mov     [rbp+290h+var_2B0], rax
0x14063acde  lea     rax, ViSpIoAllocateIrp_Exit
0x14063ace5  mov     [rbp+290h+var_2A0], rax
0x14063ace9  lea     rax, aExfreepool_1; "ExFreePool"
0x14063acf0  mov     [rbp+290h+var_290], rax
0x14063acf4  lea     rax, ViSpIoAllocateIrp_Exit
0x14063acfb  mov     [rbp+290h+var_280], rax
0x14063acff  lea     rax, aExfreepoolwith_1; "ExFreePoolWithTag"
0x14063ad06  mov     [rbp+290h+var_270], rax
0x14063ad0a  lea     rax, ViSpIoAllocateIrp_Exit
0x14063ad11  mov     [rbp+290h+var_260], rax
0x14063ad15  lea     rax, aIoallocatemdl_0; "IoAllocateMdl"
0x14063ad1c  mov     [rbp+290h+var_250], rax
0x14063ad20  lea     rax, VfPtIoAllocateMdl_Exit
0x14063ad27  mov     [rbp+290h+var_238], rax
0x14063ad2b  lea     rax, aIofreemdl; "IoFreeMdl"
0x14063ad32  mov     [rbp+290h+var_230], rax
0x14063ad36  lea     rax, aMmallocatepage_3; "MmAllocatePagesForMdl"
0x14063ad3d  mov     [rbp+290h+var_210], rax
0x14063ad44  lea     rax, VfPtMmAllocatePagesForMdl_Exit
0x14063ad4b  mov     [rbp+290h+var_1F8], rax
0x14063ad52  lea     rax, aMmallocatepage; "MmAllocatePagesForMdlEx"
0x14063ad59  mov     [rbp+290h+var_1F0], rax
0x14063ad60  lea     rax, VfPtMmAllocatePagesForMdlEx_Exit
0x14063ad67  mov     [rbp+290h+var_1D8], rax
0x14063ad6e  lea     rax, aMmallocatenode; "MmAllocateNodePagesForMdlEx"
0x14063ad75  mov     [rbp+290h+var_1D0], rax
0x14063ad7c  mov     [rsp+390h+var_358], rdi
0x14063ad81  mov     [rsp+390h+var_348], 1A3h
0x14063ad89  mov     [rsp+390h+var_338], rdi
0x14063ad8e  mov     [rsp+390h+var_328], 1A2h
0x14063ad96  mov     [rsp+390h+var_320], rdi
0x14063ad9b  mov     [rbp+290h+var_308], 19Eh
0x14063ada2  mov     [rbp+290h+var_2F8], rdi
0x14063ada6  mov     [rbp+290h+var_2E8], 19Fh
0x14063adad  mov     [rbp+290h+var_2D8], rdi
0x14063adb1  mov     [rbp+290h+var_2C8], 1A0h
0x14063adb8  mov     [rbp+290h+var_2B8], rdi
0x14063adbc  mov     [rbp+290h+var_2A8], 1A1h
0x14063adc3  mov     [rbp+290h+var_298], rdi
0x14063adc7  mov     [rbp+290h+var_288], 191h
0x14063adce  mov     [rbp+290h+var_278], rdi
0x14063add2  mov     [rbp+290h+var_268], 190h
0x14063add9  mov     [rbp+290h+var_258], rdi
0x14063addd  mov     [rbp+290h+var_248], 16Dh
0x14063ade4  mov     [rbp+290h+var_240], rdi
0x14063ade8  mov     [rbp+290h+var_228], 153h
0x14063adef  mov     [rbp+290h+var_220], rdi
0x14063adf3  mov     [rbp+290h+var_218], rdi
0x14063adf7  mov     [rbp+290h+var_208], 0E6h
0x14063ae01  mov     [rbp+290h+var_200], rdi
0x14063ae08  mov     [rbp+290h+var_1E8], 0E5h
0x14063ae12  mov     [rbp+290h+var_1E0], rdi
0x14063ae19  lea     rax, VfPtMmAllocateNodePagesForMdlEx_Exit
0x14063ae20  mov     [rbp+290h+var_1C8], 0E8h
0x14063ae2a  mov     [rbp+290h+var_1B8], rax
0x14063ae31  lea     rax, aMmallocatenonc_0; "MmAllocateNonCachedMemory"
0x14063ae38  mov     [rbp+290h+var_1B0], rax
0x14063ae3f  lea     rax, VfPtMmAllocateNonCachedMemory_Exit
0x14063ae46  mov     [rbp+290h+var_198], rax
0x14063ae4d  lea     rax, aMmcreatemdl_0; "MmCreateMdl"
0x14063ae54  mov     [rbp+290h+var_190], rax
0x14063ae5b  lea     rax, VfPtMmCreateMdl_Exit
0x14063ae62  mov     [rbp+290h+var_178], rax
0x14063ae69  lea     rax, aMmfreepagesfro_0; "MmFreePagesFromMdl"
0x14063ae70  mov     [rbp+290h+var_170], rax
0x14063ae77  lea     rax, aMmfreenoncache; "MmFreeNonCachedMemory"
0x14063ae7e  mov     [rbp+290h+var_150], rax
0x14063ae85  lea     rax, VfPtMmFreeNonCachedMemory_Entry
0x14063ae8c  mov     [rbp+290h+var_140], rax
0x14063ae93  lea     rax, aMmallocatecont_0; "MmAllocateContiguousMemory"
0x14063ae9a  mov     [rbp+290h+var_130], rax
0x14063aea1  lea     rax, VfPtMmAllocateContiguousMemory_Exit
0x14063aea8  mov     [rbp+290h+var_118], rax
0x14063aeaf  lea     rax, aMmallocatecont; "MmAllocateContiguousMemoryEx"
0x14063aeb6  mov     [rbp+290h+var_110], rax
0x14063aebd  lea     rax, VfPtMmAllocateContiguousMemoryEx_Exit
0x14063aec4  mov     [rbp+290h+var_F8], rax
0x14063aecb  lea     rax, aMmallocatecont_9; "MmAllocateContiguousMemorySpecifyCache"
0x14063aed2  mov     [rbp+290h+var_F0], rax
0x14063aed9  lea     rax, VfPtMmAllocateContiguousMemorySpecifyCache_Exit
0x14063aee0  mov     [rbp+290h+var_D8], rax
0x14063aee7  lea     rax, aMmallocatecont_11; "MmAllocateContiguousMemorySpecifyCacheN"...
0x14063aeee  mov     [rbp+290h+var_D0], rax
0x14063aef5  lea     rax, VfPtMmAllocateContiguousMemorySpecifyCache_Exit
0x14063aefc  mov     [rbp+290h+var_B8], rax
0x14063af03  lea     rax, aMmallocatecont_7; "MmAllocateContiguousNodeMemory"
0x14063af0a  mov     [rbp+290h+var_B0], rax
0x14063af11  lea     rax, VfPtMmAllocateContiguousMemorySpecifyCache_Exit
0x14063af18  mov     [rbp+290h+var_98], rax
0x14063af1f  lea     rax, aMmfreecontiguo; "MmFreeContiguousMemory"
0x14063af26  mov     [rbp+290h+var_90], rax
0x14063af2d  lea     rax, VfPtMmFreeContiguousMemory_Entry
0x14063af34  mov     [rbp+290h+var_80], rax
0x14063af3b  lea     rax, aMmallocatemapp_2; "MmAllocateMappingAddress"
0x14063af42  mov     [rbp+290h+var_70], rax
0x14063af49  lea     rax, VfPtMmAllocateMappingAddress_Exit
0x14063af50  mov     [rbp+290h+var_58], rax
0x14063af57  lea     rax, aMmallocatemapp_0; "MmAllocateMappingAddressEx"
0x14063af5e  mov     [rbp+290h+var_50], rax
0x14063af65  lea     rax, VfPtMmAllocateMappingAddressEx_Exit
0x14063af6c  mov     [rbp+290h+var_38], rax
0x14063af73  lea     rax, aMmfreemappinga; "MmFreeMappingAddress"
0x14063af7a  mov     [rbp+290h+var_30], rax
0x14063af81  lea     rax, VfPtMmFreeMappingAddress_Entry
0x14063af88  mov     [rbp+290h+var_20], rax
0x14063af8f  mov     [rbp+290h+var_1C0], rdi
0x14063af96  mov     [rbp+290h+var_1A8], 0E7h
0x14063afa0  mov     [rbp+290h+var_1A0], rdi
0x14063afa7  mov     [rbp+290h+var_188], 0E3h
0x14063afb1  mov     [rbp+290h+var_180], rdi
0x14063afb8  mov     [rbp+290h+var_168], 0E0h
0x14063afc2  mov     [rbp+290h+var_160], rdi
0x14063afc9  mov     [rbp+290h+var_158], rdi
0x14063afd0  mov     [rbp+290h+var_148], 0E1h
0x14063afda  mov     [rbp+290h+var_138], rdi
0x14063afe1  mov     [rbp+290h+var_128], 0EEh
0x14063afeb  mov     [rbp+290h+var_120], rdi
0x14063aff2  mov     [rbp+290h+var_108], 0EDh
0x14063affc  mov     [rbp+290h+var_100], rdi
0x14063b003  mov     [rbp+290h+var_E8], 0ECh
0x14063b00d  mov     [rbp+290h+var_E0], rdi
0x14063b014  mov     [rbp+290h+var_C8], 0EBh
0x14063b01e  mov     [rbp+290h+var_C0], rdi
0x14063b025  mov     [rbp+290h+var_A8], 0EAh
0x14063b02f  mov     [rbp+290h+var_A0], rdi
0x14063b036  mov     [rbp+290h+var_88], 0E2h
0x14063b040  mov     [rbp+290h+var_78], rdi
0x14063b047  mov     [rbp+290h+var_68], 0E9h
0x14063b051  mov     [rbp+290h+var_60], rdi
0x14063b058  mov     [rbp+290h+var_48], 1D1h
0x14063b062  mov     [rbp+290h+var_40], rdi
0x14063b069  mov     [rbp+290h+var_28], 1D2h
0x14063b073  mov     [rbp+290h+var_18], rdi
0x14063b07a  mov     edx, 1Bh
0x14063b07f  lea     r9, ViPoolTrackingSetting
0x14063b086  lea     rcx, [rsp+390h+var_370]
0x14063b08b  lea     r8d, [rdx-18h]
0x14063b08f  call    DifRegisterPlugin
0x14063b094  mov     ebx, eax
0x14063b096  test    eax, eax
0x14063b098  jns     short loc_14063B09F
0x14063b09a  call    ViPtPluginUnload
0x14063b09f  mov     eax, ebx
0x14063b0a1  mov     rcx, [rbp+290h+var_10]
0x14063b0a8  xor     rcx, rsp; StackCookie
0x14063b0ab  call    __security_check_cookie
0x14063b0b0  lea     r11, [rsp+390h+var_s0]
0x14063b0b8  mov     rbx, [r11+10h]
0x14063b0bc  mov     rdi, [r11+18h]
0x14063b0c0  mov     rsp, r11
0x14063b0c3  pop     rbp
0x14063b0c4  retn
```
