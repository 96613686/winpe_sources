# sub_1800DDAA0

- ea: `0x1800ddaa0`
- end: `0x1800dfa0f`
- name: `sub_1800DDAA0`
- size: `8047`
- prototype: ``
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
  int v4; // r14d
  __int64 v5; // rsi
  int v6; // ebx
  __int128 v7; // xmm0
  __int64 v8; // rdx
  bool v9; // zf
  char v10; // r13
  __int128 *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rdx
  int v15; // ebx
  __int64 *v16; // rcx
  __int64 v17; // rax
  IMFMediaBuffer *v18; // rbx
  _QWORD *v19; // r12
  HRESULT (__stdcall *Lock)(IMFMediaBuffer *, BYTE **, DWORD *, DWORD *); // rsi
  __int64 v21; // rdx
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 *v27; // rcx
  _BYTE *v28; // rsi
  __int64 v29; // rdx
  __int64 *v30; // rcx
  __int64 v31; // r12
  __int64 v32; // r13
  __int64 v33; // rdx
  __int64 *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // r9
  __int64 v37; // r8
  __int64 *v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rdx
  __int64 *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 v44; // rsi
  __int64 (__fastcall *v45)(__int64, __int64, __int64); // rbx
  __int64 v46; // rdx
  __int64 *v47; // rcx
  __int64 v48; // rsi
  __int64 (__fastcall *v49)(__int64, IMFMediaBuffer **); // rbx
  __int64 v50; // rdx
  __int64 *v51; // rcx
  __int64 v52; // rax
  _QWORD *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 *v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 *v66; // rcx
  __int64 v67; // rdx
  __int64 *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // r8
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int64 *v73; // rcx
  __int64 v74; // rdx
  __int64 *v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  int v79; // r9d
  __int64 v80; // rdx
  __int64 *v81; // rcx
  __int64 v82; // rdx
  __int64 *v83; // rcx
  __int64 v84; // rdx
  __int64 *v85; // rcx
  __int64 v86; // rdx
  __int64 *v87; // rcx
  __int64 v88; // rdx
  __int64 *v89; // rcx
  __int64 v90; // rdx
  __int64 *v91; // rcx
  __int64 v92; // r8
  __int64 v93; // rdx
  __int64 v94; // rdx
  __int64 *v95; // rcx
  int v96; // r12d
  __int64 v97; // rdx
  __int64 *v98; // rcx
  __int64 v99; // rsi
  __int64 (__fastcall *v100)(__int64, IMFMediaBuffer **); // rbx
  __int64 v101; // rdx
  __int64 *v102; // rcx
  __int64 v103; // rax
  __int64 v104; // r8
  int v105; // ebx
  int v106; // eax
  __int64 v107; // rdx
  __int64 *v108; // rcx
  __int64 v109; // rcx
  __int64 v110; // rdx
  __int64 *v111; // rcx
  __int64 v112; // rdx
  __int64 *v113; // rcx
  __int64 v114; // rax
  __int64 v115; // r8
  __int64 v116; // rdx
  __int64 *v117; // rcx
  __int64 v118; // rdx
  __int64 *v119; // rcx
  __int64 v120; // rdx
  __int64 *v121; // rcx
  __int64 v122; // rdx
  __int64 *v123; // rcx
  __int64 v124; // rdx
  __int64 *v125; // rcx
  __int64 v126; // rsi
  __int64 (__fastcall *v127)(__int64, IMFMediaBuffer **); // rbx
  __int64 v128; // rdx
  __int64 *v129; // rcx
  __int64 v130; // rax
  __int64 v131; // r8
  __int64 v132; // rdx
  __int64 *v133; // rcx
  unsigned int v134; // r13d
  __int64 v135; // rsi
  __int64 (__fastcall *v136)(__int64, _QWORD, __int64 *); // rbx
  __int64 v137; // rdx
  __int64 v138; // rdx
  __int64 v139; // rdx
  __int64 *v140; // rcx
  __int64 *v141; // rcx
  __int64 v142; // rax
  __int64 v143; // r8
  __int64 *v144; // rcx
  __int64 *v145; // rcx
  MFTIME v146; // rax
  __int64 v147; // r8
  __int64 v148; // rcx
  MFTIME v149; // rsi
  __int64 v150; // rcx
  __int64 v151; // r9
  GUID *v152; // rax
  __int64 v153; // rcx
  int v154; // r8d
  int v155; // r9d
  __int64 v156; // rax
  int v157; // ecx
  IMFMediaBuffer *ppBuffer; // [rsp+78h] [rbp-90h] BYREF
  __int64 v160; // [rsp+80h] [rbp-88h] BYREF
  MFTIME v161; // [rsp+88h] [rbp-80h] BYREF
  char v162; // [rsp+90h] [rbp-78h]
  _BYTE v163[7]; // [rsp+91h] [rbp-77h] BYREF
  DWORD cbMaxLength[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v165; // [rsp+A0h] [rbp-68h] BYREF
  char v166[8]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v167; // [rsp+B0h] [rbp-58h] BYREF
  char v168[8]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v169; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v170; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v171[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v172; // [rsp+E0h] [rbp-28h]
  __int128 v173; // [rsp+E8h] [rbp-20h] BYREF
  GUID v174; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v175; // [rsp+108h] [rbp+0h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v161 = MFGetSystemTime();
  v2 = v161;
  sub_180059AB4(v163, "CWICHeifEncoderFrame::Commit", 755);
  v4 = 0;
  if ( *(_BYTE *)(qword_180685260 + 8) && *(_QWORD *)(a1 + 192) )
  {
    v5 = sub_18005AE04(qword_180685260, v3);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 192) + 296LL))(*(_QWORD *)(a1 + 192));
    v7 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)(a1 + 192) + 280LL))(
                      *(_QWORD *)(a1 + 192),
                      &v174);
    *(_DWORD *)(v5 + 2016) = v6;
    *(_OWORD *)(v5 + 2000) = v7;
  }
  v171[0] = "CWICHeifEncoderFrame::Commit";
  v172 = 15;
  v171[1] = 0;
  sub_18005B28C(0, 15, "=>%s", "CWICHeifEncoderFrame::Commit");
  v9 = *(_DWORD *)(a1 + 480) == 2;
  v10 = 0;
  v160 = 0;
  v170 = 0;
  v162 = 0;
  if ( !v9 )
  {
    v15 = -2003292412;
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 89, qword_1805D7080, 0, -2003292412);
    }
    v145 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v145 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v145 + 8) )
      goto LABEL_447;
    v35 = sub_18005AE04(v145, v8);
    if ( *(_DWORD *)(v35 + 1996) == -2003292412 )
      goto LABEL_447;
    v37 = 760;
