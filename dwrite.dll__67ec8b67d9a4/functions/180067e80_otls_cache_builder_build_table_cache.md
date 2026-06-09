# otls::cache::builder::build_table_cache

- ea: `0x180067e80`
- end: `0x180069f2f`
- name: `otls::cache::builder::build_table_cache`
- size: `8367`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d0c60`

## callees

- `0x180063c20`
- `0x1800659d0`
- `0x180067e80`
- `0x18006a270`
- `0x18006a400`
- `0x18006a4e0`
- `0x18006a5c0`
- `0x18006a6b0`
- `0x18006a7a0`
- `0x18006a7d0`
- `0x18006a800`
- `0x18006a9d0`
- `0x18006aea0`
- `0x1800dc910`
- `0x180212f4c`
- `0x180316255`
- `0x1803168c1`
- `0x180316940`
- `0x180316980`
- `0x180316ee0`
- `0x1803191c0`

## import_xrefs

- `kernel32!HeapFree` at `0x180069c67`
- `kernel32!HeapFree` at `0x180069c67`
- `kernel32!HeapFree` at `0x180069c8e`
- `kernel32!GetProcessHeap` at `0x180069c59`
- `kernel32!GetProcessHeap` at `0x180069c6d`
- `kernel32!GetProcessHeap` at `0x180069c59`
- `kernel32!GetProcessHeap` at `0x180069c6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall otls::cache::builder::build_table_cache(
        _QWORD *a1,
        char a2,
        __int64 *a3,
        _QWORD *a4,
        __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v7; // r8
  __int64 *v9; // rax
  __int64 *v10; // r9
  unsigned __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // r14
  __int64 v14; // r13
  _WORD *v15; // r12
  __int64 v16; // r15
  unsigned __int64 v17; // rsi
  _QWORD *v18; // rdi
  __m128i **v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // r9
  unsigned __int16 v23; // cx
  unsigned __int64 v24; // r10
  unsigned __int64 v25; // r11
  __int64 v26; // rax
  __int64 v27; // r9
  unsigned __int64 v28; // r10
  bool v29; // cf
  unsigned __int64 v30; // r11
  _WORD *v31; // r10
  __int64 v32; // r14
  __int64 v33; // r15
  unsigned __int64 v34; // rdi
  unsigned __int64 v35; // rcx
  char *v36; // rdi
  unsigned __int16 v37; // r8
  unsigned __int64 v38; // r12
  __int64 v39; // r13
  unsigned __int64 v40; // r8
  unsigned __int16 v41; // cx
  unsigned __int64 v42; // rax
  void *v43; // rax
  __int64 v44; // r15
  __int64 v45; // r12
  unsigned __int64 v46; // r13
  bool v47; // cl
  unsigned __int64 v48; // r9
  unsigned __int64 v49; // r14
  unsigned __int64 v50; // r8
  unsigned __int64 v51; // r10
  __int64 v52; // rax
  unsigned __int16 v53; // ax
  __int64 v54; // r11
  unsigned __int64 v55; // rbx
  unsigned __int16 v56; // ax
  unsigned __int64 v57; // rcx
  _WORD *v58; // r11
  unsigned __int64 v59; // rcx
  unsigned __int64 v60; // rax
  _WORD *v61; // rbx
  unsigned __int64 v62; // rax
  __int16 v63; // dx
  __int16 v64; // cx
  unsigned __int16 v65; // cx
  unsigned __int64 v66; // rcx
  __int16 v67; // dx
  __int16 v68; // ax
  unsigned __int16 v69; // ax
  __int64 v70; // rax
  __int64 v71; // rax
  _WORD *v72; // rcx
  unsigned __int64 v73; // rcx
  unsigned __int64 v74; // rax
  __int16 v75; // ax
  unsigned __int64 v76; // rax
  __m128i *v77; // rcx
  __int16 v78; // dx
  __int64 v79; // rsi
  unsigned __int64 v80; // rax
  _WORD *v81; // rcx
  __int64 v82; // r10
  _WORD *v83; // rdx
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rax
  unsigned __int64 v86; // rax
  unsigned __int64 v87; // rax
  unsigned __int64 v88; // rcx
  __int64 v89; // rax
  __int16 v90; // cx
  __int64 v91; // rcx
  __int16 v92; // ax
  unsigned __int16 v93; // cx
  _WORD *v94; // rdx
  __int16 v95; // r9
  __m128i **v96; // r10
  __m128i *v97; // r11
  __int64 *v98; // rsi
  __int16 *v99; // rdi
  __m128i *v100; // r15
  unsigned __int16 *v101; // rbx
  unsigned __int64 v102; // rcx
  _WORD *v103; // rbx
  __int16 v104; // cx
  __int64 v105; // rcx
  _WORD *v106; // r11
  unsigned __int64 v107; // r9
  unsigned __int64 v108; // r10
  unsigned __int64 v109; // rdx
  unsigned __int64 v110; // rax
  _WORD *v111; // rcx
  __int64 v112; // r10
  _WORD *v113; // rdx
  int v114; // edx
  __int16 v115; // r9
  int v116; // ebx
  __int16 v117; // r8
  unsigned __int64 v118; // r11
  unsigned __int16 v119; // r11
  unsigned __int64 v120; // rdx
  unsigned __int16 v121; // si
  __int16 v122; // di
  __m128i v123; // xmm0
  __int16 v124; // r9
  int v125; // ebx
  __int16 v126; // r8
  unsigned __int64 v127; // r11
  unsigned __int16 v128; // r11
  unsigned __int64 v129; // rdx
  unsigned __int16 v130; // si
  unsigned __int16 *v131; // rax
  unsigned __int16 *v132; // rdi
  unsigned __int16 *v133; // rbx
  int v134; // r12d
  unsigned __int16 v135; // r15
  bool v136; // di
  _WORD *v137; // rax
  unsigned __int64 v138; // r13
  int v139; // esi
  __int64 v140; // rdx
  bool v141; // zf
  __int64 v142; // rax
  unsigned __int16 *v143; // rbx
  _WORD *v144; // rax
  unsigned __int64 v145; // r13
  unsigned __int16 *v146; // rdx
  int v147; // esi
  __int64 v148; // rdx
  unsigned __int64 v149; // rcx
  __int16 v150; // di
  unsigned __int64 v151; // rbx
  unsigned __int64 v152; // rax
  _WORD *v153; // rdi
  unsigned __int64 v154; // r8
  unsigned __int64 v155; // rcx
  __int64 v156; // r12
  unsigned __int64 v157; // rdx
  unsigned __int64 v158; // r10
  unsigned __int64 v159; // r15
  unsigned __int64 v160; // r13
  unsigned __int64 v161; // r11
  unsigned __int16 v162; // r12
  unsigned __int64 v163; // rax
  unsigned __int64 v164; // rsi
  __int16 v165; // r10
  unsigned __int64 v166; // rax
  unsigned __int64 v167; // r14
  __int16 v168; // ax
  bool v169; // r9
  unsigned __int64 v170; // r10
  unsigned __int64 v171; // rsi
  unsigned __int64 v172; // rax
  __int64 v173; // r9
  __int64 v174; // rcx
  __m128i v175; // xmm1
  __int64 v176; // rcx
  __m128i v177; // xmm0
  __m128i v178; // xmm2
  __m128i v179; // xmm3
  __m128i v180; // xmm0
  __m128i v181; // xmm1
  unsigned int v182; // ecx
  char *v183; // rdx
  __int64 v184; // rax
  __int64 v185; // rcx
  __int64 v186; // rdx
  unsigned __int64 v187; // r8
  __int64 v188; // r10
  __int64 v189; // r9
  __int64 v190; // rsi
  unsigned __int64 v191; // r10
  unsigned __int64 v192; // rcx
  unsigned __int64 v193; // r9
  unsigned __int64 v194; // r14
  unsigned __int64 v195; // r15
  __int64 v196; // rcx
  unsigned __int16 v197; // r11
  unsigned __int64 v198; // rax
  unsigned __int64 v199; // r12
  unsigned __int64 v200; // rcx
  unsigned __int64 v201; // rax
  __int64 v202; // r9
  __int64 v203; // rcx
  unsigned __int64 v204; // rsi
  unsigned __int64 v205; // rax
  __int64 v206; // r9
  unsigned __int64 v207; // rax
  char *v208; // r13
  __int64 v209; // r10
  unsigned __int64 v210; // r13
  __int64 v211; // rax
  unsigned __int64 v212; // r9
  unsigned __int64 v213; // rcx
  unsigned __int64 v214; // r9
  __int64 v215; // rcx
  __int16 v216; // ax
  unsigned __int64 v217; // r9
  unsigned __int64 v218; // rax
  unsigned __int64 v219; // r9
  __int16 v220; // ax
  bool v221; // r13
  unsigned __int64 v222; // rcx
  _DWORD *v223; // rax
  _DWORD *v224; // rax
  void *v225; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v227; // rax
  unsigned __int16 *v228; // [rsp+38h] [rbp-48h]
  __int64 v229; // [rsp+40h] [rbp-40h]
  _WORD *v230; // [rsp+48h] [rbp-38h]
  bool v231; // [rsp+50h] [rbp-30h]
  unsigned __int64 v232; // [rsp+58h] [rbp-28h]
  __int64 v233; // [rsp+60h] [rbp-20h]
  unsigned __int64 v234; // [rsp+68h] [rbp-18h]
  unsigned __int64 v235; // [rsp+70h] [rbp-10h]
  unsigned __int64 v236; // [rsp+78h] [rbp-8h]
  unsigned __int64 v237; // [rsp+80h] [rbp+0h]
  unsigned __int64 v238; // [rsp+88h] [rbp+8h]
  __int64 v239; // [rsp+90h] [rbp+10h] BYREF
  __int64 (__fastcall *v240)(); // [rsp+98h] [rbp+18h]
  __int64 *v241; // [rsp+A0h] [rbp+20h]
  __int64 (__fastcall *v242)(); // [rsp+A8h] [rbp+28h]
  __int16 v243; // [rsp+B0h] [rbp+30h]
  __int16 v244; // [rsp+B2h] [rbp+32h]
  __int16 v245; // [rsp+B4h] [rbp+34h]
  __int16 v246; // [rsp+B6h] [rbp+36h]
  __m128i v247; // [rsp+B8h] [rbp+38h]
  __m128i v248; // [rsp+C8h] [rbp+48h]
  __int64 v249; // [rsp+D8h] [rbp+58h]
  unsigned __int64 v250; // [rsp+E0h] [rbp+60h]
  unsigned __int64 v251; // [rsp+E8h] [rbp+68h]
  __m128i v252; // [rsp+F0h] [rbp+70h] BYREF
  __m128i v253; // [rsp+100h] [rbp+80h] BYREF
  __int64 v254; // [rsp+110h] [rbp+90h]
  __int64 v255; // [rsp+118h] [rbp+98h] BYREF
  __int64 *v256; // [rsp+120h] [rbp+A0h]
  __int64 *v257; // [rsp+128h] [rbp+A8h]
  _WORD *v258; // [rsp+130h] [rbp+B0h]
  unsigned __int64 v259; // [rsp+138h] [rbp+B8h]
  __int64 v260; // [rsp+140h] [rbp+C0h]
  __int64 v261; // [rsp+148h] [rbp+C8h]
  unsigned __int64 v262; // [rsp+150h] [rbp+D0h]
  _WORD *v263; // [rsp+158h] [rbp+D8h]
  unsigned __int64 v264; // [rsp+160h] [rbp+E0h]
  __int64 v265; // [rsp+168h] [rbp+E8h]
  _QWORD *v266; // [rsp+170h] [rbp+F0h]
  __int64 v267; // [rsp+178h] [rbp+F8h]
  __int64 v268; // [rsp+180h] [rbp+100h] BYREF
  __int64 v269; // [rsp+188h] [rbp+108h]
  __m128i **v270; // [rsp+190h] [rbp+110h]
  __int64 v271; // [rsp+198h] [rbp+118h]
  unsigned __int64 v272; // [rsp+1A0h] [rbp+120h]
  _WORD *v273; // [rsp+1A8h] [rbp+128h]
  __m128i v274; // [rsp+1B0h] [rbp+130h]
  __m128i v275; // [rsp+1C0h] [rbp+140h]
  __int64 v276; // [rsp+1D0h] [rbp+150h]
  __int16 v277; // [rsp+1DCh] [rbp+15Ch] BYREF
  __int16 v278; // [rsp+1DEh] [rbp+15Eh]
  __int32 v279; // [rsp+1E0h] [rbp+160h]
  __int32 v280; // [rsp+1E4h] [rbp+164h]
  __int16 v281; // [rsp+1E8h] [rbp+168h] BYREF
  int v282; // [rsp+1ECh] [rbp+16Ch]
  __int16 v283; // [rsp+1F0h] [rbp+170h] BYREF
  __int64 v284; // [rsp+1F8h] [rbp+178h] BYREF
  LPVOID lpMem; // [rsp+200h] [rbp+180h]
  unsigned __int64 v286; // [rsp+208h] [rbp+188h]
  __int64 v287; // [rsp+210h] [rbp+190h]
  int v288; // [rsp+21Ch] [rbp+19Ch]
  __int64 v289; // [rsp+220h] [rbp+1A0h]
  unsigned __int16 v290; // [rsp+228h] [rbp+1A8h]
  __int16 v291; // [rsp+22Ah] [rbp+1AAh]
  __int16 v292; // [rsp+22Ch] [rbp+1ACh]
  __int16 v293; // [rsp+22Eh] [rbp+1AEh]
  unsigned __int64 v294; // [rsp+230h] [rbp+1B0h]
  char *v295; // [rsp+238h] [rbp+1B8h]
  _QWORD *v296; // [rsp+240h] [rbp+1C0h]
  char v297; // [rsp+24Fh] [rbp+1CFh]
  unsigned __int64 v298; // [rsp+250h] [rbp+1D0h]
  __int64 v299; // [rsp+258h] [rbp+1D8h] BYREF
  unsigned __int16 *v300; // [rsp+260h] [rbp+1E0h]
  unsigned __int64 v301; // [rsp+268h] [rbp+1E8h]
  __int64 v302; // [rsp+270h] [rbp+1F0h]
  unsigned __int64 v303; // [rsp+278h] [rbp+1F8h]
  __int64 v304; // [rsp+280h] [rbp+200h]

  v304 = -2;
  v7 = a4[16];
  if ( !v7 )
  {
    a1[1] = 0;
    *(_DWORD *)a1 = 0;
    return;
  }
  v251 = a6;
  v9 = qword_1803B42E0;
  if ( *(_DWORD *)a3 != 3 )
    v9 = a3;
  v256 = v9;
  v10 = qword_1803B4300;
  if ( *((_DWORD *)a3 + 8) != 3 )
    v10 = a3 + 4;
  v257 = v10;
  v287 = a5;
  v252.m128i_i64[0] = v7;
  if ( v7 >> 61 )
  {
    v239 = (__int64)&v252;
    v240 = core::fmt::num::imp::impl_20::fmt;
    v241 = &qword_1803B3EF8;
    v242 = core::fmt::num::imp::impl_20::fmt;
    v268 = (__int64)&off_180339CE0;
    v269 = 2;
    v272 = 0;
    v270 = (__m128i **)&v239;
    v271 = 2;
    core::panicking::panic_fmt(&v268, &off_180339D00);
  }
  v297 = a2;
  v266 = a1;
  v295 = (char *)v7;
  v11 = v7 & 0x3F;
  v12 = (v7 >> 6) - ((v11 == 0) - 1LL);
  if ( v7 >> 6 == (v11 == 0) - 1LL )
  {
    v13 = 8;
  }
  else
  {
    v13 = std::sys::alloc::windows::process_heap_alloc(0, 8 * v12);
    if ( !v13 )
      alloc::alloc::handle_alloc_error(8, 8 * v12);
  }
  v252 = (__m128i)(unsigned __int64)v13;
  v253.m128i_i64[0] = v12;
  v284 = (__int64)v295;
  v299 = v12 << 6;
  if ( (unsigned __int64)v295 > v12 << 6 )
  {
    v239 = (__int64)&v284;
    v240 = core::fmt::num::imp::impl_20::fmt;
    v241 = &v299;
    v242 = core::fmt::num::imp::impl_20::fmt;
    v268 = (__int64)&off_180339CE0;
    v269 = 2;
    v272 = 0;
    v270 = (__m128i **)&v239;
    v271 = 2;
    core::panicking::panic_fmt(&v268, &off_180339D18);
  }
  v233 = (__int64)a3;
  memset_0((void *)v13, 0, 8 * v12);
  v14 = a4[6];
  v15 = (_WORD *)a4[21];
  v296 = (_QWORD *)v13;
  if ( v14 )
  {
    v294 = 0;
    v16 = 0;
    v17 = (unsigned __int64)v295;
    while ( 1 )
    {
      otls::features::FeatureListTable::feature_table(&v268, a4, v16);
      if ( !v268 )
        break;
      if ( v271 )
      {
        v19 = v270;
        v20 = 2 * v271;
        v21 = 0;
        v22 = v294;
        v18 = v296;
        do
        {
          v23 = __ROL2__(*(_WORD *)((char *)v19 + v21), 8);
          if ( v17 > v23 )
          {
            v18[v23 >> 6] |= 1LL << v23;
            v24 = v294;
            if ( v22 < v23 )
              v24 = v23;
            v294 = v24;
            if ( v22 <= v23 )
              v22 = v23;
          }
          v21 += 2;
        }
        while ( v20 != v21 );
      }
      else
      {
        v18 = v296;
      }
      if ( ++v16 == v14 )
        goto LABEL_28;
    }
LABEL_319:
    *v266 = 0x30200000001LL;
    v18 = v296;
    goto LABEL_375;
  }
  v18 = (_QWORD *)v13;
  v294 = 0;
  v17 = (unsigned __int64)v295;
LABEL_28:
  if ( v15 )
  {
    v25 = a4[22];
    if ( v25 <= 3 )
    {
      v268 = 1;
      v269 = (__int64)v15;
      v270 = (__m128i **)v25;
      core::result::unwrap_failed(
        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
        43,
        (unsigned int)&v268,
        (unsigned int)&qword_180339C20,
        (__int64)&off_180339DB8);
    }
    if ( *v15 == 256 )
    {
      v298 = a4[24];
      if ( v298 )
      {
        v303 = (unsigned __int64)v15;
        v26 = a4[23];
        v27 = 0;
        v289 = v25;
        v265 = v26;
        while ( 1 )
        {
          v28 = _byteswap_ulong(*(_DWORD *)(v26 + 8 * v27 + 4));
          v29 = v25 < v28;
          v30 = v25 - v28;
          if ( v29 )
            goto LABEL_319;
          if ( v30 < 6 )
            goto LABEL_319;
          v31 = (_WORD *)(v303 + v28);
          v32 = (unsigned __int16)__ROL2__(v31[2], 8);
          if ( 3 * (unsigned __int64)(unsigned int)(2 * v32) > v30 - 6 )
            goto LABEL_319;
          if ( v32 && *v31 == 256 )
            break;
LABEL_33:
          ++v27;
          v18 = v296;
          v25 = v289;
          v26 = v265;
          if ( v27 == v298 )
            goto LABEL_53;
        }
        v33 = 0;
        while ( 1 )
        {
          v34 = _byteswap_ulong(*(_DWORD *)&v31[3 * v33 + 4]);
          v35 = v30 - v34;
          if ( v30 < v34 )
            goto LABEL_319;
          if ( v35 < 4 )
            goto LABEL_319;
          v36 = (char *)v31 + v34;
          v37 = __ROL2__(*((_WORD *)v36 + 1), 8);
          v38 = 2 * (unsigned int)v37;
          if ( v38 > v35 - 4 )
            goto LABEL_319;
          if ( v37 )
          {
            v39 = 0;
            v40 = v294;
            do
            {
              v41 = __ROL2__(*(_WORD *)&v36[v39 + 4], 8);
              if ( v17 > v41 )
              {
                v296[v41 >> 6] |= 1LL << v41;
                v17 = (unsigned __int64)v295;
                v42 = v294;
                if ( v40 < v41 )
                  v42 = v41;
                v294 = v42;
                if ( v40 <= v41 )
                  v40 = v41;
              }
              v39 += 2;
            }
            while ( v38 != v39 );
          }
          if ( ++v33 == v32 )
            goto LABEL_33;
        }
      }
    }
  }
LABEL_53:
  v43 = (void *)std::sys::alloc::windows::process_heap_alloc(0, 4096);
  if ( !v43 )
    alloc::alloc::handle_alloc_error(2, 4096);
  v234 = v251 >> 2;
  v229 = 8 * v17;
  v284 = 1024;
  lpMem = v43;
  v286 = 0;
  v44 = a4[15];
  v45 = a4[17];
  v46 = a4[18];
  v47 = 0;
  v48 = 0;
  v303 = 0;
  v267 = 0;
  v49 = 0;
  while ( 2 )
  {
    v50 = v294;
    if ( v47 || v48 > v294 || (v267 & 1) != 0 )
    {
      v152 = v303;
      v151 = v303;
      goto LABEL_377;
    }
    v51 = v48;
    while ( 1 )
    {
      v51 += v48 < v294;
      v268 = v48;
      if ( v48 >= v17 )
        bitvec::slice::api::impl_2::index::closure_0_usize_bitvec::order::Lsb0_(&v268, v229, v294);
      v52 = v18[v48 >> 6];
      if ( _bittest64(&v52, v48) )
      {
        v53 = __ROL2__(*(_WORD *)(v44 + 2 * v48), 8);
        v54 = v53;
        v55 = v46 - v53;
        if ( v46 >= v53 && v55 >= 6 )
        {
          v56 = __ROL2__(*(_WORD *)(v45 + v53 + 4), 8);
          v57 = 2 * (unsigned int)v56;
          if ( v55 - 6 >= v57 )
            break;
        }
      }
      if ( v48 < v294 )
      {
        v48 = v51;
        if ( v51 <= v294 )
          continue;
      }
      v49 = v17;
      v152 = v303;
      v151 = v303;
      goto LABEL_249;
    }
    v58 = (_WORD *)(v45 + v54);
    v231 = v48 >= v294;
    v258 = v58 + 3;
    v50 = (unsigned __int16)v58[1];
    LOWORD(v50) = __ROL2__(v50, 8);
    LODWORD(v265) = v50;
    if ( (v50 & 0x10) == 0 )
    {
      v282 = 0;
LABEL_72:
      v288 = v57;
      goto LABEL_73;
    }
    LOWORD(v50) = 1;
    v282 = v50;
    if ( v55 - 6 - v57 >= 2 )
    {
      LODWORD(v57) = *(unsigned __int16 *)((char *)v258 + v57);
      LOWORD(v57) = __ROL2__(v57, 8);
      goto LABEL_72;
    }
    v288 = 0;
LABEL_73:
    v278 = *v58;
    v291 = __ROL2__(v278, 8);
    LODWORD(v265) = v265 & 0xFF1F;
    v230 = &v258[v56];
    v289 = 4 * v303;
    LODWORD(v298) = 0;
    v250 = v48;
    v232 = v51;
    v263 = v58;
    v264 = v55;
    v260 = v44;
    v261 = v45;
    v262 = v46;
    while ( v258 != v230 )
    {
      v59 = (unsigned __int16)__ROL2__(*v258, 8);
      v60 = v55 - v59;
      if ( v55 >= v59 && v60 >= 2 )
      {
        v61 = (_WORD *)((char *)v58 + v59);
        v290 = __ROL2__(*(_WORD *)((char *)v58 + v59), 8);
        v259 = v60;
        if ( (v267 & 1) != 0 )
        {
LABEL_381:
          v151 = v286;
          v152 = v303;
          goto LABEL_249;
        }
      }
      else
      {
        v61 = 0;
        if ( (v267 & 1) != 0 )
          goto LABEL_381;
      }
      if ( !v61 )
      {
        *v266 = 0x30200000001LL;
        if ( v284 )
          goto LABEL_374;
        goto LABEL_375;
      }
      if ( v297 )
      {
        if ( v278 == 2304 )
        {
          v50 = v259;
          if ( v259 < 8 )
            goto LABEL_195;
          v62 = _byteswap_ulong(*((_DWORD *)v61 + 1));
          v50 = v259 - v62;
          if ( v259 < v62 || v259 - v62 < 2 )
            goto LABEL_195;
          v63 = __ROL2__(v61[1], 8);
          v64 = *(_WORD *)((char *)v61 + v62);
          v61 = (_WORD *)((char *)v61 + v62);
          v65 = __ROL2__(v64, 8);
        }
        else
        {
          v65 = v290;
          v50 = v259;
          v63 = v291;
        }
        v70 = v65;
        switch ( v63 )
        {
          case 1:
            if ( v65 == 2 )
            {
              if ( v50 >= 8
                && (unsigned __int8)(2
                                   * ((286331153
                                     * (((134480385 * (unsigned int)*((unsigned __int8 *)v61 + 5)) >> 3) & 0x11111111)) >> 28))
                 * (unsigned __int64)(unsigned __int16)__ROL2__(v61[3], 8)
                 + 8 <= v50 )
              {
                v71 = 2;
                v72 = v61;
                v61 = 0;
                goto LABEL_167;
              }
            }
            else if ( v65 == 1 && v50 >= 6 )
            {
              v71 = *((unsigned __int8 *)v61 + 5);
              if ( v50 >= (unsigned __int8)(2
                                          * ((286331153 * (((unsigned int)(134480385 * v71) >> 3) & 0x11111111)) >> 28)
                                          + 6) )
              {
                v72 = (_WORD *)v50;
                v50 = 1;
LABEL_167:
                v268 = (__int64)v61;
                v269 = (__int64)v72;
                v270 = (__m128i **)v50;
                v271 = v71;
                enum2__otls::gpos::singlpos::SinglePosLookup_::get_coverage_table(&v299, &v268);
                goto LABEL_196;
              }
            }
            break;
          case 2:
            if ( v65 == 2 )
            {
              if ( v50 >= 0x10 )
              {
                v105 = *((unsigned __int8 *)v61 + 5);
                v114 = *((unsigned __int8 *)v61 + 7);
                v51 = (unsigned __int16)__ROL2__(v61[6], 8);
                v48 = (unsigned __int16)__ROL2__(v61[7], 8);
                if ( (unsigned __int8)(2
                                     * (((286331153 * (((unsigned int)(134480385 * v105) >> 3) & 0x11111111)) >> 28)
                                      + ((286331153 * (((unsigned int)(134480385 * v114) >> 3) & 0x11111111)) >> 28)))
                   * v48
                   * v51
                   + 16 <= v50 )
                {
                  v107 = v48 << 48;
                  v108 = v51 << 32;
                  v109 = v107 | v108 | (unsigned int)(v114 << 16);
                  v106 = v61;
                  v61 = 0;
                  goto LABEL_171;
                }
              }
            }
            else if ( v65 == 1 && v50 >= 0xA )
            {
              v105 = (unsigned __int16)__ROL2__(v61[4], 8);
              if ( (unsigned int)(2 * v105) <= v50 - 10 )
              {
                v106 = (_WORD *)v50;
                v70 = (__int64)(v61 + 5);
                LOWORD(v107) = *((unsigned __int8 *)v61 + 5);
                LOWORD(v108) = *((unsigned __int8 *)v61 + 7);
                v50 = 1;
                v109 = 0;
LABEL_171:
                v268 = (__int64)v61;
                v269 = (__int64)v106;
                v270 = (__m128i **)v50;
                v271 = v70;
                v272 = v109 | v105;
                LOWORD(v273) = v107;
                WORD1(v273) = v108;
                enum2__otls::gpos::pairpos::PairPosLookup_::get_coverage_table(&v299, &v268);
                goto LABEL_196;
              }
            }
            break;
          case 3:
            if ( v50 < 6 || *v61 != 256 )
              break;
            v73 = v50 - 6;
            v74 = 4 * (unsigned int)(unsigned __int16)__ROL2__(v61[2], 8);
            goto LABEL_139;
          case 4:
            if ( v65 != 1 || v50 <= 0xB )
              break;
            goto LABEL_157;
          case 5:
            if ( v65 != 1 || v50 <= 0xB )
              break;
            goto LABEL_157;
          case 6:
            if ( v65 != 1 || v50 <= 0xB )
              break;
LABEL_157:
            otls::gpos::singlpos::OneSinglePosSubTable::coverage(&v299, v61, v50);
            goto LABEL_196;
          case 7:
            if ( v65 == 3 )
            {
              if ( v50 >= 6 )
              {
                v128 = __ROL2__(v61[1], 8);
                v110 = v128;
                v129 = 2 * (unsigned int)v128;
                if ( v50 - 6 >= v129 )
                {
                  v130 = __ROL2__(v61[2], 8);
                  v48 = v130;
                  v51 = 4 * (unsigned int)v130;
                  if ( v51 <= v50 - 6 - v129 )
                  {
                    v150 = __ROL2__(*v61, 8);
                    v111 = v61 + 3;
                    v113 = &v61[v129 / 2 + 3];
                    v112 = 2;
                    LOWORD(v280) = v128;
                    v127 = v50;
                    v126 = v150;
                    HIWORD(v280) = v130;
                    goto LABEL_191;
                  }
                }
              }
            }
            else if ( v65 == 2 )
            {
              if ( v50 >= 8 )
              {
                v110 = (unsigned __int16)__ROL2__(v61[3], 8);
                if ( 2 * (unsigned int)(unsigned __int16)v110 <= v50 - 8 )
                {
                  v111 = v61 + 4;
                  v124 = v61[1];
                  v113 = v61;
                  v125 = (unsigned __int16)v61[2];
                  LOWORD(v125) = __ROL2__(v125, 8);
                  v61 = (_WORD *)((unsigned __int16)__ROL2__(v124, 8)
                                | v238 & 0xFFFFFFFF00000000uLL
                                | (unsigned int)(v125 << 16));
                  v112 = 1;
                  v48 = v50;
                  goto LABEL_190;
                }
              }
            }
            else if ( v65 == 1 && v50 >= 6 )
            {
              v110 = (unsigned __int16)__ROL2__(v61[2], 8);
              if ( 2 * (unsigned int)(unsigned __int16)v110 <= v50 - 6 )
              {
                v111 = v61 + 3;
                v112 = 0;
                v113 = v61;
                v48 = v50;
                v61 = (_WORD *)((unsigned __int16)__ROL2__(v61[1], 8) | v238 & 0xFFFFFFFFFFFF0000uLL);
LABEL_190:
                v126 = v293;
                v127 = v237;
LABEL_191:
                v269 = (__int64)v111;
                v270 = (__m128i **)v110;
                v271 = (__int64)v113;
                v272 = v48;
                v273 = v61;
                v237 = v127;
                v274.m128i_i64[0] = v127;
                v293 = v126;
                v274.m128i_i16[4] = v126;
                *(__int32 *)((char *)&v274.m128i_i32[2] + 2) = v280;
                v268 = v112;
                enum2__otls::gsub_gpos_shared::context::ContextLookup_::get_coverage_table(&v299, &v268);
                v238 = (unsigned __int64)v61;
                goto LABEL_196;
              }
            }
            break;
          case 8:
            goto LABEL_102;
          default:
            break;
        }
      }
      else
      {
        if ( v278 == 1792 )
        {
          v50 = v259;
          if ( v259 < 8 )
            goto LABEL_195;
          v66 = _byteswap_ulong(*((_DWORD *)v61 + 1));
          v50 = v259 - v66;
          if ( v259 < v66 || v259 - v66 < 2 )
            goto LABEL_195;
          v67 = __ROL2__(v61[1], 8);
          v68 = *(_WORD *)((char *)v61 + v66);
          v61 = (_WORD *)((char *)v61 + v66);
          v69 = __ROL2__(v68, 8);
        }
        else
        {
          v69 = v290;
          v50 = v259;
          v67 = v291;
        }
        switch ( v67 )
        {
          case 1:
            if ( v50 < 6 )
              break;
            v92 = __ROL2__(*v61, 8);
            if ( v92 == 1 )
            {
              v95 = __ROL2__(v61[1], 8);
              v93 = __ROL2__(v61[2], 8);
              v94 = 0;
              v96 = (__m128i **)&v239;
              v97 = &v252;
              v98 = &v255;
              v99 = (__int16 *)&v255 + 1;
              v100 = (__m128i *)v61;
              v101 = (unsigned __int16 *)&v255 + 2;
              goto LABEL_237;
            }
            if ( v92 == 2 )
            {
              v93 = __ROL2__(v61[2], 8);
              LOWORD(v51) = v93;
              v48 = 2 * (unsigned int)v93;
              if ( v48 <= v50 - 6 )
              {
                v94 = v61 + 3;
                v95 = __ROL2__(v61[1], 8);
                v239 = v93;
                v96 = (__m128i **)&v252;
                v97 = (__m128i *)&v255;
                v98 = (__int64 *)&v283;
                v99 = &v277;
                v100 = (__m128i *)v61;
                v101 = (unsigned __int16 *)&v281;
LABEL_237:
                *v96 = v100;
                v97->m128i_i64[0] = v50;
                *(_WORD *)v98 = v92;
                *v99 = v95;
                *v101 = v93;
                v268 = (__int64)v94;
                v269 = v239;
                v270 = (__m128i **)v252.m128i_i64[0];
                v271 = v255;
                LOWORD(v272) = v283;
                WORD1(v272) = v277;
                WORD2(v272) = v281;
                enum2__otls::gsub::singlsub::SingleSubstLookup_::get_coverage_table(&v299, &v268);
                goto LABEL_196;
              }
            }
            break;
          case 2:
          case 3:
          case 4:
            if ( v50 < 6 || *v61 != 256 )
              break;
            v73 = v50 - 6;
            v74 = 2 * (unsigned int)(unsigned __int16)__ROL2__(v61[2], 8);
LABEL_139:
            if ( v74 > v73 )
              break;
            v102 = (unsigned __int16)__ROL2__(v61[1], 8);
            v89 = 1;
            v29 = v50 < v102;
            v50 -= v102;
            if ( v29 || v50 < 4 )
              goto LABEL_242;
            v103 = (_WORD *)((char *)v61 + v102);
            v104 = __ROL2__(*v103, 8);
            if ( v104 != 2 )
            {
              if ( v104 == 1 )
              {
                v50 -= 4LL;
                v91 = (unsigned __int16)__ROL2__(v103[1], 8);
                if ( 2 * (unsigned int)(unsigned __int16)v91 <= v50 )
                {
                  v300 = 0;
                  v301 = (unsigned __int64)(v103 + 2);
                  goto LABEL_146;
                }
              }
              goto LABEL_242;
            }
            v50 -= 4LL;
            v149 = (unsigned __int16)__ROL2__(v103[1], 8);
            if ( 3 * (unsigned __int64)(2 * (unsigned int)(unsigned __int16)v149) > v50 )
              goto LABEL_242;
            v300 = v103 + 2;
            goto LABEL_240;
          case 5:
            if ( v69 == 3 )
            {
              if ( v50 >= 6 )
              {
                v119 = __ROL2__(v61[1], 8);
                v80 = v119;
                v120 = 2 * (unsigned int)v119;
                if ( v50 - 6 >= v120 )
                {
                  v121 = __ROL2__(v61[2], 8);
                  v48 = v121;
                  v51 = 4 * (unsigned int)v121;
                  if ( v51 <= v50 - 6 - v120 )
                  {
                    v122 = __ROL2__(*v61, 8);
                    v81 = v61 + 3;
                    v83 = &v61[v120 / 2 + 3];
                    v82 = 2;
                    LOWORD(v279) = v119;
                    v118 = v50;
                    v117 = v122;
                    HIWORD(v279) = v121;
                    goto LABEL_176;
                  }
                }
              }
            }
            else if ( v69 == 2 )
            {
              if ( v50 >= 8 )
              {
                v80 = (unsigned __int16)__ROL2__(v61[3], 8);
                if ( 2 * (unsigned int)(unsigned __int16)v80 <= v50 - 8 )
                {
                  v81 = v61 + 4;
                  v115 = v61[1];
                  v83 = v61;
                  v116 = (unsigned __int16)v61[2];
                  LOWORD(v116) = __ROL2__(v116, 8);
                  v61 = (_WORD *)((unsigned __int16)__ROL2__(v115, 8)
                                | v236 & 0xFFFFFFFF00000000uLL
                                | (unsigned int)(v116 << 16));
                  v82 = 1;
                  v48 = v50;
                  goto LABEL_175;
                }
              }
            }
            else if ( v69 == 1 && v50 >= 6 )
            {
              v80 = (unsigned __int16)__ROL2__(v61[2], 8);
              if ( 2 * (unsigned int)(unsigned __int16)v80 <= v50 - 6 )
              {
                v81 = v61 + 3;
                v82 = 0;
                v83 = v61;
                v48 = v50;
                v61 = (_WORD *)((unsigned __int16)__ROL2__(v61[1], 8) | v236 & 0xFFFFFFFFFFFF0000uLL);
LABEL_175:
                v117 = v292;
                v118 = v235;
LABEL_176:
                v269 = (__int64)v81;
                v270 = (__m128i **)v80;
                v271 = (__int64)v83;
                v272 = v48;
                v273 = v61;
                v235 = v118;
                v274.m128i_i64[0] = v118;
                v292 = v117;
                v274.m128i_i16[4] = v117;
                *(__int32 *)((char *)&v274.m128i_i32[2] + 2) = v279;
                v268 = v82;
                enum2__otls::gsub_gpos_shared::context::ContextLookup_::get_coverage_table(&v299, &v268);
                v236 = (unsigned __int64)v61;
                goto LABEL_196;
              }
            }
            break;
          case 6:
LABEL_102:
            if ( v50 < 4 )
              break;
            v75 = __ROL2__(*v61, 8);
            if ( v75 == 3 )
            {
              otls::gsub_gpos_shared::chaining::ChainCoverageSubTable::parse(&v239, v61, v50);
              v77 = (__m128i *)v239;
              if ( !v239 )
                break;
              v76 = (unsigned __int64)v240;
              v61 = v241;
              v50 = (unsigned __int64)v242;
              v78 = v243;
              LOWORD(v58) = v244;
              LOWORD(v48) = v245;
              LOWORD(v51) = v246;
              v252 = v247;
              v253 = v248;
              v254 = v249;
              v79 = 2;
              goto LABEL_186;
            }
            if ( v75 == 2 )
            {
              if ( v50 >= 0xC )
              {
                v76 = (unsigned __int16)__ROL2__(v61[5], 8);
                if ( 2 * (unsigned int)(unsigned __int16)v76 <= v50 - 12 )
                {
                  v77 = (__m128i *)(v61 + 6);
                  LOWORD(v51) = __ROL2__(v61[4], 8);
                  LOWORD(v48) = __ROL2__(v61[3], 8);
                  LOWORD(v58) = __ROL2__(v61[2], 8);
                  v78 = __ROL2__(v61[1], 8);
                  v79 = 1;
                  goto LABEL_186;
                }
              }
            }
            else if ( v75 == 1 && v50 >= 6 )
            {
              v76 = (unsigned __int16)__ROL2__(v61[2], 8);
              if ( 2 * (unsigned int)(unsigned __int16)v76 <= v50 - 6 )
              {
                v77 = (__m128i *)(v61 + 3);
                v78 = __ROL2__(v61[1], 8);
                v79 = 0;
LABEL_186:
                v268 = v79;
                v269 = (__int64)v77;
                v270 = (__m128i **)v76;
                v271 = (__int64)v61;
                v272 = v50;
                LOWORD(v273) = v78;
                WORD1(v273) = (_WORD)v58;
                WORD2(v273) = v48;
                HIWORD(v273) = v51;
                v276 = v254;
                v123 = _mm_load_si128(&v252);
                v275 = _mm_load_si128(&v253);
                v274 = v123;
                enum2__otls::gsub_gpos_shared::chaining::ChainingLookup_::get_coverage_table(&v299, &v268);
                goto LABEL_196;
              }
            }
            break;
          case 8:
            if ( v50 < 6 )
              break;
            if ( *v61 != 256 )
              break;
            v84 = 2 * (unsigned int)(unsigned __int16)__ROL2__(v61[2], 8);
            v85 = v50 - 6 - v84;
            if ( v50 - 6 < v84 )
              break;
            if ( v85 < 2 )
              break;
            v86 = v85 - 2;
            v48 = 2 * (unsigned int)(unsigned __int16)__ROL2__(v61[v84 / 2 + 3], 8);
            v29 = v86 < v48;
            v87 = v86 - v48;
            if ( v29
              || v87 < 2
              || 2 * (unsigned int)(unsigned __int16)__ROL2__(*(_WORD *)((char *)&v61[v84 / 2 + 4] + v48), 8) > v87 - 2 )
            {
              break;
            }
            v88 = (unsigned __int16)__ROL2__(v61[1], 8);
            v89 = 1;
            v29 = v50 < v88;
            v50 -= v88;
            if ( v29 || v50 < 4 )
              goto LABEL_242;
            v48 = (unsigned __int64)v61 + v88;
            v90 = __ROL2__(*(_WORD *)((char *)v61 + v88), 8);
            if ( v90 == 2 )
            {
              v50 -= 4LL;
              v149 = (unsigned __int16)__ROL2__(*(_WORD *)(v48 + 2), 8);
              if ( 3 * (unsigned __int64)(2 * (unsigned int)(unsigned __int16)v149) <= v50 )
              {
                v48 += 4LL;
                v300 = (unsigned __int16 *)v48;
LABEL_240:
                v301 = v149;
                LOWORD(v302) = 2;
                WORD1(v302) = v149;
                goto LABEL_241;
              }
            }
            else if ( v90 == 1 )
            {
              v50 -= 4LL;
              v91 = (unsigned __int16)__ROL2__(*(_WORD *)(v48 + 2), 8);
              if ( 2 * (unsigned int)(unsigned __int16)v91 <= v50 )
              {
                v48 += 4LL;
                v300 = 0;
                v301 = v48;
LABEL_146:
                v302 = v91;
LABEL_241:
                v89 = 0;
              }
            }
LABEL_242:
            v299 = v89;
            goto LABEL_196;
          default:
            break;
        }
      }
LABEL_195:
      v299 = 1;
LABEL_196:
      if ( (_DWORD)v299 == 1 )
      {
        *v266 = 0x30200000001LL;
        goto LABEL_373;
      }
      ++v258;
      v131 = v300;
      v132 = (unsigned __int16 *)v301;
      if ( v300 )
      {
        v228 = &v300[3 * v301];
LABEL_200:
        while ( 1 )
        {
          v133 = v131 + 3;
          if ( v131 == v228 )
            break;
          v134 = *v131;
          LOWORD(v134) = __ROL2__(v134, 8);
          v135 = __ROL2__(v131[1], 8);
          v136 = 0;
          while ( 1 )
          {
            v138 = v286;
LABEL_204:
            v139 = v134;
            if ( v136 )
            {
              v131 = v133;
              goto LABEL_200;
            }
            if ( (unsigned __int16)v134 > v135 )
              break;
            v136 = (unsigned __int16)v134 >= v135;
            LOWORD(v134) = ((unsigned __int16)v134 < v135) + (_WORD)v134;
            if ( v303 > v286 )
              core::slice::index::slice_start_index_len_fail(v303, v286, &off_18033A2F8);
            if ( (unsigned __int16)v139 > (unsigned __int16)v298 )
            {
              LODWORD(v298) = v139;
            }
            else
            {
              v140 = v289;
              while ( 4 * v286 != v140 )
              {
                v50 = v140 + 4;
                v141 = *(_WORD *)((char *)lpMem + v140) == (unsigned __int16)v139;
                v140 += 4;
                if ( v141 )
                  goto LABEL_204;
              }
            }
            v142 = otls::cache::builder::check_lookup_flags(v139, v265, v282, v288, v233, (__int64)v256, (__int64)v257);
            if ( (_BYTE)v142 )
            {
              if ( v138 == v234 )
                goto LABEL_233;
              if ( v138 == v284 )
                alloc::raw_vec::RawVec_otls::cache::builder::CacheEntry_alloc::alloc::Global_::grow_one_otls::cache::builder::CacheEntry_alloc::alloc::Global_(&v284);
              v137 = lpMem;
              *((_WORD *)lpMem + 2 * v138) = v139;
              v137[2 * v138 + 1] = v250;
              v286 = v138 + 1;
            }
          }
          v131 = v133;
        }
LABEL_234:
        v18 = v296;
        v17 = (unsigned __int64)v295;
      }
      else
      {
        v143 = (unsigned __int16 *)(v301 + 2 * v302);
        while ( 1 )
        {
          v145 = v286;
LABEL_221:
          v146 = v132;
          v50 = 0;
          v141 = v132 == v143;
          LOBYTE(v48) = v132 != v143;
          v18 = v296;
          v17 = (unsigned __int64)v295;
          if ( v141 )
            break;
          if ( v303 > v286 )
            core::slice::index::slice_start_index_len_fail(v303, v286, &off_18033A2E0);
          LOBYTE(v50) = v48;
          v132 = &v146[v50];
          v147 = *v146;
          LOWORD(v147) = __ROL2__(v147, 8);
          if ( (unsigned __int16)v147 > (unsigned __int16)v298 )
          {
            LODWORD(v298) = v147;
          }
          else
          {
            v148 = v289;
            while ( 4 * v286 != v148 )
            {
              v141 = *(_WORD *)((char *)lpMem + v148) == (unsigned __int16)v147;
              v148 += 4;
              if ( v141 )
                goto LABEL_221;
            }
          }
          v142 = otls::cache::builder::check_lookup_flags(v147, v265, v282, v288, v233, (__int64)v256, (__int64)v257);
          if ( (_BYTE)v142 )
          {
            if ( v145 == v234 )
            {
LABEL_233:
              LOBYTE(v142) = 1;
              v267 = v142;
              goto LABEL_234;
            }
            if ( v145 == v284 )
              alloc::raw_vec::RawVec_otls::cache::builder::CacheEntry_alloc::alloc::Global_::grow_one_otls::cache::builder::CacheEntry_alloc::alloc::Global_(&v284);
            v144 = lpMem;
            *((_WORD *)lpMem + 2 * v145) = v147;
            v144[2 * v145 + 1] = v250;
            v286 = v145 + 1;
          }
        }
      }
      v44 = v260;
      v45 = v261;
      v46 = v262;
      v58 = v263;
      v55 = v264;
    }
    v151 = v286;
    if ( (v267 & 1) == 0 )
    {
      v49 = v250 + 1;
      v48 = v232;
      v303 = v286;
      v47 = v231;
      continue;
    }
    break;
  }
  v152 = v303;
LABEL_377:
  if ( (v267 & 1) == 0 )
    v49 = v17;
LABEL_249:
  if ( v152 < v151 )
    v151 = v152;
  if ( !v151 )
  {
    v224 = v266;
    v266[1] = 0;
    *v224 = 0;
    if ( v284 )
      goto LABEL_374;
    goto LABEL_375;
  }
  v153 = lpMem;
  if ( v151 != 1 )
  {
    if ( v151 >= 0x15 )
      core::slice::sort::stable::driftsort_main_otls::cache::builder::CacheEntry_bool_____ref__otls::cache::builder::CacheEntry__ref__otls::cache::builder::CacheEntry___alloc::vec::Vec_otls::cache::builder::CacheEntry_alloc::alloc::Global___(
        lpMem,
        v151,
        v50);
    else
      core::slice::sort::shared::smallsort::insertion_sort_shift_left_otls::cache::builder::CacheEntry_bool_____ref__otls::cache::builder::CacheEntry__ref__otls::cache::builder::CacheEntry___(
        lpMem,
        v151,
        v50);
  }
  v289 = v287 + 16;
  v295 = (char *)(v153 + 4);
LABEL_255:
  while ( !v151 )
  {
    v151 = 0;
    v49 = 0;
    if ( v251 >= 8 )
    {
      v223 = v266;
      v266[1] = 0;
      goto LABEL_372;
    }
  }
  v154 = v151 - 1;
  v155 = 0xFFFF;
  v156 = v289;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  v160 = 0;
  do
  {
    v303 = v156;
    v298 = v158;
    v161 = v160;
    ++v157;
    v162 = v153[2 * v160];
    v163 = v160;
    while ( v154 != v163 )
    {
      v160 = v163 + 1;
      v141 = v153[2 * v163++ + 2] == v162;
      if ( !v141 )
        goto LABEL_264;
    }
    v160 = v151;
LABEL_264:
    v164 = v49;
    if ( v155 == 0xFFFF )
    {
LABEL_257:
      v158 = v298 + 1;
      v159 = v160 + v159 - v161;
    }
    else
    {
      if ( v155 >= v151 )
        core::panicking::panic_bounds_check(v155, v151, &off_18033A250);
      v165 = v153[2 * v155];
      v166 = v161 + 1;
      do
      {
        v167 = v166;
        v168 = v153[2 * v166 - 2];
        if ( v168 != v162 )
        {
          v169 = 1;
          goto LABEL_276;
        }
        if ( v153[2 * v155] != v165 || v153[2 * v167 - 1] != v153[2 * v155 + 1] )
          goto LABEL_257;
        v169 = ++v155 < v151;
        v166 = v167 + 1;
      }
      while ( v167 < v151 && v155 < v151 );
      if ( v167 >= v151 )
      {
        if ( v155 >= v151 )
          goto LABEL_281;
        goto LABEL_280;
      }
      v168 = v153[2 * v166 - 2];
      if ( v168 == v162 )
      {
LABEL_277:
        if ( v168 == v162 )
          goto LABEL_257;
        goto LABEL_281;
      }
LABEL_276:
      if ( !v169 )
        goto LABEL_277;
LABEL_280:
      if ( v153[2 * v155] == v165 )
        goto LABEL_257;
LABEL_281:
      v158 = v298;
    }
    v156 = v303 + 4;
    v155 = v161;
    v49 = v164;
  }
  while ( v160 < v151 );
  v170 = v159 + v158;
  v171 = 2 * v170 + 4 * v157 + 8;
  if ( v171 > v251
    || (v287 & 3) != 0
    || v171 < 8
    || (v173 = v287, *(_WORD *)v287 = v294, *(_WORD *)(v173 + 2) = v49, *(_DWORD *)(v173 + 4) = v157, v157 >> 62)
    || __CFADD__(4 * v157, 2 * v170) )
  {
    if ( v151 >= 9 )
    {
      v174 = v151 & 7;
      if ( (v151 & 7) == 0 )
        v174 = 8;
      v172 = v151 - v174;
      v175 = 0;
      v176 = 0;
      v177 = 0;
      do
      {
        v178 = _mm_shuffle_epi32(
                 _mm_shufflehi_epi16(
                   _mm_shufflelo_epi16(_mm_loadu_si128((const __m128i *)&v153[2 * v176 + 1]), 232),
                   232),
                 232);
        v179 = _mm_shuffle_epi32(
                 _mm_shufflehi_epi16(
                   _mm_shufflelo_epi16(_mm_loadu_si128((const __m128i *)&v153[2 * v176 + 9]), 232),
                   232),
                 232);
        v175 = _mm_add_epi16(_mm_subs_epu16(v175, v178), v178);
        v177 = _mm_add_epi16(_mm_subs_epu16(v177, v179), v179);
        v176 += 8;
      }
      while ( v172 != v176 );
      v180 = _mm_add_epi16(_mm_subs_epu16(v177, v175), v175);
      v181 = _mm_add_epi16(_mm_subs_epu16(_mm_shuffle_epi32(v180, 85), v180), v180);
      LODWORD(v49) = _mm_cvtsi128_si32(_mm_add_epi16(_mm_subs_epu16(_mm_srli_epi32(v181, 0x10u), v181), v181));
    }
    else
    {
      v172 = 0;
      LODWORD(v49) = 0;
    }
    do
    {
      v182 = (unsigned __int16)v153[2 * v172++ + 1];
      if ( (unsigned __int16)v182 <= (unsigned __int16)v49 )
        v182 = v49;
      v49 = v182;
    }
    while ( v151 != v172 );
    v183 = v295;
    v184 = 0;
    while ( v153[2 * v184 + 1] != (_WORD)v182 )
    {
      ++v184;
      v183 += 4;
      --v154;
      if ( v151 == v184 )
        goto LABEL_255;
    }
    v185 = 1;
    if ( v151 - 1 == v184 )
      goto LABEL_317;
    if ( v151 - 2 == v184 )
    {
      v186 = v184 + 1;
      v185 = 1;
      goto LABEL_314;
    }
    v187 = v154 & 0xFFFFFFFFFFFFFFFEuLL;
    v185 = 1;
    v188 = -1;
    while ( 1 )
    {
      if ( *((_WORD *)v183 - 1) == (_WORD)v49 )
      {
        ++v185;
        if ( *((_WORD *)v183 + 1) != (_WORD)v49 )
          goto LABEL_312;
      }
      else
      {
        *(_DWORD *)&v183[-4 * v185 - 4] = *((_DWORD *)v183 - 1);
        if ( *((_WORD *)v183 + 1) != (_WORD)v49 )
        {
LABEL_312:
          *(_DWORD *)&v183[-4 * v185] = *(_DWORD *)v183;
          goto LABEL_307;
        }
      }
      ++v185;
LABEL_307:
      v183 += 8;
      v189 = v187 + v188 - 2;
      v188 -= 2;
      if ( v189 == -1 )
      {
        v186 = v184 - v188;
LABEL_314:
        if ( (((_BYTE)v151 + ~(_BYTE)v184) & 1) != 0 )
        {
          if ( v153[2 * v186 + 1] == (_WORD)v49 )
          {
            ++v185;
            goto LABEL_317;
          }
          *(_DWORD *)&v153[2 * (v186 - v185)] = *(_DWORD *)&v153[2 * v186];
          v151 -= v185;
        }
        else
        {
LABEL_317:
          v151 -= v185;
        }
        goto LABEL_255;
      }
    }
  }
  v257 = (__int64 *)(2 * v170 + 4 * v157 + 8);
  v303 = v156;
  v289 = 4 * v157 + 8;
  v190 = v287 + 4 * v157 + 8;
  v287 += 8;
  v191 = v170 & 0x7FFFFFFFFFFFFFFFLL;
  v256 = (__int64 *)(v153 + 9);
  v192 = 0xFFFF;
  v193 = 0;
  v194 = 0;
  v195 = 0;
  v295 = (char *)v190;
  while ( 2 )
  {
    v294 = v193;
    v197 = v153[2 * v195];
    v198 = v195;
    do
    {
      if ( v154 == v198 )
      {
        v199 = v151;
        if ( v192 != 0xFFFF )
          goto LABEL_349;
LABEL_327:
        v298 = v199 - v195;
        if ( v199 != v195 )
        {
          v200 = v191 - v194;
          if ( v191 < v194 )
            v200 = 0;
          if ( v199 + ~v195 < v200 )
            v200 = v199 + ~v195;
          v201 = v151 - v195;
          if ( v151 < v195 )
            v201 = 0;
          if ( v200 < v201 )
            v201 = v200;
          v202 = 1;
          v203 = 0;
          if ( v201 > 7 )
          {
            v204 = v191;
            v205 = v201 + 1;
            v206 = v205 & 7;
            if ( (v205 & 7) == 0 )
              v206 = 8;
            v203 = v205 - v206;
            v202 = v205 - v206 + 1;
            v207 = v303 + 2 * v194;
            v208 = (char *)v256 + 4 * v195;
            v209 = 0;
            do
            {
              *(__m128i *)(v207 + 2 * v209 - 8) = _mm_unpacklo_epi64(
                                                    _mm_shuffle_epi32(
                                                      _mm_shufflehi_epi16(
                                                        _mm_shufflelo_epi16(
                                                          _mm_loadu_si128((const __m128i *)&v208[4 * v209 - 16]),
                                                          232),
                                                        232),
                                                      232),
                                                    _mm_shuffle_epi32(
                                                      _mm_shufflehi_epi16(
                                                        _mm_shufflelo_epi16(
                                                          _mm_loadu_si128((const __m128i *)&v208[4 * v209]),
                                                          232),
                                                        232),
                                                      232));
              v209 += 8;
            }
            while ( v203 != v209 );
            v191 = v204;
            v190 = (__int64)v295;
          }
          v210 = v298 + 1;
          do
          {
            v211 = v202;
            v212 = v203 + v195;
            if ( v203 + v195 >= v151 )
              core::panicking::panic_bounds_check(v203 + v195, v151, &off_18033A280);
            v213 = v194 + v203;
            if ( v213 >= v191 )
              core::panicking::panic_bounds_check(v213, v191, &off_18033A298);
            *(_WORD *)(v190 + 2 * v213) = v153[2 * v212 + 1];
            v202 = v211 + 1;
            v203 = v211;
          }
          while ( v210 != v211 + 1 );
        }
        v214 = v298;
        v215 = v298 + v194;
        if ( v298 + v194 >= v191 )
          core::panicking::panic_bounds_check(v215, v191, &off_18033A268);
        *(_WORD *)(v190 + 2 * v215) = -1;
        v194 += v214 + 1;
        v216 = v289;
        v289 += 2 * v214 + 2;
        v217 = v294;
        if ( v294 == v157 )
LABEL_367:
          core::panicking::panic_bounds_check(v157, v157, &off_18033A2C8);
        goto LABEL_320;
      }
      v199 = v198 + 1;
      v141 = v153[2 * v198++ + 2] == v197;
    }
    while ( v141 );
    if ( v192 == 0xFFFF )
      goto LABEL_327;
LABEL_349:
    if ( v192 >= v151 )
      core::panicking::panic_bounds_check(v192, v151, &off_18033A250);
    LOWORD(v298) = v153[2 * v192];
    v218 = v195 + 1;
    while ( 2 )
    {
      v219 = v218;
      v220 = v153[2 * v218 - 2];
      if ( v220 != v197 )
      {
        v221 = 1;
        goto LABEL_360;
      }
      if ( v153[2 * v192] != (_WORD)v298 || v153[2 * v219 - 1] != v153[2 * v192 + 1] )
        goto LABEL_327;
      v221 = ++v192 < v151;
      v218 = v219 + 1;
      if ( v219 < v151 && v192 < v151 )
        continue;
      break;
    }
    if ( v219 >= v151 )
    {
      if ( v192 >= v151 )
        goto LABEL_365;
LABEL_364:
      if ( v153[2 * v192] != (_WORD)v298 )
        goto LABEL_365;
      goto LABEL_327;
    }
    v220 = v153[2 * v218 - 2];
    if ( v220 != v197 )
    {
LABEL_360:
      if ( !v221 )
        goto LABEL_361;
      goto LABEL_364;
    }
LABEL_361:
    if ( v220 == v197 )
      goto LABEL_327;
LABEL_365:
    v217 = v294;
    v222 = v294 - 1;
    if ( v294 - 1 >= v157 )
      core::panicking::panic_bounds_check(v222, v157, &off_18033A2B0);
    v216 = *(_WORD *)(v287 + 4 * v222 + 2);
    if ( v294 == v157 )
      goto LABEL_367;
LABEL_320:
    v196 = v287;
    *(_WORD *)(v287 + 4 * v217) = v197;
    *(_WORD *)(v196 + 4 * v217 + 2) = v216;
    v193 = v217 + 1;
    v192 = v195;
    v195 = v199;
    if ( v199 < v151 )
      continue;
    break;
  }
  v223 = v266;
  v266[1] = v257;
LABEL_372:
  *v223 = 0;
LABEL_373:
  v18 = v296;
  if ( v284 )
  {
LABEL_374:
    v225 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v225);
  }
