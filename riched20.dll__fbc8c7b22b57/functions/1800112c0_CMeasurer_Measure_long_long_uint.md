# CMeasurer::Measure(long,long,uint)

- ea: `0x1800112c0`
- end: `0x180013b3f`
- name: `?Measure@CMeasurer@@IEAAJJJI@Z`
- size: `10367`
- prototype: `__int64 __fastcall(CMeasurer *__hidden this, int, int, unsigned int)`
- caller_count: `5`
- callee_count: `28`
- tags: ``

## callers

- `0x18000ec10`
- `0x18001027c`
- `0x1800104b0`
- `0x18001f788`
- `0x180040aa0`

## callees

- `0x180006570`
- `0x18000b5e0`
- `0x18000fe40`
- `0x180010890`
- `0x1800112c0`
- `0x180013b50`
- `0x180014580`
- `0x18001e3e0`
- `0x18001f4a0`
- `0x180025bb0`
- `0x1800260d0`
- `0x18002e7e4`
- `0x18002fa34`
- `0x180039990`
- `0x180039afc`
- `0x18003c080`
- `0x18003e4cc`
- `0x180043d80`
- `0x180045db8`
- `0x1800486b0`
- `0x18004c798`
- `0x1800560d4`
- `0x18005d214`
- `0x180071974`
- `0x180090024`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180012bec`
- `KERNEL32!MulDiv` at `0x18001315b`
- `KERNEL32!MulDiv` at `0x1800132ff`
- `KERNEL32!MulDiv` at `0x180012bec`
- `KERNEL32!MulDiv` at `0x18001315b`
- `KERNEL32!MulDiv` at `0x1800132ff`
- `KERNEL32!WideCharToMultiByte` at `0x180013575`
- `KERNEL32!WideCharToMultiByte` at `0x180013575`
- `USER32!CharUpperW` at `0x180013753`
- `USER32!CharUpperW` at `0x180013753`
- `GDI32!GetDeviceCaps` at `0x180013867`
- `GDI32!GetDeviceCaps` at `0x180013867`
- `GDI32!DeleteObject` at `0x180011da1`
- `GDI32!DeleteObject` at `0x180011da1`
- `GDI32!GetStockObject` at `0x1800135e5`
- `GDI32!GetStockObject` at `0x1800135e5`
- `GDI32!SelectObject` at `0x180011c2d`
- `GDI32!SelectObject` at `0x180011ce4`
- `GDI32!SelectObject` at `0x180011d91`
- `GDI32!SelectObject` at `0x1800135f9`
- `GDI32!SelectObject` at `0x18001365e`
- `GDI32!SelectObject` at `0x180011c2d`
- `GDI32!SelectObject` at `0x180011ce4`
- `GDI32!SelectObject` at `0x180011d91`
- `GDI32!SelectObject` at `0x1800135f9`
- `GDI32!SelectObject` at `0x18001365e`
- `GDI32!GetCharWidthW` at `0x180011d65`
- `GDI32!GetCharWidthW` at `0x180013515`
- `GDI32!GetCharWidthW` at `0x180011d65`
- `GDI32!GetCharWidthW` at `0x180013515`
- `GDI32!GetCharWidthA` at `0x180011ca6`
- `GDI32!GetCharWidthA` at `0x1800135a3`
- `GDI32!GetCharWidthA` at `0x180011ca6`
- `GDI32!GetCharWidthA` at `0x1800135a3`

## pseudocode

```c
__int64 __fastcall CMeasurer::Measure(CMeasurer *this, int a2, int a3, int a4)
{
  CTxtEdit *v4; // rax
  int v5; // esi
  int v6; // r12d
  int v8; // r14d
  __int64 v9; // rcx
  int v10; // edi
  int v11; // edx
  int v12; // eax
  __int64 v13; // rdx
  __int16 v14; // dx
  __int64 *v15; // rcx
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rdx
  int v19; // edi
  int v20; // esi
  _WORD *v21; // rcx
  BOOL v22; // edi
  int v23; // eax
  __int64 v24; // rdx
  int v25; // r12d
  __int64 v26; // rax
  int v27; // r9d
  int v28; // ecx
  int *v29; // rax
  int v30; // eax
  __int64 v31; // r11
  int v32; // ecx
  int v33; // eax
  void *v34; // rdx
  int v35; // r9d
  int v36; // r8d
  __int64 v37; // r10
  int v38; // ecx
  int v39; // r9d
  unsigned __int16 *v40; // r13
  __int64 v41; // rax
  int v42; // edx
  int v43; // ecx
  _DWORD *v44; // rdx
  int v45; // r14d
  int v46; // edx
  int v47; // ecx
  __int64 v48; // rdx
  __int16 v49; // dx
  HDC v50; // rsi
  char v51; // r15
  __int64 v52; // rcx
  int v53; // edx
  int v54; // eax
  __int64 v55; // rdx
  __int16 v56; // dx
  __int64 *v57; // rdi
  __int64 v58; // r8
  __int64 v59; // rcx
  int v60; // edx
  int v61; // eax
  __int64 v62; // rcx
  __int16 v63; // ax
  __int64 v64; // rdi
  unsigned __int16 v65; // cx
  __int16 v66; // r12
  int *v67; // rdx
  int v68; // r15d
  int v69; // r14d
  int v70; // esi
  __int16 v71; // ax
  int v72; // r8d
  int v73; // r14d
  int v74; // ecx
  __int16 v75; // ax
  unsigned int v76; // ecx
  unsigned int v77; // edi
  __int64 v78; // rsi
  _WORD *v79; // r8
  int v80; // eax
  BOOL v81; // r14d
  int v82; // r15d
  int v83; // r12d
  __int64 v84; // rax
  __int64 v85; // rcx
  int v86; // ecx
  int v87; // eax
  int v88; // r14d
  __int64 v89; // rcx
  int v90; // edx
  int v91; // eax
  __int64 v92; // rcx
  __int16 v93; // ax
  __int16 v94; // ax
  char v95; // dl
  HDC v96; // r9
  __int64 v97; // rax
  BOOL v98; // eax
  int *v99; // r8
  struct CCcs *Ccs; // rax
  __int16 *v101; // rdx
  int v102; // eax
  HGDIOBJ v103; // rax
  void *v104; // r12
  HDC v105; // r10
  unsigned int v106; // r15d
  __int16 v107; // r13
  unsigned __int64 v108; // rcx
  __int64 v109; // rax
  _WORD *v110; // r14
  WCHAR v111; // cx
  HDC v112; // r15
  char v113; // r15
  WCHAR v114; // r13
  int v115; // r12d
  int v116; // r11d
  int v117; // r11d
  __int64 v118; // r8
  int v119; // r10d
  int v120; // r14d
  int v121; // ecx
  int v122; // ecx
  int v123; // r9d
  int *v124; // rdx
  int v125; // eax
  int v126; // ecx
  int v127; // r10d
  __int16 *v128; // r14
  int v129; // ecx
  int v130; // ecx
  __int64 v131; // r9
  int v132; // eax
  int v133; // edx
  int v134; // r8d
  int *v135; // r10
  int v136; // esi
  int v137; // eax
  int v138; // edx
  __int64 v139; // r9
  int v140; // r11d
  __int64 v141; // r8
  int v142; // eax
  int v143; // edx
  int *v144; // r9
  int v145; // eax
  int v146; // ecx
  __int64 v147; // r8
  int v148; // r10d
  int v149; // r14d
  int WordBreak; // edi
  __int64 v151; // r8
  int v152; // eax
  int v153; // ecx
  int v154; // edx
  int *v155; // r9
  int v156; // eax
  int v157; // ecx
  __int64 v158; // r8
  int v159; // r10d
  __int64 v160; // r8
  int v161; // ecx
  int v162; // eax
  int v163; // edx
  int *v164; // r9
  int v165; // eax
  int v166; // ecx
  __int64 v167; // r8
  int v168; // r10d
  int v169; // edi
  int v170; // eax
  int v171; // esi
  int v172; // r10d
  __int64 v173; // r8
  int v174; // r9d
  int v175; // ecx
  int v176; // edx
  int *v177; // r9
  int v178; // eax
  int v179; // ecx
  int v180; // r11d
  int v181; // ecx
  int v182; // ecx
  __int64 v183; // r9
  int v184; // eax
  int v185; // edx
  int v186; // r8d
  int *v187; // r9
  int v188; // edi
  int v189; // eax
  int v190; // edx
  __int64 v191; // r10
  int v192; // r11d
  __int64 v193; // r8
  int v194; // eax
  int v195; // edx
  int *v196; // r8
  int v197; // eax
  int v198; // ecx
  __int64 v199; // r9
  int v200; // r10d
  CArrayBase *v201; // rcx
  int v202; // r9d
  int v203; // eax
  _DWORD *v204; // rdx
  int v205; // r8d
  int v206; // r9d
  const WCHAR *v207; // rcx
  int v208; // edx
  int v209; // edi
  __int64 v210; // r8
  int v211; // eax
  int v212; // ecx
  int v213; // edx
  int *v214; // r9
  int v215; // eax
  int v216; // ecx
  __int64 v217; // r8
  int v218; // r10d
  __int64 v219; // r8
  int v220; // ecx
  int v221; // eax
  int v222; // edx
  int *v223; // r9
  int v224; // eax
  int v225; // ecx
  __int64 v226; // r8
  int v227; // r10d
  CArrayBase *v228; // rcx
  int v229; // r9d
  int v230; // eax
  void *v231; // rdx
  int v232; // r8d
  unsigned __int16 *v233; // r9
  int v234; // ecx
  int v235; // ecx
  unsigned __int16 v236; // cx
  int v237; // r14d
  unsigned int v238; // edi
  bool v239; // zf
  unsigned __int8 v241; // al
  int v242; // edx
  __int64 v243; // r9
  int v244; // r8d
  int v245; // esi
  int v246; // ecx
  int v247; // ecx
  int v248; // edx
  int *v249; // r8
  int v250; // eax
  int v251; // ecx
  int v252; // r10d
  __int64 v253; // rax
  int v254; // edx
  __int64 v255; // rax
  unsigned __int16 PrevChar; // ax
  int v257; // r11d
  CTxtEdit *v258; // rsi
  int v259; // eax
  int v260; // eax
  CCcs *v261; // rcx
  int v262; // ecx
  __int64 v263; // rax
  __int16 v264; // cx
  int v265; // ecx
  int v266; // ecx
  __int64 v267; // r9
  int v268; // eax
  int v269; // edx
  int v270; // r8d
  int *v271; // r9
  int v272; // edi
  int v273; // r10d
  int v274; // edx
  __int64 v275; // rax
  int v276; // r11d
  __int64 v277; // r8
  int v278; // eax
  int v279; // edx
  int *v280; // r8
  int v281; // r9d
  int v282; // ecx
  __int64 v283; // rax
  int v284; // r10d
  __int64 v285; // rax
  int v286; // edx
  int v287; // edx
  int v288; // eax
  int v289; // eax
  int v290; // edx
  _DWORD *v291; // rax
  int v292; // edx
  int v293; // eax
  int v294; // eax
  int v295; // edx
  _DWORD *v296; // rax
  int v297; // r8d
  int v298; // eax
  int v299; // eax
  int v300; // r8d
  _DWORD *v301; // rax
  int v302; // edx
  int v303; // eax
  int v304; // eax
  int v305; // edx
  _DWORD *v306; // rax
  int v307; // edx
  int v308; // eax
  int v309; // eax
  int v310; // edx
  _DWORD *v311; // rax
  int v312; // edx
  int v313; // eax
  int v314; // eax
  int v315; // edx
  _DWORD *v316; // rax
  int v317; // eax
  int v318; // edx
  int v319; // eax
  int v320; // eax
  int v321; // edx
  _DWORD *v322; // rax
  int v323; // r8d
  int v324; // eax
  int v325; // eax
  int v326; // r8d
  _DWORD *v327; // rax
  int v328; // edx
  int v329; // eax
  int v330; // eax
  int v331; // edx
  _DWORD *v332; // rax
  int v333; // eax
  int v334; // edx
  int v335; // eax
  int v336; // eax
  int v337; // edx
  _DWORD *v338; // rax
  int *v339; // rax
  int v340; // r8d
  int v341; // eax
  int v342; // eax
  int v343; // r8d
  _DWORD *v344; // rax
  int v345; // edx
  int v346; // eax
  int v347; // eax
  int v348; // edx
  _DWORD *v349; // rax
  int v350; // eax
  int v351; // edx
  int v352; // eax
  int v353; // eax
  int v354; // edx
  _DWORD *v355; // rax
  int v356; // edx
  int v357; // eax
  unsigned __int16 v358; // cx
  HGDIOBJ StockObject; // rax
  int v360; // eax
  int v361; // eax
  int v362; // ecx
  __int64 v363; // rax
  CTxtEdit *v364; // rcx
  CObjectMgr *ObjectMgr; // rax
  COleObject *ObjectFromCp; // rax
  __int16 v367; // cx
  int v368; // r8d
  int *v369; // rdx
  int v370; // r8d
  int v371; // edx
  int v372; // eax
  int v373; // ecx
  int v374; // edx
  int cbMultiByte; // [rsp+28h] [rbp-D8h]
  WCHAR WideCharStr[4]; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  int v378; // [rsp+4Ch] [rbp-B4h]
  unsigned int v379; // [rsp+50h] [rbp-B0h]
  int v380; // [rsp+54h] [rbp-ACh] BYREF
  int v381; // [rsp+58h] [rbp-A8h]
  HDC hdc; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 MultiByteStr[2]; // [rsp+68h] [rbp-98h] BYREF
  int v384; // [rsp+6Ch] [rbp-94h]
  int v385; // [rsp+70h] [rbp-90h]
  int v386; // [rsp+74h] [rbp-8Ch] BYREF
  int v387; // [rsp+78h] [rbp-88h]
  int v388; // [rsp+7Ch] [rbp-84h]
  int v389; // [rsp+80h] [rbp-80h]
  int v390; // [rsp+84h] [rbp-7Ch]
  int v391; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v392; // [rsp+90h] [rbp-70h]
  int v393; // [rsp+98h] [rbp-68h]
  int v394; // [rsp+9Ch] [rbp-64h]
  int v395; // [rsp+A0h] [rbp-60h]
  int v396; // [rsp+A4h] [rbp-5Ch]
  CTxtEdit *v397; // [rsp+A8h] [rbp-58h]
  __int64 *v398; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v399; // [rsp+B8h] [rbp-48h] BYREF
  BOOL UsedDefaultChar; // [rsp+C0h] [rbp-40h] BYREF
  HGDIOBJ h; // [rsp+C8h] [rbp-38h]
  HGDIOBJ ho; // [rsp+D0h] [rbp-30h]
  __int64 v403; // [rsp+D8h] [rbp-28h]
  _WORD v404[128]; // [rsp+E0h] [rbp-20h]
  struct tagLOGFONTW v405; // [rsp+1E0h] [rbp+E0h] BYREF

  v4 = (CTxtEdit *)*((_QWORD *)this + 5);
  v389 = a4;
  v5 = a3;
  v378 = a3;
  v6 = a2;
  v387 = a2;
  v397 = v4;
  if ( v4 )
    v8 = *(_DWORD *)(*((_QWORD *)this + 2) + 24LL);
  else
    v8 = 0;
  v9 = *((_QWORD *)this + 8);
  v10 = a4 & 1;
  v396 = v8;
  v394 = 0;
  v379 = 0;
  *(_DWORD *)WideCharStr = 0;
  v395 = 0;
  v388 = 0;
  LODWORD(v403) = 0;
  if ( !v9 || (v11 = *(_DWORD *)(v9 + 8)) == 0 )
  {
    v398 = 0;
LABEL_11:
    v14 = *(_WORD *)(*((_QWORD *)this + 2) + 30LL);
    goto LABEL_12;
  }
  if ( v11 > 0 && (v12 = *((_DWORD *)this + 18), v12 < v11) && *(_QWORD *)v9 && v12 >= 0 )
    v13 = *(_QWORD *)v9 + *(_DWORD *)(v9 + 16) * v12;
  else
    v13 = 0;
  v14 = *(_WORD *)(v13 + 4);
  v398 = 0;
  if ( v14 < 0 )
    goto LABEL_11;
LABEL_12:
  if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, __int64 **))(*(_QWORD *)qword_1800A72C8 + 32LL))(
         qword_1800A72C8,
         (unsigned int)v14,
         &v398) >= 0 )
  {
    v15 = v398;
  }
  else
  {
    v15 = g_defaultPF;
    v398 = g_defaultPF;
  }
  v16 = *((_DWORD *)this + 20);
  *((_QWORD *)this + 18) = v15;
  if ( v16
    && (*((_BYTE *)v15 + 34) || *((_DWORD *)v15 + 5) || *((_DWORD *)v15 + 6) || (*((_WORD *)v15 + 1) & 0x4000) != 0) )
  {
    CRchTxtPtr::Advance(this, -v16);
    *((_OWORD *)this + 5) = 0;
    *((_QWORD *)this + 12) = 0;
    if ( !v10 )
      goto LABEL_16;
    v15 = (__int64 *)*((_QWORD *)this + 18);
    *((_BYTE *)this + 101) = 16;
  }
  else if ( !v10 )
  {
    goto LABEL_16;
  }
  v263 = *((_QWORD *)this + 5);
  *((_BYTE *)this + 101) |= 0x10u;
  if ( (*(_WORD *)(v263 + 184) & 0x2000) != 0 && (unsigned __int16)(*((_WORD *)v15 + 16) + 10) <= 8u )
  {
    v264 = 11;
    if ( *((__int16 *)this + 46) > 11 )
      v264 = *((_WORD *)this + 46);
    *((_WORD *)this + 46) = v264;
  }