LABEL_445:
    v36 = 2291674884LL;
    goto LABEL_446;
  }
  *(_DWORD *)(a1 + 480) = 3;
  v11 = (__int128 *)sub_1800E29E0(a1);
  v13 = *(_QWORD *)(a1 + 176);
  v175 = *v11;
  if ( *(_BYTE *)(v13 + 236) )
  {
    v165 = 0;
    ppBuffer = 0;
    sub_18005B17C(&ppBuffer);
    v15 = sub_1800E2F50(v13, &ppBuffer);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 90, qword_1805D7080, 0, v15);
      }
      v16 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v16 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = sub_18005AE04(v16, v14);
        if ( *(_DWORD *)(v17 + 1996) != v15 )
          sub_180207168(v17, "CWICHeifEncoderFrame::Commit", 772, (unsigned int)v15);
      }
      sub_18005B17C(&ppBuffer);
      sub_18005B17C(&v165);
      goto LABEL_447;
    }
    v18 = ppBuffer;
    v19 = (_QWORD *)(a1 + 208);
    Lock = ppBuffer->lpVtbl->Lock;
    sub_18005B17C(a1 + 208);
    v15 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64))Lock)(v18, a1 + 208);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 91, qword_1805D7080, 0, v15);
      }
      v22 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v22 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v22 + 8) )
        goto LABEL_28;
      v23 = sub_18005AE04(v22, v21);
      if ( *(_DWORD *)(v23 + 1996) == v15 )
        goto LABEL_28;
      v24 = 773;
LABEL_27:
      sub_180207168(v23, "CWICHeifEncoderFrame::Commit", v24, (unsigned int)v15);
LABEL_28:
      sub_18005B17C(&ppBuffer);
      sub_18005B17C(&v165);
