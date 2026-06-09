# DetermineSimpleGlyphsFromTableRust

- ea: `0x18007d900`
- end: `0x18007fcc8`
- name: `DetermineSimpleGlyphsFromTableRust`
- size: `9160`
- prototype: `__int64 __fastcall(__int64, __int64, int, const void *, unsigned __int64, unsigned int, unsigned int, unsigned __int64, IErrorInfo *, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1802b9b68`

## callees

- `0x180022de0`
- `0x180067680`
- `0x18006a270`
- `0x18006a400`
- `0x18006a4e0`
- `0x18006aea0`
- `0x18006b820`
- `0x18006baa0`
- `0x18006bc80`
- `0x18006be20`
- `0x18006c130`
- `0x18006c6a0`
- `0x18006c740`
- `0x18007d900`
- `0x1800dc910`
- `0x18021e1b6`
- `0x180316190`
- `0x180316232`
- `0x1803168c1`
- `0x180316ae0`

## import_xrefs

- `kernel32!HeapFree` at `0x18007ddb9`
- `kernel32!HeapFree` at `0x18007ddee`
- `kernel32!HeapFree` at `0x18007de3d`
- `kernel32!HeapFree` at `0x18007df7c`
- `kernel32!HeapFree` at `0x18007df95`
- `kernel32!HeapFree` at `0x18007fb9b`
- `kernel32!HeapFree` at `0x18007fcbd`
- `kernel32!HeapFree` at `0x18007ddb9`
- `kernel32!HeapFree` at `0x18007ddee`
- `kernel32!HeapFree` at `0x18007de3d`
- `kernel32!HeapFree` at `0x18007df7c`
- `kernel32!HeapFree` at `0x18007df95`
- `kernel32!HeapFree` at `0x18007fb9b`
- `kernel32!HeapFree` at `0x18007fcbd`
- `kernel32!GetProcessHeap` at `0x18007ddab`
- `kernel32!GetProcessHeap` at `0x18007dde0`
- `kernel32!GetProcessHeap` at `0x18007de2f`
- `kernel32!GetProcessHeap` at `0x18007df6e`
- `kernel32!GetProcessHeap` at `0x18007df87`
- `kernel32!GetProcessHeap` at `0x18007fb8d`
- `kernel32!GetProcessHeap` at `0x18007fcaf`
- `kernel32!GetProcessHeap` at `0x18007ddab`
- `kernel32!GetProcessHeap` at `0x18007dde0`
- `kernel32!GetProcessHeap` at `0x18007de2f`
- `kernel32!GetProcessHeap` at `0x18007df6e`
- `kernel32!GetProcessHeap` at `0x18007df87`
- `kernel32!GetProcessHeap` at `0x18007fb8d`
- `kernel32!GetProcessHeap` at `0x18007fcaf`
- `oleaut32!GetErrorInfo` at `0x18007d9cf`
- `oleaut32!GetErrorInfo` at `0x18007dd5b`
- `oleaut32!GetErrorInfo` at `0x18007de11`
- `oleaut32!GetErrorInfo` at `0x18007d9cf`
- `oleaut32!GetErrorInfo` at `0x18007dd5b`
- `oleaut32!GetErrorInfo` at `0x18007de11`

## string_xrefs

