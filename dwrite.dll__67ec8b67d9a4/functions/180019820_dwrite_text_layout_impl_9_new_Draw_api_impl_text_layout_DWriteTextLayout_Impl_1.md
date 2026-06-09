# dwrite::text_layout::impl$9::new::Draw_api_impl::text_layout::DWriteTextLayout_Impl__1_

- ea: `0x180019820`
- end: `0x18001b85a`
- name: `dwrite::text_layout::impl$9::new::Draw_api_impl::text_layout::DWriteTextLayout_Impl__1_`
- size: `8250`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180019820`
- `0x180022de0`
- `0x180027140`
- `0x180041d00`
- `0x180045970`
- `0x1800474a0`
- `0x1800486b0`
- `0x180048f40`
- `0x180048fa0`
- `0x180049090`
- `0x180049370`
- `0x180049450`
- `0x180049570`
- `0x180049c20`
- `0x180049e30`
- `0x180049f50`
- `0x18004a320`
- `0x180212ec8`
- `0x180212f4c`
- `0x180316190`
- `0x1803168c1`
- `0x180316a30`
- `0x180316ce0`
- `0x180316d00`
- `0x180316dc0`
- `0x180316ee0`
- `0x18031716c`
- `0x180318870`

## import_xrefs

- `kernel32!HeapFree` at `0x18001b3a1`
- `kernel32!HeapFree` at `0x18001b4cb`
- `kernel32!HeapFree` at `0x18001b3a1`
- `kernel32!HeapFree` at `0x18001b4cb`
- `kernel32!GetProcessHeap` at `0x18001b38f`
- `kernel32!GetProcessHeap` at `0x18001b4bd`
- `kernel32!GetProcessHeap` at `0x18001b38f`
- `kernel32!GetProcessHeap` at `0x18001b4bd`
- `oleaut32!GetErrorInfo` at `0x18001a28b`
- `oleaut32!GetErrorInfo` at `0x18001a7b3`
- `oleaut32!GetErrorInfo` at `0x18001b378`
- `oleaut32!GetErrorInfo` at `0x18001b482`
- `oleaut32!GetErrorInfo` at `0x18001a28b`
- `oleaut32!GetErrorInfo` at `0x18001a7b3`
- `oleaut32!GetErrorInfo` at `0x18001b378`
- `oleaut32!GetErrorInfo` at `0x18001b482`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=2
__int64 __fastcall dwrite::text_layout::impl_9::new::Draw_api_impl::text_layout::DWriteTextLayout_Impl__1_(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        float a4,
        int a5)
{
  __int64 v5; // rsi
  void (__fastcall *v6)(__int64); // rax
  __int64 updated; // rax
  int v8; // edx
  int v9; // ebx
  unsigned __int64 v10; // rsi
  __int64 v11; // r13
  unsigned int v12; // edi
  __int64 v14; // rsi
  __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // r14
  float v19; // xmm10_4
  float v20; // xmm13_4
  unsigned __int64 v21; // r12
  __int64 v22; // r15
  _QWORD *v23; // rax
  int v24; // r8d
  __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  _QWORD *v27; // r9
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __m128i si128; // xmm0
  __int64 v34; // rcx
  __int64 v35; // r8
  unsigned __int64 v36; // rax
  __int32 v37; // ebx
  unsigned __int64 v38; // rdx
  __int64 v39; // rsi
  unsigned __int64 v40; // rdx
  __int64 v41; // r13
  __m128i v42; // xmm0
  __int64 v43; // rcx
  __int64 v44; // rdx
  IErrorInfo *v45; // r12
  __int64 (__fastcall *v46)(__int64, __int64); // rax
  int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // r15
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 (__fastcall *v53)(__int64, __int64); // rax
  __int64 v54; // r12
  __int64 v55; // rbx
  __int64 v56; // rdx
  unsigned __int64 v57; // rbx
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rdi
  unsigned int *v61; // r8
  __int64 v62; // r9
  char v63; // al
  unsigned int *v64; // r9
  __int64 v65; // r14
  __int64 v66; // rsi
  int v67; // edi
  bool v68; // bl
  __int64 v69; // rdx
  unsigned __int64 v70; // rdx
  unsigned __int64 v71; // rax
  __int64 v72; // r8
  unsigned __int64 v73; // r9
  unsigned __int64 v74; // rdi
  unsigned __int64 v75; // rdx
  __int64 v76; // rcx
  bool v77; // zf
  bool v78; // cf
  unsigned __int64 v79; // rax
  unsigned __int64 v80; // r9
  unsigned __int64 v81; // rbx
  unsigned __int64 v82; // r15
  _QWORD *v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rax
  unsigned __int64 v86; // rdi
  unsigned __int64 v87; // rax
  float v88; // xmm7_4
  unsigned __int64 v89; // r14
  __int128 v90; // xmm8
  IErrorInfo *v91; // r8
  __m128 v92; // xmm12
  float v93; // xmm10_4
  __m128 v94; // xmm6
  __int128 v95; // xmm11
  unsigned __int64 v96; // rcx
  unsigned __int64 v97; // rdx
  __int64 v98; // r15
  __int64 v99; // rdi
  __int64 v100; // rsi
  __int64 v101; // rbx
  unsigned __int16 *font_metrics; // r12
  __int64 v103; // r15
  int v104; // r13d
  float v105; // xmm15_4
  int v106; // r9d
  float v107; // xmm14_4
  int v108; // edi
  int v109; // ecx
  int v110; // r8d
  int v111; // edx
  int v112; // esi
  int v113; // r15d
  int v114; // r15d
  __m128 v115; // xmm0
  __m128 v116; // xmm1
  __m128 v117; // xmm0
  __m128 v118; // xmm1
  int v119; // xmm2_4
  float v120; // xmm10_4
  unsigned __int64 v121; // rcx
  unsigned __int64 v122; // rdx
  __int64 v123; // r12
  __int64 v124; // rdi
  __int64 v125; // rbx
  _QWORD *v126; // rax
  __int64 v127; // r12
  __int64 v128; // r13
  __int64 v129; // rdx
  unsigned __int64 v130; // rdx
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rcx
  __int64 v135; // rcx
  float v136; // xmm15_4
  unsigned __int64 v137; // rcx
  unsigned __int64 v138; // rdx
  __int64 v139; // rbx
  __int64 v140; // r15
  __int64 v141; // rdx
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rcx
  unsigned int v145; // ebx
  __int64 v146; // rdx
  int v147; // eax
  HANDLE ProcessHeap; // rax
  __int64 v149; // rcx
  __int64 v150; // rax
  int v151; // edx
  HANDLE v152; // rax
  __int64 v153; // [rsp+48h] [rbp-38h]
  __int64 *v154; // [rsp+50h] [rbp-30h]
  __int64 v155; // [rsp+58h] [rbp-28h]
  __int64 v156; // [rsp+60h] [rbp-20h]
  __int64 v157; // [rsp+68h] [rbp-18h]
  unsigned int *v158; // [rsp+70h] [rbp-10h]
  __int64 v159; // [rsp+88h] [rbp+8h] BYREF
  __int64 v160; // [rsp+90h] [rbp+10h] BYREF
  __int64 v161; // [rsp+98h] [rbp+18h] BYREF
  __int64 v162; // [rsp+A0h] [rbp+20h]
  unsigned int *v163; // [rsp+A8h] [rbp+28h]
  IErrorInfo *pperrinfo[2]; // [rsp+B0h] [rbp+30h] BYREF
  __int128 v165; // [rsp+C0h] [rbp+40h]
  __int128 v166; // [rsp+D0h] [rbp+50h]
  __int128 v167; // [rsp+E0h] [rbp+60h]
  _QWORD v168[5]; // [rsp+F0h] [rbp+70h] BYREF
  __int64 v169; // [rsp+118h] [rbp+98h] BYREF
  __int64 v170; // [rsp+120h] [rbp+A0h]
  __int64 v171; // [rsp+128h] [rbp+A8h]
  __int64 v172; // [rsp+130h] [rbp+B0h]
  __int64 *v173; // [rsp+138h] [rbp+B8h]
  unsigned __int64 v174; // [rsp+140h] [rbp+C0h]
  __int64 v175; // [rsp+148h] [rbp+C8h] BYREF
  float v176; // [rsp+150h] [rbp+D0h]
  int v177; // [rsp+154h] [rbp+D4h]
  __int128 v178; // [rsp+158h] [rbp+D8h] BYREF
  __int64 v179; // [rsp+168h] [rbp+E8h]
  __int64 *v180; // [rsp+170h] [rbp+F0h]
  __int64 v181; // [rsp+178h] [rbp+F8h]
  _QWORD v182[4]; // [rsp+180h] [rbp+100h] BYREF
  int v183; // [rsp+1A4h] [rbp+124h]
  __int64 v184; // [rsp+1A8h] [rbp+128h]
  __m256i v185; // [rsp+1B0h] [rbp+130h] BYREF
  int v186; // [rsp+1D0h] [rbp+150h]
  IErrorInfo *v187; // [rsp+1D8h] [rbp+158h] BYREF
  LPVOID v188; // [rsp+1E0h] [rbp+160h]
  unsigned __int64 v189; // [rsp+1E8h] [rbp+168h]
  IErrorInfo *v190; // [rsp+1F0h] [rbp+170h]
  float v191; // [rsp+1FCh] [rbp+17Ch]
  int v192; // [rsp+200h] [rbp+180h]
  float v193; // [rsp+204h] [rbp+184h]
  __int64 v194; // [rsp+208h] [rbp+188h] BYREF
  unsigned __int64 v195; // [rsp+210h] [rbp+190h]
  __int64 v196; // [rsp+218h] [rbp+198h]
  __int64 v197; // [rsp+220h] [rbp+1A0h]
  LPVOID lpMem; // [rsp+228h] [rbp+1A8h]
  __m256i v199; // [rsp+230h] [rbp+1B0h] BYREF
  _BYTE v200[22]; // [rsp+250h] [rbp+1D0h]
  unsigned __int64 v201; // [rsp+268h] [rbp+1E8h]
  __m256i v202; // [rsp+270h] [rbp+1F0h] BYREF
  _BYTE v203[22]; // [rsp+290h] [rbp+210h] BYREF
  bool v204; // [rsp+2A7h] [rbp+227h]
  unsigned __int64 v205; // [rsp+2A8h] [rbp+228h]
  __int64 v206; // [rsp+2B0h] [rbp+230h]
  unsigned __int64 v207; // [rsp+2B8h] [rbp+238h]
  __int64 v208; // [rsp+2C0h] [rbp+240h]

  v208 = -2;
  v169 = a2;
  if ( *(_QWORD *)(a1 + 16) )
    core::cell::panic_already_borrowed(&off_1803352B0);
  *(_QWORD *)(a1 + 16) = -1;
  v206 = a1;
  if ( !a3 )
    core::option::unwrap_failed(&off_180335280);
  v5 = a1 + 24;
  v6 = *(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL);
  v184 = a3;
  v6(a3);
  v196 = v5;
  updated = layout::TextLayout::update_layout(v5);
  v9 = v8;
  if ( v8 )
  {
    v10 = updated;
LABEL_5:
    v11 = v206;
    goto LABEL_6;
  }
  layout::TextLayout::ensure_script_runs_valid(v196);
  v11 = v206;
  if ( (*(_BYTE *)(v206 + 208) & 2) != 0 )
  {
    v175 = 0;
    if ( (**(int (__fastcall ***)(__int64, int *, __int64 *))v184)(v184, &dword_1803B36E4, &v175) < 0
      || (v14 = v175) == 0 )
    {
      pperrinfo[0] = 0;
      GetErrorInfo(0, pperrinfo);
      v9 = -2003283958;
      if ( pperrinfo[0] )
        ((void (__fastcall *)(IErrorInfo *))pperrinfo[0]->lpVtbl->Release)(pperrinfo[0]);
      v10 = 0;
      goto LABEL_6;
    }
  }
  else
  {
    v14 = 0;
  }
  v15 = v184;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v184 + 8LL))(v184);
  v180 = &v169;
  v181 = v15;
  v175 = v14;
  v176 = a4;
  v177 = a5;
  v178 = 0;
  v179 = 0;
  memset(v182, 0, 25);
  v202.m256i_i32[0] = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __m256i *))(*(_QWORD *)v15 + 24LL))(v15, v169, &v202);
  if ( v16 < 0 )
    goto LABEL_121;
  if ( v202.m256i_i32[0] )
    goto LABEL_18;
  v202.m256i_i32[0] = 0;
  v66 = v184;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __m256i *))(*(_QWORD *)v184 + 40LL))(v184, v169, &v202);
  if ( v16 < 0 )
  {
LABEL_121:
    v9 = v16;
    pperrinfo[0] = 0;
    GetErrorInfo(0, pperrinfo);
    v10 = (unsigned __int64)pperrinfo[0];
    goto LABEL_122;
  }
  dwrite::pixel_snapping::IDWritePixelSnapping::get_current_transform(pperrinfo, v66, v169);
  if ( LODWORD(pperrinfo[0]) == 1 )
  {
    v10 = (unsigned __int64)pperrinfo[1];
    v9 = v165;
    v11 = v206;
    goto LABEL_122;
  }
  v202.m256i_i32[0] = HIDWORD(pperrinfo[0]);
  *(IErrorInfo **)((char *)v202.m256i_i64 + 4) = pperrinfo[1];
  v202.m256i_i32[3] = v165;
  v202.m256i_i64[2] = *(_QWORD *)((char *)&v165 + 4);
  v11 = v206;
  layout::pixel_snapper::PixelSnapper::set_pixel_grid(&v178, pperrinfo[1], &v202, (*(_DWORD *)(v206 + 208) & 2u) >> 1);
LABEL_18:
  v17 = 680;
  if ( !*(_QWORD *)(v11 + 720) )
    v17 = 32 * (unsigned int)(*(_QWORD *)(v11 + 496) != 0) + 424LL;
  v18 = *(_QWORD *)(v11 + v17 + 32);
  v10 = v18 + 80LL * *(_QWORD *)(v11 + v17 + 40);
  v170 = v11 + 320;
  v162 = v11 + 416;
  v171 = v11 + 560;
  v19 = *(float *)&v178;
  v191 = *((float *)&v178 + 2);
  v20 = *((float *)&v178 + 1);
  v192 = _mm_cvtsi128_si32(_mm_cvtsi32_si128(HIDWORD(v178)));
  v172 = v175;
  v173 = v180;
  v21 = 0;
  v174 = v10;
  while ( v18 != v10 )
  {
    if ( !*(_QWORD *)(v18 + 16) && *(_BYTE *)(v18 + 69) != 1 )
    {
      v22 = layout::run_list::RunList_layout::layout_types::InputRun_::get_run_at_layout::layout_types::InputRun_(
              v170,
              v21);
      v23 = (_QWORD *)layout::run_list::RunList_layout::font_runs::FontRun_::get_run_at_layout::font_runs::FontRun_(
                        v162,
                        v21);
      layout::metrics::get_glyph_run((unsigned int)pperrinfo, *v23, v24, v18, v171);
      memset(&v202, 0, 26);
      LOBYTE(v25) = 1;
      if ( (langtag::get_language_tag(v22 + 16, v25, &v202, 26) & 1) != 0 )
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)&v185,
          (unsigned int)qword_180336F90,
          (__int64)&off_1803370B8);
      *(_OWORD *)((char *)&v185.m256i_u64[1] + 2) = *(_OWORD *)((char *)&v202.m256i_u64[1] + 2);
      *(__m128i *)v185.m256i_i8 = _mm_load_si128((const __m128i *)&v202);
      memset(v203, 0, sizeof(v203));
      memset(&v202, 0, sizeof(v202));
      v27 = (_QWORD *)v206;
      if ( v26 )
      {
        if ( v26 >= 9 )
        {
          v29 = v26 - 1;
          if ( v26 - 1 >= 0x1A )
            v29 = 26;
          v30 = v29 + 1;
          v31 = v30 & 7;
          if ( (v30 & 7) == 0 )
            v31 = 8;
          v28 = v30 - v31;
          v32 = 0;
          do
          {
            *(__m128i *)&v202.m256i_i8[2 * v32] = _mm_unpacklo_epi8(
                                                    _mm_loadl_epi64((const __m128i *)&v185.m256i_i8[v32]),
                                                    (__m128i)0LL);
            v32 += 8;
          }
          while ( v28 != v32 );
        }
        else
        {
          v28 = 0;
        }
        do
        {
          if ( v28 == 26 )
            core::panicking::panic_bounds_check(26, 26, &off_180337650);
          v202.m256i_i16[v28] = v185.m256i_u8[v28];
          ++v28;
        }
        while ( v26 != v28 );
      }
      *(_QWORD *)&v200[14] = *(_QWORD *)&v203[14];
      si128 = _mm_load_si128((const __m128i *)&v202);
      *(_OWORD *)v200 = *(_OWORD *)v203;
      *(_OWORD *)&v199.m256i_u64[2] = *(_OWORD *)&v202.m256i_u64[2];
      *(__m128i *)v199.m256i_i8 = si128;
      v34 = 91;
      if ( __OFSUB__(0, v27[92]) )
        v34 = 63;
      v35 = 90;
      if ( __OFSUB__(0, v27[92]) )
        v35 = 62;
      if ( !__OFSUB__(0, v27[95]) )
      {
        v34 = 94;
        v35 = 93;
      }
      v36 = *(unsigned int *)(v18 + 72);
      v37 = v36 - v21;
      if ( v36 < v21 )
        core::slice::index::slice_index_order_fail(v21, *(unsigned int *)(v18 + 72), &off_180337548);
      v38 = v27[5];
      if ( v38 < v36 )
        core::slice::index::slice_end_index_len_fail(*(unsigned int *)(v18 + 72), v38, &off_180337548);
      v39 = v27[v35 + 3];
      v40 = v27[v34 + 3];
      v41 = v27[4];
      if ( v199.m256i_i16[0]
        && v199.m256i_i16[1]
        && v199.m256i_i16[2]
        && v199.m256i_i16[3]
        && v199.m256i_i16[4]
        && v199.m256i_i16[5]
        && v199.m256i_i16[6]
        && v199.m256i_i16[7]
        && v199.m256i_i16[8]
        && v199.m256i_i16[9]
        && v199.m256i_i16[10]
        && v199.m256i_i16[11]
        && v199.m256i_i16[12]
        && v199.m256i_i16[13]
        && v199.m256i_i16[14]
        && v199.m256i_i16[15]
        && *(_WORD *)v200
        && *(_WORD *)&v200[2]
        && *(_WORD *)&v200[4]
        && *(_WORD *)&v200[6]
        && *(_WORD *)&v200[8]
        && *(_WORD *)&v200[10]
        && *(_WORD *)&v200[12]
        && *(_WORD *)&v200[14]
        && *(_WORD *)&v200[16]
        && *(_WORD *)&v200[18]
        && *(_WORD *)&v200[20] )
      {
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)&v185,
          (unsigned int)qword_180337448,
          (__int64)&off_180337638);
      }
      if ( v40 < v36 )
        core::slice::index::slice_end_index_len_fail(*(unsigned int *)(v18 + 72), v40, &off_180337560);
      if ( v19 != 0.0 )
        o_roundf_0();
      if ( v20 != 0.0 )
        o_roundf_0();
      lpMem = (LPVOID)(v41 + 2 * v21);
      v207 = v21;
      v205 = v39 + 2 * v21;
      v42 = _mm_cvtsi32_si128(v168[0]);
      v190 = pperrinfo[1];
      v197 = *((_QWORD *)&v167 + 1);
      LODWORD(v201) = LOBYTE(v168[1]);
      LODWORD(v195) = HIDWORD(v168[0]);
      if ( v172 )
      {
        v43 = v175;
        v44 = *v173;
        v194 = v165;
        v161 = DWORD2(v165);
        if ( (_QWORD)v165 != DWORD2(v165) )
        {
          v202.m256i_i64[0] = 0;
          core::panicking::assert_failed_usize_usize_(&v194, &v161, &v202, &off_180336010);
        }
        if ( (_QWORD)v166 )
        {
          v160 = *((_QWORD *)&v166 + 1);
          if ( *((_QWORD *)&v166 + 1) != (_QWORD)v165 )
          {
            v202.m256i_i64[0] = 0;
            core::panicking::assert_failed_usize_usize_(&v160, &v194, &v202, &off_180336028);
          }
        }
        if ( (_QWORD)v167 )
        {
          v159 = v197;
          if ( v197 != (_QWORD)v165 )
          {
            v202.m256i_i64[0] = 0;
            core::panicking::assert_failed_usize_usize_(&v159, &v194, &v202, &off_180336040);
          }
        }
        v45 = pperrinfo[0];
        v202.m256i_i64[0] = (__int64)pperrinfo[0];
        v202.m256i_i64[1] = __PAIR64__(DWORD2(v165), _mm_cvtsi128_si32(v42));
        v202.m256i_i64[2] = (__int64)v190;
        v202.m256i_i64[3] = v166;
        *(_QWORD *)v203 = v167;
        *(_DWORD *)&v203[8] = v201;
        *(_DWORD *)&v203[12] = v195;
        v185.m256i_i64[0] = (__int64)&v199;
        v185.m256i_i64[1] = (__int64)lpMem;
        v185.m256i_i32[4] = v37;
        v185.m256i_i64[3] = v205;
        v186 = v207;
        v46 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v175 + 80LL);
      }
      else
      {
        v43 = v181;
        v44 = *v173;
        v194 = v165;
        v161 = DWORD2(v165);
        if ( (_QWORD)v165 != DWORD2(v165) )
        {
          v202.m256i_i64[0] = 0;
          core::panicking::assert_failed_usize_usize_(&v194, &v161, &v202, &off_180335FC8);
        }
        if ( (_QWORD)v166 )
        {
          v160 = *((_QWORD *)&v166 + 1);
          if ( *((_QWORD *)&v166 + 1) != (_QWORD)v165 )
          {
            v202.m256i_i64[0] = 0;
            core::panicking::assert_failed_usize_usize_(&v160, &v194, &v202, &off_180335FE0);
          }
        }
        if ( (_QWORD)v167 )
        {
          v159 = v197;
          if ( v197 != (_QWORD)v165 )
          {
            v202.m256i_i64[0] = 0;
            core::panicking::assert_failed_usize_usize_(&v159, &v194, &v202, &off_180335FF8);
          }
        }
        v45 = pperrinfo[0];
        v202.m256i_i64[0] = (__int64)pperrinfo[0];
        v202.m256i_i64[1] = __PAIR64__(DWORD2(v165), _mm_cvtsi128_si32(v42));
        v202.m256i_i64[2] = (__int64)v190;
        v202.m256i_i64[3] = v166;
        *(_QWORD *)v203 = v167;
        *(_DWORD *)&v203[8] = v201;
        *(_DWORD *)&v203[12] = v195;
        v185.m256i_i64[0] = (__int64)&v199;
        v185.m256i_i64[1] = (__int64)lpMem;
        v185.m256i_i32[4] = v37;
        v185.m256i_i64[3] = v205;
        v186 = v207;
        v46 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v181 + 48LL);
      }
      v47 = v46(v43, v44);
      if ( v47 < 0 )
      {
        v9 = v47;
        v187 = 0;
        GetErrorInfo(0, &v187);
        v10 = (unsigned __int64)v187;
        v11 = v206;
        ((void (__fastcall *)(IErrorInfo *))v45->lpVtbl->Release)(v45);
        goto LABEL_122;
      }
      v11 = v206;
      v10 = v174;
      ((void (__fastcall *)(IErrorInfo *))v45->lpVtbl->Release)(v45);
    }
    v21 = *(unsigned int *)(v18 + 72);
    v18 += 80;
  }
  v48 = 32 * (unsigned int)(*(_QWORD *)(v11 + 496) != 0);
  v49 = *(_QWORD *)(v48 + v11 + 464);
  if ( v49 )
  {
    v50 = *(_QWORD *)(v48 + v11 + 456);
    v10 = v50 + 80 * v49;
    v51 = v50 + 80;
    do
    {
      v54 = v50;
      v50 = v51;
      if ( *(_QWORD *)(v54 + 16) )
      {
        if ( *(_BYTE *)(v54 + 69) != 1 )
        {
          layout::run_list::RunList_layout::layout_types::InputRun_::get_run_at_layout::layout_types::InputRun_(v170, 0);
          v55 = v206;
          if ( *(float *)&v178 != 0.0 )
            o_roundf_0();
          if ( *((float *)&v178 + 1) != 0.0 )
            o_roundf_0();
          v56 = *(_QWORD *)(v54 + 16);
          if ( !v56 )
            core::option::unwrap_failed(&off_1803388A0);
          v57 = *(_QWORD *)(v55 + 576);
          LOBYTE(v18) = *(_BYTE *)(v54 + 60);
          layout::recent_metrics::RecentInlineObjectMetrics::get_inline_object_metrics(v182, v56, (unsigned int)v18);
          if ( !*(_BYTE *)(v54 + 70) && *(_QWORD *)v54 >= v57 )
            core::panicking::panic_bounds_check(*(_QWORD *)v54, v57, &off_1803388B8);
          v11 = v206;
          v58 = v175;
          if ( v175 )
          {
            v52 = *v180;
            v53 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v175 + 104LL);
          }
          else
          {
            if ( !*(_QWORD *)(v54 + 16) )
              core::option::unwrap_failed(&off_180337578);
            v58 = v181;
            v52 = *v180;
            v53 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v181 + 72LL);
          }
          v16 = v53(v58, v52);
          if ( v16 < 0 )
            goto LABEL_121;
        }
      }
      v51 = v50 + 80;
    }
    while ( v50 != v10 );
  }
  v59 = *(_DWORD *)(v11 + 848);
  if ( (v59 & 0x1000) == 0 )
  {
LABEL_246:
    if ( (v59 & 0x2000) != 0 )
    {
      v150 = layout::TextLayout::draw_strikethroughs(v196, &v175);
      v9 = v151;
      if ( v151 )
      {
        v10 = v150;
        v11 = v206;
        goto LABEL_122;
      }
    }
    core::ptr::drop_in_place_layout::draw::DrawingParameters_(&v175);
    v9 = 0;
    goto LABEL_5;
  }
  LODWORD(v171) = *(_DWORD *)(v11 + 212);
  LODWORD(v172) = *(_DWORD *)(v11 + 280);
  memset(v168, 0, 29);
  v167 = 0;
  v166 = 0;
  v165 = 0;
  *(_OWORD *)pperrinfo = 0;
  v187 = 0;
  v188 = (LPVOID)8;
  v189 = 0;
  v60 = 680;
  if ( !*(_QWORD *)(v11 + 720) )
    v60 = 32 * (unsigned int)(*(_QWORD *)(v11 + 496) != 0) + 424LL;
  v183 = *(_DWORD *)(v11 + 208) >> 1;
  v61 = *(unsigned int **)(v11 + 688);
  v62 = *(_QWORD *)(v11 + 696) << 6;
  v63 = _mm_cvtsi128_si32((__m128i)_mm_cmpeq_ss((__m128)0LL, (__m128)(unsigned int)v178));
  v193 = *(float *)&v178;
  if ( *(float *)&v178 == 0.0 )
    v193 = *((float *)&v178 + 1);
  LODWORD(v173) = v178;
  v183 &= 1u;
  v64 = (unsigned int *)((char *)v61 + v62);
  LODWORD(v174) = DWORD1(v178);
  v191 = v176;
  v192 = v177;
  v153 = v175;
  v154 = v180;
  v204 = *(float *)&v178 != 0.0 || *((float *)&v178 + 1) != 0.0;
  v157 = 4LL * (v63 & 1) + 24;
  v65 = 8;
  v205 = 0;
  v207 = v196 + v60;
  v158 = v64;
LABEL_127:
  while ( 1 )
  {
    v67 = 0;
    v68 = v61 != v64;
    if ( v61 == v64 )
      break;
    v69 = *((_QWORD *)v61 + 4);
    v163 = v61;
    v10 = layout::run_list::RunList_layout::layout_types::ShapingRun_::get_run_range_from_text_range_layout::layout_types::ShapingRun_(
            v207,
            v69,
            v69 + *v61);
    v71 = v70;
    LOBYTE(v67) = v68;
    v163 = (unsigned int *)((char *)v163 + (unsigned int)(v67 << 6));
    v72 = 80 * v10 + 66;
    v73 = v10;
    v11 = v206;
    v74 = v207;
    do
    {
      if ( v73 >= v71 )
      {
        v61 = v163;
        v64 = v158;
        goto LABEL_127;
      }
      v75 = *(_QWORD *)(v207 + 16);
      if ( v73 >= v75 )
        core::panicking::panic_bounds_check(v73, v75, &off_180337590);
      v76 = *(_QWORD *)(v207 + 8);
      ++v73;
      v77 = *(_BYTE *)(v76 + v72) == 0;
      v72 += 80;
    }
    while ( v77 );
    v78 = v71 < v10;
    v79 = v71 - v10;
    v80 = 0;
    if ( !v78 )
      v80 = v79;
    v81 = v80 - v205;
    v201 = v80;
    if ( v80 <= v205 )
    {
      v85 = v80;
    }
    else
    {
      if ( v81 > (unsigned __int64)v187 - v205 )
      {
        alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__5(
          (unsigned int)&v187,
          v205,
          v81,
          8,
          8);
        v65 = (__int64)v188;
        v205 = v189;
        v74 = v207;
      }
      v82 = v205;
      v83 = (_QWORD *)(v65 + 8 * v205);
      if ( v81 < 2 )
      {
        v84 = v205;
      }
      else
      {
        memset_0(v83, 0, 8 * v81 - 8);
        v83 = (_QWORD *)(v65 + 8 * (v82 + v81) - 8);
        v84 = v82 + v81 - 1;
      }
      *v83 = 0;
      v85 = v84 + 1;
      v76 = *(_QWORD *)(v74 + 8);
      v75 = *(_QWORD *)(v74 + 16);
      v65 = (__int64)v188;
      LODWORD(v80) = v201;
    }
    v189 = v85;
    v205 = v85;
    lpMem = (LPVOID)v65;
    layout::get_reordered_run_indices(v76, v75, v10, v80, v65, v85);
    v10 = 0;
    v11 = v206;
    v86 = v207;
    v87 = v201;
LABEL_143:
    if ( v10 < v87 )
    {
      v88 = 0.0;
      v89 = 0;
      v90 = LODWORD(FLOAT_N3_4028235e38);
      v91 = 0;
      v92 = 0;
      v93 = 0.0;
      v94 = 0;
      while ( 1 )
      {
        if ( v10 >= v205 )
          core::panicking::panic_bounds_check(v10, v205, &off_1803375A8);
        v96 = *((_QWORD *)lpMem + v10);
        v97 = *(_QWORD *)(v86 + 16);
        if ( v96 >= v97 )
          core::panicking::panic_bounds_check(v96, v97, &off_1803375C0);
        v98 = *(_QWORD *)(v86 + 8);
        v99 = 80 * v96;
        if ( *(_BYTE *)(v98 + 80 * v96 + 66) )
        {
          if ( ((unsigned __int8)v91 & 1) == 0 )
          {
            v92 = 0;
            LOBYTE(v91) = 1;
            v89 = v10;
            v93 = 0.0;
            v94 = 0;
          }
          v190 = v91;
          v195 = v10;
          if ( v96 )
            v100 = *(unsigned int *)(v99 + v98 - 8);
          else
            v100 = 0;
          v101 = layout::run_list::RunList_layout::font_runs::FontRun_::get_run_at_layout::font_runs::FontRun_(
                   v162,
                   v100);
          font_metrics = (unsigned __int16 *)layout::recent_metrics::RecentFontMetrics::get_font_metrics(
                                               pperrinfo,
                                               v196,
                                               *(_QWORD *)v101);
          v103 = v99 + v98;
          v104 = (__int16)font_metrics[6];
          v105 = *(float *)(v101 + 16);
          v106 = *font_metrics;
          v107 = *(float *)(v103 + 36);
          v95 = *(unsigned int *)(v103 + 40);
          v108 = font_metrics[7];
          v109 = font_metrics[4];
          *(float *)&v95 = *(float *)&v95 + *(float *)(v103 + 32);
          v110 = *(unsigned __int8 *)(v103 + 60);
          if ( (_BYTE)v110 )
          {
            v111 = v100;
            v112 = *font_metrics;
            v113 = font_metrics[4];
            *(float *)&v95 = *(float *)&v95
                           - (float)((float)((float)(int)layout::layout_helpers::get_baseline_delta_from_text_layout(
                                                           v196,
                                                           v111,
                                                           v110,
                                                           *(_QWORD *)(v101 + 8),
                                                           1)
                                           * *(float *)(v101 + 16))
                                   / (float)v112);
            v109 = v113;
            v106 = v112;
          }
          else if ( ((*(_BYTE *)(v103 + 52) ^ *(_BYTE *)(v103 + 48)) & 1) != 0 )
          {
            LODWORD(v197) = *font_metrics;
            v114 = v109;
            *(float *)&v95 = *(float *)&v95
                           + (float)((float)((float)(int)(2
                                                        * layout::layout_helpers::get_baseline_delta_from_text_layout(
                                                            v196,
                                                            v100,
                                                            v110,
                                                            *(_QWORD *)(v101 + 8),
                                                            2))
                                           * *(float *)(v101 + 16))
                                   / (float)*font_metrics);
            v109 = v114;
            v106 = v197;
          }
          v94.m128_f32[0] = v94.m128_f32[0] - (float)((float)((float)((float)v104 * v105) / (float)v106) * v107);
          v93 = v93 + (float)((float)((float)((float)v108 * v105) / (float)v106) * v107);
          v115 = 0;
          v115.m128_f32[0] = (float)((float)v109 * v105) / (float)v106;
          v116 = _mm_cmple_ss(v115, v92);
          v92 = _mm_or_ps(_mm_and_ps(v116, v92), _mm_andnot_ps(v116, v115));
          v88 = v88 + v107;
          v11 = v206;
          v87 = v201;
          v91 = v190;
          v10 = v195;
          if ( *(float *)&v95 > *(float *)&v90 )
            goto LABEL_147;
        }
        else
        {
          v87 = v201;
          if ( ((unsigned __int8)v91 & 1) != 0 )
          {
            v86 = v207;
LABEL_163:
            if ( ((unsigned __int8)v91 & 1) != 0 && v88 > 0.0 )
            {
              v94.m128_f32[0] = v94.m128_f32[0] / v88;
              if ( v204 )
              {
                v94.m128_f32[0] = v94.m128_f32[0] * v193;
                v117.m128_u64[1] = v94.m128_u64[1];
                *(double *)v117.m128_u64 = o_roundf_0();
                v118 = _mm_cmpeq_ss(v117, (__m128)0LL);
                v119 = *((_DWORD *)&DOUBLE_N0_007812501848093234 + (v94.m128_f32[0] < 0.0));
                v86 = v207;
                v94 = _mm_cmpneq_ss(v94, (__m128)0LL);
                v94.m128_f32[0] = COERCE_FLOAT(
                                    _mm_andnot_ps(v94, v117).m128_u32[0]
                                  | (v119 & v118.m128_i32[0] | _mm_andnot_ps(v118, v117).m128_u32[0]) & v94.m128_i32[0])
                                * *(float *)((char *)&v175 + v157);
                v87 = v201;
              }
              v120 = v93 / v88;
              v155 = v175;
              v156 = v181;
              v195 = v10;
              while ( v89 < v10 )
              {
                if ( v89 >= v205 )
                  core::panicking::panic_bounds_check(v89, v205, &off_1803375D8);
                v121 = *((_QWORD *)lpMem + v89);
                v122 = *(_QWORD *)(v86 + 16);
                if ( v121 >= v122 )
                  core::panicking::panic_bounds_check(v121, v122, &off_1803375F0);
                v123 = *(_QWORD *)(v86 + 8);
                v124 = 80 * v121;
                if ( v121 )
                  v125 = *(unsigned int *)(v124 + v123 - 8);
                else
                  v125 = 0;
                v126 = (_QWORD *)layout::run_list::RunList_layout::font_runs::FontRun_::get_run_at_layout::font_runs::FontRun_(
                                   v162,
                                   v125);
                layout::recent_metrics::RecentFontMetrics::get_font_metrics(pperrinfo, v196, *v126);
                v127 = v124 + v123;
                v128 = layout::run_list::RunList_layout::layout_types::InputRun_::get_run_at_layout::layout_types::InputRun_(
                         v170,
                         v125);
                memset(&v202, 0, 26);
                v190 = (IErrorInfo *)(v128 + 16);
                LOBYTE(v129) = 1;
                if ( (langtag::get_language_tag(v128 + 16, v129, &v202, 26) & 1) != 0 )
                  core::result::unwrap_failed(
                    (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                    43,
                    (unsigned int)&v185,
                    (unsigned int)qword_180336F90,
                    (__int64)&off_1803370B8);
                *(_OWORD *)((char *)&v185.m256i_u64[1] + 2) = *(_OWORD *)((char *)&v202.m256i_u64[1] + 2);
                *(__m128i *)v185.m256i_i8 = _mm_load_si128((const __m128i *)&v202);
                memset(v203, 0, sizeof(v203));
                memset(&v202, 0, sizeof(v202));
                v10 = v195;
                if ( v130 )
                {
                  if ( v130 >= 9 )
                  {
                    v132 = v130 - 1;
                    if ( v130 - 1 >= 0x1A )
                      v132 = 26;
                    v133 = v132 + 1;
                    v134 = v133 & 7;
                    if ( (v133 & 7) == 0 )
                      v134 = 8;
                    v131 = v133 - v134;
                    v135 = 0;
                    do
                    {
                      *(__m128i *)&v202.m256i_i8[2 * v135] = _mm_unpacklo_epi8(
                                                               _mm_loadl_epi64((const __m128i *)&v185.m256i_i8[v135]),
                                                               (__m128i)0LL);
                      v135 += 8;
                    }
                    while ( v131 != v135 );
                  }
                  else
                  {
                    v131 = 0;
                  }
                  do
                  {
                    if ( v131 == 26 )
                      core::panicking::panic_bounds_check(26, 26, &off_180337650);
                    v202.m256i_i16[v131] = v185.m256i_u8[v131];
                    ++v131;
                  }
                  while ( v130 != v131 );
                }
                *(_QWORD *)&v200[14] = *(_QWORD *)&v203[14];
                *(_OWORD *)v200 = *(_OWORD *)v203;
                v199 = v202;
                if ( v202.m256i_i16[0]
                  && v199.m256i_i16[1]
                  && v199.m256i_i16[2]
                  && v199.m256i_i16[3]
                  && v199.m256i_i16[4]
                  && v199.m256i_i16[5]
                  && v199.m256i_i16[6]
                  && v199.m256i_i16[7]
                  && v199.m256i_i16[8]
                  && v199.m256i_i16[9]
                  && v199.m256i_i16[10]
                  && v199.m256i_i16[11]
                  && v199.m256i_i16[12]
                  && v199.m256i_i16[13]
                  && v199.m256i_i16[14]
                  && v199.m256i_i16[15]
                  && *(_WORD *)v200
                  && *(_WORD *)&v200[2]
                  && *(_WORD *)&v200[4]
                  && *(_WORD *)&v200[6]
                  && *(_WORD *)&v200[8]
                  && *(_WORD *)&v200[10]
                  && *(_WORD *)&v200[12]
                  && *(_WORD *)&v200[14]
                  && *(_WORD *)&v200[16]
                  && *(_WORD *)&v200[18]
                  && *(_WORD *)&v200[20] )
                {
                  core::result::unwrap_failed(
                    (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
                    43,
                    (unsigned int)&v185,
                    (unsigned int)qword_180337448,
                    (__int64)&off_180337638);
                }
                LODWORD(v197) = *(_DWORD *)(v127 + 52) & 1 | *(_DWORD *)(v206 + 208) & 0xFFFFFFFE;
                v136 = *(float *)(v127 + 36);
                while ( ++v89 < v10 )
                {
                  if ( v89 >= v205 )
                    core::panicking::panic_bounds_check(v89, v205, &off_180337608);
                  v137 = *((_QWORD *)lpMem + v89);
                  v138 = *(_QWORD *)(v207 + 16);
                  if ( v137 >= v138 )
                    core::panicking::panic_bounds_check(v137, v138, &off_180337620);
                  v139 = *(_QWORD *)(v207 + 8);
                  v140 = 80 * v137;
                  if ( ((*(_BYTE *)(v127 + 48) ^ *(_BYTE *)(v139 + 80 * v137 + 48)) & 1) != 0 )
                    break;
                  v141 = v137 ? *(unsigned int *)(v140 + v139 - 8) : 0LL;
                  v142 = layout::run_list::RunList_layout::layout_types::InputRun_::get_run_at_layout::layout_types::InputRun_(
                           v170,
                           v141);
                  v10 = v195;
                  if ( *(struct IErrorInfoVtbl **)(v142 + 16) != v190->lpVtbl
                    || *(_DWORD *)(v142 + 24) != *(_DWORD *)(v128 + 24)
                    || *(_DWORD *)(v142 + 28) != *(_DWORD *)(v128 + 28) )
                  {
                    break;
                  }
                  v143 = *(_QWORD *)(v142 + 56);
                  v144 = *(_QWORD *)(v128 + 56);
                  if ( v143 && v144 )
                  {
                    if ( v143 != v144 )
                      break;
                  }
                  else if ( v144 | v143 )
                  {
                    break;
                  }
                  v136 = v136 + *(float *)(v140 + v139 + 36);
                }
                v11 = v206;
                v145 = v197;
                if ( *(float *)&v173 != 0.0 )
                  o_roundf_0();
                if ( *(float *)&v174 != 0.0 )
                  o_roundf_0();
                v146 = *v154;
                if ( v153 )
                {
                  v202.m256i_i64[0] = __PAIR64__(LODWORD(v120), LODWORD(v136));
                  v202.m256i_i64[1] = __PAIR64__(v92.m128_u32[0], v94.m128_u32[0]);
                  v202.m256i_i64[2] = __PAIR64__(v171, v145);
                  v202.m256i_i64[3] = (__int64)&v199;
                  *(_DWORD *)v203 = v172;
                  v86 = v207;
                  v147 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v155 + 88LL))(v155, v146);
                  if ( v147 < 0 )
                    goto LABEL_241;
                  v87 = v201;
                }
                else
                {
                  v202.m256i_i64[0] = __PAIR64__(LODWORD(v120), LODWORD(v136));
                  v202.m256i_i64[1] = __PAIR64__(v92.m128_u32[0], v94.m128_u32[0]);
                  v202.m256i_i64[2] = __PAIR64__(v171, v145);
                  v202.m256i_i64[3] = (__int64)&v199;
                  *(_DWORD *)v203 = v172;
                  v86 = v207;
                  v147 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v156 + 56LL))(v156, v146);
                  if ( v147 < 0 )
                  {
LABEL_241:
                    v9 = v147;
                    v185.m256i_i64[0] = 0;
                    GetErrorInfo(0, (IErrorInfo **)&v185);
                    v10 = v185.m256i_i64[0];
                    if ( v187 )
                    {
                      ProcessHeap = GetProcessHeap();
                      HeapFree(ProcessHeap, 0, lpMem);
                    }
                    v149 = v168[0];
                    if ( !v168[0] )
                      goto LABEL_122;
                    goto LABEL_244;
                  }
                  v87 = v201;
                }
              }
            }
            goto LABEL_143;
          }
        }
        v95 = v90;
LABEL_147:
        v86 = v207;
        ++v10;
        v90 = v95;
        if ( v10 >= v87 )
          goto LABEL_163;
      }
    }
    v61 = v163;
    v64 = v158;
    v65 = (__int64)lpMem;
  }
  if ( v187 )
  {
    v10 = (unsigned __int64)v188;
    v152 = GetProcessHeap();
    HeapFree(v152, 0, (LPVOID)v10);
  }
  v149 = v168[0];
  if ( !v168[0] )
    goto LABEL_245;
  v9 = 0;
LABEL_244:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v149 + 16LL))(v149);
  if ( !v9 )
  {
LABEL_245:
    v59 = *(_DWORD *)(v11 + 848);
    goto LABEL_246;
  }
LABEL_122:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v181 + 16LL))(v181);
  if ( v175 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v175 + 16LL))(v175);
  if ( v182[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v182[0] + 16LL))(v182[0]);
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v184 + 16LL))(v184);
  ++*(_QWORD *)(v11 + 16);
  v12 = 0;
  if ( v9 )
  {
    if ( v9 != 1398755147 )
      v12 = v9;
    if ( v10 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return v12;
}

```

