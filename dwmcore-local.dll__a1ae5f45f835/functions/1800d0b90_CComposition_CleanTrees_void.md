# CComposition::CleanTrees(void)

- ea: `0x1800d0b90`
- end: `0x1800d1a16`
- name: `?CleanTrees@CComposition@@IEAAJXZ`
- size: `3718`
- prototype: `__int64 __fastcall(CComposition *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18012fe64`

## callees

- `0x1800276d0`
- `0x18004fce4`
- `0x180050270`
- `0x1800d0b90`
- `0x1800d1a1c`
- `0x1800d1c80`
- `0x1800d1df8`
- `0x1800d22a4`
- `0x1800d2354`
- `0x1800d26a8`
- `0x1800d2730`
- `0x1800d3010`
- `0x1800ee220`
- `0x1800ee790`
- `0x1800fa6bc`
- `0x1800fa708`
- `0x1800fa918`
- `0x18012971c`
- `0x180131dc0`
- `0x180189c98`
- `0x1801dc948`
- `0x1802005d0`
- `0x180204ab8`
- `0x18021a968`
- `0x18021c704`
- `0x1802284b0`
- `0x180228880`
- `0x18022945c`
- `0x1802314a0`
- `0x180231698`
- `0x180238bcc`
- `0x1802b6010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800d0ce8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800d0ce8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0be7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0be7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d1136`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d1136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d1173`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d1173`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d1860`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d1870`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d1860`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d1870`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800d1181`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800d1181`

## string_xrefs

- `0x1800d14b3`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall CComposition::CleanTrees(struct _RTL_CRITICAL_SECTION *this, __int64 a2, __int64 a3)
{
  int v3; // r15d
  __int64 *v5; // rdx
  CComposition *v6; // r10
  const struct CVisualTree **v7; // rbx
  const struct CVisualTree **v8; // rcx
  __int64 *v9; // r14
  __int64 *v10; // rsi
  unsigned __int64 v11; // r13
  _QWORD *v12; // r9
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  _DWORD *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 *v18; // r15
  const struct CVisualTree **v19; // rbx
  const struct CVisualTree **v20; // rdi
  _BYTE *v21; // r12
  unsigned __int64 v22; // r14
  const struct CVisualTree *v23; // r13
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // r13d
  struct _RTL_CRITICAL_SECTION *v27; // r12
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  struct _RTL_CRITICAL_SECTION_DEBUG *v29; // rsi
  __int64 v30; // r12
  __int64 v31; // r14
  __int64 v32; // r9
  _DWORD *v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 *v36; // rdx
  __int64 v37; // rdx
  int v38; // r15d
  __int64 v39; // rcx
  __int64 v40; // rax
  char v41; // cl
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // rdx
  bool v48; // zf
  __int64 v49; // rax
  struct _RTL_CRITICAL_SECTION *v50; // r12
  ULONG_PTR *p_SpinCount; // rbx
  _QWORD *v52; // rax
  _QWORD *v53; // r8
  _QWORD *k; // rcx
  _QWORD *v55; // r9
  char *v56; // rdx
  PRTL_CRITICAL_SECTION_DEBUG v57; // rcx
  const char *v58; // r9
  unsigned __int64 v59; // rcx
  HANDLE CurrentThread; // rax
  BOOL v61; // eax
  HANDLE ProcessHeap; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  char v66; // cl
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  int v74; // r14d
  __int64 v75; // rax
  CPreComputeContext *v76; // rbx
  CPreComputeContext *v77; // rax
  int v78; // eax
  __int64 v79; // rax
  CPreComputeContext *v80; // rbx
  CPreComputeContext *v81; // rax
  int v82; // eax
  __int64 v83; // rcx
  unsigned int v84; // r8d
  unsigned int i; // edx
  _BYTE *v86; // rax
  CPreComputeContext *v87; // rax
  CPreComputeContext *v88; // rbx
  __int64 v89; // rax
  unsigned int v90; // r8d
  unsigned int j; // edx
  CPreComputeContext *v92; // rax
  CPreComputeContext *v93; // rbx
  __int64 v94; // rcx
  CLight **v95; // rdi
  CLight **v96; // rbx
  __int64 v97; // r10
  _QWORD *n; // rax
  __int64 ProjectedShadowCasters; // rax
  CProjectedShadowCaster **v100; // r14
  CProjectedShadowCaster **v101; // r15
  const struct D2D_RECT_F *UnoptimizedBounds; // rax
  const struct D2D_RECT_F *v103; // rax
  _QWORD *m; // rdx
  unsigned int v105; // edi
  __int64 v106; // rcx
  __int64 v107; // rax
  unsigned int ii; // esi
  _OWORD *v109; // rax
  __int64 v110; // rbx
  int v111; // [rsp+20h] [rbp-E0h]
  unsigned __int64 CycleTime; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v113; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION *v114; // [rsp+50h] [rbp-B0h]
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-A8h] BYREF
  LARGE_INTEGER v116; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v117[3]; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v118; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v119[7]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v120; // [rsp+C8h] [rbp-38h]
  const struct CVisualTree **v121; // [rsp+D0h] [rbp-30h] BYREF
  const struct CVisualTree **v122; // [rsp+D8h] [rbp-28h]
  _QWORD *v123; // [rsp+E0h] [rbp-20h]
  _BYTE Mem[64]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v125[3]; // [rsp+128h] [rbp+28h] BYREF
  _OWORD v126[8]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v3 = 0;
  v114 = this;
  PerformanceCount.QuadPart = 0;
  v116.QuadPart = 0;
  if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 4) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(Microsoft_Windows_Dwm_Compositor_Context, CleanTrees_Start, a3, 1, v125);
    QueryPerformanceCounter(&PerformanceCount);
  }
  EnterCriticalSection(this + 9);
  if ( PerformanceCount.QuadPart )
    QueryPerformanceCounter(&v116);
  v6 = g_pComposition;
  v7 = (const struct CVisualTree **)Mem;
  v8 = (const struct CVisualTree **)Mem;
  v121 = (const struct CVisualTree **)Mem;
  v122 = (const struct CVisualTree **)Mem;
  v123 = v125;
  v9 = (__int64 *)*((_QWORD *)g_pComposition + 775);
  v118 = v9;
  v10 = (__int64 *)*v9;
