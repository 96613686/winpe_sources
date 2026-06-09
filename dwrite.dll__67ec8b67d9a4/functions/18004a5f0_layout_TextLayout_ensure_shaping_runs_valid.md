# layout::TextLayout::ensure_shaping_runs_valid

- ea: `0x18004a5f0`
- end: `0x18004c6c3`
- name: `layout::TextLayout::ensure_shaping_runs_valid`
- size: `8403`
- prototype: ``
- caller_count: `2`
- callee_count: `40`
- tags: `installer_update`

## callers

- `0x18001e4a0`
- `0x1800474a0`

## callees

- `0x180022f50`
- `0x180044ca0`
- `0x180045600`
- `0x180045ba0`
- `0x180045e70`
- `0x180046350`
- `0x180046410`
- `0x1800486b0`
- `0x180048fa0`
- `0x180049450`
- `0x180049c20`
- `0x18004a460`
- `0x18004a5f0`
- `0x180056650`
- `0x180056780`
- `0x18005a4a0`
- `0x18005ce10`
- `0x18005d420`
- `0x18005e340`
- `0x18005e500`
- `0x18005e5f0`
- `0x18005ed20`
- `0x1800dc910`
- `0x18010b6d0`
- `0x18010c8b0`
- `0x18010d1d0`
- `0x18010d830`
- `0x18010e630`
- `0x18010eaf0`
- `0x180212f4c`
- `0x180316190`
- `0x180316255`
- `0x1803168c1`
- `0x180316980`
- `0x180316a30`
- `0x180316ae0`
- `0x180316ce0`
- `0x180316d00`
- `0x180318870`
- `0x18031a1c0`

## import_xrefs

- `kernel32!HeapFree` at `0x18004aa1d`
- `kernel32!HeapFree` at `0x18004aa3b`
- `kernel32!HeapFree` at `0x18004aa56`
- `kernel32!HeapFree` at `0x18004c002`
- `kernel32!HeapFree` at `0x18004c372`
- `kernel32!HeapFree` at `0x18004aa1d`
- `kernel32!HeapFree` at `0x18004aa3b`
- `kernel32!HeapFree` at `0x18004aa56`
- `kernel32!HeapFree` at `0x18004c002`
- `kernel32!HeapFree` at `0x18004c372`
- `kernel32!GetProcessHeap` at `0x18004aa0f`
- `kernel32!GetProcessHeap` at `0x18004aa2d`
- `kernel32!GetProcessHeap` at `0x18004aa48`
- `kernel32!GetProcessHeap` at `0x18004bff4`
- `kernel32!GetProcessHeap` at `0x18004c364`
- `kernel32!GetProcessHeap` at `0x18004aa0f`
- `kernel32!GetProcessHeap` at `0x18004aa2d`
- `kernel32!GetProcessHeap` at `0x18004aa48`
- `kernel32!GetProcessHeap` at `0x18004bff4`
- `kernel32!GetProcessHeap` at `0x18004c364`

## string_xrefs

