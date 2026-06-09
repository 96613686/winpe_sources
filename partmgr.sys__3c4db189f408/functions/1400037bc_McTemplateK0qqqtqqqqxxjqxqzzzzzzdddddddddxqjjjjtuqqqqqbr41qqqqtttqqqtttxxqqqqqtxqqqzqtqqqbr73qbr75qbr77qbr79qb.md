# McTemplateK0qqqtqqqqxxjqxqzzzzzzdddddddddxqjjjjtuqqqqqbr41qqqqtttqqqtttxxqqqqqtxqqqzqtqqqbr73qbr75qbr77qbr79qbr81qbr83_EtwWriteTransfer

- ea: `0x1400037bc`
- end: `0x140004184`
- name: `McTemplateK0qqqtqqqqxxjqxqzzzzzzdddddddddxqjjjjtuqqqqqbr41qqqqtttqqqtttxxqqqqqtxqqqzqtqqqbr73qbr75qbr77qbr79qbr81qbr83_EtwWriteTransfer`
- size: `2504`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140026f44`

## callees

- `0x1400037bc`
- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqqtqqqqxxjqxqzzzzzzdddddddddxqjjjjtuqqqqqbr41qqqqtttqqqtttxxqqqqqtxqqqzqtqqqbr73qbr75qbr77qbr79qbr81qbr83_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        __int64 a14,
        char a15,
        char a16,
        char a17,
        const wchar_t *a18,
        const wchar_t *a19,
        const wchar_t *a20,
        const wchar_t *a21,
        const wchar_t *a22,
        const wchar_t *a23,
        char a24,
        char a25,
        char a26,
        char a27,
        char a28,
        char a29,
        char a30,
        char a31,
        char a32,
        char a33,
        char a34,
        __int64 a35,
        __int64 a36,
        __int64 a37,
        __int64 a38,
        char a39,
        char a40,
        char a41,
        char a42,
        char a43,
        char a44,
        int a45,
        __int64 a46,
        char a47,
        char a48,
        char a49,
        char a50,
        char a51,
        char a52,
        char a53,
        char a54,
        char a55,
        char a56,
        char a57,
        char a58,
        char a59,
        char a60,
        char a61,
        char a62,
        char a63)
{
  char a64; // [rsp+7B8h] [rbp+6B8h] BYREF
  __int64 v64; // rcx
  int v66; // edx
  const wchar_t *v67; // rax
  __int64 v68; // r8
  int v69; // r8d
  const wchar_t *v70; // rax
  __int64 v71; // r8
  int v72; // r8d
  const wchar_t *v73; // rax
  __int64 v74; // r8
  int v75; // r8d
  const wchar_t *v76; // rax
  __int64 v77; // r8
  int v78; // r8d
  const wchar_t *v79; // rax
  __int64 v80; // r8
  int v81; // r8d
  const wchar_t *v82; // r8
  __int64 v83; // rax
  int v84; // eax
  const wchar_t *v85; // rax
  bool v86; // zf
  struct _EVENT_DATA_DESCRIPTOR v88; // [rsp+30h] [rbp-D0h] BYREF
  int *v89; // [rsp+40h] [rbp-C0h]
  __int64 v90; // [rsp+48h] [rbp-B8h]
  char *v91; // [rsp+50h] [rbp-B0h]
  __int64 v92; // [rsp+58h] [rbp-A8h]
  char *v93; // [rsp+60h] [rbp-A0h]
  __int64 v94; // [rsp+68h] [rbp-98h]
  char *v95; // [rsp+70h] [rbp-90h]
  __int64 v96; // [rsp+78h] [rbp-88h]
  char *v97; // [rsp+80h] [rbp-80h]
  __int64 v98; // [rsp+88h] [rbp-78h]
  char *v99; // [rsp+90h] [rbp-70h]
  __int64 v100; // [rsp+98h] [rbp-68h]
  char *v101; // [rsp+A0h] [rbp-60h]
  __int64 v102; // [rsp+A8h] [rbp-58h]
  char *v103; // [rsp+B0h] [rbp-50h]
  __int64 v104; // [rsp+B8h] [rbp-48h]
  char *v105; // [rsp+C0h] [rbp-40h]
  __int64 v106; // [rsp+C8h] [rbp-38h]
  char *v107; // [rsp+D0h] [rbp-30h]
  __int64 v108; // [rsp+D8h] [rbp-28h]
  __int64 v109; // [rsp+E0h] [rbp-20h]
  __int64 v110; // [rsp+E8h] [rbp-18h]
  char *v111; // [rsp+F0h] [rbp-10h]
  __int64 v112; // [rsp+F8h] [rbp-8h]
  char *v113; // [rsp+100h] [rbp+0h]
  __int64 v114; // [rsp+108h] [rbp+8h]
  char *v115; // [rsp+110h] [rbp+10h]
  __int64 v116; // [rsp+118h] [rbp+18h]
  const wchar_t *v117; // [rsp+120h] [rbp+20h]
  int v118; // [rsp+128h] [rbp+28h]
  int v119; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v120; // [rsp+130h] [rbp+30h]
  int v121; // [rsp+138h] [rbp+38h]
  int v122; // [rsp+13Ch] [rbp+3Ch]
  const wchar_t *v123; // [rsp+140h] [rbp+40h]
  int v124; // [rsp+148h] [rbp+48h]
  int v125; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v126; // [rsp+150h] [rbp+50h]
  int v127; // [rsp+158h] [rbp+58h]
  int v128; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v129; // [rsp+160h] [rbp+60h]
  int v130; // [rsp+168h] [rbp+68h]
  int v131; // [rsp+16Ch] [rbp+6Ch]
  const wchar_t *v132; // [rsp+170h] [rbp+70h]
  int v133; // [rsp+178h] [rbp+78h]
  int v134; // [rsp+17Ch] [rbp+7Ch]
  char *v135; // [rsp+180h] [rbp+80h]
  __int64 v136; // [rsp+188h] [rbp+88h]
  char *v137; // [rsp+190h] [rbp+90h]
  __int64 v138; // [rsp+198h] [rbp+98h]
  char *v139; // [rsp+1A0h] [rbp+A0h]
  __int64 v140; // [rsp+1A8h] [rbp+A8h]
  char *v141; // [rsp+1B0h] [rbp+B0h]
  __int64 v142; // [rsp+1B8h] [rbp+B8h]
  char *v143; // [rsp+1C0h] [rbp+C0h]
  __int64 v144; // [rsp+1C8h] [rbp+C8h]
  char *v145; // [rsp+1D0h] [rbp+D0h]
  __int64 v146; // [rsp+1D8h] [rbp+D8h]
  char *v147; // [rsp+1E0h] [rbp+E0h]
  __int64 v148; // [rsp+1E8h] [rbp+E8h]
  char *v149; // [rsp+1F0h] [rbp+F0h]
  __int64 v150; // [rsp+1F8h] [rbp+F8h]
  char *v151; // [rsp+200h] [rbp+100h]
  __int64 v152; // [rsp+208h] [rbp+108h]
  char *v153; // [rsp+210h] [rbp+110h]
  __int64 v154; // [rsp+218h] [rbp+118h]
  char *v155; // [rsp+220h] [rbp+120h]
  __int64 v156; // [rsp+228h] [rbp+128h]
  __int64 v157; // [rsp+230h] [rbp+130h]
  __int64 v158; // [rsp+238h] [rbp+138h]
  __int64 v159; // [rsp+240h] [rbp+140h]
  __int64 v160; // [rsp+248h] [rbp+148h]
  __int64 v161; // [rsp+250h] [rbp+150h]
  __int64 v162; // [rsp+258h] [rbp+158h]
  __int64 v163; // [rsp+260h] [rbp+160h]
  __int64 v164; // [rsp+268h] [rbp+168h]
  char *v165; // [rsp+270h] [rbp+170h]
  __int64 v166; // [rsp+278h] [rbp+178h]
  char *v167; // [rsp+280h] [rbp+180h]
  __int64 v168; // [rsp+288h] [rbp+188h]
  char *v169; // [rsp+290h] [rbp+190h]
  __int64 v170; // [rsp+298h] [rbp+198h]
  char *v171; // [rsp+2A0h] [rbp+1A0h]
  __int64 v172; // [rsp+2A8h] [rbp+1A8h]
  char *v173; // [rsp+2B0h] [rbp+1B0h]
  __int64 v174; // [rsp+2B8h] [rbp+1B8h]
  char *v175; // [rsp+2C0h] [rbp+1C0h]
  __int64 v176; // [rsp+2C8h] [rbp+1C8h]
  int *v177; // [rsp+2D0h] [rbp+1D0h]
  __int64 v178; // [rsp+2D8h] [rbp+1D8h]
  __int64 v179; // [rsp+2E0h] [rbp+1E0h]
  int v180; // [rsp+2E8h] [rbp+1E8h]
  int v181; // [rsp+2ECh] [rbp+1ECh]
  char *v182; // [rsp+2F0h] [rbp+1F0h]
  __int64 v183; // [rsp+2F8h] [rbp+1F8h]
  char *v184; // [rsp+300h] [rbp+200h]
  __int64 v185; // [rsp+308h] [rbp+208h]
  char *v186; // [rsp+310h] [rbp+210h]
  __int64 v187; // [rsp+318h] [rbp+218h]
  char *v188; // [rsp+320h] [rbp+220h]
  __int64 v189; // [rsp+328h] [rbp+228h]
  char *v190; // [rsp+330h] [rbp+230h]
  __int64 v191; // [rsp+338h] [rbp+238h]
  char *v192; // [rsp+340h] [rbp+240h]
  __int64 v193; // [rsp+348h] [rbp+248h]
  char *v194; // [rsp+350h] [rbp+250h]
  __int64 v195; // [rsp+358h] [rbp+258h]
  char *v196; // [rsp+360h] [rbp+260h]
  __int64 v197; // [rsp+368h] [rbp+268h]
  char *v198; // [rsp+370h] [rbp+270h]
  __int64 v199; // [rsp+378h] [rbp+278h]
  char *v200; // [rsp+380h] [rbp+280h]
  __int64 v201; // [rsp+388h] [rbp+288h]
  char *v202; // [rsp+390h] [rbp+290h]
  __int64 v203; // [rsp+398h] [rbp+298h]
  char *v204; // [rsp+3A0h] [rbp+2A0h]
  __int64 v205; // [rsp+3A8h] [rbp+2A8h]
  char *v206; // [rsp+3B0h] [rbp+2B0h]
  __int64 v207; // [rsp+3B8h] [rbp+2B8h]
  char *v208; // [rsp+3C0h] [rbp+2C0h]
  __int64 v209; // [rsp+3C8h] [rbp+2C8h]
  char *v210; // [rsp+3D0h] [rbp+2D0h]
  __int64 v211; // [rsp+3D8h] [rbp+2D8h]
  char *v212; // [rsp+3E0h] [rbp+2E0h]
  __int64 v213; // [rsp+3E8h] [rbp+2E8h]
  char *v214; // [rsp+3F0h] [rbp+2F0h]
  __int64 v215; // [rsp+3F8h] [rbp+2F8h]
  char *v216; // [rsp+400h] [rbp+300h]
  __int64 v217; // [rsp+408h] [rbp+308h]
  unsigned __int64 *v218; // [rsp+410h] [rbp+310h]
  __int64 v219; // [rsp+418h] [rbp+318h]
  unsigned __int64 *v220; // [rsp+420h] [rbp+320h]
  __int64 v221; // [rsp+428h] [rbp+328h]
  unsigned __int64 *v222; // [rsp+430h] [rbp+330h]
  __int64 v223; // [rsp+438h] [rbp+338h]
  unsigned __int64 *v224; // [rsp+440h] [rbp+340h]
  __int64 v225; // [rsp+448h] [rbp+348h]
  unsigned __int64 *v226; // [rsp+450h] [rbp+350h]
  __int64 v227; // [rsp+458h] [rbp+358h]
  unsigned __int64 *v228; // [rsp+460h] [rbp+360h]
  __int64 v229; // [rsp+468h] [rbp+368h]
  unsigned __int64 *v230; // [rsp+470h] [rbp+370h]
  __int64 v231; // [rsp+478h] [rbp+378h]
  const wchar_t *v232; // [rsp+480h] [rbp+380h]
  int v233; // [rsp+488h] [rbp+388h]
  int v234; // [rsp+48Ch] [rbp+38Ch]
  unsigned __int64 *v235; // [rsp+490h] [rbp+390h]
  __int64 v236; // [rsp+498h] [rbp+398h]
  unsigned __int64 *v237; // [rsp+4A0h] [rbp+3A0h]
  __int64 v238; // [rsp+4A8h] [rbp+3A8h]
  unsigned __int64 *v239; // [rsp+4B0h] [rbp+3B0h]
  __int64 v240; // [rsp+4B8h] [rbp+3B8h]
  unsigned __int64 *v241; // [rsp+4C0h] [rbp+3C0h]
  __int64 v242; // [rsp+4C8h] [rbp+3C8h]
  unsigned __int64 *v243; // [rsp+4D0h] [rbp+3D0h]
  __int64 v244; // [rsp+4D8h] [rbp+3D8h]
  unsigned __int64 v245; // [rsp+4E0h] [rbp+3E0h]
  int v246; // [rsp+4E8h] [rbp+3E8h]
  int v247; // [rsp+4ECh] [rbp+3ECh]
  unsigned __int64 *v248; // [rsp+4F0h] [rbp+3F0h]
  __int64 v249; // [rsp+4F8h] [rbp+3F8h]
  unsigned __int64 v250; // [rsp+500h] [rbp+400h]
  int v251; // [rsp+508h] [rbp+408h]
  int v252; // [rsp+50Ch] [rbp+40Ch]
  unsigned __int64 *v253; // [rsp+510h] [rbp+410h]
  __int64 v254; // [rsp+518h] [rbp+418h]
  unsigned __int64 v255; // [rsp+520h] [rbp+420h]
  int v256; // [rsp+528h] [rbp+428h]
  int v257; // [rsp+52Ch] [rbp+42Ch]
  unsigned __int64 *v258; // [rsp+530h] [rbp+430h]
  __int64 v259; // [rsp+538h] [rbp+438h]
  unsigned __int64 v260; // [rsp+540h] [rbp+440h]
  int v261; // [rsp+548h] [rbp+448h]
  int v262; // [rsp+54Ch] [rbp+44Ch]
  unsigned __int64 *v263; // [rsp+550h] [rbp+450h]
  __int64 v264; // [rsp+558h] [rbp+458h]
  unsigned __int64 v265; // [rsp+560h] [rbp+460h]
  int v266; // [rsp+568h] [rbp+468h]
  int v267; // [rsp+56Ch] [rbp+46Ch]
  unsigned __int64 *v268; // [rsp+570h] [rbp+470h]
  __int64 v269; // [rsp+578h] [rbp+478h]
  unsigned __int64 v270; // [rsp+580h] [rbp+480h]
  int v271; // [rsp+588h] [rbp+488h]
  int v272; // [rsp+58Ch] [rbp+48Ch]
  int v273; // [rsp+5D8h] [rbp+4D8h] BYREF

  v273 = a4;
  v90 = 4;
  v89 = &v273;
  v92 = 4;
  v91 = &a5;
  v64 = -1;
  v94 = 4;
  v93 = &a6;
  v96 = 4;
  v95 = &a7;
  v66 = 10;
  v98 = 4;
  v97 = &a8;
  v99 = &a9;
  v101 = &a10;
  v103 = &a11;
  v105 = &a12;
  v107 = &a13;
  v109 = a14;
  v111 = &a15;
  v113 = &a16;
  v115 = &a17;
  v67 = a18;
  v100 = 4;
  v102 = 4;
  v104 = 4;
  v106 = 8;
  v108 = 8;
  v110 = 16;
  v112 = 4;
  v114 = 8;
  v116 = 4;
  if ( a18 )
  {
    v68 = -1;
    do
      ++v68;
    while ( a18[v68] );
    v69 = 2 * v68 + 2;
  }
  else
  {
    v69 = 10;
  }
  v118 = v69;
  v119 = 0;
  if ( !a18 )
    v67 = L"NULL";
  v117 = v67;
  v70 = a19;
  if ( a19 )
  {
    v71 = -1;
    do
      ++v71;
    while ( a19[v71] );
    v72 = 2 * v71 + 2;
  }
  else
  {
    v72 = 10;
  }
  v121 = v72;
  v122 = 0;
  if ( !a19 )
    v70 = L"NULL";
  v120 = v70;
  v73 = a20;
  if ( a20 )
  {
    v74 = -1;
    do
      ++v74;
    while ( a20[v74] );
    v75 = 2 * v74 + 2;
  }
  else
  {
    v75 = 10;
  }
  v124 = v75;
  v125 = 0;
  if ( !a20 )
    v73 = L"NULL";
  v123 = v73;
  v76 = a21;
  if ( a21 )
  {
    v77 = -1;
    do
      ++v77;
    while ( a21[v77] );
    v78 = 2 * v77 + 2;
  }
  else
  {
    v78 = 10;
  }
  v127 = v78;
  v128 = 0;
  if ( !a21 )
    v76 = L"NULL";
  v126 = v76;
  v79 = a22;
  if ( a22 )
  {
    v80 = -1;
    do
      ++v80;
    while ( a22[v80] );
    v81 = 2 * v80 + 2;
  }
  else
  {
    v81 = 10;
  }
  v130 = v81;
  v82 = a23;
  if ( !a22 )
    v79 = L"NULL";
  v131 = 0;
  v129 = v79;
  if ( a23 )
  {
    v83 = -1;
    do
      ++v83;
    while ( a23[v83] );
    v84 = 2 * v83 + 2;
  }
  else
  {
    v84 = 10;
  }
  v133 = v84;
  v134 = 0;
  v135 = &a24;
  if ( !a23 )
    v82 = L"NULL";
  v132 = v82;
  v137 = &a25;
  v139 = &a26;
  v141 = &a27;
  v143 = &a28;
  v145 = &a29;
  v147 = &a30;
  v149 = &a31;
  v151 = &a32;
  v153 = &a33;
  v155 = &a34;
  v157 = a35;
  v159 = a36;
  v161 = a37;
  v163 = a38;
  v165 = &a39;
  v167 = &a40;
  v169 = &a41;
  v171 = &a42;
  v173 = &a43;
  v175 = &a44;
  v177 = &a45;
  v179 = a46;
  v180 = a45;
  v182 = &a47;
  v184 = &a48;
  v136 = 4;
  v138 = 4;
  v140 = 4;
  v142 = 4;
  v144 = 4;
  v146 = 4;
  v148 = 4;
  v150 = 4;
  v152 = 4;
  v154 = 8;
  v156 = 4;
  v158 = 16;
  v160 = 16;
  v162 = 16;
  v164 = 16;
  v166 = 4;
  v168 = 1;
  v170 = 4;
  v172 = 4;
  v174 = 4;
  v176 = 4;
  v178 = 4;
  v181 = 0;
  v183 = 4;
  v185 = 4;
  v186 = &a49;
  v188 = &a50;
  v190 = &a51;
  v192 = &a52;
  v194 = &a53;
  v196 = &a54;
  v198 = &a55;
  v200 = &a56;
  v202 = &a57;
  v204 = &a58;
  v206 = &a59;
  v208 = &a60;
  v210 = &a61;
  v212 = &a62;
  v214 = &a63;
  v216 = &a64;
  v218 = &STACK[0x7C0];
  v220 = &STACK[0x7C8];
  v222 = &STACK[0x7D0];
  v224 = &STACK[0x7D8];
  v226 = &STACK[0x7E0];
  v228 = &STACK[0x7E8];
  v230 = &STACK[0x7F0];
  v85 = (const wchar_t *)STACK[0x7F8];
  v187 = 4;
  v189 = 4;
  v191 = 4;
  v193 = 4;
  v195 = 4;
  v197 = 4;
  v199 = 4;
  v201 = 4;
  v203 = 4;
  v205 = 4;
  v207 = 4;
  v209 = 8;
  v211 = 8;
  v213 = 4;
  v215 = 4;
  v217 = 4;
  v219 = 4;
  v221 = 4;
  v223 = 4;
  v225 = 8;
  v227 = 4;
  v229 = 4;
  v231 = 4;
  v86 = v85 == 0;
  if ( v85 )
  {
    do
      ++v64;
    while ( v85[v64] );
    v66 = 2 * v64 + 2;
    v86 = v85 == 0;
  }
  if ( v86 )
    v85 = L"NULL";
  v233 = v66;
  v232 = v85;
  v234 = 0;
  v235 = &STACK[0x800];
  v247 = 0;
  v237 = &STACK[0x808];
  v239 = &STACK[0x810];
  v241 = &STACK[0x818];
  v243 = &STACK[0x820];
  v245 = STACK[0x828];
  v246 = STACK[0x820];
  v248 = &STACK[0x830];
  v250 = STACK[0x838];
  v251 = STACK[0x830];
  v253 = &STACK[0x840];
  v255 = STACK[0x848];
  v256 = STACK[0x840];
  v258 = &STACK[0x850];
  v260 = STACK[0x858];
  v261 = STACK[0x850];
  v263 = &STACK[0x860];
  v265 = STACK[0x868];
  v266 = STACK[0x860];
  v268 = &STACK[0x870];
  v270 = STACK[0x878];
  v271 = STACK[0x870];
  v252 = 0;
  v257 = 0;
  v262 = 0;
  v267 = 0;
  v272 = 0;
  v236 = 4;
  v238 = 4;
  v240 = 4;
  v242 = 4;
  v244 = 4;
  v249 = 4;
  v254 = 4;
  v259 = 4;
  v264 = 4;
  v269 = 4;
  return McGenEventWrite_EtwWriteTransfer(v64, a2, 0, 0x56u, &v88);
}

```

