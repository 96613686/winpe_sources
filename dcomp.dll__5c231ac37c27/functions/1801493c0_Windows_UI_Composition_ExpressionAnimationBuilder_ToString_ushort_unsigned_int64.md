# Windows::UI::Composition::ExpressionAnimationBuilder::ToString(ushort *,unsigned __int64)

- ea: `0x1801493c0`
- end: `0x18014b1e6`
- name: `?ToString@ExpressionAnimationBuilder@Composition@UI@Windows@@QEAAJPEAG_K@Z`
- size: `7718`
- prototype: `__int64 __fastcall(Windows::UI::Composition::ExpressionAnimationBuilder *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180125e90`
- `0x1801493c0`

## callees

- `0x180006590`
- `0x180040e6c`
- `0x1800434e8`
- `0x1800a88ec`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x1801493c0`

## string_xrefs

- `0x18014a897`: `Matrix4x4.CreateTranslation `
- `0x18014a8fd`: `Matrix3x2.CreateTranslation `
- `0x18014a6da`: `Matrix3x2.CreateRotation `
- `0x18014a7d9`: `Matrix3x2.CreateSkew `
- `0x18014a8ca`: `Matrix4x4.CreateScale `
- `0x18014a6a7`: `Matrix3x2.CreateScale `
- `0x18014aaae`: `Matrix4x4.CreateRotationZ `
- `0x18014a930`: `Matrix4x4.CreateRotationY `
- `0x18014a831`: `Matrix4x4.CreateRotationX `
- `0x18014a864`: `Matrix4x4.CreateFromAxisAngle `
- `0x18014a9e2`: `Matrix4x4.CreateFromQuaternion `
- `0x18014aa15`: `Matrix4x4.CreatePerspectiveOffCenter `
- `0x18014aa48`: `Matrix4x4.CreatePerspectiveFieldOfView `
- `0x18014aa7b`: `Matrix4x4.CreatePerspective `
- `0x18014abd2`: `Quaternion.CreateFromRotationMatrix `
- `0x18014aae1`: `Quaternion.CreateFromAxisAngle `
- `0x18014a9af`: `Matrix4x4.CreateFromYawPitchRoll `
- `0x18014ab9f`: `Quaternion.CreateFromYawPitchRoll `

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ExpressionAnimationBuilder::ToString(
        Windows::UI::Composition::ExpressionAnimationBuilder *this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned int v6; // esi
  __int64 v7; // r12
  __int64 v8; // rdi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const wchar_t *v20; // r9
  int v21; // eax
  int v22; // eax
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // eax
  int v28; // eax
  int *v29; // rcx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // eax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // eax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  int v60; // ecx
  int v61; // eax
  int v62; // eax
  int v63; // eax
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // ecx
  int v69; // ecx
  int v70; // ecx
  int v71; // ecx
  int v72; // eax
  int v73; // eax
  int v74; // eax
  int v75; // eax
  int v76; // eax
  int v77; // eax
  int v78; // ecx
  int v79; // ecx
  int v80; // ecx
  int v81; // ecx
  int v82; // eax
  int v83; // eax
  int v84; // eax
  int v85; // eax
  int v86; // eax
  int v87; // eax
  int v88; // ecx
  int v89; // ecx
  int v90; // ecx
  int v91; // ecx
  int v92; // eax
  int v93; // eax
  int v94; // eax
  int v95; // eax
  int v96; // eax
  int v97; // eax
  int v98; // eax
  int v99; // eax
  int v100; // ecx
  int v101; // ecx
  int v102; // ecx
  int v103; // ecx
  int v104; // ecx
  int v105; // eax
  int v106; // eax
  int v107; // eax
  int v108; // eax
  int v109; // eax
  int v110; // eax
  int v111; // eax
  int v112; // ecx
  int v113; // ecx
  int v114; // ecx
  int v115; // ecx
  int v116; // eax
  int v117; // eax
  int v118; // eax
  int v119; // eax
  int v120; // eax
  int v121; // eax
  int v122; // ecx
  int v123; // ecx
  int v124; // ecx
  int v125; // ecx
  int v126; // ecx
  int v127; // eax
  int v128; // eax
  int v129; // eax
  int v130; // eax
  int v131; // eax
  int v132; // eax
  int v133; // eax
  int v134; // ecx
  int v135; // ecx
  int v136; // ecx
  int v137; // ecx
  int v138; // eax
  int v139; // eax
  int v140; // eax
  int v141; // eax
  int v142; // eax
  int v143; // eax
  int v144; // ecx
  int v145; // ecx
  int v146; // ecx
  int v147; // ecx
  int v148; // ecx
  int v149; // eax
  int v150; // eax
  int v151; // eax
  int v152; // eax
  int v153; // eax
  int v154; // eax
  int v155; // eax
  int v156; // ecx
  int v157; // ecx
  int v158; // ecx
  int v159; // ecx
  int v160; // eax
  int v161; // eax
  int v162; // eax
  int v163; // eax
  int v164; // eax
  int v165; // eax
  int v166; // ecx
  int v167; // ecx
  int v168; // ecx
  int v169; // ecx
  int v170; // eax
  int v171; // eax
  int v172; // eax
  int v173; // eax
  int v174; // eax
  int v175; // eax
  int v176; // ecx
  int v177; // ecx
  int v178; // ecx
  int v179; // ecx
  int v180; // eax
  unsigned int i; // esi
  unsigned int v182; // ecx
  int v183; // eax
  int v184; // eax
  int v185; // eax
  int v186; // eax
  unsigned int j; // esi
  unsigned int v188; // ecx
  int v189; // eax
  int v190; // eax
  int v191; // eax
  int v192; // eax
  int v193; // eax
  int v194; // eax
  int v195; // eax
  int v196; // eax
  unsigned __int64 v197; // rcx
  unsigned int v199[2]; // [rsp+28h] [rbp-100h]
  int v200; // [rsp+A8h] [rbp-80h]
  unsigned __int64 v201; // [rsp+B0h] [rbp-78h] BYREF
  unsigned __int16 v202[256]; // [rsp+B8h] [rbp-70h] BYREF
  unsigned __int16 v203[8]; // [rsp+2B8h] [rbp+190h] BYREF
  unsigned __int16 v204[8]; // [rsp+2C8h] [rbp+1A0h] BYREF
  unsigned __int16 v205[256]; // [rsp+2D8h] [rbp+1B0h] BYREF
  unsigned __int16 v206[256]; // [rsp+4D8h] [rbp+3B0h] BYREF

  v201 = 0;
  if ( !a2 || !a3 )
LABEL_361:
    Microsoft::WRL2::FailFast::Unexpected(0);
  v6 = 0;
  v200 = 0;
  v7 = 0;
  *a2 = 0;
  while ( (unsigned int)v7 < *((_DWORD *)this + 10) )
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v7);
    v9 = *(_DWORD *)v8;
    if ( *(int *)v8 > 52 )
    {
      if ( v9 > 78 )
      {
        if ( v9 > 91 )
        {
          if ( v9 > 97 )
          {
            v176 = v9 - 98;
            if ( v176 )
            {
              v177 = v176 - 1;
              if ( v177 )
              {
                v178 = v177 - 1;
                if ( v178 )
                {
                  v179 = v178 - 1;
                  if ( v179 )
                  {
                    if ( v179 != 1 )
                      goto LABEL_361;
                    v180 = StringCchPrintfW(
                             v202,
                             0xFAu,
                             L"swizzle(%u",
                             (*(_QWORD *)(v8 + 16) >> (4 * *(_BYTE *)(v8 + 12) - 4)) & 0xFLL);
                    v15 = v180;
                    if ( v180 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v180,
                        0xF6Eu,
                        0);
                      goto LABEL_359;
                    }
                    for ( i = 1; ; ++i )
                    {
                      v182 = *(unsigned __int8 *)(v8 + 12);
                      if ( i >= v182 )
                        break;
                      v183 = StringCchPrintfW(
                               v203,
                               5u,
                               L",%u",
                               (*(_QWORD *)(v8 + 16) >> (4 * ((unsigned __int8)v182 - (unsigned __int8)i) - 4)) & 0xFLL);
                      v15 = v183;
                      if ( v183 < 0 )
                      {
                        MilInstrumentationCheckHR_MaybeFailFast(
                          4u,
                          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                          1u,
                          v183,
                          0xF72u,
                          0);
                        goto LABEL_359;
                      }
                      v184 = StringCchCatW(v202, 0xFAu, v203);
                      v15 = v184;
                      if ( v184 < 0 )
                      {
                        MilInstrumentationCheckHR_MaybeFailFast(
                          4u,
                          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                          1u,
                          v184,
                          0xF73u,
                          0);
                        goto LABEL_359;
                      }
                    }
                    v185 = StringCchCatW(v202, 0xFAu, L") ");
                    v15 = v185;
                    if ( v185 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v185,
                        0xF76u,
                        0);
                      goto LABEL_359;
                    }
                  }
                  else
                  {
                    v186 = StringCchPrintfW(
                             v202,
                             0xFAu,
                             L"swizzle(%u",
                             (*(unsigned __int8 *)(v8 + 12) >> (2 * *(_BYTE *)(v8 + 8) - 2)) & 3);
                    v15 = v186;
                    if ( v186 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v186,
                        0xF5Cu,
                        0);
                      goto LABEL_359;
                    }
                    for ( j = 1; ; ++j )
                    {
                      v188 = *(unsigned __int8 *)(v8 + 8);
                      if ( j >= v188 )
                        break;
                      v189 = StringCchPrintfW(
                               v204,
                               5u,
                               L",%u",
                               (*(unsigned __int8 *)(v8 + 12) >> (2 * (v188 - j) - 2)) & 3);
                      v15 = v189;
                      if ( v189 < 0 )
                      {
                        MilInstrumentationCheckHR_MaybeFailFast(
                          4u,
                          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                          1u,
                          v189,
                          0xF60u,
                          0);
                        goto LABEL_359;
                      }
                      v190 = StringCchCatW(v202, 0xFAu, v204);
                      v15 = v190;
                      if ( v190 < 0 )
                      {
                        MilInstrumentationCheckHR_MaybeFailFast(
                          4u,
                          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                          1u,
                          v190,
                          0xF61u,
                          0);
                        goto LABEL_359;
                      }
                    }
                    v191 = StringCchCatW(v202, 0xFAu, L") ");
                    v15 = v191;
                    if ( v191 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v191,
                        0xF64u,
                        0);
LABEL_359:
                      v197 = 0;
                      goto LABEL_360;
                    }
                  }
                  v6 = v200;
                }
                else
                {
                  v192 = StringCchPrintfW(v202, 0xFAu, L"Vector4.Transform ");
                  v15 = v192;
                  if ( v192 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v192,
                      0xF53u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v193 = StringCchPrintfW(v202, 0xFAu, L"Vector4.Dot ");
                v15 = v193;
                if ( v193 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v193,
                    0xF4Du,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v194 = StringCchPrintfW(v202, 0xFAu, L"Vector3.TransformNormal ");
              v15 = v194;
              if ( v194 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v194,
                  0xF47u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else if ( v9 == 97 )
          {
            v175 = StringCchPrintfW(v202, 0xFAu, L"Vector3.Transform ");
            v15 = v175;
            if ( v175 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v175,
                0xF41u,
                0);
              goto LABEL_359;
            }
          }
          else
          {
            v166 = v9 - 92;
            if ( v166 )
            {
              v167 = v166 - 1;
              if ( v167 )
              {
                v168 = v167 - 1;
                if ( v168 )
                {
                  v169 = v168 - 1;
                  if ( v169 )
                  {
                    if ( v169 != 1 )
                      goto LABEL_361;
                    v170 = StringCchPrintfW(v202, 0xFAu, L"Vector3.Dot ");
                    v15 = v170;
                    if ( v170 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v170,
                        0xF3Bu,
                        0);
                      goto LABEL_359;
                    }
                  }
                  else
                  {
                    v171 = StringCchPrintfW(v202, 0xFAu, L"Vector3.Cross ");
                    v15 = v171;
                    if ( v171 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v171,
                        0xF35u,
                        0);
                      goto LABEL_359;
                    }
                  }
                }
                else
                {
                  v172 = StringCchPrintfW(v202, 0xFAu, L"Vector2.TransformNormal ");
                  v15 = v172;
                  if ( v172 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v172,
                      0xF2Fu,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v173 = StringCchPrintfW(v202, 0xFAu, L"Vector2.Transform ");
                v15 = v173;
                if ( v173 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v173,
                    0xF29u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v174 = StringCchPrintfW(v202, 0xFAu, L"Vector2.Dot ");
              v15 = v174;
              if ( v174 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v174,
                  0xF23u,
                  0);
                goto LABEL_359;
              }
            }
          }
        }
        else if ( v9 == 91 )
        {
          v165 = StringCchPrintfW(v202, 0xFAu, L"TimeSpan.FromMinutes ");
          v15 = v165;
          if ( v165 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v165,
              0xF1Du,
              0);
            goto LABEL_359;
          }
        }
        else if ( v9 > 85 )
        {
          v156 = v9 - 86;
          if ( v156 )
          {
            v157 = v156 - 1;
            if ( v157 )
            {
              v158 = v157 - 1;
              if ( v158 )
              {
                v159 = v158 - 1;
                if ( v159 )
                {
                  if ( v159 != 1 )
                    goto LABEL_361;
                  v160 = StringCchPrintfW(v202, 0xFAu, L"TimeSpan.FromSeconds ");
                  v15 = v160;
                  if ( v160 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v160,
                      0xF17u,
                      0);
                    goto LABEL_359;
                  }
                }
                else
                {
                  v161 = StringCchPrintfW(v202, 0xFAu, L"TimeSpan.FromMilliSeconds ");
                  v15 = v161;
                  if ( v161 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v161,
                      0xF11u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v162 = StringCchPrintfW(v202, 0xFAu, L"Quaternion.CreateFromYawPitchRoll ");
                v15 = v162;
                if ( v162 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v162,
                    0xF0Bu,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v163 = StringCchPrintfW(v202, 0xFAu, L"Quaternion.CreateFromRotationMatrix ");
              v15 = v163;
              if ( v163 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v163,
                  0xF05u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v164 = StringCchPrintfW(v202, 0xFAu, L"Quaternion.Lerp ");
            v15 = v164;
            if ( v164 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v164,
                0xEFFu,
                0);
              goto LABEL_359;
            }
          }
        }
        else if ( v9 == 85 )
        {
          v155 = StringCchPrintfW(v202, 0xFAu, L"Quaternion.CreateFromAxisAngle ");
          v15 = v155;
          if ( v155 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v155,
              0xEF9u,
              0);
            goto LABEL_359;
          }
        }
        else
        {
          v144 = v9 - 79;
          if ( v144 )
          {
            v145 = v144 - 1;
            if ( v145 )
            {
              v146 = v145 - 1;
              if ( v146 )
              {
                v147 = v146 - 1;
                if ( v147 )
                {
                  v148 = v147 - 1;
                  if ( v148 )
                  {
                    if ( v148 != 1 )
                      goto LABEL_361;
                    v149 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateFromYawPitchRoll ");
                    v15 = v149;
                    if ( v149 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v149,
                        0xEF3u,
                        0);
                      goto LABEL_359;
                    }
                  }
                  else
                  {
                    v150 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateFromQuaternion ");
                    v15 = v150;
                    if ( v150 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v150,
                        0xEEDu,
                        0);
                      goto LABEL_359;
                    }
                  }
                }
                else
                {
                  v151 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreatePerspectiveOffCenter ");
                  v15 = v151;
                  if ( v151 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v151,
                      0xEE7u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v152 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreatePerspectiveFieldOfView ");
                v15 = v152;
                if ( v152 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v152,
                    0xEE1u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v153 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreatePerspective ");
              v15 = v153;
              if ( v153 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v153,
                  0xEDBu,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v154 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateRotationZ ");
            v15 = v154;
            if ( v154 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v154,
                0xED5u,
                0);
              goto LABEL_359;
            }
          }
        }
      }
      else if ( v9 == 78 )
      {
        v143 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateRotationY ");
        v15 = v143;
        if ( v143 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v143,
            0xECFu,
            0);
          goto LABEL_359;
        }
      }
      else if ( v9 > 65 )
      {
        if ( v9 > 72 )
        {
          v134 = v9 - 73;
          if ( v134 )
          {
            v135 = v134 - 1;
            if ( v135 )
            {
              v136 = v135 - 1;
              if ( v136 )
              {
                v137 = v136 - 1;
                if ( v137 )
                {
                  if ( v137 != 1 )
                    goto LABEL_361;
                  v138 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateRotationX ");
                  v15 = v138;
                  if ( v138 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v138,
                      0xEC9u,
                      0);
                    goto LABEL_359;
                  }
                }
                else
                {
                  v139 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateFromAxisAngle ");
                  v15 = v139;
                  if ( v139 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v139,
                      0xEC3u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v140 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateTranslation ");
                v15 = v140;
                if ( v140 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v140,
                    0xEA5u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v141 = StringCchPrintfW(v202, 0xFAu, L"Matrix4x4.CreateScale ");
              v15 = v141;
              if ( v141 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v141,
                  0xEB1u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v142 = StringCchPrintfW(v202, 0xFAu, L"Matrix3x2.CreateTranslation ");
            v15 = v142;
            if ( v142 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v142,
                0xE9Fu,
                0);
              goto LABEL_359;
            }
          }
        }
        else if ( v9 == 72 )
        {
          v133 = StringCchPrintfW(v202, 0xFAu, L"Matrix3x2.CreateSkew ");
          v15 = v133;
          if ( v133 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v133,
              0xEB7u,
              0);
            goto LABEL_359;
          }
        }
        else
        {
          v122 = v9 - 66;
          if ( v122 )
          {
            v123 = v122 - 1;
            if ( v123 )
            {
              v124 = v123 - 1;
              if ( v124 )
              {
                v125 = v124 - 1;
                if ( v125 )
                {
                  v126 = v125 - 1;
                  if ( v126 )
                  {
                    if ( v126 != 1 )
                      goto LABEL_361;
                    v127 = StringCchPrintfW(v202, 0xFAu, L"Matrix3x2.CreateScale ");
                    v15 = v127;
                    if ( v127 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v127,
                        0xEABu,
                        0);
                      goto LABEL_359;
                    }
                  }
                  else
                  {
                    v128 = StringCchPrintfW(v202, 0xFAu, L"Matrix3x2.CreateRotation ");
                    v15 = v128;
                    if ( v128 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(
                        4u,
                        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                        1u,
                        v128,
                        0xEBDu,
                        0);
                      goto LABEL_359;
                    }
                  }
                }
                else
                {
                  v129 = StringCchPrintfW(v202, 0xFAu, L"matrix4x4 ");
                  v15 = v129;
                  if ( v129 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v129,
                      0xE99u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v130 = StringCchPrintfW(v202, 0xFAu, L"matrix3x2 ");
                v15 = v130;
                if ( v130 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v130,
                    0xE93u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v131 = StringCchPrintfW(v202, 0xFAu, L"quaternion ");
              v15 = v131;
              if ( v131 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v131,
                  0xE8Du,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v132 = StringCchPrintfW(v202, 0xFAu, L"colorrgb ");
            v15 = v132;
            if ( v132 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v132,
                0xE87u,
                0);
              goto LABEL_359;
            }
          }
        }
      }
      else if ( v9 == 65 )
      {
        v121 = StringCchPrintfW(v202, 0xFAu, L"colorhsl ");
        v15 = v121;
        if ( v121 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v121,
            0xE81u,
            0);
          goto LABEL_359;
        }
      }
      else if ( v9 > 59 )
      {
        v112 = v9 - 60;
        if ( v112 )
        {
          v113 = v112 - 1;
          if ( v113 )
          {
            v114 = v113 - 1;
            if ( v114 )
            {
              v115 = v114 - 1;
              if ( v115 )
              {
                if ( v115 != 1 )
                  goto LABEL_361;
                v116 = StringCchPrintfW(v202, 0xFAu, L"vector4 ");
                v15 = v116;
                if ( v116 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v116,
                    0xE7Bu,
                    0);
                  goto LABEL_359;
                }
              }
              else
              {
                v117 = StringCchPrintfW(v202, 0xFAu, L"vector3 ");
                v15 = v117;
                if ( v117 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v117,
                    0xE75u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v118 = StringCchPrintfW(v202, 0xFAu, L"vector2 ");
              v15 = v118;
              if ( v118 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v118,
                  0xE6Fu,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v119 = StringCchPrintfW(v202, 0xFAu, L"! ");
            v15 = v119;
            if ( v119 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v119,
                0xD8Fu,
                0);
              goto LABEL_359;
            }
          }
        }
        else
        {
          v120 = StringCchPrintfW(v202, 0xFAu, L"|| ");
          v15 = v120;
          if ( v120 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v120,
              0xD89u,
              0);
            goto LABEL_359;
          }
        }
      }
      else if ( v9 == 59 )
      {
        v111 = StringCchPrintfW(v202, 0xFAu, L"&& ");
        v15 = v111;
        if ( v111 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v111,
            0xD83u,
            0);
          goto LABEL_359;
        }
      }
      else
      {
        v100 = v9 - 53;
        if ( v100 )
        {
          v101 = v100 - 1;
          if ( v101 )
          {
            v102 = v101 - 1;
            if ( v102 )
            {
              v103 = v102 - 1;
              if ( v103 )
              {
                v104 = v103 - 1;
                if ( v104 )
                {
                  if ( v104 != 1 )
                    goto LABEL_361;
                  v105 = StringCchPrintfW(v202, 0xFAu, L">= ");
                  v15 = v105;
                  if ( v105 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v105,
                      0xD7Du,
                      0);
                    goto LABEL_359;
                  }
                }
                else
                {
                  v106 = StringCchPrintfW(v202, 0xFAu, L"> ");
                  v15 = v106;
                  if ( v106 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v106,
                      0xD77u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v107 = StringCchPrintfW(v202, 0xFAu, L"<= ");
                v15 = v107;
                if ( v107 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v107,
                    0xD71u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v108 = StringCchPrintfW(v202, 0xFAu, L"< ");
              v15 = v108;
              if ( v108 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v108,
                  0xD6Bu,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v109 = StringCchPrintfW(v202, 0xFAu, L"!= ");
            v15 = v109;
            if ( v109 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v109,
                0xD65u,
                0);
              goto LABEL_359;
            }
          }
        }
        else
        {
          v110 = StringCchPrintfW(v202, 0xFAu, L"== ");
          v15 = v110;
          if ( v110 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v110,
              0xD5Fu,
              0);
            goto LABEL_359;
          }
        }
      }
    }
    else if ( v9 == 52 )
    {
      v97 = Windows::UI::Composition::ExpressionAnimationBuilder::ToString(
              *(Windows::UI::Composition::ExpressionAnimationBuilder **)(*((_QWORD *)this + 68)
                                                                       + 8LL * *(unsigned int *)(v8 + 12)),
              v206,
              0xFAu);
      v15 = v97;
      if ( v97 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          4u,
          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
          1u,
          v97,
          0xE06u,
          0);
        goto LABEL_359;
      }
      v98 = Windows::UI::Composition::ExpressionAnimationBuilder::ToString(
              *(Windows::UI::Composition::ExpressionAnimationBuilder **)(*((_QWORD *)this + 68)
                                                                       + 8LL * *(unsigned int *)(v8 + 16)),
              v205,
              0xFAu);
      v15 = v98;
      if ( v98 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          4u,
          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
          1u,
          v98,
          0xE07u,
          0);
        goto LABEL_359;
      }
      v99 = StringCchPrintfW(v202, 0xFAu, L"? (%ws) : (%ws) ", v206, v205);
      v15 = v99;
      if ( v99 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          4u,
          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
          1u,
          v99,
          0xE09u,
          0);
        goto LABEL_359;
      }
    }
    else if ( v9 > 26 )
    {
      if ( v9 > 39 )
      {
        if ( v9 > 45 )
        {
          v88 = v9 - 46;
          if ( v88 )
          {
            v89 = v88 - 1;
            if ( v89 )
            {
              v90 = v89 - 1;
              if ( v90 )
              {
                v91 = v90 - 1;
                if ( v91 )
                {
                  if ( v91 != 1 )
                    goto LABEL_361;
                  v92 = StringCchPrintfW(v202, 0xFAu, L"toradians ");
                  v15 = v92;
                  if ( v92 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v92,
                      0xE69u,
                      0);
                    goto LABEL_359;
                  }
                }
                else
                {
                  v93 = StringCchPrintfW(v202, 0xFAu, L"todegrees ");
                  v15 = v93;
                  if ( v93 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v93,
                      0xE63u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v94 = StringCchPrintfW(v202, 0xFAu, L"ln ");
                v15 = v94;
                if ( v94 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v94,
                    0xE5Du,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v95 = StringCchPrintfW(v202, 0xFAu, L"log10 ");
              v15 = v95;
              if ( v95 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v95,
                  0xE57u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v96 = StringCchPrintfW(v202, 0xFAu, L"square ");
            v15 = v96;
            if ( v96 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v96,
                0xE51u,
                0);
              goto LABEL_359;
            }
          }
        }
        else if ( v9 == 45 )
        {
          v87 = StringCchPrintfW(v202, 0xFAu, L"pow ");
          v15 = v87;
          if ( v87 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v87,
              0xE4Bu,
              0);
            goto LABEL_359;
          }
        }
        else
        {
          v78 = v9 - 40;
          if ( v78 )
          {
            v79 = v78 - 1;
            if ( v79 )
            {
              v80 = v79 - 1;
              if ( v80 )
              {
                v81 = v80 - 1;
                if ( v81 )
                {
                  if ( v81 != 1 )
                    goto LABEL_361;
                  v82 = StringCchPrintfW(v202, 0xFAu, L"sqrt ");
                  v15 = v82;
                  if ( v82 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v82,
                      0xE45u,
                      0);
                    goto LABEL_359;
                  }
                }
                else
                {
                  v83 = StringCchPrintfW(v202, 0xFAu, L"round ");
                  v15 = v83;
                  if ( v83 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v83,
                      0xE3Fu,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v84 = StringCchPrintfW(v202, 0xFAu, L"floor ");
                v15 = v84;
                if ( v84 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v84,
                    0xE39u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v85 = StringCchPrintfW(v202, 0xFAu, L"ceil ");
              v15 = v85;
              if ( v85 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v85,
                  0xE33u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v86 = StringCchPrintfW(v202, 0xFAu, L"atan ");
            v15 = v86;
            if ( v86 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v86,
                0xE2Du,
                0);
              goto LABEL_359;
            }
          }
        }
      }
      else if ( v9 == 39 )
      {
        v77 = StringCchPrintfW(v202, 0xFAu, L"tan ");
        v15 = v77;
        if ( v77 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v77,
            0xE27u,
            0);
          goto LABEL_359;
        }
      }
      else if ( v9 > 33 )
      {
        v68 = v9 - 34;
        if ( v68 )
        {
          v69 = v68 - 1;
          if ( v69 )
          {
            v70 = v69 - 1;
            if ( v70 )
            {
              v71 = v70 - 1;
              if ( v71 )
              {
                if ( v71 != 1 )
                  goto LABEL_361;
                v72 = StringCchPrintfW(v202, 0xFAu, L"acos ");
                v15 = v72;
                if ( v72 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v72,
                    0xE21u,
                    0);
                  goto LABEL_359;
                }
              }
              else
              {
                v73 = StringCchPrintfW(v202, 0xFAu, L"cos ");
                v15 = v73;
                if ( v73 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v73,
                    0xE1Bu,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v74 = StringCchPrintfW(v202, 0xFAu, L"asin ");
              v15 = v74;
              if ( v74 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v74,
                  0xE15u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v75 = StringCchPrintfW(v202, 0xFAu, L"sin ");
            v15 = v75;
            if ( v75 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v75,
                0xE0Fu,
                0);
              goto LABEL_359;
            }
          }
        }
        else
        {
          v76 = StringCchPrintfW(v202, 0xFAu, L"concatenate ");
          v15 = v76;
          if ( v76 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v76,
              0xDFBu,
              0);
            goto LABEL_359;
          }
        }
      }
      else if ( v9 == 33 )
      {
        v67 = StringCchPrintfW(v202, 0xFAu, L"slerp ");
        v15 = v67;
        if ( v67 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v67,
            0xDF5u,
            0);
          goto LABEL_359;
        }
      }
      else
      {
        v56 = v9 - 27;
        if ( v56 )
        {
          v57 = v56 - 1;
          if ( v57 )
          {
            v58 = v57 - 1;
            if ( v58 )
            {
              v59 = v58 - 1;
              if ( v59 )
              {
                v60 = v59 - 1;
                if ( v60 )
                {
                  if ( v60 != 1 )
                    goto LABEL_361;
                  v61 = StringCchPrintfW(v202, 0xFAu, L"normalize ");
                  v15 = v61;
                  if ( v61 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v61,
                      0xDEFu,
                      0);
                    goto LABEL_359;
                  }
                }
                else
                {
                  v62 = StringCchPrintfW(v202, 0xFAu, L"distancesquared ");
                  v15 = v62;
                  if ( v62 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v62,
                      0xDE9u,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v63 = StringCchPrintfW(v202, 0xFAu, L"distance ");
                v15 = v63;
                if ( v63 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v63,
                    0xDE3u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v64 = StringCchPrintfW(v202, 0xFAu, L"lengthsquared ");
              v15 = v64;
              if ( v64 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v64,
                  0xDDDu,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v65 = StringCchPrintfW(v202, 0xFAu, L"length ");
            v15 = v65;
            if ( v65 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v65,
                0xDD7u,
                0);
              goto LABEL_359;
            }
          }
        }
        else
        {
          v66 = StringCchPrintfW(v202, 0xFAu, L"colorlerprgb ");
          v15 = v66;
          if ( v66 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v66,
              0xDD1u,
              0);
            goto LABEL_359;
          }
        }
      }
    }
    else if ( v9 == 26 )
    {
      v55 = StringCchPrintfW(v202, 0xFAu, L"colorlerphsl ");
      v15 = v55;
      if ( v55 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          4u,
          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
          1u,
          v55,
          0xDCBu,
          0);
        goto LABEL_359;
      }
    }
    else if ( v9 > 13 )
    {
      if ( v9 > 20 )
      {
        v46 = v9 - 21;
        if ( v46 )
        {
          v47 = v46 - 1;
          if ( v47 )
          {
            v48 = v47 - 1;
            if ( v48 )
            {
              v49 = v48 - 1;
              if ( v49 )
              {
                if ( v49 != 1 )
                  goto LABEL_361;
                v50 = StringCchPrintfW(v202, 0xFAu, L"colorlerp ");
                v15 = v50;
                if ( v50 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v50,
                    0xDC5u,
                    0);
                  goto LABEL_359;
                }
              }
              else
              {
                v51 = StringCchPrintfW(v202, 0xFAu, L"lerp ");
                v15 = v51;
                if ( v51 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v51,
                    0xDBFu,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v52 = StringCchPrintfW(v202, 0xFAu, L"inverse ");
              v15 = v52;
              if ( v52 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v52,
                  0xDB9u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v53 = StringCchPrintfW(v202, 0xFAu, L"transform ");
            v15 = v53;
            if ( v53 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v53,
                0xDB3u,
                0);
              goto LABEL_359;
            }
          }
        }
        else
        {
          v54 = StringCchPrintfW(v202, 0xFAu, L"scale ");
          v15 = v54;
          if ( v54 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v54,
              0xDADu,
              0);
            goto LABEL_359;
          }
        }
      }
      else if ( v9 == 20 )
      {
        v45 = StringCchPrintfW(v202, 0xFAu, L"clamp ");
        v15 = v45;
        if ( v45 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v45,
            0xDA7u,
            0);
          goto LABEL_359;
        }
      }
      else
      {
        v34 = v9 - 14;
        if ( v34 )
        {
          v35 = v34 - 1;
          if ( v35 )
          {
            v36 = v35 - 1;
            if ( v36 )
            {
              v37 = v36 - 1;
              if ( v37 )
              {
                v38 = v37 - 1;
                if ( v38 )
                {
                  if ( v38 != 1 )
                    goto LABEL_361;
                  v39 = StringCchPrintfW(v202, 0xFAu, L"max ");
                  v15 = v39;
                  if ( v39 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v39,
                      0xDA1u,
                      0);
                    goto LABEL_359;
                  }
                }
                else
                {
                  v40 = StringCchPrintfW(v202, 0xFAu, L"min ");
                  v15 = v40;
                  if ( v40 < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(
                      4u,
                      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                      1u,
                      v40,
                      0xD9Bu,
                      0);
                    goto LABEL_359;
                  }
                }
              }
              else
              {
                v41 = StringCchPrintfW(v202, 0xFAu, L"mod ");
                v15 = v41;
                if ( v41 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(
                    4u,
                    &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                    1u,
                    v41,
                    0xD95u,
                    0);
                  goto LABEL_359;
                }
              }
            }
            else
            {
              v42 = StringCchPrintfW(v202, 0xFAu, L"/ ");
              v15 = v42;
              if ( v42 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v42,
                  0xD59u,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v43 = StringCchPrintfW(v202, 0xFAu, L"* ");
            v15 = v43;
            if ( v43 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v43,
                0xD53u,
                0);
              goto LABEL_359;
            }
          }
        }
        else
        {
          v44 = StringCchPrintfW(v202, 0xFAu, L"- ");
          v15 = v44;
          if ( v44 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v44,
              0xD4Du,
              0);
            goto LABEL_359;
          }
        }
      }
    }
    else if ( v9 == 13 )
    {
      v33 = StringCchPrintfW(v202, 0xFAu, L"+ ");
      v15 = v33;
      if ( v33 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          4u,
          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
          1u,
          v33,
          0xD47u,
          0);
        goto LABEL_359;
      }
    }
    else if ( v9 > 6 )
    {
      v23 = v9 - 7;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            v26 = v25 - 2;
            if ( v26 )
            {
              if ( v26 != 1 )
                goto LABEL_361;
              v27 = StringCchPrintfW(v202, 0xFAu, L"negate ");
              v15 = v27;
              if ( v27 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v27,
                  0xD41u,
                  0);
                goto LABEL_359;
              }
            }
            else
            {
              v28 = StringCchPrintfW(v202, 0xFAu, L"abs ");
              v15 = v28;
              if ( v28 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v28,
                  0xD3Bu,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v29 = (int *)L"(in degrees) ";
            if ( *(int *)(*((_QWORD *)this + 15) + 20LL * *(unsigned int *)(v8 + 4)) >= 0 )
              v29 = &dword_1801B7F9C;
            v199[0] = *(_DWORD *)(*((_QWORD *)this + 15) + 20LL * *(unsigned int *)(v8 + 4)) & 0x7FFFFFFF;
            v30 = StringCchPrintfW(v202, 0xFAu, L"{%d}.%d %s", v6, *(_QWORD *)v199, v29);
            v15 = v30;
            if ( v30 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v30,
                0xD32u,
                0);
              goto LABEL_359;
            }
            v200 = ++v6;
          }
        }
        else
        {
          v31 = StringCchPrintfW(
                  v202,
                  0xFAu,
                  L"matrix4x4(%f, %f, %f, %f, %f, %f, %f, %f, %f, %f, %f, %f, %f, %f, %f, %f) ",
                  *(float *)(v8 + 4),
                  *(float *)(v8 + 8),
                  *(float *)(v8 + 12),
                  *(float *)(v8 + 16),
                  *(float *)(v8 + 20),
                  *(float *)(v8 + 24),
                  *(float *)(v8 + 28),
                  *(float *)(v8 + 32),
                  *(float *)(v8 + 36),
                  *(float *)(v8 + 40),
                  *(float *)(v8 + 44),
                  *(float *)(v8 + 48),
                  *(float *)(v8 + 52),
                  *(float *)(v8 + 56),
                  *(float *)(v8 + 60),
                  *(float *)(v8 + 64));
          v15 = v31;
          if ( v31 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v31,
              0xD29u,
              0);
            goto LABEL_359;
          }
        }
      }
      else
      {
        v32 = StringCchPrintfW(
                v202,
                0xFAu,
                L"matrix3x2(%f, %f, %f, %f, %f, %f) ",
                *(float *)(v8 + 4),
                *(float *)(v8 + 8),
                *(float *)(v8 + 12),
                *(float *)(v8 + 16),
                *(float *)(v8 + 20),
                *(float *)(v8 + 24));
        v15 = v32;
        if ( v32 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v32,
            0xD1Bu,
            0);
          goto LABEL_359;
        }
      }
    }
    else if ( v9 == 6 )
    {
      v22 = StringCchPrintfW(
              v202,
              0xFAu,
              L"quaternion(%f, %f, %f, %f) ",
              *(float *)(v8 + 4),
              *(float *)(v8 + 8),
              *(float *)(v8 + 12),
              *(float *)(v8 + 16));
      v15 = v22;
      if ( v22 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          4u,
          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
          1u,
          v22,
          0xD0Eu,
          0);
        goto LABEL_359;
      }
    }
    else if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( v13 != 1 )
                goto LABEL_361;
              v14 = StringCchPrintfW(
                      v202,
                      0xFAu,
                      L"color(%f, %f, %f, %f) ",
                      *(float *)(v8 + 16),
                      *(float *)(v8 + 4),
                      *(float *)(v8 + 8),
                      *(float *)(v8 + 12));
              v15 = v14;
              if ( v14 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v14,
                  0xD05u,
                  0);
                goto LABEL_359;
              }
            }
            else
            {
              v16 = StringCchPrintfW(
                      v202,
                      0xFAu,
                      L"vector4(%f, %f, %f, %f) ",
                      *(float *)(v8 + 4),
                      *(float *)(v8 + 8),
                      *(float *)(v8 + 12),
                      *(float *)(v8 + 16));
              v15 = v16;
              if ( v16 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(
                  4u,
                  &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                  1u,
                  v16,
                  0xCFCu,
                  0);
                goto LABEL_359;
              }
            }
          }
          else
          {
            v17 = StringCchPrintfW(
                    v202,
                    0xFAu,
                    L"vector3(%f, %f, %f) ",
                    *(float *)(v8 + 4),
                    *(float *)(v8 + 8),
                    *(float *)(v8 + 12));
            v15 = v17;
            if ( v17 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                4u,
                &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
                1u,
                v17,
                0xCF3u,
                0);
              goto LABEL_359;
            }
          }
        }
        else
        {
          v18 = StringCchPrintfW(v202, 0xFAu, L"vector2(%f, %f) ", *(float *)(v8 + 4), *(float *)(v8 + 8));
          v15 = v18;
          if ( v18 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              4u,
              &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v18,
              0xCEAu,
              0);
            goto LABEL_359;
          }
        }
      }
      else
      {
        v19 = StringCchPrintfW(v202, 0xFAu, L"%f ", *(float *)(v8 + 4));
        v15 = v19;
        if ( v19 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v19,
            0xCE2u,
            0);
          goto LABEL_359;
        }
      }
    }
    else
    {
      v20 = L"true";
      if ( !*(_BYTE *)(v8 + 4) )
        v20 = L"false";
      v21 = StringCchPrintfW(v202, 0xFAu, L"%ws ", v20);
      v15 = v21;
      if ( v21 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          4u,
          &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
          1u,
          v21,
          0xCDAu,
          0);
        goto LABEL_359;
      }
    }
    v195 = StringCchCatW(a2, a3, v202);
    v15 = v195;
    if ( v195 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(
        4u,
        &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
        1u,
        v195,
        0xF83u,
        0);
      goto LABEL_359;
    }
    v7 = (unsigned int)(v7 + 1);
  }
  v196 = StringCchLengthW(a2, a3, &v201);
  v15 = v196;
  if ( v196 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &Windows::UI::Composition::ExpressionAnimationBuilder::MILINSTRUMENTATIONHRESULTLIST,
      1u,
      v196,
      0xF8Bu,
      0);
    goto LABEL_359;
  }
  v197 = v201;
  if ( v201 )
    v197 = v201 - 1;
  v15 = 0;
LABEL_360:
  a2[v197] = 0;
  return v15;
}

```

