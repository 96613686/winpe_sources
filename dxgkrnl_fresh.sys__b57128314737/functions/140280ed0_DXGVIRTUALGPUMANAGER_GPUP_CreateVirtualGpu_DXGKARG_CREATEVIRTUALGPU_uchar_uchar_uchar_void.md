# DXGVIRTUALGPUMANAGER_GPUP::CreateVirtualGpu(_DXGKARG_CREATEVIRTUALGPU *,uchar,uchar,uchar,void *)

- ea: `0x140280ed0`
- end: `0x140282192`
- name: `?CreateVirtualGpu@DXGVIRTUALGPUMANAGER_GPUP@@UEAAJPEAU_DXGKARG_CREATEVIRTUALGPU@@EEEPEAX@Z`
- size: `4802`
- prototype: `__int64 __fastcall(DXGVIRTUALGPUMANAGER_GPUP *this, struct _DXGKARG_CREATEVIRTUALGPU *, __int64, __int64, unsigned __int8, void *)`
- caller_count: `0`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x140015940`
- `0x140015a70`
- `0x140015b30`
- `0x140018054`
- `0x140018190`
- `0x14001aa04`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001c790`
- `0x14001d1a0`
- `0x14001f2f0`
- `0x14001f630`
- `0x14002e2e0`
- `0x14002ee60`
- `0x14002ef40`
- `0x140035130`
- `0x14004714c`
- `0x140049364`
- `0x140057ac8`
- `0x14007d814`
- `0x14007d840`
- `0x14007dd14`
- `0x14007f9d8`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1400a1520`
- `0x140259768`
- `0x140276f28`
- `0x140277fb8`
- `0x14027b230`
- `0x14027eac8`
- `0x140280ed0`
- `0x1402825d4`
- `0x14028285c`
- `0x1402bfa58`
- `0x1402bfb3c`
- `0x14032a5c4`
- `0x1403c2a5c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140280fc0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140280ff2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140280fc0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140280ff2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140280faf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140280fe1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140280faf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140280fe1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028106e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140281169`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028118f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402811d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402811fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140281512`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140281b37`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028106e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140281169`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14028118f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402811d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402811fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140281512`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140281b37`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140281062`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028115d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140281183`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1402811cd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1402811f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140281506`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140281062`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14028115d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140281183`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1402811cd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1402811f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140281506`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140281b2b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140281b2b`
- `ntoskrnl!ObfDereferenceObject` at `0x14028209e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402820e6`
- `ntoskrnl!ObfDereferenceObject` at `0x14028209e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402820e6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1402810d7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140281953`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1402810d7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140281953`
- `ntoskrnl!KeStackAttachProcess` at `0x1402810b0`
- `ntoskrnl!KeStackAttachProcess` at `0x14028192e`
- `ntoskrnl!KeStackAttachProcess` at `0x1402810b0`
- `ntoskrnl!KeStackAttachProcess` at `0x14028192e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14028200a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14028200a`
- `ntoskrnl!RtlCopyLuid` at `0x1402816b5`
- `ntoskrnl!RtlCopyLuid` at `0x1402816b5`
- `ntoskrnl!IoFileObjectType` at `0x140281fe0`
- `watchdog!WdLogSingleEntry2` at `0x140281262`
- `watchdog!WdLogSingleEntry2` at `0x1402812f6`
- `watchdog!WdLogSingleEntry2` at `0x140281262`
- `watchdog!WdLogSingleEntry2` at `0x1402812f6`
- `watchdog!WdLogSingleEntry0` at `0x140280f23`
- `watchdog!WdLogSingleEntry0` at `0x1402810ef`
- `watchdog!WdLogSingleEntry0` at `0x1402813a9`
- `watchdog!WdLogSingleEntry0` at `0x140281447`
- `watchdog!WdLogSingleEntry0` at `0x140281593`
- `watchdog!WdLogSingleEntry0` at `0x1402815f9`
- `watchdog!WdLogSingleEntry0` at `0x14028164f`
- `watchdog!WdLogSingleEntry0` at `0x14028175e`
- `watchdog!WdLogSingleEntry0` at `0x1402819d3`
- `watchdog!WdLogSingleEntry0` at `0x140281a33`
- `watchdog!WdLogSingleEntry0` at `0x140281acf`
- `watchdog!WdLogSingleEntry0` at `0x14028204f`
- `watchdog!WdLogSingleEntry0` at `0x140280f23`
- `watchdog!WdLogSingleEntry0` at `0x1402810ef`
- `watchdog!WdLogSingleEntry0` at `0x1402813a9`
- `watchdog!WdLogSingleEntry0` at `0x140281447`
- `watchdog!WdLogSingleEntry0` at `0x140281593`
- `watchdog!WdLogSingleEntry0` at `0x1402815f9`
- `watchdog!WdLogSingleEntry0` at `0x14028164f`
- `watchdog!WdLogSingleEntry0` at `0x14028175e`
- `watchdog!WdLogSingleEntry0` at `0x1402819d3`
- `watchdog!WdLogSingleEntry0` at `0x140281a33`
- `watchdog!WdLogSingleEntry0` at `0x140281acf`
- `watchdog!WdLogSingleEntry0` at `0x14028204f`
- `watchdog!WdLogSingleEntry1` at `0x14028135f`
- `watchdog!WdLogSingleEntry1` at `0x14028154a`
- `watchdog!WdLogSingleEntry1` at `0x1402816d3`
- `watchdog!WdLogSingleEntry1` at `0x140281805`
- `watchdog!WdLogSingleEntry1` at `0x140281ef2`
- `watchdog!WdLogSingleEntry1` at `0x140281f16`
- `watchdog!WdLogSingleEntry1` at `0x140281f5c`
- `watchdog!WdLogSingleEntry1` at `0x140281f7f`
- `watchdog!WdLogSingleEntry1` at `0x140281fa2`
- `watchdog!WdLogSingleEntry1` at `0x140281fc5`
- `watchdog!WdLogSingleEntry1` at `0x140282025`
- `watchdog!WdLogSingleEntry1` at `0x14028135f`
- `watchdog!WdLogSingleEntry1` at `0x14028154a`
- `watchdog!WdLogSingleEntry1` at `0x1402816d3`
- `watchdog!WdLogSingleEntry1` at `0x140281805`
- `watchdog!WdLogSingleEntry1` at `0x140281ef2`
- `watchdog!WdLogSingleEntry1` at `0x140281f16`
- `watchdog!WdLogSingleEntry1` at `0x140281f5c`
- `watchdog!WdLogSingleEntry1` at `0x140281f7f`
- `watchdog!WdLogSingleEntry1` at `0x140281fa2`
- `watchdog!WdLogSingleEntry1` at `0x140281fc5`
- `watchdog!WdLogSingleEntry1` at `0x140282025`

