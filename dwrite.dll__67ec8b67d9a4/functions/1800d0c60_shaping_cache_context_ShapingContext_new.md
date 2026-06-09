# shaping_cache::context::ShapingContext::new

- ea: `0x1800d0c60`
- end: `0x1800d322a`
- name: `shaping_cache::context::ShapingContext::new`
- size: `9674`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, _QWORD *, __int16 *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800cff10`
- `0x1800d3fc0`

## callees

- `0x180065ec0`
- `0x180066440`
- `0x180066bd0`
- `0x180067680`
- `0x180067e80`
- `0x18008cb20`
- `0x18008f220`
- `0x1800ce190`
- `0x1800ce480`
- `0x1800ce520`
- `0x1800ce7d0`
- `0x1800ce850`
- `0x1800cf650`
- `0x1800d0c60`
- `0x1800d3d40`
- `0x1800dc910`
- `0x180212f4c`
- `0x18021e1b6`
- `0x18021e1da`
- `0x180316190`
- `0x180316232`
- `0x180316255`
- `0x180316540`
- `0x180316870`
- `0x180316980`
- `0x180316a30`
- `0x180316ae0`
- `0x180316ce0`
- `0x180316d00`
- `0x180316ee0`
- `0x180319270`
- `0x180319b70`
- `0x180319c30`

## import_xrefs

- `kernel32!HeapFree` at `0x1800d15be`
- `kernel32!HeapFree` at `0x1800d16ad`
- `kernel32!HeapFree` at `0x1800d1958`
- `kernel32!HeapFree` at `0x1800d1c46`
- `kernel32!HeapFree` at `0x1800d1c69`
- `kernel32!HeapFree` at `0x1800d1de8`
- `kernel32!HeapFree` at `0x1800d1f0d`
- `kernel32!HeapFree` at `0x1800d2db2`
- `kernel32!HeapFree` at `0x1800d15be`
- `kernel32!HeapFree` at `0x1800d16ad`
- `kernel32!HeapFree` at `0x1800d1958`
- `kernel32!HeapFree` at `0x1800d1c46`
- `kernel32!HeapFree` at `0x1800d1c69`
- `kernel32!HeapFree` at `0x1800d1de8`
- `kernel32!HeapFree` at `0x1800d1f0d`
- `kernel32!HeapFree` at `0x1800d2db2`
- `kernel32!GetProcessHeap` at `0x1800d15b0`
- `kernel32!GetProcessHeap` at `0x1800d169f`
- `kernel32!GetProcessHeap` at `0x1800d194a`
- `kernel32!GetProcessHeap` at `0x1800d1c38`
- `kernel32!GetProcessHeap` at `0x1800d1c5b`
- `kernel32!GetProcessHeap` at `0x1800d1dda`
- `kernel32!GetProcessHeap` at `0x1800d1eff`
- `kernel32!GetProcessHeap` at `0x1800d2da0`
- `kernel32!GetProcessHeap` at `0x1800d15b0`
- `kernel32!GetProcessHeap` at `0x1800d169f`
- `kernel32!GetProcessHeap` at `0x1800d194a`
- `kernel32!GetProcessHeap` at `0x1800d1c38`
- `kernel32!GetProcessHeap` at `0x1800d1c5b`
- `kernel32!GetProcessHeap` at `0x1800d1dda`
- `kernel32!GetProcessHeap` at `0x1800d1eff`
- `kernel32!GetProcessHeap` at `0x1800d2da0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1800d2f2d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1800d2f3b`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1800d30e7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1800d2f2d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1800d2f3b`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressSingle` at `0x1800d30e7`

## string_xrefs

- `0x1800d1a5d`: `GSUBGPOSassertion failed: used_cache_size <= cache_buffer.len()`

## pseudocode

```c
__int64 __fastcall shaping_cache::context::ShapingContext::new(
        __int64 a1,
        unsigned __int64 a2,
        _QWORD *a3,
        __int16 *a4,
        _QWORD *a5,
        __int64 a6)
{
  __int64 v8; // r15
  float v9; // xmm8_4
  float v10; // xmm6_4
  float v11; // xmm7_4
  float v12; // xmm1_4
  _DWORD *v13; // rax
  int v14; // r9d
  unsigned __int16 v15; // ax
  int v16; // r8d
  size_t v17; // r13
  size_t v18; // r14
  __int64 v19; // rdi
  __int64 v20; // rax
  size_t v21; // rbx
  __int64 v22; // r8
  unsigned __int64 *v23; // rax
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // r15
  void *v27; // rcx
  size_t v28; // rsi
  bool v29; // cf
  __int128 *v30; // rcx
  __int128 v31; // xmm0
  int is_zero_slow_path; // eax
  float v33; // xmm6_4
  _QWORD *v34; // rsi
  unsigned __int64 v35; // r14
  __int64 v36; // rdi
  __int64 v37; // rbx
  __m128i v38; // xmm0
  __m128i v39; // xmm8
  __int64 i; // rsi
  unsigned __int64 v41; // r14
  __m128i v42; // xmm10
  int v44; // eax
  const void ***v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  char *v48; // rsi
  __int64 v49; // rcx
  __int64 v50; // rt0
  __int64 v51; // r12
  unsigned __int64 v52; // rbx
  int v53; // edi
  __int128 *v54; // r14
  char v55; // al
  __int64 v56; // rcx
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  __int64 result; // rax
  PVOID v60; // r12
  char v61; // al
  int v62; // esi
  __int64 v63; // rax
  __int128 v64; // xmm1
  __m128i si128; // xmm1
  __int64 v66; // r9
  __int64 v67; // r13
  void *v68; // rdi
  HANDLE ProcessHeap; // rax
  int engine; // r15d
  __int64 v71; // r14
  void *v72; // rdi
  HANDLE v73; // rax
  __int64 v74; // rbx
  __int64 v75; // rsi
  __int16 *v76; // rdi
  __m128i v77; // xmm0
  __m128i v78; // xmm1
  __int64 v79; // rax
  void *v80; // rsi
  unsigned __int64 v81; // rdi
  volatile signed __int64 **v82; // rbx
  HANDLE v83; // rax
  _DWORD *v84; // rax
  _DWORD *v85; // r13
  char *v86; // rsi
  __int64 v87; // rdx
  __int64 v88; // r15
  int v89; // r14d
  __int64 v90; // r14
  char v91; // si
  HANDLE v92; // rax
  HANDLE v93; // rax
  unsigned __int64 v94; // r14
  __int64 v95; // rax
  __int64 v97; // rcx
  _DWORD *v98; // rsi
  __int64 v99; // rdi
  __int64 v100; // rax
  __int64 v101; // r15
  __int64 v102; // rax
  unsigned __int64 v103; // rcx
  int v104; // r8d
  int v105; // r9d
  volatile signed __int64 *v106; // r10
  __int64 v107; // rt0
  __int64 v108; // r11
  volatile signed __int64 *v109; // rax
  volatile signed __int64 *v110; // rdi
  HANDLE v111; // rax
  __int64 v112; // rsi
  void *v113; // rdi
  size_t v114; // rbx
  __int64 v115; // r14
  volatile signed __int64 *v116; // rax
  char v118; // of
  HANDLE v119; // rax
  __int64 v120; // rt0
  signed __int8 v121; // al
  unsigned int v122; // esi
  int v124; // ebx
  char v125; // al
  __int64 v126; // rax
  __int64 v127; // rcx
  __int64 v128; // rcx
  __int64 v129; // rdx
  int v130; // r8d
  _QWORD *v131; // rsi
  unsigned __int64 v132; // r14
  __int64 v133; // rbx
  __m128i v134; // xmm0
  __m128i v135; // xmm8
  __int64 j; // rsi
  unsigned __int64 v137; // r14
  __m128i v138; // xmm10
  int v140; // eax
  volatile signed __int64 v141; // rax
  __int64 v142; // rcx
  unsigned __int64 v143; // rdi
  unsigned __int64 v144; // rbx
  int v145; // eax
  __int64 v146; // rdx
  _QWORD *v147; // rsi
  __int64 v148; // rdx
  unsigned __int128 v149; // kr00_16
  _QWORD *v150; // rbx
  char *v151; // rsi
  __int64 v152; // rax
  void *v153; // rdx
  unsigned __int64 v154; // r15
  __int64 v155; // rax
  __m128i *v156; // r13
  __int64 v157; // rdx
  __int64 v158; // rbx
  __m128i v159; // xmm0
  __m128i v160; // xmm8
  size_t v161; // r12
  __int64 v162; // r13
  void *v163; // r8
  __m128i v164; // xmm10
  int v166; // eax
  __int64 v167; // rsi
  __int64 v168; // rax
  int v169; // eax
  size_t v170; // rdi
  __int64 v171; // rsi
  __int64 v172; // rax
  unsigned __int16 v173; // r8
  char v176; // cl
  size_t v177; // rdx
  __int64 v178; // rcx
  __int64 v179; // rax
  size_t v180; // r14
  char *v181; // rax
  __int64 v182; // r12
  __m128i v183; // xmm0
  __m128i v184; // xmm8
  char *v185; // rbx
  size_t v186; // rdx
  size_t v187; // r14
  __m128i v188; // xmm10
  size_t v190; // rdi
  int v191; // eax
  const void ***v192; // rcx
  __int64 v194; // rdx
  __int64 v195; // r15
  _BYTE *v196; // rcx
  HANDLE v197; // rax
  char v198; // al
  char v200; // al
  char v202; // dl
  char *v203; // [rsp+48h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int128 v205; // [rsp+58h] [rbp-28h]
  __int64 v206; // [rsp+68h] [rbp-18h]
  __int64 v207; // [rsp+130h] [rbp+B0h] BYREF
  __int64 v208; // [rsp+210h] [rbp+190h] BYREF
  _BYTE v209[56]; // [rsp+5C0h] [rbp+540h] BYREF
  char v210; // [rsp+5F8h] [rbp+578h]
  __int16 v211; // [rsp+B40h] [rbp+AC0h] BYREF
  __int128 v212; // [rsp+B42h] [rbp+AC2h]
  _BYTE v213[30]; // [rsp+B52h] [rbp+AD2h]
  volatile signed __int64 *v214; // [rsp+B70h] [rbp+AF0h]
  unsigned __int64 v215; // [rsp+B78h] [rbp+AF8h]
  _QWORD *v216; // [rsp+B80h] [rbp+B00h]
  float v217; // [rsp+B88h] [rbp+B08h]
  float v218; // [rsp+B8Ch] [rbp+B0Ch]
  _BYTE v219[32]; // [rsp+B90h] [rbp+B10h] BYREF
  int v220; // [rsp+BB0h] [rbp+B30h]
  int v221; // [rsp+BD8h] [rbp+B58h]
  int v222; // [rsp+C00h] [rbp+B80h]
  int v223; // [rsp+C28h] [rbp+BA8h]
  int v224; // [rsp+C50h] [rbp+BD0h]
  int v225; // [rsp+C78h] [rbp+BF8h]
  int v226; // [rsp+CA0h] [rbp+C20h]
  _QWORD *v227; // [rsp+CA8h] [rbp+C28h]
  __int64 v228; // [rsp+CB0h] [rbp+C30h]
  __int128 v229; // [rsp+CB8h] [rbp+C38h]
  __int128 v230; // [rsp+CC8h] [rbp+C48h]
  __int64 v231; // [rsp+CD8h] [rbp+C58h]
  int v232; // [rsp+CE0h] [rbp+C60h]
  int v233; // [rsp+CE4h] [rbp+C64h]
  unsigned __int8 v234; // [rsp+CE8h] [rbp+C68h]
  __m128i v235; // [rsp+CF0h] [rbp+C70h] BYREF
  __m128i v236; // [rsp+D00h] [rbp+C80h] BYREF
  __int128 v237; // [rsp+D10h] [rbp+C90h]
  __int128 v238; // [rsp+D20h] [rbp+CA0h]
  __int128 v239; // [rsp+D30h] [rbp+CB0h] BYREF
  __int128 v240; // [rsp+D40h] [rbp+CC0h]
  __int128 v241; // [rsp+D50h] [rbp+CD0h]
  __int128 v242; // [rsp+D60h] [rbp+CE0h]
  _BYTE v243[36]; // [rsp+D70h] [rbp+CF0h] BYREF
  __int128 v244; // [rsp+D94h] [rbp+D14h]
  __int128 v245; // [rsp+DA4h] [rbp+D24h]
  __m128i v246; // [rsp+DB4h] [rbp+D34h]
  __m128i v247; // [rsp+DC4h] [rbp+D44h]
  __int128 v248; // [rsp+DD4h] [rbp+D54h]
  __int128 v249; // [rsp+DE4h] [rbp+D64h]
  __int16 v250; // [rsp+DF4h] [rbp+D74h]
  __int64 v251; // [rsp+DF6h] [rbp+D76h]
  int v252; // [rsp+DFEh] [rbp+D7Eh]
  __int16 v253; // [rsp+E02h] [rbp+D82h]
  __int64 v254; // [rsp+E04h] [rbp+D84h]
  int v255; // [rsp+E0Ch] [rbp+D8Ch]
  bool v256; // [rsp+E10h] [rbp+D90h]
  bool v257; // [rsp+E11h] [rbp+D91h]
  bool v258; // [rsp+E12h] [rbp+D92h]
  bool v259; // [rsp+E13h] [rbp+D93h]
  __int128 v260; // [rsp+E14h] [rbp+D94h]
  __int64 v261; // [rsp+E24h] [rbp+DA4h]
  __int128 v262; // [rsp+E30h] [rbp+DB0h]
  _BYTE v263[30]; // [rsp+E40h] [rbp+DC0h] BYREF
  __int16 *v264; // [rsp+E60h] [rbp+DE0h]
  __int64 (__fastcall **v265)(); // [rsp+E68h] [rbp+DE8h]
  __int16 v266; // [rsp+E70h] [rbp+DF0h]
  char v267; // [rsp+E72h] [rbp+DF2h]
  __int64 v268; // [rsp+E78h] [rbp+DF8h]
  _WORD v269[24]; // [rsp+E80h] [rbp+E00h] BYREF
  __int64 v270; // [rsp+EB0h] [rbp+E30h]
  unsigned __int64 v271; // [rsp+EB8h] [rbp+E38h]
  __int64 v272; // [rsp+EC0h] [rbp+E40h]
  char *v273; // [rsp+EC8h] [rbp+E48h]
  __int64 v274; // [rsp+ED0h] [rbp+E50h] BYREF
  LPVOID v275; // [rsp+ED8h] [rbp+E58h]
  __int64 v276; // [rsp+EE0h] [rbp+E60h]
  _QWORD *v277; // [rsp+EE8h] [rbp+E68h]
  volatile signed __int64 *v278[3]; // [rsp+EF0h] [rbp+E70h] BYREF
  int v279; // [rsp+F0Ch] [rbp+E8Ch]
  int v280; // [rsp+F10h] [rbp+E90h]
  int v281; // [rsp+F14h] [rbp+E94h]
  __int64 v282; // [rsp+F18h] [rbp+E98h] BYREF
  LPVOID v283; // [rsp+F20h] [rbp+EA0h]
  unsigned __int64 v284; // [rsp+F28h] [rbp+EA8h]
  __int128 *v285; // [rsp+F30h] [rbp+EB0h]
  size_t v286; // [rsp+F38h] [rbp+EB8h]
  size_t v287; // [rsp+F40h] [rbp+EC0h]
  char *v288; // [rsp+F48h] [rbp+EC8h]
  void *v289; // [rsp+F50h] [rbp+ED0h]
  unsigned __int64 v290; // [rsp+F58h] [rbp+ED8h]
  __int64 v291; // [rsp+F60h] [rbp+EE0h]
  int v292; // [rsp+F6Ch] [rbp+EECh]
  void *Src; // [rsp+F70h] [rbp+EF0h]
  PVOID Address; // [rsp+F78h] [rbp+EF8h]
  void *Buf1; // [rsp+F80h] [rbp+F00h]
  size_t Size; // [rsp+F88h] [rbp+F08h]
  unsigned __int8 v297; // [rsp+F93h] [rbp+F13h]
  char v298; // [rsp+F94h] [rbp+F14h]
  char v299; // [rsp+F95h] [rbp+F15h]
  char v300; // [rsp+F96h] [rbp+F16h]
  char v301; // [rsp+F97h] [rbp+F17h]
  __int64 v302; // [rsp+F98h] [rbp+F18h]

  v302 = -2;
  _R12 = a2;
  v272 = a1;
  v277 = a3;
  v8 = *a3;
  memset(v209, 0, 48);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 208LL))(v8, v209);
  v262 = *(_OWORD *)&v209[2];
  *(_OWORD *)v263 = *(_OWORD *)&v209[18];
  *(_OWORD *)&v263[14] = *(_OWORD *)&v209[32];
  v279 = *(unsigned __int16 *)v209;
  v9 = (float)*(unsigned __int16 *)v209;
  v10 = *((float *)a4 + 2);
  v11 = FLOAT_1_0;
  if ( *((_DWORD *)a4 + 1) )
  {
    LODWORD(v12) = *((_DWORD *)a4 + 5) & _xmm;
    if ( v12 >= 0.000015258789 )
    {
      if ( COERCE_FLOAT(*((_DWORD *)a4 + 4) & _xmm) >= 0.000015258789
        || COERCE_FLOAT(*((_DWORD *)a4 + 7) & _xmm) >= 0.000015258789 )
      {
        goto LABEL_10;
      }
      v13 = a4 + 12;
    }
    else
    {
      if ( COERCE_FLOAT(*((_DWORD *)a4 + 6) & _xmm) >= 0.000015258789 )
        goto LABEL_10;
      v13 = a4 + 14;
      LODWORD(v12) = *((_DWORD *)a4 + 4) & _xmm;
    }
    if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(v12 - COERCE_FLOAT(*v13 & _xmm)) & _xmm) < 0.000015258789 )
      v11 = (float)((float)(*((float *)a4 + 3) * v10) * v12) / v9;
  }
