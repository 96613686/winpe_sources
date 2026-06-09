# shaping_cache::get_glyphs

- ea: `0x1800cff10`
- end: `0x1800d0b2d`
- name: `shaping_cache::get_glyphs`
- size: `3101`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, char, char, __int16, char, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, void *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004a40`
- `0x18005a9a0`
- `0x18005ed20`

## callees

- `0x180043730`
- `0x180065ec0`
- `0x18008cb70`
- `0x18008d2d0`
- `0x1800a0390`
- `0x1800ce7d0`
- `0x1800cff10`
- `0x1800d0c60`
- `0x1800d3d40`
- `0x180212f4c`
- `0x18021e1b6`
- `0x180316190`
- `0x1803168c1`
- `0x180316a30`
- `0x180316ce0`
- `0x180316ee0`
- `0x18031716c`

## import_xrefs

- `kernel32!HeapFree` at `0x1800d037c`
- `kernel32!HeapFree` at `0x1800d03a1`
- `kernel32!HeapFree` at `0x1800d03ca`
- `kernel32!HeapFree` at `0x1800d03ef`
- `kernel32!HeapFree` at `0x1800d0414`
- `kernel32!HeapFree` at `0x1800d037c`
- `kernel32!HeapFree` at `0x1800d03a1`
- `kernel32!HeapFree` at `0x1800d03ca`
- `kernel32!HeapFree` at `0x1800d03ef`
- `kernel32!HeapFree` at `0x1800d0414`
- `kernel32!GetProcessHeap` at `0x1800d036e`
- `kernel32!GetProcessHeap` at `0x1800d0393`
- `kernel32!GetProcessHeap` at `0x1800d03bc`
- `kernel32!GetProcessHeap` at `0x1800d03e1`
- `kernel32!GetProcessHeap` at `0x1800d0406`
- `kernel32!GetProcessHeap` at `0x1800d036e`
- `kernel32!GetProcessHeap` at `0x1800d0393`
- `kernel32!GetProcessHeap` at `0x1800d03bc`
- `kernel32!GetProcessHeap` at `0x1800d03e1`
- `kernel32!GetProcessHeap` at `0x1800d0406`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall shaping_cache::get_glyphs(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        char a8,
        char a9,
        __int16 a10,
        char a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        char *a15,
        __int64 a16,
        unsigned __int64 a17,
        __int64 a18,
        __int64 a19,
        char *a20,
        __int64 a21)
{
  __int64 result; // rax
  int v23; // r14d
  unsigned int v24; // ebx
  int v25; // r12d
  int open_type_language_tag; // edi
  int v27; // eax
  unsigned __int64 v28; // r12
  int *v29; // rdx
  int v30; // eax
  unsigned int v31; // r15d
  __int64 v32; // rcx
  __int64 (__fastcall *v33)(char *); // rax
  __int64 v34; // rax
  unsigned __int64 v35; // rdx
  void *v36; // rsi
  HANDLE v37; // rax
  void *v38; // rsi
  HANDLE v39; // rax
  void *v40; // rsi
  HANDLE ProcessHeap; // rax
  void *v42; // rsi
  HANDLE v43; // rax
  void *v44; // rsi
  HANDLE v45; // rax
  volatile signed __int64 *v46; // rcx
  int *v47; // r10
  unsigned __int64 v48; // r11
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rdi
  char *v51; // rbx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // rcx
  __m128i si128; // xmm0
  unsigned __int64 v55; // r9
  __int64 v56; // r14
  unsigned __int64 v57; // r12
  unsigned __int64 v58; // r9
  unsigned __int64 v59; // r15
  unsigned __int64 v60; // r13
  unsigned __int64 v61; // r13
  __int64 v62; // r8
  unsigned __int64 v63; // r13
  char *v64; // r8
  __int64 v65; // r15
  __m128i v66; // xmm2
  int *v67; // r11
  unsigned __int64 v68; // r15
  unsigned __int64 v69; // rax
  __int64 v70; // rbx
  unsigned __int64 v71; // rdx
  unsigned __int64 v72; // r13
  char *v73; // r14
  __int64 v74; // r8
  unsigned __int64 v75; // rcx
  unsigned __int64 v76; // r9
  unsigned __int64 v77; // r10
  unsigned __int64 v78; // r8
  unsigned int v79; // r10d
  __int64 v80; // r15
  unsigned __int64 v82; // r10
  __int64 v83; // r12
  unsigned __int64 v84; // r10
  __int64 v85; // r9
  _WORD *v86; // r9
  __int64 v87; // r12
  unsigned __int64 v88; // r8
  _WORD *v89; // r12
  __int64 v90; // rdi
  unsigned __int64 v91; // r8
  __m128i v92; // xmm0
  __int64 v93; // r12
  __int64 v94; // r15
  unsigned __int64 v95; // r15
  unsigned __int64 v96; // xmm0_8
  bool v97; // zf
  unsigned __int64 v98; // rdx
  _WORD *v99; // rax
  unsigned __int64 v100; // r11
  char *v101; // r9
  unsigned __int64 v102; // rdi
  unsigned __int64 v103; // r10
  unsigned __int64 v104; // r8
  unsigned __int64 v105; // rcx
  unsigned __int64 v106; // rcx
  __int64 v107; // rcx
  int v108; // [rsp+88h] [rbp+8h] BYREF
  int v109; // [rsp+8Ch] [rbp+Ch] BYREF
  __int128 v110; // [rsp+90h] [rbp+10h]
  __m128i v111; // [rsp+A0h] [rbp+20h]
  volatile signed __int64 *v112; // [rsp+B8h] [rbp+38h]
  __int64 v113; // [rsp+C0h] [rbp+40h]
  char v114[280]; // [rsp+D8h] [rbp+58h] BYREF
  _QWORD *v115; // [rsp+1F0h] [rbp+170h]
  unsigned __int8 v116; // [rsp+203h] [rbp+183h]
  int v117; // [rsp+228h] [rbp+1A8h]
  unsigned int v118; // [rsp+22Ch] [rbp+1ACh]
  __int64 v119; // [rsp+230h] [rbp+1B0h]
  _QWORD Src[4]; // [rsp+238h] [rbp+1B8h] BYREF
  LPVOID v121; // [rsp+258h] [rbp+1D8h]
  unsigned __int64 v122; // [rsp+260h] [rbp+1E0h]
  __int64 v123; // [rsp+268h] [rbp+1E8h]
  LPVOID v124; // [rsp+270h] [rbp+1F0h]
  __int64 v125; // [rsp+288h] [rbp+208h]
  unsigned __int64 v126; // [rsp+290h] [rbp+210h]
  unsigned int v127; // [rsp+3DCh] [rbp+35Ch]
  __int64 v128; // [rsp+3E0h] [rbp+360h]
  char *v129; // [rsp+3E8h] [rbp+368h]
  __int64 v130; // [rsp+3F0h] [rbp+370h]
  int *v131; // [rsp+3F8h] [rbp+378h]
  unsigned __int64 v132; // [rsp+400h] [rbp+380h]
  unsigned __int64 v133; // [rsp+408h] [rbp+388h]
  __int64 v134; // [rsp+410h] [rbp+390h]
  __int64 v135; // [rsp+418h] [rbp+398h] BYREF
  __int64 v136; // [rsp+420h] [rbp+3A0h] BYREF
  __int64 v137; // [rsp+428h] [rbp+3A8h]
  __int64 v138; // [rsp+430h] [rbp+3B0h]
  __int64 v139; // [rsp+438h] [rbp+3B8h]
  int *v140; // [rsp+440h] [rbp+3C0h]
  unsigned __int64 v141; // [rsp+448h] [rbp+3C8h]
  unsigned __int64 v142; // [rsp+450h] [rbp+3D0h]
  __int64 v143; // [rsp+458h] [rbp+3D8h]
  int v144; // [rsp+460h] [rbp+3E0h]
  unsigned int v145; // [rsp+464h] [rbp+3E4h]
  int v146; // [rsp+468h] [rbp+3E8h]
  int v147; // [rsp+46Ch] [rbp+3ECh]
  int v148; // [rsp+470h] [rbp+3F0h]
  char v149; // [rsp+474h] [rbp+3F4h]
  int v150; // [rsp+475h] [rbp+3F5h]
  __int16 v151; // [rsp+479h] [rbp+3F9h]
  bool v152; // [rsp+47Bh] [rbp+3FBh]
  char v153; // [rsp+47Ch] [rbp+3FCh]
  __int64 v154; // [rsp+480h] [rbp+400h] BYREF
  LPVOID lpMem; // [rsp+488h] [rbp+408h]
  __int64 v156; // [rsp+490h] [rbp+410h]
  __int64 v157; // [rsp+498h] [rbp+418h] BYREF
  LPVOID v158; // [rsp+4A0h] [rbp+420h]
  __int64 v159; // [rsp+4A8h] [rbp+428h]
  char *v160; // [rsp+4B0h] [rbp+430h]
  volatile signed __int64 *v161; // [rsp+4B8h] [rbp+438h]
  _QWORD *v162; // [rsp+4C0h] [rbp+440h]
  volatile signed __int64 *v163; // [rsp+4C8h] [rbp+448h] BYREF
  _QWORD *v164; // [rsp+4D0h] [rbp+450h]
  unsigned __int64 v165; // [rsp+4D8h] [rbp+458h]
  unsigned __int64 v166; // [rsp+4E0h] [rbp+460h]
  char *v167; // [rsp+4E8h] [rbp+468h]
  __int64 v168; // [rsp+4F0h] [rbp+470h]

  v168 = -2;
  LOWORD(v108) = a10;
  BYTE2(v108) = a11;
  HIBYTE(v108) = a8;
  v109 = 0;
  v110 = _xmm;
  v111 = _mm_loadl_epi64((const __m128i *)&_xmm);
  result = shaping_cache::context::ShapingContext::new((__int64)Src, a2, a4, (__int16 *)&v108, a5, a3);
  v23 = Src[0];
  v24 = v127;
  if ( v127 == 136 )
  {
    *(_DWORD *)(a1 + 4) = Src[0];
    *(_DWORD *)a1 = 1;
    return result;
  }
  memcpy_0(&v109, (char *)Src + 4, 0x1A0u);
  v108 = v23;
  v118 = v24;
  v119 = v128;
  v25 = v117;
  open_type_language_tag = langtag::get_open_type_language_tag(a12);
  if ( v24 == 1 )
    v25 = 0;
  v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v115 + 88LL))(*v115);
  v145 = v24;
  v146 = v25;
  v147 = open_type_language_tag;
  v144 = 2 * v116;
  v148 = (v27 << 30 >> 31) & 0x5700;
  v149 = a9;
  v150 = 0;
  v151 = 0;
  v152 = v118 != 26;
  v153 = 1;
  v136 = a14;
  v135 = a16;
  if ( a14 != a16 )
  {
    Src[0] = 0;
    core::panicking::assert_failed_usize_usize_(&v136, &v135, Src, &off_180340940);
  }
  if ( a7 )
  {
    shaping::string::ShapingString::new(Src, a6, a7);
    v28 = v126;
    if ( v126 > a17 )
    {
      *(_QWORD *)a1 = 0xFFFFFFFE00000001uLL;
LABEL_31:
      if ( !__OFSUB__(-Src[0], 1) )
      {
        if ( Src[0] )
        {
          v40 = (void *)Src[1];
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v40);
        }
        if ( Src[3] )
        {
          v42 = v121;
          v43 = GetProcessHeap();
          HeapFree(v43, 0, v42);
        }
        if ( v123 )
        {
          v44 = v124;
          v45 = GetProcessHeap();
          HeapFree(v45, 0, v44);
        }
      }
      goto LABEL_38;
    }
    if ( a21 )
      memset_0(a20, 0, 2 * a21);
    v29 = 0;
    if ( !__OFSUB__(0, Src[0]) )
      v29 = (int *)v121;
    v140 = v29;
    v141 = v122;
    v142 = v28;
    v143 = v125;
    v138 = a18;
    v139 = a19;
    v131 = v29;
    v132 = v122;
    v133 = v28;
    v134 = v125;
    v129 = a20;
    v130 = a21;
    v157 = 0;
    v158 = (LPVOID)4;
    v159 = 0;
    v154 = 0;
    lpMem = (LPVOID)8;
    v156 = 0;
    if ( a14 )
    {
      shaping::string::remap_run_properties(&v163, Src, a15, a14, a13, a14, &v157, &v154);
      if ( ((unsigned __int8)v163 & 1) != 0 )
      {
        v30 = HIDWORD(v163);
LABEL_26:
        *(_DWORD *)(a1 + 4) = v30;
        *(_DWORD *)a1 = 1;
LABEL_27:
        if ( v154 )
        {
          v36 = lpMem;
          v37 = GetProcessHeap();
          HeapFree(v37, 0, v36);
        }
        if ( v157 )
        {
          v38 = v158;
          v39 = GetProcessHeap();
          HeapFree(v39, 0, v38);
        }
        goto LABEL_31;
      }
      v167 = (char *)v158;
    }
    else
    {
      v167 = a15;
    }
    v31 = v145;
    shaping::caching::CacheSlot_shaping::caching::CommonFontCacheData_::init_shaping::caching::CommonFontCacheData_(
      &v163,
      &v108,
      shaping_cache::context::impl_2::get_cache_slot);
    if ( !v163 )
    {
      v30 = (int)v164;
      goto LABEL_26;
    }
    v32 = v164[2];
    v162 = v164;
    v33 = (__int64 (__fastcall *)(char *))v164[3];
    v161 = v163;
    v34 = v33((char *)v163 + ((v32 - 1) & 0xFFFFFFFFFFFFFFF0uLL) + 16);
    if ( (v34 & 3) != 0 )
    {
      v107 = 0;
    }
    else
    {
      if ( v35 > 0xBB )
      {
        if ( !*(_BYTE *)(v34 + 163) || ((3 << (2 * v31)) & *(_DWORD *)(v34 + 4LL * (v31 >> 4) + 4)) != 0 )
        {
          switch ( *((_BYTE *)&off_180341570 + 32 * v31 + 24) )
          {
            case 0:
            case 1:
            case 2:
            case 3:
            case 4:
              break;
          }
        }
        _guard_dispatch_icall_fptr();
        if ( ((unsigned __int8)v163 & 1) != 0 )
        {
          *(_DWORD *)(a1 + 4) = HIDWORD(v163);
          *(_DWORD *)a1 = 1;
          v46 = v161;
          if ( _InterlockedDecrement64(v161) )
            goto LABEL_27;
LABEL_44:
          alloc::sync::Arc_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_::drop_slow_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_(
            v46,
            v162);
          goto LABEL_27;
        }
        v167 = (char *)v164;
        v47 = v131;
        if ( v131 )
        {
          v48 = v133;
          if ( v133 )
          {
            v49 = v132;
            v50 = v133 - 1;
            v51 = v129;
            v52 = v130;
            v160 = v129 + 18;
            v53 = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm_fffefffefffefffefffefffefffefffe);
            do
            {
              if ( v53 == v49 )
                core::panicking::panic_bounds_check(v49, v49, &off_180341300);
              v55 = v53++;
              v56 = v47[v55];
              v57 = v52;
              if ( v55 < v50 )
              {
                if ( v53 >= v49 )
                  core::panicking::panic_bounds_check(v53, v49, &off_180341318);
                v57 = v47[v53];
              }
              v58 = v56 + 1;
              if ( v56 + 1 < v57 )
              {
                v59 = v56 + 1;
                if ( v52 > v58 )
                  v59 = v52;
                v60 = v57 - v56 - 2;
                if ( v59 + ~v56 < v60 )
                  v60 = v59 + ~v56;
                v61 = v60 + 1;
                if ( v61 > 0x10 )
                {
                  v62 = v61 & 0xF;
                  if ( (v61 & 0xF) == 0 )
                    v62 = 16;
                  v63 = v61 - v62;
                  v58 += v63;
                  v64 = &v160[2 * v56];
                  v65 = 0;
                  do
                  {
                    v66 = _mm_and_si128(_mm_loadu_si128((const __m128i *)&v64[2 * v65]), si128);
                    *(__m128i *)&v64[2 * v65 - 16] = _mm_and_si128(
                                                       _mm_loadu_si128((const __m128i *)&v64[2 * v65 - 16]),
                                                       si128);
                    *(__m128i *)&v64[2 * v65] = v66;
                    v65 += 16;
                  }
                  while ( v63 != v65 );
                }
                do
                {
                  if ( v58 >= v52 )
                    core::panicking::panic_bounds_check(v58, v52, &off_180341330);
                  v51[2 * v58++] &= ~1u;
                }
                while ( v57 != v58 );
              }
            }
            while ( v53 != v48 );
          }
        }
        v67 = v140;
        if ( v140 )
        {
          v68 = v142;
          if ( v142 )
          {
            v69 = v141;
            v70 = v138;
            v71 = v139;
            v72 = 0;
            v73 = v167 - 1;
            if ( !v167 )
              v73 = 0;
            v160 = (char *)(v142 - 1);
            v137 = v138 + 18;
            v74 = 1;
            v75 = 0;
            v166 = v142;
            do
            {
              v76 = v75;
              if ( v75 >= v69 )
                core::panicking::panic_bounds_check(v75, v69, &off_180341348);
              v77 = v67[v75];
              if ( v71 <= v77 )
                core::panicking::panic_bounds_check(v67[v75], v71, &off_180341360);
              v75 = v74;
              v78 = *(unsigned __int16 *)(v70 + 2 * v77);
              if ( (unsigned __int64)v167 <= v78 )
              {
                *(_WORD *)(v70 + 2 * v77) = (_WORD)v73;
                v78 = (unsigned __int64)v73;
              }
              if ( v76 )
              {
                if ( v72 <= v78 || (v79 = v67[v76] - 1, (v79 & 0x80000000) != 0) )
                {
                  v72 = v78;
                }
                else
                {
                  v80 = v79 + 1LL;
                  do
                  {
                    if ( v71 <= v79 )
                      core::panicking::panic_bounds_check(v79, v71, &off_180341390);
                    if ( v78 >= *(unsigned __int16 *)(v70 + 2 * v80 - 2) )
                      break;
                    *(_WORD *)(v70 + 2 * v80 - 2) = v78;
                  }
                  while ( v80-- > 1 );
                  v72 = v78;
                  v68 = v166;
                }
              }
              else
              {
                v82 = *v67;
                if ( v71 <= v82 )
                  core::panicking::panic_bounds_check(*v67, v71, &off_180341378);
                *(_WORD *)(v70 + 2 * v82) = 0;
                v72 = 0;
              }
              v83 = v67[v76];
              v84 = v71;
              if ( v76 < (unsigned __int64)v160 )
              {
                if ( v75 >= v69 )
                  core::panicking::panic_bounds_check(v75, v69, &off_1803413A8);
                v84 = v67[v75];
              }
              v85 = v83 + 1;
              if ( v84 < v83 + 1 )
                core::slice::index::slice_index_order_fail(v83 + 1, v84, &off_1803413C0);
              if ( v84 > v71 )
                core::slice::index::slice_end_index_len_fail(v84, v71, &off_1803413C0);
              if ( v85 == v84 )
                goto LABEL_71;
              v86 = (_WORD *)(v70 + 2 * v85);
              v87 = 2 * v83;
              v88 = 2 * v84 - v87 - 4;
              if ( v88 > 5 )
              {
                v90 = (v88 >> 1) + 1;
                if ( v88 < 0x1E )
                {
                  v91 = 0;
LABEL_101:
                  v95 = v90 & 0xFFFFFFFFFFFFFFFCuLL;
                  v89 = &v86[v90 & 0xFFFFFFFFFFFFFFFCuLL];
                  v96 = _mm_shufflelo_epi16(_mm_cvtsi32_si128(v72), 0).m128i_u64[0];
                  do
                  {
                    *(_QWORD *)&v86[v91] = v96;
                    v91 += 4LL;
                  }
                  while ( v95 != v91 );
                  v97 = v90 == v95;
                  v68 = v166;
                  if ( v97 )
                    goto LABEL_71;
                  goto LABEL_106;
                }
                v91 = v90 & 0xFFFFFFFFFFFFFFF0uLL;
                v92 = _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_cvtsi32_si128(v72), 0), 0);
                v93 = v137 + v87;
                v94 = 0;
                do
                {
                  *(__m128i *)(v93 + 2 * v94 - 16) = v92;
                  *(__m128i *)(v93 + 2 * v94) = v92;
                  v94 += 16;
                }
                while ( v91 != v94 );
                v68 = v166;
                if ( v90 == v91 )
                  goto LABEL_71;
                if ( (v90 & 0xC) != 0 )
                  goto LABEL_101;
                v89 = &v86[v91];
              }
              else
              {
                v89 = v86;
              }
              do
LABEL_106:
                *v89++ = v72;
              while ( v89 != (_WORD *)(v70 + 2 * v84) );
LABEL_71:
              v74 = v75 + 1;
            }
            while ( v75 != v68 );
          }
        }
        else
        {
          v98 = v139;
          if ( v139 )
          {
            v99 = (_WORD *)v138;
            v100 = 0;
            v101 = v167 - 1;
            if ( !v167 )
              v101 = 0;
            v102 = 1;
            v103 = 0;
            do
            {
              v105 = v103;
              v103 = v102;
              v104 = (unsigned __int16)v99[v105];
              if ( (unsigned __int64)v167 <= v104 )
              {
                v99[v105] = (_WORD)v101;
                v104 = (unsigned __int64)v101;
              }
              if ( v105 )
              {
                if ( v100 > v104 )
                {
                  v106 = v105 - 1;
                  do
                  {
                    if ( v106 >= v98 )
                      core::panicking::panic_bounds_check(v106, v98, &off_1803413D8);
                    if ( v99[v106] <= (unsigned __int16)v104 )
                      break;
                    v99[v106--] = v104;
                  }
                  while ( v106 );
                }
              }
              else
              {
                *v99 = 0;
                v104 = 0;
              }
              v102 += v102 < v98;
              v100 = v104;
            }
            while ( v103 < v98 );
          }
        }
        *(_QWORD *)(a1 + 8) = v167;
        *(_DWORD *)a1 = 0;
        v46 = v161;
        if ( _InterlockedDecrement64(v161) )
          goto LABEL_27;
        goto LABEL_44;
      }
      v107 = 1;
    }
    v163 = (volatile signed __int64 *)v107;
    v164 = (_QWORD *)v34;
    v165 = v35;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)&v163,
      (unsigned int)&qword_18033B688,
      (__int64)&off_18033B840);
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 0;
LABEL_38:
  if ( !_InterlockedDecrement64(v112) )
    alloc::sync::Arc_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_::drop_slow_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_(
      v112,
      v113);
  return core::ptr::drop_in_place_shaping_cache::context::FontTables_(v114);
}

```

