# DXGDEVICE::OpenResource<_D3DKMT_OPENRESOURCE>(_D3DKMT_OPENRESOURCE *,uint,_DXGSHAREDALLOCOBJECT *,uint,COREDEVICEACCESS *,int,_EPROCESS *,uint *,unsigned __int64 *)

- ea: `0x1403d9f70`
- end: `0x1403dab2d`
- name: `??$OpenResource@U_D3DKMT_OPENRESOURCE@@@DXGDEVICE@@QEAAJPEAU_D3DKMT_OPENRESOURCE@@IPEAU_DXGSHAREDALLOCOBJECT@@IPEAVCOREDEVICEACCESS@@HPEAU_EPROCESS@@PEAIPEA_K@Z`
- size: `3005`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *this@<rcx>, unsigned int, struct COREDEVICEACCESS *, unsigned int, struct _EPROCESS *, unsigned int *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14024fd98`
- `0x140250570`
- `0x14031bb50`
- `0x1403d9960`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400160e4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001cbe0`
- `0x14001d070`
- `0x14002d9f0`
- `0x14003bab8`
- `0x140055d4c`
- `0x14006dc88`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x140291280`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x14036f9f0`
- `0x14036fd90`
- `0x140377040`
- `0x1403d9f70`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403da151`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403da151`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403da145`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403da145`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403da9da`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403da9da`
- `watchdog!WdLogSingleEntry4` at `0x1403da20d`
- `watchdog!WdLogSingleEntry4` at `0x1403da2f0`
- `watchdog!WdLogSingleEntry4` at `0x1403da3f5`
- `watchdog!WdLogSingleEntry4` at `0x1403da20d`
- `watchdog!WdLogSingleEntry4` at `0x1403da2f0`
- `watchdog!WdLogSingleEntry4` at `0x1403da3f5`
- `watchdog!WdLogSingleEntry2` at `0x1403da268`
- `watchdog!WdLogSingleEntry2` at `0x1403da4f4`
- `watchdog!WdLogSingleEntry2` at `0x1403da521`
- `watchdog!WdLogSingleEntry2` at `0x1403daab5`
- `watchdog!WdLogSingleEntry2` at `0x1403da268`
- `watchdog!WdLogSingleEntry2` at `0x1403da4f4`
- `watchdog!WdLogSingleEntry2` at `0x1403da521`
- `watchdog!WdLogSingleEntry2` at `0x1403daab5`
- `watchdog!WdLogSingleEntry3` at `0x1403da178`
- `watchdog!WdLogSingleEntry3` at `0x1403da36c`
- `watchdog!WdLogSingleEntry3` at `0x1403da178`
- `watchdog!WdLogSingleEntry3` at `0x1403da36c`
- `watchdog!WdLogSingleEntry0` at `0x1403d9fc9`
- `watchdog!WdLogSingleEntry0` at `0x1403da0e7`
- `watchdog!WdLogSingleEntry0` at `0x1403da5eb`
- `watchdog!WdLogSingleEntry0` at `0x1403da6eb`
- `watchdog!WdLogSingleEntry0` at `0x1403da800`
- `watchdog!WdLogSingleEntry0` at `0x1403da85f`
- `watchdog!WdLogSingleEntry0` at `0x1403da8f9`
- `watchdog!WdLogSingleEntry0` at `0x1403daa5a`
- `watchdog!WdLogSingleEntry0` at `0x1403d9fc9`
- `watchdog!WdLogSingleEntry0` at `0x1403da0e7`
- `watchdog!WdLogSingleEntry0` at `0x1403da5eb`
- `watchdog!WdLogSingleEntry0` at `0x1403da6eb`
- `watchdog!WdLogSingleEntry0` at `0x1403da800`
- `watchdog!WdLogSingleEntry0` at `0x1403da85f`
- `watchdog!WdLogSingleEntry0` at `0x1403da8f9`
- `watchdog!WdLogSingleEntry0` at `0x1403daa5a`
- `watchdog!WdLogSingleEntry1` at `0x1403da1cc`
- `watchdog!WdLogSingleEntry1` at `0x1403da5c6`
- `watchdog!WdLogSingleEntry1` at `0x1403da1cc`
- `watchdog!WdLogSingleEntry1` at `0x1403da5c6`

## string_xrefs

- `0x1403da5fc`: `KMCreateAlloc.hResource != 0`
- `0x1403da6fc`: `!pSharedResource->m_NtSecuritySharing || pSharedAllocObject`

## pseudocode

