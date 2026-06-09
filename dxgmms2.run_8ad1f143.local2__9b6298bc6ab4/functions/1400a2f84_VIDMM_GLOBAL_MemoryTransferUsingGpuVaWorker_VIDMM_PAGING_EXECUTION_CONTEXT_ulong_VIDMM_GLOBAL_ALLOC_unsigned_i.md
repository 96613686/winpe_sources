# VIDMM_GLOBAL::MemoryTransferUsingGpuVaWorker(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,VIDMM_TRANSFER_PARAMETER *,VIDMM_TRANSFER_PARAMETER *,unsigned __int64,_DXGK_TRANSFERFLAGS,unsigned __int64)

- ea: `0x1400a2f84`
- end: `0x1400a3843`
- name: `?MemoryTransferUsingGpuVaWorker@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@KPEAUVIDMM_GLOBAL_ALLOC@@_K2PEAUVIDMM_TRANSFER_PARAMETER@@32U_DXGK_TRANSFERFLAGS@@2@Z`
- size: `2239`
- prototype: `void __usercall(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, unsigned int@<r8d>, struct VIDMM_GLOBAL_ALLOC *@<r9>, unsigned __int64, unsigned __int64, struct VIDMM_TRANSFER_PARAMETER *, struct VIDMM_TRANSFER_PARAMETER *, unsigned __int64, struct _DXGK_TRANSFERFLAGS, unsigned __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400a6cc4`
- `0x1400a73fc`

## callees

