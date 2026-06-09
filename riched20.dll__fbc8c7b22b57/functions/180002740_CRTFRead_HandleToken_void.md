# CRTFRead::HandleToken(void)

- ea: `0x180002740`
- end: `0x180004a08`
- name: `?HandleToken@CRTFRead@@AEAAHXZ`
- size: `8904`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `48`
- tags: `broker_com_uri`

## callers

- `0x1800020c4`

## callees

- `0x180001240`
- `0x180002740`
- `0x180004a80`
- `0x18000f280`
- `0x1800193e0`
- `0x18001c1d4`
- `0x18001e170`
- `0x18001e3e0`
- `0x18001f980`
- `0x180022ad4`
- `0x180025944`
- `0x18002720c`
- `0x1800274a0`
- `0x18002c900`
- `0x18002cad4`
- `0x18003a3a0`
- `0x18003b33c`
- `0x18003e56c`
- `0x1800413b8`
- `0x18004223c`
- `0x180043a4c`
- `0x180046384`
- `0x1800466f0`
- `0x180046cb4`
- `0x180048594`
- `0x180049af4`
- `0x180049b60`
- `0x180049e74`
- `0x180049fd8`
- `0x1800602f4`
- `0x18006042c`
- `0x1800783e0`
- `0x1800791ac`
- `0x180079a3c`
- `0x180079f34`
- `0x18007b10c`
- `0x18007c4d0`
- `0x18007e120`
- `0x18007e71c`
- `0x18007ed8c`
- `0x18007eee0`
- `0x18007ef54`
- `0x18007f754`
- `0x18008686c`
- `0x1800868cc`
- `0x18008e5e0`
- `0x180093320`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CRTFRead::HandleToken(CRTFRead *this)
{
  __int64 v1; // rdx
  CRTFRead *v2; // rbx
  __int64 v3; // r9
  int v4; // esi
  __int64 v5; // rdi
  int v6; // ecx
  int v7; // eax
  int v8; // ecx
  __int64 v9; // rcx
  __int64 result; // rax
  __int16 v11; // ax
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // ecx
  __int64 v15; // rdi
  int v16; // edx
  struct IUndoBuilder *v17; // rdx
  int v18; // r8d
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // ecx
  __int16 *v23; // rdx
  int v24; // edx
  int v25; // edx
  int v26; // eax
  int v27; // ebp
  _WORD *v28; // rax
  char v29; // al
  int v30; // ebp
  int v31; // esi
  int v32; // ebp
  int v33; // edx
  char v34; // cl
  unsigned int v35; // ebp
  _WORD *v36; // rax
  _WORD *v37; // rsi
  unsigned __int8 *v38; // r10
  int TrailBytesCount; // eax
  unsigned __int8 *v40; // r11
  unsigned __int8 v41; // cl
  struct _textfont *v42; // rax
  unsigned __int8 CharSet; // al
  __int64 v44; // r10
  __int16 CodePage; // cx
  __int16 *v46; // r8
  int v47; // eax
  int v48; // eax
  __int128 v49; // xmm1
  __int64 v50; // xmm0_8
  bool v51; // zf
  int v52; // eax
  _BYTE *v53; // rax
  int v54; // eax
  struct _textfont *v55; // rax
  char v56; // r9
  struct _textfont *v57; // rax
  struct _textfont *v58; // rax
  __int16 v59; // r11
  __int16 v60; // r10
  _WORD *v61; // rax
  int v62; // r9d
  __int16 v63; // r11
  unsigned __int16 v64; // dx
  int v65; // eax
  unsigned int Color; // eax
  __int64 v67; // rcx
  void **p_lpMem; // rdx
  void *v69; // rdi
  int v70; // eax
  void **v71; // rdx
  char v72; // r9
  int v73; // ebp
  __int16 v74; // ax
  int v75; // eax
  __int64 v76; // rdx
  unsigned __int16 v77; // bp
  int v78; // eax
  int v79; // edx
  __int64 v80; // rdx
  unsigned __int8 v81; // cl
  int v82; // edx
  char v83; // cl
  int StandardColorIndex; // eax
  char v85; // r9
  int v86; // eax
  unsigned __int8 v87; // r9
  unsigned __int8 v88; // cl
  __int16 v89; // ax
  __int16 v90; // dx
  const struct CParaFormat *PF; // rax
  CRunPtrBase *v92; // rcx
  __int16 v93; // ax
  __int16 v94; // dx
  int v95; // ecx
  int v96; // eax
  _QWORD *v97; // rax
  int v98; // r8d
  int v99; // eax
  __int64 v100; // rdx
  int v101; // ecx
  int v103; // eax
  int v104; // ecx
  char v105; // dl
  int v106; // eax
  __int64 v107; // r14
  void *v108; // rcx
  int v109; // eax
  __int16 v110; // cx
  __int16 v111; // ax
  _DWORD *v112; // rax
  int v113; // eax
  int v114; // eax
  void *v115; // rax
  int v116; // ecx
  void *v117; // rax
  unsigned __int16 v118; // cx
  int *v119; // r8
  int v120; // edx
  struct _textfont *StateFont; // rax
  CRTFRead *v122; // rcx
  int v123; // r8d
  __int64 v124; // r9
  struct _textfont *v125; // rax
  CRTFRead *v126; // rcx
  int v127; // r8d
  struct STATE *v128; // r9
  __int64 v129; // rcx
  unsigned int v130; // eax
  void *lpMem; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 v132; // [rsp+78h] [rbp+10h] BYREF

  v1 = *((unsigned __int16 *)this + 357);
  v132 = 0;
  v2 = this;
  if ( (_WORD)v1 )
  {
    this = (CRTFRead *)*((unsigned __int16 *)this + 66);
    if ( (unsigned __int16)((_WORD)this - 261) > 1u && (_WORD)this != 256 && (_WORD)this != 473 )
    {
      *((_WORD *)v2 + 357) = v1 - 1;
      return *((unsigned int *)v2 + 12);
    }
  }
  v3 = *((unsigned __int16 *)v2 + 66);
  if ( (unsigned int)(v3 - 460) > 0x1D || *((_QWORD *)v2 + 79) )
  {
    v4 = *((_DWORD *)v2 + 32);
    v5 = *((_QWORD *)v2 + 27);
    switch ( (_DWORD)v3 )
    {
      case 0x1BB:
        if ( (*((_BYTE *)v2 + 472) & 0x40) == 0 && (*(_BYTE *)(v5 + 4) & 0x10) == 0 && *(_WORD *)(v5 + 10) != 19 )
        {
          *((_DWORD *)v2 + 60) |= 0x40000u;
          *((_DWORD *)v2 + 21) &= ~0x40000u;
          v132 = v4;
          v7 = *(_DWORD *)(v5 + 20);
          if ( v7 >= 0 )
          {
            v8 = *((_DWORD *)v2 + 2);
            if ( v8 > 0 && v7 < v8 && (v1 = *(_QWORD *)v2) != 0 )
              v9 = v1 + *((_DWORD *)v2 + 4) * v7;
            else
              v9 = 0;
            if ( v9 && *(_BYTE *)(v9 + 2) == 2 )
            {
              if ( (unsigned int)(unsigned __int16)v4 - 61440 > 0xFF )
              {
                if ( (unsigned __int16)v4 > 0xFFu )
                {
                  LOBYTE(lpMem) = 0;
                  CW32System::WCTMB(0x4E4u, v1, &v132, 1, (LPSTR)&lpMem, 1, 0, 0, 0, 0);
                  v132 = (unsigned __int8)lpMem;
                }
              }
              else
              {
                v132 = v4 + 4096;
              }
            }
          }
          *((_WORD *)v2 + 357) = *(_WORD *)(v5 + 16);
          CRTFRead::AddText(v2, &v132, 1, 1);
        }
        return *((unsigned int *)v2 + 12);
      case 0x101:
LABEL_446:
        switch ( *(_WORD *)(v5 + 10) )
        {
          case 1:
            v119 = (int *)CArrayBase::ArAdd((CRTFRead *)((char *)v2 + 24), 1, 0);
            if ( !v119 )
              goto LABEL_460;
            if ( (*((_BYTE *)v2 + 472) & 8) != 0 )
              v120 = *(unsigned __int8 *)(v5 + 24)
                   | (*(unsigned __int8 *)(v5 + 26) << 16)
                   | (*(unsigned __int8 *)(v5 + 25) << 8);
            else
              v120 = -9999997;
            *v119 = v120;
            *(_WORD *)(v5 + 25) = 0;
            *(_BYTE *)(v5 + 24) = 0;
            *((_WORD *)v2 + 236) &= ~8u;
            break;
          case 2:
            if ( (*(_BYTE *)(v5 + 4) & 4) == 0 )
            {
              StateFont = CRTFRead::GetStateFont(v2, *((struct STATE **)v2 + 27));
              CRTFRead::ReadFontName(v122, StateFont, v123, (struct STATE *)v5);
            }
            break;
          case 5:
            if ( CRTFRead::StrAlloc(
                   v2,
                   (unsigned __int16 **)(*((_QWORD *)v2 + 79) + 56LL),
                   *((unsigned __int8 **)v2 + 17)) )
            {
              goto LABEL_460;
            }
            break;
          case 6:
            if ( CRTFRead::StrAlloc(
                   v2,
                   (unsigned __int16 **)(*((_QWORD *)v2 + 79) + 64LL),
                   *((unsigned __int8 **)v2 + 17)) )
            {
              goto LABEL_460;
            }
            break;
          case 0xA:
            if ( !*((_QWORD *)v2 + 61) )
            {
              if ( !*((_QWORD *)v2 + 77) )
                goto LABEL_27;
              *((_DWORD *)v2 + 12) = AppendString(
                                       (unsigned __int8 **)v2 + 77,
                                       *((unsigned __int8 **)v2 + 17),
                                       (int *)v2 + 156,
                                       (int *)v2 + 157);
            }
            break;
          case 0xB:
            if ( *((_QWORD *)v2 + 75) )
            {
              if ( *((unsigned __int8 *)v2 + 487) != 128
                && *((unsigned __int8 *)v2 + 487) != 129
                && *((unsigned __int8 *)v2 + 487) != 130
                && *((unsigned __int8 *)v2 + 487) != 134
                && *((unsigned __int8 *)v2 + 487) != 136
                && (*((unsigned __int8 *)v2 + 88) == 128
                 || *((unsigned __int8 *)v2 + 88) == 129
                 || *((unsigned __int8 *)v2 + 88) == 130
                 || *((unsigned __int8 *)v2 + 88) == 134
                 || *((unsigned __int8 *)v2 + 88) == 136) )
              {
                *((_BYTE *)v2 + 487) = *((_BYTE *)v2 + 88);
              }
              *((_DWORD *)v2 + 12) = AppendString(
                                       (unsigned __int8 **)v2 + 75,
                                       *((unsigned __int8 **)v2 + 17),
                                       (int *)v2 + 152,
                                       (int *)v2 + 153);
            }
            else
            {
              CRTFRead::HandleFieldInstruction(v2);
              *((_BYTE *)v2 + 487) = *((_BYTE *)v2 + 88);
            }
            break;
          case 0xE:
            v124 = *(_QWORD *)(v5 + 40);
            if ( v124 && *(_WORD *)(v124 + 10) == 2 )
            {
              *(_DWORD *)(v124 + 4) |= 4u;
              v125 = CRTFRead::GetStateFont(v2, (struct STATE *)v124);
              CRTFRead::ReadFontName(v126, v125, v127, v128);
            }
            break;
          case 0xF:
          case 0x10:
          case 0x11:
            return *((unsigned int *)v2 + 12);
          case 0x13:
            if ( (unsigned int)CW32System::ASCIICompareI(*((const unsigned __int8 **)v2 + 17), "heading", 7) )
            {
              v130 = *(unsigned __int8 *)(v129 + 8) - 48;
              if ( v130 < 0xA )
                *((_BYTE *)v2 + v130 + 156) = *((_BYTE *)v2 + 166);
            }
            break;
          default:
LABEL_27:
            CRTFRead::HandleText(v2, *((char **)v2 + 17), (_WORD)v3 == 257, -1);
            break;
        }
        break;
      case 0x102:
        if ( *((_WORD *)v2 + 67) == 426 )
        {
LABEL_29:
          if ( !(unsigned int)CRTFRead::SkipToEndOfGroup(v2) )
          {
            v11 = *(_WORD *)(v5 + 10);
            if ( v11 == 2 || v11 == 19 )
              *(_WORD *)(v5 + 10) = 18;
LABEL_33:
            CRTFRead::HandleEndGroup(v2);
          }
        }
        return *((unsigned int *)v2 + 12);
      case 0x1C2:
LABEL_34:
        *(_DWORD *)(v5 + 4) &= ~0x200u;
        v12 = 0;
        if ( (_WORD)v3 == 447 )
          v12 = 512;
        v13 = 0;
        v14 = (*(_DWORD *)(v5 + 4) | v12) & 0xFFFFFEFF;
        if ( (_WORD)v3 != 447 )
          v13 = 256;
        *(_DWORD *)(v5 + 4) = v13 | v14;
        v15 = *((_QWORD *)v2 + 7);
        v16 = *(_DWORD *)(v15 + 192);
        if ( (v16 & 1) == 0 )
        {
          *(_DWORD *)(v15 + 192) = v16 | ((v16 & 1) == 0);
          if ( (v16 & 0x61086013 | ((v16 & 1) == 0)) == ((v16 & 1) == 0) )
          {
            CTxtEdit::OnSetTypographyOptions((CTxtEdit *)v15, 1u, 1);
            CTxtEdit::ItemizeDoc((CTxtEdit *)v15, v17, v18);
            v19 = *(_QWORD *)(v15 + 80);
            if ( v19 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 64LL))(v19);
            v20 = *(_QWORD *)(v15 + 88);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 64LL))(v20);
            *(_DWORD *)(v15 + 180) ^= (*(_DWORD *)(v15 + 180) ^ (*(_DWORD *)(v15 + 192) << 22)) & 0x400000;
          }
        }
        break;
      default:
        switch ( *((_WORD *)v2 + 66) )
        {
          case 0x100:
            goto LABEL_446;
          case 0x105:
            *((_WORD *)v2 + 357) = 0;
            CRTFRead::HandleStartGroup(v2);
            v110 = *((_WORD *)v2 + 236);
            if ( (v110 & 0x200) == 0 )
              return *((unsigned int *)v2 + 12);
            v5 = *((_QWORD *)v2 + 27);
            *((_WORD *)v2 + 236) = v110 & 0xFDFF;
            goto LABEL_125;
          case 0x106:
            *((_WORD *)v2 + 357) = 0;
            CRTFRead::HandleFieldEndGroup(v2);
            CRTFRead::HandleEndGroup(v2);
            return *((unsigned int *)v2 + 12);
          case 0x107:
            v114 = CRTFRead::ObjectReadFromEditStream(v2);
            *((_WORD *)v2 + 236) &= ~1u;
            *((_WORD *)v2 + 236) |= v114 == 0;
            goto LABEL_424;
          case 0x108:
            CRTFRead::StaticObjectReadFromEditStream(v2, 0);
LABEL_424:
            if ( (unsigned int)CRTFRead::SkipToEndOfGroup(v2) )
              return *((unsigned int *)v2 + 12);
            goto LABEL_33;
          case 0x109:
            *((_WORD *)v2 + 41) = 0;
            *((_DWORD *)v2 + 20) |= 0xFDE90020;
            if ( *(_DWORD *)(v5 + 12) != 65001 )
              *(_DWORD *)(v5 + 12) = 65001;
            goto LABEL_125;
          case 0x10A:
            *((_DWORD *)v2 + 20) |= 0x800u;
            goto LABEL_125;
          case 0x10B:
LABEL_125:
            *(_WORD *)(v5 + 10) = 0;
            CRTFRead::InitDefaultFont(v2);
            *(_WORD *)(v5 + 16) = 1;
            return *((unsigned int *)v2 + 12);
          case 0x10C:
            *((_BYTE *)v2 + 124) = 0;
            return *((unsigned int *)v2 + 12);
          case 0x10D:
            if ( (*((_BYTE *)v2 + 80) & 0x20) == 0 )
            {
              *((_DWORD *)v2 + 147) = v4;
              if ( *(_DWORD *)(v5 + 12) != 65001 )
                *(_DWORD *)(v5 + 12) = v4;
            }
            return *((unsigned int *)v2 + 12);
          case 0x10E:
            v54 = *((_DWORD *)v2 + 20);
            if ( (v54 & 0x8000) == 0 && (v54 & 0xFFFF0020) == 0xFDE90020 )
              CTxtEdit::SetViewKind(*((CTxtEdit **)v2 + 7), v4);
            return *((unsigned int *)v2 + 12);
          case 0x10F:
            if ( (*((_DWORD *)v2 + 20) & 0xA000) == 0x2000 )
              CTxtEdit::SetViewScale(*((CTxtEdit **)v2 + 7), v4);
            return *((unsigned int *)v2 + 12);
          case 0x110:
            if ( v4 < 0 )
              return *((unsigned int *)v2 + 12);
            if ( !*((_DWORD *)v2 + 2) && !CArrayBase::ArAdd(v2, 1, 0) )
              goto LABEL_460;
            *((_WORD *)v2 + 238) = v4;
            *(_WORD *)CArrayBase::Elem(v2, 0) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x111:
            if ( v4 < 0 || *((_DWORD *)v2 + 2) != 1 )
              return *((unsigned int *)v2 + 12);
            if ( !CArrayBase::ArAdd(v2, 1, 0) )
              goto LABEL_460;
            *((_WORD *)v2 + 239) = v4;
            *(_WORD *)CArrayBase::Elem(v2, 1) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x112:
            *((_WORD *)v2 + 240) = v4;
            if ( !*(_WORD *)v5 )
              *(_WORD *)v5 = v4;
            return *((unsigned int *)v2 + 12);
          case 0x113:
            *((_WORD *)v2 + 241) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x114:
            *((_WORD *)v2 + 242) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x115:
            v104 = *(__int16 *)(v5 + 10);
            if ( (unsigned int)(v104 - 1) > 7 )
            {
              if ( v104 != 13 )
              {
LABEL_358:
                v105 = *((_BYTE *)v2 + 279);
                *(_OWORD *)((char *)v2 + 244) = 0;
                *(_OWORD *)((char *)v2 + 260) = 0;
                *(_OWORD *)((char *)v2 + 276) = 0;
                *(_QWORD *)((char *)v2 + 292) = 0;
                *((_BYTE *)v2 + 260) = 1;
                *((_WORD *)v2 + 138) = -1;
                v51 = *((_BYTE *)v2 + 474) == 2;
                *((_BYTE *)v2 + 279) = 1;
                *((_WORD *)v2 + 131) = -1;
                *((_WORD *)v2 + 123) = v51;
                *(_DWORD *)(v5 + 4) &= 0xFFFFFFFC;
                *(_WORD *)(v5 + 8) = 0;
                *((_DWORD *)v2 + 76) = 0;
                *((_WORD *)v2 + 358) = 0;
                *((_BYTE *)v2 + 718) = 0;
                *((_BYTE *)v2 + 279) = v105 | 1;
                *((_DWORD *)v2 + 75) = -671089153;
                if ( *((_WORD *)v2 + 66) == 432 )
                  *((_DWORD *)v2 + 75) = 1476394472;
              }
            }
            else
            {
              *((_DWORD *)v2 + 12) = 14;
            }
            return *((unsigned int *)v2 + 12);
          case 0x116:
            CRTFRead::SetPlain(v2, *((struct STATE **)v2 + 27));
            return *((unsigned int *)v2 + 12);
          case 0x117:
            *(_WORD *)(v5 + 10) = 2;
            *(_DWORD *)(v5 + 20) = -1;
            return *((unsigned int *)v2 + 12);
          case 0x118:
            goto LABEL_8;
          case 0x119:
            v21 = *(_DWORD *)(v5 + 4);
            if ( (v21 & 0x300) != 0 )
            {
              v22 = *((_DWORD *)v2 + 2);
              if ( v22 > 0 && (v23 = *(__int16 **)v2) != 0 || (v23 = 0, v22) )
              {
                while ( 1 )
                {
                  --v22;
                  if ( v4 == *v23 )
                    break;
                  v23 += 38;
                  if ( !v22 )
                    goto LABEL_53;
                }
              }
              else
              {
LABEL_53:
                --v22;
              }
              if ( v22 < 0 )
                return *((unsigned int *)v2 + 12);
              v6 = *((unsigned __int8 *)v23 + 2);
            }
            else
            {
              if ( *((_WORD *)v2 + 239) == 0xFFFF || (v21 & 0x400) == 0 )
                return *((unsigned int *)v2 + 12);
LABEL_8:
              if ( v4 == -1 )
                goto LABEL_29;
              *(_DWORD *)(v5 + 4) &= ~0x400u;
              if ( *(_WORD *)(v5 + 10) == 2 )
              {
                v26 = *((__int16 *)v2 + 238);
                v27 = 0;
                LODWORD(lpMem) = 0;
                if ( v4 == v26 )
                {
                  *((_WORD *)v2 + 236) |= 0x20u;
                }
                else if ( v4 == *((__int16 *)v2 + 239) )
                {
                  v27 = 1;
                }
                else
                {
                  if ( !CArrayBase::ArAdd(v2, 1, (int *)&lpMem) )
                  {
LABEL_460:
                    CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)v2 + 7) + 144LL));
                    goto LABEL_461;
                  }
                  v27 = (int)lpMem;
                }
                *(_DWORD *)(v5 + 20) = v27;
                if ( v27 >= 0 )
                {
                  v28 = CArrayBase::Elem(v2, v27);
                  if ( v28 )
                  {
                    *v28 = v4;
                    v28[3] = 0;
                    v28[1] = 1;
                    *((_DWORD *)v28 + 18) = 0xFFFF;
                  }
                }
                return *((unsigned int *)v2 + 12);
              }
              if ( !*((_DWORD *)v2 + 2) )
                return *((unsigned int *)v2 + 12);
              v6 = *((unsigned __int8 *)CRTFRead::SelectCurrentFont(v2, v4) + 2);
            }
            if ( (unsigned int)(v6 - 177) <= 1 )
              *((_BYTE *)v2 + 720) = v6;
            return *((unsigned int *)v2 + 12);
          case 0x11A:
          case 0x11B:
          case 0x11C:
          case 0x11D:
          case 0x11E:
          case 0x11F:
          case 0x120:
          case 0x121:
            v55 = CRTFRead::GetStateFont(v2, *((struct STATE **)v2 + 27));
            if ( v55 )
            {
              *((_BYTE *)v55 + 3) &= 0xFu;
              *((_BYTE *)v55 + 3) |= 16 * (v56 + 6);
              if ( *((_WORD *)v2 + 66) == 288 && *((_BYTE *)v55 + 2) == 1 )
                *((_BYTE *)v55 + 2) = 2;
            }
            return *((unsigned int *)v2 + 12);
          case 0x122:
            v58 = CRTFRead::GetStateFont(v2, *((struct STATE **)v2 + 27));
            if ( !v58 )
              return *((unsigned int *)v2 + 12);
            *((_BYTE *)v58 + 2) = v4;
            CodePage = CW32System::GetCodePage(v4);
            v47 = 65001;
            v46[36] = CodePage;
            if ( *(_DWORD *)(v5 + 12) == 65001 || (v47 = CodePage, *(_DWORD *)(v5 + 12) = CodePage, CodePage != 42) )
            {
              if ( *((_DWORD *)v2 + 147) == -1 )
                *((_DWORD *)v2 + 147) = v47;
            }
            if ( (unsigned int)(unsigned __int8)v4 - 177 > 1 )
              goto LABEL_74;
            v59 = *((_WORD *)v2 + 239);
            v60 = *v46;
            if ( v59 == -1 )
              goto LABEL_76;
            if ( v59 == v60 )
              goto LABEL_77;
            v61 = CArrayBase::Elem(v2, 0);
            if ( !v62 )
              goto LABEL_190;
            while ( 1 )
            {
              --v62;
              if ( v63 == *v61 )
                break;
              v61 += 38;
              if ( !v62 )
              {
LABEL_190:
                --v62;
                break;
              }
            }
            if ( v62 >= 0 && (unsigned int)*((unsigned __int8 *)v61 + 2) - 177 > 1 )
