# CTxtRange::CleanseAndReplaceRange(long,ushort const *,int,IUndoBuilder *,ushort *,long *,ulong)

- ea: `0x18001b100`
- end: `0x18001be01`
- name: `?CleanseAndReplaceRange@CTxtRange@@QEAAJJPEBGHPEAVIUndoBuilder@@PEAGPEAJK@Z`
- size: `3329`
- prototype: `__int64 __usercall@<rax>(CTxtRange *__hidden this@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, int@<r9d>, struct IUndoBuilder *, unsigned __int16 *, int *, unsigned int)`
- caller_count: `8`
- callee_count: `26`
- tags: ``

## callers

- `0x180004a80`
- `0x180019974`
- `0x18002d048`
- `0x1800445b4`
- `0x18006e818`
- `0x180074658`
- `0x180075550`
- `0x18008ba40`

## callees

- `0x180005070`
- `0x180005510`
- `0x180006570`
- `0x1800066b0`
- `0x1800182a0`
- `0x180019e4c`
- `0x180019fe4`
- `0x18001b100`
- `0x18001be08`
- `0x18001be4c`
- `0x18001be70`
- `0x18001bfe8`
- `0x18001c0cc`
- `0x18001f230`
- `0x18001f4a0`
- `0x180022ad4`
- `0x18002720c`
- `0x180027394`
- `0x18002da30`
- `0x18002eb38`
- `0x180035b80`
- `0x18003ed40`
- `0x1800450c4`
- `0x18004a030`
- `0x180093c00`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CTxtRange::CleanseAndReplaceRange(
        CTxtRange *this,
        int a2,
        unsigned __int16 *a3,
        int a4,
        struct IUndoBuilder *a5,
        unsigned __int16 *a6,
        int *a7,
        char a8)
{
  CTxtRange *v8; // r15
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 *v14; // rbx
  unsigned __int16 *v15; // rax
  int v16; // ecx
  int v17; // esi
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // eax
  int v21; // r14d
  int v22; // r14d
  unsigned int v23; // eax
  int v24; // ebx
  CRchTxtPtr *v25; // rcx
  unsigned int v26; // r9d
  int v27; // r11d
  unsigned int v28; // eax
  int v29; // r8d
  int v30; // eax
  const struct CCharFormat *CharFormat; // rax
  __int64 v32; // xmm0_8
  unsigned int CharSetMask; // eax
  unsigned int v34; // ecx
  BOOL v35; // edx
  bool v36; // zf
  unsigned __int16 *Buf; // rax
  int v39; // edx
  __int64 *PF; // rax
  int v41; // edx
  __int64 v42; // rdx
  __int16 v43; // dx
  unsigned int v44; // r11d
  int v45; // edx
  int v46; // r10d
  unsigned int v47; // ecx
  unsigned int v48; // esi
  unsigned __int16 v49; // ax
  unsigned __int16 *v50; // rcx
  unsigned __int16 *v51; // rax
  int v52; // ebx
  unsigned int CharFlags; // eax
  unsigned int v54; // ebx
  int v55; // r15d
  CTxtRange *v56; // r14
  __int64 v57; // rax
  unsigned int v58; // eax
  int v59; // r14d
  const unsigned __int16 *v60; // r15
  unsigned int v61; // ecx
  int v62; // eax
  int v63; // r14d
  __int128 v64; // xmm1
  int v65; // eax
  int v66; // edx
  unsigned __int16 Char; // ax
  int i; // r14d
  unsigned int CharFlags125x; // ebx
  const struct CCharFormat *v70; // rax
  unsigned int v71; // eax
  unsigned __int16 *v72; // rcx
  int v73; // eax
  unsigned __int16 *v74; // rax
  struct IUndoBuilder *v75; // r14
  int v76; // eax
  int v77; // r8d
  unsigned int v78; // ebx
  unsigned int v79; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v80; // [rsp+50h] [rbp-B0h]
  int v81; // [rsp+54h] [rbp-ACh]
  bool v82; // [rsp+58h] [rbp-A8h]
  int v83; // [rsp+5Ch] [rbp-A4h]
  int v84; // [rsp+60h] [rbp-A0h]
  unsigned int v85; // [rsp+64h] [rbp-9Ch]
  int v86; // [rsp+68h] [rbp-98h]
  unsigned int v87; // [rsp+6Ch] [rbp-94h]
  unsigned int v88; // [rsp+70h] [rbp-90h]
  int v89; // [rsp+70h] [rbp-90h]
  int v90; // [rsp+74h] [rbp-8Ch] BYREF
  int v91; // [rsp+78h] [rbp-88h]
  int v92; // [rsp+7Ch] [rbp-84h]
  CTxtRange *v93; // [rsp+80h] [rbp-80h]
  int v94; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v95; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v96; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v97; // [rsp+A0h] [rbp-60h]
  struct IUndoBuilder *v98; // [rsp+A8h] [rbp-58h]
  __int128 v99; // [rsp+B0h] [rbp-50h] BYREF
  int v100; // [rsp+C0h] [rbp-40h]
  unsigned int v101; // [rsp+C4h] [rbp-3Ch]
  BOOL v102; // [rsp+C8h] [rbp-38h]
  __int64 *v103; // [rsp+D0h] [rbp-30h] BYREF
  CDisplay *v104; // [rsp+D8h] [rbp-28h]
  __int128 v105; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v106; // [rsp+F0h] [rbp-10h]
  __int64 v107; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v108; // [rsp+108h] [rbp+8h]
  __int64 v109; // [rsp+110h] [rbp+10h]
  int *v110; // [rsp+118h] [rbp+18h]
  _OWORD v111[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v112; // [rsp+140h] [rbp+40h]
  _BYTE v113[256]; // [rsp+150h] [rbp+50h] BYREF
  void *lpMem; // [rsp+250h] [rbp+150h]
  int v115; // [rsp+258h] [rbp+158h]

  v8 = this;
  v98 = a5;
  v93 = this;
  v11 = *((_QWORD *)this + 6);
  v110 = a7;
  v108 = a6;
  v97 = a6;
  v12 = (unsigned int)*(__int16 *)(v11 + 276);
  v92 = a4;
  v109 = v11;
  v13 = *(_QWORD *)qword_1800A72D0;
  v95 = 0;
  v14 = g_defaultCF;
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, unsigned __int16 **))(v13 + 32))(
         qword_1800A72D0,
         v12,
         &v95) >= 0 )
  {
    v15 = v95;
  }
  else
  {
    v15 = (unsigned __int16 *)g_defaultCF;
    v95 = (unsigned __int16 *)g_defaultCF;
  }
  v16 = *((_DWORD *)v8 + 22);
  v17 = *((_DWORD *)v8 + 10);
  v80 = *((_BYTE *)v15 + 4);
  v90 = 0;
  if ( v16 > 0 )
    v17 -= v16;
  v91 = v17;
  v18 = CTxtRange::GetiFormat(v8);
  v103 = 0;
  v19 = (unsigned int)v18;
  if ( v18 < 0 )
    v19 = (unsigned int)*(__int16 *)(*((_QWORD *)v8 + 6) + 276LL);
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A72D0 + 32LL))(
         qword_1800A72D0,
         v19,
         &v103) >= 0 )
    v14 = v103;
  else
    v103 = g_defaultCF;
  v20 = CW32System::GetFontSig(*((unsigned __int8 *)v14 + 4)) << 8;
  if ( (v20 & 0x400000) != 0 )
  {
    v22 = v20;
  }
  else
  {
    v21 = 3145728;
    if ( (v20 | 0x200000) >= 0x20000000 )
      v21 = 0x200000;
    v22 = v20 | v21;
    if ( (v22 & 0x1E000000) != 0 && ((v23 = CW32System::_syslcid & 0x3FF, v23 == 18) || v23 == 4 || v23 == 17) )
    {
      v22 |= 0x800000u;
    }
    else if ( (v22 & 0x19300) != 0 )
    {
      v22 |= 0x80000u;
    }
  }
  LODWORD(v103) = *(_DWORD *)(v11 + 180);
  v84 = 0;
  v104 = *(CDisplay **)(v11 + 64);
  CDisplay::Freeze(v104);
  v24 = (*(_DWORD *)(*(_QWORD *)(v11 + 64) + 56LL) >> 17) & 1;
  v94 = v24;
  v102 = v80 == 128 || v80 == 129 || v80 == 130 || v80 == 134 || v80 == 136;
  LODWORD(v99) = 0;
  v82 = CRchTxtPtr::fUseUIFont((CTxtRange *)((char *)v8 + 8));
  v28 = *(_DWORD *)(v11 + 180);
  v29 = v26;
  lpMem = v113;
  LOBYTE(v29) = v22 == 0x400000;
  v115 = 256;
  BYTE4(v111[0]) = 0;
  v36 = (*(_BYTE *)(v11 + 180) & 1) == 0;
  v81 = v29;
  v88 = v28;
  v95 = a3;
  if ( !v36 || (v36 = *((_DWORD *)v8 + 22) == 0, v100 = 1, v36) )
    v100 = v26;
  if ( (*(_WORD *)(v11 + 184) & 0x4000) != 0 )
  {
    v84 = 503316480;
    v30 = CTxtRange::GetiFormat(v8);
    CharFormat = CTxtArray::GetCharFormat((CTxtArray *)(v11 + 248), v30);
    v29 = v81;
    v25 = (CTxtRange *)((char *)v8 + 8);
    v27 = v99;
    v26 = 0;
    v111[0] = *(_OWORD *)CharFormat;
    v111[1] = *((_OWORD *)CharFormat + 1);
    v32 = *((_QWORD *)CharFormat + 4);
    v28 = v88;
    v112 = v32;
  }
  if ( v82 )
  {
    CharSetMask = CTxtRange::GetCharSetMask(v8, 1);
    v27 = v99;
    v34 = CharSetMask;
    v26 = 0;
    v36 = (CharSetMask & 0x300000) == 3145728;
    v28 = v88;
    v35 = v36;
    v36 = v34 == 0x400000;
    v101 = v35;
    v25 = (CTxtRange *)((char *)v8 + 8);
    if ( v36 )
    {
      v29 = 1;
      v81 = 1;
    }
    else
    {
      v29 = 0;
      v81 = 0;
      v101 = v35;
    }
  }
  else
  {
    v101 = v26;
  }
  if ( !a3 )
  {
    a2 = v26;
    goto LABEL_71;
  }
  if ( v24 )
  {
    v36 = a2 == 0;
    if ( a2 < 0 )
    {
      a2 = CW32System::wcslen(a3);
      v25 = (CTxtRange *)((char *)v8 + 8);
      v36 = a2 == 0;
    }
    Buf = v97;
    if ( !v36 && !v97 )
    {
      Buf = CTempWcharBuf::GetBuf((CTempWcharBuf *)v113, a2);
      v97 = Buf;
      if ( !Buf )
      {
        if ( lpMem != v113 )
          CW32System::FreePv(lpMem);
        CDisplay::Thaw(v104);
        return 0;
      }
      v25 = (CTxtRange *)((char *)v8 + 8);
    }
    v39 = *((_DWORD *)v8 + 22);
    v95 = Buf;
    if ( v39 <= 0 )
    {
      PF = (__int64 *)CRchTxtPtr::GetPF(v25);
LABEL_68:
      v44 = *((unsigned __int16 *)PF + 1);
      v29 = v81;
      v28 = v88;
      v27 = (v44 >> 14) & 1;
      LODWORD(v99) = v27;
      v26 = 0;
      goto LABEL_71;
    }
    v99 = *(_OWORD *)((char *)v8 + 72);
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v99, -v39);
    if ( (_QWORD)v99 && *(_DWORD *)(v99 + 8) )
    {
      v41 = *(_DWORD *)(v99 + 8);
      if ( v41 > 0 && SDWORD2(v99) < v41 && *(_QWORD *)v99 && (SDWORD2(v99) & 0x80000000) == 0 )
        v42 = *(_QWORD *)v99 + *(_DWORD *)(v99 + 16) * DWORD2(v99);
      else
        v42 = 0;
      v43 = *(_WORD *)(v42 + 4);
      *(_QWORD *)&v99 = 0;
      if ( v43 >= 0 )
        goto LABEL_65;
    }
    else
    {
      *(_QWORD *)&v99 = 0;
    }
    v43 = *(_WORD *)(v11 + 278);