LABEL_10:
  v297 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 136LL))(v8);
  v15 = *a4;
  v16 = 0;
  if ( *a4 == 1 && *((_BYTE *)a4 + 2) == 1 )
  {
    v16 = 26;
LABEL_13:
    v14 = 0;
  }
  else
  {
    LOBYTE(v14) = 1;
    switch ( (char)v15 )
    {
      case 3:
        v16 = 22;
        goto LABEL_13;
      case 4:
        v16 = 5;
        goto LABEL_13;
      case 6:
        v16 = 57;
        goto LABEL_13;
      case 8:
        v16 = 58;
        goto LABEL_13;
      case 9:
        v16 = 40;
        goto LABEL_13;
      case 10:
        v16 = 11;
        goto LABEL_13;
      case 11:
        v16 = 59;
        goto LABEL_13;
      case 12:
        v16 = 17;
        goto LABEL_13;
      case 13:
        v16 = 55;
        goto LABEL_13;
      case 14:
        v16 = 60;
        goto LABEL_13;
      case 15:
        v16 = 15;
        goto LABEL_13;
      case 17:
        v16 = 62;
        goto LABEL_13;
      case 18:
        v16 = 16;
        goto LABEL_13;
      case 22:
        v16 = 3;
        goto LABEL_13;
      case 24:
        v16 = 38;
        goto LABEL_13;
      case 25:
        v16 = 91;
        goto LABEL_13;
      case 26:
        v16 = 14;
        goto LABEL_13;
      case 27:
        v16 = 6;
        goto LABEL_13;
      case 30:
        v16 = 4;
        goto LABEL_13;
      case 31:
        v16 = 43;
        goto LABEL_13;
      case 32:
        v16 = 42;
        goto LABEL_13;
      case 33:
        v16 = 10;
        goto LABEL_13;
      case 34:
        v16 = 37;
        goto LABEL_13;
      case 35:
        v16 = 63;
        goto LABEL_13;
      case 36:
        v16 = 24;
        goto LABEL_13;
      case 37:
      case 44:
        v16 = 9;
        goto LABEL_13;
      case 41:
        v16 = 56;
        goto LABEL_13;
      case 42:
        v16 = 64;
        goto LABEL_13;
      case 43:
        v16 = 47;
        goto LABEL_13;
      case 45:
        v16 = 65;
        goto LABEL_13;
      case 46:
        v16 = 66;
        goto LABEL_13;
      case 47:
        v16 = 27;
        goto LABEL_13;
      case 48:
        v16 = 34;
        goto LABEL_13;
      case 49:
        v16 = 2;
        goto LABEL_13;
      case 50:
        v16 = 67;
        goto LABEL_13;
      case 51:
        v16 = 68;
        goto LABEL_13;
      case 53:
        v16 = 51;
        goto LABEL_13;
      case 56:
        v16 = 48;
        goto LABEL_13;
      case 57:
        v16 = 92;
        goto LABEL_13;
      case 58:
        v16 = 69;
        goto LABEL_13;
      case 59:
        v16 = 20;
        goto LABEL_13;
      case 60:
        v16 = 36;
        goto LABEL_13;
      case 61:
        v16 = 32;
        goto LABEL_13;
      case 62:
        v16 = 54;
        goto LABEL_13;
      case 63:
        v16 = 19;
        goto LABEL_13;
      case 69:
        v16 = 45;
        goto LABEL_13;
      case 71:
        v16 = 21;
        goto LABEL_13;
      case 73:
        v16 = 70;
        goto LABEL_13;
      case 74:
        v16 = 18;
        goto LABEL_13;
      case 76:
        v16 = 71;
        goto LABEL_13;
      case 78:
        v16 = 28;
        goto LABEL_13;
      case 79:
        v16 = 73;
        goto LABEL_13;
      case 80:
        v16 = 74;
        goto LABEL_13;
      case 81:
        v16 = 23;
        goto LABEL_13;
      case 82:
        v16 = 75;
        goto LABEL_13;
      case 83:
        v16 = 76;
        goto LABEL_13;
      case 84:
        v16 = 30;
        goto LABEL_13;
      case 85:
        v16 = 77;
        goto LABEL_13;
      case 86:
        v16 = 78;
        goto LABEL_13;
      case 87:
        v16 = 39;
        goto LABEL_13;
      case 88:
        v16 = 46;
        goto LABEL_13;
      case 89:
        v16 = 31;
        goto LABEL_13;
      case 90:
        v16 = 33;
        goto LABEL_13;
      case 91:
        v16 = 29;
        goto LABEL_13;
      case 92:
        v16 = 53;
        goto LABEL_13;
      case 95:
        v16 = 12;
        goto LABEL_13;
      case 96:
        v16 = 61;
        goto LABEL_13;
      case 99:
        v16 = 106;
        goto LABEL_13;
      case 100:
        v16 = 72;
        goto LABEL_13;
      case 102:
        v16 = 79;
        goto LABEL_13;
      case 105:
        v16 = 90;
        goto LABEL_13;
      case 107:
        v16 = 85;
        goto LABEL_13;
      case 108:
        v16 = 83;
        goto LABEL_13;
      case 109:
        v16 = 84;
        goto LABEL_13;
      case 111:
        v16 = 82;
        goto LABEL_13;
      case 112:
        v16 = 80;
        goto LABEL_13;
      case 114:
        v16 = 88;
        goto LABEL_13;
      case 119:
        v16 = 89;
        goto LABEL_13;
      case 122:
        v16 = 81;
        goto LABEL_13;
      case 123:
        v16 = 87;
        goto LABEL_13;
      case 124:
        v16 = 86;
        goto LABEL_13;
      case 126:
        v16 = 93;
        goto LABEL_13;
      case 127:
        v16 = 113;
        goto LABEL_13;
      case -127:
        v16 = 94;
        goto LABEL_13;
      case -125:
        v16 = 95;
        goto LABEL_13;
      case -124:
        v16 = 97;
        goto LABEL_13;
      case -123:
        v16 = 96;
        goto LABEL_13;
      case -118:
        v16 = 98;
        goto LABEL_13;
      case -116:
        v16 = 99;
        goto LABEL_13;
      case -115:
        v16 = 100;
        goto LABEL_13;
      case -114:
        v16 = 114;
        goto LABEL_13;
      case -113:
        v16 = 115;
        goto LABEL_13;
      case -112:
        v16 = 101;
        goto LABEL_13;
      case -111:
        v16 = 102;
        goto LABEL_13;
      case -110:
        v16 = 103;
        goto LABEL_13;
      case -109:
        v16 = 104;
        goto LABEL_13;
      case -108:
        v16 = 116;
        goto LABEL_13;
      case -107:
        v16 = 105;
        goto LABEL_13;
      case -106:
        v16 = 107;
        goto LABEL_13;
      case -105:
        v16 = 108;
        goto LABEL_13;
      case -104:
        v16 = 109;
        goto LABEL_13;
      case -103:
        v16 = 110;
        goto LABEL_13;
      case -102:
        v16 = 111;
        goto LABEL_13;
      case -101:
        v16 = 112;
        goto LABEL_13;
      case -100:
        v16 = 117;
        goto LABEL_13;
      case -99:
        v16 = 118;
        goto LABEL_13;
      case -98:
        v16 = 119;
        goto LABEL_13;
      case -97:
        v16 = 120;
        goto LABEL_13;
      case -96:
        v16 = 121;
        goto LABEL_13;
      case -95:
        v16 = 122;
        goto LABEL_13;
      case -94:
        v16 = 123;
        goto LABEL_13;
      case -93:
        v16 = 124;
        goto LABEL_13;
      case -92:
        v16 = 125;
        goto LABEL_13;
      case -91:
        v16 = 126;
        goto LABEL_13;
      case -90:
        v16 = 127;
        goto LABEL_13;
      case -89:
        v16 = 128;
        goto LABEL_13;
      case -88:
        v16 = 129;
        goto LABEL_13;
      case -87:
        v16 = 130;
        goto LABEL_13;
      case -86:
        v16 = 131;
        goto LABEL_13;
      case -85:
        v16 = 132;
        goto LABEL_13;
      case -84:
        v16 = 133;
        goto LABEL_13;
      case -83:
        v16 = 134;
        goto LABEL_13;
      case -82:
        v16 = 135;
        goto LABEL_13;
      default:
        break;
    }
  }
  LODWORD(v289) = v14;
  v292 = v16;
  if ( v15 >= 0xAFu )
    v15 = 0;
  v280 = HIDWORD(qword_180404390[4 * (unsigned int)v15 + 2]);
  memset(v209, 0, 32);
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 32LL))(v8, v209);
  v17 = *(_QWORD *)&v209[8];
  v18 = *(_QWORD *)&v209[24];
  v19 = 1;
  v20 = 1;
  if ( *(_QWORD *)&v209[24] )
    v20 = *(_QWORD *)&v209[16];
  if ( *(_QWORD *)&v209[8] )
    v19 = *(_QWORD *)v209;
  v21 = *(_QWORD *)&v209[8] + 72LL;
  v22 = *(_QWORD *)&v209[24] + *(_QWORD *)&v209[8] + 72LL;
  if ( v22 < 0 )
    goto LABEL_89;
  Src = (void *)v20;
  v285 = (__int128 *)a4;
  v23 = *(unsigned __int64 **)(a6 + 16);
  v24 = v23[4];
  Size = *(_QWORD *)&v209[24] + *(_QWORD *)&v209[8] + 72LL;
  if ( v22 > v24 || (v25 = v24 - v22, v25 < *v23) )
  {
    v26 = _R12;
    v25 = bumpalo::Bump::alloc_layout_slow(a6, 1);
    if ( v25 )
      goto LABEL_24;
LABEL_89:
    bumpalo::oom();
  }
  v26 = _R12;
  v23[4] = v25;
