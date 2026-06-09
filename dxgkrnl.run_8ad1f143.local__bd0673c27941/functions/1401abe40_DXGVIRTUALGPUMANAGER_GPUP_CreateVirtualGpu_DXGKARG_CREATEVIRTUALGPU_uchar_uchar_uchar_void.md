# DXGVIRTUALGPUMANAGER_GPUP::CreateVirtualGpu(_DXGKARG_CREATEVIRTUALGPU *,uchar,uchar,uchar,void *)

- ea: `0x1401abe40`
- end: `0x1401ad12c`
- name: `?CreateVirtualGpu@DXGVIRTUALGPUMANAGER_GPUP@@UEAAJPEAU_DXGKARG_CREATEVIRTUALGPU@@EEEPEAX@Z`
- size: `4844`
- prototype: `__int64 __usercall@<rax>(DXGVIRTUALGPUMANAGER_GPUP *__hidden this@<rcx>, struct _DXGKARG_CREATEVIRTUALGPU *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, unsigned __int8, void *)`
- caller_count: `0`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x140015780`
- `0x1400158b0`
- `0x140015970`
- `0x140017fb8`
- `0x1400180f0`
- `0x14001a8d0`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14001c660`
- `0x14001d070`
- `0x14001f120`
- `0x14001f460`
- `0x14002e110`
- `0x14002ec90`
- `0x14002ed70`
- `0x140034f60`
- `0x140046eec`
- `0x140049164`
- `0x140057858`
- `0x14007cf84`
- `0x14007cfb0`
- `0x14007f0d8`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1400a0a60`
- `0x140182fd0`
- `0x1401abe40`
- `0x140255118`
- `0x140271968`
- `0x1402729f8`
- `0x1402759fc`
- `0x140279294`
- `0x14027bad4`
- `0x14027bd5c`
- `0x1402b9008`
- `0x1402b90ec`
- `0x140323854`
- `0x1403c36ac`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401abf30`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401abf62`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401abf30`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401abf62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401abf1f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401abf51`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401abf1f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401abf51`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401abfde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac0d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac0ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac149`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac16e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac4c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401acaf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401abfde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac0d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac0ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac149`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac16e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac4c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401acaf6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401abfd2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac0cd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac0f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac13d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac162`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac4b8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401abfd2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac0cd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac0f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac13d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac162`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac4b8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401acaea`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401acaea`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ad038`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ad080`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ad038`
- `ntoskrnl!ObfDereferenceObject` at `0x1401ad080`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401ac047`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401aca0b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401ac047`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401aca0b`
- `ntoskrnl!KeStackAttachProcess` at `0x1401ac020`
- `ntoskrnl!KeStackAttachProcess` at `0x1401ac9e6`
- `ntoskrnl!KeStackAttachProcess` at `0x1401ac020`
- `ntoskrnl!KeStackAttachProcess` at `0x1401ac9e6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401acfa4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401acfa4`
- `ntoskrnl!RtlCopyLuid` at `0x1401ac66d`
- `ntoskrnl!RtlCopyLuid` at `0x1401ac66d`
- `ntoskrnl!IoFileObjectType` at `0x1401acf7a`
- `watchdog!WdLogSingleEntry2` at `0x1401ac1d2`
- `watchdog!WdLogSingleEntry2` at `0x1401ac266`
- `watchdog!WdLogSingleEntry2` at `0x1401ac1d2`
- `watchdog!WdLogSingleEntry2` at `0x1401ac266`
- `watchdog!WdLogSingleEntry0` at `0x1401abe93`
- `watchdog!WdLogSingleEntry0` at `0x1401ac05f`
- `watchdog!WdLogSingleEntry0` at `0x1401ac319`
- `watchdog!WdLogSingleEntry0` at `0x1401ac3fd`
- `watchdog!WdLogSingleEntry0` at `0x1401ac54b`
- `watchdog!WdLogSingleEntry0` at `0x1401ac5b1`
- `watchdog!WdLogSingleEntry0` at `0x1401ac607`
- `watchdog!WdLogSingleEntry0` at `0x1401ac71b`
- `watchdog!WdLogSingleEntry0` at `0x1401ac850`
- `watchdog!WdLogSingleEntry0` at `0x1401ac8e4`
- `watchdog!WdLogSingleEntry0` at `0x1401aca80`
- `watchdog!WdLogSingleEntry0` at `0x1401acfe9`
- `watchdog!WdLogSingleEntry0` at `0x1401abe93`
- `watchdog!WdLogSingleEntry0` at `0x1401ac05f`
- `watchdog!WdLogSingleEntry0` at `0x1401ac319`
- `watchdog!WdLogSingleEntry0` at `0x1401ac3fd`
- `watchdog!WdLogSingleEntry0` at `0x1401ac54b`
- `watchdog!WdLogSingleEntry0` at `0x1401ac5b1`
- `watchdog!WdLogSingleEntry0` at `0x1401ac607`
- `watchdog!WdLogSingleEntry0` at `0x1401ac71b`
- `watchdog!WdLogSingleEntry0` at `0x1401ac850`
- `watchdog!WdLogSingleEntry0` at `0x1401ac8e4`
- `watchdog!WdLogSingleEntry0` at `0x1401aca80`
- `watchdog!WdLogSingleEntry0` at `0x1401acfe9`
- `watchdog!WdLogSingleEntry1` at `0x1401ac2cf`
- `watchdog!WdLogSingleEntry1` at `0x1401ac502`
- `watchdog!WdLogSingleEntry1` at `0x1401ac68b`
- `watchdog!WdLogSingleEntry1` at `0x1401ac7c2`
- `watchdog!WdLogSingleEntry1` at `0x1401acbe7`
- `watchdog!WdLogSingleEntry1` at `0x1401acc2d`
- `watchdog!WdLogSingleEntry1` at `0x1401ace23`
- `watchdog!WdLogSingleEntry1` at `0x1401ace46`
- `watchdog!WdLogSingleEntry1` at `0x1401ace69`
- `watchdog!WdLogSingleEntry1` at `0x1401acf5f`
- `watchdog!WdLogSingleEntry1` at `0x1401acfbf`
- `watchdog!WdLogSingleEntry1` at `0x1401ac2cf`
- `watchdog!WdLogSingleEntry1` at `0x1401ac502`
- `watchdog!WdLogSingleEntry1` at `0x1401ac68b`
- `watchdog!WdLogSingleEntry1` at `0x1401ac7c2`
- `watchdog!WdLogSingleEntry1` at `0x1401acbe7`
- `watchdog!WdLogSingleEntry1` at `0x1401acc2d`
- `watchdog!WdLogSingleEntry1` at `0x1401ace23`
- `watchdog!WdLogSingleEntry1` at `0x1401ace46`
- `watchdog!WdLogSingleEntry1` at `0x1401ace69`
- `watchdog!WdLogSingleEntry1` at `0x1401acf5f`
- `watchdog!WdLogSingleEntry1` at `0x1401acfbf`

