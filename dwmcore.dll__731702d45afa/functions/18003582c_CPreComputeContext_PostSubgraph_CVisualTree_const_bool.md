# CPreComputeContext::PostSubgraph(CVisualTree const *,bool *)

- ea: `0x18003582c`
- end: `0x1800360f0`
- name: `?PostSubgraph@CPreComputeContext@@QEAAJPEBVCVisualTree@@PEA_N@Z`
- size: `2244`
- prototype: `int(CPreComputeContext *__hidden this, const struct CVisualTree *, bool *)`
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033cf0`

## callees

- `0x1800100b0`
- `0x18002874c`
- `0x18002a1d0`
- `0x18002ede0`
- `0x18002eef4`
- `0x18002feb0`
- `0x18003582c`
- `0x18003ef30`
- `0x18003ff78`
- `0x180047fbc`
- `0x18004dbb8`
- `0x18004fce4`
- `0x1800873b0`
- `0x1800b4f90`
- `0x1800ba8e0`
- `0x1800bbec0`
- `0x1800cf6a0`
- `0x1800d0090`
- `0x1800d02a0`
- `0x1801456b0`
- `0x18014c0d0`
- `0x18014ce80`
- `0x18014f0a0`
- `0x180166400`
- `0x18016c1f0`
- `0x180171eb0`
- `0x18017b150`
- `0x18017df60`
- `0x180183330`
- `0x1801856b0`
- `0x180187488`
- `0x1801b3728`
- `0x1801bd258`
- `0x1802284b0`
- `0x18022945c`
- `0x180229738`
- `0x18022978c`
- `0x1802328d8`
- `0x18023290c`
- `0x180276718`
- `0x1802b6010`

## import_xrefs

- `ext-ms-win-compositor-hosting-l1-3-0!NotifyInputSinkTransformChanged` at `0x180036010`
- `ext-ms-win-compositor-hosting-l1-3-0!NotifyInputSinkTransformChanged` at `0x180036010`
- `ext-ms-win-compositor-hosting-l1-2-1!NotifyInputSinkParented` at `0x180035f25`
- `ext-ms-win-compositor-hosting-l1-2-1!NotifyInputSinkParented` at `0x180035f25`

## string_xrefs

- `0x1800358ee`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x180035fea`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x180036050`: `onecoreuap\windows\dwm\dwmcore\engine\precomputecontext.cpp`
- `0x180035eae`: `PreCompute-AddedDirtyRectInPostSubgraph`

## pseudocode

```c
__int64 __fastcall CPreComputeContext::PostSubgraph(CPreComputeContext *this, const struct CVisualTree *a2, bool *a3)
{
  __int64 v3; // r12
  __int64 v4; // r13
  __int64 v6; // rsi
  __int64 v8; // rax
  __int64 v10; // r13
  const struct CVisualTree *v11; // rdx
  int v12; // ebx
  __int64 v13; // rdx
  char v15; // al
  bool *v16; // r8
  const struct CVisual *TransformParent; // rax
  bool *v18; // r8
  __int64 v19; // rbx
  const struct CVisual *v20; // r12
  __int64 v21; // rdi
  bool v22; // r9
  int v23; // edx
  int v24; // ecx
  float v25; // xmm5_4
  float v26; // xmm2_4
  float v27; // xmm4_4
  __int32 v28; // xmm1_4
  float v29; // xmm7_4
  float v30; // xmm3_4
  float v31; // xmm6_4
  char v32; // al
  int v33; // eax
  int v34; // ebx
  bool HasInputSink; // al
  int v36; // r10d
  int v37; // ebx
  char v38; // al
  int v39; // ecx
  bool v40; // al
  int v41; // r8d
  int v42; // ecx
  int v43; // edx
  int v44; // ecx
  int v45; // ecx
  unsigned int v46; // r8d
  __int64 v47; // rbx
  __int64 v48; // rdi
  struct _LIST_ENTRY *v49; // r12
  struct _LIST_ENTRY **p_Blink; // r9
  struct _LIST_ENTRY *TreeDataListHead; // rax
  struct _LIST_ENTRY *i; // rcx
  int v53; // eax
  __int64 v54; // r9
  __int64 v55; // rdi
  CVisualTreePath *v56; // rbx
  __int64 v57; // rax
  CTreeData *v58; // rdi
  void *InputHandle; // rbx
  _QWORD *TopByReference; // rax
  char IsEnabled; // al
  char v62; // cl
  int v63; // edi
  __int64 v64; // rdx
  CPreComputeSubTreeContext *v65; // rbx
  CPreComputeSubTreeContext *v66; // rdi
  const struct CVisual *Parent; // rax
  struct CVisual *v68; // rdx
  CBspPreComputeHelper *v69; // rcx
  int v70; // eax
  unsigned int v71; // r15d
  int v72; // [rsp+20h] [rbp-E0h]
  bool v73; // [rsp+50h] [rbp-B0h]
  _DWORD v74[4]; // [rsp+60h] [rbp-A0h] BYREF
  CTreeData *TreeData; // [rsp+70h] [rbp-90h]
  __int64 v76; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v77[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v78; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-50h]
  void *v80; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v81[72]; // [rsp+C8h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v3 = *((_QWORD *)this + 192);
  v4 = *((_QWORD *)this + 1);
  v6 = *((_QWORD *)this + 191);
  TreeData = 0;
  v8 = *(_QWORD *)a2;
  v76 = v3;
  v10 = v4 - 352;
  if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(v8 + 192))(a2) )
    TreeData = CVisual::FindTreeData((CVisual *)v6, a2);
  *a3 = 1;
  if ( *(_BYTE *)(v10 + 345) )
    goto LABEL_125;
  v12 = CLightStack::PopLightsFromVisual((CPreComputeContext *)((char *)this + 1176), (const struct CVisual *)v6, a2);
  if ( v12 < 0 )
  {
    v13 = 899;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
      (const char *)(unsigned int)v12,
      v72);
    return (unsigned int)v12;
  }
  v15 = *(_BYTE *)(v6 + 96);
  v73 = 0;
  if ( (v15 & 1) != 0 )
  {
    if ( CVisual::ResolveTransformParent((CVisual *)v6, v11) )
    {
      TransformParent = CVisual::GetTransformParent((CVisual *)v6, a2, v16);
      v19 = *(_QWORD *)this;
      v20 = TransformParent;
      v21 = *((_QWORD *)this + 1);
      while ( v19 != v21 )
      {
        if ( v20 != CVisual::GetTransformParent((CVisual *)v6, *(const struct CVisualTree **)(v19 + 328), v18) )
        {
          v22 = 1;
          goto LABEL_16;
        }
        v19 += 352;
      }
      v22 = 0;
    }
    else
    {
      v20 = 0;
      v22 = 0;
    }
LABEL_16:
    v12 = CVisual::ConvertInnerToOuterBounds((CVisual *)v6, a2, v20, v22);
    if ( v12 < 0 )
    {
      v13 = 930;
      goto LABEL_6;
    }
    v73 = 1;
    if ( CCommonRegistryData::EnableDwmMoveRectHints )
    {
      if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)a2 + 192LL))(a2) )
      {
        memset(v77, 0, 24);
        v79 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)((char *)v77 + 8), *(__m128d *)((char *)v77 + 8));
        v78 = v77[0];
        CWatermarkStack<CPreComputeContext::MoveRectHintData::MoveBounds,64,2,10>::TopOrDefault(
          (char *)this + 1432,
          v77,
          &v78);
        if ( *(_QWORD *)&v77[0] == v6 )
        {
          v25 = *(float *)(v6 + 144);
          v26 = *((float *)v77 + 2);
          v27 = *(float *)(v6 + 152) - v25;
          COERCE_FLOAT(v28 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
          if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*(float *)&v77[1] - *((float *)v77 + 2)) - v27) & v28) <= 0.000081380211 )
          {
            v29 = *(float *)(v6 + 148);
            v30 = *((float *)v77 + 3);
            v31 = *(float *)(v6 + 156) - v29;
            if ( COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(*((float *)&v77[1] + 1) - *((float *)v77 + 3)) - v31) & v28) <= 0.000081380211
              && (COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v77 + 2) - v25) & v28) > 0.000081380211
               || COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v77 + 3) - v29) & v28) > 0.000081380211) )
            {
              v32 = *((_BYTE *)this + 1480);
              if ( v32 && (float)(v31 * v27) <= (float)(*((float *)this + 369) * *((float *)this + 368)) )
              {
                LOBYTE(v24) = 0;
              }
              else
              {
                *((_DWORD *)this + 364) = DWORD2(v77[0]);
                LOBYTE(v24) = 1;
                *((float *)this + 365) = v30;
                *((float *)this + 366) = v25;
                *((float *)this + 367) = v29;
                *((float *)this + 368) = v27;
                *((float *)this + 369) = v31;
                if ( !v32 )
                  *((_BYTE *)this + 1480) = 1;
              }
              if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x20) != 0 )
              {
                *(float *)v74 = v26;
                *(float *)&v74[1] = v30;
                *(float *)&v74[2] = v25 - v26;
                *(float *)&v74[3] = v29 - v30;
                McTemplateU0xtnnn_EventWriteTransfer(v24, v23, v6, (unsigned __int8)v24);
              }
            }
          }
          v33 = *((_DWORD *)this + 360);
          if ( v33 )
            *((_DWORD *)this + 360) = v33 - 1;
        }
      }
    }
    *(_BYTE *)(v6 + 96) &= ~1u;
    v15 = *(_BYTE *)(v6 + 96);
    v3 = v76;
  }
  if ( (v15 & 0x10) != 0 )
  {
    v34 = (int)(*(_DWORD *)(v6 + 96) << 15) >> 23;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v6 + 272LL))(v6) && (v34 & 1) == 0 )
      CVisual::HasSingleD2DBitmapOrPrimitiveGroup((CVisual *)v6);
    CVisual::Has3DContent((CVisual *)v6);
    (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 344LL))(v6);
    CVisual::HasPixelSnappedContent((CVisual *)v6);
    HasInputSink = CVisual::HasInputSink((CVisual *)v6);
    v37 = v36 | 0x10;
    if ( !HasInputSink )
      v37 = v36;
    v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 280LL))(v6);
    v39 = v37 | 0x40;
    if ( !v38 )
      v39 = v37;
    *(_DWORD *)(v6 + 96) = (v39 << 8) ^ (*(_DWORD *)(v6 + 96) ^ (v39 << 8)) & 0xFFFE00FF;
  }
  if ( v3 )
  {
    v40 = CVisual::HasInputSink((CVisual *)v6);
    v41 = *(_DWORD *)(v3 + 96);
    v42 = 32;
    if ( (*(_BYTE *)(v6 + 102) & 4) == 0 )
      v42 = 32 * v40;
    v43 = v42 | 0x80;
    if ( (*(_DWORD *)(v6 + 96) & 0x60000) == 0 )
      v43 = v42;
    v44 = v43 | 0x100;
    if ( (*(_DWORD *)(v6 + 96) & *(_DWORD *)(v3 + 96) & 0x100) == 0 )
      v44 = v43;
    v45 = *(_DWORD *)(v6 + 96) | v41 | (v44 << 8);
    v46 = v45 ^ (v45 ^ v41) & 0xFFFE00FF;
    *(_DWORD *)(v3 + 96) = v46;
    if ( (v46 & 1) != 0 )
      TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>::UnionUnsafe(
        v3 + 168,
        v6 + 144);
  }
  if ( (*(_BYTE *)(v6 + 103) & 2) != 0 )
  {
    v12 = CPreComputeContext::ProcessPostSubgraphWindowBackdropInput(this, (struct CVisual *)v6);
    if ( v12 < 0 )
    {
      v13 = 1130;
      goto LABEL_6;
    }
  }
  v47 = *(_QWORD *)this;
  v48 = *((_QWORD *)this + 1);
  while ( v47 != v48 )
  {
    v49 = *(struct _LIST_ENTRY **)(v47 + 328);
    if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *))v49->Flink[12].Flink)(v49) )
    {
      p_Blink = (struct _LIST_ENTRY **)(v6 + 320);
    }
    else
    {
      TreeDataListHead = CVisual::GetTreeDataListHead((CVisual *)v6);
      if ( TreeDataListHead )
      {
        for ( i = TreeDataListHead->Flink; i != TreeDataListHead; i = i->Flink )
        {
          if ( i[2].Flink == v49 )
          {
            p_Blink = &i[-22].Blink;
            break;
          }
        }
      }
    }
    if ( *((_BYTE *)p_Blink + 8) )
    {
      v53 = *(_DWORD *)(v47 + 280);
      if ( v53 )
        *(_DWORD *)(v47 + 280) = v53 - 1;
      *((_BYTE *)p_Blink + 8) = 0;
    }
    if ( *((_BYTE *)p_Blink + 9) )
    {
      CBaseClipStack::Pop((CBaseClipStack *)(v47 + 296));
      *(_BYTE *)(v54 + 9) = 0;
    }
    v47 += 352;
  }
  if ( (*(_BYTE *)(v6 + 100) & 4) != 0 )
    CWatermarkStack<D2D_VECTOR_2F,2,2,10>::Pop((char *)this + 1128);
  if ( (*(_BYTE *)(v6 + 100) & 2) != 0 )
    CWatermarkStack<void *,2,2,10>::Pop((char *)this + 1104);
  if ( (*(_BYTE *)(v6 + 100) & 8) != 0 )
    CWatermarkStack<void *,2,2,10>::Pop((char *)this + 1152);
  if ( (*(_BYTE *)(v6 + 100) & 0x10) != 0 )
    *((_BYTE *)this + 1592) = *((_BYTE *)this + 1592) == 0;
  if ( *(char *)(v6 + 102) < 0 )
  {
    v12 = CPreComputeContext::ProcessPostSubgraphBackdropInput(this, (struct CVisual *)v6, v73);
    if ( v12 < 0 )
    {
      v13 = 1178;
      goto LABEL_6;
    }
  }
  if ( (**(_DWORD **)(v6 + 224) & 0x800000) != 0 )
  {
    v12 = CPreComputeContext::ProcessPostSubgraphWindowBackgroundTreatment(this, (struct CVisual *)v6, v73);
    if ( v12 < 0 )
    {
      v13 = 1183;
      goto LABEL_6;
    }
  }
  if ( (*(_BYTE *)(v6 + 96) & 4) != 0 )
  {
    --*(_DWORD *)(v10 + 340);
    v12 = CPreComputeContext::AddLocalBoundsToSubTreesDirtyRegion(this, (struct CVisual *)v6);
    if ( v12 < 0 )
    {
      v13 = 1191;
      goto LABEL_6;
    }
    if ( dword_1803B9890 && (*(int *)(v6 + 256) > 0 || *(int *)(v6 + 260) > 0) )
    {
      v55 = DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)&v76, word_1802D21E2);
      v56 = CVisualTreePath::CVisualTreePath((CVisualTreePath *)&v80, a2);
      v57 = DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)v74, "PreCompute-AddedDirtyRectInPostSubgraph");
      DwmDbg::Backdrops::LogTreeWalkEtwEvent(v57, v6, a2, v56, v55);
      detail::vector_facade<CVisualTreePath::VisualTreePathUnit,detail::buffer_impl<CVisualTreePath::VisualTreePathUnit,2,1,detail::liberal_expansion_policy>>::~vector_facade<CVisualTreePath::VisualTreePathUnit,detail::buffer_impl<CVisualTreePath::VisualTreePathUnit,2,1,detail::liberal_expansion_policy>>(&v80);
    }
  }
  v58 = TreeData;
  if ( TreeData )
  {
    InputHandle = CVisual::GetInputHandle((CVisual *)v6);
    if ( InputHandle )
    {
      if ( ((*(_BYTE *)(v6 + 100) & 0x20) != 0 || *((_BYTE *)this + 1592))
        && (unsigned __int8)IsNotifyInputSinkParentedPresent() )
      {
        TopByReference = (_QWORD *)CWatermarkStack<CBspNode *,64,2,10>::GetTopByReference((char *)this + 1152);
        NotifyInputSinkParented(InputHandle, *TopByReference);
      }
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Comp_Racy>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Comp_Racy>::GetImpl'::`2'::impl);
      v62 = *(_BYTE *)(v6 + 100) & 0x20;
      if ( IsEnabled )
      {
        if ( v62 || CTreeData::WorldTransformChangedInCurrentFrame(v58) )
        {
          memset_0(&v80, 0, 0x48u);
          v80 = InputHandle;
          CopyInputTransform((CTreeData *)((char *)v58 + 272), (struct tagINPUT_TRANSFORM *)v81);
          v63 = DynArray<COMPOSITION_INPUT_SINK_TRANSFORM,0>::AddMultipleAndSet((char *)this + 1488, &v80);
          if ( v63 < 0 )
          {
            v64 = 1238;
LABEL_110:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v64,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
              (const char *)(unsigned int)v63,
              v72);
            return (unsigned int)v63;
          }
LABEL_111:
          if ( (unsigned __int8)IsNotifyInputSinkTransformChangedPresent() )
            NotifyInputSinkTransformChanged(InputHandle, v81);
        }
      }
      else if ( v62 || CTreeData::WorldTransformChangedInCurrentFrame(v58) )
      {
        memset_0(&v80, 0, 0x48u);
        v80 = InputHandle;
        CopyInputTransform((CTreeData *)((char *)v58 + 272), (struct tagINPUT_TRANSFORM *)v81);
        v63 = DynArray<COMPOSITION_INPUT_SINK_TRANSFORM,0>::AddMultipleAndSet((char *)this + 1488, &v80);
        if ( v63 < 0 )
        {
          v64 = 1258;
          goto LABEL_110;
        }
        goto LABEL_111;
      }
    }
    *(_BYTE *)(v6 + 100) &= ~0x20u;
  }
  v65 = *(CPreComputeSubTreeContext **)this;
  v66 = (CPreComputeSubTreeContext *)*((_QWORD *)this + 1);
  while ( v65 != v66 )
  {
    Parent = CPreComputeSubTreeContext::GetParent(v65, (struct CVisual *)v6);
    v70 = CBspPreComputeHelper::PreComputePostSubgraph(v69, v68, Parent);
    v71 = v70;
    if ( v70 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4FC,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\precomputecontext.cpp",
        (const char *)(unsigned int)v70,
        v72);
      return v71;
    }
    v65 = (CPreComputeSubTreeContext *)((char *)v65 + 352);
  }
  if ( (*(_DWORD *)(v6 + 96) & 0x20000000) != 0 )
    CWatermarkStack<D2D_VECTOR_2F,2,2,10>::Pop((char *)this + 1080);
  if ( CVisual::Has3DContent((CVisual *)v6) )
    --*(_DWORD *)(v10 + 336);
  *(_BYTE *)(v6 + 100) &= 0xE0u;
  *(_BYTE *)(v6 + 96) = 0;
  if ( *(_QWORD *)(*(_QWORD *)(v10 + 328) + 72LL) != v6 )
    return 0;
  CPreComputeSubTreeContext::EndWalk((CPreComputeSubTreeContext *)v10, 0);