- `0x18007fa2c`: `assertion failed: (max_glyph_id as usize) < glyph_bits_size * 32rust\otls_interop\src\glyph_complexity.rs`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DetermineSimpleGlyphsFromTableRust(
        __int64 a1,
        __int64 a2,
        int a3,
        const void *a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int64 a8,
        IErrorInfo *a9,
        __int64 a10)
{
  int v10; // r15d
  unsigned __int64 v11; // r13
  size_t v12; // rsi
  __int64 v13; // rcx
  IErrorInfo *v14; // rcx
  unsigned int v15; // esi
  const void *v18; // r14
  __int64 v19; // rax
  __int64 v20; // r12
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // rdx
  char v23; // r14
  IErrorInfo *v24; // rcx
  _WORD *v25; // r13
  unsigned __int64 v26; // rbx
  bool v27; // cf
  unsigned __int64 v28; // r13
  _WORD *v29; // rbx
  unsigned __int64 v30; // r15
  unsigned __int64 v31; // rax
  char *v32; // r15
  unsigned __int16 v33; // cx
  __int64 v34; // r12
  _WORD *v35; // r15
  unsigned __int16 i; // r12
  unsigned __int64 v37; // r15
  unsigned __int64 v38; // rax
  char *v39; // r15
  unsigned __int16 v40; // cx
  __int64 v41; // r14
  _WORD *v42; // r15
  IErrorInfo *v43; // rbx
  __int64 v44; // r15
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rax
  char *v47; // rsi
  HANDLE ProcessHeap; // rax
  void *v49; // rsi
  HANDLE v50; // rax
  IErrorInfo *v51; // rdi
  HANDLE v52; // rax
  __int64 v53; // rbx
  unsigned __int64 v54; // r8
  __m128i si128; // xmm0
  unsigned __int64 v56; // rax
  const __m128i *v57; // rsi
  __int64 v59; // rdi
  void *v60; // rsi
  HANDLE v61; // rax
  HANDLE v62; // rax
  unsigned __int64 v65; // rax
  int v66; // r15d
  unsigned __int16 v67; // ax
  unsigned __int16 v68; // ax
  IErrorInfo *v69; // rcx
  IErrorInfo *v70; // rdx
  __int64 v71; // rax
  IErrorInfo *v72; // r11
  unsigned __int16 v73; // ax
  unsigned __int64 v74; // r10
  char *v75; // r11
  __int16 v76; // ax
  unsigned __int16 v77; // dx
  unsigned __int64 v78; // rdx
  __int16 v79; // cx
  unsigned __int16 v80; // cx
  unsigned __int64 v81; // rdx
  __int16 v82; // cx
  unsigned __int16 v83; // cx
  int v84; // r8d
  char *v85; // rcx
  __int64 v86; // rax
  IErrorInfo *v87; // rcx
  __int16 v88; // ax
  unsigned __int16 v89; // cx
  IErrorInfo *v90; // rdx
  __int16 v91; // r8
  __m128i *v92; // r9
  __m128i *v93; // r10
  __int64 v94; // r13
  __int16 *v95; // r11
  __int16 *v96; // r14
  unsigned __int16 *v97; // r12
  unsigned __int16 v98; // ax
  unsigned __int64 v99; // r10
  char *v100; // r11
  __int16 v101; // ax
  __int16 v102; // ax
  __int64 v103; // rax
  IErrorInfo *v104; // rcx
  __int16 v105; // dx
  char *v106; // r14
  __int64 v107; // r11
  unsigned __int16 v108; // ax
  unsigned __int64 v109; // r10
  char *v110; // r11
  __int16 v111; // ax
  __int64 v112; // rax
  IErrorInfo *v113; // r11
  IErrorInfo *v114; // rdx
  unsigned __int64 v115; // r13
  unsigned __int64 v116; // r9
  unsigned __int64 v117; // rcx
  unsigned __int64 v118; // rax
  _WORD *v119; // r12
  unsigned __int64 v120; // rax
  unsigned __int64 v121; // rdx
  unsigned __int64 v122; // rax
  unsigned __int16 v123; // ax
  unsigned __int64 v124; // rcx
  char *v125; // rax
  __int16 v126; // dx
  __int64 v127; // rdx
  char *v128; // r14
  IErrorInfo *v129; // rax
  IErrorInfo *v130; // rcx
  unsigned __int16 v131; // ax
  unsigned __int64 v132; // rcx
  char *v133; // rax
  __int16 v134; // dx
  __int64 v135; // rdx
  IErrorInfo *v136; // rax
  IErrorInfo *v137; // r10
  unsigned __int16 v138; // ax
  unsigned __int64 v139; // r10
  char *v140; // r11
  __int16 v141; // ax
  __int64 v142; // rax
  __int64 v143; // r8
  __int64 v144; // r9
  __int64 v145; // r12
  __int64 v146; // rdx
  __int16 v147; // ax
  __int64 v148; // rax
  IErrorInfo *v149; // rcx
  __int16 v150; // dx
  char *v151; // r14
  __int64 v152; // r11
  unsigned __int128 v153; // kr140_16
  IErrorInfo *v154; // rcx
  IErrorInfo **v155; // r14
  unsigned int v156; // eax
  unsigned int v157; // r11d
  unsigned __int64 v158; // rdx
  unsigned __int16 v159; // cx
  unsigned int v160; // r9d
  unsigned __int16 v161; // cx
  unsigned __int64 v162; // rdx
  char *v163; // r12
  __int16 v164; // cx
  _WORD *v165; // rdx
  unsigned __int64 v166; // r8
  unsigned __int64 v167; // rcx
  unsigned int v168; // r13d
  unsigned __int16 v169; // cx
  unsigned __int64 v170; // rcx
  __int16 v171; // r10
  unsigned __int16 v172; // r10
  unsigned __int64 v173; // r12
  __int64 v174; // r14
  unsigned int v175; // ecx
  unsigned __int64 v176; // r10
  char v177; // al
  int v178; // edx
  __int64 v179; // r9
  __int64 v180; // r8
  IErrorInfo *v181; // r8
  unsigned __int64 v182; // rcx
  unsigned __int16 v183; // ax
  unsigned __int64 v184; // rcx
  char *v185; // rax
  __int16 v186; // dx
  IErrorInfo *v187; // rax
  IErrorInfo *v188; // rcx
  unsigned __int16 v189; // dx
  _WORD *v190; // rax
  _WORD *v191; // r12
  unsigned __int16 v192; // ax
  unsigned __int64 v193; // rcx
  char *v194; // rax
  __int16 v195; // dx
  IErrorInfo *v196; // rax
  IErrorInfo *v197; // rcx
  unsigned __int16 v198; // dx
  IErrorInfo *v199; // rcx
  __m128i v200; // xmm0
  unsigned __int64 v201; // r12
  char *v202; // r14
  __m128i v203; // xmm0
  __int64 v204; // rcx
  IErrorInfo *v205; // rdx
  __int64 v206; // r9
  unsigned __int64 v207; // r14
  __int64 v208; // rcx
  IErrorInfo *v209; // rdx
  __int64 v210; // r9
  int v211; // r8d
  unsigned __int64 v212; // r8
  unsigned __int64 v213; // r10
  unsigned __int64 v214; // r8
  int v215; // r8d
  unsigned __int64 v216; // r8
  unsigned __int64 v217; // r8
  unsigned __int64 v218; // rdx
  int v219; // eax
  const __m128i *v220; // r12
  int v221; // eax
  unsigned __int64 v224; // rdi
  __int64 v225; // rcx
  bool v226; // zf
  unsigned __int64 v227; // rax
  void *v228; // rsi
  HANDLE v229; // rax
  __int64 v230; // [rsp+28h] [rbp-58h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-50h]
  unsigned __int64 v232; // [rsp+50h] [rbp-30h]
  unsigned __int64 v233; // [rsp+58h] [rbp-28h]
  _WORD *v234; // [rsp+78h] [rbp-8h]
  _WORD *v235; // [rsp+80h] [rbp+0h]
  IErrorInfo *v236; // [rsp+88h] [rbp+8h]
  __int64 v237; // [rsp+90h] [rbp+10h]
  __int16 v238; // [rsp+98h] [rbp+18h]
  __int64 v239; // [rsp+A0h] [rbp+20h]
  __int64 v240; // [rsp+A8h] [rbp+28h]
  __int64 v241; // [rsp+B0h] [rbp+30h]
  unsigned __int64 v242; // [rsp+B8h] [rbp+38h]
  char v243[32]; // [rsp+D0h] [rbp+50h] BYREF
  __m128i v244; // [rsp+F0h] [rbp+70h] BYREF
  __int128 v245; // [rsp+100h] [rbp+80h]
  __int64 v246; // [rsp+110h] [rbp+90h]
  __m128i v247; // [rsp+120h] [rbp+A0h] BYREF
  __int128 v248; // [rsp+130h] [rbp+B0h]
  __int64 v249; // [rsp+140h] [rbp+C0h]
  unsigned __int64 v250; // [rsp+150h] [rbp+D0h]
  __int64 v251; // [rsp+158h] [rbp+D8h]
  unsigned __int64 v252; // [rsp+160h] [rbp+E0h]
  unsigned __int64 v253; // [rsp+168h] [rbp+E8h]
  __m128i v254; // [rsp+170h] [rbp+F0h] BYREF
  __int64 v255; // [rsp+180h] [rbp+100h]
  char *v256; // [rsp+188h] [rbp+108h]
  unsigned __int64 v257; // [rsp+190h] [rbp+110h]
  IErrorInfo *v258; // [rsp+198h] [rbp+118h]
  IErrorInfo *v259; // [rsp+1A0h] [rbp+120h]
  unsigned __int64 v260; // [rsp+1A8h] [rbp+128h]
  unsigned int v261; // [rsp+1B0h] [rbp+130h]
  int v262; // [rsp+1B4h] [rbp+134h]
  unsigned __int64 v263; // [rsp+1B8h] [rbp+138h]
  char *v264; // [rsp+1C0h] [rbp+140h]
  unsigned __int64 v265; // [rsp+1C8h] [rbp+148h]
  __m128i v266; // [rsp+1D0h] [rbp+150h] BYREF
  __int128 v267; // [rsp+1E0h] [rbp+160h]
  __int16 v268; // [rsp+1F0h] [rbp+170h]
  __int16 v269; // [rsp+1F2h] [rbp+172h]
  __int16 v270; // [rsp+1F4h] [rbp+174h]
  __int16 v271; // [rsp+1F6h] [rbp+176h]
  __m128i v272; // [rsp+1F8h] [rbp+178h] BYREF
  __int128 v273; // [rsp+208h] [rbp+188h]
  __int64 v274; // [rsp+218h] [rbp+198h]
  IErrorInfo *pperrinfo[2]; // [rsp+220h] [rbp+1A0h] BYREF
  _BYTE v276[24]; // [rsp+230h] [rbp+1B0h]
  unsigned __int64 v277; // [rsp+248h] [rbp+1C8h]
  __m128i v278; // [rsp+250h] [rbp+1D0h]
  __int128 v279; // [rsp+260h] [rbp+1E0h]
  __int64 v280; // [rsp+270h] [rbp+1F0h]
  __int64 v281; // [rsp+308h] [rbp+288h] BYREF
  __int64 v282; // [rsp+310h] [rbp+290h]
  __int64 v283; // [rsp+318h] [rbp+298h]
  IErrorInfo *v284; // [rsp+320h] [rbp+2A0h] BYREF
  unsigned __int64 v285; // [rsp+328h] [rbp+2A8h]
  __int64 v286; // [rsp+330h] [rbp+2B0h]
  unsigned __int64 v287; // [rsp+338h] [rbp+2B8h]
  unsigned int v288; // [rsp+340h] [rbp+2C0h]
  unsigned int v289; // [rsp+344h] [rbp+2C4h]
  unsigned __int64 v290; // [rsp+348h] [rbp+2C8h]
  unsigned __int64 v291; // [rsp+350h] [rbp+2D0h]
  unsigned __int64 v292; // [rsp+358h] [rbp+2D8h]
  unsigned __int64 v293; // [rsp+360h] [rbp+2E0h]
  unsigned __int64 v294; // [rsp+368h] [rbp+2E8h]
  __int16 v295; // [rsp+370h] [rbp+2F0h] BYREF
  __int16 v296; // [rsp+372h] [rbp+2F2h]
  __int32 v297; // [rsp+374h] [rbp+2F4h]
  __int16 v298; // [rsp+378h] [rbp+2F8h]
  __int32 v299; // [rsp+37Ah] [rbp+2FAh]
  __int16 v300; // [rsp+37Eh] [rbp+2FEh]
  __int16 v301; // [rsp+380h] [rbp+300h] BYREF
  int v302; // [rsp+384h] [rbp+304h]
  __int16 v303; // [rsp+388h] [rbp+308h] BYREF
  _WORD *v304; // [rsp+390h] [rbp+310h]
  _WORD *v305; // [rsp+398h] [rbp+318h]
  unsigned __int64 v306; // [rsp+3A0h] [rbp+320h]
  unsigned __int16 v307; // [rsp+3AEh] [rbp+32Eh]
  IErrorInfo *v308; // [rsp+3B0h] [rbp+330h]
  unsigned __int64 v309; // [rsp+3B8h] [rbp+338h]
  unsigned __int64 v310; // [rsp+3C0h] [rbp+340h]
  unsigned __int64 v311; // [rsp+3C8h] [rbp+348h]
  LPVOID v312; // [rsp+3D0h] [rbp+350h]
  bool v313; // [rsp+3DFh] [rbp+35Fh]
  __int64 v314; // [rsp+3E0h] [rbp+360h]

  v314 = -2;
  if ( !a1 )
    return 0;
  if ( a3 == 1112888135 )
  {
    v10 = 0;
  }
  else
  {
    if ( a3 != 1397706823 )
    {
LABEL_11:
      pperrinfo[0] = 0;
      GetErrorInfo(0, pperrinfo);
      v14 = pperrinfo[0];
      v15 = -2147024809;
      goto LABEL_12;
    }
    LOBYTE(v10) = 1;
  }
  if ( 32 * a8 <= a7 )
    core::panicking::panic(
      "assertion failed: (max_glyph_id as usize) < glyph_bits_size * 32rust\\otls_interop\\src\\glyph_complexity.rs",
      64,
      &off_18033AF50);
  if ( !a4 )
    goto LABEL_11;
  v11 = a5;
  v12 = 4 * a5;
  if ( a5 >> 62 != 0 || 4 * a5 > 0x7FFFFFFFFFFFFFFCLL )
  {
    v13 = 0;
    goto LABEL_10;
  }
  if ( v12 )
  {
    v18 = a4;
    v19 = std::sys::alloc::windows::process_heap_alloc(0, 4 * a5);
    if ( !v19 )
    {
      v13 = 4;
LABEL_10:
      alloc::raw_vec::handle_error(v13, v12, &off_180348EC0);
    }
    v20 = v19;
    a4 = v18;
  }
  else
  {
    v20 = 4;
    v11 = 0;
  }
  memcpy_0((void *)v20, a4, v12);
  if ( a9 && a10 )
  {
    otls::gpos::GPosHeader::new(pperrinfo, a1, a2);
    if ( pperrinfo[0] != (IErrorInfo *)0x8000000000000001LL )
    {
      memcpy_0(&v230, pperrinfo, 0xC8u);
      v22 = v240;
      if ( !v240 )
      {
        v23 = 0;
        goto LABEL_57;
      }
      v23 = 0;
      if ( v233 && v238 )
      {
        *(_OWORD *)v276 = xmmword_180342F40;
        *(_OWORD *)pperrinfo = *(_OWORD *)&off_180342F30;
        if ( v237 )
        {
          v290 = v233;
          v282 = v240;
          v302 = v10;
          v309 = v11;
          v312 = (LPVOID)v20;
          v24 = v236;
          v306 = (unsigned __int64)v236 + 6 * v237;
          v304 = v234;
          v25 = v235;
          v305 = v235;
          do
          {
            v308 = v24;
            v26 = (unsigned __int16)__ROL2__(WORD2(v24->lpVtbl), 8);
            v27 = (unsigned __int64)v25 < v26;
            v28 = (unsigned __int64)v25 - v26;
            if ( v27
              || v28 < 2
              || (v28 & 0xFFFFFFFFFFFFFFFEuLL) == 2
              || (v29 = (_WORD *)((char *)v304 + v26),
                  LOWORD(v310) = __ROL2__(v29[1], 8),
                  3 * (unsigned __int64)(2 * (unsigned int)(unsigned __int16)v310) > v28 - 4) )
            {
LABEL_53:
              if ( pperrinfo[1] )
              {
                v46 = (8 * (__int64)pperrinfo[1] + 23) & 0xFFFFFFFFFFFFFFF0uLL;
                if ( (IErrorInfo *)((char *)pperrinfo[1] + v46) != (IErrorInfo *)-17LL )
                {
                  v47 = (char *)pperrinfo[0] - v46;
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, v47);
                }
              }
              v23 = 1;
              v20 = (__int64)v312;
              v11 = v309;
              goto LABEL_57;
            }
            if ( *v29 )
            {
              v30 = (unsigned __int16)__ROL2__(*v29, 8);
              v31 = v28 - v30;
              if ( v28 < v30 )
                goto LABEL_53;
              if ( v31 < 6 )
                goto LABEL_53;
              v32 = (char *)v29 + v30;
              v33 = __ROL2__(*((_WORD *)v32 + 2), 8);
              if ( 2 * (unsigned int)v33 > v31 - 6 )
                goto LABEL_53;
              if ( v33 )
              {
                v34 = (__int64)&v32[2 * v33 + 6];
                v35 = v32 + 6;
                do
                  hashbrown::map::HashMap_usize_tuple____bcrypt_workaround::HasherState_alloc::alloc::Global_::insert_usize_tuple____bcrypt_workaround::HasherState_alloc::alloc::Global_(
                    pperrinfo,
                    (unsigned __int16)__ROL2__(*v35++, 8));
                while ( v35 != (_WORD *)v34 );
              }
            }
            v308 = (IErrorInfo *)((char *)v308 + 6);
            for ( i = 0; i < (unsigned __int16)v310; ++i )
            {
              v37 = (unsigned __int16)__ROL2__(v29[3 * i + 4], 8);
              v38 = v28 - v37;
              if ( v28 < v37 )
                goto LABEL_53;
              if ( v38 < 6 )
                goto LABEL_53;
              v39 = (char *)v29 + v37;
              v40 = __ROL2__(*((_WORD *)v39 + 2), 8);
              if ( 2 * (unsigned int)v40 > v38 - 6 )
                goto LABEL_53;
              if ( v40 )
              {
                v41 = (__int64)&v39[2 * v40 + 6];
                v42 = v39 + 6;
                do
                  hashbrown::map::HashMap_usize_tuple____bcrypt_workaround::HasherState_alloc::alloc::Global_::insert_usize_tuple____bcrypt_workaround::HasherState_alloc::alloc::Global_(
                    pperrinfo,
                    (unsigned __int16)__ROL2__(*v42++, 8));
                while ( v42 != (_WORD *)v41 );
              }
            }
            v24 = v308;
            v25 = v305;
          }
          while ( v308 != (IErrorInfo *)v306 );
          v43 = pperrinfo[0];
          if ( !pperrinfo[0] )
          {
LABEL_345:
            v20 = (__int64)v312;
            v11 = v309;
            v23 = 1;
            goto LABEL_57;
          }
          v44 = *(_QWORD *)&v276[8];
          v267 = xmmword_180342F40;
          v266 = *(__m128i *)&off_180342F30;
          v308 = pperrinfo[1];
          if ( pperrinfo[1] )
          {
            v45 = (8LL * (_QWORD)v308 + 23) & 0xFFFFFFFFFFFFFFF0uLL;
            v305 = (_WORD *)((char *)pperrinfo[0] - v45);
            LOBYTE(v304) = (struct IErrorInfoVtbl **)((char *)&v308[2].lpVtbl + v45 + 1) == 0;
            v306 = 16;
          }
          else
          {
            v306 = 0;
          }
          if ( *(_QWORD *)&v276[8] )
          {
            v219 = ~_mm_movemask_epi8(_mm_load_si128((const __m128i *)pperrinfo[0]));
            v220 = (const __m128i *)&pperrinfo[0][2];
            v310 = v232;
            while ( 1 )
            {
              if ( !(_WORD)v219 )
              {
                do
                {
                  v221 = _mm_movemask_epi8(_mm_load_si128(v220));
                  v43 -= 16;
                  ++v220;
                }
                while ( v221 == 0xFFFF );
                v219 = ~v221;
              }
              _R13D = v219;
              __asm { tzcnt   eax, r13d }
              v224 = *(unsigned __int64 *)((char *)&v43[-1].lpVtbl - (unsigned int)(8 * _EAX));
              if ( v224 < v290 )
              {
                v225 = 0;
                do
                {
                  if ( v12 == v225 )
                    goto LABEL_330;
                  v226 = *(_DWORD *)((char *)v312 + v225) == *(_DWORD *)(v310 + 6 * v224);
                  v225 += 4;
                }
                while ( !v226 );
                otls::features::FeatureListTable::feature_table(pperrinfo, &v230, v224);
                if ( !pperrinfo[0]
                  || (unsigned __int8)otls::glyph_complexity::collect_lookup_set_for_feature(
                                        (unsigned int)&v266,
                                        v224,
                                        *(_DWORD *)v276,
                                        *(_DWORD *)&v276[8],
                                        (__int64)v243) )
                {
                  break;
                }
              }
LABEL_330:
              v219 = _R13D & (_R13D - 1);
              if ( !--v44 )
                goto LABEL_346;
            }
            if ( !((unsigned __int8)v304 & 1 | (v308 == 0)) )
              sub_180022DE0(v305, v306);
            if ( v266.m128i_i64[1] )
            {
              v227 = (8 * v266.m128i_i64[1] + 23) & 0xFFFFFFFFFFFFFFF0uLL;
              if ( v227 + v266.m128i_i64[1] != -17 )
              {
                v228 = (void *)(v266.m128i_i64[0] - v227);
                v229 = GetProcessHeap();
                HeapFree(v229, 0, v228);
              }
            }
            goto LABEL_345;
          }
LABEL_346:
          v20 = (__int64)v312;
          v11 = v309;
          v10 = v302;
          v22 = v282;
          if ( !((unsigned __int8)v304 & 1 | (v308 == 0)) )
          {
            sub_180022DE0(v305, v306);
            v22 = v282;
          }
        }
        else
        {
          v267 = xmmword_180342F40;
          v266 = *(__m128i *)&off_180342F30;
        }
        v53 = v266.m128i_i64[0];
        v23 = 1;
        if ( !v266.m128i_i64[0] )
          goto LABEL_57;
        v288 = a6;
        v289 = a7;
        v284 = a9;
        v285 = a8;
        LOWORD(v54) = a10;
        v286 = a10;
        v287 = a8;
        si128 = _mm_load_si128((const __m128i *)v266.m128i_i64[0]);
        v302 = v10;
        v290 = v266.m128i_u64[1];
        if ( v266.m128i_i64[1] )
        {
          v56 = (8 * v266.m128i_i64[1] + 23) & 0xFFFFFFFFFFFFFFF0uLL;
          LOWORD(v54) = v22;
          v263 = v266.m128i_i64[0] - v56;
          v313 = v56 + v266.m128i_i64[1] == -17;
          v283 = 16;
        }
        else
        {
          v283 = 0;
        }
        v57 = (const __m128i *)(v266.m128i_i64[0] + 16);
        _R15D = ~_mm_movemask_epi8(si128);
        v59 = *((_QWORD *)&v267 + 1) - 1LL;
        if ( *((_QWORD *)&v267 + 1) )
        {
          do
          {
            while ( 1 )
            {
              if ( !(_WORD)_R15D )
              {
                do
                {
                  v66 = _mm_movemask_epi8(_mm_load_si128(v57));
                  v53 -= 128;
                  ++v57;
                }
                while ( v66 == 0xFFFF );
                _R15D = ~v66;
              }
              __asm { tzcnt   ecx, r15d }
              _R15D &= _R15D - 1;
              v65 = *(_QWORD *)(v53 - (unsigned int)(8 * _ECX) - 8);
              if ( v65 < v22 )
                break;
              v27 = v59-- == 0;
              if ( v27 )
                goto LABEL_68;
            }
            v67 = __ROL2__(*(_WORD *)(v239 + 2 * v65), 8);
            v306 = v242 - v67;
            if ( v242 < v67 )
              goto LABEL_324;
            if ( v306 < 6 )
              goto LABEL_324;
            v305 = (_WORD *)(v241 + v67);
            v68 = __ROL2__(v305[2], 8);
            if ( 2 * (unsigned int)v68 > v306 - 6 )
              goto LABEL_324;
            v304 = v305 + 3;
            v296 = *v305;
            v307 = __ROL2__(v296, 8);
            v282 = (__int64)&v305[v68 + 3];
            v312 = (LPVOID)v20;
            v309 = v11;
            while ( v304 != (_WORD *)v282 )
            {
              v73 = __ROL2__(*v304, 8);
              v74 = v306 - v73;
              if ( v306 < v73 || v74 < 2 )
                goto LABEL_324;
              ++v304;
              v75 = (char *)v305 + v73;
              v76 = *(_WORD *)v75;
              v77 = __ROL2__(*(_WORD *)v75, 8);
              if ( (_BYTE)v302 )
              {
                if ( v296 == 2304 )
                {
                  if ( v74 < 8 )
                    goto LABEL_323;
                  v78 = _byteswap_ulong(*((_DWORD *)v75 + 1));
                  v27 = v74 < v78;
                  v74 -= v78;
                  if ( v27 || v74 < 2 )
                    goto LABEL_323;
                  v79 = *((_WORD *)v75 + 1);
                  v76 = *(_WORD *)&v75[v78];
                  v75 += v78;
                  v80 = __ROL2__(v79, 8);
                  v77 = __ROL2__(v76, 8);
                }
                else
                {
                  v80 = v307;
                }
                v84 = v80 - 1;
                v85 = (char *)v77;
                switch ( v84 )
                {
                  case 0:
                    if ( v77 == 2 )
                    {
                      if ( v74 < 8
                        || (unsigned __int8)(2
                                           * ((286331153
                                             * (((134480385 * (unsigned int)(unsigned __int8)v75[5]) >> 3) & 0x11111111)) >> 28))
                         * (unsigned __int64)(unsigned __int16)__ROL2__(*((_WORD *)v75 + 3), 8)
                         + 8 > v74 )
                      {
                        goto LABEL_323;
                      }
                      v86 = 2;
                      v87 = (IErrorInfo *)v75;
                      v75 = 0;
                    }
                    else
                    {
                      if ( v77 != 1 )
                        goto LABEL_323;
                      if ( v74 < 6 )
                        goto LABEL_323;
                      v86 = (unsigned __int8)v75[5];
                      if ( v74 < (unsigned __int8)(2
                                                 * ((286331153 * (((unsigned int)(134480385 * v86) >> 3) & 0x11111111)) >> 28)
                                                 + 6) )
                        goto LABEL_323;
                      v87 = (IErrorInfo *)v74;
                      v74 = 1;
                    }
                    pperrinfo[0] = (IErrorInfo *)v75;
                    pperrinfo[1] = v87;
                    *(_QWORD *)v276 = v74;
                    *(_QWORD *)&v276[8] = v86;
                    v177 = enum2__otls::gpos::singlpos::SinglePosLookup_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                             pperrinfo,
                             &v284);
                    break;
                  case 1:
                    if ( v77 == 2 )
                    {
                      if ( v74 < 0x10 )
                        goto LABEL_323;
                      v142 = (unsigned __int8)v75[5];
                      v178 = (unsigned __int8)v75[7];
                      v145 = v74;
                      v179 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 6), 8);
                      v180 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 7), 8);
                      if ( (unsigned __int64)(unsigned __int8)(2
                                                             * (((286331153
                                                                * (((unsigned int)(134480385 * v142) >> 3) & 0x11111111)) >> 28)
                                                              + ((286331153
                                                                * (((unsigned int)(134480385 * v178) >> 3) & 0x11111111)) >> 28)))
                         * v180
                         * v179
                         + 16 > v74 )
                        goto LABEL_323;
                      v143 = v180 << 48;
                      v144 = v179 << 32;
                      v146 = v143 | v144 | (unsigned int)(v178 << 16);
                      v74 = (unsigned __int64)v75;
                      v75 = 0;
                    }
                    else
                    {
                      if ( v77 != 1 )
                        goto LABEL_323;
                      if ( v74 < 0xA )
                        goto LABEL_323;
                      v142 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 4), 8);
                      if ( 2 * (unsigned int)(unsigned __int16)v142 > v74 - 10 )
                        goto LABEL_323;
                      v85 = v75 + 10;
                      LOWORD(v143) = (unsigned __int8)v75[5];
                      LOWORD(v144) = (unsigned __int8)v75[7];
                      v145 = 1;
                      v146 = 0;
                    }
                    pperrinfo[0] = (IErrorInfo *)v75;
                    pperrinfo[1] = (IErrorInfo *)v74;
                    *(_QWORD *)v276 = v145;
                    *(_QWORD *)&v276[8] = v85;
                    *(_QWORD *)&v276[16] = v146 | v142;
                    LOWORD(v277) = v143;
                    WORD1(v277) = v144;
                    v177 = enum2__otls::gpos::pairpos::PairPosLookup_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                             pperrinfo,
                             &v284);
                    break;
                  case 2:
                    if ( v74 < 6 )
                      goto LABEL_323;
                    if ( v76 != 256 )
                      goto LABEL_323;
                    if ( 4 * (unsigned int)(unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8) > v74 - 6 )
                      goto LABEL_323;
                    v138 = __ROL2__(*((_WORD *)v75 + 1), 8);
                    v27 = v74 < v138;
                    v139 = v74 - v138;
                    if ( v27 || v139 < 4 )
                      goto LABEL_323;
                    v140 = &v75[v138];
                    v141 = __ROL2__(*(_WORD *)v140, 8);
                    if ( v141 == 2 )
                    {
                      v199 = (IErrorInfo *)(unsigned __int16)__ROL2__(*((_WORD *)v140 + 1), 8);
                      if ( 3 * (unsigned __int64)(unsigned int)(2 * (_DWORD)v199) > v139 - 4 )
                        goto LABEL_323;
                      v114 = (IErrorInfo *)(v140 + 4);
                      v112 = (unsigned int)((_DWORD)v199 << 16) | 2LL;
                      v113 = v199;
                    }
                    else
                    {
                      if ( v141 != 1 )
                        goto LABEL_323;
                      v112 = (unsigned __int16)__ROL2__(*((_WORD *)v140 + 1), 8);
                      if ( 2 * (unsigned int)(unsigned __int16)v112 > v139 - 4 )
                        goto LABEL_323;
                      v113 = (IErrorInfo *)(v140 + 4);
                      v114 = 0;
                    }
                    goto LABEL_203;
                  case 3:
                    if ( v77 == 1 && v74 > 0xB )
                    {
                      otls::gpos::singlpos::OneSinglePosSubTable::coverage(pperrinfo, v75, v74);
                      if ( LODWORD(pperrinfo[0]) != 1 )
                        goto LABEL_197;
                    }
                    goto LABEL_323;
                  case 4:
                    if ( v77 == 1 && v74 > 0xB )
                    {
                      otls::gpos::singlpos::OneSinglePosSubTable::coverage(pperrinfo, v75, v74);
                      if ( LODWORD(pperrinfo[0]) != 1 )
                        goto LABEL_197;
                    }
                    goto LABEL_323;
                  case 5:
                    if ( v77 != 1 )
                      goto LABEL_323;
                    if ( v74 <= 0xB )
                      goto LABEL_323;
                    otls::gpos::singlpos::OneSinglePosSubTable::coverage(pperrinfo, v75, v74);
                    if ( LODWORD(pperrinfo[0]) == 1 )
                      goto LABEL_323;