LABEL_76:
              *((_WORD *)v2 + 239) = v60;
LABEL_77:
            if ( (unsigned int)*((unsigned __int8 *)v2 + 720) - 177 > 1 )
              *((_BYTE *)v2 + 720) = v4;
LABEL_74:
            *((_WORD *)v2 + 236) |= 0x100u;
            return *((unsigned int *)v2 + 12);
          case 0x123:
            v57 = CRTFRead::GetStateFont(v2, *((struct STATE **)v2 + 27));
            if ( v57 )
            {
              *((_BYTE *)v57 + 3) &= 0xF0u;
              *((_BYTE *)v57 + 3) |= v4;
            }
            return *((unsigned int *)v2 + 12);
          case 0x124:
            *(_WORD *)(v5 + 10) = 14;
            return *((unsigned int *)v2 + 12);
          case 0x125:
            if ( *(_DWORD *)(v5 + 12) != 65001 )
              *(_DWORD *)(v5 + 12) = v4;
            v42 = CRTFRead::GetStateFont(v2, (struct STATE *)v5);
            if ( *(_WORD *)(v5 + 10) == 2 )
            {
              if ( v42 )
              {
                *((_WORD *)v42 + 36) = v4;
                CharSet = CW32System::GetCharSet(v4, 0);
                *(_BYTE *)(v44 + 2) = CharSet;
                if ( *((_DWORD *)v2 + 147) == -1 )
                  *((_DWORD *)v2 + 147) = v4;
              }
            }
            return *((unsigned int *)v2 + 12);
          case 0x126:
            *((_DWORD *)v2 + 59) |= 0x80000000;
            *((_WORD *)v2 + 46) = 10 * v4;
            return *((unsigned int *)v2 + 12);
          case 0x127:
            *(_WORD *)(v5 + 10) = 1;
            *((_WORD *)v2 + 236) &= ~8u;
            return *((unsigned int *)v2 + 12);
          case 0x128:
            *((_DWORD *)v2 + 26) = CRTFRead::GetColor(v2, 0x4000000u);
            return *((unsigned int *)v2 + 12);
          case 0x129:
            Color = CRTFRead::GetColor(v2, 0x40000000u);
            v67 = *((_QWORD *)v2 + 27);
            *((_DWORD *)v2 + 24) = Color;
            if ( (*(_BYTE *)(v67 + 4) & 1) != 0 && Color == 0xFFFFFF )
              *((_DWORD *)v2 + 24) = 0;
            return *((unsigned int *)v2 + 12);
          case 0x12A:
            *(_BYTE *)(v5 + 24) = v4;
            *((_WORD *)v2 + 236) |= 8u;
            return *((unsigned int *)v2 + 12);
          case 0x12B:
            *(_BYTE *)(v5 + 25) = v4;
            *((_WORD *)v2 + 236) |= 8u;
            return *((unsigned int *)v2 + 12);
          case 0x12C:
            *(_BYTE *)(v5 + 26) = v4;
            *((_WORD *)v2 + 236) |= 8u;
            return *((unsigned int *)v2 + 12);
          case 0x12D:
          case 0x12E:
          case 0x130:
          case 0x131:
          case 0x132:
          case 0x133:
          case 0x134:
          case 0x135:
          case 0x136:
          case 0x137:
          case 0x138:
          case 0x139:
          case 0x13A:
          case 0x13B:
            goto LABEL_234;
          case 0x12F:
            v72 = 1;
            goto LABEL_233;
          case 0x13C:
            v73 = 0x200000;
            *((_DWORD *)v2 + 60) = 0x200000;
            goto LABEL_235;
          case 0x13D:
            *((_DWORD *)v2 + 21) &= ~4u;
            *((_DWORD *)v2 + 59) |= 4u;
            return *((unsigned int *)v2 + 12);
          case 0x13E:
          case 0x13F:
          case 0x140:
          case 0x141:
          case 0x142:
          case 0x143:
          case 0x144:
          case 0x145:
          case 0x146:
            *((_WORD *)v2 + 66) = 303;
            v72 = v3 - 60;
