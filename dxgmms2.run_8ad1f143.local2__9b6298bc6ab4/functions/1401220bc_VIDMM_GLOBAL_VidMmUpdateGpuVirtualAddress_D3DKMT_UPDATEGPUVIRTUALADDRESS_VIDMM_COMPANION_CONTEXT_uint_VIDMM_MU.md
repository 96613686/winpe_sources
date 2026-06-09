# VIDMM_GLOBAL::VidMmUpdateGpuVirtualAddress(_D3DKMT_UPDATEGPUVIRTUALADDRESS *,VIDMM_COMPANION_CONTEXT *,uint,VIDMM_MULTI_ALLOC * *,_VIDSCH_SYNC_OBJECT *,_KSEMAPHORE * *)

- ea: `0x1401220bc`
- end: `0x140122ce2`
- name: `?VidMmUpdateGpuVirtualAddress@VIDMM_GLOBAL@@QEAAJPEAU_D3DKMT_UPDATEGPUVIRTUALADDRESS@@PEAUVIDMM_COMPANION_CONTEXT@@IPEAPEAUVIDMM_MULTI_ALLOC@@PEAU_VIDSCH_SYNC_OBJECT@@PEAPEAU_KSEMAPHORE@@@Z`
- size: `3110`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct _D3DKMT_UPDATEGPUVIRTUALADDRESS *@<rdx>, struct VIDMM_COMPANION_CONTEXT *@<r8>, unsigned int@<r9d>, struct VIDMM_MULTI_ALLOC **, struct _VIDSCH_SYNC_OBJECT *, struct _KSEMAPHORE **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003b5c0`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002b0e0`
- `0x14002ec00`
- `0x14002ed1c`
- `0x14003090c`
- `0x14003180c`
- `0x140036060`
- `0x14003d25c`
- `0x140058ac0`
- `0x1400ab79c`
- `0x1400b6908`
- `0x1400c2f08`
- `0x1400ec028`
- `0x1401011cc`
- `0x1401165c0`
- `0x140119250`
- `0x1401220bc`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x140122c5a`
- `ntoskrnl!KeReleaseSemaphore` at `0x140122c5a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401222b4`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140122582`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401222b4`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140122582`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012211a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012211a`
- `watchdog!WdLogSingleEntry3` at `0x140122848`
- `watchdog!WdLogSingleEntry3` at `0x140122848`
- `watchdog!WdLogSingleEntry0` at `0x140122133`
- `watchdog!WdLogSingleEntry0` at `0x140122914`
- `watchdog!WdLogSingleEntry0` at `0x1401229ef`
- `watchdog!WdLogSingleEntry0` at `0x140122a42`
- `watchdog!WdLogSingleEntry0` at `0x140122bf8`
- `watchdog!WdLogSingleEntry0` at `0x140122133`
- `watchdog!WdLogSingleEntry0` at `0x140122914`
- `watchdog!WdLogSingleEntry0` at `0x1401229ef`
- `watchdog!WdLogSingleEntry0` at `0x140122a42`
- `watchdog!WdLogSingleEntry0` at `0x140122bf8`
- `watchdog!WdLogSingleEntry1` at `0x1401226b0`
- `watchdog!WdLogSingleEntry1` at `0x1401226ee`
- `watchdog!WdLogSingleEntry1` at `0x140122713`
- `watchdog!WdLogSingleEntry1` at `0x140122738`
- `watchdog!WdLogSingleEntry1` at `0x140122767`
- `watchdog!WdLogSingleEntry1` at `0x14012279e`
- `watchdog!WdLogSingleEntry1` at `0x1401227e5`
- `watchdog!WdLogSingleEntry1` at `0x14012280a`
- `watchdog!WdLogSingleEntry1` at `0x140122866`
- `watchdog!WdLogSingleEntry1` at `0x140122888`
- `watchdog!WdLogSingleEntry1` at `0x1401228a7`
- `watchdog!WdLogSingleEntry1` at `0x1401226b0`
- `watchdog!WdLogSingleEntry1` at `0x1401226ee`
- `watchdog!WdLogSingleEntry1` at `0x140122713`
- `watchdog!WdLogSingleEntry1` at `0x140122738`
- `watchdog!WdLogSingleEntry1` at `0x140122767`
- `watchdog!WdLogSingleEntry1` at `0x14012279e`
- `watchdog!WdLogSingleEntry1` at `0x1401227e5`
- `watchdog!WdLogSingleEntry1` at `0x14012280a`
- `watchdog!WdLogSingleEntry1` at `0x140122866`
- `watchdog!WdLogSingleEntry1` at `0x140122888`
- `watchdog!WdLogSingleEntry1` at `0x1401228a7`

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
  unsigned __int64 v25; // rbx
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
  __int64 Value; // rbx
  unsigned int m; // eax
  PVOID v45; // rax
  D3DGPU_SIZE_T v46; // rcx
  __int64 v47; // rax
  D3DGPU_VIRTUAL_ADDRESS v48; // r10
  _QWORD *v49; // rax
  unsigned __int64 v50; // rax
  unsigned int v51; // ebx
  int v52; // ecx
  int v53; // r8d
  int v54; // ecx
  int v55; // r8d
  int v56; // r8d
  char *v57; // rax
  CVirtualAddressAllocator *v58; // r14
  struct VIDMM_VAD *v59; // rbx
  struct VIDMM_VAD *v60; // r9
  char *v61; // rdx
  struct VIDMM_VAD **v62; // rax
  char **v63; // rcx
  __int128 *j; // rcx
  bool v65; // zf
  __int64 v66; // rax
  _DWORD *v67; // r9
  char *v68; // rcx
  __int64 k; // r8
  __int64 v70; // rax
  unsigned int v71; // edx
  _QWORD *v72; // rcx
  __int64 v73; // rax
  UINT Timeout; // [rsp+28h] [rbp-E0h]
  UINT64 FenceValue; // [rsp+38h] [rbp-D0h]
  char v76; // [rsp+78h] [rbp-90h]
  __int128 v77; // [rsp+80h] [rbp-88h] BYREF
  int v78; // [rsp+90h] [rbp-78h]
  unsigned __int64 v79; // [rsp+98h] [rbp-70h]
  unsigned int v80; // [rsp+A0h] [rbp-68h]
  UINT v81; // [rsp+A4h] [rbp-64h]
  struct VIDMM_PROCESS *v82; // [rsp+A8h] [rbp-60h]
  __int64 v83; // [rsp+B0h] [rbp-58h]
  D3DGPU_SIZE_T v84; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v85; // [rsp+C0h] [rbp-48h]
  struct VIDMM_ALLOC *v86; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v87; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v88; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v89; // [rsp+E0h] [rbp-28h]
  D3DGPU_SIZE_T v90; // [rsp+E8h] [rbp-20h]
  UINT64 DriverProtection; // [rsp+F0h] [rbp-18h]
  D3DGPU_VIRTUAL_ADDRESS v92; // [rsp+F8h] [rbp-10h]
  __int64 v93; // [rsp+100h] [rbp-8h]
  union _LARGE_INTEGER v94; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int64 v95; // [rsp+110h] [rbp+8h]
  CVirtualAddressAllocator *v96; // [rsp+118h] [rbp+10h]
  PRKSEMAPHORE Semaphore; // [rsp+120h] [rbp+18h]
  _BYTE v98[32]; // [rsp+128h] [rbp+20h] BYREF
  _QWORD v99[16]; // [rsp+148h] [rbp+40h] BYREF
  bool v103; // [rsp+208h] [rbp+100h]

  Semaphore = (PRKSEMAPHORE)((char *)a3 + 24);
  *a7 = (struct _KSEMAPHORE *)((char *)a3 + 24);
  v94.QuadPart = 0;
  v10 = KeWaitForSingleObject((char *)a3 + 24, Executive, 0, 0, &v94);
  if ( v10 == 258 )
  {
    WdLogSingleEntry0(3);
    result = 3223191810LL;
    WdLogGlobalForLineNumber = 28435;
    return result;
  }
  v12 = *((_QWORD *)a3 + 2);
  v13 = 0;
  v14 = *((_QWORD *)a3 + 1);
  v96 = *(CVirtualAddressAllocator **)a3;
  v82 = *(struct VIDMM_PROCESS **)(v12 + 8);
  v83 = *((_QWORD *)v96 + 2);
  v15 = *(_QWORD *)(v14 + 96);
  v87 = -1;
  v89 = -1;
  v85 = 0;
  v78 = *(unsigned __int16 *)(v15 + 6);
  *((_QWORD *)&v77 + 1) = &v77;
  *(_QWORD *)&v77 = &v77;
  v16 = (struct VIDMM_PROCESS *)*((_QWORD *)v96 + 13);
  FenceValue = a2->FenceValue;
  Timeout = a2->NumOperations;
  v88 = 0;
  v76 = 0;
  VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVa(this, 1u, v16, (struct _VIDSCH_CONTEXT *)v14, Timeout, a6, FenceValue);
  if ( byte_140086202 < 0 )
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
  for ( i = 0; ; v85 = i )
  {
    v81 = v20;
    if ( v20 >= a2->NumOperations )
    {
      if ( (a2->Flags.Value & 1) == 0 )
      {
        *((_BYTE *)a6 + 25) = 0;
        v10 = VidSchWaitForSingleSyncObject(*((_QWORD *)a3 + 1), a6, a2->FenceValue);
        if ( v10 < 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 28734;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            v56,
            (unsigned int)L"VidSchWaitForSingleSyncObject failed",
            28734,
            0,
            0,
            0);
          v51 = 16;
          goto LABEL_105;
        }
      }
      v57 = (char *)operator new(184, 959736150, 256);
      v13 = v57;
      if ( !v57 )
      {
        WdLogSingleEntry0(3);
        v13 = 0;
        WdLogGlobalForLineNumber = 28749;
        v51 = 17;
        v10 = -1073741801;
        goto LABEL_105;
      }
      memset(v57, 0, 0xB8u);
      v58 = v96;
      *((_QWORD *)v13 + 13) = v13 + 96;
      *((_QWORD *)v13 + 12) = v13 + 96;
      *((_QWORD *)v13 + 7) = v13 + 48;
      *((_QWORD *)v13 + 6) = v13 + 48;
      *((_QWORD *)v13 + 1) = this;
      *((_DWORD *)v13 + 5) = a2->NumOperations;
      *((_QWORD *)v13 + 10) = a2->FenceValue + 1;
      *((_DWORD *)v13 + 4) = v78;
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)v98,
        (CVirtualAddressAllocator *)((char *)v58 + 64));
      v59 = CVirtualAddressAllocator::ReferenceReservedZeroVad(v58, v87, i);
      if ( !v59 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 28770;
        v51 = 18;
LABEL_84:
        v10 = -1073741811;
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v98);
        goto LABEL_105;
      }
      v60 = 0;
      if ( v76 )
      {
        v60 = CVirtualAddressAllocator::ReferenceReservedZeroVad(v58, v89, v88);
        if ( !v60 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 28784;
          v51 = 19;
          goto LABEL_84;
        }
      }
      *((_QWORD *)v13 + 15) = v60;
      v61 = (char *)v59 + 80;
      *((_QWORD *)v13 + 14) = v59;
      *((_QWORD *)v13 + 18) = v13 + 112;
      *((_QWORD *)v13 + 21) = v13 + 120;
      v62 = (struct VIDMM_VAD **)*((_QWORD *)v59 + 11);
      if ( *v62 == (struct VIDMM_VAD *)((char *)v59 + 80) )
      {
        v63 = (char **)(v13 + 128);
        *((_QWORD *)v13 + 16) = v61;
        *((_QWORD *)v13 + 17) = v62;
        *v62 = (struct VIDMM_VAD *)(v13 + 128);
        *((_QWORD *)v59 + 11) = v13 + 128;
        if ( !v60 )
          goto LABEL_92;
        if ( *v63 == v61 )
        {
          *((_QWORD *)v13 + 19) = v61;
          *((_QWORD *)v13 + 20) = v63;
          *v63 = v13 + 152;
          *((_QWORD *)v59 + 11) = v13 + 152;
          v13[176] = 1;
LABEL_92:
          for ( j = (__int128 *)v77; j != &v77; j = *(__int128 **)j )
          {
            v65 = *((_QWORD *)j + 10) == 0;
            *((_QWORD *)j - 1) = v59;
            if ( v65 )
            {
              v66 = *((_QWORD *)v59 + 12);
              if ( v66 )
                *((_QWORD *)j + 10) = *(_QWORD *)(v66 + 80);
            }
          }
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v98);
          v67 = v13 + 32;
          *((_QWORD *)v13 + 8) = a5;
          v68 = v13 + 96;
          *((_DWORD *)v13 + 8) = a4;
          *((_QWORD *)v13 + 3) = a2->Operations;
          a2->Operations = 0;
          *((_QWORD *)v13 + 9) = a6;
          *((_QWORD *)v13 + 11) = a3;
          *(_QWORD *)v13 = *((_QWORD *)a3 + 1);
          if ( (__int128 *)v77 == &v77 )
          {
            *((_QWORD *)v13 + 13) = v13 + 96;
            *(_QWORD *)v68 = v68;
          }
          else
          {
            *(_OWORD *)v68 = v77;
            *(_QWORD *)(*(_QWORD *)v68 + 8LL) = v68;
            **((_QWORD **)v13 + 13) = v68;
          }
          *((_QWORD *)&v77 + 1) = &v77;
          *(_QWORD *)&v77 = &v77;
          _InterlockedIncrement((volatile signed __int32 *)a6 + 9);
          for ( k = 0; (unsigned int)k < *v67; k = (unsigned int)(k + 1) )
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v13 + 8) + 8 * k) + 696LL));
          memset(v99, 0, 0x50u);
          LODWORD(v99[5]) = 2;
          v99[3] = VIDMM_GLOBAL::VidMmiUpdateGpuVirtualAddress;
          v70 = *((_QWORD *)a3 + 1);
          LODWORD(v99[0]) = 2;
          v99[6] = v13;
          v99[4] = 0;
          VidSchSubmitGlobalCommand(*(_QWORD *)(*(_QWORD *)(v70 + 104) + 40LL), v99);
          return 0;
        }
      }
LABEL_113:
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
      v95 = BaseAddress;
      v79 = v38;
      if ( !(unsigned __int8)IsVirtualAddressRangeValid(BaseAddress, v38, v83) )
      {
        v51 = 1;
        goto LABEL_76;
      }
      v86 = a5[v22->Map.hAllocation];
      VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(this, v82, *((struct _VIDSCH_CONTEXT **)a3 + 1), v86, v22);
      AllocationSizeInBytes = v22->Map.AllocationSizeInBytes;
      if ( (AllocationSizeInBytes & 0xFFF) != 0
        || (AllocationOffsetInBytes = v22->Map.AllocationOffsetInBytes,
            v90 = AllocationOffsetInBytes,
            (AllocationOffsetInBytes & 0xFFF) != 0) )
      {
        WdLogSingleEntry1(3, v23);
        WdLogGlobalForLineNumber = 28508;
        v51 = 2;
        goto LABEL_76;
      }
      SizeInBytes = v22->Map.SizeInBytes;
      v84 = SizeInBytes;
      if ( AllocationSizeInBytes )
      {
        if ( AllocationSizeInBytes > SizeInBytes )
        {
          WdLogSingleEntry1(3, v23);
          WdLogGlobalForLineNumber = 28524;
          v51 = 3;
          goto LABEL_76;
        }
        if ( SizeInBytes % AllocationSizeInBytes )
        {
          WdLogSingleEntry1(3, v23);
          WdLogGlobalForLineNumber = 28533;
          v51 = 4;
          goto LABEL_76;
        }
        SizeInBytes = v84;
      }
      else
      {
        v22->Map.AllocationSizeInBytes = SizeInBytes;
        AllocationSizeInBytes = SizeInBytes;
      }
      if ( AllocationOffsetInBytes + AllocationSizeInBytes < AllocationOffsetInBytes
        || AllocationOffsetInBytes + AllocationSizeInBytes > *(_QWORD *)(***(_QWORD ***)v86 + 16LL) )
      {
        WdLogSingleEntry3(3, *(_QWORD *)(***(_QWORD ***)v86 + 16LL), v23, 28545);
        WdLogGlobalForLineNumber = 28545;
        v51 = 5;
        goto LABEL_76;
      }
      if ( (*((_BYTE *)this + 37225) & 2) != 0 )
      {
        LODWORD(v42) = 1;
        v93 = 1;
        v103 = SizeInBytes != AllocationSizeInBytes;
      }
      else
      {
        v42 = SizeInBytes / AllocationSizeInBytes;
        v93 = SizeInBytes / AllocationSizeInBytes;
        if ( SizeInBytes / AllocationSizeInBytes >= 0xFFFFFFFF )
        {
          WdLogSingleEntry1(3, v23);
          WdLogGlobalForLineNumber = 28569;
          v51 = 6;
          goto LABEL_76;
        }
        v103 = 0;
        v90 = 0;
        v84 = AllocationSizeInBytes;
      }
      v92 = BaseAddress;
      if ( v22->OperationType )
      {
        Value = v22->MapProtect.Protection.Value;
        DriverProtection = v22->MapProtect.DriverProtection;
      }
      else
      {
        DriverProtection = 0;
        Value = 1;
      }
      for ( m = 0; ; m = v80 + 1 )
      {
        v80 = m;
        if ( m >= (unsigned int)v42 )
          break;
        v45 = ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
        if ( !v45
          || (!v103 ? (v46 = 0) : (v46 = v22->Map.AllocationSizeInBytes >> 12),
              (v47 = VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(
                       v45,
                       v45,
                       0,
                       v92,
                       v92 + v84,
                       v78,
                       v86,
                       v22->Map.AllocationOffsetInBytes,
                       1,
                       Value,
                       DriverProtection,
                       v46,
                       v90,
                       0)) == 0) )
        {
          v51 = 7;
          _InterlockedIncrement(&dword_1400867F0);
          WdLogSingleEntry1(6, 7);
          WdLogGlobalForLineNumber = 28605;
          DxgkLogInternalTriageEvent(
            v54,
            262145,
            v55,
            (unsigned int)L"Failed to allocate VIDMM_MAPPED_VA_RANGE",
            7,
            0,
            0,
            0);
          goto LABEL_76;
        }
        v42 = *((_QWORD *)&v77 + 1);
        if ( **((__int128 ***)&v77 + 1) != &v77 )
          goto LABEL_113;
        v49 = (_QWORD *)(v47 + 8);
        v92 = v48;
        v49[1] = *((_QWORD *)&v77 + 1);
        *v49 = &v77;
        *(_QWORD *)v42 = v49;
        LODWORD(v42) = v93;
        *((_QWORD *)&v77 + 1) = v49;
      }
      v25 = v95;
      goto LABEL_54;
    }
    if ( OperationType == D3DDDI_UPDATEGPUVIRTUALADDRESS_UNMAP )
      break;
    if ( OperationType != D3DDDI_UPDATEGPUVIRTUALADDRESS_COPY )
      goto LABEL_70;
    v25 = v22->Unmap.Protection.Value;
    v79 = v25 + v22->Map.SizeInBytes;
    VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(this, v82, *((struct _VIDSCH_CONTEXT **)a3 + 1), 0, v22);
    if ( !(unsigned __int8)IsVirtualAddressRangeValid(v25, v79, v83) )
    {
      v51 = 10;
      goto LABEL_76;
    }
    v33 = v22->Map.BaseAddress;
    v34 = v33 + v22->Map.SizeInBytes;
    if ( v34 <= v33 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28664;
      v51 = 11;
      goto LABEL_76;
    }
    if ( (v33 & 0xFFF) != 0 || (v34 & 0xFFF) != 0 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28670;
      v51 = 12;
      goto LABEL_76;
    }
    if ( v25 < v34 && v79 > v33 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28677;
      v51 = 13;
      goto LABEL_76;
    }
    v35 = v89;
    v76 = 1;
    if ( v89 > v33 )
      v35 = v33;
    v89 = v35;
    v36 = v88;
    if ( v88 < v34 )
      v36 = v34;
    v88 = v36;
LABEL_54:
    if ( v79 <= v25 )
    {
LABEL_70:
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28704;
      v51 = 14;
      goto LABEL_76;
    }
    if ( ((v25 | v79) & 0xFFF) != 0 )
    {
      WdLogSingleEntry1(3, v23);
      WdLogGlobalForLineNumber = 28710;
      v51 = 15;
      goto LABEL_76;
    }
    v50 = v87;
    if ( v87 > v25 )
      v50 = v25;
    i = v85;
    v87 = v50;
    if ( v85 < v79 )
      i = v79;
    v20 = v81 + 1;
  }
  v25 = v22->Map.BaseAddress;
  v79 = v25 + v22->Map.SizeInBytes;
  VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(this, v82, *((struct _VIDSCH_CONTEXT **)a3 + 1), 0, v22);
  if ( !(unsigned __int8)IsVirtualAddressRangeValid(v25, v79, v83) )
  {
    v51 = 8;
    goto LABEL_76;
  }
  v28 = ExAllocateFromLookasideListEx(&g_VaRangeLookasideList);
  if ( v28 )
  {
    LOBYTE(v29) = -(v22->Unmap.Protection.Value & 8);
    v30 = VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(
            v28,
            v29,
            0,
            v25,
            v79,
            v78,
            0,
            0,
            (v22->Unmap.Protection.Value & 8) == 0 ? 6 : 0,
            v22->Unmap.Protection.Value,
            0,
            0,
            0,
            0);
    if ( v30 )
    {
      v31 = (_QWORD *)*((_QWORD *)&v77 + 1);
      if ( **((__int128 ***)&v77 + 1) != &v77 )
        goto LABEL_113;
      v32 = (_QWORD *)(v30 + 8);
      v32[1] = *((_QWORD *)&v77 + 1);
      *v32 = &v77;
      *v31 = v32;
      *((_QWORD *)&v77 + 1) = v32;
      goto LABEL_54;
    }
  }
  v51 = 9;
  _InterlockedIncrement(&dword_1400867F0);
  WdLogSingleEntry1(6, 9);
  WdLogGlobalForLineNumber = 28641;
  DxgkLogInternalTriageEvent(v52, 262145, v53, (unsigned int)L"Failed to allocate VIDMM_MAPPED_VA_RANGE", 9, 0, 0, 0);
LABEL_76:
  if ( v10 >= 0 )
    v10 = -1073741811;
LABEL_105:
  if ( byte_140086202 < 0 )
    McTemplateK0dq_EtwWriteTransfer(v26, UpdateGpuVirtualAddressFailure, v27, (unsigned int)v10, v51);
  VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaFailure(this, v82, v10, v51);
  KeReleaseSemaphore(Semaphore, 0, 1, 0);
  if ( v13 )
    VIDMM_DEVICE_COMMAND_UPDATEGPUVA::`scalar deleting destructor'((VIDMM_DEVICE_COMMAND_UPDATEGPUVA *)v13, v71);
  while ( 1 )
  {
    v72 = (_QWORD *)v77;
    if ( (__int128 *)v77 == &v77 )
      return (unsigned int)v10;
    if ( *(__int128 **)(v77 + 8) != &v77 )
      goto LABEL_113;
    v73 = *(_QWORD *)v77;
    if ( *(_QWORD *)(*(_QWORD *)v77 + 8LL) != (_QWORD)v77 )
      goto LABEL_113;
    *(_QWORD *)&v77 = *(_QWORD *)v77;
    *(_QWORD *)(v73 + 8) = &v77;
    *v72 = 0;
    v72[1] = 0;
    VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReference(v72 - 1);
  }
}

