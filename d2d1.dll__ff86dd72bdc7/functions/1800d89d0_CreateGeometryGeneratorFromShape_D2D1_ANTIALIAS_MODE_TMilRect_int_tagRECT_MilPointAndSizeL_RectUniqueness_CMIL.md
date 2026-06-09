# CreateGeometryGeneratorFromShape(D2D1_ANTIALIAS_MODE,TMilRect_<int,tagRECT,MilPointAndSizeL,RectUniqueness::_CMILSurfaceRect_> const *,CShapeBase const *,MILMatrix3x2 const *,BlendingData const *,float *,CBufferDispenser *,CShape *,CShape *,CD3DDeviceCommon *,bool,FillTessellator::Flags,FillModeModifier::Flags,GeometryRendering::Flags,IGeometryGenerator * *)

- ea: `0x1800d89d0`
- end: `0x1800d99e1`
- name: `?CreateGeometryGeneratorFromShape@@YAJW4D2D1_ANTIALIAS_MODE@@PEBV?$TMilRect_@HUtagRECT@@UMilPointAndSizeL@@U_CMILSurfaceRect_@RectUniqueness@@@@PEBVCShapeBase@@PEBVMILMatrix3x2@@PEBUBlendingData@@PEAMPEAVCBufferDispenser@@PEAVCShape@@7PEAVCD3DDeviceCommon@@_NW4Flags@FillTessellator@@W49FillModeModifier@@W49GeometryRendering@@PEAPEAUIGeometryGenerator@@@Z`
- size: `4113`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d7df0`
- `0x1800dd3cc`
- `0x180143be0`
- `0x1802279e0`

## callees

- `0x1800152a0`
- `0x18001d4bc`
- `0x18001fd58`
- `0x180036310`
- `0x180061710`
- `0x1800622c0`
- `0x1800d6140`
- `0x1800d89d0`
- `0x1800d9ed0`
- `0x1800da800`
- `0x1800dada0`
- `0x18010e778`
- `0x18010e950`
- `0x18019aab4`
- `0x1801ce68c`
- `0x1801ceadc`
- `0x1801edc20`
- `0x18025b100`
- `0x18025b148`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d97e8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d9939`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d97e8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d9939`

## pseudocode

```c
__int64 __fastcall CreateGeometryGeneratorFromShape(
        int a1,
        const __m128i *a2,
        const struct CShapeBase *a3,
        float *a4,
        BlendingData *a5,
        __int64 a6,
        CBufferDispenser *a7,
        void *a8,
        __int64 a9,
        __int64 a10,
        char a11,
        int a12,
        unsigned int a13,
        char a14,
        unsigned __int64 *a15)
{
  const struct CShapeBase *v15; // rsi
  __int64 v19; // rax
  __m128i v20; // xmm12
  __m128i v21; // xmm14
  __m128i v22; // xmm13
  float v23; // xmm6_4
  float v24; // xmm5_4
  __m128i v25; // xmm11
  float v26; // xmm13_4
  __m128i v27; // xmm8
  float v28; // xmm7_4
  __m128i v29; // xmm9
  float v30; // xmm2_4
  float v31; // xmm15_4
  __m128i v32; // xmm1
  __m128i v33; // xmm0
  __m128i v34; // xmm10
  BOOL v35; // ecx
  int v36; // eax
  bool v37; // cc
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  bool v43; // al
  unsigned __int64 v44; // rbx
  signed int v45; // r8d
  float v46; // xmm1_4
  __m128 v47; // xmm0
  __int64 v48; // rax
  void (__fastcall *v49)(const struct CShapeBase *, void ***, _QWORD, _QWORD); // rax
  unsigned int v50; // r15d
  signed int v51; // eax
  float v52; // xmm6_4
  float v53; // xmm9_4
  float v54; // xmm4_4
  float v55; // xmm5_4
  float v56; // xmm2_4
  int v57; // eax
  float v58; // xmm11_4
  float v59; // xmm10_4
  float v60; // xmm13_4
  float v61; // xmm12_4
  float v62; // xmm3_4
  float v63; // xmm0_4
  float v64; // xmm2_4
  float v65; // xmm11_4
  float v66; // xmm8_4
  float v67; // xmm7_4
  float v68; // xmm1_4
  float v69; // xmm13_4
  float v70; // xmm9_4
  float v71; // xmm6_4
  float v72; // xmm5_4
  float v73; // xmm4_4
  float v74; // xmm2_4
  float v75; // xmm8_4
  float v76; // xmm7_4
  float v77; // xmm1_4
  float v78; // xmm6_4
  float v79; // xmm7_4
  float v80; // xmm1_4
  __int64 v82; // rcx
  __m128i v83; // xmm0
  bool v84; // r9
  int v85; // xmm1_4
  _QWORD *v86; // rdx
  int v87; // eax
  int v88; // ecx
  int v89; // eax
  unsigned int v90; // ebx
  __int64 v91; // rax
  void (__fastcall *v92)(void ***, void *, _QWORD); // rax
  int v93; // edi
  __int64 v94; // rax
  int v95; // eax
  unsigned int v96; // edi
  void *v97; // r8
  __int64 v98; // rax
  __int64 v99; // rdx
  void *v100; // rax
  unsigned __int64 v101; // rax
  const struct MILMatrix3x2 *v102; // r9
  const struct CShapeBase *v103; // rdi
  const struct D2D_RECT_F *v104; // rdx
  int v105; // eax
  unsigned int v106; // esi
  __int64 v107; // rax
  unsigned __int64 v108; // rax
  unsigned int v109; // [rsp+48h] [rbp-C0h]
  int v110; // [rsp+48h] [rbp-C0h]
  void **v111; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v112; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v113; // [rsp+60h] [rbp-A8h]
  __int64 v114; // [rsp+68h] [rbp-A0h]
  int v115[2]; // [rsp+70h] [rbp-98h]
  __int64 v116; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 *v117; // [rsp+80h] [rbp-88h]
  __int64 v118[2]; // [rsp+88h] [rbp-80h] BYREF
  void **v119; // [rsp+98h] [rbp-70h] BYREF
  __m128 v120; // [rsp+A0h] [rbp-68h]
  __int64 v121; // [rsp+B0h] [rbp-58h]
  __int128 v122; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v123[2]; // [rsp+C8h] [rbp-40h] BYREF
  __m128 v124; // [rsp+D8h] [rbp-30h] BYREF
  int v125; // [rsp+E8h] [rbp-20h]
  int v126; // [rsp+ECh] [rbp-1Ch]
  __int64 TransformFunction; // [rsp+F0h] [rbp-18h]
  void **v128; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v129; // [rsp+200h] [rbp+F8h]
  __m128 v130; // [rsp+210h] [rbp+108h]
  float v131; // [rsp+220h] [rbp+118h]
  float v132; // [rsp+224h] [rbp+11Ch]
  int v133; // [rsp+228h] [rbp+120h]
  int v134; // [rsp+230h] [rbp+128h]
  int v135; // [rsp+244h] [rbp+13Ch]
  void ***v136; // [rsp+248h] [rbp+140h]
  void *Block[2]; // [rsp+258h] [rbp+150h] BYREF
  unsigned __int64 v138; // [rsp+268h] [rbp+160h]
  __int32 v139; // [rsp+270h] [rbp+168h]
  __int32 v140; // [rsp+274h] [rbp+16Ch]

  v15 = a3;
  Block[0] = a8;
  v117 = a15;
  v19 = *(_QWORD *)a3;
  v116 = 0;
  (*(void (__fastcall **)(const struct CShapeBase *, _QWORD, _QWORD, __int128 *))(v19 + 184))(a3, 0, 0, &v122);
  v20 = (__m128i)(unsigned int)v122;
  v21 = (__m128i)DWORD2(v122);
  v22 = (__m128i)DWORD1(v122);
  if ( *((float *)&v122 + 2) > *(float *)&v122 && *((float *)&v122 + 3) > *((float *)&v122 + 1) )
  {
    v23 = a4[4];
    v24 = a4[5];
    v25 = (__m128i)(unsigned int)v122;
    *(float *)v25.m128i_i32 = *(float *)&v122 * *a4;
    *(float *)v20.m128i_i32 = *(float *)&v122 * a4[1];
    v34 = (__m128i)DWORD2(v122);
    v26 = *((float *)&v122 + 1) * a4[3];
    *(float *)v34.m128i_i32 = *((float *)&v122 + 2) * *a4;
    v27 = v25;
    v28 = *((float *)&v122 + 1) * a4[2];
    v29 = v20;
    v30 = *((float *)&v122 + 3) * a4[2];
    v31 = *((float *)&v122 + 3) * a4[3];
    v33 = v34;
    *(float *)v21.m128i_i32 = *((float *)&v122 + 2) * a4[1];
    *(float *)v29.m128i_i32 = (float)(*(float *)v20.m128i_i32 + v26) + v24;
    v32 = v21;
    *(float *)v27.m128i_i32 = (float)(*(float *)v25.m128i_i32 + v28) + v23;
    *(float *)v25.m128i_i32 = (float)(*(float *)v25.m128i_i32 + v30) + v23;
    *(float *)v20.m128i_i32 = (float)(*(float *)v20.m128i_i32 + v31) + v24;
    *(float *)v33.m128i_i32 = (float)(*(float *)v34.m128i_i32 + v30) + v23;
    *(float *)v34.m128i_i32 = (float)(*(float *)v34.m128i_i32 + v28) + v23;
    v35 = (_mm_cvtsi128_si32(v27) & 0x7FFFFFFFu) > 0x48FFFFE0;
    *(float *)v22.m128i_i32 = (float)(v26 + *(float *)v21.m128i_i32) + v24;
    v36 = _mm_cvtsi128_si32(v25);
    if ( (_mm_cvtsi128_si32(v29) & 0x7FFFFFFFu) > 0x48FFFFE0 )
      v35 = 1;
    v37 = (v36 & 0x7FFFFFFFu) <= 0x48FFFFE0;
    v38 = _mm_cvtsi128_si32(v20);
    if ( !v37 )
      v35 = 1;
    v37 = (v38 & 0x7FFFFFFFu) <= 0x48FFFFE0;
    v39 = _mm_cvtsi128_si32(v33);
    if ( !v37 )
      v35 = 1;
    v37 = (v39 & 0x7FFFFFFFu) <= 0x48FFFFE0;
    *(float *)v32.m128i_i32 = (float)(*(float *)v21.m128i_i32 + v31) + v24;
    v40 = _mm_cvtsi128_si32(v32);
    if ( !v37 )
      v35 = 1;
    v37 = (v40 & 0x7FFFFFFFu) <= 0x48FFFFE0;
    v41 = _mm_cvtsi128_si32(v34);
    if ( !v37 )
      v35 = 1;
    v37 = (v41 & 0x7FFFFFFFu) <= 0x48FFFFE0;
    v42 = _mm_cvtsi128_si32(v22);
    if ( !v37 )
      v35 = 1;
    if ( (v42 & 0x7FFFFFFFu) > 0x48FFFFE0 || v35 )
    {
      CShape::Reset((CShape *)Block[0], 1);
      v102 = (const struct MILMatrix3x2 *)a4;
      v103 = (const struct CShapeBase *)Block[0];
      v105 = CShapeBase::ClipWithRect(v15, v104, (struct CShape *)Block[0], v102, 0.0);
      v106 = v105;
      if ( v105 < 0 )
      {
        DoStackCapture(v105);
        DoStackCapture(v106);
        return v106;
      }
      v107 = *(_QWORD *)v103;
      *(_OWORD *)v118 = 0;
      (*(void (__fastcall **)(const struct CShapeBase *, _QWORD, _QWORD, __int64 *))(v107 + 184))(v103, 0, 0, v118);
      v15 = v103;
      a4 = (float *)&IdentityMatrix3x2;
    }
  }
  v43 = 0;
  if ( a10 && *(_DWORD *)(a10 + 192) == 1297040209 )
    v43 = *(_BYTE *)(a10 + 250) == 0;
  if ( a1 != 1 && !v43 )
  {
    v109 = a13;
    goto LABEL_23;
  }
  v109 = a13;
  if ( (a13 & 1) != 0 )
  {
    *(_DWORD *)(a9 + 56) = 0;
    *(_WORD *)(a9 + 352) = 0;
    v82 = 0;
    *(_DWORD *)(a9 + 136) = 0;
    *(_DWORD *)(a9 + 272) = 0;
    *(_DWORD *)(a9 + 312) = 0;
    *(_DWORD *)(a9 + 344) = 0;
    v110 = 0;
    if ( *(_DWORD *)(a9 + 32) )
    {
      v97 = (void *)(a9 + 104);
      do
      {
        v98 = *(_QWORD *)(a9 + 8);
        v99 = (unsigned int)v82;
        v118[0] = (unsigned int)v82;
        v100 = *(void **)(v98 + 8 * v82);
        Block[0] = v100;
        if ( v100 != v97 )
        {
          if ( v100 )
          {
            CFigureData::~CFigureData((CFigureData *)v100);
            operator delete(Block[0]);
            LODWORD(v82) = v110;
            v97 = (void *)(a9 + 104);
            v99 = v118[0];
          }
          *(_QWORD *)(*(_QWORD *)(a9 + 8) + 8 * v99) = 0;
        }
        v82 = (unsigned int)(v82 + 1);
        v110 = v82;
      }
      while ( (unsigned int)v82 < *(_DWORD *)(a9 + 32) );
    }
    *(_DWORD *)(a9 + 32) = 0;
    *(_DWORD *)(a9 + 80) = 0;
    *(_DWORD *)(a9 + 100) = 0;
    v83 = _mm_loadu_si128(a2);
    v119 = &CRectangle::`vftable';
    v111 = &CD2DSinkToShapeBuilderAdapter::`vftable';
    v112 = 0;
    v113 = a9;
    v114 = 0;
    *(_QWORD *)v115 = 0;
    Block[0] = 0;
    v120 = _mm_cvtepi32_ps(v83);
    win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
      Block,
      &v112);
    if ( Block[0] )
      (*(void (__fastcall **)(void *))(*(_QWORD *)Block[0] + 16LL))(Block[0]);
    v111 = &ComObjectNoRef<CD2DSinkToShapeBuilderAdapter>::`vftable';
    if ( (*(unsigned int (__fastcall **)(const struct CShapeBase *))(*(_QWORD *)v15 + 24LL))(v15) )
    {
      v93 = CShapeBase::Combine(
              (const struct CShapeBase *)&v119,
              v15,
              D2D1_COMBINE_MODE_EXCLUDE,
              v84,
              (struct ID2D1SimplifiedGeometrySink *)&v111,
              0,
              (const struct MILMatrix3x2 *)a4,
              0.25);
      if ( v93 < 0 )
        goto LABEL_108;
    }
    else
    {
      v123[0] = &CTransformSink::`vftable';
      v123[1] = &v111;
      if ( a4 )
      {
        v85 = *((_DWORD *)a4 + 5);
        v124 = *(__m128 *)a4;
        v125 = *((_DWORD *)a4 + 4);
        v126 = v85;
        TransformFunction = MILMatrix3x2::GetTransformFunction(&v124);
        v123[0] = &ComObjectNoRef<CTransformSink>::`vftable';
        if ( !D2D1::Matrix3x2F::IsIdentity((D2D1::Matrix3x2F *)a4) )
          v86 = v123;
      }
      else
      {
        TransformFunction = MILMatrix3x2::GetTransformFunction(&v124);
        v123[0] = &ComObjectNoRef<CTransformSink>::`vftable';
      }
      v91 = *(_QWORD *)v15;
      *(_OWORD *)Block = 0;
      (*(void (__fastcall **)(const struct CShapeBase *, _QWORD *, _QWORD, _QWORD))(v91 + 56))(v15, v86, 0, 0);
      v139 = v120.m128_i32[0];
      v92 = (void (__fastcall *)(void ***, void *, _QWORD))v111[5];
      v138 = v120.m128_u64[1];
      v140 = v120.m128_i32[3];
      Block[1] = (void *)__PAIR64__(v120.m128_u32[1], v120.m128_u32[2]);
      Block[0] = (void *)_mm_unpacklo_ps((__m128)v120.m128_u32[0], (__m128)v120.m128_u32[1]).m128_u64[0];
      v92(&v111, Block[0], 0);
      ((void (__fastcall *)(void ***, void **, __int64))v111[6])(&v111, &Block[1], 3);
      ((void (__fastcall *)(void ***, __int64))v111[8])(&v111, 1);
    }
    v93 = v115[1];
    if ( v115[1] >= 0 )
    {
      if ( !v114 && v113 )
      {
        if ( v112 && dword_1805DC388 != -1 )
          (*(void (**)(void))(*(_QWORD *)v112 + 120LL))();
LABEL_78:
        v113 = 0;
        Block[0] = 0;
        win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
          Block,
          &v112);
        if ( Block[0] )
          (*(void (__fastcall **)(void *))(*(_QWORD *)Block[0] + 16LL))(Block[0]);
        if ( v93 >= 0 )
        {
          a4 = (float *)&IdentityMatrix3x2;
          v109 = a13 & 0xFFFFFFFE;
          v111 = &CD2DSinkToShapeBuilderAdapter::`vftable';
          v15 = (const struct CShapeBase *)a9;
          if ( v112 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
          goto LABEL_23;
        }
LABEL_108:
        DoStackCapture(v93);
        v111 = &CD2DSinkToShapeBuilderAdapter::`vftable';
        if ( v112 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
        return (unsigned int)v93;
      }
      v93 = -2003238911;
    }
    DoStackCapture(v93);
    goto LABEL_78;
  }
