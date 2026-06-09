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
  int v5; // r14d
  __int64 v6; // rsi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  __int64 v10; // r8
  bool v11; // zf
  char v12; // r13
  __int128 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rdx
  HRESULT v18; // ebx
  __int64 v19; // r8
  __int64 *v20; // rcx
  __int64 v21; // rax
  IMFMediaBuffer *v22; // rbx
  _QWORD *v23; // r12
  HRESULT (__stdcall *Lock)(IMFMediaBuffer *, BYTE **, DWORD *, DWORD *); // rsi
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 *v36; // rcx
  _BYTE *v37; // rsi
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  __int64 *v41; // r12
  __int64 v42; // r13
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 *v48; // rcx
  __int64 v49; // rbx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // r8
  __int64 v55; // rsi
  __int64 (__fastcall *v56)(__int64, __int64, __int64); // rbx
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 *v60; // rcx
  __int64 v61; // rsi
  __int64 (__fastcall *v62)(__int64, IMFMediaBuffer **); // rbx
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 *v66; // rcx
  __int64 v67; // rax
  _QWORD *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 *v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 *v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 *v86; // rcx
  __int64 v87; // rax
  __int64 v88; // r8
  __int64 *v89; // rcx
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // r9
  __int64 v99; // rdx
  __int64 v100; // r8
  __int64 v101; // r9
  __int64 *v102; // rcx
  __int64 v103; // rax
  __int64 v104; // r8
  __int64 v105; // rcx
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 *v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 *v111; // rcx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  int v115; // r9d
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 *v118; // rcx
  __int64 v119; // rdx
  __int64 v120; // r8
  __int64 *v121; // rcx
  __int64 v122; // rdx
  __int64 v123; // r8
  __int64 *v124; // rcx
  __int64 v125; // rdx
  __int64 v126; // r8
  __int64 *v127; // rcx
  __int64 v128; // rdx
  __int64 v129; // r8
  __int64 *v130; // rcx
  __int64 v131; // rdx
  __int64 v132; // r8
  __int64 *v133; // rcx
  __int64 v134; // r8
  __int64 v135; // rdx
  __int64 v136; // rdx
  __int64 v137; // r8
  __int64 v138; // r9
  __int64 *v139; // rcx
  int v140; // r12d
  __int64 *v141; // rcx
  __int64 v142; // rsi
  __int64 (__fastcall *v143)(__int64, IMFMediaBuffer **); // rbx
  __int64 v144; // rdx
  __int64 v145; // r8
  __int64 v146; // r9
  __int64 v147; // rdx
  __int64 v148; // r8
  __int64 v149; // r9
  __int64 *v150; // rcx
  __int64 v151; // rax
  __int64 v152; // r8
  int v153; // ebx
  int v154; // eax
  __int64 *v155; // rcx
  __int64 v156; // rcx
  __int64 v157; // rdx
  __int64 v158; // r8
  __int64 v159; // r9
  __int64 *v160; // rcx
  __int64 *v161; // rcx
  __int64 v162; // rax
  __int64 v163; // r8
  __int64 *v164; // rcx
  __int64 *v165; // rcx
  __int64 *v166; // rcx
  __int64 *v167; // rcx
  __int64 *v168; // rcx
  __int64 v169; // rsi
  __int64 (__fastcall *v170)(__int64, IMFMediaBuffer **); // rbx
  __int64 *v171; // rcx
  __int64 v172; // rax
  __int64 v173; // r8
  __int64 *v174; // rcx
  unsigned int v175; // r13d
  __int64 v176; // rsi
  __int64 (__fastcall *v177)(__int64, _QWORD, __int64 *); // rbx
  __int64 v178; // rdx
  __int64 v179; // r8
  __int64 v180; // r9
  __int64 v181; // rdx
  __int64 v182; // r8
  __int64 *v183; // rcx
  __int64 *v184; // rcx
  __int64 v185; // rax
  __int64 v186; // r8
  __int64 *v187; // rcx
  __int64 *v188; // rcx
  MFTIME v189; // rax
  __int64 v190; // rdx
  __int64 v191; // r8
  __int64 v192; // rcx
  MFTIME v193; // rsi
  __int64 v194; // r9
  __int64 v195; // rcx
  GUID *v196; // rax
  __int64 v197; // rcx
  __int64 v198; // rax
  int v199; // ecx
  IMFMediaBuffer *ppBuffer; // [rsp+78h] [rbp-90h] BYREF
  __int64 v202; // [rsp+80h] [rbp-88h] BYREF
  MFTIME v203; // [rsp+88h] [rbp-80h] BYREF
  char v204; // [rsp+90h] [rbp-78h]
  _BYTE v205[7]; // [rsp+91h] [rbp-77h] BYREF
  DWORD cbMaxLength[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v207; // [rsp+A0h] [rbp-68h] BYREF
  char v208[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v209; // [rsp+B0h] [rbp-58h] BYREF
  char v210[8]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v211; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v212; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v213[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v214; // [rsp+E0h] [rbp-28h]
  __int128 v215; // [rsp+E8h] [rbp-20h] BYREF
  GUID v216; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v217; // [rsp+108h] [rbp+0h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v203 = MFGetSystemTime();
  v2 = v203;
  sub_180059AB4(v205, "CWICHeifEncoderFrame::Commit", 755);
  v5 = 0;
  if ( *(_BYTE *)(qword_180685260 + 8) && *(_QWORD *)(a1 + 192) )
  {
    v6 = sub_18005AE04(qword_180685260, v3, v4);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 192) + 296LL))(*(_QWORD *)(a1 + 192));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)(a1 + 192) + 280LL))(
                      *(_QWORD *)(a1 + 192),
                      &v216);
    *(_DWORD *)(v6 + 2016) = v7;
    *(_OWORD *)(v6 + 2000) = v8;
  }
  v213[0] = "CWICHeifEncoderFrame::Commit";
  v214 = 15;
  v213[1] = 0;
  sub_18005B28C(0, 15, "=>%s", "CWICHeifEncoderFrame::Commit");
  v11 = *(_DWORD *)(a1 + 480) == 2;
  v12 = 0;
  v202 = 0;
  v212 = 0;
  v204 = 0;
  if ( v11 )
  {
    *(_DWORD *)(a1 + 480) = 3;
    v13 = (__int128 *)sub_1800E29E0(a1);
    v16 = *(_QWORD *)(a1 + 176);
    v217 = *v13;
    if ( *(_BYTE *)(v16 + 236) )
    {
      v207 = 0;
      ppBuffer = 0;
      sub_18005B17C(&ppBuffer);
      v18 = sub_1800E2F50(v16, &ppBuffer);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 90, qword_1805D7080, 0, v18);
        }
        v20 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v20 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v21 = sub_18005AE04(v20, v17, v19);
          if ( *(_DWORD *)(v21 + 1996) != v18 )
            sub_180207168(v21, "CWICHeifEncoderFrame::Commit", 772);
        }
        sub_18005B17C(&ppBuffer);
        sub_18005B17C(&v207);
        goto LABEL_446;
      }
      v22 = ppBuffer;
      v23 = (_QWORD *)(a1 + 208);
      Lock = ppBuffer->lpVtbl->Lock;
      sub_18005B17C(a1 + 208);
      v18 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64))Lock)(v22, a1 + 208);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 91, qword_1805D7080, 0, v18);
        }
        v27 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v27 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v27 + 8) )
          goto LABEL_28;
        v28 = sub_18005AE04(v27, v25, v26);
        if ( *(_DWORD *)(v28 + 1996) == v18 )
          goto LABEL_28;
        v29 = 773;
