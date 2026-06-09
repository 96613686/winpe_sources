# DxgkUpdateGpuVirtualAddress

- ea: `0x140199ae0`
- end: `0x14019ab40`
- name: `DxgkUpdateGpuVirtualAddress`
- size: `4192`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14029c4b0`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x1400146ac`
- `0x140015290`
- `0x140015b30`
- `0x1400162a4`
- `0x1400164f0`
- `0x140018054`
- `0x14001aa04`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001c450`
- `0x14001ce20`
- `0x14001cff0`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001f2f0`
- `0x14002e1d0`
- `0x140030824`
- `0x1400309f0`
- `0x140030a30`
- `0x140033da4`
- `0x140034910`
- `0x140035130`
- `0x140036ea8`
- `0x140039504`
- `0x140047990`
- `0x140048a5c`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1401992d4`
- `0x140199ae0`
- `0x14019ab48`
- `0x14032a5c4`
- `0x14032e980`
- `0x140334c88`
- `0x14037ecf0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019a668`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14019a668`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019a65c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14019a65c`
- `ntoskrnl!PsIsThreadTerminating` at `0x14019a7b7`
- `ntoskrnl!PsIsThreadTerminating` at `0x14019a7b7`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140199b69`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140199b69`
- `ntoskrnl!KeReleaseSemaphore` at `0x14019a7a2`
- `ntoskrnl!KeReleaseSemaphore` at `0x14019a7a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14019a782`
- `ntoskrnl!KeWaitForSingleObject` at `0x14019a782`
- `watchdog!WdLogSingleEntry2` at `0x140199d02`
- `watchdog!WdLogSingleEntry2` at `0x14019a4f9`
- `watchdog!WdLogSingleEntry2` at `0x14019a999`
- `watchdog!WdLogSingleEntry2` at `0x140199d02`
- `watchdog!WdLogSingleEntry2` at `0x14019a4f9`
- `watchdog!WdLogSingleEntry2` at `0x14019a999`
- `watchdog!WdLogSingleEntry3` at `0x140199d9b`
- `watchdog!WdLogSingleEntry3` at `0x140199dd1`
- `watchdog!WdLogSingleEntry3` at `0x140199f04`
- `watchdog!WdLogSingleEntry3` at `0x140199f98`
- `watchdog!WdLogSingleEntry3` at `0x14019a4a4`
- `watchdog!WdLogSingleEntry3` at `0x14019a938`
- `watchdog!WdLogSingleEntry3` at `0x140199d9b`
- `watchdog!WdLogSingleEntry3` at `0x140199dd1`
- `watchdog!WdLogSingleEntry3` at `0x140199f04`
- `watchdog!WdLogSingleEntry3` at `0x140199f98`
- `watchdog!WdLogSingleEntry3` at `0x14019a4a4`
- `watchdog!WdLogSingleEntry3` at `0x14019a938`
- `watchdog!WdLogSingleEntry0` at `0x14019a5f4`
- `watchdog!WdLogSingleEntry0` at `0x14019a854`
- `watchdog!WdLogSingleEntry0` at `0x14019a5f4`
- `watchdog!WdLogSingleEntry0` at `0x14019a854`
- `watchdog!WdLogSingleEntry1` at `0x140199b9e`
- `watchdog!WdLogSingleEntry1` at `0x140199c44`
- `watchdog!WdLogSingleEntry1` at `0x140199cad`
- `watchdog!WdLogSingleEntry1` at `0x140199eb1`
- `watchdog!WdLogSingleEntry1` at `0x14019a00e`
- `watchdog!WdLogSingleEntry1` at `0x14019a105`
- `watchdog!WdLogSingleEntry1` at `0x14019a1a3`
- `watchdog!WdLogSingleEntry1` at `0x14019a1e2`
- `watchdog!WdLogSingleEntry1` at `0x14019a28a`
- `watchdog!WdLogSingleEntry1` at `0x14019a31b`
- `watchdog!WdLogSingleEntry1` at `0x14019a80b`
- `watchdog!WdLogSingleEntry1` at `0x14019a839`
- `watchdog!WdLogSingleEntry1` at `0x14019a87c`
- `watchdog!WdLogSingleEntry1` at `0x14019a9f3`
- `watchdog!WdLogSingleEntry1` at `0x14019aa8f`
- `watchdog!WdLogSingleEntry1` at `0x140199b9e`
- `watchdog!WdLogSingleEntry1` at `0x140199c44`
- `watchdog!WdLogSingleEntry1` at `0x140199cad`
- `watchdog!WdLogSingleEntry1` at `0x140199eb1`
- `watchdog!WdLogSingleEntry1` at `0x14019a00e`
- `watchdog!WdLogSingleEntry1` at `0x14019a105`
- `watchdog!WdLogSingleEntry1` at `0x14019a1a3`
- `watchdog!WdLogSingleEntry1` at `0x14019a1e2`
- `watchdog!WdLogSingleEntry1` at `0x14019a28a`
- `watchdog!WdLogSingleEntry1` at `0x14019a31b`
- `watchdog!WdLogSingleEntry1` at `0x14019a80b`
- `watchdog!WdLogSingleEntry1` at `0x14019a839`
- `watchdog!WdLogSingleEntry1` at `0x14019a87c`
- `watchdog!WdLogSingleEntry1` at `0x14019a9f3`
- `watchdog!WdLogSingleEntry1` at `0x14019aa8f`

## string_xrefs

- `0x14019a03d`: `Failed to allocate memory for D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION, returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall DxgkUpdateGpuVirtualAddress(_D3DKMT_UPDATEGPUVIRTUALADDRESS *Src, __int64 a2, __int64 a3)
{
  char CurrentThreadPreviousMode; // r14
  struct DXGPROCESS *Current; // r15
  int updated; // esi
  _D3DKMT_UPDATEGPUVIRTUALADDRESS *v7; // r12
  unsigned int *v8; // r13
  __int64 *v9; // r14
  unsigned int *v10; // rdx
  __int64 v11; // rcx
  struct _VIDSCH_CONTEXT *VidSchCompanionContext; // r10
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rax
  void *v15; // rax
  NTSTATUS v16; // r15d
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned int v20; // r11d
  char *v21; // rcx
  int v22; // r9d
  UINT v23; // edx
  UINT NumOperations; // r10d
  unsigned __int64 v25; // rax
  int v26; // r8d
  int v27; // r8d
  void *v28; // rcx
  __int64 v29; // rax
  bool v30; // cf
  __int64 v31; // rax
  _QWORD *v32; // rax
  unsigned int v33; // edx
  DXGALLOCATIONREFERENCE *v34; // rax
  __int64 v35; // rax
  int v36; // r10d
  int v37; // r9d
  UINT i; // edx
  unsigned __int64 v39; // rax
  D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *Operations; // rcx
  int v41; // r8d
  unsigned int v42; // ecx
  __int64 AllocationSafe; // rax
  __int64 v44; // r8
  struct DXGGLOBAL *Global; // rax
  struct DXGPROCESS *v46; // rax
  bool v47; // cl
  int v48; // ecx
  __int64 v49; // rcx
  DXGPUSHLOCK *v50; // rax
  unsigned int *v51; // rdx
  struct _VIDSCH_SYNC_OBJECT *VidSchSyncObject; // rax
  int v53; // eax
  __int64 v54; // rcx
  __int64 v55; // r8
  unsigned int v56; // edx
  __int64 v57; // rcx
  __int64 v58; // r8
  unsigned int v59; // edx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // rcx
  __int64 v63; // r8
  PVOID Object; // [rsp+50h] [rbp-1E8h] BYREF
  unsigned int v65; // [rsp+58h] [rbp-1E0h] BYREF
  __int64 v66; // [rsp+60h] [rbp-1D8h]
  char v67; // [rsp+68h] [rbp-1D0h]
  char v68; // [rsp+70h] [rbp-1C8h]
  void *v69; // [rsp+78h] [rbp-1C0h]
  DXGDEVICESYNCOBJECT *v70; // [rsp+80h] [rbp-1B8h]
  char v71[8]; // [rsp+88h] [rbp-1B0h] BYREF
  unsigned __int64 v72; // [rsp+90h] [rbp-1A8h]
  DXGPUSHLOCK *v73; // [rsp+98h] [rbp-1A0h]
  struct DXGPROCESS *v74; // [rsp+A0h] [rbp-198h]
  DXGALLOCATIONREFERENCE *v75; // [rsp+A8h] [rbp-190h]
  _QWORD v76[2]; // [rsp+B0h] [rbp-188h] BYREF
  _BYTE v77[16]; // [rsp+C0h] [rbp-178h] BYREF
  _QWORD v78[2]; // [rsp+D0h] [rbp-168h] BYREF
  int v79; // [rsp+E0h] [rbp-158h]
  _BYTE v80[16]; // [rsp+E8h] [rbp-150h] BYREF
  _BYTE v81[24]; // [rsp+F8h] [rbp-140h] BYREF
  char v82[8]; // [rsp+110h] [rbp-128h] BYREF
  __int64 v83; // [rsp+118h] [rbp-120h]
  __int64 v84; // [rsp+120h] [rbp-118h]
  _D3DKMT_UPDATEGPUVIRTUALADDRESS v85; // [rsp+128h] [rbp-110h] BYREF
  _BYTE v86[160]; // [rsp+160h] [rbp-D8h] BYREF

  v65 = -1;
  v66 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v67 = 1;
    v65 = 2106;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2106);
  }
  else
  {
    v67 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v65, 2106);
  CurrentThreadPreviousMode = PsGetCurrentThreadPreviousMode();
  v68 = CurrentThreadPreviousMode;
  Current = DXGPROCESS::GetCurrent();
  v74 = Current;
  if ( !Current )
  {
    updated = -1073741811;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 13601;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process context, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
    goto LABEL_128;
  }
  memset(&v85, 0, sizeof(v85));
  v7 = &v85;
  v69 = &v85;
  if ( CurrentThreadPreviousMode == 1 )
  {
    RtlCopyFromUser(&v85, Src, 0x38u);
  }
  else
  {
    v7 = Src;
    v69 = Src;
  }
  if ( !v7->NumOperations )
  {
    updated = -1073741811;
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 13628;
    goto LABEL_128;
  }
  Object = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)v71, v7->hDevice, Current, (struct DXGDEVICE **)&Object);
  v8 = (unsigned int *)Object;
  if ( !Object )
  {
    updated = -1073741811;
    WdLogSingleEntry2(2, v7->hDevice);
    WdLogGlobalForLineNumber = 13636;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      v7->hDevice,
      -1073741811,
      0,
      0,
      0);
