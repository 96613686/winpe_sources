# VIDMM_GLOBAL::ReadConfiguration(void)

- ea: `0x14011b1e8`
- end: `0x14011bf77`
- name: `?ReadConfiguration@VIDMM_GLOBAL@@SAXXZ`
- size: `3471`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140120c40`

## callees

- `0x140058680`
- `0x140058ac0`
- `0x1400ac444`
- `0x14011875c`
- `0x14011b1e8`
- `0x14011d474`
- `0x14011e254`
- `0x14011e800`
- `0x14011f1d4`
- `0x14011fd94`
- `0x1401205b0`
- `0x140120890`
- `0x140120a5c`
- `0x1401216a0`
- `0x140121884`
- `0x140123734`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14011bc1b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011bc1b`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14011bbad`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14011bce7`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14011bbad`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14011bce7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14011bc2f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14011bc79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14011bc2f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14011bc79`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14011bc5d`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14011bc5d`
- `watchdog!WdLogSingleEntry2` at `0x14011bd21`
- `watchdog!WdLogSingleEntry2` at `0x14011bd21`
- `watchdog!WdLogSingleEntry1` at `0x14011bd49`
- `watchdog!WdLogSingleEntry1` at `0x14011bd49`
- `dxgkrnl!g_IsInternalRelease` at `0x14011b2ea`

## string_xrefs

- `0x14011b9b8`: `CommitProcessHeapOnDemand`
- `0x14011b7ce`: `EvictTemporaryPeriod`
- `0x14011b73c`: `RemovePagesFromWorkingSetOnPagingForDwm`
- `0x14011b5f7`: `NbDmaBufferLimitCompareWatermark`

## pseudocode

