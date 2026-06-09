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
  __int64 v74; // r8
  __int64 v75; // r9
  int v76; // eax
  __int64 v77; // rcx
  const struct D2D1_BLEND_DESCRIPTION *v78; // rdi
  struct tagPOINT v79; // rsi
  int v80; // edx
  int v81; // eax
  int v82; // r9d
  unsigned int v83; // r8d
  unsigned int v84; // r11d
  unsigned int BoundingPow2; // eax
  unsigned int v86; // r9d
  unsigned int v87; // r10d
  unsigned int v88; // ecx
  unsigned int v89; // eax
  __int64 j; // rbx
  CDImageContext *v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // r8
  __int64 v94; // r9
  int v95; // eax
  CDImageContext *v96; // rcx
  __int64 v97; // r8
  __int64 v98; // r9
  int v99; // eax
  CDImageContext *v100; // rcx
  __int64 v101; // r8
  __int64 v102; // r9
  int v103; // eax
  __int64 v104; // r8
  __int64 v105; // r9
  int v106; // eax
  CDImageContext *v107; // rcx
  unsigned int m; // ebx
  __int64 v109; // rcx
  int v110; // eax
  unsigned int v111; // ebx
  __int64 v112; // r8
  __int64 v113; // r9
  int v114; // eax
  CDImageContext *v115; // rcx
  __int64 *v116; // rsi
  unsigned int **v117; // rbx
  int v118; // ecx
  unsigned int v119; // eax
  unsigned int **v120; // rcx
  char *v121; // rsi
  CDImageContext *v122; // rcx
  __int64 *v123; // rcx
  __int64 v124; // rax
  unsigned int v125; // r9d
  __int64 v126; // rdx
  __int64 v127; // rcx
  int v128; // [rsp+40h] [rbp-C0h] BYREF
  bool v129; // [rsp+44h] [rbp-BCh] BYREF
  struct tagPOINT v130; // [rsp+48h] [rbp-B8h] BYREF
  CDImageContext *v131; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v132; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  __int64 v134; // [rsp+70h] [rbp-90h]
  unsigned int v135; // [rsp+80h] [rbp-80h]
  struct tagRECT v136; // [rsp+88h] [rbp-78h] BYREF
  __int64 v137; // [rsp+98h] [rbp-68h]
  __int64 *v138; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v139; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v140[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v141; // [rsp+C0h] [rbp-40h]
  __int64 v142; // [rsp+C4h] [rbp-3Ch]
  int v143; // [rsp+CCh] [rbp-34h]
  int v144; // [rsp+D0h] [rbp-30h]
  int v145; // [rsp+D4h] [rbp-2Ch]
  int v146; // [rsp+D8h] [rbp-28h]
  __int64 v147; // [rsp+E8h] [rbp-18h]
  char v148; // [rsp+F0h] [rbp-10h]
  struct tagRECT *v149; // [rsp+100h] [rbp+0h]
  struct tagPOINT *v150; // [rsp+108h] [rbp+8h]
  char v151[8]; // [rsp+110h] [rbp+10h] BYREF
  CDImageContext *v152; // [rsp+118h] [rbp+18h]
  unsigned int v153; // [rsp+120h] [rbp+20h]
  int *v154; // [rsp+128h] [rbp+28h]
  _BYTE v155[16]; // [rsp+130h] [rbp+30h] BYREF
  char *v156; // [rsp+140h] [rbp+40h] BYREF
  int v157; // [rsp+148h] [rbp+48h]
  int v158; // [rsp+14Ch] [rbp+4Ch]
  char v159; // [rsp+150h] [rbp+50h]
  char v160; // [rsp+151h] [rbp+51h] BYREF
  _QWORD v161[2]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v162[3]; // [rsp+230h] [rbp+130h] BYREF
  char v163; // [rsp+248h] [rbp+148h]
  int v164; // [rsp+24Ch] [rbp+14Ch]
  int v165; // [rsp+250h] [rbp+150h]
  int v166; // [rsp+254h] [rbp+154h]
  int v167; // [rsp+258h] [rbp+158h]
  char v168; // [rsp+267h] [rbp+167h]
  int v169; // [rsp+268h] [rbp+168h]
  int v170; // [rsp+26Ch] [rbp+16Ch]
  int v171; // [rsp+270h] [rbp+170h]
  int v172; // [rsp+274h] [rbp+174h]
  int v173; // [rsp+278h] [rbp+178h]
  int v174; // [rsp+27Ch] [rbp+17Ch]
  int v175; // [rsp+280h] [rbp+180h]
  int v176; // [rsp+284h] [rbp+184h]
  _BYTE v177[16]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v178; // [rsp+2E0h] [rbp+1E0h]
  _QWORD v179[9]; // [rsp+2E8h] [rbp+1E8h] BYREF
  CDImageContext *v180; // [rsp+330h] [rbp+230h] BYREF
  int v181; // [rsp+340h] [rbp+240h]
  __int64 v182; // [rsp+480h] [rbp+380h]
  char v183[104]; // [rsp+488h] [rbp+388h] BYREF
  char v184[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v185[432]; // [rsp+4F8h] [rbp+3F8h] BYREF
  _BYTE v186[48]; // [rsp+6A8h] [rbp+5A8h] BYREF
  _BYTE v187[544]; // [rsp+6D8h] [rbp+5D8h] BYREF
  _BYTE v188[568]; // [rsp+8F8h] [rbp+7F8h] BYREF

  v149 = a5;
  v138 = a4;
  v150 = a6;
  v139 = a7;
  *a6 = 0;
  *a7 = 0;
  v128 = 0;
  v131 = this;
  *a5 = g_emptyRectL;
  v9 = *((_QWORD *)this + 587);
  v137 = v9;
  v132 = 0;
  *((_QWORD *)this + 587) = a2;
  v10 = CDImageContext::CReentrancyCycleGuard::Initialize((CDImageContext::CReentrancyCycleGuard *)&v131);
  v11 = v10;
  if ( v10 < 0 )
  {
    DoStackCapture(v10);
    v128 = v11;
    if ( (_QWORD)v132 )
    {
      v91 = v131;
      v92 = *((_QWORD *)&v132 + 1);
      *(_BYTE *)(v132 + 16) = 0;
      *((_QWORD *)v91 + 38) = v92;
    }
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v132 + 8);
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v132);
    result = v11;
    *((_QWORD *)this + 587) = v9;
    return result;
  }
  v140[1] = *((_QWORD *)this + 39);
  v128 = v10;
  v140[0] = this;
  SafeAddRef<RefCountedObject<CMultiProcessElementBase,LockingRequired,DeleteOnZeroReference>>();
  v12 = *((_QWORD *)this + 25);
  v13 = *((_DWORD *)this + 1180);
  v14 = *((_DWORD *)this + 58);
  v141 = *((_DWORD *)this + 80);
  v143 = *((_DWORD *)this + 52);
  v144 = *((_DWORD *)this + 59);
  v147 = *((_QWORD *)this + 42);
  v148 = *((_BYTE *)this + 4760);
  v142 = v12;
  LODWORD(v12) = *((_DWORD *)this + 57);
  v154 = &v128;
  v145 = v12;
  v146 = v14;
  v152 = this;
  v135 = v13;
  v153 = v13;
  CInputTransformNode::CInputTransformNode((CInputTransformNode *)v177);
  CBrushTransformNode::CBrushTransformNode((CBrushTransformNode *)v184);
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
    v130 = 0;
    v136 = g_emptyRectL;
    goto LABEL_29;
  }
  v17 = *(struct tagPOINT *)(a3 + 16);
  v18 = 0x7FFFFFFF;
  v19 = *((_QWORD *)this + 39);
  v130 = v17;
  v20 = *(_QWORD *)(v19 + 84);
  v136 = *(struct tagRECT *)(a3 + 24);
  if ( v17.x < 0 )
  {
    left = ClipAdd(v136.left, -v17.x);
    v136.left = left;
    v130.x = 0;
    v17.x = 0;
  }
  else
  {
    if ( v17.x >= (int)v20 )
    {
      v136.right = 0;
      v136.left = 0;
      v130.x = 0;
      goto LABEL_18;
    }
    left = v136.left;
  }
  right = left;
  if ( left <= v136.right )
    right = v136.right;
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
  v136.right = v25;