LABEL_197:
                    *(_QWORD *)&v267 = *(_QWORD *)&v276[8];
                    v266 = _mm_loadu_si128((const __m128i *)&pperrinfo[1]);
                    enum2__otls::coverage::Coverage_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                      &v266,
                      &v284);
                    goto LABEL_89;
                  case 6:
                    v207 = v74;
                    if ( v77 == 3 )
                    {
                      if ( v74 < 6 )
                        goto LABEL_323;
                      LOWORD(v299) = __ROL2__(*((_WORD *)v75 + 1), 8);
                      v208 = (unsigned __int16)v299;
                      v217 = 2 * (unsigned int)(unsigned __int16)v299;
                      v218 = v74 - 6 - v217;
                      if ( v74 - 6 < v217 )
                        goto LABEL_323;
                      HIWORD(v299) = __ROL2__(*((_WORD *)v75 + 2), 8);
                      v74 = HIWORD(v299);
                      if ( 4 * (unsigned int)HIWORD(v299) > v218 )
                        goto LABEL_323;
                      v209 = (IErrorInfo *)(v75 + 6);
                      v216 = (unsigned __int64)&v75[v217 + 6];
                      v210 = 2;
                      v253 = v207;
                      v300 = __ROL2__(v76, 8);
                      v293 = (unsigned __int64)v75;
                    }
                    else
                    {
                      if ( v77 == 2 )
                      {
                        if ( v74 < 8 )
                          goto LABEL_323;
                        v208 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 3), 8);
                        if ( (unsigned int)(2 * v208) > v74 - 8 )
                          goto LABEL_323;
                        v209 = (IErrorInfo *)(v75 + 8);
                        v215 = *((unsigned __int16 *)v75 + 2);
                        LOWORD(v215) = __ROL2__(v215, 8);
                        v293 = (unsigned int)(v215 << 16)
                             | (unsigned __int16)__ROL2__(*((_WORD *)v75 + 1), 8)
                             | v293 & 0xFFFFFFFF00000000uLL;
                        v210 = 1;
                      }
                      else
                      {
                        if ( v77 != 1 )
                          goto LABEL_323;
                        if ( v74 < 6 )
                          goto LABEL_323;
                        v208 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8);
                        if ( (unsigned int)(2 * v208) > v74 - 6 )
                          goto LABEL_323;
                        v209 = (IErrorInfo *)(v75 + 6);
                        v293 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 1), 8) | v293 & 0xFFFFFFFFFFFF0000uLL;
                        v210 = 0;
                      }
                      v216 = (unsigned __int64)v75;
                    }
                    pperrinfo[1] = v209;
                    *(_QWORD *)v276 = v208;
                    *(_QWORD *)&v276[8] = v216;
                    *(_QWORD *)&v276[16] = v74;
                    v277 = v293;
                    v278.m128i_i64[0] = v253;
                    v278.m128i_i16[4] = v300;
                    *(__int32 *)((char *)&v278.m128i_i32[2] + 2) = v299;
                    pperrinfo[0] = (IErrorInfo *)v210;
                    v177 = enum2__otls::gsub_gpos_shared::context::ContextLookup_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                             pperrinfo,
                             &v284);
                    break;
                  case 7:
                    if ( v74 < 4 )
                      goto LABEL_323;
                    v147 = __ROL2__(v76, 8);
                    switch ( v147 )
                    {
                      case 3:
                        otls::gsub_gpos_shared::chaining::ChainCoverageSubTable::parse(&v266, v75, v74);
                        v149 = (IErrorInfo *)v266.m128i_i64[0];
                        if ( !v266.m128i_i64[0] )
                          goto LABEL_323;
                        v148 = v266.m128i_i64[1];
                        v153 = v267;
                        v150 = v268;
                        LOWORD(v74) = v269;
                        LOWORD(v84) = v270;
                        LOWORD(v21) = v271;
                        v244 = _mm_loadu_si128(&v272);
                        v245 = v273;
                        v246 = v274;
                        v152 = 2;
                        break;
                      case 2:
                        if ( v74 < 0xC )
                          goto LABEL_323;
                        v148 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 5), 8);
                        if ( 2 * (unsigned int)(unsigned __int16)v148 > v74 - 12 )
                          goto LABEL_323;
                        v201 = v74;
                        v149 = (IErrorInfo *)(v75 + 12);
                        LOWORD(v21) = __ROL2__(*((_WORD *)v75 + 4), 8);
                        LOWORD(v84) = __ROL2__(*((_WORD *)v75 + 3), 8);
                        LOWORD(v74) = __ROL2__(*((_WORD *)v75 + 2), 8);
                        v150 = __ROL2__(*((_WORD *)v75 + 1), 8);
                        v202 = v75;
                        v152 = 1;
                        v153 = __PAIR128__(v201, (unsigned __int64)v202);
                        break;
                      case 1:
                        if ( v74 < 6 )
                          goto LABEL_323;
                        v148 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8);
                        if ( 2 * (unsigned int)(unsigned __int16)v148 > v74 - 6 )
                          goto LABEL_323;
                        v149 = (IErrorInfo *)(v75 + 6);
                        v150 = __ROL2__(*((_WORD *)v75 + 1), 8);
                        v151 = v75;
                        v152 = 0;
                        v153 = __PAIR128__(v74, (unsigned __int64)v151);
                        break;
                      default:
                        goto LABEL_323;
                    }
                    pperrinfo[0] = (IErrorInfo *)v152;
                    pperrinfo[1] = v149;
                    *(_QWORD *)v276 = v148;
                    *(_OWORD *)&v276[8] = v153;
                    LOWORD(v277) = v150;
                    WORD1(v277) = v74;
                    WORD2(v277) = v84;
                    HIWORD(v277) = v21;
                    v280 = v246;
                    v203 = _mm_load_si128(&v244);
                    v279 = v245;
                    v278 = v203;
                    v177 = enum2__otls::gsub_gpos_shared::chaining::ChainingLookup_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                             pperrinfo,
                             &v284);
                    break;
                  default:
                    goto LABEL_323;
                }
