# VfSpecialPoolEntry

- ea: `0x1406dabe0`
- end: `0x1406db0fe`
- name: `VfSpecialPoolEntry`
- size: `1310`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14053fcf0`
- `0x1406dc8c0`

## string_xrefs

- `0x1406daf13`: `IoSetCompletionRoutineEx`
- `0x1406daea3`: `RtlCreateUnicodeString`
- `0x1406db044`: `MmMapLockedPagesSpecifyCache`

## pseudocode

```c
__int64 VfSpecialPoolEntry()
{
  const char *v1; // [rsp+20h] [rbp-E0h] BYREF
  int v2; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall *v3)(); // [rsp+30h] [rbp-D0h]
  __int64 v4; // [rsp+38h] [rbp-C8h]
  const char *v5; // [rsp+40h] [rbp-C0h]
  int v6; // [rsp+48h] [rbp-B8h]
  __int64 (__fastcall *v7)(); // [rsp+50h] [rbp-B0h]
  __int64 v8; // [rsp+58h] [rbp-A8h]
  const char *v9; // [rsp+60h] [rbp-A0h]
  int v10; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v11)(); // [rsp+70h] [rbp-90h]
  __int64 v12; // [rsp+78h] [rbp-88h]
  const char *v13; // [rsp+80h] [rbp-80h]
  int v14; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v15)(); // [rsp+90h] [rbp-70h]
  __int64 v16; // [rsp+98h] [rbp-68h]
  const char *v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v19)(); // [rsp+B0h] [rbp-50h]
  __int64 v20; // [rsp+B8h] [rbp-48h]
  const char *v21; // [rsp+C0h] [rbp-40h]
  int v22; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v23)(); // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+D8h] [rbp-28h]
  const char *v25; // [rsp+E0h] [rbp-20h]
  int v26; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v27)(); // [rsp+F0h] [rbp-10h]
  __int64 v28; // [rsp+F8h] [rbp-8h]
  const char *v29; // [rsp+100h] [rbp+0h]
  int v30; // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v31)(); // [rsp+110h] [rbp+10h]
  __int64 v32; // [rsp+118h] [rbp+18h]
  const char *v33; // [rsp+120h] [rbp+20h]
  int v34; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v35)(); // [rsp+130h] [rbp+30h]
  __int64 v36; // [rsp+138h] [rbp+38h]
  const char *v37; // [rsp+140h] [rbp+40h]
  int v38; // [rsp+148h] [rbp+48h]
  __int64 v39; // [rsp+150h] [rbp+50h]
  __int64 (__fastcall *v40)(); // [rsp+158h] [rbp+58h]
  const char *v41; // [rsp+160h] [rbp+60h]
  int v42; // [rsp+168h] [rbp+68h]
  __int64 v43; // [rsp+170h] [rbp+70h]
  __int64 (__fastcall *v44)(); // [rsp+178h] [rbp+78h]
  const char *v45; // [rsp+180h] [rbp+80h]
  int v46; // [rsp+188h] [rbp+88h]
  __int64 v47; // [rsp+190h] [rbp+90h]
  __int64 (__fastcall *v48)(); // [rsp+198h] [rbp+98h]
  const char *v49; // [rsp+1A0h] [rbp+A0h]
  int v50; // [rsp+1A8h] [rbp+A8h]
  __int64 v51; // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v52)(); // [rsp+1B8h] [rbp+B8h]
  const char *v53; // [rsp+1C0h] [rbp+C0h]
  int v54; // [rsp+1C8h] [rbp+C8h]
  __int64 v55; // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v56)(); // [rsp+1D8h] [rbp+D8h]
  const char *v57; // [rsp+1E0h] [rbp+E0h]
  int v58; // [rsp+1E8h] [rbp+E8h]
  __int64 v59; // [rsp+1F0h] [rbp+F0h]
  __int64 (__fastcall *v60)(); // [rsp+1F8h] [rbp+F8h]
  const char *v61; // [rsp+200h] [rbp+100h]
  int v62; // [rsp+208h] [rbp+108h]
  __int64 v63; // [rsp+210h] [rbp+110h]
  __int64 (__fastcall *v64)(); // [rsp+218h] [rbp+118h]
  const char *v65; // [rsp+220h] [rbp+120h]
  int v66; // [rsp+228h] [rbp+128h]
  __int64 v67; // [rsp+230h] [rbp+130h]
  __int64 (__fastcall *v68)(); // [rsp+238h] [rbp+138h]
  const char *v69; // [rsp+240h] [rbp+140h]
  int v70; // [rsp+248h] [rbp+148h]
  __int64 v71; // [rsp+250h] [rbp+150h]
  __int64 (__fastcall *v72)(); // [rsp+258h] [rbp+158h]
  const char *v73; // [rsp+260h] [rbp+160h]
  int v74; // [rsp+268h] [rbp+168h]
  __int64 v75; // [rsp+270h] [rbp+170h]
  __int64 (__fastcall *v76)(); // [rsp+278h] [rbp+178h]
  const char *v77; // [rsp+280h] [rbp+180h]
  int v78; // [rsp+288h] [rbp+188h]
  __int64 v79; // [rsp+290h] [rbp+190h]
  __int64 (__fastcall *v80)(); // [rsp+298h] [rbp+198h]
  const char *v81; // [rsp+2A0h] [rbp+1A0h]
  int v82; // [rsp+2A8h] [rbp+1A8h]
  __int64 v83; // [rsp+2B0h] [rbp+1B0h]
  __int64 (__fastcall *v84)(); // [rsp+2B8h] [rbp+1B8h]
  const char *v85; // [rsp+2C0h] [rbp+1C0h]
  int v86; // [rsp+2C8h] [rbp+1C8h]
  __int64 v87; // [rsp+2D0h] [rbp+1D0h]
  __int64 (__fastcall *v88)(); // [rsp+2D8h] [rbp+1D8h]
  const char *v89; // [rsp+2E0h] [rbp+1E0h]
  int v90; // [rsp+2E8h] [rbp+1E8h]
  __int64 v91; // [rsp+2F0h] [rbp+1F0h]
  __int64 (__fastcall *v92)(); // [rsp+2F8h] [rbp+1F8h]
  const char *v93; // [rsp+300h] [rbp+200h]
  int v94; // [rsp+308h] [rbp+208h]
  __int64 v95; // [rsp+310h] [rbp+210h]
  __int64 (__fastcall *v96)(); // [rsp+318h] [rbp+218h]
  const char *v97; // [rsp+320h] [rbp+220h]
  int v98; // [rsp+328h] [rbp+228h]
  __int64 v99; // [rsp+330h] [rbp+230h]
  __int64 (__fastcall *v100)(); // [rsp+338h] [rbp+238h]
  const char *v101; // [rsp+340h] [rbp+240h]
  int v102; // [rsp+348h] [rbp+248h]
  __int64 (__fastcall *v103)(); // [rsp+350h] [rbp+250h]
  __int64 v104; // [rsp+358h] [rbp+258h]
  const char *v105; // [rsp+360h] [rbp+260h]
  int v106; // [rsp+368h] [rbp+268h]
  __int64 (__fastcall *v107)(); // [rsp+370h] [rbp+270h]
  __int64 v108; // [rsp+378h] [rbp+278h]
  const char *v109; // [rsp+380h] [rbp+280h]
  int v110; // [rsp+388h] [rbp+288h]
  __int64 (__fastcall *v111)(); // [rsp+390h] [rbp+290h]
  __int64 v112; // [rsp+398h] [rbp+298h]
  const char *v113; // [rsp+3A0h] [rbp+2A0h]
  int v114; // [rsp+3A8h] [rbp+2A8h]
  __int64 (__fastcall *v115)(); // [rsp+3B0h] [rbp+2B0h]
  __int64 v116; // [rsp+3B8h] [rbp+2B8h]
  const char *v117; // [rsp+3C0h] [rbp+2C0h]
  int v118; // [rsp+3C8h] [rbp+2C8h]
  __int64 (__fastcall *v119)(); // [rsp+3D0h] [rbp+2D0h]
  __int64 v120; // [rsp+3D8h] [rbp+2D8h]

  v2 = 413;
  v4 = 0;
  v1 = "ExAllocatePool";
  v3 = ViSpIoAllocateIrp_Exit;
  v5 = "ExAllocatePool2";
  v7 = ViSpIoAllocateIrp_Exit;
  v9 = "ExAllocatePool3";
  v11 = ViSpIoAllocateIrp_Exit;
  v13 = "ExAllocatePoolWithTag";
  v15 = ViSpIoAllocateIrp_Exit;
  v17 = "ExAllocatePoolWithTagPriority";
  v19 = ViSpIoAllocateIrp_Exit;
  v21 = "ExAllocatePoolWithQuota";
  v23 = ViSpIoAllocateIrp_Exit;
  v25 = "ExAllocatePoolWithQuotaTag";
  v27 = ViSpIoAllocateIrp_Exit;
  v29 = "ExFreePool";
  v31 = ViSpIoAllocateIrp_Exit;
  v33 = "ExFreePoolWithTag";
  v35 = ViSpIoAllocateIrp_Exit;
  v37 = "RtlAnsiStringToUnicodeString";
  v40 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v41 = "RtlUnicodeStringToAnsiString";
  v44 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v45 = "RtlUpcaseUnicodeStringToAnsiString";
  v48 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v49 = "RtlOemStringToUnicodeString";
  v52 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v53 = "RtlUnicodeStringToOemString";
  v6 = 419;
  v8 = 0;
  v10 = 418;
  v12 = 0;
  v14 = 414;
  v16 = 0;
  v18 = 415;
  v20 = 0;
  v22 = 416;
  v24 = 0;
  v26 = 417;
  v28 = 0;
  v30 = 401;
  v32 = 0;
  v34 = 400;
  v36 = 0;
  v38 = 169;
  v39 = 0;
  v42 = 156;
  v43 = 0;
  v46 = 152;
  v47 = 0;
  v50 = 160;
  v51 = 0;
  v54 = 154;
  v56 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v57 = "RtlUpcaseUnicodeStringToOemString";
  v60 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v61 = "RtlOemStringToCountedUnicodeString";
  v64 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v65 = "RtlUnicodeStringToCountedOemString";
  v68 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v69 = "RtlUpcaseUnicodeStringToCountedOemString";
  v72 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v73 = "RtlUpcaseUnicodeString";
  v76 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v77 = "RtlDowncaseUnicodeString";
  v80 = ViSpRtlUpcaseUnicodeStringToAnsiString_Exit;
  v81 = "RtlCreateUnicodeString";
  v84 = ViSpRtlCreateUnicodeString_Exit;
  v85 = "RtlDuplicateUnicodeString";
  v88 = ViSpRtlDuplicateUnicodeString_Exit;
  v89 = "IoAllocateIrp";
  v92 = ViSpIoAllocateIrp_Exit;
  v93 = "IoAllocateMdl";
  v96 = ViSpIoAllocateIrp_Exit;
  v97 = "IoSetCompletionRoutineEx";
  v100 = ViSpIoSetCompletionRoutineEx_Exit;
  v101 = "MmProbeAndLockPages";
  v103 = ViSpMmProbeAndLockPages_Entry;
  v105 = "MmProbeAndLockProcessPages";
  v107 = ViSpMmProbeAndLockProcessPages_Entry;
  v55 = 0;
  v58 = 150;
  v59 = 0;
  v62 = 161;
  v63 = 0;
  v66 = 155;
  v67 = 0;
  v70 = 151;
  v71 = 0;
  v74 = 153;
  v75 = 0;
  v78 = 163;
  v79 = 0;
  v82 = 165;
  v83 = 0;
  v86 = 162;
  v87 = 0;
  v90 = 366;
  v91 = 0;
  v94 = 365;
  v95 = 0;
  v98 = 314;
  v99 = 0;
  v102 = 217;
  v104 = 0;
  v106 = 216;
  v108 = 0;
  v109 = "MmMapLockedPagesSpecifyCache";
  v111 = ViSpMmMapLockedPagesSpecifyCache_Entry;
  v113 = "MmMapIoSpace";
  v115 = ViSpMmMapIoSpace_Entry;
  v117 = "MmMapLockedPages";
  v119 = ViSpMmMapLockedPages_Entry;
  v110 = 219;
  v112 = 0;
  v114 = 221;
  v116 = 0;
  v118 = 220;
  v120 = 0;
  return DifRegisterPlugin((__int64)&v1, 0x1Eu, 0, 0);
}

