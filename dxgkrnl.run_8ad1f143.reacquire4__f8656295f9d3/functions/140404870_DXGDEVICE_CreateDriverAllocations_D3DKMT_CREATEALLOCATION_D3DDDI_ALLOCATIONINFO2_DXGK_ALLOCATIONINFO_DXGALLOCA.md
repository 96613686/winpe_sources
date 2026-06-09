# DXGDEVICE::CreateDriverAllocations(_D3DKMT_CREATEALLOCATION *,_D3DDDI_ALLOCATIONINFO2 *,_DXGK_ALLOCATIONINFO *,DXGALLOCATION *,DXGRESOURCE *,void * *,void * *,void *,_D3DKM_CREATESTANDARDALLOCATION const *,int,_D3DKMT_CREATESTANDARDALLOCATION *)

- ea: `0x140404870`
- end: `0x140405644`
- name: `?CreateDriverAllocations@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@PEAU_DXGK_ALLOCATIONINFO@@PEAVDXGALLOCATION@@PEAVDXGRESOURCE@@PEAPEAX5PEAXPEBU_D3DKM_CREATESTANDARDALLOCATION@@HPEAU_D3DKMT_CREATESTANDARDALLOCATION@@@Z`
- size: `3540`
- prototype: `__int64 __fastcall(DXGDEVICE *__hidden this, struct _D3DKMT_CREATEALLOCATION *, struct _D3DDDI_ALLOCATIONINFO2 *, struct _DXGK_ALLOCATIONINFO *, struct DXGALLOCATION *, struct DXGRESOURCE *, void **, void **, void *, const struct _D3DKM_CREATESTANDARDALLOCATION *, int, struct _D3DKMT_CREATESTANDARDALLOCATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x140377040`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x14001b890`
- `0x14002d9f0`
- `0x14002fdc0`
- `0x140033bb0`
- `0x140050284`
- `0x1400a0240`
- `0x14034599c`
- `0x1403c2b10`
- `0x140404870`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x140404a18`
- `watchdog!WdLogSingleEntry3` at `0x1404053e7`
- `watchdog!WdLogSingleEntry3` at `0x140405441`
- `watchdog!WdLogSingleEntry3` at `0x1404054a7`
- `watchdog!WdLogSingleEntry3` at `0x1404054de`
- `watchdog!WdLogSingleEntry3` at `0x140405510`
- `watchdog!WdLogSingleEntry3` at `0x140404a18`
- `watchdog!WdLogSingleEntry3` at `0x1404053e7`
- `watchdog!WdLogSingleEntry3` at `0x140405441`
- `watchdog!WdLogSingleEntry3` at `0x1404054a7`
- `watchdog!WdLogSingleEntry3` at `0x1404054de`
- `watchdog!WdLogSingleEntry3` at `0x140405510`
- `watchdog!WdLogSingleEntry0` at `0x1404048c7`
- `watchdog!WdLogSingleEntry0` at `0x140404ce2`
- `watchdog!WdLogSingleEntry0` at `0x14040536b`
- `watchdog!WdLogSingleEntry0` at `0x140405388`
- `watchdog!WdLogSingleEntry0` at `0x1404048c7`
- `watchdog!WdLogSingleEntry0` at `0x140404ce2`
- `watchdog!WdLogSingleEntry0` at `0x14040536b`
- `watchdog!WdLogSingleEntry0` at `0x140405388`
- `watchdog!WdLogSingleEntry5` at `0x1404055a3`
- `watchdog!WdLogSingleEntry5` at `0x1404055fe`
- `watchdog!WdLogSingleEntry5` at `0x1404055a3`
- `watchdog!WdLogSingleEntry5` at `0x1404055fe`
- `watchdog!WdLogSingleEntry1` at `0x140404ace`
- `watchdog!WdLogSingleEntry1` at `0x140404ace`

## string_xrefs

