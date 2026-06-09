# DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendCreateAllocation(uint,uint,uint,_D3DKMT_CREATEALLOCATION const *,_D3DDDI_ALLOCATIONINFO2 *,void * *,void const *,void const *,uchar,uchar,uchar * *)

- ea: `0x1401dd804`
- end: `0x1401dea22`
- name: `?VmBusSendCreateAllocation@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJIIIPEBU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@PEAPEAXPEBX3EEPEAPEAE@Z`
- size: `4638`
- prototype: `__int64 __fastcall(DXG_GUEST_VIRTUALGPU_VMBUS *__hidden this, unsigned int, unsigned int, unsigned int, const struct _D3DKMT_CREATEALLOCATION *, struct _D3DDDI_ALLOCATIONINFO2 *, void **, const void *, const void *Src, char, char, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140377040`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x14001b890`
- `0x1400378f0`
- `0x140062450`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x140192b24`
- `0x1401dd804`
- `0x14025c5bc`
- `0x14027e3c0`
- `0x14027e420`
- `0x140292b54`
- `0x14035f150`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401de05b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401de339`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401de05b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401de339`
- `ntoskrnl!ObfDereferenceObject` at `0x1401de115`
- `ntoskrnl!ObfDereferenceObject` at `0x1401de35f`
- `ntoskrnl!ObfDereferenceObject` at `0x1401de115`
- `ntoskrnl!ObfDereferenceObject` at `0x1401de35f`
- `ntoskrnl!IoAllocateMdl` at `0x1401de1a5`
- `ntoskrnl!IoAllocateMdl` at `0x1401de1a5`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401de245`
- `ntoskrnl!MmProbeAndLockPages` at `0x1401de245`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401ddfc4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401ddfc4`
- `ntoskrnl!MmSectionObjectType` at `0x1401ddfb4`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1401dded2`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1401dded2`
- `watchdog!WdLogSingleEntry2` at `0x1401ddff3`
- `watchdog!WdLogSingleEntry2` at `0x1401de9ae`
- `watchdog!WdLogSingleEntry2` at `0x1401ddff3`
- `watchdog!WdLogSingleEntry2` at `0x1401de9ae`
- `watchdog!WdLogSingleEntry0` at `0x1401dda97`
- `watchdog!WdLogSingleEntry0` at `0x1401ddcf5`
- `watchdog!WdLogSingleEntry0` at `0x1401ddeef`
- `watchdog!WdLogSingleEntry0` at `0x1401de55e`
- `watchdog!WdLogSingleEntry0` at `0x1401de748`
- `watchdog!WdLogSingleEntry0` at `0x1401dda97`
- `watchdog!WdLogSingleEntry0` at `0x1401ddcf5`
- `watchdog!WdLogSingleEntry0` at `0x1401ddeef`
- `watchdog!WdLogSingleEntry0` at `0x1401de55e`
- `watchdog!WdLogSingleEntry0` at `0x1401de748`
- `watchdog!WdLogSingleEntry5` at `0x1401ddc84`
- `watchdog!WdLogSingleEntry5` at `0x1401de8ae`
- `watchdog!WdLogSingleEntry5` at `0x1401ddc84`
- `watchdog!WdLogSingleEntry5` at `0x1401de8ae`
- `watchdog!WdLogSingleEntry1` at `0x1401de0c7`
- `watchdog!WdLogSingleEntry1` at `0x1401de1ce`
- `watchdog!WdLogSingleEntry1` at `0x1401de273`
- `watchdog!WdLogSingleEntry1` at `0x1401de393`
- `watchdog!WdLogSingleEntry1` at `0x1401de4ae`
- `watchdog!WdLogSingleEntry1` at `0x1401de672`
- `watchdog!WdLogSingleEntry1` at `0x1401de812`
- `watchdog!WdLogSingleEntry1` at `0x1401de94d`
- `watchdog!WdLogSingleEntry1` at `0x1401de0c7`
- `watchdog!WdLogSingleEntry1` at `0x1401de1ce`
- `watchdog!WdLogSingleEntry1` at `0x1401de273`
- `watchdog!WdLogSingleEntry1` at `0x1401de393`
- `watchdog!WdLogSingleEntry1` at `0x1401de4ae`
- `watchdog!WdLogSingleEntry1` at `0x1401de672`
- `watchdog!WdLogSingleEntry1` at `0x1401de812`
- `watchdog!WdLogSingleEntry1` at `0x1401de94d`