LABEL_24:
  if ( Size )
  {
    v27 = (void *)v25;
    _R12 = v25;
    v28 = Size;
    memset_0(v27, 0, Size);
    v29 = v28 < 0x48;
    v25 = _R12;
    if ( !v29 )
    {
      v30 = v285;
      *(_QWORD *)(_R12 + 32) = *((_QWORD *)v285 + 4);
      v31 = *v30;
      *(_OWORD *)(_R12 + 16) = v30[1];
      *(_OWORD *)_R12 = v31;
      *(_QWORD *)(_R12 + 40) = v21;
      *(_QWORD *)(_R12 + 48) = v18;
      *(_QWORD *)(_R12 + 56) = 72;
      *(_QWORD *)(_R12 + 64) = v17;
    }
  }
  if ( v17 > 0xFFFFFFFFFFFFFFB7uLL )
    core::slice::index::slice_index_order_fail(72, v17 + 72, &off_180343028);
  if ( v21 > Size )
    core::slice::index::slice_end_index_len_fail(v17 + 72, Size, &off_180343028);
  memcpy_0((void *)(v25 + 72), (const void *)v19, v17);
  memcpy_0((void *)(v25 + v21), Src, v18);
  if ( _InterlockedCompareExchange8((volatile signed __int8 *)v26, 1, 0) )
    std::sys::sync::mutex::futex::Mutex::lock_contended((volatile void *)v26);
  if ( 2 * qword_1804B1950 )
  {
    is_zero_slow_path = std::panicking::panic_count::is_zero_slow_path();
    LOBYTE(is_zero_slow_path) = is_zero_slow_path ^ 1;
  }
  else
  {
    is_zero_slow_path = 0;
  }
  if ( *(_BYTE *)(v26 + 1) )
  {
    *(_QWORD *)v209 = v26;
    v209[8] = is_zero_slow_path;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)v209,
      (unsigned int)&off_180342FA0,
      (__int64)&off_180343058);
  }
  LODWORD(Buf1) = is_zero_slow_path;
  Src = (void *)v25;
  v33 = v10 / (float)(v9 * v11);
  Address = (PVOID)v26;
  if ( *(_QWORD *)(v26 + 32) )
  {
    v34 = Address;
    *(_QWORD *)&v209[16] = *((_QWORD *)Address + 5);
    *(_OWORD *)v209 = 0;
    v210 = 0;
    *(_OWORD *)&v209[24] = xmmword_1804B1900;
    *(_OWORD *)&v209[40] = xmmword_1804B1910;
    core::hash::impls::impl_4::hash_u8_foldhash::fast::FoldHasher_(Src, Size, v209);
    if ( v210 )
      v35 = ((*(_QWORD *)v209 ^ *(_QWORD *)&v209[16]) * (*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24]))
          ^ (((unsigned __int64)(*(_QWORD *)v209 ^ *(_QWORD *)&v209[16])
            * (unsigned __int128)(unsigned __int64)(*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24])) >> 64);
    else
      v35 = *(_QWORD *)&v209[16];
    v36 = v34[1];
    v37 = v34[2];
    v38 = _mm_cvtsi32_si128(v35 >> 57);
    v39 = _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v38, v38), 0), 0);
    for ( i = 0; ; i += 16 )
    {
      v41 = v37 & v35;
      v42 = _mm_loadu_si128((const __m128i *)(v36 + v41));
      _R13D = _mm_movemask_epi8(_mm_cmpeq_epi8(v42, v39));
      if ( _R13D )
        break;
LABEL_42:
      if ( _mm_movemask_epi8(_mm_cmpeq_epi8(v42, (__m128i)-1LL)) )
        goto LABEL_53;
      v35 = i + v41 + 16;
    }
    while ( 1 )
    {
      __asm { tzcnt   r12d, r13d }
      _R12 = v37 & (v41 + _R12);
      v45 = (const void ***)(v36 - 16 - 16 * _R12);
      if ( (const void *)Size == (*v45)[1] && !memcmp_0(Src, **v45, Size) )
        break;
      v44 = _R13D - 1;
      LOWORD(v44) = _R13D & (_R13D - 1);
      _R13D = v44;
      if ( !(_WORD)v44 )
        goto LABEL_42;
    }
    v46 = *(_QWORD *)(v36 - 16 * _R12 - 8);
    v47 = *(_QWORD *)(v46 + 48);
    *(_QWORD *)(*(_QWORD *)(v46 + 40) + 48LL) = v47;
    *(_QWORD *)(v47 + 40) = *(_QWORD *)(v46 + 40);
    v48 = (char *)Address;
    v49 = *((_QWORD *)Address + 7);
    *(_QWORD *)(v46 + 48) = *(_QWORD *)(v49 + 48);
    *(_QWORD *)(v46 + 40) = v49;
    *(_QWORD *)(v49 + 48) = v46;
    *(_QWORD *)(*(_QWORD *)(v46 + 48) + 40LL) = v46;
    v50 = _InterlockedIncrement64(*(volatile signed __int64 **)(v46 + 16));
    if ( !((v50 < 0) ^ v118 | (v50 == 0)) )
    {
      v51 = *(_QWORD *)(v46 + 16);
      v52 = *(_QWORD *)(v46 + 24);
      v53 = *(_DWORD *)(v46 + 32);
      v54 = v285;
      if ( !(_BYTE)Buf1 && 2 * qword_1804B1950 && !(unsigned __int8)std::panicking::panic_count::is_zero_slow_path() )
        v48[1] = 1;
      v55 = *v48;
      *v48 = 0;
      if ( v55 == 2 )
        WakeByAddressSingle(v48);
      goto LABEL_52;
    }
