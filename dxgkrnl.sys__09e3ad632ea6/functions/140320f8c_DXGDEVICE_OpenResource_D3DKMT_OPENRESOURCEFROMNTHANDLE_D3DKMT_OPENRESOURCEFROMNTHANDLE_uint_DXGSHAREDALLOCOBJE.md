# DXGDEVICE::OpenResource<_D3DKMT_OPENRESOURCEFROMNTHANDLE>(_D3DKMT_OPENRESOURCEFROMNTHANDLE *,uint,_DXGSHAREDALLOCOBJECT *,uint,COREDEVICEACCESS *,int,_EPROCESS *,uint *,unsigned __int64 *)

- ea: `0x140320f8c`
- end: `0x140321a24`
- name: `??$OpenResource@U_D3DKMT_OPENRESOURCEFROMNTHANDLE@@@DXGDEVICE@@QEAAJPEAU_D3DKMT_OPENRESOURCEFROMNTHANDLE@@IPEAU_DXGSHAREDALLOCOBJECT@@IPEAVCOREDEVICEACCESS@@HPEAU_EPROCESS@@PEAIPEA_K@Z`
- size: `2712`
- prototype: `__int64 __fastcall(ADAPTER_RENDER **, __int64, unsigned int, __int64, unsigned int, struct COREDEVICEACCESS *, char, struct _EPROCESS *, unsigned int *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140212540`
- `0x14024d9cc`
- `0x14031ffb8`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x1400146ac`
- `0x140015290`
- `0x1400162a4`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001cd10`
- `0x14002dbc0`
- `0x14003bd18`
- `0x14006e240`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140297be0`
- `0x140320f8c`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x14036fa30`
- `0x14036fdd0`
- `0x140377080`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140321913`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140321913`
- `watchdog!WdLogSingleEntry4` at `0x14032110a`
- `watchdog!WdLogSingleEntry4` at `0x1403211d9`
- `watchdog!WdLogSingleEntry4` at `0x140321322`
- `watchdog!WdLogSingleEntry4` at `0x14032110a`
- `watchdog!WdLogSingleEntry4` at `0x1403211d9`
- `watchdog!WdLogSingleEntry4` at `0x140321322`
- `watchdog!WdLogSingleEntry2` at `0x140321178`
- `watchdog!WdLogSingleEntry2` at `0x14032145e`
- `watchdog!WdLogSingleEntry2` at `0x140321490`
- `watchdog!WdLogSingleEntry2` at `0x1403219eb`
- `watchdog!WdLogSingleEntry2` at `0x140321178`
- `watchdog!WdLogSingleEntry2` at `0x14032145e`
- `watchdog!WdLogSingleEntry2` at `0x140321490`
- `watchdog!WdLogSingleEntry2` at `0x1403219eb`
- `watchdog!WdLogSingleEntry3` at `0x14032106d`
- `watchdog!WdLogSingleEntry3` at `0x140321255`
- `watchdog!WdLogSingleEntry3` at `0x14032106d`
- `watchdog!WdLogSingleEntry3` at `0x140321255`
- `watchdog!WdLogSingleEntry0` at `0x140320fe1`
- `watchdog!WdLogSingleEntry0` at `0x14032155b`
- `watchdog!WdLogSingleEntry0` at `0x14032173b`
- `watchdog!WdLogSingleEntry0` at `0x140321796`
- `watchdog!WdLogSingleEntry0` at `0x140321832`
- `watchdog!WdLogSingleEntry0` at `0x14032198d`
- `watchdog!WdLogSingleEntry0` at `0x140320fe1`
- `watchdog!WdLogSingleEntry0` at `0x14032155b`
- `watchdog!WdLogSingleEntry0` at `0x14032173b`
- `watchdog!WdLogSingleEntry0` at `0x140321796`
- `watchdog!WdLogSingleEntry0` at `0x140321832`
- `watchdog!WdLogSingleEntry0` at `0x14032198d`
- `watchdog!WdLogSingleEntry1` at `0x1403210ca`
- `watchdog!WdLogSingleEntry1` at `0x140321536`
- `watchdog!WdLogSingleEntry1` at `0x1403210ca`
- `watchdog!WdLogSingleEntry1` at `0x140321536`

## string_xrefs

