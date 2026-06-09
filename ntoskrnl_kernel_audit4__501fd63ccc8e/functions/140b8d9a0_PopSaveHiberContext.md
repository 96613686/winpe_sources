# PopSaveHiberContext

- ea: `0x140b8d9a0`
- end: `0x140b8e3e7`
- name: `PopSaveHiberContext`
- size: `2631`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1406ea980`

## callees

- `0x140369210`
- `0x140469c70`
- `0x1404c86b0`
- `0x1404dd3c4`
- `0x140529df0`
- `0x14052c620`
- `0x140532324`
- `0x140536c20`
- `0x140541bf0`
- `0x14058cf50`
- `0x1405c32c0`
- `0x1405c36a4`
- `0x1405ca668`
- `0x1405ca6d0`
- `0x1405ca9a0`
- `0x1405caaa4`
- `0x1405cea0c`
- `0x1405d199c`
- `0x1405d233c`
- `0x1405d2488`
- `0x1405d2574`
- `0x1406033d0`
- `0x140609224`
- `0x140609240`
- `0x1406eb0e0`
- `0x1406f6f80`
- `0x1406f7380`
- `0x140b8b124`
- `0x140b8b9ac`
- `0x140b8d910`
- `0x140b8d9a0`
- `0x140b8e4b4`
- `0x140b8e4f8`
- `0x140b9d0f4`
- `0x140b9d2cc`
- `0x140b9dc44`
- `0x140b9dcd8`
- `0x140b9ec0c`
- `0x140b9eca4`
- `0x140b9eea8`
- `0x140b9f288`
- `0x140ba82a0`

## import_xrefs

- `PSHED!PshedArePluginsPresent` at `0x140b8dafd`
- `PSHED!PshedArePluginsPresent` at `0x140b8dafd`

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
      if ( PoResumeFromHibernate )
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
    dword_140EFA2F8 |= 4u;
    byte_140EFA261 = 1;
    goto LABEL_27;
  }
  v87 = IoDumpStackResumeCapable(&v89);
  if ( !v87 )
    goto LABEL_26;
LABEL_27:
  if ( (unsigned int)PshedArePluginsPresent() )
  {
    dword_140EFA2F8 |= 8u;
    byte_140EFA261 = 1;
  }
  if ( !(unsigned __int8)guard_dispatch_icall_no_overrides(v7) )
  {
    dword_140EFA2F8 |= 1u;
    byte_140EFA261 = 1;
  }
  if ( byte_140EFA261 )
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
      *(_QWORD *)&v79 = qword_140E2B3A8;
      *((_QWORD *)&v79 + 1) = qword_140E2B348;
      *(_QWORD *)&v80 = qword_140E2B350;
      *((_QWORD *)&v80 + 1) = qword_140E2B340;
      *(_QWORD *)&v81 = qword_140E2B360;
      *((_QWORD *)&v81 + 1) = qword_140E2B358;
      v82 = xmmword_140E2B388;
      v83 = xmmword_140E2B398;
      v84[0] = v79;
      v84[1] = v80;
      v84[2] = v81;
      v84[4] = xmmword_140E2B398;
      v84[3] = xmmword_140E2B388;
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
  if ( !byte_140EFA261 )
  {
    RtlCopyBitMap(BugCheckParameter3 + 64, BugCheckParameter3 + 48, 0);
    v27 = (RTL_BITMAP *)(BugCheckParameter3 + 64);
  }
  RtlSetAllBits(v27);
  *(_DWORD *)(BugCheckParameter3 + 200) = 8;
  v28 = (_QWORD *)(BugCheckParameter3 + 184);
  PopHibernateInProgress = 1;
  IoGetDumpHiberRanges(v29, *(_QWORD *)(BugCheckParameter3 + 184));
  if ( !byte_140EFA261 )
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
  qword_140EFA3A8 += (((unsigned __int64)HIDWORD(v36) << 32) | (unsigned int)v36) - v30;
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
  v46 = qword_140EFA238;
  *v45 = qword_140EFA238;
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
    v50 = qword_140EFA398;
    PopWriteSecurePages(BugCheckParameter3);
    qword_140EFA678 = qword_140EFA398 - v50;
    qword_140EFA550 = *(unsigned int *)(BugCheckParameter3 + 284);
  }
  *(_DWORD *)(BugCheckParameter3 + 200) = 4;
  *(_QWORD *)(BugCheckParameter3 + 112) = v23;
  v51 = RtlNumberOfClearBits(v23);
  v52 = qword_140EFA2C8;
  v53 = *(_DWORD *)(BugCheckParameter3 + 312);
  v54 = *(_QWORD *)(BugCheckParameter3 + 304);
  v55 = (v51 + *(_QWORD *)(BugCheckParameter3 + 104)) << 12;
  memset_0(qword_140EFA2C8, 0, 0x40u);
  v52[6] = 0;
  *(_QWORD *)v52 = v54;
  v52[2] = v53;
  *((_QWORD *)v52 + 2) = v55;
  qword_140EFA558 = 0;
  qword_140EFA560 = 0;
  *(_DWORD *)(BugCheckParameter3 + 360) = 0;
  *(_QWORD *)(BugCheckParameter3 + 376) = 0;
  v56 = qword_140EFA398;
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
  for ( qword_140EFA680 = (((unsigned __int64)HIDWORD(v59) << 32) | (unsigned int)v59) - v58;
        v60 < *(_DWORD *)(BugCheckParameter3 + 288);
        *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + v64 + 56) = 0 )
  {
    for ( i = 0; i != 5; ++i )
    {
      v62 = 168LL * v60 + 88 + 8 * i;
      qword_140EFA618[i] += *(_QWORD *)(v62 + *(_QWORD *)(BugCheckParameter3 + 296));
      *(_QWORD *)(v62 + *(_QWORD *)(BugCheckParameter3 + 296)) = 0;
    }
    v63 = v60++;
    v64 = 168 * v63;
    qword_140EFA3B8 += *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + 168 * v63 + 40);
    *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + v64 + 40) = 0;
    qword_140EFA558 += *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 296) + 168 * v63 + 56);
  }
  qword_140EFA668 = qword_140EFA398 - v56;
  qword_140EFA568 = qword_140EFA588;
  qword_140EFA578 = (unsigned int)dword_140EFA590;
  qword_140EFA588 = 0;
  dword_140EFA590 = 0;
  *(_DWORD *)(BugCheckParameter3 + 200) = 5;
  *(_QWORD *)(BugCheckParameter3 + 112) = BugCheckParameter3 + 48;
  *(_QWORD *)(BugCheckParameter3 + 128) = 0;
  v65 = RtlNumberOfClearBits((PRTL_BITMAP)(BugCheckParameter3 + 48));
  v66 = qword_140EFA2C8;
  v67 = *(_DWORD *)(BugCheckParameter3 + 312);
  v68 = *(_QWORD *)(BugCheckParameter3 + 304);
  v69 = (unsigned __int64)v65 << 12;
  memset_0(qword_140EFA2C8, 0, 0x40u);
  v66[6] = 0;
  *(_QWORD *)v66 = v68;
  v66[2] = v67;
  *((_QWORD *)v66 + 2) = v69;
  *(_QWORD *)(v19 + 112) = (unsigned __int64)(*(_QWORD *)(BugCheckParameter3 + 408) + 4095LL) >> 12;
  v70 = qword_140EFA398;
  *(_DWORD *)(BugCheckParameter3 + 8) = 0;
  *(_QWORD *)(BugCheckParameter3 + 376) = 0;
  v71 = __rdtsc();
  PopWriteHiberImage(BugCheckParameter3);
  qword_140EFA688 = __rdtsc() - v71;
  qword_140EFA670 = qword_140EFA398 - v70;
  PopHiberWriteBootFreePageMap(BugCheckParameter3, v19);
  *(_DWORD *)(BugCheckParameter3 + 200) = 7;
  PopWriteChecksumPages(BugCheckParameter3);
  v72 = (unsigned int)v90;
  *(_DWORD *)(BugCheckParameter3 + 200) = 6;
  PopWriteImageHeader(BugCheckParameter3, v19, v72, v76);
  v47 = *(_DWORD *)(BugCheckParameter3 + 204);
  if ( v47 < 0 )
    goto LABEL_99;
  if ( dword_140EF9DAC == dword_140EF9DB4 )
  {
    if ( (PopSimulate & 0x8000) == 0 )
      DbgUnLoadImageSymbols(0, -2);
    LOBYTE(v73) = 1;
    VslNotifyShutdown(v73);
  }
  if ( (PopSimulate & 0x1000) != 0 )
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
      if ( dword_140EF9DAC == 5 )
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
0x140b8d9a0  push    rbp
0x140b8d9a2  push    rbx
0x140b8d9a3  push    rsi
0x140b8d9a4  push    rdi
0x140b8d9a5  push    r12
0x140b8d9a7  push    r13
0x140b8d9a9  push    r14
0x140b8d9ab  push    r15
0x140b8d9ad  lea     rbp, [rsp-28h]
0x140b8d9b2  sub     rsp, 128h
0x140b8d9b9  xor     eax, eax
0x140b8d9bb  xor     edi, edi
0x140b8d9bd  mov     [rbp+60h+var_50], rax
0x140b8d9c1  xorps   xmm0, xmm0
0x140b8d9c4  mov     [rsp+160h+var_110], rax
0x140b8d9c9  xorps   xmm1, xmm1
0x140b8d9cc  mov     rax, [rcx+160h]
0x140b8d9d3  mov     r15, rcx
0x140b8d9d6  movups  [rbp+60h+var_60], xmm0
0x140b8d9da  mov     [rbp+60h+arg_10], edi
0x140b8d9e0  lea     r14d, [rdi+1]
0x140b8d9e4  movups  [rsp+160h+var_120], xmm1
0x140b8d9e9  mov     [rbp+60h+arg_8], edi
0x140b8d9ec  mov     [rbp+60h+arg_18], rax
0x140b8d9f3  mov     rax, gs:20h
0x140b8d9fc  mov     ebx, [rax+24h]
0x140b8d9ff  test    ebx, ebx
0x140b8da01  jnz     short loc_140B8DA0D
0x140b8da03  lea     ecx, [rdi+13h]
0x140b8da06  call    PopCheckpointSystemSleep
0x140b8da0b  jmp     short loc_140B8DA4B
0x140b8da0d  call    PopIsHvAssistedHibernation
0x140b8da12  test    al, al
0x140b8da14  jz      short loc_140B8DA4B
0x140b8da16  lock add [r15+10h], r14d
0x140b8da1b  jmp     short loc_140B8DA1F
0x140b8da1d  pause
0x140b8da1f  mov     eax, [r15+10h]
0x140b8da23  test    eax, eax
0x140b8da25  jnz     short loc_140B8DA1D
0x140b8da27  cmp     cs:PoResumeFromHibernate, dil
0x140b8da2e  jz      short loc_140B8DA3A
0x140b8da30  mov     ebx, 40000294h
0x140b8da35  jmp     loc_140B8E397
0x140b8da3a  lock add [r15+14h], r14d
0x140b8da3f  jmp     short loc_140B8DA43
0x140b8da41  pause
0x140b8da43  mov     eax, [r15+14h]
0x140b8da47  test    eax, eax
0x140b8da49  jnz     short loc_140B8DA41
0x140b8da4b  cmp     ebx, [r15+120h]
0x140b8da52  jb      short loc_140B8DA5B
0x140b8da54  mov     ebx, edi
0x140b8da56  jmp     loc_140B8E397
0x140b8da5b  test    ebx, ebx
0x140b8da5d  jnz     short loc_140B8DA7B
0x140b8da5f  mov     cs:PopWatchdogTimerCount, edi
0x140b8da65  call    KeDisableInterrupts
0x140b8da6a  test    al, al
0x140b8da6c  jz      short loc_140B8DACC
0x140b8da6e  mov     ecx, 0A1E00h; BugCheckParameter2
0x140b8da73  call    _PopInternalError
0x140b8da79  pause
0x140b8da7b  mov     al, [r15+3]
0x140b8da7f  test    al, al
0x140b8da81  jz      short loc_140B8DA79
0x140b8da83  mov     rdx, [r15+128h]
0x140b8da8a  mov     r8b, r14b
0x140b8da8d  imul    rbx, 0A8h
0x140b8da94  mov     rcx, r15
0x140b8da97  add     rdx, rbx
0x140b8da9a  call    PopCompressHiberBlocks
0x140b8da9f  lock add [r15+8], r14d
0x140b8daa4  jmp     short loc_140B8DAA8
0x140b8daa6  pause
0x140b8daa8  mov     eax, [r15+8]
0x140b8daac  test    eax, eax
0x140b8daae  jnz     short loc_140B8DAA6
0x140b8dab0  mov     rdx, [r15+128h]
0x140b8dab7  xor     r8d, r8d
0x140b8daba  add     rdx, rbx
0x140b8dabd  mov     rcx, r15
0x140b8dac0  call    PopCompressHiberBlocks
0x140b8dac5  mov     ebx, eax
0x140b8dac7  jmp     loc_140B8E397
0x140b8dacc  mov     eax, cs:PopSimulateHiberBugcheck
0x140b8dad2  test    al, al
0x140b8dad4  jns     short loc_140B8DADC
0x140b8dad6  mov     [rbp+60h+arg_0], dil
0x140b8dada  jmp     short loc_140B8DAEF
0x140b8dadc  lea     rcx, [rbp+60h+arg_10]
0x140b8dae3  call    IoDumpStackResumeCapable
0x140b8dae8  mov     [rbp+60h+arg_0], al
0x140b8daeb  test    al, al
0x140b8daed  jnz     short loc_140B8DAFD
0x140b8daef  or      cs:dword_140EFA2F8, 4
0x140b8daf6  mov     cs:byte_140EFA261, r14b
0x140b8dafd  call    cs:__imp_PshedArePluginsPresent
0x140b8db04  nop     dword ptr [rax+rax+00h]
0x140b8db09  test    eax, eax
0x140b8db0b  jz      short loc_140B8DB1B
0x140b8db0d  or      cs:dword_140EFA2F8, 8
0x140b8db14  mov     cs:byte_140EFA261, r14b
0x140b8db1b  mov     rax, cs:off_140E00AB0
0x140b8db22  call    _guard_dispatch_icall_no_overrides
0x140b8db27  test    al, al
0x140b8db29  jnz     short loc_140B8DB39
0x140b8db2b  or      cs:dword_140EFA2F8, r14d
0x140b8db32  mov     cs:byte_140EFA261, r14b
0x140b8db39  cmp     cs:byte_140EFA261, dil
0x140b8db40  jz      short loc_140B8DBB7
0x140b8db42  xorps   xmm0, xmm0
0x140b8db45  movups  [rsp+160h+var_130], xmm0
0x140b8db4a  call    KiGetCpuVendor
0x140b8db4f  cmp     eax, 2
0x140b8db52  jnz     short loc_140B8DBB7
0x140b8db54  xor     eax, eax
0x140b8db56  xor     ecx, ecx
0x140b8db58  cpuid
0x140b8db5a  mov     dword ptr [rsp+160h+var_130+4], ebx
0x140b8db5e  cmp     eax, 7
0x140b8db61  jb      short loc_140B8DBB7
0x140b8db63  xor     ecx, ecx
0x140b8db65  mov     eax, 7
0x140b8db6a  cpuid
0x140b8db6c  mov     dword ptr [rsp+160h+var_130], eax
0x140b8db70  mov     dword ptr [rsp+160h+var_130+4], ebx
0x140b8db74  bt      ecx, 0Dh
0x140b8db78  jnb     short loc_140B8DBB7
0x140b8db7a  mov     ecx, 982h
0x140b8db7f  rdmsr
0x140b8db81  shl     rdx, 20h
0x140b8db85  or      rax, rdx
0x140b8db88  test    al, 2
0x140b8db8a  jz      short loc_140B8DBB7
0x140b8db8c  mov     rcx, 0F00000000h
0x140b8db96  test    rcx, rax
0x140b8db99  jbe     short loc_140B8DBB7
0x140b8db9b  mov     edx, 112h; BugCheckParameter1
0x140b8dba0  mov     [rsp+160h+BugCheckParameter4], rdi; BugCheckParameter4
0x140b8dba5  mov     r9, r15; BugCheckParameter3
0x140b8dba8  mov     r8d, 0Ah; BugCheckParameter2
0x140b8dbae  lea     ecx, [rdx-72h]; BugCheckCode
0x140b8dbb1  call    KeBugCheckEx
0x140b8dbb7  cmp     cs:HvlHypervisorConnected, dil
0x140b8dbbe  lea     rax, [rbp+60h+var_60]
0x140b8dbc2  mov     r13, [r15+0D8h]
0x140b8dbc9  mov     [r15+0B0h], rax
0x140b8dbd0  lea     rax, PoWakeState
0x140b8dbd7  mov     [r15+0C0h], rax
0x140b8dbde  mov     [r15+1], r14b
0x140b8dbe2  jz      loc_140B8DD76
0x140b8dbe8  xor     ecx, ecx
0x140b8dbea  mov     cs:PopHibernateHvMinloopEnabled, r14d
0x140b8dbf1  call    HvlDisableEnlightenment
0x140b8dbf6  mov     rax, cs:off_140E00A00
0x140b8dbfd  call    _guard_dispatch_icall_no_overrides
0x140b8dc02  call    PopIsHvAssistedHibernation
0x140b8dc07  test    al, al
0x140b8dc09  jz      loc_140B8DD5E
0x140b8dc0f  lock add [r15+10h], r14d
0x140b8dc14  jmp     short loc_140B8DC18
0x140b8dc16  pause
0x140b8dc18  mov     ecx, [r15+10h]
0x140b8dc1c  mov     eax, cs:KeNumberProcessors_0
0x140b8dc22  cmp     ecx, eax
0x140b8dc24  jnz     short loc_140B8DC16
0x140b8dc26  lea     rcx, [rbp+60h+var_B0]
0x140b8dc2a  mov     rax, cs:qword_140E2B3A8
0x140b8dc31  mov     qword ptr [rsp+160h+var_100], rax
0x140b8dc36  mov     rax, cs:qword_140E2B348
0x140b8dc3d  mov     qword ptr [rsp+160h+var_100+8], rax
0x140b8dc42  mov     rax, cs:qword_140E2B350
0x140b8dc49  movaps  xmm0, [rsp+160h+var_100]
0x140b8dc4e  mov     qword ptr [rsp+160h+var_F0], rax
0x140b8dc53  mov     rax, cs:qword_140E2B340
0x140b8dc5a  mov     qword ptr [rsp+160h+var_F0+8], rax
0x140b8dc5f  mov     rax, cs:qword_140E2B360
0x140b8dc66  movaps  xmm1, [rsp+160h+var_F0]
0x140b8dc6b  mov     qword ptr [rbp+60h+var_E0], rax
0x140b8dc6f  mov     rax, cs:qword_140E2B358
0x140b8dc76  mov     qword ptr [rbp+60h+var_E0+8], rax
0x140b8dc7a  mov     rax, qword ptr cs:xmmword_140E2B388
0x140b8dc81  mov     qword ptr [rbp+60h+var_D0], rax
0x140b8dc85  mov     rax, qword ptr cs:xmmword_140E2B388+8
0x140b8dc8c  mov     qword ptr [rbp+60h+var_D0+8], rax
0x140b8dc90  mov     rax, qword ptr cs:xmmword_140E2B398
0x140b8dc97  mov     qword ptr [rbp+60h+var_C0], rax
0x140b8dc9b  mov     rax, qword ptr cs:xmmword_140E2B398+8
0x140b8dca2  movaps  [rbp+60h+var_B0], xmm0
0x140b8dca6  movaps  xmm0, [rbp+60h+var_E0]
0x140b8dcaa  mov     qword ptr [rbp+60h+var_C0+8], rax
0x140b8dcae  movaps  [rbp+60h+var_A0], xmm1
0x140b8dcb2  movaps  xmm1, [rbp+60h+var_D0]
0x140b8dcb6  movaps  [rbp+60h+var_90], xmm0
0x140b8dcba  movaps  xmm0, [rbp+60h+var_C0]
0x140b8dcbe  movaps  [rbp+60h+var_70], xmm0
0x140b8dcc2  movaps  [rbp+60h+var_80], xmm1
0x140b8dcc6  cmp     [r15+1E8h], dil
0x140b8dccd  jz      short loc_140B8DCD6
0x140b8dccf  call    HvlPrepareForSecureHibernate
0x140b8dcd4  jmp     short loc_140B8DCFC
0x140b8dcd6  lea     rax, [r13+498h]
0x140b8dcdd  lea     r9, [r13+490h]
0x140b8dce4  mov     [rsp+160h+BugCheckParameter4], rax
0x140b8dce9  lea     r8, [r13+488h]
0x140b8dcf0  lea     rdx, [r13+480h]
0x140b8dcf7  call    HvlPrepareForHibernate
0x140b8dcfc  mov     ebx, eax
0x140b8dcfe  test    eax, eax
0x140b8dd00  jns     short loc_140B8DD35
0x140b8dd02  mov     rcx, [r15+0B8h]
0x140b8dd09  xor     r8d, r8d
0x140b8dd0c  mov     edx, 178h
0x140b8dd11  call    PopInternalAddToDumpFile
0x140b8dd16  mov     r9, [r15+0B8h]; BugCheckParameter3
0x140b8dd1d  mov     edx, 0Ch; BugCheckParameter1
0x140b8dd22  movsxd  r8, ebx; BugCheckParameter2
0x140b8dd25  mov     ecx, 0A0h; BugCheckCode
0x140b8dd2a  mov     [rsp+160h+BugCheckParameter4], rdi; BugCheckParameter4
0x140b8dd2f  call    KeBugCheckEx
0x140b8dd35  mov     [r15+10h], edi
0x140b8dd39  lock add [r15+14h], r14d
0x140b8dd3e  jmp     short loc_140B8DD42
0x140b8dd40  pause
0x140b8dd42  mov     ecx, [r15+14h]
0x140b8dd46  mov     eax, cs:KeNumberProcessors_0
0x140b8dd4c  cmp     ecx, eax
0x140b8dd4e  jnz     short loc_140B8DD40
0x140b8dd50  mov     eax, cs:KeNumberProcessors_0
0x140b8dd56  mov     [r15+10h], eax
0x140b8dd5a  mov     [r15+14h], edi
0x140b8dd5e  mov     rcx, r15; MemoryMap
0x140b8dd61  cmp     [r15+1E8h], dil
0x140b8dd68  jz      short loc_140B8DD71
0x140b8dd6a  call    HvlDiscardSecurePagesFromHibernation
0x140b8dd6f  jmp     short loc_140B8DD76
0x140b8dd71  call    HvlDiscardPagesFromHibernation
0x140b8dd76  lea     rax, PopHiberNotificationDiscardMemoryCallback
0x140b8dd7d  mov     qword ptr [rsp+160h+var_120], r13
0x140b8dd82  mov     qword ptr [rsp+160h+var_120+8], rax
0x140b8dd87  lea     rdx, [rsp+160h+var_120]
0x140b8dd8c  lea     rax, PopHiberNotificationDiscardPhysicalMemoryCallback
0x140b8dd93  xor     ecx, ecx
0x140b8dd95  mov     [rsp+160h+var_110], rax
0x140b8dd9a  call    PopSstInvokeNotificationHandlers
0x140b8dd9f  add     [r13+0], r14d
0x140b8dda3  lea     rsi, [r15+40h]
0x140b8dda7  test    dword ptr [rsi], 0FFFFFFE0h
0x140b8ddad  mov     ebx, edi
0x140b8ddaf  mov     rcx, [r15+48h]
0x140b8ddb3  mov     rdx, [r15+38h]
0x140b8ddb7  jbe     short loc_140B8DDD1
0x140b8ddb9  mov     eax, [rdx]
0x140b8ddbb  add     ebx, r14d
0x140b8ddbe  or      [rcx], eax
0x140b8ddc0  lea     rdx, [rdx+4]
0x140b8ddc4  mov     eax, [rsi]
0x140b8ddc6  lea     rcx, [rcx+4]
0x140b8ddca  shr     eax, 5
0x140b8ddcd  cmp     ebx, eax
0x140b8ddcf  jb      short loc_140B8DDB9
0x140b8ddd1  cmp     cs:byte_140EFA261, dil
0x140b8ddd8  lea     rcx, [r15+30h]
0x140b8dddc  jnz     short loc_140B8DDEF
0x140b8ddde  mov     rdx, rcx
0x140b8dde1  xor     r8d, r8d
0x140b8dde4  mov     rcx, rsi
0x140b8dde7  call    RtlCopyBitMap
0x140b8ddec  mov     rcx, rsi; BitMapHeader
0x140b8ddef  call    RtlSetAllBits
0x140b8ddf4  mov     dword ptr [r15+0C8h], 8
0x140b8ddff  lea     r12, [r15+0B8h]
0x140b8de06  mov     cs:PopHibernateInProgress, r14d
0x140b8de0d  mov     rdx, [r12]
0x140b8de11  call    IoGetDumpHiberRanges
0x140b8de16  cmp     cs:byte_140EFA261, dil
0x140b8de1d  jnz     short loc_140B8DE27
0x140b8de1f  mov     ecx, r14d
0x140b8de22  call    IoNotifyDump
0x140b8de27  rdtsc
0x140b8de29  mov     rcx, [r12]
0x140b8de2d  shl     rdx, 20h
0x140b8de31  or      rax, rdx
0x140b8de34  mov     r14, rax
0x140b8de37  call    IoInitializeDumpStack
0x140b8de3c  lea     rdx, [rbp+60h+arg_8]
0x140b8de40  movsxd  rdi, eax
0x140b8de43  xor     ecx, ecx
0x140b8de45  call    IoGetDumpStackTransferSizes
0x140b8de4a  mov     ecx, [rbp+60h+arg_8]
0x140b8de4d  mov     eax, 100000h
0x140b8de52  cmp     ecx, eax
0x140b8de54  jb      short loc_140B8DE5B
0x140b8de56  mov     ecx, eax
0x140b8de58  mov     [rbp+60h+arg_8], eax
0x140b8de5b  mov     eax, [r15+1B8h]
0x140b8de62  shr     ecx, 0Ch
0x140b8de65  cmp     ecx, eax
0x140b8de67  jz      short loc_140B8DE7C
  ... truncated ...
```