LABEL_375:
    BUG();
  }
LABEL_53:
  if ( !(_BYTE)Buf1 && 2 * qword_1804B1950 && !(unsigned __int8)std::panicking::panic_count::is_zero_slow_path() )
    *((_BYTE *)Address + 1) = 1;
  v60 = Address;
  v61 = *(_BYTE *)Address;
  *(_BYTE *)Address = 0;
  v62 = v292;
  if ( v61 == 2 )
    WakeByAddressSingle(v60);
  v63 = std::sys::alloc::windows::process_heap_alloc(0, 16);
  if ( !v63 )
  {
    v299 = 0;
    alloc::alloc::handle_alloc_error(8, 16);
  }
  *(_QWORD *)v63 = 1;
  *(_QWORD *)(v63 + 8) = 1;
  v227 = v277;
  v64 = v285[1];
  v229 = *v285;
  v230 = v64;
  v231 = *((_QWORD *)v285 + 4);
  v216 = a5;
  v211 = v279;
  si128 = _mm_load_si128((const __m128i *)v263);
  v212 = v262;
  *(__m128i *)v213 = si128;
  *(__m128i *)&v213[14] = _mm_loadu_si128((const __m128i *)&v263[14]);
  v217 = v11;
  v218 = v33;
  v234 = v297;
  v214 = (volatile signed __int64 *)v63;
  v215 = 0;
  v233 = v62;
  v232 = v280;
  v228 = a6;
  v220 = 3;
  v221 = 3;
  v222 = 3;
  v223 = 3;
  v224 = 3;
  v225 = 3;
  v226 = 3;
  v282 = 0;
  v283 = (LPVOID)8;
  v284 = 0;
  memset(v269, 0, 26);
  if ( a5 )
    v66 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a5 + 32LL))(*a5);
  else
    v66 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, const char *, _QWORD, __int64, _WORD *))(*(_QWORD *)*v277
                                                                                                  + 344LL))(
    *v277,
    0,
    0,
    v66,
    " ",
    0,
    13,
    v269);
  v242 = 0;
  v241 = 0;
  v240 = 0;
  v239 = 0;
  v301 = 1;
  v300 = 0;
  shaping_cache::context::impl_2::get_font_table(v243, &v211, 1112888135);
  v67 = *(_QWORD *)v243;
  if ( *(_QWORD *)v243 )
  {
    otls::gpos::GPosHeader::new(v209, *(_QWORD *)v243, *(_QWORD *)&v243[8]);
    if ( *(_QWORD *)v209 == 0x8000000000000001uLL )
    {
      v301 = 1;
      v300 = 0;
      core::result::unwrap_failed(
        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
        43,
        (unsigned int)v278,
        (unsigned int)qword_18033B508,
        (__int64)&off_180340958);
    }
    memcpy_0(&v203, v209, 0xE0u);
    shaping::gsub::load_open_type_supported_scripts(&v203, 1112888135, &v239);
    if ( 2LL * (_QWORD)v203 )
    {
      v68 = lpMem;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v68);
    }
  }
  else
  {
    engine = *(_DWORD *)&v243[8];
    if ( *(_DWORD *)&v243[8] != -300 )
      goto LABEL_78;
  }
  v238 = 0;
  v237 = 0;
  v236 = 0;
  v235 = 0;
  v301 = 1;
  v300 = 0;
  shaping_cache::context::impl_2::get_font_table(v243, &v211, 1397706823);
  v71 = *(_QWORD *)v243;
  if ( *(_QWORD *)v243 )
  {
    otls::gpos::GPosHeader::new(v209, *(_QWORD *)v243, *(_QWORD *)&v243[8]);
    if ( *(_QWORD *)v209 == 0x8000000000000001uLL )
    {
      v301 = 1;
      v300 = 0;
      core::result::unwrap_failed(
        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
        43,
        (unsigned int)v278,
        (unsigned int)qword_18033B508,
        (__int64)&off_180340970);
    }
    memcpy_0(&v203, v209, 0xE0u);
    shaping::gsub::load_open_type_supported_scripts(&v203, 1397706823, &v235);
    if ( 2LL * (_QWORD)v203 )
    {
      v72 = lpMem;
      v73 = GetProcessHeap();
      HeapFree(v73, 0, v72);
    }
  }
  else
  {
    engine = *(_DWORD *)&v243[8];
    if ( *(_DWORD *)&v243[8] != -300 )
      goto LABEL_78;
  }
  v301 = 1;
  v300 = 0;
  shaping_cache::context::impl_2::get_font_table(v209, &v211, 1178944583);
  v74 = *(_QWORD *)v209;
  if ( !*(_QWORD *)v209 )
  {
    engine = *(_DWORD *)&v209[8];
    if ( *(_DWORD *)&v209[8] != -300 )
      goto LABEL_78;
  }
  v301 = 1;
  v300 = 0;
  shaping_cache::context::impl_2::get_font_table(v209, &v211, 2020765549);
  v75 = *(_QWORD *)v209;
  if ( !*(_QWORD *)v209 )
  {
    engine = *(_DWORD *)&v209[8];
    if ( *(_DWORD *)&v209[8] != -300 )
      goto LABEL_78;
  }
  v301 = 1;
  v300 = 0;
  v76 = &v211;
  shaping_cache::context::impl_2::get_font_table(v209, &v211, 1953656685);
  if ( !*(_QWORD *)v209 )
  {
    engine = *(_DWORD *)&v209[8];
    if ( *(_DWORD *)&v209[8] != -300 )
      goto LABEL_78;
  }
  *(_OWORD *)&v243[4] = v239;
  *(_OWORD *)&v243[20] = v240;
  v244 = v241;
  v245 = v242;
  v77 = _mm_load_si128(&v235);
  v78 = _mm_load_si128(&v236);
  v249 = v238;
  v248 = v237;
  v247 = v78;
  v246 = v77;
  v256 = v74 != 0;
  v257 = v71 != 0;
  v260 = 0;
  v261 = 0;
  v258 = v67 != 0;
  *(_DWORD *)v243 = 0;
  v250 = v269[0];
  v251 = *(_QWORD *)&v269[1];
  v252 = *(_DWORD *)&v269[5];
  v253 = v269[0];
  v254 = *(_QWORD *)&v269[7];
  v255 = *(_DWORD *)&v269[11];
  v259 = (*(_QWORD *)v209 | v75) != 0;
  v301 = 1;
  v300 = 0;
  engine = shaping_cache::context::impl_0::write_cache_slot(&v282, 0, 0x20000, v243, 188);
  if ( engine )
    goto LABEL_78;
  v264 = &v211;
  v265 = &off_180343070;
  v266 = 0;
  v267 = 0;
  v84 = (_DWORD *)std::sys::alloc::windows::process_heap_alloc(8, 0x10000);
  if ( !v84 )
  {
    v301 = 1;
    v300 = 0;
    alloc::alloc::handle_alloc_error(1, 0x10000);
  }
  v85 = v84;
  v274 = 0x10000;
  v275 = v84;
  v276 = 0x10000;
  v278[0] = 0;
  otls::resource::ResourceMgr::init(v209, 2);
  v86 = *(char **)v209;
  if ( *(_QWORD *)v209 == 4 )
    goto LABEL_102;
  LODWORD(v76) = *(_DWORD *)&v209[8];
  memcpy_0((char *)&lpMem + 4, &v209[12], 0x56Cu);
  v203 = v86;
  LODWORD(lpMem) = (_DWORD)v76;
  if ( v208 == 0x8000000000000001uLL )
    core::option::unwrap_failed(&off_18033A310);
  otls::cache::builder::build_table_cache(
    (unsigned int)v209,
    0,
    (unsigned int)&v203,
    (unsigned int)&v208,
    (__int64)(v85 + 3),
    65524);
  if ( (v209[0] & 1) != 0 )
    goto LABEL_101;
  v88 = *(_QWORD *)&v209[8];
  if ( *(_QWORD *)&v209[8] )
  {
    v89 = *(_DWORD *)&v209[8] + 12;
    LODWORD(v76) = 12;
    if ( (unsigned __int64)(*(_QWORD *)&v209[8] + 12LL) >= 0x10001 )
      core::panicking::panic("assertion failed: used_cache_size <= cache_buffer.len()", 55, &off_18033A328);
  }
  else
  {
    v89 = 12;
    LODWORD(v76) = 0;
  }
  if ( v207 == 0x8000000000000001uLL )
    core::option::unwrap_failed(&off_18033A340);
  v90 = (v89 + 3) & 0x3FFFC;
  if ( (unsigned int)v90 > 0x10000 )
    core::slice::index::slice_start_index_len_fail(v90, 0x10000, &off_18033A388);
  LOBYTE(v87) = 1;
  otls::cache::builder::build_table_cache(
    (unsigned int)v209,
    v87,
    (unsigned int)&v203,
    (unsigned int)&v207,
    (__int64)v85 + v90,
    0x10000 - v90);
  if ( (v209[0] & 1) != 0 )
  {
LABEL_101:
    core::ptr::drop_in_place_otls::resource::ResourceMgr_(&v203, v87);
LABEL_102:
    if ( !v278[0] || _InterlockedDecrement64(v278[0]) )
      goto LABEL_111;
    v91 = 1;
    goto LABEL_105;
  }
  if ( !*(_QWORD *)&v209[8] )
  {
    v129 = (unsigned int)v76;
    v74 = 0;
    v128 = v90;
    LODWORD(v90) = 0;
    LODWORD(v76) = 0;
    if ( !v88 )
      goto LABEL_285;
    goto LABEL_281;
  }
  v128 = *(_QWORD *)&v209[8] + v90;
  if ( (unsigned __int64)(*(_QWORD *)&v209[8] + v90) >= 0x10001 )
    core::panicking::panic("assertion failed: used_cache_size <= cache_buffer.len()", 55, &off_18033A358);
  LODWORD(v129) = (_DWORD)v76;
  if ( v88 )
  {
LABEL_281:
    v130 = v129;
    if ( ((unsigned __int8)v85 & 3) != 0 )
    {
      *(_QWORD *)v209 = 0;
      *(_QWORD *)&v209[8] = v85;
      *(_QWORD *)&v209[16] = 0x10000;
      core::result::unwrap_failed(
        (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
        43,
        (unsigned int)v209,
        (unsigned int)&qword_180339C40,
        (__int64)&off_18033A370);
    }
    goto LABEL_282;
  }
  v130 = 0;
  if ( ((unsigned __int8)v85 & 3) != 0 )
  {
    *(_QWORD *)v209 = 0;
    *(_QWORD *)&v209[8] = v85;
    *(_QWORD *)&v209[16] = 0x10000;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)v209,
      (unsigned int)&qword_180339C40,
      (__int64)&off_18033A370);
  }
LABEL_282:
  v129 = 0;
  if ( !*(_QWORD *)&v209[8] )
    LODWORD(v90) = 0;
  *v85 = v128;
  v85[1] = v130;
  v85[2] = v90;
  LODWORD(v76) = 0x20000;
  v74 = v128;