LABEL_27:
        sub_180207168(v28, "CWICHeifEncoderFrame::Commit", v29);
LABEL_28:
        sub_18005B17C(&ppBuffer);
        sub_18005B17C(&v207);
LABEL_29:
        sub_18005B17C(&v202);
        v2 = v203;
        goto LABEL_447;
      }
      if ( !*(_DWORD *)(a1 + 476) )
      {
        v33 = *v23;
        v210[0] = 0;
        v215 = 0;
        v18 = (*(__int64 (__fastcall **)(__int64, __int128 *, char *))(*(_QWORD *)v33 + 48LL))(v33, &v215, v210);
        if ( v18 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 92, qword_1805D7080, 0, v18);
          }
          v36 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v36 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v36 + 8) )
            goto LABEL_28;
          v28 = sub_18005AE04(v36, v34, v35);
          if ( *(_DWORD *)(v28 + 1996) == v18 )
            goto LABEL_28;
          v29 = 783;
          goto LABEL_27;
        }
        if ( !(unsigned int)sub_1802B69B0(&v215, "HEVC", 16) || !(unsigned int)sub_1802B69B0(&v215, "AV01", 16) )
          v217 = v215;
      }
      v37 = (_BYTE *)(a1 + 448);
      if ( *(_BYTE *)(a1 + 448) )
      {
        v18 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->GetMaxLength)(ppBuffer, *v23);
        if ( v18 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 93, qword_1805D7080, 0, v18);
          }
          v40 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v40 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v40 + 8) )
            goto LABEL_28;
          v28 = sub_18005AE04(v40, v38, v39);
          if ( *(_DWORD *)(v28 + 1996) == v18 )
            goto LABEL_28;
          v29 = 796;
          goto LABEL_27;
        }
      }
      sub_18005B17C(&ppBuffer);
      sub_18005B17C(&v207);
      goto LABEL_56;
    }
    v37 = (_BYTE *)(a1 + 448);
    if ( *(_BYTE *)(a1 + 448) )
      goto LABEL_81;
    if ( *(_QWORD *)(a1 + 512) )
    {
LABEL_56:
      if ( !*v37 )
      {
        if ( !*(_QWORD *)(a1 + 512) )
          goto LABEL_174;
        v41 = (__int64 *)(a1 + 512);
        v42 = a1 + 512;
        goto LABEL_82;
      }
LABEL_81:
      v41 = (__int64 *)(a1 + 512);
      v42 = a1 + 512;
      if ( !*(_QWORD *)(a1 + 512) )
      {
        sub_18005B17C(a1 + 208);
        v18 = sub_1800E1CD0(
                a1,
                *(_QWORD *)(a1 + 200),
                *(_DWORD *)(a1 + 224),
                *(_DWORD *)(a1 + 228),
                (__int64)&v217,
                (__int64)v37,
                a1 + 208);
        if ( v18 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 103, qword_1805D7080, 0, v18);
          }
          v102 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v102 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v102 + 8) )
            goto LABEL_29;
          v103 = sub_18005AE04(v102, v99, v100);
          if ( *(_DWORD *)(v103 + 1996) == v18 )
            goto LABEL_29;
          v104 = 850;
          goto LABEL_172;
        }
        sub_180070474(a1 + 200, v99, v100, v101);
        *(_QWORD *)(a1 + 440) = 0;
        v12 = 0;