LABEL_6:
  if ( v10 != v9 )
  {
    v11 = v10[2];
    v12 = v119;
    v119[0] = off_1802B9F98;
    v13 = v11;
    CycleTime = v11;
    v119[1] = &v121;
    v14 = v11;
    v120 = v119;
    while ( 1 )
    {
      if ( !v13 )
      {
LABEL_23:
        if ( v12 )
        {
          LOBYTE(v5) = v12 != v119;
          (*(void (__fastcall **)(_QWORD *, __int64 *))(*v12 + 32LL))(v12, v5);
          v120 = 0;
        }
        *((_BYTE *)v10 + 51) = 0;
        v113 = 0;
        v18 = v10 + 3;
        if ( g_pComposition )
          v113 = *((_QWORD *)g_pComposition + 110);
        v19 = v121;
        v20 = v122;
        v21 = (char *)v10 + 50;
        v22 = v113;
        v125[0] = (char *)v10 + 50;
        while ( v19 != v20 )
        {
          v23 = *v19;
          CPreWalkVisual::CalcTransform((CPreWalkVisual *)v18, (struct CVisual *)CycleTime, *v19, v22);
          if ( *((_BYTE *)v18 + 24) )
            CPreWalkVisual::DirtyBoundsForTransformParentChild((struct CVisual *)CycleTime, v23);
          v21 = (char *)v18 + 26;
          if ( *((_BYTE *)v18 + 26) )
          {
            ProjectedShadowCasters = CVisual::GetProjectedShadowCasters(CycleTime);
            v5 = *(__int64 **)(ProjectedShadowCasters + 8);
            if ( *(__int64 **)ProjectedShadowCasters != v5 )
            {
              v100 = *(CProjectedShadowCaster ***)ProjectedShadowCasters;
              v101 = *(CProjectedShadowCaster ***)(ProjectedShadowCasters + 8);
              do
                CProjectedShadowCaster::UpdateVisualProperty(*v100++, v23);
              while ( v100 != v101 );
              v22 = v113;
              v18 = v10 + 3;
            }
          }
          ++v19;
        }
        v9 = v118;
        if ( *((_BYTE *)v18 + 27) )
        {
          if ( *((_BYTE *)v18 + 25) )
          {
            v95 = (CLight **)v18[1];
            v96 = (CLight **)*v18;
            if ( (CLight **)*v18 == v95 )
            {
              v86 = (_BYTE *)v125[0];
            }
            else
            {
              do
                CLight::IssueLightChangedNotification(*v96++);
              while ( v96 != v95 );
              v86 = (char *)v18 + 26;
            }
          }
          else
          {
            v86 = v21;
          }
          if ( *v86 )
            CVisual::DirtyProjectedShadowCasters((CVisual *)CycleTime);
        }
        v8 = v122;
        v7 = v121;
        v24 = v122 - v121;
        if ( v24 )
        {
          v8 = &v122[-v24];
          v122 = v8;
        }
        v10 = (__int64 *)*v10;
        v3 = 0;
        v6 = g_pComposition;
        goto LABEL_6;
      }
      v15 = *(_DWORD **)(v13 + 224);
      if ( (*v15 & 0x8000000) != 0 )
        break;
LABEL_16:
      if ( v14 )
      {
        v14 = *(_QWORD *)(v14 + 88);
        if ( v14 )
        {
          if ( v13 == v14 )
            goto LABEL_23;
          v14 = *(_QWORD *)(v14 + 88);
          if ( v13 == v14 )
            goto LABEL_23;
        }
      }
      v13 = *(_QWORD *)(v13 + 88);
    }
    v16 = (unsigned int)v15[1];
    v17 = 0;
    if ( (_DWORD)v16 )
    {
      while ( *((_BYTE *)v15 + v17 + 8) != 5 )
      {
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= (unsigned int)v16 )
          goto LABEL_21;
      }
    }
    else
    {
LABEL_21:
      if ( (unsigned int)v17 >= (unsigned int)v16 )
      {
        v5 = 0;
LABEL_13:
        if ( *v5 )
        {
          v117[0] = *v5;
          if ( !v12 )
          {
            std::_Xbad_function_call();
            __debugbreak();
          }
          (*(void (__fastcall **)(_QWORD *, __int64 *))(*v12 + 16LL))(v12, v117);
          v12 = v120;
        }
        goto LABEL_16;
      }
    }
    v5 = (__int64 *)((char *)v15 + v16 + 8 * v17 - (((_BYTE)v16 + 15) & 7) + 15);
    goto LABEL_13;
  }
  LODWORD(v113) = 0;
  v25 = v8 - v7;
  v26 = 0;
  if ( v25 )
    v122 = &v8[-v25];
  v121 = 0;
  if ( v7 != (const struct CVisualTree **)Mem && v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
    v6 = g_pComposition;
  }
  v27 = v114;
  LOBYTE(v114[141].OwningThread) = 1;
  DebugInfo = v27[10].DebugInfo;
  v29 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&v27[10].LockCount;
  while ( DebugInfo != v29 )
  {
    v30 = *(_QWORD *)&DebugInfo->Type;
    v31 = *(_QWORD *)&DebugInfo->Type;
    v32 = *(_QWORD *)(*(_QWORD *)&DebugInfo->Type + 72LL);
    if ( v32 )
    {
      while ( 1 )
      {
        v33 = *(_DWORD **)(v32 + 224);
        if ( (*v33 & 0x8000000) != 0 )
          break;
LABEL_54:
        v32 = *(_QWORD *)(v32 + 88);
        if ( !v32 )
          goto LABEL_55;
      }
      v34 = (unsigned int)v33[1];
      v35 = 0;
      if ( (_DWORD)v34 )
      {
        while ( *((_BYTE *)v33 + v35 + 8) != 5 )
        {
          v35 = (unsigned int)(v35 + 1);
          if ( (unsigned int)v35 >= (unsigned int)v34 )
            goto LABEL_101;
        }
LABEL_51:
        v36 = (__int64 *)((char *)v33 + v34 + 8 * v35 - (((_BYTE)v34 + 15) & 7) + 15);
      }
      else
      {
LABEL_101:
        if ( (unsigned int)v35 < (unsigned int)v34 )
          goto LABEL_51;
        v36 = 0;
      }
      if ( *v36 )
        v31 = *v36;
      goto LABEL_54;
    }
LABEL_55:
    v37 = *(_QWORD *)(v31 + 72);
    if ( v37 && *(_BYTE *)(v37 + 96) )
      LODWORD(v113) = v3 + 1;
    v38 = 0;
    v39 = 0;
    if ( v6 )
      v39 = *((_QWORD *)v6 + 110);
    if ( *(_QWORD *)(v31 + 120) != v39 && v37 && *(_BYTE *)(v37 + 96) )
    {
      v76 = 0;
      v77 = *(CPreComputeContext **)&v114[15].LockCount;
      if ( !v77 )
      {
        v87 = (CPreComputeContext *)operator new(0x640u);
        v88 = v87;
        if ( v87 )
        {
          memset_0(v87, 0, 0x640u);
          v77 = CPreComputeContext::CPreComputeContext(v88);
        }
        else
        {
          v77 = 0;
        }
        v76 = v77;
      }
      v78 = CPreComputeContext::PreCompute(v77, (struct CVisualTree *)v31);
      v38 = v78;
      if ( v78 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18B,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\visualtree.cpp",
          (const char *)(unsigned int)v78,
          v111);
        if ( v76 )
        {
          CPreComputeContext::~CPreComputeContext(v76);
          operator delete(v76, 0x640u);
        }
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v38, 0xBF3u, 0);
        v6 = g_pComposition;
        goto LABEL_81;
      }
      if ( v76 )
      {
        CPreComputeContext::~CPreComputeContext(v76);
        operator delete(v76, 0x640u);
      }
      v6 = g_pComposition;
      v38 = 0;
    }
    v40 = 0;
    if ( v6 )
      v40 = *((_QWORD *)v6 + 110);
    if ( *(_QWORD *)(v31 + 120) == v40 )
      goto LABEL_81;
    if ( *(_BYTE *)(v31 + 2628) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 232LL))(v31);
      *(_BYTE *)(v31 + 2628) = 0;
    }
    v41 = *(_BYTE *)(v31 + 2630);
    *(_QWORD *)(v31 + 120) = 0;
    *(_BYTE *)(v31 + 2437) = 0;
    *(_WORD *)(v31 + 2439) = 0;
    *(_BYTE *)(v31 + 2436) = v41 == 0;
    *(_OWORD *)(v31 + 2420) = *(_OWORD *)(*(_QWORD *)(v31 + 112) + 2504LL);
    if ( v41 )
    {
      if ( *(_BYTE *)(v31 + 2438) )
        *(_BYTE *)(v31 + 2438) = 0;
      *(_DWORD *)(v31 + 128) = 0;
      *(_BYTE *)(v31 + 564) = 0;
      if ( !*(_BYTE *)(v31 + 2438) )
        CTreeDirty::ClearDirtyRectAnnotationLists((CTreeDirty *)(v31 + 112));
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v31 + 192LL))(v31) )
    {
      v42 = (__int64)(*(_QWORD *)(v31 + 4776) - *(_QWORD *)(v31 + 4768)) >> 3;
      if ( v42 )
        *(_QWORD *)(v31 + 4776) += -8 * v42;
    }
    v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 224LL))(v31);
    v45 = v43;
    if ( v43 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, v31);
    v46 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v31 + 224LL))(v31, v44, v45);
    v47 = v46;
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 32LL))(v46);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 192LL))(v31, v47) )
    {
      v75 = *(_QWORD *)(v31 + 24);
      if ( !*(_DWORD *)(v75 + 6368) )
        goto LABEL_139;
      if ( *(_BYTE *)(v75 + 6461) )
      {
LABEL_229:
        *(_BYTE *)(v31 + 2439) = 1;
        *(_BYTE *)(v75 + 6461) = 0;
      }
      else
      {
        UnoptimizedBounds = (const struct D2D_RECT_F *)CTreeDirty::GetUnoptimizedBounds(v31 + 112, v125);
        if ( !IsEmpty(UnoptimizedBounds) )
        {
          v75 = *(_QWORD *)(v31 + 24);
          goto LABEL_229;
        }
      }
LABEL_139:
      if ( *(_DWORD *)(*(_QWORD *)(v31 + 24) + 6376LL) )
        *(_BYTE *)(v31 + 2440) = 1;
    }
    if ( !*(_BYTE *)(v31 + 2436) )
    {
      while ( 1 )
      {
        CRectangleCollection<8>::EnsureWeights(v31 + 128);
        v84 = 1;
LABEL_156:
        if ( v84 >= *(_DWORD *)(v31 + 128) )
          break;
        for ( i = 0; ; ++i )
        {
          if ( i >= v84 )
          {
            ++v84;
            goto LABEL_156;
          }
          if ( *(float *)(v31 + 8LL * (i + ((v84 * (v84 - 1)) >> 1)) + 280) < 0.5 )
            break;
        }
        CTreeDirty::Merge((CTreeDirty *)(v31 + 112), i, v84);
      }
      v38 = 0;
    }
    v48 = *(_BYTE *)(v31 + 2439) == 0;
    *(_BYTE *)(v31 + 2437) = 1;
    if ( v48 )
    {
      if ( *(_BYTE *)(v31 + 2440) )
      {
        CTreeDirty::SetFullDirty((CTreeDirty *)(v31 + 112));
        *(_BYTE *)(v31 + 2440) = 0;
      }
    }
    else
    {
      CTreeDirty::SetRedrawRects((CTreeDirty *)(v31 + 112));
      CTreeDirty::SetFullDirty((CTreeDirty *)(v31 + 112));
      *(_WORD *)(v31 + 2439) = 0;
    }
    v6 = g_pComposition;
    v49 = 0;
    if ( g_pComposition )
      v49 = *((_QWORD *)g_pComposition + 110);
    *(_QWORD *)(v31 + 120) = v49;