```c
__int64 __fastcall DXGDEVICE::OpenResource<_D3DKMT_OPENRESOURCE>(
        ADAPTER_RENDER **this,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        struct COREDEVICEACCESS *a6,
        unsigned int a7,
        struct _EPROCESS *a8,
        unsigned int *a9,
        unsigned __int64 *a10)
{
  unsigned int v10; // r12d
  __int64 v11; // rdi
  struct DXGPROCESS *v14; // r13
  int v15; // r15d
  struct DXGGLOBAL *Global; // rax
  __int64 ObjectA; // rbx
  int v18; // eax
  __int64 v19; // rbx
  __int64 v20; // r12
  unsigned int v21; // eax
  __int64 v22; // rbx
  int v23; // edx
  __int64 v24; // r8
  int v25; // edi
  __int64 v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // edx
  unsigned int v29; // eax
  unsigned int v30; // ecx
  __int64 v31; // rax
  D3DDDI_ALLOCATIONINFO *v32; // rax
  UINT v33; // ecx
  char *v34; // r8
  D3DKMT_CREATESTANDARDALLOCATION *v35; // r9
  size_t v36; // rdx
  unsigned int v37; // eax
  unsigned int v38; // r15d
  char *v39; // r9
  _QWORD *v40; // rdi
  unsigned int v41; // ecx
  const void *v42; // rdx
  __int64 v43; // rdx
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // rax
  D3DKMT_HANDLE hResource; // eax
  unsigned __int64 v48; // rcx
  unsigned int v49; // r10d
  _DWORD *v50; // r9
  __int64 v51; // rax
  __int64 v52; // rax
  unsigned int *v53; // r12
  unsigned int v54; // edx
  unsigned int v55; // r8d
  __int64 v56; // rax
  DXG_GUEST_VIRTUALGPU_VMBUS *v57; // rcx
  int v58; // r9d
  struct DXGPROCESS *v59; // r15
  unsigned int v60; // eax
  __int64 v61; // r9
  int v62; // ecx
  struct DXGRESOURCE *v63; // rdx
  unsigned int v64; // r12d
  unsigned int v65; // eax
  __int64 v66; // r9
  int v67; // ecx
  struct DXGALLOCATION *v68; // rdx
  char *v69; // r15
  unsigned int v70; // eax
  __int64 v71; // r13
  __int64 v72; // rbx
  unsigned int CurrentProcessId; // eax
  int v74; // r8d
  int v76; // [rsp+38h] [rbp-C8h]
  int v77; // [rsp+68h] [rbp-98h]
  unsigned int v78; // [rsp+70h] [rbp-90h]
  char v79[8]; // [rsp+80h] [rbp-80h] BYREF
  char v80; // [rsp+88h] [rbp-78h]
  __int64 v81; // [rsp+90h] [rbp-70h]
  __int64 v82; // [rsp+98h] [rbp-68h]
  __int64 v83; // [rsp+A0h] [rbp-60h]
  __int64 v84; // [rsp+A8h] [rbp-58h]
  struct DXGPROCESS *Current; // [rsp+B0h] [rbp-50h]
  struct _EX_RUNDOWN_REF *v86; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v87; // [rsp+C0h] [rbp-40h]
  struct _D3DKMT_CREATEALLOCATION v88; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v89[80]; // [rsp+120h] [rbp+20h] BYREF
  char *v90; // [rsp+180h] [rbp+80h] BYREF
  void *v91; // [rsp+198h] [rbp+98h]

  v10 = 0;
  v11 = a3;
  v91 = 0;
  memset(&v88, 0, sizeof(v88));
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(this[2]) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 7874;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      7874,
      0,
      0,
      0,
      0);
  }
  Current = DXGPROCESS::GetCurrent();
  v14 = Current;
  v15 = *((_DWORD *)Current + 102);
  DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)v79);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v79);
  if ( !(_DWORD)v11 )
  {
    v25 = -1073741811;
    WdLogSingleEntry2(2, this);
    WdLogGlobalForLineNumber = 7927;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Device 0x%I64x: Caller passed NULL for both the NT object and the global shared handle. Returning 0x%I64x",
      (__int64)this,
      -1073741811,
      0,
      0,
      0);
    goto LABEL_106;
  }
  LOBYTE(v15) = BYTE1(v15) & 1;
  if ( (v15 & 0x100) != 0 )
  {
    v18 = *((_DWORD *)v14 + 102);
    if ( (v18 & 0x100) != 0 )
      v19 = *((_QWORD *)v14 + 75);
    else
      v19 = (unsigned __int64)v14 & -(__int64)((v18 & 0x80u) != 0);
    v20 = v19 + 248;
    DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v19 + 248));
    v21 = ((unsigned int)v11 >> 6) & 0xFFFFFF;
    if ( v21 < *(_DWORD *)(v19 + 296)
      && (v22 = *(_QWORD *)(v19 + 280), (((unsigned int)v11 >> 25) & 0x60) == (*(_BYTE *)(v22 + 16LL * v21 + 8) & 0x60))
      && (*(_DWORD *)(v22 + 16LL * v21 + 8) & 0x2000) == 0
      && (v23 = *(_DWORD *)(v22 + 16LL * v21 + 8) & 0x1F) != 0 )
    {
      if ( v23 == 2 )
      {
        ObjectA = *(_QWORD *)(v22 + 16LL * v21);
      }
      else
      {
        WdLogSingleEntry0(2);
        ObjectA = 0;
        WdLogGlobalForLineNumber = 318;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
      }
    }
    else
    {
      ObjectA = 0;
    }
    _InterlockedDecrement((volatile signed __int32 *)(v20 + 16));
    ExReleasePushLockSharedEx(v20, 0);
    KeLeaveCriticalRegion();
    v10 = 0;
  }
  else
  {
    Global = DXGGLOBAL::GetGlobal();
    ObjectA = DXGGLOBAL::GetObjectA(Global, (unsigned int)v11, 2);
  }
  if ( !ObjectA )
  {
    v24 = v11;
    v25 = -1073741811;
    WdLogSingleEntry3(3, this, v24, -1073741811);
    WdLogGlobalForLineNumber = 7918;
LABEL_106:
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v79);
    goto LABEL_107;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(ObjectA + 136) - 44LL) & 2) != 0 )
  {
    v26 = *((_QWORD *)this[5] + 11);
    if ( v26 )
    {
      if ( !(*(unsigned int (**)(void))(v26 + 224))() )
      {
        v25 = -1073741790;
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 7937;
        goto LABEL_106;
      }
    }
  }
  v27 = *(_DWORD *)(a2 + 8);
  v28 = *(_DWORD *)(ObjectA + 132);
  if ( v28 != v27 )
  {
    v25 = -1073741811;
    WdLogSingleEntry4(2, this, v28, v27, -1073741811);
    WdLogGlobalForLineNumber = 7949;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Device 0x%I64x: Caller specified incorrect number of allocations, should have been 0x%I64x but was 0"
                     "x%I64x, returning 0x%I64x",
      (__int64)this,
      *(unsigned int *)(ObjectA + 132),
      *(unsigned int *)(a2 + 8),
      -1073741811,
      0);
    goto LABEL_106;
  }
  if ( (*(_DWORD *)(ObjectA + 12) & 4) != 0 )
  {
    v25 = -1073741811;
    WdLogSingleEntry2(2, this);
    WdLogGlobalForLineNumber = 7960;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Device 0x%I64x: PrivateRuntimeData has been marked as invalid, returning 0x%I64x",
      (__int64)this,
      -1073741811,
      0,
      0,
      0);
    if ( v80 )
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v79);
    goto LABEL_107;
  }
  if ( !(_BYTE)v15 )
  {
    v29 = *(_DWORD *)(ObjectA + 112);
    v30 = *(_DWORD *)(a2 + 32);
    if ( v30 != v29 )
    {
      v25 = -1073741811;
      WdLogSingleEntry4(3, this, v30, v29, -1073741811);
      WdLogGlobalForLineNumber = 7974;
      goto LABEL_106;
    }
    if ( v29 )
      memmove(*(void **)(a2 + 24), *(const void **)(ObjectA + 104), *(unsigned int *)(ObjectA + 112));
  }
  v31 = 96LL * *(unsigned int *)(a2 + 8);
  if ( !is_mul_ok(*(unsigned int *)(a2 + 8), 0x60u) )
    v31 = -1;
  v32 = (D3DDDI_ALLOCATIONINFO *)operator new[](v31, 1265072196, 256);
  v33 = *(_DWORD *)(a2 + 8);
  v34 = (char *)v32;
  v91 = v32;
  if ( !v32 )
  {
    WdLogSingleEntry3(3, this, v33, -1073741801);
    WdLogGlobalForLineNumber = 7993;
LABEL_38:
    v25 = -1073741801;
    goto LABEL_106;
  }
  v35 = *(D3DKMT_CREATESTANDARDALLOCATION **)(a2 + 40);
  v36 = *(unsigned int *)(a2 + 48);
  v88.hDevice = *(_DWORD *)a2;
  v88.NumAllocations = v33;
  v88.hGlobalShare = v11;
  v88.pStandardAllocation = v35;
  v88.Flags = (D3DKMT_CREATEALLOCATIONFLAGS)(*(_DWORD *)&v88.Flags & 0xFFFFFF3E | 1);
  v88.PrivateDriverDataSize = v36;
  v88.pAllocationInfo = v32;
  *(_DWORD *)&v88.Flags ^= (*(_DWORD *)&v88.Flags ^ (32 * *(_DWORD *)(ObjectA + 12))) & 0x100000;
  if ( !(_BYTE)v15 )
  {
    v37 = *(_DWORD *)(ObjectA + 128);
    if ( (_DWORD)v36 != v37 )
    {
      v25 = -1073741811;
      WdLogSingleEntry4(3, this, (unsigned int)v36, v37, -1073741811);
      WdLogGlobalForLineNumber = 8020;
      goto LABEL_106;
    }
  }
  v38 = 0;
  if ( (_DWORD)v36 )
  {
    memmove(v35, *(const void **)(ObjectA + 120), v36);
    v34 = (char *)v91;
  }
  v39 = *(char **)(a2 + 56);
  v40 = *(_QWORD **)(ObjectA + 136);
  while ( 1 )
  {
    v90 = v39;
    if ( v10 >= *(_DWORD *)(a2 + 8) )
      break;
    v41 = *((_DWORD *)v40 - 2);
    if ( v41 + v38 < v38 )
    {
      v25 = -1073741675;
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 8046;
      goto LABEL_106;
    }
    if ( v41 + v38 > *(_DWORD *)(a2 + 64) )
    {
      WdLogSingleEntry2(3, this);
      WdLogGlobalForLineNumber = 8055;
      goto LABEL_38;
    }
    v42 = (const void *)*(v40 - 2);
    if ( v42 )
    {
      memmove(v39, v42, v41);
      v39 = v90;
      v34 = (char *)v91;
    }
    v43 = 96LL * v10;
    *(_DWORD *)&v34[v43] = 0;
    *(_QWORD *)&v34[v43 + 8] = 0;
    v44 = *((_DWORD *)v40 - 11);
    *(_DWORD *)&v34[v43 + 32] = 0;
    *(_DWORD *)&v34[v43 + 28] = (v44 >> 6) & 0xF;
    v45 = *((_DWORD *)v40 - 11);
    *(_QWORD *)&v34[v43 + 16] = v39;
    *(_DWORD *)&v34[v43 + 32] = v45 & 1 | (((v45 | (v45 >> 12)) & 2) != 0);
    *(_DWORD *)&v34[v43 + 24] = *((_DWORD *)v40 - 2);
    v46 = *((unsigned int *)v40 - 2);
    v40 = (_QWORD *)*v40;
    v38 += v46;
    v39 += v46;
    ++v10;
  }
  if ( v80 )
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v79);
  v25 = DXGDEVICE::CreateAllocation((DXGDEVICE *)this, &v88, 0, 1u, 0, 0, a6, a5, a8, a9, a10, 0, 0, 0, 0);
  if ( v25 < 0 )
  {
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 8086;
    goto LABEL_107;
  }
  hResource = v88.hResource;
  if ( !v88.hResource )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 8091;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"KMCreateAlloc.hResource != 0", 8091, 0, 0, 0, 0);
    hResource = v88.hResource;
  }
  v48 = *(unsigned int *)(a2 + 8);
  v49 = 0;
  v50 = *(_DWORD **)(a2 + 16);
  *(_DWORD *)(a2 + 64) = v38;
  for ( *(_DWORD *)(a2 + 68) = hResource; v49 < (unsigned int)v48; v48 = *(unsigned int *)(a2 + 8) )
  {
    v51 = v49++;
    *v50 = *(&v88.pAllocationInfo->hAllocation + 24 * v51);
    v50 += 20;
    *((_QWORD *)v50 - 9) = *(_QWORD *)(a2 + 56)
                         + (unsigned int)(*((_DWORD *)&v88.pAllocationInfo->pPrivateDriverData + 24 * v51)
                                        - *(_DWORD *)(a2 + 56));
    *(v50 - 16) = *(&v88.pAllocationInfo->PrivateDriverDataSize + 24 * v51);
  }
  if ( (*((_BYTE *)this + 1917) & 1) != 0 )
  {
    v52 = 4 * v48;
    if ( !is_mul_ok(v48, 4u) )
      v52 = -1;
    v81 = operator new[](v52, 1265072196, 256);
    v53 = (unsigned int *)v81;
    if ( !v81 )
    {
      v25 = -1073741801;
      goto LABEL_107;
    }
    if ( (*(_DWORD *)(ObjectA + 12) & 8) != 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 8120;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"!pSharedResource->m_NtSecuritySharing || pSharedAllocObject",
        8120,
        0,
        0,
        0,
        0);
    }
    v54 = *(_DWORD *)(a2 + 64);
    v55 = *(_DWORD *)(a2 + 8);
    v56 = 40;
    v57 = (DXG_GUEST_VIRTUALGPU_VMBUS *)(*((_QWORD *)this[2] + 2) + 4776LL);
    v58 = *(_DWORD *)(ObjectA + 12) >> 3;
    a7 = 0;
    if ( (v58 & 1) == 0 )
      v56 = ObjectA + 28;
    v59 = Current;
    v25 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendOpenResource(
            v57,
            Current,
            (struct DXGDEVICE *)this,
            v58 & 1,
            *(_DWORD *)v56,
            v55,
            v54,
            &a7,
            v53);
    if ( v25 < 0 )
    {
LABEL_104:
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v53);
      goto LABEL_107;
    }
    DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v89, v59);
    v60 = (*(_DWORD *)(a2 + 68) >> 6) & 0xFFFFFF;
    if ( v60 < *((_DWORD *)v59 + 74) )
    {
      v61 = *((_QWORD *)v59 + 35);
      if ( ((*(_DWORD *)(a2 + 68) >> 25) & 0x60) == (*(_BYTE *)(v61 + 16LL * v60 + 8) & 0x60)
        && (*(_DWORD *)(v61 + 16LL * v60 + 8) & 0x2000) == 0 )
      {
        v62 = *(_DWORD *)(v61 + 16LL * v60 + 8) & 0x1F;
        if ( v62 )
        {
          if ( v62 == 4 )
          {
            v63 = *(struct DXGRESOURCE **)(v61 + 16LL * v60);
            goto LABEL_78;
          }
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
    }
    v63 = 0;
LABEL_78:
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v86, v63);
    if ( v86 )
    {
      v64 = 0;
      HIDWORD(v86[2].Ptr) = a7;
      while ( v64 < *(_DWORD *)(a2 + 8) )
      {
        v65 = (*(_DWORD *)(*(_QWORD *)(a2 + 16) + 80LL * v64) >> 6) & 0xFFFFFF;
        if ( v65 < *((_DWORD *)v59 + 74)
          && (v66 = *((_QWORD *)v59 + 35),
              ((*(_DWORD *)(*(_QWORD *)(a2 + 16) + 80LL * v64) >> 25) & 0x60) == (*(_BYTE *)(v66 + 16LL * v65 + 8) & 0x60))
          && (*(_DWORD *)(v66 + 16LL * v65 + 8) & 0x2000) == 0
          && (v67 = *(_DWORD *)(v66 + 16LL * v65 + 8) & 0x1F) != 0 )
        {
          if ( v67 == 5 )
          {
            v68 = *(struct DXGALLOCATION **)(v66 + 16LL * v65);
          }
          else
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 318;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            v68 = 0;
          }
        }
        else
        {
          v68 = 0;
        }
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v90, v68);
        v69 = v90;
        if ( !v90 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 8148;
          v25 = -1073741811;
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v90);
          break;
        }
        v70 = *(_DWORD *)(v81 + 4LL * v64);
        v90[128] |= 4u;
        *((_DWORD *)v69 + 5) = v70;
        a7 = v70;
        if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
        {
          v71 = *((_QWORD *)v69 + 5);
          if ( v71 )
          {
            v82 = *(_QWORD *)(v71 + 48);
            v83 = *(unsigned int *)(v71 + 16);
          }
          else
          {
            v82 = 0;
            v83 = 0;
          }
          v87 = *((unsigned int *)v69 + 4);
          if ( v71 )
            v84 = *(_QWORD *)(v71 + 56);
          else
            v84 = 0;
          v72 = *((_QWORD *)this[2] + 2);
          CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
          McTemplateK0ppppppppppppq_EtwWriteTransfer(
            v84,
            (unsigned int)EventCreateDeviceAllocation,
            v74,
            CurrentProcessId,
            (char)this,
            v72,
            (char)v69,
            v76,
            v71,
            v84,
            v87,
            v83,
            v82,
            v77,
            v78,
            a7);
        }
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v90);
        v59 = Current;
        ++v64;
      }
      v53 = (unsigned int *)v81;
    }
    else
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 8137;
      v25 = -1073741811;
    }
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v86);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v89);
    goto LABEL_104;
  }
LABEL_107:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v91);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1403d9f70  mov     [rsp-8+arg_8], rbx
0x1403d9f75  mov     [rsp-8+arg_18], r9
0x1403d9f7a  push    rbp
0x1403d9f7b  push    rsi
0x1403d9f7c  push    rdi
0x1403d9f7d  push    r12
0x1403d9f7f  push    r13
0x1403d9f81  push    r14
0x1403d9f83  push    r15
0x1403d9f85  lea     rbp, [rsp-40h]
0x1403d9f8a  sub     rsp, 140h
0x1403d9f91  xor     r12d, r12d
0x1403d9f94  mov     edi, r8d
0x1403d9f97  mov     r14, rdx
0x1403d9f9a  mov     [rbp+70h+arg_18], r12
0x1403d9fa1  mov     rsi, rcx
0x1403d9fa4  xor     edx, edx; Val
0x1403d9fa6  lea     rcx, [rbp+70h+var_A0]; void *
0x1403d9faa  lea     r8d, [r12+48h]; Size
0x1403d9faf  call    memset
0x1403d9fb4  mov     rcx, [rsi+10h]; this
0x1403d9fb8  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x1403d9fbd  or      ebx, 0FFFFFFFFh
0x1403d9fc0  test    al, al
0x1403d9fc2  jnz     short loc_1403DA00F
0x1403d9fc4  lea     ecx, [r12+1]
0x1403d9fc9  call    cs:__imp_WdLogSingleEntry0
0x1403d9fd0  nop     dword ptr [rax+rax+00h]
0x1403d9fd5  mov     [rsp+170h+var_130], r12
0x1403d9fda  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x1403d9fe1  mov     [rsp+170h+var_138], r12
0x1403d9fe6  mov     eax, 1EC2h
0x1403d9feb  mov     [rsp+170h+var_140], r12
0x1403d9ff0  mov     r8d, ebx
0x1403d9ff3  mov     [rsp+170h+var_148], r12
0x1403d9ff8  mov     edx, 40002h
0x1403d9ffd  xor     ecx, ecx
0x1403d9fff  mov     [rsp+170h+var_150], rax
0x1403da004  mov     cs:WdLogGlobalForLineNumber, eax
0x1403da00a  call    DxgkLogInternalTriageEvent
0x1403da00f  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1403da014  lea     rcx, [rbp+70h+var_F0]; this
0x1403da018  mov     [rbp+70h+var_C0], rax
0x1403da01c  mov     r13, rax
0x1403da01f  mov     r15d, [rax+198h]
0x1403da026  call    ??0DXGGLOBALSHAREMUTEX@@QEAA@XZ; DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX(void)
0x1403da02b  lea     rcx, [rbp+70h+var_F0]; this
0x1403da02f  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1403da034  test    edi, edi
0x1403da036  jz      loc_1403DAAA3
0x1403da03c  shr     r15d, 8
0x1403da040  and     r15b, 1
0x1403da044  jnz     short loc_1403DA066
0x1403da046  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1403da04b  mov     r13d, 2
0x1403da051  mov     edx, edi
0x1403da053  mov     r8d, r13d
0x1403da056  mov     rcx, rax
0x1403da059  call    ?GetObjectA@DXGGLOBAL@@QEAAPEAXIW4_HMGRENTRY_TYPE@@_N@Z; DXGGLOBAL::GetObjectA(uint,_HMGRENTRY_TYPE,bool)
0x1403da05e  mov     rbx, rax
0x1403da061  jmp     loc_1403DA160
0x1403da066  mov     eax, [r13+198h]
0x1403da06d  bt      eax, 8
0x1403da071  jnb     short loc_1403DA07C
0x1403da073  mov     rbx, [r13+258h]
0x1403da07a  jmp     short loc_1403DA086
0x1403da07c  and     al, 80h
0x1403da07e  neg     al
0x1403da080  sbb     rbx, rbx
0x1403da083  and     rbx, r13
0x1403da086  lea     r12, [rbx+0F8h]
0x1403da08d  mov     rcx, r12; this
0x1403da090  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x1403da095  mov     eax, edi
0x1403da097  mov     r13d, 2
0x1403da09d  shr     eax, 6
0x1403da0a0  and     eax, 0FFFFFFh
0x1403da0a5  cmp     eax, [rbx+128h]
0x1403da0ab  jnb     loc_1403DA138
0x1403da0b1  mov     rbx, [rbx+118h]
0x1403da0b8  mov     ecx, edi
0x1403da0ba  mov     r8d, eax
0x1403da0bd  add     r8, r8
0x1403da0c0  shr     ecx, 19h
0x1403da0c3  and     ecx, 60h
0x1403da0c6  mov     edx, [rbx+r8*8+8]
0x1403da0cb  mov     eax, edx
0x1403da0cd  and     eax, 60h
0x1403da0d0  cmp     cl, al
0x1403da0d2  jnz     short loc_1403DA138
0x1403da0d4  bt      edx, 0Dh
0x1403da0d8  jb      short loc_1403DA138
0x1403da0da  and     edx, 1Fh
0x1403da0dd  jz      short loc_1403DA138
0x1403da0df  cmp     edx, r13d
0x1403da0e2  jz      short loc_1403DA132
0x1403da0e4  mov     ecx, r13d
0x1403da0e7  call    cs:__imp_WdLogSingleEntry0
0x1403da0ee  nop     dword ptr [rax+rax+00h]
0x1403da0f3  xor     ebx, ebx
0x1403da0f5  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1403da0fc  mov     [rsp+170h+var_130], rbx
0x1403da101  mov     eax, 13Eh
0x1403da106  mov     [rsp+170h+var_138], rbx
0x1403da10b  or      r8d, 0FFFFFFFFh
0x1403da10f  mov     [rsp+170h+var_140], rbx
0x1403da114  mov     edx, 40000h
0x1403da119  mov     [rsp+170h+var_148], rbx
0x1403da11e  xor     ecx, ecx
0x1403da120  mov     [rsp+170h+var_150], rax
0x1403da125  mov     cs:WdLogGlobalForLineNumber, eax
0x1403da12b  call    DxgkLogInternalTriageEvent
0x1403da130  jmp     short loc_1403DA13A
0x1403da132  mov     rbx, [rbx+r8*8]
0x1403da136  jmp     short loc_1403DA13A
0x1403da138  xor     ebx, ebx
0x1403da13a  lock dec dword ptr [r12+10h]
0x1403da140  xor     edx, edx
0x1403da142  mov     rcx, r12
0x1403da145  call    cs:__imp_ExReleasePushLockSharedEx
0x1403da14c  nop     dword ptr [rax+rax+00h]
0x1403da151  call    cs:__imp_KeLeaveCriticalRegion
0x1403da158  nop     dword ptr [rax+rax+00h]
0x1403da15d  xor     r12d, r12d
0x1403da160  test    rbx, rbx
0x1403da163  jnz     short loc_1403DA193
0x1403da165  mov     r8, rdi
0x1403da168  lea     ecx, [rbx+3]
0x1403da16b  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da172  mov     rdx, rsi
0x1403da175  mov     r9, rdi
0x1403da178  call    cs:__imp_WdLogSingleEntry3
0x1403da17f  nop     dword ptr [rax+rax+00h]
0x1403da184  mov     cs:WdLogGlobalForLineNumber, 1EEEh
0x1403da18e  jmp     loc_1403DAAFA
0x1403da193  mov     rax, [rbx+88h]
0x1403da19a  mov     ecx, [rax-2Ch]
0x1403da19d  test    r13b, cl
0x1403da1a0  jz      short loc_1403DA1E7
0x1403da1a2  mov     rax, [rsi+28h]
0x1403da1a6  mov     rax, [rax+58h]
0x1403da1aa  test    rax, rax
0x1403da1ad  jz      short loc_1403DA1E7
0x1403da1af  mov     rax, [rax+0E0h]
0x1403da1b6  call    _guard_dispatch_icall
0x1403da1bb  test    eax, eax
0x1403da1bd  jnz     short loc_1403DA1E7
0x1403da1bf  mov     rdi, 0FFFFFFFFC0000022h
0x1403da1c6  lea     ecx, [rax+4]
0x1403da1c9  mov     rdx, rdi
0x1403da1cc  call    cs:__imp_WdLogSingleEntry1
0x1403da1d3  nop     dword ptr [rax+rax+00h]
0x1403da1d8  mov     cs:WdLogGlobalForLineNumber, 1F01h
0x1403da1e2  jmp     loc_1403DAAFA
0x1403da1e7  mov     eax, [r14+8]
0x1403da1eb  mov     edx, [rbx+84h]
0x1403da1f1  cmp     edx, eax
0x1403da1f3  jz      short loc_1403DA251
0x1403da1f5  mov     r8d, edx
0x1403da1f8  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da1ff  mov     rdx, rsi
0x1403da202  mov     [rsp+170h+var_150], rdi
0x1403da207  mov     r9d, eax
0x1403da20a  mov     ecx, r13d
0x1403da20d  call    cs:__imp_WdLogSingleEntry4
0x1403da214  nop     dword ptr [rax+rax+00h]
0x1403da219  mov     [rsp+170h+var_130], r12
0x1403da21e  lea     r9, aDevice0xI64xCa_1; "Device 0x%I64x: Caller specified incorr"...
0x1403da225  mov     cs:WdLogGlobalForLineNumber, 1F0Dh
0x1403da22f  or      r8d, 0FFFFFFFFh
0x1403da233  mov     eax, [r14+8]
0x1403da237  mov     ecx, [rbx+84h]
0x1403da23d  mov     [rsp+170h+var_138], rdi
0x1403da242  mov     [rsp+170h+var_140], rax
0x1403da247  mov     [rsp+170h+var_148], rcx
0x1403da24c  jmp     loc_1403DAAE9
0x1403da251  mov     eax, [rbx+0Ch]
0x1403da254  test    al, 4
0x1403da256  jz      short loc_1403DA2C6
0x1403da258  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da25f  mov     rdx, rsi
0x1403da262  mov     r8, rdi
0x1403da265  mov     ecx, r13d
0x1403da268  call    cs:__imp_WdLogSingleEntry2
0x1403da26f  nop     dword ptr [rax+rax+00h]
0x1403da274  mov     [rsp+170h+var_130], r12
0x1403da279  lea     r9, aDevice0xI64xPr; "Device 0x%I64x: PrivateRuntimeData has "...
0x1403da280  mov     [rsp+170h+var_138], r12
0x1403da285  or      r8d, 0FFFFFFFFh
0x1403da289  mov     [rsp+170h+var_140], r12
0x1403da28e  mov     edx, 40000h
0x1403da293  mov     [rsp+170h+var_148], rdi
0x1403da298  xor     ecx, ecx
0x1403da29a  mov     [rsp+170h+var_150], rsi
0x1403da29f  mov     cs:WdLogGlobalForLineNumber, 1F18h
0x1403da2a9  call    DxgkLogInternalTriageEvent
0x1403da2ae  cmp     [rbp+70h+var_E8], r12b
0x1403da2b2  jz      loc_1403DAB03
0x1403da2b8  lea     rcx, [rbp+70h+var_F0]; this
0x1403da2bc  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1403da2c1  jmp     loc_1403DAB03
0x1403da2c6  test    r15b, r15b
0x1403da2c9  jnz     short loc_1403DA31F
0x1403da2cb  mov     eax, [rbx+70h]
0x1403da2ce  mov     ecx, [r14+20h]
0x1403da2d2  cmp     ecx, eax
0x1403da2d4  jz      short loc_1403DA30B
0x1403da2d6  mov     r8d, ecx
0x1403da2d9  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da2e0  mov     ecx, 3
0x1403da2e5  mov     [rsp+170h+var_150], rdi
0x1403da2ea  mov     r9d, eax
0x1403da2ed  mov     rdx, rsi
0x1403da2f0  call    cs:__imp_WdLogSingleEntry4
0x1403da2f7  nop     dword ptr [rax+rax+00h]
0x1403da2fc  mov     cs:WdLogGlobalForLineNumber, 1F26h
0x1403da306  jmp     loc_1403DAAFA
0x1403da30b  test    eax, eax
0x1403da30d  jz      short loc_1403DA31F
0x1403da30f  mov     rdx, [rbx+68h]; Src
0x1403da313  mov     r8, rax; Size
0x1403da316  mov     rcx, [r14+18h]; void *
0x1403da31a  call    memmove
0x1403da31f  mov     ecx, [r14+8]
0x1403da323  mov     eax, 60h ; '`'
0x1403da328  mul     rcx
0x1403da32b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1403da332  mov     edx, 4B677844h
0x1403da337  mov     r8d, 100h
0x1403da33d  cmovb   rax, rcx
0x1403da341  mov     rcx, rax
0x1403da344  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1403da349  mov     ecx, [r14+8]
0x1403da34d  mov     r8, rax
0x1403da350  mov     [rbp+70h+arg_18], rax
0x1403da357  test    rax, rax
0x1403da35a  jnz     short loc_1403DA38C
0x1403da35c  mov     r8d, ecx
0x1403da35f  mov     r9, 0FFFFFFFFC0000017h
0x1403da366  lea     ecx, [rax+3]
0x1403da369  mov     rdx, rsi
0x1403da36c  call    cs:__imp_WdLogSingleEntry3
0x1403da373  nop     dword ptr [rax+rax+00h]
0x1403da378  mov     cs:WdLogGlobalForLineNumber, 1F39h
0x1403da382  mov     edi, 0C0000017h
0x1403da387  jmp     loc_1403DAAFA
0x1403da38c  mov     eax, [r14]
0x1403da38f  mov     r9, [r14+28h]
0x1403da393  mov     edx, [r14+30h]
0x1403da397  mov     [rbp+70h+var_A0.hDevice], eax
0x1403da39a  mov     [rbp+70h+var_A0.NumAllocations], ecx
0x1403da39d  mov     ecx, dword ptr [rbp+70h+var_A0.Flags.CreateResource]
0x1403da3a0  and     ecx, 0FFFFFF3Fh
0x1403da3a6  mov     [rbp+70h+var_A0.hGlobalShare], edi
0x1403da3a9  or      ecx, 1
0x1403da3ac  mov     qword ptr [rbp+70h+var_A0.20h], r9
0x1403da3b0  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], ecx
0x1403da3b3  mov     [rbp+70h+var_A0.PrivateDriverDataSize], edx
0x1403da3b6  mov     qword ptr [rbp+70h+var_A0.30h], r8
0x1403da3ba  mov     eax, [rbx+0Ch]
0x1403da3bd  shl     eax, 5
0x1403da3c0  xor     eax, ecx
0x1403da3c2  and     eax, 100000h
0x1403da3c7  xor     eax, ecx
0x1403da3c9  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], eax
0x1403da3cc  test    r15b, r15b
0x1403da3cf  jnz     short loc_1403DA410
0x1403da3d1  mov     eax, [rbx+80h]
0x1403da3d7  cmp     edx, eax
0x1403da3d9  jz      short loc_1403DA410
0x1403da3db  mov     r8d, edx
0x1403da3de  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da3e5  mov     rdx, rsi
0x1403da3e8  mov     [rsp+170h+var_150], rdi
0x1403da3ed  mov     r9d, eax
0x1403da3f0  mov     ecx, 3
0x1403da3f5  call    cs:__imp_WdLogSingleEntry4
0x1403da3fc  nop     dword ptr [rax+rax+00h]
0x1403da401  mov     cs:WdLogGlobalForLineNumber, 1F54h
0x1403da40b  jmp     loc_1403DAAFA
0x1403da410  mov     r15d, r12d
0x1403da413  test    edx, edx
0x1403da415  jz      short loc_1403DA42D
0x1403da417  mov     r8, rdx; Size
0x1403da41a  mov     rcx, r9; void *
0x1403da41d  mov     rdx, [rbx+78h]; Src
0x1403da421  call    memmove
0x1403da426  mov     r8, [rbp+70h+arg_18]
0x1403da42d  mov     r9, [r14+38h]
0x1403da431  mov     rdi, [rbx+88h]
0x1403da438  mov     [rbp+70h+arg_0], r9
0x1403da43f  cmp     r12d, [r14+8]
0x1403da443  jnb     loc_1403DA53C
0x1403da449  mov     ecx, [rdi-8]
0x1403da44c  lea     eax, [rcx+r15]
0x1403da450  cmp     eax, r15d
0x1403da453  jb      loc_1403DA50F
0x1403da459  cmp     eax, [r14+40h]
0x1403da45d  ja      loc_1403DA4E5
0x1403da463  mov     rdx, [rdi-10h]; Src
  ... truncated ...
```
