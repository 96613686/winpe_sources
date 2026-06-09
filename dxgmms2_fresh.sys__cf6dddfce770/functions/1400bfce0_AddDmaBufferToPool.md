# AddDmaBufferToPool

- ea: `0x1400bfce0`
- end: `0x1400c0780`
- name: `AddDmaBufferToPool`
- size: `2720`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b3730`
- `0x1400c0fa0`
- `0x1400fd490`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002e6c0`
- `0x14002ed58`
- `0x14002fd50`
- `0x14002fe98`
- `0x140030854`
- `0x14003cf34`
- `0x140059380`
- `0x1400995d8`
- `0x1400b4cd8`
- `0x1400bfce0`
- `0x1400e827c`
- `0x1400ea180`
- `0x1400f24e0`
- `0x1400fdc1c`
- `0x1400feb90`
- `0x1400ff470`
- `0x1400ffd4c`
- `0x14010167c`
- `0x1401104a4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400c0604`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400c0604`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400c0240`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400c0240`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400c025f`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400c025f`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x1400c074d`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x1400c074d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bfd1e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400c0569`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400c061c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bfd1e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400c0569`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400c061c`
- `watchdog!WdLogSingleEntry0` at `0x1400bfdba`
- `watchdog!WdLogSingleEntry0` at `0x1400bfe10`
- `watchdog!WdLogSingleEntry0` at `0x1400bfe7c`
- `watchdog!WdLogSingleEntry0` at `0x1400bffce`
- `watchdog!WdLogSingleEntry0` at `0x1400c0049`
- `watchdog!WdLogSingleEntry0` at `0x1400c0113`
- `watchdog!WdLogSingleEntry0` at `0x1400c02b0`
- `watchdog!WdLogSingleEntry0` at `0x1400c030e`
- `watchdog!WdLogSingleEntry0` at `0x1400c035c`
- `watchdog!WdLogSingleEntry0` at `0x1400c0698`
- `watchdog!WdLogSingleEntry0` at `0x1400bfdba`
- `watchdog!WdLogSingleEntry0` at `0x1400bfe10`
- `watchdog!WdLogSingleEntry0` at `0x1400bfe7c`
- `watchdog!WdLogSingleEntry0` at `0x1400bffce`
- `watchdog!WdLogSingleEntry0` at `0x1400c0049`
- `watchdog!WdLogSingleEntry0` at `0x1400c0113`
- `watchdog!WdLogSingleEntry0` at `0x1400c02b0`
- `watchdog!WdLogSingleEntry0` at `0x1400c030e`
- `watchdog!WdLogSingleEntry0` at `0x1400c035c`
- `watchdog!WdLogSingleEntry0` at `0x1400c0698`
- `watchdog!WdLogSingleEntry1` at `0x1400c01e4`
- `watchdog!WdLogSingleEntry1` at `0x1400c01e4`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400bfd03`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400c0553`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400c0610`

## string_xrefs

- `0x1400bfe21`: `Can't create regular DMA buffer with no associated allocation list`
- `0x1400bffdf`: `Couldn't create a global allocation for DMA the buffer.`
- `0x1400c005a`: `Couldn't open the global allocation for the DMA buffer.`

## pseudocode

