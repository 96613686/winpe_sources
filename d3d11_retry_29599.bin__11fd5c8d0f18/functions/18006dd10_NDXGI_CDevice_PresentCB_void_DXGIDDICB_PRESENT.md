# NDXGI::CDevice::PresentCB(void *,DXGIDDICB_PRESENT *)

- ea: `0x18006dd10`
- end: `0x18006ee00`
- name: `?PresentCB@CDevice@NDXGI@@KAJPEAXPEAUDXGIDDICB_PRESENT@@@Z`
- size: `4336`
- prototype: `__int64 __fastcall(char *, struct DXGIDDICB_PRESENT *)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18006db90`
- `0x18006dc40`

## callees

- `0x180021b90`
- `0x180022630`
- `0x1800229a0`
- `0x180023124`
- `0x180030710`
- `0x180035c00`
- `0x180053c88`
- `0x18006dd10`
- `0x180074d78`
- `0x180081630`
- `0x180098260`
- `0x1800a9d20`
- `0x1800aa990`
- `0x1800aa9a8`
- `0x1800b72e0`
- `0x1800b7fd0`
- `0x1800bc008`
- `0x1800dd610`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006eb43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006eb43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e078`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dfd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e078`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e007`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006df63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e007`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006eb3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006eb3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ebb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006ebb4`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTPresentMultiPlaneOverlay3` at `0x18006e986`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NDXGI::CDevice::PresentCB(char *a1, struct DXGIDDICB_PRESENT *a2)
{
  struct DXGIDDICB_PRESENT *v2; // rbx
  __int64 v4; // rcx
  __int64 v5; // rax
  volatile signed __int32 *v6; // r14
  __int64 v7; // xmm1_8
  __int64 v8; // rcx
  __int64 *v9; // r13
  _DWORD *v10; // rdi
  volatile signed __int32 *v11; // rsi
  char IsEnabled; // al
  HRESULT (__stdcall *v13)(IErrorInfo *, BSTR *); // rdi
  bool v14; // r9
  struct IErrorInfo *v15; // r8
  struct IErrorInfoVtbl *lpVtbl; // rdx
  struct IErrorInfo *v17; // rsi
  bool v18; // cf
  struct IErrorInfoVtbl *p_Release; // rax
  struct IErrorInfoVtbl *v20; // rax
  std::_Ref_count_base *v21; // rdi
  __int64 *v22; // r9
  __int64 *v23; // r8
  __int64 *v24; // rdx
  bool v25; // cf
  __int64 *v26; // rax
  __int64 v27; // rdx
  char v28; // al
  __int64 v29; // rdx
  signed int v31; // edi
  _QWORD *v32; // rdx
  _QWORD *v33; // r8
  _QWORD *i; // rcx
  __int64 v35; // rdx
  bool v36; // r9
  unsigned int v37; // ebx
  __int64 v38; // rdx
  struct DXGIDDICB_PRESENT *v39; // rcx
  unsigned int v40; // eax
  __int64 v41; // rcx
  char v42; // al
  __int64 v43; // rdx
  __int64 v44; // r8
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  int v48; // r13d
  struct DXGIDDICB_PRESENT *v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rcx
  char v52; // al
  __int64 v53; // rdx
  struct DXGIDDICB_PRESENT *v54; // r9
  unsigned int v55; // eax
  __int64 v56; // rcx
  char v57; // al
  __int64 v58; // r8
  int v59; // eax
  int v60; // eax
  __int64 v61; // rcx
  char v62; // al
  int v63; // ebx
  __int64 v64; // rdx
  bool v65; // r8
  int v66; // eax
  signed int *v67; // rax
  __int64 *v68; // rcx
  int v69; // r10d
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  signed int *v73; // rax
  __int64 v74; // rcx
  char v75; // al
  __int64 v76; // rdx
  char v77; // [rsp+40h] [rbp-FE8h]
  void *Src; // [rsp+48h] [rbp-FE0h] BYREF
  bool v79[8]; // [rsp+50h] [rbp-FD8h]
  __int64 *v80; // [rsp+58h] [rbp-FD0h]
  _QWORD *v81; // [rsp+60h] [rbp-FC8h] BYREF
  __int64 v82; // [rsp+68h] [rbp-FC0h] BYREF
  int v83; // [rsp+70h] [rbp-FB8h]
  std::_Ref_count_base *v84[2]; // [rsp+78h] [rbp-FB0h]
  std::_Ref_count_base *v85[2]; // [rsp+88h] [rbp-FA0h]
  unsigned int *v86; // [rsp+98h] [rbp-F90h]
  __int64 v87; // [rsp+A0h] [rbp-F88h]
  char *v88; // [rsp+A8h] [rbp-F80h]
  struct DXGIDDICB_PRESENT *v89; // [rsp+B0h] [rbp-F78h]
  _QWORD v90[2]; // [rsp+C0h] [rbp-F68h] BYREF
  __int128 v91; // [rsp+D0h] [rbp-F58h]
  _QWORD *v92; // [rsp+E0h] [rbp-F48h]
  __int64 v93; // [rsp+E8h] [rbp-F40h]
  __int128 v94; // [rsp+F0h] [rbp-F38h]
  __int128 v95; // [rsp+100h] [rbp-F28h]
  _QWORD v96[2]; // [rsp+110h] [rbp-F18h] BYREF
  __int128 v97; // [rsp+120h] [rbp-F08h]
  __int128 v98; // [rsp+130h] [rbp-EF8h]
  _OWORD *v99; // [rsp+140h] [rbp-EE8h]
  __int64 v100; // [rsp+148h] [rbp-EE0h]
  __int128 v101; // [rsp+150h] [rbp-ED8h]
  int v102; // [rsp+16Ch] [rbp-EBCh]
  _BYTE pExceptionObject[32]; // [rsp+178h] [rbp-EB0h] BYREF
  _BYTE v104[40]; // [rsp+198h] [rbp-E90h] BYREF
  _DWORD v105[21]; // [rsp+1C0h] [rbp-E68h] BYREF
  int v106; // [rsp+214h] [rbp-E14h]
  unsigned int v107; // [rsp+218h] [rbp-E10h]
  unsigned int v108; // [rsp+21Ch] [rbp-E0Ch]
  _DWORD v109[66]; // [rsp+220h] [rbp-E08h]
  int v110; // [rsp+328h] [rbp-D00h]
  int v111; // [rsp+350h] [rbp-CD8h]
  char v112; // [rsp+354h] [rbp-CD4h] BYREF
  int v113; // [rsp+360h] [rbp-CC8h]
  unsigned int v114; // [rsp+364h] [rbp-CC4h]
  __int128 *v115; // [rsp+760h] [rbp-8C8h]
  int v116; // [rsp+768h] [rbp-8C0h]
  __int64 v117; // [rsp+770h] [rbp-8B8h]
  __int64 v118; // [rsp+778h] [rbp-8B0h]
  int v119; // [rsp+780h] [rbp-8A8h]
  __int64 v120; // [rsp+788h] [rbp-8A0h]
  char v121; // [rsp+790h] [rbp-898h]
  _DWORD v122[3]; // [rsp+7A0h] [rbp-888h] BYREF
  unsigned int v123; // [rsp+7ACh] [rbp-87Ch]
  _DWORD v124[14]; // [rsp+7B0h] [rbp-878h] BYREF
  char *v125; // [rsp+7E8h] [rbp-840h]
  unsigned int v126; // [rsp+7F8h] [rbp-830h]
  __int128 v127; // [rsp+8B0h] [rbp-778h]
  __int128 v128; // [rsp+8C0h] [rbp-768h]
  unsigned int v129; // [rsp+8D0h] [rbp-758h]
  int v130; // [rsp+8D4h] [rbp-754h]
  __int64 v131; // [rsp+D40h] [rbp-2E8h]
  _OWORD v132[5]; // [rsp+D80h] [rbp-2A8h] BYREF
  __int64 v133; // [rsp+DD0h] [rbp-258h]
  _QWORD *v134; // [rsp+DE0h] [rbp-248h]
  _BYTE v135[520]; // [rsp+DE8h] [rbp-240h] BYREF

  v2 = a2;
  *(_QWORD *)v79 = a2;
  v81 = (_QWORD *)*((_QWORD *)a2 + 2);
  *(_OWORD *)v85 = 0;
  v4 = *((_QWORD *)a1 + 9);
  if ( *(_BYTE *)(v4 + 1112) > 8u
    || *(_BYTE *)(v4 + 1112) == 8 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 1232) + 96LL) + 912LL)) )
  {
    v87 = 0;
    v77 = 0;
    v6 = (volatile signed __int32 *)v85[1];
    v86 = (unsigned int *)v85[0];
  }
  else
  {
    v5 = *((_QWORD *)a1 + 254);
    if ( v5 )
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
    v86 = (unsigned int *)*((_QWORD *)a1 + 253);
    v85[0] = (std::_Ref_count_base *)v86;
    v85[1] = *((std::_Ref_count_base **)a1 + 254);
    v6 = (volatile signed __int32 *)v85[1];
    v87 = *((_QWORD *)a1 + 255);
    v77 = a1[2048];
    *((_QWORD *)a1 + 253) = 0;
    *((_QWORD *)a1 + 254) = 0;
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    *((_QWORD *)a1 + 255) = 0;
    a1[2048] = 0;
    v2 = *(struct DXGIDDICB_PRESENT **)v79;
  }
  v82 = 0;
  v83 = 0;
  if ( a1[2052] )
  {
    v7 = v82;
    v82 = *(_QWORD *)(a1 + 2052);
    v83 = *((_DWORD *)a1 + 515);
    *(_QWORD *)(a1 + 2052) = v7;
    *((_DWORD *)a1 + 515) = 0;
  }
  *(_OWORD *)v84 = 0;
  v88 = a1;
  v89 = v2;
  v8 = *((_QWORD *)a1 + 9);
  if ( *(_BYTE *)(v8 + 1112) > 9u
    || *(_BYTE *)(v8 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 1232) + 96LL) + 912LL)) >= 4u )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
    v9 = (__int64 *)((char *)v2 + 8);
    v80 = (__int64 *)((char *)v2 + 8);
    v13 = (HRESULT (__stdcall *)(IErrorInfo *, BSTR *))*((_QWORD *)v2 + 1);
    if ( IsEnabled )
    {
      Src = a1 + 1792;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1792));
      v15 = (struct IErrorInfo *)*((_QWORD *)a1 + 229);
      lpVtbl = v15[1].lpVtbl;
      v102 = 0;
      v17 = v15;
      if ( !BYTE1(lpVtbl->GetGUID) )
      {
        do
        {
          v18 = (char *)lpVtbl->GetSource < (char *)v13;
          if ( (char *)lpVtbl->GetSource >= (char *)v13 )
            v17 = (struct IErrorInfo *)lpVtbl;
          v80 = (__int64 *)((char *)v2 + 8);
          p_Release = (struct IErrorInfoVtbl *)&lpVtbl->Release;
          if ( !v18 )
            p_Release = lpVtbl;
          lpVtbl = (struct IErrorInfoVtbl *)p_Release->QueryInterface;
        }
        while ( !*((_BYTE *)p_Release->QueryInterface + 25) );
      }
      if ( BYTE1(v17[3].lpVtbl) || (struct IErrorInfoVtbl *)v13 < v17[4].lpVtbl || v17 == v15 )
      {
        _com_error::_com_error((_com_error *)pExceptionObject, -2147024809, v15, v14);
        throw (_com_error *)pExceptionObject;
      }
      v20 = v17[6].lpVtbl;
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)&v20->AddRef);
      v21 = (std::_Ref_count_base *)v17[5].lpVtbl;
      v11 = (volatile signed __int32 *)v17[6].lpVtbl;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1792));
      v84[0] = v21;
      v84[1] = (std::_Ref_count_base *)v11;
      v10 = (_DWORD *)*((_QWORD *)v21 + 3);
      Src = v10;
    }
    else
    {
      Src = a1 + 1856;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1856));
      v22 = (__int64 *)*((_QWORD *)a1 + 237);
      v23 = (__int64 *)v22[1];
      v102 = 0;
      v24 = v22;
      if ( !*((_BYTE *)v23 + 25) )
      {
        do
        {
          v25 = v23[4] < (unsigned __int64)v13;
          if ( v23[4] >= (unsigned __int64)v13 )
            v24 = v23;
          v80 = (__int64 *)((char *)v2 + 8);
          v26 = v23 + 2;
          if ( !v25 )
            v26 = v23;
          v23 = (__int64 *)*v26;
        }
        while ( !*(_BYTE *)(*v26 + 25) );
      }
      if ( *((_BYTE *)v24 + 25) || (unsigned __int64)v13 < v24[4] || v24 == v22 )
      {
        _com_error::_com_error((_com_error *)v104, -2147024809, (struct IErrorInfo *)v23, (bool)v22);
        throw (_com_error *)v104;
      }
      v10 = (_DWORD *)v24[8];
      Src = v10;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1856));
      v11 = (volatile signed __int32 *)v84[1];
    }
    v2 = *(struct DXGIDDICB_PRESENT **)v79;
  }
  else
  {
    v9 = (__int64 *)((char *)v2 + 8);
    v80 = (__int64 *)((char *)v2 + 8);
    v10 = (_DWORD *)*((_QWORD *)v2 + 1);
    Src = v10;
    v11 = (volatile signed __int32 *)v84[1];
  }
  if ( (v10[22] & 0x8000) != 0 && v10[91] )
  {
    v27 = *((_QWORD *)a1 + 9);
    if ( *(_BYTE *)(v27 + 1112) > 9u
      || *(_BYTE *)(v27 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v27 + 1232) + 96LL) + 912LL)) >= 4u )
    {
      v28 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
      v29 = *v9;
      if ( v28 )
        NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken(a1 + 1792, v29);
      else
        NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken(a1 + 1856, v29);
    }
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
    return 0;
  }
  v31 = 0;
  memset_0(v135, 0, 0x200u);
  v134 = v81;
  v32 = (_QWORD *)((char *)v2 + 8 * *((unsigned int *)v2 + 6) + 32);
  v33 = v135;
  for ( i = (_QWORD *)((char *)v2 + 32); i != v32; ++i )
    *v33++ = *i;
  memset_0(v105, 0, 0x5D8u);
  memcpy_0(v105, Src, 0x5D8u);
  v37 = v107;
  if ( (v107 & 0x800000) != 0 )
  {
    memset_0(v124, 0, 0x128u);
    v122[0] = *((_DWORD *)v81 + 2);
    v39 = *(struct DXGIDDICB_PRESENT **)v79;
    v122[1] = **(_DWORD **)v79;
    v122[2] = v105[4];
    v40 = *(_DWORD *)(*(_QWORD *)v79 + 24LL);
    v123 = v40;
    if ( v40 > 0x40 )
    {
      v41 = *((_QWORD *)a1 + 9);
      if ( *(_BYTE *)(v41 + 1112) <= 9u
        && (*(_BYTE *)(v41 + 1112) != 9 || HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v41 + 1232) + 96LL) + 912LL)) < 4u) )
      {
        goto LABEL_131;
      }
      v42 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
      v43 = *v9;
      if ( !v42 )
        goto LABEL_130;
      goto LABEL_105;
    }
    v44 = 0;
    if ( v40 )
    {
      do
      {
        v124[v44] = *(_DWORD *)(*((_QWORD *)v39 + v44 + 4) + 8LL);
        v44 = (unsigned int)(v44 + 1);
        v39 = *(struct DXGIDDICB_PRESENT **)v79;
      }
      while ( (unsigned int)v44 < v123 );
    }
    if ( v115 )
    {
      v127 = *v115;
      v128 = v115[1];
    }
    v129 = v129 & 0xFFFFFFF4 | ((v37 & 0x3000000 | (v37 >> 1) & 0x8000000) >> 24);
    v45 = v130;
    if ( (v129 & 8) != 0 )
      v45 = v116;
    v130 = v45;
    v46 = *(_QWORD *)(*((_QWORD *)a1 + 12) + 472LL);
    if ( !v46 )
    {
      v51 = *((_QWORD *)a1 + 9);
      if ( *(_BYTE *)(v51 + 1112) > 9u
        || *(_BYTE *)(v51 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v51 + 1232) + 96LL) + 912LL)) >= 4u )
      {
        v52 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
        v53 = *v9;
        if ( v52 )
          NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken(a1 + 1792, v53);
        else
          NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken(a1 + 1856, v53);
      }
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v11)(v11, v38, v44);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v6)(v6, v38, v44);
          if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      return 2147500033LL;
    }
    v47 = CallAndLogImpl<long (*)(_D3DKMT_OUTPUTDUPLPRESENT const *),_D3DKMT_OUTPUTDUPLPRESENT *>(v46, v38, v122);
    goto LABEL_76;
  }
  v48 = 0;
  if ( v77 )
    goto LABEL_77;
  v105[0] = *((_DWORD *)a1 + 26);
  v54 = *(struct DXGIDDICB_PRESENT **)v79;
  v105[5] = **(_DWORD **)v79;
  v105[6] = *(_DWORD *)(*(_QWORD *)v79 + 4LL);
  if ( v81 )
    v105[0] = *((_DWORD *)v81 + 2);
  else
    v105[0] = 0;
  v55 = *(_DWORD *)(*(_QWORD *)v79 + 24LL);
  v108 = v55;
  if ( v55 > 0x40 )
  {
    v56 = *((_QWORD *)a1 + 9);
    if ( *(_BYTE *)(v56 + 1112) <= 9u
      && (*(_BYTE *)(v56 + 1112) != 9 || HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v56 + 1232) + 96LL) + 912LL)) < 4u) )
    {
      goto LABEL_131;
    }
    v57 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
    v43 = *v80;
    if ( !v57 )
    {
LABEL_130:
      NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken(a1 + 1856, v43);
LABEL_131:
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      return 2147942487LL;
    }
