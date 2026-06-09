# DXGVIRTUALGPUMANAGER_GPUP::CreateVirtualGpu(_DXGKARG_CREATEVIRTUALGPU *,uchar,uchar,uchar,void *)

- ea: `0x140280ed0`
- end: `0x140282192`
- name: `?CreateVirtualGpu@DXGVIRTUALGPUMANAGER_GPUP@@UEAAJPEAU_DXGKARG_CREATEVIRTUALGPU@@EEEPEAX@Z`
- size: `4802`
- prototype: `__int64 __usercall@<rax>(DXGVIRTUALGPUMANAGER_GPUP *__hidden this@<rcx>, struct _DXGKARG_CREATEVIRTUALGPU *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, unsigned __int8, void *)`
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
  __int64 v12; // rdi
  struct _EX_PUSH_LOCK *GpuVirtualizationLock; // rax
  struct DXGDEVICE *v14; // rdi
  int v16; // ebx
  struct _EX_PUSH_LOCK *v17; // rax
  ULONG PartitionId; // eax
  _DWORD *v19; // r13
  DXGK_VIRTUAL_GPU_GPUP *v20; // r14
  char v21; // bl
  ULONG v22; // edx
  __int64 v23; // rbx
  DXGK_VIRTUAL_GPU_GPUP *v24; // rax
  _DWORD *v25; // rdi
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 NumMemorySegments; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rdi
  __int64 v33; // rax
  bool v34; // cf
  __int64 v35; // rax
  unsigned __int64 *v36; // rax
  _QWORD *v37; // rbx
  __int64 v38; // rax
  int SavedAdapterState; // eax
  unsigned int v40; // edx
  _DWORD *v41; // rcx
  unsigned int v42; // ebx
  DXGDEVICE *v43; // rbx
  DXGPROCESS *v44; // rdi
  unsigned int v45; // ebx
  unsigned int v46; // eax
  __int64 v47; // rdi
  int v48; // ecx
  __int64 v49; // rdi
  ULONG v50; // r9d
  __int64 v51; // rdx
  DXGPROCESS *v52; // rax
  __int64 v53; // rbx
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // r13
  __int64 v58; // rax
  struct VIDMM_GLOBAL *v59; // rdx
  __int64 v60; // r8
  char *v61; // r9
  __int64 v62; // rdx
  ULONG v63; // ecx
  char v64; // bl
  int v65; // eax
  int v66; // r13d
  unsigned __int64 i; // rbx
  PVOID v68; // rbx
  PVOID v69; // rcx
  int Object; // [rsp+20h] [rbp-E0h]
  unsigned int v71; // [rsp+50h] [rbp-B0h] BYREF
  DXGPROCESS *v72; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v73; // [rsp+60h] [rbp-A0h] BYREF
  DXGDEVICE *VirtualGpuDevice; // [rsp+68h] [rbp-98h]
  PVOID v75; // [rsp+70h] [rbp-90h] BYREF
  __int64 v76; // [rsp+78h] [rbp-88h]
  void *v77; // [rsp+80h] [rbp-80h]
  HANDLE Handle; // [rsp+88h] [rbp-78h]
  _BYTE v79[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v80[16]; // [rsp+A8h] [rbp-58h] BYREF
  union _LARGE_INTEGER v81; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v82[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v83[24]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v84[32]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v85[54]; // [rsp+110h] [rbp+10h] BYREF
  UINT64 Size; // [rsp+2C0h] [rbp+1C0h] BYREF
  UINT Alignment; // [rsp+2C8h] [rbp+1C8h]
  ULONG DriverSegmentId; // [rsp+2CCh] [rbp+1CCh]
  UINT PrivateDriverData; // [rsp+2D0h] [rbp+1D0h]
  int v90; // [rsp+2D4h] [rbp+1D4h]
  struct _KAPC_STATE ApcState; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v92[160]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v93[144]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _DXGKARG_SETVIRTUALGPURESOURCES v94; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v95[992]; // [rsp+468h] [rbp+368h] BYREF

  Handle = a6;
  Current = DXGPROCESS::GetCurrent();
  if ( !Current )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1368;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pProcess != nullptr", 1368, 0, 0, 0, 0);
  }
  *((_DWORD *)Current + 102) |= 0x40u;
  v76 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL);
  v9 = (struct DXGADAPTER *)v76;
  v72 = (DXGPROCESS *)*((_QWORD *)DXGGLOBAL::GetGlobal() + 173);
  memset(&ApcState, 0, sizeof(ApcState));
  v10 = (char *)v72 + 216;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)v72 + 216, 0);
  *((_QWORD *)v72 + 28) = KeGetCurrentThread();
  v11 = *((_QWORD *)this + 4) + 24LL;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v11, 0);
  *(_QWORD *)(v11 + 8) = KeGetCurrentThread();
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79, v9, 1u);
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v93, v9, 0);
  LODWORD(v12) = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v93, 0);
  if ( (int)v12 < 0 )
  {
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v93);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79);
    *(_QWORD *)(v11 + 8) = 0;
    ExReleasePushLockExclusiveEx(v11, 0);
    KeLeaveCriticalRegion();
    *((_QWORD *)v10 + 1) = 0;
