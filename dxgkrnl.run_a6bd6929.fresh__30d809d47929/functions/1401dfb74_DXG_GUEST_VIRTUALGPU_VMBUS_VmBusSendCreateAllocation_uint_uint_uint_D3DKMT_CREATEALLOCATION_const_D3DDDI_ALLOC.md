# DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateAllocation(uint,uint,uint,_D3DKMT_CREATEALLOCATION const *,_D3DDDI_ALLOCATIONINFO2 *,void * *,void const *,void const *,uchar,uchar,uchar * *)

- ea: `0x1401dfb74`
- end: `0x1401e0d92`
- name: `?VmBusSendCreateAllocation@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJIIIPEBU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@PEAPEAXPEBX3EEPEAPEAE@Z`
- size: `4638`
- prototype: `__int64 __fastcall(DXG_GUEST_VIRTUALGPU_VMBUS *__hidden this, unsigned int, unsigned int, unsigned int, const struct _D3DKMT_CREATEALLOCATION *, struct _D3DDDI_ALLOCATIONINFO2 *, void **, const void *, const void *Src, char, char, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140377080`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x14001b9c0`
- `0x140037ac0`
- `0x140062800`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x140196b24`
- `0x1401dfb74`
- `0x140260c0c`
- `0x140284fd0`
- `0x140285030`
- `0x1402994b4`
- `0x14035f600`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401e03cb`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401e06a9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401e03cb`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401e06a9`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e0485`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e06cf`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e0485`
- `ntoskrnl!ObfDereferenceObject` at `0x1401e06cf`
- `ntoskrnl!IoAllocateMdl` at `0x1401e0515`
- `ntoskrnl!IoAllocateMdl` at `0x1401e0515`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401e05b5`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401e05b5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401e0334`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401e0334`
- `ntoskrnl!MmSectionObjectType` at `0x1401e0324`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1401e0242`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1401e0242`
- `watchdog!WdLogSingleEntry2` at `0x1401e0363`
- `watchdog!WdLogSingleEntry2` at `0x1401e0d1e`
- `watchdog!WdLogSingleEntry2` at `0x1401e0363`
- `watchdog!WdLogSingleEntry2` at `0x1401e0d1e`
- `watchdog!WdLogSingleEntry0` at `0x1401dfe07`
- `watchdog!WdLogSingleEntry0` at `0x1401e0065`
- `watchdog!WdLogSingleEntry0` at `0x1401e025f`
- `watchdog!WdLogSingleEntry0` at `0x1401e08ce`
- `watchdog!WdLogSingleEntry0` at `0x1401e0ab8`
- `watchdog!WdLogSingleEntry0` at `0x1401dfe07`
- `watchdog!WdLogSingleEntry0` at `0x1401e0065`
- `watchdog!WdLogSingleEntry0` at `0x1401e025f`
- `watchdog!WdLogSingleEntry0` at `0x1401e08ce`
- `watchdog!WdLogSingleEntry0` at `0x1401e0ab8`
- `watchdog!WdLogSingleEntry5` at `0x1401dfff4`
- `watchdog!WdLogSingleEntry5` at `0x1401e0c1e`
- `watchdog!WdLogSingleEntry5` at `0x1401dfff4`
- `watchdog!WdLogSingleEntry5` at `0x1401e0c1e`
- `watchdog!WdLogSingleEntry1` at `0x1401e0437`
- `watchdog!WdLogSingleEntry1` at `0x1401e053e`
- `watchdog!WdLogSingleEntry1` at `0x1401e05e3`
- `watchdog!WdLogSingleEntry1` at `0x1401e0703`
- `watchdog!WdLogSingleEntry1` at `0x1401e081e`
- `watchdog!WdLogSingleEntry1` at `0x1401e09e2`
- `watchdog!WdLogSingleEntry1` at `0x1401e0b82`
- `watchdog!WdLogSingleEntry1` at `0x1401e0cbd`
- `watchdog!WdLogSingleEntry1` at `0x1401e0437`
- `watchdog!WdLogSingleEntry1` at `0x1401e053e`
- `watchdog!WdLogSingleEntry1` at `0x1401e05e3`
- `watchdog!WdLogSingleEntry1` at `0x1401e0703`
- `watchdog!WdLogSingleEntry1` at `0x1401e081e`
- `watchdog!WdLogSingleEntry1` at `0x1401e09e2`
- `watchdog!WdLogSingleEntry1` at `0x1401e0b82`
- `watchdog!WdLogSingleEntry1` at `0x1401e0cbd`

## string_xrefs

- `0x1401e0901`: `Failed to allocate DXGKVMB_COMMAND_SETEXISTINGSYSMEMPAGES`
- `0x1401e0cec`: `VmBusSendCreateAllocation failed: 0x%I64x`
- `0x1401e0bb1`: `VmBusSendMakeResident failed: 0x%I64x`
- `0x1401dfe37`: `Open cross adapter allocation is not supported`
- `0x1401e0aeb`: `Failed to allocate storage for input buffer to MakeResident`
- `0x1401e0a11`: `DXGKVMB_COMMAND_SETEXISTINGSYSMEMPAGES failed: 0x%I64x`

## pseudocode

```c
__int64 __fastcall DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateAllocation(
        DXG_GUEST_VIRTUALGPU_VMBUS *this,
        int a2,
        int a3,
        int a4,
        const struct _D3DKMT_CREATEALLOCATION *a5,
        struct _D3DDDI_ALLOCATIONINFO2 *a6,
        void **a7,
        void *a8,
        void *Src,
        char a10,
        char a11,
        unsigned __int8 **a12)
{
  struct DXGGLOBAL *Global; // r10
  UINT PrivateRuntimeDataSize; // edx
  unsigned int v15; // r8d
  unsigned int v16; // esi
  unsigned int v17; // ecx
  __int64 NumAllocations; // rdx
  unsigned int v19; // eax
  unsigned int v20; // ecx
  int v21; // r15d
  __int64 v22; // rdi
  __int64 v24; // r14
  void *v25; // rcx
  D3DKMT_CREATEALLOCATIONFLAGS *p_Flags; // r8
  D3DKMT_CREATEALLOCATIONFLAGS Flags; // ecx
  size_t v28; // rdx
  unsigned int v29; // ecx
  D3DKMT_CREATEALLOCATIONFLAGS v30; // eax
  unsigned int v31; // ecx
  unsigned int v32; // r15d
  UINT v33; // esi
  unsigned int v34; // eax
  UINT *v35; // r14
  UINT v36; // r12d
  struct _D3DDDI_ALLOCATIONINFO2 *v37; // rsi
  UINT v38; // r15d
  unsigned int v39; // r13d
  UINT *v40; // rcx
  D3DKMT_CREATEALLOCATIONFLAGS v41; // eax
  struct DXGGLOBAL *v42; // rax
  void *pPrivateDriverData; // rdx
  bool v44; // si
  __int64 v45; // rcx
  char v46; // al
  __int64 v47; // rdi
  _DWORD *v48; // r15
  _DWORD *v49; // rdx
  UINT *v50; // r8
  char *v51; // r12
  struct _D3DDDI_ALLOCATIONINFO2 *v52; // r13
  UINT i; // edi
  __int64 v54; // rcx
  __int64 v55; // r12
  _DWORD *v56; // rsi
  SIZE_T v57; // rdi
  PMDL PagesForMdl; // rax
  struct _MDL *v59; // rdi
  struct DXGGLOBAL *v60; // rax
  HANDLE *p_hSection; // r12
  NTSTATUS v62; // eax
  __int64 v63; // rcx
  PVOID v64; // r13
  __int64 v65; // rdi
  __int64 CurrentProcess; // rsi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  char v68; // si
  struct DXGGLOBAL *v69; // rax
  struct _MDL *Mdl; // rdi
  PVOID v71; // rsi
  __int64 v72; // rdi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v73; // rax
  DXG_VMBUS_CHANNEL_BASE *v74; // r13
  struct DXGKVMB_COMMAND_BASE *v75; // r8
  int v76; // edx
  int v77; // ecx
  int v78; // r12d
  int v79; // eax
  unsigned int v80; // esi
  DXG_VMBUS_CHANNEL_BASE *v81; // rdi
  unsigned int v82; // edx
  __int64 *j; // r13
  struct DXGKVMB_COMMAND_BASE *v84; // rcx
  _QWORD *v85; // r8
  unsigned int v86; // r12d
  int v87; // eax
  unsigned int k; // ecx
  __int64 v89; // rax
  int v90; // eax
  __int64 v91; // rcx
  int v92; // eax
  __int64 v93; // rdi
  struct _MDL *CacheTypea; // [rsp+20h] [rbp-5E8h]
  struct _MDL *CacheType; // [rsp+20h] [rbp-5E8h]
  char v96; // [rsp+60h] [rbp-5A8h]
  bool v97; // [rsp+60h] [rbp-5A8h]
  int v98; // [rsp+64h] [rbp-5A4h]
  UINT v99; // [rsp+64h] [rbp-5A4h]
  unsigned int v100[2]; // [rsp+70h] [rbp-598h] BYREF
  PVOID VirtualAddress; // [rsp+78h] [rbp-590h] BYREF
  struct DXG_VMBUS_CHANNEL_BASE *v102; // [rsp+80h] [rbp-588h]
  struct _D3DDDI_ALLOCATIONINFO2 *v103; // [rsp+88h] [rbp-580h]
  _DWORD *v104; // [rsp+90h] [rbp-578h]
  void *v105; // [rsp+98h] [rbp-570h]
  _DWORD *v106; // [rsp+A0h] [rbp-568h] BYREF
  UINT v107; // [rsp+A8h] [rbp-560h]
  D3DKMT_CREATEALLOCATIONFLAGS *v108; // [rsp+B0h] [rbp-558h]
  UINT *p_NumAllocations; // [rsp+B8h] [rbp-550h]
  __int64 v110; // [rsp+C0h] [rbp-548h]
  void *v111; // [rsp+C8h] [rbp-540h]
  ULONG Length[2]; // [rsp+D0h] [rbp-538h]
  void **v113; // [rsp+D8h] [rbp-530h]
  char *v114; // [rsp+E0h] [rbp-528h]
  struct _MDL *v115; // [rsp+E8h] [rbp-520h] BYREF
  PVOID Object; // [rsp+F0h] [rbp-518h] BYREF
  PVOID v117; // [rsp+F8h] [rbp-510h]
  unsigned __int8 **v118; // [rsp+100h] [rbp-508h]
  DXG_GUEST_VIRTUALGPU_VMBUS *v119; // [rsp+108h] [rbp-500h]
  UINT *v120; // [rsp+110h] [rbp-4F8h]
  union _D3DDDI_ALLOCATIONINFO2::$332422D50CC5DC1C38BC4DCC57A4E2CB *v121; // [rsp+118h] [rbp-4F0h]
  _DWORD *v122; // [rsp+120h] [rbp-4E8h]
  char *v123; // [rsp+128h] [rbp-4E0h]
  struct DXGKVMB_COMMAND_BASE *v124[2]; // [rsp+130h] [rbp-4D8h] BYREF
  unsigned int v125; // [rsp+140h] [rbp-4C8h]
  struct DXGKVMB_COMMAND_BASE *v126[2]; // [rsp+250h] [rbp-3B8h] BYREF
  unsigned int v127; // [rsp+260h] [rbp-3A8h]
  __int128 v128; // [rsp+370h] [rbp-298h] BYREF
  int v129; // [rsp+380h] [rbp-288h]
  __int128 v130; // [rsp+490h] [rbp-178h] BYREF
  int v131; // [rsp+4A0h] [rbp-168h]
  char v132[16]; // [rsp+5B0h] [rbp-58h] BYREF
  __int64 v133; // [rsp+5C0h] [rbp-48h]

  v102 = this;
  v119 = this;
  v103 = a6;
  v113 = a7;
  v111 = a8;
  v118 = a12;
  *a12 = 0;
  if ( !a10 || (v96 = 1, (*(_DWORD *)&a5->Flags & 0x10000) != 0) )
    v96 = 0;
  Global = DXGGLOBAL::GetGlobal();
  PrivateRuntimeDataSize = a5->PrivateRuntimeDataSize;
  v15 = PrivateRuntimeDataSize + a5->PrivateDriverDataSize;
  if ( v15 < PrivateRuntimeDataSize )
    return 2147483653LL;
  v16 = 0;
  v17 = 0;
  p_NumAllocations = &a5->NumAllocations;
  NumAllocations = a5->NumAllocations;
  while ( v17 < (unsigned int)NumAllocations )
  {
    if ( v16 + a6[v17].PrivateDriverDataSize < v16 )
      return 2147483653LL;
    v16 += a6[v17++].PrivateDriverDataSize;
  }
  v19 = v15 + v16;
  if ( v15 + v16 < v15 )
    return 2147483653LL;
  v20 = v19 + 64;
  if ( v19 + 64 < v19 )
    return 2147483653LL;
  v120 = &a5->NumAllocations;
  if ( (unsigned int)(NumAllocations - 1) > 0x71B || v16 > 0x20000 )
  {
    WdLogSingleEntry2(2, v16);
    WdLogGlobalForLineNumber = 10112;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid VM bus message size: 0x%I64x or invalid number of allocations: 0x%I64x",
      v16,
      a5->NumAllocations,
      0,
      0,
      0);
    return 2147483653LL;
  }
  v21 = 12 * NumAllocations;
  if ( (unsigned __int64)(12 * NumAllocations) > 0xFFFFFFFF )
    return 2147483653LL;
  LODWORD(VirtualAddress) = v21 + v20;
  if ( v21 + v20 < v20 )
    return 2147483653LL;
  v100[0] = *((_DWORD *)Global + 438);
  v98 = 0;
  v128 = 0;
  v129 = 0;
  DXGVMBUSMESSAGE::InitializeMessage((DXGVMBUSMESSAGE *)&v128, v102, v21 + v20, 0, 0, 0);
  v22 = v128;
  if ( !(_QWORD)v128 )
  {
    DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v128);
    return 3221225495LL;
  }
  *(_QWORD *)v128 = 0;
  *(_DWORD *)(v22 + 8) = 0;
  *(_BYTE *)(v22 + 12) = 0;
  *(_DWORD *)(v22 + 12) &= 0x1FFu;
  *(_QWORD *)(v22 + 16) = 4;
  v110 = (v16 + 72 * a5->NumAllocations + 23) & 0xFFFFFFF8;
  v105 = (void *)operator new[]((unsigned int)v110, 1265072196, 64);
  if ( !v105 )
  {
    LODWORD(v24) = -1073741801;
    v25 = 0;
    goto LABEL_133;
  }
  *(_DWORD *)(v22 + 24) = a3;
  *(_DWORD *)(v22 + 8) = a2;
  p_Flags = &a5->Flags;
  v108 = &a5->Flags;
  Flags = a5->Flags;
  *(D3DKMT_CREATEALLOCATIONFLAGS *)(v22 + 44) = Flags;
  *(_DWORD *)(v22 + 28) = a4;
  *(_QWORD *)(v22 + 48) = a5->hPrivateRuntimeResourceHandle;
  *(_DWORD *)(v22 + 40) = a5->NumAllocations;
  v28 = a5->PrivateRuntimeDataSize;
  *(_DWORD *)(v22 + 32) = v28;
  *(_DWORD *)(v22 + 36) = a5->PrivateDriverDataSize;
  v29 = *(_DWORD *)&Flags & 0xFFFEFFFF;
  *(_DWORD *)(v22 + 44) = v29;
  if ( (*(_DWORD *)&a5->Flags & 0x20020) != 0 )
  {
    v29 &= 0xFFFFE7FF;
    *(_DWORD *)(v22 + 44) = v29;
  }
  else if ( (v29 & 0x1000) != 0 )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 10170;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Open cross adapter allocation is not supported",
      10170,
      0,
      0,
      0,
      0);
    LODWORD(v24) = -1073741811;
