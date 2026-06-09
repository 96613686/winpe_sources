# Jot::Graphics::CreateGdiplusBrushFromPBrush(Jot::Graphics::PBrush,Gdiplus::Brush * *)

- ea: `0x180761558`
- end: `0x180762044`
- name: `?CreateGdiplusBrushFromPBrush@Graphics@Jot@@YAXVPBrush@12@PEAPEAVBrush@Gdiplus@@@Z`
- size: `2796`
- prototype: ``
- caller_count: `11`
- callee_count: `36`
- tags: `file_ops`

## callers

- `0x180761260`
- `0x180761340`
- `0x180761490`
- `0x180ab0110`
- `0x180ab0240`
- `0x180ab0330`
- `0x180ab0430`
- `0x180ab0550`
- `0x180ab0740`
- `0x180ab0bd0`
- `0x180ab0df0`

## callees

- `0x18006eaec`
- `0x18008e374`
- `0x1800b5b5f`
- `0x1802ad37c`
- `0x1802e3f10`
- `0x1802e3f30`
- `0x1802e5160`
- `0x1802e5170`
- `0x1802e5190`
- `0x1804207d0`
- `0x180708380`
- `0x180761558`
- `0x180762320`
- `0x18076239c`
- `0x18076250c`
- `0x180780930`
- `0x1808b869c`
- `0x1808f26ac`
- `0x180aa0428`
- `0x180aa21a8`
- `0x180aa2558`
- `0x180aa26a8`
- `0x180aa2974`
- `0x180aa2b98`
- `0x180aa2c6c`
- `0x180aaeb9c`
- `0x180aaec90`
- `0x180aaed00`
- `0x180aaed70`
- `0x180aaf1b0`
- `0x180aaf224`
- `0x180aaf280`
- `0x180ab1004`
- `0x180ab16a4`
- `0x180ab16cc`
- `0x180ab16f8`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x18076191f`
- `gdiplus!GdipDeleteBrush` at `0x180761a71`
- `gdiplus!GdipDeleteBrush` at `0x180761b60`
- `gdiplus!GdipDeleteBrush` at `0x180761e1f`
- `gdiplus!GdipDeleteBrush` at `0x180761fd4`
- `gdiplus!GdipDeleteBrush` at `0x18076191f`
- `gdiplus!GdipDeleteBrush` at `0x180761a71`
- `gdiplus!GdipDeleteBrush` at `0x180761b60`
- `gdiplus!GdipDeleteBrush` at `0x180761e1f`
- `gdiplus!GdipDeleteBrush` at `0x180761fd4`
- `gdiplus!GdipDeleteMatrix` at `0x180761a7c`
- `gdiplus!GdipDeleteMatrix` at `0x180761fdf`
- `gdiplus!GdipDeleteMatrix` at `0x180761a7c`
- `gdiplus!GdipDeleteMatrix` at `0x180761fdf`
- `gdiplus!GdipCreateSolidFill` at `0x180761b3b`
- `gdiplus!GdipCreateSolidFill` at `0x180761b3b`
- `gdiplus!GdipSetLinePresetBlend` at `0x1807618d1`
- `gdiplus!GdipSetLinePresetBlend` at `0x180761dd1`
- `gdiplus!GdipSetLinePresetBlend` at `0x1807618d1`
- `gdiplus!GdipSetLinePresetBlend` at `0x180761dd1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180761e9f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180761ed4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180761e9f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180761ed4`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1807615d2`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1807615d2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18076192d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18076193c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180761e2d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180761e3c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180761e4f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18076192d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18076193c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180761e2d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180761e3c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180761e4f`

## pseudocode

```c
void __fastcall Jot::Graphics::CreateGdiplusBrushFromPBrush(Jot::Graphics::PBrush *a1, struct Gdiplus::Brush **a2)
{
  Jot::Graphics::PBrush *v3; // rdi
  bool v4; // al
  unsigned int v5; // eax
  unsigned int v6; // r8d
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // r12
  unsigned __int128 v9; // rax
  unsigned __int64 v10; // kr00_8
  unsigned int v11; // r8d
  unsigned __int128 v12; // rax
  struct Jot::Graphics::CColorF *v13; // rax
  struct Jot::Graphics::CColorF *v14; // r13
  unsigned int v15; // r8d
  unsigned __int128 v16; // rax
  const struct Gdiplus::Color *v17; // rax
  const struct Gdiplus::Color *v18; // rsi
  _DWORD *v19; // r14
  float *v20; // rdi
  float v21; // xmm8_4
  float v22; // xmm7_4
  float v23; // xmm6_4
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  const struct Gdiplus::PointF *v27; // rbx
  const struct Gdiplus::PointF *v28; // rax
  unsigned __int64 v29; // rdx
  unsigned int v30; // r8d
  char *v31; // rax
  char *v32; // rbx
  int v33; // edi
  __int64 v34; // rcx
  char *v35; // rax
  char *v36; // rcx
  __int64 v37; // r8
  float *v38; // rdi
  int v39; // eax
  int v40; // ecx
  struct Gdiplus::Brush *v41; // rax
  void *v42; // rdx
  __int64 v43; // rax
  struct ARC::IBitmapBrush *ARC; // rdi
  unsigned int v45; // ebx
  unsigned int v46; // eax
  unsigned int v47; // ebx
  unsigned int StopsCount; // eax
  unsigned int v49; // r8d
  unsigned __int64 v50; // r14
  unsigned __int64 v51; // r12
  unsigned __int128 v52; // rax
  unsigned __int64 v53; // kr10_8
  unsigned int v54; // r8d
  unsigned __int128 v55; // rax
  struct Jot::Graphics::CColorF *v56; // rax
  struct Jot::Graphics::CColorF *v57; // r13
  unsigned int v58; // r8d
  unsigned __int128 v59; // rax
  const struct Gdiplus::Color *v60; // rax
  const struct Gdiplus::Color *v61; // rsi
  _DWORD *v62; // r14
  float *v63; // rdi
  float v64; // xmm8_4
  float v65; // xmm7_4
  float v66; // xmm6_4
  int v67; // ebx
  int v68; // ebx
  int v69; // ebx
  const struct Gdiplus::PointF *EndPoint; // rbx
  const struct Gdiplus::PointF *StartPoint; // rax
  unsigned __int64 v72; // rdx
  unsigned int v73; // r8d
  char *v74; // rax
  char *v75; // rbx
  int v76; // edi
  __int64 v77; // rcx
  char *v78; // rax
  char *v79; // rcx
  __int64 v80; // r8
  int v81; // eax
  int v82; // ecx
  struct Gdiplus::Brush *v83; // rax
  Jot::Graphics::PBrush *v84; // rcx
  __int64 v85; // rax
  struct Gdiplus::Brush **v86; // rcx
  __int64 v87; // rdi
  __int64 v88; // rax
  __int64 v89; // rax
  unsigned int v90; // ebx
  __int64 v91; // rax
  unsigned int v92; // eax
  unsigned int GDIWrapMode; // ebx
  float *v94; // [rsp+40h] [rbp-C0h] BYREF
  struct Jot::Graphics::CColorF *v95; // [rsp+48h] [rbp-B8h] BYREF
  float v96; // [rsp+50h] [rbp-B0h]
  float v97; // [rsp+54h] [rbp-ACh]
  int v98; // [rsp+58h] [rbp-A8h] BYREF
  Jot::Graphics::PBrush *v99; // [rsp+60h] [rbp-A0h] BYREF
  struct Gdiplus::Brush **v100; // [rsp+68h] [rbp-98h] BYREF
  void **v101; // [rsp+70h] [rbp-90h] BYREF
  float *v102; // [rsp+78h] [rbp-88h]
  int v103; // [rsp+80h] [rbp-80h]
  const struct Gdiplus::Color *v104; // [rsp+88h] [rbp-78h]
  _QWORD v105[3]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v106; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v107; // [rsp+B8h] [rbp-48h]

  if ( !a2 )
    return;
  v100 = a2;
  v3 = a1;
  v99 = a1;
  *a2 = 0;
  if ( byte_181516040 < 0 )
    v4 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_181516040);
  else
    v4 = byte_181516040 != 0;
  if ( !v4 )
  {
    if ( Jot::Graphics::PBrush::IsSolidColorBrush(v3) )
    {
      Jot::Graphics::PSolidColorBrush::GetColor(v3, &v95);
      v101 = &Gdiplus::LinearGradientBrush::`vftable';
      v94 = 0;
      v103 = GdipCreateSolidFill(
               (unsigned __int8)(int)(float)(v96 * 255.0)
             | (((unsigned __int8)(int)(float)(*((float *)&v95 + 1) * 255.0)
               | ((((unsigned __int8)(int)(float)(v97 * 255.0) << 8)
                 | (unsigned int)(unsigned __int8)(int)(float)(*(float *)&v95 * 255.0)) << 8)) << 8),
               &v94);
      v102 = v94;
      goto LABEL_56;
    }
    if ( !Jot::Graphics::PBrush::IsLinearGradientBrush(v3) )
    {
      if ( Jot::Graphics::PBrush::IsBitmapBrush(v3) )
      {
        if ( *((_BYTE *)v3 + 8) )
          Mso::ThrowOnInvalidVariant::OnInvalidVariant<void>();
        qi_cast_or_crash<ID2D1BitmapBrush,ID2D1Brush>(&v94, *(_QWORD *)v3);
        qi_cast_or_crash<Jot::CFakeBitmapBrush,ID2D1Brush>(&v99, *(_QWORD *)v3);
        v84 = v99;
        if ( !v99 )
          CrashWithRecovery(0x1E3C3840u, 0);
        v85 = (*(__int64 (__fastcall **)(Jot::Graphics::PBrush *))(*(_QWORD *)v84 + 136LL))(v84);
        qi_cast_or_crash<Jot::IGDIBitmapContainer,IUnknown>(&v100, v85);
        v86 = v100;
        if ( !v100 )
          CrashWithRecovery(0x1E3C3840u, 0);
        v87 = (*((__int64 (__fastcall **)(struct Gdiplus::Brush **))*v86 + 4))(v86);
        v106 = 0;
        v107 = 0;
        v88 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v94);
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v88 + 56LL))(v88, &v106);
        v89 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v94);
        v90 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v89 + 104LL))(v89);
        v91 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v94);
        v92 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 96LL))(v91);
        GDIWrapMode = Jot::GetGDIWrapMode(v92, v90);
        Gdiplus::Matrix::Matrix(
          (Gdiplus::Matrix *)&v95,
          *(float *)&v106,
          *((float *)&v106 + 1),
          *((float *)&v106 + 2),
          *((float *)&v106 + 3),
          *(float *)&v107,
          *((float *)&v107 + 1));
        Gdiplus::TextureBrush::TextureBrush(&v101, v87);
        Gdiplus::TextureBrush::SetTransform(&v101, &v95);
        Gdiplus::TextureBrush::SetWrapMode(&v101, GDIWrapMode);
        *a2 = Gdiplus::Brush::Clone((Gdiplus::Brush *)&v101);
        GdipDeleteBrush(v102);
        GdipDeleteMatrix(v95);
        Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(&v100);
        Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(&v99);
        Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(&v94);
      }
      return;
    }
    StopsCount = Jot::Graphics::PLinearGradientBrush::GetStopsCount(v3);
    v50 = StopsCount;
    v98 = StopsCount;
    v51 = StopsCount;
    v53 = StopsCount;
    v52 = StopsCount * (unsigned __int128)4uLL;
    if ( !is_mul_ok(v53, 4u) )
      *(_QWORD *)&v52 = -1;
    v94 = (float *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)v52, *((unsigned __int64 *)&v52 + 1), v49);
    v55 = v50 * (unsigned __int128)0x10u;
    if ( !is_mul_ok(v50, 0x10u) )
      *(_QWORD *)&v55 = -1;
    v56 = (struct Jot::Graphics::CColorF *)Mso::Memory::Throw::AllocateEx(
                                             (Mso::Memory::Throw *)v55,
                                             *((unsigned __int64 *)&v55 + 1),
                                             v54);
    v57 = v56;
    v95 = v56;
    if ( v56 )
      `vector constructor iterator'(v56, 0x10u, (unsigned int)v51, (void *(*)(void *))Jot::Graphics::CColorF::CColorF);
    else
      v57 = 0;
    v95 = v57;
    Jot::Graphics::PLinearGradientBrush::GetStopsAndColors(v3, v94, v57, v50);
    v59 = v51 * (unsigned __int128)4uLL;
    if ( !is_mul_ok(v51, 4u) )
      *(_QWORD *)&v59 = -1;
    v60 = (const struct Gdiplus::Color *)Mso::Memory::Throw::AllocateEx(
                                           (Mso::Memory::Throw *)v59,
                                           *((unsigned __int64 *)&v59 + 1),
                                           v58);
    v61 = v60;
    if ( v60 )
      `vector constructor iterator'(v60, 4u, v51, (void *(*)(void *))Gdiplus::Color::Color);
    else
      v61 = 0;
    v104 = v61;
    if ( (_DWORD)v50 )
    {
      v62 = v61;
      v63 = (float *)((char *)v57 + 4);
      do
      {
        v64 = v63[1];
        v65 = *v63 * 255.0;
        v66 = v63[2] * 255.0;
        v67 = (unsigned __int8)(int)floorf_0((float)(*(v63 - 1) * 255.0) + 0.5);
        v68 = (((unsigned __int8)(int)floorf_0(v66 + 0.5) << 8) | v67) << 8;
        v69 = ((unsigned __int8)(int)floorf_0(v65 + 0.5) | v68) << 8;
        *v62 = (unsigned __int8)(int)floorf_0((float)(v64 * 255.0) + 0.5) | v69;
        v63 += 4;
        ++v62;
        --v51;
      }
      while ( v51 );
      v3 = v99;
      LODWORD(v50) = v98;
    }
    EndPoint = (const struct Gdiplus::PointF *)Jot::Graphics::PLinearGradientBrush::GetEndPoint(v3, &v99);
    StartPoint = (const struct Gdiplus::PointF *)Jot::Graphics::PLinearGradientBrush::GetStartPoint(v3, &v98);
    Gdiplus::LinearGradientBrush::LinearGradientBrush(
      (Gdiplus::LinearGradientBrush *)&v106,
      StartPoint,
      EndPoint,
      v61,
      (const struct Gdiplus::Color *)((char *)v61 + 4 * (unsigned int)(v50 - 1)));
    if ( (int)v50 > 0 && v61 )
    {
      v74 = (char *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(4LL * (int)v50), v72, v73);
      v75 = v74;
      if ( v74 )
      {
        v76 = 0;
        if ( (unsigned int)v50 >= 4 )
        {
          v77 = (int)v50 - 1;
          v78 = &v74[4 * v77];
          if ( v75 > (char *)v61 + 4 * v77 || v78 < (char *)v61 )
          {
            memcpy_0(v75, v61, 4LL * (int)v50);
            do
              ++v76;
            while ( v76 < (int)v50 );
          }
        }
        if ( v76 < (int)v50 )
        {
          v79 = &v75[4 * v76];
          v80 = (unsigned int)(v50 - v76);
          do
          {
            *(_DWORD *)v79 = *(_DWORD *)&v79[v61 - (const struct Gdiplus::Color *)v75];
            v79 += 4;
            --v80;
          }
          while ( v80 );
        }
        v38 = v94;
        v81 = GdipSetLinePresetBlend(*((_QWORD *)&v106 + 1), v75, v94, (unsigned int)v50);
        v82 = v107;
        if ( v81 )
          v82 = v81;
        LODWORD(v107) = v82;
        operator delete(v75);
        goto LABEL_91;
      }
      LODWORD(v107) = 3;
    }
    else
    {
      LODWORD(v107) = 2;
    }
    v38 = v94;
LABEL_91:
    Gdiplus::LinearGradientBrush::SetWrapMode(&v106);
    v83 = Gdiplus::Brush::Clone((Gdiplus::Brush *)&v106);
    *v100 = v83;
    GdipDeleteBrush(*((_QWORD *)&v106 + 1));
    if ( v61 )
      Mso::Memory::Free(v61, v42);
    if ( v57 )
      Mso::Memory::Free(v57, v42);
    goto LABEL_95;
  }
  if ( Jot::Graphics::PBrush::IsSolidColorBrush(v3) )
  {
    Jot::Graphics::PSolidColorBrush::GetColor(v3, &v95);
    v98 = (unsigned __int8)(int)(float)(v96 * 255.0)
        | (((unsigned __int8)(int)(float)(*((float *)&v95 + 1) * 255.0)
          | (((unsigned __int8)(int)(float)(*(float *)&v95 * 255.0) | ((unsigned __int8)(int)(float)(v97 * 255.0) << 8)) << 8)) << 8);
    Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)&v101, (const struct Gdiplus::Color *)&v98);
LABEL_56:
    *a2 = Gdiplus::Brush::Clone((Gdiplus::Brush *)&v101);
    GdipDeleteBrush(v102);
    return;
  }
  if ( Jot::Graphics::PBrush::IsLinearGradientBrush(v3) )
  {
    v5 = Jot::Graphics::PLinearGradientBrush::GetStopsCount(v3);
    v7 = v5;
    v98 = v5;
    v8 = v5;
    v10 = v5;
    v9 = v5 * (unsigned __int128)4uLL;
    if ( !is_mul_ok(v10, 4u) )
      *(_QWORD *)&v9 = -1;
    v94 = (float *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)v9, *((unsigned __int64 *)&v9 + 1), v6);
    v12 = v7 * (unsigned __int128)0x10u;
    if ( !is_mul_ok(v7, 0x10u) )
      *(_QWORD *)&v12 = -1;
    v13 = (struct Jot::Graphics::CColorF *)Mso::Memory::Throw::AllocateEx(
                                             (Mso::Memory::Throw *)v12,
                                             *((unsigned __int64 *)&v12 + 1),
                                             v11);
    v14 = v13;
    v104 = v13;
    if ( v13 )
      `vector constructor iterator'(v13, 0x10u, (unsigned int)v8, (void *(*)(void *))Jot::Graphics::CColorF::CColorF);
    else
      v14 = 0;
    v104 = v14;
    Jot::Graphics::PLinearGradientBrush::GetStopsAndColors(v3, v94, v14, v7);
    v16 = v8 * (unsigned __int128)4uLL;
    if ( !is_mul_ok(v8, 4u) )
      *(_QWORD *)&v16 = -1;
    v17 = (const struct Gdiplus::Color *)Mso::Memory::Throw::AllocateEx(
                                           (Mso::Memory::Throw *)v16,
                                           *((unsigned __int64 *)&v16 + 1),
                                           v15);
    v18 = v17;
    if ( v17 )
      `vector constructor iterator'(v17, 4u, v8, (void *(*)(void *))Gdiplus::Color::Color);
    else
      v18 = 0;
    v95 = v18;
    if ( (_DWORD)v7 )
    {
      v19 = v18;
      v20 = (float *)((char *)v14 + 4);
      do
      {
        v21 = v20[1];
        v22 = *v20 * 255.0;
        v23 = v20[2] * 255.0;
        v24 = (unsigned __int8)(int)floorf_0((float)(*(v20 - 1) * 255.0) + 0.5);
        v25 = (((unsigned __int8)(int)floorf_0(v23 + 0.5) << 8) | v24) << 8;
        v26 = ((unsigned __int8)(int)floorf_0(v22 + 0.5) | v25) << 8;
        *v19 = (unsigned __int8)(int)floorf_0((float)(v21 * 255.0) + 0.5) | v26;
        v20 += 4;
        ++v19;
        --v8;
      }
      while ( v8 );
      v3 = v99;
      LODWORD(v7) = v98;
    }
    v27 = (const struct Gdiplus::PointF *)Jot::Graphics::PLinearGradientBrush::GetEndPoint(v3, &v99);
    v28 = (const struct Gdiplus::PointF *)Jot::Graphics::PLinearGradientBrush::GetStartPoint(v3, &v98);
    Gdiplus::LinearGradientBrush::LinearGradientBrush(
      (Gdiplus::LinearGradientBrush *)&v106,
      v28,
      v27,
      v18,
      (const struct Gdiplus::Color *)((char *)v18 + 4 * (unsigned int)(v7 - 1)));
    if ( (int)v7 > 0 && v18 )
    {
      v31 = (char *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(4LL * (int)v7), v29, v30);
      v32 = v31;
      if ( v31 )
      {
        v33 = 0;
        if ( (unsigned int)v7 >= 4 )
        {
          v34 = (int)v7 - 1;
          v35 = &v31[4 * v34];
          if ( v32 > (char *)v18 + 4 * v34 || v35 < (char *)v18 )
          {
            memcpy_0(v32, v18, 4LL * (int)v7);
            do
              ++v33;
            while ( v33 < (int)v7 );
          }
        }
        if ( v33 < (int)v7 )
        {
          v36 = &v32[4 * v33];
          v37 = (unsigned int)(v7 - v33);
          do
          {
            *(_DWORD *)v36 = *(_DWORD *)&v36[v18 - (const struct Gdiplus::Color *)v32];
            v36 += 4;
            --v37;
          }
          while ( v37 );
        }
        v38 = v94;
        v39 = GdipSetLinePresetBlend(*((_QWORD *)&v106 + 1), v32, v94, (unsigned int)v7);
        v40 = v107;
        if ( v39 )
          v40 = v39;
        LODWORD(v107) = v40;
        operator delete(v32);
        goto LABEL_42;
      }
      LODWORD(v107) = 3;
    }
    else
    {
      LODWORD(v107) = 2;
    }
    v38 = v94;
LABEL_42:
    Gdiplus::LinearGradientBrush::SetWrapMode(&v106);
    v41 = Gdiplus::Brush::Clone((Gdiplus::Brush *)&v106);
    *v100 = v41;
    GdipDeleteBrush(*((_QWORD *)&v106 + 1));
    if ( v18 )
      Mso::Memory::Free(v18, v42);
    if ( v14 )
      Mso::Memory::Free(v14, v42);
LABEL_95:
    if ( v38 )
      Mso::Memory::Free((Mso::Memory *)v38, v42);
    return;
  }
  if ( Jot::Graphics::PBrush::IsBitmapBrush(v3) )
  {
    v94 = 0;
    v43 = Jot::Graphics::PBitmapBrush::UseBitmap(v3, &v95);
    if ( *(_BYTE *)(v43 + 8) != 1 )
      Mso::ThrowOnInvalidVariant::OnInvalidVariant<void>();
    if ( (unsigned __int8)ARC::IPlatformObject::GetInterface<ARC::GDIPlus::IGpImageAccess>(*(_QWORD *)v43, &v94) )
    {
      v105[1] = (*(__int64 (__fastcall **)(float *))(*(_QWORD *)v94 + 16LL))(v94);
      v105[2] = 0;
      v105[0] = &Jot::ImageFromGpImage::`vftable';
      ARC = Jot::Graphics::PBitmapBrush::GetARC(v3);
      (*(void (__fastcall **)(struct ARC::IBitmapBrush *, __int128 *))(*(_QWORD *)ARC + 72LL))(ARC, &v106);
      v45 = (*(__int64 (__fastcall **)(struct ARC::IBitmapBrush *))(*(_QWORD *)ARC + 128LL))(ARC);
      v46 = (*(__int64 (__fastcall **)(struct ARC::IBitmapBrush *))(*(_QWORD *)ARC + 120LL))(ARC);
      v47 = ARC::GDIPlus::ToGDIPlusWrapMode(v46, v45);
      Gdiplus::Matrix::Matrix(
        (Gdiplus::Matrix *)&v95,
        *(float *)&v106,
        *((float *)&v106 + 1),
        *((float *)&v106 + 2),
        *((float *)&v106 + 3),
        *(float *)&v107,
        *((float *)&v107 + 1));
      Gdiplus::TextureBrush::TextureBrush(&v101, v105);
      Gdiplus::TextureBrush::SetTransform(&v101, &v95);
      Gdiplus::TextureBrush::SetWrapMode(&v101, v47);
      *a2 = Gdiplus::Brush::Clone((Gdiplus::Brush *)&v101);
      GdipDeleteBrush(v102);
      GdipDeleteMatrix(v95);
      Jot::ImageFromGpImage::~ImageFromGpImage((Jot::ImageFromGpImage *)v105);
    }
    if ( v94 )
      (*(void (__fastcall **)(float *))(*(_QWORD *)v94 + 8LL))(v94);
  }
}