LABEL_289:
                v20 = (__int64)v312;
                v11 = v309;
                v23 = 1;
                if ( v177 )
                  goto LABEL_324;
              }
              else
              {
                if ( v296 == 1792 )
                {
                  if ( v74 < 8 )
                    goto LABEL_323;
                  v81 = _byteswap_ulong(*((_DWORD *)v75 + 1));
                  v27 = v74 < v81;
                  v74 -= v81;
                  if ( v27 || v74 < 2 )
                    goto LABEL_323;
                  v82 = *((_WORD *)v75 + 1);
                  v76 = *(_WORD *)&v75[v81];
                  v75 += v81;
                  v83 = __ROL2__(v82, 8);
                  v77 = __ROL2__(v76, 8);
                }
                else
                {
                  v83 = v307;
                }
                v311 = v74;
                switch ( v83 )
                {
                  case 1u:
                    if ( v74 < 6 )
                      goto LABEL_323;
                    v88 = __ROL2__(v76, 8);
                    if ( v88 == 1 )
                    {
                      v91 = __ROL2__(*((_WORD *)v75 + 1), 8);
                      v89 = __ROL2__(*((_WORD *)v75 + 2), 8);
                      v90 = 0;
                      v92 = &v266;
                      v93 = &v254;
                      v94 = (__int64)v75;
                      v95 = (__int16 *)&v281;
                      v96 = (__int16 *)&v281 + 1;
                      v97 = (unsigned __int16 *)&v281 + 2;
                    }
                    else
                    {
                      if ( v88 != 2 )
                        goto LABEL_323;
                      v89 = __ROL2__(*((_WORD *)v75 + 2), 8);
                      if ( 2 * (unsigned int)v89 > v74 - 6 )
                        goto LABEL_323;
                      v90 = (IErrorInfo *)(v75 + 6);
                      v91 = __ROL2__(*((_WORD *)v75 + 1), 8);
                      v266.m128i_i64[0] = v89;
                      v92 = &v254;
                      v93 = (__m128i *)&v281;
                      v94 = (__int64)v75;
                      v95 = &v303;
                      v96 = &v295;
                      v97 = (unsigned __int16 *)&v301;
                    }
                    v92->m128i_i64[0] = v94;
                    v93->m128i_i64[0] = v311;
                    *v95 = v88;
                    *v96 = v91;
                    *v97 = v89;
                    pperrinfo[0] = v90;
                    pperrinfo[1] = (IErrorInfo *)v266.m128i_i64[0];
                    *(_QWORD *)v276 = v254.m128i_i64[0];
                    *(_QWORD *)&v276[8] = v281;
                    *(_WORD *)&v276[16] = v303;
                    *(_WORD *)&v276[18] = v295;
                    *(_WORD *)&v276[20] = v301;
                    enum2__otls::gsub::singlsub::SingleSubstLookup_::get_coverage_table(&v266, pperrinfo);
                    if ( v266.m128i_i32[0] == 1 )
                      goto LABEL_323;
                    v255 = *((_QWORD *)&v267 + 1);
                    v254 = _mm_loadu_si128((const __m128i *)&v266.m128i_u64[1]);
                    enum2__otls::coverage::Coverage_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                      &v254,
                      &v284);
                    goto LABEL_89;
                  case 2u:
                    if ( v74 < 6 )
                      goto LABEL_323;
                    if ( v76 != 256 )
                      goto LABEL_323;
                    if ( 2 * (unsigned int)(unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8) > v74 - 6 )
                      goto LABEL_323;
                    v108 = __ROL2__(*((_WORD *)v75 + 1), 8);
                    v27 = v74 < v108;
                    v109 = v74 - v108;
                    if ( v27 || v109 < 4 )
                      goto LABEL_323;
                    v110 = &v75[v108];
                    v111 = __ROL2__(*(_WORD *)v110, 8);
                    if ( v111 == 2 )
                    {
                      v154 = (IErrorInfo *)(unsigned __int16)__ROL2__(*((_WORD *)v110 + 1), 8);
                      if ( 3 * (unsigned __int64)(unsigned int)(2 * (_DWORD)v154) > v109 - 4 )
                        goto LABEL_323;
                      v114 = (IErrorInfo *)(v110 + 4);
                      v112 = (unsigned int)((_DWORD)v154 << 16) | 2LL;
                      v113 = v154;
                    }
                    else
                    {
                      if ( v111 != 1 )
                        goto LABEL_323;
                      v112 = (unsigned __int16)__ROL2__(*((_WORD *)v110 + 1), 8);
                      if ( 2 * (unsigned int)(unsigned __int16)v112 > v109 - 4 )
                        goto LABEL_323;
                      v113 = (IErrorInfo *)(v110 + 4);
                      v114 = 0;
                    }
LABEL_203:
                    pperrinfo[0] = v114;
                    pperrinfo[1] = v113;
                    *(_QWORD *)v276 = v112;
                    enum2__otls::coverage::Coverage_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                      pperrinfo,
                      &v284);
                    goto LABEL_89;
                  case 3u:
                    if ( v74 < 6 )
                      goto LABEL_323;
                    if ( v76 != 256 )
                      goto LABEL_323;
                    if ( 2 * (unsigned int)(unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8) > v74 - 6 )
                      goto LABEL_323;
                    v98 = __ROL2__(*((_WORD *)v75 + 1), 8);
                    v27 = v74 < v98;
                    v99 = v74 - v98;
                    if ( v27 || v99 < 4 )
                      goto LABEL_323;
                    v100 = &v75[v98];
                    v101 = __ROL2__(*(_WORD *)v100, 8);
                    if ( v101 == 2 )
                    {
                      v69 = (IErrorInfo *)(unsigned __int16)__ROL2__(*((_WORD *)v100 + 1), 8);
                      if ( 3 * (unsigned __int64)(unsigned int)(2 * (_DWORD)v69) > v99 - 4 )
                        goto LABEL_323;
                      v70 = (IErrorInfo *)(v100 + 4);
                      v71 = (unsigned int)((_DWORD)v69 << 16) | 2LL;
                      v72 = v69;
                    }
                    else
                    {
                      if ( v101 != 1 )
                        goto LABEL_323;
                      v71 = (unsigned __int16)__ROL2__(*((_WORD *)v100 + 1), 8);
                      if ( 2 * (unsigned int)(unsigned __int16)v71 > v99 - 4 )
                        goto LABEL_323;
                      v72 = (IErrorInfo *)(v100 + 4);
                      v70 = 0;
                    }
                    pperrinfo[0] = v70;
                    pperrinfo[1] = v72;
                    *(_QWORD *)v276 = v71;
                    JUMPOUT(0x18007E10ELL);
                  case 4u:
                    if ( v74 < 6 )
                      goto LABEL_323;
                    if ( v76 != 256 )
                      goto LABEL_323;
                    v250 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8);
                    if ( (unsigned int)(2 * v250) > v74 - 6 )
                      goto LABEL_323;
                    v264 = v75;
                    v131 = __ROL2__(*((_WORD *)v75 + 1), 8);
                    v132 = v74 - v131;
                    if ( v74 < v131 || v132 < 4 )
                      goto LABEL_323;
                    v133 = &v264[v131];
                    v134 = __ROL2__(*(_WORD *)v133, 8);
                    if ( v134 == 2 )
                    {
                      v54 = (unsigned __int16)__ROL2__(*((_WORD *)v133 + 1), 8);
                      if ( 3 * (unsigned __int64)(unsigned int)(2 * v54) > v132 - 4 )
                        goto LABEL_323;
                      v137 = (IErrorInfo *)(v133 + 4);
                      v135 = (unsigned int)((_DWORD)v54 << 16) | 2LL;
                      v136 = (IErrorInfo *)v54;
                    }
                    else
                    {
                      if ( v134 != 1 )
                        goto LABEL_323;
                      v135 = (unsigned __int16)__ROL2__(*((_WORD *)v133 + 1), 8);
                      v54 = 2 * (unsigned int)(unsigned __int16)v135;
                      if ( v54 > v132 - 4 )
                        goto LABEL_323;
                      v136 = (IErrorInfo *)(v133 + 4);
                      v137 = 0;
                    }
                    pperrinfo[0] = v137;
                    pperrinfo[1] = v136;
                    v155 = 0;
                    if ( !v137 )
                      v155 = &pperrinfo[1];
                    *(_QWORD *)v276 = v135;
                    v156 = v288;
                    v157 = v289;
                    v308 = v284;
                    v310 = v285;
                    v260 = v287;
                    v251 = v286;
                    v294 = 0;
                    v158 = v311;
                    v258 = v137;
