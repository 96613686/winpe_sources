# shaping_cache::get_glyph_placements

- ea: `0x1800d3fc0`
- end: `0x1800d5455`
- name: `shaping_cache::get_glyph_placements`
- size: `5269`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, __int64, int, int, __int64, int, char, char, __int16, char, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, void *, __int64, void *, __int64)`
- caller_count: `4`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180005820`
- `0x1800064c0`
- `0x18005a9a0`
- `0x18005ed20`

## callees

- `0x180043730`
- `0x180065ec0`
- `0x18008cb70`
- `0x18008d2d0`
- `0x1800a0390`
- `0x1800a0800`
- `0x1800a13b0`
- `0x1800ce7d0`
- `0x1800cedf0`
- `0x1800d0c60`
- `0x1800d3d40`
- `0x1800d3fc0`
- `0x180212f4c`
- `0x18021e1b6`
- `0x180316190`
- `0x1803168c1`
- `0x180316a30`
- `0x180316ae0`
- `0x180316ee0`
- `0x18031716c`
- `0x180318360`

## import_xrefs

- `kernel32!HeapFree` at `0x1800d472d`
- `kernel32!HeapFree` at `0x1800d4752`
- `kernel32!HeapFree` at `0x1800d4777`
- `kernel32!HeapFree` at `0x1800d479c`
- `kernel32!HeapFree` at `0x1800d47bf`
- `kernel32!HeapFree` at `0x1800d47de`
- `kernel32!HeapFree` at `0x1800d47fd`
- `kernel32!HeapFree` at `0x1800d4a7a`
- `kernel32!HeapFree` at `0x1800d4e0d`
- `kernel32!HeapFree` at `0x1800d4e32`
- `kernel32!HeapFree` at `0x1800d4e57`
- `kernel32!HeapFree` at `0x1800d4e7c`
- `kernel32!HeapFree` at `0x1800d4ea1`
- `kernel32!HeapFree` at `0x1800d4ec4`
- `kernel32!HeapFree` at `0x1800d4ee3`
- `kernel32!HeapFree` at `0x1800d472d`
- `kernel32!HeapFree` at `0x1800d4752`
- `kernel32!HeapFree` at `0x1800d4777`
- `kernel32!HeapFree` at `0x1800d479c`
- `kernel32!HeapFree` at `0x1800d47bf`
- `kernel32!HeapFree` at `0x1800d47de`
- `kernel32!HeapFree` at `0x1800d47fd`
- `kernel32!HeapFree` at `0x1800d4a7a`
- `kernel32!HeapFree` at `0x1800d4e0d`
- `kernel32!HeapFree` at `0x1800d4e32`
- `kernel32!HeapFree` at `0x1800d4e57`
- `kernel32!HeapFree` at `0x1800d4e7c`
- `kernel32!HeapFree` at `0x1800d4ea1`
- `kernel32!HeapFree` at `0x1800d4ec4`
- `kernel32!HeapFree` at `0x1800d4ee3`
- `kernel32!GetProcessHeap` at `0x1800d471f`
- `kernel32!GetProcessHeap` at `0x1800d4744`
- `kernel32!GetProcessHeap` at `0x1800d4769`
- `kernel32!GetProcessHeap` at `0x1800d478e`
- `kernel32!GetProcessHeap` at `0x1800d47b1`
- `kernel32!GetProcessHeap` at `0x1800d47d0`
- `kernel32!GetProcessHeap` at `0x1800d47ef`
- `kernel32!GetProcessHeap` at `0x1800d4a6c`
- `kernel32!GetProcessHeap` at `0x1800d4dff`
- `kernel32!GetProcessHeap` at `0x1800d4e24`
- `kernel32!GetProcessHeap` at `0x1800d4e49`
- `kernel32!GetProcessHeap` at `0x1800d4e6e`
- `kernel32!GetProcessHeap` at `0x1800d4e93`
- `kernel32!GetProcessHeap` at `0x1800d4eb6`
- `kernel32!GetProcessHeap` at `0x1800d4ed5`
- `kernel32!GetProcessHeap` at `0x1800d471f`
- `kernel32!GetProcessHeap` at `0x1800d4744`
- `kernel32!GetProcessHeap` at `0x1800d4769`
- `kernel32!GetProcessHeap` at `0x1800d478e`
- `kernel32!GetProcessHeap` at `0x1800d47b1`
- `kernel32!GetProcessHeap` at `0x1800d47d0`
- `kernel32!GetProcessHeap` at `0x1800d47ef`
- `kernel32!GetProcessHeap` at `0x1800d4a6c`
- `kernel32!GetProcessHeap` at `0x1800d4dff`
- `kernel32!GetProcessHeap` at `0x1800d4e24`
- `kernel32!GetProcessHeap` at `0x1800d4e49`
- `kernel32!GetProcessHeap` at `0x1800d4e6e`
- `kernel32!GetProcessHeap` at `0x1800d4e93`
- `kernel32!GetProcessHeap` at `0x1800d4eb6`
- `kernel32!GetProcessHeap` at `0x1800d4ed5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall shaping_cache::get_glyph_placements(
        unsigned __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int *a12,
        int a13,
        char a14,
        char a15,
        __int16 a16,
        char a17,
        __int64 a18,
        LPVOID a19,
        __int64 a20,
        void *a21,
        void *a22,
        __int64 a23,
        unsigned __int64 a24,
        __int64 a25,
        unsigned __int64 a26,
        char *a27,
        unsigned __int64 a28,
        char *a29,
        unsigned __int64 a30)
{
  __m128i v31; // xmm0
  __m128i v32; // xmm1
  __m128i v33; // xmm7
  unsigned int v34; // xmm6_4
  unsigned int v35; // xmm5_4
  __m128i v36; // xmm2
  unsigned int v37; // xmm4_4
  __m128i v38; // xmm3
  __int64 v39; // r13
  __int64 v40; // r14
  int v41; // r15d
  int open_type_language_tag; // ebx
  int v43; // eax
  unsigned __int64 v44; // r12
  LPVOID v45; // rdi
  __int64 v46; // rax
  int v47; // esi
  __int64 v48; // rcx
  __int64 (__fastcall *v49)(unsigned __int64); // rax
  __int64 v50; // rax
  unsigned __int64 v51; // rdx
  __int64 v52; // rdx
  int v53; // r8d
  int v54; // esi
  __int64 v55; // r9
  unsigned __int64 v56; // r8
  volatile signed __int64 *v57; // rcx
  __int64 v58; // rbx
  __int64 v59; // rsi
  __int64 v60; // rdi
  unsigned __int64 v61; // r15
  char *v62; // r13
  _DWORD *v63; // rcx
  unsigned __int64 v64; // r15
  char *v65; // r12
  _DWORD *v66; // rcx
  void *v67; // r14
  HANDLE v68; // rax
  void *v69; // r14
  HANDLE v70; // rax
  void *v71; // r14
  HANDLE v72; // rax
  void *v73; // r14
  HANDLE v74; // rax
  void *v75; // r14
  HANDLE v76; // rax
  void *v77; // r14
  HANDLE v78; // rax
  void *v79; // r14
  HANDLE v80; // rax
  __int64 v82; // rsi
  unsigned __int64 v83; // rbx
  __int64 v84; // rdi
  unsigned __int64 v85; // r13
  unsigned __int64 v86; // rbx
  int glyph_positions; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int8 v89; // r11
  unsigned __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rax
  unsigned __int64 v93; // r8
  unsigned __int64 v94; // rdx
  unsigned __int64 v95; // rax
  unsigned __int64 v96; // r9
  unsigned __int64 v97; // rcx
  int v98; // r10d
  unsigned __int64 v99; // rdx
  unsigned __int64 v100; // rax
  unsigned __int64 v101; // r9
  unsigned __int64 v102; // rcx
  int v103; // r10d
  unsigned __int64 v104; // rdx
  unsigned __int64 v105; // r9
  unsigned __int64 v106; // r10
  unsigned __int64 v107; // rax
  unsigned __int64 v108; // r10
  __int64 v109; // r8
  unsigned __int64 v110; // r9
  unsigned __int64 v111; // rbx
  unsigned __int64 v112; // rcx
  __int64 v113; // rdi
  int v114; // r8d
  int v115; // r14d
  int v116; // r15d
  void *v117; // rsi
  __m128i v118; // xmm0
  HANDLE v119; // rax
  void *v120; // r14
  HANDLE v121; // rax
  void *v122; // r14
  HANDLE v123; // rax
  void *v124; // r14
  HANDLE v125; // rax
  void *v126; // r14
  HANDLE v127; // rax
  void *v128; // r14
  HANDLE v129; // rax
  void *v130; // r14
  HANDLE v131; // rax
  float v132; // xmm0_4
  unsigned __int64 v133; // rdx
  float *v134; // rcx
  unsigned __int64 v135; // rdx
  unsigned __int64 v136; // r8
  __m128 v137; // xmm1
  __int64 v138; // r9
  __m128 v139; // xmm3
  float v140; // xmm0_4
  unsigned __int64 v141; // rax
  char *v142; // rcx
  unsigned __int64 v143; // rax
  unsigned __int64 v144; // rdx
  __m128 v145; // xmm1
  __int64 v146; // r8
  __m128 v147; // xmm3
  float v148; // xmm2_4
  char *v149; // rsi
  bool v150; // di
  bool v151; // r14
  bool v152; // r11
  bool v153; // si
  __int64 v154; // r11
  __int64 v155; // r10
  char *v156; // rdi
  __m128i v157; // xmm3
  __m128i v158; // xmm1
  __m128i v159; // xmm2
  __m128i v160; // xmm1
  __m128i v161; // xmm3
  __m128i v162; // xmm2
  __m128i v163; // xmm1
  __m128i v164; // xmm2
  __int64 v165; // rcx
  int v166; // [rsp+38h] [rbp-48h]
  __int64 v167; // [rsp+40h] [rbp-40h]
  int v168; // [rsp+40h] [rbp-40h]
  __m128i v169; // [rsp+58h] [rbp-28h]
  __int64 Src; // [rsp+98h] [rbp+18h] BYREF
  LPVOID v171; // [rsp+A0h] [rbp+20h]
  __int64 v172; // [rsp+B0h] [rbp+30h]
  LPVOID v173; // [rsp+B8h] [rbp+38h]
  __int64 v174; // [rsp+C0h] [rbp+40h]
  __int64 v175; // [rsp+C8h] [rbp+48h]
  LPVOID v176; // [rsp+D0h] [rbp+50h]
  __int64 v177; // [rsp+E8h] [rbp+68h]
  __int64 v178; // [rsp+F0h] [rbp+70h]
  unsigned int v179; // [rsp+23Ch] [rbp+1BCh]
  __int64 v180; // [rsp+240h] [rbp+1C0h]
  int v181; // [rsp+248h] [rbp+1C8h] BYREF
  _DWORD v182[11]; // [rsp+24Ch] [rbp+1CCh] BYREF
  volatile signed __int64 *v183; // [rsp+278h] [rbp+1F8h]
  __int64 v184; // [rsp+280h] [rbp+200h]
  float v185; // [rsp+294h] [rbp+214h]
  _BYTE v186[280]; // [rsp+298h] [rbp+218h] BYREF
  _QWORD *v187; // [rsp+3B0h] [rbp+330h]
  unsigned __int8 v188; // [rsp+3C3h] [rbp+343h]
  int v189; // [rsp+3E8h] [rbp+368h]
  int v190; // [rsp+3ECh] [rbp+36Ch]
  __int64 v191; // [rsp+3F0h] [rbp+370h]
  __int64 v192; // [rsp+3F8h] [rbp+378h]
  __int64 v193; // [rsp+400h] [rbp+380h]
  LPVOID v194; // [rsp+408h] [rbp+388h]
  __int64 v195; // [rsp+410h] [rbp+390h]
  __int64 v196; // [rsp+418h] [rbp+398h]
  __int64 v197; // [rsp+420h] [rbp+3A0h]
  _QWORD v198[6]; // [rsp+428h] [rbp+3A8h] BYREF
  __int64 v199; // [rsp+458h] [rbp+3D8h] BYREF
  LPVOID v200; // [rsp+460h] [rbp+3E0h]
  unsigned __int64 v201; // [rsp+468h] [rbp+3E8h]
  __int64 v202; // [rsp+470h] [rbp+3F0h] BYREF
  LPVOID v203; // [rsp+478h] [rbp+3F8h]
  void *v204; // [rsp+480h] [rbp+400h]
  unsigned __int64 v205; // [rsp+488h] [rbp+408h] BYREF
  LPVOID v206; // [rsp+490h] [rbp+410h]
  LPVOID v207; // [rsp+498h] [rbp+418h]
  _DWORD v208[4]; // [rsp+4A0h] [rbp+420h] BYREF
  int v209; // [rsp+4B0h] [rbp+430h]
  char v210; // [rsp+4B4h] [rbp+434h]
  int v211; // [rsp+4B5h] [rbp+435h]
  __int16 v212; // [rsp+4B9h] [rbp+439h]
  bool v213; // [rsp+4BBh] [rbp+43Bh]
  char v214; // [rsp+4BCh] [rbp+43Ch]
  __int64 v215; // [rsp+4C0h] [rbp+440h] BYREF
  LPVOID lpMem[2]; // [rsp+4C8h] [rbp+448h] BYREF
  __int64 v217; // [rsp+4D8h] [rbp+458h] BYREF
  LPVOID v218[2]; // [rsp+4E0h] [rbp+460h] BYREF
  unsigned __int64 v219; // [rsp+4F0h] [rbp+470h] BYREF
  unsigned __int64 v220; // [rsp+4F8h] [rbp+478h] BYREF
  __int64 v221; // [rsp+500h] [rbp+480h]
  __int64 v222; // [rsp+508h] [rbp+488h] BYREF
  __int64 v223; // [rsp+510h] [rbp+490h]
  unsigned __int64 v224; // [rsp+518h] [rbp+498h]
  unsigned __int64 v225; // [rsp+520h] [rbp+4A0h] BYREF
  LPVOID v226; // [rsp+528h] [rbp+4A8h]
  unsigned __int64 v227; // [rsp+530h] [rbp+4B0h]
  volatile signed __int64 *v228; // [rsp+538h] [rbp+4B8h]
  unsigned __int8 v229; // [rsp+547h] [rbp+4C7h]
  __int64 v230; // [rsp+548h] [rbp+4C8h]

  v230 = -2;
  v31 = _mm_cvtsi32_si128(a11);
  v32 = _mm_cvtsi32_si128(a10);
  if ( a12 )
  {
    v33 = _mm_cvtsi32_si128(*a12);
    v34 = a12[1];
    v35 = a12[2];
    v36 = _mm_cvtsi32_si128(a12[3]);
    v37 = a12[4];
    v38 = _mm_cvtsi32_si128(a12[5]);
  }
  else
  {
    v36 = _mm_cvtsi32_si128(LODWORD(FLOAT_1_0));
    v38 = 0;
    v37 = 0;
    v35 = 0;
    v34 = 0;
    v33 = v36;
  }
  LOWORD(v181) = a16;
  BYTE2(v181) = a17;
  HIBYTE(v181) = a14;
  v182[0] = a13;
  v182[1] = _mm_cvtsi128_si32(v32);
  v182[2] = _mm_cvtsi128_si32(v31);
  v182[3] = _mm_cvtsi128_si32(v33);
  v182[4] = v34;
  v182[5] = v35;
  v182[6] = _mm_cvtsi128_si32(v36);
  v182[7] = v37;
  v182[8] = _mm_cvtsi128_si32(v38);
  shaping_cache::context::ShapingContext::new((__int64)&Src, a1, a3, (__int16 *)&v181, 0, a2);
  LODWORD(v39) = Src;
  v40 = v179;
  if ( v179 == 136 )
    return (unsigned int)v39;
  memcpy_0(v182, (char *)&Src + 4, 0x1A0u);
  v181 = v39;
  v190 = v40;
  v191 = v180;
  v41 = v189;
  open_type_language_tag = langtag::get_open_type_language_tag(a18);
  if ( (_DWORD)v40 == 1 )
    v41 = 0;
  v43 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v187 + 88LL))(*v187);
  v208[1] = v40;
  v208[2] = v41;
  v208[3] = open_type_language_tag;
  v208[0] = 2 * v188;
  v209 = (v43 << 30 >> 31) & 0x5700;
  v210 = a15;
  v211 = 0;
  v212 = 0;
  v213 = v190 != 26;
  v214 = 1;
  v225 = a24;
  v205 = a26;
  if ( a26 != a24 )
  {
    Src = 0;
    core::panicking::assert_failed_usize_usize_(&v205, &v225, &Src, &off_180340778);
  }
  v44 = a26;
  v220 = a30;
  if ( a30 != a26 )
  {
    Src = 0;
    core::panicking::assert_failed_usize_usize_(&v220, &v225, &Src, &off_180340790);
  }
  v219 = a28;
  if ( a28 != a26 )
  {
    Src = 0;
    core::panicking::assert_failed_usize_usize_(&v219, &v225, &Src, &off_1803407A8);
  }
  v39 = 0xFFFFFFFFLL;
  if ( a26 > 0xFFFF )
    goto LABEL_68;
  v226 = a22;
  if ( a20 != 0 && a22 == 0 )
    core::panicking::panic(
      "assertion failed: !range_lens.is_empty()rust\\shaping\\src\\get_glyphs.rs",
      40,
      &off_1803407C0);
  shaping::string::ShapingString::new(&Src, a4, a5);
  v227 = 0;
  v45 = 0;
  if ( !__OFSUB__(-Src, 1) )
    v45 = v173;
  v194 = v45;
  v195 = v174;
  v196 = v178;
  v197 = v177;
  v192 = a6;
  v193 = a7;
  v198[2] = v45;
  v198[3] = v174;
  v198[4] = v178;
  v198[5] = v177;
  v198[0] = a8;
  v198[1] = a9;
  v202 = 0;
  v203 = (LPVOID)4;
  v204 = 0;
  v199 = 0;
  v200 = (LPVOID)8;
  v201 = 0;
  if ( a20 )
  {
    shaping::string::remap_run_properties(&v222, &Src, a21, a22, a19, a20, &v202, &v199);
    if ( (v222 & 1) != 0 )
    {
      LODWORD(v39) = HIDWORD(v222);
      goto LABEL_57;
    }
    v206 = v203;
    v226 = v204;
    v207 = v200;
    v227 = v201;
  }
  else
  {
    v207 = a19;
    v206 = a21;
  }
  v46 = (unsigned int)(32 * v40);
  v47 = *((unsigned __int8 *)&off_180341570 + v46 + 24);
  if ( *((_BYTE *)&off_180341570 + v46 + 24) )
  {
    shaping::caching::CacheSlot_shaping::caching::CommonFontCacheData_::init_shaping::caching::CommonFontCacheData_(
      &v222,
      &v181,
      shaping_cache::context::impl_2::get_cache_slot);
    if ( !v222 )
    {
      LODWORD(v39) = v223;
      goto LABEL_57;
    }
    v48 = *(_QWORD *)(v223 + 16);
    v221 = v223;
    v49 = *(__int64 (__fastcall **)(unsigned __int64))(v223 + 24);
    v228 = (volatile signed __int64 *)v222;
    v50 = v49(v222 + ((v48 - 1) & 0xFFFFFFFFFFFFFFF0uLL) + 16);
    if ( (v50 & 3) != 0 )
    {
      v165 = 0;
    }
    else
    {
      if ( v51 > 0xBB )
      {
        v52 = (unsigned int)v40 >> 4;
        v53 = 3 << (2 * v40);
        v54 = v47 - 1;
        switch ( v54 )
        {
          case 0:
            v55 = 4;
            goto LABEL_33;
          case 1:
            goto LABEL_32;
          case 2:
            v55 = 68;
            v57 = v228;
            if ( (v53 & *(_DWORD *)(v50 + 4 * v52 + 4)) != 0 )
              goto LABEL_34;
            LOBYTE(v54) = 1;
            break;
          case 3:
            if ( (v53 & *(_DWORD *)(v50 + 4 * v52 + 4)) != 0 )
            {
              v54 = 0;
              v57 = v228;
            }
            else
            {
LABEL_32:
              v55 = 68;
LABEL_33:
              v57 = v228;
LABEL_34:
              LOBYTE(v54) = (v53 & *(_DWORD *)(v55 + v50 + 4 * v52)) == 0;
            }
            break;
        }
        if ( !_InterlockedDecrement64(v57) )
          JUMPOUT(0x1800D4519LL);
        v56 = v220;
        if ( v220 )
          goto LABEL_38;
        goto LABEL_39;
      }
      v165 = 1;
    }
    v222 = v165;
    v223 = v50;
    v224 = v51;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&v222,
      (unsigned int)&qword_18033B688,
      (__int64)&off_18033B840);
  }
  v54 = 0;
  v56 = a26;
  if ( a26 )
LABEL_38:
    memset_0(a29, 0, 8 * v56);
LABEL_39:
  v217 = 0;
  v218[0] = (LPVOID)4;
  v218[1] = 0;
  v215 = 0;
  lpMem[0] = (LPVOID)4;
  lpMem[1] = 0;
  LODWORD(v228) = v208[0];
  LODWORD(v221) = v54;
  if ( v208[0] != 2 )
  {
    v58 = a26;
    v59 = 0;
    v60 = 0;
    goto LABEL_52;
  }
  v61 = v225;
  if ( v225 )
  {
    alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2((unsigned int)&v217, 0, v225, 4, 4);
    v60 = (__int64)v218[0];
    v62 = (char *)v218[1];
    v63 = (char *)v218[0] + 4 * (__int64)v218[1];
    if ( v61 != 1 )
    {
      memset_0(v63, 0, 4 * v61 - 4);
      v63 = (_DWORD *)(v60 + 4LL * (_QWORD)&v62[v61] - 4);
      v62 = &v62[v61 - 1];
    }
    *v63 = 0;
    v39 = (__int64)(v62 + 1);
    v64 = v225;
    v218[1] = (LPVOID)v39;
    if ( v225 )
    {
      alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2((unsigned int)&v215, 0, v225, 4, 4);
      v58 = a26;
      v59 = (__int64)lpMem[0];
      v65 = (char *)lpMem[1];
      v66 = (char *)lpMem[0] + 4 * (__int64)lpMem[1];
      if ( v64 != 1 )
      {
        memset_0(v66, 0, 4 * v64 - 4);
        v66 = (_DWORD *)(v59 + 4LL * (_QWORD)&v65[v64] - 4);
        v65 = &v65[v64 - 1];
      }
      *v66 = 0;
      v44 = (unsigned __int64)(v65 + 1);
      goto LABEL_51;
    }
    v58 = a26;
    v59 = 4;
  }
  else
  {
    v58 = a26;
    v218[1] = 0;
    v59 = 4;
    v39 = 0;
    v60 = 4;
  }
  v44 = 0;
LABEL_51:
  lpMem[1] = (LPVOID)v44;
LABEL_52:
  v167 = v44;
  v44 = v58;
  LODWORD(v39) = shaping_cache::context::impl_2::get_glyph_default_advance_widths(
                   (unsigned int)&v181,
                   a23,
                   v58,
                   (_DWORD)a27,
                   v58,
                   v60,
                   v39,
                   v59,
                   v167);
  if ( !(_DWORD)v39 )
  {
    v222 = 0;
    v223 = 4;
    v224 = 0;
    v229 = v210;
    if ( v210 )
    {
      if ( (_DWORD)v228 != 2 && HIBYTE(v212) )
      {
        v82 = a23;
        v83 = 0;
        v84 = 4;
        goto LABEL_81;
      }
    }
    else if ( (_DWORD)v228 != 2 )
    {
      v82 = a23;
      v84 = 4;
      v83 = 0;
      goto LABEL_81;
    }
    v85 = v219;
    if ( v219 )
    {
      alloc::raw_vec::impl_4::reserve::do_reserve_and_handle_alloc::alloc::Global__2((unsigned int)&v222, 0, v219, 4, 4);
      v84 = v223;
      v86 = v224;
    }
    else
    {
      v84 = 4;
      v86 = 0;
    }
    v82 = a23;
    memcpy_0((void *)(v84 + 4 * v86), a27, 4 * v85);
    v83 = v85 + v86;
    v224 = v83;
LABEL_81:
    if ( (_BYTE)v221 )
      glyph_positions = shaping::engine::generic::get_glyph_positions(
                          (unsigned int)&v181,
                          (unsigned int)&off_180343070,
                          (unsigned int)v208,
                          (_DWORD)v206,
                          (__int64)v226,
                          (__int64)v207,
                          v227,
                          v166,
                          v168,
                          (__int64)v198,
                          v82,
                          v44,
                          a25,
                          v44,
                          (__int64)a27,
                          v44,
                          (__int64)a29,
                          v44);
    else
      glyph_positions = _guard_dispatch_icall_fptr();
    LODWORD(v39) = glyph_positions;
    if ( glyph_positions )
    {
      if ( v222 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)v84);
      }
      goto LABEL_53;
    }
    v227 = v83;
    v226 = (LPVOID)v84;
    v89 = v229;
    if ( !byte_1803B4C57[v40] )
    {
      v93 = v225;
      if ( v229 )
      {
        if ( !v225 )
          goto LABEL_139;
        v94 = v205;
        v95 = v219;
        v96 = v220;
        v97 = 0;
        v89 = v229;
        do
        {
          if ( v97 >= v94 )
            core::panicking::panic_bounds_check(v97, v94, &off_180340850);
          if ( (*(_BYTE *)(a25 + 2 * v97) & 0x40) != 0 )
          {
            if ( v97 >= v95 )
              core::panicking::panic_bounds_check(v97, v95, &off_180340868);
            if ( v97 >= v96 )
              core::panicking::panic_bounds_check(v97, v96, &off_180340880);
            v98 = *(_DWORD *)&a27[4 * v97];
            *(_DWORD *)&a29[8 * v97] -= v98;
            *(_DWORD *)&a27[4 * v97++] = 0;
            if ( v97 < v93 )
            {
              while ( 1 )
              {
                if ( v94 == v97 )
                  core::panicking::panic_bounds_check(v94, v94, &off_180340898);
                if ( (*(_BYTE *)(a25 + 2 * v97) & 0x40) == 0 )
                  break;
                if ( v95 == v97 )
                  core::panicking::panic_bounds_check(v95, v95, &off_1803408B0);
                if ( v96 == v97 )
                  core::panicking::panic_bounds_check(v96, v96, &off_1803408C8);
                v98 += *(_DWORD *)&a27[4 * v97];
                *(_DWORD *)&a29[8 * v97] -= v98;
                *(_DWORD *)&a27[4 * v97++] = 0;
                if ( v93 == v97 )
                {
                  v97 = v93;
                  break;
                }
              }
            }
          }
          ++v97;
        }
        while ( v97 < v93 );
      }
      else
      {
        if ( !v225 )
          goto LABEL_139;
        v99 = v205;
        v100 = v219;
        v101 = v220;
        v102 = 0;
        v89 = v229;
        do
        {
          if ( v102 >= v99 )
            core::panicking::panic_bounds_check(v102, v99, &off_1803407D8);
          if ( (*(_BYTE *)(a25 + 2 * v102) & 0x40) != 0 )
          {
            if ( v102 >= v100 )
              core::panicking::panic_bounds_check(v102, v100, &off_1803407F0);
            v103 = *(_DWORD *)&a27[4 * v102];
            *(_DWORD *)&a27[4 * v102++] = 0;
            if ( v102 < v93 )
            {
              while ( 1 )
              {
                if ( v99 == v102 )
                  core::panicking::panic_bounds_check(v99, v99, &off_180340808);
                if ( (*(_BYTE *)(a25 + 2 * v102) & 0x40) == 0 )
                  break;
                if ( v102 >= v101 )
                  core::panicking::panic_bounds_check(v102, v101, &off_180340820);
                *(_DWORD *)&a29[8 * v102] += v103;
                if ( v100 == v102 )
                  core::panicking::panic_bounds_check(v100, v100, &off_180340838);
                v103 += *(_DWORD *)&a27[4 * v102];
                *(_DWORD *)&a27[4 * v102++] = 0;
                if ( v93 == v102 )
                {
                  v102 = v93;
                  break;
                }
              }
            }
          }
          ++v102;
        }
        while ( v102 < v93 );
      }
    }
    if ( v89 )
    {
      v90 = v225;
      if ( HIBYTE(v212) )
      {
        if ( v225 > v44 )
          core::slice::index::slice_end_index_len_fail(v225, v44, &off_180340928);
        if ( v225 )
        {
          v91 = 8 * v225;
          v92 = 0;
          do
          {
            *(_DWORD *)&a29[v92] = -*(_DWORD *)&a29[v92];
            v92 += 8;
          }
          while ( v91 != v92 );
        }
      }
      else if ( v225 )
      {
        v104 = v219;
        v105 = v225 - 1;
        v106 = v219;
        if ( v225 - 1 < v219 )
          v106 = v225 - 1;
        if ( v106 >= v227 )
          v106 = v227;
        v107 = v220;
        if ( v106 >= v220 )
          v106 = v220;
        v108 = v106 + 1;
        v109 = 1;
        if ( v108 > 0x14 )
        {
          if ( v105 >= v219 )
            v105 = v219;
          if ( v105 >= v227 )
            v105 = v227;
          if ( v105 >= v220 )
            v105 = v220;
          v149 = &a29[8 * v105 + 4];
          v150 = a29 < (char *)v226 + 4 * v105 + 4;
          v151 = v226 < v149;
          v152 = a29 < &a27[4 * v105 + 4];
          v153 = a27 < v149;
          v110 = 0;
          if ( v151 && v150 )
          {
            v111 = v227;
          }
          else
          {
            v111 = v227;
            if ( !v153 || !v152 )
            {
              v154 = 4;
              if ( (v108 & 3) != 0 )
                v154 = v108 & 3;
              v110 = v108 - v154;
              v109 = v108 - v154 + 1;
              v155 = 0;
              v156 = (char *)v226;
              do
              {
                v157 = (__m128i)_mm_shuffle_ps(*(__m128 *)&a29[8 * v155], *(__m128 *)&a29[8 * v155 + 16], 136);
                v158 = _mm_sub_epi32((__m128i)0LL, v157);
                *(_DWORD *)&a29[8 * v155] = _mm_cvtsi128_si32(v158);
                *(_DWORD *)&a29[8 * v155 + 8] = _mm_cvtsi128_si32(_mm_shuffle_epi32(v158, 85));
                *(_DWORD *)&a29[8 * v155 + 16] = _mm_cvtsi128_si32(_mm_shuffle_epi32(v158, 238));
                *(_DWORD *)&a29[8 * v155 + 24] = _mm_cvtsi128_si32(_mm_shuffle_epi32(v158, 255));
                v159 = _mm_loadu_si128((const __m128i *)&v156[4 * v155]);
                v160 = _mm_loadu_si128((const __m128i *)&a27[4 * v155]);
                v161 = _mm_add_epi32(v157, v159);
                v162 = _mm_cmpeq_epi32(v159, v160);
                v163 = _mm_sub_epi32(v160, v161);
                if ( (~_mm_cvtsi128_si32(v162) & 1) != 0 )
                  *(_DWORD *)&a29[8 * v155] = _mm_cvtsi128_si32(v163);
                v164 = _mm_xor_si128(v162, (__m128i)-1LL);
                if ( (_mm_extract_epi16(v164, 2) & 1) != 0 )
                  *(_DWORD *)&a29[8 * v155 + 8] = _mm_cvtsi128_si32(_mm_shuffle_epi32(v163, 85));
                if ( (_mm_extract_epi16(v164, 4) & 1) != 0 )
                  *(_DWORD *)&a29[8 * v155 + 16] = _mm_cvtsi128_si32(_mm_shuffle_epi32(v163, 238));
                if ( (_mm_extract_epi16(v164, 6) & 1) != 0 )
                  *(_DWORD *)&a29[8 * v155 + 24] = _mm_cvtsi128_si32(_mm_shuffle_epi32(v163, 255));
                v155 += 4;
              }
              while ( v110 != v155 );
            }
          }
        }
        else
        {
          v110 = 0;
          v111 = v227;
        }
        v112 = v90 + 1;
        do
        {
          v113 = v109;
          if ( !(v109 + ~v107) )
            core::panicking::panic_bounds_check(v110, v107, &off_1803408E0);
          v114 = *(_DWORD *)&a29[8 * v110];
          *(_DWORD *)&a29[8 * v110] = -v114;
          if ( !(~v111 + v113) )
            core::panicking::panic_bounds_check(v110, v227, &off_1803408F8);
          if ( !(v113 + ~v104) )
            core::panicking::panic_bounds_check(v110, v104, &off_180340910);
          v115 = *((_DWORD *)v226 + v110);
          v116 = *(_DWORD *)&a27[4 * v110];
          if ( v115 != v116 )
            *(_DWORD *)&a29[8 * v110] = v116 - (v114 + v115);
          v109 = v113 + 1;
          v110 = v113;
        }
        while ( v112 != v113 + 1 );
      }
    }
LABEL_139:
    v117 = v226;
    if ( (_DWORD)v228 == 2 )
    {
      v118 = _mm_loadu_si128((const __m128i *)v218);
      v169 = _mm_loadu_si128((const __m128i *)lpMem);
      shaping::get_glyph_positions::rotate_glyph_clusters_sideways(
        v229,
        a5,
        v225,
        a6,
        a7,
        (__int64)a27,
        v44,
        (__int64)v226,
        v227,
        v118.m128i_i64[0],
        v118.m128i_i64[1],
        v169.m128i_i64[0],
        v169.m128i_i64[1],
        (__int64)a29,
        v44,
        v209);
    }
    if ( v222 )
    {
      v119 = GetProcessHeap();
      HeapFree(v119, 0, v117);
    }
    if ( v215 )
    {
      v120 = lpMem[0];
      v121 = GetProcessHeap();
      HeapFree(v121, 0, v120);
    }
    if ( v217 )
    {
      v122 = v218[0];
      v123 = GetProcessHeap();
      HeapFree(v123, 0, v122);
    }
    if ( v199 )
    {
      v124 = v200;
      v125 = GetProcessHeap();
      HeapFree(v125, 0, v124);
    }
    if ( v202 )
    {
      v126 = v203;
      v127 = GetProcessHeap();
      HeapFree(v127, 0, v126);
    }
    if ( __OFSUB__(-Src, 1) )
      goto LABEL_157;
    if ( Src )
    {
      v128 = v171;
      v129 = GetProcessHeap();
      HeapFree(v129, 0, v128);
    }
    if ( v172 )
    {
      v130 = v173;
      v131 = GetProcessHeap();
      HeapFree(v131, 0, v130);
    }
    LODWORD(v39) = 0;
    if ( !v175 )
      goto LABEL_157;
    goto LABEL_67;
  }
LABEL_53:
  if ( v215 )
  {
    v67 = lpMem[0];
    v68 = GetProcessHeap();
    HeapFree(v68, 0, v67);
  }
  if ( v217 )
  {
    v69 = v218[0];
    v70 = GetProcessHeap();
    HeapFree(v70, 0, v69);
  }
LABEL_57:
  if ( v199 )
  {
    v71 = v200;
    v72 = GetProcessHeap();
    HeapFree(v72, 0, v71);
  }
  if ( v202 )
  {
    v73 = v203;
    v74 = GetProcessHeap();
    HeapFree(v74, 0, v73);
  }
  if ( __OFSUB__(-Src, 1) )
    goto LABEL_68;
  if ( Src )
  {
    v75 = v171;
    v76 = GetProcessHeap();
    HeapFree(v76, 0, v75);
  }
  if ( v172 )
  {
    v77 = v173;
    v78 = GetProcessHeap();
    HeapFree(v78, 0, v77);
  }
  if ( !v175 )
    goto LABEL_68;
LABEL_67:
  v79 = v176;
  v80 = GetProcessHeap();
  HeapFree(v80, 0, v79);
  if ( (_DWORD)v39 )
  {
LABEL_68:
    if ( !_InterlockedDecrement64(v183) )
      alloc::sync::Arc_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_::drop_slow_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_(
        v183,
        v184);
    core::ptr::drop_in_place_shaping_cache::context::FontTables_(v186);
    return (unsigned int)v39;
  }
LABEL_157:
  if ( v44 )
  {
    v132 = v185;
    v133 = (v44 - 1) & 0x3FFFFFFFFFFFFFFFLL;
    v134 = (float *)a27;
    if ( v133 < 7 )
      goto LABEL_217;
    v135 = v133 + 1;
    v136 = v135 & 0xFFFFFFFFFFFFFFF8uLL;
    v134 = (float *)&a27[4 * (v135 & 0xFFFFFFFFFFFFFFF8uLL)];
    v137 = _mm_shuffle_ps((__m128)LODWORD(v185), (__m128)LODWORD(v185), 0);
    v138 = 0;
    do
    {
      v139 = _mm_mul_ps(_mm_cvtepi32_ps(*(__m128i *)&a27[4 * v138 + 16]), v137);
      *(__m128 *)&a27[4 * v138] = _mm_mul_ps(_mm_cvtepi32_ps(*(__m128i *)&a27[4 * v138]), v137);
      *(__m128 *)&a27[4 * v138 + 16] = v139;
      v138 += 8;
    }
    while ( v136 != v138 );
    if ( v135 != v136 )
    {
LABEL_217:
      do
      {
        *v134 = (float)*(int *)v134 * v132;
        ++v134;
      }
      while ( v134 != (float *)&a27[4 * v44] );
    }
    v140 = v185;
    v141 = (v44 - 1) & 0x1FFFFFFFFFFFFFFFLL;
    v142 = a29;
    if ( v141 < 3 )
      goto LABEL_218;
    v143 = v141 + 1;
    v144 = v143 & 0xFFFFFFFFFFFFFFFCuLL;
    v142 = &a29[8 * (v143 & 0xFFFFFFFFFFFFFFFCuLL)];
    v145 = _mm_shuffle_ps((__m128)LODWORD(v185), (__m128)LODWORD(v185), 0);
    v146 = 0;
    do
    {
      v147 = _mm_mul_ps(_mm_cvtepi32_ps(*(__m128i *)&a29[8 * v146 + 16]), v145);
      *(__m128 *)&a29[8 * v146] = _mm_mul_ps(_mm_cvtepi32_ps(*(__m128i *)&a29[8 * v146]), v145);
      *(__m128 *)&a29[8 * v146 + 16] = v147;
      v146 += 4;
    }
    while ( v144 != v146 );
    if ( v143 != v144 )
    {
LABEL_218:
      do
      {
        v148 = (float)*((int *)v142 + 1) * v140;
        *(float *)v142 = (float)*(int *)v142 * v140;
        *((float *)v142 + 1) = v148;
        v142 += 8;
      }
      while ( v142 != &a29[8 * v44] );
    }
  }
  if ( !_InterlockedDecrement64(v183) )
    alloc::sync::Arc_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_::drop_slow_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_(
      v183,
      v184);
  core::ptr::drop_in_place_shaping_cache::context::FontTables_(v186);
  LODWORD(v39) = 0;
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x1800d3fc0  push    rbp
0x1800d3fc1  push    r15
0x1800d3fc3  push    r14
0x1800d3fc5  push    r13
0x1800d3fc7  push    r12
0x1800d3fc9  push    rsi
0x1800d3fca  push    rdi
0x1800d3fcb  push    rbx
0x1800d3fcc  sub     rsp, 578h
0x1800d3fd3  lea     rbp, [rsp+80h]
0x1800d3fdb  movaps  [rbp+530h+var_50], xmm7
0x1800d3fe2  movaps  [rbp+530h+var_60], xmm6
0x1800d3fe9  mov     [rbp+530h+var_68], 0FFFFFFFFFFFFFFFEh
0x1800d3ff4  mov     rdi, r9
0x1800d3ff7  mov     rax, rcx
0x1800d3ffa  movzx   r10d, [rbp+530h+arg_78]
0x1800d4002  movzx   r9d, [rbp+530h+arg_68]
0x1800d400a  mov     ecx, [rbp+530h+arg_60]
0x1800d4010  mov     rsi, [rbp+530h+arg_58]
0x1800d4017  movd    xmm0, [rbp+530h+arg_50]
0x1800d401f  movd    xmm1, [rbp+530h+arg_48]
0x1800d4027  movzx   r11d, [rbp+530h+arg_80]
0x1800d402f  test    rsi, rsi
0x1800d4032  jz      short loc_1800D4053
0x1800d4034  movd    xmm7, dword ptr [rsi]
0x1800d4038  movss   xmm6, dword ptr [rsi+4]
0x1800d403d  movss   xmm5, dword ptr [rsi+8]
0x1800d4042  movd    xmm2, dword ptr [rsi+0Ch]
0x1800d4047  movss   xmm4, dword ptr [rsi+10h]
0x1800d404c  movd    xmm3, dword ptr [rsi+14h]
0x1800d4051  jmp     short loc_1800D406C
0x1800d4053  movd    xmm2, cs:__real@3f800000
0x1800d405b  pxor    xmm3, xmm3
0x1800d405f  xorps   xmm4, xmm4
0x1800d4062  xorps   xmm5, xmm5
0x1800d4065  xorps   xmm6, xmm6
0x1800d4068  movdqa  xmm7, xmm2
0x1800d406c  mov     word ptr [rbp+530h+var_368], r10w
0x1800d4074  mov     byte ptr [rbp+530h+var_368+2], r11b
0x1800d407b  mov     byte ptr [rbp+530h+var_368+3], r9b
0x1800d4082  mov     [rbp+530h+var_364], ecx
0x1800d4088  movd    [rbp+530h+var_360], xmm1
0x1800d4090  movd    [rbp+530h+var_35C], xmm0
0x1800d4098  movd    [rbp+530h+var_358], xmm7
0x1800d40a0  movss   [rbp+530h+var_354], xmm6
0x1800d40a8  movss   [rbp+530h+var_350], xmm5
0x1800d40b0  movd    [rbp+530h+var_34C], xmm2
0x1800d40b8  movss   [rbp+530h+var_348], xmm4
0x1800d40c0  movd    [rbp+530h+var_344], xmm3
0x1800d40c8  mov     [rsp+5B0h+var_588], rdx
0x1800d40cd  mov     [rsp+5B0h+var_590], 0
0x1800d40d6  lea     rcx, [rbp+530h+Src]
0x1800d40da  lea     r9, [rbp+530h+var_368]
0x1800d40e1  mov     rdx, rax
0x1800d40e4  call    shaping_cache__context__ShapingContext__new
0x1800d40e9  mov     r13d, dword ptr [rbp+530h+Src]
0x1800d40ed  mov     r14d, [rbp+530h+var_374]
0x1800d40f4  cmp     r14, 88h
0x1800d40fb  jz      loc_1800D4838
0x1800d4101  mov     rsi, [rbp+530h+arg_88]
0x1800d4108  lea     rdx, [rbp+530h+Src+4]; Src
0x1800d410c  lea     rcx, [rbp+530h+var_364]; void *
0x1800d4113  mov     r8d, 1A0h; Size
0x1800d4119  call    memcpy_0
0x1800d411e  mov     rax, [rbp+530h+var_370]
0x1800d4125  mov     [rbp+530h+var_368], r13d
0x1800d412c  mov     [rbp+530h+var_1C4], r14d
0x1800d4133  mov     [rbp+530h+var_1C0], rax
0x1800d413a  mov     r15d, [rbp+530h+var_1C8]
0x1800d4141  mov     rcx, rsi
0x1800d4144  call    langtag__get_open_type_language_tag
0x1800d4149  mov     ebx, eax
0x1800d414b  mov     r13, [rbp+530h+arg_C8]
0x1800d4152  mov     rsi, [rbp+530h+arg_B8]
0x1800d4159  movzx   r12d, [rbp+530h+arg_70]
0x1800d4161  xor     eax, eax
0x1800d4163  cmp     r14d, 1
0x1800d4167  cmovz   r15d, eax
0x1800d416b  mov     rax, [rbp+530h+var_200]
0x1800d4172  mov     rcx, [rax]
0x1800d4175  mov     rax, [rcx]
0x1800d4178  mov     rax, [rax+58h]
0x1800d417c  call    cs:__guard_dispatch_icall_fptr
0x1800d4182  shl     eax, 1Eh
0x1800d4185  sar     eax, 1Fh
0x1800d4188  and     eax, 5700h
0x1800d418d  movzx   ecx, [rbp+530h+var_1ED]
0x1800d4194  add     ecx, ecx
0x1800d4196  cmp     [rbp+530h+var_1C4], 1Ah
0x1800d419d  mov     [rbp+530h+var_10C], r14d
0x1800d41a4  mov     [rbp+530h+var_108], r15d
0x1800d41ab  mov     [rbp+530h+var_104], ebx
0x1800d41b1  mov     [rbp+530h+var_110], ecx
0x1800d41b7  mov     [rbp+530h+var_100], eax
0x1800d41bd  mov     [rbp+530h+var_FC], r12b
0x1800d41c4  mov     [rbp+530h+var_FB], 0
0x1800d41ce  mov     [rbp+530h+var_F7], 0
0x1800d41d7  setnz   [rbp+530h+var_F5]
0x1800d41de  mov     [rbp+530h+var_F4], 1
0x1800d41e5  mov     [rbp+530h+var_90], rsi
0x1800d41ec  mov     [rbp+530h+var_128], r13
0x1800d41f3  cmp     r13, rsi
0x1800d41f6  jnz     loc_1800D520C
0x1800d41fc  mov     r12, r13
0x1800d41ff  mov     rax, [rbp+530h+arg_E8]
0x1800d4206  mov     [rbp+530h+var_B8], rax
0x1800d420d  cmp     rax, r13
0x1800d4210  jnz     loc_1800D5237
0x1800d4216  mov     rax, [rbp+530h+arg_D8]
0x1800d421d  mov     [rbp+530h+var_C0], rax
0x1800d4224  cmp     rax, r12
0x1800d4227  jnz     loc_1800D5262
0x1800d422d  mov     r13d, 0FFFFFFFFh
0x1800d4233  cmp     r12, 0FFFFh
0x1800d423a  ja      loc_1800D480C
0x1800d4240  mov     rcx, [rbp+530h+arg_A8]
0x1800d4247  mov     rsi, [rbp+530h+arg_98]
0x1800d424e  test    rsi, rsi
0x1800d4251  setz    al
0x1800d4254  mov     [rbp+530h+var_88], rcx
0x1800d425b  test    rcx, rcx
0x1800d425e  setnz   cl
0x1800d4261  or      cl, al
0x1800d4263  jz      loc_1800D528D
0x1800d4269  mov     r8, [rbp+530h+arg_20]
0x1800d4270  lea     rcx, [rbp+530h+Src]
0x1800d4274  mov     rdx, rdi
0x1800d4277  call    shaping__string__ShapingString__new
0x1800d427c  mov     rax, [rbp+530h+arg_40]
0x1800d4283  mov     rcx, [rbp+530h+arg_38]
0x1800d428a  mov     r8, [rbp+530h+Src]
0x1800d428e  mov     rdx, [rbp+530h+var_4F0]
0x1800d4292  mov     [rbp+530h+var_80], 0
0x1800d429d  neg     r8
0x1800d42a0  mov     edi, 0
0x1800d42a5  jo      short loc_1800D42AB
0x1800d42a7  mov     rdi, [rbp+530h+var_4F8]
0x1800d42ab  mov     r8, [rbp+530h+arg_A0]
0x1800d42b2  mov     rbx, [rbp+530h+arg_90]
0x1800d42b9  mov     r9, [rbp+530h+var_4C0]
0x1800d42bd  mov     r10, [rbp+530h+var_4C8]
0x1800d42c1  mov     [rbp+530h+var_1A8], rdi
0x1800d42c8  mov     [rbp+530h+var_1A0], rdx
0x1800d42cf  mov     [rbp+530h+var_198], r9
0x1800d42d6  mov     [rbp+530h+var_190], r10
0x1800d42dd  mov     r11, [rbp+530h+arg_28]
0x1800d42e4  mov     [rbp+530h+var_1B8], r11
0x1800d42eb  mov     r11, [rbp+530h+arg_30]
0x1800d42f2  mov     [rbp+530h+var_1B0], r11
0x1800d42f9  mov     [rbp+530h+var_178], rdi
0x1800d4300  mov     [rbp+530h+var_170], rdx
0x1800d4307  mov     [rbp+530h+var_168], r9
0x1800d430e  mov     [rbp+530h+var_160], r10
0x1800d4315  mov     [rbp+530h+var_188], rcx
0x1800d431c  mov     [rbp+530h+var_180], rax
0x1800d4323  mov     [rbp+530h+var_140], 0
0x1800d432e  mov     [rbp+530h+var_138], 4
0x1800d4339  mov     [rbp+530h+var_130], 0
0x1800d4344  mov     [rbp+530h+var_158], 0
0x1800d434f  mov     [rbp+530h+var_150], 8
0x1800d435a  mov     [rbp+530h+var_148], 0
0x1800d4365  test    rsi, rsi
0x1800d4368  jz      short loc_1800D43B8
0x1800d436a  lea     rax, [rbp+530h+var_158]
0x1800d4371  mov     [rsp+5B0h+var_578], rax
0x1800d4376  lea     rax, [rbp+530h+var_140]
0x1800d437d  mov     [rsp+5B0h+var_580], rax
0x1800d4382  mov     [rsp+5B0h+var_588], rsi
0x1800d4387  mov     [rsp+5B0h+var_590], rbx
0x1800d438c  lea     rcx, [rbp+530h+var_A8]
0x1800d4393  lea     rdx, [rbp+530h+Src]
0x1800d4397  mov     r9, [rbp+530h+arg_A8]
0x1800d439e  call    shaping__string__remap_run_properties
0x1800d43a3  test    byte ptr [rbp+530h+var_A8], 1
0x1800d43aa  jz      short loc_1800D43C8
0x1800d43ac  mov     r13d, dword ptr [rbp+530h+var_A8+4]
0x1800d43b3  jmp     loc_1800D4758
0x1800d43b8  mov     [rbp+530h+var_118], rbx
0x1800d43bf  mov     [rbp+530h+var_120], r8
0x1800d43c6  jmp     short loc_1800D4400
0x1800d43c8  mov     rax, [rbp+530h+var_138]
0x1800d43cf  mov     [rbp+530h+var_120], rax
0x1800d43d6  mov     rax, [rbp+530h+var_130]
0x1800d43dd  mov     [rbp+530h+var_88], rax
0x1800d43e4  mov     rax, [rbp+530h+var_150]
0x1800d43eb  mov     [rbp+530h+var_118], rax
0x1800d43f2  mov     rax, [rbp+530h+var_148]
0x1800d43f9  mov     [rbp+530h+var_80], rax
0x1800d4400  mov     eax, r14d
0x1800d4403  shl     eax, 5
0x1800d4406  lea     rcx, off_180341570
0x1800d440d  movzx   esi, byte ptr [rax+rcx+18h]
0x1800d4412  test    esi, esi
0x1800d4414  jz      loc_1800D44B8
0x1800d441a  lea     r8, shaping_cache__context__impl$2__get_cache_slot
0x1800d4421  lea     rcx, [rbp+530h+var_A8]
0x1800d4428  lea     rdx, [rbp+530h+var_368]
0x1800d442f  call    shaping__caching__CacheSlot_shaping__caching__CommonFontCacheData___init_shaping__caching__CommonFontCacheData_
0x1800d4434  mov     rdx, [rbp+530h+var_A8]
0x1800d443b  test    rdx, rdx
0x1800d443e  jz      loc_1800D44C4
0x1800d4444  mov     rax, [rbp+530h+var_A0]
0x1800d444b  mov     rcx, [rax+10h]
0x1800d444f  mov     [rbp+530h+var_B0], rax
0x1800d4456  mov     rax, [rax+18h]
0x1800d445a  dec     rcx
0x1800d445d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800d4461  mov     [rbp+530h+var_78], rdx
0x1800d4468  add     rcx, rdx
0x1800d446b  add     rcx, 10h
0x1800d446f  call    cs:__guard_dispatch_icall_fptr
0x1800d4475  test    al, 3
0x1800d4477  jnz     loc_1800D53D7
0x1800d447d  cmp     rdx, 0BBh
0x1800d4484  jbe     loc_1800D53DB
0x1800d448a  lea     ecx, [r14+r14]
0x1800d448e  mov     edx, r14d
0x1800d4491  shr     edx, 4
0x1800d4494  mov     r8d, 3
0x1800d449a  shl     r8d, cl
0x1800d449d  dec     esi
0x1800d449f  lea     rcx, jpt_1800D44AD
0x1800d44a6  movsxd  r9, ds:(jpt_1800D44AD - 180407318h)[rcx+rsi*4]; switch 4 cases
0x1800d44aa  add     r9, rcx
0x1800d44ad  jmp     r9; switch jump
0x1800d44b0  mov     r9d, 4; jumptable 00000001800D44AD case 0
0x1800d44b6  jmp     short loc_1800D4501
0x1800d44b8  xor     esi, esi
0x1800d44ba  mov     r8, r12
0x1800d44bd  test    r8, r8
0x1800d44c0  jnz     short loc_1800D4531
0x1800d44c2  jmp     short loc_1800D4543
0x1800d44c4  mov     r13d, dword ptr [rbp+530h+var_A0]
0x1800d44cb  jmp     loc_1800D4758
0x1800d44d0  mov     r9d, 44h ; 'D'; jumptable 00000001800D44AD case 2
0x1800d44d6  test    [rax+rdx*4+4], r8d
0x1800d44db  mov     rcx, [rbp+530h+var_78]
0x1800d44e2  jnz     short loc_1800D4508
0x1800d44e4  mov     sil, 1
0x1800d44e7  jmp     short loc_1800D4513
0x1800d44e9  test    [rax+rdx*4+4], r8d; jumptable 00000001800D44AD case 3
0x1800d44ee  jz      short loc_1800D44FB; jumptable 00000001800D44AD case 1
0x1800d44f0  xor     esi, esi
0x1800d44f2  mov     rcx, [rbp+530h+var_78]
0x1800d44f9  jmp     short loc_1800D4513
0x1800d44fb  mov     r9d, 44h ; 'D'; jumptable 00000001800D44AD case 1
0x1800d4501  mov     rcx, [rbp+530h+var_78]
0x1800d4508  add     rax, r9
0x1800d450b  test    [rax+rdx*4], r8d
0x1800d450f  setz    sil
0x1800d4513  lock dec qword ptr [rcx]
0x1800d4517  jnz     short loc_1800D4525
0x1800d451a  mov     edx, dword ptr [rbp+530h+var_B0]
0x1800d4520  call    alloc__sync__Arc_dyn$_otls__client__TableData_assoc$_Target_slice2$_u8________alloc__alloc__Global___drop_slow_dyn$_otls__client__TableData_assoc$_Target_slice2$_u8________alloc__alloc__Global_
0x1800d4525  mov     r8, [rbp+530h+var_B8]
0x1800d452c  test    r8, r8
0x1800d452f  jz      short loc_1800D4543
0x1800d4531  shl     r8, 3; Size
0x1800d4535  mov     rcx, [rbp+530h+arg_E0]; void *
0x1800d453c  xor     edx, edx; Val
0x1800d453e  call    memset_0
0x1800d4543  mov     [rbp+530h+var_D8], 0
0x1800d454e  mov     [rbp+530h+var_D0], 4
0x1800d4559  mov     [rbp+530h+var_D0+8], 0
0x1800d4564  mov     [rbp+530h+var_F0], 0
0x1800d456f  mov     [rbp+530h+lpMem], 4
0x1800d457a  mov     [rbp+530h+lpMem+8], 0
0x1800d4585  mov     eax, [rbp+530h+var_110]
0x1800d458b  mov     dword ptr [rbp+530h+var_78], eax
0x1800d4591  cmp     eax, 2
0x1800d4594  mov     dword ptr [rbp+530h+var_B0], esi
0x1800d459a  jz      short loc_1800D45A8
0x1800d459c  mov     rbx, r12
0x1800d459f  xor     esi, esi
0x1800d45a1  xor     edi, edi
0x1800d45a3  jmp     loc_1800D46C7
0x1800d45a8  mov     r15, [rbp+530h+var_90]
0x1800d45af  test    r15, r15
0x1800d45b2  jz      loc_1800D4698
0x1800d45b8  mov     [rsp+5B0h+var_590], 4
0x1800d45c1  lea     rcx, [rbp+530h+var_D8]
0x1800d45c8  mov     r9d, 4
0x1800d45ce  xor     edx, edx
0x1800d45d0  mov     r8, r15
0x1800d45d3  call    alloc__raw_vec__impl$4__reserve__do_reserve_and_handle_alloc__alloc__Global__2
0x1800d45d8  mov     rdi, [rbp+530h+var_D0]
0x1800d45df  mov     r13, [rbp+530h+var_D0+8]
0x1800d45e6  lea     rcx, [rdi+r13*4]; void *
0x1800d45ea  cmp     r15, 1
0x1800d45ee  jz      short loc_1800D4611
0x1800d45f0  lea     r8, ds:0FFFFFFFFFFFFFFFCh[r15*4]; Size
0x1800d45f8  xor     edx, edx; Val
0x1800d45fa  call    memset_0
0x1800d45ff  lea     rax, [r15+r13]
0x1800d4603  lea     rcx, [rdi+rax*4]
0x1800d4607  add     rcx, 0FFFFFFFFFFFFFFFCh
0x1800d460b  add     r13, r15
0x1800d460e  dec     r13
0x1800d4611  mov     dword ptr [rcx], 0
0x1800d4617  inc     r13
  ... truncated ...
```