```

## disassembly

```asm
0x180761558  test    rdx, rdx
0x18076155b  jz      locret_180762043
0x180761561  mov     rax, rsp
0x180761564  mov     [rax+18h], rbx
0x180761568  push    rbp
0x180761569  push    rsi
0x18076156a  push    rdi
0x18076156b  push    r12
0x18076156d  push    r13
0x18076156f  push    r14
0x180761571  push    r15
0x180761573  lea     rbp, [rax-58h]
0x180761577  sub     rsp, 120h
0x18076157e  movaps  xmmword ptr [rax-48h], xmm6
0x180761582  movaps  xmmword ptr [rax-58h], xmm7
0x180761586  movaps  xmmword ptr [rax-68h], xmm8
0x18076158b  movaps  xmmword ptr [rax-78h], xmm9
0x180761590  movaps  xmmword ptr [rax-88h], xmm10
0x180761598  mov     rax, cs:__security_cookie
0x18076159f  xor     rax, rsp
0x1807615a2  mov     [rbp+50h+var_90], rax
0x1807615a6  mov     rsi, rdx
0x1807615a9  mov     [rsp+150h+var_E8], rdx
0x1807615ae  mov     rdi, rcx
0x1807615b1  mov     [rsp+150h+var_F0], rcx
0x1807615b6  xor     r14d, r14d
0x1807615b9  mov     [rdx], r14
0x1807615bc  mov     al, cs:byte_181516040
0x1807615c2  test    al, al
0x1807615c4  js      short loc_1807615CB
0x1807615c6  setnz   al
0x1807615c9  jmp     short loc_1807615D8
0x1807615cb  lea     rcx, byte_181516040
0x1807615d2  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x1807615d8  mov     rcx, rdi; this
0x1807615db  test    al, al
0x1807615dd  jz      loc_180761AAD
0x1807615e3  call    ?IsSolidColorBrush@PBrush@Graphics@Jot@@QEBA_NXZ; Jot::Graphics::PBrush::IsSolidColorBrush(void)
0x1807615e8  mov     rcx, rdi; this
0x1807615eb  test    al, al
0x1807615ed  jz      short loc_18076166C
0x1807615ef  lea     rdx, [rsp+150h+var_108]
0x1807615f4  call    ?GetColor@PSolidColorBrush@Graphics@Jot@@QEBA?AVCColorF@23@XZ; Jot::Graphics::PSolidColorBrush::GetColor(void)
0x1807615f9  movss   xmm0, [rsp+150h+var_FC]
0x1807615ff  movss   xmm1, cs:__real@437f0000
0x180761607  mulss   xmm0, xmm1
0x18076160b  cvttss2si eax, xmm0
0x18076160f  movzx   edx, al
0x180761612  shl     edx, 8
0x180761615  movss   xmm0, dword ptr [rsp+150h+var_108]
0x18076161b  mulss   xmm0, xmm1
0x18076161f  cvttss2si eax, xmm0
0x180761623  movzx   ecx, al
0x180761626  or      edx, ecx
0x180761628  shl     edx, 8
0x18076162b  movss   xmm0, dword ptr [rsp+150h+var_108+4]
0x180761631  mulss   xmm0, xmm1
0x180761635  cvttss2si eax, xmm0
0x180761639  movzx   ecx, al
0x18076163c  or      edx, ecx
0x18076163e  shl     edx, 8
0x180761641  movss   xmm0, [rsp+150h+var_100]
0x180761647  mulss   xmm0, xmm1
0x18076164b  cvttss2si eax, xmm0
0x18076164f  movzx   ecx, al
0x180761652  or      edx, ecx
0x180761654  mov     [rsp+150h+var_F8], edx
0x180761658  lea     rdx, [rsp+150h+var_F8]; struct Gdiplus::Color *
0x18076165d  lea     rcx, [rsp+150h+var_E0]; this
0x180761662  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180761667  jmp     loc_180761B4E
0x18076166c  call    ?IsLinearGradientBrush@PBrush@Graphics@Jot@@QEBA_NXZ; Jot::Graphics::PBrush::IsLinearGradientBrush(void)
0x180761671  mov     rcx, rdi; this
0x180761674  test    al, al
0x180761676  jz      loc_180761948
0x18076167c  call    ?GetStopsCount@PLinearGradientBrush@Graphics@Jot@@QEBAIXZ; Jot::Graphics::PLinearGradientBrush::GetStopsCount(void)
0x180761681  mov     r14d, eax
0x180761684  mov     [rsp+150h+var_F8], r14d
0x180761689  mov     r12d, eax
0x18076168c  mov     r15d, 4
0x180761692  mov     eax, r15d
0x180761695  mul     r14
0x180761698  lea     rbx, [r15-5]
0x18076169c  cmovb   rax, rbx
0x1807616a0  mov     rcx, rax; this
0x1807616a3  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1807616a8  mov     [rsp+150h+var_110], rax
0x1807616ad  lea     esi, [rbx+11h]
0x1807616b0  mov     eax, esi
0x1807616b2  mul     r14
0x1807616b5  cmovb   rax, rbx
0x1807616b9  mov     rcx, rax; this
0x1807616bc  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1807616c1  mov     r13, rax
0x1807616c4  mov     [rbp+50h+var_C8], rax
0x1807616c8  test    rax, rax
0x1807616cb  jz      short loc_1807616E3
0x1807616cd  lea     r9, ??0CColorF@Graphics@Jot@@QEAA@XZ; void *(*)(void *)
0x1807616d4  mov     r8d, r12d; unsigned __int64
0x1807616d7  mov     edx, esi; unsigned __int64
0x1807616d9  mov     rcx, rax; void *
0x1807616dc  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1807616e1  jmp     short loc_1807616E6
0x1807616e3  xor     r13d, r13d
0x1807616e6  mov     [rbp+50h+var_C8], r13
0x1807616ea  mov     r9d, r14d; unsigned int
0x1807616ed  mov     r8, r13; struct Jot::Graphics::CColorF *
0x1807616f0  mov     rdx, [rsp+150h+var_110]; float *
0x1807616f5  mov     rcx, rdi; this
0x1807616f8  call    ?GetStopsAndColors@PLinearGradientBrush@Graphics@Jot@@QEBAXPEAMPEAVCColorF@23@I@Z; Jot::Graphics::PLinearGradientBrush::GetStopsAndColors(float *,Jot::Graphics::CColorF *,uint)
0x1807616fd  mov     rax, r15
0x180761700  mul     r12
0x180761703  cmovb   rax, rbx
0x180761707  mov     rcx, rax; this
0x18076170a  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18076170f  mov     rsi, rax
0x180761712  test    rax, rax
0x180761715  jz      short loc_18076172E
0x180761717  lea     r9, ??0Color@Gdiplus@@QEAA@XZ; void *(*)(void *)
0x18076171e  mov     r8, r12; unsigned __int64
0x180761721  mov     rdx, r15; unsigned __int64
0x180761724  mov     rcx, rax; void *
0x180761727  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18076172c  jmp     short loc_180761730
0x18076172e  xor     esi, esi
0x180761730  mov     [rsp+150h+var_108], rsi
0x180761735  test    r14d, r14d
0x180761738  jz      loc_1807617FA
0x18076173e  mov     r14, rsi
0x180761741  lea     rdi, [r13+4]
0x180761745  movss   xmm9, cs:__real@437f0000
0x18076174e  movss   xmm10, cs:__real@3f000000
0x180761757  movss   xmm8, dword ptr [rdi+4]
0x18076175d  mulss   xmm8, xmm9
0x180761762  movss   xmm7, dword ptr [rdi]
0x180761766  mulss   xmm7, xmm9
0x18076176b  movss   xmm6, dword ptr [rdi+8]
0x180761770  mulss   xmm6, xmm9
0x180761775  movss   xmm0, dword ptr [rdi-4]
0x18076177a  mulss   xmm0, xmm9
0x18076177f  addss   xmm0, xmm10; X
0x180761784  call    floorf_0
0x180761789  cvttss2si eax, xmm0
0x18076178d  movzx   ebx, al
0x180761790  addss   xmm6, xmm10
0x180761795  movaps  xmm0, xmm6; X
0x180761798  call    floorf_0
0x18076179d  cvttss2si eax, xmm0
0x1807617a1  movzx   ecx, al
0x1807617a4  shl     ecx, 8
0x1807617a7  or      ebx, ecx
0x1807617a9  shl     ebx, 8
0x1807617ac  addss   xmm7, xmm10
0x1807617b1  movaps  xmm0, xmm7; X
0x1807617b4  call    floorf_0
0x1807617b9  cvttss2si eax, xmm0
0x1807617bd  movzx   ecx, al
0x1807617c0  or      ebx, ecx
0x1807617c2  shl     ebx, 8
0x1807617c5  addss   xmm8, xmm10
0x1807617ca  movaps  xmm0, xmm8; X
0x1807617ce  call    floorf_0
0x1807617d3  cvttss2si eax, xmm0
0x1807617d7  movzx   ecx, al
0x1807617da  or      ebx, ecx
0x1807617dc  mov     [r14], ebx
0x1807617df  add     rdi, 10h
0x1807617e3  add     r14, r15
0x1807617e6  sub     r12, 1
0x1807617ea  jnz     loc_180761757
0x1807617f0  mov     rdi, [rsp+150h+var_F0]
0x1807617f5  mov     r14d, [rsp+150h+var_F8]
0x1807617fa  lea     rdx, [rsp+150h+var_F0]
0x1807617ff  mov     rcx, rdi
0x180761802  call    ?GetEndPoint@PLinearGradientBrush@Graphics@Jot@@QEBA?AVCPointF@MsoCF@@XZ; Jot::Graphics::PLinearGradientBrush::GetEndPoint(void)
0x180761807  mov     rbx, rax
0x18076180a  lea     rdx, [rsp+150h+var_F8]
0x18076180f  mov     rcx, rdi
0x180761812  call    ?GetStartPoint@PLinearGradientBrush@Graphics@Jot@@QEBA?AVCPointF@MsoCF@@XZ; Jot::Graphics::PLinearGradientBrush::GetStartPoint(void)
0x180761817  lea     ecx, [r14-1]
0x18076181b  lea     rdx, [rsi+rcx*4]
0x18076181f  mov     [rsp+150h+var_130], rdx; struct Gdiplus::Color *
0x180761824  mov     r9, rsi; struct Gdiplus::Color *
0x180761827  mov     r8, rbx; struct Gdiplus::PointF *
0x18076182a  mov     rdx, rax; struct Gdiplus::PointF *
0x18076182d  lea     rcx, [rbp+50h+var_A8]; this
0x180761831  call    ??0LinearGradientBrush@Gdiplus@@QEAA@AEBVPointF@1@0AEBVColor@1@1@Z; Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::PointF const &,Gdiplus::PointF const &,Gdiplus::Color const &,Gdiplus::Color const &)
0x180761836  nop
0x180761837  test    r14d, r14d
0x18076183a  jle     loc_1807618F5
0x180761840  test    rsi, rsi
0x180761843  jz      loc_1807618F5
0x180761849  movsxd  r12, r14d
0x18076184c  shl     r12, 2
0x180761850  mov     rcx, r12; this
0x180761853  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180761858  mov     rbx, rax
0x18076185b  test    rax, rax
0x18076185e  jz      loc_1807618EC
0x180761864  xor     edi, edi
0x180761866  cmp     r14d, r15d
0x180761869  jb      short loc_180761899
0x18076186b  lea     eax, [r14-1]
0x18076186f  movsxd  rcx, eax
0x180761872  lea     rax, [rbx+rcx*4]
0x180761876  lea     rcx, [rsi+rcx*4]
0x18076187a  cmp     rbx, rcx
0x18076187d  ja      short loc_180761884
0x18076187f  cmp     rax, rsi
0x180761882  jnb     short loc_180761899
0x180761884  mov     r8, r12; Size
0x180761887  mov     rdx, rsi; Src
0x18076188a  mov     rcx, rbx; void *
0x18076188d  call    memcpy_0
0x180761892  inc     edi
0x180761894  cmp     edi, r14d
0x180761897  jl      short loc_180761892
0x180761899  cmp     edi, r14d
0x18076189c  jge     short loc_1807618BF
0x18076189e  movsxd  rax, edi
0x1807618a1  lea     rcx, [rbx+rax*4]
0x1807618a5  mov     rdx, rsi
0x1807618a8  sub     rdx, rbx
0x1807618ab  mov     r8d, r14d
0x1807618ae  sub     r8d, edi
0x1807618b1  mov     eax, [rcx+rdx]
0x1807618b4  mov     [rcx], eax
0x1807618b6  add     rcx, r15
0x1807618b9  sub     r8, 1
0x1807618bd  jnz     short loc_1807618B1
0x1807618bf  mov     r9d, r14d
0x1807618c2  mov     rdi, [rsp+150h+var_110]
0x1807618c7  mov     r8, rdi
0x1807618ca  mov     rdx, rbx
0x1807618cd  mov     rcx, qword ptr [rbp+50h+var_A8+8]
0x1807618d1  call    cs:__imp_GdipSetLinePresetBlend
0x1807618d7  mov     ecx, [rbp+50h+var_98]
0x1807618da  test    eax, eax
0x1807618dc  cmovnz  ecx, eax
0x1807618df  mov     [rbp+50h+var_98], ecx
0x1807618e2  mov     rcx, rbx; void *
0x1807618e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1807618ea  jmp     short loc_180761901
0x1807618ec  mov     [rbp+50h+var_98], 3
0x1807618f3  jmp     short loc_1807618FC
0x1807618f5  mov     [rbp+50h+var_98], 2
0x1807618fc  mov     rdi, [rsp+150h+var_110]
0x180761901  lea     rcx, [rbp+50h+var_A8]
0x180761905  call    ?SetWrapMode@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@W4WrapMode@2@@Z; Gdiplus::LinearGradientBrush::SetWrapMode(Gdiplus::WrapMode)
0x18076190a  lea     rcx, [rbp+50h+var_A8]; this
0x18076190e  call    ?Clone@Brush@Gdiplus@@UEBAPEAV12@XZ; Gdiplus::Brush::Clone(void)
0x180761913  mov     rcx, [rsp+150h+var_E8]
0x180761918  mov     [rcx], rax
0x18076191b  mov     rcx, qword ptr [rbp+50h+var_A8+8]
0x18076191f  call    cs:__imp_GdipDeleteBrush
0x180761925  test    rsi, rsi
0x180761928  jz      short loc_180761934
0x18076192a  mov     rcx, rsi
0x18076192d  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180761933  nop
0x180761934  test    r13, r13
0x180761937  jz      short loc_180761943
0x180761939  mov     rcx, r13
0x18076193c  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180761942  nop
0x180761943  jmp     loc_180761E43
0x180761948  call    ?IsBitmapBrush@PBrush@Graphics@Jot@@QEBA_NXZ; Jot::Graphics::PBrush::IsBitmapBrush(void)
0x18076194d  test    al, al
0x18076194f  jz      loc_180762004
0x180761955  mov     [rsp+150h+var_110], r14
0x18076195a  lea     rdx, [rsp+150h+var_108]
0x18076195f  mov     rcx, rdi
0x180761962  call    ?UseBitmap@PBitmapBrush@Graphics@Jot@@QEBA?AVPBitmap@23@XZ; Jot::Graphics::PBitmapBrush::UseBitmap(void)
0x180761967  cmp     byte ptr [rax+8], 1
0x18076196b  jz      short loc_180761973
0x18076196d  call    ??$OnInvalidVariant@X@ThrowOnInvalidVariant@Mso@@SAXXZ; Mso::ThrowOnInvalidVariant::OnInvalidVariant<void>(void)
0x180761973  lea     rdx, [rsp+150h+var_110]
0x180761978  mov     rcx, [rax]
0x18076197b  call    ??$GetInterface@UIGpImageAccess@GDIPlus@ARC@@@IPlatformObject@ARC@@QEAA_NAEAV?$TPtr@UIGpImageAccess@GDIPlus@ARC@@@1@@Z; ARC::IPlatformObject::GetInterface<ARC::GDIPlus::IGpImageAccess>(ARC::TPtr<ARC::GDIPlus::IGpImageAccess> &)
0x180761980  test    al, al
0x180761982  jz      loc_180761A8D
0x180761988  mov     rcx, [rsp+150h+var_110]
0x18076198d  mov     rax, [rcx]
0x180761990  mov     rax, [rax+10h]
0x180761994  call    cs:__guard_dispatch_icall_fptr
0x18076199a  mov     [rbp+50h+var_B8], rax
0x18076199e  mov     [rbp+50h+var_B0], r14
0x1807619a2  lea     rax, ??_7ImageFromGpImage@Jot@@6B@; const Jot::ImageFromGpImage::`vftable'
0x1807619a9  mov     [rbp+50h+var_C0], rax
0x1807619ad  mov     rcx, rdi; this
0x1807619b0  call    ?GetARC@PBitmapBrush@Graphics@Jot@@QEAAPEAUIBitmapBrush@ARC@@XZ; Jot::Graphics::PBitmapBrush::GetARC(void)
0x1807619b5  mov     rdi, rax
0x1807619b8  mov     rcx, [rax]
0x1807619bb  mov     rax, [rcx+48h]
0x1807619bf  lea     rdx, [rbp+50h+var_A8]
0x1807619c3  mov     rcx, rdi
0x1807619c6  call    cs:__guard_dispatch_icall_fptr
0x1807619cc  mov     rcx, [rdi]
0x1807619cf  mov     rax, [rcx+80h]
0x1807619d6  mov     rcx, rdi
  ... truncated ...
```