- `0x18004c467`: `assertion failed: text_range.end <= ro.text.len() && text_range.start < text_range.endC++ code failed to create last resort font reference.rust\layout\src\text_layout_factory.rs`
- `0x18004c50c`: `assertion failed: text_range.end <= ro.text.len() && text_range.start < text_range.endC++ code failed to create last resort font reference.rust\layout\src\text_layout_factory.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall layout::TextLayout::ensure_shaping_runs_valid(_BYTE *a1)
{
  __int64 v1; // rbx
  bool v2; // zf
  _QWORD *v3; // rsi
  __int64 v4; // rdi
  unsigned __int64 v5; // rdi
  unsigned __int32 v6; // ecx
  unsigned __int16 *v7; // rsi
  int v8; // ebx
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rdx
  unsigned __int16 v11; // r8
  __int64 v12; // rcx
  unsigned __int8 BidiClass; // al
  __int64 v14; // r8
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rcx
  char v18; // cl
  unsigned int v19; // r12d
  unsigned int v20; // r14d
  _BYTE *v21; // rbx
  __int64 v22; // rsi
  unsigned __int64 v23; // rsi
  void *v24; // r15
  void *v25; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  unsigned int v29; // eax
  unsigned __int64 v30; // r15
  int i; // ebx
  __m128i v32; // xmm1
  int v33; // r12d
  unsigned __int64 v34; // r13
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // r9
  _QWORD *v38; // r10
  char v39; // r14
  __int64 v40; // rax
  unsigned __int64 v41; // rcx
  char v42; // al
  unsigned __int64 v43; // rsi
  int v44; // r8d
  char v45; // r11
  char v46; // r12
  int v47; // ebx
  unsigned __int64 *v48; // r15
  unsigned __int64 orientation_info; // rax
  __int64 v50; // rdx
  __int32 v51; // esi
  __m128i v52; // xmm1
  unsigned __int64 v53; // r13
  unsigned __int64 v54; // r15
  unsigned __int64 v55; // rdi
  unsigned __int64 v56; // r12
  __int32 v57; // eax
  unsigned int v58; // r13d
  __int8 v59; // si
  __int8 v60; // al
  unsigned __int64 v61; // r12
  __int64 v62; // rsi
  __int32 v63; // r14d
  __int64 v64; // rax
  __m128i v65; // xmm1
  __m128i v66; // xmm2
  int v67; // edx
  __m128i v68; // xmm1
  __m128i v69; // xmm1
  unsigned int v70; // ebx
  int v71; // ecx
  __m128i si128; // xmm1
  __int64 v73; // rax
  __m128i v74; // xmm1
  __m128i v75; // xmm2
  unsigned __int64 v76; // rax
  unsigned __int64 v77; // rdx
  unsigned __int64 v78; // rsi
  unsigned __int64 v79; // rdx
  __int64 v80; // rbx
  __int64 v81; // rdi
  __int64 v82; // rsi
  _QWORD *v83; // r12
  __int64 v84; // rcx
  __int64 v85; // rsi
  __int64 v86; // rdi
  _QWORD *v87; // rsi
  __int64 v88; // rax
  __int64 v89; // rsi
  __int64 v90; // rdi
  _QWORD *v91; // rsi
  __int64 v92; // rax
  void *v93; // rdx
  __m128i v94; // xmm6
  __m128i v95; // xmm7
  __m128i v96; // xmm8
  __m128i v97; // xmm9
  __m128i v98; // xmm10
  __m128 v99; // xmm11
  unsigned __int64 v100; // r14
  unsigned __int64 v101; // r15
  unsigned __int64 v102; // rbx
  __int64 v103; // r8
  __int64 v104; // rax
  __int64 v105; // rcx
  unsigned __int64 v106; // r13
  unsigned __int64 v107; // rax
  __int64 v108; // r8
  unsigned __int64 v109; // rdi
  __int64 v110; // r11
  __int64 v111; // rsi
  unsigned __int64 v112; // rcx
  unsigned __int64 v113; // r9
  __int64 v114; // rdi
  unsigned __int64 v115; // rcx
  __int64 v116; // r12
  unsigned __int64 v117; // r13
  __int64 v118; // rdx
  unsigned __int64 v119; // r15
  float *inline_object_metrics; // rsi
  unsigned __int64 v121; // rdi
  __int64 v122; // rbx
  __int64 v123; // r12
  unsigned __int64 v124; // rdx
  unsigned __int64 v125; // rdx
  unsigned __int64 v126; // rdx
  unsigned __int64 v127; // rdx
  __m128i *v128; // r15
  unsigned __int64 v129; // rbx
  void (*v130)(void); // rax
  float v131; // xmm12_4
  float v132; // xmm13_4
  float v133; // xmm14_4
  unsigned int v134; // r13d
  unsigned int v135; // esi
  unsigned int v136; // r15d
  float v137; // xmm15_4
  __int64 v138; // r9
  __int32 v139; // ecx
  unsigned __int64 v140; // rdx
  unsigned __int64 v141; // rcx
  char v142; // r8
  __int64 v143; // r15
  unsigned __int64 v144; // rsi
  __int64 v145; // rax
  __int64 v146; // rdi
  unsigned __int64 v147; // rax
  __int64 v148; // rbx
  unsigned __int64 v149; // rdx
  __int64 v150; // rsi
  __int64 v151; // r14
  __int16 *v152; // rax
  __int64 v153; // r9
  __int64 v154; // rcx
  unsigned __int64 v155; // rbx
  __int16 v156; // r12
  unsigned int v157; // esi
  int v158; // r13d
  __int64 v159; // rcx
  __int64 v160; // r9
  int v161; // r13d
  int v162; // ebx
  int v163; // esi
  int v164; // r15d
  __int64 v165; // r8
  unsigned __int16 *font_metrics; // rax
  int v167; // ecx
  __int64 v168; // rsi
  __int64 v169; // rax
  int v170; // edx
  unsigned __int64 v171; // r14
  __m128i v172; // xmm0
  _QWORD *v173; // rsi
  int v174; // edx
  __int64 v175; // rbx
  HANDLE v176; // rax
  _QWORD *v177; // rdi
  unsigned __int64 v178; // rbx
  __int64 v179; // rsi
  __int64 v180; // rax
  __int64 v181; // rcx
  __int64 v182; // rdx
  __int64 v183; // r8
  __m128i v184; // xmm0
  __int64 v185; // rdx
  __m128i v186; // xmm0
  unsigned __int64 v187; // r14
  __int64 v188; // r12
  _QWORD *v189; // r15
  unsigned __int64 v190; // rsi
  unsigned __int64 v191; // rdx
  unsigned __int64 v192; // rdx
  unsigned __int64 v193; // rdx
  __int64 v194; // rsi
  size_t v195; // rbx
  unsigned __int64 v196; // rdx
  __int64 line_spacing_metrics; // rax
  __int64 v198; // rsi
  __int64 v199; // rax
  __int64 v200; // rcx
  __int64 v201; // rcx
  __int64 v202; // rdi
  HANDLE v203; // rax
  _QWORD *v204; // rsi
  __int64 v205; // rcx
  int v206; // [rsp+20h] [rbp-60h]
  int v207; // [rsp+20h] [rbp-60h]
  __m128i v208; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v209; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v210; // [rsp+B8h] [rbp+38h]
  __int64 v211; // [rsp+C0h] [rbp+40h]
  __int64 v212; // [rsp+C8h] [rbp+48h]
  _QWORD *v213; // [rsp+D0h] [rbp+50h]
  __int32 v214; // [rsp+D8h] [rbp+58h]
  unsigned __int64 v215; // [rsp+E0h] [rbp+60h]
  __int64 v216; // [rsp+E8h] [rbp+68h]
  LPVOID v217[2]; // [rsp+F0h] [rbp+70h] BYREF
  __m128i v218; // [rsp+100h] [rbp+80h] BYREF
  __m128i v219; // [rsp+110h] [rbp+90h]
  __int32 v220; // [rsp+120h] [rbp+A0h]
  __m128i v221[8]; // [rsp+130h] [rbp+B0h] BYREF
  __int64 v222; // [rsp+1B8h] [rbp+138h]
  LPVOID lpMem[2]; // [rsp+1C0h] [rbp+140h] BYREF
  __m128i v224; // [rsp+1D0h] [rbp+150h] BYREF
  __m128i v225; // [rsp+1E0h] [rbp+160h]
  __m128i v226; // [rsp+1F0h] [rbp+170h]
  __int64 v227; // [rsp+200h] [rbp+180h]
  __int64 v228; // [rsp+208h] [rbp+188h]
  __m256i v229; // [rsp+210h] [rbp+190h] BYREF
  __m128i v230; // [rsp+230h] [rbp+1B0h]
  __m128i v231; // [rsp+240h] [rbp+1C0h]
  __int64 v232; // [rsp+250h] [rbp+1D0h]
  __int64 v233; // [rsp+260h] [rbp+1E0h]
  unsigned __int64 *v234; // [rsp+268h] [rbp+1E8h]
  _QWORD *v235; // [rsp+270h] [rbp+1F0h]
  __int64 v236; // [rsp+278h] [rbp+1F8h]
  __int64 v237; // [rsp+280h] [rbp+200h]
  unsigned __int64 v238; // [rsp+288h] [rbp+208h]
  unsigned __int64 v239; // [rsp+290h] [rbp+210h]
  unsigned __int64 v240; // [rsp+298h] [rbp+218h]
  __int64 v241; // [rsp+2A0h] [rbp+220h]
  unsigned __int64 v242; // [rsp+2A8h] [rbp+228h]
  unsigned __int64 v243; // [rsp+2B0h] [rbp+230h]
  _QWORD *v244; // [rsp+2B8h] [rbp+238h]
  unsigned __int64 v245; // [rsp+2C0h] [rbp+240h]
  __int64 v246; // [rsp+2C8h] [rbp+248h]
  char v247; // [rsp+2D7h] [rbp+257h]
  __int64 v248; // [rsp+2D8h] [rbp+258h]

  v248 = -2;
  if ( (a1[824] & 0x10) != 0 )
    return;
  v1 = (__int64)a1;
  if ( ((a1[188] ^ a1[184]) & 2) != 0 )
    return;
  layout::TextLayout::ensure_font_runs_valid(a1);
  v2 = (*(_BYTE *)(v1 + 824) & 8) == 0;
  v246 = v1;
  if ( v2 )
  {
    v3 = *(_QWORD **)(v1 + 368);
    v4 = *(_QWORD *)(v1 + 376);
    for ( *(_QWORD *)(v1 + 376) = 0; v4; --v4 )
    {
      if ( *v3 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
      v3 += 4;
    }
    v241 = v246 + 360;
    v5 = *(_QWORD *)(v246 + 16);
    if ( v5 )
    {
      v6 = *(_DWORD *)(v246 + 184);
      v7 = *(unsigned __int16 **)(v246 + 8);
      switch ( v6 )
      {
        case 0u:
        case 2u:
          v8 = 464963;
          break;
        case 1u:
        case 3u:
          v14 = v246;
          goto LABEL_25;
        default:
          goto LABEL_261;
      }
      while ( 1 )
      {
        v9 = v5;
        v10 = v7;
        v11 = *v7;
        v12 = *v7++;
        if ( --v5 && (v11 & 0xFC00) == 0xD800 && (*v7 & 0xFC00) == 0xDC00 )
        {
          v12 = ((v11 & 0x3FF) << 10) + (*v7 & 0x3FFu) + 0x10000;
          v10 += 2;
          v7 = v10;
          v5 = v9 - 2;
        }
        BidiClass = GetBidiClass(v12, v10);
        if ( BidiClass <= 0x12u )
        {
          if ( _bittest(&v8, BidiClass) )
            break;
        }
        if ( !v5 )
          goto LABEL_21;
      }
      v14 = v246;
      v7 = *(unsigned __int16 **)(v246 + 8);
      v5 = *(_QWORD *)(v246 + 16);
      v6 = *(_DWORD *)(v246 + 184);
LABEL_25:
      v221[0].m128i_i64[0] = (__int64)v7;
      v221[0].m128i_i64[1] = v5;
      v221[1].m128i_i64[0] = v14 + 392;
      v221[1].m128i_i64[1] = v14 + 296;
      v221[2].m128i_i64[0] = v14 + 760;
      v221[2].m128i_i32[2] = v6;
      if ( v5 )
      {
        if ( v6 >= 4 )
LABEL_261:
          core::panicking::panic(
            "internal error: entered unreachable coderust\\unicode_analysis\\src\\bidi_analysis.rs",
            40,
            &off_1803488D8);
        v18 = 8 * v6;
        v19 = 0x1000100u >> v18;
        v20 = 0x100A100Au >> v18;
        v217[0] = 0;
        v217[1] = (LPVOID)1;
        v218.m128i_i64[0] = 0;
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
          (unsigned int)v217,
          0,
          v5 + 1,
          1,
          4);
        v21 = v217[1];
        v22 = v218.m128i_i64[0];
        memset_0((char *)v217[1] + 4 * v218.m128i_i64[0], 0, 4 * (v5 + 1));
        v23 = v5 + 1 + v22;
        if ( v5 >= v23 )
          core::panicking::panic_bounds_check(v5, v23, &off_180337318);
        v21[4 * v5] = 2;
        v21[4 * v5 + 3] = v19;
        v229.m256i_i64[0] = 0;
        *(_OWORD *)&v229.m256i_u64[1] = 4u;
        lpMem[0] = 0;
        lpMem[1] = (LPVOID)4;
        v224.m128i_i64[0] = 0;
        unicode_analysis::bidi_analysis::determine_types_and_explicit_levels_layout::layout_text_source::LayoutTextSource_(
          v20,
          (unsigned int)v221,
          v5,
          (unsigned int)&v229,
          (__int64)lpMem,
          (__int64)v21,
          v23);
        unicode_analysis::bidi_analysis::resolve_weak_types(v20, v5 + 1, v21, v23);
        v24 = (void *)v229.m256i_i64[1];
        unicode_analysis::bidi_analysis::resolve_parentheses(
          v5,
          v20,
          v229.m256i_i32[2],
          v229.m256i_i32[4],
          (__int64)v21,
          v23);
        unicode_analysis::bidi_analysis::resolve_neutrals_and_implicit_levels_layout::unicode_runs::TextLayoutBidiAnalysisSink_(
          v20,
          v5,
          v241,
          (_DWORD)v21,
          v23);
        if ( lpMem[0] )
        {
          v25 = lpMem[1];
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
        }
        if ( v229.m256i_i64[0] )
        {
          v27 = GetProcessHeap();
          HeapFree(v27, 0, v24);
        }
        if ( v217[0] )
        {
          v28 = GetProcessHeap();
          HeapFree(v28, 0, v21);
        }
      }
      v1 = v246;
    }
    else
    {
LABEL_21:
      v15 = *(_QWORD *)(v246 + 376);
      if ( v15 == *(_QWORD *)(v246 + 360) )
        alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::BidiRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::BidiRun__alloc::alloc::Global_(
          v241,
          &off_180338A80);
      v1 = v246;
      v16 = *(_QWORD *)(v246 + 368);
      v17 = 32 * v15;
      *(_OWORD *)(v16 + v17) = 0;
      *(_QWORD *)(v16 + v17 + 13) = 0;
      *(_DWORD *)(v16 + v17 + 24) = -1;
      *(_QWORD *)(v1 + 376) = v15 + 1;
    }
    v29 = *(_DWORD *)(v1 + 184);
    if ( (v29 & 2) != 0 )
    {
      v30 = *(_QWORD *)(v1 + 16);
      v229.m256i_i64[0] = *(_QWORD *)(v1 + 8);
      v229.m256i_i64[1] = v30;
      v229.m256i_i64[2] = v1 + 392;
      v236 = v1 + 296;
      v229.m256i_i64[3] = v1 + 296;
      v230.m128i_i64[0] = v1 + 760;
      v230.m128i_i32[2] = v29;
      if ( v29 >= 4 )
        unicode_analysis::orientation::analyze_glyph_orientation::panic_cold_explicit(&off_180337300);
      if ( v30 )
      {
        i = *(_DWORD *)(v246 + 192);
        v221[0].m128i_i64[0] = 2;
        *(__m128i *)((char *)v221 + 8) = 0;
        v221[1].m128i_i64[1] = (__int64)&v229;
        v221[2].m128i_i64[0] = 0;
        v221[2].m128i_i64[1] = v30;
        v221[4].m128i_i32[0] = 0;
        v221[3].m128i_i64[0] = 0;
        v221[3].m128i_i64[1] = v30;
        unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(v221);
        v32 = _mm_loadu_si128(&v221[1]);
        *(__m128i *)lpMem = _mm_loadu_si128(v221);
        v224 = v32;
        v225 = v221[2];
        v226 = v221[3];
        v227 = v221[4].m128i_i64[0];
        v33 = -1;
        v34 = 0;
        LOBYTE(v228) = -1;
        v234 = 0;
        v35 = 0;
        v36 = 0;
        v37 = 0;
        v38 = 0;
        v39 = 0;
        v233 = v30;
        LODWORD(v238) = i;
        do
        {
          v240 = (unsigned __int64)v38;
          v243 = v37;
          v242 = v36;
          v245 = v35;
          v40 = layout::run_list::RunList_layout::layout_types::BidiRun_::get_run_at_layout::layout_types::BidiRun_(
                  v241,
                  v34);
          v41 = *(unsigned int *)(v40 + 24);
          v42 = *(_BYTE *)(v40 + 8);
          v43 = v30;
          if ( v41 < v30 )
            v43 = v41;
          if ( v34 == v41 )
            v43 = v30;
          if ( i != v33 || (_BYTE)v228 != v42 )
          {
            v39 = 0;
            LOBYTE(v228) = v42;
          }
          v35 = v245;
          v44 = v245;
          v36 = v242;
          v45 = v242;
          v37 = v243;
          v46 = v243;
          v38 = (_QWORD *)v240;
          LOBYTE(v244) = v240;
          for ( i = v238; v34 < v43; v42 = (char)v235 )
          {
            LOBYTE(v239) = v46;
            LOBYTE(v222) = v45;
            LODWORD(v237) = v44;
            LOBYTE(v235) = v42;
            v47 = v5;
            v48 = (unsigned __int64 *)v34;
            while ( 1 )
            {
              LODWORD(v5) = GetOrientationClass((unsigned int)v227);
              if ( (((_BYTE)v5 == (unsigned __int8)v47) & (unsigned __int8)v39) == 0
                && (((unsigned __int8)v39 & ((unsigned __int8)(v5 - 3) < 3u)) != 1 || (_BYTE)v47 == 2) )
              {
                break;
              }
              v48 = (unsigned __int64 *)((char *)v48
                                       + unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(lpMem));
              if ( (unsigned __int64)v48 >= v43 )
              {
                LODWORD(v5) = v47;
                LOBYTE(v38) = (_BYTE)v244;
                LOBYTE(v37) = v239;
                LOBYTE(v36) = v222;
                v35 = (unsigned int)v237;
                v34 = (unsigned __int64)v48;
                v30 = v233;
                i = v238;
                goto LABEL_40;
              }
            }
            i = v238;
            orientation_info = unicode_analysis::orientation::get_orientation_info(
                                 (unsigned int)v5,
                                 (unsigned int)v238,
                                 (unsigned __int8)v235);
            if ( (_BYTE)v222 != BYTE4(orientation_info)
              || ((BYTE5(orientation_info) ^ (unsigned __int8)v239) & 1) != 0
              || ((BYTE6(orientation_info) ^ (unsigned __int8)v244) & 1) != 0
              || (_DWORD)v237 != (_DWORD)orientation_info )
            {
              v240 = HIWORD(orientation_info);
              v243 = orientation_info >> 40;
              v242 = HIDWORD(orientation_info);
              v245 = orientation_info;
              if ( v48 > v234 )
              {
                layout::orientation::impl_0::set_glyph_orientation(
                  v241,
                  v236,
                  (_DWORD)v234,
                  (_DWORD)v48 - (_DWORD)v234,
                  v237,
                  v222,
                  v239,
                  (char)v244);
                v234 = v48;
              }
            }
            else
            {
              v240 = (unsigned __int8)v244;
              v243 = (unsigned __int8)v239;
              v242 = (unsigned __int8)v222;
              v245 = (unsigned int)v237;
            }
            v34 = (unsigned __int64)v48
                + unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(lpMem);
            v39 = 1;
            v35 = v245;
            v44 = v245;
            v36 = v242;
            v45 = v242;
            v37 = v243;
            v46 = v243;
            v38 = (_QWORD *)v240;
            LOBYTE(v244) = v240;
            v30 = v233;
          }
LABEL_40:
          v33 = i;
        }
        while ( v34 < v30 );
        layout::orientation::impl_0::set_glyph_orientation(
          v241,
          v236,
          (_DWORD)v234,
          v34 - (_DWORD)v234,
          v35,
          v36,
          v37,
          (char)v38);
      }
      v1 = v246;
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 760) + 24LL))(*(_QWORD *)(v1 + 760)) )
    {
      v50 = *(_QWORD *)(v1 + 16);
      v51 = *(_DWORD *)(v1 + 184);
      v209 = *(_QWORD *)(v1 + 8);
      v210 = v50;
      v211 = v1 + 392;
      v212 = v1 + 296;
      v213 = (_QWORD *)(v1 + 760);
      v214 = v51;
      v221[0].m128i_i64[0] = 2;
      *(__m128i *)((char *)v221 + 8) = 0;
      v221[1].m128i_i64[1] = (__int64)&v209;
      v221[2].m128i_i64[0] = 0;
      v221[2].m128i_i64[1] = v50;
      v221[4].m128i_i32[0] = 0;
      v221[3].m128i_i64[0] = 0;
      v221[3].m128i_i64[1] = v50;
      unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(v221);
      v52 = _mm_loadu_si128(&v221[1]);
      *(__m128i *)v229.m256i_i8 = _mm_loadu_si128(v221);
      *(__m128i *)&v229.m256i_u64[2] = v52;
      v230 = v221[2];
      v231 = v221[3];
      v232 = v221[4].m128i_i64[0];
      v221[6].m128i_i16[2] = 1;
      v221[5].m128i_i32[3] = v51;
      v221[6].m128i_i32[0] = v51;
      v221[3].m128i_i64[1] = (v51 & 1) + 1LL;
      v221[4].m128i_i64[0] = 0;
      v221[4].m128i_i32[2] = v51 & 1;
      v221[0].m128i_i32[0] = 0;
      *(__m128i *)((char *)&v221[4] + 12) = 0;
      v219 = 0;
      v218 = 0;
      *(_OWORD *)v217 = 0;
      v220 = 0;
      v53 = v231.m128i_u64[1];
      v54 = v231.m128i_i64[0];
      if ( v231.m128i_i64[0] < (unsigned __int64)v231.m128i_i64[1] )
      {
        v243 = v210;
        v240 = (unsigned __int64)v213;
        LODWORD(v245) = 0;
        LODWORD(v242) = 0;
        v55 = v231.m128i_i64[0];
        do
        {
          v56 = v221[5].m128i_u64[0];
          if ( v55 >= v221[5].m128i_i64[0] )
          {
            v61 = v243 - v55;
            if ( v243 <= v55 )
              core::panicking::panic(
                "assertion failed: text_position < self.text.len()rust\\layout\\src\\line_breaking.rs",
                49,
                &off_1803384F8);
            v62 = *(_QWORD *)v240;
            v63 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v240 + 24LL))(*(_QWORD *)v240);
            v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 32LL))(v62);
            v65 = *(__m128i *)(v64 + 16);
            v66 = *(__m128i *)(v64 + 32);
            *(_OWORD *)v217 = *(_OWORD *)v64;
            v218 = v65;
            v219 = v66;
            v220 = *(_DWORD *)(v64 + 48);
            v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v62 + 40LL))(v62);
            v221[5].m128i_i32[2] = v63;
            v68 = _mm_load_si128(&v218);
            *(__m128i *)((char *)v221 + 4) = _mm_load_si128((const __m128i *)v217);
            *(__m128i *)((char *)&v221[1] + 4) = v68;
            *(__m128i *)((char *)&v221[2] + 4) = v219;
            v221[3].m128i_i32[1] = v220;
            v221[0].m128i_i32[0] = 1;
            v56 = v54 + v61;
            if ( v53 < v56 )
              v56 = v53;
            LODWORD(v242) = v67;
            v221[6].m128i_i8[5] = v67;
            v221[5].m128i_i64[0] = v56;
            v55 = v54;
            LODWORD(v245) = v63;
            v57 = v63;
            if ( !v63 )
            {
LABEL_84:
              if ( v56 < v53 )
              {
                if ( v55 < v56 )
                {
                  do
                  {
                    unicode_analysis::number_substitution::Context::update_script(v221, (unsigned int)v232);
                    unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(&v229);
                    v54 = v231.m128i_i64[0];
                    v55 = v231.m128i_i64[0];
                  }
                  while ( v231.m128i_i64[0] < (unsigned __int64)v221[5].m128i_i64[0] );
                }
                goto LABEL_70;
              }
              v229.m256i_i64[0] = 2;
              *(_OWORD *)&v229.m256i_u64[1] = 0;
              v54 = v230.m128i_u64[1];
              v230.m128i_i64[0] = v230.m128i_i64[1];
              LODWORD(v232) = 0;
              v231.m128i_i64[0] = v230.m128i_i64[1];
              goto LABEL_93;
            }
          }
          else
          {
            v57 = v221[5].m128i_i32[2];
            if ( !v221[5].m128i_i32[2] )
              goto LABEL_84;
          }
          v58 = v232;
          if ( (unsigned int)(v232 - 48) < 0xA )
          {
            v59 = 1;
            if ( v57 == 2 )
            {
              v60 = v221[6].m128i_i8[4];
              if ( v221[6].m128i_i8[4] == 81 )
                v60 = 3;
              if ( v221[6].m128i_i8[5] == 3 )
              {
                if ( v60 == 1 )
                  v59 = v221[6].m128i_i8[0];
                else
                  v59 = v60 == 3;
              }
              else
              {
                v59 = v60 == 1 || v60 == v221[6].m128i_i8[5];
              }
            }
            unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(&v229);
            v54 = v231.m128i_i64[0];
            while ( v54 < v56 )
            {
              v70 = v232;
              if ( (unsigned int)(v232 - 37) > 0x1A )
                break;
              v71 = 2095745;
              if ( !_bittest(&v71, v232 - 37) || (unsigned int)(v232 - 48) >= 0xA && v58 - 48 >= 0xA )
                break;
              if ( (v232 & 0x3D) == 0x2C )
              {
                si128 = _mm_load_si128((const __m128i *)&v229.m256i_u64[2]);
                *(__m128i *)lpMem = _mm_load_si128((const __m128i *)&v229);
                v224 = si128;
                v225 = v230;
                LODWORD(v227) = v232;
                v226.m128i_i64[0] = v54;
                v226.m128i_i64[1] = v231.m128i_i64[1];
                unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(lpMem);
                if ( v226.m128i_i64[0] >= v56 )
                  break;
                v70 = v227;
                if ( (unsigned int)(v227 - 48) >= 0xA )
                  break;
                v69 = _mm_load_si128(&v224);
                *(__m128i *)v229.m256i_i8 = _mm_load_si128((const __m128i *)lpMem);
                *(__m128i *)&v229.m256i_u64[2] = v69;
                v230 = v225;
                v231 = v226;
                LODWORD(v232) = v227;
              }
              unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(&v229);
              v54 = v231.m128i_i64[0];
              v58 = v70;
            }
            if ( (v59 & 1) != 0 )
            {
              v73 = std::sys::alloc::windows::process_heap_alloc(0, 88);
              if ( !v73 )
                alloc::alloc::handle_alloc_error(8, 88);
              *(_QWORD *)v73 = off_180348E60;
              v244 = (_QWORD *)(v73 + 8);
              *(_QWORD *)(v73 + 8) = off_180348E90;
              *(_DWORD *)(v73 + 16) = v245;
              v74 = _mm_load_si128(&v218);
              v75 = v219;
              *(__m128i *)(v73 + 20) = _mm_load_si128((const __m128i *)v217);
              *(__m128i *)(v73 + 36) = v74;
              *(__m128i *)(v73 + 52) = v75;
              *(_DWORD *)(v73 + 68) = v220;
              *(_BYTE *)(v73 + 72) = v242;
              *(_QWORD *)(v73 + 80) = 1;
              v76 = layout::run_list::RunList_layout::layout_types::BidiRun_::select_runs_layout::layout_types::BidiRun_(
                      v241,
                      v55,
                      v54);
              v78 = v77;
              if ( v77 < v76 )
                core::slice::index::slice_index_order_fail(v76, v77, &off_180338AE0);
              v79 = *(_QWORD *)(v246 + 376);
              if ( v78 > v79 )
                core::slice::index::slice_end_index_len_fail(v78, v79, &off_180338AE0);
              v80 = *(_QWORD *)(v246 + 368);
              v81 = 32 * v76;
              v82 = 32 * v78;
              v83 = v244;
              while ( v82 != v81 )
              {
                (*(void (__fastcall **)(_QWORD *))(*v83 + 8LL))(v83);
                v84 = *(_QWORD *)(v80 + v81);
                if ( v84 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                *(_QWORD *)(v80 + v81) = v83;
                v81 += 32;
              }
              (*(void (__fastcall **)(_QWORD *))(*v83 + 16LL))(v83);
            }
            v55 = v54;
            goto LABEL_70;
          }
          if ( v55 < v56 )
          {
            while ( 1 )
            {
              unicode_analysis::number_substitution::Context::update_script(v221, v58);
              unicode_analysis::text_iterator::impl_1::advance_unicode_analysis::text_iterator::char_source::AnalysisCharSource_layout::layout_text_source::LayoutTextSource___(&v229);
              v54 = v231.m128i_i64[0];
              if ( v231.m128i_i64[0] >= v56 )
                break;
              v58 = v232;
              v55 = v231.m128i_i64[0];
              if ( (unsigned int)(v232 - 48) < 0xA )
                goto LABEL_70;
            }
LABEL_93:
            v55 = v54;
          }
LABEL_70:
          v53 = v231.m128i_u64[1];
        }
        while ( v55 < v231.m128i_i64[1] );
      }
      v1 = v246;
    }
    *(_BYTE *)(v1 + 824) |= 8u;
  }
  layout::TextLayout::ensure_script_runs_valid(v1);
  v85 = *(_QWORD *)(v1 + 432);
  v86 = *(_QWORD *)(v1 + 440);
  *(_QWORD *)(v1 + 440) = 0;
  if ( v86 )
  {
    v87 = (_QWORD *)(v85 + 16);
    do
    {
      if ( *v87 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v87 + 16LL))(*v87);
      v87 += 10;
      --v86;
    }
    while ( v86 );
  }
  v88 = v246;
  *(_QWORD *)(v246 + 552) = 0;
  *(_QWORD *)(v88 + 576) = 0;
  *(_QWORD *)(v88 + 600) = 0;
  *(_QWORD *)(v88 + 624) = 0;
  *(_OWORD *)(v88 + 640) = 0;
  v89 = *(_QWORD *)(v88 + 464);
  v90 = *(_QWORD *)(v88 + 472);
  *(_QWORD *)(v88 + 472) = 0;
  if ( v90 )
  {
    v91 = (_QWORD *)(v89 + 16);
    do
    {
      if ( *v91 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v91 + 16LL))(*v91);
      v91 += 10;
      --v90;
    }
    while ( v90 );
  }
  v92 = v246;
  v235 = (_QWORD *)(v246 + 424);
  v244 = (_QWORD *)(v246 + 536);
  v234 = (unsigned __int64 *)(v246 + 640);
  *(_QWORD *)(v246 + 672) = 0;
  v236 = v92 + 296;
  v93 = *(void **)(v92 + 16);
  memset(&v221[2], 0, 93);
  memset(v221, 0, 25);
  v229.m256i_i64[0] = 0;
  v229.m256i_i64[2] = (__int64)&off_1804AF000;
  v228 = v92 + 360;
  v233 = v92 + 392;
  v241 = v92 + 328;
  v216 = v92 + 760;
  v94 = _mm_loadl_epi64((const __m128i *)&_xmm);
  v95 = _mm_load_si128((const __m128i *)&_xmm);
  v96 = _mm_load_si128((const __m128i *)&_xmm);
  v97 = _mm_load_si128((const __m128i *)&_xmm);
  v98 = _mm_load_si128((const __m128i *)&_xmm);
  v99.m128_i32[0] = 0;
  v215 = (unsigned __int64)v93;
  v239 = 0;
  v100 = 0;
  v242 = 0;
  v101 = 0;
  v102 = 0;
LABEL_131:
  if ( v102 < (unsigned __int64)v93 )
  {
    v245 = v102;
    if ( v102 < v242 )
    {
      if ( !v101 )
        core::option::unwrap_failed(&off_180338B88);
      goto LABEL_156;
    }
    v107 = *(_QWORD *)(v246 + 312);
    if ( v100 >= v107 )
      core::panicking::panic_bounds_check(v100, *(_QWORD *)(v246 + 312), &off_180337868);
    v108 = *(_QWORD *)(v246 + 304);
    v101 = v108 + 120 * v100;
    v109 = v100 + 1;
    if ( v100 + 1 >= v107 )
    {
      v112 = v100;
      v113 = v100 + 1;
      if ( v100 >= v107 )
        goto LABEL_267;
      goto LABEL_153;
    }
    v110 = *(_QWORD *)(v101 + 64);
    v111 = v108 + 120 * v100 + 136;
    v112 = v100;
    while ( 1 )
    {
      v113 = v109;
      v114 = *(_QWORD *)(v111 + 48);
      if ( v110 )
      {
        if ( v110 != v114 )
        {
          v112 = v113 - 1;
LABEL_152:
          if ( v112 >= v107 )
LABEL_267:
            core::panicking::panic_bounds_check(v112, *(_QWORD *)(v246 + 312), &off_1803374B8);
LABEL_153:
          v115 = *(unsigned int *)(v108 + 120 * v112 + 112);
          if ( v215 < v115 )
            v115 = v215;
          v242 = v115;
          v239 = v100;
          v100 = v113;
LABEL_156:
          v243 = v101;
          v240 = v100;
          if ( *(_QWORD *)(v101 + 64) )
          {
            v116 = layout::run_list::RunList_layout::layout_types::BidiRun_::get_run_at_layout::layout_types::BidiRun_(
                     v228,
                     v102);
            if ( v242 > *(_QWORD *)(v246 + 16) || (v117 = v242 - v245, v242 <= v245) )
              core::panicking::panic(
                "assertion failed: text_range.end <= ro.text.len() && text_range.start < text_range.endC++ code failed to"
                " create last resort font reference.rust\\layout\\src\\text_layout_factory.rs",
                86,
                &off_180338BA0);
            v118 = *(_QWORD *)(v243 + 64);
            if ( !v118 )
              core::option::unwrap_failed(&off_180338BB8);
            v237 = *(_QWORD *)(v246 + 496);
            v119 = *(_QWORD *)(v246 + 504);
            LOBYTE(v100) = *(_BYTE *)(v116 + 20);
            inline_object_metrics = (float *)layout::recent_metrics::RecentInlineObjectMetrics::get_inline_object_metrics(
                                               v221,
                                               v118,
                                               (unsigned int)v100);
            layout::TextLayoutGlyphs::ensure_free_glyph_capacity(v244, 1);
            v121 = *v234;
            v122 = *v234 + 1;
            layout::TextLayoutGlyphs::resize_arrays_only(v244, v122);
            v238 = v116;
            v123 = v246;
            *(_QWORD *)(v246 + 640) = v122;
            v124 = *(_QWORD *)(v123 + 552);
            if ( v121 >= v124 )
              core::panicking::panic_bounds_check(v121, v124, &off_180338BD0);
            *(_QWORD *)(*(_QWORD *)(v123 + 544) + 8 * v121) = 0;
            v125 = *(_QWORD *)(v123 + 576);
            if ( v121 >= v125 )
              core::panicking::panic_bounds_check(v121, v125, &off_180338BE8);
            *(float *)(*(_QWORD *)(v123 + 568) + 4 * v121) = *inline_object_metrics;
            v126 = *(_QWORD *)(v123 + 600);
            if ( v121 >= v126 )
              core::panicking::panic_bounds_check(v121, v126, &off_180338C00);
            *(_WORD *)(*(_QWORD *)(v123 + 592) + 2 * v121) = 0;
            v127 = *(_QWORD *)(v123 + 624);
            if ( v121 >= v127 )
              core::panicking::panic_bounds_check(v121, v127, &off_180338C18);
            *(_WORD *)(*(_QWORD *)(v123 + 616) + 2 * v121) = ((_mm_cvtsi128_si32((__m128i)_mm_cmpeq_ss(
                                                                                            (__m128)*(unsigned int *)inline_object_metrics,
                                                                                            v99))
                                                             & 1) << 6)
                                                           | 0x10;
            if ( v242 > v119 )
              core::slice::index::slice_end_index_len_fail(v242, v119, &off_180338C30);
            v222 = v122;
            v128 = (__m128i *)(v238 + 8);
            v129 = v245;
            memset_0((void *)(v237 + 2 * v245), 0, 2 * v117);
            v130 = *(void (**)(void))(**(_QWORD **)(v243 + 64) + 8LL);
            v237 = *(_QWORD *)(v243 + 64);
            v130();
            v131 = inline_object_metrics[1];
            v132 = inline_object_metrics[2];
            v208 = *v128;
            v133 = *inline_object_metrics;
            v134 = (unsigned __int8)v100 + 1;
            v135 = *(_DWORD *)(v123 + 184);
            v136 = ((v135 & 2 | 0x200000000uLL) - 1) >> 32;
            v137 = 0.0;
            if ( v134 != v136 )
            {
              v247 = 1;
              v151 = layout::run_list::RunList_layout::font_runs::FontRun_::get_run_at_layout::font_runs::FontRun_(
                       v233,
                       v129);
              v247 = 1;
              v152 = (__int16 *)layout::run_list::RunList_layout::layout_types::ScriptRun_::get_run_at_layout::layout_types::ScriptRun_(
                                  v241,
                                  v129);
              v154 = *(_QWORD *)(v151 + 8);
              if ( !v154 )
              {
                v247 = 1;
                core::option::unwrap_failed(&off_180338C48);
              }
              v155 = v243 + 16;
              v156 = *v152;
              v157 = (v135 >> 1) & 1;
              LODWORD(lpMem[0]) = 0;
              LOWORD(v206) = v156;
              LOBYTE(v153) = 1;
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, unsigned __int64, LPVOID *))(*(_QWORD *)v154 + 576LL))(
                v154,
                v134,
                v157,
                v153,
                v206,
                v243 + 16,
                lpMem);
              v158 = (int)lpMem[0];
              v159 = *(_QWORD *)(v151 + 8);
              LODWORD(lpMem[0]) = 0;
              LOWORD(v207) = v156;
              LOBYTE(v160) = 1;
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, unsigned __int64, LPVOID *))(*(_QWORD *)v159 + 576LL))(
                v159,
                v136,
                v157,
                v160,
                v207,
                v155,
                lpMem);
              v161 = v158 - LODWORD(lpMem[0]);
              v162 = -v161;
              if ( !v157 )
                v162 = v161;
              if ( v162 )
              {
                v163 = *(_DWORD *)(v238 + 8);
                v164 = *(_DWORD *)(v238 + 12);
                v165 = *(_QWORD *)v151;
                v247 = 1;
                font_metrics = (unsigned __int16 *)layout::recent_metrics::RecentFontMetrics::get_font_metrics(
                                                     &v221[2],
                                                     v246,
                                                     v165);
                v167 = -v162;
                if ( (((unsigned __int8)v164 ^ (unsigned __int8)v163) & 1) == 0 )
                  v167 = v162;
                v137 = (float)((float)v167 * *(float *)(v151 + 16)) / (float)*font_metrics;
              }
            }
            v168 = *(_QWORD *)(v246 + 440);
            if ( v168 == *(_QWORD *)(v246 + 424) )
              alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_(
                v235,
                &off_180338A80);
            v103 = v246;
            v104 = *(_QWORD *)(v246 + 432);
            v105 = 80 * v168;
            *(_QWORD *)(v104 + v105) = v121;
            *(_QWORD *)(v104 + v105 + 8) = v222;
            *(_QWORD *)(v104 + v105 + 16) = v237;
            *(float *)(v104 + v105 + 24) = v132;
            *(float *)(v104 + v105 + 28) = v131 - v132;
            *(float *)(v104 + v105 + 32) = v137;
            *(float *)(v104 + v105 + 36) = v133;
            *(_QWORD *)(v104 + v105 + 40) = 0;
            *(__m128i *)(v104 + v105 + 48) = _mm_load_si128(&v208);
            *(_DWORD *)(v104 + v105 + 64) = 0;
            *(_DWORD *)(v104 + v105 + 67) = 0;
            v106 = v242;
            *(_DWORD *)(v104 + v105 + 72) = v242;
            *(_QWORD *)(v103 + 440) = v168 + 1;
            *(_BYTE *)(v103 + 824) |= 0x20u;
            goto LABEL_129;
          }
          v106 = v242;
          if ( v242 - v102 > 0x3E80 )
          {
            v138 = v246;
            if ( (*(_BYTE *)(v246 + 824) & 0x41) == 0 )
            {
              v139 = *(_DWORD *)(v246 + 184);
              lpMem[0] = *(LPVOID *)(v246 + 8);
              lpMem[1] = v93;
              v224.m128i_i64[0] = v233;
              v224.m128i_i64[1] = v236;
              v225.m128i_i64[0] = v216;
              v225.m128i_i32[2] = v139;
              unicode_analysis::line_break_analysis::analyze_line_breaks_layout::layout_text_source::LayoutTextSource_layout::unicode_runs::TextLayoutLineBreakAnalysisSink_(
                lpMem,
                v93,
                *(_QWORD *)(v246 + 280),
                *(_QWORD *)(v246 + 288));
              v138 = v246;
              *(_BYTE *)(v246 + 824) |= 1u;
              v102 = v245;
            }
            v106 = v102 + 16000;
            v140 = *(_QWORD *)(v138 + 288);
            v141 = v102 + 15998;
            while ( v102 < v141 + 2 )
            {
              if ( v141 >= v140 )
                core::panicking::panic_bounds_check(v141, v140, &off_180339528);
              v142 = ((*(_BYTE *)(*(_QWORD *)(v138 + 280) + v141--) >> 2) & 3) - 1;
              if ( (v142 & 0xFD) == 0 )
              {
                v106 = v141 + 2;
                break;
              }
            }
          }
          v143 = layout::run_list::RunList_layout::layout_types::BidiRun_::get_run_at_layout::layout_types::BidiRun_(
                   v228,
                   v102);
          v144 = *(unsigned int *)(v143 + 24);
          v145 = layout::run_list::RunList_layout::font_runs::FontRun_::get_run_at_layout::font_runs::FontRun_(
                   v233,
                   v245);
          v146 = v145;
          if ( v144 < v106 )
            v106 = v144;
          v147 = *(unsigned int *)(v145 + 24);
          if ( v147 < v106 )
            v106 = v147;
          v148 = v240 - v239;
          if ( v240 < v239 )
            core::slice::index::slice_index_order_fail(v239, v240, &off_180337850);
          v149 = *(_QWORD *)(v246 + 312);
          if ( v240 > v149 )
            core::slice::index::slice_end_index_len_fail(v240, v149, &off_180337850);
          v150 = *(_QWORD *)(v246 + 304) + 120 * v239;
          if ( (unsigned __int8)layout::shaping::try_shape_fast(
                                  v246,
                                  *(_QWORD *)(v246 + 496),
                                  *(_QWORD *)(v246 + 504),
                                  (_DWORD)v244,
                                  v241,
                                  v236,
                                  (__int64)v235,
                                  (__int64)v221,
                                  v245,
                                  v106,
                                  v150,
                                  v240 - v239,
                                  v143,
                                  v146) )
          {
LABEL_182:
            v103 = v246;
            goto LABEL_129;
          }
          v169 = layout::run_list::RunList_layout::layout_types::ScriptRun_::get_run_at_layout::layout_types::ScriptRun_(
                   v241,
                   v245);
          if ( *(unsigned int *)(v169 + 8) < v106 )
            v106 = *(unsigned int *)(v169 + 8);
          v170 = *(_DWORD *)(v169 + 4);
          v171 = *(_QWORD *)(v246 + 504);
          if ( (v170 & 1) != 0 )
          {
            if ( v106 > *(_QWORD *)(v246 + 16) || (v178 = v106 - v245, v106 <= v245) )
              core::panicking::panic(
                "assertion failed: text_range.end <= ro.text.len() && text_range.start < text_range.endC++ code failed to"
                " create last resort font reference.rust\\layout\\src\\text_layout_factory.rs",
                86,
                &off_180338D98);
            v179 = *(_QWORD *)(v246 + 496);
            layout::TextLayoutGlyphs::ensure_free_glyph_capacity(v244, v106 - v245);
            if ( v171 < v245 )
              core::slice::index::slice_start_index_len_fail(v245, v171, &off_180338E28);
            if ( v106 > v171 )
              core::slice::index::slice_end_index_len_fail(v178, v171 - v245, &off_180338DB0);
            v180 = v179 + 2 * v245;
            if ( v178 <= 3 )
            {
              v181 = 0;
              goto LABEL_219;
            }
            if ( v178 >= 0x10 )
            {
              v181 = (unsigned int)v178 & 0xFFFFFFF0;
              v182 = v179 + 2 * v245 + 16;
              v183 = 0;
              v184 = v96;
              do
              {
                *(__m128i *)(v182 + 2 * v183 - 16) = v184;
                *(__m128i *)(v182 + 2 * v183) = _mm_add_epi16(v184, v97);
                v183 += 16;
                v184 = _mm_add_epi16(v184, v98);
              }
              while ( v181 != v183 );
              if ( v178 != v181 )
              {
                if ( (v178 & 0xC) == 0 )
                  goto LABEL_219;
                goto LABEL_216;
              }
            }
            else
            {
              v181 = 0;
LABEL_216:
              v185 = v181;
              v181 = (unsigned int)v178 & 0xFFFFFFFC;
              v186 = _mm_or_si128(_mm_shufflelo_epi16(_mm_cvtsi32_si128(v185), 0), v94);
              do
              {
                *(_QWORD *)(v180 + 2 * v185) = v186.m128i_i64[0];
                v185 += 4;
                v186 = _mm_add_epi16(v186, v95);
              }
              while ( v181 != v185 );
              for ( ; v178 != v181; ++v181 )
LABEL_219:
                *(_WORD *)(v180 + 2 * v181) = v181;
            }
            v238 = *v234;
            v187 = v238 + v178;
            layout::TextLayoutGlyphs::resize_arrays_only(v244, v238 + v178);
            v188 = v143;
            v189 = (_QWORD *)v246;
            *(_QWORD *)(v246 + 640) = v187;
            v190 = v238;
            if ( v187 < v238 )
              core::slice::index::slice_index_order_fail(v238, v187, &off_180338DC8);
            v191 = v189[69];
            if ( v187 > v191 )
              core::slice::index::slice_end_index_len_fail(v187, v191, &off_180338DC8);
            memset_0((void *)(v189[68] + 8 * v238), 0, 8 * v178);
            v192 = v189[72];
            if ( v187 > v192 )
              core::slice::index::slice_end_index_len_fail(v187, v192, &off_180338DE0);
            memset_0((void *)(v189[71] + 4 * v190), 0, 4 * v178);
            v193 = v189[75];
            if ( v187 > v193 )
              core::slice::index::slice_end_index_len_fail(v187, v193, &off_180338DF8);
            v194 = 2 * v190;
            v195 = 2 * v178;
            memset_0((void *)(v194 + v189[74]), 0, v195);
            v196 = v189[78];
            if ( v187 > v196 )
              core::slice::index::slice_end_index_len_fail(v187, v196, &off_180338E10);
            memset_0((void *)(v189[77] + v194), 0, v195);
            line_spacing_metrics = layout::recent_metrics::RecentFontMetrics::get_line_spacing_metrics(
                                     (unsigned int)&v221[2],
                                     (_DWORD)v189,
                                     v241,
                                     v236,
                                     v245,
                                     v146,
                                     v188);
            LODWORD(lpMem[1]) = *(_DWORD *)(line_spacing_metrics + 8);
            lpMem[0] = *(LPVOID *)line_spacing_metrics;
            v198 = *(_QWORD *)(v246 + 440);
            if ( v198 == *(_QWORD *)(v246 + 424) )
              alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_(
                v235,
                &off_180338A80);
            v103 = v246;
            v199 = *(_QWORD *)(v246 + 432);
            v200 = 80 * v198;
            *(_QWORD *)(v199 + v200) = v238;
            *(_QWORD *)(v199 + v200 + 8) = v187;
            *(_QWORD *)(v199 + v200 + 16) = 0;
            *(LPVOID *)(v199 + v200 + 24) = lpMem[0];
            *(_DWORD *)(v199 + v200 + 32) = lpMem[1];
            *(_QWORD *)(v199 + v200 + 36) = 0;
            *(_DWORD *)(v199 + v200 + 44) = 0;
            *(__m128i *)(v199 + v200 + 48) = _mm_loadu_si128((const __m128i *)(v188 + 8));
            *(_WORD *)(v199 + v200 + 64) = 256;
            *(_DWORD *)(v199 + v200 + 66) = 0;
            *(_BYTE *)(v199 + v200 + 70) = 0;
            *(_DWORD *)(v199 + v200 + 72) = v106;
            *(_QWORD *)(v103 + 440) = v198 + 1;
LABEL_129:
            v101 = v243;
            goto LABEL_130;
          }
          v172 = _mm_loadu_si128((const __m128i *)(v246 + 520));
          layout::shaping::shape_slow(
            v246,
            v244,
            *(_QWORD *)(v246 + 496),
            v171,
            v172.m128i_i64[0],
            v172.m128i_u64[1],
            (__int64)v221,
            v245,
            v106,
            v235,
            v236,
            v150,
            v148,
            v241,
            v143,
            v146,
            *(_WORD *)v169,
            v170,
            (__int64)&v229);
          v173 = (_QWORD *)v229.m256i_i64[2];
          if ( v174 )
          {
            bumpalo::impl_6::drop(v229.m256i_i64[2]);
            if ( v221[6].m128i_i64[0] )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v221[6].m128i_i64[0] + 16LL))(v221[6].m128i_i64[0]);
            v205 = v221[0].m128i_i64[0];
            if ( !v221[0].m128i_i64[0] )
              return;
LABEL_236:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v205 + 16LL))(v205);
            return;
          }
          if ( (_UNKNOWN **)v229.m256i_i64[2] == &off_1804AF000 )
            goto LABEL_182;
          v175 = *(_QWORD *)(v229.m256i_i64[2] + 24);
          *(_QWORD *)(v229.m256i_i64[2] + 24) = &off_1804AF000;
          v101 = v243;
          while ( (_UNKNOWN **)v175 != &off_1804AF000 )
          {
            v177 = *(_QWORD **)v175;
            if ( *(_QWORD *)(v175 + 8) >= 0x11u )
              v177 = (_QWORD *)*(v177 - 1);
            v175 = *(_QWORD *)(v175 + 24);
            v176 = GetProcessHeap();
            HeapFree(v176, 0, v177);
          }
          v173[4] = v173;
          v173[5] = v173[2];
          v103 = v246;
LABEL_130:
          v93 = *(void **)(v103 + 16);
          v102 = v106;
          v100 = v240;
          goto LABEL_131;
        }
      }
      else
      {
        if ( v114 )
          goto LABEL_152;
        if ( *(_BYTE *)(v101 + 111) != *(_BYTE *)(v111 + 95) )
        {
          v102 = v245;
          if ( v112 >= v107 )
            goto LABEL_267;
          goto LABEL_153;
        }
        v102 = v245;
        if ( *(_QWORD *)(v101 + 16) != *(_QWORD *)v111
          || *(_DWORD *)(v101 + 24) != *(_DWORD *)(v111 + 8)
          || *(_DWORD *)(v101 + 28) != *(_DWORD *)(v111 + 12) )
        {
          goto LABEL_152;
        }
      }
      v109 = v113 + 1;
      v111 += 120;
      v112 = v113;
      if ( v107 == v113 + 1 )
      {
        v112 = v107 - 1;
        v113 = *(_QWORD *)(v246 + 312);
        if ( v107 - 1 >= v107 )
          goto LABEL_267;
        goto LABEL_153;
      }
    }
  }
  v201 = v246;
  *(_QWORD *)(v246 + 648) = *(_QWORD *)(v246 + 640);
  *(_BYTE *)(v201 + 824) |= 0x10u;
  v202 = v229.m256i_i64[2];
  while ( (_UNKNOWN **)v202 != &off_1804AF000 )
  {
    v204 = *(_QWORD **)v202;
    if ( *(_QWORD *)(v202 + 8) >= 0x11u )
      v204 = (_QWORD *)*(v204 - 1);
    v202 = *(_QWORD *)(v202 + 24);
    v203 = GetProcessHeap();
    HeapFree(v203, 0, v204);
  }
  if ( v221[6].m128i_i64[0] )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v221[6].m128i_i64[0] + 16LL))(v221[6].m128i_i64[0]);
  v205 = v221[0].m128i_i64[0];
  if ( v221[0].m128i_i64[0] )
    goto LABEL_236;
}

```

