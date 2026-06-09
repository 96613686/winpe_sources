# DXGDEVICE::CreateVidMmAllocations(_D3DKMT_CREATEALLOCATION *,_D3DDDI_ALLOCATIONINFO2 *,_DXGK_ALLOCATIONINFO *,DXGALLOCATION *,_D3DKM_CREATESTANDARDALLOCATION const *,uchar,COREDEVICEACCESS *)

- ea: `0x1403b9a2c`
- end: `0x1403babf4`
- name: `?CreateVidMmAllocations@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@PEAU_DXGK_ALLOCATIONINFO@@PEAVDXGALLOCATION@@PEBU_D3DKM_CREATESTANDARDALLOCATION@@EPEAVCOREDEVICEACCESS@@@Z`
- size: `4552`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, struct _D3DKMT_CREATEALLOCATION *@<rdx>, struct _D3DDDI_ALLOCATIONINFO2 *@<r8>, struct _DXGK_ALLOCATIONINFO *@<r9>, struct DXGALLOCATION *, const struct _D3DKM_CREATESTANDARDALLOCATION *, unsigned __int8, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140377040`

## callees

- `0x14001b890`
- `0x14002d9f0`
- `0x14003c1e8`
- `0x14003f134`
- `0x14003f930`
- `0x1400490ac`
- `0x14004ce64`
- `0x14004d914`
- `0x140052380`
- `0x1400530e8`
- `0x140057858`
- `0x1400592cc`
- `0x1400a01e0`
- `0x1401958c8`
- `0x14020da68`
- `0x14020db94`
- `0x14031d034`
- `0x140323854`
- `0x1403b9a2c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1403ba62e`
- `ntoskrnl!ObfDereferenceObject` at `0x1403bab99`
- `ntoskrnl!ObfDereferenceObject` at `0x1403ba62e`
- `ntoskrnl!ObfDereferenceObject` at `0x1403bab99`
- `ntoskrnl!ObfReferenceObject` at `0x1403ba495`
- `ntoskrnl!ObfReferenceObject` at `0x1403ba495`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403ba28d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403ba28d`
- `ntoskrnl!MmSectionObjectType` at `0x1403ba250`
- `watchdog!WdLogSingleEntry2` at `0x1403ba09c`
- `watchdog!WdLogSingleEntry2` at `0x1403ba95c`
- `watchdog!WdLogSingleEntry2` at `0x1403ba9a4`
- `watchdog!WdLogSingleEntry2` at `0x1403baa05`
- `watchdog!WdLogSingleEntry2` at `0x1403baaab`
- `watchdog!WdLogSingleEntry2` at `0x1403ba09c`
- `watchdog!WdLogSingleEntry2` at `0x1403ba95c`
- `watchdog!WdLogSingleEntry2` at `0x1403ba9a4`
- `watchdog!WdLogSingleEntry2` at `0x1403baa05`
- `watchdog!WdLogSingleEntry2` at `0x1403baaab`
- `watchdog!WdLogSingleEntry0` at `0x1403b9b78`
- `watchdog!WdLogSingleEntry0` at `0x1403b9bee`
- `watchdog!WdLogSingleEntry0` at `0x1403ba0e9`
- `watchdog!WdLogSingleEntry0` at `0x1403ba144`
- `watchdog!WdLogSingleEntry0` at `0x1403ba3da`
- `watchdog!WdLogSingleEntry0` at `0x1403ba4e3`
- `watchdog!WdLogSingleEntry0` at `0x1403ba641`
- `watchdog!WdLogSingleEntry0` at `0x1403ba789`
- `watchdog!WdLogSingleEntry0` at `0x1403baa50`
- `watchdog!WdLogSingleEntry0` at `0x1403b9b78`
- `watchdog!WdLogSingleEntry0` at `0x1403b9bee`
- `watchdog!WdLogSingleEntry0` at `0x1403ba0e9`
- `watchdog!WdLogSingleEntry0` at `0x1403ba144`
- `watchdog!WdLogSingleEntry0` at `0x1403ba3da`
- `watchdog!WdLogSingleEntry0` at `0x1403ba4e3`
- `watchdog!WdLogSingleEntry0` at `0x1403ba641`
- `watchdog!WdLogSingleEntry0` at `0x1403ba789`
- `watchdog!WdLogSingleEntry0` at `0x1403baa50`
- `watchdog!WdLogSingleEntry1` at `0x1403baaf1`
- `watchdog!WdLogSingleEntry1` at `0x1403bab45`
- `watchdog!WdLogSingleEntry1` at `0x1403baaf1`
- `watchdog!WdLogSingleEntry1` at `0x1403bab45`

## string_xrefs