## string_xrefs

- `0x1401de591`: `Failed to allocate DXGKVMB_COMMAND_SETEXISTINGSYSMEMPAGES`
- `0x1401de97c`: `VmBusSendCreateAllocation failed: 0x%I64x`
- `0x1401de841`: `VmBusSendMakeResident failed: 0x%I64x`
- `0x1401ddac7`: `Open cross adapter allocation is not supported`
- `0x1401de77b`: `Failed to allocate storage for input buffer to MakeResident`
- `0x1401de6a1`: `DXGKVMB_COMMAND_SETEXISTINGSYSMEMPAGES failed: 0x%I64x`

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
    WdLogGlobalForLineNumber = 10114;
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
    WdLogGlobalForLineNumber = 10172;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Open cross adapter allocation is not supported",
      10172,
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
      WdLogGlobalForLineNumber = 10258;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"pSysMem pointer is NULL: 0x%I64x", 10258, 0, 0, 0, 0);
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
        && v106 == *(_DWORD **)(*((_QWORD *)v102 + 9) + 4876LL) )
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
      WdLogGlobalForLineNumber = 10291;
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
          WdLogGlobalForLineNumber = 10591;
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
          WdLogGlobalForLineNumber = 10378;
          DxgkLogInternalTriageEvent(
            0,
            262145,
            -1,
            (unsigned int)L"Failed to allocate memory for protecter allocation",
            10378,
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
              WdLogGlobalForLineNumber = 10504;
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
            WdLogGlobalForLineNumber = 10520;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed to allocate DXGKVMB_COMMAND_SETEXISTINGSYSMEMPAGES",
              10520,
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
              WdLogGlobalForLineNumber = 10541;
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
          WdLogGlobalForLineNumber = 10490;
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
              WdLogGlobalForLineNumber = 10576;
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
            WdLogGlobalForLineNumber = 10560;
            DxgkLogInternalTriageEvent(
              0,
              262145,
              -1,
              (unsigned int)L"Failed to allocate storage for input buffer to MakeResident",
              10560,
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
                  WdLogGlobalForLineNumber = 10459;
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
          WdLogGlobalForLineNumber = 10431;
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
          WdLogGlobalForLineNumber = 10412;
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
    WdLogGlobalForLineNumber = 10609;
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
0x1401dd804  mov     [rsp+arg_10], r8d
0x1401dd809  mov     [rsp+arg_8], edx
0x1401dd80d  push    rbx
0x1401dd80e  push    rsi
0x1401dd80f  push    rdi
0x1401dd810  push    r12
0x1401dd812  push    r13
0x1401dd814  push    r14
0x1401dd816  push    r15
0x1401dd818  sub     rsp, 5D0h
0x1401dd81f  mov     rax, cs:__security_cookie
0x1401dd826  xor     rax, rsp
0x1401dd829  mov     [rsp+608h+var_40], rax
0x1401dd831  mov     r12d, r9d
0x1401dd834  mov     [rsp+608h+var_588], rcx
0x1401dd83c  mov     [rsp+608h+var_500], rcx
0x1401dd844  mov     r14, [rsp+608h+arg_20]
0x1401dd84c  mov     rdi, [rsp+608h+arg_28]
0x1401dd854  mov     [rsp+608h+var_580], rdi
0x1401dd85c  mov     rax, [rsp+608h+arg_30]
0x1401dd864  mov     [rsp+608h+var_530], rax
0x1401dd86c  mov     rax, [rsp+608h+arg_38]
0x1401dd874  mov     [rsp+608h+var_540], rax
0x1401dd87c  mov     r13, [rsp+608h+Src]
0x1401dd884  mov     rax, [rsp+608h+arg_58]
0x1401dd88c  mov     [rsp+608h+var_508], rax
0x1401dd894  xor     ebx, ebx
0x1401dd896  mov     [rax], rbx
0x1401dd899  cmp     [rsp+608h+arg_48], bl
0x1401dd8a0  jz      short loc_1401DD8B1
0x1401dd8a2  test    dword ptr [r14+38h], 10000h
0x1401dd8aa  mov     [rsp+608h+var_5A8], 1
0x1401dd8af  jz      short loc_1401DD8B5
0x1401dd8b1  mov     [rsp+608h+var_5A8], bl
0x1401dd8b5  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401dd8ba  mov     r10, rax
0x1401dd8bd  mov     edx, [r14+18h]
0x1401dd8c1  mov     r8d, [r14+28h]
0x1401dd8c5  add     r8d, edx
0x1401dd8c8  cmp     r8d, edx
0x1401dd8cb  jb      loc_1401DE9F9
0x1401dd8d1  mov     esi, ebx
0x1401dd8d3  mov     ecx, ebx
0x1401dd8d5  lea     r15, [r14+2Ch]
0x1401dd8d9  mov     [rsp+608h+var_550], r15
0x1401dd8e1  mov     edx, [r15]
0x1401dd8e4  cmp     ecx, edx
0x1401dd8e6  jnb     short loc_1401DD90A
0x1401dd8e8  mov     eax, ecx
0x1401dd8ea  lea     rax, [rax+rax*2]
0x1401dd8ee  shl     rax, 5
0x1401dd8f2  mov     r9d, [rax+rdi+18h]
0x1401dd8f7  add     r9d, esi
0x1401dd8fa  cmp     r9d, esi
0x1401dd8fd  jb      loc_1401DE9F9
0x1401dd903  mov     esi, r9d
0x1401dd906  inc     ecx
0x1401dd908  jmp     short loc_1401DD8E4
0x1401dd90a  lea     eax, [r8+rsi]
0x1401dd90e  cmp     eax, r8d
0x1401dd911  jb      loc_1401DE9F9
0x1401dd917  lea     ecx, [rax+40h]
0x1401dd91a  cmp     ecx, eax
0x1401dd91c  jb      loc_1401DE9F9
0x1401dd922  mov     [rsp+608h+var_4F8], r15
0x1401dd92a  lea     eax, [rdx-1]
0x1401dd92d  cmp     eax, 71Bh
0x1401dd932  ja      loc_1401DE9A2
0x1401dd938  cmp     esi, 20000h
0x1401dd93e  ja      loc_1401DE9A2
0x1401dd944  lea     r15, [rdx+rdx*2]
0x1401dd948  shl     r15, 2
0x1401dd94c  mov     eax, 0FFFFFFFFh
0x1401dd951  cmp     r15, rax
0x1401dd954  ja      loc_1401DE9F9
0x1401dd95a  lea     eax, [r15+rcx]
0x1401dd95e  mov     dword ptr [rsp+608h+VirtualAddress], eax
0x1401dd962  cmp     eax, ecx
0x1401dd964  jb      loc_1401DE9F9
0x1401dd96a  mov     ecx, [r10+6D8h]
0x1401dd971  mov     [rsp+608h+var_598], ecx
0x1401dd975  mov     [rsp+608h+var_5A4], ebx
0x1401dd979  xorps   xmm0, xmm0
0x1401dd97c  movdqa  [rsp+608h+var_298], xmm0
0x1401dd985  mov     [rsp+608h+var_288], ebx
0x1401dd98c  mov     qword ptr [rsp+608h+Flags], rbx; unsigned int *
0x1401dd991  mov     qword ptr [rsp+608h+CacheType], rbx; unsigned int *
0x1401dd996  xor     r9d, r9d; unsigned int *
0x1401dd999  mov     r8d, eax; unsigned int
0x1401dd99c  mov     rdx, [rsp+608h+var_588]; struct DXG_VMBUS_CHANNEL_BASE *
0x1401dd9a4  lea     rcx, [rsp+608h+var_298]; this
0x1401dd9ac  call    ?InitializeMessage@DXGVMBUSMESSAGE@@QEAAXPEAUDXG_VMBUS_CHANNEL_BASE@@IPEAI11@Z; DXGVMBUSMESSAGE::InitializeMessage(DXG_VMBUS_CHANNEL_BASE *,uint,uint *,uint *,uint *)
0x1401dd9b1  mov     rdi, qword ptr [rsp+608h+var_298]
0x1401dd9b9  test    rdi, rdi
0x1401dd9bc  jnz     short loc_1401DD9D5
0x1401dd9be  lea     rcx, [rsp+608h+var_298]; this
0x1401dd9c6  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x1401dd9cb  mov     eax, 0C0000017h
0x1401dd9d0  jmp     loc_1401DE9FE
0x1401dd9d5  mov     [rdi], rbx
0x1401dd9d8  mov     [rdi+8], ebx
0x1401dd9db  mov     [rdi+0Ch], bl
0x1401dd9de  and     dword ptr [rdi+0Ch], 1FFh
0x1401dd9e5  mov     qword ptr [rdi+10h], 4
0x1401dd9ed  mov     eax, [r14+2Ch]
0x1401dd9f1  lea     ecx, [rax+rax*8]
0x1401dd9f4  lea     eax, ds:17h[rcx*8]
0x1401dd9fb  add     eax, esi
0x1401dd9fd  and     eax, 0FFFFFFF8h
0x1401dda00  mov     [rsp+608h+var_548], rax
0x1401dda08  mov     edx, 4B677844h
0x1401dda0d  mov     r8d, 40h ; '@'
0x1401dda13  mov     ecx, eax
0x1401dda15  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401dda1a  mov     [rsp+608h+var_570], rax
0x1401dda22  test    rax, rax
0x1401dda25  jnz     short loc_1401DDA35
0x1401dda27  mov     r14d, 0C0000017h
0x1401dda2d  mov     rcx, rax
0x1401dda30  jmp     loc_1401DE92D
0x1401dda35  mov     eax, [rsp+608h+arg_10]
0x1401dda3c  mov     [rdi+18h], eax
0x1401dda3f  mov     eax, [rsp+608h+arg_8]
0x1401dda46  mov     [rdi+8], eax
0x1401dda49  lea     r8, [r14+38h]
0x1401dda4d  mov     [rsp+608h+var_558], r8
0x1401dda55  mov     ecx, [r8]
0x1401dda58  mov     [rdi+2Ch], ecx
0x1401dda5b  mov     [rdi+1Ch], r12d
0x1401dda5f  mov     rax, [r14+40h]
0x1401dda63  mov     [rdi+30h], rax
0x1401dda67  mov     eax, [r14+2Ch]
0x1401dda6b  mov     [rdi+28h], eax
0x1401dda6e  mov     edx, [r14+18h]
0x1401dda72  mov     [rdi+20h], edx
0x1401dda75  mov     eax, [r14+28h]
0x1401dda79  mov     [rdi+24h], eax
0x1401dda7c  btr     ecx, 10h
0x1401dda80  mov     [rdi+2Ch], ecx
0x1401dda83  test    dword ptr [r8], 20020h
0x1401dda8a  jnz     short loc_1401DDAF9
0x1401dda8c  bt      ecx, 0Ch
0x1401dda90  jnb     short loc_1401DDB02
0x1401dda92  mov     ecx, 2
0x1401dda97  call    cs:__imp_WdLogSingleEntry0
0x1401dda9e  nop     dword ptr [rax+rax+00h]
0x1401ddaa3  mov     eax, 27BCh
0x1401ddaa8  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ddaae  mov     [rsp+608h+var_5C8], rbx
0x1401ddab3  mov     [rsp+608h+var_5D0], rbx
0x1401ddab8  mov     [rsp+608h+var_5D8], rbx
0x1401ddabd  mov     qword ptr [rsp+608h+Flags], rbx
0x1401ddac2  mov     qword ptr [rsp+608h+CacheType], rax
0x1401ddac7  lea     r9, aOpenCrossAdapt; "Open cross adapter allocation is not su"...
0x1401ddace  mov     esi, 0FFFFFFFFh
0x1401ddad3  mov     r8d, esi
0x1401ddad6  mov     r15d, 40000h
0x1401ddadc  mov     edx, r15d
0x1401ddadf  xor     ecx, ecx
0x1401ddae1  call    DxgkLogInternalTriageEvent
0x1401ddae6  mov     r14d, 0C000000Dh
0x1401ddaec  mov     rcx, [rsp+608h+var_570]
0x1401ddaf4  jmp     loc_1401DE938
0x1401ddaf9  and     ecx, 0FFFFE7FFh
0x1401ddaff  mov     [rdi+2Ch], ecx
0x1401ddb02  mov     eax, [r8]
0x1401ddb05  test    al, 8
0x1401ddb07  jz      short loc_1401DDB13
0x1401ddb09  mov     byte ptr [rsp+608h+var_5A4], 1
0x1401ddb0e  and     ecx, 0FFFFFFF7h
0x1401ddb11  jmp     short loc_1401DDB2D
0x1401ddb13  test    al, 20h
0x1401ddb15  jz      short loc_1401DDB1E
0x1401ddb17  mov     byte ptr [rsp+608h+var_5A4], 2
0x1401ddb1c  jmp     short loc_1401DDB33
0x1401ddb1e  bt      eax, 11h
0x1401ddb22  jnb     short loc_1401DDB33
0x1401ddb24  mov     byte ptr [rsp+608h+var_5A4], 2
0x1401ddb29  btr     ecx, 11h
0x1401ddb2d  or      ecx, 20h
0x1401ddb30  mov     [rdi+2Ch], ecx
0x1401ddb33  add     r15d, 40h ; '@'
0x1401ddb37  mov     esi, [r14+18h]
0x1401ddb3b  add     esi, r15d
0x1401ddb3e  test    edx, edx
0x1401ddb40  jz      short loc_1401DDB58
0x1401ddb42  test    r13, r13
0x1401ddb45  jz      short loc_1401DDB58
0x1401ddb47  mov     r8, rdx; Size
0x1401ddb4a  mov     ecx, r15d
0x1401ddb4d  add     rcx, rdi; void *
0x1401ddb50  mov     rdx, r13; Src
0x1401ddb53  call    memmove
0x1401ddb58  mov     eax, [rdi+24h]
0x1401ddb5b  test    eax, eax
0x1401ddb5d  jz      short loc_1401DDB79
0x1401ddb5f  mov     rdx, [rsp+608h+var_540]; Src
0x1401ddb67  test    rdx, rdx
0x1401ddb6a  jz      short loc_1401DDB79
0x1401ddb6c  mov     r8d, eax; Size
0x1401ddb6f  mov     ecx, esi
0x1401ddb71  add     rcx, rdi; void *
0x1401ddb74  call    memmove
0x1401ddb79  lea     r14, [rdi+40h]
0x1401ddb7d  mov     r12d, [rdi+24h]
0x1401ddb81  add     r12d, esi
0x1401ddb84  mov     rsi, [rsp+608h+var_580]
0x1401ddb8c  mov     r15d, ebx
0x1401ddb8f  mov     r13d, dword ptr [rsp+608h+VirtualAddress]
0x1401ddb94  mov     rcx, [rsp+608h+var_550]
0x1401ddb9c  mov     rax, [rsp+608h+var_558]
0x1401ddba4  cmp     r15d, [rcx]
0x1401ddba7  jnb     loc_1401DDD49
0x1401ddbad  mov     eax, [rax]
0x1401ddbaf  cmp     [rsi+8], rbx
0x1401ddbb3  jz      short loc_1401DDBC6
0x1401ddbb5  bt      eax, 11h
0x1401ddbb9  jb      short loc_1401DDBCE
0x1401ddbbb  or      dword ptr [rdi+2Ch], 20h
0x1401ddbbf  or      byte ptr [rsp+608h+var_5A4], 2
0x1401ddbc4  jmp     short loc_1401DDBCE
0x1401ddbc6  test    al, 20h
0x1401ddbc8  jnz     loc_1401DDCEA
0x1401ddbce  mov     eax, [rsi+20h]
0x1401ddbd1  mov     [r14], eax
0x1401ddbd4  mov     eax, [rsi+20h]
0x1401ddbd7  test    al, 1
0x1401ddbd9  jz      short loc_1401DDC5A
0x1401ddbdb  cmp     dword ptr [rcx], 1
0x1401ddbde  jnz     short loc_1401DDC5A
0x1401ddbe0  cmp     [rsp+608h+var_598], 1Eh
0x1401ddbe5  jb      short loc_1401DDC5A
0x1401ddbe7  xor     eax, eax
0x1401ddbe9  mov     [rsp+608h+var_568], rax
0x1401ddbf1  mov     [rsp+608h+var_560], eax
0x1401ddbf8  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401ddbfd  lea     rcx, [rax+4A878h]; this
0x1401ddc04  lea     r8, [rsp+608h+var_568]; struct REMOTEMONITORMAPPING::PATH_IDENTIFIER_HOST *
0x1401ddc0c  mov     edx, [rsi+1Ch]; unsigned int
0x1401ddc0f  call    ?FindMappingFromGuestVidPnSourceId@REMOTEMONITORMAPPING@@QEAAJIPEAUPATH_IDENTIFIER_HOST@1@@Z; REMOTEMONITORMAPPING::FindMappingFromGuestVidPnSourceId(uint,REMOTEMONITORMAPPING::PATH_IDENTIFIER_HOST *)
0x1401ddc14  test    eax, eax
0x1401ddc16  js      short loc_1401DDC54
0x1401ddc18  mov     rax, [rsp+608h+var_588]
0x1401ddc20  mov     rcx, [rax+48h]
0x1401ddc24  mov     eax, dword ptr [rsp+608h+var_568]
0x1401ddc2b  cmp     eax, [rcx+130Ch]
0x1401ddc31  jnz     short loc_1401DDC54
0x1401ddc33  mov     eax, dword ptr [rsp+608h+var_568+4]
0x1401ddc3a  cmp     eax, [rcx+1310h]
0x1401ddc40  jnz     short loc_1401DDC54
0x1401ddc42  mov     eax, [rsp+608h+var_560]
0x1401ddc49  mov     [r14+8], eax
0x1401ddc4d  or      qword ptr [rdi+38h], 2
0x1401ddc52  jmp     short loc_1401DDC61
0x1401ddc54  mov     [r14+8], ebx
0x1401ddc58  jmp     short loc_1401DDC61
0x1401ddc5a  mov     eax, [rsi+1Ch]
0x1401ddc5d  mov     [r14+8], eax
0x1401ddc61  mov     ecx, [rsi+18h]
0x1401ddc64  add     ecx, r12d
0x1401ddc67  cmp     ecx, r13d
0x1401ddc6a  jbe     short loc_1401DDC9A
0x1401ddc6c  mov     qword ptr [rsp+608h+Flags], rbx
0x1401ddc71  mov     qword ptr [rsp+608h+CacheType], rbx
0x1401ddc76  xor     r9d, r9d
0x1401ddc79  mov     edx, 113h
0x1401ddc7e  xor     ecx, ecx
0x1401ddc80  lea     r8d, [r9+2]
0x1401ddc84  call    cs:__imp_WdLogSingleEntry5
0x1401ddc8b  nop     dword ptr [rax+rax+00h]
0x1401ddc90  mov     cs:WdLogGlobalForLineNumber, 2833h
0x1401ddc9a  mov     eax, [rsi+18h]
0x1401ddc9d  mov     [r14+4], eax
0x1401ddca1  mov     ecx, [rsi+18h]
0x1401ddca4  test    ecx, ecx
0x1401ddca6  jz      short loc_1401DDCDA
0x1401ddca8  cmp     [rsp+608h+var_5A8], bl
0x1401ddcac  jz      short loc_1401DDCBF
0x1401ddcae  mov     eax, r15d
0x1401ddcb1  mov     rdx, [rsp+608h+var_530]
0x1401ddcb9  mov     rdx, [rdx+rax*8]
0x1401ddcbd  jmp     short loc_1401DDCC3
0x1401ddcbf  mov     rdx, [rsi+10h]; Src
0x1401ddcc3  test    rdx, rdx
0x1401ddcc6  jz      short loc_1401DDCD6
0x1401ddcc8  mov     r8, rcx; Size
0x1401ddccb  mov     ecx, r12d
0x1401ddcce  add     rcx, rdi; void *
0x1401ddcd1  call    memmove
0x1401ddcd6  add     r12d, [rsi+18h]
0x1401ddcda  add     r14, 0Ch
0x1401ddcde  add     rsi, 60h ; '`'
0x1401ddce2  inc     r15d
0x1401ddce5  jmp     loc_1401DDB94
0x1401ddcea  mov     ecx, 2
0x1401ddcef  mov     r14d, 0C000000Dh
0x1401ddcf5  call    cs:__imp_WdLogSingleEntry0
0x1401ddcfc  nop     dword ptr [rax+rax+00h]
0x1401ddd01  mov     eax, 2812h
0x1401ddd06  mov     cs:WdLogGlobalForLineNumber, eax
  ... truncated ...
```