LABEL_233:
            *((_BYTE *)v2 + 116) = v72;
            *((_DWORD *)v2 + 59) |= 0x800000u;
LABEL_234:
            v73 = 1 << (*((_WORD *)v2 + 66) - 45);
            *((_DWORD *)v2 + 59) |= v73;
LABEL_235:
            *((_DWORD *)v2 + 21) &= ~v73;
            if ( !*((_BYTE *)v2 + 144) || v4 )
              *((_DWORD *)v2 + 21) |= v73;
            return *((unsigned int *)v2 + 12);
          case 0x147:
            v74 = -10;
            goto LABEL_244;
          case 0x148:
            v74 = 10;
LABEL_244:
            if ( !*((_BYTE *)v2 + 144) )
              LOWORD(v4) = 6;
            *((_DWORD *)v2 + 59) |= 0x10000000u;
            *((_WORD *)v2 + 47) = v74 * v4;
            return *((unsigned int *)v2 + 12);
          case 0x149:
            v75 = 0x10000;
            goto LABEL_250;
          case 0x14A:
            v75 = 0;
            goto LABEL_250;
          case 0x14B:
            v75 = 0x20000;
LABEL_250:
            *((_DWORD *)v2 + 59) |= 0x30000u;
            *((_DWORD *)v2 + 21) &= 0xFFFCFFFF;
            *((_DWORD *)v2 + 21) |= v75;
            return *((unsigned int *)v2 + 12);
          case 0x14C:
            *((_DWORD *)v2 + 59) |= 0x40000u;
            *((_BYTE *)v2 + 117) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x14D:
            *((_WORD *)v2 + 51) = v4;
            *((_DWORD *)v2 + 59) |= 0x200000u;
            return *((unsigned int *)v2 + 12);
          case 0x14E:
            *((_DWORD *)v2 + 59) |= 0x100000u;
            *((_WORD *)v2 + 57) = 10 * v4;
            return *((unsigned int *)v2 + 12);
          case 0x14F:
            *(_DWORD *)(v5 + 4) |= 8u;
            *(_WORD *)v5 = v4;
            *((_DWORD *)v2 + 27) = (unsigned __int16)v4;
            if ( (unsigned int)CW32System::IsBiDiLcid((unsigned __int16)v4) )
            {
              v65 = CW32System::ConvertLanguageIDtoCodePage(v64);
              *((_BYTE *)v2 + 720) = CW32System::GetCharSet(v65, 0);
            }
            *((_DWORD *)v2 + 59) |= 0x2000000u;
            return *((unsigned int *)v2 + 12);
          case 0x150:
            if ( *(_WORD *)(v5 + 10) == 19 )
              goto LABEL_29;
            return *((unsigned int *)v2 + 12);
          case 0x151:
          case 0x152:
            goto LABEL_69;
          case 0x153:
            *((_DWORD *)v2 + 62) += v4 + *((_DWORD *)v2 + 64);
            *((_DWORD *)v2 + 75) |= 5u;
            *((_DWORD *)v2 + 64) = -v4;
            return *((unsigned int *)v2 + 12);
          case 0x154:
          case 0x155:
            v24 = *((_DWORD *)v2 + 75);
            if ( (*((_WORD *)v2 + 123) & 1) == ((_WORD)v3 == 340) )
            {
              *((_DWORD *)v2 + 63) = v4;
              v25 = v24 | 2;
            }
            else
            {
              *((_DWORD *)v2 + 62) = v4 - *((_DWORD *)v2 + 64);
              v25 = v24 | 1;
            }
            *((_DWORD *)v2 + 75) = v25;
            return *((unsigned int *)v2 + 12);
          case 0x156:
          case 0x157:
          case 0x158:
          case 0x159:
            if ( (*(_BYTE *)(v5 + 4) & 1) == 0 )
            {
              *((_DWORD *)v2 + 75) |= 8u;
              *((_BYTE *)v2 + 260) = v3 - 85;
            }
            return *((unsigned int *)v2 + 12);
          case 0x15A:
            *((_DWORD *)v2 + 75) |= 0x40u;
            *((_DWORD *)v2 + 66) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x15B:
            *((_DWORD *)v2 + 75) |= 0x80u;
            *((_DWORD *)v2 + 67) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x15C:
            if ( v4 >= 0 )
            {
              *((_DWORD *)v2 + 68) = v4;
              if ( !v4 || v4 == 1000 )
              {
                v29 = 0;
LABEL_82:
                *((_DWORD *)v2 + 75) |= 0x100u;
                *((_BYTE *)v2 + 278) = v29;
                return *((unsigned int *)v2 + 12);
              }
            }
            else
            {
              *((_DWORD *)v2 + 68) = -v4;
            }
            v29 = (v4 <= 0) + 3;
            goto LABEL_82;
          case 0x15D:
            if ( v4 )
            {
              *((_BYTE *)v2 + 278) = 5;
              v79 = *((_DWORD *)v2 + 68) / 12;
              *((_DWORD *)v2 + 75) |= 0x100u;
              *((_DWORD *)v2 + 68) = v79;
            }
            return *((unsigned int *)v2 + 12);
          case 0x15E:
            if ( *((_BYTE *)v2 + 278) == 4 )
              *((_BYTE *)v2 + 278) = 3;
            return *((unsigned int *)v2 + 12);
          case 0x15F:
            *((_WORD *)v2 + 83) = v4;
            if ( *(_WORD *)(v5 + 10) == 19 )
              return *((unsigned int *)v2 + 12);
            *((_BYTE *)v2 + 279) |= 1u;
            v80 = 0;
            *((_WORD *)v2 + 138) = -1;
            while ( v4 != *((unsigned __int8 *)v2 + v80 + 156) )
            {
              v80 = (unsigned int)(v80 + 1);
              if ( (int)v80 >= 10 )
                goto LABEL_277;
            }
            *((_BYTE *)v2 + 279) = 2 * v80 - 2;
            *((_WORD *)v2 + 138) = ~(_WORD)v80;
