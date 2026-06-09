# DXGDEVICE::OpenResource<_D3DKMT_OPENRESOURCEFROMNTHANDLE>(_D3DKMT_OPENRESOURCEFROMNTHANDLE *,uint,_DXGSHAREDALLOCOBJECT *,uint,COREDEVICEACCESS *,int,_EPROCESS *,uint *,unsigned __int64 *)

- ea: `0x14031a21c`
- end: `0x14031acb4`
- name: `??$OpenResource@U_D3DKMT_OPENRESOURCEFROMNTHANDLE@@@DXGDEVICE@@QEAAJPEAU_D3DKMT_OPENRESOURCEFROMNTHANDLE@@IPEAU_DXGSHAREDALLOCOBJECT@@IPEAVCOREDEVICEACCESS@@HPEAU_EPROCESS@@PEAIPEA_K@Z`
- size: `2712`
- prototype: `__int64 __usercall@<rax>(struct DXGDEVICE *@<rcx>, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14020fef0`
- `0x14024a3ec`
- `0x140319248`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400160e4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001cbe0`
- `0x14002d9f0`
- `0x14003bab8`
- `0x14006dc88`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x140291280`
- `0x14031a21c`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x14036f9f0`
- `0x14036fd90`
- `0x140377040`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14031aba3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14031aba3`
- `watchdog!WdLogSingleEntry4` at `0x14031a39a`
- `watchdog!WdLogSingleEntry4` at `0x14031a469`
- `watchdog!WdLogSingleEntry4` at `0x14031a5b2`
- `watchdog!WdLogSingleEntry4` at `0x14031a39a`
- `watchdog!WdLogSingleEntry4` at `0x14031a469`
- `watchdog!WdLogSingleEntry4` at `0x14031a5b2`
- `watchdog!WdLogSingleEntry2` at `0x14031a408`
- `watchdog!WdLogSingleEntry2` at `0x14031a6ee`
- `watchdog!WdLogSingleEntry2` at `0x14031a720`
- `watchdog!WdLogSingleEntry2` at `0x14031ac7b`
- `watchdog!WdLogSingleEntry2` at `0x14031a408`
- `watchdog!WdLogSingleEntry2` at `0x14031a6ee`
- `watchdog!WdLogSingleEntry2` at `0x14031a720`
- `watchdog!WdLogSingleEntry2` at `0x14031ac7b`
- `watchdog!WdLogSingleEntry3` at `0x14031a2fd`
- `watchdog!WdLogSingleEntry3` at `0x14031a4e5`
- `watchdog!WdLogSingleEntry3` at `0x14031a2fd`
- `watchdog!WdLogSingleEntry3` at `0x14031a4e5`
- `watchdog!WdLogSingleEntry0` at `0x14031a271`
- `watchdog!WdLogSingleEntry0` at `0x14031a7eb`
- `watchdog!WdLogSingleEntry0` at `0x14031a9cb`
- `watchdog!WdLogSingleEntry0` at `0x14031aa26`
- `watchdog!WdLogSingleEntry0` at `0x14031aac2`
- `watchdog!WdLogSingleEntry0` at `0x14031ac1d`
- `watchdog!WdLogSingleEntry0` at `0x14031a271`
- `watchdog!WdLogSingleEntry0` at `0x14031a7eb`
- `watchdog!WdLogSingleEntry0` at `0x14031a9cb`
- `watchdog!WdLogSingleEntry0` at `0x14031aa26`
- `watchdog!WdLogSingleEntry0` at `0x14031aac2`
- `watchdog!WdLogSingleEntry0` at `0x14031ac1d`
- `watchdog!WdLogSingleEntry1` at `0x14031a35a`
- `watchdog!WdLogSingleEntry1` at `0x14031a7c6`
- `watchdog!WdLogSingleEntry1` at `0x14031a35a`
- `watchdog!WdLogSingleEntry1` at `0x14031a7c6`

## string_xrefs

- `0x14031a800`: `KMCreateAlloc.hResource != 0`

## pseudocode