LABEL_22:
    v25 = v105;
    goto LABEL_133;
  }
  v30 = *p_Flags;
  if ( (*(_DWORD *)p_Flags & 8) != 0 )
  {
    LOBYTE(v98) = 1;
    v31 = v29 & 0xFFFFFFF7;
LABEL_30:
    *(_DWORD *)(v22 + 44) = v31 | 0x20;
    goto LABEL_31;
  }
  if ( (*(_BYTE *)&v30 & 0x20) != 0 )
  {
    LOBYTE(v98) = 2;
  }
  else if ( (*(_DWORD *)&v30 & 0x20000) != 0 )
  {
    LOBYTE(v98) = 2;
    v31 = v29 & 0xFFFDFFFF;
    goto LABEL_30;
  }
LABEL_31:
  v32 = v21 + 64;
  v33 = v32 + a5->PrivateRuntimeDataSize;
  if ( (_DWORD)v28 && Src )
    memmove((void *)(v22 + v32), Src, v28);
  v34 = *(_DWORD *)(v22 + 36);
  if ( v34 && v111 )
    memmove((void *)(v22 + v33), v111, v34);
  v35 = (UINT *)(v22 + 64);
  v36 = v33 + *(_DWORD *)(v22 + 36);
  v37 = v103;
  v38 = 0;
  v39 = (unsigned int)VirtualAddress;
  while ( 1 )
  {
    v40 = p_NumAllocations;
    if ( v38 >= *p_NumAllocations )
      break;
    v41 = *v108;
    if ( v37->hSection )
    {
      if ( (*(_DWORD *)&v41 & 0x20000) == 0 )
      {
        *(_DWORD *)(v22 + 44) |= 0x20u;
        LOBYTE(v98) = v98 | 2;
      }
    }
    else if ( (*(_BYTE *)&v41 & 0x20) != 0 )
    {
      LODWORD(v24) = -1073741811;
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 10256;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"pSysMem pointer is NULL: 0x%I64x", 10256, 0, 0, 0, 0);
      goto LABEL_22;
    }
    *v35 = v37->Flags.Value;
    if ( (v37->Flags.Value & 1) != 0 && *v40 == 1 && v100[0] >= 0x1E )
    {
      v106 = 0;
      v107 = 0;
      v42 = DXGGLOBAL::GetGlobal();
      if ( (int)REMOTEMONITORMAPPING::FindMappingFromGuestVidPnSourceId(
                  (struct DXGGLOBAL *)((char *)v42 + 305272),
                  v37->VidPnSourceId,
                  (struct REMOTEMONITORMAPPING::PATH_IDENTIFIER_HOST *)&v106) >= 0
        && v106 == *(_DWORD **)(*((_QWORD *)v102 + 9) + 4892LL) )
      {
        v35[2] = v107;
        *(_QWORD *)(v22 + 56) |= 2uLL;
      }
      else
      {
        v35[2] = 0;
      }
    }
    else
    {
      v35[2] = v37->VidPnSourceId;
    }
    if ( v36 + v37->PrivateDriverDataSize > v39 )
    {
      WdLogSingleEntry5(0, 275, 2, 0, 0, 0);
      WdLogGlobalForLineNumber = 10289;
    }
    v35[1] = v37->PrivateDriverDataSize;
    if ( v37->PrivateDriverDataSize )
    {
      if ( v96 )
        pPrivateDriverData = v113[v38];
      else
        pPrivateDriverData = v37->pPrivateDriverData;
      if ( pPrivateDriverData )
        memmove((void *)(v22 + v36), pPrivateDriverData, v37->PrivateDriverDataSize);
      v36 += v37->PrivateDriverDataSize;
    }
    v35 += 3;
    ++v37;
    ++v38;
  }
  v44 = (*(_BYTE *)v108 & 8) == 0 && (*(_DWORD *)(v22 + 44) & 0x20020) == 0;
  v97 = v44;
  if ( v100[0] < 0x1E )
  {
    if ( !a11 || (v46 = 1, !v44) )
      v46 = 0;
    *(_BYTE *)(v22 + 56) = v46;
  }
  else
  {
    if ( !a11 || (v45 = 1, !v44) )
      v45 = 0;
    *(_QWORD *)(v22 + 56) = v45 | *(_QWORD *)(v22 + 56) & 0xFFFFFFFFFFFFFFFEuLL;
  }
  v47 = v110;
  v100[0] = v110;
  v48 = v105;
  LODWORD(v24) = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSyncMessage(v102, (struct DXGVMBUSMESSAGE *)&v128, v105, v100);
  if ( (int)v24 >= 0 )
  {
    LODWORD(v24) = -1073741823;
    if ( v100[0] >= (unsigned int)v47 )
    {
      LODWORD(v24) = 0;
      v122 = v48;
      v49 = v48;
      v106 = v48;
      v48[3] = v98;
      v123 = (char *)v48 + v47;
      v50 = p_NumAllocations;
      v51 = (char *)&v48[16 * *p_NumAllocations + 4 + 2 * *p_NumAllocations];
      v52 = v103;
      for ( i = 0; ; ++i )
      {
        v99 = i;
        v111 = v52;
        v114 = v51;
        if ( i >= *v50 )
        {
LABEL_131:
          *v118 = (unsigned __int8 *)v105;
          v25 = 0;
          goto LABEL_133;
        }
        if ( !v44 && (int)v24 >= 0 )
          break;
LABEL_128:
        if ( &v51[v52->PrivateDriverDataSize] > v123 )
        {
          WdLogSingleEntry5(0, 275, 2, 0, 0, 0);
          WdLogGlobalForLineNumber = 10589;
        }
        memmove(v113[i], v51, v52->PrivateDriverDataSize);
        v51 += v52->PrivateDriverDataSize;
        v103 = ++v52;
        v49 = v106;
        v50 = p_NumAllocations;
      }
      v54 = (__int64)*v108;
      v55 = i;
      v110 = i;
      v56 = &v49[18 * i];
      v104 = v56;
      v57 = *((_QWORD *)v56 + 4);
      *(_QWORD *)Length = v57;
      if ( (v54 & 8) != 0 )
      {
        PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, v57, MmCached, 4u);
        v59 = PagesForMdl;
        if ( !PagesForMdl )
        {
          LODWORD(v24) = -1073741801;
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 10376;
          DxgkLogInternalTriageEvent(
            0,
            262145,
            -1,
            (unsigned int)L"Failed to allocate memory for protecter allocation",
            10376,
            0,
            0,
            0,
            0);
          goto LABEL_131;
        }
        v52->hSection = PagesForMdl;
        if ( (*((_BYTE *)DXGGLOBAL::GetGlobal() + 1760) & 1) == 0 )
        {
          v60 = DXGGLOBAL::GetGlobal();
          LODWORD(v24) = DXG_GUEST_GLOBAL_VMBUS::CreateGpadlFromMdl(
                           *((DXG_GUEST_GLOBAL_VMBUS **)v60 + 212),
                           v59,
                           v56 + 7);
        }
LABEL_101:
        if ( (int)v24 >= 0 )
        {
          if ( (*((_BYTE *)DXGGLOBAL::GetGlobal() + 1760) & 1) == 0 )
          {
            *(_OWORD *)v126 = 0;
            v127 = 0;
            v74 = v102;
            DXGVMBUSMESSAGE::InitializeMessage((DXGVMBUSMESSAGE *)v126, v102, 0x28u, 0, 0, 0);
            v75 = v126[0];
            v76 = v56[7];
            v77 = v122[18 * v55 + 4];
            *(_QWORD *)v126[0] = 0;
            *((_DWORD *)v75 + 2) = a2;
            *((_BYTE *)v75 + 12) = 0;
            *((_DWORD *)v75 + 3) &= 0x1FFu;
            *((_QWORD *)v75 + 2) = 45;
            v78 = a3;
            *((_DWORD *)v75 + 6) = a3;
            *((_DWORD *)v75 + 7) = v77;
            *((_DWORD *)v75 + 8) = v76;
            v79 = DXG_VMBUS_CHANNEL_BASE::VmBusSendSyncMessageStatusReturn(
                    v74,
                    (unsigned __int8 *)v126[1],
                    v126[0],
                    v127,
                    CacheTypea);
            v24 = v79;
            if ( v79 < 0 )
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 10502;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Failed to set existing sysmem Gpadl: 0x%I64x",
                v24,
                0,
                0,
                0,
                0);
            }
            DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)v126);
            goto LABEL_120;
          }
          v80 = (unsigned int)(v56[8] + 4095) >> 12;
          *(_OWORD *)v124 = 0;
          v125 = 0;
          v81 = v102;
          DXGVMBUSMESSAGE::InitializeMessage((DXGVMBUSMESSAGE *)v124, v102, 0x1EFF0u, 0, 0, 0);
          if ( !v124[0] )
          {
            LODWORD(v24) = -1073741801;
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 10518;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed to allocate DXGKVMB_COMMAND_SETEXISTINGSYSMEMPAGES",
              10518,
              0,
              0,
              0,
              0);
          }
          v82 = 0;
          v100[0] = 0;
          for ( j = (__int64 *)((char *)v52->hSection + 48); v82 < v80; v100[0] = v82 )
          {
            if ( (int)v24 < 0 )
              break;
            v84 = v124[0];
            v85 = (_QWORD *)((char *)v124[0] + 40);
            v86 = 15865;
            if ( v80 - v82 < 0x3DF9 )
              v86 = v80 - v82;
            v87 = v104[4];
            *(_QWORD *)v124[0] = 0;
            *((_DWORD *)v84 + 2) = a2;
            *((_BYTE *)v84 + 12) = 0;
            *((_DWORD *)v84 + 3) &= 0x1FFu;
            *((_QWORD *)v84 + 2) = 66;
            *((_DWORD *)v84 + 6) = a3;
            *((_DWORD *)v84 + 7) = v87;
            *((_DWORD *)v84 + 8) = v86;
            *((_DWORD *)v84 + 9) = v82;
            for ( k = 0; k < v86; ++k )
            {
              v89 = *j++;
              *v85++ = v89;
            }
            v90 = DXG_VMBUS_CHANNEL_BASE::VmBusSendSyncMessageStatusReturn(
                    v81,
                    (unsigned __int8 *)v124[1],
                    v124[0],
                    v125,
                    CacheType);
            v24 = v90;
            if ( v90 < 0 )
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 10539;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"DXGKVMB_COMMAND_SETEXISTINGSYSMEMPAGES failed: 0x%I64x",
                v24,
                0,
                0,
                0,
                0);
              v81 = v102;
            }
            v82 = v86 + v100[0];
          }
          DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)v124);
        }
        else
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 10488;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to allocate existing sysmem Gpadl: 0x%I64x",
            (int)v24,
            0,
            0,
            0,
            0);
        }
        v78 = a3;
        v74 = v102;