LABEL_105:
    NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken(a1 + 1792, v43);
    goto LABEL_131;
  }
  v58 = 0;
  if ( v55 )
  {
    do
    {
      v35 = (unsigned int)v58;
      v109[(unsigned int)v58] = *(_DWORD *)(*((_QWORD *)v54 + (unsigned int)v58 + 4) + 8LL);
      v58 = (unsigned int)(v58 + 1);
    }
    while ( (unsigned int)v58 < v108 );
    v37 = v107;
  }
  v120 = *((_QWORD *)v54 + 71);
  v119 = *((_DWORD *)v54 + 140);
  v117 = *((_QWORD *)v54 + 68);
  v118 = *((_QWORD *)v54 + 69);
  if ( (v37 & 4) != 0 || (v37 & 0x8000) != 0 )
  {
    v37 &= ~0x2000u;
    v107 = v37;
  }
  if ( !*((_DWORD *)v54 + 145) )
    goto LABEL_212;
  v35 = *((int *)v54 + 146);
  switch ( (int)v35 )
  {
    case 0:
    case 1:
    case 2:
    case 3:
    case 4:
      v58 = (unsigned int)v35;
      break;
    case 5:
      v58 = 0;
      break;
    default:
      CModule::RecordJournal(
        (CModule *)&g_Module,
        0x80070057,
        "Driver set invalid sync interval override.",
        (bool)v54,
        1);
      v61 = *((_QWORD *)a1 + 9);
      if ( *(_BYTE *)(v61 + 1112) <= 9u
        && (*(_BYTE *)(v61 + 1112) != 9 || HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 1232) + 96LL) + 912LL)) < 4u) )
      {
        goto LABEL_131;
      }
      v62 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
      v43 = *v80;
      if ( !v62 )
        goto LABEL_130;
      goto LABEL_105;
  }
  if ( (v37 & 4) != 0 )
  {
    v59 = v106;
    if ( (v37 & 0x8000000) == 0 )
      v59 = v58;
    v106 = v59;
  }
  if ( (v37 & 0x8000) != 0 && v110 == 2 )
  {
    if ( (v114 & 0x80000) == 0 )
    {
      v113 = v58;
      v60 = 0;
      if ( (_DWORD)v35 == 5 )
        v60 = 0x800000;
      v114 = v114 & 0xFF7FFFFF | v60;
    }
  }
  else
  {
LABEL_212:
    if ( v110 == -1 )
    {
      v110 = 0;
      v63 = v111;
      if ( v111 )
      {
        memcpy_0(v122, v105, 0x5D8u);
        v124[1] = 0;
        v125 = &v112;
        v124[12] = v63;
        v126 = v126 & 0xFFBFEF38 | 2;
        v131 = 0;
        if ( *(_BYTE *)(*((_QWORD *)a1 + 9) + 1136LL) )
          (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)a1 + 260) + 32LL))(*((_QWORD *)a1 + 260), v122);
        else
          CallAndLogImpl<long (*)(_D3DKMT_PRESENT *),_D3DKMT_PRESENT *>(
            *(_QWORD *)(*((_QWORD *)a1 + 12) + 240LL),
            v64,
            v122);
      }
    }
  }
  if ( *(_BYTE *)(*((_QWORD *)a1 + 9) + 1136LL) )
  {
    v48 = 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, __int64))(**((_QWORD **)a1 + 260) + 32LL))(
            *((_QWORD *)a1 + 260),
            v105,
            v58);
    goto LABEL_77;
  }
  if ( (_BYTE)v82 )
  {
    v90[0] = 0;
    v90[1] = 0;
    v91 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96[0] = 0;
    v96[1] = 0;
    v97 = 0;
    v98 = 0;
    v100 = 0;
    v101 = 0;
    memset(v132, 0, sizeof(v132));
    v133 = 0;
    v81 = v96;
    v99 = v132;
    v92 = &v81;
    NDXGI::CDevice::ConvertPresentArgToPresentMPO3(
      (const struct _D3DKMT_PRESENT *)v105,
      (const struct NDXGI::CDevice::DDisplayPrivateData *)&v82,
      *(_DWORD *)(*((_QWORD *)a1 + 12) + 96LL),
      (struct _D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 *)v90);
    v47 = CallAndLogImpl<long (*)(_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT const *),_D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *>(
            D3DKMTPresentMultiPlaneOverlay3,
            "PresentMultiplaneOverlay3",
            v90);
LABEL_76:
    v48 = v47;
LABEL_77:
    v49 = *(struct DXGIDDICB_PRESENT **)v79;
    goto LABEL_78;
  }
  v48 = CallAndLogImpl<long (*)(_D3DKMT_PRESENT *),_D3DKMT_PRESENT *>(
          *(_QWORD *)(*((_QWORD *)a1 + 12) + 240LL),
          v35,
          v105);
  v49 = *(struct DXGIDDICB_PRESENT **)v79;
  *(_BYTE *)(*(_QWORD *)v79 + 576LL) = v121;