```c
__int64 __fastcall DXGDEVICE::OpenResource<_D3DKMT_OPENRESOURCEFROMNTHANDLE>(
        ADAPTER_RENDER **a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        struct COREDEVICEACCESS *a6,
        char a7,
        struct _EPROCESS *a8,
        unsigned int *a9,
        unsigned __int64 *a10)
{
  D3DDDI_ALLOCATIONINFO *v13; // r15
  int v14; // edi
  __int64 v15; // rbx
  int v16; // edi
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // edx
  const wchar_t *v20; // r9
  unsigned int v21; // eax
  unsigned int v22; // ecx
  __int64 v23; // rax
  D3DDDI_ALLOCATIONINFO *v24; // rax
  UINT v25; // ecx
  D3DDDI_ALLOCATIONINFO *v26; // r11
  D3DKMT_CREATESTANDARDALLOCATION *v28; // r9
  size_t v29; // rdx
  unsigned int v30; // eax
  unsigned int v31; // r8d
  unsigned int *v32; // r10
  unsigned int v33; // r9d
  _QWORD *v34; // rdi
  unsigned int *v35; // r12
  unsigned int *v36; // r15
  unsigned int v37; // ecx
  const void *v38; // rdx
  __int64 v39; // rdx
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // rax
  D3DKMT_HANDLE hResource; // eax
  __int64 v44; // r10
  _DWORD *v45; // r9
  unsigned __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // rax
  unsigned int *v49; // r15
  unsigned int v50; // edx
  unsigned int v51; // r8d
  DXG_GUEST_VIRTUALGPU_VMBUS *v52; // rcx
  int v53; // r9d
  unsigned int v54; // eax
  struct DXGPROCESS *v55; // r13
  unsigned int v56; // eax
  __int64 v57; // r9
  int v58; // ecx
  struct DXGRESOURCE *v59; // rdx
  unsigned int v60; // r12d
  unsigned int v61; // eax
  __int64 v62; // r9
  int v63; // ecx
  struct DXGALLOCATION *v64; // rdx
  struct _EX_RUNDOWN_REF *v65; // r15
  unsigned int v66; // eax
  ULONG_PTR Count; // r13
  __int64 v68; // rbx
  unsigned int CurrentProcessId; // eax
  int v70; // r8d
  __int64 v71; // [rsp+28h] [rbp-D8h]
  __int64 v72; // [rsp+30h] [rbp-D0h]
  __int64 v73; // [rsp+38h] [rbp-C8h]
  int v74; // [rsp+38h] [rbp-C8h]
  int v75; // [rsp+68h] [rbp-98h]
  unsigned int v76; // [rsp+70h] [rbp-90h]
  char v77[8]; // [rsp+80h] [rbp-80h] BYREF
  char v78; // [rsp+88h] [rbp-78h]
  unsigned int *v79; // [rsp+90h] [rbp-70h]
  __int64 v80; // [rsp+98h] [rbp-68h]
  __int64 v81; // [rsp+A0h] [rbp-60h]
  __int64 v82; // [rsp+A8h] [rbp-58h]
  struct DXGPROCESS *Current; // [rsp+B0h] [rbp-50h]
  struct _EX_RUNDOWN_REF *v84; // [rsp+B8h] [rbp-48h] BYREF
  __int64 Count_low; // [rsp+C0h] [rbp-40h]
  struct _D3DKMT_CREATEALLOCATION v86; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v87[80]; // [rsp+120h] [rbp+20h] BYREF
  struct _EX_RUNDOWN_REF *v88; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v89; // [rsp+190h] [rbp+90h] BYREF
  D3DDDI_ALLOCATIONINFO *v90; // [rsp+198h] [rbp+98h]

  v89 = a3;
  v13 = 0;
  memset(&v86, 0, sizeof(v86));
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(a1[2]) )
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
  v14 = *((_DWORD *)Current + 102);
  DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)v77);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v77);
  if ( !a4 )
  {
    v16 = -1073741811;
    WdLogSingleEntry2(2, a1);
    WdLogGlobalForLineNumber = 7927;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Device 0x%I64x: Caller passed NULL for both the NT object and the global shared handle. Returning 0x%I64x",
      (__int64)a1,
      -1073741811,
      0,
      0,
      0);
    goto LABEL_6;
  }
  v15 = *(_QWORD *)(a4 + 16);
  if ( v15 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v15 + 136) - 44LL) & 2) != 0 )
    {
      v17 = *((_QWORD *)a1[5] + 11);
      if ( v17 )
      {
        if ( !(*(unsigned int (**)(void))(v17 + 224))() )
        {
          v16 = -1073741790;
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 7937;
          goto LABEL_6;
        }
      }
    }
    v18 = *(_DWORD *)(a2 + 16);
    v19 = *(_DWORD *)(v15 + 132);
    if ( v19 != v18 )
    {
      v16 = -1073741811;
      WdLogSingleEntry4(2, a1, v19, v18, -1073741811);
      v20 = L"Device 0x%I64x: Caller specified incorrect number of allocations, should have been 0x%I64x but was 0x%I64x, "
             "returning 0x%I64x";
      WdLogGlobalForLineNumber = 7949;
      v73 = -1073741811;
      v72 = *(unsigned int *)(a2 + 16);
      v71 = *(unsigned int *)(v15 + 132);
LABEL_13:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v20, (__int64)a1, v71, v72, v73, 0);
      goto LABEL_6;
    }
    if ( (*(_DWORD *)(v15 + 12) & 4) != 0 )
    {
      v16 = -1073741811;
      WdLogSingleEntry2(2, a1);
      v20 = L"Device 0x%I64x: PrivateRuntimeData has been marked as invalid, returning 0x%I64x";
      v73 = 0;
      v72 = 0;
      v71 = -1073741811;
      WdLogGlobalForLineNumber = 7960;
      goto LABEL_13;
    }
    if ( (v14 & 0x100) == 0 )
    {
      v21 = *(_DWORD *)(v15 + 112);
      v22 = *(_DWORD *)(a2 + 32);
      if ( v22 != v21 )
      {
        v16 = -1073741811;
        WdLogSingleEntry4(3, a1, v22, v21, -1073741811);
        WdLogGlobalForLineNumber = 7974;
        goto LABEL_6;
      }
      if ( v21 )
        memmove(*(void **)(a2 + 40), *(const void **)(v15 + 104), *(unsigned int *)(v15 + 112));
    }
    v23 = 96LL * *(unsigned int *)(a2 + 16);
    if ( !is_mul_ok(*(unsigned int *)(a2 + 16), 0x60u) )
      v23 = -1;
    v24 = (D3DDDI_ALLOCATIONINFO *)operator new[](v23, 1265072196, 256);
    v25 = *(_DWORD *)(a2 + 16);
    v26 = v24;
    v90 = v24;
    if ( !v24 )
    {
      WdLogSingleEntry3(3, a1, v25, -1073741801);
      v16 = -1073741801;
      WdLogGlobalForLineNumber = 7993;
      if ( v78 )
        DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v77);
      goto LABEL_27;
    }
    v28 = *(D3DKMT_CREATESTANDARDALLOCATION **)(a2 + 56);
    v29 = *(unsigned int *)(a2 + 48);
    v86.hDevice = *(_DWORD *)a2;
    v86.NumAllocations = v25;
    v86.hGlobalShare = 0;
    v86.pStandardAllocation = v28;
    v86.PrivateDriverDataSize = v29;
    v86.Flags = (D3DKMT_CREATEALLOCATIONFLAGS)(*(_DWORD *)&v86.Flags & 0xFFFFFF7F | ((a7 & 1) << 7) | 0x41);
    v86.pAllocationInfo = v24;
    *(_DWORD *)&v86.Flags ^= (*(_DWORD *)&v86.Flags ^ (32 * *(_DWORD *)(v15 + 12))) & 0x100000;
    if ( (v14 & 0x100) == 0 )
    {
      v30 = *(_DWORD *)(v15 + 128);
      if ( (_DWORD)v29 != v30 )
      {
        v16 = -1073741811;
        WdLogSingleEntry4(3, a1, (unsigned int)v29, v30, -1073741811);
        WdLogGlobalForLineNumber = 8020;
LABEL_32:
        DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v77);
        goto LABEL_27;
      }
    }
    v89 = 0;
    v31 = 0;
    if ( (_DWORD)v29 )
    {
      memmove(v28, *(const void **)(v15 + 120), v29);
      v26 = v90;
      v31 = 0;
    }
    v32 = *(unsigned int **)(a2 + 72);
    v33 = 0;
    v34 = *(_QWORD **)(v15 + 136);
    LODWORD(v88) = 0;
    v35 = (unsigned int *)(a2 + 64);
    v36 = (unsigned int *)(a2 + 64);
    while ( 1 )
    {
      v79 = v32;
      if ( v33 >= *(_DWORD *)(a2 + 16) )
        break;
      v37 = *((_DWORD *)v34 - 2);
      if ( v37 + v31 < v31 )
      {
        v16 = -1073741675;
        WdLogSingleEntry2(3, a1);
        WdLogGlobalForLineNumber = 8046;
        goto LABEL_32;
      }
      v36 = (unsigned int *)(a2 + 64);
      if ( v37 + v31 > *(_DWORD *)(a2 + 64) )
      {
        WdLogSingleEntry2(3, a1);
        WdLogGlobalForLineNumber = 8055;
        v16 = -1073741801;
        goto LABEL_32;
      }
      v38 = (const void *)*(v34 - 2);
      if ( v38 )
      {
        memmove(v32, v38, v37);
        v31 = v89;
        v33 = (unsigned int)v88;
        v32 = v79;
        v26 = v90;
      }
      v39 = 96LL * v33;
      *(D3DKMT_HANDLE *)((char *)&v26->hAllocation + v39) = 0;
      *(const void **)((char *)&v26->pSystemMem + v39) = 0;
      v40 = *((_DWORD *)v34 - 11);
      *(UINT *)((char *)&v26->Flags.Value + v39) = 0;
      *(D3DDDI_VIDEO_PRESENT_SOURCE_ID *)((char *)&v26->VidPnSourceId + v39) = (v40 >> 6) & 0xF;
      v41 = *((_DWORD *)v34 - 11);
      *(void **)((char *)&v26->pPrivateDriverData + v39) = v32;
      *(UINT *)((char *)&v26->Flags.Value + v39) = v41 & 1 | (((v41 | (v41 >> 12)) & 2) != 0);
      *(UINT *)((char *)&v26->PrivateDriverDataSize + v39) = *((_DWORD *)v34 - 2);
      v42 = *((unsigned int *)v34 - 2);
      v34 = (_QWORD *)*v34;
      v31 += v42;
      v32 = (unsigned int *)((char *)v32 + v42);
      v89 = v31;
      LODWORD(v88) = ++v33;
    }
    if ( v78 )
    {
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v77);
      v36 = (unsigned int *)(a2 + 64);
    }
    v16 = DXGDEVICE::CreateAllocation(
            (DXGDEVICE *)a1,
            &v86,
            0,
            1u,
            (struct _DXGSHAREDALLOCOBJECT *)a4,
            0,
            a6,
            a5,
            a8,
            a9,
            a10,
            0,
            0,
            0,
            0);
    if ( v16 < 0 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 8086;
LABEL_27:
      v13 = v90;
      goto LABEL_28;
    }
    hResource = v86.hResource;
    if ( v86.hResource )
    {
      v35 = v36;
    }
    else
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 8091;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"KMCreateAlloc.hResource != 0", 8091, 0, 0, 0, 0);
      hResource = v86.hResource;
    }
    v44 = 0;
    v45 = *(_DWORD **)(a2 + 24);
    *v35 = v89;
    v46 = *(unsigned int *)(a2 + 16);
    *(_DWORD *)(a2 + 80) = hResource;
    if ( (_DWORD)v46 )
    {
      do
      {
        v47 = 96 * v44;
        v44 = (unsigned int)(v44 + 1);
        *v45 = *(D3DKMT_HANDLE *)((char *)&v86.pAllocationInfo->hAllocation + v47);
        v45 += 20;
        *((_QWORD *)v45 - 9) = *(_QWORD *)(a2 + 72)
                             + (unsigned int)(*(_DWORD *)((char *)&v86.pAllocationInfo->pPrivateDriverData + v47)
                                            - *(_DWORD *)(a2 + 72));
        *(v45 - 16) = *(UINT *)((char *)&v86.pAllocationInfo->PrivateDriverDataSize + v47);
        v46 = *(unsigned int *)(a2 + 16);
      }
      while ( (unsigned int)v44 < (unsigned int)v46 );
    }
    if ( (*((_BYTE *)a1 + 1917) & 1) == 0 )
      goto LABEL_27;
    v48 = 4 * v46;
    if ( !is_mul_ok(v46, 4u) )
      v48 = -1;
    v79 = (unsigned int *)operator new[](v48, 1265072196, 256);
    v49 = v79;
    if ( !v79 )
    {
      v16 = -1073741801;
      goto LABEL_27;
    }
    v50 = *v35;
    v51 = *(_DWORD *)(a2 + 16);
    v52 = (DXG_GUEST_VIRTUALGPU_VMBUS *)(*((_QWORD *)a1[2] + 2) + 4776LL);
    v53 = *(_DWORD *)(v15 + 12) >> 3;
    v89 = 0;
    if ( (v53 & 1) != 0 )
      v54 = *(_DWORD *)(a4 + 40);
    else
      v54 = *(_DWORD *)(v15 + 28);
    v55 = Current;
    v16 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendOpenResource(
            v52,
            Current,
            (struct DXGDEVICE *)a1,
            v53 & 1,
            v54,
            v51,
            v50,
            &v89,
            v79);
    if ( v16 < 0 )
    {
LABEL_95:
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v49);
      goto LABEL_27;
    }
    DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v87, v55);
    v56 = (*(_DWORD *)(a2 + 80) >> 6) & 0xFFFFFF;
    if ( v56 < *((_DWORD *)v55 + 74) )
    {
      v57 = *((_QWORD *)v55 + 35);
      if ( ((*(_DWORD *)(a2 + 80) >> 25) & 0x60) == (*(_BYTE *)(v57 + 16LL * v56 + 8) & 0x60)
        && (*(_DWORD *)(v57 + 16LL * v56 + 8) & 0x2000) == 0 )
      {
        v58 = *(_DWORD *)(v57 + 16LL * v56 + 8) & 0x1F;
        if ( v58 )
        {
          if ( v58 == 4 )
          {
            v59 = *(struct DXGRESOURCE **)(v57 + 16LL * v56);
            goto LABEL_69;
          }
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
    }
    v59 = 0;
LABEL_69:
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v84, v59);
    if ( v84 )
    {
      v60 = 0;
      HIDWORD(v84[2].Ptr) = v89;
      while ( v60 < *(_DWORD *)(a2 + 16) )
      {
        v61 = (*(_DWORD *)(*(_QWORD *)(a2 + 24) + 80LL * v60) >> 6) & 0xFFFFFF;
        if ( v61 < *((_DWORD *)v55 + 74)
          && (v62 = *((_QWORD *)v55 + 35),
              ((*(_DWORD *)(*(_QWORD *)(a2 + 24) + 80LL * v60) >> 25) & 0x60) == (*(_BYTE *)(v62 + 16LL * v61 + 8) & 0x60))
          && (*(_DWORD *)(v62 + 16LL * v61 + 8) & 0x2000) == 0
          && (v63 = *(_DWORD *)(v62 + 16LL * v61 + 8) & 0x1F) != 0 )
        {
          if ( v63 == 5 )
          {
            v64 = *(struct DXGALLOCATION **)(v62 + 16LL * v61);
          }
          else
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 318;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            v64 = 0;
          }
        }
        else
        {
          v64 = 0;
        }
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v88, v64);
        v65 = v88;
        if ( !v88 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 8148;
          v16 = -1073741811;
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(&v88);
          break;
        }
        v66 = v79[v60];
        LOBYTE(v88[16].Count) |= 4u;
        HIDWORD(v65[2].Ptr) = v66;
        v89 = v66;
        if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
        {
          Count = v65[5].Count;
          if ( Count )
          {
            v80 = *(_QWORD *)(Count + 48);
            v81 = *(unsigned int *)(Count + 16);
          }
          else
          {
            v80 = 0;
            v81 = 0;
          }
          Count_low = LODWORD(v65[2].Count);
          if ( Count )
            v82 = *(_QWORD *)(Count + 56);
          else
            v82 = 0;
          v68 = *((_QWORD *)a1[2] + 2);
          CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
          McTemplateK0ppppppppppppq_EtwWriteTransfer(
            v82,
            (unsigned int)EventCreateDeviceAllocation,
            v70,
            CurrentProcessId,
            (char)a1,
            v68,
            (char)v65,
            v74,
            Count,
            v82,
            Count_low,
            v81,
            v80,
            v75,
            v76,
            v89);
          v55 = Current;
        }
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(&v88);
        ++v60;
      }
      v49 = v79;
    }
    else
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 8137;
      v16 = -1073741811;
    }
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v84);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v87);
    goto LABEL_95;
  }
  v16 = -1073741811;
  WdLogSingleEntry3(3, a1, a4, -1073741811);
  WdLogGlobalForLineNumber = 7896;
LABEL_6:
  DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v77);
LABEL_28:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v13);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14031a21c  mov     [rsp-8+arg_8], rbx
0x14031a221  mov     [rsp-8+arg_10], r8d
0x14031a226  push    rbp
0x14031a227  push    rsi
0x14031a228  push    rdi
0x14031a229  push    r12
0x14031a22b  push    r13
0x14031a22d  push    r14
0x14031a22f  push    r15
0x14031a231  lea     rbp, [rsp-40h]
0x14031a236  sub     rsp, 140h
0x14031a23d  xor     r12d, r12d
0x14031a240  mov     r14, rdx
0x14031a243  mov     rsi, rcx
0x14031a246  xor     edx, edx; Val
0x14031a248  lea     rcx, [rbp+70h+var_A0]; void *
0x14031a24c  mov     r13, r9
0x14031a24f  mov     r15d, r12d
0x14031a252  lea     r8d, [r12+48h]; Size
0x14031a257  call    memset
0x14031a25c  mov     rcx, [rsi+10h]; this
0x14031a260  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x14031a265  or      ebx, 0FFFFFFFFh
0x14031a268  test    al, al
0x14031a26a  jnz     short loc_14031A2B7
0x14031a26c  lea     ecx, [r12+1]
0x14031a271  call    cs:__imp_WdLogSingleEntry0
0x14031a278  nop     dword ptr [rax+rax+00h]
0x14031a27d  mov     [rsp+170h+var_130], r12
0x14031a282  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x14031a289  mov     [rsp+170h+var_138], r12
0x14031a28e  mov     eax, 1EC2h
0x14031a293  mov     [rsp+170h+var_140], r12
0x14031a298  mov     r8d, ebx
0x14031a29b  mov     [rsp+170h+var_148], r12
0x14031a2a0  mov     edx, 40002h
0x14031a2a5  xor     ecx, ecx
0x14031a2a7  mov     [rsp+170h+var_150], rax
0x14031a2ac  mov     cs:WdLogGlobalForLineNumber, eax
0x14031a2b2  call    DxgkLogInternalTriageEvent
0x14031a2b7  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14031a2bc  lea     rcx, [rbp+70h+var_F0]; this
0x14031a2c0  mov     [rbp+70h+var_C0], rax
0x14031a2c4  mov     edi, [rax+198h]
0x14031a2ca  call    ??0DXGGLOBALSHAREMUTEX@@QEAA@XZ; DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX(void)
0x14031a2cf  lea     rcx, [rbp+70h+var_F0]; this
0x14031a2d3  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x14031a2d8  test    r13, r13
0x14031a2db  jz      loc_14031AC69
0x14031a2e1  mov     rbx, [r13+10h]
0x14031a2e5  test    rbx, rbx
0x14031a2e8  jnz     short loc_14031A321
0x14031a2ea  mov     rdi, 0FFFFFFFFC000000Dh
0x14031a2f1  lea     ecx, [rbx+3]
0x14031a2f4  mov     r9, rdi
0x14031a2f7  mov     r8, r13
0x14031a2fa  mov     rdx, rsi
0x14031a2fd  call    cs:__imp_WdLogSingleEntry3
0x14031a304  nop     dword ptr [rax+rax+00h]
0x14031a309  mov     cs:WdLogGlobalForLineNumber, 1ED8h
0x14031a313  lea     rcx, [rbp+70h+var_F0]; this
0x14031a317  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x14031a31c  jmp     loc_14031A516
0x14031a321  mov     rax, [rbx+88h]
0x14031a328  mov     ecx, [rax-2Ch]
0x14031a32b  test    cl, 2
0x14031a32e  jz      short loc_14031A372
0x14031a330  mov     rax, [rsi+28h]
0x14031a334  mov     rax, [rax+58h]
0x14031a338  test    rax, rax
0x14031a33b  jz      short loc_14031A372
0x14031a33d  mov     rax, [rax+0E0h]
0x14031a344  call    _guard_dispatch_icall
0x14031a349  test    eax, eax
0x14031a34b  jnz     short loc_14031A372
0x14031a34d  mov     rdi, 0FFFFFFFFC0000022h
0x14031a354  lea     ecx, [rax+4]
0x14031a357  mov     rdx, rdi
0x14031a35a  call    cs:__imp_WdLogSingleEntry1
0x14031a361  nop     dword ptr [rax+rax+00h]
0x14031a366  mov     cs:WdLogGlobalForLineNumber, 1F01h
0x14031a370  jmp     short loc_14031A313
0x14031a372  mov     eax, [r14+10h]
0x14031a376  mov     edx, [rbx+84h]
0x14031a37c  cmp     edx, eax
0x14031a37e  jz      short loc_14031A3EF
0x14031a380  mov     r8d, edx
0x14031a383  mov     rdi, 0FFFFFFFFC000000Dh
0x14031a38a  mov     rdx, rsi
0x14031a38d  mov     [rsp+170h+var_150], rdi
0x14031a392  mov     r9d, eax
0x14031a395  mov     ecx, 2
0x14031a39a  call    cs:__imp_WdLogSingleEntry4
0x14031a3a1  nop     dword ptr [rax+rax+00h]
0x14031a3a6  mov     [rsp+170h+var_130], r12
0x14031a3ab  lea     r9, aDevice0xI64xCa_1; "Device 0x%I64x: Caller specified incorr"...
0x14031a3b2  mov     cs:WdLogGlobalForLineNumber, 1F0Dh
0x14031a3bc  mov     eax, [r14+10h]
0x14031a3c0  mov     ecx, [rbx+84h]
0x14031a3c6  mov     [rsp+170h+var_138], rdi
0x14031a3cb  mov     [rsp+170h+var_140], rax
0x14031a3d0  mov     [rsp+170h+var_148], rcx
0x14031a3d5  or      r8d, 0FFFFFFFFh
0x14031a3d9  mov     edx, 40000h
0x14031a3de  mov     [rsp+170h+var_150], rsi
0x14031a3e3  xor     ecx, ecx
0x14031a3e5  call    DxgkLogInternalTriageEvent
0x14031a3ea  jmp     loc_14031A313
0x14031a3ef  mov     eax, [rbx+0Ch]
0x14031a3f2  test    al, 4
0x14031a3f4  jz      short loc_14031A43B
0x14031a3f6  mov     rdi, 0FFFFFFFFC000000Dh
0x14031a3fd  mov     rdx, rsi
0x14031a400  mov     r8, rdi
0x14031a403  mov     ecx, 2
0x14031a408  call    cs:__imp_WdLogSingleEntry2
0x14031a40f  nop     dword ptr [rax+rax+00h]
0x14031a414  mov     [rsp+170h+var_130], r12
0x14031a419  lea     r9, aDevice0xI64xPr; "Device 0x%I64x: PrivateRuntimeData has "...
0x14031a420  mov     [rsp+170h+var_138], r12
0x14031a425  mov     [rsp+170h+var_140], r12
0x14031a42a  mov     [rsp+170h+var_148], rdi
0x14031a42f  mov     cs:WdLogGlobalForLineNumber, 1F18h
0x14031a439  jmp     short loc_14031A3D5
0x14031a43b  shr     edi, 8
0x14031a43e  and     dil, 1
0x14031a442  jnz     short loc_14031A498
0x14031a444  mov     eax, [rbx+70h]
0x14031a447  mov     ecx, [r14+20h]
0x14031a44b  cmp     ecx, eax
0x14031a44d  jz      short loc_14031A484
0x14031a44f  mov     r8d, ecx
0x14031a452  mov     rdi, 0FFFFFFFFC000000Dh
0x14031a459  mov     ecx, 3
0x14031a45e  mov     [rsp+170h+var_150], rdi
0x14031a463  mov     r9d, eax
0x14031a466  mov     rdx, rsi
0x14031a469  call    cs:__imp_WdLogSingleEntry4
0x14031a470  nop     dword ptr [rax+rax+00h]
0x14031a475  mov     cs:WdLogGlobalForLineNumber, 1F26h
0x14031a47f  jmp     loc_14031A313
0x14031a484  test    eax, eax
0x14031a486  jz      short loc_14031A498
0x14031a488  mov     rdx, [rbx+68h]; Src
0x14031a48c  mov     r8, rax; Size
0x14031a48f  mov     rcx, [r14+28h]; void *
0x14031a493  call    memmove
0x14031a498  mov     ecx, [r14+10h]
0x14031a49c  mov     eax, 60h ; '`'
0x14031a4a1  mul     rcx
0x14031a4a4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14031a4ab  mov     edx, 4B677844h
0x14031a4b0  mov     r8d, 100h
0x14031a4b6  cmovb   rax, rcx
0x14031a4ba  mov     rcx, rax
0x14031a4bd  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14031a4c2  mov     ecx, [r14+10h]
0x14031a4c6  mov     r11, rax
0x14031a4c9  mov     [rbp+70h+arg_18], rax
0x14031a4d0  test    rax, rax
0x14031a4d3  jnz     short loc_14031A53C
0x14031a4d5  mov     r8d, ecx
0x14031a4d8  mov     r9, 0FFFFFFFFC0000017h
0x14031a4df  lea     ecx, [rax+3]
0x14031a4e2  mov     rdx, rsi
0x14031a4e5  call    cs:__imp_WdLogSingleEntry3
0x14031a4ec  nop     dword ptr [rax+rax+00h]
0x14031a4f1  mov     edi, 0C0000017h
0x14031a4f6  mov     cs:WdLogGlobalForLineNumber, 1F39h
0x14031a500  cmp     [rbp+70h+var_E8], r12b
0x14031a504  jz      short loc_14031A50F
0x14031a506  lea     rcx, [rbp+70h+var_F0]; this
0x14031a50a  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x14031a50f  mov     r15, [rbp+70h+arg_18]
0x14031a516  mov     rcx, r15; void *
0x14031a519  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14031a51e  mov     rbx, [rsp+170h+arg_8]
0x14031a526  mov     eax, edi
0x14031a528  add     rsp, 140h
0x14031a52f  pop     r15
0x14031a531  pop     r14
0x14031a533  pop     r13
0x14031a535  pop     r12
0x14031a537  pop     rdi
0x14031a538  pop     rsi
0x14031a539  pop     rbp
0x14031a53a  retn
0x14031a53c  mov     eax, [r14]
0x14031a53f  mov     r9, [r14+38h]
0x14031a543  mov     edx, [r14+30h]
0x14031a547  mov     [rbp+70h+var_A0.hDevice], eax
0x14031a54a  mov     eax, dword ptr [rbp+70h+var_A0.Flags.CreateResource]
0x14031a54d  btr     eax, 7
0x14031a551  mov     [rbp+70h+var_A0.NumAllocations], ecx
0x14031a554  mov     ecx, dword ptr [rbp+70h+arg_30]
0x14031a55a  and     ecx, 1
0x14031a55d  mov     [rbp+70h+var_A0.hGlobalShare], r12d
0x14031a561  shl     ecx, 7
0x14031a564  or      ecx, eax
0x14031a566  mov     qword ptr [rbp+70h+var_A0.20h], r9
0x14031a56a  or      ecx, 41h
0x14031a56d  mov     [rbp+70h+var_A0.PrivateDriverDataSize], edx
0x14031a570  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], ecx
0x14031a573  mov     qword ptr [rbp+70h+var_A0.30h], r11
0x14031a577  mov     eax, [rbx+0Ch]
0x14031a57a  shl     eax, 5
0x14031a57d  xor     eax, ecx
0x14031a57f  and     eax, 100000h
0x14031a584  xor     eax, ecx
0x14031a586  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], eax
0x14031a589  test    dil, dil
0x14031a58c  jnz     short loc_14031A5D6
0x14031a58e  mov     eax, [rbx+80h]
0x14031a594  cmp     edx, eax
0x14031a596  jz      short loc_14031A5D6
0x14031a598  mov     r8d, edx
0x14031a59b  mov     rdi, 0FFFFFFFFC000000Dh
0x14031a5a2  mov     rdx, rsi
0x14031a5a5  mov     [rsp+170h+var_150], rdi
0x14031a5aa  mov     r9d, eax
0x14031a5ad  mov     ecx, 3
0x14031a5b2  call    cs:__imp_WdLogSingleEntry4
0x14031a5b9  nop     dword ptr [rax+rax+00h]
0x14031a5be  mov     cs:WdLogGlobalForLineNumber, 1F54h
0x14031a5c8  lea     rcx, [rbp+70h+var_F0]; this
0x14031a5cc  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x14031a5d1  jmp     loc_14031A50F
0x14031a5d6  mov     [rbp+70h+arg_10], r12d
0x14031a5dd  mov     r8d, r12d
0x14031a5e0  test    edx, edx
0x14031a5e2  jz      short loc_14031A5FD
0x14031a5e4  mov     r8, rdx; Size
0x14031a5e7  mov     rcx, r9; void *
0x14031a5ea  mov     rdx, [rbx+78h]; Src
0x14031a5ee  call    memmove
0x14031a5f3  mov     r11, [rbp+70h+arg_18]
0x14031a5fa  mov     r8d, r12d
0x14031a5fd  mov     r10, [r14+48h]
0x14031a601  mov     r9d, r12d
0x14031a604  mov     rdi, [rbx+88h]
0x14031a60b  mov     dword ptr [rbp+70h+arg_0], r12d
0x14031a612  lea     r12, [r14+40h]
0x14031a616  mov     r15, r12
0x14031a619  mov     [rbp+70h+var_E0], r10
0x14031a61d  cmp     r9d, [r14+10h]
0x14031a621  jnb     loc_14031A73B
0x14031a627  mov     ecx, [rdi-8]
0x14031a62a  lea     eax, [rcx+r8]
0x14031a62e  cmp     eax, r8d
0x14031a631  jb      loc_14031A70E
0x14031a637  lea     r15, [r14+40h]
0x14031a63b  cmp     eax, [r15]
0x14031a63e  ja      loc_14031A6DF
0x14031a644  mov     rdx, [rdi-10h]; Src
0x14031a648  test    rdx, rdx
0x14031a64b  jz      short loc_14031A671
0x14031a64d  mov     r8d, ecx; Size
0x14031a650  mov     rcx, r10; void *
0x14031a653  call    memmove
0x14031a658  mov     r8d, [rbp+70h+arg_10]
0x14031a65f  mov     r9d, dword ptr [rbp+70h+arg_0]
0x14031a666  mov     r10, [rbp+70h+var_E0]
0x14031a66a  mov     r11, [rbp+70h+arg_18]
0x14031a671  xor     ecx, ecx
0x14031a673  mov     eax, r9d
0x14031a676  lea     rdx, [rax+rax*2]
0x14031a67a  shl     rdx, 5
0x14031a67e  mov     [rdx+r11], ecx
0x14031a682  mov     [rdx+r11+8], rcx
0x14031a687  mov     eax, [rdi-2Ch]
0x14031a68a  mov     [rdx+r11+20h], ecx
0x14031a68f  shr     eax, 6
0x14031a692  and     eax, 0Fh
0x14031a695  mov     [rdx+r11+1Ch], eax
0x14031a69a  mov     eax, [rdi-2Ch]
0x14031a69d  mov     ecx, eax
0x14031a69f  shr     ecx, 0Ch
0x14031a6a2  or      ecx, eax
0x14031a6a4  mov     [rdx+r11+10h], r10
0x14031a6a9  shr     ecx, 1
0x14031a6ab  or      ecx, eax
0x14031a6ad  and     ecx, 1
0x14031a6b0  mov     [rdx+r11+20h], ecx
0x14031a6b5  mov     eax, [rdi-8]
0x14031a6b8  mov     [rdx+r11+18h], eax
0x14031a6bd  mov     eax, [rdi-8]
0x14031a6c0  mov     rdi, [rdi]
0x14031a6c3  add     r8d, eax
0x14031a6c6  add     r10, rax
0x14031a6c9  mov     [rbp+70h+arg_10], r8d
0x14031a6d0  inc     r9d
0x14031a6d3  mov     dword ptr [rbp+70h+arg_0], r9d
0x14031a6da  jmp     loc_14031A619
0x14031a6df  mov     r8, 0FFFFFFFFC0000017h
0x14031a6e6  mov     rdx, rsi
0x14031a6e9  mov     ecx, 3
0x14031a6ee  call    cs:__imp_WdLogSingleEntry2
0x14031a6f5  nop     dword ptr [rax+rax+00h]
0x14031a6fa  mov     cs:WdLogGlobalForLineNumber, 1F77h
0x14031a704  mov     edi, 0C0000017h
  ... truncated ...
```