LABEL_81:
    if ( !v26 || v26 >= 0 && v38 < 0 )
      v26 = v38;
    if ( v31 != v30 )
    {
      v64 = 0;
      if ( v6 )
        v64 = *((_QWORD *)v6 + 110);
      if ( *(_QWORD *)(v30 + 120) != v64 )
      {
        v79 = *(_QWORD *)(v30 + 72);
        if ( v79 )
        {
          if ( *(_BYTE *)(v79 + 96) )
          {
            v80 = 0;
            v81 = *(CPreComputeContext **)&v114[15].LockCount;
            if ( !v81 )
            {
              v92 = (CPreComputeContext *)operator new(0x640u);
              v93 = v92;
              if ( v92 )
              {
                memset_0(v92, 0, 0x640u);
                v81 = CPreComputeContext::CPreComputeContext(v93);
              }
              else
              {
                v81 = 0;
              }
              v80 = v81;
            }
            v82 = CPreComputeContext::PreCompute(v81, (struct CVisualTree *)v30);
            v74 = v82;
            if ( v82 >= 0 )
            {
              if ( v80 )
                std::default_delete<CPreComputeContext>::operator()(v83, v80);
              v6 = g_pComposition;
              goto LABEL_112;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x18B,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\visualtree.cpp",
              (const char *)(unsigned int)v82,
              v111);
            if ( v80 )
              std::default_delete<CPreComputeContext>::operator()(v94, v80);
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v74, 0xBFBu, 0);
            v6 = g_pComposition;
LABEL_134:
            if ( !v26 || v26 >= 0 && v74 < 0 )
              v26 = v74;
            goto LABEL_84;
          }
        }
      }