LABEL_16:
  v17 = *((_QWORD *)this + 5);
  v18 = *((_QWORD *)this + 18);
  v19 = *(_DWORD *)(v18 + 4);
  if ( (*(_BYTE *)(v17 + 180) & 1) != 0 )
  {
    v20 = *(_DWORD *)(v18 + 12);
    if ( (*(_WORD *)(v17 + 184) & 0x2000) != 0 )
    {
      v19 = 360 * (*(unsigned __int8 *)(v18 + 35) + 1);
      if ( (*((_BYTE *)this + 101) & 0x10) == 0 )
      {
LABEL_323:
        v20 = 0;
        goto LABEL_19;
      }
    }
    else if ( (*((_BYTE *)this + 101) & 0x10) == 0 )
    {
LABEL_19:
      v19 += v20;
      v5 = v378;
      goto LABEL_20;
    }
    if ( *(_WORD *)v18 && (*(_WORD *)(v18 + 42) & 0xF00) != 0x400 )
    {
      v360 = CMeasurer::MeasureBullet(this);
      v361 = CMeasurer::DXtoLX(this, v360);
      v18 = *((_QWORD *)this + 18);
      v362 = *(unsigned __int16 *)(v18 + 44);
      if ( v361 > v362 )
        v362 = v361;
      if ( v20 > v362 )
        v362 = v20;
      v20 = v362;
      goto LABEL_19;
    }
    if ( (*(_WORD *)(v18 + 2) & 0x4000) != 0 )
    {
      v19 += v20;
      goto LABEL_19;
    }
    goto LABEL_323;
  }
LABEL_20:
  if ( (*(_WORD *)(v18 + 2) & 0x4000) != 0 || v19 > 0 )
  {
    v339 = (int *)((char *)this + 116);
    if ( (*((_BYTE *)this + 162) & 2) == 0 )
      v339 = (int *)((char *)this + 132);
    if ( *v339 != 1440 && v19 )
      v19 = MulDiv(v19, *v339, 1440);
  }
  else
  {
    v19 = 0;
  }
  v21 = (_WORD *)*((_QWORD *)this + 15);
  *((_DWORD *)this + 21) = v19;
  if ( v6 >= 0 )
  {
    v253 = *((_QWORD *)this + 13);
    v393 = 1;
    v254 = *(__int16 *)(v253 + 20);
    if ( v21[18] == *(_WORD *)(v253 + 20) && v21[19] == *(_WORD *)(v253 + 22) || (*((_BYTE *)this + 162) & 2) == 0 )
      goto LABEL_42;
    v255 = 20;
    if ( v21 )
      v255 = (__int64)(v21 + 18);
    v6 = CW32System::MulDiv(v6, v254, *(__int16 *)v255);
  }
  else
  {
    v6 = 24575;
    if ( (*(unsigned int (__fastcall **)(_WORD *))(*(_QWORD *)v21 + 128LL))(v21) )
    {
      v22 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 112LL))(*((_QWORD *)this + 15))
         && (*(_BYTE *)(*((_QWORD *)this + 5) + 180LL) & 4) == 0;
      v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 152LL))(*((_QWORD *)this + 15));
      v24 = *((_QWORD *)this + 15);
      v25 = v23;
      v26 = *((_QWORD *)this + 13);
      v27 = *(__int16 *)(v26 + 20);
      if ( (*(_WORD *)(v24 + 36) != *(_WORD *)(v26 + 20) || *(_WORD *)(v24 + 38) != *(_WORD *)(v26 + 22))
        && (*((_BYTE *)this + 162) & 2) != 0 )
      {
        v363 = 0;
        if ( v24 )
          v363 = v24 + 16;
        v25 = CW32System::MulDiv(v25, v27, *(__int16 *)(v363 + 20));
      }
      v28 = *(_DWORD *)(*((_QWORD *)this + 18) + 8LL);
      v29 = (int *)((char *)this + 116);
      if ( v28 <= 0 )
        v28 = 0;
      if ( (*((_BYTE *)this + 162) & 2) == 0 )
        v29 = (int *)((char *)this + 132);
      if ( *v29 != 1440 && v28 )
        v28 = MulDiv(v28, *v29, 1440);
      v6 = v25 - v28 - v22 - *((_DWORD *)this + 21);
    }
    v393 = 0;
    if ( v6 <= 0 )
      v6 = 0;
  }
  v387 = v6;
LABEL_42:
  if ( v5 < 0 || v5 > v8 - *((_DWORD *)this + 8) )
    v5 = v8 - *((_DWORD *)this + 8);
  v30 = *((_DWORD *)this + 22);
  v390 = *((_DWORD *)this + 20);
  v391 = v30;
  v378 = v5;
  while ( 1 )
  {
LABEL_45:
    if ( v5 <= 0 )
      goto LABEL_466;
    v31 = *((_QWORD *)this + 2);
    if ( !v31 || (v32 = *(_DWORD *)(v31 + 8)) == 0 )
    {
      v35 = 0;
LABEL_62:
      v40 = 0;
      v392 = 0;
      goto LABEL_63;
    }
    if ( v32 > 0 && (v33 = *((_DWORD *)this + 6), v33 < v32) && *(_QWORD *)v31 && v33 >= 0 )
      v34 = (void *)(*(_QWORD *)v31 + *(_DWORD *)(v31 + 16) * v33);
    else
      v34 = 0;
    v35 = 0;
    if ( !v34 )
      goto LABEL_62;
    v36 = *((_DWORD *)this + 7);
    if ( v36 == *(_DWORD *)v34 )
    {
      v286 = *((_DWORD *)this + 6);
      if ( v286 >= *(_DWORD *)(v31 + 8) - 1 )
        goto LABEL_62;
      v34 = CArrayBase::Elem(*((CArrayBase **)this + 2), v286 + 1);
      if ( !v34 )
        goto LABEL_62;
      v36 = 0;
    }
    v37 = *((_QWORD *)v34 + 1) + 2LL * v36;
    v38 = *((_DWORD *)v34 + 4);
    if ( 2 * v36 >= v38 )
    {
      v39 = *(_DWORD *)v34;
      v37 += 2LL * (*((_DWORD *)v34 + 5) / 2 - *(_DWORD *)v34);
    }
    else
    {
      v39 = v38 / 2;
    }
    v35 = v39 - v36;
    v40 = 0;
    if ( v35 )
      v40 = (unsigned __int16 *)v37;
    v392 = v40;
    if ( v35 >= v5 )
    {
      v35 = v5;
      v392 = v40;
    }
LABEL_63:
    v41 = *((_QWORD *)this + 6);
    if ( v41 && (v42 = *(_DWORD *)(v41 + 8)) != 0 )
    {
      if ( v42 > 0 && (v43 = *((_DWORD *)this + 14), v43 < v42) && *(_QWORD *)v41 && v43 >= 0 )
        v44 = (_DWORD *)(*(_QWORD *)v41 + *(_DWORD *)(v41 + 16) * v43);
      else
        v44 = 0;
      v45 = *v44 - *((_DWORD *)this + 15);
    }
    else
    {
      if ( *((_QWORD *)this + 5) )
        v88 = *(_DWORD *)(v31 + 24);
      else
        v88 = 0;
      v45 = v88 - *((_DWORD *)this + 8);
    }
    if ( v35 < v45 )
      v45 = v35;
    v384 = v45;
    if ( !v41 || (v46 = *(_DWORD *)(v41 + 8)) == 0 )
    {
      hdc = 0;
LABEL_81:
      v49 = *(_WORD *)(v31 + 28);
      goto LABEL_82;
    }
    if ( v46 > 0 && (v47 = *((_DWORD *)this + 14), v47 < v46) && *(_QWORD *)v41 && v47 >= 0 )
      v48 = *(_QWORD *)v41 + *(_DWORD *)(v41 + 16) * v47;
    else
      v48 = 0;
    v49 = *(_WORD *)(v48 + 4);
    hdc = 0;
    if ( v49 < 0 )
      goto LABEL_81;
LABEL_82:
    if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, HDC *))(*(_QWORD *)qword_1800A72D0 + 32LL))(
           qword_1800A72D0,
           (unsigned int)v49,
           &hdc) >= 0 )
    {
      v50 = hdc;
    }
    else
    {
      v50 = (HDC)g_defaultCF;
      hdc = (HDC)g_defaultCF;
    }
    v385 = *(_DWORD *)v50;
    v51 = v385;
    if ( (v385 & 0x100) == 0 )
      break;
    *((_DWORD *)this + 20) += v45;
