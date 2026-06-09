# CTxtRange::SetCharFormat(CCharFormat const *,ulong,IUndoBuilder *,ulong,ulong,ulong,CBiDiLevel const *,int,bool)

- ea: `0x1800b6598`
- end: `0x1800b89d6`
- name: `?SetCharFormat@CTxtRange@@QEAAJPEBVCCharFormat@@KPEAVIUndoBuilder@@KKKPEBVCBiDiLevel@@H_N@Z`
- size: `9278`
- prototype: `__int64 __usercall@<rax>(CTxtRange *__hidden this@<rcx>, const struct CCharFormat *@<rdx>, unsigned int@<r8d>, struct IUndoBuilder *@<r9>, unsigned int, unsigned int, unsigned int, const struct CBiDiLevel *, int, bool)`
- caller_count: `47`
- callee_count: `92`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012c48`
- `0x180014720`
- `0x180015d8c`
- `0x18001b720`
- `0x18001ef7c`
- `0x18001f1dc`
- `0x18001fd3c`
- `0x1800310b0`
- `0x180062578`
- `0x180064f00`
- `0x180065498`
- `0x1800655d8`
- `0x180092344`
- `0x18009b294`
- `0x18009c09c`
- `0x18009d060`
- `0x1800aaf6c`
- `0x1800b3790`
- `0x1800b49c4`
- `0x1800b526c`
- `0x1800e6568`
- `0x1800e8120`
- `0x1800ff010`
- `0x180118b78`
- `0x18011964c`
- `0x18011afc4`
- `0x180124900`
- `0x18012eeec`
- `0x180132664`
- `0x180153a40`
- `0x180155180`
- `0x180177f50`
- `0x18017c398`
- `0x18017dc00`
- `0x18017e16c`
- `0x18017ee34`
- `0x1801822f0`
- `0x180183178`
- `0x1801835a0`
- `0x180183a94`
- `0x180184ee0`
- `0x1801851ec`
- `0x180185d30`
- `0x180187128`
- `0x1801ad870`
- `0x1801add28`
- `0x1801ae5d8`

## callees

- `0x18000c138`
- `0x180010e30`
- `0x180010e6c`
- `0x1800117e4`
- `0x180013b84`
- `0x180014128`
- `0x180014720`
- `0x180015130`
- `0x1800163bc`
- `0x180016508`
- `0x180016588`
- `0x180016630`
- `0x18001668c`
- `0x1800166fc`
- `0x1800187f0`
- `0x1800189a8`
- `0x1800189e8`
- `0x18001aa80`
- `0x18001b174`
- `0x18001b1b4`
- `0x18001b234`
- `0x18001cdd8`
- `0x18001db40`
- `0x18001ebd0`
- `0x180020474`
- `0x1800205a0`
- `0x180020bfc`
- `0x180021468`
- `0x180023ab0`
- `0x1800258c0`
- `0x18002fc20`
- `0x180032260`
- `0x180032944`
- `0x180032968`
- `0x180034728`
- `0x1800349e8`
- `0x18003acfc`
- `0x18003ada0`
- `0x18003af60`
- `0x18003ec20`
- `0x18003ee3c`
- `0x18003eed4`
- `0x1800425b0`
- `0x180043f2c`
- `0x180043f84`
- `0x18004ad98`
- `0x18004b2c8`
- `0x180053efc`
- `0x1800556a4`
- `0x18005674c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b83d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b8408`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b83d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b8408`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b83a8`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b83c0`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b83f5`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b83a8`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b83c0`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800b83f5`

## pseudocode

