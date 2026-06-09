# NtfsPerformHotFix

- ea: `0x1400cf580`
- end: `0x1400d07ac`
- name: `NtfsPerformHotFix`
- size: `4652`
- prototype: ``
- caller_count: `0`
- callee_count: `46`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000549c`
- `0x1400054e8`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000d1e0`
- `0x14000d510`
- `0x140012ab0`
- `0x140012e70`
- `0x140014e74`
- `0x140016ea0`
- `0x14001c910`
- `0x140020de0`
- `0x1400291f0`
- `0x140029d80`
- `0x140031410`
- `0x140037db4`
- `0x1400410a8`
- `0x140042fc4`
- `0x14004b254`
- `0x140059250`
- `0x1400596c0`
- `0x1400c2798`
- `0x1400cf580`
- `0x1400d1948`
- `0x1401250b0`
- `0x140128d50`
- `0x140129500`
- `0x14013cde0`
- `0x14013f374`
- `0x140140660`
- `0x140150c80`
- `0x140159768`
- `0x14015f620`
- `0x1401606a0`
- `0x140160e90`
- `0x1401620c0`
- `0x140163f78`
- `0x14019a718`
- `0x1401ac080`
- `0x1401c00e0`
- `0x1401d24d8`
- `0x1401d2c34`
- `0x1401d2cec`
- `0x1401e0660`
- `0x140209910`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400d0557`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c0f7f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0557`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c0f7f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf688`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cf688`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d059c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402c0fc3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d059c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402c0fc3`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400cf6de`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400cf6de`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400d0590`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402c0fb7`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400d0590`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402c0fb7`
- `ntoskrnl!IoAllocateMdl` at `0x1400cfc2d`
- `ntoskrnl!IoAllocateMdl` at `0x1400cfc2d`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400cfc4d`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400cfc4d`
- `ntoskrnl!IoFreeMdl` at `0x1400cfc73`
- `ntoskrnl!IoFreeMdl` at `0x1400d000b`
- `ntoskrnl!IoFreeMdl` at `0x1400d0489`
- `ntoskrnl!IoFreeMdl` at `0x1402c0e90`
- `ntoskrnl!IoFreeMdl` at `0x1400cfc73`
- `ntoskrnl!IoFreeMdl` at `0x1400d000b`
- `ntoskrnl!IoFreeMdl` at `0x1400d0489`
- `ntoskrnl!IoFreeMdl` at `0x1402c0e90`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400cfcd7`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400cfcd7`
- `ntoskrnl!MmUnlockPages` at `0x1400cfff8`
- `ntoskrnl!MmUnlockPages` at `0x1400d0475`
- `ntoskrnl!MmUnlockPages` at `0x1402c0e74`
- `ntoskrnl!MmUnlockPages` at `0x1400cfff8`
- `ntoskrnl!MmUnlockPages` at `0x1400d0475`
- `ntoskrnl!MmUnlockPages` at `0x1402c0e74`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400cfcbf`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1400cfcbf`
- `ntoskrnl!CcUnpinData` at `0x1400cfc97`
- `ntoskrnl!CcUnpinData` at `0x1400d0045`
- `ntoskrnl!CcUnpinData` at `0x1400d0450`
- `ntoskrnl!CcUnpinData` at `0x1402c0e45`
- `ntoskrnl!CcUnpinData` at `0x1400cfc97`
- `ntoskrnl!CcUnpinData` at `0x1400d0045`
- `ntoskrnl!CcUnpinData` at `0x1400d0450`
- `ntoskrnl!CcUnpinData` at `0x1402c0e45`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cf989`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cf989`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400cffe9`
- `ntoskrnl!MmSetAddressRangeModified` at `0x1400cffe9`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x1400d002c`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x1400d002c`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400d0353`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400d0393`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400d0353`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400d0393`
- `ntoskrnl!CcFlushCache` at `0x1400d0126`
- `ntoskrnl!CcFlushCache` at `0x1400d0126`

## pseudocode