```

## disassembly

```asm
0x1406dabe0  push    rbp
0x1406dabe2  lea     rbp, [rsp-2F0h]
0x1406dabea  sub     rsp, 3F0h
0x1406dabf1  mov     rax, cs:__security_cookie
0x1406dabf8  xor     rax, rsp
0x1406dabfb  mov     [rbp+2F0h+var_10], rax
0x1406dac02  xor     ecx, ecx
0x1406dac04  mov     [rsp+3F0h+var_3C8], 19Dh
0x1406dac0c  lea     rax, aExallocatepool_0; "ExAllocatePool"
0x1406dac13  mov     [rsp+3F0h+var_3B8], rcx
0x1406dac18  mov     [rsp+3F0h+var_3D0], rax
0x1406dac1d  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dac24  mov     [rsp+3F0h+var_3C0], rax
0x1406dac29  lea     rax, aExallocatepool; "ExAllocatePool2"
0x1406dac30  mov     [rsp+3F0h+var_3B0], rax
0x1406dac35  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dac3c  mov     [rsp+3F0h+var_3A0], rax
0x1406dac41  lea     rax, aExallocatepool_13; "ExAllocatePool3"
0x1406dac48  mov     [rsp+3F0h+var_390], rax
0x1406dac4d  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dac54  mov     [rsp+3F0h+var_380], rax
0x1406dac59  lea     rax, aExallocatepool_1; "ExAllocatePoolWithTag"
0x1406dac60  mov     [rbp+2F0h+var_370], rax
0x1406dac64  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dac6b  mov     [rbp+2F0h+var_360], rax
0x1406dac6f  lea     rax, aExallocatepool_15; "ExAllocatePoolWithTagPriority"
0x1406dac76  mov     [rbp+2F0h+var_350], rax
0x1406dac7a  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dac81  mov     [rbp+2F0h+var_340], rax
0x1406dac85  lea     rax, aExallocatepool_14; "ExAllocatePoolWithQuota"
0x1406dac8c  mov     [rbp+2F0h+var_330], rax
0x1406dac90  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dac97  mov     [rbp+2F0h+var_320], rax
0x1406dac9b  lea     rax, aExallocatepool_16; "ExAllocatePoolWithQuotaTag"
0x1406daca2  mov     [rbp+2F0h+var_310], rax
0x1406daca6  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dacad  mov     [rbp+2F0h+var_300], rax
0x1406dacb1  lea     rax, aExfreepool_1; "ExFreePool"
0x1406dacb8  mov     [rbp+2F0h+var_2F0], rax
0x1406dacbc  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dacc3  mov     [rbp+2F0h+var_2E0], rax
0x1406dacc7  lea     rax, aExfreepoolwith_1; "ExFreePoolWithTag"
0x1406dacce  mov     [rbp+2F0h+var_2D0], rax
0x1406dacd2  lea     rax, ViSpIoAllocateIrp_Exit
0x1406dacd9  mov     [rbp+2F0h+var_2C0], rax
0x1406dacdd  lea     rax, aRtlansistringt_1; "RtlAnsiStringToUnicodeString"
0x1406dace4  mov     [rbp+2F0h+var_2B0], rax
0x1406dace8  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dacef  mov     [rbp+2F0h+var_298], rax
0x1406dacf3  lea     rax, aRtlunicodestri_5; "RtlUnicodeStringToAnsiString"
0x1406dacfa  mov     [rbp+2F0h+var_290], rax
0x1406dacfe  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dad05  mov     [rbp+2F0h+var_278], rax
0x1406dad09  lea     rax, aRtlupcaseunico_8; "RtlUpcaseUnicodeStringToAnsiString"
0x1406dad10  mov     [rbp+2F0h+var_270], rax
0x1406dad17  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dad1e  mov     [rbp+2F0h+var_258], rax
0x1406dad25  lea     rax, aRtloemstringto; "RtlOemStringToUnicodeString"
0x1406dad2c  mov     [rbp+2F0h+var_250], rax
0x1406dad33  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dad3a  mov     [rbp+2F0h+var_238], rax
0x1406dad41  lea     rax, aRtlunicodestri_1; "RtlUnicodeStringToOemString"
0x1406dad48  mov     [rbp+2F0h+var_230], rax
0x1406dad4f  mov     [rsp+3F0h+var_3A8], 1A3h
0x1406dad57  mov     [rsp+3F0h+var_398], rcx
0x1406dad5c  mov     [rsp+3F0h+var_388], 1A2h
0x1406dad64  mov     [rsp+3F0h+var_378], rcx
0x1406dad69  mov     [rbp+2F0h+var_368], 19Eh
0x1406dad70  mov     [rbp+2F0h+var_358], rcx
0x1406dad74  mov     [rbp+2F0h+var_348], 19Fh
0x1406dad7b  mov     [rbp+2F0h+var_338], rcx
0x1406dad7f  mov     [rbp+2F0h+var_328], 1A0h
0x1406dad86  mov     [rbp+2F0h+var_318], rcx
0x1406dad8a  mov     [rbp+2F0h+var_308], 1A1h
0x1406dad91  mov     [rbp+2F0h+var_2F8], rcx
0x1406dad95  mov     [rbp+2F0h+var_2E8], 191h
0x1406dad9c  mov     [rbp+2F0h+var_2D8], rcx
0x1406dada0  mov     [rbp+2F0h+var_2C8], 190h
0x1406dada7  mov     [rbp+2F0h+var_2B8], rcx
0x1406dadab  mov     [rbp+2F0h+var_2A8], 0A9h
0x1406dadb2  mov     [rbp+2F0h+var_2A0], rcx
0x1406dadb6  mov     [rbp+2F0h+var_288], 9Ch
0x1406dadbd  mov     [rbp+2F0h+var_280], rcx
0x1406dadc1  mov     [rbp+2F0h+var_268], 98h
0x1406dadcb  mov     [rbp+2F0h+var_260], rcx
0x1406dadd2  mov     [rbp+2F0h+var_248], 0A0h
0x1406daddc  mov     [rbp+2F0h+var_240], rcx
0x1406dade3  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dadea  mov     [rbp+2F0h+var_228], 9Ah
0x1406dadf4  mov     [rbp+2F0h+var_218], rax
0x1406dadfb  lea     rax, aRtlupcaseunico_2; "RtlUpcaseUnicodeStringToOemString"
0x1406dae02  mov     [rbp+2F0h+var_210], rax
0x1406dae09  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dae10  mov     [rbp+2F0h+var_1F8], rax
0x1406dae17  lea     rax, aRtloemstringto_0; "RtlOemStringToCountedUnicodeString"
0x1406dae1e  mov     [rbp+2F0h+var_1F0], rax
0x1406dae25  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dae2c  mov     [rbp+2F0h+var_1D8], rax
0x1406dae33  lea     rax, aRtlunicodestri_2; "RtlUnicodeStringToCountedOemString"
0x1406dae3a  mov     [rbp+2F0h+var_1D0], rax
0x1406dae41  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dae48  mov     [rbp+2F0h+var_1B8], rax
0x1406dae4f  lea     rax, aRtlupcaseunico_7; "RtlUpcaseUnicodeStringToCountedOemStrin"...
0x1406dae56  mov     [rbp+2F0h+var_1B0], rax
0x1406dae5d  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dae64  mov     [rbp+2F0h+var_198], rax
0x1406dae6b  lea     rax, aRtlupcaseunico_4; "RtlUpcaseUnicodeString"
0x1406dae72  mov     [rbp+2F0h+var_190], rax
0x1406dae79  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dae80  mov     [rbp+2F0h+var_178], rax
0x1406dae87  lea     rax, aRtldowncaseuni_1; "RtlDowncaseUnicodeString"
0x1406dae8e  mov     [rbp+2F0h+var_170], rax
0x1406dae95  lea     rax, ViSpRtlUpcaseUnicodeStringToAnsiString_Exit
0x1406dae9c  mov     [rbp+2F0h+var_158], rax
0x1406daea3  lea     rax, aRtlcreateunico_1; "RtlCreateUnicodeString"
0x1406daeaa  mov     [rbp+2F0h+var_150], rax
0x1406daeb1  lea     rax, ViSpRtlCreateUnicodeString_Exit
0x1406daeb8  mov     [rbp+2F0h+var_138], rax
0x1406daebf  lea     rax, aRtlduplicateun_0; "RtlDuplicateUnicodeString"
0x1406daec6  mov     [rbp+2F0h+var_130], rax
0x1406daecd  lea     rax, ViSpRtlDuplicateUnicodeString_Exit
0x1406daed4  mov     [rbp+2F0h+var_118], rax
0x1406daedb  lea     rax, aIoallocateirp_1; "IoAllocateIrp"
0x1406daee2  mov     [rbp+2F0h+var_110], rax
0x1406daee9  lea     rax, ViSpIoAllocateIrp_Exit
0x1406daef0  mov     [rbp+2F0h+var_F8], rax
0x1406daef7  lea     rax, aIoallocatemdl_0; "IoAllocateMdl"
0x1406daefe  mov     [rbp+2F0h+var_F0], rax
0x1406daf05  lea     rax, ViSpIoAllocateIrp_Exit
0x1406daf0c  mov     [rbp+2F0h+var_D8], rax
0x1406daf13  lea     rax, aIosetcompletio_0; "IoSetCompletionRoutineEx"
0x1406daf1a  mov     [rbp+2F0h+var_D0], rax
0x1406daf21  lea     rax, ViSpIoSetCompletionRoutineEx_Exit
0x1406daf28  mov     [rbp+2F0h+var_B8], rax
0x1406daf2f  lea     rax, aMmprobeandlock; "MmProbeAndLockPages"
0x1406daf36  mov     [rbp+2F0h+var_B0], rax
0x1406daf3d  lea     rax, ViSpMmProbeAndLockPages_Entry
0x1406daf44  mov     [rbp+2F0h+var_A0], rax
0x1406daf4b  lea     rax, aMmprobeandlock_2; "MmProbeAndLockProcessPages"
0x1406daf52  mov     [rbp+2F0h+var_90], rax
0x1406daf59  lea     rax, ViSpMmProbeAndLockProcessPages_Entry
0x1406daf60  mov     [rbp+2F0h+var_80], rax
0x1406daf67  mov     [rbp+2F0h+var_220], rcx
0x1406daf6e  mov     [rbp+2F0h+var_208], 96h
0x1406daf78  mov     [rbp+2F0h+var_200], rcx
0x1406daf7f  mov     [rbp+2F0h+var_1E8], 0A1h
0x1406daf89  mov     [rbp+2F0h+var_1E0], rcx
0x1406daf90  mov     [rbp+2F0h+var_1C8], 9Bh
0x1406daf9a  mov     [rbp+2F0h+var_1C0], rcx
0x1406dafa1  mov     [rbp+2F0h+var_1A8], 97h
0x1406dafab  mov     [rbp+2F0h+var_1A0], rcx
0x1406dafb2  mov     [rbp+2F0h+var_188], 99h
0x1406dafbc  mov     [rbp+2F0h+var_180], rcx
0x1406dafc3  mov     [rbp+2F0h+var_168], 0A3h
0x1406dafcd  mov     [rbp+2F0h+var_160], rcx
0x1406dafd4  mov     [rbp+2F0h+var_148], 0A5h
0x1406dafde  mov     [rbp+2F0h+var_140], rcx
0x1406dafe5  mov     [rbp+2F0h+var_128], 0A2h
0x1406dafef  mov     [rbp+2F0h+var_120], rcx
0x1406daff6  mov     [rbp+2F0h+var_108], 16Eh
0x1406db000  mov     [rbp+2F0h+var_100], rcx
0x1406db007  mov     [rbp+2F0h+var_E8], 16Dh
0x1406db011  mov     [rbp+2F0h+var_E0], rcx
0x1406db018  mov     [rbp+2F0h+var_C8], 13Ah
0x1406db022  mov     [rbp+2F0h+var_C0], rcx
0x1406db029  mov     [rbp+2F0h+var_A8], 0D9h
0x1406db033  mov     [rbp+2F0h+var_98], rcx
0x1406db03a  mov     [rbp+2F0h+var_88], 0D8h
0x1406db044  lea     rax, aMmmaplockedpag_0; "MmMapLockedPagesSpecifyCache"
0x1406db04b  mov     [rbp+2F0h+var_78], rcx
0x1406db052  mov     [rbp+2F0h+var_70], rax
0x1406db059  lea     rax, ViSpMmMapLockedPagesSpecifyCache_Entry
0x1406db060  mov     [rbp+2F0h+var_60], rax
0x1406db067  lea     rax, aMmmapiospace; "MmMapIoSpace"
0x1406db06e  mov     [rbp+2F0h+var_50], rax
0x1406db075  lea     rax, ViSpMmMapIoSpace_Entry
0x1406db07c  mov     [rbp+2F0h+var_40], rax
0x1406db083  lea     rax, aMmmaplockedpag_3; "MmMapLockedPages"
0x1406db08a  mov     [rbp+2F0h+var_30], rax
0x1406db091  lea     rax, ViSpMmMapLockedPages_Entry
0x1406db098  mov     [rbp+2F0h+var_20], rax
0x1406db09f  mov     [rbp+2F0h+var_68], 0DBh
0x1406db0a9  mov     [rbp+2F0h+var_58], rcx
0x1406db0b0  mov     [rbp+2F0h+var_48], 0DDh
0x1406db0ba  mov     [rbp+2F0h+var_38], rcx
0x1406db0c1  mov     [rbp+2F0h+var_28], 0DCh
0x1406db0cb  mov     [rbp+2F0h+var_18], rcx
0x1406db0d2  lea     edx, [rcx+1Eh]
0x1406db0d5  xor     r9d, r9d
0x1406db0d8  lea     rcx, [rsp+3F0h+var_3D0]
0x1406db0dd  xor     r8d, r8d
0x1406db0e0  call    DifRegisterPlugin
0x1406db0e5  mov     rcx, [rbp+2F0h+var_10]
0x1406db0ec  xor     rcx, rsp; StackCookie
0x1406db0ef  call    __security_check_cookie
0x1406db0f4  add     rsp, 3F0h
0x1406db0fb  pop     rbp
0x1406db0fc  retn
```
