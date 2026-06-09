# DXGDEVICE::CreateDriverAllocations(_D3DKMT_CREATEALLOCATION *,_D3DDDI_ALLOCATIONINFO2 *,_DXGK_ALLOCATIONINFO *,DXGALLOCATION *,DXGRESOURCE *,void * *,void * *,void *,_D3DKM_CREATESTANDARDALLOCATION const *,int,_D3DKMT_CREATESTANDARDALLOCATION *)

- ea: `0x14040297c`
- end: `0x140403750`
- name: `?CreateDriverAllocations@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@PEAU_DXGK_ALLOCATIONINFO@@PEAVDXGALLOCATION@@PEAVDXGRESOURCE@@PEAPEAX5PEAXPEBU_D3DKM_CREATESTANDARDALLOCATION@@HPEAU_D3DKMT_CREATESTANDARDALLOCATION@@@Z`
- size: `3540`
- prototype: `__int64 __fastcall(DXGDEVICE *__hidden this, struct _D3DKMT_CREATEALLOCATION *, struct _D3DDDI_ALLOCATIONINFO2 *, struct _DXGK_ALLOCATIONINFO *, struct DXGALLOCATION *, struct DXGRESOURCE *, void **, void **, void *, const struct _D3DKM_CREATESTANDARDALLOCATION *, int, struct _D3DKMT_CREATESTANDARDALLOCATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x140377080`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x14001b9c0`
- `0x14002dbc0`
- `0x14002ff90`
- `0x140033d80`
- `0x140050484`
- `0x1400a0d00`
- `0x14038818c`
- `0x1403c1ec0`
- `0x14040297c`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x140402b24`
- `watchdog!WdLogSingleEntry3` at `0x1404034f3`
- `watchdog!WdLogSingleEntry3` at `0x14040354d`
- `watchdog!WdLogSingleEntry3` at `0x1404035b3`
- `watchdog!WdLogSingleEntry3` at `0x1404035ea`
- `watchdog!WdLogSingleEntry3` at `0x14040361c`
- `watchdog!WdLogSingleEntry3` at `0x140402b24`
- `watchdog!WdLogSingleEntry3` at `0x1404034f3`
- `watchdog!WdLogSingleEntry3` at `0x14040354d`
- `watchdog!WdLogSingleEntry3` at `0x1404035b3`
- `watchdog!WdLogSingleEntry3` at `0x1404035ea`
- `watchdog!WdLogSingleEntry3` at `0x14040361c`
- `watchdog!WdLogSingleEntry0` at `0x1404029d3`
- `watchdog!WdLogSingleEntry0` at `0x140402dee`
- `watchdog!WdLogSingleEntry0` at `0x140403477`
- `watchdog!WdLogSingleEntry0` at `0x140403494`
- `watchdog!WdLogSingleEntry0` at `0x1404029d3`
- `watchdog!WdLogSingleEntry0` at `0x140402dee`
- `watchdog!WdLogSingleEntry0` at `0x140403477`
- `watchdog!WdLogSingleEntry0` at `0x140403494`
- `watchdog!WdLogSingleEntry5` at `0x1404036af`
- `watchdog!WdLogSingleEntry5` at `0x14040370a`
- `watchdog!WdLogSingleEntry5` at `0x1404036af`
- `watchdog!WdLogSingleEntry5` at `0x14040370a`
- `watchdog!WdLogSingleEntry1` at `0x140402bda`
- `watchdog!WdLogSingleEntry1` at `0x140402bda`

## string_xrefs