```c
void __fastcall NtfsPerformHotFix(__int64 a1)
{
  unsigned int v2; // r13d
  struct _MDL *v3; // r12
  void *v4; // rsi
  _QWORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 v9; // r14
  char v10; // cl
  __int64 v11; // rax
  __int64 v12; // r15
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r14
  unsigned int v18; // eax
  __int64 v19; // rcx
  struct _ERESOURCE *v20; // rcx
  __int16 *v21; // r14
  __int64 v22; // r14
  LONGLONG v23; // r14
  unsigned int j; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // r9d
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // r14d
  __int64 v39; // r15
  char v40; // r15
  __int64 v41; // r9
  __int64 v42; // rcx
  int Irp; // [rsp+88h] [rbp-258h]
  int Irpa; // [rsp+88h] [rbp-258h]
  int v45; // [rsp+90h] [rbp-250h]
  int v46; // [rsp+90h] [rbp-250h]
  int v47; // [rsp+98h] [rbp-248h]
  char v48; // [rsp+D9h] [rbp-207h]
  char v49; // [rsp+DAh] [rbp-206h]
  char v50; // [rsp+DBh] [rbp-205h]
  char v51[4]; // [rsp+DCh] [rbp-204h] BYREF
  NTSTATUS Exception; // [rsp+E0h] [rbp-200h]
  __int64 v53; // [rsp+E8h] [rbp-1F8h]
  unsigned int v54; // [rsp+F0h] [rbp-1F0h]
  __int64 v55; // [rsp+F8h] [rbp-1E8h] BYREF
  PVOID Bcb; // [rsp+100h] [rbp-1E0h] BYREF
  unsigned int v57; // [rsp+108h] [rbp-1D8h]
  __int64 v58; // [rsp+110h] [rbp-1D0h] BYREF
  PMDL Mdl; // [rsp+118h] [rbp-1C8h]
  char v60; // [rsp+120h] [rbp-1C0h]
  __int64 v61; // [rsp+128h] [rbp-1B8h]
  PVOID VirtualAddress; // [rsp+130h] [rbp-1B0h] BYREF
  __int64 v63; // [rsp+138h] [rbp-1A8h] BYREF
  __int64 v64; // [rsp+140h] [rbp-1A0h] BYREF
  int v65[2]; // [rsp+148h] [rbp-198h]
  unsigned int v66; // [rsp+150h] [rbp-190h]
  int v67; // [rsp+154h] [rbp-18Ch]
  unsigned int v68; // [rsp+158h] [rbp-188h]
  int v69; // [rsp+15Ch] [rbp-184h]
  __int64 v70; // [rsp+160h] [rbp-180h] BYREF
  __int64 v71; // [rsp+168h] [rbp-178h]
  __int64 v72; // [rsp+170h] [rbp-170h]
  __int64 v73; // [rsp+178h] [rbp-168h]
  PVOID Object; // [rsp+180h] [rbp-160h]
  int v75; // [rsp+188h] [rbp-158h]
  unsigned int v76; // [rsp+18Ch] [rbp-154h]
  __int64 v77; // [rsp+190h] [rbp-150h]
  __int64 v78; // [rsp+198h] [rbp-148h]
  __int64 v79; // [rsp+1A0h] [rbp-140h]
  __int64 v80; // [rsp+1A8h] [rbp-138h]
  void *v81; // [rsp+1B0h] [rbp-130h]
  __int64 v82; // [rsp+1B8h] [rbp-128h] BYREF
  __int64 i; // [rsp+1C0h] [rbp-120h]
  __int64 v84; // [rsp+1C8h] [rbp-118h]
  __int64 v85; // [rsp+1D0h] [rbp-110h]
  __int64 v86; // [rsp+1D8h] [rbp-108h]
  __int64 v87; // [rsp+1E0h] [rbp-100h] BYREF
  UNICODE_STRING v88; // [rsp+1E8h] [rbp-F8h] BYREF
  __int64 v89; // [rsp+1F8h] [rbp-E8h]
  __int64 v90; // [rsp+200h] [rbp-E0h]
  __int128 v91; // [rsp+208h] [rbp-D8h] BYREF
  __int128 v92; // [rsp+218h] [rbp-C8h]
  __int64 v93; // [rsp+228h] [rbp-B8h]
  _DWORD v94[24]; // [rsp+238h] [rbp-A8h] BYREF
  __int128 v95; // [rsp+298h] [rbp-48h] BYREF
  __int64 v96; // [rsp+2A8h] [rbp-38h]

  v53 = a1;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  memset(v94, 0, 0x58u);
  v64 = 0;
  v58 = 0;
  v63 = 0;
  v77 = 0;
  v55 = 0;
  v70 = 0;
  VirtualAddress = 0;
  Bcb = 0;
  v48 = 0;
  v50 = 0;
  v2 = 0;
  v54 = 0;
  v79 = 0;
  *(_QWORD *)v65 = 0;
  v3 = 0;
  Mdl = 0;
  v49 = 0;
  v4 = *(void **)(a1 + 112);
  Object = v4;
  v81 = v4;
  v95 = 0;
  v96 = 0;
  KeEnterCriticalRegion();
  v5 = *(_QWORD **)(a1 + 120);
  if ( v5 )
  {
    *((_QWORD *)&v95 + 1) = *v5;
    v96 = v5[1];
    *(_QWORD *)&v95 = (char *)&v95 + 8;
  }
  else
  {
    *(_QWORD *)&v95 = 0;
  }
  v86 = IoSetActivityIdThread(v95);
  if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    McTemplateK0pq_EtwWriteTransfer(v6, WORKITEM_START, v95);
  *(_QWORD *)(a1 + 176) = a1 + 168;
  *(_QWORD *)(a1 + 168) = a1 + 168;
  *(_QWORD *)(a1 + 160) = a1 + 152;
  *(_QWORD *)(a1 + 152) = a1 + 152;
  v7 = NtfsInitializeTopLevelIrp(&v91, 1, 0);
  NtfsUpdateIrpContextWithTopLevel(a1, v7);
  NtfsDecodeFileObject(a1, (_DWORD)v4, (unsigned int)&v64, (unsigned int)&v58, (__int64)&v63, (__int64)&v87, 0);
  v8 = v64;
  v61 = *(_QWORD *)(v64 + 88);
  v89 = v61;
  v9 = *(_QWORD *)(a1 + 576);
  v71 = v9;
  v84 = v9;
  v87 = v9;
  v10 = *(_BYTE *)(v64 + 488);
  v73 = v9 >> v10;
  v78 = v9 >> v10;
  v85 = *(__int64 *)(a1 + 584) >> v10;
  v55 = v85;
  v90 = v85;
  v57 = (unsigned int)(*(_DWORD *)(v64 + 480) + *(_DWORD *)(a1 + 592)) >> *(_DWORD *)(v64 + 488);
  v68 = v57;
  v76 = v57;
  v69 = *(_DWORD *)(a1 + 640);
  v75 = v69;
  *(_DWORD *)(a1 + 640) = 0;
  v11 = *(_QWORD *)(a1 + 40);
  v72 = v11;
  v80 = v11;
  *(_QWORD *)(a1 + 40) = 0;
  if ( v11 )
  {
    v2 = *(_DWORD *)(v11 + 48);
    v54 = v2;
  }
  memset(v94, 0, 0x58u);
  *(_DWORD *)(a1 + 12) |= 1u;
  *(_QWORD *)(a1 + 112) = 0;
  *((_QWORD *)&v91 + 1) = v9;
  v12 = v63;
  *(_QWORD *)&v92 = v63;
  LOBYTE(v13) = 1;
  NtfsAcquireExclusiveVcb(a1, v8, v13);
  if ( (*(_DWORD *)(v8 + 4) & 1) == 0 )
    goto LABEL_88;
  if ( *(_QWORD *)(v12 + 16) )
  {
    v17 = v58;
    LOBYTE(v15) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v58, v15) )
    {
      v18 = 0;
      v66 = 0;
      while ( v18 < 2 )
      {
        v19 = *(_QWORD *)(a1 + 8LL * v18 + 48);
        if ( !v19 || v19 == v17 )
        {
          *(_QWORD *)(a1 + 8LL * v18 + 48) = v17;
          break;
        }
        v66 = ++v18;
      }
    }
  }
  NtfsAcquireAllFiles(a1, v8, 7, v16);
  v48 = 1;
  if ( (*(_DWORD *)(v12 + 512) & 0x42) != 0 )
  {
LABEL_88:
    v40 = v48;
  }
  else
  {
    if ( v12 == *(_QWORD *)(v8 + 72) || v12 == *(_QWORD *)(v8 + 48) )
    {
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(v12 + 184), v12, 8);
      if ( *(_WORD *)v58 == 1794 )
        v20 = (struct _ERESOURCE *)(*(_QWORD *)(v58 + 104) + 64LL);
      else
        v20 = *(struct _ERESOURCE **)(v58 + 8);
      ExReleaseResourceLite(v20);
    }
    v14 = *(unsigned int *)(v58 + 4);
    if ( (v14 & 4) != 0 && (*(_DWORD *)(v12 + 200) & 0x10) != 0 )
    {
      *(_QWORD *)&v88.Length = 917516;
      v88.Buffer = L"Mirror";
      v51[0] = 0;
      i = 0;
      v82 = 0;
      v21 = NtfsCreateScb(a1, *(_QWORD *)(v12 + 184), 128, &v88, 0, 0, v51);
      *(_QWORD *)v65 = v21;
      v21[132] = 0;
      NtfsUpdateScbFromAttribute(a1, v21, 0);
      NtfsSnapshotScb(a1, v21);
      v22 = 0;
      for ( i = 0; ; i = v22 )
      {
        LOBYTE(v14) = *(_BYTE *)(v8 + 488);
        if ( v22 >= (__int64)(*(_QWORD *)(v12 + 24) + *(unsigned int *)(v8 + 480)) >> v14
          || !(unsigned __int8)NtfsLookupNtfsMcbEntryWithSyncFlag(v12 + 400, v22, &v82, &v70, 0, 0, 0, 0) )
        {
          break;
        }
        LOBYTE(v45) = 1;
        LOBYTE(Irp) = 0;
        if ( !(unsigned __int8)NtfsAddNtfsMcbEntry(*(_QWORD *)v65 + 400LL, v22, v82, v70, Irp, v45) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225626LL, 804896);
          NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 804896);
          if ( NtfsStatusDebugFlags
            && (_DWORD)v22
            && (_DWORD)v22 != 294
            && (unsigned int)(v22 - 298) > 1
            && (unsigned int)v22 < 0xFFFFFFED
            && (_DWORD)v22 != -1073741802
            && (unsigned int)(v22 + 2147483643) > 1
            && (_DWORD)v22 != -1073741807
            && (_DWORD)v22 != 259
            && (_DWORD)v22 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v22, 805015);
          }
          NtfsRaiseStatusInternal(a1, v22, 0, 0, 805015);
          if ( NtfsStatusDebugFlags
            && Exception
            && Exception != 294
            && (unsigned int)(Exception - 298) > 1
            && (unsigned int)Exception < 0xFFFFFFED
            && Exception != -1073741802
            && (unsigned int)(Exception + 2147483643) > 1
            && Exception != -1073741807
            && Exception != 259
            && Exception != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(v53, (unsigned int)Exception, 805005);
          }
          NtfsRaiseStatusInternal(v53, Exception, 0, 0, 805005);
LABEL_136:
          NtfsAttachCorruption_BadOrOrphanFRS(
            a1,
            2,
            805061,
            v29,
            *(_QWORD *)(v28 + 184) + 8LL,
            *(_QWORD *)(v28 + 184),
            0);
          NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA9000C48C5LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 805061);
          NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v61 + 184) + 8, *(_QWORD *)(v61 + 184), 805061);
          __debugbreak();
          JUMPOUT(0x1400D07ACLL);
        }
        v22 += v70;
      }
      v79 = v12;
      v12 = *(_QWORD *)v65;
      v63 = *(_QWORD *)v65;
    }
    v23 = v73;
    for ( j = v57; j; v68 = j )
    {
      if ( !(unsigned __int8)NtfsLookupAllocation(a1, (__int64)&v70)
        && (unsigned __int8)NtfsLookupAllocation(a1, (__int64)&v70)
        && v77 == v55 )
      {
        *(_DWORD *)(*(_QWORD *)(v12 + 184) + 16LL) |= 1u;
        if ( !v72 )
        {
          v67 = 100;
          NtfsCreateInternalAttributeStream(a1, v12, 0, 0, (__int64)&qword_1400620F0, 0);
          Exception = 0;
          NtfsPinStream(a1, v12, v71, *(unsigned int *)(v8 + 356), &Bcb, &VirtualAddress);
          v3 = IoAllocateMdl(VirtualAddress, *(_DWORD *)(v8 + 356), 0, 0, 0);
          Mdl = v3;
          MmProbeAndLockPages(v3, 0, IoWriteAccess);
          v49 = 1;
          v25 = (unsigned int)--v67;
          v23 = v73;
        }
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000) != 0 )
        {
          McTemplateU0dd_EtwWriteTransfer(v25, deviosup_c18593, (unsigned int)v23, HIDWORD(v78));
        }
        NtfsSnapshotScb(a1, v12);
        v26 = *(_QWORD *)(v12 + 496);
        if ( v23 < *(_QWORD *)(v26 + 64) )
          *(_QWORD *)(v26 + 64) = v23;
        v27 = *(_QWORD *)(v12 + 496);
        if ( v23 > *(_QWORD *)(v27 + 72) )
          *(_QWORD *)(v27 + 72) = v23;
        NtfsDeallocateClusters(a1, v8, v12, v23, v23, (__int64 *)(v12 + 472));
        LOBYTE(v47) = 0;
        if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                 a1,
                                 *(_QWORD *)(v61 + 184),
                                 *(_QWORD *)(v61 + 184) + 8LL,
                                 *(unsigned int *)(v61 + 256),
                                 v61 + 264,
                                 0,
                                 v47,
                                 0,
                                 0,
                                 v94) )
        {
          v28 = v61;
          if ( (*(_DWORD *)(v61 + 512) & 4) == 0 )
            goto LABEL_136;
        }
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000) != 0 )
        {
          McTemplateU0dd_EtwWriteTransfer(v28, deviosup_c18635, (unsigned int)v55, HIDWORD(v55));
        }
        NtfsAddBadCluster(a1, v8, v55);
        v50 = 1;
        v60 = 1;
        NtfsSnapshotScb(a1, v61);
        v30 = v61;
        v31 = *(_QWORD *)(v61 + 496);
        if ( v31 )
        {
          if ( v55 < *(_QWORD *)(v31 + 64) )
            *(_QWORD *)(v31 + 64) = v55;
          *(_QWORD *)(*(_QWORD *)(v30 + 496) + 72LL) = 0x7FFFFFFFFFFFFFFFLL;
        }
        LOBYTE(v46) = 0;
        NtfsAddAttributeAllocation(a1, v30, v94, &v55, &NtfsLarge1, v46);
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000) != 0 )
        {
          McTemplateU0_EtwWriteTransfer(v32, deviosup_c18688);
        }
        NtfsAddAllocation(a1, 1, 0, 0);
        NtfsCleanupAttributeContext(v33, v94);
        if ( !v72 )
        {
          v58 = v71;
          MmSetAddressRangeModified(VirtualAddress, *(unsigned int *)(v8 + 356));
          MmUnlockPages(v3);
          v49 = 0;
          IoFreeMdl(v3);
          v3 = 0;
          Mdl = 0;
          CcSetDirtyPinnedData(Bcb, 0);
          if ( Bcb )
          {
            CcUnpinData(Bcb);
            Bcb = 0;
          }
          VirtualAddress = 0;
          if ( (*(_DWORD *)(v12 + 512) & 1) != 0 )
            v58 -= *(_QWORD *)(*(_QWORD *)(v12 + 192) + 1952LL);
          if ( v12 != *(_QWORD *)(v8 + 64) )
          {
            LOBYTE(Irpa) = 0;
            Exception = NtfsFlushUserStream(a1, v12, &v58, *(unsigned int *)(v8 + 356), Irpa);
            if ( Exception < 0 )
            {
              v34 = *(_QWORD *)(a1 + 144);
              if ( a1 != v34 && *(_BYTE *)(a1 + 32) == 3 )
                v34 = a1;
              if ( *(int *)(v34 + 24) < 0 )
              {
                v35 = *(_QWORD *)(v34 + 16);
                if ( (v35 & 0x20000) != 0 )
                {
                  *(_DWORD *)(v34 + 24) = 0;
                  *(_QWORD *)(v34 + 16) = v35 & 0xFFFFFFFFFFFDFFFFuLL;
                }
              }
            }
          }
        }
        NtfsCommitCurrentTransaction(a1);
        if ( v12 == *(_QWORD *)(v8 + 64) )
        {
          v36 = *(_QWORD *)(v8 + 48);
          if ( *(_QWORD *)(v36 + 280) )
            CcFlushCache(
              (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v36 + 288) + 16LL),
              &NtfsLarge0,
              4 * *(_DWORD *)(v8 + 360),
              0);
        }
        else
        {
          NtfsWriteLog(a1, v12, 0, 23, 0, 0, 0, 0, 0, v23 << *(_BYTE *)(v8 + 488), 0, 0, *(_DWORD *)(v8 + 356));
          NtfsCommitCurrentTransaction(a1);
        }
        LfsFlushToLsn(*(_QWORD *)(v8 + 232), NtfsLargeMax);
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000) != 0 )
        {
          McTemplateU0_EtwWriteTransfer(v37, deviosup_c18823);
        }
      }
      v73 = ++v23;
      v78 = v23;
      ++v55;
      v14 = *(unsigned int *)(v8 + 356) + v71;
      v71 = v14;
      v84 = v14;
      j = v57 - 1;
      v57 = j;
    }
    v38 = v65[0];
    if ( *(_QWORD *)v65 )
    {
      v39 = v79;
      NtfsSwapMcbs(*(_QWORD *)v65 + 400LL, v79 + 400);
      NtfsTeardownStructures(a1, v38, 0);
      v63 = v39;
    }
    if ( v50 )
      NtfsWriteBadClusterHotFixEvent(a1, v76, v69);
    v40 = 1;
  }
  NtfsCleanupAttributeContext(v14, v94);
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  VirtualAddress = 0;
  if ( v49 )
    MmUnlockPages(v3);
  if ( v3 )
    IoFreeMdl(v3);
  if ( v40 )
    NtfsReleaseAllFiles(a1, v8, 6);
  NtfsReleaseVcb(a1, v8);
  if ( NtfsStatusDebugFlags
    && v2
    && v2 != 294
    && v2 - 298 > 1
    && v2 < 0xFFFFFFED
    && v2 != -1073741802
    && v2 + 2147483643 > 1
    && v2 != -1073741807
    && v2 != 259
    && v2 != -1073741608 )
  {
    NtfsStatusTraceAndDebugInternal(a1, v2, 805437);
  }
  LOBYTE(v41) = v72 != 0;
  NtfsExtendedCompleteRequestInternal(a1, v72, v2, v41, (v2 & 0x80000000) == 0);
  ObfDereferenceObject(Object);
  if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    McTemplateK0pq_EtwWriteTransfer(v42, WORKITEM_COMPLETE, v95);
  IoClearActivityIdThread(v86);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400cf580  mov     r11, rsp
0x1400cf583  mov     [r11+10h], rbx
0x1400cf587  mov     [r11+18h], rsi
0x1400cf58b  push    rdi
0x1400cf58c  push    r12
0x1400cf58e  push    r13
0x1400cf590  push    r14
0x1400cf592  push    r15
0x1400cf594  sub     rsp, 250h
0x1400cf59b  mov     rax, cs:__security_cookie
0x1400cf5a2  xor     rax, rsp
0x1400cf5a5  mov     [rsp+278h+var_30], rax
0x1400cf5ad  mov     rdi, rcx
0x1400cf5b0  mov     [r11-1F8h], rcx
0x1400cf5b7  xorps   xmm0, xmm0
0x1400cf5ba  xor     eax, eax
0x1400cf5bc  movups  [rsp+278h+var_D8], xmm0
0x1400cf5c4  movups  [rsp+278h+var_C8], xmm0
0x1400cf5cc  mov     [r11-0B8h], rax
0x1400cf5d3  lea     r15d, [rax+58h]
0x1400cf5d7  mov     r8d, r15d; Size
0x1400cf5da  xor     edx, edx; Val
0x1400cf5dc  lea     rcx, [r11-0A8h]; void *
0x1400cf5e3  call    memset
0x1400cf5e8  xor     ebx, ebx
0x1400cf5ea  mov     [rsp+278h+var_1A0], rbx
0x1400cf5f2  mov     [rsp+278h+var_1D0], rbx
0x1400cf5fa  mov     [rsp+278h+var_1A8], rbx
0x1400cf602  mov     [rsp+278h+var_150], rbx
0x1400cf60a  mov     [rsp+278h+var_1E8], rbx
0x1400cf612  mov     [rsp+278h+var_180], rbx
0x1400cf61a  mov     [rsp+278h+VirtualAddress], rbx
0x1400cf622  mov     [rsp+278h+Bcb], rbx
0x1400cf62a  mov     [rsp+278h+var_207], bl
0x1400cf62e  mov     [rsp+278h+var_205], bl
0x1400cf632  mov     r13d, ebx
0x1400cf635  mov     [rsp+278h+var_1F0], ebx
0x1400cf63c  mov     [rsp+278h+var_140], rbx
0x1400cf644  mov     qword ptr [rsp+278h+var_198], rbx
0x1400cf64c  mov     r12d, ebx
0x1400cf64f  mov     [rsp+278h+Mdl], rbx
0x1400cf657  mov     [rsp+278h+var_206], bl
0x1400cf65b  mov     [rsp+278h+var_208], bl
0x1400cf65f  mov     rsi, [rdi+70h]
0x1400cf663  mov     [rsp+278h+Object], rsi
0x1400cf66b  mov     [rsp+278h+var_130], rsi
0x1400cf673  xorps   xmm0, xmm0
0x1400cf676  xor     eax, eax
0x1400cf678  movups  [rsp+278h+var_48], xmm0
0x1400cf680  mov     [rsp+278h+var_38], rax
0x1400cf688  call    cs:__imp_KeEnterCriticalRegion
0x1400cf68f  nop     dword ptr [rax+rax+00h]
0x1400cf694  mov     rcx, [rdi+78h]
0x1400cf698  test    rcx, rcx
0x1400cf69b  jz      short loc_1400CF6C6
0x1400cf69d  mov     rax, [rcx]
0x1400cf6a0  mov     qword ptr [rsp+278h+var_48+8], rax
0x1400cf6a8  mov     rax, [rcx+8]
0x1400cf6ac  mov     [rsp+278h+var_38], rax
0x1400cf6b4  lea     rax, [rsp+278h+var_48+8]
0x1400cf6bc  mov     qword ptr [rsp+278h+var_48], rax
0x1400cf6c4  jmp     short loc_1400CF6CE
0x1400cf6c6  mov     qword ptr [rsp+278h+var_48], rbx
0x1400cf6ce  mov     rax, qword ptr [rsp+278h+var_48]
0x1400cf6d6  mov     rcx, qword ptr [rsp+278h+var_48]
0x1400cf6de  call    cs:__imp_IoSetActivityIdThread
0x1400cf6e5  nop     dword ptr [rax+rax+00h]
0x1400cf6ea  mov     [rsp+278h+var_108], rax
0x1400cf6f2  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x1400cf6f9  jz      short loc_1400CF717
0x1400cf6fb  mov     r8, qword ptr [rsp+278h+var_48]
0x1400cf703  mov     dword ptr [rsp+278h+Irp], 4
0x1400cf70b  lea     rdx, WORKITEM_START
0x1400cf712  call    McTemplateK0pq_EtwWriteTransfer
0x1400cf717  lea     rax, [rdi+0A8h]
0x1400cf71e  mov     [rax+8], rax
0x1400cf722  mov     [rax], rax
0x1400cf725  lea     rax, [rdi+98h]
0x1400cf72c  mov     [rax+8], rax
0x1400cf730  mov     [rax], rax
0x1400cf733  xor     r8d, r8d
0x1400cf736  lea     edx, [r8+1]
0x1400cf73a  lea     rcx, [rsp+278h+var_D8]
0x1400cf742  call    NtfsInitializeTopLevelIrp
0x1400cf747  mov     rdx, rax
0x1400cf74a  mov     rcx, rdi
0x1400cf74d  call    NtfsUpdateIrpContextWithTopLevel
0x1400cf752  mov     byte ptr [rsp+278h+var_248], bl
0x1400cf756  lea     rax, [rsp+278h+var_100]
0x1400cf75e  mov     [rsp+278h+var_250], rax
0x1400cf763  lea     rax, [rsp+278h+var_1A8]
0x1400cf76b  mov     [rsp+278h+Irp], rax
0x1400cf770  lea     r9, [rsp+278h+var_1D0]
0x1400cf778  lea     r8, [rsp+278h+var_1A0]
0x1400cf780  mov     rdx, rsi
0x1400cf783  mov     rcx, rdi
0x1400cf786  call    NtfsDecodeFileObject
0x1400cf78b  mov     rsi, [rsp+278h+var_1A0]
0x1400cf793  mov     rax, [rsi+58h]
0x1400cf797  mov     [rsp+278h+var_1B8], rax
0x1400cf79f  mov     [rsp+278h+var_E8], rax
0x1400cf7a7  mov     r14, [rdi+240h]
0x1400cf7ae  mov     [rsp+278h+var_178], r14
0x1400cf7b6  mov     [rsp+278h+var_118], r14
0x1400cf7be  mov     [rsp+278h+var_100], r14
0x1400cf7c6  movsx   ecx, byte ptr [rsi+1E8h]
0x1400cf7cd  mov     rax, r14
0x1400cf7d0  sar     rax, cl
0x1400cf7d3  mov     [rsp+278h+var_168], rax
0x1400cf7db  mov     [rsp+278h+var_148], rax
0x1400cf7e3  mov     rax, [rdi+248h]
0x1400cf7ea  sar     rax, cl
0x1400cf7ed  mov     [rsp+278h+var_110], rax
0x1400cf7f5  mov     [rsp+278h+var_1E8], rax
0x1400cf7fd  mov     [rsp+278h+var_E0], rax
0x1400cf805  mov     eax, [rdi+250h]
0x1400cf80b  add     eax, [rsi+1E0h]
0x1400cf811  mov     ecx, [rsi+1E8h]
0x1400cf817  shr     eax, cl
0x1400cf819  mov     [rsp+278h+var_1D8], eax
0x1400cf820  mov     [rsp+278h+var_188], eax
0x1400cf827  mov     [rsp+278h+var_154], eax
0x1400cf82e  mov     eax, [rdi+280h]
0x1400cf834  mov     [rsp+278h+var_184], eax
0x1400cf83b  mov     [rsp+278h+var_158], eax
0x1400cf842  mov     [rdi+280h], ebx
0x1400cf848  mov     rax, [rdi+28h]
0x1400cf84c  mov     [rsp+278h+var_170], rax
0x1400cf854  mov     [rsp+278h+var_138], rax
0x1400cf85c  mov     [rdi+28h], rbx
0x1400cf860  test    rax, rax
0x1400cf863  jz      short loc_1400CF871
0x1400cf865  mov     r13d, [rax+30h]
0x1400cf869  mov     [rsp+278h+var_1F0], r13d
0x1400cf871  mov     r8, r15; Size
0x1400cf874  xor     edx, edx; Val
0x1400cf876  lea     rcx, [rsp+278h+var_A8]; void *
0x1400cf87e  call    memset
0x1400cf883  or      dword ptr [rdi+0Ch], 1
0x1400cf887  mov     [rdi+70h], rbx
0x1400cf88b  mov     qword ptr [rsp+278h+var_D8+8], r14
0x1400cf893  mov     r15, [rsp+278h+var_1A8]
0x1400cf89b  mov     qword ptr [rsp+278h+var_C8], r15
0x1400cf8a3  mov     r8b, 1
0x1400cf8a6  mov     rdx, rsi
0x1400cf8a9  mov     rcx, rdi
0x1400cf8ac  call    NtfsAcquireExclusiveVcb
0x1400cf8b1  mov     [rsp+278h+var_208], 1
0x1400cf8b6  mov     eax, [rsi+4]
0x1400cf8b9  test    al, 1
0x1400cf8bb  jz      loc_1400D042C
0x1400cf8c1  cmp     [r15+10h], rbx
0x1400cf8c5  jz      short loc_1400CF917
0x1400cf8c7  mov     r14, [rsp+278h+var_1D0]
0x1400cf8cf  mov     r8b, 1
0x1400cf8d2  mov     rdx, r14
0x1400cf8d5  mov     rcx, rdi
0x1400cf8d8  call    NtfsAcquirePagingResourceExclusive
0x1400cf8dd  test    al, al
0x1400cf8df  jz      short loc_1400CF917
0x1400cf8e1  mov     [rsp+278h+var_190], ebx
0x1400cf8e8  mov     eax, ebx
0x1400cf8ea  mov     [rsp+278h+var_190], ebx
0x1400cf8f1  cmp     eax, 2
0x1400cf8f4  jnb     short loc_1400CF917
0x1400cf8f6  mov     edx, eax
0x1400cf8f8  mov     rcx, [rdi+rdx*8+30h]
0x1400cf8fd  test    rcx, rcx
0x1400cf900  jz      short loc_1400CF912
0x1400cf902  cmp     rcx, r14
0x1400cf905  jz      short loc_1400CF912
0x1400cf907  inc     eax
0x1400cf909  mov     [rsp+278h+var_190], eax
0x1400cf910  jmp     short loc_1400CF8F1
0x1400cf912  mov     [rdi+rdx*8+30h], r14
0x1400cf917  mov     r8d, 7
0x1400cf91d  mov     rdx, rsi
0x1400cf920  mov     rcx, rdi
0x1400cf923  call    NtfsAcquireAllFiles
0x1400cf928  mov     al, 1
0x1400cf92a  mov     [rsp+278h+var_207], al
0x1400cf92e  mov     eax, [r15+200h]
0x1400cf935  test    al, 42h
0x1400cf937  jnz     loc_1400D042C
0x1400cf93d  cmp     r15, [rsi+48h]
0x1400cf941  jz      short loc_1400CF949
0x1400cf943  cmp     r15, [rsi+30h]
0x1400cf947  jnz     short loc_1400CF996
0x1400cf949  mov     r9d, 8
0x1400cf94f  mov     r8, r15
0x1400cf952  mov     rdx, [r15+0B8h]
0x1400cf959  mov     rcx, rdi
0x1400cf95c  call    NtfsAcquireExclusiveFcb
0x1400cf961  mov     eax, 702h
0x1400cf966  mov     rcx, [rsp+278h+var_1D0]
0x1400cf96e  cmp     ax, [rcx]
0x1400cf971  jnz     short loc_1400CF97D
0x1400cf973  mov     rcx, [rcx+68h]
0x1400cf977  add     rcx, 40h ; '@'
0x1400cf97b  jmp     short loc_1400CF989
0x1400cf97d  mov     rcx, [rsp+278h+var_1D0]
0x1400cf985  mov     rcx, [rcx+8]; Resource
0x1400cf989  call    cs:__imp_ExReleaseResourceLite
0x1400cf990  nop     dword ptr [rax+rax+00h]
0x1400cf995  nop
0x1400cf996  mov     rax, [rsp+278h+var_1D0]
0x1400cf99e  mov     ecx, [rax+4]
0x1400cf9a1  test    cl, 4
0x1400cf9a4  jz      loc_1400CFB06
0x1400cf9aa  mov     eax, [r15+0C8h]
0x1400cf9b1  test    al, 10h
0x1400cf9b3  jz      loc_1400CFB06
0x1400cf9b9  mov     [rsp+278h+var_F8], 0E000Ch
0x1400cf9c5  lea     rax, aMirror; "Mirror"
0x1400cf9cc  mov     [rsp+278h+var_F0], rax
0x1400cf9d4  mov     [rsp+278h+var_204], bl
0x1400cf9d8  mov     [rsp+278h+var_120], rbx
0x1400cf9e0  mov     [rsp+278h+var_128], rbx
0x1400cf9e8  lea     rax, [rsp+278h+var_204]
0x1400cf9ed  mov     [rsp+278h+var_248], rax
0x1400cf9f2  mov     [rsp+278h+var_250], rbx
0x1400cf9f7  mov     byte ptr [rsp+278h+Irp], bl
0x1400cf9fb  lea     r9, [rsp+278h+var_F8]
0x1400cfa03  mov     r8d, 80h
0x1400cfa09  mov     rdx, [r15+0B8h]
0x1400cfa10  mov     rcx, rdi
0x1400cfa13  call    NtfsCreateScb
0x1400cfa18  mov     r14, rax
0x1400cfa1b  mov     qword ptr [rsp+278h+var_198], rax
0x1400cfa23  mov     [rax+108h], bx
0x1400cfa2a  xor     r8d, r8d
0x1400cfa2d  mov     rdx, rax
0x1400cfa30  mov     rcx, rdi
0x1400cfa33  call    NtfsUpdateScbFromAttribute
0x1400cfa38  mov     rdx, r14
0x1400cfa3b  mov     rcx, rdi
0x1400cfa3e  call    NtfsSnapshotScb
0x1400cfa43  mov     r14, rbx
0x1400cfa46  mov     [rsp+278h+var_120], rbx
0x1400cfa4e  mov     eax, [rsi+1E0h]
0x1400cfa54  add     rax, [r15+18h]
0x1400cfa58  mov     cl, [rsi+1E8h]
0x1400cfa5e  sar     rax, cl
0x1400cfa61  cmp     r14, rax
0x1400cfa64  jge     loc_1400CFAEE
0x1400cfa6a  lea     rcx, [r15+190h]
0x1400cfa71  mov     [rsp+278h+var_240], rbx
0x1400cfa76  mov     [rsp+278h+var_248], rbx
0x1400cfa7b  mov     [rsp+278h+var_250], rbx
0x1400cfa80  mov     [rsp+278h+Irp], rbx
0x1400cfa85  lea     r9, [rsp+278h+var_180]
0x1400cfa8d  lea     r8, [rsp+278h+var_128]
0x1400cfa95  mov     rdx, r14
0x1400cfa98  call    NtfsLookupNtfsMcbEntryWithSyncFlag
0x1400cfa9d  test    al, al
0x1400cfa9f  jz      short loc_1400CFAEE
0x1400cfaa1  mov     rcx, qword ptr [rsp+278h+var_198]
0x1400cfaa9  add     rcx, 190h
0x1400cfab0  mov     byte ptr [rsp+278h+var_250], 1
0x1400cfab5  mov     byte ptr [rsp+278h+Irp], bl
0x1400cfab9  mov     r9, [rsp+278h+var_180]
0x1400cfac1  mov     r8, [rsp+278h+var_128]
0x1400cfac9  mov     rdx, r14
0x1400cfacc  call    NtfsAddNtfsMcbEntry
0x1400cfad1  test    al, al
0x1400cfad3  jz      loc_1400D05D6
0x1400cfad9  add     r14, [rsp+278h+var_180]
0x1400cfae1  mov     [rsp+278h+var_120], r14
0x1400cfae9  jmp     loc_1400CFA4E
0x1400cfaee  mov     [rsp+278h+var_140], r15
0x1400cfaf6  mov     r15, qword ptr [rsp+278h+var_198]
0x1400cfafe  mov     [rsp+278h+var_1A8], r15
0x1400cfb06  mov     r14, [rsp+278h+var_168]
0x1400cfb0e  mov     eax, [rsp+278h+var_1D8]
0x1400cfb15  test    eax, eax
0x1400cfb17  jz      loc_1400D0218
0x1400cfb1d  lea     rax, [rsp+278h+var_180]
0x1400cfb25  mov     [rsp+278h+Irp], rax
0x1400cfb2a  lea     r9, [rsp+278h+var_150]
0x1400cfb32  mov     r8, [rsp+278h+var_1E8]
0x1400cfb3a  mov     rdx, [rsp+278h+var_1B8]
0x1400cfb42  mov     rcx, rdi
0x1400cfb45  call    NtfsLookupAllocation
0x1400cfb4a  test    al, al
0x1400cfb4c  jnz     loc_1400D01C0
0x1400cfb52  lea     rax, [rsp+278h+var_180]
0x1400cfb5a  mov     [rsp+278h+Irp], rax
0x1400cfb5f  lea     r9, [rsp+278h+var_150]
0x1400cfb67  mov     r8, r14
0x1400cfb6a  mov     rdx, r15
0x1400cfb6d  mov     rcx, rdi
0x1400cfb70  call    NtfsLookupAllocation
0x1400cfb75  test    al, al
0x1400cfb77  jz      loc_1400D01C0
0x1400cfb7d  mov     rax, [rsp+278h+var_150]
0x1400cfb85  cmp     rax, [rsp+278h+var_1E8]
0x1400cfb8d  jnz     loc_1400D01C0
0x1400cfb93  mov     rax, [r15+0B8h]
0x1400cfb9a  or      dword ptr [rax+10h], 1
0x1400cfb9e  cmp     [rsp+278h+var_170], rbx
  ... truncated ...
```