```c
__int64 __fastcall CTxtRange::SetCharFormat(
        CTxtRange *this,
        const struct CCharFormat *a2,
        int a3,
        struct IUndoBuilder *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        const struct CBiDiLevel *a8,
        int a9,
        bool a10)
{
  __int16 v10; // bx
  __int64 v13; // rsi
  unsigned int v14; // r12d
  __int64 v15; // r14
  int v16; // ebx
  __int128 v17; // xmm0
  __m128i v18; // xmm2
  __int128 v19; // xmm1
  unsigned int v20; // r15d
  __int128 v21; // xmm0
  bool v22; // al
  int v23; // r10d
  int v24; // eax
  int v25; // r8d
  int v26; // ecx
  int v27; // r12d
  CTxtStory *v28; // r9
  struct IProvideFontInfo *FontInfoProvider; // rax
  int v30; // edx
  int v31; // r8d
  unsigned __int16 v32; // r10
  unsigned __int8 v33; // r11
  __int64 v34; // r11
  int v35; // r10d
  signed int v36; // esi
  const struct CCharFormat *CF; // rdi
  unsigned int v38; // edx
  __int64 result; // rax
  int v40; // ecx
  int v41; // eax
  int v42; // eax
  unsigned int v43; // r8d
  unsigned int v44; // r9d
  int v45; // edx
  int v46; // edx
  int v47; // edx
  bool v48; // zf
  int v49; // eax
  int v50; // ebx
  __int128 *v51; // rdi
  unsigned int v52; // ebx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 FontOptions; // rax
  __int16 FontInfoFlags; // ax
  __int64 v57; // rax
  int v58; // edi
  __int64 v59; // xmm1_8
  int v60; // r9d
  unsigned int v61; // eax
  __int16 v62; // si
  struct CDisplay *v63; // rdx
  unsigned int v64; // esi
  __int64 v65; // rcx
  int v66; // edx
  int v67; // eax
  int v68; // edi
  const struct CParaFormat *PF; // rax
  int v70; // ecx
  int v71; // edx
  int v72; // ecx
  __int128 v73; // xmm0
  unsigned int v74; // ebx
  int v75; // edi
  int v76; // eax
  CAntiEventDispenser *v77; // rcx
  struct IAntiEvent *ReplaceFormattingAE; // rbx
  unsigned int v79; // r10d
  int v80; // r9d
  int v81; // r12d
  char v82; // r11
  __int128 v83; // xmm0
  __int128 v84; // xmm0
  __int16 v85; // ax
  int v86; // r8d
  unsigned int v87; // r10d
  int v88; // r11d
  __int64 v89; // rdx
  __int64 *v90; // rax
  __int64 v91; // xmm0_8
  CRchTxtPtr *v92; // r12
  int IsRich; // eax
  int v94; // r10d
  int TextLength; // eax
  unsigned __int16 v96; // dx
  int v97; // edi
  unsigned __int8 v98; // dl
  int v99; // r8d
  __int16 Format; // ax
  __int16 v101; // ax
  const struct CCharFormat *v102; // rax
  __m128i v103; // xmm9
  unsigned __int8 v104; // r12
  int v105; // ecx
  unsigned __int8 v106; // al
  unsigned int v107; // esi
  unsigned int v108; // edx
  unsigned int v109; // edi
  int CchLeft; // r12d
  int v111; // edi
  unsigned __int16 Char; // ax
  int v113; // ebx
  int v114; // esi
  int v115; // esi
  int v116; // ecx
  unsigned int v117; // ebx
  __int64 v118; // rdx
  unsigned __int8 CharRep; // dl
  const unsigned __int16 *Pch; // rax
  __int16 MathFont; // ax
  int v122; // eax
  __m128i v123; // xmm0
  bool v124; // cc
  unsigned __int8 v125; // al
  __int64 v126; // r10
  char v127; // r11
  __int64 v128; // rbx
  unsigned __int64 v129; // rdi
  int v130; // r12d
  int FontInfoFromFaceName; // eax
  int v132; // ebx
  int v133; // esi
  unsigned __int16 v134; // ax
  int v135; // r11d
  char v136; // r10
  unsigned __int8 v137; // al
  unsigned int v138; // r9d
  int v139; // eax
  int v140; // edi
  int v141; // eax
  int v142; // ecx
  int v143; // edi
  unsigned int v144; // esi
  unsigned int v145; // r12d
  unsigned int v146; // r9d
  unsigned int v147; // r9d
  int Exact; // eax
  unsigned __int16 *Buf; // rbx
  const struct CFontOptions *v150; // rax
  int v151; // r10d
  const unsigned __int16 *v152; // r9
  unsigned __int8 v153; // dl
  int v154; // r12d
  int v155; // r8d
  unsigned int v156; // edi
  __int16 v157; // r11
  char v158; // bl
  int v159; // eax
  int v160; // r10d
  __int16 v161; // dx
  int v162; // esi
  unsigned __int16 *v163; // rbx
  int Text; // edi
  const unsigned __int16 *FontName; // r10
  int v166; // edx
  int v167; // eax
  unsigned int v168; // eax
  struct IFormatCache *v169; // rbx
  const struct CDisplay *v170; // rdx
  bool v171; // r8
  LS *v172; // rcx
  int v173; // ebx
  int v174; // edi
  int v175; // eax
  int v176; // ecx
  __int64 v177; // rax
  CRunPtrBase *v178; // rcx
  int v179; // eax
  __int64 v180; // r11
  CTxtStory *ActiveStory; // rax
  int v182; // eax
  unsigned int v183; // ebx
  unsigned int v184; // edi
  int v185; // eax
  int v186; // eax
  int v187; // eax
  const struct CCharFormat *CharFormat; // rax
  __m128i v189; // xmm2
  int v190; // eax
  int v191; // ebx
  int v192; // eax
  __int16 v193; // bx
  struct IFormatCache *v194; // rbx
  int *v195; // r9
  int v196; // edx
  int v197; // r8d
  CTxtStory *v198; // rbx
  struct IDpiAccessor *v199; // [rsp+38h] [rbp-D0h]
  unsigned int v200; // [rsp+68h] [rbp-A0h]
  unsigned int v201; // [rsp+6Ch] [rbp-9Ch]
  unsigned __int8 v202[4]; // [rsp+70h] [rbp-98h] BYREF
  int v203; // [rsp+74h] [rbp-94h]
  unsigned int v204; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v205; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v206; // [rsp+80h] [rbp-88h]
  int v207; // [rsp+84h] [rbp-84h]
  int v208; // [rsp+88h] [rbp-80h]
  int v209; // [rsp+8Ch] [rbp-7Ch]
  int v210; // [rsp+90h] [rbp-78h]
  int v211; // [rsp+94h] [rbp-74h]
  int v212; // [rsp+98h] [rbp-70h]
  int v213; // [rsp+9Ch] [rbp-6Ch] BYREF
  char v214; // [rsp+A0h] [rbp-68h]
  __int16 v215[2]; // [rsp+A4h] [rbp-64h] BYREF
  unsigned int v216; // [rsp+A8h] [rbp-60h]
  __int16 PrevNonMathFont; // [rsp+ACh] [rbp-5Ch]
  int v218; // [rsp+B0h] [rbp-58h] BYREF
  int v219; // [rsp+B4h] [rbp-54h] BYREF
  int v220; // [rsp+B8h] [rbp-50h]
  int v221; // [rsp+BCh] [rbp-4Ch]
  int v222; // [rsp+C0h] [rbp-48h] BYREF
  int v223; // [rsp+C4h] [rbp-44h] BYREF
  int v224; // [rsp+C8h] [rbp-40h]
  CTxtStory *v225; // [rsp+D0h] [rbp-38h]
  int v226; // [rsp+D8h] [rbp-30h]
  int v227; // [rsp+DCh] [rbp-2Ch]
  int v228; // [rsp+E0h] [rbp-28h]
  int v229; // [rsp+E4h] [rbp-24h] BYREF
  unsigned __int8 v230[16]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v231; // [rsp+F8h] [rbp-10h]
  __m128i v232; // [rsp+108h] [rbp+0h] BYREF
  __int128 v233; // [rsp+118h] [rbp+10h]
  int v234; // [rsp+128h] [rbp+20h]
  int v235; // [rsp+138h] [rbp+30h]
  BOOL v236; // [rsp+13Ch] [rbp+34h]
  int v237; // [rsp+140h] [rbp+38h] BYREF
  int v238; // [rsp+144h] [rbp+3Ch]
  unsigned int v239; // [rsp+148h] [rbp+40h] BYREF
  __int64 v240; // [rsp+150h] [rbp+48h]
  int v241; // [rsp+158h] [rbp+50h] BYREF
  int v242; // [rsp+15Ch] [rbp+54h]
  int v243; // [rsp+160h] [rbp+58h]
  __int16 v244; // [rsp+164h] [rbp+5Ch]
  int v245; // [rsp+168h] [rbp+60h]
  struct IUndoBuilder *v246; // [rsp+170h] [rbp+68h]
  int v247; // [rsp+178h] [rbp+70h] BYREF
  __int128 v248; // [rsp+180h] [rbp+78h] BYREF
  int v249; // [rsp+190h] [rbp+88h]
  int v250; // [rsp+194h] [rbp+8Ch] BYREF
  unsigned int v251; // [rsp+198h] [rbp+90h]
  unsigned int v252; // [rsp+19Ch] [rbp+94h]
  int v253; // [rsp+1A0h] [rbp+98h]
  int v254; // [rsp+1A4h] [rbp+9Ch]
  int v255; // [rsp+1A8h] [rbp+A0h] BYREF
  int v256; // [rsp+1ACh] [rbp+A4h]
  int v257; // [rsp+1B0h] [rbp+A8h]
  struct IFormatCache *v258; // [rsp+1B8h] [rbp+B0h]
  int v259; // [rsp+1C0h] [rbp+B8h]
  int IsBiDiCharRep; // [rsp+1C4h] [rbp+BCh]
  int v261; // [rsp+1C8h] [rbp+C0h]
  int v262; // [rsp+1CCh] [rbp+C4h]
  __int64 v263; // [rsp+1D0h] [rbp+C8h] BYREF
  __int64 v264; // [rsp+1D8h] [rbp+D0h]
  __int64 v265; // [rsp+1E0h] [rbp+D8h]
  __int64 v266; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v267; // [rsp+1F0h] [rbp+E8h]
  __int128 v268; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v269; // [rsp+208h] [rbp+100h]
  __int128 v270; // [rsp+210h] [rbp+108h] BYREF
  __int64 v271; // [rsp+220h] [rbp+118h]
  __int128 v272; // [rsp+228h] [rbp+120h]
  int v273; // [rsp+238h] [rbp+130h]
  unsigned int v274; // [rsp+23Ch] [rbp+134h]
  CNotifyMgr *v275; // [rsp+240h] [rbp+138h]
  _OWORD v276[2]; // [rsp+248h] [rbp+140h] BYREF
  char v277[8]; // [rsp+268h] [rbp+160h] BYREF
  struct IProvideFontInfo *v278; // [rsp+270h] [rbp+168h]
  int *v279; // [rsp+278h] [rbp+170h]
  __int64 v280; // [rsp+280h] [rbp+178h] BYREF
  __int128 v281; // [rsp+288h] [rbp+180h]
  CTxtStory *v282; // [rsp+298h] [rbp+190h]
  __m128i v283; // [rsp+2A8h] [rbp+1A0h] BYREF
  unsigned int v284[4]; // [rsp+2B8h] [rbp+1B0h]
  __int128 v285; // [rsp+2C8h] [rbp+1C0h]
  __int128 v286; // [rsp+2D8h] [rbp+1D0h]
  int v287; // [rsp+2E8h] [rbp+1E0h]
  struct CRchTxtPtr *v288; // [rsp+2F8h] [rbp+1F0h]
  struct CBiDiLevel *v289; // [rsp+300h] [rbp+1F8h]
  _QWORD v290[2]; // [rsp+308h] [rbp+200h] BYREF
  unsigned __int64 CharFlagsHelper; // [rsp+318h] [rbp+210h] BYREF
  unsigned __int64 v292[3]; // [rsp+320h] [rbp+218h] BYREF
  void *Block[2]; // [rsp+338h] [rbp+230h]
  char v294[32]; // [rsp+348h] [rbp+240h] BYREF
  char v295[8]; // [rsp+368h] [rbp+260h] BYREF
  char v296[8]; // [rsp+370h] [rbp+268h] BYREF
  char v297[56]; // [rsp+378h] [rbp+270h] BYREF
  char v298[184]; // [rsp+3B0h] [rbp+2A8h] BYREF
  char *v299; // [rsp+468h] [rbp+360h]
  int v300; // [rsp+470h] [rbp+368h]

  v10 = a3;
  v289 = a8;
  v246 = a4;
  v242 = a3;
  v288 = (CTxtRange *)((char *)this + 8);
  if ( !(unsigned int)CRchTxtPtr::Check_rpCF((CTxtRange *)((char *)this + 8)) )
    return 0;
  v13 = *((_QWORD *)this + 3);
  v14 = a6 | 0x10000;
  if ( (v10 & 0x200) == 0 )
    v14 = a6;
  v200 = v14;
  if ( v13 )
    v15 = *(_QWORD *)(v13 + 40);
  else
    v15 = 0;
  v16 = *((_DWORD *)this + 26);
  v218 = 0;
  memset_0(v230, 0, 0x44u);
  v17 = *((_OWORD *)a2 + 1);
  v18 = *(__m128i *)a2;
  v19 = *((_OWORD *)a2 + 2);
  v287 = *((_DWORD *)a2 + 16);
  v20 = 1;
  *(_OWORD *)v284 = v17;
  v21 = *((_OWORD *)a2 + 3);
  v226 = 0x7FFFFFFF;
  v247 = 0x7FFFFFFF;
  v229 = 0x7FFFFFFF;
  v286 = v21;
  v283 = v18;
  v285 = v19;
  v237 = -1;
  v22 = (*(_BYTE *)(v15 + 276) & 0x40) != 0;
  v23 = _mm_cvtsi128_si32(v18);
  v223 = 0;
  v222 = 0;
  v227 = -1;
  v241 = -1;
  v250 = 0;
  LOBYTE(v244) = v22;
  v235 = v23;
  if ( (v14 & 0x20000000) != 0 || (a5 & 0x20000000) != 0 && (v14 & 0x10000) != 0 )
  {
    v24 = 1;
    v25 = 1;
    if ( (v23 & 0x20000000) != 0 )
    {
      v245 = 1;
      v206 = 1;
      goto LABEL_12;
    }
  }
  else
  {
    v24 = 0;
    v25 = 0;
  }
  v206 = v25;
  v245 = 0;
LABEL_12:
  if ( (v14 & 0x10000000) != 0 || (a5 & 0x10000000) != 0 && (v14 & 0x10000) != 0 )
  {
    v206 = v25;
    v209 = 1;
    if ( (v23 & 0x10000000) != 0 )
    {
      v27 = 1;
      v207 = 1;
LABEL_22:
      v238 = 0;
      goto LABEL_23;
    }
    v26 = 1;
    v206 = v25;
  }
  else
  {
    v26 = 0;
    v209 = 0;
  }
  v207 = 0;
  v27 = 0;
  v238 = 1;
  if ( !v26 )
    goto LABEL_22;
LABEL_23:
  if ( !v24 || (*(_DWORD *)(v15 + 176) & 0x10000) != 0 || (v243 = 1, (a5 & 2) != 0) )
    v243 = 0;
  v28 = (CTxtStory *)(v13 - 8);
  v258 = qword_1802E45A8;
  v215[0] = 0;
  v239 = 0;
  v279 = (int *)((unsigned __int64)&v250 & -(__int64)((v200 & 2) != 0));
  if ( !v13 )
    v28 = 0;
  v225 = v28;
  FontInfoProvider = CTxtEdit::GetFontInfoProvider((CTxtEdit *)v15);
  v278 = FontInfoProvider;
  if ( a10 != v33 || FontInfoProvider && ((v30 & 0x20400003) != 0 || (a7 & 0x400200) != 0) )
    v214 = 1;
  else
    v214 = v33;
  if ( v30 || a7 || (v202[0] = 1, v31 != 16) )
    v202[0] = v33;
  if ( !v27 )
    goto LABEL_42;
  if ( !(unsigned int)CRchTxtPtr::IsRich((CTxtRange *)((char *)this + 8)) )
    return 0;
  v266 = 0x1000000;
  v267 = v34;
  CTxtEdit::OrCharFlags(v15, &v266, 0);
  LOWORD(v30) = a5;
  v32 = v235;
LABEL_42:
  PrevNonMathFont = -1;
  v235 = (unsigned __int16)v30 & v32 & 0x100;
  if ( ((unsigned __int16)v30 & v32 & 0x100) != 0 )
  {
    CCFRunPtr::CCFRunPtr((CCFRunPtr *)&v268, (CTxtRange *)((char *)this + 8));
    CTxtRange::CheckILSObject(this, (struct CCFRunPtr *)&v268, 0);
    v16 = *((_DWORD *)this + 26);
  }
  v35 = 0;
  v36 = a7 & 0xFFFFFE0;
  if ( (*(_BYTE *)(v15 + 358) & 0x20) != 0 )
    v36 = a7;
  if ( (*(_BYTE *)(v15 + 184) & 0x40) != 0 )
    v200 |= 8u;
  if ( !v238 )
    goto LABEL_68;
  if ( *((int *)this + 26) > 0 )
    CRunPtrBase::AdjustBackward((CTxtRange *)((char *)this + 64));
  CF = CRchTxtPtr::GetCF((CTxtRange *)((char *)this + 8));
  CRunPtrBase::AdjustForward((CTxtRange *)((char *)this + 64));
  if ( *((_DWORD *)this + 26)
    && CCharFormat::IsMathZonePlaceHolder(CF)
    && !(unsigned int)CTxtRange::WriteAccessDenied(this, v38) )
  {
    CTxtRange::SetCp(this, *((_DWORD *)this + 10) - 1, 0);
    (*(void (__fastcall **)(CTxtRange *, __int64))(*(_QWORD *)this + 200LL))(this, 20);
    return (*(__int64 (__fastcall **)(CTxtRange *, _QWORD, _QWORD, struct IUndoBuilder *, int, _QWORD, _DWORD, _DWORD))(*(_QWORD *)this + 888LL))(
             this,
             0,
             0,
             v246,
             1,
             0,
             0,
             0);
  }
  if ( *((_BYTE *)CF + 5) != 0x80 )
  {
    PrevNonMathFont = *((_WORD *)CF + 3);
    v239 = *((_DWORD *)CF + 6);
  }
  if ( (*(_DWORD *)CF & 0x10000000) != 0 )
    PrevNonMathFont = CTxtRange::GetPrevNonMathFont(this, &v239, &v202[1]);
  v40 = *((_DWORD *)this + 26);
  v35 = 0;
  if ( !v40 || (*((_DWORD *)this + 29) & 0x60000) != 0 )
    goto LABEL_68;
  if ( v40 == 1 )
  {
    v41 = CTxtPtr::IsAfterEOP((CTxtRange *)((char *)this + 24));
    v35 = 0;
    if ( v41 )
    {
LABEL_68:
      v44 = v200;
      v43 = a5;
      goto LABEL_69;
    }
    v40 = *((_DWORD *)this + 26);
  }
  if ( v40 == -1 )
  {
    v42 = CTxtPtr::IsAtEOP((CTxtRange *)((char *)this + 24));
    v35 = 0;
    if ( v42 )
      goto LABEL_68;
  }
  v43 = a5;
  v200 &= 0xC7FFFFFF;
  v44 = v200;
  if ( (v200 & 0x10000) != 0 )
  {
    v43 = a5 & 0xC7FFFFFF;
    a5 &= 0xC7FFFFFF;
  }
LABEL_69:
  v45 = *(_DWORD *)(v15 + 176);
  v254 = 0;
  v257 = 0;
  v202[1] = 0;
  if ( (v45 & 0x10) != 0 || CTxtEdit::FDisableMath((CTxtEdit *)v15) )
  {
    v200 = v44 & 0xEFFFFFFF;
    if ( (v44 & 0x10000) != 0 )
    {
      v43 &= ~0x10000000u;
      a5 = v43;
    }
  }
  if ( (v45 & 0x10000) == 0 && (v43 & 0x8000000C) != 0 && (v43 & 0x7FFFFFF3) == 0 )
  {
    if ( *((_DWORD *)this + 26) == v35 )
    {
      if ( (*(_DWORD *)CRchTxtPtr::GetCFBackward((CTxtRange *)((char *)this + 8)) & 0x10000000) == 0 )
        goto LABEL_87;
      v48 = (*(_DWORD *)CRchTxtPtr::GetCF((CTxtRange *)((char *)this + 8)) & 0x10000000) == 0;
    }
    else
    {
      CCFRunPtr::CCFRunPtr((CCFRunPtr *)v276, (CTxtRange *)((char *)this + 8));
      v46 = *((_DWORD *)this + 26);
      if ( v46 > 0 )
        CRunPtrBase::Move((CRunPtrBase *)v276, -v46);
      if ( (*(_DWORD *)CCFRunPtr::GetCF((CCFRunPtr *)v276) & 0x10000000) != 0 )
        goto LABEL_86;
      v47 = -*((_DWORD *)this + 26);
      if ( *((int *)this + 26) > 0 )
        v47 = *((_DWORD *)this + 26);
      CRunPtrBase::Move((CRunPtrBase *)v276, v47);
      CRunPtrBase::AdjustBackward((CRunPtrBase *)v276);
      v48 = (*(_DWORD *)CCFRunPtr::GetCF((CCFRunPtr *)v276) & 0x10000000) == 0;
    }
    if ( !v48 )
    {
LABEL_86:
      v205 = 0;
      v219 = 0;
      CTxtRange::FindAttributes(this, (int *)&v205, &v219, -1879048192);
      CTxtRange::Set(this, v205, v205 - v219);
      v16 = *((_DWORD *)this + 26);
    }
LABEL_87:
    v35 = 0;
  }
  v49 = *((_DWORD *)this + 26);
  v203 = v49;
  if ( v49 > 0 )
  {
    v50 = v49;
    v220 = -v49;
LABEL_93:
    v51 = (__int128 *)((char *)this + 24);
    goto LABEL_94;
  }
  v50 = -v16;
  v220 = v35;
  if ( v49 < 0 )
  {
    CRunPtrBase::AdjustForward((CTxtRange *)((char *)this + 64));
LABEL_92:
    v203 = v50;
    goto LABEL_93;
  }
  if ( v50 || (v242 & 0xA) == 0 )
    goto LABEL_92;
  if ( (v242 & 2) != 0 )
  {
    CTxtRange::FindWord(this, &v223, &v222, 1);
    v58 = v223;
    if ( v223 < *((_DWORD *)this + 10) )
    {
      v203 = v222;
      if ( *((_DWORD *)this + 10) < v222 )
      {
        v205 = 0;
        CTxtRange::CTxtRange((CTxtRange *)v295, this);
        CTxtRange::Set((CTxtRange *)v295, v58, v58 - v203);
        v257 = CTxtRange::WriteAccessDenied((CTxtRange *)v295, 0);
        if ( !v257
          && ((*(_DWORD *)(v15 + 176) & 0x80000) == 0
           || (a5 & CTxtRange::GetCharFormat((CTxtRange *)v295, (struct CCharFormat *)v230, 0, &v205, 0)) == a5
           && (v205 & v36) == v36) )
        {
          v220 = v58 - *((_DWORD *)this + 10);
          v50 = v203 - v58;
        }
        v203 = v50;
        CTxtRange::~CTxtRange((CTxtRange *)v295);
        goto LABEL_93;
      }
    }
  }
  v51 = (__int128 *)((char *)this + 24);
  if ( !(unsigned int)CTxtPtr::IsAtEOP((CTxtRange *)((char *)this + 24))
    || *((_WORD *)CRchTxtPtr::GetPF((CTxtRange *)((char *)this + 8)) + 28) )
  {
    v203 = 0;
  }
  else
  {
    v59 = *((_QWORD *)this + 5);
    v268 = *v51;
    v269 = v59;
    v203 = CTxtPtr::AdvanceCRLF(&v268, 2);
    v50 = v203;
    CRunPtrBase::AdjustForward((CTxtRange *)((char *)this + 64));
    v200 |= 0x1000u;
    v254 = 1;
  }
LABEL_94:
  v218 = v50;
  v52 = a5;
  if ( (a5 & 0x2000000) != 0 && (unsigned int)CW32System::IsBiDiLcid(v284[2]) )
  {
    LOBYTE(v53) = CCharFormat::CharRepFromLang((CCharFormat *)&v283);
    v276[0] = *(_OWORD *)CCharFlags::FontSigFromCharRep(v290, v53);
    CTxtEdit::OrCharFlags(v15, v276, 0);
  }
  if ( (*(_DWORD *)(v15 + 280) & 0x200) == 0 && (*(_BYTE *)(v15 + 358) & 1) == 0 )
  {
    if ( v27
      || (a5 & 0x20000000) != 0
      && (CTxtEdit::FGlyphAll((CTxtEdit *)v15)
       || (FontOptions = CTxtEdit::GetFontOptions(v54, &v268),
           FontInfoFlags = CFICache::GetFontInfoFlags(v283.m128i_u16[3], FontOptions),
           (FontInfoFlags & 0x100) != 0)
       || (FontInfoFlags & 0x200) != 0 && (*(_BYTE *)(v15 + 284) & 0x10) != 0) )
    {
      CTxtEdit::OnSetTypographyOptions((CTxtEdit *)v15, 1u, 1);
    }
  }
  if ( (v36 & 0xB000001F) != 0
    && (*(_BYTE *)(v15 + 358) & 1) == 0
    && (((unsigned __int8)v36 & BYTE4(v286) & 0x1F) != 0
     || (v36 & 0x10000000) != 0 && BYTE11(v286)
     || v36 < 0 && BYTE9(v286)
     || (v36 & 0x20000000) != 0 && BYTE8(v286) && (v57 = *(_QWORD *)(v15 + 256)) != 0 && *(_QWORD *)(v57 + 64)) )
  {
    if ( (v36 & 0xFFFFFFE3) != 0 || (*((_BYTE *)v225 + 71) & 4) != 0 )
      CTxtEdit::OnSetTypographyOptions((CTxtEdit *)v15, 1u, 1);
    else
      *(_DWORD *)(v15 + 280) |= 0x4000u;
  }
  if ( v27 )
  {
    v267 = 0;
    v266 = 0x1000000;
    CTxtEdit::OrCharFlags(v15, &v266, v246);
  }
  v256 = CCharFormat::fSetStyle((CCharFormat *)&v283, a5, v200);
  v61 = v36 | (((*(unsigned __int16 *)(v15 + 276) >> 6) & 1) << 17);
  v62 = 2600;
  v216 = v61;
  if ( v203 == v60 )
    goto LABEL_505;
  v63 = *(struct CDisplay **)(v15 + 136);
  v228 = v60;
  v64 = v60;
  v213 = v60;
  CFreezeDisplay::CFreezeDisplay((CFreezeDisplay *)v277, v63);
  v280 = 0;
  *(_QWORD *)&v281 = 0;
  DWORD2(v281) = 0;
  v282 = 0;
  if ( (v242 & 0x40000000) != 0 )
  {
    v275 = 0;
    goto LABEL_152;
  }
  v65 = *(_QWORD *)(((*(_QWORD *)v51 - 8LL) & -(__int64)(*(_QWORD *)v51 != 0)) + 0x30);
  v275 = (CNotifyMgr *)((v65 + 232) & -(__int64)(v65 != 0));
  if ( !v275 )
  {
LABEL_152:
    v68 = v220;
    goto LABEL_153;
  }
  CTxtRange::CTxtRange((CTxtRange *)v295, this);
  v66 = *((_DWORD *)this + 10);
  if ( *((int *)this + 26) > 0 )
    v66 = *((_DWORD *)this + 10) - *((_DWORD *)this + 26);
  CTxtRange::SetCp((CTxtRange *)v295, v66, 0);
  v282 = v225;
  v67 = *((_DWORD *)this + 10);
  v280 = 0;
  v68 = v220;
  v228 = v220 + v67;
  v281 = 0;
  PF = CRchTxtPtr::GetPF((CRchTxtPtr *)v296);
  if ( !*((_WORD *)PF + 28) || (*((_WORD *)PF + 21) & 0x400) != 0 )
    goto LABEL_149;
  v219 = 0;
  v205 = 0;
  CTxtRange::FindParagraph((CTxtRange *)v295, &v219, (int *)&v205, 1);
  v70 = *((_DWORD *)this + 10);
  if ( *((int *)this + 26) < 0 )
    v70 = *((_DWORD *)this + 10) - *((_DWORD *)this + 26);
  if ( (int)v205 > v70 )
  {
LABEL_149:
    v72 = v218;
    v71 = v228;
  }
  else
  {
    v71 = v219;
    v72 = v228 - v219 + v218;
    v228 = v219;
    v218 = v72;
  }
  CNotifyMgr::NotifyPreReplaceRange(
    v275,
    (CTxtRange *)((char *)this + 8),
    0x3FFFFFFF,
    0,
    0,
    v71,
    v71 + v72,
    (struct tagNOTIFY_DATA *)&v280);
  CTxtRange::~CTxtRange((CTxtRange *)v295);
LABEL_153:
  CRunPtrBase::Move((CTxtRange *)((char *)this + 64), v68);
  v73 = *((_OWORD *)this + 4);
  v208 = v68 + *((_DWORD *)this + 10);
  v248 = v73;
  if ( v246 )
  {
    v74 = 0;
    v205 = 0;
    if ( (*((_BYTE *)v225 + 71) & 1) != 0 )
    {
      CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v295, (CTxtRange *)((char *)this + 8));
      if ( v68 )
      {
        CRunPtrBase::Move((CRunPtrBase *)v298, v68);
        CTxtPtrEx::Move((CTxtPtrEx *)v297, v68);
      }
      v76 = CRchTxtPtr::ExpandRangeFormatting((CRchTxtPtr *)v295, v203, 0, (int *)&v205);
      v74 = v205;
      v75 = v76;
    }
    else
    {
      v75 = 0;
    }
    CRunPtrBase::Move((CRunPtrBase *)&v248, v75);
    ReplaceFormattingAE = CAntiEventDispenser::CreateReplaceFormattingAE(
                            v77,
                            (struct CTxtEdit *)v15,
                            v75 + v208,
                            (struct CFormatRunPtr *)&v248,
                            v203 + v74 - v75,
                            v258,
                            0);
    CRunPtrBase::Move((CRunPtrBase *)&v248, -v75);
    if ( ReplaceFormattingAE )
      (*(void (__fastcall **)(struct IUndoBuilder *, struct IAntiEvent *))(*(_QWORD *)v246 + 8LL))(
        v246,
        ReplaceFormattingAE);
    v52 = a5;
  }
  v79 = v200;
  v224 = 0;
  v240 = 0;
  v263 = 0;
  v265 = 0;
  v264 = 0;
  v251 = v52;
  v252 = v200;
  v274 = v216;
  IsBiDiCharRep = 0;
  v259 = 0;
  if ( (v200 & 0x100) == 0 || (v221 = 1, (*((_BYTE *)v225 + 70) & 0x78) != 0) )
    v221 = 0;
  if ( !v27 || (v52 & 1) != 0 )
  {
    v212 = 0;
    if ( !v27 )
    {
LABEL_170:
      v253 = 0;
      goto LABEL_171;
    }
  }
  else
  {
    v212 = 1;
  }
  v253 = 1;
  if ( (v52 & 2) != 0 )
    goto LABEL_170;
LABEL_171:
  if ( (v216 & 0x800000) == 0 || (v219 = 1, (BYTE12(v286) & 0x40) == 0) )
    v219 = 0;
  LOBYTE(v80) = v283.m128i_i8[4];
  v81 = v52 & 0x8000000;
  v236 = 0;
  v205 = v52 & 0x8000000;
  LOBYTE(v223) = 0;
  v210 = -1;
  v262 = 1;
  if ( (v52 & 0x8000000) != 0 && (v200 & 0x10000) == 0 )
  {
    v223 = v283.m128i_u8[4];
    IsBiDiCharRep = CW32System::IsBiDiCharRep(v283.m128i_u8[4]);
    v259 = (unsigned int)(v80 - 12) <= 3;
    v236 = (_BYTE)v80 == 10 || v82 == 17;
  }
  v83 = *(_OWORD *)((char *)this + 24);
  v271 = *((_QWORD *)this + 5);
  v261 = 0;
  v222 = 0;
  v270 = v83;
  v84 = *((_OWORD *)this + 3);
  *(_OWORD *)Block = 0;
  v272 = v84;
  if ( !v221 )
  {
    v85 = *(_WORD *)(v15 + 278);
    if ( (v85 & 2) != 0 && (v52 & 0x20000000) != 0 && (v79 & 0x10000) == 0 )
    {
      v221 = 1;
      if ( (v85 & 0x200) != 0 )
      {
        v261 = 1;
        if ( !v81 || (v222 = 1, (_BYTE)v80) )
          v222 = 0;
      }
    }
  }
  CFontOptions::CFontOptions((CFontOptions *)&v268, (const struct CTxtEdit *)v15);
  if ( v88 && !v86 && (v52 & 0x20000000) != 0 )
  {
    CFICache::GetFontInfoFromFaceName(
      v283.m128i_i16[3],
      (const struct CFontOptions *)&v268,
      (struct CCharFlags *)&v263,
      0);
    v240 = v263;
    v265 = v264;
    if ( !v263 && !v264 && v81 )
    {
      LOBYTE(v89) = v283.m128i_i8[4];
      v90 = (__int64 *)CCharFlags::FontSigFromCharRep(v276, v89);
      v91 = v90[1];
      v240 = *v90;
      v265 = v91;
    }
    v87 = v200;
  }
  if ( (*(_BYTE *)(v15 + 278) & 2) != 0 && (v87 & 0x2000) == 0 )
    v200 = v87 | 0x1000;
  v92 = (CTxtRange *)((char *)this + 8);
  IsRich = CRchTxtPtr::IsRich((CTxtRange *)((char *)this + 8));
  v94 = 0;
  if ( IsRich )
  {
    TextLength = CTxtPtr::GetTextLength((CTxtRange *)((char *)this + 24));
    v97 = v203;
    if ( v203 + v208 == TextLength && ((unsigned __int16)v52 & v96 & 0x120) != 0 )
      v97 = --v203;
  }
  else
  {
    v97 = v203;
  }
  *(_DWORD *)v230 = v94;
  if ( v97 <= 0 )
  {
LABEL_468:
    free(Block[1]);
    CRunPtrBase::AdjustBackward((CTxtRange *)((char *)this + 64));
    CRunPtrBase::AdjustForward((CRunPtrBase *)&v248);
    if ( (unsigned int)CFormatRunPtr::MergeRuns((CFormatRunPtr *)&v248, *((_DWORD *)this + 18), v258) && v279 )
    {
      CTxtRange::GetRange(this, &v247, &v241);
      v227 = v241;
      v226 = v247;
    }
    v178 = (CTxtRange *)((char *)this + 64);
    if ( v220 )
      CRunPtrBase::Move(v178, -v220);
    else
      CRunPtrBase::AdjustForward(v178);
    v179 = CRchTxtPtr::IsRich(v92);
    v180 = 0;
    if ( v179 )
    {
      if ( *(_WORD *)(v15 + 56) )
      {
        if ( (-(__int64)(v15 != 0) & (v15 + 48)) != 0 )
        {
          ActiveStory = CTxtEdit::GetActiveStory((CTxtEdit *)v15);
          if ( v225 == ActiveStory && (v202[0] == (_BYTE)v180 || v202[1] != (_BYTE)v180) )
            CCallMgrCenter::SetChangeEvent((v15 + 48) & -(__int64)(v15 != 0), 0);
        }
      }
    }
    if ( v275 )
    {
      HIDWORD(v280) = v251;
      LODWORD(v281) = v252;
      v182 = v280;
      if ( (v216 & 0xFFFFFFBF) != 0 )
        v182 = 2;
      LODWORD(v280) = v182;
      CNotifyMgr::NotifyPostReplaceRange(
        v275,
        v92,
        0x3FFFFFFF,
        0,
        v180,
        v228,
        v218 + v228 - v97,
        (struct tagNOTIFY_DATA *)&v280);
      v180 = 0;
    }
    v183 = *((_DWORD *)this + 26);
    v184 = *((_DWORD *)this + 10);
    if ( (*(_DWORD *)(v15 + 184) & 0x40000000) == 0
      && (*((_DWORD *)this + 29) & 0x20000) == 0
      && v229 < v208
      && (v200 & 0x2080) == 0
      && (*((_DWORD *)this + 29) & 0x40000) == 0 )
    {
      v185 = CTxtRange::SetMathCharFormat(this, v246, &v229, &v237, &v218, v253, v212, v238);
      v180 = 0;
      if ( !v185 )
      {
        v186 = v229;
        if ( v226 < v229 )
          v186 = v226;
        v226 = v186;
        v187 = v237;
        if ( v227 > v237 )
          v187 = v227;
        v227 = v187;
      }
    }
    if ( v246
      && v242 >= (int)v180
      && (*((_BYTE *)this + 116) & 0x40) != 0
      && (v202[0] == (_BYTE)v180 || v202[1] != (_BYTE)v180) )
    {
      HandleSelectionAEInfo(v15, v246, v184, v183, *((_DWORD *)this + 10), *((_DWORD *)this + 26), 2, v180);
    }
    if ( !*((_DWORD *)this + 26) )
    {
      if ( v254 )
      {
        CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)v277);
        v52 = a5;
        v62 = 2600;
LABEL_505:
        CharFormat = CTxtEdit::GetCharFormat((CTxtEdit *)v15, *((_WORD *)this + 56));
        *(_OWORD *)v230 = *(_OWORD *)CharFormat;
        v189 = *(__m128i *)v230;
        v231 = *((_OWORD *)CharFormat + 1);
        v232 = *((__m128i *)CharFormat + 2);
        v233 = *((_OWORD *)CharFormat + 3);
        v234 = *((_DWORD *)CharFormat + 16);
        CFontOptions::CFontOptions((CFontOptions *)&v268, (const struct CTxtEdit *)v15);
        v190 = _mm_cvtsi128_si32(v189);
        if ( (v190 & 0x20) != 0 && *(_QWORD *)(v15 + 248) && (*(_DWORD *)(v15 + 176) & 0x10000) == 0 )
          a5 = v52 & 0xFFFFFFDF;
        if ( (v190 & 0x10000000) == 0 || (v191 = 1, (_mm_cvtsi128_si32(_mm_srli_si128(v189, 5)) & 0xF0) != 0x80) )
          v191 = 0;
        if ( v256 )
          CCharFormat::ApplyDefaultStyle((CCharFormat *)v230, (__int16)v285, (const struct CFontOptions *)&v268);
        result = CCharFormat::Apply(
                   (CCharFormat *)v230,
                   (const struct CCharFormat *)&v283,
                   a5,
                   v200 | 0x1000,
                   v216,
                   v278,
                   *(const struct IDpiAccessor **)(v15 + 568));
        if ( (_DWORD)result )
          return result;
        if ( CTxtEdit::FIdealLayout((CTxtEdit *)v15) )
        {
          if ( *(__int16 *)&v230[8] < 2600 )
            v62 = *(_WORD *)&v230[8];
          *(_WORD *)&v230[8] = v62;
        }
        if ( v243 )
        {
          if ( (*(_DWORD *)v230 & 0x10000000) != 0 )
          {
            v192 = *(_DWORD *)v230 | 2;
            *(_DWORD *)v230 = v192;
            if ( (v192 & 0x20000000) != 0 )
              *(_DWORD *)v230 = v192 & 0xFFFFFFFD;
          }
        }
        if ( v238 )
        {
          if ( v191 )
          {
            v193 = PrevNonMathFont;
            if ( (CFICache::GetFontInfoFlags((unsigned __int16)PrevNonMathFont, &v268) & 0x80u) == 0LL )
            {
              DWORD2(v231) = v239;
              *(_WORD *)&v230[6] = v193;
              v230[5] = 0;
            }
          }
        }
        v194 = v258;
        result = (*(__int64 (__fastcall **)(struct IFormatCache *, unsigned __int8 *, __int16 *))(*(_QWORD *)v258 + 24LL))(
                   v258,
                   v230,
                   v215);
        if ( (_DWORD)result )
          return result;
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v194 + 8LL))(
          v194,
          *((unsigned __int16 *)this + 56));
        v64 = v257 != 0;
        *((_WORD *)this + 56) = v215[0];
LABEL_529:
        v195 = (int *)((char *)this + 40);
        if ( (*((_BYTE *)this + 116) & 0x40) != 0
          && (unsigned int)CRchTxtPtr::IsRich((CTxtRange *)((char *)this + 8))
          && (*(_DWORD *)(v15 + 176) & 0x80000) == 0
          && *(_WORD *)(v15 + 56)
          && (-(__int64)(v15 != 0) & (v15 + 48)) != 0
          && (!v202[0] || v202[1]) )
        {
          CCallMgrCenter::SetSelectionChanged((CCallMgrCenter *)((v15 + 48) & -(__int64)(v15 != 0)));
        }
        if ( v279 )
        {
          if ( v227 >= 0 )
          {
            v196 = v226;
            v197 = v226 - v227;
          }
          else
          {
            v196 = *v195;
            v197 = 0;
          }
          CTxtRange::Set(this, v196, v197);
        }
        if ( v64 || !v203 )
          return v64;
        return v20;
      }
      CTxtRange::Update_iFormat(this, -1);
    }
    v198 = v225;
    v255 = 0;
    (*(void (__fastcall **)(CTxtStory *, int *))(*(_QWORD *)v225 + 56LL))(v225, &v255);
    if ( (v200 & 0x2800) == 0
      && v218
      && !v64
      && !v203
      && CTxtStory::IsComplexScript(v198)
      && v255 != 127
      && (!v202[0] || v202[1]) )
    {
      CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v295, v288);
      CRchTxtPtr::Move((CRchTxtPtr *)v295, v220 + v218);
      CRchTxtPtr::ItemizeReplaceRange((CRchTxtPtr *)v295, v218, 0, v246, 0, 0);
      v20 = 0;
      goto LABEL_550;
    }
    CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)v277);
    goto LABEL_529;
  }
  while ( 1 )
  {
    if ( !(unsigned int)CRunPtrBase::IsValid((CRunPtrBase *)&v248) )
      goto LABEL_467;
    if ( (v99 & 0x1000000) != 0
      && ((unsigned __int8)v52 & v98 & 3) != 0
      && CCharFormat::IsMathZonePlaceHolder((CCharFormat *)v230) )
    {
      while ( 1 )
      {
        Format = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v248);
        if ( (*(_DWORD *)CTxtEdit::GetCharFormat((CTxtEdit *)v15, Format) & 0x20000000) == 0 )
          break;
        if ( v97 <= 0 )
          goto LABEL_467;
        v97 -= CRunPtrBase::GetCchLeft((CRunPtrBase *)&v248);
        v203 = v97;
        CRunPtrBase::NextRun((CRunPtrBase *)&v248);
      }
      if ( v97 <= 0 )
      {
LABEL_467:
        v92 = (CTxtRange *)((char *)this + 8);
        goto LABEL_468;
      }
    }
    v101 = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v248);
    v102 = CTxtEdit::GetCharFormat((CTxtEdit *)v15, v101);
    v103 = *(__m128i *)v102;
    *(_OWORD *)v230 = *(_OWORD *)v102;
    v231 = *((_OWORD *)v102 + 1);
    v232 = *((__m128i *)v102 + 2);
    v233 = *((_OWORD *)v102 + 3);
    v234 = *((_DWORD *)v102 + 16);
    if ( v256 )
    {
      CCharFormat::ApplyDefaultStyle((CCharFormat *)v230, (__int16)v285, (const struct CFontOptions *)&v268);
      v103 = *(__m128i *)v230;
    }
    if ( PrevNonMathFont < 0 || (v52 & 0x20000000) != 0 )
    {
      v104 = _mm_cvtsi128_si32(_mm_srli_si128(v103, 5));
    }
    else
    {
      v104 = _mm_cvtsi128_si32(_mm_srli_si128(v103, 5));
      if ( (v104 & 0xF0) == 0x80 )
      {
        v104 = 0;
        *(_WORD *)&v230[6] = PrevNonMathFont;
        v230[5] = 0;
        v103 = *(__m128i *)v230;
        DWORD2(v231) = v239;
        LOWORD(v204) = PrevNonMathFont;
        goto LABEL_222;
      }
    }
    LOWORD(v204) = _mm_extract_epi16(v103, 3);
LABEL_222:
    v105 = v210;
    v106 = _mm_cvtsi128_si32(_mm_srli_si128(_mm_load_si128(&v232), 12));
    v107 = _mm_cvtsi128_si32(v103);
    if ( v210 == -1 )
    {
      v105 = v106;
      v210 = v106;
      if ( (v107 & 0x1000000) != 0 )
      {
        v105 = v106 - 1;
        v210 = v105;
LABEL_226:
        v108 = v216 & 0xFEFFFFFF;
        v216 &= ~0x1000000u;
        if ( v106 > v105 + 1 && v219 )
          v216 = v108 & 0xFF7FFFFF;
        goto LABEL_232;
      }
    }
    else if ( (v107 & 0x1000000) != 0 )
    {
      goto LABEL_226;
    }
    if ( v106 > v105 && v219 )
      v216 &= ~0x800000u;
LABEL_232:
    v201 = v97;
    if ( !v235 && !v207 && !v245 )
    {
      v109 = v200;
      if ( (v107 & 0x800120) == 0x800120 )
      {
        v52 &= ~0x100u;
        a5 = v52;
      }
      goto LABEL_268;
    }
    if ( (v107 & 0x800000) != 0 )
    {
      v52 &= ~0x100u;
LABEL_242:
      a5 = v52;
      goto LABEL_267;
    }
    if ( v235 && (v107 & 0x20) != 0 )
    {
      v52 |= 0x20u;
      goto LABEL_242;
    }
    if ( v224 )
    {
      v201 = v224;
      v224 = 0;
      if ( (v200 & 0x10000) != 0 )
        v52 &= 0xC7FFFEFF;
      else
        v52 &= ~0x100u;
      v109 = v200 & 0xC7FFFFFF;
      a5 = v52;
      v200 &= 0xC7FFFFFF;
      goto LABEL_268;
    }
    CTxtPtrEx::SetCp((CTxtPtrEx *)&v270, v208);
    CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v248);
    if ( v97 < CchLeft )
      CchLeft = v97;
    v111 = 0;
    if ( CchLeft <= 0 )
    {
LABEL_264:
      v111 = v201;
    }
    else
    {
      while ( 1 )
      {
        Char = CTxtPtr::GetChar((CTxtPtr *)&v270);
        if ( Char == 7 )
          break;
        v113 = Char;
        if ( v245 )
        {
          if ( (unsigned int)Char - 64976 <= 0x1F )
            break;
        }
        v114 = v210;
        if ( (unsigned int)Char - 65529 <= 2 && (unsigned int)CTxtPtr::IsAtTRD((CTxtPtr *)&v270, 0) )
        {
          v116 = v207;
          v224 = 2;
          v210 = v114;
LABEL_272:
          v207 = v116;
LABEL_273:
          v201 = v111;
          goto LABEL_265;
        }
        v115 = CTxtPtrEx::AdvanceCRLF(&v270, 0);
        if ( (unsigned int)(v113 - 10) > 3 )
        {
          v116 = v207;
        }
        else
        {
          if ( (unsigned int)CTxtPtr::IsAtTRD((CTxtPtr *)&v270, 0xFFF9u) )
          {
            v224 = v115 + 2;
            goto LABEL_273;
          }
          v116 = v207;
          if ( v207 && !v235 )
          {
            v224 = 1;
            goto LABEL_272;
          }
        }
        v111 += v115;
        if ( v111 >= CchLeft )
        {
          v207 = v116;
          goto LABEL_264;
        }
      }
      v224 = 1;
      v201 = v111;
    }
LABEL_265:
    v52 = a5;
    if ( v111 )
      break;
    v64 = v213;
LABEL_457:
    v97 = v203;
    if ( v203 <= 0 )
      goto LABEL_467;
  }
  v104 = v230[5];
  v107 = *(_DWORD *)v230;
  v103 = *(__m128i *)v230;
  LOWORD(v204) = *(_WORD *)&v230[6];
LABEL_267:
  v109 = v200;
LABEL_268:
  v211 = 1;
  if ( (v107 & 0x40000) != 0 )
  {
    v117 = v52 & 0xD5FFFFFF;
    a5 = v117;
    goto LABEL_270;
  }
  if ( (*(_DWORD *)(v15 + 176) & 0x10000) != 0
    || !v207
    || (v104 & 0xF0) == 0x80
    || (v109 & 0x10000) == 0 && (a5 & 0x20000000) != 0 && (v283.m128i_i8[5] & 0xF0) == 0x80 )
  {
    v117 = a5;
    if ( !v221
      && ((v107 & 0x10000000) == 0
       || (v109 & 0x10000) != 0
       || (a5 & 0x20000000) == 0
       || (v283.m128i_i8[5] & 0xF0) == 0x80) )
    {
LABEL_270:
      LODWORD(v118) = v201;
      v230[4] = _mm_cvtsi128_si32(_mm_srli_si128(v103, 4));
      goto LABEL_387;
    }
    v122 = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v248);
    v123 = _mm_srli_si128(v103, 4);
    if ( (int)v201 < v122 )
      v122 = v201;
    v124 = v203 < v122;
    v118 = (unsigned int)v122;
    v125 = _mm_cvtsi128_si32(v123);
    if ( v124 )
      v118 = (unsigned int)v203;
    v201 = v118;
    v230[4] = v125;
    if ( v125 == 10 && (v109 & 1) != 0 )
    {
      if ( v236 )
        goto LABEL_387;
      v117 = a5 & 0xF7FFFFFF;
      a5 = v117;
      if ( (v117 & 0x20000000) == 0 )
        goto LABEL_387;
      if ( CFICache::IsSymbolFont(v283.m128i_i16[3], (const struct CFontOptions *)&v268) )
      {
        v117 &= ~0x20000000u;
        a5 = v117;
      }
LABEL_305:
      v107 = *(_DWORD *)v230;
      goto LABEL_289;
    }
    if ( v236 )
      goto LABEL_387;
    LOBYTE(v118) = v230[4];
    CCharFlags::FontSigFromCharRep(v290, v118);
    v128 = v290[0];
    v129 = v290[0] & 0xFFFFFFFFFFFFFF3FuLL;
    if ( (v107 & 0x30000000) == 0x10000000 && (v104 & 0xF0) == 0x80 && (v127 & 0xF0) != 0x80 )
    {
      v266 = v126;
      v267 = v126;
      v130 = 1;
      FontInfoFromFaceName = CFICache::GetFontInfoFromFaceName(
                               v204,
                               (const struct CFontOptions *)&v268,
                               (struct CCharFlags *)&v266,
                               0);
      LODWORD(v126) = 0;
      if ( !FontInfoFromFaceName )
        v129 &= ~v266;
    }
    else
    {
      v130 = v126;
    }
    if ( (v240 & v128) != 0 || (v132 = v126, (v265 & v290[1]) != 0) )
      v132 = 1;
    if ( v259 != (_DWORD)v126 || (v133 = v126, (v240 & 0x7800000000F00000LL) != 0) )
      v133 = 1;
    if ( (unsigned int)v230[4] - 12 <= 3 || (v204 = v126, (unsigned int)v230[4] - 46 <= 3) )
      v204 = 1;
    a5 &= ~0x8000000u;
    CTxtPtrEx::SetCp((CTxtPtrEx *)&v270, v208);
    v134 = CTxtPtr::GetChar((CTxtPtr *)&v270);
    if ( (unsigned int)v134 - 57344 <= 0x18FF )
    {
      v117 = a5;
      LODWORD(v118) = v201 - CTxtPtrEx::MoveWhile((CTxtPtrEx *)&v270, v201, 0xE000u, 0xF8FFu, 1);
      v201 = v118;
LABEL_386:
      v107 = *(_DWORD *)v230;
      goto LABEL_387;
    }
    if ( v134 >= 0x80u )
    {
      v135 = 0;
      v213 = 0;
    }
    else
    {
      v200 |= 8u;
      v135 = 0;
      v213 = 1;
    }
    v136 = v240;
    if ( !v132 )
    {
      if ( (v129 & 0xFF800000000LL) != 0 && (v240 & 0xFF800000000LL) != 0 )
      {
        if ( (unsigned int)v134 - 2404 <= 1 )
        {
          v201 = 1;
          v132 = 1;
          v137 = CCharFlags::CharRepFontSig(v240 & 0xFF800000000LL, 1);
          v136 = v240;
          v138 = a5 | 0x8000000;
          a5 |= 0x8000000u;
          v135 = 0;
          v230[4] = v137;
LABEL_339:
          if ( IsBiDiCharRep || (unsigned int)CW32System::IsBiDiCharRep(v230[4]) )
          {
            v142 = v222;
            if ( !v222 )
            {
              v143 = v213;
              goto LABEL_343;
            }
          }
          else
          {
            v142 = v222;
          }
          v143 = v213;
          if ( v213 && !v130 && ((v136 & 0xC0) == 0xC0 || v133) )
          {
            v144 = v204;
            if ( v261 == v135 || v204 || !(_BYTE)v223 )
            {
              if ( v132 && !v142 && (!(unsigned int)CW32System::IsLatinCharRep(v223) || (v200 & 1) == 0) )
                goto LABEL_368;
              v146 = v138 | 0x8000000;
            }
            else
            {
              v146 = v138 & 0xDFFFFFFF;
            }
            a5 = v146;
LABEL_368:
            v145 = v200;
            goto LABEL_369;
          }
LABEL_343:
          if ( !v132 && (v230[4] != 9 || *(_WORD *)&v230[6] == 1) )
          {
            v144 = v204;
            v145 = v200 & 0xFFEFFFFF;
            v200 &= ~0x100000u;
            a5 = v138 & 0xDFFFFFFF;
LABEL_369:
            Exact = CTxtPtrEx::FindExact((CTxtPtrEx *)&v270, v201, &dword_1802B1B14, 0);
            LODWORD(v118) = v201;
            if ( Exact == -1 )
            {
              LODWORD(v118) = v201 - CTxtPtrEx::MoveWhile((CTxtPtrEx *)&v270, v201, 0, 0x7Fu, v143);
              v201 = v118;
            }
            if ( v132 )
            {
              if ( !v144 )
              {
                v107 = *(_DWORD *)v230;
                if ( (*(_DWORD *)v230 & 0x2000000) == 0 || !(_DWORD)v118 )
                {
                  v117 = a5;
                  goto LABEL_387;
                }
              }
            }
            v299 = v295;
            v300 = 256;
            memset_0(v295, 0, 0x100u);
            if ( v201 < 0x3FFFFFFF
              && (Buf = (unsigned __int16 *)CTempBuf::GetBuf((CTempBuf *)v295, 2 * v201)) != 0
              && (CTxtPtrEx::SetCp((CTxtPtrEx *)&v270, v208), CTxtPtr::GetText((CTxtPtr *)&v270, v201, Buf)) )
            {
              v150 = (const struct CFontOptions *)CTxtEdit::GetFontOptions(v15, v294);
              v152 = Buf;
              v153 = v230[4];
              if ( v205 )
                v153 = v283.m128i_u8[4];
              v117 = a5;
              if ( CheckFontCMap(v283.m128i_i16[3], v153, v151, v152, v150, 0) )
              {
                v117 = a5 & 0xD7FFFFFF;
                a5 &= 0xD7FFFFFF;
                v200 = v145 & 0xFFEFFFFF;
              }
            }
            else
            {
              v117 = a5;
            }
            CTempBuf::FreeBuf((CTempBuf *)v295);
            LODWORD(v118) = v201;
            goto LABEL_386;
          }
          if ( v230[4] == v283.m128i_i8[4] )
          {
            if ( (*(_BYTE *)(v15 + 278) & 2) != 0 && v133 )
              v147 = v138 & 0xDFFFFFFF;
            else
              v147 = v138 | 0x8000000;
            a5 = v147;
          }
          v144 = v204;
          goto LABEL_368;
        }
        v139 = CTxtPtrEx::FindExact((CTxtPtrEx *)&v270, v201, "d\te\t", 0x80000u);
        if ( v139 == -1 )
        {
          v141 = v208;
        }
        else
        {
          v140 = v139;
          v141 = v208;
          v201 = v140 - v208;
        }
        CTxtPtrEx::SetCp((CTxtPtrEx *)&v270, v141);
        v136 = v240;
        v135 = 0;
      }
      v132 = 0;
    }
    v138 = a5;
    goto LABEL_339;
  }
  CharRep = v230[4];
  if ( v230[4] == 9 )
  {
    CTxtPtrEx::SetCp((CTxtPtrEx *)&v270, v208);
    v213 = 0;
    Pch = CTxtPtr::GetPch((CTxtPtr *)&v270, &v213);
    CharFlagsHelper = CCharFlags::GetCharFlagsHelper(Pch, v213, 0, 0, 1, v244, v292);
    CharRep = CCharFlags::GetCharRep((CCharFlags *)&CharFlagsHelper, 0);
    if ( CharRep == 51 )
      CharRep = 0;
  }
  MathFont = CTxtEdit::GetMathFont((CTxtEdit *)v15, CharRep);
  if ( MathFont < 0 )
  {
    v117 = a5;
    goto LABEL_305;
  }
  v117 = a5;
  if ( (v109 & 0x10000) == 0 )
  {
    v117 = a5 & 0xDFFFFFFF;
    a5 &= ~0x20000000u;
  }
  v107 = *(_DWORD *)v230 & 0xFFEFFFFF;
  *(_WORD *)&v230[4] = 0x8000;
  *(_DWORD *)v230 &= ~0x100000u;
  *(_WORD *)&v230[6] = MathFont;
LABEL_289:
  LODWORD(v118) = v201;
LABEL_387:
  v154 = 1;
  v155 = v208;
  v273 = v234;
  v249 = 1;
  while ( 2 )
  {
    v156 = v117;
    if ( (v200 & 0x10000) == 0 && v205 && (v117 & 0x8000000) == 0 )
      v156 = v117 & 0xFDFFFFFF;
    if ( v209 && (*(_DWORD *)(v15 + 184) & 0x40000000) == 0 && (*(_BYTE *)(v15 + 278) & 2) == 0
      || (v107 & 0x10000000) != 0 && ((v156 & 3) != 0 || v206) )
    {
      if ( v155 < v229 )
        v229 = v155;
      if ( (int)v118 + v155 > v237 )
        v237 = v118 + v155;
    }
    if ( v202[0]
      && ((_WORD)v233 == (_WORD)v286
       || (LOWORD(v263) = 0, BYTE2(v263) = 0, CW32System::GetTmpData(v286, (struct _tmpDispAttrib *)&v263))
       && (_WORD)v263 == 4
       && ((v158 = BYTE2(v263), v157 == -1) && !BYTE2(v263)
        || (BYTE2(v276[0]) = 0, CW32System::GetTmpData(v157, (struct _tmpDispAttrib *)v276)) && BYTE2(v276[0]) == v158)) )
    {
      v213 = 0;
    }
    else
    {
      v199 = *(struct IDpiAccessor **)(v15 + 568);
      v202[1] = v202[0];
      v159 = CCharFormat::Apply((CCharFormat *)v230, (const struct CCharFormat *)&v283, v156, v200, v216, v278, v199);
      v107 = *(_DWORD *)v230;
      v213 = v159;
    }
    if ( CTxtEdit::FIdealLayout((CTxtEdit *)v15) )
    {
      v161 = 2600;
      if ( *(__int16 *)&v230[8] < 2600 )
        v161 = *(_WORD *)&v230[8];
      *(_WORD *)&v230[8] = v161;
    }
    if ( v243 != v160 && (v107 & 0x10000000) != 0 )
    {
      v162 = v107 | 2;
      *(_DWORD *)v230 = v162;
      if ( (v162 & 0x20000000) != 0 )
        *(_DWORD *)v230 = v162 & 0xFFFFFFFD;
    }
    if ( v214 != (_BYTE)v160 )
    {
      v299 = v295;
      v300 = 256;
      memset_0(v295, 0, 0x100u);
      if ( v201 < 0x3FFFFFFF )
      {
        v163 = (unsigned __int16 *)CTempBuf::GetBuf((CTempBuf *)v295, 2 * v201);
        if ( v163 )
        {
          CTxtPtrEx::SetCp((CTxtPtrEx *)&v270, v208);
          Text = CTxtPtr::GetText((CTxtPtr *)&v270, v201, v163);
          if ( Text > 0 )
          {
            v204 = 0;
            FontName = CFICache::GetFontName(*(__int16 *)&v230[6]);
            if ( FontName )
            {
              v166 = 9;
              v167 = 2;
              if ( (*(_DWORD *)(v15 + 180) & 0x20000000) == 0 )
                v166 = DWORD2(v231);
              if ( (v230[0] & 2) == 0 )
                v167 = (DWORD1(v233) >> 9) & 1;
              HIDWORD(v231) = (*(__int64 (__fastcall **)(struct IProvideFontInfo *, const unsigned __int16 *, _QWORD, _QWORD, int, int, unsigned __int16 *, int, _DWORD, unsigned int *))(*(_QWORD *)v278 + 32LL))(
                                v278,
                                FontName,
                                (unsigned __int16)v231,
                                HIBYTE(v233) & 0xF,
                                v167,
                                v166,
                                v163,
                                Text,
                                HIDWORD(v231),
                                &v204);
              v168 = v204;
              if ( v204 > Text )
                v168 = 0;
              if ( v168 )
              {
                v201 = v168;
                goto LABEL_434;
              }
              goto LABEL_435;
            }
            v168 = v204;
LABEL_434:
            if ( !v168 )
LABEL_435:
              HIDWORD(v231) = 0;
          }
        }
      }
      CTempBuf::FreeBuf((CTempBuf *)v295);
    }
    v64 = v213;
    if ( v213
      || (v169 = v258,
          v213 = (*(__int64 (__fastcall **)(struct IFormatCache *, unsigned __int8 *, __int16 *))(*(_QWORD *)v258 + 24LL))(
                   v258,
                   v230,
                   v215),
          (v64 = v213) != 0) )
    {
      v20 = v64;
      goto LABEL_466;
    }
    if ( v262 )
    {
      v172 = *(LS **)(v15 + 136);
      v262 = 0;
      LS::InvalidateLineCache(v172, v170, v171);
    }
    v173 = CFormatRunPtr::SetFormat((CFormatRunPtr *)&v248, v215[0], v201, v169, v289, v279);
    if ( v173 >= (int)v201 )
    {
      v174 = v249;
    }
    else
    {
      v224 = 0;
      v174 = 0;
      v249 = 0;
    }
    (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v258 + 8LL))(v258, (unsigned __int16)v215[0]);
    if ( v173 != 0x3FFFFFFF )
    {
      if ( v250 )
      {
        v175 = v226;
        v176 = v227;
        if ( v208 < v226 )
          v175 = v208;
        v226 = v175;
        v247 = v175;
        if ( v173 + v208 > v227 )
          v176 = v173 + v208;
        v227 = v176;
        v241 = v176;
      }
      if ( v173 <= 0 || (v203 -= v173, v155 = v173 + v208, ++v154, v208 += v173, v154 > 1) || !v174 )
      {
        v52 = v251;
        v200 = v252;
        v216 = v274;
        a5 = v251;
        goto LABEL_457;
      }
      v107 = *(_DWORD *)v230;
      LODWORD(v118) = v173;
      v201 = v173;
      v117 = a5;
      continue;
    }
    break;
  }
  if ( *(_WORD *)(v15 + 56) && (-(__int64)(v15 != 0) & (v15 + 48)) != 0 )
  {
    v177 = v15 + 60;
    if ( !v15 )
      v177 = 12;
    *(_DWORD *)v177 |= 0x40u;
  }
LABEL_466:
  free(Block[1]);
LABEL_550:
  CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)v277);
  return v20;
}

```