## disassembly

```asm
0x1400037bc  mov     [rsp-8+arg_0], rbx
0x1400037c1  mov     [rsp-8+arg_18], r9d
0x1400037c6  push    rbp
0x1400037c7  push    rsi
0x1400037c8  push    rdi
0x1400037c9  lea     rbp, [rsp-4A0h]
0x1400037d1  sub     rsp, 5A0h
0x1400037d8  mov     rax, cs:__security_cookie
0x1400037df  xor     rax, rsp
0x1400037e2  mov     [rbp+4B0h+var_20], rax
0x1400037e9  lea     rax, [rbp+4B0h+arg_18]
0x1400037f0  mov     [rsp+5B0h+var_568], 4
0x1400037f9  mov     [rsp+5B0h+var_570], rax
0x1400037fe  xor     r9d, r9d
0x140003801  lea     rax, [rbp+4B0h+arg_20]
0x140003808  mov     [rsp+5B0h+var_558], 4
0x140003811  mov     [rsp+5B0h+var_560], rax
0x140003816  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000381a  lea     rax, [rbp+4B0h+arg_28]
0x140003821  mov     [rsp+5B0h+var_548], 4
0x14000382a  mov     [rsp+5B0h+var_550], rax
0x14000382f  mov     r10, rdx
0x140003832  lea     rax, [rbp+4B0h+arg_30]
0x140003839  mov     [rsp+5B0h+var_538], 4
0x140003842  mov     [rsp+5B0h+var_540], rax
0x140003847  lea     edx, [r9+0Ah]
0x14000384b  lea     rax, [rbp+4B0h+arg_38]
0x140003852  mov     [rbp+4B0h+var_528], 4
0x14000385a  mov     [rbp+4B0h+var_530], rax
0x14000385e  lea     rax, [rbp+4B0h+arg_40]
0x140003865  mov     [rbp+4B0h+var_520], rax
0x140003869  lea     rax, [rbp+4B0h+arg_48]
0x140003870  mov     [rbp+4B0h+var_510], rax
0x140003874  lea     rax, [rbp+4B0h+arg_50]
0x14000387b  mov     [rbp+4B0h+var_500], rax
0x14000387f  lea     rax, [rbp+4B0h+arg_58]
0x140003886  mov     [rbp+4B0h+var_4F0], rax
0x14000388a  lea     rax, [rbp+4B0h+arg_60]
0x140003891  mov     [rbp+4B0h+var_4E0], rax
0x140003895  mov     rax, [rbp+4B0h+arg_68]
0x14000389c  mov     [rbp+4B0h+var_4D0], rax
0x1400038a0  lea     rax, [rbp+4B0h+arg_70]
0x1400038a7  mov     [rbp+4B0h+var_4C0], rax
0x1400038ab  lea     rax, [rbp+4B0h+arg_78]
0x1400038b2  mov     [rbp+4B0h+var_4B0], rax
0x1400038b6  lea     rax, [rbp+4B0h+arg_80]
0x1400038bd  mov     [rbp+4B0h+var_4A0], rax
0x1400038c1  mov     rax, [rbp+4B0h+arg_88]
0x1400038c8  mov     [rbp+4B0h+var_518], 4
0x1400038d0  mov     [rbp+4B0h+var_508], 4
0x1400038d8  mov     [rbp+4B0h+var_4F8], 4
0x1400038e0  mov     [rbp+4B0h+var_4E8], 8
0x1400038e8  mov     [rbp+4B0h+var_4D8], 8
0x1400038f0  mov     [rbp+4B0h+var_4C8], 10h
0x1400038f8  mov     [rbp+4B0h+var_4B8], 4
0x140003900  mov     [rbp+4B0h+var_4A8], 8
0x140003908  mov     [rbp+4B0h+var_498], 4
0x140003910  test    rax, rax
0x140003913  jz      loc_14000413C
0x140003919  mov     r8, rcx
0x14000391c  inc     r8
0x14000391f  cmp     [rax+r8*2], r9w
0x140003924  jnz     short loc_14000391C
0x140003926  lea     r8d, ds:2[r8*2]
0x14000392e  test    rax, rax
0x140003931  mov     [rbp+4B0h+var_488], r8d
0x140003935  lea     rbx, aNull_0; "NULL"
0x14000393c  mov     [rbp+4B0h+var_484], r9d
0x140003940  cmovz   rax, rbx
0x140003944  mov     [rbp+4B0h+var_490], rax
0x140003948  mov     rax, [rbp+4B0h+arg_90]
0x14000394f  test    rax, rax
0x140003952  jz      loc_140004144
0x140003958  mov     r8, rcx
0x14000395b  inc     r8
0x14000395e  cmp     [rax+r8*2], r9w
0x140003963  jnz     short loc_14000395B
0x140003965  lea     r8d, ds:2[r8*2]
0x14000396d  test    rax, rax
0x140003970  mov     [rbp+4B0h+var_478], r8d
0x140003974  mov     [rbp+4B0h+var_474], r9d
0x140003978  cmovz   rax, rbx
0x14000397c  mov     [rbp+4B0h+var_480], rax
0x140003980  mov     rax, [rbp+4B0h+arg_98]
0x140003987  test    rax, rax
0x14000398a  jz      loc_140004163
0x140003990  mov     r8, rcx
0x140003993  inc     r8
0x140003996  cmp     [rax+r8*2], r9w
0x14000399b  jnz     short loc_140003993
0x14000399d  lea     r8d, ds:2[r8*2]
0x1400039a5  test    rax, rax
0x1400039a8  mov     [rbp+4B0h+var_468], r8d
0x1400039ac  mov     [rbp+4B0h+var_464], r9d
0x1400039b0  cmovz   rax, rbx
0x1400039b4  mov     [rbp+4B0h+var_470], rax
0x1400039b8  mov     rax, [rbp+4B0h+arg_A0]
0x1400039bf  test    rax, rax
0x1400039c2  jz      loc_14000414C
0x1400039c8  mov     r8, rcx
0x1400039cb  inc     r8
0x1400039ce  cmp     [rax+r8*2], r9w
0x1400039d3  jnz     short loc_1400039CB
0x1400039d5  lea     r8d, ds:2[r8*2]
0x1400039dd  test    rax, rax
0x1400039e0  mov     [rbp+4B0h+var_458], r8d
0x1400039e4  mov     [rbp+4B0h+var_454], r9d
0x1400039e8  cmovz   rax, rbx
0x1400039ec  mov     [rbp+4B0h+var_460], rax
0x1400039f0  mov     rax, [rbp+4B0h+arg_A8]
0x1400039f7  test    rax, rax
0x1400039fa  jz      loc_14000415B
0x140003a00  mov     r8, rcx
0x140003a03  inc     r8
0x140003a06  cmp     [rax+r8*2], r9w
0x140003a0b  jnz     short loc_140003A03
0x140003a0d  lea     r8d, ds:2[r8*2]
0x140003a15  test    rax, rax
0x140003a18  mov     [rbp+4B0h+var_448], r8d
0x140003a1c  mov     r8, [rbp+4B0h+arg_B0]
0x140003a23  cmovz   rax, rbx
0x140003a27  mov     [rbp+4B0h+var_444], r9d
0x140003a2b  mov     [rbp+4B0h+var_450], rax
0x140003a2f  test    r8, r8
0x140003a32  jz      loc_140004154
0x140003a38  mov     rax, rcx
0x140003a3b  inc     rax
0x140003a3e  cmp     [r8+rax*2], r9w
0x140003a43  jnz     short loc_140003A3B
0x140003a45  lea     eax, ds:2[rax*2]
0x140003a4c  mov     [rbp+4B0h+var_438], eax
0x140003a4f  test    r8, r8
0x140003a52  lea     rax, [rbp+4B0h+arg_B8]
0x140003a59  mov     [rbp+4B0h+var_434], r9d
0x140003a5d  mov     [rbp+4B0h+var_430], rax
0x140003a64  cmovz   r8, rbx
0x140003a68  lea     rax, [rbp+4B0h+arg_C0]
0x140003a6f  mov     [rbp+4B0h+var_440], r8
0x140003a73  mov     [rbp+4B0h+var_420], rax
0x140003a7a  lea     rax, [rbp+4B0h+arg_C8]
0x140003a81  mov     [rbp+4B0h+var_410], rax
0x140003a88  lea     rax, [rbp+4B0h+arg_D0]
0x140003a8f  mov     [rbp+4B0h+var_400], rax
0x140003a96  lea     rax, [rbp+4B0h+arg_D8]
0x140003a9d  mov     [rbp+4B0h+var_3F0], rax
0x140003aa4  lea     rax, [rbp+4B0h+arg_E0]
0x140003aab  mov     [rbp+4B0h+var_3E0], rax
0x140003ab2  lea     rax, [rbp+4B0h+arg_E8]
0x140003ab9  mov     [rbp+4B0h+var_3D0], rax
0x140003ac0  lea     rax, [rbp+4B0h+arg_F0]
0x140003ac7  mov     [rbp+4B0h+var_3C0], rax
0x140003ace  lea     rax, [rbp+4B0h+arg_F8]
0x140003ad5  mov     [rbp+4B0h+var_3B0], rax
0x140003adc  lea     rax, [rbp+4B0h+arg_100]
0x140003ae3  mov     [rbp+4B0h+var_3A0], rax
0x140003aea  lea     rax, [rbp+4B0h+arg_108]
0x140003af1  mov     [rbp+4B0h+var_390], rax
0x140003af8  mov     rax, [rbp+4B0h+arg_110]
0x140003aff  mov     [rbp+4B0h+var_380], rax
0x140003b06  mov     rax, [rbp+4B0h+arg_118]
0x140003b0d  mov     [rbp+4B0h+var_370], rax
0x140003b14  mov     rax, [rbp+4B0h+arg_120]
0x140003b1b  mov     [rbp+4B0h+var_360], rax
0x140003b22  mov     rax, [rbp+4B0h+arg_128]
0x140003b29  mov     [rbp+4B0h+var_350], rax
0x140003b30  lea     rax, [rbp+4B0h+arg_130]
0x140003b37  mov     [rbp+4B0h+var_340], rax
0x140003b3e  lea     rax, [rbp+4B0h+arg_138]
0x140003b45  mov     [rbp+4B0h+var_330], rax
0x140003b4c  lea     rax, [rbp+4B0h+arg_140]
0x140003b53  mov     [rbp+4B0h+var_320], rax
0x140003b5a  lea     rax, [rbp+4B0h+arg_148]
0x140003b61  mov     [rbp+4B0h+var_310], rax
0x140003b68  lea     rax, [rbp+4B0h+arg_150]
0x140003b6f  mov     [rbp+4B0h+var_300], rax
0x140003b76  lea     rax, [rbp+4B0h+arg_158]
0x140003b7d  mov     [rbp+4B0h+var_2F0], rax
0x140003b84  lea     rax, [rbp+4B0h+arg_160]
0x140003b8b  mov     [rbp+4B0h+var_2E0], rax
0x140003b92  mov     rax, [rbp+4B0h+arg_168]
0x140003b99  mov     [rbp+4B0h+var_2D0], rax
0x140003ba0  mov     eax, [rbp+4B0h+arg_160]
0x140003ba6  mov     [rbp+4B0h+var_2C8], eax
0x140003bac  lea     rax, [rbp+4B0h+arg_170]
0x140003bb3  mov     [rbp+4B0h+var_2C0], rax
0x140003bba  lea     rax, [rbp+4B0h+arg_178]
0x140003bc1  mov     [rbp+4B0h+var_2B0], rax
0x140003bc8  mov     [rbp+4B0h+var_428], 4
0x140003bd3  mov     [rbp+4B0h+var_418], 4
0x140003bde  mov     [rbp+4B0h+var_408], 4
0x140003be9  mov     [rbp+4B0h+var_3F8], 4
0x140003bf4  mov     [rbp+4B0h+var_3E8], 4
0x140003bff  mov     [rbp+4B0h+var_3D8], 4
0x140003c0a  mov     [rbp+4B0h+var_3C8], 4
0x140003c15  mov     [rbp+4B0h+var_3B8], 4
0x140003c20  mov     [rbp+4B0h+var_3A8], 4
0x140003c2b  mov     [rbp+4B0h+var_398], 8
0x140003c36  mov     [rbp+4B0h+var_388], 4
0x140003c41  mov     [rbp+4B0h+var_378], 10h
0x140003c4c  mov     [rbp+4B0h+var_368], 10h
0x140003c57  mov     [rbp+4B0h+var_358], 10h
0x140003c62  mov     [rbp+4B0h+var_348], 10h
0x140003c6d  mov     [rbp+4B0h+var_338], 4
0x140003c78  mov     [rbp+4B0h+var_328], 1
0x140003c83  mov     [rbp+4B0h+var_318], 4
0x140003c8e  mov     [rbp+4B0h+var_308], 4
0x140003c99  mov     [rbp+4B0h+var_2F8], 4
0x140003ca4  mov     [rbp+4B0h+var_2E8], 4
0x140003caf  mov     [rbp+4B0h+var_2D8], 4
0x140003cba  mov     [rbp+4B0h+var_2C4], r9d
0x140003cc1  mov     [rbp+4B0h+var_2B8], 4
0x140003ccc  lea     rax, [rbp+4B0h+arg_180]
0x140003cd3  mov     [rbp+4B0h+var_2A8], 4
0x140003cde  mov     [rbp+4B0h+var_2A0], rax
0x140003ce5  lea     rax, [rbp+4B0h+arg_188]
0x140003cec  mov     [rbp+4B0h+var_290], rax
0x140003cf3  lea     rax, [rbp+4B0h+arg_190]
0x140003cfa  mov     [rbp+4B0h+var_280], rax
0x140003d01  lea     rax, [rbp+4B0h+arg_198]
0x140003d08  mov     [rbp+4B0h+var_270], rax
0x140003d0f  lea     rax, [rbp+4B0h+arg_1A0]
0x140003d16  mov     [rbp+4B0h+var_260], rax
0x140003d1d  lea     rax, [rbp+4B0h+arg_1A8]
0x140003d24  mov     [rbp+4B0h+var_250], rax
0x140003d2b  lea     rax, [rbp+4B0h+arg_1B0]
0x140003d32  mov     [rbp+4B0h+var_240], rax
0x140003d39  lea     rax, [rbp+4B0h+arg_1B8]
0x140003d40  mov     [rbp+4B0h+var_230], rax
0x140003d47  lea     rax, [rbp+4B0h+arg_1C0]
0x140003d4e  mov     [rbp+4B0h+var_220], rax
0x140003d55  lea     rax, [rbp+4B0h+arg_1C8]
0x140003d5c  mov     [rbp+4B0h+var_210], rax
0x140003d63  lea     rax, [rbp+4B0h+arg_1D0]
0x140003d6a  mov     [rbp+4B0h+var_200], rax
0x140003d71  lea     rax, [rbp+4B0h+arg_1D8]
0x140003d78  mov     [rbp+4B0h+var_1F0], rax
0x140003d7f  lea     rax, [rbp+4B0h+arg_1E0]
0x140003d86  mov     [rbp+4B0h+var_1E0], rax
0x140003d8d  lea     rax, [rbp+4B0h+arg_1E8]
0x140003d94  mov     [rbp+4B0h+var_1D0], rax
0x140003d9b  lea     rax, [rbp+4B0h+arg_1F0]
0x140003da2  mov     [rbp+4B0h+var_1C0], rax
0x140003da9  lea     rax, [rbp+4B0h+arg_1F8]
0x140003db0  mov     [rbp+4B0h+var_1B0], rax
0x140003db7  lea     rax, [rbp+4B0h+arg_200]
0x140003dbe  mov     [rbp+4B0h+var_1A0], rax
0x140003dc5  lea     rax, [rbp+4B0h+arg_208]
0x140003dcc  mov     [rbp+4B0h+var_190], rax
0x140003dd3  lea     rax, [rbp+4B0h+arg_210]
0x140003dda  mov     [rbp+4B0h+var_180], rax
0x140003de1  lea     rax, [rbp+4B0h+arg_218]
0x140003de8  mov     [rbp+4B0h+var_170], rax
0x140003def  lea     rax, [rbp+4B0h+arg_220]
0x140003df6  mov     [rbp+4B0h+var_160], rax
0x140003dfd  lea     rax, [rbp+4B0h+arg_228]
0x140003e04  mov     [rbp+4B0h+var_150], rax
0x140003e0b  lea     rax, [rbp+4B0h+arg_230]
0x140003e12  mov     [rbp+4B0h+var_140], rax
0x140003e19  mov     rax, [rbp+4B0h+arg_238]
0x140003e20  mov     [rbp+4B0h+var_298], 4
0x140003e2b  mov     [rbp+4B0h+var_288], 4
0x140003e36  mov     [rbp+4B0h+var_278], 4
0x140003e41  mov     [rbp+4B0h+var_268], 4
0x140003e4c  mov     [rbp+4B0h+var_258], 4
0x140003e57  mov     [rbp+4B0h+var_248], 4
0x140003e62  mov     [rbp+4B0h+var_238], 4
0x140003e6d  mov     [rbp+4B0h+var_228], 4
0x140003e78  mov     [rbp+4B0h+var_218], 4
0x140003e83  mov     [rbp+4B0h+var_208], 4
0x140003e8e  mov     [rbp+4B0h+var_1F8], 4
0x140003e99  mov     [rbp+4B0h+var_1E8], 8
0x140003ea4  mov     [rbp+4B0h+var_1D8], 8
0x140003eaf  mov     [rbp+4B0h+var_1C8], 4
0x140003eba  mov     [rbp+4B0h+var_1B8], 4
0x140003ec5  mov     [rbp+4B0h+var_1A8], 4
0x140003ed0  mov     [rbp+4B0h+var_198], 4
0x140003edb  mov     [rbp+4B0h+var_188], 4
0x140003ee6  mov     [rbp+4B0h+var_178], 4
0x140003ef1  mov     [rbp+4B0h+var_168], 8
0x140003efc  mov     [rbp+4B0h+var_158], 4
0x140003f07  mov     [rbp+4B0h+var_148], 4
0x140003f12  mov     [rbp+4B0h+var_138], 4
0x140003f1d  test    rax, rax
0x140003f20  jnz     loc_14000416B
0x140003f26  cmovz   rax, rbx
0x140003f2a  mov     [rbp+4B0h+var_128], edx
0x140003f30  mov     [rbp+4B0h+var_130], rax
0x140003f37  xor     r8d, r8d
0x140003f3a  lea     rax, [rbp+4B0h+arg_240]
0x140003f41  mov     [rbp+4B0h+var_124], r9d
0x140003f48  mov     [rbp+4B0h+var_120], rax
0x140003f4f  mov     rdx, r10
0x140003f52  lea     rax, [rbp+4B0h+arg_248]
0x140003f59  mov     [rbp+4B0h+var_C4], r9d
0x140003f60  mov     [rbp+4B0h+var_110], rax
0x140003f67  lea     rax, [rbp+4B0h+arg_250]
0x140003f6e  mov     [rbp+4B0h+var_100], rax
0x140003f75  lea     rax, [rbp+4B0h+arg_258]
0x140003f7c  mov     [rbp+4B0h+var_F0], rax
0x140003f83  lea     rax, [rbp+4B0h+arg_260]
  ... truncated ...
```