LABEL_112:
      v65 = 0;
      if ( v6 )
        v65 = *((_QWORD *)v6 + 110);
      if ( *(_QWORD *)(v30 + 120) == v65 )
      {
LABEL_133:
        v74 = 0;
        goto LABEL_134;
      }
      if ( *(_BYTE *)(v30 + 2628) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 232LL))(v30);
        *(_BYTE *)(v30 + 2628) = 0;
      }
      v66 = *(_BYTE *)(v30 + 2630);
      *(_QWORD *)(v30 + 120) = 0;
      *(_BYTE *)(v30 + 2437) = 0;
      *(_WORD *)(v30 + 2439) = 0;
      *(_BYTE *)(v30 + 2436) = v66 == 0;
      *(_OWORD *)(v30 + 2420) = *(_OWORD *)(*(_QWORD *)(v30 + 112) + 2504LL);
      if ( v66 )
      {
        if ( *(_BYTE *)(v30 + 2438) )
          *(_BYTE *)(v30 + 2438) = 0;
        *(_DWORD *)(v30 + 128) = 0;
        *(_BYTE *)(v30 + 564) = 0;
        if ( !*(_BYTE *)(v30 + 2438) )
          CTreeDirty::ClearDirtyRectAnnotationLists((CTreeDirty *)(v30 + 112));
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v30 + 192LL))(v30) )
      {
        v67 = (__int64)(*(_QWORD *)(v30 + 4776) - *(_QWORD *)(v30 + 4768)) >> 3;
        if ( v67 )
          *(_QWORD *)(v30 + 4776) += -8 * v67;
      }
      v68 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 224LL))(v30);
      v70 = v68;
      if ( v68 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 24LL))(v68, v30);
      v71 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v30 + 224LL))(v30, v69, v70);
      v72 = v71;
      if ( v71 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 32LL))(v71);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 192LL))(v30, v72) )
      {
LABEL_126:
        if ( !*(_BYTE *)(v30 + 2436) )
        {
          while ( 1 )
          {
            CRectangleCollection<8>::EnsureWeights(v30 + 128);
            v90 = 1;
LABEL_182:
            if ( v90 >= *(_DWORD *)(v30 + 128) )
              break;
            for ( j = 0; ; ++j )
            {
              if ( j >= v90 )
              {
                ++v90;
                goto LABEL_182;
              }
              if ( *(float *)(v30 + 8LL * (j + ((v90 * (v90 - 1)) >> 1)) + 280) < 0.5 )
                break;
            }
            CTreeDirty::Merge((CTreeDirty *)(v30 + 112), j, v90);
          }
        }
        *(_BYTE *)(v30 + 2437) = 1;
        if ( *(_BYTE *)(v30 + 2439) )
        {
          CTreeDirty::SetRedrawRects((CTreeDirty *)(v30 + 112));
          CTreeDirty::SetFullDirty((CTreeDirty *)(v30 + 112));
          *(_WORD *)(v30 + 2439) = 0;
        }
        else if ( *(_BYTE *)(v30 + 2440) )
        {
          CTreeDirty::SetFullDirty((CTreeDirty *)(v30 + 112));
          *(_BYTE *)(v30 + 2440) = 0;
        }
        v6 = g_pComposition;
        v73 = 0;
        if ( g_pComposition )
          v73 = *((_QWORD *)g_pComposition + 110);
        *(_QWORD *)(v30 + 120) = v73;
        goto LABEL_133;
      }
      v89 = *(_QWORD *)(v30 + 24);
      if ( *(_DWORD *)(v89 + 6368) )
      {
        if ( !*(_BYTE *)(v89 + 6461) )
        {
          v103 = (const struct D2D_RECT_F *)CTreeDirty::GetUnoptimizedBounds(v30 + 112, &v118);
          if ( IsEmpty(v103) )
            goto LABEL_179;
          v89 = *(_QWORD *)(v30 + 24);
        }
        *(_BYTE *)(v30 + 2439) = 1;
        *(_BYTE *)(v89 + 6461) = 0;
      }