- `0x140402bf8`: `Driver failed call to DdiCreateAllocation. Status=0x%.8x`
- `0x1404034a5`: `Invalid private driver data size for NoKmdAccess`
- `0x140403488`: `Primary cannot be used with NoKmdAccess`
- `0x140403559`: `Device 0x%I64x: Driver tried to create non-cross adapter physically contiguous buffer, adapter 0x%I64x, returning 0x%I64x`
- `0x1404035bf`: `Device 0x%I64x: Driver tried to create capture buffer but didn't supply StopCapture, adapter 0x%I64x, returning 0x%I64x`
- `0x1404035f6`: `Device 0x%I64x: Driver tried to create overlay but didn't supply Overlay DDI, adapter 0x%I64x, returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall DXGDEVICE::CreateDriverAllocations(
        DXGDEVICE *this,
        struct _D3DKMT_CREATEALLOCATION *a2,
        struct _D3DDDI_ALLOCATIONINFO2 *a3,
        struct _DXGK_ALLOCATIONINFO *a4,
        struct DXGALLOCATION *a5,
        HANDLE **a6,
        void **a7,
        void **a8,
        D3DKMT_CREATESTANDARDALLOCATION *pStandardAllocation,
        const struct _D3DKM_CREATESTANDARDALLOCATION *a10,
        int a11,
        struct _D3DKMT_CREATESTANDARDALLOCATION *a12)
{
  ADAPTER_RENDER *v13; // rcx
  unsigned int NumAllocations; // ecx
  __int64 v17; // rsi
  struct _D3DDDI_ALLOCATIONINFO2 *v18; // r10
  __int64 v19; // rcx
  UINT PrivateDriverDataSize; // r9d
  __int64 v21; // r8
  void *v22; // rcx
  struct DXGRESOURCE *v23; // rsi
  int v24; // eax
  HANDLE *v25; // rdx
  UINT v26; // eax
  void *v27; // rax
  __int64 v28; // r12
  UINT i; // edx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // r13
  __int64 v34; // rsi
  __int64 v35; // r8
  struct DXGALLOCATION *v36; // r10
  UINT *pPrivateDriverData; // rdx
  bool v38; // zf
  UINT Value; // edx
  __int64 v40; // rax
  const wchar_t *v41; // r9
  __int64 v42; // rcx
  UINT v43; // eax
  UINT v44; // eax
  SIZE_T v45; // rax
  _DWORD *v46; // roff
  D3DKMT_CREATEALLOCATIONFLAGS Flags; // ecx
  __int64 v48; // rsi
  SIZE_T v49; // rdx
  SIZE_T v50; // r8
  unsigned int NumDifferentPhysicalAdapters; // eax
  DXGADAPTER *v52; // rcx
  unsigned int v53; // r11d
  int v54; // edx
  __int64 v55; // r10
  __int64 v56; // rcx
  UINT v57; // eax
  __int64 v58; // rdx
  __int64 (__fastcall **v59)(void *const, const struct _DXGKARG_STOPCAPTURE *); // r8
  __int64 v60; // r9
  __int64 v61; // r10
  __int64 v62; // r11
  struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D v63; // eax
  __int64 v64; // r8
  __int64 v65; // rcx
  __int64 v66; // rdx
  D3DKMT_CREATEALLOCATIONFLAGS v67; // eax
  int v68; // r9d
  __int64 v69; // r8
  unsigned int v70; // eax
  int v71; // ecx
  UINT v72; // edx
  UINT v73; // ecx
  int v74; // ecx
  __int64 v75; // rax
  int v76; // edx
  unsigned int v77; // edx
  UINT v78; // edx
  int v79; // ecx
  __int64 v80; // rax
  UINT v81; // edx
  D3DKMT_CREATEALLOCATIONFLAGS v82; // edx
  const wchar_t *v83; // r9
  HANDLE v84; // rcx
  HANDLE v85; // rcx
  struct _DXGKARG_CREATEALLOCATION Size; // [rsp+50h] [rbp-30h] BYREF
  struct DXGALLOCATION *v88; // [rsp+C8h] [rbp+48h]

  v13 = (ADAPTER_RENDER *)*((_QWORD *)this + 2);
  memset(&Size, 0, sizeof(Size));
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(v13) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3055;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      3055,
      0,
      0,
      0,
      0);
  }
  NumAllocations = a2->NumAllocations;
  v17 = 0;
  Size.pPrivateDriverData = 0;
  if ( NumAllocations )
  {
    v18 = a3;
    do
    {
      v19 = v17;
      if ( v18[v17].pPrivateDriverData )
      {
        PrivateDriverDataSize = v18[v19].PrivateDriverDataSize;
        v21 = (unsigned int)v17;
        a4[v21].PrivateDriverDataSize = PrivateDriverDataSize;
        if ( !a11 || (*(_DWORD *)&a2->Flags & 0x10000) != 0 )
        {
          a4[v21].pPrivateDriverData = v18[v19].pPrivateDriverData;
        }
        else
        {
          v22 = a7[v17];
          a4[v21].pPrivateDriverData = v22;
          memmove(v22, a8[v17], PrivateDriverDataSize);
          v18 = a3;
        }
      }
      NumAllocations = a2->NumAllocations;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < NumAllocations );
  }
  v23 = (struct DXGRESOURCE *)a6;
  Size.Flags.Value = 0;
  if ( a6 )
  {
    v24 = *((_DWORD *)a6 + 1);
    v25 = a6[7];
    Size.Flags.Value = 1;
    if ( (v24 & 1) != 0 )
      Size.hResource = v25[2];
    else
      Size.hResource = v25;
  }
  else
  {
    Size.hResource = 0;
  }
  v26 = a2->PrivateDriverDataSize;
  Size.NumAllocations = NumAllocations;
  Size.pAllocationInfo = a4;
  if ( v26 && a2->pStandardAllocation )
  {
    Size.PrivateDriverDataSize = v26;
    v27 = (void *)operator new[](v26, 1265072196, 258);
    Size.pPrivateDriverData = v27;
    if ( !v27 )
    {
      LODWORD(v28) = -1073741801;
      WdLogSingleEntry3(3, this, Size.PrivateDriverDataSize, -1073741801);
      WdLogGlobalForLineNumber = 3126;
      goto LABEL_181;
    }
    if ( !a11 )
      pStandardAllocation = a2->pStandardAllocation;
    memmove(v27, pStandardAllocation, Size.PrivateDriverDataSize);
  }
  else
  {
    Size.PrivateDriverDataSize = 0;
    Size.pPrivateDriverData = 0;
  }
  LODWORD(v28) = 0;
  if ( a10 )
  {
    if ( (*(_DWORD *)a10 & 0x3000) != 0 )
    {
      if ( DXGADAPTER::IsDxgmms2(*(DXGADAPTER **)(*((_QWORD *)this + 2) + 16LL)) )
      {
        for ( i = 0; i < a2->NumAllocations; Size.pAllocationInfo[v31].Flags.Value |= 0x400u )
          v31 = i++;
      }
    }
  }
  if ( (*(_DWORD *)&a2->Flags & 0x100000) == 0 )
  {
    v32 = ADAPTER_RENDER::DdiCreateAllocation(*((ADAPTER_RENDER **)this + 2), &Size);
    v28 = v32;
    if ( v32 < 0 )
    {
      WdLogSingleEntry1(2, v32);
      WdLogGlobalForLineNumber = 3172;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Driver failed call to DdiCreateAllocation. Status=0x%.8x",
        v28,
        0,
        0,
        0,
        0);
      goto LABEL_181;
    }
  }
  v33 = 0;
  v88 = a5;
  if ( !a2->NumAllocations )
  {
LABEL_169:
    if ( v23 )
    {
      if ( (*(_DWORD *)&a2->Flags & 2) != 0 )
      {
        v84 = *(HANDLE *)(*((_QWORD *)v23 + 7) + 16LL);
        if ( v84 && Size.hResource && Size.hResource != v84 )
        {
          WdLogSingleEntry5(0, 275, 7, 0, 0, 0);
          WdLogGlobalForLineNumber = 3621;
        }
        *(_QWORD *)(*((_QWORD *)v23 + 7) + 16LL) = Size.hResource;
      }
      else
      {
        v85 = (HANDLE)*((_QWORD *)v23 + 7);
        if ( v85 && Size.hResource && v85 != Size.hResource )
        {
          WdLogSingleEntry5(0, 275, 7, 0, 0, 0);
          WdLogGlobalForLineNumber = 3636;
        }
        *((_QWORD *)v23 + 7) = Size.hResource;
      }
    }
    goto LABEL_181;
  }
  while ( 1 )
  {
    v34 = (unsigned int)v33;
    if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 1) != 0 )
      *(&a4[v34].AllocationPriority + 1) &= ~0x40u;
    if ( (*((_DWORD *)DXGGLOBAL::GetGlobal() + 64) & 8) != 0
      && (*((_DWORD *)this + 122) & 8) != 0
      && !LOWORD(a4[v34].Size) )
    {
      *(&a4[v34].AllocationPriority + 1) |= 0x40u;
      a4[v34].Alignment = 0x10000;
    }
    if ( !_bittest((const signed __int32 *)&a2->Flags, 0x14u) )
    {
      v36 = v88;
      v35 = (unsigned int)v33;
      goto LABEL_47;
    }
    if ( a4[v34].PrivateDriverDataSize < 0x40 )
    {
      WdLogSingleEntry0(2);
      v40 = 3212;
      v41 = L"Invalid private driver data size for NoKmdAccess";
LABEL_160:
      WdLogGlobalForLineNumber = v40;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v41, v40, 0, 0, 0, 0);
      goto LABEL_162;
    }
    v35 = (unsigned int)v33;
    if ( (a3[v33].Flags.Value & 1) != 0 )
    {
      WdLogSingleEntry0(2);
      v40 = 3218;
      v41 = L"Primary cannot be used with NoKmdAccess";
      goto LABEL_160;
    }
    v36 = v88;
    *((_DWORD *)v88 + 18) |= 0x200000u;
    *(_DWORD *)(*((_QWORD *)v88 + 6) + 4LL) |= 0x10000000u;
    pPrivateDriverData = (UINT *)a4[v34].pPrivateDriverData;
    v38 = (*(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 5168LL) & 1) == 0;
    a4[v34].SupportedReadSegmentSet = pPrivateDriverData[8];
    if ( v38 )
    {
      a4[v34].Alignment = *pPrivateDriverData;
    }
    else
    {
      LOWORD(a4[v34].Alignment) = *(_WORD *)pPrivateDriverData;
      HIWORD(a4[v34].Alignment) = *((_WORD *)pPrivateDriverData + 1);
    }
    a4[v34].Size = pPrivateDriverData[2];
    a4[v34].PitchAlignedSize = pPrivateDriverData[4];
    a4[v34].HintedBank.Value = pPrivateDriverData[6];
    a4[v34].PreferredSegment.Value = pPrivateDriverData[7];
    a4[v34].SupportedWriteSegmentSet = pPrivateDriverData[9];
    a4[v34].EvictionSegmentSet = pPrivateDriverData[10];
    a4[v34].MaximumRenamingListLength = pPrivateDriverData[11];
    a4[v34].Flags.Value = pPrivateDriverData[12];
    a4[v34].AllocationPriority = pPrivateDriverData[13];
    *(&a4[v34].AllocationPriority + 1) = pPrivateDriverData[15];
LABEL_47:
    *(_QWORD *)(*((_QWORD *)v36 + 6) + 16LL) = a4[v34].hAllocation;
    *(_QWORD *)(*((_QWORD *)v36 + 6) + 24LL) = a4[v34].pAllocationUsageHint;
    *(_DWORD *)(*((_QWORD *)v36 + 6) + 4LL) = *(_DWORD *)(*((_QWORD *)v36 + 6) + 4LL) & 0xFFFFF7FF
                                            | ((a4[v34].Flags.Value & 0x30) != 0 ? 0x800 : 0);
    *(_DWORD *)(*((_QWORD *)v36 + 6) + 4LL) ^= (*(_DWORD *)(*((_QWORD *)v36 + 6) + 4LL)
                                              ^ (a4[v34].Flags.Value << 17))
                                             & 0x80000;
    a4[v34].Flags.Value &= 0x807FFFFu;
    Value = a4[v34].Flags.Value;
    if ( *(int *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 2864LL) < 12288 )
    {
      if ( !_bittest((const signed __int32 *)&a2->Flags, 0x14u) )
        *(&a4[v34].AllocationPriority + 1) = 0;
    }
    else if ( *(&a4[v34].AllocationPriority + 1) >= 0x80 )
    {
      WdLogSingleEntry0(2);
      v40 = 3285;
      v41 = L"Flags2.Reserved is not zero";
      goto LABEL_160;
    }
    v42 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
    if ( (*(_DWORD *)(v42 + 2596) & 0x40) != 0 && *(_BYTE *)(v42 + 3165) )
    {
      Value |= 0x8000u;
      a4[v34].Flags.Value = Value;
    }
    if ( (Value & 0x8000) != 0 && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3166LL) )
    {
      Value |= 0x10000u;
      a4[v34].Flags.Value = Value;
    }
    if ( a10 )
    {
      if ( (*(_DWORD *)a10 & 0x1000) != 0 )
        a4[v34].Flags.Value = Value | 0x20000;
      v43 = *((_DWORD *)a10 + 96);
      if ( v43 )
      {
        a4[v34].SupportedWriteSegmentSet = v43;
        a4[v34].PreferredSegment.Value = *((_DWORD *)a10 + 97);
      }
      v44 = *((_DWORD *)a10 + 98);
      if ( v44 )
        a4[v34].Alignment = v44;
      if ( (*(_DWORD *)a10 & 0x2000) != 0 )
        *(_DWORD *)(*((_QWORD *)a5 + 12 * v35 + 6) + 4LL) |= 0x8000u;
      v45 = *((_QWORD *)a10 + 50);
      if ( v45 )
        a4[v34].Size = v45;
      if ( (*(_DWORD *)a10 & 0x8000) != 0 )
        a4[v34].Flags.Value |= 0x8000u;
      if ( *((_DWORD *)a10 + 4) == 5 )
      {
        v46 = (_DWORD *)(*((_QWORD *)a5 + 12 * v35 + 6) + 4LL);
        *v46 |= 0x10000u;
        a4[(unsigned int)v33].Flags.Value = a4[v35].Flags.Value | 0x8000;
      }
    }
    Flags = a2->Flags;
    if ( (*(_DWORD *)&Flags & 0x10000) != 0 )
    {
      v48 = (unsigned int)v33;
      v49 = a4[v48].Size;
      v50 = a12->ExistingHeapData.Size;
      if ( v49 != v50 )
      {
        WdLogSingleEntry3(2, v49, v50, -1073741811);
        WdLogGlobalForLineNumber = 3350;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Mismatch between Driver returned allocation size:0x%I64x and ExistingSysMem buffer size:0xI64x, "
                         "returning 0x%I64x",
          a4[v48].Size,
          a12->ExistingHeapData.Size,
          -1073741811,
          0,
          0);
LABEL_162:
        LODWORD(v28) = -1073741811;
        goto LABEL_181;
      }
      if ( (*(_DWORD *)&Flags & 0x20020) != 0 )
        goto LABEL_79;
    }
    if ( a10 && (*((_QWORD *)a10 + 42) || *((_QWORD *)a10 + 41)) )
LABEL_79:
      a4[(unsigned int)v33].Flags.Value |= 1u;
    if ( *((_DWORD *)this + 116) == 2 )
    {
      NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(*(DXGADAPTER **)(*((_QWORD *)this + 2)
                                                                                                + 16LL));
      if ( NumDifferentPhysicalAdapters > v53 && !DXGADAPTER::ReplicateGdiContent(v52) && (a3[v33].Flags.Value & 1) == 0 )
        a4[(unsigned int)v33].MaximumRenamingListLength = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3276LL);
    }
    if ( DXGADAPTER::IsDxgmms2(*(DXGADAPTER **)(*((_QWORD *)this + 2) + 16LL)) )
    {
      v56 = (unsigned int)v33;
      v57 = v54 ^ (v54 ^ (a4[v56].MaximumRenamingListLength << 12)) & 0x3F000;
      v58 = *(_QWORD *)(v55 + 48);
      *(_DWORD *)(v55 + 72) = v57;
      *(_DWORD *)(v58 + 4) ^= (*(_DWORD *)(v58 + 4) ^ (a4[v56].MaximumRenamingListLength << 21)) & 0x7E00000;
    }
    else
    {
      *(_DWORD *)(v55 + 72) = v54 & 0xFFFC0FFF;
    }
    if ( DXGADAPTER::IsDxgmms2(*(DXGADAPTER **)(*((_QWORD *)this + 2) + 16LL))
      && (*(_DWORD *)&a2->Flags & 0x80800) == 0x80000 )
    {
      WdLogSingleEntry3(2, this, v59, -1073741637);
      v83 = L"Device 0x%I64x: Driver tried to create non-cross adapter physically contiguous buffer, adapter 0x%I64x, returning 0x%I64x";
      WdLogGlobalForLineNumber = 3406;
      goto LABEL_165;
    }
    v63 = (struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D)a4[(unsigned int)v33].Flags.Value;
    if ( (*(_WORD *)&v63 & 0x200) != 0 && v59[86] == ADAPTER_RENDER::DefaultDdiStopCapture )
    {
      WdLogSingleEntry3(2, this, v59, -1073741637);
      v83 = L"Device 0x%I64x: Driver tried to create capture buffer but didn't supply StopCapture, adapter 0x%I64x, returning 0x%I64x";
      WdLogGlobalForLineNumber = 3422;
      goto LABEL_165;
    }
    if ( (*(_WORD *)&v63 & 0x100) != 0
      && (!DXGADAPTER::IsFullWDDMAdapter((DXGADAPTER *)v59)
       || *(__int64 (__fastcall **)(void *const, struct _DXGKARG_CREATEOVERLAY *))(v64 + 704) == ADAPTER_RENDER::DefaultDdiCreateOverlay
       || *(__int64 (__fastcall **)(void *const))(v64 + 768) == ADAPTER_RENDER::DefaultDdiDestroyOverlay
       || *(__int64 (__fastcall **)(void *const, const struct _DXGKARG_FLIPOVERLAY *))(v64 + 760) == ADAPTER_RENDER::DefaultDdiFlipOverlay
       || *(__int64 (__fastcall **)(void *const, const struct _DXGKARG_UPDATEOVERLAY *))(v64 + 752) == ADAPTER_RENDER::DefaultDdiUpdateOverlay) )
    {
      break;
    }
    v65 = *(_QWORD *)(v61 + 48);
    if ( !*(_QWORD *)(v65 + 16) && (*(_DWORD *)&a2->Flags & 0x100000) == 0 )
    {
      WdLogSingleEntry3(2, this, v61, -1073741811);
      WdLogGlobalForLineNumber = 3448;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Device 0x%I64x: Driver did not return an allocation handle for 0x%I64x, returning 0x%I64x",
        (__int64)this,
        (__int64)v88,
        -1073741811,
        0,
        0);
      goto LABEL_162;
    }
    v66 = 96 * v33;
    if ( (*(_DWORD *)(96 * v33 + v62 + 32) & 2) != 0 )
      *(_DWORD *)(v65 + 4) |= 0x1000u;
    if ( (*(_DWORD *)(v66 + v62 + 32) & 1) != 0 && (a4[(unsigned int)v33].Flags.Value & 0x100) == 0 )
    {
      v67 = a2->Flags;
      v68 = *(_DWORD *)(v66 + v62 + 28);
      if ( (*(_BYTE *)&v67 & 2) != 0 )
      {
        v74 = *((_DWORD *)this + 116);
        if ( v74 == 2 )
        {
          *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 2u;
          v73 = a4[(unsigned int)v33].Flags.Value | 0x40000000;
          v75 = (unsigned int)v33;
          goto LABEL_131;
        }
        if ( (*(_WORD *)&v67 & 0x800) != 0 )
        {
          if ( (*(_WORD *)&v67 & 0x400) != 0 )
          {
            if ( v74 == 1 && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3067LL) )
              v76 = 0x2000;
            else
              v76 = 0;
            *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) = v76 | *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) & 0xFFFFDFFF;
          }
          else
          {
            *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 1u;
            a4[(unsigned int)v33].Flags.Value |= 0x80000u;
          }
        }
        else if ( v74 == 1 )
        {
          if ( (*(_WORD *)&v67 & 0x400) != 0 )
          {
            if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3067LL) )
              *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 0x2000u;
          }
          else
          {
            *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 1u;
          }
        }
        v69 = (unsigned int)v33;
        v77 = 0;
        if ( *((_DWORD *)this + 116) == 1 )
          v77 = 0x80000000;
        v78 = a4[(unsigned int)v33].Flags.Value & 0x7FFFFFFF | v77;
        v79 = 0;
        a4[(unsigned int)v33].Flags.Value = v78;
        if ( !*((_DWORD *)this + 116) )
          v79 = 0x40000000;
        v73 = v78 & 0xBFFFFFFF | v79 | 0x20000000;
      }
      else
      {
        v69 = (unsigned int)v33;
        *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 1u;
        v70 = 0;
        if ( *((_DWORD *)this + 116) == 1 )
          v70 = 0x80000000;
        v71 = 0;
        v72 = v70 | a4[(unsigned int)v33].Flags.Value & 0x7FFFFFFF;
        a4[(unsigned int)v33].Flags.Value = v72;
        if ( !*((_DWORD *)this + 116) )
          v71 = 0x40000000;
        v73 = v72 & 0xBFFFFFFF | v71;
      }
      v75 = v69;
LABEL_131:
      a4[v75].Flags.Value = v73;
      if ( (*(_DWORD *)(*((_QWORD *)this + 5) + 408LL) & 0x100) == 0
        && *((_QWORD *)this + 237) != *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) )
      {
        *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 4u;
        v80 = (unsigned int)v33;
        v81 = a4[v80].Flags.Value & 0x3DFFFFFF | 0x2000000;
        a4[v80].Flags.Value = v81;
        if ( (*(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) & 2) != 0 )
          a4[(unsigned int)v33].Flags.Value = v81 | 0x20400000;
      }
      *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) ^= ((unsigned __int16)*(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL)
                                                 ^ (unsigned __int16)((_WORD)v68 << 6))
                                                & 0x3C0;
      goto LABEL_147;
    }
    v82 = a2->Flags;
    if ( (*(_BYTE *)&v82 & 2) != 0 )
    {
      a4[(unsigned int)v33].Flags.Value |= 0x20000000u;
      v82 = a2->Flags;
    }
    if ( *((_DWORD *)this + 116) == 2
      && *((_QWORD *)this + 237) != *(_QWORD *)(*((_QWORD *)this + 2) + 16LL)
      && (*(_DWORD *)(*((_QWORD *)this + 5) + 408LL) & 0x100) == 0
      && v60
      && *(_QWORD *)(v60 + 32)
      && *(_QWORD *)(v60 + 40)
      && *(_DWORD *)(v60 + 16) == 2
      && (*(_BYTE *)&v82 & 0x22) == 2 )
    {
      *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 2u;
      *(_DWORD *)(*(_QWORD *)(v61 + 48) + 4LL) |= 4u;
      a4[(unsigned int)v33].Flags.Value = a4[(unsigned int)v33].Flags.Value & 0x3DBFFFFF | 0x2400000;
    }
LABEL_147:
    v23 = (struct DXGRESOURCE *)a6;
    if ( a6 && (*((_DWORD *)a6 + 1) & 8) != 0 )
      a4[(unsigned int)v33].Flags.Value |= 0x88000u;
    if ( (*(_DWORD *)&a2->Flags & 0x1800) != 0 )
      a4[(unsigned int)v33].Flags.Value |= 0x20100000u;
    if ( (*(_DWORD *)&a2->Flags & 0x400) != 0 )
      a4[(unsigned int)v33].Flags.Value |= 0x200000u;
    if ( (*(_DWORD *)&a2->Flags & 0x400000) != 0 )
      *(&a4[(unsigned int)v33].AllocationPriority + 1) |= 2u;
    v33 = (unsigned int)(v33 + 1);
    if ( (unsigned int)v33 >= a2->NumAllocations )
      goto LABEL_169;
    v88 = *(struct DXGALLOCATION **)(v61 + 64);
  }
  WdLogSingleEntry3(2, this, *(_QWORD *)(*((_QWORD *)this + 2) + 16LL), -1073741637);
  v83 = L"Device 0x%I64x: Driver tried to create overlay but didn't supply Overlay DDI, adapter 0x%I64x, returning 0x%I64x";
  WdLogGlobalForLineNumber = 3437;
LABEL_165:
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (_DWORD)v83,
    (__int64)this,
    *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
    -1073741637,
    0,
    0);
  LODWORD(v28) = -1073741637;
LABEL_181:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete((void *)Size.pPrivateDriverData);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x14040297c  mov     [rsp-38h+arg_18], rbx
0x140402981  mov     [rsp-38h+arg_10], r8
0x140402986  push    rbp
0x140402987  push    rsi
0x140402988  push    rdi
0x140402989  push    r12
0x14040298b  push    r13
0x14040298d  push    r14
0x14040298f  push    r15
0x140402991  mov     rbp, rsp
0x140402994  sub     rsp, 80h
0x14040299b  mov     r12, [rbp+arg_38]
0x14040299f  xorps   xmm0, xmm0
0x1404029a2  mov     r13, [rbp+arg_30]
0x1404029a6  mov     rdi, rcx
0x1404029a9  mov     rcx, [rcx+10h]; this
0x1404029ad  xor     eax, eax
0x1404029af  movups  xmmword ptr [rbp+Size], xmm0
0x1404029b3  mov     [rbp+var_10], rax
0x1404029b7  mov     rbx, r9
0x1404029ba  movups  [rbp+var_20], xmm0
0x1404029be  mov     r15, rdx
0x1404029c1  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x1404029c6  mov     r8d, 1
0x1404029cc  test    al, al
0x1404029ce  jnz     short loc_140402A23
0x1404029d0  mov     ecx, r8d
0x1404029d3  call    cs:__imp_WdLogSingleEntry0
0x1404029da  nop     dword ptr [rax+rax+00h]
0x1404029df  xor     r11d, r11d
0x1404029e2  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x1404029e9  mov     [rsp+80h+var_40], r11
0x1404029ee  mov     eax, 0BEFh
0x1404029f3  mov     [rsp+80h+var_48], r11
0x1404029f8  or      r8d, 0FFFFFFFFh
0x1404029fc  mov     [rsp+80h+var_50], r11
0x140402a01  mov     edx, 40002h
0x140402a06  mov     [rsp+80h+var_58], r11
0x140402a0b  xor     ecx, ecx
0x140402a0d  mov     [rsp+80h+var_60], rax
0x140402a12  mov     cs:WdLogGlobalForLineNumber, eax
0x140402a18  call    DxgkLogInternalTriageEvent
0x140402a1d  mov     r8d, 1
0x140402a23  mov     ecx, [r15+2Ch]
0x140402a27  xor     esi, esi
0x140402a29  mov     r14d, [rbp+arg_50]
0x140402a30  mov     [rbp+Size], 0
0x140402a38  test    ecx, ecx
0x140402a3a  jz      short loc_140402AA4
0x140402a3c  mov     r10, [rbp+arg_10]
0x140402a40  lea     rcx, [rsi+rsi*2]
0x140402a44  mov     edx, esi
0x140402a46  shl     rcx, 5
0x140402a4a  cmp     qword ptr [rcx+r10+10h], 0
0x140402a50  jz      short loc_140402A99
0x140402a52  mov     r9d, [rcx+r10+18h]
0x140402a57  imul    r8, rdx, 58h ; 'X'
0x140402a5b  mov     [r8+rbx+8], r9d
0x140402a60  test    r14d, r14d
0x140402a63  jz      short loc_140402A8A
0x140402a65  test    dword ptr [r15+38h], 10000h
0x140402a6d  jnz     short loc_140402A8A
0x140402a6f  mov     rcx, [r13+rsi*8+0]; void *
0x140402a74  mov     [r8+rbx], rcx
0x140402a78  mov     r8d, r9d; Size
0x140402a7b  mov     rdx, [r12+rsi*8]; Src
0x140402a7f  call    memmove
0x140402a84  mov     r10, [rbp+arg_10]
0x140402a88  jmp     short loc_140402A93
0x140402a8a  mov     rax, [rcx+r10+10h]
0x140402a8f  mov     [r8+rbx], rax
0x140402a93  mov     r8d, 1
0x140402a99  mov     ecx, [r15+2Ch]
0x140402a9d  add     esi, r8d
0x140402aa0  cmp     esi, ecx
0x140402aa2  jb      short loc_140402A40
0x140402aa4  mov     rsi, [rbp+arg_28]
0x140402aa8  mov     dword ptr [rbp+var_10], 0
0x140402aaf  test    rsi, rsi
0x140402ab2  jz      short loc_140402AD4
0x140402ab4  mov     eax, [rsi+4]
0x140402ab7  mov     rdx, [rsi+38h]
0x140402abb  mov     dword ptr [rbp+var_10], r8d
0x140402abf  test    r8b, al
0x140402ac2  jz      short loc_140402ACE
0x140402ac4  mov     rax, [rdx+10h]
0x140402ac8  mov     qword ptr [rbp+var_20+8], rax
0x140402acc  jmp     short loc_140402ADC
0x140402ace  mov     qword ptr [rbp+var_20+8], rdx
0x140402ad2  jmp     short loc_140402ADC
0x140402ad4  mov     qword ptr [rbp+var_20+8], 0
0x140402adc  mov     eax, [r15+28h]
0x140402ae0  mov     dword ptr [rbp+Size+0Ch], ecx
0x140402ae3  mov     qword ptr [rbp+var_20], rbx
0x140402ae7  test    eax, eax
0x140402ae9  jz      short loc_140402B5D
0x140402aeb  cmp     qword ptr [r15+20h], 0
0x140402af0  jz      short loc_140402B5D
0x140402af2  mov     ecx, eax
0x140402af4  mov     dword ptr [rbp+Size+8], eax
0x140402af7  mov     edx, 4B677844h
0x140402afc  mov     r8d, 102h
0x140402b02  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140402b07  mov     [rbp+Size], rax
0x140402b0b  test    rax, rax
0x140402b0e  jnz     short loc_140402B3F
0x140402b10  mov     r8d, dword ptr [rbp+Size+8]
0x140402b14  lea     ecx, [rax+3]
0x140402b17  mov     r12, 0FFFFFFFFC0000017h
0x140402b1e  mov     rdx, rdi
0x140402b21  mov     r9, r12
0x140402b24  call    cs:__imp_WdLogSingleEntry3
0x140402b2b  nop     dword ptr [rax+rax+00h]
0x140402b30  mov     cs:WdLogGlobalForLineNumber, 0C36h
0x140402b3a  jmp     loc_140403728
0x140402b3f  mov     r8d, dword ptr [rbp+Size+8]; Size
0x140402b43  mov     rcx, rax; void *
0x140402b46  mov     rdx, [rbp+arg_40]
0x140402b4d  test    r14d, r14d
0x140402b50  jnz     short loc_140402B56
0x140402b52  mov     rdx, [r15+20h]; Src
0x140402b56  call    memmove
0x140402b5b  jmp     short loc_140402B6C
0x140402b5d  mov     dword ptr [rbp+Size+8], 0
0x140402b64  mov     [rbp+Size], 0
0x140402b6c  mov     rax, [rbp+arg_48]
0x140402b73  xor     r12d, r12d
0x140402b76  test    rax, rax
0x140402b79  jz      short loc_140402BB4
0x140402b7b  test    dword ptr [rax], 3000h
0x140402b81  jz      short loc_140402BB4
0x140402b83  mov     rcx, [rdi+10h]
0x140402b87  mov     rcx, [rcx+10h]; this
0x140402b8b  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x140402b90  test    al, al
0x140402b92  jz      short loc_140402BB4
0x140402b94  xor     edx, edx
0x140402b96  cmp     [r15+2Ch], edx
0x140402b9a  jbe     short loc_140402BB4
0x140402b9c  mov     eax, edx
0x140402b9e  inc     edx
0x140402ba0  imul    rcx, rax, 58h ; 'X'
0x140402ba4  mov     rax, qword ptr [rbp+var_20]
0x140402ba8  bts     dword ptr [rcx+rax+40h], 0Ah
0x140402bae  cmp     edx, [r15+2Ch]
0x140402bb2  jb      short loc_140402B9C
0x140402bb4  test    dword ptr [r15+38h], 100000h
0x140402bbc  jnz     short loc_140402C28
0x140402bbe  mov     rcx, [rdi+10h]; this
0x140402bc2  lea     rdx, [rbp+Size]; struct _DXGKARG_CREATEALLOCATION *
0x140402bc6  call    ?DdiCreateAllocation@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_CREATEALLOCATION@@@Z; ADAPTER_RENDER::DdiCreateAllocation(_DXGKARG_CREATEALLOCATION *)
0x140402bcb  movsxd  r12, eax
0x140402bce  test    eax, eax
0x140402bd0  jns     short loc_140402C28
0x140402bd2  mov     rdx, r12
0x140402bd5  mov     ecx, 2
0x140402bda  call    cs:__imp_WdLogSingleEntry1
0x140402be1  nop     dword ptr [rax+rax+00h]
0x140402be6  xor     r11d, r11d
0x140402be9  mov     cs:WdLogGlobalForLineNumber, 0C64h
0x140402bf3  mov     [rsp+80h+var_40], r11
0x140402bf8  lea     r9, aDriverFailedCa; "Driver failed call to DdiCreateAllocati"...
0x140402bff  mov     [rsp+80h+var_48], r11
0x140402c04  or      r8d, 0FFFFFFFFh
0x140402c08  mov     [rsp+80h+var_50], r11
0x140402c0d  mov     edx, 40000h
0x140402c12  mov     [rsp+80h+var_58], r11
0x140402c17  xor     ecx, ecx
0x140402c19  mov     [rsp+80h+var_60], r12
0x140402c1e  call    DxgkLogInternalTriageEvent
0x140402c23  jmp     loc_140403728
0x140402c28  mov     rax, [rbp+arg_20]
0x140402c2c  xor     r13d, r13d
0x140402c2f  mov     [rbp+arg_8], rax
0x140402c33  lea     r14d, [r13+2]
0x140402c37  cmp     [r15+2Ch], r13d
0x140402c3b  jbe     loc_140403662
0x140402c41  mov     eax, r13d
0x140402c44  imul    rsi, rax, 58h ; 'X'
0x140402c48  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140402c4d  mov     ecx, [rax+100h]
0x140402c53  test    cl, 1
0x140402c56  jz      short loc_140402C5D
0x140402c58  and     dword ptr [rsi+rbx+54h], 0FFFFFFBFh
0x140402c5d  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140402c62  mov     ecx, [rax+100h]
0x140402c68  test    cl, 8
0x140402c6b  jz      short loc_140402C8C
0x140402c6d  mov     eax, [rdi+1E8h]
0x140402c73  test    al, 8
0x140402c75  jz      short loc_140402C8C
0x140402c77  cmp     word ptr [rsi+rbx+10h], 0
0x140402c7d  jnz     short loc_140402C8C
0x140402c7f  or      dword ptr [rsi+rbx+54h], 40h
0x140402c84  mov     dword ptr [rsi+rbx+0Ch], 10000h
0x140402c8c  bt      dword ptr [r15+38h], 14h
0x140402c92  jnb     loc_140402D5F
0x140402c98  cmp     dword ptr [rsi+rbx+8], 40h ; '@'
0x140402c9d  jb      loc_140403491
0x140402ca3  mov     rcx, [rbp+arg_10]
0x140402ca7  lea     rax, ds:0[r13*2]
0x140402caf  add     rax, r13
0x140402cb2  mov     r8d, r13d
0x140402cb5  shl     rax, 5
0x140402cb9  mov     r11d, 1
0x140402cbf  mov     eax, [rax+rcx+20h]
0x140402cc3  test    r11b, al
0x140402cc6  jnz     loc_140403474
0x140402ccc  mov     r10, [rbp+arg_8]
0x140402cd0  bts     dword ptr [r10+48h], 15h
0x140402cd6  mov     rax, [r10+30h]
0x140402cda  bts     dword ptr [rax+4], 1Ch
0x140402cdf  mov     rax, [rdi+10h]
0x140402ce3  mov     rdx, [rsi+rbx]
0x140402ce7  mov     rcx, [rax+10h]
0x140402ceb  mov     eax, [rdx+20h]
0x140402cee  test    [rcx+1430h], r11w
0x140402cf6  mov     [rsi+rbx+28h], eax
0x140402cfa  jz      short loc_140402D0F
0x140402cfc  movzx   eax, word ptr [rdx]
0x140402cff  mov     [rsi+rbx+0Ch], ax
0x140402d04  movzx   eax, word ptr [rdx+2]
0x140402d08  mov     [rsi+rbx+0Eh], ax
0x140402d0d  jmp     short loc_140402D15
0x140402d0f  mov     eax, [rdx]
0x140402d11  mov     [rsi+rbx+0Ch], eax
0x140402d15  mov     eax, [rdx+8]
0x140402d18  mov     [rsi+rbx+10h], rax
0x140402d1d  mov     eax, [rdx+10h]
0x140402d20  mov     [rsi+rbx+18h], rax
0x140402d25  mov     eax, [rdx+18h]
0x140402d28  mov     [rsi+rbx+20h], eax
0x140402d2c  mov     eax, [rdx+1Ch]
0x140402d2f  mov     [rsi+rbx+24h], eax
0x140402d33  mov     eax, [rdx+24h]
0x140402d36  mov     [rsi+rbx+2Ch], eax
0x140402d3a  mov     eax, [rdx+28h]
0x140402d3d  mov     [rsi+rbx+30h], eax
0x140402d41  mov     eax, [rdx+2Ch]
0x140402d44  mov     [rsi+rbx+34h], eax
0x140402d48  mov     eax, [rdx+30h]
0x140402d4b  mov     [rsi+rbx+40h], eax
0x140402d4f  mov     eax, [rdx+34h]
0x140402d52  mov     [rsi+rbx+50h], eax
0x140402d56  mov     eax, [rdx+3Ch]
0x140402d59  mov     [rsi+rbx+54h], eax
0x140402d5d  jmp     short loc_140402D6C
0x140402d5f  mov     r10, [rbp+arg_8]
0x140402d63  mov     r11d, 1
0x140402d69  mov     r8d, r13d
0x140402d6c  mov     rcx, [r10+30h]
0x140402d70  mov     rax, [rsi+rbx+38h]
0x140402d75  mov     [rcx+10h], rax
0x140402d79  mov     rcx, [r10+30h]
0x140402d7d  mov     rax, [rsi+rbx+48h]
0x140402d82  mov     [rcx+18h], rax
0x140402d86  mov     eax, [rsi+rbx+40h]
0x140402d8a  mov     rdx, [r10+30h]
0x140402d8e  and     al, 30h
0x140402d90  neg     al
0x140402d92  sbb     ecx, ecx
0x140402d94  mov     eax, [rdx+4]
0x140402d97  and     ecx, 800h
0x140402d9d  btr     eax, 0Bh
0x140402da1  or      ecx, eax
0x140402da3  mov     [rdx+4], ecx
0x140402da6  mov     rdx, [r10+30h]
0x140402daa  mov     ecx, [rsi+rbx+40h]
0x140402dae  shl     ecx, 11h
0x140402db1  mov     eax, [rdx+4]
0x140402db4  xor     ecx, eax
0x140402db6  and     ecx, 80000h
0x140402dbc  xor     ecx, eax
0x140402dbe  mov     [rdx+4], ecx
0x140402dc1  and     dword ptr [rsi+rbx+40h], 807FFFFh
0x140402dc9  mov     rax, [rdi+10h]
0x140402dcd  mov     edx, [rsi+rbx+40h]
0x140402dd1  mov     rcx, [rax+10h]
0x140402dd5  cmp     dword ptr [rcx+0B30h], 3000h
0x140402ddf  jl      short loc_140402E0B
0x140402de1  cmp     dword ptr [rsi+rbx+54h], 80h
0x140402de9  jb      short loc_140402E1B
0x140402deb  mov     ecx, r14d
0x140402dee  call    cs:__imp_WdLogSingleEntry0
0x140402df5  nop     dword ptr [rax+rax+00h]
0x140402dfa  mov     eax, 0CD5h
0x140402dff  lea     r9, aFlags2Reserved; "Flags2.Reserved is not zero"
0x140402e06  jmp     loc_1404034AC
0x140402e0b  bt      dword ptr [r15+38h], 14h
0x140402e11  jb      short loc_140402E1B
0x140402e13  mov     dword ptr [rsi+rbx+54h], 0
0x140402e1b  mov     rax, [rdi+10h]
0x140402e1f  mov     rcx, [rax+10h]
0x140402e23  mov     eax, [rcx+0A24h]
0x140402e29  test    al, 40h
0x140402e2b  jz      short loc_140402E3E
0x140402e2d  cmp     byte ptr [rcx+0C5Dh], 0
0x140402e34  jz      short loc_140402E3E
0x140402e36  bts     edx, 0Fh
0x140402e3a  mov     [rsi+rbx+40h], edx
  ... truncated ...
```