## disassembly

```asm
0x1800cff10  push    rbp
0x1800cff11  push    r15
0x1800cff13  push    r14
0x1800cff15  push    r13
0x1800cff17  push    r12
0x1800cff19  push    rsi
0x1800cff1a  push    rdi
0x1800cff1b  push    rbx
0x1800cff1c  sub     rsp, 4F8h
0x1800cff23  lea     rbp, [rsp+80h]
0x1800cff2b  mov     [rbp+4B0h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800cff36  mov     rax, r9
0x1800cff39  mov     rsi, rcx
0x1800cff3c  mov     rcx, [rbp+4B0h+arg_20]
0x1800cff43  movzx   r9d, [rbp+4B0h+arg_38]
0x1800cff4b  movzx   r10d, [rbp+4B0h+arg_50]
0x1800cff53  movzx   r11d, [rbp+4B0h+arg_48]
0x1800cff5b  mov     word ptr [rbp+4B0h+var_4A8], r11w
0x1800cff60  mov     byte ptr [rbp+4B0h+var_4A8+2], r10b
0x1800cff64  mov     byte ptr [rbp+4B0h+var_4A8+3], r9b
0x1800cff68  mov     [rbp+4B0h+var_4A4], 0
0x1800cff6f  movaps  xmm0, cs:__xmm@000000003f8000003f80000041200000
0x1800cff76  movups  [rbp+4B0h+var_4A0], xmm0
0x1800cff7a  movq    xmm0, cs:__xmm@00000000000000003f80000000000000
0x1800cff82  movdqu  [rbp+4B0h+var_490], xmm0
0x1800cff87  mov     [rsp+530h+var_508], r8
0x1800cff8c  mov     [rsp+530h+var_510], rcx
0x1800cff91  lea     rcx, [rbp+4B0h+Src]
0x1800cff98  lea     r9, [rbp+4B0h+var_4A8]
0x1800cff9c  mov     r8, rax
0x1800cff9f  call    shaping_cache__context__ShapingContext__new
0x1800cffa4  mov     r14d, dword ptr [rbp+4B0h+Src]
0x1800cffab  mov     ebx, [rbp+4B0h+var_154]
0x1800cffb1  cmp     ebx, 88h
0x1800cffb7  jnz     short loc_1800CFFC8
0x1800cffb9  mov     [rsi+4], r14d
0x1800cffbd  mov     dword ptr [rsi], 1
0x1800cffc3  jmp     loc_1800D043A
0x1800cffc8  mov     rdi, [rbp+4B0h+arg_58]
0x1800cffcf  lea     rdx, [rbp+4B0h+Src+4]; Src
0x1800cffd6  lea     rcx, [rbp+4B0h+var_4A4]; void *
0x1800cffda  mov     r8d, 1A0h; Size
0x1800cffe0  call    memcpy_0
0x1800cffe5  mov     rax, [rbp+4B0h+var_150]
0x1800cffec  mov     [rbp+4B0h+var_4A8], r14d
0x1800cfff0  mov     [rbp+4B0h+var_304], ebx
0x1800cfff6  mov     [rbp+4B0h+var_300], rax
0x1800cfffd  mov     r12d, [rbp+4B0h+var_308]
0x1800d0004  mov     rcx, rdi
0x1800d0007  call    langtag__get_open_type_language_tag
0x1800d000c  mov     edi, eax
0x1800d000e  mov     r15, [rbp+4B0h+arg_78]
0x1800d0015  mov     r14, [rbp+4B0h+arg_68]
0x1800d001c  movzx   r13d, [rbp+4B0h+arg_40]
0x1800d0024  xor     eax, eax
0x1800d0026  cmp     ebx, 1
0x1800d0029  cmovz   r12d, eax
0x1800d002d  mov     rax, [rbp+4B0h+var_340]
0x1800d0034  mov     rcx, [rax]
0x1800d0037  mov     rax, [rcx]
0x1800d003a  mov     rax, [rax+58h]
0x1800d003e  call    cs:__guard_dispatch_icall_fptr
0x1800d0044  shl     eax, 1Eh
0x1800d0047  sar     eax, 1Fh
0x1800d004a  and     eax, 5700h
0x1800d004f  movzx   ecx, [rbp+4B0h+var_32D]
0x1800d0056  add     ecx, ecx
0x1800d0058  cmp     [rbp+4B0h+var_304], 1Ah
0x1800d005f  mov     [rbp+4B0h+var_CC], ebx
0x1800d0065  mov     [rbp+4B0h+var_C8], r12d
0x1800d006c  mov     [rbp+4B0h+var_C4], edi
0x1800d0072  mov     [rbp+4B0h+var_D0], ecx
0x1800d0078  mov     [rbp+4B0h+var_C0], eax
0x1800d007e  mov     [rbp+4B0h+var_BC], r13b
0x1800d0085  mov     [rbp+4B0h+var_BB], 0
0x1800d008f  mov     [rbp+4B0h+var_B7], 0
0x1800d0098  setnz   [rbp+4B0h+var_B5]
0x1800d009f  mov     [rbp+4B0h+var_B4], 1
0x1800d00a6  mov     [rbp+4B0h+var_110], r14
0x1800d00ad  mov     [rbp+4B0h+var_118], r15
0x1800d00b4  cmp     r14, r15
0x1800d00b7  jnz     loc_1800D09DE
0x1800d00bd  mov     r8, [rbp+4B0h+arg_30]
0x1800d00c4  test    r8, r8
0x1800d00c7  jz      short loc_1800D00FE
0x1800d00c9  mov     rdx, [rbp+4B0h+arg_28]
0x1800d00d0  lea     rcx, [rbp+4B0h+Src]
0x1800d00d7  call    shaping__string__ShapingString__new
0x1800d00dc  mov     r12, [rbp+4B0h+var_2A0]
0x1800d00e3  cmp     r12, [rbp+4B0h+arg_80]
0x1800d00ea  jbe     short loc_1800D0111
0x1800d00ec  mov     rax, 0FFFFFFFE00000001h
0x1800d00f6  mov     [rsi], rax
0x1800d00f9  jmp     loc_1800D03A7
0x1800d00fe  mov     qword ptr [rsi+8], 0
0x1800d0106  mov     dword ptr [rsi], 0
0x1800d010c  jmp     loc_1800D041A
0x1800d0111  mov     rbx, [rbp+4B0h+arg_A0]
0x1800d0118  mov     r15, [rbp+4B0h+arg_98]
0x1800d011f  test    rbx, rbx
0x1800d0122  jz      short loc_1800D0132
0x1800d0124  lea     r8, [rbx+rbx]; Size
0x1800d0128  mov     rcx, r15; void *
0x1800d012b  xor     edx, edx; Val
0x1800d012d  call    memset_0
0x1800d0132  mov     rax, [rbp+4B0h+arg_90]
0x1800d0139  mov     rcx, [rbp+4B0h+arg_88]
0x1800d0140  xor     edi, edi
0x1800d0142  cmp     rdi, [rbp+4B0h+Src]
0x1800d0149  mov     edx, 0
0x1800d014e  jo      short loc_1800D0157
0x1800d0150  mov     rdx, [rbp+4B0h+var_2D8]
0x1800d0157  mov     r8, [rbp+4B0h+arg_70]
0x1800d015e  mov     r13, [rbp+4B0h+arg_60]
0x1800d0165  mov     r10, [rbp+4B0h+var_2D0]
0x1800d016c  mov     r9, [rbp+4B0h+var_2A8]
0x1800d0173  mov     [rbp+4B0h+var_F0], rdx
0x1800d017a  mov     [rbp+4B0h+var_E8], r10
0x1800d0181  mov     [rbp+4B0h+var_E0], r12
0x1800d0188  mov     [rbp+4B0h+var_D8], r9
0x1800d018f  mov     [rbp+4B0h+var_100], rcx
0x1800d0196  mov     [rbp+4B0h+var_F8], rax
0x1800d019d  mov     [rbp+4B0h+var_138], rdx
0x1800d01a4  mov     [rbp+4B0h+var_130], r10
0x1800d01ab  mov     [rbp+4B0h+var_128], r12
0x1800d01b2  mov     [rbp+4B0h+var_120], r9
0x1800d01b9  mov     [rbp+4B0h+var_148], r15
0x1800d01c0  mov     [rbp+4B0h+var_140], rbx
0x1800d01c7  mov     [rbp+4B0h+var_98], 0
0x1800d01d2  mov     [rbp+4B0h+var_90], 4
0x1800d01dd  mov     [rbp+4B0h+var_88], 0
0x1800d01e8  mov     [rbp+4B0h+var_B0], 0
0x1800d01f3  mov     [rbp+4B0h+lpMem], 8
0x1800d01fe  mov     [rbp+4B0h+var_A0], 0
0x1800d0209  test    r14, r14
0x1800d020c  jz      short loc_1800D025A
0x1800d020e  lea     rax, [rbp+4B0h+var_B0]
0x1800d0215  mov     [rsp+530h+var_4F8], rax
0x1800d021a  lea     rax, [rbp+4B0h+var_98]
0x1800d0221  mov     [rsp+530h+var_500], rax
0x1800d0226  mov     [rsp+530h+var_508], r14
0x1800d022b  mov     [rsp+530h+var_510], r13
0x1800d0230  lea     rcx, [rbp+4B0h+var_68]
0x1800d0237  lea     rdx, [rbp+4B0h+Src]
0x1800d023e  mov     r9, r14
0x1800d0241  call    shaping__string__remap_run_properties
0x1800d0246  test    byte ptr [rbp+4B0h+var_68], 1
0x1800d024d  jz      short loc_1800D0266
0x1800d024f  mov     eax, dword ptr [rbp+4B0h+var_68+4]
0x1800d0255  jmp     loc_1800D0354
0x1800d025a  mov     [rbp+4B0h+var_48], r8
0x1800d0261  xor     r14d, r14d
0x1800d0264  jmp     short loc_1800D0289
0x1800d0266  mov     rax, [rbp+4B0h+var_90]
0x1800d026d  mov     [rbp+4B0h+var_48], rax
0x1800d0274  mov     r14, [rbp+4B0h+var_88]
0x1800d027b  mov     r13, [rbp+4B0h+lpMem]
0x1800d0282  mov     rdi, [rbp+4B0h+var_A0]
0x1800d0289  mov     r15d, [rbp+4B0h+var_CC]
0x1800d0290  lea     r8, shaping_cache__context__impl$2__get_cache_slot
0x1800d0297  lea     rcx, [rbp+4B0h+var_68]
0x1800d029e  lea     rdx, [rbp+4B0h+var_4A8]
0x1800d02a2  call    shaping__caching__CacheSlot_shaping__caching__CommonFontCacheData___init_shaping__caching__CommonFontCacheData_
0x1800d02a7  mov     rdx, [rbp+4B0h+var_68]
0x1800d02ae  test    rdx, rdx
0x1800d02b1  jz      loc_1800D034E
0x1800d02b7  mov     rax, [rbp+4B0h+var_60]
0x1800d02be  mov     rcx, [rax+10h]
0x1800d02c2  mov     [rbp+4B0h+var_70], rax
0x1800d02c9  mov     rax, [rax+18h]
0x1800d02cd  dec     rcx
0x1800d02d0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800d02d4  mov     [rbp+4B0h+var_78], rdx
0x1800d02db  add     rcx, rdx
0x1800d02de  add     rcx, 10h
0x1800d02e2  call    cs:__guard_dispatch_icall_fptr
0x1800d02e8  test    al, 3
0x1800d02ea  jnz     loc_1800D0AE2
0x1800d02f0  cmp     rdx, 0BBh
0x1800d02f7  jbe     loc_1800D0AE6
0x1800d02fd  mov     r10, [rbp+4B0h+arg_C0]
0x1800d0304  mov     r9, [rbp+4B0h+arg_B8]
0x1800d030b  mov     r8, [rbp+4B0h+arg_B0]
0x1800d0312  lea     ecx, [r15+r15]
0x1800d0316  mov     r11d, r15d
0x1800d0319  mov     ebx, 3
0x1800d031e  shl     ebx, cl
0x1800d0320  shr     r11d, 4
0x1800d0324  mov     ecx, [rax+r11*4+4]
0x1800d0329  cmp     byte ptr [rax+0A3h], 0
0x1800d0330  jz      loc_1800D044F
0x1800d0336  mov     r12d, ecx
0x1800d0339  and     r12d, ebx
0x1800d033c  jnz     loc_1800D044F
0x1800d0342  lea     rax, shaping__engine__aat__get_glyphs
0x1800d0349  jmp     loc_1800D047E
0x1800d034e  mov     eax, dword ptr [rbp+4B0h+var_60]
0x1800d0354  mov     [rsi+4], eax
0x1800d0357  mov     dword ptr [rsi], 1
0x1800d035d  cmp     [rbp+4B0h+var_B0], 0
0x1800d0365  jz      short loc_1800D0382
0x1800d0367  mov     rsi, [rbp+4B0h+lpMem]
0x1800d036e  call    cs:__imp_GetProcessHeap
0x1800d0374  mov     rcx, rax; hHeap
0x1800d0377  xor     edx, edx; dwFlags
0x1800d0379  mov     r8, rsi; lpMem
0x1800d037c  call    cs:__imp_HeapFree
0x1800d0382  cmp     [rbp+4B0h+var_98], 0
0x1800d038a  jz      short loc_1800D03A7
0x1800d038c  mov     rsi, [rbp+4B0h+var_90]
0x1800d0393  call    cs:__imp_GetProcessHeap
0x1800d0399  mov     rcx, rax; hHeap
0x1800d039c  xor     edx, edx; dwFlags
0x1800d039e  mov     r8, rsi; lpMem
0x1800d03a1  call    cs:__imp_HeapFree
0x1800d03a7  mov     rax, [rbp+4B0h+Src]
0x1800d03ae  neg     rax
0x1800d03b1  jo      short loc_1800D041A
0x1800d03b3  jnb     short loc_1800D03D0
0x1800d03b5  mov     rsi, [rbp+4B0h+var_2F0]
0x1800d03bc  call    cs:__imp_GetProcessHeap
0x1800d03c2  mov     rcx, rax; hHeap
0x1800d03c5  xor     edx, edx; dwFlags
0x1800d03c7  mov     r8, rsi; lpMem
0x1800d03ca  call    cs:__imp_HeapFree
0x1800d03d0  cmp     [rbp+4B0h+var_2E0], 0
0x1800d03d8  jz      short loc_1800D03F5
0x1800d03da  mov     rsi, [rbp+4B0h+var_2D8]
0x1800d03e1  call    cs:__imp_GetProcessHeap
0x1800d03e7  mov     rcx, rax; hHeap
0x1800d03ea  xor     edx, edx; dwFlags
0x1800d03ec  mov     r8, rsi; lpMem
0x1800d03ef  call    cs:__imp_HeapFree
0x1800d03f5  cmp     [rbp+4B0h+var_2C8], 0
0x1800d03fd  jz      short loc_1800D041A
0x1800d03ff  mov     rsi, [rbp+4B0h+var_2C0]
0x1800d0406  call    cs:__imp_GetProcessHeap
0x1800d040c  mov     rcx, rax; hHeap
0x1800d040f  xor     edx, edx; dwFlags
0x1800d0411  mov     r8, rsi; lpMem
0x1800d0414  call    cs:__imp_HeapFree
0x1800d041a  mov     rax, [rbp+4B0h+var_478]
0x1800d041e  lock dec qword ptr [rax]
0x1800d0422  jnz     short loc_1800D0431
0x1800d0424  mov     rcx, [rbp+4B0h+var_478]
0x1800d0428  mov     rdx, [rbp+4B0h+var_470]
0x1800d042c  call    alloc__sync__Arc_slice2$_shaping_cache__ShapingCacheSlot__alloc__alloc__Global___drop_slow_slice2$_shaping_cache__ShapingCacheSlot__alloc__alloc__Global_
0x1800d0431  lea     rcx, [rbp+4B0h+var_458]
0x1800d0435  call    core__ptr__drop_in_place_shaping_cache__context__FontTables_
0x1800d043a  nop
0x1800d043b  add     rsp, 4F8h
0x1800d0442  pop     rbx
0x1800d0443  pop     rdi
0x1800d0444  pop     rsi
0x1800d0445  pop     r12
0x1800d0447  pop     r13
0x1800d0449  pop     r14
0x1800d044b  pop     r15
0x1800d044d  pop     rbp
0x1800d044e  retn
0x1800d044f  mov     r12d, r15d
0x1800d0452  shl     r12d, 5
0x1800d0456  lea     rdx, off_180341570
0x1800d045d  movzx   edx, byte ptr [r12+rdx+18h]
0x1800d0463  lea     r12, jpt_1800D0471
0x1800d046a  movsxd  rdx, ds:(jpt_1800D0471 - 180407054h)[r12+rdx*4]; switch 5 cases
0x1800d046e  add     rdx, r12
0x1800d0471  jmp     rdx; switch jump
0x1800d0473  lea     rax, off_180342670; jumptable 00000001800D0471 case 0
0x1800d047a  mov     rax, [rax+r15*8]
0x1800d047e  mov     r11, cs:__guard_dispatch_icall_fptr
0x1800d0485  mov     [rsp+530h+var_4B8], r10
0x1800d048a  mov     [rsp+530h+var_4C0], r9
0x1800d048f  mov     [rsp+530h+var_4C8], r8
0x1800d0494  mov     rcx, [rbp+4B0h+arg_A8]
0x1800d049b  mov     [rsp+530h+var_4D0], rcx
0x1800d04a0  mov     rcx, [rbp+4B0h+arg_80]
0x1800d04a7  mov     [rsp+530h+var_4D8], rcx
0x1800d04ac  lea     rcx, [rbp+4B0h+var_148]
0x1800d04b3  mov     [rsp+530h+var_4E0], rcx
0x1800d04b8  lea     rcx, [rbp+4B0h+var_100]
0x1800d04bf  mov     [rsp+530h+var_4E8], rcx
0x1800d04c4  lea     rcx, [rbp+4B0h+Src]
0x1800d04cb  mov     [rsp+530h+var_4F0], rcx
0x1800d04d0  mov     [rsp+530h+var_4F8], rdi
0x1800d04d5  mov     [rsp+530h+var_500], r13
0x1800d04da  mov     [rsp+530h+var_508], r14
0x1800d04df  mov     rcx, [rbp+4B0h+var_48]
0x1800d04e6  mov     [rsp+530h+var_510], rcx
0x1800d04eb  lea     r8, off_180343070
0x1800d04f2  lea     rcx, [rbp+4B0h+var_68]
0x1800d04f9  lea     rdx, [rbp+4B0h+var_4A8]
0x1800d04fd  lea     r9, [rbp+4B0h+var_D0]
0x1800d0504  call    r11 ; _guard_dispatch_icall_nop
0x1800d0507  test    byte ptr [rbp+4B0h+var_68], 1
0x1800d050e  jz      short loc_1800D0541
0x1800d0510  mov     eax, dword ptr [rbp+4B0h+var_68+4]
0x1800d0516  mov     [rsi+4], eax
0x1800d0519  mov     dword ptr [rsi], 1
0x1800d051f  mov     rcx, [rbp+4B0h+var_78]
  ... truncated ...
```