LABEL_120:
        if ( a11 )
        {
          v130 = 0;
          v131 = 0;
          DXGVMBUSMESSAGE::InitializeMessage((DXGVMBUSMESSAGE *)&v130, v74, 0x30u, 0, 0, 0);
          v91 = v130;
          if ( (_QWORD)v130 )
          {
            *(_QWORD *)v130 = 0;
            *(_BYTE *)(v91 + 12) = 0;
            *(_DWORD *)(v91 + 12) &= 0x1FFu;
            *(_QWORD *)(v91 + 16) = 11;
            *(_DWORD *)(v91 + 8) = a2;
            *(_DWORD *)(v91 + 24) = v78;
            *(_DWORD *)(v91 + 36) = 1;
            *(_DWORD *)(v91 + 40) = v104[4];
            *(_DWORD *)(v91 + 32) = 3;
            LODWORD(VirtualAddress) = 24;
            v92 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSyncMessage(
                    v74,
                    (struct DXGVMBUSMESSAGE *)&v130,
                    v132,
                    (unsigned int *)&VirtualAddress);
            LODWORD(v24) = v92;
            if ( v92 >= 0 )
            {
              LODWORD(v24) = v133;
            }
            else
            {
              v93 = v92;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 10574;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"VmBusSendMakeResident failed: 0x%I64x",
                v93,
                0,
                0,
                0,
                0);
            }
          }
          else
          {
            WdLogSingleEntry0(6);
            WdLogGlobalForLineNumber = 10558;
            DxgkLogInternalTriageEvent(
              0,
              262145,
              -1,
              (unsigned int)L"Failed to allocate storage for input buffer to MakeResident",
              10558,
              0,
              0,
              0,
              0);
            LODWORD(v24) = -1073741801;
          }
          DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v130);
        }
        v52 = v103;
        v51 = v114;
        i = v99;
        v44 = v97;
        goto LABEL_128;
      }
      VirtualAddress = 0;
      p_hSection = &v52->hSection;
      v121 = (union _D3DDDI_ALLOCATIONINFO2::$332422D50CC5DC1C38BC4DCC57A4E2CB *)&v52->hSection;
      if ( (v54 & 0x20000) != 0 )
      {
        Object = 0;
        v62 = ObReferenceObjectByHandle(*p_hSection, 0x20000u, MmSectionObjectType, 1, &Object, 0);
        v24 = v62;
        v64 = Object;
        v117 = Object;
        if ( v62 >= 0 )
        {
          v115 = 0;
          *(_QWORD *)v100 = *((_QWORD *)v56 + 4);
          v65 = *(_QWORD *)v100;
          CurrentProcess = PsGetCurrentProcess(v63);
          VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
          LODWORD(v24) = (*((__int64 (__fastcall **)(PVOID, __int64, PVOID *, _QWORD, __int64, struct _MDL **, unsigned int *, int, _DWORD, int))VirtualMemoryInterface
                          + 3))(
                           v64,
                           CurrentProcess,
                           &VirtualAddress,
                           0,
                           v65,
                           &v115,
                           v100,
                           2,
                           0,
                           4);
          if ( (int)v24 >= 0 )
          {
            v68 = 1;
            LODWORD(v57) = Length[0];
LABEL_91:
            if ( (int)v24 >= 0 )
            {
              if ( (*((_BYTE *)DXGGLOBAL::GetGlobal() + 1760) & 1) != 0 )
              {
                Mdl = IoAllocateMdl(VirtualAddress, v57, 0, 0, 0);
                v115 = Mdl;
                if ( Mdl )
                {
                  v104[6] &= ~0x200000u;
                  MmProbeAndLockPages(Mdl, 0, (LOCK_OPERATION)(~(unsigned __int8)(*(unsigned int *)v108 >> 6) & 2));
                  v104[6] |= 0x200000u;
                }
                else
                {
                  LODWORD(v24) = -1073741801;
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 10457;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"Failed to allocate MDL for sysmem: 0x%I64x",
                    -1073741801,
                    0,
                    0,
                    0,
                    0);
                }
                *p_hSection = Mdl;
              }
              else
              {
                v69 = DXGGLOBAL::GetGlobal();
                LODWORD(v24) = DXG_GUEST_GLOBAL_VMBUS::CreateGpadlFromBuffer(
                                 *((DXG_GUEST_GLOBAL_VMBUS **)v69 + 212),
                                 VirtualAddress,
                                 v57,
                                 v104 + 7);
              }
            }
            if ( v68 )
            {
              v71 = VirtualAddress;
              v72 = PsGetCurrentProcess(v54);
              v73 = DxgkGetVirtualMemoryInterface();
              (*((void (__fastcall **)(__int64, PVOID))v73 + 4))(v72, v71);
              ObfDereferenceObject(v64);
            }
            v52 = v103;
            v55 = v110;
            v56 = v104;
            goto LABEL_101;
          }
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 10429;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to map allocation view. Size: 0x%I64x",
            *(__int64 *)v100,
            0,
            0,
            0,
            0);
          ObfDereferenceObject(v64);
        }
        else
        {
          WdLogSingleEntry2(2, *p_hSection);
          WdLogGlobalForLineNumber = 10410;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to take a reference on hSection:0x%I64x, returning 0x%I64x",
            (__int64)*p_hSection,
            v24,
            0,
            0,
            0);
        }
        LODWORD(v57) = Length[0];
      }
      else
      {
        v64 = 0;
        v117 = 0;
        VirtualAddress = *p_hSection;
      }
      v68 = 0;
      goto LABEL_91;
    }
  }
  v25 = v105;