## disassembly

```asm
0x1800b6598  mov     rax, rsp
0x1800b659b  mov     [rax+18h], rbx
0x1800b659f  push    rbp
0x1800b65a0  push    rsi
0x1800b65a1  push    rdi
0x1800b65a2  push    r12
0x1800b65a4  push    r13
0x1800b65a6  push    r14
0x1800b65a8  push    r15
0x1800b65aa  lea     rbp, [rax-408h]
0x1800b65b1  sub     rsp, 4D0h
0x1800b65b8  movaps  xmmword ptr [rax-48h], xmm6
0x1800b65bc  movaps  xmmword ptr [rax-58h], xmm7
0x1800b65c0  movaps  xmmword ptr [rax-68h], xmm8
0x1800b65c5  movaps  xmmword ptr [rax-78h], xmm9
0x1800b65ca  movaps  xmmword ptr [rax-88h], xmm10
0x1800b65d2  mov     rax, cs:__security_cookie
0x1800b65d9  xor     rax, rsp
0x1800b65dc  mov     [rbp+400h+var_90], rax
0x1800b65e3  mov     rax, [rbp+400h+arg_38]
0x1800b65ea  mov     ebx, r8d
0x1800b65ed  mov     [rbp+400h+var_208], rax
0x1800b65f4  mov     r13, rcx
0x1800b65f7  lea     rax, [rcx+8]
0x1800b65fb  mov     [rbp+400h+var_398], r9
0x1800b65ff  mov     rcx, rax; this
0x1800b6602  mov     [rbp+400h+var_3AC], ebx
0x1800b6605  mov     rdi, rdx
0x1800b6608  mov     [rbp+400h+var_210], rax
0x1800b660f  call    ?Check_rpCF@CRchTxtPtr@@QEAAHXZ; CRchTxtPtr::Check_rpCF(void)
0x1800b6614  xor     ecx, ecx
0x1800b6616  test    eax, eax
0x1800b6618  jz      loc_1800B8990
0x1800b661e  mov     r12d, [rbp+400h+arg_28]
0x1800b6625  mov     rsi, [r13+18h]
0x1800b6629  bts     r12d, 10h
0x1800b662e  bt      ebx, 9
0x1800b6632  cmovnb  r12d, [rbp+400h+arg_28]
0x1800b663a  mov     [rsp+500h+var_4A0], r12d
0x1800b663f  test    rsi, rsi
0x1800b6642  jz      short loc_1800B664A
0x1800b6644  mov     r14, [rsi+28h]
0x1800b6648  jmp     short loc_1800B664D
0x1800b664a  mov     r14, rcx
0x1800b664d  mov     ebx, [r13+68h]
0x1800b6651  xor     edx, edx; Val
0x1800b6653  mov     [rbp+400h+var_458], ecx
0x1800b6656  lea     rcx, [rbp+400h+var_420]; void *
0x1800b665a  lea     r8d, [rdx+44h]; Size
0x1800b665e  call    memset_0
0x1800b6663  movups  xmm0, xmmword ptr [rdi+10h]
0x1800b6667  mov     eax, [rdi+40h]
0x1800b666a  xor     r11d, r11d
0x1800b666d  movups  xmm2, xmmword ptr [rdi]
0x1800b6670  mov     edx, [rbp+400h+arg_20]
0x1800b6676  or      ecx, 0FFFFFFFFh
0x1800b6679  movups  xmm1, xmmword ptr [rdi+20h]
0x1800b667d  mov     [rbp+400h+var_220], eax
0x1800b6683  lea     r15d, [r11+1]
0x1800b6687  mov     eax, 7FFFFFFFh
0x1800b668c  movaps  xmmword ptr [rbp+400h+var_250], xmm0
0x1800b6693  movups  xmm0, xmmword ptr [rdi+30h]
0x1800b6697  mov     [rbp+400h+var_430], eax
0x1800b669a  mov     [rbp+400h+var_390], eax
0x1800b669d  mov     [rbp+400h+var_424], eax
0x1800b66a0  movaps  [rbp+400h+var_230], xmm0
0x1800b66a7  movaps  [rbp+400h+var_260], xmm2
0x1800b66ae  movaps  [rbp+400h+var_240], xmm1
0x1800b66b5  mov     [rbp+400h+var_3C8], ecx
0x1800b66b8  mov     al, [r14+114h]
0x1800b66bf  shr     al, 6
0x1800b66c2  and     al, r15b
0x1800b66c5  movd    r10d, xmm2
0x1800b66ca  bt      r12d, 1Dh
0x1800b66cf  mov     [rbp+400h+var_444], r11d
0x1800b66d3  mov     [rbp+400h+var_448], r11d
0x1800b66d7  mov     [rbp+400h+var_42C], ecx
0x1800b66da  mov     [rbp+400h+var_3B0], ecx
0x1800b66dd  mov     [rbp+400h+var_374], r11d
0x1800b66e4  mov     byte ptr [rbp+400h+var_3A4], al
0x1800b66e7  mov     [rbp+400h+var_3D0], r10d
0x1800b66eb  jb      short loc_1800B6726
0x1800b66ed  bt      edx, 1Dh
0x1800b66f1  jnb     short loc_1800B66FA
0x1800b66f3  bt      r12d, 10h
0x1800b66f8  jb      short loc_1800B6726
0x1800b66fa  mov     eax, r11d
0x1800b66fd  mov     r8d, r11d
0x1800b6700  mov     [rsp+500h+var_488], r8d
0x1800b6705  mov     [rbp+400h+var_3A0], r11d
0x1800b6709  bt      r12d, 1Ch
0x1800b670e  jb      short loc_1800B673E
0x1800b6710  bt      edx, 1Ch
0x1800b6714  jnb     short loc_1800B671D
0x1800b6716  bt      r12d, 10h
0x1800b671b  jb      short loc_1800B673E
0x1800b671d  mov     ecx, r11d
0x1800b6720  mov     [rbp+400h+var_47C], r11d
0x1800b6724  jmp     short loc_1800B6760
0x1800b6726  bt      r10d, 1Dh
0x1800b672b  mov     eax, r15d
0x1800b672e  mov     r8d, r15d
0x1800b6731  jnb     short loc_1800B6700
0x1800b6733  mov     [rbp+400h+var_3A0], r15d
0x1800b6737  mov     [rsp+500h+var_488], r15d
0x1800b673c  jmp     short loc_1800B6709
0x1800b673e  bt      r10d, 1Ch
0x1800b6743  mov     [rsp+500h+var_488], r8d
0x1800b6748  mov     [rbp+400h+var_47C], r15d
0x1800b674c  jnb     short loc_1800B6758
0x1800b674e  mov     r12d, r15d
0x1800b6751  mov     [rsp+500h+var_484], r15d
0x1800b6756  jmp     short loc_1800B6770
0x1800b6758  mov     ecx, r15d
0x1800b675b  mov     [rsp+500h+var_488], r8d
0x1800b6760  mov     [rsp+500h+var_484], r11d
0x1800b6765  mov     r12d, r11d
0x1800b6768  mov     [rbp+400h+var_3C4], r15d
0x1800b676c  test    ecx, ecx
0x1800b676e  jnz     short loc_1800B6774
0x1800b6770  mov     [rbp+400h+var_3C4], r11d
0x1800b6774  mov     ecx, 2
0x1800b6779  test    eax, eax
0x1800b677b  jz      short loc_1800B6792
0x1800b677d  test    dword ptr [r14+0B0h], 10000h
0x1800b6788  jnz     short loc_1800B6792
0x1800b678a  mov     [rbp+400h+var_3A8], r15d
0x1800b678e  test    cl, dl
0x1800b6790  jz      short loc_1800B6796
0x1800b6792  mov     [rbp+400h+var_3A8], r11d
0x1800b6796  mov     rax, cs:qword_1802E45A8
0x1800b679d  lea     r9, [rsi-8]
0x1800b67a1  mov     r8d, [rsp+500h+var_4A0]
0x1800b67a6  mov     [rbp+400h+var_350], rax
0x1800b67ad  mov     eax, r8d
0x1800b67b0  and     al, cl
0x1800b67b2  mov     [rbp+400h+var_464], r11w
0x1800b67b7  neg     al
0x1800b67b9  mov     [rbp+400h+var_3C0], r11d
0x1800b67bd  lea     rcx, [rbp+400h+var_374]
0x1800b67c4  sbb     rax, rax
0x1800b67c7  and     rax, rcx
0x1800b67ca  mov     [rbp+400h+var_290], rax
0x1800b67d1  test    rsi, rsi
0x1800b67d4  jnz     short loc_1800B67D9
0x1800b67d6  mov     r9, r11
0x1800b67d9  mov     rcx, r14; this
0x1800b67dc  mov     [rbp+400h+var_438], r9
0x1800b67e0  call    ?GetFontInfoProvider@CTxtEdit@@QEBAPEAUIProvideFontInfo@@XZ; CTxtEdit::GetFontInfoProvider(void)
0x1800b67e5  mov     edi, [rbp+400h+arg_30]
0x1800b67eb  mov     [rbp+400h+var_298], rax
0x1800b67f2  cmp     [rbp+400h+arg_48], r11b
0x1800b67f9  jnz     short loc_1800B6816
0x1800b67fb  test    rax, rax
0x1800b67fe  jz      short loc_1800B6810
0x1800b6800  test    edx, 20400003h
0x1800b6806  jnz     short loc_1800B6816
0x1800b6808  test    edi, 400200h
0x1800b680e  jnz     short loc_1800B6816
0x1800b6810  mov     [rbp+400h+var_468], r11b
0x1800b6814  jmp     short loc_1800B681A
0x1800b6816  mov     [rbp+400h+var_468], r15b
0x1800b681a  test    edx, edx
0x1800b681c  jnz     short loc_1800B682D
0x1800b681e  test    edi, edi
0x1800b6820  jnz     short loc_1800B682D
0x1800b6822  mov     [rsp+500h+var_498], r15b
0x1800b6827  cmp     r8d, 10h
0x1800b682b  jz      short loc_1800B6832
0x1800b682d  mov     [rsp+500h+var_498], r11b
0x1800b6832  lea     rsi, [r13+8]
0x1800b6836  test    r12d, r12d
0x1800b6839  jz      short loc_1800B6879
0x1800b683b  mov     rcx, rsi; this
0x1800b683e  call    ?IsRich@CRchTxtPtr@@QEBAHXZ; CRchTxtPtr::IsRich(void)
0x1800b6843  test    eax, eax
0x1800b6845  jz      loc_1800B8990
0x1800b684b  xor     r8d, r8d
0x1800b684e  mov     [rbp+400h+var_320], 1000000h
0x1800b6859  lea     rdx, [rbp+400h+var_320]
0x1800b6860  mov     [rbp+400h+var_318], r11
0x1800b6867  mov     rcx, r14
0x1800b686a  call    ?OrCharFlags@CTxtEdit@@QEAAXVCCharFlags@@PEAVIUndoBuilder@@PEAVCTxtStory@@@Z; CTxtEdit::OrCharFlags(CCharFlags,IUndoBuilder *,CTxtStory *)
0x1800b686f  mov     edx, [rbp+400h+arg_20]
0x1800b6875  mov     r10d, [rbp+400h+var_3D0]
0x1800b6879  and     r10d, edx
0x1800b687c  mov     eax, 0FFFFFFFFh
0x1800b6881  and     r10d, 100h
0x1800b6888  mov     [rbp+400h+var_45C], ax
0x1800b688c  mov     [rbp+400h+var_3D0], r10d
0x1800b6890  jz      short loc_1800B68B7
0x1800b6892  mov     rdx, rsi; struct CRchTxtPtr *
0x1800b6895  lea     rcx, [rbp+400h+var_310]; this
0x1800b689c  call    ??0CCFRunPtr@@QEAA@AEBVCRchTxtPtr@@@Z; CCFRunPtr::CCFRunPtr(CRchTxtPtr const &)
0x1800b68a1  xor     r8d, r8d; int
0x1800b68a4  lea     rdx, [rbp+400h+var_310]; struct CCFRunPtr *
0x1800b68ab  mov     rcx, r13; this
0x1800b68ae  call    ?CheckILSObject@CTxtRange@@QEAAHAEAVCCFRunPtr@@H@Z; CTxtRange::CheckILSObject(CCFRunPtr &,int)
0x1800b68b3  mov     ebx, [r13+68h]
0x1800b68b7  xor     r10d, r10d
0x1800b68ba  mov     esi, edi
0x1800b68bc  and     esi, 0FFFFFE0h
0x1800b68c2  test    byte ptr [r14+166h], 20h
0x1800b68ca  cmovnz  esi, edi
0x1800b68cd  test    byte ptr [r14+0B8h], 40h
0x1800b68d5  jz      short loc_1800B68DE
0x1800b68d7  or      [rsp+500h+var_4A0], 8
0x1800b68dc  jmp     short loc_1800B68E6
0x1800b68de  mov     eax, [rsp+500h+var_4A0]
0x1800b68e2  mov     [rsp+500h+var_4A0], eax
0x1800b68e6  cmp     [rbp+400h+var_3C4], r10d
0x1800b68ea  jz      loc_1800B6A3A
0x1800b68f0  cmp     [r13+68h], r10d
0x1800b68f4  jle     short loc_1800B68FF
0x1800b68f6  lea     rcx, [r13+40h]; this
0x1800b68fa  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x1800b68ff  lea     rcx, [r13+8]; this
0x1800b6903  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x1800b6908  lea     rcx, [r13+40h]; this
0x1800b690c  mov     rdi, rax
0x1800b690f  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x1800b6914  xor     edx, edx
0x1800b6916  cmp     [r13+68h], edx
0x1800b691a  jz      short loc_1800B6995
0x1800b691c  mov     rcx, rdi; this
0x1800b691f  call    ?IsMathZonePlaceHolder@CCharFormat@@QEBA_NXZ; CCharFormat::IsMathZonePlaceHolder(void)
0x1800b6924  test    al, al
0x1800b6926  jz      short loc_1800B6995
0x1800b6928  mov     rcx, r13; this
0x1800b692b  call    ?WriteAccessDenied@CTxtRange@@QEAAHI@Z; CTxtRange::WriteAccessDenied(uint)
0x1800b6930  test    eax, eax
0x1800b6932  jnz     short loc_1800B6995
0x1800b6934  mov     edx, [r13+28h]
0x1800b6938  xor     r8d, r8d; int
0x1800b693b  sub     edx, r15d; int
0x1800b693e  mov     rcx, r13; this
0x1800b6941  call    ?SetCp@CTxtRange@@QEAAJJH@Z; CTxtRange::SetCp(long,int)
0x1800b6946  mov     rax, [r13+0]
0x1800b694a  xor     r8d, r8d
0x1800b694d  mov     rcx, r13
0x1800b6950  mov     rax, [rax+0C8h]
0x1800b6957  lea     edx, [r8+14h]
0x1800b695b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6960  mov     rax, [r13+0]
0x1800b6964  xor     ecx, ecx
0x1800b6966  mov     r9, [rbp+400h+var_398]
0x1800b696a  xor     r8d, r8d
0x1800b696d  mov     dword ptr [rsp+500h+var_4C8], ecx
0x1800b6971  xor     edx, edx
0x1800b6973  mov     dword ptr [rsp+500h+var_4D0], ecx
0x1800b6977  mov     rax, [rax+378h]
0x1800b697e  mov     [rsp+500h+var_4D8], rcx
0x1800b6983  mov     rcx, r13
0x1800b6986  mov     dword ptr [rsp+500h+var_4E0], r15d
0x1800b698b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6990  jmp     loc_1800B8992
0x1800b6995  cmp     byte ptr [rdi+5], 80h
0x1800b6999  jz      short loc_1800B69A9
0x1800b699b  movzx   eax, word ptr [rdi+6]
0x1800b699f  mov     [rbp+400h+var_45C], ax
0x1800b69a3  mov     eax, [rdi+18h]
0x1800b69a6  mov     [rbp+400h+var_3C0], eax
0x1800b69a9  test    dword ptr [rdi], 10000000h
0x1800b69af  jz      short loc_1800B69C6
0x1800b69b1  lea     r8, [rsp+500h+var_498+1]; unsigned __int8 *
0x1800b69b6  mov     rcx, r13; this
0x1800b69b9  lea     rdx, [rbp+400h+var_3C0]; unsigned int *
0x1800b69bd  call    ?GetPrevNonMathFont@CTxtRange@@QEAAFAEAKAEAE@Z; CTxtRange::GetPrevNonMathFont(ulong &,uchar &)
0x1800b69c2  mov     [rbp+400h+var_45C], ax
0x1800b69c6  mov     ecx, [r13+68h]
0x1800b69ca  xor     r10d, r10d
0x1800b69cd  test    ecx, ecx
0x1800b69cf  jz      short loc_1800B6A3A
0x1800b69d1  test    dword ptr [r13+74h], 60000h
0x1800b69d9  jnz     short loc_1800B6A3A
0x1800b69db  lea     rdi, [r13+18h]
0x1800b69df  cmp     ecx, r15d
0x1800b69e2  jnz     short loc_1800B69F7
0x1800b69e4  mov     rcx, rdi; this
0x1800b69e7  call    ?IsAfterEOP@CTxtPtr@@QEBAHXZ; CTxtPtr::IsAfterEOP(void)
0x1800b69ec  xor     r10d, r10d
0x1800b69ef  test    eax, eax
0x1800b69f1  jnz     short loc_1800B6A3A
0x1800b69f3  mov     ecx, [r13+68h]
0x1800b69f7  cmp     ecx, 0FFFFFFFFh
0x1800b69fa  jnz     short loc_1800B6A0B
0x1800b69fc  mov     rcx, rdi; this
0x1800b69ff  call    ?IsAtEOP@CTxtPtr@@QEBAHXZ; CTxtPtr::IsAtEOP(void)
0x1800b6a04  xor     r10d, r10d
0x1800b6a07  test    eax, eax
0x1800b6a09  jnz     short loc_1800B6A3A
0x1800b6a0b  mov     r9d, [rsp+500h+var_4A0]
0x1800b6a10  mov     r8d, [rbp+400h+arg_20]
0x1800b6a17  and     r9d, 0C7FFFFFFh
0x1800b6a1e  mov     [rsp+500h+var_4A0], r9d
0x1800b6a23  bt      r9d, 10h
0x1800b6a28  jnb     short loc_1800B6A46
0x1800b6a2a  and     r8d, 0C7FFFFFFh
0x1800b6a31  mov     [rbp+400h+arg_20], r8d
0x1800b6a38  jmp     short loc_1800B6A46
  ... truncated ...
```