## disassembly

```asm
0x1801493c0  mov     rax, rsp
0x1801493c3  mov     [rax+20h], rbx
0x1801493c7  push    rbp
0x1801493c8  push    rsi
0x1801493c9  push    rdi
0x1801493ca  push    r12
0x1801493cc  push    r13
0x1801493ce  push    r14
0x1801493d0  push    r15
0x1801493d2  lea     rbp, [rax-698h]
0x1801493d9  sub     rsp, 780h
0x1801493e0  movaps  xmmword ptr [rax-48h], xmm6
0x1801493e4  movaps  xmmword ptr [rax-58h], xmm7
0x1801493e8  movaps  xmmword ptr [rax-68h], xmm8
0x1801493ed  movaps  xmmword ptr [rax-78h], xmm9
0x1801493f2  movaps  xmmword ptr [rax-88h], xmm10
0x1801493fa  movaps  xmmword ptr [rax-98h], xmm11
0x180149402  movaps  xmmword ptr [rax-0A8h], xmm12
0x18014940a  movaps  xmmword ptr [rax-0B8h], xmm13
0x180149412  movaps  xmmword ptr [rax-0C8h], xmm14
0x18014941a  movaps  xmmword ptr [rax-0D8h], xmm15
0x180149422  mov     rax, cs:__security_cookie
0x180149429  xor     rax, rsp
0x18014942c  mov     [rbp+690h+var_E0], rax
0x180149433  mov     [rbp+690h+var_708], 0
0x18014943b  mov     r14, r8
0x18014943e  mov     r13, rdx
0x180149441  mov     r15, rcx
0x180149444  test    rdx, rdx
0x180149447  jz      loc_18014B1DE
0x18014944d  test    r8, r8
0x180149450  jz      loc_18014B1DE
0x180149456  xor     esi, esi
0x180149458  xor     eax, eax
0x18014945a  mov     [rbp+690h+var_710], esi
0x18014945d  xor     r12d, r12d
0x180149460  mov     [rdx], ax
0x180149463  mov     r10d, 0FAh
0x180149469  cmp     r12d, [r15+28h]
0x18014946d  jnb     loc_18014B121
0x180149473  mov     rax, [r15+10h]
0x180149477  mov     rdi, [rax+r12*8]
0x18014947b  mov     ecx, [rdi]
0x18014947d  cmp     ecx, 34h ; '4'
0x180149480  jg      loc_18014A353
0x180149486  jz      loc_18014A2BB
0x18014948c  cmp     ecx, 1Ah
0x18014948f  jg      loc_180149D29
0x180149495  jz      loc_180149CF6
0x18014949b  cmp     ecx, 0Dh
0x18014949e  jg      loc_180149A30
0x1801494a4  jz      loc_1801499FD
0x1801494aa  cmp     ecx, 6
0x1801494ad  jg      loc_18014975B
0x1801494b3  jz      loc_1801496F1
0x1801494b9  test    ecx, ecx
0x1801494bb  jz      loc_1801496A8
0x1801494c1  sub     ecx, 1
0x1801494c4  jz      loc_180149668
0x1801494ca  sub     ecx, 1
0x1801494cd  jz      loc_18014961A
0x1801494d3  sub     ecx, 1
0x1801494d6  jz      loc_1801495BE
0x1801494dc  sub     ecx, 1
0x1801494df  jz      short loc_180149554
0x1801494e1  cmp     ecx, 1
0x1801494e4  jnz     loc_18014B1DE
0x1801494ea  movss   xmm0, dword ptr [rdi+0Ch]
0x1801494ef  lea     r8, aColorFFFF; "color(%f, %f, %f, %f) "
0x1801494f6  movss   xmm1, dword ptr [rdi+8]
0x1801494fb  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x1801494ff  movss   xmm3, dword ptr [rdi+10h]
0x180149504  mov     edx, r10d; unsigned __int64
0x180149507  movss   xmm2, dword ptr [rdi+4]
0x18014950c  cvtps2pd xmm0, xmm0
0x18014950f  cvtps2pd xmm1, xmm1
0x180149512  movsd   [rsp+7B0h+var_780], xmm0
0x180149518  cvtps2pd xmm3, xmm3
0x18014951b  cvtps2pd xmm2, xmm2
0x18014951e  movsd   [rsp+7B0h+var_788], xmm1
0x180149524  movq    r9, xmm3
0x180149529  movsd   qword ptr [rsp+7B0h+var_790], xmm2
0x18014952f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180149534  mov     ebx, eax
0x180149536  test    eax, eax
0x180149538  jns     loc_18014B004
0x18014953e  mov     [rsp+7B0h+var_788], 0
0x180149547  mov     [rsp+7B0h+var_790], 0D05h
0x18014954f  jmp     loc_18014B157
0x180149554  movss   xmm0, dword ptr [rdi+10h]
0x180149559  lea     r8, aVector4FFFF; "vector4(%f, %f, %f, %f) "
0x180149560  movss   xmm1, dword ptr [rdi+0Ch]
0x180149565  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x180149569  movss   xmm3, dword ptr [rdi+4]
0x18014956e  mov     rdx, r10; unsigned __int64
0x180149571  movss   xmm2, dword ptr [rdi+8]
0x180149576  cvtps2pd xmm0, xmm0
0x180149579  cvtps2pd xmm1, xmm1
0x18014957c  movsd   [rsp+7B0h+var_780], xmm0
0x180149582  cvtps2pd xmm3, xmm3
0x180149585  cvtps2pd xmm2, xmm2
0x180149588  movsd   [rsp+7B0h+var_788], xmm1
0x18014958e  movq    r9, xmm3
0x180149593  movsd   qword ptr [rsp+7B0h+var_790], xmm2
0x180149599  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014959e  mov     ebx, eax
0x1801495a0  test    eax, eax
0x1801495a2  jns     loc_18014B004
0x1801495a8  mov     [rsp+7B0h+var_788], 0
0x1801495b1  mov     [rsp+7B0h+var_790], 0CFCh
0x1801495b9  jmp     loc_18014B157
0x1801495be  movss   xmm0, dword ptr [rdi+0Ch]
0x1801495c3  lea     r8, aVector3FFF; "vector3(%f, %f, %f) "
0x1801495ca  movss   xmm3, dword ptr [rdi+4]
0x1801495cf  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x1801495d3  movss   xmm1, dword ptr [rdi+8]
0x1801495d8  mov     rdx, r10; unsigned __int64
0x1801495db  cvtps2pd xmm0, xmm0
0x1801495de  cvtps2pd xmm3, xmm3
0x1801495e1  cvtps2pd xmm1, xmm1
0x1801495e4  movsd   [rsp+7B0h+var_788], xmm0
0x1801495ea  movq    r9, xmm3
0x1801495ef  movsd   qword ptr [rsp+7B0h+var_790], xmm1
0x1801495f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801495fa  mov     ebx, eax
0x1801495fc  test    eax, eax
0x1801495fe  jns     loc_18014B004
0x180149604  mov     [rsp+7B0h+var_788], 0
0x18014960d  mov     [rsp+7B0h+var_790], 0CF3h
0x180149615  jmp     loc_18014B157
0x18014961a  movss   xmm3, dword ptr [rdi+4]
0x18014961f  lea     r8, aVector2FF; "vector2(%f, %f) "
0x180149626  movss   xmm0, dword ptr [rdi+8]
0x18014962b  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x18014962f  cvtps2pd xmm3, xmm3
0x180149632  mov     rdx, r10; unsigned __int64
0x180149635  cvtps2pd xmm0, xmm0
0x180149638  movq    r9, xmm3
0x18014963d  movsd   qword ptr [rsp+7B0h+var_790], xmm0
0x180149643  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180149648  mov     ebx, eax
0x18014964a  test    eax, eax
0x18014964c  jns     loc_18014B004
0x180149652  mov     [rsp+7B0h+var_788], 0
0x18014965b  mov     [rsp+7B0h+var_790], 0CEAh
0x180149663  jmp     loc_18014B157
0x180149668  movss   xmm3, dword ptr [rdi+4]
0x18014966d  lea     r8, asc_1801C2438; "%f "
0x180149674  cvtps2pd xmm3, xmm3
0x180149677  mov     rdx, r10; unsigned __int64
0x18014967a  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x18014967e  movq    r9, xmm3
0x180149683  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180149688  mov     ebx, eax
0x18014968a  test    eax, eax
0x18014968c  jns     loc_18014B004
0x180149692  mov     [rsp+7B0h+var_788], 0
0x18014969b  mov     [rsp+7B0h+var_790], 0CE2h
0x1801496a3  jmp     loc_18014B157
0x1801496a8  cmp     byte ptr [rdi+4], 0
0x1801496ac  lea     rax, aFalse; "false"
0x1801496b3  lea     r9, aTrue; "true"
0x1801496ba  mov     rdx, r10; unsigned __int64
0x1801496bd  cmovz   r9, rax
0x1801496c1  lea     r8, aWs_0; "%ws "
0x1801496c8  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x1801496cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801496d1  mov     ebx, eax
0x1801496d3  test    eax, eax
0x1801496d5  jns     loc_18014B004
0x1801496db  mov     [rsp+7B0h+var_788], 0
0x1801496e4  mov     [rsp+7B0h+var_790], 0CDAh
0x1801496ec  jmp     loc_18014B157
0x1801496f1  movss   xmm0, dword ptr [rdi+10h]
0x1801496f6  lea     r8, aQuaternionFFFF; "quaternion(%f, %f, %f, %f) "
0x1801496fd  movss   xmm1, dword ptr [rdi+0Ch]
0x180149702  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x180149706  movss   xmm3, dword ptr [rdi+4]
0x18014970b  mov     rdx, r10; unsigned __int64
0x18014970e  movss   xmm2, dword ptr [rdi+8]
0x180149713  cvtps2pd xmm0, xmm0
0x180149716  cvtps2pd xmm1, xmm1
0x180149719  movsd   [rsp+7B0h+var_780], xmm0
0x18014971f  cvtps2pd xmm3, xmm3
0x180149722  cvtps2pd xmm2, xmm2
0x180149725  movsd   [rsp+7B0h+var_788], xmm1
0x18014972b  movq    r9, xmm3
0x180149730  movsd   qword ptr [rsp+7B0h+var_790], xmm2
0x180149736  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014973b  mov     ebx, eax
0x18014973d  test    eax, eax
0x18014973f  jns     loc_18014B004
0x180149745  mov     [rsp+7B0h+var_788], 0
0x18014974e  mov     [rsp+7B0h+var_790], 0D0Eh
0x180149756  jmp     loc_18014B157
0x18014975b  sub     ecx, 7
0x18014975e  jz      loc_180149977
0x180149764  sub     ecx, 1
0x180149767  jz      loc_180149844
0x18014976d  sub     ecx, 1
0x180149770  jz      short loc_1801497E6
0x180149772  sub     ecx, 2
0x180149775  jz      short loc_1801497B3
0x180149777  cmp     ecx, 1
0x18014977a  jnz     loc_18014B1DE
0x180149780  lea     r8, aNegate; "negate "
0x180149787  mov     rdx, r10; unsigned __int64
0x18014978a  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x18014978e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180149793  mov     ebx, eax
0x180149795  test    eax, eax
0x180149797  jns     loc_18014B004
0x18014979d  mov     [rsp+7B0h+var_788], 0
0x1801497a6  mov     [rsp+7B0h+var_790], 0D41h
0x1801497ae  jmp     loc_18014B157
0x1801497b3  lea     r8, aAbs; "abs "
0x1801497ba  mov     rdx, r10; unsigned __int64
0x1801497bd  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x1801497c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801497c6  mov     ebx, eax
0x1801497c8  test    eax, eax
0x1801497ca  jns     loc_18014B004
0x1801497d0  mov     [rsp+7B0h+var_788], 0
0x1801497d9  mov     [rsp+7B0h+var_790], 0D3Bh
0x1801497e1  jmp     loc_18014B157
0x1801497e6  mov     eax, [rdi+4]
0x1801497e9  lea     r8, dword_1801B7F9C
0x1801497f0  mov     r9d, esi
0x1801497f3  lea     rcx, [rax+rax*4]
0x1801497f7  mov     rax, [r15+78h]
0x1801497fb  mov     edx, [rax+rcx*4]
0x1801497fe  mov     eax, edx
0x180149800  btr     eax, 1Fh
0x180149804  shr     edx, 1Fh
0x180149807  test    dl, dl
0x180149809  lea     rcx, aInDegrees; "(in degrees) "
0x180149810  mov     rdx, r10; unsigned __int64
0x180149813  cmovz   rcx, r8
0x180149817  lea     r8, aDDS; "{%d}.%d %s"
0x18014981e  mov     [rsp+7B0h+var_788], rcx
0x180149823  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x180149827  mov     [rsp+7B0h+var_790], eax
0x18014982b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180149830  mov     ebx, eax
0x180149832  test    eax, eax
0x180149834  js      loc_18014B025
0x18014983a  inc     esi
0x18014983c  mov     [rbp+690h+var_710], esi
0x18014983f  jmp     loc_18014B004
0x180149844  movss   xmm0, dword ptr [rdi+40h]
0x180149849  lea     r8, aMatrix4x4FFFFF; "matrix4x4(%f, %f, %f, %f, %f, %f, %f, %"...
0x180149850  movss   xmm1, dword ptr [rdi+3Ch]
0x180149855  lea     rcx, [rbp+690h+var_700]; unsigned __int16 *
0x180149859  movss   xmm2, dword ptr [rdi+38h]
0x18014985e  mov     rdx, r10; unsigned __int64
0x180149861  movss   xmm4, dword ptr [rdi+34h]
0x180149866  movss   xmm5, dword ptr [rdi+30h]
0x18014986b  movss   xmm6, dword ptr [rdi+2Ch]
0x180149870  movss   xmm7, dword ptr [rdi+28h]
0x180149875  movss   xmm8, dword ptr [rdi+24h]
0x18014987b  movss   xmm9, dword ptr [rdi+20h]
0x180149881  movss   xmm10, dword ptr [rdi+1Ch]
0x180149887  movss   xmm11, dword ptr [rdi+18h]
0x18014988d  movss   xmm12, dword ptr [rdi+14h]
0x180149893  movss   xmm13, dword ptr [rdi+10h]
0x180149899  movss   xmm14, dword ptr [rdi+0Ch]
0x18014989f  movss   xmm3, dword ptr [rdi+4]
0x1801498a4  movss   xmm15, dword ptr [rdi+8]
0x1801498aa  cvtps2pd xmm0, xmm0
0x1801498ad  cvtps2pd xmm1, xmm1
0x1801498b0  movsd   [rsp+7B0h+var_720], xmm0
0x1801498b9  movsd   [rsp+7B0h+var_728], xmm1
0x1801498c2  cvtps2pd xmm2, xmm2
0x1801498c5  cvtps2pd xmm4, xmm4
0x1801498c8  movsd   [rsp+7B0h+var_730], xmm2
0x1801498d1  movsd   [rsp+7B0h+var_738], xmm4
0x1801498d7  cvtps2pd xmm5, xmm5
0x1801498da  cvtps2pd xmm6, xmm6
0x1801498dd  movsd   [rsp+7B0h+var_740], xmm5
0x1801498e3  movsd   [rsp+7B0h+var_748], xmm6
0x1801498e9  cvtps2pd xmm7, xmm7
0x1801498ec  cvtps2pd xmm8, xmm8
0x1801498f0  movsd   [rsp+7B0h+var_750], xmm7
0x1801498f6  movsd   [rsp+7B0h+var_758], xmm8
0x1801498fd  cvtps2pd xmm9, xmm9
0x180149901  cvtps2pd xmm10, xmm10
0x180149905  movsd   [rsp+7B0h+var_760], xmm9
0x18014990c  movsd   [rsp+7B0h+var_768], xmm10
0x180149913  cvtps2pd xmm11, xmm11
0x180149917  cvtps2pd xmm12, xmm12
0x18014991b  movsd   [rsp+7B0h+var_770], xmm11
0x180149922  movsd   [rsp+7B0h+var_778], xmm12
0x180149929  cvtps2pd xmm13, xmm13
0x18014992d  cvtps2pd xmm14, xmm14
0x180149931  movsd   [rsp+7B0h+var_780], xmm13
0x180149938  cvtps2pd xmm3, xmm3
0x18014993b  cvtps2pd xmm15, xmm15
0x18014993f  movsd   [rsp+7B0h+var_788], xmm14
0x180149946  movq    r9, xmm3
0x18014994b  movsd   qword ptr [rsp+7B0h+var_790], xmm15
  ... truncated ...
```