- `0x140404aec`: `Driver failed call to DdiCreateAllocation. Status=0x%.8x`
- `0x140405399`: `Invalid private driver data size for NoKmdAccess`
- `0x14040537c`: `Primary cannot be used with NoKmdAccess`
- `0x14040544d`: `Device 0x%I64x: Driver tried to create non-cross adapter physically contiguous buffer, adapter 0x%I64x, returning 0x%I64x`
- `0x1404054b3`: `Device 0x%I64x: Driver tried to create capture buffer but didn't supply StopCapture, adapter 0x%I64x, returning 0x%I64x`
- `0x1404054ea`: `Device 0x%I64x: Driver tried to create overlay but didn't supply Overlay DDI, adapter 0x%I64x, returning 0x%I64x`

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
      WdLogSingleEntry1(2);
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
    v38 = (*(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 5152LL) & 1) == 0;
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
    if ( *(int *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 2848LL) < 12288 )
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
    if ( (*(_DWORD *)(v42 + 2580) & 0x40) != 0 && *(_BYTE *)(v42 + 3149) )
    {
      Value |= 0x8000u;
      a4[v34].Flags.Value = Value;
    }
    if ( (Value & 0x8000) != 0 && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3150LL) )
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
        a4[(unsigned int)v33].MaximumRenamingListLength = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3260LL);
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
            if ( v74 == 1 && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3051LL) )
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
            if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 3051LL) )
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
0x140404870  mov     [rsp-38h+arg_18], rbx
0x140404875  mov     [rsp-38h+arg_10], r8
0x14040487a  push    rbp
0x14040487b  push    rsi
0x14040487c  push    rdi
0x14040487d  push    r12
0x14040487f  push    r13
0x140404881  push    r14
0x140404883  push    r15
0x140404885  mov     rbp, rsp
0x140404888  sub     rsp, 80h
0x14040488f  mov     r12, [rbp+arg_38]
0x140404893  xorps   xmm0, xmm0
0x140404896  mov     r13, [rbp+arg_30]
0x14040489a  mov     rdi, rcx
0x14040489d  mov     rcx, [rcx+10h]; this
0x1404048a1  xor     eax, eax
0x1404048a3  movups  xmmword ptr [rbp+Size], xmm0
0x1404048a7  mov     [rbp+var_10], rax
0x1404048ab  mov     rbx, r9
0x1404048ae  movups  [rbp+var_20], xmm0
0x1404048b2  mov     r15, rdx
0x1404048b5  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x1404048ba  mov     r8d, 1
0x1404048c0  test    al, al
0x1404048c2  jnz     short loc_140404917
0x1404048c4  mov     ecx, r8d
0x1404048c7  call    cs:__imp_WdLogSingleEntry0
0x1404048ce  nop     dword ptr [rax+rax+00h]
0x1404048d3  xor     r11d, r11d
0x1404048d6  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x1404048dd  mov     [rsp+80h+var_40], r11
0x1404048e2  mov     eax, 0BEFh
0x1404048e7  mov     [rsp+80h+var_48], r11
0x1404048ec  or      r8d, 0FFFFFFFFh
0x1404048f0  mov     [rsp+80h+var_50], r11
0x1404048f5  mov     edx, 40002h
0x1404048fa  mov     [rsp+80h+var_58], r11
0x1404048ff  xor     ecx, ecx
0x140404901  mov     [rsp+80h+var_60], rax
0x140404906  mov     cs:WdLogGlobalForLineNumber, eax
0x14040490c  call    DxgkLogInternalTriageEvent
0x140404911  mov     r8d, 1
0x140404917  mov     ecx, [r15+2Ch]
0x14040491b  xor     esi, esi
0x14040491d  mov     r14d, [rbp+arg_50]
0x140404924  mov     [rbp+Size], 0
0x14040492c  test    ecx, ecx
0x14040492e  jz      short loc_140404998
0x140404930  mov     r10, [rbp+arg_10]
0x140404934  lea     rcx, [rsi+rsi*2]
0x140404938  mov     edx, esi
0x14040493a  shl     rcx, 5
0x14040493e  cmp     qword ptr [rcx+r10+10h], 0
0x140404944  jz      short loc_14040498D
0x140404946  mov     r9d, [rcx+r10+18h]
0x14040494b  imul    r8, rdx, 58h ; 'X'
0x14040494f  mov     [r8+rbx+8], r9d
0x140404954  test    r14d, r14d
0x140404957  jz      short loc_14040497E
0x140404959  test    dword ptr [r15+38h], 10000h
0x140404961  jnz     short loc_14040497E
0x140404963  mov     rcx, [r13+rsi*8+0]; void *
0x140404968  mov     [r8+rbx], rcx
0x14040496c  mov     r8d, r9d; Size
0x14040496f  mov     rdx, [r12+rsi*8]; Src
0x140404973  call    memmove
0x140404978  mov     r10, [rbp+arg_10]
0x14040497c  jmp     short loc_140404987
0x14040497e  mov     rax, [rcx+r10+10h]
0x140404983  mov     [r8+rbx], rax
0x140404987  mov     r8d, 1
0x14040498d  mov     ecx, [r15+2Ch]
0x140404991  add     esi, r8d
0x140404994  cmp     esi, ecx
0x140404996  jb      short loc_140404934
0x140404998  mov     rsi, [rbp+arg_28]
0x14040499c  mov     dword ptr [rbp+var_10], 0
0x1404049a3  test    rsi, rsi
0x1404049a6  jz      short loc_1404049C8
0x1404049a8  mov     eax, [rsi+4]
0x1404049ab  mov     rdx, [rsi+38h]
0x1404049af  mov     dword ptr [rbp+var_10], r8d
0x1404049b3  test    r8b, al
0x1404049b6  jz      short loc_1404049C2
0x1404049b8  mov     rax, [rdx+10h]
0x1404049bc  mov     qword ptr [rbp+var_20+8], rax
0x1404049c0  jmp     short loc_1404049D0
0x1404049c2  mov     qword ptr [rbp+var_20+8], rdx
0x1404049c6  jmp     short loc_1404049D0
0x1404049c8  mov     qword ptr [rbp+var_20+8], 0
0x1404049d0  mov     eax, [r15+28h]
0x1404049d4  mov     dword ptr [rbp+Size+0Ch], ecx
0x1404049d7  mov     qword ptr [rbp+var_20], rbx
0x1404049db  test    eax, eax
0x1404049dd  jz      short loc_140404A51
0x1404049df  cmp     qword ptr [r15+20h], 0
0x1404049e4  jz      short loc_140404A51
0x1404049e6  mov     ecx, eax
0x1404049e8  mov     dword ptr [rbp+Size+8], eax
0x1404049eb  mov     edx, 4B677844h
0x1404049f0  mov     r8d, 102h
0x1404049f6  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1404049fb  mov     [rbp+Size], rax
0x1404049ff  test    rax, rax
0x140404a02  jnz     short loc_140404A33
0x140404a04  mov     r8d, dword ptr [rbp+Size+8]
0x140404a08  lea     ecx, [rax+3]
0x140404a0b  mov     r12, 0FFFFFFFFC0000017h
0x140404a12  mov     rdx, rdi
0x140404a15  mov     r9, r12
0x140404a18  call    cs:__imp_WdLogSingleEntry3
0x140404a1f  nop     dword ptr [rax+rax+00h]
0x140404a24  mov     cs:WdLogGlobalForLineNumber, 0C36h
0x140404a2e  jmp     loc_14040561C
0x140404a33  mov     r8d, dword ptr [rbp+Size+8]; Size
0x140404a37  mov     rcx, rax; void *
0x140404a3a  mov     rdx, [rbp+arg_40]
0x140404a41  test    r14d, r14d
0x140404a44  jnz     short loc_140404A4A
0x140404a46  mov     rdx, [r15+20h]; Src
0x140404a4a  call    memmove
0x140404a4f  jmp     short loc_140404A60
0x140404a51  mov     dword ptr [rbp+Size+8], 0
0x140404a58  mov     [rbp+Size], 0
0x140404a60  mov     rax, [rbp+arg_48]
0x140404a67  xor     r12d, r12d
0x140404a6a  test    rax, rax
0x140404a6d  jz      short loc_140404AA8
0x140404a6f  test    dword ptr [rax], 3000h
0x140404a75  jz      short loc_140404AA8
0x140404a77  mov     rcx, [rdi+10h]
0x140404a7b  mov     rcx, [rcx+10h]; this
0x140404a7f  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x140404a84  test    al, al
0x140404a86  jz      short loc_140404AA8
0x140404a88  xor     edx, edx
0x140404a8a  cmp     [r15+2Ch], edx
0x140404a8e  jbe     short loc_140404AA8
0x140404a90  mov     eax, edx
0x140404a92  inc     edx
0x140404a94  imul    rcx, rax, 58h ; 'X'
0x140404a98  mov     rax, qword ptr [rbp+var_20]
0x140404a9c  bts     dword ptr [rcx+rax+40h], 0Ah
0x140404aa2  cmp     edx, [r15+2Ch]
0x140404aa6  jb      short loc_140404A90
0x140404aa8  test    dword ptr [r15+38h], 100000h
0x140404ab0  jnz     short loc_140404B1C
0x140404ab2  mov     rcx, [rdi+10h]; this
0x140404ab6  lea     rdx, [rbp+Size]; struct _DXGKARG_CREATEALLOCATION *
0x140404aba  call    ?DdiCreateAllocation@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_CREATEALLOCATION@@@Z; ADAPTER_RENDER::DdiCreateAllocation(_DXGKARG_CREATEALLOCATION *)
0x140404abf  movsxd  r12, eax
0x140404ac2  test    eax, eax
0x140404ac4  jns     short loc_140404B1C
0x140404ac6  mov     rdx, r12
0x140404ac9  mov     ecx, 2
0x140404ace  call    cs:__imp_WdLogSingleEntry1
0x140404ad5  nop     dword ptr [rax+rax+00h]
0x140404ada  xor     r11d, r11d
0x140404add  mov     cs:WdLogGlobalForLineNumber, 0C64h
0x140404ae7  mov     [rsp+80h+var_40], r11
0x140404aec  lea     r9, aDriverFailedCa; "Driver failed call to DdiCreateAllocati"...
0x140404af3  mov     [rsp+80h+var_48], r11
0x140404af8  or      r8d, 0FFFFFFFFh
0x140404afc  mov     [rsp+80h+var_50], r11
0x140404b01  mov     edx, 40000h
0x140404b06  mov     [rsp+80h+var_58], r11
0x140404b0b  xor     ecx, ecx
0x140404b0d  mov     [rsp+80h+var_60], r12
0x140404b12  call    DxgkLogInternalTriageEvent
0x140404b17  jmp     loc_14040561C
0x140404b1c  mov     rax, [rbp+arg_20]
0x140404b20  xor     r13d, r13d
0x140404b23  mov     [rbp+arg_8], rax
0x140404b27  lea     r14d, [r13+2]
0x140404b2b  cmp     [r15+2Ch], r13d
0x140404b2f  jbe     loc_140405556
0x140404b35  mov     eax, r13d
0x140404b38  imul    rsi, rax, 58h ; 'X'
0x140404b3c  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140404b41  mov     ecx, [rax+100h]
0x140404b47  test    cl, 1
0x140404b4a  jz      short loc_140404B51
0x140404b4c  and     dword ptr [rsi+rbx+54h], 0FFFFFFBFh
0x140404b51  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140404b56  mov     ecx, [rax+100h]
0x140404b5c  test    cl, 8
0x140404b5f  jz      short loc_140404B80
0x140404b61  mov     eax, [rdi+1E8h]
0x140404b67  test    al, 8
0x140404b69  jz      short loc_140404B80
0x140404b6b  cmp     word ptr [rsi+rbx+10h], 0
0x140404b71  jnz     short loc_140404B80
0x140404b73  or      dword ptr [rsi+rbx+54h], 40h
0x140404b78  mov     dword ptr [rsi+rbx+0Ch], 10000h
0x140404b80  bt      dword ptr [r15+38h], 14h
0x140404b86  jnb     loc_140404C53
0x140404b8c  cmp     dword ptr [rsi+rbx+8], 40h ; '@'
0x140404b91  jb      loc_140405385
0x140404b97  mov     rcx, [rbp+arg_10]
0x140404b9b  lea     rax, ds:0[r13*2]
0x140404ba3  add     rax, r13
0x140404ba6  mov     r8d, r13d
0x140404ba9  shl     rax, 5
0x140404bad  mov     r11d, 1
0x140404bb3  mov     eax, [rax+rcx+20h]
0x140404bb7  test    r11b, al
0x140404bba  jnz     loc_140405368
0x140404bc0  mov     r10, [rbp+arg_8]
0x140404bc4  bts     dword ptr [r10+48h], 15h
0x140404bca  mov     rax, [r10+30h]
0x140404bce  bts     dword ptr [rax+4], 1Ch
0x140404bd3  mov     rax, [rdi+10h]
0x140404bd7  mov     rdx, [rsi+rbx]
0x140404bdb  mov     rcx, [rax+10h]
0x140404bdf  mov     eax, [rdx+20h]
0x140404be2  test    [rcx+1420h], r11w
0x140404bea  mov     [rsi+rbx+28h], eax
0x140404bee  jz      short loc_140404C03
0x140404bf0  movzx   eax, word ptr [rdx]
0x140404bf3  mov     [rsi+rbx+0Ch], ax
0x140404bf8  movzx   eax, word ptr [rdx+2]
0x140404bfc  mov     [rsi+rbx+0Eh], ax
0x140404c01  jmp     short loc_140404C09
0x140404c03  mov     eax, [rdx]
0x140404c05  mov     [rsi+rbx+0Ch], eax
0x140404c09  mov     eax, [rdx+8]
0x140404c0c  mov     [rsi+rbx+10h], rax
0x140404c11  mov     eax, [rdx+10h]
0x140404c14  mov     [rsi+rbx+18h], rax
0x140404c19  mov     eax, [rdx+18h]
0x140404c1c  mov     [rsi+rbx+20h], eax
0x140404c20  mov     eax, [rdx+1Ch]
0x140404c23  mov     [rsi+rbx+24h], eax
0x140404c27  mov     eax, [rdx+24h]
0x140404c2a  mov     [rsi+rbx+2Ch], eax
0x140404c2e  mov     eax, [rdx+28h]
0x140404c31  mov     [rsi+rbx+30h], eax
0x140404c35  mov     eax, [rdx+2Ch]
0x140404c38  mov     [rsi+rbx+34h], eax
0x140404c3c  mov     eax, [rdx+30h]
0x140404c3f  mov     [rsi+rbx+40h], eax
0x140404c43  mov     eax, [rdx+34h]
0x140404c46  mov     [rsi+rbx+50h], eax
0x140404c4a  mov     eax, [rdx+3Ch]
0x140404c4d  mov     [rsi+rbx+54h], eax
0x140404c51  jmp     short loc_140404C60
0x140404c53  mov     r10, [rbp+arg_8]
0x140404c57  mov     r11d, 1
0x140404c5d  mov     r8d, r13d
0x140404c60  mov     rcx, [r10+30h]
0x140404c64  mov     rax, [rsi+rbx+38h]
0x140404c69  mov     [rcx+10h], rax
0x140404c6d  mov     rcx, [r10+30h]
0x140404c71  mov     rax, [rsi+rbx+48h]
0x140404c76  mov     [rcx+18h], rax
0x140404c7a  mov     eax, [rsi+rbx+40h]
0x140404c7e  mov     rdx, [r10+30h]
0x140404c82  and     al, 30h
0x140404c84  neg     al
0x140404c86  sbb     ecx, ecx
0x140404c88  mov     eax, [rdx+4]
0x140404c8b  and     ecx, 800h
0x140404c91  btr     eax, 0Bh
0x140404c95  or      ecx, eax
0x140404c97  mov     [rdx+4], ecx
0x140404c9a  mov     rdx, [r10+30h]
0x140404c9e  mov     ecx, [rsi+rbx+40h]
0x140404ca2  shl     ecx, 11h
0x140404ca5  mov     eax, [rdx+4]
0x140404ca8  xor     ecx, eax
0x140404caa  and     ecx, 80000h
0x140404cb0  xor     ecx, eax
0x140404cb2  mov     [rdx+4], ecx
0x140404cb5  and     dword ptr [rsi+rbx+40h], 807FFFFh
0x140404cbd  mov     rax, [rdi+10h]
0x140404cc1  mov     edx, [rsi+rbx+40h]
0x140404cc5  mov     rcx, [rax+10h]
0x140404cc9  cmp     dword ptr [rcx+0B20h], 3000h
0x140404cd3  jl      short loc_140404CFF
0x140404cd5  cmp     dword ptr [rsi+rbx+54h], 80h
0x140404cdd  jb      short loc_140404D0F
0x140404cdf  mov     ecx, r14d
0x140404ce2  call    cs:__imp_WdLogSingleEntry0
0x140404ce9  nop     dword ptr [rax+rax+00h]
0x140404cee  mov     eax, 0CD5h
0x140404cf3  lea     r9, aFlags2Reserved; "Flags2.Reserved is not zero"
0x140404cfa  jmp     loc_1404053A0
0x140404cff  bt      dword ptr [r15+38h], 14h
0x140404d05  jb      short loc_140404D0F
0x140404d07  mov     dword ptr [rsi+rbx+54h], 0
0x140404d0f  mov     rax, [rdi+10h]
0x140404d13  mov     rcx, [rax+10h]
0x140404d17  mov     eax, [rcx+0A14h]
0x140404d1d  test    al, 40h
0x140404d1f  jz      short loc_140404D32
0x140404d21  cmp     byte ptr [rcx+0C4Dh], 0
0x140404d28  jz      short loc_140404D32
0x140404d2a  bts     edx, 0Fh
0x140404d2e  mov     [rsi+rbx+40h], edx
  ... truncated ...
```