## string_xrefs

- `0x140282060`: `The device file handle to bind to the new vGPU has already been bound to some other object.`
- `0x140281100`: `Failed to create partitioned GPU device 0x%I64x`
- `0x1402815a4`: `pArgs->UserModeVirtualDeviceProvider == m_pVirtualGpu[pArgs->PartitionId]->UserModeDllId`
- `0x140281370`: `The PartitionId refers to a vGPU that has not yet been created: 0x%I64x`

## pseudocode

```c
__int64 __fastcall DXGVIRTUALGPUMANAGER_GPUP::CreateVirtualGpu(
        DXGVIRTUALGPUMANAGER_GPUP *this,
        struct _DXGKARG_CREATEVIRTUALGPU *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        void *a6)
{
  struct DXGPROCESS *Current; // r13
  struct DXGADAPTER *v9; // r12
  char *v10; // r14
  __int64 v11; // rbx
  __int64 StandardAllocation; // rdi
  struct _EX_PUSH_LOCK *GpuVirtualizationLock; // rax
  struct DXGDEVICE *v14; // rdi
  int v16; // eax
  unsigned int v17; // ebx
  struct _EX_PUSH_LOCK *v18; // rax
  __int64 v19; // r8
  ULONG PartitionId; // eax
  ULONG v21; // ecx
  _DWORD *v22; // r13
  DXGK_VIRTUAL_GPU_GPUP *v23; // r14
  char v24; // bl
  ULONG v25; // edx
  __int64 v26; // rbx
  DXGK_VIRTUAL_GPU_GPUP *v27; // rax
  _DWORD *v28; // rdi
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rax
  int VirtualGpu; // eax
  __int64 v33; // rdx
  __int64 NumMemorySegments; // rax
  __int64 v35; // rcx
  unsigned __int64 v36; // rdi
  __int64 v37; // rax
  bool v38; // cf
  __int64 v39; // rax
  unsigned __int64 *v40; // rax
  _QWORD *v41; // rbx
  __int64 v42; // rax
  int SavedAdapterState; // eax
  unsigned int v44; // edx
  _DWORD *v45; // rcx
  unsigned int v46; // ebx
  __int64 v47; // rdi
  DXGDEVICE *v48; // rbx
  DXGPROCESS *v49; // rdi
  unsigned int v50; // ebx
  unsigned int v51; // eax
  __int64 v52; // rdi
  int v53; // ecx
  __int64 v54; // rdi
  ULONG v55; // r9d
  __int64 v56; // rdx
  DXGPROCESS *v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rcx
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // r13
  __int64 v63; // rax
  struct VIDMM_GLOBAL *v64; // rdx
  __int64 v65; // r8
  char *v66; // r9
  __int64 v67; // rdx
  ULONG v68; // ecx
  int SegmentStatistics; // eax
  char v70; // bl
  int v71; // eax
  int v72; // eax
  int v73; // eax
  int v74; // r13d
  unsigned __int64 i; // rbx
  NTSTATUS v76; // eax
  PVOID v77; // rbx
  PVOID v78; // rcx
  int Object; // [rsp+20h] [rbp-E0h]
  unsigned int v80; // [rsp+50h] [rbp-B0h] BYREF
  DXGPROCESS *v81; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v82; // [rsp+60h] [rbp-A0h] BYREF
  DXGDEVICE *VirtualGpuDevice; // [rsp+68h] [rbp-98h]
  PVOID v84; // [rsp+70h] [rbp-90h] BYREF
  __int64 v85; // [rsp+78h] [rbp-88h]
  void *v86; // [rsp+80h] [rbp-80h]
  HANDLE Handle; // [rsp+88h] [rbp-78h]
  _BYTE v88[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v89[16]; // [rsp+A8h] [rbp-58h] BYREF
  union _LARGE_INTEGER v90; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v91[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v92[24]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v93[32]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v94[54]; // [rsp+110h] [rbp+10h] BYREF
  UINT64 Size; // [rsp+2C0h] [rbp+1C0h] BYREF
  UINT Alignment; // [rsp+2C8h] [rbp+1C8h]
  ULONG DriverSegmentId; // [rsp+2CCh] [rbp+1CCh]
  UINT PrivateDriverData; // [rsp+2D0h] [rbp+1D0h]
  int v99; // [rsp+2D4h] [rbp+1D4h]
  struct _KAPC_STATE ApcState; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v101[160]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v102[144]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _DXGKARG_SETVIRTUALGPURESOURCES v103; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v104[992]; // [rsp+468h] [rbp+368h] BYREF

  Handle = a6;
  Current = DXGPROCESS::GetCurrent();
  if ( !Current )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1368;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pProcess != nullptr", 1368, 0, 0, 0, 0);
  }
  *((_DWORD *)Current + 102) |= 0x40u;
  v85 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
  v9 = (struct DXGADAPTER *)v85;
  v81 = (DXGPROCESS *)*((_QWORD *)DXGGLOBAL::GetGlobal() + 173);
  memset(&ApcState, 0, sizeof(ApcState));
  v10 = (char *)v81 + 216;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)v81 + 216, 0);
  *((_QWORD *)v81 + 28) = KeGetCurrentThread();
  v11 = *((_QWORD *)this + 4) + 24LL;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v11, 0);
  *(_QWORD *)(v11 + 8) = KeGetCurrentThread();
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88, v9, 1u);
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v102, v9, 0);
  LODWORD(StandardAllocation) = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v102, 0);
  if ( (int)StandardAllocation < 0 )
  {
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v102);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88);
    *(_QWORD *)(v11 + 8) = 0;
    ExReleasePushLockExclusiveEx(v11, 0);
    KeLeaveCriticalRegion();
    *((_QWORD *)v10 + 1) = 0;
LABEL_7:
    ExReleasePushLockExclusiveEx(v10, 0);
    KeLeaveCriticalRegion();
    return (unsigned int)StandardAllocation;
  }
  GpuVirtualizationLock = (struct _EX_PUSH_LOCK *)DpiGetGpuVirtualizationLock(*((_QWORD *)v9 + 27));
  DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE((DXGAUTOEXPUSHLOCKEXCLUSIVE *)v93, GpuVirtualizationLock);
  KeStackAttachProcess(*((PRKPROCESS *)v81 + 7), &ApcState);
  VirtualGpuDevice = DXGPROCESS::GetVirtualGpuDevice(v81, *((struct ADAPTER_RENDER **)this + 4));
  v14 = VirtualGpuDevice;
  KeUnstackDetachProcess(&ApcState);
  if ( !VirtualGpuDevice )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 1413;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to create partitioned GPU device 0x%I64x",
      1413,
      0,
      0,
      0,
      0);
    DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v93);
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v102);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88);
    *(_QWORD *)(v11 + 8) = 0;
    ExReleasePushLockExclusiveEx(v11, 0);
    KeLeaveCriticalRegion();
    *((_QWORD *)v10 + 1) = 0;
    LODWORD(StandardAllocation) = -1073741801;
    goto LABEL_7;
  }
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v93);
  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v102);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88);
  *(_QWORD *)(v11 + 8) = 0;
  ExReleasePushLockExclusiveEx(v11, 0);
  KeLeaveCriticalRegion();
  *((_QWORD *)v10 + 1) = 0;
  ExReleasePushLockExclusiveEx(v10, 0);
  KeLeaveCriticalRegion();
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(
    (DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v89,
    v14);
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88, v9, 1u);
  LOBYTE(Object) = 0;
  COREDEVICEACCESS::COREDEVICEACCESS(v101, v14, 2);
  v16 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v101, 0);
  v17 = v16;
  if ( v16 < 0 )
  {
    WdLogSingleEntry2(3, v14, v16);
    WdLogGlobalForLineNumber = 1428;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v101);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v89);
    return v17;
  }
  v18 = (struct _EX_PUSH_LOCK *)DpiGetGpuVirtualizationLock(*(_QWORD *)(v85 + 216));
  DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE((DXGAUTOEXPUSHLOCKEXCLUSIVE *)v92, v18);
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)v91,
    (DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 40));
  if ( *((_BYTE *)DXGGLOBAL::GetGlobal() + 305637) )
  {
    PartitionId = a2->PartitionId;
    if ( a2->PartitionId == 0xFFFF )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 1521;
      LODWORD(StandardAllocation) = -1073741637;
      goto LABEL_110;
    }
    v21 = *((_DWORD *)this + 3);
    if ( PartitionId >= v21 )
    {
      WdLogSingleEntry2(2, PartitionId, v21);
      WdLogGlobalForLineNumber = 1501;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"The PartitionId supplied is greater that the number of available GPU partitions: 0x%I64x 0x%I64x",
        a2->PartitionId,
        *((unsigned int *)this + 3),
        0,
        0,
        0);
LABEL_15:
      LODWORD(StandardAllocation) = -1073741811;
LABEL_110:
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v91);
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v92);
      COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v101);
      DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88);
      DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v89);
      return (unsigned int)StandardAllocation;
    }
    v22 = 0;
    v23 = *(DXGK_VIRTUAL_GPU_GPUP **)(*((_QWORD *)this + 3) + 8LL * PartitionId);
    if ( !v23 )
    {
      WdLogSingleEntry1(2, PartitionId);
      WdLogGlobalForLineNumber = 1510;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"The PartitionId refers to a vGPU that has not yet been created: 0x%I64x",
        a2->PartitionId,
        0,
        0,
        0,
        0);
      goto LABEL_15;
    }
    v86 = 0;
    v24 = 1;
LABEL_28:
    VirtualGpu = ADAPTER_RENDER::DdiCreateVirtualGpu(*((struct DXGADAPTER ***)this + 4), a2, v19);
    LODWORD(StandardAllocation) = VirtualGpu;
    if ( VirtualGpu < 0 )
    {
      WdLogSingleEntry1(3, VirtualGpu);
      WdLogGlobalForLineNumber = 1529;
LABEL_105:
      if ( v86 )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v86);
      (*(void (__fastcall **)(DXGVIRTUALGPUMANAGER_GPUP *, DXGK_VIRTUAL_GPU_GPUP *))(*(_QWORD *)this + 24LL))(this, v23);
      goto LABEL_110;
    }
    if ( v24 )
    {
      if ( memcmp(
             &a2->UserModeVirtualDeviceProvider,
             (const void *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL * a2->PartitionId) + 36LL),
             0x10u) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1536;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"pArgs->UserModeVirtualDeviceProvider == m_pVirtualGpu[pArgs->PartitionId]->UserModeDllId",
          1536,
          0,
          0,
          0,
          0);
      }
      v33 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * a2->PartitionId);
      if ( a2->VirtualGpuLuid.LowPart != *(_DWORD *)(v33 + 28) || a2->VirtualGpuLuid.HighPart != *(_DWORD *)(v33 + 32) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1537;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"RtlEqualLuid(&pArgs->VirtualGpuLuid, &m_pVirtualGpu[pArgs->PartitionId]->VirtualGpuLuid)",
          1537,
          0,
          0,
          0,
          0);
      }
      if ( Handle )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1538;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"vGPUHandle == nullptr", 1538, 0, 0, 0, 0);
      }
    }
    else
    {
      *((_BYTE *)v23 + 192) = 1;
      *(CLSID *)((char *)v23 + 36) = a2->UserModeVirtualDeviceProvider;
      RtlCopyLuid((PLUID)((char *)v23 + 28), &a2->VirtualGpuLuid);
      NumMemorySegments = a2->NumMemorySegments;
      if ( (unsigned int)NumMemorySegments > 0x20 )
      {
        WdLogSingleEntry1(3, (unsigned int)NumMemorySegments);
        WdLogGlobalForLineNumber = 1547;
        LODWORD(StandardAllocation) = -1073741811;
        goto LABEL_105;
      }
      v35 = -1;
      if ( (_DWORD)NumMemorySegments )
      {
        v36 = a2->NumMemorySegments;
        v37 = 120 * NumMemorySegments;
        if ( !is_mul_ok(v36, 0x78u) )
          v37 = -1;
        v38 = __CFADD__(v37, 8);
        v39 = v37 + 8;
        if ( v38 )
          v39 = -1;
        v40 = (unsigned __int64 *)operator new[](v39, 1265072196, 256);
        if ( v40 )
        {
          v41 = v40 + 1;
          *v40 = v36;
          `vector constructor iterator'(
            v40 + 1,
            0x78u,
            v36,
            (void *(*)(void *))DXGK_GPUP_ALLOCATION_INFO::DXGK_GPUP_ALLOCATION_INFO);
        }
        else
        {
          v41 = 0;
        }
        *((_QWORD *)v23 + 23) = v41;
        if ( !v41 )
        {
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 1556;
          DxgkLogInternalTriageEvent(
            0,
            262145,
            -1,
            (unsigned int)L"Failed to allocate allocations array",
            1556,
            0,
            0,
            0,
            0);
          LODWORD(StandardAllocation) = -1073741801;
          goto LABEL_105;
        }
        *((_DWORD *)v23 + 42) = a2->NumMemorySegments;
      }
      if ( (unsigned __int8)DpiKsrIsSoftBoot(v35) )
      {
        v42 = *((_QWORD *)this + 4);
        v80 = 0;
        v82 = 0;
        SavedAdapterState = DpiKsrGetSavedAdapterState(*(_QWORD *)(*(_QWORD *)(v42 + 16) + 216LL), &v80, &v82);
        StandardAllocation = SavedAdapterState;
        if ( SavedAdapterState < 0 )
        {
          WdLogSingleEntry1(2, SavedAdapterState);
          WdLogGlobalForLineNumber = 1579;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to find saved GPU-P state. Status: 0x%I64x",
            StandardAllocation,
            0,
            0,
            0,
            0);
          goto LABEL_105;
        }
        if ( v82 && *(_DWORD *)v82 )
        {
          v44 = 0;
          v45 = (_DWORD *)(v82 + 4);
          while ( *v45 != a2->PartitionId )
          {
            ++v44;
            v45 = (_DWORD *)((char *)v45 + (unsigned int)v45[3]);
            if ( v44 >= *(_DWORD *)v82 )
              goto LABEL_59;
          }
          v55 = a2->NumMemorySegments;
          if ( v45[2] != v55 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 1592;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"NumMemorySegments in saved virtual function and new vGPU is different",
              1592,
              0,
              0,
              0,
              0);
            goto LABEL_105;
          }
          v56 = 0;
          v22 = v45 + 4;
          if ( v55 )
          {
            while ( v22[6 * v56] == a2->SegmentInfo[v56].DriverSegmentId
                 && *(_QWORD *)&v22[6 * v56 + 4] == a2->SegmentInfo[v56].Size
                 && v22[6 * v56 + 1] == a2->SegmentInfo[v56].Alignment )
            {
              v56 = (unsigned int)(v56 + 1);
              if ( (unsigned int)v56 >= v55 )
                goto LABEL_59;
            }
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 1602;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Segment parameters in the saved data do not match",
              1602,
              0,
              0,
              0,
              0);
            goto LABEL_105;
          }
        }
      }