LABEL_437:
    v5 = v378 - v45;
    v378 -= v45;
    if ( v45 )
    {
      v243 = *((_QWORD *)this + 2);
      if ( v243 )
      {
        v244 = *(_DWORD *)(v243 + 8);
        if ( v244 )
        {
          v245 = *((_DWORD *)this + 8);
          v246 = v45 + v245;
          if ( v45 + v245 < v245 / 2 )
          {
            *((_QWORD *)this + 3) = 0;
            if ( v246 <= 0 )
              v246 = 0;
            v265 = CRunPtrBase::AdvanceCp((CMeasurer *)((char *)this + 16), v246);
            *((_DWORD *)this + 8) = v265;
          }
          else
          {
            v247 = v45;
            if ( v45 < 0 )
            {
              while ( v247 < 0 )
              {
                v350 = *((_DWORD *)this + 7);
                v351 = v350 + v247;
                if ( -v247 <= v350 )
                {
                  *((_DWORD *)this + 7) = v351;
LABEL_486:
                  v247 = 0;
                  break;
                }
                v352 = *((_DWORD *)this + 6);
                v247 = v351;
                if ( v352 <= 0 )
                {
                  *((_QWORD *)this + 3) = 0;
                  break;
                }
                v353 = v352 - 1;
                *((_DWORD *)this + 6) = v353;
                v354 = *(_DWORD *)(v243 + 8);
                if ( v354 > 0 && v353 < v354 && *(_QWORD *)v243 && v353 >= 0 )
                  v355 = (_DWORD *)(*(_QWORD *)v243 + *(_DWORD *)(v243 + 16) * v353);
                else
                  v355 = 0;
                *((_DWORD *)this + 7) = *v355;
              }
            }
            else
            {
              v248 = *((_DWORD *)this + 6);
              if ( v244 > 0 && v248 < v244 && *(_QWORD *)v243 && v248 >= 0 )
                v249 = (int *)(*(_QWORD *)v243 + *(_DWORD *)(v243 + 16) * v248);
              else
                v249 = 0;
              while ( v247 > 0 )
              {
                v250 = *v249;
                *((_DWORD *)this + 7) += v247;
                v251 = *((_DWORD *)this + 7);
                if ( v251 < v250 )
                  goto LABEL_486;
                v247 = v251 - v250;
                v252 = v248++;
                *((_DWORD *)this + 6) = v248;
                if ( v248 >= *(_DWORD *)(v243 + 8) )
                {
                  *((_DWORD *)this + 6) = v252;
                  *((_DWORD *)this + 7) = v250;
                  break;
                }
                *((_DWORD *)this + 7) = 0;
                v249 = (int *)((char *)v249 + *(int *)(v243 + 16));
              }
            }
            v265 = v45 - v247 + v245;
            *((_DWORD *)this + 8) = v265;
          }
          v266 = v265 - v245;
          if ( v266 )
          {
            v267 = *((_QWORD *)this + 6);
            if ( v267 && (v268 = *(_DWORD *)(v267 + 8)) != 0 )
            {
              v269 = v266;
              if ( v266 >= 0 )
              {
                v270 = *((_DWORD *)this + 14);
                if ( v268 > 0 && v270 < v268 && *(_QWORD *)v267 && v270 >= 0 )
                  v271 = (int *)(*(_QWORD *)v267 + *(_DWORD *)(v267 + 16) * v270);
                else
                  v271 = 0;
                v272 = v266;
                while ( v269 > 0 )
                {
                  v273 = *v271;
                  *((_DWORD *)this + 15) += v269;
                  v274 = *((_DWORD *)this + 15);
                  if ( v274 < v273 )
                    goto LABEL_505;
                  v275 = *((_QWORD *)this + 6);
                  v276 = v270++;
                  *((_DWORD *)this + 14) = v270;
                  if ( v270 >= *(_DWORD *)(v275 + 8) )
                  {
                    *((_DWORD *)this + 14) = v276;
                    *((_DWORD *)this + 15) = v273;
                    goto LABEL_505;
                  }
                  *((_DWORD *)this + 15) = 0;
                  v269 = v274 - v273;
                  v271 = (int *)((char *)v271 + *(int *)(v275 + 16));
                }
                goto LABEL_503;
              }
              v272 = v266;
              while ( v269 < 0 )
              {
                v340 = *((_DWORD *)this + 15);
                if ( -v269 <= v340 )
                {
                  *((_DWORD *)this + 15) = v269 + v340;
                  break;
                }
                v341 = *((_DWORD *)this + 14);
                if ( v341 <= 0 )
                {
                  *((_QWORD *)this + 7) = 0;
                  break;
                }
                v269 += v340;
                v342 = v341 - 1;
                *((_DWORD *)this + 14) = v342;
                v343 = *(_DWORD *)(v267 + 8);
                if ( v343 > 0 && v342 < v343 && *(_QWORD *)v267 && v342 >= 0 )
                  v344 = (_DWORD *)(*(_QWORD *)v267 + *(_DWORD *)(v267 + 16) * v342);
                else
                  v344 = 0;
                *((_DWORD *)this + 15) = *v344;
              }
            }
            else
            {
              v272 = v266;
            }
LABEL_505:
            v277 = *((_QWORD *)this + 8);
            v5 = v378;
            if ( v277 )
            {
              v278 = *(_DWORD *)(v277 + 8);
              if ( v278 )
              {
                if ( v272 < 0 )
                {
                  while ( 1 )
                  {
                    v5 = v378;
                    if ( v266 >= 0 )
                      break;
                    v345 = *((_DWORD *)this + 19);
                    if ( -v266 <= v345 )
                    {
                      *((_DWORD *)this + 19) = v266 + v345;
                      goto LABEL_45;
                    }
                    v346 = *((_DWORD *)this + 18);
                    if ( v346 <= 0 )
                    {
                      *((_QWORD *)this + 9) = 0;
                      goto LABEL_45;
                    }
                    v266 += v345;
                    v347 = v346 - 1;
                    *((_DWORD *)this + 18) = v347;
                    v348 = *(_DWORD *)(v277 + 8);
                    if ( v348 > 0 && v347 < v348 && *(_QWORD *)v277 && v347 >= 0 )
                      v349 = (_DWORD *)(*(_QWORD *)v277 + *(_DWORD *)(v277 + 16) * v347);
                    else
                      v349 = 0;
                    *((_DWORD *)this + 19) = *v349;
                  }
                }
                else
                {
                  v279 = *((_DWORD *)this + 18);
                  if ( v278 > 0 && v279 < v278 && *(_QWORD *)v277 && v279 >= 0 )
                    v280 = (int *)(*(_QWORD *)v277 + *(_DWORD *)(v277 + 16) * v279);
                  else
                    v280 = 0;
                  while ( 1 )
                  {
                    v5 = v378;
                    if ( v266 <= 0 )
                      break;
                    v281 = *v280;
                    *((_DWORD *)this + 19) += v266;
                    v282 = *((_DWORD *)this + 19);
                    if ( v282 < v281 )
                      break;
                    v283 = *((_QWORD *)this + 8);
                    v284 = v279++;
                    *((_DWORD *)this + 18) = v279;
                    if ( v279 >= *(_DWORD *)(v283 + 8) )
                    {
                      *((_DWORD *)this + 18) = v284;
                      *((_DWORD *)this + 19) = v281;
                      goto LABEL_45;
                    }
                    *((_DWORD *)this + 19) = 0;
                    v266 = v282 - v281;
                    v280 = (int *)((char *)v280 + *(int *)(v283 + 16));
                  }
                }
              }
            }
          }
          else
          {
            v272 = 0;
LABEL_503:
            v5 = v378;
            if ( v272 )
            {
              v266 = v272;
              goto LABEL_505;
            }
          }
        }
      }
    }
  }
  v52 = *((_QWORD *)this + 6);
  if ( !v52 || (v53 = *(_DWORD *)(v52 + 8)) == 0 )
  {
    v399 = 0;
    goto LABEL_93;
  }
  if ( v53 > 0 && (v54 = *((_DWORD *)this + 14), v54 < v53) && *(_QWORD *)v52 && v54 >= 0 )
    v55 = *(_QWORD *)v52 + *(_DWORD *)(v52 + 16) * v54;
  else
    v55 = 0;
  v56 = *(_WORD *)(v55 + 4);
  v399 = 0;
  if ( v56 < 0 )
