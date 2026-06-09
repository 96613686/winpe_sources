# CRdpUdpTransport::OnICEUpdateConnectionType(uint,RdpNanoIceConnectionInfo *)

- ea: `0x180416940`
- end: `0x18041816c`
- name: `?OnICEUpdateConnectionType@CRdpUdpTransport@@UEAAJIPEAURdpNanoIceConnectionInfo@@@Z`
- size: `6188`
- prototype: `__int64 __fastcall(CRdpUdpTransport *__hidden this, unsigned int, struct RdpNanoIceConnectionInfo *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callees

- `0x1800011f4`
- `0x180009060`
- `0x180009320`
- `0x180009bb0`
- `0x180082910`
- `0x18012962c`
- `0x18040faa0`
- `0x18040fea0`
- `0x180412750`
- `0x180414080`
- `0x180416940`
- `0x180418d50`
- `0x18041a510`
- `0x18041ab50`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180417023`
- `ADVAPI32!EventWriteTransfer` at `0x1804172c9`
- `ADVAPI32!EventWriteTransfer` at `0x180417680`
- `ADVAPI32!EventWriteTransfer` at `0x18041791e`
- `ADVAPI32!EventWriteTransfer` at `0x180417d14`
- `ADVAPI32!EventWriteTransfer` at `0x180417df8`
- `ADVAPI32!EventWriteTransfer` at `0x180417f2f`
- `ADVAPI32!EventWriteTransfer` at `0x18041808f`
- `ADVAPI32!EventWriteTransfer` at `0x180417023`
- `ADVAPI32!EventWriteTransfer` at `0x1804172c9`
- `ADVAPI32!EventWriteTransfer` at `0x180417680`
- `ADVAPI32!EventWriteTransfer` at `0x18041791e`
- `ADVAPI32!EventWriteTransfer` at `0x180417d14`
- `ADVAPI32!EventWriteTransfer` at `0x180417df8`
- `ADVAPI32!EventWriteTransfer` at `0x180417f2f`
- `ADVAPI32!EventWriteTransfer` at `0x18041808f`
- `ADVAPI32!EventActivityIdControl` at `0x180416a11`
- `ADVAPI32!EventActivityIdControl` at `0x1804171fe`
- `ADVAPI32!EventActivityIdControl` at `0x1804172d6`
- `ADVAPI32!EventActivityIdControl` at `0x180417f5e`
- `ADVAPI32!EventActivityIdControl` at `0x180416a11`
- `ADVAPI32!EventActivityIdControl` at `0x1804171fe`
- `ADVAPI32!EventActivityIdControl` at `0x1804172d6`
- `ADVAPI32!EventActivityIdControl` at `0x180417f5e`

## string_xrefs

- `0x180417b8c`: `ICE: Smiles Switch Active Link`
- `0x180417c70`: `ICE: Updated active link type`
- `0x180417fe2`: `ICE: Updated active link type`
- `0x180417100`: `ICE: Smiles Add Link`
- `0x180417872`: `ICE: Smiles Remove Link`
- `0x180417191`: `OnICEUpdateConnectionType`
- `0x1804171b8`: `Set new links failed`
- `0x180417d59`: `ICE: Set first Smiles active Link`
- `0x180417e74`: `ICE: swap smilesLinkInfo`

## pseudocode