LABEL_65:
    if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, __int128 *))(*(_QWORD *)qword_1800A72C8 + 32LL))(
           qword_1800A72C8,
           (unsigned int)v43,
           &v99) >= 0 )
    {
      PF = (__int64 *)v99;
    }
    else
    {
      PF = g_defaultPF;
      *(_QWORD *)&v99 = g_defaultPF;
    }
    goto LABEL_68;
  }
  if ( a2 < 0 )
    a2 = 0x3FFFFFFF;
LABEL_71:
  v45 = 0;
  v86 = v26;
  v85 = v26;
  v46 = v26;
  v87 = v26;
  v89 = (v28 >> 19) & 1;
  v83 = 0;
  if ( !a2 )
    goto LABEL_193;
  do
  {
    v47 = *a3;
    if ( !(_WORD)v47 && (!v24 || !v108) )
      break;
    v48 = *a3;
    if ( v47 - 9 > 4 )
    {
      if ( (v47 | 1) == 0x2029 )
      {
        if ( !v24 )
          break;
        v48 = 11;
        if ( v47 == 8233 )
          v48 = 13;
      }
    }
    else
    {
      if ( !v24 && v47 >= 0xA )
        break;
      if ( v47 != 13 || ((unsigned int)v103 & 0x80000) != 0 )
      {
        if ( v89 || v47 != 10 )
        {
          if ( v47 == 9 && v27 )
            v48 = 32;
        }
        else
        {
          v48 = 13;
        }
      }
      else
      {
        if ( a2 > 1 )
        {
          v49 = a3[1];
          if ( v49 == 13 && a2 > 2 )
          {
            if ( a3[2] == 10 )
            {
              if ( v89 )
              {
                v50 = v97;
                v48 = 10;
                *(_DWORD *)v97 = 851981;
                v45 += 2;
                v97 = v50 + 2;
                v83 = v45;
              }
              else
              {
                v48 = 32;
                if ( (*(_WORD *)(v11 + 186) & 0x4000) != 0 )
                  v48 = 13;
              }
              a3 += 2;
              a2 -= 2;
            }
          }
          else if ( v49 == 10 )
          {
            if ( v89 && !v27 )
            {
              v51 = v97;
              v48 = 10;
              *v97 = 13;
              ++v45;
              v97 = v51 + 1;
              v83 = v45;
            }
            ++a3;
            --a2;
          }
        }
        if ( v27 && v48 == 13 )
          v48 = 32;
      }
    }
    v52 = 0x400000;
    if ( !v29 )
    {
      CharFlags = GetCharFlags(v48, v80);
      v45 = v83;
      v52 = CharFlags;
      v29 = v81;
      v26 = v87;
      v46 = v86;
    }
    v26 |= v52;
    v54 = v52 & 0xFFFFFF00;
    v87 = v26;
    if ( (*(_DWORD *)(v11 + 180) & 0x200000) == 0 || v29 )
      goto LABEL_186;
    v55 = 0;
    if ( v100 )
    {
      v56 = v93;
      v57 = *(_QWORD *)v93;
      v100 = 0;
      (*(void (__fastcall **)(CTxtRange *, _QWORD, _QWORD, struct IUndoBuilder *, int, _QWORD, int))(v57 + 560))(
        v93,
        0,
        0,
        v98,
        1,
        0,
        2);
      CTxtRange::Set_iCF(v56, -1);
      v58 = CTxtRange::GetCharSetMask(v56, 1);
      v45 = v83;
      v22 = v58;
      v29 = v81;
      v26 = v87;
      v46 = v86;
    }
    if ( (*(_WORD *)(v11 + 184) & 0x4000) != 0 )
    {
      if ( v48 > 0x7F )
        goto LABEL_173;
      if ( v82 )
      {
LABEL_165:
        if ( v84 != 3145728 )
        {
          v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, 0, &v90, v91, 0, v79);
          v70 = CTxtArray::GetCharFormat((CTxtArray *)(v11 + 248), -1);
          v105 = *(_OWORD *)v70;
          v106 = *((_OWORD *)v70 + 1);
          v107 = *((_QWORD *)v70 + 4);
          CTxtRange::SetCharFormat(v93, (const struct CCharFormat *)&v105, 0, v98, 0xA8000000, 0x9000u);
          v45 = v83;
          v55 = 1;
          v29 = v81;
          v26 = v87;
          v46 = v86;
        }
        v84 = 3145728;
        goto LABEL_176;
      }
      if ( (*(_BYTE *)(v11 + 188) & 2) != 0 && (*((_BYTE *)&rgbCharClass + (unsigned __int8)v48) & 3) != 0 )
      {
        if ( v84 != 1 )
        {
          v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, v54, &v90, v91, 0, v79);
          v55 = 1;
          v45 = v83;
          v29 = v81;
          v26 = v87;
          v46 = v86;
        }
        v84 = 1;
      }
      else
      {
LABEL_173:
        if ( v84 != 503316480 )
        {
          v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, 0, &v90, v91, 0, v79);
          CTxtRange::SetCharFormat(v93, (const struct CCharFormat *)v111, 0, v98, 0xA8000000, 0x9000u);
          v45 = v83;
          v55 = 1;
          v29 = v81;
          v26 = v87;
          v46 = v86;
        }
        v84 = 503316480;
      }