LABEL_209:
                    while ( 2 )
                    {
                      while ( 2 )
                      {
                        while ( 2 )
                        {
                          if ( v137 )
                          {
                            if ( (IErrorInfo *)v155 >= pperrinfo[1] || v294 )
                              goto LABEL_89;
                            v159 = __ROL2__(*((_WORD *)&pperrinfo[0]->lpVtbl + 3 * (_QWORD)v155 + 1), 8);
                            v54 = (unsigned __int16)__ROL2__(
                                                      *((_WORD *)&pperrinfo[0]->lpVtbl + 3 * (_QWORD)v155 + 2),
                                                      8);
                            v155 = (IErrorInfo **)((char *)v155 + 1);
                            v294 = 0;
                          }
                          else
                          {
                            LOWORD(v21) = v294;
                            if ( v294 >= (unsigned __int64)v155[1] )
                              goto LABEL_89;
                            v159 = __ROL2__(*((_WORD *)&(*v155)->lpVtbl + v294), 8);
                            v54 = v294++;
                          }
                          BYTE1(v21) = HIBYTE(v159);
                          LOBYTE(v21) = v156 <= v159 && v157 >= v159;
                          if ( (_BYTE)v21 != 1 )
                            continue;
                          break;
                        }
                        v21 = v159 >> 5;
                        if ( v310 <= v21 )
                          core::panicking::panic_bounds_check(v159 >> 5, v310, &off_18033A710);
                        v265 = v159 >> 5;
                        v160 = *((_DWORD *)&v308->lpVtbl + v21);
                        v262 = v159 & 0x1F;
                        LODWORD(v21) = v160 >> (v159 & 0x1F);
                        if ( !(_DWORD)v21 || v54 >= v250 )
                          continue;
                        break;
                      }
                      v161 = __ROL2__(*(_WORD *)&v264[2 * v54 + 6], 8);
                      v27 = v158 < v161;
                      v162 = v158 - v161;
                      if ( !v27 && v162 >= 2 )
                      {
                        v163 = &v264[v161];
                        v164 = *(_WORD *)v163;
                        LOWORD(v21) = v162 - 2;
                        v54 = 2 * (unsigned int)(unsigned __int16)__ROL2__(*(_WORD *)v163, 8);
                        v291 = v54;
                        if ( v54 <= v162 - 2 )
                        {
                          v257 = v162;
                          v256 = v163;
                          v158 = v311;
                          if ( !v164 )
                            continue;
                          v165 = v256;
                          v166 = (unsigned __int16)__ROL2__(*((_WORD *)v256 + 1), 8);
                          v167 = v257;
                          if ( v257 >= v166 )
                          {
                            v291 += (unsigned __int64)v256;
                            v21 = (unsigned __int64)(v256 + 2);
                            v168 = 0;
                            v259 = (IErrorInfo *)v155;
                            while ( 1 )
                            {
                              v170 = v167 - v166;
                              if ( v170 < 4 )
                                goto LABEL_323;
                              v171 = *(_WORD *)((char *)v165 + v166 + 2);
                              if ( !v171 )
                                goto LABEL_323;
                              v172 = __ROL2__(v171, 8);
                              v173 = 2LL * v172 - 2;
                              if ( v173 > v170 - 4 )
                                goto LABEL_323;
                              if ( v172 == 1 )
                              {
                                LOBYTE(v168) = 1;
                                if ( v21 == v291 )
                                  goto LABEL_240;
                              }
                              else
                              {
                                v261 = v168;
                                v54 = (unsigned __int64)v165 + v166;
                                LOBYTE(v168) = 1;
                                v174 = 0;
                                do
                                {
                                  v175 = (unsigned __int16)__ROL2__(*(_WORD *)(v54 + v174 + 4), 8);
                                  if ( v156 <= (unsigned __int16)v175 && v157 >= (unsigned __int16)v175 )
                                  {
                                    v176 = v175 >> 5;
                                    if ( v310 <= v176 )
                                      core::panicking::panic_bounds_check(v175 >> 5, v310, &off_18033A710);
                                    LOBYTE(v175) = v168 & (*((_DWORD *)&v308->lpVtbl + v176) >> v175 != 0);
                                    v168 = v175;
                                  }
                                  else
                                  {
                                    v168 = 0;
                                  }
                                  v174 += 2;
                                }
                                while ( v173 != v174 );
                                LOBYTE(v168) = v261 | v168;
                                v137 = v258;
                                v155 = (IErrorInfo **)v259;
                                if ( v21 == v291 )
                                {
                                  v158 = v311;
                                  if ( (v168 & 1) != 0 )
                                  {
LABEL_240:
                                    if ( v260 <= v265 )
                                      core::panicking::panic_bounds_check(v265, v260, &off_18033A728);
                                    LODWORD(v54) = __ROL4__(-2, v262);
                                    *(_DWORD *)(v251 + 4 * v265) &= v54;
                                    v158 = v311;
                                    v137 = v258;
                                    v155 = (IErrorInfo **)v259;
                                  }
                                  goto LABEL_209;
                                }
                              }
                              v169 = __ROL2__(*(_WORD *)(v21 + 2), 8);
                              v21 += 2LL;
                              v166 = v169;
                              v167 = v257;
                              v165 = v256;
                              if ( v257 < v166 )
                                goto LABEL_323;
                            }
                          }
                        }
                      }
                      goto LABEL_323;
                    }
                  case 5u:
                    if ( v77 == 3 )
                    {
                      if ( v311 < 6 )
                        goto LABEL_323;
                      LOWORD(v297) = __ROL2__(*((_WORD *)v75 + 1), 8);
                      v204 = (unsigned __int16)v297;
                      v214 = 2 * (unsigned int)(unsigned __int16)v297;
                      if ( v311 - 6 < v214 )
                        goto LABEL_323;
                      HIWORD(v297) = __ROL2__(*((_WORD *)v75 + 2), 8);
                      v213 = HIWORD(v297);
                      if ( 4 * (unsigned int)HIWORD(v297) > v311 - 6 - v214 )
                        goto LABEL_323;
                      v205 = (IErrorInfo *)(v75 + 6);
                      v212 = (unsigned __int64)&v75[v214 + 6];
                      v206 = 2;
                      v252 = v311;
                      v298 = __ROL2__(v76, 8);
                      v292 = (unsigned __int64)v75;
                    }
                    else
                    {
                      if ( v77 == 2 )
                      {
                        if ( v311 < 8 )
                          goto LABEL_323;
                        v204 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 3), 8);
                        if ( (unsigned int)(2 * v204) > v311 - 8 )
                          goto LABEL_323;
                        v205 = (IErrorInfo *)(v75 + 8);
                        v211 = *((unsigned __int16 *)v75 + 2);
                        LOWORD(v211) = __ROL2__(v211, 8);
                        v292 = (unsigned int)(v211 << 16)
                             | (unsigned __int16)__ROL2__(*((_WORD *)v75 + 1), 8)
                             | v292 & 0xFFFFFFFF00000000uLL;
                        v206 = 1;
                      }
                      else
                      {
                        if ( v77 != 1 )
                          goto LABEL_323;
                        if ( v311 < 6 )
                          goto LABEL_323;
                        v204 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8);
                        if ( (unsigned int)(2 * v204) > v311 - 6 )
                          goto LABEL_323;
                        v205 = (IErrorInfo *)(v75 + 6);
                        v292 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 1), 8) | v292 & 0xFFFFFFFFFFFF0000uLL;
                        v206 = 0;
                      }
                      v212 = (unsigned __int64)v75;
                      v213 = v311;
                    }
                    pperrinfo[1] = v205;
                    *(_QWORD *)v276 = v204;
                    *(_QWORD *)&v276[8] = v212;
                    *(_QWORD *)&v276[16] = v213;
                    v277 = v292;
                    v278.m128i_i64[0] = v252;
                    v278.m128i_i16[4] = v298;
                    *(__int32 *)((char *)&v278.m128i_i32[2] + 2) = v297;
                    pperrinfo[0] = (IErrorInfo *)v206;
                    v177 = enum2__otls::gsub_gpos_shared::context::ContextLookup_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                             pperrinfo,
                             &v284);
                    goto LABEL_289;
                  case 6u:
                    if ( v74 < 4 )
                      goto LABEL_323;
                    v102 = __ROL2__(v76, 8);
                    switch ( v102 )
                    {
                      case 3:
                        otls::gsub_gpos_shared::chaining::ChainCoverageSubTable::parse(&v266, v75, v74);
                        v104 = (IErrorInfo *)v266.m128i_i64[0];
                        if ( !v266.m128i_i64[0] )
                          goto LABEL_323;
                        v103 = v266.m128i_i64[1];
                        v311 = *((_QWORD *)&v267 + 1);
                        v106 = (char *)v267;
                        v105 = v268;
                        LOWORD(v74) = v269;
                        LOWORD(v54) = v270;
                        LOWORD(v21) = v271;
                        v247 = _mm_loadu_si128(&v272);
                        v248 = v273;
                        v249 = v274;
                        v107 = 2;
                        break;
                      case 2:
                        if ( v74 < 0xC )
                          goto LABEL_323;
                        v103 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 5), 8);
                        if ( 2 * (unsigned int)(unsigned __int16)v103 > v74 - 12 )
                          goto LABEL_323;
                        v104 = (IErrorInfo *)(v75 + 12);
                        LOWORD(v21) = __ROL2__(*((_WORD *)v75 + 4), 8);
                        LOWORD(v54) = __ROL2__(*((_WORD *)v75 + 3), 8);
                        LOWORD(v74) = __ROL2__(*((_WORD *)v75 + 2), 8);
                        v105 = __ROL2__(*((_WORD *)v75 + 1), 8);
                        v106 = v75;
                        v107 = 1;
                        break;
                      case 1:
                        if ( v74 < 6 )
                          goto LABEL_323;
                        v103 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8);
                        if ( 2 * (unsigned int)(unsigned __int16)v103 > v74 - 6 )
                          goto LABEL_323;
                        v104 = (IErrorInfo *)(v75 + 6);
                        v105 = __ROL2__(*((_WORD *)v75 + 1), 8);
                        v106 = v75;
                        v107 = 0;
                        break;
                      default:
                        goto LABEL_323;
                    }
                    pperrinfo[0] = (IErrorInfo *)v107;
                    pperrinfo[1] = v104;
                    *(_QWORD *)v276 = v103;
                    *(_QWORD *)&v276[8] = v106;
                    *(_QWORD *)&v276[16] = v311;
                    LOWORD(v277) = v105;
                    WORD1(v277) = v74;
                    WORD2(v277) = v54;
                    HIWORD(v277) = v21;
                    v280 = v249;
                    v200 = _mm_load_si128(&v247);
                    v279 = v248;
                    v278 = v200;
                    v177 = enum2__otls::gsub_gpos_shared::chaining::ChainingLookup_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                             pperrinfo,
                             &v284);
                    goto LABEL_289;
                  case 8u:
                    if ( v74 < 6 )
                      goto LABEL_323;
                    if ( v76 != 256 )
                      goto LABEL_323;
                    v115 = *((unsigned __int16 *)v75 + 2);
                    v116 = (unsigned __int16)__ROL2__(*((_WORD *)v75 + 2), 8);
                    v117 = (unsigned int)(2 * v116);
                    v118 = v74 - 6 - v117;
                    if ( v74 - 6 < v117 )
                      goto LABEL_323;
                    if ( v118 < 2 )
                      goto LABEL_323;
                    v119 = v75 + 6;
                    LOWORD(v308) = *(_WORD *)&v75[v117 + 6];
                    v120 = v118 - 2;
                    v291 = (unsigned __int16)__ROL2__((_WORD)v308, 8);
                    v121 = (unsigned int)(2 * v291);
                    v27 = v120 < v121;
                    v122 = v120 - v121;
                    if ( v27 )
                      goto LABEL_323;
                    if ( v122 < 2 )
                      goto LABEL_323;
                    v294 = (unsigned __int64)v119 + v117 + 2;
                    if ( 2 * (unsigned int)(unsigned __int16)__ROL2__(*(_WORD *)(v294 + v121), 8) > v122 - 2 )
                      goto LABEL_323;
                    v123 = __ROL2__(*((_WORD *)v75 + 1), 8);
                    v124 = v74 - v123;
                    if ( v74 < v123 || v124 < 4 )
                      goto LABEL_323;
                    v125 = &v75[v123];
                    v126 = __ROL2__(*(_WORD *)v125, 8);
                    v310 = v116;
                    if ( v126 == 2 )
                    {
                      v181 = (IErrorInfo *)(unsigned __int16)__ROL2__(*((_WORD *)v125 + 1), 8);
                      if ( 3 * (unsigned __int64)(unsigned int)(2 * (_DWORD)v181) > v124 - 4 )
                        goto LABEL_323;
                      v128 = v75;
                      v130 = (IErrorInfo *)(v125 + 4);
                      v127 = (unsigned int)((_DWORD)v181 << 16) | 2LL;
                      v129 = v181;
                    }
                    else
                    {
                      if ( v126 != 1 )
                        goto LABEL_323;
                      v127 = (unsigned __int16)__ROL2__(*((_WORD *)v125 + 1), 8);
                      if ( 2 * (unsigned int)(unsigned __int16)v127 > v124 - 4 )
                        goto LABEL_323;
                      v128 = v75;
                      v129 = (IErrorInfo *)(v125 + 4);
                      v130 = 0;
                    }
                    pperrinfo[0] = v130;
                    pperrinfo[1] = v129;
                    *(_QWORD *)v276 = v127;
                    enum2__otls::coverage::Coverage_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                      pperrinfo,
                      &v284);
                    v182 = v311;
                    if ( (_WORD)v115 )
                    {
                      v310 = (unsigned __int64)&v119[v310];
                      while ( 1 )
                      {
                        v183 = __ROL2__(*v119, 8);
                        v27 = v182 < v183;
                        v184 = v182 - v183;
                        if ( v27 || v184 < 4 )
                          break;
                        v185 = &v128[v183];
                        v186 = __ROL2__(*(_WORD *)v185, 8);
                        if ( v186 == 2 )
                        {
                          v189 = __ROL2__(*((_WORD *)v185 + 1), 8);
                          if ( 3 * (unsigned __int64)(2 * (unsigned int)v189) > v184 - 4 )
                            break;
                          v115 = (v189 << 16) + (v115 & 0xFFFFFFFF00000000uLL) + 2;
                          v188 = (IErrorInfo *)(v185 + 4);
                          v187 = (IErrorInfo *)v189;
                        }
                        else
                        {
                          if ( v186 != 1 )
                            break;
                          v115 = (unsigned __int16)__ROL2__(*((_WORD *)v185 + 1), 8);
                          if ( (unsigned int)(2 * v115) > v184 - 4 )
                            break;
                          v187 = (IErrorInfo *)(v185 + 4);
                          v188 = 0;
                        }
                        pperrinfo[0] = v188;
                        pperrinfo[1] = v187;
                        *(_QWORD *)v276 = v115;
                        enum2__otls::coverage::Coverage_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                          pperrinfo,
                          &v284);
                        ++v119;
                        v182 = v311;
                        if ( v119 == (_WORD *)v310 )
                          goto LABEL_263;
                      }