LABEL_78:
  v50 = *((_QWORD *)a1 + 9);
  if ( *(_BYTE *)(v50 + 1136) )
  {
    if ( v31 == -2005270523 )
      (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)a1 + 2) + 264LL))(a1 + 16, 2289696773LL);
    goto LABEL_159;
  }
  v65 = *(_BYTE *)(v50 + 1112) > 8u
     || *(_BYTE *)(v50 + 1112) == 8 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v50 + 1232) + 96LL) + 912LL));
  if ( v48 > -1071775744 )
  {
    if ( v48 <= -1071775720 )
    {
      if ( v48 != -1071775720 )
      {
        switch ( v48 )
        {
          case -1071775739:
          case -1071775738:
          case -1071775737:
            goto LABEL_157;
          case -1071775733:
          case -1071775730:
          case -1071775729:
            goto LABEL_168;
          case -1071775731:
            v48 = 0;
            v31 = *((int *)a1 + 312) < 0 ? 0x88760870 : 0;
            break;
          case -1071775728:
            if ( v65 )
              goto LABEL_168;
            goto LABEL_171;
          default:
            goto LABEL_171;
        }
        goto LABEL_159;
      }
      goto LABEL_157;
    }
    if ( v48 == -1071774910 )
    {
LABEL_157:
      v31 = 0;
      if ( *((int *)a1 + 312) < 0 )
        v31 = -2005530512;
      goto LABEL_159;
    }
    if ( v48 == 259 )
    {
LABEL_168:
      v31 = 0;
      goto LABEL_159;
    }
  }
  else if ( v48 == -1071775744 )
  {
    goto LABEL_157;
  }
