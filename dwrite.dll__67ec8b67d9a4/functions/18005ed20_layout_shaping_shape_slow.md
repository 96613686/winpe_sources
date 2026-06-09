# layout::shaping::shape_slow

- ea: `0x18005ed20`
- end: `0x1800600b3`
- name: `layout::shaping::shape_slow`
- size: `5011`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops`

## callers

- `0x18004a5f0`

## callees

- `0x180027680`
- `0x180027820`
- `0x180029de0`
- `0x180046410`
- `0x180056650`
- `0x18005a4a0`
- `0x18005c710`
- `0x18005cc60`
- `0x18005ed20`
- `0x180084280`
- `0x1800cff10`
- `0x1800d3fc0`
- `0x1800dc910`
- `0x180212ec8`
- `0x180212f4c`
- `0x180316190`
- `0x180316232`
- `0x180316255`
- `0x1803168c1`
- `0x180316980`
- `0x180316a30`
- `0x180316ae0`
- `0x180316ce0`
- `0x180316d00`
- `0x18031716c`
- `0x180318870`

## import_xrefs

- `kernel32!HeapFree` at `0x18005f122`
- `kernel32!HeapFree` at `0x18005f858`
- `kernel32!HeapFree` at `0x18005f87d`
- `kernel32!HeapFree` at `0x18005f8a2`
- `kernel32!HeapFree` at `0x18005f8c7`
- `kernel32!HeapFree` at `0x18005fb42`
- `kernel32!HeapFree` at `0x18005fb4e`
- `kernel32!HeapFree` at `0x18005fd5c`
- `kernel32!HeapFree` at `0x18005fd81`
- `kernel32!HeapFree` at `0x18005fda6`
- `kernel32!HeapFree` at `0x18005fdca`
- `kernel32!HeapFree` at `0x18005f122`
- `kernel32!HeapFree` at `0x18005f858`
- `kernel32!HeapFree` at `0x18005f87d`
- `kernel32!HeapFree` at `0x18005f8a2`
- `kernel32!HeapFree` at `0x18005f8c7`
- `kernel32!HeapFree` at `0x18005fb3b`
- `kernel32!HeapFree` at `0x18005fd5c`
- `kernel32!HeapFree` at `0x18005fd81`
- `kernel32!HeapFree` at `0x18005fda6`
- `kernel32!HeapFree` at `0x18005fdca`
- `kernel32!GetProcessHeap` at `0x18005f114`
- `kernel32!GetProcessHeap` at `0x18005f846`
- `kernel32!GetProcessHeap` at `0x18005f86f`
- `kernel32!GetProcessHeap` at `0x18005f894`
- `kernel32!GetProcessHeap` at `0x18005f8b9`
- `kernel32!GetProcessHeap` at `0x18005fb31`
- `kernel32!GetProcessHeap` at `0x18005fb44`
- `kernel32!GetProcessHeap` at `0x18005fd4a`
- `kernel32!GetProcessHeap` at `0x18005fd73`
- `kernel32!GetProcessHeap` at `0x18005fd98`
- `kernel32!GetProcessHeap` at `0x18005fdb6`
- `kernel32!GetProcessHeap` at `0x18005f114`
- `kernel32!GetProcessHeap` at `0x18005f846`
- `kernel32!GetProcessHeap` at `0x18005f86f`
- `kernel32!GetProcessHeap` at `0x18005f894`
- `kernel32!GetProcessHeap` at `0x18005f8b9`
- `kernel32!GetProcessHeap` at `0x18005fb2a`
- `kernel32!GetProcessHeap` at `0x18005fd4a`
- `kernel32!GetProcessHeap` at `0x18005fd73`
- `kernel32!GetProcessHeap` at `0x18005fd98`
- `kernel32!GetProcessHeap` at `0x18005fdb6`

## string_xrefs

- `0x18005fec5`: `assertion failed: text_range.end <= ro.text.len() && text_range.start < text_range.endC++ code failed to create last resort font reference.rust\layout\src\text_layout_factory.rs`
- `0x18005ff20`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x180060014`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_DWORD *__fastcall layout::shaping::shape_slow(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        unsigned __int64 a6,
        __int64 a7,
        unsigned __int64 a8,
        unsigned __int64 a9,
        _QWORD *a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int16 a17,
        char a18,
        __int64 a19)
{
  unsigned __int64 v21; // r13
  __int64 typographic_features; // rax
  int v24; // edx
  _DWORD *v25; // r15
  unsigned __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 i; // r14
  __int64 v30; // r15
  unsigned __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rsi
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned __int64 v37; // r13
  __int64 v38; // rdi
  unsigned __int64 v39; // rax
  __int64 v40; // rbx
  HANDLE v41; // rax
  _QWORD *v42; // rsi
  unsigned __int64 v43; // r14
  unsigned __int64 v44; // rdi
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // rsi
  __int64 v47; // rbx
  __int64 v48; // r15
  _WORD *v49; // rcx
  unsigned __int64 v50; // rsi
  unsigned __int64 v51; // r15
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rbx
  unsigned __int64 v54; // rax
  unsigned __int64 v55; // rdx
  __int64 nominal_glyph_ids; // rsi
  unsigned __int64 v57; // r13
  unsigned __int64 v58; // r14
  unsigned __int64 v59; // r15
  unsigned __int64 v60; // r14
  unsigned __int64 v61; // r14
  unsigned __int64 v62; // r15
  unsigned __int64 v63; // r14
  unsigned __int64 v64; // r13
  unsigned __int64 v65; // rdx
  unsigned __int64 v66; // rdx
  unsigned __int64 v67; // rdx
  __int64 v68; // r14
  __int64 v69; // rdi
  __int64 v70; // r15
  __int64 v71; // rsi
  __int64 v72; // rax
  __int64 v73; // rax
  void *v74; // r12
  int v75; // xmm6_4
  int v76; // xmm7_4
  __int64 v77; // r13
  int v78; // r14d
  unsigned __int64 v79; // rsi
  int glyph_placements; // eax
  __int64 v81; // rdi
  HANDLE v82; // rax
  void *v83; // rsi
  HANDLE ProcessHeap; // rax
  void *v85; // rsi
  HANDLE v86; // rax
  void *v87; // rsi
  HANDLE v88; // rax
  __int64 v90; // rcx
  int v91; // edx
  int v92; // r8d
  int v93; // r9d
  __int64 v94; // rdi
  __int64 v95; // rsi
  float v96; // xmm1_4
  int v97; // r8d
  int v98; // r9d
  double v99; // xmm0_8
  float v100; // xmm6_4
  __int64 v101; // rdi
  int *v102; // r14
  float v103; // xmm0_4
  int v104; // esi
  float v105; // xmm10_4
  HANDLE v106; // rax
  HANDLE v107; // rax
  __int64 line_spacing_metrics; // rax
  float v109; // xmm6_4
  unsigned __int64 v110; // rcx
  __int64 v111; // rdx
  __int64 v112; // r10
  unsigned __int64 v113; // rsi
  __int64 v114; // r8
  __int64 v115; // r10
  __int64 j; // rdx
  __int64 v117; // rsi
  __int64 v118; // rax
  __int64 v119; // rcx
  HANDLE v120; // rax
  void *v121; // rsi
  HANDLE v122; // rax
  void *v123; // rsi
  HANDLE v124; // rax
  HANDLE v125; // rax
  __int64 v126; // [rsp+38h] [rbp-48h]
  __int64 v127; // [rsp+48h] [rbp-38h]
  void *v128; // [rsp+E0h] [rbp+60h]
  __int64 v129; // [rsp+F0h] [rbp+70h] BYREF
  unsigned __int64 v130; // [rsp+F8h] [rbp+78h] BYREF
  unsigned __int64 v131; // [rsp+100h] [rbp+80h] BYREF
  unsigned __int64 v132; // [rsp+108h] [rbp+88h] BYREF
  int v133[2]; // [rsp+110h] [rbp+90h] BYREF
  __int64 v134; // [rsp+118h] [rbp+98h]
  __int64 v135; // [rsp+120h] [rbp+A0h] BYREF
  unsigned __int64 v136; // [rsp+128h] [rbp+A8h] BYREF
  int v137[2]; // [rsp+130h] [rbp+B0h]
  _OWORD *v138; // [rsp+138h] [rbp+B8h]
  LPVOID v139; // [rsp+140h] [rbp+C0h]
  void *v140; // [rsp+148h] [rbp+C8h]
  __int64 v141; // [rsp+150h] [rbp+D0h]
  __int64 v142; // [rsp+158h] [rbp+D8h]
  __int64 v143; // [rsp+160h] [rbp+E0h]
  __int64 v144; // [rsp+168h] [rbp+E8h]
  unsigned __int64 v145; // [rsp+170h] [rbp+F0h] BYREF
  __int64 v146; // [rsp+178h] [rbp+F8h]
  __int64 v147; // [rsp+180h] [rbp+100h]
  __int64 v148; // [rsp+188h] [rbp+108h] BYREF
  LPVOID v149; // [rsp+190h] [rbp+110h]
  __int64 v150; // [rsp+198h] [rbp+118h]
  _OWORD v151[3]; // [rsp+1A0h] [rbp+120h] BYREF
  __int64 v152; // [rsp+1D8h] [rbp+158h] BYREF
  LPVOID v153; // [rsp+1E0h] [rbp+160h]
  unsigned __int64 v154; // [rsp+1E8h] [rbp+168h]
  __int64 v155; // [rsp+1F0h] [rbp+170h] BYREF
  LPVOID v156; // [rsp+1F8h] [rbp+178h]
  __int64 v157; // [rsp+200h] [rbp+180h]
  __int64 v158; // [rsp+208h] [rbp+188h]
  _QWORD *v159; // [rsp+210h] [rbp+190h]
  _QWORD *v160; // [rsp+218h] [rbp+198h]
  __int64 v161; // [rsp+220h] [rbp+1A0h]
  __int64 v162; // [rsp+228h] [rbp+1A8h] BYREF
  LPVOID lpMem; // [rsp+230h] [rbp+1B0h]
  __int64 v164; // [rsp+238h] [rbp+1B8h]
  __int64 v165; // [rsp+240h] [rbp+1C0h]
  int v166; // [rsp+24Ch] [rbp+1CCh]
  __int64 v167; // [rsp+250h] [rbp+1D0h]
  int v168[2]; // [rsp+258h] [rbp+1D8h]
  unsigned __int64 v169; // [rsp+260h] [rbp+1E0h]
  LPVOID v170; // [rsp+268h] [rbp+1E8h]
  LPVOID v171; // [rsp+270h] [rbp+1F0h]
  _QWORD *v172; // [rsp+278h] [rbp+1F8h]
  char v173; // [rsp+287h] [rbp+207h]
  __int64 v174; // [rsp+288h] [rbp+208h]

  v174 = -2;
  if ( a9 > *(_QWORD *)(a1 + 16) || a9 <= a8 )
    core::panicking::panic(
      "assertion failed: text_range.end <= ro.text.len() && text_range.start < text_range.endC++ code failed to create la"
      "st resort font reference.rust\\layout\\src\\text_layout_factory.rs",
      86,
      &off_180338E40);
  if ( !a13 )
    core::panicking::panic_bounds_check(0, 0, &off_180338E58);
  v21 = 0;
  v170 = (LPVOID)(a9 - a8);
  if ( a9 >= a8 )
    v21 = a9 - a8;
  if ( a9 > a4 )
    core::slice::index::slice_end_index_len_fail(a9, a4, &off_180338E70);
  if ( a9 > a6 )
    core::slice::index::slice_end_index_len_fail(a9, a6, &off_180338E88);
  v171 = (LPVOID)(*(_QWORD *)(a1 + 8) + 2 * a8);
  v152 = 0;
  v153 = (LPVOID)8;
  v154 = 0;
  v148 = 0;
  v149 = (LPVOID)4;
  v150 = 0;
  v155 = 0;
  v156 = (LPVOID)4;
  v157 = 0;
  typographic_features = layout::get_typographic_features(
                           a8,
                           a9,
                           a12,
                           a13,
                           (__int64)&v152,
                           (__int64)&v148,
                           (__int64)&v155);
  if ( v24 )
  {
    v25 = (_DWORD *)typographic_features;
LABEL_100:
    if ( v155 )
    {
      v83 = v156;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v83);
    }
    if ( v148 )
    {
      v85 = v149;
      v86 = GetProcessHeap();
      HeapFree(v86, 0, v85);
    }
    if ( v152 )
    {
      v87 = v153;
      v88 = GetProcessHeap();
      HeapFree(v88, 0, v87);
    }
    return v25;
  }
  v26 = v154;
  v161 = a1;
  if ( v154 )
  {
    v27 = std::sys::alloc::windows::process_heap_alloc(0, 8 * v154);
    if ( !v27 )
      alloc::alloc::handle_alloc_error(8, 8 * v26);
  }
  else
  {
    v27 = 8;
  }
  v158 = a3 + 2 * a8;
  v140 = (void *)(a5 + 2 * a8);
  v145 = v26;
  v146 = v27;
  v139 = v153;
  v28 = 0;
  for ( i = 0; ; ++i )
  {
    v147 = v28;
    if ( i >= v26 )
      break;
    v30 = v28;
    if ( v28 == v145 )
    {
      alloc::raw_vec::RawVec_dwrite::font_collection::IDWriteFontCollection_alloc::alloc::Global_::grow_one_dwrite::font_collection::IDWriteFontCollection_alloc::alloc::Global_(
        &v145,
        &off_180338FD8);
      v27 = v146;
    }
    *(_QWORD *)(v27 + 8 * v30) = (char *)v139 + 16 * i;
    v28 = v30 + 1;
  }
  v141 = v28;
  lpMem = (LPVOID)v27;
  v31 = v21 + (v21 >> 1) + 16;
  if ( v21 > v31 )
    v31 = v21;
  v32 = 0xFFFF;
  if ( v31 < 0xFFFF )
    v32 = v31;
  layout::TextLayoutGlyphs::ensure_free_glyph_capacity(a2, v32);
  v33 = *(_QWORD *)(a16 + 8);
  v34 = a16 + 8;
  if ( !v33 )
    v34 = 0;
  v167 = v34;
  if ( !v33 )
    core::option::unwrap_failed(&off_180338EA0);
  *(_QWORD *)v137 = a16 + 8;
  v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 296LL))(v33);
  if ( !v35 )
    core::option::unwrap_failed(&off_180336098);
  *(_QWORD *)v168 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 144LL))(v35);
  if ( !*(_QWORD *)v168 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_1803431B8);
  v165 = v33;
  v172 = a2 + 13;
  v159 = a2 + 6;
  v160 = a2 + 9;
  v36 = *(_QWORD *)a15;
  if ( *(_QWORD *)a15 )
    v36 = a15;
  v164 = v36;
  v138 = (_OWORD *)(a15 + 8);
  v173 = *(_BYTE *)(a15 + 20);
  v166 = *(_DWORD *)(a15 + 8);
  v142 = a12 + 16;
  v143 = (__int64)v156;
  v144 = v157;
  LODWORD(v169) = 3;
  while ( 1 )
  {
    v37 = a2[8];
    v136 = v37;
    if ( a2[13] != v37 )
    {
      *(_QWORD *)&v151[0] = 0;
      core::panicking::assert_failed_usize_usize_(v172, &v136, v151, &off_180338EB8);
    }
    v135 = a2[11];
    if ( v37 != v135 )
    {
      *(_QWORD *)&v151[0] = 0;
      core::panicking::assert_failed_usize_usize_(v172, &v135, v151, &off_180338ED0);
    }
    v38 = *(_QWORD *)(a19 + 16);
    v39 = v37;
    if ( (_UNKNOWN **)v38 != &off_1804AF000 )
    {
      v40 = *(_QWORD *)(v38 + 24);
      *(_QWORD *)(v38 + 24) = &off_1804AF000;
      while ( (_UNKNOWN **)v40 != &off_1804AF000 )
      {
        v42 = *(_QWORD **)v40;
        if ( *(_QWORD *)(v40 + 8) >= 0x11u )
          v42 = (_QWORD *)*(v42 - 1);
        v40 = *(_QWORD *)(v40 + 24);
        v41 = GetProcessHeap();
        HeapFree(v41, 0, v42);
      }
      *(_QWORD *)(v38 + 32) = v38;
      *(_QWORD *)(v38 + 40) = *(_QWORD *)(v38 + 16);
      v37 = a2[8];
      v39 = a2[13];
    }
    v43 = *a2 - v39;
    if ( v43 >= 0xFFFF )
      v43 = 0xFFFF;
    v44 = v43 + v37;
    v45 = v43 + v37;
    v46 = *a2 - v39;
    if ( v46 )
    {
      v47 = v37;
      if ( v43 > *v159 - v37 )
      {
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5((_DWORD)v159, v37, v43, 2, 2);
        v47 = a2[8];
      }
      v48 = a2[7];
      v49 = (_WORD *)(v48 + 2 * v47);
      if ( v46 >= 2 )
      {
        memset_0(v49, 0, 2 * v43 - 2);
        v49 = (_WORD *)(v48 + 2 * (v47 + v43) - 2);
        v47 = v43 + v47 - 1;
      }
      *v49 = 0;
      v45 = v47 + 1;
    }
    a2[8] = v45;
    v50 = a2[11];
    v51 = v44 - v50;
    if ( v44 > v50 )
    {
      if ( v51 > *v160 - v50 )
      {
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
          (_DWORD)v160,
          v50,
          v44 - v50,
          2,
          2);
        v50 = a2[11];
      }
      memset_0((void *)(a2[10] + 2 * v50), 0, 2 * v51);
      v45 = a2[8];
      v44 = v51 + v50;
    }
    a2[11] = v44;
    v52 = a2[13];
    if ( v45 < v52 )
      core::slice::index::slice_start_index_len_fail(v52, v45, &off_180338FC0);
    if ( v44 < v52 )
      core::slice::index::slice_start_index_len_fail(v52, v44, &off_180338FA8);
    shaping_cache::get_glyphs(
      (int)v133,
      v168[0],
      a19,
      v167,
      v164,
      (__int64)v171,
      (__int64)v170,
      v173,
      v166 & 1,
      a17,
      a18,
      v142,
      (__int64)lpMem,
      v141,
      v143,
      v144,
      v43,
      v158,
      (__int64)v170,
      v140,
      (__int64)v170,
      2 * v52 + a2[7],
      v45 - v52,
      a2[10] + 2 * v52,
      v44 - v52);
    v53 = a2[8];
    if ( v133[0] != 1 )
      break;
    if ( (unsigned int)(v133[1] + 3) >= 2 )
    {
      if ( v37 <= v53 )
        a2[8] = v37;
      if ( v37 <= a2[11] )
        a2[11] = v37;
LABEL_98:
      v25 = 0;
      if ( v145 )
      {
        v82 = GetProcessHeap();
        HeapFree(v82, 0, lpMem);
      }
      goto LABEL_100;
    }
    if ( v37 <= v53 )
    {
      a2[8] = v37;
      v53 = v37;
    }
    v54 = a2[11];
    if ( v37 <= v54 )
    {
      a2[11] = v37;
      v54 = v37;
    }
    v132 = v53;
    if ( *v172 != v53 )
    {
      *(_QWORD *)&v151[0] = 0;
      core::panicking::assert_failed_usize_usize_(v172, &v132, v151, &off_180338EE8);
    }
    v131 = v54;
    if ( v53 != v54 )
    {
      *(_QWORD *)&v151[0] = 0;
      core::panicking::assert_failed_usize_usize_(v172, &v131, v151, &off_180338F00);
    }
    LODWORD(v169) = v169 - 1;
    if ( !(_DWORD)v169 )
    {
      nominal_glyph_ids = layout::get_nominal_glyph_ids(
                            v165,
                            (_DWORD)v171,
                            (_DWORD)v170,
                            (_DWORD)v159,
                            (__int64)v160,
                            v158,
                            (__int64)v170);
      v53 = a2[8];
      goto LABEL_78;
    }
    v55 = v43 + (v43 >> 1) + 16;
    if ( v43 > v55 )
      v55 = v43;
    if ( v55 >= 0xFFFF )
      v55 = 0xFFFF;
    layout::TextLayoutGlyphs::ensure_free_glyph_capacity(a2, v55);
  }
  nominal_glyph_ids = v134;
  v57 = v134 + v37;
  if ( v57 <= v53 )
  {
    a2[8] = v57;
    v53 = v57;
  }
  if ( v57 <= a2[11] )
    a2[11] = v57;