- `0x1403b9b8d`: `(pKMTCreateAllocation->NumAllocations == 1) && (pDriverAllocations[i].Flags.DoDPrimary) && (pCreateStandardAllocation != NULL) && (pCreateStandardAllocation->pfnAllocateSysMem != NULL)`
- `0x1403b9c03`: `Cannot create section object for DoD primary backing store.`
- `0x1403ba0ad`: `Device 0x%I64x: Can not create StandardAllocation from UserMode and Kernel simultaneously,                             returning 0x%I64x`
- `0x1403ba152`: `pAllocation->m_pAllocation->m_hDriverAllocation != NULL || pKMTCreateAllocation->Flags.NoKmdAccess`
- `0x1403bab56`: `Failed to create VIDMM_CROSSADAPTER_ALLOC, returning 0x%I64x`
- `0x1403bab0e`: `Failed to make shadow allocation resident. Status = 0x%I64x`

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
  D3DKMT_CREATEALLOCATIONFLAGS Flags; // ecx
  struct _D3DKMT_CREATEALLOCATION *v9; // rdi
  __int64 v10; // rsi
  bool v11; // cf
  BOOL v12; // eax
  ADAPTER_RENDER *v13; // rcx
  struct DXGALLOCATION *v14; // r15
  UINT v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rsi
  struct _DXGK_ALLOCATIONINFO *v18; // rdi
  struct _D3DKMT_CREATEALLOCATION *v19; // r9
  struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D Value; // r8d
  D3DKMT_CREATEALLOCATIONFLAGS v21; // ecx
  UINT v22; // edi
  struct DXGALLOCATION *v23; // r15
  __int64 v24; // rcx
  struct VIDMM_MULTI_GLOBAL_ALLOC *v25; // r8
  struct VIDMM_MULTI_ALLOC *v26; // r8
  struct _DXGK_ALLOCATIONINFO *v27; // rdx
  __int64 v28; // rcx
  char v29; // r12
  struct _D3DKMT_CREATEALLOCATION *v30; // rsi
  PVOID *v31; // rdi
  __int64 v32; // rcx
  PVOID v33; // r12
  int v34; // r8d
  __int64 v35; // rcx
  __int64 *v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  ADAPTER_RENDER *v39; // rcx
  __int64 v40; // r8
  int v41; // ecx
  __int64 v42; // rax
  struct _DXGK_ALLOCATIONINFO *v43; // r8
  struct VIDMM_MULTI_ALLOC **v44; // rdi
  __int64 v45; // rax
  struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D v46; // ecx
  int v47; // edx
  PVOID v48; // rsi
  SIZE_T v49; // r12
  __int64 v50; // rdi
  struct DXGPROCESS *v51; // rax
  __int64 v52; // r9
  int v53; // eax
  __int64 v54; // rdi
  HANDLE hSection; // rcx
  __int64 v56; // r12
  NTSTATUS v57; // eax
  PVOID v58; // r12
  int v59; // eax
  __int64 v60; // rdx
  unsigned int v61; // ecx
  unsigned __int64 Size; // rdx
  void *v63; // rax
  __int64 v64; // rdi
  __int64 v65; // rax
  void *v66; // rax
  struct DXGPROCESS *Current; // rax
  struct _DXGK_ALLOCATIONINFO *v68; // rdi
  __int64 v69; // rdx
  PVOID v70; // rax
  int v71; // ecx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  _DWORD *v75; // rcx
  _DWORD *v76; // rcx
  __int64 v77; // rax
  ADAPTER_RENDER *v78; // rcx
  struct VIDMM_DEVICE *v79; // rdx
  int v80; // r8d
  ADAPTER_RENDER *v81; // rcx
  int Resident; // eax
  PVOID v83; // rcx
  const wchar_t *v84; // r9
  PVOID *Objectb; // [rsp+28h] [rbp-B9h]
  unsigned int Object; // [rsp+28h] [rbp-B9h]
  PVOID *Objecta; // [rsp+28h] [rbp-B9h]
  POBJECT_HANDLE_INFORMATION HandleInformation; // [rsp+30h] [rbp-B1h]
  __int64 HandleInformationa; // [rsp+30h] [rbp-B1h]
  char v91; // [rsp+68h] [rbp-79h] BYREF
  char v92; // [rsp+69h] [rbp-78h]
  struct _DXGK_ALLOCATIONINFO *v93; // [rsp+70h] [rbp-71h]
  PVOID BaseAddress; // [rsp+78h] [rbp-69h]
  int v95; // [rsp+80h] [rbp-61h]
  int v96; // [rsp+84h] [rbp-5Dh] BYREF
  UINT v97; // [rsp+88h] [rbp-59h]
  PVOID v98; // [rsp+90h] [rbp-51h]
  BOOL v99; // [rsp+98h] [rbp-49h]
  unsigned int v100[2]; // [rsp+A0h] [rbp-41h]
  __int64 v101; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v102; // [rsp+B0h] [rbp-31h] BYREF
  PVOID v103; // [rsp+B8h] [rbp-29h] BYREF
  struct VIDMM_PAGING_QUEUE *v104; // [rsp+C0h] [rbp-21h] BYREF
  unsigned __int64 v105; // [rsp+C8h] [rbp-19h] BYREF
  struct _VIDSCH_SYNC_OBJECT *v106; // [rsp+D0h] [rbp-11h] BYREF
  __int64 v107; // [rsp+D8h] [rbp-9h]
  unsigned __int64 v108[7]; // [rsp+E0h] [rbp-1h] BYREF
  unsigned __int8 v113; // [rsp+160h] [rbp+7Fh]

  Flags = a2->Flags;
  v9 = a2;
  if ( (*(_DWORD *)&Flags & 0x10000) != 0 && a6 )
  {
    LODWORD(v10) = -1073741811;
    WdLogSingleEntry2(2, this);
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
    return (unsigned int)v10;
  }
  v95 = 0;
  LODWORD(v10) = 0;
  v113 = 1;
  v11 = (*(_WORD *)&Flags & 0x400) != 0;
  v12 = (*(_DWORD *)&Flags & 0x40000) == 0;
  v13 = this[2];
  if ( v11 )
    v12 = 1;
  v99 = v12;
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(v13) )
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
  v14 = a5;
  v15 = 0;
  while ( 1 )
  {
    v97 = v15;
    if ( v15 >= v9->NumAllocations )
    {
      if ( (int)v10 >= 0 )
      {
        *(_DWORD *)&v9->Flags ^= ((unsigned __int16)*(_DWORD *)&v9->Flags ^ (unsigned __int16)(v113 << 14)) & 0x4000;
        return (unsigned int)v10;
      }
      goto LABEL_22;
    }
    v16 = *((_QWORD *)v14 + 6);
    v17 = v15;
    v101 = 0;
    v18 = &a4[v15];
    v102 = 0;
    v107 = v15;
    v93 = v18;
    v100[0] = (LODWORD(v18->Size) + 4095) & 0xFFFFF000;
    v91 = v99;
    if ( (*(_DWORD *)(v16 + 4) & 0x200F) != 0 )
      v91 = 1;
    v19 = a2;
    if ( !*(_QWORD *)(v16 + 16) && (*(_DWORD *)&a2->Flags & 0x100000) == 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4126;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"pAllocation->m_pAllocation->m_hDriverAllocation != NULL || pKMTCreateAllocation->Flags.NoKmdAccess",
        4126,
        0,
        0,
        0,
        0);
      v19 = a2;
    }
    Value = (struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D)v18->Flags.Value;
    if ( (*(_WORD *)&Value & 0x4000) != 0 )
    {
      v54 = *(_QWORD *)(352LL * ((*((_DWORD *)v14 + 18) >> 12) & 0x3F)
                      + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this[2] + 2) + 3240LL) + 16LL) + 3104LL)
                      + 40);
      if ( !*((_BYTE *)this + 1912) || !v54 )
      {
        WdLogSingleEntry2(2, this);
        WdLogGlobalForLineNumber = 4146;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Driver asking for history buffer, but device history buffer creation is disabled, or adapter doe"
                         "s not have precision data. Device=0x%I64x, PrecisionData=%I64X",
          (__int64)this,
          v54,
          0,
          0,
          0);
        goto LABEL_21;
      }
      v18 = v93;
    }
    BaseAddress = 0;
    if ( a7 )
    {
      v37 = *(_QWORD *)(*((_QWORD *)v14 + 5) + 56LL);
      if ( v37 )
        BaseAddress = *(PVOID *)(v37 + 192);
      v38 = v95;
      if ( *(_BYTE *)&v19->Flags < 0 )
        v38 = 1;
      v95 = v38;
      goto LABEL_63;
    }
    v21 = v19->Flags;
    v98 = 0;
    v92 = 0;
    if ( (*(_DWORD *)&v21 & 0x10000) != 0 )
    {
      if ( (*(_BYTE *)&v21 & 0x20) != 0 )
      {
        BaseAddress = a3[v17].hSection;
        v18->Flags.Value = *(_DWORD *)&Value | 0x10;
        if ( (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 0x100) != 0 )
          goto LABEL_97;
      }
      else if ( (*(_DWORD *)&v21 & 0x20000) != 0 )
      {
        v56 = v17;
        v103 = 0;
        v57 = ObReferenceObjectByHandle(a3[v17].hSection, 0x20000u, MmSectionObjectType, 1, &v103, 0);
        v10 = v57;
        if ( v57 < 0 )
        {
          WdLogSingleEntry2(2, a3[v56].hSection);
          WdLogGlobalForLineNumber = 4185;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to take a reference on hSection:0x%I64x, returning 0x%I64x",
            (__int64)a3[v56].hSection,
            v10,
            0,
            0,
            0);
          goto LABEL_22;
        }
        v58 = v103;
        v18->Flags.Value |= 0x400000u;
        v98 = v58;
        v59 = ProcessSectionAttributes(v58, v18);
        v10 = v59;
        if ( v59 < 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 4197;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to query section attributes. Device=0x%I64x, Status=%I64X",
            (__int64)this,
            v10,
            0,
            0,
            0);
          v83 = v58;
          goto LABEL_165;
        }
        v17 = v107;
        v60 = *(_QWORD *)(*((_QWORD *)v14 + 5) + 56LL);
        *(_DWORD *)(v60 + 12) |= 0x400u;
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v14 + 5) + 56LL) + 192LL) = v58;
        *(_DWORD *)(v60 + 204) = v18->Alignment;
        *(_DWORD *)(v60 + 12) ^= ((unsigned __int16)*(_DWORD *)(v60 + 12)
                                ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&v18->Flags.0 << 9))
                               & 0x800;
      }
    }
    else if ( (*(_BYTE *)&v21 & 0x20) != 0 )
    {
      if ( (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 0x100) != 0 )
      {
        hSection = a3[v17].hSection;
        v18->Flags.Value |= 0x10u;
        BaseAddress = hSection;
LABEL_97:
        *(_DWORD *)(*((_QWORD *)v14 + 6) + 4LL) |= 0x20000000u;
        goto LABEL_34;
      }
      v61 = v100[0];
      Size = v18->Size;
      if ( Size > v100[0] )
      {
        LODWORD(v10) = -1073741811;
        WdLogSingleEntry2(2, Size);
        WdLogGlobalForLineNumber = 4246;
        v84 = L"Overflow rounding allocation size 0x%I64x to next page boundary returning 0x%I64x";
        HandleInformationa = -1073741811;
        Objecta = (PVOID *)v18->Size;
LABEL_162:
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v84, (__int64)Objecta, HandleInformationa, 0, 0, 0);
        goto LABEL_22;
      }
      v18->Size = v100[0];
      v63 = (void *)(*((__int64 (__fastcall **)(_QWORD, _QWORD))a6 + 4))(*((_QWORD *)a6 + 5), v61);
      BaseAddress = v63;
      if ( !v63 )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 4253;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Cannot allocate memory allocation for existing sys mem.",
          4253,
          0,
          0,
          0,
          0);
        goto LABEL_21;
      }
      a3[v17].hSection = v63;
    }
    else if ( (*(_BYTE *)&Value & 0x10) != 0 )
    {
      BaseAddress = a3[v17].hSection;
    }
    else if ( (*(_DWORD *)&Value & 0x400000) != 0 )
    {
      if ( v19->NumAllocations != 1 || (*(_DWORD *)&Value & 0x2000000) == 0 || !a6 || !*((_QWORD *)a6 + 4) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 4272;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"(pKMTCreateAllocation->NumAllocations == 1) && (pDriverAllocations[i].Flags.DoDPrimary) && (pCre"
                         "ateStandardAllocation != NULL) && (pCreateStandardAllocation->pfnAllocateSysMem != NULL)",
          4272,
          0,
          0,
          0,
          0);
      }
      v98 = (PVOID)(*((__int64 (__fastcall **)(_QWORD, _QWORD))a6 + 4))(*((_QWORD *)a6 + 5), v100[0]);
      if ( !v98 )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 4278;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Cannot create section object for DoD primary backing store.",
          4278,
          0,
          0,
          0,
          0);