- `0x140030f7c`
- `0x140031d4c`
- `0x1400396e0`
- `0x14003a468`
- `0x140042960`
- `0x140058680`
- `0x140058ac0`
- `0x1400986ac`
- `0x14009881c`
- `0x14009df00`
- `0x14009e2f0`
- `0x1400a14f8`
- `0x1400a2f84`
- `0x1400c29d8`
- `0x1400df9c0`
- `0x140103230`
- `0x14010aa7c`
- `0x1401122a4`
- `0x1401138a4`
- `0x14011540c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a3645`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a3645`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a30e5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3114`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a314d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3192`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a30e5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3114`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a314d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3192`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a30cb`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a30fa`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a3133`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a317c`

## pseudocode

```c
void __fastcall VIDMM_GLOBAL::MemoryTransferUsingGpuVaWorker(
        VIDMM_GLOBAL *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        unsigned int a3,
        struct VIDMM_GLOBAL_ALLOC *a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        struct VIDMM_TRANSFER_PARAMETER *a7,
        struct VIDMM_TRANSFER_PARAMETER *a8,
        unsigned __int64 a9,
        struct _DXGK_TRANSFERFLAGS a10,
        unsigned __int64 a11)
{
  struct VIDMM_TRANSFER_PARAMETER *v12; // r12
  struct VIDMM_GLOBAL_ALLOC *v13; // r11
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v14; // r10
  SIZE_T v15; // rsi
  SIZE_T v16; // rdi
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  unsigned int v19; // r9d
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned __int64 v22; // r15
  unsigned __int64 v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  _QWORD *v32; // rax
  unsigned __int64 v33; // r8
  unsigned __int64 v34; // rdx
  SIZE_T v35; // r15
  unsigned __int64 v36; // rbx
  unsigned __int64 v37; // r8
  unsigned int v38; // esi
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // rax
  struct VIDMM_TRANSFER_PARAMETER *v41; // r13
  unsigned int v42; // r12d
  const unsigned __int64 *v43; // rdx
  unsigned int v44; // ebx
  bool MustFlushTlbOnValidTransition; // al
  __int64 v46; // r9
  unsigned __int64 v47; // rax
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // r9
  __int64 v51; // r8
  __int64 v52; // r10
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v53; // rax
  LARGE_INTEGER *v54; // rsi
  struct VIDMM_MAPPED_VA_RANGE *v55; // rdi
  void *DriverAllocation; // rax
  ADAPTER_RENDER *v57; // rcx
  CVirtualAddressAllocator *v58; // rbx
  int v59; // eax
  __int64 v60; // rcx
  int v61; // ebx
  __int64 v62; // rdx
  __int64 v63; // rax
  bool v64; // zf
  __int64 v65; // rbx
  unsigned int CurrentProcessId; // eax
  int v67; // edx
  int v68; // r8d
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rbx
  SIZE_T v73; // rdi
  SIZE_T v74; // rsi
  __int64 v75; // rcx
  _QWORD *v76; // rdx
  struct VIDMM_MAPPED_VA_RANGE *v77; // r9
  char *v78; // rax
  __int64 v79; // rax
  __int64 v80; // rcx
  __int64 **v81; // rdx
  __int64 v82; // r8
  __int64 *v83; // rax
  unsigned __int64 v84; // rdx
  int v85; // [rsp+28h] [rbp-D8h]
  bool v86; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v87; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned __int8 v88[2]; // [rsp+62h] [rbp-9Eh] BYREF
  unsigned int v89; // [rsp+64h] [rbp-9Ch]
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v90; // [rsp+68h] [rbp-98h]
  struct VIDMM_GLOBAL_ALLOC *v91; // [rsp+70h] [rbp-90h]
  unsigned __int64 v92; // [rsp+78h] [rbp-88h]
  unsigned int v93[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v94; // [rsp+88h] [rbp-78h]
  unsigned int v95; // [rsp+8Ch] [rbp-74h]
  int v96; // [rsp+90h] [rbp-70h]
  SIZE_T v97; // [rsp+98h] [rbp-68h]
  SIZE_T v98; // [rsp+A0h] [rbp-60h]
  unsigned int v99[4]; // [rsp+A8h] [rbp-58h] BYREF
  int v100; // [rsp+B8h] [rbp-48h] BYREF
  int v101; // [rsp+BCh] [rbp-44h]
  unsigned __int64 v102; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v103; // [rsp+C8h] [rbp-38h]
  unsigned __int64 i; // [rsp+D0h] [rbp-30h]
  SIZE_T v105; // [rsp+D8h] [rbp-28h]
  struct VIDMM_MAPPED_VA_RANGE *v106; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v107; // [rsp+E8h] [rbp-18h]
  __int64 v108; // [rsp+F0h] [rbp-10h]
  SIZE_T v109; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v110; // [rsp+100h] [rbp+0h]
  struct VIDMM_TRANSFER_PARAMETER *v111; // [rsp+108h] [rbp+8h]
  struct VIDMM_TRANSFER_PARAMETER *v112; // [rsp+110h] [rbp+10h]
  __int64 v113; // [rsp+118h] [rbp+18h]
  struct _DXGKARG_BUILDPAGINGBUFFER v114; // [rsp+120h] [rbp+20h] BYREF
  __int128 v115; // [rsp+260h] [rbp+160h] BYREF
  SIZE_T v116; // [rsp+270h] [rbp+170h]

  v12 = a7;
  v13 = a4;
  v14 = a2;
  v107 = a11;
  v15 = *(_QWORD *)a8;
  v16 = *(_QWORD *)a7;
  v17 = *((unsigned int *)this + 9324);
  v18 = *((unsigned int *)this + 799);
  v86 = *(_QWORD *)a8 < *(_QWORD *)a7;
  v91 = a4;
  v89 = a3;
  v19 = a3;
  v90 = a2;
  v111 = a8;
  v112 = a7;
  v97 = v16;
  v98 = v15;
  if ( (_DWORD)v18 && (unsigned int)v17 >= (unsigned int)v18 )
    v17 = (unsigned int)v18;
  v20 = *((_QWORD *)a8 + 2);
  v21 = *((_QWORD *)a7 + 2);
  if ( v21 != v20 )
  {
    v103 = v17;
    v86 = 1;
LABEL_14:
    v23 = a9;
    v22 = a5;
    v92 = a9;
    goto LABEL_15;
  }
  if ( v16 == v15 )
    return;
  if ( v16 <= v15 )
    v18 = v15 - v16;
  else
    v18 = v16 - v15;
  if ( v18 <= v17 )
    v17 = v18;
  v103 = v17;
  if ( v15 < v16 )
    goto LABEL_14;
  v22 = a5;
  v23 = a9;
  v16 += a5;
  v15 += a5;
  v97 = v16;
  v98 = v15;
  v103 = v17;
  v18 = a5 + a9;
  v92 = a5 + a9;
  LOBYTE(v18) = v86;
LABEL_15:
  if ( v21 )
    v94 = *(unsigned __int16 *)(v21 + 64);
  else
    v94 = 0;
  if ( v20 )
  {
    v18 = *(unsigned __int16 *)(v20 + 64);
    v95 = *(unsigned __int16 *)(v20 + 64);
  }
  else
  {
    v95 = 0;
  }
  v88[0] = 0;
  v87 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v18, v21) + 24) = v91;
    WdLogGlobalForLineNumber = 15968;
    v26 = (_QWORD *)WdLogNewEntry5_WdTrace(v25, v24);
    v26[3] = v22;
    v26[4] = a6;
    v26[5] = v23;
    WdLogGlobalForLineNumber = 15970;
    v29 = (_QWORD *)WdLogNewEntry5_WdTrace(v28, v27);
    v29[3] = *((_QWORD *)a7 + 2);
    v29[4] = *(_QWORD *)a7;
    v29[5] = *((_QWORD *)a7 + 5);
    v30 = *((_QWORD *)a7 + 3);
    v29[6] = v30;
    WdLogGlobalForLineNumber = 15972;
    v32 = (_QWORD *)WdLogNewEntry5_WdTrace(v30, v31);
    v32[3] = *((_QWORD *)a8 + 2);
    v32[4] = *(_QWORD *)a8;
    v32[5] = *((_QWORD *)a8 + 5);
    v32[6] = *((_QWORD *)a8 + 3);
    WdLogGlobalForLineNumber = 15974;
    v13 = v91;
    v19 = v89;
    v14 = v90;
  }
  v33 = a6;
  v34 = v22;
  v110 = v22;
  if ( !v22 )
    return;
  v113 = v19;
  while ( 2 )
  {
    v35 = (unsigned int)v103;
    v36 = v92;
    if ( v34 <= v103 )
      v35 = (unsigned int)v34;
    if ( v86 )
    {
      v105 = v16;
      v109 = v15;
    }
    else
    {
      v105 = v16 - v35;
      v109 = v15 - v35;
      v36 = v92 - v35;
    }
    v37 = v92 + v33;
    v38 = v89;
    for ( i = v37; ; v37 = i )
    {
      v39 = *((_QWORD *)v12 + 5);
      *(_QWORD *)v99 = a5 >> 12;
      if ( v39 )
      {
        v40 = *((_QWORD *)v12 + 1);
        v101 = 0;
        v100 = a5 >> 12;
        if ( !v40 )
        {
          v102 = v39;
          goto LABEL_36;
        }
      }
      else
      {
        v100 = (unsigned int)a5 >> 12;
        v40 = *(_QWORD *)v12 + *((_QWORD *)v12 + 3);
      }
      v102 = v40 >> 12;
      v101 = 1;
LABEL_36:
      v106 = VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(
               (VIDMM_GLOBAL *)((char *)this + 36672),
               v14,
               v38,
               v35,
               v13,
               v37,
               v94,
               v36,
               (const struct _DXGK_ADL *)&v100,
               v88,
               v107);
      if ( v106 )
        break;
      VIDMM_GLOBAL::FlushPagingBufferInternal(this, v90, v38, 1, 0, 0);
      VIDMM_GLOBAL::FlushScratchGpuVaRanges(this, v90, v38);
      v14 = v90;
      v13 = v91;
    }
    v41 = v111;
    v42 = v99[0];
    while ( 1 )
    {
      v43 = (const unsigned __int64 *)*((_QWORD *)v41 + 5);
      *(_OWORD *)v99 = 0;
      if ( v43 )
      {
        VidMmiInitializeAdlForPfnArray((struct _DXGK_ADL *)v99, v43, v42, *((_QWORD *)v41 + 1));
      }
      else
      {
        v99[1] = 1;
        v99[0] = (unsigned int)a5 >> 12;
        *(_QWORD *)&v99[2] = (*(_QWORD *)v41 + *((_QWORD *)v41 + 3)) >> 12;
      }
      *(_QWORD *)v99 = VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(
                         (VIDMM_GLOBAL *)((char *)this + 36672),
                         v90,
                         v38,
                         v35,
                         v91,
                         i,
                         v95,
                         v36,
                         (const struct _DXGK_ADL *)v99,
                         &v87,
                         v107);
      if ( *(_QWORD *)v99 )
        break;
      VIDMM_GLOBAL::FlushPagingBufferInternal(this, v90, v38, 1, 0, 0);
      VIDMM_GLOBAL::FlushScratchGpuVaRanges(this, v90, v38);
    }
    v44 = v38;
    MustFlushTlbOnValidTransition = VIDMM_GLOBAL::MustFlushTlbOnValidTransition(this, v38);
    v12 = v112;
    if ( MustFlushTlbOnValidTransition )
    {
      v47 = *(_QWORD *)(v46 + 112);
      v48 = *(_QWORD *)(v46 + 104);
      v49 = *((_QWORD *)v106 + 14);
      v50 = *((_QWORD *)v106 + 13);
      if ( v49 <= v47 )
        v49 = v47;
      if ( v50 >= v48 )
        v50 = v48;
      CVirtualAddressAllocator::FlushGpuVaTlb(*((CVirtualAddressAllocator **)this + v38 + 4588), v90, v38, v50, v49);
    }
    memset(&v114, 0, sizeof(v114));
    LOBYTE(v51) = *((_BYTE *)this + 37231) != 0;
    v114.hSystemContext = (HANDLE)VidSchGetDriverPagingContext(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v38, v51);
    v53 = v90;
    v114.MultipassOffset = v52;
    if ( v90 )
    {
      v108 = *(_QWORD *)(*((_QWORD *)v90 + 3) + 8LL * v38);
      v53 = v90;
    }
    else
    {
      v108 = v52;
    }
    if ( *((_QWORD *)v12 + 5) == v52 )
    {
      v114.Transfer.Destination.SegmentAddress.LowPart = v52;
      if ( *((_QWORD *)v41 + 5) == v52 )
        v114.Transfer.Destination.SegmentAddress.LowPart = 2;
    }
    else
    {
      v114.Transfer.Destination.SegmentAddress.LowPart = 1;
    }
    v54 = *(LARGE_INTEGER **)v99;
    v55 = v106;
    while ( 1 )
    {
      VIDMM_GLOBAL::SetupForBuildPagingBufferIteration(this, v53, v44, v91, &v114);
      DriverAllocation = VidMmGetDriverAllocation(v91);
      v57 = (ADAPTER_RENDER *)*((_QWORD *)this + 2);
      v114.UpdateContextAllocation.ContextAllocation = (D3DGPU_VIRTUAL_ADDRESS)DriverAllocation;
      v114.Fill.FillSize = i;
      v114.Operation = DXGK_OPERATION_VIRTUAL_TRANSFER;
      v114.Transfer.TransferSize = v35;
      v114.MapApertureSegment.OffsetInPages = *((_QWORD *)v55 + 13);
      v114.Transfer.Source.SegmentAddress = v54[13];
      if ( (*((_DWORD *)ADAPTER_RENDER::GetGpuMmuCaps(v57, v44) + 5) & 1) != 0 )
      {
        v58 = (CVirtualAddressAllocator *)*((_QWORD *)this + v44 + 4588);
        v114.UnmapApertureSegment.DummyPage.QuadPart = (unsigned int)CVirtualAddressAllocator::GetVirtualAddressOfPageTable(
                                                                       v58,
                                                                       v89,
                                                                       *((_QWORD *)v55 + 13),
                                                                       v88[0] != 0);
        v114.TransferVirtual.DestinationPageTable = (unsigned int)CVirtualAddressAllocator::GetVirtualAddressOfPageTable(
                                                                    v58,
                                                                    v89,
                                                                    v54[13].QuadPart,
                                                                    v87 != 0);
        v114.Transfer.Destination.SegmentAddress.HighPart = v114.Transfer.Destination.SegmentAddress.HighPart
                                                          & 0xFFFFFFFC
                                                          | v88[0] & 1
                                                          | (2 * (v87 & 1));
      }
      VIDMM_GLOBAL::RecordVaPagingHistoryVirtualTransfer(this, &v114, v91);
      v59 = ADAPTER_RENDER::DdiBuildPagingBuffer(*((ADAPTER_RENDER **)this + 2), &v114);
      v60 = *((_QWORD *)this + 390);
      v61 = v59;
      v96 = v59;
      if ( v60 )
      {
        v62 = *((_QWORD *)v41 + 2);
        if ( !v62 || *(_DWORD *)(v62 + 100) != 1 )
          VIDMM_PROCESS::ChargeEvictionTransfer(
            *(VIDMM_PROCESS **)(v60 + 8),
            *(_DWORD *)(*((_QWORD *)this + 3) + 240LL),
            v35);
      }
      _InterlockedAdd64((volatile signed __int64 *)this + 501, v35);
      LOBYTE(v93[0]) = byte_140086201 & 0x10;
      if ( (byte_140086201 & 0x10) != 0 )
      {
        v63 = *((_QWORD *)v12 + 2);
        if ( !v63 || (v64 = *(_DWORD *)(v63 + 100) == 1, v93[0] = 2, !v64) )
          v93[0] = 1;
        v65 = *(_QWORD *)(v108 + 16);
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        McTemplateK0pppxxq_EtwWriteTransfer((_DWORD)v91, v67, v68, CurrentProcessId, (char)v91, v65, v105, v35, v93[0]);
        VidMmRecordTransfer((VIDMM_GLOBAL *)((char *)this + 3296), v35, v93[0]);
        v61 = v96;
      }
      v116 = 0;
      v69 = *((_QWORD *)v12 + 2);
      v115 = 0;
      if ( v69 )
        LODWORD(v115) = (unsigned __int16)(*(_WORD *)(v69 + 62) + 1);
      *((_QWORD *)&v115 + 1) = v105;
      v70 = *((_QWORD *)v41 + 2);
      DWORD1(v115) = v70 ? (unsigned __int16)(*(_WORD *)(v70 + 62) + 1) : 0;
      v116 = v109;
      v85 = v61;
      v44 = v89;
      *(_QWORD *)v93 = 0;
      VIDMM_GLOBAL::CompleteBuildPagingBufferIteration(
        this,
        v90,
        v89,
        v91,
        &v114,
        v85,
        0,
        (unsigned __int64 *)v93,
        &v115);
      if ( v96 >= 0 )
        break;
      v53 = v90;
    }
    v71 = *((_QWORD *)this + 4560);
    v72 = v113;
    v73 = v97;
    v74 = v98;
    v75 = *(_QWORD *)(v71 + 8 * v113) + 1112LL;
    v76 = *(_QWORD **)(*(_QWORD *)(v71 + 8 * v113) + 1120LL);
    if ( *v76 != v75 )
      goto LABEL_83;
    v77 = v106;
    v78 = (char *)v106 + 32;
    *((_QWORD *)v106 + 4) = v75;
    *((_QWORD *)v78 + 1) = v76;
    *v76 = v78;
    *(_QWORD *)(v75 + 8) = v78;
    v79 = *((_QWORD *)this + 4560);
    v80 = *(_QWORD *)(v79 + 8 * v72) + 1112LL;
    v81 = *(__int64 ***)(*(_QWORD *)(v79 + 8 * v72) + 1120LL);
    if ( *v81 != (__int64 *)v80 )
LABEL_83:
      __fastfail(3u);
    v82 = *(_QWORD *)v99;
    v13 = v91;
    v83 = (__int64 *)(*(_QWORD *)v99 + 32LL);
    *(_QWORD *)(*(_QWORD *)v99 + 40LL) = v81;
    *v83 = v80;
    *v81 = v83;
    v84 = v110;
    *(_QWORD *)(v80 + 8) = v83;
    v34 = v84 - v35;
    *((_QWORD *)v77 + 6) = *((_QWORD *)v13 + 11);
    *(_QWORD *)(v82 + 48) = *((_QWORD *)v13 + 11);
    v110 = v34;
    if ( v86 )
    {
      v16 = v35 + v73;
      v15 = v35 + v74;
      v92 += v35;
    }
    else
    {
      v16 = v73 - v35;
      v15 = v74 - v35;
      v92 -= v35;
    }
    v98 = v15;
    v97 = v16;
    if ( v34 )
    {
      v14 = v90;
      v33 = a6;
      continue;
    }
    break;
  }
}