LABEL_323:
                      v20 = (__int64)v312;
                      v11 = v309;
                      v23 = 1;
LABEL_324:
                      if ( !v313 && v290 != 0 )
                        sub_180022DE0(v263, v283);
                      goto LABEL_57;
                    }
LABEL_263:
                    v190 = (_WORD *)v294;
                    if ( (_WORD)v308 )
                    {
                      v310 = v294 + 2 * v291;
                      do
                      {
                        v191 = v190;
                        v192 = __ROL2__(*v190, 8);
                        v27 = v182 < v192;
                        v193 = v182 - v192;
                        if ( v27 || v193 < 4 )
                          goto LABEL_323;
                        v194 = &v128[v192];
                        v195 = __ROL2__(*(_WORD *)v194, 8);
                        if ( v195 == 2 )
                        {
                          v198 = __ROL2__(*((_WORD *)v194 + 1), 8);
                          if ( 3 * (unsigned __int64)(2 * (unsigned int)v198) > v193 - 4 )
                            goto LABEL_323;
                          v115 = (v198 << 16) + (v115 & 0xFFFFFFFF00000000uLL) + 2;
                          v197 = (IErrorInfo *)(v194 + 4);
                          v196 = (IErrorInfo *)v198;
                        }
                        else
                        {
                          if ( v195 != 1 )
                            goto LABEL_323;
                          v115 = (unsigned __int16)__ROL2__(*((_WORD *)v194 + 1), 8);
                          if ( (unsigned int)(2 * v115) > v193 - 4 )
                            goto LABEL_323;
                          v196 = (IErrorInfo *)(v194 + 4);
                          v197 = 0;
                        }
                        pperrinfo[0] = v197;
                        pperrinfo[1] = v196;
                        *(_QWORD *)v276 = v115;
                        enum2__otls::coverage::Coverage_::collect_complex_glyphs_otls::glyph_complexity::DWriteComplexGlyphSetSink_(
                          pperrinfo,
                          &v284);
                        v190 = v191 + 1;
                        v182 = v311;
                      }
                      while ( v191 + 1 != (_WORD *)v310 );
                    }
