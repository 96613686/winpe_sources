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
  __int64 v34; // r9
  __int64 v35; // r11
  int v36; // r10d
  signed int v37; // esi
  const struct CCharFormat *CF; // rdi
  unsigned int v39; // edx
  __int64 result; // rax
  int v41; // ecx
  int v42; // eax
  int v43; // eax
  unsigned int v44; // r8d
  unsigned int v45; // r9d
  int v46; // edx
  int v47; // edx
  int v48; // edx
  bool v49; // zf
  int v50; // eax
  int v51; // ebx
  __int128 *v52; // rdi
  unsigned int v53; // ebx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 FontOptions; // rax
  __int16 FontInfoFlags; // ax
  __int64 v58; // rax
  CTxtStory *v59; // rax
  int v60; // edi
  __int64 v61; // xmm1_8
  int v62; // r9d
  unsigned int v63; // eax
  __int16 v64; // si
  struct CDisplay *v65; // rdx
  unsigned int v66; // esi
  __int64 v67; // rcx
  int v68; // edx
  int v69; // eax
  int v70; // edi
  const struct CParaFormat *PF; // rax
  int v72; // ecx
  int v73; // edx
  int v74; // ecx
  __int128 v75; // xmm0
  unsigned int v76; // ebx
  int v77; // edi
  int v78; // eax
  CAntiEventDispenser *v79; // rcx
  struct IAntiEvent *ReplaceFormattingAE; // rbx
  unsigned int v81; // r10d
  int v82; // r9d
  int v83; // r12d
  char v84; // r11
  __int128 v85; // xmm0
  __int128 v86; // xmm0
  __int16 v87; // ax
  int v88; // r8d
  unsigned int v89; // r10d
  int v90; // r11d
  __int64 v91; // rdx
  __int64 *v92; // rax
  __int64 v93; // xmm0_8
  CRchTxtPtr *v94; // r12
  int IsRich; // eax
  int v96; // r10d
  int TextLength; // eax
  unsigned __int16 v98; // dx
  int v99; // edi
  unsigned __int8 v100; // dl
  int v101; // r8d
  __int16 Format; // ax
  __int16 v103; // ax
  const struct CCharFormat *v104; // rax
  __m128i v105; // xmm9
  unsigned __int8 v106; // r12
  int v107; // ecx
  unsigned __int8 v108; // al
  unsigned int v109; // esi
  unsigned int v110; // edx
  unsigned int v111; // edi
  int CchLeft; // r12d
  int v113; // edi
  unsigned __int16 Char; // ax
  int v115; // ebx
  int v116; // esi
  int v117; // esi
  int v118; // ecx
  unsigned int v119; // ebx
  __int64 v120; // rdx
  unsigned __int8 CharRep; // dl
  const unsigned __int16 *Pch; // rax
  __int16 MathFont; // ax
  int v124; // eax
  __m128i v125; // xmm0
  bool v126; // cc
  unsigned __int8 v127; // al
  __int64 v128; // r10
  char v129; // r11
  __int64 v130; // rbx
  unsigned __int64 v131; // rdi
  int v132; // r12d
  int FontInfoFromFaceName; // eax
  int v134; // ebx
  int v135; // esi
  unsigned __int16 v136; // ax
  int v137; // r11d
  char v138; // r10
  unsigned __int8 v139; // al
  unsigned int v140; // r9d
  int v141; // eax
  int v142; // edi
  int v143; // eax
  int v144; // ecx
  int v145; // edi
  unsigned int v146; // esi
  unsigned int v147; // r12d
  unsigned int v148; // r9d
  unsigned int v149; // r9d
  int Exact; // eax
  unsigned __int16 *Buf; // rbx
  const struct CFontOptions *v152; // rax
  int v153; // r10d
  const unsigned __int16 *v154; // r9
  unsigned __int8 v155; // dl
  int v156; // r12d
  int v157; // r8d
  unsigned int v158; // edi
  __int16 v159; // r11
  char v160; // bl
  int v161; // eax
  int v162; // r10d
  __int16 v163; // dx
  int v164; // esi
  unsigned __int16 *v165; // rbx
  int Text; // edi
  const unsigned __int16 *FontName; // r10
  int v168; // edx
  int v169; // eax
  unsigned int v170; // eax
  struct IFormatCache *v171; // rbx
  const struct CDisplay *v172; // rdx
  bool v173; // r8
  LS *v174; // rcx
  int v175; // ebx
  int v176; // edi
  int v177; // eax
  int v178; // ecx
  __int64 v179; // rax
  CRunPtrBase *v180; // rcx
  int v181; // eax
  __int64 v182; // r11
  CTxtStory *ActiveStory; // rax
  int v184; // eax
  unsigned int v185; // ebx
  unsigned int v186; // edi
  int v187; // eax
  int v188; // eax
  int v189; // eax
  const struct CCharFormat *CharFormat; // rax
  __m128i v191; // xmm2
  int v192; // eax
  int v193; // ebx
  int v194; // eax
  __int16 v195; // bx
  struct IFormatCache *v196; // rbx
  int *v197; // r9
  int v198; // edx
  int v199; // r8d
  CTxtStory *v200; // rbx
  struct IDpiAccessor *v201; // [rsp+38h] [rbp-D0h]
  unsigned int v202; // [rsp+68h] [rbp-A0h]
  unsigned int v203; // [rsp+6Ch] [rbp-9Ch]
  unsigned __int8 v204[4]; // [rsp+70h] [rbp-98h] BYREF
  int v205; // [rsp+74h] [rbp-94h]
  unsigned int v206; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v207; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v208; // [rsp+80h] [rbp-88h]
  int v209; // [rsp+84h] [rbp-84h]
  int v210; // [rsp+88h] [rbp-80h]
  int v211; // [rsp+8Ch] [rbp-7Ch]
  int v212; // [rsp+90h] [rbp-78h]
  int v213; // [rsp+94h] [rbp-74h]
  int v214; // [rsp+98h] [rbp-70h]
  int v215; // [rsp+9Ch] [rbp-6Ch] BYREF
  char v216; // [rsp+A0h] [rbp-68h]
  __int16 v217[2]; // [rsp+A4h] [rbp-64h] BYREF
  unsigned int v218; // [rsp+A8h] [rbp-60h]
  __int16 PrevNonMathFont; // [rsp+ACh] [rbp-5Ch]
  int v220; // [rsp+B0h] [rbp-58h] BYREF
  int v221; // [rsp+B4h] [rbp-54h] BYREF
  int v222; // [rsp+B8h] [rbp-50h]
  int v223; // [rsp+BCh] [rbp-4Ch]
  int v224; // [rsp+C0h] [rbp-48h] BYREF
  int v225; // [rsp+C4h] [rbp-44h] BYREF
  int v226; // [rsp+C8h] [rbp-40h]
  CTxtStory *v227; // [rsp+D0h] [rbp-38h]
  int v228; // [rsp+D8h] [rbp-30h]
  int v229; // [rsp+DCh] [rbp-2Ch]
  int v230; // [rsp+E0h] [rbp-28h]
  int v231; // [rsp+E4h] [rbp-24h] BYREF
  unsigned __int8 v232[16]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v233; // [rsp+F8h] [rbp-10h]
  __m128i v234; // [rsp+108h] [rbp+0h] BYREF
  __int128 v235; // [rsp+118h] [rbp+10h]
  int v236; // [rsp+128h] [rbp+20h]
  int v237; // [rsp+138h] [rbp+30h]
  BOOL v238; // [rsp+13Ch] [rbp+34h]
  int v239; // [rsp+140h] [rbp+38h] BYREF
  int v240; // [rsp+144h] [rbp+3Ch]
  unsigned int v241; // [rsp+148h] [rbp+40h] BYREF
  __int64 v242; // [rsp+150h] [rbp+48h]
  int v243; // [rsp+158h] [rbp+50h] BYREF
  int v244; // [rsp+15Ch] [rbp+54h]
  int v245; // [rsp+160h] [rbp+58h]
  __int16 v246; // [rsp+164h] [rbp+5Ch]
  int v247; // [rsp+168h] [rbp+60h]
  struct IUndoBuilder *v248; // [rsp+170h] [rbp+68h]
  int v249; // [rsp+178h] [rbp+70h] BYREF
  __int128 v250; // [rsp+180h] [rbp+78h] BYREF
  int v251; // [rsp+190h] [rbp+88h]
  int v252; // [rsp+194h] [rbp+8Ch] BYREF
  unsigned int v253; // [rsp+198h] [rbp+90h]
  unsigned int v254; // [rsp+19Ch] [rbp+94h]
  int v255; // [rsp+1A0h] [rbp+98h]
  int v256; // [rsp+1A4h] [rbp+9Ch]
  int v257; // [rsp+1A8h] [rbp+A0h] BYREF
  int v258; // [rsp+1ACh] [rbp+A4h]
  int v259; // [rsp+1B0h] [rbp+A8h]
  struct IFormatCache *v260; // [rsp+1B8h] [rbp+B0h]
  int v261; // [rsp+1C0h] [rbp+B8h]
  int IsBiDiCharRep; // [rsp+1C4h] [rbp+BCh]
  int v263; // [rsp+1C8h] [rbp+C0h]
  int v264; // [rsp+1CCh] [rbp+C4h]
  __int64 v265; // [rsp+1D0h] [rbp+C8h] BYREF
  __int64 v266; // [rsp+1D8h] [rbp+D0h]
  __int64 v267; // [rsp+1E0h] [rbp+D8h]
  __int64 v268; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v269; // [rsp+1F0h] [rbp+E8h]
  __int128 v270; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v271; // [rsp+208h] [rbp+100h]
  __int128 v272; // [rsp+210h] [rbp+108h] BYREF
  __int64 v273; // [rsp+220h] [rbp+118h]
  __int128 v274; // [rsp+228h] [rbp+120h]
  int v275; // [rsp+238h] [rbp+130h]
  unsigned int v276; // [rsp+23Ch] [rbp+134h]
  CNotifyMgr *v277; // [rsp+240h] [rbp+138h]
  _OWORD v278[2]; // [rsp+248h] [rbp+140h] BYREF
  char v279[8]; // [rsp+268h] [rbp+160h] BYREF
  struct IProvideFontInfo *v280; // [rsp+270h] [rbp+168h]
  int *v281; // [rsp+278h] [rbp+170h]
  __int64 v282; // [rsp+280h] [rbp+178h] BYREF
  __int128 v283; // [rsp+288h] [rbp+180h]
  CTxtStory *v284; // [rsp+298h] [rbp+190h]
  __m128i v285; // [rsp+2A8h] [rbp+1A0h] BYREF
  unsigned int v286[4]; // [rsp+2B8h] [rbp+1B0h]
  __int128 v287; // [rsp+2C8h] [rbp+1C0h]
  __int128 v288; // [rsp+2D8h] [rbp+1D0h]
  int v289; // [rsp+2E8h] [rbp+1E0h]
  struct CRchTxtPtr *v290; // [rsp+2F8h] [rbp+1F0h]
  struct CBiDiLevel *v291; // [rsp+300h] [rbp+1F8h]
  _QWORD v292[2]; // [rsp+308h] [rbp+200h] BYREF
  __int64 CharFlagsHelper; // [rsp+318h] [rbp+210h] BYREF
  unsigned __int64 v294[3]; // [rsp+320h] [rbp+218h] BYREF
  void *Block[2]; // [rsp+338h] [rbp+230h]
  char v296[32]; // [rsp+348h] [rbp+240h] BYREF
  char v297[8]; // [rsp+368h] [rbp+260h] BYREF
  char v298[8]; // [rsp+370h] [rbp+268h] BYREF
  char v299[56]; // [rsp+378h] [rbp+270h] BYREF
  char v300[184]; // [rsp+3B0h] [rbp+2A8h] BYREF
  char *v301; // [rsp+468h] [rbp+360h]
  int v302; // [rsp+470h] [rbp+368h]

  v10 = a3;
  v291 = a8;
  v248 = a4;
  v244 = a3;
  v290 = (CTxtRange *)((char *)this + 8);
  if ( !(unsigned int)CRchTxtPtr::Check_rpCF((CTxtRange *)((char *)this + 8)) )
    return 0;
  v13 = *((_QWORD *)this + 3);
  v14 = a6 | 0x10000;
  if ( (v10 & 0x200) == 0 )
    v14 = a6;
  v202 = v14;
  if ( v13 )
    v15 = *(_QWORD *)(v13 + 40);
  else
    v15 = 0;
  v16 = *((_DWORD *)this + 26);
  v220 = 0;
  memset_0(v232, 0, 0x44u);
  v17 = *((_OWORD *)a2 + 1);
  v18 = *(__m128i *)a2;
  v19 = *((_OWORD *)a2 + 2);
  v289 = *((_DWORD *)a2 + 16);
  v20 = 1;
  *(_OWORD *)v286 = v17;
  v21 = *((_OWORD *)a2 + 3);
  v228 = 0x7FFFFFFF;
  v249 = 0x7FFFFFFF;
  v231 = 0x7FFFFFFF;
  v288 = v21;
  v285 = v18;
  v287 = v19;
  v239 = -1;
  v22 = (*(_BYTE *)(v15 + 276) & 0x40) != 0;
  v23 = _mm_cvtsi128_si32(v18);
  v225 = 0;
  v224 = 0;
  v229 = -1;
  v243 = -1;
  v252 = 0;
  LOBYTE(v246) = v22;
  v237 = v23;
  if ( (v14 & 0x20000000) != 0 || (a5 & 0x20000000) != 0 && (v14 & 0x10000) != 0 )
  {
    v24 = 1;
    v25 = 1;
    if ( (v23 & 0x20000000) != 0 )
    {
      v247 = 1;
      v208 = 1;
      goto LABEL_12;
    }
  }
  else
  {
    v24 = 0;
    v25 = 0;
  }
  v208 = v25;
  v247 = 0;