LABEL_125:
  detail::vector_facade<CPreComputeSubTreeContext,detail::buffer_impl<CPreComputeSubTreeContext,3,1,detail::liberal_expansion_policy>>::pop_back(this);
  return 0;
}

```

## disassembly

```asm
0x18003582c  mov     rax, rsp
0x18003582f  mov     [rax+20h], rbx
0x180035833  push    rbp
0x180035834  push    rsi
0x180035835  push    rdi
0x180035836  push    r12
0x180035838  push    r13
0x18003583a  push    r14
0x18003583c  push    r15
0x18003583e  lea     rbp, [rsp-50h]
0x180035843  sub     rsp, 150h
0x18003584a  movaps  xmmword ptr [rax-48h], xmm6
0x18003584e  movaps  xmmword ptr [rax-58h], xmm7
0x180035852  movaps  xmmword ptr [rax-68h], xmm8
0x180035857  mov     rax, cs:__security_cookie
0x18003585e  xor     rax, rsp
0x180035861  mov     [rbp+80h+var_70], rax
0x180035865  mov     r12, [rcx+600h]
0x18003586c  xor     eax, eax
0x18003586e  mov     r13, [rcx+8]
0x180035872  mov     r14, rcx
0x180035875  mov     rsi, [rcx+5F8h]
0x18003587c  mov     rbx, r8
0x18003587f  mov     [rsp+180h+var_110], rax
0x180035884  mov     rcx, rdx
0x180035887  mov     rax, [rdx]
0x18003588a  mov     r15, rdx
0x18003588d  mov     [rsp+180h+var_108], r12
0x180035892  add     r13, 0FFFFFFFFFFFFFEA0h
0x180035899  mov     rax, [rax+0C0h]
0x1800358a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358a5  test    al, al
0x1800358a7  jz      short loc_1800358B9
0x1800358a9  mov     rdx, r15; struct CVisualTree *
0x1800358ac  mov     rcx, rsi; this
0x1800358af  call    ?FindTreeData@CVisual@@QEBAPEAVCTreeData@@PEBVCVisualTree@@@Z; CVisual::FindTreeData(CVisualTree const *)
0x1800358b4  mov     [rsp+180h+var_110], rax
0x1800358b9  mov     byte ptr [rbx], 1
0x1800358bc  cmp     byte ptr [r13+159h], 0
0x1800358c4  jnz     loc_1800360B0
0x1800358ca  lea     rcx, [r14+498h]; this
0x1800358d1  mov     r8, r15; struct CVisualTree *
0x1800358d4  mov     rdx, rsi; struct CVisual *
0x1800358d7  call    ?PopLightsFromVisual@CLightStack@@QEAAJPEBVCVisual@@PEBVCVisualTree@@@Z; CLightStack::PopLightsFromVisual(CVisual const *,CVisualTree const *)
0x1800358dc  mov     ebx, eax
0x1800358de  test    eax, eax
0x1800358e0  jns     short loc_180035904
0x1800358e2  mov     edx, 383h; void *
0x1800358e7  mov     rcx, [rbp+88h]; this
0x1800358ee  lea     r8, aOnecoreuapWind_217; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x1800358f5  mov     r9d, ebx; char *
0x1800358f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358fd  mov     eax, ebx
0x1800358ff  jmp     loc_1800360BA
0x180035904  mov     al, [rsi+60h]
0x180035907  mov     [rsp+180h+var_130], 0
0x18003590c  test    al, 1
0x18003590e  jz      loc_180035B7E
0x180035914  mov     rcx, rsi; this
0x180035917  call    ?ResolveTransformParent@CVisual@@IEBA_NPEBVCVisualTree@@@Z; CVisual::ResolveTransformParent(CVisualTree const *)
0x18003591c  test    al, al
0x18003591e  jz      short loc_18003595C
0x180035920  mov     rdx, r15; struct CVisualTree *
0x180035923  mov     rcx, rsi; this
0x180035926  call    ?GetTransformParent@CVisual@@QEBAPEBV1@PEBVCVisualTree@@PEA_N@Z; CVisual::GetTransformParent(CVisualTree const *,bool *)
0x18003592b  mov     rbx, [r14]
0x18003592e  mov     r12, rax
0x180035931  mov     rdi, [r14+8]
0x180035935  cmp     rbx, rdi
0x180035938  jz      short loc_180035964
0x18003593a  mov     rdx, [rbx+148h]; struct CVisualTree *
0x180035941  mov     rcx, rsi; this
0x180035944  call    ?GetTransformParent@CVisual@@QEBAPEBV1@PEBVCVisualTree@@PEA_N@Z; CVisual::GetTransformParent(CVisualTree const *,bool *)
0x180035949  cmp     r12, rax
0x18003594c  jnz     short loc_180035957
0x18003594e  add     rbx, 160h
0x180035955  jmp     short loc_180035935
0x180035957  mov     r9b, 1
0x18003595a  jmp     short loc_180035969
0x18003595c  xor     r12d, r12d
0x18003595f  mov     r9b, r12b
0x180035962  jmp     short loc_180035969
0x180035964  mov     r9b, [rsp+180h+var_130]; bool
0x180035969  mov     r8, r12; struct CVisual *
0x18003596c  mov     rdx, r15; struct CVisualTree *
0x18003596f  mov     rcx, rsi; this
0x180035972  call    ?ConvertInnerToOuterBounds@CVisual@@IEAAJPEBVCVisualTree@@PEAV1@_N@Z; CVisual::ConvertInnerToOuterBounds(CVisualTree const *,CVisual *,bool)
0x180035977  mov     ebx, eax
0x180035979  test    eax, eax
0x18003597b  jns     short loc_180035987
0x18003597d  mov     edx, 3A2h
0x180035982  jmp     loc_1800358E7
0x180035987  cmp     cs:?EnableDwmMoveRectHints@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, 0; details::CRegistryKey<bool,bool> const CCommonRegistryData::EnableDwmMoveRectHints
0x18003598e  mov     [rsp+180h+var_130], 1
0x180035993  jz      loc_180035B72
0x180035999  mov     rax, [r15]
0x18003599c  mov     rcx, r15
0x18003599f  mov     rax, [rax+0C0h]
0x1800359a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359ab  test    al, al
0x1800359ad  jz      loc_180035B72
0x1800359b3  xorps   xmm1, xmm1
0x1800359b6  lea     rcx, [r14+598h]
0x1800359bd  movups  [rbp+80h+var_100+8], xmm1
0x1800359c1  xor     eax, eax
0x1800359c3  lea     r8, [rbp+80h+var_E0]
0x1800359c7  unpckhpd xmm1, xmm1
0x1800359cb  lea     rdx, [rbp+80h+var_100]
0x1800359cf  mov     qword ptr [rbp+80h+var_100], rax
0x1800359d3  movups  xmm0, [rbp+80h+var_100]
0x1800359d7  movsd   [rbp+80h+var_D0], xmm1
0x1800359dc  movaps  [rbp+80h+var_E0], xmm0
0x1800359e0  call    ?TopOrDefault@?$CWatermarkStack@UMoveBounds@MoveRectHintData@CPreComputeContext@@$0EA@$01$09@@QEBA?AUMoveBounds@MoveRectHintData@CPreComputeContext@@U234@@Z; CWatermarkStack<CPreComputeContext::MoveRectHintData::MoveBounds,64,2,10>::TopOrDefault(CPreComputeContext::MoveRectHintData::MoveBounds)
0x1800359e5  cmp     qword ptr [rbp+80h+var_100], rsi
0x1800359e9  jnz     loc_180035B72
0x1800359ef  movss   xmm0, [rbp+80h+var_F0]
0x1800359f4  movss   xmm5, dword ptr [rsi+90h]
0x1800359fc  movss   xmm4, dword ptr [rsi+98h]
0x180035a04  movss   xmm2, dword ptr [rbp+80h+var_100+8]
0x180035a09  subss   xmm4, xmm5
0x180035a0d  movdqa  xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180035a15  subss   xmm0, xmm2
0x180035a19  movss   xmm8, cs:__real@38aaaaab
0x180035a22  subss   xmm0, xmm4
0x180035a26  andps   xmm0, xmm1
0x180035a29  comiss  xmm8, xmm0
0x180035a2d  jb      loc_180035B5E
0x180035a33  movss   xmm0, [rbp+80h+var_EC]
0x180035a38  movss   xmm7, dword ptr [rsi+94h]
0x180035a40  movss   xmm6, dword ptr [rsi+9Ch]
0x180035a48  movss   xmm3, dword ptr [rbp+80h+var_100+0Ch]
0x180035a4d  subss   xmm6, xmm7
0x180035a51  subss   xmm0, xmm3
0x180035a55  subss   xmm0, xmm6
0x180035a59  andps   xmm0, xmm1
0x180035a5c  comiss  xmm8, xmm0
0x180035a60  jb      loc_180035B5E
0x180035a66  movaps  xmm0, xmm2
0x180035a69  subss   xmm0, xmm5
0x180035a6d  andps   xmm0, xmm1
0x180035a70  comiss  xmm8, xmm0
0x180035a74  jb      short loc_180035A8A
0x180035a76  movaps  xmm0, xmm3
0x180035a79  subss   xmm0, xmm7
0x180035a7d  andps   xmm0, xmm1
0x180035a80  comiss  xmm8, xmm0
0x180035a84  jnb     loc_180035B5E
0x180035a8a  mov     al, [r14+5C8h]
0x180035a91  test    al, al
0x180035a93  jz      short loc_180035AB3
0x180035a95  movss   xmm0, dword ptr [r14+5C4h]
0x180035a9e  movaps  xmm1, xmm6
0x180035aa1  mulss   xmm0, dword ptr [r14+5C0h]
0x180035aaa  mulss   xmm1, xmm4
0x180035aae  comiss  xmm1, xmm0
0x180035ab1  jbe     short loc_180035AF8
0x180035ab3  movss   dword ptr [r14+5B0h], xmm2
0x180035abc  mov     cl, 1
0x180035abe  movss   dword ptr [r14+5B4h], xmm3
0x180035ac7  movss   dword ptr [r14+5B8h], xmm5
0x180035ad0  movss   dword ptr [r14+5BCh], xmm7
0x180035ad9  movss   dword ptr [r14+5C0h], xmm4
0x180035ae2  movss   dword ptr [r14+5C4h], xmm6
0x180035aeb  test    al, al
0x180035aed  jnz     short loc_180035AFA
0x180035aef  mov     [r14+5C8h], cl
0x180035af6  jmp     short loc_180035AFA
0x180035af8  xor     cl, cl
0x180035afa  mov     al, byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits
0x180035b00  and     al, 20h
0x180035b02  mov     byte ptr [rsp+180h+var_128], al
0x180035b06  jz      short loc_180035B5E
0x180035b08  lea     rax, [rsp+180h+var_128]
0x180035b0d  movzx   r9d, cl
0x180035b11  mov     [rsp+180h+var_138], rax
0x180035b16  subss   xmm5, xmm2
0x180035b1a  subss   xmm7, xmm3
0x180035b1e  movss   [rsp+180h+var_120], xmm2
0x180035b24  lea     rax, [rsp+180h+var_118]
0x180035b29  movss   [rsp+180h+var_11C], xmm3
0x180035b2f  mov     [rsp+180h+var_148], rax
0x180035b34  mov     r8, rsi
0x180035b37  lea     rax, [rsp+180h+var_120]
0x180035b3c  movss   [rsp+180h+var_128], xmm4
0x180035b42  mov     [rsp+180h+var_158], rax
0x180035b47  movss   [rsp+180h+var_118], xmm5
0x180035b4d  movss   [rsp+180h+var_114], xmm7
0x180035b53  movss   [rsp+180h+var_124], xmm6
0x180035b59  call    McTemplateU0xtnnn_EventWriteTransfer
0x180035b5e  mov     eax, [r14+5A0h]
0x180035b65  test    eax, eax
0x180035b67  jz      short loc_180035B72
0x180035b69  dec     eax
0x180035b6b  mov     [r14+5A0h], eax
0x180035b72  and     byte ptr [rsi+60h], 0FEh
0x180035b76  mov     al, [rsi+60h]
0x180035b79  mov     r12, [rsp+180h+var_108]
0x180035b7e  test    al, 10h
0x180035b80  jz      loc_180035C4C
0x180035b86  mov     rax, [rsi]
0x180035b89  mov     rcx, rsi
0x180035b8c  mov     ebx, [rsi+60h]
0x180035b8f  shl     ebx, 0Fh
0x180035b92  sar     ebx, 17h
0x180035b95  mov     rax, [rax+110h]
0x180035b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ba1  test    al, al
0x180035ba3  jz      short loc_180035BC7
0x180035ba5  test    bl, 1
0x180035ba8  jnz     short loc_180035BC3
0x180035baa  mov     rcx, rsi; this
0x180035bad  call    ?HasSingleD2DBitmapOrPrimitiveGroup@CVisual@@QEBA_NXZ; CVisual::HasSingleD2DBitmapOrPrimitiveGroup(void)
0x180035bb2  test    al, al
0x180035bb4  jnz     short loc_180035BBE
0x180035bb6  or      ebx, 101h
0x180035bbc  jmp     short loc_180035BC7
0x180035bbe  or      ebx, 1
0x180035bc1  jmp     short loc_180035BC7
0x180035bc3  bts     ebx, 8
0x180035bc7  mov     rcx, rsi; this
0x180035bca  call    ?Has3DContent@CVisual@@IEBA_NXZ; CVisual::Has3DContent(void)
0x180035bcf  mov     edi, ebx
0x180035bd1  mov     rcx, rsi
0x180035bd4  or      edi, 2
0x180035bd7  test    al, al
0x180035bd9  mov     rax, [rsi]
0x180035bdc  cmovz   edi, ebx
0x180035bdf  mov     rax, [rax+158h]
0x180035be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035beb  mov     ebx, edi
0x180035bed  mov     rcx, rsi; this
0x180035bf0  or      ebx, 4
0x180035bf3  test    al, al
0x180035bf5  cmovz   ebx, edi
0x180035bf8  call    ?HasPixelSnappedContent@CVisual@@IEBA_NXZ; CVisual::HasPixelSnappedContent(void)
0x180035bfd  mov     r10d, ebx
0x180035c00  mov     rcx, rsi; this
0x180035c03  or      r10d, 8
0x180035c07  test    al, al
0x180035c09  cmovz   r10d, ebx
0x180035c0d  call    ?HasInputSink@CVisual@@QEBA_NXZ; CVisual::HasInputSink(void)
0x180035c12  mov     ebx, r10d
0x180035c15  mov     rcx, rsi
0x180035c18  or      ebx, 10h
0x180035c1b  test    al, al
0x180035c1d  mov     rax, [rsi]
0x180035c20  cmovz   ebx, r10d
0x180035c24  mov     rax, [rax+118h]
0x180035c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c30  mov     ecx, ebx
0x180035c32  or      ecx, 40h
0x180035c35  test    al, al
0x180035c37  cmovz   ecx, ebx
0x180035c3a  shl     ecx, 8
0x180035c3d  mov     eax, ecx
0x180035c3f  xor     eax, [rsi+60h]
0x180035c42  and     eax, 0FFFE00FFh
0x180035c47  xor     eax, ecx
0x180035c49  mov     [rsi+60h], eax
0x180035c4c  test    r12, r12
0x180035c4f  jz      short loc_180035CD0
0x180035c51  mov     rcx, rsi; this
0x180035c54  call    ?HasInputSink@CVisual@@QEBA_NXZ; CVisual::HasInputSink(void)
0x180035c59  mov     r8d, [r12+60h]
0x180035c5e  mov     ecx, 20h ; ' '
0x180035c63  movzx   r10d, al
0x180035c67  mov     eax, r8d
0x180035c6a  shl     r10d, 5
0x180035c6e  test    byte ptr [rsi+66h], 4
0x180035c72  cmovz   ecx, r10d
0x180035c76  mov     edx, ecx
0x180035c78  bts     edx, 7
0x180035c7c  test    dword ptr [rsi+60h], 60000h
0x180035c83  cmovz   edx, ecx
0x180035c86  and     eax, [rsi+60h]
0x180035c89  bt      eax, 8
0x180035c8d  mov     ecx, edx
0x180035c8f  setb    al
0x180035c92  bts     ecx, 8
0x180035c96  test    al, al
0x180035c98  cmovz   ecx, edx
0x180035c9b  shl     ecx, 8
0x180035c9e  or      ecx, r8d
0x180035ca1  or      ecx, [rsi+60h]
0x180035ca4  xor     r8d, ecx
0x180035ca7  and     r8d, 0FFFE00FFh
0x180035cae  xor     r8d, ecx
0x180035cb1  mov     [r12+60h], r8d
0x180035cb6  test    r8b, 1
0x180035cba  jz      short loc_180035CD0
0x180035cbc  lea     rdx, [rsi+90h]
0x180035cc3  lea     rcx, [r12+0A8h]
0x180035ccb  call    ?UnionUnsafe@?$TMil3DRect@MV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@UD3D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@QEAA_NAEBV1@@Z; TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>::UnionUnsafe(TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded> const &)
0x180035cd0  test    byte ptr [rsi+67h], 2
0x180035cd4  jz      short loc_180035CF4
0x180035cd6  mov     rdx, rsi; struct CVisual *
0x180035cd9  mov     rcx, r14; this
0x180035cdc  call    ?ProcessPostSubgraphWindowBackdropInput@CPreComputeContext@@AEAAJPEAVCVisual@@@Z; CPreComputeContext::ProcessPostSubgraphWindowBackdropInput(CVisual *)
0x180035ce1  xor     r12d, r12d
0x180035ce4  mov     ebx, eax
  ... truncated ...
```