```c
void __fastcall VIDMM_GLOBAL::ReadConfiguration(void *a1)
{
  int v1; // eax
  int v2; // eax
  int v3; // eax
  ULONG i; // ebx
  int v5; // eax
  unsigned int v6; // eax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+3Ch] [rbp-C4h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+54h] [rbp-ACh] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+64h] [rbp-9Ch] BYREF
  int v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+6Ch] [rbp-94h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+74h] [rbp-8Ch] BYREF
  int v28; // [rsp+78h] [rbp-88h] BYREF
  int v29; // [rsp+7Ch] [rbp-84h] BYREF
  int v30; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+84h] [rbp-7Ch] BYREF
  int v32; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+8Ch] [rbp-74h] BYREF
  int v34; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+94h] [rbp-6Ch] BYREF
  int v36; // [rsp+98h] [rbp-68h] BYREF
  int v37; // [rsp+9Ch] [rbp-64h] BYREF
  int v38; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v39; // [rsp+A4h] [rbp-5Ch] BYREF
  int v40; // [rsp+A8h] [rbp-58h] BYREF
  int v41; // [rsp+ACh] [rbp-54h] BYREF
  int v42; // [rsp+B0h] [rbp-50h] BYREF
  int v43; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v44; // [rsp+B8h] [rbp-48h] BYREF
  int v45; // [rsp+BCh] [rbp-44h] BYREF
  int v46; // [rsp+C0h] [rbp-40h] BYREF
  int v47; // [rsp+C4h] [rbp-3Ch] BYREF
  int v48; // [rsp+C8h] [rbp-38h] BYREF
  int v49; // [rsp+CCh] [rbp-34h] BYREF
  int v50; // [rsp+D0h] [rbp-30h] BYREF
  int v51; // [rsp+D4h] [rbp-2Ch] BYREF
  int v52; // [rsp+D8h] [rbp-28h] BYREF
  int v53; // [rsp+DCh] [rbp-24h] BYREF
  int v54; // [rsp+E0h] [rbp-20h] BYREF
  int v55; // [rsp+E4h] [rbp-1Ch] BYREF
  int v56; // [rsp+E8h] [rbp-18h] BYREF
  int v57; // [rsp+ECh] [rbp-14h] BYREF
  int v58; // [rsp+F0h] [rbp-10h] BYREF
  int v59; // [rsp+F4h] [rbp-Ch] BYREF
  int v60; // [rsp+F8h] [rbp-8h] BYREF
  int v61; // [rsp+FCh] [rbp-4h] BYREF
  int v62; // [rsp+100h] [rbp+0h] BYREF
  int v63; // [rsp+104h] [rbp+4h] BYREF
  int v64; // [rsp+108h] [rbp+8h] BYREF
  int v65; // [rsp+10Ch] [rbp+Ch] BYREF
  int v66; // [rsp+110h] [rbp+10h] BYREF
  int v67; // [rsp+114h] [rbp+14h] BYREF
  int v68; // [rsp+118h] [rbp+18h] BYREF
  int v69; // [rsp+11Ch] [rbp+1Ch] BYREF
  int v70; // [rsp+120h] [rbp+20h] BYREF
  int v71; // [rsp+124h] [rbp+24h] BYREF
  int v72; // [rsp+128h] [rbp+28h] BYREF
  int v73; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v74; // [rsp+130h] [rbp+30h] BYREF
  int v75; // [rsp+134h] [rbp+34h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+138h] [rbp+38h] BYREF
  struct _UNICODE_STRING String; // [rsp+148h] [rbp+48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+158h] [rbp+58h] BYREF
  _OWORD v79[116]; // [rsp+170h] [rbp+70h] BYREF
  char v80; // [rsp+8B0h] [rbp+7B0h] BYREF
  _BYTE v81[64]; // [rsp+8C0h] [rbp+7C0h] BYREF

  qword_140086300 = VIDMM_GLOBAL::QuerySystemMemorySize(a1);
  qword_1400862F8 = qword_140086300;
  v45 = 0;
  v14 = 25;
  v10 = 25;
  v12 = 0;
  v50 = 0;
  v15 = 40;
  v11 = 40;
  v16 = 0;
  v52 = 4;
  v46 = 10;
  v26 = 10;
  v47 = 15;
  v27 = 15;
  v48 = 5;
  v28 = 5;
  v49 = 300;
  v29 = 300;
  v1 = 256;
  if ( (unsigned __int64)qword_140086300 > 0x20000000 )
    v1 = 1024;
  v18 = 4;
  v51 = v1;
  v17 = v1;
  v2 = 0x800000;
  if ( (unsigned __int64)qword_140086300 > 0x20000000 )
    v2 = 0x2000000;
  v55 = 10;
  v53 = v2;
  v19 = v2;
  v3 = 0x400000;
  if ( (unsigned __int64)qword_140086300 > 0x20000000 )
    v3 = 0x1000000;
  v21 = 10;
  v54 = v3;
  v20 = v3;
  v57 = 1;
  v23 = 1;
  v58 = 1;
  v25 = 1;
  v56 = g_IsInternalRelease != 0 ? 0x40 : 0;
  v22 = v56;
  v60 = 0x100000;
  v30 = 0x100000;
  v62 = 60;
  v32 = 60;
  v63 = 60;
  v33 = 60;
  v65 = 8;
  v35 = 8;
  v59 = 1;
  v24 = 1;
  v61 = 0x800000;
  v31 = 0x800000;
  v64 = 1;
  v34 = 1;
  v66 = 2;
  v36 = 2;
  v69 = 200;
  v39 = 200;
  v71 = 4096;
  v41 = 4096;
  v72 = 6;
  v42 = 6;
  v73 = 20;
  v43 = 20;
  v74 = 900;
  v44 = 900;
  *(_QWORD *)&v79[1] = L"PinnedMemoryLimit";
  *((_QWORD *)&v79[1] + 1) = &v10;
  *((_QWORD *)&v79[2] + 1) = &v14;
  *((_QWORD *)&v79[4] + 1) = L"PinnedApertureMemoryLimit";
  *(_QWORD *)&v79[5] = &v11;
  *(_QWORD *)&v79[6] = &v15;
  *(_QWORD *)&v79[8] = L"PagesHistory";
  *((_QWORD *)&v79[8] + 1) = &v12;
  *((_QWORD *)&v79[9] + 1) = &v45;
  *((_QWORD *)&v79[11] + 1) = L"MemTransferThreshold";
  *(_QWORD *)&v79[12] = &v26;
  *(_QWORD *)&v79[13] = &v46;
  *(_QWORD *)&v79[15] = L"ExcessiveMemTransferFlipThreshold";
  *((_QWORD *)&v79[15] + 1) = &v27;
  *((_QWORD *)&v79[16] + 1) = &v47;
  *((_QWORD *)&v79[18] + 1) = L"ExcessiveMemTransferPenalty";
  *(_QWORD *)&v79[19] = &v28;
  v67 = 0;
  v37 = 0;
  v68 = 0;
  v38 = 0;
  v70 = 1;
  v40 = 1;
  *(_QWORD *)&v79[0] = 0;
  DWORD2(v79[0]) = 288;
  LODWORD(v79[2]) = 67108868;
  LODWORD(v79[3]) = 4;
  *((_QWORD *)&v79[3] + 1) = 0;
  LODWORD(v79[4]) = 288;
  DWORD2(v79[5]) = 67108868;
  DWORD2(v79[6]) = 4;
  *(_QWORD *)&v79[7] = 0;
  DWORD2(v79[7]) = 288;
  LODWORD(v79[9]) = 67108868;
  LODWORD(v79[10]) = 4;
  *((_QWORD *)&v79[10] + 1) = 0;
  LODWORD(v79[11]) = 288;
  DWORD2(v79[12]) = 67108868;
  DWORD2(v79[13]) = 4;
  *(_QWORD *)&v79[14] = 0;
  DWORD2(v79[14]) = 288;
  LODWORD(v79[16]) = 67108868;
  LODWORD(v79[17]) = 4;
  *((_QWORD *)&v79[17] + 1) = 0;
  LODWORD(v79[18]) = 288;
  DWORD2(v79[19]) = 67108868;
  *(_QWORD *)&v79[20] = &v48;
  *(_QWORD *)&v79[22] = L"EventThrottleThreshold";
  *((_QWORD *)&v79[22] + 1) = &v29;
  *((_QWORD *)&v79[23] + 1) = &v49;
  *((_QWORD *)&v79[25] + 1) = L"DisablePrefetching";
  *(_QWORD *)&v79[26] = &v16;
  *(_QWORD *)&v79[27] = &v50;
  *(_QWORD *)&v79[29] = L"NbDmaBufferLimitPerDevice";
  *((_QWORD *)&v79[29] + 1) = &v17;
  *((_QWORD *)&v79[30] + 1) = &v51;
  *((_QWORD *)&v79[32] + 1) = L"NbCddDmaBufferLimitPerDevice";
  *(_QWORD *)&v79[33] = &v18;
  *(_QWORD *)&v79[34] = &v52;
  *(_QWORD *)&v79[36] = L"DmaBufferBytesLimitAllDevices";
  *((_QWORD *)&v79[36] + 1) = &v19;
  *((_QWORD *)&v79[37] + 1) = &v53;
  *((_QWORD *)&v79[39] + 1) = L"DmaBufferListBytesLimitAllDevices";
  *(_QWORD *)&v79[40] = &v20;
  *(_QWORD *)&v79[41] = &v54;
  *(_QWORD *)&v79[43] = L"NbDmaBufferLimitCompareWatermark";
  *((_QWORD *)&v79[43] + 1) = &v21;
  *((_QWORD *)&v79[44] + 1) = &v55;
  *((_QWORD *)&v79[46] + 1) = L"NbPagingHistoryRecords";
  *(_QWORD *)&v79[47] = &v22;
  DWORD2(v79[20]) = 4;
  *(_QWORD *)&v79[21] = 0;
  DWORD2(v79[21]) = 288;
  LODWORD(v79[23]) = 67108868;
  LODWORD(v79[24]) = 4;
  *((_QWORD *)&v79[24] + 1) = 0;
  LODWORD(v79[25]) = 288;
  DWORD2(v79[26]) = 67108868;
  DWORD2(v79[27]) = 4;
  *(_QWORD *)&v79[28] = 0;
  DWORD2(v79[28]) = 288;
  LODWORD(v79[30]) = 67108868;
  LODWORD(v79[31]) = 4;
  *((_QWORD *)&v79[31] + 1) = 0;
  LODWORD(v79[32]) = 288;
  DWORD2(v79[33]) = 67108868;
  DWORD2(v79[34]) = 4;
  *(_QWORD *)&v79[35] = 0;
  DWORD2(v79[35]) = 288;
  LODWORD(v79[37]) = 67108868;
  LODWORD(v79[38]) = 4;
  *((_QWORD *)&v79[38] + 1) = 0;
  LODWORD(v79[39]) = 288;
  DWORD2(v79[40]) = 67108868;
  DWORD2(v79[41]) = 4;
  *(_QWORD *)&v79[42] = 0;
  DWORD2(v79[42]) = 288;
  LODWORD(v79[44]) = 67108868;
  LODWORD(v79[45]) = 4;
  *((_QWORD *)&v79[45] + 1) = 0;
  LODWORD(v79[46]) = 288;
  DWORD2(v79[47]) = 67108868;
  DWORD2(v79[48]) = 4;
  *(_QWORD *)&v79[48] = &v56;
  *(_QWORD *)&v79[50] = L"PinDWMAllocationBackingStore";
  *((_QWORD *)&v79[50] + 1) = &v23;
  *((_QWORD *)&v79[51] + 1) = &v57;
  *((_QWORD *)&v79[53] + 1) = L"RemovePagesFromWorkingSetOnPagingForDwm";
  *(_QWORD *)&v79[54] = &v25;
  *(_QWORD *)&v79[55] = &v58;
  *(_QWORD *)&v79[57] = L"UseUnreset";
  *((_QWORD *)&v79[57] + 1) = &v24;
  *((_QWORD *)&v79[58] + 1) = &v59;
  *((_QWORD *)&v79[60] + 1) = L"PrivateHeapPackingThreshold";
  *(_QWORD *)&v79[61] = &v30;
  *(_QWORD *)&v79[62] = &v60;
  *(_QWORD *)&v79[64] = L"PrivateHeapPackingBlockSize";
  *((_QWORD *)&v79[64] + 1) = &v31;
  *((_QWORD *)&v79[65] + 1) = &v61;
  *((_QWORD *)&v79[67] + 1) = L"EvictTemporaryPeriod";
  *(_QWORD *)&v79[68] = &v32;
  *(_QWORD *)&v79[69] = &v62;
  *(_QWORD *)&v79[71] = L"EvictUnusedPeriod";
  *((_QWORD *)&v79[71] + 1) = &v33;
  *((_QWORD *)&v79[72] + 1) = &v63;
  *((_QWORD *)&v79[74] + 1) = L"ProcessPendingOfferPeriod";
  *(_QWORD *)&v79[75] = &v34;
  *(_QWORD *)&v79[49] = 0;
  DWORD2(v79[49]) = 288;
  LODWORD(v79[51]) = 67108868;
  LODWORD(v79[52]) = 4;
  *((_QWORD *)&v79[52] + 1) = 0;
  LODWORD(v79[53]) = 288;
  DWORD2(v79[54]) = 67108868;
  DWORD2(v79[55]) = 4;
  *(_QWORD *)&v79[56] = 0;
  DWORD2(v79[56]) = 288;
  LODWORD(v79[58]) = 67108868;
  LODWORD(v79[59]) = 4;
  *((_QWORD *)&v79[59] + 1) = 0;
  LODWORD(v79[60]) = 288;
  DWORD2(v79[61]) = 67108868;
  DWORD2(v79[62]) = 4;
  *(_QWORD *)&v79[63] = 0;
  DWORD2(v79[63]) = 288;
  LODWORD(v79[65]) = 67108868;
  LODWORD(v79[66]) = 4;
  *((_QWORD *)&v79[66] + 1) = 0;
  LODWORD(v79[67]) = 288;
  DWORD2(v79[68]) = 67108868;
  DWORD2(v79[69]) = 4;
  *(_QWORD *)&v79[70] = 0;
  DWORD2(v79[70]) = 288;
  LODWORD(v79[72]) = 67108868;
  LODWORD(v79[73]) = 4;
  *((_QWORD *)&v79[73] + 1) = 0;
  LODWORD(v79[74]) = 288;
  DWORD2(v79[75]) = 67108868;
  *(_QWORD *)&v79[76] = &v64;
  *(_QWORD *)&v79[78] = L"ProcessSysmemOfferPeriod";
  *((_QWORD *)&v79[78] + 1) = &v35;
  *((_QWORD *)&v79[79] + 1) = &v65;
  *((_QWORD *)&v79[81] + 1) = L"SegmentBalancingPolicy";
  *(_QWORD *)&v79[82] = &v36;
  *(_QWORD *)&v79[83] = &v66;
  *(_QWORD *)&v79[85] = L"BugcheckOnApertureCorruption";
  *((_QWORD *)&v79[85] + 1) = &v37;
  *((_QWORD *)&v79[86] + 1) = &v67;
  *((_QWORD *)&v79[88] + 1) = L"QuickApertureCorruptionCheck";
  *(_QWORD *)&v79[89] = &v38;
  *(_QWORD *)&v79[90] = &v68;
  *(_QWORD *)&v79[92] = L"DirectFlipMemoryRequirement";
  *((_QWORD *)&v79[92] + 1) = &v39;
  *((_QWORD *)&v79[93] + 1) = &v69;
  *((_QWORD *)&v79[95] + 1) = L"CommitProcessHeapOnDemand";
  *(_QWORD *)&v79[96] = &v40;
  *(_QWORD *)&v79[97] = &v70;
  *(_QWORD *)&v79[99] = L"SegmentCleanupSizeThreshold";
  *((_QWORD *)&v79[99] + 1) = &v41;
  *((_QWORD *)&v79[100] + 1) = &v71;
  *((_QWORD *)&v79[102] + 1) = L"SegmentCleanupCountThreshold";
  *(_QWORD *)&v79[103] = &v42;
  *(_QWORD *)&v79[104] = &v72;
  DWORD2(v79[76]) = 4;
  *(_QWORD *)&v79[77] = 0;
  DWORD2(v79[77]) = 288;
  LODWORD(v79[79]) = 67108868;
  LODWORD(v79[80]) = 4;
  *((_QWORD *)&v79[80] + 1) = 0;
  LODWORD(v79[81]) = 288;
  DWORD2(v79[82]) = 67108868;
  DWORD2(v79[83]) = 4;
  *(_QWORD *)&v79[84] = 0;
  DWORD2(v79[84]) = 288;
  LODWORD(v79[86]) = 67108868;
  LODWORD(v79[87]) = 4;
  *((_QWORD *)&v79[87] + 1) = 0;
  LODWORD(v79[88]) = 288;
  DWORD2(v79[89]) = 67108868;
  DWORD2(v79[90]) = 4;
  *(_QWORD *)&v79[91] = 0;
  DWORD2(v79[91]) = 288;
  LODWORD(v79[93]) = 67108868;
  LODWORD(v79[94]) = 4;
  *((_QWORD *)&v79[94] + 1) = 0;
  LODWORD(v79[95]) = 288;
  DWORD2(v79[96]) = 67108868;
  DWORD2(v79[97]) = 4;
  *(_QWORD *)&v79[98] = 0;
  DWORD2(v79[98]) = 288;
  LODWORD(v79[100]) = 67108868;
  LODWORD(v79[101]) = 4;
  *((_QWORD *)&v79[101] + 1) = 0;
  LODWORD(v79[102]) = 288;
  DWORD2(v79[103]) = 67108868;
  LODWORD(v79[107]) = 67108868;
  DWORD2(v79[110]) = 67108868;
  *(_QWORD *)&v79[106] = L"SegmentCleanupTime";
  DWORD2(v79[104]) = 4;
  *((_QWORD *)&v79[106] + 1) = &v43;
  *(_QWORD *)&v79[105] = 0;
  *((_QWORD *)&v79[107] + 1) = &v73;
  DWORD2(v79[105]) = 288;
  *((_QWORD *)&v79[109] + 1) = L"SelfRefreshVramForceEvictionTimer";
  LODWORD(v79[108]) = 4;
  *(_QWORD *)&v79[110] = &v44;
  *(_QWORD *)&v79[111] = &v74;
  *((_QWORD *)&v79[108] + 1) = 0;
  LODWORD(v79[109]) = 288;
  DWORD2(v79[111]) = 4;
  memset(&v79[112], 0, 56);
  RtlQueryRegistryValuesEx(2, L"GraphicsDrivers\\MemoryManager", v79, 0, 0);
  memset(qword_140086328, 0, sizeof(qword_140086328));
  memset(v79, 0, 0x738u);
  for ( i = 0; i < 0x20; ++i )
  {
    memset(v81, 0, sizeof(v81));
    *(_QWORD *)&Destination.Length = 0x400000;
    Destination.Buffer = (PWSTR)v81;
    DestinationString = 0;
    String = 0;
    RtlInitUnicodeString(&DestinationString, L"MaxSegmentSize");
    if ( RtlAppendUnicodeStringToString(&Destination, &DestinationString) >= 0 )
    {
      *(_DWORD *)&String.Length = 0x100000;
      String.Buffer = (PWSTR)&v80;
      if ( RtlIntegerToUnicodeString(i, 0, &String) >= 0 && RtlAppendUnicodeStringToString(&Destination, &String) >= 0 )
      {
        *((_QWORD *)&v79[1] + 1) = &v13;
        *((_QWORD *)&v79[2] + 1) = &v75;
        v75 = 0;
        v13 = 0;
        *(_QWORD *)&v79[0] = 0;
        *((_QWORD *)&v79[0] + 1) = 288;
        *(_QWORD *)&v79[1] = Destination.Buffer;
        *(_QWORD *)&v79[2] = 67108868;
        *(_QWORD *)&v79[3] = 4;
        RtlQueryRegistryValuesEx(2, L"GraphicsDrivers\\MemoryManager", v79, 0, 0);
        v5 = v13;
        *((_DWORD *)qword_140086328 + i) = v13;
        if ( v5 )
        {
          v6 = (v5 + 4095) & 0xFFFFF000;
          if ( v6 < 0x800000 )
            v6 = 0x800000;
          *((_DWORD *)qword_140086328 + i) = v6;
          WdLogSingleEntry2(4, i, v6);
          WdLogGlobalForLineNumber = 248;
        }
      }
    }
  }
  WdLogSingleEntry1(4, v10);
  v7 = v14;
  if ( v10 < 0x5A )
    v7 = v10;
  dword_140086318 = v7;
  v8 = v15;
  if ( v11 < 0x5A )
    v8 = v11;
  dword_14008631C = v8;
  v9 = 0x7FFFFFF;
  WdLogGlobalForLineNumber = 256;
  if ( v12 < 0x7FFFFFF )
    v9 = v12;
  dword_140086324 = v9;
  dword_140086320 = 0;
  dword_140086428 = v17;
  dword_14008642C = v18;
  dword_140086430 = v19;
  dword_140086434 = v20;
  dword_140086438 = v21;
  dword_14008643C = v22;
  qword_140086440 = (unsigned int)(v26 << 20);
  dword_140086448 = v27;
  dword_14008644C = v28;
  dword_140086458 = v30;
  dword_14008645C = v31;
  dword_140086480 = v36;
  qword_140086450 = (unsigned int)(10000000 * v29);
  qword_140086460 = (unsigned int)(10000000 * v32);
  qword_140086468 = (unsigned int)(10000000 * v33);
  qword_140086470 = (unsigned int)(10000000 * v34);
  qword_140086478 = (unsigned int)(10000000 * v35);
  VIDMM_GLOBAL::_Config = (v37 != 0 ? 0x10 : 0)
                        | (v23 != 0 ? 2 : 0)
                        | v16 & 1
                        | VIDMM_GLOBAL::_Config & 0xFFFFFFE0
                        | (4 * (v25 & 1 | (unsigned __int8)(2 * (v24 & 1)))) & 0xEF;
  dword_1400862E4 = v38 != 0;
  qword_1400862F0 = (unsigned __int64)v39 << 20;
  dword_1400862E8 = v40 != 0;
  qword_1400864B0 = (unsigned int)(v41 << 10);
  dword_1400864B8 = v42;
  qword_1400864C0 = (unsigned int)(10000 * v43);
  qword_140086670 = 10000000LL * v44;
  VIDMM_GLOBAL::ReadCommitLimitInformation();
  VIDMM_GLOBAL::ReadWorkingSetConfiguration();
  VIDMM_GLOBAL::ReadUnusedAllocationConfiguration();
  VIDMM_GLOBAL::ReadPreparationPeriodConfiguration();
  VIDMM_GLOBAL::ReadHeapConfiguration();
  VIDMM_GLOBAL::ReadPowerConfiguration();
  VIDMM_GLOBAL::ReadGpuVaPagingHistoryConfiguration();
  VIDMM_GLOBAL::ReadGpuVaConfiguration();
  VIDMM_GLOBAL::ReadPagingConfiguration();
  VIDMM_GLOBAL::ReadTestAndStagingConfiguration();
  VIDMM_GLOBAL::ReadVPRConfiguration();
  VIDMM_GLOBAL::ReadBudgetConfiguration();
}

```