LABEL_12:
  if ( (v14 & 0x10000000) != 0 || (a5 & 0x10000000) != 0 && (v14 & 0x10000) != 0 )
  {
    v208 = v25;
    v211 = 1;
    if ( (v23 & 0x10000000) != 0 )
    {
      v27 = 1;
      v209 = 1;
LABEL_22:
      v240 = 0;
      goto LABEL_23;
    }
    v26 = 1;
    v208 = v25;
  }
  else
  {
    v26 = 0;
    v211 = 0;
  }
  v209 = 0;
  v27 = 0;
  v240 = 1;
  if ( !v26 )
    goto LABEL_22;
LABEL_23:
  if ( !v24 || (*(_DWORD *)(v15 + 176) & 0x10000) != 0 || (v245 = 1, (a5 & 2) != 0) )
    v245 = 0;
  v28 = (CTxtStory *)(v13 - 8);
  v260 = qword_1802E45A8;
  v217[0] = 0;
  v241 = 0;
  v281 = (int *)((unsigned __int64)&v252 & -(__int64)((v202 & 2) != 0));
  if ( !v13 )
    v28 = 0;
  v227 = v28;
  FontInfoProvider = CTxtEdit::GetFontInfoProvider((CTxtEdit *)v15);
  v280 = FontInfoProvider;
  if ( a10 != v33 || FontInfoProvider && ((v30 & 0x20400003) != 0 || (a7 & 0x400200) != 0) )
    v216 = 1;
  else
    v216 = v33;
  if ( v30 || a7 || (v204[0] = 1, v31 != 16) )
    v204[0] = v33;
  if ( !v27 )
    goto LABEL_42;
  if ( !(unsigned int)CRchTxtPtr::IsRich((CTxtRange *)((char *)this + 8)) )
    return 0;
  v268 = 0x1000000;
  v269 = v35;
  CTxtEdit::OrCharFlags(v15, &v268, 0, v34);
  LOWORD(v30) = a5;
  v32 = v237;