## disassembly

```asm
0x180019820  push    rbp
0x180019821  push    r15
0x180019823  push    r14
0x180019825  push    r13
0x180019827  push    r12
0x180019829  push    rsi
0x18001982a  push    rdi
0x18001982b  push    rbx
0x18001982c  sub     rsp, 378h
0x180019833  lea     rbp, [rsp+80h]
0x18001983b  movaps  [rbp+330h+var_50], xmm15
0x180019843  movaps  [rbp+330h+var_60], xmm14
0x18001984b  movaps  [rbp+330h+var_70], xmm13
0x180019853  movdqa  [rbp+330h+var_80], xmm12
0x18001985c  movaps  [rbp+330h+var_90], xmm11
0x180019864  movaps  [rbp+330h+var_A0], xmm10
0x18001986c  movaps  [rbp+330h+var_B0], xmm9
0x180019874  movaps  [rbp+330h+var_C0], xmm8
0x18001987c  movaps  [rbp+330h+var_D0], xmm7
0x180019883  movaps  [rbp+330h+var_E0], xmm6
0x18001988a  mov     [rbp+330h+var_F0], 0FFFFFFFFFFFFFFFEh
0x180019895  mov     [rbp+330h+var_298], rdx
0x18001989c  cmp     qword ptr [rcx+10h], 0
0x1800198a1  jnz     loc_18001B515
0x1800198a7  mov     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x1800198af  test    r8, r8
0x1800198b2  mov     [rbp+330h+var_100], rcx
0x1800198b9  jz      loc_18001B526
0x1800198bf  movaps  xmm6, xmm3
0x1800198c2  lea     rsi, [rcx+18h]
0x1800198c6  mov     rax, [r8]
0x1800198c9  mov     rax, [rax+8]
0x1800198cd  mov     [rbp+330h+var_208], r8
0x1800198d4  mov     rcx, r8
0x1800198d7  call    cs:__guard_dispatch_icall_fptr
0x1800198dd  mov     [rbp+330h+var_198], rsi
0x1800198e4  mov     rcx, rsi
0x1800198e7  call    layout__TextLayout__update_layout
0x1800198ec  mov     ebx, edx
0x1800198ee  test    edx, edx
0x1800198f0  jz      loc_1800199A0
0x1800198f6  mov     rsi, rax
0x1800198f9  mov     r13, [rbp+330h+var_100]
0x180019900  mov     rcx, [rbp+330h+var_208]
0x180019907  mov     rax, [rcx]
0x18001990a  mov     rax, [rax+10h]
0x18001990e  call    cs:__guard_dispatch_icall_fptr
0x180019914  inc     qword ptr [r13+10h]
0x180019918  xor     edi, edi
0x18001991a  test    ebx, ebx
0x18001991c  jz      short loc_18001993C
0x18001991e  cmp     ebx, 535F4F4Bh
0x180019924  cmovnz  edi, ebx
0x180019927  test    rsi, rsi
0x18001992a  jz      short loc_18001993C
0x18001992c  mov     rax, [rsi]
0x18001992f  mov     rax, [rax+10h]
0x180019933  mov     rcx, rsi
0x180019936  call    cs:__guard_dispatch_icall_fptr
0x18001993c  mov     eax, edi
0x18001993e  movaps  xmm6, [rbp+330h+var_E0]
0x180019945  movaps  xmm7, [rbp+330h+var_D0]
0x18001994c  movaps  xmm8, [rbp+330h+var_C0]
0x180019954  movaps  xmm9, [rbp+330h+var_B0]
0x18001995c  movaps  xmm10, [rbp+330h+var_A0]
0x180019964  movaps  xmm11, [rbp+330h+var_90]
0x18001996c  movaps  xmm12, [rbp+330h+var_80]
0x180019974  movaps  xmm13, [rbp+330h+var_70]
0x18001997c  movaps  xmm14, [rbp+330h+var_60]
0x180019984  movaps  xmm15, [rbp+330h+var_50]
0x18001998c  add     rsp, 378h
0x180019993  pop     rbx
0x180019994  pop     rdi
0x180019995  pop     rsi
0x180019996  pop     r12
0x180019998  pop     r13
0x18001999a  pop     r14
0x18001999c  pop     r15
0x18001999e  pop     rbp
0x18001999f  retn
0x1800199a0  mov     rcx, [rbp+330h+var_198]
0x1800199a7  call    layout__TextLayout__ensure_script_runs_valid
0x1800199ac  mov     r13, [rbp+330h+var_100]
0x1800199b3  test    byte ptr [r13+0D0h], 2
0x1800199bb  jnz     short loc_1800199C1
0x1800199bd  xor     esi, esi
0x1800199bf  jmp     short loc_180019A05
0x1800199c1  mov     [rbp+330h+var_268], 0
0x1800199cc  mov     rcx, [rbp+330h+var_208]
0x1800199d3  mov     rax, [rcx]
0x1800199d6  mov     rax, [rax]
0x1800199d9  lea     rdx, dword_1803B36E4
0x1800199e0  lea     r8, [rbp+330h+var_268]
0x1800199e7  call    cs:__guard_dispatch_icall_fptr
0x1800199ed  test    eax, eax
0x1800199ef  js      loc_18001A27D
0x1800199f5  mov     rsi, [rbp+330h+var_268]
0x1800199fc  test    rsi, rsi
0x1800199ff  jz      loc_18001A27D
0x180019a05  movss   xmm7, [rbp+330h+arg_20]
0x180019a0d  mov     rdi, [rbp+330h+var_208]
0x180019a14  mov     rax, [rdi]
0x180019a17  mov     rax, [rax+8]
0x180019a1b  mov     rcx, rdi
0x180019a1e  call    cs:__guard_dispatch_icall_fptr
0x180019a24  lea     rax, [rbp+330h+var_298]
0x180019a2b  mov     [rbp+330h+var_240], rax
0x180019a32  mov     [rbp+330h+var_238], rdi
0x180019a39  mov     [rbp+330h+var_268], rsi
0x180019a40  movss   [rbp+330h+var_260], xmm6
0x180019a48  movss   [rbp+330h+var_25C], xmm7
0x180019a50  xorps   xmm0, xmm0
0x180019a53  movups  [rbp+330h+var_258], xmm0
0x180019a5a  mov     [rbp+330h+var_248], 0
0x180019a65  movups  xmmword ptr [rbp+330h+var_230], xmm0
0x180019a6c  movups  xmmword ptr [rbp+330h+var_230+9], xmm0
0x180019a73  mov     rdx, [rbp+330h+var_298]
0x180019a7a  mov     dword ptr [rbp+330h+var_140], 0
0x180019a84  mov     rax, [rdi]
0x180019a87  mov     rax, [rax+18h]
0x180019a8b  lea     r8, [rbp+330h+var_140]
0x180019a92  mov     rcx, rdi
0x180019a95  call    cs:__guard_dispatch_icall_fptr
0x180019a9b  test    eax, eax
0x180019a9d  js      loc_18001A7A3
0x180019aa3  cmp     dword ptr [rbp+330h+var_140], 0
0x180019aaa  jz      loc_18001A73B
0x180019ab0  mov     eax, 2A8h
0x180019ab5  cmp     qword ptr [r13+2D0h], 0
0x180019abd  jnz     short loc_180019AD5
0x180019abf  xor     eax, eax
0x180019ac1  cmp     qword ptr [r13+1F0h], 0
0x180019ac9  setnz   al
0x180019acc  shl     eax, 5
0x180019acf  add     rax, 1A8h
0x180019ad5  mov     r14, [r13+rax+20h]
0x180019ada  mov     rax, [r13+rax+28h]
0x180019adf  lea     rsi, [rax+rax*4]
0x180019ae3  shl     rsi, 4
0x180019ae7  add     rsi, r14
0x180019aea  lea     rax, [r13+140h]
0x180019af1  mov     [rbp+330h+var_290], rax
0x180019af8  lea     rax, [r13+1A0h]
0x180019aff  mov     [rbp+330h+var_310], rax
0x180019b03  lea     rax, [r13+230h]
0x180019b0a  mov     [rbp+330h+var_288], rax
0x180019b11  movss   xmm8, [rbp+330h+var_260]
0x180019b1a  movss   xmm9, [rbp+330h+var_25C]
0x180019b23  movss   xmm10, dword ptr [rbp+330h+var_258]
0x180019b2c  movss   xmm11, dword ptr [rbp+330h+var_248]
0x180019b35  movss   xmm0, dword ptr [rbp+330h+var_258+8]
0x180019b3d  movss   [rbp+330h+var_1B4], xmm0
0x180019b45  movss   xmm13, dword ptr [rbp+330h+var_258+4]
0x180019b4e  movss   xmm14, dword ptr [rbp+330h+var_248+4]
0x180019b57  movd    xmm0, dword ptr [rbp+330h+var_258+0Ch]
0x180019b5f  movd    [rbp+330h+var_1B0], xmm0
0x180019b67  mov     rax, [rbp+330h+var_268]
0x180019b6e  mov     [rbp+330h+var_280], rax
0x180019b75  mov     rax, [rbp+330h+var_240]
0x180019b7c  mov     [rbp+330h+var_278], rax
0x180019b83  pxor    xmm12, xmm12
0x180019b88  xorps   xmm15, xmm15
0x180019b8c  xor     r12d, r12d
0x180019b8f  mov     [rbp+330h+var_270], rsi
0x180019b96  jmp     short loc_180019BA7
0x180019ba0  mov     r12d, [r14+48h]
0x180019ba4  mov     r14, rdi
0x180019ba7  lea     rdi, [r14+50h]
0x180019bab  cmp     r14, rsi
0x180019bae  cmovz   rdi, r14
0x180019bb2  jz      loc_18001A2B3
0x180019bb8  cmp     qword ptr [r14+10h], 0
0x180019bbd  jnz     short loc_180019BA0
0x180019bbf  cmp     byte ptr [r14+45h], 1
0x180019bc4  jz      short loc_180019BA0
0x180019bc6  mov     rcx, [rbp+330h+var_290]
0x180019bcd  mov     rdx, r12
0x180019bd0  call    layout__run_list__RunList_layout__layout_types__InputRun___get_run_at_layout__layout_types__InputRun_
0x180019bd5  mov     r15, rax
0x180019bd8  mov     rcx, [rbp+330h+var_310]
0x180019bdc  mov     rdx, r12
0x180019bdf  call    layout__run_list__RunList_layout__font_runs__FontRun___get_run_at_layout__font_runs__FontRun_
0x180019be4  mov     rdx, [rax]
0x180019be7  movss   xmm2, dword ptr [rax+10h]
0x180019bec  mov     rax, [rbp+330h+var_288]
0x180019bf3  mov     [rsp+3B0h+var_390], rax
0x180019bf8  lea     rcx, [rbp+330h+pperrinfo]
0x180019bfc  mov     r9, r14
0x180019bff  call    layout__metrics__get_glyph_run
0x180019c04  lea     rcx, [r15+10h]
0x180019c08  movdqu  [rbp+330h+var_140+0Ah], xmm12
0x180019c11  movdqa  [rbp+330h+var_140], xmm12
0x180019c1a  mov     r9d, 1Ah
0x180019c20  mov     dl, 1
0x180019c22  lea     r8, [rbp+330h+var_140]
0x180019c29  call    langtag__get_language_tag
0x180019c2e  test    al, 1
0x180019c30  jnz     loc_18001B537
0x180019c36  movups  xmm0, [rbp+330h+var_140+0Ah]
0x180019c3d  movups  xmmword ptr [rbp+330h+var_200+0Ah], xmm0
0x180019c44  movdqa  xmm0, [rbp+330h+var_140]
0x180019c4c  movdqa  xmmword ptr [rbp+130h], xmm0
0x180019c54  movdqa  xmmword ptr [rbp+330h+var_120], xmm12
0x180019c5d  movdqa  [rbp+330h+var_130], xmm12
0x180019c66  movdqa  [rbp+330h+var_140], xmm12
0x180019c6f  mov     qword ptr [rbp+330h+var_120+0Eh], 0
0x180019c7a  test    rdx, rdx
0x180019c7d  mov     r9, [rbp+330h+var_100]
0x180019c84  jz      loc_180019D06
0x180019c8a  cmp     rdx, 9
0x180019c8e  jnb     short loc_180019C94
0x180019c90  xor     eax, eax
0x180019c92  jmp     short loc_180019CE0
0x180019c94  lea     rax, [rdx-1]
0x180019c98  cmp     rax, 1Ah
0x180019c9c  mov     ecx, 1Ah
0x180019ca1  cmovnb  rax, rcx
0x180019ca5  inc     rax
0x180019ca8  mov     ecx, eax
0x180019caa  and     ecx, 7
0x180019cad  mov     r8d, 8
0x180019cb3  cmovz   rcx, r8
0x180019cb7  sub     rax, rcx
0x180019cba  xor     ecx, ecx
0x180019cbc  nop     dword ptr [rax+00h]
0x180019cc0  movq    xmm0, [rbp+rcx+330h+var_200]
0x180019cc9  punpcklbw xmm0, xmm12
0x180019cce  movdqu  [rbp+rcx*2+330h+var_140], xmm0
0x180019cd7  add     rcx, 8
0x180019cdb  cmp     rax, rcx
0x180019cde  jnz     short loc_180019CC0
0x180019ce0  cmp     rax, 1Ah
0x180019ce4  jz      loc_18001B6F7
0x180019cea  movzx   ecx, byte ptr [rbp+rax+330h+var_200]
0x180019cf2  mov     word ptr [rbp+rax*2+330h+var_140], cx
0x180019cfa  lea     rcx, [rax+1]
0x180019cfe  mov     rax, rcx
0x180019d01  cmp     rdx, rcx
0x180019d04  jnz     short loc_180019CE0
0x180019d06  mov     rax, qword ptr [rbp+330h+var_120+0Eh]
0x180019d0d  mov     qword ptr [rbp+330h+var_160+0Eh], rax
0x180019d14  movdqa  xmm0, [rbp+330h+var_140]
0x180019d1c  movaps  xmm1, [rbp+330h+var_130]
0x180019d23  movaps  xmm2, xmmword ptr [rbp+330h+var_120]
0x180019d2a  movaps  xmmword ptr [rbp+1D0h], xmm2
0x180019d31  movaps  [rbp+330h+var_170], xmm1
0x180019d38  movdqa  [rbp+330h+var_180], xmm0
0x180019d40  xor     eax, eax
0x180019d42  cmp     rax, [r9+2E0h]
0x180019d49  mov     ecx, 2D8h
0x180019d4e  mov     edx, 1F8h
0x180019d53  cmovo   rcx, rdx
0x180019d57  mov     r8d, 2D0h
0x180019d5d  mov     edx, 1F0h
0x180019d62  cmovo   r8, rdx
0x180019d66  cmp     rax, [r9+2F8h]
0x180019d6d  mov     eax, 2F0h
0x180019d72  cmovno  rcx, rax
0x180019d76  mov     eax, 2E8h
0x180019d7b  cmovno  r8, rax
0x180019d7f  mov     eax, [r14+48h]
0x180019d83  mov     rbx, rax
0x180019d86  sub     rbx, r12
0x180019d89  jb      loc_18001B567
0x180019d8f  mov     rdx, [r9+28h]
0x180019d93  cmp     rdx, rax
0x180019d96  jb      loc_18001B57E
0x180019d9c  mov     rsi, [r9+r8+18h]
0x180019da1  mov     rdx, [r9+rcx+18h]
0x180019da6  mov     r13, [r9+20h]
0x180019daa  cmp     word ptr [rbp+330h+var_180], 0
0x180019db2  jz      loc_180019EF4
0x180019db8  cmp     word ptr [rbp+330h+var_180+2], 0
0x180019dc0  jz      loc_180019EF4
0x180019dc6  cmp     word ptr [rbp+330h+var_180+4], 0
0x180019dce  jz      loc_180019EF4
0x180019dd4  cmp     word ptr [rbp+330h+var_180+6], 0
0x180019ddc  jz      loc_180019EF4
0x180019de2  cmp     word ptr [rbp+330h+var_180+8], 0
0x180019dea  jz      loc_180019EF4
0x180019df0  cmp     word ptr [rbp+330h+var_180+0Ah], 0
0x180019df8  jz      loc_180019EF4
0x180019dfe  cmp     word ptr [rbp+330h+var_180+0Ch], 0
0x180019e06  jz      loc_180019EF4
0x180019e0c  cmp     word ptr [rbp+330h+var_180+0Eh], 0
0x180019e14  jz      loc_180019EF4
0x180019e1a  cmp     word ptr [rbp+330h+var_170], 0
0x180019e22  jz      loc_180019EF4
0x180019e28  cmp     word ptr [rbp+330h+var_170+2], 0
0x180019e30  jz      loc_180019EF4
0x180019e36  cmp     word ptr [rbp+330h+var_170+4], 0
0x180019e3e  jz      loc_180019EF4
0x180019e44  cmp     word ptr [rbp+330h+var_170+6], 0
0x180019e4c  jz      loc_180019EF4
0x180019e52  cmp     word ptr [rbp+330h+var_170+8], 0
0x180019e5a  jz      loc_180019EF4
0x180019e60  cmp     word ptr [rbp+330h+var_170+0Ah], 0
0x180019e68  jz      loc_180019EF4
0x180019e6e  cmp     word ptr [rbp+330h+var_170+0Ch], 0
0x180019e76  jz      short loc_180019EF4
  ... truncated ...
```