LABEL_375:
  v227 = GetProcessHeap();
  HeapFree(v227, 0, v18);
}

```

## disassembly

```asm
0x180067e80  push    rbp
0x180067e81  push    r15
0x180067e83  push    r14
0x180067e85  push    r13
0x180067e87  push    r12
0x180067e89  push    rsi
0x180067e8a  push    rdi
0x180067e8b  push    rbx
0x180067e8c  sub     rsp, 288h
0x180067e93  lea     rbp, [rsp+80h]
0x180067e9b  mov     [rbp+240h+var_40], 0FFFFFFFFFFFFFFFEh
0x180067ea6  mov     r15, r8
0x180067ea9  mov     r8, [r9+80h]
0x180067eb0  test    r8, r8
0x180067eb3  jz      loc_180067F6C
0x180067eb9  mov     rbx, r9
0x180067ebc  mov     rax, [rbp+240h+arg_28]
0x180067ec3  mov     [rbp+240h+var_1D8], rax
0x180067ec7  cmp     dword ptr [r15], 3
0x180067ecb  lea     rax, qword_1803B42E0
0x180067ed2  cmovnz  rax, r15
0x180067ed6  mov     [rbp+240h+var_1A0], rax
0x180067edd  cmp     dword ptr [r15+20h], 3
0x180067ee2  lea     rax, [r15+20h]
0x180067ee6  lea     r9, qword_1803B4300
0x180067eed  cmovnz  r9, rax
0x180067ef1  mov     [rbp+240h+var_198], r9
0x180067ef8  mov     rax, [rbp+240h+arg_20]
0x180067eff  mov     [rbp+240h+var_B0], rax
0x180067f06  mov     qword ptr [rbp+240h+var_1D0], r8
0x180067f0a  mov     rax, r8
0x180067f0d  shr     rax, 3Dh
0x180067f11  jnz     loc_180069D1D
0x180067f17  mov     [rbp+240h+var_71], dl
0x180067f1d  mov     [rbp+240h+var_150], rcx
0x180067f24  mov     rdi, r8
0x180067f27  shr     rdi, 6
0x180067f2b  mov     [rbp+240h+var_88], r8
0x180067f32  mov     eax, r8d
0x180067f35  and     eax, 3Fh
0x180067f38  cmp     rax, 1
0x180067f3c  sbb     rdi, 0FFFFFFFFFFFFFFFFh
0x180067f40  lea     rsi, ds:0[rdi*8]
0x180067f48  test    rdi, rdi
0x180067f4b  jz      short loc_180067F8E
0x180067f4d  xor     ecx, ecx
0x180067f4f  mov     rdx, rsi
0x180067f52  call    std__sys__alloc__windows__process_heap_alloc
0x180067f57  mov     r14, rax
0x180067f5a  test    rax, rax
0x180067f5d  jnz     short loc_180067F94
0x180067f5f  mov     ecx, 8
0x180067f64  mov     rdx, rsi
0x180067f67  call    alloc__alloc__handle_alloc_error
0x180067f6c  mov     qword ptr [rcx+8], 0
0x180067f74  mov     dword ptr [rcx], 0
0x180067f7a  add     rsp, 288h
0x180067f81  pop     rbx
0x180067f82  pop     rdi
0x180067f83  pop     rsi
0x180067f84  pop     r12
0x180067f86  pop     r13
0x180067f88  pop     r14
0x180067f8a  pop     r15
0x180067f8c  pop     rbp
0x180067f8d  retn
0x180067f8e  mov     r14d, 8
0x180067f94  mov     qword ptr [rbp+240h+var_1D0], r14
0x180067f98  mov     qword ptr [rbp+240h+var_1D0+8], 0
0x180067fa0  mov     qword ptr [rbp+240h+var_1C0], rdi
0x180067fa7  mov     rax, [rbp+240h+var_88]
0x180067fae  mov     [rbp+240h+var_C8], rax
0x180067fb5  shl     rdi, 6
0x180067fb9  mov     [rbp+240h+var_68], rdi
0x180067fc0  cmp     rax, rdi
0x180067fc3  ja      loc_180069D8C
0x180067fc9  mov     [rbp+240h+var_260], r15
0x180067fcd  mov     rcx, r14; void *
0x180067fd0  xor     edx, edx; Val
0x180067fd2  mov     r8, rsi; Size
0x180067fd5  call    memset_0
0x180067fda  mov     r13, [rbx+30h]
0x180067fde  mov     r12, [rbx+0A8h]
0x180067fe5  test    r13, r13
0x180067fe8  mov     [rbp+240h+var_80], r14
0x180067fef  jz      loc_1800680C9
0x180067ff5  mov     [rbp+240h+var_90], 0
0x180068000  lea     r14, [rbp+240h+var_140]
0x180068007  xor     r15d, r15d
0x18006800a  mov     rsi, [rbp+240h+var_88]
0x180068011  jmp     short loc_180068033
0x180068020  mov     rdi, [rbp+240h+var_80]
0x180068027  inc     r15
0x18006802a  cmp     r15, r13
0x18006802d  jz      loc_1800680DE
0x180068033  mov     rcx, r14
0x180068036  mov     rdx, rbx
0x180068039  mov     r8, r15
0x18006803c  call    otls__features__FeatureListTable__feature_table
0x180068041  cmp     [rbp+240h+var_140], 0
0x180068049  jz      loc_180069879
0x18006804f  mov     rax, [rbp+240h+var_128]
0x180068056  test    rax, rax
0x180068059  jz      short loc_180068020
0x18006805b  mov     rdx, [rbp+240h+var_130]
0x180068062  add     rax, rax
0x180068065  xor     r8d, r8d
0x180068068  mov     r9, [rbp+240h+var_90]
0x18006806f  mov     rdi, [rbp+240h+var_80]
0x180068076  jmp     short loc_180068089
0x180068080  add     r8, 2
0x180068084  cmp     rax, r8
0x180068087  jz      short loc_180068027
0x180068089  movzx   ecx, word ptr [rdx+r8]
0x18006808e  rol     cx, 8
0x180068092  movzx   ecx, cx
0x180068095  cmp     rsi, rcx
0x180068098  jbe     short loc_180068080
0x18006809a  mov     r10d, ecx
0x18006809d  mov     r11d, 1
0x1800680a3  shl     r11, cl
0x1800680a6  shr     r10d, 6
0x1800680aa  or      [rdi+r10*8], r11
0x1800680ae  cmp     r9, rcx
0x1800680b1  mov     r10, [rbp+240h+var_90]
0x1800680b8  cmovb   r10, rcx
0x1800680bc  mov     [rbp+240h+var_90], r10
0x1800680c3  cmovbe  r9, rcx
0x1800680c7  jmp     short loc_180068080
0x1800680c9  mov     rdi, r14
0x1800680cc  mov     [rbp+240h+var_90], 0
0x1800680d7  mov     rsi, [rbp+240h+var_88]
0x1800680de  test    r12, r12
0x1800680e1  jz      loc_180068275
0x1800680e7  mov     r11, [rbx+0B0h]
0x1800680ee  cmp     r11, 3
0x1800680f2  jbe     loc_180069ED9
0x1800680f8  cmp     word ptr [r12], 100h
0x1800680ff  jnz     loc_180068275
0x180068105  mov     rax, [rbx+0C0h]
0x18006810c  mov     [rbp+240h+var_70], rax
0x180068113  test    rax, rax
0x180068116  jz      loc_180068275
0x18006811c  mov     [rbp+240h+var_48], r12
0x180068123  mov     rax, [rbx+0B8h]
0x18006812a  xor     r9d, r9d
0x18006812d  mov     [rbp+240h+var_A0], r11
0x180068134  mov     [rbp+240h+var_158], rax
0x18006813b  jmp     short loc_180068162
0x18006813d  inc     r9
0x180068140  cmp     r9, [rbp+240h+var_70]
0x180068147  mov     rdi, [rbp+240h+var_80]
0x18006814e  mov     r11, [rbp+240h+var_A0]
0x180068155  mov     rax, [rbp+240h+var_158]
0x18006815c  jz      loc_180068275
0x180068162  mov     r10d, [rax+r9*8+4]
0x180068167  bswap   r10d
0x18006816a  sub     r11, r10
0x18006816d  jb      loc_180069879
0x180068173  cmp     r11, 6
0x180068177  jb      loc_180069879
0x18006817d  add     r10, [rbp+240h+var_48]
0x180068184  movzx   ecx, word ptr [r10+4]
0x180068189  rol     cx, 8
0x18006818d  movzx   r14d, cx
0x180068191  lea     rcx, [r11-6]
0x180068195  lea     r8d, [r14+r14]
0x180068199  lea     r8, [r8+r8*2]
0x18006819d  cmp     r8, rcx
0x1800681a0  ja      loc_180069879
0x1800681a6  test    r14, r14
0x1800681a9  jz      short loc_18006813D
0x1800681ab  movzx   ecx, word ptr [r10]
0x1800681af  cmp     ecx, 100h
0x1800681b5  jnz     short loc_18006813D
0x1800681b7  xor     r15d, r15d
0x1800681ba  jmp     short loc_1800681CC
0x1800681c0  inc     r15
0x1800681c3  cmp     r15, r14
0x1800681c6  jz      loc_18006813D
0x1800681cc  lea     rcx, [r15+r15*2]
0x1800681d0  mov     edi, [r10+rcx*2+8]
0x1800681d5  bswap   edi
0x1800681d7  mov     rcx, r11
0x1800681da  sub     rcx, rdi
0x1800681dd  jb      loc_180069879
0x1800681e3  cmp     rcx, 4
0x1800681e7  jb      loc_180069879
0x1800681ed  add     rdi, r10
0x1800681f0  movzx   r8d, word ptr [rdi+2]
0x1800681f5  rol     r8w, 8
0x1800681fa  movzx   r8d, r8w
0x1800681fe  add     rcx, 0FFFFFFFFFFFFFFFCh
0x180068202  lea     r12d, [r8+r8]
0x180068206  cmp     r12, rcx
0x180068209  ja      loc_180069879
0x18006820f  test    r8, r8
0x180068212  jz      short loc_1800681C0
0x180068214  xor     r13d, r13d
0x180068217  mov     r8, [rbp+240h+var_90]
0x18006821e  jmp     short loc_180068229
0x180068220  add     r13, 2
0x180068224  cmp     r12, r13
0x180068227  jz      short loc_1800681C0
0x180068229  movzx   ecx, word ptr [rdi+r13+4]
0x18006822f  rol     cx, 8
0x180068233  movzx   ecx, cx
0x180068236  cmp     rsi, rcx
0x180068239  jbe     short loc_180068220
0x18006823b  mov     edx, ecx
0x18006823d  mov     eax, 1
0x180068242  shl     rax, cl
0x180068245  shr     edx, 6
0x180068248  mov     rsi, [rbp+240h+var_80]
0x18006824f  or      [rsi+rdx*8], rax
0x180068253  mov     rsi, [rbp+240h+var_88]
0x18006825a  cmp     r8, rcx
0x18006825d  mov     rax, [rbp+240h+var_90]
0x180068264  cmovb   rax, rcx
0x180068268  mov     [rbp+240h+var_90], rax
0x18006826f  cmovbe  r8, rcx
0x180068273  jmp     short loc_180068220
0x180068275  mov     edx, 1000h
0x18006827a  xor     ecx, ecx
0x18006827c  call    std__sys__alloc__windows__process_heap_alloc
0x180068281  test    rax, rax
0x180068284  jz      loc_180069EC8
0x18006828a  mov     rcx, [rbp+240h+var_1D8]
0x18006828e  shr     rcx, 2
0x180068292  mov     [rbp+240h+var_258], rcx
0x180068296  lea     rcx, ds:0[rsi*8]
0x18006829e  mov     [rbp+240h+var_280], rcx
0x1800682a2  mov     [rbp+240h+var_C8], 400h
0x1800682ad  mov     [rbp+240h+lpMem], rax
0x1800682b4  mov     [rbp+240h+var_B8], 0
0x1800682bf  mov     r15, [rbx+78h]
0x1800682c3  mov     r12, [rbx+88h]
0x1800682ca  mov     r13, [rbx+90h]
0x1800682d1  xor     ecx, ecx
0x1800682d3  xor     r9d, r9d
0x1800682d6  mov     [rbp+240h+var_48], 0
0x1800682e1  mov     [rbp+240h+var_148], 0
0x1800682ec  xor     r14d, r14d
0x1800682ef  test    cl, 1
0x1800682f2  mov     r8, [rbp+240h+var_90]
0x1800682f9  jnz     loc_180069C95
0x1800682ff  cmp     r9, r8
0x180068302  ja      loc_180069C95
0x180068308  test    byte ptr [rbp+240h+var_148], 1
0x18006830f  jnz     loc_180069C95
0x180068315  mov     r10, r9
0x180068318  nop     dword ptr [rax+rax+00000000h]
0x180068320  cmp     r9, r8
0x180068323  adc     r10, 0
0x180068327  mov     [rbp+240h+var_140], r9
0x18006832e  cmp     r9, rsi
0x180068331  jnb     loc_180069E83
0x180068337  mov     rax, r9
0x18006833a  shr     rax, 6
0x18006833e  mov     rax, [rdi+rax*8]
0x180068342  bt      rax, r9
0x180068346  jnb     short loc_180068380
0x180068348  movzx   eax, word ptr [r15+r9*2]
0x18006834d  rol     ax, 8
0x180068351  movzx   r11d, ax
0x180068355  mov     rbx, r13
0x180068358  sub     rbx, r11
0x18006835b  jb      short loc_180068380
0x18006835d  cmp     rbx, 6
0x180068361  jb      short loc_180068380
0x180068363  movzx   eax, word ptr [r12+r11+4]
0x180068369  rol     ax, 8
0x18006836d  lea     rdx, [rbx-6]
0x180068371  movzx   eax, ax
0x180068374  lea     ecx, [rax+rax]
0x180068377  sub     rdx, rcx
0x18006837a  jnb     short loc_180068396
0x18006837c  nop     dword ptr [rax+00h]
0x180068380  cmp     r9, r8
0x180068383  jnb     loc_18006946B
0x180068389  mov     r9, r10
0x18006838c  cmp     r10, r8
0x18006838f  jbe     short loc_180068320
0x180068391  jmp     loc_18006946B
0x180068396  add     r11, r12
0x180068399  cmp     r9, r8
0x18006839c  setnb   r8b
0x1800683a0  mov     [rbp+240h+var_270], r8
0x1800683a4  lea     r8, [r11+6]
0x1800683a8  mov     [rbp+240h+var_190], r8
0x1800683af  movzx   r8d, word ptr [r11+2]
0x1800683b4  rol     r8w, 8
0x1800683b9  mov     dword ptr [rbp+240h+var_158], r8d
0x1800683c0  test    r8b, 10h
0x1800683c4  jnz     short loc_1800683D2
0x1800683c6  mov     [rbp+240h+var_D4], 0
0x1800683d0  jmp     short loc_1800683FF
0x1800683d2  mov     r8w, 1
0x1800683d7  mov     [rbp+240h+var_D4], r8d
0x1800683de  cmp     rdx, 2
  ... truncated ...
```