LABEL_42:
  PrevNonMathFont = -1;
  v237 = (unsigned __int16)v30 & v32 & 0x100;
  if ( ((unsigned __int16)v30 & v32 & 0x100) != 0 )
  {
    CCFRunPtr::CCFRunPtr((CCFRunPtr *)&v270, (CTxtRange *)((char *)this + 8));
    CTxtRange::CheckILSObject(this, (struct CCFRunPtr *)&v270, 0);
    v16 = *((_DWORD *)this + 26);
  }
  v36 = 0;
  v37 = a7 & 0xFFFFFE0;
  if ( (*(_BYTE *)(v15 + 358) & 0x20) != 0 )
    v37 = a7;
  if ( (*(_BYTE *)(v15 + 184) & 0x40) != 0 )
    v202 |= 8u;
  if ( !v240 )
    goto LABEL_68;
  if ( *((int *)this + 26) > 0 )
    CRunPtrBase::AdjustBackward((CTxtRange *)((char *)this + 64));
  CF = CRchTxtPtr::GetCF((CTxtRange *)((char *)this + 8));
  CRunPtrBase::AdjustForward((CTxtRange *)((char *)this + 64));
  if ( *((_DWORD *)this + 26)
    && CCharFormat::IsMathZonePlaceHolder(CF)
    && !(unsigned int)CTxtRange::WriteAccessDenied(this, v39) )
  {
    CTxtRange::SetCp(this, *((_DWORD *)this + 10) - 1, 0);
    (*(void (__fastcall **)(CTxtRange *, __int64))(*(_QWORD *)this + 200LL))(this, 20);
    return (*(__int64 (__fastcall **)(CTxtRange *, _QWORD, _QWORD, struct IUndoBuilder *, int, _QWORD, _DWORD, _DWORD))(*(_QWORD *)this + 888LL))(
             this,
             0,
             0,
             v248,
             1,
             0,
             0,
             0);
  }
  if ( *((_BYTE *)CF + 5) != 0x80 )
  {
    PrevNonMathFont = *((_WORD *)CF + 3);
    v241 = *((_DWORD *)CF + 6);
  }
  if ( (*(_DWORD *)CF & 0x10000000) != 0 )
    PrevNonMathFont = CTxtRange::GetPrevNonMathFont(this, &v241, &v204[1]);
  v41 = *((_DWORD *)this + 26);
  v36 = 0;
  if ( !v41 || (*((_DWORD *)this + 29) & 0x60000) != 0 )
    goto LABEL_68;
  if ( v41 == 1 )
  {
    v42 = CTxtPtr::IsAfterEOP((CTxtRange *)((char *)this + 24));
    v36 = 0;
    if ( v42 )
    {
LABEL_68:
      v45 = v202;
      v44 = a5;
      goto LABEL_69;
    }
    v41 = *((_DWORD *)this + 26);
  }
  if ( v41 == -1 )
  {
    v43 = CTxtPtr::IsAtEOP((CTxtRange *)((char *)this + 24));
    v36 = 0;
    if ( v43 )
      goto LABEL_68;
  }
  v44 = a5;
  v202 &= 0xC7FFFFFF;
  v45 = v202;
  if ( (v202 & 0x10000) != 0 )
  {
    v44 = a5 & 0xC7FFFFFF;
    a5 &= 0xC7FFFFFF;
  }
LABEL_69:
  v46 = *(_DWORD *)(v15 + 176);
  v256 = 0;
  v259 = 0;
  v204[1] = 0;
  if ( (v46 & 0x10) != 0 || CTxtEdit::FDisableMath((CTxtEdit *)v15) )
  {
    v202 = v45 & 0xEFFFFFFF;
    if ( (v45 & 0x10000) != 0 )
    {
      v44 &= ~0x10000000u;
      a5 = v44;
    }
  }
  if ( (v46 & 0x10000) == 0 && (v44 & 0x8000000C) != 0 && (v44 & 0x7FFFFFF3) == 0 )
  {
    if ( *((_DWORD *)this + 26) == v36 )
    {
      if ( (*(_DWORD *)CRchTxtPtr::GetCFBackward((CTxtRange *)((char *)this + 8)) & 0x10000000) == 0 )
        goto LABEL_87;
      v49 = (*(_DWORD *)CRchTxtPtr::GetCF((CTxtRange *)((char *)this + 8)) & 0x10000000) == 0;
    }
    else
    {
      CCFRunPtr::CCFRunPtr((CCFRunPtr *)v278, (CTxtRange *)((char *)this + 8));
      v47 = *((_DWORD *)this + 26);
      if ( v47 > 0 )
        CRunPtrBase::Move((CRunPtrBase *)v278, -v47);
      if ( (*(_DWORD *)CCFRunPtr::GetCF((CCFRunPtr *)v278) & 0x10000000) != 0 )
        goto LABEL_86;
      v48 = -*((_DWORD *)this + 26);
      if ( *((int *)this + 26) > 0 )
        v48 = *((_DWORD *)this + 26);
      CRunPtrBase::Move((CRunPtrBase *)v278, v48);
      CRunPtrBase::AdjustBackward((CRunPtrBase *)v278);
      v49 = (*(_DWORD *)CCFRunPtr::GetCF((CCFRunPtr *)v278) & 0x10000000) == 0;
    }
    if ( !v49 )
    {
LABEL_86:
      v207 = 0;
      v221 = 0;
      CTxtRange::FindAttributes(this, (int *)&v207, &v221, -1879048192);
      CTxtRange::Set(this, v207, v207 - v221);
      v16 = *((_DWORD *)this + 26);
    }
LABEL_87:
    v36 = 0;
  }
  v50 = *((_DWORD *)this + 26);
  v205 = v50;
  if ( v50 > 0 )
  {
    v51 = v50;
    v222 = -v50;
LABEL_93:
    v52 = (__int128 *)((char *)this + 24);
    goto LABEL_94;
  }
  v51 = -v16;
  v222 = v36;
  if ( v50 < 0 )
  {
    CRunPtrBase::AdjustForward((CTxtRange *)((char *)this + 64));
LABEL_92:
    v205 = v51;
    goto LABEL_93;
  }
  if ( v51 || (v244 & 0xA) == 0 )
    goto LABEL_92;
  if ( (v244 & 2) != 0 )
  {
    CTxtRange::FindWord(this, &v225, &v224, 1);
    v60 = v225;
    if ( v225 < *((_DWORD *)this + 10) )
    {
      v205 = v224;
      if ( *((_DWORD *)this + 10) < v224 )
      {
        v207 = 0;
        CTxtRange::CTxtRange((CTxtRange *)v297, this);
        CTxtRange::Set((CTxtRange *)v297, v60, v60 - v205);
        v259 = CTxtRange::WriteAccessDenied((CTxtRange *)v297, 0);
        if ( !v259
          && ((*(_DWORD *)(v15 + 176) & 0x80000) == 0
           || (a5 & CTxtRange::GetCharFormat((CTxtRange *)v297, (struct CCharFormat *)v232, 0, &v207, 0)) == a5
           && (v207 & v37) == v37) )
        {
          v222 = v60 - *((_DWORD *)this + 10);
          v51 = v205 - v60;
        }
        v205 = v51;
        CTxtRange::~CTxtRange((CTxtRange *)v297);
        goto LABEL_93;
      }
    }
  }
  v52 = (__int128 *)((char *)this + 24);
  if ( !(unsigned int)CTxtPtr::IsAtEOP((CTxtRange *)((char *)this + 24))
    || *((_WORD *)CRchTxtPtr::GetPF((CTxtRange *)((char *)this + 8)) + 28) )
  {
    v205 = 0;
  }
  else
  {
    v61 = *((_QWORD *)this + 5);
    v270 = *v52;
    v271 = v61;
    v205 = CTxtPtr::AdvanceCRLF(&v270, 2);
    v51 = v205;
    CRunPtrBase::AdjustForward((CTxtRange *)((char *)this + 64));
    v202 |= 0x1000u;
    v256 = 1;
  }