LABEL_93:
    v56 = *(_WORD *)(*((_QWORD *)this + 2) + 28LL);
  if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, __int64 **))(*(_QWORD *)qword_1800A72D0 + 32LL))(
         qword_1800A72D0,
         (unsigned int)v56,
         &v399) >= 0 )
  {
    v57 = v399;
  }
  else
  {
    v57 = g_defaultCF;
    v399 = g_defaultCF;
  }
  v58 = *((_QWORD *)this + 17);
  if ( !v58
    || ((v59 = *((_QWORD *)this + 6)) == 0 || (v60 = *(_DWORD *)(v59 + 8)) == 0
      ? (v63 = -1)
      : (v60 <= 0 || (v61 = *((_DWORD *)this + 14), v61 >= v60) || !*(_QWORD *)v59 || v61 < 0
       ? (v62 = 0)
       : (v62 = *(_QWORD *)v59 + *(_DWORD *)(v59 + 16) * v61),
         v63 = *(_WORD *)(v62 + 4)),
        *((_WORD *)this + 79) != v63 || (*((_BYTE *)this + 162) & 8) != 0) )
  {
    v89 = *((_QWORD *)this + 6);
    if ( v89 && (v90 = *(_DWORD *)(v89 + 8)) != 0 )
    {
      if ( v90 > 0 && (v91 = *((_DWORD *)this + 14), v91 < v90) && *(_QWORD *)v89 && v91 >= 0 )
        v92 = *(_QWORD *)v89 + *(_DWORD *)(v89 + 16) * v91;
      else
        v92 = 0;
      v93 = *(_WORD *)(v92 + 4);
    }
    else
    {
      v93 = -1;
    }
    *((_WORD *)this + 79) = v93;
    if ( v58 )
    {
      v94 = *(_WORD *)(v58 + 10);
      if ( v94 )
        *(_WORD *)(v58 + 10) = v94 - 1;
    }
    v95 = *((_BYTE *)this + 162);
    v96 = 0;
    if ( (v95 & 2) != 0 )
    {
      v97 = *((_QWORD *)this + 13);
      if ( *(_QWORD *)(v97 + 8) && *((_BYTE *)this + 160) == 2 )
        v96 = *(HDC *)(v97 + 8);
    }
    else
    {
      v285 = *((_QWORD *)this + 15);
      if ( *(_QWORD *)(v285 + 24) && *((_BYTE *)this + 161) == 2 )
        v96 = *(HDC *)(v285 + 24);
    }
    v98 = (v95 & 0x10) != 0 && *((_BYTE *)this + 160) == 2;
    v99 = (int *)((char *)this + 112);
    if ( (v95 & 2) == 0 )
      v99 = (int *)((char *)this + 128);
    Ccs = CFontCache::GetCcs(qword_1800A6FC0, (const struct CCharFormat *const)v57, *v99, v96, v98);
    *((_BYTE *)this + 162) &= ~8u;
    *((_QWORD *)this + 17) = Ccs;
    if ( !Ccs )
      return 0xFFFFFFFFLL;
  }
  if ( *((_BYTE *)v57 + 32) == 4 )
    *((_BYTE *)this + 101) |= 0x20u;
  v64 = *((_QWORD *)this + 17);
  *((_WORD *)this + 48) = *(_WORD *)(v64 + 98);
  if ( !v64 )
    return 0xFFFFFFFFLL;
  v380 = v45;
  if ( (v389 & 8) != 0 )
    v381 = v6;
  else
    v381 = v6 - *(__int16 *)(v64 + 98) - v393;
  if ( v45 <= 0 )
  {
LABEL_436:
    v6 = v387;
    v45 = v384;
    goto LABEL_437;
  }
  v65 = *v40;
  if ( *v40
    && ((*(_BYTE *)(*((_QWORD *)this + 5) + 180LL) & 1) != 0 || *((_QWORD *)v397 + 17))
    && (!v390 || v65 != 13 && v65 != 10) )
  {
    v66 = *((_WORD *)this + 46);
    if ( (*((_BYTE *)this + 162) & 2) != 0 )
      v67 = (int *)((char *)this + 112);
    else
      v67 = (int *)((char *)this + 128);
    v68 = 0;
    if ( *((_WORD *)v50 + 5) )
      v68 = CW32System::MulDiv(*((__int16 *)v50 + 5), *v67, 1440);
    v69 = *(__int16 *)(v64 + 90);
    v70 = *(__int16 *)(v64 + 92);
    if ( (*((_BYTE *)this + 162) & 4) != 0 && (*(_BYTE *)(v64 + 123) & 8) != 0 )
    {
      v71 = *(_WORD *)(v64 + 90) ? MulDiv(v69, 15, 100) : 0;
      if ( v71 )
      {
        v70 += v71;
        v69 += 2 * v71;
      }
    }
    v72 = *((__int16 *)this + 47);
    v73 = v69 - v70;
    if ( v73 <= v68 + v73 )
      v73 += v68;
    if ( v70 <= v70 - v68 )
      v70 -= v68;
    v74 = *((__int16 *)this + 46) - v72;
    if ( v73 > v74 )
      LOWORD(v74) = v73;
    if ( v70 <= v72 )
    {
      v75 = v72 + v74;
      LOWORD(v70) = *((_WORD *)this + 47);
    }
    else
    {
      v75 = v74 + v70;
    }
    v45 = v380;
    v51 = v385;
    *((_WORD *)this + 46) = v75;
    *((_WORD *)this + 47) = v70;
    if ( v66 )
    {
      v262 = v388;
      if ( v66 != v75 )
        v262 = 1;
      v388 = v262;
    }
  }
  while ( 2 )
  {
    if ( v45 <= 0 )
      goto LABEL_436;
    v76 = *((unsigned __int16 *)this + 77);
    v77 = *v40;
    *(_DWORD *)WideCharStr = 0;
    Buffer = 0;
    if ( (_WORD)v76 && v77 - 10 > 3 )
      v77 = v76;
    if ( v51 < 0 )
      v77 = (unsigned __int16)CharUpperW((LPWSTR)v77);
    if ( v77 == 65532 )
    {
      v364 = v397;
      *((_BYTE *)this + 101) |= 8u;
      ObjectMgr = CTxtEdit::GetObjectMgr(v364);
      ObjectFromCp = CObjectMgr::GetObjectFromCp(ObjectMgr, *((_DWORD *)this + 8) + v384 - v45);
      if ( ObjectFromCp )
      {
        v239 = (*((_BYTE *)this + 162) & 2) == 0;
        v367 = *((_WORD *)this + 47);
        v380 = 0;
        v386 = 0;
        if ( v239 )
        {
          v368 = *((_DWORD *)this + 33);
          v369 = (int *)((char *)this + 128);
        }
        else
        {
          v368 = *((_DWORD *)this + 29);
          v369 = (int *)((char *)this + 112);
        }
        COleObject::MeasureObj(ObjectFromCp, *v369, v368, &Buffer, &v380, &v386, v367);
        v239 = *((_DWORD *)this + 20) == 0;
        v82 = Buffer;
        v370 = v381;
        *(_DWORD *)WideCharStr = Buffer;
        if ( v239 || Buffer + *((_DWORD *)this + 22) <= v381 )
        {
          v371 = *((__int16 *)this + 47);
          if ( v380 > *((__int16 *)this + 46) - v371 )
            *((_WORD *)this + 46) = v371 + v380;
        }
      }
      else
      {
        v82 = *(_DWORD *)WideCharStr;
        v370 = v381;
      }
      if ( v82 + *((_DWORD *)this + 22) > v370 )
        v394 = 1;
      goto LABEL_153;
    }
    if ( v77 - 9 > 4 )
    {
      if ( v77 - 768 > 0x6F )
      {
        v78 = *((_QWORD *)this + 17);
        if ( (unsigned __int16)v77 >= 0x4E00u
          && ((unsigned int)(unsigned __int16)v77 - 19968 <= 0x51FF
           || (unsigned int)(unsigned __int16)v77 - 63744 <= 0x1FF) )
        {
          if ( (unsigned int)(unsigned __int16)v77 - 44032 <= 0x2BFF )
            v101 = (__int16 *)(v78 + 36);
          else
            v101 = (__int16 *)(v78 + 38);
          v102 = *v101;
          *(_DWORD *)WideCharStr = v102;
          Buffer = v102;
          v81 = v102 != 0;
          goto LABEL_195;
        }
        v79 = (_WORD *)(*(_QWORD *)(v78 + 48) + 4 * (*(int *)(v78 + 16) & (unsigned __int64)(unsigned __int16)v77));
        if ( (_WORD)v77 == *v79 && (v80 = (__int16)v79[1], v79[1]) )
        {
          v81 = 1;
          *(_DWORD *)WideCharStr = (__int16)v79[1];
          Buffer = v80;
        }
        else
        {
          v81 = 0;
        }
        if ( !*(_DWORD *)(v78 + 32) )
        {
          ++*(_DWORD *)(v78 + 28);
          if ( v81 )
            goto LABEL_148;
          if ( v79[1] )
            ++*(_DWORD *)(v78 + 24);
          else
            ++*(_DWORD *)(v78 + 20);
          if ( *(int *)(v78 + 28) >= 64 )
            CWidthCache::CheckPerformance((CWidthCache *)(v78 + 16));
        }
LABEL_195:
        if ( !v81 )
        {
          v103 = SelectObject(*(HDC *)(v78 + 64), *(HGDIOBJ *)(v78 + 72));
          v104 = v103;
          if ( !v103 )
          {
            v82 = *(_DWORD *)WideCharStr;
            goto LABEL_203;
          }
          v105 = *(HDC *)(v78 + 64);
          v106 = *(unsigned __int16 *)(v78 + 116);
          v107 = *(_WORD *)(v78 + 96);
          hdc = v105;
          if ( (unsigned __int16)v77 >= 0x4E00u && (v77 - 19968 <= 0x51FF || v77 - 63744 <= 0x1FF) )
          {
            v128 = (__int16 *)(v78 + 36);
            if ( (unsigned int)(unsigned __int16)v77 - 44032 > 0x2B9F )
              v128 = (__int16 *)(v78 + 38);
            CW32System::REGetCharWidth(v105, v77, v128, v106, v107, cbMultiByte);
            v82 = *v128;
            *(_DWORD *)WideCharStr = v82;
            Buffer = v82;
LABEL_202:
            SelectObject(*(HDC *)(v78 + 64), v104);
            v40 = v392;
            LODWORD(v103) = 1;
LABEL_203:
            if ( !(_DWORD)v103 )
              return 0xFFFFFFFFLL;
            v45 = v380;
LABEL_150:
            if ( v77 == 173 )
            {
              v261 = (CCcs *)*((_QWORD *)this + 17);
              *((_BYTE *)this + 101) |= 4u;
              if ( !(unsigned int)CCcs::Include(v261, 0x2Du, &Buffer) )
                return 0xFFFFFFFFLL;
              v82 = Buffer;
              v372 = Buffer + *((_DWORD *)this + 22);
              *(_DWORD *)WideCharStr = Buffer;
              if ( v372 < v381 || !*((_DWORD *)this + 20) )
              {
                v395 = Buffer;
                v82 = 0;
                *(_DWORD *)WideCharStr = 0;
              }
            }
            else if ( v77 == 8364 )
            {
              *((_BYTE *)this + 101) |= 2u;
            }
LABEL_153:
            v83 = v403 + 1;
            v84 = v403 & 0x1F;
            v403 = (unsigned int)(v403 + 1);
            v85 = 4 * v84;
            v404[v85 + 1] = *((_WORD *)this + 48);
            v404[v85 + 2] = *((_WORD *)this + 46);
            v404[v85 + 3] = *((_WORD *)this + 47);
            v404[v85] = v82;
            v86 = v82 + *((_DWORD *)this + 22);
            *((_DWORD *)this + 22) = v86;
            if ( v86 <= v381 || (v113 = v389, (v389 & 4) == 0) && *((int *)this + 20) <= 0 )
            {
              ++v40;
              v51 = v385;
              v87 = *((_DWORD *)this + 20) + 1;
              --v45;
              *((_DWORD *)this + 20) = v87;
              v392 = v40;
              v380 = v45;
              if ( v77 != 32 )
              {
                v390 = v87;
                v391 = v86;
              }
              continue;
            }
            v114 = WideCharStr[0];
            v115 = v83 - 1;
            v116 = v384;
            *((_DWORD *)this + 22) = v86 - *(_DWORD *)WideCharStr;
            *((_WORD *)this + 48) = v404[4 * (v115 & 0x1F) + 1];
            v117 = v116 - v45;
            if ( !v117 )
              goto LABEL_269;
            v118 = *((_QWORD *)this + 2);
            if ( !v118 )
              goto LABEL_269;
            v119 = *(_DWORD *)(v118 + 8);
            if ( !v119 )
              goto LABEL_269;
            v120 = *((_DWORD *)this + 8);
            v121 = v120 + v117;
            if ( v120 + v117 < v120 / 2 )
            {
              *((_QWORD *)this + 3) = 0;
              if ( v121 <= 0 )
                v121 = 0;
              v129 = CRunPtrBase::AdvanceCp((CMeasurer *)((char *)this + 16), v121);
              *((_DWORD *)this + 8) = v129;
            }
            else
            {
              v122 = v117;
              if ( v117 < 0 )
              {
                while ( v122 < 0 )
                {
                  v317 = *((_DWORD *)this + 7);
                  v318 = v317 + v122;
                  if ( -v122 <= v317 )
                  {
                    *((_DWORD *)this + 7) = v318;
LABEL_238:
                    v122 = 0;
                    break;
                  }
                  v319 = *((_DWORD *)this + 6);
                  v122 = v318;
                  if ( v319 <= 0 )
                  {
                    *((_QWORD *)this + 3) = 0;
                    break;
                  }
                  v320 = v319 - 1;
                  *((_DWORD *)this + 6) = v320;
                  v321 = *(_DWORD *)(v118 + 8);
                  if ( v321 > 0 && v320 < v321 && *(_QWORD *)v118 && v320 >= 0 )
                    v322 = (_DWORD *)(*(_QWORD *)v118 + *(_DWORD *)(v118 + 16) * v320);
                  else
                    v322 = 0;
                  *((_DWORD *)this + 7) = *v322;
                }
              }
              else
              {
                v123 = *((_DWORD *)this + 6);
                if ( v119 > 0 && v123 < v119 && *(_QWORD *)v118 && v123 >= 0 )
                  v124 = (int *)(*(_QWORD *)v118 + *(_DWORD *)(v118 + 16) * v123);
                else
                  v124 = 0;
                while ( v122 > 0 )
                {
                  v125 = *v124;
                  *((_DWORD *)this + 7) += v122;
                  v126 = *((_DWORD *)this + 7);
                  if ( v126 < v125 )
                    goto LABEL_238;
                  v122 = v126 - v125;
                  v127 = v123++;
                  *((_DWORD *)this + 6) = v123;
                  if ( v123 >= *(_DWORD *)(v118 + 8) )
                  {
                    *((_DWORD *)this + 6) = v127;
                    *((_DWORD *)this + 7) = v125;
                    break;
                  }
                  *((_DWORD *)this + 7) = 0;
                  v124 = (int *)((char *)v124 + *(int *)(v118 + 16));
                }
              }
              v129 = v117 - v122 + v120;
              *((_DWORD *)this + 8) = v129;
            }
            v130 = v129 - v120;
            if ( !v130 )
            {
              v136 = 0;
              goto LABEL_255;
            }
            v131 = *((_QWORD *)this + 6);
            if ( v131 && (v132 = *(_DWORD *)(v131 + 8)) != 0 )
            {
              v133 = v130;
              if ( v130 >= 0 )
              {
                v134 = *((_DWORD *)this + 14);
                if ( v132 > 0 && v134 < v132 && *(_QWORD *)v131 && v134 >= 0 )
                  v135 = (int *)(*(_QWORD *)v131 + *(_DWORD *)(v131 + 16) * v134);
                else
                  v135 = 0;
                v136 = v130;
                while ( v133 > 0 )
                {
                  v137 = *v135;
                  *((_DWORD *)this + 15) += v133;
                  v138 = *((_DWORD *)this + 15);
                  if ( v138 < v137 )
                    goto LABEL_257;
                  v139 = *((_QWORD *)this + 6);
                  v140 = v134++;
                  *((_DWORD *)this + 14) = v134;
                  if ( v134 >= *(_DWORD *)(v139 + 8) )
                  {
                    *((_DWORD *)this + 14) = v140;
                    *((_DWORD *)this + 15) = v137;
                    goto LABEL_257;
                  }
                  v133 = v138 - v137;
                  *((_DWORD *)this + 15) = 0;
                  v135 = (int *)((char *)v135 + *(int *)(v139 + 16));
                }
LABEL_255:
                if ( v136 )
                {
                  v130 = v136;
                  goto LABEL_257;
                }
LABEL_269:
                if ( (v113 & 2) != 0 )
                {
                  *((_BYTE *)this + 100) = 0;
                  if ( v77 != 9 )
                  {
                    v149 = *((_DWORD *)this + 8);
                    WordBreak = CTxtPtr::FindWordBreak((CMeasurer *)((char *)this + 16), 6, *((_DWORD *)this + 20) + 1);
                    if ( !WordBreak )
                      goto LABEL_284;
                    v151 = *((_QWORD *)this + 6);
                    if ( !v151 )
                      goto LABEL_285;
                    v152 = *(_DWORD *)(v151 + 8);
                    if ( !v152 )
                      goto LABEL_285;
                    v153 = WordBreak;
                    if ( WordBreak < 0 )
                    {
                      while ( v153 < 0 )
                      {
                        v287 = *((_DWORD *)this + 15);
                        if ( -v153 <= v287 )
                        {
                          *((_DWORD *)this + 15) = v153 + v287;
                          goto LABEL_285;
                        }
                        v288 = *((_DWORD *)this + 14);
                        if ( v288 <= 0 )
                        {
                          *((_QWORD *)this + 7) = 0;
                          goto LABEL_285;
                        }
                        v153 += v287;
                        v289 = v288 - 1;
                        *((_DWORD *)this + 14) = v289;
                        v290 = *(_DWORD *)(v151 + 8);
                        if ( v290 > 0 && v289 < v290 && *(_QWORD *)v151 && v289 >= 0 )
                          v291 = (_DWORD *)(*(_QWORD *)v151 + *(_DWORD *)(v151 + 16) * v289);
                        else
                          v291 = 0;
                        *((_DWORD *)this + 15) = *v291;
                      }
                      goto LABEL_285;
                    }
                    v154 = *((_DWORD *)this + 14);
                    if ( v152 > 0 && v154 < v152 && *(_QWORD *)v151 && v154 >= 0 )
                      v155 = (int *)(*(_QWORD *)v151 + *(_DWORD *)(v151 + 16) * v154);
                    else
                      v155 = 0;
                    while ( v153 > 0 )
                    {
                      v156 = *v155;
                      *((_DWORD *)this + 15) += v153;
                      v157 = *((_DWORD *)this + 15);
                      if ( v157 < v156 )
                        goto LABEL_285;
                      v158 = *((_QWORD *)this + 6);
                      v159 = v154++;
                      *((_DWORD *)this + 14) = v154;
                      if ( v154 >= *(_DWORD *)(v158 + 8) )
                      {
                        *((_DWORD *)this + 14) = v159;
                        *((_DWORD *)this + 15) = v156;
                        goto LABEL_285;
                      }
                      v153 = v157 - v156;
                      *((_DWORD *)this + 15) = 0;
                      v155 = (int *)((char *)v155 + *(int *)(v158 + 16));
                    }
LABEL_284:
                    if ( WordBreak )
                    {
LABEL_285:
                      v160 = *((_QWORD *)this + 8);
                      v161 = WordBreak;
                      if ( v160 )
                      {
                        v162 = *(_DWORD *)(v160 + 8);
                        if ( v162 )
                        {
                          if ( WordBreak < 0 )
                          {
                            while ( v161 < 0 )
                            {
                              v292 = *((_DWORD *)this + 19);
                              if ( -v161 <= v292 )
                              {
                                *((_DWORD *)this + 19) = v161 + v292;
                                break;
                              }
                              v293 = *((_DWORD *)this + 18);
                              if ( v293 <= 0 )
                              {
                                *((_QWORD *)this + 9) = 0;
                                break;
                              }
                              v161 += v292;
                              v294 = v293 - 1;
                              *((_DWORD *)this + 18) = v294;
                              v295 = *(_DWORD *)(v160 + 8);
                              if ( v295 > 0 && v294 < v295 && *(_QWORD *)v160 && v294 >= 0 )
                                v296 = (_DWORD *)(*(_QWORD *)v160 + *(_DWORD *)(v160 + 16) * v294);
                              else
                                v296 = 0;
                              *((_DWORD *)this + 19) = *v296;
                            }
                          }
                          else
                          {
                            v163 = *((_DWORD *)this + 18);
                            if ( v162 > 0 && v163 < v162 && *(_QWORD *)v160 && v163 >= 0 )
                              v164 = (int *)(*(_QWORD *)v160 + *(_DWORD *)(v160 + 16) * v163);
                            else
                              v164 = 0;
                            while ( v161 > 0 )
                            {
                              v165 = *v164;
                              *((_DWORD *)this + 19) += v161;
                              v166 = *((_DWORD *)this + 19);
                              if ( v166 < v165 )
                                break;
                              v167 = *((_QWORD *)this + 8);
                              v168 = v163++;
                              *((_DWORD *)this + 18) = v163;
                              if ( v163 >= *(_DWORD *)(v167 + 8) )
                              {
                                *((_DWORD *)this + 18) = v168;
                                *((_DWORD *)this + 19) = v165;
                                break;
                              }
                              v161 = v166 - v165;
                              *((_DWORD *)this + 19) = 0;
                              v164 = (int *)((char *)v164 + *(int *)(v167 + 16));
                            }
                          }
                        }
                      }
                    }
                    v169 = -WordBreak;
                    if ( v169 || !v394 )
                    {
                      v170 = *((_DWORD *)this + 20);
                      if ( v169 + 1 < v170 )
                      {
                        PrevChar = CTxtPtr::GetPrevChar((CMeasurer *)((char *)this + 16));
                        if ( PrevChar == 9 )
                        {
                          v169 = v257;
                          CRchTxtPtr::Advance(this, -1);
                        }
                        else if ( PrevChar == 173 )
                        {
                          *((_DWORD *)this + 22) += v395;
                        }
                        *((_DWORD *)this + 20) -= v169;
                      }
                      else
                      {
                        if ( v169 == v170 && v169 > 1 && CTxtPtr::GetChar((CMeasurer *)((char *)this + 16)) == 32 )
                        {
                          CRchTxtPtr::Advance(this, 1);
                          *((_DWORD *)this + 20) = 1;
                          goto LABEL_363;
                        }
                        v171 = *((_DWORD *)this + 8);
                        v172 = v149 - v171;
                        if ( v149 != v171 )
                        {
                          v173 = *((_QWORD *)this + 2);
                          if ( v173 )
                          {
                            v174 = *(_DWORD *)(v173 + 8);
                            if ( v174 )
                            {
                              if ( v149 < v171 / 2 )
                              {
                                *((_QWORD *)this + 3) = 0;
                                v356 = 0;
                                if ( v149 > 0 )
                                  v356 = v149;
                                v181 = CRunPtrBase::AdvanceCp((CMeasurer *)((char *)this + 16), v356);
                                *((_DWORD *)this + 8) = v181;
                              }
                              else
                              {
                                v175 = v149 - v171;
                                if ( v172 < 0 )
                                {
                                  while ( v175 < 0 )
                                  {
                                    v333 = *((_DWORD *)this + 7);
                                    v334 = v175 + v333;
                                    if ( -v175 <= v333 )
                                    {
                                      *((_DWORD *)this + 7) = v334;
LABEL_330:
                                      v175 = 0;
                                      break;
                                    }
                                    v335 = *((_DWORD *)this + 6);
                                    v175 = v334;
                                    if ( v335 <= 0 )
                                    {
                                      *((_QWORD *)this + 3) = 0;
                                      break;
                                    }
                                    v336 = v335 - 1;
                                    *((_DWORD *)this + 6) = v336;
                                    v337 = *(_DWORD *)(v173 + 8);
                                    if ( v337 > 0 && v336 < v337 && *(_QWORD *)v173 && v336 >= 0 )
                                      v338 = (_DWORD *)(*(_QWORD *)v173 + *(_DWORD *)(v173 + 16) * v336);
                                    else
                                      v338 = 0;
                                    *((_DWORD *)this + 7) = *v338;
                                  }
                                }
                                else
                                {
                                  v176 = *((_DWORD *)this + 6);
                                  if ( v174 > 0 && v176 < v174 && *(_QWORD *)v173 && v176 >= 0 )
                                    v177 = (int *)(*(_QWORD *)v173 + *(_DWORD *)(v173 + 16) * v176);
                                  else
                                    v177 = 0;
                                  while ( v175 > 0 )
                                  {
                                    v178 = *v177;
                                    *((_DWORD *)this + 7) += v175;
                                    v179 = *((_DWORD *)this + 7);
                                    if ( v179 < v178 )
                                      goto LABEL_330;
                                    v175 = v179 - v178;
                                    v180 = v176++;
                                    *((_DWORD *)this + 6) = v176;
                                    if ( v176 >= *(_DWORD *)(v173 + 8) )
                                    {
                                      *((_DWORD *)this + 6) = v180;
                                      *((_DWORD *)this + 7) = v178;
                                      break;
                                    }
                                    *((_DWORD *)this + 7) = 0;
                                    v177 = (int *)((char *)v177 + *(int *)(v173 + 16));
                                  }
                                }
                                *((_DWORD *)this + 8) += v172 - v175;
                                v181 = *((_DWORD *)this + 8);
                              }
                              v182 = v181 - v171;
                              if ( !v182 )
                              {
                                v188 = 0;
                                goto LABEL_347;
                              }
                              v183 = *((_QWORD *)this + 6);
                              if ( v183 && (v184 = *(_DWORD *)(v183 + 8)) != 0 )
                              {
                                v185 = v182;
                                if ( v182 < 0 )
                                {
                                  v188 = v182;
                                  while ( v185 < 0 )
                                  {
                                    v323 = *((_DWORD *)this + 15);
                                    if ( -v185 <= v323 )
                                    {
                                      *((_DWORD *)this + 15) = v185 + v323;
                                      break;
                                    }
                                    v324 = *((_DWORD *)this + 14);
                                    if ( v324 <= 0 )
                                    {
                                      *((_QWORD *)this + 7) = 0;
                                      break;
                                    }
                                    v185 += v323;
                                    v325 = v324 - 1;
                                    *((_DWORD *)this + 14) = v325;
                                    v326 = *(_DWORD *)(v183 + 8);
                                    if ( v326 > 0 && v325 < v326 && *(_QWORD *)v183 && v325 >= 0 )
                                      v327 = (_DWORD *)(*(_QWORD *)v183 + *(_DWORD *)(v183 + 16) * v325);
                                    else
                                      v327 = 0;
                                    *((_DWORD *)this + 15) = *v327;
                                  }
                                }
                                else
                                {
                                  v186 = *((_DWORD *)this + 14);
                                  if ( v184 > 0 && v186 < v184 && *(_QWORD *)v183 && v186 >= 0 )
                                    v187 = (int *)(*(_QWORD *)v183 + *(_DWORD *)(v183 + 16) * v186);
                                  else
                                    v187 = 0;
                                  v188 = v182;
                                  while ( v185 > 0 )
                                  {
                                    v189 = *v187;
                                    *((_DWORD *)this + 15) += v185;
                                    v190 = *((_DWORD *)this + 15);
                                    if ( v190 < v189 )
                                      goto LABEL_349;
                                    v191 = *((_QWORD *)this + 6);
                                    v192 = v186++;
                                    *((_DWORD *)this + 14) = v186;
                                    if ( v186 >= *(_DWORD *)(v191 + 8) )
                                    {
                                      *((_DWORD *)this + 14) = v192;
                                      *((_DWORD *)this + 15) = v189;
                                      goto LABEL_349;
                                    }
                                    v185 = v190 - v189;
                                    *((_DWORD *)this + 15) = 0;
                                    v187 = (int *)((char *)v187 + *(int *)(v191 + 16));
                                  }
LABEL_347:
                                  if ( !v188 )
                                    goto LABEL_363;
                                  v182 = v188;
                                }
                              }
                              else
                              {
                                v188 = v182;
                              }
LABEL_349:
                              v193 = *((_QWORD *)this + 8);
                              if ( v193 )
                              {
                                v194 = *(_DWORD *)(v193 + 8);
                                if ( v194 )
                                {
                                  if ( v188 < 0 )
                                  {
                                    while ( v182 < 0 )
                                    {
                                      v328 = *((_DWORD *)this + 19);
                                      if ( -v182 <= v328 )
                                      {
                                        v197 = v182 + v328;
LABEL_362:
                                        *((_DWORD *)this + 19) = v197;
                                        break;
                                      }
                                      v329 = *((_DWORD *)this + 18);
                                      if ( v329 <= 0 )
                                      {
                                        *((_QWORD *)this + 9) = 0;
                                        break;
                                      }
                                      v182 += v328;
                                      v330 = v329 - 1;
                                      *((_DWORD *)this + 18) = v330;
                                      v331 = *(_DWORD *)(v193 + 8);
                                      if ( v331 > 0 && v330 < v331 && *(_QWORD *)v193 && v330 >= 0 )
                                        v332 = (_DWORD *)(*(_QWORD *)v193 + *(_DWORD *)(v193 + 16) * v330);
                                      else
                                        v332 = 0;
                                      *((_DWORD *)this + 19) = *v332;
                                    }
                                  }
                                  else
                                  {
                                    v195 = *((_DWORD *)this + 18);
                                    if ( v194 > 0 && v195 < v194 && *(_QWORD *)v193 && v195 >= 0 )
                                      v196 = (int *)(*(_QWORD *)v193 + *(_DWORD *)(v193 + 16) * v195);
                                    else
                                      v196 = 0;
                                    while ( v182 > 0 )
                                    {
                                      v197 = *v196;
                                      *((_DWORD *)this + 19) += v182;
                                      v198 = *((_DWORD *)this + 19);
                                      if ( v198 < v197 )
                                        break;
                                      v199 = *((_QWORD *)this + 8);
                                      v200 = v195++;
                                      *((_DWORD *)this + 18) = v195;
                                      if ( v195 >= *(_DWORD *)(v199 + 8) )
                                      {
                                        *((_DWORD *)this + 18) = v200;
                                        goto LABEL_362;
                                      }
                                      v182 = v198 - v197;
                                      *((_DWORD *)this + 19) = 0;
                                      v196 = (int *)((char *)v196 + *(int *)(v199 + 16));
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
LABEL_363:
                      if ( *((_DWORD *)this + 8) >= v396 )
                        goto LABEL_423;
                      v201 = (CArrayBase *)*((_QWORD *)this + 2);
                      if ( v201 )
                      {
                        v202 = *((_DWORD *)v201 + 2);
                        if ( v202 )
                        {
                          if ( v202 > 0 && (v203 = *((_DWORD *)this + 6), v203 < v202) && *(_QWORD *)v201 && v203 >= 0 )
                            v204 = (_DWORD *)(*(_QWORD *)v201 + *((_DWORD *)v201 + 4) * v203);
                          else
                            v204 = 0;
                          if ( v204 )
                          {
                            v205 = *((_DWORD *)this + 7);
                            if ( v205 != *v204 )
                            {
LABEL_373:
                              v206 = v204[4];
                              v207 = (const WCHAR *)(*((_QWORD *)v204 + 1) + 2LL * v205);
                              if ( 2 * v205 >= v206 )
                              {
                                v207 += v204[5] / 2 - *v204;
                                if ( *v204 == v205 )
                                  v207 = 0;
                              }
                              else if ( v206 / 2 == v205 )
                              {
                                v207 = 0;
                              }
LABEL_379:
                              v209 = 0;
                              if ( (unsigned int)CTxtEdit::TxWordBreakProc(
                                                   v397,
                                                   v207,
                                                   0,
                                                   2,
                                                   2,
                                                   *((_DWORD *)this + 8),
                                                   -1) )
                              {
                                v209 = CTxtPtr::FindWordBreak((CMeasurer *)((char *)this + 16), 1, -1);
                                if ( !v209 )
                                  goto LABEL_393;
                                v210 = *((_QWORD *)this + 6);
                                if ( !v210 )
                                  goto LABEL_394;
                                v211 = *(_DWORD *)(v210 + 8);
                                if ( !v211 )
                                  goto LABEL_394;
                                v212 = v209;
                                if ( v209 < 0 )
                                {
                                  while ( v212 < 0 )
                                  {
                                    v307 = *((_DWORD *)this + 15);
                                    if ( -v212 <= v307 )
                                    {
                                      *((_DWORD *)this + 15) = v307 + v212;
                                      goto LABEL_394;
                                    }
                                    v308 = *((_DWORD *)this + 14);
                                    if ( v308 <= 0 )
                                    {
                                      *((_QWORD *)this + 7) = 0;
                                      goto LABEL_394;
                                    }
                                    v212 += v307;
                                    v309 = v308 - 1;
                                    *((_DWORD *)this + 14) = v309;
                                    v310 = *(_DWORD *)(v210 + 8);
                                    if ( v310 > 0 && v309 < v310 && *(_QWORD *)v210 && v309 >= 0 )
                                      v311 = (_DWORD *)(*(_QWORD *)v210 + *(_DWORD *)(v210 + 16) * v309);
                                    else
                                      v311 = 0;
                                    *((_DWORD *)this + 15) = *v311;
                                  }
                                  goto LABEL_394;
                                }
                                v213 = *((_DWORD *)this + 14);
                                if ( v211 > 0 && v213 < v211 && *(_QWORD *)v210 && v213 >= 0 )
                                  v214 = (int *)(*(_QWORD *)v210 + *(_DWORD *)(v210 + 16) * v213);
                                else
                                  v214 = 0;
                                while ( v212 > 0 )
                                {
                                  v215 = *v214;
                                  *((_DWORD *)this + 15) += v212;
                                  v216 = *((_DWORD *)this + 15);
                                  if ( v216 < v215 )
                                    goto LABEL_394;
                                  v217 = *((_QWORD *)this + 6);
                                  v218 = v213++;
                                  *((_DWORD *)this + 14) = v213;
                                  if ( v213 >= *(_DWORD *)(v217 + 8) )
                                  {
                                    *((_DWORD *)this + 14) = v218;
                                    *((_DWORD *)this + 15) = v215;
                                    goto LABEL_394;
                                  }
                                  v212 = v216 - v215;
                                  *((_DWORD *)this + 15) = 0;
                                  v214 = (int *)((char *)v214 + *(int *)(v217 + 16));
                                }
LABEL_393:
                                if ( v209 )
                                {
LABEL_394:
                                  v219 = *((_QWORD *)this + 8);
                                  v220 = v209;
                                  if ( v219 )
                                  {
                                    v221 = *(_DWORD *)(v219 + 8);
                                    if ( v221 )
                                    {
                                      if ( v209 < 0 )
                                      {
                                        while ( v220 < 0 )
                                        {
                                          v312 = *((_DWORD *)this + 19);
                                          if ( -v220 <= v312 )
                                          {
                                            v224 = v312 + v220;
LABEL_407:
                                            *((_DWORD *)this + 19) = v224;
                                            break;
                                          }
                                          v313 = *((_DWORD *)this + 18);
                                          if ( v313 <= 0 )
                                          {
                                            *((_QWORD *)this + 9) = 0;
                                            break;
                                          }
                                          v220 += v312;
                                          v314 = v313 - 1;
                                          *((_DWORD *)this + 18) = v314;
                                          v315 = *(_DWORD *)(v219 + 8);
                                          if ( v315 > 0 && v314 < v315 && *(_QWORD *)v219 && v314 >= 0 )
                                            v316 = (_DWORD *)(*(_QWORD *)v219 + *(_DWORD *)(v219 + 16) * v314);
                                          else
                                            v316 = 0;
                                          *((_DWORD *)this + 19) = *v316;
                                        }
                                      }
                                      else
                                      {
                                        v222 = *((_DWORD *)this + 18);
                                        if ( v221 > 0 && v222 < v221 && *(_QWORD *)v219 && v222 >= 0 )
                                          v223 = (int *)(*(_QWORD *)v219 + *(_DWORD *)(v219 + 16) * v222);
                                        else
                                          v223 = 0;
                                        while ( v220 > 0 )
                                        {
                                          v224 = *v223;
                                          *((_DWORD *)this + 19) += v220;
                                          v225 = *((_DWORD *)this + 19);
                                          if ( v225 < v224 )
                                            break;
                                          v226 = *((_QWORD *)this + 8);
                                          v227 = v222++;
                                          *((_DWORD *)this + 18) = v222;
                                          if ( v222 >= *(_DWORD *)(v226 + 8) )
                                          {
                                            *((_DWORD *)this + 18) = v227;
                                            goto LABEL_407;
                                          }
                                          v220 = v225 - v224;
                                          *((_DWORD *)this + 19) = 0;
                                          v223 = (int *)((char *)v223 + *(int *)(v226 + 16));
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                              *((_DWORD *)this + 20) += v209;
                              *((_WORD *)this + 49) = v209;
                              v228 = (CArrayBase *)*((_QWORD *)this + 2);
                              if ( !v228 )
                                goto LABEL_434;
                              v229 = *((_DWORD *)v228 + 2);
                              if ( !v229 )
                                goto LABEL_434;
                              if ( v229 > 0
                                && (v230 = *((_DWORD *)this + 6), v230 < v229)
                                && *(_QWORD *)v228
                                && v230 >= 0 )
                              {
                                v231 = (void *)(*(_QWORD *)v228 + *((_DWORD *)v228 + 4) * v230);
                              }
                              else
                              {
                                v231 = 0;
                              }
                              if ( !v231 )
                                goto LABEL_434;
                              v232 = *((_DWORD *)this + 7);
                              if ( v232 != *(_DWORD *)v231 )
                                goto LABEL_417;
                              v242 = *((_DWORD *)this + 6);
                              if ( v242 >= v229 - 1 )
                                goto LABEL_434;
                              v231 = CArrayBase::Elem(v228, v242 + 1);
                              if ( !v231 )
                                goto LABEL_434;
                              v232 = 0;
LABEL_417:
                              v233 = (unsigned __int16 *)(*((_QWORD *)v231 + 1) + 2LL * v232);
                              v234 = *((_DWORD *)v231 + 4);
                              if ( 2 * v232 >= v234 )
                              {
                                v235 = *(_DWORD *)v231;
                                v233 += *((_DWORD *)v231 + 5) / 2 - *(_DWORD *)v231;
                              }
                              else
                              {
                                v235 = v234 / 2;
                              }
                              if ( v235 != v232 && v233 )
                                v236 = *v233;
                              else
LABEL_434:
                                v236 = 0;
                              if ( (unsigned int)v236 - 10 <= 3 )
                              {
                                if ( v236 == 13 )
                                  *((_BYTE *)this + 101) |= 1u;
                                v241 = CRchTxtPtr::AdvanceCRLF(this);
                                *((_DWORD *)this + 20) += v241;
                                *((_BYTE *)this + 100) = v241;
                                goto LABEL_426;
                              }
LABEL_423:
                              v237 = v149 - *((_DWORD *)this + 8);
                              if ( v237 )
                              {
                                if ( v237 > 0 )
                                {
                                  v373 = v237 + *((unsigned __int16 *)this + 49);
                                  if ( v373 > 0 && v115 > 0 && v373 < v115 && v373 < 31 )
                                  {
                                    v374 = *((_DWORD *)this + 22);
                                    do
                                    {
                                      --v373;
                                      LOBYTE(v115) = (v115 - 1) & 0x1F;
                                      v374 -= (__int16)v404[4 * (unsigned __int8)v115];
                                    }
                                    while ( v373 > 0 );
                                    *((_DWORD *)this + 22) = v374;
                                    *((_WORD *)this + 48) = v404[4 * (((_BYTE)v115 - 1) & 0x1F) + 1];
                                    *((_WORD *)this + 46) = v404[4 * (((_BYTE)v115 - 1) & 0x1F) + 2];
                                    *((_WORD *)this + 47) = v404[4 * (((_BYTE)v115 - 1) & 0x1F) + 3];
                                    goto LABEL_426;
                                  }
                                }
                              }
                              else if ( !v388 )
                              {
                                *((_DWORD *)this + 22) = v391;
                                goto LABEL_426;
                              }
                              *((_DWORD *)this + 22) = -1;
                              v238 = -2;
                              goto LABEL_427;
                            }
                            v208 = *((_DWORD *)this + 6);
                            if ( v208 < v202 - 1 )
                            {
                              v204 = CArrayBase::Elem(v201, v208 + 1);
                              if ( v204 )
                              {
                                v205 = 0;
                                goto LABEL_373;
                              }
                            }
                          }
                        }
                      }
                      v207 = 0;
                      goto LABEL_379;
                    }
                  }
                }
LABEL_426:
                v238 = v379;
                goto LABEL_427;
              }
              v136 = v130;
              while ( v133 < 0 )
              {
                v297 = *((_DWORD *)this + 15);
                if ( -v133 <= v297 )
                {
                  *((_DWORD *)this + 15) = v297 + v133;
                  break;
                }
                v298 = *((_DWORD *)this + 14);
                if ( v298 <= 0 )
                {
                  *((_QWORD *)this + 7) = 0;
                  break;
                }
                v133 += v297;
                v299 = v298 - 1;
                *((_DWORD *)this + 14) = v299;
                v300 = *(_DWORD *)(v131 + 8);
                if ( v300 > 0 && v299 < v300 && *(_QWORD *)v131 && v299 >= 0 )
                  v301 = (_DWORD *)(*(_QWORD *)v131 + *(_DWORD *)(v131 + 16) * v299);
                else
                  v301 = 0;
                *((_DWORD *)this + 15) = *v301;
              }
            }
            else
            {
              v136 = v130;
            }
LABEL_257:
            v141 = *((_QWORD *)this + 8);
            if ( v141 )
            {
              v142 = *(_DWORD *)(v141 + 8);
              if ( v142 )
              {
                if ( v136 < 0 )
                {
                  while ( v130 < 0 )
                  {
                    v302 = *((_DWORD *)this + 19);
                    if ( -v130 <= v302 )
                    {
                      *((_DWORD *)this + 19) = v130 + v302;
                      goto LABEL_269;
                    }
                    v303 = *((_DWORD *)this + 18);
                    if ( v303 <= 0 )
                    {
                      *((_QWORD *)this + 9) = 0;
                      goto LABEL_269;
                    }
                    v130 += v302;
                    v304 = v303 - 1;
                    *((_DWORD *)this + 18) = v304;
                    v305 = *(_DWORD *)(v141 + 8);
                    if ( v305 > 0 && v304 < v305 && *(_QWORD *)v141 && v304 >= 0 )
                      v306 = (_DWORD *)(*(_QWORD *)v141 + *(_DWORD *)(v141 + 16) * v304);
                    else
                      v306 = 0;
                    *((_DWORD *)this + 19) = *v306;
                  }
                }
                else
                {
                  v143 = *((_DWORD *)this + 18);
                  if ( v142 > 0 && v143 < v142 && *(_QWORD *)v141 && v143 >= 0 )
                    v144 = (int *)(*(_QWORD *)v141 + *(_DWORD *)(v141 + 16) * v143);
                  else
                    v144 = 0;
                  while ( v130 > 0 )
                  {
                    v145 = *v144;
                    *((_DWORD *)this + 19) += v130;
                    v146 = *((_DWORD *)this + 19);
                    if ( v146 < v145 )
                      break;
                    v147 = *((_QWORD *)this + 8);
                    v148 = v143++;
                    *((_DWORD *)this + 18) = v143;
                    if ( v143 >= *(_DWORD *)(v147 + 8) )
                    {
                      *((_DWORD *)this + 18) = v148;
                      *((_DWORD *)this + 19) = v145;
                      goto LABEL_269;
                    }
                    v130 = v146 - v145;
                    *((_DWORD *)this + 19) = 0;
                    v144 = (int *)((char *)v144 + *(int *)(v147 + 16));
                  }
                }
              }
            }
            goto LABEL_269;
          }
          v108 = *(int *)(v78 + 16) & (unsigned __int64)(unsigned __int16)v77;
          Buffer = 0;
          v109 = *(_QWORD *)(v78 + 48);
          *(_WORD *)(v109 + 4 * v108 + 2) = 0;
          v110 = (_WORD *)(v109 + 4 * v108);
          v111 = v77;
          WideCharStr[0] = v77;
          if ( v106 != 42 && (unsigned __int16)v77 > 0x7Fu )
          {
LABEL_207:
            v386 = 0;
            ho = 0;
            h = 0;
            if ( v111 == 8364 )
            {
              if ( GetDeviceCaps(v105, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(hdc) )
              {
                v386 = 1;
                StockObject = GetStockObject(12);
                h = SelectObject(hdc, StockObject);
                memset_0(&v405, 0, sizeof(v405));
                CW32System::GetObjectW(h, 92, &v405);
                if ( CW32System::_dwPlatformId == 1 )
                  v405.lfOutPrecision = 7;
                else
                  v405.lfOutPrecision = 9;
                ho = CW32System::CreateFontIndirect(&v405);
                SelectObject(hdc, ho);
              }
              v111 = WideCharStr[0];
            }
            if ( CW32System::_dwPlatformId == 1
              && CW32System::_dwMajorVersion == 4
              && !CW32System::_dwMinorVersion
              && (unsigned int)v111 - 128 > 0x7F
              && (v106 == 950 || v106 == 936) )
            {
              GetCharWidthW(hdc, 0x4E00u, 0x4E00u, &Buffer);
              v110[1] = Buffer;
              if ( (unsigned int)WideCharStr[0] - 19968 > 0x51FF )
              {
                UsedDefaultChar = 0;
                v357 = WideCharToMultiByte(v106, 0, WideCharStr, 1, (LPSTR)MultiByteStr, 2, 0, &UsedDefaultChar);
                v358 = LOBYTE(MultiByteStr[0]);
                if ( v357 != 2 )
                {
                  if ( v357 > 0 )
                    goto LABEL_735;
                  goto LABEL_736;
                }
                v358 = _byteswap_ushort(MultiByteStr[0]);
LABEL_735:
                if ( !GetCharWidthA(hdc, v358, v358, &Buffer) )
                {
LABEL_736:
                  v111 = WideCharStr[0];
                  goto LABEL_209;
                }
LABEL_200:
                v110[1] = Buffer;
              }
            }
            else
            {
LABEL_209:
              if ( v111 == 0xFFFF )
              {
                v111 = -2;
                WideCharStr[0] = -2;
              }
              v112 = hdc;
              if ( GetCharWidthW(hdc, v111, v111, &Buffer) )
                v110[1] = Buffer;
              if ( v386 )
              {
                SelectObject(v112, h);
                DeleteObject(ho);
              }
            }
            v110[1] -= v107;
            *(_DWORD *)WideCharStr = (__int16)v110[1];
            v82 = *(_DWORD *)WideCharStr;
            Buffer = *(_DWORD *)WideCharStr;
            *v110 = v77;
            goto LABEL_202;
          }
          if ( !GetCharWidthA(v105, (unsigned __int16)v77, (unsigned __int16)v77, &Buffer) )
          {
            v111 = WideCharStr[0];
            v105 = hdc;
            goto LABEL_207;
          }
          goto LABEL_200;
        }
LABEL_148:
        v45 = v380;
      }
      v82 = *(_DWORD *)WideCharStr;
      goto LABEL_150;
    }
    break;
  }
  if ( v77 == 9 )
  {
    *((_BYTE *)this + 101) |= 4u;
    v82 = CMeasurer::MeasureTab(this, 9u);
    *(_DWORD *)WideCharStr = v82;
    goto LABEL_153;
  }
  v258 = v397;
  if ( v77 == 12 && (*((_DWORD *)v397 + 45) & 0x80000) != 0 )
  {
    CCcs::Include(*((CCcs **)this + 17), 0xCu, &Buffer);
    v82 = Buffer;
    *(_DWORD *)WideCharStr = Buffer;
    goto LABEL_153;
  }
  CRchTxtPtr::Advance(this, v384 - v45);
  v259 = CRchTxtPtr::AdvanceCRLF(this);
  *((_DWORD *)this + 20) += v259;
  *((_BYTE *)this + 100) = v259;
  if ( v77 == 13 || (*((_DWORD *)v258 + 45) & 0x80000) != 0 && v77 == 10 )
    *((_BYTE *)this + 101) |= 1u;
LABEL_466:
  v114 = WideCharStr[0];
  v238 = v379;
  if ( (v389 & 2) != 0 )
  {
    v260 = v391;
    *((_WORD *)this + 49) = *((_WORD *)this + 40) - v390;
    *((_DWORD *)this + 22) = v260;
  }
LABEL_427:
  v239 = *((_WORD *)this + 46) == 0;
  *((_WORD *)this + 76) = v114;
  if ( v239 )
    CMeasurer::CheckLineHeight(this);
  CMeasurer::AdjustLineHeight(this);
  return v238;
}

```

## disassembly

```asm
0x1800112c0  mov     [rsp-8+arg_18], rbx
0x1800112c5  push    rbp
0x1800112c6  push    rsi
0x1800112c7  push    rdi
0x1800112c8  push    r12
0x1800112ca  push    r13
0x1800112cc  push    r14
0x1800112ce  push    r15
0x1800112d0  lea     rbp, [rsp-150h]
0x1800112d8  sub     rsp, 250h
0x1800112df  mov     rax, cs:__security_cookie
0x1800112e6  xor     rax, rsp
0x1800112e9  mov     [rbp+180h+var_40], rax
0x1800112f0  mov     rax, [rcx+28h]
0x1800112f4  xor     r10d, r10d
0x1800112f7  mov     [rbp+180h+var_200], r9d
0x1800112fb  mov     esi, r8d
0x1800112fe  mov     [rsp+280h+var_234], r8d
0x180011303  mov     r12d, edx
0x180011306  mov     [rsp+280h+var_208], edx
0x18001130a  mov     rbx, rcx
0x18001130d  mov     [rbp+180h+var_1D8], rax
0x180011311  test    rax, rax
0x180011314  jz      loc_1800133C2
0x18001131a  mov     rax, [rcx+10h]
0x18001131e  mov     r14d, [rax+18h]
0x180011322  mov     rcx, [rcx+40h]
0x180011326  mov     edi, r9d
0x180011329  and     edi, 1
0x18001132c  mov     [rbp+180h+var_1DC], r14d
0x180011330  mov     [rbp+180h+var_1E4], r10d
0x180011334  mov     [rsp+280h+var_230], r10d
0x180011339  mov     dword ptr [rsp+280h+WideCharStr], r10d
0x18001133e  mov     [rbp+180h+var_1E0], r10d
0x180011342  mov     [rsp+280h+var_204], r10d
0x180011347  mov     dword ptr [rbp+180h+var_1A8], r10d
0x18001134b  test    rcx, rcx
0x18001134e  jz      loc_180011BAC
0x180011354  mov     edx, [rcx+8]
0x180011357  test    edx, edx
0x180011359  jz      loc_180011BAC
0x18001135f  jle     loc_1800133CA
0x180011365  mov     eax, [rbx+48h]
0x180011368  cmp     eax, edx
0x18001136a  jge     loc_1800133CA
0x180011370  mov     r8, [rcx]
0x180011373  test    r8, r8
0x180011376  jz      loc_1800133CA
0x18001137c  test    eax, eax
0x18001137e  js      loc_1800133CA
0x180011384  imul    eax, [rcx+10h]
0x180011388  movsxd  rdx, eax
0x18001138b  add     rdx, r8
0x18001138e  movzx   edx, word ptr [rdx+4]
0x180011392  mov     [rbp+180h+var_1D0], r10
0x180011396  test    dx, dx
0x180011399  jns     short loc_1800113A3
0x18001139b  mov     rax, [rbx+10h]
0x18001139f  movzx   edx, word ptr [rax+1Eh]
0x1800113a3  mov     rcx, cs:qword_1800A72C8
0x1800113aa  lea     r8, [rbp+180h+var_1D0]
0x1800113ae  movsx   edx, dx
0x1800113b1  mov     rax, [rcx]
0x1800113b4  mov     rax, [rax+20h]
0x1800113b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113bd  test    eax, eax
0x1800113bf  jns     loc_180011A8E
0x1800113c5  lea     rcx, ?g_defaultPF@@3VCParaFormat@@A; CParaFormat g_defaultPF
0x1800113cc  mov     [rbp+180h+var_1D0], rcx
0x1800113d0  mov     edx, [rbx+50h]
0x1800113d3  mov     r13d, 2000h
0x1800113d9  mov     [rbx+90h], rcx
0x1800113e0  mov     r15d, 4000h
0x1800113e6  test    edx, edx
0x1800113e8  jnz     loc_180012A0F
0x1800113ee  test    edi, edi
0x1800113f0  jnz     loc_180012A49
0x1800113f6  mov     rax, [rbx+28h]
0x1800113fa  mov     rdx, [rbx+90h]
0x180011401  test    byte ptr [rax+0B4h], 1
0x180011408  mov     edi, [rdx+4]
0x18001140b  jz      short loc_180011433
0x18001140d  movzx   ecx, byte ptr [rbx+65h]
0x180011411  mov     esi, [rdx+0Ch]
0x180011414  and     ecx, 10h
0x180011417  test    [rax+0B8h], r13w
0x18001141f  jnz     loc_18001368E
0x180011425  test    ecx, ecx
0x180011427  jnz     loc_1800122D1
0x18001142d  add     edi, esi
0x18001142f  mov     esi, [rsp+280h+var_234]
0x180011433  test    [rdx+2], r15w
0x180011438  jnz     loc_180013126
0x18001143e  test    edi, edi
0x180011440  jg      loc_180013126
0x180011446  xor     r15d, r15d
0x180011449  mov     edi, r15d
0x18001144c  mov     rcx, [rbx+78h]
0x180011450  mov     [rbx+54h], edi
0x180011453  test    r12d, r12d
0x180011456  jns     loc_1800128AB
0x18001145c  mov     rax, [rcx]
0x18001145f  mov     r12d, 5FFFh
0x180011465  mov     rax, [rax+80h]
0x18001146c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011471  test    eax, eax
0x180011473  jz      loc_180011529
0x180011479  mov     rcx, [rbx+78h]
0x18001147d  mov     rax, [rcx]
0x180011480  mov     rax, [rax+70h]
0x180011484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011489  test    eax, eax
0x18001148b  jz      short loc_1800114A1
0x18001148d  mov     rax, [rbx+28h]
0x180011491  test    byte ptr [rax+0B4h], 4
0x180011498  jnz     short loc_1800114A1
0x18001149a  mov     edi, 1
0x18001149f  jmp     short loc_1800114A4
0x1800114a1  mov     edi, r15d
0x1800114a4  mov     rcx, [rbx+78h]
0x1800114a8  mov     rax, [rcx]
0x1800114ab  mov     rax, [rax+98h]
0x1800114b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114b7  mov     rdx, [rbx+78h]
0x1800114bb  mov     r12d, eax
0x1800114be  mov     rax, [rbx+68h]
0x1800114c2  lea     rcx, [rdx+10h]
0x1800114c6  movsx   r9d, word ptr [rax+14h]
0x1800114cb  cmp     [rcx+14h], r9w
0x1800114d0  jnz     loc_1800136EF
0x1800114d6  movzx   eax, word ptr [rax+16h]
0x1800114da  cmp     [rcx+16h], ax
0x1800114de  jnz     loc_1800136EF
0x1800114e4  mov     rax, [rbx+90h]
0x1800114eb  mov     ecx, [rax+8]
0x1800114ee  test    ecx, ecx
0x1800114f0  lea     rax, [rbx+74h]
0x1800114f4  cmovle  ecx, r15d; nNumber
0x1800114f8  test    byte ptr [rbx+0A2h], 2
0x1800114ff  jnz     short loc_180011508
0x180011501  lea     rax, [rbx+84h]
0x180011508  mov     edx, [rax]; nNumerator
0x18001150a  test    r15b, r15b
0x18001150d  jnz     short loc_18001151F
0x18001150f  cmp     edx, 5A0h
0x180011515  jz      short loc_18001151F
0x180011517  test    ecx, ecx
0x180011519  jnz     loc_180012BE6
0x18001151f  sub     r12d, ecx
0x180011522  sub     r12d, edi
0x180011525  sub     r12d, [rbx+54h]
0x180011529  test    r12d, r12d
0x18001152c  mov     [rbp+180h+var_1E8], r15d
0x180011530  cmovle  r12d, r15d
0x180011534  mov     [rsp+280h+var_208], r12d
0x180011539  mov     eax, r14d
0x18001153c  sub     eax, [rbx+20h]
0x18001153f  test    esi, esi
0x180011541  jns     loc_180011B9F
0x180011547  mov     esi, eax
0x180011549  mov     r10d, [rbx+50h]
0x18001154d  mov     eax, [rbx+58h]
0x180011550  mov     [rbp+180h+var_1FC], r10d
0x180011554  mov     [rbp+180h+var_1F8], eax
0x180011557  mov     [rsp+280h+var_234], esi
0x18001155b  test    esi, esi
0x18001155d  jle     loc_180012981
0x180011563  mov     r11, [rbx+10h]
0x180011567  test    r11, r11
0x18001156a  jz      loc_180011604
0x180011570  mov     ecx, [r11+8]
0x180011574  test    ecx, ecx
0x180011576  jz      loc_180011604
0x18001157c  jle     loc_180013381
0x180011582  mov     eax, [rbx+18h]
0x180011585  cmp     eax, ecx
0x180011587  jge     loc_180013381
0x18001158d  mov     rcx, [r11]
0x180011590  test    rcx, rcx
0x180011593  jz      loc_180013381
0x180011599  test    eax, eax
0x18001159b  js      loc_180013381
0x1800115a1  imul    eax, [r11+10h]
0x1800115a6  movsxd  rdx, eax
0x1800115a9  add     rdx, rcx
0x1800115ac  mov     r9d, r15d
0x1800115af  test    rdx, rdx
0x1800115b2  jz      short loc_180011607
0x1800115b4  mov     r8d, [rbx+1Ch]
0x1800115b8  cmp     r8d, [rdx]
0x1800115bb  jz      loc_180012CA4
0x1800115c1  mov     rax, [rdx+8]
0x1800115c5  movsxd  rcx, r8d
0x1800115c8  lea     r10, [rax+rcx*2]
0x1800115cc  mov     ecx, [rdx+10h]
0x1800115cf  lea     eax, [r8+r8]
0x1800115d3  cmp     eax, ecx
0x1800115d5  jge     loc_1800128FF
0x1800115db  mov     eax, ecx
0x1800115dd  cdq
0x1800115de  sub     eax, edx
0x1800115e0  sar     eax, 1
0x1800115e2  mov     r9d, eax
0x1800115e5  sub     r9d, r8d
0x1800115e8  mov     r13, r15
0x1800115eb  test    r9d, r9d
0x1800115ee  cmovnz  r13, r10
0x1800115f2  mov     [rbp+180h+var_1F0], r13
0x1800115f6  cmp     r9d, esi
0x1800115f9  jl      short loc_18001160E
0x1800115fb  mov     r9d, esi
0x1800115fe  mov     [rbp+180h+var_1F0], r13
0x180011602  jmp     short loc_18001160E
0x180011604  mov     r9d, r15d
0x180011607  mov     r13, r15
0x18001160a  mov     [rbp+180h+var_1F0], r15
0x18001160e  mov     rax, [rbx+30h]
0x180011612  test    rax, rax
0x180011615  jz      loc_180011AA1
0x18001161b  mov     edx, [rax+8]
0x18001161e  test    edx, edx
0x180011620  jz      loc_180011AA1
0x180011626  jle     loc_1800133AB
0x18001162c  mov     ecx, [rbx+38h]
0x18001162f  cmp     ecx, edx
0x180011631  jge     loc_1800133AB
0x180011637  mov     r8, [rax]
0x18001163a  test    r8, r8
0x18001163d  jz      loc_1800133AB
0x180011643  test    ecx, ecx
0x180011645  js      loc_1800133AB
0x18001164b  imul    ecx, [rax+10h]
0x18001164f  movsxd  rdx, ecx
0x180011652  add     rdx, r8
0x180011655  mov     r14d, [rdx]
0x180011658  sub     r14d, [rbx+3Ch]
0x18001165c  cmp     r9d, r14d
0x18001165f  cmovl   r14d, r9d
0x180011663  mov     [rsp+280h+var_214], r14d
0x180011668  test    rax, rax
0x18001166b  jz      loc_180011A97
0x180011671  mov     edx, [rax+8]
0x180011674  test    edx, edx
0x180011676  jz      loc_180011A97
0x18001167c  jle     loc_1800133B3
0x180011682  mov     ecx, [rbx+38h]
0x180011685  cmp     ecx, edx
0x180011687  jge     loc_1800133B3
0x18001168d  mov     r8, [rax]
0x180011690  test    r8, r8
0x180011693  jz      loc_1800133B3
0x180011699  test    ecx, ecx
0x18001169b  js      loc_1800133B3
0x1800116a1  imul    ecx, [rax+10h]
0x1800116a5  movsxd  rdx, ecx
0x1800116a8  add     rdx, r8
0x1800116ab  movzx   edx, word ptr [rdx+4]
0x1800116af  mov     [rsp+280h+hdc], r15
0x1800116b4  test    dx, dx
0x1800116b7  jns     short loc_1800116BE
0x1800116b9  movzx   edx, word ptr [r11+1Ch]
0x1800116be  mov     rcx, cs:qword_1800A72D0
0x1800116c5  lea     r8, [rsp+280h+hdc]
0x1800116ca  movsx   edx, dx
0x1800116cd  mov     rax, [rcx]
0x1800116d0  mov     rax, [rax+20h]
0x1800116d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d9  test    eax, eax
0x1800116db  jns     loc_180011A7B
0x1800116e1  lea     rsi, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x1800116e8  mov     [rsp+280h+hdc], rsi
0x1800116ed  mov     r15d, [rsi]
0x1800116f0  mov     [rsp+280h+var_210], r15d
0x1800116f5  bt      r15d, 8
0x1800116fa  jb      loc_180012C8F
0x180011700  mov     rcx, [rbx+30h]
0x180011704  test    rcx, rcx
0x180011707  jz      loc_180011B92
0x18001170d  mov     edx, [rcx+8]
0x180011710  test    edx, edx
0x180011712  jz      loc_180011B92
0x180011718  jle     loc_1800133BB
0x18001171e  mov     eax, [rbx+38h]
0x180011721  cmp     eax, edx
0x180011723  jge     loc_1800133BB
0x180011729  mov     r8, [rcx]
0x18001172c  test    r8, r8
0x18001172f  jz      loc_1800133BB
0x180011735  test    eax, eax
0x180011737  js      loc_1800133BB
0x18001173d  imul    eax, [rcx+10h]
0x180011741  movsxd  rdx, eax
0x180011744  add     rdx, r8
0x180011747  movzx   edx, word ptr [rdx+4]
0x18001174b  mov     [rbp+180h+var_1C8], 0
0x180011753  test    dx, dx
0x180011756  jns     short loc_180011760
0x180011758  mov     rax, [rbx+10h]
0x18001175c  movzx   edx, word ptr [rax+1Ch]
0x180011760  mov     rcx, cs:qword_1800A72D0
  ... truncated ...
```
