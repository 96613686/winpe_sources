# DXGDEVICE::CreateVidMmAllocations(_D3DKMT_CREATEALLOCATION *,_D3DDDI_ALLOCATIONINFO2 *,_DXGK_ALLOCATIONINFO *,DXGALLOCATION *,_D3DKM_CREATESTANDARDALLOCATION const *,uchar,COREDEVICEACCESS *)

- ea: `0x140403758`
- end: `0x140404991`
- name: `?CreateVidMmAllocations@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@PEAU_DXGK_ALLOCATIONINFO@@PEAVDXGALLOCATION@@PEBU_D3DKM_CREATESTANDARDALLOCATION@@EPEAVCOREDEVICEACCESS@@@Z`
- size: `4665`
- prototype: `__int64 __fastcall(ADAPTER_RENDER **this, struct _D3DKMT_CREATEALLOCATION *, struct _D3DDDI_ALLOCATIONINFO2 *, struct _DXGK_ALLOCATIONINFO *, struct DXGALLOCATION *, const struct _D3DKM_CREATESTANDARDALLOCATION *, unsigned __int8)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140377080`

## callees

- `0x14001b9c0`
- `0x14002dbc0`
- `0x14003bfbc`
- `0x14003c448`
- `0x14003f394`
- `0x14003fb90`
- `0x1400492ac`
- `0x14004d064`
- `0x14004db14`
- `0x140052560`
- `0x1400532c8`
- `0x140057ac8`
- `0x14005953c`
- `0x14006e1e8`
- `0x1400a0cb0`
- `0x1401998c8`
- `0x1402100b8`
- `0x1402101e4`
- `0x140323da4`
- `0x14032a5c4`
- `0x140403758`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140403fc7`
- `ntoskrnl!ObfDereferenceObject` at `0x1404048ca`
- `ntoskrnl!ObfDereferenceObject` at `0x140403fc7`
- `ntoskrnl!ObfDereferenceObject` at `0x1404048ca`
- `ntoskrnl!ObfReferenceObject` at `0x140403d12`
- `ntoskrnl!ObfReferenceObject` at `0x140403d12`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140403a5b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140403a5b`
- `ntoskrnl!MmSectionObjectType` at `0x140403a1e`
- `watchdog!WdLogSingleEntry2` at `0x1404037aa`
- `watchdog!WdLogSingleEntry2` at `0x140404495`
- `watchdog!WdLogSingleEntry2` at `0x1404044f2`
- `watchdog!WdLogSingleEntry2` at `0x140404553`
- `watchdog!WdLogSingleEntry2` at `0x1404046b8`
- `watchdog!WdLogSingleEntry2` at `0x1404037aa`
- `watchdog!WdLogSingleEntry2` at `0x140404495`
- `watchdog!WdLogSingleEntry2` at `0x1404044f2`
- `watchdog!WdLogSingleEntry2` at `0x140404553`
- `watchdog!WdLogSingleEntry2` at `0x1404046b8`
- `watchdog!WdLogSingleEntry0` at `0x140403832`
- `watchdog!WdLogSingleEntry0` at `0x1404038ec`
- `watchdog!WdLogSingleEntry0` at `0x140403c1b`
- `watchdog!WdLogSingleEntry0` at `0x140403d75`
- `watchdog!WdLogSingleEntry0` at `0x140403fe6`
- `watchdog!WdLogSingleEntry0` at `0x14040426c`
- `watchdog!WdLogSingleEntry0` at `0x14040466a`
- `watchdog!WdLogSingleEntry0` at `0x140404762`
- `watchdog!WdLogSingleEntry0` at `0x1404047ec`
- `watchdog!WdLogSingleEntry0` at `0x14040482e`
- `watchdog!WdLogSingleEntry0` at `0x140403832`
- `watchdog!WdLogSingleEntry0` at `0x1404038ec`
- `watchdog!WdLogSingleEntry0` at `0x140403c1b`
- `watchdog!WdLogSingleEntry0` at `0x140403d75`
- `watchdog!WdLogSingleEntry0` at `0x140403fe6`
- `watchdog!WdLogSingleEntry0` at `0x14040426c`
- `watchdog!WdLogSingleEntry0` at `0x14040466a`
- `watchdog!WdLogSingleEntry0` at `0x140404762`
- `watchdog!WdLogSingleEntry0` at `0x1404047ec`
- `watchdog!WdLogSingleEntry0` at `0x14040482e`
- `watchdog!WdLogSingleEntry1` at `0x14040471d`
- `watchdog!WdLogSingleEntry1` at `0x1404047ab`
- `watchdog!WdLogSingleEntry1` at `0x140404873`
- `watchdog!WdLogSingleEntry1` at `0x1404048e1`
- `watchdog!WdLogSingleEntry1` at `0x14040471d`
- `watchdog!WdLogSingleEntry1` at `0x1404047ab`
- `watchdog!WdLogSingleEntry1` at `0x140404873`
- `watchdog!WdLogSingleEntry1` at `0x1404048e1`

## string_xrefs

- `0x1404037bb`: `Device 0x%I64x: Can not create StandardAllocation from UserMode and Kernel simultaneously,                             returning 0x%I64x`
- `0x1404038fa`: `pAllocation->m_pAllocation->m_hDriverAllocation != NULL || pKMTCreateAllocation->Flags.NoKmdAccess`
- `0x140403c29`: `(pKMTCreateAllocation->NumAllocations == 1) && (pDriverAllocations[i].Flags.DoDPrimary) && (pCreateStandardAllocation != NULL) && (pCreateStandardAllocation->pfnAllocateSysMem != NULL)`
- `0x1404047fb`: `Cannot create section object for DoD primary backing store.`
- `0x140404891`: `Failed to create VIDMM_CROSSADAPTER_ALLOC, returning 0x%I64x`
- `0x1404048ff`: `Failed to make shadow allocation resident. Status = 0x%I64x`

## pseudocode