LABEL_94:
  v220 = v51;
  v53 = a5;
  if ( (a5 & 0x2000000) != 0 && (unsigned int)CW32System::IsBiDiLcid(v286[2]) )
  {
    LOBYTE(v54) = CCharFormat::CharRepFromLang((CCharFormat *)&v285);
    v278[0] = *(_OWORD *)CCharFlags::FontSigFromCharRep(v292, v54);
    CTxtEdit::OrCharFlags(v15, v278, 0, v227);
  }
  if ( (*(_DWORD *)(v15 + 280) & 0x200) == 0 && (*(_BYTE *)(v15 + 358) & 1) == 0 )
  {
    if ( v27
      || (a5 & 0x20000000) != 0
      && (CTxtEdit::FGlyphAll((CTxtEdit *)v15)
       || (FontOptions = CTxtEdit::GetFontOptions(v55, &v270),
           FontInfoFlags = CFICache::GetFontInfoFlags(v285.m128i_u16[3], FontOptions),
           (FontInfoFlags & 0x100) != 0)
       || (FontInfoFlags & 0x200) != 0 && (*(_BYTE *)(v15 + 284) & 0x10) != 0) )
    {
      CTxtEdit::OnSetTypographyOptions((CTxtEdit *)v15, 1u, 1);
    }
  }
  if ( (v37 & 0xB000001F) != 0
    && (*(_BYTE *)(v15 + 358) & 1) == 0
    && (((unsigned __int8)v37 & BYTE4(v288) & 0x1F) != 0
     || (v37 & 0x10000000) != 0 && BYTE11(v288)
     || v37 < 0 && BYTE9(v288)
     || (v37 & 0x20000000) != 0 && BYTE8(v288) && (v58 = *(_QWORD *)(v15 + 256)) != 0 && *(_QWORD *)(v58 + 64)) )
  {
    if ( (v37 & 0xFFFFFFE3) == 0 )
    {
      v59 = v227;
      if ( (*((_BYTE *)v227 + 71) & 4) == 0 )
      {
        *(_DWORD *)(v15 + 280) |= 0x4000u;
        goto LABEL_137;
      }
    }
    CTxtEdit::OnSetTypographyOptions((CTxtEdit *)v15, 1u, 1);
  }
  v59 = v227;
LABEL_137:
  if ( v27 )
  {
    v269 = 0;
    v268 = 0x1000000;
    CTxtEdit::OrCharFlags(v15, &v268, v248, v59);
  }
  v258 = CCharFormat::fSetStyle((CCharFormat *)&v285, a5, v202);
  v63 = v37 | (((*(unsigned __int16 *)(v15 + 276) >> 6) & 1) << 17);
  v64 = 2600;
  v218 = v63;
  if ( v205 == v62 )
    goto LABEL_506;
  v65 = *(struct CDisplay **)(v15 + 136);
  v230 = v62;
  v66 = v62;
  v215 = v62;
  CFreezeDisplay::CFreezeDisplay((CFreezeDisplay *)v279, v65);
  v282 = 0;
  *(_QWORD *)&v283 = 0;
  DWORD2(v283) = 0;
  v284 = 0;
  if ( (v244 & 0x40000000) != 0 )
  {
    v277 = 0;
    goto LABEL_153;
  }
  v67 = *(_QWORD *)(((*(_QWORD *)v52 - 8LL) & -(__int64)(*(_QWORD *)v52 != 0)) + 0x30);
  v277 = (CNotifyMgr *)((v67 + 232) & -(__int64)(v67 != 0));
  if ( !v277 )
  {
LABEL_153:
    v70 = v222;
    goto LABEL_154;
  }
  CTxtRange::CTxtRange((CTxtRange *)v297, this);
  v68 = *((_DWORD *)this + 10);
  if ( *((int *)this + 26) > 0 )
    v68 = *((_DWORD *)this + 10) - *((_DWORD *)this + 26);
  CTxtRange::SetCp((CTxtRange *)v297, v68, 0);
  v284 = v227;
  v69 = *((_DWORD *)this + 10);
  v282 = 0;
  v70 = v222;
  v230 = v222 + v69;
  v283 = 0;
  PF = CRchTxtPtr::GetPF((CRchTxtPtr *)v298);
  if ( !*((_WORD *)PF + 28) || (*((_WORD *)PF + 21) & 0x400) != 0 )
    goto LABEL_150;
  v221 = 0;
  v207 = 0;
  CTxtRange::FindParagraph((CTxtRange *)v297, &v221, (int *)&v207, 1);
  v72 = *((_DWORD *)this + 10);
  if ( *((int *)this + 26) < 0 )
    v72 = *((_DWORD *)this + 10) - *((_DWORD *)this + 26);
  if ( (int)v207 > v72 )
  {
LABEL_150:
    v74 = v220;
    v73 = v230;
  }
  else
  {
    v73 = v221;
    v74 = v230 - v221 + v220;
    v230 = v221;
    v220 = v74;
  }
  CNotifyMgr::NotifyPreReplaceRange(
    v277,
    (CTxtRange *)((char *)this + 8),
    0x3FFFFFFF,
    0,
    0,
    v73,
    v73 + v74,
    (struct tagNOTIFY_DATA *)&v282);
  CTxtRange::~CTxtRange((CTxtRange *)v297);
LABEL_154:
  CRunPtrBase::Move((CTxtRange *)((char *)this + 64), v70);
  v75 = *((_OWORD *)this + 4);
  v210 = v70 + *((_DWORD *)this + 10);
  v250 = v75;
  if ( v248 )
  {
    v76 = 0;
    v207 = 0;
    if ( (*((_BYTE *)v227 + 71) & 1) != 0 )
    {
      CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v297, (CTxtRange *)((char *)this + 8));
      if ( v70 )
      {
        CRunPtrBase::Move((CRunPtrBase *)v300, v70);
        CTxtPtrEx::Move((CTxtPtrEx *)v299, v70);
      }
      v78 = CRchTxtPtr::ExpandRangeFormatting((CRchTxtPtr *)v297, v205, 0, (int *)&v207);
      v76 = v207;
      v77 = v78;
    }
    else
    {
      v77 = 0;
    }
    CRunPtrBase::Move((CRunPtrBase *)&v250, v77);
    ReplaceFormattingAE = CAntiEventDispenser::CreateReplaceFormattingAE(
                            v79,
                            (struct CTxtEdit *)v15,
                            v77 + v210,
                            (struct CFormatRunPtr *)&v250,
                            v205 + v76 - v77,
                            v260,
                            0);
    CRunPtrBase::Move((CRunPtrBase *)&v250, -v77);
    if ( ReplaceFormattingAE )
      (*(void (__fastcall **)(struct IUndoBuilder *, struct IAntiEvent *))(*(_QWORD *)v248 + 8LL))(
        v248,
        ReplaceFormattingAE);
    v53 = a5;
  }
  v81 = v202;
  v226 = 0;
  v242 = 0;
  v265 = 0;
  v267 = 0;
  v266 = 0;
  v253 = v53;
  v254 = v202;
  v276 = v218;
  IsBiDiCharRep = 0;
  v261 = 0;
  if ( (v202 & 0x100) == 0 || (v223 = 1, (*((_BYTE *)v227 + 70) & 0x78) != 0) )
    v223 = 0;
  if ( !v27 || (v53 & 1) != 0 )
  {
    v214 = 0;
    if ( !v27 )
    {
LABEL_171:
      v255 = 0;
      goto LABEL_172;
    }
  }
  else
  {
    v214 = 1;
  }
  v255 = 1;
  if ( (v53 & 2) != 0 )
    goto LABEL_171;