LABEL_59:
      v46 = a2->NumMemorySegments;
      v47 = 0;
      v80 = 0;
      if ( v46 )
      {
        while ( 1 )
        {
          v99 = 0;
          memset(v94, 0, 0x1A8u);
          v48 = VirtualGpuDevice;
          LODWORD(v94[2]) = 5;
          LODWORD(v94[0]) = 512;
          HIDWORD(v94[0]) = *((_DWORD *)VirtualGpuDevice + 117);
          v94[3] = &Size;
          Size = a2->SegmentInfo[v47].Size;
          Alignment = a2->SegmentInfo[v47].Alignment;
          DriverSegmentId = a2->SegmentInfo[v47].DriverSegmentId;
          PrivateDriverData = a2->SegmentInfo[v47].PrivateDriverData;
          KeStackAttachProcess(*((PRKPROCESS *)v81 + 7), &ApcState);
          StandardAllocation = (int)DXGDEVICE::CreateStandardAllocation(
                                      v48,
                                      (struct _D3DKM_CREATESTANDARDALLOCATION *)v94,
                                      0);
          KeUnstackDetachProcess(&ApcState);
          if ( (int)StandardAllocation < 0 )
            break;
          v49 = v81;
          v50 = HIDWORD(v94[6]);
          DXGPUSHLOCK::AcquireShared((DXGPROCESS *)((char *)v81 + 248));
          v51 = (v50 >> 6) & 0xFFFFFF;
          if ( v51 < *((_DWORD *)v49 + 74)
            && (v52 = *((_QWORD *)v49 + 35), ((v50 >> 25) & 0x60) == (*(_BYTE *)(v52 + 16LL * v51 + 8) & 0x60))
            && (*(_DWORD *)(v52 + 16LL * v51 + 8) & 0x2000) == 0
            && (v53 = *(_DWORD *)(v52 + 16LL * v51 + 8) & 0x1F) != 0 )
          {
            if ( v53 == 5 )
            {
              v54 = *(_QWORD *)(v52 + 16LL * v51);
            }
            else
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              v54 = 0;
            }
          }
          else
          {
            v54 = 0;
          }
          v57 = v81;
          _InterlockedDecrement((volatile signed __int32 *)v81 + 66);
          ExReleasePushLockSharedEx((char *)v57 + 248, 0);
          KeLeaveCriticalRegion();
          v58 = 120LL * v80;
          v59 = v80;
          *(_QWORD *)(v58 + *((_QWORD *)v23 + 23)) = v54;
          if ( v22 )
            v60 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)VirtualGpuDevice + 2) + 760LL)
                                                                                             + 8LL)
                                                                                 + 1192LL))(
                    *(_QWORD *)(*((_QWORD *)this + 4) + 768LL),
                    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v23 + 23) + v58) + 24LL),
                    (unsigned int)v22[6 * v59],
                    *(_QWORD *)&v22[6 * v59 + 2],
                    Object);
          else
            v60 = VIDMM_EXPORT::VidMmPinAllocation(
                    *(VIDMM_EXPORT **)(*((_QWORD *)VirtualGpuDevice + 2) + 760LL),
                    *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL),
                    *(struct VIDMM_MULTI_ALLOC **)(*(_QWORD *)(*((_QWORD *)v23 + 23) + v58) + 24LL),
                    0,
                    0);
          LODWORD(StandardAllocation) = v60;
          if ( v60 < 0 )
          {
            WdLogSingleEntry1(2, v60);
            WdLogGlobalForLineNumber = 1692;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed to pin virtual GPU allocation. Status = 0x%I64x",
              (int)StandardAllocation,
              0,
              0,
              0,
              0);
            goto LABEL_105;
          }
          v47 = v80 + 1;
          *(_QWORD *)(*((_QWORD *)v23 + 23) + v58 + 16) = Size;
          v61 = *((_QWORD *)v23 + 23);
          v80 = v47;
          *(_DWORD *)(v61 + v58 + 24) = Alignment;
          v46 = a2->NumMemorySegments;
          if ( (unsigned int)v47 >= v46 )
            goto LABEL_83;
        }
        WdLogSingleEntry1(3, StandardAllocation);
        WdLogGlobalForLineNumber = 1642;
        goto LABEL_105;
      }