LABEL_78:
  v162 = nominal_glyph_ids + *v172;
  v130 = v53;
  if ( v162 != v53 )
  {
    *(_QWORD *)&v151[0] = 0;
    core::panicking::assert_failed_usize_usize_(&v162, &v130, v151, &off_180338F18);
  }
  v129 = a2[11];
  if ( v53 != v129 )
  {
    *(_QWORD *)&v151[0] = 0;
    core::panicking::assert_failed_usize_usize_(&v162, &v129, v151, &off_180338F30);
  }
  v58 = a2[5];
  v59 = v53 - v58;
  if ( v53 <= v58 )
  {
    v60 = v53;
  }
  else
  {
    if ( v59 > a2[3] - v58 )
    {
      alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
        (_DWORD)a2 + 24,
        v58,
        v53 - v58,
        4,
        4);
      v58 = a2[5];
      v53 = v162;
    }
    memset_0((void *)(a2[4] + 4 * v58), 0, 4 * v59);
    v60 = v59 + v58;
  }
  a2[5] = v60;
  v61 = a2[2];
  v62 = v53 - v61;
  if ( v53 <= v61 )
  {
    v63 = v53;
  }
  else
  {
    if ( v62 > *a2 - v61 )
    {
      alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5((_DWORD)a2, v61, v53 - v61, 4, 8);
      v61 = a2[2];
      v53 = v162;
    }
    memset_0((void *)(a2[1] + 8 * v61), 0, 8 * v62);
    v63 = v62 + v61;
  }
  a2[2] = v63;
  v64 = a2[13];
  v167 = v53 - v64;
  if ( v53 < v64 )
    core::slice::index::slice_index_order_fail(v64, v53, &off_180338F48);
  v65 = a2[8];
  if ( v53 > v65 )
    core::slice::index::slice_end_index_len_fail(v53, v65, &off_180338F48);
  v66 = a2[11];
  if ( v53 > v66 )
    core::slice::index::slice_end_index_len_fail(v53, v66, &off_180338F60);
  v67 = a2[5];
  if ( v53 > v67 )
    core::slice::index::slice_end_index_len_fail(v53, v67, &off_180338F78);
  v164 = nominal_glyph_ids;
  if ( v53 > v63 )
    core::slice::index::slice_end_index_len_fail(v53, v63, &off_180338F90);
  v68 = a2[7];
  v69 = a2[10] + 2 * v64;
  v70 = a2[4];
  v71 = a2[1] + 8 * v64;
  v72 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v165 + 296LL))(v165);
  if ( !v72 )
    core::option::unwrap_failed(&off_180336098);
  *(_QWORD *)v168 = v70;
  v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v72 + 144LL))(v72);
  if ( !v73 )
    core::panicking::panic(
      "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
      32,
      &off_1803431B8);
  v25 = (_DWORD *)(v68 + 2 * v64);
  v169 = v64;
  v74 = (void *)(*(_QWORD *)v168 + 4 * v64);
  v75 = *(_DWORD *)(a16 + 16);
  v76 = *(_DWORD *)(v161 + 220);
  v77 = v161 + 224;
  v78 = *(_DWORD *)(v161 + 256);
  v128 = (void *)v71;
  v79 = v167;
  glyph_placements = shaping_cache::get_glyph_placements(
                       v73,
                       a19,
                       v137[0],
                       (int)v171,
                       (__int64)v170,
                       v158,
                       (__int64)v170,
                       (__int64)v140,
                       (__int64)v170,
                       v75,
                       v76,
                       v161 + 224,
                       v78,
                       v173,
                       v166 & 1,
                       a17,
                       a18,
                       v142,
                       (__int64)lpMem,
                       v141,
                       v143,
                       v144,
                       (__int64)v25,
                       v167,
                       v69,
                       v167,
                       v74,
                       v167,
                       v128,
                       v167);
  v81 = v164;
  switch ( glyph_placements )
  {
    case 0:
      if ( v173 & 1 | ((*(_BYTE *)(a12 + 111) & 1) == 0)
        || v53 == v169
        || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v165 + 680LL))(v165) )
      {
        goto LABEL_126;
      }
      if ( v79 >> 62 != 0 || 4 * v79 > 0x7FFFFFFFFFFFFFFCLL )
      {
        v90 = 0;
        goto LABEL_112;
      }
      v170 = (LPVOID)std::sys::alloc::windows::process_heap_alloc(8, 4 * v79);
      if ( !v170 )
      {
        v90 = 4;
LABEL_112:
        alloc::raw_vec::handle_error(v90, 4 * v79, &off_180338FF0);
      }
      v171 = (LPVOID)std::sys::alloc::windows::process_heap_alloc(8, 4 * v79);
      if ( !v171 )
        alloc::alloc::handle_alloc_error(4, 4 * v79);
      v127 = v79;
      v126 = v79;
      v94 = v79;
      v95 = v165;
      v96 = *(float *)&v75;
      dwritecore_defs::font_face::IFontFace::get_glyph_advances(
        v165,
        v91,
        v92,
        v93,
        v77,
        v78,
        (__int64)v25,
        v126,
        (__int64)v170,
        v127,
        0);
      dwritecore_defs::font_face::IFontFace::get_kerning_pair_adjustments(v95, (_DWORD)v25, v94, (_DWORD)v171, v94);
      memset(v151, 0, sizeof(v151));
      (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v95 + 208LL))(v95, v151);
      v99 = rendering_helpers::metrics_converter::MetricsConverter::new(LOWORD(v151[0]), v78, v97, v98, v76, v77);
      v100 = *(float *)&v99;
      v101 = 0;
      v102 = (int *)v170;
      v25 = v171;
      break;
    default:
      goto LABEL_98;
  }
  while ( v167 != v101 )
  {
    v104 = v25[v101];
    if ( v104 )
    {
      v105 = *((float *)v74 + v101);
      if ( v100 != 1.0 )
      {
        if ( v105 != (float)(o_roundf_0() * v96) )
          goto LABEL_119;
        v103 = o_roundf_0();
        goto LABEL_118;
      }
      if ( v105 == (float)((float)v102[v101] * v96) )
      {
        v103 = (float)v104;
LABEL_118:
        *((float *)v74 + v101) = fmaxf(v105 + (float)(v103 * v96), 0.0);
      }
    }
LABEL_119:
    ++v101;
  }
  v106 = GetProcessHeap();
  HeapFree(v106, 0, v25);
  v107 = GetProcessHeap();
  HeapFree(v107, 0, v102);
  v81 = v164;
  v79 = v167;