LABEL_29:
      sub_18005B17C(&v160);
      v2 = v161;
      goto LABEL_448;
    }
    if ( !*(_DWORD *)(a1 + 476) )
    {
      v25 = *v19;
      v168[0] = 0;
      v173 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int128 *, char *))(*(_QWORD *)v25 + 48LL))(v25, &v173, v168);
      if ( v15 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 92, qword_1805D7080, 0, v15);
        }
        v27 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v27 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v27 + 8) )
          goto LABEL_28;
        v23 = sub_18005AE04(v27, v26);
        if ( *(_DWORD *)(v23 + 1996) == v15 )
          goto LABEL_28;
        v24 = 783;
        goto LABEL_27;
      }
      if ( !(unsigned int)sub_1802B69B0(&v173, "HEVC", 16) || !(unsigned int)sub_1802B69B0(&v173, "AV01", 16) )
        v175 = v173;
    }
    v28 = (_BYTE *)(a1 + 448);
    if ( *(_BYTE *)(a1 + 448) )
    {
      v15 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->GetMaxLength)(ppBuffer, *v19);
      if ( v15 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 93, qword_1805D7080, 0, v15);
        }
        v30 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v30 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v30 + 8) )
          goto LABEL_28;
        v23 = sub_18005AE04(v30, v29);
        if ( *(_DWORD *)(v23 + 1996) == v15 )
          goto LABEL_28;
        v24 = 796;
        goto LABEL_27;
      }
    }
    sub_18005B17C(&ppBuffer);
    sub_18005B17C(&v165);
    goto LABEL_56;
  }
  v28 = (_BYTE *)(a1 + 448);
  if ( *(_BYTE *)(a1 + 448) )
    goto LABEL_81;
  if ( *(_QWORD *)(a1 + 512) )
  {
LABEL_56:
    if ( !*v28 )
    {
      if ( !*(_QWORD *)(a1 + 512) )
        goto LABEL_174;
      v31 = a1 + 512;
      v32 = a1 + 512;
      goto LABEL_82;
    }
LABEL_81:
    v31 = a1 + 512;
    v32 = a1 + 512;
    if ( !*(_QWORD *)(a1 + 512) )
    {
      sub_18005B17C(a1 + 208);
      v15 = sub_1800E1CD0(
              a1,
              *(_QWORD *)(a1 + 200),
              *(_DWORD *)(a1 + 224),
              *(_DWORD *)(a1 + 228),
              (__int64)&v175,
              (__int64)v28,
              a1 + 208);
      if ( v15 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 103, qword_1805D7080, 0, v15);
        }
        v68 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v68 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v68 + 8) )
          goto LABEL_29;
        v69 = sub_18005AE04(v68, v67);
        if ( *(_DWORD *)(v69 + 1996) == v15 )
          goto LABEL_29;
        v70 = 850;
        goto LABEL_172;
      }
      sub_180070474(a1 + 200);
      *(_QWORD *)(a1 + 440) = 0;
      v10 = 0;