LABEL_133:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v25);
  if ( (int)v24 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 10607;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"VmBusSendCreateAllocation failed: 0x%I64x",
      (int)v24,
      0,
      0,
      0,
      0);
  }
  DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v128);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1401dfb74  mov     [rsp+arg_10], r8d
0x1401dfb79  mov     [rsp+arg_8], edx
0x1401dfb7d  push    rbx
0x1401dfb7e  push    rsi
0x1401dfb7f  push    rdi
0x1401dfb80  push    r12
0x1401dfb82  push    r13
0x1401dfb84  push    r14
0x1401dfb86  push    r15
0x1401dfb88  sub     rsp, 5D0h
0x1401dfb8f  mov     rax, cs:__security_cookie
0x1401dfb96  xor     rax, rsp
0x1401dfb99  mov     [rsp+608h+var_40], rax
0x1401dfba1  mov     r12d, r9d
0x1401dfba4  mov     [rsp+608h+var_588], rcx
0x1401dfbac  mov     [rsp+608h+var_500], rcx
0x1401dfbb4  mov     r14, [rsp+608h+arg_20]
0x1401dfbbc  mov     rdi, [rsp+608h+arg_28]
0x1401dfbc4  mov     [rsp+608h+var_580], rdi
0x1401dfbcc  mov     rax, [rsp+608h+arg_30]
0x1401dfbd4  mov     [rsp+608h+var_530], rax
0x1401dfbdc  mov     rax, [rsp+608h+arg_38]
0x1401dfbe4  mov     [rsp+608h+var_540], rax
0x1401dfbec  mov     r13, [rsp+608h+Src]
0x1401dfbf4  mov     rax, [rsp+608h+arg_58]
0x1401dfbfc  mov     [rsp+608h+var_508], rax
0x1401dfc04  xor     ebx, ebx
0x1401dfc06  mov     [rax], rbx
0x1401dfc09  cmp     [rsp+608h+arg_48], bl
0x1401dfc10  jz      short loc_1401DFC21
0x1401dfc12  test    dword ptr [r14+38h], 10000h
0x1401dfc1a  mov     [rsp+608h+var_5A8], 1
0x1401dfc1f  jz      short loc_1401DFC25
0x1401dfc21  mov     [rsp+608h+var_5A8], bl
0x1401dfc25  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401dfc2a  mov     r10, rax
0x1401dfc2d  mov     edx, [r14+18h]
0x1401dfc31  mov     r8d, [r14+28h]
0x1401dfc35  add     r8d, edx
0x1401dfc38  cmp     r8d, edx
0x1401dfc3b  jb      loc_1401E0D69
0x1401dfc41  mov     esi, ebx
0x1401dfc43  mov     ecx, ebx
0x1401dfc45  lea     r15, [r14+2Ch]
0x1401dfc49  mov     [rsp+608h+var_550], r15
0x1401dfc51  mov     edx, [r15]
0x1401dfc54  cmp     ecx, edx
0x1401dfc56  jnb     short loc_1401DFC7A
0x1401dfc58  mov     eax, ecx
0x1401dfc5a  lea     rax, [rax+rax*2]
0x1401dfc5e  shl     rax, 5
0x1401dfc62  mov     r9d, [rax+rdi+18h]
0x1401dfc67  add     r9d, esi
0x1401dfc6a  cmp     r9d, esi
0x1401dfc6d  jb      loc_1401E0D69
0x1401dfc73  mov     esi, r9d
0x1401dfc76  inc     ecx
0x1401dfc78  jmp     short loc_1401DFC54
0x1401dfc7a  lea     eax, [r8+rsi]
0x1401dfc7e  cmp     eax, r8d
0x1401dfc81  jb      loc_1401E0D69
0x1401dfc87  lea     ecx, [rax+40h]
0x1401dfc8a  cmp     ecx, eax
0x1401dfc8c  jb      loc_1401E0D69
0x1401dfc92  mov     [rsp+608h+var_4F8], r15
0x1401dfc9a  lea     eax, [rdx-1]
0x1401dfc9d  cmp     eax, 71Bh
0x1401dfca2  ja      loc_1401E0D12
0x1401dfca8  cmp     esi, 20000h
0x1401dfcae  ja      loc_1401E0D12
0x1401dfcb4  lea     r15, [rdx+rdx*2]
0x1401dfcb8  shl     r15, 2
0x1401dfcbc  mov     eax, 0FFFFFFFFh
0x1401dfcc1  cmp     r15, rax
0x1401dfcc4  ja      loc_1401E0D69
0x1401dfcca  lea     eax, [r15+rcx]
0x1401dfcce  mov     dword ptr [rsp+608h+VirtualAddress], eax
0x1401dfcd2  cmp     eax, ecx
0x1401dfcd4  jb      loc_1401E0D69
0x1401dfcda  mov     ecx, [r10+6D8h]
0x1401dfce1  mov     [rsp+608h+var_598], ecx
0x1401dfce5  mov     [rsp+608h+var_5A4], ebx
0x1401dfce9  xorps   xmm0, xmm0
0x1401dfcec  movdqa  [rsp+608h+var_298], xmm0
0x1401dfcf5  mov     [rsp+608h+var_288], ebx
0x1401dfcfc  mov     qword ptr [rsp+608h+Flags], rbx; unsigned int *
0x1401dfd01  mov     qword ptr [rsp+608h+CacheType], rbx; unsigned int *
0x1401dfd06  xor     r9d, r9d; unsigned int *
0x1401dfd09  mov     r8d, eax; unsigned int
0x1401dfd0c  mov     rdx, [rsp+608h+var_588]; struct DXG_VMBUS_CHANNEL_BASE *
0x1401dfd14  lea     rcx, [rsp+608h+var_298]; this
0x1401dfd1c  call    ?InitializeMessage@DXGVMBUSMESSAGE@@QEAAXPEAUDXG_VMBUS_CHANNEL_BASE@@IPEAI11@Z; DXGVMBUSMESSAGE::InitializeMessage(DXG_VMBUS_CHANNEL_BASE *,uint,uint *,uint *,uint *)
0x1401dfd21  mov     rdi, qword ptr [rsp+608h+var_298]
0x1401dfd29  test    rdi, rdi
0x1401dfd2c  jnz     short loc_1401DFD45
0x1401dfd2e  lea     rcx, [rsp+608h+var_298]; this
0x1401dfd36  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x1401dfd3b  mov     eax, 0C0000017h
0x1401dfd40  jmp     loc_1401E0D6E
0x1401dfd45  mov     [rdi], rbx
0x1401dfd48  mov     [rdi+8], ebx
0x1401dfd4b  mov     [rdi+0Ch], bl
0x1401dfd4e  and     dword ptr [rdi+0Ch], 1FFh
0x1401dfd55  mov     qword ptr [rdi+10h], 4
0x1401dfd5d  mov     eax, [r14+2Ch]
0x1401dfd61  lea     ecx, [rax+rax*8]
0x1401dfd64  lea     eax, ds:17h[rcx*8]
0x1401dfd6b  add     eax, esi
0x1401dfd6d  and     eax, 0FFFFFFF8h
0x1401dfd70  mov     [rsp+608h+var_548], rax
0x1401dfd78  mov     edx, 4B677844h
0x1401dfd7d  mov     r8d, 40h ; '@'
0x1401dfd83  mov     ecx, eax
0x1401dfd85  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401dfd8a  mov     [rsp+608h+var_570], rax
0x1401dfd92  test    rax, rax
0x1401dfd95  jnz     short loc_1401DFDA5
0x1401dfd97  mov     r14d, 0C0000017h
0x1401dfd9d  mov     rcx, rax
0x1401dfda0  jmp     loc_1401E0C9D
0x1401dfda5  mov     eax, [rsp+608h+arg_10]
0x1401dfdac  mov     [rdi+18h], eax
0x1401dfdaf  mov     eax, [rsp+608h+arg_8]
0x1401dfdb6  mov     [rdi+8], eax
0x1401dfdb9  lea     r8, [r14+38h]
0x1401dfdbd  mov     [rsp+608h+var_558], r8
0x1401dfdc5  mov     ecx, [r8]
0x1401dfdc8  mov     [rdi+2Ch], ecx
0x1401dfdcb  mov     [rdi+1Ch], r12d
0x1401dfdcf  mov     rax, [r14+40h]
0x1401dfdd3  mov     [rdi+30h], rax
0x1401dfdd7  mov     eax, [r14+2Ch]
0x1401dfddb  mov     [rdi+28h], eax
0x1401dfdde  mov     edx, [r14+18h]
0x1401dfde2  mov     [rdi+20h], edx
0x1401dfde5  mov     eax, [r14+28h]
0x1401dfde9  mov     [rdi+24h], eax
0x1401dfdec  btr     ecx, 10h
0x1401dfdf0  mov     [rdi+2Ch], ecx
0x1401dfdf3  test    dword ptr [r8], 20020h
0x1401dfdfa  jnz     short loc_1401DFE69
0x1401dfdfc  bt      ecx, 0Ch
0x1401dfe00  jnb     short loc_1401DFE72
0x1401dfe02  mov     ecx, 2
0x1401dfe07  call    cs:__imp_WdLogSingleEntry0
0x1401dfe0e  nop     dword ptr [rax+rax+00h]
0x1401dfe13  mov     eax, 27BAh
0x1401dfe18  mov     cs:WdLogGlobalForLineNumber, eax
0x1401dfe1e  mov     [rsp+608h+var_5C8], rbx
0x1401dfe23  mov     [rsp+608h+var_5D0], rbx
0x1401dfe28  mov     [rsp+608h+var_5D8], rbx
0x1401dfe2d  mov     qword ptr [rsp+608h+Flags], rbx
0x1401dfe32  mov     qword ptr [rsp+608h+CacheType], rax
0x1401dfe37  lea     r9, aOpenCrossAdapt; "Open cross adapter allocation is not su"...
0x1401dfe3e  mov     esi, 0FFFFFFFFh
0x1401dfe43  mov     r8d, esi
0x1401dfe46  mov     r15d, 40000h
0x1401dfe4c  mov     edx, r15d
0x1401dfe4f  xor     ecx, ecx
0x1401dfe51  call    DxgkLogInternalTriageEvent
0x1401dfe56  mov     r14d, 0C000000Dh
0x1401dfe5c  mov     rcx, [rsp+608h+var_570]
0x1401dfe64  jmp     loc_1401E0CA8
0x1401dfe69  and     ecx, 0FFFFE7FFh
0x1401dfe6f  mov     [rdi+2Ch], ecx
0x1401dfe72  mov     eax, [r8]
0x1401dfe75  test    al, 8
0x1401dfe77  jz      short loc_1401DFE83
0x1401dfe79  mov     byte ptr [rsp+608h+var_5A4], 1
0x1401dfe7e  and     ecx, 0FFFFFFF7h
0x1401dfe81  jmp     short loc_1401DFE9D
0x1401dfe83  test    al, 20h
0x1401dfe85  jz      short loc_1401DFE8E
0x1401dfe87  mov     byte ptr [rsp+608h+var_5A4], 2
0x1401dfe8c  jmp     short loc_1401DFEA3
0x1401dfe8e  bt      eax, 11h
0x1401dfe92  jnb     short loc_1401DFEA3
0x1401dfe94  mov     byte ptr [rsp+608h+var_5A4], 2
0x1401dfe99  btr     ecx, 11h
0x1401dfe9d  or      ecx, 20h
0x1401dfea0  mov     [rdi+2Ch], ecx
0x1401dfea3  add     r15d, 40h ; '@'
0x1401dfea7  mov     esi, [r14+18h]
0x1401dfeab  add     esi, r15d
0x1401dfeae  test    edx, edx
0x1401dfeb0  jz      short loc_1401DFEC8
0x1401dfeb2  test    r13, r13
0x1401dfeb5  jz      short loc_1401DFEC8
0x1401dfeb7  mov     r8, rdx; Size
0x1401dfeba  mov     ecx, r15d
0x1401dfebd  add     rcx, rdi; void *
0x1401dfec0  mov     rdx, r13; Src
0x1401dfec3  call    memmove
0x1401dfec8  mov     eax, [rdi+24h]
0x1401dfecb  test    eax, eax
0x1401dfecd  jz      short loc_1401DFEE9
0x1401dfecf  mov     rdx, [rsp+608h+var_540]; Src
0x1401dfed7  test    rdx, rdx
0x1401dfeda  jz      short loc_1401DFEE9
0x1401dfedc  mov     r8d, eax; Size
0x1401dfedf  mov     ecx, esi
0x1401dfee1  add     rcx, rdi; void *
0x1401dfee4  call    memmove
0x1401dfee9  lea     r14, [rdi+40h]
0x1401dfeed  mov     r12d, [rdi+24h]
0x1401dfef1  add     r12d, esi
0x1401dfef4  mov     rsi, [rsp+608h+var_580]
0x1401dfefc  mov     r15d, ebx
0x1401dfeff  mov     r13d, dword ptr [rsp+608h+VirtualAddress]
0x1401dff04  mov     rcx, [rsp+608h+var_550]
0x1401dff0c  mov     rax, [rsp+608h+var_558]
0x1401dff14  cmp     r15d, [rcx]
0x1401dff17  jnb     loc_1401E00B9
0x1401dff1d  mov     eax, [rax]
0x1401dff1f  cmp     [rsi+8], rbx
0x1401dff23  jz      short loc_1401DFF36
0x1401dff25  bt      eax, 11h
0x1401dff29  jb      short loc_1401DFF3E
0x1401dff2b  or      dword ptr [rdi+2Ch], 20h
0x1401dff2f  or      byte ptr [rsp+608h+var_5A4], 2
0x1401dff34  jmp     short loc_1401DFF3E
0x1401dff36  test    al, 20h
0x1401dff38  jnz     loc_1401E005A
0x1401dff3e  mov     eax, [rsi+20h]
0x1401dff41  mov     [r14], eax
0x1401dff44  mov     eax, [rsi+20h]
0x1401dff47  test    al, 1
0x1401dff49  jz      short loc_1401DFFCA
0x1401dff4b  cmp     dword ptr [rcx], 1
0x1401dff4e  jnz     short loc_1401DFFCA
0x1401dff50  cmp     [rsp+608h+var_598], 1Eh
0x1401dff55  jb      short loc_1401DFFCA
0x1401dff57  xor     eax, eax
0x1401dff59  mov     [rsp+608h+var_568], rax
0x1401dff61  mov     [rsp+608h+var_560], eax
0x1401dff68  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401dff6d  lea     rcx, [rax+4A878h]; this
0x1401dff74  lea     r8, [rsp+608h+var_568]; struct REMOTEMONITORMAPPING::PATH_IDENTIFIER_HOST *
0x1401dff7c  mov     edx, [rsi+1Ch]; unsigned int
0x1401dff7f  call    ?FindMappingFromGuestVidPnSourceId@REMOTEMONITORMAPPING@@QEAAJIPEAUPATH_IDENTIFIER_HOST@1@@Z; REMOTEMONITORMAPPING::FindMappingFromGuestVidPnSourceId(uint,REMOTEMONITORMAPPING::PATH_IDENTIFIER_HOST *)
0x1401dff84  test    eax, eax
0x1401dff86  js      short loc_1401DFFC4
0x1401dff88  mov     rax, [rsp+608h+var_588]
0x1401dff90  mov     rcx, [rax+48h]
0x1401dff94  mov     eax, dword ptr [rsp+608h+var_568]
0x1401dff9b  cmp     eax, [rcx+131Ch]
0x1401dffa1  jnz     short loc_1401DFFC4
0x1401dffa3  mov     eax, dword ptr [rsp+608h+var_568+4]
0x1401dffaa  cmp     eax, [rcx+1320h]
0x1401dffb0  jnz     short loc_1401DFFC4
0x1401dffb2  mov     eax, [rsp+608h+var_560]
0x1401dffb9  mov     [r14+8], eax
0x1401dffbd  or      qword ptr [rdi+38h], 2
0x1401dffc2  jmp     short loc_1401DFFD1
0x1401dffc4  mov     [r14+8], ebx
0x1401dffc8  jmp     short loc_1401DFFD1
0x1401dffca  mov     eax, [rsi+1Ch]
0x1401dffcd  mov     [r14+8], eax
0x1401dffd1  mov     ecx, [rsi+18h]
0x1401dffd4  add     ecx, r12d
0x1401dffd7  cmp     ecx, r13d
0x1401dffda  jbe     short loc_1401E000A
0x1401dffdc  mov     qword ptr [rsp+608h+Flags], rbx
0x1401dffe1  mov     qword ptr [rsp+608h+CacheType], rbx
0x1401dffe6  xor     r9d, r9d
0x1401dffe9  mov     edx, 113h
0x1401dffee  xor     ecx, ecx
0x1401dfff0  lea     r8d, [r9+2]
0x1401dfff4  call    cs:__imp_WdLogSingleEntry5
0x1401dfffb  nop     dword ptr [rax+rax+00h]
0x1401e0000  mov     cs:WdLogGlobalForLineNumber, 2831h
0x1401e000a  mov     eax, [rsi+18h]
0x1401e000d  mov     [r14+4], eax
0x1401e0011  mov     ecx, [rsi+18h]
0x1401e0014  test    ecx, ecx
0x1401e0016  jz      short loc_1401E004A
0x1401e0018  cmp     [rsp+608h+var_5A8], bl
0x1401e001c  jz      short loc_1401E002F
0x1401e001e  mov     eax, r15d
0x1401e0021  mov     rdx, [rsp+608h+var_530]
0x1401e0029  mov     rdx, [rdx+rax*8]
0x1401e002d  jmp     short loc_1401E0033
0x1401e002f  mov     rdx, [rsi+10h]; Src
0x1401e0033  test    rdx, rdx
0x1401e0036  jz      short loc_1401E0046
0x1401e0038  mov     r8, rcx; Size
0x1401e003b  mov     ecx, r12d
0x1401e003e  add     rcx, rdi; void *
0x1401e0041  call    memmove
0x1401e0046  add     r12d, [rsi+18h]
0x1401e004a  add     r14, 0Ch
0x1401e004e  add     rsi, 60h ; '`'
0x1401e0052  inc     r15d
0x1401e0055  jmp     loc_1401DFF04
0x1401e005a  mov     ecx, 2
0x1401e005f  mov     r14d, 0C000000Dh
0x1401e0065  call    cs:__imp_WdLogSingleEntry0
0x1401e006c  nop     dword ptr [rax+rax+00h]
0x1401e0071  mov     eax, 2810h
0x1401e0076  mov     cs:WdLogGlobalForLineNumber, eax
  ... truncated ...
```
