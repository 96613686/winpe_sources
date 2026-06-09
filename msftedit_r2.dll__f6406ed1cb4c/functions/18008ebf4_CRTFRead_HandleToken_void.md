# CRTFRead::HandleToken(void)

- ea: `0x18008ebf4`
- end: `0x18009233b`
- name: `?HandleToken@CRTFRead@@AEAAHXZ`
- size: `14151`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `71`
- tags: ``

## callers

- `0x18008e1f8`

## callees

- `0x18000c138`
- `0x18000d3d8`
- `0x18000f430`
- `0x1800117e4`
- `0x18001b5d0`
- `0x18001ce7c`
- `0x18001ebd0`
- `0x18001f324`
- `0x18001f868`
- `0x18001fb5c`
- `0x1800201dc`
- `0x180020474`
- `0x180020bc4`
- `0x180021ac4`
- `0x1800237fc`
- `0x1800310b0`
- `0x180032444`
- `0x180032944`
- `0x180034728`
- `0x180038c24`
- `0x180053efc`
- `0x180055088`
- `0x180063170`
- `0x1800872a0`
- `0x18008a47c`
- `0x18008b170`
- `0x18008ceb8`
- `0x18008cf3c`
- `0x18008d90c`
- `0x18008ebf4`
- `0x180092344`
- `0x180092cb0`
- `0x180092ce4`
- `0x18009333c`
- `0x180098b78`
- `0x1800cd5e0`
- `0x1800ce3ec`
- `0x1800cf408`
- `0x1800d97c0`
- `0x1800e8120`
- `0x1800fb76c`
- `0x180106098`
- `0x18010825c`
- `0x180108908`
- `0x180108f88`
- `0x18010aa68`
- `0x180110104`
- `0x180117704`
- `0x18014e1e8`
- `0x180156d40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fc66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fc66`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800916e2`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800916e2`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180090eca`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180090eca`

## pseudocode