LABEL_126:
  line_spacing_metrics = layout::recent_metrics::RecentFontMetrics::get_line_spacing_metrics(
                           (int)a7 + 32,
                           v161,
                           a14,
                           a11,
                           a8,
                           a16,
                           a15);
  if ( v53 == v169 )
  {
    v109 = FLOAT_N0_0;
  }
  else
  {
    v110 = v79 & 7;
    if ( v169 - v53 <= 0xFFFFFFFFFFFFFFF8uLL )
    {
      v113 = v79 & 0xFFFFFFFFFFFFFFF8uLL;
      v112 = *(_QWORD *)v168;
      v109 = FLOAT_N0_0;
      v111 = 0;
      do
      {
        v114 = *(_QWORD *)v168 + 4 * v169 + 28;
        v109 = (float)((float)((float)((float)((float)((float)((float)(v109 + *(float *)(v114 + 4 * v111 - 28))
                                                             + *(float *)(v114 + 4 * v111 - 24))
                                                     + *(float *)(v114 + 4 * v111 - 20))
                                             + *(float *)(v114 + 4 * v111 - 16))
                                     + *(float *)(v114 + 4 * v111 - 12))
                             + *(float *)(v114 + 4 * v111 - 8))
                     + *(float *)(v114 + 4 * v111 - 4))
             + *(float *)(v114 + 4 * v111);
        v111 += 8;
      }
      while ( v113 != v111 );
    }
    else
    {
      v109 = FLOAT_N0_0;
      v111 = 0;
      v112 = *(_QWORD *)v168;
    }
    if ( v110 )
    {
      v115 = 4 * v169 + 4 * v111 + v112;
      for ( j = 0; j != v110; ++j )
        v109 = v109 + *(float *)(v115 + 4 * j);
    }
  }
  DWORD2(v151[0]) = *(_DWORD *)(line_spacing_metrics + 8);
  *(_QWORD *)&v151[0] = *(_QWORD *)line_spacing_metrics;
  v117 = a10[2];
  if ( v117 == *a10 )
    alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_(
      a10,
      &off_180338A80);
  v118 = a10[1];
  v119 = 80 * v117;
  *(_QWORD *)(v118 + v119) = v169;
  *(_QWORD *)(v118 + v119 + 8) = v53;
  *(_QWORD *)(v118 + v119 + 16) = 0;
  *(_QWORD *)(v118 + v119 + 24) = *(_QWORD *)&v151[0];
  *(_DWORD *)(v118 + v119 + 32) = DWORD2(v151[0]);
  *(float *)(v118 + v119 + 36) = v109;
  *(_QWORD *)(v118 + v119 + 40) = 0;
  *(_OWORD *)(v118 + v119 + 48) = *v138;
  *(_DWORD *)(v118 + v119 + 64) = 0;
  *(_DWORD *)(v118 + v119 + 67) = 0;
  *(_DWORD *)(v118 + v119 + 72) = a9;
  *v172 += v81;
  a10[2] = v117 + 1;
  if ( v145 )
  {
    v120 = GetProcessHeap();
    HeapFree(v120, 0, lpMem);
  }
  if ( v155 )
  {
    v121 = v156;
    v122 = GetProcessHeap();
    HeapFree(v122, 0, v121);
  }
  if ( v148 )
  {
    v123 = v149;
    v124 = GetProcessHeap();
    HeapFree(v124, 0, v123);
  }
  if ( v152 )
  {
    v125 = GetProcessHeap();
    HeapFree(v125, 0, v139);
  }
  return v25;
}