LABEL_172:
  if ( (v218 & 0x800000) == 0 || (v221 = 1, (BYTE12(v288) & 0x40) == 0) )
    v221 = 0;
  LOBYTE(v82) = v285.m128i_i8[4];
  v83 = v53 & 0x8000000;
  v238 = 0;
  v207 = v53 & 0x8000000;
  LOBYTE(v225) = 0;
  v212 = -1;
  v264 = 1;
  if ( (v53 & 0x8000000) != 0 && (v202 & 0x10000) == 0 )
  {
    v225 = v285.m128i_u8[4];
    IsBiDiCharRep = CW32System::IsBiDiCharRep(v285.m128i_u8[4]);
    v261 = (unsigned int)(v82 - 12) <= 3;
    v238 = (_BYTE)v82 == 10 || v84 == 17;
  }
  v85 = *(_OWORD *)((char *)this + 24);
  v273 = *((_QWORD *)this + 5);
  v263 = 0;
  v224 = 0;
  v272 = v85;
  v86 = *((_OWORD *)this + 3);
  *(_OWORD *)Block = 0;
  v274 = v86;
  if ( !v223 )
  {
    v87 = *(_WORD *)(v15 + 278);
    if ( (v87 & 2) != 0 && (v53 & 0x20000000) != 0 && (v81 & 0x10000) == 0 )
    {
      v223 = 1;
      if ( (v87 & 0x200) != 0 )
      {
        v263 = 1;
        if ( !v83 || (v224 = 1, (_BYTE)v82) )
          v224 = 0;
      }
    }
  }
  CFontOptions::CFontOptions((CFontOptions *)&v270, (const struct CTxtEdit *)v15);
  if ( v90 && !v88 && (v53 & 0x20000000) != 0 )
  {
    CFICache::GetFontInfoFromFaceName(
      v285.m128i_i16[3],
      (const struct CFontOptions *)&v270,
      (struct CCharFlags *)&v265,
      0);
    v242 = v265;
    v267 = v266;
    if ( !v265 && !v266 && v83 )
    {
      LOBYTE(v91) = v285.m128i_i8[4];
      v92 = (__int64 *)CCharFlags::FontSigFromCharRep(v278, v91);
      v93 = v92[1];
      v242 = *v92;
      v267 = v93;
    }
    v89 = v202;
  }
  if ( (*(_BYTE *)(v15 + 278) & 2) != 0 && (v89 & 0x2000) == 0 )
    v202 = v89 | 0x1000;
  v94 = (CTxtRange *)((char *)this + 8);
  IsRich = CRchTxtPtr::IsRich((CTxtRange *)((char *)this + 8));
  v96 = 0;
  if ( IsRich )
  {
    TextLength = CTxtPtr::GetTextLength((CTxtRange *)((char *)this + 24));
    v99 = v205;
    if ( v205 + v210 == TextLength && ((unsigned __int16)v53 & v98 & 0x120) != 0 )
      v99 = --v205;
  }
  else
  {
    v99 = v205;
  }
  *(_DWORD *)v232 = v96;
  if ( v99 <= 0 )
  {
LABEL_469:
    free(Block[1]);
    CRunPtrBase::AdjustBackward((CTxtRange *)((char *)this + 64));
    CRunPtrBase::AdjustForward((CRunPtrBase *)&v250);
    if ( (unsigned int)CFormatRunPtr::MergeRuns((CFormatRunPtr *)&v250, *((_DWORD *)this + 18), v260) && v281 )
    {
      CTxtRange::GetRange(this, &v249, &v243);
      v229 = v243;
      v228 = v249;
    }
    v180 = (CTxtRange *)((char *)this + 64);
    if ( v222 )
      CRunPtrBase::Move(v180, -v222);
    else
      CRunPtrBase::AdjustForward(v180);
    v181 = CRchTxtPtr::IsRich(v94);
    v182 = 0;
    if ( v181 )
    {
      if ( *(_WORD *)(v15 + 56) )
      {
        if ( (-(__int64)(v15 != 0) & (v15 + 48)) != 0 )
        {
          ActiveStory = CTxtEdit::GetActiveStory((CTxtEdit *)v15);
          if ( v227 == ActiveStory && (v204[0] == (_BYTE)v182 || v204[1] != (_BYTE)v182) )
            CCallMgrCenter::SetChangeEvent((v15 + 48) & -(__int64)(v15 != 0), 0);
        }
      }
    }
    if ( v277 )
    {
      HIDWORD(v282) = v253;
      LODWORD(v283) = v254;
      v184 = v282;
      if ( (v218 & 0xFFFFFFBF) != 0 )
        v184 = 2;
      LODWORD(v282) = v184;
      CNotifyMgr::NotifyPostReplaceRange(
        v277,
        v94,
        0x3FFFFFFF,
        0,
        v182,
        v230,
        v220 + v230 - v99,
        (struct tagNOTIFY_DATA *)&v282);
      v182 = 0;
    }
    v185 = *((_DWORD *)this + 26);
    v186 = *((_DWORD *)this + 10);
    if ( (*(_DWORD *)(v15 + 184) & 0x40000000) == 0
      && (*((_DWORD *)this + 29) & 0x20000) == 0
      && v231 < v210
      && (v202 & 0x2080) == 0
      && (*((_DWORD *)this + 29) & 0x40000) == 0 )
    {
      v187 = CTxtRange::SetMathCharFormat(this, v248, &v231, &v239, &v220, v255, v214, v240);
      v182 = 0;
      if ( !v187 )
      {
        v188 = v231;
        if ( v228 < v231 )
          v188 = v228;
        v228 = v188;
        v189 = v239;
        if ( v229 > v239 )
          v189 = v229;
        v229 = v189;
      }
    }
    if ( v248
      && v244 >= (int)v182
      && (*((_BYTE *)this + 116) & 0x40) != 0
      && (v204[0] == (_BYTE)v182 || v204[1] != (_BYTE)v182) )
    {
      HandleSelectionAEInfo(v15, v248, v186, v185, *((_DWORD *)this + 10), *((_DWORD *)this + 26), 2, v182);
    }
    if ( !*((_DWORD *)this + 26) )
    {
      if ( v256 )
      {
        CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)v279);
        v53 = a5;
        v64 = 2600;
LABEL_506:
        CharFormat = CTxtEdit::GetCharFormat((CTxtEdit *)v15, *((_WORD *)this + 56));
        *(_OWORD *)v232 = *(_OWORD *)CharFormat;
        v191 = *(__m128i *)v232;
        v233 = *((_OWORD *)CharFormat + 1);
        v234 = *((__m128i *)CharFormat + 2);
        v235 = *((_OWORD *)CharFormat + 3);
        v236 = *((_DWORD *)CharFormat + 16);
        CFontOptions::CFontOptions((CFontOptions *)&v270, (const struct CTxtEdit *)v15);
        v192 = _mm_cvtsi128_si32(v191);
        if ( (v192 & 0x20) != 0 && *(_QWORD *)(v15 + 248) && (*(_DWORD *)(v15 + 176) & 0x10000) == 0 )
          a5 = v53 & 0xFFFFFFDF;
        if ( (v192 & 0x10000000) == 0 || (v193 = 1, (_mm_cvtsi128_si32(_mm_srli_si128(v191, 5)) & 0xF0) != 0x80) )
          v193 = 0;
        if ( v258 )
          CCharFormat::ApplyDefaultStyle((CCharFormat *)v232, (__int16)v287, (const struct CFontOptions *)&v270);
        result = CCharFormat::Apply(
                   (CCharFormat *)v232,
                   (const struct CCharFormat *)&v285,
                   a5,
                   v202 | 0x1000,
                   v218,
                   v280,
                   *(const struct IDpiAccessor **)(v15 + 568));
        if ( (_DWORD)result )
          return result;
        if ( CTxtEdit::FIdealLayout((CTxtEdit *)v15) )
        {
          if ( *(__int16 *)&v232[8] < 2600 )
            v64 = *(_WORD *)&v232[8];
          *(_WORD *)&v232[8] = v64;
        }
        if ( v245 )
        {
          if ( (*(_DWORD *)v232 & 0x10000000) != 0 )
          {
            v194 = *(_DWORD *)v232 | 2;
            *(_DWORD *)v232 = v194;
            if ( (v194 & 0x20000000) != 0 )
              *(_DWORD *)v232 = v194 & 0xFFFFFFFD;
          }
        }
        if ( v240 )
        {
          if ( v193 )
          {
            v195 = PrevNonMathFont;
            if ( (CFICache::GetFontInfoFlags((unsigned __int16)PrevNonMathFont, &v270) & 0x80u) == 0LL )
            {
              DWORD2(v233) = v241;
              *(_WORD *)&v232[6] = v195;
              v232[5] = 0;
            }
          }
        }
        v196 = v260;
        result = (*(__int64 (__fastcall **)(struct IFormatCache *, unsigned __int8 *, __int16 *))(*(_QWORD *)v260 + 24LL))(
                   v260,
                   v232,
                   v217);
        if ( (_DWORD)result )
          return result;
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v196 + 8LL))(
          v196,
          *((unsigned __int16 *)this + 56));
        v66 = v259 != 0;
        *((_WORD *)this + 56) = v217[0];
