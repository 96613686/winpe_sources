# AddDmaBufferToPool

- ea: `0x1400bc240`
- end: `0x1400bccd8`
- name: `AddDmaBufferToPool`
- size: `2712`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b2180`
- `0x1400bd4f0`
- `0x140101b50`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140030ae0`
- `0x140031178`
- `0x140031f84`
- `0x1400320d8`
- `0x140032a04`
- `0x14003e56c`
- `0x140058ac0`
- `0x140095a88`
- `0x1400bc240`
- `0x1400dfe1c`
- `0x1400e1d30`
- `0x1400e84b4`
- `0x1400e9900`
- `0x1400ea1dc`
- `0x1400ebb0c`
- `0x140102390`
- `0x14010416c`
- `0x140105808`
- `0x14010c894`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400bcb5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400bcb5c`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400bc798`
- `ntoskrnl!MmAllocateContiguousNodeMemory` at `0x1400bc798`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400bc7b7`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400bc7b7`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x1400bcca5`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x1400bcca5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bc27e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bcac1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bcb74`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bc27e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bcac1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bcb74`
- `watchdog!WdLogSingleEntry0` at `0x1400bc31a`
- `watchdog!WdLogSingleEntry0` at `0x1400bc370`
- `watchdog!WdLogSingleEntry0` at `0x1400bc3dc`
- `watchdog!WdLogSingleEntry0` at `0x1400bc526`
- `watchdog!WdLogSingleEntry0` at `0x1400bc5a1`
- `watchdog!WdLogSingleEntry0` at `0x1400bc66b`
- `watchdog!WdLogSingleEntry0` at `0x1400bc808`
- `watchdog!WdLogSingleEntry0` at `0x1400bc866`
- `watchdog!WdLogSingleEntry0` at `0x1400bc8b4`
- `watchdog!WdLogSingleEntry0` at `0x1400bcbf0`
- `watchdog!WdLogSingleEntry0` at `0x1400bc31a`
- `watchdog!WdLogSingleEntry0` at `0x1400bc370`
- `watchdog!WdLogSingleEntry0` at `0x1400bc3dc`
- `watchdog!WdLogSingleEntry0` at `0x1400bc526`
- `watchdog!WdLogSingleEntry0` at `0x1400bc5a1`
- `watchdog!WdLogSingleEntry0` at `0x1400bc66b`
- `watchdog!WdLogSingleEntry0` at `0x1400bc808`
- `watchdog!WdLogSingleEntry0` at `0x1400bc866`
- `watchdog!WdLogSingleEntry0` at `0x1400bc8b4`
- `watchdog!WdLogSingleEntry0` at `0x1400bcbf0`
- `watchdog!WdLogSingleEntry1` at `0x1400bc73c`
- `watchdog!WdLogSingleEntry1` at `0x1400bc73c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400bc263`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400bcaab`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400bcb68`

## string_xrefs

- `0x1400bc381`: `Can't create regular DMA buffer with no associated allocation list`
- `0x1400bc537`: `Couldn't create a global allocation for DMA the buffer.`
- `0x1400bc5b2`: `Couldn't open the global allocation for the DMA buffer.`

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
  int v72; // [rsp+68h] [rbp-E8h]
  int v73; // [rsp+70h] [rbp-E0h]
  unsigned __int64 v74; // [rsp+D0h] [rbp-80h] BYREF
  unsigned __int64 v75; // [rsp+D8h] [rbp-78h] BYREF
  struct VIDMM_MULTI_ALLOC *v76; // [rsp+E0h] [rbp-70h] BYREF
  _QWORD v77[12]; // [rsp+F0h] [rbp-60h] BYREF
  char v78; // [rsp+190h] [rbp+40h] BYREF
  SIZE_T NumberOfBytes; // [rsp+198h] [rbp+48h]
  unsigned int v80; // [rsp+1A8h] [rbp+58h]

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
  if ( *(_DWORD *)(a1 + 84) > (unsigned int)dword_140086A60 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    if ( !v8
      || (v9 = *(_QWORD *)(v8 + 24), *(_DWORD *)(v9 + 464) != 2) && (*(_DWORD *)(*(_QWORD *)(v9 + 40) + 408LL) & 4) == 0 )
    {
      if ( qword_140086A48 > qword_140086A40 || qword_140086A18 > qword_140086A10 || qword_1400869E8 > qword_1400869E0 )
      {
        _InterlockedAdd(&dword_140086778, 1u);
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
    _InterlockedAdd(&dword_1400866D0, 1u);
    WdLogSingleEntry0(6);
    v12 = 470;
    v13 = L"Couldn't allocate memory for DMA buffer object.";
    goto LABEL_11;
  }
  v18 = *(_DWORD *)(a1 + 40);
  if ( v18 )
  {
    if ( (*(_DWORD *)(a1 + 36) & 1) != 0 )
      v19 = ((~*(_BYTE *)(*(_QWORD *)(a1 + 16) + 1084LL) & 0x80) << 8) | 0x10000040;
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
      _InterlockedAdd(&dword_1400866D8, 1u);
      WdLogSingleEntry0(6);
      v26 = 540;
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
      _InterlockedAdd(&dword_1400866DC, 1u);
      WdLogSingleEntry0(6);
      v26 = 557;
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
        Resident = VIDMM_GLOBAL::MakeResident(v43, (struct VIDMM_PAGING_QUEUE *)v42, &v76, 1u, 3, &v74, &v75);
        v23 = Resident;
        if ( Resident == 259 )
        {
          VIDMM_GLOBAL::WaitForFence(*(VIDMM_GLOBAL **)a1, v42[11], v74);
          v23 = 0;
        }
        else if ( Resident < 0 )
        {
          WdLogSingleEntry1(1, *v29);
          WdLogGlobalForLineNumber = 589;
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
    v45 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 2512LL);
    *((_DWORD *)v17 + 18) = 2;
    ContiguousNodeMemory = (void *)MmAllocateContiguousNodeMemory(v5, 0, v45, 0, 1028, 0x80000000);
    *((_QWORD *)v17 + 8) = ContiguousNodeMemory;
    if ( !ContiguousNodeMemory )
    {
      _InterlockedAdd(&dword_1400866E4, 1u);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 620;
      DxgkLogInternalTriageEvent(
        v67,
        262145,
        v68,
        (unsigned int)L"Couldn't allocate a contiguous buffer for the DMA buffer.",
        620,
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
      _InterlockedAdd(&dword_1400866F0, 1u);
      WdLogSingleEntry0(6);
      v37 = 647;
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
      _InterlockedAdd(&dword_1400866E8, 1u);
      WdLogSingleEntry0(6);
      v37 = 660;
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
      _InterlockedAdd(&dword_1400866EC, 1u);
      WdLogSingleEntry0(6);
      v37 = 676;
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
      _InterlockedAdd(&dword_140086750, 1u);
      WdLogSingleEntry0(6);
      v37 = 689;
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
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 3064LL),
                    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 3072LL),
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
      WdLogGlobalForLineNumber = 753;
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
          (const struct _DXGK_ADL *)&xmmword_14005D4E0,
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
    _InterlockedAdd64(&qword_140086A48, *((unsigned int *)v17 + 9));
    _InterlockedAdd64(&qword_140086A18, 24LL * *((unsigned int *)v17 + 10));
    _InterlockedAdd64(&qword_1400869E8, 24LL * *((unsigned int *)v17 + 11));
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
      WdLogGlobalForLineNumber = 839;
    }
    if ( (byte_140086201 & 1) != 0 )
      McTemplateK0pppxxxp_EtwWriteTransfer(
        *((_DWORD *)v17 + 11),
        (unsigned int)EventAddDmaBuffer,
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
0x1400bc240  mov     [rsp-38h+arg_10], rbx
0x1400bc245  mov     [rsp-38h+arg_18], r9d
0x1400bc24a  mov     dword ptr [rsp-38h+NumberOfBytes], edx
0x1400bc24e  push    rbp
0x1400bc24f  push    rsi
0x1400bc250  push    rdi
0x1400bc251  push    r12
0x1400bc253  push    r13
0x1400bc255  push    r14
0x1400bc257  push    r15
0x1400bc259  mov     rbp, rsp
0x1400bc25c  sub     rsp, 150h
0x1400bc263  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400bc26a  xor     r13d, r13d
0x1400bc26d  mov     ebx, r9d
0x1400bc270  mov     r15d, edx
0x1400bc273  mov     r12d, r8d
0x1400bc276  mov     rsi, rcx
0x1400bc279  cmp     [rax], r13b
0x1400bc27c  jz      short loc_1400BC298
0x1400bc27e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400bc285  nop     dword ptr [rax+rax+00h]
0x1400bc28a  mov     [rax+18h], rsi
0x1400bc28e  mov     cs:WdLogGlobalForLineNumber, 1AFh
0x1400bc298  mov     eax, cs:dword_140086A60
0x1400bc29e  mov     r14d, 1
0x1400bc2a4  cmp     [rsi+54h], eax
0x1400bc2a7  jbe     loc_1400BC360
0x1400bc2ad  mov     rax, [rsi+8]
0x1400bc2b1  test    rax, rax
0x1400bc2b4  jz      short loc_1400BC2DD
0x1400bc2b6  mov     rax, [rax+18h]
0x1400bc2ba  cmp     dword ptr [rax+1D0h], 2
0x1400bc2c1  jz      loc_1400BC360
0x1400bc2c7  mov     rax, [rax+28h]
0x1400bc2cb  mov     ecx, [rax+198h]
0x1400bc2d1  shr     ecx, 2
0x1400bc2d4  test    r14b, cl
0x1400bc2d7  jnz     loc_1400BC360
0x1400bc2dd  mov     rax, cs:qword_140086A40
0x1400bc2e4  cmp     cs:qword_140086A48, rax
0x1400bc2eb  jg      short loc_1400BC30D
0x1400bc2ed  mov     rax, cs:qword_140086A10
0x1400bc2f4  cmp     cs:qword_140086A18, rax
0x1400bc2fb  jg      short loc_1400BC30D
0x1400bc2fd  mov     rax, cs:qword_1400869E0
0x1400bc304  cmp     cs:qword_1400869E8, rax
0x1400bc30b  jle     short loc_1400BC360
0x1400bc30d  lock add cs:dword_140086778, r14d
0x1400bc315  mov     ecx, 6
0x1400bc31a  call    cs:__imp_WdLogSingleEntry0
0x1400bc321  nop     dword ptr [rax+rax+00h]
0x1400bc326  mov     eax, 1BFh
0x1400bc32b  lea     r9, aReachTheMaximu; "Reach the maximum size for the DMA pool"...
0x1400bc332  mov     [rsp+150h+var_118], r13
0x1400bc337  mov     edx, 40001h
0x1400bc33c  mov     [rsp+150h+var_120], r13
0x1400bc341  mov     [rsp+150h+var_128], r13
0x1400bc346  mov     qword ptr [rsp+150h+var_130], rax
0x1400bc34b  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bc351  call    DxgkLogInternalTriageEvent
0x1400bc356  mov     eax, 0C0000017h
0x1400bc35b  jmp     loc_1400BCCBC
0x1400bc360  mov     eax, [rsi+24h]
0x1400bc363  test    r14b, al
0x1400bc366  jnz     short loc_1400BC3B6
0x1400bc368  test    r12d, r12d
0x1400bc36b  jnz     short loc_1400BC3B6
0x1400bc36d  mov     ecx, r14d
0x1400bc370  call    cs:__imp_WdLogSingleEntry0
0x1400bc377  nop     dword ptr [rax+rax+00h]
0x1400bc37c  mov     [rsp+150h+var_118], r13
0x1400bc381  lea     r9, aCanTCreateRegu; "Can't create regular DMA buffer with no"...
0x1400bc388  mov     eax, 1CAh
0x1400bc38d  mov     [rsp+150h+var_120], r13
0x1400bc392  mov     [rsp+150h+var_128], r13
0x1400bc397  mov     edx, 40000h
0x1400bc39c  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bc3a2  mov     qword ptr [rsp+150h+var_130], rax
0x1400bc3a7  call    DxgkLogInternalTriageEvent
0x1400bc3ac  mov     eax, 0C000000Dh
0x1400bc3b1  jmp     loc_1400BCCBC
0x1400bc3b6  mov     ecx, 0A0h
0x1400bc3bb  mov     edx, 32326956h
0x1400bc3c0  lea     r8d, [rcx-60h]
0x1400bc3c4  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400bc3c9  mov     rdi, rax
0x1400bc3cc  test    rax, rax
0x1400bc3cf  jnz     short loc_1400BC3F9
0x1400bc3d1  lock add cs:dword_1400866D0, r14d
0x1400bc3d9  lea     ecx, [rax+6]
0x1400bc3dc  call    cs:__imp_WdLogSingleEntry0
0x1400bc3e3  nop     dword ptr [rax+rax+00h]
0x1400bc3e8  mov     eax, 1D6h
0x1400bc3ed  lea     r9, aCouldnTAllocat_22; "Couldn't allocate memory for DMA buffer"...
0x1400bc3f4  jmp     loc_1400BC332
0x1400bc3f9  mov     r8d, [rsi+28h]
0x1400bc3fd  test    r8d, r8d
0x1400bc400  jz      loc_1400BC766
0x1400bc406  mov     eax, [rsi+24h]
0x1400bc409  test    r14b, al
0x1400bc40c  jz      short loc_1400BC42B
0x1400bc40e  mov     rax, [rsi+10h]
0x1400bc412  mov     cl, [rax+43Ch]
0x1400bc418  not     cl
0x1400bc41a  movzx   ecx, cl
0x1400bc41d  and     ecx, 0FFFFFF80h
0x1400bc420  shl     ecx, 8
0x1400bc423  or      ecx, 10000040h
0x1400bc429  jmp     short loc_1400BC445
0x1400bc42b  mov     rax, [rsi+18h]
0x1400bc42f  mov     cl, [rax+1AEh]
0x1400bc435  neg     cl
0x1400bc437  sbb     ecx, ecx
0x1400bc439  and     ecx, 0FFFF8000h
0x1400bc43f  add     ecx, 8048h
0x1400bc445  mov     r10, [rsi]
0x1400bc448  mov     rax, [r10+18h]
0x1400bc44c  mov     edx, [rax+1BCh]
0x1400bc452  test    dl, 8
0x1400bc455  jnz     short loc_1400BC45C
0x1400bc457  test    dl, 10h
0x1400bc45a  jz      short loc_1400BC45F
0x1400bc45c  or      ecx, 4
0x1400bc45f  mov     rdx, [rsi+8]
0x1400bc463  lea     r11, [rbp+arg_0]
0x1400bc467  mov     [rsp+150h+var_88], r11
0x1400bc46f  mov     r9, r15
0x1400bc472  lea     r15, [rdi+30h]
0x1400bc476  mov     [rbp+arg_0], r13b
0x1400bc47a  mov     [rsp+150h+var_90], r15
0x1400bc482  mov     [rsp+150h+var_98], r13
0x1400bc48a  mov     [rsp+150h+var_A0], r13
0x1400bc492  mov     [rsp+150h+var_A8], r13
0x1400bc49a  mov     [rsp+150h+var_B0], r13
0x1400bc4a2  mov     [rsp+150h+var_B8], r13b
0x1400bc4aa  mov     [rsp+150h+var_C0], 0A0000000h
0x1400bc4b5  mov     [rsp+150h+var_C8], r13
0x1400bc4bd  mov     [rsp+150h+var_D0], r13
0x1400bc4c5  mov     [rsp+150h+var_D8], r13
0x1400bc4ca  mov     [rsp+150h+var_E0], r13
0x1400bc4cf  mov     [rsp+150h+var_E8], r13d
0x1400bc4d4  mov     dword ptr [rsp+150h+var_F0], ecx
0x1400bc4d8  mov     rcx, r10
0x1400bc4db  mov     [rsp+150h+var_F8], r13d
0x1400bc4e0  mov     dword ptr [rsp+150h+var_100], r13d
0x1400bc4e5  mov     dword ptr [rsp+150h+var_108], r13d
0x1400bc4ea  mov     dword ptr [rsp+150h+var_110], r8d
0x1400bc4ef  mov     r8d, [rsi+20h]
0x1400bc4f3  mov     dword ptr [rsp+150h+var_118], r13d
0x1400bc4f8  mov     dword ptr [rsp+150h+var_120], r13d
0x1400bc4fd  mov     dword ptr [rsp+150h+var_128], r13d
0x1400bc502  mov     qword ptr [rsp+150h+var_130], r9
0x1400bc507  call    ?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX77KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z; VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)
0x1400bc50c  mov     r14d, eax
0x1400bc50f  test    eax, eax
0x1400bc511  jns     short loc_1400BC567
0x1400bc513  mov     r12d, 1
0x1400bc519  lock add cs:dword_1400866D8, r12d
0x1400bc521  lea     ecx, [r12+5]
0x1400bc526  call    cs:__imp_WdLogSingleEntry0
0x1400bc52d  nop     dword ptr [rax+rax+00h]
0x1400bc532  mov     eax, 21Ch
0x1400bc537  lea     r9, aCouldnTCreateA; "Couldn't create a global allocation for"...
0x1400bc53e  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bc544  mov     edx, 40001h
0x1400bc549  mov     [rsp+150h+var_118], r13
0x1400bc54e  mov     [rsp+150h+var_120], r13
0x1400bc553  mov     [rsp+150h+var_128], r13
0x1400bc558  mov     qword ptr [rsp+150h+var_130], rax
0x1400bc55d  call    DxgkLogInternalTriageEvent
0x1400bc562  jmp     loc_1400BCC38
0x1400bc567  mov     r8, [r15]; struct VIDMM_GLOBAL_ALLOC *
0x1400bc56a  lea     rbx, [rdi+38h]
0x1400bc56e  mov     rdx, [rsi+8]; struct VIDMM_DEVICE *
0x1400bc572  xor     r9d, r9d; bool
0x1400bc575  mov     rcx, [rsi]; this
0x1400bc578  mov     [rsp+150h+var_128], rbx; struct VIDMM_ALLOC **
0x1400bc57d  mov     qword ptr [rsp+150h+var_130], r13; struct DXGALLOCATION *
0x1400bc582  call    ?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)
0x1400bc587  mov     r14d, eax
0x1400bc58a  test    eax, eax
0x1400bc58c  jns     short loc_1400BC5BB
0x1400bc58e  mov     r12d, 1
0x1400bc594  lock add cs:dword_1400866DC, r12d
0x1400bc59c  lea     ecx, [r12+5]
0x1400bc5a1  call    cs:__imp_WdLogSingleEntry0
0x1400bc5a8  nop     dword ptr [rax+rax+00h]
0x1400bc5ad  mov     eax, 22Dh
0x1400bc5b2  lea     r9, aCouldnTOpenThe_0; "Couldn't open the global allocation for"...
0x1400bc5b9  jmp     short loc_1400BC53E
0x1400bc5bb  mov     r15, [rbx]
0x1400bc5be  mov     eax, [r15+1Ch]
0x1400bc5c2  test    al, 3
0x1400bc5c4  jnz     short loc_1400BC60F
0x1400bc5c6  mov     eax, [rsi+24h]
0x1400bc5c9  test    al, 1
0x1400bc5cb  jz      loc_1400BC6AC
0x1400bc5d1  xor     edx, edx; Val
0x1400bc5d3  lea     rcx, [rbp+var_60]; void *
0x1400bc5d7  lea     r8d, [rdx+58h]; Size
0x1400bc5db  call    memset
0x1400bc5e0  mov     rax, [r15]
0x1400bc5e3  lea     rdx, [rbp+var_60]; struct VIDMM_SYSTEM_COMMAND *
0x1400bc5e7  mov     [rbp+var_60], 68h ; 'h'
0x1400bc5ee  mov     r8b, 1; bool
0x1400bc5f1  mov     [rbp+var_50], r15
0x1400bc5f5  mov     rcx, [rax]
0x1400bc5f8  mov     rax, [rcx]
0x1400bc5fb  mov     ecx, [rax+3Ch]
0x1400bc5fe  shr     ecx, 2
0x1400bc601  and     ecx, 3Fh
0x1400bc604  mov     [rbp+var_5C], ecx
0x1400bc607  mov     rcx, [rsi]; this
0x1400bc60a  call    ?QueueSystemCommandAndWait@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_SYSTEM_COMMAND@@_N@Z; VIDMM_GLOBAL::QueueSystemCommandAndWait(VIDMM_SYSTEM_COMMAND *,bool)
0x1400bc60f  mov     r15d, dword ptr [rbp+NumberOfBytes]
0x1400bc613  mov     ebx, [rbp+arg_18]
0x1400bc616  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400bc61a  test    r12d, r12d
0x1400bc61d  jz      loc_1400BC829
0x1400bc623  lea     ecx, [r8+4]
0x1400bc627  cmp     r12d, ecx
0x1400bc62a  lea     eax, [r8+9]
0x1400bc62e  cmova   ecx, r12d
0x1400bc632  mov     r12d, ecx
0x1400bc635  mul     r12
0x1400bc638  mov     edx, 33326956h
0x1400bc63d  cmovb   rax, r8
0x1400bc641  mov     r8d, 40h ; '@'
0x1400bc647  mov     rcx, rax
0x1400bc64a  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400bc64f  mov     [rdi+60h], rax
0x1400bc653  test    rax, rax
0x1400bc656  jnz     loc_1400BC7CC
0x1400bc65c  lea     r12d, [rax+1]
0x1400bc660  lock add cs:dword_1400866F0, r12d
0x1400bc668  lea     ecx, [rax+6]
0x1400bc66b  call    cs:__imp_WdLogSingleEntry0
0x1400bc672  nop     dword ptr [rax+rax+00h]
0x1400bc677  mov     eax, 287h
0x1400bc67c  lea     r9, aCouldnTAllocat_27; "Couldn't allocate memory for the DMA bu"...
0x1400bc683  mov     [rsp+150h+var_118], r13
0x1400bc688  mov     edx, 40001h
0x1400bc68d  mov     [rsp+150h+var_120], r13
0x1400bc692  mov     [rsp+150h+var_128], r13
0x1400bc697  mov     qword ptr [rsp+150h+var_130], rax
0x1400bc69c  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bc6a2  call    DxgkLogInternalTriageEvent
0x1400bc6a7  jmp     loc_1400BCC32
0x1400bc6ac  mov     rax, [r15+8]
0x1400bc6b0  lea     r8, [rbp+var_70]; struct VIDMM_MULTI_ALLOC **
0x1400bc6b4  mov     edx, [rsi+20h]
0x1400bc6b7  mov     r9d, 1; unsigned __int64
0x1400bc6bd  shl     rdx, 5
0x1400bc6c1  mov     [rbp+var_80], 0
0x1400bc6c9  mov     rcx, [rax+48h]
0x1400bc6cd  lea     rax, [rbp+var_78]
0x1400bc6d1  mov     [rsp+150h+var_120], rax; unsigned __int64 *
0x1400bc6d6  lea     rax, [rbp+var_80]
0x1400bc6da  mov     [rsp+150h+var_128], rax; unsigned __int64 *
0x1400bc6df  mov     [rbp+var_78], 0
0x1400bc6e7  mov     r13, [rdx+rcx]
0x1400bc6eb  mov     rcx, [rsi]; this
0x1400bc6ee  mov     rdx, r13; struct VIDMM_PAGING_QUEUE *
0x1400bc6f1  mov     [rbp+var_70], r15
0x1400bc6f5  mov     dword ptr [rsp+150h+var_130], 3; char
0x1400bc6fd  call    ?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z; VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)
0x1400bc702  mov     r14d, eax
0x1400bc705  cmp     eax, 103h
0x1400bc70a  jnz     short loc_1400BC727
0x1400bc70c  mov     r8, [rbp+var_80]; unsigned __int64
0x1400bc710  mov     rdx, [r13+58h]; struct _VIDSCH_SYNC_OBJECT *
0x1400bc714  mov     rcx, [rsi]; this
0x1400bc717  call    ?WaitForFence@VIDMM_GLOBAL@@QEAAXPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::WaitForFence(_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x1400bc71c  xor     r13d, r13d
0x1400bc71f  mov     r14d, r13d
0x1400bc722  jmp     loc_1400BC60F
0x1400bc727  xor     r13d, r13d
0x1400bc72a  test    eax, eax
0x1400bc72c  jns     loc_1400BC60F
0x1400bc732  mov     rdx, [rbx]
0x1400bc735  lea     r12d, [r13+1]
0x1400bc739  mov     ecx, r12d
0x1400bc73c  call    cs:__imp_WdLogSingleEntry1
0x1400bc743  nop     dword ptr [rax+rax+00h]
0x1400bc748  mov     cs:WdLogGlobalForLineNumber, 24Dh
0x1400bc752  lea     r9, aCouldnTPageInT; "Couldn't page in the new DMA buffer 0x%"...
0x1400bc759  mov     rax, [rbx]
0x1400bc75c  mov     edx, 40000h
0x1400bc761  jmp     loc_1400BC549
0x1400bc766  mov     rax, [rsi]
0x1400bc769  mov     rcx, r15
0x1400bc76c  mov     rdx, qword ptr cs:LowAddress
0x1400bc773  mov     dword ptr [rsp+150h+var_128], 80000000h
0x1400bc77b  mov     r9, rdx
0x1400bc77e  mov     dword ptr [rsp+150h+var_130], 404h
0x1400bc786  mov     r8, [rax+18h]
0x1400bc78a  mov     r8, [r8+9D0h]
0x1400bc791  mov     dword ptr [rdi+48h], 2
0x1400bc798  call    cs:__imp_MmAllocateContiguousNodeMemory
  ... truncated ...
```