LABEL_127:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v71);
LABEL_128:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v65);
    if ( v67 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v62, EventProfilerExit, v63, v65);
    }
    return (unsigned int)updated;
  }
  Object = 0;
  DXGCONTEXTBYHANDLE::DXGCONTEXTBYHANDLE(
    (DXGCONTEXTBYHANDLE *)v77,
    v7->hContext,
    Current,
    (struct DXGCONTEXT **)&Object,
    0,
    1);
  v9 = (__int64 *)Object;
  if ( !Object )
  {
    updated = -1073741811;
    WdLogSingleEntry3(3, Current, v7->hContext, -1073741811);
    WdLogGlobalForLineNumber = 13645;
LABEL_126:
    DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v77);
    goto LABEL_127;
  }
  v10 = (unsigned int *)*((_QWORD *)Object + 2);
  if ( v10 != v8 )
  {
    updated = -1073741811;
    WdLogSingleEntry3(2, v10, v8, -1073741811);
    WdLogGlobalForLineNumber = 13652;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Context device 0x%p does not match user provided device 0x%p, returning 0x%I64x",
      v9[2],
      (__int64)v8,
      -1073741811,
      0,
      0);
    goto LABEL_126;
  }
  v11 = *(_QWORD *)(*((_QWORD *)v8 + 2) + 16LL);
  if ( *(_BYTE *)(v11 + 209) )
  {
    updated = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendUpdateGpuVirtualAddress(
                (DXG_GUEST_VIRTUALGPU_VMBUS *)(v11 + 4792),
                Current,
                v8[118],
                *((_DWORD *)Object + 7),
                v7);
    goto LABEL_126;
  }
  DXGDEVICEACCESSLOCKSHARED::DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v80, (struct DXGDEVICE *)v8);
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)v81,
    (struct DXGPUSHLOCK *const)(v9 + 55));
  COREDEVICEACCESS::COREDEVICEACCESS(v86, v8, 0);
  updated = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v86, 0);
  if ( updated < 0 )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 13679;
