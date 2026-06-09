# RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,RegistrationRequestSerializer::TokenType,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_VDI_SETTINGS const &,ushort * *)

- ea: `0x1800618b0`
- end: `0x180063e70`
- name: `?CreateRegistrationRequestBodyImpl@RegistrationRequestSerializer@@CAJPEBG0000000000000W4TokenType@1@000000000000AEBU_VDI_SETTINGS@@PEAPEAG@Z`
- size: `9664`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800612b0`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180012948`
- `0x18001b560`
- `0x18003334c`
- `0x180043ef8`
- `0x180044300`
- `0x1800448a0`
- `0x180044d30`
- `0x18004651c`
- `0x18004654c`
- `0x180061054`
- `0x1800610f0`
- `0x1800618b0`
- `0x180064228`
- `0x18006453c`
- `0x18007ca54`
- `0x18008a810`
- `0x180098078`

## string_xrefs

- `0x180062b9a`: `StringCompare`
- `0x180061a03`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180061a43`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180061aa4`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180061b09`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180063065`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x1800630ce`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180063166`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180063287`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180063c9e`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180063cc5`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180063e38`: `RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl`
- `0x180061a0a`: `%s: Unexpected tokentype '%d' as join attribute.`
- `0x180061c6b`: `,"KeySecurity":"`
- `0x18006276a`: `"ClientIdentity":{"Type":"sha256signed","Sid":"`
- `0x18006306c`: `%s: Added device token of type '%d' as join attribute.`
- `0x1800633ff`: `EscapeStringForJson`
- `0x180063cbe`: `EscapeStringForJson`
- `0x180063616`: `"ReturnClientSid":"`
- `0x180063a9e`: `"Extensions":{`
- `0x180063ca5`: `%s: VDI extensions[%lu] has empty key or value. Ignore it.`
- `0x180062e66`: `ReadBoolOption`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        unsigned __int16 *a14,
        unsigned int a15,
        unsigned __int16 *a16,
        unsigned __int16 *a17,
        unsigned __int16 *a18,
        unsigned __int16 *a19,
        unsigned __int16 *a20,
        unsigned __int16 *a21,
        unsigned __int16 *a22,
        __int64 a23,
        unsigned __int16 *a24,
        unsigned __int16 *a25,
        unsigned __int16 *a26,
        unsigned __int16 *a27,
        __int64 a28,
        void **a29)
{
  void *v32; // rsi
  void *v33; // r14
  int v34; // edi
  void *v35; // rbx
  unsigned __int64 v36; // r14
  unsigned __int64 v37; // rcx
  int v38; // eax
  const unsigned __int16 *v39; // r8
  unsigned __int64 v40; // r8
  unsigned __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // r9
  const unsigned __int16 *v44; // r8
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // r8
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // r8
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rcx
  unsigned __int64 v54; // rcx
  unsigned __int16 *v55; // rbx
  unsigned __int64 v56; // rcx
  unsigned __int64 v57; // r8
  unsigned __int64 v58; // rcx
  unsigned __int64 v59; // rcx
  unsigned __int16 *v60; // r12
  unsigned __int64 v61; // rcx
  unsigned __int16 *v62; // rbx
  int v63; // eax
  unsigned __int16 *v64; // r15
  unsigned __int64 v65; // rcx
  unsigned __int64 v66; // r8
  unsigned __int64 v67; // rcx
  unsigned __int64 v68; // rcx
  const unsigned __int16 *v69; // r9
  unsigned __int16 *v70; // rbx
  unsigned __int16 *v71; // r15
  unsigned __int64 v72; // rcx
  unsigned __int64 v73; // r8
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rcx
  unsigned __int64 v76; // rcx
  unsigned __int64 v77; // r8
  unsigned __int64 v78; // rcx
  unsigned __int64 v79; // rcx
  unsigned __int64 v80; // rcx
  unsigned __int64 v81; // r8
  unsigned __int64 v82; // rcx
  unsigned __int64 v83; // rcx
  unsigned __int16 *v84; // r15
  const unsigned __int16 *v85; // rcx
  unsigned __int16 *v86; // rcx
  const unsigned __int16 *v87; // r9
  unsigned __int64 v88; // r8
  unsigned __int64 v89; // rcx
  unsigned __int64 v90; // rcx
  unsigned __int64 v91; // rcx
  unsigned __int64 v92; // rcx
  unsigned __int64 v93; // rcx
  unsigned __int64 v94; // rcx
  unsigned __int64 v95; // r8
  unsigned __int64 v96; // rcx
  unsigned __int64 v97; // rcx
  unsigned __int64 v98; // rcx
  unsigned __int64 v99; // r8
  unsigned __int64 v100; // rcx
  unsigned __int64 v101; // rcx
  unsigned __int16 *v102; // rbx
  unsigned __int64 v103; // rcx
  unsigned __int64 v104; // r8
  unsigned __int64 v105; // rcx
  unsigned __int64 v106; // rcx
  unsigned __int64 v107; // rcx
  unsigned __int64 v108; // r8
  unsigned __int64 v109; // rcx
  unsigned __int64 v110; // rcx
  unsigned __int16 *v111; // rbx
  unsigned __int64 v112; // rcx
  unsigned __int64 v113; // r8
  unsigned __int64 v114; // rcx
  unsigned __int64 v115; // rcx
  unsigned __int64 v116; // r8
  unsigned __int64 v117; // rcx
  unsigned __int64 v118; // rcx
  unsigned __int64 v119; // rcx
  unsigned __int64 v120; // rcx
  unsigned __int64 v121; // r8
  unsigned __int64 v122; // rcx
  unsigned __int16 *v123; // rbx
  unsigned __int64 v124; // rcx
  unsigned __int64 v125; // r8
  unsigned __int64 v126; // rcx
  unsigned __int64 v127; // rcx
  unsigned __int16 *v128; // rbx
  unsigned __int64 v129; // rcx
  unsigned __int64 v130; // r8
  unsigned __int64 v131; // rcx
  unsigned __int64 v132; // rcx
  int v133; // r15d
  int v134; // eax
  const unsigned __int16 *v135; // rdx
  const WCHAR *v136; // r10
  int v137; // r13d
  int v138; // r12d
  unsigned __int64 v139; // rcx
  char v140; // bl
  unsigned __int64 v141; // rcx
  unsigned __int64 v142; // r8
  unsigned __int64 v143; // rcx
  unsigned __int64 v144; // rcx
  unsigned __int64 v145; // rcx
  unsigned __int64 v146; // rcx
  unsigned __int64 v147; // r8
  unsigned __int64 v148; // rcx
  unsigned __int64 v149; // rcx
  unsigned __int64 v150; // rcx
  int v151; // eax
  bool v152; // r12
  __int64 v153; // rdx
  bool v154; // r13
  unsigned __int64 v155; // rcx
  int v156; // r15d
  const unsigned __int16 *v157; // r9
  unsigned __int64 v158; // r8
  unsigned __int64 v159; // rcx
  unsigned __int64 v160; // r8
  unsigned __int64 v161; // rcx
  unsigned __int64 v162; // rcx
  unsigned int i; // ecx
  bool v164; // dl
  unsigned __int16 *v165; // rbx
  unsigned __int16 *v166; // rax
  unsigned __int16 *v167; // rax
  unsigned __int64 v168; // rcx
  int v169; // eax
  unsigned __int64 v170; // rcx
  unsigned __int64 v171; // r8
  unsigned __int64 v172; // rcx
  unsigned __int64 v173; // rcx
  unsigned __int64 v174; // rcx
  unsigned __int64 v175; // rcx
  unsigned __int16 *v176; // rbx
  unsigned __int64 v177; // rcx
  unsigned __int64 v178; // rcx
  int v179; // eax
  unsigned __int64 v180; // r8
  void *v181; // r12
  unsigned __int64 v182; // rcx
  unsigned __int16 *v183; // rbx
  unsigned __int64 v184; // rcx
  unsigned __int64 v185; // rcx
  unsigned __int64 v186; // r8
  unsigned __int64 v187; // rcx
  unsigned __int64 v188; // rcx
  unsigned __int16 *v189; // rbx
  unsigned __int64 v190; // rcx
  unsigned __int64 v191; // rcx
  unsigned __int64 v192; // r8
  unsigned __int64 v193; // rcx
  unsigned __int64 v194; // rcx
  unsigned __int64 v195; // rcx
  unsigned __int64 v196; // rcx
  int v197; // ebx
  __int64 v198; // r12
  unsigned __int64 v199; // rcx
  unsigned __int64 v200; // r8
  void *v201; // r12
  unsigned __int64 v202; // rcx
  const unsigned __int16 *v203; // r15
  unsigned __int64 v204; // rcx
  unsigned __int64 v205; // rcx
  const unsigned __int16 *v206; // r9
  unsigned __int64 v207; // r8
  unsigned __int64 v208; // rcx
  unsigned __int64 v209; // rcx
  unsigned __int64 v210; // rcx
  unsigned __int64 v211; // r8
  unsigned __int64 v212; // rcx
  unsigned __int64 v213; // rcx
  unsigned __int64 v214; // rcx
  unsigned int j; // ebx
  __int64 v216; // rdx
  __int16 v217; // r8
  unsigned __int64 v218; // rcx
  unsigned __int64 v219; // r8
  void *v220; // r12
  unsigned __int64 v221; // rcx
  unsigned __int64 v222; // rcx
  unsigned __int64 v223; // r8
  void *v224; // r12
  unsigned __int64 v225; // rcx
  unsigned __int64 v226; // rcx
  unsigned __int64 v227; // rcx
  unsigned __int64 v228; // rcx
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  void *lpMem; // [rsp+38h] [rbp-C8h] BYREF
  bool v232; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v233; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v234; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v235; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v236; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v237; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v238; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v239; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v240; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v241; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v242; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v243; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v244; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v245; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v246; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v247; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v248; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v249; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v250; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v251; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v252; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v253; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v254; // [rsp+F0h] [rbp-10h]
  void **v255; // [rsp+F8h] [rbp-8h]
  char v256[272]; // [rsp+100h] [rbp+0h] BYREF

  v242 = a4;
  v247 = a13;
  v248 = a12;
  v234 = a28;
  v244 = a5;
  v233 = a6;
  v245 = a7;
  v246 = a8;
  v243 = a9;
  v252 = a10;
  v251 = a11;
  v253 = a14;
  v235 = a16;
  v238 = a18;
  v239 = a19;
  v240 = a20;
  v254 = a21;
  v241 = a22;
  v250 = a24;
  v249 = a25;
  v236 = a26;
  v237 = a27;
  v255 = a29;
  v32 = 0;
  v33 = 0;
  lpMem = 0;
  *a29 = 0;
  if ( a15 - 1 > 1 )
  {
    Logger::TraceError(
      L"%s: Unexpected tokentype '%d' as join attribute.",
      L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
      a15);
    v34 = -2147024809;
    goto LABEL_547;
  }
  v35 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
  Block = v35;
  if ( !v35 )
  {
    v34 = -2147024882;
    Logger::TraceCritical(
      L"%s: Out of memory. Allocation failed.",
      L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl");
    goto LABEL_545;
  }
  *(_WORD *)Block = 0;
  v36 = -1;
  v37 = -1;
  do
    ++v37;
  while ( *((_WORD *)v35 + v37) );
  v38 = ConcatenateStringW(
          v37,
          (const unsigned __int16 *)Block,
          0x2Fu,
          L"{\"CertificateRequest\":{\"Type\":\"pkcs10\",\"Data\":\"",
          (unsigned __int16 **)&Block);
  v34 = v38;
  if ( v38 < 0 )
  {
    v39 = L"ConcatenateStringW";
LABEL_9:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
      v39,
      (unsigned int)v38);
LABEL_543:
    v32 = v35;
    goto LABEL_544;
  }
  operator delete(v35);
  v32 = Block;
  v40 = -1;
  do
    ++v40;
  while ( a1[v40] );
  v41 = -1;
  do
    ++v41;
  while ( *((_WORD *)Block + v41) );
  v42 = ConcatenateStringW(v41, (const unsigned __int16 *)Block, v40, a1, (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v45 = -1;
  do
    ++v45;
  while ( *((_WORD *)Block + v45) );
  v42 = ConcatenateStringW(v45, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  if ( !(unsigned int)IsEmptyString(a2) )
  {
    v32 = Block;
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)Block + v46) );
    v42 = ConcatenateStringW(
            v46,
            (const unsigned __int16 *)Block,
            0xCu,
            L",\"KeyType\":\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v47 = -1;
    do
      ++v47;
    while ( a2[v47] );
    v48 = -1;
    do
      ++v48;
    while ( *((_WORD *)Block + v48) );
    v42 = ConcatenateStringW(v48, (const unsigned __int16 *)Block, v47, a2, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v49 = -1;
    do
      ++v49;
    while ( *((_WORD *)Block + v49) );
    v42 = ConcatenateStringW(v49, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  if ( !(unsigned int)IsEmptyString(a3) )
  {
    v32 = Block;
    v50 = -1;
    do
      ++v50;
    while ( *((_WORD *)Block + v50) );
    v42 = ConcatenateStringW(
            v50,
            (const unsigned __int16 *)Block,
            0x10u,
            L",\"KeySecurity\":\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v51 = -1;
    do
      ++v51;
    while ( a3[v51] );
    v52 = -1;
    do
      ++v52;
    while ( *((_WORD *)Block + v52) );
    v42 = ConcatenateStringW(v52, (const unsigned __int16 *)Block, v51, a3, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v53 = -1;
    do
      ++v53;
    while ( *((_WORD *)Block + v53) );
    v42 = ConcatenateStringW(v53, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v32 = Block;
  v54 = -1;
  do
    ++v54;
  while ( *((_WORD *)Block + v54) );
  v42 = ConcatenateStringW(v54, (const unsigned __int16 *)Block, 2u, L"},", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v55 = v242;
  if ( !(unsigned int)IsEmptyString(v242) )
  {
    v32 = Block;
    v56 = -1;
    do
      ++v56;
    while ( *((_WORD *)Block + v56) );
    v42 = ConcatenateStringW(
            v56,
            (const unsigned __int16 *)Block,
            0x30u,
            L"\"RaCertificateRequest\":{\"Type\":\"pkcs10\",\"Data\":\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v57 = -1;
    do
      ++v57;
    while ( v55[v57] );
    v58 = -1;
    do
      ++v58;
    while ( *((_WORD *)Block + v58) );
    v42 = ConcatenateStringW(v58, (const unsigned __int16 *)Block, v57, v55, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v59 = -1;
    do
      ++v59;
    while ( *((_WORD *)Block + v59) );
    v42 = ConcatenateStringW(v59, (const unsigned __int16 *)Block, 3u, L"\"},", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v60 = v243;
  if ( !(unsigned int)IsEmptyString(v243) )
  {
    v32 = Block;
    v61 = -1;
    do
      ++v61;
    while ( *((_WORD *)Block + v61) );
    v42 = ConcatenateStringW(
            v61,
            (const unsigned __int16 *)Block,
            0x14u,
            L"\"ServerAdJoinData\":{",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v62 = v244;
  v63 = IsEmptyString(v244);
  v64 = v233;
  if ( !v63 || !(unsigned int)IsEmptyString(v233) )
  {
    if ( (unsigned int)IsEmptyString(v62) )
    {
      if ( (unsigned int)IsEmptyString(v64) )
      {
LABEL_84:
        v70 = v245;
        if ( !(unsigned int)IsEmptyString(v245) )
        {
          v71 = v246;
          if ( !(unsigned int)IsEmptyString(v246) )
          {
            v32 = Block;
            v72 = -1;
            do
              ++v72;
            while ( *((_WORD *)Block + v72) );
            v42 = ConcatenateStringW(
                    v72,
                    (const unsigned __int16 *)Block,
                    0x12u,
                    L"\"AikCertificate\":\"",
                    (unsigned __int16 **)&Block);
            v34 = v42;
            if ( v42 < 0 )
              goto LABEL_15;
            operator delete(v32);
            v32 = Block;
            v73 = -1;
            do
              ++v73;
            while ( v70[v73] );
            v74 = -1;
            do
              ++v74;
            while ( *((_WORD *)Block + v74) );
            v42 = ConcatenateStringW(v74, (const unsigned __int16 *)Block, v73, v70, (unsigned __int16 **)&Block);
            v34 = v42;
            if ( v42 < 0 )
              goto LABEL_15;
            operator delete(v32);
            v32 = Block;
            v75 = -1;
            do
              ++v75;
            while ( *((_WORD *)Block + v75) );
            v42 = ConcatenateStringW(v75, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
            v34 = v42;
            if ( v42 < 0 )
              goto LABEL_15;
            operator delete(v32);
            v32 = Block;
            v76 = -1;
            do
              ++v76;
            while ( *((_WORD *)Block + v76) );
            v42 = ConcatenateStringW(
                    v76,
                    (const unsigned __int16 *)Block,
                    0x13u,
                    L"\"AttestationData\":\"",
                    (unsigned __int16 **)&Block);
            v34 = v42;
            if ( v42 < 0 )
              goto LABEL_15;
            operator delete(v32);
            v32 = Block;
            v77 = -1;
            do
              ++v77;
            while ( v71[v77] );
            v78 = -1;
            do
              ++v78;
            while ( *((_WORD *)Block + v78) );
            v42 = ConcatenateStringW(v78, (const unsigned __int16 *)Block, v77, v71, (unsigned __int16 **)&Block);
            v34 = v42;
            if ( v42 < 0 )
              goto LABEL_15;
            operator delete(v32);
            v32 = Block;
            v79 = -1;
            do
              ++v79;
            while ( *((_WORD *)Block + v79) );
            v42 = ConcatenateStringW(v79, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
            v34 = v42;
            if ( v42 < 0 )
              goto LABEL_15;
            operator delete(v32);
          }
        }
        goto LABEL_121;
      }
      v32 = Block;
      v80 = -1;
      do
        ++v80;
      while ( *((_WORD *)Block + v80) );
      v42 = ConcatenateStringW(
              v80,
              (const unsigned __int16 *)Block,
              0xEu,
              L"\"DeviceKeys\":[",
              (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v81 = -1;
      do
        ++v81;
      while ( v64[v81] );
      v82 = -1;
      do
        ++v82;
      while ( *((_WORD *)Block + v82) );
      v42 = ConcatenateStringW(v82, (const unsigned __int16 *)Block, v81, v64, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v68 = -1;
      do
        ++v68;
      while ( *((_WORD *)Block + v68) );
      v69 = L"],";
    }
    else
    {
      v32 = Block;
      v65 = -1;
      do
        ++v65;
      while ( *((_WORD *)Block + v65) );
      v42 = ConcatenateStringW(
              v65,
              (const unsigned __int16 *)Block,
              0x10u,
              L"\"TransportKey\":\"",
              (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v66 = -1;
      do
        ++v66;
      while ( v62[v66] );
      v67 = -1;
      do
        ++v67;
      while ( *((_WORD *)Block + v67) );
      v42 = ConcatenateStringW(v67, (const unsigned __int16 *)Block, v66, v62, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v68 = -1;
      do
        ++v68;
      while ( *((_WORD *)Block + v68) );
      v69 = L"\",";
    }
    v42 = ConcatenateStringW(v68, (const unsigned __int16 *)v32, 2u, v69, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    goto LABEL_84;
  }
LABEL_121:
  v32 = Block;
  v83 = -1;
  do
    ++v83;
  while ( *((_WORD *)Block + v83) );
  v42 = ConcatenateStringW(
          v83,
          (const unsigned __int16 *)Block,
          0x10u,
          L"\"TargetDomain\":\"",
          (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  IsEmptyString(v247);
  v84 = v248;
  if ( (unsigned int)IsEmptyString(v85) )
    v86 = v84;
  v88 = -1;
  do
    ++v88;
  while ( v86[v88] );
  v89 = -1;
  do
    ++v89;
  while ( *((_WORD *)v32 + v89) );
  v42 = ConcatenateStringW(v89, (const unsigned __int16 *)v32, v88, v87, (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v90 = -1;
  do
    ++v90;
  while ( *((_WORD *)Block + v90) );
  v42 = ConcatenateStringW(v90, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v91 = -1;
  do
    ++v91;
  while ( *((_WORD *)Block + v91) );
  v42 = ConcatenateStringW(
          v91,
          (const unsigned __int16 *)Block,
          0xEu,
          L"\"DeviceType\":\"",
          (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v92 = -1;
  do
    ++v92;
  while ( *((_WORD *)Block + v92) );
  v42 = ConcatenateStringW(v92, (const unsigned __int16 *)Block, 7u, L"Windows", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v93 = -1;
  do
    ++v93;
  while ( *((_WORD *)Block + v93) );
  v42 = ConcatenateStringW(v93, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v94 = -1;
  do
    ++v94;
  while ( *((_WORD *)Block + v94) );
  v42 = ConcatenateStringW(v94, (const unsigned __int16 *)Block, 0xDu, L"\"OSVersion\":\"", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v95 = -1;
  do
    ++v95;
  while ( v249[v95] );
  v96 = -1;
  do
    ++v96;
  while ( *((_WORD *)Block + v96) );
  v42 = ConcatenateStringW(v96, (const unsigned __int16 *)Block, v95, v249, (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v97 = -1;
  do
    ++v97;
  while ( *((_WORD *)Block + v97) );
  v42 = ConcatenateStringW(v97, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v98 = -1;
  do
    ++v98;
  while ( *((_WORD *)Block + v98) );
  v42 = ConcatenateStringW(
          v98,
          (const unsigned __int16 *)Block,
          0x15u,
          L"\"DeviceDisplayName\":\"",
          (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v99 = -1;
  do
    ++v99;
  while ( v250[v99] );
  v100 = -1;
  do
    ++v100;
  while ( *((_WORD *)Block + v100) );
  v42 = ConcatenateStringW(v100, (const unsigned __int16 *)Block, v99, v250, (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v101 = -1;
  do
    ++v101;
  while ( *((_WORD *)Block + v101) );
  v42 = ConcatenateStringW(v101, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  if ( !(unsigned int)IsEmptyString(v60) )
  {
    v102 = v251;
    if ( !(unsigned int)IsEmptyString(v251) )
    {
      v32 = Block;
      v103 = -1;
      do
        ++v103;
      while ( *((_WORD *)Block + v103) );
      v42 = ConcatenateStringW(
              v103,
              (const unsigned __int16 *)Block,
              0x1Au,
              L"\"SourceDomainController\":\"",
              (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v104 = -1;
      do
        ++v104;
      while ( v102[v104] );
      v105 = -1;
      do
        ++v105;
      while ( *((_WORD *)Block + v105) );
      v42 = ConcatenateStringW(v105, (const unsigned __int16 *)Block, v104, v102, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v106 = -1;
      do
        ++v106;
      while ( *((_WORD *)Block + v106) );
      v42 = ConcatenateStringW(v106, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    if ( !(unsigned int)IsEmptyString(v84) )
    {
      v32 = Block;
      v107 = -1;
      do
        ++v107;
      while ( *((_WORD *)Block + v107) );
      v42 = ConcatenateStringW(
              v107,
              (const unsigned __int16 *)Block,
              0x12u,
              L"\"TargetDomainId\":\"",
              (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v108 = -1;
      do
        ++v108;
      while ( v84[v108] );
      v109 = -1;
      do
        ++v109;
      while ( *((_WORD *)Block + v109) );
      v42 = ConcatenateStringW(v109, (const unsigned __int16 *)Block, v108, v84, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v110 = -1;
      do
        ++v110;
      while ( *((_WORD *)Block + v110) );
      v42 = ConcatenateStringW(v110, (const unsigned __int16 *)Block, 2u, L"\",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v111 = v252;
    if ( !(unsigned int)IsEmptyString(v252) && !(unsigned int)IsEmptyString(v60) )
    {
      v32 = Block;
      v112 = -1;
      do
        ++v112;
      while ( *((_WORD *)Block + v112) );
      v42 = ConcatenateStringW(
              v112,
              (const unsigned __int16 *)Block,
              0x2Fu,
              L"\"ClientIdentity\":{\"Type\":\"sha256signed\",\"Sid\":\"",
              (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v113 = -1;
      do
        ++v113;
      while ( v111[v113] );
      v114 = -1;
      do
        ++v114;
      while ( *((_WORD *)Block + v114) );
      v42 = ConcatenateStringW(v114, (const unsigned __int16 *)Block, v113, v111, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v115 = -1;
      do
        ++v115;
      while ( *((_WORD *)Block + v115) );
      v42 = ConcatenateStringW(
              v115,
              (const unsigned __int16 *)Block,
              0x10u,
              L"\",\"SignedBlob\":\"",
              (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v116 = -1;
      do
        ++v116;
      while ( v60[v116] );
      v117 = -1;
      do
        ++v117;
      while ( *((_WORD *)Block + v117) );
      v42 = ConcatenateStringW(v117, (const unsigned __int16 *)Block, v116, v60, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v118 = -1;
      do
        ++v118;
      while ( *((_WORD *)Block + v118) );
      v42 = ConcatenateStringW(v118, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
  }
  if ( !(unsigned int)IsEmptyString(v60) )
  {
    v32 = Block;
    v119 = -1;
    do
      ++v119;
    while ( *((_WORD *)Block + v119) );
    v42 = ConcatenateStringW(v119, (const unsigned __int16 *)Block, 3u, L"}},", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v32 = Block;
  v120 = -1;
  do
    ++v120;
  while ( *((_WORD *)Block + v120) );
  v42 = ConcatenateStringW(v120, (const unsigned __int16 *)Block, 0xBu, L"\"JoinType\":", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v32 = Block;
  v121 = -1;
  do
    ++v121;
  while ( v253[v121] );
  v122 = -1;
  do
    ++v122;
  while ( *((_WORD *)Block + v122) );
  v42 = ConcatenateStringW(v122, (const unsigned __int16 *)Block, v121, v253, (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 < 0 )
    goto LABEL_15;
  operator delete(v32);
  v123 = v254;
  if ( !(unsigned int)IsEmptyString(v254) )
  {
    v32 = Block;
    v124 = -1;
    do
      ++v124;
    while ( *((_WORD *)Block + v124) );
    v42 = ConcatenateStringW(
            v124,
            (const unsigned __int16 *)Block,
            0x11u,
            L",\"RAAccountUpn\":\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v125 = -1;
    do
      ++v125;
    while ( v123[v125] );
    v126 = -1;
    do
      ++v126;
    while ( *((_WORD *)Block + v126) );
    v42 = ConcatenateStringW(v126, (const unsigned __int16 *)Block, v125, v123, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v127 = -1;
    do
      ++v127;
    while ( *((_WORD *)Block + v127) );
    v42 = ConcatenateStringW(v127, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v128 = v241;
  if ( !(unsigned int)IsEmptyString(v241) )
  {
    v32 = Block;
    v129 = -1;
    do
      ++v129;
    while ( *((_WORD *)Block + v129) );
    v42 = ConcatenateStringW(
            v129,
            (const unsigned __int16 *)Block,
            0x13u,
            L",\"RAFriendlyName\":\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v130 = -1;
    do
      ++v130;
    while ( v128[v130] );
    v131 = -1;
    do
      ++v131;
    while ( *((_WORD *)Block + v131) );
    v42 = ConcatenateStringW(v131, (const unsigned __int16 *)Block, v130, v128, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v132 = -1;
    do
      ++v132;
    while ( *((_WORD *)Block + v132) );
    v42 = ConcatenateStringW(v132, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v133 = IsEmptyString(v236);
  v134 = IsEmptyString(v237);
  v137 = v134;
  if ( !v133 || !v134 )
  {
    v138 = 0;
    LODWORD(v233) = 0;
    if ( !v133 && !v134 )
    {
      v38 = StringCompare(v136, v135, 0x30001u, (int *)&v233);
      v34 = v38;
      v35 = 0;
      if ( v38 < 0 )
      {
        v39 = L"StringCompare";
        goto LABEL_9;
      }
      v138 = (int)v233;
    }
    v32 = Block;
    v139 = -1;
    do
      ++v139;
    while ( *((_WORD *)Block + v139) );
    v34 = ConcatenateStringW(
            v139,
            (const unsigned __int16 *)Block,
            0xEu,
            L",\"Hostnames\":[",
            (unsigned __int16 **)&Block);
    if ( v34 < 0 )
    {
      v43 = (unsigned int)v34;
      goto LABEL_16;
    }
    v140 = 0;
    operator delete(v32);
    if ( !v133 )
    {
      v32 = Block;
      v141 = -1;
      do
        ++v141;
      while ( *((_WORD *)Block + v141) );
      v140 = 1;
      v42 = ConcatenateStringW(v141, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v142 = -1;
      do
        ++v142;
      while ( v236[v142] );
      v143 = -1;
      do
        ++v143;
      while ( *((_WORD *)Block + v143) );
      v42 = ConcatenateStringW(v143, (const unsigned __int16 *)Block, v142, v236, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v144 = -1;
      do
        ++v144;
      while ( *((_WORD *)Block + v144) );
      v42 = ConcatenateStringW(v144, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    if ( !v137 && !v138 )
    {
      v32 = 0;
      if ( v140 )
        v32 = Block;
      v145 = -1;
      do
        ++v145;
      while ( *((_WORD *)Block + v145) );
      v42 = ConcatenateStringW(v145, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v146 = -1;
      do
        ++v146;
      while ( *((_WORD *)Block + v146) );
      v42 = ConcatenateStringW(v146, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v147 = -1;
      do
        ++v147;
      while ( v237[v147] );
      v148 = -1;
      do
        ++v148;
      while ( *((_WORD *)Block + v148) );
      v42 = ConcatenateStringW(v148, (const unsigned __int16 *)Block, v147, v237, (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
      v32 = Block;
      v149 = -1;
      do
        ++v149;
      while ( *((_WORD *)Block + v149) );
      v42 = ConcatenateStringW(v149, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v150 = -1;
    do
      ++v150;
    while ( *((_WORD *)Block + v150) );
    v42 = ConcatenateStringW(v150, (const unsigned __int16 *)Block, 1u, L"]", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v232 = 1;
  v151 = ReadBoolOption(L"DeviceReuse", &v232);
  if ( v151 < 0 )
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"IsDeviceReuseEnabled",
      L"ReadBoolOption",
      (unsigned int)v151);
  v152 = v232;
  v154 = !(unsigned int)IsEmptyString(*(const unsigned __int16 **)v234)
      || *(_DWORD *)(v153 + 8)
      || *(_DWORD *)(v153 + 12)
      || *(_DWORD *)(v153 + 16) && *(_QWORD *)(v153 + 24);
  if ( !v152
    && !v154
    && (unsigned int)IsEmptyString(v235)
    && (unsigned int)IsEmptyString(a17)
    && (unsigned int)IsEmptyString(v238)
    && (unsigned int)IsEmptyString(v239)
    && (unsigned int)IsEmptyString(v240) )
  {
    v232 = 0;
  }
  else
  {
    v32 = Block;
    v155 = -1;
    do
      ++v155;
    while ( *((_WORD *)Block + v155) );
    v42 = ConcatenateStringW(
            v155,
            (const unsigned __int16 *)Block,
            0xFu,
            L",\"attributes\":{",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    v232 = 1;
    operator delete(v32);
  }
  v156 = 0;
  if ( !(unsigned int)IsEmptyString(v235) )
  {
    v157 = L"\"DDID\":\"";
    if ( a15 != 2 )
      v157 = L"\"MSA-DDID\":\"";
    v32 = Block;
    v158 = -1;
    do
      ++v158;
    while ( v157[v158] );
    v159 = -1;
    do
      ++v159;
    while ( *((_WORD *)Block + v159) );
    v42 = ConcatenateStringW(v159, (const unsigned __int16 *)Block, v158, v157, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v160 = -1;
    do
      ++v160;
    while ( v235[v160] );
    v161 = -1;
    do
      ++v161;
    while ( *((_WORD *)Block + v161) );
    v42 = ConcatenateStringW(v161, (const unsigned __int16 *)Block, v160, v235, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v162 = -1;
    do
      ++v162;
    while ( *((_WORD *)Block + v162) );
    v42 = ConcatenateStringW(v162, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v156 = 1;
    Logger::TraceInformation(
      L"%s: Added device token of type '%d' as join attribute.",
      L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
      a15);
  }
  if ( !(unsigned int)IsEmptyString(a17) )
  {
    for ( i = 0; (int)i < 128; ++i )
    {
      v164 = i;
      if ( !a17[i] )
        break;
      v256[i] = a17[i];
    }
    if ( i >= 0x81uLL )
      _report_rangecheckfailure();
    v256[i] = 0;
    v165 = (unsigned __int16 *)TraceLoggingCorrelationVector::Extend(v256, v164);
    v233 = v165;
    if ( v165 )
      goto LABEL_348;
    Logger::TraceInformation(
      L"%s: Supplied correlation vector did not validate. Seeding a new one.",
      L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl");
    v166 = (unsigned __int16 *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v241 = v166;
    if ( v166 )
    {
      v167 = (unsigned __int16 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v166);
      v165 = v167;
      v233 = v167;
    }
    else
    {
      v167 = 0;
      v165 = 0;
      v233 = 0;
    }
    if ( v167 )
    {
LABEL_348:
      if ( v156 )
      {
        v32 = Block;
        v168 = -1;
        do
          ++v168;
        while ( *((_WORD *)Block + v168) );
        v169 = ConcatenateStringW(v168, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
        v34 = v169;
        if ( v169 < 0 )
          goto LABEL_352;
        operator delete(v32);
      }
      memset_0(v256, 0, 0x102u);
      TraceLoggingCorrelationVector::IncrementW((TraceLoggingCorrelationVector *)v165, (unsigned __int16 *)v256);
      v32 = Block;
      v170 = -1;
      do
        ++v170;
      while ( *((_WORD *)Block + v170) );
      v169 = ConcatenateStringW(v170, (const unsigned __int16 *)Block, 9u, L"\"MS-CV\":\"", (unsigned __int16 **)&Block);
      v34 = v169;
      if ( v169 < 0 )
        goto LABEL_352;
      operator delete(v32);
      v32 = Block;
      v171 = -1;
      do
        ++v171;
      while ( *(_WORD *)&v256[2 * v171] );
      v172 = -1;
      do
        ++v172;
      while ( *((_WORD *)Block + v172) );
      v169 = ConcatenateStringW(
               v172,
               (const unsigned __int16 *)Block,
               v171,
               (const unsigned __int16 *)v256,
               (unsigned __int16 **)&Block);
      v34 = v169;
      if ( v169 < 0 )
        goto LABEL_352;
      operator delete(v32);
      v32 = Block;
      v173 = -1;
      do
        ++v173;
      while ( *((_WORD *)Block + v173) );
      v169 = ConcatenateStringW(v173, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
      v34 = v169;
      if ( v169 < 0 )
      {
LABEL_352:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
          L"ConcatenateStringW",
          (unsigned int)v169);
        std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>((void **)&v233);
        goto LABEL_544;
      }
      operator delete(v32);
      ++v156;
      Logger::TraceInformation(
        L"%s: Added correlation vector '%ls' as join attribute.",
        L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
        v256);
    }
    std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>((void **)&v233);
  }
  if ( v152 )
  {
    if ( v156 )
    {
      v32 = Block;
      v174 = -1;
      do
        ++v174;
      while ( *((_WORD *)Block + v174) );
      v42 = ConcatenateStringW(v174, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v175 = -1;
    do
      ++v175;
    while ( *((_WORD *)Block + v175) );
    v42 = ConcatenateStringW(
            v175,
            (const unsigned __int16 *)Block,
            0x14u,
            L"\"ReuseDevice\":\"true\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    ++v156;
  }
  v176 = v238;
  if ( !(unsigned int)IsEmptyString(v238) )
  {
    if ( v156 )
    {
      v32 = Block;
      v177 = -1;
      do
        ++v177;
      while ( *((_WORD *)Block + v177) );
      v42 = ConcatenateStringW(v177, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v178 = -1;
    do
      ++v178;
    while ( *((_WORD *)Block + v178) );
    v42 = ConcatenateStringW(
            v178,
            (const unsigned __int16 *)Block,
            0x12u,
            L"\"AzureResourceId\":",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v179 = EscapeStringForJson(v176, 1, (unsigned __int16 **)&lpMem);
    v34 = v179;
    if ( v179 < 0 )
      goto LABEL_387;
    v32 = Block;
    v180 = -1;
    v181 = lpMem;
    do
      ++v180;
    while ( *((_WORD *)lpMem + v180) );
    v182 = -1;
    do
      ++v182;
    while ( *((_WORD *)Block + v182) );
    v42 = ConcatenateStringW(
            v182,
            (const unsigned __int16 *)Block,
            v180,
            (const unsigned __int16 *)lpMem,
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    SafeFree(v181);
    lpMem = 0;
    ++v156;
  }
  v183 = v239;
  if ( !(unsigned int)IsEmptyString(v239) )
  {
    if ( v156 )
    {
      v32 = Block;
      v184 = -1;
      do
        ++v184;
      while ( *((_WORD *)Block + v184) );
      v42 = ConcatenateStringW(v184, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v185 = -1;
    do
      ++v185;
    while ( *((_WORD *)Block + v185) );
    v42 = ConcatenateStringW(
            v185,
            (const unsigned __int16 *)Block,
            0x10u,
            L"\"InferredAuth\":\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v186 = -1;
    do
      ++v186;
    while ( v183[v186] );
    v187 = -1;
    do
      ++v187;
    while ( *((_WORD *)Block + v187) );
    v42 = ConcatenateStringW(v187, (const unsigned __int16 *)Block, v186, v183, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v188 = -1;
    do
      ++v188;
    while ( *((_WORD *)Block + v188) );
    v42 = ConcatenateStringW(v188, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    ++v156;
  }
  v189 = v240;
  if ( !(unsigned int)IsEmptyString(v240) )
  {
    if ( v156 )
    {
      v32 = Block;
      v190 = -1;
      do
        ++v190;
      while ( *((_WORD *)Block + v190) );
      v42 = ConcatenateStringW(v190, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v191 = -1;
    do
      ++v191;
    while ( *((_WORD *)Block + v191) );
    v42 = ConcatenateStringW(
            v191,
            (const unsigned __int16 *)Block,
            0x13u,
            L"\"ReturnClientSid\":\"",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v192 = -1;
    do
      ++v192;
    while ( v189[v192] );
    v193 = -1;
    do
      ++v193;
    while ( *((_WORD *)Block + v193) );
    v42 = ConcatenateStringW(v193, (const unsigned __int16 *)Block, v192, v189, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v194 = -1;
    do
      ++v194;
    while ( *((_WORD *)Block + v194) );
    v42 = ConcatenateStringW(v194, (const unsigned __int16 *)Block, 1u, L"\"", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    ++v156;
  }
  if ( v154 )
  {
    if ( v156 )
    {
      v32 = Block;
      v195 = -1;
      do
        ++v195;
      while ( *((_WORD *)Block + v195) );
      v42 = ConcatenateStringW(v195, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v196 = -1;
    do
      ++v196;
    while ( *((_WORD *)Block + v196) );
    v42 = ConcatenateStringW(
            v196,
            (const unsigned __int16 *)Block,
            0x12u,
            L"\"VirtualDesktop\":{",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  v197 = 0;
  v198 = v234;
  if ( !(unsigned int)IsEmptyString(*(const unsigned __int16 **)v234) )
  {
    v32 = Block;
    v199 = -1;
    do
      ++v199;
    while ( *((_WORD *)Block + v199) );
    v42 = ConcatenateStringW(v199, (const unsigned __int16 *)Block, 0xBu, L"\"Provider\":", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v179 = EscapeStringForJson(*(const unsigned __int16 **)v198, 1, (unsigned __int16 **)&lpMem);
    v34 = v179;
    if ( v179 < 0 )
    {
LABEL_387:
      v32 = 0;
LABEL_388:
      v43 = (unsigned int)v179;
      v44 = L"EscapeStringForJson";
      goto LABEL_17;
    }
    v32 = Block;
    v200 = -1;
    v201 = lpMem;
    do
      ++v200;
    while ( *((_WORD *)lpMem + v200) );
    v202 = -1;
    do
      ++v202;
    while ( *((_WORD *)Block + v202) );
    v42 = ConcatenateStringW(
            v202,
            (const unsigned __int16 *)Block,
            v200,
            (const unsigned __int16 *)lpMem,
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    SafeFree(v201);
    lpMem = 0;
    v197 = 1;
    v198 = v234;
  }
  v203 = L"true";
  if ( *(_DWORD *)(v198 + 8) )
  {
    if ( v197 )
    {
      v32 = Block;
      v204 = -1;
      do
        ++v204;
      while ( *((_WORD *)Block + v204) );
      v42 = ConcatenateStringW(v204, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v205 = -1;
    do
      ++v205;
    while ( *((_WORD *)Block + v205) );
    v42 = ConcatenateStringW(
            v205,
            (const unsigned __int16 *)Block,
            0xDu,
            L"\"Persistent\":",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    v206 = L"true";
    if ( *(_DWORD *)(v198 + 8) != 2 )
      v206 = L"false";
    v207 = -1;
    do
      ++v207;
    while ( v206[v207] );
    v208 = -1;
    do
      ++v208;
    while ( *((_WORD *)Block + v208) );
    v42 = ConcatenateStringW(v208, (const unsigned __int16 *)Block, v207, v206, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    ++v197;
  }
  if ( *(_DWORD *)(v198 + 12) )
  {
    if ( v197 )
    {
      v32 = Block;
      v209 = -1;
      do
        ++v209;
      while ( *((_WORD *)Block + v209) );
      v42 = ConcatenateStringW(v209, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v210 = -1;
    do
      ++v210;
    while ( *((_WORD *)Block + v210) );
    v42 = ConcatenateStringW(
            v210,
            (const unsigned __int16 *)Block,
            0xCu,
            L"\"MultiUser\":",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    v32 = Block;
    if ( *(_DWORD *)(v198 + 12) != 2 )
      v203 = L"false";
    v211 = -1;
    do
      ++v211;
    while ( v203[v211] );
    v212 = -1;
    do
      ++v212;
    while ( *((_WORD *)Block + v212) );
    v42 = ConcatenateStringW(v212, (const unsigned __int16 *)Block, v211, v203, (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    ++v197;
  }
  if ( *(_DWORD *)(v198 + 16) && *(_QWORD *)(v198 + 24) )
  {
    if ( v197 )
    {
      v32 = Block;
      v213 = -1;
      do
        ++v213;
      while ( *((_WORD *)Block + v213) );
      v42 = ConcatenateStringW(v213, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
      v34 = v42;
      if ( v42 < 0 )
        goto LABEL_15;
      operator delete(v32);
    }
    v32 = Block;
    v214 = -1;
    do
      ++v214;
    while ( *((_WORD *)Block + v214) );
    v42 = ConcatenateStringW(
            v214,
            (const unsigned __int16 *)Block,
            0xEu,
            L"\"Extensions\":{",
            (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
    for ( j = 0; j < *(_DWORD *)(v198 + 16); ++j )
    {
      if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(*(_QWORD *)(v198 + 24) + 16LL * j))
        || (unsigned int)IsEmptyString(*(const unsigned __int16 **)(v216 + 16LL * j + 8)) )
      {
        Logger::TraceWarning(
          (wchar_t *)L"%s: VDI extensions[%lu] has empty key or value. Ignore it.",
          L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
          j);
      }
      else
      {
        if ( j )
        {
          v32 = Block;
          v218 = -1;
          do
            ++v218;
          while ( *((_WORD *)Block + v218) != v217 );
          v42 = ConcatenateStringW(v218, (const unsigned __int16 *)Block, 1u, L",", (unsigned __int16 **)&Block);
          v34 = v42;
          if ( v42 < 0 )
            goto LABEL_15;
          operator delete(v32);
        }
        v34 = EscapeStringForJson(
                *(const unsigned __int16 **)(*(_QWORD *)(v198 + 24) + 16LL * j),
                1,
                (unsigned __int16 **)&lpMem);
        if ( v34 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
            L"EscapeStringForJson",
            (unsigned int)v34);
          v32 = 0;
          goto LABEL_544;
        }
        v32 = Block;
        v219 = -1;
        v220 = lpMem;
        do
          ++v219;
        while ( *((_WORD *)lpMem + v219) );
        v221 = -1;
        do
          ++v221;
        while ( *((_WORD *)Block + v221) );
        v42 = ConcatenateStringW(
                v221,
                (const unsigned __int16 *)Block,
                v219,
                (const unsigned __int16 *)lpMem,
                (unsigned __int16 **)&Block);
        v34 = v42;
        if ( v42 < 0 )
          goto LABEL_15;
        operator delete(v32);
        SafeFree(v220);
        lpMem = 0;
        v32 = Block;
        v222 = -1;
        do
          ++v222;
        while ( *((_WORD *)Block + v222) );
        v42 = ConcatenateStringW(v222, (const unsigned __int16 *)Block, 1u, L":", (unsigned __int16 **)&Block);
        v34 = v42;
        if ( v42 < 0 )
          goto LABEL_15;
        operator delete(v32);
        v32 = 0;
        v179 = EscapeStringForJson(
                 *(const unsigned __int16 **)(*(_QWORD *)(v234 + 24) + 16LL * j + 8),
                 1,
                 (unsigned __int16 **)&lpMem);
        v34 = v179;
        if ( v179 < 0 )
          goto LABEL_388;
        v32 = Block;
        v223 = -1;
        v224 = lpMem;
        do
          ++v223;
        while ( *((_WORD *)lpMem + v223) );
        v225 = -1;
        do
          ++v225;
        while ( *((_WORD *)Block + v225) );
        v42 = ConcatenateStringW(
                v225,
                (const unsigned __int16 *)Block,
                v223,
                (const unsigned __int16 *)lpMem,
                (unsigned __int16 **)&Block);
        v34 = v42;
        if ( v42 < 0 )
          goto LABEL_15;
        operator delete(v32);
        SafeFree(v224);
        lpMem = 0;
        v198 = v234;
      }
    }
    v32 = Block;
    v226 = -1;
    do
      ++v226;
    while ( *((_WORD *)Block + v226) );
    v42 = ConcatenateStringW(v226, (const unsigned __int16 *)Block, 1u, L"}", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  if ( v154 )
  {
    v32 = Block;
    v227 = -1;
    do
      ++v227;
    while ( *((_WORD *)Block + v227) );
    v42 = ConcatenateStringW(v227, (const unsigned __int16 *)Block, 1u, L"}", (unsigned __int16 **)&Block);
    v34 = v42;
    if ( v42 < 0 )
      goto LABEL_15;
    operator delete(v32);
  }
  if ( !v232 )
  {
LABEL_539:
    v32 = Block;
    do
      ++v36;
    while ( *((_WORD *)Block + v36) );
    v42 = ConcatenateStringW(v36, (const unsigned __int16 *)Block, 1u, L"}", (unsigned __int16 **)&Block);
    v34 = v42;
    v35 = 0;
    if ( v42 >= 0 )
    {
      operator delete(v32);
      *v255 = Block;
      Block = 0;
      goto LABEL_543;
    }
    goto LABEL_15;
  }
  v32 = Block;
  v228 = -1;
  do
    ++v228;
  while ( *((_WORD *)Block + v228) );
  v42 = ConcatenateStringW(v228, (const unsigned __int16 *)Block, 1u, L"}", (unsigned __int16 **)&Block);
  v34 = v42;
  if ( v42 >= 0 )
  {
    operator delete(v32);
    goto LABEL_539;
  }
LABEL_15:
  v43 = (unsigned int)v42;
LABEL_16:
  v44 = L"ConcatenateStringW";
LABEL_17:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
    v44,
    v43);
LABEL_544:
  v33 = lpMem;
LABEL_545:
  if ( Block != v32 )
    operator delete(Block);
LABEL_547:
  operator delete(v32);
  SafeFree(v33);
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationRequestSerializer::CreateRegistrationRequestBodyImpl",
    (unsigned int)v34);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x1800618b0  push    rbp
0x1800618b2  push    rbx
0x1800618b3  push    rsi
0x1800618b4  push    rdi
0x1800618b5  push    r12
0x1800618b7  push    r13
0x1800618b9  push    r14
0x1800618bb  push    r15
0x1800618bd  lea     rbp, [rsp-128h]
0x1800618c5  sub     rsp, 228h
0x1800618cc  mov     rax, cs:__security_cookie
0x1800618d3  xor     rax, rsp
0x1800618d6  mov     [rbp+160h+var_50], rax
0x1800618dd  mov     [rbp+160h+var_1D0], r9
0x1800618e1  mov     r13, r8
0x1800618e4  mov     r12, rdx
0x1800618e7  mov     r15, rcx
0x1800618ea  mov     rax, [rbp+160h+arg_60]
0x1800618f1  mov     [rbp+160h+var_1A8], rax
0x1800618f5  mov     rax, [rbp+160h+arg_58]
0x1800618fc  mov     [rbp+160h+var_1A0], rax
0x180061900  mov     rcx, [rbp+160h+arg_D8]
0x180061907  mov     [rsp+260h+var_210], rcx
0x18006190c  mov     rax, [rbp+160h+arg_20]
0x180061913  mov     [rbp+160h+var_1C0], rax
0x180061917  mov     rcx, [rbp+160h+arg_28]
0x18006191e  mov     [rsp+260h+var_218], rcx
0x180061923  mov     rax, [rbp+160h+arg_30]
0x18006192a  mov     [rbp+160h+var_1B8], rax
0x18006192e  mov     rcx, [rbp+160h+arg_38]
0x180061935  mov     [rbp+160h+var_1B0], rcx
0x180061939  mov     rax, [rbp+160h+arg_40]
0x180061940  mov     [rbp+160h+var_1C8], rax
0x180061944  mov     rax, [rbp+160h+arg_48]
0x18006194b  mov     [rbp+160h+var_180], rax
0x18006194f  mov     rax, [rbp+160h+arg_50]
0x180061956  mov     [rbp+160h+var_188], rax
0x18006195a  mov     rax, [rbp+160h+arg_68]
0x180061961  mov     [rbp+160h+var_178], rax
0x180061965  mov     rax, [rbp+160h+arg_78]
0x18006196c  mov     [rsp+260h+var_208], rax
0x180061971  mov     rax, [rbp+160h+arg_88]
0x180061978  mov     [rsp+260h+var_1F0], rax
0x18006197d  mov     rax, [rbp+160h+arg_90]
0x180061984  mov     [rsp+260h+var_1E8], rax
0x180061989  mov     rax, [rbp+160h+arg_98]
0x180061990  mov     [rbp+160h+var_1E0], rax
0x180061994  mov     rax, [rbp+160h+arg_A0]
0x18006199b  mov     [rbp+160h+var_170], rax
0x18006199f  mov     rcx, [rbp+160h+arg_A8]
0x1800619a6  mov     [rbp+160h+var_1D8], rcx
0x1800619aa  mov     rax, [rbp+160h+arg_B8]
0x1800619b1  mov     [rbp+160h+var_190], rax
0x1800619b5  mov     rax, [rbp+160h+arg_C0]
0x1800619bc  mov     [rbp+160h+var_198], rax
0x1800619c0  mov     rax, [rbp+160h+arg_C8]
0x1800619c7  mov     [rsp+260h+var_200], rax
0x1800619cc  mov     rax, [rbp+160h+arg_D0]
0x1800619d3  mov     [rsp+260h+var_1F8], rax
0x1800619d8  mov     rax, [rbp+160h+arg_E0]
0x1800619df  mov     [rbp+160h+var_168], rax
0x1800619e3  xor     edi, edi
0x1800619e5  mov     esi, edi
0x1800619e7  mov     r14d, edi
0x1800619ea  mov     [rsp+260h+lpMem], rdi
0x1800619ef  mov     [rax], rdi
0x1800619f2  mov     ecx, [rbp+160h+arg_70]
0x1800619f8  lea     eax, [rcx-1]
0x1800619fb  cmp     eax, 1
0x1800619fe  jbe     short loc_180061A20
0x180061a00  mov     r8d, ecx
0x180061a03  lea     rdx, aRegistrationre_2; "RegistrationRequestSerializer::CreateRe"...
0x180061a0a  lea     rcx, aSUnexpectedTok; "%s: Unexpected tokentype '%d' as join a"...
0x180061a11  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180061a16  mov     edi, 80070057h
0x180061a1b  jmp     loc_180063E25
0x180061a20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180061a27  mov     ecx, 2; unsigned __int64
0x180061a2c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180061a31  mov     rbx, rax
0x180061a34  mov     [rsp+260h+Block], rax
0x180061a39  test    rax, rax
0x180061a3c  jnz     short loc_180061A5B
0x180061a3e  mov     edi, 8007000Eh
0x180061a43  lea     rdx, aRegistrationre_2; "RegistrationRequestSerializer::CreateRe"...
0x180061a4a  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180061a51  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180061a56  jmp     loc_180063E16
0x180061a5b  mov     rax, [rsp+260h+Block]
0x180061a60  mov     [rax], di
0x180061a63  or      r14, 0FFFFFFFFFFFFFFFFh
0x180061a67  mov     rcx, r14
0x180061a6a  inc     rcx; unsigned __int64
0x180061a6d  cmp     [rbx+rcx*2], di
0x180061a71  jnz     short loc_180061A6A
0x180061a73  lea     rax, [rsp+260h+Block]
0x180061a78  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061a7d  lea     r9, aCertificatereq; "{\"CertificateRequest\":{\"Type\":\"pkc"...
0x180061a84  mov     r8d, 2Fh ; '/'; unsigned __int64
0x180061a8a  mov     rdx, [rsp+260h+Block]; unsigned __int16 *
0x180061a8f  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061a94  mov     edi, eax
0x180061a96  test    eax, eax
0x180061a98  jns     short loc_180061ABC
0x180061a9a  lea     r8, aConcatenatestr; "ConcatenateStringW"
0x180061aa1  mov     r9d, eax
0x180061aa4  lea     rdx, aRegistrationre_2; "RegistrationRequestSerializer::CreateRe"...
0x180061aab  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180061ab2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180061ab7  jmp     loc_180063E0E
0x180061abc  mov     rcx, rbx; Block
0x180061abf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061ac4  mov     rsi, [rsp+260h+Block]
0x180061ac9  mov     r8, r14
0x180061acc  xor     ebx, ebx
0x180061ace  inc     r8; unsigned __int64
0x180061ad1  cmp     [r15+r8*2], bx
0x180061ad6  jnz     short loc_180061ACE
0x180061ad8  mov     rcx, r14
0x180061adb  inc     rcx; unsigned __int64
0x180061ade  cmp     [rsi+rcx*2], bx
0x180061ae2  jnz     short loc_180061ADB
0x180061ae4  lea     rax, [rsp+260h+Block]
0x180061ae9  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061aee  mov     r9, r15; unsigned __int16 *
0x180061af1  mov     rdx, rsi; unsigned __int16 *
0x180061af4  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061af9  mov     edi, eax
0x180061afb  test    eax, eax
0x180061afd  jns     short loc_180061B21
0x180061aff  mov     r9d, eax
0x180061b02  lea     r8, aConcatenatestr; "ConcatenateStringW"
0x180061b09  lea     rdx, aRegistrationre_2; "RegistrationRequestSerializer::CreateRe"...
0x180061b10  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180061b17  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180061b1c  jmp     loc_180063E11
0x180061b21  mov     rcx, rsi; Block
0x180061b24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061b29  mov     rsi, [rsp+260h+Block]
0x180061b2e  mov     rcx, r14
0x180061b31  inc     rcx; unsigned __int64
0x180061b34  cmp     [rsi+rcx*2], bx
0x180061b38  jnz     short loc_180061B31
0x180061b3a  lea     rax, [rsp+260h+Block]
0x180061b3f  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061b44  lea     r9, asc_1800D5D20; "\""
0x180061b4b  mov     r15d, 1
0x180061b51  mov     r8d, r15d; unsigned __int64
0x180061b54  mov     rdx, rsi; unsigned __int16 *
0x180061b57  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061b5c  mov     edi, eax
0x180061b5e  test    eax, eax
0x180061b60  js      short loc_180061AFF
0x180061b62  mov     rcx, rsi; Block
0x180061b65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061b6a  mov     rcx, r12; unsigned __int16 *
0x180061b6d  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180061b72  test    eax, eax
0x180061b74  jnz     loc_180061C40
0x180061b7a  mov     rsi, [rsp+260h+Block]
0x180061b7f  mov     rcx, r14
0x180061b82  inc     rcx; unsigned __int64
0x180061b85  cmp     [rsi+rcx*2], bx
0x180061b89  jnz     short loc_180061B82
0x180061b8b  lea     rax, [rsp+260h+Block]
0x180061b90  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061b95  lea     r9, aKeytype; ",\"KeyType\":\""
0x180061b9c  mov     r8d, 0Ch; unsigned __int64
0x180061ba2  mov     rdx, rsi; unsigned __int16 *
0x180061ba5  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061baa  mov     edi, eax
0x180061bac  test    eax, eax
0x180061bae  js      loc_180061AFF
0x180061bb4  mov     rcx, rsi; Block
0x180061bb7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061bbc  mov     rsi, [rsp+260h+Block]
0x180061bc1  mov     r8, r14
0x180061bc4  inc     r8; unsigned __int64
0x180061bc7  cmp     [r12+r8*2], bx
0x180061bcc  jnz     short loc_180061BC4
0x180061bce  mov     rcx, r14
0x180061bd1  inc     rcx; unsigned __int64
0x180061bd4  cmp     [rsi+rcx*2], bx
0x180061bd8  jnz     short loc_180061BD1
0x180061bda  lea     rax, [rsp+260h+Block]
0x180061bdf  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061be4  mov     r9, r12; unsigned __int16 *
0x180061be7  mov     rdx, rsi; unsigned __int16 *
0x180061bea  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061bef  mov     edi, eax
0x180061bf1  test    eax, eax
0x180061bf3  js      loc_180061AFF
0x180061bf9  mov     rcx, rsi; Block
0x180061bfc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061c01  mov     rsi, [rsp+260h+Block]
0x180061c06  mov     rcx, r14
0x180061c09  inc     rcx; unsigned __int64
0x180061c0c  cmp     [rsi+rcx*2], bx
0x180061c10  jnz     short loc_180061C09
0x180061c12  lea     rax, [rsp+260h+Block]
0x180061c17  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061c1c  lea     r9, asc_1800D5D20; "\""
0x180061c23  mov     r8, r15; unsigned __int64
0x180061c26  mov     rdx, rsi; unsigned __int16 *
0x180061c29  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061c2e  mov     edi, eax
0x180061c30  test    eax, eax
0x180061c32  js      loc_180061AFF
0x180061c38  mov     rcx, rsi; Block
0x180061c3b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061c40  mov     rcx, r13; unsigned __int16 *
0x180061c43  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180061c48  test    eax, eax
0x180061c4a  jnz     loc_180061D1D
0x180061c50  mov     rsi, [rsp+260h+Block]
0x180061c55  mov     rcx, r14
0x180061c58  inc     rcx; unsigned __int64
0x180061c5b  cmp     [rsi+rcx*2], bx
0x180061c5f  jnz     short loc_180061C58
0x180061c61  lea     rax, [rsp+260h+Block]
0x180061c66  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061c6b  lea     r9, aKeysecurity; ",\"KeySecurity\":\""
0x180061c72  mov     r8d, 10h; unsigned __int64
0x180061c78  mov     rdx, rsi; unsigned __int16 *
0x180061c7b  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061c80  mov     edi, eax
0x180061c82  test    eax, eax
0x180061c84  js      loc_180061AFF
0x180061c8a  mov     rcx, rsi; Block
0x180061c8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061c92  mov     rsi, [rsp+260h+Block]
0x180061c97  mov     r8, r14
0x180061c9a  inc     r8; unsigned __int64
0x180061c9d  cmp     [r13+r8*2+0], bx
0x180061ca3  jnz     short loc_180061C9A
0x180061ca5  mov     rcx, r14
0x180061ca8  inc     rcx; unsigned __int64
0x180061cab  cmp     [rsi+rcx*2], bx
0x180061caf  jnz     short loc_180061CA8
0x180061cb1  lea     rax, [rsp+260h+Block]
0x180061cb6  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061cbb  mov     r9, r13; unsigned __int16 *
0x180061cbe  mov     rdx, rsi; unsigned __int16 *
0x180061cc1  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061cc6  mov     edi, eax
0x180061cc8  xor     r13d, r13d
0x180061ccb  test    eax, eax
0x180061ccd  js      loc_180061AFF
0x180061cd3  mov     rcx, rsi; Block
0x180061cd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061cdb  mov     rsi, [rsp+260h+Block]
0x180061ce0  mov     rcx, r14
0x180061ce3  inc     rcx; unsigned __int64
0x180061ce6  cmp     [rsi+rcx*2], r13w
0x180061ceb  jnz     short loc_180061CE3
0x180061ced  lea     rax, [rsp+260h+Block]
0x180061cf2  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061cf7  lea     r9, asc_1800D5D20; "\""
0x180061cfe  mov     r8, r15; unsigned __int64
0x180061d01  mov     rdx, rsi; unsigned __int16 *
0x180061d04  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061d09  mov     edi, eax
0x180061d0b  test    eax, eax
0x180061d0d  js      loc_180061AFF
0x180061d13  mov     rcx, rsi; Block
0x180061d16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061d1b  jmp     short loc_180061D20
0x180061d1d  xor     r13d, r13d
0x180061d20  mov     rsi, [rsp+260h+Block]
0x180061d25  mov     rcx, r14
0x180061d28  inc     rcx; unsigned __int64
0x180061d2b  cmp     [rsi+rcx*2], r13w
0x180061d30  jnz     short loc_180061D28
0x180061d32  lea     rax, [rsp+260h+Block]
0x180061d37  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061d3c  lea     r9, asc_1800E8764; "},"
0x180061d43  mov     r8d, 2; unsigned __int64
0x180061d49  mov     rdx, rsi; unsigned __int16 *
0x180061d4c  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
0x180061d51  mov     edi, eax
0x180061d53  test    eax, eax
0x180061d55  js      loc_180061AFF
0x180061d5b  mov     rcx, rsi; Block
0x180061d5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180061d63  mov     rbx, [rbp+160h+var_1D0]
0x180061d67  mov     rcx, rbx; unsigned __int16 *
0x180061d6a  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180061d6f  test    eax, eax
0x180061d71  jnz     loc_180061E43
0x180061d77  mov     rsi, [rsp+260h+Block]
0x180061d7c  mov     rcx, r14
0x180061d7f  inc     rcx; unsigned __int64
0x180061d82  cmp     [rsi+rcx*2], r13w
0x180061d87  jnz     short loc_180061D7F
0x180061d89  lea     rax, [rsp+260h+Block]
0x180061d8e  mov     [rsp+260h+var_240], rax; unsigned __int16 **
0x180061d93  lea     r9, aRacertificater_0; "\"RaCertificateRequest\":{\"Type\":\"pk"...
0x180061d9a  mov     r8d, 30h ; '0'; unsigned __int64
0x180061da0  mov     rdx, rsi; unsigned __int16 *
0x180061da3  call    ?ConcatenateStringW@@YAJ_KPEBG01PEAPEAG@Z; ConcatenateStringW(unsigned __int64,ushort const *,unsigned __int64,ushort const *,ushort * *)
  ... truncated ...
```