LABEL_277:
            *((_DWORD *)v2 + 75) |= 0xD7FFFDFF;
            return *((unsigned int *)v2 + 12);
          case 0x160:
            *((_WORD *)v2 + 123) &= ~1u;
            v78 = 0x10000;
            goto LABEL_302;
          case 0x161:
            *((_BYTE *)v2 + 718) = 0;
            *((_WORD *)v2 + 123) |= 0x400u;
            *((_DWORD *)v2 + 75) |= 0x4000000u;
            return *((unsigned int *)v2 + 12);
          case 0x162:
          case 0x163:
          case 0x164:
          case 0x165:
          case 0x166:
          case 0x167:
          case 0x168:
          case 0x169:
          case 0x16A:
            v77 = 1 << (v3 - 98);
            *((_WORD *)v2 + 123) |= v77;
            v78 = v77 << 16;
            goto LABEL_302;
          case 0x16B:
          case 0x16C:
          case 0x16D:
          case 0x16E:
          case 0x16F:
          case 0x170:
          case 0x171:
          case 0x172:
            *((_BYTE *)v2 + 718) = v3 - 107;
            return *((unsigned int *)v2 + 12);
          case 0x173:
          case 0x174:
          case 0x175:
            *((_DWORD *)v2 + 74) |= 1 << (v3 - 95);
            *((_DWORD *)v2 + 113) = *((_DWORD *)v2 + 74);
            return *((unsigned int *)v2 + 12);
          case 0x176:
          case 0x177:
          case 0x178:
          case 0x179:
          case 0x17A:
          case 0x17B:
          case 0x17C:
          case 0x17D:
            v81 = *((_BYTE *)v2 + 718);
            if ( v81 < 4u )
            {
              v82 = 15;
              if ( (int)v3 - 374 < 15 )
                v82 = v3 - 374;
              v83 = 4 * v81;
              if ( v82 <= 0 )
                LOWORD(v82) = 0;
              *((_WORD *)v2 + 147) = *((_WORD *)v2 + 147) & ~(15 << v83) | ((_WORD)v82 << v83);
              *((_DWORD *)v2 + 75) |= 0x800u;
            }
            return *((unsigned int *)v2 + 12);
          case 0x17E:
            if ( *((_BYTE *)v2 + 718) < 4u )
            {
              StandardColorIndex = CRTFRead::GetStandardColorIndex(v2);
              v86 = *((_DWORD *)v2 + 74) & ~(31 << v85) | (StandardColorIndex << v85);
              *((_DWORD *)v2 + 74) = v86;
              *((_DWORD *)v2 + 113) = v86;
            }
            return *((unsigned int *)v2 + 12);
          case 0x17F:
            v87 = *((_BYTE *)v2 + 718);
            if ( v87 >= 4u )
            {
              v31 = v4 + 10;
              if ( v31 < 40 )
              {
                LOBYTE(v32) = 1;
              }
              else
              {
                v32 = v31 / 20;
                if ( v31 / 20 >= 3 )
                  LOBYTE(v32) = 3;
              }
              *((_BYTE *)v2 + 719) |= (_BYTE)v32 << (2 * v87 - 8);
            }
            else
            {
              if ( (unsigned int)(v4 - 1) > 3 )
              {
                v30 = (v4 + 5) / 10;
                if ( v30 >= 15 )
                  v30 = 15;
              }
              else
              {
                v30 = 1;
              }
              if ( v30 <= 0 )
                LOWORD(v30) = 0;
              *((_WORD *)v2 + 146) = *((_WORD *)v2 + 146) & ~(15 << (4 * v87)) | ((_WORD)v30 << (4 * v87));
              *((_DWORD *)v2 + 75) |= 0x800u;
            }
            return *((unsigned int *)v2 + 12);
          case 0x180:
            v88 = *((_BYTE *)v2 + 718);
            if ( v88 < 4u )
            {
              if ( v4 >= 300 )
                v33 = 15;
              else
                v33 = v4 / 20;
              v34 = 4 * v88;
              if ( v33 <= 0 )
                LOWORD(v33) = 0;
              *((_WORD *)v2 + 145) = *((_WORD *)v2 + 145) & ~(15 << v34) | ((_WORD)v33 << v34);
              *((_DWORD *)v2 + 75) |= 0x800u;
            }
            return *((unsigned int *)v2 + 12);
          case 0x181:
            v89 = (unsigned __int16)CRTFRead::GetStandardColorIndex(v2) << 11;
            v90 = 2047;
            goto LABEL_300;
          case 0x182:
            v89 = (unsigned __int16)CRTFRead::GetStandardColorIndex(v2) << 6;
            v90 = -1985;
LABEL_300:
            *((_WORD *)v2 + 141) = v90 & *((_WORD *)v2 + 141) | v89;
            goto LABEL_301;
          case 0x183:
            *((_WORD *)v2 + 140) = v4;
            *((_DWORD *)v2 + 75) |= 0x1000u;
            return *((unsigned int *)v2 + 12);
          case 0x184:
          case 0x185:
          case 0x186:
          case 0x187:
          case 0x188:
          case 0x189:
          case 0x18A:
          case 0x18B:
          case 0x18C:
          case 0x18D:
          case 0x18E:
          case 0x18F:
            *((_WORD *)v2 + 141) &= 0xFFC0u;
            *((_WORD *)v2 + 141) |= (_WORD)v3 - 387;
LABEL_301:
            v78 = 4096;
LABEL_302:
            *((_DWORD *)v2 + 75) |= v78;
            return *((unsigned int *)v2 + 12);
          case 0x190:
            goto LABEL_253;
          case 0x191:
            *((_BYTE *)v2 + 716) = 4;