LABEL_21:
        LODWORD(v10) = -1073741823;
        goto LABEL_22;
      }
      v92 = 1;
    }
LABEL_34:
    if ( !a6 || (*(_DWORD *)a6 & 0x40) == 0 )
      goto LABEL_35;
    if ( !*((_QWORD *)a6 + 41) && !*((_QWORD *)a6 + 42) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 4300;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Section object or SystemMem is not supplied for a cross adapter allocation.",
        4300,
        0,
        0,
        0,
        0);
      goto LABEL_21;
    }
    v64 = *(_QWORD *)(*((_QWORD *)v14 + 5) + 56LL);
    *(_DWORD *)(v64 + 12) ^= ((unsigned __int16)*(_DWORD *)(v64 + 12)
                            ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)a6 << 7))
                           & 0x800;
    v65 = *((_QWORD *)a6 + 42);
    if ( !v65 )
    {
      if ( *((_QWORD *)a6 + 41) )
      {
        v93->Flags.Value |= 0x400000u;
        ObfReferenceObject(*((PVOID *)a6 + 41));
        v66 = (void *)*((_QWORD *)a6 + 41);
        *(_DWORD *)(v64 + 12) |= 0x400u;
        v98 = v66;
        *(_QWORD *)(v64 + 192) = *((_QWORD *)a6 + 41);
        *(_DWORD *)(v64 + 204) = *((_DWORD *)a6 + 98);
      }
LABEL_35:
      v27 = v93;
      goto LABEL_36;
    }
    v27 = v93;
    BaseAddress = (PVOID)*((_QWORD *)a6 + 42);
    v93->Flags.Value |= 0x10u;
    *(_DWORD *)(v64 + 12) |= 0x200u;
    *(_QWORD *)(v64 + 192) = v65;
    *(_DWORD *)(v64 + 204) = *((_DWORD *)a6 + 98);
LABEL_36:
    if ( (a3[v17].Flags.Value & 4) != 0 )
    {
      v27->AllocationPriority = a3[v17].Priority;
    }
    else if ( !v27->AllocationPriority )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 4344;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"KMD should set a non-zero initial priority for allocations.",
        4344,
        0,
        0,
        0,
        0);
      v27 = v93;
    }
    v28 = *((_QWORD *)v14 + 5);
    v29 = 0;
    if ( v28 )
    {
      if ( (v27->Flags.Value & 0x100000) != 0 )
      {
        v29 = 1;
        if ( !*(_QWORD *)(*(_QWORD *)(v28 + 56) + 184LL) )
          break;
      }
    }