LABEL_89:
                    v20 = (__int64)v312;
                    v11 = v309;
                    v23 = 1;
                    break;
                  default:
                    goto LABEL_323;
                }
              }
            }
            v22 = v240;
            v27 = v59-- == 0;
          }
          while ( !v27 );
        }
LABEL_68:
        if ( !v313 && v290 != 0 )
          sub_180022DE0(v263, v283);
        if ( 2 * v230 )
        {
          v60 = lpMem;
          v61 = GetProcessHeap();
          HeapFree(v61, 0, v60);
        }
        goto LABEL_72;
      }
LABEL_57:
      if ( 2 * v230 )
      {
        v49 = lpMem;
        v50 = GetProcessHeap();
        HeapFree(v50, 0, v49);
      }
      if ( !v23 )
      {
LABEL_72:
        if ( v11 )
        {
          v62 = GetProcessHeap();
          HeapFree(v62, 0, (LPVOID)v20);
        }
        return 0;
      }
    }
    pperrinfo[0] = 0;
    GetErrorInfo(0, pperrinfo);
    v14 = pperrinfo[0];
    v15 = -2147483637;
    if ( v11 )
      goto LABEL_61;
  }
  else
  {
    pperrinfo[0] = 0;
    GetErrorInfo(0, pperrinfo);
    v14 = pperrinfo[0];
    v15 = -2147024809;
    if ( v11 )
    {
LABEL_61:
      v51 = v14;
      v52 = GetProcessHeap();
      HeapFree(v52, 0, (LPVOID)v20);
      v14 = v51;
    }
  }
LABEL_12:
  if ( v14 )
    ((void (__fastcall *)(IErrorInfo *))v14->lpVtbl->Release)(v14);
  return v15;
}