LABEL_285:
  core::ptr::drop_in_place_otls::resource::ResourceMgr_(&v203, v129);
  v91 = 0;
  if ( v278[0] && !_InterlockedDecrement64(v278[0]) )
LABEL_105:
    alloc::sync::Arc_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_::drop_slow_dyn__otls::client::TableData_assoc__Target_slice2__u8________alloc::alloc::Global_(
      v278[0],
      v278[1]);
  if ( !v91 )
  {
    if ( v74 )
    {
      alloc::vec::Vec_u8_alloc::alloc::Global_::resize_u8_alloc::alloc::Global__0(&v274, v74);
      v85 = v275;
      engine = shaping_cache::context::impl_0::write_cache_slot(&v282, 1, (unsigned int)v76, v275, v276);
      if ( engine )
      {
        if ( v274 )
        {
          v92 = GetProcessHeap();
          HeapFree(v92, 0, v85);
        }
        goto LABEL_78;
      }
    }
  }
LABEL_111:
  if ( v274 )
  {
    v93 = GetProcessHeap();
    HeapFree(v93, 0, v85);
  }
  v94 = v284;
  v95 = 24 * v284;
  HIDWORD(_R13) = 0x7FFFFFFF;
  if ( (0x18 * (unsigned __int128)v284) >> 64 != 0 || 24 * v284 > 0x7FFFFFFFFFFFFFF8LL )
  {
    v97 = 0;
    goto LABEL_115;
  }
  if ( v95 )
  {
    v98 = v283;
    v99 = 24 * v284;
    v100 = std::sys::alloc::windows::process_heap_alloc(0, v95);
    if ( !v100 )
    {
      v97 = 8;
      v95 = v99;
LABEL_115:
      v301 = 1;
      v300 = 0;
      alloc::raw_vec::handle_error(v97, v95, &off_180342F70);
    }
    v101 = v100;
    if ( v94 )
    {
      v102 = 0;
      v103 = v94;
      do
      {
        if ( v99 == v102 )
          break;
        v104 = v98[4];
        v105 = v98[5];
        v106 = *(volatile signed __int64 **)v98;
        v107 = _InterlockedIncrement64(*(volatile signed __int64 **)v98);
        if ( (v107 < 0) ^ __OFSUB__(v99, v102) | (v107 == 0) )
          goto LABEL_375;
        --v103;
        v108 = *((_QWORD *)v98 + 1);
        v98 += 6;
        *(_QWORD *)(v101 + v102) = v106;
        *(_QWORD *)(v101 + v102 + 8) = v108;
        *(_DWORD *)(v101 + v102 + 16) = v104;
        *(_DWORD *)(v101 + v102 + 20) = v105;
        v102 += 24;
      }
      while ( v103 );
      if ( v94 >= 0x555555555555555LL )
      {
        v301 = 1;
        v300 = 0;
        core::result::unwrap_failed(
          (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
          43,
          (unsigned int)v278,
          (unsigned int)qword_180334F58,
          (__int64)&off_180334FC0);
      }
    }
  }
  else
  {
    v101 = 8;
  }
  v109 = (volatile signed __int64 *)std::sys::alloc::windows::process_heap_alloc(
                                      0,
                                      (24 * v94 + 23) & 0x7FFFFFFFFFFFFFF8LL);
  if ( !v109 )
  {
    v301 = 1;
    v300 = 0;
    alloc::alloc::handle_alloc_error(8, (24 * v94 + 23) & 0x7FFFFFFFFFFFFFF8LL);
  }
  v110 = v109;
  *v109 = 1;
  *((_QWORD *)v109 + 1) = 1;
  memcpy_0((void *)(v109 + 2), (const void *)v101, 24 * v94);
  if ( v94 )
  {
    v111 = GetProcessHeap();
    HeapFree(v111, 0, (LPVOID)v101);
  }
  if ( !_InterlockedDecrement64(v214) )
    alloc::sync::Arc_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_::drop_slow_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_(
      v214,
      v215);
  v214 = v110;
  v215 = v94;
  v301 = 1;
  v300 = 0;
  engine = _guard_dispatch_icall_fptr();
  if ( engine == -200 )
  {
    engine = -200;
    if ( !(_BYTE)v289 )
    {
      v301 = 1;
      v300 = 0;
      engine = shaping::engine::generic::load_engine(
                 (unsigned int)&v211,
                 (unsigned int)&off_180343070,
                 (unsigned int)&v282,
                 (unsigned int)&off_1803430E8,
                 0);
      if ( !engine )
      {
        v292 = 0;
        goto LABEL_133;
      }
    }
LABEL_78:
    v79 = v272;
    *(_DWORD *)v272 = engine;
    *(_DWORD *)(v79 + 420) = 136;
    v80 = v283;
    v81 = v284;
    if ( v284 )
    {
      v82 = (volatile signed __int64 **)v283;
      do
      {
        if ( !_InterlockedDecrement64(*v82) )
          alloc::sync::Arc_slice2__u8__alloc::alloc::Global_::drop_slow_slice2__u8__alloc::alloc::Global_(*v82, v82[1]);
        v82 += 3;
        --v81;
      }
      while ( v81 );
    }
    if ( v282 )
    {
      v83 = GetProcessHeap();
      HeapFree(v83, 0, v80);
    }
    if ( !_InterlockedDecrement64(v214) )
      alloc::sync::Arc_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_::drop_slow_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_(
        v214,
        v215);
    v299 = 0;
    return core::ptr::drop_in_place_shaping_cache::context::FontTables_(v219);
  }
  if ( engine )
    goto LABEL_78;
LABEL_133:
  if ( v284 >= 0x555555555555555LL )
  {
    v301 = 0;
    v300 = 0;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)v278,
      (unsigned int)qword_180334F58,
      (__int64)&off_180334FC0);
  }
  v112 = v282;
  v113 = v283;
  v290 = v284;
  v114 = 24 * v284;
  v115 = (24 * v284 + 23) & 0x7FFFFFFFFFFFFFF8LL;
  v116 = (volatile signed __int64 *)std::sys::alloc::windows::process_heap_alloc(0, v115);
  if ( !v116 )
  {
    v301 = 0;
    v300 = 0;
    alloc::alloc::handle_alloc_error(8, v115);
  }
  _R15 = (signed __int64)v116;
  *v116 = 1;
  *((_QWORD *)v116 + 1) = 1;
  memcpy_0((void *)(v116 + 2), v113, v114);
  v118 = 0;
  if ( v112 )
  {
    v119 = GetProcessHeap();
    HeapFree(v119, 0, v113);
  }
  v120 = _InterlockedIncrement64((volatile signed __int64 *)_R15);
  if ( (v120 < 0) ^ v118 | (v120 == 0) )
    goto LABEL_375;
  v121 = _InterlockedCompareExchange8((volatile signed __int8 *)v60, 1, 0);
  v122 = v292;
  _RDI = Size;
  if ( v121 )
    std::sys::sync::mutex::futex::Mutex::lock_contended(v60);
  if ( 2 * qword_1804B1950 )
  {
    v124 = std::panicking::panic_count::is_zero_slow_path();
    LOBYTE(v124) = v124 ^ 1;
  }
  else
  {
    v124 = 0;
  }
  v125 = *((_BYTE *)v60 + 1);
  v291 = _R15;
  if ( v125 )
  {
    *(_QWORD *)v209 = v60;
    v209[8] = v124;
    core::result::unwrap_failed(
      (unsigned int)"called `Result::unwrap()` on an `Err` valueObject has been over-released.d:\\os\\out\\rust\\cargo_home\\amd64fre\\registry\\src\\microsoft.pkgs.visualstudio.com-f1660d608e0bcbd6\\windows-core-0.62.2\\src\\imp\\ref_count.rs",
      43,
      (unsigned int)v209,
      (unsigned int)&off_180342FA0,
      (__int64)&off_180343108);
  }
  v281 = v124;
  if ( _RDI )
  {
    v126 = std::sys::alloc::windows::process_heap_alloc(0, _RDI);
    if ( !v126 )
    {
      v298 = 1;
      alloc::alloc::handle_alloc_error(1, _RDI);
    }
    v127 = v126;
  }
  else
  {
    v127 = 1;
  }
  Buf1 = (void *)v127;
  memcpy_0((void *)v127, Src, _RDI);
  v286 = v122;
  v288 = (char *)*((_QWORD *)v60 + 4);
  if ( v288 )
  {
    v131 = Address;
    *(_QWORD *)&v209[16] = *((_QWORD *)Address + 5);
    *(_OWORD *)v209 = 0;
    v210 = 0;
    *(_OWORD *)&v209[24] = xmmword_1804B1900;
    *(__m128i *)&v209[40] = _mm_loadu_si128((const __m128i *)&xmmword_1804B1910);
    core::hash::impls::impl_4::hash_u8_foldhash::fast::FoldHasher_(Buf1, Size, v209);
    if ( v210 )
      v132 = ((*(_QWORD *)v209 ^ *(_QWORD *)&v209[16]) * (*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24]))
           ^ (((unsigned __int64)(*(_QWORD *)v209 ^ *(_QWORD *)&v209[16])
             * (unsigned __int128)(unsigned __int64)(*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24])) >> 64);
    else
      v132 = *(_QWORD *)&v209[16];
    _RDI = v131[1];
    v133 = v131[2];
    v134 = _mm_cvtsi32_si128(v132 >> 57);
    v135 = _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v134, v134), 0), 0);
    _R15 = _RDI - 16;
    for ( j = 0; ; j += 16 )
    {
      v137 = v133 & v132;
      v138 = _mm_loadu_si128((const __m128i *)(_RDI + v137));
      _R12D = _mm_movemask_epi8(_mm_cmpeq_epi8(v138, v135));
      if ( _R12D )
      {
        do
        {
          __asm { tzcnt   r13d, r12d }
          _R13 = v133 & (v137 + _R13);
          v141 = *(_QWORD *)(_R15 - 16 * _R13);
          if ( Size == *(_QWORD *)(v141 + 8) && !memcmp_0(Buf1, *(const void **)v141, Size) )
          {
            v142 = *(_QWORD *)(_RDI - 16 * _R13 - 8);
            v143 = *(_QWORD *)(v142 + 16);
            v144 = *(_QWORD *)(v142 + 24);
            v51 = v291;
            *(_QWORD *)(v142 + 16) = v291;
            *(_QWORD *)(v142 + 24) = v290;
            v145 = *(_DWORD *)(v142 + 32);
            *(_QWORD *)(v142 + 32) = v286;
            v146 = *(_QWORD *)(v142 + 48);
            *(_QWORD *)(*(_QWORD *)(v142 + 40) + 48LL) = v146;
            *(_QWORD *)(v146 + 40) = *(_QWORD *)(v142 + 40);
            v147 = Address;
            v148 = *((_QWORD *)Address + 7);
            *(_QWORD *)(v142 + 48) = *(_QWORD *)(v148 + 48);
            *(_QWORD *)(v142 + 40) = v148;
            *(_QWORD *)(v148 + 48) = v142;
            *(_QWORD *)(*(_QWORD *)(v142 + 48) + 40LL) = v142;
            v289 = Buf1;
            v54 = v285;
            v149 = __PAIR128__(v144, v143);
            goto LABEL_332;
          }
          v140 = _R12D - 1;
          LOWORD(v140) = _R12D & (_R12D - 1);
          _R12D = v140;
        }
        while ( (_WORD)v140 );
      }
      if ( _mm_movemask_epi8(_mm_cmpeq_epi8(v138, (__m128i)-1LL)) )
        break;
      v132 = j + v137 + 16;
    }
  }
  v150 = Address;
  v151 = (char *)*((_QWORD *)Address + 6);
  if ( v288 == v151 )
  {
    v152 = *(_QWORD *)(*((_QWORD *)Address + 8) + 40LL);
    v268 = *((_QWORD *)Address + 5);
    *(_QWORD *)&v209[16] = v268;
    *(_OWORD *)v209 = 0;
    v210 = 0;
    *(_OWORD *)&v209[24] = xmmword_1804B1900;
    *(__m128i *)&v209[40] = _mm_loadu_si128((const __m128i *)&xmmword_1804B1910);
    v153 = *(void **)(v152 + 8);
    v289 = *(void **)v152;
    Src = v153;
    core::hash::impls::impl_4::hash_u8_foldhash::fast::FoldHasher_(v289, v153, v209);
    v273 = v151;
    if ( v210 )
      v154 = ((*(_QWORD *)v209 ^ *(_QWORD *)&v209[16]) * (*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24]))
           ^ (((unsigned __int64)(*(_QWORD *)v209 ^ *(_QWORD *)&v209[16])
             * (unsigned __int128)(unsigned __int64)(*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24])) >> 64);
    else
      v154 = *(_QWORD *)&v209[16];
    v158 = *((_QWORD *)Address + 2);
    v159 = _mm_cvtsi32_si128(v154 >> 57);
    v160 = _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v159, v159), 0), 0);
    v287 = *((_QWORD *)Address + 1);
    v161 = v287 - 16;
    v162 = 0;
    v163 = Src;
    while ( 1 )
    {
      _R15 = v158 & v154;
      v164 = _mm_loadu_si128((const __m128i *)(v287 + _R15));
      _R14D = _mm_movemask_epi8(_mm_cmpeq_epi8(v164, v160));
      if ( _R14D )
        break;
LABEL_305:
      if ( _mm_movemask_epi8(_mm_cmpeq_epi8(v164, (__m128i)-1LL)) )
        core::option::unwrap_failed(&off_180342FE0);
      v154 = v162 + _R15 + 16;
      v162 += 16;
    }
    while ( 1 )
    {
      __asm { tzcnt   edi, r14d }
      _RDI = v158 & (_R15 + _RDI);
      v167 = 16 * _RDI;
      v168 = *(_QWORD *)(v161 - 16 * _RDI);
      if ( v163 == *(void **)(v168 + 8) )
      {
        v169 = memcmp_0(v289, *(const void **)v168, (size_t)v163);
        v163 = Src;
        if ( !v169 )
          break;
      }
      v166 = _R14D - 1;
      LOWORD(v166) = _R14D & (_R14D - 1);
      _R14D = v166;
      if ( !(_WORD)v166 )
        goto LABEL_305;
    }
    v170 = v287 - 16 * _RDI;
    v171 = v167 >> 4;
    v172 = v158 & (v171 - 16);
    _BitScanReverse(
      &v173,
      _mm_movemask_epi8(_mm_cmpeq_epi8(_mm_loadu_si128((const __m128i *)(v287 + v172)), (__m128i)-1LL)));
    _EDX = _mm_movemask_epi8(_mm_cmpeq_epi8(_mm_loadu_si128((const __m128i *)(v287 + v171)), (__m128i)-1LL)) | 0x10000;
    __asm { tzcnt   edx, edx }
    v176 = 0x80;
    v150 = Address;
    if ( (unsigned __int16)((v173 ^ 0xF) + _EDX) <= 0xFu )
    {
      ++*((_QWORD *)Address + 3);
      v176 = -1;
    }
    v177 = v287;
    *(_BYTE *)(v287 + v171) = v176;
    *(_BYTE *)(v177 + v172 + 16) = v176;
    v150[4] = v288 - 1;
    v156 = *(__m128i **)(v170 - 8);
    v151 = (char *)v156->m128i_i64[0];
    _RDI = v156->m128i_u64[1];
    v156->m128i_i64[0] = (__int64)Buf1;
    v156->m128i_i64[1] = Size;
    *(_QWORD *)&v243[16] = v156[2].m128i_i64[0];
    *(__m128i *)v243 = _mm_loadu_si128(v156 + 1);
    v156[1].m128i_i64[0] = v291;
    v156[1].m128i_i64[1] = v290;
    v156[2].m128i_i64[0] = v286;
    v178 = v156[3].m128i_i64[0];
    *(_QWORD *)(v156[2].m128i_i64[1] + 48) = v178;
    *(_QWORD *)(v178 + 40) = v156[2].m128i_i64[1];
    v157 = v268;
  }
  else
  {
    *(_DWORD *)&v209[32] = 136;
    v155 = std::sys::alloc::windows::process_heap_alloc(0, 56);
    if ( !v155 )
    {
      v273 = v151;
      alloc::alloc::handle_alloc_error(8, 56);
    }
    v156 = (__m128i *)v155;
    *(_QWORD *)v155 = Buf1;
    *(_QWORD *)(v155 + 8) = Size;
    *(_QWORD *)(v155 + 16) = v291;
    *(_QWORD *)(v155 + 24) = v290;
    *(_QWORD *)(v155 + 32) = v286;
    *(_OWORD *)(v155 + 40) = 0;
    *(_QWORD *)&v243[16] = *(_QWORD *)&v209[32];
    *(__m128i *)v243 = _mm_loadu_si128((const __m128i *)&v209[16]);
    v157 = v150[5];
  }
  v203 = v151;
  lpMem = (LPVOID)_RDI;
  v205 = *(_OWORD *)v243;
  v206 = *(_QWORD *)&v243[16];
  v179 = v150[7];
  v156[3].m128i_i64[0] = *(_QWORD *)(v179 + 48);
  v156[2].m128i_i64[1] = v179;
  *(_QWORD *)(v179 + 48) = v156;
  *(_QWORD *)(v156[3].m128i_i64[0] + 40) = v156;
  *(_QWORD *)&v209[16] = v157;
  *(_OWORD *)v209 = 0;
  v210 = 0;
  *(__m128i *)&v209[24] = _mm_loadu_si128((const __m128i *)&xmmword_1804B1900);
  *(__m128i *)&v209[40] = _mm_loadu_si128((const __m128i *)&xmmword_1804B1910);
  core::hash::impls::impl_4::hash_u8_foldhash::fast::FoldHasher_(v156->m128i_i64[0], v156->m128i_i64[1], v209);
  if ( v210 )
    v180 = ((*(_QWORD *)v209 ^ *(_QWORD *)&v209[16]) * (*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24]))
         ^ (((unsigned __int64)(*(_QWORD *)v209 ^ *(_QWORD *)&v209[16])
           * (unsigned __int128)(unsigned __int64)(*(_QWORD *)&v209[8] ^ *(_QWORD *)&v209[24])) >> 64);
  else
    v180 = *(_QWORD *)&v209[16];
  if ( !v150[3] )
    hashbrown::raw::RawTable_tuple__lru::KeyRef_alloc::boxed::Box_slice2__u8__alloc::alloc::Global____core::ptr::non_null::NonNull_lru::LruEntry_alloc::boxed::Box_slice2__u8__alloc::alloc::Global__shaping_cache::ShapingCacheEntry______allocator_api2::stable::alloc::global::Global_::reserve_rehash_tuple__lru::KeyRef_alloc::boxed::Box_slice2__u8__alloc::alloc::Global____core::ptr::non_null::NonNull_lru::LruEntry_alloc::boxed::Box_slice2__u8__alloc::alloc::Global__shaping_cache::ShapingCacheEntry______allocator_api2::stable::alloc::global::Global_hashbrown::map::make_hasher::closure_env_0_lru::KeyRef_alloc::boxed::Box_slice2__u8__alloc::alloc::Global____core::ptr::non_null::NonNull_lru::LruEntry_alloc::boxed::Box_slice2__u8__alloc::alloc::Global__shaping_cache::ShapingCacheEntry____foldhash::fast::RandomState___(
      v150 + 1,
      v150[5]);
  v286 = _RDI;
  v289 = v151;
  v181 = (char *)v150[1];
  v182 = v150[2];
  v288 = (char *)(v180 >> 57);
  v183 = _mm_cvtsi32_si128(v180 >> 57);
  v184 = _mm_shuffle_epi32(_mm_shufflelo_epi16(_mm_unpacklo_epi8(v183, v183), 0), 0);
  v185 = v181 - 16;
  v186 = 0;
  Src = 0;
  Buf1 = v181;
  while ( 1 )
  {
    Size = v186;
    v187 = v182 & v180;
    v188 = _mm_loadu_si128((const __m128i *)&v181[v187]);
    _ESI = _mm_movemask_epi8(_mm_cmpeq_epi8(v188, v184));
    if ( _ESI )
      break;
LABEL_325:
    if ( Src != (void *)1 )
    {
      _RAX = (unsigned int)_mm_movemask_epi8(v188);
      if ( !(_DWORD)_RAX )
      {
        v194 = 0;
        goto LABEL_329;
      }
      __asm { tzcnt   eax, eax }
      v287 = v182 & (v187 + _RAX);
    }
    v194 = 1;
    if ( _mm_movemask_epi8(_mm_cmpeq_epi8(v188, (__m128i)-1LL)) )
    {
      v196 = Buf1;
      _R8 = v287;
      v200 = *((_BYTE *)Buf1 + v287);
      if ( v200 >= 0 )
      {
        _EAX = _mm_movemask_epi8(_mm_load_si128((const __m128i *)Buf1));
        __asm { tzcnt   r8d, eax }
        v200 = *((_BYTE *)Buf1 + _R8);
      }
      v147 = Address;
      *((_QWORD *)Address + 3) -= v200 & 1;
      v202 = (char)v288;
      v196[_R8] = (_BYTE)v288;
      v196[(v182 & (_R8 - 16)) + 16] = v202;
      ++v147[4];
      v195 = -(__int64)_R8;
      *(_QWORD *)&v196[-16 * _R8 - 16] = v156;
      goto LABEL_331;
    }
LABEL_329:
    v181 = (char *)Buf1;
    Src = (void *)v194;
    v180 = Size + v187 + 16;
    v186 = Size + 16;
  }
  v190 = v156->m128i_u64[1];
  while ( 1 )
  {
    __asm { tzcnt   r15d, esi }
    _R15 = v182 & (v187 + _R15);
    v192 = (const void ***)&v185[-16 * _R15];
    if ( (const void *)v190 == (*v192)[1] && !memcmp_0((const void *)v156->m128i_i64[0], **v192, v190) )
      break;
    v191 = _ESI - 1;
    LOWORD(v191) = _ESI & (_ESI - 1);
    _ESI = v191;
    if ( !(_WORD)v191 )
      goto LABEL_325;
  }
  v195 = -_R15;
  v147 = Address;
  v196 = Buf1;
