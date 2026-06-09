# VfRlrsEntry

- ea: `0x14063f2f0`
- end: `0x14063f71e`
- name: `VfRlrsEntry`
- size: `1070`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14053fcf0`
- `0x14063f2f0`
- `0x1406dc8c0`
- `0x140bd5374`
- `0x140bd54a0`

## string_xrefs

- `0x14063f3e6`: `MmAllocateNonCachedMemory`
- `0x14063f3ca`: `MmAllocateContiguousMemorySpecifyCache`
- `0x14063f3bf`: `MmAllocateContiguousMemorySpecifyCacheNode`
- `0x14063f55e`: `IoAllocateDriverObjectExtension`
- `0x14063f5d8`: `KeDelayExecutionThread`
- `0x14063f584`: `IoSetCompletionRoutineEx`

## pseudocode

```c

```

## disassembly

```asm
0x14063f2f0  mov     [rsp-8+arg_0], rbx
0x14063f2f5  mov     [rsp-8+arg_8], rdi
0x14063f2fa  push    rbp
0x14063f2fb  lea     rbp, [rsp-290h]
0x14063f303  sub     rsp, 390h
0x14063f30a  mov     rax, cs:__security_cookie
0x14063f311  xor     rax, rsp
0x14063f314  mov     [rbp+290h+var_10], rax
0x14063f31b  xor     edi, edi
0x14063f31d  mov     [rsp+390h+var_368], 19Dh
0x14063f325  lea     rax, ViRlrsUnload
0x14063f32c  mov     [rsp+390h+var_360], rdi
0x14063f331  mov     cs:qword_140EF2008, rax
0x14063f338  lea     rax, aExallocatepool_0; "ExAllocatePool"
0x14063f33f  mov     [rsp+390h+var_370], rax
0x14063f344  lea     rax, aExallocatepool_1; "ExAllocatePoolWithTag"
0x14063f34b  mov     [rsp+390h+var_350], rax
0x14063f350  lea     rax, aExallocatepool_15; "ExAllocatePoolWithTagPriority"
0x14063f357  mov     [rsp+390h+var_330], rax
0x14063f35c  lea     rax, aExallocatepool; "ExAllocatePool2"
0x14063f363  mov     [rbp+290h+var_310], rax
0x14063f367  lea     rax, aExallocatepool_13; "ExAllocatePool3"
0x14063f36e  mov     [rbp+290h+var_2F0], rax
0x14063f372  lea     rax, aMmprobeandlock; "MmProbeAndLockPages"
0x14063f379  mov     [rbp+290h+var_2D0], rax
0x14063f37d  lea     rax, ViRlrsMmProbeAndLockProcessPages_Entry
0x14063f384  mov     [rbp+290h+var_2C0], rax
0x14063f388  lea     rax, aMmprobeandlock_2; "MmProbeAndLockProcessPages"
0x14063f38f  mov     [rbp+290h+var_2B0], rax
0x14063f393  lea     rax, ViRlrsMmProbeAndLockProcessPages_Entry
0x14063f39a  mov     [rbp+290h+var_2A0], rax
0x14063f39e  lea     rax, aMmmapiospace; "MmMapIoSpace"
0x14063f3a5  mov     [rbp+290h+var_290], rax
0x14063f3a9  lea     rax, aMmallocatemapp_2; "MmAllocateMappingAddress"
0x14063f3b0  mov     [rbp+290h+var_270], rax
0x14063f3b4  lea     rax, aMmallocatecont_0; "MmAllocateContiguousMemory"
0x14063f3bb  mov     [rbp+290h+var_250], rax
0x14063f3bf  lea     rax, aMmallocatecont_11; "MmAllocateContiguousMemorySpecifyCacheN"...
0x14063f3c6  mov     [rbp+290h+var_230], rax
0x14063f3ca  lea     rax, aMmallocatecont_9; "MmAllocateContiguousMemorySpecifyCache"
0x14063f3d1  mov     [rbp+290h+var_210], rax
0x14063f3d8  lea     rax, aMmallocatecont_7; "MmAllocateContiguousNodeMemory"
0x14063f3df  mov     [rbp+290h+var_1F0], rax
0x14063f3e6  lea     rax, aMmallocatenonc_0; "MmAllocateNonCachedMemory"
0x14063f3ed  mov     [rbp+290h+var_1D0], rax
0x14063f3f4  lea     rax, aMmallocatepage_3; "MmAllocatePagesForMdl"
0x14063f3fb  mov     [rbp+290h+var_1B0], rax
0x14063f402  lea     rax, aMmallocatepage; "MmAllocatePagesForMdlEx"
0x14063f409  mov     [rsp+390h+var_358], rdi
0x14063f40e  mov     [rsp+390h+var_348], 19Eh
0x14063f416  mov     [rsp+390h+var_340], rdi
0x14063f41b  mov     [rsp+390h+var_338], rdi
0x14063f420  mov     [rsp+390h+var_328], 19Fh
0x14063f428  mov     [rsp+390h+var_320], rdi
0x14063f42d  mov     [rsp+390h+var_318], rdi
0x14063f432  mov     [rbp+290h+var_308], 1A3h
0x14063f439  mov     [rbp+290h+var_300], rdi
0x14063f43d  mov     [rbp+290h+var_2F8], rdi
0x14063f441  mov     [rbp+290h+var_2E8], 1A2h
0x14063f448  mov     [rbp+290h+var_2E0], rdi
0x14063f44c  mov     [rbp+290h+var_2D8], rdi
0x14063f450  mov     [rbp+290h+var_2C8], 0D9h
0x14063f457  mov     [rbp+290h+var_2B8], rdi
0x14063f45b  mov     [rbp+290h+var_2A8], 0D8h
0x14063f462  mov     [rbp+290h+var_298], rdi
0x14063f466  mov     [rbp+290h+var_288], 0DDh
0x14063f46d  mov     [rbp+290h+var_280], rdi
0x14063f471  mov     [rbp+290h+var_278], rdi
0x14063f475  mov     [rbp+290h+var_268], 0E9h
0x14063f47c  mov     [rbp+290h+var_260], rdi
0x14063f480  mov     [rbp+290h+var_258], rdi
0x14063f484  mov     [rbp+290h+var_248], 0EEh
0x14063f48b  mov     [rbp+290h+var_240], rdi
0x14063f48f  mov     [rbp+290h+var_238], rdi
0x14063f493  mov     [rbp+290h+var_228], 0EBh
0x14063f49a  mov     [rbp+290h+var_220], rdi
0x14063f49e  mov     [rbp+290h+var_218], rdi
0x14063f4a2  mov     [rbp+290h+var_208], 0ECh
0x14063f4ac  mov     [rbp+290h+var_200], rdi
0x14063f4b3  mov     [rbp+290h+var_1F8], rdi
0x14063f4ba  mov     [rbp+290h+var_1E8], 0EAh
0x14063f4c4  mov     [rbp+290h+var_1E0], rdi
0x14063f4cb  mov     [rbp+290h+var_1D8], rdi
0x14063f4d2  mov     [rbp+290h+var_1C8], 0E7h
0x14063f4dc  mov     [rbp+290h+var_1C0], rdi
0x14063f4e3  mov     [rbp+290h+var_1B8], rdi
0x14063f4ea  mov     [rbp+290h+var_1A8], 0E6h
0x14063f4f4  mov     [rbp+290h+var_1A0], rdi
0x14063f4fb  mov     [rbp+290h+var_198], rdi
0x14063f502  mov     [rbp+290h+var_190], rax
0x14063f509  lea     r9, ViRandomFailureSetting
0x14063f510  lea     rax, aMmallocatenode; "MmAllocateNodePagesForMdlEx"
0x14063f517  mov     [rbp+290h+var_188], 0E5h
0x14063f521  mov     [rbp+290h+var_170], rax
0x14063f528  lea     edx, [rdi+1Bh]
0x14063f52b  lea     rax, aMmmaplockedpag_3; "MmMapLockedPages"
0x14063f532  mov     [rbp+290h+var_180], rdi
0x14063f539  mov     [rbp+290h+var_150], rax
0x14063f540  lea     r8d, [rdi+2]
0x14063f544  lea     rax, ViRlrsMmMapLockedPages_Entry
0x14063f54b  mov     [rbp+290h+var_178], rdi
0x14063f552  mov     [rbp+290h+var_140], rax
0x14063f559  lea     rcx, [rsp+390h+var_370]
0x14063f55e  lea     rax, aIoallocatedriv; "IoAllocateDriverObjectExtension"
0x14063f565  mov     [rbp+290h+var_168], 0E8h
0x14063f56f  mov     [rbp+290h+var_130], rax
0x14063f576  lea     rax, aIoallocateerro_0; "IoAllocateErrorLogEntry"
0x14063f57d  mov     [rbp+290h+var_110], rax
0x14063f584  lea     rax, aIosetcompletio_0; "IoSetCompletionRoutineEx"
0x14063f58b  mov     [rbp+290h+var_F0], rax
0x14063f592  lea     rax, aIoallocateirp_1; "IoAllocateIrp"
0x14063f599  mov     [rbp+290h+var_D0], rax
0x14063f5a0  lea     rax, aIoallocatework_1; "IoAllocateWorkItem"
0x14063f5a7  mov     [rbp+290h+var_B0], rax
0x14063f5ae  lea     rax, aIoallocatemdl_0; "IoAllocateMdl"
0x14063f5b5  mov     [rbp+290h+var_90], rax
0x14063f5bc  lea     rax, aKewaitforsingl_0; "KeWaitForSingleObject"
0x14063f5c3  mov     [rbp+290h+var_70], rax
0x14063f5ca  lea     rax, aKewaitformulti_0; "KeWaitForMultipleObjects"
0x14063f5d1  mov     [rbp+290h+var_50], rax
0x14063f5d8  lea     rax, aKedelayexecuti_0; "KeDelayExecutionThread"
0x14063f5df  mov     [rbp+290h+var_30], rax
0x14063f5e6  mov     [rbp+290h+var_160], rdi
0x14063f5ed  mov     [rbp+290h+var_158], rdi
0x14063f5f4  mov     [rbp+290h+var_148], 0DCh
0x14063f5fe  mov     [rbp+290h+var_138], rdi
0x14063f605  mov     [rbp+290h+var_128], 171h
0x14063f60f  mov     [rbp+290h+var_120], rdi
0x14063f616  mov     [rbp+290h+var_118], rdi
0x14063f61d  mov     [rbp+290h+var_108], 170h
0x14063f627  mov     [rbp+290h+var_100], rdi
0x14063f62e  mov     [rbp+290h+var_F8], rdi
0x14063f635  mov     [rbp+290h+var_E8], 13Ah
0x14063f63f  mov     [rbp+290h+var_E0], rdi
0x14063f646  mov     [rbp+290h+var_D8], rdi
0x14063f64d  mov     [rbp+290h+var_C8], 16Eh
0x14063f657  mov     [rbp+290h+var_C0], rdi
0x14063f65e  mov     [rbp+290h+var_B8], rdi
0x14063f665  mov     [rbp+290h+var_A8], 16Ch
0x14063f66f  mov     [rbp+290h+var_A0], rdi
0x14063f676  mov     [rbp+290h+var_98], rdi
0x14063f67d  mov     [rbp+290h+var_88], 16Dh
0x14063f687  mov     [rbp+290h+var_80], rdi
0x14063f68e  mov     [rbp+290h+var_78], rdi
0x14063f695  mov     [rbp+290h+var_68], 0F0h
0x14063f69f  mov     [rbp+290h+var_60], rdi
0x14063f6a6  mov     [rbp+290h+var_58], rdi
0x14063f6ad  mov     [rbp+290h+var_48], 0F1h
0x14063f6b7  mov     [rbp+290h+var_40], rdi
0x14063f6be  mov     [rbp+290h+var_38], rdi
0x14063f6c5  mov     [rbp+290h+var_28], 121h
0x14063f6cf  mov     [rbp+290h+var_20], rdi
0x14063f6d6  mov     [rbp+290h+var_18], rdi
0x14063f6dd  call    DifRegisterPlugin
0x14063f6e2  mov     ebx, eax
0x14063f6e4  call    VfFaultsInitPhase0
0x14063f6e9  cmp     cs:VfDifRunningWithoutReboot, dil
0x14063f6f0  jz      short loc_14063F6F7
0x14063f6f2  call    VfFaultsInitPhase1
0x14063f6f7  mov     eax, ebx
0x14063f6f9  mov     rcx, [rbp+290h+var_10]
0x14063f700  xor     rcx, rsp; StackCookie
0x14063f703  call    __security_check_cookie
0x14063f708  lea     r11, [rsp+390h+var_s0]
0x14063f710  mov     rbx, [r11+10h]
0x14063f714  mov     rdi, [r11+18h]
0x14063f718  mov     rsp, r11
0x14063f71b  pop     rbp
0x14063f71c  retn
```
