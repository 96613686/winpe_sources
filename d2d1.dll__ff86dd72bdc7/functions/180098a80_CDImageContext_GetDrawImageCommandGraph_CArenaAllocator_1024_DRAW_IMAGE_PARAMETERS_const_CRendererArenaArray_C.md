# CDImageContext::GetDrawImageCommandGraph(CArenaAllocator<1024> *,DRAW_IMAGE_PARAMETERS const &,CRendererArenaArray<CRefCountPtr<BitmapRealization>,CDefaultTraits<CRefCountPtr<BitmapRealization>>> &,tagRECT *,CRenderIntermediate * *,uint *)

- ea: `0x180098a80`
- end: `0x180099a03`
- name: `?GetDrawImageCommandGraph@CDImageContext@@QEAAJPEAV?$CArenaAllocator@$0EAA@@@AEBUDRAW_IMAGE_PARAMETERS@@AEAV?$CRendererArenaArray@V?$CRefCountPtr@VBitmapRealization@@@@V?$CDefaultTraits@V?$CRefCountPtr@VBitmapRealization@@@@@@@@PEAUtagRECT@@PEAPEAVCRenderIntermediate@@PEAI@Z`
- size: `3971`
- prototype: `__int64 __usercall@<rax>(CDImageContext *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `39`
- tags: `broker_com_uri`

## callers

- `0x180096f00`

## callees

- `0x18001fd58`
- `0x1800379e0`
- `0x180092ca0`
- `0x180094f74`
- `0x180094fa0`
- `0x18009584c`
- `0x1800969a0`
- `0x180097820`
- `0x180097920`
- `0x1800980d0`
- `0x18009869c`
- `0x1800986dc`
- `0x18009872c`
- `0x180098800`
- `0x180098830`
- `0x180098980`
- `0x1800989c0`
- `0x180098a14`
- `0x180098a80`
- `0x180099d50`
- `0x18009bb60`
- `0x1800a0130`
- `0x1800a5dc0`
- `0x1800ac5ac`
- `0x1800b1cac`
- `0x1800b46b4`
- `0x1800c88e0`
- `0x1800fabac`
- `0x1801008a0`
- `0x180100930`
- `0x180120cf0`
- `0x180128c50`
- `0x18015e854`
- `0x18017a5c0`
- `0x1801866f0`
- `0x1801bb8b4`
- `0x18025b100`
- `0x18025c979`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009922d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800996a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180099751`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009990e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009922d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800996a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180099751`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009990e`

## pseudocode

