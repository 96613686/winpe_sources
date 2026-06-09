# WriteDBEntry6

- ea: `0x18001bde8`
- end: `0x18001c9d4`
- name: `WriteDBEntry6`
- size: `3052`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a008`
- `0x18001a160`
- `0x18001a338`
- `0x18001a5ec`
- `0x18001a778`
- `0x18001a978`
- `0x18001aa28`

## callees

- `0x180002854`
- `0x18000f144`
- `0x180013890`
- `0x18001ac00`
- `0x18001bde8`
- `0x18008f788`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetUpdate` at `0x18001c917`
- `ESENT!JetUpdate` at `0x18001c917`
- `ESENT!JetBeginTransaction` at `0x18001be79`
- `ESENT!JetBeginTransaction` at `0x18001befe`
- `ESENT!JetBeginTransaction` at `0x18001be79`
- `ESENT!JetBeginTransaction` at `0x18001befe`
- `ESENT!JetPrepareUpdate` at `0x18001beae`
- `ESENT!JetPrepareUpdate` at `0x18001bf4c`
- `ESENT!JetPrepareUpdate` at `0x18001c95b`
- `ESENT!JetPrepareUpdate` at `0x18001beae`
- `ESENT!JetPrepareUpdate` at `0x18001bf4c`
- `ESENT!JetPrepareUpdate` at `0x18001c95b`
- `ESENT!JetSetColumn` at `0x18001bfce`
- `ESENT!JetSetColumn` at `0x18001c014`
- `ESENT!JetSetColumn` at `0x18001c0ab`
- `ESENT!JetSetColumn` at `0x18001c154`
- `ESENT!JetSetColumn` at `0x18001c19a`
- `ESENT!JetSetColumn` at `0x18001c238`
- `ESENT!JetSetColumn` at `0x18001c2c5`
- `ESENT!JetSetColumn` at `0x18001c358`
- `ESENT!JetSetColumn` at `0x18001c3fc`
- `ESENT!JetSetColumn` at `0x18001c4a0`
- `ESENT!JetSetColumn` at `0x18001c544`
- `ESENT!JetSetColumn` at `0x18001c5e2`
- `ESENT!JetSetColumn` at `0x18001c680`
- `ESENT!JetSetColumn` at `0x18001c719`
- `ESENT!JetSetColumn` at `0x18001c7ba`
- `ESENT!JetSetColumn` at `0x18001c853`
- `ESENT!JetSetColumn` at `0x18001c8f2`
- `ESENT!JetSetColumn` at `0x18001bfce`
- `ESENT!JetSetColumn` at `0x18001c014`
- `ESENT!JetSetColumn` at `0x18001c0ab`
- `ESENT!JetSetColumn` at `0x18001c154`
- `ESENT!JetSetColumn` at `0x18001c19a`
- `ESENT!JetSetColumn` at `0x18001c238`
- `ESENT!JetSetColumn` at `0x18001c2c5`
- `ESENT!JetSetColumn` at `0x18001c358`
- `ESENT!JetSetColumn` at `0x18001c3fc`
- `ESENT!JetSetColumn` at `0x18001c4a0`
- `ESENT!JetSetColumn` at `0x18001c544`
- `ESENT!JetSetColumn` at `0x18001c5e2`
- `ESENT!JetSetColumn` at `0x18001c680`
- `ESENT!JetSetColumn` at `0x18001c719`
- `ESENT!JetSetColumn` at `0x18001c7ba`
- `ESENT!JetSetColumn` at `0x18001c853`
- `ESENT!JetSetColumn` at `0x18001c8f2`

## string_xrefs

- `0x18001be87`: `WriteDBEntry6:JetBeginTransaction`
- `0x18001bf0c`: `WriteDBEntry6:JetBeginTransaction`
- `0x18001bebc`: `WriteDBEntry6:JetPrepareUpdate`
- `0x18001bf5a`: `WriteDBEntry6:JetPrepareUpdate`
- `0x18001c933`: `WriteDBEntry6:JetUpdate`

## pseudocode