LABEL_331:
  *(_QWORD *)&v196[16 * v195 - 8] = v156;
  v145 = v206;
  v149 = v205;
  Size = v286;
  v54 = v285;
  v51 = v291;
LABEL_332:
  if ( v145 != 136 )
  {
    if ( Size )
    {
      v197 = GetProcessHeap();
      HeapFree(v197, 0, v289);
    }
    if ( !_InterlockedDecrement64((volatile signed __int64 *)v149) )
      alloc::sync::Arc_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_::drop_slow_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_(
        v149,
        *((_QWORD *)&v149 + 1));
  }
  if ( !(_BYTE)v281 && 2 * qword_1804B1950 && !(unsigned __int8)std::panicking::panic_count::is_zero_slow_path() )
    *((_BYTE *)v147 + 1) = 1;
  v198 = *(_BYTE *)v147;
  *(_BYTE *)v147 = 0;
  v53 = v292;
  v52 = v290;
  if ( v198 == 2 )
    WakeByAddressSingle(v147);
  if ( !_InterlockedDecrement64(v214) )
    alloc::sync::Arc_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_::drop_slow_slice2__shaping_cache::ShapingCacheSlot__alloc::alloc::Global_(
      v214,
      v215);
  v271 = v52;
  v270 = v51;
  v299 = 1;
  core::ptr::drop_in_place_shaping_cache::context::FontTables_(v219);