```

## disassembly

```asm
0x1401220bc  mov     rax, rsp
0x1401220bf  mov     [rax+10h], rbx
0x1401220c3  mov     [rax+20h], r9d
0x1401220c7  mov     [rax+18h], r8
0x1401220cb  mov     [rax+8], rcx
0x1401220cf  push    rbp
0x1401220d0  push    rsi
0x1401220d1  push    rdi
0x1401220d2  push    r12
0x1401220d4  push    r13
0x1401220d6  push    r14
0x1401220d8  push    r15
0x1401220da  lea     rbp, [rax-0C8h]
0x1401220e1  sub     rsp, 190h
0x1401220e8  mov     rax, [rbp+0C0h+arg_30]
0x1401220ef  mov     rbx, rcx
0x1401220f2  lea     rcx, [r8+18h]; Object
0x1401220f6  mov     r15, r8
0x1401220f9  mov     r13, rdx
0x1401220fc  mov     [rbp+0C0h+Semaphore], rcx
0x140122100  xor     esi, esi
0x140122102  xor     r9d, r9d; Alertable
0x140122105  mov     [rax], rcx
0x140122108  xor     r8d, r8d; WaitMode
0x14012210b  lea     rax, [rbp+0C0h+var_C0]
0x14012210f  mov     qword ptr [rbp+0C0h+var_C0], rsi
0x140122113  xor     edx, edx; WaitReason
0x140122115  mov     [rsp+1C0h+Timeout], rax; Timeout
0x14012211a  call    cs:__imp_KeWaitForSingleObject
0x140122121  nop     dword ptr [rax+rax+00h]
0x140122126  mov     r14d, eax
0x140122129  cmp     eax, 102h
0x14012212e  jnz     short loc_140122153
0x140122130  lea     ecx, [rsi+3]
0x140122133  call    cs:__imp_WdLogSingleEntry0
0x14012213a  nop     dword ptr [rax+rax+00h]
0x14012213f  mov     eax, 0C01E0102h
0x140122144  mov     cs:WdLogGlobalForLineNumber, 6F13h
0x14012214e  jmp     loc_140122CC6
0x140122153  mov     rcx, [r15]
0x140122156  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14012215a  mov     rax, [r15+10h]
0x14012215e  mov     rdi, rsi
0x140122161  mov     r9, [r15+8]; struct _VIDSCH_CONTEXT *
0x140122165  mov     r12, [rbp+0C0h+arg_28]
0x14012216c  mov     [rbp+0C0h+var_B0], rcx
0x140122170  mov     rax, [rax+8]
0x140122174  mov     [rbp+0C0h+var_120], rax
0x140122178  mov     rax, [rcx+10h]
0x14012217c  mov     [rbp+0C0h+var_118], rax
0x140122180  mov     rax, [r9+60h]
0x140122184  mov     [rbp+0C0h+var_F8], rdx
0x140122188  mov     [rbp+0C0h+var_E8], rdx
0x14012218c  mov     dl, 1; unsigned __int8
0x14012218e  mov     [rbp+0C0h+var_108], rsi
0x140122192  movzx   eax, word ptr [rax+6]
0x140122196  mov     [rbp+0C0h+var_138], eax
0x140122199  lea     rax, [rsp+1C0h+var_150+8]
0x14012219e  mov     [rbp+0C0h+var_140], rax
0x1401221a2  lea     rax, [rsp+1C0h+var_150+8]
0x1401221a7  mov     qword ptr [rsp+1C0h+var_150+8], rax
0x1401221ac  mov     rax, [r13+28h]
0x1401221b0  mov     r8, [rcx+68h]; struct VIDMM_PROCESS *
0x1401221b4  mov     rcx, rbx; this
0x1401221b7  mov     [rsp+1C0h+var_190], rax; unsigned __int64
0x1401221bc  mov     eax, [r13+0Ch]
0x1401221c0  mov     [rsp+1C0h+var_198], r12; struct _VIDSCH_SYNC_OBJECT *
0x1401221c5  mov     dword ptr [rsp+1C0h+Timeout], eax; unsigned int
0x1401221c9  mov     [rbp+0C0h+var_F0], rsi
0x1401221cd  mov     byte ptr [rsp+1C0h+var_150], sil
0x1401221d2  call    ?RecordVaPagingHistoryUpdateGpuVa@VIDMM_GLOBAL@@QEAAXEPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@IPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVa(uchar,VIDMM_PROCESS *,_VIDSCH_CONTEXT *,uint,_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x1401221d7  cmp     cs:byte_140086202, sil
0x1401221de  jge     short loc_140122220
0x1401221e0  mov     rax, [r15+8]
0x1401221e4  mov     r9d, [r13+0]
0x1401221e8  mov     [rsp+1C0h+var_170], rax
0x1401221ed  mov     rax, [r13+28h]
0x1401221f1  mov     [rsp+1C0h+var_178], r12
0x1401221f6  mov     [rsp+1C0h+var_180], rax
0x1401221fb  mov     eax, [r13+30h]
0x1401221ff  mov     dword ptr [rsp+1C0h+var_188], eax
0x140122203  mov     eax, [r13+0Ch]
0x140122207  mov     dword ptr [rsp+1C0h+var_190], eax
0x14012220b  mov     eax, [r13+8]
0x14012220f  mov     dword ptr [rsp+1C0h+var_198], eax
0x140122213  mov     eax, [r13+4]
0x140122217  mov     dword ptr [rsp+1C0h+Timeout], eax
0x14012221b  call    McTemplateK0qqqqqxpp_EtwWriteTransfer
0x140122220  mov     eax, esi
0x140122222  mov     esi, 3
0x140122227  mov     ebx, eax
0x140122229  mov     [rbp+0C0h+var_124], eax
0x14012222c  cmp     eax, [r13+0Ch]
0x140122230  jnb     loc_1401228DD
0x140122236  mov     r12d, eax
0x140122239  shl     r12, 6
0x14012223d  add     r12, [r13+10h]
0x140122241  mov     r15d, eax
0x140122244  mov     eax, [r12]
0x140122248  test    eax, eax
0x14012224a  jz      loc_14012241B
0x140122250  cmp     eax, esi
0x140122252  jz      loc_14012241B
0x140122258  cmp     eax, 1
0x14012225b  jnz     loc_14012235F
0x140122261  mov     rbx, [r12+8]
0x140122266  xor     r9d, r9d; struct VIDMM_ALLOC *
0x140122269  mov     rax, [r12+10h]
0x14012226e  mov     rdx, [rbp+0C0h+var_120]; struct VIDMM_PROCESS *
0x140122272  add     rax, rbx
0x140122275  mov     rcx, [rbp+0C0h+arg_0]; this
0x14012227c  mov     [rbp+0C0h+var_130], rax
0x140122280  mov     rax, [rbp+0C0h+arg_10]
0x140122287  mov     [rsp+1C0h+Timeout], r12; struct _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *
0x14012228c  mov     r8, [rax+8]; struct _VIDSCH_CONTEXT *
0x140122290  call    ?RecordVaPagingHistoryUpdateGpuVaOp@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@PEAUVIDMM_ALLOC@@PEAU_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION@@@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(VIDMM_PROCESS *,_VIDSCH_CONTEXT *,VIDMM_ALLOC *,_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *)
0x140122295  mov     r8, [rbp+0C0h+var_118]
0x140122299  mov     rcx, rbx
0x14012229c  mov     rdx, [rbp+0C0h+var_130]
0x1401222a0  call    IsVirtualAddressRangeValid
0x1401222a5  test    al, al
0x1401222a7  jz      loc_1401226DF
0x1401222ad  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1401222b4  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401222bb  nop     dword ptr [rax+rax+00h]
0x1401222c0  test    rax, rax
0x1401222c3  jz      loc_14012269C
0x1401222c9  mov     rcx, [r12+18h]
0x1401222ce  mov     r9, rbx
0x1401222d1  mov     dl, cl
0x1401222d3  and     dl, 8
0x1401222d6  neg     dl
0x1401222d8  sbb     r8d, r8d
0x1401222db  xor     r12d, r12d
0x1401222de  mov     dword ptr [rsp+1C0h+var_158], r12d
0x1401222e3  not     r8d
0x1401222e6  mov     qword ptr [rsp+1C0h+var_160], r12
0x1401222eb  and     r8d, 6
0x1401222ef  mov     [rsp+1C0h+var_168], r12
0x1401222f4  mov     [rsp+1C0h+var_170], r12
0x1401222f9  mov     [rsp+1C0h+var_178], rcx
0x1401222fe  mov     ecx, [rbp+0C0h+var_138]
0x140122301  mov     dword ptr [rsp+1C0h+var_180], r8d
0x140122306  xor     r8d, r8d
0x140122309  mov     [rsp+1C0h+var_188], r12
0x14012230e  mov     [rsp+1C0h+var_190], r12
0x140122313  mov     dword ptr [rsp+1C0h+var_198], ecx
0x140122317  mov     rcx, [rbp+0C0h+var_130]
0x14012231b  mov     [rsp+1C0h+Timeout], rcx
0x140122320  mov     rcx, rax
0x140122323  call    ??0VIDMM_MAPPED_VA_RANGE@@QEAA@PEAVCVirtualAddressAllocator@@PEAUVIDMM_VAD@@_K2IPEAX2W4VIDMM_VAD_OWNER_TYPE@@U_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@222K@Z; VIDMM_MAPPED_VA_RANGE::VIDMM_MAPPED_VA_RANGE(CVirtualAddressAllocator *,VIDMM_VAD *,unsigned __int64,unsigned __int64,uint,void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,ulong)
0x140122328  test    rax, rax
0x14012232b  jz      loc_14012269F
0x140122331  mov     rcx, [rbp+0C0h+var_140]
0x140122335  lea     rdx, [rsp+1C0h+var_150+8]
0x14012233a  cmp     [rcx], rdx
0x14012233d  jnz     loc_140122CBE
0x140122343  add     rax, 8
0x140122347  lea     rdx, [rsp+1C0h+var_150+8]
0x14012234c  mov     [rax+8], rcx
0x140122350  mov     [rax], rdx
0x140122353  mov     [rcx], rax
0x140122356  mov     [rbp+0C0h+var_140], rax
0x14012235a  jmp     loc_140122655
0x14012235f  cmp     eax, 2
0x140122362  jnz     loc_140122805
0x140122368  mov     rbx, [r12+18h]
0x14012236d  xor     r9d, r9d; struct VIDMM_ALLOC *
0x140122370  mov     rax, [r12+10h]
0x140122375  mov     rdx, [rbp+0C0h+var_120]; struct VIDMM_PROCESS *
0x140122379  add     rax, rbx
0x14012237c  mov     rcx, [rbp+0C0h+arg_0]; this
0x140122383  mov     [rbp+0C0h+var_130], rax
0x140122387  mov     rax, [rbp+0C0h+arg_10]
0x14012238e  mov     [rsp+1C0h+Timeout], r12; struct _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *
0x140122393  mov     r8, [rax+8]; struct _VIDSCH_CONTEXT *
0x140122397  call    ?RecordVaPagingHistoryUpdateGpuVaOp@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@PEAUVIDMM_ALLOC@@PEAU_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION@@@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(VIDMM_PROCESS *,_VIDSCH_CONTEXT *,VIDMM_ALLOC *,_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *)
0x14012239c  mov     r8, [rbp+0C0h+var_118]
0x1401223a0  mov     rcx, rbx
0x1401223a3  mov     rdx, [rbp+0C0h+var_130]
0x1401223a7  call    IsVirtualAddressRangeValid
0x1401223ac  test    al, al
0x1401223ae  jz      loc_140122758
0x1401223b4  mov     rcx, [r12+8]
0x1401223b9  mov     rdx, [r12+10h]
0x1401223be  add     rdx, rcx
0x1401223c1  cmp     rdx, rcx
0x1401223c4  jbe     loc_140122733
0x1401223ca  test    rcx, 0FFFh
0x1401223d1  jnz     loc_14012270E
0x1401223d7  test    rdx, 0FFFh
0x1401223de  jnz     loc_14012270E
0x1401223e4  cmp     rbx, rdx
0x1401223e7  jnb     short loc_1401223F3
0x1401223e9  cmp     [rbp+0C0h+var_130], rcx
0x1401223ed  ja      loc_1401226E9
0x1401223f3  mov     rax, [rbp+0C0h+var_E8]
0x1401223f7  cmp     rax, rcx
0x1401223fa  mov     byte ptr [rsp+1C0h+var_150], 1
0x1401223ff  cmova   rax, rcx
0x140122403  mov     [rbp+0C0h+var_E8], rax
0x140122407  mov     rax, [rbp+0C0h+var_F0]
0x14012240b  cmp     rax, rdx
0x14012240e  cmovb   rax, rdx
0x140122412  mov     [rbp+0C0h+var_F0], rax
0x140122416  jmp     loc_140122655
0x14012241b  mov     rbx, [r12+8]
0x140122420  mov     rax, [r12+10h]
0x140122425  mov     rcx, rbx
0x140122428  mov     r8, [rbp+0C0h+var_118]
0x14012242c  add     rax, rbx
0x14012242f  mov     rdx, rax
0x140122432  mov     [rbp+0C0h+var_B8], rbx
0x140122436  mov     [rbp+0C0h+var_130], rax
0x14012243a  call    IsVirtualAddressRangeValid
0x14012243f  test    al, al
0x140122441  jz      loc_1401228C4
0x140122447  mov     eax, [r12+18h]
0x14012244c  mov     rcx, [rbp+0C0h+arg_20]
0x140122453  mov     rdx, [rbp+0C0h+var_120]; struct VIDMM_PROCESS *
0x140122457  mov     [rsp+1C0h+Timeout], r12; struct _D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *
0x14012245c  mov     rax, [rcx+rax*8]
0x140122460  mov     rcx, [rbp+0C0h+arg_0]; this
0x140122467  mov     r9, rax; struct VIDMM_ALLOC *
0x14012246a  mov     [rbp+0C0h+var_100], rax
0x14012246e  mov     rax, [rbp+0C0h+arg_10]
0x140122475  mov     r8, [rax+8]; struct _VIDSCH_CONTEXT *
0x140122479  call    ?RecordVaPagingHistoryUpdateGpuVaOp@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_PROCESS@@PEAU_VIDSCH_CONTEXT@@PEAUVIDMM_ALLOC@@PEAU_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION@@@Z; VIDMM_GLOBAL::RecordVaPagingHistoryUpdateGpuVaOp(VIDMM_PROCESS *,_VIDSCH_CONTEXT *,VIDMM_ALLOC *,_D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *)
0x14012247e  mov     r8, [r12+28h]
0x140122483  test    r8, 0FFFh
0x14012248a  jnz     loc_1401228A2
0x140122490  mov     r10, [r12+20h]
0x140122495  mov     [rbp+0C0h+var_E0], r10
0x140122499  test    r10, 0FFFh
0x1401224a0  jnz     loc_1401228A2
0x1401224a6  mov     rax, [r12+10h]
0x1401224ab  mov     [rbp+0C0h+var_110], rax
0x1401224af  test    r8, r8
0x1401224b2  jnz     short loc_1401224BE
0x1401224b4  mov     [r12+28h], rax
0x1401224b9  mov     r8, rax
0x1401224bc  jmp     short loc_1401224D9
0x1401224be  cmp     r8, rax
0x1401224c1  ja      loc_140122883
0x1401224c7  xor     edx, edx
0x1401224c9  div     r8
0x1401224cc  test    rdx, rdx
0x1401224cf  jnz     loc_140122861
0x1401224d5  mov     rax, [rbp+0C0h+var_110]
0x1401224d9  lea     r9, [r10+r8]
0x1401224dd  cmp     r9, r10
0x1401224e0  jb      loc_14012282A
0x1401224e6  mov     rcx, [rbp+0C0h+var_100]
0x1401224ea  mov     rcx, [rcx]
0x1401224ed  mov     rdx, [rcx]
0x1401224f0  mov     rcx, [rdx]
0x1401224f3  cmp     r9, [rcx+10h]
0x1401224f7  ja      loc_14012282A
0x1401224fd  mov     rcx, [rbp+0C0h+arg_0]
0x140122504  test    byte ptr [rcx+9169h], 2
0x14012250b  jnz     short loc_140122538
0x14012250d  xor     edx, edx
0x14012250f  div     r8
0x140122512  mov     rcx, rax
0x140122515  mov     [rbp+0C0h+var_C8], rax
0x140122519  mov     eax, 0FFFFFFFFh
0x14012251e  cmp     rcx, rax
0x140122521  jnb     loc_140122762
0x140122527  mov     byte ptr [rbp+0C0h+arg_30], dil
0x14012252e  mov     [rbp+0C0h+var_E0], rdi
0x140122532  mov     [rbp+0C0h+var_110], r8
0x140122536  jmp     short loc_14012254B
0x140122538  cmp     rax, r8
0x14012253b  mov     ecx, 1
0x140122540  mov     [rbp+0C0h+var_C8], rcx
0x140122544  setnz   byte ptr [rbp+0C0h+arg_30]
0x14012254b  mov     [rbp+0C0h+var_D0], rbx
0x14012254f  cmp     [r12], edi
0x140122553  jnz     short loc_140122560
0x140122555  mov     [rbp+0C0h+var_D8], rdi
0x140122559  mov     ebx, 1
0x14012255e  jmp     short loc_14012256E
0x140122560  mov     rax, [r12+38h]
0x140122565  mov     rbx, [r12+30h]
0x14012256a  mov     [rbp+0C0h+var_D8], rax
0x14012256e  xor     eax, eax
0x140122570  mov     [rbp+0C0h+var_128], eax
0x140122573  cmp     eax, ecx
0x140122575  jnb     loc_140122651
0x14012257b  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140122582  call    cs:__imp_ExAllocateFromLookasideListEx
0x140122589  nop     dword ptr [rax+rax+00h]
0x14012258e  mov     rdx, rax
0x140122591  test    rax, rax
0x140122594  jz      loc_140122787
0x14012259a  mov     r10, [rbp+0C0h+var_110]
0x14012259e  mov     r9, [rbp+0C0h+var_D0]
0x1401225a2  add     r10, r9
0x1401225a5  cmp     byte ptr [rbp+0C0h+arg_30], dil
0x1401225ac  jz      short loc_1401225B9
  ... truncated ...
```