LABEL_83:
      memset(v103.MemoryInfo, 0, sizeof(v103.MemoryInfo));
      memset(v104, 0, sizeof(v104));
      v62 = 0;
      v103.PartitionId = a2->PartitionId;
      v103.NumMemoryAllocations = v46;
      if ( v46 )
      {
        while ( 1 )
        {
          v80 = 0;
          v90.QuadPart = 0;
          v82 = 0;
          LODWORD(v81) = *(_DWORD *)(v85 + 5300);
          memset(v94, 0, 0x98u);
          v63 = *((_QWORD *)v23 + 23);
          StandardAllocation = (__int64)VirtualGpuDevice;
          v64 = *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL);
          v84 = (PVOID)(120LL * (unsigned int)v62);
          VIDMM_EXPORT::VidMmGetPinnedAllocationInfo(
            *(VIDMM_EXPORT **)(*((_QWORD *)VirtualGpuDevice + 2) + 760LL),
            v64,
            *(struct VIDMM_MULTI_GLOBAL_ALLOC **)(*(_QWORD *)(*(_QWORD *)((char *)v84 + v63) + 48LL) + 8LL),
            &v80,
            &v90,
            &v82);
          v65 = *((_QWORD *)v23 + 23);
          v66 = (char *)v84;
          v67 = (unsigned int)v62;
          v68 = v80;
          v103.MemoryInfo[v67].DriverAllocationHandle = *(HANDLE *)(*(_QWORD *)(*(_QWORD *)((char *)v84 + v65) + 48LL)
                                                                  + 16LL);
          v103.MemoryInfo[v67].AllocationAddress.MemorySegmentOffset = v82;
          v103.MemoryInfo[v67].AllocationAddress.MemorySegmentId = v68;
          v103.MemoryInfo[v67].AllocationSize = a2->SegmentInfo[v62].Size;
          *(_DWORD *)&v66[v65 + 28] = v68;
          *(_QWORD *)&v66[*((_QWORD *)v23 + 23) + 8] = v82;
          SegmentStatistics = VIDMM_EXPORT::VidMmQuerySegmentStatistics(
                                *(VIDMM_EXPORT **)(*(_QWORD *)(StandardAllocation + 16) + 760LL),
                                *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL),
                                0,
                                v80 - 1,
                                (struct _D3DKMT_QUERYSTATISTICS_SEGMENT_INFORMATION *)v94);
          LODWORD(StandardAllocation) = SegmentStatistics;
          if ( SegmentStatistics < 0 )
            break;
          v70 = (char)v81;
          *((_BYTE *)v84 + *((_QWORD *)v23 + 23) + 112) = LODWORD(v94[5]) != 0;
          if ( (v70 & 1) != 0 && !LODWORD(v94[5]) )
          {
            v71 = DXGK_VIRTUAL_GPU_GPUP::InitializeDirtyBitplaneForAllocation(v23, v62);
            LODWORD(StandardAllocation) = v71;
            if ( v71 < 0 )
            {
              WdLogSingleEntry1(3, v71);
              WdLogGlobalForLineNumber = 1748;
              goto LABEL_105;
            }
            if ( (v70 & 2) != 0 )
            {
              v72 = DXGK_VIRTUAL_GPU_GPUP::EnableDirtyBitTrackingForAllocation(v23, v62);
              LODWORD(StandardAllocation) = v72;
              if ( v72 < 0 )
              {
                WdLogSingleEntry1(3, v72);
                WdLogGlobalForLineNumber = 1757;
                goto LABEL_105;
              }
            }
          }
          v62 = (unsigned int)(v62 + 1);
          if ( (unsigned int)v62 >= a2->NumMemorySegments )
            goto LABEL_91;
        }
        WdLogSingleEntry1(3, SegmentStatistics);
        WdLogGlobalForLineNumber = 1737;
        goto LABEL_105;
      }