```

## disassembly

```asm
0x18005ed20  push    rbp
0x18005ed21  push    r15
0x18005ed23  push    r14
0x18005ed25  push    r13
0x18005ed27  push    r12
0x18005ed29  push    rsi
0x18005ed2a  push    rdi
0x18005ed2b  push    rbx
0x18005ed2c  sub     rsp, 2E8h
0x18005ed33  lea     rbp, [rsp+80h]
0x18005ed3b  movaps  [rbp+2A0h+var_50], xmm10
0x18005ed43  movaps  [rbp+2A0h+var_60], xmm9
0x18005ed4b  movaps  [rbp+2A0h+var_70], xmm8
0x18005ed53  movaps  [rbp+2A0h+var_80], xmm7
0x18005ed5a  movaps  [rbp+2A0h+var_90], xmm6
0x18005ed61  mov     [rbp+2A0h+var_98], 0FFFFFFFFFFFFFFFEh
0x18005ed6c  mov     r10, [rbp+2A0h+arg_40]
0x18005ed73  cmp     r10, [rcx+10h]
0x18005ed77  ja      loc_18005FEC5
0x18005ed7d  mov     rsi, rcx
0x18005ed80  mov     rcx, [rbp+2A0h+arg_38]
0x18005ed87  cmp     r10, rcx
0x18005ed8a  jbe     loc_18005FEC5
0x18005ed90  mov     rax, r9
0x18005ed93  mov     r9, [rbp+2A0h+arg_60]
0x18005ed9a  test    r9, r9
0x18005ed9d  jz      loc_18006008A
0x18005eda3  mov     r12, rdx
0x18005eda6  xor     r13d, r13d
0x18005eda9  mov     rdx, r10
0x18005edac  sub     rdx, rcx
0x18005edaf  mov     [rbp+2A0h+var_B8], rdx
0x18005edb6  cmovnb  r13, rdx
0x18005edba  cmp     r10, rax
0x18005edbd  ja      loc_18005FEDD
0x18005edc3  mov     rdx, [rbp+2A0h+arg_28]
0x18005edca  cmp     r10, rdx
0x18005edcd  ja      loc_18005FEEF
0x18005edd3  mov     r14, r8
0x18005edd6  mov     r8, [rbp+2A0h+arg_58]
0x18005eddd  lea     rax, [rcx+rcx]
0x18005ede1  add     rax, [rsi+8]
0x18005ede5  mov     [rbp+2A0h+var_B0], rax
0x18005edec  mov     [rbp+2A0h+var_148], 0
0x18005edf7  mov     [rbp+2A0h+var_140], 8
0x18005ee02  mov     [rbp+2A0h+var_138], 0
0x18005ee0d  mov     [rbp+2A0h+var_198], 0
0x18005ee18  mov     [rbp+2A0h+var_190], 4
0x18005ee23  mov     [rbp+2A0h+var_188], 0
0x18005ee2e  mov     [rbp+2A0h+var_130], 0
0x18005ee39  mov     [rbp+2A0h+var_128], 4
0x18005ee44  mov     [rbp+2A0h+var_120], 0
0x18005ee4f  lea     rax, [rbp+2A0h+var_130]
0x18005ee56  mov     [rsp+320h+var_2F0], rax
0x18005ee5b  lea     rax, [rbp+2A0h+var_198]
0x18005ee62  mov     [rsp+320h+var_2F8], rax
0x18005ee67  lea     rax, [rbp+2A0h+var_148]
0x18005ee6e  mov     [rsp+320h+var_300], rax
0x18005ee73  mov     rdx, r10
0x18005ee76  call    layout__get_typographic_features
0x18005ee7b  mov     ebx, edx
0x18005ee7d  test    edx, edx
0x18005ee7f  jz      short loc_18005EE89
0x18005ee81  mov     r15, rax
0x18005ee84  jmp     loc_18005F85E
0x18005ee89  mov     rbx, [rbp+2A0h+var_138]
0x18005ee90  test    rbx, rbx
0x18005ee93  mov     [rbp+2A0h+var_100], rsi
0x18005ee9a  jz      short loc_18005EEC5
0x18005ee9c  lea     rsi, ds:0[rbx*8]
0x18005eea4  xor     ecx, ecx
0x18005eea6  mov     rdx, rsi
0x18005eea9  call    std__sys__alloc__windows__process_heap_alloc
0x18005eeae  test    rax, rax
0x18005eeb1  jnz     short loc_18005EECA
0x18005eeb3  mov     ecx, 8
0x18005eeb8  mov     rdx, rsi
0x18005eebb  call    alloc__alloc__handle_alloc_error
0x18005eec0  jmp     loc_1800600B1
0x18005eec5  mov     eax, 8
0x18005eeca  mov     rcx, [rbp+2A0h+arg_20]
0x18005eed1  mov     rdx, [rbp+2A0h+arg_38]
0x18005eed8  lea     r8, [r14+rdx*2]
0x18005eedc  mov     [rbp+2A0h+var_118], r8
0x18005eee3  lea     rcx, [rcx+rdx*2]
0x18005eee7  mov     [rbp+2A0h+var_1D8], rcx
0x18005eeee  mov     [rbp+2A0h+var_1B0], rbx
0x18005eef5  mov     [rbp+2A0h+var_1A8], rax
0x18005eefc  mov     rcx, [rbp+2A0h+var_140]
0x18005ef03  mov     [rbp+2A0h+var_1E0], rcx
0x18005ef0a  xor     ecx, ecx
0x18005ef0c  lea     rsi, off_180338FD8; "rust\\layout\\src\\shaping.rs"
0x18005ef13  lea     rdi, [rbp+2A0h+var_1B0]
0x18005ef1a  xor     r14d, r14d
0x18005ef1d  jmp     short loc_18005EF3C
0x18005ef20  lea     rcx, [r14+1]
0x18005ef24  shl     r14, 4
0x18005ef28  add     r14, [rbp+2A0h+var_1E0]
0x18005ef2f  mov     [rax+r15*8], r14
0x18005ef33  inc     r15
0x18005ef36  mov     r14, rcx
0x18005ef39  mov     rcx, r15
0x18005ef3c  mov     [rbp+2A0h+var_1A0], rcx
0x18005ef43  cmp     r14, rbx
0x18005ef46  jnb     short loc_18005EF68
0x18005ef48  mov     r15, rcx
0x18005ef4b  cmp     rcx, [rbp+2A0h+var_1B0]
0x18005ef52  jnz     short loc_18005EF20
0x18005ef54  mov     rcx, rdi
0x18005ef57  mov     rdx, rsi
0x18005ef5a  call    alloc__raw_vec__RawVec_dwrite__font_collection__IDWriteFontCollection_alloc__alloc__Global___grow_one_dwrite__font_collection__IDWriteFontCollection_alloc__alloc__Global_
0x18005ef5f  mov     rax, [rbp+2A0h+var_1A8]
0x18005ef66  jmp     short loc_18005EF20
0x18005ef68  mov     [rbp+2A0h+var_1D0], rcx
0x18005ef6f  mov     [rbp+2A0h+lpMem], rax
0x18005ef76  mov     rax, r13
0x18005ef79  shr     rax, 1
0x18005ef7c  add     rax, r13
0x18005ef7f  add     rax, 10h
0x18005ef83  cmp     r13, rax
0x18005ef86  cmova   rax, r13
0x18005ef8a  cmp     rax, 0FFFFh
0x18005ef90  mov     edx, 0FFFFh
0x18005ef95  cmovb   rdx, rax
0x18005ef99  mov     rcx, r12
0x18005ef9c  call    layout__TextLayoutGlyphs__ensure_free_glyph_capacity
0x18005efa1  mov     rax, [rbp+2A0h+arg_78]
0x18005efa8  lea     rcx, [rax+8]
0x18005efac  mov     rsi, [rax+8]
0x18005efb0  mov     rax, rcx
0x18005efb3  test    rsi, rsi
0x18005efb6  cmovz   rax, rsi
0x18005efba  mov     [rbp+2A0h+var_D0], rax
0x18005efc1  jz      loc_18005FEFE
0x18005efc7  mov     qword ptr [rbp+2A0h+var_1F0], rcx
0x18005efce  mov     rax, [rsi]
0x18005efd1  mov     rax, [rax+128h]
0x18005efd8  mov     rcx, rsi
0x18005efdb  call    cs:__guard_dispatch_icall_fptr
0x18005efe1  test    rax, rax
0x18005efe4  jz      loc_18005FF0F
0x18005efea  mov     rcx, [rax]
0x18005efed  mov     rdx, [rcx+90h]
0x18005eff4  mov     rcx, rax
0x18005eff7  mov     rax, rdx
0x18005effa  call    cs:__guard_dispatch_icall_fptr
0x18005f000  mov     qword ptr [rbp+2A0h+var_C8], rax
0x18005f007  test    rax, rax
0x18005f00a  jz      loc_18005FF20
0x18005f010  mov     [rbp+2A0h+var_E0], rsi
0x18005f017  lea     rax, [r12+68h]
0x18005f01c  mov     [rbp+2A0h+var_A8], rax
0x18005f023  lea     rax, [r12+30h]
0x18005f028  mov     [rbp+2A0h+var_110], rax
0x18005f02f  lea     rax, [r12+48h]
0x18005f034  mov     [rbp+2A0h+var_108], rax
0x18005f03b  mov     rcx, [rbp+2A0h+arg_70]
0x18005f042  mov     rax, [rcx]
0x18005f045  test    rax, rax
0x18005f048  cmovnz  rax, rcx
0x18005f04c  mov     [rbp+2A0h+var_E8], rax
0x18005f053  lea     rax, [rcx+8]
0x18005f057  mov     [rbp+2A0h+var_1E8], rax
0x18005f05e  movzx   eax, byte ptr [rcx+14h]
0x18005f062  mov     [rbp+2A0h+var_99], al
0x18005f068  mov     eax, [rcx+8]
0x18005f06b  mov     [rbp+2A0h+var_D4], eax
0x18005f071  mov     rax, [rbp+2A0h+arg_58]
0x18005f078  add     rax, 10h
0x18005f07c  mov     [rbp+2A0h+var_1C8], rax
0x18005f083  mov     rax, [rbp+2A0h+var_128]
0x18005f08a  mov     [rbp+2A0h+var_1C0], rax
0x18005f091  mov     rax, [rbp+2A0h+var_120]
0x18005f098  mov     [rbp+2A0h+var_1B8], rax
0x18005f09f  mov     dword ptr [rbp+2A0h+var_C0], 3
0x18005f0a9  nop     dword ptr [rax+00000000h]
0x18005f0b0  mov     r13, [r12+40h]
0x18005f0b5  mov     [rbp+2A0h+var_1F8], r13
0x18005f0bc  cmp     [r12+68h], r13
0x18005f0c1  jnz     loc_18005FDD9
0x18005f0c7  mov     rax, [r12+58h]
0x18005f0cc  mov     [rbp+2A0h+var_200], rax
0x18005f0d3  cmp     r13, rax
0x18005f0d6  jnz     loc_18005FE0A
0x18005f0dc  mov     rax, qword ptr [rbp+2A0h+arg_90]
0x18005f0e3  mov     rdi, [rax+10h]
0x18005f0e7  mov     rax, r13
0x18005f0ea  lea     rcx, off_1804AF000
0x18005f0f1  cmp     rdi, rcx
0x18005f0f4  jz      short loc_18005F166
0x18005f0f6  mov     rbx, [rdi+18h]
0x18005f0fa  lea     rax, off_1804AF000
0x18005f101  mov     [rdi+18h], rax
0x18005f105  jmp     short loc_18005F12F
0x18005f110  mov     rbx, [rbx+18h]
0x18005f114  call    cs:__imp_GetProcessHeap
0x18005f11a  mov     rcx, rax; hHeap
0x18005f11d  xor     edx, edx; dwFlags
0x18005f11f  mov     r8, rsi; lpMem
0x18005f122  call    cs:__imp_HeapFree
0x18005f128  lea     rax, off_1804AF000
0x18005f12f  cmp     rbx, rax
0x18005f132  jz      short loc_18005F150
0x18005f134  mov     rsi, [rbx]
0x18005f137  cmp     qword ptr [rbx+8], 11h
0x18005f13c  jb      short loc_18005F110
0x18005f13e  mov     rsi, [rsi-8]
0x18005f142  jmp     short loc_18005F110
0x18005f150  mov     [rdi+20h], rdi
0x18005f154  mov     rax, [rdi+10h]
0x18005f158  mov     [rdi+28h], rax
0x18005f15c  mov     r13, [r12+40h]
0x18005f161  mov     rax, [r12+68h]
0x18005f166  mov     rsi, [r12]
0x18005f16a  mov     r14, rsi
0x18005f16d  sub     r14, rax
0x18005f170  cmp     r14, 0FFFFh
0x18005f177  mov     ecx, 0FFFFh
0x18005f17c  cmovnb  r14, rcx
0x18005f180  lea     rdi, [r14+r13]
0x18005f184  mov     rbx, rdi
0x18005f187  sub     rsi, rax
0x18005f18a  jz      short loc_18005F1E0
0x18005f18c  mov     rax, [rbp+2A0h+var_110]
0x18005f193  mov     rax, [rax]
0x18005f196  sub     rax, r13
0x18005f199  mov     rbx, r13
0x18005f19c  cmp     r14, rax
0x18005f19f  ja      loc_18005F405
0x18005f1a5  mov     r15, [r12+38h]
0x18005f1aa  lea     rcx, [r15+rbx*2]; void *
0x18005f1ae  cmp     rsi, 2
0x18005f1b2  jb      short loc_18005F1D8
0x18005f1b4  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r14*2]; Size
0x18005f1bc  xor     edx, edx; Val
0x18005f1be  call    memset_0
0x18005f1c3  lea     rax, [rbx+rdi]
0x18005f1c7  sub     rax, r13
0x18005f1ca  lea     rcx, [r15+rax*2]
0x18005f1ce  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18005f1d2  add     rbx, r14
0x18005f1d5  dec     rbx
0x18005f1d8  mov     word ptr [rcx], 0
0x18005f1dd  inc     rbx
0x18005f1e0  mov     [r12+40h], rbx
0x18005f1e5  mov     rsi, [r12+58h]
0x18005f1ea  mov     r15, rdi
0x18005f1ed  sub     r15, rsi
0x18005f1f0  jbe     short loc_18005F227
0x18005f1f2  mov     rax, [rbp+2A0h+var_108]
0x18005f1f9  mov     rax, [rax]
0x18005f1fc  sub     rax, rsi
0x18005f1ff  cmp     r15, rax
0x18005f202  ja      loc_18005F430
0x18005f208  lea     rcx, [rsi+rsi]
0x18005f20c  add     rcx, [r12+50h]; void *
0x18005f211  lea     r8, [r15+r15]; Size
0x18005f215  xor     edx, edx; Val
0x18005f217  call    memset_0
0x18005f21c  add     rsi, r15
0x18005f21f  mov     rbx, [r12+40h]
0x18005f224  mov     rdi, rsi
0x18005f227  mov     [r12+58h], rdi
0x18005f22c  mov     rcx, [r12+68h]
0x18005f231  mov     rax, rbx
0x18005f234  sub     rax, rcx
0x18005f237  jb      loc_18005FE3B
0x18005f23d  mov     rdx, rdi
0x18005f240  sub     rdx, rcx
0x18005f243  jb      loc_18005FE4F
0x18005f249  add     rcx, rcx
0x18005f24c  mov     r8, [r12+38h]
0x18005f251  add     r8, rcx
0x18005f254  add     rcx, [r12+50h]
0x18005f259  mov     [rsp+320h+var_260], rdx; __int64
0x18005f261  mov     [rsp+320h+var_268], rcx; __int64
0x18005f269  mov     [rsp+320h+var_270], rax; __int64
0x18005f271  mov     [rsp+320h+var_278], r8; __int64
0x18005f279  mov     rcx, [rbp+2A0h+var_B8]
0x18005f280  mov     [rsp+320h+var_280], rcx; __int64
0x18005f288  mov     rax, [rbp+2A0h+var_1D8]
0x18005f28f  mov     [rsp+320h+var_288], rax; void *
0x18005f297  mov     [rsp+320h+var_290], rcx; __int64
0x18005f29f  mov     rax, [rbp+2A0h+var_118]
0x18005f2a6  mov     [rsp+320h+var_298], rax; __int64
0x18005f2ae  mov     qword ptr [rsp+320h+var_2A0], r14; __int64
0x18005f2b6  mov     rax, [rbp+2A0h+var_1B8]
0x18005f2bd  mov     qword ptr [rsp+320h+var_2A8], rax; __int64
0x18005f2c2  mov     rax, [rbp+2A0h+var_1C0]
0x18005f2c9  mov     qword ptr [rsp+320h+var_2B0], rax; __int64
0x18005f2ce  mov     rax, [rbp+2A0h+var_1D0]
0x18005f2d5  mov     qword ptr [rsp+320h+var_2B8], rax; __int64
0x18005f2da  mov     rax, [rbp+2A0h+lpMem]
0x18005f2e1  mov     [rsp+320h+var_2C0], rax; __int64
0x18005f2e6  mov     rax, [rbp+2A0h+var_1C8]
0x18005f2ed  mov     [rsp+320h+var_2C8], rax; __int64
0x18005f2f2  mov     eax, dword ptr [rbp+2A0h+arg_88]
0x18005f2f8  mov     dword ptr [rsp+320h+var_2D0], eax; char
0x18005f2fc  movzx   eax, [rbp+2A0h+arg_80]
0x18005f303  mov     [rsp+320h+var_2D8], ax; __int16
  ... truncated ...
```