LABEL_176:
      v36 = v55 == 0;
      v8 = v93;
      if ( !v36 )
        goto LABEL_177;
      goto LABEL_186;
    }
    if ( v82 )
    {
      if ( v54 != 512 && v48 - 592 > 0xAF && v48 - 65104 > 0x1F || CW32System::_ACP != 936 && CW32System::_ACP != 950 )
        goto LABEL_123;
      v96 = v48;
      if ( (unsigned int)CW32System::VerifyFEString(936, &v96, 1, 1) == 936
        || (unsigned int)CW32System::VerifyFEString(950, &v96, 1, 1) == 950 )
      {
        v45 = v83;
        v54 = 0x4000000;
        v29 = v81;
        v26 = v87;
        v46 = v86;
      }
      else
      {
        v45 = v83;
        v29 = v81;
        v26 = v87;
        v46 = v86;
LABEL_123:
        if ( v54 == 256 && v102 )
        {
          if ( v84 != 256 )
          {
            v55 = 1;
            v85 += CTxtRange::CheckLimitReplaceRange(v93, v45, v95, v92, v98, 0x100u, &v90, v91, 0, v79);
            v45 = v83;
            v29 = v81;
            v26 = v87;
            v46 = v86;
          }
          v84 = 256;
          goto LABEL_176;
        }
      }
      if ( v101 && ((v54 & 0x300000) != 0 || v48 - 8216 <= 5) )
        goto LABEL_165;
    }
    if ( v54 && (v22 & v54) == 0 || v84 )
    {
      v84 = 0;
      if ( (v54 & 0x14000000) != 0 )
      {
        v59 = a2 - 1;
        v60 = a3 + 1;
        if ( a2 - 1 <= 10 )
        {
          if ( a2 != 1 )
            goto LABEL_139;
        }
        else
        {
          v59 = 10;
          do
          {
LABEL_139:
            if ( !*v60 )
              break;
            v61 = *v60++;
            v54 |= GetCharFlags(v61, v80);
            --v59;
          }
          while ( v59 );
          v11 = v109;
        }
        v8 = v93;
        v62 = CTxtRange::CalcTextLenNotInRange(v93);
        if ( a2 < 6 && v62 )
        {
          v63 = 6;
          v64 = *(_OWORD *)((char *)v8 + 40);
          v105 = *(_OWORD *)((char *)v8 + 24);
          if ( v62 < 6 )
            v63 = v62;
          v65 = *((_DWORD *)v8 + 22);
          v106 = v64;
          if ( !v65 )
          {
            v66 = v63 / -2;
            goto LABEL_150;
          }
          if ( v65 < 0 )
          {
            v66 = -v63;
LABEL_150:
            CTxtPtr::AdvanceCp((CTxtPtr *)&v105, v66);
          }
          do
          {
            Char = CTxtPtr::GetChar((CTxtPtr *)&v105);
            v54 |= GetCharFlags(Char, v80);
            CTxtPtr::AdvanceCp((CTxtPtr *)&v105, 1);
            --v63;
          }
          while ( v63 );
          v8 = v93;
        }
        v45 = v83;
        v54 &= 0x1E000000u;
      }
      else
      {
        if ( (v54 & 0x300) != 0 )
        {
          i = v22 & 0x19300;
          if ( i )
          {
            CharFlags125x = CW32System::GetCharFlags125x(v48);
            if ( (CharFlags125x & i) == 0 )
            {
              for ( i = 256; i < 0x20000; i *= 2 )
              {
                if ( (i & CharFlags125x & 0x19300) != 0 )
                  break;
              }
            }
            v45 = v83;
            v54 = i & CharFlags125x & 0x19300;
          }
        }
        v8 = v93;
      }
      v85 += CTxtRange::CheckLimitReplaceRange(v8, v45, v95, v92, v98, v54, &v90, v91, 2, v79);
      v29 = v81;
      v26 = v87;
      v46 = v86;
LABEL_177:
      if ( (v54 & 0x400000) != 0 )
      {
        v22 = 0x400000;
      }
      else
      {
        v71 = CTxtRange::GetCharSetMask(v8, 0);
        v29 = v81;
        v22 = v71;
        v26 = v87;
        v46 = v86;
      }
      v72 = a3;
      if ( v90 )
        v46 = v90;
      v73 = v94;
      v86 = v46;
      if ( v94 )
        v72 = v97;
      v45 = 0;
      v95 = v72;
      goto LABEL_187;
    }
    v8 = v93;