LABEL_91:
      v73 = ADAPTER_RENDER::DdiSetVirtualGpuResources(*((ADAPTER_RENDER **)this + 4), &v103);
      StandardAllocation = v73;
      if ( bTracingEnabled )
      {
        v74 = v85;
        DxgkLogInternalTriageEvent(
          v85,
          196610,
          a2->PartitionId,
          (unsigned int)L"Setting vGPU resources with %1 segments returns %2",
          a2->NumMemorySegments,
          v73,
          0,
          0,
          0);
        for ( i = 0; i < a2->NumMemorySegments; ++i )
          DxgkLogInternalTriageEvent(
            v74,
            196610,
            a2->PartitionId,
            (unsigned int)L"vGPU has a resource set on segment %1 at offset %2 with a size of %3",
            v103.MemoryInfo[i].AllocationAddress.MemorySegmentId,
            v103.MemoryInfo[i].AllocationAddress.MemorySegmentOffset,
            v103.MemoryInfo[i].AllocationSize,
            0,
            0);
      }
      if ( (int)StandardAllocation < 0 )
      {
        WdLogSingleEntry1(3, StandardAllocation);
        WdLogGlobalForLineNumber = 1790;
        goto LABEL_105;
      }
      v84 = 0;
      v76 = ObReferenceObjectByHandle(Handle, 0x20000u, (POBJECT_TYPE)IoFileObjectType, 0, &v84, 0);
      LODWORD(StandardAllocation) = v76;
      if ( v76 < 0 )
      {
        WdLogSingleEntry1(3, v76);
        WdLogGlobalForLineNumber = 1800;
        goto LABEL_105;
      }
      v77 = v84;
      if ( *((_QWORD *)v84 + 4) )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 1808;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"The device file handle to bind to the new vGPU has already been bound to some other object.",
          1808,
          0,
          0,
          0,
          0);
        LODWORD(StandardAllocation) = -1073741816;
        ObfDereferenceObject(v77);
        goto LABEL_105;
      }
      v78 = v84;
      *((_QWORD *)v84 + 4) = v86;
      *((_QWORD *)v23 + 20) = v77;
      ObfDereferenceObject(v78);
    }
    DXGK_VIRTUAL_GPU::ReportState(v23);
    LODWORD(StandardAllocation) = 0;
    goto LABEL_110;
  }
  v25 = a2->PartitionId;
  v80 = 0xFFFF;
  LODWORD(StandardAllocation) = DXGVIRTUALGPUMANAGER::GetTargetPartitionId(this, v25, &v80);
  if ( (int)StandardAllocation < 0 )
    goto LABEL_110;
  v26 = v80;
  a2->PartitionId = v80;
  v27 = (DXGK_VIRTUAL_GPU_GPUP *)operator new(360, 1265072196, 256);
  if ( v27 )
  {
    v23 = DXGK_VIRTUAL_GPU_GPUP::DXGK_VIRTUAL_GPU_GPUP(v27, *((struct ADAPTER_RENDER **)this + 4));
    if ( v23 )
    {
      v86 = (void *)operator new(16, 1265072196, 256);
      v28 = v86;
      if ( !v86 )
      {
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 1475;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Not enough memory to allocate the DXGSHAREDVGPUOBJECT for handle tracking.",
          1475,
          0,
          0,
          0,
          0);
        (**(void (__fastcall ***)(DXGK_VIRTUAL_GPU_GPUP *, __int64))v23)(v23, 1);
        LODWORD(StandardAllocation) = -1073741801;
        goto LABEL_110;
      }
      *((_QWORD *)v23 + 22) = VirtualGpuDevice;
      *((_QWORD *)v23 + 11) = Current;
      *((_DWORD *)v23 + 6) = v26;
      *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v26) = v23;
      ++*((_DWORD *)this + 4);
      DXGPUSHLOCK::AcquireExclusive((DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 72));
      v29 = (_QWORD *)((char *)this + 104);
      v30 = *((_QWORD *)this + 13);
      if ( *(DXGVIRTUALGPUMANAGER_GPUP **)(v30 + 8) != (DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 104) )
        __fastfail(3u);
      *((_QWORD *)v23 + 15) = v30;
      *((_QWORD *)v23 + 16) = v29;
      *(_QWORD *)(v30 + 8) = (char *)v23 + 120;
      *v29 = (char *)v23 + 120;
      *((_QWORD *)this + 10) = 0;
      ExReleasePushLockExclusiveEx((char *)this + 72, 0);
      KeLeaveCriticalRegion();
      v31 = v85;
      v22 = 0;
      v28[2] = v26;
      v24 = 0;
      *(_QWORD *)v28 = v31;
      goto LABEL_28;
    }
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v91);
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v92);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v101);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v88);
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v89);
  return 3221225495LL;
}