```c
__int64 __fastcall WriteDBEntry6(unsigned int *a1)
{
  unsigned int DBRecord6; // edi
  int v3; // r14d
  JET_SESID v4; // rdi
  unsigned int v5; // esi
  unsigned int v6; // ecx
  bool v7; // zf
  unsigned int v8; // eax
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // eax
  JET_COLUMNID v15; // r8d
  JET_COLUMNID v16; // r8d
  __int128 v17; // xmm1
  __int64 v18; // rax
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  JET_COLUMNID v24; // r8d
  __int64 v25; // rax
  __int128 v26; // xmm1
  __int64 v27; // rdi
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  _WORD *v34; // r9
  __int64 v35; // rax
  unsigned __int64 v36; // rax
  JET_COLUMNID v37; // r8d
  __int64 v38; // rax
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  _WORD *v46; // r9
  __int64 v47; // rax
  __int64 v48; // rax
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int64 v56; // rax
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  JET_COLUMNID v64; // r8d
  __int64 v65; // rax
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  __int128 v72; // xmm1
  _WORD *v73; // r9
  __int64 v74; // rax
  __int64 v75; // rax
  __int128 v76; // xmm1
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm0
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  __int128 v82; // xmm1
  _WORD *v83; // r9
  __int64 v84; // rax
  __int64 v85; // rax
  __int128 v86; // xmm1
  __int128 v87; // xmm0
  __int128 v88; // xmm1
  __int128 v89; // xmm0
  __int128 v90; // xmm1
  __int128 v91; // xmm0
  __int128 v92; // xmm1
  __int64 v93; // rax
  __int128 v94; // xmm1
  __int128 v95; // xmm0
  __int128 v96; // xmm1
  __int128 v97; // xmm0
  __int128 v98; // xmm1
  __int128 v99; // xmm0
  __int128 v100; // xmm1
  __int64 v101; // rax
  __int128 v102; // xmm1
  __int128 v103; // xmm0
  __int128 v104; // xmm1
  __int128 v105; // xmm0
  __int128 v106; // xmm1
  __int128 v107; // xmm0
  __int128 v108; // xmm1
  __int64 v109; // rax
  __int128 v110; // xmm1
  __int128 v111; // xmm0
  __int128 v112; // xmm1
  __int128 v113; // xmm0
  __int128 v114; // xmm1
  __int128 v115; // xmm0
  __int128 v116; // xmm1
  JET_COLUMNID v117; // r8d
  __int64 v118; // rax
  __int128 v119; // xmm1
  __int128 v120; // xmm0
  __int128 v121; // xmm1
  __int128 v122; // xmm0
  __int128 v123; // xmm1
  __int128 v124; // xmm0
  __int128 v125; // xmm1
  _WORD *v126; // r9
  __int64 v127; // rax
  __int128 v128; // xmm1
  __int128 v129; // xmm0
  __int128 v130; // xmm1
  __int128 v131; // xmm0
  __int128 v132; // xmm1
  __int128 v133; // xmm0
  __int128 v134; // xmm1
  JET_COLUMNID v135; // r8d
  __int64 v136; // rax
  __int128 v137; // xmm1
  __int128 v138; // xmm0
  __int128 v139; // xmm1
  __int128 v140; // xmm0
  __int128 v141; // xmm1
  __int128 v142; // xmm0
  __int128 v143; // xmm1
  JET_COLUMNID v144; // r8d
  unsigned int v145; // eax
  unsigned int v146; // ebx
  char v148; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v149[3]; // [rsp+49h] [rbp-BFh] BYREF
  unsigned int pvData; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int v151; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v152; // [rsp+54h] [rbp-B4h] BYREF
  __int128 v153; // [rsp+58h] [rbp-B0h]
  __int128 v154; // [rsp+68h] [rbp-A0h]
  __int128 v155; // [rsp+78h] [rbp-90h]
  __int128 v156; // [rsp+88h] [rbp-80h]
  __int128 v157; // [rsp+98h] [rbp-70h]
  __int128 v158; // [rsp+A8h] [rbp-60h]
  __int128 v159; // [rsp+B8h] [rbp-50h]
  __int128 v160; // [rsp+C8h] [rbp-40h]
  __int64 v161; // [rsp+D8h] [rbp-30h]
  _BYTE v162[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v163[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v164[16]; // [rsp+108h] [rbp+0h] BYREF

  if ( !a1 )
  {
    DBRecord6 = 87;
    goto LABEL_66;
  }
  v3 = -1;
  if ( *a1 == -1 )
  {
    v4 = DhcpGlobalJetServerSession;
    v5 = 0;
    while ( !(unsigned int)FindDBRecord6(v4) )
    {
      v6 = v5 + 1;
      v7 = v5 == -2;
      v5 = 0;
      if ( !v7 )
        v5 = v6;
    }
    *a1 = v5;
    v8 = JetBeginTransaction(DhcpGlobalJetServerSession);
    DBRecord6 = DhcpMapJetError(v8, "WriteDBEntry6:JetBeginTransaction");
    if ( !DBRecord6 )
    {
      v9 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 0);
      DBRecord6 = DhcpMapJetError(v9, "WriteDBEntry6:JetPrepareUpdate");
      if ( !DBRecord6 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          v11 = 12;
          v12 = v5;
LABEL_20:
          WPP_SF_D(v10[2], v11, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids, v12);
          goto LABEL_21;
        }
        goto LABEL_21;
      }
    }
  }
  else
  {
    v13 = JetBeginTransaction(DhcpGlobalJetServerSession);
    DBRecord6 = DhcpMapJetError(v13, "WriteDBEntry6:JetBeginTransaction");
    if ( !DBRecord6 )
    {
      DBRecord6 = FindDBRecord6(DhcpGlobalJetServerSession);
      if ( !DBRecord6 )
      {
        v14 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 2u);
        DBRecord6 = DhcpMapJetError(v14, "WriteDBEntry6:JetPrepareUpdate");
        if ( !DBRecord6 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
          {
            v12 = *a1;
            v11 = 13;
            goto LABEL_20;
          }
LABEL_21:
          v15 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 8);
          pvData = *a1;
          JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v15, &pvData, 4u, 0, 0);
          v16 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 24);
          v148 = *((_BYTE *)a1 + 4);
          JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v16, &v148, 1u, 0, 0);
          v17 = *((_OWORD *)a1 + 1);
          v18 = *((_QWORD *)a1 + 16);
          v153 = *(_OWORD *)a1;
          v19 = *((_OWORD *)a1 + 2);
          v154 = v17;
          v20 = *((_OWORD *)a1 + 3);
          v155 = v19;
          v21 = *((_OWORD *)a1 + 4);
          v156 = v20;
          v22 = *((_OWORD *)a1 + 5);
          v157 = v21;
          v23 = *((_OWORD *)a1 + 6);
          v158 = v22;
          v159 = v23;
          v160 = *((_OWORD *)a1 + 7);
          v161 = v18;
          if ( (v154 & 4) != 0 )
          {
            v24 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 40);
            v149[0] = *((_BYTE *)a1 + 6);
            JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v24, v149, 1u, 0, 0);
          }
          v25 = *((_QWORD *)a1 + 16);
          v26 = *((_OWORD *)a1 + 1);
          v27 = -1;
          v153 = *(_OWORD *)a1;
          v28 = *((_OWORD *)a1 + 2);
          v154 = v26;
          v29 = *((_OWORD *)a1 + 3);
          v155 = v28;
          v30 = *((_OWORD *)a1 + 4);
          v156 = v29;
          v31 = *((_OWORD *)a1 + 5);
          v157 = v30;
          v32 = *((_OWORD *)a1 + 6);
          v158 = v31;
          v33 = *((_OWORD *)a1 + 7);
          v159 = v32;
          v160 = v33;
          v161 = v25;
          if ( (v154 & 8) != 0 )
          {
            v34 = (_WORD *)*((_QWORD *)a1 + 1);
            v35 = -1;
            do
              ++v35;
            while ( v34[v35] );
            v36 = v35 + 1;
            if ( v36 <= 0xFFFFFFFF )
              v3 = v36;
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 56),
              v34,
              2 * v3,
              0,
              0);
          }
          v37 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 72);
          pvData = a1[4];
          JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v37, &pvData, 4u, 0, 0);
          v38 = *((_QWORD *)a1 + 16);
          v39 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v40 = *((_OWORD *)a1 + 2);
          v154 = v39;
          v41 = *((_OWORD *)a1 + 3);
          v155 = v40;
          v42 = *((_OWORD *)a1 + 4);
          v156 = v41;
          v43 = *((_OWORD *)a1 + 5);
          v157 = v42;
          v44 = *((_OWORD *)a1 + 6);
          v158 = v43;
          v45 = *((_OWORD *)a1 + 7);
          v159 = v44;
          v160 = v45;
          v161 = v38;
          if ( (v154 & 0x20) != 0 )
          {
            v46 = (_WORD *)*((_QWORD *)a1 + 3);
            v47 = -1;
            do
              ++v47;
            while ( v46[v47] );
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 88),
              v46,
              2 * v47 + 2,
              0,
              0);
          }
          v48 = *((_QWORD *)a1 + 16);
          v49 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v50 = *((_OWORD *)a1 + 2);
          v154 = v49;
          v51 = *((_OWORD *)a1 + 3);
          v155 = v50;
          v52 = *((_OWORD *)a1 + 4);
          v156 = v51;
          v53 = *((_OWORD *)a1 + 5);
          v157 = v52;
          v54 = *((_OWORD *)a1 + 6);
          v158 = v53;
          v55 = *((_OWORD *)a1 + 7);
          v159 = v54;
          v160 = v55;
          v161 = v48;
          if ( (v154 & 0x40) != 0 )
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 104),
              *((const void **)a1 + 4),
              a1[10],
              0,
              0);
          v56 = *((_QWORD *)a1 + 16);
          v57 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v58 = *((_OWORD *)a1 + 2);
          v154 = v57;
          v59 = *((_OWORD *)a1 + 3);
          v155 = v58;
          v60 = *((_OWORD *)a1 + 4);
          v156 = v59;
          v61 = *((_OWORD *)a1 + 5);
          v157 = v60;
          v62 = *((_OWORD *)a1 + 6);
          v158 = v61;
          v63 = *((_OWORD *)a1 + 7);
          v159 = v62;
          v160 = v63;
          v161 = v56;
          if ( (v154 & 0x80) != 0 )
          {
            v64 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 120);
            v151 = a1[11];
            JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v64, &v151, 4u, 0, 0);
          }
          v65 = *((_QWORD *)a1 + 16);
          v66 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v67 = *((_OWORD *)a1 + 2);
          v154 = v66;
          v68 = *((_OWORD *)a1 + 3);
          v155 = v67;
          v69 = *((_OWORD *)a1 + 4);
          v156 = v68;
          v70 = *((_OWORD *)a1 + 5);
          v157 = v69;
          v71 = *((_OWORD *)a1 + 6);
          v158 = v70;
          v72 = *((_OWORD *)a1 + 7);
          v159 = v71;
          v160 = v72;
          v161 = v65;
          if ( (v154 & 0x100) != 0 )
          {
            v73 = (_WORD *)*((_QWORD *)a1 + 6);
            v74 = -1;
            do
              ++v74;
            while ( v73[v74] );
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 136),
              v73,
              2 * v74 + 2,
              0,
              0);
          }
          v75 = *((_QWORD *)a1 + 16);
          v76 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v77 = *((_OWORD *)a1 + 2);
          v154 = v76;
          v78 = *((_OWORD *)a1 + 3);
          v155 = v77;
          v79 = *((_OWORD *)a1 + 4);
          v156 = v78;
          v80 = *((_OWORD *)a1 + 5);
          v157 = v79;
          v81 = *((_OWORD *)a1 + 6);
          v158 = v80;
          v82 = *((_OWORD *)a1 + 7);
          v159 = v81;
          v160 = v82;
          v161 = v75;
          if ( (v154 & 0x200) != 0 )
          {
            v83 = (_WORD *)*((_QWORD *)a1 + 7);
            v84 = -1;
            do
              ++v84;
            while ( v83[v84] );
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 152),
              v83,
              2 * v84 + 2,
              0,
              0);
          }
          v85 = *((_QWORD *)a1 + 16);
          v86 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v87 = *((_OWORD *)a1 + 2);
          v154 = v86;
          v88 = *((_OWORD *)a1 + 3);
          v155 = v87;
          v89 = *((_OWORD *)a1 + 4);
          v156 = v88;
          v90 = *((_OWORD *)a1 + 5);
          v157 = v89;
          v91 = *((_OWORD *)a1 + 6);
          v158 = v90;
          v92 = *((_OWORD *)a1 + 7);
          v159 = v91;
          v160 = v92;
          v161 = v85;
          if ( (v154 & 0x400) != 0 )
          {
            MemAddr6ConvertIpv6AddrToByte(a1 + 16, v162);
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 168),
              v162,
              0x10u,
              0,
              0);
          }
          v93 = *((_QWORD *)a1 + 16);
          v94 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v95 = *((_OWORD *)a1 + 2);
          v154 = v94;
          v96 = *((_OWORD *)a1 + 3);
          v155 = v95;
          v97 = *((_OWORD *)a1 + 4);
          v156 = v96;
          v98 = *((_OWORD *)a1 + 5);
          v157 = v97;
          v99 = *((_OWORD *)a1 + 6);
          v158 = v98;
          v100 = *((_OWORD *)a1 + 7);
          v159 = v99;
          v160 = v100;
          v161 = v93;
          if ( (v154 & 0x4000) != 0 )
          {
            MemAddr6ConvertIpv6AddrToByte(a1 + 28, v163);
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 232),
              v163,
              0x10u,
              0,
              0);
          }
          v101 = *((_QWORD *)a1 + 16);
          v102 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v103 = *((_OWORD *)a1 + 2);
          v154 = v102;
          v104 = *((_OWORD *)a1 + 3);
          v155 = v103;
          v105 = *((_OWORD *)a1 + 4);
          v156 = v104;
          v106 = *((_OWORD *)a1 + 5);
          v157 = v105;
          v107 = *((_OWORD *)a1 + 6);
          v158 = v106;
          v108 = *((_OWORD *)a1 + 7);
          v159 = v107;
          v160 = v108;
          v161 = v101;
          if ( (v154 & 0x2000) != 0 )
          {
            MemAddr6ConvertIpv6AddrToByte(a1 + 24, v164);
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 216),
              v164,
              0x10u,
              0,
              0);
          }
          v109 = *((_QWORD *)a1 + 16);
          v110 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v111 = *((_OWORD *)a1 + 2);
          v154 = v110;
          v112 = *((_OWORD *)a1 + 3);
          v155 = v111;
          v113 = *((_OWORD *)a1 + 4);
          v156 = v112;
          v114 = *((_OWORD *)a1 + 5);
          v157 = v113;
          v115 = *((_OWORD *)a1 + 6);
          v158 = v114;
          v116 = *((_OWORD *)a1 + 7);
          v159 = v115;
          v160 = v116;
          v161 = v109;
          if ( (v154 & 0x800) != 0 )
          {
            v117 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 184);
            v149[0] = *((_BYTE *)a1 + 80);
            JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v117, v149, 1u, 0, 0);
          }
          v118 = *((_QWORD *)a1 + 16);
          v119 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v120 = *((_OWORD *)a1 + 2);
          v154 = v119;
          v121 = *((_OWORD *)a1 + 3);
          v155 = v120;
          v122 = *((_OWORD *)a1 + 4);
          v156 = v121;
          v123 = *((_OWORD *)a1 + 5);
          v157 = v122;
          v124 = *((_OWORD *)a1 + 6);
          v158 = v123;
          v125 = *((_OWORD *)a1 + 7);
          v159 = v124;
          v160 = v125;
          v161 = v118;
          if ( (v154 & 0x1000) != 0 )
          {
            v126 = (_WORD *)*((_QWORD *)a1 + 11);
            do
              ++v27;
            while ( v126[v27] );
            JetSetColumn(
              DhcpGlobalJetServerSession,
              DhcpGlobalConfigTableV6Handle,
              *(_DWORD *)(DhcpGlobalConfigTableV6 + 200),
              v126,
              2 * v27 + 2,
              0,
              0);
          }
          v127 = *((_QWORD *)a1 + 16);
          v128 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v129 = *((_OWORD *)a1 + 2);
          v154 = v128;
          v130 = *((_OWORD *)a1 + 3);
          v155 = v129;
          v131 = *((_OWORD *)a1 + 4);
          v156 = v130;
          v132 = *((_OWORD *)a1 + 5);
          v157 = v131;
          v133 = *((_OWORD *)a1 + 6);
          v158 = v132;
          v134 = *((_OWORD *)a1 + 7);
          v159 = v133;
          v160 = v134;
          v161 = v127;
          if ( (v154 & 0x8000) != 0 )
          {
            v135 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 248);
            v148 = *((_BYTE *)a1 + 128);
            JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v135, &v148, 1u, 0, 0);
          }
          v136 = *((_QWORD *)a1 + 16);
          v137 = *((_OWORD *)a1 + 1);
          v153 = *(_OWORD *)a1;
          v138 = *((_OWORD *)a1 + 2);
          v154 = v137;
          v139 = *((_OWORD *)a1 + 3);
          v155 = v138;
          v140 = *((_OWORD *)a1 + 4);
          v156 = v139;
          v141 = *((_OWORD *)a1 + 5);
          v157 = v140;
          v142 = *((_OWORD *)a1 + 6);
          v158 = v141;
          v143 = *((_OWORD *)a1 + 7);
          v159 = v142;
          v160 = v143;
          v161 = v136;
          if ( (v154 & 0x10000) != 0 )
          {
            v144 = *(_DWORD *)(DhcpGlobalConfigTableV6 + 264);
            v152 = a1[33];
            JetSetColumn(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, v144, &v152, 4u, 0, 0);
          }
          v145 = JetUpdate(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 0, 0, 0);
          v146 = v145;
          if ( v145 == -1605 )
          {
            DBRecord6 = 20013;
          }
          else
          {
            DBRecord6 = DhcpMapJetError(v145, "WriteDBEntry6:JetUpdate");
            if ( !v146 )
            {
LABEL_65:
              DhcpJetCommitTransactionV6(DhcpGlobalJetServerSession);
              goto LABEL_66;
            }
          }
          JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalConfigTableV6Handle, 3u);
          goto LABEL_65;
        }
      }
    }
  }
LABEL_66:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids, DBRecord6);
  return DBRecord6;
}

```

