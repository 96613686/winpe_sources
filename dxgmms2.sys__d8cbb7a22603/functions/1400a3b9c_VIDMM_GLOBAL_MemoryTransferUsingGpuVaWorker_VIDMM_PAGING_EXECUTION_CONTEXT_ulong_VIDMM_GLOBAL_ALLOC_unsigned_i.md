# VIDMM_GLOBAL::MemoryTransferUsingGpuVaWorker(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,VIDMM_TRANSFER_PARAMETER *,VIDMM_TRANSFER_PARAMETER *,unsigned __int64,_DXGK_TRANSFERFLAGS,unsigned __int64)

- ea: `0x1400a3b9c`
- end: `0x1400a445b`
- name: `?MemoryTransferUsingGpuVaWorker@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@KPEAUVIDMM_GLOBAL_ALLOC@@_K2PEAUVIDMM_TRANSFER_PARAMETER@@32U_DXGK_TRANSFERFLAGS@@2@Z`
- size: `2239`
- prototype: `void __usercall(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, unsigned int@<r8d>, struct VIDMM_GLOBAL_ALLOC *@<r9>, unsigned __int64, unsigned __int64, struct VIDMM_TRANSFER_PARAMETER *, struct VIDMM_TRANSFER_PARAMETER *, unsigned __int64, struct _DXGK_TRANSFERFLAGS, unsigned __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400a7528`
- `0x1400a7c60`

## callees