```c
__int64 __fastcall CDImageContext::GetDrawImageCommandGraph(
        CDImageContext *this,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        struct tagRECT *a5,
        struct tagPOINT *a6,
        unsigned int *a7)
{
  __int64 v9; // r12
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // xmm0_8
  unsigned int v13; // r13d
  int v14; // xmm1_4
  int v15; // eax
  void (__fastcall ***v16)(_QWORD); // rbx
  struct tagPOINT v17; // rcx
  LONG v18; // r10d
  __int64 v19; // r9
  unsigned __int64 v20; // r9
  LONG left; // edx
  LONG right; // r8d
  int v23; // eax
  LONG v24; // ecx
  LONG v25; // eax
  LONG y; // r8d
  unsigned __int64 v27; // r9
  LONG top; // ecx
  LONG bottom; // edx
  int v30; // r9d
  LONG v31; // eax
  void (__fastcall ***v32)(_QWORD); // rbx
  struct IBrushRedirection **v33; // r15
  __int64 v34; // rbx
  int v35; // edi
  const struct D2D_MATRIX_3X2_F *v36; // rdx
  struct D2D_MATRIX_3X2_F *v37; // rbx
  unsigned int v38; // edi
  struct ICommandListInternal *v39; // rax
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rdi
  int v43; // eax
  int v44; // ebx
  unsigned int v45; // r12d
  unsigned int v46; // eax
  unsigned int *v47; // r15
  unsigned __int64 v48; // r8
  unsigned __int64 v49; // rbx
  int UnresolvedRootIntermediateForTile; // edi
  __int64 v51; // rcx
  unsigned __int64 v52; // r9
  __int64 v53; // r8
  char v54; // r11
  __int64 v55; // rdx
  __int64 v56; // r10
  struct tagPOINT v57; // r13
  struct BitmapRealization *AllocationNoRef; // rax
  struct BitmapRealization *v59; // rax
  _BYTE *v60; // rax
  int v61; // ebx
  __int64 i; // rbx
  __int64 result; // rax
  unsigned int *v64; // rcx
  char v65; // r15
  unsigned int v66; // ecx
  int OcclusionRect; // eax
  unsigned int v68; // ecx
  __int64 v69; // rdx
  char v70; // bl
  unsigned int k; // edi
  unsigned int v72; // ebx
  _QWORD **v73; // r9
  int v74; // eax
  __int64 v75; // rcx
  const struct D2D1_BLEND_DESCRIPTION *v76; // rdi
  struct tagPOINT v77; // rsi
  int v78; // edx
  int v79; // eax
  int v80; // r9d
  unsigned int v81; // r8d
  unsigned int v82; // r11d
  unsigned int BoundingPow2; // eax
  unsigned int v84; // r9d
  unsigned int v85; // r10d
  unsigned int v86; // ecx
  unsigned int v87; // eax
  __int64 j; // rbx
  CDImageContext *v89; // rdx
  __int64 v90; // rcx
  int v91; // eax
  CDImageContext *v92; // rcx
  int v93; // eax
  CDImageContext *v94; // rcx
  int v95; // eax
  int v96; // eax
  CDImageContext *v97; // rcx
  unsigned int m; // ebx
  __int64 v99; // rcx
  int v100; // eax
  unsigned int v101; // ebx
  int v102; // eax
  CDImageContext *v103; // rcx
  __int64 *v104; // rsi
  unsigned int **v105; // rbx
  int v106; // ecx
  unsigned int v107; // eax
  unsigned int **v108; // rcx
  char *v109; // rsi
  CDImageContext *v110; // rcx
  __int64 *v111; // rcx
  __int64 v112; // rax
  unsigned int v113; // r9d
  __int64 v114; // rdx
  __int64 v115; // rcx
  int v116; // [rsp+40h] [rbp-C0h] BYREF
  bool v117; // [rsp+44h] [rbp-BCh] BYREF
  struct tagPOINT v118; // [rsp+48h] [rbp-B8h] BYREF
  CDImageContext *v119; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v120; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  __int64 v122; // [rsp+70h] [rbp-90h]
  unsigned int v123; // [rsp+80h] [rbp-80h]
  struct tagRECT v124; // [rsp+88h] [rbp-78h] BYREF
  __int64 v125; // [rsp+98h] [rbp-68h]
  __int64 *v126; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v127; // [rsp+A8h] [rbp-58h] BYREF
  CDImageContext *v128; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v129; // [rsp+B8h] [rbp-48h]
  int v130; // [rsp+C0h] [rbp-40h]
  __int64 v131; // [rsp+C4h] [rbp-3Ch]
  int v132; // [rsp+CCh] [rbp-34h]
  int v133; // [rsp+D0h] [rbp-30h]
  int v134; // [rsp+D4h] [rbp-2Ch]
  int v135; // [rsp+D8h] [rbp-28h]
  __int64 v136; // [rsp+E8h] [rbp-18h]
  char v137; // [rsp+F0h] [rbp-10h]
  struct tagRECT *v138; // [rsp+100h] [rbp+0h]
  struct tagPOINT *v139; // [rsp+108h] [rbp+8h]
  char v140[8]; // [rsp+110h] [rbp+10h] BYREF
  CDImageContext *v141; // [rsp+118h] [rbp+18h]
  unsigned int v142; // [rsp+120h] [rbp+20h]
  int *v143; // [rsp+128h] [rbp+28h]
  _BYTE v144[16]; // [rsp+130h] [rbp+30h] BYREF
  char *v145; // [rsp+140h] [rbp+40h] BYREF
  int v146; // [rsp+148h] [rbp+48h]
  int v147; // [rsp+14Ch] [rbp+4Ch]
  char v148; // [rsp+150h] [rbp+50h]
  char v149; // [rsp+151h] [rbp+51h] BYREF
  _QWORD v150[2]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v151[3]; // [rsp+230h] [rbp+130h] BYREF
  char v152; // [rsp+248h] [rbp+148h]
  int v153; // [rsp+24Ch] [rbp+14Ch]
  int v154; // [rsp+250h] [rbp+150h]
  int v155; // [rsp+254h] [rbp+154h]
  int v156; // [rsp+258h] [rbp+158h]
  char v157; // [rsp+267h] [rbp+167h]
  int v158; // [rsp+268h] [rbp+168h]
  int v159; // [rsp+26Ch] [rbp+16Ch]
  int v160; // [rsp+270h] [rbp+170h]
  int v161; // [rsp+274h] [rbp+174h]
  int v162; // [rsp+278h] [rbp+178h]
  int v163; // [rsp+27Ch] [rbp+17Ch]
  int v164; // [rsp+280h] [rbp+180h]
  int v165; // [rsp+284h] [rbp+184h]
  _BYTE v166[16]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v167; // [rsp+2E0h] [rbp+1E0h]
  _QWORD v168[9]; // [rsp+2E8h] [rbp+1E8h] BYREF
  CDImageContext *v169; // [rsp+330h] [rbp+230h] BYREF
  int v170; // [rsp+340h] [rbp+240h]
  __int64 v171; // [rsp+480h] [rbp+380h]
  char v172[104]; // [rsp+488h] [rbp+388h] BYREF
  char v173[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v174[432]; // [rsp+4F8h] [rbp+3F8h] BYREF
  _BYTE v175[48]; // [rsp+6A8h] [rbp+5A8h] BYREF
  _BYTE v176[544]; // [rsp+6D8h] [rbp+5D8h] BYREF
  _BYTE v177[568]; // [rsp+8F8h] [rbp+7F8h] BYREF

  v138 = a5;
  v126 = a4;
  v139 = a6;
  v127 = a7;
  *a6 = 0;
  *a7 = 0;
  v116 = 0;
  v119 = this;
  *a5 = g_emptyRectL;
  v9 = *((_QWORD *)this + 587);
  v125 = v9;
  v120 = 0;
  *((_QWORD *)this + 587) = a2;
  v10 = CDImageContext::CReentrancyCycleGuard::Initialize((CDImageContext::CReentrancyCycleGuard *)&v119);
  v11 = v10;
  if ( v10 < 0 )
  {
    DoStackCapture(v10);
    v116 = v11;
    if ( (_QWORD)v120 )
    {
      v89 = v119;
      v90 = *((_QWORD *)&v120 + 1);
      *(_BYTE *)(v120 + 16) = 0;
      *((_QWORD *)v89 + 38) = v90;
    }
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v120 + 8);
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v120);
    result = v11;
    *((_QWORD *)this + 587) = v9;
    return result;
  }
  v129 = *((_QWORD *)this + 39);
  v116 = v10;
  v128 = this;
  SafeAddRef<RefCountedObject<CMultiProcessElementBase,LockingRequired,DeleteOnZeroReference>>(v129);
  v12 = *((_QWORD *)this + 25);
  v13 = *((_DWORD *)this + 1180);
  v14 = *((_DWORD *)this + 58);
  v130 = *((_DWORD *)this + 80);
  v132 = *((_DWORD *)this + 52);
  v133 = *((_DWORD *)this + 59);
  v136 = *((_QWORD *)this + 42);
  v137 = *((_BYTE *)this + 4760);
  v131 = v12;
  LODWORD(v12) = *((_DWORD *)this + 57);
  v143 = &v116;
  v134 = v12;
  v135 = v14;
  v141 = this;
  v123 = v13;
  v142 = v13;
  CInputTransformNode::CInputTransformNode((CInputTransformNode *)v166);
  CBrushTransformNode::CBrushTransformNode((CBrushTransformNode *)v173);
  v15 = *(_DWORD *)(a3 + 84);
  *((_DWORD *)this + 58) = *(_DWORD *)(a3 + 88);
  *((_DWORD *)this + 57) = v15;
  *((_DWORD *)this + 59) = *(_DWORD *)(a3 + 80);
  *((_BYTE *)this + 4688) = 1;
  v16 = *(void (__fastcall ****)(_QWORD))a3;
  win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)this + 312);
  *((_QWORD *)this + 39) = v16;
  if ( v16 )
    (**v16)(v16);
  *((_DWORD *)this + 80) = *(_DWORD *)(a3 + 56);
  *((_QWORD *)this + 25) = *(_QWORD *)(a3 + 60);
  *((_DWORD *)this + 52) = *(_DWORD *)(a3 + 68);
  if ( !*((_BYTE *)this + 330) )
    *(struct D2D_SIZE_U *)((char *)this + 4636) = GetMinAllocationSize(*(struct D2D_SIZE_U *)((char *)this + 204));
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 8) + 168LL))(*(_QWORD *)(a3 + 8)) )
  {
    v118 = 0;
    v124 = g_emptyRectL;
    goto LABEL_29;
  }
  v17 = *(struct tagPOINT *)(a3 + 16);
  v18 = 0x7FFFFFFF;
  v19 = *((_QWORD *)this + 39);
  v118 = v17;
  v20 = *(_QWORD *)(v19 + 84);
  v124 = *(struct tagRECT *)(a3 + 24);
  if ( v17.x < 0 )
  {
    left = ClipAdd(v124.left, -v17.x);
    v124.left = left;
    v118.x = 0;
    v17.x = 0;
  }
  else
  {
    if ( v17.x >= (int)v20 )
    {
      v124.right = 0;
      v124.left = 0;
      v118.x = 0;
      goto LABEL_18;
    }
    left = v124.left;
  }
  right = left;
  if ( left <= v124.right )
    right = v124.right;
  v23 = v20 - v17.x;
  v24 = left + v20 - v17.x;
  if ( v23 < 0 )
  {
    v25 = 0x80000000;
    if ( v24 <= left )
      v25 = v24;
  }
  else
  {
    v25 = v18;
    if ( v24 >= left )
      v25 = v24;
  }
  if ( right < v25 )
    v25 = right;
  v124.right = v25;
LABEL_18:
  y = v118.y;
  v27 = HIDWORD(v20);
  if ( v118.y < 0 )
  {
    top = ClipAdd(v124.top, -v118.y);
    v124.top = top;
    y = 0;
    v118.y = 0;
  }
  else
  {
    if ( v118.y >= (int)v27 )
    {
      v124.bottom = 0;
      v124.top = 0;
      v118.y = 0;
      goto LABEL_29;
    }
    top = v124.top;
  }
  bottom = top;
  if ( top <= v124.bottom )
    bottom = v124.bottom;
  v30 = v27 - y;
  v31 = top + v30;
  if ( v30 < 0 )
  {
    v18 = 0x80000000;
    if ( v31 <= top )
      v18 = top + v30;
  }
  else if ( v31 >= top )
  {
    v18 = top + v30;
  }
  if ( bottom < v18 )
    v18 = bottom;
  v124.bottom = v18;
LABEL_29:
  v32 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 37);
  v168[1] = *((_QWORD *)this + 594);
  v167 = 0;
  win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(v168);
  v168[0] = v32;
  if ( v32 )
    (**v32)(v32);
  win_scope::com_ptr<ID3D11DepthStencilState *>::~com_ptr<ID3D11DepthStencilState *>(&v169);
  v169 = this;
  (*(void (__fastcall **)(CDImageContext *))(*(_QWORD *)this + 8LL))(this);
  v168[4] = 0;
  v33 = *(struct IBrushRedirection ***)(a3 + 96);
  v170 = 3;
  if ( v33 )
  {
    v37 = *(struct D2D_MATRIX_3X2_F **)(a3 + 112);
    v38 = *(_DWORD *)(a3 + 104);
    v39 = (struct ICommandListInternal *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 8) + 120LL))(*(_QWORD *)(a3 + 8));
    v40 = CBrushTransformNode::Initialize((CBrushTransformNode *)v173, this, v39, v33, v38, v37);
    v35 = v40;
    if ( v40 < 0 )
    {
      DoStackCapture(v40);
      goto LABEL_120;
    }
    v41 = v171;
    if ( v171 )
    {
      v171 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    CRefCountPtr<CTickCounter>::operator=(v172, v174);
  }
  else
  {
    v34 = *(_QWORD *)(a3 + 8);
    v35 = 0;
    if ( v34 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v34 + 8LL))(*(_QWORD *)(a3 + 8));
    if ( v171 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v171 + 16LL))(v171);
    v36 = *(const struct D2D_MATRIX_3X2_F **)(a3 + 112);
    v171 = v34;
    if ( v36 )
      CInputTransformNode::SetExtraInputTransform((CInputTransformNode *)v166, v36);
  }
  if ( v35 < 0 )
  {
LABEL_120:
    DoStackCapture(v35);
    v116 = v35;
    CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
    CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
    CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v140);
    CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
    CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v119);
    result = (unsigned int)v35;
    *((_QWORD *)this + 587) = v9;
    return result;
  }
  v145 = &v149;
  v150[1] = v150;
  v150[0] = v150;
  v116 = v35;
  v42 = *((_QWORD *)this + 596);
  v146 = 0;
  v148 = 0;
  v147 = 25;
  v117 = 0;
  v43 = CDImageContext::InitializeRenderObjects(
          this,
          (struct CTransformNode *)v166,
          &v124,
          &v118,
          (const struct tagRECT *)(a3 + 40),
          (struct CDImageContext::RENDER_STACK_OBJECTS *)v144,
          &v117,
          0xFFFFFFFFFFFFFFFFuLL);
  v44 = v43;
  if ( v43 < 0 )
  {
    DoStackCapture(v43);
    v116 = v44;
    CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
    CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
    CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
    v91 = CDImageContext::EnsureRenderingMode(this, v13);
    if ( v116 >= 0 )
      v116 = v91;
    CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
    if ( (_QWORD)v120 )
    {
      v92 = v119;
      *(_BYTE *)(v120 + 16) = 0;
      *((_QWORD *)v92 + 38) = *((_QWORD *)&v120 + 1);
    }
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v120 + 8);
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v120);
    *((_QWORD *)this + 587) = v9;
    return (unsigned int)v44;
  }
  v116 = v43;
  if ( *((_QWORD *)this + 596) == v42 )
  {
    v45 = 1;
    Block = 0;
    v122 = 0;
    if ( v157 )
      goto LABEL_112;
    v46 = v155 - v153;
    if ( v155 - v153 <= (unsigned int)(v156 - v154) )
      v46 = v156 - v154;
    if ( v46 <= 0x10 )
    {
LABEL_112:
      v47 = (unsigned int *)((char *)this + 204);
      v49 = *((unsigned int *)this + 60) | ((unsigned __int64)*((unsigned int *)this + 60) << 32);
    }
    else
    {
      v47 = (unsigned int *)((char *)this + 204);
      v48 = (unsigned int)(v155 - v153) * (unsigned __int64)(unsigned int)(v156 - v154);
      if ( v48 > 0xFFFFFFFF )
        LODWORD(v48) = -1;
      if ( (unsigned int)v48 <= *((_DWORD *)this + 61) * *((_DWORD *)this + 61) )
      {
        GetBoundingPow2(*v47);
        GetBoundingPow2(*((_DWORD *)this + 52));
        BoundingPow2 = GetBoundingPow2(v82 / v81);
        if ( BoundingPow2 > 1 )
        {
          v86 = BoundingPow2 - 1;
          v87 = *((_DWORD *)this + 60);
          v86 >>= 1;
          v84 <<= v86;
          v85 <<= v86;
          if ( v84 >= v87 )
            v84 = *((_DWORD *)this + 60);
          if ( v85 >= v87 )
            v85 = *((_DWORD *)this + 60);
        }
        v118 = (struct tagPOINT)__PAIR64__(v85, v84);
        v49 = __PAIR64__(v85, v84);
      }
      else
      {
        v49 = *(_QWORD *)v47;
      }
    }
    v118 = 0;
    UnresolvedRootIntermediateForTile = CDImageContext::GetUnresolvedRootIntermediateForTile(
                                          this,
                                          (const struct TILE *)v151,
                                          (struct CRenderIntermediate **)&v118);
    if ( UnresolvedRootIntermediateForTile < 0 )
    {
LABEL_63:
      DoStackCapture(UnresolvedRootIntermediateForTile);
      DoStackCapture(UnresolvedRootIntermediateForTile);
      v116 = UnresolvedRootIntermediateForTile;
      CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>(&Block);
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
      CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v140);
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
      CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v119);
      *((_QWORD *)this + 587) = v125;
      return (unsigned int)UnresolvedRootIntermediateForTile;
    }
    v51 = *((_QWORD *)this + 37);
    v52 = *(_QWORD *)v47;
    v53 = *((_QWORD *)this + 587);
    v54 = v152;
    v55 = *(_QWORD *)(v51 + 8);
    v56 = v151[0];
    v57 = v118;
    *(_QWORD *)(v51 + 8) = v55 + 1;
    *((_QWORD *)this + 53) = v144;
    *((_QWORD *)this + 62) = v55;
    *((_QWORD *)this + 58) = 0;
    *((_BYTE *)this + 472) = 0;
    *((_QWORD *)this + 60) = 0;
    *((_QWORD *)this + 46) = v53;
    *((_QWORD *)this + 63) = v52;
    *((struct tagPOINT *)this + 54) = v57;
    *((_QWORD *)this + 55) = v56;
    *((_BYTE *)this + 448) = v54;
    *((_DWORD *)this + 113) = 3;
    *((_QWORD *)this + 57) = v49;
    AllocationNoRef = CRenderIntermediate::GetAllocationNoRef(*(CRenderIntermediate **)&v57);
    if ( AllocationNoRef )
    {
      v59 = CRenderIntermediate::GetAllocationNoRef(*(CRenderIntermediate **)&v57);
      LOBYTE(AllocationNoRef) = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v59 + 1) + 8LL))((__int64)v59 + 8);
    }
    *((_BYTE *)this + 513) = (_BYTE)AllocationNoRef;
    v60 = (_BYTE *)*((_QWORD *)this + 60);
    if ( v60 )
      *v60 = 0;
    v61 = v146;
    *((_QWORD *)this + 61) = &Block;
    for ( i = (unsigned int)(v61 - 1); ; i = (unsigned int)(i - 1) )
    {
      UnresolvedRootIntermediateForTile = CRenderOperationResolver::ResolveRenderOperationsCallback(
                                            (struct CTransformNode **)this + 44,
                                            *(struct CTransformNode **)&v145[8 * i]);
      if ( UnresolvedRootIntermediateForTile < 0 )
        goto LABEL_62;
      if ( !(_DWORD)i )
        break;
    }
    if ( *((_BYTE *)this + 472) && *((_DWORD *)this + 113) == 1 )
    {
      for ( j = (unsigned int)(v146 - 1); ; j = (unsigned int)(j - 1) )
      {
        UnresolvedRootIntermediateForTile = CRenderOperationResolver::DetermineTilingLocationsCallback(
                                              (CDImageContext *)((char *)this + 352),
                                              *(struct CTransformNode **)&v145[8 * j]);
        if ( UnresolvedRootIntermediateForTile < 0 )
          break;
        if ( !(_DWORD)j )
          goto LABEL_65;
      }
LABEL_62:
      DoStackCapture(UnresolvedRootIntermediateForTile);
      DoStackCapture(UnresolvedRootIntermediateForTile);
      goto LABEL_63;
    }
LABEL_65:
    v64 = v127;
    v65 = *((_BYTE *)this + 472);
    *v127 = *((_DWORD *)this + 116);
    if ( g_pSqm )
    {
      v66 = *v64;
      if ( v66 > *((_DWORD *)g_pSqm + 2) )
        *((_DWORD *)g_pSqm + 2) = v66;
    }
    v116 = UnresolvedRootIntermediateForTile;
    if ( (v159 < v163 || v158 < v162 || v160 > v164 || v161 > v165) && v158 < v160 && v159 < v161 )
    {
      v75 = *((_QWORD *)this + 587);
      v76 = (const struct D2D1_BLEND_DESCRIPTION *)v151[2];
      v118 = 0;
      v44 = CRenderOperation::Create(v75, &v118);
      if ( v44 < 0 )
        goto LABEL_98;
      v77 = v118;
      *(_DWORD *)(*(_QWORD *)&v118 + 123LL) = 2;
      *(_OWORD *)(*(_QWORD *)&v77 + 48LL) = 0;
      *(_DWORD *)(*(_QWORD *)&v77 + 32LL) = 0;
      v78 = v164;
      v79 = v162;
      v80 = v165;
      *(_DWORD *)(*(_QWORD *)&v77 + 52LL) = v163;
      *(_DWORD *)(*(_QWORD *)&v77 + 56LL) = v78;
      *(_DWORD *)(*(_QWORD *)&v77 + 48LL) = v79;
      *(_DWORD *)(*(_QWORD *)&v77 + 60LL) = v80;
      v44 = CRenderOperation::SetTargetParams(*(CRenderOperation **)&v77, *(struct CRenderIntermediate **)&v57, v76);
      if ( v44 < 0 )
        goto LABEL_98;
      v105 = &v127;
      *(_DWORD *)(*(_QWORD *)&v77 + 147LL) = v158;
      *(_DWORD *)(*(_QWORD *)&v77 + 151LL) = v159;
      *(_DWORD *)(*(_QWORD *)&v77 + 155LL) = v160;
      *(_DWORD *)(*(_QWORD *)&v77 + 159LL) = v161;
      v106 = *(_DWORD *)(*(_QWORD *)&v57 + 48LL);
      v127 = (unsigned int *)v77;
      v118 = (struct tagPOINT)&v127;
      if ( v106 )
        v45 = v106 + 1;
      if ( *(_DWORD *)(*(_QWORD *)&v57 + 52LL) < v45 )
      {
        v44 = CArray<CRenderOperation *,CPodTraits<CRenderOperation *>,CIndirectAllocator<CArenaAllocator<1024>>>::EnsureLargerCapacity(
                *(_QWORD *)&v57 + 40LL,
                v45,
                &v118);
        if ( v44 < 0 )
        {
LABEL_98:
          DoStackCapture(v44);
          DoStackCapture(v44);
          v116 = v44;
          CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>(&Block);
          CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
          CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
          CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v140);
          CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
          CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v119);
          goto LABEL_92;
        }
        v105 = (unsigned int **)v118;
      }
      v107 = *(_DWORD *)(*(_QWORD *)&v57 + 48LL);
      if ( v107 )
        memmove_0(
          (void *)(*(_QWORD *)(*(_QWORD *)&v57 + 40LL) + 8LL),
          *(const void **)(*(_QWORD *)&v57 + 40LL),
          8LL * v107);
      v108 = *(unsigned int ***)(*(_QWORD *)&v57 + 40LL);
      *(_DWORD *)(*(_QWORD *)&v57 + 48LL) = v45;
      *v108 = *v105;
    }
    v116 = 0;
    if ( v117 )
    {
      v44 = 0;
    }
    else
    {
      OcclusionRect = CDImageContext::GetOcclusionRect(this, *(struct CRenderIntermediate **)&v57, v138);
      v44 = OcclusionRect;
      if ( OcclusionRect < 0 )
      {
        DoStackCapture(OcclusionRect);
        v116 = v44;
        if ( Block )
        {
          free(Block);
          Block = 0;
          HIDWORD(v122) = 0;
        }
        LODWORD(v122) = 0;
        CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
        CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
        CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v176);
        CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>::~CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>(v175);
        CTransformNode::~CTransformNode((CTransformNode *)v174);
        CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
        v93 = CDImageContext::EnsureRenderingMode(this, v123);
        if ( v116 >= 0 )
          v116 = v93;
        CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
        if ( (_QWORD)v120 )
        {
          v94 = v119;
          *(_BYTE *)(v120 + 16) = 0;
          *((_QWORD *)v94 + 38) = *((_QWORD *)&v120 + 1);
        }
        goto LABEL_91;
      }
      v116 = OcclusionRect;
    }
    if ( v65 )
    {
      if ( Block )
      {
        free(Block);
        Block = 0;
        HIDWORD(v122) = 0;
      }
      LODWORD(v122) = 0;
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
      v95 = CDImageContext::EnsureRenderingMode(this, v123);
      if ( v116 >= 0 )
        v116 = v95;
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
      if ( !(_QWORD)v120 )
        goto LABEL_91;
      *(_BYTE *)(v120 + 16) = 0;
      goto LABEL_90;
    }
    v68 = v122;
    v69 = (unsigned int)(v122 + *((_DWORD *)v126 + 2));
    if ( *((_DWORD *)v126 + 3) >= (unsigned int)v69 )
    {
      v116 = 0;
      goto LABEL_79;
    }
    v100 = CArray<CRefCountPtr<BitmapRealization>,CDefaultTraits<CRefCountPtr<BitmapRealization>>,CIndirectAllocator<CArenaAllocator<1024>>>::EnsureLargerCapacity(
             v126,
             v69,
             0);
    v116 = v100;
    v101 = v100;
    if ( v100 == -2147024882 )
    {
      if ( Block )
      {
        free(Block);
        Block = 0;
        HIDWORD(v122) = 0;
      }
      LODWORD(v122) = 0;
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
      v102 = CDImageContext::EnsureRenderingMode(this, v123);
      if ( v116 >= 0 )
        v116 = v102;
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
      if ( (_QWORD)v120 )
      {
        v103 = v119;
        *(_BYTE *)(v120 + 16) = 0;
        *((_QWORD *)v103 + 38) = *((_QWORD *)&v120 + 1);
      }
      win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v120 + 8);
      win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v120);
      *((_QWORD *)this + 587) = v125;
      return 0;
    }
    else
    {
      if ( v100 >= 0 )
      {
        v68 = v122;
LABEL_79:
        v70 = 1;
        for ( k = 0; k < v68; ++k )
        {
          if ( !v70 )
            goto LABEL_149;
          v109 = (char *)Block + 152 * k;
          v124 = *(struct tagRECT *)(*((_QWORD *)v109 + 13) + 48LL);
          if ( !(unsigned __int8)IsRectEmptyOrWithinRect<tagRECT,tagRECT>(v109 + 112, &v124) )
            goto LABEL_150;
          if ( !CDImageContext::LockCachedTile(v110, (struct TILE *)v109) )
            goto LABEL_149;
          if ( v109[52] && *(_DWORD *)(*(_QWORD *)(**((_QWORD **)v109 + 1) + 64LL) + 112LL) <= 1u )
            v70 = 0;
          v68 = v122;
        }
        if ( !v70 )
        {
LABEL_149:
          v73 = (_QWORD **)Block;
LABEL_150:
          for ( m = 0; m < k; ++m )
          {
            v99 = *v73[19 * m + 1];
            if ( v99 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 24LL))(v99);
              v73 = (_QWORD **)Block;
            }
          }
          goto LABEL_84;
        }
        v72 = 0;
        if ( !v68 )
        {
LABEL_83:
          v73 = (_QWORD **)Block;
          *v139 = v57;
LABEL_84:
          v44 = v116;
          if ( v73 )
          {
            free(v73);
            Block = 0;
            HIDWORD(v122) = 0;
          }
          LODWORD(v122) = 0;
          CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v176);
          CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>::~CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>(v175);
          CTransformNode::~CTransformNode((CTransformNode *)v174);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
          v74 = CDImageContext::EnsureRenderingMode(this, v123);
          if ( v116 >= 0 )
            v116 = v74;
          CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
          if ( !(_QWORD)v120 )
            goto LABEL_91;
          *(_BYTE *)(v120 + 16) = 0;
LABEL_90:
          *((_QWORD *)v119 + 38) = *((_QWORD *)&v120 + 1);
LABEL_91:
          win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v120 + 8);
          win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v120);
LABEL_92:
          *((_QWORD *)this + 587) = v125;
          return (unsigned int)v44;
        }
        v104 = v126;
        while ( 1 )
        {
          v111 = (__int64 *)*((_QWORD *)Block + 19 * v72 + 1);
          v112 = *((unsigned int *)v104 + 2);
          v113 = v112 + 1;
          if ( (_DWORD)v112 != *((_DWORD *)v104 + 3) )
            break;
          v126 = (__int64 *)*((_QWORD *)Block + 19 * v72 + 1);
          if ( (int)CArray<CRefCountPtr<BitmapRealization>,CDefaultTraits<CRefCountPtr<BitmapRealization>>,CIndirectAllocator<CArenaAllocator<1024>>>::EnsureLargerCapacity(
                      v104,
                      v113,
                      &v126) >= 0 )
          {
            v114 = *((unsigned int *)v104 + 2);
            *((_DWORD *)v104 + 2) = v114 + 1;
            v115 = *v126;
LABEL_187:
            *(_QWORD *)(*v104 + 8 * v114) = v115;
            SafeAddRef<RefCountedObject<CMultiProcessElementBase,LockingRequired,DeleteOnZeroReference>>(v115);
          }
          if ( ++v72 >= (unsigned int)v122 )
            goto LABEL_83;
        }
        *((_DWORD *)v104 + 2) = v113;
        v114 = v112;
        v115 = *v111;
        goto LABEL_187;
      }
      DoStackCapture(v100);
      v116 = v101;
      CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>(&Block);
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
      CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v140);
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
      CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v119);
      *((_QWORD *)this + 587) = v125;
      return v101;
    }
  }
  else
  {
    CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v145);
    CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v173);
    CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v166);
    v96 = CDImageContext::EnsureRenderingMode(this, v13);
    if ( v116 >= 0 )
      v116 = v96;
    CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)&v128);
    if ( (_QWORD)v120 )
    {
      v97 = v119;
      *(_BYTE *)(v120 + 16) = 0;
      *((_QWORD *)v97 + 38) = *((_QWORD *)&v120 + 1);
    }
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v120 + 8);
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v120);
    result = 0;
    *((_QWORD *)this + 587) = v9;
  }
  return result;
}

```

