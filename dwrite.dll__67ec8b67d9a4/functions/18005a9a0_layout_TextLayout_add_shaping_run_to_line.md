# layout::TextLayout::add_shaping_run_to_line

- ea: `0x18005a9a0`
- end: `0x18005c2e2`
- name: `layout::TextLayout::add_shaping_run_to_line`
- size: `6466`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops`

## callers

- `0x180053af0`

## callees

- `0x180029de0`
- `0x180046410`
- `0x1800534f0`
- `0x180056650`
- `0x18005a9a0`
- `0x18005c4e0`
- `0x18005c710`
- `0x18005cc60`
- `0x1800cff10`
- `0x1800d3fc0`
- `0x1800dc910`
- `0x180212f4c`
- `0x180316190`
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

- `kernel32!HeapFree` at `0x18005bb3e`
- `kernel32!HeapFree` at `0x18005bb63`
- `kernel32!HeapFree` at `0x18005bb88`
- `kernel32!HeapFree` at `0x18005bbb0`
- `kernel32!HeapFree` at `0x18005bbcd`
- `kernel32!HeapFree` at `0x18005bed1`
- `kernel32!HeapFree` at `0x18005bef3`
- `kernel32!HeapFree` at `0x18005bf18`
- `kernel32!HeapFree` at `0x18005bb3e`
- `kernel32!HeapFree` at `0x18005bb63`
- `kernel32!HeapFree` at `0x18005bb88`
- `kernel32!HeapFree` at `0x18005bbb0`
- `kernel32!HeapFree` at `0x18005bbcd`
- `kernel32!HeapFree` at `0x18005bed1`
- `kernel32!HeapFree` at `0x18005bef3`
- `kernel32!HeapFree` at `0x18005bf18`
- `kernel32!GetProcessHeap` at `0x18005bb30`
- `kernel32!GetProcessHeap` at `0x18005bb55`
- `kernel32!GetProcessHeap` at `0x18005bb7a`
- `kernel32!GetProcessHeap` at `0x18005bba2`
- `kernel32!GetProcessHeap` at `0x18005bbbb`
- `kernel32!GetProcessHeap` at `0x18005bebf`
- `kernel32!GetProcessHeap` at `0x18005bee1`
- `kernel32!GetProcessHeap` at `0x18005bf0a`
- `kernel32!GetProcessHeap` at `0x18005bb30`
- `kernel32!GetProcessHeap` at `0x18005bb55`
- `kernel32!GetProcessHeap` at `0x18005bb7a`
- `kernel32!GetProcessHeap` at `0x18005bba2`
- `kernel32!GetProcessHeap` at `0x18005bbbb`
- `kernel32!GetProcessHeap` at `0x18005bebf`
- `kernel32!GetProcessHeap` at `0x18005bee1`
- `kernel32!GetProcessHeap` at `0x18005bf0a`

## string_xrefs

- `0x18005bfc1`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`
- `0x18005c12e`: `assertion failed: !ptr.is_null()d:\os\src\onecoreuap\windows\directwrite\dwritecore-copy\rust\interop_utils\src\lib.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall layout::TextLayout::add_shaping_run_to_line(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5)
{
  _QWORD *v7; // rsi
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r11
  unsigned __int64 v13; // r9
  __int64 result; // rax
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // r13
  __int64 v18; // r12
  unsigned __int64 v19; // rdx
  __int64 v20; // r11
  unsigned __int64 v21; // r10
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rbx
  __int64 v25; // r8
  unsigned __int64 v26; // r8
  char v27; // r14
  unsigned int *v28; // r9
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // r10
  unsigned int *v31; // r9
  unsigned __int64 v32; // r11
  unsigned __int64 v33; // r9
  unsigned int *v34; // r11
  unsigned __int64 v35; // r15
  unsigned __int64 v36; // r10
  __int64 v37; // r8
  unsigned __int64 v38; // r8
  unsigned int *v39; // r9
  unsigned __int64 v40; // r10
  unsigned __int64 v41; // r11
  unsigned __int64 v42; // rdi
  __int64 v43; // r8
  unsigned __int64 v44; // r8
  unsigned int *v45; // r9
  __int64 v46; // rdi
  __int64 v47; // r8
  unsigned __int64 v48; // r8
  unsigned int *v49; // r10
  unsigned __int64 v50; // rcx
  size_t v51; // rdi
  void *v52; // rax
  char *v53; // rbx
  __int64 typographic_features; // rax
  int v55; // edx
  __int64 v56; // r15
  __int64 v57; // rax
  char *v58; // rbx
  char *v59; // r15
  __int64 v60; // rdi
  int v61; // r12d
  unsigned __int64 v62; // r14
  __int64 v63; // rdx
  __int64 v64; // rcx
  unsigned __int64 v65; // r15
  unsigned __int64 v66; // r12
  __int64 v67; // rax
  __int64 v68; // rdi
  unsigned __int64 v69; // rdi
  unsigned __int64 v70; // r12
  __int64 v71; // rax
  __int64 v72; // rdi
  __int64 v73; // rax
  __int64 v74; // r8
  unsigned __int64 v75; // rcx
  unsigned __int64 v76; // r10
  bool v77; // cf
  __int64 v78; // r10
  unsigned __int64 v79; // r15
  __int64 v80; // r15
  int v81; // r9d
  LPVOID v82; // rdx
  unsigned __int64 v83; // rcx
  unsigned __int64 v84; // rax
  unsigned __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // r9
  __int64 v88; // r13
  unsigned __int64 v89; // r13
  unsigned __int64 v90; // rax
  __int64 v91; // r12
  _QWORD *v92; // rdx
  int v93; // eax
  unsigned __int64 v94; // rbx
  unsigned __int64 v95; // r14
  __int64 v96; // rdi
  __int64 v97; // r15
  _DWORD *v98; // rcx
  size_t v99; // r13
  _QWORD *v100; // rbx
  unsigned __int64 v101; // rdi
  unsigned __int64 v102; // r14
  unsigned __int64 v103; // rbx
  __int64 v104; // rdi
  unsigned __int64 v105; // r14
  unsigned __int64 v106; // rbx
  __int64 v107; // rax
  __int64 v108; // rax
  unsigned __int64 v109; // rdx
  unsigned __int64 v110; // rdx
  unsigned __int64 v111; // rdx
  unsigned __int64 v112; // rdx
  int v113; // xmm0_4
  int v114; // xmm1_4
  __int64 v115; // rdx
  int v116; // r8d
  int v117; // r9d
  __int16 v118; // r10
  int v119; // r11d
  _QWORD *v120; // rdi
  __int64 v121; // rsi
  __int64 v122; // r12
  __int64 v123; // r15
  void *v124; // r13
  int glyph_placements; // eax
  int v126; // ecx
  __int64 v127; // rdi
  void *v128; // rdi
  HANDLE v129; // rax
  void *v130; // rdi
  HANDLE v131; // rax
  void *v132; // rdi
  HANDLE v133; // rax
  void *v134; // rbx
  HANDLE v135; // rax
  HANDLE v136; // rax
  char v137; // bl
  __int64 v138; // r15
  int v139; // r12d
  int v140; // r13d
  char v141; // r14
  __int64 v142; // rdi
  __int64 v143; // rcx
  __int128 v144; // xmm1
  __int64 v145; // rcx
  unsigned __int64 v146; // rdx
  __int64 v147; // r10
  char v148; // r9
  char v149; // bl
  char v150; // dl
  int v151; // xmm0_4
  int v152; // xmm1_4
  float v153; // xmm2_4
  char v154; // r15
  _OWORD *v155; // r8
  __int64 v156; // r11
  __int64 v157; // r12
  __int64 v158; // rax
  __int64 v159; // r11
  __int64 v160; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v162; // rax
  void *v163; // rdi
  HANDLE v164; // rax
  char **v165; // r8
  LPVOID v166; // [rsp+40h] [rbp-40h]
  LPVOID v167; // [rsp+88h] [rbp+8h]
  __int64 v168; // [rsp+B0h] [rbp+30h]
  unsigned __int64 v169; // [rsp+F8h] [rbp+78h] BYREF
  unsigned __int64 v170; // [rsp+100h] [rbp+80h] BYREF
  unsigned __int64 v171; // [rsp+108h] [rbp+88h] BYREF
  __int64 v172; // [rsp+110h] [rbp+90h] BYREF
  __int64 v173; // [rsp+118h] [rbp+98h] BYREF
  LPVOID v174; // [rsp+120h] [rbp+A0h]
  int v175[2]; // [rsp+128h] [rbp+A8h] BYREF
  __int64 v176; // [rsp+130h] [rbp+B0h]
  _QWORD *v177; // [rsp+138h] [rbp+B8h]
  __int128 v178; // [rsp+140h] [rbp+C0h] BYREF
  _OWORD v179[2]; // [rsp+150h] [rbp+D0h]
  __int64 v180; // [rsp+178h] [rbp+F8h] BYREF
  LPVOID v181; // [rsp+180h] [rbp+100h]
  __int64 v182; // [rsp+188h] [rbp+108h]
  __int64 v183; // [rsp+190h] [rbp+110h] BYREF
  LPVOID v184; // [rsp+198h] [rbp+118h]
  __int64 v185; // [rsp+1A0h] [rbp+120h]
  __int64 v186; // [rsp+1A8h] [rbp+128h] BYREF
  __int64 v187; // [rsp+1B0h] [rbp+130h]
  __int64 v188; // [rsp+1B8h] [rbp+138h]
  __int128 v189; // [rsp+1C0h] [rbp+140h]
  _BYTE v190[30]; // [rsp+1D0h] [rbp+150h]
  char v191; // [rsp+1EEh] [rbp+16Eh]
  char v192; // [rsp+1EFh] [rbp+16Fh]
  __int64 v193; // [rsp+1F0h] [rbp+170h]
  __int64 v194; // [rsp+1F8h] [rbp+178h]
  __int64 v195; // [rsp+200h] [rbp+180h]
  _QWORD *v196; // [rsp+208h] [rbp+188h]
  __int64 v197; // [rsp+210h] [rbp+190h] BYREF
  LPVOID v198; // [rsp+218h] [rbp+198h]
  __int64 v199; // [rsp+220h] [rbp+1A0h]
  unsigned __int64 v200; // [rsp+228h] [rbp+1A8h] BYREF
  unsigned __int64 v201; // [rsp+230h] [rbp+1B0h]
  __int64 v202; // [rsp+238h] [rbp+1B8h]
  __int64 v203; // [rsp+240h] [rbp+1C0h]
  __int64 v204; // [rsp+248h] [rbp+1C8h]
  LPVOID v205; // [rsp+250h] [rbp+1D0h]
  __int64 v206; // [rsp+258h] [rbp+1D8h]
  __int64 v207; // [rsp+260h] [rbp+1E0h] BYREF
  LPVOID lpMem; // [rsp+268h] [rbp+1E8h]
  __int64 v209; // [rsp+270h] [rbp+1F0h]
  __int64 v210; // [rsp+278h] [rbp+1F8h]
  _QWORD *v211; // [rsp+280h] [rbp+200h]
  LPVOID v212; // [rsp+288h] [rbp+208h]
  int v213[2]; // [rsp+290h] [rbp+210h]
  __int64 nominal_glyph_ids; // [rsp+298h] [rbp+218h]
  _QWORD *v215; // [rsp+2A0h] [rbp+220h]
  __int64 v216; // [rsp+2A8h] [rbp+228h]
  __int64 v217; // [rsp+2B0h] [rbp+230h]
  int v218[2]; // [rsp+2B8h] [rbp+238h]
  LPVOID v219; // [rsp+2C0h] [rbp+240h]
  unsigned __int8 v220; // [rsp+2CFh] [rbp+24Fh]
  __int64 v221; // [rsp+2D0h] [rbp+250h]

  v221 = -2;
  v7 = a1;
  if ( !a4 )
  {
    v9 = a1[55];
    v10 = 0;
    if ( v9 )
      goto LABEL_4;
LABEL_32:
    core::panicking::panic_bounds_check(a4, v9, &off_1803374B8);
  }
  v8 = a4 - 1;
  v9 = v7[55];
  if ( a4 - 1 >= v9 )
    core::panicking::panic_bounds_check(v8, v7[55], &off_1803374B8);
  v10 = *(unsigned int *)(v7[54] + 80 * v8 + 72);
  if ( a4 >= v9 )
    goto LABEL_32;
LABEL_4:
  v11 = v7[54];
  v12 = 80 * a4;
  v13 = *(unsigned int *)(v11 + 80 * a4 + 72);
  if ( v10 >= a2 && a3 >= v13 )
    return layout::copy_shaping_run_to_line(v7 + 53, a4);
  v16 = a2;
  if ( v10 > a2 )
    v16 = v10;
  v17 = a3;
  if ( v13 < a3 )
    v17 = *(unsigned int *)(v11 + 80 * a4 + 72);
  v217 = v11 + v12;
  v18 = v7[62];
  v19 = v7[63];
  if ( !*(_BYTE *)(v11 + v12 + 64) )
  {
    v220 = *(_BYTE *)(v217 + 65);
    if ( !(v220 | (v17 <= v16)) )
    {
      v20 = v7[65];
      v21 = v7[66];
      if ( v10 < a2 )
      {
        if ( v16 - 1 >= v21 )
          core::panicking::panic_bounds_check(v16 - 1, v7[66], &off_1803395A0);
        if ( (*(_BYTE *)(v20 + 2 * v16 - 2) & 4) == 0 )
          goto LABEL_19;
      }
      if ( a3 < v13 )
      {
        if ( v17 - 1 >= v21 )
          core::panicking::panic_bounds_check(v17 - 1, v7[66], &off_1803395B8);
        if ( (*(_BYTE *)(v20 + 2 * v17 - 2) & 4) == 0 )
        {
LABEL_19:
          if ( !__OFSUB__(0, v7[89]) )
          {
            v19 = v7[91];
            v18 = v7[90];
          }
          if ( v17 > v7[2] )
            core::panicking::panic(
              "assertion failed: new_text_range.end <= ro.text.len() &&\n    new_text_range.start < new_text_range.end",
              102,
              &off_1803395D0);
          v22 = v7[39];
          v23 = v7[40];
          v24 = v23 - 1;
          if ( v23 - 1 >= v22 )
          {
            v23 = 0;
          }
          else
          {
            v25 = v7[38];
            if ( v16 < *(unsigned int *)(v25 + 120 * v24 + 112) )
            {
              if ( v23 == 1 )
              {
                v24 = 0;
                goto LABEL_42;
              }
              v23 -= 2LL;
              if ( v23 >= v22 )
                goto LABEL_269;
              if ( v16 >= *(unsigned int *)(v25 + 120 * v23 + 112) )
                goto LABEL_42;
              v26 = v23;
              v23 = 0;
LABEL_35:
              if ( v23 < v26 )
              {
                v28 = (unsigned int *)(120 * v23 + v7[38] + 112);
                v24 = v23;
                while ( v24 < v22 )
                {
                  if ( v16 < *v28 )
                    goto LABEL_42;
                  ++v24;
                  v28 += 30;
                  if ( v26 == v24 )
                  {
                    v24 = v26;
                    goto LABEL_42;
                  }
                }
LABEL_267:
                if ( v23 <= v22 )
                  v23 = v22;
LABEL_269:
                core::panicking::panic_bounds_check(v23, v22, &off_1803374B8);
              }
              v24 = v23;
LABEL_42:
              v7[40] = v24;
              v29 = v17 - 1;
              v30 = v24 - 1;
              v31 = (unsigned int *)v7[38];
              v219 = v31;
              if ( v24 - 1 >= v22 )
              {
                v33 = 0;
                v23 = v22;
              }
              else
              {
                v32 = v31[30 * v30 + 28];
                v23 = v22;
                v33 = v24;
                if ( v29 < v32 )
                {
                  if ( v24 == 1 )
                  {
                    v30 = 0;
                    goto LABEL_56;
                  }
                  v23 = v24 - 2;
                  if ( v24 - 2 >= v22 )
                    goto LABEL_269;
                  if ( v29 >= *((unsigned int *)v219 + 30 * v23 + 28) )
                    goto LABEL_56;
                  v33 = 0;
                }
              }
              if ( v33 < v23 )
              {
                v34 = (unsigned int *)((char *)v219 + 120 * v33 + 112);
                v30 = v33;
                while ( v30 < v22 )
                {
                  if ( v29 < *v34 )
                    goto LABEL_56;
                  ++v30;
                  v34 += 30;
                  if ( v23 == v30 )
                  {
                    v30 = v23;
                    goto LABEL_56;
                  }
                }
                if ( v33 <= v22 )
                  v33 = v22;
                v165 = &off_1803374B8;
LABEL_275:
                core::panicking::panic_bounds_check(v33, v22, v165);
              }
              v30 = v33;
LABEL_56:
              v7[40] = v30;
              if ( v30 + 1 < v24 )
                core::slice::index::slice_index_order_fail(v24, v30 + 1, &off_1803395E8);
              if ( v30 >= v22 )
                core::slice::index::slice_end_index_len_fail(v30 + 1, v22, &off_1803395E8);
              v35 = v30 + 1 - v24;
              if ( !v35 )
                core::panicking::panic_bounds_check(0, 0, &off_180339600);
              v22 = v7[51];
              v23 = v7[52];
              v36 = v23 - 1;
              if ( v23 - 1 >= v22 )
              {
                v23 = 0;
              }
              else
              {
                v37 = v7[50];
                if ( v16 < *(unsigned int *)(v37 + 32 * v36 + 24) )
                {
                  if ( v23 == 1 )
                  {
                    v33 = 0;
                    goto LABEL_78;
                  }
                  v23 -= 2LL;
                  if ( v23 >= v22 )
                    goto LABEL_269;
                  v33 = v36;
                  if ( v16 >= *(unsigned int *)(v37 + 32 * v23 + 24) )
                  {
LABEL_78:
                    v7[52] = v33;
                    if ( v33 >= v22 )
                    {
                      v165 = &off_180339618;
                      goto LABEL_275;
                    }
                    v210 = v7[50] + 32 * v33;
                    v22 = v7[47];
                    v23 = v7[48];
                    v42 = v23 - 1;
                    if ( v23 - 1 >= v22 )
                    {
                      v23 = 0;
                    }
                    else
                    {
                      v43 = v7[46];
                      if ( v16 < *(unsigned int *)(v43 + 32 * v42 + 24) )
                      {
                        if ( v23 == 1 )
                        {
                          v42 = 0;
                          goto LABEL_94;
                        }
                        v23 -= 2LL;
                        if ( v23 >= v22 )
                          goto LABEL_269;
                        if ( v16 >= *(unsigned int *)(v43 + 32 * v23 + 24) )
                        {
LABEL_94:
                          v7[48] = v42;
                          if ( v42 >= v22 )
                            core::panicking::panic_bounds_check(v42, v22, &off_180339630);
                          v46 = v7[46] + 32 * v42;
                          v22 = v7[43];
                          v23 = v7[44];
                          v33 = v23 - 1;
                          if ( v23 - 1 >= v22 )
                          {
                            v23 = 0;
                          }
                          else
                          {
                            v47 = v7[42];
                            if ( v16 < *(unsigned int *)(v47 + 12 * v33 + 8) )
                            {
                              if ( v23 == 1 )
                              {
                                v33 = 0;
                                goto LABEL_110;
                              }
                              v23 -= 2LL;
                              if ( v23 >= v22 )
                                goto LABEL_269;
                              if ( v16 >= *(unsigned int *)(v47 + 12 * v23 + 8) )
                              {
LABEL_110:
                                v7[44] = v33;
                                if ( v33 >= v22 )
                                {
                                  v165 = &off_180339648;
                                  goto LABEL_275;
                                }
                                v216 = v46;
                                v50 = 0;
                                v193 = v17 - v16;
                                if ( v17 >= v16 )
                                  v50 = v17 - v16;
                                if ( v17 > v19 )
                                  core::slice::index::slice_end_index_len_fail(v17, v19, &off_180339660);
                                v206 = v7[42] + 12 * v33;
                                v194 = v7[1] + 2 * v16;
                                v212 = (LPVOID)v50;
                                v51 = 2 * v50;
                                v52 = (void *)std::sys::alloc::windows::process_heap_alloc(0, 2 * v50);
                                if ( !v52 )
                                  alloc::alloc::handle_alloc_error(2, v51);
                                v53 = (char *)v219 + 120 * v24;
                                v205 = v52;
                                memset_0(v52, 0, v51);
                                v183 = 0;
                                v184 = (LPVOID)8;
                                v185 = 0;
                                v180 = 0;
                                v181 = (LPVOID)4;
                                v182 = 0;
                                v197 = 0;
                                v198 = (LPVOID)4;
                                v199 = 0;
                                v219 = v53;
                                typographic_features = layout::get_typographic_features(
                                                         v16,
                                                         v17,
                                                         (_DWORD)v53,
                                                         v35,
                                                         (__int64)&v183,
                                                         (__int64)&v180,
                                                         (__int64)&v197);
                                if ( v55 )
                                {
                                  v186 = typographic_features;
                                  LODWORD(v187) = v55;
                                }
                                else
                                {
                                  v56 = v185;
                                  if ( v185 )
                                  {
                                    v57 = std::sys::alloc::windows::process_heap_alloc(0, 8 * v185);
                                    if ( !v57 )
                                      alloc::alloc::handle_alloc_error(8, 8 * v56);
                                  }
                                  else
                                  {
                                    v57 = 8;
                                  }
                                  v215 = v7 + 67;
                                  v219 = (char *)v219 + 16;
                                  v195 = v18 + 2 * v16;
                                  v207 = v56;
                                  lpMem = (LPVOID)v57;
                                  v209 = 0;
                                  v58 = (char *)v184;
                                  v59 = (char *)v184 + 16 * v56;
                                  v60 = 0;
                                  v174 = v184;
                                  while ( 1 )
                                  {
                                    v61 = 0;
                                    if ( v58 == v59 )
                                      break;
                                    if ( v60 == v207 )
                                    {
                                      alloc::raw_vec::RawVec_dwrite::font_collection::IDWriteFontCollection_alloc::alloc::Global_::grow_one_dwrite::font_collection::IDWriteFontCollection_alloc::alloc::Global_(
                                        &v207,
                                        &off_1803397F8);
                                      v57 = (__int64)lpMem;
                                    }
                                    LOBYTE(v61) = v58 != v59;
                                    *(_QWORD *)(v57 + 8 * v60++) = v58;
                                    v209 = v60;
                                    v58 += (unsigned int)(16 * v61);
                                  }
                                  v62 = (unsigned __int64)v212 + ((unsigned __int64)v212 >> 1) + 16;
                                  if ( (unsigned __int64)v212 > v62 )
                                    v62 = (unsigned __int64)v212;
                                  if ( v62 >= 0xFFFF )
                                    v62 = 0xFFFF;
                                  layout::TextLayoutGlyphs::ensure_free_glyph_capacity(v215, v62);
                                  v211 = v7 + 80;
                                  v177 = v7 + 73;
                                  v196 = v7 + 76;
                                  *(_QWORD *)v218 = v210 + 8;
                                  v203 = 3;
                                  v201 = v17;
                                  while ( 1 )
                                  {
                                    v63 = v7[75];
                                    v173 = v63;
                                    if ( v7[80] != v63 )
                                    {
                                      *(_QWORD *)&v178 = 0;
                                      core::panicking::assert_failed_usize_usize_(v211, &v173, &v178, &off_180339678);
                                    }
                                    v172 = v7[78];
                                    if ( v63 != v172 )
                                    {
                                      *(_QWORD *)&v178 = 0;
                                      core::panicking::assert_failed_usize_usize_(v211, &v172, &v178, &off_180339690);
                                    }
                                    v64 = v7[73];
                                    v204 = v7[79];
                                    v65 = v63 + v62;
                                    v66 = v63 + v62;
                                    nominal_glyph_ids = v63;
                                    v67 = v63;
                                    if ( v62 > v64 - v63 )
                                    {
                                      alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
                                        (_DWORD)v177,
                                        nominal_glyph_ids,
                                        v62,
                                        2,
                                        2);
                                      v67 = v7[75];
                                      v66 = v67 + v62;
                                    }
                                    v68 = v7[74];
                                    memset_0((void *)(v68 + 2 * v67), 0, 2 * v62 - 2);
                                    *(_WORD *)(v68 + 2 * v66 - 2) = 0;
                                    v69 = v7[78];
                                    v7[75] = v66;
                                    v70 = v65 - v69;
                                    if ( v65 > v69 )
                                    {
                                      if ( v70 > *v196 - v69 )
                                      {
                                        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
                                          (_DWORD)v196,
                                          v69,
                                          v65 - v69,
                                          2,
                                          2);
                                        v69 = v7[78];
                                      }
                                      memset_0((void *)(v7[77] + 2 * v69), 0, 2 * v70);
                                      v65 = v70 + v69;
                                    }
                                    v7[78] = v65;
                                    if ( !**(_QWORD **)v218 )
                                      core::option::unwrap_failed(&off_1803396A8);
                                    v71 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)v218 + 296LL))(**(_QWORD **)v218);
                                    v72 = v216;
                                    if ( !v71 )
                                      core::option::unwrap_failed(&off_180336098);
                                    v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 144LL))(v71);
                                    if ( !v73 )
                                      core::panicking::panic(
                                        "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\d"
                                        "writecore-copy\\rust\\interop_utils\\src\\lib.rs",
                                        32,
                                        &off_1803431B8);
                                    v74 = *(_QWORD *)v72;
                                    if ( *(_QWORD *)v72 )
                                      v74 = v72;
                                    v75 = v7[80];
                                    v76 = v7[75];
                                    v77 = v76 < v75;
                                    v78 = v76 - v75;
                                    if ( v77 )
                                      core::slice::index::slice_start_index_len_fail(v75, v7[75], &off_1803397E0);
                                    v79 = v7[78];
                                    v77 = v79 < v75;
                                    v80 = v79 - v75;
                                    if ( v77 )
                                      core::slice::index::slice_start_index_len_fail(v75, v7[78], &off_1803397C8);
                                    LOBYTE(v202) = *(_BYTE *)(v72 + 20);
                                    v81 = *(_DWORD *)(v72 + 8);
                                    LOWORD(v213[0]) = *(_WORD *)v206;
                                    shaping_cache::get_glyphs(
                                      (int)v175,
                                      v73,
                                      a5,
                                      v218[0],
                                      v74,
                                      v194,
                                      v193,
                                      v202,
                                      v81 & 1,
                                      v213[0],
                                      *(_DWORD *)(v206 + 4),
                                      (__int64)v219,
                                      (__int64)lpMem,
                                      v209,
                                      (__int64)v198,
                                      v199,
                                      v62,
                                      v195,
                                      v193,
                                      v205,
                                      (__int64)v212,
                                      2 * v75 + v7[74],
                                      v78,
                                      v7[77] + 2 * v75,
                                      v80);
                                    v17 = v201;
                                    if ( v175[0] != 1 )
                                    {
                                      v88 = v7[80];
                                      nominal_glyph_ids = v176;
                                      v89 = v176 + v88;
                                      v90 = v7[75];
                                      if ( v89 <= v90 )
                                      {
                                        v7[75] = v89;
                                        v90 = v89;
                                      }
                                      v91 = v210;
                                      v92 = v215;
                                      if ( v89 <= v7[78] )
                                        v7[78] = v89;
                                      goto LABEL_169;
                                    }
                                    v82 = v212;
                                    if ( (unsigned int)(v175[1] + 3) >= 2 )
                                      break;
                                    v83 = v7[75];
                                    v84 = v7[80];
                                    if ( v84 <= v83 )
                                    {
                                      v7[75] = v84;
                                      v83 = v84;
                                    }
                                    v85 = v7[78];
                                    v86 = v203;
                                    if ( v84 <= v85 )
                                    {
                                      v7[78] = v84;
                                      v85 = v84;
                                    }
                                    v171 = v83;
                                    if ( v84 != v83 )
                                    {
                                      *(_QWORD *)&v178 = 0;
                                      core::panicking::assert_failed_usize_usize_(v211, &v171, &v178, &off_1803396C0);
                                    }
                                    v170 = v85;
                                    if ( v84 != v85 )
                                    {
                                      *(_QWORD *)&v178 = 0;
                                      core::panicking::assert_failed_usize_usize_(v211, &v170, &v178, &off_1803396D8);
                                    }
                                    v87 = v86 - 1;
                                    if ( !v87 )
                                    {
                                      layout::TextLayoutGlyphs::ensure_free_glyph_capacity(v215, v82);
                                      if ( !**(_QWORD **)v218 )
                                        core::option::unwrap_failed(&off_1803396F0);
                                      nominal_glyph_ids = layout::get_nominal_glyph_ids(
                                                            **(_QWORD **)v218,
                                                            v194,
                                                            v193,
                                                            (_DWORD)v177,
                                                            (__int64)v196,
                                                            v195,
                                                            v193);
                                      v90 = v7[75];
                                      v89 = nominal_glyph_ids + v7[80];
                                      v91 = v210;
                                      v92 = v215;
LABEL_169:
                                      v200 = v89;
                                      v169 = v90;
                                      if ( v89 != v90 )
                                      {
                                        *(_QWORD *)&v178 = 0;
                                        core::panicking::assert_failed_usize_usize_(&v200, &v169, &v178, &off_180339708);
                                      }
                                      *(_QWORD *)v175 = v7[78];
                                      if ( v89 != *(_QWORD *)v175 )
                                      {
                                        *(_QWORD *)&v178 = 0;
                                        core::panicking::assert_failed_usize_usize_(&v200, v175, &v178, &off_180339720);
                                      }
                                      v94 = v7[72];
                                      v95 = v89 - v94;
                                      if ( v89 <= v94 )
                                      {
                                        v101 = v89;
                                      }
                                      else
                                      {
                                        v96 = v7[72];
                                        if ( v95 > v7[70] - v94 )
                                        {
                                          alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
                                            (_DWORD)v7 + 560,
                                            v94,
                                            v89 - v94,
                                            4,
                                            4);
                                          v96 = v7[72];
                                          v91 = v210;
                                          v92 = v215;
                                        }
                                        v97 = v7[71];
                                        v98 = (_DWORD *)(v97 + 4 * v96);
                                        if ( v95 >= 2 )
                                        {
                                          v99 = 4 * (~v94 + v89);
                                          v100 = v92;
                                          memset_0(v98, 0, v99);
                                          v92 = v100;
                                          v98 = (_DWORD *)(v97 + 4 * (v96 + v95) - 4);
                                          v96 = v95 + v96 - 1;
                                        }
                                        *v98 = 0;
                                        v101 = v96 + 1;
                                        v89 = v200;
                                      }
                                      v7[72] = v101;
                                      v102 = v7[69];
                                      v103 = v89 - v102;
                                      if ( v89 <= v102 )
                                      {
                                        v105 = v89;
                                        v104 = v216;
                                      }
                                      else
                                      {
                                        v104 = v216;
                                        if ( v103 > *v92 - v102 )
                                        {
                                          alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
                                            (_DWORD)v92,
                                            v102,
                                            v89 - v102,
                                            4,
                                            8);
                                          v102 = v7[69];
                                          v89 = v200;
                                          v91 = v210;
                                          v104 = v216;
                                        }
                                        memset_0((void *)(v7[68] + 8 * v102), 0, 8 * v103);
                                        v105 = v103 + v102;
                                      }
                                      v7[69] = v105;
                                      if ( !**(_QWORD **)v218 )
                                        core::option::unwrap_failed(&off_180339738);
                                      v106 = v7[80];
                                      v107 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)v218 + 296LL))(**(_QWORD **)v218);
                                      if ( !v107 )
                                        core::option::unwrap_failed(&off_180336098);
                                      v108 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v107 + 144LL))(v107);
                                      if ( !v108 )
                                        core::panicking::panic(
                                          "assertion failed: !ptr.is_null()d:\\os\\src\\onecoreuap\\windows\\directwrite\\"
                                          "dwritecore-copy\\rust\\interop_utils\\src\\lib.rs",
                                          32,
                                          &off_1803431B8);
                                      v202 = v89 - v106;
                                      if ( v89 < v106 )
                                        core::slice::index::slice_index_order_fail(v106, v89, &off_180339750);
                                      v109 = v7[75];
                                      if ( v89 > v109 )
                                        core::slice::index::slice_end_index_len_fail(v89, v109, &off_180339750);
                                      v110 = v7[78];
                                      if ( v89 > v110 )
                                        core::slice::index::slice_end_index_len_fail(v89, v110, &off_180339768);
                                      v111 = v7[72];
                                      if ( v89 > v111 )
                                        core::slice::index::slice_end_index_len_fail(v89, v111, &off_180339780);
                                      *(_QWORD *)v213 = v108;
                                      v112 = v7[69];
                                      v216 = v89;
                                      if ( v89 > v112 )
                                        core::slice::index::slice_end_index_len_fail(v216, v112, &off_180339798);
                                      v113 = *(_DWORD *)(v91 + 16);
                                      v114 = *((_DWORD *)v7 + 55);
                                      v115 = (__int64)(v7 + 28);
                                      v116 = *((_DWORD *)v7 + 64);
                                      LOBYTE(v203) = *(_BYTE *)(v104 + 20);
                                      v117 = *(_DWORD *)(v104 + 8);
                                      v118 = *(_WORD *)v206;
                                      v119 = *(_DWORD *)(v206 + 4);
                                      v120 = v7;
                                      v121 = v7[74] + 2 * v106;
                                      v122 = v120[77] + 2 * v106;
                                      v123 = v120[71];
                                      v206 = 4 * v106;
                                      v204 = v106;
                                      v124 = (void *)(v120[68] + 8 * v106);
                                      v168 = v121;
                                      v7 = v120;
                                      v167 = v219;
                                      v166 = v212;
                                      v219 = v198;
                                      v212 = lpMem;
                                      glyph_placements = shaping_cache::get_glyph_placements(
                                                           v213[0],
                                                           a5,
                                                           v218[0],
                                                           v194,
                                                           v193,
                                                           v195,
                                                           v193,
                                                           (__int64)v205,
                                                           (__int64)v166,
                                                           v113,
                                                           v114,
                                                           v115,
                                                           v116,
                                                           v203,
                                                           v117 & 1,
                                                           v118,
                                                           v119,
                                                           (__int64)v167,
                                                           (__int64)lpMem,
                                                           v209,
                                                           (__int64)v198,
                                                           v199,
                                                           v168,
                                                           v202,
                                                           v122,
                                                           v202,
                                                           (void *)(4 * v106 + v123),
                                                           v202,
                                                           v124,
                                                           v202);
                                      v17 = v201;
                                      switch ( glyph_placements )
                                      {
                                        case -4:
                                          v126 = -2003283968;
                                          goto LABEL_204;
                                        case -3:
                                        case -2:
                                          v126 = -2147024774;
                                          goto LABEL_204;
                                        case -1:
                                          v126 = -2147024809;
                                          goto LABEL_204;
                                        case 0:
                                          v127 = *(_QWORD *)(v217 + 16);
                                          if ( v127 )
                                            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v127 + 8LL))(*(_QWORD *)(v217 + 16));
                                          else
                                            v127 = 0;
                                          v145 = v216;
                                          v146 = v7[72];
                                          *(_QWORD *)v218 = v127;
                                          if ( v216 > v146 )
                                            core::slice::index::slice_end_index_len_fail(v216, v146, &off_1803397B0);
                                          v147 = v217 + 24;
                                          *(_QWORD *)v213 = v217 + 48;
                                          v148 = *(_BYTE *)(v217 + 67);
                                          v149 = *(_BYTE *)(v217 + 68);
                                          v150 = *(_BYTE *)(v217 + 69);
                                          v151 = *(_DWORD *)(v217 + 40);
                                          v152 = *(_DWORD *)(v217 + 44);
                                          if ( v216 == v204 )
                                          {
                                            v153 = FLOAT_N0_0;
                                            v154 = *(_BYTE *)(v217 + 66);
                                            v155 = *(_OWORD **)v213;
                                          }
                                          else
                                          {
                                            v156 = v7[71];
                                            if ( (unsigned __int64)(v204 - v216) <= 0xFFFFFFFFFFFFFFF8uLL )
                                            {
                                              v153 = FLOAT_N0_0;
                                              v157 = 0;
                                              v154 = *(_BYTE *)(v217 + 66);
                                              do
                                              {
                                                v158 = v156 + 4 * v204 + 28;
                                                v153 = (float)((float)((float)((float)((float)((float)((float)(v153 + *(float *)(v158 + 4 * v157 - 28)) + *(float *)(v158 + 4 * v157 - 24))
                                                                                             + *(float *)(v158 + 4 * v157 - 20))
                                                                                     + *(float *)(v158 + 4 * v157 - 16))
                                                                             + *(float *)(v158 + 4 * v157 - 12))
                                                                     + *(float *)(v158 + 4 * v157 - 8))
                                                             + *(float *)(v158 + 4 * v157 - 4))
                                                     + *(float *)(v158 + 4 * v157);
                                                v157 += 8;
                                              }
                                              while ( (v202 & 0xFFFFFFFFFFFFFFF8uLL) != v157 );
                                            }
                                            else
                                            {
                                              v153 = FLOAT_N0_0;
                                              v157 = 0;
                                              v154 = *(_BYTE *)(v217 + 66);
                                            }
                                            v155 = *(_OWORD **)v213;
                                            if ( (v202 & 7) != 0 )
                                            {
                                              v159 = v206 + 4 * v157 + v156;
                                              v160 = 0;
                                              do
                                                v153 = v153 + *(float *)(v159 + 4 * v160++);
                                              while ( (v202 & 7) != v160 );
                                            }
                                          }
                                          v27 = *(_BYTE *)(v217 + 70);
                                          *v211 += nominal_glyph_ids;
                                          v186 = v204;
                                          v187 = v145;
                                          v188 = *(_QWORD *)v218;
                                          *(_QWORD *)&v189 = *(_QWORD *)v147;
                                          DWORD2(v189) = *(_DWORD *)(v147 + 8);
                                          *((float *)&v189 + 3) = v153;
                                          *(_DWORD *)v190 = v151;
                                          *(_DWORD *)&v190[4] = v152;
                                          *(_OWORD *)&v190[8] = *v155;
                                          v190[24] = 0;
                                          v190[25] = v220;
                                          v190[26] = v154;
                                          v190[27] = v148;
                                          v190[28] = v149;
                                          v190[29] = v150;
                                          v134 = v174;
                                          if ( v207 )
                                          {
                                            ProcessHeap = GetProcessHeap();
                                            HeapFree(ProcessHeap, 0, v212);
                                          }
                                          if ( v197 )
                                          {
                                            v162 = GetProcessHeap();
                                            HeapFree(v162, 0, v219);
                                          }
                                          if ( v180 )
                                          {
                                            v163 = v181;
                                            v164 = GetProcessHeap();
                                            HeapFree(v164, 0, v163);
                                          }
                                          if ( v183 )
                                            goto LABEL_217;
                                          goto LABEL_219;
                                        default:
                                          v126 = -2003283967;
                                          if ( glyph_placements == -101 )
                                            v126 = -2147467263;
LABEL_204:
                                          v186 = 0;
                                          LODWORD(v187) = v126;
                                          break;
                                      }
                                      goto LABEL_209;
                                    }
                                    v203 = v87;
                                    v62 = ((unsigned __int64)(3 * (v204 - nominal_glyph_ids)) >> 1) + 16;
                                    if ( v204 - nominal_glyph_ids > v62 )
                                      v62 = v204 - nominal_glyph_ids;
                                    if ( v62 >= 0xFFFF )
                                      v62 = 0xFFFF;
                                    layout::TextLayoutGlyphs::ensure_free_glyph_capacity(v215, v62);
                                  }
                                  v93 = -2003283967;
                                  if ( v175[1] <= -4 )
                                  {
                                    if ( v175[1] == -101 )
                                    {
                                      v93 = -2147467263;
                                    }
                                    else if ( v175[1] == -4 )
                                    {
                                      v93 = -2003283968;
                                    }
                                  }
                                  else if ( (unsigned int)(v175[1] + 3) >= 2 )
                                  {
                                    if ( v175[1] == -1 )
                                      v93 = -2147024809;
                                  }
                                  else
                                  {
                                    v93 = -2147024774;
                                  }
                                  v186 = 0;
                                  LODWORD(v187) = v93;
LABEL_209:
                                  if ( v207 )
                                  {
                                    v128 = lpMem;
                                    v129 = GetProcessHeap();
                                    HeapFree(v129, 0, v128);
                                  }
                                }
                                if ( v197 )
                                {
                                  v130 = v198;
                                  v131 = GetProcessHeap();
                                  HeapFree(v131, 0, v130);
                                }
                                if ( v180 )
                                {
                                  v132 = v181;
                                  v133 = GetProcessHeap();
                                  HeapFree(v133, 0, v132);
                                }
                                if ( v183 )
                                {
                                  v27 = 2;
                                  v134 = v184;
LABEL_217:
                                  v135 = GetProcessHeap();
                                  HeapFree(v135, 0, v134);
                                }
                                else
                                {
                                  v27 = 2;
                                }
LABEL_219:
                                v136 = GetProcessHeap();
                                HeapFree(v136, 0, v205);
                                if ( v27 != 2 )
                                  goto LABEL_220;
                                return v186;
                              }
                              v48 = v23;
                              v23 = 0;
LABEL_103:
                              if ( v23 >= v48 )
                              {
                                v33 = v23;
                              }
                              else
                              {
                                v49 = (unsigned int *)(v7[42] + 12 * v23 + 8);
                                v33 = v23;
                                do
                                {
                                  if ( v33 >= v22 )
                                    goto LABEL_267;
                                  if ( v16 < *v49 )
                                    goto LABEL_110;
                                  ++v33;
                                  v49 += 3;
                                }
                                while ( v48 != v33 );
                                v33 = v48;
                              }
                              goto LABEL_110;
                            }
                          }
                          v48 = v7[43];
                          goto LABEL_103;
                        }
                        v44 = v23;
                        v23 = 0;
LABEL_87:
                        if ( v23 >= v44 )
                        {
                          v42 = v23;
                        }
                        else
                        {
                          v45 = (unsigned int *)(32 * v23 + v7[46] + 24);
                          v42 = v23;
                          do
                          {
                            if ( v42 >= v22 )
                              goto LABEL_267;
                            if ( v16 < *v45 )
                              goto LABEL_94;
                            ++v42;
                            v45 += 8;
                          }
                          while ( v44 != v42 );
                          v42 = v44;
                        }
                        goto LABEL_94;
                      }
                    }
                    v44 = v7[47];
                    goto LABEL_87;
                  }
                  v38 = v23;
                  v23 = 0;
LABEL_67:
                  if ( v23 >= v38 )
                  {
                    v33 = v23;
                  }
                  else
                  {
                    v39 = (unsigned int *)(32 * v23 + v7[50] + 24);
                    v40 = v23;
                    while ( 1 )
                    {
                      if ( v40 >= v22 )
                        goto LABEL_267;
                      v41 = v40;
                      if ( v16 < *v39 )
                        break;
                      ++v40;
                      v39 += 8;
                      if ( v38 == v41 + 1 )
                      {
                        v33 = v38;
                        goto LABEL_78;
                      }
                    }
                    v33 = v40;
                  }
                  goto LABEL_78;
                }
              }
              v38 = v7[51];
              goto LABEL_67;
            }
          }
          v26 = v7[39];
          goto LABEL_35;
        }
      }
    }
  }
  if ( __OFSUB__(0, v7[89]) )
    core::option::unwrap_failed(&off_180339540);
  layout::split_shaping_run_simple((unsigned int)&v186, v217, v10, v13, v16, v17, v18, v19, v7[90], v7[91]);
  v27 = v191;
  if ( v191 == 2 )
    return v186;
LABEL_220:
  v137 = v27;
  v201 = v17;
  v138 = v186;
  v139 = v187;
  v140 = HIDWORD(v187);
  v217 = v188;
  v178 = v189;
  v179[0] = *(_OWORD *)v190;
  *(_OWORD *)((char *)v179 + 14) = *(_OWORD *)&v190[14];
  v141 = v192;
  v142 = v7[59];
  if ( v142 == v7[57] )
    alloc::raw_vec::RawVec_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_::grow_one_layout::run_list::Run_layout::layout_types::ShapingRun__alloc::alloc::Global_(
      v7 + 57,
      &off_180338A80);
  result = v7[58];
  v143 = 80 * v142;
  *(_QWORD *)(result + v143) = v138;
  *(_DWORD *)(result + v143 + 8) = v139;
  *(_DWORD *)(result + v143 + 12) = v140;
  *(_QWORD *)(result + v143 + 16) = v217;
  v144 = v179[0];
  *(_OWORD *)(result + v143 + 24) = v178;
  *(_OWORD *)(result + v143 + 40) = v144;
  *(_OWORD *)(result + v143 + 54) = *(_OWORD *)((char *)v179 + 14);
  *(_BYTE *)(result + v143 + 70) = v137;
  *(_BYTE *)(result + v143 + 71) = v141;
  *(_DWORD *)(result + v143 + 72) = v201;
  v7[59] = v142 + 1;
  return result;
}

```