LABEL_171:
  v31 = NDXGI::CDevice::NTStatusToHResult((NDXGI::CDevice *)a1, v48);
LABEL_159:
  if ( v86 )
  {
    v36 = v87;
    if ( v87 )
    {
      if ( *((_DWORD *)v49 + 6) <= 0x40u )
      {
        v66 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD))(*(_QWORD *)a1 + 312LL))(a1, *(_QWORD *)v86, v86[4]);
        if ( v66 < 0 )
        {
          v31 = v66;
          v48 = -1073741823;
        }
      }
      else
      {
        v31 = -2147024809;
        v48 = -1073741811;
      }
    }
  }
  if ( a1[898] )
  {
    v67 = (signed int *)*((_QWORD *)a1 + 176);
    if ( v67 )
    {
      *v67 = v31;
      v67[1] = v48;
    }
  }
  else
  {
    AcquireSRWLockShared((PSRWLOCK)a1 + 167);
    LODWORD(Src) = GetCurrentThreadId();
    v68 = (__int64 *)(16 * (*((_QWORD *)a1 + 174) & std::_Hash_representation<unsigned long>(&Src))
                    + *((_QWORD *)a1 + 171));
    v70 = v68[1];
    v71 = *((_QWORD *)a1 + 169);
    if ( v70 == v71 )
    {
LABEL_182:
      v70 = 0;
    }
    else
    {
      v72 = *v68;
      while ( v69 != *(_DWORD *)(v70 + 16) )
      {
        if ( v70 == v72 )
          goto LABEL_182;
        v70 = *(_QWORD *)(v70 + 8);
      }
    }
    if ( v70 && v70 != v71 )
    {
      v73 = *(signed int **)(v70 + 24);
      *v73 = v31;
      v73[1] = v48;
    }
    if ( a1 != (char *)-1336LL )
      ReleaseSRWLockShared((PSRWLOCK)a1 + 167);
  }
  if ( v31 == -2005532132 || v31 == -2005530512 )
  {
    v31 = 0;
  }
  else if ( v31 < 0 )
  {
    CModule::RecordJournal((CModule *)&g_Module, v31, "PresentCB", v36, 1);
  }
  v74 = *((_QWORD *)a1 + 9);
  if ( *(_BYTE *)(v74 + 1112) > 9u
    || *(_BYTE *)(v74 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v74 + 1232) + 96LL) + 912LL)) >= 4u )
  {
    v75 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
    v76 = *v80;
    if ( v75 )
      NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken(a1 + 1792, v76);
    else
      NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken(a1 + 1856, v76);
  }
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x18006dd10  mov     [rsp+arg_10], rbx
0x18006dd15  mov     [rsp+arg_18], rsi
0x18006dd1a  push    rdi
0x18006dd1b  push    r12
0x18006dd1d  push    r13
0x18006dd1f  push    r14
0x18006dd21  push    r15
0x18006dd23  mov     eax, 1000h
0x18006dd28  call    _alloca_probe
0x18006dd2d  sub     rsp, rax
0x18006dd30  mov     rax, cs:__security_cookie
0x18006dd37  xor     rax, rsp
0x18006dd3a  mov     [rsp+1028h+var_38], rax
0x18006dd42  mov     rbx, rdx
0x18006dd45  mov     qword ptr [rsp+1028h+var_FD8], rdx
0x18006dd4a  mov     r12, rcx
0x18006dd4d  xor     edi, edi
0x18006dd4f  mov     rax, [rdx+10h]
0x18006dd53  mov     [rsp+1028h+var_FC8], rax
0x18006dd58  xorps   xmm0, xmm0
0x18006dd5b  movdqu  xmmword ptr [rsp+1028h+var_FA0], xmm0
0x18006dd64  mov     rcx, [rcx+48h]
0x18006dd68  cmp     byte ptr [rcx+458h], 8
0x18006dd6f  ja      loc_18006DE5B
0x18006dd75  jnz     short loc_18006DD96
0x18006dd77  mov     rax, [rcx+4D0h]
0x18006dd7e  mov     rcx, [rax+60h]
0x18006dd82  mov     eax, [rcx+390h]
0x18006dd88  shr     rax, 10h
0x18006dd8c  cmp     ax, 1
0x18006dd90  jnb     loc_18006DE5B
0x18006dd96  mov     rax, [r12+7F0h]
0x18006dd9e  test    rax, rax
0x18006dda1  jz      short loc_18006DDA7
0x18006dda3  lock inc dword ptr [rax+8]
0x18006dda7  mov     rcx, [r12+7E8h]
0x18006ddaf  mov     [rsp+1028h+var_F90], rcx
0x18006ddb7  mov     [rsp+1028h+var_FA0], rcx
0x18006ddbf  mov     r14, [r12+7F0h]
0x18006ddc7  mov     [rsp+1028h+var_FA0+8], r14
0x18006ddcf  mov     rcx, [r12+7F8h]
0x18006ddd7  mov     [rsp+1028h+var_F88], rcx
0x18006dddf  movzx   eax, byte ptr [r12+800h]
0x18006dde8  mov     [rsp+1028h+var_FE8], al
0x18006ddec  mov     [r12+7E8h], rdi
0x18006ddf4  mov     rbx, r14
0x18006ddf7  mov     [r12+7F0h], rdi
0x18006ddff  mov     r15d, 0FFFFFFFFh
0x18006de05  test    r14, r14
0x18006de08  jz      short loc_18006DE43
0x18006de0a  mov     eax, r15d
0x18006de0d  lock xadd [r14+8], eax
0x18006de13  cmp     eax, 1
0x18006de16  jnz     short loc_18006DE43
0x18006de18  mov     rax, [r14]
0x18006de1b  mov     rcx, rbx
0x18006de1e  mov     rax, [rax]
0x18006de21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de26  mov     eax, r15d
0x18006de29  lock xadd [r14+0Ch], eax
0x18006de2f  cmp     eax, 1
0x18006de32  jnz     short loc_18006DE43
0x18006de34  mov     rax, [r14]
0x18006de37  mov     rcx, rbx
0x18006de3a  mov     rax, [rax+8]
0x18006de3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de43  mov     [r12+7F8h], rdi
0x18006de4b  mov     byte ptr [r12+800h], 0
0x18006de54  mov     rbx, qword ptr [rsp+1028h+var_FD8]
0x18006de59  jmp     short loc_18006DE86
0x18006de5b  mov     [rsp+1028h+var_F88], rdi
0x18006de63  mov     [rsp+1028h+var_FE8], 0
0x18006de68  mov     r15d, 0FFFFFFFFh
0x18006de6e  mov     r14, [rsp+1028h+var_FA0+8]
0x18006de76  mov     rax, [rsp+1028h+var_FA0]
0x18006de7e  mov     [rsp+1028h+var_F90], rax
0x18006de86  xor     ecx, ecx
0x18006de88  mov     [rsp+1028h+var_FC0], rcx
0x18006de8d  mov     [rsp+1028h+var_FB8], ecx
0x18006de91  cmp     [r12+804h], cl
0x18006de99  jz      short loc_18006DECF
0x18006de9b  movsd   xmm1, [rsp+1028h+var_FC0]
0x18006dea1  movsd   xmm0, qword ptr [r12+804h]
0x18006deab  movsd   [rsp+1028h+var_FC0], xmm0
0x18006deb1  mov     eax, [r12+80Ch]
0x18006deb9  mov     [rsp+1028h+var_FB8], eax
0x18006debd  movsd   qword ptr [r12+804h], xmm1
0x18006dec7  mov     [r12+80Ch], ecx
0x18006decf  xorps   xmm0, xmm0
0x18006ded2  movdqu  xmmword ptr [rsp+1028h+var_FB0], xmm0
0x18006ded8  mov     [rsp+1028h+var_F80], r12
0x18006dee0  mov     [rsp+1028h+var_F78], rbx
0x18006dee8  mov     rcx, [r12+48h]
0x18006deed  cmp     byte ptr [rcx+458h], 9
0x18006def4  ja      short loc_18006DF32
0x18006def6  jnz     short loc_18006DF13
0x18006def8  mov     rax, [rcx+4D0h]
0x18006deff  mov     rcx, [rax+60h]
0x18006df03  mov     eax, [rcx+390h]
0x18006df09  shr     rax, 10h
0x18006df0d  cmp     ax, 4
0x18006df11  jnb     short loc_18006DF32
0x18006df13  lea     r13, [rbx+8]
0x18006df17  mov     [rsp+1028h+var_FD0], r13
0x18006df1c  mov     rdi, [r13+0]
0x18006df20  mov     [rsp+1028h+Src], rdi
0x18006df25  mov     rsi, [rsp+1028h+var_FB0+8]
0x18006df2d  jmp     loc_18006E08B
0x18006df32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl(void)'::`2'::impl
0x18006df39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(void)
0x18006df3e  lea     r13, [rbx+8]
0x18006df42  mov     [rsp+1028h+var_FD0], r13
0x18006df47  mov     rdi, [r13+0]
0x18006df4b  test    al, al
0x18006df4d  jz      loc_18006DFF7
0x18006df53  lea     rbx, [r12+700h]
0x18006df5b  mov     [rsp+1028h+Src], rbx
0x18006df60  mov     rcx, rbx; lpCriticalSection
0x18006df63  call    cs:__imp_EnterCriticalSection
0x18006df69  nop
0x18006df6a  mov     r8, [rbx+28h]; struct IErrorInfo *
0x18006df6e  mov     rdx, [r8+8]
0x18006df72  xor     eax, eax
0x18006df74  mov     [rsp+1028h+var_EBC], eax
0x18006df7b  mov     rsi, r8
0x18006df7e  cmp     [rdx+19h], al
0x18006df81  jnz     short loc_18006DFA1
0x18006df83  cmp     [rdx+20h], rdi
0x18006df87  cmovnb  rsi, rdx
0x18006df8b  mov     [rsp+1028h+var_FD0], r13
0x18006df90  lea     rax, [rdx+10h]
0x18006df94  cmovnb  rax, rdx
0x18006df98  mov     rdx, [rax]
0x18006df9b  cmp     byte ptr [rdx+19h], 0
0x18006df9f  jz      short loc_18006DF83
0x18006dfa1  cmp     byte ptr [rsi+19h], 0
0x18006dfa5  jnz     loc_18006ED67
0x18006dfab  cmp     rdi, [rsi+20h]
0x18006dfaf  jb      loc_18006ED67
0x18006dfb5  cmp     rsi, r8
0x18006dfb8  jz      loc_18006ED67
0x18006dfbe  mov     rax, [rsi+30h]
0x18006dfc2  test    rax, rax
0x18006dfc5  jz      short loc_18006DFCB
0x18006dfc7  lock inc dword ptr [rax+8]
0x18006dfcb  mov     rdi, [rsi+28h]
0x18006dfcf  mov     rsi, [rsi+30h]
0x18006dfd3  mov     rcx, rbx; lpCriticalSection
0x18006dfd6  call    cs:__imp_LeaveCriticalSection
0x18006dfdc  mov     [rsp+1028h+var_FB0], rdi
0x18006dfe1  mov     [rsp+1028h+var_FB0+8], rsi
0x18006dfe9  mov     rdi, [rdi+18h]
0x18006dfed  mov     [rsp+1028h+Src], rdi
0x18006dff2  jmp     loc_18006E086
0x18006dff7  lea     rbx, [r12+740h]
0x18006dfff  mov     [rsp+1028h+Src], rbx
0x18006e004  mov     rcx, rbx; lpCriticalSection
0x18006e007  call    cs:__imp_EnterCriticalSection
0x18006e00d  nop
0x18006e00e  mov     r9, [rbx+28h]; bool
0x18006e012  mov     r8, [r9+8]
0x18006e016  xor     eax, eax
0x18006e018  mov     [rsp+1028h+var_EBC], eax
0x18006e01f  mov     rdx, r9
0x18006e022  cmp     [r8+19h], al
0x18006e026  jnz     short loc_18006E04F
0x18006e028  nop     dword ptr [rax+rax+00000000h]
0x18006e030  cmp     [r8+20h], rdi
0x18006e034  cmovnb  rdx, r8
0x18006e038  mov     [rsp+1028h+var_FD0], r13
0x18006e03d  lea     rax, [r8+10h]
0x18006e041  cmovnb  rax, r8
0x18006e045  mov     r8, [rax]; struct IErrorInfo *
0x18006e048  cmp     byte ptr [r8+19h], 0
0x18006e04d  jz      short loc_18006E030
0x18006e04f  cmp     byte ptr [rdx+19h], 0
0x18006e053  jnz     loc_18006ED8E
0x18006e059  cmp     rdi, [rdx+20h]
0x18006e05d  jb      loc_18006ED8E
0x18006e063  cmp     rdx, r9
0x18006e066  jz      loc_18006ED8E
0x18006e06c  mov     rdi, [rdx+40h]
0x18006e070  mov     [rsp+1028h+Src], rdi
0x18006e075  mov     rcx, rbx; lpCriticalSection
0x18006e078  call    cs:__imp_LeaveCriticalSection
0x18006e07e  mov     rsi, [rsp+1028h+var_FB0+8]
0x18006e086  mov     rbx, qword ptr [rsp+1028h+var_FD8]
0x18006e08b  test    dword ptr [rdi+58h], 8000h
0x18006e092  jz      loc_18006E182
0x18006e098  cmp     dword ptr [rdi+16Ch], 0
0x18006e09f  jz      loc_18006E182
0x18006e0a5  mov     rdx, [r12+48h]
0x18006e0aa  cmp     byte ptr [rdx+458h], 9
0x18006e0b1  ja      short loc_18006E0D1
0x18006e0b3  jnz     short loc_18006E102
0x18006e0b5  mov     rax, [rdx+4D0h]
0x18006e0bc  mov     r8, [rax+60h]
0x18006e0c0  mov     eax, [r8+390h]
0x18006e0c7  shr     rax, 10h
0x18006e0cb  cmp     ax, 4
0x18006e0cf  jb      short loc_18006E102
0x18006e0d1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl(void)'::`2'::impl
0x18006e0d8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(void)
0x18006e0dd  mov     rdx, [r13+0]
0x18006e0e1  test    al, al
0x18006e0e3  jz      short loc_18006E0F4
0x18006e0e5  lea     rcx, [r12+700h]
0x18006e0ed  call    ?FreeToken@?$OpaqueHandleManager@V?$shared_ptr@UBatchablePresent@@@std@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken(void *)
0x18006e0f2  jmp     short loc_18006E102
0x18006e0f4  lea     rcx, [r12+740h]
0x18006e0fc  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresent@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken(void *)
0x18006e101  nop
0x18006e102  test    rsi, rsi
0x18006e105  jz      short loc_18006E13F
0x18006e107  mov     eax, r15d
0x18006e10a  lock xadd [rsi+8], eax
0x18006e10f  cmp     eax, 1
0x18006e112  jnz     short loc_18006E13F
0x18006e114  mov     rax, [rsi]
0x18006e117  mov     rcx, rsi
0x18006e11a  mov     rax, [rax]
0x18006e11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e122  mov     eax, r15d
0x18006e125  lock xadd [rsi+0Ch], eax
0x18006e12a  cmp     eax, 1
0x18006e12d  jnz     short loc_18006E13F
0x18006e12f  mov     rax, [rsi]
0x18006e132  mov     rcx, rsi
0x18006e135  mov     rax, [rax+8]
0x18006e139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e13e  nop
0x18006e13f  test    r14, r14
0x18006e142  jz      short loc_18006E17B
0x18006e144  mov     eax, r15d
0x18006e147  lock xadd [r14+8], eax
0x18006e14d  cmp     eax, 1
0x18006e150  jnz     short loc_18006E17B
0x18006e152  mov     rax, [r14]
0x18006e155  mov     rcx, r14
0x18006e158  mov     rax, [rax]
0x18006e15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e160  lock xadd [r14+0Ch], r15d
0x18006e166  cmp     r15d, 1
0x18006e16a  jnz     short loc_18006E17B
0x18006e16c  mov     rax, [r14]
0x18006e16f  mov     rcx, r14
0x18006e172  mov     rax, [rax+8]
0x18006e176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e17b  xor     eax, eax
0x18006e17d  jmp     loc_18006ED3A
0x18006e182  xor     edi, edi
0x18006e184  xor     edx, edx; Val
0x18006e186  mov     r8d, 200h; Size
0x18006e18c  lea     rcx, [rsp+1028h+var_240]; void *
0x18006e194  call    memset_0
0x18006e199  mov     rax, [rsp+1028h+var_FC8]
0x18006e19e  mov     [rsp+1028h+var_248], rax
0x18006e1a6  mov     edx, [rbx+18h]
0x18006e1a9  add     rdx, 4
0x18006e1ad  lea     rdx, [rbx+rdx*8]
0x18006e1b1  lea     r8, [rsp+1028h+var_240]
0x18006e1b9  lea     rcx, [rbx+20h]
0x18006e1bd  cmp     rcx, rdx
0x18006e1c0  jz      short loc_18006E1D5
0x18006e1c2  mov     rax, [rcx]
0x18006e1c5  mov     [r8], rax
0x18006e1c8  lea     r8, [r8+8]
0x18006e1cc  add     rcx, 8
0x18006e1d0  cmp     rcx, rdx
0x18006e1d3  jnz     short loc_18006E1C2
0x18006e1d5  xor     edx, edx; Val
0x18006e1d7  mov     r8d, 5D8h; Size
0x18006e1dd  lea     rcx, [rsp+1028h+var_E68]; void *
0x18006e1e5  call    memset_0
0x18006e1ea  lea     rcx, [rsp+1028h+var_E68]; void *
0x18006e1f2  mov     rdx, [rsp+1028h+Src]; Src
0x18006e1f7  mov     r8d, 5D8h; Size
0x18006e1fd  call    memcpy_0
0x18006e202  mov     ebx, [rsp+1028h+var_E10]
0x18006e209  mov     r11d, 800000h
0x18006e20f  test    r11d, ebx
0x18006e212  jz      loc_18006E49F
0x18006e218  xor     edx, edx; Val
0x18006e21a  mov     r8d, 128h; Size
0x18006e220  lea     rcx, [rsp+1028h+var_878]; void *
0x18006e228  call    memset_0
0x18006e22d  mov     rcx, [rsp+1028h+var_FC8]
0x18006e232  mov     eax, [rcx+8]
0x18006e235  mov     [rsp+1028h+var_888], eax
0x18006e23c  mov     rcx, qword ptr [rsp+1028h+var_FD8]
0x18006e241  mov     eax, [rcx]
0x18006e243  mov     [rsp+1028h+var_884], eax
0x18006e24a  mov     eax, [rsp+1028h+var_E58]
0x18006e251  mov     [rsp+1028h+var_880], eax
0x18006e258  mov     eax, [rcx+18h]
0x18006e25b  mov     [rsp+1028h+var_87C], eax
0x18006e262  cmp     eax, 40h ; '@'
0x18006e265  jbe     short loc_18006E2C8
0x18006e267  mov     rcx, [r12+48h]
0x18006e26c  cmp     byte ptr [rcx+458h], 9
  ... truncated ...
```