LABEL_174:
        v105 = *(_QWORD *)(a1 + 232);
        if ( v105 )
        {
          LODWORD(v209) = 0;
          cbMaxLength[0] = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, __int64 *, DWORD *))(*(_QWORD *)v105 + 24LL))(
                  v105,
                  &v209,
                  cbMaxLength);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 104, qword_1805D7080, 0, v18);
            }
            v108 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v108 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v108 + 8) )
              goto LABEL_29;
            v103 = sub_18005AE04(v108, v106, v107);
            if ( *(_DWORD *)(v103 + 1996) == v18 )
              goto LABEL_29;
            v104 = 860;
            goto LABEL_172;
          }
          v18 = sub_1800DD10C(a1, (unsigned int)v209, cbMaxLength[0]);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 105, qword_1805D7080, 0, v18);
            }
            v111 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v111 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v111 + 8) )
              goto LABEL_29;
            v103 = sub_18005AE04(v111, v109, v110);
            if ( *(_DWORD *)(v103 + 1996) == v18 )
              goto LABEL_29;
            v104 = 862;
            goto LABEL_172;
          }
          v112 = *(_QWORD *)(a1 + 440);
          v113 = *(_QWORD *)(a1 + 232);
          v114 = *(unsigned int *)(a1 + 452);
          v115 = *(_DWORD *)(a1 + 452);
          *((_QWORD *)&v215 + 1) = __PAIR64__(cbMaxLength[0], v209);
          *(_QWORD *)&v215 = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, __int64))(*(_QWORD *)v113 + 56LL))(
                  v113,
                  &v215,
                  v114,
                  cbMaxLength[0] * v115,
                  v112);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 106, qword_1805D7080, 0, v18);
            }
            v118 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v118 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v118 + 8) )
              goto LABEL_29;
            v103 = sub_18005AE04(v118, v116, v117);
            if ( *(_DWORD *)(v103 + 1996) == v18 )
              goto LABEL_29;
            v104 = 865;
            goto LABEL_172;
          }
          sub_18005B17C(&v202);
          v18 = sub_1800E1CD0(a1, *(_QWORD *)(a1 + 200), v209, cbMaxLength[0], (__int64)&v217, a1 + 448, (__int64)&v202);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 107, qword_1805D7080, 0, v18);
            }
            v121 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v121 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v121 + 8) )
              goto LABEL_29;
            v103 = sub_18005AE04(v121, v119, v120);
            if ( *(_DWORD *)(v103 + 1996) == v18 )
              goto LABEL_29;
            v104 = 867;
            goto LABEL_172;
          }
          v18 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 208) + 184LL))(
                  *(_QWORD *)(a1 + 208),
                  v202);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 108, qword_1805D7080, 0, v18);
            }
            v124 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v124 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v124 + 8) )
              goto LABEL_29;
            v103 = sub_18005AE04(v124, v122, v123);
            if ( *(_DWORD *)(v103 + 1996) == v18 )
              goto LABEL_29;
            v104 = 868;
            goto LABEL_172;
          }
        }
        v18 = sub_1800E1284(a1);
        if ( v18 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 109, qword_1805D7080, 0, v18);
          }
          v127 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v127 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v127 + 8) )
            goto LABEL_29;
          v103 = sub_18005AE04(v127, v125, v126);
          if ( *(_DWORD *)(v103 + 1996) == v18 )
            goto LABEL_29;
          v104 = 873;
          goto LABEL_172;
        }
        v18 = sub_1800DFA18(a1);
        if ( v18 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 110, qword_1805D7080, 0, v18);
          }
          v130 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v130 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v130 + 8) )
            goto LABEL_29;
          v103 = sub_18005AE04(v130, v128, v129);
          if ( *(_DWORD *)(v103 + 1996) == v18 )
            goto LABEL_29;
          v104 = 876;
          goto LABEL_172;
        }
        v18 = sub_1800DFCB4(a1);
        if ( v18 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 111, qword_1805D7080, 0, v18);
          }
          v133 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v133 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v133 + 8) )
            goto LABEL_29;
          v103 = sub_18005AE04(v133, v131, v132);
          if ( *(_DWORD *)(v103 + 1996) == v18 )
            goto LABEL_29;
          v104 = 879;
          goto LABEL_172;
        }
        v134 = *(_QWORD *)(a1 + 112);
        v135 = *(_QWORD *)(a1 + 208);
        v205[0] = 0;
        v208[0] = 0;
        v18 = sub_1800ED83C((int)a1 + 120, v135, v134, 0, (__int64)v205, (__int64)v208);
        if ( v18 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 112, qword_1805D7080, 0, v18);
          }
          v139 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v139 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v139 + 8) )
            goto LABEL_29;
          v103 = sub_18005AE04(v139, v136, v137);
          if ( *(_DWORD *)(v103 + 1996) == v18 )
            goto LABEL_29;
          v104 = 884;
          goto LABEL_172;
        }
        v140 = 0;
        LODWORD(v209) = 0;
        if ( v208[0] )
        {
          v18 = sub_1800EBE44(a1 + 120, &v209);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 113, qword_1805D7080, 0, v18);
            }
            v141 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v141 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v141 + 8) )
              goto LABEL_29;
            v103 = sub_18005AE04(v141, v136, v137);
            if ( *(_DWORD *)(v103 + 1996) == v18 )
              goto LABEL_29;
            v104 = 889;
            goto LABEL_172;
          }
          v140 = v209;
        }
        if ( *(_DWORD *)(a1 + 472) )
        {
          LODWORD(v209) = 0;
          cbMaxLength[0] = 0;
          sub_1800E7990(a1 + 472, &v209, cbMaxLength);
          v142 = *(_QWORD *)(a1 + 208);
          ppBuffer = 0;
          v143 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v142 + 240LL);
          sub_180070474(&ppBuffer, v144, v145, v146);
          v18 = v143(v142, &ppBuffer);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 114, qword_1805D7080, 0, v18);
            }
            v150 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v150 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v150 + 8) )
              goto LABEL_289;
            v151 = sub_18005AE04(v150, v147, v148);
            if ( *(_DWORD *)(v151 + 1996) == v18 )
              goto LABEL_289;
            v152 = 901;
            goto LABEL_288;
          }
          v153 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->GetMaxLength)(ppBuffer);
          v154 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->GetCurrentLength)(ppBuffer);
          sub_180088AB8(v154, v153, v209, cbMaxLength[0], (__int64)&v209, (__int64)cbMaxLength);
          ((void (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
            ppBuffer,
            (unsigned int)v209);
          ((void (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl[1].QueryInterface)(ppBuffer, cbMaxLength[0]);
          v18 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**(_QWORD **)(a1 + 208) + 248LL))(
                  *(_QWORD *)(a1 + 208),
                  ppBuffer);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 115, qword_1805D7080, 0, v18);
            }
            v155 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v155 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v155 + 8) )
              goto LABEL_289;
            v151 = sub_18005AE04(v155, v147, v148);
            if ( *(_DWORD *)(v151 + 1996) == v18 )
              goto LABEL_289;
            v152 = 907;