## disassembly

```asm
0x180098a80  push    rbp
0x180098a82  push    rbx
0x180098a83  push    rsi
0x180098a84  push    r12
0x180098a86  push    r14
0x180098a88  push    r15
0x180098a8a  lea     rbp, [rsp-0A48h]
0x180098a92  sub     rsp, 0B48h
0x180098a99  mov     rax, cs:__security_cookie
0x180098aa0  xor     rax, rsp
0x180098aa3  mov     [rbp+0A70h+var_40], rax
0x180098aaa  mov     rax, [rbp+0A70h+arg_30]
0x180098ab1  mov     r14, rcx
0x180098ab4  mov     rcx, [rbp+0A70h+arg_20]
0x180098abb  xor     r15d, r15d
0x180098abe  mov     rsi, r8
0x180098ac1  mov     [rbp+0A70h+var_A70], rcx
0x180098ac5  mov     r8, [rbp+0A70h+arg_28]
0x180098acc  mov     [rbp+0A70h+var_AD0], r9
0x180098ad0  mov     [rbp+0A70h+var_A68], r8
0x180098ad4  mov     [rbp+0A70h+var_AC8], rax
0x180098ad8  mov     [r8], r15
0x180098adb  mov     [rax], r15d
0x180098ade  movups  xmm0, cs:?g_emptyRectL@@3UtagRECT@@B; tagRECT const g_emptyRectL
0x180098ae5  mov     [rsp+0B70h+var_B30], r15d
0x180098aea  mov     [rsp+0B70h+var_B20], r14
0x180098aef  movups  xmmword ptr [rcx], xmm0
0x180098af2  mov     r12, [r14+1258h]
0x180098af9  lea     rcx, [rsp+0B70h+var_B20]; this
0x180098afe  xorps   xmm0, xmm0
0x180098b01  mov     [rbp+0A70h+var_AD8], r12
0x180098b05  movdqu  [rsp+0B70h+var_B18], xmm0
0x180098b0b  mov     [r14+1258h], rdx
0x180098b12  call    ?Initialize@CReentrancyCycleGuard@CDImageContext@@QEAAJXZ; CDImageContext::CReentrancyCycleGuard::Initialize(void)
0x180098b17  mov     ebx, eax
0x180098b19  test    eax, eax
0x180098b1b  js      loc_18009957D
0x180098b21  mov     rcx, [r14+138h]
0x180098b28  mov     [rsp+0B70h+arg_8], rdi
0x180098b30  mov     [rbp+0A70h+var_AB8], rcx
0x180098b34  mov     [rsp+0B70h+var_30], r13
0x180098b3c  mov     [rsp+0B70h+var_B30], eax
0x180098b40  mov     [rbp+0A70h+var_AC0], r14
0x180098b44  call    ??$SafeAddRef@V?$RefCountedObject@VCMultiProcessElementBase@@ULockingRequired@@UDeleteOnZeroReference@@@@@@YAXPEAV?$RefCountedObject@VCMultiProcessElementBase@@ULockingRequired@@UDeleteOnZeroReference@@@@@Z; SafeAddRef<RefCountedObject<CMultiProcessElementBase,LockingRequired,DeleteOnZeroReference>>(RefCountedObject<CMultiProcessElementBase,LockingRequired,DeleteOnZeroReference> *)
0x180098b49  mov     eax, [r14+140h]
0x180098b50  lea     rcx, [rbp+0A70h+var_8A0]; this
0x180098b57  movsd   xmm0, qword ptr [r14+0C8h]
0x180098b60  mov     r13d, [r14+1270h]
0x180098b67  movss   xmm1, dword ptr [r14+0E8h]
0x180098b70  mov     [rbp+0A70h+var_AB0], eax
0x180098b73  mov     eax, [r14+0D0h]
0x180098b7a  mov     [rbp+0A70h+var_AA4], eax
0x180098b7d  mov     eax, [r14+0ECh]
0x180098b84  mov     [rbp+0A70h+var_AA0], eax
0x180098b87  mov     rax, [r14+150h]
0x180098b8e  mov     [rbp+0A70h+var_A88], rax
0x180098b92  movzx   eax, byte ptr [r14+1298h]
0x180098b9a  mov     [rbp+0A70h+var_A80], al
0x180098b9d  lea     rax, [rsp+0B70h+var_B30]
0x180098ba2  movsd   [rbp+0A70h+var_AAC], xmm0
0x180098ba7  movss   xmm0, dword ptr [r14+0E4h]
0x180098bb0  mov     [rbp+0A70h+var_A48], rax
0x180098bb4  movss   [rbp+0A70h+var_A9C], xmm0
0x180098bb9  movss   [rbp+0A70h+var_A98], xmm1
0x180098bbe  mov     [rbp+0A70h+var_A58], r14
0x180098bc2  mov     [rbp+0A70h+var_AF0], r13d
0x180098bc6  mov     [rbp+0A70h+var_A50], r13d
0x180098bca  call    ??0CInputTransformNode@@QEAA@XZ; CInputTransformNode::CInputTransformNode(void)
0x180098bcf  lea     rcx, [rbp+0A70h+var_680]; this
0x180098bd6  call    ??0CBrushTransformNode@@QEAA@XZ; CBrushTransformNode::CBrushTransformNode(void)
0x180098bdb  mov     eax, [rsi+54h]
0x180098bde  lea     rcx, [r14+138h]; void *
0x180098be5  movss   xmm0, dword ptr [rsi+58h]
0x180098bea  movss   dword ptr [r14+0E8h], xmm0
0x180098bf3  mov     [r14+0E4h], eax
0x180098bfa  mov     eax, [rsi+50h]
0x180098bfd  mov     [r14+0ECh], eax
0x180098c04  mov     byte ptr [r14+1250h], 1
0x180098c0c  mov     rbx, [rsi]
0x180098c0f  call    ??1?$com_ptr@PEAVBitmapRealization@@@win_scope@@QEAA@XZ; win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(void)
0x180098c14  mov     [r14+138h], rbx
0x180098c1b  test    rbx, rbx
0x180098c1e  jz      short loc_180098C2E
0x180098c20  mov     rax, [rbx]
0x180098c23  mov     rcx, rbx
0x180098c26  mov     rax, [rax]
0x180098c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c2e  mov     eax, [rsi+38h]
0x180098c31  mov     [r14+140h], eax
0x180098c38  movsd   xmm0, qword ptr [rsi+3Ch]
0x180098c3d  movsd   qword ptr [r14+0C8h], xmm0
0x180098c46  mov     eax, [rsi+44h]
0x180098c49  mov     [r14+0D0h], eax
0x180098c50  cmp     [r14+14Ah], r15b
0x180098c57  jnz     short loc_180098C6C
0x180098c59  mov     rcx, [r14+0CCh]; struct D2D_SIZE_U
0x180098c60  call    ?GetMinAllocationSize@@YA?AUD2D_SIZE_U@@U1@@Z; GetMinAllocationSize(D2D_SIZE_U)
0x180098c65  mov     [r14+121Ch], rax
0x180098c6c  mov     rcx, [rsi+8]
0x180098c70  mov     rax, [rcx]
0x180098c73  mov     rax, [rax+0A8h]
0x180098c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c7f  test    al, al
0x180098c81  jnz     loc_1800994BF
0x180098c87  mov     rcx, [rsi+10h]
0x180098c8b  mov     r10d, 7FFFFFFFh
0x180098c91  mov     r9, [r14+138h]
0x180098c98  mov     qword ptr [rsp+0B70h+var_B28.x], rcx
0x180098c9d  movups  xmm0, xmmword ptr [rsi+18h]
0x180098ca1  mov     r9, [r9+54h]
0x180098ca5  movups  xmmword ptr [rbp+0A70h+var_AE8.left], xmm0
0x180098ca9  test    ecx, ecx
0x180098cab  js      loc_180099653
0x180098cb1  cmp     ecx, r9d
0x180098cb4  jge     loc_1800999A8
0x180098cba  mov     edx, [rbp+0A70h+var_AE8.left]
0x180098cbd  cmp     edx, [rbp+0A70h+var_AE8.right]
0x180098cc0  mov     r8d, edx
0x180098cc3  mov     eax, r9d
0x180098cc6  cmovle  r8d, [rbp+0A70h+var_AE8.right]
0x180098ccb  sub     eax, ecx
0x180098ccd  lea     ecx, [rdx+rax]
0x180098cd0  js      loc_180099483
0x180098cd6  cmp     ecx, edx
0x180098cd8  mov     eax, r10d
0x180098cdb  cmovge  eax, ecx
0x180098cde  cmp     r8d, eax
0x180098ce1  cmovl   eax, r8d
0x180098ce5  mov     [rbp+0A70h+var_AE8.right], eax
0x180098ce8  mov     r8d, [rsp+0B70h+var_B28.y]
0x180098ced  shr     r9, 20h
0x180098cf1  test    r8d, r8d
0x180098cf4  js      loc_180099671
0x180098cfa  cmp     r8d, r9d
0x180098cfd  jge     loc_1800999BA
0x180098d03  mov     ecx, [rbp+0A70h+var_AE8.top]
0x180098d06  cmp     ecx, [rbp+0A70h+var_AE8.bottom]
0x180098d09  mov     edx, ecx
0x180098d0b  cmovle  edx, [rbp+0A70h+var_AE8.bottom]
0x180098d0f  sub     r9d, r8d
0x180098d12  lea     eax, [rcx+r9]
0x180098d16  js      loc_180099492
0x180098d1c  cmp     eax, ecx
0x180098d1e  cmovge  r10d, eax
0x180098d22  cmp     edx, r10d
0x180098d25  cmovl   r10d, edx
0x180098d29  mov     [rbp+0A70h+var_AE8.bottom], r10d
0x180098d2d  mov     rax, [r14+1290h]
0x180098d34  lea     rcx, [rbp+0A70h+var_888]; void *
0x180098d3b  mov     rbx, [r14+128h]
0x180098d42  mov     [rbp+0A70h+var_880], rax
0x180098d49  mov     [rbp+0A70h+var_890], r15
0x180098d50  call    ??1?$com_ptr@PEAVBitmapRealization@@@win_scope@@QEAA@XZ; win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(void)
0x180098d55  mov     [rbp+0A70h+var_888], rbx
0x180098d5c  test    rbx, rbx
0x180098d5f  jz      short loc_180098D6F
0x180098d61  mov     rax, [rbx]
0x180098d64  mov     rcx, rbx
0x180098d67  mov     rax, [rax]
0x180098d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d6f  lea     rcx, [rbp+0A70h+var_840]; void *
0x180098d76  call    ??1?$com_ptr@PEAUID3D11DepthStencilState@@@win_scope@@QEAA@XZ; win_scope::com_ptr<ID3D11DepthStencilState *>::~com_ptr<ID3D11DepthStencilState *>(void)
0x180098d7b  mov     [rbp+0A70h+var_840], r14
0x180098d82  mov     rcx, r14
0x180098d85  mov     rax, [r14]
0x180098d88  mov     rax, [rax+8]
0x180098d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d91  mov     [rbp+0A70h+var_868], r15
0x180098d98  mov     r15, [rsi+60h]
0x180098d9c  mov     [rbp+0A70h+var_830], 3
0x180098da6  test    r15, r15
0x180098da9  jnz     short loc_180098DFC
0x180098dab  mov     rbx, [rsi+8]
0x180098daf  mov     edi, r15d
0x180098db2  test    rbx, rbx
0x180098db5  jz      short loc_180098DC6
0x180098db7  mov     rax, [rbx]
0x180098dba  mov     rcx, rbx
0x180098dbd  mov     rax, [rax+8]
0x180098dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098dc6  mov     rcx, [rbp+0A70h+var_6F0]
0x180098dcd  test    rcx, rcx
0x180098dd0  jz      short loc_180098DDE
0x180098dd2  mov     rax, [rcx]
0x180098dd5  mov     rax, [rax+10h]
0x180098dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098dde  mov     rdx, [rsi+70h]; struct D2D_MATRIX_3X2_F *
0x180098de2  mov     [rbp+0A70h+var_6F0], rbx
0x180098de9  test    rdx, rdx
0x180098dec  jz      short loc_180098E61
0x180098dee  lea     rcx, [rbp+0A70h+var_8A0]; this
0x180098df5  call    ?SetExtraInputTransform@CInputTransformNode@@QEAAJAEBUD2D_MATRIX_3X2_F@@@Z; CInputTransformNode::SetExtraInputTransform(D2D_MATRIX_3X2_F const &)
0x180098dfa  jmp     short loc_180098E61
0x180098dfc  mov     rcx, [rsi+8]
0x180098e00  mov     rbx, [rsi+70h]
0x180098e04  mov     edi, [rsi+68h]
0x180098e07  mov     rax, [rcx]
0x180098e0a  mov     rax, [rax+78h]
0x180098e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098e13  mov     r9, r15; struct IBrushRedirection **
0x180098e16  mov     [rsp+0B70h+var_B48], rbx; struct D2D_MATRIX_3X2_F *
0x180098e1b  mov     r8, rax; struct ICommandListInternal *
0x180098e1e  mov     dword ptr [rsp+0B70h+var_B50], edi; unsigned int
0x180098e22  mov     rdx, r14; struct CDImageContext *
0x180098e25  lea     rcx, [rbp+0A70h+var_680]; this
0x180098e2c  call    ?Initialize@CBrushTransformNode@@QEAAJPEAVCDImageContext@@PEAVICommandListInternal@@PEAPEAVIBrushRedirection@@IPEAUD2D_MATRIX_3X2_F@@@Z; CBrushTransformNode::Initialize(CDImageContext *,ICommandListInternal *,IBrushRedirection * *,uint,D2D_MATRIX_3X2_F *)
0x180098e31  mov     edi, eax
0x180098e33  test    eax, eax
0x180098e35  js      loc_180099527
0x180098e3b  mov     rcx, [rbp+0A70h+var_6F0]
0x180098e42  xor     r15d, r15d
0x180098e45  test    rcx, rcx
0x180098e48  jnz     loc_1800999CC
0x180098e4e  lea     rdx, [rbp+0A70h+var_678]
0x180098e55  lea     rcx, [rbp+0A70h+var_6E8]
0x180098e5c  call    ??4?$CRefCountPtr@VCTickCounter@@@@QEAAAEAV0@PEAVCTickCounter@@@Z; CRefCountPtr<CTickCounter>::operator=(CTickCounter *)
0x180098e61  test    edi, edi
0x180098e63  js      loc_18009952E
0x180098e69  mov     [rsp+0B70h+var_B38], 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180098e72  lea     rax, [rbp+0A70h+var_A1F]
0x180098e76  mov     [rbp+0A70h+var_A30], rax
0x180098e7a  lea     rcx, [rsp+0B70h+var_B2C]
0x180098e7f  mov     [rsp+0B70h+var_B40], rcx; bool *
0x180098e84  lea     rax, [rbp+0A70h+var_950]
0x180098e8b  mov     [rbp+0A70h+var_948], rax
0x180098e92  lea     rcx, [rbp+0A70h+var_A40]
0x180098e96  mov     [rsp+0B70h+var_B48], rcx; struct CDImageContext::RENDER_STACK_OBJECTS *
0x180098e9b  lea     rax, [rbp+0A70h+var_950]
0x180098ea2  mov     [rbp+0A70h+var_950], rax
0x180098ea9  lea     r9, [rsp+0B70h+var_B28]; struct tagPOINT *
0x180098eae  lea     rax, [rsi+28h]
0x180098eb2  mov     [rsp+0B70h+var_B30], edi
0x180098eb6  mov     rdi, [r14+12A0h]
0x180098ebd  lea     r8, [rbp+0A70h+var_AE8]; struct tagRECT *
0x180098ec1  lea     rdx, [rbp+0A70h+var_8A0]; struct CTransformNode *
0x180098ec8  mov     [rsp+0B70h+var_B50], rax; struct tagRECT *
0x180098ecd  mov     rcx, r14; this
0x180098ed0  mov     [rbp+0A70h+var_A28], r15d
0x180098ed4  mov     [rbp+0A70h+var_A20], 0
0x180098ed8  mov     [rbp+0A70h+var_A24], 19h
0x180098edf  mov     [rsp+0B70h+var_B2C], 0
0x180098ee4  call    ?InitializeRenderObjects@CDImageContext@@IEAAJPEAVCTransformNode@@PEBUtagRECT@@PEBUtagPOINT@@AEBU3@PEAURENDER_STACK_OBJECTS@1@PEA_N_K@Z; CDImageContext::InitializeRenderObjects(CTransformNode *,tagRECT const *,tagPOINT const *,tagRECT const &,CDImageContext::RENDER_STACK_OBJECTS *,bool *,unsigned __int64)
0x180098ee9  mov     ebx, eax
0x180098eeb  test    eax, eax
0x180098eed  js      loc_1800995C9
0x180098ef3  mov     [rsp+0B70h+var_B30], eax
0x180098ef7  cmp     [r14+12A0h], rdi
0x180098efe  jnz     loc_1800997BD
0x180098f04  cmp     [rbp+0A70h+var_909], 0
0x180098f0b  mov     r12d, 1
0x180098f11  mov     [rsp+0B70h+Block], r15
0x180098f16  mov     r9d, 0FFFFFFFFh
0x180098f1c  mov     [rsp+0B70h+var_B00], 0
0x180098f25  jnz     loc_1800994A3
0x180098f2b  mov     ecx, [rbp+0A70h+var_91C]
0x180098f31  sub     ecx, [rbp+0A70h+var_924]
0x180098f37  mov     edx, [rbp+0A70h+var_918]
0x180098f3d  mov     eax, ecx
0x180098f3f  sub     edx, [rbp+0A70h+var_920]
0x180098f45  cmp     ecx, edx
0x180098f47  cmovbe  eax, edx
0x180098f4a  cmp     eax, 10h
0x180098f4d  jbe     loc_1800994A3
0x180098f53  mov     r11d, [r14+0F4h]
0x180098f5a  lea     r15, [r14+0CCh]
0x180098f61  mov     r8d, edx
0x180098f64  mov     eax, ecx
0x180098f66  imul    r8, rax
0x180098f6a  cmp     r8, r9
0x180098f6d  cmova   r8, r9
0x180098f71  imul    r11d, r11d
0x180098f75  cmp     r8d, r11d
0x180098f78  jbe     loc_18009940D
0x180098f7e  mov     rbx, [r15]
0x180098f81  lea     r8, [rsp+0B70h+var_B28]; struct CRenderIntermediate **
0x180098f86  mov     qword ptr [rsp+0B70h+var_B28.x], 0
0x180098f8f  lea     rdx, [rbp+0A70h+var_940]; struct TILE *
0x180098f96  mov     rcx, r14; this
0x180098f99  call    ?GetUnresolvedRootIntermediateForTile@CDImageContext@@IEAAJPEBUTILE@@PEAPEAVCRenderIntermediate@@@Z; CDImageContext::GetUnresolvedRootIntermediateForTile(TILE const *,CRenderIntermediate * *)
0x180098f9e  mov     edi, eax
0x180098fa0  test    eax, eax
0x180098fa2  js      loc_1800990B1
0x180098fa8  mov     rcx, [r14+128h]
0x180098faf  lea     rsi, [r14+160h]
0x180098fb6  mov     r9, [r15]
0x180098fb9  mov     r8, [r14+1258h]
0x180098fc0  movzx   r11d, [rbp+0A70h+var_928]
0x180098fc8  mov     rdx, [rcx+8]
0x180098fcc  mov     r10, [rbp+0A70h+var_940]
0x180098fd3  mov     r13, qword ptr [rsp+0B70h+var_B28.x]
0x180098fd8  lea     rax, [rdx+1]
0x180098fdc  mov     [rcx+8], rax
0x180098fe0  lea     rax, [rbp+0A70h+var_A40]
0x180098fe4  mov     [rsi+48h], rax
0x180098fe8  mov     rcx, r13; this
0x180098feb  xor     eax, eax
0x180098fed  mov     [rsi+90h], rdx
0x180098ff4  mov     [rsi+70h], rax
0x180098ff8  mov     [rsi+78h], al
0x180098ffb  mov     [rsi+80h], rax
  ... truncated ...
```