LABEL_174:
      v71 = *(_QWORD *)(a1 + 232);
      if ( v71 )
      {
        LODWORD(v167) = 0;
        cbMaxLength[0] = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, DWORD *))(*(_QWORD *)v71 + 24LL))(v71, &v167, cbMaxLength);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 104, qword_1805D7080, 0, v15);
          }
          v73 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v73 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v73 + 8) )
            goto LABEL_29;
          v69 = sub_18005AE04(v73, v72);
          if ( *(_DWORD *)(v69 + 1996) == v15 )
            goto LABEL_29;
          v70 = 860;
          goto LABEL_172;
        }
        v15 = sub_1800DD10C(a1, (unsigned int)v167, cbMaxLength[0]);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 105, qword_1805D7080, 0, v15);
          }
          v75 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v75 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v75 + 8) )
            goto LABEL_29;
          v69 = sub_18005AE04(v75, v74);
          if ( *(_DWORD *)(v69 + 1996) == v15 )
            goto LABEL_29;
          v70 = 862;
          goto LABEL_172;
        }
        v76 = *(_QWORD *)(a1 + 440);
        v77 = *(_QWORD *)(a1 + 232);
        v78 = *(unsigned int *)(a1 + 452);
        v79 = *(_DWORD *)(a1 + 452);
        *((_QWORD *)&v173 + 1) = __PAIR64__(cbMaxLength[0], v167);
        *(_QWORD *)&v173 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, __int64))(*(_QWORD *)v77 + 56LL))(
                v77,
                &v173,
                v78,
                cbMaxLength[0] * v79,
                v76);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 106, qword_1805D7080, 0, v15);
          }
          v81 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v81 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v81 + 8) )
            goto LABEL_29;
          v69 = sub_18005AE04(v81, v80);
          if ( *(_DWORD *)(v69 + 1996) == v15 )
            goto LABEL_29;
          v70 = 865;
          goto LABEL_172;
        }
        sub_18005B17C(&v160);
        v15 = sub_1800E1CD0(a1, *(_QWORD *)(a1 + 200), v167, cbMaxLength[0], (__int64)&v175, a1 + 448, (__int64)&v160);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 107, qword_1805D7080, 0, v15);
          }
          v83 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v83 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v83 + 8) )
            goto LABEL_29;
          v69 = sub_18005AE04(v83, v82);
          if ( *(_DWORD *)(v69 + 1996) == v15 )
            goto LABEL_29;
          v70 = 867;
          goto LABEL_172;
        }
        v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 208) + 184LL))(
                *(_QWORD *)(a1 + 208),
                v160);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 108, qword_1805D7080, 0, v15);
          }
          v85 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v85 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v85 + 8) )
            goto LABEL_29;
          v69 = sub_18005AE04(v85, v84);
          if ( *(_DWORD *)(v69 + 1996) == v15 )
            goto LABEL_29;
          v70 = 868;
          goto LABEL_172;
        }
      }
      v15 = sub_1800E1284(a1);
      if ( v15 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 109, qword_1805D7080, 0, v15);
        }
        v87 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v87 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v87 + 8) )
          goto LABEL_29;
        v69 = sub_18005AE04(v87, v86);
        if ( *(_DWORD *)(v69 + 1996) == v15 )
          goto LABEL_29;
        v70 = 873;
        goto LABEL_172;
      }
      v15 = sub_1800DFA18(a1);
      if ( v15 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 110, qword_1805D7080, 0, v15);
        }
        v89 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v89 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v89 + 8) )
          goto LABEL_29;
        v69 = sub_18005AE04(v89, v88);
        if ( *(_DWORD *)(v69 + 1996) == v15 )
          goto LABEL_29;
        v70 = 876;
        goto LABEL_172;
      }
      v15 = sub_1800DFCB4(a1);
      if ( v15 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 111, qword_1805D7080, 0, v15);
        }
        v91 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v91 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v91 + 8) )
          goto LABEL_29;
        v69 = sub_18005AE04(v91, v90);
        if ( *(_DWORD *)(v69 + 1996) == v15 )
          goto LABEL_29;
        v70 = 879;
        goto LABEL_172;
      }
      v92 = *(_QWORD *)(a1 + 112);
      v93 = *(_QWORD *)(a1 + 208);
      v163[0] = 0;
      v166[0] = 0;
      v15 = sub_1800ED83C((int)a1 + 120, v93, v92, 0, (__int64)v163, (__int64)v166);
      if ( v15 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 112, qword_1805D7080, 0, v15);
        }
        v95 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v95 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v95 + 8) )
          goto LABEL_29;
        v69 = sub_18005AE04(v95, v94);
        if ( *(_DWORD *)(v69 + 1996) == v15 )
          goto LABEL_29;
        v70 = 884;
        goto LABEL_172;
      }
      v96 = 0;
      LODWORD(v167) = 0;
      if ( v166[0] )
      {
        v15 = sub_1800EBE44(a1 + 120, &v167);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 113, qword_1805D7080, 0, v15);
          }
          v98 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v98 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v98 + 8) )
            goto LABEL_29;
          v69 = sub_18005AE04(v98, v97);
          if ( *(_DWORD *)(v69 + 1996) == v15 )
            goto LABEL_29;
          v70 = 889;
          goto LABEL_172;
        }
        v96 = v167;
      }
      if ( *(_DWORD *)(a1 + 472) )
      {
        LODWORD(v167) = 0;
        cbMaxLength[0] = 0;
        sub_1800E7990(a1 + 472, &v167, cbMaxLength);
        v99 = *(_QWORD *)(a1 + 208);
        ppBuffer = 0;
        v100 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v99 + 240LL);
        sub_180070474(&ppBuffer);
        v15 = v100(v99, &ppBuffer);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 114, qword_1805D7080, 0, v15);
          }
          v102 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v102 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v102 + 8) )
            goto LABEL_289;
          v103 = sub_18005AE04(v102, v101);
          if ( *(_DWORD *)(v103 + 1996) == v15 )
            goto LABEL_289;
          v104 = 901;
          goto LABEL_288;
        }
        v105 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->GetMaxLength)(ppBuffer);
        v106 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->GetCurrentLength)(ppBuffer);
        sub_180088AB8(v106, v105, v167, cbMaxLength[0], (__int64)&v167, (__int64)cbMaxLength);
        ((void (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
          ppBuffer,
          (unsigned int)v167);
        ((void (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl[1].QueryInterface)(ppBuffer, cbMaxLength[0]);
        v15 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**(_QWORD **)(a1 + 208) + 248LL))(
                *(_QWORD *)(a1 + 208),
                ppBuffer);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 115, qword_1805D7080, 0, v15);
          }
          v108 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v108 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v108 + 8) )
            goto LABEL_289;
          v103 = sub_18005AE04(v108, v107);
          if ( *(_DWORD *)(v103 + 1996) == v15 )
            goto LABEL_289;
          v104 = 907;
