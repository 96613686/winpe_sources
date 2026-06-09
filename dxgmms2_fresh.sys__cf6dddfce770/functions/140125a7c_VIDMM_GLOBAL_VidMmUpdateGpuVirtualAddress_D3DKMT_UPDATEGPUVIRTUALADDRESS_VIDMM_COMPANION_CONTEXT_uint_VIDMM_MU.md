# VIDMM_GLOBAL::VidMmUpdateGpuVirtualAddress(_D3DKMT_UPDATEGPUVIRTUALADDRESS *,VIDMM_COMPANION_CONTEXT *,uint,VIDMM_MULTI_ALLOC * *,_VIDSCH_SYNC_OBJECT *,_KSEMAPHORE * *)

- ea: `0x140125a7c`
- end: `0x1401266a2`
- name: `?VidMmUpdateGpuVirtualAddress@VIDMM_GLOBAL@@QEAAJPEAU_D3DKMT_UPDATEGPUVIRTUALADDRESS@@PEAUVIDMM_COMPANION_CONTEXT@@IPEAPEAUVIDMM_MULTI_ALLOC@@PEAU_VIDSCH_SYNC_OBJECT@@PEAPEAU_KSEMAPHORE@@@Z`
- size: `3110`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *this, struct _D3DKMT_UPDATEGPUVIRTUALADDRESS *, struct VIDMM_COMPANION_CONTEXT *, int, struct VIDMM_MULTI_ALLOC **, struct _VIDSCH_SYNC_OBJECT *, struct _KSEMAPHORE **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003a2d0`

## callees

- `0x140003490`
- `0x140004268`
- `0x140028a20`
- `0x14002bcc0`
- `0x14002bddc`
- `0x14002e4ec`
- `0x14002f6a8`
- `0x140034e60`
- `0x14003bf6c`
- `0x140059380`
- `0x1400acb4c`
- `0x1400ba2e0`
- `0x1400c70b4`
- `0x140101b98`
- `0x14010a2cc`
- `0x14011a004`
- `0x14011ccc0`
- `0x140125a7c`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14012661a`
- `ntoskrnl!KeReleaseSemaphore` at `0x14012661a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140125c74`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140125f42`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140125c74`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140125f42`
- `ntoskrnl!KeWaitForSingleObject` at `0x140125ada`
- `ntoskrnl!KeWaitForSingleObject` at `0x140125ada`
- `watchdog!WdLogSingleEntry3` at `0x140126208`
- `watchdog!WdLogSingleEntry3` at `0x140126208`
- `watchdog!WdLogSingleEntry0` at `0x140125af3`
- `watchdog!WdLogSingleEntry0` at `0x1401262d4`
- `watchdog!WdLogSingleEntry0` at `0x1401263af`
- `watchdog!WdLogSingleEntry0` at `0x140126402`
- `watchdog!WdLogSingleEntry0` at `0x1401265b8`
- `watchdog!WdLogSingleEntry0` at `0x140125af3`
- `watchdog!WdLogSingleEntry0` at `0x1401262d4`
- `watchdog!WdLogSingleEntry0` at `0x1401263af`
- `watchdog!WdLogSingleEntry0` at `0x140126402`
- `watchdog!WdLogSingleEntry0` at `0x1401265b8`
- `watchdog!WdLogSingleEntry1` at `0x140126070`
- `watchdog!WdLogSingleEntry1` at `0x1401260ae`
- `watchdog!WdLogSingleEntry1` at `0x1401260d3`
- `watchdog!WdLogSingleEntry1` at `0x1401260f8`
- `watchdog!WdLogSingleEntry1` at `0x140126127`
- `watchdog!WdLogSingleEntry1` at `0x14012615e`
- `watchdog!WdLogSingleEntry1` at `0x1401261a5`
- `watchdog!WdLogSingleEntry1` at `0x1401261ca`
- `watchdog!WdLogSingleEntry1` at `0x140126226`
- `watchdog!WdLogSingleEntry1` at `0x140126248`
- `watchdog!WdLogSingleEntry1` at `0x140126267`
- `watchdog!WdLogSingleEntry1` at `0x140126070`
- `watchdog!WdLogSingleEntry1` at `0x1401260ae`
- `watchdog!WdLogSingleEntry1` at `0x1401260d3`
- `watchdog!WdLogSingleEntry1` at `0x1401260f8`
- `watchdog!WdLogSingleEntry1` at `0x140126127`
- `watchdog!WdLogSingleEntry1` at `0x14012615e`
- `watchdog!WdLogSingleEntry1` at `0x1401261a5`
- `watchdog!WdLogSingleEntry1` at `0x1401261ca`
- `watchdog!WdLogSingleEntry1` at `0x140126226`
- `watchdog!WdLogSingleEntry1` at `0x140126248`
- `watchdog!WdLogSingleEntry1` at `0x140126267`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::VidMmUpdateGpuVirtualAddress(
        VIDMM_GLOBAL *this,
        struct _D3DKMT_UPDATEGPUVIRTUALADDRESS *a2,
        struct VIDMM_COMPANION_CONTEXT *a3,
        int a4,
        struct VIDMM_MULTI_ALLOC **a5,
        struct _VIDSCH_SYNC_OBJECT *a6,
        struct _KSEMAPHORE **a7)
{
  NTSTATUS v10; // r14d
  __int64 result; // rax
  __int64 v12; // rax
  char *v13; // rdi
  __int64 v14; // r9
  __int64 v15; // rax
  struct VIDMM_PROCESS *v16; // r8
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  UINT v20; // eax
  unsigned __int64 i; // rbx
  D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *v22; // r12
  __int64 v23; // r15
  D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION_TYPE OperationType; // eax
  unsigned __int64 Value; // rbx
  __int64 v26; // rcx
  __int64 v27; // r8
  PVOID v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  _QWORD *v31; // rcx
  _QWORD *v32; // rax
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rax
  D3DGPU_VIRTUAL_ADDRESS BaseAddress; // rbx
  unsigned __int64 v38; // rdx
  D3DGPU_SIZE_T AllocationSizeInBytes; // r8
  D3DGPU_SIZE_T AllocationOffsetInBytes; // r10
  D3DGPU_SIZE_T SizeInBytes; // rax
  D3DGPU_SIZE_T v42; // rcx
  unsigned int m; // eax
  PVOID v44; // rax
  __int64 v45; // rax
  D3DGPU_VIRTUAL_ADDRESS v46; // r10
  _QWORD *v47; // rax
  unsigned __int64 v48; // rax
  unsigned int v49; // ebx
  int v50; // ecx
  int v51; // r8d
  int v52; // ecx
  int v53; // r8d
  int v54; // r8d
  char *v55; // rax
  CVirtualAddressAllocator *v56; // r14
  struct VIDMM_VAD *v57; // rbx
  struct VIDMM_VAD *v58; // r9
  char *v59; // rdx
  struct VIDMM_VAD **v60; // rax
  char **v61; // rcx
  __int128 *j; // rcx
  bool v63; // zf
  __int64 v64; // rax
  _DWORD *v65; // r9
  char *v66; // rcx
  __int64 k; // r8
  __int64 v68; // rax
  unsigned int v69; // edx
  _QWORD *v70; // rcx
  __int64 v71; // rax
  UINT Timeout; // [rsp+28h] [rbp-E0h]
  UINT64 FenceValue; // [rsp+38h] [rbp-D0h]
  char v74; // [rsp+78h] [rbp-90h]
  __int128 v75; // [rsp+80h] [rbp-88h] BYREF
  int v76; // [rsp+90h] [rbp-78h]
  unsigned __int64 v77; // [rsp+98h] [rbp-70h]
  unsigned int v78; // [rsp+A0h] [rbp-68h]
  UINT v79; // [rsp+A4h] [rbp-64h]
  struct VIDMM_PROCESS *v80; // [rsp+A8h] [rbp-60h]
  __int64 v81; // [rsp+B0h] [rbp-58h]
  D3DGPU_SIZE_T v82; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v83; // [rsp+C0h] [rbp-48h]
  struct VIDMM_ALLOC *v84; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v85; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v86; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v87; // [rsp+E0h] [rbp-28h]
  D3DGPU_SIZE_T v88; // [rsp+E8h] [rbp-20h]
  UINT64 DriverProtection; // [rsp+F0h] [rbp-18h]
  D3DGPU_VIRTUAL_ADDRESS v90; // [rsp+F8h] [rbp-10h]
  __int64 v91; // [rsp+100h] [rbp-8h]
  union _LARGE_INTEGER v92; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int64 v93; // [rsp+110h] [rbp+8h]
  CVirtualAddressAllocator *v94; // [rsp+118h] [rbp+10h]
  PRKSEMAPHORE Semaphore; // [rsp+120h] [rbp+18h]
  _BYTE v96[32]; // [rsp+128h] [rbp+20h] BYREF
  _QWORD v97[16]; // [rsp+148h] [rbp+40h] BYREF

  Semaphore = (PRKSEMAPHORE)((char *)a3 + 24);
  *a7 = (struct _KSEMAPHORE *)((char *)a3 + 24);
  v92.QuadPart = 0;
  v10 = KeWaitForSingleObject((char *)a3 + 24, Executive, 0, 0, &v92);
  if ( v10 == 258 )
  {
    WdLogSingleEntry0(3);
    result = 3223191810LL;
    WdLogGlobalForLineNumber = 28697;
    return result;
  }
  v12 = *((_QWORD *)a3 + 2);
  v13 = 0;
  v14 = *((_QWORD *)a3 + 1);
  v94 = *(CVirtualAddressAllocator **)a3;
  v80 = *(struct VIDMM_PROCESS **)(v12 + 8);
  v81 = *((_QWORD *)v94 + 2);
  v15 = *(_QWORD *)(v14 + 96);
  v85 = -1;
  v87 = -1;
  v83 = 0;
  v76 = *(unsigned __int16 *)(v15 + 6);
  *((_QWORD *)&v75 + 1) = &v75;
  *(_QWORD *)&v75 = &v75;
  v16 = (struct VIDMM_PROCESS *)*((_QWORD *)v94 + 13);
  FenceValue = a2->FenceValue;
  Timeout = a2->NumOperations;
  v86 = 0;
  v74 = 0;
  VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVa(this, 1u, v16, (struct _VIDSCH_CONTEXT *)v14, Timeout, a6, FenceValue);
  if ( byte_140087202 < 0 )
    McTemplateK0qqqqqxpp_EtwWriteTransfer(
      v18,
      v17,
      v19,
      a2->hDevice,
      a2->hContext,
      a2->hFenceObject,
      a2->NumOperations,
      a2->Flags.Value,
      a2->FenceValue,
      (char)a6,
      *((_QWORD *)a3 + 1));
  v20 = 0;
  for ( i = 0; ; v83 = i )
  {
    v79 = v20;
    if ( v20 >= a2->NumOperations )
    {
      if ( (a2->Flags.Value & 1) == 0 )
      {
        *((_BYTE *)a6 + 25) = 0;
        v10 = VidSchWaitForSingleSyncObject(*((_QWORD *)a3 + 1), a6, a2->FenceValue);
        if ( v10 < 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 28996;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            v54,
            (unsigned int)L"VidSchWaitForSingleSyncObject failed",
            28996,
            0,
            0,
            0);
          v49 = 16;
          goto LABEL_102;
        }
      }
      v55 = (char *)operator new(184, 959736150, 256);
      v13 = v55;
      if ( !v55 )
      {
        WdLogSingleEntry0(3);
        v13 = 0;
        WdLogGlobalForLineNumber = 29011;
        v49 = 17;
        v10 = -1073741801;
        goto LABEL_102;
      }
      memset(v55, 0, 0xB8u);
      v56 = v94;
      *((_QWORD *)v13 + 13) = v13 + 96;
      *((_QWORD *)v13 + 12) = v13 + 96;
      *((_QWORD *)v13 + 7) = v13 + 48;
      *((_QWORD *)v13 + 6) = v13 + 48;
      *((_QWORD *)v13 + 1) = this;
      *((_DWORD *)v13 + 5) = a2->NumOperations;
      *((_QWORD *)v13 + 10) = a2->FenceValue + 1;
      *((_DWORD *)v13 + 4) = v76;
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)v96,
        (CVirtualAddressAllocator *)((char *)v56 + 64));
      v57 = CVirtualAddressAllocator::ReferenceReservedZeroVad(v56, v85, i);
      if ( !v57 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 29032;
        v49 = 18;
LABEL_81:
        v10 = -1073741811;
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v96);
        goto LABEL_102;
      }
      v58 = 0;
      if ( v74 )
      {
        v58 = CVirtualAddressAllocator::ReferenceReservedZeroVad(v56, v87, v86);
        if ( !v58 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 29046;
          v49 = 19;
          goto LABEL_81;
        }
      }
      *((_QWORD *)v13 + 15) = v58;
      v59 = (char *)v57 + 80;
      *((_QWORD *)v13 + 14) = v57;
      *((_QWORD *)v13 + 18) = v13 + 112;
      *((_QWORD *)v13 + 21) = v13 + 120;
      v60 = (struct VIDMM_VAD **)*((_QWORD *)v57 + 11);
      if ( *v60 == (struct VIDMM_VAD *)((char *)v57 + 80) )
      {
        v61 = (char **)(v13 + 128);
        *((_QWORD *)v13 + 16) = v59;
        *((_QWORD *)v13 + 17) = v60;
        *v60 = (struct VIDMM_VAD *)(v13 + 128);
        *((_QWORD *)v57 + 11) = v13 + 128;
        if ( !v58 )
          goto LABEL_89;
        if ( *v61 == v59 )
        {
          *((_QWORD *)v13 + 19) = v59;
          *((_QWORD *)v13 + 20) = v61;
          *v61 = v13 + 152;
          *((_QWORD *)v57 + 11) = v13 + 152;
          v13[176] = 1;
LABEL_89:
          for ( j = (__int128 *)v75; j != &v75; j = *(__int128 **)j )
          {
            v63 = *((_QWORD *)j + 10) == 0;
            *((_QWORD *)j - 1) = v57;
            if ( v63 )
            {
              v64 = *((_QWORD *)v57 + 12);
              if ( v64 )
                *((_QWORD *)j + 10) = *(_QWORD *)(v64 + 80);
            }
          }
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v96);
          v65 = v13 + 32;
          *((_QWORD *)v13 + 8) = a5;
          v66 = v13 + 96;
          *((_DWORD *)v13 + 8) = a4;
          *((_QWORD *)v13 + 3) = a2->Operations;
          a2->Operations = 0;
          *((_QWORD *)v13 + 9) = a6;
          *((_QWORD *)v13 + 11) = a3;
          *(_QWORD *)v13 = *((_QWORD *)a3 + 1);
          if ( (__int128 *)v75 == &v75 )
          {
            *((_QWORD *)v13 + 13) = v13 + 96;
            *(_QWORD *)v66 = v66;
          }
          else
          {
            *(_OWORD *)v66 = v75;
            *(_QWORD *)(*(_QWORD *)v66 + 8LL) = v66;
            **((_QWORD **)v13 + 13) = v66;
          }
          *((_QWORD *)&v75 + 1) = &v75;
          *(_QWORD *)&v75 = &v75;
          _InterlockedIncrement((volatile signed __int32 *)a6 + 9);
          for ( k = 0; (unsigned int)k < *v65; k = (unsigned int)(k + 1) )
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v13 + 8) + 8 * k) + 696LL));
          memset(v97, 0, 0x50u);
          LODWORD(v97[5]) = 2;
          v97[3] = VIDMM_GLOBAL::VidMmiUpdateGpuVirtualAddress;
          v68 = *((_QWORD *)a3 + 1);
          LODWORD(v97[0]) = 2;
          v97[6] = v13;
          v97[4] = 0;
          VidSchSubmitGlobalCommand(*(_QWORD *)(*(_QWORD *)(v68 + 104) + 40LL), v97);
          return 0;
        }
      }
LABEL_110:
      __fastfail(3u);
    }
    v22 = &a2->Operations[(unsigned __int64)v20];
    v23 = v20;
    OperationType = v22->OperationType;
    if ( v22->OperationType == D3DDDI_UPDATEGPUVIRTUALADDRESS_MAP
      || OperationType == D3DDDI_UPDATEGPUVIRTUALADDRESS_MAP_PROTECT )
    {
      BaseAddress = v22->Map.BaseAddress;
      v38 = BaseAddress + v22->Map.SizeInBytes;
      v93 = BaseAddress;
      v77 = v38;
      if ( !(unsigned __int8)IsVirtualAddressRangeValid(BaseAddress, v38, v81) )
      {
        v49 = 1;
        goto LABEL_73;
      }
      v84 = a5[v22->Map.hAllocation];
      VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(this, v80, *((struct _VIDSCH_CONTEXT **)a3 + 1), v84, v22);
      AllocationSizeInBytes = v22->Map.AllocationSizeInBytes;
      if ( (AllocationSizeInBytes & 0xFFF) != 0
        || (AllocationOffsetInBytes = v22->Map.AllocationOffsetInBytes,
            v88 = AllocationOffsetInBytes,
            (AllocationOffsetInBytes & 0xFFF) != 0) )
      {
        WdLogSingleEntry1(3, v23);
        WdLogGlobalForLineNumber = 28770;
        v49 = 2;
        goto LABEL_73;
      }
      SizeInBytes = v22->Map.SizeInBytes;
      v82 = SizeInBytes;
      if ( AllocationSizeInBytes )
      {
        if ( AllocationSizeInBytes > SizeInBytes )
        {
          WdLogSingleEntry1(3, v23);
          WdLogGlobalForLineNumber = 28786;
          v49 = 3;
          goto LABEL_73;
        }
        if ( SizeInBytes % AllocationSizeInBytes )
        {
          WdLogSingleEntry1(3, v23);
          WdLogGlobalForLineNumber = 28795;
          v49 = 4;
          goto LABEL_73;
        }
        SizeInBytes = v82;
      }
      else
      {
        v22->Map.AllocationSizeInBytes = SizeInBytes;
        AllocationSizeInBytes = SizeInBytes;
      }
      if ( AllocationOffsetInBytes + AllocationSizeInBytes < AllocationOffsetInBytes
        || AllocationOffsetInBytes + AllocationSizeInBytes > *(_QWORD *)(***(_QWORD ***)v84 + 16LL) )
      {
        WdLogSingleEntry3(3, *(_QWORD *)(***(_QWORD ***)v84 + 16LL), v23, 28807);
        WdLogGlobalForLineNumber = 28807;
        v49 = 5;
        goto LABEL_73;
      }
      if ( (*((_BYTE *)this + 37225) & 2) != 0 )
      {
        LODWORD(v42) = 1;
        v91 = 1;
      }
      else
      {
        v42 = SizeInBytes / AllocationSizeInBytes;
        v91 = SizeInBytes / AllocationSizeInBytes;
        if ( SizeInBytes / AllocationSizeInBytes >= 0xFFFFFFFF )
        {
          WdLogSingleEntry1(3, v23);
          WdLogGlobalForLineNumber = 28831;
          v49 = 6;
          goto LABEL_73;
        }
        v88 = 0;
        v82 = AllocationSizeInBytes;
      }
      v90 = BaseAddress;
      if ( v22->OperationType )
        DriverProtection = v22->MapProtect.DriverProtection;
      else
        DriverProtection = 0;
      for ( m = 0; ; m = v78 + 1 )
      {
        v78 = m;
        if ( m >= (unsigned int)v42 )
          break;
        v44 = ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
        if ( !v44 || (v45 = VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(v44, v44, 0)) == 0 )
        {
          v49 = 7;
          _InterlockedIncrement(&dword_1400877D0);
          WdLogSingleEntry1(6, 7);
          WdLogGlobalForLineNumber = 28867;
          DxgkLogInternalTriageEvent(
            v52,
            262145,
            v53,
            (unsigned int)L"Failed to allocate VIDMM_MAPPED_VA_RANGE",
            7,
            0,
            0,
            0);
          goto LABEL_73;
        }
        v42 = *((_QWORD *)&v75 + 1);
        if ( **((__int128 ***)&v75 + 1) != &v75 )
          goto LABEL_110;
        v47 = (_QWORD *)(v45 + 8);
        v90 = v46;
        v47[1] = *((_QWORD *)&v75 + 1);
        *v47 = &v75;
        *(_QWORD *)v42 = v47;
        LODWORD(v42) = v91;
        *((_QWORD *)&v75 + 1) = v47;
      }
      Value = v93;
      goto LABEL_51;
    }
    if ( OperationType == D3DDDI_UPDATEGPUVIRTUALADDRESS_UNMAP )
      break;
    if ( OperationType != D3DDDI_UPDATEGPUVIRTUALADDRESS_COPY )
      goto LABEL_67;
    Value = v22->Unmap.Protection.Value;
    v77 = Value + v22->Map.SizeInBytes;
    VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(this, v80, *((struct _VIDSCH_CONTEXT **)a3 + 1), 0, v22);
    if ( !(unsigned __int8)IsVirtualAddressRangeValid(Value, v77, v81) )
    {
      v49 = 10;
      goto LABEL_73;
    }
    v33 = v22->Map.BaseAddress;
    v34 = v33 + v22->Map.SizeInBytes;
    if ( v34 <= v33 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28926;
      v49 = 11;
      goto LABEL_73;
    }
    if ( (v33 & 0xFFF) != 0 || (v34 & 0xFFF) != 0 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28932;
      v49 = 12;
      goto LABEL_73;
    }
    if ( Value < v34 && v77 > v33 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28939;
      v49 = 13;
      goto LABEL_73;
    }
    v35 = v87;
    v74 = 1;
    if ( v87 > v33 )
      v35 = v33;
    v87 = v35;
    v36 = v86;
    if ( v86 < v34 )
      v36 = v34;
    v86 = v36;
LABEL_51:
    if ( v77 <= Value )
    {
LABEL_67:
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28966;
      v49 = 14;
      goto LABEL_73;
    }
    if ( ((Value | v77) & 0xFFF) != 0 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28972;
      v49 = 15;
      goto LABEL_73;
    }
    v48 = v85;
    if ( v85 > Value )
      v48 = Value;
    i = v83;
    v85 = v48;
    if ( v83 < v77 )
      i = v77;
    v20 = v79 + 1;
  }
  Value = v22->Map.BaseAddress;
  v77 = Value + v22->Map.SizeInBytes;
  VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(this, v80, *((struct _VIDSCH_CONTEXT **)a3 + 1), 0, v22);
  if ( !(unsigned __int8)IsVirtualAddressRangeValid(Value, v77, v81) )
  {
    v49 = 8;
    goto LABEL_73;
  }
  v28 = ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
  if ( v28 )
  {
    LOBYTE(v29) = -(v22->Unmap.Protection.Value & 8);
    v30 = VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(v28, v29, 0);
    if ( v30 )
    {
      v31 = (_QWORD *)*((_QWORD *)&v75 + 1);
      if ( **((__int128 ***)&v75 + 1) != &v75 )
        goto LABEL_110;
      v32 = (_QWORD *)(v30 + 8);
      v32[1] = *((_QWORD *)&v75 + 1);
      *v32 = &v75;
      *v31 = v32;
      *((_QWORD *)&v75 + 1) = v32;
      goto LABEL_51;
    }
  }
  v49 = 9;
  _InterlockedIncrement(&dword_1400877D0);
  WdLogSingleEntry1(6, 9);
  WdLogGlobalForLineNumber = 28903;
  DxgkLogInternalTriageEvent(v50, 262145, v51, (unsigned int)L"Failed to allocate VIDMM_MAPPED_VA_RANGE", 9, 0, 0, 0);
LABEL_73:
  if ( v10 >= 0 )
    v10 = -1073741811;
LABEL_102:
  if ( byte_140087202 < 0 )
    McTemplateK0dq_EtwWriteTransfer(v26, &UpdateGpuVirtualAddressFailure, v27, (unsigned int)v10, v49);
  VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaFailure(this, v80, v10, v49);
  KeReleaseSemaphore(Semaphore, 0, 1, 0);
  if ( v13 )
    VIDMM_DEVICE_COMMAND_UPDATEGPUVA::`scalar deleting destructor'((VIDMM_DEVICE_COMMAND_UPDATEGPUVA *)v13, v69);
  while ( 1 )
  {
    v70 = (_QWORD *)v75;
    if ( (__int128 *)v75 == &v75 )
      return (unsigned int)v10;
    if ( *(__int128 **)(v75 + 8) != &v75 )
      goto LABEL_110;
    v71 = *(_QWORD *)v75;
    if ( *(_QWORD *)(*(_QWORD *)v75 + 8LL) != (_QWORD)v75 )
      goto LABEL_110;
    *(_QWORD *)&v75 = *(_QWORD *)v75;
    *(_QWORD *)(v71 + 8) = &v75;
    *v70 = 0;
    v70[1] = 0;
    VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(v70 - 1);
  }
}