LABEL_253:
            if ( (*(_BYTE *)(v5 + 4) & 1) == 0 )
            {
              v76 = *((int *)v2 + 76);
              if ( (unsigned int)v76 <= 0x1F && (unsigned int)v4 < 0x1000000 )
              {
                *((_DWORD *)v2 + v76 + 80) = (v4 & 0xFFFFFF)
                                           + ((*((unsigned __int8 *)v2 + 716) + 16 * *((unsigned __int8 *)v2 + 717)) << 24);
                ++*((_DWORD *)v2 + 76);
              }
              *((_DWORD *)v2 + 75) |= 0x10u;
            }
            *((_WORD *)v2 + 358) = 0;
            return *((unsigned int *)v2 + 12);
          case 0x192:
          case 0x193:
          case 0x194:
          case 0x195:
          case 0x196:
            *((_BYTE *)v2 + 717) = v3 + 111;
            return *((unsigned int *)v2 + 12);
          case 0x197:
          case 0x198:
          case 0x199:
            *((_BYTE *)v2 + 716) = v3 + 106;
            return *((unsigned int *)v2 + 12);
          case 0x19A:
            *(_DWORD *)(v5 + 4) &= ~2u;
            *(_WORD *)(v5 + 10) = 12;
            *((_DWORD *)v2 + 75) |= 0x8000u;
            *((_WORD *)v2 + 142) = 1;
            return *((unsigned int *)v2 + 12);
          case 0x19B:
            if ( *(_WORD *)(v5 + 10) == 12 )
              *(_WORD *)(v5 + 8) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x19C:
            *((_WORD *)v2 + 66) = 417;
            *((_WORD *)v2 + 356) = 0;
            goto LABEL_314;
          case 0x19D:
            CRunPtrBase::AdjustBackward((CRunPtrBase *)(*((_QWORD *)v2 + 8) + 72LL));
            PF = CRchTxtPtr::GetPF((CRchTxtPtr *)(*((_QWORD *)v2 + 8) + 8LL));
            v92 = (CRunPtrBase *)(*((_QWORD *)v2 + 8) + 72LL);
            *((_WORD *)v2 + 122) = *(_WORD *)PF;
            CRunPtrBase::AdjustForward(v92);
            *((_DWORD *)v2 + 75) |= 0x20u;
            *((_WORD *)v2 + 356) = 1024;
            *(_DWORD *)(v5 + 4) |= 2u;
            return *((unsigned int *)v2 + 12);
          case 0x19E:
          case 0x19F:
            *((_WORD *)v2 + 356) &= 0xFFFCu;
            *((_WORD *)v2 + 356) |= (_WORD)v3 - 413;
            return *((unsigned int *)v2 + 12);
          case 0x1A0:
            *((_WORD *)v2 + 356) = 0;
            goto LABEL_314;
          case 0x1A1:
          case 0x1A2:
          case 0x1A3:
          case 0x1A4:
          case 0x1A5:
            if ( *((_WORD *)v2 + 122) != 1 || (*(_BYTE *)(v5 + 4) & 2) == 0 )
            {
LABEL_314:
              if ( *(_WORD *)(v5 + 10) == 12 )
              {
                v93 = *((_WORD *)v2 + 66);
                *((_DWORD *)v2 + 75) |= 0x20u;
                *((_WORD *)v2 + 122) = v93 - 415;
                *(_DWORD *)(v5 + 4) |= 2u;
              }
            }
            return *((unsigned int *)v2 + 12);
          case 0x1A6:
            *((_DWORD *)v2 + 148) = 0;
            *(_WORD *)(v5 + 10) = 13;
            return *((unsigned int *)v2 + 12);
          case 0x1A7:
            if ( *(_WORD *)(v5 + 10) == 12 )
            {
              *((_DWORD *)v2 + 75) |= 0x8000u;
              *((_WORD *)v2 + 142) = v4;
            }
            return *((unsigned int *)v2 + 12);
          case 0x1A8:
          case 0x1A9:
          case 0x1DA:
          case 0x1DB:
          case 0x1ED:
            goto LABEL_29;
          case 0x1AA:
            return *((unsigned int *)v2 + 12);
          case 0x1AB:
            if ( (unsigned __int16)(*(_WORD *)(v5 + 10) - 15) <= 2u || (*(_BYTE *)(v5 + 4) & 0x10) != 0 )
              goto LABEL_29;
            v106 = *(_DWORD *)(v5 + 12);
            *(_WORD *)(v5 + 10) = 9;
            *((_DWORD *)v2 + 134) = v106;
            *((_DWORD *)v2 + 137) = -1;
            *((_DWORD *)v2 + 138) = 1;
            return *((unsigned int *)v2 + 12);
          case 0x1AC:
            *(_DWORD *)(v5 + 4) &= ~0x10u;
            *(_DWORD *)(v5 + 4) |= 0x20u;
            if ( *((_DWORD *)v2 + 138) && (*((_BYTE *)v2 + 472) & 0x40) != 0 )
            {
              v48 = *((_DWORD *)v2 + 137);
              v49 = *((_OWORD *)v2 + 32);
              *(_OWORD *)((char *)v2 + 84) = *((_OWORD *)v2 + 31);
              v50 = *((_QWORD *)v2 + 66);
              *(_OWORD *)((char *)v2 + 100) = v49;
              *(_QWORD *)((char *)v2 + 116) = v50;
              *(_DWORD *)(v5 + 20) = v48;
              if ( *(_DWORD *)(v5 + 12) != 65001 )
                *(_DWORD *)(v5 + 12) = *((_DWORD *)v2 + 134);
              *((_DWORD *)v2 + 59) = *((_DWORD *)v2 + 135);
              *((_DWORD *)v2 + 60) = *((_DWORD *)v2 + 136);
            }
            v51 = (*((_BYTE *)v2 + 472) & 0x40) == 0;
            *((_DWORD *)v2 + 138) = 0;
            if ( v51 )
            {
              *(_WORD *)(v5 + 10) = 9;
              return *((unsigned int *)v2 + 12);
            }
            v107 = *((_QWORD *)v2 + 75);
            if ( !v107 )
              goto LABEL_145;
            v37 = 0;
            if ( *(_BYTE *)(v107 + 1) != 34 )
              goto LABEL_144;
            if ( *((unsigned __int8 *)v2 + 487) == 128
              || *((unsigned __int8 *)v2 + 487) == 129
              || *((unsigned __int8 *)v2 + 487) == 130
              || *((unsigned __int8 *)v2 + 487) == 134
              || *((unsigned __int8 *)v2 + 487) == 136 )
            {
              v35 = CW32System::GetCodePage(*((_BYTE *)v2 + 487));
            }
            else
            {
              v35 = 0;
            }
            v36 = CW32System::PvAlloc(*((_DWORD *)v2 + 153) + 1, 0x40u);
            v37 = v36;
            if ( !v36 )
              goto LABEL_461;
            v38 = (unsigned __int8 *)(v107 + 2);
            *v36 = 15392;
            TrailBytesCount = 0;
            v40 = (unsigned __int8 *)(v37 + 1);
            while ( 2 )
            {
              if ( TrailBytesCount || *v38 != 92 )
              {
                v41 = *v38;
                if ( *v38 == 34 )
                {
                  *v40 = 62;
                  break;
                }
                if ( v35 )
                {
                  if ( TrailBytesCount )
                    TrailBytesCount = 0;
                  else
                    TrailBytesCount = CW32System::GetTrailBytesCount(v41, v35);
                }
              }
              else
              {
                v41 = *++v38;
              }
              *v40 = v41;
              if ( v41 )
              {
                ++v38;
                ++v40;
                continue;
              }
              break;
            }
LABEL_144:
            CW32System::FreePv(*((void **)v2 + 75));
            v52 = *((_DWORD *)v2 + 153) + 1;
            *((_QWORD *)v2 + 75) = v37;
            *((_DWORD *)v2 + 152) = v52;