LABEL_288:
          sub_180207168(v103, "CWICHeifEncoderFrame::Commit", v104, (unsigned int)v15);
          goto LABEL_289;
        }
        sub_180070474(&ppBuffer);
      }
      v109 = *(_QWORD *)(a1 + 240);
      if ( v109 )
      {
        cbMaxLength[0] = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v109 + 56LL))(
                v109,
                0,
                0,
                cbMaxLength);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 116, qword_1805D7080, 0, v15);
          }
          v111 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v111 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v111 + 8) )
            goto LABEL_29;
          v69 = sub_18005AE04(v111, v110);
          if ( *(_DWORD *)(v69 + 1996) == v15 )
            goto LABEL_29;
          v70 = 914;
          goto LABEL_172;
        }
        ppBuffer = 0;
        v165 = 0;
        sub_180070474(&ppBuffer);
        v15 = MFCreateMemoryBuffer(cbMaxLength[0], &ppBuffer);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 117, qword_1805D7080, 0, v15);
          }
          v113 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v113 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v113 + 8) )
            goto LABEL_289;
          v114 = sub_18005AE04(v113, v112);
          if ( *(_DWORD *)(v114 + 1996) == v15 )
            goto LABEL_289;
          v115 = 918;
          goto LABEL_322;
        }
        v15 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
                ppBuffer,
                &v165,
                0,
                0);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 118, qword_1805D7080, 0, v15);
          }
          v117 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v117 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v117 + 8) )
            goto LABEL_289;
          v114 = sub_18005AE04(v117, v116);
          if ( *(_DWORD *)(v114 + 1996) == v15 )
            goto LABEL_289;
          v115 = 919;
          goto LABEL_322;
        }
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, DWORD *))(**(_QWORD **)(a1 + 240) + 56LL))(
                *(_QWORD *)(a1 + 240),
                cbMaxLength[0],
                v165,
                cbMaxLength);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 119, qword_1805D7080, 0, v15);
          }
          v119 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v119 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v119 + 8) )
            goto LABEL_289;
          v114 = sub_18005AE04(v119, v118);
          if ( *(_DWORD *)(v114 + 1996) == v15 )
            goto LABEL_289;
          v115 = 920;
          goto LABEL_322;
        }
        v15 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 120, qword_1805D7080, 0, v15);
          }
          v121 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v121 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v121 + 8) )
            goto LABEL_289;
          v114 = sub_18005AE04(v121, v120);
          if ( *(_DWORD *)(v114 + 1996) == v15 )
            goto LABEL_289;
          v115 = 921;
          goto LABEL_322;
        }
        v15 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
                ppBuffer,
                cbMaxLength[0]);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 121, qword_1805D7080, 0, v15);
          }
          v123 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v123 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v123 + 8) )
            goto LABEL_289;
          v114 = sub_18005AE04(v123, v122);
          if ( *(_DWORD *)(v114 + 1996) == v15 )
            goto LABEL_289;
          v115 = 922;
          goto LABEL_322;
        }
        v15 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**(_QWORD **)(a1 + 208) + 168LL))(
                *(_QWORD *)(a1 + 208),
                ppBuffer);
        if ( v15 < 0 )
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 122, qword_1805D7080, 0, v15);
          }
          v125 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v125 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v125 + 8) )
            goto LABEL_289;
          v114 = sub_18005AE04(v125, v124);
          if ( *(_DWORD *)(v114 + 1996) == v15 )
            goto LABEL_289;
          v115 = 924;