LABEL_18:
  y = v130.y;
  v27 = HIDWORD(v20);
  if ( v130.y < 0 )
  {
    top = ClipAdd(v136.top, -v130.y);
    v136.top = top;
    y = 0;
    v130.y = 0;
  }
  else
  {
    if ( v130.y >= (int)v27 )
    {
      v136.bottom = 0;
      v136.top = 0;
      v130.y = 0;
      goto LABEL_29;
    }
    top = v136.top;
  }
  bottom = top;
  if ( top <= v136.bottom )
    bottom = v136.bottom;
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
  v136.bottom = v18;
LABEL_29:
  v32 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 37);
  v179[1] = *((_QWORD *)this + 594);
  v178 = 0;
  win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(v179);
  v179[0] = v32;
  if ( v32 )
    (**v32)(v32);
  win_scope::com_ptr<ID3D11DepthStencilState *>::~com_ptr<ID3D11DepthStencilState *>(&v180);
  v180 = this;
  (*(void (__fastcall **)(CDImageContext *))(*(_QWORD *)this + 8LL))(this);
  v179[4] = 0;
  v33 = *(struct IBrushRedirection ***)(a3 + 96);
  v181 = 3;
  if ( v33 )
  {
    v37 = *(struct D2D_MATRIX_3X2_F **)(a3 + 112);
    v38 = *(_DWORD *)(a3 + 104);
    v39 = (struct ICommandListInternal *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 8) + 120LL))(*(_QWORD *)(a3 + 8));
    v40 = CBrushTransformNode::Initialize((CBrushTransformNode *)v184, this, v39, v33, v38, v37);
    v35 = v40;
    if ( v40 < 0 )
    {
      DoStackCapture(v40);
      goto LABEL_120;
    }
    v41 = v182;
    if ( v182 )
    {
      v182 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    CRefCountPtr<CTickCounter>::operator=(v183, v185);
  }
  else
  {
    v34 = *(_QWORD *)(a3 + 8);
    v35 = 0;
    if ( v34 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v34 + 8LL))(*(_QWORD *)(a3 + 8));
    if ( v182 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v182 + 16LL))(v182);
    v36 = *(const struct D2D_MATRIX_3X2_F **)(a3 + 112);
    v182 = v34;
    if ( v36 )
      CInputTransformNode::SetExtraInputTransform((CInputTransformNode *)v177, v36);
  }
  if ( v35 < 0 )
  {
LABEL_120:
    DoStackCapture(v35);
    v128 = v35;
    CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
    CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
    CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v151);
    CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
    CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v131);
    result = (unsigned int)v35;
    *((_QWORD *)this + 587) = v9;
    return result;
  }
  v156 = &v160;
  v161[1] = v161;
  v161[0] = v161;
  v128 = v35;
  v42 = *((_QWORD *)this + 596);
  v157 = 0;
  v159 = 0;
  v158 = 25;
  v129 = 0;
  v43 = CDImageContext::InitializeRenderObjects(
          this,
          (struct CTransformNode *)v177,
          &v136,
          &v130,
          (const struct tagRECT *)(a3 + 40),
          (struct CDImageContext::RENDER_STACK_OBJECTS *)v155,
          &v129,
          0xFFFFFFFFFFFFFFFFuLL);
  v44 = v43;
  if ( v43 < 0 )
  {
    DoStackCapture(v43);
    v128 = v44;
    CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
    CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
    CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
    v95 = CDImageContext::EnsureRenderingMode(this, v13, v93, v94);
    if ( v128 >= 0 )
      v128 = v95;
    CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
    if ( (_QWORD)v132 )
    {
      v96 = v131;
      *(_BYTE *)(v132 + 16) = 0;
      *((_QWORD *)v96 + 38) = *((_QWORD *)&v132 + 1);
    }
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v132 + 8);
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v132);
    *((_QWORD *)this + 587) = v9;
    return (unsigned int)v44;
  }
  v128 = v43;
  if ( *((_QWORD *)this + 596) == v42 )
  {
    v45 = 1;
    Block = 0;
    v134 = 0;
    if ( v168 )
      goto LABEL_112;
    v46 = v166 - v164;
    if ( v166 - v164 <= (unsigned int)(v167 - v165) )
      v46 = v167 - v165;
    if ( v46 <= 0x10 )
    {
LABEL_112:
      v47 = (unsigned int *)((char *)this + 204);
      v49 = *((unsigned int *)this + 60) | ((unsigned __int64)*((unsigned int *)this + 60) << 32);
    }
    else
    {
      v47 = (unsigned int *)((char *)this + 204);
      v48 = (unsigned int)(v166 - v164) * (unsigned __int64)(unsigned int)(v167 - v165);
      if ( v48 > 0xFFFFFFFF )
        LODWORD(v48) = -1;
      if ( (unsigned int)v48 <= *((_DWORD *)this + 61) * *((_DWORD *)this + 61) )
      {
        GetBoundingPow2(*v47);
        GetBoundingPow2(*((_DWORD *)this + 52));
        BoundingPow2 = GetBoundingPow2(v84 / v83);
        if ( BoundingPow2 > 1 )
        {
          v88 = BoundingPow2 - 1;
          v89 = *((_DWORD *)this + 60);
          v88 >>= 1;
          v86 <<= v88;
          v87 <<= v88;
          if ( v86 >= v89 )
            v86 = *((_DWORD *)this + 60);
          if ( v87 >= v89 )
            v87 = *((_DWORD *)this + 60);
        }
        v130 = (struct tagPOINT)__PAIR64__(v87, v86);
        v49 = __PAIR64__(v87, v86);
      }
      else
      {
        v49 = *(_QWORD *)v47;
      }
    }
    v130 = 0;
    UnresolvedRootIntermediateForTile = CDImageContext::GetUnresolvedRootIntermediateForTile(
                                          this,
                                          (const struct TILE *)v162,
                                          (struct CRenderIntermediate **)&v130);
    if ( UnresolvedRootIntermediateForTile < 0 )
    {
LABEL_63:
      DoStackCapture(UnresolvedRootIntermediateForTile);
      DoStackCapture(UnresolvedRootIntermediateForTile);
      v128 = UnresolvedRootIntermediateForTile;
      CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>(&Block);
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
      CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v151);
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
      CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v131);
      *((_QWORD *)this + 587) = v137;
      return (unsigned int)UnresolvedRootIntermediateForTile;
    }
    v51 = *((_QWORD *)this + 37);
    v52 = *(_QWORD *)v47;
    v53 = *((_QWORD *)this + 587);
    v54 = v163;
    v55 = *(_QWORD *)(v51 + 8);
    v56 = v162[0];
    v57 = v130;
    *(_QWORD *)(v51 + 8) = v55 + 1;
    *((_QWORD *)this + 53) = v155;
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
    v61 = v157;
    *((_QWORD *)this + 61) = &Block;
    for ( i = (unsigned int)(v61 - 1); ; i = (unsigned int)(i - 1) )
    {
      UnresolvedRootIntermediateForTile = CRenderOperationResolver::ResolveRenderOperationsCallback(
                                            (CDImageContext *)((char *)this + 352),
                                            *(struct CTransformNode **)&v156[8 * i]);
      if ( UnresolvedRootIntermediateForTile < 0 )
        goto LABEL_62;
      if ( !(_DWORD)i )
        break;
    }
    if ( *((_BYTE *)this + 472) && *((_DWORD *)this + 113) == 1 )
    {
      for ( j = (unsigned int)(v157 - 1); ; j = (unsigned int)(j - 1) )
      {
        UnresolvedRootIntermediateForTile = CRenderOperationResolver::DetermineTilingLocationsCallback(
                                              (CDImageContext *)((char *)this + 352),
                                              *(struct CTransformNode **)&v156[8 * j]);
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
    v64 = v139;
    v65 = *((_BYTE *)this + 472);
    *v139 = *((_DWORD *)this + 116);
    if ( g_pSqm )
    {
      v66 = *v64;
      if ( v66 > *((_DWORD *)g_pSqm + 2) )
        *((_DWORD *)g_pSqm + 2) = v66;
    }
    v128 = UnresolvedRootIntermediateForTile;
    if ( (v170 < v174 || v169 < v173 || v171 > v175 || v172 > v176) && v169 < v171 && v170 < v172 )
    {
      v77 = *((_QWORD *)this + 587);
      v78 = (const struct D2D1_BLEND_DESCRIPTION *)v162[2];
      v130 = 0;
      v44 = CRenderOperation::Create(v77, &v130);
      if ( v44 < 0 )
        goto LABEL_98;
      v79 = v130;
      *(_DWORD *)(*(_QWORD *)&v130 + 123LL) = 2;
      *(_OWORD *)(*(_QWORD *)&v79 + 48LL) = 0;
      *(_DWORD *)(*(_QWORD *)&v79 + 32LL) = 0;
      v80 = v175;
      v81 = v173;
      v82 = v176;
      *(_DWORD *)(*(_QWORD *)&v79 + 52LL) = v174;
      *(_DWORD *)(*(_QWORD *)&v79 + 56LL) = v80;
      *(_DWORD *)(*(_QWORD *)&v79 + 48LL) = v81;
      *(_DWORD *)(*(_QWORD *)&v79 + 60LL) = v82;
      v44 = CRenderOperation::SetTargetParams(*(CRenderOperation **)&v79, *(struct CRenderIntermediate **)&v57, v78);
      if ( v44 < 0 )
        goto LABEL_98;
      v117 = &v139;
      *(_DWORD *)(*(_QWORD *)&v79 + 147LL) = v169;
      *(_DWORD *)(*(_QWORD *)&v79 + 151LL) = v170;
      *(_DWORD *)(*(_QWORD *)&v79 + 155LL) = v171;
      *(_DWORD *)(*(_QWORD *)&v79 + 159LL) = v172;
      v118 = *(_DWORD *)(*(_QWORD *)&v57 + 48LL);
      v139 = (unsigned int *)v79;
      v130 = (struct tagPOINT)&v139;
      if ( v118 )
        v45 = v118 + 1;
      if ( *(_DWORD *)(*(_QWORD *)&v57 + 52LL) < v45 )
      {
        v44 = CArray<CRenderOperation *,CPodTraits<CRenderOperation *>,CIndirectAllocator<CArenaAllocator<1024>>>::EnsureLargerCapacity(
                *(_QWORD *)&v57 + 40LL,
                v45,
                &v130);
        if ( v44 < 0 )
        {
LABEL_98:
          DoStackCapture(v44);
          DoStackCapture(v44);
          v128 = v44;
          CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>(&Block);
          CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
          CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
          CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v151);
          CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
          CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v131);
          goto LABEL_92;
        }
        v117 = (unsigned int **)v130;
      }
      v119 = *(_DWORD *)(*(_QWORD *)&v57 + 48LL);
      if ( v119 )
        memmove_0(
          (void *)(*(_QWORD *)(*(_QWORD *)&v57 + 40LL) + 8LL),
          *(const void **)(*(_QWORD *)&v57 + 40LL),
          8LL * v119);
      v120 = *(unsigned int ***)(*(_QWORD *)&v57 + 40LL);
      *(_DWORD *)(*(_QWORD *)&v57 + 48LL) = v45;
      *v120 = *v117;
    }
    v128 = 0;
    if ( v129 )
    {
      v44 = 0;
    }
    else
    {
      OcclusionRect = CDImageContext::GetOcclusionRect(this, *(struct CRenderIntermediate **)&v57, v149);
      v44 = OcclusionRect;
      if ( OcclusionRect < 0 )
      {
        DoStackCapture(OcclusionRect);
        v128 = v44;
        if ( Block )
        {
          free(Block);
          Block = 0;
          HIDWORD(v134) = 0;
        }
        LODWORD(v134) = 0;
        CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
        CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v188);
        CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v187);
        CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>::~CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>(v186);
        CTransformNode::~CTransformNode((CTransformNode *)v185);
        CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
        v99 = CDImageContext::EnsureRenderingMode(this, v135, v97, v98);
        if ( v128 >= 0 )
          v128 = v99;
        CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
        if ( (_QWORD)v132 )
        {
          v100 = v131;
          *(_BYTE *)(v132 + 16) = 0;
          *((_QWORD *)v100 + 38) = *((_QWORD *)&v132 + 1);
        }
        goto LABEL_91;
      }
      v128 = OcclusionRect;
    }
    if ( v65 )
    {
      if ( Block )
      {
        free(Block);
        Block = 0;
        HIDWORD(v134) = 0;
      }
      LODWORD(v134) = 0;
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
      v103 = CDImageContext::EnsureRenderingMode(this, v135, v101, v102);
      if ( v128 >= 0 )
        v128 = v103;
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
      if ( !(_QWORD)v132 )
        goto LABEL_91;
      *(_BYTE *)(v132 + 16) = 0;
      goto LABEL_90;
    }
    v68 = v134;
    v69 = (unsigned int)(v134 + *((_DWORD *)v138 + 2));
    if ( *((_DWORD *)v138 + 3) >= (unsigned int)v69 )
    {
      v128 = 0;
      goto LABEL_79;
    }
    v110 = CArray<CRefCountPtr<BitmapRealization>,CDefaultTraits<CRefCountPtr<BitmapRealization>>,CIndirectAllocator<CArenaAllocator<1024>>>::EnsureLargerCapacity(
             v138,
             v69,
             0);
    v128 = v110;
    v111 = v110;
    if ( v110 == -2147024882 )
    {
      if ( Block )
      {
        free(Block);
        Block = 0;
        HIDWORD(v134) = 0;
      }
      LODWORD(v134) = 0;
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
      v114 = CDImageContext::EnsureRenderingMode(this, v135, v112, v113);
      if ( v128 >= 0 )
        v128 = v114;
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
      if ( (_QWORD)v132 )
      {
        v115 = v131;
        *(_BYTE *)(v132 + 16) = 0;
        *((_QWORD *)v115 + 38) = *((_QWORD *)&v132 + 1);
      }
      win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v132 + 8);
      win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v132);
      *((_QWORD *)this + 587) = v137;
      return 0;
    }
    else
    {
      if ( v110 >= 0 )
      {
        v68 = v134;
LABEL_79:
        v70 = 1;
        for ( k = 0; k < v68; ++k )
        {
          if ( !v70 )
            goto LABEL_149;
          v121 = (char *)Block + 152 * k;
          v136 = *(struct tagRECT *)(*((_QWORD *)v121 + 13) + 48LL);
          if ( !(unsigned __int8)IsRectEmptyOrWithinRect<tagRECT,tagRECT>(v121 + 112, &v136) )
            goto LABEL_150;
          if ( !CDImageContext::LockCachedTile(v122, (struct TILE *)v121) )
            goto LABEL_149;
          if ( v121[52] && *(_DWORD *)(*(_QWORD *)(**((_QWORD **)v121 + 1) + 64LL) + 112LL) <= 1u )
            v70 = 0;
          v68 = v134;
        }
        if ( !v70 )
        {
LABEL_149:
          v73 = (_QWORD **)Block;
LABEL_150:
          for ( m = 0; m < k; ++m )
          {
            v109 = *v73[19 * m + 1];
            if ( v109 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 24LL))(v109);
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
          *v150 = v57;
LABEL_84:
          v44 = v128;
          if ( v73 )
          {
            free(v73);
            Block = 0;
            HIDWORD(v134) = 0;
          }
          LODWORD(v134) = 0;
          CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v188);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v187);
          CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>::~CArray<CRefCountPtr<CPixelShader>,CDefaultTraits<CRefCountPtr<CPixelShader>>,CDefaultAllocator>(v186);
          CTransformNode::~CTransformNode((CTransformNode *)v185);
          CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
          v76 = CDImageContext::EnsureRenderingMode(this, v135, v74, v75);
          if ( v128 >= 0 )
            v128 = v76;
          CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
          if ( !(_QWORD)v132 )
            goto LABEL_91;
          *(_BYTE *)(v132 + 16) = 0;
LABEL_90:
          *((_QWORD *)v131 + 38) = *((_QWORD *)&v132 + 1);
LABEL_91:
          win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v132 + 8);
          win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v132);