LABEL_288:
            sub_180207168(v151, "CWICHeifEncoderFrame::Commit", v152);
            goto LABEL_289;
          }
          sub_180070474(&ppBuffer, v147, v148, v149);
        }
        v156 = *(_QWORD *)(a1 + 240);
        if ( v156 )
        {
          cbMaxLength[0] = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v156 + 56LL))(
                  v156,
                  0,
                  0,
                  cbMaxLength);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 116, qword_1805D7080, 0, v18);
            }
            v160 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v160 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v160 + 8) )
              goto LABEL_29;
            v103 = sub_18005AE04(v160, v157, v158);
            if ( *(_DWORD *)(v103 + 1996) == v18 )
              goto LABEL_29;
            v104 = 914;
            goto LABEL_172;
          }
          ppBuffer = 0;
          v207 = 0;
          sub_180070474(&ppBuffer, v157, v158, v159);
          v18 = MFCreateMemoryBuffer(cbMaxLength[0], &ppBuffer);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 117, qword_1805D7080, 0, v18);
            }
            v161 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v161 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v161 + 8) )
              goto LABEL_289;
            v162 = sub_18005AE04(v161, v147, v148);
            if ( *(_DWORD *)(v162 + 1996) == v18 )
              goto LABEL_289;
            v163 = 918;
            goto LABEL_322;
          }
          v18 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                  ppBuffer,
                  &v207,
                  0,
                  0);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 118, qword_1805D7080, 0, v18);
            }
            v164 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v164 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v164 + 8) )
              goto LABEL_289;
            v162 = sub_18005AE04(v164, v147, v148);
            if ( *(_DWORD *)(v162 + 1996) == v18 )
              goto LABEL_289;
            v163 = 919;
            goto LABEL_322;
          }
          v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, DWORD *))(**(_QWORD **)(a1 + 240) + 56LL))(
                  *(_QWORD *)(a1 + 240),
                  cbMaxLength[0],
                  v207,
                  cbMaxLength);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 119, qword_1805D7080, 0, v18);
            }
            v165 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v165 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v165 + 8) )
              goto LABEL_289;
            v162 = sub_18005AE04(v165, v147, v148);
            if ( *(_DWORD *)(v162 + 1996) == v18 )
              goto LABEL_289;
            v163 = 920;
            goto LABEL_322;
          }
          v18 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 120, qword_1805D7080, 0, v18);
            }
            v166 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v166 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v166 + 8) )
              goto LABEL_289;
            v162 = sub_18005AE04(v166, v147, v148);
            if ( *(_DWORD *)(v162 + 1996) == v18 )
              goto LABEL_289;
            v163 = 921;
            goto LABEL_322;
          }
          v18 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                  ppBuffer,
                  cbMaxLength[0]);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 121, qword_1805D7080, 0, v18);
            }
            v167 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v167 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v167 + 8) )
              goto LABEL_289;
            v162 = sub_18005AE04(v167, v147, v148);
            if ( *(_DWORD *)(v162 + 1996) == v18 )
              goto LABEL_289;
            v163 = 922;
            goto LABEL_322;
          }
          v18 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**(_QWORD **)(a1 + 208) + 168LL))(
                  *(_QWORD *)(a1 + 208),
                  ppBuffer);
          if ( v18 < 0 )
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 122, qword_1805D7080, 0, v18);
            }
            v168 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v168 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v168 + 8) )
              goto LABEL_289;
            v162 = sub_18005AE04(v168, v147, v148);
            if ( *(_DWORD *)(v162 + 1996) == v18 )
              goto LABEL_289;
            v163 = 924;