LABEL_52:
  v56 = v272;
  *(_QWORD *)(v272 + 408) = *((_QWORD *)v54 + 4);
  v57 = *v54;
  *(_OWORD *)(v56 + 392) = v54[1];
  *(_OWORD *)(v56 + 376) = v57;
  *(_WORD *)v56 = v279;
  v58 = *(_OWORD *)v263;
  *(_OWORD *)(v56 + 2) = v262;
  *(_OWORD *)(v56 + 18) = v58;
  *(_OWORD *)(v56 + 32) = *(_OWORD *)&v263[14];
  *(_QWORD *)(v56 + 48) = v51;
  *(_QWORD *)(v56 + 56) = v52;
  *(_QWORD *)(v56 + 64) = a5;
  *(float *)(v56 + 72) = v11;
  *(float *)(v56 + 76) = v33;
  *(_DWORD *)(v56 + 112) = 3;
  *(_DWORD *)(v56 + 152) = 3;
  *(_DWORD *)(v56 + 192) = 3;
  *(_DWORD *)(v56 + 232) = 3;
  *(_DWORD *)(v56 + 272) = 3;
  *(_DWORD *)(v56 + 312) = 3;
  *(_DWORD *)(v56 + 352) = 3;
  *(_QWORD *)(v56 + 360) = v277;
  *(_QWORD *)(v56 + 368) = a6;
  *(_DWORD *)(v56 + 416) = v280;
  *(_DWORD *)(v56 + 420) = v53;
  result = v297;
  *(_BYTE *)(v56 + 424) = v297;
  return result;
}