LABEL_145:
            *(_WORD *)(v5 + 10) = 10;
            *((_DWORD *)v2 + 157) = 0;
            if ( *((_QWORD *)v2 + 75) )
            {
              *((_DWORD *)v2 + 156) = 260;
              v53 = CW32System::PvAlloc(0x104u, 0);
              *((_QWORD *)v2 + 77) = v53;
              if ( v53 )
                *v53 = 0;
              else
LABEL_461:
                *((_DWORD *)v2 + 12) = 9;
            }
            else
            {
              v108 = (void *)*((_QWORD *)v2 + 77);
              *((_DWORD *)v2 + 156) = 0;
              CW32System::FreePv(v108);
              *((_QWORD *)v2 + 77) = 0;
              *((_WORD *)v2 + 236) &= ~0x40u;
            }
            return *((unsigned int *)v2 + 12);
          case 0x1AD:
            v109 = *(_DWORD *)(v5 + 4);
            if ( (v109 & 0x30) != 0 )
              goto LABEL_29;
            *(_WORD *)(v5 + 10) = 11;
            *(_DWORD *)(v5 + 4) = v109 | 0x10;
            return *((unsigned int *)v2 + 12);
          case 0x1AE:
            *(_WORD *)(v5 + 10) = 19;
            *((_WORD *)v2 + 83) = 0;
            return *((unsigned int *)v2 + 12);
          case 0x1AF:
          case 0x1B0:
            goto LABEL_358;
          case 0x1B1:
            *(_WORD *)(v5 + 10) = 17;
            return *((unsigned int *)v2 + 12);
          case 0x1B2:
            if ( (*((_WORD *)v2 + 236) & 0x400) != 0 )
              *((_DWORD *)v2 + 12) = 6;
            v94 = *((_WORD *)v2 + 230);
            v95 = *((_DWORD *)v2 + 75) | 0x10;
            if ( v94 )
            {
              v95 = *((_DWORD *)v2 + 75) | 0x810;
              *((_DWORD *)v2 + 74) = *((_DWORD *)v2 + 113);
              *((_WORD *)v2 + 147) = *((_WORD *)v2 + 228);
              *((_WORD *)v2 + 145) = *((_WORD *)v2 + 229);
              *((_WORD *)v2 + 146) = v94;
            }
            *((_BYTE *)v2 + 260) = *((_BYTE *)v2 + 486);
            *((_DWORD *)v2 + 62) = *((_DWORD *)v2 + 112);
            *((_DWORD *)v2 + 64) = *((_DWORD *)v2 + 77);
            *((_WORD *)v2 + 123) |= 0x4000u;
            *((_DWORD *)v2 + 75) = v95 | 0x4000000C;
            *(_DWORD *)(v5 + 4) |= 1u;
            return *((unsigned int *)v2 + 12);
          case 0x1B3:
            if ( (*((_WORD *)v2 + 236) & 0x400) != 0 )
              goto LABEL_343;
            if ( (*(_BYTE *)(v5 + 4) & 1) != 0 )
            {
              if ( (unsigned int)(*((_DWORD *)v2 + 78) - 1) <= 0x1E )
              {
                v96 = *((__int16 *)v2 + 231);
                if ( *((__int16 *)v2 + 231) >= 0 && v96 < *((_DWORD *)qword_1800A72C0 + 2) )
                {
                  v97 = CArrayBase::Elem(qword_1800A72C0, v96);
                  if ( v97 )
                  {
                    v98 = *(_DWORD *)v97;
                    for ( *((_DWORD *)v2 + 78) = *(_DWORD *)v97;
                          v98;
                          *((_DWORD *)v2 + v98 + 80) = *(_DWORD *)(v97[1] + 4LL * v98) )
                    {
                      --v98;
                    }
                  }
                }
              }
              v99 = *((_DWORD *)v2 + 79);
              if ( v99 < *((_DWORD *)v2 + 78) )
              {
                *((_DWORD *)v2 + 79) = v99 + 1;
                CRTFRead::HandleChar(v2, 9u);
              }
            }
            return *((unsigned int *)v2 + 12);
          case 0x1B4:
            *((_DWORD *)v2 + 77) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1B5:
            v100 = *((int *)v2 + 78);
            if ( (unsigned int)v100 <= 0x1F )
            {
              if ( !(_DWORD)v100 )
              {
                *((_WORD *)v2 + 228) = *((_WORD *)v2 + 147);
                *((_WORD *)v2 + 229) = *((_WORD *)v2 + 145);
                *((_WORD *)v2 + 230) = *((_WORD *)v2 + 146);
              }
              *((_DWORD *)v2 + v100 + 80) = v4 + (*((unsigned __int8 *)v2 + 719) << 24);
              ++*((_DWORD *)v2 + 78);
              *((_BYTE *)v2 + 719) = 0;
            }
            return *((unsigned int *)v2 + 12);
          case 0x1B6:
            if ( *((_DWORD *)v2 + 79) < *((_DWORD *)v2 + 78) )
            {
              do
              {
                CRTFRead::HandleChar(v2, 9u);
                v103 = *((_DWORD *)v2 + 79) + 1;
                *((_DWORD *)v2 + 79) = v103;
              }
              while ( v103 < *((_DWORD *)v2 + 78) );
            }
            *((_DWORD *)v2 + 79) = 0;
            CRTFRead::HandleEndOfPara(v2);
            return *((unsigned int *)v2 + 12);
          case 0x1B7:
            if ( (*((_WORD *)v2 + 236) & 0x400) != 0 )
            {
LABEL_343:
              *((_DWORD *)v2 + 12) = 6;
            }
            else
            {
              v101 = *((_DWORD *)v2 + 172);
              if ( v101 == *(_DWORD *)(*((_QWORD *)v2 + 8) + 40LL)
                && *((_DWORD *)v2 + 58) != v101
                && !((*(_DWORD *)(*((_QWORD *)v2 + 7) + 180LL) & 0x80000) != 0
                   ? CRTFRead::HandleText(v2, (char *)byte_18009B3E1, 1, -1)
                   : (unsigned int)CRTFRead::HandleChar(v2, 0xDu)) )
              {
                *((_DWORD *)v2 + 58) = *(_DWORD *)(*((_QWORD *)v2 + 8) + 40LL);
              }
              *(_QWORD *)((char *)v2 + 308) = 0;
              *((_QWORD *)v2 + 56) = 0;
              *((_BYTE *)v2 + 719) = 0;
              *((_DWORD *)v2 + 115) = -65536;
              *((_BYTE *)v2 + 486) = 1;
            }
            return *((unsigned int *)v2 + 12);
          case 0x1B8:
            *((_DWORD *)v2 + 112) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1B9:
          case 0x1BA:
            *((_BYTE *)v2 + 486) = v3 + 73;
            return *((unsigned int *)v2 + 12);
          case 0x1BC:
            if ( (unsigned int)v4 <= 2 )
              *(_WORD *)(v5 + 16) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1BF:
            goto LABEL_34;
          case 0x1C0:
            *((_BYTE *)v2 + 474) = 1;
            return *((unsigned int *)v2 + 12);
          case 0x1C3:
            *((_BYTE *)v2 + 474) = 2;
            return *((unsigned int *)v2 + 12);
          case 0x1C7:
            *(_DWORD *)(v5 + 4) |= 0x400u;
            return *((unsigned int *)v2 + 12);
          case 0x1C8:
            *(_WORD *)(v5 + 10) = 15;
            p_lpMem = &lpMem;
            v51 = (*((_DWORD *)v2 + 20) & 0x8000) == 0;
            lpMem = 0;
            if ( !v51 )
              p_lpMem = 0;
            if ( !(unsigned int)CRTFRead::ReadRawText(v2, (char **)p_lpMem) )
              goto LABEL_228;
            v69 = lpMem;
            if ( !lpMem )
              return *((unsigned int *)v2 + 12);
            v70 = CTxtEdit::SetFollowingPunct(*((CTxtEdit **)v2 + 7), (char *)lpMem);
            goto LABEL_226;
          case 0x1C9:
            *(_WORD *)(v5 + 10) = 16;
            v71 = &lpMem;
            v51 = (*((_DWORD *)v2 + 20) & 0x8000) == 0;
            lpMem = 0;
            if ( !v51 )
              v71 = 0;
            if ( (unsigned int)CRTFRead::ReadRawText(v2, (char **)v71) )
            {
              v69 = lpMem;
              if ( lpMem )
              {
                v70 = CTxtEdit::SetLeadingPunct(*((CTxtEdit **)v2 + 7), (char *)lpMem);
LABEL_226:
                if ( v70 )
                  CW32System::FreePv(v69);
              }
            }
            else
            {
LABEL_228:
              if ( lpMem )
                CW32System::FreePv(lpMem);
            }
            return *((unsigned int *)v2 + 12);
          case 0x1CA:
            goto LABEL_387;
          case 0x1CB:
            *((_WORD *)v2 + 236) |= 1u;