LABEL_322:
            sub_180207168(v162, "CWICHeifEncoderFrame::Commit", v163);
            goto LABEL_289;
          }
          sub_180070474(&ppBuffer, v147, v148, v149);
        }
        if ( *(_QWORD *)(a1 + 512) && (v140 || *(_DWORD *)(a1 + 472) || v12) )
        {
          v169 = *(_QWORD *)(a1 + 208);
          ppBuffer = 0;
          v170 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v169 + 176LL);
          sub_180070474(&ppBuffer, v136, v137, v138);
          v18 = v170(v169, &ppBuffer);
          if ( v18 >= 0 )
          {
            v18 = sub_1800E5384(a1, (_DWORD)ppBuffer, v202, v140, v12, (__int64)&v212);
            if ( v18 >= 0 )
            {
              v175 = 0;
              while ( 1 )
              {
                v176 = *(_QWORD *)(a1 + 208);
                v207 = 0;
                v177 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v176 + 216LL);
                sub_180070474(&v207, v147, v148, v149);
                v18 = v177(v176, v175, &v207);
                if ( v18 < 0 )
                  break;
                v18 = sub_1800E5384(a1, v207, 0, v140, v204, (__int64)&v212);
                if ( v18 < 0 )
                {
                  if ( RequestContext != &RequestContext
                    && (*((_BYTE *)RequestContext + 28) & 1) != 0
                    && *((_BYTE *)RequestContext + 25) >= 4u )
                  {
                    sub_180079880(*((_QWORD *)RequestContext + 2), 126, qword_1805D7080, 0, v18);
                  }
                  v184 = (__int64 *)qword_180685260;
                  if ( !qword_180685260 )
                  {
                    v184 = &qword_180684620;
                    qword_180685260 = (__int64)&qword_180684620;
                  }
                  if ( *((_BYTE *)v184 + 8) )
                  {
                    v185 = sub_18005AE04(v184, v178, v179);
                    if ( *(_DWORD *)(v185 + 1996) != v18 )
                    {
                      v186 = 943;
LABEL_434:
                      sub_180207168(v185, "CWICHeifEncoderFrame::Commit", v186);
                      goto LABEL_435;
                    }
                  }
                  goto LABEL_435;
                }
                sub_180070474(&v207, v178, v179, v180);
                if ( ++v175 >= 4 )
                {
                  sub_180070474(&ppBuffer, v147, v148, v149);
                  goto LABEL_406;
                }
              }
              if ( RequestContext != &RequestContext
                && (*((_BYTE *)RequestContext + 28) & 1) != 0
                && *((_BYTE *)RequestContext + 25) >= 4u )
              {
                sub_180079880(*((_QWORD *)RequestContext + 2), 125, qword_1805D7080, 0, v18);
              }
              v187 = (__int64 *)qword_180685260;
              if ( !qword_180685260 )
              {
                v187 = &qword_180684620;
                qword_180685260 = (__int64)&qword_180684620;
              }
              if ( *((_BYTE *)v187 + 8) )
              {
                v185 = sub_18005AE04(v187, v178, v179);
                if ( *(_DWORD *)(v185 + 1996) != v18 )
                {
                  v186 = 942;
                  goto LABEL_434;
                }
              }
LABEL_435:
              sub_180070474(&v207, v178, v179, v180);
              goto LABEL_289;
            }
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 124, qword_1805D7080, 0, v18);
            }
            v174 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v174 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v174 + 8) || (v172 = sub_18005AE04(v174, v147, v148), *(_DWORD *)(v172 + 1996) == v18) )
            {
LABEL_289:
              sub_180070474(&ppBuffer, v147, v148, v149);
              goto LABEL_29;
            }
            v173 = 937;
          }
          else
          {
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 123, qword_1805D7080, 0, v18);
            }
            v171 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v171 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( !*((_BYTE *)v171 + 8) )
              goto LABEL_289;
            v172 = sub_18005AE04(v171, v147, v148);
            if ( *(_DWORD *)(v172 + 1996) == v18 )
              goto LABEL_289;
            v173 = 933;
          }
          sub_180207168(v172, "CWICHeifEncoderFrame::Commit", v173);
          goto LABEL_289;
        }