LABEL_125:
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v86);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v81);
    DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v80);
    goto LABEL_126;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 2) + 16LL) + 2596LL) & 0x40) == 0 )
  {
    updated = -1073741811;
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 13685;
    goto LABEL_125;
  }
  if ( !DXGCONTEXT::GetVidSchCompanionContext((DXGCONTEXT *)v9) )
  {
    updated = -1073741811;
    WdLogSingleEntry3(3, Current, v7->hContext, -1073741811);
    WdLogGlobalForLineNumber = 13693;
    goto LABEL_125;
  }
  if ( !v9[34] )
  {
    VidSchCompanionContext = DXGCONTEXT::GetVidSchCompanionContext((DXGCONTEXT *)v9);
    if ( VidSchCompanionContext )
      v9[34] = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _VIDSCH_CONTEXT *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9[2] + 16) + 760LL)
                                                                                               + 8LL)
                                                                                   + 952LL))(
                 *(_QWORD *)(*(_QWORD *)(v9[2] + 16) + 768LL),
                 *(_QWORD *)(v9[2] + 792),
                 VidSchCompanionContext);
  }
  v84 = v9[34];
  if ( !v84 )
  {
    updated = -1073741811;
    WdLogSingleEntry3(3, Current, v7->hContext, -1073741811);
    WdLogGlobalForLineNumber = 13701;
    goto LABEL_125;
  }
  v13 = (unsigned __int64)v7->NumOperations << 6;
  if ( v13 > 0xFFFFFFFF )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 13718;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v86);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v81);
    DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v80);
    DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v77);
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v71);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v65);
    if ( v67 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v60, EventProfilerExit, v61, v65);
    return (unsigned int)-1073741811;
  }
  v14 = (unsigned __int64)v7->NumOperations << 6;
  if ( !is_mul_ok(v7->NumOperations, 0x40u) )
    v14 = -1;
  v15 = (void *)operator new[](v14, 1265072196, 256);
  Object = v15;
  if ( !v15 )
  {
    v16 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 13724;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate memory for D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION, returning 0x%I64x",
      -1073741801,
      0,
      0,
      0,
      0);
    goto LABEL_35;
  }
  v16 = -1073741811;
  LODWORD(v70) = -1073741811;
  v75 = 0;
  if ( v68 == 1 )
    RtlCopyFromUser(v15, v7->Operations, (unsigned int)v13);
  else
    memmove(v15, v7->Operations, (unsigned int)v13);
  v20 = 0;
  LODWORD(v72) = 0;
  v21 = (char *)Object;
  v7->Operations = (D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION *)Object;
  v22 = 0;
  v23 = 0;
  NumOperations = v7->NumOperations;
  while ( v23 < NumOperations )
  {
    v25 = (unsigned __int64)v23 << 6;
    v26 = *(_DWORD *)&v21[v25];
    if ( !v26 || v26 == 3 )
    {
      v27 = *(_DWORD *)&v21[v25 + 24];
      if ( !v27 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 13761;
        goto LABEL_53;
      }
      if ( v22 != v27 )
      {
        LODWORD(v72) = ++v20;
        v22 = v27;
      }
    }
    else if ( (unsigned int)(v26 - 1) > 1 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 13774;
LABEL_53:
      v28 = 0;
      goto LABEL_118;
    }
    ++v23;
  }
  v29 = 8LL * v20;
  if ( !is_mul_ok(v20, 8u) )
    v29 = -1;
  v30 = __CFADD__(v29, 8);
  v31 = v29 + 8;
  if ( v30 )
    v31 = -1;
  v32 = (_QWORD *)operator new[](v31, 1265072196, 256);
  if ( v32 )
  {
    v33 = v72;
    *v32 = (unsigned int)v72;
    v75 = (DXGALLOCATIONREFERENCE *)(v32 + 1);
    `vector constructor iterator'(
      v32 + 1,
      8u,
      v33,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_KEVENT *,void (void *),&void widxg::details::DereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_KEVENT *,_KEVENT *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_KEVENT *,void (void *),&void widxg::details::DereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_KEVENT *,_KEVENT *,0,std::nullptr_t>>>);
    v34 = v75;
  }
  else
  {
    v34 = 0;
    v75 = 0;
  }
  if ( !v34 )
  {
    v16 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 13783;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate DXGALLOCATIONREFERENCE array, returning 0x%I64x",
      -1073741801,
      0,
      0,
      0,
      0);
    goto LABEL_53;
  }
  v35 = 8LL * (unsigned int)v72;
  if ( !is_mul_ok((unsigned int)v72, 8u) )
    v35 = -1;
  v69 = (void *)operator new[](v35, 1265072196, 256);
  if ( !v69 )
  {
    v16 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 13791;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate VIDMM_MULTI_ALLOC* array, returning 0x%I64x",
      -1073741801,
      0,
      0,
      0,
      0);
    goto LABEL_117;
  }
  v36 = 0;
  v37 = -1;
  v79 = -1;
  for ( i = 0; ; ++i )
  {
    LODWORD(v73) = i;
    if ( i >= v7->NumOperations )
      break;
    v39 = (unsigned __int64)i << 6;
    v78[0] = v39;
    Operations = v7->Operations;
    v76[0] = Operations;
    v41 = *(D3DDDI_UPDATEGPUVIRTUALADDRESS_OPERATION_TYPE *)((char *)&Operations->OperationType + v39);
    if ( !v41 || v41 == 3 )
    {
      v42 = *(D3DKMT_HANDLE *)((char *)&Operations->Map.hAllocation + v39);
      LODWORD(v70) = v42;
      if ( v36 != v42 )
      {
        v83 = v37;
        Object = (char *)v75 + 8 * v37 + 8;
        AllocationSafe = DXGPROCESS::GetAllocationSafe(v74, v82, v42);
        DXGALLOCATIONREFERENCE::MoveAssign(Object, AllocationSafe);
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v82);
        v44 = *(_QWORD *)Object;
        if ( !*(_QWORD *)Object )
        {
          WdLogSingleEntry2(3, (unsigned int)v70);
          WdLogGlobalForLineNumber = 13822;
LABEL_117:
          v28 = v69;
LABEL_118:
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v28);
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v7->Operations);
          if ( v75 )
            DXGALLOCATIONREFERENCE::`vector deleting destructor'(v75, v59);
LABEL_35:
          COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v86);
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v81);
          DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v80);
          DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v77);
          ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v71);
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v65);
          if ( v67 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v17, EventProfilerExit, v18, v65);
          return (unsigned int)v16;
        }
        if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v44 + 8) + 16LL) + 16LL) != *(_QWORD *)(*((_QWORD *)v8 + 2) + 16LL) )
        {
          WdLogSingleEntry3(2, v8, v44, -1073741811);
          WdLogGlobalForLineNumber = 13830;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
            (__int64)v8,
            *(_QWORD *)Object,
            -1073741811,
            0,
            0);
          goto LABEL_117;
        }
        v37 = ++v79;
        v36 = (int)v70;
        *((_QWORD *)v69 + v83 + 1) = *(_QWORD *)(v44 + 24);
        v39 = v78[0];
        i = (unsigned int)v73;
      }
      *(_DWORD *)(v39 + v76[0] + 24) = v37;
    }
  }
  v73 = (struct DXGPROCESS *)((char *)v74 + 248);
  while ( 1 )
  {
    Global = DXGGLOBAL::GetGlobal();
    DXGSYNCOBJECTLOCK::DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v76, Global, 0);
    DXGSYNCOBJECTLOCK::AcquireShared((DXGSYNCOBJECTLOCK *)v76);
    LODWORD(v70) = v7->hFenceObject;
    DXGPUSHLOCK::AcquireShared(v73);
    v46 = v74;
    if ( (((unsigned int)v70 >> 6) & 0xFFFFFF) < *((_DWORD *)v74 + 74) )
    {
      v48 = *(_DWORD *)(*((_QWORD *)v74 + 35) + 16LL * (((unsigned int)v70 >> 6) & 0xFFFFFF) + 8);
      v47 = (((unsigned int)v70 >> 25) & 0x60) == (*(_BYTE *)(*((_QWORD *)v74 + 35)
                                                            + 16LL * (((unsigned int)v70 >> 6) & 0xFFFFFF)
                                                            + 8)
                                                 & 0x60)
         && (v48 & 0x2000) == 0
         && (v48 & 0x1F) != 0;
      v46 = v74;
    }
    else
    {
      v47 = 0;
    }
    if ( !v47 )
      goto LABEL_88;
    v49 = *((_QWORD *)v46 + 35);
    if ( (*(_BYTE *)(v49 + 16LL * (((unsigned int)v70 >> 6) & 0xFFFFFF) + 8) & 0x1F) != 0xB )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 318;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
