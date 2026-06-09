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
__int64 VfRlrsEntry()
{
  unsigned int v0; // ebx
  const char *v2; // [rsp+20h] [rbp-E0h] BYREF
  int v3; // [rsp+28h] [rbp-D8h]
  __int64 v4; // [rsp+30h] [rbp-D0h]
  __int64 v5; // [rsp+38h] [rbp-C8h]
  const char *v6; // [rsp+40h] [rbp-C0h]
  int v7; // [rsp+48h] [rbp-B8h]
  __int64 v8; // [rsp+50h] [rbp-B0h]
  __int64 v9; // [rsp+58h] [rbp-A8h]
  const char *v10; // [rsp+60h] [rbp-A0h]
  int v11; // [rsp+68h] [rbp-98h]
  __int64 v12; // [rsp+70h] [rbp-90h]
  __int64 v13; // [rsp+78h] [rbp-88h]
  const char *v14; // [rsp+80h] [rbp-80h]
  int v15; // [rsp+88h] [rbp-78h]
  __int64 v16; // [rsp+90h] [rbp-70h]
  __int64 v17; // [rsp+98h] [rbp-68h]
  const char *v18; // [rsp+A0h] [rbp-60h]
  int v19; // [rsp+A8h] [rbp-58h]
  __int64 v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+B8h] [rbp-48h]
  const char *v22; // [rsp+C0h] [rbp-40h]
  int v23; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v24)(); // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  const char *v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v28)(); // [rsp+F0h] [rbp-10h]
  __int64 v29; // [rsp+F8h] [rbp-8h]
  const char *v30; // [rsp+100h] [rbp+0h]
  int v31; // [rsp+108h] [rbp+8h]
  __int64 v32; // [rsp+110h] [rbp+10h]
  __int64 v33; // [rsp+118h] [rbp+18h]
  const char *v34; // [rsp+120h] [rbp+20h]
  int v35; // [rsp+128h] [rbp+28h]
  __int64 v36; // [rsp+130h] [rbp+30h]
  __int64 v37; // [rsp+138h] [rbp+38h]
  const char *v38; // [rsp+140h] [rbp+40h]
  int v39; // [rsp+148h] [rbp+48h]
  __int64 v40; // [rsp+150h] [rbp+50h]
  __int64 v41; // [rsp+158h] [rbp+58h]
  const char *v42; // [rsp+160h] [rbp+60h]
  int v43; // [rsp+168h] [rbp+68h]
  __int64 v44; // [rsp+170h] [rbp+70h]
  __int64 v45; // [rsp+178h] [rbp+78h]
  const char *v46; // [rsp+180h] [rbp+80h]
  int v47; // [rsp+188h] [rbp+88h]
  __int64 v48; // [rsp+190h] [rbp+90h]
  __int64 v49; // [rsp+198h] [rbp+98h]
  const char *v50; // [rsp+1A0h] [rbp+A0h]
  int v51; // [rsp+1A8h] [rbp+A8h]
  __int64 v52; // [rsp+1B0h] [rbp+B0h]
  __int64 v53; // [rsp+1B8h] [rbp+B8h]
  const char *v54; // [rsp+1C0h] [rbp+C0h]
  int v55; // [rsp+1C8h] [rbp+C8h]
  __int64 v56; // [rsp+1D0h] [rbp+D0h]
  __int64 v57; // [rsp+1D8h] [rbp+D8h]
  const char *v58; // [rsp+1E0h] [rbp+E0h]
  int v59; // [rsp+1E8h] [rbp+E8h]
  __int64 v60; // [rsp+1F0h] [rbp+F0h]
  __int64 v61; // [rsp+1F8h] [rbp+F8h]
  const char *v62; // [rsp+200h] [rbp+100h]
  int v63; // [rsp+208h] [rbp+108h]
  __int64 v64; // [rsp+210h] [rbp+110h]
  __int64 v65; // [rsp+218h] [rbp+118h]
  const char *v66; // [rsp+220h] [rbp+120h]
  int v67; // [rsp+228h] [rbp+128h]
  __int64 v68; // [rsp+230h] [rbp+130h]
  __int64 v69; // [rsp+238h] [rbp+138h]
  const char *v70; // [rsp+240h] [rbp+140h]
  int v71; // [rsp+248h] [rbp+148h]
  __int64 (__fastcall *v72)(); // [rsp+250h] [rbp+150h]
  __int64 v73; // [rsp+258h] [rbp+158h]
  const char *v74; // [rsp+260h] [rbp+160h]
  int v75; // [rsp+268h] [rbp+168h]
  __int64 v76; // [rsp+270h] [rbp+170h]
  __int64 v77; // [rsp+278h] [rbp+178h]
  const char *v78; // [rsp+280h] [rbp+180h]
  int v79; // [rsp+288h] [rbp+188h]
  __int64 v80; // [rsp+290h] [rbp+190h]
  __int64 v81; // [rsp+298h] [rbp+198h]
  const char *v82; // [rsp+2A0h] [rbp+1A0h]
  int v83; // [rsp+2A8h] [rbp+1A8h]
  __int64 v84; // [rsp+2B0h] [rbp+1B0h]
  __int64 v85; // [rsp+2B8h] [rbp+1B8h]
  const char *v86; // [rsp+2C0h] [rbp+1C0h]
  int v87; // [rsp+2C8h] [rbp+1C8h]
  __int64 v88; // [rsp+2D0h] [rbp+1D0h]
  __int64 v89; // [rsp+2D8h] [rbp+1D8h]
  const char *v90; // [rsp+2E0h] [rbp+1E0h]
  int v91; // [rsp+2E8h] [rbp+1E8h]
  __int64 v92; // [rsp+2F0h] [rbp+1F0h]
  __int64 v93; // [rsp+2F8h] [rbp+1F8h]
  const char *v94; // [rsp+300h] [rbp+200h]
  int v95; // [rsp+308h] [rbp+208h]
  __int64 v96; // [rsp+310h] [rbp+210h]
  __int64 v97; // [rsp+318h] [rbp+218h]
  const char *v98; // [rsp+320h] [rbp+220h]
  int v99; // [rsp+328h] [rbp+228h]
  __int64 v100; // [rsp+330h] [rbp+230h]
  __int64 v101; // [rsp+338h] [rbp+238h]
  const char *v102; // [rsp+340h] [rbp+240h]
  int v103; // [rsp+348h] [rbp+248h]
  __int64 v104; // [rsp+350h] [rbp+250h]
  __int64 v105; // [rsp+358h] [rbp+258h]
  const char *v106; // [rsp+360h] [rbp+260h]
  int v107; // [rsp+368h] [rbp+268h]
  __int64 v108; // [rsp+370h] [rbp+270h]
  __int64 v109; // [rsp+378h] [rbp+278h]

  v3 = 413;
  v4 = 0;
  qword_140EF2008 = (__int64)ViRlrsUnload;
  v2 = "ExAllocatePool";
  v6 = "ExAllocatePoolWithTag";
  v10 = "ExAllocatePoolWithTagPriority";
  v14 = "ExAllocatePool2";
  v18 = "ExAllocatePool3";
  v22 = "MmProbeAndLockPages";
  v24 = ViRlrsMmProbeAndLockProcessPages_Entry;
  v26 = "MmProbeAndLockProcessPages";
  v28 = ViRlrsMmProbeAndLockProcessPages_Entry;
  v30 = "MmMapIoSpace";
  v34 = "MmAllocateMappingAddress";
  v38 = "MmAllocateContiguousMemory";
  v42 = "MmAllocateContiguousMemorySpecifyCacheNode";
  v46 = "MmAllocateContiguousMemorySpecifyCache";
  v50 = "MmAllocateContiguousNodeMemory";
  v54 = "MmAllocateNonCachedMemory";
  v58 = "MmAllocatePagesForMdl";
  v5 = 0;
  v7 = 414;
  v8 = 0;
  v9 = 0;
  v11 = 415;
  v12 = 0;
  v13 = 0;
  v15 = 419;
  v16 = 0;
  v17 = 0;
  v19 = 418;
  v20 = 0;
  v21 = 0;
  v23 = 217;
  v25 = 0;
  v27 = 216;
  v29 = 0;
  v31 = 221;
  v32 = 0;
  v33 = 0;
  v35 = 233;
  v36 = 0;
  v37 = 0;
  v39 = 238;
  v40 = 0;
  v41 = 0;
  v43 = 235;
  v44 = 0;
  v45 = 0;
  v47 = 236;
  v48 = 0;
  v49 = 0;
  v51 = 234;
  v52 = 0;
  v53 = 0;
  v55 = 231;
  v56 = 0;
  v57 = 0;
  v59 = 230;
  v60 = 0;
  v61 = 0;
  v62 = "MmAllocatePagesForMdlEx";
  v63 = 229;
  v66 = "MmAllocateNodePagesForMdlEx";
  v64 = 0;
  v70 = "MmMapLockedPages";
  v65 = 0;
  v72 = ViRlrsMmMapLockedPages_Entry;
  v67 = 232;
  v74 = "IoAllocateDriverObjectExtension";
  v78 = "IoAllocateErrorLogEntry";
  v82 = "IoSetCompletionRoutineEx";
  v86 = "IoAllocateIrp";
  v90 = "IoAllocateWorkItem";
  v94 = "IoAllocateMdl";
  v98 = "KeWaitForSingleObject";
  v102 = "KeWaitForMultipleObjects";
  v106 = "KeDelayExecutionThread";
  v68 = 0;
  v69 = 0;
  v71 = 220;
  v73 = 0;
  v75 = 369;
  v76 = 0;
  v77 = 0;
  v79 = 368;
  v80 = 0;
  v81 = 0;
  v83 = 314;
  v84 = 0;
  v85 = 0;
  v87 = 366;
  v88 = 0;
  v89 = 0;
  v91 = 364;
  v92 = 0;
  v93 = 0;
  v95 = 365;
  v96 = 0;
  v97 = 0;
  v99 = 240;
  v100 = 0;
  v101 = 0;
  v103 = 241;
  v104 = 0;
  v105 = 0;
  v107 = 289;
  v108 = 0;
  v109 = 0;
  v0 = DifRegisterPlugin((__int64)&v2, 0x1Bu, 2u, (__int64)&ViRandomFailureSetting);
  VfFaultsInitPhase0();
  if ( VfDifRunningWithoutReboot )
    VfFaultsInitPhase1();
  return v0;
}

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