LABEL_406:
        v18 = sub_1800DFF4C(a1);
        if ( v18 >= 0 )
          goto LABEL_29;
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 127, qword_1805D7080, 0, v18);
        }
        v183 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v183 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v183 + 8) )
          goto LABEL_29;
        v103 = sub_18005AE04(v183, v181, v182);
        if ( *(_DWORD *)(v103 + 1996) == v18 )
          goto LABEL_29;
        v104 = 949;
LABEL_172:
        sub_180207168(v103, "CWICHeifEncoderFrame::Commit", v104);
        goto LABEL_29;
      }
LABEL_82:
      v49 = *(_QWORD *)(a1 + 176);
      v211 = 0;
      sub_18005B17C(&v211);
      v18 = sub_1800E2F50(v49, &v211);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 96, qword_1805D7080, 0, v18);
        }
        v52 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v52 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v52 + 8) )
          goto LABEL_93;
        v53 = sub_18005AE04(v52, v50, v51);
        if ( *(_DWORD *)(v53 + 1996) == v18 )
          goto LABEL_93;
        v54 = 824;
        goto LABEL_92;
      }
      v55 = *v41;
      v56 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)*v41 + 32LL);
      sub_18005B17C(a1 + 208);
      v18 = v56(v55, v211, a1 + 208);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 97, qword_1805D7080, 0, v18);
        }
        v60 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v60 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v60 + 8) )
          goto LABEL_93;
        v53 = sub_18005AE04(v60, v57, v58);
        if ( *(_DWORD *)(v53 + 1996) == v18 )
          goto LABEL_93;
        v54 = 825;