- `0x140321570`: `KMCreateAlloc.hResource != 0`

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
  const wchar_t *v18; // r9
  int v19; // eax
  __int64 v20; // rax
  D3DDDI_ALLOCATIONINFO *v21; // rax
  UINT v22; // ecx
  D3DDDI_ALLOCATIONINFO *v23; // r11
  D3DKMT_CREATESTANDARDALLOCATION *v25; // r9
  size_t v26; // rdx
  unsigned int v27; // r8d
  unsigned int *v28; // r10
  unsigned int v29; // r9d
  _QWORD *v30; // rdi
  unsigned int *v31; // r12
  unsigned int *v32; // r15
  unsigned int v33; // ecx
  const void *v34; // rdx
  __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  D3DKMT_HANDLE hResource; // eax
  __int64 v41; // r10
  _DWORD *v42; // r9
  unsigned __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rax
  unsigned int *v46; // r15
  unsigned int v47; // edx
  unsigned int v48; // r8d
  DXG_GUEST_VIRTUALGPU_VMBUS *v49; // rcx
  int v50; // r9d
  unsigned int v51; // eax
  struct DXGPROCESS *v52; // r13
  unsigned int v53; // eax
  __int64 v54; // r9
  int v55; // ecx
  struct DXGRESOURCE *v56; // rdx
  unsigned int v57; // r12d
  unsigned int v58; // eax
  __int64 v59; // r9
  int v60; // ecx
  struct DXGALLOCATION *v61; // rdx
  __int64 v62; // r15
  unsigned int v63; // eax
  __int64 v64; // r13
  __int64 v65; // rbx
  unsigned int CurrentProcessId; // eax
  int v67; // r8d
  __int64 v68; // [rsp+28h] [rbp-D8h]
  __int64 v69; // [rsp+30h] [rbp-D0h]
  __int64 v70; // [rsp+38h] [rbp-C8h]
  int v71; // [rsp+38h] [rbp-C8h]
  int v72; // [rsp+68h] [rbp-98h]
  unsigned int v73; // [rsp+70h] [rbp-90h]
  char v74[8]; // [rsp+80h] [rbp-80h] BYREF
  char v75; // [rsp+88h] [rbp-78h]
  unsigned int *v76; // [rsp+90h] [rbp-70h]
  __int64 v77; // [rsp+98h] [rbp-68h]
  __int64 v78; // [rsp+A0h] [rbp-60h]
  __int64 v79; // [rsp+A8h] [rbp-58h]
  struct DXGPROCESS *Current; // [rsp+B0h] [rbp-50h]
  __int64 v81; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v82; // [rsp+C0h] [rbp-40h]
  struct _D3DKMT_CREATEALLOCATION v83; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v84[80]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v85; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v86; // [rsp+190h] [rbp+90h] BYREF
  D3DDDI_ALLOCATIONINFO *v87; // [rsp+198h] [rbp+98h]

  v86 = a3;
  v13 = 0;
  memset(&v83, 0, sizeof(v83));
  if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(a1[2]) )
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
  v14 = *((_DWORD *)Current + 102);
  DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX((DXGGLOBALSHAREMUTEX *)v74);
  DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)v74);
  if ( !a4 )
  {
    v16 = -1073741811;
    WdLogSingleEntry2(2, a1, -1073741811);
    WdLogGlobalForLineNumber = 7953;
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
          WdLogSingleEntry1(4, -1073741790);
          WdLogGlobalForLineNumber = 7963;
          goto LABEL_6;
        }
      }
    }
    if ( *(_DWORD *)(v15 + 132) != *(_DWORD *)(a2 + 16) )
    {
      v16 = -1073741811;
      WdLogSingleEntry4(2, a1);
      v18 = L"Device 0x%I64x: Caller specified incorrect number of allocations, should have been 0x%I64x but was 0x%I64x, "
             "returning 0x%I64x";
      WdLogGlobalForLineNumber = 7975;
      v70 = -1073741811;
      v69 = *(unsigned int *)(a2 + 16);
      v68 = *(unsigned int *)(v15 + 132);
LABEL_13:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v18, (__int64)a1, v68, v69, v70, 0);
      goto LABEL_6;
    }
    if ( (*(_DWORD *)(v15 + 12) & 4) != 0 )
    {
      v16 = -1073741811;
      WdLogSingleEntry2(2, a1, -1073741811);
      v18 = L"Device 0x%I64x: PrivateRuntimeData has been marked as invalid, returning 0x%I64x";
      v70 = 0;
      v69 = 0;
      v68 = -1073741811;
      WdLogGlobalForLineNumber = 7986;
      goto LABEL_13;
    }
    if ( (v14 & 0x100) == 0 )
    {
      v19 = *(_DWORD *)(v15 + 112);
      if ( *(_DWORD *)(a2 + 32) != v19 )
      {
        v16 = -1073741811;
        WdLogSingleEntry4(3, a1);
        WdLogGlobalForLineNumber = 8000;
        goto LABEL_6;
      }
      if ( v19 )
        memmove(*(void **)(a2 + 40), *(const void **)(v15 + 104), *(unsigned int *)(v15 + 112));
    }
    v20 = 96LL * *(unsigned int *)(a2 + 16);
    if ( !is_mul_ok(*(unsigned int *)(a2 + 16), 0x60u) )
      v20 = -1;
    v21 = (D3DDDI_ALLOCATIONINFO *)operator new[](v20, 1265072196, 256);
    v22 = *(_DWORD *)(a2 + 16);
    v23 = v21;
    v87 = v21;
    if ( !v21 )
    {
      WdLogSingleEntry3(3, a1, v22, -1073741801);
      v16 = -1073741801;
      WdLogGlobalForLineNumber = 8019;
      if ( v75 )
        DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v74);
      goto LABEL_27;
    }
    v25 = *(D3DKMT_CREATESTANDARDALLOCATION **)(a2 + 56);
    v26 = *(unsigned int *)(a2 + 48);
    v83.hDevice = *(_DWORD *)a2;
    v83.NumAllocations = v22;
    v83.hGlobalShare = 0;
    v83.pStandardAllocation = v25;
    v83.PrivateDriverDataSize = v26;
    v83.Flags = (D3DKMT_CREATEALLOCATIONFLAGS)(*(_DWORD *)&v83.Flags & 0xFFFFFF7F | ((a7 & 1) << 7) | 0x41);
    v83.pAllocationInfo = v21;
    *(_DWORD *)&v83.Flags ^= (*(_DWORD *)&v83.Flags ^ (32 * *(_DWORD *)(v15 + 12))) & 0x100000;
    if ( (v14 & 0x100) == 0 && (_DWORD)v26 != *(_DWORD *)(v15 + 128) )
    {
      v16 = -1073741811;
      WdLogSingleEntry4(3, a1);
      WdLogGlobalForLineNumber = 8046;
LABEL_32:
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v74);
      goto LABEL_27;
    }
    v86 = 0;
    v27 = 0;
    if ( (_DWORD)v26 )
    {
      memmove(v25, *(const void **)(v15 + 120), v26);
      v23 = v87;
      v27 = 0;
    }
    v28 = *(unsigned int **)(a2 + 72);
    v29 = 0;
    v30 = *(_QWORD **)(v15 + 136);
    LODWORD(v85) = 0;
    v31 = (unsigned int *)(a2 + 64);
    v32 = (unsigned int *)(a2 + 64);
    while ( 1 )
    {
      v76 = v28;
      if ( v29 >= *(_DWORD *)(a2 + 16) )
        break;
      v33 = *((_DWORD *)v30 - 2);
      if ( v33 + v27 < v27 )
      {
        v16 = -1073741675;
        WdLogSingleEntry2(3, a1, -1073741675);
        WdLogGlobalForLineNumber = 8072;
        goto LABEL_32;
      }
      v32 = (unsigned int *)(a2 + 64);
      if ( v33 + v27 > *(_DWORD *)(a2 + 64) )
      {
        WdLogSingleEntry2(3, a1, -1073741801);
        WdLogGlobalForLineNumber = 8081;
        v16 = -1073741801;
        goto LABEL_32;
      }
      v34 = (const void *)*(v30 - 2);
      if ( v34 )
      {
        memmove(v28, v34, v33);
        v27 = v86;
        v29 = v85;
        v28 = v76;
        v23 = v87;
      }
      v35 = 96LL * v29;
      *(D3DKMT_HANDLE *)((char *)&v23->hAllocation + v35) = 0;
      *(const void **)((char *)&v23->pSystemMem + v35) = 0;
      v36 = *((_DWORD *)v30 - 11);
      *(UINT *)((char *)&v23->Flags.Value + v35) = 0;
      *(D3DDDI_VIDEO_PRESENT_SOURCE_ID *)((char *)&v23->VidPnSourceId + v35) = (v36 >> 6) & 0xF;
      v37 = *((_DWORD *)v30 - 11);
      *(void **)((char *)&v23->pPrivateDriverData + v35) = v28;
      *(UINT *)((char *)&v23->Flags.Value + v35) = v37 & 1 | (((v37 | (v37 >> 12)) & 2) != 0);
      *(UINT *)((char *)&v23->PrivateDriverDataSize + v35) = *((_DWORD *)v30 - 2);
      v38 = *((unsigned int *)v30 - 2);
      v30 = (_QWORD *)*v30;
      v27 += v38;
      v28 = (unsigned int *)((char *)v28 + v38);
      v86 = v27;
      LODWORD(v85) = ++v29;
    }
    if ( v75 )
    {
      DXGAUTOMUTEX::Release((DXGAUTOMUTEX *)v74);
      v32 = (unsigned int *)(a2 + 64);
    }
    v39 = DXGDEVICE::CreateAllocation(
            (DXGDEVICE *)a1,
            &v83,
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
    v16 = v39;
    if ( v39 < 0 )
    {
      WdLogSingleEntry1(3, v39);
      WdLogGlobalForLineNumber = 8112;
LABEL_27:
      v13 = v87;
      goto LABEL_28;
    }
    hResource = v83.hResource;
    if ( v83.hResource )
    {
      v31 = v32;
    }
    else
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 8117;
      DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"KMCreateAlloc.hResource != 0", 8117, 0, 0, 0, 0);
      hResource = v83.hResource;
    }
    v41 = 0;
    v42 = *(_DWORD **)(a2 + 24);
    *v31 = v86;
    v43 = *(unsigned int *)(a2 + 16);
    *(_DWORD *)(a2 + 80) = hResource;
    if ( (_DWORD)v43 )
    {
      do
      {
        v44 = 96 * v41;
        v41 = (unsigned int)(v41 + 1);
        *v42 = *(D3DKMT_HANDLE *)((char *)&v83.pAllocationInfo->hAllocation + v44);
        v42 += 20;
        *((_QWORD *)v42 - 9) = *(_QWORD *)(a2 + 72)
                             + (unsigned int)(*(_DWORD *)((char *)&v83.pAllocationInfo->pPrivateDriverData + v44)
                                            - *(_DWORD *)(a2 + 72));
        *(v42 - 16) = *(UINT *)((char *)&v83.pAllocationInfo->PrivateDriverDataSize + v44);
        v43 = *(unsigned int *)(a2 + 16);
      }
      while ( (unsigned int)v41 < (unsigned int)v43 );
    }
    if ( (*((_BYTE *)a1 + 1917) & 1) == 0 )
      goto LABEL_27;
    v45 = 4 * v43;
    if ( !is_mul_ok(v43, 4u) )
      v45 = -1;
    v76 = (unsigned int *)operator new[](v45, 1265072196, 256);
    v46 = v76;
    if ( !v76 )
    {
      v16 = -1073741801;
      goto LABEL_27;
    }
    v47 = *v31;
    v48 = *(_DWORD *)(a2 + 16);
    v49 = (DXG_GUEST_VIRTUALGPU_VMBUS *)(*((_QWORD *)a1[2] + 2) + 4792LL);
    v50 = *(_DWORD *)(v15 + 12) >> 3;
    v86 = 0;
    if ( (v50 & 1) != 0 )
      v51 = *(_DWORD *)(a4 + 40);
    else
      v51 = *(_DWORD *)(v15 + 28);
    v52 = Current;
    v16 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendOpenResource(
            v49,
            Current,
            (struct DXGDEVICE *)a1,
            v50 & 1,
            v51,
            v48,
            v47,
            &v86,
            v76);
    if ( v16 < 0 )
    {
LABEL_95:
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v46);
      goto LABEL_27;
    }
    DXGHANDLETABLELOCKSHARED::DXGHANDLETABLELOCKSHARED((DXGHANDLETABLELOCKSHARED *)v84, v52);
    v53 = (*(_DWORD *)(a2 + 80) >> 6) & 0xFFFFFF;
    if ( v53 < *((_DWORD *)v52 + 74) )
    {
      v54 = *((_QWORD *)v52 + 35);
      if ( ((*(_DWORD *)(a2 + 80) >> 25) & 0x60) == (*(_BYTE *)(v54 + 16LL * v53 + 8) & 0x60)
        && (*(_DWORD *)(v54 + 16LL * v53 + 8) & 0x2000) == 0 )
      {
        v55 = *(_DWORD *)(v54 + 16LL * v53 + 8) & 0x1F;
        if ( v55 )
        {
          if ( v55 == 4 )
          {
            v56 = *(struct DXGRESOURCE **)(v54 + 16LL * v53);
            goto LABEL_69;
          }
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
    }
    v56 = 0;
LABEL_69:
    DXGRESOURCEREFERENCE::DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v81, v56);
    if ( v81 )
    {
      v57 = 0;
      *(_DWORD *)(v81 + 20) = v86;
      while ( v57 < *(_DWORD *)(a2 + 16) )
      {
        v58 = (*(_DWORD *)(*(_QWORD *)(a2 + 24) + 80LL * v57) >> 6) & 0xFFFFFF;
        if ( v58 < *((_DWORD *)v52 + 74)
          && (v59 = *((_QWORD *)v52 + 35),
              ((*(_DWORD *)(*(_QWORD *)(a2 + 24) + 80LL * v57) >> 25) & 0x60) == (*(_BYTE *)(v59 + 16LL * v58 + 8) & 0x60))
          && (*(_DWORD *)(v59 + 16LL * v58 + 8) & 0x2000) == 0
          && (v60 = *(_DWORD *)(v59 + 16LL * v58 + 8) & 0x1F) != 0 )
        {
          if ( v60 == 5 )
          {
            v61 = *(struct DXGALLOCATION **)(v59 + 16LL * v58);
          }
          else
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 318;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
            v61 = 0;
          }
        }
        else
        {
          v61 = 0;
        }
        DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v85, v61);
        v62 = v85;
        if ( !v85 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 8174;
          v16 = -1073741811;
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v85);
          break;
        }
        v63 = v76[v57];
        *(_BYTE *)(v85 + 128) |= 4u;
        *(_DWORD *)(v62 + 20) = v63;
        v86 = v63;
        if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x1000) != 0 )
        {
          v64 = *(_QWORD *)(v62 + 40);
          if ( v64 )
          {
            v77 = *(_QWORD *)(v64 + 48);
            v78 = *(unsigned int *)(v64 + 16);
          }
          else
          {
            v77 = 0;
            v78 = 0;
          }
          v82 = *(unsigned int *)(v62 + 16);
          if ( v64 )
            v79 = *(_QWORD *)(v64 + 56);
          else
            v79 = 0;
          v65 = *((_QWORD *)a1[2] + 2);
          CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
          McTemplateK0ppppppppppppq_EtwWriteTransfer(
            v79,
            (unsigned int)EventCreateDeviceAllocation,
            v67,
            CurrentProcessId,
            (char)a1,
            v65,
            v62,
            v71,
            v64,
            v79,
            v82,
            v78,
            v77,
            v72,
            v73,
            v86);
          v52 = Current;
        }
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v85);
        ++v57;
      }
      v46 = v76;
    }
    else
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 8163;
      v16 = -1073741811;
    }
    DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((DXGRESOURCEREFERENCE *)&v81);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v84);
    goto LABEL_95;
  }
  v16 = -1073741811;
  WdLogSingleEntry3(3, a1, a4, -1073741811);
  WdLogGlobalForLineNumber = 7922;