```c
__int64 __fastcall AddDmaBufferToPool(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  unsigned int v4; // ebx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // r12
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ecx
  int v11; // r8d
  __int64 v12; // rax
  const wchar_t *v13; // r9
  int v15; // ecx
  int v16; // r8d
  char *v17; // rdi
  unsigned int v18; // r8d
  int v19; // ecx
  __int64 v20; // r10
  int v21; // edx
  struct VIDMM_DEVICE *v22; // rdx
  int v23; // r14d
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // rax
  const wchar_t *v27; // r9
  int v28; // edx
  __int64 *v29; // rbx
  __int64 v30; // r15
  __int64 v31; // rax
  unsigned int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // ecx
  int v36; // r8d
  __int64 v37; // rax
  const wchar_t *v38; // r9
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  struct _VIDSCH_SYNC_OBJECT **v42; // r13
  VIDMM_GLOBAL *v43; // rcx
  int Resident; // eax
  __int64 v45; // r8
  void *ContiguousNodeMemory; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  unsigned int v51; // eax
  __int64 v52; // rax
  _QWORD *v53; // r8
  VIDMM_PROCESS_ADAPTER_INFO *v54; // rbx
  __int64 v55; // rax
  _QWORD *v56; // rax
  __int64 v57; // rdx
  struct CVirtualAddressAllocator *VirtualAddressAllocator; // rbx
  _QWORD *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  void *v62; // r15
  __int64 v63; // rax
  struct _ERESOURCE *v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // ecx
  int v68; // r8d
  __int64 **v69; // rdx
  struct VIDMM_GLOBAL_ALLOC *v70; // r8
  void *v71; // rcx
  int v72; // [rsp+68h] [rbp-F8h]
  int v73; // [rsp+70h] [rbp-F0h]
  unsigned __int64 v74; // [rsp+E0h] [rbp-80h] BYREF
  unsigned __int64 v75; // [rsp+E8h] [rbp-78h] BYREF
  struct VIDMM_MULTI_ALLOC *v76; // [rsp+F0h] [rbp-70h] BYREF
  _QWORD v77[12]; // [rsp+100h] [rbp-60h] BYREF
  char v78; // [rsp+1A0h] [rbp+40h] BYREF
  SIZE_T NumberOfBytes; // [rsp+1A8h] [rbp+48h]
  unsigned int v80; // [rsp+1B8h] [rbp+58h]

  v80 = a4;
  LODWORD(NumberOfBytes) = a2;
  v4 = a4;
  v5 = (unsigned int)a2;
  LODWORD(v6) = a3;
  if ( g_IsInternalReleaseOrDbg )
  {
    *(_QWORD *)(WdLogNewEntry5_WdTrace(a1, a2) + 24) = a1;
    WdLogGlobalForLineNumber = 431;
  }
  if ( *(_DWORD *)(a1 + 84) > (unsigned int)dword_140087A50 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    if ( !v8
      || (v9 = *(_QWORD *)(v8 + 24), *(_DWORD *)(v9 + 464) != 2) && (*(_DWORD *)(*(_QWORD *)(v9 + 40) + 408LL) & 4) == 0 )
    {
      if ( qword_140087A38 > qword_140087A30 || qword_140087A08 > qword_140087A00 || qword_1400879D8 > qword_1400879D0 )
      {
        _InterlockedAdd(&dword_140087758, 1u);
        WdLogSingleEntry0(6);
        v12 = 447;
        v13 = L"Reach the maximum size for the DMA pools.\n";
LABEL_11:
        WdLogGlobalForLineNumber = v12;
        DxgkLogInternalTriageEvent(v10, 262145, v11, (_DWORD)v13, v12, 0, 0, 0);
        return 3221225495LL;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 36) & 1) == 0 && !(_DWORD)v6 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 458;
    DxgkLogInternalTriageEvent(
      v15,
      0x40000,
      v16,
      (unsigned int)L"Can't create regular DMA buffer with no associated allocation list",
      458,
      0,
      0,
      0);
    return 3221225485LL;
  }
  v17 = (char *)operator new(160, 842164566, 64);
  if ( !v17 )
  {
    _InterlockedAdd(&dword_1400876B0, 1u);
    WdLogSingleEntry0(6);
    v12 = 470;
    v13 = L"Couldn't allocate memory for DMA buffer object.";
    goto LABEL_11;
  }
  v18 = *(_DWORD *)(a1 + 40);
  if ( v18 )
  {
    if ( (*(_DWORD *)(a1 + 36) & 1) != 0 )
      v19 = ((~*(_BYTE *)(*(_QWORD *)(a1 + 16) + 1348LL) & 0x80) << 8) | 0x10000040;
    else
      v19 = *(_BYTE *)(*(_QWORD *)(a1 + 24) + 430LL) != 0 ? 72 : 32840;
    v20 = *(_QWORD *)a1;
    v21 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 444LL);
    if ( (v21 & 8) != 0 || (v21 & 0x10) != 0 )
      v19 |= 4u;
    v22 = *(struct VIDMM_DEVICE **)(a1 + 8);
    v78 = 0;
    v23 = VIDMM_GLOBAL::CreateOneAllocation(
            v20,
            v22,
            *(_DWORD *)(a1 + 32),
            v5,
            v5,
            0,
            0,
            0,
            v18,
            0,
            0,
            0,
            v19,
            0,
            0,
            0,
            0,
            0,
            0,
            -1610612736,
            0,
            0,
            0,
            0,
            0,
            v17 + 48,
            &v78);
    if ( v23 < 0 )
    {
      _InterlockedAdd(&dword_1400876B8, 1u);
      WdLogSingleEntry0(6);
      v26 = 541;
      v27 = L"Couldn't create a global allocation for DMA the buffer.";
LABEL_26:
      WdLogGlobalForLineNumber = v26;
      v28 = 262145;
LABEL_27:
      DxgkLogInternalTriageEvent(v24, v28, v25, (_DWORD)v27, v26, 0, 0, 0);
      goto LABEL_79;
    }
    v29 = (__int64 *)(v17 + 56);
    v23 = VIDMM_GLOBAL::OpenOneAllocation(
            *(VIDMM_GLOBAL **)a1,
            *(struct VIDMM_DEVICE **)(a1 + 8),
            *((struct VIDMM_GLOBAL_ALLOC **)v17 + 6),
            0,
            0,
            (struct VIDMM_ALLOC **)v17 + 7);
    if ( v23 < 0 )
    {
      _InterlockedAdd(&dword_1400876BC, 1u);
      WdLogSingleEntry0(6);
      v26 = 558;
      v27 = L"Couldn't open the global allocation for the DMA buffer.";
      goto LABEL_26;
    }
    v30 = *v29;
    if ( (*(_DWORD *)(*v29 + 28) & 3) == 0 )
    {
      if ( (*(_DWORD *)(a1 + 36) & 1) != 0 )
      {
        memset(v77, 0, 0x58u);
        v31 = *(_QWORD *)v30;
        LODWORD(v77[0]) = 104;
        v77[2] = v30;
        HIDWORD(v77[0]) = (*(_DWORD *)(**(_QWORD **)v31 + 60LL) >> 2) & 0x3F;
        VIDMM_GLOBAL::QueueSystemCommandAndWait(*(VIDMM_GLOBAL **)a1, (struct VIDMM_SYSTEM_COMMAND *)v77, 1);
      }
      else
      {
        v39 = *(_QWORD *)(v30 + 8);
        v40 = 32LL * *(unsigned int *)(a1 + 32);
        v74 = 0;
        v41 = *(_QWORD *)(v39 + 72);
        v75 = 0;
        v42 = *(struct _VIDSCH_SYNC_OBJECT ***)(v40 + v41);
        v43 = *(VIDMM_GLOBAL **)a1;
        v76 = (struct VIDMM_MULTI_ALLOC *)v30;
        Resident = VIDMM_GLOBAL::MakeResident(v43, (struct VIDMM_PAGING_QUEUE *)v42, &v76, 1u, 3u, &v74, &v75);
        v23 = Resident;
        if ( Resident == 259 )
        {
          VIDMM_GLOBAL::WaitForFence(*(VIDMM_GLOBAL **)a1, v42[11], v74);
          v23 = 0;
        }
        else if ( Resident < 0 )
        {
          WdLogSingleEntry1(1, *v29);
          WdLogGlobalForLineNumber = 590;
          v27 = L"Couldn't page in the new DMA buffer 0x%p.";
          v26 = *v29;
          v28 = 0x40000;
          goto LABEL_27;
        }
      }
    }
    LODWORD(v5) = NumberOfBytes;
    v4 = v80;
  }
  else
  {
    v45 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 2528LL);
    *((_DWORD *)v17 + 18) = 2;
    ContiguousNodeMemory = (void *)MmAllocateContiguousNodeMemory(v5, 0, v45, 0, 1028, 0x80000000);
    *((_QWORD *)v17 + 8) = ContiguousNodeMemory;
    if ( !ContiguousNodeMemory )
    {
      _InterlockedAdd(&dword_1400876C4, 1u);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 621;
      DxgkLogInternalTriageEvent(
        v67,
        262145,
        v68,
        (unsigned int)L"Couldn't allocate a contiguous buffer for the DMA buffer.",
        621,
        0,
        0,
        0);
      goto LABEL_78;
    }
    v23 = 0;
    *((PHYSICAL_ADDRESS *)v17 + 10) = MmGetPhysicalAddress(ContiguousNodeMemory);
  }
  if ( (_DWORD)v6 )
  {
    v32 = 3;
    if ( (unsigned int)v6 > 3 )
      v32 = v6;
    v6 = v32;
    v33 = 8LL * v32;
    if ( !is_mul_ok(v32, 8u) )
      v33 = -1;
    v34 = operator new[](v33, 858941782, 64);
    *((_QWORD *)v17 + 12) = v34;
    if ( !v34 )
    {
      _InterlockedAdd(&dword_1400876D0, 1u);
      WdLogSingleEntry0(6);
      v37 = 648;
      v38 = L"Couldn't allocate memory for the DMA buffer allocation table.";
LABEL_41:
      WdLogGlobalForLineNumber = v37;
      DxgkLogInternalTriageEvent(v35, 262145, v36, (_DWORD)v38, v37, 0, 0, 0);
LABEL_78:
      v23 = -1073741801;
      goto LABEL_79;
    }
    v47 = 24 * v6;
    if ( !is_mul_ok(v6, 0x18u) )
      v47 = -1;
    v48 = operator new[](v47, 875718998, 64);
    *((_QWORD *)v17 + 13) = v48;
    if ( !v48 )
    {
      _InterlockedAdd(&dword_1400876C8, 1u);
      WdLogSingleEntry0(6);
      v37 = 661;
      v38 = L"Couldn't allocate memory for the DMA buffer allocation list.";
      goto LABEL_41;
    }
  }
  if ( v4 )
  {
    v49 = 24LL * v4;
    if ( !is_mul_ok(v4, 0x18u) )
      v49 = -1;
    v50 = operator new[](v49, 892496214, 256);
    *((_QWORD *)v17 + 14) = v50;
    if ( !v50 )
    {
      _InterlockedAdd(&dword_1400876CC, 1u);
      WdLogSingleEntry0(6);
      v37 = 677;
      v38 = L"Couldn't allocate memory for the DMA buffer patch location list.\n";
      goto LABEL_41;
    }
  }
  v51 = *(_DWORD *)(a1 + 80);
  if ( v51 )
  {
    v52 = operator new[](v51, 842230102, 64);
    *((_QWORD *)v17 + 15) = v52;
    if ( !v52 )
    {
      _InterlockedAdd(&dword_140087730, 1u);
      WdLogSingleEntry0(6);
      v37 = 690;
      v38 = L"Couldn't allocate the private data for the DMA buffer.\n";
      goto LABEL_41;
    }
  }
  *((_DWORD *)v17 + 9) = v5;
  *((_DWORD *)v17 + 10) = v6;
  *((_DWORD *)v17 + 11) = v4;
  *((_QWORD *)v17 + 16) = a1;
  *((_QWORD *)v17 + 19) = 0;
  if ( (*(_DWORD *)(a1 + 36) & 0x10) == 0 )
    goto LABEL_63;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 431LL) )
  {
    *((_QWORD *)v17 + 11) = *(_QWORD *)(*((_QWORD *)v17 + 7) + 680LL);
    goto LABEL_63;
  }
  VirtualAddressAllocator = VIDMM_PROCESS::GetVirtualAddressAllocator(
                              *(VIDMM_PROCESS **)(*(_QWORD *)(a1 + 8) + 8LL),
                              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 240LL),
                              *(_DWORD *)(a1 + 32));
  if ( !VirtualAddressAllocator )
    goto LABEL_78;
  LOBYTE(v73) = 0;
  LOBYTE(v72) = 1;
  v59 = (_QWORD *)CVirtualAddressAllocator::MapVirtualAddressRange(
                    VirtualAddressAllocator,
                    *((_QWORD *)v17 + 7),
                    0,
                    1,
                    (unsigned int)v5,
                    0,
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 3080LL),
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 3088LL),
                    4096,
                    (*(_DWORD *)(*(_QWORD *)a1 + 40LL) < 0x6000u) | 0x12LL,
                    0,
                    *(_DWORD *)(a1 + 32),
                    0,
                    v72,
                    v73);
  v62 = v59;
  if ( !v59 )
  {
    v23 = -1073741823;
    if ( g_IsInternalReleaseOrDbg )
    {
      v63 = WdLogNewEntry5_WdTrace(v61, v60);
      *(_QWORD *)(v63 + 24) = v17;
      *(_QWORD *)(v63 + 32) = a1;
      WdLogGlobalForLineNumber = 754;
    }
    goto LABEL_79;
  }
  *((_QWORD *)v17 + 11) = v59[13];
  v23 = VIDMM_GLOBAL::CommitVirtualAddressRange(
          *(VIDMM_GLOBAL **)a1,
          0,
          VirtualAddressAllocator,
          *(struct VIDMM_PAGING_QUEUE **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v17 + 7) + 8LL) + 72LL)
                                        + 32LL * *(unsigned int *)(a1 + 32)),
          (struct VIDMM_MAPPED_VA_RANGE *)v59,
          (const struct _DXGK_ADL *)&xmmword_14005DEF0,
          0,
          0);
  VIDMM_MAPPED_VA_RANGE::ReleaseVaRangeReferenceSafe(v62, VirtualAddressAllocator);
  if ( v23 >= 0 )
  {
LABEL_63:
    *(_DWORD *)(a1 + 36) &= ~8u;
    *(_DWORD *)(a1 + 120) += *((_DWORD *)v17 + 9);
    v53 = *(_QWORD **)(a1 + 8);
    *(_DWORD *)(a1 + 124) += 24 * *((_DWORD *)v17 + 10);
    *(_DWORD *)(a1 + 128) += 24 * *((_DWORD *)v17 + 11);
    if ( v53 )
    {
      v54 = *(VIDMM_PROCESS_ADAPTER_INFO **)(*(_QWORD *)(v53[1] + 32LL)
                                           + 8LL * *(unsigned int *)(*(_QWORD *)(*v53 + 24LL) + 240LL));
      VIDMM_PROCESS_ADAPTER_INFO::AcquireProcessAdapterInfoLock(v54);
      v55 = *((_QWORD *)v54 + 23);
      *(_QWORD *)(v55 + 8) += *((unsigned int *)v17 + 9);
      ++*(_DWORD *)v55;
      *(_DWORD *)(*((_QWORD *)v54 + 23) + 16LL) += 24 * *((_DWORD *)v17 + 10);
      *(_DWORD *)(*((_QWORD *)v54 + 23) + 20LL) += 24 * *((_DWORD *)v17 + 11);
      VIDMM_PROCESS_ADAPTER_INFO::ReleaseProcessAdapterInfoLock(v54);
    }
    _InterlockedAdd64(&qword_140087A38, *((unsigned int *)v17 + 9));
    _InterlockedAdd64(&qword_140087A08, 24LL * *((unsigned int *)v17 + 10));
    _InterlockedAdd64(&qword_1400879D8, 24LL * *((unsigned int *)v17 + 11));
    ++*(_DWORD *)(a1 + 84);
    LockAllPoolForAddRemove(0);
    v56 = (_QWORD *)(a1 + 88);
    v57 = *(_QWORD *)(a1 + 88);
    if ( *(_QWORD *)(v57 + 8) != a1 + 88 )
      __fastfail(3u);
    v64 = Resource;
    *(_QWORD *)v17 = v57;
    *((_QWORD *)v17 + 1) = v56;
    *(_QWORD *)(v57 + 8) = v17;
    *v56 = v17;
    ExReleaseResourceLite(v64);
    if ( g_IsInternalReleaseOrDbg )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace(v66, v65) + 24) = v17;
      WdLogGlobalForLineNumber = 840;
    }
    if ( (byte_140087201 & 1) != 0 )
      McTemplateK0pppxxxp_EtwWriteTransfer(
        *((_DWORD *)v17 + 11),
        (unsigned int)&EventAddDmaBuffer,
        *((_DWORD *)v17 + 9),
        *(_QWORD *)(a1 + 24),
        *(_QWORD *)(*(_QWORD *)a1 + 24LL),
        (char)v17,
        *((_DWORD *)v17 + 9),
        *((_DWORD *)v17 + 10),
        *((_DWORD *)v17 + 11),
        *((_QWORD *)v17 + 6));
    return (unsigned int)v23;
  }
LABEL_79:
  operator delete(*((void **)v17 + 15));
  operator delete(*((void **)v17 + 14));
  operator delete(*((void **)v17 + 13));
  operator delete(*((void **)v17 + 12));
  v69 = (__int64 **)*((_QWORD *)v17 + 7);
  if ( v69 )
    VIDMM_GLOBAL::CloseOneAllocation(*(VIDMM_GLOBAL **)a1, v69, 0, 0, 0, 0);
  v70 = (struct VIDMM_GLOBAL_ALLOC *)*((_QWORD *)v17 + 6);
  if ( v70 )
    VIDMM_GLOBAL::DestroyOneAllocation(*(VIDMM_GLOBAL **)a1, *(struct VIDMM_DEVICE **)(a1 + 8), v70, 1);
  v71 = (void *)*((_QWORD *)v17 + 8);
  if ( v71 )
    MmFreeContiguousMemorySpecifyCache(v71, (unsigned int)NumberOfBytes, *((MEMORY_CACHING_TYPE *)v17 + 18));
  operator delete(v17);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1400bfce0  mov     [rsp-38h+arg_10], rbx
0x1400bfce5  mov     [rsp-38h+arg_18], r9d
0x1400bfcea  mov     dword ptr [rsp-38h+NumberOfBytes], edx
0x1400bfcee  push    rbp
0x1400bfcef  push    rsi
0x1400bfcf0  push    rdi
0x1400bfcf1  push    r12
0x1400bfcf3  push    r13
0x1400bfcf5  push    r14
0x1400bfcf7  push    r15
0x1400bfcf9  mov     rbp, rsp
0x1400bfcfc  sub     rsp, 160h
0x1400bfd03  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400bfd0a  xor     r13d, r13d
0x1400bfd0d  mov     ebx, r9d
0x1400bfd10  mov     r15d, edx
0x1400bfd13  mov     r12d, r8d
0x1400bfd16  mov     rsi, rcx
0x1400bfd19  cmp     [rax], r13b
0x1400bfd1c  jz      short loc_1400BFD38
0x1400bfd1e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400bfd25  nop     dword ptr [rax+rax+00h]
0x1400bfd2a  mov     [rax+18h], rsi
0x1400bfd2e  mov     cs:WdLogGlobalForLineNumber, 1AFh
0x1400bfd38  mov     eax, cs:dword_140087A50
0x1400bfd3e  mov     r14d, 1
0x1400bfd44  cmp     [rsi+54h], eax
0x1400bfd47  jbe     loc_1400BFE00
0x1400bfd4d  mov     rax, [rsi+8]
0x1400bfd51  test    rax, rax
0x1400bfd54  jz      short loc_1400BFD7D
0x1400bfd56  mov     rax, [rax+18h]
0x1400bfd5a  cmp     dword ptr [rax+1D0h], 2
0x1400bfd61  jz      loc_1400BFE00
0x1400bfd67  mov     rax, [rax+28h]
0x1400bfd6b  mov     ecx, [rax+198h]
0x1400bfd71  shr     ecx, 2
0x1400bfd74  test    r14b, cl
0x1400bfd77  jnz     loc_1400BFE00
0x1400bfd7d  mov     rax, cs:qword_140087A30
0x1400bfd84  cmp     cs:qword_140087A38, rax
0x1400bfd8b  jg      short loc_1400BFDAD
0x1400bfd8d  mov     rax, cs:qword_140087A00
0x1400bfd94  cmp     cs:qword_140087A08, rax
0x1400bfd9b  jg      short loc_1400BFDAD
0x1400bfd9d  mov     rax, cs:qword_1400879D0
0x1400bfda4  cmp     cs:qword_1400879D8, rax
0x1400bfdab  jle     short loc_1400BFE00
0x1400bfdad  lock add cs:dword_140087758, r14d
0x1400bfdb5  mov     ecx, 6
0x1400bfdba  call    cs:__imp_WdLogSingleEntry0
0x1400bfdc1  nop     dword ptr [rax+rax+00h]
0x1400bfdc6  mov     eax, 1BFh
0x1400bfdcb  lea     r9, aReachTheMaximu; "Reach the maximum size for the DMA pool"...
0x1400bfdd2  mov     [rsp+160h+var_128], r13
0x1400bfdd7  mov     edx, 40001h
0x1400bfddc  mov     [rsp+160h+var_130], r13
0x1400bfde1  mov     [rsp+160h+var_138], r13
0x1400bfde6  mov     qword ptr [rsp+160h+var_140], rax
0x1400bfdeb  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bfdf1  call    DxgkLogInternalTriageEvent
0x1400bfdf6  mov     eax, 0C0000017h
0x1400bfdfb  jmp     loc_1400C0764
0x1400bfe00  mov     eax, [rsi+24h]
0x1400bfe03  test    r14b, al
0x1400bfe06  jnz     short loc_1400BFE56
0x1400bfe08  test    r12d, r12d
0x1400bfe0b  jnz     short loc_1400BFE56
0x1400bfe0d  mov     ecx, r14d
0x1400bfe10  call    cs:__imp_WdLogSingleEntry0
0x1400bfe17  nop     dword ptr [rax+rax+00h]
0x1400bfe1c  mov     [rsp+160h+var_128], r13
0x1400bfe21  lea     r9, aCanTCreateRegu; "Can't create regular DMA buffer with no"...
0x1400bfe28  mov     eax, 1CAh
0x1400bfe2d  mov     [rsp+160h+var_130], r13
0x1400bfe32  mov     [rsp+160h+var_138], r13
0x1400bfe37  mov     edx, 40000h
0x1400bfe3c  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bfe42  mov     qword ptr [rsp+160h+var_140], rax
0x1400bfe47  call    DxgkLogInternalTriageEvent
0x1400bfe4c  mov     eax, 0C000000Dh
0x1400bfe51  jmp     loc_1400C0764
0x1400bfe56  mov     ecx, 0A0h
0x1400bfe5b  mov     edx, 32326956h
0x1400bfe60  lea     r8d, [rcx-60h]
0x1400bfe64  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400bfe69  mov     rdi, rax
0x1400bfe6c  test    rax, rax
0x1400bfe6f  jnz     short loc_1400BFE99
0x1400bfe71  lock add cs:dword_1400876B0, r14d
0x1400bfe79  lea     ecx, [rax+6]
0x1400bfe7c  call    cs:__imp_WdLogSingleEntry0
0x1400bfe83  nop     dword ptr [rax+rax+00h]
0x1400bfe88  mov     eax, 1D6h
0x1400bfe8d  lea     r9, aCouldnTAllocat_24; "Couldn't allocate memory for DMA buffer"...
0x1400bfe94  jmp     loc_1400BFDD2
0x1400bfe99  mov     r8d, [rsi+28h]
0x1400bfe9d  test    r8d, r8d
0x1400bfea0  jz      loc_1400C020E
0x1400bfea6  mov     eax, [rsi+24h]
0x1400bfea9  test    r14b, al
0x1400bfeac  jz      short loc_1400BFECB
0x1400bfeae  mov     rax, [rsi+10h]
0x1400bfeb2  mov     cl, [rax+544h]
0x1400bfeb8  not     cl
0x1400bfeba  movzx   ecx, cl
0x1400bfebd  and     ecx, 0FFFFFF80h
0x1400bfec0  shl     ecx, 8
0x1400bfec3  or      ecx, 10000040h
0x1400bfec9  jmp     short loc_1400BFEE5
0x1400bfecb  mov     rax, [rsi+18h]
0x1400bfecf  mov     cl, [rax+1AEh]
0x1400bfed5  neg     cl
0x1400bfed7  sbb     ecx, ecx
0x1400bfed9  and     ecx, 0FFFF8000h
0x1400bfedf  add     ecx, 8048h
0x1400bfee5  mov     r10, [rsi]
0x1400bfee8  mov     rax, [r10+18h]
0x1400bfeec  mov     edx, [rax+1BCh]
0x1400bfef2  test    dl, 8
0x1400bfef5  jnz     short loc_1400BFEFC
0x1400bfef7  test    dl, 10h
0x1400bfefa  jz      short loc_1400BFEFF
0x1400bfefc  or      ecx, 4
0x1400bfeff  mov     rdx, [rsi+8]
0x1400bff03  lea     r11, [rbp+arg_0]
0x1400bff07  mov     [rsp+160h+var_90], r11
0x1400bff0f  mov     r9, r15
0x1400bff12  lea     r15, [rdi+30h]
0x1400bff16  mov     [rbp+arg_0], r13b
0x1400bff1a  mov     [rsp+160h+var_98], r15
0x1400bff22  mov     [rsp+160h+var_A0], r13
0x1400bff2a  mov     [rsp+160h+var_A8], r13
0x1400bff32  mov     [rsp+160h+var_B0], r13
0x1400bff3a  mov     [rsp+160h+var_B8], r13
0x1400bff42  mov     [rsp+160h+var_C0], r13b
0x1400bff4a  mov     [rsp+160h+var_C8], 0A0000000h
0x1400bff55  mov     [rsp+160h+var_D0], r13
0x1400bff5d  mov     [rsp+160h+var_D8], r13
0x1400bff65  mov     [rsp+160h+var_E0], r13
0x1400bff6d  mov     [rsp+160h+var_E8], r13
0x1400bff72  mov     [rsp+160h+var_F0], r13
0x1400bff77  mov     [rsp+160h+var_F8], r13d
0x1400bff7c  mov     dword ptr [rsp+160h+var_100], ecx
0x1400bff80  mov     rcx, r10
0x1400bff83  mov     [rsp+160h+var_108], r13d
0x1400bff88  mov     dword ptr [rsp+160h+var_110], r13d
0x1400bff8d  mov     dword ptr [rsp+160h+var_118], r13d
0x1400bff92  mov     dword ptr [rsp+160h+var_120], r8d
0x1400bff97  mov     r8d, [rsi+20h]
0x1400bff9b  mov     dword ptr [rsp+160h+var_128], r13d
0x1400bffa0  mov     dword ptr [rsp+160h+var_130], r13d
0x1400bffa5  mov     dword ptr [rsp+160h+var_138], r13d
0x1400bffaa  mov     qword ptr [rsp+160h+var_140], r9
0x1400bffaf  call    ?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX777KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z; VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)
0x1400bffb4  mov     r14d, eax
0x1400bffb7  test    eax, eax
0x1400bffb9  jns     short loc_1400C000F
0x1400bffbb  mov     r12d, 1
0x1400bffc1  lock add cs:dword_1400876B8, r12d
0x1400bffc9  lea     ecx, [r12+5]
0x1400bffce  call    cs:__imp_WdLogSingleEntry0
0x1400bffd5  nop     dword ptr [rax+rax+00h]
0x1400bffda  mov     eax, 21Dh
0x1400bffdf  lea     r9, aCouldnTCreateA; "Couldn't create a global allocation for"...
0x1400bffe6  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bffec  mov     edx, 40001h
0x1400bfff1  mov     [rsp+160h+var_128], r13
0x1400bfff6  mov     [rsp+160h+var_130], r13
0x1400bfffb  mov     [rsp+160h+var_138], r13
0x1400c0000  mov     qword ptr [rsp+160h+var_140], rax
0x1400c0005  call    DxgkLogInternalTriageEvent
0x1400c000a  jmp     loc_1400C06E0
0x1400c000f  mov     r8, [r15]; struct VIDMM_GLOBAL_ALLOC *
0x1400c0012  lea     rbx, [rdi+38h]
0x1400c0016  mov     rdx, [rsi+8]; struct VIDMM_DEVICE *
0x1400c001a  xor     r9d, r9d; bool
0x1400c001d  mov     rcx, [rsi]; this
0x1400c0020  mov     [rsp+160h+var_138], rbx; struct VIDMM_ALLOC **
0x1400c0025  mov     qword ptr [rsp+160h+var_140], r13; struct DXGALLOCATION *
0x1400c002a  call    ?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)
0x1400c002f  mov     r14d, eax
0x1400c0032  test    eax, eax
0x1400c0034  jns     short loc_1400C0063
0x1400c0036  mov     r12d, 1
0x1400c003c  lock add cs:dword_1400876BC, r12d
0x1400c0044  lea     ecx, [r12+5]
0x1400c0049  call    cs:__imp_WdLogSingleEntry0
0x1400c0050  nop     dword ptr [rax+rax+00h]
0x1400c0055  mov     eax, 22Eh
0x1400c005a  lea     r9, aCouldnTOpenThe_0; "Couldn't open the global allocation for"...
0x1400c0061  jmp     short loc_1400BFFE6
0x1400c0063  mov     r15, [rbx]
0x1400c0066  mov     eax, [r15+1Ch]
0x1400c006a  test    al, 3
0x1400c006c  jnz     short loc_1400C00B7
0x1400c006e  mov     eax, [rsi+24h]
0x1400c0071  test    al, 1
0x1400c0073  jz      loc_1400C0154
0x1400c0079  xor     edx, edx; Val
0x1400c007b  lea     rcx, [rbp+var_60]; void *
0x1400c007f  lea     r8d, [rdx+58h]; Size
0x1400c0083  call    memset
0x1400c0088  mov     rax, [r15]
0x1400c008b  lea     rdx, [rbp+var_60]; struct VIDMM_SYSTEM_COMMAND *
0x1400c008f  mov     [rbp+var_60], 68h ; 'h'
0x1400c0096  mov     r8b, 1; bool
0x1400c0099  mov     [rbp+var_50], r15
0x1400c009d  mov     rcx, [rax]
0x1400c00a0  mov     rax, [rcx]
0x1400c00a3  mov     ecx, [rax+3Ch]
0x1400c00a6  shr     ecx, 2
0x1400c00a9  and     ecx, 3Fh
0x1400c00ac  mov     [rbp+var_5C], ecx
0x1400c00af  mov     rcx, [rsi]; this
0x1400c00b2  call    ?QueueSystemCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x1400c00b7  mov     r15d, dword ptr [rbp+NumberOfBytes]
0x1400c00bb  mov     ebx, [rbp+arg_18]
0x1400c00be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400c00c2  test    r12d, r12d
0x1400c00c5  jz      loc_1400C02D1
0x1400c00cb  lea     ecx, [r8+4]
0x1400c00cf  cmp     r12d, ecx
0x1400c00d2  lea     eax, [r8+9]
0x1400c00d6  cmova   ecx, r12d
0x1400c00da  mov     r12d, ecx
0x1400c00dd  mul     r12
0x1400c00e0  mov     edx, 33326956h
0x1400c00e5  cmovb   rax, r8
0x1400c00e9  mov     r8d, 40h ; '@'
0x1400c00ef  mov     rcx, rax
0x1400c00f2  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c00f7  mov     [rdi+60h], rax
0x1400c00fb  test    rax, rax
0x1400c00fe  jnz     loc_1400C0274
0x1400c0104  lea     r12d, [rax+1]
0x1400c0108  lock add cs:dword_1400876D0, r12d
0x1400c0110  lea     ecx, [rax+6]
0x1400c0113  call    cs:__imp_WdLogSingleEntry0
0x1400c011a  nop     dword ptr [rax+rax+00h]
0x1400c011f  mov     eax, 288h
0x1400c0124  lea     r9, aCouldnTAllocat_29; "Couldn't allocate memory for the DMA bu"...
0x1400c012b  mov     [rsp+160h+var_128], r13
0x1400c0130  mov     edx, 40001h
0x1400c0135  mov     [rsp+160h+var_130], r13
0x1400c013a  mov     [rsp+160h+var_138], r13
0x1400c013f  mov     qword ptr [rsp+160h+var_140], rax
0x1400c0144  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c014a  call    DxgkLogInternalTriageEvent
0x1400c014f  jmp     loc_1400C06DA
0x1400c0154  mov     rax, [r15+8]
0x1400c0158  lea     r8, [rbp+var_70]; struct VIDMM_MULTI_ALLOC **
0x1400c015c  mov     edx, [rsi+20h]
0x1400c015f  mov     r9d, 1; unsigned __int64
0x1400c0165  shl     rdx, 5
0x1400c0169  mov     [rbp+var_80], 0
0x1400c0171  mov     rcx, [rax+48h]
0x1400c0175  lea     rax, [rbp+var_78]
0x1400c0179  mov     [rsp+160h+var_130], rax; unsigned __int64 *
0x1400c017e  lea     rax, [rbp+var_80]
0x1400c0182  mov     [rsp+160h+var_138], rax; unsigned __int64 *
0x1400c0187  mov     [rbp+var_78], 0
0x1400c018f  mov     r13, [rdx+rcx]
0x1400c0193  mov     rcx, [rsi]; this
0x1400c0196  mov     rdx, r13; struct VIDMM_PAGING_QUEUE *
0x1400c0199  mov     [rbp+var_70], r15
0x1400c019d  mov     dword ptr [rsp+160h+var_140], 3; unsigned int
0x1400c01a5  call    ?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z; VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)
0x1400c01aa  mov     r14d, eax
0x1400c01ad  cmp     eax, 103h
0x1400c01b2  jnz     short loc_1400C01CF
0x1400c01b4  mov     r8, [rbp+var_80]; unsigned __int64
0x1400c01b8  mov     rdx, [r13+58h]; struct _VIDSCH_SYNC_OBJECT *
0x1400c01bc  mov     rcx, [rsi]; this
0x1400c01bf  call    ?WaitForFence@VIDMM_GLOBAL@@QEAAXPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::WaitForFence(_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x1400c01c4  xor     r13d, r13d
0x1400c01c7  mov     r14d, r13d
0x1400c01ca  jmp     loc_1400C00B7
0x1400c01cf  xor     r13d, r13d
0x1400c01d2  test    eax, eax
0x1400c01d4  jns     loc_1400C00B7
0x1400c01da  mov     rdx, [rbx]
0x1400c01dd  lea     r12d, [r13+1]
0x1400c01e1  mov     ecx, r12d
0x1400c01e4  call    cs:__imp_WdLogSingleEntry1
0x1400c01eb  nop     dword ptr [rax+rax+00h]
0x1400c01f0  mov     cs:WdLogGlobalForLineNumber, 24Eh
0x1400c01fa  lea     r9, aCouldnTPageInT; "Couldn't page in the new DMA buffer 0x%"...
0x1400c0201  mov     rax, [rbx]
0x1400c0204  mov     edx, 40000h
0x1400c0209  jmp     loc_1400BFFF1
0x1400c020e  mov     rax, [rsi]
0x1400c0211  mov     rcx, r15
0x1400c0214  mov     rdx, qword ptr cs:LowAddress
0x1400c021b  mov     dword ptr [rsp+160h+var_138], 80000000h
0x1400c0223  mov     r9, rdx
0x1400c0226  mov     dword ptr [rsp+160h+var_140], 404h
0x1400c022e  mov     r8, [rax+18h]
0x1400c0232  mov     r8, [r8+9E0h]
0x1400c0239  mov     dword ptr [rdi+48h], 2
  ... truncated ...
```