LABEL_23:
  v122 = 0;
  if ( !a10 )
    goto LABEL_25;
  if ( !*(_QWORD *)(a10 + 88) )
    goto LABEL_25;
  v94 = *(_QWORD *)(a10 + 96);
  if ( (v94 & 0x400) == 0 || (v94 & 0x800) == 0 || a11 )
    goto LABEL_25;
  if ( a5 && a1 != 1 && !BlendingData::SupportsWarpTessellator(a5) )
  {
LABEL_26:
    v118[0] = 0;
    if ( a7 && *((_QWORD *)a7 + 2) >= 0x8E0u )
    {
      v44 = (*((_QWORD *)a7 + 1) + 15LL) & 0xFFFFFFFFFFFFFFF8uLL;
      *(_QWORD *)(v44 - 8) = a7;
      *((_QWORD *)a7 + 1) += 2272LL;
      *((_QWORD *)a7 + 2) -= 2272LL;
      ++*((_DWORD *)a7 + 6);
    }
    else
    {
      v44 = 0;
      v101 = (unsigned __int64)malloc(0x8E0u);
      if ( v101 )
      {
        v44 = (v101 + 15) & 0xFFFFFFFFFFFFFFF8uLL;
        *(_QWORD *)(v44 - 8) = v101 | 1;
      }
    }
    if ( v44 )
    {
      *(_QWORD *)v44 = &CHwRasterizer::`vftable';
      *(_QWORD *)(v44 + 48) = v44 + 80;
      *(_DWORD *)(v44 + 32) = 0;
      *(_QWORD *)(v44 + 40) = v44 + 64;
      *(_DWORD *)(v44 + 36) = 33;
      *(_DWORD *)(v44 + 72) = 33;
      *(_QWORD *)(v44 + 64) = 0;
    }
    else
    {
      v44 = 0;
    }
    Block[0] = 0;
    win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
      Block,
      v118);
    if ( Block[0] )
      win_scope::close_delete::close<CHwRasterizer>(Block);
    v118[0] = v44;
    if ( v44 )
    {
      if ( dword_1805DC088 != -1 )
      {
        *(_QWORD *)(v44 + 1680) = 0;
        v45 = 0x80000000;
        *(_DWORD *)(v44 + 8) = 16 * a2->m128i_i32[0];
        *(_DWORD *)(v44 + 12) = 16 * a2->m128i_i32[1];
        *(_DWORD *)(v44 + 16) = 16 * a2->m128i_i32[2];
        *(_DWORD *)(v44 + 20) = 16 * a2->m128i_i32[3];
        *(_QWORD *)(v44 + 1736) = v44 + 1752;
        *(_QWORD *)(v44 + 1696) = v44 + 1736;
        *(_QWORD *)(v44 + 1704) = v44 + 1736;
        *(_QWORD *)(v44 + 1712) = v44 + 1768;
        *(_QWORD *)(v44 + 1720) = v44 + 2184;
        HIDWORD(v119) = 0;
        *(_DWORD *)(v44 + 1744) = 0x80000000;
        v121 = 0;
        *(_DWORD *)(v44 + 1748) = 0;
        *(_DWORD *)(v44 + 1760) = 0x7FFFFFFF;
        *(_DWORD *)(v44 + 1764) = -559038737;
        *(_QWORD *)(v44 + 1752) = 0;
        *(_QWORD *)(v44 + 1728) = 0;
        *(_QWORD *)(v44 + 2248) = v44 + 1728;
        v120.m128_u64[1] = v44 + 32;
        *(_BYTE *)(v44 + 1692) = v109 & 1;
        LODWORD(v119) = 0x80000000;
        LOBYTE(v121) = 1;
        v120.m128_u64[0] = v44 + 8;
        if ( *(_DWORD *)(v44 + 16) > *(_DWORD *)(v44 + 8) && *(_DWORD *)(v44 + 20) > *(_DWORD *)(v44 + 12) )
        {
          v46 = a4[4];
          v129 = *(_OWORD *)(v44 + 8);
          v128 = &CD2DSinkToEdgeListAdapter::`vftable';
          v47 = *(__m128 *)a4;
          v136 = &v119;
          v48 = *(_QWORD *)v15;
          v133 = 0;
          v49 = *(void (__fastcall **)(const struct CShapeBase *, void ***, _QWORD, _QWORD))(v48 + 56);
          v134 = 0;
          v130 = _mm_mul_ps(v47, (__m128)_xmm);
          v135 = 0;
          v47.m128_f32[0] = a4[5];
          v131 = (float)(v46 - 0.5) * 16.0;
          v132 = (float)(v47.m128_f32[0] - 0.5) * 16.0;
          v49(v15, &v128, 0, 0);
          v50 = v135;
          if ( v135 < 0 )
          {
            v88 = v135;
            goto LABEL_112;
          }
          if ( (v109 & 1) != 0 )
          {
            v87 = AddComplementEdges((struct CInitializeEdgesContext *)&v119);
            v50 = v87;
            if ( v87 < 0 )
            {
              v88 = v87;
LABEL_112:
              DoStackCapture(v88);
              DoStackCapture(v50);
              DoStackCapture(v50);
              win_scope::close_delete::close<CHwRasterizer>(v118);
              return v50;
            }
          }
          v45 = (int)v119;
        }
        v51 = (*(int *)(v44 + 20) >> 1) & 0xFFFFFFF8;
        if ( v45 < v51 )
          v51 = v45;
        *(_DWORD *)(v44 + 24) = v51;
        *(_DWORD *)(v44 + 1688) = (*(__int64 (__fastcall **)(const struct CShapeBase *))(*(_QWORD *)v15 + 24LL))(v15);
        (*(void (__fastcall **)(const struct CShapeBase *, _QWORD, _QWORD, void **))(*(_QWORD *)v15 + 184LL))(
          v15,
          0,
          0,
          Block);
        v52 = *(float *)&Block[1];
        v53 = *(float *)Block;
        v54 = *((float *)&Block[1] + 1);
        v55 = *((float *)Block + 1);
        if ( *(float *)&Block[1] < *(float *)Block || *((float *)&Block[1] + 1) < *((float *)Block + 1) )
        {
          v57 = 0;
        }
        else
        {
          LODWORD(v56) = COERCE_UNSIGNED_INT(
                           (float)((float)(*a4 * a4[3]) - (float)(a4[2] * a4[1]))
                         * (float)((float)(*(float *)&Block[1] - *(float *)Block)
                                 * (float)(*((float *)&Block[1] + 1) - *((float *)Block + 1))))
                       & _xmm;
          if ( v56 > 2147483500.0 )
            v57 = -1;
          else
            v57 = (int)v56;
        }
        *(_DWORD *)(v44 + 2256) = v57;
        if ( v53 > v52 || v55 > v54 )
        {
          *(_OWORD *)(v44 + 1664) = *(_OWORD *)Block;
        }
        else
        {
          v58 = a4[2];
          v59 = a4[4];
          v60 = a4[3];
          v61 = a4[5];
          v62 = v58 * v54;
          v63 = *a4 * v52;
          v64 = v60 * v54;
          v65 = v58 * v55;
          v66 = *a4 * v53;
          v67 = a4[1] * v53;
          v68 = a4[1] * v52;
          v69 = v60 * v55;
          v70 = (float)(v63 + v65) + v59;
          v71 = (float)(v68 + v69) + v61;
          v72 = (float)(v62 + v66) + v59;
          v73 = (float)(v64 + v67) + v61;
          v74 = (float)(v64 + v68) + v61;
          v75 = (float)(v66 + v65) + v59;
          v76 = (float)(v67 + v69) + v61;
          v77 = fminf(v71, v76);
          v78 = fmaxf(v71, v76);
          v79 = fminf(v73, v77);
          v80 = (float)(v62 + v63) + v59;
          *(float *)(v44 + 1664) = fminf(v80, fminf(v72, fminf(v70, v75)));
          *(float *)(v44 + 1668) = fminf(v74, v79);
          *(float *)(v44 + 1672) = fmaxf(v80, fmaxf(v72, fmaxf(v70, v75)));
          *(float *)(v44 + 1676) = fmaxf(v74, fmaxf(v73, v78));
        }
        Block[0] = 0;
LABEL_50:
        std::swap<win_dox::IXpsOMPackageTargetInternal *,0>(Block, &v116);
        if ( !Block[0] )
        {
LABEL_52:
          *v117 = v44;
          return 0;
        }
LABEL_51:
        win_scope::close_delete::close<OfferableBuffer>(Block);
        goto LABEL_52;
      }
      DoStackCapture(-2147024882);
      win_scope::close_delete::close<CHwRasterizer>(v118);
      return 2147942414LL;
    }