```c
__int64 __fastcall DXGDEVICE::CreateVidMmAllocations(
        ADAPTER_RENDER **this,
        struct _D3DKMT_CREATEALLOCATION *a2,
        struct _D3DDDI_ALLOCATIONINFO2 *a3,
        struct _DXGK_ALLOCATIONINFO *a4,
        struct DXGALLOCATION *a5,
        const struct _D3DKM_CREATESTANDARDALLOCATION *a6,
        unsigned __int8 a7)
{
  D3DKMT_CREATEALLOCATIONFLAGS Flags; // r10d
  struct _D3DKMT_CREATEALLOCATION *v8; // rdi
  ADAPTER_RENDER *v11; // rcx
  struct _DXGK_ALLOCATIONINFO *v12; // rsi
  BOOL v13; // eax
  unsigned __int8 v14; // r12
  struct DXGALLOCATION *v15; // r15
  UINT v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rsi
  struct _DXGK_ALLOCATIONINFO *v19; // rdi
  struct _D3DKMT_CREATEALLOCATION *v20; // r9
  struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D Value; // r8d
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdi
  D3DKMT_CREATEALLOCATIONFLAGS v25; // ecx
  struct DXGPROCESS *Current; // rax
  __int64 v27; // r12
  NTSTATUS v28; // eax
  PVOID v29; // r12
  int v30; // eax
  __int64 v31; // rdx
  HANDLE hSection; // rcx
  __int64 v33; // rax
  unsigned __int64 v34; // rdx
  __int64 v35; // rdx
  void *v36; // rax
  __int64 v37; // rdi
  int v38; // ecx
  HANDLE v39; // rax
  __int64 v40; // rdi
  void *v41; // rax
  int v42; // eax
  void *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  char v46; // di
  PVOID v47; // rsi
  __int64 v48; // rdi
  struct DXGPROCESS *v49; // rax
  __int64 v50; // r9
  int v51; // eax
  struct _D3DKMT_CREATEALLOCATION *v52; // rsi
  struct _DXGK_ALLOCATIONINFO *v53; // r8
  __int64 v54; // rdx
  PVOID v55; // rax
  int v56; // ecx
  PVOID v57; // r8
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  int v62; // r8d
  __int64 v63; // rcx
  _DWORD *v64; // rcx
  _DWORD *v65; // rcx
  _DWORD *v66; // rcx
  __int64 v67; // rcx
  int v68; // eax
  ADAPTER_RENDER *v69; // rcx
  __int64 v70; // r8
  int v71; // ecx
  __int64 v72; // rax
  struct VIDMM_MULTI_ALLOC **v73; // rdx
  struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D v74; // ecx
  __int64 v75; // rax
  int v76; // edx
  __int64 v77; // rax
  struct VIDMM_MULTI_ALLOC **v78; // rdi
  ADAPTER_RENDER *v79; // rcx
  struct VIDMM_DEVICE *v80; // rdx
  int v81; // r8d
  ADAPTER_RENDER *v82; // rcx
  int Resident; // eax
  PVOID v84; // rcx
  UINT v85; // edi
  struct DXGALLOCATION *v86; // r15
  __int64 v87; // rcx
  struct VIDMM_MULTI_GLOBAL_ALLOC *v88; // r8
  struct VIDMM_MULTI_ALLOC *v89; // r8
  const wchar_t *v90; // r9
  __int64 v91; // rax
  unsigned int Object; // [rsp+28h] [rbp-C9h]
  POBJECT_HANDLE_INFORMATION HandleInformation; // [rsp+30h] [rbp-C1h]
  __int64 HandleInformationa; // [rsp+30h] [rbp-C1h]
  char v95; // [rsp+68h] [rbp-89h] BYREF
  char v96; // [rsp+69h] [rbp-88h]
  struct _DXGK_ALLOCATIONINFO *v97; // [rsp+70h] [rbp-81h]
  PVOID BaseAddress; // [rsp+80h] [rbp-71h]
  int v99; // [rsp+88h] [rbp-69h]
  UINT v100; // [rsp+8Ch] [rbp-65h]
  PVOID v101; // [rsp+90h] [rbp-61h]
  int v102; // [rsp+98h] [rbp-59h] BYREF
  BOOL v103; // [rsp+9Ch] [rbp-55h]
  unsigned int v104[2]; // [rsp+A0h] [rbp-51h]
  __int64 v105; // [rsp+A8h] [rbp-49h] BYREF
  __int64 v106; // [rsp+B0h] [rbp-41h] BYREF
  PVOID v107; // [rsp+B8h] [rbp-39h] BYREF
  SIZE_T Size; // [rsp+C0h] [rbp-31h]
  HANDLE v109; // [rsp+C8h] [rbp-29h]
  struct VIDMM_PAGING_QUEUE *v110; // [rsp+D0h] [rbp-21h] BYREF
  unsigned __int64 v111; // [rsp+D8h] [rbp-19h] BYREF
  struct _VIDSCH_SYNC_OBJECT *v112; // [rsp+E0h] [rbp-11h] BYREF
  unsigned __int64 v113[8]; // [rsp+E8h] [rbp-9h] BYREF
  char v118; // [rsp+170h] [rbp+7Fh]

  Flags = a2->Flags;
  v8 = a2;
  if ( (*(_DWORD *)&Flags & 0x10000) != 0 && a6 )
  {
    WdLogSingleEntry2(2, this, -1073741811);
    WdLogGlobalForLineNumber = 4083;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Device 0x%I64x: Can not create StandardAllocation from UserMode and Kernel simultaneously,          "
                     "                   returning 0x%I64x",
      (__int64)this,
      -1073741811,
      0,
      0,
      0);
    return 3221225485LL;
  }
  v11 = this[2];
  LODWORD(v12) = 0;
  v99 = 0;
  v118 = 1;
  v13 = (*(_DWORD *)&Flags & 0x40000) == 0;
  v14 = 1;
  if ( (*(_WORD *)&Flags & 0x400) != 0 )
    v13 = 1;
  v103 = v13;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(v11) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 4098;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      4098,
      0,
      0,
      0,
      0);
  }
  v15 = a5;
  v16 = 0;
  v100 = 0;
  if ( !v8->NumAllocations )
  {
LABEL_171:
    *(_DWORD *)&v8->Flags ^= ((unsigned __int16)*(_DWORD *)&v8->Flags ^ (unsigned __int16)(v14 << 14)) & 0x4000;
    return (unsigned int)v12;
  }
  while ( 1 )
  {
    v17 = *((_QWORD *)v15 + 6);
    v18 = v16;
    v105 = 0;
    v19 = &a4[v16];
    v106 = 0;
    v97 = v19;
    v104[0] = (LODWORD(v19->Size) + 4095) & 0xFFFFF000;
    v95 = v103;
    if ( (*(_DWORD *)(v17 + 4) & 0x200F) != 0 )
      v95 = 1;
    v20 = a2;
    if ( !*(_QWORD *)(v17 + 16) && (*(_DWORD *)&a2->Flags & 0x100000) == 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4127;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"pAllocation->m_pAllocation->m_hDriverAllocation != NULL || pKMTCreateAllocation->Flags.NoKmdAccess",
        4127,
        0,
        0,
        0,
        0);
      v20 = a2;
    }
    Value = (struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D)v19->Flags.Value;
    if ( (*(_WORD *)&Value & 0x4000) != 0 )
    {
      v22 = 352LL * ((*((_DWORD *)v15 + 18) >> 12) & 0x3F);
      v23 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this[2] + 2) + 3256LL) + 16LL) + 3120LL);
      v24 = *(_QWORD *)(v22 + v23 + 40);
      if ( !*((_BYTE *)this + 1912) || !v24 )
      {
        WdLogSingleEntry2(2, this, *(_QWORD *)(v22 + v23 + 40));
        WdLogGlobalForLineNumber = 4147;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Driver asking for history buffer, but device history buffer creation is disabled, or adapter doe"
                         "s not have precision data. Device=0x%I64x, PrecisionData=%I64X",
          (__int64)this,
          v24,
          0,
          0,
          0);
LABEL_142:
        LODWORD(v12) = -1073741823;
        goto LABEL_145;
      }
      v19 = v97;
    }
    BaseAddress = 0;
    if ( a7 )
    {
      v67 = *(_QWORD *)(*((_QWORD *)v15 + 5) + 56LL);
      if ( v67 )
        BaseAddress = *(PVOID *)(v67 + 192);
      v68 = v99;
      if ( *(_BYTE *)&v20->Flags < 0 )
        v68 = 1;
      v99 = v68;
      goto LABEL_113;
    }
    v25 = v20->Flags;
    v101 = 0;
    v109 = 0;
    v96 = 0;
    if ( (*(_DWORD *)&v25 & 0x10000) == 0 )
      break;
    if ( (*(_BYTE *)&v25 & 0x20) == 0 )
    {
      if ( (*(_DWORD *)&v25 & 0x20000) != 0 )
      {
        v27 = v18;
        v107 = 0;
        v28 = ObReferenceObjectByHandle(a3[v18].hSection, 0x20000u, MmSectionObjectType, 1, &v107, 0);
        v12 = (struct _DXGK_ALLOCATIONINFO *)v28;
        if ( v28 < 0 )
        {
          WdLogSingleEntry2(2, a3[v27].hSection, v28);
          WdLogGlobalForLineNumber = 4186;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to take a reference on hSection:0x%I64x, returning 0x%I64x",
            (__int64)a3[v27].hSection,
            (__int64)v12,
            0,
            0,
            0);
          goto LABEL_145;
        }
        v29 = v107;
        v19->Flags.Value |= 0x400000u;
        v101 = v29;
        v30 = ProcessSectionAttributes(v29, v19);
        v12 = (struct _DXGK_ALLOCATIONINFO *)v30;
        if ( v30 < 0 )
        {
          WdLogSingleEntry2(2, this, v30);
          WdLogGlobalForLineNumber = 4198;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to query section attributes. Device=0x%I64x, Status=%I64X",
            (__int64)this,
            (__int64)v12,
            0,
            0,
            0);
          v84 = v29;
          goto LABEL_167;
        }
        v31 = *(_QWORD *)(*((_QWORD *)v15 + 5) + 56LL);
        *(_DWORD *)(v31 + 12) |= 0x400u;
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v15 + 5) + 56LL) + 192LL) = v29;
        *(_DWORD *)(v31 + 204) = v19->Alignment;
        *(_DWORD *)(v31 + 12) ^= ((unsigned __int16)*(_DWORD *)(v31 + 12)
                                ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&v19->Flags.0 << 9))
                               & 0x800;
      }
      goto LABEL_50;
    }
    BaseAddress = a3[v18].hSection;
    v19->Flags.Value = *(_DWORD *)&Value | 0x10;
    Current = DXGPROCESS::GetCurrent();
    v12 = v97;
    if ( (*((_DWORD *)Current + 102) & 0x100) != 0 )
      *(_DWORD *)(*((_QWORD *)v15 + 6) + 4LL) |= 0x20000000u;
LABEL_51:
    if ( !a6 || (*(_DWORD *)a6 & 0x40) == 0 )
      goto LABEL_60;
    if ( !*((_QWORD *)a6 + 41) && !*((_QWORD *)a6 + 42) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 4335;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Section object or SystemMem is not supplied for a cross adapter allocation.",
        4335,
        0,
        0,
        0,
        0);
      goto LABEL_142;
    }
    v40 = *(_QWORD *)(*((_QWORD *)v15 + 5) + 56LL);
    *(_DWORD *)(v40 + 12) ^= ((unsigned __int16)*(_DWORD *)(v40 + 12)
                            ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)a6 << 7))
                           & 0x800;
    v41 = (void *)*((_QWORD *)a6 + 42);
    if ( v41 )
    {
      v12->Flags.Value |= 0x10u;
      *(_DWORD *)(v40 + 12) |= 0x200u;
      BaseAddress = v41;
      *(_QWORD *)(v40 + 192) = v41;
      v42 = *((_DWORD *)a6 + 98);
LABEL_59:
      *(_DWORD *)(v40 + 204) = v42;
      goto LABEL_60;
    }
    if ( *((_QWORD *)a6 + 41) )
    {
      v12->Flags.Value |= 0x400000u;
      ObfReferenceObject(*((PVOID *)a6 + 41));
      v43 = (void *)*((_QWORD *)a6 + 41);
      *(_DWORD *)(v40 + 12) |= 0x400u;
      v101 = v43;
      *(_QWORD *)(v40 + 192) = *((_QWORD *)a6 + 41);
      v42 = *((_DWORD *)a6 + 98);
      goto LABEL_59;
    }
LABEL_60:
    v44 = v100;
    if ( (a3[v44].Flags.Value & 4) != 0 )
    {
      v12->AllocationPriority = a3[v44].Priority;
    }
    else if ( !v12->AllocationPriority )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 4379;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"KMD should set a non-zero initial priority for allocations.",
        4379,
        0,
        0,
        0,
        0);
    }
    v45 = *((_QWORD *)v15 + 5);
    v46 = 0;
    if ( v45 )
    {
      if ( (v12->Flags.Value & 0x100000) != 0 )
      {
        v46 = 1;
        if ( !*(_QWORD *)(*(_QWORD *)(v45 + 56) + 184LL) )
        {
          v47 = 0;
          Size = 0;
          if ( (*(_DWORD *)&a2->Flags & 0x10000) != 0 && BaseAddress )
          {
            v47 = BaseAddress;
            Size = a2->pStandardAllocation->ExistingHeapData.Size;
          }
          v48 = *((_QWORD *)this[2] + 95);
          v49 = DXGPROCESS::GetCurrent();
          v50 = *((_DWORD *)v49 + 102) >> 8;
          LOBYTE(v50) = BYTE1(*((_DWORD *)v49 + 102)) & 1;
          v51 = (*(__int64 (__fastcall **)(__int64, PVOID, SIZE_T, __int64))(*(_QWORD *)(v48 + 8) + 1160LL))(
                  *(_QWORD *)(*((_QWORD *)v15 + 5) + 56LL) + 184LL,
                  v47,
                  Size,
                  v50);
          v12 = (struct _DXGK_ALLOCATIONINFO *)v51;
          if ( v51 < 0 )
          {
            WdLogSingleEntry1(2, v51);
            WdLogGlobalForLineNumber = 4414;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed to create VIDMM_CROSSADAPTER_ALLOC, returning 0x%I64x",
              (__int64)v12,
              0,
              0,
              0,
              0);
            if ( v96 )
            {
              v84 = v101;
LABEL_167:
              ObfDereferenceObject(v84);
            }
            goto LABEL_145;
          }
          v12 = v97;
          v46 = 1;
        }
      }
    }
    if ( (*(_DWORD *)&a2->Flags & 0x10020) == 0x10020 )
    {
      if ( (*((_BYTE *)this + 1917) & 1) == 0 && (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 0x10) == 0 )
      {
        LODWORD(v12) = ProcessSysMemAttributes(BaseAddress, v104[0], v12);
        if ( (int)v12 < 0 )
          goto LABEL_145;
      }
      v52 = a2;
      if ( (*(_DWORD *)&a2->Flags & 2) != 0 )
      {
        v53 = v97;
        v54 = *(_QWORD *)(*((_QWORD *)v15 + 5) + 56LL);
        v55 = BaseAddress;
        *(_DWORD *)(v54 + 12) |= 0x200u;
        v56 = *(_DWORD *)(v54 + 12);
        *(_QWORD *)(v54 + 192) = v55;
        *(_DWORD *)(v54 + 204) = v53->Alignment;
        *(_DWORD *)(v54 + 12) = v56
                              ^ ((unsigned __int16)v56
                               ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&v53->Flags.0 << 9))
                              & 0x800;
      }
    }
    else
    {
      v52 = a2;
    }
    v57 = BaseAddress;
    if ( BaseAddress )
    {
      if ( (*(_DWORD *)&v52->Flags & 0x80u) != 0 )
      {
        v58 = *((_QWORD *)v15 + 6);
        v99 = 1;
        *(_DWORD *)(v58 + 4) |= 0x8000000u;
        v59 = *((_QWORD *)v15 + 5);
        if ( v59 )
        {
          v60 = *(_QWORD *)(v59 + 56);
          if ( v60 )
            *(_DWORD *)(v60 + 12) |= 0x1000u;
        }
      }
    }
    if ( v46 )
      v61 = *(_QWORD *)(*((_QWORD *)v15 + 5) + 56LL) + 184LL;
    else
      v61 = 0;
    v19 = v97;
    LODWORD(v12) = (*(__int64 (__fastcall **)(ADAPTER_RENDER *, struct _DXGK_ALLOCATIONINFO *, _QWORD, PVOID, PVOID, HANDLE, __int64, __int64 *, char *))(*(_QWORD *)(*((_QWORD *)this[2] + 95) + 8LL) + 112LL))(
                     this[99],
                     v97,
                     *((_QWORD *)v15 + 6),
                     v101,
                     v57,
                     v109,
                     v61,
                     &v105,
                     &v95);
    if ( !v118 || (v118 = 1, !v95) )
      v118 = 0;
    if ( v96 )
      ObfDereferenceObject(v101);
    if ( (int)v12 < 0 )
      goto LABEL_145;
    v63 = v105;
    if ( !v105 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4484;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pVidMmMultiGlobalAlloc", 4484, 0, 0, 0, 0);
      v63 = v105;
    }
    *(_QWORD *)(*((_QWORD *)v15 + 6) + 8LL) = v63;
    if ( a6 )
    {
      switch ( *((_DWORD *)a6 + 4) )
      {
        case 1:
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          {
            v66 = (_DWORD *)*((_QWORD *)a6 + 3);
            McTemplateK0pqqqqqqq_EtwWriteTransfer(
              (_DWORD)v66,
              (unsigned int)EventCddStandardAllocationSharedPrimarySurface,
              v62,
              *((_QWORD *)v15 + 6),
              *(_DWORD *)a6,
              *v66,
              v66[1],
              v66[2],
              v66[3],
              v66[4],
              v66[5]);
          }
          break;
        case 2:
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          {
            v65 = (_DWORD *)*((_QWORD *)a6 + 3);
            McTemplateK0pqqqqq_EtwWriteTransfer(
              (_DWORD)v65,
              (unsigned int)EventCddStandardAllocationShadowSurface,
              v62,
              *((_QWORD *)v15 + 6),
              *(_DWORD *)a6,
              *v65,
              v65[1],
              v65[2],
              v65[3]);
          }
          break;
        case 3:
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
            McTemplateK0pqtqq_EtwWriteTransfer(
              *((_QWORD *)a6 + 3),
              (unsigned int)EventCddStandardAllocationStagingSurface,
              v62,
              *((_QWORD *)v15 + 6),
              *(_DWORD *)a6,
              **((_DWORD **)a6 + 3),
              *(_DWORD *)(*((_QWORD *)a6 + 3) + 4LL),
              *(_DWORD *)(*((_QWORD *)a6 + 3) + 8LL));
          break;
        default:
          if ( *((_DWORD *)a6 + 4) == 4 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          {
            v64 = (_DWORD *)*((_QWORD *)a6 + 3);
            McTemplateK0pqqqqqqq_EtwWriteTransfer(
              (_DWORD)v64,
              (unsigned int)EventCddStandardAllocationGdiSurface,
              v62,
              *((_QWORD *)v15 + 6),
              *(_DWORD *)a6,
              *v64,
              v64[1],
              v64[2],
              v64[3],
              v64[4],
              v64[5]);
          }
          break;
      }
    }
LABEL_113:
    v69 = this[2];
    v70 = *((_QWORD *)v15 + 6);
    v102 = 0;
    LOBYTE(HandleInformation) = v99 != 0;
    LODWORD(v12) = (*(__int64 (__fastcall **)(_QWORD, ADAPTER_RENDER *, _QWORD, _QWORD, PVOID, POBJECT_HANDLE_INFORMATION, struct DXGALLOCATION *, __int64 *, int *, char *))(*(_QWORD *)(*((_QWORD *)v69 + 95) + 8LL) + 128LL))(
                     *((_QWORD *)v69 + 96),
                     this[99],
                     *(_QWORD *)(v70 + 8),
                     v19->MaximumRenamingListLength,
                     BaseAddress,
                     HandleInformation,
                     v15,
                     &v106,
                     &v102,
                     &v95);
    if ( !v118 || (v118 = 1, !v95) )
      v118 = 0;
    v71 = v102 & 0x3F;
    *((_DWORD *)v15 + 18) = *((_DWORD *)v15 + 18) & 0xFFFC0FFF | (v71 << 12);
    *(_DWORD *)(*((_QWORD *)v15 + 6) + 4LL) = *(_DWORD *)(*((_QWORD *)v15 + 6) + 4LL) & 0xF81FFFFF | (v71 << 21);
    if ( (int)v12 < 0 )
      goto LABEL_145;
    v72 = v106;
    if ( !v106 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4589;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pVidMmMultiAlloc", 4589, 0, 0, 0, 0);
      v72 = v106;
    }
    v73 = (struct VIDMM_MULTI_ALLOC **)((char *)v15 + 24);
    *((_QWORD *)v15 + 3) = v72;
    v74 = (struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D)v19->Flags.Value;
    v75 = *((_QWORD *)v15 + 6);
    if ( (*(_WORD *)&v74 & 0x100) != 0 )
    {
      *(_DWORD *)(v75 + 4) |= 8u;
    }
    else
    {
      v76 = *(_DWORD *)(v75 + 4);
      if ( (v76 & 0x20) == 0 && (*(_DWORD *)&v74 & 0x20200) == 0 && (v76 & 0x4000) == 0 )
      {
        v78 = (struct VIDMM_MULTI_ALLOC **)((char *)v15 + 24);
        goto LABEL_133;
      }
      v73 = (struct VIDMM_MULTI_ALLOC **)((char *)v15 + 24);
    }
    if ( (v19->Flags.Value & 0x200) != 0 )
      *(_DWORD *)(*((_QWORD *)v15 + 6) + 4LL) |= 0x20u;
    if ( (v19->Flags.Value & 0x20000) != 0 )
      *(_DWORD *)(*((_QWORD *)v15 + 6) + 4LL) |= 0x4000u;
    LODWORD(v12) = VIDMM_EXPORT::VidMmPinAllocation(
                     *((VIDMM_EXPORT **)this[2] + 95),
                     *((struct VIDMM_GLOBAL **)this[2] + 96),
                     *v73,
                     0,
                     0);
    if ( (int)v12 < 0 )
      goto LABEL_145;
    v77 = *((_QWORD *)v15 + 6);
    v78 = (struct VIDMM_MULTI_ALLOC **)((char *)v15 + 24);
    *((_DWORD *)v15 + 18) |= 0x800u;
    if ( (*(_DWORD *)(v77 + 4) & 0x4000) != 0 )
    {
      VIDMM_EXPORT::VidMmUnpinAllocation(
        *((VIDMM_EXPORT **)this[2] + 95),
        *((struct VIDMM_GLOBAL **)this[2] + 96),
        *v78);
      *((_DWORD *)v15 + 18) &= ~0x800u;
    }
LABEL_133:
    if ( DXGDEVICE::UmdManagesResidency((DXGDEVICE *)this) && a6 && *((_DWORD *)a6 + 4) == 2 )
    {
      v79 = this[2];
      v80 = this[99];
      v81 = *((_DWORD *)v15 + 18) >> 12;
      v110 = 0;
      v112 = 0;
      VIDMM_EXPORT::VidMmGetDevicePagingQueue(*((VIDMM_EXPORT **)v79 + 95), v80, v81 & 0x3F, &v110, &v112);
      v82 = this[2];
      v111 = 0;
      v113[0] = 0;
      Resident = VIDMM_EXPORT::VidMmMakeResident(
                   *((VIDMM_EXPORT **)v82 + 95),
                   *((struct VIDMM_GLOBAL **)v82 + 96),
                   v110,
                   v78,
                   1u,
                   3u,
                   &v111,
                   v113);
      v12 = (struct _DXGK_ALLOCATIONINFO *)Resident;
      if ( Resident < 0 )
      {
        WdLogSingleEntry1(2, Resident);
        WdLogGlobalForLineNumber = 4676;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to make shadow allocation resident. Status = 0x%I64x",
          (__int64)v12,
          0,
          0,
          0,
          0);
        goto LABEL_145;
      }
      if ( Resident == 259 )
      {
        VIDMM_EXPORT::VidMmWaitForFences(
          *((VIDMM_EXPORT **)this[2] + 95),
          *((struct VIDMM_GLOBAL **)this[2] + 96),
          &v112,
          &v111,
          Object);
        LODWORD(v12) = 0;
      }
    }
    v8 = a2;
    v16 = v100 + 1;
    v100 = v16;
    if ( v16 >= a2->NumAllocations )
    {
      if ( (int)v12 >= 0 )
      {
        v14 = v118;
        goto LABEL_171;
      }
      goto LABEL_145;
    }
    v15 = (struct DXGALLOCATION *)*((_QWORD *)v15 + 8);
  }
  if ( (*(_BYTE *)&v25 & 0x20) != 0 )
  {
    if ( (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 0x100) != 0 )
    {
      hSection = a3[v18].hSection;
      v19->Flags.Value |= 0x10u;
      v33 = *((_QWORD *)v15 + 6);
      BaseAddress = hSection;
      *(_DWORD *)(v33 + 4) |= 0x20000000u;
    }
    else
    {
      v34 = v19->Size;
      if ( v34 > v104[0] )
      {
        LODWORD(v12) = -1073741811;
        WdLogSingleEntry2(2, v34, -1073741811);
        v90 = L"Overflow rounding allocation size 0x%I64x to next page boundary returning 0x%I64x";
        WdLogGlobalForLineNumber = 4247;
        v91 = v97->Size;
        HandleInformationa = -1073741811;
        goto LABEL_159;
      }
      v35 = v104[0];
      v19->Size = v104[0];
      v36 = (void *)(*((__int64 (__fastcall **)(_QWORD, __int64))a6 + 4))(*((_QWORD *)a6 + 5), v35);
      BaseAddress = v36;
      if ( !v36 )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 4254;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Cannot allocate memory allocation for existing sys mem.",
          4254,
          0,
          0,
          0,
          0);
        goto LABEL_142;
      }
      a3[v18].hSection = v36;
    }
    goto LABEL_50;
  }
  v37 = v18;
  if ( (a3[v18].Flags.Value & 8) == 0 )
  {
    if ( (*(_BYTE *)&Value & 0x10) != 0 )
    {
      BaseAddress = a3[v37].hSection;
    }
    else if ( (*(_DWORD *)&Value & 0x400000) != 0 )
    {
      if ( v20->NumAllocations != 1 || (*(_DWORD *)&Value & 0x2000000) == 0 || !a6 || !*((_QWORD *)a6 + 4) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 4307;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"(pKMTCreateAllocation->NumAllocations == 1) && (pDriverAllocations[i].Flags.DoDPrimary) && (pCre"
                         "ateStandardAllocation != NULL) && (pCreateStandardAllocation->pfnAllocateSysMem != NULL)",
          4307,
          0,
          0,
          0,
          0);
      }
      v101 = (PVOID)(*((__int64 (__fastcall **)(_QWORD, _QWORD))a6 + 4))(*((_QWORD *)a6 + 5), v104[0]);
      if ( !v101 )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 4313;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Cannot create section object for DoD primary backing store.",
          4313,
          0,
          0,
          0,
          0);
        goto LABEL_142;
      }
      v96 = 1;
    }
LABEL_50:
    v12 = v97;
    goto LABEL_51;
  }
  if ( !(unsigned int)Feature_SupportHostManagedPresentationInDxgkrnl__private_IsEnabledDeviceUsageNoInline() )
  {
    LODWORD(v12) = -1073741811;
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 4266;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Allocations backed by guest system memory is not supported when host managed presentation is disable"
                     "d, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
    goto LABEL_145;
  }
  v38 = *((_DWORD *)DXGPROCESS::GetCurrent() + 102);
  if ( (v38 & 0x8000) == 0 && (v38 & 0x10000) == 0 )
  {
    LODWORD(v12) = -1073741811;
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 4274;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"GuestExistingSysMem flag is set but the current process is not a proxy process for the host managed "
                     "presentation, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
    goto LABEL_145;
  }
  v12 = v97;
  if ( (v38 & 0x10000) != 0 || (v97->Flags.Value & 1) == 0 )
  {
    v39 = a3[v37].hSection;
    v97->Flags.Value |= 4u;
    v109 = v39;
    *(_DWORD *)(*((_QWORD *)v15 + 6) + 4LL) |= 0x40000000u;
    goto LABEL_51;
  }
  LODWORD(v12) = -1073741811;
  WdLogSingleEntry0(2);
  v90 = L"Driver should not set the CpuVisible flag for allocations backed by guest system memory.";
  v91 = 4287;
  HandleInformationa = 0;
  WdLogGlobalForLineNumber = 4287;
LABEL_159:
  DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v90, v91, HandleInformationa, 0, 0, 0);
LABEL_145:
  v85 = 0;
  if ( a2->NumAllocations )
  {
    v86 = a5;
    do
    {
      if ( (*((_DWORD *)v86 + 18) & 0x800) != 0 )
      {
        VIDMM_EXPORT::VidMmUnpinAllocation(
          *((VIDMM_EXPORT **)this[2] + 95),
          *((struct VIDMM_GLOBAL **)this[2] + 96),
          *((struct VIDMM_MULTI_ALLOC **)v86 + 3));
        *((_DWORD *)v86 + 18) &= ~0x800u;
      }
      v87 = *((_QWORD *)v86 + 6);
      v88 = *(struct VIDMM_MULTI_GLOBAL_ALLOC **)(v87 + 8);
      if ( v88
        && !a7
        && (!*((_DWORD *)this + 116) && (*(_DWORD *)(v87 + 4) & 1) != 0 || (*(_DWORD *)(v87 + 4) & 2) != 0) )
      {
        VIDMM_EXPORT::VidMmInvalidateAllocation(
          *((VIDMM_EXPORT **)this[2] + 95),
          *((struct VIDMM_GLOBAL **)this[2] + 96),
          v88);
        *(_DWORD *)(*((_QWORD *)v86 + 6) + 4LL) |= 0x10u;
      }
      v89 = (struct VIDMM_MULTI_ALLOC *)*((_QWORD *)v86 + 3);
      if ( v89 )
      {
        VIDMM_EXPORT::VidMmCloseAllocation(
          *((VIDMM_EXPORT **)this[2] + 95),
          *((struct VIDMM_GLOBAL **)this[2] + 96),
          v89,
          0,
          (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
        *((_QWORD *)v86 + 3) = 0;
      }
      else
      {
        DXGDEVICE::TraceCloseParavirtualizedAllocation((DXGDEVICE *)this, v86);
      }
      if ( !a7 )
        DXGDEVICE::DestroyAdapterAllocation((DXGDEVICE *)this, *((struct DXGADAPTERALLOCATION **)v86 + 6));
      v86 = (struct DXGALLOCATION *)*((_QWORD *)v86 + 8);
      ++v85;
    }
    while ( v85 < a2->NumAllocations );
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140403758  mov     rax, rsp
0x14040375b  mov     [rax+8], rbx
0x14040375f  mov     [rax+20h], r9
0x140403763  mov     [rax+18h], r8
0x140403767  mov     [rax+10h], rdx
0x14040376b  push    rbp
0x14040376c  push    rsi
0x14040376d  push    rdi
0x14040376e  push    r12
0x140403770  push    r13
0x140403772  push    r14
0x140403774  push    r15
0x140403776  lea     rbp, [rax-3Fh]
0x14040377a  sub     rsp, 0F0h
0x140403781  mov     r10d, [rdx+38h]
0x140403785  xor     ebx, ebx
0x140403787  mov     rdi, rdx
0x14040378a  mov     r14, rcx
0x14040378d  bt      r10d, 10h
0x140403792  jnb     short loc_1404037F7
0x140403794  cmp     [rbp+37h+arg_28], rbx
0x140403798  jz      short loc_1404037F7
0x14040379a  mov     rdx, rcx
0x14040379d  mov     rdi, 0FFFFFFFFC000000Dh
0x1404037a4  mov     r8, rdi
0x1404037a7  lea     ecx, [rbx+2]
0x1404037aa  call    cs:__imp_WdLogSingleEntry2
0x1404037b1  nop     dword ptr [rax+rax+00h]
0x1404037b6  mov     [rsp+120h+var_E0], rbx
0x1404037bb  lea     r9, aDevice0xI64xCa_0; "Device 0x%I64x: Can not create Standard"...
0x1404037c2  mov     [rsp+120h+var_E8], rbx
0x1404037c7  or      r8d, 0FFFFFFFFh
0x1404037cb  mov     [rsp+120h+var_F0], rbx
0x1404037d0  mov     edx, 40000h
0x1404037d5  mov     [rsp+120h+HandleInformation], rdi
0x1404037da  xor     ecx, ecx
0x1404037dc  mov     [rsp+120h+Object], r14
0x1404037e1  mov     cs:WdLogGlobalForLineNumber, 0FF3h
0x1404037eb  call    DxgkLogInternalTriageEvent
0x1404037f0  mov     eax, edi
0x1404037f2  jmp     loc_140404947
0x1404037f7  mov     rcx, [rcx+10h]; this
0x1404037fb  mov     eax, r10d
0x1404037fe  shr     eax, 12h
0x140403801  mov     esi, ebx
0x140403803  not     al
0x140403805  mov     [rbp+37h+var_A0], ebx
0x140403808  mov     ebx, 1
0x14040380d  and     al, bl
0x14040380f  mov     byte ptr [rbp+37h+arg_38], bl
0x140403812  bt      r10d, 0Ah
0x140403817  movzx   eax, al
0x14040381a  mov     r12b, bl
0x14040381d  cmovb   eax, ebx
0x140403820  mov     [rbp+37h+var_8C], eax
0x140403823  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140403828  or      r13d, 0FFFFFFFFh
0x14040382c  test    al, al
0x14040382e  jnz     short loc_140403878
0x140403830  mov     ecx, ebx
0x140403832  call    cs:__imp_WdLogSingleEntry0
0x140403839  nop     dword ptr [rax+rax+00h]
0x14040383e  xor     ecx, ecx
0x140403840  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x140403847  mov     [rsp+120h+var_E0], rcx
0x14040384c  mov     eax, 1002h
0x140403851  mov     [rsp+120h+var_E8], rcx
0x140403856  mov     r8d, r13d
0x140403859  mov     [rsp+120h+var_F0], rcx
0x14040385e  mov     edx, 40002h
0x140403863  mov     [rsp+120h+HandleInformation], rcx
0x140403868  mov     [rsp+120h+Object], rax
0x14040386d  mov     cs:WdLogGlobalForLineNumber, eax
0x140403873  call    DxgkLogInternalTriageEvent
0x140403878  mov     r15, [rbp+37h+arg_20]
0x14040387c  xor     eax, eax
0x14040387e  mov     [rbp+37h+var_9C], eax
0x140403881  cmp     [rdi+2Ch], eax
0x140403884  jbe     loc_14040492E
0x14040388a  lea     r12d, [rax+2]
0x14040388e  mov     rcx, [r15+30h]
0x140403892  mov     esi, eax
0x140403894  imul    rdi, rsi, 58h ; 'X'
0x140403898  mov     [rbp+37h+var_80], 0
0x1404038a0  add     rdi, [rbp+37h+arg_18]
0x1404038a4  mov     [rbp+37h+var_78], 0
0x1404038ac  mov     [rsp+120h+var_B8], rdi
0x1404038b1  mov     eax, [rdi+10h]
0x1404038b4  add     eax, 0FFFh
0x1404038b9  and     eax, 0FFFFF000h
0x1404038be  mov     [rbp+37h+var_88], eax
0x1404038c1  mov     eax, [rbp+37h+var_8C]
0x1404038c4  mov     byte ptr [rsp+120h+var_C0], al
0x1404038c8  test    dword ptr [rcx+4], 200Fh
0x1404038cf  jz      short loc_1404038D5
0x1404038d1  mov     byte ptr [rsp+120h+var_C0], bl
0x1404038d5  cmp     qword ptr [rcx+10h], 0
0x1404038da  mov     r9, [rbp+37h+arg_8]
0x1404038de  jnz     short loc_140403938
0x1404038e0  test    dword ptr [r9+38h], 100000h
0x1404038e8  jnz     short loc_140403938
0x1404038ea  mov     ecx, ebx
0x1404038ec  call    cs:__imp_WdLogSingleEntry0
0x1404038f3  nop     dword ptr [rax+rax+00h]
0x1404038f8  xor     eax, eax
0x1404038fa  lea     r9, aPallocationMPa_1; "pAllocation->m_pAllocation->m_hDriverAl"...
0x140403901  mov     [rsp+120h+var_E0], rax
0x140403906  mov     ecx, 101Fh
0x14040390b  mov     [rsp+120h+var_E8], rax
0x140403910  mov     r8d, r13d
0x140403913  mov     [rsp+120h+var_F0], rax
0x140403918  mov     edx, 40002h
0x14040391d  mov     [rsp+120h+HandleInformation], rax
0x140403922  mov     [rsp+120h+Object], rcx
0x140403927  mov     cs:WdLogGlobalForLineNumber, ecx
0x14040392d  xor     ecx, ecx
0x14040392f  call    DxgkLogInternalTriageEvent
0x140403934  mov     r9, [rbp+37h+arg_8]
0x140403938  mov     r8d, [rdi+40h]
0x14040393c  bt      r8d, 0Eh
0x140403941  jnb     short loc_140403990
0x140403943  mov     eax, [r15+48h]
0x140403947  shr     rax, 0Ch
0x14040394b  and     eax, 3Fh
0x14040394e  imul    rdx, rax, 160h
0x140403955  cmp     byte ptr [r14+778h], 0
0x14040395d  mov     rax, [r14+10h]
0x140403961  mov     rcx, [rax+10h]
0x140403965  mov     rax, [rcx+0CB8h]
0x14040396c  mov     rcx, [rax+10h]
0x140403970  mov     rax, [rcx+0C30h]
0x140403977  mov     rdi, [rdx+rax+28h]
0x14040397c  jz      loc_14040448C
0x140403982  test    rdi, rdi
0x140403985  jz      loc_14040448C
0x14040398b  mov     rdi, [rsp+120h+var_B8]
0x140403990  cmp     [rbp+37h+arg_30], 0
0x140403994  mov     [rbp+37h+BaseAddress], 0
0x14040399c  jnz     loc_14040417C
0x1404039a2  mov     ecx, [r9+38h]
0x1404039a6  mov     eax, ecx
0x1404039a8  and     eax, 20h
0x1404039ab  mov     [rbp+37h+var_98], 0
0x1404039b3  mov     [rbp+37h+var_60], 0
0x1404039bb  mov     byte ptr [rsp+120h+var_C0+1], 0
0x1404039c0  bt      ecx, 10h
0x1404039c4  jnb     loc_140403ADB
0x1404039ca  test    eax, eax
0x1404039cc  jz      short loc_140403A14
0x1404039ce  mov     r11, [rbp+37h+arg_10]
0x1404039d2  lea     rax, [rsi+rsi*2]
0x1404039d6  shl     rax, 5
0x1404039da  or      r8d, 10h
0x1404039de  mov     rax, [rax+r11+8]
0x1404039e3  mov     [rbp+37h+BaseAddress], rax
0x1404039e7  mov     [rdi+40h], r8d
0x1404039eb  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1404039f0  mov     rsi, [rsp+120h+var_B8]
0x1404039f5  mov     ecx, [rax+198h]
0x1404039fb  shr     ecx, 8
0x1404039fe  test    bl, cl
0x140403a00  jz      loc_140403C89
0x140403a06  mov     rax, [r15+30h]
0x140403a0a  bts     dword ptr [rax+4], 1Dh
0x140403a0f  jmp     loc_140403C89
0x140403a14  bt      ecx, 11h
0x140403a18  jnb     loc_140403C84
0x140403a1e  mov     r8, cs:__imp_MmSectionObjectType
0x140403a25  lea     rax, [rbp+37h+var_70]
0x140403a29  mov     r11, [rbp+37h+arg_10]
0x140403a2d  lea     r12, [rsi+rsi*2]
0x140403a31  shl     r12, 5
0x140403a35  mov     r9b, bl; AccessMode
0x140403a38  mov     [rsp+120h+HandleInformation], 0; HandleInformation
0x140403a41  mov     edx, 20000h; DesiredAccess
0x140403a46  mov     r8, [r8]; ObjectType
0x140403a49  mov     [rbp+37h+var_70], 0
0x140403a51  mov     rcx, [r12+r11+8]; Handle
0x140403a56  mov     [rsp+120h+Object], rax; Object
0x140403a5b  call    cs:__imp_ObReferenceObjectByHandle
0x140403a62  nop     dword ptr [rax+rax+00h]
0x140403a67  movsxd  rsi, eax
0x140403a6a  test    eax, eax
0x140403a6c  js      loc_140404542
0x140403a72  mov     r12, [rbp+37h+var_70]
0x140403a76  mov     rdx, rdi; struct _DXGK_ALLOCATIONINFO *
0x140403a79  bts     dword ptr [rdi+40h], 16h
0x140403a7e  mov     rcx, r12; Object
0x140403a81  mov     [rbp+37h+var_98], r12
0x140403a85  call    ?ProcessSectionAttributes@@YAJPEAXPEAU_DXGK_ALLOCATIONINFO@@@Z; ProcessSectionAttributes(void *,_DXGK_ALLOCATIONINFO *)
0x140403a8a  movsxd  rsi, eax
0x140403a8d  test    eax, eax
0x140403a8f  js      loc_1404044E7
0x140403a95  mov     rax, [r15+28h]
0x140403a99  mov     rdx, [rax+38h]
0x140403a9d  bts     dword ptr [rdx+0Ch], 0Ah
0x140403aa2  mov     rax, [r15+28h]
0x140403aa6  mov     rcx, [rax+38h]
0x140403aaa  mov     [rcx+0C0h], r12
0x140403ab1  mov     r12d, 2
0x140403ab7  mov     eax, [rdi+0Ch]
0x140403aba  mov     [rdx+0CCh], eax
0x140403ac0  mov     eax, [rdx+0Ch]
0x140403ac3  mov     ecx, [rdi+40h]
0x140403ac6  shl     ecx, 9
0x140403ac9  xor     ecx, eax
0x140403acb  and     ecx, 800h
0x140403ad1  xor     ecx, eax
0x140403ad3  mov     [rdx+0Ch], ecx
0x140403ad6  jmp     loc_140403C84
0x140403adb  test    eax, eax
0x140403add  jz      loc_140403B6B
0x140403ae3  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140403ae8  mov     ecx, [rax+198h]
0x140403aee  shr     ecx, 8
0x140403af1  test    bl, cl
0x140403af3  jz      short loc_140403B1C
0x140403af5  mov     r11, [rbp+37h+arg_10]
0x140403af9  lea     rax, [rsi+rsi*2]
0x140403afd  shl     rax, 5
0x140403b01  mov     rcx, [rax+r11+8]
0x140403b06  or      dword ptr [rdi+40h], 10h
0x140403b0a  mov     rax, [r15+30h]
0x140403b0e  mov     [rbp+37h+BaseAddress], rcx
0x140403b12  bts     dword ptr [rax+4], 1Dh
0x140403b17  jmp     loc_140403C84
0x140403b1c  mov     r8, qword ptr [rbp+37h+var_88]
0x140403b20  mov     rdx, [rdi+10h]
0x140403b24  mov     eax, r8d
0x140403b27  cmp     rdx, rax
0x140403b2a  ja      loc_1404046A9
0x140403b30  mov     rcx, [rbp+37h+arg_28]
0x140403b34  mov     edx, r8d
0x140403b37  mov     [rdi+10h], rax
0x140403b3b  mov     rax, [rcx+20h]
0x140403b3f  mov     rcx, [rcx+28h]
0x140403b43  call    _guard_dispatch_icall
0x140403b48  mov     [rbp+37h+BaseAddress], rax
0x140403b4c  test    rax, rax
0x140403b4f  jz      loc_140404667
0x140403b55  mov     r11, [rbp+37h+arg_10]
0x140403b59  lea     rcx, [rsi+rsi*2]
0x140403b5d  shl     rcx, 5
0x140403b61  mov     [rcx+r11+8], rax
0x140403b66  jmp     loc_140403C84
0x140403b6b  mov     rcx, [rbp+37h+arg_10]
0x140403b6f  lea     rdi, [rsi+rsi*2]
0x140403b73  shl     rdi, 5
0x140403b77  mov     eax, [rdi+rcx+20h]
0x140403b7b  test    al, 8
0x140403b7d  jz      short loc_140403BDD
0x140403b7f  call    Feature_SupportHostManagedPresentationInDxgkrnl__private_IsEnabledDeviceUsageNoInline
0x140403b84  test    eax, eax
0x140403b86  jz      loc_14040479C
0x140403b8c  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140403b91  mov     ecx, [rax+198h]
0x140403b97  mov     eax, ecx
0x140403b99  shr     eax, 10h
0x140403b9c  bt      ecx, 0Fh
0x140403ba0  jb      short loc_140403BAA
0x140403ba2  test    bl, al
0x140403ba4  jz      loc_14040470E
0x140403baa  mov     rsi, [rsp+120h+var_B8]
0x140403baf  test    bl, al
0x140403bb1  jnz     short loc_140403BBE
0x140403bb3  mov     eax, [rsi+40h]
0x140403bb6  test    bl, al
0x140403bb8  jnz     loc_140404758
0x140403bbe  mov     r11, [rbp+37h+arg_10]
0x140403bc2  mov     rax, [rdi+r11+8]
0x140403bc7  or      dword ptr [rsi+40h], 4
0x140403bcb  mov     [rbp+37h+var_60], rax
0x140403bcf  mov     rax, [r15+30h]
0x140403bd3  bts     dword ptr [rax+4], 1Eh
0x140403bd8  jmp     loc_140403C89
0x140403bdd  test    r8b, 10h
0x140403be1  jz      short loc_140403BF1
0x140403be3  mov     rax, [rdi+rcx+8]
0x140403be8  mov     [rbp+37h+BaseAddress], rax
0x140403bec  jmp     loc_140403C84
0x140403bf1  bt      r8d, 16h
0x140403bf6  jnb     loc_140403C84
0x140403bfc  mov     rdi, [rbp+37h+arg_28]
0x140403c00  cmp     [r9+2Ch], ebx
0x140403c04  jnz     short loc_140403C19
0x140403c06  bt      r8d, 19h
0x140403c0b  jnb     short loc_140403C19
0x140403c0d  test    rdi, rdi
0x140403c10  jz      short loc_140403C19
0x140403c12  cmp     qword ptr [rdi+20h], 0
0x140403c17  jnz     short loc_140403C63
0x140403c19  mov     ecx, ebx
0x140403c1b  call    cs:__imp_WdLogSingleEntry0
0x140403c22  nop     dword ptr [rax+rax+00h]
0x140403c27  xor     eax, eax
0x140403c29  lea     r9, aPkmtcreateallo; "(pKMTCreateAllocation->NumAllocations ="...
0x140403c30  mov     [rsp+120h+var_E0], rax
0x140403c35  mov     ecx, 10D3h
0x140403c3a  mov     [rsp+120h+var_E8], rax
0x140403c3f  mov     r8d, r13d
  ... truncated ...
```