LABEL_40:
    v30 = a2;
    if ( (*(_DWORD *)&a2->Flags & 0x10020) == 0x10020 )
    {
      if ( (*((_BYTE *)this + 1917) & 1) != 0 )
      {
        v68 = v93;
      }
      else
      {
        Current = DXGPROCESS::GetCurrent();
        v68 = v93;
        if ( (*((_DWORD *)Current + 102) & 0x10) == 0 )
        {
          LODWORD(v10) = ProcessSysMemAttributes(BaseAddress, v100[0], v93);
          if ( (int)v10 < 0 )
            goto LABEL_22;
          v30 = a2;
        }
      }
      if ( (*(_DWORD *)&v30->Flags & 2) != 0 )
      {
        v69 = *(_QWORD *)(*((_QWORD *)v14 + 5) + 56LL);
        v70 = BaseAddress;
        *(_DWORD *)(v69 + 12) |= 0x200u;
        v71 = *(_DWORD *)(v69 + 12);
        *(_QWORD *)(v69 + 192) = v70;
        *(_DWORD *)(v69 + 204) = v68->Alignment;
        *(_DWORD *)(v69 + 12) = v71
                              ^ ((unsigned __int16)v71
                               ^ (unsigned __int16)((unsigned __int16)*(_DWORD *)&v68->Flags.0 << 9))
                              & 0x800;
      }
    }
    v31 = (PVOID *)BaseAddress;
    if ( BaseAddress )
    {
      if ( (*(_DWORD *)&v30->Flags & 0x80u) != 0 )
      {
        v72 = *((_QWORD *)v14 + 6);
        v95 = 1;
        *(_DWORD *)(v72 + 4) |= 0x8000000u;
        v73 = *((_QWORD *)v14 + 5);
        if ( v73 )
        {
          v74 = *(_QWORD *)(v73 + 56);
          if ( v74 )
            *(_DWORD *)(v74 + 12) |= 0x1000u;
        }
      }
    }
    if ( v29 )
      v32 = *(_QWORD *)(*((_QWORD *)v14 + 5) + 56LL) + 184LL;
    else
      v32 = 0;
    v33 = v98;
    Objectb = v31;
    v18 = v93;
    LODWORD(v10) = (*(__int64 (__fastcall **)(ADAPTER_RENDER *, struct _DXGK_ALLOCATIONINFO *, _QWORD, PVOID, PVOID *, __int64, __int64 *, char *))(*(_QWORD *)(*((_QWORD *)this[2] + 95) + 8LL) + 112LL))(
                     this[99],
                     v93,
                     *((_QWORD *)v14 + 6),
                     v98,
                     Objectb,
                     v32,
                     &v101,
                     &v91);
    if ( !v113 || (v113 = 1, !v91) )
      v113 = 0;
    if ( v92 )
      ObfDereferenceObject(v33);
    if ( (int)v10 < 0 )
      goto LABEL_22;
    v35 = v101;
    if ( !v101 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4448;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pVidMmMultiGlobalAlloc", 4448, 0, 0, 0, 0);
      v35 = v101;
    }
    *(_QWORD *)(*((_QWORD *)v14 + 6) + 8LL) = v35;
    if ( a6 )
    {
      switch ( *((_DWORD *)a6 + 4) )
      {
        case 1:
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          {
            v36 = EventCddStandardAllocationSharedPrimarySurface;
            goto LABEL_141;
          }
          break;
        case 2:
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          {
            v75 = (_DWORD *)*((_QWORD *)a6 + 3);
            McTemplateK0pqqqqq_EtwWriteTransfer(
              (_DWORD)v75,
              (unsigned int)EventCddStandardAllocationShadowSurface,
              v34,
              *((_QWORD *)v14 + 6),
              *(_DWORD *)a6,
              *v75,
              v75[1],
              v75[2],
              v75[3]);
          }
          break;
        case 3:
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
            McTemplateK0pqtqq_EtwWriteTransfer(
              *((_QWORD *)a6 + 3),
              (unsigned int)EventCddStandardAllocationStagingSurface,
              v34,
              *((_QWORD *)v14 + 6),
              *(_DWORD *)a6,
              **((_DWORD **)a6 + 3),
              *(_DWORD *)(*((_QWORD *)a6 + 3) + 4LL),
              *(_DWORD *)(*((_QWORD *)a6 + 3) + 8LL));
          break;
        default:
          if ( *((_DWORD *)a6 + 4) == 4 && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
          {
            v36 = EventCddStandardAllocationGdiSurface;
LABEL_141:
            v76 = (_DWORD *)*((_QWORD *)a6 + 3);
            McTemplateK0pqqqqqqq_EtwWriteTransfer(
              (_DWORD)v76,
              (_DWORD)v36,
              v34,
              *((_QWORD *)v14 + 6),
              *(_DWORD *)a6,
              *v76,
              v76[1],
              v76[2],
              v76[3],
              v76[4],
              v76[5]);
          }
          break;
      }
    }
LABEL_63:
    v39 = this[2];
    v40 = *((_QWORD *)v14 + 6);
    v96 = 0;
    LOBYTE(HandleInformation) = v95 != 0;
    LODWORD(v10) = (*(__int64 (__fastcall **)(_QWORD, ADAPTER_RENDER *, _QWORD, _QWORD, PVOID, POBJECT_HANDLE_INFORMATION, struct DXGALLOCATION *, __int64 *, int *, char *))(*(_QWORD *)(*((_QWORD *)v39 + 95) + 8LL) + 128LL))(
                     *((_QWORD *)v39 + 96),
                     this[99],
                     *(_QWORD *)(v40 + 8),
                     v18->MaximumRenamingListLength,
                     BaseAddress,
                     HandleInformation,
                     v14,
                     &v102,
                     &v96,
                     &v91);
    if ( !v113 || (v113 = 1, !v91) )
      v113 = 0;
    v41 = v96 & 0x3F;
    *((_DWORD *)v14 + 18) = *((_DWORD *)v14 + 18) & 0xFFFC0FFF | (v41 << 12);
    *(_DWORD *)(*((_QWORD *)v14 + 6) + 4LL) = *(_DWORD *)(*((_QWORD *)v14 + 6) + 4LL) & 0xF81FFFFF | (v41 << 21);
    if ( (int)v10 < 0 )
      goto LABEL_22;
    v42 = v102;
    if ( !v102 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4553;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pVidMmMultiAlloc", 4553, 0, 0, 0, 0);
      v42 = v102;
    }
    v43 = v93;
    v44 = (struct VIDMM_MULTI_ALLOC **)((char *)v14 + 24);
    *((_QWORD *)v14 + 3) = v42;
    v45 = *((_QWORD *)v14 + 6);
    v46 = (struct _DXGK_ALLOCATIONINFOFLAGS::$40A47C449A349A58A7C5834230A0E536::$A7A7060B19326E67B1E22F9FC616157D)v43->Flags.Value;
    if ( (*(_WORD *)&v46 & 0x100) != 0 )
    {
      *(_DWORD *)(v45 + 4) |= 8u;
    }
    else
    {
      v47 = *(_DWORD *)(v45 + 4);
      if ( (*(_DWORD *)&v46 & 0x20200) == 0 && (v47 & 0x20) == 0 && (v47 & 0x4000) == 0 )
        goto LABEL_71;
    }
    if ( (v43->Flags.Value & 0x200) != 0 )
      *(_DWORD *)(*((_QWORD *)v14 + 6) + 4LL) |= 0x20u;
    if ( (v43->Flags.Value & 0x20000) != 0 )
      *(_DWORD *)(*((_QWORD *)v14 + 6) + 4LL) |= 0x4000u;
    LODWORD(v10) = VIDMM_EXPORT::VidMmPinAllocation(
                     *((VIDMM_EXPORT **)this[2] + 95),
                     *((struct VIDMM_GLOBAL **)this[2] + 96),
                     *v44,
                     0,
                     0);
    if ( (int)v10 < 0 )
      goto LABEL_22;
    v77 = *((_QWORD *)v14 + 6);
    *((_DWORD *)v14 + 18) |= 0x800u;
    if ( (*(_DWORD *)(v77 + 4) & 0x4000) != 0 )
    {
      VIDMM_EXPORT::VidMmUnpinAllocation(
        *((VIDMM_EXPORT **)this[2] + 95),
        *((struct VIDMM_GLOBAL **)this[2] + 96),
        *v44);
      *((_DWORD *)v14 + 18) &= ~0x800u;
    }
LABEL_71:
    if ( !*((_BYTE *)this + 1919)
      && (*((_DWORD *)this + 116) != 2 || *(int *)(*((_QWORD *)this[2] + 2) + 3116LL) < 2000)
      || !a6
      || *((_DWORD *)a6 + 4) != 2 )
    {
      goto LABEL_73;
    }
    v78 = this[2];
    v79 = this[99];
    v80 = *((_DWORD *)v14 + 18) >> 12;
    v104 = 0;
    v106 = 0;
    VIDMM_EXPORT::VidMmGetDevicePagingQueue(*((VIDMM_EXPORT **)v78 + 95), v79, v80 & 0x3F, &v104, &v106);
    v81 = this[2];
    v105 = 0;
    v108[0] = 0;
    Resident = VIDMM_EXPORT::VidMmMakeResident(
                 *((VIDMM_EXPORT **)v81 + 95),
                 *((struct VIDMM_GLOBAL **)v81 + 96),
                 v104,
                 (struct VIDMM_MULTI_ALLOC **)v14 + 3,
                 1u,
                 3u,
                 &v105,
                 v108);
    v10 = Resident;
    if ( Resident < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 4640;
      v84 = L"Failed to make shadow allocation resident. Status = 0x%I64x";
      HandleInformationa = 0;
      Objecta = (PVOID *)v10;
      goto LABEL_162;
    }
    if ( Resident == 259 )
    {
      VIDMM_EXPORT::VidMmWaitForFences(
        *((VIDMM_EXPORT **)this[2] + 95),
        *((struct VIDMM_GLOBAL **)this[2] + 96),
        &v106,
        &v105,
        Object);
      LODWORD(v10) = 0;
    }
LABEL_73:
    v14 = (struct DXGALLOCATION *)*((_QWORD *)v14 + 8);
    v15 = v97 + 1;
    v9 = a2;
  }
  v48 = 0;
  v49 = 0;
  if ( (*(_DWORD *)&a2->Flags & 0x10000) != 0 && BaseAddress )
  {
    v48 = BaseAddress;
    v49 = a2->pStandardAllocation->ExistingHeapData.Size;
  }
  v50 = *((_QWORD *)this[2] + 95);
  v51 = DXGPROCESS::GetCurrent();
  v52 = *((_DWORD *)v51 + 102) >> 8;
  LOBYTE(v52) = BYTE1(*((_DWORD *)v51 + 102)) & 1;
  v53 = (*(__int64 (__fastcall **)(__int64, PVOID, SIZE_T, __int64))(*(_QWORD *)(v50 + 8) + 1160LL))(
          *(_QWORD *)(*((_QWORD *)v14 + 5) + 56LL) + 184LL,
          v48,
          v49,
          v52);
  v10 = v53;
  if ( v53 >= 0 )
  {
    v29 = 1;
    goto LABEL_40;
  }
  WdLogSingleEntry1(2);
  WdLogGlobalForLineNumber = 4379;
  DxgkLogInternalTriageEvent(
    0,
    0x40000,
    -1,
    (unsigned int)L"Failed to create VIDMM_CROSSADAPTER_ALLOC, returning 0x%I64x",
    v10,
    0,
    0,
    0,
    0);
  if ( v92 )
  {
    v83 = v98;
LABEL_165:
    ObfDereferenceObject(v83);
  }
