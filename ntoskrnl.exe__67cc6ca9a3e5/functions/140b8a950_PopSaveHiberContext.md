# PopSaveHiberContext

- ea: `0x140b8a950`
- end: `0x140b8b397`
- name: `PopSaveHiberContext`
- size: `2631`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1406e7e30`

## callees

- `0x14031c3b0`
- `0x140457f90`
- `0x1404b8970`
- `0x1404cdb64`
- `0x140522d60`
- `0x140525500`
- `0x14052b204`
- `0x14052fb60`
- `0x14053a530`
- `0x1405859e0`
- `0x1405bc5d0`
- `0x1405bc9b4`
- `0x1405c3978`
- `0x1405c39e0`
- `0x1405c3cb0`
- `0x1405c3db4`
- `0x1405c7d1c`
- `0x1405cacac`
- `0x1405cb638`
- `0x1405cb784`
- `0x1405cb874`
- `0x1405fd770`
- `0x1406035c4`
- `0x1406035e0`
- `0x1406e8590`
- `0x1406f4480`
- `0x1406f4880`
- `0x140b88124`
- `0x140b889ac`
- `0x140b8a8c0`
- `0x140b8a950`
- `0x140b8b464`
- `0x140b8b4a8`
- `0x140b9a074`
- `0x140b9a24c`
- `0x140b9abc4`
- `0x140b9ac58`
- `0x140b9bb8c`
- `0x140b9bc24`
- `0x140b9be28`
- `0x140b9c208`
- `0x140ba5330`

## import_xrefs

- `PSHED!PshedArePluginsPresent` at `0x140b8aaad`
- `PSHED!PshedArePluginsPresent` at `0x140b8aaad`

## pseudocode

```c
__int64 __fastcall PopSaveHiberContext(ULONG_PTR BugCheckParameter3)
{
  __int64 v1; // rax
  __int64 Number; // rbx
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rcx
  unsigned __int64 v17; // rax
  bool v18; // zf
  __int64 v19; // r13
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ebx
  RTL_BITMAP *v23; // rsi
  unsigned int v24; // ebx
  _DWORD *v25; // rcx
  _DWORD *v26; // rdx
  RTL_BITMAP *v27; // rcx
  _QWORD *v28; // r12
  __int64 v29; // rcx
  unsigned __int64 v30; // r14
  ULONG_PTR v31; // rdi
  unsigned int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // ecx
  ULONG_PTR *v35; // rbx
  unsigned __int64 v36; // rax
  _QWORD *v37; // rbx
  _QWORD *v38; // rsi
  _QWORD *v39; // rax
  unsigned __int64 v40; // rdi
  unsigned __int64 v41; // r14
  char *v42; // r12
  __int64 v43; // rsi
  unsigned __int64 v44; // rax
  _QWORD *v45; // rcx
  PVOID v46; // rax
  int v47; // edi
  int v48; // eax
  unsigned int v49; // ecx
  __int64 v50; // rbx
  ULONG v51; // eax
  _DWORD *v52; // rdi
  int v53; // esi
  __int64 v54; // rbx
  __int64 v55; // r14
  __int64 v56; // rdi
  __int64 v57; // rax
  unsigned __int64 v58; // rbx
  unsigned __int64 v59; // rax
  unsigned int v60; // r8d
  __int64 i; // rbx
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rdx
  ULONG v65; // eax
  _DWORD *v66; // rdi
  int v67; // esi
  __int64 v68; // rbx
  unsigned __int64 v69; // r14
  __int64 v70; // rdi
  unsigned __int64 v71; // rbx
  __int64 v72; // r8
  __int64 v73; // rcx
  __int64 v74; // rcx
  unsigned __int64 v76; // [rsp+30h] [rbp-D0h]
  __int128 v77; // [rsp+40h] [rbp-C0h] BYREF
  void *v78; // [rsp+50h] [rbp-B0h]
  __int128 v79; // [rsp+60h] [rbp-A0h]
  __int128 v80; // [rsp+70h] [rbp-90h]
  __int128 v81; // [rsp+80h] [rbp-80h]
  __int128 v82; // [rsp+90h] [rbp-70h]
  __int128 v83; // [rsp+A0h] [rbp-60h]
  _OWORD v84[5]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v85; // [rsp+100h] [rbp+0h] BYREF
  __int64 v86; // [rsp+110h] [rbp+10h]
  char v87; // [rsp+170h] [rbp+70h]
  unsigned int v88; // [rsp+178h] [rbp+78h] BYREF
  int v89; // [rsp+180h] [rbp+80h] BYREF
  __int64 v90; // [rsp+188h] [rbp+88h]

  v86 = 0;
  v78 = 0;
  v1 = *(_QWORD *)(BugCheckParameter3 + 352);
  v85 = 0;
  v89 = 0;
  v77 = 0;
  v88 = 0;
  v90 = v1;
  Number = KeGetCurrentPrcb()->Number;
  if ( (_DWORD)Number )
  {
    if ( (unsigned __int8)PopIsHvAssistedHibernation() )
    {
      _InterlockedAdd((volatile signed __int32 *)(BugCheckParameter3 + 16), 1u);
      while ( *(_DWORD *)(BugCheckParameter3 + 16) )
        _mm_pause();
      if ( LOBYTE(PopAwaymodeLock.Padding[2]) )
        return 1073742484;
      _InterlockedAdd((volatile signed __int32 *)(BugCheckParameter3 + 20), 1u);
      while ( *(_DWORD *)(BugCheckParameter3 + 20) )
        _mm_pause();
    }
  }
  else
  {
    PopCheckpointSystemSleep(19);
  }
  if ( (unsigned int)Number >= *(_DWORD *)(BugCheckParameter3 + 288) )
    return 0;
  if ( (_DWORD)Number )
  {
    while ( !*(_BYTE *)(BugCheckParameter3 + 3) )
      _mm_pause();
    LOBYTE(v4) = 1;
    v6 = 168 * Number;
    PopCompressHiberBlocks(BugCheckParameter3, v6 + *(_QWORD *)(BugCheckParameter3 + 296), v4);
    _InterlockedAdd((volatile signed __int32 *)(BugCheckParameter3 + 8), 1u);
    while ( *(_DWORD *)(BugCheckParameter3 + 8) )
      _mm_pause();
    return (unsigned int)PopCompressHiberBlocks(BugCheckParameter3, v6 + *(_QWORD *)(BugCheckParameter3 + 296), 0);
  }
  PopWatchdogTimerCount = 0;
  if ( (unsigned __int8)KeDisableInterrupts() )
    PopInternalError(0xA1E00u);
  if ( (PopSimulateHiberBugcheck & 0x80u) != 0 )
  {
    v87 = 0;
LABEL_26:
    dword_140EFA3F8 |= 4u;
    byte_140EFA361 = 1;
    goto LABEL_27;
  }
  v87 = IoDumpStackResumeCapable(&v89);
  if ( !v87 )
    goto LABEL_26;
LABEL_27:
  if ( (unsigned int)PshedArePluginsPresent() )
  {
    dword_140EFA3F8 |= 8u;
    byte_140EFA361 = 1;
  }
  if ( !(unsigned __int8)guard_dispatch_icall_no_overrides(v7) )
  {
    dword_140EFA3F8 |= 1u;
    byte_140EFA361 = 1;
  }
  if ( byte_140EFA361 )
  {
    if ( (unsigned int)KiGetCpuVendor() == 2 )
    {
      _RAX = 0;
      __asm { cpuid }
      if ( (unsigned int)_RAX >= 7 )
      {
        _RAX = 7;
        __asm { cpuid }
        if ( (_RCX & 0x2000) != 0 )
        {
          v17 = __readmsr(0x982u);
          _RDX = (unsigned __int64)HIDWORD(v17) << 32;
          if ( (v17 & 2) != 0 && (v17 & 0xF00000000LL) != 0 )
            KeBugCheckEx(0xA0u, 0x112u, 0xAu, BugCheckParameter3, 0);
        }
      }
    }
  }
  v18 = HvlHypervisorConnected == 0;
  v19 = *(_QWORD *)(BugCheckParameter3 + 216);
  *(_QWORD *)(BugCheckParameter3 + 176) = &v85;
  *(_QWORD *)(BugCheckParameter3 + 192) = PoWakeState;
  *(_BYTE *)(BugCheckParameter3 + 1) = 1;
  if ( !v18 )
  {
    PopHibernateHvMinloopEnabled = 1;
    HvlDisableEnlightenment(0, _RDX);
    guard_dispatch_icall_no_overrides(v20);
    if ( (unsigned __int8)PopIsHvAssistedHibernation() )
    {
      _InterlockedAdd((volatile signed __int32 *)(BugCheckParameter3 + 16), 1u);
      while ( *(_DWORD *)(BugCheckParameter3 + 16) != (_DWORD)KeNumberProcessors_0 )
        _mm_pause();
      *(_QWORD *)&v79 = qword_140E2B428;
      *((_QWORD *)&v79 + 1) = qword_140E2B3C8;
      *(_QWORD *)&v80 = qword_140E2B3D0;
      *((_QWORD *)&v80 + 1) = qword_140E2B3C0;
      *(_QWORD *)&v81 = qword_140E2B3E0;
      *((_QWORD *)&v81 + 1) = qword_140E2B3D8;
      v82 = xmmword_140E2B408;
      v83 = xmmword_140E2B418;
      v84[0] = v79;
      v84[1] = v80;
      v84[2] = v81;
      v84[4] = xmmword_140E2B418;
      v84[3] = xmmword_140E2B408;
      if ( *(_BYTE *)(BugCheckParameter3 + 488) )
        v21 = HvlPrepareForSecureHibernate(v84);
      else
        v21 = HvlPrepareForHibernate((unsigned int)v84, (int)v19 + 1152, (int)v19 + 1160, (int)v19 + 1168, v19 + 1176);
      v22 = v21;
      if ( v21 < 0 )
      {
        PopInternalAddToDumpFile(*(_QWORD *)(BugCheckParameter3 + 184), 376, 0);
        KeBugCheckEx(0xA0u, 0xCu, v22, *(_QWORD *)(BugCheckParameter3 + 184), 0);
      }
      *(_DWORD *)(BugCheckParameter3 + 16) = 0;
      _InterlockedAdd((volatile signed __int32 *)(BugCheckParameter3 + 20), 1u);
      while ( *(_DWORD *)(BugCheckParameter3 + 20) != (_DWORD)KeNumberProcessors_0 )
        _mm_pause();
      *(_DWORD *)(BugCheckParameter3 + 16) = KeNumberProcessors_0;
      *(_DWORD *)(BugCheckParameter3 + 20) = 0;
    }
    if ( *(_BYTE *)(BugCheckParameter3 + 488) )
      HvlDiscardSecurePagesFromHibernation((PVOID)BugCheckParameter3);
    else
      HvlDiscardPagesFromHibernation((PVOID)BugCheckParameter3);
  }
  *(_QWORD *)&v77 = v19;
  *((_QWORD *)&v77 + 1) = &PopHiberNotificationDiscardMemoryCallback;
  v78 = &PopHiberNotificationDiscardPhysicalMemoryCallback;
  PopSstInvokeNotificationHandlers(0, &v77);
  ++*(_DWORD *)v19;
  v23 = (RTL_BITMAP *)(BugCheckParameter3 + 64);
  v24 = 0;
  v25 = *(_DWORD **)(BugCheckParameter3 + 72);
  v26 = *(_DWORD **)(BugCheckParameter3 + 56);
  if ( (*(_DWORD *)(BugCheckParameter3 + 64) & 0xFFFFFFE0) != 0 )
  {
    do
    {
      ++v24;
      *v25++ |= *v26++;
    }
    while ( v24 < v23->SizeOfBitMap >> 5 );
  }
  v27 = (RTL_BITMAP *)(BugCheckParameter3 + 48);
  if ( !byte_140EFA361 )
  {
    RtlCopyBitMap(BugCheckParameter3 + 64, BugCheckParameter3 + 48, 0);
    v27 = (RTL_BITMAP *)(BugCheckParameter3 + 64);
  }
  RtlSetAllBits(v27);
  *(_DWORD *)(BugCheckParameter3 + 200) = 8;
  v28 = (_QWORD *)(BugCheckParameter3 + 184);
  PopHibernateInProgress = 1;
  IoGetDumpHiberRanges(v29, *(_QWORD *)(BugCheckParameter3 + 184));
  if ( !byte_140EFA361 )
    IoNotifyDump(1);
  v30 = __rdtsc();
  v31 = (int)IoInitializeDumpStack(*v28);
  IoGetDumpStackTransferSizes(0, &v88);
  v32 = v88;
  if ( v88 >= 0x100000 )
  {
    v32 = 0x100000;
    v88 = 0x100000;
  }
  v33 = *(_DWORD *)(BugCheckParameter3 + 440);
  v34 = v32 >> 12;
  if ( v34 == v33 )
  {
    v35 = (ULONG_PTR *)(BugCheckParameter3 + 184);
  }
  else
  {
    if ( v34 <= v33 )
      v33 = v34;
    v35 = (ULONG_PTR *)(BugCheckParameter3 + 184);
    *(_DWORD *)(BugCheckParameter3 + 440) = v33;
  }
  v36 = __rdtsc();
  qword_140EFA788 += (((unsigned __int64)HIDWORD(v36) << 32) | (unsigned int)v36) - v30;
  if ( (v31 & 0x80000000) != 0LL || PopSimulateHiberBugcheck == 1 )
  {
    PopCheckpointSystemSleep(20);
    PopInternalAddToDumpFile(*v35, 376, 0);
    KeBugCheckEx(0xA0u, 0xCu, v31, *v35, 0);
  }
  PopMarkComponentsBootPhase((PVOID)BugCheckParameter3);
  v37 = *(_QWORD **)(BugCheckParameter3 + 80);
  if ( v37 != (_QWORD *)(BugCheckParameter3 + 80) )
  {
    v38 = (_QWORD *)(BugCheckParameter3 + 80);
    do
    {
      v39 = v37;
      v37 = (_QWORD *)*v37;
      v40 = v39[3];
      v41 = v39[4];
      v42 = (char *)v39[5];
      *(_QWORD *)(BugCheckParameter3 + 104) = v41 + *(_QWORD *)(BugCheckParameter3 + 104) - v40;
      if ( v40 < v41 )
      {
        v43 = v90;
        do
        {
          PopCreateDumpMdl(BugCheckParameter3, v43, v40, v41);
          memmove(v42, *(const void **)(v43 + 24), *(unsigned int *)(v43 + 40));
          v44 = *(unsigned int *)(v43 + 40);
          v42 += v44;
          v40 += v44 >> 12;
        }
        while ( v40 < v41 );
        v38 = (_QWORD *)(BugCheckParameter3 + 80);
      }
    }
    while ( v37 != v38 );
    v23 = (RTL_BITMAP *)(BugCheckParameter3 + 64);
    v28 = (_QWORD *)(BugCheckParameter3 + 184);
  }
  PopResetRangeEnum(BugCheckParameter3);
  v45 = *(_QWORD **)(BugCheckParameter3 + 176);
  v46 = qword_140EFA338;
  *v45 = qword_140EFA338;
  v45[1] = v46;
  v45[2] = 0;
  v76 = __rdtsc();
  v47 = PopWriteHeaderPages(BugCheckParameter3, v19);
  if ( v47 < 0 )
    goto LABEL_99;
  v18 = *(_BYTE *)(BugCheckParameter3 + 488) == 0;
  LODWORD(v90) = *(_DWORD *)(v19 + 80);
  if ( !v18 )
  {
    v48 = *(_DWORD *)(BugCheckParameter3 + 280) + 2;
    v49 = (*(_DWORD *)(BugCheckParameter3 + 32) >> 3) + 4095;
    *(_DWORD *)(BugCheckParameter3 + 200) = 3;
    *(_QWORD *)(v19 + 96) = (v49 >> 12) + v48;
    v50 = qword_140EFA778;
    PopWriteSecurePages(BugCheckParameter3);
    qword_140EFAA58 = qword_140EFA778 - v50;
    qword_140EFA930 = *(unsigned int *)(BugCheckParameter3 + 284);
  }
  *(_DWORD *)(BugCheckParameter3 + 200) = 4;
  *(_QWORD *)(BugCheckParameter3 + 112) = v23;
  v51 = RtlNumberOfClearBits(v23);
  v52 = qword_140EFA3C8;
  v53 = *(_DWORD *)(BugCheckParameter3 + 312);
  v54 = *(_QWORD *)(BugCheckParameter3 + 304);
  v55 = (v51 + *(_QWORD *)(BugCheckParameter3 + 104)) << 12;
  memset_0(qword_140EFA3C8, 0, 0x40u);
  v52[6] = 0;
  *(_QWORD *)v52 = v54;
  v52[2] = v53;
  *((_QWORD *)v52 + 2) = v55;
  qword_140EFA938 = 0;
  qword_140EFA940 = 0;
  *(_DWORD *)(BugCheckParameter3 + 360) = 0;
  *(_QWORD *)(BugCheckParameter3 + 376) = 0;
  v56 = qword_140EFA778;
  if ( v87 && *(_QWORD *)(*v28 + 128LL) )
    *(_BYTE *)(BugCheckParameter3 + 424) = 1;
  v57 = *(_DWORD *)(BugCheckParameter3 + 284)
      + ((unsigned int)((*(_DWORD *)(BugCheckParameter3 + 32) >> 3) + 4095) >> 12)
      + *(_DWORD *)(BugCheckParameter3 + 280)
      + 2;
  *(_QWORD *)(v19 + 104) = v57;
  *(_QWORD *)(BugCheckParameter3 + 408) = v57 << 12;
  *(_BYTE *)(BugCheckParameter3 + 3) = 1;
  v58 = __rdtsc();
  PopWriteHiberImage(BugCheckParameter3);
  _InterlockedIncrement((volatile signed __int32 *)(BugCheckParameter3 + 8));
  while ( *(_DWORD *)(BugCheckParameter3 + 8) != *(_DWORD *)(BugCheckParameter3 + 288) )
    _mm_pause();
  v59 = __rdtsc();
  v60 = 0;
  for ( qword_140EFAA60 = (((unsigned __int64)HIDWORD(v59) << 32) | (unsigned int)v59) - v58;
        v60 < *(_DWORD *)(BugCheckParameter3 + 288);
        *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + v64 + 56) = 0 )
  {
    for ( i = 0; i != 5; ++i )
    {
      v62 = 168LL * v60 + 88 + 8 * i;
      qword_140EFA9F8[i] += *(_QWORD *)(v62 + *(_QWORD *)(BugCheckParameter3 + 296));
      *(_QWORD *)(v62 + *(_QWORD *)(BugCheckParameter3 + 296)) = 0;
    }
    v63 = v60++;
    v64 = 168 * v63;
    qword_140EFA798 += *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + 168 * v63 + 40);
    *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + v64 + 40) = 0;
    qword_140EFA938 += *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + 168 * v63 + 56);
  }
  qword_140EFAA48 = qword_140EFA778 - v56;
  qword_140EFA948 = qword_140EFA968;
  qword_140EFA958 = (unsigned int)dword_140EFA970;
  qword_140EFA968 = 0;
  dword_140EFA970 = 0;
  *(_DWORD *)(BugCheckParameter3 + 200) = 5;
  *(_QWORD *)(BugCheckParameter3 + 112) = BugCheckParameter3 + 48;
  *(_QWORD *)(BugCheckParameter3 + 128) = 0;
  v65 = RtlNumberOfClearBits((PRTL_BITMAP)(BugCheckParameter3 + 48));
  v66 = qword_140EFA3C8;
  v67 = *(_DWORD *)(BugCheckParameter3 + 312);
  v68 = *(_QWORD *)(BugCheckParameter3 + 304);
  v69 = (unsigned __int64)v65 << 12;
  memset_0(qword_140EFA3C8, 0, 0x40u);
  v66[6] = 0;
  *(_QWORD *)v66 = v68;
  v66[2] = v67;
  *((_QWORD *)v66 + 2) = v69;
  *(_QWORD *)(v19 + 112) = (unsigned __int64)(*(_QWORD *)(BugCheckParameter3 + 408) + 4095LL) >> 12;
  v70 = qword_140EFA778;
  *(_DWORD *)(BugCheckParameter3 + 8) = 0;
  *(_QWORD *)(BugCheckParameter3 + 376) = 0;
  v71 = __rdtsc();
  PopWriteHiberImage(BugCheckParameter3);
  qword_140EFAA68 = __rdtsc() - v71;
  qword_140EFAA50 = qword_140EFA778 - v70;
  PopHiberWriteBootFreePageMap(BugCheckParameter3, v19);
  *(_DWORD *)(BugCheckParameter3 + 200) = 7;
  PopWriteChecksumPages(BugCheckParameter3);
  v72 = (unsigned int)v90;
  *(_DWORD *)(BugCheckParameter3 + 200) = 6;
  PopWriteImageHeader(BugCheckParameter3, v19, v72, v76);
  v47 = *(_DWORD *)(BugCheckParameter3 + 204);
  if ( v47 < 0 )
    goto LABEL_99;
  if ( dword_140EFA16C == dword_140EFA174 )
  {
    if ( (PopAwaymodeLock.RealtimePriorityFloor & 0x8000) == 0 )
      DbgUnLoadImageSymbols(0, -2);
    LOBYTE(v73) = 1;
    VslNotifyShutdown(v73);
  }
  if ( (PopAwaymodeLock.RealtimePriorityFloor & 0x1000) != 0 )
    HalReturnToFirmware(3);
  v47 = 0;
  if ( (PopSimulateHiberBugcheck & 0x10) != 0 )
  {
    v5 = 1073742484;
  }
  else
  {
LABEL_99:
    v5 = v47;
    KdPowerTransition(4);
    if ( v47 >= 0 )
    {
      if ( dword_140EFA16C == 5 )
      {
        PopNotifyShutdownListener();
        if ( HvlHypervisorConnected )
          HvlConfigureMemoryZeroingOnReset(0);
        PopSetMemoryOverwriteRequestAction();
      }
      v5 = v47;
    }
  }
  PopCheckpointSystemSleep(24);
  guard_dispatch_icall_no_overrides(v74);
  return v5;
}