LABEL_322:
          sub_180207168(v114, "CWICHeifEncoderFrame::Commit", v115, (unsigned int)v15);
          goto LABEL_289;
        }
        sub_180070474(&ppBuffer);
      }
      if ( *(_QWORD *)(a1 + 512) && (v96 || *(_DWORD *)(a1 + 472) || v10) )
      {
        v126 = *(_QWORD *)(a1 + 208);
        ppBuffer = 0;
        v127 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v126 + 176LL);
        sub_180070474(&ppBuffer);
        v15 = v127(v126, &ppBuffer);
        if ( v15 >= 0 )
        {
          v15 = sub_1800E5384(a1, (_DWORD)ppBuffer, v160, v96, v10, (__int64)&v170);
          if ( v15 >= 0 )
          {
            v134 = 0;
            while ( 1 )
            {
              v135 = *(_QWORD *)(a1 + 208);
              v165 = 0;
              v136 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v135 + 216LL);
              sub_180070474(&v165);
              v15 = v136(v135, v134, &v165);
              if ( v15 < 0 )
                break;
              v15 = sub_1800E5384(a1, v165, 0, v96, v162, (__int64)&v170);
              if ( v15 < 0 )
              {
                if ( RequestContext != &RequestContext
                  && (*((_BYTE *)RequestContext + 28) & 1) != 0
                  && *((_BYTE *)RequestContext + 25) >= 4u )
                {
                  sub_180079880(*((_QWORD *)RequestContext + 2), 126, qword_1805D7080, 0, v15);
                }
                v141 = (__int64 *)qword_180685260;
                if ( !qword_180685260 )
                {
                  v141 = &qword_180684620;
                  qword_180685260 = (__int64)&qword_180684620;
                }
                if ( *((_BYTE *)v141 + 8) )
                {
                  v142 = sub_18005AE04(v141, v138);
                  if ( *(_DWORD *)(v142 + 1996) != v15 )
                  {
                    v143 = 943;
LABEL_434:
                    sub_180207168(v142, "CWICHeifEncoderFrame::Commit", v143, (unsigned int)v15);
                    goto LABEL_435;
                  }
                }
                goto LABEL_435;
              }
              sub_180070474(&v165);
              if ( ++v134 >= 4 )
              {
                sub_180070474(&ppBuffer);
                goto LABEL_406;
              }
            }
            if ( RequestContext != &RequestContext
              && (*((_BYTE *)RequestContext + 28) & 1) != 0
              && *((_BYTE *)RequestContext + 25) >= 4u )
            {
              sub_180079880(*((_QWORD *)RequestContext + 2), 125, qword_1805D7080, 0, v15);
            }
            v144 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v144 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( *((_BYTE *)v144 + 8) )
            {
              v142 = sub_18005AE04(v144, v137);
              if ( *(_DWORD *)(v142 + 1996) != v15 )
              {
                v143 = 942;
                goto LABEL_434;
              }
            }
LABEL_435:
            sub_180070474(&v165);
            goto LABEL_289;
          }
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 124, qword_1805D7080, 0, v15);
          }
          v133 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v133 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v133 + 8) || (v130 = sub_18005AE04(v133, v132), *(_DWORD *)(v130 + 1996) == v15) )
          {
LABEL_289:
            sub_180070474(&ppBuffer);
            goto LABEL_29;
          }
          v131 = 937;
        }
        else
        {
          if ( RequestContext != &RequestContext
            && (*((_BYTE *)RequestContext + 28) & 1) != 0
            && *((_BYTE *)RequestContext + 25) >= 4u )
          {
            sub_180079880(*((_QWORD *)RequestContext + 2), 123, qword_1805D7080, 0, v15);
          }
          v129 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v129 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( !*((_BYTE *)v129 + 8) )
            goto LABEL_289;
          v130 = sub_18005AE04(v129, v128);
          if ( *(_DWORD *)(v130 + 1996) == v15 )
            goto LABEL_289;
          v131 = 933;
        }
        sub_180207168(v130, "CWICHeifEncoderFrame::Commit", v131, (unsigned int)v15);
        goto LABEL_289;
      }
LABEL_406:
      v15 = sub_1800DFF4C(a1);
      if ( v15 >= 0 )
        goto LABEL_29;
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 127, qword_1805D7080, 0, v15);
      }
      v140 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v140 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v140 + 8) )
        goto LABEL_29;
      v69 = sub_18005AE04(v140, v139);
      if ( *(_DWORD *)(v69 + 1996) == v15 )
        goto LABEL_29;
      v70 = 949;
LABEL_172:
      sub_180207168(v69, "CWICHeifEncoderFrame::Commit", v70, (unsigned int)v15);
      goto LABEL_29;
    }