LABEL_7:
    ExReleasePushLockExclusiveEx(v10, 0);
    KeLeaveCriticalRegion();
    return (unsigned int)v12;
  }
  GpuVirtualizationLock = (struct _EX_PUSH_LOCK *)DpiGetGpuVirtualizationLock(*((_QWORD *)v9 + 27));
  DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE((DXGAUTOEXPUSHLOCKEXCLUSIVE *)v84, GpuVirtualizationLock);
  KeStackAttachProcess(*((PRKPROCESS *)v72 + 7), &ApcState);
  VirtualGpuDevice = DXGPROCESS::GetVirtualGpuDevice(v72, *((struct ADAPTER_RENDER **)this + 4));
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
    DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v84);
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v93);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79);
    *(_QWORD *)(v11 + 8) = 0;
    ExReleasePushLockExclusiveEx(v11, 0);
    KeLeaveCriticalRegion();
    *((_QWORD *)v10 + 1) = 0;
    LODWORD(v12) = -1073741801;
    goto LABEL_7;
  }
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v84);
  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v93);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79);
  *(_QWORD *)(v11 + 8) = 0;
  ExReleasePushLockExclusiveEx(v11, 0);
  KeLeaveCriticalRegion();
  *((_QWORD *)v10 + 1) = 0;
  ExReleasePushLockExclusiveEx(v10, 0);
  KeLeaveCriticalRegion();
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(
    (DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80,
    v14);
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79, v9, 1u);
  LOBYTE(Object) = 0;
  COREDEVICEACCESS::COREDEVICEACCESS(v92, v14, 2);
  v16 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v92, 0);
  if ( v16 < 0 )
  {
    WdLogSingleEntry2(3, v14);
    WdLogGlobalForLineNumber = 1428;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v92);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
    return (unsigned int)v16;
  }
  v17 = (struct _EX_PUSH_LOCK *)DpiGetGpuVirtualizationLock(*(_QWORD *)(v76 + 216));
  DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE((DXGAUTOEXPUSHLOCKEXCLUSIVE *)v83, v17);
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)v82,
    (DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 40));
  if ( *((_BYTE *)DXGGLOBAL::GetGlobal() + 305637) )
  {
    PartitionId = a2->PartitionId;
    if ( a2->PartitionId == 0xFFFF )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 1521;
      LODWORD(v12) = -1073741637;
      goto LABEL_110;
    }
    if ( PartitionId >= *((_DWORD *)this + 3) )
    {
      WdLogSingleEntry2(2, PartitionId);
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
      LODWORD(v12) = -1073741811;
LABEL_110:
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v82);
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v83);
      COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v92);
      DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79);
      DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
      return (unsigned int)v12;
    }
    v19 = 0;
    v20 = *(DXGK_VIRTUAL_GPU_GPUP **)(*((_QWORD *)this + 3) + 8LL * PartitionId);
    if ( !v20 )
    {
      WdLogSingleEntry1(2);
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
    v77 = 0;
    v21 = 1;
LABEL_28:
    LODWORD(v12) = ADAPTER_RENDER::DdiCreateVirtualGpu(*((ADAPTER_RENDER **)this + 4), a2);
    if ( (int)v12 < 0 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 1529;
LABEL_105:
      if ( v77 )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v77);
      (*(void (__fastcall **)(DXGVIRTUALGPUMANAGER_GPUP *, DXGK_VIRTUAL_GPU_GPUP *))(*(_QWORD *)this + 24LL))(this, v20);
      goto LABEL_110;
    }
    if ( v21 )
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
      v29 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * a2->PartitionId);
      if ( a2->VirtualGpuLuid.LowPart != *(_DWORD *)(v29 + 28) || a2->VirtualGpuLuid.HighPart != *(_DWORD *)(v29 + 32) )
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
      *((_BYTE *)v20 + 192) = 1;
      *(CLSID *)((char *)v20 + 36) = a2->UserModeVirtualDeviceProvider;
      RtlCopyLuid((PLUID)((char *)v20 + 28), &a2->VirtualGpuLuid);
      NumMemorySegments = a2->NumMemorySegments;
      if ( (unsigned int)NumMemorySegments > 0x20 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1547;
        LODWORD(v12) = -1073741811;
        goto LABEL_105;
      }
      v31 = -1;
      if ( (_DWORD)NumMemorySegments )
      {
        v32 = a2->NumMemorySegments;
        v33 = 120 * NumMemorySegments;
        if ( !is_mul_ok(v32, 0x78u) )
          v33 = -1;
        v34 = __CFADD__(v33, 8);
        v35 = v33 + 8;
        if ( v34 )
          v35 = -1;
        v36 = (unsigned __int64 *)operator new[](v35, 1265072196, 256);
        if ( v36 )
        {
          v37 = v36 + 1;
          *v36 = v32;
          `vector constructor iterator'(
            v36 + 1,
            0x78u,
            v32,
            (void *(*)(void *))DXGK_GPUP_ALLOCATION_INFO::DXGK_GPUP_ALLOCATION_INFO);
        }
        else
        {
          v37 = 0;
        }
        *((_QWORD *)v20 + 23) = v37;
        if ( !v37 )
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
          LODWORD(v12) = -1073741801;
          goto LABEL_105;
        }
        *((_DWORD *)v20 + 42) = a2->NumMemorySegments;
      }
      if ( (unsigned __int8)DpiKsrIsSoftBoot(v31) )
      {
        v38 = *((_QWORD *)this + 4);
        v71 = 0;
        v73 = 0;
        SavedAdapterState = DpiKsrGetSavedAdapterState(*(_QWORD *)(*(_QWORD *)(v38 + 16) + 216LL), &v71, &v73);
        v12 = SavedAdapterState;
        if ( SavedAdapterState < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1579;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to find saved GPU-P state. Status: 0x%I64x",
            v12,
            0,
            0,
            0,
            0);
          goto LABEL_105;
        }
        if ( v73 && *(_DWORD *)v73 )
        {
          v40 = 0;
          v41 = (_DWORD *)(v73 + 4);
          while ( *v41 != a2->PartitionId )
          {
            ++v40;
            v41 = (_DWORD *)((char *)v41 + (unsigned int)v41[3]);
            if ( v40 >= *(_DWORD *)v73 )
              goto LABEL_59;
          }
          v50 = a2->NumMemorySegments;
          if ( v41[2] != v50 )
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
          v51 = 0;
          v19 = v41 + 4;
          if ( v50 )
          {
            while ( v19[6 * v51] == a2->SegmentInfo[v51].DriverSegmentId
                 && *(_QWORD *)&v19[6 * v51 + 4] == a2->SegmentInfo[v51].Size
                 && v19[6 * v51 + 1] == a2->SegmentInfo[v51].Alignment )
            {
              v51 = (unsigned int)(v51 + 1);
              if ( (unsigned int)v51 >= v50 )
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
      v42 = a2->NumMemorySegments;
      v12 = 0;
      v71 = 0;
      if ( v42 )
      {
        while ( 1 )
        {
          v90 = 0;
          memset(v85, 0, 0x1A8u);
          v43 = VirtualGpuDevice;
          LODWORD(v85[2]) = 5;
          LODWORD(v85[0]) = 512;
          HIDWORD(v85[0]) = *((_DWORD *)VirtualGpuDevice + 117);
          v85[3] = &Size;
          Size = a2->SegmentInfo[v12].Size;
          Alignment = a2->SegmentInfo[v12].Alignment;
          DriverSegmentId = a2->SegmentInfo[v12].DriverSegmentId;
          PrivateDriverData = a2->SegmentInfo[v12].PrivateDriverData;
          KeStackAttachProcess(*((PRKPROCESS *)v72 + 7), &ApcState);
          LODWORD(v12) = DXGDEVICE::CreateStandardAllocation(v43, (struct _D3DKM_CREATESTANDARDALLOCATION *)v85, 0);
          KeUnstackDetachProcess(&ApcState);
          if ( (int)v12 < 0 )
            break;
          v44 = v72;
          v45 = HIDWORD(v85[6]);
          DXGPUSHLOCK::AcquireShared((DXGPROCESS *)((char *)v72 + 248));
          v46 = (v45 >> 6) & 0xFFFFFF;
          if ( v46 < *((_DWORD *)v44 + 74)
            && (v47 = *((_QWORD *)v44 + 35), ((v45 >> 25) & 0x60) == (*(_BYTE *)(v47 + 16LL * v46 + 8) & 0x60))
            && (*(_DWORD *)(v47 + 16LL * v46 + 8) & 0x2000) == 0
            && (v48 = *(_DWORD *)(v47 + 16LL * v46 + 8) & 0x1F) != 0 )
          {
            if ( v48 == 5 )
            {
              v49 = *(_QWORD *)(v47 + 16LL * v46);
            }
            else
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              v49 = 0;
            }
          }
          else
          {
            v49 = 0;
          }
          v52 = v72;
          _InterlockedDecrement((volatile signed __int32 *)v72 + 66);
          ExReleasePushLockSharedEx((char *)v52 + 248, 0);
          KeLeaveCriticalRegion();
          v53 = 120LL * v71;
          v54 = v71;
          *(_QWORD *)(v53 + *((_QWORD *)v20 + 23)) = v49;
          if ( v19 )
            v55 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)VirtualGpuDevice + 2) + 760LL)
                                                                                             + 8LL)
                                                                                 + 1192LL))(
                    *(_QWORD *)(*((_QWORD *)this + 4) + 768LL),
                    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v20 + 23) + v53) + 24LL),
                    (unsigned int)v19[6 * v54],
                    *(_QWORD *)&v19[6 * v54 + 2],
                    Object);
          else
            v55 = VIDMM_EXPORT::VidMmPinAllocation(
                    *(VIDMM_EXPORT **)(*((_QWORD *)VirtualGpuDevice + 2) + 760LL),
                    *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL),
                    *(struct VIDMM_MULTI_ALLOC **)(*(_QWORD *)(*((_QWORD *)v20 + 23) + v53) + 24LL),
                    0,
                    0);
          LODWORD(v12) = v55;
          if ( v55 < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1692;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Failed to pin virtual GPU allocation. Status = 0x%I64x",
              (int)v12,
              0,
              0,
              0,
              0);
            goto LABEL_105;
          }
          v12 = v71 + 1;
          *(_QWORD *)(*((_QWORD *)v20 + 23) + v53 + 16) = Size;
          v56 = *((_QWORD *)v20 + 23);
          v71 = v12;
          *(_DWORD *)(v56 + v53 + 24) = Alignment;
          v42 = a2->NumMemorySegments;
          if ( (unsigned int)v12 >= v42 )
            goto LABEL_83;
        }
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1642;
        goto LABEL_105;
      }
LABEL_83:
      memset(v94.MemoryInfo, 0, sizeof(v94.MemoryInfo));
      memset(v95, 0, sizeof(v95));
      v57 = 0;
      v94.PartitionId = a2->PartitionId;
      v94.NumMemoryAllocations = v42;
      if ( v42 )
      {
        while ( 1 )
        {
          v71 = 0;
          v81.QuadPart = 0;
          v73 = 0;
          LODWORD(v72) = *(_DWORD *)(v76 + 5300);
          memset(v85, 0, 0x98u);
          v58 = *((_QWORD *)v20 + 23);
          v12 = (__int64)VirtualGpuDevice;
          v59 = *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL);
          v75 = (PVOID)(120LL * (unsigned int)v57);
          VIDMM_EXPORT::VidMmGetPinnedAllocationInfo(
            *(VIDMM_EXPORT **)(*((_QWORD *)VirtualGpuDevice + 2) + 760LL),
            v59,
            *(struct VIDMM_MULTI_GLOBAL_ALLOC **)(*(_QWORD *)(*(_QWORD *)((char *)v75 + v58) + 48LL) + 8LL),
            &v71,
            &v81,
            &v73);
          v60 = *((_QWORD *)v20 + 23);
          v61 = (char *)v75;
          v62 = (unsigned int)v57;
          v63 = v71;
          v94.MemoryInfo[v62].DriverAllocationHandle = *(HANDLE *)(*(_QWORD *)(*(_QWORD *)((char *)v75 + v60) + 48LL)
                                                                 + 16LL);
          v94.MemoryInfo[v62].AllocationAddress.MemorySegmentOffset = v73;
          v94.MemoryInfo[v62].AllocationAddress.MemorySegmentId = v63;
          v94.MemoryInfo[v62].AllocationSize = a2->SegmentInfo[v57].Size;
          *(_DWORD *)&v61[v60 + 28] = v63;
          *(_QWORD *)&v61[*((_QWORD *)v20 + 23) + 8] = v73;
          LODWORD(v12) = VIDMM_EXPORT::VidMmQuerySegmentStatistics(
                           *(VIDMM_EXPORT **)(*(_QWORD *)(v12 + 16) + 760LL),
                           *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL),
                           0,
                           v71 - 1,
                           (struct _D3DKMT_QUERYSTATISTICS_SEGMENT_INFORMATION *)v85);
          if ( (int)v12 < 0 )
            break;
          v64 = (char)v72;
          *((_BYTE *)v75 + *((_QWORD *)v20 + 23) + 112) = LODWORD(v85[5]) != 0;
          if ( (v64 & 1) != 0 && !LODWORD(v85[5]) )
          {
            LODWORD(v12) = DXGK_VIRTUAL_GPU_GPUP::InitializeDirtyBitplaneForAllocation(v20, v57);
            if ( (int)v12 < 0 )
            {
              WdLogSingleEntry1(3);
              WdLogGlobalForLineNumber = 1748;
              goto LABEL_105;
            }
            if ( (v64 & 2) != 0 )
            {
              LODWORD(v12) = DXGK_VIRTUAL_GPU_GPUP::EnableDirtyBitTrackingForAllocation(v20, v57);
              if ( (int)v12 < 0 )
              {
                WdLogSingleEntry1(3);
                WdLogGlobalForLineNumber = 1757;
                goto LABEL_105;
              }
            }
          }
          v57 = (unsigned int)(v57 + 1);
          if ( (unsigned int)v57 >= a2->NumMemorySegments )
            goto LABEL_91;
        }
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1737;
        goto LABEL_105;
      }
LABEL_91:
      v65 = ADAPTER_RENDER::DdiSetVirtualGpuResources(*((ADAPTER_RENDER **)this + 4), &v94);
      LODWORD(v12) = v65;
      if ( bTracingEnabled )
      {
        v66 = v76;
        DxgkLogInternalTriageEvent(
          v76,
          196610,
          a2->PartitionId,
          (unsigned int)L"Setting vGPU resources with %1 segments returns %2",
          a2->NumMemorySegments,
          v65,
          0,
          0,
          0);
        for ( i = 0; i < a2->NumMemorySegments; ++i )
          DxgkLogInternalTriageEvent(
            v66,
            196610,
            a2->PartitionId,
            (unsigned int)L"vGPU has a resource set on segment %1 at offset %2 with a size of %3",
            v94.MemoryInfo[i].AllocationAddress.MemorySegmentId,
            v94.MemoryInfo[i].AllocationAddress.MemorySegmentOffset,
            v94.MemoryInfo[i].AllocationSize,
            0,
            0);
      }
      if ( (int)v12 < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1790;
        goto LABEL_105;
      }
      v75 = 0;
      LODWORD(v12) = ObReferenceObjectByHandle(Handle, 0x20000u, (POBJECT_TYPE)IoFileObjectType, 0, &v75, 0);
      if ( (int)v12 < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1800;
        goto LABEL_105;
      }
      v68 = v75;
      if ( *((_QWORD *)v75 + 4) )
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
        LODWORD(v12) = -1073741816;
        ObfDereferenceObject(v68);
        goto LABEL_105;
      }
      v69 = v75;
      *((_QWORD *)v75 + 4) = v77;
      *((_QWORD *)v20 + 20) = v68;
      ObfDereferenceObject(v69);
    }
    DXGK_VIRTUAL_GPU::ReportState(v20);
    LODWORD(v12) = 0;
    goto LABEL_110;
  }
  v22 = a2->PartitionId;
  v71 = 0xFFFF;
  LODWORD(v12) = DXGVIRTUALGPUMANAGER::GetTargetPartitionId(this, v22, &v71);
  if ( (int)v12 < 0 )
    goto LABEL_110;
  v23 = v71;
  a2->PartitionId = v71;
  v24 = (DXGK_VIRTUAL_GPU_GPUP *)operator new(360, 1265072196, 256);
  if ( v24 )
  {
    v20 = DXGK_VIRTUAL_GPU_GPUP::DXGK_VIRTUAL_GPU_GPUP(v24, *((struct ADAPTER_RENDER **)this + 4));
    if ( v20 )
    {
      v77 = (void *)operator new(16, 1265072196, 256);
      v25 = v77;
      if ( !v77 )
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
        (**(void (__fastcall ***)(DXGK_VIRTUAL_GPU_GPUP *, __int64))v20)(v20, 1);
        LODWORD(v12) = -1073741801;
        goto LABEL_110;
      }
      *((_QWORD *)v20 + 22) = VirtualGpuDevice;
      *((_QWORD *)v20 + 11) = Current;
      *((_DWORD *)v20 + 6) = v23;
      *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v23) = v20;
      ++*((_DWORD *)this + 4);
      DXGPUSHLOCK::AcquireExclusive((DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 72));
      v26 = (_QWORD *)((char *)this + 104);
      v27 = *((_QWORD *)this + 13);
      if ( *(DXGVIRTUALGPUMANAGER_GPUP **)(v27 + 8) != (DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 104) )
        __fastfail(3u);
      *((_QWORD *)v20 + 15) = v27;
      *((_QWORD *)v20 + 16) = v26;
      *(_QWORD *)(v27 + 8) = (char *)v20 + 120;
      *v26 = (char *)v20 + 120;
      *((_QWORD *)this + 10) = 0;
      ExReleasePushLockExclusiveEx((char *)this + 72, 0);
      KeLeaveCriticalRegion();
      v28 = v76;
      v19 = 0;
      v25[2] = v23;
      v21 = 0;
      *(_QWORD *)v25 = v28;
      goto LABEL_28;
    }
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v82);
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v83);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v92);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v79);
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v80);
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