```

## disassembly

```asm
0x18007d900  push    rbp
0x18007d901  push    r15
0x18007d903  push    r14
0x18007d905  push    r13
0x18007d907  push    r12
0x18007d909  push    rsi
0x18007d90a  push    rdi
0x18007d90b  push    rbx
0x18007d90c  sub     rsp, 418h
0x18007d913  lea     rbp, [rsp+80h]
0x18007d91b  movaps  [rbp+3D0h+var_50], xmm7
0x18007d922  movaps  [rbp+3D0h+var_60], xmm6
0x18007d929  mov     [rbp+3D0h+var_70], 0FFFFFFFFFFFFFFFEh
0x18007d934  test    rcx, rcx
0x18007d937  jz      loc_18007DF9B
0x18007d93d  cmp     r8d, 42555347h
0x18007d944  jz      short loc_18007D954
0x18007d946  cmp     r8d, 534F5047h
0x18007d94d  jnz     short loc_18007D9BB
0x18007d94f  mov     r15b, 1
0x18007d952  jmp     short loc_18007D957
0x18007d954  xor     r15d, r15d
0x18007d957  mov     r8, [rbp+3D0h+arg_38]
0x18007d95e  mov     eax, [rbp+3D0h+arg_30]
0x18007d964  shl     r8, 5
0x18007d968  cmp     r8, rax
0x18007d96b  jbe     loc_18007FA2C
0x18007d971  test    r9, r9
0x18007d974  jz      short loc_18007D9BB
0x18007d976  mov     r13, [rbp+3D0h+arg_20]
0x18007d97d  lea     rsi, ds:0[r13*4]
0x18007d985  mov     rax, r13
0x18007d988  shr     rax, 3Eh
0x18007d98c  setnz   al
0x18007d98f  mov     r8, 7FFFFFFFFFFFFFFCh
0x18007d999  cmp     rsi, r8
0x18007d99c  setnbe  r8b
0x18007d9a0  or      r8b, al
0x18007d9a3  jz      short loc_18007D9FC
0x18007d9a5  xor     ecx, ecx
0x18007d9a7  lea     r8, off_180348EC0; "D:\\os\\tools\\Rust\\vpack\\rust.tools"...
0x18007d9ae  mov     rdx, rsi
0x18007d9b1  call    alloc__raw_vec__handle_error
0x18007d9b6  jmp     loc_18007FC5F
0x18007d9bb  mov     [rbp+3D0h+pperrinfo], 0
0x18007d9c6  lea     rdx, [rbp+3D0h+pperrinfo]; pperrinfo
0x18007d9cd  xor     ecx, ecx; dwReserved
0x18007d9cf  call    cs:__imp_GetErrorInfo
0x18007d9d5  mov     rcx, [rbp+3D0h+pperrinfo]
0x18007d9dc  mov     esi, 80070057h
0x18007d9e1  test    rcx, rcx
0x18007d9e4  jz      loc_18007DF9D
0x18007d9ea  mov     rax, [rcx]
0x18007d9ed  mov     rax, [rax+10h]
0x18007d9f1  call    cs:__guard_dispatch_icall_fptr
0x18007d9f7  jmp     loc_18007DF9D
0x18007d9fc  mov     rbx, rcx
0x18007d9ff  mov     rdi, rdx
0x18007da02  test    rsi, rsi
0x18007da05  jz      short loc_18007DA25
0x18007da07  mov     r14, r9
0x18007da0a  xor     ecx, ecx
0x18007da0c  mov     rdx, rsi
0x18007da0f  call    std__sys__alloc__windows__process_heap_alloc
0x18007da14  test    rax, rax
0x18007da17  jz      loc_18007FC0B
0x18007da1d  mov     r12, rax
0x18007da20  mov     r9, r14
0x18007da23  jmp     short loc_18007DA2E
0x18007da25  mov     r12d, 4
0x18007da2b  xor     r13d, r13d
0x18007da2e  mov     rcx, r12; void *
0x18007da31  mov     rdx, r9; Src
0x18007da34  mov     r8, rsi; Size
0x18007da37  call    memcpy_0
0x18007da3c  cmp     [rbp+3D0h+arg_40], 0
0x18007da44  jz      loc_18007DD47
0x18007da4a  cmp     [rbp+3D0h+arg_48], 0
0x18007da52  jz      loc_18007DD47
0x18007da58  mov     r14, 8000000000000001h
0x18007da62  lea     rcx, [rbp+3D0h+pperrinfo]
0x18007da69  mov     rdx, rbx
0x18007da6c  mov     r8, rdi
0x18007da6f  test    r15b, r15b
0x18007da72  call    otls__gpos__GPosHeader__new
0x18007da77  cmp     [rbp+3D0h+pperrinfo], r14
0x18007da7e  jz      loc_18007DDFD
0x18007da84  lea     rcx, [rbp+3D0h+var_428]; void *
0x18007da88  lea     rdx, [rbp+3D0h+pperrinfo]; Src
0x18007da8f  mov     r8d, 0C8h; Size
0x18007da95  call    memcpy_0
0x18007da9a  mov     rdx, [rbp+3D0h+var_3A8]
0x18007da9e  test    rdx, rdx
0x18007daa1  jz      loc_18007DD7B
0x18007daa7  mov     rcx, [rbp+3D0h+var_3F8]
0x18007daab  xor     r14d, r14d
0x18007daae  test    rcx, rcx
0x18007dab1  jz      loc_18007DDD0
0x18007dab7  cmp     [rbp+3D0h+var_3B8], 0
0x18007dabc  jz      loc_18007DDD0
0x18007dac2  movups  xmm6, cs:xmmword_180342F40
0x18007dac9  movaps  [rbp+3D0h+var_220], xmm6
0x18007dad0  movups  xmm7, xmmword ptr cs:off_180342F30
0x18007dad7  movaps  xmmword ptr [rbp+3D0h+pperrinfo], xmm7
0x18007dade  mov     rax, [rbp+3D0h+var_3C0]
0x18007dae2  test    rax, rax
0x18007dae5  jz      loc_18007DE4B
0x18007daeb  mov     [rbp+3D0h+var_108], rcx
0x18007daf2  mov     [rbp+3D0h+var_140], rdx
0x18007daf9  mov     [rbp+3D0h+var_CC], r15d
0x18007db00  mov     [rbp+3D0h+var_98], r13
0x18007db07  mov     [rbp+3D0h+var_80], r12
0x18007db0e  mov     rcx, [rbp+3D0h+var_3C8]
0x18007db12  lea     rax, [rax+rax*2]
0x18007db16  lea     rax, [rcx+rax*2]
0x18007db1a  mov     [rbp+3D0h+var_B0], rax
0x18007db21  mov     rax, [rbp+3D0h+var_3D8]
0x18007db25  mov     [rbp+3D0h+var_C0], rax
0x18007db2c  mov     r13, [rbp+3D0h+var_3D0]
0x18007db30  lea     rdi, [rbp+3D0h+pperrinfo]
0x18007db37  mov     [rbp+3D0h+var_B8], r13
0x18007db3e  mov     [rbp+3D0h+var_A0], rcx
0x18007db45  movzx   eax, word ptr [rcx+4]
0x18007db49  rol     ax, 8
0x18007db4d  movzx   ebx, ax
0x18007db50  sub     r13, rbx
0x18007db53  jb      loc_18007DD80
0x18007db59  cmp     r13, 2
0x18007db5d  jb      loc_18007DD80
0x18007db63  mov     rax, r13
0x18007db66  and     rax, 0FFFFFFFFFFFFFFFEh
0x18007db6a  cmp     rax, 2
0x18007db6e  jz      loc_18007DD80
0x18007db74  add     rbx, [rbp+3D0h+var_C0]
0x18007db7b  lea     rax, [r13-4]
0x18007db7f  movzx   ecx, word ptr [rbx+2]
0x18007db83  rol     cx, 8
0x18007db87  mov     word ptr [rbp+3D0h+var_90], cx
0x18007db8e  movzx   ecx, cx
0x18007db91  add     ecx, ecx
0x18007db93  lea     rcx, [rcx+rcx*2]
0x18007db97  cmp     rcx, rax
0x18007db9a  ja      loc_18007DD80
0x18007dba0  movzx   eax, word ptr [rbx]
0x18007dba3  test    ax, ax
0x18007dba6  jz      short loc_18007DC12
0x18007dba8  rol     ax, 8
0x18007dbac  movzx   r15d, ax
0x18007dbb0  mov     rax, r13
0x18007dbb3  sub     rax, r15
0x18007dbb6  jb      loc_18007DD80
0x18007dbbc  cmp     rax, 6
0x18007dbc0  jb      loc_18007DD80
0x18007dbc6  add     r15, rbx
0x18007dbc9  movzx   ecx, word ptr [r15+4]
0x18007dbce  rol     cx, 8
0x18007dbd2  movzx   ecx, cx
0x18007dbd5  add     rax, 0FFFFFFFFFFFFFFFAh
0x18007dbd9  lea     edx, [rcx+rcx]
0x18007dbdc  cmp     rdx, rax
0x18007dbdf  ja      loc_18007DD80
0x18007dbe5  test    rcx, rcx
0x18007dbe8  jz      short loc_18007DC12
0x18007dbea  lea     r12, [r15+rcx*2]
0x18007dbee  add     r12, 6
0x18007dbf2  add     r15, 6
0x18007dbf6  movzx   eax, word ptr [r15]
0x18007dbfa  rol     ax, 8
0x18007dbfe  movzx   edx, ax
0x18007dc01  mov     rcx, rdi
0x18007dc04  call    hashbrown__map__HashMap_usize_tuple$___bcrypt_workaround__HasherState_alloc__alloc__Global___insert_usize_tuple$___bcrypt_workaround__HasherState_alloc__alloc__Global_
0x18007dc09  add     r15, 2
0x18007dc0d  cmp     r15, r12
0x18007dc10  jnz     short loc_18007DBF6
0x18007dc12  add     [rbp+3D0h+var_A0], 6
0x18007dc1a  xor     r12d, r12d
0x18007dc1d  cmp     r12w, word ptr [rbp+3D0h+var_90]
0x18007dc25  jnb     loc_18007DCB1
0x18007dc2b  movzx   eax, r12w
0x18007dc2f  lea     rax, [rax+rax*2]
0x18007dc33  movzx   eax, word ptr [rbx+rax*2+8]
0x18007dc38  rol     ax, 8
0x18007dc3c  movzx   r15d, ax
0x18007dc40  mov     rax, r13
0x18007dc43  sub     rax, r15
0x18007dc46  jb      loc_18007DD80
0x18007dc4c  cmp     rax, 6
0x18007dc50  jb      loc_18007DD80
0x18007dc56  add     r15, rbx
0x18007dc59  movzx   ecx, word ptr [r15+4]
0x18007dc5e  rol     cx, 8
0x18007dc62  movzx   ecx, cx
0x18007dc65  add     rax, 0FFFFFFFFFFFFFFFAh
0x18007dc69  lea     edx, [rcx+rcx]
0x18007dc6c  cmp     rdx, rax
0x18007dc6f  ja      loc_18007DD80
0x18007dc75  inc     r12d
0x18007dc78  test    rcx, rcx
0x18007dc7b  jz      short loc_18007DC1D
0x18007dc7d  lea     r14, [r15+rcx*2]
0x18007dc81  add     r14, 6
0x18007dc85  add     r15, 6
0x18007dc89  nop     dword ptr [rax+00000000h]
0x18007dc90  movzx   eax, word ptr [r15]
0x18007dc94  rol     ax, 8
0x18007dc98  movzx   edx, ax
0x18007dc9b  mov     rcx, rdi
0x18007dc9e  call    hashbrown__map__HashMap_usize_tuple$___bcrypt_workaround__HasherState_alloc__alloc__Global___insert_usize_tuple$___bcrypt_workaround__HasherState_alloc__alloc__Global_
0x18007dca3  add     r15, 2
0x18007dca7  cmp     r15, r14
0x18007dcaa  jnz     short loc_18007DC90
0x18007dcac  jmp     loc_18007DC1D
0x18007dcb1  mov     rcx, [rbp+3D0h+var_A0]
0x18007dcb8  cmp     rcx, [rbp+3D0h+var_B0]
0x18007dcbf  mov     r13, [rbp+3D0h+var_B8]
0x18007dcc6  jnz     loc_18007DB3E
0x18007dccc  mov     rbx, [rbp+3D0h+pperrinfo]
0x18007dcd3  test    rbx, rbx
0x18007dcd6  jz      loc_18007FBA1
0x18007dcdc  mov     rax, [rbp+3D0h+pperrinfo+8]
0x18007dce3  mov     r15, qword ptr [rbp+3D0h+var_220+8]
0x18007dcea  movaps  [rbp+3D0h+var_270], xmm6
0x18007dcf1  movaps  [rbp+3D0h+var_280], xmm7
0x18007dcf8  mov     [rbp+3D0h+var_A0], rax
0x18007dcff  test    rax, rax
0x18007dd02  jz      loc_18007FA49
0x18007dd08  mov     rcx, [rbp+3D0h+var_A0]
0x18007dd0f  lea     rax, ds:17h[rcx*8]
0x18007dd17  and     rax, 0FFFFFFFFFFFFFFF0h
0x18007dd1b  add     rcx, rax
0x18007dd1e  mov     rdx, rbx
0x18007dd21  sub     rdx, rax
0x18007dd24  mov     [rbp+3D0h+var_B8], rdx
0x18007dd2b  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x18007dd2f  setz    byte ptr [rbp+3D0h+var_C0]
0x18007dd36  mov     eax, 10h
0x18007dd3b  mov     [rbp+3D0h+var_B0], rax
0x18007dd42  jmp     loc_18007FA54
0x18007dd47  mov     [rbp+3D0h+pperrinfo], 0
0x18007dd52  lea     rdx, [rbp+3D0h+pperrinfo]; pperrinfo
0x18007dd59  xor     ecx, ecx; dwReserved
0x18007dd5b  call    cs:__imp_GetErrorInfo
0x18007dd61  mov     rcx, [rbp+3D0h+pperrinfo]
0x18007dd68  mov     esi, 80070057h
0x18007dd6d  test    r13, r13
0x18007dd70  jnz     loc_18007DE2C
0x18007dd76  jmp     loc_18007D9E1
0x18007dd7b  xor     r14d, r14d
0x18007dd7e  jmp     short loc_18007DDD0
0x18007dd80  mov     rcx, [rbp+3D0h+pperrinfo+8]
0x18007dd87  test    rcx, rcx
0x18007dd8a  jz      short loc_18007DDBF
0x18007dd8c  lea     rax, ds:17h[rcx*8]
0x18007dd94  and     rax, 0FFFFFFFFFFFFFFF0h
0x18007dd98  add     rcx, rax
0x18007dd9b  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x18007dd9f  jz      short loc_18007DDBF
0x18007dda1  mov     rsi, [rbp+3D0h+pperrinfo]
0x18007dda8  sub     rsi, rax
0x18007ddab  call    cs:__imp_GetProcessHeap
0x18007ddb1  mov     rcx, rax; hHeap
0x18007ddb4  xor     edx, edx; dwFlags
0x18007ddb6  mov     r8, rsi; lpMem
0x18007ddb9  call    cs:__imp_HeapFree
0x18007ddbf  mov     r14b, 1
0x18007ddc2  mov     r12, [rbp+3D0h+var_80]
0x18007ddc9  mov     r13, [rbp+3D0h+var_98]
0x18007ddd0  mov     rax, [rbp+3D0h+var_428]
0x18007ddd4  shl     rax, 1
0x18007ddd7  test    rax, rax
0x18007ddda  jz      short loc_18007DDF4
0x18007dddc  mov     rsi, [rbp+3D0h+lpMem]
0x18007dde0  call    cs:__imp_GetProcessHeap
0x18007dde6  mov     rcx, rax; hHeap
0x18007dde9  xor     edx, edx; dwFlags
0x18007ddeb  mov     r8, rsi; lpMem
0x18007ddee  call    cs:__imp_HeapFree
0x18007ddf4  test    r14b, r14b
0x18007ddf7  jz      loc_18007DF82
0x18007ddfd  mov     [rbp+3D0h+pperrinfo], 0
0x18007de08  lea     rdx, [rbp+3D0h+pperrinfo]; pperrinfo
0x18007de0f  xor     ecx, ecx; dwReserved
0x18007de11  call    cs:__imp_GetErrorInfo
0x18007de17  mov     rcx, [rbp+3D0h+pperrinfo]
0x18007de1e  mov     esi, 8000000Bh
0x18007de23  test    r13, r13
0x18007de26  jz      loc_18007D9E1
0x18007de2c  mov     rdi, rcx
0x18007de2f  call    cs:__imp_GetProcessHeap
0x18007de35  mov     rcx, rax; hHeap
0x18007de38  xor     edx, edx; dwFlags
0x18007de3a  mov     r8, r12; lpMem
0x18007de3d  call    cs:__imp_HeapFree
0x18007de43  mov     rcx, rdi
0x18007de46  jmp     loc_18007D9E1
0x18007de4b  movaps  [rbp+3D0h+var_270], xmm6
0x18007de52  movaps  [rbp+3D0h+var_280], xmm7
0x18007de59  mov     rbx, qword ptr [rbp+3D0h+var_280]
0x18007de60  mov     r14b, 1
0x18007de63  test    rbx, rbx
  ... truncated ...
```
