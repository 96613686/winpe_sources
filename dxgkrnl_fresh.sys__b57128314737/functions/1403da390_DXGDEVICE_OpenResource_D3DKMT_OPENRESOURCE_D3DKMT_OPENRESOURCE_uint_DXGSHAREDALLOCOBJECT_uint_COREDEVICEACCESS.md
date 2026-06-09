# DXGDEVICE::OpenResource<_D3DKMT_OPENRESOURCE>(_D3DKMT_OPENRESOURCE *,uint,_DXGSHAREDALLOCOBJECT *,uint,COREDEVICEACCESS *,int,_EPROCESS *,uint *,unsigned __int64 *)

- ea: `0x1403da390`
- end: `0x1403daf4d`
- name: `??$OpenResource@U_D3DKMT_OPENRESOURCE@@@DXGDEVICE@@QEAAJPEAU_D3DKMT_OPENRESOURCE@@IPEAU_DXGSHAREDALLOCOBJECT@@IPEAVCOREDEVICEACCESS@@HPEAU_EPROCESS@@PEAIPEA_K@Z`
- size: `3005`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *this@<rcx>, unsigned int, struct COREDEVICEACCESS *, unsigned int, struct _EPROCESS *, unsigned int *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140253378`
- `0x140253b50`
- `0x1403228c0`
- `0x1403d9d80`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x1400162a4`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001cd10`
- `0x14001d1a0`
- `0x14002dbc0`
- `0x14003bd18`
- `0x140055fbc`
- `0x14006e240`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140297be0`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x14036fa30`
- `0x14036fdd0`
- `0x140377080`
- `0x1403da390`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403da571`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403da571`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403da565`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403da565`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403dadfa`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403dadfa`
- `watchdog!WdLogSingleEntry4` at `0x1403da62d`
- `watchdog!WdLogSingleEntry4` at `0x1403da710`
- `watchdog!WdLogSingleEntry4` at `0x1403da815`
- `watchdog!WdLogSingleEntry4` at `0x1403da62d`
- `watchdog!WdLogSingleEntry4` at `0x1403da710`
- `watchdog!WdLogSingleEntry4` at `0x1403da815`
- `watchdog!WdLogSingleEntry2` at `0x1403da688`
- `watchdog!WdLogSingleEntry2` at `0x1403da914`
- `watchdog!WdLogSingleEntry2` at `0x1403da941`
- `watchdog!WdLogSingleEntry2` at `0x1403daed5`
- `watchdog!WdLogSingleEntry2` at `0x1403da688`
- `watchdog!WdLogSingleEntry2` at `0x1403da914`
- `watchdog!WdLogSingleEntry2` at `0x1403da941`
- `watchdog!WdLogSingleEntry2` at `0x1403daed5`
- `watchdog!WdLogSingleEntry3` at `0x1403da598`
- `watchdog!WdLogSingleEntry3` at `0x1403da78c`
- `watchdog!WdLogSingleEntry3` at `0x1403da598`
- `watchdog!WdLogSingleEntry3` at `0x1403da78c`
- `watchdog!WdLogSingleEntry0` at `0x1403da3e9`
- `watchdog!WdLogSingleEntry0` at `0x1403da507`
- `watchdog!WdLogSingleEntry0` at `0x1403daa0b`
- `watchdog!WdLogSingleEntry0` at `0x1403dab0b`
- `watchdog!WdLogSingleEntry0` at `0x1403dac20`
- `watchdog!WdLogSingleEntry0` at `0x1403dac7f`
- `watchdog!WdLogSingleEntry0` at `0x1403dad19`
- `watchdog!WdLogSingleEntry0` at `0x1403dae7a`
- `watchdog!WdLogSingleEntry0` at `0x1403da3e9`
- `watchdog!WdLogSingleEntry0` at `0x1403da507`
- `watchdog!WdLogSingleEntry0` at `0x1403daa0b`
- `watchdog!WdLogSingleEntry0` at `0x1403dab0b`
- `watchdog!WdLogSingleEntry0` at `0x1403dac20`
- `watchdog!WdLogSingleEntry0` at `0x1403dac7f`
- `watchdog!WdLogSingleEntry0` at `0x1403dad19`
- `watchdog!WdLogSingleEntry0` at `0x1403dae7a`
- `watchdog!WdLogSingleEntry1` at `0x1403da5ec`
- `watchdog!WdLogSingleEntry1` at `0x1403da9e6`
- `watchdog!WdLogSingleEntry1` at `0x1403da5ec`
- `watchdog!WdLogSingleEntry1` at `0x1403da9e6`

## string_xrefs

- `0x1403daa1c`: `KMCreateAlloc.hResource != 0`
- `0x1403dab1c`: `!pSharedResource->m_NtSecuritySharing || pSharedAllocObject`

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
  unsigned int v27; // edx
  int v28; // eax
  unsigned int v29; // ecx
  __int64 v30; // rax
  D3DDDI_ALLOCATIONINFO *v31; // rax
  UINT v32; // ecx
  char *v33; // r8
  D3DKMT_CREATESTANDARDALLOCATION *v34; // r9
  size_t v35; // rdx
  unsigned int v36; // r15d
  char *v37; // r9
  _QWORD *v38; // rdi
  unsigned int v39; // ecx
  const void *v40; // rdx
  __int64 v41; // rdx
  unsigned int v42; // eax
  unsigned int v43; // eax
  __int64 v44; // rax
  int v45; // eax
  D3DKMT_HANDLE hResource; // eax
  unsigned __int64 v47; // rcx
  unsigned int v48; // r10d
  _DWORD *v49; // r9
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned int *v52; // r12
  unsigned int v53; // edx
  unsigned int v54; // r8d
  __int64 v55; // rax
  DXG_GUEST_VIRTUALGPU_VMBUS *v56; // rcx
  int v57; // r9d
  struct DXGPROCESS *v58; // r15
  unsigned int v59; // eax
  __int64 v60; // r9
  int v61; // ecx
  struct DXGRESOURCE *v62; // rdx
  unsigned int v63; // r12d
  unsigned int v64; // eax
  __int64 v65; // r9
  int v66; // ecx
  struct DXGALLOCATION *v67; // rdx
  char *v68; // r15
  unsigned int v69; // eax
  __int64 v70; // r13
  __int64 v71; // rbx
  unsigned int CurrentProcessId; // eax
  int v73; // r8d
  int v75; // [rsp+38h] [rbp-C8h]
  int v76; // [rsp+68h] [rbp-98h]
  unsigned int v77; // [rsp+70h] [rbp-90h]
  char v78[8]; // [rsp+80h] [rbp-80h] BYREF
  char v79; // [rsp+88h] [rbp-78h]
  __int64 v80; // [rsp+90h] [rbp-70h]
  __int64 v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A0h] [rbp-60h]
  __int64 v83; // [rsp+A8h] [rbp-58h]
  struct DXGPROCESS *Current; // [rsp+B0h] [rbp-50h]
  struct _EX_RUNDOWN_REF *v85; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v86; // [rsp+C0h] [rbp-40h]
  struct _D3DKMT_CREATEALLOCATION v87; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v88[80]; // [rsp+120h] [rbp+20h] BYREF
  char *v89; // [rsp+180h] [rbp+80h] BYREF
  void *v90; // [rsp+198h] [rbp+98h]

  v10 = 0;
  v11 = a3;
  v90 = 0;
  memset(&v87, 0, sizeof(v87));
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(this[2]) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 7900;
    DxgkLogInternalTriageEvent(
      0,
      262146,
      -1,
      (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
      7900,
      0,
      0,
      0,
      0);
  }
  Current = DXGPROCESS::GetCurrent();
  v14 = Current;
  v15 = *((_DWORD *)Current + 102);
  DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)v78);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v78);
  if ( !(_DWORD)v11 )
  {
    v25 = -1073741811;
    WdLogSingleEntry2(2, this, -1073741811);
    WdLogGlobalForLineNumber = 7953;
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
    WdLogGlobalForLineNumber = 7944;
LABEL_106:
    DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v78);
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
        WdLogSingleEntry1(4, -1073741790);
        WdLogGlobalForLineNumber = 7963;
        goto LABEL_106;
      }
    }
  }
  v27 = *(_DWORD *)(ObjectA + 132);
  if ( v27 != *(_DWORD *)(a2 + 8) )
  {
    v25 = -1073741811;
    WdLogSingleEntry4(2, this, v27);
    WdLogGlobalForLineNumber = 7975;
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
    WdLogSingleEntry2(2, this, -1073741811);
    WdLogGlobalForLineNumber = 7986;
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
    if ( v79 )
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v78);
    goto LABEL_107;
  }
  if ( !(_BYTE)v15 )
  {
    v28 = *(_DWORD *)(ObjectA + 112);
    v29 = *(_DWORD *)(a2 + 32);
    if ( v29 != v28 )
    {
      v25 = -1073741811;
      WdLogSingleEntry4(3, this, v29);
      WdLogGlobalForLineNumber = 8000;
      goto LABEL_106;
    }
    if ( v28 )
      memmove(*(void **)(a2 + 24), *(const void **)(ObjectA + 104), *(unsigned int *)(ObjectA + 112));
  }
  v30 = 96LL * *(unsigned int *)(a2 + 8);
  if ( !is_mul_ok(*(unsigned int *)(a2 + 8), 0x60u) )
    v30 = -1;
  v31 = (D3DDDI_ALLOCATIONINFO *)operator new[](v30, 1265072196, 256);
  v32 = *(_DWORD *)(a2 + 8);
  v33 = (char *)v31;
  v90 = v31;
  if ( !v31 )
  {
    WdLogSingleEntry3(3, this, v32, -1073741801);
    WdLogGlobalForLineNumber = 8019;
LABEL_38:
    v25 = -1073741801;
    goto LABEL_106;
  }
  v34 = *(D3DKMT_CREATESTANDARDALLOCATION **)(a2 + 40);
  v35 = *(unsigned int *)(a2 + 48);
  v87.hDevice = *(_DWORD *)a2;
  v87.NumAllocations = v32;
  v87.hGlobalShare = v11;
  v87.pStandardAllocation = v34;
  v87.Flags = (D3DKMT_CREATEALLOCATIONFLAGS)(*(_DWORD *)&v87.Flags & 0xFFFFFF3E | 1);
  v87.PrivateDriverDataSize = v35;
  v87.pAllocationInfo = v31;
  *(_DWORD *)&v87.Flags ^= (*(_DWORD *)&v87.Flags ^ (32 * *(_DWORD *)(ObjectA + 12))) & 0x100000;
  if ( !(_BYTE)v15 && (_DWORD)v35 != *(_DWORD *)(ObjectA + 128) )
  {
    v25 = -1073741811;
    WdLogSingleEntry4(3, this, (unsigned int)v35);
    WdLogGlobalForLineNumber = 8046;
    goto LABEL_106;
  }
  v36 = 0;
  if ( (_DWORD)v35 )
  {
    memmove(v34, *(const void **)(ObjectA + 120), v35);
    v33 = (char *)v90;
  }
  v37 = *(char **)(a2 + 56);
  v38 = *(_QWORD **)(ObjectA + 136);
  while ( 1 )
  {
    v89 = v37;
    if ( v10 >= *(_DWORD *)(a2 + 8) )
      break;
    v39 = *((_DWORD *)v38 - 2);
    if ( v39 + v36 < v36 )
    {
      v25 = -1073741675;
      WdLogSingleEntry2(3, this, -1073741675);
      WdLogGlobalForLineNumber = 8072;
      goto LABEL_106;
    }
    if ( v39 + v36 > *(_DWORD *)(a2 + 64) )
    {
      WdLogSingleEntry2(3, this, -1073741801);
      WdLogGlobalForLineNumber = 8081;
      goto LABEL_38;
    }
    v40 = (const void *)*(v38 - 2);
    if ( v40 )
    {
      memmove(v37, v40, v39);
      v37 = v89;
      v33 = (char *)v90;
    }
    v41 = 96LL * v10;
    *(_DWORD *)&v33[v41] = 0;
    *(_QWORD *)&v33[v41 + 8] = 0;
    v42 = *((_DWORD *)v38 - 11);
    *(_DWORD *)&v33[v41 + 32] = 0;
    *(_DWORD *)&v33[v41 + 28] = (v42 >> 6) & 0xF;
    v43 = *((_DWORD *)v38 - 11);
    *(_QWORD *)&v33[v41 + 16] = v37;
    *(_DWORD *)&v33[v41 + 32] = v43 & 1 | (((v43 | (v43 >> 12)) & 2) != 0);
    *(_DWORD *)&v33[v41 + 24] = *((_DWORD *)v38 - 2);
    v44 = *((unsigned int *)v38 - 2);
    v38 = (_QWORD *)*v38;
    v36 += v44;
    v37 += v44;
    ++v10;
  }
  if ( v79 )
    DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v78);
  v45 = DXGDEVICE::CreateAllocation((DXGDEVICE *)this, &v87, 0, 1u, 0, 0, a6, a5, a8, a9, a10, 0, 0, 0, 0);
  v25 = v45;
  if ( v45 < 0 )
  {
    WdLogSingleEntry1(3, v45);
    WdLogGlobalForLineNumber = 8112;
    goto LABEL_107;
  }
  hResource = v87.hResource;
  if ( !v87.hResource )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 8117;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"KMCreateAlloc.hResource != 0", 8117, 0, 0, 0, 0);
    hResource = v87.hResource;
  }
  v47 = *(unsigned int *)(a2 + 8);
  v48 = 0;
  v49 = *(_DWORD **)(a2 + 16);
  *(_DWORD *)(a2 + 64) = v36;
  for ( *(_DWORD *)(a2 + 68) = hResource; v48 < (unsigned int)v47; v47 = *(unsigned int *)(a2 + 8) )
  {
    v50 = v48++;
    *v49 = *(&v87.pAllocationInfo->hAllocation + 24 * v50);
    v49 += 20;
    *((_QWORD *)v49 - 9) = *(_QWORD *)(a2 + 56)
                         + (unsigned int)(*((_DWORD *)&v87.pAllocationInfo->pPrivateDriverData + 24 * v50)
                                        - *(_DWORD *)(a2 + 56));
    *(v49 - 16) = *(&v87.pAllocationInfo->PrivateDriverDataSize + 24 * v50);
  }
  if ( (*((_BYTE *)this + 1917) & 1) != 0 )
  {
    v51 = 4 * v47;
    if ( !is_mul_ok(v47, 4u) )
      v51 = -1;
    v80 = operator new[](v51, 1265072196, 256);
    v52 = (unsigned int *)v80;
    if ( !v80 )
    {
      v25 = -1073741801;
      goto LABEL_107;
    }
    if ( (*(_DWORD *)(ObjectA + 12) & 8) != 0 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 8146;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"!pSharedResource->m_NtSecuritySharing || pSharedAllocObject",
        8146,
        0,
        0,
        0,
        0);
    }
    v53 = *(_DWORD *)(a2 + 64);
    v54 = *(_DWORD *)(a2 + 8);
    v55 = 40;
    v56 = (DXG_GUEST_VIRTUALGPU_VMBUS *)(*((_QWORD *)this[2] + 2) + 4792LL);
    v57 = *(_DWORD *)(ObjectA + 12) >> 3;
    a7 = 0;
    if ( (v57 & 1) == 0 )
      v55 = ObjectA + 28;
    v58 = Current;
    v25 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendOpenResource(
            v56,
            Current,
            (struct DXGDEVICE *)this,
            v57 & 1,
            *(_DWORD *)v55,
            v54,
            v53,
            &a7,
            v52);
    if ( v25 < 0 )
    {
LABEL_104:
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v52);
      goto LABEL_107;
    }
    DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v88, v58);
    v59 = (*(_DWORD *)(a2 + 68) >> 6) & 0xFFFFFF;
    if ( v59 < *((_DWORD *)v58 + 74) )
    {
      v60 = *((_QWORD *)v58 + 35);
      if ( ((*(_DWORD *)(a2 + 68) >> 25) & 0x60) == (*(_BYTE *)(v60 + 16LL * v59 + 8) & 0x60)
        && (*(_DWORD *)(v60 + 16LL * v59 + 8) & 0x2000) == 0 )
      {
        v61 = *(_DWORD *)(v60 + 16LL * v59 + 8) & 0x1F;
        if ( v61 )
        {
          if ( v61 == 4 )
          {
            v62 = *(struct DXGRESOURCE **)(v60 + 16LL * v59);
            goto LABEL_78;
          }
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
    }
    v62 = 0;
LABEL_78:
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v85, v62);
    if ( v85 )
    {
      v63 = 0;
      HIDWORD(v85[2].Ptr) = a7;
      while ( v63 < *(_DWORD *)(a2 + 8) )
      {
        v64 = (*(_DWORD *)(*(_QWORD *)(a2 + 16) + 80LL * v63) >> 6) & 0xFFFFFF;
        if ( v64 < *((_DWORD *)v58 + 74)
          && (v65 = *((_QWORD *)v58 + 35),
              ((*(_DWORD *)(*(_QWORD *)(a2 + 16) + 80LL * v63) >> 25) & 0x60) == (*(_BYTE *)(v65 + 16LL * v64 + 8) & 0x60))
          && (*(_DWORD *)(v65 + 16LL * v64 + 8) & 0x2000) == 0
          && (v66 = *(_DWORD *)(v65 + 16LL * v64 + 8) & 0x1F) != 0 )
        {
          if ( v66 == 5 )
          {
            v67 = *(struct DXGALLOCATION **)(v65 + 16LL * v64);
          }
          else
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 318;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            v67 = 0;
          }
        }
        else
        {
          v67 = 0;
        }
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v89, v67);
        v68 = v89;
        if ( !v89 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 8174;
          v25 = -1073741811;
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v89);
          break;
        }
        v69 = *(_DWORD *)(v80 + 4LL * v63);
        v89[128] |= 4u;
        *((_DWORD *)v68 + 5) = v69;
        a7 = v69;
        if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
        {
          v70 = *((_QWORD *)v68 + 5);
          if ( v70 )
          {
            v81 = *(_QWORD *)(v70 + 48);
            v82 = *(unsigned int *)(v70 + 16);
          }
          else
          {
            v81 = 0;
            v82 = 0;
          }
          v86 = *((unsigned int *)v68 + 4);
          if ( v70 )
            v83 = *(_QWORD *)(v70 + 56);
          else
            v83 = 0;
          v71 = *((_QWORD *)this[2] + 2);
          CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
          McTemplateK0ppppppppppppq_EtwWriteTransfer(
            v83,
            (unsigned int)&EventCreateDeviceAllocation,
            v73,
            CurrentProcessId,
            (char)this,
            v71,
            (char)v68,
            v75,
            v70,
            v83,
            v86,
            v82,
            v81,
            v76,
            v77,
            a7);
        }
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v89);
        v58 = Current;
        ++v63;
      }
      v52 = (unsigned int *)v80;
    }
    else
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 8163;
      v25 = -1073741811;
    }
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v85);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v88);
    goto LABEL_104;
  }
LABEL_107:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v90);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1403da390  mov     [rsp-8+arg_8], rbx
0x1403da395  mov     [rsp-8+arg_18], r9
0x1403da39a  push    rbp
0x1403da39b  push    rsi
0x1403da39c  push    rdi
0x1403da39d  push    r12
0x1403da39f  push    r13
0x1403da3a1  push    r14
0x1403da3a3  push    r15
0x1403da3a5  lea     rbp, [rsp-40h]
0x1403da3aa  sub     rsp, 140h
0x1403da3b1  xor     r12d, r12d
0x1403da3b4  mov     edi, r8d
0x1403da3b7  mov     r14, rdx
0x1403da3ba  mov     [rbp+70h+arg_18], r12
0x1403da3c1  mov     rsi, rcx
0x1403da3c4  xor     edx, edx; Val
0x1403da3c6  lea     rcx, [rbp+70h+var_A0]; void *
0x1403da3ca  lea     r8d, [r12+48h]; Size
0x1403da3cf  call    memset
0x1403da3d4  mov     rcx, [rsi+10h]; this
0x1403da3d8  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x1403da3dd  or      ebx, 0FFFFFFFFh
0x1403da3e0  test    al, al
0x1403da3e2  jnz     short loc_1403DA42F
0x1403da3e4  lea     ecx, [r12+1]
0x1403da3e9  call    cs:__imp_WdLogSingleEntry0
0x1403da3f0  nop     dword ptr [rax+rax+00h]
0x1403da3f5  mov     [rsp+170h+var_130], r12
0x1403da3fa  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x1403da401  mov     [rsp+170h+var_138], r12
0x1403da406  mov     eax, 1EDCh
0x1403da40b  mov     [rsp+170h+var_140], r12
0x1403da410  mov     r8d, ebx
0x1403da413  mov     [rsp+170h+var_148], r12
0x1403da418  mov     edx, 40002h
0x1403da41d  xor     ecx, ecx
0x1403da41f  mov     [rsp+170h+var_150], rax
0x1403da424  mov     cs:WdLogGlobalForLineNumber, eax
0x1403da42a  call    DxgkLogInternalTriageEvent
0x1403da42f  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1403da434  lea     rcx, [rbp+70h+var_F0]; this
0x1403da438  mov     [rbp+70h+var_C0], rax
0x1403da43c  mov     r13, rax
0x1403da43f  mov     r15d, [rax+198h]
0x1403da446  call    ??0DXGGLOBALSHAREMUTEX@@QEAA@XZ; DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX(void)
0x1403da44b  lea     rcx, [rbp+70h+var_F0]; this
0x1403da44f  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1403da454  test    edi, edi
0x1403da456  jz      loc_1403DAEC3
0x1403da45c  shr     r15d, 8
0x1403da460  and     r15b, 1
0x1403da464  jnz     short loc_1403DA486
0x1403da466  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1403da46b  mov     r13d, 2
0x1403da471  mov     edx, edi
0x1403da473  mov     r8d, r13d
0x1403da476  mov     rcx, rax
0x1403da479  call    ?GetObjectA@DXGGLOBAL@@QEAAPEAXIW4_HMGRENTRY_TYPE@@_N@Z; DXGGLOBAL::GetObjectA(uint,_HMGRENTRY_TYPE,bool)
0x1403da47e  mov     rbx, rax
0x1403da481  jmp     loc_1403DA580
0x1403da486  mov     eax, [r13+198h]
0x1403da48d  bt      eax, 8
0x1403da491  jnb     short loc_1403DA49C
0x1403da493  mov     rbx, [r13+258h]
0x1403da49a  jmp     short loc_1403DA4A6
0x1403da49c  and     al, 80h
0x1403da49e  neg     al
0x1403da4a0  sbb     rbx, rbx
0x1403da4a3  and     rbx, r13
0x1403da4a6  lea     r12, [rbx+0F8h]
0x1403da4ad  mov     rcx, r12; this
0x1403da4b0  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x1403da4b5  mov     eax, edi
0x1403da4b7  mov     r13d, 2
0x1403da4bd  shr     eax, 6
0x1403da4c0  and     eax, 0FFFFFFh
0x1403da4c5  cmp     eax, [rbx+128h]
0x1403da4cb  jnb     loc_1403DA558
0x1403da4d1  mov     rbx, [rbx+118h]
0x1403da4d8  mov     ecx, edi
0x1403da4da  mov     r8d, eax
0x1403da4dd  add     r8, r8
0x1403da4e0  shr     ecx, 19h
0x1403da4e3  and     ecx, 60h
0x1403da4e6  mov     edx, [rbx+r8*8+8]
0x1403da4eb  mov     eax, edx
0x1403da4ed  and     eax, 60h
0x1403da4f0  cmp     cl, al
0x1403da4f2  jnz     short loc_1403DA558
0x1403da4f4  bt      edx, 0Dh
0x1403da4f8  jb      short loc_1403DA558
0x1403da4fa  and     edx, 1Fh
0x1403da4fd  jz      short loc_1403DA558
0x1403da4ff  cmp     edx, r13d
0x1403da502  jz      short loc_1403DA552
0x1403da504  mov     ecx, r13d
0x1403da507  call    cs:__imp_WdLogSingleEntry0
0x1403da50e  nop     dword ptr [rax+rax+00h]
0x1403da513  xor     ebx, ebx
0x1403da515  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1403da51c  mov     [rsp+170h+var_130], rbx
0x1403da521  mov     eax, 13Eh
0x1403da526  mov     [rsp+170h+var_138], rbx
0x1403da52b  or      r8d, 0FFFFFFFFh
0x1403da52f  mov     [rsp+170h+var_140], rbx
0x1403da534  mov     edx, 40000h
0x1403da539  mov     [rsp+170h+var_148], rbx
0x1403da53e  xor     ecx, ecx
0x1403da540  mov     [rsp+170h+var_150], rax
0x1403da545  mov     cs:WdLogGlobalForLineNumber, eax
0x1403da54b  call    DxgkLogInternalTriageEvent
0x1403da550  jmp     short loc_1403DA55A
0x1403da552  mov     rbx, [rbx+r8*8]
0x1403da556  jmp     short loc_1403DA55A
0x1403da558  xor     ebx, ebx
0x1403da55a  lock dec dword ptr [r12+10h]
0x1403da560  xor     edx, edx
0x1403da562  mov     rcx, r12
0x1403da565  call    cs:__imp_ExReleasePushLockSharedEx
0x1403da56c  nop     dword ptr [rax+rax+00h]
0x1403da571  call    cs:__imp_KeLeaveCriticalRegion
0x1403da578  nop     dword ptr [rax+rax+00h]
0x1403da57d  xor     r12d, r12d
0x1403da580  test    rbx, rbx
0x1403da583  jnz     short loc_1403DA5B3
0x1403da585  mov     r8, rdi
0x1403da588  lea     ecx, [rbx+3]
0x1403da58b  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da592  mov     rdx, rsi
0x1403da595  mov     r9, rdi
0x1403da598  call    cs:__imp_WdLogSingleEntry3
0x1403da59f  nop     dword ptr [rax+rax+00h]
0x1403da5a4  mov     cs:WdLogGlobalForLineNumber, 1F08h
0x1403da5ae  jmp     loc_1403DAF1A
0x1403da5b3  mov     rax, [rbx+88h]
0x1403da5ba  mov     ecx, [rax-2Ch]
0x1403da5bd  test    r13b, cl
0x1403da5c0  jz      short loc_1403DA607
0x1403da5c2  mov     rax, [rsi+28h]
0x1403da5c6  mov     rax, [rax+58h]
0x1403da5ca  test    rax, rax
0x1403da5cd  jz      short loc_1403DA607
0x1403da5cf  mov     rax, [rax+0E0h]
0x1403da5d6  call    _guard_dispatch_icall
0x1403da5db  test    eax, eax
0x1403da5dd  jnz     short loc_1403DA607
0x1403da5df  mov     rdi, 0FFFFFFFFC0000022h
0x1403da5e6  lea     ecx, [rax+4]
0x1403da5e9  mov     rdx, rdi
0x1403da5ec  call    cs:__imp_WdLogSingleEntry1
0x1403da5f3  nop     dword ptr [rax+rax+00h]
0x1403da5f8  mov     cs:WdLogGlobalForLineNumber, 1F1Bh
0x1403da602  jmp     loc_1403DAF1A
0x1403da607  mov     eax, [r14+8]
0x1403da60b  mov     edx, [rbx+84h]
0x1403da611  cmp     edx, eax
0x1403da613  jz      short loc_1403DA671
0x1403da615  mov     r8d, edx
0x1403da618  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da61f  mov     rdx, rsi
0x1403da622  mov     [rsp+170h+var_150], rdi
0x1403da627  mov     r9d, eax
0x1403da62a  mov     ecx, r13d
0x1403da62d  call    cs:__imp_WdLogSingleEntry4
0x1403da634  nop     dword ptr [rax+rax+00h]
0x1403da639  mov     [rsp+170h+var_130], r12
0x1403da63e  lea     r9, aDevice0xI64xCa_1; "Device 0x%I64x: Caller specified incorr"...
0x1403da645  mov     cs:WdLogGlobalForLineNumber, 1F27h
0x1403da64f  or      r8d, 0FFFFFFFFh
0x1403da653  mov     eax, [r14+8]
0x1403da657  mov     ecx, [rbx+84h]
0x1403da65d  mov     [rsp+170h+var_138], rdi
0x1403da662  mov     [rsp+170h+var_140], rax
0x1403da667  mov     [rsp+170h+var_148], rcx
0x1403da66c  jmp     loc_1403DAF09
0x1403da671  mov     eax, [rbx+0Ch]
0x1403da674  test    al, 4
0x1403da676  jz      short loc_1403DA6E6
0x1403da678  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da67f  mov     rdx, rsi
0x1403da682  mov     r8, rdi
0x1403da685  mov     ecx, r13d
0x1403da688  call    cs:__imp_WdLogSingleEntry2
0x1403da68f  nop     dword ptr [rax+rax+00h]
0x1403da694  mov     [rsp+170h+var_130], r12
0x1403da699  lea     r9, aDevice0xI64xPr; "Device 0x%I64x: PrivateRuntimeData has "...
0x1403da6a0  mov     [rsp+170h+var_138], r12
0x1403da6a5  or      r8d, 0FFFFFFFFh
0x1403da6a9  mov     [rsp+170h+var_140], r12
0x1403da6ae  mov     edx, 40000h
0x1403da6b3  mov     [rsp+170h+var_148], rdi
0x1403da6b8  xor     ecx, ecx
0x1403da6ba  mov     [rsp+170h+var_150], rsi
0x1403da6bf  mov     cs:WdLogGlobalForLineNumber, 1F32h
0x1403da6c9  call    DxgkLogInternalTriageEvent
0x1403da6ce  cmp     [rbp+70h+var_E8], r12b
0x1403da6d2  jz      loc_1403DAF23
0x1403da6d8  lea     rcx, [rbp+70h+var_F0]; this
0x1403da6dc  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1403da6e1  jmp     loc_1403DAF23
0x1403da6e6  test    r15b, r15b
0x1403da6e9  jnz     short loc_1403DA73F
0x1403da6eb  mov     eax, [rbx+70h]
0x1403da6ee  mov     ecx, [r14+20h]
0x1403da6f2  cmp     ecx, eax
0x1403da6f4  jz      short loc_1403DA72B
0x1403da6f6  mov     r8d, ecx
0x1403da6f9  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da700  mov     ecx, 3
0x1403da705  mov     [rsp+170h+var_150], rdi
0x1403da70a  mov     r9d, eax
0x1403da70d  mov     rdx, rsi
0x1403da710  call    cs:__imp_WdLogSingleEntry4
0x1403da717  nop     dword ptr [rax+rax+00h]
0x1403da71c  mov     cs:WdLogGlobalForLineNumber, 1F40h
0x1403da726  jmp     loc_1403DAF1A
0x1403da72b  test    eax, eax
0x1403da72d  jz      short loc_1403DA73F
0x1403da72f  mov     rdx, [rbx+68h]; Src
0x1403da733  mov     r8, rax; Size
0x1403da736  mov     rcx, [r14+18h]; void *
0x1403da73a  call    memmove
0x1403da73f  mov     ecx, [r14+8]
0x1403da743  mov     eax, 60h ; '`'
0x1403da748  mul     rcx
0x1403da74b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1403da752  mov     edx, 4B677844h
0x1403da757  mov     r8d, 100h
0x1403da75d  cmovb   rax, rcx
0x1403da761  mov     rcx, rax
0x1403da764  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1403da769  mov     ecx, [r14+8]
0x1403da76d  mov     r8, rax
0x1403da770  mov     [rbp+70h+arg_18], rax
0x1403da777  test    rax, rax
0x1403da77a  jnz     short loc_1403DA7AC
0x1403da77c  mov     r8d, ecx
0x1403da77f  mov     r9, 0FFFFFFFFC0000017h
0x1403da786  lea     ecx, [rax+3]
0x1403da789  mov     rdx, rsi
0x1403da78c  call    cs:__imp_WdLogSingleEntry3
0x1403da793  nop     dword ptr [rax+rax+00h]
0x1403da798  mov     cs:WdLogGlobalForLineNumber, 1F53h
0x1403da7a2  mov     edi, 0C0000017h
0x1403da7a7  jmp     loc_1403DAF1A
0x1403da7ac  mov     eax, [r14]
0x1403da7af  mov     r9, [r14+28h]
0x1403da7b3  mov     edx, [r14+30h]
0x1403da7b7  mov     [rbp+70h+var_A0.hDevice], eax
0x1403da7ba  mov     [rbp+70h+var_A0.NumAllocations], ecx
0x1403da7bd  mov     ecx, dword ptr [rbp+70h+var_A0.Flags.CreateResource]
0x1403da7c0  and     ecx, 0FFFFFF3Fh
0x1403da7c6  mov     [rbp+70h+var_A0.hGlobalShare], edi
0x1403da7c9  or      ecx, 1
0x1403da7cc  mov     qword ptr [rbp+70h+var_A0.20h], r9
0x1403da7d0  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], ecx
0x1403da7d3  mov     [rbp+70h+var_A0.PrivateDriverDataSize], edx
0x1403da7d6  mov     qword ptr [rbp+70h+var_A0.30h], r8
0x1403da7da  mov     eax, [rbx+0Ch]
0x1403da7dd  shl     eax, 5
0x1403da7e0  xor     eax, ecx
0x1403da7e2  and     eax, 100000h
0x1403da7e7  xor     eax, ecx
0x1403da7e9  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], eax
0x1403da7ec  test    r15b, r15b
0x1403da7ef  jnz     short loc_1403DA830
0x1403da7f1  mov     eax, [rbx+80h]
0x1403da7f7  cmp     edx, eax
0x1403da7f9  jz      short loc_1403DA830
0x1403da7fb  mov     r8d, edx
0x1403da7fe  mov     rdi, 0FFFFFFFFC000000Dh
0x1403da805  mov     rdx, rsi
0x1403da808  mov     [rsp+170h+var_150], rdi
0x1403da80d  mov     r9d, eax
0x1403da810  mov     ecx, 3
0x1403da815  call    cs:__imp_WdLogSingleEntry4
0x1403da81c  nop     dword ptr [rax+rax+00h]
0x1403da821  mov     cs:WdLogGlobalForLineNumber, 1F6Eh
0x1403da82b  jmp     loc_1403DAF1A
0x1403da830  mov     r15d, r12d
0x1403da833  test    edx, edx
0x1403da835  jz      short loc_1403DA84D
0x1403da837  mov     r8, rdx; Size
0x1403da83a  mov     rcx, r9; void *
0x1403da83d  mov     rdx, [rbx+78h]; Src
0x1403da841  call    memmove
0x1403da846  mov     r8, [rbp+70h+arg_18]
0x1403da84d  mov     r9, [r14+38h]
0x1403da851  mov     rdi, [rbx+88h]
0x1403da858  mov     [rbp+70h+arg_0], r9
0x1403da85f  cmp     r12d, [r14+8]
0x1403da863  jnb     loc_1403DA95C
0x1403da869  mov     ecx, [rdi-8]
0x1403da86c  lea     eax, [rcx+r15]
0x1403da870  cmp     eax, r15d
0x1403da873  jb      loc_1403DA92F
0x1403da879  cmp     eax, [r14+40h]
0x1403da87d  ja      loc_1403DA905
0x1403da883  mov     rdx, [rdi-10h]; Src
  ... truncated ...
```