LABEL_88:
      v70 = 0;
      goto LABEL_92;
    }
    v70 = *(DXGDEVICESYNCOBJECT **)(v49 + 16LL * (((unsigned int)v70 >> 6) & 0xFFFFFF));
LABEL_92:
    v50 = v73;
    _InterlockedDecrement((volatile signed __int32 *)v73 + 4);
    ExReleasePushLockSharedEx(v50, 0);
    KeLeaveCriticalRegion();
    if ( !v70 )
    {
      WdLogSingleEntry2(3, v7->hFenceObject);
      WdLogGlobalForLineNumber = 13865;
      goto LABEL_116;
    }
    v51 = (unsigned int *)*((_QWORD *)v70 + 2);
    if ( v51 != v8 )
    {
      WdLogSingleEntry3(2, v51, v8, -1073741811);
      WdLogGlobalForLineNumber = 13872;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Monitored fence device 0x%p does not match user provided device 0x%p, returning 0x%I64x",
        *((_QWORD *)v70 + 2),
        (__int64)v8,
        -1073741811,
        0,
        0);
      goto LABEL_116;
    }
    DXGSYNCOBJECTMUTEX::DXGSYNCOBJECTMUTEX((DXGSYNCOBJECTMUTEX *)v78, *((struct DXGSYNCOBJECT **)v70 + 4));
    DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v78);
    VidSchSyncObject = DXGDEVICESYNCOBJECT::GetVidSchSyncObject(v70);
    Object = 0;
    v53 = (*(__int64 (__fastcall **)(_QWORD, _D3DKMT_UPDATEGPUVIRTUALADDRESS *, __int64, _QWORD, void *, struct _VIDSCH_SYNC_OBJECT *, PVOID *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 2) + 760LL) + 8LL) + 968LL))(
            *(_QWORD *)(*((_QWORD *)v8 + 2) + 768LL),
            v7,
            v84,
            (unsigned int)v72,
            v69,
            VidSchSyncObject,
            &Object);
    v16 = v53;
    if ( v53 != -1071775486 )
      break;
    COREDEVICEACCESS::Release((COREDEVICEACCESS *)v86);
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v78);
    DXGSYNCOBJECTLOCK::Release((DXGSYNCOBJECTLOCK *)v76);
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
      McTemplateK0q_EtwWriteTransfer(v54, EventBlockThread, v55, 68);
    v16 = KeWaitForSingleObject(Object, UserRequest, 0, 1u, 0);
    if ( !v16 )
      KeReleaseSemaphore((PRKSEMAPHORE)Object, 0, 1, 0);
    if ( PsIsThreadTerminating(KeGetCurrentThread()) )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 13919;
      v16 = -1073741130;
      goto LABEL_105;
    }
    if ( v16 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 13926;
      goto LABEL_105;
    }
    v16 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v86, 0);
    if ( v16 < 0 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 13936;
      goto LABEL_105;
    }
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v78);
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v76);
  }
  if ( v53 < 0 )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 13943;