LABEL_530:
        v197 = (int *)((char *)this + 40);
        if ( (*((_BYTE *)this + 116) & 0x40) != 0
          && (unsigned int)CRchTxtPtr::IsRich((CTxtRange *)((char *)this + 8))
          && (*(_DWORD *)(v15 + 176) & 0x80000) == 0
          && *(_WORD *)(v15 + 56)
          && (-(__int64)(v15 != 0) & (v15 + 48)) != 0
          && (!v204[0] || v204[1]) )
        {
          CCallMgrCenter::SetSelectionChanged((CCallMgrCenter *)((v15 + 48) & -(__int64)(v15 != 0)));
        }
        if ( v281 )
        {
          if ( v229 >= 0 )
          {
            v198 = v228;
            v199 = v228 - v229;
          }
          else
          {
            v198 = *v197;
            v199 = 0;
          }
          CTxtRange::Set(this, v198, v199);
        }
        if ( v66 || !v205 )
          return v66;
        return v20;
      }
      CTxtRange::Update_iFormat(this, -1);
    }
    v200 = v227;
    v257 = 0;
    (*(void (__fastcall **)(CTxtStory *, int *))(*(_QWORD *)v227 + 56LL))(v227, &v257);
    if ( (v202 & 0x2800) == 0
      && v220
      && !v66
      && !v205
      && CTxtStory::IsComplexScript(v200)
      && v257 != 127
      && (!v204[0] || v204[1]) )
    {
      CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v297, v290);
      CRchTxtPtr::Move((CRchTxtPtr *)v297, v222 + v220);
      CRchTxtPtr::ItemizeReplaceRange((CRchTxtPtr *)v297, v220, 0, v248, 0, 0);
      v20 = 0;
      goto LABEL_551;
    }
    CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)v279);
    goto LABEL_530;
  }
  while ( 1 )
  {
    if ( !(unsigned int)CRunPtrBase::IsValid((CRunPtrBase *)&v250) )
      goto LABEL_468;
    if ( (v101 & 0x1000000) != 0
      && ((unsigned __int8)v53 & v100 & 3) != 0
      && CCharFormat::IsMathZonePlaceHolder((CCharFormat *)v232) )
    {
      while ( 1 )
      {
        Format = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v250);
        if ( (*(_DWORD *)CTxtEdit::GetCharFormat((CTxtEdit *)v15, Format) & 0x20000000) == 0 )
          break;
        if ( v99 <= 0 )
          goto LABEL_468;
        v99 -= CRunPtrBase::GetCchLeft((CRunPtrBase *)&v250);
        v205 = v99;
        CRunPtrBase::NextRun((CRunPtrBase *)&v250);
      }
      if ( v99 <= 0 )
      {
LABEL_468:
        v94 = (CTxtRange *)((char *)this + 8);
        goto LABEL_469;
      }
    }
    v103 = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v250);
    v104 = CTxtEdit::GetCharFormat((CTxtEdit *)v15, v103);
    v105 = *(__m128i *)v104;
    *(_OWORD *)v232 = *(_OWORD *)v104;
    v233 = *((_OWORD *)v104 + 1);
    v234 = *((__m128i *)v104 + 2);
    v235 = *((_OWORD *)v104 + 3);
    v236 = *((_DWORD *)v104 + 16);
    if ( v258 )
    {
      CCharFormat::ApplyDefaultStyle((CCharFormat *)v232, (__int16)v287, (const struct CFontOptions *)&v270);
      v105 = *(__m128i *)v232;
    }
    if ( PrevNonMathFont < 0 || (v53 & 0x20000000) != 0 )
    {
      v106 = _mm_cvtsi128_si32(_mm_srli_si128(v105, 5));
    }
    else
    {
      v106 = _mm_cvtsi128_si32(_mm_srli_si128(v105, 5));
      if ( (v106 & 0xF0) == 0x80 )
      {
        v106 = 0;
        *(_WORD *)&v232[6] = PrevNonMathFont;
        v232[5] = 0;
        v105 = *(__m128i *)v232;
        DWORD2(v233) = v241;
        LOWORD(v206) = PrevNonMathFont;
        goto LABEL_223;
      }
    }
    LOWORD(v206) = _mm_extract_epi16(v105, 3);
LABEL_223:
    v107 = v212;
    v108 = _mm_cvtsi128_si32(_mm_srli_si128(_mm_load_si128(&v234), 12));
    v109 = _mm_cvtsi128_si32(v105);
    if ( v212 == -1 )
    {
      v107 = v108;
      v212 = v108;
      if ( (v109 & 0x1000000) != 0 )
      {
        v107 = v108 - 1;
        v212 = v107;
LABEL_227:
        v110 = v218 & 0xFEFFFFFF;
        v218 &= ~0x1000000u;
        if ( v108 > v107 + 1 && v221 )
          v218 = v110 & 0xFF7FFFFF;
        goto LABEL_233;
      }
    }
    else if ( (v109 & 0x1000000) != 0 )
    {
      goto LABEL_227;
    }
    if ( v108 > v107 && v221 )
      v218 &= ~0x800000u;
LABEL_233:
    v203 = v99;
    if ( !v237 && !v209 && !v247 )
    {
      v111 = v202;
      if ( (v109 & 0x800120) == 0x800120 )
      {
        v53 &= ~0x100u;
        a5 = v53;
      }
      goto LABEL_269;
    }
    if ( (v109 & 0x800000) != 0 )
    {
      v53 &= ~0x100u;
LABEL_243:
      a5 = v53;
      goto LABEL_268;
    }
    if ( v237 && (v109 & 0x20) != 0 )
    {
      v53 |= 0x20u;
      goto LABEL_243;
    }
    if ( v226 )
    {
      v203 = v226;
      v226 = 0;
      if ( (v202 & 0x10000) != 0 )
        v53 &= 0xC7FFFEFF;
      else
        v53 &= ~0x100u;
      v111 = v202 & 0xC7FFFFFF;
      a5 = v53;
      v202 &= 0xC7FFFFFF;
      goto LABEL_269;
    }
    CTxtPtrEx::SetCp((CTxtPtrEx *)&v272, v210);
    CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v250);
    if ( v99 < CchLeft )
      CchLeft = v99;
    v113 = 0;
    if ( CchLeft <= 0 )
    {
LABEL_265:
      v113 = v203;
    }
    else
    {
      while ( 1 )
      {
        Char = CTxtPtr::GetChar((CTxtPtr *)&v272);
        if ( Char == 7 )
          break;
        v115 = Char;
        if ( v247 )
        {
          if ( (unsigned int)Char - 64976 <= 0x1F )
            break;
        }
        v116 = v212;
        if ( (unsigned int)Char - 65529 <= 2 && (unsigned int)CTxtPtr::IsAtTRD((CTxtPtr *)&v272, 0) )
        {
          v118 = v209;
          v226 = 2;
          v212 = v116;
LABEL_273:
          v209 = v118;
LABEL_274:
          v203 = v113;
          goto LABEL_266;
        }
        v117 = CTxtPtrEx::AdvanceCRLF(&v272, 0);
        if ( (unsigned int)(v115 - 10) > 3 )
        {
          v118 = v209;
        }
        else
        {
          if ( (unsigned int)CTxtPtr::IsAtTRD((CTxtPtr *)&v272, 0xFFF9u) )
          {
            v226 = v117 + 2;
            goto LABEL_274;
          }
          v118 = v209;
          if ( v209 && !v237 )
          {
            v226 = 1;
            goto LABEL_273;
          }
        }
        v113 += v117;
        if ( v113 >= CchLeft )
        {
          v209 = v118;
          goto LABEL_265;
        }
      }
      v226 = 1;
      v203 = v113;
    }
LABEL_266:
    v53 = a5;
    if ( v113 )
      break;
    v66 = v215;