## disassembly

```asm
0x18005a9a0  push    rbp
0x18005a9a1  push    r15
0x18005a9a3  push    r14
0x18005a9a5  push    r13
0x18005a9a7  push    r12
0x18005a9a9  push    rsi
0x18005a9aa  push    rdi
0x18005a9ab  push    rbx
0x18005a9ac  sub     rsp, 2D8h
0x18005a9b3  lea     rbp, [rsp+80h]
0x18005a9bb  mov     [rbp+290h+var_40], 0FFFFFFFFFFFFFFFEh
0x18005a9c6  mov     r10, r9
0x18005a9c9  mov     rax, r8
0x18005a9cc  mov     rsi, rcx
0x18005a9cf  test    r9, r9
0x18005a9d2  jz      loc_18005ABD5
0x18005a9d8  lea     rcx, [r10-1]
0x18005a9dc  mov     r9, [rsi+1B8h]
0x18005a9e3  cmp     rcx, r9
0x18005a9e6  jnb     loc_18005C25A
0x18005a9ec  mov     r8, [rsi+1B0h]
0x18005a9f3  lea     rcx, [rcx+rcx*4]
0x18005a9f7  shl     rcx, 4
0x18005a9fb  mov     r8d, [r8+rcx+48h]
0x18005aa00  cmp     r10, r9
0x18005aa03  jnb     loc_18005ABE8
0x18005aa09  mov     rcx, [rsi+1B0h]
0x18005aa10  lea     r11, [r10+r10*4]
0x18005aa14  shl     r11, 4
0x18005aa18  mov     r9d, [rcx+r11+48h]
0x18005aa1d  cmp     r8, rdx
0x18005aa20  jb      short loc_18005AA3E
0x18005aa22  cmp     rax, r9
0x18005aa25  jb      short loc_18005AA3E
0x18005aa27  add     rsi, 1A8h
0x18005aa2e  mov     rcx, rsi
0x18005aa31  mov     rdx, r10
0x18005aa34  call    layout__copy_shaping_run_to_line
0x18005aa39  jmp     loc_18005BCCA
0x18005aa3e  cmp     r8, rdx
0x18005aa41  mov     rdi, rdx
0x18005aa44  mov     r14, rdx
0x18005aa47  cmova   r14, r8
0x18005aa4b  cmp     r9, rax
0x18005aa4e  mov     r13, rax
0x18005aa51  cmovb   r13, r9
0x18005aa55  lea     rdx, [rcx+r11]
0x18005aa59  mov     [rbp+290h+var_60], rdx
0x18005aa60  mov     r12, [rsi+1F0h]
0x18005aa67  mov     rdx, [rsi+1F8h]
0x18005aa6e  cmp     byte ptr [rcx+r11+40h], 0
0x18005aa74  jnz     loc_18005AB6F
0x18005aa7a  mov     rcx, [rbp+290h+var_60]
0x18005aa81  movzx   r10d, byte ptr [rcx+41h]
0x18005aa86  cmp     r13, r14
0x18005aa89  setbe   cl
0x18005aa8c  mov     [rbp+290h+var_41], r10b
0x18005aa93  or      cl, r10b
0x18005aa96  jnz     loc_18005AB6F
0x18005aa9c  mov     r11, [rsi+208h]
0x18005aaa3  mov     r10, [rsi+210h]
0x18005aaaa  cmp     r8, rdi
0x18005aaad  jnb     short loc_18005AAC4
0x18005aaaf  lea     rcx, [r14-1]
0x18005aab3  cmp     rcx, r10
0x18005aab6  jnb     loc_18005C282
0x18005aabc  test    byte ptr [r11+r14*2-2], 4
0x18005aac2  jz      short loc_18005AAE6
0x18005aac4  cmp     rax, r9
0x18005aac7  jnb     loc_18005AB6F
0x18005aacd  lea     rcx, [r13-1]
0x18005aad1  cmp     rcx, r10
0x18005aad4  jnb     loc_18005C2D2
0x18005aada  test    byte ptr [r11+r13*2-2], 4
0x18005aae0  jnz     loc_18005AB6F
0x18005aae6  xor     eax, eax
0x18005aae8  cmp     rax, [rsi+2C8h]
0x18005aaef  jo      short loc_18005AAFF
0x18005aaf1  mov     rdx, [rsi+2D8h]
0x18005aaf8  mov     r12, [rsi+2D0h]
0x18005aaff  cmp     r13, [rsi+10h]
0x18005ab03  ja      loc_18005C062
0x18005ab09  mov     rax, [rsi+138h]
0x18005ab10  mov     rcx, [rsi+140h]
0x18005ab17  lea     rbx, [rcx-1]
0x18005ab1b  cmp     rbx, rax
0x18005ab1e  jnb     loc_18005ABFA
0x18005ab24  mov     r8, [rsi+130h]
0x18005ab2b  imul    r9, rbx, 78h ; 'x'
0x18005ab2f  mov     r9d, [r8+r9+70h]
0x18005ab34  cmp     r14, r9
0x18005ab37  jnb     loc_18005ABFC
0x18005ab3d  test    rbx, rbx
0x18005ab40  jz      loc_18005ADD2
0x18005ab46  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18005ab4a  cmp     rcx, rax
0x18005ab4d  jnb     loc_18005C23D
0x18005ab53  imul    r9, rcx, 78h ; 'x'
0x18005ab57  mov     r8d, [r8+r9+70h]
0x18005ab5c  cmp     r14, r8
0x18005ab5f  jnb     loc_18005AC45
0x18005ab65  mov     r8, rcx
0x18005ab68  xor     ecx, ecx
0x18005ab6a  jmp     loc_18005ABFF
0x18005ab6f  xor     eax, eax
0x18005ab71  cmp     rax, [rsi+2C8h]
0x18005ab78  jo      loc_18005BF31
0x18005ab7e  movups  xmm0, xmmword ptr [rsi+2D0h]
0x18005ab85  movups  xmmword ptr [rsp+310h+var_2D0], xmm0
0x18005ab8a  mov     qword ptr [rsp+310h+var_2D8], rdx
0x18005ab8f  mov     [rsp+310h+var_2E0], r12
0x18005ab94  mov     [rsp+310h+var_2E8], r13
0x18005ab99  mov     [rsp+310h+var_2F0], r14
0x18005ab9e  lea     rcx, [rbp+290h+var_168]
0x18005aba5  mov     rdx, [rbp+290h+var_60]
0x18005abac  call    layout__split_shaping_run_simple
0x18005abb1  movzx   r14d, [rbp+290h+var_122]
0x18005abb9  cmp     r14b, 2
0x18005abbd  jnz     loc_18005BBDD
0x18005abc3  mov     rax, [rbp+290h+var_168]
0x18005abca  mov     edx, dword ptr [rbp+290h+var_160]
0x18005abd0  jmp     loc_18005BCCC
0x18005abd5  mov     r9, [rsi+1B8h]
0x18005abdc  xor     r8d, r8d
0x18005abdf  cmp     r10, r9
0x18005abe2  jb      loc_18005AA09
0x18005abe8  lea     r8, off_1803374B8; "rust\\layout\\src\\run_list.rs"
0x18005abef  mov     rcx, r10
0x18005abf2  mov     rdx, r9
0x18005abf5  call    core__panicking__panic_bounds_check
0x18005abfa  xor     ecx, ecx
0x18005abfc  mov     r8, rax
0x18005abff  cmp     rcx, r8
0x18005ac02  jnb     short loc_18005AC42
0x18005ac04  mov     r9, [rsi+130h]
0x18005ac0b  imul    r10, rcx, 78h ; 'x'
0x18005ac0f  add     r9, r10
0x18005ac12  add     r9, 70h ; 'p'
0x18005ac16  mov     rbx, rcx
0x18005ac19  nop     dword ptr [rax+00000000h]
0x18005ac20  cmp     rbx, rax
0x18005ac23  jnb     loc_18005C236
0x18005ac29  mov     r10d, [r9]
0x18005ac2c  cmp     r14, r10
0x18005ac2f  jb      short loc_18005AC45
0x18005ac31  inc     rbx
0x18005ac34  add     r9, 78h ; 'x'
0x18005ac38  cmp     r8, rbx
0x18005ac3b  jnz     short loc_18005AC20
0x18005ac3d  mov     rbx, r8
0x18005ac40  jmp     short loc_18005AC45
0x18005ac42  mov     rbx, rcx
0x18005ac45  mov     [rsi+140h], rbx
0x18005ac4c  lea     r8, [r13-1]
0x18005ac50  lea     r10, [rbx-1]
0x18005ac54  mov     r9, [rsi+130h]
0x18005ac5b  cmp     r10, rax
0x18005ac5e  mov     [rbp+290h+var_50], r9
0x18005ac65  jnb     short loc_18005ACAB
0x18005ac67  imul    rcx, r10, 78h ; 'x'
0x18005ac6b  mov     r11d, [r9+rcx+70h]
0x18005ac70  mov     rcx, rax
0x18005ac73  mov     r9, rbx
0x18005ac76  cmp     r8, r11
0x18005ac79  jnb     short loc_18005ACB1
0x18005ac7b  test    r10, r10
0x18005ac7e  jz      loc_18005ADD9
0x18005ac84  lea     rcx, [rbx-2]
0x18005ac88  cmp     rcx, rax
0x18005ac8b  jnb     loc_18005C23D
0x18005ac91  imul    r9, rcx, 78h ; 'x'
0x18005ac95  mov     r11, [rbp+290h+var_50]
0x18005ac9c  mov     r9d, [r11+r9+70h]
0x18005aca1  cmp     r8, r9
0x18005aca4  jnb     short loc_18005ACF5
0x18005aca6  xor     r9d, r9d
0x18005aca9  jmp     short loc_18005ACB1
0x18005acab  xor     r9d, r9d
0x18005acae  mov     rcx, rax
0x18005acb1  cmp     r9, rcx
0x18005acb4  jnb     short loc_18005ACF2
0x18005acb6  imul    r10, r9, 78h ; 'x'
0x18005acba  mov     r11, [rbp+290h+var_50]
0x18005acc1  add     r11, r10
0x18005acc4  add     r11, 70h ; 'p'
0x18005acc8  mov     r10, r9
0x18005accb  nop     dword ptr [rax+rax+00h]
0x18005acd0  cmp     r10, rax
0x18005acd3  jnb     loc_18005C269
0x18005acd9  mov     edi, [r11]
0x18005acdc  cmp     r8, rdi
0x18005acdf  jb      short loc_18005ACF5
0x18005ace1  inc     r10
0x18005ace4  add     r11, 78h ; 'x'
0x18005ace8  cmp     rcx, r10
0x18005aceb  jnz     short loc_18005ACD0
0x18005aced  mov     r10, rcx
0x18005acf0  jmp     short loc_18005ACF5
0x18005acf2  mov     r10, r9
0x18005acf5  mov     [rsi+140h], r10
0x18005acfc  lea     r15, [r10+1]
0x18005ad00  cmp     r15, rbx
0x18005ad03  jb      loc_18005C07A
0x18005ad09  cmp     r10, rax
0x18005ad0c  jnb     loc_18005C08C
0x18005ad12  sub     r15, rbx
0x18005ad15  jz      loc_18005C291
0x18005ad1b  mov     rax, [rsi+198h]
0x18005ad22  mov     rcx, [rsi+1A0h]
0x18005ad29  lea     r10, [rcx-1]
0x18005ad2d  cmp     r10, rax
0x18005ad30  jnb     short loc_18005AD7B
0x18005ad32  mov     r8, [rsi+190h]
0x18005ad39  mov     r9, r10
0x18005ad3c  shl     r9, 5
0x18005ad40  mov     r9d, [r8+r9+18h]
0x18005ad45  cmp     r14, r9
0x18005ad48  jnb     short loc_18005AD7D
0x18005ad4a  test    r10, r10
0x18005ad4d  jz      loc_18005ADE1
0x18005ad53  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18005ad57  cmp     rcx, rax
0x18005ad5a  jnb     loc_18005C23D
0x18005ad60  mov     r9, rcx
0x18005ad63  shl     r9, 5
0x18005ad67  mov     r8d, [r8+r9+18h]
0x18005ad6c  cmp     r14, r8
0x18005ad6f  mov     r9, r10
0x18005ad72  jnb     short loc_18005ADE4
0x18005ad74  mov     r8, rcx
0x18005ad77  xor     ecx, ecx
0x18005ad79  jmp     short loc_18005AD80
0x18005ad7b  xor     ecx, ecx
0x18005ad7d  mov     r8, rax
0x18005ad80  cmp     rcx, r8
0x18005ad83  jnb     short loc_18005ADC8
0x18005ad85  mov     r9, [rsi+190h]
0x18005ad8c  mov     r10, rcx
0x18005ad8f  shl     r10, 5
0x18005ad93  add     r9, r10
0x18005ad96  add     r9, 18h
0x18005ad9a  mov     r10, rcx
0x18005ad9d  nop     dword ptr [rax]
0x18005ada0  cmp     r10, rax
0x18005ada3  jnb     loc_18005C236
0x18005ada9  mov     r11, r10
0x18005adac  mov     r10d, [r9]
0x18005adaf  cmp     r14, r10
0x18005adb2  jb      short loc_18005ADCD
0x18005adb4  mov     r10, r11
0x18005adb7  inc     r10
0x18005adba  add     r9, 20h ; ' '
0x18005adbe  cmp     r8, r10
0x18005adc1  jnz     short loc_18005ADA0
0x18005adc3  mov     r9, r8
0x18005adc6  jmp     short loc_18005ADE4
0x18005adc8  mov     r9, rcx
0x18005adcb  jmp     short loc_18005ADE4
0x18005adcd  mov     r9, r11
0x18005add0  jmp     short loc_18005ADE4
0x18005add2  xor     ebx, ebx
0x18005add4  jmp     loc_18005AC45
0x18005add9  xor     r10d, r10d
0x18005addc  jmp     loc_18005ACF5
0x18005ade1  xor     r9d, r9d
0x18005ade4  mov     [rsi+1A0h], r9
0x18005adeb  cmp     r9, rax
0x18005adee  jnb     loc_18005C2A1
0x18005adf4  shl     r9, 5
0x18005adf8  add     r9, [rsi+190h]
0x18005adff  mov     [rbp+290h+var_98], r9
0x18005ae06  mov     rax, [rsi+178h]
0x18005ae0d  mov     rcx, [rsi+180h]
0x18005ae14  lea     rdi, [rcx-1]
0x18005ae18  cmp     rdi, rax
0x18005ae1b  jnb     short loc_18005AE63
0x18005ae1d  mov     r8, [rsi+170h]
0x18005ae24  mov     r9, rdi
0x18005ae27  shl     r9, 5
0x18005ae2b  mov     r9d, [r8+r9+18h]
0x18005ae30  cmp     r14, r9
0x18005ae33  jnb     short loc_18005AE65
0x18005ae35  test    rdi, rdi
0x18005ae38  jz      loc_18005BA84
0x18005ae3e  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18005ae42  cmp     rcx, rax
0x18005ae45  jnb     loc_18005C23D
0x18005ae4b  mov     r9, rcx
0x18005ae4e  shl     r9, 5
0x18005ae52  mov     r8d, [r8+r9+18h]
0x18005ae57  cmp     r14, r8
0x18005ae5a  jnb     short loc_18005AEB5
0x18005ae5c  mov     r8, rcx
0x18005ae5f  xor     ecx, ecx
0x18005ae61  jmp     short loc_18005AE68
0x18005ae63  xor     ecx, ecx
0x18005ae65  mov     r8, rax
0x18005ae68  cmp     rcx, r8
0x18005ae6b  jnb     short loc_18005AEB2
0x18005ae6d  mov     r9, [rsi+170h]
  ... truncated ...
```
