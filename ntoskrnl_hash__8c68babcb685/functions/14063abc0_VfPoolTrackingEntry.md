# VfPoolTrackingEntry

- ea: `0x14063abc0`
- end: `0x14063b0c6`
- name: `VfPoolTrackingEntry`
- size: `1286`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

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
__int64 VfPoolTrackingEntry()
{
  int inited; // ebx
  const char *v2; // [rsp+20h] [rbp-E0h] BYREF
  int v3; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall *v4)(); // [rsp+30h] [rbp-D0h]
  __int64 v5; // [rsp+38h] [rbp-C8h]
  const char *v6; // [rsp+40h] [rbp-C0h]
  int v7; // [rsp+48h] [rbp-B8h]
  __int64 (__fastcall *v8)(); // [rsp+50h] [rbp-B0h]
  __int64 v9; // [rsp+58h] [rbp-A8h]
  const char *v10; // [rsp+60h] [rbp-A0h]
  int v11; // [rsp+68h] [rbp-98h]
  __int64 v12; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v13)(); // [rsp+78h] [rbp-88h]
  const char *v14; // [rsp+80h] [rbp-80h]
  int v15; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v16)(); // [rsp+90h] [rbp-70h]
  __int64 v17; // [rsp+98h] [rbp-68h]
  const char *v18; // [rsp+A0h] [rbp-60h]
  int v19; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v20)(); // [rsp+B0h] [rbp-50h]
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
  __int64 (__fastcall *v32)(); // [rsp+110h] [rbp+10h]
  __int64 v33; // [rsp+118h] [rbp+18h]
  const char *v34; // [rsp+120h] [rbp+20h]
  int v35; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v36)(); // [rsp+130h] [rbp+30h]
  __int64 v37; // [rsp+138h] [rbp+38h]
  const char *v38; // [rsp+140h] [rbp+40h]
  int v39; // [rsp+148h] [rbp+48h]
  __int64 v40; // [rsp+150h] [rbp+50h]
  __int64 (__fastcall *v41)(); // [rsp+158h] [rbp+58h]
  const char *v42; // [rsp+160h] [rbp+60h]
  int v43; // [rsp+168h] [rbp+68h]
  __int64 v44; // [rsp+170h] [rbp+70h]
  __int64 v45; // [rsp+178h] [rbp+78h]
  const char *v46; // [rsp+180h] [rbp+80h]
  int v47; // [rsp+188h] [rbp+88h]
  __int64 v48; // [rsp+190h] [rbp+90h]
  __int64 (__fastcall *v49)(); // [rsp+198h] [rbp+98h]
  const char *v50; // [rsp+1A0h] [rbp+A0h]
  int v51; // [rsp+1A8h] [rbp+A8h]
  __int64 v52; // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v53)(); // [rsp+1B8h] [rbp+B8h]
  const char *v54; // [rsp+1C0h] [rbp+C0h]
  int v55; // [rsp+1C8h] [rbp+C8h]
  __int64 v56; // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v57)(); // [rsp+1D8h] [rbp+D8h]
  const char *v58; // [rsp+1E0h] [rbp+E0h]
  int v59; // [rsp+1E8h] [rbp+E8h]
  __int64 v60; // [rsp+1F0h] [rbp+F0h]
  __int64 (__fastcall *v61)(); // [rsp+1F8h] [rbp+F8h]
  const char *v62; // [rsp+200h] [rbp+100h]
  int v63; // [rsp+208h] [rbp+108h]
  __int64 v64; // [rsp+210h] [rbp+110h]
  __int64 (__fastcall *v65)(); // [rsp+218h] [rbp+118h]
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
  __int64 (__fastcall *v77)(); // [rsp+278h] [rbp+178h]
  const char *v78; // [rsp+280h] [rbp+180h]
  int v79; // [rsp+288h] [rbp+188h]
  __int64 v80; // [rsp+290h] [rbp+190h]
  __int64 (__fastcall *v81)(); // [rsp+298h] [rbp+198h]
  const char *v82; // [rsp+2A0h] [rbp+1A0h]
  int v83; // [rsp+2A8h] [rbp+1A8h]
  __int64 v84; // [rsp+2B0h] [rbp+1B0h]
  __int64 (__fastcall *v85)(); // [rsp+2B8h] [rbp+1B8h]
  const char *v86; // [rsp+2C0h] [rbp+1C0h]
  int v87; // [rsp+2C8h] [rbp+1C8h]
  __int64 v88; // [rsp+2D0h] [rbp+1D0h]
  __int64 (__fastcall *v89)(); // [rsp+2D8h] [rbp+1D8h]
  const char *v90; // [rsp+2E0h] [rbp+1E0h]
  int v91; // [rsp+2E8h] [rbp+1E8h]
  __int64 v92; // [rsp+2F0h] [rbp+1F0h]
  __int64 (__fastcall *v93)(); // [rsp+2F8h] [rbp+1F8h]
  const char *v94; // [rsp+300h] [rbp+200h]
  int v95; // [rsp+308h] [rbp+208h]
  __int64 (__fastcall *v96)(); // [rsp+310h] [rbp+210h]
  __int64 v97; // [rsp+318h] [rbp+218h]
  const char *v98; // [rsp+320h] [rbp+220h]
  int v99; // [rsp+328h] [rbp+228h]
  __int64 v100; // [rsp+330h] [rbp+230h]
  __int64 (__fastcall *v101)(); // [rsp+338h] [rbp+238h]
  const char *v102; // [rsp+340h] [rbp+240h]
  int v103; // [rsp+348h] [rbp+248h]
  __int64 v104; // [rsp+350h] [rbp+250h]
  __int64 (__fastcall *v105)(); // [rsp+358h] [rbp+258h]
  const char *v106; // [rsp+360h] [rbp+260h]
  int v107; // [rsp+368h] [rbp+268h]
  __int64 (__fastcall *v108)(); // [rsp+370h] [rbp+270h]
  __int64 v109; // [rsp+378h] [rbp+278h]

  ViPtUnloadRundown.Count = 0;
  inited = ViPtInitCircularPoolTrace();
  if ( inited < 0 )
    goto LABEL_8;
  if ( (VfOptionFlags & 0x1000) != 0 )
    ViPtInitAvlTrees();
  if ( !VfDifRunningWithoutReboot && (VfOptionFlags & 0x800) == 0 )
    MmTrackLockedPages = 1;
  v3 = 413;
  qword_140EF24C8 = (__int64)ViPtPluginUnload;
  v2 = "ExAllocatePool";
  v4 = ViSpIoAllocateIrp_Exit;
  v6 = "ExAllocatePool2";
  v8 = ViSpIoAllocateIrp_Exit;
  v10 = "ExAllocatePool3";
  v13 = ViSpIoAllocateIrp_Exit;
  v14 = "ExAllocatePoolWithTag";
  v16 = ViSpIoAllocateIrp_Exit;
  v18 = "ExAllocatePoolWithTagPriority";
  v20 = ViSpIoAllocateIrp_Exit;
  v22 = "ExAllocatePoolWithQuota";
  v24 = ViSpIoAllocateIrp_Exit;
  v26 = "ExAllocatePoolWithQuotaTag";
  v28 = ViSpIoAllocateIrp_Exit;
  v30 = "ExFreePool";
  v32 = ViSpIoAllocateIrp_Exit;
  v34 = "ExFreePoolWithTag";
  v36 = ViSpIoAllocateIrp_Exit;
  v38 = "IoAllocateMdl";
  v41 = VfPtIoAllocateMdl_Exit;
  v42 = "IoFreeMdl";
  v46 = "MmAllocatePagesForMdl";
  v49 = VfPtMmAllocatePagesForMdl_Exit;
  v50 = "MmAllocatePagesForMdlEx";
  v53 = VfPtMmAllocatePagesForMdlEx_Exit;
  v54 = "MmAllocateNodePagesForMdlEx";
  v5 = 0;
  v7 = 419;
  v9 = 0;
  v11 = 418;
  v12 = 0;
  v15 = 414;
  v17 = 0;
  v19 = 415;
  v21 = 0;
  v23 = 416;
  v25 = 0;
  v27 = 417;
  v29 = 0;
  v31 = 401;
  v33 = 0;
  v35 = 400;
  v37 = 0;
  v39 = 365;
  v40 = 0;
  v43 = 339;
  v44 = 0;
  v45 = 0;
  v47 = 230;
  v48 = 0;
  v51 = 229;
  v52 = 0;
  v55 = 232;
  v57 = VfPtMmAllocateNodePagesForMdlEx_Exit;
  v58 = "MmAllocateNonCachedMemory";
  v61 = VfPtMmAllocateNonCachedMemory_Exit;
  v62 = "MmCreateMdl";
  v65 = VfPtMmCreateMdl_Exit;
  v66 = "MmFreePagesFromMdl";
  v70 = "MmFreeNonCachedMemory";
  v72 = VfPtMmFreeNonCachedMemory_Entry;
  v74 = "MmAllocateContiguousMemory";
  v77 = VfPtMmAllocateContiguousMemory_Exit;
  v78 = "MmAllocateContiguousMemoryEx";
  v81 = VfPtMmAllocateContiguousMemoryEx_Exit;
  v82 = "MmAllocateContiguousMemorySpecifyCache";
  v85 = VfPtMmAllocateContiguousMemorySpecifyCache_Exit;
  v86 = "MmAllocateContiguousMemorySpecifyCacheNode";
  v89 = VfPtMmAllocateContiguousMemorySpecifyCache_Exit;
  v90 = "MmAllocateContiguousNodeMemory";
  v93 = VfPtMmAllocateContiguousMemorySpecifyCache_Exit;
  v94 = "MmFreeContiguousMemory";
  v96 = VfPtMmFreeContiguousMemory_Entry;
  v98 = "MmAllocateMappingAddress";
  v101 = VfPtMmAllocateMappingAddress_Exit;
  v102 = "MmAllocateMappingAddressEx";
  v105 = VfPtMmAllocateMappingAddressEx_Exit;
  v106 = "MmFreeMappingAddress";
  v108 = VfPtMmFreeMappingAddress_Entry;
  v56 = 0;
  v59 = 231;
  v60 = 0;
  v63 = 227;
  v64 = 0;
  v67 = 224;
  v68 = 0;
  v69 = 0;
  v71 = 225;
  v73 = 0;
  v75 = 238;
  v76 = 0;
  v79 = 237;
  v80 = 0;
  v83 = 236;
  v84 = 0;
  v87 = 235;
  v88 = 0;
  v91 = 234;
  v92 = 0;
  v95 = 226;
  v97 = 0;
  v99 = 233;
  v100 = 0;
  v103 = 465;
  v104 = 0;
  v107 = 466;
  v109 = 0;
  inited = DifRegisterPlugin((__int64)&v2, 0x1Bu, 3u, (__int64)&ViPoolTrackingSetting);
  if ( inited < 0 )
LABEL_8:
    ViPtPluginUnload();
  return (unsigned int)inited;
}

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