LABEL_92:
        sub_180207168(v53, "CWICHeifEncoderFrame::Commit", v54);
LABEL_93:
        sub_18005B17C(&v211);
        goto LABEL_29;
      }
      v61 = *(_QWORD *)(a1 + 208);
      ppBuffer = 0;
      v62 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v61 + 240LL);
      sub_180070474(&ppBuffer, v57, v58, v59);
      v18 = v62(v61, &ppBuffer);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 98, qword_1805D7080, 0, v18);
        }
        v66 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v66 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v67 = sub_18005AE04(v66, v63, v64);
          if ( *(_DWORD *)(v67 + 1996) != v18 )
            sub_180207168(v67, "CWICHeifEncoderFrame::Commit", 828);
        }
        goto LABEL_114;
      }
      v68 = (_QWORD *)((__int64 (__fastcall *)(IMFMediaBuffer *, GUID *))ppBuffer->lpVtbl->Lock)(ppBuffer, &v216);
      v69 = *v68 - *(_QWORD *)(v42 + 8);
      if ( *v68 == *(_QWORD *)(v42 + 8) )
        v69 = v68[1] - *(_QWORD *)(v42 + 16);
      *(_QWORD *)cbMaxLength = 0;
      v12 = v69 != 0;
      v204 = v69 != 0;
      v18 = sub_18005C374(&ppBuffer, cbMaxLength);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 99, qword_1805D7080, 0, v18);
        }
        v73 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v73 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v73 + 8) )
        {
          v74 = sub_18005AE04(v73, v70, v71);
          if ( *(_DWORD *)(v74 + 1996) != v18 )
            sub_180207168(v74, "CWICHeifEncoderFrame::Commit", 834);
        }
        goto LABEL_127;
      }
      v212 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)cbMaxLength + 72LL))(
                          *(_QWORD *)cbMaxLength,
                          &v215);
      v209 = 0;
      sub_180070474(&v209, v75, v76, v77);
      v216 = *(GUID *)(a1 + 520);
      v18 = sub_180085E04(&v216, 0, 0, &v209);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 100, qword_1805D7080, 0, v18);
        }
        v81 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v81 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v81 + 8) )
        {
          v82 = sub_18005AE04(v81, v78, v79);
          if ( *(_DWORD *)(v82 + 1996) != v18 )
            sub_180207168(v82, "CWICHeifEncoderFrame::Commit", 839);
        }
        goto LABEL_138;
      }
      v207 = 0;
      sub_180070474(&v207, v78, v79, v80);
      v18 = sub_180088760(ppBuffer, v209, &v207);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 101, qword_1805D7080, 0, v18);
        }
        v86 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v86 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v86 + 8) )
          goto LABEL_150;
        v87 = sub_18005AE04(v86, v83, v84);
        if ( *(_DWORD *)(v87 + 1996) == v18 )
          goto LABEL_150;
        v88 = 842;
LABEL_149:
        sub_180207168(v87, "CWICHeifEncoderFrame::Commit", v88);
LABEL_150:
        sub_180070474(&v207, v83, v84, v85);
LABEL_138:
        sub_180070474(&v209, v78, v79, v80);
LABEL_127:
        sub_180070474(cbMaxLength, v70, v71, v72);