LABEL_105:
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v78);
LABEL_116:
    DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v76);
    goto LABEL_117;
  }
  DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v78);
  DXGSYNCOBJECTLOCK::~DXGSYNCOBJECTLOCK((DXGSYNCOBJECTLOCK *)v76);
  DXGALLOCATIONREFERENCE::`vector deleting destructor'(v75, v56);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v86);
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v81);
  DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED((DXGDEVICEACCESSLOCKSHARED *)v80);
  DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)v77);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v71);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v65);
  if ( v67 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v57, EventProfilerExit, v58, v65);
  return 0;
}

```

## disassembly

```asm
0x140199ae0  mov     [rsp+arg_8], rbx
0x140199ae5  mov     [rsp+arg_10], rsi
0x140199aea  push    rdi
0x140199aeb  push    r12
0x140199aed  push    r13
0x140199aef  push    r14
0x140199af1  push    r15
0x140199af3  sub     rsp, 210h
0x140199afa  mov     rax, cs:__security_cookie
0x140199b01  xor     rax, rsp
0x140199b04  mov     [rsp+238h+var_38], rax
0x140199b0c  mov     rsi, rcx
0x140199b0f  mov     [rsp+238h+var_1E0], 0FFFFFFFFh
0x140199b17  xor     ebx, ebx
0x140199b19  mov     [rsp+238h+var_1D8], rbx
0x140199b1e  mov     rax, cs:qword_1401604F0
0x140199b25  lea     edi, [rbx+1]
0x140199b28  test    al, 2
0x140199b2a  jz      short loc_140199B56
0x140199b2c  mov     [rsp+238h+var_1D0], dil
0x140199b31  mov     [rsp+238h+var_1E0], 83Ah
0x140199b39  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x140199b40  jz      short loc_140199B5A
0x140199b42  mov     r9d, 83Ah
0x140199b48  lea     rdx, EventProfilerEnter
0x140199b4f  call    McTemplateK0q_EtwWriteTransfer
0x140199b54  jmp     short loc_140199B5A
0x140199b56  mov     [rsp+238h+var_1D0], bl
0x140199b5a  mov     edx, 83Ah
0x140199b5f  lea     rcx, [rsp+238h+var_1E0]
0x140199b64  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140199b69  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x140199b70  nop     dword ptr [rax+rax+00h]
0x140199b75  mov     r14b, al
0x140199b78  mov     [rsp+238h+var_1C8], al
0x140199b7c  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140199b81  mov     r15, rax
0x140199b84  mov     [rsp+238h+var_198], rax
0x140199b8c  test    rax, rax
0x140199b8f  jnz     short loc_140199BEB
0x140199b91  mov     rsi, 0FFFFFFFFC000000Dh
0x140199b98  mov     rdx, rsi
0x140199b9b  lea     ecx, [rax+2]
0x140199b9e  call    cs:__imp_WdLogSingleEntry1
0x140199ba5  nop     dword ptr [rax+rax+00h]
0x140199baa  mov     cs:WdLogGlobalForLineNumber, 3521h
0x140199bb4  mov     [rsp+238h+var_1F8], rbx
0x140199bb9  mov     [rsp+238h+var_200], rbx
0x140199bbe  mov     [rsp+238h+var_208], rbx
0x140199bc3  mov     qword ptr [rsp+238h+var_210], rbx
0x140199bc8  mov     [rsp+238h+Timeout], rsi
0x140199bcd  lea     r9, aInvalidProcess_4; "Invalid process context, returning 0x%I"...
0x140199bd4  mov     edx, 40000h
0x140199bd9  xor     ecx, ecx
0x140199bdb  mov     r8d, 0FFFFFFFFh
0x140199be1  call    DxgkLogInternalTriageEvent
0x140199be6  jmp     loc_14019AAE6
0x140199beb  xorps   xmm0, xmm0
0x140199bee  xor     eax, eax
0x140199bf0  movups  xmmword ptr [rsp+238h+var_110.hDevice], xmm0
0x140199bf8  movups  xmmword ptr [rsp+238h+var_110.Operations], xmm0
0x140199c00  movups  xmmword ptr [rsp+238h+var_110.Reserved1], xmm0
0x140199c08  mov     qword ptr [rsp+238h+var_110.Flags], rax
0x140199c10  lea     r12, [rsp+238h+var_110]
0x140199c18  mov     [rsp+238h+var_1C0], r12
0x140199c1d  cmp     r14b, dil
0x140199c20  jnz     short loc_140199C8F
0x140199c22  lea     r8d, [rax+38h]; Size
0x140199c26  mov     rdx, rsi; Src
0x140199c29  lea     rcx, [rsp+238h+var_110]; void *
0x140199c31  call    RtlCopyFromUser
0x140199c36  jmp     short loc_140199C97
0x140199c38  mov     rdx, 0FFFFFFFFC000000Dh
0x140199c3f  mov     ecx, 3
0x140199c44  call    cs:__imp_WdLogSingleEntry1
0x140199c4b  nop     dword ptr [rax+rax+00h]
0x140199c50  mov     cs:WdLogGlobalForLineNumber, 3530h
0x140199c5a  lea     rcx, [rsp+238h+var_1E0]; this
0x140199c5f  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140199c64  cmp     [rsp+238h+var_1D0], 0
0x140199c69  jz      short loc_140199C85
0x140199c6b  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140199c72  jz      short loc_140199C85
0x140199c74  mov     r9d, [rsp+238h+var_1E0]
0x140199c79  lea     rdx, EventProfilerExit
0x140199c80  call    McTemplateK0q_EtwWriteTransfer
0x140199c85  mov     eax, 0C000000Dh
0x140199c8a  jmp     loc_14019AB12
0x140199c8f  mov     r12, rsi
0x140199c92  mov     [rsp+238h+var_1C0], rsi
0x140199c97  cmp     [r12+0Ch], ebx
0x140199c9c  jnz     short loc_140199CC8
0x140199c9e  mov     rsi, 0FFFFFFFFC000000Dh
0x140199ca5  mov     rdx, rsi
0x140199ca8  mov     ecx, 3
0x140199cad  call    cs:__imp_WdLogSingleEntry1
0x140199cb4  nop     dword ptr [rax+rax+00h]
0x140199cb9  mov     cs:WdLogGlobalForLineNumber, 353Ch
0x140199cc3  jmp     loc_14019AAE6
0x140199cc8  mov     [rsp+238h+Object], rbx
0x140199ccd  lea     r9, [rsp+238h+Object]; struct DXGDEVICE **
0x140199cd2  mov     r8, r15; struct DXGPROCESS *
0x140199cd5  mov     edx, [r12]; unsigned int
0x140199cd9  lea     rcx, [rsp+238h+var_1B0]; this
0x140199ce1  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x140199ce6  mov     r13, [rsp+238h+Object]
0x140199ceb  test    r13, r13
0x140199cee  jnz     short loc_140199D53
0x140199cf0  mov     edx, [r12]
0x140199cf4  mov     rsi, 0FFFFFFFFC000000Dh
0x140199cfb  mov     r8, rsi
0x140199cfe  lea     ecx, [r13+2]
0x140199d02  call    cs:__imp_WdLogSingleEntry2
0x140199d09  nop     dword ptr [rax+rax+00h]
0x140199d0e  mov     cs:WdLogGlobalForLineNumber, 3544h
0x140199d18  mov     eax, [r12]
0x140199d1c  mov     [rsp+238h+var_1F8], rbx
0x140199d21  mov     [rsp+238h+var_200], rbx
0x140199d26  mov     [rsp+238h+var_208], rbx
0x140199d2b  mov     qword ptr [rsp+238h+var_210], rsi
0x140199d30  mov     [rsp+238h+Timeout], rax
0x140199d35  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x140199d3c  mov     edx, 40000h
0x140199d41  xor     ecx, ecx
0x140199d43  mov     r8d, 0FFFFFFFFh
0x140199d49  call    DxgkLogInternalTriageEvent
0x140199d4e  jmp     loc_14019AAD9
0x140199d53  mov     [rsp+238h+Object], rbx
0x140199d58  mov     [rsp+238h+var_210], dil; bool
0x140199d5d  mov     byte ptr [rsp+238h+Timeout], bl; bool
0x140199d61  lea     r9, [rsp+238h+Object]; struct DXGCONTEXT **
0x140199d66  mov     r8, r15; struct DXGPROCESS *
0x140199d69  mov     edx, [r12+4]; unsigned int
0x140199d6e  lea     rcx, [rsp+238h+var_178]; this
0x140199d76  call    ??0DXGCONTEXTBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGCONTEXT@@_N2@Z; DXGCONTEXTBYHANDLE::DXGCONTEXTBYHANDLE(uint,DXGPROCESS *,DXGCONTEXT * *,bool,bool)
0x140199d7b  mov     r14, [rsp+238h+Object]
0x140199d80  test    r14, r14
0x140199d83  jnz     short loc_140199DB6
0x140199d85  mov     r8d, [r12+4]
0x140199d8a  mov     rsi, 0FFFFFFFFC000000Dh
0x140199d91  mov     r9, rsi
0x140199d94  mov     rdx, r15
0x140199d97  lea     ecx, [r14+3]
0x140199d9b  call    cs:__imp_WdLogSingleEntry3
0x140199da2  nop     dword ptr [rax+rax+00h]
0x140199da7  mov     cs:WdLogGlobalForLineNumber, 354Dh
0x140199db1  jmp     loc_14019AACC
0x140199db6  mov     rdx, [r14+10h]
0x140199dba  cmp     rdx, r13
0x140199dbd  jz      short loc_140199E22
0x140199dbf  mov     rsi, 0FFFFFFFFC000000Dh
0x140199dc6  mov     r9, rsi
0x140199dc9  mov     r8, r13
0x140199dcc  mov     ecx, 2
0x140199dd1  call    cs:__imp_WdLogSingleEntry3
0x140199dd8  nop     dword ptr [rax+rax+00h]
0x140199ddd  mov     cs:WdLogGlobalForLineNumber, 3554h
0x140199de7  mov     [rsp+238h+var_1F8], rbx
0x140199dec  mov     [rsp+238h+var_200], rbx
0x140199df1  mov     [rsp+238h+var_208], rsi
0x140199df6  mov     qword ptr [rsp+238h+var_210], r13
0x140199dfb  mov     rax, [r14+10h]
0x140199dff  mov     [rsp+238h+Timeout], rax
0x140199e04  lea     r9, aContextDevice0; "Context device 0x%p does not match user"...
0x140199e0b  mov     edx, 40000h
0x140199e10  xor     ecx, ecx
0x140199e12  mov     r8d, 0FFFFFFFFh
0x140199e18  call    DxgkLogInternalTriageEvent
0x140199e1d  jmp     loc_14019AACC
0x140199e22  mov     rax, [r13+10h]
0x140199e26  mov     rcx, [rax+10h]
0x140199e2a  cmp     [rcx+0D1h], bl
0x140199e30  jz      short loc_140199E58
0x140199e32  add     rcx, 12B8h; this
0x140199e39  mov     [rsp+238h+Timeout], r12; struct _D3DKMT_UPDATEGPUVIRTUALADDRESS *
0x140199e3e  mov     r9d, [r14+1Ch]; unsigned int
0x140199e42  mov     r8d, [r13+1D8h]; unsigned int
0x140199e49  mov     rdx, r15; struct DXGPROCESS *
0x140199e4c  call    ?VmBusSendUpdateGpuVirtualAddress@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAVDXGPROCESS@@IIPEAU_D3DKMT_UPDATEGPUVIRTUALADDRESS@@@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendUpdateGpuVirtualAddress(DXGPROCESS *,uint,uint,_D3DKMT_UPDATEGPUVIRTUALADDRESS *)
0x140199e51  mov     esi, eax
0x140199e53  jmp     loc_14019AACC
0x140199e58  mov     rdx, r13; struct DXGDEVICE *
0x140199e5b  lea     rcx, [rsp+238h+var_150]; this
0x140199e63  call    ??0DXGDEVICEACCESSLOCKSHARED@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICEACCESSLOCKSHARED::DXGDEVICEACCESSLOCKSHARED(DXGDEVICE *)
0x140199e68  lea     rdx, [r14+1B8h]; struct DXGPUSHLOCK *
0x140199e6f  lea     rcx, [rsp+238h+var_140]; this
0x140199e77  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x140199e7c  mov     byte ptr [rsp+238h+Timeout], bl
0x140199e80  xor     r8d, r8d
0x140199e83  mov     rdx, r13
0x140199e86  lea     rcx, [rsp+238h+var_D8]
0x140199e8e  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x140199e93  xor     edx, edx; char *
0x140199e95  lea     rcx, [rsp+238h+var_D8]; this
0x140199e9d  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x140199ea2  movsxd  rsi, eax
0x140199ea5  test    eax, eax
0x140199ea7  jns     short loc_140199ECC
0x140199ea9  mov     rdx, rsi
0x140199eac  mov     ecx, 3
0x140199eb1  call    cs:__imp_WdLogSingleEntry1
0x140199eb8  nop     dword ptr [rax+rax+00h]
0x140199ebd  mov     cs:WdLogGlobalForLineNumber, 356Fh
0x140199ec7  jmp     loc_14019AAA5
0x140199ecc  mov     rax, [r13+10h]
0x140199ed0  mov     rcx, [rax+10h]
0x140199ed4  mov     eax, [rcx+0A24h]
0x140199eda  test    al, 40h
0x140199edc  jz      loc_14019AA80
0x140199ee2  mov     rcx, r14; this
0x140199ee5  call    ?GetVidSchCompanionContext@DXGCONTEXT@@QEAAPEAU_VIDSCH_CONTEXT@@XZ; DXGCONTEXT::GetVidSchCompanionContext(void)
0x140199eea  test    rax, rax
0x140199eed  jnz     short loc_140199F1F
0x140199eef  mov     r8d, [r12+4]
0x140199ef4  mov     rsi, 0FFFFFFFFC000000Dh
0x140199efb  mov     r9, rsi
0x140199efe  mov     rdx, r15
0x140199f01  lea     ecx, [rax+3]
0x140199f04  call    cs:__imp_WdLogSingleEntry3
0x140199f0b  nop     dword ptr [rax+rax+00h]
0x140199f10  mov     cs:WdLogGlobalForLineNumber, 357Dh
0x140199f1a  jmp     loc_14019AAA5
0x140199f1f  cmp     [r14+110h], rbx
0x140199f26  jnz     short loc_140199F6F
0x140199f28  mov     rcx, r14; this
0x140199f2b  call    ?GetVidSchCompanionContext@DXGCONTEXT@@QEAAPEAU_VIDSCH_CONTEXT@@XZ; DXGCONTEXT::GetVidSchCompanionContext(void)
0x140199f30  mov     r10, rax
0x140199f33  test    rax, rax
0x140199f36  jz      short loc_140199F6F
0x140199f38  mov     rdx, [r14+10h]
0x140199f3c  mov     rcx, [rdx+10h]
0x140199f40  mov     r8, [rcx+2F8h]
0x140199f47  mov     r9, [r8+8]
0x140199f4b  mov     rax, [r9+3B8h]
0x140199f52  mov     r8, r10
0x140199f55  mov     rdx, [rdx+318h]
0x140199f5c  mov     rcx, [rcx+300h]
0x140199f63  call    _guard_dispatch_icall
0x140199f68  mov     [r14+110h], rax
0x140199f6f  mov     rax, [r14+110h]
0x140199f76  mov     [rsp+238h+var_118], rax
0x140199f7e  test    rax, rax
0x140199f81  jnz     short loc_140199FB3
0x140199f83  mov     r8d, [r12+4]
0x140199f88  mov     rsi, 0FFFFFFFFC000000Dh
0x140199f8f  mov     r9, rsi
0x140199f92  mov     rdx, r15
0x140199f95  lea     ecx, [rax+3]
0x140199f98  call    cs:__imp_WdLogSingleEntry3
0x140199f9f  nop     dword ptr [rax+rax+00h]
0x140199fa4  mov     cs:WdLogGlobalForLineNumber, 3585h
0x140199fae  jmp     loc_14019AAA5
0x140199fb3  mov     edx, [r12+0Ch]
0x140199fb8  mov     r14d, edx
0x140199fbb  shl     r14, 6
0x140199fbf  mov     esi, 0FFFFFFFFh
0x140199fc4  cmp     r14, rsi
0x140199fc7  ja      loc_14019A9EE
0x140199fcd  mov     eax, 40h ; '@'
0x140199fd2  mul     rdx
0x140199fd5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140199fdc  cmovb   rax, rcx
0x140199fe0  mov     edx, 4B677844h
0x140199fe5  mov     r8d, 100h
0x140199feb  mov     rcx, rax
0x140199fee  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140199ff3  mov     [rsp+238h+Object], rax
0x140199ff8  test    rax, rax
0x140199ffb  jnz     loc_14019A0C6
0x14019a001  mov     r15, 0FFFFFFFFC0000017h
0x14019a008  mov     rdx, r15
0x14019a00b  lea     ecx, [rax+6]
0x14019a00e  call    cs:__imp_WdLogSingleEntry1
0x14019a015  nop     dword ptr [rax+rax+00h]
0x14019a01a  mov     cs:WdLogGlobalForLineNumber, 359Ch
0x14019a024  mov     [rsp+238h+var_1F8], rbx
0x14019a029  mov     [rsp+238h+var_200], rbx
0x14019a02e  mov     [rsp+238h+var_208], rbx
0x14019a033  mov     qword ptr [rsp+238h+var_210], rbx
0x14019a038  mov     [rsp+238h+Timeout], r15
0x14019a03d  lea     r9, aFailedToAlloca_134; "Failed to allocate memory for D3DDDI_UP"...
0x14019a044  mov     r8d, esi
0x14019a047  mov     edx, 40001h
0x14019a04c  xor     ecx, ecx
0x14019a04e  call    DxgkLogInternalTriageEvent
0x14019a053  lea     rcx, [rsp+238h+var_D8]; this
0x14019a05b  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x14019a060  lea     rcx, [rsp+238h+var_140]; this
0x14019a068  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14019a06d  lea     rcx, [rsp+238h+var_150]; this
0x14019a075  call    ??1DXGDEVICEACCESSLOCKSHARED@@QEAA@XZ; DXGDEVICEACCESSLOCKSHARED::~DXGDEVICEACCESSLOCKSHARED(void)
0x14019a07a  lea     rcx, [rsp+238h+var_178]; this
0x14019a082  call    ??1DXGCONTEXTBYHANDLE@@QEAA@XZ; DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE(void)
0x14019a087  lea     rcx, [rsp+238h+var_1B0]; this
0x14019a08f  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x14019a094  lea     rcx, [rsp+238h+var_1E0]; this
0x14019a099  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14019a09e  cmp     [rsp+238h+var_1D0], bl
0x14019a0a2  jz      short loc_14019A0BE
0x14019a0a4  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
  ... truncated ...
```
