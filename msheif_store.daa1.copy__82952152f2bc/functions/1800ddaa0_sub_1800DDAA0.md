# sub_1800DDAA0

- ea: `0x1800ddaa0`
- end: `0x1800dfa0f`
- name: `sub_1800DDAA0`
- size: `8047`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `32`
- tags: `broker_com_uri`

## callees

- `0x180001228`
- `0x1800012f8`
- `0x180002d00`
- `0x180059ab4`
- `0x180059cbc`
- `0x180059eac`
- `0x18005ae04`
- `0x18005b17c`
- `0x18005b28c`
- `0x18005c374`
- `0x180070474`
- `0x180079880`
- `0x180085e04`
- `0x180088760`
- `0x180088ab8`
- `0x1800dd10c`
- `0x1800ddaa0`
- `0x1800dfa18`
- `0x1800dfcb4`
- `0x1800dff4c`
- `0x1800e0c94`
- `0x1800e1284`
- `0x1800e1cd0`
- `0x1800e29e0`
- `0x1800e2f50`
- `0x1800e5384`
- `0x1800e7990`
- `0x1800ebe44`
- `0x1800ed83c`
- `0x180207168`
- `0x1802b69b0`
- `0x1802b9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df9d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df9d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ddad8`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800df00b`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800df00b`
- `MFPlat!MFGetSystemTime` at `0x1800ddae4`
- `MFPlat!MFGetSystemTime` at `0x1800df828`
- `MFPlat!MFGetSystemTime` at `0x1800ddae4`
- `MFPlat!MFGetSystemTime` at `0x1800df828`

## string_xrefs

- `0x1800ddaf0`: `CWICHeifEncoderFrame::Commit`
- `0x1800ddb74`: `CWICHeifEncoderFrame::Commit`
- `0x1800ddd4b`: `CWICHeifEncoderFrame::Commit`
- `0x1800de13c`: `CWICHeifEncoderFrame::Commit`
- `0x1800de2a8`: `CWICHeifEncoderFrame::Commit`
- `0x1800de384`: `CWICHeifEncoderFrame::Commit`
- `0x1800de463`: `CWICHeifEncoderFrame::Commit`
- `0x1800de520`: `CWICHeifEncoderFrame::Commit`
- `0x1800de6d1`: `CWICHeifEncoderFrame::Commit`
- `0x1800dee13`: `CWICHeifEncoderFrame::Commit`
- `0x1800df092`: `CWICHeifEncoderFrame::Commit`
- `0x1800df487`: `CWICHeifEncoderFrame::Commit`
- `0x1800df744`: `CWICHeifEncoderFrame::Commit`
- `0x1800df7d9`: `CWICHeifEncoderFrame::Commit`
- `0x1800df941`: `CWICHeifEncoderFrame::Commit`

## pseudocode