LABEL_114:
        sub_180070474(&ppBuffer, v63, v64, v65);
        goto LABEL_93;
      }
      v18 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 208) + 248LL))(*(_QWORD *)(a1 + 208), v207);
      if ( v18 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 102, qword_1805D7080, 0, v18);
        }
        v89 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v89 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v89 + 8) )
          goto LABEL_150;
        v87 = sub_18005AE04(v89, v83, v84);
        if ( *(_DWORD *)(v87 + 1996) == v18 )
          goto LABEL_150;
        v88 = 844;
        goto LABEL_149;
      }
      sub_180070474(&v207, v83, v84, v85);
      sub_180070474(&v209, v90, v91, v92);
      sub_180070474(cbMaxLength, v93, v94, v95);
      sub_180070474(&ppBuffer, v96, v97, v98);
      sub_18005B17C(&v211);
      goto LABEL_174;
    }
    if ( (__int64)(*(_QWORD *)(a1 + 304) - *(_QWORD *)(a1 + 296)) >> 3 )
    {
      v18 = sub_1800E0C94(a1);
      if ( v18 >= 0 )
        goto LABEL_56;
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 94, qword_1805D7080, 0, v18);
      }
      v45 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v45 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v45 + 8) )
        goto LABEL_446;
      v46 = sub_18005AE04(v45, v43, v44);
      if ( *(_DWORD *)(v46 + 1996) == v18 )
        goto LABEL_446;
      v47 = 807;
    }
    else
    {
      v18 = -2003292412;
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 95, qword_1805D7080, 0, -2003292412);
      }
      v48 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v48 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v48 + 8) )
        goto LABEL_446;
      v46 = sub_18005AE04(v48, v14, v15);
      if ( *(_DWORD *)(v46 + 1996) == -2003292412 )
        goto LABEL_446;
      v47 = 811;
    }
  }
  else
  {
    v18 = -2003292412;
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 89, qword_1805D7080, 0, -2003292412);
    }
    v188 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v188 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v188 + 8) )
      goto LABEL_446;
    v46 = sub_18005AE04(v188, v9, v10);
    if ( *(_DWORD *)(v46 + 1996) == -2003292412 )
      goto LABEL_446;
    v47 = 760;
  }
  sub_180207168(v46, "CWICHeifEncoderFrame::Commit", v47);
LABEL_446:
  sub_18005B17C(&v202);
LABEL_447:
  if ( *(_BYTE *)(a1 + 448) )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 200) + 32LL))(*(_QWORD *)(a1 + 200));
    *(_BYTE *)(a1 + 448) = 0;
  }
  sub_180070474(a1 + 200, v30, v31, v32);
  *(_QWORD *)(a1 + 440) = 0;
  v189 = MFGetSystemTime();
  v192 = *(_QWORD *)(a1 + 192);
  v193 = v189 - v2;
  if ( !v192 || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v192 + 320LL))(v192, qword_1805D10C0) )
  {
    v195 = *(_QWORD *)(a1 + 192);
    v194 = 0;
    v216 = guidExtendedType;
    if ( v195 )
    {
      v196 = (GUID *)(*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD))(*(_QWORD *)v195 + 280LL))(
                       v195,
                       &v215,
                       v191,
                       0);
      v197 = *(_QWORD *)(a1 + 192);
      v216 = *v196;
      v194 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v197 + 296LL))(v197);
    }
    if ( (unsigned int)dword_180681438 > 5
      && (unsigned __int8)sub_180001228(&dword_180681438, 0x400000000000LL, v191, v194) )
    {
      v212 = 0x1000000;
      LODWORD(v209) = v18;
      v11 = *(_QWORD *)(a1 + 232) == 0;
      cbMaxLength[0] = *(_DWORD *)(a1 + 460);
      LOBYTE(v5) = !v11;
      LODWORD(v211) = *(_DWORD *)(a1 + 472);
      v198 = *(_QWORD *)(a1 + 176);
      v207 = v193 / 10000;
      LODWORD(ppBuffer) = v5;
      v199 = *(unsigned __int8 *)(v198 + 236);
      *(_QWORD *)&v217 = L"CWICHeifEncoderFrame::Commit";
      *(_QWORD *)&v215 = &v216;
      LODWORD(v203) = v199;
      LODWORD(v202) = v194;
      sub_1800012F8(
        v199,
        (unsigned int)byte_18066563B,
        v191,
        v194,
        (__int64)&v215,
        (__int64)&v202,
        (__int64)&v217,
        (__int64)&v203,
        (__int64)&ppBuffer,
        (__int64)&v211,
        (__int64)cbMaxLength,
        (__int64)&v207,
        (__int64)&v209,
        (__int64)&v212);
    }
  }
  sub_180059CBC(v213, v190, v191, v194);
  sub_180059EAC(v205);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  return (unsigned int)v18;
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