LABEL_82:
    v39 = *(_QWORD *)(a1 + 176);
    v169 = 0;
    sub_18005B17C(&v169);
    v15 = sub_1800E2F50(v39, &v169);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 96, qword_1805D7080, 0, v15);
      }
      v41 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v41 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v41 + 8) )
        goto LABEL_93;
      v42 = sub_18005AE04(v41, v40);
      if ( *(_DWORD *)(v42 + 1996) == v15 )
        goto LABEL_93;
      v43 = 824;
      goto LABEL_92;
    }
    v44 = *(_QWORD *)v31;
    v45 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)v31 + 32LL);
    sub_18005B17C(a1 + 208);
    v15 = v45(v44, v169, a1 + 208);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 97, qword_1805D7080, 0, v15);
      }
      v47 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v47 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v47 + 8) )
        goto LABEL_93;
      v42 = sub_18005AE04(v47, v46);
      if ( *(_DWORD *)(v42 + 1996) == v15 )
        goto LABEL_93;
      v43 = 825;
LABEL_92:
      sub_180207168(v42, "CWICHeifEncoderFrame::Commit", v43, (unsigned int)v15);
LABEL_93:
      sub_18005B17C(&v169);
      goto LABEL_29;
    }
    v48 = *(_QWORD *)(a1 + 208);
    ppBuffer = 0;
    v49 = *(__int64 (__fastcall **)(__int64, IMFMediaBuffer **))(*(_QWORD *)v48 + 240LL);
    sub_180070474(&ppBuffer);
    v15 = v49(v48, &ppBuffer);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 98, qword_1805D7080, 0, v15);
      }
      v51 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v51 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v51 + 8) )
      {
        v52 = sub_18005AE04(v51, v50);
        if ( *(_DWORD *)(v52 + 1996) != v15 )
          sub_180207168(v52, "CWICHeifEncoderFrame::Commit", 828, (unsigned int)v15);
      }
      goto LABEL_114;
    }
    v53 = (_QWORD *)((__int64 (__fastcall *)(IMFMediaBuffer *, GUID *))ppBuffer->lpVtbl->Lock)(ppBuffer, &v174);
    v54 = *v53 - *(_QWORD *)(v32 + 8);
    if ( *v53 == *(_QWORD *)(v32 + 8) )
      v54 = v53[1] - *(_QWORD *)(v32 + 16);
    *(_QWORD *)cbMaxLength = 0;
    v10 = v54 != 0;
    v162 = v54 != 0;
    v15 = sub_18005C374(&ppBuffer, cbMaxLength);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 99, qword_1805D7080, 0, v15);
      }
      v56 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v56 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v57 = sub_18005AE04(v56, v55);
        if ( *(_DWORD *)(v57 + 1996) != v15 )
          sub_180207168(v57, "CWICHeifEncoderFrame::Commit", 834, (unsigned int)v15);
      }
      goto LABEL_127;
    }
    v170 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)cbMaxLength + 72LL))(
                        *(_QWORD *)cbMaxLength,
                        &v173);
    v167 = 0;
    sub_180070474(&v167);
    v174 = *(GUID *)(a1 + 520);
    v15 = sub_180085E04(&v174, 0, 0, &v167);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 100, qword_1805D7080, 0, v15);
      }
      v59 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v59 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v60 = sub_18005AE04(v59, v58);
        if ( *(_DWORD *)(v60 + 1996) != v15 )
          sub_180207168(v60, "CWICHeifEncoderFrame::Commit", 839, (unsigned int)v15);
      }
      goto LABEL_138;
    }
    v165 = 0;
    sub_180070474(&v165);
    v15 = sub_180088760(ppBuffer, v167, &v165);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 101, qword_1805D7080, 0, v15);
      }
      v62 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v62 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v62 + 8) )
        goto LABEL_150;
      v63 = sub_18005AE04(v62, v61);
      if ( *(_DWORD *)(v63 + 1996) == v15 )
        goto LABEL_150;
      v64 = 842;
LABEL_149:
      sub_180207168(v63, "CWICHeifEncoderFrame::Commit", v64, (unsigned int)v15);
LABEL_150:
      sub_180070474(&v165);
LABEL_138:
      sub_180070474(&v167);
LABEL_127:
      sub_180070474(cbMaxLength);