## disassembly

```asm
0x14011b1e8  push    rbp
0x14011b1ea  push    rbx
0x14011b1eb  push    rsi
0x14011b1ec  push    rdi
0x14011b1ed  push    r12
0x14011b1ef  push    r13
0x14011b1f1  push    r14
0x14011b1f3  push    r15
0x14011b1f5  lea     rbp, [rsp-818h]
0x14011b1fd  sub     rsp, 918h
0x14011b204  mov     rax, cs:__security_cookie
0x14011b20b  xor     rax, rsp
0x14011b20e  mov     [rbp+850h+var_50], rax
0x14011b215  call    ?QuerySystemMemorySize@VIDMM_GLOBAL@@SA_KPEAX@Z; VIDMM_GLOBAL::QuerySystemMemorySize(void *)
0x14011b21a  mov     rcx, rax
0x14011b21d  mov     cs:qword_140086300, rax
0x14011b224  mov     cs:qword_1400862F8, rax
0x14011b22b  xor     edi, edi
0x14011b22d  mov     eax, 19h
0x14011b232  mov     [rbp+850h+var_894], edi
0x14011b235  mov     [rsp+950h+var_910], eax
0x14011b239  mov     r15d, 800000h
0x14011b23f  mov     [rsp+950h+var_920], eax
0x14011b243  mov     edx, 400h
0x14011b248  lea     r14d, [rdi+1]
0x14011b24c  mov     [rsp+950h+var_918], edi
0x14011b250  mov     eax, 28h ; '('
0x14011b255  mov     [rbp+850h+var_880], edi
0x14011b258  mov     [rsp+950h+var_90C], eax
0x14011b25c  lea     esi, [rdi+4]
0x14011b25f  mov     [rsp+950h+var_91C], eax
0x14011b263  lea     r12d, [rdi+40h]
0x14011b267  mov     r8d, 20000000h
0x14011b26d  mov     [rsp+950h+var_908], edi
0x14011b271  lea     r9d, [rax-1Eh]
0x14011b275  mov     [rbp+850h+var_878], esi
0x14011b278  cmp     rcx, r8
0x14011b27b  mov     [rbp+850h+var_890], r9d
0x14011b27f  lea     eax, [rdi+0Fh]
0x14011b282  mov     [rsp+950h+var_8E0], r9d
0x14011b287  mov     [rbp+850h+var_88C], eax
0x14011b28a  lea     r10d, [rdi+2]
0x14011b28e  mov     [rsp+950h+var_8DC], eax
0x14011b292  lea     eax, [rdi+5]
0x14011b295  mov     [rbp+850h+var_888], eax
0x14011b298  mov     [rsp+950h+var_8D8], eax
0x14011b29c  mov     eax, 12Ch
0x14011b2a1  mov     [rbp+850h+var_884], eax
0x14011b2a4  mov     [rsp+950h+var_8D4], eax
0x14011b2a8  mov     eax, 100h
0x14011b2ad  cmova   eax, edx
0x14011b2b0  mov     [rsp+950h+var_900], esi
0x14011b2b4  mov     [rbp+850h+var_87C], eax
0x14011b2b7  mov     edx, 2000000h
0x14011b2bc  mov     [rsp+950h+var_904], eax
0x14011b2c0  mov     eax, r15d
0x14011b2c3  cmova   eax, edx
0x14011b2c6  mov     [rbp+850h+var_86C], r9d
0x14011b2ca  mov     [rbp+850h+var_874], eax
0x14011b2cd  mov     edx, 1000000h
0x14011b2d2  mov     [rsp+950h+var_8FC], eax
0x14011b2d6  mov     eax, 400000h
0x14011b2db  cmova   eax, edx
0x14011b2de  mov     [rsp+950h+var_8F4], r9d
0x14011b2e3  mov     [rbp+850h+var_870], eax
0x14011b2e6  mov     [rsp+950h+var_8F8], eax
0x14011b2ea  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x14011b2f1  mov     cl, [rax]
0x14011b2f3  neg     cl
0x14011b2f5  mov     [rbp+850h+var_864], r14d
0x14011b2f9  mov     [rsp+950h+var_8EC], r14d
0x14011b2fe  sbb     eax, eax
0x14011b300  mov     [rbp+850h+var_860], r14d
0x14011b304  and     eax, r12d
0x14011b307  mov     [rsp+950h+var_8E4], r14d
0x14011b30c  mov     [rbp+850h+var_868], eax
0x14011b30f  mov     [rsp+950h+var_8F0], eax
0x14011b313  mov     eax, 100000h
0x14011b318  mov     [rbp+850h+var_858], eax
0x14011b31b  mov     [rbp+850h+var_8D0], eax
0x14011b31e  lea     eax, [rdi+3Ch]
0x14011b321  mov     [rbp+850h+var_850], eax
0x14011b324  mov     [rbp+850h+var_8C8], eax
0x14011b327  mov     [rbp+850h+var_84C], eax
0x14011b32a  mov     [rbp+850h+var_8C4], eax
0x14011b32d  lea     eax, [rdi+8]
0x14011b330  mov     [rbp+850h+var_844], eax
0x14011b333  mov     [rbp+850h+var_8BC], eax
0x14011b336  mov     [rbp+850h+var_85C], r14d
0x14011b33a  mov     [rsp+950h+var_8E8], r14d
0x14011b33f  mov     [rbp+850h+var_854], r15d
0x14011b343  mov     [rbp+850h+var_8CC], r15d
0x14011b347  mov     [rbp+850h+var_848], r14d
0x14011b34b  mov     [rbp+850h+var_8C0], r14d
0x14011b34f  mov     r13d, 120h
0x14011b355  mov     [rbp+850h+var_840], r10d
0x14011b359  mov     eax, 0C8h
0x14011b35e  mov     [rbp+850h+var_8B8], r10d
0x14011b362  mov     [rbp+850h+var_834], eax
0x14011b365  mov     ecx, 4000004h
0x14011b36a  mov     [rbp+850h+var_8AC], eax
0x14011b36d  mov     eax, 1000h
0x14011b372  mov     [rbp+850h+var_82C], eax
0x14011b375  mov     [rbp+850h+var_8A4], eax
0x14011b378  lea     eax, [rdi+6]
0x14011b37b  mov     [rbp+850h+var_828], eax
0x14011b37e  mov     [rbp+850h+var_8A0], eax
0x14011b381  lea     eax, [rdi+14h]
0x14011b384  mov     [rbp+850h+var_824], eax
0x14011b387  mov     [rbp+850h+var_89C], eax
0x14011b38a  mov     eax, 384h
0x14011b38f  mov     [rbp+850h+var_820], eax
0x14011b392  mov     [rbp+850h+var_898], eax
0x14011b395  lea     rax, aPinnedmemoryli; "PinnedMemoryLimit"
0x14011b39c  mov     [rbp+850h+var_7D0], rax
0x14011b3a3  lea     rax, [rsp+950h+var_920]
0x14011b3a8  mov     [rbp+850h+var_7C8], rax
0x14011b3af  lea     rax, [rsp+950h+var_910]
0x14011b3b4  mov     [rbp+850h+var_7B8], rax
0x14011b3bb  lea     rax, aPinnedaperture; "PinnedApertureMemoryLimit"
0x14011b3c2  mov     [rbp+850h+var_798], rax
0x14011b3c9  lea     rax, [rsp+950h+var_91C]
0x14011b3ce  mov     [rbp+850h+var_790], rax
0x14011b3d5  lea     rax, [rsp+950h+var_90C]
0x14011b3da  mov     [rbp+850h+var_780], rax
0x14011b3e1  lea     rax, aPageshistory; "PagesHistory"
0x14011b3e8  mov     [rbp+850h+var_760], rax
0x14011b3ef  lea     rax, [rsp+950h+var_918]
0x14011b3f4  mov     [rbp+850h+var_758], rax
0x14011b3fb  lea     rax, [rbp+850h+var_894]
0x14011b3ff  mov     [rbp+850h+var_748], rax
0x14011b406  lea     rax, aMemtransferthr; "MemTransferThreshold"
0x14011b40d  mov     [rbp+850h+var_728], rax
0x14011b414  lea     rax, [rsp+950h+var_8E0]
0x14011b419  mov     [rbp+850h+var_720], rax
0x14011b420  lea     rax, [rbp+850h+var_890]
0x14011b424  mov     [rbp+850h+var_710], rax
0x14011b42b  lea     rax, aExcessivememtr; "ExcessiveMemTransferFlipThreshold"
0x14011b432  mov     [rbp+850h+var_6F0], rax
0x14011b439  lea     rax, [rsp+950h+var_8DC]
0x14011b43e  mov     [rbp+850h+var_6E8], rax
0x14011b445  lea     rax, [rbp+850h+var_88C]
0x14011b449  mov     [rbp+850h+var_6D8], rax
0x14011b450  lea     rax, aExcessivememtr_0; "ExcessiveMemTransferPenalty"
0x14011b457  mov     [rbp+850h+var_6B8], rax
0x14011b45e  lea     rax, [rsp+950h+var_8D8]
0x14011b463  mov     [rbp+850h+var_6B0], rax
0x14011b46a  mov     [rbp+850h+var_83C], edi
0x14011b46d  mov     [rbp+850h+var_8B4], edi
0x14011b470  mov     [rbp+850h+var_838], edi
0x14011b473  mov     [rbp+850h+var_8B0], edi
0x14011b476  mov     [rbp+850h+var_830], r14d
0x14011b47a  mov     [rbp+850h+var_8A8], r14d
0x14011b47e  mov     [rbp+850h+var_7E0], rdi
0x14011b482  mov     dword ptr [rbp+850h+var_7D8], r13d
0x14011b486  mov     dword ptr [rbp+850h+var_7C0], ecx
0x14011b48c  mov     dword ptr [rbp+850h+var_7B0], esi
0x14011b492  mov     [rbp+850h+var_7A8], rdi
0x14011b499  mov     [rbp+850h+var_7A0], r13d
0x14011b4a0  mov     [rbp+850h+var_788], ecx
0x14011b4a6  mov     [rbp+850h+var_778], esi
0x14011b4ac  mov     [rbp+850h+var_770], rdi
0x14011b4b3  mov     [rbp+850h+var_768], r13d
0x14011b4ba  mov     [rbp+850h+var_750], ecx
0x14011b4c0  mov     [rbp+850h+var_740], esi
0x14011b4c6  mov     [rbp+850h+var_738], rdi
0x14011b4cd  mov     [rbp+850h+var_730], r13d
0x14011b4d4  mov     [rbp+850h+var_718], ecx
0x14011b4da  mov     [rbp+850h+var_708], esi
0x14011b4e0  mov     [rbp+850h+var_700], rdi
0x14011b4e7  mov     [rbp+850h+var_6F8], r13d
0x14011b4ee  mov     [rbp+850h+var_6E0], ecx
0x14011b4f4  mov     [rbp+850h+var_6D0], esi
0x14011b4fa  mov     [rbp+850h+var_6C8], rdi
0x14011b501  mov     [rbp+850h+var_6C0], r13d
0x14011b508  lea     rax, [rbp+850h+var_888]
0x14011b50c  mov     [rbp+850h+var_6A8], ecx
0x14011b512  mov     [rbp+850h+var_6A0], rax
0x14011b519  lea     rax, aEventthrottlet; "EventThrottleThreshold"
0x14011b520  mov     [rbp+850h+var_680], rax
0x14011b527  lea     rax, [rsp+950h+var_8D4]
0x14011b52c  mov     [rbp+850h+var_678], rax
0x14011b533  lea     rax, [rbp+850h+var_884]
0x14011b537  mov     [rbp+850h+var_668], rax
0x14011b53e  lea     rax, aDisableprefetc; "DisablePrefetching"
0x14011b545  mov     [rbp+850h+var_648], rax
0x14011b54c  lea     rax, [rsp+950h+var_908]
0x14011b551  mov     [rbp+850h+var_640], rax
0x14011b558  lea     rax, [rbp+850h+var_880]
0x14011b55c  mov     [rbp+850h+var_630], rax
0x14011b563  lea     rax, aNbdmabufferlim_0; "NbDmaBufferLimitPerDevice"
0x14011b56a  mov     [rbp+850h+var_610], rax
0x14011b571  lea     rax, [rsp+950h+var_904]
0x14011b576  mov     [rbp+850h+var_608], rax
0x14011b57d  lea     rax, [rbp+850h+var_87C]
0x14011b581  mov     [rbp+850h+var_5F8], rax
0x14011b588  lea     rax, aNbcdddmabuffer; "NbCddDmaBufferLimitPerDevice"
0x14011b58f  mov     [rbp+850h+var_5D8], rax
0x14011b596  lea     rax, [rsp+950h+var_900]
0x14011b59b  mov     [rbp+850h+var_5D0], rax
0x14011b5a2  lea     rax, [rbp+850h+var_878]
0x14011b5a6  mov     [rbp+850h+var_5C0], rax
0x14011b5ad  lea     rax, aDmabufferbytes; "DmaBufferBytesLimitAllDevices"
0x14011b5b4  mov     [rbp+850h+var_5A0], rax
0x14011b5bb  lea     rax, [rsp+950h+var_8FC]
0x14011b5c0  mov     [rbp+850h+var_598], rax
0x14011b5c7  lea     rax, [rbp+850h+var_874]
0x14011b5cb  mov     [rbp+850h+var_588], rax
0x14011b5d2  lea     rax, aDmabufferlistb; "DmaBufferListBytesLimitAllDevices"
0x14011b5d9  mov     [rbp+850h+var_568], rax
0x14011b5e0  lea     rax, [rsp+950h+var_8F8]
0x14011b5e5  mov     [rbp+850h+var_560], rax
0x14011b5ec  lea     rax, [rbp+850h+var_870]
0x14011b5f0  mov     [rbp+850h+var_550], rax
0x14011b5f7  lea     rax, aNbdmabufferlim; "NbDmaBufferLimitCompareWatermark"
0x14011b5fe  mov     [rbp+850h+var_530], rax
0x14011b605  lea     rax, [rsp+950h+var_8F4]
0x14011b60a  mov     [rbp+850h+var_528], rax
0x14011b611  lea     rax, [rbp+850h+var_86C]
0x14011b615  mov     [rbp+850h+var_518], rax
0x14011b61c  lea     rax, aNbpaginghistor; "NbPagingHistoryRecords"
0x14011b623  mov     [rbp+850h+var_4F8], rax
0x14011b62a  lea     rax, [rsp+950h+var_8F0]
0x14011b62f  mov     [rbp+850h+var_4F0], rax
0x14011b636  mov     [rbp+850h+var_698], esi
0x14011b63c  mov     [rbp+850h+var_690], rdi
0x14011b643  mov     [rbp+850h+var_688], r13d
0x14011b64a  mov     [rbp+850h+var_670], ecx
0x14011b650  mov     [rbp+850h+var_660], esi
0x14011b656  mov     [rbp+850h+var_658], rdi
0x14011b65d  mov     [rbp+850h+var_650], r13d
0x14011b664  mov     [rbp+850h+var_638], ecx
0x14011b66a  mov     [rbp+850h+var_628], esi
0x14011b670  mov     [rbp+850h+var_620], rdi
0x14011b677  mov     [rbp+850h+var_618], r13d
0x14011b67e  mov     [rbp+850h+var_600], ecx
0x14011b684  mov     [rbp+850h+var_5F0], esi
0x14011b68a  mov     [rbp+850h+var_5E8], rdi
0x14011b691  mov     [rbp+850h+var_5E0], r13d
0x14011b698  mov     [rbp+850h+var_5C8], ecx
0x14011b69e  mov     [rbp+850h+var_5B8], esi
0x14011b6a4  mov     [rbp+850h+var_5B0], rdi
0x14011b6ab  mov     [rbp+850h+var_5A8], r13d
0x14011b6b2  mov     [rbp+850h+var_590], ecx
0x14011b6b8  mov     [rbp+850h+var_580], esi
0x14011b6be  mov     [rbp+850h+var_578], rdi
0x14011b6c5  mov     [rbp+850h+var_570], r13d
0x14011b6cc  mov     [rbp+850h+var_558], ecx
0x14011b6d2  mov     [rbp+850h+var_548], esi
0x14011b6d8  mov     [rbp+850h+var_540], rdi
0x14011b6df  mov     [rbp+850h+var_538], r13d
0x14011b6e6  mov     [rbp+850h+var_520], ecx
0x14011b6ec  mov     [rbp+850h+var_510], esi
0x14011b6f2  mov     [rbp+850h+var_508], rdi
0x14011b6f9  mov     [rbp+850h+var_500], r13d
0x14011b700  mov     [rbp+850h+var_4E8], ecx
0x14011b706  lea     rax, [rbp+850h+var_868]
0x14011b70a  mov     [rbp+850h+var_4D8], esi
0x14011b710  mov     [rbp+850h+var_4E0], rax
0x14011b717  lea     rax, aPindwmallocati; "PinDWMAllocationBackingStore"
0x14011b71e  mov     [rbp+850h+var_4C0], rax
0x14011b725  lea     rax, [rsp+950h+var_8EC]
0x14011b72a  mov     [rbp+850h+var_4B8], rax
0x14011b731  lea     rax, [rbp+850h+var_864]
0x14011b735  mov     [rbp+850h+var_4A8], rax
0x14011b73c  lea     rax, aRemovepagesfro; "RemovePagesFromWorkingSetOnPagingForDwm"
0x14011b743  mov     [rbp+850h+var_488], rax
0x14011b74a  lea     rax, [rsp+950h+var_8E4]
0x14011b74f  mov     [rbp+850h+var_480], rax
0x14011b756  lea     rax, [rbp+850h+var_860]
0x14011b75a  mov     [rbp+850h+var_470], rax
0x14011b761  lea     rax, aUseunreset; "UseUnreset"
0x14011b768  mov     [rbp+850h+var_450], rax
0x14011b76f  lea     rax, [rsp+950h+var_8E8]
0x14011b774  mov     [rbp+850h+var_448], rax
0x14011b77b  lea     rax, [rbp+850h+var_85C]
0x14011b77f  mov     [rbp+850h+var_438], rax
0x14011b786  lea     rax, aPrivateheappac_0; "PrivateHeapPackingThreshold"
0x14011b78d  mov     [rbp+850h+var_418], rax
0x14011b794  lea     rax, [rbp+850h+var_8D0]
0x14011b798  mov     [rbp+850h+var_410], rax
0x14011b79f  lea     rax, [rbp+850h+var_858]
0x14011b7a3  mov     [rbp+850h+var_400], rax
0x14011b7aa  lea     rax, aPrivateheappac; "PrivateHeapPackingBlockSize"
0x14011b7b1  mov     [rbp+850h+var_3E0], rax
0x14011b7b8  lea     rax, [rbp+850h+var_8CC]
0x14011b7bc  mov     [rbp+850h+var_3D8], rax
0x14011b7c3  lea     rax, [rbp+850h+var_854]
0x14011b7c7  mov     [rbp+850h+var_3C8], rax
0x14011b7ce  lea     rax, aEvicttemporary; "EvictTemporaryPeriod"
0x14011b7d5  mov     [rbp+850h+var_3A8], rax
0x14011b7dc  lea     rax, [rbp+850h+var_8C8]
0x14011b7e0  mov     [rbp+850h+var_3A0], rax
0x14011b7e7  lea     rax, [rbp+850h+var_850]
0x14011b7eb  mov     [rbp+850h+var_390], rax
0x14011b7f2  lea     rax, aEvictunusedper; "EvictUnusedPeriod"
0x14011b7f9  mov     [rbp+850h+var_370], rax
0x14011b800  lea     rax, [rbp+850h+var_8C4]
0x14011b804  mov     [rbp+850h+var_368], rax
0x14011b80b  lea     rax, [rbp+850h+var_84C]
  ... truncated ...
```