LABEL_458:
    v99 = v205;
    if ( v205 <= 0 )
      goto LABEL_468;
  }
  v106 = v232[5];
  v109 = *(_DWORD *)v232;
  v105 = *(__m128i *)v232;
  LOWORD(v206) = *(_WORD *)&v232[6];
LABEL_268:
  v111 = v202;
LABEL_269:
  v213 = 1;
  if ( (v109 & 0x40000) != 0 )
  {
    v119 = v53 & 0xD5FFFFFF;
    a5 = v119;
    goto LABEL_271;
  }
  if ( (*(_DWORD *)(v15 + 176) & 0x10000) != 0
    || !v209
    || (v106 & 0xF0) == 0x80
    || (v111 & 0x10000) == 0 && (a5 & 0x20000000) != 0 && (v285.m128i_i8[5] & 0xF0) == 0x80 )
  {
    v119 = a5;
    if ( !v223
      && ((v109 & 0x10000000) == 0
       || (v111 & 0x10000) != 0
       || (a5 & 0x20000000) == 0
       || (v285.m128i_i8[5] & 0xF0) == 0x80) )
    {
LABEL_271:
      LODWORD(v120) = v203;
      v232[4] = _mm_cvtsi128_si32(_mm_srli_si128(v105, 4));
      goto LABEL_388;
    }
    v124 = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v250);
    v125 = _mm_srli_si128(v105, 4);
    if ( (int)v203 < v124 )
      v124 = v203;
    v126 = v205 < v124;
    v120 = (unsigned int)v124;
    v127 = _mm_cvtsi128_si32(v125);
    if ( v126 )
      v120 = (unsigned int)v205;
    v203 = v120;
    v232[4] = v127;
    if ( v127 == 10 && (v111 & 1) != 0 )
    {
      if ( v238 )
        goto LABEL_388;
      v119 = a5 & 0xF7FFFFFF;
      a5 = v119;
      if ( (v119 & 0x20000000) == 0 )
        goto LABEL_388;
      if ( CFICache::IsSymbolFont(v285.m128i_i16[3], (const struct CFontOptions *)&v270) )
      {
        v119 &= ~0x20000000u;
        a5 = v119;
      }
LABEL_306:
      v109 = *(_DWORD *)v232;
      goto LABEL_290;
    }
    if ( v238 )
      goto LABEL_388;
    LOBYTE(v120) = v232[4];
    CCharFlags::FontSigFromCharRep(v292, v120);
    v130 = v292[0];
    v131 = v292[0] & 0xFFFFFFFFFFFFFF3FuLL;
    if ( (v109 & 0x30000000) == 0x10000000 && (v106 & 0xF0) == 0x80 && (v129 & 0xF0) != 0x80 )
    {
      v268 = v128;
      v269 = v128;
      v132 = 1;
      FontInfoFromFaceName = CFICache::GetFontInfoFromFaceName(
                               v206,
                               (const struct CFontOptions *)&v270,
                               (struct CCharFlags *)&v268,
                               0);
      LODWORD(v128) = 0;
      if ( !FontInfoFromFaceName )
        v131 &= ~v268;
    }
    else
    {
      v132 = v128;
    }
    if ( (v242 & v130) != 0 || (v134 = v128, (v267 & v292[1]) != 0) )
      v134 = 1;
    if ( v261 != (_DWORD)v128 || (v135 = v128, (v242 & 0x7800000000F00000LL) != 0) )
      v135 = 1;
    if ( (unsigned int)v232[4] - 12 <= 3 || (v206 = v128, (unsigned int)v232[4] - 46 <= 3) )
      v206 = 1;
    a5 &= ~0x8000000u;
    CTxtPtrEx::SetCp((CTxtPtrEx *)&v272, v210);
    v136 = CTxtPtr::GetChar((CTxtPtr *)&v272);
    if ( (unsigned int)v136 - 57344 <= 0x18FF )
    {
      v119 = a5;
      LODWORD(v120) = v203 - CTxtPtrEx::MoveWhile((CTxtPtrEx *)&v272, v203, 0xE000u, 0xF8FFu, 1);
      v203 = v120;
LABEL_387:
      v109 = *(_DWORD *)v232;
      goto LABEL_388;
    }
    if ( v136 >= 0x80u )
    {
      v137 = 0;
      v215 = 0;
    }
    else
    {
      v202 |= 8u;
      v137 = 0;
      v215 = 1;
    }
    v138 = v242;
    if ( !v134 )
    {
      if ( (v131 & 0xFF800000000LL) != 0 && (v242 & 0xFF800000000LL) != 0 )
      {
        if ( (unsigned int)v136 - 2404 <= 1 )
        {
          v203 = 1;
          v134 = 1;
          v139 = CCharFlags::CharRepFontSig(v242 & 0xFF800000000LL, 1);
          v138 = v242;
          v140 = a5 | 0x8000000;
          a5 |= 0x8000000u;
          v137 = 0;
          v232[4] = v139;
LABEL_340:
          if ( IsBiDiCharRep || (unsigned int)CW32System::IsBiDiCharRep(v232[4]) )
          {
            v144 = v224;
            if ( !v224 )
            {
              v145 = v215;
              goto LABEL_344;
            }
          }
          else
          {
            v144 = v224;
          }
          v145 = v215;
          if ( v215 && !v132 && ((v138 & 0xC0) == 0xC0 || v135) )
          {
            v146 = v206;
            if ( v263 == v137 || v206 || !(_BYTE)v225 )
            {
              if ( v134 && !v144 && (!(unsigned int)CW32System::IsLatinCharRep(v225) || (v202 & 1) == 0) )
                goto LABEL_369;
              v148 = v140 | 0x8000000;
            }
            else
            {
              v148 = v140 & 0xDFFFFFFF;
            }
            a5 = v148;
LABEL_369:
            v147 = v202;
            goto LABEL_370;
          }
LABEL_344:
          if ( !v134 && (v232[4] != 9 || *(_WORD *)&v232[6] == 1) )
          {
            v146 = v206;
            v147 = v202 & 0xFFEFFFFF;
            v202 &= ~0x100000u;
            a5 = v140 & 0xDFFFFFFF;
LABEL_370:
            Exact = CTxtPtrEx::FindExact((CTxtPtrEx *)&v272, v203, &dword_1802B1B14, 0);
            LODWORD(v120) = v203;
            if ( Exact == -1 )
            {
              LODWORD(v120) = v203 - CTxtPtrEx::MoveWhile((CTxtPtrEx *)&v272, v203, 0, 0x7Fu, v145);
              v203 = v120;
            }
            if ( v134 )
            {
              if ( !v146 )
              {
                v109 = *(_DWORD *)v232;
                if ( (*(_DWORD *)v232 & 0x2000000) == 0 || !(_DWORD)v120 )
                {
                  v119 = a5;
                  goto LABEL_388;
                }
              }
            }
            v301 = v297;
            v302 = 256;
            memset_0(v297, 0, 0x100u);
            if ( v203 < 0x3FFFFFFF
              && (Buf = (unsigned __int16 *)CTempBuf::GetBuf((CTempBuf *)v297, 2 * v203)) != 0
              && (CTxtPtrEx::SetCp((CTxtPtrEx *)&v272, v210), CTxtPtr::GetText((CTxtPtr *)&v272, v203, Buf)) )
            {
              v152 = (const struct CFontOptions *)CTxtEdit::GetFontOptions(v15, v296);
              v154 = Buf;
              v155 = v232[4];
              if ( v207 )
                v155 = v285.m128i_u8[4];
              v119 = a5;
              if ( CheckFontCMap(v285.m128i_i16[3], v155, v153, v154, v152, 0) )
              {
                v119 = a5 & 0xD7FFFFFF;
                a5 &= 0xD7FFFFFF;
                v202 = v147 & 0xFFEFFFFF;
              }
            }
            else
            {
              v119 = a5;
            }
            CTempBuf::FreeBuf((CTempBuf *)v297);
            LODWORD(v120) = v203;
            goto LABEL_387;
          }
          if ( v232[4] == v285.m128i_i8[4] )
          {
            if ( (*(_BYTE *)(v15 + 278) & 2) != 0 && v135 )
              v149 = v140 & 0xDFFFFFFF;
            else
              v149 = v140 | 0x8000000;
            a5 = v149;
          }
          v146 = v206;
          goto LABEL_369;
        }
        v141 = CTxtPtrEx::FindExact((CTxtPtrEx *)&v272, v203, "d\te\t", 0x80000u);
        if ( v141 == -1 )
        {
          v143 = v210;
        }
        else
        {
          v142 = v141;
          v143 = v210;
          v203 = v142 - v210;
        }
        CTxtPtrEx::SetCp((CTxtPtrEx *)&v272, v143);
        v138 = v242;
        v137 = 0;
      }
      v134 = 0;
    }
    v140 = a5;
    goto LABEL_340;
  }
  CharRep = v232[4];
  if ( v232[4] == 9 )
  {
    CTxtPtrEx::SetCp((CTxtPtrEx *)&v272, v210);
    v215 = 0;
    Pch = CTxtPtr::GetPch((CTxtPtr *)&v272, &v215);
    CharFlagsHelper = CCharFlags::GetCharFlagsHelper(Pch, v215, 0, 0, 1, v246, v294);
    CharRep = CCharFlags::GetCharRep((CCharFlags *)&CharFlagsHelper, 0);
    if ( CharRep == 51 )
      CharRep = 0;
  }
  MathFont = CTxtEdit::GetMathFont((CTxtEdit *)v15, CharRep);
  if ( MathFont < 0 )
  {
    v119 = a5;
    goto LABEL_306;
  }
  v119 = a5;
  if ( (v111 & 0x10000) == 0 )
  {
    v119 = a5 & 0xDFFFFFFF;
    a5 &= ~0x20000000u;
  }
  v109 = *(_DWORD *)v232 & 0xFFEFFFFF;
  *(_WORD *)&v232[4] = 0x8000;
  *(_DWORD *)v232 &= ~0x100000u;
  *(_WORD *)&v232[6] = MathFont;