```c
__int64 __fastcall CRTFRead::HandleToken(CRTFRead *this)
{
  __int64 v2; // rsi
  _WORD *v3; // r10
  __int64 v4; // r8
  int v5; // ecx
  _WORD *v6; // r15
  struct STATE *v7; // rdx
  unsigned int v8; // ecx
  _DWORD *v9; // r9
  int v10; // r13d
  int v11; // edi
  char v12; // al
  int v13; // r11d
  int v14; // r14d
  bool v15; // zf
  __int64 result; // rax
  int v17; // edx
  _BYTE *v18; // rax
  __int64 v19; // rcx
  char v20; // r9
  __int16 v21; // dx
  char v22; // cl
  __int16 v23; // dx
  __int64 v24; // rax
  int v25; // eax
  __int16 v26; // cx
  __int16 v27; // dx
  __int64 v28; // rax
  int v29; // edx
  _BYTE *v30; // rax
  unsigned __int8 v31; // al
  __int64 v32; // r10
  unsigned __int16 v33; // ax
  _WORD *v34; // r10
  int v35; // edx
  _BYTE *v36; // rax
  _BYTE *v37; // r10
  int v38; // edx
  _WORD *v39; // rax
  int v40; // edx
  _BYTE *v41; // rax
  unsigned __int16 v42; // dx
  __int64 v43; // rdx
  __int64 v44; // rax
  unsigned int Color; // eax
  int v46; // edx
  __int16 v47; // r11
  int v48; // edx
  __int64 v49; // r10
  int v50; // eax
  int v51; // edx
  _WORD *v52; // rax
  __int64 v53; // r10
  __int64 v54; // rdx
  int v55; // edx
  _WORD *v56; // rax
  __int64 v57; // r10
  int v58; // r8d
  char *v59; // rax
  char *v60; // rdi
  const struct CCharFormat *CF; // rax
  __int64 v62; // rdx
  const unsigned __int16 *FontName; // rax
  int v64; // r8d
  unsigned __int16 *v65; // rdx
  unsigned __int16 v66; // cx
  unsigned __int16 *v67; // rcx
  int v68; // edx
  char v69; // cl
  __int64 v70; // rcx
  unsigned __int16 v71; // dx
  enum __MIDL___MIDL_itf_tom_0000_0000_0002 v72; // r8d
  __int64 v73; // rcx
  int v74; // r14d
  int v75; // edx
  __int64 v76; // rcx
  int v77; // eax
  CTxtEdit *v78; // rcx
  struct _textfont *TextFont; // rax
  unsigned __int8 v80; // al
  __int64 v81; // r10
  int v82; // edx
  unsigned int *v83; // r8
  struct _textfont *v84; // rax
  char v85; // r8
  CRTFRead *v86; // rcx
  void **p_Block; // rdx
  void *v88; // rdi
  int v89; // eax
  void *v90; // rcx
  CRTFRead *v91; // rcx
  void **v92; // rdx
  int v93; // edx
  char v94; // al
  unsigned __int8 StandardColorIndex; // al
  __int16 v96; // dx
  int v97; // ecx
  char v98; // al
  char v99; // al
  int v100; // r14d
  __int16 v101; // ax
  char v102; // al
  int v103; // edx
  _WORD *v104; // rax
  __int64 v105; // r10
  int v106; // r8d
  int v107; // edx
  __int64 v108; // rcx
  int v109; // eax
  char v110; // al
  unsigned int v111; // r8d
  int v112; // r8d
  int v113; // r8d
  char v114; // cl
  int v115; // eax
  int v116; // eax
  char v117; // r10
  unsigned __int8 v118; // cl
  int v119; // eax
  int v120; // edx
  char v121; // cl
  int CellColorIndex; // eax
  char v123; // r11
  unsigned int v124; // eax
  unsigned __int8 v125; // r9
  int v126; // eax
  char v127; // r9
  unsigned __int8 v128; // cl
  __int16 v129; // ax
  __int16 v130; // dx
  int v131; // r8d
  int v132; // edx
  int v133; // r10d
  _WORD *v134; // rax
  __int64 v135; // r10
  __int64 v136; // rdx
  char v137; // al
  int v138; // edx
  _WORD *v139; // rax
  __int64 v140; // r10
  int v141; // edx
  _WORD *v142; // rax
  __int64 v143; // r10
  int v144; // edx
  _BYTE *v145; // rax
  CArrayBase *v146; // rcx
  int v147; // r10d
  int v148; // edx
  _DWORD *v149; // rax
  int v150; // r10d
  int i; // r11d
  _WORD *v152; // rax
  __int16 v153; // r11
  int v154; // eax
  _WORD *v155; // rax
  __int16 v156; // r10
  _WORD *v157; // r15
  __int64 v158; // rdx
  __int16 v159; // ax
  int v160; // ecx
  _WORD *v161; // rax
  int v162; // r8d
  __int16 v163; // cx
  int v164; // eax
  __int16 v165; // ax
  __int16 v166; // ax
  int v167; // edx
  CTxtRange *v168; // rcx
  bool v169; // dl
  int v170; // ecx
  int v171; // edx
  int v172; // ecx
  char v174; // r15
  int v175; // ecx
  struct CDocInfo *DocInfo; // rax
  struct CDocInfo *v177; // rdi
  void *v178; // rcx
  void *v179; // rcx
  __int64 v180; // rcx
  unsigned __int16 *v181; // rdx
  unsigned int v182; // r8d
  _BYTE *v183; // rax
  __int16 v184; // dx
  __int16 v185; // r8
  _WORD *v186; // rax
  __int16 v187; // ax
  __int64 v188; // r11
  __int16 *v189; // rax
  __int16 v190; // ax
  __int64 v191; // r11
  __int64 v192; // rax
  int v193; // ecx
  CRTFRead *v194; // rcx
  _WORD *v195; // rax
  __int16 v196; // cx
  _QWORD **v197; // rdx
  int v198; // eax
  __int64 v199; // rcx
  char *v200; // r14
  int v201; // ecx
  int v202; // eax
  _WORD *v203; // rax
  int v204; // eax
  __int64 *v205; // rdi
  __int64 v206; // rax
  _QWORD *v207; // rsi
  int v208; // ecx
  __int64 v209; // rax
  __int16 v210; // dx
  __int16 v211; // r10
  char v212; // al
  char v213; // al
  char v214; // al
  struct CDocInfo *v215; // rax
  struct CDocInfo *v216; // rax
  struct CDocInfo *v217; // rdx
  int v218; // eax
  CTxtEdit *v219; // rcx
  int v220; // esi
  __int16 *v221; // r10
  __int64 v222; // r11
  int v223; // edx
  const struct CFontOptions *FontOptions; // rax
  __int64 v225; // r10
  CDocInfo *v226; // r11
  struct CDocInfo *v227; // rcx
  int v228; // edi
  int v229; // eax
  struct CDocInfo *v230; // rax
  struct CDocInfo *v231; // rax
  char v232; // cl
  char v233; // dl
  __int64 v234; // rax
  __int16 v235; // cx
  __int16 v236; // dx
  __int64 v237; // rax
  struct STATE *v238; // rdx
  CRTFRead *v239; // rcx
  __int64 v240; // rax
  struct STATE *v241; // rdx
  char v242; // cl
  char v243; // cl
  bool v244; // [rsp+20h] [rbp-49h]
  unsigned __int8 *v245; // [rsp+28h] [rbp-41h]
  __int64 v246; // [rsp+50h] [rbp-19h]
  __int64 v247; // [rsp+60h] [rbp-9h] BYREF
  __int64 v248; // [rsp+68h] [rbp-1h]
  char v249; // [rsp+D0h] [rbp+67h]
  void *Block; // [rsp+D8h] [rbp+6Fh] BYREF
  char *v251; // [rsp+E0h] [rbp+77h]
  __int64 v252; // [rsp+E8h] [rbp+7Fh]

  v2 = *((_QWORD *)this + 38);
  v3 = (_WORD *)((char *)this + 244);
  v252 = *(_QWORD *)(*((_QWORD *)this + 13) + 24LL);
  v251 = (char *)this + 244;
  v246 = v252 - 8;
  v4 = (v252 - 8) & -(__int64)(v252 != 0);
  if ( v2 )
  {
    v251 = (char *)this + 244;
  }
  else if ( *v3 != 261 )
  {
LABEL_16:
    result = 24;
    *((_DWORD *)this + 31) = 24;
    return result;
  }
  v5 = (unsigned __int16)*v3;
  LODWORD(Block) = v5;
  if ( (unsigned int)(v5 - 579) > 0x24 )
  {
    v6 = v3;
LABEL_5:
    v7 = (struct STATE *)(unsigned __int16)v5;
    v247 = (__int64)v6;
    v8 = v5 - 256;
    v249 = 0;
    v9 = (_DWORD *)((char *)this + 240);
    v10 = 2048;
    v11 = *((_DWORD *)this + 60);
    v12 = 4;
    v13 = 4096;
    v14 = 1;
    switch ( v8 )
    {
      case 0u:
      case 1u:
        if ( (*((_BYTE *)this + 1523) & 0x20) == 0 )
          goto LABEL_13;
        if ( !*(_WORD *)(v2 + 10) )
        {
          v183 = (_BYTE *)*((_QWORD *)this + 31);
          if ( *v183 == 32 && !v183[1] )
          {
            *v6 = *((_WORD *)this + 123);
            v249 = 1;
            goto LABEL_13;
          }
        }
        if ( *((_WORD *)this + 123) != 527 )
        {
LABEL_13:
          CRTFRead::HandleTextToken(this, (struct STATE *)v2);
          goto LABEL_14;
        }
LABEL_148:
        *((_DWORD *)this + 31) = 24;
        goto LABEL_14;
      case 2u:
        v15 = *((_WORD *)this + 123) == 527;
        goto LABEL_7;
      case 3u:
      case 4u:
      case 0x64u:
      case 0x7Au:
      case 0x8Bu:
      case 0x8Cu:
      case 0x99u:
      case 0x9Au:
      case 0x9Bu:
      case 0x9Cu:
      case 0x9Du:
      case 0x9Eu:
      case 0x9Fu:
      case 0xB4u:
      case 0x115u:
      case 0x12Eu:
      case 0x12Fu:
      case 0x136u:
      case 0x138u:
      case 0x139u:
      case 0x13Au:
      case 0x13Bu:
      case 0x16Cu:
      case 0x18Au:
      case 0x18Du:
      case 0x18Eu:
      case 0x18Fu:
      case 0x195u:
      case 0x198u:
      case 0x19Au:
      case 0x19Bu:
      case 0x19Cu:
      case 0x1A9u:
      case 0x1AAu:
      case 0x1ABu:
      case 0x1ACu:
      case 0x1AEu:
      case 0x1AFu:
      case 0x1B1u:
      case 0x1B3u:
      case 0x1B4u:
      case 0x1B6u:
      case 0x1B8u:
      case 0x1C7u:
      case 0x1CBu:
      case 0x1CCu:
      case 0x1CDu:
      case 0x1CEu:
      case 0x1CFu:
      case 0x1D0u:
      case 0x1D1u:
      case 0x1D2u:
      case 0x1D3u:
      case 0x1D4u:
      case 0x1D5u:
      case 0x1D6u:
      case 0x1D7u:
      case 0x1DBu:
      case 0x1DCu:
      case 0x1DDu:
      case 0x1DEu:
      case 0x1DFu:
      case 0x1E0u:
      case 0x1E1u:
      case 0x1E2u:
      case 0x1E3u:
      case 0x1E4u:
      case 0x1E5u:
        goto LABEL_14;
      case 5u:
        CRTFRead::HandleStartGroup(this);
        v21 = *((_WORD *)this + 760);
        if ( (v21 & 0x100) == 0 )
        {
          v249 = 1;
          goto LABEL_14;
        }
        v2 = *((_QWORD *)this + 38);
        *((_WORD *)this + 760) = v21 & 0xFEFF;
LABEL_84:
        if ( *(_QWORD *)(v2 + 32) )
          goto LABEL_16;
        *(_WORD *)(v2 + 10) = 0;
        if ( !*((_DWORD *)this + 2) && !CArrayBase::ArAdd(this, 1, 0) )
          goto LABEL_87;
        *((_WORD *)this + 762) = 0;
        v59 = (char *)CArrayBase::Elem(this, 0);
        *(_DWORD *)(v2 + 16) = 0;
        v60 = v59;
        CF = CRchTxtPtr::GetCF((CRchTxtPtr *)(*((_QWORD *)this + 13) + 8LL));
        v60[2] = *((_BYTE *)CF + 4);
        v60[3] = *((_BYTE *)CF + 5);
        *((_WORD *)v60 + 38) = CW32System::CodePageFromCharRep(*((_BYTE *)CF + 4));
        v60[78] = (*(_DWORD *)v62 & 0x80000) != 0;
        FontName = CFICache::GetFontName(*(_WORD *)(v62 + 6));
        v64 = 32;
        v65 = (unsigned __int16 *)(v60 + 6);
        while ( 1 )
        {
          v66 = *FontName;
          *v65 = *FontName;
          if ( !v66 )
            break;
          v67 = v65;
          ++FontName;
          ++v65;
          if ( !--v64 )
          {
            *v67 = 0;
            break;
          }
        }
        *((_WORD *)v60 + 34) = 0;
        *(_WORD *)v2 = 1;
        goto LABEL_14;
      case 6u:
        CRTFRead::HandleFieldEndGroup(this);
        CRTFRead::HandleEndGroup(this);
        v27 = *((_WORD *)this + 822);
        if ( (v27 & 0x100) == 0 )
          goto LABEL_14;
        v28 = *(_QWORD *)(v2 + 32);
        if ( !v28 || *(_WORD *)(v28 + 10) != 7 )
          goto LABEL_14;
        *((_WORD *)this + 822) = v27 & 0xFEFF;
        goto LABEL_8;
      case 7u:
        v203 = (_WORD *)*((_QWORD *)this + 193);
        if ( !v203 || *v203 == 11 )
        {
          *((_WORD *)this + 760) |= 1u;
        }
        else
        {
          v204 = CRTFRead::ObjectReadFromEditStream(this);
          *((_WORD *)this + 760) &= ~1u;
          *((_WORD *)this + 760) |= v204 != 0;
        }
        goto LABEL_647;
      case 8u:
        if ( !CRTFRead::StaticObjectReadFromEditStream(this, 0) && *((_DWORD *)this + 31) )
          goto LABEL_14;
LABEL_647:
        if ( !(unsigned int)CRTFRead::SkipToEndOfGroup(this) )
          goto LABEL_11;
        goto LABEL_14;
      case 9u:
        *((_WORD *)this + 61) = 0;
        *((_DWORD *)this + 30) |= 0xFDE90020;
        STATE::SetCodePage((STATE *)v2, 0xFDE9u);
        goto LABEL_84;
      case 0xAu:
        *((_DWORD *)this + 30) |= 0x800u;
        goto LABEL_84;
      case 0xBu:
        goto LABEL_84;
      case 0xCu:
        *((_BYTE *)this + 198) = 0;
        goto LABEL_14;
      case 0xDu:
        *((_WORD *)this + 760) |= 0x4000u;
        goto LABEL_14;
      case 0xEu:
        if ( (*((_BYTE *)this + 120) & 0x20) == 0 )
        {
          *((_WORD *)this + 768) = v11;
          STATE::SetCodePage((STATE *)v2, v11);
        }
        goto LABEL_14;
      case 0xFu:
        v77 = *((_DWORD *)this + 30);
        if ( (v77 & 0x8000) == 0 && (v77 & 0xFFFF0020) == 0xFDE90020 )
          CTxtEdit::SetViewKind(*((CTxtEdit **)this + 12), v11);
        goto LABEL_14;
      case 0x10u:
        if ( (*((_DWORD *)this + 30) & 0xA000) == 0x2000 )
        {
          v78 = (CTxtEdit *)*((_QWORD *)this + 12);
          if ( (*((_BYTE *)v78 + 276) & 0x40) == 0 )
            CTxtEdit::SetViewScale(v78, v11);
        }
        goto LABEL_14;
      case 0x11u:
        if ( v11 < 0 || (*((_BYTE *)this + 1520) & 0x40) != 0 )
          goto LABEL_14;
        if ( !*((_DWORD *)this + 2) && !CArrayBase::ArAdd(this, 1, 0) )
          goto LABEL_87;
        *((_WORD *)this + 762) = v11;
        v48 = 0;
        goto LABEL_107;
      case 0x12u:
        if ( v11 < 0 || *((_DWORD *)this + 2) != 1 )
          goto LABEL_14;
        if ( !CArrayBase::ArAdd(this, 1, 0) )
          goto LABEL_87;
        *((_WORD *)this + 763) = v11;
        v48 = 1;
LABEL_107:
        *(_WORD *)CArrayBase::Elem(this, v48) = v11;
        goto LABEL_14;
      case 0x13u:
        *((_WORD *)this + 764) = v11;
        goto LABEL_14;
      case 0x14u:
        *((_WORD *)this + 765) = v11;
        goto LABEL_14;
      case 0x15u:
        *((_WORD *)this + 766) = v11;
        goto LABEL_14;
      case 0x16u:
        if ( *(_WORD *)(v2 + 10) != 12 && *(_WORD *)(v2 + 10) != 24 )
          CRTFRead::Pard(this, (struct STATE *)v2);
        goto LABEL_14;
      case 0x17u:
        CRTFRead::SetPlain(this, v7);
        goto LABEL_14;
      case 0x18u:
        *((_WORD *)this + 822) |= 0x400u;
        goto LABEL_181;
      case 0x19u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 )
          *(_WORD *)(*((_QWORD *)this + 12) + 358LL) &= ~0x100u;
        goto LABEL_14;
      case 0x1Au:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 2);
        *(_DWORD *)(v2 + 16) = -1;
        goto LABEL_14;
      case 0x1Bu:
        if ( *(_WORD *)(v2 + 10) != 2 )
        {
          if ( *((_DWORD *)this + 2) && *(_WORD *)(v2 + 10) != 18 && v11 != -1 )
          {
            CRTFRead::SelectCurrentFont(this, v11, 0);
            v17 = *(_DWORD *)(v2 + 16);
            if ( v17 < 0 || v17 >= *((_DWORD *)this + 2) )
            {
              v19 = 1;
            }
            else
            {
              v18 = CArrayBase::Elem(this, v17);
              v19 = 1;
              if ( v18 )
              {
                if ( (unsigned int)CW32System::IsBiDiCharRep(v18[2]) )
                {
                  *((_BYTE *)this + 1617) = v20;
                  if ( *(_BYTE *)(v2 + 23) == 1 )
                    *(_BYTE *)(v2 + 23) = 2;
                  v19 = 2;
                }
                else
                {
                  v19 = 1;
                  if ( *(_BYTE *)(v2 + 23) == 2 && v20 == 11 )
                    *(_BYTE *)(v2 + 23) = 0;
                }
              }
            }
            *(_WORD *)(v2 + 4 * v19 + 62) = 0;
            *(_WORD *)(v2 + 4 * v19 + 60) = v11;
            *(_DWORD *)(v2 + 4) |= 0x10u;
          }
          goto LABEL_14;
        }
        if ( v11 == -1 )
          goto LABEL_8;
        if ( v11 == *((__int16 *)this + 762) )
        {
          *((_WORD *)this + 760) |= 0x20u;
          v14 = 0;
          v38 = 0;
        }
        else
        {
          v38 = 1;
          if ( v11 != *((__int16 *)this + 763) )
          {
            v39 = CArrayBase::ArAdd(this, 1, 0);
            if ( !v39 )
            {
LABEL_87:
              v43 = *((_QWORD *)this + 12) & -(__int64)(*(_WORD *)(*((_QWORD *)this + 12) + 56LL) != 0);
              v44 = v43 + 60;
              if ( !v43 )
                v44 = 12;
              *(_DWORD *)v44 |= 0x40u;
LABEL_90:
              *((_DWORD *)this + 31) = 9;
              goto LABEL_14;
            }
            v14 = *((_DWORD *)this + 2) - 1;
LABEL_72:
            *(_DWORD *)(v2 + 16) = v14;
            *v39 = v11;
            v39[3] = 0;
            v39[1] = 9;
            *((_DWORD *)v39 + 19) = 0xFFFF;
            goto LABEL_14;
          }
        }
        v39 = CArrayBase::Elem(this, v38);
        if ( !v39 )
          goto LABEL_209;
        goto LABEL_72;
      case 0x1Cu:
        *(_WORD *)(v2 + 4LL * *(char *)(v2 + 23) + 60) = v11;
        LOWORD(v11) = 0;
        goto LABEL_30;
      case 0x1Du:
LABEL_30:
        *(_WORD *)(v2 + 4LL * *(char *)(v2 + 23) + 62) = v11;
        goto LABEL_14;
      case 0x1Eu:
      case 0x1Fu:
      case 0x20u:
      case 0x21u:
      case 0x22u:
      case 0x23u:
      case 0x24u:
      case 0x25u:
        v35 = *(_DWORD *)(v2 + 16);
        if ( v35 >= 0 && v35 < *((_DWORD *)this + 2) )
        {
          v36 = CArrayBase::Elem(this, v35);
          if ( v36 )
          {
            v36[3] = v36[3] & 0xF | (16 * (*v37 + 2));
            if ( *(_WORD *)v37 == 292 && v36[2] == 9 )
              v36[2] = 10;
          }
        }
        goto LABEL_14;
      case 0x26u:
        v29 = *(_DWORD *)(v2 + 16);
        if ( v29 < 0 )
          goto LABEL_14;
        if ( v29 >= *((_DWORD *)this + 2) )
          goto LABEL_14;
        v30 = CArrayBase::Elem(this, v29);
        if ( !v30 )
          goto LABEL_14;
        v31 = v30[2];
        if ( v31 != 10 )
        {
          v31 = CW32System::CharRepFromCharSet(v11);
          *(_BYTE *)(v32 + 2) = v31;
        }
        v33 = CW32System::CodePageFromCharRep(v31);
        v34[38] = v33;
        if ( *(_WORD *)(v2 + 12) == 0xFDE9 )
        {
          v33 = -535;
        }
        else
        {
          *(_WORD *)(v2 + 12) = v33;
          if ( v33 == 42 )
            goto LABEL_56;
        }
        if ( *((_WORD *)this + 768) == 0xFFFF )
          *((_WORD *)this + 768) = v33;
LABEL_56:
        if ( (unsigned int)(unsigned __int8)v11 - 177 <= 1 )
        {
          if ( *((_WORD *)this + 763) == 0xFFFF )
            *((_WORD *)this + 763) = *v34;
          if ( !(unsigned int)CW32System::IsBiDiCharRep(*((_BYTE *)this + 1617)) )
            *((_BYTE *)this + 1617) = *(_BYTE *)(v49 + 2);
        }
        *((_WORD *)this + 760) |= 0x80u;
        if ( v11 )
          *((_BYTE *)this + 1523) |= 8u;
        goto LABEL_14;
      case 0x27u:
        v40 = *(_DWORD *)(v2 + 16);
        if ( v40 >= 0 && v40 < *((_DWORD *)this + 2) )
        {
          v41 = CArrayBase::Elem(this, v40);
          if ( v41 )
          {
            v41[3] &= 0xF0u;
            v41[3] |= v11;
          }
        }
        goto LABEL_14;
      case 0x28u:
        v58 = 13;
        goto LABEL_135;
      case 0x29u:
        STATE::SetCodePage((STATE *)v2, v11);
        if ( *(_WORD *)(v2 + 10) == 2 )
        {
          TextFont = CRTFRead::GetTextFont(this, *(_DWORD *)(v2 + 16));
          if ( TextFont )
          {
            *((_WORD *)TextFont + 38) = v11;
            v80 = CW32System::CharRepFromCodePage(v11);
            *(_BYTE *)(v81 + 2) = v80;
            if ( *((_WORD *)this + 768) == 0xFFFF )
              *((_WORD *)this + 768) = v11;
          }
        }
        goto LABEL_14;
      case 0x2Au:
        goto LABEL_36;
      case 0x2Bu:
        *((_DWORD *)this + 83) |= 0x400000u;
        if ( (unsigned __int8)v11 <= 9u )
        {
          *((_BYTE *)this + 191) &= 0xF0u;
          *((_BYTE *)this + 191) |= v11;
        }
        goto LABEL_14;
      case 0x2Cu:
        *((_DWORD *)this + 81) |= 0x400000u;
        *((_WORD *)this + 72) = v11;
        goto LABEL_14;
      case 0x2Du:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 1);
        *((_WORD *)this + 760) &= ~8u;
        goto LABEL_14;
      case 0x2Eu:
      case 0x30u:
        *((_DWORD *)this + 37) = CRTFRead::GetColor(this, 0x4000000u);
        goto LABEL_14;
      case 0x2Fu:
        Color = CRTFRead::GetColor(this, 0x40000000u);
        goto LABEL_92;
      case 0x31u:
        *(_BYTE *)(v2 + 20) = v11;
        goto LABEL_228;
      case 0x32u:
        *(_BYTE *)(v2 + 21) = v11;
        goto LABEL_228;
      case 0x33u:
        *(_BYTE *)(v2 + 22) = v11;
LABEL_228:
        *((_WORD *)this + 760) |= 8u;
        goto LABEL_14;
      case 0x34u:
      case 0x35u:
      case 0x37u:
      case 0x38u:
      case 0x39u:
      case 0x3Bu:
      case 0x41u:
      case 0x42u:
        goto LABEL_97;
      case 0x36u:
        v94 = 1;
        goto LABEL_268;
      case 0x3Au:
      case 0x3Du:
      case 0x3Eu:
      case 0x3Fu:
      case 0x40u:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
        v3 = v251;
        v9 = (_DWORD *)((char *)this + 240);
        goto LABEL_97;
      case 0x3Cu:
        if ( *(_WORD *)(v2 + 10) != 12 )
          goto LABEL_97;
        goto LABEL_14;
      case 0x43u:
        v46 = 0x200000;
        *((_DWORD *)this + 82) = 0x200000;
        goto LABEL_98;
      case 0x44u:
        *((_DWORD *)this + 32) &= ~4u;
        *((_DWORD *)this + 81) |= 4u;
        goto LABEL_14;
      case 0x45u:
      case 0x46u:
      case 0x47u:
      case 0x48u:
      case 0x49u:
      case 0x4Au:
      case 0x4Bu:
      case 0x4Cu:
      case 0x4Du:
      case 0x4Eu:
      case 0x4Fu:
      case 0x50u:
      case 0x51u:
      case 0x52u:
      case 0x53u:
      case 0x54u:
      case 0x55u:
        v9 = (_DWORD *)((char *)this + 240);
        v94 = *(_BYTE *)v3 - 67;
        *v3 = 310;
LABEL_268:
        *((_BYTE *)this + 164) = v94;
        *((_DWORD *)this + 81) |= 0x800000u;
LABEL_97:
        v46 = 1 << (*v3 - 52);
        *((_DWORD *)this + 81) |= v46;
LABEL_98:
        *((_DWORD *)this + 32) &= ~v46;
        v47 = *((_WORD *)this + 760) & 0x1000;
        if ( !v47 || *v9 )
          *((_DWORD *)this + 32) |= v46;
        *((_BYTE *)this + 1659) |= *((_BYTE *)this + 128) & 3;
        if ( v47 && !*v9 )
          *((_BYTE *)this + 1659) &= ~(_BYTE)v46;
        goto LABEL_14;
      case 0x56u:
        StandardColorIndex = CRTFRead::GetStandardColorIndex(this);
        *((_BYTE *)this + 167) = StandardColorIndex;
        if ( StandardColorIndex > 1u )
          *((_DWORD *)this + 81) |= 0x800004u;
        goto LABEL_14;
      case 0x57u:
        v96 = -10;
        goto LABEL_281;
      case 0x58u:
        v96 = 10;
LABEL_281:
        if ( (*((_WORD *)this + 760) & 0x1000) == 0 )
          LOWORD(v11) = 6;
        *((_DWORD *)this + 81) |= 0x10000000u;
        *((_WORD *)this + 69) = v96 * v11;
        goto LABEL_14;
      case 0x59u:
        v97 = 0x10000;
        goto LABEL_287;
      case 0x5Au:
        v97 = 0;
        goto LABEL_287;
      case 0x5Bu:
        v97 = 0x20000;
LABEL_287:
        *((_DWORD *)this + 81) |= 0x30000u;
        *((_DWORD *)this + 32) &= 0xFFFCFFFF;
        *((_DWORD *)this + 32) |= v97;
        goto LABEL_14;
      case 0x5Cu:
        *((_DWORD *)this + 81) |= 0x40000u;
        *((_BYTE *)this + 165) = v11;
        CRTFRead::CheckNotifyLowFiRTF(this, 1);
        goto LABEL_14;
      case 0x5Du:
        *((_WORD *)this + 73) = v11;
        *((_DWORD *)this + 81) |= 0x200000u;
        if ( v11 )
          CTxtEdit::OnSetTypographyOptions(*((CTxtEdit **)this + 12), 1u, 1);
        goto LABEL_14;
      case 0x5Eu:
        *((_DWORD *)this + 81) |= 0x100000u;
        *((_WORD *)this + 81) = 10 * v11;
        goto LABEL_14;
      case 0x5Fu:
        v82 = *((_DWORD *)this + 81);
        v83 = (unsigned int *)((char *)this + 152);
        if ( (v82 & 0x2000000) == 0 || !CLangTagTable::IsValidIndex(*v83) )
        {
          *((_DWORD *)this + 81) = v82 | 0x2000000;
          *((_DWORD *)this + 38) = (unsigned __int16)v11;
          *(_DWORD *)(v2 + 56) = (unsigned __int16)v11;
          if ( (unsigned int)CW32System::IsBiDiLcid(*v83) )
          {
            *((_BYTE *)this + 1617) = CCharFormat::CharRepFromLang((CRTFRead *)((char *)this + 128));
            if ( *(_BYTE *)(v2 + 23) == 1 )
              *(_BYTE *)(v2 + 23) = 2;
            if ( *((_BYTE *)this + 1617) > 0x13u && (*((_DWORD *)this + 81) & 0x20000000) != 0 )
            {
              v84 = CRTFRead::GetTextFont(this, *(_DWORD *)(v2 + 16));
              if ( v84 )
                *((_BYTE *)v84 + 2) = v85;
            }
          }
        }
        goto LABEL_14;
      case 0x60u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 38);
        *((_DWORD *)this + 81) &= 0x2000000u;
        goto LABEL_14;
      case 0x61u:
        v15 = *(_WORD *)(v2 + 10) == 18;
LABEL_7:
        if ( v15 )
          goto LABEL_8;
        goto LABEL_14;
      case 0x62u:
        if ( (unsigned int)v11 <= 0xFF )
        {
          *((_DWORD *)this + 83) |= 0x2000000u;
          *((_BYTE *)this + 189) = v11;
        }
        goto LABEL_14;
      case 0x63u:
        if ( v252 )
          v70 = *(_QWORD *)(v246 + 48);
        else
          v70 = 0;
        if ( (*(_BYTE *)(v70 + 358) & 0x40) == 0 || *(_BYTE *)(v2 + 84) == 2 )
          goto LABEL_14;
        *(_BYTE *)(v2 + 84) = 2;
        v71 = -558;
        *(_BYTE *)(v2 + 86) = 0;
        v72 = tomHorzVert;
        goto LABEL_238;
      case 0x65u:
        if ( v252 )
          v73 = *(_QWORD *)(v246 + 48);
        else
          v73 = 0;
        if ( (*(_BYTE *)(v73 + 358) & 0x40) != 0 )
        {
          *(_BYTE *)(v2 + 84) = 5;
          *(_BYTE *)(v2 + 86) = 0;
          ++*((_BYTE *)this + 201);
          CRTFRead::StoreDestination(this, (struct STATE *)v2, 39);
          *((_BYTE *)this + 1647) = v11;
          *(_DWORD *)((char *)this + 1650) = 9645;
        }
        goto LABEL_14;
      case 0x66u:
        *((_WORD *)this + 825) = v11;
        goto LABEL_14;
      case 0x67u:
        *((_WORD *)this + 826) = v11;
        goto LABEL_14;
      case 0x68u:
        if ( !*(_QWORD *)(v2 + 32) )
          goto LABEL_14;
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 40);
        v71 = -555;
        v72 = *(unsigned __int8 *)(*(_QWORD *)(v2 + 32) + 84LL);
LABEL_238:
        CRTFRead::DelimitILSObject(this, v71, v72, 0);
        goto LABEL_14;
      case 0x69u:
        *((_DWORD *)this + 83) |= 0x20000000u;
        if ( v11 <= 255 )
          LOBYTE(v14) = v11;
        *((_BYTE *)this + 184) = v14;
        goto LABEL_14;
      case 0x6Au:
      case 0x6Bu:
      case 0x6Cu:
        *((_DWORD *)this + 83) |= 0x20000000u;
        *((_BYTE *)this + 184) = *(_BYTE *)v3 - 106;
        goto LABEL_14;
      case 0x6Du:
        v98 = *(_BYTE *)v9;
        *((_DWORD *)this + 83) |= 0x40000000u;
        *((_BYTE *)this + 186) = v98;
        goto LABEL_14;
      case 0x6Eu:
        v99 = *(_BYTE *)v9;
        *((_DWORD *)this + 83) |= 0x80000000;
        *((_BYTE *)this + 185) = v99;
        goto LABEL_14;
      case 0x6Fu:
      case 0x70u:
      case 0x71u:
        *((_DWORD *)this + 83) |= 0x10000000u;
        *((_BYTE *)this + 187) = (_BYTE)v7 - 111;
        goto LABEL_14;
      case 0x72u:
      case 0x73u:
      case 0x74u:
      case 0x75u:
      case 0x76u:
      case 0x77u:
      case 0x79u:
      case 0x7Bu:
        goto LABEL_296;
      case 0x78u:
        if ( (*((_WORD *)this + 760) & 0x1000) != 0 )
        {
LABEL_296:
          if ( *(_WORD *)(v2 + 10) != 18 )
          {
            v100 = 1 << ((_BYTE)v7 - 114);
            *((_DWORD *)this + 83) |= v100;
            v101 = *((_WORD *)this + 90) & ~(_WORD)v100;
            *((_WORD *)this + 90) = v101;
            if ( (*((_WORD *)this + 760) & 0x1000) == 0 || v11 )
              *((_WORD *)this + 90) = v100 | v101;
          }
        }
        goto LABEL_14;
      case 0x7Cu:
        goto LABEL_523;
      case 0x7Du:
        if ( (*((_BYTE *)this + 203) & 1) != 0 )
        {
          if ( *((_BYTE *)this + 1658) )
          {
            v42 = 64;
LABEL_82:
            CRTFRead::HandleChar(this, v42);
            goto LABEL_14;
          }
          *((_WORD *)this + 822) |= 0x10u;
        }
        else if ( *(_WORD *)(v2 + 10) != 18 )
        {
          v42 = 11;
          goto LABEL_82;
        }
LABEL_14:
        result = *((unsigned int *)this + 31);
        *((_BYTE *)this + 1523) ^= (*((_BYTE *)this + 1523) ^ (32 * v249)) & 0x20;
        return result;
      case 0x7Eu:
        *((_DWORD *)this + 85) += v11 + *((_DWORD *)this + 87);
        *((_DWORD *)this + 101) |= 5u;
        *((_DWORD *)this + 87) = -v11;
        goto LABEL_14;
      case 0x7Fu:
      case 0x80u:
        v112 = *((_DWORD *)this + 101);
        if ( ((_WORD)v7 == 383) == ((*((_DWORD *)this + 84) & 0x1001) == 1) )
        {
          *((_DWORD *)this + 86) = v11;
          v113 = v112 | 2;
        }
        else
        {
          *((_DWORD *)this + 85) = v11 - *((_DWORD *)this + 87);
          v113 = v112 | 1;
        }
        *((_DWORD *)this + 101) = v113;
        goto LABEL_14;
      case 0x81u:
      case 0x82u:
      case 0x83u:
      case 0x84u:
      case 0x85u:
      case 0x86u:
        v114 = *((_BYTE *)this + 352) ^ (*(_BYTE *)v6 ^ *((_BYTE *)this + 352)) & 0xF;
        *((_DWORD *)this + 101) |= 8u;
        *((_BYTE *)this + 352) = v114;
        goto LABEL_14;
      case 0x87u:
        *((_DWORD *)this + 101) |= 0x40u;
        *((_DWORD *)this + 89) = v11;
        goto LABEL_14;
      case 0x88u:
        *((_DWORD *)this + 90) = v11;
        v50 = 128;
        goto LABEL_117;
      case 0x89u:
        v109 = -v11;
        if ( v11 > 0 )
          v109 = *((_DWORD *)this + 60);
        *((_DWORD *)this + 91) = v109;
        if ( !v11 || v11 == 1000 )
          v110 = 0;
        else
          v110 = (v11 <= 0) + 3;
        *((_BYTE *)this + 370) = v110;
        goto LABEL_116;
      case 0x8Au:
        if ( !v11 )
          goto LABEL_14;
        *((_BYTE *)this + 370) = 5;
        *((int *)this + 91) /= 12;
LABEL_116:
        v50 = 256;
LABEL_117:
        *((_DWORD *)this + 101) |= v50;
        goto LABEL_14;
      case 0x8Du:
        *((_WORD *)this + 135) = v11;
        if ( *(_WORD *)(v2 + 10) == 18 )
          goto LABEL_14;
        *((_BYTE *)this + 371) |= 1u;
        *((_WORD *)this + 184) = -1;
        v111 = 0;
        while ( v11 != *((unsigned __int8 *)this + v111 + 260) )
        {
          if ( (int)++v111 >= 10 )
            goto LABEL_338;
        }
        *((_BYTE *)this + 371) = 2 * v111 - 2;
        *((_WORD *)this + 184) = ~(_WORD)v111;
LABEL_338:
        *((_DWORD *)this + 101) |= 0xD7FFFDFF;
        goto LABEL_14;
      case 0x8Eu:
        *((_DWORD *)this + 84) &= ~1u;
        *((_DWORD *)this + 101) |= 0x10000u;
        goto LABEL_14;
      case 0x8Fu:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
        *((_DWORD *)this + 101) |= 0x4000000u;
        *((_DWORD *)this + 84) |= 0x400u;
        *((_BYTE *)this + 1616) = 0;
        goto LABEL_14;
      case 0x90u:
        v108 = *((_QWORD *)this + 12);
        v247 = 1;
        v248 = 0;
        CTxtEdit::OrCharFlags(v108, &v247, 0, (v252 - 8) & -(__int64)(v252 != 0));
        goto LABEL_165;
      case 0x91u:
      case 0x92u:
      case 0x93u:
      case 0x94u:
      case 0x95u:
      case 0x96u:
      case 0x97u:
      case 0x98u:
      case 0xA0u:
      case 0xA1u:
      case 0xA2u:
      case 0xA3u:
      case 0xA4u:
      case 0xA5u:
      case 0xA6u:
LABEL_165:
        v74 = 1 << (*v6 + 112);
        *((_DWORD *)this + 84) |= v74;
        *((_DWORD *)this + 101) |= v74 << 16;
        *((_DWORD *)this + 102) |= (unsigned __int16)v74;
        if ( (*(_BYTE *)(*((_QWORD *)this + 12) + 358LL) & 0x20) == 0 )
          *((_DWORD *)this + 102) &= 0xFFFFFFCF;
        goto LABEL_14;
      case 0xA7u:
      case 0xABu:
      case 0xACu:
      case 0xADu:
      case 0xAEu:
        goto LABEL_351;
      case 0xA8u:
      case 0xA9u:
      case 0xAAu:
        if ( (**((_BYTE **)&rgKeyword + 2 * *((__int16 *)this + 767)) | 0x20) != 0x74 )
          CRTFRead::CheckNotifyLowFiRTF(this, 0);
LABEL_351:
        *((_BYTE *)this + 1616) = *(_BYTE *)v6 + 89;
        goto LABEL_14;
      case 0xAFu:
        v124 = (unsigned int)CRTFRead::GetCellColorIndex(this) << 20;
        goto LABEL_361;
      case 0xB0u:
        v124 = (unsigned int)CRTFRead::GetCellColorIndex(this) << 25;
        goto LABEL_361;
      case 0xB1u:
        *((_DWORD *)this + 365) = v11 / 50;
        goto LABEL_14;
      case 0xB2u:
      case 0xB3u:
        v12 = *(_BYTE *)v6 + 79;
        goto LABEL_508;
      case 0xB5u:
        *((_BYTE *)this + 1618) |= 0x40u;
        goto LABEL_14;
      case 0xB6u:
      case 0xB7u:
      case 0xB8u:
        *((_DWORD *)this + 97) |= 1 << ((_BYTE)Block + 94);
        v115 = *((_DWORD *)this + 97);
        goto LABEL_347;
      case 0xB9u:
      case 0xBAu:
      case 0xBBu:
      case 0xBCu:
      case 0xBDu:
      case 0xBEu:
      case 0xBFu:
      case 0xC0u:
        v118 = *((_BYTE *)this + 1616);
        if ( v118 >= 4u )
          goto LABEL_14;
        v119 = (unsigned __int16)v7 - 441;
        v120 = 15;
        if ( v119 < 15 )
          v120 = v119;
        v121 = 4 * v118;
        if ( v120 <= 0 )
          LOWORD(v120) = 0;
        *((_WORD *)this + 193) = *((_WORD *)this + 193) & ~(15 << v121) | ((_WORD)v120 << v121);
        goto LABEL_153;
      case 0xC1u:
        if ( *((_BYTE *)this + 1616) < 4u )
        {
          v116 = CRTFRead::GetStandardColorIndex(this);
          v115 = *((_DWORD *)this + 97) & ~(31 << v117) | (v116 << v117);
          *((_DWORD *)this + 97) = v115;
LABEL_347:
          *((_DWORD *)this + 363) = v115;
        }
        else
        {
          CellColorIndex = CRTFRead::GetCellColorIndex(this);
          v124 = CellColorIndex << (5 * (*((_BYTE *)this + 1616) - v123));
LABEL_361:
          *((_DWORD *)this + 364) |= v124;
        }
        goto LABEL_14;
      case 0xC2u:
        v125 = *((_BYTE *)this + 1616);
        if ( v125 >= 4u )
        {
          v126 = CheckTwips(v11);
          *((_DWORD *)this + 400) |= v126 << (8 * v127 - 32);
        }
        else
        {
          if ( v11 > 0 )
          {
            v75 = (v11 + 3) / 5;
            if ( v75 >= 15 )
              v75 = 15;
          }
          else
          {
            v75 = 0;
          }
          if ( v75 <= 0 )
            LOWORD(v75) = 0;
          *((_WORD *)this + 192) = *((_WORD *)this + 192) & ~(15 << (4 * v125)) | ((_WORD)v75 << (4 * v125));
LABEL_153:
          *((_DWORD *)this + 101) |= 0x800u;
        }
        goto LABEL_14;
      case 0xC3u:
        v128 = *((_BYTE *)this + 1616);
        if ( v128 >= 4u )
          goto LABEL_14;
        if ( v11 < 300 )
          v68 = v11 / 20;
        else
          v68 = 15;
        v69 = 4 * v128;
        if ( v68 <= 0 )
          LOWORD(v68) = 0;
        *((_WORD *)this + 191) = *((_WORD *)this + 191) & ~(15 << v69) | ((_WORD)v68 << v69);
        goto LABEL_153;
      case 0xC4u:
        v129 = (unsigned __int16)CRTFRead::GetStandardColorIndex(this) << 11;
        v130 = 2047;
        goto LABEL_373;
      case 0xC5u:
        v129 = (unsigned __int16)CRTFRead::GetStandardColorIndex(this) << 6;
        v130 = -1985;
LABEL_373:
        *((_WORD *)this + 187) = v130 & *((_WORD *)this + 187) | v129;
        goto LABEL_370;
      case 0xC6u:
        *((_WORD *)this + 186) = v11;
        goto LABEL_370;
      case 0xC7u:
        if ( (*((_DWORD *)this + 30) & 0x8000) != 0 )
          goto LABEL_8;
        DocInfo = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
        v177 = DocInfo;
        if ( DocInfo )
        {
          v178 = (void *)*((_QWORD *)DocInfo + 11);
          if ( v178 )
          {
            CW32System::GlobalFree(v178);
            *((_QWORD *)v177 + 11) = 0;
          }
          v179 = (void *)*((_QWORD *)v177 + 12);
          if ( v179 )
          {
            DeleteObject(v179);
            *((_QWORD *)v177 + 12) = 0;
          }
          v180 = *((_QWORD *)v177 + 13);
          if ( v180 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v180 + 16LL))(v180);
            *((_QWORD *)v177 + 13) = 0;
          }
          *((_DWORD *)v177 + 32) = -9999999;
          *(_DWORD *)(v2 + 4) |= 4u;
        }
        goto LABEL_14;
      case 0xC8u:
      case 0xC9u:
      case 0xCAu:
      case 0xCBu:
      case 0xCCu:
      case 0xCDu:
      case 0xCEu:
      case 0xCFu:
      case 0xD0u:
      case 0xD1u:
      case 0xD2u:
      case 0xD3u:
        *((_WORD *)this + 187) &= 0xFFC0u;
        *((_WORD *)this + 187) |= (_WORD)v7 - 455;
LABEL_370:
        *((_DWORD *)this + 101) |= v13;
        goto LABEL_14;
      case 0xD4u:
        goto LABEL_302;
      case 0xD5u:
        *((_BYTE *)this + 1612) = 4;
LABEL_302:
        v102 = *((_BYTE *)this + 1523);
        if ( (v102 & 0x10) != 0 )
        {
          *((_WORD *)this + 822) |= 2u;
          *((_WORD *)this + 190) = v11;
          *((_BYTE *)this + 1523) = v102 & 0xEF;
          *((_DWORD *)this + 101) |= 0x4000u;
          if ( *(_WORD *)(v2 + 10) == 22 )
          {
            v103 = *((_DWORD *)this + 18);
            if ( v103 > 0 && *((_WORD *)this + 98) <= 8u )
            {
              v104 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v103 - 1);
              v104[5 * v105 + 7] = v11;
            }
          }
        }
        else
        {
          if ( (v102 & 4) != 0 && !*((_BYTE *)this + 199) )
            CRTFRead::DelimitRow(this, (unsigned __int16 *)&szRowStart);
          if ( *((int *)this + 103) < 32 && (unsigned int)v11 < 0x1000000 )
          {
            v106 = *((unsigned __int8 *)this + 1613);
            v107 = *((unsigned __int8 *)this + 1612);
            LOBYTE(Block) = *((_BYTE *)this + 412);
            if ( !(unsigned int)AddTabHelper(
                                  v11 & 0xFFFFFF,
                                  v107,
                                  v106,
                                  (int *)this + 109,
                                  252,
                                  (unsigned __int8 *)&Block) )
            {
              *((_DWORD *)this + 101) |= 0x10u;
              *((_DWORD *)this + 103) = (unsigned __int8)Block;
              if ( *((_BYTE *)this + 1612) || *((_BYTE *)this + 1613) )
                CTxtEdit::OnSetTypographyOptions(*((CTxtEdit **)this + 12), 1u, 1);
            }
          }
          *((_WORD *)this + 806) = 0;
          *((_DWORD *)this + 105) = 0;
        }
        goto LABEL_14;
      case 0xD6u:
        v6 = v3;
        goto LABEL_320;
      case 0xD7u:
      case 0xD8u:
      case 0xD9u:
      case 0xDAu:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
LABEL_320:
        *((_BYTE *)this + 1613) = *(_BYTE *)v6 + 43;
        goto LABEL_14;
      case 0xDBu:
      case 0xDCu:
      case 0xDDu:
        *((_BYTE *)this + 1612) = *(_BYTE *)v3 + 38;
        goto LABEL_14;
      case 0xDEu:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 11) )
          goto LABEL_14;
        *(_DWORD *)(v2 + 4) &= ~1u;
        *((_WORD *)this + 188) = 0;
        goto LABEL_432;
      case 0xDFu:
        if ( *(_WORD *)(v2 + 10) == 11 )
          *(_WORD *)(v2 + 8) = v11;
        goto LABEL_14;
      case 0xE0u:
        if ( *((int *)this + 395) >= 0 )
          *((_WORD *)this + 804) = 0;
        *v6 = 483;
        goto LABEL_446;
      case 0xE1u:
        CRTFRead::ContinueList(this);
        goto LABEL_14;
      case 0xE2u:
        if ( (unsigned int)(v11 - 1) <= 8 )
        {
          *((_WORD *)this + 804) &= 0xFB0Fu;
          *((_WORD *)this + 804) |= 16 * (v11 - 1);
        }
        goto LABEL_14;
      case 0xE3u:
      case 0xE4u:
        *((_WORD *)this + 804) &= 0xFFFCu;
        *((_WORD *)this + 804) |= (_WORD)v7 - 482;
        goto LABEL_14;
      case 0xE5u:
        *((_WORD *)this + 804) = 0;
        goto LABEL_446;
      case 0xE6u:
      case 0xE7u:
      case 0xE8u:
      case 0xE9u:
      case 0xEAu:
      case 0xEBu:
      case 0xECu:
      case 0xEDu:
      case 0xEEu:
      case 0xEFu:
      case 0xF0u:
      case 0xF1u:
      case 0xF2u:
      case 0xF3u:
      case 0xF4u:
      case 0xF5u:
      case 0xF6u:
      case 0xF7u:
      case 0xF8u:
      case 0xF9u:
      case 0xFAu:
      case 0xFBu:
        if ( *((_WORD *)this + 196) != 1 || (*(_BYTE *)(v2 + 4) & 1) == 0 )
        {
LABEL_446:
          if ( *(_WORD *)(v2 + 10) == 11 )
          {
            v166 = *((_WORD *)this + 122);
            *((_DWORD *)this + 101) |= 0x20u;
            *((_WORD *)this + 196) = v166 - 484;
            *(_DWORD *)(v2 + 4) |= 1u;
          }
        }
        goto LABEL_14;
      case 0xFCu:
        if ( (unsigned int)(*(__int16 *)(v2 + 10) - 8) <= 2
          && ((*(_BYTE *)(v2 + 4) & 0x20) == 0
           || !(unsigned int)CTxtPtr::IsAfterHardEOP((CTxtPtr *)(*((_QWORD *)this + 13) + 24LL))) )
        {
          goto LABEL_8;
        }
        *((_WORD *)this + 760) &= ~0x400u;
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 12) )
          goto LABEL_14;
        if ( *((char *)this + 1523) < 0 )
        {
          v167 = *((_DWORD *)this + 395);
          if ( v167 != -1 )
          {
            v168 = (CTxtRange *)*((_QWORD *)this + 13);
            if ( v167 < *((_DWORD *)v168 + 10) )
            {
              CTxtRange::SetCp(v168, v167, 1);
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, int, _DWORD))(**((_QWORD **)this + 13)
                                                                                                  + 888LL))(
                *((_QWORD *)this + 13),
                0,
                0,
                0,
                0,
                0,
                224,
                0);
            }
          }
        }
        *((_BYTE *)this + 1523) |= 0x80u;
LABEL_378:
        *((_DWORD *)this + 395) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        goto LABEL_14;
      case 0xFDu:
        if ( *(_WORD *)(v2 + 10) != 11 )
          goto LABEL_14;
        *((_WORD *)this + 188) = v11;
LABEL_432:
        *((_DWORD *)this + 101) |= 0x8000u;
        goto LABEL_14;
      case 0xFEu:
      case 0xFFu:
      case 0x129u:
      case 0x1E6u:
        goto LABEL_8;
      case 0x100u:
        goto LABEL_414;
      case 0x101u:
        v137 = *((_BYTE *)this + 1644);
        *((_BYTE *)this + 1523) &= ~0x10u;
        *((_BYTE *)this + 1523) |= ~(8 * v137) & 0x10;
        goto LABEL_14;
      case 0x102u:
        v51 = *((_DWORD *)this + 18);
        if ( v51 && (unsigned int)v11 <= 2 && *((_WORD *)this + 98) <= 8u )
        {
          v52 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v51 - 1);
          v54 = 5 * (v53 + 1);
          v52[v54] &= 0xFFFCu;
          v52[v54] |= v11;
        }
        goto LABEL_14;
      case 0x103u:
        v55 = *((_DWORD *)this + 18);
        if ( v55 && (unsigned int)v11 <= 0xFF && *((_WORD *)this + 98) <= 8u )
        {
          v56 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v55 - 1);
          if ( v11 < 5 )
          {
            LOWORD(v11) = *((unsigned __int8 *)&dword_1802B19E4 + v11);
          }
          else if ( v11 == 23 )
          {
            LOWORD(v11) = 1;
          }
          v56[5 * v57 + 4] = v11;
        }
        goto LABEL_14;
      case 0x104u:
        v141 = *((_DWORD *)this + 18);
        if ( v141 && *((_WORD *)this + 98) <= 8u )
        {
          v142 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v141 - 1);
          v142[5 * v143 + 6] = v11;
        }
        goto LABEL_14;
      case 0x105u:
        CArrayBase::ArAdd((CRTFRead *)((char *)this + 64), 1, 0);
        *((_WORD *)this + 98) = -1;
        goto LABEL_14;
      case 0x106u:
        v146 = (CRTFRead *)((char *)this + 64);
        v147 = *((_DWORD *)this + 18);
        if ( *(_WORD *)(v2 + 10) == 22 )
        {
          if ( v147 > 0 )
            *(_DWORD *)CArrayBase::Elem(v146, v147 - 1) = v11;
        }
        else
        {
          v148 = *((__int16 *)this + 754);
          if ( v148 >= v147 )
          {
            CArrayBase::Clear(v146, 2);
            goto LABEL_14;
          }
          if ( (v148 & 0x8000u) == 0 )
          {
            v149 = CArrayBase::Elem(v146, 0);
            for ( i = 0; ; ++i )
            {
              if ( i >= v150 )
                goto LABEL_408;
              if ( v11 == *v149 )
                break;
              v149 += 25;
            }
            v152 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), *((__int16 *)this + 754));
            v152[2] = v153;
LABEL_408:
            ++*((_WORD *)this + 754);
            goto LABEL_14;
          }
        }
        goto LABEL_14;
      case 0x107u:
        v132 = *((_DWORD *)this + 18);
        if ( v132 )
        {
          v133 = *((__int16 *)this + 98);
          if ( (unsigned int)(v133 + 1) <= 8 )
          {
            *((_WORD *)this + 98) = v133 + 1;
            v134 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v132 - 1);
            v136 = 5 * v135;
            *(_DWORD *)&v134[v136 + 10] = 0x10000;
            v134[v136 + 13] = -1;
          }
        }
        goto LABEL_14;
      case 0x108u:
        if ( !*((_DWORD *)this + 18) )
          goto LABEL_8;
        v131 = 25;
LABEL_375:
        if ( CRTFRead::StoreDestination(this, (struct STATE *)v2, v131) )
          goto LABEL_378;
        goto LABEL_14;
      case 0x109u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 23);
        *((_WORD *)this + 754) = 0;
        goto LABEL_14;
      case 0x10Au:
        v144 = *((_DWORD *)this + 18);
        if ( v144 )
        {
          v145 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v144 - 1);
          v145[6] |= 1u;
        }
        goto LABEL_14;
      case 0x10Bu:
        v58 = 22;
        goto LABEL_135;
      case 0x10Cu:
        v131 = 24;
        goto LABEL_375;
      case 0x10Du:
        if ( v11 < 1 )
          goto LABEL_14;
        if ( v11 > *((_DWORD *)this + 18) )
          goto LABEL_14;
        if ( *(_WORD *)(v2 + 10) == 23 )
          goto LABEL_14;
        *((_WORD *)this + 755) = *((_WORD *)this + 754);
        *((_WORD *)this + 754) = *((_WORD *)CArrayBase::Elem((CRTFRead *)((char *)this + 64), v11 - 1) + 2);
        if ( *((char *)this + 1523) < 0 )
          goto LABEL_14;
        v11 = 0;
        *((_WORD *)this + 804) = 0;
LABEL_414:
        if ( *((char *)this + 1523) >= 0 && (unsigned int)v11 <= 8 )
        {
          v154 = *((__int16 *)this + 754);
          if ( *((__int16 *)this + 754) >= 0 && v154 < *((_DWORD *)this + 18) )
          {
            *((_WORD *)this + 98) = v11;
            v155 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v154);
            v157 = v155;
            if ( (v155[3] & 2) != 0 )
            {
              *((_WORD *)this + 196) = v156;
            }
            else
            {
              v158 = 5LL * v11;
              v159 = v155[5 * v11 + 4];
              Block = (void *)v158;
              *((_WORD *)this + 196) = v159;
              if ( v159 == -4 )
              {
                *((_WORD *)this + 196) = 1;
                CRTFRead::CheckNotifyLowFiRTF(this, 0);
                v158 = (__int64)Block;
                v156 = 0;
              }
              *((_WORD *)this + 804) &= 0x400u;
              if ( *((_WORD *)this + 196) > 6u )
              {
                *((_WORD *)this + 196) = v156;
                *((_BYTE *)v157 + 6) |= 2u;
              }
              else
              {
                v160 = (__int16)v157[v158 + 7];
                v161 = (_WORD *)((char *)this + 380);
                v162 = *((_DWORD *)this + 85);
                if ( v160 > v162 && *v161 == v156 )
                {
                  v163 = v160 - v162;
                  *v161 = v163;
                  *((_DWORD *)this + 101) |= 0x4000u;
                  *(_WORD *)(v2 + 8) = v163;
                }
                else
                {
                  v164 = (unsigned __int16)*v161;
                  if ( v164 > v162 )
                    *(_WORD *)(v2 + 8) = v164 - *((_WORD *)this + 170);
                }
                *((_WORD *)this + 804) |= v157[v158 + 5] | (unsigned __int16)(16 * v11);
                v165 = v157[v158 + 6];
                *((_DWORD *)this + 101) |= 0xA020u;
                *((_WORD *)this + 188) = v165;
              }
            }
          }
        }
        goto LABEL_14;
      case 0x10Eu:
        v138 = *((_DWORD *)this + 18);
        if ( v138 && *((_WORD *)this + 98) <= 8u )
        {
          v139 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v138 - 1);
          v139[5 * v140 + 4] = -4;
        }
        goto LABEL_14;
      case 0x10Fu:
        v249 = *((_BYTE *)this + 1523) >> 5;
        goto LABEL_14;
      case 0x110u:
        if ( (unsigned __int16)(*(_WORD *)(v2 + 10) - 14) <= 2u )
          goto LABEL_8;
        v58 = 8;
        goto LABEL_135;
      case 0x111u:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 9) )
          goto LABEL_14;
        v181 = (unsigned __int16 *)&dword_1802B1A24;
        goto LABEL_544;
      case 0x112u:
        if ( (*((_BYTE *)this + 1523) & 0x20) != 0
          && !(unsigned int)CRTFRead::AddText(this, (unsigned __int16 *)&dword_1802B1A14, 2u, 0, 0, 0) )
        {
          *(_WORD *)(v2 + 10) = 10;
        }
        goto LABEL_14;
      case 0x113u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 18);
        *((_WORD *)this + 135) = 0;
        goto LABEL_14;
      case 0x114u:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
        if ( !*(_WORD *)(*(_QWORD *)(v2 + 40) + 56LL) )
        {
          *((_WORD *)this + 760) &= ~0x400u;
LABEL_523:
          CRTFRead::HandleEndOfPara(this);
        }
        goto LABEL_14;
      case 0x116u:
        v58 = 16;
        goto LABEL_135;
      case 0x117u:
        if ( *(_WORD *)(v2 + 10) > 0x1Cu )
          goto LABEL_209;
        v170 = 352326145;
        if ( !_bittest(&v170, *(__int16 *)(v2 + 10)) )
          goto LABEL_209;
        if ( !*((_DWORD *)this + 106) && !*((_BYTE *)this + 199) )
        {
          CRTFRead::DelimitRow(this, (unsigned __int16 *)&szRowStart);
          if ( *(_WORD *)(v2 + 10) == 24 || *(_WORD *)(v2 + 10) == 12 )
            *((_DWORD *)this + 395) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        }
        *((_BYTE *)this + 1523) &= ~4u;
        goto LABEL_14;
      case 0x118u:
        if ( (*((_BYTE *)this + 1523) & 4) != 0 && !*((_BYTE *)this + 199) )
          CRTFRead::DelimitRow(this, (unsigned __int16 *)&szRowStart);
        goto LABEL_472;
      case 0x119u:
LABEL_472:
        CRTFRead::HandleCell(this);
        goto LABEL_14;
      case 0x11Au:
        if ( (unsigned int)v11 > 0xFF )
          v11 = 108;
        *((_DWORD *)this + 104) = v11;
        goto LABEL_14;
      case 0x11Bu:
        CRTFRead::HandleCellx(this, v11);
        goto LABEL_14;
      case 0x11Cu:
        goto LABEL_495;
      case 0x11Du:
        *((_WORD *)this + 760) |= 0x800u;
LABEL_495:
        if ( *((_BYTE *)this + 199) )
        {
          while ( *((_DWORD *)this + 106) < *((_DWORD *)this + 105) && CRTFRead::HandleCell(this) )
            ;
          CRTFRead::DelimitRow(this, (unsigned __int16 *)&szRowEnd);
          if ( !*((_BYTE *)this + 199) )
          {
            if ( *((__int16 *)this + 805) >= 0 )
              (*(void (__fastcall **)(CTabsArray *))(*(_QWORD *)qword_1802E4598 + 8LL))(qword_1802E4598);
            *((_WORD *)this + 805) = -1;
          }
          if ( (*((_WORD *)this + 760) & 0x800) != 0 && !*((_BYTE *)this + 199) )
          {
            CRTFRead::InitializeTableRowParms(this);
            *((_DWORD *)this + 106) = 0;
          }
        }
        goto LABEL_14;
      case 0x11Eu:
        v171 = *(_DWORD *)(*((_QWORD *)this + 12) + 176LL);
        if ( (v171 & 0x10) != 0
          || *((char *)this + 201) + *((char *)this + 202)
          || *(_WORD *)(v2 + 10) == 12
          || *(_WORD *)(v2 + 10) == 24 )
        {
          goto LABEL_209;
        }
        if ( *((_WORD *)this + 123) == 527 )
          goto LABEL_8;
        v172 = *((_DWORD *)this + 394);
        if ( v172 == *(_DWORD *)(*((_QWORD *)this + 13) + 40LL)
          && *((_DWORD *)this + 80) != v172
          && !((v171 & 0x80000) != 0
             ? CRTFRead::HandleText(this, byte_1802A7E11, 1, (int)v9)
             : (unsigned int)CRTFRead::HandleChar(this, 0xDu)) )
        {
          *((_DWORD *)this + 80) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        }
        CRTFRead::InitializeTableRowParms(this);
        *((_BYTE *)this + 1523) |= 4u;
        *((_DWORD *)this + 109) = 0;
        goto LABEL_14;
      case 0x11Fu:
        *((_DWORD *)this + 401) = v11;
        goto LABEL_14;
      case 0x120u:
        *((_DWORD *)this + 362) = v11;
        goto LABEL_14;
      case 0x121u:
      case 0x122u:
        *((_BYTE *)this + 1622) = *(_BYTE *)v6 - 31;
        goto LABEL_14;
      case 0x123u:
        *((_BYTE *)this + 1618) |= 0x20u;
        goto LABEL_14;
      case 0x124u:
        v174 = 16;
        goto LABEL_511;
      case 0x125u:
LABEL_508:
        *((_BYTE *)this + 1618) |= v12;
        goto LABEL_14;
      case 0x126u:
        v174 = 8;
LABEL_511:
        *((_BYTE *)this + 1618) |= v174;
        goto LABEL_14;
      case 0x127u:
        if ( (*(_BYTE *)(v2 + 4) & 8) != 0 )
          goto LABEL_14;
        if ( !v11 )
          goto LABEL_124;
        if ( *(_WORD *)(v2 + 10) > 0x1Au )
          goto LABEL_16;
        v175 = 67109377;
        if ( !_bittest(&v175, *(__int16 *)(v2 + 10))
          || v11 > 127
          || (*(_DWORD *)(*((_QWORD *)this + 12) + 176LL) & 0x10) != 0 )
        {
          goto LABEL_16;
        }
        *((_WORD *)this + 735) = -1;
        *((_DWORD *)this + 105) = 0;
        while ( v11 > *((char *)this + 199) && (unsigned int)CRTFRead::DelimitRow(this, (unsigned __int16 *)&szRowStart) )
          ;
LABEL_124:
        *((_WORD *)this + 760) |= 0x800u;
        goto LABEL_14;
      case 0x128u:
        v58 = 26;
        goto LABEL_135;
      case 0x12Au:
        *((_BYTE *)this + 1523) |= 2u;
        goto LABEL_14;
      case 0x12Bu:
        CRTFRead::HandleUN(this, (struct STATE *)v2);
        goto LABEL_14;
      case 0x12Cu:
        if ( (unsigned int)v11 <= 2 )
          *(_WORD *)v2 = v11;
        goto LABEL_14;
      case 0x12Du:
        *((_WORD *)this + 822) |= 1u;
        goto LABEL_14;
      case 0x130u:
      case 0x131u:
      case 0x133u:
      case 0x134u:
        goto LABEL_32;
      case 0x132u:
        *(_DWORD *)(v2 + 4) ^= (*(_DWORD *)(v2 + 4) ^ (16 * *((unsigned __int8 *)this + 203))) & 0x10;
LABEL_32:
        v22 = *(_BYTE *)v3 - 47;
        *(_BYTE *)(v2 + 23) = v22;
        if ( (unsigned int)(v22 - 1) <= 1 )
        {
          v23 = *(_WORD *)(v2 + 4LL * v22 + 60);
          if ( v23 != -1 )
          {
            CRTFRead::SelectCurrentFont(this, v23, 0);
            CRTFRead::HandleNumber(this);
            v24 = *(char *)(v2 + 23);
            v11 = *(__int16 *)(v2 + 4 * v24 + 62);
            if ( *(_WORD *)(v2 + 4 * v24 + 62) )
            {
              v3 = v251;
LABEL_36:
              v25 = -v11;
              if ( v11 > 0 )
                v25 = v11;
              if ( v25 <= 10000 )
              {
                *(_WORD *)(v2 + 4LL * *(char *)(v2 + 23) + 62) = v11;
                *((_DWORD *)this + 81) |= 0x80000000;
                v26 = *((_WORD *)this + 822);
                *((_WORD *)this + 68) = 10 * v11;
                if ( (v26 & 8) != 0 && *v3 == 298 )
                {
                  *((_WORD *)this + 828) = 10 * v11;
                  *((_WORD *)this + 822) = v26 & 0xFFF7;
                }
              }
            }
          }
        }
        goto LABEL_14;
      case 0x135u:
        *((_BYTE *)this + 1522) = 1;
        goto LABEL_14;
      case 0x137u:
        *((_BYTE *)this + 1522) = 2;
LABEL_181:
        v76 = *((_QWORD *)this + 12);
        v247 = 1;
        v248 = 0;
        CTxtEdit::OrCharFlags(v76, &v247, 0, v4);
        goto LABEL_14;
      case 0x13Cu:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 14) )
          goto LABEL_14;
        v15 = (*((_DWORD *)this + 30) & 0x8000) == 0;
        p_Block = &Block;
        Block = 0;
        if ( !v15 )
          p_Block = 0;
        if ( !(unsigned int)CRTFRead::ReadRawText(v86, (char **)p_Block) )
          goto LABEL_251;
        v88 = Block;
        if ( !Block )
          goto LABEL_14;
        v89 = CTxtEdit::SetFollowingPunct(*((CTxtEdit **)this + 12), (char *)Block);
        goto LABEL_249;
      case 0x13Du:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 15) )
          goto LABEL_14;
        v15 = (*((_DWORD *)this + 30) & 0x8000) == 0;
        v92 = &Block;
        Block = 0;
        if ( !v15 )
          v92 = 0;
        if ( (unsigned int)CRTFRead::ReadRawText(v91, (char **)v92) )
        {
          v88 = Block;
          if ( !Block )
            goto LABEL_14;
          v89 = CTxtEdit::SetLeadingPunct(*((CTxtEdit **)this + 12), (char *)Block);
LABEL_249:
          if ( !v89 )
            goto LABEL_14;
          v90 = v88;
        }
        else
        {
LABEL_251:
          v90 = Block;
          if ( !Block )
            goto LABEL_14;
        }
        free(v90);
        goto LABEL_14;
      case 0x13Eu:
        if ( (*((_DWORD *)this + 30) & 0x8000) != 0 )
          goto LABEL_14;
        v93 = 1;
        goto LABEL_262;
      case 0x13Fu:
        v184 = *((_WORD *)this + 760);
        v185 = *((_WORD *)this + 822);
        if ( ((v184 & 1) == 0 || (v185 & 4) != 0) && (v184 & 4) == 0 )
        {
          *((_WORD *)this + 760) = v184 & 0xFFFE;
          *((_WORD *)this + 822) = v185 & 0xFFFB;
          goto LABEL_14;
        }
        *((_WORD *)this + 760) = v184 & 0xFFFE;
        *((_WORD *)this + 822) = v185 & 0xFFFB;
        goto LABEL_8;
      case 0x140u:
        v186 = (_WORD *)*((_QWORD *)this + 193);
        if ( v186 && (*v186 <= 4u || *v186 == 9) )
          goto LABEL_8;
        goto LABEL_14;
      case 0x141u:
        *((_WORD *)this + 760) |= 1u;
        *((_WORD *)this + 822) &= ~4u;
        goto LABEL_583;
      case 0x142u:
LABEL_583:
        if ( (*(_BYTE *)(v2 + 4) & 8) == 0 )
          CRTFRead::FreeRtfObject(this);
        v192 = *((_QWORD *)this + 38);
        *((_WORD *)this + 822) &= ~0x100u;
        if ( (unsigned int)(*(__int16 *)(v192 + 10) - 1) <= 6 )
          goto LABEL_209;
        v193 = 7;
        if ( *(_WORD *)v247 != 578 )
          v193 = 3;
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, v193) )
          goto LABEL_14;
        if ( !CRTFRead::CheckRtfObject(v194) )
          goto LABEL_87;
        *(_DWORD *)(*((_QWORD *)this + 193) + 36LL) = 100;
        *(_DWORD *)(*((_QWORD *)this + 193) + 32LL) = 100;
        *(_WORD *)(*((_QWORD *)this + 193) + 4LL) = 1;
        *(_WORD *)(*((_QWORD *)this + 193) + 6LL) = 1;
        *(_QWORD *)(*((_QWORD *)this + 193) + 72LL) = 0;
        *(_QWORD *)(*((_QWORD *)this + 193) + 80LL) = 0;
        **((_WORD **)this + 193) = -1;
        CRTFRead::CheckListText(this, *(struct STATE **)(v2 + 32));
        goto LABEL_14;
      case 0x143u:
      case 0x144u:
      case 0x145u:
      case 0x146u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 4LL * (int)Block - 2264) = v11;
        goto LABEL_14;
      case 0x147u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 24LL) = v11;
        goto LABEL_14;
      case 0x148u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 20LL) = v11;
        goto LABEL_14;
      case 0x149u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 32LL) = v11;
        goto LABEL_14;
      case 0x14Au:
        *(_DWORD *)(*((_QWORD *)this + 193) + 36LL) = v11;
        goto LABEL_14;
      case 0x14Bu:
        *(_WORD *)(*((_QWORD *)this + 193) + 42LL) = v11;
        goto LABEL_14;
      case 0x14Cu:
        *(_WORD *)(*((_QWORD *)this + 193) + 40LL) = v11;
        goto LABEL_14;
      case 0x14Du:
        *((_WORD *)this + 822) &= 0xFE3Fu;
        *((_BYTE *)this + 1623) = 0;
        *((_QWORD *)this + 203) = 0;
        *((_QWORD *)this + 204) = 0;
        *((_DWORD *)this + 410) = -9999997;
        v58 = 29;
        goto LABEL_135;
      case 0x14Eu:
        *(_DWORD *)(*((_QWORD *)this + 193) + 28LL) = v11;
        goto LABEL_14;
      case 0x14Fu:
      case 0x150u:
      case 0x151u:
      case 0x152u:
      case 0x153u:
        **((_WORD **)this + 193) = (_WORD)v7 - 591;
        goto LABEL_619;
      case 0x154u:
        **((_WORD **)this + 193) = 9;
LABEL_619:
        *(_WORD *)(*((_QWORD *)this + 193) + 2LL) = v11;
        goto LABEL_14;
      case 0x155u:
        *((_DWORD *)this + 68) = v11;
        v197 = (_QWORD **)((char *)this + 208);
        **((_QWORD **)this + 26) = RTFGetBinaryDataFromStream;
        v198 = *((_DWORD *)this + 68);
        if ( v198 < 0 )
          goto LABEL_209;
        if ( v198 <= 125829120 )
        {
          v200 = (char *)this + 208;
        }
        else
        {
          v199 = *(_QWORD *)(*((_QWORD *)this + 12) + 240LL);
          if ( !v199 || !*(_QWORD *)(v199 + 24) )
          {
LABEL_209:
            *((_DWORD *)this + 31) = 16;
            goto LABEL_14;
          }
          v200 = (char *)this + 208;
        }
        switch ( *(_WORD *)(v2 + 10) )
        {
          case 6:
            v202 = CRTFRead::ObjectReadFromEditStream(this);
            *((_WORD *)this + 760) &= ~1u;
            *((_WORD *)this + 760) |= v202 != 0;
            break;
          case 7:
            CRTFRead::StaticObjectReadFromEditStream(this, v11);
            break;
          case 0x15:
            v201 = CRTFRead::BlobObjectReadFromEditStream((CTxtEdit **)this, v11);
            if ( v201 >= 0 )
            {
              *((_WORD *)this + 760) &= ~1u;
              *((_WORD *)this + 760) |= v201 != 0;
            }
            else
            {
              *((_DWORD *)this + 31) = 16;
            }
            break;
          default:
            goto LABEL_640;
        }
        v197 = (_QWORD **)v200;
LABEL_640:
        **v197 = RTFGetFromStream;
        goto LABEL_14;
      case 0x156u:
      case 0x157u:
        goto LABEL_458;
      case 0x158u:
        *(_WORD *)(*((_QWORD *)this + 193) + 4LL) = v11;
        goto LABEL_14;
      case 0x159u:
        *(_WORD *)(*((_QWORD *)this + 193) + 6LL) = v11;
        goto LABEL_14;
      case 0x15Au:
        *(_WORD *)(*((_QWORD *)this + 193) + 8LL) = v11;
        goto LABEL_14;
      case 0x15Bu:
      case 0x15Cu:
      case 0x15Du:
      case 0x15Eu:
        **((_WORD **)this + 193) = (_WORD)v7 - 598;
        v195 = (_WORD *)*((_QWORD *)this + 193);
        if ( *v195 == 8 && v11 == 1 )
          *v195 = 12;
        goto LABEL_14;
      case 0x15Fu:
        v58 = 4;
        goto LABEL_135;
      case 0x160u:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 6) )
          goto LABEL_14;
        if ( ((**((_WORD **)this + 193) - 8) & 0xFFFB) != 0 )
        {
          if ( (*((_DWORD *)this + 30) & 0x8000) == 0 && (unsigned int)CW32System::SkipObjectData()
            || **((_WORD **)this + 193) == 10 )
          {
            *((_WORD *)this + 822) |= 4u;
LABEL_8:
            if ( !(unsigned int)CRTFRead::SkipToEndOfGroup(this) )
            {
              if ( ((*(_WORD *)(v2 + 10) - 2) & 0xFFEF) == 0 )
                *(_WORD *)(v2 + 10) = 17;
LABEL_11:
              CRTFRead::HandleEndGroup(this);
            }
          }
        }
        else
        {
          *(_WORD *)(v2 + 10) = 21;
        }
        goto LABEL_14;
      case 0x161u:
      case 0x163u:
      case 0x165u:
        **((_WORD **)this + 193) = 10;
        goto LABEL_14;
      case 0x162u:
        v58 = 5;
        goto LABEL_135;
      case 0x164u:
        *(_BYTE *)(*((_QWORD *)this + 193) + 14LL) = 1;
        goto LABEL_14;
      case 0x166u:
        v196 = *((_WORD *)this + 760);
        if ( (v196 & 0x4000) == 0 && **((_WORD **)this + 193) != 10 && (v196 & 5) == 0 )
          goto LABEL_8;
        *(_WORD *)(v2 + 10) = 0;
        goto LABEL_14;
      case 0x167u:
        **((_WORD **)this + 193) = 11;
        goto LABEL_14;
      case 0x168u:
      case 0x169u:
        if ( (*(_BYTE *)(v2 + 4) & 4) == 0 )
          CRTFRead::CheckNotifyLowFiRTF(this, 1);
        *(_DWORD *)(v2 + 4) |= 8u;
        *((_DWORD *)this + 388) = 0;
        CRTFRead::CheckRtfObject(this);
        goto LABEL_14;
      case 0x16Au:
        *(_WORD *)(v2 + 10) = 27;
        goto LABEL_14;
      case 0x16Bu:
        if ( *((_QWORD *)this + 193) )
        {
          v187 = CW32System::MulDivFunc(v11, 127, 72);
          *(_WORD *)(v188 + 44) = v187;
        }
        goto LABEL_14;
      case 0x16Du:
        *(_WORD *)(v2 + 10) = 19;
        goto LABEL_14;
      case 0x16Eu:
        v189 = (__int16 *)*((_QWORD *)this + 193);
        if ( !v189 || (unsigned int)(*v189 - 3) > 1 )
          goto LABEL_14;
        goto LABEL_8;
      case 0x16Fu:
        *(_WORD *)(v2 + 10) = 28;
        goto LABEL_14;
      case 0x170u:
        if ( *((_QWORD *)this + 193) )
        {
          v190 = CW32System::MulDivFunc(v11, 127, 72);
          *(_WORD *)(v191 + 46) = v190;
        }
        goto LABEL_14;
      case 0x171u:
        *(_WORD *)(v2 + 10) = 20;
        goto LABEL_14;
      case 0x172u:
        if ( (unsigned int)(v11 - 1) <= 4 && v11 != 3 )
        {
          *((_DWORD *)this + 388) |= 0x200u;
          if ( v11 == 1 )
            *((_DWORD *)this + 388) |= 0x1000u;
        }
        goto LABEL_14;
      case 0x173u:
        *((_DWORD *)this + 388) |= 0x100u;
        goto LABEL_14;
      case 0x174u:
      case 0x175u:
      case 0x176u:
      case 0x177u:
      case 0x178u:
      case 0x179u:
      case 0x17Au:
      case 0x17Bu:
      case 0x17Cu:
      case 0x17Du:
      case 0x17Eu:
      case 0x17Fu:
      case 0x180u:
      case 0x181u:
      case 0x182u:
      case 0x183u:
      case 0x184u:
      case 0x185u:
      case 0x186u:
        if ( (*((_BYTE *)this + 203) & 1) != 0 )
        {
          *(_BYTE *)(v2 + 86) = 0;
          v234 = *((unsigned __int16 *)this + 122);
          *(_WORD *)(v2 + 10) = 35;
          v235 = 41;
          *(_BYTE *)(v2 + 84) = *((_BYTE *)L"adee" + v234);
          *((_WORD *)this + 822) &= ~0x20u;
          ++*((_BYTE *)this + 201);
          v236 = *((_WORD *)this + 122);
          *((_BYTE *)this + 1647) = 0;
          *((_WORD *)this + 825) = *(&szRowStart + *(unsigned __int8 *)(v2 + 84));
          if ( v236 != 632 )
            v235 = 0;
          *((_WORD *)this + 826) = v235;
          *((_WORD *)this + 827) = 0;
          if ( v236 != 633 && v236 != 639 )
            LOBYTE(v14) = 0;
          *((_BYTE *)this + 1649) = v14;
        }
        goto LABEL_14;
      case 0x187u:
      case 0x188u:
        v240 = *(_QWORD *)(v2 + 32);
        if ( !v240
          || (unsigned int)(*(__int16 *)(v240 + 10) - 34) > 1
          || !CRTFRead::StoreDestination(this, (struct STATE *)v2, 30) )
        {
          goto LABEL_148;
        }
        v242 = *(_BYTE *)(*(_QWORD *)(v2 + 32) + 86LL);
        *((_BYTE *)this + 172) = *((_BYTE *)this + 201) + *((_BYTE *)this + 202);
        *((_BYTE *)this + 174) = v242;
        v243 = *(_BYTE *)(*(_QWORD *)(v2 + 32) + 84LL);
        *((_DWORD *)this + 82) |= 0x1000080u;
        *((_BYTE *)this + 173) = v243;
        if ( v243 != 20 )
          CRTFRead::CheckStartObject(this, v241);
        *((_BYTE *)this + 1659) = 0;
        goto LABEL_14;
      case 0x189u:
        v212 = *((_BYTE *)this + 203);
        if ( (v212 & 4) != 0 )
          goto LABEL_14;
        *((_DWORD *)this + 82) |= 0x8000000u;
        v213 = v212 | 4;
        *((_DWORD *)this + 32) = 0x8000000;
        goto LABEL_669;
      case 0x18Bu:
      case 0x18Cu:
        if ( (unsigned int)v11 <= 2 && (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v227 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v227 )
          {
            if ( *v6 == 651 )
              v228 = v11 << 16;
            else
              v228 = v11 << 18;
            v229 = -196609;
            if ( *v6 != 651 )
              v229 = -786433;
            *((_DWORD *)v227 + 47) = v228 | *((_DWORD *)v227 + 47) & v229;
          }
        }
        goto LABEL_14;
      case 0x190u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v215 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v215 )
          {
            *((_DWORD *)v215 + 47) &= 0xFFFFFFFC;
            if ( (unsigned int)(v11 - 3) <= 1 )
              *((_DWORD *)v215 + 47) |= (v11 != 3) + 2;
          }
        }
        goto LABEL_14;
      case 0x191u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v216 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          v217 = v216;
          if ( v216 )
          {
            *((_DWORD *)v216 + 47) &= 0xFFFFFCFF;
            if ( (unsigned int)(v11 - 1) <= 1 )
            {
              v218 = 256;
              if ( v11 != 1 )
                v218 = 768;
              *((_DWORD *)v217 + 47) |= v218;
            }
          }
        }
        goto LABEL_14;
      case 0x192u:
        goto LABEL_706;
      case 0x193u:
        v219 = (CTxtEdit *)*((_QWORD *)this + 12);
        if ( (*((_DWORD *)v219 + 70) & 0x200) != 0 )
          goto LABEL_14;
        v220 = *((_DWORD *)this + 2);
        CTxtEdit::GetDocInfo(v219);
        v221 = (__int16 *)CArrayBase::Elem(this, 0);
        v223 = 0;
        if ( v220 <= 0 )
          goto LABEL_14;
        while ( v11 != *v221 )
        {
          v221 += 40;
          if ( ++v223 >= v220 )
            goto LABEL_14;
        }
        if ( v222 )
        {
          FontOptions = (const struct CFontOptions *)CTxtEdit::GetFontOptions(*((_QWORD *)this + 12), &v247);
          CDocInfo::SetMathFont(v226, (const unsigned __int16 *)(v225 + 6), FontOptions);
          *((_WORD *)this + 102) = v11;
        }
        goto LABEL_14;
      case 0x194u:
        if ( v11 <= 4 )
        {
          *((_BYTE *)this + 352) &= 0xFu;
          *((_BYTE *)this + 352) |= 16 * (_BYTE)v11;
          *((_DWORD *)this + 102) |= 0x1000000u;
        }
        goto LABEL_14;
      case 0x196u:
        if ( CTxtEdit::FDisableMath(*((CTxtEdit **)this + 12)) )
          goto LABEL_8;
        if ( (*((_BYTE *)this + 203) & 1) != 0 )
          goto LABEL_14;
        *((_DWORD *)this + 82) |= 0x10000000u;
        *((_DWORD *)this + 32) = 0x10000000;
        v210 = *((_WORD *)this + 102);
        if ( v210 == -1 )
        {
          CW32System::IsDefaultFontDefined(0x33u, -1, 0, (__int16 *)this + 67, v244, (const struct IDpiAccessor *)v245);
          *((_BYTE *)this + 133) = v211;
          *((_DWORD *)this + 81) |= 0x20000000u;
        }
        else
        {
          CRTFRead::SelectCurrentFont(this, v210, 0);
          v211 = 0;
        }
        *((_BYTE *)this + 203) |= 1u;
        *((_WORD *)this + 822) |= 8u;
        *((_WORD *)this + 828) = v211;
        *((_BYTE *)this + 1659) = v211;
        v58 = 36;
        goto LABEL_135;
      case 0x197u:
        *((_BYTE *)this + 352) &= 0xFu;
        v58 = 37;
        *((_DWORD *)this + 102) |= 0x1000000u;
        goto LABEL_135;
      case 0x199u:
        if ( CTxtEdit::FDisableMath(*((CTxtEdit **)this + 12)) )
          goto LABEL_14;
LABEL_458:
        v169 = 1;
        goto LABEL_460;
      case 0x19Du:
        v10 = 4;
        goto LABEL_706;
      case 0x19Eu:
        v10 = 8;
        goto LABEL_706;
      case 0x19Fu:
        v10 = 1024;
LABEL_706:
        if ( (unsigned int)v11 <= 1 && (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v231 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v231 )
          {
            *((_DWORD *)v231 + 47) &= ~v10;
            if ( v11 )
              *((_DWORD *)v231 + 47) |= v10;
          }
        }
        goto LABEL_14;
      case 0x1A0u:
      case 0x1A1u:
      case 0x1A2u:
      case 0x1A3u:
      case 0x1A4u:
      case 0x1A5u:
      case 0x1A6u:
      case 0x1A7u:
      case 0x1A8u:
        if ( (unsigned int)IsValidTwip(v11) )
        {
          v230 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v230 )
            *((_DWORD *)v230 + (unsigned __int16)*v6 - 624) = v11;
        }
        goto LABEL_14;
      case 0x1ADu:
        v237 = *(_QWORD *)(v2 + 32);
        if ( !v237 || *(_WORD *)(v237 + 10) != 35 )
          goto LABEL_148;
        *(_BYTE *)(v2 + 86) = *(_BYTE *)(v237 + 86);
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 34);
        CRTFRead::CheckStartObject(v239, v238);
        goto LABEL_14;
      case 0x1B0u:
        if ( *(_BYTE *)(v2 + 85) )
          goto LABEL_14;
        v181 = L"&";
        v182 = 1;
        goto LABEL_545;
      case 0x1B2u:
        v58 = 31;
        goto LABEL_135;
      case 0x1B5u:
        if ( (unsigned int)v11 > 0x7D )
          goto LABEL_148;
        if ( *(_BYTE *)(v2 + 85) )
          goto LABEL_14;
        if ( !*((_BYTE *)this + 1658) )
          *((_BYTE *)this + 1658) = v11 + 1;
        v181 = L"@&";
LABEL_544:
        v182 = 2;
LABEL_545:
        CRTFRead::AddText(this, v181, v182, 0, 0, 0);
        goto LABEL_14;
      case 0x1B7u:
        v214 = *((_BYTE *)this + 203);
        if ( (v214 & 2) == 0 )
        {
          *((_DWORD *)this + 82) |= 0x20000000u;
          v213 = v214 | 2;
          *((_DWORD *)this + 32) = 0x20000000;
LABEL_669:
          *((_BYTE *)this + 203) = v213;
        }
        goto LABEL_14;
      case 0x1B9u:
        v232 = 0;
        if ( (unsigned int)v11 <= 0xC )
          v232 = *((_DWORD *)this + 60);
        *((_BYTE *)this + 1646) = v232;
        goto LABEL_14;
      case 0x1BAu:
        v233 = 0;
        if ( (unsigned int)(v11 - 1) <= 2 )
          v233 = *((_DWORD *)this + 60);
        *((_BYTE *)this + 1646) |= 16 * v233;
        goto LABEL_14;
      case 0x1BBu:
        *((_BYTE *)this + 1648) = v11;
        *((_WORD *)this + 822) |= 0x20u;
        goto LABEL_14;
      case 0x1BCu:
      case 0x1BDu:
      case 0x1BEu:
      case 0x1BFu:
      case 0x1C1u:
      case 0x1C2u:
      case 0x1C3u:
      case 0x1C4u:
      case 0x1C5u:
      case 0x1C6u:
      case 0x1C9u:
      case 0x1CAu:
        goto LABEL_734;
      case 0x1C0u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 32);
        *((_DWORD *)this + 32) = 0;
        *((_DWORD *)this + 81) |= 3u;
        goto LABEL_14;
      case 0x1C8u:
        *((_BYTE *)this + 1647) = 1;
LABEL_734:
        v58 = 33;
LABEL_135:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, v58);
        goto LABEL_14;
      case 0x1D8u:
        *((_WORD *)this + 825) = 0;
        goto LABEL_14;
      case 0x1D9u:
        *((_WORD *)this + 826) = 0;
        goto LABEL_14;
      case 0x1DAu:
        *((_WORD *)this + 827) = 0;
        goto LABEL_14;
      case 0x1E7u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 && (*(_DWORD *)(*((_QWORD *)this + 12) + 176LL) & 0x80000) == 0 )
        {
          v93 = *((_DWORD *)this + 60);
LABEL_262:
          CRTFRead::HandleSTextFlow(this, v93);
        }
        goto LABEL_14;
      case 0x1E8u:
        if ( v11 > 0 )
        {
          *((_DWORD *)this + 32) &= ~0x40000000u;
          *((_DWORD *)this + 81) |= 0x40000000u;
          Color = *((_DWORD *)&rgcrRevisions + (((_BYTE)v11 - 1) & 7));
LABEL_92:
          *((_DWORD *)this + 35) = Color;
        }
        goto LABEL_14;
      case 0x1E9u:
        if ( (*(_DWORD *)(*((_QWORD *)this + 12) + 272LL) & 0x2000000) == 0 )
          goto LABEL_14;
        v205 = (__int64 *)((char *)this + 1584);
        if ( *((_QWORD *)this + 198) )
        {
          v207 = (_QWORD *)((char *)this + 1584);
        }
        else
        {
          v206 = mallocTypeZeroed<long>(32, v7, v4);
          *v205 = v206;
          if ( !v206 )
            goto LABEL_90;
          *((_QWORD *)this + 199) = 8;
          v207 = (_QWORD *)((char *)this + 1584);
        }
        v208 = *((_DWORD *)this + 398);
        *((_DWORD *)this + 398) = v208 - 1;
        if ( v208 > 0 )
        {
          v207 = (_QWORD *)((char *)this + 1584);
        }
        else
        {
          v209 = _o_realloc(*v205, 4LL * (*((_DWORD *)this + 399) + 8));
          if ( !v209 )
            goto LABEL_90;
          *v205 = v209;
          *((_DWORD *)this + 398) = 7;
        }
        *(_DWORD *)(*v207 + 4LL * (int)(*((_DWORD *)this + 399))++) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        goto LABEL_14;
      case 0x1EAu:
        v169 = 0;
LABEL_460:
        CRTFRead::CheckNotifyLowFiRTF(this, v169);
        goto LABEL_8;
      default:
        if ( v8 <= 0x1EC )
          goto LABEL_14;
        if ( (*(_DWORD *)(*((_QWORD *)this + 12) + 176LL) & 0x80000) == 0
          || (unsigned int)(unsigned __int16)v7 - 8216 > 5 )
        {
          goto LABEL_79;
        }
        if ( (_WORD)v7 == 8216 )
          goto LABEL_752;
        if ( (_WORD)v7 == 8217 )
        {
          v6 = (_WORD *)((char *)this + 244);
LABEL_752:
          *v6 = 39;
        }
        else if ( (unsigned __int16)(*((_WORD *)this + 122) - 8220) <= 1u )
        {
          *((_WORD *)this + 122) = 34;
        }
LABEL_79:
        if ( CRTFRead::IsLowMergedCell(this) )
          goto LABEL_14;
        if ( (*((_DWORD *)this + 81) & 0xA000000) == 0xA000000
          && (unsigned int)CW32System::IsBiDiLcid(*((_DWORD *)this + 38))
          && !*((_BYTE *)this + 132) )
        {
          *((_BYTE *)this + 132) = CCharFormat::CharRepFromLang((CRTFRead *)((char *)this + 128));
        }
        v42 = *((_WORD *)this + 122);
        goto LABEL_82;
    }
  }
  if ( *((_QWORD *)this + 193) )
  {
    v6 = (_WORD *)((char *)this + 244);
    goto LABEL_5;
  }
  *((_DWORD *)this + 31) = 16;
  return 16;
}

```