- `0x14002eb5c`
- `0x14002fbe8`
- `0x140038740`
- `0x1400393e8`
- `0x140042ad0`
- `0x140058f50`
- `0x140059380`
- `0x140097be8`
- `0x140097fd8`
- `0x14009c1f4`
- `0x14009c364`
- `0x1400a2698`
- `0x1400a3b9c`
- `0x1400c6b84`
- `0x1400e7e20`
- `0x14010b070`
- `0x14010e82c`
- `0x140114ee4`
- `0x140116694`
- `0x140118fcc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a425d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400a425d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3cfd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3d2c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3d65`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3daa`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3cfd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3d2c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3d65`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a3daa`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a3ce3`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a3d12`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a3d4b`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a3d94`

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
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rcx
  _QWORD *v29; // rax
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // rdx
  SIZE_T v32; // r15
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // r8
  unsigned int v35; // esi
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rax
  struct VIDMM_TRANSFER_PARAMETER *v38; // r13
  unsigned int v39; // r12d
  const unsigned __int64 *v40; // rdx
  unsigned int v41; // ebx
  bool MustFlushTlbOnValidTransition; // al
  __int64 v43; // r9
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // r9
  __int64 v48; // r8
  __int64 v49; // r10
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v50; // rax
  LARGE_INTEGER *v51; // rsi
  struct VIDMM_MAPPED_VA_RANGE *v52; // rdi
  void *DriverAllocation; // rax
  ADAPTER_RENDER *v54; // rcx
  CVirtualAddressAllocator *v55; // rbx
  int v56; // eax
  __int64 v57; // rcx
  int v58; // ebx
  __int64 v59; // rdx
  __int64 v60; // rax
  bool v61; // zf
  __int64 v62; // rbx
  unsigned int CurrentProcessId; // eax
  int v64; // edx
  int v65; // r8d
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rbx
  SIZE_T v70; // rdi
  SIZE_T v71; // rsi
  __int64 v72; // rcx
  _QWORD *v73; // rdx
  struct VIDMM_MAPPED_VA_RANGE *v74; // r9
  char *v75; // rax
  __int64 v76; // rax
  __int64 v77; // rcx
  __int64 **v78; // rdx
  __int64 v79; // r8
  __int64 *v80; // rax
  unsigned __int64 v81; // rdx
  int v82; // [rsp+28h] [rbp-D8h]
  bool v83; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v84; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned __int8 v85[2]; // [rsp+62h] [rbp-9Eh] BYREF
  unsigned int v86; // [rsp+64h] [rbp-9Ch]
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v87; // [rsp+68h] [rbp-98h]
  struct VIDMM_GLOBAL_ALLOC *v88; // [rsp+70h] [rbp-90h]
  unsigned __int64 v89; // [rsp+78h] [rbp-88h]
  unsigned int v90[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v91; // [rsp+88h] [rbp-78h]
  unsigned int v92; // [rsp+8Ch] [rbp-74h]
  int v93; // [rsp+90h] [rbp-70h]
  SIZE_T v94; // [rsp+98h] [rbp-68h]
  SIZE_T v95; // [rsp+A0h] [rbp-60h]
  unsigned int v96[4]; // [rsp+A8h] [rbp-58h] BYREF
  int v97; // [rsp+B8h] [rbp-48h] BYREF
  int v98; // [rsp+BCh] [rbp-44h]
  unsigned __int64 v99; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v100; // [rsp+C8h] [rbp-38h]
  unsigned __int64 i; // [rsp+D0h] [rbp-30h]
  SIZE_T v102; // [rsp+D8h] [rbp-28h]
  struct VIDMM_MAPPED_VA_RANGE *v103; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v104; // [rsp+E8h] [rbp-18h]
  __int64 v105; // [rsp+F0h] [rbp-10h]
  SIZE_T v106; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v107; // [rsp+100h] [rbp+0h]
  struct VIDMM_TRANSFER_PARAMETER *v108; // [rsp+108h] [rbp+8h]
  struct VIDMM_TRANSFER_PARAMETER *v109; // [rsp+110h] [rbp+10h]
  __int64 v110; // [rsp+118h] [rbp+18h]
  struct _DXGKARG_BUILDPAGINGBUFFER v111; // [rsp+120h] [rbp+20h] BYREF
  __int128 v112; // [rsp+260h] [rbp+160h] BYREF
  SIZE_T v113; // [rsp+270h] [rbp+170h]

  v12 = a7;
  v13 = a4;
  v14 = a2;
  v104 = a11;
  v15 = *(_QWORD *)a8;
  v16 = *(_QWORD *)a7;
  v17 = *((unsigned int *)this + 9324);
  v18 = *((unsigned int *)this + 799);
  v83 = *(_QWORD *)a8 < *(_QWORD *)a7;
  v88 = a4;
  v86 = a3;
  v19 = a3;
  v87 = a2;
  v108 = a8;
  v109 = a7;
  v94 = v16;
  v95 = v15;
  if ( (_DWORD)v18 && (unsigned int)v17 >= (unsigned int)v18 )
    v17 = (unsigned int)v18;
  v20 = *((_QWORD *)a8 + 2);
  v21 = *((_QWORD *)a7 + 2);
  if ( v21 != v20 )
  {
    v100 = v17;
    v83 = 1;
LABEL_14:
    v23 = a9;
    v22 = a5;
    v89 = a9;
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
  v100 = v17;
  if ( v15 < v16 )
    goto LABEL_14;
  v22 = a5;
  v23 = a9;
  v16 += a5;
  v15 += a5;
  v94 = v16;
  v95 = v15;
  v100 = v17;
  v18 = a5 + a9;
  v89 = a5 + a9;
  LOBYTE(v18) = v83;
LABEL_15:
  if ( v21 )
    v91 = *(unsigned __int16 *)(v21 + 64);
  else
    v91 = 0;
  if ( v20 )
  {
    v18 = *(unsigned __int16 *)(v20 + 64);
    v92 = *(unsigned __int16 *)(v20 + 64);
  }
  else
  {
    v92 = 0;
  }
  v85[0] = 0;
  v84 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(v18) + 24) = v88;
    WdLogGlobalForLineNumber = 16140;
    v25 = (_QWORD *)WdLogNewEntry5_WdTrace(v24);
    v25[3] = v22;
    v25[4] = a6;
    v25[5] = v23;
    WdLogGlobalForLineNumber = 16142;
    v27 = (_QWORD *)WdLogNewEntry5_WdTrace(v26);
    v27[3] = *((_QWORD *)a7 + 2);
    v27[4] = *(_QWORD *)a7;
    v27[5] = *((_QWORD *)a7 + 5);
    v28 = *((_QWORD *)a7 + 3);
    v27[6] = v28;
    WdLogGlobalForLineNumber = 16144;
    v29 = (_QWORD *)WdLogNewEntry5_WdTrace(v28);
    v29[3] = *((_QWORD *)a8 + 2);
    v29[4] = *(_QWORD *)a8;
    v29[5] = *((_QWORD *)a8 + 5);
    v29[6] = *((_QWORD *)a8 + 3);
    WdLogGlobalForLineNumber = 16146;
    v13 = v88;
    v19 = v86;
    v14 = v87;
  }
  v30 = a6;
  v31 = v22;
  v107 = v22;
  if ( !v22 )
    return;
  v110 = v19;
  while ( 2 )
  {
    v32 = (unsigned int)v100;
    v33 = v89;
    if ( v31 <= v100 )
      v32 = (unsigned int)v31;
    if ( v83 )
    {
      v102 = v16;
      v106 = v15;
    }
    else
    {
      v102 = v16 - v32;
      v106 = v15 - v32;
      v33 = v89 - v32;
    }
    v34 = v89 + v30;
    v35 = v86;
    for ( i = v34; ; v34 = i )
    {
      v36 = *((_QWORD *)v12 + 5);
      *(_QWORD *)v96 = a5 >> 12;
      if ( v36 )
      {
        v37 = *((_QWORD *)v12 + 1);
        v98 = 0;
        v97 = a5 >> 12;
        if ( !v37 )
        {
          v99 = v36;
          goto LABEL_36;
        }
      }
      else
      {
        v97 = (unsigned int)a5 >> 12;
        v37 = *(_QWORD *)v12 + *((_QWORD *)v12 + 3);
      }
      v99 = v37 >> 12;
      v98 = 1;
LABEL_36:
      v103 = VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(
               (VIDMM_GLOBAL *)((char *)this + 36672),
               v14,
               v35,
               v32,
               v13,
               v34,
               v91,
               v33,
               (const struct _DXGK_ADL *)&v97,
               v85,
               v104);
      if ( v103 )
        break;
      VIDMM_GLOBAL::FlushPagingBufferInternal(this, v87, v35, 1, 0, 0);
      VIDMM_GLOBAL::FlushScratchGpuVaRanges(this, v87, v35);
      v14 = v87;
      v13 = v88;
    }
    v38 = v108;
    v39 = v96[0];
    while ( 1 )
    {
      v40 = (const unsigned __int64 *)*((_QWORD *)v38 + 5);
      *(_OWORD *)v96 = 0;
      if ( v40 )
      {
        VidMmiInitializeAdlForPfnArray((struct _DXGK_ADL *)v96, v40, v39, *((_QWORD *)v38 + 1));
      }
      else
      {
        v96[1] = 1;
        v96[0] = (unsigned int)a5 >> 12;
        *(_QWORD *)&v96[2] = (*(_QWORD *)v38 + *((_QWORD *)v38 + 3)) >> 12;
      }
      *(_QWORD *)v96 = VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(
                         (VIDMM_GLOBAL *)((char *)this + 36672),
                         v87,
                         v35,
                         v32,
                         v88,
                         i,
                         v92,
                         v33,
                         (const struct _DXGK_ADL *)v96,
                         &v84,
                         v104);
      if ( *(_QWORD *)v96 )
        break;
      VIDMM_GLOBAL::FlushPagingBufferInternal(this, v87, v35, 1, 0, 0);
      VIDMM_GLOBAL::FlushScratchGpuVaRanges(this, v87, v35);
    }
    v41 = v35;
    MustFlushTlbOnValidTransition = VIDMM_GLOBAL::MustFlushTlbOnValidTransition(this, v35);
    v12 = v109;
    if ( MustFlushTlbOnValidTransition )
    {
      v44 = *(_QWORD *)(v43 + 112);
      v45 = *(_QWORD *)(v43 + 104);
      v46 = *((_QWORD *)v103 + 14);
      v47 = *((_QWORD *)v103 + 13);
      if ( v46 <= v44 )
        v46 = v44;
      if ( v47 >= v45 )
        v47 = v45;
      CVirtualAddressAllocator::FlushGpuVaTlb(*((CVirtualAddressAllocator **)this + v35 + 4588), v87, v35, v47, v46);
    }
    memset(&v111, 0, sizeof(v111));
    LOBYTE(v48) = *((_BYTE *)this + 37231) != 0;
    v111.hSystemContext = (HANDLE)VidSchGetDriverPagingContext(*(_QWORD *)(*((_QWORD *)this + 2) + 744LL), v35, v48);
    v50 = v87;
    v111.MultipassOffset = v49;
    if ( v87 )
    {
      v105 = *(_QWORD *)(*((_QWORD *)v87 + 3) + 8LL * v35);
      v50 = v87;
    }
    else
    {
      v105 = v49;
    }
    if ( *((_QWORD *)v12 + 5) == v49 )
    {
      v111.Transfer.Destination.SegmentAddress.LowPart = v49;
      if ( *((_QWORD *)v38 + 5) == v49 )
        v111.Transfer.Destination.SegmentAddress.LowPart = 2;
    }
    else
    {
      v111.Transfer.Destination.SegmentAddress.LowPart = 1;
    }
    v51 = *(LARGE_INTEGER **)v96;
    v52 = v103;
    while ( 1 )
    {
      VIDMM_GLOBAL::SetupForBuildPagingBufferIteration(this, v50, v41, v88, &v111);
      DriverAllocation = VidMmGetDriverAllocation(v88);
      v54 = (ADAPTER_RENDER *)*((_QWORD *)this + 2);
      v111.UpdateContextAllocation.ContextAllocation = (D3DGPU_VIRTUAL_ADDRESS)DriverAllocation;
      v111.Fill.FillSize = i;
      v111.Operation = DXGK_OPERATION_VIRTUAL_TRANSFER;
      v111.Transfer.TransferSize = v32;
      v111.MapApertureSegment.OffsetInPages = *((_QWORD *)v52 + 13);
      v111.Transfer.Source.SegmentAddress = v51[13];
      if ( (*((_DWORD *)ADAPTER_RENDER::GetGpuMmuCaps(v54, v41) + 5) & 1) != 0 )
      {
        v55 = (CVirtualAddressAllocator *)*((_QWORD *)this + v41 + 4588);
        v111.UnmapApertureSegment.DummyPage.QuadPart = (unsigned int)CVirtualAddressAllocator::GetVirtualAddressOfPageTable(
                                                                       v55,
                                                                       v86,
                                                                       *((_QWORD *)v52 + 13),
                                                                       v85[0] != 0);
        v111.TransferVirtual.DestinationPageTable = (unsigned int)CVirtualAddressAllocator::GetVirtualAddressOfPageTable(
                                                                    v55,
                                                                    v86,
                                                                    v51[13].QuadPart,
                                                                    v84 != 0);
        v111.Transfer.Destination.SegmentAddress.HighPart = v111.Transfer.Destination.SegmentAddress.HighPart
                                                          & 0xFFFFFFFC
                                                          | v85[0] & 1
                                                          | (2 * (v84 & 1));
      }
      VIDMM_GLOBAL::RecordVaPagingHistoryVirtualTransfer(this, &v111, v88);
      v56 = ADAPTER_RENDER::DdiBuildPagingBuffer(*((ADAPTER_RENDER **)this + 2), &v111);
      v57 = *((_QWORD *)this + 390);
      v58 = v56;
      v93 = v56;
      if ( v57 )
      {
        v59 = *((_QWORD *)v38 + 2);
        if ( !v59 || *(_DWORD *)(v59 + 100) != 1 )
          VIDMM_PROCESS::ChargeEvictionTransfer(
            *(VIDMM_PROCESS **)(v57 + 8),
            *(_DWORD *)(*((_QWORD *)this + 3) + 240LL),
            v32);
      }
      _InterlockedAdd64((volatile signed __int64 *)this + 501, v32);
      LOBYTE(v90[0]) = byte_140087201 & 0x10;
      if ( (byte_140087201 & 0x10) != 0 )
      {
        v60 = *((_QWORD *)v12 + 2);
        if ( !v60 || (v61 = *(_DWORD *)(v60 + 100) == 1, v90[0] = 2, !v61) )
          v90[0] = 1;
        v62 = *(_QWORD *)(v105 + 16);
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        McTemplateK0pppxxq_EtwWriteTransfer((_DWORD)v88, v64, v65, CurrentProcessId, (char)v88, v62, v102, v32, v90[0]);
        VidMmRecordTransfer((VIDMM_GLOBAL *)((char *)this + 3296), v32, v90[0]);
        v58 = v93;
      }
      v113 = 0;
      v66 = *((_QWORD *)v12 + 2);
      v112 = 0;
      if ( v66 )
        LODWORD(v112) = (unsigned __int16)(*(_WORD *)(v66 + 62) + 1);
      *((_QWORD *)&v112 + 1) = v102;
      v67 = *((_QWORD *)v38 + 2);
      DWORD1(v112) = v67 ? (unsigned __int16)(*(_WORD *)(v67 + 62) + 1) : 0;
      v113 = v106;
      v82 = v58;
      v41 = v86;
      *(_QWORD *)v90 = 0;
      VIDMM_GLOBAL::CompleteBuildPagingBufferIteration(
        this,
        v87,
        v86,
        v88,
        &v111,
        v82,
        0,
        (unsigned __int64 *)v90,
        &v112);
      if ( v93 >= 0 )
        break;
      v50 = v87;
    }
    v68 = *((_QWORD *)this + 4560);
    v69 = v110;
    v70 = v94;
    v71 = v95;
    v72 = *(_QWORD *)(v68 + 8 * v110) + 1376LL;
    v73 = *(_QWORD **)(*(_QWORD *)(v68 + 8 * v110) + 1384LL);
    if ( *v73 != v72 )
      goto LABEL_83;
    v74 = v103;
    v75 = (char *)v103 + 32;
    *((_QWORD *)v103 + 4) = v72;
    *((_QWORD *)v75 + 1) = v73;
    *v73 = v75;
    *(_QWORD *)(v72 + 8) = v75;
    v76 = *((_QWORD *)this + 4560);
    v77 = *(_QWORD *)(v76 + 8 * v69) + 1376LL;
    v78 = *(__int64 ***)(*(_QWORD *)(v76 + 8 * v69) + 1384LL);
    if ( *v78 != (__int64 *)v77 )
LABEL_83:
      __fastfail(3u);
    v79 = *(_QWORD *)v96;
    v13 = v88;
    v80 = (__int64 *)(*(_QWORD *)v96 + 32LL);
    *(_QWORD *)(*(_QWORD *)v96 + 40LL) = v78;
    *v80 = v77;
    *v78 = v80;
    v81 = v107;
    *(_QWORD *)(v77 + 8) = v80;
    v31 = v81 - v32;
    *((_QWORD *)v74 + 6) = *((_QWORD *)v13 + 11);
    *(_QWORD *)(v79 + 48) = *((_QWORD *)v13 + 11);
    v107 = v31;
    if ( v83 )
    {
      v16 = v32 + v70;
      v15 = v32 + v71;
      v89 += v32;
    }
    else
    {
      v16 = v70 - v32;
      v15 = v71 - v32;
      v89 -= v32;
    }
    v95 = v15;
    v94 = v16;
    if ( v31 )
    {
      v14 = v87;
      v30 = a6;
      continue;
    }
    break;
  }
}

```