LABEL_186:
    v73 = v94;
LABEL_187:
    if ( v73 )
    {
      if ( (v54 & 0x400000) != 0 )
        LOWORD(v48) = (unsigned __int8)v48;
      v74 = v97;
      *v97 = v48;
      v97 = v74 + 1;
    }
    v24 = v94;
    ++v45;
    v27 = v99;
    ++a3;
    v83 = v45;
    --a2;
  }
  while ( a2 );
  v17 = v91;
LABEL_193:
  v75 = v98;
  CTxtEdit::OrCharFlags((CTxtEdit *)v11, v26, v98);
  v76 = CTxtRange::CheckLimitReplaceRange(v8, v83, v95, v92, v75, 0, &v90, v17, 0, v79);
  v77 = v86;
  v78 = v76 + v85;
  if ( v90 )
    v77 = v90;
  if ( v110 )
    *v110 = v77;
  if ( (*(_DWORD *)(v11 + 192) & 0x61086013) != 0 )
  {
    if ( (*(_DWORD *)(v11 + 180) & 0x10000) == 0 && (a8 & 2) == 0 )
      CRchTxtPtr::ItemizeReplaceRange((CTxtRange *)((char *)v8 + 8), v78, v77, v75, a8 & 1);
    else
      *(_WORD *)(v11 + 188) |= 8u;
  }
  if ( lpMem != v113 )
    CW32System::FreePv(lpMem);
  CDisplay::Thaw(v104);
  return v78;
}