```

## disassembly

```asm
0x140280ed0  mov     [rsp-8+arg_10], rbx
0x140280ed5  push    rbp
0x140280ed6  push    rsi
0x140280ed7  push    rdi
0x140280ed8  push    r12
0x140280eda  push    r13
0x140280edc  push    r14
0x140280ede  push    r15
0x140280ee0  lea     rbp, [rsp-760h]
0x140280ee8  sub     rsp, 860h
0x140280eef  mov     rax, cs:__security_cookie
0x140280ef6  xor     rax, rsp
0x140280ef9  mov     [rbp+790h+var_40], rax
0x140280f00  mov     rax, [rbp+790h+arg_28]
0x140280f07  mov     rsi, rdx
0x140280f0a  mov     [rbp+790h+Handle], rax
0x140280f0e  mov     r15, rcx
0x140280f11  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140280f16  xor     ebx, ebx
0x140280f18  mov     r13, rax
0x140280f1b  test    rax, rax
0x140280f1e  jnz     short loc_140280F6A
0x140280f20  lea     ecx, [rax+1]
0x140280f23  call    cs:__imp_WdLogSingleEntry0
0x140280f2a  nop     dword ptr [rax+rax+00h]
0x140280f2f  mov     [rsp+890h+var_850], rbx
0x140280f34  lea     r9, aPprocessNullpt; "pProcess != nullptr"
0x140280f3b  mov     [rsp+890h+var_858], rbx
0x140280f40  mov     eax, 558h
0x140280f45  mov     [rsp+890h+var_860], rbx
0x140280f4a  or      r8d, 0FFFFFFFFh
0x140280f4e  mov     [rsp+890h+HandleInformation], rbx
0x140280f53  mov     edx, 40002h
0x140280f58  xor     ecx, ecx
0x140280f5a  mov     [rsp+890h+Object], rax
0x140280f5f  mov     cs:WdLogGlobalForLineNumber, eax
0x140280f65  call    DxgkLogInternalTriageEvent
0x140280f6a  or      dword ptr [r13+198h], 40h
0x140280f72  mov     rax, [r15+20h]
0x140280f76  mov     r12, [rax+10h]
0x140280f7a  mov     [rsp+890h+var_818], r12
0x140280f7f  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140280f84  xorps   xmm0, xmm0
0x140280f87  mov     rax, [rax+568h]
0x140280f8e  mov     [rsp+890h+var_838], rax
0x140280f93  movups  xmmword ptr [rbp+790h+ApcState.ApcListHead.Flink], xmm0
0x140280f9a  lea     r14, [rax+0D8h]
0x140280fa1  movups  xmmword ptr [rbp+790h+ApcState.ApcListHead.Flink+10h], xmm0
0x140280fa8  movups  xmmword ptr [rbp+790h+ApcState.Process], xmm0
0x140280faf  call    cs:__imp_KeEnterCriticalRegion
0x140280fb6  nop     dword ptr [rax+rax+00h]
0x140280fbb  xor     edx, edx
0x140280fbd  mov     rcx, r14
0x140280fc0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140280fc7  nop     dword ptr [rax+rax+00h]
0x140280fcc  mov     rax, gs:188h
0x140280fd5  mov     [r14+8], rax
0x140280fd9  mov     rbx, [r15+20h]
0x140280fdd  add     rbx, 18h
0x140280fe1  call    cs:__imp_KeEnterCriticalRegion
0x140280fe8  nop     dword ptr [rax+rax+00h]
0x140280fed  xor     edx, edx
0x140280fef  mov     rcx, rbx
0x140280ff2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140280ff9  nop     dword ptr [rax+rax+00h]
0x140280ffe  mov     rax, gs:188h
0x140281007  lea     rcx, [rbp+790h+var_800]; this
0x14028100b  mov     r8b, 1; unsigned __int8
0x14028100e  mov     [rbx+8], rax
0x140281012  mov     rdx, r12; struct DXGADAPTER *
0x140281015  call    ??0DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@PEAVDXGADAPTER@@E@Z; DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(DXGADAPTER *,uchar)
0x14028101a  xor     r8d, r8d; struct DXGADAPTER *
0x14028101d  lea     rcx, [rbp+790h+var_4E0]; this
0x140281024  mov     rdx, r12; struct DXGADAPTER *
0x140281027  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x14028102c  xor     edx, edx; char *
0x14028102e  lea     rcx, [rbp+790h+var_4E0]; this
0x140281035  call    ?AcquireShared@COREADAPTERACCESS@@QEAAJPEBD@Z; COREADAPTERACCESS::AcquireShared(char const *)
0x14028103a  mov     edi, eax
0x14028103c  test    eax, eax
0x14028103e  jns     short loc_140281087
0x140281040  lea     rcx, [rbp+790h+var_4E0]; this
0x140281047  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x14028104c  lea     rcx, [rbp+790h+var_800]; this
0x140281050  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x140281055  xor     edx, edx
0x140281057  mov     qword ptr [rbx+8], 0
0x14028105f  mov     rcx, rbx
0x140281062  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140281069  nop     dword ptr [rax+rax+00h]
0x14028106e  call    cs:__imp_KeLeaveCriticalRegion
0x140281075  nop     dword ptr [rax+rax+00h]
0x14028107a  mov     qword ptr [r14+8], 0
0x140281082  jmp     loc_14028117E
0x140281087  mov     rcx, [r12+0D8h]
0x14028108f  call    DpiGetGpuVirtualizationLock
0x140281094  mov     rdx, rax; struct _EX_PUSH_LOCK *
0x140281097  lea     rcx, [rbp+790h+var_7A0]; this
0x14028109b  call    ??0DXGAUTOEXPUSHLOCKEXCLUSIVE@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(_EX_PUSH_LOCK * const)
0x1402810a0  mov     rdi, [rsp+890h+var_838]
0x1402810a5  lea     rdx, [rbp+790h+ApcState]; ApcState
0x1402810ac  mov     rcx, [rdi+38h]; PROCESS
0x1402810b0  call    cs:__imp_KeStackAttachProcess
0x1402810b7  nop     dword ptr [rax+rax+00h]
0x1402810bc  mov     rdx, [r15+20h]; struct ADAPTER_RENDER *
0x1402810c0  mov     rcx, rdi; this
0x1402810c3  call    ?GetVirtualGpuDevice@DXGPROCESS@@QEAAPEAVDXGDEVICE@@PEAVADAPTER_RENDER@@@Z; DXGPROCESS::GetVirtualGpuDevice(ADAPTER_RENDER *)
0x1402810c8  lea     rcx, [rbp+790h+ApcState]; ApcState
0x1402810cf  mov     [rsp+890h+var_828], rax
0x1402810d4  mov     rdi, rax
0x1402810d7  call    cs:__imp_KeUnstackDetachProcess
0x1402810de  nop     dword ptr [rax+rax+00h]
0x1402810e3  test    rdi, rdi
0x1402810e6  jnz     loc_1402811A2
0x1402810ec  lea     ecx, [rdi+2]
0x1402810ef  call    cs:__imp_WdLogSingleEntry0
0x1402810f6  nop     dword ptr [rax+rax+00h]
0x1402810fb  mov     [rsp+890h+var_850], rdi
0x140281100  lea     r9, aFailedToCreate_52; "Failed to create partitioned GPU device"...
0x140281107  mov     [rsp+890h+var_858], rdi
0x14028110c  mov     eax, 585h
0x140281111  mov     [rsp+890h+var_860], rdi
0x140281116  or      r8d, 0FFFFFFFFh
0x14028111a  mov     [rsp+890h+HandleInformation], rdi
0x14028111f  mov     edx, 40000h
0x140281124  xor     ecx, ecx
0x140281126  mov     [rsp+890h+Object], rax
0x14028112b  mov     cs:WdLogGlobalForLineNumber, eax
0x140281131  call    DxgkLogInternalTriageEvent
0x140281136  lea     rcx, [rbp+790h+var_7A0]; this
0x14028113a  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x14028113f  lea     rcx, [rbp+790h+var_4E0]; this
0x140281146  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x14028114b  lea     rcx, [rbp+790h+var_800]; this
0x14028114f  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x140281154  xor     edx, edx
0x140281156  mov     [rbx+8], rdi
0x14028115a  mov     rcx, rbx
0x14028115d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140281164  nop     dword ptr [rax+rax+00h]
0x140281169  call    cs:__imp_KeLeaveCriticalRegion
0x140281170  nop     dword ptr [rax+rax+00h]
0x140281175  mov     [r14+8], rdi
0x140281179  mov     edi, 0C0000017h
0x14028117e  xor     edx, edx
0x140281180  mov     rcx, r14
0x140281183  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14028118a  nop     dword ptr [rax+rax+00h]
0x14028118f  call    cs:__imp_KeLeaveCriticalRegion
0x140281196  nop     dword ptr [rax+rax+00h]
0x14028119b  mov     eax, edi
0x14028119d  jmp     loc_140282167
0x1402811a2  lea     rcx, [rbp+790h+var_7A0]; this
0x1402811a6  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1402811ab  lea     rcx, [rbp+790h+var_4E0]; this
0x1402811b2  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x1402811b7  lea     rcx, [rbp+790h+var_800]; this
0x1402811bb  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1402811c0  xor     edx, edx
0x1402811c2  mov     qword ptr [rbx+8], 0
0x1402811ca  mov     rcx, rbx
0x1402811cd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1402811d4  nop     dword ptr [rax+rax+00h]
0x1402811d9  call    cs:__imp_KeLeaveCriticalRegion
0x1402811e0  nop     dword ptr [rax+rax+00h]
0x1402811e5  xor     edx, edx
0x1402811e7  mov     qword ptr [r14+8], 0
0x1402811ef  mov     rcx, r14
0x1402811f2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1402811f9  nop     dword ptr [rax+rax+00h]
0x1402811fe  call    cs:__imp_KeLeaveCriticalRegion
0x140281205  nop     dword ptr [rax+rax+00h]
0x14028120a  mov     rdx, rdi; struct DXGDEVICE *
0x14028120d  lea     rcx, [rbp+790h+var_7E8]; this
0x140281211  call    ??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)
0x140281216  mov     r8b, 1; unsigned __int8
0x140281219  lea     rcx, [rbp+790h+var_800]; this
0x14028121d  mov     rdx, r12; struct DXGADAPTER *
0x140281220  call    ??0DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@PEAVDXGADAPTER@@E@Z; DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(DXGADAPTER *,uchar)
0x140281225  xor     r14d, r14d
0x140281228  lea     rcx, [rbp+790h+var_580]
0x14028122f  mov     rdx, rdi
0x140281232  mov     byte ptr [rsp+890h+Object], r14b
0x140281237  lea     r12d, [r14+2]
0x14028123b  mov     r8d, r12d
0x14028123e  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x140281243  xor     edx, edx; char *
0x140281245  lea     rcx, [rbp+790h+var_580]; this
0x14028124c  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x140281251  movsxd  rbx, eax
0x140281254  test    eax, eax
0x140281256  jns     short loc_14028129D
0x140281258  mov     r8, rbx
0x14028125b  lea     ecx, [r14+3]
0x14028125f  mov     rdx, rdi
0x140281262  call    cs:__imp_WdLogSingleEntry2
0x140281269  nop     dword ptr [rax+rax+00h]
0x14028126e  lea     rcx, [rbp+790h+var_580]; this
0x140281275  mov     cs:WdLogGlobalForLineNumber, 594h
0x14028127f  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x140281284  lea     rcx, [rbp+790h+var_800]; this
0x140281288  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x14028128d  lea     rcx, [rbp+790h+var_7E8]; this
0x140281291  call    ??1DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@XZ; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL(void)
0x140281296  mov     eax, ebx
0x140281298  jmp     loc_140282167
0x14028129d  mov     rcx, [rsp+890h+var_818]
0x1402812a2  mov     rcx, [rcx+0D8h]
0x1402812a9  call    DpiGetGpuVirtualizationLock
0x1402812ae  mov     rdx, rax; struct _EX_PUSH_LOCK *
0x1402812b1  lea     rcx, [rbp+790h+var_7B8]; this
0x1402812b5  call    ??0DXGAUTOEXPUSHLOCKEXCLUSIVE@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(_EX_PUSH_LOCK * const)
0x1402812ba  lea     rdx, [r15+28h]; struct DXGPUSHLOCK *
0x1402812be  lea     rcx, [rbp+790h+var_7D0]; this
0x1402812c2  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1402812c7  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1402812cc  cmp     [rax+4A9E5h], r14b
0x1402812d3  jz      loc_1402813C9
0x1402812d9  mov     eax, [rsi]
0x1402812db  cmp     eax, 0FFFFh
0x1402812e0  jz      loc_1402813A4
0x1402812e6  mov     ecx, [r15+0Ch]
0x1402812ea  mov     edx, eax
0x1402812ec  cmp     eax, ecx
0x1402812ee  jb      short loc_14028134C
0x1402812f0  mov     r8d, ecx
0x1402812f3  mov     ecx, r12d
0x1402812f6  call    cs:__imp_WdLogSingleEntry2
0x1402812fd  nop     dword ptr [rax+rax+00h]
0x140281302  mov     [rsp+890h+var_850], r14
0x140281307  lea     r9, aThePartitionid_0; "The PartitionId supplied is greater tha"...
0x14028130e  mov     [rsp+890h+var_858], r14
0x140281313  mov     cs:WdLogGlobalForLineNumber, 5DDh
0x14028131d  mov     eax, [r15+0Ch]
0x140281321  mov     ecx, [rsi]
0x140281323  mov     [rsp+890h+var_860], r14
0x140281328  mov     [rsp+890h+HandleInformation], rax
0x14028132d  mov     [rsp+890h+Object], rcx
0x140281332  or      r8d, 0FFFFFFFFh
0x140281336  mov     edx, 40000h
0x14028133b  xor     ecx, ecx
0x14028133d  call    DxgkLogInternalTriageEvent
0x140281342  mov     edi, 0C000000Dh
0x140281347  jmp     loc_1402820FD
0x14028134c  mov     rax, [r15+18h]
0x140281350  xor     r13d, r13d
0x140281353  mov     r14, [rax+rdx*8]
0x140281357  test    r14, r14
0x14028135a  jnz     short loc_140281399
0x14028135c  mov     ecx, r12d
0x14028135f  call    cs:__imp_WdLogSingleEntry1
0x140281366  nop     dword ptr [rax+rax+00h]
0x14028136b  mov     [rsp+890h+var_850], r13
0x140281370  lea     r9, aThePartitionid; "The PartitionId refers to a vGPU that h"...
0x140281377  mov     [rsp+890h+var_858], r13
0x14028137c  mov     [rsp+890h+var_860], r13
0x140281381  mov     cs:WdLogGlobalForLineNumber, 5E6h
0x14028138b  mov     eax, [rsi]
0x14028138d  mov     [rsp+890h+HandleInformation], r13
0x140281392  mov     [rsp+890h+Object], rax
0x140281397  jmp     short loc_140281332
0x140281399  mov     [rbp+790h+var_810], r13
0x14028139d  mov     bl, 1
0x14028139f  jmp     loc_14028152F
0x1402813a4  mov     ecx, 3
0x1402813a9  call    cs:__imp_WdLogSingleEntry0
0x1402813b0  nop     dword ptr [rax+rax+00h]
0x1402813b5  mov     cs:WdLogGlobalForLineNumber, 5F1h
0x1402813bf  mov     edi, 0C00000BBh
0x1402813c4  jmp     loc_1402820FD
0x1402813c9  mov     edx, [rsi]; unsigned int
0x1402813cb  lea     r8, [rsp+890h+var_840]; unsigned int *
0x1402813d0  mov     rcx, r15; this
0x1402813d3  mov     [rsp+890h+var_840], 0FFFFh
0x1402813db  call    ?GetTargetPartitionId@DXGVIRTUALGPUMANAGER@@QEAAJIPEAI@Z; DXGVIRTUALGPUMANAGER::GetTargetPartitionId(uint,uint *)
0x1402813e0  mov     edi, eax
0x1402813e2  test    eax, eax
0x1402813e4  js      loc_1402820FD
0x1402813ea  mov     ebx, [rsp+890h+var_840]
0x1402813ee  mov     edi, 100h
0x1402813f3  mov     r8d, edi
0x1402813f6  mov     [rsi], ebx
0x1402813f8  mov     edx, 4B677844h
0x1402813fd  lea     ecx, [rdi+68h]
0x140281400  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140281405  test    rax, rax
0x140281408  jz      loc_140282132
0x14028140e  mov     rdx, [r15+20h]; struct ADAPTER_RENDER *
0x140281412  mov     rcx, rax; this
0x140281415  call    ??0DXGK_VIRTUAL_GPU_GPUP@@QEAA@PEAVADAPTER_RENDER@@@Z; DXGK_VIRTUAL_GPU_GPUP::DXGK_VIRTUAL_GPU_GPUP(ADAPTER_RENDER *)
0x14028141a  mov     r14, rax
0x14028141d  test    rax, rax
0x140281420  jz      loc_140282132
0x140281426  mov     r8d, edi
0x140281429  mov     edx, 4B677844h
0x14028142e  mov     ecx, 10h
0x140281433  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140281438  mov     [rbp+790h+var_810], rax
0x14028143c  mov     rdi, rax
0x14028143f  test    rax, rax
  ... truncated ...
```
