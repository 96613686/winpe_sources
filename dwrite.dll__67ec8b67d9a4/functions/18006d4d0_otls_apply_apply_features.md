# otls::apply::apply_features

- ea: `0x18006d4d0`
- end: `0x18006f2de`
- name: `otls::apply::apply_features`
- size: `7694`
- prototype: ``
- caller_count: `4`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006cfa0`
- `0x18007cfa0`
- `0x18008ed10`
- `0x1800a5950`

## callees

- `0x180065aa0`
- `0x180065ec0`
- `0x18006b3c0`
- `0x18006d4d0`
- `0x18006f3f0`
- `0x18006f790`
- `0x180070e50`
- `0x180070f40`
- `0x180071080`
- `0x1800713e0`
- `0x180071740`
- `0x1800753b0`
- `0x180075500`
- `0x1800dc910`
- `0x180212f4c`
- `0x18021e1b6`
- `0x180316190`
- `0x180316232`
- `0x180316540`
- `0x180316870`
- `0x1803168c1`
- `0x180316980`
- `0x180316a30`
- `0x180316ae0`
- `0x180316c90`
- `0x180316ce0`
- `0x180316d00`
- `0x180316ee0`

## import_xrefs

- `kernel32!HeapFree` at `0x18006eecf`
- `kernel32!HeapFree` at `0x18006ef0e`
- `kernel32!HeapFree` at `0x18006ef55`
- `kernel32!HeapFree` at `0x18006ef7b`
- `kernel32!HeapFree` at `0x18006eecf`
- `kernel32!HeapFree` at `0x18006ef0e`
- `kernel32!HeapFree` at `0x18006ef55`
- `kernel32!HeapFree` at `0x18006ef7b`
- `kernel32!GetProcessHeap` at `0x18006eec1`
- `kernel32!GetProcessHeap` at `0x18006ef00`
- `kernel32!GetProcessHeap` at `0x18006ef47`
- `kernel32!GetProcessHeap` at `0x18006ef69`
- `kernel32!GetProcessHeap` at `0x18006eec1`
- `kernel32!GetProcessHeap` at `0x18006ef00`
- `kernel32!GetProcessHeap` at `0x18006ef47`
- `kernel32!GetProcessHeap` at `0x18006ef69`

## string_xrefs

- `0x18006d80a`: `rust\otls\src\cache.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall otls::apply::apply_features(
        unsigned __int8 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int64 a6,
        int a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // r13
  unsigned __int64 v16; // rsi
  __int128 v17; // xmm0
  _QWORD *v18; // r12
  __int64 v19; // rcx
  _QWORD *v20; // rax
  unsigned __int64 v21; // r15
  void *v22; // r15
  __int64 v23; // rbx
  __int64 v24; // r10
  __int64 result; // rax
  unsigned int **v26; // r15
  __int64 v27; // rdx
  __int64 v28; // r10
  unsigned __int64 v29; // rcx
  unsigned __int16 v30; // dx
  unsigned __int64 v31; // rcx
  __int64 v32; // r12
  _WORD *v33; // rdx
  unsigned __int16 v34; // r9
  __int16 v35; // ax
  unsigned __int16 *v36; // rsi
  __int64 *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int128 v40; // rax
  __int64 v41; // r8
  __int64 v42; // r15
  __int64 v43; // rax
  __int64 v44; // r9
  const char *v45; // r9
  unsigned __int64 v46; // r8
  int *v47; // rbx
  unsigned __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  unsigned __int64 v51; // rsi
  unsigned __int64 *v52; // rbx
  __int64 v53; // rdx
  int v54; // r8d
  char v55; // bl
  __int64 v56; // rsi
  int v57; // r11d
  unsigned int **v58; // rdi
  unsigned __int64 v59; // rbx
  unsigned __int64 v60; // rax
  unsigned int *v61; // r10
  __int64 v62; // rdx
  unsigned __int16 v63; // r9
  unsigned __int64 v64; // r9
  bool v65; // of
  unsigned __int64 v66; // rbx
  __int64 v67; // rcx
  const void *v68; // rdx
  const void *v69; // rbx
  __int64 v70; // rax
  __int128 v71; // xmm0
  unsigned __int64 v72; // rcx
  unsigned __int64 v73; // rsi
  unsigned __int64 v74; // rdx
  __int64 v75; // rax
  unsigned __int64 v76; // rsi
  __int64 v77; // rdx
  unsigned __int64 v78; // rdx
  __int64 v79; // rcx
  unsigned __int64 v80; // r11
  __int64 v81; // r15
  unsigned __int64 v82; // rdi
  __int64 v83; // r14
  unsigned __int64 v84; // r12
  __int128 v85; // rax
  unsigned __int64 v86; // rcx
  unsigned __int64 v87; // r13
  unsigned __int64 v88; // rax
  __int64 v89; // rax
  unsigned __int64 v90; // rbx
  unsigned __int64 v91; // rdx
  unsigned __int64 v92; // rcx
  unsigned __int16 v93; // r8
  unsigned __int64 v94; // rax
  unsigned __int16 v95; // r9
  __int64 v96; // rax
  __int16 v97; // r8
  unsigned __int64 v98; // rsi
  __int64 v99; // r10
  unsigned __int64 v100; // r11
  __int64 v101; // r13
  unsigned __int64 v102; // rcx
  __int64 v103; // rsi
  unsigned __int16 *v104; // rax
  unsigned __int64 v105; // r15
  int v106; // ecx
  bool v107; // zf
  unsigned __int64 v108; // rdi
  __int64 v109; // r14
  int v110; // ecx
  unsigned __int64 v111; // r8
  int v112; // r8d
  int v113; // r9d
  __int16 v114; // ax
  char glyph_in_lookup; // al
  unsigned __int64 v116; // rdx
  unsigned __int64 v117; // r12
  unsigned __int64 v118; // r9
  __int64 v119; // r10
  unsigned __int64 v120; // r11
  __int64 v121; // rdx
  unsigned __int16 v122; // r8
  __int64 v123; // rcx
  __int64 v124; // rcx
  __int64 v125; // r8
  unsigned __int64 v126; // rdx
  unsigned __int64 v127; // rax
  unsigned __int64 v128; // r9
  unsigned __int64 v129; // r11
  unsigned __int16 *v130; // r9
  char glyph_in_lookup_backward; // al
  __int64 v132; // rdx
  unsigned __int64 v133; // rsi
  unsigned __int64 v134; // rax
  unsigned __int64 v135; // rdi
  __int64 v136; // rax
  unsigned __int64 v137; // r14
  unsigned int *v138; // r13
  char v139; // al
  unsigned int v140; // eax
  unsigned __int64 v141; // rcx
  unsigned __int64 v142; // rsi
  unsigned int *v143; // rax
  __int64 v144; // rdi
  unsigned int *v145; // r14
  char v146; // cl
  unsigned __int64 v147; // rcx
  unsigned __int64 v148; // r8
  unsigned __int64 v149; // rdi
  char v150; // cl
  unsigned int *v151; // rax
  unsigned __int64 v152; // rcx
  unsigned __int64 v153; // rax
  unsigned __int64 v154; // r9
  unsigned __int64 v155; // rdi
  __int64 v156; // rsi
  unsigned __int64 v157; // r10
  unsigned __int64 v158; // rcx
  unsigned __int64 v159; // rdx
  bool v160; // cf
  bool v161; // cc
  unsigned __int64 v162; // rdx
  unsigned __int64 v163; // r13
  unsigned __int64 v164; // r8
  unsigned __int64 v165; // r8
  unsigned __int64 v166; // rax
  unsigned __int64 v167; // r13
  unsigned __int64 v168; // rax
  unsigned __int64 v169; // r13
  _WORD *v170; // rcx
  unsigned __int64 v171; // rcx
  unsigned __int64 v172; // rcx
  unsigned __int64 v173; // rdx
  __int64 v174; // rdi
  __int64 v175; // r9
  __int64 v176; // rdi
  __int64 v177; // r9
  unsigned __int64 v178; // rdi
  unsigned __int64 v179; // rdx
  unsigned __int64 v180; // rax
  unsigned __int16 v181; // cx
  unsigned __int64 v182; // rax
  _WORD *v183; // rcx
  unsigned __int16 v184; // dx
  unsigned __int64 v185; // r10
  unsigned __int64 v186; // r14
  __int64 v187; // r8
  __int16 v188; // bx
  __int16 v189; // di
  _QWORD *v190; // rdi
  void *v191; // rsi
  HANDLE ProcessHeap; // rax
  void *v193; // rsi
  HANDLE v194; // rax
  void *v195; // rsi
  unsigned int v196; // edi
  HANDLE v197; // rax
  unsigned int v198; // esi
  HANDLE v199; // rax
  __int64 v200; // rcx
  __int64 v201; // [rsp+88h] [rbp+8h] BYREF
  unsigned __int16 *v202; // [rsp+90h] [rbp+10h]
  _QWORD v203[4]; // [rsp+98h] [rbp+18h] BYREF
  __int16 v204; // [rsp+B8h] [rbp+38h]
  unsigned __int16 v205; // [rsp+BAh] [rbp+3Ah]
  __int128 v206; // [rsp+C0h] [rbp+40h]
  __int32 v207; // [rsp+D0h] [rbp+50h]
  unsigned __int8 v208; // [rsp+E0h] [rbp+60h] BYREF
  unsigned int v209; // [rsp+E4h] [rbp+64h]
  unsigned __int64 v210; // [rsp+E8h] [rbp+68h]
  unsigned __int64 v211; // [rsp+F0h] [rbp+70h]
  _QWORD *v212; // [rsp+F8h] [rbp+78h]
  unsigned __int64 v213; // [rsp+100h] [rbp+80h]
  unsigned __int16 *v214; // [rsp+108h] [rbp+88h]
  __int64 v215; // [rsp+110h] [rbp+90h]
  _BOOL8 v216; // [rsp+118h] [rbp+98h]
  _WORD *v217; // [rsp+120h] [rbp+A0h] BYREF
  unsigned __int64 v218; // [rsp+128h] [rbp+A8h]
  __int64 v219; // [rsp+130h] [rbp+B0h]
  unsigned __int64 v220; // [rsp+138h] [rbp+B8h]
  _WORD *v221; // [rsp+140h] [rbp+C0h]
  unsigned __int64 v222; // [rsp+148h] [rbp+C8h]
  __int16 v223; // [rsp+150h] [rbp+D0h]
  __int16 v224; // [rsp+152h] [rbp+D2h]
  unsigned __int16 v225; // [rsp+154h] [rbp+D4h]
  unsigned int *v226; // [rsp+158h] [rbp+D8h]
  LPVOID v227; // [rsp+160h] [rbp+E0h]
  __m256i v228; // [rsp+168h] [rbp+E8h] BYREF
  unsigned __int64 v229; // [rsp+188h] [rbp+108h]
  __int128 v230; // [rsp+190h] [rbp+110h]
  unsigned __int64 v231; // [rsp+1A0h] [rbp+120h] BYREF
  LPVOID lpMem; // [rsp+1A8h] [rbp+128h]
  unsigned __int64 v233; // [rsp+1B0h] [rbp+130h]
  __int128 v234; // [rsp+1B8h] [rbp+138h]
  __int128 v235; // [rsp+1C8h] [rbp+148h]
  __int64 v236; // [rsp+1D8h] [rbp+158h]
  unsigned __int64 v237; // [rsp+1E0h] [rbp+160h]
  unsigned __int64 v238; // [rsp+1E8h] [rbp+168h]
  unsigned int *v239; // [rsp+1F0h] [rbp+170h]
  unsigned __int64 v240; // [rsp+1F8h] [rbp+178h]
  unsigned __int16 *v241; // [rsp+200h] [rbp+180h]
  _BYTE v242[20]; // [rsp+208h] [rbp+188h]
  __int32 v243; // [rsp+21Ch] [rbp+19Ch]
  char v244; // [rsp+220h] [rbp+1A0h]
  int v245; // [rsp+22Ch] [rbp+1ACh]
  unsigned __int64 v246; // [rsp+230h] [rbp+1B0h]
  unsigned __int64 v247; // [rsp+238h] [rbp+1B8h]
  unsigned __int64 v248; // [rsp+240h] [rbp+1C0h]
  unsigned __int64 v249; // [rsp+248h] [rbp+1C8h]
  unsigned __int64 v250; // [rsp+250h] [rbp+1D0h]
  unsigned __int64 v251; // [rsp+258h] [rbp+1D8h]
  unsigned __int64 v252; // [rsp+260h] [rbp+1E0h]
  __int64 v253; // [rsp+268h] [rbp+1E8h]
  unsigned __int16 *v254; // [rsp+270h] [rbp+1F0h]
  unsigned __int64 v255; // [rsp+278h] [rbp+1F8h]
  unsigned int *v256; // [rsp+280h] [rbp+200h]
  unsigned __int64 *v257; // [rsp+288h] [rbp+208h]
  unsigned __int64 v258; // [rsp+290h] [rbp+210h]
  __int64 v259; // [rsp+298h] [rbp+218h]
  unsigned __int64 v260; // [rsp+2A0h] [rbp+220h]
  __int64 v261; // [rsp+2A8h] [rbp+228h]
  unsigned __int64 v262; // [rsp+2B0h] [rbp+230h]
  unsigned __int64 v263; // [rsp+2B8h] [rbp+238h]
  unsigned __int64 v264; // [rsp+2C0h] [rbp+240h]
  unsigned __int64 v265; // [rsp+2C8h] [rbp+248h]
  bool v266; // [rsp+2D6h] [rbp+256h]
  char v267; // [rsp+2D7h] [rbp+257h]
  unsigned __int64 v268; // [rsp+2D8h] [rbp+258h]
  unsigned __int64 v269; // [rsp+2E0h] [rbp+260h]
  unsigned __int64 v270; // [rsp+2E8h] [rbp+268h]
  unsigned __int64 v271; // [rsp+2F0h] [rbp+270h]
  unsigned __int8 v272; // [rsp+2FFh] [rbp+27Fh]
  __int64 v273; // [rsp+300h] [rbp+280h]

  v273 = -2;
  v253 = a3;
  v14 = a6;
  if ( a1 )
  {
    if ( *(_QWORD *)(a6 + 232) == 0x8000000000000001uLL )
      core::option::unwrap_failed(&off_18033A190);
    v15 = a6 + 232;
  }
  else
  {
    if ( *(_QWORD *)(a6 + 456) == 0x8000000000000001uLL )
      core::option::unwrap_failed(&off_18033A178);
    v15 = a6 + 456;
  }
  if ( !((*(_BYTE *)(a6 + 1320) == 2) | (a1 ^ *(_BYTE *)(a6 + 1320)) & 1) )
    goto LABEL_14;
  v16 = *(_QWORD *)(v15 + 128);
  v17 = *(_OWORD *)(v15 + 120);
  *(_OWORD *)(a6 + 1288) = *(_OWORD *)(v15 + 136);
  *(_OWORD *)(a6 + 1272) = v17;
  if ( v16 >> 60 )
    goto LABEL_29;
  v18 = a2;
  v19 = *(_QWORD *)(a6 + 1336);
  v20 = *(_QWORD **)(v19 + 16);
  v21 = v20[4];
  if ( 8 * v16 > v21 || (v22 = (void *)((v21 - 8 * v16) & 0xFFFFFFFFFFFFFFF8uLL), (unsigned __int64)v22 < *v20) )
  {
    v42 = a4;
    v43 = bumpalo::Bump::alloc_layout_slow(v19, 8);
    a4 = v42;
    v22 = (void *)v43;
    if ( v43 )
      goto LABEL_11;
LABEL_29:
    bumpalo::oom();
  }
  v20[4] = v22;
LABEL_11:
  if ( v16 )
  {
    v23 = a4;
    memset_0(v22, 0, 8 * v16);
    a4 = v23;
  }
  *(_QWORD *)(a6 + 1304) = v22;
  *(_QWORD *)(a6 + 1312) = v16;
  *(_BYTE *)(a6 + 1320) = a1;
  a2 = v18;
LABEL_14:
  v24 = *(_QWORD *)(v15 + 104);
  result = 258;
  if ( v24 )
  {
    v26 = (unsigned int **)a2;
    v27 = *(_QWORD *)(v15 + 96);
    v28 = 6 * v24;
    while ( *(_DWORD *)v27 != a7 )
    {
      v27 += 6;
      v28 -= 6;
      if ( !v28 )
        return result;
    }
    v29 = *(_QWORD *)(v15 + 88);
    v30 = __ROL2__(*(_WORD *)(v27 + 4), 8);
    v160 = v29 < v30;
    v31 = v29 - v30;
    if ( !v160 && v31 >= 2 && (v31 & 0xFFFFFFFFFFFFFFFEuLL) != 2 )
    {
      v32 = a4;
      v33 = (_WORD *)(*(_QWORD *)(v15 + 80) + v30);
      v34 = __ROL2__(v33[1], 8);
      if ( 3 * (unsigned __int64)(2 * (unsigned int)v34) <= v31 - 4 )
      {
        v35 = __ROL2__(*v33, 8);
        v203[0] = v33;
        v203[1] = v31;
        v203[2] = v33 + 2;
        v203[3] = v34;
        v204 = v35;
        v205 = v34;
        otls::scrilang::find_lang_sys(&v228, v203, a8);
        v36 = (unsigned __int16 *)v228.m256i_i64[0];
        result = v228.m256i_u32[2];
        if ( v228.m256i_i64[0] )
        {
          LODWORD(v271) = v228.m256i_i32[2];
          v207 = v228.m256i_i32[7];
          v206 = *(_OWORD *)((char *)&v228.m256i_u64[1] + 4);
          v37 = *(__int64 **)(a6 + 1328);
          v38 = *v37;
          if ( !*v37 )
          {
            (*(void (__fastcall **)(__m256i *, _QWORD, __int64))(*(_QWORD *)(a6 + 1352) + 64LL))(
              &v228,
              *(_QWORD *)(a6 + 1344),
              0x20000);
            v39 = v228.m256i_i64[0];
            *((_QWORD *)&v40 + 1) = v228.m256i_u32[2];
            if ( !v228.m256i_i64[0] )
              return DWORD2(v40);
            *(_QWORD *)&v40 = v228.m256i_u32[3];
            v41 = *(_QWORD *)(a6 + 1328);
            if ( *(_QWORD *)v41 )
            {
              if ( !_InterlockedDecrement64((volatile signed __int64 *)v228.m256i_i64[0]) )
                alloc::sync::Arc_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_::drop_slow_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_(
                  v39,
                  *((_QWORD *)&v40 + 1) | ((_QWORD)v40 << 32));
            }
            else
            {
              v44 = v228.m256i_i64[2];
              *(_QWORD *)v41 = v228.m256i_i64[0];
              *(_DWORD *)(v41 + 8) = DWORD2(v40);
              *(_DWORD *)(v41 + 12) = v40;
              *(_QWORD *)(v41 + 16) = v44;
            }
            v37 = *(__int64 **)(a6 + 1328);
            v38 = *v37;
            if ( !*v37 )
              core::option::unwrap_failed(&off_18033AED8);
          }
          *(_QWORD *)&v40 = (*(__int64 (__fastcall **)(unsigned __int64))(v37[1] + 24))(((*(_QWORD *)(v37[1] + 16) - 1LL)
                                                                                       & 0xFFFFFFFFFFFFFFF0uLL)
                                                                                      + v38 + 16);
          if ( (_QWORD)v40 )
          {
            v272 = a1;
            v270 = *(_QWORD *)(a5 + 16);
            v45 = "rust\\otls\\src\\cache.rs";
            v46 = 8;
            v47 = &dword_1803B41CC;
            v254 = v36;
            if ( *((_QWORD *)&v40 + 1) >= 0xCu )
            {
              if ( (v40 & 3) != 0 )
              {
                v228.m256i_i64[0] = 0;
                *(_OWORD *)&v228.m256i_u64[1] = v40;
                core::result::unwrap_failed(
                  (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                  43,
                  (unsigned int)&v228,
                  (unsigned int)&qword_180339C60,
                  (__int64)&off_18033A400);
              }
              v48 = *(unsigned int *)(v40 + 4LL * v272 + 4);
              if ( *(_DWORD *)(v40 + 4LL * v272 + 4) )
              {
                v46 = *((_QWORD *)&v40 + 1) - v48;
                if ( *((_QWORD *)&v40 + 1) < v48 )
                  core::slice::index::slice_start_index_len_fail(v48, *((_QWORD *)&v40 + 1), &off_18033A418);
                v49 = v48 + v40;
                if ( (v49 & 3) != 0 )
                {
                  v200 = 0;
                }
                else
                {
                  if ( v46 > 7 )
                  {
                    v45 = (const char *)(v49 + 8);
                    v50 = *(unsigned int *)(v49 + 4);
                    if ( 4 * v50 > v46 - 8 )
                    {
                      v228.m256i_i64[0] = 1;
                      v228.m256i_i64[1] = v49 + 8;
                      v228.m256i_i64[2] = v46 - 8;
                      core::result::unwrap_failed(
                        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                        43,
                        (unsigned int)&v228,
                        (unsigned int)&qword_180339CA0,
                        (__int64)&off_18033A3B8);
                    }
                    v47 = (int *)v49;
LABEL_43:
                    v257 = (unsigned __int64 *)(a6 + 680);
                    *(_QWORD *)(a6 + 712) = v47;
                    *(_QWORD *)(a6 + 720) = v46;
                    *(_QWORD *)(a6 + 728) = v47;
                    *(_QWORD *)(a6 + 736) = v45;
                    *(_QWORD *)(a6 + 744) = v50;
                    *(_QWORD *)(a6 + 704) = 0;
                    *(_BYTE *)(a6 + 1264) = 1;
                    v51 = v270;
                    if ( v270 )
                    {
                      if ( *(_QWORD *)(a6 + 696) >= v270 )
                      {
                        v53 = 0;
                        v52 = v257;
                      }
                      else
                      {
                        v52 = v257;
                        bumpalo::collections::raw_vec::RawVec_otls::cache::CacheLookupPointer_::reserve_internal_or_panic_otls::cache::CacheLookupPointer_(
                          v257,
                          0,
                          v270);
                        v53 = *(_QWORD *)(a6 + 704);
                      }
                      do
                      {
                        if ( v53 == *(_QWORD *)(a6 + 696) )
                        {
                          bumpalo::collections::raw_vec::RawVec_otls::cache::CacheLookupPointer_::reserve_internal_or_panic_otls::cache::CacheLookupPointer_(
                            v52,
                            v53,
                            1);
                          v53 = *(_QWORD *)(a6 + 704);
                        }
                        *(_WORD *)(*(_QWORD *)(a6 + 680) + 2 * v53++) = 0;
                        *(_QWORD *)(a6 + 704) = v53;
                        --v51;
                      }
                      while ( v51 );
                      v55 = *(_BYTE *)(a6 + 1264);
                      v56 = 0;
                      v250 = a6 + 752;
                      memset_0((void *)(a6 + 752), 0, 0x200u);
                      if ( (v55 & 1) == 0 )
                      {
                        v246 = 0;
                        v57 = v271;
                        v58 = v26;
                        goto LABEL_55;
                      }
                      v47 = *(int **)(a6 + 728);
                    }
                    else
                    {
                      v250 = a6 + 752;
                      memset_0((void *)(a6 + 752), 0, 0x200u);
                    }
                    v57 = v271;
                    v58 = v26;
                    v56 = *(unsigned __int16 *)v47;
                    v246 = *((unsigned __int16 *)v47 + 1);
LABEL_55:
                    v261 = *(_QWORD *)(a6 + 208);
                    v59 = *(_QWORD *)(a6 + 216);
                    v60 = *(_QWORD *)(a6 + 224);
                    *(_QWORD *)(a6 + 208) = 0;
                    *(_QWORD *)(a6 + 216) = 1;
                    *(_QWORD *)(a6 + 224) = 0;
                    v61 = *v58;
                    LOBYTE(v54) = 1;
                    v269 = (unsigned __int64)v58[1];
                    if ( !v269 )
                      goto LABEL_61;
                    v62 = 0;
                    LOWORD(v54) = 0;
                    while ( 1 )
                    {
                      v63 = v54;
                      v54 = LOWORD(v61[v62 + 2]);
                      if ( (unsigned __int16)v54 < v63 )
                        break;
                      v62 += 3;
                      if ( 3 * v269 == v62 )
                      {
                        v58 = v26;
                        LOBYTE(v54) = 1;
                        goto LABEL_61;
                      }
                    }
                    v54 = 0;
                    v58 = v26;
LABEL_61:
                    v64 = *(_QWORD *)(v15 + 64);
                    v268 = *(_QWORD *)(v15 + 72);
                    v65 = __OFSUB__(0, *(_QWORD *)v15);
                    v255 = v32;
                    v256 = v61;
                    v263 = v59;
                    if ( v65 )
                    {
                      v66 = 0x8000000000000000uLL;
                      goto LABEL_71;
                    }
                    v14 = *(_QWORD *)(v15 + 16);
                    if ( v14 >> 61 != 0 || 8 * v14 > 0x7FFFFFFFFFFFFFF8LL )
                    {
                      v67 = 0;
                      goto LABEL_65;
                    }
                    v258 = v64;
                    LODWORD(v252) = v54;
                    v251 = v60;
                    v68 = *(const void **)(v15 + 8);
                    if ( 8 * v14 )
                    {
                      v69 = *(const void **)(v15 + 8);
                      v70 = std::sys::alloc::windows::process_heap_alloc(0, 8 * v14);
                      v68 = v69;
                      v32 = v70;
                      v66 = v14;
                      if ( !v70 )
                      {
                        v67 = 8;
LABEL_65:
                        alloc::raw_vec::handle_error(v67, 8 * v14, &off_180348EC0);
                      }
                    }
                    else
                    {
                      v32 = 8;
                      v66 = 0;
                    }
                    memcpy_0((void *)v32, v68, 8 * v14);
                    v57 = v271;
                    v61 = v256;
                    v26 = v58;
                    v60 = v251;
                    LOBYTE(v54) = v252;
                    v64 = v258;
LABEL_71:
                    v236 = *(_QWORD *)(v15 + 56);
                    v71 = *(_OWORD *)(v15 + 24);
                    v235 = *(_OWORD *)(v15 + 40);
                    v234 = v71;
                    v239 = v61;
                    v240 = v269;
                    v244 = v54;
                    v241 = v254;
                    *(_DWORD *)v242 = v57;
                    v243 = v207;
                    *(_OWORD *)&v242[4] = v206;
                    v231 = v66;
                    lpMem = (LPVOID)v32;
                    v233 = v14;
                    v237 = v64;
                    v238 = v268;
                    v228.m256i_i64[0] = v261;
                    v72 = (v269 + 9) >> 3;
                    v228.m256i_i64[1] = v263;
                    *(_OWORD *)&v228.m256i_u64[2] = v60;
                    v229 = v72;
                    v230 = 0;
                    v73 = v72 * v56;
                    v74 = 8193;
                    if ( v73 < 0x2001 )
                      v74 = v73;
                    if ( v73 <= v60 || v74 >= v72 )
                    {
                      if ( v269 + 9 < 8 )
                        core::panicking::panic_const::panic_const_div_by_zero(&off_18033A5E0);
                      if ( (v72 | v60) >> 32 )
                        v75 = v60 / v72;
                      else
                        v75 = (unsigned int)v60 / (unsigned int)v72;
                      v228.m256i_i64[3] = v75;
                    }
                    else
                    {
                      v228.m256i_i64[2] = 0;
                    }
                    v76 = otls::enables_cache::EnablesCache::refresh(&v228, 0);
                    v212 = (_QWORD *)(a6 + 208);
                    v226 = &v256[3 * v269];
                    v78 = v77 + 1;
                    v211 = *(_QWORD *)(v15 + 128);
                    if ( v211 < v78 )
                      v78 = v211;
                    v251 = v78 - 1;
                    v79 = *((unsigned __int16 *)v26 + 9);
                    v213 = *((unsigned __int16 *)v26 + 8);
                    v247 = v213 + v79;
                    v80 = v270;
                    v262 = v78;
                    if ( v76 >= v78 )
                    {
LABEL_331:
                      v190 = v212;
                      if ( *v212 )
                      {
                        v191 = *(void **)(a6 + 216);
                        ProcessHeap = GetProcessHeap();
                        HeapFree(ProcessHeap, 0, v191);
                      }
                      v190[2] = v228.m256i_i64[2];
                      *(_OWORD *)v190 = *(_OWORD *)v228.m256i_i8;
                      if ( 2 * v231 )
                      {
                        v193 = lpMem;
                        v194 = GetProcessHeap();
                        HeapFree(v194, 0, v193);
                      }
                      return 0;
                    }
                    while ( 1 )
                    {
                      v271 = *(_QWORD *)(a5 + 8);
                      LOBYTE(v259) = *(_BYTE *)(a6 + 1264);
                      v258 = *(_QWORD *)(a6 + 728);
                      v81 = *(_QWORD *)(a6 + 680);
                      v82 = *(_QWORD *)(a6 + 704);
                      v83 = *(_QWORD *)(a6 + 736);
                      v254 = *(unsigned __int16 **)(a6 + 744);
                      v84 = *(_QWORD *)(a6 + 720);
                      v261 = *(_QWORD *)(a6 + 712);
                      v85 = v230;
                      v270 = v80;
                      v252 = v84;
                      while ( 1 )
                      {
                        if ( v76 < (unsigned __int64)v85 || v76 >= *((_QWORD *)&v85 + 1) )
                          otls::enables_cache::EnablesCache::refresh(&v228, v76);
                        v263 = v228.m256i_u64[2];
                        v80 = v270;
                        if ( !v228.m256i_i64[2] )
                          break;
                        v85 = v230;
                        if ( v76 < (unsigned __int64)v230 || v76 >= *((_QWORD *)&v230 + 1) )
                          break;
                        v86 = v229 * (v76 - v230);
                        if ( v86 > v263 )
                          core::slice::index::slice_start_index_len_fail(v86, v263, &off_18033A5F8);
                        if ( v86 == v263 )
                          core::panicking::panic_bounds_check(0, 0, &off_18033A5C8);
                        if ( (*(_BYTE *)(v228.m256i_i64[1] + v86) & 1) != 0 )
                          break;
                        v87 = v76;
LABEL_139:
                        v76 = v87 + 1;
                        if ( v87 >= v251 )
                          goto LABEL_331;
                      }
                      if ( (v259 & 1) == 0 || (v88 = *(unsigned __int16 *)(v258 + 2), v76 >= v88) )
                      {
                        v90 = 0;
                        v87 = v76;
                        goto LABEL_144;
                      }
                      if ( !v82 )
                      {
                        v90 = 0;
                        v87 = v262;
                        if ( v251 < v88 )
                          goto LABEL_129;
LABEL_128:
                        if ( v87 < v88 )
                          goto LABEL_129;
                        v90 = 0;
                        v87 = v88;
                        goto LABEL_144;
                      }
                      v89 = 1;
                      v87 = v262;
                      v90 = v82;
                      v91 = 0;
                      v268 = v76;
                      do
                      {
                        v92 = v91;
                        v91 = v89;
                        v93 = *(_WORD *)(v81 + 2 * v92);
                        if ( !v93 )
                        {
                          if ( v92 >= v80 )
                            core::panicking::panic_bounds_check(v92, v80, &off_18033A478);
                          v95 = *(_WORD *)(v271 + 8 * v92);
                          v96 = v95 & 0x7F;
                          v97 = *(_WORD *)(v250 + 4 * v96);
                          if ( v97 && v97 == v95 )
                          {
                            v93 = *(_WORD *)(v250 + 4 * v96 + 2);
                          }
                          else
                          {
                            *(_WORD *)(v250 + 4 * v96) = v95;
                            v93 = -1;
                            if ( v254 )
                            {
                              v98 = v87;
                              if ( v254 == (unsigned __int16 *)1 )
                              {
                                v99 = 0;
                              }
                              else
                              {
                                v100 = (unsigned __int64)v254;
                                v101 = 0;
                                do
                                {
                                  v99 = (v100 >> 1) + v101;
                                  if ( *(_WORD *)(v83 + 4 * v99) > v95 )
                                    v99 = v101;
                                  v100 -= v100 >> 1;
                                  v101 = v99;
                                }
                                while ( v100 > 1 );
                              }
                              v80 = v270;
                              v87 = v98;
                              v84 = v252;
                              v76 = v268;
                              if ( *(_WORD *)(v83 + 4 * v99) == v95 )
                                v93 = *(_WORD *)(v83 + 4 * v99 + 2);
                            }
                            *(_WORD *)(v250 + 4 * v96 + 2) = v93;
                          }
                          goto LABEL_123;
                        }
                        while ( 1 )
                        {
                          if ( v93 == 0xFFFF )
                            goto LABEL_102;
                          if ( v84 < v93 )
                            core::slice::index::slice_start_index_len_fail(v93, v84, &off_18033A3E8);
                          if ( v84 - v93 <= 1 )
                          {
                            v217 = (_WORD *)(v261 + v93);
                            v218 = v84 - v93;
                            core::result::unwrap_failed(
                              (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                              43,
                              (unsigned int)&v217,
                              (unsigned int)&qword_180339CC0,
                              (__int64)&off_18033A3D0);
                          }
                          v94 = *(unsigned __int16 *)(v261 + v93);
                          if ( v76 <= v94 )
                            break;
                          v93 += 2;
LABEL_123:
                          *(_WORD *)(v81 + 2 * v92) = v93;
                          if ( !v93 )
                            goto LABEL_102;
                        }
                        if ( v87 > v94 )
                          v90 = v92;
                        if ( v87 >= v94 )
                          v87 = *(unsigned __int16 *)(v261 + v93);
LABEL_102:
                        v89 = (v91 < v82) + v91;
                      }
                      while ( v91 < v82 );
                      v88 = *(unsigned __int16 *)(v258 + 2);
                      if ( v251 >= v88 )
                        goto LABEL_128;
LABEL_129:
                      if ( v87 > v251 )
                        goto LABEL_331;
                      if ( v87 < (unsigned __int64)v230 || v87 >= *((_QWORD *)&v230 + 1) )
                      {
                        otls::enables_cache::EnablesCache::refresh(&v228, v87);
                        v263 = v228.m256i_u64[2];
                        v80 = v270;
                      }
                      if ( v263 )
                      {
                        *(_QWORD *)&v85 = v230;
                        if ( v87 >= (unsigned __int64)v230 )
                        {
                          *((_QWORD *)&v85 + 1) = *((_QWORD *)&v230 + 1);
                          if ( v87 < *((_QWORD *)&v230 + 1) )
                          {
                            v102 = v229 * (v87 - v230);
                            if ( v102 > v263 )
                              core::slice::index::slice_start_index_len_fail(v102, v263, &off_18033A5F8);
                            if ( v102 == v263 )
                              core::panicking::panic_bounds_check(0, 0, &off_18033A5C8);
                            if ( (*(_BYTE *)(v228.m256i_i64[1] + v102) & 1) == 0 )
                              goto LABEL_139;
                          }
                        }
                      }
                      else
                      {
                        v263 = 0;
                      }
LABEL_144:
                      if ( v87 >= v211 )
                        goto LABEL_331;
                      if ( v87 >= *(_QWORD *)(a6 + 1312) )
                      {
LABEL_321:
                        v178 = v262;
                      }
                      else
                      {
                        v103 = *(_QWORD *)(a6 + 1304);
                        v104 = *(unsigned __int16 **)(v103 + 8 * v87);
                        v105 = v87;
                        if ( v104 )
                          goto LABEL_147;
                        v179 = *(_QWORD *)(a6 + 1280);
                        if ( v87 >= v179 )
                          core::panicking::panic_bounds_check(v87, v179, &off_18033AF38);
                        v180 = *(_QWORD *)(a6 + 1296);
                        v181 = __ROL2__(*(_WORD *)(*(_QWORD *)(a6 + 1272) + 2 * v87), 8);
                        v160 = v180 < v181;
                        v182 = v180 - v181;
                        v178 = v262;
                        if ( !v160 && v182 >= 6 )
                        {
                          v183 = (_WORD *)(*(_QWORD *)(a6 + 1288) + v181);
                          v184 = __ROL2__(v183[2], 8);
                          v185 = 2 * (unsigned int)v184;
                          if ( v182 - 6 >= v185 )
                          {
                            v186 = v90;
                            v187 = *(_QWORD *)(a6 + 1336);
                            v188 = __ROL2__(v183[1], 8);
                            v189 = __ROL2__(*v183, 8);
                            v217 = v183 + 3;
                            v218 = v184;
                            v219 = (__int64)&v183[v185 / 2 + 3];
                            v220 = v182 - 6 - v185;
                            v221 = v183;
                            v222 = v182;
                            v223 = v189;
                            v224 = v188;
                            v225 = v184;
                            otls::lookups::parse_lookup(&v201, v272, v187, (__int64)&v217);
                            if ( (_DWORD)v201 != 1 )
                            {
                              v104 = v202;
                              *(_QWORD *)(v103 + 8 * v87) = v202;
                              v90 = v186;
LABEL_147:
                              v106 = 1;
                              v259 = 0;
                              v107 = (*(_BYTE *)v104 & 1) == 0;
                              v254 = v104;
                              if ( v107 && *((_QWORD *)v104 + 2) )
                              {
                                v261 = **((_DWORD **)v104 + 1) == 9;
                                v106 = -(int)v261 | 1;
                              }
                              else
                              {
                                v261 = 0;
                              }
                              v108 = v269;
                              v216 = v106 != 1;
                              v245 = v106;
                              v252 = v106;
                              v227 = (LPVOID)v228.m256i_i64[1];
                              v248 = v229 * (v87 - v230);
                              v267 = v244;
                              v266 = v87 >= *((_QWORD *)&v230 + 1) || v263 == 0 || v87 < (unsigned __int64)v230;
                              v214 = v241;
                              LOBYTE(v84) = 1;
                              v215 = *(_QWORD *)v242;
                              v268 = 0;
                              v258 = 0;
                              v109 = v90;
                              while ( 1 )
                              {
                                v110 = v84;
                                v111 = v270;
                                while ( 1 )
                                {
                                  if ( v90 >= v111 )
                                    goto LABEL_320;
                                  LODWORD(v84) = v110;
                                  if ( (v110 & 1) != 0 || v90 >= v109 )
                                  {
                                    v117 = v258;
                                    if ( v213 > v258 )
                                      v117 = v213;
                                    if ( v266 )
                                    {
                                      otls::features::required_feature(&v217, v214, v215, &v231);
                                      v118 = v255;
                                      v119 = v253;
                                      v108 = v269;
                                      v120 = v247;
                                      v87 = v105;
                                      if ( v217 )
                                      {
                                        v121 = 0;
                                        while ( 2 * v220 != v121 )
                                        {
                                          v122 = __ROL2__(*(_WORD *)(v219 + v121), 8);
                                          v121 += 2;
                                          if ( v105 == v122 )
                                            goto LABEL_223;
                                        }
                                      }
                                      goto LABEL_200;
                                    }
                                    v118 = v255;
                                    v119 = v253;
                                    if ( v248 > v263 )
                                      core::slice::index::slice_start_index_len_fail(v248, v263, &off_18033A5F8);
                                    v120 = v247;
                                    if ( v248 == v263 )
                                      core::panicking::panic_bounds_check(0, 0, &off_18033A5C8);
                                    if ( (*((_BYTE *)v227 + v248) & 2) != 0 )
                                    {
LABEL_223:
                                      if ( v117 < v118 )
                                      {
                                        if ( *(unsigned __int16 *)(v119 + 2 * v117) > v90 )
                                          v90 = *(unsigned __int16 *)(v119 + 2 * v117);
                                        v133 = -1;
                                        v259 = 1;
                                        if ( v120 >= v118 )
                                        {
                                          LODWORD(v84) = 0;
                                          v258 = v120;
                                          v109 = v270;
                                        }
                                        else
                                        {
                                          v109 = *(unsigned __int16 *)(v119 + 2 * v120);
                                          LODWORD(v84) = 0;
                                          v258 = v120;
                                        }
                                        goto LABEL_316;
                                      }
                                    }
                                    else
                                    {
LABEL_200:
                                      if ( (v267 & 1) != 0 )
                                      {
                                        if ( v268 < v108 )
                                        {
                                          v271 = 0;
                                          v133 = -1;
                                          v265 = -1;
                                          v259 = 0;
                                          while ( 2 )
                                          {
                                            v134 = v268;
                                            while ( 1 )
                                            {
                                              v135 = v134;
                                              v268 = v134 + 1;
                                              v136 = 3 * v134;
                                              v137 = LOWORD(v256[v136 + 2]) + (unsigned __int64)HIWORD(v256[v136 + 2]);
                                              if ( v137 >= v117 )
                                              {
                                                v138 = &v256[v136];
                                                v139 = otls::enables_cache::EnablesCache::enables(
                                                         &v228,
                                                         *v138,
                                                         v105,
                                                         v135);
                                                if ( v139 == 2 )
                                                {
                                                  result = 770;
                                                  goto LABEL_338;
                                                }
                                                if ( (v139 & 1) != 0 )
                                                {
                                                  v140 = v138[1];
                                                  if ( v140 )
                                                  {
                                                    if ( v137 >= v255 || v90 <= *(unsigned __int16 *)(v253 + 2 * v137) )
                                                      break;
                                                  }
                                                }
                                              }
                                              v108 = v269;
                                              v134 = v268;
                                              if ( v268 >= v269 )
                                              {
                                                v87 = v105;
                                                if ( v265 != -1 )
                                                  goto LABEL_261;
                                                goto LABEL_320;
                                              }
                                            }
                                            v141 = *((unsigned __int16 *)v138 + 4);
                                            if ( v117 > v141 )
                                              v141 = v117;
                                            if ( v265 == -1 )
                                            {
                                              v259 = v138[1];
                                              v271 = v137;
                                              v265 = v141;
                                            }
                                            else
                                            {
                                              if ( v141 > v271 )
                                              {
                                                if ( v135 < v133 )
                                                  v133 = v135;
                                                v108 = v269;
                                                v87 = v105;
                                                break;
                                              }
                                              if ( v137 > v271 )
                                              {
                                                if ( v140 == (_DWORD)v259 )
                                                {
                                                  v271 = v137;
                                                }
                                                else if ( v135 < v133 )
                                                {
                                                  v133 = v135;
                                                }
                                              }
                                            }
                                            v87 = v105;
                                            v108 = v269;
                                            if ( v268 < v269 )
                                              continue;
                                            break;
                                          }
LABEL_261:
                                          v84 = v271;
                                          if ( v247 < v271 )
                                            v84 = v247;
                                          if ( v265 < v255 )
                                          {
                                            if ( *(unsigned __int16 *)(v253 + 2 * v265) > v90 )
                                              v90 = *(unsigned __int16 *)(v253 + 2 * v265);
                                            v258 = v84;
                                            if ( v84 >= v255 )
                                            {
                                              LODWORD(v84) = 0;
                                              v109 = v270;
                                            }
                                            else
                                            {
                                              v109 = *(unsigned __int16 *)(v253 + 2 * v84);
                                              LODWORD(v84) = 0;
                                            }
                                            goto LABEL_316;
                                          }
                                        }
                                      }
                                      else if ( v108 )
                                      {
                                        v271 = 0;
                                        v265 = -1;
                                        v259 = 0;
                                        v142 = -1;
                                        v143 = v256;
                                        v144 = 0;
                                        while ( 1 )
                                        {
                                          v145 = v143;
                                          v146 = otls::enables_cache::EnablesCache::enables(&v228, *v143, v87, v144);
                                          result = 770;
                                          if ( v146 == 2 )
                                            goto LABEL_338;
                                          v143 = v145 + 3;
                                          ++v144;
                                          if ( (v146 & 1) != 0
                                            && v145[1]
                                            && (v147 = *((unsigned __int16 *)v145 + 4),
                                                v148 = v147 + *((unsigned __int16 *)v145 + 5),
                                                v148 > v117)
                                            && (v148 >= v255 || v90 <= *(unsigned __int16 *)(v253 + 2 * v148)) )
                                          {
                                            if ( v117 > v147 )
                                              v147 = v117;
                                            v87 = v105;
                                            if ( v147 >= v265 )
                                            {
                                              if ( v147 < v142 )
                                                v142 = v147;
                                            }
                                            else
                                            {
                                              v142 = v265;
                                              v259 = v145[1];
                                              v271 = v148;
                                              v265 = v147;
                                            }
                                            if ( v143 == v226 )
                                              goto LABEL_249;
                                          }
                                          else
                                          {
                                            v87 = v105;
                                            if ( v143 == v226 )
                                            {
                                              if ( v265 == -1 )
                                                break;
LABEL_249:
                                              if ( v142 == -1 || v271 < v142 )
                                              {
LABEL_260:
                                                v133 = v268;
                                                v108 = v269;
                                                goto LABEL_261;
                                              }
                                              v149 = 0;
                                              while ( 1 )
                                              {
                                                v150 = otls::enables_cache::EnablesCache::enables(
                                                         &v228,
                                                         v256[3 * v149],
                                                         v87,
                                                         v149);
                                                result = 770;
                                                if ( v150 == 2 )
                                                  goto LABEL_338;
                                                if ( (v150 & 1) != 0
                                                  && (v151 = &v256[3 * v149], v151[1] == (_DWORD)v259) )
                                                {
                                                  v152 = *((unsigned __int16 *)v151 + 4);
                                                  v153 = v152 + *((unsigned __int16 *)v151 + 5);
                                                  v87 = v105;
                                                  if ( v153 > v271 && v271 >= v152 )
                                                  {
                                                    v149 = 0;
                                                    v271 = v153;
                                                  }
                                                  else
                                                  {
                                                    ++v149;
                                                  }
                                                }
                                                else
                                                {
                                                  ++v149;
                                                  v87 = v105;
                                                }
                                                if ( v149 >= v269 )
                                                  goto LABEL_260;
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
LABEL_320:
                                    v80 = v270;
                                    goto LABEL_321;
                                  }
                                  if ( v87 < v246 )
                                    break;
                                  v112 = v254[14];
                                  v113 = v254[12];
                                  v114 = v254[13];
                                  if ( (_BYTE)v261 )
                                  {
                                    glyph_in_lookup_backward = otls::apply::next_glyph_in_lookup_backward(
                                                                 v271,
                                                                 v270,
                                                                 v109,
                                                                 v112,
                                                                 v113,
                                                                 v114,
                                                                 a6);
                                    v109 = v132 + 1;
                                    if ( (glyph_in_lookup_backward & 1) == 0 )
                                      v109 = 0;
                                    LODWORD(v84) = (unsigned __int8)v84;
                                    if ( (glyph_in_lookup_backward & 1) == 0 )
                                      LODWORD(v84) = 1;
                                    v108 = v269;
                                    v87 = v105;
                                    goto LABEL_190;
                                  }
                                  glyph_in_lookup = otls::apply::next_glyph_in_lookup(
                                                      v271,
                                                      v270,
                                                      v112,
                                                      v113,
                                                      v114,
                                                      a6,
                                                      v90);
                                  LOBYTE(v110) = 1;
                                  v111 = v270;
                                  v90 = v270;
                                  v108 = v269;
                                  v87 = v105;
                                  if ( (glyph_in_lookup & 1) != 0 )
                                  {
                                    v90 = v116;
                                    goto LABEL_190;
                                  }
                                }
                                v123 = v90;
                                if ( *(_BYTE *)(a6 + 1264) == 1 )
                                {
                                  v124 = v109 - 1;
                                  if ( v245 == 1 )
                                    v124 = v90;
                                  if ( v124 < v109 && v124 >= 0 )
                                  {
                                    v125 = *(_QWORD *)(a6 + 680);
                                    v126 = *(_QWORD *)(a6 + 704);
                                    v127 = *(_QWORD *)(a6 + 720);
                                    do
                                    {
                                      if ( v124 >= v126 )
                                        core::panicking::panic_bounds_check(v124, v126, &off_18033A490);
                                      v128 = *(unsigned __int16 *)(v125 + 2 * v124);
                                      if ( *(_WORD *)(v125 + 2 * v124) && (_DWORD)v128 != 0xFFFF )
                                      {
                                        v129 = v127 - v128;
                                        if ( v127 < v128 )
                                          core::slice::index::slice_start_index_len_fail(
                                            v128,
                                            *(_QWORD *)(a6 + 720),
                                            &off_18033A3E8);
                                        v130 = (unsigned __int16 *)(*(_QWORD *)(a6 + 712) + v128);
                                        if ( v129 <= 1 )
                                        {
                                          v217 = v130;
                                          v218 = v129;
                                          core::result::unwrap_failed(
                                            (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                                            43,
                                            (unsigned int)&v217,
                                            (unsigned int)&qword_180339CC0,
                                            (__int64)&off_18033A3D0);
                                        }
                                        if ( v87 == *v130 )
                                          break;
                                      }
                                      v124 += v252;
                                      if ( v124 >= v109 )
                                        break;
                                    }
                                    while ( v124 >= 0 );
                                  }
                                  v123 = v216 + v124;
                                }
                                if ( (_BYTE)v261 )
                                  v109 = v123;
                                else
                                  v90 = v123;
LABEL_190:
                                if ( (v84 & 1) == 0 && v90 < v109 )
                                {
                                  otls::apply::apply_lookup(
                                    (unsigned int)&v208,
                                    v272,
                                    v253,
                                    v255,
                                    a5,
                                    a6,
                                    (__int64)v254,
                                    v259,
                                    0,
                                    a9,
                                    a10,
                                    a11,
                                    a12,
                                    a13,
                                    v90,
                                    v109);
                                  result = v209;
                                  if ( ((v209 >= 0x100) & v208) == 0 )
                                  {
                                    v108 = v269;
                                    v87 = v105;
                                    if ( (v208 & 1) != 0 )
                                    {
                                      if ( (_BYTE)v261 )
                                        --v109;
                                      else
                                        ++v90;
                                      v133 = v268;
                                    }
                                    else
                                    {
                                      if ( (_BYTE)v261 )
                                      {
                                        v154 = v109;
                                        v155 = v210;
                                        v109 = v210;
                                      }
                                      else
                                      {
                                        v154 = v210;
                                        v155 = v90;
                                        v90 = v210;
                                      }
                                      v156 = *(_QWORD *)(a5 + 8);
                                      v157 = *(_QWORD *)(a5 + 16);
                                      if ( !v272 )
                                      {
                                        if ( v154 < v155 )
                                          core::slice::index::slice_index_order_fail(v155, v154, &off_18033A1A8);
                                        v271 = v154;
                                        v265 = v157;
                                        if ( v154 > v157 )
                                          core::slice::index::slice_end_index_len_fail(v271, v265, &off_18033A1A8);
                                        otls::gdef::assign_glyph_types_all(v156 + 8 * v155, v154 - v155, a6);
                                        v87 = v105;
                                        v154 = v271;
                                        v157 = v265;
                                        if ( v105 < v246 )
                                        {
                                          v158 = 0;
                                          if ( v271 >= v155 )
                                            v158 = v271 - v155;
                                          v159 = v158 + v270 - v265;
                                          v249 = v158;
                                          v160 = v159 < v158;
                                          v161 = v159 <= v158;
                                          v162 = v270 - v265;
                                          if ( v161 )
                                          {
                                            v167 = *(_QWORD *)(a6 + 704);
                                            if ( v160 )
                                            {
                                              v168 = *(_QWORD *)(a6 + 696) - v167;
                                              v260 = v249 - (v158 + v270 - v265);
                                              if ( v168 >= v260 )
                                              {
                                                v264 = v167;
                                              }
                                              else
                                              {
                                                bumpalo::collections::raw_vec::RawVec_otls::cache::CacheLookupPointer_::reserve_internal_or_panic_otls::cache::CacheLookupPointer_(
                                                  v257,
                                                  v167,
                                                  v260);
                                                v264 = *(_QWORD *)(a6 + 704);
                                              }
                                              v167 = v264 + v260;
                                              if ( v264 + v260 > v264 )
                                              {
                                                if ( *(_QWORD *)(a6 + 696) - v264 < v260 )
                                                {
                                                  bumpalo::collections::raw_vec::RawVec_otls::cache::CacheLookupPointer_::reserve_internal_or_panic_otls::cache::CacheLookupPointer_(
                                                    v257,
                                                    v264,
                                                    v260);
                                                  v264 = *(_QWORD *)(a6 + 704);
                                                }
                                                v169 = *v257;
                                                v170 = (_WORD *)(*v257 + 2 * v264);
                                                if ( v260 >= 2 )
                                                {
                                                  memset_0(v170, 0, 2 * v260 - 2);
                                                  v170 = (_WORD *)(v169 + 2 * (v264 + v260) - 2);
                                                  v264 = v260 + v264 - 1;
                                                }
                                                *v170 = 0;
                                                v167 = v264 + 1;
                                              }
                                              *(_QWORD *)(a6 + 704) = v167;
                                              v171 = v167 - v155;
                                              if ( v167 < v155 )
                                                core::slice::index::slice_start_index_len_fail(
                                                  v155,
                                                  v167,
                                                  &off_18033A430);
                                              v160 = v171 < v260;
                                              v172 = v171 - v260;
                                              if ( v160 )
                                                core::panicking::panic(
                                                  "assertion failed: k <= self.len()assertion failed: mid <= self.len()Al"
                                                  "ignmentErrorDecodeErrorSizeErrorAlignmentSizerust\\shaping\\src\\caching.rs",
                                                  33,
                                                  &off_18033B4D8);
                                              v264 = *v257;
                                              core::slice::rotate::ptr_rotate_u16_(
                                                v172,
                                                v264 + 2 * v155 + 2 * v172,
                                                v260);
                                            }
                                            else
                                            {
                                              v264 = *v257;
                                            }
                                          }
                                          else
                                          {
                                            v163 = *(_QWORD *)(a6 + 704);
                                            v164 = v163 - v155;
                                            if ( v163 < v155 )
                                              core::slice::index::slice_start_index_len_fail(
                                                v155,
                                                *(_QWORD *)(a6 + 704),
                                                &off_18033A460);
                                            v160 = v164 < v162;
                                            v165 = v164 - v162;
                                            if ( v160 )
                                              core::panicking::panic(
                                                "assertion failed: mid <= self.len()AlignmentErrorDecodeErrorSizeErrorAlignmentSizerust\\shaping\\src\\caching.rs",
                                                35,
                                                &off_18033B4F0);
                                            v264 = *(_QWORD *)(a6 + 680);
                                            v260 = v270 - v265;
                                            core::slice::rotate::ptr_rotate_u16_(
                                              v270 - v265,
                                              v264 + 2 * v155 + 2 * v162,
                                              v165);
                                            v166 = v163 - v260;
                                            if ( v163 < v260 )
                                              v166 = v163;
                                            v167 = v166;
                                            *(_QWORD *)(a6 + 704) = v166;
                                          }
                                          v173 = v155 + v249;
                                          if ( __CFADD__(v155, v249) )
                                            core::slice::index::slice_index_order_fail(v155, v173, &off_18033A448);
                                          if ( v173 > v167 )
                                            core::slice::index::slice_end_index_len_fail(
                                              v155 + v249,
                                              v167,
                                              &off_18033A448);
                                          v154 = v271;
                                          v87 = v105;
                                          v157 = v265;
                                          if ( v271 > v155 )
                                          {
                                            memset_0((void *)(v264 + 2 * v155), 0, 2 * v249);
                                            v157 = v265;
                                            v154 = v271;
                                          }
                                        }
                                      }
                                      if ( v154 < v155 )
                                        core::slice::index::slice_index_order_fail(v155, v154, &off_18033A1C0);
                                      if ( v154 > v157 )
                                        core::slice::index::slice_end_index_len_fail(v154, v157, &off_18033A1C0);
                                      if ( v272 )
                                      {
                                        if ( v154 != v155 )
                                        {
                                          v174 = 8 * v155;
                                          v175 = 8 * v154;
                                          do
                                          {
                                            *(_BYTE *)(v156 + v174 + 2) |= 0x20u;
                                            v174 += 8;
                                          }
                                          while ( v175 != v174 );
                                        }
                                      }
                                      else if ( v154 != v155 )
                                      {
                                        v176 = 8 * v155;
                                        v177 = 8 * v154;
                                        do
                                        {
                                          *(_BYTE *)(v156 + v176 + 2) |= 0x10u;
                                          v176 += 8;
                                        }
                                        while ( v177 != v176 );
                                      }
                                      if ( !(_BYTE)v261 )
                                        v109 = v157 + v109 - v270;
                                      v133 = v268;
                                      v108 = v269;
                                    }
LABEL_316:
                                    v271 = *(_QWORD *)(a5 + 8);
                                    v270 = *(_QWORD *)(a5 + 16);
                                    v268 = v133;
                                    continue;
                                  }
LABEL_338:
                                  if ( 2 * v231 )
                                  {
                                    v195 = lpMem;
                                    v196 = result;
                                    v197 = GetProcessHeap();
                                    HeapFree(v197, 0, v195);
                                    result = v196;
                                  }
                                  if ( v228.m256i_i64[0] )
                                  {
                                    v198 = result;
                                    v199 = GetProcessHeap();
                                    HeapFree(v199, 0, v227);
                                    return v198;
                                  }
                                  return result;
                                }
                              }
                            }
                            v80 = v270;
                            v178 = v262;
                          }
                        }
                      }
                      v76 = v87 + 1;
                      if ( v87 + 1 >= v178 )
                        goto LABEL_331;
                    }
                  }
                  v200 = 1;
                }
                v228.m256i_i64[0] = v200;
                v228.m256i_i64[1] = v49;
                v228.m256i_i64[2] = v46;
                core::result::unwrap_failed(
                  (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                  43,
                  (unsigned int)&v228,
                  (unsigned int)&qword_180339C80,
                  (__int64)&off_18033A3A0);
              }
            }
            v50 = 0;
            goto LABEL_43;
          }
          return DWORD2(v40);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006d4d0  push    rbp
0x18006d4d1  push    r15
0x18006d4d3  push    r14
0x18006d4d5  push    r13
0x18006d4d7  push    r12
0x18006d4d9  push    rsi
0x18006d4da  push    rdi
0x18006d4db  push    rbx
0x18006d4dc  sub     rsp, 308h
0x18006d4e3  lea     rbp, [rsp+80h]
0x18006d4eb  mov     [rbp+2C0h+var_40], 0FFFFFFFFFFFFFFFEh
0x18006d4f6  mov     [rbp+2C0h+var_D8], r8
0x18006d4fd  mov     edi, ecx
0x18006d4ff  mov     r14, [rbp+2C0h+arg_28]
0x18006d506  mov     rax, 8000000000000001h
0x18006d510  test    cl, cl
0x18006d512  jz      short loc_18006D52A
0x18006d514  cmp     [r14+0E8h], rax
0x18006d51b  jz      loc_18006EF9C
0x18006d521  lea     r13, [r14+0E8h]
0x18006d528  jmp     short loc_18006D53E
0x18006d52a  cmp     [r14+1C8h], rax
0x18006d531  jz      loc_18006EFA8
0x18006d537  lea     r13, [r14+1C8h]
0x18006d53e  movzx   eax, byte ptr [r14+528h]
0x18006d546  cmp     al, 2
0x18006d548  setz    cl
0x18006d54b  xor     al, dil
0x18006d54e  or      al, cl
0x18006d550  test    al, 1
0x18006d552  jz      loc_18006D5EE
0x18006d558  lea     rax, [r14+4F8h]
0x18006d55f  mov     rsi, [r13+80h]
0x18006d566  movups  xmm0, xmmword ptr [r13+78h]
0x18006d56b  movups  xmm1, xmmword ptr [r13+88h]
0x18006d573  movups  xmmword ptr [rax+10h], xmm1
0x18006d577  movups  xmmword ptr [rax], xmm0
0x18006d57a  mov     rax, rsi
0x18006d57d  shr     rax, 3Ch
0x18006d581  jnz     loc_18006D79A
0x18006d587  mov     r12, rdx
0x18006d58a  mov     rcx, [r14+538h]
0x18006d591  lea     rbx, ds:0[rsi*8]
0x18006d599  mov     rax, [rcx+10h]
0x18006d59d  mov     r15, [rax+20h]
0x18006d5a1  cmp     rbx, r15
0x18006d5a4  ja      loc_18006D77B
0x18006d5aa  sub     r15, rbx
0x18006d5ad  and     r15, 0FFFFFFFFFFFFFFF8h
0x18006d5b1  cmp     r15, [rax]
0x18006d5b4  jb      loc_18006D77B
0x18006d5ba  mov     [rax+20h], r15
0x18006d5be  test    rsi, rsi
0x18006d5c1  jz      short loc_18006D5D6
0x18006d5c3  mov     rcx, r15; void *
0x18006d5c6  xor     edx, edx; Val
0x18006d5c8  mov     r8, rbx; Size
0x18006d5cb  mov     rbx, r9
0x18006d5ce  call    memset_0
0x18006d5d3  mov     r9, rbx
0x18006d5d6  mov     [r14+518h], r15
0x18006d5dd  mov     [r14+520h], rsi
0x18006d5e4  mov     [r14+528h], dil
0x18006d5eb  mov     rdx, r12
0x18006d5ee  mov     r10, [r13+68h]
0x18006d5f2  mov     eax, 102h
0x18006d5f7  test    r10, r10
0x18006d5fa  jz      loc_18006EF16
0x18006d600  mov     r15, rdx
0x18006d603  mov     r8d, [rbp+2C0h+arg_38]
0x18006d60a  mov     ecx, [rbp+2C0h+arg_30]
0x18006d610  mov     rdx, [r13+60h]
0x18006d614  add     r10, r10
0x18006d617  lea     r10, [r10+r10*2]
0x18006d61b  nop     dword ptr [rax+rax+00h]
0x18006d620  cmp     [rdx], ecx
0x18006d622  jz      short loc_18006D633
0x18006d624  add     rdx, 6
0x18006d628  add     r10, 0FFFFFFFFFFFFFFFAh
0x18006d62c  jnz     short loc_18006D620
0x18006d62e  jmp     loc_18006EF16
0x18006d633  mov     rcx, [r13+58h]
0x18006d637  movzx   edx, word ptr [rdx+4]
0x18006d63b  rol     dx, 8
0x18006d63f  movzx   edx, dx
0x18006d642  sub     rcx, rdx
0x18006d645  setb    r11b
0x18006d649  cmp     rcx, 2
0x18006d64d  setb    r10b
0x18006d651  or      r10b, r11b
0x18006d654  jnz     loc_18006EF16
0x18006d65a  mov     r10, rcx
0x18006d65d  and     r10, 0FFFFFFFFFFFFFFFEh
0x18006d661  cmp     r10, 2
0x18006d665  jz      loc_18006EF16
0x18006d66b  mov     r12, r9
0x18006d66e  add     rdx, [r13+50h]
0x18006d672  lea     r10, [rcx-4]
0x18006d676  movzx   r9d, word ptr [rdx+2]
0x18006d67b  rol     r9w, 8
0x18006d680  movzx   r9d, r9w
0x18006d684  lea     r11d, [r9+r9]
0x18006d688  lea     r11, [r11+r11*2]
0x18006d68c  cmp     r11, r10
0x18006d68f  ja      loc_18006EF16
0x18006d695  movzx   eax, word ptr [rdx]
0x18006d698  rol     ax, 8
0x18006d69c  mov     r10, rcx
0x18006d69f  shr     r10, 20h
0x18006d6a3  mov     [rbp+2C0h+var_2A8], rdx
0x18006d6a7  add     rdx, 4
0x18006d6ab  mov     [rbp+2C0h+var_2A0], ecx
0x18006d6ae  mov     [rbp+2C0h+var_29C], r10d
0x18006d6b2  mov     [rbp+2C0h+var_298], rdx
0x18006d6b6  mov     [rbp+2C0h+var_290], r9
0x18006d6ba  mov     [rbp+2C0h+var_288], ax
0x18006d6be  mov     [rbp+2C0h+var_286], r9w
0x18006d6c3  lea     rcx, [rbp+2C0h+var_1D8]
0x18006d6ca  lea     rdx, [rbp+2C0h+var_2A8]
0x18006d6ce  call    otls__scrilang__find_lang_sys
0x18006d6d3  mov     rsi, qword ptr [rbp+2C0h+var_1D8]
0x18006d6da  mov     eax, dword ptr [rbp+2C0h+var_1D8+8]
0x18006d6e0  test    rsi, rsi
0x18006d6e3  jz      loc_18006EF16
0x18006d6e9  mov     dword ptr [rbp+2C0h+var_50], eax
0x18006d6ef  mov     eax, [rbp+2C0h+var_1BC]
0x18006d6f5  mov     [rbp+2C0h+var_270], eax
0x18006d6f8  movups  xmm0, [rbp+2C0h+var_1D8+0Ch]
0x18006d6ff  movaps  [rbp+2C0h+var_280], xmm0
0x18006d703  mov     rax, [r14+530h]
0x18006d70a  mov     rcx, [rax]
0x18006d70d  test    rcx, rcx
0x18006d710  jnz     loc_18006D7C8
0x18006d716  mov     rdx, [r14+540h]
0x18006d71d  mov     rax, [r14+548h]
0x18006d724  mov     rax, [rax+40h]
0x18006d728  lea     rcx, [rbp+2C0h+var_1D8]
0x18006d72f  mov     r8d, 20000h
0x18006d735  call    cs:__guard_dispatch_icall_fptr
0x18006d73b  mov     rcx, qword ptr [rbp+2C0h+var_1D8]
0x18006d742  mov     edx, dword ptr [rbp+2C0h+var_1D8+8]
0x18006d748  test    rcx, rcx
0x18006d74b  jz      loc_18006D885
0x18006d751  mov     eax, dword ptr [rbp+2C0h+var_1D8+0Ch]
0x18006d757  mov     r8, [r14+530h]
0x18006d75e  cmp     qword ptr [r8], 0
0x18006d762  jz      short loc_18006D79F
0x18006d764  lock dec qword ptr [rcx]
0x18006d768  jnz     short loc_18006D7B5
0x18006d76a  shl     rax, 20h
0x18006d76e  or      rax, rdx
0x18006d771  mov     rdx, rax
0x18006d774  call    alloc__sync__Arc_dyn$_otls__client__TableData_assoc$_Target_slice2$_u8________alloc__alloc__Global___drop_slow_dyn$_otls__client__TableData_assoc$_Target_slice2$_u8________alloc__alloc__Global_
0x18006d779  jmp     short loc_18006D7B5
0x18006d77b  mov     edx, 8
0x18006d780  mov     r8, rbx
0x18006d783  mov     r15, r9
0x18006d786  call    bumpalo__Bump__alloc_layout_slow
0x18006d78b  mov     r9, r15
0x18006d78e  mov     r15, rax
0x18006d791  test    rax, rax
0x18006d794  jnz     loc_18006D5BE
0x18006d79a  call    bumpalo__oom
0x18006d79f  mov     r9, [rbp+2C0h+var_1C8]
0x18006d7a6  mov     [r8], rcx
0x18006d7a9  mov     [r8+8], edx
0x18006d7ad  mov     [r8+0Ch], eax
0x18006d7b1  mov     [r8+10h], r9
0x18006d7b5  mov     rax, [r14+530h]
0x18006d7bc  mov     rcx, [rax]
0x18006d7bf  test    rcx, rcx
0x18006d7c2  jz      loc_18006EFFB
0x18006d7c8  mov     rax, [rax+8]
0x18006d7cc  mov     rdx, [rax+10h]
0x18006d7d0  mov     rax, [rax+18h]
0x18006d7d4  dec     rdx
0x18006d7d7  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18006d7db  add     rcx, rdx
0x18006d7de  add     rcx, 10h
0x18006d7e2  call    cs:__guard_dispatch_icall_fptr
0x18006d7e8  test    rax, rax
0x18006d7eb  jz      loc_18006D885
0x18006d7f1  mov     [rbp+2C0h+var_41], dil
0x18006d7f8  mov     rcx, [rbp+2C0h+arg_20]
0x18006d7ff  mov     rcx, [rcx+10h]
0x18006d803  mov     [rbp+2C0h+var_58], rcx
0x18006d80a  lea     r9, aRustOtlsSrcCac; "rust\\otls\\src\\cache.rs"
0x18006d811  mov     r8d, 8
0x18006d817  lea     rbx, dword_1803B41CC
0x18006d81e  cmp     rdx, 0Ch
0x18006d822  mov     [rbp+2C0h+var_D0], rsi
0x18006d829  jb      short loc_18006D88C
0x18006d82b  test    al, 3
0x18006d82d  jnz     loc_18006F1C0
0x18006d833  movzx   ecx, [rbp+2C0h+var_41]
0x18006d83a  mov     ecx, [rax+rcx*4+4]
0x18006d83e  test    rcx, rcx
0x18006d841  jz      short loc_18006D88C
0x18006d843  mov     r8, rdx
0x18006d846  sub     r8, rcx
0x18006d849  jb      loc_18006F007
0x18006d84f  add     rax, rcx
0x18006d852  test    al, 3
0x18006d854  jnz     loc_18006F23D
0x18006d85a  cmp     r8, 7
0x18006d85e  jbe     loc_18006F241
0x18006d864  lea     r9, [rax+8]
0x18006d868  lea     rdx, [r8-8]
0x18006d86c  mov     ecx, [rax+4]
0x18006d86f  lea     r10, ds:0[rcx*4]
0x18006d877  cmp     r10, rdx
0x18006d87a  ja      loc_18006F277
0x18006d880  mov     rbx, rax
0x18006d883  jmp     short loc_18006D88E
0x18006d885  mov     eax, edx
0x18006d887  jmp     loc_18006EF16
0x18006d88c  xor     ecx, ecx
0x18006d88e  lea     rax, [r14+2A8h]
0x18006d895  mov     [rbp+2C0h+var_B8], rax
0x18006d89c  mov     [r14+2C8h], rbx
0x18006d8a3  mov     [r14+2D0h], r8
0x18006d8aa  mov     [r14+2D8h], rbx
0x18006d8b1  mov     [r14+2E0h], r9
0x18006d8b8  mov     [r14+2E8h], rcx
0x18006d8bf  mov     qword ptr [r14+2C0h], 0
0x18006d8ca  mov     byte ptr [r14+4F0h], 1
0x18006d8d2  mov     rsi, [rbp+2C0h+var_58]
0x18006d8d9  test    rsi, rsi
0x18006d8dc  jz      short loc_18006D904
0x18006d8de  cmp     [r14+2B8h], rsi
0x18006d8e5  jnb     short loc_18006D921
0x18006d8e7  mov     rbx, [rbp+2C0h+var_B8]
0x18006d8ee  mov     rcx, rbx
0x18006d8f1  xor     edx, edx
0x18006d8f3  mov     r8, rsi
0x18006d8f6  call    bumpalo__collections__raw_vec__RawVec_otls__cache__CacheLookupPointer___reserve_internal_or_panic_otls__cache__CacheLookupPointer_
0x18006d8fb  mov     rdx, [r14+2C0h]
0x18006d902  jmp     short loc_18006D94C
0x18006d904  lea     rcx, [r14+2F0h]; void *
0x18006d90b  mov     r8d, 200h; Size
0x18006d911  mov     [rbp+2C0h+var_F0], rcx
0x18006d918  xor     edx, edx; Val
0x18006d91a  call    memset_0
0x18006d91f  jmp     short loc_18006D99D
0x18006d921  xor     edx, edx
0x18006d923  mov     rbx, [rbp+2C0h+var_B8]
0x18006d92a  jmp     short loc_18006D94C
0x18006d930  mov     rax, [r14+2A8h]
0x18006d937  mov     word ptr [rax+rdx*2], 0
0x18006d93d  inc     rdx
0x18006d940  mov     [r14+2C0h], rdx
0x18006d947  dec     rsi
0x18006d94a  jz      short loc_18006D96C
0x18006d94c  cmp     rdx, [r14+2B8h]
0x18006d953  jnz     short loc_18006D930
0x18006d955  mov     r8d, 1
0x18006d95b  mov     rcx, rbx
0x18006d95e  call    bumpalo__collections__raw_vec__RawVec_otls__cache__CacheLookupPointer___reserve_internal_or_panic_otls__cache__CacheLookupPointer_
0x18006d963  mov     rdx, [r14+2C0h]
0x18006d96a  jmp     short loc_18006D930
0x18006d96c  lea     rcx, [r14+2F0h]; void *
0x18006d973  movzx   ebx, byte ptr [r14+4F0h]
0x18006d97b  xor     esi, esi
0x18006d97d  mov     r8d, 200h; Size
0x18006d983  mov     [rbp+2C0h+var_F0], rcx
0x18006d98a  xor     edx, edx; Val
0x18006d98c  call    memset_0
0x18006d991  test    bl, 1
0x18006d994  jz      short loc_18006D9B7
0x18006d996  mov     rbx, [r14+2D8h]
0x18006d99d  mov     r11d, dword ptr [rbp+2C0h+var_50]
0x18006d9a4  mov     rdi, r15
0x18006d9a7  movzx   esi, word ptr [rbx]
0x18006d9aa  movzx   ecx, word ptr [rbx+2]
0x18006d9ae  mov     [rbp+2C0h+var_110], rcx
0x18006d9b5  jmp     short loc_18006D9CC
0x18006d9b7  mov     [rbp+2C0h+var_110], 0
0x18006d9c2  mov     r11d, dword ptr [rbp+2C0h+var_50]
0x18006d9c9  mov     rdi, r15
0x18006d9cc  mov     rax, [r14+0D0h]
0x18006d9d3  mov     [rbp+2C0h+var_98], rax
0x18006d9da  mov     rbx, [r14+0D8h]
0x18006d9e1  mov     rax, [r14+0E0h]
0x18006d9e8  mov     qword ptr [r14+0D0h], 0
0x18006d9f3  mov     qword ptr [r14+0D8h], 1
0x18006d9fe  mov     qword ptr [r14+0E0h], 0
0x18006da09  mov     r10, [rdi]
0x18006da0c  mov     rcx, [rdi+8]
0x18006da10  mov     r8b, 1
0x18006da13  test    rcx, rcx
0x18006da16  mov     [rbp+2C0h+var_60], rcx
0x18006da1d  jz      short loc_18006DA56
0x18006da1f  lea     rcx, ds:0[rcx*4]
0x18006da27  lea     rcx, [rcx+rcx*2]
0x18006da2b  xor     edx, edx
0x18006da2d  xor     r8d, r8d
0x18006da30  mov     r9d, r8d
0x18006da33  movzx   r8d, word ptr [r10+rdx+8]
0x18006da39  cmp     r8w, r9w
0x18006da3d  jb      short loc_18006DA50
  ... truncated ...
```