```c
__int64 __fastcall CRdpUdpTransport::OnICEUpdateConnectionType(
        CRdpUdpTransport *this,
        unsigned int a2,
        struct RdpNanoIceConnectionInfo *a3)
{
  const GUID *v3; // r9
  struct RdpNanoIceConnectionInfo *v4; // rsi
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  unsigned int v11; // eax
  __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // kr00_8
  int v15; // edi
  bool v16; // cf
  size_t v17; // rax
  _QWORD *v18; // rax
  SessionStartupCtl::SmilesLinkInfo *v19; // rdi
  struct SessionStartupCtl *v20; // r13
  const char *v21; // r12
  const char *v22; // rdx
  unsigned int v23; // r11d
  int v24; // r9d
  __int64 v25; // rax
  BOOL v26; // r12d
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // r10d
  struct RdpNanoIceCandidate *v31; // r14
  __int64 v32; // rax
  struct RdpNanoIceCandidate *v33; // rdi
  unsigned int v34; // edx
  unsigned int v35; // r8d
  __int64 v36; // r15
  unsigned int v37; // ebx
  unsigned int v38; // r14d
  unsigned __int64 v39; // rdi
  unsigned int v40; // esi
  unsigned int v41; // eax
  int v42; // ecx
  unsigned int v43; // ebx
  int v44; // r8d
  int v45; // r9d
  const char *v46; // r8
  __int64 v47; // rdx
  const char *v48; // r9
  const char *v49; // r10
  const char *v50; // r11
  const char *v51; // rbx
  const char *v52; // rsi
  const char *v53; // rdi
  __int64 v54; // rdx
  const char *v55; // rcx
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  __int64 v62; // rax
  int v63; // eax
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rax
  int v67; // eax
  __int64 v68; // rax
  int v69; // eax
  __int64 v70; // rax
  int v71; // eax
  __int64 v72; // rdx
  int v73; // ecx
  int v74; // ecx
  int v75; // ecx
  int v76; // ecx
  const char *v77; // rax
  __int64 v78; // rdx
  int v79; // ecx
  unsigned int v80; // r14d
  unsigned int v81; // r9d
  const char **v82; // rbx
  bool v83; // zf
  unsigned int v84; // eax
  const char *v85; // rcx
  const char *v86; // rdx
  const char *v87; // r8
  const char *v88; // rdi
  const char *v89; // r9
  const char *v90; // r10
  const char *v91; // r11
  const char *v92; // rsi
  __int64 v93; // rax
  int v94; // eax
  __int64 v95; // rax
  int v96; // eax
  __int64 v97; // rax
  int v98; // eax
  __int64 v99; // rax
  int v100; // eax
  __int64 v101; // rax
  int v102; // eax
  __int64 v103; // rax
  int v104; // eax
  __int64 v105; // rax
  int v106; // eax
  __int64 v107; // rax
  int v108; // eax
  const char *v109; // rcx
  const char *v110; // rdx
  const char *v111; // r8
  const char *v112; // r9
  const char *v113; // r10
  const char *v114; // r11
  const char *v115; // rdi
  const char *v116; // rbx
  __int64 v117; // rax
  int v118; // eax
  __int64 v119; // rax
  int v120; // eax
  __int64 v121; // rax
  int v122; // eax
  __int64 v123; // rax
  int v124; // eax
  __int64 v125; // rax
  unsigned int v126; // eax
  __int64 v127; // rax
  unsigned int v128; // eax
  __int64 v129; // rax
  unsigned int v130; // eax
  __int64 v131; // rax
  unsigned int v132; // eax
  unsigned int v133; // eax
  unsigned int v134; // esi
  const char *v135; // rbx
  const char *v136; // rdi
  const char *v137; // rsi
  const char *v138; // r14
  const char *v139; // r15
  unsigned int *v140; // rcx
  struct RdpNanoIceCandidate *v141; // r10
  const char *v142; // r8
  struct RdpNanoIceCandidate *v143; // r9
  __int64 v144; // rax
  const char *v145; // r13
  unsigned int *v146; // rcx
  const char *v147; // r11
  __int64 v148; // rax
  struct SessionStartupCtl *v149; // rax
  SessionStartupCtl::SmilesLinkInfo *v150; // rcx
  unsigned int v151; // ebx
  _QWORD *v152; // rcx
  unsigned int v153; // eax
  unsigned int v154; // ecx
  __int64 v155; // rcx
  __int64 v156; // rax
  __int64 v157; // rcx
  __int64 v158; // r8
  __int64 v159; // rdx
  unsigned int v160; // edx
  unsigned int v161; // ecx
  unsigned int v162; // [rsp+B0h] [rbp-80h] BYREF
  const char *v163; // [rsp+B8h] [rbp-78h] BYREF
  unsigned int v164; // [rsp+C0h] [rbp-70h]
  unsigned int v165; // [rsp+C4h] [rbp-6Ch]
  struct SessionStartupCtl *v166; // [rsp+C8h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+D0h] [rbp-60h] BYREF
  struct RdpNanoIceCandidate *v168; // [rsp+E0h] [rbp-50h] BYREF
  struct RdpNanoIceCandidate *v169; // [rsp+E8h] [rbp-48h] BYREF
  const char *v170; // [rsp+F0h] [rbp-40h] BYREF
  struct RdpNanoIceCandidate *v171; // [rsp+F8h] [rbp-38h] BYREF
  struct RdpNanoIceCandidate *v172; // [rsp+100h] [rbp-30h] BYREF
  _QWORD *v173; // [rsp+108h] [rbp-28h]
  const char *v174; // [rsp+110h] [rbp-20h]
  const char *v175; // [rsp+118h] [rbp-18h] BYREF
  const char *v176; // [rsp+120h] [rbp-10h] BYREF
  __int64 v177; // [rsp+128h] [rbp-8h] BYREF
  const char *v178; // [rsp+130h] [rbp+0h] BYREF
  const char *v179; // [rsp+138h] [rbp+8h] BYREF
  const char *v180; // [rsp+140h] [rbp+10h] BYREF
  const char *v181; // [rsp+148h] [rbp+18h] BYREF
  struct RdpNanoIceCandidate *v182; // [rsp+150h] [rbp+20h] BYREF
  struct RdpNanoIceCandidate *v183; // [rsp+158h] [rbp+28h] BYREF
  const char *v184; // [rsp+160h] [rbp+30h] BYREF
  EVENT_DESCRIPTOR *v185; // [rsp+168h] [rbp+38h] BYREF
  const char *v186; // [rsp+170h] [rbp+40h] BYREF
  const char *v187; // [rsp+178h] [rbp+48h] BYREF
  EVENT_DESCRIPTOR v188; // [rsp+180h] [rbp+50h] BYREF
  EVENT_DESCRIPTOR v189; // [rsp+190h] [rbp+60h] BYREF
  GUID ActivityId; // [rsp+1A0h] [rbp+70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1B0h] [rbp+80h] BYREF
  char *v192; // [rsp+1C0h] [rbp+90h]
  int v193; // [rsp+1C8h] [rbp+98h]
  int v194; // [rsp+1CCh] [rbp+9Ch]
  const char *v195; // [rsp+1D0h] [rbp+A0h]
  __int64 v196; // [rsp+1D8h] [rbp+A8h]
  struct RdpNanoIceCandidate **v197; // [rsp+1E0h] [rbp+B0h]
  __int64 v198; // [rsp+1E8h] [rbp+B8h]
  const char *v199; // [rsp+1F0h] [rbp+C0h]
  __int64 v200; // [rsp+1F8h] [rbp+C8h]
  const char *v201; // [rsp+200h] [rbp+D0h]
  __int64 v202; // [rsp+208h] [rbp+D8h]
  EVENT_DESCRIPTOR *v203; // [rsp+210h] [rbp+E0h]
  __int64 v204; // [rsp+218h] [rbp+E8h]
  const char *v205; // [rsp+220h] [rbp+F0h]
  int v206; // [rsp+228h] [rbp+F8h]
  int v207; // [rsp+22Ch] [rbp+FCh]
  const char *v208; // [rsp+230h] [rbp+100h]
  int v209; // [rsp+238h] [rbp+108h]
  int v210; // [rsp+23Ch] [rbp+10Ch]
  const char *v211; // [rsp+240h] [rbp+110h]
  int v212; // [rsp+248h] [rbp+118h]
  int v213; // [rsp+24Ch] [rbp+11Ch]
  const char *v214; // [rsp+250h] [rbp+120h]
  int v215; // [rsp+258h] [rbp+128h]
  int v216; // [rsp+25Ch] [rbp+12Ch]
  const char *v217; // [rsp+260h] [rbp+130h]
  int v218; // [rsp+268h] [rbp+138h]
  int v219; // [rsp+26Ch] [rbp+13Ch]
  const char *v220; // [rsp+270h] [rbp+140h]
  int v221; // [rsp+278h] [rbp+148h]
  int v222; // [rsp+27Ch] [rbp+14Ch]
  const char *v223; // [rsp+280h] [rbp+150h]
  int v224; // [rsp+288h] [rbp+158h]
  int v225; // [rsp+28Ch] [rbp+15Ch]
  const char *v226; // [rsp+290h] [rbp+160h]
  int v227; // [rsp+298h] [rbp+168h]
  int v228; // [rsp+29Ch] [rbp+16Ch]

  v3 = 0;
  v174 = (const char *)a3;
  v4 = a3;
  v166 = 0;
  if ( !*((_DWORD *)this + 102) )
  {
    v153 = *((_DWORD *)a3 + 17);
    v154 = 7;
    if ( v153 < *((_DWORD *)a3 + 16) )
    {
      v155 = v153;
      v156 = *((_QWORD *)a3 + 7);
      v157 = 2 * v155;
      v158 = *(unsigned int *)(v156 + 8 * v157);
      if ( (unsigned int)v158 >= *((_DWORD *)v4 + 8)
        || (v159 = *(unsigned int *)(v156 + 8 * v157 + 4), (unsigned int)v159 >= *((_DWORD *)v4 + 12)) )
      {
        if ( (unsigned int)dword_1808B5850 > 3 )
        {
          v196 = 43;
          v195 = "Invalid RdpNanoIceConnectionInfo structure";
          *(_DWORD *)&v189.Level = 3;
          UserData.Ptr = (ULONGLONG)off_1808B5858;
          *(_DWORD *)&v189.Id = 184549376;
          v189.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1808B5858;
          v192 = &byte_18087EBC7;
          UserData.Reserved = 2;
          v193 = 15;
          v194 = 1;
          v162 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v189, 0, 0, 3u, &UserData);
        }
        return 0;
      }
      v160 = *(_DWORD *)(*((_QWORD *)v4 + 5) + 40 * v159);
      v161 = *(_DWORD *)(*((_QWORD *)v4 + 3) + 40 * v158);
      if ( v161 <= v160 )
        v161 = v160;
      v154 = RdpNanoIceCandidateTypeToType(v161);
    }
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v162 = v154;
      v197 = (struct RdpNanoIceCandidate **)&v162;
      v198 = 4;
      v195 = "ICE: Updated active link type";
      *(_DWORD *)&v189.Level = 4;
      UserData.Ptr = (ULONGLONG)off_1808B5858;
      v196 = 30;
      *(_DWORD *)&v189.Id = 184549376;
      v189.Keyword = (ULONGLONG)v3;
      UserData.Size = *(unsigned __int16 *)off_1808B5858;
      v192 = (char *)&dword_18087CC6C;
      UserData.Reserved = 2;
      v193 = 25;
      v194 = 1;
      LODWORD(v163) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v189, 0, v3, 4u, &UserData);
    }
    return 0;
  }
  if ( !(unsigned int)SessionCtlBlkManager::Find((CRdpUdpTransport *)((char *)this + 416), a2, &v166) )
  {
    v189 = (EVENT_DESCRIPTOR)*((_OWORD *)v166 + 6);
    ActivityId = (GUID)v189;
    EventActivityIdControl(4u, &ActivityId);
    v11 = *((_DWORD *)v4 + 16);
    if ( v11 )
    {
      v12 = v11;
      v162 = 7;
      v14 = v11;
      v13 = (unsigned __int64)v11 << 6;
      v15 = -1;
      v165 = -1;
      if ( !is_mul_ok(v14, 0x40u) )
        v13 = -1;
      v16 = __CFADD__(v13, 8);
      v17 = v13 + 8;
      if ( v16 )
        v17 = -1;
      v18 = operator new(v17);
      if ( v18 )
      {
        *v18 = v12;
        v173 = v18 + 1;
        v19 = (SessionStartupCtl::SmilesLinkInfo *)(v18 + 1);
        do
        {
          SessionStartupCtl::SmilesLinkInfo::SmilesLinkInfo(v19);
          v19 = (SessionStartupCtl::SmilesLinkInfo *)((char *)v19 + 64);
          --v12;
        }
        while ( v12 );
        v18 = v173;
        v15 = v165;
      }
      else
      {
        v173 = 0;
      }
      memset_0(v18, 0, (unsigned __int64)*((unsigned int *)v4 + 16) << 6);
      v20 = v166;
      v21 = pszFormat;
      LODWORD(v22) = 0;
      v178 = pszFormat;
      v23 = 0;
      v164 = 0;
      LODWORD(v171) = 0;
      v177 = 0x470000000000LL;
      if ( *((_DWORD *)v4 + 16) )
      {
        while ( 1 )
        {
          v24 = *((_DWORD *)v4 + 17);
          v25 = *((_QWORD *)v4 + 7);
          v26 = v23 == v24;
          LODWORD(v172) = v24;
          v27 = *(unsigned int *)(v25 + 16LL * v23);
          if ( (unsigned int)v27 >= *((_DWORD *)v4 + 8) )
            break;
          v28 = *(unsigned int *)(v25 + 16LL * v23 + 4);
          if ( (unsigned int)v28 >= *((_DWORD *)v4 + 12) )
            break;
          v29 = *((_QWORD *)v4 + 3);
          LODWORD(v163) = v15;
          v30 = v15;
          v31 = (struct RdpNanoIceCandidate *)(v29 + 40 * v27);
          v32 = *((_QWORD *)v4 + 5);
          v168 = v31;
          v33 = (struct RdpNanoIceCandidate *)(v32 + 40 * v28);
          v169 = v33;
          if ( v23 == v24 )
          {
            v34 = 0;
            if ( *(_DWORD *)v31 )
            {
              switch ( *(_DWORD *)v31 )
              {
                case 1:
                case 2:
                  v34 = 2;
                  break;
                case 3:
                  v34 = 3;
                  break;
                case 4:
                  v34 = 4;
                  break;
              }
            }
            else
            {
              v34 = 1;
            }
            v35 = 0;
            if ( *(_DWORD *)v33 )
            {
              switch ( *(_DWORD *)v33 )
              {
                case 1:
                case 2:
                  v35 = 2;
                  break;
                case 3:
                  v35 = 3;
                  break;
                case 4:
                  v35 = 4;
                  break;
              }
            }
            else
            {
              v35 = 1;
            }
            if ( v34 == 4 )
              v34 = 2;
            if ( v35 == 4 )
              v35 = 2;
            if ( v34 > v35 )
              v35 = v34;
            v162 = v35;
          }
          v36 = *((_QWORD *)v20 + 16);
          v37 = 0;
          if ( v36 )
          {
            v38 = *((_DWORD *)v20 + 28);
            if ( v38 )
            {
              while ( 1 )
              {
                v39 = (unsigned __int64)v37 << 6;
                if ( (unsigned int)SessionStartupCtl::SmilesLinkInfo::IsEqual(
                                     (SessionStartupCtl::SmilesLinkInfo *)(v39 + v36),
                                     v168,
                                     v169) )
                  break;
                if ( ++v37 >= v38 )
                  goto LABEL_51;
              }
              *(_DWORD *)(v39 + v36 + 56) = 1;
              *(_DWORD *)(*((_QWORD *)v166 + 16) + v39 + 60) = v26;
              v20 = v166;
LABEL_51:
              v23 = (unsigned int)v171;
              v4 = (struct RdpNanoIceConnectionInfo *)v174;
              v33 = v169;
              v30 = (int)v163;
              v24 = (int)v172;
            }
            v31 = v168;
          }
          if ( v37 == *((_DWORD *)v20 + 28) )
          {
            v40 = v164;
            v41 = v164;
            if ( v23 != v24 )
              v41 = v30;
            v165 = v41;
            v43 = SessionStartupCtl::SmilesLinkInfo::Set(
                    (SessionStartupCtl::SmilesLinkInfo *)&v173[8 * (unsigned __int64)v164],
                    v31,
                    v33,
                    v26);
            if ( v43 )
            {
              if ( (unsigned int)dword_1808B5850 > 2 )
              {
                v162 = 739;
                v170 = "OnICEUpdateConnectionType";
                LODWORD(v163) = v43;
                v176 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
                v175 = "Set new links failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v42,
                  (unsigned int)&word_18087CC86,
                  v44,
                  v45,
                  (__int64)&v175,
                  (__int64)&v163,
                  (__int64)&v176,
                  (__int64)&v162,
                  (__int64)&v170);
              }
              EventActivityIdControl(2u, &ActivityId);
              return v43;
            }
            v164 = v40 + 1;
            if ( (unsigned int)dword_1808B5850 > 4
              && (qword_1808B5860 & 0x470000000000LL) != 0
              && (qword_1808B5868 & 0x470000000000LL) == qword_1808B5868 )
            {
              v46 = (const char *)*((_QWORD *)v33 + 3);
              v47 = 0;
              v48 = (const char *)*((_QWORD *)v33 + 1);
              v49 = (const char *)*((_QWORD *)v33 + 2);
              v50 = (const char *)*((_QWORD *)v31 + 3);
              v51 = (const char *)*((_QWORD *)v31 + 1);
              v52 = (const char *)*((_QWORD *)v31 + 2);
              if ( *(_DWORD *)v33 )
              {
                switch ( *(_DWORD *)v33 )
                {
                  case 1:
                  case 2:
                    v47 = 2;
                    break;
                  case 3:
                    v47 = 3;
                    break;
                  case 4:
                    v47 = 4;
                    break;
                }
              }
              else
              {
                v47 = 1;
              }
              v53 = (const char *)*(&off_1806BD210 + v47);
              v54 = 0;
              if ( *(_DWORD *)v31 )
              {
                switch ( *(_DWORD *)v31 )
                {
                  case 1:
                  case 2:
                    v54 = 2;
                    break;
                  case 3:
                    v54 = 3;
                    break;
                  case 4:
                    v54 = 4;
                    break;
                }
              }
              else
              {
                v54 = 1;
              }
              v55 = (const char *)*(&off_1806BD210 + v54);
              v168 = (struct RdpNanoIceCandidate *)0x1000000;
              if ( v46 )
              {
                v56 = -1;
                do
                  ++v56;
                while ( v46[v56] );
                v57 = v56 + 1;
              }
              else
              {
                v57 = 1;
                v46 = pszFormat;
              }
              v226 = v46;
              v227 = v57;
              v228 = 0;
              if ( v48 )
              {
                v58 = -1;
                do
                  ++v58;
                while ( v48[v58] );
                v59 = v58 + 1;
              }
              else
              {
                v48 = pszFormat;
                v59 = 1;
              }
              v223 = v48;
              v224 = v59;
              v225 = 0;
              if ( v49 )
              {
                v60 = -1;
                do
                  ++v60;
                while ( v49[v60] );
                v61 = v60 + 1;
              }
              else
              {
                v49 = pszFormat;
                v61 = 1;
              }
              v220 = v49;
              v221 = v61;
              v222 = 0;
              if ( v50 )
              {
                v62 = -1;
                do
                  ++v62;
                while ( v50[v62] );
                v63 = v62 + 1;
              }
              else
              {
                v50 = pszFormat;
                v63 = 1;
              }
              v217 = v50;
              v218 = v63;
              v219 = 0;
              if ( v51 )
              {
                v64 = -1;
                do
                  ++v64;
                while ( v51[v64] );
                v65 = v64 + 1;
              }
              else
              {
                v51 = pszFormat;
                v65 = 1;
              }
              v214 = v51;
              v215 = v65;
              v216 = 0;
              if ( v52 )
              {
                v66 = -1;
                do
                  ++v66;
                while ( v52[v66] );
                v67 = v66 + 1;
              }
              else
              {
                v52 = pszFormat;
                v67 = 1;
              }
              v211 = v52;
              v212 = v67;
              v213 = 0;
              if ( v53 )
              {
                v68 = -1;
                do
                  ++v68;
                while ( v53[v68] );
                v69 = v68 + 1;
              }
              else
              {
                v53 = pszFormat;
                v69 = 1;
              }
              v208 = v53;
              v209 = v69;
              v210 = 0;
              if ( v55 )
              {
                v70 = -1;
                do
                  ++v70;
                while ( v55[v70] );
                v71 = v70 + 1;
              }
              else
              {
                v55 = pszFormat;
                v71 = 1;
              }
              v206 = v71;
              v205 = v55;
              v203 = &v189;
              v207 = 0;
              v201 = "Udp";
              v204 = 16;
              v199 = "Stack";
              v202 = 4;
              v197 = &v168;
              v195 = "Checkpoint";
              *(_DWORD *)&EventDescriptor.Level = 11268;
              EventDescriptor.Keyword = 0x470000000000LL;
              UserData.Ptr = (ULONGLONG)off_1808B5858;
              v200 = 6;
              v198 = 8;
              v196 = 11;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              UserData.Size = *(unsigned __int16 *)off_1808B5858;
              v192 = (char *)&word_18087D39E;
              UserData.Reserved = 2;
              v193 = 233;
              v194 = 1;
              LODWORD(v163) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xFu, &UserData);
              v33 = v169;
            }
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              v72 = 0;
              v73 = *(_DWORD *)v33;
              v169 = (struct RdpNanoIceCandidate *)*((_QWORD *)v33 + 3);
              v168 = (struct RdpNanoIceCandidate *)*((_QWORD *)v33 + 1);
              v163 = (const char *)*((_QWORD *)v33 + 2);
              v172 = (struct RdpNanoIceCandidate *)*((_QWORD *)v31 + 3);
              v179 = (const char *)*((_QWORD *)v31 + 1);
              v180 = (const char *)*((_QWORD *)v31 + 2);
              if ( v73 )
              {
                v74 = v73 - 1;
                if ( v74 && (v75 = v74 - 1) != 0 )
                {
                  v76 = v75 - 1;
                  if ( v76 )
                  {
                    if ( v76 == 1 )
                      v72 = 4;
                  }
                  else
                  {
                    v72 = 3;
                  }
                }
                else
                {
                  v72 = 2;
                }
              }
              else
              {
                v72 = 1;
              }
              v77 = (const char *)*(&off_1806BD210 + v72);
              v78 = 0;
              v79 = *(_DWORD *)v31;
              v175 = v77;
              if ( v79 )
              {
                if ( --v79 && (--v79, v79) )
                {
                  if ( --v79 )
                  {
                    if ( v79 == 1 )
                      v78 = 4;
                  }
                  else
                  {
                    v78 = 3;
                  }
                }
                else
                {
                  v78 = 2;
                }
              }
              else
              {
                v78 = 1;
              }
              v176 = (const char *)*(&off_1806BD210 + v78);
              v170 = "ICE: Smiles Add Link";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v79,
                (unsigned int)byte_18087B97B,
                v44,
                v45,
                (__int64)&v170,
                (__int64)&v176,
                (__int64)&v175,
                (__int64)&v180,
                (__int64)&v179,
                (__int64)&v172,
                (__int64)&v163,
                (__int64)&v168,
                (__int64)&v169);
            }
            v20 = v166;
            v4 = (struct RdpNanoIceConnectionInfo *)v174;
            v23 = (unsigned int)v171;
          }
          LODWORD(v171) = ++v23;
          if ( v23 >= *((_DWORD *)v4 + 16) )
          {
            LODWORD(v22) = v164;
            v21 = pszFormat;
            goto LABEL_149;
          }
          v15 = v165;
        }
        if ( (unsigned int)dword_1808B5850 > 3 )
        {
          v196 = 43;
          v195 = "Invalid RdpNanoIceConnectionInfo structure";
          *(_DWORD *)&EventDescriptor.Level = 3;
          UserData.Ptr = (ULONGLONG)off_1808B5858;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1808B5858;
          v192 = (char *)&dword_18087CA44;
          UserData.Reserved = 2;
          v193 = 15;
          v194 = 1;
          v162 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        EventActivityIdControl(2u, &ActivityId);
        return 0;
      }
LABEL_149:
      v80 = 0;
      if ( *((_DWORD *)v20 + 28) )
      {
        v81 = 0;
        do
        {
          v82 = (const char **)(*((_QWORD *)v20 + 16) + ((unsigned __int64)v80 << 6));
          if ( *((_DWORD *)v82 + 14) )
          {
            v83 = *((_DWORD *)v82 + 15) == 0;
            v84 = (unsigned int)v22;
            *((_DWORD *)v82 + 14) = v81;
            if ( v83 )
              v84 = v165;
            v165 = v84;
            if ( v80 == *((_DWORD *)v166 + 30) )
              *((_DWORD *)v166 + 30) = (_DWORD)v22;
            v164 = (_DWORD)v22 + 1;
            SessionStartupCtl::SmilesLinkInfo::Transfer(
              (SessionStartupCtl::SmilesLinkInfo *)&v173[8 * (unsigned __int64)(unsigned int)v22],
              (struct SessionStartupCtl::SmilesLinkInfo *)v82);
          }
          else
          {
            if ( (unsigned int)dword_1808B5850 > 4
              && (qword_1808B5860 & 0x470000000000LL) != 0
              && (qword_1808B5868 & 0x470000000000LL) == qword_1808B5868 )
            {
              v85 = v82[6];
              v86 = v82[5];
              v87 = v82[4];
              v88 = (const char *)*(&off_1806BD210 + *((unsigned int *)v82 + 1));
              v89 = v82[3];
              v90 = v82[2];
              v91 = v82[1];
              v92 = (const char *)*(&off_1806BD210 + *(unsigned int *)v82);
              v170 = (const char *)0x1000000;
              if ( v85 )
              {
                v93 = -1;
                do
                  ++v93;
                while ( v85[v93] );
                v94 = v93 + 1;
              }
              else
              {
                v85 = pszFormat;
                v94 = 1;
              }
              v226 = v85;
              v227 = v94;
              v228 = 0;
              if ( v86 )
              {
                v95 = -1;
                do
                  ++v95;
                while ( v86[v95] );
                v96 = v95 + 1;
              }
              else
              {
                v86 = pszFormat;
                v96 = 1;
              }
              v223 = v86;
              v224 = v96;
              v225 = 0;
              if ( v87 )
              {
                v97 = -1;
                do
                  ++v97;
                while ( v87[v97] );
                v98 = v97 + 1;
              }
              else
              {
                v87 = pszFormat;
                v98 = 1;
              }
              v220 = v87;
              v221 = v98;
              v222 = 0;
              if ( v89 )
              {
                v99 = -1;
                do
                  ++v99;
                while ( v89[v99] );
                v100 = v99 + 1;
              }
              else
              {
                v89 = pszFormat;
                v100 = 1;
              }
              v217 = v89;
              v218 = v100;
              v219 = 0;
              if ( v90 )
              {
                v101 = -1;
                do
                  ++v101;
                while ( v90[v101] );
                v102 = v101 + 1;
              }
              else
              {
                v90 = pszFormat;
                v102 = 1;
              }
              v214 = v90;
              v215 = v102;
              v216 = 0;
              if ( v91 )
              {
                v103 = -1;
                do
                  ++v103;
                while ( v91[v103] );
                v104 = v103 + 1;
              }
              else
              {
                v91 = pszFormat;
                v104 = 1;
              }
              v211 = v91;
              v212 = v104;
              v213 = 0;
              if ( v88 )
              {
                v105 = -1;
                do
                  ++v105;
                while ( v88[v105] );
                v106 = v105 + 1;
              }
              else
              {
                v88 = pszFormat;
                v106 = 1;
              }
              v208 = v88;
              v209 = v106;
              v210 = 0;
              if ( v92 )
              {
                v107 = -1;
                do
                  ++v107;
                while ( v92[v107] );
                v108 = v107 + 1;
              }
              else
              {
                v92 = pszFormat;
                v108 = 1;
              }
              v206 = v108;
              v205 = v92;
              v203 = &v189;
              v207 = 0;
              v201 = "Udp";
              v204 = 16;
              v199 = "Stack";
              v202 = 4;
              v197 = (struct RdpNanoIceCandidate **)&v170;
              v195 = "Checkpoint";
              *(_DWORD *)&EventDescriptor.Level = 11268;
              EventDescriptor.Keyword = 0x470000000000LL;
              UserData.Ptr = (ULONGLONG)off_1808B5858;
              v200 = 6;
              v198 = 8;
              v196 = 11;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              UserData.Size = *(unsigned __int16 *)off_1808B5858;
              v192 = &byte_18087DE3F;
              UserData.Reserved = 2;
              v193 = 236;
              v194 = 1;
              LODWORD(v163) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xFu, &UserData);
            }
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              v109 = v82[6];
              v110 = v82[5];
              v111 = v82[4];
              v112 = v82[3];
              v113 = v82[2];
              v114 = v82[1];
              v115 = (const char *)*(&off_1806BD210 + *((unsigned int *)v82 + 1));
              v116 = (const char *)*(&off_1806BD210 + *(unsigned int *)v82);
              if ( v109 )
              {
                v117 = -1;
                do
                  ++v117;
                while ( v109[v117] );
                v118 = v117 + 1;
              }
              else
              {
                v109 = pszFormat;
                v118 = 1;
              }
              v214 = v109;
              v215 = v118;
              v216 = 0;
              if ( v110 )
              {
                v119 = -1;
                do
                  ++v119;
                while ( v110[v119] );
                v120 = v119 + 1;
              }
              else
              {
                v110 = pszFormat;
                v120 = 1;
              }
              v211 = v110;
              v212 = v120;
              v213 = 0;
              if ( v111 )
              {
                v121 = -1;
                do
                  ++v121;
                while ( v111[v121] );
                v122 = v121 + 1;
              }
              else
              {
                v111 = pszFormat;
                v122 = 1;
              }
              v208 = v111;
              v209 = v122;
              v210 = 0;
              if ( v112 )
              {
                v123 = -1;
                do
                  ++v123;
                while ( v112[v123] );
                v124 = v123 + 1;
              }
              else
              {
                v112 = pszFormat;
                v124 = 1;
              }
              v205 = v112;
              v206 = v124;
              v207 = 0;
              if ( v113 )
              {
                v125 = -1;
                do
                  ++v125;
                while ( v113[v125] );
                v126 = v125 + 1;
              }
              else
              {
                v113 = pszFormat;
                v126 = 1;
              }
              v203 = (EVENT_DESCRIPTOR *)v113;
              v204 = v126;
              if ( v114 )
              {
                v127 = -1;
                do
                  ++v127;
                while ( v114[v127] );
                v128 = v127 + 1;
              }
              else
              {
                v114 = pszFormat;
                v128 = 1;
              }
              v201 = v114;
              v202 = v128;
              if ( v115 )
              {
                v129 = -1;
                do
                  ++v129;
                while ( v115[v129] );
                v130 = v129 + 1;
              }
              else
              {
                v115 = pszFormat;
                v130 = 1;
              }
              v199 = v115;
              v200 = v130;
              if ( v116 )
              {
                v131 = -1;
                do
                  ++v131;
                while ( v116[v131] );
                v132 = v131 + 1;
              }
              else
              {
                v116 = pszFormat;
                v132 = 1;
              }
              v198 = v132;
              v197 = (struct RdpNanoIceCandidate **)v116;
              v195 = "ICE: Smiles Remove Link";
              *(_DWORD *)&v188.Level = 4;
              UserData.Ptr = (ULONGLONG)off_1808B5858;
              v196 = 24;
              *(_DWORD *)&v188.Id = 184549376;
              v188.Keyword = 0;
              UserData.Size = *(unsigned __int16 *)off_1808B5858;
              v192 = byte_18087D8A3;
              UserData.Reserved = 2;
              v193 = 167;
              v194 = 1;
              LODWORD(v163) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &v188, 0, 0, 0xBu, &UserData);
            }
            v81 = 0;
          }
          v20 = v166;
          ++v80;
          LODWORD(v22) = v164;
        }
        while ( v80 < *((_DWORD *)v166 + 28) );
      }
      v133 = *((_DWORD *)v20 + 30);
      v134 = v165;
      if ( v133 != v165 )
      {
        v135 = pszFormat;
        v136 = pszFormat;
        v137 = pszFormat;
        v138 = pszFormat;
        v139 = pszFormat;
        if ( v133 == -1 )
        {
          v145 = pszFormat;
          v174 = pszFormat;
          v142 = pszFormat;
          v169 = (struct RdpNanoIceCandidate *)pszFormat;
          v143 = (struct RdpNanoIceCandidate *)pszFormat;
          v141 = (struct RdpNanoIceCandidate *)pszFormat;
        }
        else
        {
          v140 = (unsigned int *)&v173[8 * (unsigned __int64)v133];
          v141 = (struct RdpNanoIceCandidate *)*((_QWORD *)v140 + 5);
          v142 = (const char *)*((_QWORD *)v140 + 2);
          v143 = (struct RdpNanoIceCandidate *)*((_QWORD *)v140 + 4);
          v21 = (const char *)*(&off_1806BD210 + *v140);
          v144 = v140[1];
          v169 = v141;
          v145 = (const char *)*(&off_1806BD210 + v144);
          v22 = (const char *)*((_QWORD *)v140 + 1);
          v174 = v22;
        }
        LODWORD(v146) = v165;
        v168 = v143;
        v163 = v142;
        if ( v165 == -1 )
        {
          v147 = pszFormat;
        }
        else
        {
          v146 = (unsigned int *)&v173[8 * (unsigned __int64)v165];
          v136 = (const char *)*((_QWORD *)v146 + 1);
          v137 = (const char *)*((_QWORD *)v146 + 2);
          v138 = (const char *)*((_QWORD *)v146 + 4);
          v147 = (const char *)*(&off_1806BD210 + *v146);
          v148 = v146[1];
          v139 = (const char *)*((_QWORD *)v146 + 5);
          v178 = v147;
          v135 = (const char *)*(&off_1806BD210 + v148);
        }
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          LODWORD(v146) = qword_1808B5868;
          LODWORD(v22) = (_DWORD)v174;
          if ( (qword_1808B5860 & 0x470000000000LL) != 0 && (v177 & qword_1808B5868) == qword_1808B5868 )
          {
            v182 = (struct RdpNanoIceCandidate *)v174;
            v185 = &v189;
            v177 = (__int64)v139;
            v186 = "Udp";
            v187 = "Stack";
            *(_QWORD *)&EventDescriptor.Id = "Checkpoint";
            v170 = v138;
            v176 = v137;
            v175 = v136;
            v180 = v135;
            v179 = v147;
            v172 = v141;
            v171 = v143;
            v181 = v142;
            v183 = (struct RdpNanoIceCandidate *)v145;
            v184 = v21;
            *(_QWORD *)&v188.Id = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              qword_1808B5868,
              (unsigned int)&dword_18087E454,
              (_DWORD)v142,
              (_DWORD)v143,
              (__int64)&EventDescriptor,
              (__int64)&v188,
              (__int64)&v187,
              (__int64)&v186,
              (__int64)&v185,
              (__int64)&v184,
              (__int64)&v183,
              (__int64)&v182,
              (__int64)&v181,
              (__int64)&v171,
              (__int64)&v172,
              (__int64)&v179,
              (__int64)&v180,
              (__int64)&v175,
              (__int64)&v176,
              (__int64)&v170,
              (__int64)&v177);
          }
        }
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v184 = v178;
          v183 = v169;
          v182 = v168;
          v181 = v163;
          v177 = (__int64)v174;
          v175 = "ICE: Smiles Switch Active Link";
          *(_QWORD *)&EventDescriptor.Id = v139;
          *(_QWORD *)&v188.Id = v138;
          v187 = v137;
          v186 = v136;
          v185 = (EVENT_DESCRIPTOR *)v135;
          v170 = v145;
          v176 = v21;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)v146,
            (unsigned int)byte_18087CAF9,
            (_DWORD)v142,
            (_DWORD)v143,
            (__int64)&v175,
            (__int64)&v176,
            (__int64)&v170,
            (__int64)&v177,
            (__int64)&v181,
            (__int64)&v182,
            (__int64)&v183,
            (__int64)&v184,
            (__int64)&v185,
            (__int64)&v186,
            (__int64)&v187,
            (__int64)&v188,
            (__int64)&EventDescriptor);
        }
        v134 = v165;
      }
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v198 = 4;
        v197 = (struct RdpNanoIceCandidate **)&v162;
        v196 = 30;
        v195 = "ICE: Updated active link type";
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = (ULONGLONG)off_1808B5858;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1808B5858;
        v192 = byte_18087CF31;
        UserData.Reserved = 2;
        v193 = 25;
        v194 = 1;
        LODWORD(v163) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
      v149 = v166;
      if ( *((_DWORD *)v166 + 30) == -1 && v134 != -1 )
      {
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v196 = 34;
          v195 = "ICE: Set first Smiles active Link";
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_1808B5858;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1808B5858;
          v192 = (char *)qword_18087D5E0;
          UserData.Reserved = 2;
          v193 = 19;
          v194 = 1;
          v162 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        v149 = v166;
      }
      v150 = (SessionStartupCtl::SmilesLinkInfo *)*((_QWORD *)v149 + 16);
      if ( v150 )
        SessionStartupCtl::SmilesLinkInfo::`vector deleting destructor'(v150, (unsigned int)v22);
      v151 = v164;
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v162 = v164;
        LODWORD(v163) = v134;
        LODWORD(v172) = *((_DWORD *)v166 + 28);
        LODWORD(v171) = *((_DWORD *)v166 + 30);
        v203 = (EVENT_DESCRIPTOR *)&v162;
        v201 = (const char *)&v163;
        v199 = (const char *)&v172;
        v197 = &v171;
        v195 = "ICE: swap smilesLinkInfo";
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = (ULONGLONG)off_1808B5858;
        v204 = 4;
        v202 = 4;
        v200 = 4;
        v198 = 4;
        v196 = 25;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1808B5858;
        v192 = byte_18087D755;
        UserData.Reserved = 2;
        v193 = 103;
        v194 = 1;
        v164 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
      }
      v152 = v173;
      *((_DWORD *)v166 + 30) = v134;
      *((_QWORD *)v166 + 16) = v152;
      *((_DWORD *)v166 + 28) = v151;
    }
    EventActivityIdControl(2u, &ActivityId);
    return 0;
  }
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v162 = *((_DWORD *)this + 109);
    v178 = "ICE: find SessionStartupCtl for request failed";
    LODWORD(v163) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&dword_18087DF4C,
      v8,
      v9,
      (__int64)&v178,
      (__int64)&v163,
      (__int64)&v162);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180416940  mov     [rsp-8+arg_8], rbx