```

## disassembly

```asm
0x1800d0c60  push    rbp
0x1800d0c61  push    r15
0x1800d0c63  push    r14
0x1800d0c65  push    r13
0x1800d0c67  push    r12
0x1800d0c69  push    rsi
0x1800d0c6a  push    rdi
0x1800d0c6b  push    rbx
0x1800d0c6c  sub     rsp, 0FF8h
0x1800d0c73  lea     rbp, [rsp+80h]
0x1800d0c7b  movdqa  [rbp+0FB0h+var_50], xmm10
0x1800d0c84  movdqa  [rbp+0FB0h+var_60], xmm9
0x1800d0c8d  movaps  [rbp+0FB0h+var_70], xmm8
0x1800d0c95  movaps  [rbp+0FB0h+var_80], xmm7
0x1800d0c9c  movaps  [rbp+0FB0h+var_90], xmm6
0x1800d0ca3  mov     [rbp+0FB0h+var_98], 0FFFFFFFFFFFFFFFEh
0x1800d0cae  mov     rsi, r9
0x1800d0cb1  mov     r12, rdx
0x1800d0cb4  mov     [rbp+0FB0h+var_170], rcx
0x1800d0cbb  mov     [rbp+0FB0h+var_148], r8
0x1800d0cc2  mov     r15, [r8]
0x1800d0cc5  xorps   xmm0, xmm0
0x1800d0cc8  movaps  [rbp+0FB0h+var_A50], xmm0
0x1800d0ccf  movaps  xmmword ptr [rbp+0FB0h+var_A60], xmm0
0x1800d0cd6  movaps  xmmword ptr [rbp+0FB0h+var_A70], xmm0
0x1800d0cdd  mov     rax, [r15]
0x1800d0ce0  mov     rax, [rax+0D0h]
0x1800d0ce7  lea     rdx, [rbp+0FB0h+var_A70]
0x1800d0cee  mov     rcx, r15
0x1800d0cf1  call    cs:__guard_dispatch_icall_fptr
0x1800d0cf7  movzx   eax, word ptr [rbp+0FB0h+var_A70]
0x1800d0cfe  movups  xmm0, xmmword ptr [rbp+0FB0h+var_A70+2]
0x1800d0d05  movups  xmm1, xmmword ptr [rbp+0FB0h+var_A60+2]
0x1800d0d0c  movups  xmm2, [rbp+0FB0h+var_A50]
0x1800d0d13  movaps  [rbp+0FB0h+var_200], xmm0
0x1800d0d1a  movaps  [rbp+0FB0h+var_1F0], xmm1
0x1800d0d21  movups  [rbp+0FB0h+var_1F0+0Eh], xmm2
0x1800d0d28  mov     [rbp+0FB0h+var_124], eax
0x1800d0d2e  xorps   xmm8, xmm8
0x1800d0d32  cvtsi2ss xmm8, eax
0x1800d0d37  movss   xmm6, dword ptr [rsi+8]
0x1800d0d3c  movss   xmm7, cs:__real@3f800000
0x1800d0d44  cmp     dword ptr [rsi+4], 0
0x1800d0d48  jz      loc_1800D0DE2
0x1800d0d4e  movss   xmm1, dword ptr [rsi+14h]
0x1800d0d53  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800d0d5a  movss   xmm0, dword ptr [rsi+0Ch]
0x1800d0d5f  movss   xmm2, cs:__real@37800000
0x1800d0d67  ucomiss xmm2, xmm1
0x1800d0d6a  jbe     short loc_1800D0D8F
0x1800d0d6c  movss   xmm1, dword ptr [rsi+18h]
0x1800d0d71  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800d0d78  ucomiss xmm2, xmm1
0x1800d0d7b  jbe     short loc_1800D0DE2
0x1800d0d7d  lea     rax, [rsi+1Ch]
0x1800d0d81  movss   xmm1, dword ptr [rsi+10h]
0x1800d0d86  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800d0d8d  jmp     short loc_1800D0DB5
0x1800d0d8f  movss   xmm3, dword ptr [rsi+10h]
0x1800d0d94  andps   xmm3, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800d0d9b  ucomiss xmm2, xmm3
0x1800d0d9e  jbe     short loc_1800D0DE2
0x1800d0da0  movss   xmm3, dword ptr [rsi+1Ch]
0x1800d0da5  andps   xmm3, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800d0dac  ucomiss xmm2, xmm3
0x1800d0daf  jbe     short loc_1800D0DE2
0x1800d0db1  lea     rax, [rsi+18h]
0x1800d0db5  movss   xmm3, dword ptr [rax]
0x1800d0db9  movaps  xmm4, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x1800d0dc0  andps   xmm3, xmm4
0x1800d0dc3  movaps  xmm5, xmm1
0x1800d0dc6  subss   xmm5, xmm3
0x1800d0dca  andps   xmm5, xmm4
0x1800d0dcd  ucomiss xmm2, xmm5
0x1800d0dd0  jbe     short loc_1800D0DE2
0x1800d0dd2  mulss   xmm0, xmm6
0x1800d0dd6  mulss   xmm0, xmm1
0x1800d0dda  divss   xmm0, xmm8
0x1800d0ddf  movaps  xmm7, xmm0
0x1800d0de2  mov     rax, [r15]
0x1800d0de5  mov     rax, [rax+88h]
0x1800d0dec  mov     rcx, r15
0x1800d0def  call    cs:__guard_dispatch_icall_fptr
0x1800d0df5  mov     [rbp+0FB0h+var_9D], al
0x1800d0dfb  movzx   eax, word ptr [rsi]
0x1800d0dfe  xor     r8d, r8d
0x1800d0e01  cmp     ax, 1
0x1800d0e05  jnz     loc_1800D1072
0x1800d0e0b  cmp     byte ptr [rsi+2], 1
0x1800d0e0f  jnz     loc_1800D1072
0x1800d0e15  mov     r8d, 1Ah
0x1800d0e1b  xor     r9d, r9d
0x1800d0e1e  mov     dword ptr [rbp+0FB0h+var_E0], r9d; jumptable 00000001800D1095 default case, cases 5,7,16,19-21,23,28,29,38-40,52,54,55,64-68,70,72,75,77,93,94,97,98,101,103,104,106,110,113,115-118,120,121,125,128,130,134-137,139
0x1800d0e25  mov     [rbp+0FB0h+var_C4], r8d
0x1800d0e2c  movzx   ecx, ax
0x1800d0e2f  xor     edx, edx
0x1800d0e31  cmp     ecx, 0AFh
0x1800d0e37  cmovnb  eax, edx
0x1800d0e3a  movzx   eax, ax
0x1800d0e3d  shl     eax, 5
0x1800d0e40  lea     rcx, qword_180404390
0x1800d0e47  mov     eax, [rax+rcx+14h]
0x1800d0e4b  mov     [rbp+0FB0h+var_120], eax
0x1800d0e51  xorps   xmm0, xmm0
0x1800d0e54  movaps  xmmword ptr [rbp+0FB0h+var_A60], xmm0
0x1800d0e5b  movaps  xmmword ptr [rbp+0FB0h+var_A70], xmm0
0x1800d0e62  mov     rax, [r15]
0x1800d0e65  mov     rax, [rax+20h]
0x1800d0e69  lea     rdx, [rbp+0FB0h+var_A70]
0x1800d0e70  mov     rcx, r15
0x1800d0e73  call    cs:__guard_dispatch_icall_fptr
0x1800d0e79  mov     r13, [rbp+0FB0h+var_A70+8]
0x1800d0e80  mov     r14, [rbp+0FB0h+var_A60+8]
0x1800d0e87  mov     edi, 1
0x1800d0e8c  mov     eax, 1
0x1800d0e91  test    r14, r14
0x1800d0e94  jz      short loc_1800D0E9D
0x1800d0e96  mov     rax, [rbp+0FB0h+var_A60]
0x1800d0e9d  test    r13, r13
0x1800d0ea0  jz      short loc_1800D0EA9
0x1800d0ea2  mov     rdi, [rbp+0FB0h+var_A70]
0x1800d0ea9  lea     rbx, [r13+48h]
0x1800d0ead  mov     r8, rbx
0x1800d0eb0  add     r8, r14
0x1800d0eb3  js      loc_1800D19E7
0x1800d0eb9  mov     [rbp+0FB0h+Src], rax
0x1800d0ec0  mov     [rbp+0FB0h+var_100], rsi
0x1800d0ec7  mov     rax, [rbp+0FB0h+arg_28]
0x1800d0ece  mov     rax, [rax+10h]
0x1800d0ed2  mov     rsi, [rax+20h]
0x1800d0ed6  cmp     r8, rsi
0x1800d0ed9  mov     [rbp+0FB0h+Size], r8
0x1800d0ee0  ja      loc_1800D19C7
0x1800d0ee6  sub     rsi, r8
0x1800d0ee9  cmp     rsi, [rax]
0x1800d0eec  jb      loc_1800D19C7
0x1800d0ef2  mov     r15, r12
0x1800d0ef5  mov     [rax+20h], rsi
0x1800d0ef9  cmp     [rbp+0FB0h+Size], 0
0x1800d0f01  jz      short loc_1800D0F54
0x1800d0f03  mov     rcx, rsi; void *
0x1800d0f06  xor     edx, edx; Val
0x1800d0f08  mov     r12, rsi
0x1800d0f0b  mov     rsi, [rbp+0FB0h+Size]
0x1800d0f12  mov     r8, rsi; Size
0x1800d0f15  call    memset_0
0x1800d0f1a  cmp     rsi, 48h ; 'H'
0x1800d0f1e  mov     rsi, r12
0x1800d0f21  jb      short loc_1800D0F54
0x1800d0f23  mov     rcx, [rbp+0FB0h+var_100]
0x1800d0f2a  mov     rax, [rcx+20h]
0x1800d0f2e  mov     [rsi+20h], rax
0x1800d0f32  movups  xmm0, xmmword ptr [rcx]
0x1800d0f35  movups  xmm1, xmmword ptr [rcx+10h]
0x1800d0f39  movups  xmmword ptr [rsi+10h], xmm1
0x1800d0f3d  movups  xmmword ptr [rsi], xmm0
0x1800d0f40  mov     [rsi+28h], rbx
0x1800d0f44  mov     [rsi+30h], r14
0x1800d0f48  mov     qword ptr [rsi+38h], 48h ; 'H'
0x1800d0f50  mov     [rsi+40h], r13
0x1800d0f54  cmp     r13, 0FFFFFFFFFFFFFFB7h
0x1800d0f58  ja      loc_1800D2E40
0x1800d0f5e  cmp     rbx, [rbp+0FB0h+Size]
0x1800d0f65  ja      loc_1800D2E54
0x1800d0f6b  lea     rcx, [rsi+48h]; void *
0x1800d0f6f  mov     rdx, rdi; Src
0x1800d0f72  mov     r8, r13; Size
0x1800d0f75  call    memcpy_0
0x1800d0f7a  add     rbx, rsi
0x1800d0f7d  mov     rcx, rbx; void *
0x1800d0f80  mov     rdx, [rbp+0FB0h+Src]; Src
0x1800d0f87  mov     r8, r14; Size
0x1800d0f8a  call    memcpy_0
0x1800d0f8f  mov     cl, 1
0x1800d0f91  xor     eax, eax
0x1800d0f93  lock cmpxchg [r15], cl
0x1800d0f98  jnz     loc_1800D2E6A
0x1800d0f9e  mov     rax, cs:qword_1804B1950
0x1800d0fa5  shl     rax, 1
0x1800d0fa8  test    rax, rax
0x1800d0fab  jnz     loc_1800D2E77
0x1800d0fb1  xor     eax, eax
0x1800d0fb3  movzx   ecx, byte ptr [r15+1]
0x1800d0fb8  test    cl, cl
0x1800d0fba  jnz     loc_1800D2E83
0x1800d0fc0  mov     dword ptr [rbp+0FB0h+Buf1], eax
0x1800d0fc6  mov     [rbp+0FB0h+Src], rsi
0x1800d0fcd  mulss   xmm8, xmm7
0x1800d0fd2  divss   xmm6, xmm8
0x1800d0fd7  mov     [rbp+0FB0h+Address], r15
0x1800d0fde  cmp     qword ptr [r15+20h], 0
0x1800d0fe3  jz      loc_1800D12E6
0x1800d0fe9  mov     rsi, [rbp+0FB0h+Address]
0x1800d0ff0  mov     rax, [rsi+28h]
0x1800d0ff4  movups  xmm0, cs:xmmword_1804B1900
0x1800d0ffb  movups  xmm1, cs:xmmword_1804B1910
0x1800d1002  mov     [rbp+0FB0h+var_A60], rax
0x1800d1009  xorps   xmm2, xmm2
0x1800d100c  movaps  xmmword ptr [rbp+0FB0h+var_A70], xmm2
0x1800d1013  mov     [rbp+0FB0h+var_A38], 0
0x1800d101a  movups  xmmword ptr [rbp+0FB0h+var_A60+8], xmm0
0x1800d1021  movups  [rbp+0FB0h+var_A50+8], xmm1
0x1800d1028  lea     r8, [rbp+0FB0h+var_A70]
0x1800d102f  mov     rcx, [rbp+0FB0h+Src]
0x1800d1036  mov     rdx, [rbp+0FB0h+Size]
0x1800d103d  call    core__hash__impls__impl$4__hash_u8_foldhash__fast__FoldHasher_
0x1800d1042  cmp     [rbp+0FB0h+var_A38], 0
0x1800d1049  jz      short loc_1800D10A2
0x1800d104b  mov     rcx, [rbp+0FB0h+var_A60]
0x1800d1052  mov     rax, [rbp+0FB0h+var_A60+8]
0x1800d1059  xor     rcx, [rbp+0FB0h+var_A70]
0x1800d1060  xor     rax, [rbp+0FB0h+var_A70+8]
0x1800d1067  mul     rcx
0x1800d106a  mov     r14, rdx
0x1800d106d  xor     r14, rax
0x1800d1070  jmp     short loc_1800D10A9
0x1800d1072  movzx   ecx, al
0x1800d1075  mov     r9b, 1
0x1800d1078  add     ecx, 0FFFFFFFDh; switch 172 cases
0x1800d107b  cmp     ecx, 0ABh
0x1800d1081  ja      def_1800D1095; jumptable 00000001800D1095 default case, cases 5,7,16,19-21,23,28,29,38-40,52,54,55,64-68,70,72,75,77,93,94,97,98,101,103,104,106,110,113,115-118,120,121,125,128,130,134-137,139
0x1800d1087  lea     rdx, jpt_1800D1095
0x1800d108e  movsxd  rcx, ds:(jpt_1800D1095 - 180407068h)[rdx+rcx*4]
0x1800d1092  add     rcx, rdx
0x1800d1095  jmp     rcx; switch jump
0x1800d1097  mov     r8d, 9; jumptable 00000001800D1095 cases 37,44
0x1800d109d  jmp     loc_1800D0E1B
0x1800d10a2  mov     r14, [rbp+0FB0h+var_A60]
0x1800d10a9  mov     rax, r14
0x1800d10ac  shr     rax, 39h
0x1800d10b0  mov     rdi, [rsi+8]
0x1800d10b4  mov     rbx, [rsi+10h]
0x1800d10b8  movd    xmm0, eax
0x1800d10bc  punpcklbw xmm0, xmm0
0x1800d10c0  pshuflw xmm0, xmm0, 0
0x1800d10c5  pshufd  xmm8, xmm0, 0
0x1800d10cb  lea     r15, [rdi-10h]
0x1800d10cf  xor     esi, esi
0x1800d10d1  pcmpeqd xmm9, xmm9
0x1800d10d6  and     r14, rbx
0x1800d10d9  movdqu  xmm10, xmmword ptr [rdi+r14]
0x1800d10df  movdqa  xmm0, xmm10
0x1800d10e4  pcmpeqb xmm0, xmm8
0x1800d10e9  pmovmskb r13d, xmm0
0x1800d10ee  test    r13d, r13d
0x1800d10f1  jnz     short loc_1800D112D
0x1800d10f3  pcmpeqb xmm10, xmm9
0x1800d10f8  pmovmskb eax, xmm10
0x1800d10fd  test    eax, eax
0x1800d10ff  jnz     loc_1800D12E6
0x1800d1105  add     r14, rsi
0x1800d1108  add     r14, 10h
0x1800d110c  add     rsi, 10h
0x1800d1110  jmp     short loc_1800D10D6
0x1800d1120  lea     eax, [r13-1]
0x1800d1124  and     ax, r13w
0x1800d1128  mov     r13d, eax
0x1800d112b  jz      short loc_1800D10F3
0x1800d112d  tzcnt   r12d, r13d
0x1800d1132  add     r12, r14
0x1800d1135  and     r12, rbx
0x1800d1138  mov     rax, r12
0x1800d113b  shl     rax, 4
0x1800d113f  mov     rcx, r15
0x1800d1142  sub     rcx, rax
0x1800d1145  mov     rax, [rcx]
0x1800d1148  mov     r8, [rbp+0FB0h+Size]; Size
0x1800d114f  cmp     r8, [rax+8]
0x1800d1153  jnz     short loc_1800D1120
0x1800d1155  mov     rdx, [rax]; Buf2
0x1800d1158  mov     rcx, [rbp+0FB0h+Src]; Buf1
0x1800d115f  call    memcmp_0
0x1800d1164  test    eax, eax
0x1800d1166  jnz     short loc_1800D1120
0x1800d1168  neg     r12
0x1800d116b  shl     r12, 4
0x1800d116f  mov     rax, [rdi+r12-8]
0x1800d1174  mov     rcx, [rax+28h]
0x1800d1178  mov     rdx, [rax+30h]
0x1800d117c  mov     [rcx+30h], rdx
0x1800d1180  mov     rcx, [rax+28h]
0x1800d1184  mov     [rdx+28h], rcx
0x1800d1188  mov     rsi, [rbp+0FB0h+Address]
0x1800d118f  mov     rcx, [rsi+38h]
0x1800d1193  mov     rdx, [rcx+30h]
0x1800d1197  mov     [rax+30h], rdx
0x1800d119b  mov     [rax+28h], rcx
0x1800d119f  mov     [rcx+30h], rax
0x1800d11a3  mov     rcx, [rax+30h]
0x1800d11a7  mov     [rcx+28h], rax
0x1800d11ab  mov     rcx, [rax+10h]
0x1800d11af  lock inc qword ptr [rcx]
0x1800d11b3  jle     loc_1800D3228
0x1800d11b9  mov     r12, [rax+10h]
0x1800d11bd  mov     rbx, [rax+18h]
0x1800d11c1  mov     edi, [rax+20h]
0x1800d11c4  cmp     byte ptr [rbp+0FB0h+Buf1], 0
0x1800d11cb  mov     r14, [rbp+0FB0h+var_100]
0x1800d11d2  jnz     short loc_1800D11E7
0x1800d11d4  mov     rax, cs:qword_1804B1950
  ... truncated ...
```