LABEL_387:
            v111 = 8;
            if ( (_WORD)v3 != 458 )
              v111 = 4;
            *(_WORD *)(v5 + 10) = v111;
            CRTFRead::FreeRtfObject(v2);
            v112 = CW32System::PvAlloc(0x60u, 0x40u);
            *((_QWORD *)v2 + 79) = v112;
            if ( !v112 )
              goto LABEL_460;
            v112[7] = 100;
            *(_DWORD *)(*((_QWORD *)v2 + 79) + 24LL) = 100;
            *(_WORD *)(*((_QWORD *)v2 + 79) + 4LL) = 1;
            *(_WORD *)(*((_QWORD *)v2 + 79) + 6LL) = 1;
            *(_QWORD *)(*((_QWORD *)v2 + 79) + 56LL) = 0;
            *(_QWORD *)(*((_QWORD *)v2 + 79) + 64LL) = 0;
            **((_WORD **)v2 + 79) = -1;
            return *((unsigned int *)v2 + 12);
          case 0x1CC:
          case 0x1CD:
          case 0x1CE:
          case 0x1CF:
            *(_DWORD *)(*((_QWORD *)v2 + 79) + 4 * v3 - 1804) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D0:
            *(_DWORD *)(*((_QWORD *)v2 + 79) + 20LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D1:
            *(_DWORD *)(*((_QWORD *)v2 + 79) + 16LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D2:
            *(_DWORD *)(*((_QWORD *)v2 + 79) + 24LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D3:
            *(_DWORD *)(*((_QWORD *)v2 + 79) + 28LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D4:
            *(_WORD *)(*((_QWORD *)v2 + 79) + 34LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D5:
            *(_WORD *)(*((_QWORD *)v2 + 79) + 32LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D6:
          case 0x1D7:
          case 0x1D8:
            **((_WORD **)v2 + 79) = v3 - 470;
            *(_WORD *)(*((_QWORD *)v2 + 79) + 2LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1D9:
            if ( v4 >= 0 )
            {
              if ( (_WORD)v1 )
              {
                *((_WORD *)v2 + 357) = v1 - 1;
                CRTFRead::SkipBinaryData(v2, v4);
              }
              else
              {
                **((_QWORD **)v2 + 80) = RTFGetBinaryDataFromStream;
                *((_DWORD *)v2 + 42) = v4;
                if ( *(_WORD *)(v5 + 10) == 7 )
                {
                  v113 = CRTFRead::ObjectReadFromEditStream(v2);
                  *((_WORD *)v2 + 236) &= ~1u;
                  *((_WORD *)v2 + 236) |= v113 == 0;
                }
                else if ( *(_WORD *)(v5 + 10) == 8 )
                {
                  CRTFRead::StaticObjectReadFromEditStream(v2, v4);
                }
                **((_QWORD **)v2 + 80) = RTFGetFromStream;
              }
            }
            return *((unsigned int *)v2 + 12);
          case 0x1DC:
            *(_WORD *)(*((_QWORD *)v2 + 79) + 4LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1DD:
            *(_WORD *)(*((_QWORD *)v2 + 79) + 6LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1DE:
            *(_WORD *)(*((_QWORD *)v2 + 79) + 8LL) = v4;
            return *((unsigned int *)v2 + 12);
          case 0x1DF:
          case 0x1E0:
          case 0x1E1:
            **((_WORD **)v2 + 79) = v3 - 476;
            return *((unsigned int *)v2 + 12);
          case 0x1E2:
            *(_WORD *)(v5 + 10) = 5;
            return *((unsigned int *)v2 + 12);
          case 0x1E3:
            *(_WORD *)(v5 + 10) = 7;
            if ( (*((_DWORD *)v2 + 20) & 0x8000) == 0
              && (unsigned int)CW32System::SkipObjectData((__int64)this, v1, 0x80000000)
              || **((_WORD **)v2 + 79) == 6 )
            {
              goto LABEL_29;
            }
            return *((unsigned int *)v2 + 12);
          case 0x1E4:
          case 0x1E6:
          case 0x1E8:
            **((_WORD **)v2 + 79) = 6;
            return *((unsigned int *)v2 + 12);
          case 0x1E5:
            *(_WORD *)(v5 + 10) = 6;
            return *((unsigned int *)v2 + 12);
          case 0x1E7:
            *(_DWORD *)(*((_QWORD *)v2 + 79) + 12LL) = 1;
            return *((unsigned int *)v2 + 12);
          case 0x1E9:
            if ( **((_WORD **)v2 + 79) != 6 && (*((_BYTE *)v2 + 472) & 5) == 0 )
              goto LABEL_29;
            *(_WORD *)(v5 + 10) = 0;
            return *((unsigned int *)v2 + 12);
          case 0x1EA:
            if ( v4 > 0 )
            {
              *((_DWORD *)v2 + 21) &= ~0x40000000u;
              *((_DWORD *)v2 + 59) |= 0x40000000u;
              *((_DWORD *)v2 + 24) = *((_DWORD *)&rgcrRevisions + (((_BYTE)v4 - 1) & 7));
            }
            return *((unsigned int *)v2 + 12);
          case 0x1EB:
            if ( (*(_DWORD *)(*((_QWORD *)v2 + 7) + 176LL) & 0x2000000) == 0 )
              return *((unsigned int *)v2 + 12);
            if ( *((_QWORD *)v2 + 87) )
              goto LABEL_430;
            v115 = CW32System::PvAlloc(0x20u, 0x40u);
            *((_QWORD *)v2 + 87) = v115;
            if ( !v115 )
              goto LABEL_461;
            *((_QWORD *)v2 + 88) = 8;
LABEL_430:
            v116 = *((_DWORD *)v2 + 176);
            *((_DWORD *)v2 + 176) = v116 - 1;
            if ( v116 > 0 )
              goto LABEL_433;
            v117 = CW32System::PvReAlloc(*((void **)v2 + 87), 4 * *((_DWORD *)v2 + 177) + 32);
            if ( !v117 )
              goto LABEL_461;
            *((_QWORD *)v2 + 87) = v117;
            *((_DWORD *)v2 + 176) = 7;
LABEL_433:
            *(_DWORD *)(*((_QWORD *)v2 + 87) + 4LL * (int)(*((_DWORD *)v2 + 177))++) = *(_DWORD *)(*((_QWORD *)v2 + 8)
                                                                                                 + 40LL);
            return *((unsigned int *)v2 + 12);
          case 0x1EC:
            if ( !*((_WORD *)v2 + 122) )
            {
LABEL_69:
              if ( (*(_BYTE *)(v5 + 4) & 1) != 0 )
              {
                CRTFRead::HandleChar(v2, 0x20u);
              }
              else
              {
                *((_DWORD *)v2 + 78) = 0;
                CRTFRead::HandleEndOfPara(v2);
              }
            }
            return *((unsigned int *)v2 + 12);
          default:
            if ( *(_WORD *)(v5 + 10) != 11 && (unsigned int)(v3 - 256) > 0xEE )
            {
              if ( (_DWORD)v3 == 9 && (*(_BYTE *)(v5 + 4) & 1) != 0 )
                *((_WORD *)v2 + 66) = 32;
              if ( (*(_DWORD *)(*((_QWORD *)v2 + 7) + 180LL) & 0x80000) != 0 )
              {
                v118 = *((_WORD *)v2 + 66);
                if ( (unsigned int)v118 - 8216 <= 5 )
                {
                  if ( (unsigned __int16)(v118 - 8216) <= 1u )
                  {
                    *((_WORD *)v2 + 66) = 39;
                  }
                  else if ( (unsigned __int16)(v118 - 8220) <= 1u )
                  {
                    *((_WORD *)v2 + 66) = 34;
                  }
                }
              }
              CRTFRead::HandleChar(v2, *((_WORD *)v2 + 66));
            }
            return *((unsigned int *)v2 + 12);
        }
    }
    return *((unsigned int *)v2 + 12);
  }
  result = 16;
  *((_DWORD *)v2 + 12) = 16;
  return result;
}

```

## disassembly

```asm
0x180002740  push    rbx
0x180002742  push    rbp
0x180002743  push    r14
0x180002745  sub     rsp, 50h
0x180002749  movzx   edx, word ptr [rcx+2CAh]
0x180002750  xor     eax, eax
0x180002752  mov     [rsp+68h+arg_8], ax
0x180002757  mov     rbx, rcx
0x18000275a  mov     ebp, 100h
0x18000275f  test    dx, dx
0x180002762  jnz     loc_18000302B
0x180002768  movzx   r9d, word ptr [rbx+84h]
0x180002770  lea     eax, [r9-1CCh]
0x180002777  cmp     eax, 1Dh
0x18000277a  jbe     loc_180002A31
0x180002780  mov     [rsp+68h+arg_10], rsi
0x180002788  mov     esi, [rbx+80h]
0x18000278e  mov     [rsp+68h+arg_18], rdi
0x180002796  mov     rdi, [rbx+0D8h]
0x18000279d  cmp     r9d, 1BBh
0x1800027a4  jz      loc_180002858
0x1800027aa  mov     r11d, 101h
0x1800027b0  cmp     r9d, r11d
0x1800027b3  jz      loc_180002907
0x1800027b9  cmp     r9d, 102h
0x1800027c0  jz      loc_18000293F
0x1800027c6  cmp     r9d, 1C2h
0x1800027cd  jz      loc_18000297C; jumptable 0000000180002805 case 447
0x1800027d3  lea     r10d, [r9-100h]; switch 238 cases
0x1800027da  cmp     r10d, 0EDh
0x1800027e1  ja      def_180002805; jumptable 0000000180002805 default case, cases 257-260,443,445,446,449,450,452-454
0x1800027e7  lea     r8, cs:180000000h
0x1800027ee  movsxd  rax, r10d
0x1800027f1  movzx   eax, ds:(byte_1800048CC - 180000000h)[r8+rax]
0x1800027fa  mov     ecx, ds:(jpt_180002805 - 180000000h)[r8+rax*4]
0x180002802  add     rcx, r8
0x180002805  jmp     rcx; switch jump
0x18000280b  cmp     esi, 0FFFFFFFFh; jumptable 0000000180002805 case 280
0x18000280e  jz      loc_18000294D; jumptable 0000000180002805 cases 424,425,474,475,493
0x180002814  and     dword ptr [rdi+4], 0FFFFFBFFh
0x18000281b  cmp     word ptr [rdi+0Ah], 2
0x180002820  jz      loc_180002B13
0x180002826  cmp     dword ptr [rbx+8], 0
0x18000282a  jz      loc_1800028EA; jumptable 0000000180002805 case 426
0x180002830  mov     edx, esi; int
0x180002832  mov     rcx, rbx; this
0x180002835  call    ?SelectCurrentFont@CRTFRead@@AEAAPEAU_textfont@@H@Z; CRTFRead::SelectCurrentFont(int)
0x18000283a  movzx   ecx, byte ptr [rax+2]
0x18000283e  lea     eax, [rcx-0B1h]
0x180002844  cmp     eax, 1
0x180002847  ja      loc_1800028EA; jumptable 0000000180002805 case 426
0x18000284d  mov     [rbx+2D0h], cl
0x180002853  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002858  test    byte ptr [rbx+1D8h], 40h
0x18000285f  jnz     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002865  test    byte ptr [rdi+4], 10h
0x180002869  jnz     short loc_1800028EA; jumptable 0000000180002805 case 426
0x18000286b  cmp     word ptr [rdi+0Ah], 13h
0x180002870  jz      short loc_1800028EA; jumptable 0000000180002805 case 426
0x180002872  or      dword ptr [rbx+0F0h], 40000h
0x18000287c  mov     ebp, 1
0x180002881  and     dword ptr [rbx+54h], 0FFFBFFFFh
0x180002888  mov     [rsp+68h+arg_8], si
0x18000288d  mov     eax, [rdi+14h]
0x180002890  test    eax, eax
0x180002892  js      short loc_1800028CC
0x180002894  mov     ecx, [rbx+8]
0x180002897  test    ecx, ecx
0x180002899  jle     loc_180002BBB
0x18000289f  cmp     eax, ecx
0x1800028a1  jge     loc_180002BBB
0x1800028a7  mov     rdx, [rbx]; unsigned int
0x1800028aa  test    rdx, rdx
0x1800028ad  jz      loc_180002BBB
0x1800028b3  imul    eax, [rbx+10h]
0x1800028b7  movsxd  rcx, eax
0x1800028ba  add     rcx, rdx
0x1800028bd  test    rcx, rcx
0x1800028c0  jz      short loc_1800028CC
0x1800028c2  cmp     byte ptr [rcx+2], 2
0x1800028c6  jz      loc_180004634
0x1800028cc  movzx   eax, word ptr [rdi+10h]
0x1800028d0  lea     rdx, [rsp+68h+arg_8]; unsigned __int16 *
0x1800028d5  mov     r9d, ebp; int
0x1800028d8  mov     [rbx+2CAh], ax
0x1800028df  mov     r8d, ebp; int
0x1800028e2  mov     rcx, rbx; this
0x1800028e5  call    ?AddText@CRTFRead@@AEAAHPEAGJH@Z; CRTFRead::AddText(ushort *,long,int)
0x1800028ea  mov     rsi, [rsp+68h+arg_10]; jumptable 0000000180002805 case 426
0x1800028f2  mov     rdi, [rsp+68h+arg_18]
0x1800028fa  mov     eax, [rbx+30h]
0x1800028fd  add     rsp, 50h
0x180002901  pop     r14
0x180002903  pop     rbp
0x180002904  pop     rbx
0x180002905  retn
0x180002907  lea     r8, cs:180000000h
0x18000290e  movsx   eax, word ptr [rdi+0Ah]; jumptable 0000000180002805 case 256
0x180002912  dec     eax; switch 19 cases
0x180002914  cmp     eax, 12h
0x180002917  jbe     loc_180004463
0x18000291d  mov     rdx, [rbx+88h]; jumptable 0000000180004470 default case, cases 3,4,7-9,12,13,18
0x180002924  xor     r8d, r8d
0x180002927  cmp     r9w, r11w
0x18000292b  mov     rcx, rbx; this
0x18000292e  mov     r9d, 0FFFFFFFFh; int
0x180002934  setz    r8b; int
0x180002938  call    ?HandleText@CRTFRead@@AEAAHPEAEHJ@Z; CRTFRead::HandleText(uchar *,int,long)
0x18000293d  jmp     short loc_1800028EA; jumptable 0000000180002805 case 426
0x18000293f  mov     eax, 1AAh
0x180002944  cmp     [rbx+86h], ax
0x18000294b  jnz     short loc_1800028EA; jumptable 0000000180002805 case 426
0x18000294d  mov     rcx, rbx; jumptable 0000000180002805 cases 424,425,474,475,493
0x180002950  call    ?SkipToEndOfGroup@CRTFRead@@AEAAHXZ; CRTFRead::SkipToEndOfGroup(void)
0x180002955  test    eax, eax
0x180002957  jnz     short loc_1800028EA; jumptable 0000000180002805 case 426
0x180002959  movzx   eax, word ptr [rdi+0Ah]
0x18000295d  cmp     ax, 2
0x180002961  jz      short loc_180002969
0x180002963  cmp     ax, 13h
0x180002967  jnz     short loc_18000296F
0x180002969  mov     word ptr [rdi+0Ah], 12h
0x18000296f  mov     rcx, rbx; this
0x180002972  call    ?HandleEndGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleEndGroup(void)
0x180002977  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x18000297c  and     dword ptr [rdi+4], 0FFFFFDFFh; jumptable 0000000180002805 case 447
0x180002983  xor     ecx, ecx
0x180002985  mov     edx, 1BFh
0x18000298a  mov     eax, 200h
0x18000298f  cmp     r9w, dx
0x180002993  cmovz   ecx, eax
0x180002996  xor     eax, eax
0x180002998  or      ecx, [rdi+4]
0x18000299b  btr     ecx, 8
0x18000299f  cmp     r9w, dx
0x1800029a3  cmovnz  eax, ebp
0x1800029a6  or      ecx, eax
0x1800029a8  mov     [rdi+4], ecx
0x1800029ab  mov     rdi, [rbx+38h]
0x1800029af  mov     edx, [rdi+0C0h]
0x1800029b5  mov     ecx, edx
0x1800029b7  not     ecx
0x1800029b9  and     ecx, 1
0x1800029bc  jz      loc_1800028EA; jumptable 0000000180002805 case 426
0x1800029c2  mov     eax, ecx
0x1800029c4  or      eax, edx
0x1800029c6  mov     [rdi+0C0h], eax
0x1800029cc  and     eax, 61086013h
0x1800029d1  cmp     eax, ecx
0x1800029d3  jnz     loc_1800028EA; jumptable 0000000180002805 case 426
0x1800029d9  mov     ebp, 1
0x1800029de  mov     rcx, rdi; this
0x1800029e1  mov     r8d, ebp; __int64
0x1800029e4  mov     edx, ebp; unsigned __int64
0x1800029e6  call    ?OnSetTypographyOptions@CTxtEdit@@QEAAJ_K_J@Z; CTxtEdit::OnSetTypographyOptions(unsigned __int64,__int64)
0x1800029eb  mov     rcx, rdi; this
0x1800029ee  call    ?ItemizeDoc@CTxtEdit@@QEAAXPEAVIUndoBuilder@@J@Z; CTxtEdit::ItemizeDoc(IUndoBuilder *,long)
0x1800029f3  mov     rcx, [rdi+50h]
0x1800029f7  test    rcx, rcx
0x1800029fa  jnz     loc_180004441
0x180002a00  mov     rcx, [rdi+58h]
0x180002a04  test    rcx, rcx
0x180002a07  jnz     loc_180004452
0x180002a0d  mov     eax, [rdi+0B4h]
0x180002a13  mov     ecx, [rdi+0C0h]
0x180002a19  shl     ecx, 16h
0x180002a1c  xor     ecx, eax
0x180002a1e  and     ecx, 400000h
0x180002a24  xor     ecx, eax
0x180002a26  mov     [rdi+0B4h], ecx
0x180002a2c  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002a31  cmp     qword ptr [rbx+278h], 0
0x180002a39  jnz     loc_180002780
0x180002a3f  mov     eax, 10h
0x180002a44  mov     [rbx+30h], eax
0x180002a47  add     rsp, 50h
0x180002a4b  pop     r14
0x180002a4d  pop     rbp
0x180002a4e  pop     rbx
0x180002a4f  retn
0x180002a51  mov     eax, [rdi+4]; jumptable 0000000180002805 case 281
0x180002a54  test    eax, 300h
0x180002a59  jz      loc_1800032AC
0x180002a5f  mov     ecx, [rbx+8]
0x180002a62  test    ecx, ecx
0x180002a64  jle     short loc_180002A6E
0x180002a66  mov     rdx, [rbx]
0x180002a69  test    rdx, rdx
0x180002a6c  jnz     short loc_180002A74
0x180002a6e  xor     edx, edx
0x180002a70  test    ecx, ecx
0x180002a72  jz      short loc_180002A85
0x180002a74  movsx   eax, word ptr [rdx]
0x180002a77  dec     ecx
0x180002a79  cmp     esi, eax
0x180002a7b  jz      short loc_180002A87
0x180002a7d  add     rdx, 4Ch ; 'L'
0x180002a81  test    ecx, ecx
0x180002a83  jnz     short loc_180002A74
0x180002a85  dec     ecx
0x180002a87  test    ecx, ecx
0x180002a89  js      loc_1800028EA; jumptable 0000000180002805 case 426
0x180002a8f  movzx   ecx, byte ptr [rdx+2]
0x180002a93  jmp     loc_18000283E
0x180002a98  movzx   ecx, word ptr [rbx+0F6h]; jumptable 0000000180002805 cases 340,341
0x180002a9f  xor     eax, eax
0x180002aa1  mov     edx, [rbx+12Ch]
0x180002aa7  and     ecx, 1
0x180002aaa  mov     r8d, 154h
0x180002ab0  cmp     r9w, r8w
0x180002ab4  setz    al
0x180002ab7  cmp     ecx, eax
0x180002ab9  jz      short loc_180002AEA
0x180002abb  sub     esi, [rbx+100h]
0x180002ac1  mov     [rbx+0F8h], esi
0x180002ac7  or      edx, 1
0x180002aca  mov     [rbx+12Ch], edx
0x180002ad0  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002ad5  or      dword ptr [rbx+12Ch], 80h; jumptable 0000000180002805 case 347
0x180002adf  mov     [rbx+10Ch], esi
0x180002ae5  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002aea  mov     [rbx+0FCh], esi
0x180002af0  or      edx, 2
0x180002af3  jmp     short loc_180002ACA
0x180002af5  xor     eax, eax; jumptable 0000000180002805 case 262
0x180002af7  mov     rcx, rbx; this
0x180002afa  mov     [rbx+2CAh], ax
0x180002b01  call    ?HandleFieldEndGroup@CRTFRead@@AEAAXXZ; CRTFRead::HandleFieldEndGroup(void)
0x180002b06  mov     rcx, rbx; this
0x180002b09  call    ?HandleEndGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleEndGroup(void)
0x180002b0e  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002b13  movsx   eax, word ptr [rbx+1DCh]
0x180002b1a  xor     ebp, ebp
0x180002b1c  mov     dword ptr [rsp+68h+lpMem], ebp
0x180002b20  cmp     esi, eax
0x180002b22  jz      loc_1800032C9
0x180002b28  movsx   eax, word ptr [rbx+1DEh]
0x180002b2f  cmp     esi, eax
0x180002b31  jz      loc_1800032D6
0x180002b37  lea     r8, [rsp+68h+lpMem]; int *
0x180002b3c  mov     edx, 1; int
0x180002b41  mov     rcx, rbx; this
0x180002b44  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x180002b49  test    rax, rax
0x180002b4c  jz      loc_180004591
0x180002b52  mov     ebp, dword ptr [rsp+68h+lpMem]
0x180002b56  mov     [rdi+14h], ebp
0x180002b59  test    ebp, ebp
0x180002b5b  js      loc_1800028EA; jumptable 0000000180002805 case 426
0x180002b61  mov     edx, ebp; int
0x180002b63  mov     rcx, rbx; this
0x180002b66  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x180002b6b  test    rax, rax
0x180002b6e  jz      loc_1800028EA; jumptable 0000000180002805 case 426
0x180002b74  xor     ecx, ecx
0x180002b76  mov     [rax], si
0x180002b79  mov     [rax+6], cx
0x180002b7d  mov     word ptr [rax+2], 1
0x180002b83  mov     dword ptr [rax+48h], 0FFFFh
0x180002b8a  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002b8f  test    byte ptr [rdi+4], 1; jumptable 0000000180002805 cases 337,338
0x180002b93  mov     rcx, rbx; this
0x180002b96  jz      short loc_180002BA7
0x180002b98  mov     edx, 20h ; ' '; unsigned __int16
0x180002b9d  call    ?HandleChar@CRTFRead@@AEAAHG@Z; CRTFRead::HandleChar(ushort)
0x180002ba2  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002ba7  mov     dword ptr [rbx+138h], 0
0x180002bb1  call    ?HandleEndOfPara@CRTFRead@@AEAAHXZ; CRTFRead::HandleEndOfPara(void)
0x180002bb6  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002bbb  xor     ecx, ecx
0x180002bbd  jmp     loc_1800028BD
0x180002bc2  movzx   eax, sil
0x180002bc6  sub     eax, 0B1h
0x180002bcb  cmp     eax, 1
0x180002bce  jbe     loc_18000324A
0x180002bd4  or      [rbx+1D8h], bp
0x180002bdb  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
0x180002be0  movzx   eax, byte ptr [rax+2]
0x180002be4  sub     eax, 0B1h
0x180002be9  cmp     eax, 1
0x180002bec  jbe     short loc_180002BF6
0x180002bee  mov     [rbx+1DEh], r10w
0x180002bf6  movzx   eax, byte ptr [rbx+2D0h]
0x180002bfd  sub     eax, 0B1h
0x180002c02  cmp     eax, 1
0x180002c05  jbe     short loc_180002BD4
0x180002c07  mov     [rbx+2D0h], sil
0x180002c0e  jmp     short loc_180002BD4
0x180002c10  test    esi, esi; jumptable 0000000180002805 case 348
0x180002c12  jns     loc_1800036CB
0x180002c18  mov     eax, esi
0x180002c1a  neg     eax
0x180002c1c  mov     [rbx+110h], eax
0x180002c22  xor     eax, eax
0x180002c24  test    esi, esi
0x180002c26  setle   al
0x180002c29  add     eax, 3
0x180002c2c  or      [rbx+12Ch], ebp
0x180002c32  mov     [rbx+116h], al
0x180002c38  jmp     loc_1800028EA; jumptable 0000000180002805 case 426
  ... truncated ...
```