## string_xrefs

- `0x1401ac55c`: `pArgs->UserModeVirtualDeviceProvider == m_pVirtualGpu[pArgs->PartitionId]->UserModeDllId`
- `0x1401acffa`: `The device file handle to bind to the new vGPU has already been bound to some other object.`
- `0x1401ac070`: `Failed to create partitioned GPU device 0x%I64x`
- `0x1401ac2e0`: `The PartitionId refers to a vGPU that has not yet been created: 0x%I64x`

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
  DXGK_VIRTUAL_GPU *v20; // r14
  char v21; // bl
  ULONG v22; // edx
  __int64 v23; // rbx
  DXGK_VIRTUAL_GPU *v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  _QWORD *v27; // r13
  PVOID v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 NumMemorySegments; // rax
  unsigned __int64 v32; // rdi
  __int64 v33; // rax
  bool v34; // cf
  __int64 v35; // rax
  unsigned __int64 *v36; // rax
  _QWORD *v37; // rbx
  __int64 v38; // rax
  int SavedAdapterState; // eax
  _DWORD *v40; // rcx
  unsigned int i; // edx
  ULONG v42; // r10d
  __int64 j; // rdx
  DXGDEVICE *v44; // rbx
  unsigned int v45; // eax
  ULONG v46; // edi
  unsigned int v47; // ebx
  unsigned int v48; // eax
  __int64 v49; // rdx
  int v50; // ecx
  __int64 v51; // rdi
  DXGPROCESS *v52; // rax
  __int64 *v53; // rbx
  __int64 v54; // r8
  union _LARGE_INTEGER v55; // rdx
  __int64 v56; // rax
  char *v57; // rcx
  int v58; // eax
  union _LARGE_INTEGER v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r13
  _QWORD *v62; // r9
  __int64 v63; // rdx
  __int64 v64; // r8
  ULONG v65; // ecx
  char v66; // bl
  int v67; // eax
  int v68; // r13d
  unsigned __int64 k; // rbx
  PVOID v70; // rbx
  PVOID v71; // rcx
  int Object; // [rsp+20h] [rbp-E0h]
  unsigned int v73; // [rsp+50h] [rbp-B0h] BYREF
  DXGDEVICE *VirtualGpuDevice; // [rsp+58h] [rbp-A8h] BYREF
  DXGPROCESS *v75; // [rsp+60h] [rbp-A0h]
  char *v76; // [rsp+68h] [rbp-98h] BYREF
  PVOID v77; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v78; // [rsp+78h] [rbp-88h]
  void *v79; // [rsp+80h] [rbp-80h]
  union _LARGE_INTEGER v80; // [rsp+88h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-70h]
  _BYTE v82[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v83[16]; // [rsp+B0h] [rbp-50h] BYREF
  char *v84; // [rsp+C0h] [rbp-40h]
  _BYTE v85[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v86[24]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v87[24]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v88[54]; // [rsp+110h] [rbp+10h] BYREF
  UINT64 Size; // [rsp+2C0h] [rbp+1C0h] BYREF
  UINT Alignment; // [rsp+2C8h] [rbp+1C8h]
  ULONG DriverSegmentId; // [rsp+2CCh] [rbp+1CCh]
  UINT PrivateDriverData; // [rsp+2D0h] [rbp+1D0h]
  int v93; // [rsp+2D4h] [rbp+1D4h]
  struct _KAPC_STATE ApcState; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v95[160]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v96[144]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _DXGKARG_SETVIRTUALGPURESOURCES v97; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v98[992]; // [rsp+468h] [rbp+368h] BYREF

  Handle = a6;
  Current = DXGPROCESS::GetCurrent();
  if ( !Current )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1342;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pProcess != nullptr", 1342, 0, 0, 0, 0);
  }
  *((_DWORD *)Current + 102) |= 0x40u;
  v77 = *(PVOID *)(*((_QWORD *)this + 4) + 16LL);
  v9 = (struct DXGADAPTER *)v77;
  v75 = (DXGPROCESS *)*((_QWORD *)DXGGLOBAL::GetGlobal() + 173);
  memset(&ApcState, 0, sizeof(ApcState));
  v10 = (char *)v75 + 216;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)v75 + 216, 0);
  *((_QWORD *)v75 + 28) = KeGetCurrentThread();
  v11 = *((_QWORD *)this + 4) + 24LL;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v11, 0);
  *(_QWORD *)(v11 + 8) = KeGetCurrentThread();
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82, v9, 1u);
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v96, v9, 0);
  LODWORD(v12) = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v96, 0);
  if ( (int)v12 < 0 )
  {
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v96);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82);
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
  DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE((DXGAUTOEXPUSHLOCKEXCLUSIVE *)v87, GpuVirtualizationLock);
  KeStackAttachProcess(*((PRKPROCESS *)v75 + 7), &ApcState);
  VirtualGpuDevice = DXGPROCESS::GetVirtualGpuDevice(v75, *((struct ADAPTER_RENDER **)this + 4));
  v14 = VirtualGpuDevice;
  KeUnstackDetachProcess(&ApcState);
  if ( !VirtualGpuDevice )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 1387;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to create partitioned GPU device 0x%I64x",
      1387,
      0,
      0,
      0,
      0);
    DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v87);
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v96);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82);
    *(_QWORD *)(v11 + 8) = 0;
    ExReleasePushLockExclusiveEx(v11, 0);
    KeLeaveCriticalRegion();
    *((_QWORD *)v10 + 1) = 0;
    LODWORD(v12) = -1073741801;
    goto LABEL_7;
  }
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v87);
  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v96);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82);
  *(_QWORD *)(v11 + 8) = 0;
  ExReleasePushLockExclusiveEx(v11, 0);
  KeLeaveCriticalRegion();
  *((_QWORD *)v10 + 1) = 0;
  ExReleasePushLockExclusiveEx(v10, 0);
  KeLeaveCriticalRegion();
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(
    (DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v83,
    v14);
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82, v9, 1u);
  LOBYTE(Object) = 0;
  COREDEVICEACCESS::COREDEVICEACCESS(v95, v14, 2);
  v16 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v95, 0);
  if ( v16 < 0 )
  {
    WdLogSingleEntry2(3, v14);
    WdLogGlobalForLineNumber = 1402;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v95);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v83);
    return (unsigned int)v16;
  }
  v17 = (struct _EX_PUSH_LOCK *)DpiGetGpuVirtualizationLock(*((_QWORD *)v77 + 27));
  DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE((DXGAUTOEXPUSHLOCKEXCLUSIVE *)v86, v17);
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)v85,
    (DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 40));
  if ( *((_BYTE *)DXGGLOBAL::GetGlobal() + 305637) )
  {
    PartitionId = a2->PartitionId;
    if ( a2->PartitionId == 0xFFFF )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 1495;
      LODWORD(v12) = -1073741637;
      goto LABEL_112;
    }
    if ( PartitionId >= *((_DWORD *)this + 3) )
    {
      WdLogSingleEntry2(2, PartitionId);
      WdLogGlobalForLineNumber = 1475;
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
LABEL_112:
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v85);
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v86);
      COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v95);
      DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82);
      DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v83);
      return (unsigned int)v12;
    }
    v19 = 0;
    v20 = *(DXGK_VIRTUAL_GPU **)(*((_QWORD *)this + 3) + 8LL * PartitionId);
    if ( !v20 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1484;
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
    v79 = 0;
    v21 = 1;
LABEL_27:
    LODWORD(v12) = ADAPTER_RENDER::DdiCreateVirtualGpu(*((ADAPTER_RENDER **)this + 4), a2);
    if ( (int)v12 < 0 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 1503;
LABEL_106:
      if ( v79 )
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v79);
      if ( v20 )
        (*(void (__fastcall **)(DXGVIRTUALGPUMANAGER_GPUP *, DXGK_VIRTUAL_GPU *))(*(_QWORD *)this + 24LL))(this, v20);
      goto LABEL_112;
    }
    if ( v21 )
    {
      if ( memcmp(
             &a2->UserModeVirtualDeviceProvider,
             (const void *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL * a2->PartitionId) + 36LL),
             0x10u) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1510;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"pArgs->UserModeVirtualDeviceProvider == m_pVirtualGpu[pArgs->PartitionId]->UserModeDllId",
          1510,
          0,
          0,
          0,
          0);
      }
      v29 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * a2->PartitionId);
      if ( a2->VirtualGpuLuid.LowPart != *(_DWORD *)(v29 + 28) || a2->VirtualGpuLuid.HighPart != *(_DWORD *)(v29 + 32) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1511;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"RtlEqualLuid(&pArgs->VirtualGpuLuid, &m_pVirtualGpu[pArgs->PartitionId]->VirtualGpuLuid)",
          1511,
          0,
          0,
          0,
          0);
      }
      if ( Handle )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 1512;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"vGPUHandle == nullptr", 1512, 0, 0, 0, 0);
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
        WdLogGlobalForLineNumber = 1521;
        LODWORD(v12) = -1073741811;
        goto LABEL_106;
      }
      if ( (_DWORD)NumMemorySegments )
      {
        v32 = a2->NumMemorySegments;
        v33 = 112 * NumMemorySegments;
        if ( !is_mul_ok(v32, 0x70u) )
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
            0x70u,
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
          WdLogGlobalForLineNumber = 1530;
          DxgkLogInternalTriageEvent(
            0,
            262145,
            -1,
            (unsigned int)L"Failed to allocate allocations array",
            1530,
            0,
            0,
            0,
            0);
          LODWORD(v12) = -1073741801;
          goto LABEL_106;
        }
        *((_DWORD *)v20 + 42) = a2->NumMemorySegments;
      }
      if ( (unsigned __int8)DpiKsrIsSoftBoot(v30) )
      {
        v38 = *((_QWORD *)this + 4);
        v73 = 0;
        v76 = 0;
        SavedAdapterState = DpiKsrGetSavedAdapterState(*(_QWORD *)(*(_QWORD *)(v38 + 16) + 216LL), &v73, &v76);
        v12 = SavedAdapterState;
        if ( SavedAdapterState < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1553;
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
          goto LABEL_106;
        }
        if ( v76 )
        {
          v40 = v76 + 4;
          for ( i = 0; i < *(_DWORD *)v76; ++i )
          {
            if ( *v40 == a2->PartitionId )
            {
              v42 = a2->NumMemorySegments;
              if ( v40[2] != v42 )
              {
                WdLogSingleEntry0(2);
                WdLogGlobalForLineNumber = 1566;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"NumMemorySegments in saved virtual function and new vGPU is different",
                  1566,
                  0,
                  0,
                  0,
                  0);
                goto LABEL_106;
              }
              v19 = v40 + 4;
              for ( j = 0; (unsigned int)j < v42; j = (unsigned int)(j + 1) )
              {
                if ( v19[6 * j] != a2->SegmentInfo[j].DriverSegmentId
                  || *(_QWORD *)&v19[6 * j + 4] != a2->SegmentInfo[j].Size
                  || v19[6 * j + 1] != a2->SegmentInfo[j].Alignment )
                {
                  WdLogSingleEntry0(2);
                  WdLogGlobalForLineNumber = 1576;
                  DxgkLogInternalTriageEvent(
                    0,
                    0x40000,
                    -1,
                    (unsigned int)L"Segment parameters in the saved data do not match",
                    1576,
                    0,
                    0,
                    0,
                    0);
                  goto LABEL_106;
                }
              }
              break;
            }
            v40 = (_DWORD *)((char *)v40 + (unsigned int)v40[3]);
          }
        }
      }
      v44 = VirtualGpuDevice;
      v78 = (_QWORD *)((char *)v20 + 184);
      v45 = 0;
      v84 = (char *)VirtualGpuDevice + 16;
      v76 = (char *)VirtualGpuDevice + 16;
      while ( 1 )
      {
        v46 = a2->NumMemorySegments;
        v73 = v45;
        if ( v45 >= v46 )
          break;
        v93 = 0;
        memset(v88, 0, 0x1A8u);
        HIDWORD(v88[0]) = *((_DWORD *)v44 + 117);
        v88[3] = &Size;
        LODWORD(v88[2]) = 5;
        LODWORD(v88[0]) = 512;
        Size = a2->SegmentInfo[v73].Size;
        Alignment = a2->SegmentInfo[v73].Alignment;
        DriverSegmentId = a2->SegmentInfo[v73].DriverSegmentId;
        PrivateDriverData = a2->SegmentInfo[v73].PrivateDriverData;
        KeStackAttachProcess(*((PRKPROCESS *)v75 + 7), &ApcState);
        LODWORD(v12) = DXGDEVICE::CreateStandardAllocation(v44, (struct _D3DKM_CREATESTANDARDALLOCATION *)v88, 0);
        KeUnstackDetachProcess(&ApcState);
        if ( (int)v12 < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 1616;
          goto LABEL_106;
        }
        v47 = HIDWORD(v88[6]);
        DXGPUSHLOCK::AcquireShared((DXGPROCESS *)((char *)v75 + 248));
        v48 = (v47 >> 6) & 0xFFFFFF;
        if ( v48 < *((_DWORD *)v75 + 74)
          && (v49 = *((_QWORD *)v75 + 35), ((v47 >> 25) & 0x60) == (*(_BYTE *)(v49 + 16LL * v48 + 8) & 0x60))
          && (*(_DWORD *)(v49 + 16LL * v48 + 8) & 0x2000) == 0
          && (v50 = *(_DWORD *)(v49 + 16LL * v48 + 8) & 0x1F) != 0 )
        {
          if ( v50 == 5 )
          {
            v51 = *(_QWORD *)(v49 + 16LL * v48);
          }
          else
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 318;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            v51 = 0;
          }
        }
        else
        {
          v51 = 0;
        }
        v52 = v75;
        _InterlockedDecrement((volatile signed __int32 *)v75 + 66);
        ExReleasePushLockSharedEx((char *)v52 + 248, 0);
        KeLeaveCriticalRegion();
        v53 = (__int64 *)((char *)v20 + 184);
        v54 = v73;
        v55.QuadPart = 112LL * v73;
        v56 = *((_QWORD *)v20 + 23);
        v57 = (char *)VirtualGpuDevice + 16;
        v80 = v55;
        v78 = (_QWORD *)((char *)v20 + 184);
        v76 = (char *)VirtualGpuDevice + 16;
        *(_QWORD *)(v55.QuadPart + v56) = v51;
        if ( v19 )
          v58 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v57 + 760LL)
                                                                                           + 8LL)
                                                                               + 1192LL))(
                  *(_QWORD *)(*((_QWORD *)this + 4) + 768LL),
                  *(_QWORD *)(*(_QWORD *)(*v53 + v55.QuadPart) + 24LL),
                  (unsigned int)v19[6 * v54],
                  *(_QWORD *)&v19[6 * v54 + 2],
                  Object);
        else
          v58 = VIDMM_EXPORT::VidMmPinAllocation(
                  *(VIDMM_EXPORT **)(*(_QWORD *)v57 + 760LL),
                  *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL),
                  *(struct VIDMM_MULTI_ALLOC **)(*(_QWORD *)(*v53 + v55.QuadPart) + 24LL),
                  0,
                  0);
        LODWORD(v12) = v58;
        if ( v58 < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1666;
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
          goto LABEL_106;
        }
        v59 = v80;
        *(_QWORD *)(*v53 + v80.QuadPart + 16) = Size;
        v60 = *v53;
        v44 = VirtualGpuDevice;
        *(_DWORD *)(v60 + v59.QuadPart + 24) = Alignment;
        v45 = v73 + 1;
      }
      memset(v97.MemoryInfo, 0, sizeof(v97.MemoryInfo));
      memset(v98, 0, sizeof(v98));
      v61 = 0;
      v97.PartitionId = a2->PartitionId;
      v97.NumMemoryAllocations = v46;
      while ( (unsigned int)v61 < a2->NumMemorySegments )
      {
        v73 = 0;
        v80.QuadPart = 0;
        VirtualGpuDevice = 0;
        LODWORD(v75) = *((_DWORD *)v77 + 1321);
        memset(v88, 0, 0x98u);
        v12 = 112LL * (unsigned int)v61;
        VIDMM_EXPORT::VidMmGetPinnedAllocationInfo(
          *(VIDMM_EXPORT **)(*(_QWORD *)v76 + 760LL),
          *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL),
          *(struct VIDMM_MULTI_GLOBAL_ALLOC **)(*(_QWORD *)(*(_QWORD *)(*v78 + v12) + 48LL) + 8LL),
          &v73,
          &v80,
          (unsigned __int64 *)&VirtualGpuDevice);
        v62 = v78;
        v63 = (unsigned int)v61;
        v64 = *v78;
        v65 = v73;
        v97.MemoryInfo[v63].DriverAllocationHandle = *(HANDLE *)(*(_QWORD *)(*(_QWORD *)(*v78 + v12) + 48LL) + 16LL);
        v97.MemoryInfo[v63].AllocationAddress.MemorySegmentOffset = (UINT64)VirtualGpuDevice;
        v97.MemoryInfo[v63].AllocationAddress.MemorySegmentId = v65;
        v97.MemoryInfo[v63].AllocationSize = a2->SegmentInfo[v61].Size;
        *(_DWORD *)(v64 + v12 + 28) = v65;
        *(_QWORD *)(*v62 + v12 + 8) = VirtualGpuDevice;
        LODWORD(v12) = VIDMM_EXPORT::VidMmQuerySegmentStatistics(
                         *(VIDMM_EXPORT **)(*(_QWORD *)v76 + 760LL),
                         *(struct VIDMM_GLOBAL **)(*((_QWORD *)this + 4) + 768LL),
                         0,
                         v73 - 1,
                         (struct _D3DKMT_QUERYSTATISTICS_SEGMENT_INFORMATION *)v88);
        if ( (int)v12 < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 1711;
          goto LABEL_106;
        }
        v66 = (char)v75;
        if ( ((unsigned __int8)v75 & 1) != 0 && !LODWORD(v88[5]) )
        {
          LODWORD(v12) = DXGK_VIRTUAL_GPU_GPUP::InitializeDirtyBitplaneForAllocation(v20, v61);
          if ( (int)v12 < 0 )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 1720;
            goto LABEL_106;
          }
          if ( (v66 & 2) != 0 )
          {
            LODWORD(v12) = DXGK_VIRTUAL_GPU_GPUP::EnableDirtyBitTrackingForAllocation(v20, v61);
            if ( (int)v12 < 0 )
            {
              WdLogSingleEntry1(3);
              WdLogGlobalForLineNumber = 1729;
              goto LABEL_106;
            }
          }
        }
        v61 = (unsigned int)(v61 + 1);
        v78 = (_QWORD *)((char *)v20 + 184);
        v76 = v84;
      }
      v67 = ADAPTER_RENDER::DdiSetVirtualGpuResources(*((ADAPTER_RENDER **)this + 4), &v97);
      LODWORD(v12) = v67;
      if ( bTracingEnabled )
      {
        v68 = (int)v77;
        DxgkLogInternalTriageEvent(
          (_DWORD)v77,
          196610,
          a2->PartitionId,
          (unsigned int)L"Setting vGPU resources with %1 segments returns %2",
          a2->NumMemorySegments,
          v67,
          0,
          0,
          0);
        for ( k = 0; k < a2->NumMemorySegments; ++k )
          DxgkLogInternalTriageEvent(
            v68,
            196610,
            a2->PartitionId,
            (unsigned int)L"vGPU has a resource set on segment %1 at offset %2 with a size of %3",
            v97.MemoryInfo[k].AllocationAddress.MemorySegmentId,
            v97.MemoryInfo[k].AllocationAddress.MemorySegmentOffset,
            v97.MemoryInfo[k].AllocationSize,
            0,
            0);
      }
      if ( (int)v12 < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1762;
        goto LABEL_106;
      }
      v77 = 0;
      LODWORD(v12) = ObReferenceObjectByHandle(Handle, 0x20000u, (POBJECT_TYPE)IoFileObjectType, 0, &v77, 0);
      if ( (int)v12 < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1772;
        goto LABEL_106;
      }
      v70 = v77;
      if ( *((_QWORD *)v77 + 4) )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 1780;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"The device file handle to bind to the new vGPU has already been bound to some other object.",
          1780,
          0,
          0,
          0,
          0);
        LODWORD(v12) = -1073741816;
        ObfDereferenceObject(v70);
        goto LABEL_106;
      }
      v71 = v77;
      *((_QWORD *)v77 + 4) = v79;
      *((_QWORD *)v20 + 20) = v70;
      ObfDereferenceObject(v71);
    }
    DXGK_VIRTUAL_GPU::ReportState(v20);
    LODWORD(v12) = 0;
    goto LABEL_112;
  }
  v22 = a2->PartitionId;
  v73 = 0xFFFF;
  LODWORD(v12) = DXGVIRTUALGPUMANAGER::GetTargetPartitionId(this, v22, &v73);
  if ( (int)v12 < 0 )
    goto LABEL_112;
  v23 = v73;
  a2->PartitionId = v73;
  v24 = (DXGK_VIRTUAL_GPU *)operator new(360, 1265072196, 256);
  v20 = v24;
  if ( v24 )
  {
    DXGK_VIRTUAL_GPU::DXGK_VIRTUAL_GPU(v24, *((struct ADAPTER_RENDER **)this + 4), 0);
    *(_QWORD *)v20 = &DXGK_VIRTUAL_GPU_GPUP::`vftable';
    *((_QWORD *)v20 + 25) = 0;
    *((_QWORD *)v20 + 26) = 0;
    *((_DWORD *)v20 + 54) = 0;
    *((_DWORD *)v20 + 55) = 33;
    *((_DWORD *)v20 + 56) = -1;
    `vector constructor iterator'(
      (char *)v20 + 232,
      0x30u,
      2u,
      (void *(*)(void *))DXGK_TRANSPORT_BUFFER::DXGK_TRANSPORT_BUFFER);
    v79 = (void *)operator new(16, 1265072196, 256);
    if ( !v79 )
    {
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1449;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Not enough memory to allocate the DXGSHAREDVGPUOBJECT for handle tracking.",
        1449,
        0,
        0,
        0,
        0);
      (**(void (__fastcall ***)(DXGK_VIRTUAL_GPU *, __int64))v20)(v20, 1);
      LODWORD(v12) = -1073741801;
      goto LABEL_112;
    }
    *((_QWORD *)v20 + 22) = VirtualGpuDevice;
    *((_QWORD *)v20 + 11) = Current;
    *((_DWORD *)v20 + 6) = v23;
    *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v23) = v20;
    ++*((_DWORD *)this + 4);
    DXGPUSHLOCK::AcquireExclusive((DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 72));
    v25 = (_QWORD *)((char *)this + 104);
    v26 = *((_QWORD *)this + 13);
    if ( *(DXGVIRTUALGPUMANAGER_GPUP **)(v26 + 8) != (DXGVIRTUALGPUMANAGER_GPUP *)((char *)this + 104) )
      __fastfail(3u);
    *((_QWORD *)v20 + 15) = v26;
    *((_QWORD *)v20 + 16) = v25;
    *(_QWORD *)(v26 + 8) = (char *)v20 + 120;
    *v25 = (char *)v20 + 120;
    *((_QWORD *)this + 10) = 0;
    ExReleasePushLockExclusiveEx((char *)this + 72, 0);
    KeLeaveCriticalRegion();
    v27 = v79;
    v28 = v77;
    *((_DWORD *)v79 + 2) = v23;
    *v27 = v28;
    v19 = 0;
    v21 = 0;
    goto LABEL_27;
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v85);
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v86);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v95);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v82);
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v83);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1401abe40  mov     [rsp-8+arg_10], rbx
0x1401abe45  push    rbp
0x1401abe46  push    rsi
0x1401abe47  push    rdi
0x1401abe48  push    r12
0x1401abe4a  push    r13
0x1401abe4c  push    r14
0x1401abe4e  push    r15
0x1401abe50  lea     rbp, [rsp-760h]
0x1401abe58  sub     rsp, 860h
0x1401abe5f  mov     rax, cs:__security_cookie
0x1401abe66  xor     rax, rsp
0x1401abe69  mov     [rbp+790h+var_40], rax
0x1401abe70  mov     rax, [rbp+790h+arg_28]
0x1401abe77  mov     rsi, rdx
0x1401abe7a  mov     [rbp+790h+Handle], rax
0x1401abe7e  mov     r15, rcx
0x1401abe81  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1401abe86  xor     ebx, ebx
0x1401abe88  mov     r13, rax
0x1401abe8b  test    rax, rax
0x1401abe8e  jnz     short loc_1401ABEDA
0x1401abe90  lea     ecx, [rax+1]
0x1401abe93  call    cs:__imp_WdLogSingleEntry0
0x1401abe9a  nop     dword ptr [rax+rax+00h]
0x1401abe9f  mov     [rsp+890h+var_850], rbx
0x1401abea4  lea     r9, aPprocessNullpt; "pProcess != nullptr"
0x1401abeab  mov     [rsp+890h+var_858], rbx
0x1401abeb0  mov     eax, 53Eh
0x1401abeb5  mov     [rsp+890h+var_860], rbx
0x1401abeba  or      r8d, 0FFFFFFFFh
0x1401abebe  mov     [rsp+890h+HandleInformation], rbx
0x1401abec3  mov     edx, 40002h
0x1401abec8  xor     ecx, ecx
0x1401abeca  mov     [rsp+890h+Object], rax
0x1401abecf  mov     cs:WdLogGlobalForLineNumber, eax
0x1401abed5  call    DxgkLogInternalTriageEvent
0x1401abeda  or      dword ptr [r13+198h], 40h
0x1401abee2  mov     rax, [r15+20h]
0x1401abee6  mov     r12, [rax+10h]
0x1401abeea  mov     [rsp+890h+var_820], r12
0x1401abeef  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401abef4  xorps   xmm0, xmm0
0x1401abef7  mov     rax, [rax+568h]
0x1401abefe  mov     [rsp+890h+var_830], rax
0x1401abf03  movups  xmmword ptr [rbp+790h+ApcState.ApcListHead.Flink], xmm0
0x1401abf0a  lea     r14, [rax+0D8h]
0x1401abf11  movups  xmmword ptr [rbp+790h+ApcState.ApcListHead.Flink+10h], xmm0
0x1401abf18  movups  xmmword ptr [rbp+790h+ApcState.Process], xmm0
0x1401abf1f  call    cs:__imp_KeEnterCriticalRegion
0x1401abf26  nop     dword ptr [rax+rax+00h]
0x1401abf2b  xor     edx, edx
0x1401abf2d  mov     rcx, r14
0x1401abf30  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401abf37  nop     dword ptr [rax+rax+00h]
0x1401abf3c  mov     rax, gs:188h
0x1401abf45  mov     [r14+8], rax
0x1401abf49  mov     rbx, [r15+20h]
0x1401abf4d  add     rbx, 18h
0x1401abf51  call    cs:__imp_KeEnterCriticalRegion
0x1401abf58  nop     dword ptr [rax+rax+00h]
0x1401abf5d  xor     edx, edx
0x1401abf5f  mov     rcx, rbx
0x1401abf62  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401abf69  nop     dword ptr [rax+rax+00h]
0x1401abf6e  mov     rax, gs:188h
0x1401abf77  lea     rcx, [rbp+790h+var_7F8]; this
0x1401abf7b  mov     r8b, 1; unsigned __int8
0x1401abf7e  mov     [rbx+8], rax
0x1401abf82  mov     rdx, r12; struct DXGADAPTER *
0x1401abf85  call    ??0DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@PEAVDXGADAPTER@@E@Z; DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(DXGADAPTER *,uchar)
0x1401abf8a  xor     r8d, r8d; struct DXGADAPTER *
0x1401abf8d  lea     rcx, [rbp+790h+var_4E0]; this
0x1401abf94  mov     rdx, r12; struct DXGADAPTER *
0x1401abf97  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x1401abf9c  xor     edx, edx; char *
0x1401abf9e  lea     rcx, [rbp+790h+var_4E0]; this
0x1401abfa5  call    ?AcquireShared@COREADAPTERACCESS@@QEAAJPEBD@Z; COREADAPTERACCESS::AcquireShared(char const *)
0x1401abfaa  mov     edi, eax
0x1401abfac  test    eax, eax
0x1401abfae  jns     short loc_1401ABFF7
0x1401abfb0  lea     rcx, [rbp+790h+var_4E0]; this
0x1401abfb7  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x1401abfbc  lea     rcx, [rbp+790h+var_7F8]; this
0x1401abfc0  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1401abfc5  xor     edx, edx
0x1401abfc7  mov     qword ptr [rbx+8], 0
0x1401abfcf  mov     rcx, rbx
0x1401abfd2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401abfd9  nop     dword ptr [rax+rax+00h]
0x1401abfde  call    cs:__imp_KeLeaveCriticalRegion
0x1401abfe5  nop     dword ptr [rax+rax+00h]
0x1401abfea  mov     qword ptr [r14+8], 0
0x1401abff2  jmp     loc_1401AC0EE
0x1401abff7  mov     rcx, [r12+0D8h]
0x1401abfff  call    DpiGetGpuVirtualizationLock
0x1401ac004  mov     rdx, rax; struct _EX_PUSH_LOCK *
0x1401ac007  lea     rcx, [rbp+790h+var_798]; this
0x1401ac00b  call    ??0DXGAUTOEXPUSHLOCKEXCLUSIVE@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(_EX_PUSH_LOCK * const)
0x1401ac010  mov     rdi, [rsp+890h+var_830]
0x1401ac015  lea     rdx, [rbp+790h+ApcState]; ApcState
0x1401ac01c  mov     rcx, [rdi+38h]; PROCESS
0x1401ac020  call    cs:__imp_KeStackAttachProcess
0x1401ac027  nop     dword ptr [rax+rax+00h]
0x1401ac02c  mov     rdx, [r15+20h]; struct ADAPTER_RENDER *
0x1401ac030  mov     rcx, rdi; this
0x1401ac033  call    ?GetVirtualGpuDevice@DXGPROCESS@@QEAAPEAVDXGDEVICE@@PEAVADAPTER_RENDER@@@Z; DXGPROCESS::GetVirtualGpuDevice(ADAPTER_RENDER *)
0x1401ac038  lea     rcx, [rbp+790h+ApcState]; ApcState
0x1401ac03f  mov     [rsp+890h+var_838], rax
0x1401ac044  mov     rdi, rax
0x1401ac047  call    cs:__imp_KeUnstackDetachProcess
0x1401ac04e  nop     dword ptr [rax+rax+00h]
0x1401ac053  test    rdi, rdi
0x1401ac056  jnz     loc_1401AC112
0x1401ac05c  lea     ecx, [rdi+2]
0x1401ac05f  call    cs:__imp_WdLogSingleEntry0
0x1401ac066  nop     dword ptr [rax+rax+00h]
0x1401ac06b  mov     [rsp+890h+var_850], rdi
0x1401ac070  lea     r9, aFailedToCreate_51; "Failed to create partitioned GPU device"...
0x1401ac077  mov     [rsp+890h+var_858], rdi
0x1401ac07c  mov     eax, 56Bh
0x1401ac081  mov     [rsp+890h+var_860], rdi
0x1401ac086  or      r8d, 0FFFFFFFFh
0x1401ac08a  mov     [rsp+890h+HandleInformation], rdi
0x1401ac08f  mov     edx, 40000h
0x1401ac094  xor     ecx, ecx
0x1401ac096  mov     [rsp+890h+Object], rax
0x1401ac09b  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ac0a1  call    DxgkLogInternalTriageEvent
0x1401ac0a6  lea     rcx, [rbp+790h+var_798]; this
0x1401ac0aa  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1401ac0af  lea     rcx, [rbp+790h+var_4E0]; this
0x1401ac0b6  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x1401ac0bb  lea     rcx, [rbp+790h+var_7F8]; this
0x1401ac0bf  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1401ac0c4  xor     edx, edx
0x1401ac0c6  mov     [rbx+8], rdi
0x1401ac0ca  mov     rcx, rbx
0x1401ac0cd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ac0d4  nop     dword ptr [rax+rax+00h]
0x1401ac0d9  call    cs:__imp_KeLeaveCriticalRegion
0x1401ac0e0  nop     dword ptr [rax+rax+00h]
0x1401ac0e5  mov     [r14+8], rdi
0x1401ac0e9  mov     edi, 0C0000017h
0x1401ac0ee  xor     edx, edx
0x1401ac0f0  mov     rcx, r14
0x1401ac0f3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ac0fa  nop     dword ptr [rax+rax+00h]
0x1401ac0ff  call    cs:__imp_KeLeaveCriticalRegion
0x1401ac106  nop     dword ptr [rax+rax+00h]
0x1401ac10b  mov     eax, edi
0x1401ac10d  jmp     loc_1401AD101
0x1401ac112  lea     rcx, [rbp+790h+var_798]; this
0x1401ac116  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x1401ac11b  lea     rcx, [rbp+790h+var_4E0]; this
0x1401ac122  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x1401ac127  lea     rcx, [rbp+790h+var_7F8]; this
0x1401ac12b  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1401ac130  xor     edx, edx
0x1401ac132  mov     qword ptr [rbx+8], 0
0x1401ac13a  mov     rcx, rbx
0x1401ac13d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ac144  nop     dword ptr [rax+rax+00h]
0x1401ac149  call    cs:__imp_KeLeaveCriticalRegion
0x1401ac150  nop     dword ptr [rax+rax+00h]
0x1401ac155  xor     edx, edx
0x1401ac157  mov     qword ptr [r14+8], 0
0x1401ac15f  mov     rcx, r14
0x1401ac162  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ac169  nop     dword ptr [rax+rax+00h]
0x1401ac16e  call    cs:__imp_KeLeaveCriticalRegion
0x1401ac175  nop     dword ptr [rax+rax+00h]
0x1401ac17a  mov     rdx, rdi; struct DXGDEVICE *
0x1401ac17d  lea     rcx, [rbp+790h+var_7E0]; this
0x1401ac181  call    ??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)
0x1401ac186  mov     r8b, 1; unsigned __int8
0x1401ac189  lea     rcx, [rbp+790h+var_7F8]; this
0x1401ac18d  mov     rdx, r12; struct DXGADAPTER *
0x1401ac190  call    ??0DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@PEAVDXGADAPTER@@E@Z; DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(DXGADAPTER *,uchar)
0x1401ac195  xor     r14d, r14d
0x1401ac198  lea     rcx, [rbp+790h+var_580]
0x1401ac19f  mov     rdx, rdi
0x1401ac1a2  mov     byte ptr [rsp+890h+Object], r14b
0x1401ac1a7  lea     r12d, [r14+2]
0x1401ac1ab  mov     r8d, r12d
0x1401ac1ae  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x1401ac1b3  xor     edx, edx; char *
0x1401ac1b5  lea     rcx, [rbp+790h+var_580]; this
0x1401ac1bc  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x1401ac1c1  movsxd  rbx, eax
0x1401ac1c4  test    eax, eax
0x1401ac1c6  jns     short loc_1401AC20D
0x1401ac1c8  mov     r8, rbx
0x1401ac1cb  lea     ecx, [r14+3]
0x1401ac1cf  mov     rdx, rdi
0x1401ac1d2  call    cs:__imp_WdLogSingleEntry2
0x1401ac1d9  nop     dword ptr [rax+rax+00h]
0x1401ac1de  lea     rcx, [rbp+790h+var_580]; this
0x1401ac1e5  mov     cs:WdLogGlobalForLineNumber, 57Ah
0x1401ac1ef  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1401ac1f4  lea     rcx, [rbp+790h+var_7F8]; this
0x1401ac1f8  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1401ac1fd  lea     rcx, [rbp+790h+var_7E0]; this
0x1401ac201  call    ??1DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@XZ; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL(void)
0x1401ac206  mov     eax, ebx
0x1401ac208  jmp     loc_1401AD101
0x1401ac20d  mov     rcx, [rsp+890h+var_820]
0x1401ac212  mov     rcx, [rcx+0D8h]
0x1401ac219  call    DpiGetGpuVirtualizationLock
0x1401ac21e  mov     rdx, rax; struct _EX_PUSH_LOCK *
0x1401ac221  lea     rcx, [rbp+790h+var_7B0]; this
0x1401ac225  call    ??0DXGAUTOEXPUSHLOCKEXCLUSIVE@@QEAA@QEAU_EX_PUSH_LOCK@@@Z; DXGAUTOEXPUSHLOCKEXCLUSIVE::DXGAUTOEXPUSHLOCKEXCLUSIVE(_EX_PUSH_LOCK * const)
0x1401ac22a  lea     rdx, [r15+28h]; struct DXGPUSHLOCK *
0x1401ac22e  lea     rcx, [rbp+790h+var_7C8]; this
0x1401ac232  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1401ac237  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401ac23c  cmp     [rax+4A9E5h], r14b
0x1401ac243  jz      loc_1401AC339
0x1401ac249  mov     eax, [rsi]
0x1401ac24b  cmp     eax, 0FFFFh
0x1401ac250  jz      loc_1401AC314
0x1401ac256  mov     ecx, [r15+0Ch]
0x1401ac25a  mov     edx, eax
0x1401ac25c  cmp     eax, ecx
0x1401ac25e  jb      short loc_1401AC2BC
0x1401ac260  mov     r8d, ecx
0x1401ac263  mov     ecx, r12d
0x1401ac266  call    cs:__imp_WdLogSingleEntry2
0x1401ac26d  nop     dword ptr [rax+rax+00h]
0x1401ac272  mov     [rsp+890h+var_850], r14
0x1401ac277  lea     r9, aThePartitionid_0; "The PartitionId supplied is greater tha"...
0x1401ac27e  mov     [rsp+890h+var_858], r14
0x1401ac283  mov     cs:WdLogGlobalForLineNumber, 5C3h
0x1401ac28d  mov     eax, [r15+0Ch]
0x1401ac291  mov     ecx, [rsi]
0x1401ac293  mov     [rsp+890h+var_860], r14
0x1401ac298  mov     [rsp+890h+HandleInformation], rax
0x1401ac29d  mov     [rsp+890h+Object], rcx
0x1401ac2a2  or      r8d, 0FFFFFFFFh
0x1401ac2a6  mov     edx, 40000h
0x1401ac2ab  xor     ecx, ecx
0x1401ac2ad  call    DxgkLogInternalTriageEvent
0x1401ac2b2  mov     edi, 0C000000Dh
0x1401ac2b7  jmp     loc_1401AD097
0x1401ac2bc  mov     rax, [r15+18h]
0x1401ac2c0  xor     r13d, r13d
0x1401ac2c3  mov     r14, [rax+rdx*8]
0x1401ac2c7  test    r14, r14
0x1401ac2ca  jnz     short loc_1401AC309
0x1401ac2cc  mov     ecx, r12d
0x1401ac2cf  call    cs:__imp_WdLogSingleEntry1
0x1401ac2d6  nop     dword ptr [rax+rax+00h]
0x1401ac2db  mov     [rsp+890h+var_850], r13
0x1401ac2e0  lea     r9, aThePartitionid; "The PartitionId refers to a vGPU that h"...
0x1401ac2e7  mov     [rsp+890h+var_858], r13
0x1401ac2ec  mov     [rsp+890h+var_860], r13
0x1401ac2f1  mov     cs:WdLogGlobalForLineNumber, 5CCh
0x1401ac2fb  mov     eax, [rsi]
0x1401ac2fd  mov     [rsp+890h+HandleInformation], r13
0x1401ac302  mov     [rsp+890h+Object], rax
0x1401ac307  jmp     short loc_1401AC2A2
0x1401ac309  mov     [rbp+790h+var_810], r13
0x1401ac30d  mov     bl, 1
0x1401ac30f  jmp     loc_1401AC4E7
0x1401ac314  mov     ecx, 3
0x1401ac319  call    cs:__imp_WdLogSingleEntry0
0x1401ac320  nop     dword ptr [rax+rax+00h]
0x1401ac325  mov     cs:WdLogGlobalForLineNumber, 5D7h
0x1401ac32f  mov     edi, 0C00000BBh
0x1401ac334  jmp     loc_1401AD097
0x1401ac339  mov     edx, [rsi]; unsigned int
0x1401ac33b  lea     r8, [rsp+890h+var_840]; unsigned int *
0x1401ac340  mov     rcx, r15; this
0x1401ac343  mov     [rsp+890h+var_840], 0FFFFh
0x1401ac34b  call    ?GetTargetPartitionId@DXGVIRTUALGPUMANAGER@@QEAAJIPEAI@Z; DXGVIRTUALGPUMANAGER::GetTargetPartitionId(uint,uint *)
0x1401ac350  mov     edi, eax
0x1401ac352  test    eax, eax
0x1401ac354  js      loc_1401AD097
0x1401ac35a  mov     ebx, [rsp+890h+var_840]
0x1401ac35e  mov     ecx, 168h
0x1401ac363  mov     edx, 4B677844h
0x1401ac368  mov     [rsi], ebx
0x1401ac36a  lea     r8d, [rcx-68h]
0x1401ac36e  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401ac373  xor     edi, edi
0x1401ac375  mov     r14, rax
0x1401ac378  test    rax, rax
0x1401ac37b  jz      loc_1401AD0CC
0x1401ac381  mov     rdx, [r15+20h]; struct ADAPTER_RENDER *
0x1401ac385  xor     r8d, r8d; unsigned __int8
0x1401ac388  mov     rcx, rax; this
0x1401ac38b  call    ??0DXGK_VIRTUAL_GPU@@QEAA@PEAVADAPTER_RENDER@@E@Z; DXGK_VIRTUAL_GPU::DXGK_VIRTUAL_GPU(ADAPTER_RENDER *,uchar)
0x1401ac390  lea     r8, ??_7DXGK_VIRTUAL_GPU_GPUP@@6B@; const DXGK_VIRTUAL_GPU_GPUP::`vftable'
0x1401ac397  mov     [r14], r8
0x1401ac39a  lea     rcx, [r14+0E8h]; void *
0x1401ac3a1  mov     [r14+0C8h], rdi
0x1401ac3a8  lea     r9, ??0DXGK_TRANSPORT_BUFFER@@QEAA@XZ; void *(*)(void *)
0x1401ac3af  mov     [r14+0D0h], rdi
0x1401ac3b6  lea     edx, [rdi+30h]; unsigned __int64
0x1401ac3b9  mov     r8, r12; unsigned __int64
  ... truncated ...
```