LABEL_92:
          *((_QWORD *)this + 587) = v137;
          return (unsigned int)v44;
        }
        v116 = v138;
        while ( 1 )
        {
          v123 = (__int64 *)*((_QWORD *)Block + 19 * v72 + 1);
          v124 = *((unsigned int *)v116 + 2);
          v125 = v124 + 1;
          if ( (_DWORD)v124 != *((_DWORD *)v116 + 3) )
            break;
          v138 = (__int64 *)*((_QWORD *)Block + 19 * v72 + 1);
          if ( (int)CArray<CRefCountPtr<BitmapRealization>,CDefaultTraits<CRefCountPtr<BitmapRealization>>,CIndirectAllocator<CArenaAllocator<1024>>>::EnsureLargerCapacity(
                      v116,
                      v125,
                      &v138) >= 0 )
          {
            v126 = *((unsigned int *)v116 + 2);
            *((_DWORD *)v116 + 2) = v126 + 1;
            v127 = *v138;
LABEL_187:
            *(_QWORD *)(*v116 + 8 * v126) = v127;
            SafeAddRef<RefCountedObject<CMultiProcessElementBase,LockingRequired,DeleteOnZeroReference>>();
          }
          if ( ++v72 >= (unsigned int)v134 )
            goto LABEL_83;
        }
        *((_DWORD *)v116 + 2) = v125;
        v126 = v124;
        v127 = *v123;
        goto LABEL_187;
      }
      DoStackCapture(v110);
      v128 = v111;
      CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>::~CArray<D2D1_INPUT_DESCRIPTION,CDIHeapRenderInfoRenderDataCommon<CDIPSRenderData>::CInputDescriptionTraits,CDefaultAllocator>(&Block);
      CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
      CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
      CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
      CRestoreRenderModeOnExit::~CRestoreRenderModeOnExit((CRestoreRenderModeOnExit *)v151);
      CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
      CDImageContext::CReentrancyCycleGuard::~CReentrancyCycleGuard((CDImageContext::CReentrancyCycleGuard *)&v131);
      *((_QWORD *)this + 587) = v137;
      return v111;
    }
  }
  else
  {
    CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>::~CArray<CLinkingNode *,CDefaultTraits<CLinkingNode *>,CInitialAllocAllocator<128,CDefaultAllocator>>(&v156);
    CBrushTransformNode::~CBrushTransformNode((CBrushTransformNode *)v184);
    CInputTransformNode::~CInputTransformNode((CInputTransformNode *)v177);
    v106 = CDImageContext::EnsureRenderingMode(this, v13, v104, v105);
    if ( v128 >= 0 )
      v128 = v106;
    CDImageContext::CDImageContextStateSaver::~CDImageContextStateSaver((CDImageContext::CDImageContextStateSaver *)v140);
    if ( (_QWORD)v132 )
    {
      v107 = v131;
      *(_BYTE *)(v132 + 16) = 0;
      *((_QWORD *)v107 + 38) = *((_QWORD *)&v132 + 1);
    }
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>((char *)&v132 + 8);
    win_scope::com_ptr<BitmapRealization *>::~com_ptr<BitmapRealization *>(&v132);
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