LABEL_114:
      sub_180070474(&ppBuffer);
      goto LABEL_93;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 208) + 248LL))(*(_QWORD *)(a1 + 208), v165);
    if ( v15 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 102, qword_1805D7080, 0, v15);
      }
      v66 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v66 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v66 + 8) )
        goto LABEL_150;
      v63 = sub_18005AE04(v66, v65);
      if ( *(_DWORD *)(v63 + 1996) == v15 )
        goto LABEL_150;
      v64 = 844;
      goto LABEL_149;
    }
    sub_180070474(&v165);
    sub_180070474(&v167);
    sub_180070474(cbMaxLength);
    sub_180070474(&ppBuffer);
    sub_18005B17C(&v169);
    goto LABEL_174;
  }
  if ( !((__int64)(*(_QWORD *)(a1 + 304) - *(_QWORD *)(a1 + 296)) >> 3) )
  {
    v15 = -2003292412;
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 95, qword_1805D7080, 0, -2003292412);
    }
    v38 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v38 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v38 + 8) )
      goto LABEL_447;
    v35 = sub_18005AE04(v38, v12);
    if ( *(_DWORD *)(v35 + 1996) == -2003292412 )
      goto LABEL_447;
    v37 = 811;
    goto LABEL_445;
  }
  v15 = sub_1800E0C94(a1);
  if ( v15 >= 0 )
    goto LABEL_56;
  if ( RequestContext != &RequestContext
    && (*((_BYTE *)RequestContext + 28) & 1) != 0
    && *((_BYTE *)RequestContext + 25) >= 4u )
  {
    sub_180079880(*((_QWORD *)RequestContext + 2), 94, qword_1805D7080, 0, v15);
  }
  v34 = (__int64 *)qword_180685260;
  if ( !qword_180685260 )
  {
    v34 = &qword_180684620;
    qword_180685260 = (__int64)&qword_180684620;
  }
  if ( !*((_BYTE *)v34 + 8) )
    goto LABEL_447;
  v35 = sub_18005AE04(v34, v33);
  if ( *(_DWORD *)(v35 + 1996) == v15 )
    goto LABEL_447;
  v36 = (unsigned int)v15;
  v37 = 807;
LABEL_446:
  sub_180207168(v35, "CWICHeifEncoderFrame::Commit", v37, v36);
LABEL_447:
  sub_18005B17C(&v160);
LABEL_448:
  if ( *(_BYTE *)(a1 + 448) )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 200) + 32LL))(*(_QWORD *)(a1 + 200));
    *(_BYTE *)(a1 + 448) = 0;
  }
  sub_180070474(a1 + 200);
  *(_QWORD *)(a1 + 440) = 0;
  v146 = MFGetSystemTime();
  v148 = *(_QWORD *)(a1 + 192);
  v149 = v146 - v2;
  if ( !v148 || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v148 + 320LL))(v148, qword_1805D10C0) )
  {
    v150 = *(_QWORD *)(a1 + 192);
    v151 = 0;
    v174 = guidExtendedType;
    if ( v150 )
    {
      v152 = (GUID *)(*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD))(*(_QWORD *)v150 + 280LL))(
                       v150,
                       &v173,
                       v147,
                       0);
      v153 = *(_QWORD *)(a1 + 192);
      v174 = *v152;
      v151 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v153 + 296LL))(v153);
    }
    if ( (unsigned int)dword_180681438 > 5
      && (unsigned __int8)sub_180001228(&dword_180681438, 0x400000000000LL, v147, v151) )
    {
      v170 = 0x1000000;
      LODWORD(v167) = v15;
      v9 = *(_QWORD *)(a1 + 232) == 0;
      cbMaxLength[0] = *(_DWORD *)(a1 + 460);
      LOBYTE(v4) = !v9;
      LODWORD(v169) = *(_DWORD *)(a1 + 472);
      v156 = *(_QWORD *)(a1 + 176);
      v165 = v149 / 10000;
      LODWORD(ppBuffer) = v4;
      v157 = *(unsigned __int8 *)(v156 + 236);
      *(_QWORD *)&v175 = L"CWICHeifEncoderFrame::Commit";
      *(_QWORD *)&v173 = &v174;
      LODWORD(v161) = v157;
      LODWORD(v160) = v155;
      sub_1800012F8(
        v157,
        (unsigned int)byte_18066563B,
        v154,
        v155,
        (__int64)&v173,
        (__int64)&v160,
        (__int64)&v175,
        (__int64)&v161,
        (__int64)&ppBuffer,
        (__int64)&v169,
        (__int64)cbMaxLength,
        (__int64)&v165,
        (__int64)&v167,
        (__int64)&v170);
    }
  }
  sub_180059CBC(v171);
  sub_180059EAC(v163);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  return (unsigned int)v15;
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