LABEL_179:
      if ( *(_DWORD *)(*(_QWORD *)(v30 + 24) + 6376LL) )
        *(_BYTE *)(v30 + 2440) = 1;
      goto LABEL_126;
    }
LABEL_84:
    v3 = v113;
    DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)DebugInfo + 8);
  }
  v50 = v114;
  p_SpinCount = &v114[13].SpinCount;
  LOBYTE(v114[141].OwningThread) = 0;
  v52 = (_QWORD *)p_SpinCount[1];
  if ( v52 != (_QWORD *)*p_SpinCount )
  {
    v53 = *(_QWORD **)&v50[10].LockCount;
    for ( k = &v50[10].DebugInfo->Type; ; ++k )
    {
      v55 = v52;
      if ( k == v53 )
        break;
      for ( m = (_QWORD *)*p_SpinCount; m != v52 && *m != *k; ++m )
        ;
      v52 = (_QWORD *)p_SpinCount[1];
      v55 = v52;
      if ( m != v52 )
        break;
    }
    v56 = (char *)k;
    if ( k != v53 )
    {
      while ( ++k != v53 )
      {
        v97 = *k;
        for ( n = (_QWORD *)*p_SpinCount; n != v55 && *n != v97; ++n )
          ;
        v55 = (_QWORD *)p_SpinCount[1];
        if ( n == v55 )
        {
          *(_QWORD *)v56 = v97;
          v56 += 8;
          v55 = (_QWORD *)p_SpinCount[1];
        }
      }
    }
    detail::vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>::clear_region(
      &v50[10],
      (v56 - (char *)v50[10].DebugInfo) >> 3,
      (__int64)(*(_QWORD *)&v50[10].LockCount - (_QWORD)v56) >> 3,
      v55);
    if ( (__int64)(p_SpinCount[1] - *p_SpinCount) >> 3 )
      detail::vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>::clear_region(p_SpinCount);
  }
  if ( LOBYTE(v50[160].LockCount) )
  {
    v57 = v50[160].DebugInfo;
    LOBYTE(v50[160].LockCount) = 0;
    if ( !SetEvent(v57) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v58);
  }
  if ( v50 != (struct _RTL_CRITICAL_SECTION *)-360LL )
    LeaveCriticalSection(v50 + 9);
  if ( PerformanceCount.QuadPart )
  {
    v105 = 0;
    memset_0(v126, 0, sizeof(v126));
    v106 = *(_QWORD *)v50[15].OwningThread;
    if ( v106 )
    {
      v107 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 56LL))(v106);
      if ( v107 )
      {
        CTreeDirty::GetDirtyRects(v107 + 112, v125);
        v105 = v125[0];
        for ( ii = 0; ii < v105; v126[v110] = *v109 )
        {
          v109 = (_OWORD *)gsl::span<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const,-1>::operator[](
                             v125,
                             ii);
          v110 = ii++;
        }
      }
    }
    if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 4) != 0 )
      McTemplateU0qqxqNR3_EventWriteTransfer(
        (unsigned int)v126,
        (unsigned __int64)(1000000 * (v116.QuadPart - PerformanceCount.QuadPart)) % g_qpcFrequency.QuadPart,
        v26,
        v3,
        (unsigned __int64)(1000000 * (v116.QuadPart - PerformanceCount.QuadPart)) / g_qpcFrequency.QuadPart,
        v105);
  }
  v59 = 0;
  CycleTime = 0;
  if ( ::CycleTime )
  {
    CurrentThread = GetCurrentThread();
    v61 = QueryThreadCycleTime(CurrentThread, &CycleTime);
    v59 = CycleTime;
    if ( v61 )
      qword_1803BADC8 += CycleTime - ::CycleTime;
  }
  ::CycleTime = v59;
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1800d0b90  push    rbp
0x1800d0b92  push    rbx
0x1800d0b93  push    rsi
0x1800d0b94  push    rdi
0x1800d0b95  push    r12
0x1800d0b97  push    r13
0x1800d0b99  push    r14
0x1800d0b9b  push    r15
0x1800d0b9d  lea     rbp, [rsp-0E8h]
0x1800d0ba5  sub     rsp, 1E8h
0x1800d0bac  mov     rax, cs:__security_cookie
0x1800d0bb3  xor     rax, rsp
0x1800d0bb6  mov     [rbp+120h+var_60], rax
0x1800d0bbd  xor     r15d, r15d
0x1800d0bc0  mov     [rsp+220h+var_1D0], rcx
0x1800d0bc5  test    byte ptr cs:Microsoft_Windows_Dwm_CompositorEnableBits, 4
0x1800d0bcc  mov     r12, rcx
0x1800d0bcf  mov     qword ptr [rsp+220h+PerformanceCount], r15
0x1800d0bd4  mov     qword ptr [rsp+220h+var_1C0], r15
0x1800d0bd9  jnz     loc_1800D1839
0x1800d0bdf  lea     rcx, [r12+168h]; lpCriticalSection
0x1800d0be7  call    cs:__imp_EnterCriticalSection
0x1800d0bed  cmp     qword ptr [rsp+220h+PerformanceCount], r15
0x1800d0bf2  jnz     loc_1800D186B
0x1800d0bf8  mov     r10, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d0bff  lea     rbx, [rbp+120h+Mem]
0x1800d0c03  lea     rcx, [rbp+120h+Mem]
0x1800d0c07  mov     [rbp+120h+var_150], rbx
0x1800d0c0b  lea     rax, [rbp+120h+var_F8]
0x1800d0c0f  mov     [rbp+120h+var_148], rcx
0x1800d0c13  mov     [rbp+120h+var_140], rax
0x1800d0c17  mov     r14, [r10+1838h]
0x1800d0c1e  mov     [rbp+120h+var_1A0], r14
0x1800d0c22  mov     rsi, [r14]
0x1800d0c25  lea     rax, off_1802B9F98
0x1800d0c2c  cmp     rsi, r14
0x1800d0c2f  jz      loc_1800D0E05
0x1800d0c35  mov     r13, [rsi+10h]
0x1800d0c39  lea     r9, [rbp+120h+var_190]
0x1800d0c3d  mov     [rbp+120h+var_190], rax
0x1800d0c41  mov     rdi, r13
0x1800d0c44  lea     rax, [rbp+120h+var_150]
0x1800d0c48  mov     [rsp+220h+CycleTime], r13
0x1800d0c4d  mov     [rbp+120h+var_188], rax
0x1800d0c51  mov     rbx, r13
0x1800d0c54  mov     [rbp+120h+var_158], r9
0x1800d0c58  nop     dword ptr [rax+rax+00000000h]
0x1800d0c60  test    rdi, rdi
0x1800d0c63  jz      loc_1800D0CFE
0x1800d0c69  mov     r8, [rdi+0E0h]
0x1800d0c70  test    dword ptr [r8], 8000000h
0x1800d0c77  jz      short loc_1800D0CCD
0x1800d0c79  mov     ecx, [r8+4]
0x1800d0c7d  mov     edx, r15d
0x1800d0c80  test    ecx, ecx
0x1800d0c82  jz      short loc_1800D0CF5
0x1800d0c84  cmp     byte ptr [rdx+r8+8], 5
0x1800d0c8a  jnz     short loc_1800D0CEF
0x1800d0c8c  add     rcx, 0Fh
0x1800d0c90  shl     rdx, 3
0x1800d0c94  mov     rax, rcx
0x1800d0c97  and     eax, 7
0x1800d0c9a  sub     rdx, rax
0x1800d0c9d  add     rdx, rcx
0x1800d0ca0  add     rdx, r8
0x1800d0ca3  mov     rax, [rdx]
0x1800d0ca6  test    rax, rax
0x1800d0ca9  jz      short loc_1800D0CCD
0x1800d0cab  mov     [rsp+220h+var_1B8], rax
0x1800d0cb0  test    r9, r9
0x1800d0cb3  jz      short loc_1800D0CE8
0x1800d0cb5  mov     rax, [r9]
0x1800d0cb8  lea     rdx, [rsp+220h+var_1B8]
0x1800d0cbd  mov     rcx, r9
0x1800d0cc0  mov     rax, [rax+10h]
0x1800d0cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0cc9  mov     r9, [rbp+120h+var_158]
0x1800d0ccd  test    rbx, rbx
0x1800d0cd0  jz      short loc_1800D0CDF
0x1800d0cd2  mov     rbx, [rbx+58h]
0x1800d0cd6  test    rbx, rbx
0x1800d0cd9  jnz     loc_1800D0DDD
0x1800d0cdf  mov     rdi, [rdi+58h]
0x1800d0ce3  jmp     loc_1800D0C60
0x1800d0ce8  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800d0cee  int     3; Trap to Debugger
0x1800d0cef  inc     edx
0x1800d0cf1  cmp     edx, ecx
0x1800d0cf3  jb      short loc_1800D0C84
0x1800d0cf5  cmp     edx, ecx
0x1800d0cf7  jb      short loc_1800D0C8C
0x1800d0cf9  mov     rdx, r15
0x1800d0cfc  jmp     short loc_1800D0CA3
0x1800d0cfe  test    r9, r9
0x1800d0d01  jz      short loc_1800D0D20
0x1800d0d03  mov     rax, [r9]
0x1800d0d06  lea     rcx, [rbp+120h+var_190]
0x1800d0d0a  cmp     r9, rcx
0x1800d0d0d  mov     rcx, r9
0x1800d0d10  setnz   dl
0x1800d0d13  mov     rax, [rax+20h]
0x1800d0d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0d1c  mov     [rbp+120h+var_158], r15
0x1800d0d20  xor     eax, eax
0x1800d0d22  mov     byte ptr [rsi+33h], 0
0x1800d0d26  mov     [rsp+220h+var_1D8], rax
0x1800d0d2b  lea     r15, [rsi+18h]
0x1800d0d2f  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d0d36  test    rax, rax
0x1800d0d39  jz      short loc_1800D0D47
0x1800d0d3b  mov     rax, [rax+370h]
0x1800d0d42  mov     [rsp+220h+var_1D8], rax
0x1800d0d47  mov     rbx, [rbp+120h+var_150]
0x1800d0d4b  lea     rax, [r15+1Ah]
0x1800d0d4f  mov     rdi, [rbp+120h+var_148]
0x1800d0d53  mov     r12, rax
0x1800d0d56  mov     r14, [rsp+220h+var_1D8]
0x1800d0d5b  mov     [rbp+120h+var_F8], rax
0x1800d0d5f  nop
0x1800d0d60  cmp     rbx, rdi
0x1800d0d63  jz      short loc_1800D0D9A
0x1800d0d65  mov     r13, [rbx]
0x1800d0d68  mov     r9, r14; unsigned __int64
0x1800d0d6b  mov     r12, [rsp+220h+CycleTime]
0x1800d0d70  mov     r8, r13; struct CVisualTree *
0x1800d0d73  mov     rdx, r12; struct CVisual *
0x1800d0d76  mov     rcx, r15; this
0x1800d0d79  call    ?CalcTransform@CPreWalkVisual@@AEAAXPEAVCVisual@@PEBVCVisualTree@@_K@Z; CPreWalkVisual::CalcTransform(CVisual *,CVisualTree const *,unsigned __int64)
0x1800d0d7e  cmp     byte ptr [r15+18h], 0
0x1800d0d83  jnz     short loc_1800D0DF8
0x1800d0d85  cmp     byte ptr [r15+1Ah], 0
0x1800d0d8a  lea     r12, [r15+1Ah]
0x1800d0d8e  jnz     loc_1800D187B
0x1800d0d94  add     rbx, 8
0x1800d0d98  jmp     short loc_1800D0D60
0x1800d0d9a  cmp     byte ptr [r15+1Bh], 0
0x1800d0d9f  mov     r14, [rbp+120h+var_1A0]
0x1800d0da3  jnz     loc_1800D1578
0x1800d0da9  mov     rcx, [rbp+120h+var_148]
0x1800d0dad  mov     rbx, [rbp+120h+var_150]
0x1800d0db1  mov     rax, rcx
0x1800d0db4  sub     rax, rbx
0x1800d0db7  sar     rax, 3
0x1800d0dbb  test    rax, rax
0x1800d0dbe  jz      short loc_1800D0DCB
0x1800d0dc0  neg     rax
0x1800d0dc3  lea     rcx, [rcx+rax*8]
0x1800d0dc7  mov     [rbp+120h+var_148], rcx
0x1800d0dcb  mov     rsi, [rsi]
0x1800d0dce  xor     r15d, r15d
0x1800d0dd1  mov     r10, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d0dd8  jmp     loc_1800D0C25
0x1800d0ddd  cmp     rdi, rbx
0x1800d0de0  jz      loc_1800D0CFE
0x1800d0de6  mov     rbx, [rbx+58h]
0x1800d0dea  cmp     rdi, rbx
0x1800d0ded  jnz     loc_1800D0CDF
0x1800d0df3  jmp     loc_1800D0CFE
0x1800d0df8  mov     rdx, r13; struct CVisualTree *
0x1800d0dfb  mov     rcx, r12; struct CVisual *
0x1800d0dfe  call    ?DirtyBoundsForTransformParentChild@CPreWalkVisual@@CAXPEAVCVisual@@PEBVCVisualTree@@@Z; CPreWalkVisual::DirtyBoundsForTransformParentChild(CVisual *,CVisualTree const *)
0x1800d0e03  jmp     short loc_1800D0D85
0x1800d0e05  mov     rax, rcx
0x1800d0e08  movaps  [rsp+220h+var_50], xmm6
0x1800d0e10  sub     rax, rbx
0x1800d0e13  mov     dword ptr [rsp+220h+var_1D8], r15d
0x1800d0e18  sar     rax, 3
0x1800d0e1c  mov     r13d, r15d
0x1800d0e1f  test    rax, rax
0x1800d0e22  jz      short loc_1800D0E2F
0x1800d0e24  neg     rax
0x1800d0e27  lea     rax, [rcx+rax*8]
0x1800d0e2b  mov     [rbp+120h+var_148], rax
0x1800d0e2f  lea     rax, [rbp+120h+Mem]
0x1800d0e33  mov     [rbp+120h+var_150], 0
0x1800d0e3b  cmp     rbx, rax
0x1800d0e3e  jz      short loc_1800D0E49
0x1800d0e40  test    rbx, rbx
0x1800d0e43  jnz     loc_1800D1215
0x1800d0e49  mov     r12, [rsp+220h+var_1D0]
0x1800d0e4e  movss   xmm6, cs:__real@3f000000
0x1800d0e56  mov     byte ptr [r12+1618h], 1
0x1800d0e5f  mov     rdi, [r12+190h]
0x1800d0e67  mov     rsi, [r12+198h]
0x1800d0e6f  nop
0x1800d0e70  cmp     rdi, rsi
0x1800d0e73  jz      loc_1800D108D
0x1800d0e79  mov     r12, [rdi]
0x1800d0e7c  mov     r14, r12
0x1800d0e7f  mov     r9, [r12+48h]
0x1800d0e84  test    r9, r9
0x1800d0e87  jz      short loc_1800D0EDD
0x1800d0e89  mov     r8, [r9+0E0h]
0x1800d0e90  test    dword ptr [r8], 8000000h
0x1800d0e97  jz      short loc_1800D0ED4
0x1800d0e99  mov     ecx, [r8+4]
0x1800d0e9d  xor     edx, edx
0x1800d0e9f  test    ecx, ecx
0x1800d0ea1  jz      loc_1800D11D8
0x1800d0ea7  cmp     byte ptr [rdx+r8+8], 5
0x1800d0ead  jnz     loc_1800D11CE
0x1800d0eb3  add     rcx, 0Fh
0x1800d0eb7  shl     rdx, 3
0x1800d0ebb  mov     rax, rcx
0x1800d0ebe  and     eax, 7
0x1800d0ec1  sub     rdx, rax
0x1800d0ec4  add     rdx, rcx
0x1800d0ec7  add     rdx, r8
0x1800d0eca  mov     rax, [rdx]
0x1800d0ecd  test    rax, rax
0x1800d0ed0  cmovnz  r14, rax
0x1800d0ed4  mov     r9, [r9+58h]
0x1800d0ed8  test    r9, r9
0x1800d0edb  jnz     short loc_1800D0E89
0x1800d0edd  mov     rdx, [r14+48h]
0x1800d0ee1  test    rdx, rdx
0x1800d0ee4  jnz     loc_1800D11FE
0x1800d0eea  xor     r15d, r15d
0x1800d0eed  mov     ecx, r15d
0x1800d0ef0  test    r10, r10
0x1800d0ef3  jz      short loc_1800D0EFC
0x1800d0ef5  mov     rcx, [r10+370h]
0x1800d0efc  cmp     [r14+78h], rcx
0x1800d0f00  jz      short loc_1800D0F0B
0x1800d0f02  test    rdx, rdx
0x1800d0f05  jnz     loc_1800D144B
0x1800d0f0b  mov     rax, r15
0x1800d0f0e  test    r10, r10
0x1800d0f11  jz      short loc_1800D0F1A
0x1800d0f13  mov     rax, [r10+370h]
0x1800d0f1a  cmp     [r14+78h], rax
0x1800d0f1e  jz      loc_1800D106A
0x1800d0f24  cmp     byte ptr [r14+0A44h], 0
0x1800d0f2c  jz      short loc_1800D0F48
0x1800d0f2e  mov     rax, [r14]
0x1800d0f31  mov     rcx, r14
0x1800d0f34  mov     rax, [rax+0E8h]
0x1800d0f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0f40  mov     byte ptr [r14+0A44h], 0
0x1800d0f48  movzx   ecx, byte ptr [r14+0A46h]
0x1800d0f50  test    cl, cl
0x1800d0f52  mov     [r14+78h], r15
0x1800d0f56  mov     byte ptr [r14+985h], 0
0x1800d0f5e  setz    al
0x1800d0f61  mov     word ptr [r14+987h], 0
0x1800d0f6b  mov     [r14+984h], al
0x1800d0f72  mov     rax, [r14+70h]
0x1800d0f76  movups  xmm0, xmmword ptr [rax+9C8h]
0x1800d0f7d  movups  xmmword ptr [r14+974h], xmm0
0x1800d0f85  test    cl, cl
0x1800d0f87  jnz     loc_1800D1235
0x1800d0f8d  mov     rax, [r14]
0x1800d0f90  mov     rcx, r14
0x1800d0f93  mov     rax, [rax+0C0h]
0x1800d0f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0f9f  test    al, al
0x1800d0fa1  jz      short loc_1800D0FC8
0x1800d0fa3  mov     rax, [r14+12A8h]
0x1800d0faa  sub     rax, [r14+12A0h]
0x1800d0fb1  sar     rax, 3
0x1800d0fb5  test    rax, rax
0x1800d0fb8  jz      short loc_1800D0FC8
0x1800d0fba  neg     rax
0x1800d0fbd  shl     rax, 3
0x1800d0fc1  add     [r14+12A8h], rax
0x1800d0fc8  mov     rax, [r14]
0x1800d0fcb  mov     rcx, r14
0x1800d0fce  mov     rax, [rax+0E0h]
0x1800d0fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0fda  mov     r8, rax
0x1800d0fdd  test    rax, rax
0x1800d0fe0  jnz     loc_1800D11E7
0x1800d0fe6  mov     rax, [r14]
0x1800d0fe9  mov     rcx, r14
0x1800d0fec  mov     rax, [rax+0E0h]
0x1800d0ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ff8  mov     rdx, rax
0x1800d0ffb  test    rax, rax
0x1800d0ffe  jnz     loc_1800D18A9
0x1800d1004  mov     rax, [r14]
0x1800d1007  mov     rcx, r14
0x1800d100a  mov     rax, [rax+0C0h]
0x1800d1011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1016  test    al, al
0x1800d1018  jnz     loc_1800D141C
0x1800d101e  cmp     byte ptr [r14+984h], 0
0x1800d1026  jz      loc_1800D1524
0x1800d102c  cmp     byte ptr [r14+987h], 0
0x1800d1034  mov     byte ptr [r14+985h], 1
0x1800d103c  jnz     loc_1800D18FE
0x1800d1042  cmp     byte ptr [r14+988h], 0
0x1800d104a  jnz     loc_1800D191F
0x1800d1050  mov     r10, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d1057  mov     rax, r15
0x1800d105a  test    r10, r10
0x1800d105d  jz      short loc_1800D1066
0x1800d105f  mov     rax, [r10+370h]
0x1800d1066  mov     [r14+78h], rax
0x1800d106a  test    r13d, r13d
0x1800d106d  jnz     loc_1800D1935
  ... truncated ...
```