```

## disassembly

```asm
0x140b8a950  push    rbp
0x140b8a952  push    rbx
0x140b8a953  push    rsi
0x140b8a954  push    rdi
0x140b8a955  push    r12
0x140b8a957  push    r13
0x140b8a959  push    r14
0x140b8a95b  push    r15
0x140b8a95d  lea     rbp, [rsp-28h]
0x140b8a962  sub     rsp, 128h
0x140b8a969  xor     eax, eax
0x140b8a96b  xor     edi, edi
0x140b8a96d  mov     [rbp+60h+var_50], rax
0x140b8a971  xorps   xmm0, xmm0
0x140b8a974  mov     [rsp+160h+var_110], rax
0x140b8a979  xorps   xmm1, xmm1
0x140b8a97c  mov     rax, [rcx+160h]
0x140b8a983  mov     r15, rcx
0x140b8a986  movups  [rbp+60h+var_60], xmm0
0x140b8a98a  mov     [rbp+60h+arg_10], edi
0x140b8a990  lea     r14d, [rdi+1]
0x140b8a994  movups  [rsp+160h+var_120], xmm1
0x140b8a999  mov     [rbp+60h+arg_8], edi
0x140b8a99c  mov     [rbp+60h+arg_18], rax
0x140b8a9a3  mov     rax, gs:20h
0x140b8a9ac  mov     ebx, [rax+24h]
0x140b8a9af  test    ebx, ebx
0x140b8a9b1  jnz     short loc_140B8A9BD
0x140b8a9b3  lea     ecx, [rdi+13h]
0x140b8a9b6  call    PopCheckpointSystemSleep
0x140b8a9bb  jmp     short loc_140B8A9FB
0x140b8a9bd  call    PopIsHvAssistedHibernation
0x140b8a9c2  test    al, al
0x140b8a9c4  jz      short loc_140B8A9FB
0x140b8a9c6  lock add [r15+10h], r14d
0x140b8a9cb  jmp     short loc_140B8A9CF
0x140b8a9cd  pause
0x140b8a9cf  mov     eax, [r15+10h]
0x140b8a9d3  test    eax, eax
0x140b8a9d5  jnz     short loc_140B8A9CD
0x140b8a9d7  cmp     byte ptr cs:PopAwaymodeLock.Padding+10h, dil
0x140b8a9de  jz      short loc_140B8A9EA
0x140b8a9e0  mov     ebx, 40000294h
0x140b8a9e5  jmp     loc_140B8B347
0x140b8a9ea  lock add [r15+14h], r14d
0x140b8a9ef  jmp     short loc_140B8A9F3
0x140b8a9f1  pause
0x140b8a9f3  mov     eax, [r15+14h]
0x140b8a9f7  test    eax, eax
0x140b8a9f9  jnz     short loc_140B8A9F1
0x140b8a9fb  cmp     ebx, [r15+120h]
0x140b8aa02  jb      short loc_140B8AA0B
0x140b8aa04  mov     ebx, edi
0x140b8aa06  jmp     loc_140B8B347
0x140b8aa0b  test    ebx, ebx
0x140b8aa0d  jnz     short loc_140B8AA2B
0x140b8aa0f  mov     cs:PopWatchdogTimerCount, edi
0x140b8aa15  call    KeDisableInterrupts
0x140b8aa1a  test    al, al
0x140b8aa1c  jz      short loc_140B8AA7C
0x140b8aa1e  mov     ecx, 0A1E00h; BugCheckParameter2
0x140b8aa23  call    _PopInternalError
0x140b8aa29  pause
0x140b8aa2b  mov     al, [r15+3]
0x140b8aa2f  test    al, al
0x140b8aa31  jz      short loc_140B8AA29
0x140b8aa33  mov     rdx, [r15+128h]
0x140b8aa3a  mov     r8b, r14b
0x140b8aa3d  imul    rbx, 0A8h
0x140b8aa44  mov     rcx, r15
0x140b8aa47  add     rdx, rbx
0x140b8aa4a  call    PopCompressHiberBlocks
0x140b8aa4f  lock add [r15+8], r14d
0x140b8aa54  jmp     short loc_140B8AA58
0x140b8aa56  pause
0x140b8aa58  mov     eax, [r15+8]
0x140b8aa5c  test    eax, eax
0x140b8aa5e  jnz     short loc_140B8AA56
0x140b8aa60  mov     rdx, [r15+128h]
0x140b8aa67  xor     r8d, r8d
0x140b8aa6a  add     rdx, rbx
0x140b8aa6d  mov     rcx, r15
0x140b8aa70  call    PopCompressHiberBlocks
0x140b8aa75  mov     ebx, eax
0x140b8aa77  jmp     loc_140B8B347
0x140b8aa7c  mov     eax, cs:PopSimulateHiberBugcheck
0x140b8aa82  test    al, al
0x140b8aa84  jns     short loc_140B8AA8C
0x140b8aa86  mov     [rbp+60h+arg_0], dil
0x140b8aa8a  jmp     short loc_140B8AA9F
0x140b8aa8c  lea     rcx, [rbp+60h+arg_10]
0x140b8aa93  call    IoDumpStackResumeCapable
0x140b8aa98  mov     [rbp+60h+arg_0], al
0x140b8aa9b  test    al, al
0x140b8aa9d  jnz     short loc_140B8AAAD
0x140b8aa9f  or      cs:dword_140EFA3F8, 4
0x140b8aaa6  mov     cs:byte_140EFA361, r14b
0x140b8aaad  call    cs:__imp_PshedArePluginsPresent
0x140b8aab4  nop     dword ptr [rax+rax+00h]
0x140b8aab9  test    eax, eax
0x140b8aabb  jz      short loc_140B8AACB
0x140b8aabd  or      cs:dword_140EFA3F8, 8
0x140b8aac4  mov     cs:byte_140EFA361, r14b
0x140b8aacb  mov     rax, cs:off_140E009E0
0x140b8aad2  call    _guard_dispatch_icall_no_overrides
0x140b8aad7  test    al, al
0x140b8aad9  jnz     short loc_140B8AAE9
0x140b8aadb  or      cs:dword_140EFA3F8, r14d
0x140b8aae2  mov     cs:byte_140EFA361, r14b
0x140b8aae9  cmp     cs:byte_140EFA361, dil
0x140b8aaf0  jz      short loc_140B8AB67
0x140b8aaf2  xorps   xmm0, xmm0
0x140b8aaf5  movups  [rsp+160h+var_130], xmm0
0x140b8aafa  call    KiGetCpuVendor
0x140b8aaff  cmp     eax, 2
0x140b8ab02  jnz     short loc_140B8AB67
0x140b8ab04  xor     eax, eax
0x140b8ab06  xor     ecx, ecx
0x140b8ab08  cpuid
0x140b8ab0a  mov     dword ptr [rsp+160h+var_130+4], ebx
0x140b8ab0e  cmp     eax, 7
0x140b8ab11  jb      short loc_140B8AB67
0x140b8ab13  xor     ecx, ecx
0x140b8ab15  mov     eax, 7
0x140b8ab1a  cpuid
0x140b8ab1c  mov     dword ptr [rsp+160h+var_130], eax
0x140b8ab20  mov     dword ptr [rsp+160h+var_130+4], ebx
0x140b8ab24  bt      ecx, 0Dh
0x140b8ab28  jnb     short loc_140B8AB67
0x140b8ab2a  mov     ecx, 982h
0x140b8ab2f  rdmsr
0x140b8ab31  shl     rdx, 20h
0x140b8ab35  or      rax, rdx
0x140b8ab38  test    al, 2
0x140b8ab3a  jz      short loc_140B8AB67
0x140b8ab3c  mov     rcx, 0F00000000h
0x140b8ab46  test    rcx, rax
0x140b8ab49  jbe     short loc_140B8AB67
0x140b8ab4b  mov     edx, 112h; BugCheckParameter1
0x140b8ab50  mov     [rsp+160h+BugCheckParameter4], rdi; BugCheckParameter4
0x140b8ab55  mov     r9, r15; BugCheckParameter3
0x140b8ab58  mov     r8d, 0Ah; BugCheckParameter2
0x140b8ab5e  lea     ecx, [rdx-72h]; BugCheckCode
0x140b8ab61  call    KeBugCheckEx
0x140b8ab67  cmp     cs:HvlHypervisorConnected, dil
0x140b8ab6e  lea     rax, [rbp+60h+var_60]
0x140b8ab72  mov     r13, [r15+0D8h]
0x140b8ab79  mov     [r15+0B0h], rax
0x140b8ab80  lea     rax, PoWakeState
0x140b8ab87  mov     [r15+0C0h], rax
0x140b8ab8e  mov     [r15+1], r14b
0x140b8ab92  jz      loc_140B8AD26
0x140b8ab98  xor     ecx, ecx
0x140b8ab9a  mov     cs:PopHibernateHvMinloopEnabled, r14d
0x140b8aba1  call    HvlDisableEnlightenment
0x140b8aba6  mov     rax, cs:off_140E00930
0x140b8abad  call    _guard_dispatch_icall_no_overrides
0x140b8abb2  call    PopIsHvAssistedHibernation
0x140b8abb7  test    al, al
0x140b8abb9  jz      loc_140B8AD0E
0x140b8abbf  lock add [r15+10h], r14d
0x140b8abc4  jmp     short loc_140B8ABC8
0x140b8abc6  pause
0x140b8abc8  mov     ecx, [r15+10h]
0x140b8abcc  mov     eax, cs:KeNumberProcessors_0
0x140b8abd2  cmp     ecx, eax
0x140b8abd4  jnz     short loc_140B8ABC6
0x140b8abd6  lea     rcx, [rbp+60h+var_B0]
0x140b8abda  mov     rax, cs:qword_140E2B428
0x140b8abe1  mov     qword ptr [rsp+160h+var_100], rax
0x140b8abe6  mov     rax, cs:qword_140E2B3C8
0x140b8abed  mov     qword ptr [rsp+160h+var_100+8], rax
0x140b8abf2  mov     rax, cs:qword_140E2B3D0
0x140b8abf9  movaps  xmm0, [rsp+160h+var_100]
0x140b8abfe  mov     qword ptr [rsp+160h+var_F0], rax
0x140b8ac03  mov     rax, cs:qword_140E2B3C0
0x140b8ac0a  mov     qword ptr [rsp+160h+var_F0+8], rax
0x140b8ac0f  mov     rax, cs:qword_140E2B3E0
0x140b8ac16  movaps  xmm1, [rsp+160h+var_F0]
0x140b8ac1b  mov     qword ptr [rbp+60h+var_E0], rax
0x140b8ac1f  mov     rax, cs:qword_140E2B3D8
0x140b8ac26  mov     qword ptr [rbp+60h+var_E0+8], rax
0x140b8ac2a  mov     rax, qword ptr cs:xmmword_140E2B408
0x140b8ac31  mov     qword ptr [rbp+60h+var_D0], rax
0x140b8ac35  mov     rax, qword ptr cs:xmmword_140E2B408+8
0x140b8ac3c  mov     qword ptr [rbp+60h+var_D0+8], rax
0x140b8ac40  mov     rax, qword ptr cs:xmmword_140E2B418
0x140b8ac47  mov     qword ptr [rbp+60h+var_C0], rax
0x140b8ac4b  mov     rax, qword ptr cs:xmmword_140E2B418+8
0x140b8ac52  movaps  [rbp+60h+var_B0], xmm0
0x140b8ac56  movaps  xmm0, [rbp+60h+var_E0]
0x140b8ac5a  mov     qword ptr [rbp+60h+var_C0+8], rax
0x140b8ac5e  movaps  [rbp+60h+var_A0], xmm1
0x140b8ac62  movaps  xmm1, [rbp+60h+var_D0]
0x140b8ac66  movaps  [rbp+60h+var_90], xmm0
0x140b8ac6a  movaps  xmm0, [rbp+60h+var_C0]
0x140b8ac6e  movaps  [rbp+60h+var_70], xmm0
0x140b8ac72  movaps  [rbp+60h+var_80], xmm1
0x140b8ac76  cmp     [r15+1E8h], dil
0x140b8ac7d  jz      short loc_140B8AC86
0x140b8ac7f  call    HvlPrepareForSecureHibernate
0x140b8ac84  jmp     short loc_140B8ACAC
0x140b8ac86  lea     rax, [r13+498h]
0x140b8ac8d  lea     r9, [r13+490h]
0x140b8ac94  mov     [rsp+160h+BugCheckParameter4], rax
0x140b8ac99  lea     r8, [r13+488h]
0x140b8aca0  lea     rdx, [r13+480h]
0x140b8aca7  call    HvlPrepareForHibernate
0x140b8acac  mov     ebx, eax
0x140b8acae  test    eax, eax
0x140b8acb0  jns     short loc_140B8ACE5
0x140b8acb2  mov     rcx, [r15+0B8h]
0x140b8acb9  xor     r8d, r8d
0x140b8acbc  mov     edx, 178h
0x140b8acc1  call    PopInternalAddToDumpFile
0x140b8acc6  mov     r9, [r15+0B8h]; BugCheckParameter3
0x140b8accd  mov     edx, 0Ch; BugCheckParameter1
0x140b8acd2  movsxd  r8, ebx; BugCheckParameter2
0x140b8acd5  mov     ecx, 0A0h; BugCheckCode
0x140b8acda  mov     [rsp+160h+BugCheckParameter4], rdi; BugCheckParameter4
0x140b8acdf  call    KeBugCheckEx
0x140b8ace5  mov     [r15+10h], edi
0x140b8ace9  lock add [r15+14h], r14d
0x140b8acee  jmp     short loc_140B8ACF2
0x140b8acf0  pause
0x140b8acf2  mov     ecx, [r15+14h]
0x140b8acf6  mov     eax, cs:KeNumberProcessors_0
0x140b8acfc  cmp     ecx, eax
0x140b8acfe  jnz     short loc_140B8ACF0
0x140b8ad00  mov     eax, cs:KeNumberProcessors_0
0x140b8ad06  mov     [r15+10h], eax
0x140b8ad0a  mov     [r15+14h], edi
0x140b8ad0e  mov     rcx, r15; MemoryMap
0x140b8ad11  cmp     [r15+1E8h], dil
0x140b8ad18  jz      short loc_140B8AD21
0x140b8ad1a  call    HvlDiscardSecurePagesFromHibernation
0x140b8ad1f  jmp     short loc_140B8AD26
0x140b8ad21  call    HvlDiscardPagesFromHibernation
0x140b8ad26  lea     rax, PopHiberNotificationDiscardMemoryCallback
0x140b8ad2d  mov     qword ptr [rsp+160h+var_120], r13
0x140b8ad32  mov     qword ptr [rsp+160h+var_120+8], rax
0x140b8ad37  lea     rdx, [rsp+160h+var_120]
0x140b8ad3c  lea     rax, PopHiberNotificationDiscardPhysicalMemoryCallback
0x140b8ad43  xor     ecx, ecx
0x140b8ad45  mov     [rsp+160h+var_110], rax
0x140b8ad4a  call    PopSstInvokeNotificationHandlers
0x140b8ad4f  add     [r13+0], r14d
0x140b8ad53  lea     rsi, [r15+40h]
0x140b8ad57  test    dword ptr [rsi], 0FFFFFFE0h
0x140b8ad5d  mov     ebx, edi
0x140b8ad5f  mov     rcx, [r15+48h]
0x140b8ad63  mov     rdx, [r15+38h]
0x140b8ad67  jbe     short loc_140B8AD81
0x140b8ad69  mov     eax, [rdx]
0x140b8ad6b  add     ebx, r14d
0x140b8ad6e  or      [rcx], eax
0x140b8ad70  lea     rdx, [rdx+4]
0x140b8ad74  mov     eax, [rsi]
0x140b8ad76  lea     rcx, [rcx+4]
0x140b8ad7a  shr     eax, 5
0x140b8ad7d  cmp     ebx, eax
0x140b8ad7f  jb      short loc_140B8AD69
0x140b8ad81  cmp     cs:byte_140EFA361, dil
0x140b8ad88  lea     rcx, [r15+30h]
0x140b8ad8c  jnz     short loc_140B8AD9F
0x140b8ad8e  mov     rdx, rcx
0x140b8ad91  xor     r8d, r8d
0x140b8ad94  mov     rcx, rsi
0x140b8ad97  call    RtlCopyBitMap
0x140b8ad9c  mov     rcx, rsi; BitMapHeader
0x140b8ad9f  call    RtlSetAllBits
0x140b8ada4  mov     dword ptr [r15+0C8h], 8
0x140b8adaf  lea     r12, [r15+0B8h]
0x140b8adb6  mov     cs:PopHibernateInProgress, r14d
0x140b8adbd  mov     rdx, [r12]
0x140b8adc1  call    IoGetDumpHiberRanges
0x140b8adc6  cmp     cs:byte_140EFA361, dil
0x140b8adcd  jnz     short loc_140B8ADD7
0x140b8adcf  mov     ecx, r14d
0x140b8add2  call    IoNotifyDump
0x140b8add7  rdtsc
0x140b8add9  mov     rcx, [r12]
0x140b8addd  shl     rdx, 20h
0x140b8ade1  or      rax, rdx
0x140b8ade4  mov     r14, rax
0x140b8ade7  call    IoInitializeDumpStack
0x140b8adec  lea     rdx, [rbp+60h+arg_8]
0x140b8adf0  movsxd  rdi, eax
0x140b8adf3  xor     ecx, ecx
0x140b8adf5  call    IoGetDumpStackTransferSizes
0x140b8adfa  mov     ecx, [rbp+60h+arg_8]
0x140b8adfd  mov     eax, 100000h
0x140b8ae02  cmp     ecx, eax
0x140b8ae04  jb      short loc_140B8AE0B
0x140b8ae06  mov     ecx, eax
0x140b8ae08  mov     [rbp+60h+arg_8], eax
0x140b8ae0b  mov     eax, [r15+1B8h]
0x140b8ae12  shr     ecx, 0Ch
0x140b8ae15  cmp     ecx, eax
0x140b8ae17  jz      short loc_140B8AE2C
  ... truncated ...
```