## disassembly

```asm
0x18004a5f0  push    rbp
0x18004a5f1  push    r15
0x18004a5f3  push    r14
0x18004a5f5  push    r13
0x18004a5f7  push    r12
0x18004a5f9  push    rsi
0x18004a5fa  push    rdi
0x18004a5fb  push    rbx
0x18004a5fc  sub     rsp, 388h
0x18004a603  lea     rbp, [rsp+80h]
0x18004a60b  movaps  [rbp+340h+var_50], xmm15
0x18004a613  movaps  [rbp+340h+var_60], xmm14
0x18004a61b  movaps  [rbp+340h+var_70], xmm13
0x18004a623  movaps  [rbp+340h+var_80], xmm12
0x18004a62b  movaps  [rbp+340h+var_90], xmm11
0x18004a633  movdqa  [rbp+340h+var_A0], xmm10
0x18004a63c  movdqa  [rbp+340h+var_B0], xmm9
0x18004a645  movdqa  [rbp+340h+var_C0], xmm8
0x18004a64e  movdqa  [rbp+340h+var_D0], xmm7
0x18004a656  movdqa  [rbp+340h+var_E0], xmm6
0x18004a65e  mov     [rbp+340h+var_E8], 0FFFFFFFFFFFFFFFEh
0x18004a669  test    byte ptr [rcx+338h], 10h
0x18004a670  jnz     short loc_18004A692
0x18004a672  mov     rbx, rcx
0x18004a675  movzx   eax, byte ptr [rcx+0B8h]
0x18004a67c  xor     al, [rcx+0BCh]
0x18004a682  test    al, 2
0x18004a684  jz      short loc_18004A699
0x18004a686  mov     edx, 8898500Bh
0x18004a68b  xor     eax, eax
0x18004a68d  jmp     loc_18004C3C8
0x18004a692  xor     edx, edx
0x18004a694  jmp     loc_18004C3C8
0x18004a699  mov     rcx, rbx
0x18004a69c  call    layout__TextLayout__ensure_font_runs_valid
0x18004a6a1  test    byte ptr [rbx+338h], 8
0x18004a6a8  mov     [rbp+340h+var_F8], rbx
0x18004a6af  jnz     loc_18004B528
0x18004a6b5  mov     rsi, [rbx+170h]
0x18004a6bc  mov     rdi, [rbx+178h]
0x18004a6c3  mov     qword ptr [rbx+178h], 0
0x18004a6ce  test    rdi, rdi
0x18004a6d1  jnz     short loc_18004A739
0x18004a6d3  mov     rax, [rbp+340h+var_F8]
0x18004a6da  lea     rcx, [rax+168h]
0x18004a6e1  mov     [rbp+340h+var_120], rcx
0x18004a6e8  mov     rdi, [rax+10h]
0x18004a6ec  test    rdi, rdi
0x18004a6ef  jz      loc_18004A7F9
0x18004a6f5  mov     rax, [rbp+340h+var_F8]
0x18004a6fc  mov     ecx, [rax+0B8h]
0x18004a702  cmp     rcx, 3; switch 4 cases
0x18004a706  ja      def_18004A71E; jumptable 000000018004A71E default case
0x18004a70c  mov     rsi, [rax+8]
0x18004a710  lea     rax, jpt_18004A71E
0x18004a717  movsxd  rdx, ds:(jpt_18004A71E - 1804064ACh)[rax+rcx*4]
0x18004a71b  add     rdx, rax
0x18004a71e  jmp     rdx; switch jump
0x18004a720  mov     ebx, 71843h; jumptable 000000018004A71E cases 0,2
0x18004a725  jmp     short loc_18004A759
0x18004a730  add     rsi, 20h ; ' '
0x18004a734  dec     rdi
0x18004a737  jz      short loc_18004A6D3
0x18004a739  mov     rcx, [rsi]
0x18004a73c  test    rcx, rcx
0x18004a73f  jz      short loc_18004A730
0x18004a741  mov     rax, [rcx]
0x18004a744  mov     rax, [rax+10h]
0x18004a748  call    cs:__guard_dispatch_icall_fptr
0x18004a74e  jmp     short loc_18004A730
0x18004a750  test    rdi, rdi
0x18004a753  jz      loc_18004A7F9
0x18004a759  mov     rax, rdi
0x18004a75c  mov     rdx, rsi
0x18004a75f  movzx   r8d, word ptr [rsi]
0x18004a763  movzx   ecx, r8w
0x18004a767  add     rsi, 2
0x18004a76b  dec     rdi
0x18004a76e  jz      short loc_18004A7C8
0x18004a770  mov     r9d, r8d
0x18004a773  and     r9d, 0FC00h
0x18004a77a  movzx   r9d, r9w
0x18004a77e  cmp     r9d, 0D800h
0x18004a785  jnz     short loc_18004A7C8
0x18004a787  movzx   r9d, word ptr [rsi]
0x18004a78b  mov     r10d, r9d
0x18004a78e  and     r10d, 0FC00h
0x18004a795  cmp     r10d, 0DC00h
0x18004a79c  jnz     short loc_18004A7C8
0x18004a79e  and     r8d, 3FFh
0x18004a7a5  shl     r8d, 0Ah
0x18004a7a9  and     r9d, 3FFh
0x18004a7b0  lea     ecx, [r8+r9]
0x18004a7b4  add     ecx, 10000h
0x18004a7ba  add     rax, 0FFFFFFFFFFFFFFFEh
0x18004a7be  add     rdx, 4
0x18004a7c2  mov     rsi, rdx
0x18004a7c5  mov     rdi, rax
0x18004a7c8  call    GetBidiClass
0x18004a7cd  cmp     al, 12h
0x18004a7cf  ja      loc_18004A750
0x18004a7d5  movzx   eax, al
0x18004a7d8  bt      ebx, eax
0x18004a7db  jnb     loc_18004A750
0x18004a7e1  mov     r8, [rbp+340h+var_F8]
0x18004a7e8  mov     rsi, [r8+8]
0x18004a7ec  mov     rdi, [r8+10h]
0x18004a7f0  mov     ecx, [r8+0B8h]
0x18004a7f7  jmp     short loc_18004A868
0x18004a7f9  mov     rax, [rbp+340h+var_F8]
0x18004a800  mov     rsi, [rax+178h]
0x18004a807  cmp     rsi, [rax+168h]
0x18004a80e  jnz     short loc_18004A823
0x18004a810  lea     rdx, off_180338A80; "rust\\layout\\src\\run_list.rs"
0x18004a817  mov     rcx, [rbp+340h+var_120]
0x18004a81e  call    alloc__raw_vec__RawVec_layout__run_list__Run_layout__layout_types__BidiRun__alloc__alloc__Global___grow_one_layout__run_list__Run_layout__layout_types__BidiRun__alloc__alloc__Global_
0x18004a823  mov     rbx, [rbp+340h+var_F8]
0x18004a82a  mov     rax, [rbx+170h]
0x18004a831  mov     rcx, rsi
0x18004a834  shl     rcx, 5
0x18004a838  pxor    xmm0, xmm0
0x18004a83c  movdqu  xmmword ptr [rax+rcx], xmm0
0x18004a841  mov     qword ptr [rax+rcx+0Dh], 0
0x18004a84a  mov     dword ptr [rax+rcx+18h], 0FFFFFFFFh
0x18004a852  inc     rsi
0x18004a855  mov     [rbx+178h], rsi
0x18004a85c  jmp     loc_18004AA63
0x18004a861  mov     r8, [rbp+340h+var_F8]; jumptable 000000018004A71E cases 1,3
0x18004a868  lea     rax, [r8+188h]
0x18004a86f  lea     rdx, [r8+128h]
0x18004a876  add     r8, 2F8h
0x18004a87d  mov     qword ptr [rbp+340h+var_290], rsi
0x18004a884  mov     qword ptr [rbp+340h+var_290+8], rdi
0x18004a88b  mov     [rbp+0C0h], rax
0x18004a892  mov     [rbp+340h+var_278], rdx
0x18004a899  mov     qword ptr [rbp+340h+var_270], r8
0x18004a8a0  mov     dword ptr [rbp+340h+var_270+8], ecx
0x18004a8a6  test    rdi, rdi
0x18004a8a9  jz      loc_18004AA5C
0x18004a8af  cmp     ecx, 4
0x18004a8b2  jnb     def_18004A71E; jumptable 000000018004A71E default case
0x18004a8b8  shl     ecx, 3
0x18004a8bb  mov     r12d, 1000100h
0x18004a8c1  shr     r12d, cl
0x18004a8c4  mov     r14d, 100A100Ah
0x18004a8ca  shr     r14d, cl
0x18004a8cd  mov     [rbp+340h+var_2D0], 0
0x18004a8d5  mov     [rbp+340h+var_2D0+8], 1
0x18004a8dd  mov     qword ptr [rbp+340h+var_2C0], 0
0x18004a8e8  lea     r15, [rdi+1]
0x18004a8ec  mov     qword ptr [rsp+3C0h+var_3A0], 4
0x18004a8f5  lea     rcx, [rbp+340h+var_2D0]
0x18004a8f9  mov     r9d, 1
0x18004a8ff  xor     edx, edx
0x18004a901  mov     r8, r15
0x18004a904  call    alloc__raw_vec__impl$4__reserve__do_reserve_and_handle_alloc__alloc__Global__5
0x18004a909  mov     rbx, [rbp+340h+var_2D0+8]
0x18004a90d  mov     rsi, qword ptr [rbp+340h+var_2C0]
0x18004a914  lea     rcx, [rbx+rsi*4]; void *
0x18004a918  lea     r8, ds:0[r15*4]; Size
0x18004a920  xor     edx, edx; Val
0x18004a922  call    memset_0
0x18004a927  add     rsi, r15
0x18004a92a  cmp     rdi, rsi
0x18004a92d  jnb     loc_18004C6AF
0x18004a933  mov     byte ptr [rbx+rdi*4], 2
0x18004a937  mov     [rbx+rdi*4+3], r12b
0x18004a93c  mov     [rbp+340h+var_1B0], 0
0x18004a947  mov     [rbp+340h+var_1B0+8], 4
0x18004a952  mov     qword ptr [rbp+340h+var_1A0], 0
0x18004a95d  mov     [rbp+340h+lpMem], 0
0x18004a968  mov     [rbp+340h+lpMem+8], 4
0x18004a973  mov     qword ptr [rbp+340h+var_1F0], 0
0x18004a97e  mov     [rsp+3C0h+var_390], rsi
0x18004a983  mov     qword ptr [rsp+3C0h+var_3A0+8], rbx
0x18004a988  lea     rax, [rbp+340h+lpMem]
0x18004a98f  mov     qword ptr [rsp+3C0h+var_3A0], rax
0x18004a994  lea     rdx, [rbp+340h+var_290]
0x18004a99b  lea     r9, [rbp+340h+var_1B0]
0x18004a9a2  mov     ecx, r14d
0x18004a9a5  mov     r8, rdi
0x18004a9a8  call    unicode_analysis__bidi_analysis__determine_types_and_explicit_levels_layout__layout_text_source__LayoutTextSource_
0x18004a9ad  mov     ecx, r14d
0x18004a9b0  mov     rdx, r15
0x18004a9b3  mov     r8, rbx
0x18004a9b6  mov     r9, rsi
0x18004a9b9  call    unicode_analysis__bidi_analysis__resolve_weak_types
0x18004a9be  mov     r15, [rbp+340h+var_1B0+8]
0x18004a9c5  mov     r9, qword ptr [rbp+340h+var_1A0]
0x18004a9cc  mov     qword ptr [rsp+3C0h+var_3A0+8], rsi
0x18004a9d1  mov     qword ptr [rsp+3C0h+var_3A0], rbx
0x18004a9d6  mov     rcx, rdi
0x18004a9d9  mov     edx, r14d
0x18004a9dc  mov     r8, r15
0x18004a9df  call    unicode_analysis__bidi_analysis__resolve_parentheses
0x18004a9e4  mov     qword ptr [rsp+3C0h+var_3A0], rsi
0x18004a9e9  mov     ecx, r14d
0x18004a9ec  mov     rdx, rdi
0x18004a9ef  mov     r8, [rbp+340h+var_120]
0x18004a9f6  mov     r9, rbx
0x18004a9f9  call    unicode_analysis__bidi_analysis__resolve_neutrals_and_implicit_levels_layout__unicode_runs__TextLayoutBidiAnalysisSink_
0x18004a9fe  cmp     [rbp+340h+lpMem], 0
0x18004aa06  jz      short loc_18004AA23
0x18004aa08  mov     rsi, [rbp+340h+lpMem+8]
0x18004aa0f  call    cs:__imp_GetProcessHeap
0x18004aa15  mov     rcx, rax; hHeap
0x18004aa18  xor     edx, edx; dwFlags
0x18004aa1a  mov     r8, rsi; lpMem
0x18004aa1d  call    cs:__imp_HeapFree
0x18004aa23  cmp     [rbp+340h+var_1B0], 0
0x18004aa2b  jz      short loc_18004AA41
0x18004aa2d  call    cs:__imp_GetProcessHeap
0x18004aa33  mov     rcx, rax; hHeap
0x18004aa36  xor     edx, edx; dwFlags
0x18004aa38  mov     r8, r15; lpMem
0x18004aa3b  call    cs:__imp_HeapFree
0x18004aa41  cmp     [rbp+340h+var_2D0], 0
0x18004aa46  jz      short loc_18004AA5C
0x18004aa48  call    cs:__imp_GetProcessHeap
0x18004aa4e  mov     rcx, rax; hHeap
0x18004aa51  xor     edx, edx; dwFlags
0x18004aa53  mov     r8, rbx; lpMem
0x18004aa56  call    cs:__imp_HeapFree
0x18004aa5c  mov     rbx, [rbp+340h+var_F8]
0x18004aa63  mov     eax, [rbx+0B8h]
0x18004aa69  test    al, 2
0x18004aa6b  jz      loc_18004AE8B
0x18004aa71  mov     rcx, [rbx+8]
0x18004aa75  mov     r15, [rbx+10h]
0x18004aa79  lea     rdx, [rbx+188h]
0x18004aa80  lea     r9, [rbx+128h]
0x18004aa87  lea     r8, [rbx+2F8h]
0x18004aa8e  mov     [rbp+340h+var_1B0], rcx
0x18004aa95  mov     [rbp+340h+var_1B0+8], r15
0x18004aa9c  mov     qword ptr [rbp+340h+var_1A0], rdx
0x18004aaa3  mov     [rbp+340h+var_148], r9
0x18004aaaa  mov     qword ptr [rbp+340h+var_1A0+8], r9
0x18004aab1  mov     qword ptr [rbp+340h+var_190], r8
0x18004aab8  mov     dword ptr [rbp+340h+var_190+8], eax
0x18004aabe  cmp     eax, 4
0x18004aac1  jnb     loc_18004C63A
0x18004aac7  test    r15, r15
0x18004aaca  jz      loc_18004AE84
0x18004aad0  mov     rax, [rbp+340h+var_F8]
0x18004aad7  mov     ebx, [rax+0C0h]
0x18004aadd  mov     qword ptr [rbp+340h+var_290], 2
0x18004aae8  pxor    xmm0, xmm0
0x18004aaec  movdqu  [rbp+340h+var_290+8], xmm0
0x18004aaf4  lea     rax, [rbp+340h+var_1B0]
0x18004aafb  mov     [rbp+340h+var_278], rax
0x18004ab02  mov     qword ptr [rbp+340h+var_270], 0
0x18004ab0d  mov     qword ptr [rbp+340h+var_270+8], r15
0x18004ab14  mov     dword ptr [rbp+340h+var_250], 0
0x18004ab1e  mov     qword ptr [rbp+340h+var_260], 0
0x18004ab29  mov     qword ptr [rbp+340h+var_260+8], r15
0x18004ab30  lea     rcx, [rbp+340h+var_290]
0x18004ab37  call    unicode_analysis__text_iterator__impl$1__advance_unicode_analysis__text_iterator__char_source__AnalysisCharSource_layout__layout_text_source__LayoutTextSource___
0x18004ab3c  movdqu  xmm0, [rbp+340h+var_290]
0x18004ab44  movdqu  xmm1, xmmword ptr [rbp+0C0h]
0x18004ab4c  movups  xmm2, [rbp+340h+var_270]
0x18004ab53  movups  xmm3, [rbp+340h+var_260]
0x18004ab5a  movdqa  xmmword ptr [rbp+340h+lpMem], xmm0
0x18004ab62  movdqa  [rbp+340h+var_1F0], xmm1
0x18004ab6a  movaps  [rbp+340h+var_1E0], xmm2
0x18004ab71  movaps  [rbp+340h+var_1D0], xmm3
0x18004ab78  mov     rax, qword ptr [rbp+340h+var_250]
0x18004ab7f  mov     [rbp+340h+var_1C0], rax
0x18004ab86  mov     r12d, 0FFFFFFFFh
0x18004ab8c  xor     r13d, r13d
0x18004ab8f  mov     byte ptr [rbp+340h+var_1B8], 0FFh
0x18004ab96  mov     [rbp+340h+var_158], 0
0x18004aba1  xor     ecx, ecx
0x18004aba3  xor     edx, edx
0x18004aba5  xor     r9d, r9d
0x18004aba8  xor     r10d, r10d
0x18004abab  xor     r14d, r14d
0x18004abae  mov     [rbp+340h+var_160], r15
0x18004abb5  mov     dword ptr [rbp+340h+var_138], ebx
0x18004abbb  jmp     short loc_18004ABF8
0x18004abc0  mov     edi, ebx
0x18004abc2  mov     r10b, byte ptr [rbp+340h+var_108]
0x18004abc9  mov     r9b, byte ptr [rbp+340h+var_130]
0x18004abd0  mov     dl, byte ptr [rbp+340h+var_208]
0x18004abd6  mov     ecx, dword ptr [rbp+340h+var_140]
0x18004abdc  mov     r13, r15
0x18004abdf  mov     r15, [rbp+340h+var_160]
0x18004abe6  mov     ebx, dword ptr [rbp+340h+var_138]
0x18004abec  mov     r12d, ebx
0x18004abef  cmp     r13, r15
0x18004abf2  jnb     loc_18004AE52
0x18004abf8  mov     [rbp+340h+var_128], r10
0x18004abff  mov     [rbp+340h+var_110], r9
0x18004ac06  mov     [rbp+340h+var_118], rdx
0x18004ac0d  mov     [rbp+340h+var_100], rcx
0x18004ac14  mov     rcx, [rbp+340h+var_120]
0x18004ac1b  mov     rdx, r13
0x18004ac1e  call    layout__run_list__RunList_layout__layout_types__BidiRun___get_run_at_layout__layout_types__BidiRun_
0x18004ac23  mov     ecx, [rax+18h]
0x18004ac26  movzx   eax, byte ptr [rax+8]
0x18004ac2a  cmp     rcx, r15
  ... truncated ...
```