0x180416945  push    rbp
0x180416946  push    rsi
0x180416947  push    rdi
0x180416948  push    r12
0x18041694a  push    r13
0x18041694c  push    r14
0x18041694e  push    r15
0x180416950  lea     rbp, [rsp-180h]
0x180416958  sub     rsp, 2B0h
0x18041695f  mov     rax, cs:__security_cookie
0x180416966  xor     rax, rsp
0x180416969  mov     [rbp+1B0h+var_40], rax
0x180416970  xor     r9d, r9d
0x180416973  mov     [rbp+1B0h+var_1D0], r8
0x180416977  mov     rsi, r8
0x18041697a  mov     edi, edx
0x18041697c  mov     rbx, rcx
0x18041697f  mov     [rbp+1B0h+var_218], r9
0x180416983  cmp     [rcx+198h], r9d
0x18041698a  jz      loc_180417F69
0x180416990  add     rcx, 1A0h; this
0x180416997  lea     r8, [rbp+1B0h+var_218]; struct SessionStartupCtl **
0x18041699b  call    ?Find@SessionCtlBlkManager@@QEAAJIPEAPEAUSessionStartupCtl@@@Z; SessionCtlBlkManager::Find(uint,SessionStartupCtl * *)
0x1804169a0  test    eax, eax
0x1804169a2  jz      short loc_1804169F7
0x1804169a4  mov     eax, cs:dword_1808B5850
0x1804169aa  cmp     eax, 4
0x1804169ad  jbe     short loc_1804169ED
0x1804169af  mov     eax, [rbx+1B4h]
0x1804169b5  lea     rdx, dword_18087DF4C
0x1804169bc  mov     [rbp+1B0h+var_230], eax
0x1804169bf  lea     rax, aIceFindSession; "ICE: find SessionStartupCtl for request"...
0x1804169c6  mov     [rbp+1B0h+var_1B0], rax
0x1804169ca  lea     rax, [rbp+1B0h+var_230]
0x1804169ce  mov     [rsp+2E0h+var_2B0], rax
0x1804169d3  lea     rax, [rbp+1B0h+var_228]
0x1804169d7  mov     [rsp+2E0h+UserData], rax
0x1804169dc  lea     rax, [rbp+1B0h+var_1B0]
0x1804169e0  mov     qword ptr [rsp+2E0h+UserDataCount], rax
0x1804169e5  mov     dword ptr [rbp+1B0h+var_228], edi
0x1804169e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1804169ed  mov     eax, 80004005h
0x1804169f2  jmp     loc_180418097
0x1804169f7  mov     rax, [rbp+1B0h+var_218]
0x1804169fb  lea     rdx, [rbp+1B0h+ActivityId]; ActivityId
0x1804169ff  mov     ecx, 4; ControlCode
0x180416a04  movups  xmm0, xmmword ptr [rax+60h]
0x180416a08  movaps  xmmword ptr [rbp+1B0h+var_150.Id], xmm0
0x180416a0c  movdqa  xmmword ptr [rbp+1B0h+ActivityId.Data1], xmm0
0x180416a11  call    cs:__imp_EventActivityIdControl
0x180416a17  mov     eax, [rsi+40h]
0x180416a1a  mov     r15d, 2
0x180416a20  test    eax, eax
0x180416a22  jz      loc_180417F57
0x180416a28  mov     ebx, eax
0x180416a2a  mov     [rbp+1B0h+var_230], 7
0x180416a31  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180416a38  mov     eax, 40h ; '@'
0x180416a3d  mul     rbx
0x180416a40  mov     edi, 0FFFFFFFFh
0x180416a45  mov     [rbp+1B0h+var_21C], edi
0x180416a48  cmovb   rax, rcx
0x180416a4c  add     rax, 8
0x180416a50  cmovb   rax, rcx
0x180416a54  mov     rcx, rax; Size
0x180416a57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180416a5c  test    rax, rax
0x180416a5f  jz      short loc_180416A8F
0x180416a61  mov     [rax], rbx
0x180416a64  add     rax, 8
0x180416a68  mov     [rbp+1B0h+var_1D8], rax
0x180416a6c  mov     rdi, rax
0x180416a6f  test    rbx, rbx
0x180416a72  jz      short loc_180416A8A
0x180416a74  mov     rcx, rdi; this
0x180416a77  call    ??0SmilesLinkInfo@SessionStartupCtl@@QEAA@XZ; SessionStartupCtl::SmilesLinkInfo::SmilesLinkInfo(void)
0x180416a7c  add     rdi, 40h ; '@'
0x180416a80  sub     rbx, 1
0x180416a84  jnz     short loc_180416A74
0x180416a86  mov     rax, [rbp+1B0h+var_1D8]
0x180416a8a  mov     edi, [rbp+1B0h+var_21C]
0x180416a8d  jmp     short loc_180416A93
0x180416a8f  mov     [rbp+1B0h+var_1D8], rax
0x180416a93  mov     r8d, [rsi+40h]
0x180416a97  xor     edx, edx; Val
0x180416a99  shl     r8, 6; Size
0x180416a9d  mov     rcx, rax; void *
0x180416aa0  call    memset_0
0x180416aa5  mov     r13, [rbp+1B0h+var_218]
0x180416aa9  lea     r12, pszFormat
0x180416ab0  xor     edx, edx
0x180416ab2  mov     [rbp+1B0h+var_1B0], r12
0x180416ab6  xor     r11d, r11d
0x180416ab9  mov     [rbp+1B0h+var_220], edx
0x180416abc  mov     r8, 470000000000h
0x180416ac6  mov     dword ptr [rbp+1B0h+var_1E8], r11d
0x180416aca  mov     [rbp+1B0h+var_1B8], r8
0x180416ace  cmp     [rsi+40h], edx
0x180416ad1  jbe     loc_1804172F5
0x180416ad7  nop     word ptr [rax+rax+00000000h]
0x180416ae0  mov     r9d, [rsi+44h]
0x180416ae4  xor     r12d, r12d
0x180416ae7  mov     rax, [rsi+38h]
0x180416aeb  cmp     r11d, r9d
0x180416aee  mov     ecx, r11d
0x180416af1  setz    r12b
0x180416af5  mov     dword ptr [rbp+1B0h+var_1E0], r9d
0x180416af9  add     rcx, rcx
0x180416afc  mov     r8d, [rax+rcx*8]
0x180416b00  cmp     r8d, [rsi+20h]
0x180416b04  jnb     loc_18041720B
0x180416b0a  mov     edx, [rax+rcx*8+4]
0x180416b0e  cmp     edx, [rsi+30h]
0x180416b11  jnb     loc_18041720B
0x180416b17  mov     rax, [rsi+18h]
0x180416b1b  lea     rcx, [r8+r8*4]
0x180416b1f  mov     dword ptr [rbp+1B0h+var_228], edi
0x180416b22  mov     r10d, edi
0x180416b25  lea     r14, [rax+rcx*8]
0x180416b29  mov     rax, [rsi+28h]
0x180416b2d  mov     [rbp+1B0h+var_200], r14
0x180416b31  lea     rcx, [rdx+rdx*4]
0x180416b35  lea     rdi, [rax+rcx*8]
0x180416b39  mov     [rbp+1B0h+var_1F8], rdi
0x180416b3d  cmp     r11d, r9d
0x180416b40  jnz     loc_180416BCD
0x180416b46  mov     ecx, [r14]
0x180416b49  xor     edx, edx
0x180416b4b  test    ecx, ecx
0x180416b4d  jz      short loc_180416B76
0x180416b4f  sub     ecx, 1
0x180416b52  jz      short loc_180416B71
0x180416b54  sub     ecx, 1
0x180416b57  jz      short loc_180416B71
0x180416b59  sub     ecx, 1
0x180416b5c  jz      short loc_180416B6A
0x180416b5e  cmp     ecx, 1
0x180416b61  jnz     short loc_180416B7B
0x180416b63  mov     edx, 4
0x180416b68  jmp     short loc_180416B7B
0x180416b6a  mov     edx, 3
0x180416b6f  jmp     short loc_180416B7B
0x180416b71  mov     edx, r15d
0x180416b74  jmp     short loc_180416B7B
0x180416b76  mov     edx, 1
0x180416b7b  mov     ecx, [rdi]
0x180416b7d  xor     r8d, r8d
0x180416b80  test    ecx, ecx
0x180416b82  jz      short loc_180416BAD
0x180416b84  sub     ecx, 1
0x180416b87  jz      short loc_180416BA8
0x180416b89  sub     ecx, 1
0x180416b8c  jz      short loc_180416BA8
0x180416b8e  sub     ecx, 1
0x180416b91  jz      short loc_180416BA0
0x180416b93  cmp     ecx, 1
0x180416b96  jnz     short loc_180416BB3
0x180416b98  mov     r8d, 4
0x180416b9e  jmp     short loc_180416BB3
0x180416ba0  mov     r8d, 3
0x180416ba6  jmp     short loc_180416BB3
0x180416ba8  mov     r8d, r15d
0x180416bab  jmp     short loc_180416BB3
0x180416bad  mov     r8d, 1
0x180416bb3  cmp     edx, 4
0x180416bb6  cmovz   edx, r15d
0x180416bba  cmp     r8d, 4
0x180416bbe  cmovz   r8d, r15d
0x180416bc2  cmp     edx, r8d
0x180416bc5  cmova   r8d, edx
0x180416bc9  mov     [rbp+1B0h+var_230], r8d
0x180416bcd  mov     r15, [r13+80h]
0x180416bd4  xor     ebx, ebx
0x180416bd6  test    r15, r15
0x180416bd9  jz      short loc_180416C4A
0x180416bdb  mov     r14d, [r13+70h]
0x180416bdf  test    r14d, r14d
0x180416be2  jz      short loc_180416C46
0x180416be4  nop     dword ptr [rax+00h]
0x180416be8  nop     dword ptr [rax+rax+00000000h]
0x180416bf0  mov     r8, [rbp+1B0h+var_1F8]; struct RdpNanoIceCandidate *
0x180416bf4  mov     rdx, [rbp+1B0h+var_200]; struct RdpNanoIceCandidate *
0x180416bf8  mov     edi, ebx
0x180416bfa  shl     rdi, 6
0x180416bfe  lea     rsi, [rdi+r15]
0x180416c02  mov     rcx, rsi; this
0x180416c05  call    ?IsEqual@SmilesLinkInfo@SessionStartupCtl@@QEAAHPEBURdpNanoIceCandidate@@0@Z; SessionStartupCtl::SmilesLinkInfo::IsEqual(RdpNanoIceCandidate const *,RdpNanoIceCandidate const *)
0x180416c0a  test    eax, eax
0x180416c0c  jnz     short loc_180416C17
0x180416c0e  inc     ebx
0x180416c10  cmp     ebx, r14d
0x180416c13  jb      short loc_180416BF0
0x180416c15  jmp     short loc_180416C32
0x180416c17  mov     dword ptr [rsi+38h], 1
0x180416c1e  mov     rax, [rbp+1B0h+var_218]
0x180416c22  mov     rcx, [rax+80h]
0x180416c29  mov     [rcx+rdi+3Ch], r12d
0x180416c2e  mov     r13, [rbp+1B0h+var_218]
0x180416c32  mov     r11d, dword ptr [rbp+1B0h+var_1E8]
0x180416c36  mov     rsi, [rbp+1B0h+var_1D0]
0x180416c3a  mov     rdi, [rbp+1B0h+var_1F8]
0x180416c3e  mov     r10d, dword ptr [rbp+1B0h+var_228]
0x180416c42  mov     r9d, dword ptr [rbp+1B0h+var_1E0]
0x180416c46  mov     r14, [rbp+1B0h+var_200]
0x180416c4a  cmp     ebx, [r13+70h]
0x180416c4e  jnz     loc_18041716D
0x180416c54  mov     esi, [rbp+1B0h+var_220]
0x180416c57  cmp     r11d, r9d
0x180416c5a  mov     eax, esi
0x180416c5c  mov     ecx, esi
0x180416c5e  cmovnz  eax, r10d
0x180416c62  mov     r9d, r12d; int
0x180416c65  shl     rcx, 6
0x180416c69  mov     r8, rdi; struct RdpNanoIceCandidate *
0x180416c6c  add     rcx, [rbp+1B0h+var_1D8]; this
0x180416c70  mov     rdx, r14; struct RdpNanoIceCandidate *
0x180416c73  mov     [rbp+1B0h+var_21C], eax
0x180416c76  call    ?Set@SmilesLinkInfo@SessionStartupCtl@@QEAAJPEBURdpNanoIceCandidate@@0H@Z; SessionStartupCtl::SmilesLinkInfo::Set(RdpNanoIceCandidate const *,RdpNanoIceCandidate const *,int)
0x180416c7b  mov     ebx, eax
0x180416c7d  test    eax, eax
0x180416c7f  mov     eax, cs:dword_1808B5850
0x180416c85  jnz     loc_18041718C
0x180416c8b  inc     esi
0x180416c8d  mov     [rbp+1B0h+var_220], esi
0x180416c90  cmp     eax, 4
0x180416c93  jbe     loc_18041702F
0x180416c99  mov     rcx, cs:qword_1808B5868
0x180416ca0  mov     rdx, 470000000000h
0x180416caa  mov     rax, cs:qword_1808B5860
0x180416cb1  test    rdx, rax
0x180416cb4  jz      loc_18041702F
0x180416cba  mov     rax, rcx
0x180416cbd  and     rax, rdx
0x180416cc0  cmp     rax, rcx
0x180416cc3  jnz     loc_18041702F
0x180416cc9  mov     ecx, [rdi]
0x180416ccb  xor     r15d, r15d
0x180416cce  mov     r8, [rdi+18h]
0x180416cd2  mov     edx, r15d
0x180416cd5  mov     r9, [rdi+8]
0x180416cd9  mov     r10, [rdi+10h]
0x180416cdd  mov     r11, [r14+18h]
0x180416ce1  mov     rbx, [r14+8]
0x180416ce5  mov     rsi, [r14+10h]
0x180416ce9  test    ecx, ecx
0x180416ceb  jz      short loc_180416D16
0x180416ced  sub     ecx, 1
0x180416cf0  jz      short loc_180416D0F
0x180416cf2  sub     ecx, 1
0x180416cf5  jz      short loc_180416D0F
0x180416cf7  sub     ecx, 1
0x180416cfa  jz      short loc_180416D08
0x180416cfc  cmp     ecx, 1
0x180416cff  jnz     short loc_180416D1B
0x180416d01  mov     edx, 4
0x180416d06  jmp     short loc_180416D1B
0x180416d08  mov     edx, 3
0x180416d0d  jmp     short loc_180416D1B
0x180416d0f  mov     edx, 2
0x180416d14  jmp     short loc_180416D1B
0x180416d16  mov     edx, 1
0x180416d1b  mov     ecx, [r14]
0x180416d1e  lea     r13, off_1806BD210
0x180416d25  mov     rdi, [r13+rdx*8+0]
0x180416d2a  mov     rdx, r15
0x180416d2d  test    ecx, ecx
0x180416d2f  jz      short loc_180416D5A
0x180416d31  sub     ecx, 1
0x180416d34  jz      short loc_180416D53
0x180416d36  sub     ecx, 1
0x180416d39  jz      short loc_180416D53
0x180416d3b  sub     ecx, 1
0x180416d3e  jz      short loc_180416D4C
0x180416d40  cmp     ecx, 1
0x180416d43  jnz     short loc_180416D5F
0x180416d45  mov     edx, 4
0x180416d4a  jmp     short loc_180416D5F
0x180416d4c  mov     edx, 3
0x180416d51  jmp     short loc_180416D5F
0x180416d53  mov     edx, 2
0x180416d58  jmp     short loc_180416D5F
0x180416d5a  mov     edx, 1
0x180416d5f  mov     rcx, [r13+rdx*8+0]
0x180416d64  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180416d6b  mov     [rbp+1B0h+var_200], 1000000h
0x180416d73  test    r8, r8
0x180416d76  jz      short loc_180416D94
0x180416d78  mov     rax, r12
0x180416d7b  nop     dword ptr [rax+rax+00h]
0x180416d80  inc     rax
0x180416d83  cmp     [r8+rax], r15b
0x180416d87  jnz     short loc_180416D80
0x180416d89  inc     eax
0x180416d8b  lea     rdx, pszFormat
0x180416d92  jmp     short loc_180416DA3
0x180416d94  lea     rdx, pszFormat
0x180416d9b  mov     eax, 1
0x180416da0  mov     r8, rdx
0x180416da3  mov     [rbp+1B0h+var_50], r8
  ... truncated ...
```