```

## disassembly

```asm
0x18001b100  push    rbp
0x18001b102  push    rbx
0x18001b103  push    rsi
0x18001b104  push    rdi
0x18001b105  push    r12
0x18001b107  push    r13
0x18001b109  push    r14
0x18001b10b  push    r15
0x18001b10d  lea     rbp, [rsp-178h]
0x18001b115  sub     rsp, 278h
0x18001b11c  mov     rax, cs:__security_cookie
0x18001b123  xor     rax, rsp
0x18001b126  mov     [rbp+1B0h+var_50], rax
0x18001b12d  mov     rax, [rbp+1B0h+arg_20]
0x18001b134  mov     r15, rcx
0x18001b137  mov     [rbp+1B0h+var_208], rax
0x18001b13b  mov     r12, r8
0x18001b13e  mov     rax, [rbp+1B0h+arg_30]
0x18001b145  lea     r8, [rbp+1B0h+var_220]
0x18001b149  mov     [rbp+1B0h+var_230], rcx
0x18001b14d  mov     r13d, edx
0x18001b150  mov     rcx, [rbp+1B0h+arg_28]
0x18001b157  xor     r14d, r14d
0x18001b15a  mov     rdi, [r15+30h]
0x18001b15e  mov     [rbp+1B0h+var_198], rax
0x18001b162  mov     [rbp+1B0h+var_1A8], rcx
0x18001b166  mov     [rbp+1B0h+var_210], rcx
0x18001b16a  mov     rcx, cs:qword_1800A72D0
0x18001b171  movsx   edx, word ptr [rdi+114h]
0x18001b178  mov     [rsp+2B0h+var_234], r9d
0x18001b17d  mov     [rbp+1B0h+var_1A0], rdi
0x18001b181  mov     rax, [rcx]
0x18001b184  mov     [rbp+1B0h+var_220], r14
0x18001b188  mov     rax, [rax+20h]
0x18001b18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b191  lea     rbx, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x18001b198  test    eax, eax
0x18001b19a  jns     short loc_18001B1A5
0x18001b19c  mov     rax, rbx
0x18001b19f  mov     [rbp+1B0h+var_220], rbx
0x18001b1a3  jmp     short loc_18001B1A9
0x18001b1a5  mov     rax, [rbp+1B0h+var_220]
0x18001b1a9  movzx   eax, byte ptr [rax+4]
0x18001b1ad  mov     ecx, [r15+58h]
0x18001b1b1  mov     esi, [r15+28h]
0x18001b1b5  mov     [rsp+2B0h+var_260], al
0x18001b1b9  mov     eax, esi
0x18001b1bb  sub     eax, ecx
0x18001b1bd  mov     [rsp+2B0h+var_23C], r14d
0x18001b1c2  test    ecx, ecx
0x18001b1c4  mov     rcx, r15; this
0x18001b1c7  cmovg   esi, eax
0x18001b1ca  mov     [rsp+2B0h+var_238], esi
0x18001b1ce  call    ?GetiFormat@CTxtRange@@QEBAJXZ; CTxtRange::GetiFormat(void)
0x18001b1d3  mov     [rbp+1B0h+var_1E0], r14
0x18001b1d7  mov     edx, eax
0x18001b1d9  test    eax, eax
0x18001b1db  jns     short loc_18001B1E8
0x18001b1dd  mov     rax, [r15+30h]
0x18001b1e1  movsx   edx, word ptr [rax+114h]
0x18001b1e8  mov     rcx, cs:qword_1800A72D0
0x18001b1ef  lea     r8, [rbp+1B0h+var_1E0]
0x18001b1f3  mov     rax, [rcx]
0x18001b1f6  mov     rax, [rax+20h]
0x18001b1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ff  test    eax, eax
0x18001b201  jns     short loc_18001B209
0x18001b203  mov     [rbp+1B0h+var_1E0], rbx
0x18001b207  jmp     short loc_18001B20D
0x18001b209  mov     rbx, [rbp+1B0h+var_1E0]
0x18001b20d  movzx   ecx, byte ptr [rbx+4]; unsigned __int16
0x18001b211  call    ?GetFontSig@CW32System@@SAKG@Z; CW32System::GetFontSig(ushort)
0x18001b216  shl     eax, 8
0x18001b219  mov     edx, 200000h
0x18001b21e  bt      eax, 16h
0x18001b222  jb      short loc_18001B276
0x18001b224  mov     ecx, eax
0x18001b226  mov     r14d, 300000h
0x18001b22c  or      ecx, edx
0x18001b22e  cmp     ecx, 20000000h
0x18001b234  cmovnb  r14d, edx
0x18001b238  or      r14d, eax
0x18001b23b  test    r14d, 1E000000h
0x18001b242  jz      short loc_18001B266
0x18001b244  movzx   eax, word ptr cs:?_syslcid@CW32System@@0KA; ulong CW32System::_syslcid
0x18001b24b  and     eax, 3FFh
0x18001b250  cmp     eax, 12h
0x18001b253  jz      short loc_18001B25F
0x18001b255  cmp     eax, 4
0x18001b258  jz      short loc_18001B25F
0x18001b25a  cmp     eax, 11h
0x18001b25d  jnz     short loc_18001B266
0x18001b25f  bts     r14d, 17h
0x18001b264  jmp     short loc_18001B279
0x18001b266  test    r14d, 19300h
0x18001b26d  jz      short loc_18001B279
0x18001b26f  bts     r14d, 13h
0x18001b274  jmp     short loc_18001B279
0x18001b276  mov     r14d, eax
0x18001b279  mov     eax, [rdi+0B4h]
0x18001b27f  mov     dword ptr [rbp+1B0h+var_1E0], eax
0x18001b282  mov     rax, [rdi+40h]
0x18001b286  mov     rcx, rax; this
0x18001b289  mov     [rsp+2B0h+var_250], 0
0x18001b291  mov     [rbp+1B0h+var_1D8], rax
0x18001b295  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18001b29a  mov     rax, [rdi+40h]
0x18001b29e  mov     ebx, [rax+38h]
0x18001b2a1  movzx   eax, [rsp+2B0h+var_260]
0x18001b2a6  shr     ebx, 11h
0x18001b2a9  and     ebx, 1
0x18001b2ac  mov     [rbp+1B0h+var_228], ebx
0x18001b2af  sub     eax, 80h
0x18001b2b4  jz      short loc_18001B2D3
0x18001b2b6  sub     eax, 1
0x18001b2b9  jz      short loc_18001B2D3
0x18001b2bb  sub     eax, 1
0x18001b2be  jz      short loc_18001B2D3
0x18001b2c0  sub     eax, 4
0x18001b2c3  jz      short loc_18001B2D3
0x18001b2c5  cmp     eax, 2
0x18001b2c8  jz      short loc_18001B2D3
0x18001b2ca  xor     r9d, r9d
0x18001b2cd  mov     [rbp+1B0h+var_1E8], r9d
0x18001b2d1  jmp     short loc_18001B2DD
0x18001b2d3  mov     [rbp+1B0h+var_1E8], 1
0x18001b2da  xor     r9d, r9d
0x18001b2dd  lea     rcx, [r15+8]; this
0x18001b2e1  mov     dword ptr [rbp+1B0h+var_200], r9d
0x18001b2e5  mov     r11d, r9d
0x18001b2e8  call    ?fUseUIFont@CRchTxtPtr@@IEBA_NXZ; CRchTxtPtr::fUseUIFont(void)
0x18001b2ed  cmp     r14d, 400000h
0x18001b2f4  mov     [rsp+2B0h+var_258], al
0x18001b2f8  mov     eax, [rdi+0B4h]
0x18001b2fe  lea     rdx, [rbp+1B0h+var_160]
0x18001b302  mov     r8d, r9d
0x18001b305  mov     [rbp+1B0h+lpMem], rdx
0x18001b30c  setz    r8b
0x18001b310  mov     [rbp+1B0h+var_58], 100h
0x18001b31a  mov     [rbp+1B0h+var_18C], 0
0x18001b31e  test    byte ptr [rdi+0B4h], 1
0x18001b325  mov     [rsp+2B0h+var_25C], r8d
0x18001b32a  mov     [rsp+2B0h+var_240], eax
0x18001b32e  mov     [rbp+1B0h+var_220], r12
0x18001b332  jnz     short loc_18001B342
0x18001b334  cmp     dword ptr [r15+58h], 0
0x18001b339  mov     [rbp+1B0h+var_1F0], 1
0x18001b340  jnz     short loc_18001B346
0x18001b342  mov     [rbp+1B0h+var_1F0], r9d
0x18001b346  mov     edx, 4000h
0x18001b34b  test    [rdi+0B8h], dx
0x18001b352  jz      short loc_18001B39F
0x18001b354  mov     rcx, r15; this
0x18001b357  mov     [rsp+2B0h+var_250], 1E000000h
0x18001b35f  call    ?GetiFormat@CTxtRange@@QEBAJXZ; CTxtRange::GetiFormat(void)
0x18001b364  lea     rcx, [rdi+0F8h]; this
0x18001b36b  mov     edx, eax; int
0x18001b36d  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x18001b372  mov     r8d, [rsp+2B0h+var_25C]
0x18001b377  lea     rcx, [r15+8]
0x18001b37b  mov     r11d, dword ptr [rbp+1B0h+var_200]
0x18001b37f  xor     r9d, r9d
0x18001b382  movups  xmm0, xmmword ptr [rax]
0x18001b385  movups  xmmword ptr [rbp+20h], xmm0
0x18001b389  movups  xmm1, xmmword ptr [rax+10h]
0x18001b38d  movups  [rbp+1B0h+var_180], xmm1
0x18001b391  movsd   xmm0, qword ptr [rax+20h]
0x18001b396  mov     eax, [rsp+2B0h+var_240]
0x18001b39a  movsd   [rbp+1B0h+var_170], xmm0
0x18001b39f  cmp     [rsp+2B0h+var_258], 0
0x18001b3a4  jz      short loc_18001B3F9
0x18001b3a6  mov     edx, 1; int
0x18001b3ab  mov     rcx, r15; this
0x18001b3ae  call    ?GetCharSetMask@CTxtRange@@QEAAKH@Z; CTxtRange::GetCharSetMask(int)
0x18001b3b3  mov     r11d, dword ptr [rbp+1B0h+var_200]
0x18001b3b7  mov     ecx, eax
0x18001b3b9  and     eax, 300000h
0x18001b3be  xor     r9d, r9d
0x18001b3c1  cmp     eax, 300000h
0x18001b3c6  mov     edx, r9d
0x18001b3c9  mov     eax, [rsp+2B0h+var_240]
0x18001b3cd  setz    dl
0x18001b3d0  cmp     ecx, 400000h
0x18001b3d6  mov     [rbp+1B0h+var_1EC], edx
0x18001b3d9  lea     rcx, [r15+8]
0x18001b3dd  jnz     short loc_18001B3EC
0x18001b3df  mov     r8d, 1
0x18001b3e5  mov     [rsp+2B0h+var_25C], r8d
0x18001b3ea  jmp     short loc_18001B3FD
0x18001b3ec  mov     r8d, r9d
0x18001b3ef  mov     [rsp+2B0h+var_25C], r9d
0x18001b3f4  mov     [rbp+1B0h+var_1EC], edx
0x18001b3f7  jmp     short loc_18001B3FD
0x18001b3f9  mov     [rbp+1B0h+var_1EC], r9d
0x18001b3fd  test    r12, r12
0x18001b400  jnz     short loc_18001B40A
0x18001b402  mov     r13d, r9d
0x18001b405  jmp     loc_18001B54E
0x18001b40a  test    ebx, ebx
0x18001b40c  jz      loc_18001B543
0x18001b412  test    r13d, r13d
0x18001b415  jns     short loc_18001B429
0x18001b417  mov     rcx, r12; unsigned __int16 *
0x18001b41a  call    ?wcslen@CW32System@@SA_KPEBG@Z; CW32System::wcslen(ushort const *)
0x18001b41f  mov     r13, rax
0x18001b422  lea     rcx, [r15+8]
0x18001b426  test    r13d, r13d
0x18001b429  mov     rax, [rbp+1B0h+var_210]
0x18001b42d  jz      short loc_18001B472
0x18001b42f  test    rax, rax
0x18001b432  jnz     short loc_18001B472
0x18001b434  mov     edx, r13d; int
0x18001b437  lea     rcx, [rbp+1B0h+var_160]; this
0x18001b43b  call    ?GetBuf@CTempWcharBuf@@QEAAPEAGJ@Z; CTempWcharBuf::GetBuf(long)
0x18001b440  mov     [rbp+1B0h+var_210], rax
0x18001b444  test    rax, rax
0x18001b447  jnz     short loc_18001B46E
0x18001b449  mov     rcx, [rbp+1B0h+lpMem]; lpMem
0x18001b450  lea     rax, [rbp+1B0h+var_160]
0x18001b454  cmp     rcx, rax
0x18001b457  jz      short loc_18001B45E
0x18001b459  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18001b45e  mov     rcx, [rbp+1B0h+var_1D8]; this
0x18001b462  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x18001b467  xor     eax, eax
0x18001b469  jmp     loc_18001BDDD
0x18001b46e  lea     rcx, [r15+8]; this
0x18001b472  mov     edx, [r15+58h]
0x18001b476  mov     [rbp+1B0h+var_220], rax
0x18001b47a  test    edx, edx
0x18001b47c  jg      short loc_18001B488
0x18001b47e  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18001b483  jmp     loc_18001B524
0x18001b488  movups  xmm0, xmmword ptr [r15+48h]
0x18001b48d  neg     edx; int
0x18001b48f  lea     rcx, [rbp+1B0h+var_200]; this
0x18001b493  movups  [rbp+1B0h+var_200], xmm0
0x18001b497  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18001b49c  mov     rcx, qword ptr [rbp+1B0h+var_200]
0x18001b4a0  test    rcx, rcx
0x18001b4a3  jz      short loc_18001B4E6
0x18001b4a5  cmp     dword ptr [rcx+8], 0
0x18001b4a9  jz      short loc_18001B4E6
0x18001b4ab  mov     edx, [rcx+8]
0x18001b4ae  test    edx, edx
0x18001b4b0  jle     short loc_18001B4D1
0x18001b4b2  mov     eax, dword ptr [rbp+1B0h+var_200+8]
0x18001b4b5  cmp     eax, edx
0x18001b4b7  jge     short loc_18001B4D1
0x18001b4b9  mov     r8, [rcx]
0x18001b4bc  test    r8, r8
0x18001b4bf  jz      short loc_18001B4D1
0x18001b4c1  test    eax, eax
0x18001b4c3  js      short loc_18001B4D1
0x18001b4c5  imul    eax, [rcx+10h]
0x18001b4c9  movsxd  rdx, eax
0x18001b4cc  add     rdx, r8
0x18001b4cf  jmp     short loc_18001B4D3
0x18001b4d1  xor     edx, edx
0x18001b4d3  movzx   edx, word ptr [rdx+4]
0x18001b4d7  mov     qword ptr [rbp+1B0h+var_200], 0
0x18001b4df  test    dx, dx
0x18001b4e2  jns     short loc_18001B4F5
0x18001b4e4  jmp     short loc_18001B4EE
0x18001b4e6  mov     qword ptr [rbp+1B0h+var_200], 0
0x18001b4ee  movzx   edx, word ptr [rdi+116h]
0x18001b4f5  mov     rcx, cs:qword_1800A72C8
0x18001b4fc  lea     r8, [rbp+1B0h+var_200]
0x18001b500  movsx   edx, dx
0x18001b503  mov     rax, [rcx]
0x18001b506  mov     rax, [rax+20h]
0x18001b50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b50f  test    eax, eax
0x18001b511  jns     short loc_18001B520
0x18001b513  lea     rax, ?g_defaultPF@@3VCParaFormat@@A; CParaFormat g_defaultPF
0x18001b51a  mov     qword ptr [rbp+1B0h+var_200], rax
0x18001b51e  jmp     short loc_18001B524
0x18001b520  mov     rax, qword ptr [rbp+1B0h+var_200]
0x18001b524  movzx   r11d, word ptr [rax+2]
0x18001b529  mov     r8d, [rsp+2B0h+var_25C]
0x18001b52e  mov     eax, [rsp+2B0h+var_240]
0x18001b532  shr     r11d, 0Eh
0x18001b536  and     r11d, 1
0x18001b53a  mov     dword ptr [rbp+1B0h+var_200], r11d
0x18001b53e  xor     r9d, r9d
0x18001b541  jmp     short loc_18001B54E
0x18001b543  test    r13d, r13d
0x18001b546  jns     short loc_18001B54E
0x18001b548  mov     r13d, 3FFFFFFFh
0x18001b54e  shr     eax, 13h
0x18001b551  xor     edx, edx
0x18001b553  and     eax, 1
0x18001b556  mov     [rsp+2B0h+var_248], r9d
0x18001b55b  mov     [rsp+2B0h+var_24C], r9d
0x18001b560  mov     r10d, r9d
0x18001b563  mov     [rsp+2B0h+var_244], r9d
0x18001b568  mov     [rsp+2B0h+var_240], eax
0x18001b56c  mov     [rsp+2B0h+var_254], edx
0x18001b570  test    r13d, r13d
0x18001b573  jz      loc_18001BD0C
  ... truncated ...
```