LABEL_53:
    DoStackCapture(-2147024882);
    return 2147942414LL;
  }
  if ( (a14 & 2) == 0 )
  {
    v118[0] = 0;
    if ( a7 && *((_QWORD *)a7 + 2) >= 0x30u )
    {
      v44 = (*((_QWORD *)a7 + 1) + 15LL) & 0xFFFFFFFFFFFFFFF8uLL;
      *(_QWORD *)(v44 - 8) = a7;
      *((_QWORD *)a7 + 1) += 48LL;
      *((_QWORD *)a7 + 2) -= 48LL;
      ++*((_DWORD *)a7 + 6);
    }
    else
    {
      v44 = 0;
      v108 = (unsigned __int64)malloc(0x30u);
      if ( v108 )
      {
        v44 = (v108 + 15) & 0xFFFFFFFFFFFFFFF8uLL;
        *(_QWORD *)(v44 - 8) = v108 | 1;
      }
    }
    if ( v44 )
    {
      *(_QWORD *)v44 = &CWarpTessellator::`vftable';
      *(_QWORD *)(v44 + 32) = 0;
    }
    else
    {
      v44 = 0;
    }
    Block[0] = 0;
    win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(
      Block,
      v118);
    if ( Block[0] )
      win_scope::close_delete::close<CWarpTessellator>(Block);
    v118[0] = v44;
    if ( !v44 )
      goto LABEL_53;
    if ( dword_1805DC088 == -1 )
    {
      DoStackCapture(-2147024882);
      win_scope::close_delete::close<CWarpTessellator>(v118);
      return 2147942414LL;
    }
    v95 = CWarpTessellator::Initialize(v44, a10, v15, a4, a2, a1, v109);
    v96 = v95;
    if ( v95 >= 0 )
    {
      Block[0] = 0;
      goto LABEL_50;
    }
    DoStackCapture(v95);
    win_scope::close_delete::close<CWarpTessellator>(v118);
    return v96;
  }
  else
  {
LABEL_25:
    if ( a1 != 1 )
      goto LABEL_26;
    v118[0] = 0;
    v89 = CShapeBase::SetupFillTessellator(v15, (MILMatrix3x2 *)a4, a7, a12, (__int64)v118);
    v90 = v89;
    if ( v89 >= 0 )
    {
      Block[0] = 0;
      std::swap<win_dox::IXpsOMPackageTargetInternal *,0>(Block, &v116);
      v44 = v118[0];
      if ( !Block[0] )
        goto LABEL_52;
      goto LABEL_51;
    }
    DoStackCapture(v89);
    if ( v118[0] )
      win_scope::close_delete::close<OfferableBuffer>(v118);
    return v90;
  }
}

```

## disassembly

```asm
0x1800d89d0  mov     rax, rsp
0x1800d89d3  mov     [rax+8], rbx
0x1800d89d7  push    rbp
0x1800d89d8  push    rsi
0x1800d89d9  push    rdi
0x1800d89da  push    r12
0x1800d89dc  push    r13
0x1800d89de  push    r14
0x1800d89e0  push    r15
0x1800d89e2  lea     rbp, [rax-258h]
0x1800d89e9  sub     rsp, 320h
0x1800d89f0  movaps  xmmword ptr [rax-48h], xmm6
0x1800d89f4  movaps  xmmword ptr [rax-58h], xmm7
0x1800d89f8  movaps  xmmword ptr [rax-68h], xmm8
0x1800d89fd  movaps  xmmword ptr [rax-78h], xmm9
0x1800d8a02  movaps  xmmword ptr [rax-88h], xmm10
0x1800d8a0a  movaps  xmmword ptr [rax-98h], xmm11
0x1800d8a12  movaps  xmmword ptr [rax-0A8h], xmm12
0x1800d8a1a  movaps  xmmword ptr [rax-0B8h], xmm13
0x1800d8a22  movaps  xmmword ptr [rax-0C8h], xmm14
0x1800d8a2a  movaps  xmmword ptr [rax-0D8h], xmm15
0x1800d8a32  mov     rax, cs:__security_cookie
0x1800d8a39  xor     rax, rsp
0x1800d8a3c  mov     [rbp+250h+var_E0], rax
0x1800d8a43  mov     rax, [rbp+250h+arg_38]
0x1800d8a4a  mov     rsi, r8
0x1800d8a4d  mov     r14, [rbp+250h+arg_30]
0x1800d8a54  mov     rdi, r9
0x1800d8a57  mov     rbx, [rbp+250h+arg_40]
0x1800d8a5e  lea     r9, [rbp+250h+var_2A0]
0x1800d8a62  mov     r15, [rbp+250h+arg_48]
0x1800d8a69  mov     r13, rdx
0x1800d8a6c  mov     [rbp+250h+Block], rax
0x1800d8a73  mov     r12d, ecx
0x1800d8a76  mov     rax, [rbp+250h+arg_70]
0x1800d8a7d  xor     edx, edx
0x1800d8a7f  mov     [rsp+350h+var_2D8], rax
0x1800d8a84  mov     rcx, rsi
0x1800d8a87  mov     rax, [r8]
0x1800d8a8a  xor     r8d, r8d
0x1800d8a8d  mov     [rsp+350h+var_2E0], 0
0x1800d8a96  mov     rax, [rax+0B8h]
0x1800d8a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8aa2  movss   xmm12, dword ptr [rbp+250h+var_2A0]
0x1800d8aa8  ucomiss xmm12, xmm12
0x1800d8aac  jp      loc_1800D934E
0x1800d8ab2  movss   xmm14, dword ptr [rbp+250h+var_2A0+8]
0x1800d8ab8  ucomiss xmm14, xmm14
0x1800d8abc  jp      loc_1800D934E
0x1800d8ac2  movss   xmm13, dword ptr [rbp+250h+var_2A0+4]
0x1800d8ac8  ucomiss xmm13, xmm13
0x1800d8acc  jp      loc_1800D934E
0x1800d8ad2  movss   xmm15, dword ptr [rbp+250h+var_2A0+0Ch]
0x1800d8ad8  ucomiss xmm15, xmm15
0x1800d8adc  jp      loc_1800D934E
0x1800d8ae2  comiss  xmm14, xmm12
0x1800d8ae6  mov     edx, 1; bool
0x1800d8aeb  jbe     loc_1800D8C31
0x1800d8af1  comiss  xmm15, xmm13
0x1800d8af5  jbe     loc_1800D8C31
0x1800d8afb  movss   xmm6, dword ptr [rdi+10h]
0x1800d8b00  xor     ecx, ecx
0x1800d8b02  movss   xmm5, dword ptr [rdi+14h]
0x1800d8b07  movaps  xmm11, xmm12
0x1800d8b0b  mulss   xmm11, dword ptr [rdi]
0x1800d8b10  movaps  xmm7, xmm13
0x1800d8b14  mulss   xmm12, dword ptr [rdi+4]
0x1800d8b1a  movaps  xmm10, xmm14
0x1800d8b1e  mulss   xmm13, dword ptr [rdi+0Ch]
0x1800d8b24  movaps  xmm2, xmm15
0x1800d8b28  mulss   xmm10, dword ptr [rdi]
0x1800d8b2d  movaps  xmm8, xmm11
0x1800d8b31  mulss   xmm7, dword ptr [rdi+8]
0x1800d8b36  movaps  xmm9, xmm12
0x1800d8b3a  mulss   xmm2, dword ptr [rdi+8]
0x1800d8b3f  addss   xmm9, xmm13
0x1800d8b44  mulss   xmm15, dword ptr [rdi+0Ch]
0x1800d8b4a  movaps  xmm0, xmm10
0x1800d8b4e  mulss   xmm14, dword ptr [rdi+4]
0x1800d8b54  addss   xmm8, xmm7
0x1800d8b59  addss   xmm9, xmm5
0x1800d8b5e  addss   xmm11, xmm2
0x1800d8b63  addss   xmm12, xmm15
0x1800d8b68  movaps  xmm1, xmm14
0x1800d8b6c  addss   xmm8, xmm6
0x1800d8b71  addss   xmm0, xmm2
0x1800d8b75  addss   xmm1, xmm15
0x1800d8b7a  addss   xmm11, xmm6
0x1800d8b7f  addss   xmm12, xmm5
0x1800d8b84  movd    eax, xmm8
0x1800d8b89  addss   xmm10, xmm7
0x1800d8b8e  addss   xmm0, xmm6
0x1800d8b92  addss   xmm1, xmm5
0x1800d8b96  btr     eax, 1Fh
0x1800d8b9a  addss   xmm13, xmm14
0x1800d8b9f  cmp     eax, 48FFFFE0h
0x1800d8ba4  movd    eax, xmm9
0x1800d8ba9  addss   xmm10, xmm6
0x1800d8bae  setnbe  cl
0x1800d8bb1  btr     eax, 1Fh
0x1800d8bb5  cmp     eax, 48FFFFE0h
0x1800d8bba  addss   xmm13, xmm5
0x1800d8bbf  movd    eax, xmm11
0x1800d8bc4  cmova   ecx, edx
0x1800d8bc7  btr     eax, 1Fh
0x1800d8bcb  cmp     eax, 48FFFFE0h
0x1800d8bd0  movd    eax, xmm12
0x1800d8bd5  cmova   ecx, edx
0x1800d8bd8  btr     eax, 1Fh
0x1800d8bdc  cmp     eax, 48FFFFE0h
0x1800d8be1  movd    eax, xmm0
0x1800d8be5  cmova   ecx, edx
0x1800d8be8  btr     eax, 1Fh
0x1800d8bec  cmp     eax, 48FFFFE0h
0x1800d8bf1  movd    eax, xmm1
0x1800d8bf5  cmova   ecx, edx
0x1800d8bf8  btr     eax, 1Fh
0x1800d8bfc  cmp     eax, 48FFFFE0h
0x1800d8c01  movd    eax, xmm10
0x1800d8c06  cmova   ecx, edx
0x1800d8c09  btr     eax, 1Fh
0x1800d8c0d  cmp     eax, 48FFFFE0h
0x1800d8c12  movd    eax, xmm13
0x1800d8c17  cmova   ecx, edx
0x1800d8c1a  btr     eax, 1Fh
0x1800d8c1e  cmp     eax, 48FFFFE0h
0x1800d8c23  ja      loc_1800D988C
0x1800d8c29  test    ecx, ecx
0x1800d8c2b  jnz     loc_1800D988C
0x1800d8c31  xor     al, al
0x1800d8c33  test    r15, r15
0x1800d8c36  jz      short loc_1800D8C49
0x1800d8c38  cmp     dword ptr [r15+0C0h], 4D4F4351h
0x1800d8c43  jz      loc_1800D9965
0x1800d8c49  cmp     r12d, 1
0x1800d8c4d  jz      loc_1800D91CC
0x1800d8c53  test    al, al
0x1800d8c55  jnz     loc_1800D91CC
0x1800d8c5b  mov     eax, [rbp+250h+arg_60]
0x1800d8c61  mov     dword ptr [rsp+350h+var_310], eax
0x1800d8c65  xorps   xmm0, xmm0
0x1800d8c68  movups  [rbp+250h+var_2A0], xmm0
0x1800d8c6c  test    r15, r15
0x1800d8c6f  jz      short loc_1800D8C7C
0x1800d8c71  cmp     qword ptr [r15+58h], 0
0x1800d8c76  jnz     loc_1800D9556
0x1800d8c7c  cmp     r12d, 1
0x1800d8c80  jz      loc_1800D9368
0x1800d8c86  xor     r15d, r15d
0x1800d8c89  mov     [rbp+250h+var_2D0], r15
0x1800d8c8d  test    r14, r14
0x1800d8c90  jz      loc_1800D97E0
0x1800d8c96  cmp     qword ptr [r14+10h], 8E0h
0x1800d8c9e  jb      loc_1800D97E0
0x1800d8ca4  mov     rbx, [r14+8]
0x1800d8ca8  add     rbx, 0Fh
0x1800d8cac  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1800d8cb0  mov     [rbx-8], r14
0x1800d8cb4  add     qword ptr [r14+8], 8E0h
0x1800d8cbc  add     qword ptr [r14+10h], 0FFFFFFFFFFFFF720h
0x1800d8cc4  inc     dword ptr [r14+18h]
0x1800d8cc8  test    rbx, rbx
0x1800d8ccb  jz      loc_1800D983F
0x1800d8cd1  lea     rcx, [rbx+40h]
0x1800d8cd5  lea     rax, ??_7CHwRasterizer@@6B@; const CHwRasterizer::`vftable'
0x1800d8cdc  mov     [rbx], rax
0x1800d8cdf  lea     rax, [rcx+10h]
0x1800d8ce3  mov     [rbx+30h], rax
0x1800d8ce7  mov     [rbx+20h], r15d
0x1800d8ceb  mov     [rbx+28h], rcx
0x1800d8cef  mov     dword ptr [rbx+24h], 21h ; '!'
0x1800d8cf6  mov     dword ptr [rbx+48h], 21h ; '!'
0x1800d8cfd  mov     [rcx], r15
0x1800d8d00  lea     rdx, [rbp+250h+var_2D0]
0x1800d8d04  mov     [rbp+250h+Block], r15
0x1800d8d0b  lea     rcx, [rbp+250h+Block]
0x1800d8d12  call    ??$Swap@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@?$scope@PEAV?$RefCountedObject@V?$D2DFactoryLocking@VMultiThreadedTrait@@@@ULockingRequired@@UDeleteOnZeroReference@@@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAAXAEAV01@@Z; win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>>::Swap<win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<RefCountedObject<D2DFactoryLocking<MultiThreadedTrait>,LockingRequired,DeleteOnZeroReference> *,win_scope::const_policies<win_scope::com_policies>> &)
0x1800d8d17  cmp     [rbp+250h+Block], r15
0x1800d8d1e  jz      short loc_1800D8D2C
0x1800d8d20  lea     rcx, [rbp+250h+Block]
0x1800d8d27  call    ??$close@VCHwRasterizer@@@close_delete@win_scope@@SAXPEAPEAVCHwRasterizer@@@Z; win_scope::close_delete::close<CHwRasterizer>(CHwRasterizer * *)
0x1800d8d2c  mov     [rbp+250h+var_2D0], rbx
0x1800d8d30  test    rbx, rbx
0x1800d8d33  jz      loc_1800D91B1
0x1800d8d39  cmp     cs:dword_1805DC088, 0FFFFFFFFh
0x1800d8d40  jz      loc_1800D99C9
0x1800d8d46  mov     r14d, dword ptr [rsp+350h+var_310]
0x1800d8d4b  lea     rdx, [rbx+8]
0x1800d8d4f  mov     [rbx+690h], r15
0x1800d8d56  lea     rcx, [rbx+6C0h]
0x1800d8d5d  mov     eax, [r13+0]
0x1800d8d61  mov     r8d, 80000000h
0x1800d8d67  shl     eax, 4
0x1800d8d6a  xorps   xmm0, xmm0
0x1800d8d6d  mov     [rdx], eax
0x1800d8d6f  and     r14d, 1
0x1800d8d73  mov     eax, [r13+4]
0x1800d8d77  shl     eax, 4
0x1800d8d7a  mov     [rbx+0Ch], eax
0x1800d8d7d  mov     eax, [r13+8]
0x1800d8d81  shl     eax, 4
0x1800d8d84  mov     [rbx+10h], eax
0x1800d8d87  mov     eax, [r13+0Ch]
0x1800d8d8b  shl     eax, 4
0x1800d8d8e  mov     [rbx+14h], eax
0x1800d8d91  lea     rax, [rcx+18h]
0x1800d8d95  mov     [rbx+6C8h], rax
0x1800d8d9c  lea     rax, [rcx+8]
0x1800d8da0  mov     [rbx+6A0h], rax
0x1800d8da7  mov     [rbx+6A8h], rax
0x1800d8dae  lea     rax, [rbx+6E8h]
0x1800d8db5  mov     [rbx+6B0h], rax
0x1800d8dbc  lea     rax, [rbx+888h]
0x1800d8dc3  mov     [rbx+6B8h], rax
0x1800d8dca  lea     rax, [rbx+20h]
0x1800d8dce  movups  [rbp+250h+var_2C0], xmm0
0x1800d8dd2  mov     [rbx+6D0h], r8d
0x1800d8dd9  movups  [rbp+250h+var_2B0], xmm0
0x1800d8ddd  mov     [rbx+6D4h], r15d
0x1800d8de4  mov     dword ptr [rbx+6E0h], 7FFFFFFFh
0x1800d8dee  mov     dword ptr [rbx+6E4h], 0DEADBEEFh
0x1800d8df8  mov     [rbx+6D8h], r15
0x1800d8dff  mov     [rcx], r15
0x1800d8e02  mov     [rbx+8C8h], rcx
0x1800d8e09  mov     qword ptr [rbp+250h+var_2B0], rax
0x1800d8e0d  mov     [rbx+69Ch], r14b
0x1800d8e14  mov     dword ptr [rbp+250h+var_2C0], r8d
0x1800d8e18  mov     byte ptr [rbp+250h+var_2B0+8], 1
0x1800d8e1c  mov     qword ptr [rbp+250h+var_2C0+8], rdx
0x1800d8e20  mov     eax, [rdx]
0x1800d8e22  cmp     [rdx+8], eax
0x1800d8e25  jle     loc_1800D8EEB
0x1800d8e2b  mov     eax, [rdx+4]
0x1800d8e2e  cmp     [rdx+0Ch], eax
0x1800d8e31  jle     loc_1800D8EEB
0x1800d8e37  movups  xmm0, xmmword ptr [rdx]
0x1800d8e3a  lea     rax, ??_7CD2DSinkToEdgeListAdapter@@6B@; const CD2DSinkToEdgeListAdapter::`vftable'
0x1800d8e41  xor     r9d, r9d
0x1800d8e44  movaps  xmm3, cs:__xmm@41800000418000004180000041800000
0x1800d8e4b  lea     rdx, [rbp+250h+var_260]
0x1800d8e4f  movss   xmm1, dword ptr [rdi+10h]
0x1800d8e54  xor     r8d, r8d
0x1800d8e57  subss   xmm1, cs:__real@3f000000
0x1800d8e5f  movups  [rbp+250h+var_158], xmm0
0x1800d8e66  mov     [rbp+250h+var_260], rax
0x1800d8e6a  lea     rax, [rbp+250h+var_2C0]
0x1800d8e6e  movups  xmm0, xmmword ptr [rdi]
0x1800d8e71  mov     [rbp+250h+var_110], rax
0x1800d8e78  mov     rcx, rsi
0x1800d8e7b  mov     rax, [rsi]
0x1800d8e7e  mulps   xmm0, xmm3
0x1800d8e81  mov     [rbp+250h+var_130], r15d
0x1800d8e88  mulss   xmm1, xmm3
0x1800d8e8c  mov     rax, [rax+38h]
0x1800d8e90  mov     [rbp+250h+var_128], r15d
0x1800d8e97  movups  [rbp+250h+var_148], xmm0
0x1800d8e9e  mov     [rbp+250h+var_114], r15d
0x1800d8ea5  movss   xmm0, dword ptr [rdi+14h]
0x1800d8eaa  subss   xmm0, cs:__real@3f000000
0x1800d8eb2  movss   [rbp+250h+var_138], xmm1
0x1800d8eba  mulss   xmm0, xmm3
0x1800d8ebe  movss   [rbp+250h+var_134], xmm0
0x1800d8ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8ecb  mov     r15d, [rbp+250h+var_114]
0x1800d8ed2  test    r15d, r15d
0x1800d8ed5  js      loc_1800D97A5
0x1800d8edb  test    r14d, r14d
0x1800d8ede  jnz     loc_1800D9333
0x1800d8ee4  mov     r8d, dword ptr [rbp+250h+var_2C0]
0x1800d8ee8  xor     r15d, r15d
0x1800d8eeb  mov     eax, [rbx+14h]
0x1800d8eee  mov     rcx, rsi
0x1800d8ef1  sar     eax, 1
0x1800d8ef3  and     eax, 0FFFFFFF8h
0x1800d8ef6  cmp     r8d, eax
0x1800d8ef9  cmovl   eax, r8d
0x1800d8efd  mov     [rbx+18h], eax
0x1800d8f00  mov     rax, [rsi]
0x1800d8f03  mov     rax, [rax+18h]
0x1800d8f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8f0c  mov     [rbx+698h], eax
0x1800d8f12  lea     r9, [rbp+250h+Block]
0x1800d8f19  mov     rax, [rsi]
0x1800d8f1c  xor     r8d, r8d
0x1800d8f1f  xor     edx, edx
0x1800d8f21  mov     rcx, rsi
0x1800d8f24  mov     rax, [rax+0B8h]
0x1800d8f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8f30  movss   xmm6, dword ptr [rbp+250h+Block+8]
0x1800d8f38  movss   xmm9, dword ptr [rbp+250h+Block]
0x1800d8f41  comiss  xmm6, xmm9
0x1800d8f45  movss   xmm4, dword ptr [rbp+250h+Block+0Ch]
0x1800d8f4d  movss   xmm5, dword ptr [rbp+250h+Block+4]
0x1800d8f55  jb      loc_1800D932B
0x1800d8f5b  comiss  xmm4, xmm5
0x1800d8f5e  jb      loc_1800D932B
0x1800d8f64  movss   xmm2, dword ptr [rdi]
0x1800d8f68  movaps  xmm1, xmm6
0x1800d8f6b  mulss   xmm2, dword ptr [rdi+0Ch]
0x1800d8f70  subss   xmm1, xmm9
  ... truncated ...
```