LABEL_22:
  v22 = 0;
  if ( a2->NumAllocations )
  {
    v23 = a5;
    do
    {
      if ( (*((_DWORD *)v23 + 18) & 0x800) != 0 )
      {
        VIDMM_EXPORT::VidMmUnpinAllocation(
          *((VIDMM_EXPORT **)this[2] + 95),
          *((struct VIDMM_GLOBAL **)this[2] + 96),
          *((struct VIDMM_MULTI_ALLOC **)v23 + 3));
        *((_DWORD *)v23 + 18) &= ~0x800u;
      }
      v24 = *((_QWORD *)v23 + 6);
      v25 = *(struct VIDMM_MULTI_GLOBAL_ALLOC **)(v24 + 8);
      if ( v25
        && !a7
        && (!*((_DWORD *)this + 116) && (*(_DWORD *)(v24 + 4) & 1) != 0 || (*(_DWORD *)(v24 + 4) & 2) != 0) )
      {
        VIDMM_EXPORT::VidMmInvalidateAllocation(
          *((VIDMM_EXPORT **)this[2] + 95),
          *((struct VIDMM_GLOBAL **)this[2] + 96),
          v25);
        *(_DWORD *)(*((_QWORD *)v23 + 6) + 4LL) |= 0x10u;
      }
      v26 = (struct VIDMM_MULTI_ALLOC *)*((_QWORD *)v23 + 3);
      if ( v26 )
      {
        VIDMM_EXPORT::VidMmCloseAllocation(
          *((VIDMM_EXPORT **)this[2] + 95),
          *((struct VIDMM_GLOBAL **)this[2] + 96),
          v26,
          0,
          (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1);
        *((_QWORD *)v23 + 3) = 0;
      }
      else
      {
        DXGDEVICE::TraceCloseParavirtualizedAllocation((DXGDEVICE *)this, v23);
      }
      if ( !a7 )
        DXGDEVICE::DestroyAdapterAllocation((DXGDEVICE *)this, *((struct DXGADAPTERALLOCATION **)v23 + 6));
      v23 = (struct DXGALLOCATION *)*((_QWORD *)v23 + 8);
      ++v22;
    }
    while ( v22 < a2->NumAllocations );
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1403b9a2c  mov     rax, rsp
0x1403b9a2f  mov     [rax+8], rbx
0x1403b9a33  mov     [rax+20h], r9
0x1403b9a37  mov     [rax+18h], r8
0x1403b9a3b  mov     [rax+10h], rdx
0x1403b9a3f  push    rbp
0x1403b9a40  push    rsi
0x1403b9a41  push    rdi
0x1403b9a42  push    r12
0x1403b9a44  push    r13
0x1403b9a46  push    r14
0x1403b9a48  push    r15
0x1403b9a4a  lea     rbp, [rax-3Fh]
0x1403b9a4e  sub     rsp, 0E0h
0x1403b9a55  mov     r13, [rbp+37h+arg_28]
0x1403b9a59  mov     r14, rcx
0x1403b9a5c  mov     ecx, [rdx+38h]
0x1403b9a5f  xor     ebx, ebx
0x1403b9a61  mov     rdi, rdx
0x1403b9a64  bt      ecx, 10h
0x1403b9a68  jb      loc_1403BA081
0x1403b9a6e  mov     eax, ecx
0x1403b9a70  mov     [rbp+37h+var_98], ebx
0x1403b9a73  shr     eax, 12h
0x1403b9a76  mov     esi, ebx
0x1403b9a78  not     al
0x1403b9a7a  mov     ebx, 1
0x1403b9a7f  and     al, bl
0x1403b9a81  mov     byte ptr [rbp+37h+arg_38], bl
0x1403b9a84  bt      ecx, 0Ah
0x1403b9a88  movzx   eax, al
0x1403b9a8b  mov     rcx, [r14+10h]; this
0x1403b9a8f  cmovb   eax, ebx
0x1403b9a92  mov     [rbp+37h+var_80], eax
0x1403b9a95  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x1403b9a9a  or      r12d, 0FFFFFFFFh
0x1403b9a9e  test    al, al
0x1403b9aa0  jz      loc_1403BA0E7
0x1403b9aa6  mov     r15, [rbp+37h+arg_20]
0x1403b9aaa  xor     eax, eax
0x1403b9aac  mov     [rbp+37h+var_90], eax
0x1403b9aaf  cmp     eax, [rdi+2Ch]
0x1403b9ab2  jnb     loc_1403BA05D
0x1403b9ab8  mov     rcx, [r15+30h]
0x1403b9abc  mov     esi, eax
0x1403b9abe  imul    rdi, rsi, 58h ; 'X'
0x1403b9ac2  mov     [rbp+37h+var_70], 0
0x1403b9aca  add     rdi, [rbp+37h+arg_18]
0x1403b9ace  mov     [rbp+37h+var_68], 0
0x1403b9ad6  mov     [rbp+37h+var_40], rsi
0x1403b9ada  mov     [rbp+37h+var_A8], rdi
0x1403b9ade  mov     eax, [rdi+10h]
0x1403b9ae1  add     eax, 0FFFh
0x1403b9ae6  and     eax, 0FFFFF000h
0x1403b9aeb  mov     [rbp+37h+var_78], eax
0x1403b9aee  mov     eax, [rbp+37h+var_80]
0x1403b9af1  mov     [rbp+37h+var_B0], al
0x1403b9af4  test    dword ptr [rcx+4], 200Fh
0x1403b9afb  jz      short loc_1403B9B00
0x1403b9afd  mov     [rbp+37h+var_B0], bl
0x1403b9b00  cmp     qword ptr [rcx+10h], 0
0x1403b9b05  mov     r9, [rbp+37h+arg_8]
0x1403b9b09  jz      loc_1403BA134
0x1403b9b0f  mov     r8d, [rdi+40h]
0x1403b9b13  bt      r8d, 0Eh
0x1403b9b18  jb      loc_1403BA195
0x1403b9b1e  cmp     [rbp+37h+arg_30], 0
0x1403b9b22  mov     [rbp+37h+BaseAddress], 0
0x1403b9b2a  jnz     loc_1403B9E3C
0x1403b9b30  mov     ecx, [r9+38h]
0x1403b9b34  mov     eax, ecx
0x1403b9b36  and     eax, 20h
0x1403b9b39  mov     [rbp+37h+var_88], 0
0x1403b9b41  mov     [rbp+37h+var_AF], 0
0x1403b9b45  bt      ecx, 10h
0x1403b9b49  jb      loc_1403BA1E6
0x1403b9b4f  test    eax, eax
0x1403b9b51  jnz     loc_1403BA30F
0x1403b9b57  test    r8b, 10h
0x1403b9b5b  jnz     loc_1403BA36E
0x1403b9b61  bt      r8d, 16h
0x1403b9b66  jnb     loc_1403B9D0D
0x1403b9b6c  cmp     [r9+2Ch], ebx
0x1403b9b70  jz      loc_1403BA388
0x1403b9b76  mov     ecx, ebx
0x1403b9b78  call    cs:__imp_WdLogSingleEntry0
0x1403b9b7f  nop     dword ptr [rax+rax+00h]
0x1403b9b84  mov     [rsp+110h+var_D0], 0
0x1403b9b8d  lea     r9, aPkmtcreateallo; "(pKMTCreateAllocation->NumAllocations ="...
0x1403b9b94  mov     [rsp+110h+var_D8], 0
0x1403b9b9d  mov     eax, 10B0h
0x1403b9ba2  mov     [rsp+110h+var_E0], 0
0x1403b9bab  mov     r8d, r12d
0x1403b9bae  mov     [rsp+110h+HandleInformation], 0
0x1403b9bb7  mov     edx, 40002h
0x1403b9bbc  xor     ecx, ecx
0x1403b9bbe  mov     [rsp+110h+Object], rax
0x1403b9bc3  mov     cs:WdLogGlobalForLineNumber, eax
0x1403b9bc9  call    DxgkLogInternalTriageEvent
0x1403b9bce  mov     rax, [r13+20h]
0x1403b9bd2  mov     edx, [rbp+37h+var_78]
0x1403b9bd5  mov     rcx, [r13+28h]
0x1403b9bd9  call    _guard_dispatch_icall
0x1403b9bde  mov     [rbp+37h+var_88], rax
0x1403b9be2  test    rax, rax
0x1403b9be5  jnz     loc_1403BA3AC
0x1403b9beb  lea     ecx, [rax+2]
0x1403b9bee  call    cs:__imp_WdLogSingleEntry0
0x1403b9bf5  nop     dword ptr [rax+rax+00h]
0x1403b9bfa  mov     [rsp+110h+var_D0], 0
0x1403b9c03  lea     r9, aCannotCreateSe; "Cannot create section object for DoD pr"...
0x1403b9c0a  mov     [rsp+110h+var_D8], 0
0x1403b9c13  mov     eax, 10B6h
0x1403b9c18  mov     [rsp+110h+var_E0], 0
0x1403b9c21  mov     [rsp+110h+HandleInformation], 0
0x1403b9c2a  mov     [rsp+110h+Object], rax
0x1403b9c2f  mov     cs:WdLogGlobalForLineNumber, eax
0x1403b9c35  mov     r8d, r12d
0x1403b9c38  mov     edx, 40000h
0x1403b9c3d  xor     ecx, ecx
0x1403b9c3f  call    DxgkLogInternalTriageEvent
0x1403b9c44  mov     esi, 0C0000001h
0x1403b9c49  mov     r13, [rbp+37h+arg_8]
0x1403b9c4d  xor     edi, edi
0x1403b9c4f  cmp     [r13+2Ch], edi
0x1403b9c53  jbe     loc_1403BABD6
0x1403b9c59  mov     r15, [rbp+37h+arg_20]
0x1403b9c5d  mov     r12b, [rbp+37h+arg_30]
0x1403b9c61  test    dword ptr [r15+48h], 800h
0x1403b9c69  jz      short loc_1403B9C8C
0x1403b9c6b  mov     rcx, [r14+10h]
0x1403b9c6f  mov     r8, [r15+18h]; struct VIDMM_MULTI_ALLOC *
0x1403b9c73  mov     rdx, [rcx+300h]; struct VIDMM_GLOBAL *
0x1403b9c7a  mov     rcx, [rcx+2F8h]; this
0x1403b9c81  call    ?VidMmUnpinAllocation@VIDMM_EXPORT@@QEAAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_MULTI_ALLOC@@@Z; VIDMM_EXPORT::VidMmUnpinAllocation(VIDMM_GLOBAL *,VIDMM_MULTI_ALLOC *)
0x1403b9c86  btr     dword ptr [r15+48h], 0Bh
0x1403b9c8c  mov     rcx, [r15+30h]
0x1403b9c90  mov     r8, [rcx+8]; struct VIDMM_MULTI_GLOBAL_ALLOC *
0x1403b9c94  test    r8, r8
0x1403b9c97  jz      short loc_1403B9CD5
0x1403b9c99  test    r12b, r12b
0x1403b9c9c  jnz     short loc_1403B9CD5
0x1403b9c9e  cmp     dword ptr [r14+1D0h], 0
0x1403b9ca6  jnz     short loc_1403B9CAF
0x1403b9ca8  mov     eax, [rcx+4]
0x1403b9cab  test    bl, al
0x1403b9cad  jnz     short loc_1403B9CB6
0x1403b9caf  mov     eax, [rcx+4]
0x1403b9cb2  test    al, 2
0x1403b9cb4  jz      short loc_1403B9CD5
0x1403b9cb6  mov     rcx, [r14+10h]
0x1403b9cba  mov     rdx, [rcx+300h]; struct VIDMM_GLOBAL *
0x1403b9cc1  mov     rcx, [rcx+2F8h]; this
0x1403b9cc8  call    ?VidMmInvalidateAllocation@VIDMM_EXPORT@@QEAAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_MULTI_GLOBAL_ALLOC@@@Z; VIDMM_EXPORT::VidMmInvalidateAllocation(VIDMM_GLOBAL *,VIDMM_MULTI_GLOBAL_ALLOC *)
0x1403b9ccd  mov     rax, [r15+30h]
0x1403b9cd1  or      dword ptr [rax+4], 10h
0x1403b9cd5  mov     r8, [r15+18h]; struct VIDMM_MULTI_ALLOC *
0x1403b9cd9  test    r8, r8
0x1403b9cdc  jz      loc_1403BABAA
0x1403b9ce2  mov     rcx, [r14+10h]
0x1403b9ce6  xor     r9d, r9d; struct VIDMM_LOCAL_ALLOC **
0x1403b9ce9  mov     dword ptr [rsp+110h+Object], ebx; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1403b9ced  mov     rdx, [rcx+300h]; struct VIDMM_GLOBAL *
0x1403b9cf4  mov     rcx, [rcx+2F8h]; this
0x1403b9cfb  call    ?VidMmCloseAllocation@VIDMM_EXPORT@@QEAAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_MULTI_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@U_D3DDDICB_DESTROYALLOCATION2FLAGS@@@Z; VIDMM_EXPORT::VidMmCloseAllocation(VIDMM_GLOBAL *,VIDMM_MULTI_ALLOC *,VIDMM_LOCAL_ALLOC * *,_D3DDDICB_DESTROYALLOCATION2FLAGS)
0x1403b9d00  mov     qword ptr [r15+18h], 0
0x1403b9d08  jmp     loc_1403BABB5
0x1403b9d0d  test    r13, r13
0x1403b9d10  jnz     loc_1403BA3B4
0x1403b9d16  mov     rdx, [rbp+37h+var_A8]
0x1403b9d1a  mov     r8, [rbp+37h+arg_10]
0x1403b9d1e  lea     rcx, [rsi+rsi*2]
0x1403b9d22  shl     rcx, 5
0x1403b9d26  mov     eax, [rcx+r8+20h]
0x1403b9d2b  test    al, 4
0x1403b9d2d  jnz     loc_1403BA4D1
0x1403b9d33  cmp     dword ptr [rdx+50h], 0
0x1403b9d37  jz      loc_1403BA4DE
0x1403b9d3d  mov     rcx, [r15+28h]
0x1403b9d41  xor     r12b, r12b
0x1403b9d44  test    rcx, rcx
0x1403b9d47  jnz     loc_1403B9F91
0x1403b9d4d  mov     rsi, [rbp+37h+arg_8]
0x1403b9d51  mov     ecx, 10020h
0x1403b9d56  mov     eax, [rsi+38h]
0x1403b9d59  and     eax, ecx
0x1403b9d5b  cmp     eax, ecx
0x1403b9d5d  jz      loc_1403BA542
0x1403b9d63  mov     rdi, [rbp+37h+BaseAddress]
0x1403b9d67  test    rdi, rdi
0x1403b9d6a  jnz     loc_1403BA5CA
0x1403b9d70  mov     rax, [r14+10h]
0x1403b9d74  mov     rdx, [rax+2F8h]
0x1403b9d7b  test    r12b, r12b
0x1403b9d7e  jnz     loc_1403BA605
0x1403b9d84  xor     ecx, ecx
0x1403b9d86  mov     rax, [rdx+8]
0x1403b9d8a  lea     rdx, [rbp+37h+var_B0]
0x1403b9d8e  mov     r12, [rbp+37h+var_88]
0x1403b9d92  mov     r8, [r15+30h]
0x1403b9d96  mov     r9, r12
0x1403b9d99  mov     [rsp+110h+var_D8], rdx
0x1403b9d9e  lea     rdx, [rbp+37h+var_70]
0x1403b9da2  mov     rax, [rax+70h]
0x1403b9da6  mov     [rsp+110h+var_E0], rdx
0x1403b9dab  mov     [rsp+110h+HandleInformation], rcx
0x1403b9db0  mov     rcx, [r14+318h]
0x1403b9db7  mov     [rsp+110h+Object], rdi
0x1403b9dbc  mov     rdi, [rbp+37h+var_A8]
0x1403b9dc0  mov     rdx, rdi
0x1403b9dc3  call    _guard_dispatch_icall
0x1403b9dc8  cmp     byte ptr [rbp+37h+arg_38], 0
0x1403b9dcc  mov     esi, eax
0x1403b9dce  jnz     loc_1403BA619
0x1403b9dd4  mov     byte ptr [rbp+37h+arg_38], 0
0x1403b9dd8  cmp     [rbp+37h+var_AF], 0
0x1403b9ddc  jnz     loc_1403BA62B
0x1403b9de2  test    esi, esi
0x1403b9de4  js      loc_1403B9C49
0x1403b9dea  mov     rcx, [rbp+37h+var_70]
0x1403b9dee  test    rcx, rcx
0x1403b9df1  jz      loc_1403BA63F
0x1403b9df7  or      r12d, 0FFFFFFFFh
0x1403b9dfb  mov     rax, [r15+30h]
0x1403b9dff  mov     [rax+8], rcx
0x1403b9e03  test    r13, r13
0x1403b9e06  jz      short loc_1403B9E62
0x1403b9e08  mov     ecx, [r13+10h]
0x1403b9e0c  sub     ecx, ebx
0x1403b9e0e  jz      loc_1403BA71F
0x1403b9e14  sub     ecx, ebx
0x1403b9e16  jz      loc_1403BA6D7
0x1403b9e1c  sub     ecx, ebx
0x1403b9e1e  jz      loc_1403BA696
0x1403b9e24  cmp     ecx, ebx
0x1403b9e26  jnz     short loc_1403B9E62
0x1403b9e28  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, bl
0x1403b9e2e  jz      short loc_1403B9E62
0x1403b9e30  lea     rdx, EventCddStandardAllocationGdiSurface
0x1403b9e37  jmp     loc_1403BA732
0x1403b9e3c  mov     rax, [r15+28h]
0x1403b9e40  mov     rcx, [rax+38h]
0x1403b9e44  test    rcx, rcx
0x1403b9e47  jz      short loc_1403B9E54
0x1403b9e49  mov     rax, [rcx+0C0h]
0x1403b9e50  mov     [rbp+37h+BaseAddress], rax
0x1403b9e54  mov     eax, [rbp+37h+var_98]
0x1403b9e57  test    byte ptr [r9+38h], 80h
0x1403b9e5c  cmovnz  eax, ebx
0x1403b9e5f  mov     [rbp+37h+var_98], eax
0x1403b9e62  mov     rcx, [r14+10h]
0x1403b9e66  mov     r8, [r15+30h]
0x1403b9e6a  cmp     [rbp+37h+var_98], 0
0x1403b9e6e  mov     [rbp+37h+var_94], 0
0x1403b9e75  mov     rax, [rcx+2F8h]
0x1403b9e7c  setnz   r9b
0x1403b9e80  mov     r8, [r8+8]
0x1403b9e84  mov     rcx, [rcx+300h]
0x1403b9e8b  mov     rdx, [rax+8]
0x1403b9e8f  mov     rax, [rdx+80h]
0x1403b9e96  lea     rdx, [rbp+37h+var_B0]
0x1403b9e9a  mov     qword ptr [rsp+110h+var_C8], rdx
0x1403b9e9f  lea     rdx, [rbp+37h+var_94]
0x1403b9ea3  mov     [rsp+110h+var_D0], rdx
0x1403b9ea8  lea     rdx, [rbp+37h+var_68]
0x1403b9eac  mov     [rsp+110h+var_D8], rdx
0x1403b9eb1  mov     rdx, [r14+318h]
0x1403b9eb8  mov     [rsp+110h+var_E0], r15
0x1403b9ebd  mov     byte ptr [rsp+110h+HandleInformation], r9b
0x1403b9ec2  mov     r9, [rbp+37h+BaseAddress]
0x1403b9ec6  mov     [rsp+110h+Object], r9
0x1403b9ecb  mov     r9d, [rdi+34h]
0x1403b9ecf  call    _guard_dispatch_icall
0x1403b9ed4  cmp     byte ptr [rbp+37h+arg_38], 0
0x1403b9ed8  mov     esi, eax
0x1403b9eda  jnz     loc_1403BA775
0x1403b9ee0  mov     byte ptr [rbp+37h+arg_38], 0
0x1403b9ee4  mov     eax, [r15+48h]
0x1403b9ee8  mov     edx, [rbp+37h+var_94]
0x1403b9eeb  and     eax, 0FFFC0FFFh
0x1403b9ef0  and     edx, 3Fh
0x1403b9ef3  mov     ecx, edx
0x1403b9ef5  shl     edx, 15h
0x1403b9ef8  shl     ecx, 0Ch
0x1403b9efb  or      ecx, eax
0x1403b9efd  mov     [r15+48h], ecx
0x1403b9f01  mov     rcx, [r15+30h]
0x1403b9f05  mov     eax, [rcx+4]
0x1403b9f08  and     eax, 0F81FFFFFh
0x1403b9f0d  or      edx, eax
0x1403b9f0f  mov     [rcx+4], edx
0x1403b9f12  test    esi, esi
0x1403b9f14  js      loc_1403B9C49
0x1403b9f1a  mov     rax, [rbp+37h+var_68]
0x1403b9f1e  test    rax, rax
0x1403b9f21  jz      loc_1403BA787
0x1403b9f27  mov     r8, [rbp+37h+var_A8]
0x1403b9f2b  lea     rdi, [r15+18h]
0x1403b9f2f  mov     [rdi], rax
0x1403b9f32  mov     rax, [r15+30h]
  ... truncated ...
```