LABEL_290:
  LODWORD(v120) = v203;
LABEL_388:
  v156 = 1;
  v157 = v210;
  v275 = v236;
  v251 = 1;
  while ( 2 )
  {
    v158 = v119;
    if ( (v202 & 0x10000) == 0 && v207 && (v119 & 0x8000000) == 0 )
      v158 = v119 & 0xFDFFFFFF;
    if ( v211 && (*(_DWORD *)(v15 + 184) & 0x40000000) == 0 && (*(_BYTE *)(v15 + 278) & 2) == 0
      || (v109 & 0x10000000) != 0 && ((v158 & 3) != 0 || v208) )
    {
      if ( v157 < v231 )
        v231 = v157;
      if ( (int)v120 + v157 > v239 )
        v239 = v120 + v157;
    }
    if ( v204[0]
      && ((_WORD)v235 == (_WORD)v288
       || (LOWORD(v265) = 0, BYTE2(v265) = 0, CW32System::GetTmpData(v288, (struct _tmpDispAttrib *)&v265))
       && (_WORD)v265 == 4
       && ((v160 = BYTE2(v265), v159 == -1) && !BYTE2(v265)
        || (BYTE2(v278[0]) = 0, CW32System::GetTmpData(v159, (struct _tmpDispAttrib *)v278)) && BYTE2(v278[0]) == v160)) )
    {
      v215 = 0;
    }
    else
    {
      v201 = *(struct IDpiAccessor **)(v15 + 568);
      v204[1] = v204[0];
      v161 = CCharFormat::Apply((CCharFormat *)v232, (const struct CCharFormat *)&v285, v158, v202, v218, v280, v201);
      v109 = *(_DWORD *)v232;
      v215 = v161;
    }
    if ( CTxtEdit::FIdealLayout((CTxtEdit *)v15) )
    {
      v163 = 2600;
      if ( *(__int16 *)&v232[8] < 2600 )
        v163 = *(_WORD *)&v232[8];
      *(_WORD *)&v232[8] = v163;
    }
    if ( v245 != v162 && (v109 & 0x10000000) != 0 )
    {
      v164 = v109 | 2;
      *(_DWORD *)v232 = v164;
      if ( (v164 & 0x20000000) != 0 )
        *(_DWORD *)v232 = v164 & 0xFFFFFFFD;
    }
    if ( v216 != (_BYTE)v162 )
    {
      v301 = v297;
      v302 = 256;
      memset_0(v297, 0, 0x100u);
      if ( v203 < 0x3FFFFFFF )
      {
        v165 = (unsigned __int16 *)CTempBuf::GetBuf((CTempBuf *)v297, 2 * v203);
        if ( v165 )
        {
          CTxtPtrEx::SetCp((CTxtPtrEx *)&v272, v210);
          Text = CTxtPtr::GetText((CTxtPtr *)&v272, v203, v165);
          if ( Text > 0 )
          {
            v206 = 0;
            FontName = CFICache::GetFontName(*(__int16 *)&v232[6]);
            if ( FontName )
            {
              v168 = 9;
              v169 = 2;
              if ( (*(_DWORD *)(v15 + 180) & 0x20000000) == 0 )
                v168 = DWORD2(v233);
              if ( (v232[0] & 2) == 0 )
                v169 = (DWORD1(v235) >> 9) & 1;
              HIDWORD(v233) = (*(__int64 (__fastcall **)(struct IProvideFontInfo *, const unsigned __int16 *, _QWORD, _QWORD, int, int, unsigned __int16 *, int, _DWORD, unsigned int *))(*(_QWORD *)v280 + 32LL))(
                                v280,
                                FontName,
                                (unsigned __int16)v233,
                                HIBYTE(v235) & 0xF,
                                v169,
                                v168,
                                v165,
                                Text,
                                HIDWORD(v233),
                                &v206);
              v170 = v206;
              if ( v206 > Text )
                v170 = 0;
              if ( v170 )
              {
                v203 = v170;
                goto LABEL_435;
              }
              goto LABEL_436;
            }
            v170 = v206;
LABEL_435:
            if ( !v170 )
LABEL_436:
              HIDWORD(v233) = 0;
          }
        }
      }
      CTempBuf::FreeBuf((CTempBuf *)v297);
    }
    v66 = v215;
    if ( v215
      || (v171 = v260,
          v215 = (*(__int64 (__fastcall **)(struct IFormatCache *, unsigned __int8 *, __int16 *))(*(_QWORD *)v260 + 24LL))(
                   v260,
                   v232,
                   v217),
          (v66 = v215) != 0) )
    {
      v20 = v66;
      goto LABEL_467;
    }
    if ( v264 )
    {
      v174 = *(LS **)(v15 + 136);
      v264 = 0;
      LS::InvalidateLineCache(v174, v172, v173);
    }
    v175 = CFormatRunPtr::SetFormat((CFormatRunPtr *)&v250, v217[0], v203, v171, v291, v281);
    if ( v175 >= (int)v203 )
    {
      v176 = v251;
    }
    else
    {
      v226 = 0;
      v176 = 0;
      v251 = 0;
    }
    (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v260 + 8LL))(v260, (unsigned __int16)v217[0]);
    if ( v175 != 0x3FFFFFFF )
    {
      if ( v252 )
      {
        v177 = v228;
        v178 = v229;
        if ( v210 < v228 )
          v177 = v210;
        v228 = v177;
        v249 = v177;
        if ( v175 + v210 > v229 )
          v178 = v175 + v210;
        v229 = v178;
        v243 = v178;
      }
      if ( v175 <= 0 || (v205 -= v175, v157 = v175 + v210, ++v156, v210 += v175, v156 > 1) || !v176 )
      {
        v53 = v253;
        v202 = v254;
        v218 = v276;
        a5 = v253;
        goto LABEL_458;
      }
      v109 = *(_DWORD *)v232;
      LODWORD(v120) = v175;
      v203 = v175;
      v119 = a5;
      continue;
    }
    break;
  }
  if ( *(_WORD *)(v15 + 56) && (-(__int64)(v15 != 0) & (v15 + 48)) != 0 )
  {
    v179 = v15 + 60;
    if ( !v15 )
      v179 = 12;
    *(_DWORD *)v179 |= 0x40u;
  }
LABEL_467:
  free(Block[1]);
LABEL_551:
  CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)v279);
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