```c
__int64 __fastcall sub_1800DDAA0(__int64 a1)
{
  MFTIME v2; // r12
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // r14d
  __int64 v7; // rsi
  int v8; // ebx
  __int128 v9; // xmm0
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  bool v13; // zf
  char v14; // r13
  __int128 *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rbx
  __int64 v20; // rdx
  HRESULT v21; // ebx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  __int64 v25; // rax
  IMFMediaBuffer *v26; // rbx
  _QWORD *v27; // r12
  HRESULT (__stdcall *Lock)(IMFMediaBuffer *, BYTE **, DWORD *, DWORD *); // rsi
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  _BYTE *v40; // rsi
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  __int64 *v45; // r12
  __int64 v46; // r13
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // r9
  __int64 v53; // r8
  __int64 *v54; // rcx
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 *v59; // rcx
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rsi
  __int64 (__fastcall *v63)(__int64, __int64, __int64); // rbx
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 *v67; // rcx
  __int64 v68; // rsi
  __int64 (__fastcall *v69)(__int64, IMFMediaBuffer **); // rbx
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 *v73; // rcx
  __int64 v74; // rax
  _QWORD *v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 *v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 *v85; // rcx
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 *v90; // rcx
  __int64 v91; // rax
  __int64 v92; // r8
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 *v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 *v100; // rcx
  __int64 v101; // rax
  __int64 v102; // r8
  __int64 v103; // rcx
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 *v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // r9
  __int64 *v111; // rcx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  int v115; // r9d
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 *v119; // rcx
  __int64 v120; // rdx
  __int64 v121; // r8
  __int64 v122; // r9
  __int64 *v123; // rcx
  __int64 v124; // rdx
  __int64 v125; // r8
  __int64 v126; // r9
  __int64 *v127; // rcx
  __int64 v128; // rdx
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 *v131; // rcx
  __int64 v132; // rdx
  __int64 v133; // r8
  __int64 v134; // r9
  __int64 *v135; // rcx
  __int64 v136; // rdx
  __int64 v137; // r8
  __int64 v138; // r9
  __int64 *v139; // rcx
  __int64 v140; // r8
  __int64 v141; // rdx
  __int64 v142; // rdx
  __int64 v143; // r8
  __int64 v144; // r9
  __int64 *v145; // rcx
  int v146; // r12d
  __int64 v147; // rdx
  __int64 v148; // r8
  __int64 v149; // r9
  __int64 *v150; // rcx
  __int64 v151; // rsi
  __int64 (__fastcall *v152)(__int64, IMFMediaBuffer **); // rbx
  __int64 v153; // rdx
  __int64 v154; // r8
  __int64 v155; // r9
  __int64 *v156; // rcx
  __int64 v157; // rax
  __int64 v158; // r8
  int v159; // ebx
  int v160; // eax
  __int64 v161; // rdx
  __int64 v162; // r8
  __int64 v163; // r9
  __int64 *v164; // rcx
  __int64 v165; // rcx
  __int64 v166; // rdx
  __int64 v167; // r8
  __int64 v168; // r9
  __int64 *v169; // rcx
  __int64 v170; // rdx
  __int64 v171; // r8
  __int64 v172; // r9
  __int64 *v173; // rcx
  __int64 v174; // rax
  __int64 v175; // r8
  __int64 v176; // rdx
  __int64 v177; // r8
  __int64 v178; // r9
  __int64 *v179; // rcx
  __int64 v180; // rdx
  __int64 v181; // r8
  __int64 v182; // r9
  __int64 *v183; // rcx
  __int64 v184; // rdx
  __int64 v185; // r8
  __int64 v186; // r9
  __int64 *v187; // rcx
  __int64 v188; // rdx
  __int64 v189; // r8
  __int64 v190; // r9
  __int64 *v191; // rcx
  __int64 v192; // rdx
  __int64 v193; // r8
  __int64 v194; // r9
  __int64 *v195; // rcx
  __int64 v196; // rsi
  __int64 (__fastcall *v197)(__int64, IMFMediaBuffer **); // rbx
  __int64 v198; // rdx
  __int64 v199; // r8
  __int64 v200; // r9
  __int64 *v201; // rcx
  __int64 v202; // rax
  __int64 v203; // r8
  __int64 v204; // rdx
  __int64 v205; // r8
  __int64 v206; // r9
  __int64 *v207; // rcx
  unsigned int v208; // r13d
  __int64 v209; // rsi
  __int64 (__fastcall *v210)(__int64, _QWORD, __int64 *); // rbx
  __int64 v211; // rdx
  __int64 v212; // r8
  __int64 v213; // r9
  __int64 v214; // rdx
  __int64 v215; // r8
  __int64 v216; // r9
  __int64 v217; // rdx
  __int64 v218; // r8
  __int64 v219; // r9
  __int64 *v220; // rcx
  __int64 *v221; // rcx
  __int64 v222; // rax
  __int64 v223; // r8
  __int64 *v224; // rcx
  __int64 *v225; // rcx
  MFTIME v226; // rax
  __int64 v227; // r8
  __int64 v228; // rcx
  MFTIME v229; // rsi
  __int64 v230; // rcx
  __int64 v231; // r9
  GUID *v232; // rax
  __int64 v233; // rcx
  int v234; // r8d
  int v235; // r9d
  __int64 v236; // rax
  int v237; // ecx
  IMFMediaBuffer *ppBuffer; // [rsp+78h] [rbp-90h] BYREF
  __int64 v240; // [rsp+80h] [rbp-88h] BYREF
  MFTIME v241; // [rsp+88h] [rbp-80h] BYREF
  char v242; // [rsp+90h] [rbp-78h]
  _BYTE v243[7]; // [rsp+91h] [rbp-77h] BYREF
  DWORD cbMaxLength[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v245; // [rsp+A0h] [rbp-68h] BYREF
  char v246[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v247; // [rsp+B0h] [rbp-58h] BYREF
  char v248[8]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v249; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v250; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v251[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v252; // [rsp+E0h] [rbp-28h]
  __int128 v253; // [rsp+E8h] [rbp-20h] BYREF
  GUID v254; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v255; // [rsp+108h] [rbp+0h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v241 = MFGetSystemTime();
  v2 = v241;
  sub_180059AB4(v243, "CWICHeifEncoderFrame::Commit", 755);
  v6 = 0;
  if ( *(_BYTE *)(qword_180685260 + 8) && *(_QWORD *)(a1 + 192) )
  {
    v7 = sub_18005AE04(qword_180685260, v3, v4, v5);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 192) + 296LL))(*(_QWORD *)(a1 + 192));
    v9 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)(a1 + 192) + 280LL))(
                      *(_QWORD *)(a1 + 192),
                      &v254);
    *(_DWORD *)(v7 + 2016) = v8;
    *(_OWORD *)(v7 + 2000) = v9;
  }
  v251[0] = "CWICHeifEncoderFrame::Commit";
  v252 = 15;
  v251[1] = 0;
  sub_18005B28C(0, 15, "=>%s", "CWICHeifEncoderFrame::Commit");
  v13 = *(_DWORD *)(a1 + 480) == 2;
  v14 = 0;
  v240 = 0;
  v250 = 0;
  v242 = 0;
  if ( !v13 )
  {
    v21 = -2003292412;
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 89, qword_1805D7080, 0, -2003292412);
    }
    v225 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v225 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v225 + 8) )
      goto LABEL_447;
    v51 = sub_18005AE04(v225, v10, v11, v12);
    if ( *(_DWORD *)(v51 + 1996) == -2003292412 )
      goto LABEL_447;
    v53 = 760;
LABEL_445:
    v52 = 2291674884LL;
    goto LABEL_446;
  }
  *(_DWORD *)(a1 + 480) = 3;
  v15 = (__int128 *)sub_1800E29E0(a1);
  v19 = *(_QWORD *)(a1 + 176);
  v255 = *v15;
  if ( *(_BYTE *)(v19 + 236) )
  {
    v245 = 0;
    ppBuffer = 0;
    sub_18005B17C(&ppBuffer);
    v21 = sub_1800E2F50(v19, &ppBuffer);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 90, qword_1805D7080, 0, v21);
      }
      v24 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v24 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v25 = sub_18005AE04(v24, v20, v22, v23);
        if ( *(_DWORD *)(v25 + 1996) != v21 )
          sub_180207168(v25, "CWICHeifEncoderFrame::Commit", 772, (unsigned int)v21);
      }
      sub_18005B17C(&ppBuffer);
      sub_18005B17C(&v245);
      goto LABEL_447;
    }
    v26 = ppBuffer;
    v27 = (_QWORD *)(a1 + 208);
    Lock = ppBuffer->lpVtbl->Lock;
    sub_18005B17C(a1 + 208);
    v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64))Lock)(v26, a1 + 208);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 91, qword_1805D7080, 0, v21);
      }
      v32 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v32 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v32 + 8) )
        goto LABEL_28;
      v33 = sub_18005AE04(v32, v29, v30, v31);
      if ( *(_DWORD *)(v33 + 1996) == v21 )
        goto LABEL_28;
      v34 = 773;
LABEL_27:
      sub_180207168(v33, "CWICHeifEncoderFrame::Commit", v34, (unsigned int)v21);
LABEL_28:
      sub_18005B17C(&ppBuffer);
      sub_18005B17C(&v245);
LABEL_29:
      sub_18005B17C(&v240);
      v2 = v241;
      goto LABEL_448;
    }
    if ( !*(_DWORD *)(a1 + 476) )
    {
      v35 = *v27;
      v248[0] = 0;
      v253 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, __int128 *, char *))(*(_QWORD *)v35 + 48LL))(v35, &v253, v248);
      if ( v21 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 92, qword_1805D7080, 0, v21);
        }
        v39 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v39 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v39 + 8) )
          goto LABEL_28;
        v33 = sub_18005AE04(v39, v36, v37, v38);
        if ( *(_DWORD *)(v33 + 1996) == v21 )
          goto LABEL_28;
        v34 = 783;
        goto LABEL_27;
      }
      if ( !(unsigned int)sub_1802B69B0(&v253, "HEVC", 16) || !(unsigned int)sub_1802B69B0(&v253, "AV01", 16) )
        v255 = v253;
    }
    v40 = (_BYTE *)(a1 + 448);
    if ( *(_BYTE *)(a1 + 448) )
    {
      v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->GetMaxLength)(ppBuffer, *v27);
      if ( v21 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 93, qword_1805D7080, 0, v21);
        }
        v44 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v44 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v44 + 8) )
          goto LABEL_28;
        v33 = sub_18005AE04(v44, v41, v42, v43);
        if ( *(_DWORD *)(v33 + 1996) == v21 )
          goto LABEL_28;
        v34 = 796;
        goto LABEL_27;
      }
    }
    sub_18005B17C(&ppBuffer);
    sub_18005B17C(&v245);
    goto LABEL_56;
  }
  v40 = (_BYTE *)(a1 + 448);
  if ( *(_BYTE *)(a1 + 448) )
    goto LABEL_81;
  if ( *(_QWORD *)(a1 + 512) )
  {
LABEL_56:
    if ( !*v40 )
    {
      if ( !*(_QWORD *)(a1 + 512) )
        goto LABEL_174;
      v45 = (__int64 *)(a1 + 512);
      v46 = a1 + 512;
      goto LABEL_82;
    }
LABEL_81:
    v45 = (__int64 *)(a1 + 512);
    v46 = a1 + 512;
    if ( !*(_QWORD *)(a1 + 512) )
    {
      sub_18005B17C(a1 + 208);
      v21 = sub_1800E1CD0(
              a1,
              *(_QWORD *)(a1 + 200),
              *(_DWORD *)(a1 + 224),
              *(_DWORD *)(a1 + 228),
              (__int64)&v255,
              (__int64)v40,
              a1 + 208);
      if ( v21 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 103, qword_1805D7080, 0, v21);
        }
        v100 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v100 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v100 + 8) )
          goto LABEL_29;
        v101 = sub_18005AE04(v100, v97, v98, v99);
        if ( *(_DWORD *)(v101 + 1996) == v21 )
          goto LABEL_29;
        v102 = 850;
        goto LABEL_172;
      }
      sub_180070474(a1 + 200);
      *(_QWORD *)(a1 + 440) = 0;
      v14 = 0;
LABEL_174:
      v103 = *(_QWORD *)(a1 + 232);
      if ( v103 )
      {
        LODWORD(v247) = 0;
        cbMaxLength[0] = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, __int64 *, DWORD *))(*(_QWORD *)v103 + 24LL))(
                v103,
                &v247,
                cbMaxLength);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 104, qword_1805D7080, 0, v21);
          }
          v107 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v107 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v107 + 8) )
            goto LABEL_29;
          v101 = sub_18005AE04(v107, v104, v105, v106);
          if ( *(_DWORD *)(v101 + 1996) == v21 )
            goto LABEL_29;
          v102 = 860;
          goto LABEL_172;
        }
        v21 = sub_1800DD10C(a1, (unsigned int)v247, cbMaxLength[0]);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 105, qword_1805D7080, 0, v21);
          }
          v111 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v111 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v111 + 8) )
            goto LABEL_29;
          v101 = sub_18005AE04(v111, v108, v109, v110);
          if ( *(_DWORD *)(v101 + 1996) == v21 )
            goto LABEL_29;
          v102 = 862;
          goto LABEL_172;
        }
        v112 = *(_QWORD *)(a1 + 440);
        v113 = *(_QWORD *)(a1 + 232);
        v114 = *(unsigned int *)(a1 + 452);
        v115 = *(_DWORD *)(a1 + 452);
        *((_QWORD *)&v253 + 1) = __PAIR64__(cbMaxLength[0], v247);
        *(_QWORD *)&v253 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, __int64))(*(_QWORD *)v113 + 56LL))(
                v113,
                &v253,
                v114,
                cbMaxLength[0] * v115,
                v112);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 106, qword_1805D7080, 0, v21);
          }
          v119 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v119 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v119 + 8) )
            goto LABEL_29;
          v101 = sub_18005AE04(v119, v116, v117, v118);
          if ( *(_DWORD *)(v101 + 1996) == v21 )
            goto LABEL_29;
          v102 = 865;
          goto LABEL_172;
        }
        sub_18005B17C(&v240);
        v21 = sub_1800E1CD0(a1, *(_QWORD *)(a1 + 200), v247, cbMaxLength[0], (__int64)&v255, a1 + 448, (__int64)&v240);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 107, qword_1805D7080, 0, v21);
          }
          v123 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v123 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v123 + 8) )
            goto LABEL_29;
          v101 = sub_18005AE04(v123, v120, v121, v122);
          if ( *(_DWORD *)(v101 + 1996) == v21 )
            goto LABEL_29;
          v102 = 867;
          goto LABEL_172;
        }
        v21 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 208) + 184LL))(
                *(_QWORD *)(a1 + 208),
                v240);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 108, qword_1805D7080, 0, v21);
          }
          v127 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v127 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v127 + 8) )
            goto LABEL_29;
          v101 = sub_18005AE04(v127, v124, v125, v126);
          if ( *(_DWORD *)(v101 + 1996) == v21 )
            goto LABEL_29;
          v102 = 868;
          goto LABEL_172;
        }
      }
      v21 = sub_1800E1284(a1);
      if ( v21 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 109, qword_1805D7080, 0, v21);
        }
        v131 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v131 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v131 + 8) )
          goto LABEL_29;
        v101 = sub_18005AE04(v131, v128, v129, v130);
        if ( *(_DWORD *)(v101 + 1996) == v21 )
          goto LABEL_29;
        v102 = 873;
        goto LABEL_172;
      }
      v21 = sub_1800DFA18(a1);
      if ( v21 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 110, qword_1805D7080, 0, v21);
        }
        v135 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v135 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v135 + 8) )
          goto LABEL_29;
        v101 = sub_18005AE04(v135, v132, v133, v134);
        if ( *(_DWORD *)(v101 + 1996) == v21 )
          goto LABEL_29;
        v102 = 876;
        goto LABEL_172;
      }
      v21 = sub_1800DFCB4(a1);
      if ( v21 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 111, qword_1805D7080, 0, v21);
        }
        v139 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v139 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v139 + 8) )
          goto LABEL_29;
        v101 = sub_18005AE04(v139, v136, v137, v138);
        if ( *(_DWORD *)(v101 + 1996) == v21 )
          goto LABEL_29;
        v102 = 879;
        goto LABEL_172;
      }
      v140 = *(_QWORD *)(a1 + 112);
      v141 = *(_QWORD *)(a1 + 208);
      v243[0] = 0;
      v246[0] = 0;
      v21 = sub_1800ED83C((int)a1 + 120, v141, v140, 0, (__int64)v243, (__int64)v246);
      if ( v21 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 112, qword_1805D7080, 0, v21);
        }
        v145 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v145 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v145 + 8) )
          goto LABEL_29;
        v101 = sub_18005AE04(v145, v142, v143, v144);
        if ( *(_DWORD *)(v101 + 1996) == v21 )
          goto LABEL_29;
        v102 = 884;
        goto LABEL_172;
      }
      v146 = 0;
      LODWORD(v247) = 0;
      if ( v246[0] )
      {
        v21 = sub_1800EBE44(a1 + 120, &v247);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 113, qword_1805D7080, 0, v21);
          }
          v150 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v150 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v150 + 8) )
            goto LABEL_29;
          v101 = sub_18005AE04(v150, v147, v148, v149);
          if ( *(_DWORD *)(v101 + 1996) == v21 )
            goto LABEL_29;
          v102 = 889;
          goto LABEL_172;
        }
        v146 = v247;
      }
      if ( *(_DWORD *)(a1 + 472) )
      {
        LODWORD(v247) = 0;
        cbMaxLength[0] = 0;
        sub_1800E7990(a1 + 472, &v247, cbMaxLength);
        v151 = *(_QWORD *)(a1 + 208);
        ppBuffer = 0;
        v152 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v151 + 240LL);
        sub_180070474(&ppBuffer);
        v21 = v152(v151, &ppBuffer);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 114, qword_1805D7080, 0, v21);
          }
          v156 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v156 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v156 + 8) )
            goto LABEL_289;
          v157 = sub_18005AE04(v156, v153, v154, v155);
          if ( *(_DWORD *)(v157 + 1996) == v21 )
            goto LABEL_289;
          v158 = 901;
          goto LABEL_288;
        }
        v159 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->GetMaxLength)(ppBuffer);
        v160 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->GetCurrentLength)(ppBuffer);
        sub_180088AB8(v160, v159, v247, cbMaxLength[0], (__int64)&v247, (__int64)cbMaxLength);
        ((void (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
          ppBuffer,
          (unsigned int)v247);
        ((void (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl[1].QueryInterface)(ppBuffer, cbMaxLength[0]);
        v21 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**(_QWORD **)(a1 + 208) + 248LL))(
                *(_QWORD *)(a1 + 208),
                ppBuffer);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 115, qword_1805D7080, 0, v21);
          }
          v164 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v164 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v164 + 8) )
            goto LABEL_289;
          v157 = sub_18005AE04(v164, v161, v162, v163);
          if ( *(_DWORD *)(v157 + 1996) == v21 )
            goto LABEL_289;
          v158 = 907;
LABEL_288:
          sub_180207168(v157, "CWICHeifEncoderFrame::Commit", v158, (unsigned int)v21);
          goto LABEL_289;
        }
        sub_180070474(&ppBuffer);
      }
      v165 = *(_QWORD *)(a1 + 240);
      if ( v165 )
      {
        cbMaxLength[0] = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v165 + 56LL))(
                v165,
                0,
                0,
                cbMaxLength);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 116, qword_1805D7080, 0, v21);
          }
          v169 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v169 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v169 + 8) )
            goto LABEL_29;
          v101 = sub_18005AE04(v169, v166, v167, v168);
          if ( *(_DWORD *)(v101 + 1996) == v21 )
            goto LABEL_29;
          v102 = 914;
          goto LABEL_172;
        }
        ppBuffer = 0;
        v245 = 0;
        sub_180070474(&ppBuffer);
        v21 = MFCreateMemoryBuffer(cbMaxLength[0], &ppBuffer);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 117, qword_1805D7080, 0, v21);
          }
          v173 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v173 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v173 + 8) )
            goto LABEL_289;
          v174 = sub_18005AE04(v173, v170, v171, v172);
          if ( *(_DWORD *)(v174 + 1996) == v21 )
            goto LABEL_289;
          v175 = 918;
          goto LABEL_322;
        }
        v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                ppBuffer,
                &v245,
                0,
                0);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 118, qword_1805D7080, 0, v21);
          }
          v179 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v179 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v179 + 8) )
            goto LABEL_289;
          v174 = sub_18005AE04(v179, v176, v177, v178);
          if ( *(_DWORD *)(v174 + 1996) == v21 )
            goto LABEL_289;
          v175 = 919;
          goto LABEL_322;
        }
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, DWORD *))(**(_QWORD **)(a1 + 240) + 56LL))(
                *(_QWORD *)(a1 + 240),
                cbMaxLength[0],
                v245,
                cbMaxLength);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 119, qword_1805D7080, 0, v21);
          }
          v183 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v183 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v183 + 8) )
            goto LABEL_289;
          v174 = sub_18005AE04(v183, v180, v181, v182);
          if ( *(_DWORD *)(v174 + 1996) == v21 )
            goto LABEL_289;
          v175 = 920;
          goto LABEL_322;
        }
        v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 120, qword_1805D7080, 0, v21);
          }
          v187 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v187 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v187 + 8) )
            goto LABEL_289;
          v174 = sub_18005AE04(v187, v184, v185, v186);
          if ( *(_DWORD *)(v174 + 1996) == v21 )
            goto LABEL_289;
          v175 = 921;
          goto LABEL_322;
        }
        v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                ppBuffer,
                cbMaxLength[0]);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 121, qword_1805D7080, 0, v21);
          }
          v191 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v191 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v191 + 8) )
            goto LABEL_289;
          v174 = sub_18005AE04(v191, v188, v189, v190);
          if ( *(_DWORD *)(v174 + 1996) == v21 )
            goto LABEL_289;
          v175 = 922;
          goto LABEL_322;
        }
        v21 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**(_QWORD **)(a1 + 208) + 168LL))(
                *(_QWORD *)(a1 + 208),
                ppBuffer);
        if ( v21 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 122, qword_1805D7080, 0, v21);
          }
          v195 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v195 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v195 + 8) )
            goto LABEL_289;
          v174 = sub_18005AE04(v195, v192, v193, v194);
          if ( *(_DWORD *)(v174 + 1996) == v21 )
            goto LABEL_289;
          v175 = 924;
LABEL_322:
          sub_180207168(v174, "CWICHeifEncoderFrame::Commit", v175, (unsigned int)v21);
          goto LABEL_289;
        }
        sub_180070474(&ppBuffer);
      }
      if ( *(_QWORD *)(a1 + 512) && (v146 || *(_DWORD *)(a1 + 472) || v14) )
      {
        v196 = *(_QWORD *)(a1 + 208);
        ppBuffer = 0;
        v197 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v196 + 176LL);
        sub_180070474(&ppBuffer);
        v21 = v197(v196, &ppBuffer);
        if ( v21 >= 0 )
        {
          v21 = sub_1800E5384(a1, (_DWORD)ppBuffer, v240, v146, v14, (__int64)&v250);
          if ( v21 >= 0 )
          {
            v208 = 0;
            while ( 1 )
            {
              v209 = *(_QWORD *)(a1 + 208);
              v245 = 0;
              v210 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v209 + 216LL);
              sub_180070474(&v245);
              v21 = v210(v209, v208, &v245);
              if ( v21 < 0 )
                break;
              v21 = sub_1800E5384(a1, v245, 0, v146, v242, (__int64)&v250);
              if ( v21 < 0 )
              {
                if ( RequestContext != &RequestContext
                  && (*((_BYTE *)RequestContext + 28) & 1) != 0
                  && *((_BYTE *)RequestContext + 25) >= 4u )
                {
                  sub_180079880(*((_QWORD *)RequestContext + 2), 126, qword_1805D7080, 0, v21);
                }
                v221 = (__int64 *)qword_180685260;
                if ( !qword_180685260 )
                {
                  v221 = &qword_180684620;
                  qword_180685260 = (__int64)&qword_180684620;
                }
                if ( *((_BYTE *)v221 + 8) )
                {
                  v222 = sub_18005AE04(v221, v214, v215, v216);
                  if ( *(_DWORD *)(v222 + 1996) != v21 )
                  {
                    v223 = 943;
LABEL_434:
                    sub_180207168(v222, "CWICHeifEncoderFrame::Commit", v223, (unsigned int)v21);
                    goto LABEL_435;
                  }
                }
                goto LABEL_435;
              }
              sub_180070474(&v245);
              if ( ++v208 >= 4 )
              {
                sub_180070474(&ppBuffer);
                goto LABEL_406;
              }
            }
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 125, qword_1805D7080, 0, v21);
            }
            v224 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v224 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( *((_BYTE *)v224 + 8) )
            {
              v222 = sub_18005AE04(v224, v211, v212, v213);
              if ( *(_DWORD *)(v222 + 1996) != v21 )
              {
                v223 = 942;
                goto LABEL_434;
              }
            }
LABEL_435:
            sub_180070474(&v245);
            goto LABEL_289;
          }
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 124, qword_1805D7080, 0, v21);
          }
          v207 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v207 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v207 + 8) || (v202 = sub_18005AE04(v207, v204, v205, v206), *(_DWORD *)(v202 + 1996) == v21) )
          {
LABEL_289:
            sub_180070474(&ppBuffer);
            goto LABEL_29;
          }
          v203 = 937;
        }
        else
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 123, qword_1805D7080, 0, v21);
          }
          v201 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v201 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v201 + 8) )
            goto LABEL_289;
          v202 = sub_18005AE04(v201, v198, v199, v200);
          if ( *(_DWORD *)(v202 + 1996) == v21 )
            goto LABEL_289;
          v203 = 933;
        }
        sub_180207168(v202, "CWICHeifEncoderFrame::Commit", v203, (unsigned int)v21);
        goto LABEL_289;
      }
LABEL_406:
      v21 = sub_1800DFF4C(a1);
      if ( v21 >= 0 )
        goto LABEL_29;
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 127, qword_1805D7080, 0, v21);
      }
      v220 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v220 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v220 + 8) )
        goto LABEL_29;
      v101 = sub_18005AE04(v220, v217, v218, v219);
      if ( *(_DWORD *)(v101 + 1996) == v21 )
        goto LABEL_29;
      v102 = 949;
LABEL_172:
      sub_180207168(v101, "CWICHeifEncoderFrame::Commit", v102, (unsigned int)v21);
      goto LABEL_29;
    }
LABEL_82:
    v55 = *(_QWORD *)(a1 + 176);
    v249 = 0;
    sub_18005B17C(&v249);
    v21 = sub_1800E2F50(v55, &v249);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 96, qword_1805D7080, 0, v21);
      }
      v59 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v59 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v59 + 8) )
        goto LABEL_93;
      v60 = sub_18005AE04(v59, v56, v57, v58);
      if ( *(_DWORD *)(v60 + 1996) == v21 )
        goto LABEL_93;
      v61 = 824;
      goto LABEL_92;
    }
    v62 = *v45;
    v63 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)*v45 + 32LL);
    sub_18005B17C(a1 + 208);
    v21 = v63(v62, v249, a1 + 208);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 97, qword_1805D7080, 0, v21);
      }
      v67 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v67 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v67 + 8) )
        goto LABEL_93;
      v60 = sub_18005AE04(v67, v64, v65, v66);
      if ( *(_DWORD *)(v60 + 1996) == v21 )
        goto LABEL_93;
      v61 = 825;
LABEL_92:
      sub_180207168(v60, "CWICHeifEncoderFrame::Commit", v61, (unsigned int)v21);
LABEL_93:
      sub_18005B17C(&v249);
      goto LABEL_29;
    }
    v68 = *(_QWORD *)(a1 + 208);
    ppBuffer = 0;
    v69 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v68 + 240LL);
    sub_180070474(&ppBuffer);
    v21 = v69(v68, &ppBuffer);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 98, qword_1805D7080, 0, v21);
      }
      v73 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v73 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v73 + 8) )
      {
        v74 = sub_18005AE04(v73, v70, v71, v72);
        if ( *(_DWORD *)(v74 + 1996) != v21 )
          sub_180207168(v74, "CWICHeifEncoderFrame::Commit", 828, (unsigned int)v21);
      }
      goto LABEL_114;
    }
    v75 = (_QWORD *)((__int64 (__fastcall *)(IMFMediaBuffer *, GUID *))ppBuffer->lpVtbl->Lock)(ppBuffer, &v254);
    v76 = *v75 - *(_QWORD *)(v46 + 8);
    if ( *v75 == *(_QWORD *)(v46 + 8) )
      v76 = v75[1] - *(_QWORD *)(v46 + 16);
    *(_QWORD *)cbMaxLength = 0;
    v14 = v76 != 0;
    v242 = v76 != 0;
    v21 = sub_18005C374(&ppBuffer, cbMaxLength);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 99, qword_1805D7080, 0, v21);
      }
      v80 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v80 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v80 + 8) )
      {
        v81 = sub_18005AE04(v80, v77, v78, v79);
        if ( *(_DWORD *)(v81 + 1996) != v21 )
          sub_180207168(v81, "CWICHeifEncoderFrame::Commit", 834, (unsigned int)v21);
      }
      goto LABEL_127;
    }
    v250 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)cbMaxLength + 72LL))(
                        *(_QWORD *)cbMaxLength,
                        &v253);
    v247 = 0;
    sub_180070474(&v247);
    v254 = *(GUID *)(a1 + 520);
    v21 = sub_180085E04(&v254, 0, 0, &v247);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 100, qword_1805D7080, 0, v21);
      }
      v85 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v85 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v85 + 8) )
      {
        v86 = sub_18005AE04(v85, v82, v83, v84);
        if ( *(_DWORD *)(v86 + 1996) != v21 )
          sub_180207168(v86, "CWICHeifEncoderFrame::Commit", 839, (unsigned int)v21);
      }
      goto LABEL_138;
    }
    v245 = 0;
    sub_180070474(&v245);
    v21 = sub_180088760(ppBuffer, v247, &v245);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 101, qword_1805D7080, 0, v21);
      }
      v90 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v90 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v90 + 8) )
        goto LABEL_150;
      v91 = sub_18005AE04(v90, v87, v88, v89);
      if ( *(_DWORD *)(v91 + 1996) == v21 )
        goto LABEL_150;
      v92 = 842;
LABEL_149:
      sub_180207168(v91, "CWICHeifEncoderFrame::Commit", v92, (unsigned int)v21);
LABEL_150:
      sub_180070474(&v245);
LABEL_138:
      sub_180070474(&v247);
LABEL_127:
      sub_180070474(cbMaxLength);
LABEL_114:
      sub_180070474(&ppBuffer);
      goto LABEL_93;
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 208) + 248LL))(*(_QWORD *)(a1 + 208), v245);
    if ( v21 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 102, qword_1805D7080, 0, v21);
      }
      v96 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v96 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v96 + 8) )
        goto LABEL_150;
      v91 = sub_18005AE04(v96, v93, v94, v95);
      if ( *(_DWORD *)(v91 + 1996) == v21 )
        goto LABEL_150;
      v92 = 844;
      goto LABEL_149;
    }
    sub_180070474(&v245);
    sub_180070474(&v247);
    sub_180070474(cbMaxLength);
    sub_180070474(&ppBuffer);
    sub_18005B17C(&v249);
    goto LABEL_174;
  }
  if ( !((__int64)(*(_QWORD *)(a1 + 304) - *(_QWORD *)(a1 + 296)) >> 3) )
  {
    v21 = -2003292412;
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 95, qword_1805D7080, 0, -2003292412);
    }
    v54 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v54 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v54 + 8) )
      goto LABEL_447;
    v51 = sub_18005AE04(v54, v16, v17, v18);
    if ( *(_DWORD *)(v51 + 1996) == -2003292412 )
      goto LABEL_447;
    v53 = 811;
    goto LABEL_445;
  }
  v21 = sub_1800E0C94(a1);
  if ( v21 >= 0 )
    goto LABEL_56;
  if ( RequestContext != &RequestContext
    && (*((_BYTE *)RequestContext + 28) & 1) != 0
    && *((_BYTE *)RequestContext + 25) >= 4u )
  {
    sub_180079880(*((_QWORD *)RequestContext + 2), 94, qword_1805D7080, 0, v21);
  }
  v50 = (__int64 *)qword_180685260;
  if ( !qword_180685260 )
  {
    v50 = &qword_180684620;
    qword_180685260 = (__int64)&qword_180684620;
  }
  if ( !*((_BYTE *)v50 + 8) )
    goto LABEL_447;
  v51 = sub_18005AE04(v50, v47, v48, v49);
  if ( *(_DWORD *)(v51 + 1996) == v21 )
    goto LABEL_447;
  v52 = (unsigned int)v21;
  v53 = 807;
LABEL_446:
  sub_180207168(v51, "CWICHeifEncoderFrame::Commit", v53, v52);
LABEL_447:
  sub_18005B17C(&v240);
LABEL_448:
  if ( *(_BYTE *)(a1 + 448) )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 200) + 32LL))(*(_QWORD *)(a1 + 200));
    *(_BYTE *)(a1 + 448) = 0;
  }
  sub_180070474(a1 + 200);
  *(_QWORD *)(a1 + 440) = 0;
  v226 = MFGetSystemTime();
  v228 = *(_QWORD *)(a1 + 192);
  v229 = v226 - v2;
  if ( !v228 || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v228 + 320LL))(v228, qword_1805D10C0) )
  {
    v230 = *(_QWORD *)(a1 + 192);
    v231 = 0;
    v254 = guidExtendedType;
    if ( v230 )
    {
      v232 = (GUID *)(*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD))(*(_QWORD *)v230 + 280LL))(
                       v230,
                       &v253,
                       v227,
                       0);
      v233 = *(_QWORD *)(a1 + 192);
      v254 = *v232;
      v231 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v233 + 296LL))(v233);
    }
    if ( (unsigned int)dword_180681438 > 5
      && (unsigned __int8)sub_180001228(&dword_180681438, 0x400000000000LL, v227, v231) )
    {
      v250 = 0x1000000;
      LODWORD(v247) = v21;
      v13 = *(_QWORD *)(a1 + 232) == 0;
      cbMaxLength[0] = *(_DWORD *)(a1 + 460);
      LOBYTE(v6) = !v13;
      LODWORD(v249) = *(_DWORD *)(a1 + 472);
      v236 = *(_QWORD *)(a1 + 176);
      v245 = v229 / 10000;
      LODWORD(ppBuffer) = v6;
      v237 = *(unsigned __int8 *)(v236 + 236);
      *(_QWORD *)&v255 = L"CWICHeifEncoderFrame::Commit";
      *(_QWORD *)&v253 = &v254;
      LODWORD(v241) = v237;
      LODWORD(v240) = v235;
      sub_1800012F8(
        v237,
        (unsigned int)byte_18066563B,
        v234,
        v235,
        (__int64)&v253,
        (__int64)&v240,
        (__int64)&v255,
        (__int64)&v241,
        (__int64)&ppBuffer,
        (__int64)&v249,
        (__int64)cbMaxLength,
        (__int64)&v245,
        (__int64)&v247,
        (__int64)&v250);
    }
  }
  sub_180059CBC(v251);
  sub_180059EAC(v243);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800ddaa0  mov     rax, rsp
0x1800ddaa3  mov     [rax+10h], rbx
0x1800ddaa7  mov     [rax+18h], rsi
0x1800ddaab  mov     [rax+20h], rdi
0x1800ddaaf  push    rbp
0x1800ddab0  push    r12
0x1800ddab2  push    r13
0x1800ddab4  push    r14
0x1800ddab6  push    r15
0x1800ddab8  lea     rbp, [rax-48h]
0x1800ddabc  sub     rsp, 120h
0x1800ddac3  mov     rax, cs:__security_cookie
0x1800ddaca  xor     rax, rsp
0x1800ddacd  mov     [rbp+40h+var_30], rax
0x1800ddad1  mov     r15, rcx
0x1800ddad4  add     rcx, 30h ; '0'; lpCriticalSection
0x1800ddad8  call    cs:EnterCriticalSection
0x1800ddadf  nop     dword ptr [rax+rax+00h]
0x1800ddae4  call    cs:MFGetSystemTime
0x1800ddaeb  nop     dword ptr [rax+rax+00h]
0x1800ddaf0  lea     rsi, aCwicheifencode_9; "CWICHeifEncoderFrame::Commit"
0x1800ddaf7  mov     r8d, 2F3h
0x1800ddafd  lea     rcx, [rbp+40h+var_B7]
0x1800ddb01  mov     [rbp+40h+var_C0], rax
0x1800ddb05  mov     rdx, rsi
0x1800ddb08  mov     r12, rax
0x1800ddb0b  call    sub_180059AB4
0x1800ddb10  mov     rcx, cs:qword_180685260
0x1800ddb17  xor     r14d, r14d
0x1800ddb1a  cmp     [rcx+8], r14b
0x1800ddb1e  jz      short loc_1800DDB7B
0x1800ddb20  cmp     [r15+0C0h], r14
0x1800ddb27  jz      short loc_1800DDB7B
0x1800ddb29  call    sub_18005AE04
0x1800ddb2e  mov     rcx, [r15+0C0h]
0x1800ddb35  mov     rsi, rax
0x1800ddb38  mov     rdx, [rcx]
0x1800ddb3b  mov     rax, [rdx+128h]
0x1800ddb42  call    j__guard_dispatch_icall
0x1800ddb47  mov     rcx, [r15+0C0h]
0x1800ddb4e  mov     ebx, eax
0x1800ddb50  mov     rdx, [rcx]
0x1800ddb53  mov     rax, [rdx+118h]
0x1800ddb5a  lea     rdx, [rbp+40h+var_50]
0x1800ddb5e  call    j__guard_dispatch_icall
0x1800ddb63  movups  xmm0, xmmword ptr [rax]
0x1800ddb66  mov     [rsi+7E0h], ebx
0x1800ddb6c  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x1800ddb74  lea     rsi, aCwicheifencode_9; "CWICHeifEncoderFrame::Commit"
0x1800ddb7b  mov     edx, 0Fh
0x1800ddb80  mov     [rbp+40h+var_78], rsi
0x1800ddb84  mov     r9, rsi
0x1800ddb87  mov     [rbp+40h+var_68], edx
0x1800ddb8a  lea     r8, aS_0; "=>%s"
0x1800ddb91  mov     [rbp+40h+var_70], r14
0x1800ddb95  xor     ecx, ecx
0x1800ddb97  call    sub_18005B28C
0x1800ddb9c  cmp     dword ptr [r15+1E0h], 2
0x1800ddba4  mov     r13b, r14b
0x1800ddba7  mov     [rsp+140h+var_C8], r14
0x1800ddbac  mov     [rbp+40h+var_80], r14
0x1800ddbb0  mov     [rbp+40h+var_B8], r14b
0x1800ddbb4  jnz     loc_1800DF761
0x1800ddbba  mov     rcx, r15
0x1800ddbbd  mov     dword ptr [r15+1E0h], 3
0x1800ddbc8  call    sub_1800E29E0
0x1800ddbcd  mov     rbx, [r15+0B0h]
0x1800ddbd4  movups  xmm0, xmmword ptr [rax]
0x1800ddbd7  movdqu  [rbp+40h+var_40], xmm0
0x1800ddbdc  cmp     [rbx+0ECh], r14b
0x1800ddbe3  jz      loc_1800DDF4B
0x1800ddbe9  lea     rcx, [rsp+140h+ppBuffer]
0x1800ddbee  mov     [rbp+40h+var_A8], r14
0x1800ddbf2  mov     [rsp+140h+ppBuffer], r14
0x1800ddbf7  call    sub_18005B17C
0x1800ddbfc  lea     rdx, [rsp+140h+ppBuffer]
0x1800ddc01  mov     rcx, rbx
0x1800ddc04  call    sub_1800E2F50
0x1800ddc09  mov     ebx, eax
0x1800ddc0b  test    eax, eax
0x1800ddc0d  jns     loc_1800DDCA7
0x1800ddc13  mov     rcx, cs:RequestContext
0x1800ddc1a  lea     rax, RequestContext
0x1800ddc21  cmp     rcx, rax
0x1800ddc24  jz      short loc_1800DDC4E
0x1800ddc26  test    byte ptr [rcx+1Ch], 1
0x1800ddc2a  jz      short loc_1800DDC4E
0x1800ddc2c  cmp     byte ptr [rcx+19h], 4
0x1800ddc30  jb      short loc_1800DDC4E
0x1800ddc32  mov     rcx, [rcx+10h]
0x1800ddc36  lea     r8, qword_1805D7080
0x1800ddc3d  mov     edx, 5Ah ; 'Z'
0x1800ddc42  mov     dword ptr [rsp+140h+var_120], ebx
0x1800ddc46  xor     r9d, r9d
0x1800ddc49  call    sub_180079880
0x1800ddc4e  mov     rcx, cs:qword_180685260
0x1800ddc55  test    rcx, rcx
0x1800ddc58  jnz     short loc_1800DDC68
0x1800ddc5a  lea     rcx, qword_180684620
0x1800ddc61  mov     cs:qword_180685260, rcx
0x1800ddc68  cmp     [rcx+8], r14b
0x1800ddc6c  jz      short loc_1800DDC8F
0x1800ddc6e  call    sub_18005AE04
0x1800ddc73  cmp     [rax+7CCh], ebx
0x1800ddc79  jz      short loc_1800DDC8F
0x1800ddc7b  mov     r9d, ebx
0x1800ddc7e  mov     r8d, 304h
0x1800ddc84  mov     rdx, rsi
0x1800ddc87  mov     rcx, rax
0x1800ddc8a  call    sub_180207168
0x1800ddc8f  lea     rcx, [rsp+140h+ppBuffer]
0x1800ddc94  call    sub_18005B17C
0x1800ddc99  lea     rcx, [rbp+40h+var_A8]
0x1800ddc9d  call    sub_18005B17C
0x1800ddca2  jmp     loc_1800DF7E8
0x1800ddca7  mov     rbx, [rsp+140h+ppBuffer]
0x1800ddcac  lea     r12, [r15+0D0h]
0x1800ddcb3  mov     rcx, r12
0x1800ddcb6  mov     rax, [rbx]
0x1800ddcb9  mov     rsi, [rax+18h]
0x1800ddcbd  call    sub_18005B17C
0x1800ddcc2  mov     rdx, r12
0x1800ddcc5  mov     rcx, rbx
0x1800ddcc8  mov     rax, rsi
0x1800ddccb  call    j__guard_dispatch_icall
0x1800ddcd0  mov     ebx, eax
0x1800ddcd2  test    eax, eax
0x1800ddcd4  jns     loc_1800DDD80
0x1800ddcda  mov     rcx, cs:RequestContext
0x1800ddce1  lea     rax, RequestContext
0x1800ddce8  cmp     rcx, rax
0x1800ddceb  jz      short loc_1800DDD15
0x1800ddced  test    byte ptr [rcx+1Ch], 1
0x1800ddcf1  jz      short loc_1800DDD15
0x1800ddcf3  cmp     byte ptr [rcx+19h], 4
0x1800ddcf7  jb      short loc_1800DDD15
0x1800ddcf9  mov     rcx, [rcx+10h]
0x1800ddcfd  lea     r8, qword_1805D7080
0x1800ddd04  mov     edx, 5Bh ; '['
0x1800ddd09  mov     dword ptr [rsp+140h+var_120], ebx
0x1800ddd0d  xor     r9d, r9d
0x1800ddd10  call    sub_180079880
0x1800ddd15  mov     rcx, cs:qword_180685260
0x1800ddd1c  test    rcx, rcx
0x1800ddd1f  jnz     short loc_1800DDD2F
0x1800ddd21  lea     rcx, qword_180684620
0x1800ddd28  mov     cs:qword_180685260, rcx
0x1800ddd2f  cmp     [rcx+8], r14b
0x1800ddd33  jz      short loc_1800DDD5A
0x1800ddd35  call    sub_18005AE04
0x1800ddd3a  cmp     [rax+7CCh], ebx
0x1800ddd40  jz      short loc_1800DDD5A
0x1800ddd42  mov     r8d, 305h
0x1800ddd48  mov     r9d, ebx
0x1800ddd4b  lea     rdx, aCwicheifencode_9; "CWICHeifEncoderFrame::Commit"
0x1800ddd52  mov     rcx, rax
0x1800ddd55  call    sub_180207168
0x1800ddd5a  lea     rcx, [rsp+140h+ppBuffer]
0x1800ddd5f  call    sub_18005B17C
0x1800ddd64  lea     rcx, [rbp+40h+var_A8]
0x1800ddd68  call    sub_18005B17C
0x1800ddd6d  lea     rcx, [rsp+140h+var_C8]
0x1800ddd72  call    sub_18005B17C
0x1800ddd77  mov     r12, [rbp+40h+var_C0]
0x1800ddd7b  jmp     loc_1800DF7F2
0x1800ddd80  cmp     [r15+1DCh], r14d
0x1800ddd87  jnz     loc_1800DDE6D
0x1800ddd8d  mov     rcx, [r12]
0x1800ddd91  lea     r8, [rbp+40h+var_90]
0x1800ddd95  xorps   xmm0, xmm0
0x1800ddd98  mov     [rbp+40h+var_90], r14b
0x1800ddd9c  movups  [rbp+40h+var_60], xmm0
0x1800ddda0  lea     rdx, [rbp+40h+var_60]
0x1800ddda4  mov     rax, [rcx]
0x1800ddda7  mov     rax, [rax+30h]
0x1800dddab  call    j__guard_dispatch_icall
0x1800dddb0  mov     ebx, eax
0x1800dddb2  test    eax, eax
0x1800dddb4  jns     short loc_1800DDE31
0x1800dddb6  mov     rcx, cs:RequestContext
0x1800dddbd  lea     rax, RequestContext
0x1800dddc4  cmp     rcx, rax
0x1800dddc7  jz      short loc_1800DDDF1
0x1800dddc9  test    byte ptr [rcx+1Ch], 1
0x1800dddcd  jz      short loc_1800DDDF1
0x1800dddcf  cmp     byte ptr [rcx+19h], 4
0x1800dddd3  jb      short loc_1800DDDF1
0x1800dddd5  mov     rcx, [rcx+10h]
0x1800dddd9  lea     r8, qword_1805D7080
0x1800ddde0  mov     edx, 5Ch ; '\'
0x1800ddde5  mov     dword ptr [rsp+140h+var_120], ebx
0x1800ddde9  xor     r9d, r9d
0x1800dddec  call    sub_180079880
0x1800dddf1  mov     rcx, cs:qword_180685260
0x1800dddf8  test    rcx, rcx
0x1800dddfb  jnz     short loc_1800DDE0B
0x1800dddfd  lea     rcx, qword_180684620
0x1800dde04  mov     cs:qword_180685260, rcx
0x1800dde0b  cmp     [rcx+8], r14b
0x1800dde0f  jz      loc_1800DDD5A
0x1800dde15  call    sub_18005AE04
0x1800dde1a  cmp     [rax+7CCh], ebx
0x1800dde20  jz      loc_1800DDD5A
0x1800dde26  mov     r8d, 30Fh
0x1800dde2c  jmp     loc_1800DDD48
0x1800dde31  mov     ebx, 10h
0x1800dde36  lea     rdx, aHevc; "HEVC"
0x1800dde3d  mov     r8d, ebx
0x1800dde40  lea     rcx, [rbp+40h+var_60]
0x1800dde44  call    sub_1802B69B0
0x1800dde49  test    eax, eax
0x1800dde4b  jz      short loc_1800DDE64
0x1800dde4d  mov     r8d, ebx
0x1800dde50  lea     rdx, aAv01; "AV01"
0x1800dde57  lea     rcx, [rbp+40h+var_60]
0x1800dde5b  call    sub_1802B69B0
0x1800dde60  test    eax, eax
0x1800dde62  jnz     short loc_1800DDE6D
0x1800dde64  movaps  xmm0, [rbp+40h+var_60]
0x1800dde68  movdqa  [rbp+40h+var_40], xmm0
0x1800dde6d  lea     rsi, [r15+1C0h]
0x1800dde74  cmp     [rsi], r14b
0x1800dde77  jz      loc_1800DDF13
0x1800dde7d  mov     rcx, [rsp+140h+ppBuffer]
0x1800dde82  mov     rdx, [r12]
0x1800dde86  mov     rax, [rcx]
0x1800dde89  mov     rax, [rax+38h]
0x1800dde8d  call    j__guard_dispatch_icall
0x1800dde92  mov     ebx, eax
0x1800dde94  test    eax, eax
0x1800dde96  jns     short loc_1800DDF13
0x1800dde98  mov     rcx, cs:RequestContext
0x1800dde9f  lea     rax, RequestContext
0x1800ddea6  cmp     rcx, rax
0x1800ddea9  jz      short loc_1800DDED3
0x1800ddeab  test    byte ptr [rcx+1Ch], 1
0x1800ddeaf  jz      short loc_1800DDED3
0x1800ddeb1  cmp     byte ptr [rcx+19h], 4
0x1800ddeb5  jb      short loc_1800DDED3
0x1800ddeb7  mov     rcx, [rcx+10h]
0x1800ddebb  lea     r8, qword_1805D7080
0x1800ddec2  mov     edx, 5Dh ; ']'
0x1800ddec7  mov     dword ptr [rsp+140h+var_120], ebx
0x1800ddecb  xor     r9d, r9d
0x1800ddece  call    sub_180079880
0x1800dded3  mov     rcx, cs:qword_180685260
0x1800ddeda  test    rcx, rcx
0x1800ddedd  jnz     short loc_1800DDEED
0x1800ddedf  lea     rcx, qword_180684620
0x1800ddee6  mov     cs:qword_180685260, rcx
0x1800ddeed  cmp     [rcx+8], r14b
0x1800ddef1  jz      loc_1800DDD5A
0x1800ddef7  call    sub_18005AE04
0x1800ddefc  cmp     [rax+7CCh], ebx
0x1800ddf02  jz      loc_1800DDD5A
0x1800ddf08  mov     r8d, 31Ch
0x1800ddf0e  jmp     loc_1800DDD48
0x1800ddf13  lea     rcx, [rsp+140h+ppBuffer]
0x1800ddf18  call    sub_18005B17C
0x1800ddf1d  lea     rcx, [rbp+40h+var_A8]
0x1800ddf21  call    sub_18005B17C
0x1800ddf26  cmp     [rsi], r14b
0x1800ddf29  jnz     loc_1800DE08D
0x1800ddf2f  cmp     [r15+200h], r14
0x1800ddf36  jz      loc_1800DE6F7
0x1800ddf3c  lea     r12, [r15+200h]
0x1800ddf43  mov     r13, r12
0x1800ddf46  jmp     loc_1800DE0A1
0x1800ddf4b  lea     rsi, [r15+1C0h]
0x1800ddf52  cmp     [rsi], r14b
0x1800ddf55  jnz     loc_1800DE08D
0x1800ddf5b  cmp     [r15+200h], r14
0x1800ddf62  jnz     short loc_1800DDF26
0x1800ddf64  mov     rax, [r15+130h]
0x1800ddf6b  sub     rax, [r15+128h]
0x1800ddf72  sar     rax, 3
0x1800ddf76  test    rax, rax
0x1800ddf79  jz      loc_1800DE00B
0x1800ddf7f  mov     rcx, r15
0x1800ddf82  call    sub_1800E0C94
0x1800ddf87  mov     ebx, eax
0x1800ddf89  test    eax, eax
0x1800ddf8b  jns     short loc_1800DDF26
0x1800ddf8d  mov     rcx, cs:RequestContext
0x1800ddf94  lea     rax, RequestContext
0x1800ddf9b  cmp     rcx, rax
0x1800ddf9e  jz      short loc_1800DDFC8
0x1800ddfa0  test    byte ptr [rcx+1Ch], 1
0x1800ddfa4  jz      short loc_1800DDFC8
0x1800ddfa6  cmp     byte ptr [rcx+19h], 4
0x1800ddfaa  jb      short loc_1800DDFC8
0x1800ddfac  mov     rcx, [rcx+10h]
0x1800ddfb0  lea     r8, qword_1805D7080
0x1800ddfb7  mov     edx, 5Eh ; '^'
0x1800ddfbc  mov     dword ptr [rsp+140h+var_120], ebx
0x1800ddfc0  xor     r9d, r9d
0x1800ddfc3  call    sub_180079880
0x1800ddfc8  mov     rcx, cs:qword_180685260
0x1800ddfcf  test    rcx, rcx
0x1800ddfd2  jnz     short loc_1800DDFE2
  ... truncated ...
```