## disassembly

```asm
0x1400a3b9c  push    rbp
0x1400a3b9e  push    rbx
0x1400a3b9f  push    rsi
0x1400a3ba0  push    rdi
0x1400a3ba1  push    r12
0x1400a3ba3  push    r13
0x1400a3ba5  push    r14
0x1400a3ba7  push    r15
0x1400a3ba9  lea     rbp, [rsp-188h]
0x1400a3bb1  sub     rsp, 288h
0x1400a3bb8  mov     rax, cs:__security_cookie
0x1400a3bbf  xor     rax, rsp
0x1400a3bc2  mov     [rbp+1C0h+var_48], rax
0x1400a3bc9  mov     r13, [rbp+1C0h+arg_38]
0x1400a3bd0  mov     r14, rcx
0x1400a3bd3  mov     r12, [rbp+1C0h+arg_30]
0x1400a3bda  mov     r11, r9
0x1400a3bdd  mov     rax, [rbp+1C0h+arg_50]
0x1400a3be4  mov     r10, rdx
0x1400a3be7  mov     [rbp+1C0h+var_1D8], rax
0x1400a3beb  mov     rsi, [r13+0]
0x1400a3bef  mov     rdi, [r12]
0x1400a3bf3  mov     eax, [rcx+91B0h]
0x1400a3bf9  cmp     rsi, rdi
0x1400a3bfc  mov     ecx, [rcx+0C7Ch]
0x1400a3c02  setb    [rsp+2C0h+var_260]
0x1400a3c07  mov     [rsp+2C0h+var_250], r9
0x1400a3c0c  mov     [rsp+2C0h+var_25C], r8d
0x1400a3c11  mov     r9d, r8d
0x1400a3c14  mov     [rsp+2C0h+var_258], rdx
0x1400a3c19  mov     [rbp+1C0h+var_1B8], r13
0x1400a3c1d  mov     [rbp+1C0h+var_1B0], r12
0x1400a3c21  mov     [rbp+1C0h+var_228], rdi
0x1400a3c25  mov     [rbp+1C0h+var_220], rsi
0x1400a3c29  test    ecx, ecx
0x1400a3c2b  jz      short loc_1400A3C32
0x1400a3c2d  cmp     eax, ecx
0x1400a3c2f  cmovnb  eax, ecx
0x1400a3c32  mov     r8, [r13+10h]
0x1400a3c36  mov     rdx, [r12+10h]
0x1400a3c3b  cmp     rdx, r8
0x1400a3c3e  jnz     short loc_1400A3C9C
0x1400a3c40  cmp     rdi, rsi
0x1400a3c43  jz      loc_1400A4437
0x1400a3c49  jbe     short loc_1400A3C53
0x1400a3c4b  mov     rcx, rdi
0x1400a3c4e  sub     rcx, rsi
0x1400a3c51  jmp     short loc_1400A3C59
0x1400a3c53  mov     rcx, rsi
0x1400a3c56  sub     rcx, rdi
0x1400a3c59  cmp     rcx, rax
0x1400a3c5c  cmovbe  rax, rcx
0x1400a3c60  mov     [rbp+1C0h+var_1F8], rax
0x1400a3c64  cmp     rsi, rdi
0x1400a3c67  jb      short loc_1400A3CA5
0x1400a3c69  mov     r15, [rbp+1C0h+arg_20]
0x1400a3c70  mov     rbx, [rbp+1C0h+arg_40]
0x1400a3c77  add     rdi, r15
0x1400a3c7a  add     rsi, r15
0x1400a3c7d  mov     [rbp+1C0h+var_228], rdi
0x1400a3c81  mov     [rbp+1C0h+var_220], rsi
0x1400a3c85  mov     [rbp+1C0h+var_1F8], rax
0x1400a3c89  lea     rcx, [r15+rbx]
0x1400a3c8d  mov     [rsp+2C0h+var_248], rcx
0x1400a3c92  mov     cl, [rsp+2C0h+var_260]
0x1400a3c96  mov     [rsp+2C0h+var_260], cl
0x1400a3c9a  jmp     short loc_1400A3CB8
0x1400a3c9c  mov     [rbp+1C0h+var_1F8], rax
0x1400a3ca0  mov     [rsp+2C0h+var_260], 1
0x1400a3ca5  mov     rbx, [rbp+1C0h+arg_40]
0x1400a3cac  mov     r15, [rbp+1C0h+arg_20]
0x1400a3cb3  mov     [rsp+2C0h+var_248], rbx
0x1400a3cb8  test    rdx, rdx
0x1400a3cbb  jz      short loc_1400A3CC6
0x1400a3cbd  movzx   eax, word ptr [rdx+40h]
0x1400a3cc1  mov     [rbp+1C0h+var_238], eax
0x1400a3cc4  jmp     short loc_1400A3CCD
0x1400a3cc6  mov     [rbp+1C0h+var_238], 0
0x1400a3ccd  test    r8, r8
0x1400a3cd0  jz      short loc_1400A3CDC
0x1400a3cd2  movzx   ecx, word ptr [r8+40h]
0x1400a3cd7  mov     [rbp+1C0h+var_234], ecx
0x1400a3cda  jmp     short loc_1400A3CE3
0x1400a3cdc  mov     [rbp+1C0h+var_234], 0
0x1400a3ce3  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a3cea  mov     [rsp+2C0h+var_25E], 0
0x1400a3cef  mov     [rsp+2C0h+var_25F], 0
0x1400a3cf4  cmp     byte ptr [rax], 0
0x1400a3cf7  jz      loc_1400A3DEF
0x1400a3cfd  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a3d04  nop     dword ptr [rax+rax+00h]
0x1400a3d09  mov     r11, [rsp+2C0h+var_250]
0x1400a3d0e  mov     [rax+18h], r11
0x1400a3d12  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a3d19  mov     cs:WdLogGlobalForLineNumber, 3F0Ch
0x1400a3d23  cmp     byte ptr [rax], 0
0x1400a3d26  jz      loc_1400A3DE5
0x1400a3d2c  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a3d33  nop     dword ptr [rax+rax+00h]
0x1400a3d38  mov     r8, [rbp+1C0h+arg_28]
0x1400a3d3f  mov     [rax+18h], r15
0x1400a3d43  mov     [rax+20h], r8
0x1400a3d47  mov     [rax+28h], rbx
0x1400a3d4b  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a3d52  mov     cs:WdLogGlobalForLineNumber, 3F0Eh
0x1400a3d5c  cmp     byte ptr [rax], 0
0x1400a3d5f  jz      loc_1400A3E34
0x1400a3d65  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a3d6c  nop     dword ptr [rax+rax+00h]
0x1400a3d71  mov     rcx, [r12+10h]
0x1400a3d76  mov     [rax+18h], rcx
0x1400a3d7a  mov     rcx, [r12]
0x1400a3d7e  mov     [rax+20h], rcx
0x1400a3d82  mov     rcx, [r12+28h]
0x1400a3d87  mov     [rax+28h], rcx
0x1400a3d8b  mov     rcx, [r12+18h]
0x1400a3d90  mov     [rax+30h], rcx
0x1400a3d94  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a3d9b  mov     cs:WdLogGlobalForLineNumber, 3F10h
0x1400a3da5  cmp     byte ptr [rax], 0
0x1400a3da8  jz      short loc_1400A3DE0
0x1400a3daa  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a3db1  nop     dword ptr [rax+rax+00h]
0x1400a3db6  mov     rcx, [r13+10h]
0x1400a3dba  mov     [rax+18h], rcx
0x1400a3dbe  mov     rcx, [r13+0]
0x1400a3dc2  mov     [rax+20h], rcx
0x1400a3dc6  mov     rcx, [r13+28h]
0x1400a3dca  mov     [rax+28h], rcx
0x1400a3dce  mov     rcx, [r13+18h]
0x1400a3dd2  mov     [rax+30h], rcx
0x1400a3dd6  mov     cs:WdLogGlobalForLineNumber, 3F12h
0x1400a3de0  mov     r11, [rsp+2C0h+var_250]
0x1400a3de5  mov     r9d, [rsp+2C0h+var_25C]
0x1400a3dea  mov     r10, [rsp+2C0h+var_258]
0x1400a3def  mov     r8, [rbp+1C0h+arg_28]
0x1400a3df6  mov     rdx, r15
0x1400a3df9  mov     [rbp+1C0h+var_1C0], rdx
0x1400a3dfd  test    r15, r15
0x1400a3e00  jz      loc_1400A4437
0x1400a3e06  mov     ebx, r9d
0x1400a3e09  mov     [rbp+1C0h+var_1A8], rbx
0x1400a3e0d  mov     rcx, [rbp+1C0h+var_1F8]
0x1400a3e11  mov     rax, [rsp+2C0h+var_248]
0x1400a3e16  cmp     rdx, rcx
0x1400a3e19  mov     r15d, ecx
0x1400a3e1c  mov     rbx, rax
0x1400a3e1f  cmovbe  r15d, edx
0x1400a3e23  cmp     [rsp+2C0h+var_260], 0
0x1400a3e28  jz      short loc_1400A3E45
0x1400a3e2a  mov     [rbp+1C0h+var_1E8], rdi
0x1400a3e2e  mov     [rbp+1C0h+var_1C8], rsi
0x1400a3e32  jmp     short loc_1400A3E5C
0x1400a3e34  mov     r9d, [rsp+2C0h+var_25C]
0x1400a3e39  mov     r10, [rsp+2C0h+var_258]
0x1400a3e3e  mov     r11, [rsp+2C0h+var_250]
0x1400a3e43  jmp     short loc_1400A3DF6
0x1400a3e45  mov     rcx, rdi
0x1400a3e48  sub     rcx, r15
0x1400a3e4b  mov     [rbp+1C0h+var_1E8], rcx
0x1400a3e4f  mov     rcx, rsi
0x1400a3e52  sub     rcx, r15
0x1400a3e55  mov     [rbp+1C0h+var_1C8], rcx
0x1400a3e59  sub     rbx, r15
0x1400a3e5c  mov     r13, [rbp+1C0h+arg_20]
0x1400a3e63  add     r8, rax
0x1400a3e66  mov     esi, [rsp+2C0h+var_25C]
0x1400a3e6a  mov     [rbp+1C0h+var_1F0], r8
0x1400a3e6e  mov     rcx, [r12+28h]
0x1400a3e73  mov     rdx, r13
0x1400a3e76  shr     rdx, 0Ch
0x1400a3e7a  mov     qword ptr [rbp+1C0h+var_218], rdx
0x1400a3e7e  test    rcx, rcx
0x1400a3e81  jz      short loc_1400A3E9D
0x1400a3e83  mov     rax, [r12+8]
0x1400a3e88  mov     [rbp+1C0h+var_204], 0
0x1400a3e8f  mov     [rbp+1C0h+var_208], edx
0x1400a3e92  test    rax, rax
0x1400a3e95  jnz     short loc_1400A3EAF
0x1400a3e97  mov     [rbp+1C0h+var_200], rcx
0x1400a3e9b  jmp     short loc_1400A3EBE
0x1400a3e9d  mov     eax, r13d
0x1400a3ea0  shr     eax, 0Ch
0x1400a3ea3  mov     [rbp+1C0h+var_208], eax
0x1400a3ea6  mov     rax, [r12+18h]
0x1400a3eab  add     rax, [r12]
0x1400a3eaf  shr     rax, 0Ch
0x1400a3eb3  mov     [rbp+1C0h+var_200], rax
0x1400a3eb7  mov     [rbp+1C0h+var_204], 1
0x1400a3ebe  mov     rax, [rbp+1C0h+var_1D8]
0x1400a3ec2  lea     rcx, [r14+8F40h]; this
0x1400a3ec9  mov     [rsp+2C0h+var_270], rax; unsigned __int64
0x1400a3ece  mov     r9, r15; unsigned __int64
0x1400a3ed1  lea     rax, [rsp+2C0h+var_25E]
0x1400a3ed6  mov     rdx, r10; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a3ed9  mov     [rsp+2C0h+var_278], rax; unsigned __int8 *
0x1400a3ede  lea     rax, [rbp+1C0h+var_208]
0x1400a3ee2  mov     [rsp+2C0h+var_280], rax; struct _DXGK_ADL *
0x1400a3ee7  mov     eax, [rbp+1C0h+var_238]
0x1400a3eea  mov     [rsp+2C0h+var_288], rbx; unsigned __int64
0x1400a3eef  mov     dword ptr [rsp+2C0h+var_290], eax; unsigned int
0x1400a3ef3  mov     qword ptr [rsp+2C0h+var_298], r8; unsigned __int64
0x1400a3ef8  mov     r8d, esi; unsigned int
0x1400a3efb  mov     [rsp+2C0h+var_2A0], r11; struct VIDMM_GLOBAL_ALLOC *
0x1400a3f00  call    ?MapScratchAreaVaRange@VIDMM_PAGING_PROCESS@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_KPEAUVIDMM_GLOBAL_ALLOC@@1I1PEBU_DXGK_ADL@@PEAE1@Z; VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,unsigned __int64,VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,unsigned __int64,_DXGK_ADL const *,uchar *,unsigned __int64)
0x1400a3f05  mov     [rbp+1C0h+var_1E0], rax
0x1400a3f09  test    rax, rax
0x1400a3f0c  jnz     short loc_1400A3F4C
0x1400a3f0e  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a3f13  mov     r9b, 1; bool
0x1400a3f16  mov     [rsp+2C0h+var_298], al; bool
0x1400a3f1a  mov     r8d, esi; unsigned int
0x1400a3f1d  mov     rcx, r14; this
0x1400a3f20  mov     byte ptr [rsp+2C0h+var_2A0], al; bool
0x1400a3f24  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a3f29  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a3f2e  mov     r8d, esi; unsigned int
0x1400a3f31  mov     rcx, r14; this
0x1400a3f34  call    ?FlushScratchGpuVaRanges@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::FlushScratchGpuVaRanges(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a3f39  mov     r10, [rsp+2C0h+var_258]
0x1400a3f3e  mov     r11, [rsp+2C0h+var_250]
0x1400a3f43  mov     r8, [rbp+1C0h+var_1F0]
0x1400a3f47  jmp     loc_1400A3E6E
0x1400a3f4c  mov     r13, [rbp+1C0h+var_1B8]
0x1400a3f50  mov     r12, qword ptr [rbp+1C0h+var_218]
0x1400a3f54  mov     rdi, [rbp+1C0h+arg_20]
0x1400a3f5b  mov     rdx, [r13+28h]; unsigned __int64 *
0x1400a3f5f  xorps   xmm0, xmm0
0x1400a3f62  movups  xmmword ptr [rbp+1C0h+var_218], xmm0
0x1400a3f66  test    rdx, rdx
0x1400a3f69  jz      short loc_1400A3F7D
0x1400a3f6b  mov     r9, [r13+8]; unsigned __int64
0x1400a3f6f  lea     rcx, [rbp+1C0h+var_218]; struct _DXGK_ADL *
0x1400a3f73  mov     r8d, r12d; unsigned int
0x1400a3f76  call    ?VidMmiInitializeAdlForPfnArray@@YAXPEAU_DXGK_ADL@@PEB_KI_K@Z; VidMmiInitializeAdlForPfnArray(_DXGK_ADL *,unsigned __int64 const *,uint,unsigned __int64)
0x1400a3f7b  jmp     short loc_1400A3F9C
0x1400a3f7d  mov     eax, edi
0x1400a3f7f  mov     [rbp+1C0h+var_218+4], 1
0x1400a3f86  shr     eax, 0Ch
0x1400a3f89  mov     [rbp+1C0h+var_218], eax
0x1400a3f8c  mov     rax, [r13+18h]
0x1400a3f90  add     rax, [r13+0]
0x1400a3f94  shr     rax, 0Ch
0x1400a3f98  mov     qword ptr [rbp+1C0h+var_218+8], rax
0x1400a3f9c  mov     rax, [rbp+1C0h+var_1D8]
0x1400a3fa0  lea     rcx, [r14+8F40h]; this
0x1400a3fa7  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a3fac  mov     r9, r15; unsigned __int64
0x1400a3faf  mov     [rsp+2C0h+var_270], rax; unsigned __int64
0x1400a3fb4  mov     r8d, esi; unsigned int
0x1400a3fb7  lea     rax, [rsp+2C0h+var_25F]
0x1400a3fbc  mov     [rsp+2C0h+var_278], rax; unsigned __int8 *
0x1400a3fc1  lea     rax, [rbp+1C0h+var_218]
0x1400a3fc5  mov     [rsp+2C0h+var_280], rax; struct _DXGK_ADL *
0x1400a3fca  mov     eax, [rbp+1C0h+var_234]
0x1400a3fcd  mov     [rsp+2C0h+var_288], rbx; unsigned __int64
0x1400a3fd2  mov     dword ptr [rsp+2C0h+var_290], eax; unsigned int
0x1400a3fd6  mov     rax, [rbp+1C0h+var_1F0]
0x1400a3fda  mov     qword ptr [rsp+2C0h+var_298], rax; unsigned __int64
0x1400a3fdf  mov     rax, [rsp+2C0h+var_250]
0x1400a3fe4  mov     [rsp+2C0h+var_2A0], rax; struct VIDMM_GLOBAL_ALLOC *
0x1400a3fe9  call    ?MapScratchAreaVaRange@VIDMM_PAGING_PROCESS@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_KPEAUVIDMM_GLOBAL_ALLOC@@1I1PEBU_DXGK_ADL@@PEAE1@Z; VIDMM_PAGING_PROCESS::MapScratchAreaVaRange(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,unsigned __int64,VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,unsigned __int64,_DXGK_ADL const *,uchar *,unsigned __int64)
0x1400a3fee  mov     qword ptr [rbp+1C0h+var_218], rax
0x1400a3ff2  mov     r9, rax
0x1400a3ff5  mov     rcx, r14; this
0x1400a3ff8  test    rax, rax
0x1400a3ffb  jnz     short loc_1400A402A
0x1400a3ffd  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a4002  mov     r9b, 1; bool
0x1400a4005  mov     [rsp+2C0h+var_298], al; bool
0x1400a4009  mov     r8d, esi; unsigned int
0x1400a400c  mov     byte ptr [rsp+2C0h+var_2A0], al; bool
0x1400a4010  call    ?FlushPagingBufferInternal@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@K_N11@Z; VIDMM_GLOBAL::FlushPagingBufferInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,ulong,bool,bool,bool)
0x1400a4015  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a401a  mov     r8d, esi; unsigned int
0x1400a401d  mov     rcx, r14; this
0x1400a4020  call    ?FlushScratchGpuVaRanges@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::FlushScratchGpuVaRanges(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400a4025  jmp     loc_1400A3F5B
0x1400a402a  mov     ebx, esi
0x1400a402c  mov     edx, ebx; unsigned int
0x1400a402e  call    ?MustFlushTlbOnValidTransition@VIDMM_GLOBAL@@QEAA_NI@Z; VIDMM_GLOBAL::MustFlushTlbOnValidTransition(uint)
0x1400a4033  mov     r12, [rbp+1C0h+var_1B0]
0x1400a4037  test    al, al
0x1400a4039  jz      short loc_1400A4077
0x1400a403b  mov     rax, [r9+70h]
0x1400a403f  mov     rcx, [r9+68h]
0x1400a4043  mov     r8, [rbp+1C0h+var_1E0]
0x1400a4047  mov     rdx, [r8+70h]
0x1400a404b  mov     r9, [r8+68h]
0x1400a404f  cmp     rdx, rax
0x1400a4052  mov     r8d, ebx; unsigned int
0x1400a4055  cmovbe  rdx, rax
0x1400a4059  cmp     r9, rcx
0x1400a405c  mov     [rsp+2C0h+var_2A0], rdx; unsigned __int64
0x1400a4061  mov     rdx, [rsp+2C0h+var_258]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a4066  cmovnb  r9, rcx; unsigned __int64
0x1400a406a  mov     rcx, [r14+rbx*8+8F60h]; this
0x1400a4072  call    ?FlushGpuVaTlb@CVirtualAddressAllocator@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I_K1@Z; CVirtualAddressAllocator::FlushGpuVaTlb(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,unsigned __int64,unsigned __int64)
0x1400a4077  xor     edx, edx; Val
0x1400a4079  lea     rcx, [rbp+1C0h+var_1A0]; void *
  ... truncated ...
```