```

## disassembly

```asm
0x140125a7c  mov     rax, rsp
0x140125a7f  mov     [rax+10h], rbx
0x140125a83  mov     [rax+20h], r9d
0x140125a87  mov     [rax+18h], r8
0x140125a8b  mov     [rax+8], rcx
0x140125a8f  push    rbp
0x140125a90  push    rsi
0x140125a91  push    rdi
0x140125a92  push    r12
0x140125a94  push    r13
0x140125a96  push    r14
0x140125a98  push    r15
0x140125a9a  lea     rbp, [rax-0C8h]
0x140125aa1  sub     rsp, 190h
0x140125aa8  mov     rax, [rbp+0C0h+arg_30]
0x140125aaf  mov     rbx, rcx
0x140125ab2  lea     rcx, [r8+18h]; Object
0x140125ab6  mov     r15, r8
0x140125ab9  mov     r13, rdx
0x140125abc  mov     [rbp+0C0h+Semaphore], rcx
0x140125ac0  xor     esi, esi
0x140125ac2  xor     r9d, r9d; Alertable
0x140125ac5  mov     [rax], rcx
0x140125ac8  xor     r8d, r8d; WaitMode
0x140125acb  lea     rax, [rbp+0C0h+var_C0]
0x140125acf  mov     qword ptr [rbp+0C0h+var_C0], rsi
0x140125ad3  xor     edx, edx; WaitReason
0x140125ad5  mov     [rsp+1C0h+Timeout], rax; Timeout
0x140125ada  call    cs:__imp_KeWaitForSingleObject
0x140125ae1  nop     dword ptr [rax+rax+00h]
0x140125ae6  mov     r14d, eax
0x140125ae9  cmp     eax, 102h
0x140125aee  jnz     short loc_140125B13
0x140125af0  lea     ecx, [rsi+3]
0x140125af3  call    cs:__imp_WdLogSingleEntry0
0x140125afa  nop     dword ptr [rax+rax+00h]
0x140125aff  mov     eax, 0C01E0102h
0x140125b04  mov     cs:WdLogGlobalForLineNumber, 7019h
0x140125b0e  jmp     loc_140126686
0x140125b13  mov     rcx, [r15]
0x140125b16  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140125b1a  mov     rax, [r15+10h]
0x140125b1e  mov     rdi, rsi
0x140125b21  mov     r9, [r15+8]; struct _VIDSCH_CONTEXT *
0x140125b25  mov     r12, [rbp+0C0h+arg_28]
0x140125b2c  mov     [rbp+0C0h+var_B0], rcx
0x140125b30  mov     rax, [rax+8]
0x140125b34  mov     [rbp+0C0h+var_120], rax
0x140125b38  mov     rax, [rcx+10h]
0x140125b3c  mov     [rbp+0C0h+var_118], rax
0x140125b40  mov     rax, [r9+60h]
0x140125b44  mov     [rbp+0C0h+var_F8], rdx
0x140125b48  mov     [rbp+0C0h+var_E8], rdx
0x140125b4c  mov     dl, 1; unsigned __int8
0x140125b4e  mov     [rbp+0C0h+var_108], rsi
0x140125b52  movzx   eax, word ptr [rax+6]
0x140125b56  mov     [rbp+0C0h+var_138], eax
0x140125b59  lea     rax, [rsp+1C0h+var_150+8]
0x140125b5e  mov     [rbp+0C0h+var_140], rax
0x140125b62  lea     rax, [rsp+1C0h+var_150+8]
0x140125b67  mov     qword ptr [rsp+1C0h+var_150+8], rax
0x140125b6c  mov     rax, [r13+28h]
0x140125b70  mov     r8, [rcx+68h]; struct VIDMM_PROCESS *
0x140125b74  mov     rcx, rbx; this
0x140125b77  mov     [rsp+1C0h+var_190], rax; unsigned __int64
0x140125b7c  mov     eax, [r13+0Ch]
0x140125b80  mov     [rsp+1C0h+var_198], r12; struct _VIDSCH_SYNC_OBJECT *
0x140125b85  mov     dword ptr [rsp+1C0h+Timeout], eax; unsigned int
0x140125b89  mov     [rbp+0C0h+var_F0], rsi
0x140125b8d  mov     byte ptr [rsp+1C0h+var_150], sil
0x140125b92  call    ?RecordVaPagingHistoryUpdateGpuVa@VIDMM_GLOBAL@@QEAAXEPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@IPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVa(uchar,VIDMM_PROCESS *,_VIDSCH_CONTEXT *,uint,_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x140125b97  cmp     cs:byte_140087202, sil
0x140125b9e  jge     short loc_140125BE0
0x140125ba0  mov     rax, [r15+8]
0x140125ba4  mov     r9d, [r13+0]
0x140125ba8  mov     [rsp+1C0h+var_170], rax
0x140125bad  mov     rax, [r13+28h]
0x140125bb1  mov     [rsp+1C0h+var_178], r12
0x140125bb6  mov     [rsp+1C0h+var_180], rax
0x140125bbb  mov     eax, [r13+30h]
0x140125bbf  mov     dword ptr [rsp+1C0h+var_188], eax
0x140125bc3  mov     eax, [r13+0Ch]
0x140125bc7  mov     dword ptr [rsp+1C0h+var_190], eax
0x140125bcb  mov     eax, [r13+8]
0x140125bcf  mov     dword ptr [rsp+1C0h+var_198], eax
0x140125bd3  mov     eax, [r13+4]
0x140125bd7  mov     dword ptr [rsp+1C0h+Timeout], eax
0x140125bdb  call    McTemplateK0qqqqqxpp_EtwWriteTransfer
0x140125be0  mov     eax, esi
0x140125be2  mov     esi, 3
0x140125be7  mov     ebx, eax
0x140125be9  mov     [rbp+0C0h+var_124], eax
0x140125bec  cmp     eax, [r13+0Ch]
0x140125bf0  jnb     loc_14012629D
0x140125bf6  mov     r12d, eax
0x140125bf9  shl     r12, 6
0x140125bfd  add     r12, [r13+10h]
0x140125c01  mov     r15d, eax
0x140125c04  mov     eax, [r12]
0x140125c08  test    eax, eax
0x140125c0a  jz      loc_140125DDB
0x140125c10  cmp     eax, esi
0x140125c12  jz      loc_140125DDB
0x140125c18  cmp     eax, 1
0x140125c1b  jnz     loc_140125D1F
0x140125c21  mov     rbx, [r12+8]
0x140125c26  xor     r9d, r9d; struct VIDMM_ALLOC *
0x140125c29  mov     rax, [r12+10h]
0x140125c2e  mov     rdx, [rbp+0C0h+var_120]; struct VIDMM_PROCESS *
0x140125c32  add     rax, rbx
0x140125c35  mov     rcx, [rbp+0C0h+arg_0]; this
0x140125c3c  mov     [rbp+0C0h+var_130], rax
0x140125c40  mov     rax, [rbp+0C0h+arg_10]
0x140125c47  mov     [rsp+1C0h+Timeout], r12; struct _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *
0x140125c4c  mov     r8, [rax+8]; struct _VIDSCH_CONTEXT *
0x140125c50  call    ?RecordVaPagingHistoryUpdateGpuVaOp@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@PEAUVIDMM_ALLOC@@PEAU_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION@@@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(VIDMM_PROCESS *,_VIDSCH_CONTEXT *,VIDMM_ALLOC *,_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *)
0x140125c55  mov     r8, [rbp+0C0h+var_118]
0x140125c59  mov     rcx, rbx
0x140125c5c  mov     rdx, [rbp+0C0h+var_130]
0x140125c60  call    IsVirtualAddressRangeValid
0x140125c65  test    al, al
0x140125c67  jz      loc_14012609F
0x140125c6d  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140125c74  call    cs:__imp_ExAllocateFromLookasideListEx
0x140125c7b  nop     dword ptr [rax+rax+00h]
0x140125c80  test    rax, rax
0x140125c83  jz      loc_14012605C
0x140125c89  mov     rcx, [r12+18h]
0x140125c8e  mov     r9, rbx
0x140125c91  mov     dl, cl
0x140125c93  and     dl, 8
0x140125c96  neg     dl
0x140125c98  sbb     r8d, r8d
0x140125c9b  xor     r12d, r12d
0x140125c9e  mov     dword ptr [rsp+1C0h+var_158], r12d
0x140125ca3  not     r8d
0x140125ca6  mov     qword ptr [rsp+1C0h+var_160], r12
0x140125cab  and     r8d, 6
0x140125caf  mov     [rsp+1C0h+var_168], r12
0x140125cb4  mov     [rsp+1C0h+var_170], r12
0x140125cb9  mov     [rsp+1C0h+var_178], rcx
0x140125cbe  mov     ecx, [rbp+0C0h+var_138]
0x140125cc1  mov     dword ptr [rsp+1C0h+var_180], r8d
0x140125cc6  xor     r8d, r8d
0x140125cc9  mov     [rsp+1C0h+var_188], r12
0x140125cce  mov     [rsp+1C0h+var_190], r12
0x140125cd3  mov     dword ptr [rsp+1C0h+var_198], ecx
0x140125cd7  mov     rcx, [rbp+0C0h+var_130]
0x140125cdb  mov     [rsp+1C0h+Timeout], rcx
0x140125ce0  mov     rcx, rax
0x140125ce3  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
0x140125ce8  test    rax, rax
0x140125ceb  jz      loc_14012605F
0x140125cf1  mov     rcx, [rbp+0C0h+var_140]
0x140125cf5  lea     rdx, [rsp+1C0h+var_150+8]
0x140125cfa  cmp     [rcx], rdx
0x140125cfd  jnz     loc_14012667E
0x140125d03  add     rax, 8
0x140125d07  lea     rdx, [rsp+1C0h+var_150+8]
0x140125d0c  mov     [rax+8], rcx
0x140125d10  mov     [rax], rdx
0x140125d13  mov     [rcx], rax
0x140125d16  mov     [rbp+0C0h+var_140], rax
0x140125d1a  jmp     loc_140126015
0x140125d1f  cmp     eax, 2
0x140125d22  jnz     loc_1401261C5
0x140125d28  mov     rbx, [r12+18h]
0x140125d2d  xor     r9d, r9d; struct VIDMM_ALLOC *
0x140125d30  mov     rax, [r12+10h]
0x140125d35  mov     rdx, [rbp+0C0h+var_120]; struct VIDMM_PROCESS *
0x140125d39  add     rax, rbx
0x140125d3c  mov     rcx, [rbp+0C0h+arg_0]; this
0x140125d43  mov     [rbp+0C0h+var_130], rax
0x140125d47  mov     rax, [rbp+0C0h+arg_10]
0x140125d4e  mov     [rsp+1C0h+Timeout], r12; struct _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *
0x140125d53  mov     r8, [rax+8]; struct _VIDSCH_CONTEXT *
0x140125d57  call    ?RecordVaPagingHistoryUpdateGpuVaOp@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@PEAUVIDMM_ALLOC@@PEAU_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION@@@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(VIDMM_PROCESS *,_VIDSCH_CONTEXT *,VIDMM_ALLOC *,_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *)
0x140125d5c  mov     r8, [rbp+0C0h+var_118]
0x140125d60  mov     rcx, rbx
0x140125d63  mov     rdx, [rbp+0C0h+var_130]
0x140125d67  call    IsVirtualAddressRangeValid
0x140125d6c  test    al, al
0x140125d6e  jz      loc_140126118
0x140125d74  mov     rcx, [r12+8]
0x140125d79  mov     rdx, [r12+10h]
0x140125d7e  add     rdx, rcx
0x140125d81  cmp     rdx, rcx
0x140125d84  jbe     loc_1401260F3
0x140125d8a  test    rcx, 0FFFh
0x140125d91  jnz     loc_1401260CE
0x140125d97  test    rdx, 0FFFh
0x140125d9e  jnz     loc_1401260CE
0x140125da4  cmp     rbx, rdx
0x140125da7  jnb     short loc_140125DB3
0x140125da9  cmp     [rbp+0C0h+var_130], rcx
0x140125dad  ja      loc_1401260A9
0x140125db3  mov     rax, [rbp+0C0h+var_E8]
0x140125db7  cmp     rax, rcx
0x140125dba  mov     byte ptr [rsp+1C0h+var_150], 1
0x140125dbf  cmova   rax, rcx
0x140125dc3  mov     [rbp+0C0h+var_E8], rax
0x140125dc7  mov     rax, [rbp+0C0h+var_F0]
0x140125dcb  cmp     rax, rdx
0x140125dce  cmovb   rax, rdx
0x140125dd2  mov     [rbp+0C0h+var_F0], rax
0x140125dd6  jmp     loc_140126015
0x140125ddb  mov     rbx, [r12+8]
0x140125de0  mov     rax, [r12+10h]
0x140125de5  mov     rcx, rbx
0x140125de8  mov     r8, [rbp+0C0h+var_118]
0x140125dec  add     rax, rbx
0x140125def  mov     rdx, rax
0x140125df2  mov     [rbp+0C0h+var_B8], rbx
0x140125df6  mov     [rbp+0C0h+var_130], rax
0x140125dfa  call    IsVirtualAddressRangeValid
0x140125dff  test    al, al
0x140125e01  jz      loc_140126284
0x140125e07  mov     eax, [r12+18h]
0x140125e0c  mov     rcx, [rbp+0C0h+arg_20]
0x140125e13  mov     rdx, [rbp+0C0h+var_120]; struct VIDMM_PROCESS *
0x140125e17  mov     [rsp+1C0h+Timeout], r12; struct _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *
0x140125e1c  mov     rax, [rcx+rax*8]
0x140125e20  mov     rcx, [rbp+0C0h+arg_0]; this
0x140125e27  mov     r9, rax; struct VIDMM_ALLOC *
0x140125e2a  mov     [rbp+0C0h+var_100], rax
0x140125e2e  mov     rax, [rbp+0C0h+arg_10]
0x140125e35  mov     r8, [rax+8]; struct _VIDSCH_CONTEXT *
0x140125e39  call    ?RecordVaPagingHistoryUpdateGpuVaOp@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@PEAUVIDMM_ALLOC@@PEAU_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION@@@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(VIDMM_PROCESS *,_VIDSCH_CONTEXT *,VIDMM_ALLOC *,_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *)
0x140125e3e  mov     r8, [r12+28h]
0x140125e43  test    r8, 0FFFh
0x140125e4a  jnz     loc_140126262
0x140125e50  mov     r10, [r12+20h]
0x140125e55  mov     [rbp+0C0h+var_E0], r10
0x140125e59  test    r10, 0FFFh
0x140125e60  jnz     loc_140126262
0x140125e66  mov     rax, [r12+10h]
0x140125e6b  mov     [rbp+0C0h+var_110], rax
0x140125e6f  test    r8, r8
0x140125e72  jnz     short loc_140125E7E
0x140125e74  mov     [r12+28h], rax
0x140125e79  mov     r8, rax
0x140125e7c  jmp     short loc_140125E99
0x140125e7e  cmp     r8, rax
0x140125e81  ja      loc_140126243
0x140125e87  xor     edx, edx
0x140125e89  div     r8
0x140125e8c  test    rdx, rdx
0x140125e8f  jnz     loc_140126221
0x140125e95  mov     rax, [rbp+0C0h+var_110]
0x140125e99  lea     r9, [r10+r8]
0x140125e9d  cmp     r9, r10
0x140125ea0  jb      loc_1401261EA
0x140125ea6  mov     rcx, [rbp+0C0h+var_100]
0x140125eaa  mov     rcx, [rcx]
0x140125ead  mov     rdx, [rcx]
0x140125eb0  mov     rcx, [rdx]
0x140125eb3  cmp     r9, [rcx+10h]
0x140125eb7  ja      loc_1401261EA
0x140125ebd  mov     rcx, [rbp+0C0h+arg_0]
0x140125ec4  test    byte ptr [rcx+9169h], 2
0x140125ecb  jnz     short loc_140125EF8
0x140125ecd  xor     edx, edx
0x140125ecf  div     r8
0x140125ed2  mov     rcx, rax
0x140125ed5  mov     [rbp+0C0h+var_C8], rax
0x140125ed9  mov     eax, 0FFFFFFFFh
0x140125ede  cmp     rcx, rax
0x140125ee1  jnb     loc_140126122
0x140125ee7  mov     byte ptr [rbp+0C0h+arg_30], dil
0x140125eee  mov     [rbp+0C0h+var_E0], rdi
0x140125ef2  mov     [rbp+0C0h+var_110], r8
0x140125ef6  jmp     short loc_140125F0B
0x140125ef8  cmp     rax, r8
0x140125efb  mov     ecx, 1
0x140125f00  mov     [rbp+0C0h+var_C8], rcx
0x140125f04  setnz   byte ptr [rbp+0C0h+arg_30]
0x140125f0b  mov     [rbp+0C0h+var_D0], rbx
0x140125f0f  cmp     [r12], edi
0x140125f13  jnz     short loc_140125F20
0x140125f15  mov     [rbp+0C0h+var_D8], rdi
0x140125f19  mov     ebx, 1
0x140125f1e  jmp     short loc_140125F2E
0x140125f20  mov     rax, [r12+38h]
0x140125f25  mov     rbx, [r12+30h]
0x140125f2a  mov     [rbp+0C0h+var_D8], rax
0x140125f2e  xor     eax, eax
0x140125f30  mov     [rbp+0C0h+var_128], eax
0x140125f33  cmp     eax, ecx
0x140125f35  jnb     loc_140126011
0x140125f3b  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140125f42  call    cs:__imp_ExAllocateFromLookasideListEx
0x140125f49  nop     dword ptr [rax+rax+00h]
0x140125f4e  mov     rdx, rax
0x140125f51  test    rax, rax
0x140125f54  jz      loc_140126147
0x140125f5a  mov     r10, [rbp+0C0h+var_110]
0x140125f5e  mov     r9, [rbp+0C0h+var_D0]
0x140125f62  add     r10, r9
0x140125f65  cmp     byte ptr [rbp+0C0h+arg_30], dil
0x140125f6c  jz      short loc_140125F79
  ... truncated ...
```