LABEL_6:
  DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)v74);
LABEL_28:
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v13);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140320f8c  mov     [rsp-8+arg_8], rbx
0x140320f91  mov     [rsp-8+arg_10], r8d
0x140320f96  push    rbp
0x140320f97  push    rsi
0x140320f98  push    rdi
0x140320f99  push    r12
0x140320f9b  push    r13
0x140320f9d  push    r14
0x140320f9f  push    r15
0x140320fa1  lea     rbp, [rsp-40h]
0x140320fa6  sub     rsp, 140h
0x140320fad  xor     r12d, r12d
0x140320fb0  mov     r14, rdx
0x140320fb3  mov     rsi, rcx
0x140320fb6  xor     edx, edx; Val
0x140320fb8  lea     rcx, [rbp+70h+var_A0]; void *
0x140320fbc  mov     r13, r9
0x140320fbf  mov     r15d, r12d
0x140320fc2  lea     r8d, [r12+48h]; Size
0x140320fc7  call    memset
0x140320fcc  mov     rcx, [rsi+10h]; this
0x140320fd0  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140320fd5  or      ebx, 0FFFFFFFFh
0x140320fd8  test    al, al
0x140320fda  jnz     short loc_140321027
0x140320fdc  lea     ecx, [r12+1]
0x140320fe1  call    cs:__imp_WdLogSingleEntry0
0x140320fe8  nop     dword ptr [rax+rax+00h]
0x140320fed  mov     [rsp+170h+var_130], r12
0x140320ff2  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x140320ff9  mov     [rsp+170h+var_138], r12
0x140320ffe  mov     eax, 1EDCh
0x140321003  mov     [rsp+170h+var_140], r12
0x140321008  mov     r8d, ebx
0x14032100b  mov     [rsp+170h+var_148], r12
0x140321010  mov     edx, 40002h
0x140321015  xor     ecx, ecx
0x140321017  mov     [rsp+170h+var_150], rax
0x14032101c  mov     cs:WdLogGlobalForLineNumber, eax
0x140321022  call    DxgkLogInternalTriageEvent
0x140321027  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14032102c  lea     rcx, [rbp+70h+var_F0]; this
0x140321030  mov     [rbp+70h+var_C0], rax
0x140321034  mov     edi, [rax+198h]
0x14032103a  call    ??0DXGGLOBALSHAREMUTEX@@QEAA@XZ; DXGGLOBALSHAREMUTEX::DXGGLOBALSHAREMUTEX(void)
0x14032103f  lea     rcx, [rbp+70h+var_F0]; this
0x140321043  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x140321048  test    r13, r13
0x14032104b  jz      loc_1403219D9
0x140321051  mov     rbx, [r13+10h]
0x140321055  test    rbx, rbx
0x140321058  jnz     short loc_140321091
0x14032105a  mov     rdi, 0FFFFFFFFC000000Dh
0x140321061  lea     ecx, [rbx+3]
0x140321064  mov     r9, rdi
0x140321067  mov     r8, r13
0x14032106a  mov     rdx, rsi
0x14032106d  call    cs:__imp_WdLogSingleEntry3
0x140321074  nop     dword ptr [rax+rax+00h]
0x140321079  mov     cs:WdLogGlobalForLineNumber, 1EF2h
0x140321083  lea     rcx, [rbp+70h+var_F0]; this
0x140321087  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x14032108c  jmp     loc_140321286
0x140321091  mov     rax, [rbx+88h]
0x140321098  mov     ecx, [rax-2Ch]
0x14032109b  test    cl, 2
0x14032109e  jz      short loc_1403210E2
0x1403210a0  mov     rax, [rsi+28h]
0x1403210a4  mov     rax, [rax+58h]
0x1403210a8  test    rax, rax
0x1403210ab  jz      short loc_1403210E2
0x1403210ad  mov     rax, [rax+0E0h]
0x1403210b4  call    _guard_dispatch_icall
0x1403210b9  test    eax, eax
0x1403210bb  jnz     short loc_1403210E2
0x1403210bd  mov     rdi, 0FFFFFFFFC0000022h
0x1403210c4  lea     ecx, [rax+4]
0x1403210c7  mov     rdx, rdi
0x1403210ca  call    cs:__imp_WdLogSingleEntry1
0x1403210d1  nop     dword ptr [rax+rax+00h]
0x1403210d6  mov     cs:WdLogGlobalForLineNumber, 1F1Bh
0x1403210e0  jmp     short loc_140321083
0x1403210e2  mov     eax, [r14+10h]
0x1403210e6  mov     edx, [rbx+84h]
0x1403210ec  cmp     edx, eax
0x1403210ee  jz      short loc_14032115F
0x1403210f0  mov     r8d, edx
0x1403210f3  mov     rdi, 0FFFFFFFFC000000Dh
0x1403210fa  mov     rdx, rsi
0x1403210fd  mov     [rsp+170h+var_150], rdi
0x140321102  mov     r9d, eax
0x140321105  mov     ecx, 2
0x14032110a  call    cs:__imp_WdLogSingleEntry4
0x140321111  nop     dword ptr [rax+rax+00h]
0x140321116  mov     [rsp+170h+var_130], r12
0x14032111b  lea     r9, aDevice0xI64xCa_1; "Device 0x%I64x: Caller specified incorr"...
0x140321122  mov     cs:WdLogGlobalForLineNumber, 1F27h
0x14032112c  mov     eax, [r14+10h]
0x140321130  mov     ecx, [rbx+84h]
0x140321136  mov     [rsp+170h+var_138], rdi
0x14032113b  mov     [rsp+170h+var_140], rax
0x140321140  mov     [rsp+170h+var_148], rcx
0x140321145  or      r8d, 0FFFFFFFFh
0x140321149  mov     edx, 40000h
0x14032114e  mov     [rsp+170h+var_150], rsi
0x140321153  xor     ecx, ecx
0x140321155  call    DxgkLogInternalTriageEvent
0x14032115a  jmp     loc_140321083
0x14032115f  mov     eax, [rbx+0Ch]
0x140321162  test    al, 4
0x140321164  jz      short loc_1403211AB
0x140321166  mov     rdi, 0FFFFFFFFC000000Dh
0x14032116d  mov     rdx, rsi
0x140321170  mov     r8, rdi
0x140321173  mov     ecx, 2
0x140321178  call    cs:__imp_WdLogSingleEntry2
0x14032117f  nop     dword ptr [rax+rax+00h]
0x140321184  mov     [rsp+170h+var_130], r12
0x140321189  lea     r9, aDevice0xI64xPr; "Device 0x%I64x: PrivateRuntimeData has "...
0x140321190  mov     [rsp+170h+var_138], r12
0x140321195  mov     [rsp+170h+var_140], r12
0x14032119a  mov     [rsp+170h+var_148], rdi
0x14032119f  mov     cs:WdLogGlobalForLineNumber, 1F32h
0x1403211a9  jmp     short loc_140321145
0x1403211ab  shr     edi, 8
0x1403211ae  and     dil, 1
0x1403211b2  jnz     short loc_140321208
0x1403211b4  mov     eax, [rbx+70h]
0x1403211b7  mov     ecx, [r14+20h]
0x1403211bb  cmp     ecx, eax
0x1403211bd  jz      short loc_1403211F4
0x1403211bf  mov     r8d, ecx
0x1403211c2  mov     rdi, 0FFFFFFFFC000000Dh
0x1403211c9  mov     ecx, 3
0x1403211ce  mov     [rsp+170h+var_150], rdi
0x1403211d3  mov     r9d, eax
0x1403211d6  mov     rdx, rsi
0x1403211d9  call    cs:__imp_WdLogSingleEntry4
0x1403211e0  nop     dword ptr [rax+rax+00h]
0x1403211e5  mov     cs:WdLogGlobalForLineNumber, 1F40h
0x1403211ef  jmp     loc_140321083
0x1403211f4  test    eax, eax
0x1403211f6  jz      short loc_140321208
0x1403211f8  mov     rdx, [rbx+68h]; Src
0x1403211fc  mov     r8, rax; Size
0x1403211ff  mov     rcx, [r14+28h]; void *
0x140321203  call    memmove
0x140321208  mov     ecx, [r14+10h]
0x14032120c  mov     eax, 60h ; '`'
0x140321211  mul     rcx
0x140321214  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14032121b  mov     edx, 4B677844h
0x140321220  mov     r8d, 100h
0x140321226  cmovb   rax, rcx
0x14032122a  mov     rcx, rax
0x14032122d  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140321232  mov     ecx, [r14+10h]
0x140321236  mov     r11, rax
0x140321239  mov     [rbp+70h+arg_18], rax
0x140321240  test    rax, rax
0x140321243  jnz     short loc_1403212AC
0x140321245  mov     r8d, ecx
0x140321248  mov     r9, 0FFFFFFFFC0000017h
0x14032124f  lea     ecx, [rax+3]
0x140321252  mov     rdx, rsi
0x140321255  call    cs:__imp_WdLogSingleEntry3
0x14032125c  nop     dword ptr [rax+rax+00h]
0x140321261  mov     edi, 0C0000017h
0x140321266  mov     cs:WdLogGlobalForLineNumber, 1F53h
0x140321270  cmp     [rbp+70h+var_E8], r12b
0x140321274  jz      short loc_14032127F
0x140321276  lea     rcx, [rbp+70h+var_F0]; this
0x14032127a  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x14032127f  mov     r15, [rbp+70h+arg_18]
0x140321286  mov     rcx, r15; void *
0x140321289  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14032128e  mov     rbx, [rsp+170h+arg_8]
0x140321296  mov     eax, edi
0x140321298  add     rsp, 140h
0x14032129f  pop     r15
0x1403212a1  pop     r14
0x1403212a3  pop     r13
0x1403212a5  pop     r12
0x1403212a7  pop     rdi
0x1403212a8  pop     rsi
0x1403212a9  pop     rbp
0x1403212aa  retn
0x1403212ac  mov     eax, [r14]
0x1403212af  mov     r9, [r14+38h]
0x1403212b3  mov     edx, [r14+30h]
0x1403212b7  mov     [rbp+70h+var_A0.hDevice], eax
0x1403212ba  mov     eax, dword ptr [rbp+70h+var_A0.Flags.CreateResource]
0x1403212bd  btr     eax, 7
0x1403212c1  mov     [rbp+70h+var_A0.NumAllocations], ecx
0x1403212c4  mov     ecx, dword ptr [rbp+70h+arg_30]
0x1403212ca  and     ecx, 1
0x1403212cd  mov     [rbp+70h+var_A0.hGlobalShare], r12d
0x1403212d1  shl     ecx, 7
0x1403212d4  or      ecx, eax
0x1403212d6  mov     qword ptr [rbp+70h+var_A0.20h], r9
0x1403212da  or      ecx, 41h
0x1403212dd  mov     [rbp+70h+var_A0.PrivateDriverDataSize], edx
0x1403212e0  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], ecx
0x1403212e3  mov     qword ptr [rbp+70h+var_A0.30h], r11
0x1403212e7  mov     eax, [rbx+0Ch]
0x1403212ea  shl     eax, 5
0x1403212ed  xor     eax, ecx
0x1403212ef  and     eax, 100000h
0x1403212f4  xor     eax, ecx
0x1403212f6  mov     dword ptr [rbp+70h+var_A0.Flags.CreateResource], eax
0x1403212f9  test    dil, dil
0x1403212fc  jnz     short loc_140321346
0x1403212fe  mov     eax, [rbx+80h]
0x140321304  cmp     edx, eax
0x140321306  jz      short loc_140321346
0x140321308  mov     r8d, edx
0x14032130b  mov     rdi, 0FFFFFFFFC000000Dh
0x140321312  mov     rdx, rsi
0x140321315  mov     [rsp+170h+var_150], rdi
0x14032131a  mov     r9d, eax
0x14032131d  mov     ecx, 3
0x140321322  call    cs:__imp_WdLogSingleEntry4
0x140321329  nop     dword ptr [rax+rax+00h]
0x14032132e  mov     cs:WdLogGlobalForLineNumber, 1F6Eh
0x140321338  lea     rcx, [rbp+70h+var_F0]; this
0x14032133c  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x140321341  jmp     loc_14032127F
0x140321346  mov     [rbp+70h+arg_10], r12d
0x14032134d  mov     r8d, r12d
0x140321350  test    edx, edx
0x140321352  jz      short loc_14032136D
0x140321354  mov     r8, rdx; Size
0x140321357  mov     rcx, r9; void *
0x14032135a  mov     rdx, [rbx+78h]; Src
0x14032135e  call    memmove
0x140321363  mov     r11, [rbp+70h+arg_18]
0x14032136a  mov     r8d, r12d
0x14032136d  mov     r10, [r14+48h]
0x140321371  mov     r9d, r12d
0x140321374  mov     rdi, [rbx+88h]
0x14032137b  mov     dword ptr [rbp+70h+arg_0], r12d
0x140321382  lea     r12, [r14+40h]
0x140321386  mov     r15, r12
0x140321389  mov     [rbp+70h+var_E0], r10
0x14032138d  cmp     r9d, [r14+10h]
0x140321391  jnb     loc_1403214AB
0x140321397  mov     ecx, [rdi-8]
0x14032139a  lea     eax, [rcx+r8]
0x14032139e  cmp     eax, r8d
0x1403213a1  jb      loc_14032147E
0x1403213a7  lea     r15, [r14+40h]
0x1403213ab  cmp     eax, [r15]
0x1403213ae  ja      loc_14032144F
0x1403213b4  mov     rdx, [rdi-10h]; Src
0x1403213b8  test    rdx, rdx
0x1403213bb  jz      short loc_1403213E1
0x1403213bd  mov     r8d, ecx; Size
0x1403213c0  mov     rcx, r10; void *
0x1403213c3  call    memmove
0x1403213c8  mov     r8d, [rbp+70h+arg_10]
0x1403213cf  mov     r9d, dword ptr [rbp+70h+arg_0]
0x1403213d6  mov     r10, [rbp+70h+var_E0]
0x1403213da  mov     r11, [rbp+70h+arg_18]
0x1403213e1  xor     ecx, ecx
0x1403213e3  mov     eax, r9d
0x1403213e6  lea     rdx, [rax+rax*2]
0x1403213ea  shl     rdx, 5
0x1403213ee  mov     [rdx+r11], ecx
0x1403213f2  mov     [rdx+r11+8], rcx
0x1403213f7  mov     eax, [rdi-2Ch]
0x1403213fa  mov     [rdx+r11+20h], ecx
0x1403213ff  shr     eax, 6
0x140321402  and     eax, 0Fh
0x140321405  mov     [rdx+r11+1Ch], eax
0x14032140a  mov     eax, [rdi-2Ch]
0x14032140d  mov     ecx, eax
0x14032140f  shr     ecx, 0Ch
0x140321412  or      ecx, eax
0x140321414  mov     [rdx+r11+10h], r10
0x140321419  shr     ecx, 1
0x14032141b  or      ecx, eax
0x14032141d  and     ecx, 1
0x140321420  mov     [rdx+r11+20h], ecx
0x140321425  mov     eax, [rdi-8]
0x140321428  mov     [rdx+r11+18h], eax
0x14032142d  mov     eax, [rdi-8]
0x140321430  mov     rdi, [rdi]
0x140321433  add     r8d, eax
0x140321436  add     r10, rax
0x140321439  mov     [rbp+70h+arg_10], r8d
0x140321440  inc     r9d
0x140321443  mov     dword ptr [rbp+70h+arg_0], r9d
0x14032144a  jmp     loc_140321389
0x14032144f  mov     r8, 0FFFFFFFFC0000017h
0x140321456  mov     rdx, rsi
0x140321459  mov     ecx, 3
0x14032145e  call    cs:__imp_WdLogSingleEntry2
0x140321465  nop     dword ptr [rax+rax+00h]
0x14032146a  mov     cs:WdLogGlobalForLineNumber, 1F91h
0x140321474  mov     edi, 0C0000017h
  ... truncated ...
```