## disassembly

```asm
0x18001bde8  mov     rax, rsp
0x18001bdeb  mov     [rax+10h], rbx
0x18001bdef  mov     [rax+18h], rsi
0x18001bdf3  mov     [rax+20h], rdi
0x18001bdf7  push    rbp
0x18001bdf8  push    r12
0x18001bdfa  push    r13
0x18001bdfc  push    r14
0x18001bdfe  push    r15
0x18001be00  lea     rbp, [rax-48h]
0x18001be04  sub     rsp, 120h
0x18001be0b  mov     rax, cs:__security_cookie
0x18001be12  xor     rax, rsp
0x18001be15  mov     [rbp+40h+var_30], rax
0x18001be19  xor     r15d, r15d
0x18001be1c  lea     r13, WPP_GLOBAL_Control
0x18001be23  mov     rbx, rcx
0x18001be26  mov     r12d, 8000h
0x18001be2c  test    rcx, rcx
0x18001be2f  jnz     short loc_18001BE39
0x18001be31  lea     edi, [rcx+57h]
0x18001be34  jmp     loc_18001C97A
0x18001be39  mov     r14d, 0FFFFFFFFh
0x18001be3f  cmp     [rcx], r14d
0x18001be42  jnz     loc_18001BEF7
0x18001be48  mov     rdi, cs:DhcpGlobalJetServerSession
0x18001be4f  mov     esi, r15d
0x18001be52  mov     edx, esi
0x18001be54  mov     rcx, rdi; sesid
0x18001be57  call    FindDBRecord6
0x18001be5c  test    eax, eax
0x18001be5e  jnz     short loc_18001BE70
0x18001be60  mov     eax, esi
0x18001be62  lea     ecx, [rsi+1]
0x18001be65  cmp     eax, 0FFFFFFFEh
0x18001be68  mov     esi, r15d
0x18001be6b  cmovnz  esi, ecx
0x18001be6e  jmp     short loc_18001BE52
0x18001be70  mov     [rbx], esi
0x18001be72  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001be79  call    cs:__imp_JetBeginTransaction
0x18001be80  nop     dword ptr [rax+rax+00h]
0x18001be85  mov     ecx, eax
0x18001be87  lea     rdx, aWritedbentry6J_0; "WriteDBEntry6:JetBeginTransaction"
0x18001be8e  call    DhcpMapJetError
0x18001be93  mov     edi, eax
0x18001be95  test    eax, eax
0x18001be97  jnz     loc_18001C97A
0x18001be9d  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001bea4  xor     r8d, r8d; prep
0x18001bea7  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001beae  call    cs:__imp_JetPrepareUpdate
0x18001beb5  nop     dword ptr [rax+rax+00h]
0x18001beba  mov     ecx, eax
0x18001bebc  lea     rdx, aWritedbentry6J; "WriteDBEntry6:JetPrepareUpdate"
0x18001bec3  call    DhcpMapJetError
0x18001bec8  mov     edi, eax
0x18001beca  test    eax, eax
0x18001becc  jnz     loc_18001C97A
0x18001bed2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bed9  cmp     rcx, r13
0x18001bedc  jz      loc_18001BF98
0x18001bee2  test    [rcx+1Ch], r12d
0x18001bee6  jz      loc_18001BF98
0x18001beec  lea     edx, [rax+0Ch]
0x18001beef  mov     r9d, esi
0x18001bef2  jmp     loc_18001BF88
0x18001bef7  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001befe  call    cs:__imp_JetBeginTransaction
0x18001bf05  nop     dword ptr [rax+rax+00h]
0x18001bf0a  mov     ecx, eax
0x18001bf0c  lea     rdx, aWritedbentry6J_0; "WriteDBEntry6:JetBeginTransaction"
0x18001bf13  call    DhcpMapJetError
0x18001bf18  mov     edi, eax
0x18001bf1a  test    eax, eax
0x18001bf1c  jnz     loc_18001C97A
0x18001bf22  mov     edx, [rbx]
0x18001bf24  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001bf2b  call    FindDBRecord6
0x18001bf30  mov     edi, eax
0x18001bf32  test    eax, eax
0x18001bf34  jnz     loc_18001C97A
0x18001bf3a  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001bf41  lea     r8d, [rax+2]; prep
0x18001bf45  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001bf4c  call    cs:__imp_JetPrepareUpdate
0x18001bf53  nop     dword ptr [rax+rax+00h]
0x18001bf58  mov     ecx, eax
0x18001bf5a  lea     rdx, aWritedbentry6J; "WriteDBEntry6:JetPrepareUpdate"
0x18001bf61  call    DhcpMapJetError
0x18001bf66  mov     edi, eax
0x18001bf68  test    eax, eax
0x18001bf6a  jnz     loc_18001C97A
0x18001bf70  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf77  cmp     rcx, r13
0x18001bf7a  jz      short loc_18001BF98
0x18001bf7c  test    [rcx+1Ch], r12d
0x18001bf80  jz      short loc_18001BF98
0x18001bf82  mov     r9d, [rbx]
0x18001bf85  lea     edx, [rax+0Dh]
0x18001bf88  mov     rcx, [rcx+10h]
0x18001bf8c  lea     r8, WPP_eb597571a7903c0e253e9367b42d8bcf_Traceguids
0x18001bf93  call    WPP_SF_D
0x18001bf98  mov     r8, cs:DhcpGlobalConfigTableV6
0x18001bf9f  lea     r9, [rsp+140h+pvData]; pvData
0x18001bfa4  mov     eax, [rbx]
0x18001bfa6  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001bfad  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001bfb4  mov     r8d, [r8+8]; columnid
0x18001bfb8  mov     [rsp+140h+psetinfo], r15; psetinfo
0x18001bfbd  mov     [rsp+140h+grbit], r15d; grbit
0x18001bfc2  mov     [rsp+140h+pvData], eax
0x18001bfc6  mov     [rsp+140h+cbData], 4; cbData
0x18001bfce  call    cs:__imp_JetSetColumn
0x18001bfd5  nop     dword ptr [rax+rax+00h]
0x18001bfda  mov     r8, cs:DhcpGlobalConfigTableV6
0x18001bfe1  lea     r9, [rsp+140h+var_100]; pvData
0x18001bfe6  mov     al, [rbx+4]
0x18001bfe9  mov     r13d, 1
0x18001bfef  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001bff6  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001bffd  mov     r8d, [r8+18h]; columnid
0x18001c001  mov     [rsp+140h+psetinfo], r15; psetinfo
0x18001c006  mov     [rsp+140h+grbit], r15d; grbit
0x18001c00b  mov     byte ptr [rsp+140h+var_100], al
0x18001c00f  mov     [rsp+140h+cbData], r13d; cbData
0x18001c014  call    cs:__imp_JetSetColumn
0x18001c01b  nop     dword ptr [rax+rax+00h]
0x18001c020  movups  xmm0, xmmword ptr [rbx]
0x18001c023  lea     rcx, [rsp+140h+var_F0]
0x18001c028  movups  xmm1, xmmword ptr [rbx+10h]
0x18001c02c  lea     esi, [r13+7Fh]
0x18001c030  mov     rax, [rbx+rsi]
0x18001c034  movups  xmmword ptr [rcx], xmm0
0x18001c037  movups  xmm0, xmmword ptr [rbx+20h]
0x18001c03b  movups  xmmword ptr [rcx+10h], xmm1
0x18001c03f  movups  xmm1, xmmword ptr [rbx+30h]
0x18001c043  movups  xmmword ptr [rcx+20h], xmm0
0x18001c047  movups  xmm0, xmmword ptr [rbx+40h]
0x18001c04b  movups  xmmword ptr [rcx+30h], xmm1
0x18001c04f  movups  xmm1, xmmword ptr [rbx+50h]
0x18001c053  movups  xmmword ptr [rcx+40h], xmm0
0x18001c057  movups  xmm0, xmmword ptr [rbx+60h]
0x18001c05b  movups  xmmword ptr [rcx+50h], xmm1
0x18001c05f  movups  xmmword ptr [rcx+60h], xmm0
0x18001c063  movups  xmm0, xmmword ptr [rbx+70h]
0x18001c067  movups  xmmword ptr [rcx+rsi-10h], xmm0
0x18001c06c  mov     [rcx+rsi], rax
0x18001c070  test    byte ptr [rsp+140h+var_E0], 4
0x18001c075  jz      short loc_18001C0B7
0x18001c077  mov     r8, cs:DhcpGlobalConfigTableV6
0x18001c07e  lea     r9, [rsp+140h+var_100+1]; pvData
0x18001c083  mov     al, [rbx+6]
0x18001c086  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001c08d  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001c094  mov     r8d, [r8+28h]; columnid
0x18001c098  mov     [rsp+140h+psetinfo], r15; psetinfo
0x18001c09d  mov     [rsp+140h+grbit], r15d; grbit
0x18001c0a2  mov     byte ptr [rsp+140h+var_100+1], al
0x18001c0a6  mov     [rsp+140h+cbData], r13d; cbData
0x18001c0ab  call    cs:__imp_JetSetColumn
0x18001c0b2  nop     dword ptr [rax+rax+00h]
0x18001c0b7  movups  xmm0, xmmword ptr [rbx]
0x18001c0ba  mov     rax, [rbx+rsi]
0x18001c0be  lea     rcx, [rsp+140h+var_F0]
0x18001c0c3  movups  xmm1, xmmword ptr [rbx+10h]
0x18001c0c7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c0cb  movups  xmmword ptr [rcx], xmm0
0x18001c0ce  movups  xmm0, xmmword ptr [rbx+20h]
0x18001c0d2  movups  xmmword ptr [rcx+10h], xmm1
0x18001c0d6  movups  xmm1, xmmword ptr [rbx+30h]
0x18001c0da  movups  xmmword ptr [rcx+20h], xmm0
0x18001c0de  movups  xmm0, xmmword ptr [rbx+40h]
0x18001c0e2  movups  xmmword ptr [rcx+30h], xmm1
0x18001c0e6  movups  xmm1, xmmword ptr [rbx+50h]
0x18001c0ea  movups  xmmword ptr [rcx+40h], xmm0
0x18001c0ee  movups  xmm0, xmmword ptr [rbx+60h]
0x18001c0f2  movups  xmmword ptr [rcx+50h], xmm1
0x18001c0f6  movups  xmm1, xmmword ptr [rbx+70h]
0x18001c0fa  movups  xmmword ptr [rcx+60h], xmm0
0x18001c0fe  movups  xmmword ptr [rcx+rsi-10h], xmm1
0x18001c103  mov     [rcx+rsi], rax
0x18001c107  test    byte ptr [rsp+140h+var_E0], 8
0x18001c10c  jz      short loc_18001C160
0x18001c10e  mov     r9, [rbx+8]; pvData
0x18001c112  mov     rax, rdi
0x18001c115  inc     rax
0x18001c118  cmp     [r9+rax*2], r15w
0x18001c11d  jnz     short loc_18001C115
0x18001c11f  mov     r8, cs:DhcpGlobalConfigTableV6
0x18001c126  add     rax, r13
0x18001c129  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001c130  cmp     rax, r14
0x18001c133  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001c13a  cmovbe  r14d, eax
0x18001c13e  mov     [rsp+140h+psetinfo], r15; psetinfo
0x18001c143  mov     r8d, [r8+38h]; columnid
0x18001c147  mov     [rsp+140h+grbit], r15d; grbit
0x18001c14c  lea     eax, [r14+r14]
0x18001c150  mov     [rsp+140h+cbData], eax; cbData
0x18001c154  call    cs:__imp_JetSetColumn
0x18001c15b  nop     dword ptr [rax+rax+00h]
0x18001c160  mov     r8, cs:DhcpGlobalConfigTableV6
0x18001c167  lea     r9, [rsp+140h+pvData]; pvData
0x18001c16c  mov     eax, [rbx+10h]
0x18001c16f  mov     r14d, 4
0x18001c175  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001c17c  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001c183  mov     r8d, [r8+48h]; columnid
0x18001c187  mov     [rsp+140h+psetinfo], r15; psetinfo
0x18001c18c  mov     [rsp+140h+grbit], r15d; grbit
0x18001c191  mov     [rsp+140h+pvData], eax
0x18001c195  mov     [rsp+140h+cbData], r14d; cbData
0x18001c19a  call    cs:__imp_JetSetColumn
0x18001c1a1  nop     dword ptr [rax+rax+00h]
0x18001c1a6  movups  xmm0, xmmword ptr [rbx]
0x18001c1a9  mov     rax, [rbx+rsi]
0x18001c1ad  lea     rcx, [rsp+140h+var_F0]
0x18001c1b2  movups  xmm1, xmmword ptr [rbx+10h]
0x18001c1b6  movups  xmmword ptr [rcx], xmm0
0x18001c1b9  movups  xmm0, xmmword ptr [rbx+20h]
0x18001c1bd  movups  xmmword ptr [rcx+10h], xmm1
0x18001c1c1  movups  xmm1, xmmword ptr [rbx+30h]
0x18001c1c5  movups  xmmword ptr [rcx+20h], xmm0
0x18001c1c9  movups  xmm0, xmmword ptr [rbx+40h]
0x18001c1cd  movups  xmmword ptr [rcx+30h], xmm1
0x18001c1d1  movups  xmm1, xmmword ptr [rbx+50h]
0x18001c1d5  movups  xmmword ptr [rcx+40h], xmm0
0x18001c1d9  movups  xmm0, xmmword ptr [rbx+60h]
0x18001c1dd  movups  xmmword ptr [rcx+50h], xmm1
0x18001c1e1  movups  xmm1, xmmword ptr [rbx+70h]
0x18001c1e5  movups  xmmword ptr [rcx+60h], xmm0
0x18001c1e9  movups  xmmword ptr [rcx+rsi-10h], xmm1
0x18001c1ee  mov     [rcx+rsi], rax
0x18001c1f2  test    byte ptr [rsp+140h+var_E0], 20h
0x18001c1f7  jz      short loc_18001C244
0x18001c1f9  mov     r9, [rbx+18h]; pvData
0x18001c1fd  mov     rax, rdi
0x18001c200  inc     rax
0x18001c203  cmp     [r9+rax*2], r15w
0x18001c208  jnz     short loc_18001C200
0x18001c20a  mov     r8, cs:DhcpGlobalConfigTableV6
0x18001c211  lea     eax, ds:2[rax*2]
0x18001c218  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001c21f  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001c226  mov     [rsp+140h+psetinfo], r15; psetinfo
0x18001c22b  mov     r8d, [r8+58h]; columnid
0x18001c22f  mov     [rsp+140h+grbit], r15d; grbit
0x18001c234  mov     [rsp+140h+cbData], eax; cbData
0x18001c238  call    cs:__imp_JetSetColumn
0x18001c23f  nop     dword ptr [rax+rax+00h]
0x18001c244  movups  xmm0, xmmword ptr [rbx]
0x18001c247  mov     rax, [rbx+rsi]
0x18001c24b  lea     rcx, [rsp+140h+var_F0]
0x18001c250  movups  xmm1, xmmword ptr [rbx+10h]
0x18001c254  movups  xmmword ptr [rcx], xmm0
0x18001c257  movups  xmm0, xmmword ptr [rbx+20h]
0x18001c25b  movups  xmmword ptr [rcx+10h], xmm1
0x18001c25f  movups  xmm1, xmmword ptr [rbx+30h]
0x18001c263  movups  xmmword ptr [rcx+20h], xmm0
0x18001c267  movups  xmm0, xmmword ptr [rbx+40h]
0x18001c26b  movups  xmmword ptr [rcx+30h], xmm1
0x18001c26f  movups  xmm1, xmmword ptr [rbx+50h]
0x18001c273  movups  xmmword ptr [rcx+40h], xmm0
0x18001c277  movups  xmm0, xmmword ptr [rbx+60h]
0x18001c27b  movups  xmmword ptr [rcx+50h], xmm1
0x18001c27f  movups  xmm1, xmmword ptr [rbx+70h]
0x18001c283  movups  xmmword ptr [rcx+60h], xmm0
0x18001c287  movups  xmmword ptr [rcx+rsi-10h], xmm1
0x18001c28c  mov     [rcx+rsi], rax
0x18001c290  test    byte ptr [rsp+140h+var_E0], 40h
0x18001c295  jz      short loc_18001C2D1
0x18001c297  mov     r8, cs:DhcpGlobalConfigTableV6
0x18001c29e  mov     eax, [rbx+28h]
0x18001c2a1  mov     r9, [rbx+20h]; pvData
0x18001c2a5  mov     rdx, cs:DhcpGlobalConfigTableV6Handle; tableid
0x18001c2ac  mov     r8d, [r8+68h]; columnid
0x18001c2b0  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18001c2b7  mov     [rsp+140h+psetinfo], r15; psetinfo
0x18001c2bc  mov     [rsp+140h+grbit], r15d; grbit
0x18001c2c1  mov     [rsp+140h+cbData], eax; cbData
0x18001c2c5  call    cs:__imp_JetSetColumn
0x18001c2cc  nop     dword ptr [rax+rax+00h]
0x18001c2d1  movups  xmm0, xmmword ptr [rbx]
0x18001c2d4  mov     rax, [rbx+rsi]
0x18001c2d8  lea     rcx, [rsp+140h+var_F0]
0x18001c2dd  movups  xmm1, xmmword ptr [rbx+10h]
0x18001c2e1  movups  xmmword ptr [rcx], xmm0
0x18001c2e4  movups  xmm0, xmmword ptr [rbx+20h]
0x18001c2e8  movups  xmmword ptr [rcx+10h], xmm1
0x18001c2ec  movups  xmm1, xmmword ptr [rbx+30h]
0x18001c2f0  movups  xmmword ptr [rcx+20h], xmm0
0x18001c2f4  movups  xmm0, xmmword ptr [rbx+40h]
0x18001c2f8  movups  xmmword ptr [rcx+30h], xmm1
0x18001c2fc  movups  xmm1, xmmword ptr [rbx+50h]
0x18001c300  movups  xmmword ptr [rcx+40h], xmm0
0x18001c304  movups  xmm0, xmmword ptr [rbx+60h]
0x18001c308  movups  xmmword ptr [rcx+50h], xmm1
0x18001c30c  movups  xmm1, xmmword ptr [rbx+70h]
0x18001c310  movups  xmmword ptr [rcx+60h], xmm0
  ... truncated ...
```