## disassembly

```asm
0x18008ebf4  push    rbp
0x18008ebf6  push    rbx
0x18008ebf7  push    rsi
0x18008ebf8  push    rdi
0x18008ebf9  push    r12
0x18008ebfb  push    r13
0x18008ebfd  push    r14
0x18008ebff  push    r15
0x18008ec01  lea     rbp, [rsp-1Fh]
0x18008ec06  sub     rsp, 88h
0x18008ec0d  mov     rax, [rcx+68h]
0x18008ec11  mov     rbx, rcx
0x18008ec14  mov     rsi, [rcx+130h]
0x18008ec1b  mov     rax, [rax+18h]
0x18008ec1f  lea     r10, [rbx+0F4h]
0x18008ec26  mov     [rbp+57h+arg_18], rax
0x18008ec2a  mov     [rbp+57h+arg_10], r10
0x18008ec2e  lea     rcx, [rax-8]
0x18008ec32  neg     rax
0x18008ec35  mov     [rbp+57h+var_70], rcx
0x18008ec39  sbb     r8, r8
0x18008ec3c  xor     r12d, r12d
0x18008ec3f  and     r8, rcx
0x18008ec42  test    rsi, rsi
0x18008ec45  jz      loc_18008ED4F
0x18008ec4b  mov     [rbp+57h+arg_10], r10
0x18008ec4f  movzx   ecx, word ptr [r10]
0x18008ec53  mov     dword ptr [rbp+57h+Block], ecx
0x18008ec56  lea     eax, [rcx-243h]
0x18008ec5c  cmp     eax, 24h ; '$'
0x18008ec5f  jbe     loc_18008F748
0x18008ec65  mov     r15, r10
0x18008ec68  movzx   edx, cx; struct STATE *
0x18008ec6b  mov     [rbp+57h+var_60], r15
0x18008ec6f  add     ecx, 0FFFFFF00h; switch 491 cases
0x18008ec75  mov     [rbp+57h+arg_0], r12b
0x18008ec79  cmp     ecx, 1EAh
0x18008ec7f  ja      def_18008ECC6; jumptable 000000018008ECC6 default case
0x18008ec85  lea     r11, __ImageBase
0x18008ec8c  movsxd  rax, ecx
0x18008ec8f  lea     r9, [rbx+0F0h]; int
0x18008ec96  mov     r13d, 800h
0x18008ec9c  mov     edi, [r9]
0x18008ec9f  movzx   eax, ds:(byte_180092150 - 180000000h)[r11+rax]
0x18008eca8  mov     ecx, ds:(jpt_18008ECC6 - 180000000h)[r11+rax*4]
0x18008ecb0  mov     eax, 4
0x18008ecb5  add     rcx, r11
0x18008ecb8  mov     r11d, 1000h
0x18008ecbe  lea     r12d, [rax-2]
0x18008ecc2  lea     r14d, [rax-3]
0x18008ecc6  jmp     rcx; switch jump
0x18008eccc  mov     eax, 20Fh; jumptable 000000018008ECC6 case 258
0x18008ecd1  cmp     [rbx+0F6h], ax
0x18008ecd8  jnz     short loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ecda  mov     rcx, rbx; jumptable 000000018008ECC6 cases 510,511,553,742
0x18008ecdd  call    ?SkipToEndOfGroup@CRTFRead@@AEAAHXZ; CRTFRead::SkipToEndOfGroup(void)
0x18008ece2  test    eax, eax
0x18008ece4  jnz     short loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ece6  movzx   eax, word ptr [rsi+0Ah]
0x18008ecea  mov     ecx, 0FFEFh
0x18008ecef  sub     ax, r12w
0x18008ecf3  test    cx, ax
0x18008ecf6  jz      loc_18008F468
0x18008ecfc  mov     rcx, rbx; this
0x18008ecff  call    ?HandleEndGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleEndGroup(void)
0x18008ed04  jmp     short loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ed06  test    byte ptr [rbx+5F3h], 20h; jumptable 000000018008ECC6 cases 256,257
0x18008ed0d  jnz     loc_180090FC4
0x18008ed13  mov     rdx, rsi; struct STATE *
0x18008ed16  mov     rcx, rbx; this
0x18008ed19  call    ?HandleTextToken@CRTFRead@@AEAAHPEAUSTATE@@@Z; CRTFRead::HandleTextToken(STATE *)
0x18008ed1e  mov     al, [rbx+5F3h]; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ed24  mov     cl, [rbp+57h+arg_0]
0x18008ed27  shl     cl, 5
0x18008ed2a  xor     cl, al
0x18008ed2c  and     cl, 20h
0x18008ed2f  xor     cl, al
0x18008ed31  mov     eax, [rbx+7Ch]
0x18008ed34  mov     [rbx+5F3h], cl
0x18008ed3a  add     rsp, 88h
0x18008ed41  pop     r15
0x18008ed43  pop     r14
0x18008ed45  pop     r13
0x18008ed47  pop     r12
0x18008ed49  pop     rdi
0x18008ed4a  pop     rsi
0x18008ed4b  pop     rbx
0x18008ed4c  pop     rbp
0x18008ed4d  retn
0x18008ed4f  mov     eax, 105h
0x18008ed54  cmp     [r10], ax
0x18008ed58  jz      loc_18008EC4F
0x18008ed5e  mov     eax, 18h
0x18008ed63  mov     [rbx+7Ch], eax
0x18008ed66  jmp     short loc_18008ED3A
0x18008ed68  cmp     [rsi+0Ah], r12w; jumptable 000000018008ECC6 case 283
0x18008ed6d  jz      loc_18008F092
0x18008ed73  xor     r15d, r15d
0x18008ed76  cmp     [rbx+8], r15d
0x18008ed7a  jz      short loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ed7c  lea     r8d, [r15+12h]
0x18008ed80  cmp     [rsi+0Ah], r8w
0x18008ed85  jz      short loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ed87  or      ecx, 0FFFFFFFFh
0x18008ed8a  cmp     edi, ecx
0x18008ed8c  jz      short loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ed8e  xor     r8d, r8d; struct CCharFormat *
0x18008ed91  movzx   edx, di; __int16
0x18008ed94  mov     rcx, rbx; this
0x18008ed97  call    ?SelectCurrentFont@CRTFRead@@AEAA_NFPEAVCCharFormat@@@Z; CRTFRead::SelectCurrentFont(short,CCharFormat *)
0x18008ed9c  mov     edx, [rsi+10h]; int
0x18008ed9f  test    edx, edx
0x18008eda1  js      loc_18008F59A
0x18008eda7  cmp     edx, [rbx+8]
0x18008edaa  jge     loc_18008F59A
0x18008edb0  mov     rcx, rbx; this
0x18008edb3  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18008edb8  mov     rcx, r14
0x18008edbb  test    rax, rax
0x18008edbe  jz      short loc_18008EDE1
0x18008edc0  mov     r9b, [rax+2]
0x18008edc4  mov     cl, r9b; unsigned __int8
0x18008edc7  call    ?IsBiDiCharRep@CW32System@@SAHE@Z; CW32System::IsBiDiCharRep(uchar)
0x18008edcc  test    eax, eax
0x18008edce  jnz     loc_18008F9A1
0x18008edd4  mov     rcx, r14
0x18008edd7  cmp     [rsi+17h], r12b
0x18008eddb  jz      loc_18008F342
0x18008ede1  mov     [rsi+rcx*4+3Eh], r15w
0x18008ede7  mov     r15d, 10h
0x18008eded  mov     [rsi+rcx*4+3Ch], di
0x18008edf2  or      [rsi+4], r15d
0x18008edf6  jmp     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008edfb  mov     rcx, rbx; jumptable 000000018008ECC6 case 261
0x18008edfe  call    ?HandleStartGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleStartGroup(void)
0x18008ee03  movzx   edx, word ptr [rbx+5F0h]
0x18008ee0a  bt      dx, 8
0x18008ee0f  jb      loc_18008F1B3
0x18008ee15  mov     [rbp+57h+arg_0], r14b
0x18008ee19  jmp     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ee1e  movsx   rax, byte ptr [rsi+17h]; jumptable 000000018008ECC6 case 284
0x18008ee23  xor     r13d, r13d
0x18008ee26  mov     [rsi+rax*4+3Ch], di
0x18008ee2b  mov     edi, r13d
0x18008ee2e  movsx   rax, byte ptr [rsi+17h]; jumptable 000000018008ECC6 case 285
0x18008ee33  mov     [rsi+rax*4+3Eh], di
0x18008ee38  jmp     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ee3d  movzx   eax, byte ptr [rbx+0CBh]; jumptable 000000018008ECC6 case 562
0x18008ee44  shl     eax, 4
0x18008ee47  xor     eax, [rsi+4]
0x18008ee4a  and     eax, 10h
0x18008ee4d  xor     [rsi+4], eax
0x18008ee50  mov     cl, [r10]; jumptable 000000018008ECC6 cases 560,561,563,564
0x18008ee53  sub     cl, 2Fh ; '/'
0x18008ee56  movsx   eax, cl
0x18008ee59  sub     eax, r14d
0x18008ee5c  mov     [rsi+17h], cl
0x18008ee5f  cmp     eax, r14d
0x18008ee62  ja      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ee68  movsx   rax, cl
0x18008ee6c  or      ecx, 0FFFFFFFFh
0x18008ee6f  movzx   edx, word ptr [rsi+rax*4+3Ch]; __int16
0x18008ee74  cmp     dx, cx
0x18008ee77  jz      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ee7d  xor     r8d, r8d; struct CCharFormat *
0x18008ee80  mov     rcx, rbx; this
0x18008ee83  call    ?SelectCurrentFont@CRTFRead@@AEAA_NFPEAVCCharFormat@@@Z; CRTFRead::SelectCurrentFont(short,CCharFormat *)
0x18008ee88  mov     rcx, rbx; this
0x18008ee8b  call    ?HandleNumber@CRTFRead@@AEAAHXZ; CRTFRead::HandleNumber(void)
0x18008ee90  movsx   rax, byte ptr [rsi+17h]
0x18008ee95  movsx   ecx, word ptr [rsi+rax*4+3Eh]
0x18008ee9a  mov     edi, ecx
0x18008ee9c  test    cx, cx
0x18008ee9f  jz      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008eea5  mov     r10, [rbp+57h+arg_10]
0x18008eea9  mov     eax, edi; jumptable 000000018008ECC6 case 298
0x18008eeab  neg     eax
0x18008eead  cmovs   eax, edi
0x18008eeb0  cmp     eax, 2710h
0x18008eeb5  jg      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008eebb  movsx   rax, byte ptr [rsi+17h]
0x18008eec0  mov     r15d, 8
0x18008eec6  mov     [rsi+rax*4+3Eh], di
0x18008eecb  movzx   eax, di
0x18008eece  bts     dword ptr [rbx+144h], 1Fh
0x18008eed6  movzx   ecx, word ptr [rbx+66Ch]
0x18008eedd  shl     di, 2
0x18008eee1  add     ax, di
0x18008eee4  add     ax, ax
0x18008eee7  mov     [rbx+88h], ax
0x18008eeee  test    r15b, cl
0x18008eef1  jz      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008eef7  mov     edx, 12Ah
0x18008eefc  cmp     [r10], dx
0x18008ef00  jnz     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef06  mov     [rbx+678h], ax
0x18008ef0d  mov     eax, 0FFF7h
0x18008ef12  and     cx, ax
0x18008ef15  mov     [rbx+66Ch], cx
0x18008ef1c  jmp     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef21  mov     rcx, rbx; jumptable 000000018008ECC6 case 262
0x18008ef24  call    ?HandleFieldEndGroup@CRTFRead@@AEAAXXZ; CRTFRead::HandleFieldEndGroup(void)
0x18008ef29  mov     rcx, rbx; this
0x18008ef2c  call    ?HandleEndGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleEndGroup(void)
0x18008ef31  movzx   edx, word ptr [rbx+66Ch]
0x18008ef38  bt      dx, 8
0x18008ef3d  jnb     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef43  mov     rax, [rsi+20h]
0x18008ef47  test    rax, rax
0x18008ef4a  jz      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef50  mov     ecx, 7
0x18008ef55  cmp     [rax+0Ah], cx
0x18008ef59  jnz     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef5f  mov     ecx, 0FEFFh
0x18008ef64  and     dx, cx
0x18008ef67  mov     [rbx+66Ch], dx
0x18008ef6e  jmp     loc_18008ECDA; jumptable 000000018008ECC6 cases 510,511,553,742
0x18008ef73  mov     al, [rbx+5F3h]; jumptable 000000018008ECC6 case 527
0x18008ef79  shr     al, 5
0x18008ef7c  mov     [rbp+57h+arg_0], al
0x18008ef7f  jmp     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef84  mov     edx, [rsi+10h]; jumptable 000000018008ECC6 case 294
0x18008ef87  test    edx, edx
0x18008ef89  js      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef8f  cmp     edx, [rbx+8]
0x18008ef92  jge     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008ef98  mov     rcx, rbx; this
0x18008ef9b  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18008efa0  mov     r10, rax
0x18008efa3  test    rax, rax
0x18008efa6  jz      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008efac  mov     al, [rax+2]
0x18008efaf  mov     edx, 0Ah
0x18008efb4  cmp     al, dl
0x18008efb6  jz      short loc_18008EFC4
0x18008efb8  mov     cl, dil; unsigned __int8
0x18008efbb  call    ?CharRepFromCharSet@CW32System@@SAEE@Z; CW32System::CharRepFromCharSet(uchar)
0x18008efc0  mov     [r10+2], al
0x18008efc4  mov     cl, al; unsigned __int8
0x18008efc6  call    ?CodePageFromCharRep@CW32System@@SAGE@Z; CW32System::CodePageFromCharRep(uchar)
0x18008efcb  mov     edx, 0FDE9h
0x18008efd0  mov     [r10+4Ch], ax
0x18008efd5  cmp     [rsi+0Ch], dx
0x18008efd9  jz      loc_18008F95F
0x18008efdf  mov     [rsi+0Ch], ax
0x18008efe3  cmp     ax, 2Ah ; '*'
0x18008efe7  jz      short loc_18008EFFB
0x18008efe9  mov     ecx, 0FFFFh
0x18008efee  cmp     [rbx+600h], cx
0x18008eff5  jz      loc_18008F966
0x18008effb  movzx   eax, dil
0x18008efff  sub     eax, 0B1h
0x18008f004  cmp     eax, r14d
0x18008f007  jbe     loc_18008F310
0x18008f00d  mov     eax, 80h
0x18008f012  or      [rbx+5F0h], ax
0x18008f019  test    edi, edi
0x18008f01b  jz      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f021  lea     r15d, [rax-78h]
0x18008f025  or      [rbx+5F3h], r15b
0x18008f02c  jmp     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f031  mov     edx, [rsi+10h]; jumptable 000000018008ECC6 cases 286-293
0x18008f034  test    edx, edx
0x18008f036  js      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f03c  cmp     edx, [rbx+8]
0x18008f03f  jge     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f045  mov     rcx, rbx; this
0x18008f048  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18008f04d  test    rax, rax
0x18008f050  jz      loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f056  mov     cl, [rax+3]
0x18008f059  mov     dl, [r10]
0x18008f05c  and     cl, 0Fh
0x18008f05f  add     dl, r12b
0x18008f062  shl     dl, 4
0x18008f065  or      dl, cl
0x18008f067  mov     ecx, 124h
0x18008f06c  mov     [rax+3], dl
0x18008f06f  cmp     cx, [r10]
0x18008f073  jnz     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f079  mov     r8d, 9
0x18008f07f  cmp     [rax+2], r8b
0x18008f083  jnz     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f089  mov     byte ptr [rax+2], 0Ah
0x18008f08d  jmp     loc_18008ED1E; jumptable 000000018008ECC6 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18008f092  or      ecx, 0FFFFFFFFh
0x18008f095  cmp     edi, ecx
0x18008f097  jz      loc_18008ECDA; jumptable 000000018008ECC6 cases 510,511,553,742
0x18008f09d  movsx   eax, word ptr [rbx+5F4h]
0x18008f0a4  cmp     edi, eax
0x18008f0a6  jz      short loc_18008F0DC
0x18008f0a8  movsx   eax, word ptr [rbx+5F6h]
0x18008f0af  mov     edx, r14d; int
0x18008f0b2  cmp     edi, eax
0x18008f0b4  jz      loc_18008F98D
0x18008f0ba  xor     r8d, r8d; int *
0x18008f0bd  mov     rcx, rbx; this
0x18008f0c0  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x18008f0c5  xor     r13d, r13d
0x18008f0c8  test    rax, rax
  ... truncated ...
```