```

## disassembly

```asm
0x1400a2f84  push    rbp
0x1400a2f86  push    rbx
0x1400a2f87  push    rsi
0x1400a2f88  push    rdi
0x1400a2f89  push    r12
0x1400a2f8b  push    r13
0x1400a2f8d  push    r14
0x1400a2f8f  push    r15
0x1400a2f91  lea     rbp, [rsp-188h]
0x1400a2f99  sub     rsp, 288h
0x1400a2fa0  mov     rax, cs:__security_cookie
0x1400a2fa7  xor     rax, rsp
0x1400a2faa  mov     [rbp+1C0h+var_48], rax
0x1400a2fb1  mov     r13, [rbp+1C0h+arg_38]
0x1400a2fb8  mov     r14, rcx
0x1400a2fbb  mov     r12, [rbp+1C0h+arg_30]
0x1400a2fc2  mov     r11, r9
0x1400a2fc5  mov     rax, [rbp+1C0h+arg_50]
0x1400a2fcc  mov     r10, rdx
0x1400a2fcf  mov     [rbp+1C0h+var_1D8], rax
0x1400a2fd3  mov     rsi, [r13+0]
0x1400a2fd7  mov     rdi, [r12]
0x1400a2fdb  mov     eax, [rcx+91B0h]
0x1400a2fe1  cmp     rsi, rdi
0x1400a2fe4  mov     ecx, [rcx+0C7Ch]
0x1400a2fea  setb    [rsp+2C0h+var_260]
0x1400a2fef  mov     [rsp+2C0h+var_250], r9
0x1400a2ff4  mov     [rsp+2C0h+var_25C], r8d
0x1400a2ff9  mov     r9d, r8d
0x1400a2ffc  mov     [rsp+2C0h+var_258], rdx
0x1400a3001  mov     [rbp+1C0h+var_1B8], r13
0x1400a3005  mov     [rbp+1C0h+var_1B0], r12
0x1400a3009  mov     [rbp+1C0h+var_228], rdi
0x1400a300d  mov     [rbp+1C0h+var_220], rsi
0x1400a3011  test    ecx, ecx
0x1400a3013  jz      short loc_1400A301A
0x1400a3015  cmp     eax, ecx
0x1400a3017  cmovnb  eax, ecx
0x1400a301a  mov     r8, [r13+10h]
0x1400a301e  mov     rdx, [r12+10h]
0x1400a3023  cmp     rdx, r8
0x1400a3026  jnz     short loc_1400A3084
0x1400a3028  cmp     rdi, rsi
0x1400a302b  jz      loc_1400A381F
0x1400a3031  jbe     short loc_1400A303B
0x1400a3033  mov     rcx, rdi
0x1400a3036  sub     rcx, rsi
0x1400a3039  jmp     short loc_1400A3041
0x1400a303b  mov     rcx, rsi
0x1400a303e  sub     rcx, rdi
0x1400a3041  cmp     rcx, rax
0x1400a3044  cmovbe  rax, rcx
0x1400a3048  mov     [rbp+1C0h+var_1F8], rax
0x1400a304c  cmp     rsi, rdi
0x1400a304f  jb      short loc_1400A308D
0x1400a3051  mov     r15, [rbp+1C0h+arg_20]
0x1400a3058  mov     rbx, [rbp+1C0h+arg_40]
0x1400a305f  add     rdi, r15
0x1400a3062  add     rsi, r15
0x1400a3065  mov     [rbp+1C0h+var_228], rdi
0x1400a3069  mov     [rbp+1C0h+var_220], rsi
0x1400a306d  mov     [rbp+1C0h+var_1F8], rax
0x1400a3071  lea     rcx, [r15+rbx]
0x1400a3075  mov     [rsp+2C0h+var_248], rcx
0x1400a307a  mov     cl, [rsp+2C0h+var_260]
0x1400a307e  mov     [rsp+2C0h+var_260], cl
0x1400a3082  jmp     short loc_1400A30A0
0x1400a3084  mov     [rbp+1C0h+var_1F8], rax
0x1400a3088  mov     [rsp+2C0h+var_260], 1
0x1400a308d  mov     rbx, [rbp+1C0h+arg_40]
0x1400a3094  mov     r15, [rbp+1C0h+arg_20]
0x1400a309b  mov     [rsp+2C0h+var_248], rbx
0x1400a30a0  test    rdx, rdx
0x1400a30a3  jz      short loc_1400A30AE
0x1400a30a5  movzx   eax, word ptr [rdx+40h]
0x1400a30a9  mov     [rbp+1C0h+var_238], eax
0x1400a30ac  jmp     short loc_1400A30B5
0x1400a30ae  mov     [rbp+1C0h+var_238], 0
0x1400a30b5  test    r8, r8
0x1400a30b8  jz      short loc_1400A30C4
0x1400a30ba  movzx   ecx, word ptr [r8+40h]
0x1400a30bf  mov     [rbp+1C0h+var_234], ecx
0x1400a30c2  jmp     short loc_1400A30CB
0x1400a30c4  mov     [rbp+1C0h+var_234], 0
0x1400a30cb  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a30d2  mov     [rsp+2C0h+var_25E], 0
0x1400a30d7  mov     [rsp+2C0h+var_25F], 0
0x1400a30dc  cmp     byte ptr [rax], 0
0x1400a30df  jz      loc_1400A31D7
0x1400a30e5  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a30ec  nop     dword ptr [rax+rax+00h]
0x1400a30f1  mov     r11, [rsp+2C0h+var_250]
0x1400a30f6  mov     [rax+18h], r11
0x1400a30fa  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a3101  mov     cs:WdLogGlobalForLineNumber, 3E60h
0x1400a310b  cmp     byte ptr [rax], 0
0x1400a310e  jz      loc_1400A31CD
0x1400a3114  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a311b  nop     dword ptr [rax+rax+00h]
0x1400a3120  mov     r8, [rbp+1C0h+arg_28]
0x1400a3127  mov     [rax+18h], r15
0x1400a312b  mov     [rax+20h], r8
0x1400a312f  mov     [rax+28h], rbx
0x1400a3133  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a313a  mov     cs:WdLogGlobalForLineNumber, 3E62h
0x1400a3144  cmp     byte ptr [rax], 0
0x1400a3147  jz      loc_1400A321C
0x1400a314d  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a3154  nop     dword ptr [rax+rax+00h]
0x1400a3159  mov     rcx, [r12+10h]
0x1400a315e  mov     [rax+18h], rcx
0x1400a3162  mov     rcx, [r12]
0x1400a3166  mov     [rax+20h], rcx
0x1400a316a  mov     rcx, [r12+28h]
0x1400a316f  mov     [rax+28h], rcx
0x1400a3173  mov     rcx, [r12+18h]
0x1400a3178  mov     [rax+30h], rcx
0x1400a317c  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a3183  mov     cs:WdLogGlobalForLineNumber, 3E64h
0x1400a318d  cmp     byte ptr [rax], 0
0x1400a3190  jz      short loc_1400A31C8
0x1400a3192  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a3199  nop     dword ptr [rax+rax+00h]
0x1400a319e  mov     rcx, [r13+10h]
0x1400a31a2  mov     [rax+18h], rcx
0x1400a31a6  mov     rcx, [r13+0]
0x1400a31aa  mov     [rax+20h], rcx
0x1400a31ae  mov     rcx, [r13+28h]
0x1400a31b2  mov     [rax+28h], rcx
0x1400a31b6  mov     rcx, [r13+18h]
0x1400a31ba  mov     [rax+30h], rcx
0x1400a31be  mov     cs:WdLogGlobalForLineNumber, 3E66h
0x1400a31c8  mov     r11, [rsp+2C0h+var_250]
0x1400a31cd  mov     r9d, [rsp+2C0h+var_25C]
0x1400a31d2  mov     r10, [rsp+2C0h+var_258]
0x1400a31d7  mov     r8, [rbp+1C0h+arg_28]
0x1400a31de  mov     rdx, r15
0x1400a31e1  mov     [rbp+1C0h+var_1C0], rdx
0x1400a31e5  test    r15, r15
0x1400a31e8  jz      loc_1400A381F
0x1400a31ee  mov     ebx, r9d
0x1400a31f1  mov     [rbp+1C0h+var_1A8], rbx
0x1400a31f5  mov     rcx, [rbp+1C0h+var_1F8]
0x1400a31f9  mov     rax, [rsp+2C0h+var_248]
0x1400a31fe  cmp     rdx, rcx
0x1400a3201  mov     r15d, ecx
0x1400a3204  mov     rbx, rax
0x1400a3207  cmovbe  r15d, edx
0x1400a320b  cmp     [rsp+2C0h+var_260], 0
0x1400a3210  jz      short loc_1400A322D
0x1400a3212  mov     [rbp+1C0h+var_1E8], rdi
0x1400a3216  mov     [rbp+1C0h+var_1C8], rsi
0x1400a321a  jmp     short loc_1400A3244
0x1400a321c  mov     r9d, [rsp+2C0h+var_25C]
0x1400a3221  mov     r10, [rsp+2C0h+var_258]
0x1400a3226  mov     r11, [rsp+2C0h+var_250]
0x1400a322b  jmp     short loc_1400A31DE
0x1400a322d  mov     rcx, rdi
0x1400a3230  sub     rcx, r15
0x1400a3233  mov     [rbp+1C0h+var_1E8], rcx
0x1400a3237  mov     rcx, rsi
0x1400a323a  sub     rcx, r15
0x1400a323d  mov     [rbp+1C0h+var_1C8], rcx
0x1400a3241  sub     rbx, r15
0x1400a3244  mov     r13, [rbp+1C0h+arg_20]
0x1400a324b  add     r8, rax
0x1400a324e  mov     esi, [rsp+2C0h+var_25C]
0x1400a3252  mov     [rbp+1C0h+var_1F0], r8
0x1400a3256  mov     rcx, [r12+28h]
0x1400a325b  mov     rdx, r13
0x1400a325e  shr     rdx, 0Ch
0x1400a3262  mov     qword ptr [rbp+1C0h+var_218], rdx
0x1400a3266  test    rcx, rcx
0x1400a3269  jz      short loc_1400A3285
0x1400a326b  mov     rax, [r12+8]
0x1400a3270  mov     [rbp+1C0h+var_204], 0
0x1400a3277  mov     [rbp+1C0h+var_208], edx
0x1400a327a  test    rax, rax
0x1400a327d  jnz     short loc_1400A3297
0x1400a327f  mov     [rbp+1C0h+var_200], rcx
0x1400a3283  jmp     short loc_1400A32A6
0x1400a3285  mov     eax, r13d
0x1400a3288  shr     eax, 0Ch
0x1400a328b  mov     [rbp+1C0h+var_208], eax
0x1400a328e  mov     rax, [r12+18h]
0x1400a3293  add     rax, [r12]
0x1400a3297  shr     rax, 0Ch
0x1400a329b  mov     [rbp+1C0h+var_200], rax
0x1400a329f  mov     [rbp+1C0h+var_204], 1
0x1400a32a6  mov     rax, [rbp+1C0h+var_1D8]
0x1400a32aa  lea     rcx, [r14+8F40h]; this
0x1400a32b1  mov     [rsp+2C0h+var_270], rax; unsigned __int64
0x1400a32b6  mov     r9, r15; unsigned __int64
0x1400a32b9  lea     rax, [rsp+2C0h+var_25E]
0x1400a32be  mov     rdx, r10; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a32c1  mov     [rsp+2C0h+var_278], rax; unsigned __int8 *
0x1400a32c6  lea     rax, [rbp+1C0h+var_208]
0x1400a32ca  mov     [rsp+2C0h+var_280], rax; struct _DXGK_ADL *
0x1400a32cf  mov     eax, [rbp+1C0h+var_238]
0x1400a32d2  mov     [rsp+2C0h+var_288], rbx; unsigned __int64
0x1400a32d7  mov     dword ptr [rsp+2C0h+var_290], eax; unsigned int
0x1400a32db  mov     qword ptr [rsp+2C0h+var_298], r8; unsigned __int64
0x1400a32e0  mov     r8d, esi; unsigned int
0x1400a32e3  mov     [rsp+2C0h+var_2A0], r11; struct VIDMM_GLOBAL_ALLOC *
0x1400a32e8  call    ?MapScratchAreaVaRange@VIDMM_PAGING_PROCESS@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_KPEAUVIDMM_GLOBAL_ALLOC@@1I1PEBU_DXGK_ADL@@PEAE1@Z; VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,unsigned __int64,VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,unsigned __int64,_DXGK_ADL const *,uchar *,unsigned __int64)
0x1400a32ed  mov     [rbp+1C0h+var_1E0], rax
0x1400a32f1  test    rax, rax
0x1400a32f4  jnz     short loc_1400A3334
0x1400a32f6  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a32fb  mov     r9b, 1; bool
0x1400a32fe  mov     [rsp+2C0h+var_298], al; bool
0x1400a3302  mov     r8d, esi; unsigned int
0x1400a3305  mov     rcx, r14; this
0x1400a3308  mov     byte ptr [rsp+2C0h+var_2A0], al; bool
0x1400a330c  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a3311  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a3316  mov     r8d, esi; unsigned int
0x1400a3319  mov     rcx, r14; this
0x1400a331c  call    ?FlushScratchGpuVaRanges@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::FlushScratchGpuVaRanges(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a3321  mov     r10, [rsp+2C0h+var_258]
0x1400a3326  mov     r11, [rsp+2C0h+var_250]
0x1400a332b  mov     r8, [rbp+1C0h+var_1F0]
0x1400a332f  jmp     loc_1400A3256
0x1400a3334  mov     r13, [rbp+1C0h+var_1B8]
0x1400a3338  mov     r12, qword ptr [rbp+1C0h+var_218]
0x1400a333c  mov     rdi, [rbp+1C0h+arg_20]
0x1400a3343  mov     rdx, [r13+28h]; unsigned __int64 *
0x1400a3347  xorps   xmm0, xmm0
0x1400a334a  movups  xmmword ptr [rbp+1C0h+var_218], xmm0
0x1400a334e  test    rdx, rdx
0x1400a3351  jz      short loc_1400A3365
0x1400a3353  mov     r9, [r13+8]; unsigned __int64
0x1400a3357  lea     rcx, [rbp+1C0h+var_218]; struct _DXGK_ADL *
0x1400a335b  mov     r8d, r12d; unsigned int
0x1400a335e  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x1400a3363  jmp     short loc_1400A3384
0x1400a3365  mov     eax, edi
0x1400a3367  mov     [rbp+1C0h+var_218+4], 1
0x1400a336e  shr     eax, 0Ch
0x1400a3371  mov     [rbp+1C0h+var_218], eax
0x1400a3374  mov     rax, [r13+18h]
0x1400a3378  add     rax, [r13+0]
0x1400a337c  shr     rax, 0Ch
0x1400a3380  mov     qword ptr [rbp+1C0h+var_218+8], rax
0x1400a3384  mov     rax, [rbp+1C0h+var_1D8]
0x1400a3388  lea     rcx, [r14+8F40h]; this
0x1400a338f  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a3394  mov     r9, r15; unsigned __int64
0x1400a3397  mov     [rsp+2C0h+var_270], rax; unsigned __int64
0x1400a339c  mov     r8d, esi; unsigned int
0x1400a339f  lea     rax, [rsp+2C0h+var_25F]
0x1400a33a4  mov     [rsp+2C0h+var_278], rax; unsigned __int8 *
0x1400a33a9  lea     rax, [rbp+1C0h+var_218]
0x1400a33ad  mov     [rsp+2C0h+var_280], rax; struct _DXGK_ADL *
0x1400a33b2  mov     eax, [rbp+1C0h+var_234]
0x1400a33b5  mov     [rsp+2C0h+var_288], rbx; unsigned __int64
0x1400a33ba  mov     dword ptr [rsp+2C0h+var_290], eax; unsigned int
0x1400a33be  mov     rax, [rbp+1C0h+var_1F0]
0x1400a33c2  mov     qword ptr [rsp+2C0h+var_298], rax; unsigned __int64
0x1400a33c7  mov     rax, [rsp+2C0h+var_250]
0x1400a33cc  mov     [rsp+2C0h+var_2A0], rax; struct VIDMM_GLOBAL_ALLOC *
0x1400a33d1  call    ?MapScratchAreaVaRange@VIDMM_PAGING_PROCESS@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_KPEAUVIDMM_GLOBAL_ALLOC@@1I1PEBU_DXGK_ADL@@PEAE1@Z; VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,unsigned __int64,VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,unsigned __int64,_DXGK_ADL const *,uchar *,unsigned __int64)
0x1400a33d6  mov     qword ptr [rbp+1C0h+var_218], rax
0x1400a33da  mov     r9, rax
0x1400a33dd  mov     rcx, r14; this
0x1400a33e0  test    rax, rax
0x1400a33e3  jnz     short loc_1400A3412
0x1400a33e5  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a33ea  mov     r9b, 1; bool
0x1400a33ed  mov     [rsp+2C0h+var_298], al; bool
0x1400a33f1  mov     r8d, esi; unsigned int
0x1400a33f4  mov     byte ptr [rsp+2C0h+var_2A0], al; bool
0x1400a33f8  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a33fd  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a3402  mov     r8d, esi; unsigned int
0x1400a3405  mov     rcx, r14; this
0x1400a3408  call    ?FlushScratchGpuVaRanges@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::FlushScratchGpuVaRanges(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a340d  jmp     loc_1400A3343
0x1400a3412  mov     ebx, esi
0x1400a3414  mov     edx, ebx; unsigned int
0x1400a3416  call    ?MustFlushTlbOnValidTransition@VIDMM_GLOBAL@@QEAA_NI@Z; VIDMM_GLOBAL::MustFlushTlbOnValidTransition(uint)
0x1400a341b  mov     r12, [rbp+1C0h+var_1B0]
0x1400a341f  test    al, al
0x1400a3421  jz      short loc_1400A345F
0x1400a3423  mov     rax, [r9+70h]
0x1400a3427  mov     rcx, [r9+68h]
0x1400a342b  mov     r8, [rbp+1C0h+var_1E0]
0x1400a342f  mov     rdx, [r8+70h]
0x1400a3433  mov     r9, [r8+68h]
0x1400a3437  cmp     rdx, rax
0x1400a343a  mov     r8d, ebx; unsigned int
0x1400a343d  cmovbe  rdx, rax
0x1400a3441  cmp     r9, rcx
0x1400a3444  mov     [rsp+2C0h+var_2A0], rdx; unsigned __int64
0x1400a3449  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a344e  cmovnb  r9, rcx; unsigned __int64
0x1400a3452  mov     rcx, [r14+rbx*8+8F60h]; this
0x1400a345a  call    ?FlushGpuVaTlb@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_K1@Z; CVirtualAddressAllocator::FlushGpuVaTlb(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,unsigned __int64,unsigned __int64)
0x1400a345f  xor     edx, edx; Val
0x1400a3461  lea     rcx, [rbp+1C0h+var_1A0]; void *
  ... truncated ...
```
