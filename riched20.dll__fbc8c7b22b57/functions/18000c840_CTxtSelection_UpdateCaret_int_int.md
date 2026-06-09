# CTxtSelection::UpdateCaret(int,int)

- ea: `0x18000c840`
- end: `0x18000da10`
- name: `?UpdateCaret@CTxtSelection@@QEAAHHH@Z`
- size: `4560`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int, int)`
- caller_count: `17`
- callee_count: `27`
- tags: `installer_update`

## callers

- `0x1800066b0`
- `0x18000bac0`
- `0x180027794`
- `0x18002d048`
- `0x18002da98`
- `0x180035230`
- `0x180039460`
- `0x180040500`
- `0x180040d50`
- `0x18004a41c`
- `0x18005a420`
- `0x18005e9bc`
- `0x18005ea08`
- `0x18005ec00`
- `0x1800813b8`
- `0x180082e70`
- `0x1800832a8`

## callees

- `0x180009070`
- `0x18000b5e0`
- `0x18000c6f0`
- `0x18000c840`
- `0x18000da20`
- `0x18000dad0`
- `0x18000e67c`
- `0x18000e708`
- `0x18000f280`
- `0x18000fe40`
- `0x180010260`
- `0x180015448`
- `0x18001f980`
- `0x180022ad4`
- `0x180023884`
- `0x1800267a0`
- `0x180032770`
- `0x180037b10`
- `0x180039990`
- `0x18003a200`
- `0x18003c908`
- `0x18003d748`
- `0x180043044`
- `0x180045000`
- `0x180046cb4`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18000ca52`
- `KERNEL32!MulDiv` at `0x18000d31b`
- `KERNEL32!MulDiv` at `0x18000d33a`
- `KERNEL32!MulDiv` at `0x18000d357`
- `KERNEL32!MulDiv` at `0x18000d374`
- `KERNEL32!MulDiv` at `0x18000d38a`
- `KERNEL32!MulDiv` at `0x18000d3a5`
- `KERNEL32!MulDiv` at `0x18000d4f3`
- `KERNEL32!MulDiv` at `0x18000ca52`
- `KERNEL32!MulDiv` at `0x18000d31b`
- `KERNEL32!MulDiv` at `0x18000d33a`
- `KERNEL32!MulDiv` at `0x18000d357`
- `KERNEL32!MulDiv` at `0x18000d374`
- `KERNEL32!MulDiv` at `0x18000d38a`
- `KERNEL32!MulDiv` at `0x18000d3a5`
- `KERNEL32!MulDiv` at `0x18000d4f3`
- `KERNEL32!EnterCriticalSection` at `0x18000cda2`
- `KERNEL32!EnterCriticalSection` at `0x18000cda2`
- `KERNEL32!LeaveCriticalSection` at `0x18000cf74`
- `KERNEL32!LeaveCriticalSection` at `0x18000d492`
- `KERNEL32!LeaveCriticalSection` at `0x18000cf74`
- `KERNEL32!LeaveCriticalSection` at `0x18000d492`
- `GDI32!GetDeviceCaps` at `0x18000ce6e`
- `GDI32!GetDeviceCaps` at `0x18000ce6e`

## pseudocode

```c
__int64 __fastcall CTxtSelection::UpdateCaret(CTxtSelection *this, int a2, int a3)
{
  __int64 v6; // r9
  __int64 v7; // rdi
  CRchTxtPtr *v8; // r13
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  _QWORD *v12; // r8
  int v13; // r15d
  __int64 v14; // rcx
  _DWORD *v15; // rcx
  unsigned int v16; // eax
  bool v17; // zf
  int v18; // edx
  __int16 v19; // ax
  int v20; // edx
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // r12d
  int v24; // edi
  int v25; // r15d
  int v26; // r13d
  int ZoomDenominator; // eax
  __int64 v28; // rcx
  int v29; // edx
  int v30; // edx
  int v31; // eax
  __int64 v32; // rcx
  int v33; // edx
  int v34; // edx
  int v35; // r15d
  int v36; // eax
  __int64 v37; // rcx
  int v38; // edx
  int v39; // edx
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v43; // eax
  __int32 v44; // r15d
  __int32 v45; // ecx
  __int32 v46; // edi
  __int32 v47; // ebx
  __int32 v48; // r15d
  __int128 v49; // xmm0
  __int64 v50; // r8
  __int64 v51; // r10
  int v52; // ecx
  int v53; // r14d
  int v54; // edx
  int v55; // eax
  int v56; // r12d
  int v57; // eax
  int v58; // r9d
  _DWORD *v59; // r8
  int v60; // ecx
  _DWORD *v61; // r8
  __int64 v62; // rax
  int v63; // r12d
  int v64; // r14d
  int v65; // r13d
  __int64 v66; // rax
  int v67; // eax
  int v68; // r9d
  __int64 v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rcx
  _QWORD *v72; // rdx
  __int64 v73; // rax
  CDisplay *v74; // rcx
  HDC v75; // r14
  int v76; // eax
  __int64 v77; // rdx
  __int64 v78; // rcx
  int v79; // r12d
  int DeviceCaps; // r14d
  struct CCcs *Ccs; // r12
  struct CCharFormat *v82; // r13
  int v83; // edx
  int v84; // r14d
  __int64 v85; // rax
  int v86; // ecx
  __int16 v87; // ax
  int v88; // edx
  int v89; // r10d
  int v90; // r9d
  int v91; // eax
  int v92; // r8d
  __int64 *v93; // r11
  __int64 *v94; // r14
  __int64 *v95; // r12
  __int64 *v96; // rax
  int v97; // eax
  __int64 *v98; // r9
  __int64 *v99; // rax
  int v100; // eax
  int v101; // r14d
  int v102; // r12d
  int v103; // r9d
  __int64 v104; // r13
  __int32 v105; // r11d
  __int64 v106; // rdx
  __int32 v107; // eax
  int v108; // eax
  int v109; // eax
  int v110; // r11d
  BOOL v112; // eax
  int v113; // edi
  int v114; // edx
  int v115; // eax
  int v116; // r9d
  int v117; // ecx
  int v118; // r10d
  int v119; // eax
  int v120; // ecx
  int IsHScrollEnabled; // eax
  int v122; // eax
  int SelBarInPixels; // eax
  __int16 v124; // ax
  int v125; // eax
  int v126; // eax
  int v127; // eax
  CRchTxtPtr *v128; // rcx
  unsigned __int8 v129; // r11
  int v130; // r13d
  unsigned __int8 Level; // r12
  unsigned __int8 v132; // r11
  int v133; // ecx
  int v134; // eax
  CTxtPtr *v135; // rcx
  const struct CParaFormat *PF; // rax
  int v137; // r9d
  char v138; // cl
  struct CLine *Line; // rax
  unsigned int v140; // edi
  struct CLine *v141; // rax
  struct CLine *v142; // rax
  __int64 v143; // r9
  int v144; // r11d
  __int64 v145; // r10
  unsigned int v146; // eax
  int v147; // ebx
  int v148; // eax
  bool v149; // sf
  int v150; // ebx
  int v151; // eax
  BOOL v152; // [rsp+50h] [rbp-B0h]
  unsigned int v153; // [rsp+54h] [rbp-ACh] BYREF
  int v154; // [rsp+58h] [rbp-A8h] BYREF
  int v155; // [rsp+5Ch] [rbp-A4h] BYREF
  BOOL v156; // [rsp+60h] [rbp-A0h]
  int nDenominator; // [rsp+64h] [rbp-9Ch]
  int v158; // [rsp+68h] [rbp-98h]
  int v159; // [rsp+6Ch] [rbp-94h]
  unsigned int v160; // [rsp+70h] [rbp-90h]
  int v161; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v162; // [rsp+78h] [rbp-88h] BYREF
  __int64 v163; // [rsp+80h] [rbp-80h]
  __int64 v164; // [rsp+88h] [rbp-78h]
  struct CCharFormat *v165; // [rsp+90h] [rbp-70h] BYREF
  int v166; // [rsp+98h] [rbp-68h]
  __int64 v167; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v168; // [rsp+A8h] [rbp-58h]
  _QWORD *v169; // [rsp+B0h] [rbp-50h]
  __int64 *v170; // [rsp+B8h] [rbp-48h]
  _QWORD v171[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v172; // [rsp+D0h] [rbp-30h] BYREF
  int v173; // [rsp+E0h] [rbp-20h]
  __int64 v174; // [rsp+E4h] [rbp-1Ch]
  int v175; // [rsp+ECh] [rbp-14h]
  __int64 v176; // [rsp+F0h] [rbp-10h] BYREF
  int v177; // [rsp+F8h] [rbp-8h]
  int v178; // [rsp+FCh] [rbp-4h]
  __int64 v179; // [rsp+100h] [rbp+0h]
  int v180; // [rsp+108h] [rbp+8h]
  int v181; // [rsp+10Ch] [rbp+Ch]
  __int64 v182; // [rsp+110h] [rbp+10h]
  __m128i v183; // [rsp+120h] [rbp+20h]
  int nNumber[4]; // [rsp+130h] [rbp+30h] BYREF
  __m128i v185; // [rsp+140h] [rbp+40h] BYREF

  v6 = *(_QWORD *)(*((_QWORD *)this + 13) + 48LL);
  if ( v6 )
  {
    *(_DWORD *)(v6 + 16) |= 1u;
    v114 = *(_DWORD *)(v6 + 16);
    if ( (v114 & 2) == 0 )
      *(_DWORD *)(v6 + 16) = (2 * a2) ^ (v114 ^ (2 * a2)) & 0xFFFFFFFD;
    return 0;
  }
  v7 = *((_QWORD *)this + 6);
  v8 = (CTxtSelection *)((char *)this + 8);
  v164 = v7;
  v9 = *(_DWORD *)(v7 + 180);
  if ( (v9 & 0x10000) != 0 )
    return 0;
  if ( (v9 & 8) == 0 )
  {
    if ( a2 )
      *(_DWORD *)(v7 + 180) = v9 | 0x8000;
    return 0;
  }
  v10 = *(_QWORD *)(v7 + 48);
  v161 = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 248LL))(v10, &v161);
  v152 = 0;
  v156 = 0;
  v11 = CTxtPtr::IsAfterEOP((CTxtSelection *)((char *)this + 24));
  v12 = (_QWORD *)*((_QWORD *)this + 13);
  v162 = 0;
  v13 = v11;
  v167 = 0;
  v168 = 0;
  v169 = v12;
  v170 = 0;
  v14 = *v12;
  nDenominator = v11;
  (*(void (__fastcall **)(_QWORD *, __int64 *))(v14 + 24))(v12, &v167);
  v15 = (_DWORD *)*((_QWORD *)this + 13);
  v185 = 0;
  v183 = 0;
  v158 = v15[18];
  v16 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v15 + 288LL))(v15);
  v17 = *(_BYTE *)(v7 + 180) >= 0;
  v160 = v16;
  if ( !v17 )
  {
    v18 = *((_DWORD *)this + 34);
    if ( (v18 & 8) != 0 || a3 )
    {
      v19 = *((_WORD *)this + 49);
      v20 = v18 | 8;
      *((_DWORD *)this + 34) = v20;
      if ( (v20 & 0xA20) == 0 && (v19 & 0x10) == 0 )
      {
        *((_DWORD *)this + 34) = v20 | 0x200;
        CTxtSelection::CheckChangeKeyboardLayout(this);
        if ( !v13
          && (*(_BYTE *)(v7 + 192) & 1) != 0
          && (unsigned int)CRunPtrBase::IsValid((CTxtSelection *)((char *)this + 56))
          && (!*((_DWORD *)this + 17) || !(unsigned int)CRunPtrBase::GetCchLeft((CTxtSelection *)((char *)this + 56))) )
        {
          CRunPtrBase::AdjustBackward((CTxtSelection *)((char *)this + 56));
          v113 = (unsigned int)*((unsigned __int8 *)CRchTxtPtr::GetCF(v8) + 4) - 177 <= 1;
          CRunPtrBase::AdjustForward((CTxtSelection *)((char *)this + 56));
          if ( v113 != (unsigned int)*((unsigned __int8 *)CRchTxtPtr::GetCF(v8) + 4) - 177 <= 1 )
          {
            if ( v113 != (unsigned int)CW32System::IsBiDiLcid((unsigned __int16)CW32System::_hklCurrent) )
              v13 = 1;
            nDenominator = v13;
          }
          v7 = v164;
        }
        *((_DWORD *)this + 34) &= ~0x200u;
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, __m128i *))(**(_QWORD **)(v7 + 48) + 192LL))(*(_QWORD *)(v7 + 48), &v185);
  v21 = *((_QWORD *)this + 13);
  v183 = v185;
  *(_OWORD *)nNumber = 0;
  v22 = *(_QWORD *)(v21 + 16);
  *(_DWORD *)(v21 + 68) = _mm_cvtsi128_si32(_mm_srli_si128(v185, 12)) - _mm_cvtsi128_si32(_mm_srli_si128(v185, 4));
  if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v22 + 48) + 200LL))(*(_QWORD *)(v22 + 48), nNumber) < 0 )
  {
    v35 = 0;
    v40 = 0;
    v24 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    v23 = _mm_cvtsi128_si32((__m128i)0LL);
  }
  else
  {
    v23 = nNumber[0];
    v24 = nNumber[1];
    v25 = nNumber[1];
    v26 = nNumber[2];
    v155 = nNumber[3];
    if ( nNumber[0] )
    {
      ZoomDenominator = CDisplay::GetZoomDenominator((CDisplay *)v21);
      v28 = *(_QWORD *)(v21 + 16);
      v29 = *(unsigned __int16 *)(v28 + 202);
      if ( !*(_WORD *)(v28 + 202) )
      {
        v29 = 1;
        if ( *(int *)(v21 + 68) > 0 )
          v29 = *(_DWORD *)(v21 + 68);
      }
      if ( v29 != ZoomDenominator )
        v23 = MulDiv(v23, v29, ZoomDenominator);
      v30 = *(__int16 *)(v21 + 36);
      if ( v30 != 2540 && v23 )
        v23 = MulDiv(v23, v30, 2540);
      v24 = nNumber[1];
    }
    else
    {
      v23 = 0;
    }
    if ( v25 )
    {
      v31 = CDisplay::GetZoomDenominator((CDisplay *)v21);
      v32 = *(_QWORD *)(v21 + 16);
      v33 = *(unsigned __int16 *)(v32 + 202);
      if ( !*(_WORD *)(v32 + 202) )
      {
        v33 = 1;
        if ( *(int *)(v21 + 68) > 0 )
          v33 = *(_DWORD *)(v21 + 68);
      }
      if ( v33 != v31 && (!v31 || v24) )
        v24 = MulDiv(v24, v33, v31);
      v34 = *(__int16 *)(v21 + 38);
      if ( v34 != 2540 && v24 )
        v24 = MulDiv(v24, v34, 2540);
    }
    else
    {
      v24 = 0;
    }
    if ( v26 )
    {
      v35 = nNumber[2];
      v36 = CDisplay::GetZoomDenominator((CDisplay *)v21);
      v37 = *(_QWORD *)(v21 + 16);
      v38 = *(unsigned __int16 *)(v37 + 202);
      if ( !*(_WORD *)(v37 + 202) )
      {
        v38 = 1;
        if ( *(int *)(v21 + 68) > 0 )
          v38 = *(_DWORD *)(v21 + 68);
      }
      if ( v38 != v36 && (!v36 || v35) )
        v35 = MulDiv(v35, v38, v36);
      v39 = *(__int16 *)(v21 + 36);
      if ( v39 != 2540 && v35 )
        v35 = MulDiv(v35, v39, 2540);
    }
    else
    {
      v35 = 0;
    }
    if ( v155 )
      v40 = CDisplay::HimetricYtoDY((CDisplay *)v21, nNumber[3]);
    else
      v40 = 0;
    v8 = (CTxtSelection *)((char *)this + 8);
  }
  v183.m128i_i32[0] += v23;
  v183.m128i_i32[1] += v24;
  v183.m128i_i32[2] -= v35;
  v183.m128i_i32[3] -= v40;
  v41 = *(_QWORD *)(v21 + 16);
  if ( (*(_DWORD *)(v41 + 180) & 0x2000000) != 0
    && (v42 = *(_QWORD *)(v41 + 48),
        v155 = 0,
        v154 = 0,
        (*(void (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v42 + 400LL))(v42, &v155, &v154),
        (v154 & 0x4000) != 0) )
  {
    SelBarInPixels = CDisplay::GetSelBarInPixels((CDisplay *)v21);
    v45 = v183.m128i_i32[0];
    v44 = v183.m128i_i32[2] - SelBarInPixels;
    v183.m128i_i32[2] -= SelBarInPixels;
  }
  else
  {
    v43 = CDisplay::GetSelBarInPixels((CDisplay *)v21);
    v44 = v183.m128i_i32[2];
    v45 = v43 + v183.m128i_i32[0];
    v183.m128i_i32[0] += v43;
  }
  v46 = v185.m128i_i32[1];
  v47 = v185.m128i_i32[3];
  if ( v183.m128i_i32[1] > v185.m128i_i32[1] )
    v46 = v183.m128i_i32[1];
  if ( v183.m128i_i32[3] < v185.m128i_i32[3] )
    v47 = v183.m128i_i32[3];
  v48 = v44 - v45;
  if ( a2 )
  {
    v152 = (v161 & 0x40) != 0;
    v125 = *(_DWORD *)(v164 + 180);
    v156 = (v161 & 0x80) != 0;
    if ( (v125 & 0x80000) == 0 || (*((_DWORD *)this + 34) & 0x2000) == 0 )
    {
      if ( (v125 & 0x80u) == 0 && (v125 & 0x20) != 0 )
      {
        v152 = (v161 & 0x40) != 0;
        v156 = (v161 & 0x80) != 0;
        if ( (v161 & 0x40) != 0 || (v161 & 0x80) != 0 )
        {
          v126 = v125 | 0x8000;
          *(_DWORD *)(v164 + 180) = v126;
          if ( (v126 & 0x80000) == 0 || (*((_DWORD *)this + 34) & 0x1000) == 0 )
          {
            v156 = 0;
            v152 = 0;
          }
        }
      }
      else
      {
        v152 = (v161 & 0x40) != 0;
        v156 = (v161 & 0x80) != 0;
      }
    }
  }
  *((_DWORD *)this + 34) &= ~0x1000u;
  if ( !*((_DWORD *)this + 22)
    && (*(_WORD *)(*((_QWORD *)this + 6) + 184LL) & 0x2000) != 0
    && (*((_WORD *)CRchTxtPtr::GetPF(v8) + 1) & 0x100) != 0 )
  {
    goto LABEL_155;
  }
  v49 = *(_OWORD *)((char *)this + 24);
  v50 = *((_QWORD *)this + 7);
  v51 = *((_QWORD *)this + 9);
  v52 = *((_DWORD *)this + 16);
  v53 = *((_DWORD *)this + 17);
  v54 = *((_DWORD *)this + 20);
  v171[0] = &CRchTxtPtr::`vftable';
  v55 = *((_DWORD *)this + 10);
  v172 = v49;
  *(_QWORD *)&v49 = *(_QWORD *)((char *)this + 44);
  v165 = 0;
  v56 = *((_DWORD *)this + 21);
  v155 = v55;
  v173 = v55;
  v57 = *((_DWORD *)this + 13);
  v174 = v49;
  v175 = v57;
  v176 = v50;
  v177 = v52;
  v178 = v53;
  v179 = v51;
  v180 = v54;
  v181 = v56;
  if ( v50 )
  {
    v58 = *(_DWORD *)(v50 + 8);
    if ( v58 )
    {
      v59 = v58 > 0 && v52 < v58 && *(_QWORD *)v50 && v52 >= 0
          ? (_DWORD *)(*(_QWORD *)v50 + *(_DWORD *)(v50 + 16) * v52)
          : 0LL;
      if ( *v59 == v53 && v52 < v58 - 1 )
      {
        v178 = 0;
        v177 = v52 + 1;
      }
    }
  }
  if ( v51 )
  {
    v60 = *(_DWORD *)(v51 + 8);
    if ( v60 )
    {
      v61 = v60 > 0 && v54 < v60 && *(_QWORD *)v51 && v54 >= 0
          ? (_DWORD *)(*(_QWORD *)v51 + *(_DWORD *)(v51 + 16) * v54)
          : 0LL;
      if ( *v61 == v56 && v54 < v60 - 1 )
      {
        v181 = 0;
        v180 = v54 + 1;
      }
    }
  }
  v62 = *((_QWORD *)this + 6);
  v63 = -1;
  v64 = 8216;
  v159 = -1;
  if ( (*(_BYTE *)(v62 + 192) & 1) != 0 && (unsigned int)CRunPtrBase::IsValid((CTxtSelection *)((char *)this + 56)) )
  {
    v127 = *((_DWORD *)this + 34);
    if ( (v127 & 0x800) != 0 )
    {
      v64 = ((((v127 & 1) == 0) + 1) << 14) | 0x2018;
    }
    else if ( !(unsigned int)CRchTxtPtr::GetIchRunCF((CTxtSelection *)((char *)this + 8))
           || !(unsigned int)CRchTxtPtr::GetCchLeftRunCF(v128) )
    {
      LOWORD(v153) = 0;
      CRchTxtPtr::IsParaRTL((CRchTxtPtr *)v171);
      CRunPtrBase::AdjustBackward((CRunPtrBase *)&v176);
      v130 = v155;
      if ( v155 )
        Level = CFormatRunPtr::GetLevel((CFormatRunPtr *)&v176, 0);
      else
        Level = v129;
      CRunPtrBase::AdjustForward((CRunPtrBase *)&v176);
      if ( v130 == (unsigned int)CTxtPtr::GetTextLength((CTxtPtr *)&v172) )
      {
        v133 = 0;
      }
      else
      {
        v132 = CFormatRunPtr::GetLevel((CFormatRunPtr *)&v176, (struct CBiDiLevel *)&v153);
        v133 = BYTE1(v153) & 1;
      }
      if ( Level != v132 || v133 )
      {
        v63 = -1;
        if ( !nDenominator && (unsigned int)CRchTxtPtr::Advance((CRchTxtPtr *)v171, -1) )
        {
          v64 = 8218;
          v134 = CTxtPtr::IsAfterEOP((CTxtPtr *)&v172);
          *((_DWORD *)this + 34) &= ~1u;
          *((_DWORD *)this + 34) |= v134 == 0;
        }
      }
      else
      {
        v63 = -1;
      }
    }
  }
  if ( (*(int (__fastcall **)(_QWORD, _QWORD *, __m128i *, _QWORD, __int64 *, __int64 *, int, struct CCharFormat **))(**((_QWORD **)this + 13) + 240LL))(
         *((_QWORD *)this + 13),
         v171,
         &v185,
         *((_DWORD *)this + 34) & 1,
         &v162,
         &v167,
         v64,
         &v165) < 0 )
  {
LABEL_155:
    v104 = v164;
    goto LABEL_159;
  }
  v153 = 0;
  v155 = v47 - v46;
  v65 = 0;
  v66 = *((_QWORD *)this + 6);
  v154 = 0;
  if ( (*(_BYTE *)(v66 + 180) & 1) == 0
    && (*(_DWORD *)(*((_QWORD *)this + 13) + 56LL) & 0x20000) != 0
    && (*((_BYTE *)this + 136) & 1) == 0
    && *((_DWORD *)this + 10) == (unsigned int)CTxtPtr::GetTextLength((CTxtSelection *)((char *)this + 24))
    && (unsigned int)CTxtPtr::IsAfterEOP(v135) )
  {
    PF = CTxtSelection::GetPF(this);
    v137 = v183.m128i_i32[0];
    v138 = *((_BYTE *)PF + 16);
    if ( v138 == 3 )
    {
      v137 = (v183.m128i_i32[0] + v183.m128i_i32[2]) / 2;
    }
    else if ( v138 == 2 )
    {
      v137 = v183.m128i_i32[2];
    }
    LODWORD(v162) = v137 - v158;
    Line = CLinePtr::GetLine((CLinePtr *)&v167);
    v67 = *((__int16 *)Line + 6) + HIDWORD(v162);
    HIDWORD(v162) = v67;
  }
  else
  {
    v67 = HIDWORD(v162);
    v68 = v162;
  }
  v166 = v67;
  *((_DWORD *)this + 30) = v68;
  EnterCriticalSection(&g_CriticalSection);
  v69 = (unsigned int)*((__int16 *)this + 48);
  v70 = *((_QWORD *)this + 6);
  v182 = v70;
  v165 = 0;
  if ( (int)v69 < 0 )
    v69 = (unsigned int)*(__int16 *)(v70 + 276);
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, struct CCharFormat **))(*(_QWORD *)qword_1800A72D0 + 32LL))(
         qword_1800A72D0,
         v69,
         &v165) < 0 )
    v165 = (struct CCharFormat *)g_defaultCF;
  v71 = *((_QWORD *)this + 13);
  v72 = (_QWORD *)(v71 + 16);
  if ( !v71 )
    v72 = 0;
  *(_QWORD *)nNumber = v72;
  v73 = v72[1];
  v163 = v73;
  if ( v73
    || (v73 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v72 + 48LL) + 24LL))(*(_QWORD *)(*v72 + 48LL)),
        (v163 = v73) != 0) )
  {
    v74 = (CDisplay *)*((_QWORD *)this + 13);
    v75 = (HDC)v73;
    v159 = -1;
    v76 = CDisplay::GetZoomDenominator(v74);
    v77 = *((_QWORD *)this + 13);
    nDenominator = v76;
    v78 = *(_QWORD *)(v77 + 16);
    v79 = *(unsigned __int16 *)(v78 + 202);
    if ( !*(_WORD *)(v78 + 202) )
    {
      v79 = *(_DWORD *)(v77 + 68);
      if ( v79 <= 0 )
        v79 = 1;
    }
    DeviceCaps = GetDeviceCaps(v75, 90);
    if ( v79 != nDenominator && (!nDenominator || DeviceCaps) )
      DeviceCaps = MulDiv(DeviceCaps, v79, nDenominator);
    Ccs = CFontCache::GetCcs(qword_1800A6FC0, v165, DeviceCaps, 0, 0);
    if ( Ccs )
    {
      v82 = v165;
      v83 = 0;
      nDenominator = 0;
      if ( *((_WORD *)v165 + 5) )
      {
        v83 = CW32System::MulDiv(*((__int16 *)v165 + 5), DeviceCaps, 1440);
        nDenominator = v83;
      }
      if ( (*(_DWORD *)v82 & 0x20000) != 0 )
      {
        v84 = *((__int16 *)Ccs + 55);
      }
      else
      {
        v84 = 0;
        if ( (*(_DWORD *)v82 & 0x10000) != 0 )
          v84 = *((__int16 *)Ccs + 56);
      }
      v85 = *((_QWORD *)this + 6);
      if ( (*(_BYTE *)(v85 + 180) & 1) != 0
        && (*(_BYTE *)(v85 + 188) & 4) == 0
        && (*(_DWORD *)(*(_QWORD *)(v182 + 64) + 56LL) & 0x20000) != 0
        && (*((_BYTE *)Ccs + 123) & 8) != 0 )
      {
        v86 = *((__int16 *)Ccs + 45);
        if ( *((_WORD *)Ccs + 45) )
        {
          v124 = MulDiv(v86, 15, 100);
          v83 = nDenominator;
          LOWORD(v86) = v124;
        }
      }
      else
      {
        LOWORD(v86) = 0;
      }
      v65 = (__int16)v86 + *((__int16 *)Ccs + 46) - v84 - v83;
      v87 = *((_WORD *)Ccs + 5);
      v159 = *((__int16 *)Ccs + 45) + 2 * (__int16)v86;
      if ( v87 )
        *((_WORD *)Ccs + 5) = v87 - 1;
    }
    if ( !*(_QWORD *)(*(_QWORD *)nNumber + 8LL) )
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(**(_QWORD **)nNumber + 48LL) + 32LL))(
        *(_QWORD *)(**(_QWORD **)nNumber + 48LL),
        v163);
    LeaveCriticalSection(&g_CriticalSection);
    v63 = v159;
  }
  else
  {
    LeaveCriticalSection(&g_CriticalSection);
  }
  v88 = v63 - v65;
  v89 = v65;
  v90 = v63 - v65;
  if ( v167 )
  {
    if ( !*(_DWORD *)(v167 + 8) )
      goto LABEL_133;
    v91 = *(_DWORD *)(v167 + 8);
    v92 = v168;
    if ( v91 > 0 && (int)v168 < v91 && *(_QWORD *)v167 && (int)v168 >= 0 )
      v93 = (__int64 *)(*(_QWORD *)v167 + *(_DWORD *)(v167 + 16) * (int)v168);
    else
      v93 = 0;
    v94 = v170;
  }
  else
  {
    v94 = v170;
    if ( !v170 )
      goto LABEL_133;
    v92 = v168;
    v93 = v170;
  }
  v95 = g_defaultLi;
  v96 = g_defaultLi;
  if ( v93 )
    v96 = v93;
  if ( *((_WORD *)v96 + 7) != 0xFFFF )
  {
    if ( v167 )
    {
      v97 = *(_DWORD *)(v167 + 8);
      if ( v97 > 0 && v92 < v97 && *(_QWORD *)v167 && v92 >= 0 )
        v98 = (__int64 *)(*(_QWORD *)v167 + *(_DWORD *)(v167 + 16) * v92);
      else
        v98 = 0;
    }
    else
    {
      v98 = v94;
    }
    v99 = g_defaultLi;
    if ( v98 )
      v99 = v98;
    v89 = *((__int16 *)v99 + 7);
    if ( v167 )
    {
      v100 = *(_DWORD *)(v167 + 8);
      if ( v100 > 0 && v92 < v100 && *(_QWORD *)v167 && v92 >= 0 )
        v94 = (__int64 *)(*(_QWORD *)v167 + *(_DWORD *)(v167 + 16) * v92);
      else
        v94 = 0;
    }
    if ( v94 )
      v95 = v94;
    v90 = *((__int16 *)v95 + 6) - v89;
  }
  v63 = v159;
LABEL_133:
  v17 = v63 == 0;
  v101 = v90;
  v102 = v89;
  if ( !v17 )
  {
    if ( v88 < v90 )
      v101 = v88;
    if ( v65 < v89 )
      v102 = v65;
  }
  if ( v152 )
  {
    if ( v101 > v155 )
    {
      v102 = 0;
      v101 = v155;
      v153 = 0;
      v118 = 0;
    }
    else
    {
      v115 = v102 + v101;
      if ( v102 + v101 > v155 )
      {
        v153 = 0;
        v102 = v155 - v101;
        v118 = 0;
      }
      else
      {
        v116 = v90 - v101;
        v117 = v116 + v115;
        if ( v116 + v115 > v155 )
        {
          v153 = v155 - v115;
          v118 = 0;
        }
        else
        {
          v118 = v89 - v102;
          v153 = v116;
          v119 = v118 + v117;
          v120 = v155 - v117;
          if ( v119 > v155 )
            v118 = v120;
        }
      }
    }
    v154 = v118;
  }
  v103 = v183.m128i_i32[0];
  v17 = (v161 & 0x80u) == 0;
  *((_DWORD *)this + 32) = v158 + *((_DWORD *)this + 30) - v183.m128i_i32[0];
  if ( v17 )
  {
    IsHScrollEnabled = CDisplay::IsHScrollEnabled(*((CDisplay **)this + 13));
    v103 = v183.m128i_i32[0];
    if ( !IsHScrollEnabled )
    {
      v122 = *((_DWORD *)this + 30);
      if ( v122 < v183.m128i_i32[0] )
      {
        *((_DWORD *)this + 30) = v183.m128i_i32[0];
      }
      else if ( v122 > v183.m128i_i32[2] )
      {
        *((_DWORD *)this + 30) = v183.m128i_i32[2] - 1;
      }
    }
  }
  v104 = v164;
  *((_DWORD *)this + 34) &= ~0x100u;
  if ( *(char *)(v104 + 180) < 0 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v104 + 48) + 96LL))(*(_QWORD *)(v104 + 48), 0);
    v103 = v183.m128i_i32[0];
  }
  v105 = v166;
  v106 = v153;
  if ( v166 + v102 + v154 > v46 )
  {
    v107 = v166 - v101 - v153;
    if ( v107 < v47 )
    {
      if ( v107 < v46 )
      {
        if ( v152 )
          goto LABEL_257;
        v101 = v166 - v46;
        if ( v166 < v46 )
        {
          v102 += v101;
          v105 = v46;
          v101 = 0;
        }
      }
      if ( v105 + v102 + v154 <= v47 )
      {
LABEL_146:
        if ( v101 > 0 || v102 > 0 )
        {
          v108 = *((_DWORD *)this + 30);
          if ( v108 >= v103 && v108 <= v183.m128i_i32[2] )
          {
            v109 = v102 + v101;
            v110 = v105 - v101;
            goto LABEL_150;
          }
          if ( v156 )
            goto LABEL_257;
        }
LABEL_159:
        v110 = -32000;
        v109 = 1;
        *((_DWORD *)this + 30) = -32000;
LABEL_150:
        *((_DWORD *)this + 31) = v110;
        *((_DWORD *)this + 33) = v109;
        if ( *(char *)(v104 + 180) < 0 && (*((_BYTE *)this + 136) & 8) != 0 )
        {
LABEL_151:
          CTxtSelection::CreateCaret(this);
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v104 + 48) + 96LL))(*(_QWORD *)(v104 + 48), 1);
        }
        return 0;
      }
      if ( !v152 )
      {
        v102 = v47 - v105;
        if ( v105 > v47 )
        {
          v101 += v102;
          v105 = v47;
          v102 = 0;
        }
        goto LABEL_146;
      }
LABEL_257:
      v112 = v152;
      goto LABEL_258;
    }
  }
  v112 = v152;
  if ( !v156 && !v152 )
    goto LABEL_159;
LABEL_258:
  if ( v112 )
  {
    if ( *((_DWORD *)this + 10) )
    {
      if ( (int)(v105 - v101 - v153) >= v46 )
      {
        v140 = v160;
        if ( v105 + v102 + v154 > v47 )
        {
          v140 = v105 + v154 + v102 - v47 + v160;
          v141 = CLinePtr::GetLine((CLinePtr *)&v167);
          if ( *((__int16 *)v141 + 6) < v155 )
          {
            v142 = CLinePtr::GetLine((CLinePtr *)&v167);
            v146 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(v143 + 344))(
                     v145,
                     (unsigned int)(v144 + *((__int16 *)v142 + 6)),
                     v140);
            v103 = v183.m128i_i32[0];
            v140 = v146;
          }
        }
      }
      else
      {
        v140 = v105 - v46 - v101 - v153 + v160;
      }
    }
    else
    {
      v140 = 0;
    }
  }
  else
  {
    v140 = v160;
  }
  v147 = v158;
  if ( v156 )
  {
    v148 = *((_DWORD *)this + 30);
    if ( v148 >= v103 )
    {
      if ( v148 > v183.m128i_i32[2] )
        v147 = v148 - v48 - v103 + v158 + 1;
    }
    else
    {
      v147 = v148 + v158 - v103;
      if ( v147 > 0 )
      {
        v106 = (unsigned int)(v48 / 3);
        v150 = v147 - v106;
        v149 = v150 < 0;
        v151 = v150;
        v147 = 0;
        if ( !v149 )
          v147 = v151;
      }
    }
  }
  if ( v140 == (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 288LL))(
                 *((_QWORD *)this + 13),
                 v106)
    && v147 == *(_DWORD *)(*((_QWORD *)this + 13) + 72LL) )
  {
    return 0;
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(**((_QWORD **)this + 13) + 336LL))(
          *((_QWORD *)this + 13),
          (unsigned int)v147,
          v140,
          0,
          0) )
  {
    if ( *(char *)(v104 + 180) >= 0 || (*((_BYTE *)this + 136) & 8) == 0 )
      return 0;
    goto LABEL_151;
  }
  return 1;
}

```

## disassembly

```asm
0x18000c840  push    rbp
0x18000c842  push    rbx
0x18000c843  push    rsi
0x18000c844  push    rdi
0x18000c845  push    r12
0x18000c847  push    r13
0x18000c849  push    r14
0x18000c84b  push    r15
0x18000c84d  lea     rbp, [rsp-68h]
0x18000c852  sub     rsp, 168h
0x18000c859  mov     rax, cs:__security_cookie
0x18000c860  xor     rax, rsp
0x18000c863  mov     [rbp+0A0h+var_50], rax
0x18000c867  mov     rax, [rcx+68h]
0x18000c86b  mov     ebx, r8d
0x18000c86e  mov     r14d, edx
0x18000c871  mov     rsi, rcx
0x18000c874  mov     r9, [rax+30h]
0x18000c878  test    r9, r9
0x18000c87b  jnz     loc_18000D2E3
0x18000c881  mov     rdi, [rcx+30h]
0x18000c885  lea     r13, [rcx+8]
0x18000c889  mov     [rbp+0A0h+var_118], rdi
0x18000c88d  mov     eax, [rdi+0B4h]
0x18000c893  bt      eax, 10h
0x18000c897  jb      loc_18000D1BB
0x18000c89d  test    al, 8
0x18000c89f  jz      loc_18000D565
0x18000c8a5  mov     rcx, [rdi+30h]
0x18000c8a9  lea     rdx, [rsp+1A0h+var_12C]
0x18000c8ae  xor     r12d, r12d
0x18000c8b1  mov     [rsp+1A0h+var_12C], r12d
0x18000c8b6  mov     rax, [rcx]
0x18000c8b9  mov     rax, [rax+0F8h]
0x18000c8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8c5  lea     rcx, [rsi+18h]; this
0x18000c8c9  mov     [rsp+1A0h+var_150], r12d
0x18000c8ce  mov     [rsp+1A0h+var_140], r12d
0x18000c8d3  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x18000c8d8  mov     r8, [rsi+68h]
0x18000c8dc  lea     rdx, [rbp+0A0h+var_100]
0x18000c8e0  mov     [rsp+1A0h+var_128], r12
0x18000c8e5  mov     r15d, eax
0x18000c8e8  mov     [rbp+0A0h+var_100], r12
0x18000c8ec  mov     [rbp+0A0h+var_F8], r12
0x18000c8f0  mov     [rbp+0A0h+var_F0], r8
0x18000c8f4  mov     [rbp+0A0h+var_E8], r12
0x18000c8f8  mov     rcx, [r8]
0x18000c8fb  mov     [rsp+1A0h+nDenominator], eax
0x18000c8ff  mov     rax, [rcx+18h]
0x18000c903  mov     rcx, r8
0x18000c906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90b  mov     rcx, [rsi+68h]
0x18000c90f  xorps   xmm0, xmm0
0x18000c912  movups  [rbp+0A0h+var_60], xmm0
0x18000c916  xorps   xmm1, xmm1
0x18000c919  movups  [rbp+0A0h+var_80], xmm1
0x18000c91d  mov     eax, [rcx+48h]
0x18000c920  mov     [rsp+1A0h+var_138], eax
0x18000c924  mov     rax, [rcx]
0x18000c927  mov     rax, [rax+120h]
0x18000c92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c933  test    byte ptr [rdi+0B4h], 80h
0x18000c93a  mov     [rsp+1A0h+var_130], eax
0x18000c93e  jz      short loc_18000C99C
0x18000c940  mov     edx, [rsi+88h]
0x18000c946  test    dl, 8
0x18000c949  jz      loc_18000D57D
0x18000c94f  movzx   eax, word ptr [rsi+62h]
0x18000c953  or      edx, 8
0x18000c956  test    edx, 0A20h
0x18000c95c  mov     [rsi+88h], edx
0x18000c962  mov     r8d, 4
0x18000c968  setz    cl
0x18000c96b  bt      ax, r8w
0x18000c970  setnb   al
0x18000c973  test    al, cl
0x18000c975  jz      short loc_18000C99C
0x18000c977  bts     edx, 9
0x18000c97b  mov     rcx, rsi; this
0x18000c97e  mov     [rsi+88h], edx
0x18000c984  call    ?CheckChangeKeyboardLayout@CTxtSelection@@QEAAXXZ; CTxtSelection::CheckChangeKeyboardLayout(void)
0x18000c989  test    r15d, r15d
0x18000c98c  jz      loc_18000D261
0x18000c992  and     dword ptr [rsi+88h], 0FFFFFDFFh
0x18000c99c  mov     rcx, [rdi+30h]
0x18000c9a0  lea     rdx, [rbp+0A0h+var_60]
0x18000c9a4  mov     rax, [rcx]
0x18000c9a7  mov     rax, [rax+0C0h]
0x18000c9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9b3  movaps  xmm1, [rbp+0A0h+var_60]
0x18000c9b7  lea     rdx, [rbp+0A0h+nNumber]
0x18000c9bb  mov     rbx, [rsi+68h]
0x18000c9bf  movdqa  xmm0, xmm1
0x18000c9c3  movdqa  [rbp+0A0h+var_80], xmm1
0x18000c9c8  psrldq  xmm0, 0Ch
0x18000c9cd  movd    ecx, xmm0
0x18000c9d1  xorps   xmm0, xmm0
0x18000c9d4  psrldq  xmm1, 4
0x18000c9d9  movd    eax, xmm1
0x18000c9dd  movups  xmmword ptr [rbp+0A0h+nNumber], xmm0
0x18000c9e1  sub     ecx, eax
0x18000c9e3  mov     rax, [rbx+10h]
0x18000c9e7  mov     [rbx+44h], ecx
0x18000c9ea  mov     rcx, [rax+30h]
0x18000c9ee  mov     rax, [rcx]
0x18000c9f1  mov     rax, [rax+0C8h]
0x18000c9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9fd  test    eax, eax
0x18000c9ff  js      loc_18000D217
0x18000ca05  mov     r12d, [rbp+0A0h+nNumber]
0x18000ca09  mov     edi, [rbp+0A0h+nNumber+4]
0x18000ca0c  mov     r15d, edi
0x18000ca0f  mov     eax, [rbp+0A0h+nNumber+0Ch]
0x18000ca12  mov     r13d, [rbp+0A0h+nNumber+8]
0x18000ca16  mov     [rsp+1A0h+var_144], eax
0x18000ca1a  test    r12d, r12d
0x18000ca1d  jz      loc_18000D5C1
0x18000ca23  mov     rcx, rbx; this
0x18000ca26  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x18000ca2b  mov     rcx, [rbx+10h]
0x18000ca2f  mov     r8d, eax; nDenominator
0x18000ca32  movzx   edx, word ptr [rcx+0CAh]
0x18000ca39  test    edx, edx
0x18000ca3b  jnz     short loc_18000CA4A
0x18000ca3d  mov     eax, [rbx+44h]
0x18000ca40  mov     edx, 1
0x18000ca45  test    eax, eax
0x18000ca47  cmovg   edx, eax; nNumerator
0x18000ca4a  cmp     edx, r8d
0x18000ca4d  jz      short loc_18000CA61
0x18000ca4f  mov     ecx, r12d; nNumber
0x18000ca52  call    cs:__imp_MulDiv
0x18000ca59  nop     dword ptr [rax+rax+00h]
0x18000ca5e  mov     r12d, eax
0x18000ca61  movsx   edx, word ptr [rbx+24h]; nNumerator
0x18000ca65  cmp     edx, 9ECh
0x18000ca6b  jz      short loc_18000CA76
0x18000ca6d  test    r12d, r12d
0x18000ca70  jnz     loc_18000D34E
0x18000ca76  mov     edi, [rbp+0A0h+nNumber+4]
0x18000ca79  test    r15d, r15d
0x18000ca7c  jz      loc_18000D30B
0x18000ca82  mov     rcx, rbx; this
0x18000ca85  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x18000ca8a  mov     rcx, [rbx+10h]
0x18000ca8e  mov     r8d, eax; nDenominator
0x18000ca91  movzx   edx, word ptr [rcx+0CAh]
0x18000ca98  test    edx, edx
0x18000ca9a  jnz     short loc_18000CAA9
0x18000ca9c  mov     eax, [rbx+44h]
0x18000ca9f  mov     edx, 1
0x18000caa4  test    eax, eax
0x18000caa6  cmovg   edx, eax; nNumerator
0x18000caa9  cmp     edx, r8d
0x18000caac  jz      short loc_18000CABF
0x18000caae  test    r8d, r8d
0x18000cab1  jz      loc_18000D388
0x18000cab7  test    edi, edi
0x18000cab9  jnz     loc_18000D388
0x18000cabf  movsx   edx, word ptr [rbx+26h]; nNumerator
0x18000cac3  cmp     edx, 9ECh
0x18000cac9  jz      short loc_18000CAD3
0x18000cacb  test    edi, edi
0x18000cacd  jnz     loc_18000D39D
0x18000cad3  test    r13d, r13d
0x18000cad6  jz      loc_18000D5C9
0x18000cadc  mov     r15d, [rbp+0A0h+nNumber+8]
0x18000cae0  mov     rcx, rbx; this
0x18000cae3  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x18000cae8  mov     rcx, [rbx+10h]
0x18000caec  mov     r8d, eax; nDenominator
0x18000caef  movzx   edx, word ptr [rcx+0CAh]
0x18000caf6  test    edx, edx
0x18000caf8  jnz     short loc_18000CB07
0x18000cafa  mov     eax, [rbx+44h]
0x18000cafd  mov     edx, 1
0x18000cb02  test    eax, eax
0x18000cb04  cmovg   edx, eax; nNumerator
0x18000cb07  cmp     edx, r8d
0x18000cb0a  jz      short loc_18000CB1E
0x18000cb0c  test    r8d, r8d
0x18000cb0f  jz      loc_18000D337
0x18000cb15  test    r15d, r15d
0x18000cb18  jnz     loc_18000D337
0x18000cb1e  movsx   edx, word ptr [rbx+24h]; nNumerator
0x18000cb22  cmp     edx, 9ECh
0x18000cb28  jz      short loc_18000CB33
0x18000cb2a  test    r15d, r15d
0x18000cb2d  jnz     loc_18000D36B
0x18000cb33  cmp     [rsp+1A0h+var_144], 0
0x18000cb38  jnz     loc_18000D4BB
0x18000cb3e  xor     eax, eax
0x18000cb40  lea     r13, [rsi+8]
0x18000cb44  add     dword ptr [rbp+0A0h+var_80], r12d
0x18000cb48  xor     r12d, r12d
0x18000cb4b  add     dword ptr [rbp+0A0h+var_80+4], edi
0x18000cb4e  sub     dword ptr [rbp+0A0h+var_80+8], r15d
0x18000cb52  sub     dword ptr [rbp+0A0h+var_80+0Ch], eax
0x18000cb55  mov     rcx, [rbx+10h]
0x18000cb59  test    dword ptr [rcx+0B4h], 2000000h
0x18000cb63  jz      short loc_18000CB9A
0x18000cb65  mov     rcx, [rcx+30h]
0x18000cb69  lea     r8, [rsp+1A0h+var_148]
0x18000cb6e  mov     [rsp+1A0h+var_144], r12d
0x18000cb73  lea     rdx, [rsp+1A0h+var_144]
0x18000cb78  mov     [rsp+1A0h+var_148], r12d
0x18000cb7d  mov     rax, [rcx]
0x18000cb80  mov     rax, [rax+190h]
0x18000cb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb8c  test    [rsp+1A0h+var_148], 4000h
0x18000cb94  jnz     loc_18000D460
0x18000cb9a  mov     rcx, rbx; this
0x18000cb9d  call    ?GetSelBarInPixels@CDisplay@@IEAAJXZ; CDisplay::GetSelBarInPixels(void)
0x18000cba2  mov     ecx, dword ptr [rbp+0A0h+var_80]
0x18000cba5  mov     r15d, dword ptr [rbp+0A0h+var_80+8]
0x18000cba9  add     ecx, eax
0x18000cbab  mov     dword ptr [rbp+0A0h+var_80], ecx
0x18000cbae  mov     edi, dword ptr [rbp+0A0h+var_60+4]
0x18000cbb1  cmp     dword ptr [rbp+0A0h+var_80+4], edi
0x18000cbb4  mov     ebx, dword ptr [rbp+0A0h+var_60+0Ch]
0x18000cbb7  cmovg   edi, dword ptr [rbp+0A0h+var_80+4]
0x18000cbbb  cmp     dword ptr [rbp+0A0h+var_80+0Ch], ebx
0x18000cbbe  cmovl   ebx, dword ptr [rbp+0A0h+var_80+0Ch]
0x18000cbc2  sub     r15d, ecx
0x18000cbc5  mov     ecx, 2000h
0x18000cbca  test    r14d, r14d
0x18000cbcd  jnz     loc_18000D50A
0x18000cbd3  and     dword ptr [rsi+88h], 0FFFFEFFFh
0x18000cbdd  cmp     dword ptr [rsi+58h], 0
0x18000cbe1  jz      loc_18000D1E9
0x18000cbe7  movups  xmm0, xmmword ptr [rsi+18h]
0x18000cbeb  mov     r8, [rsi+38h]
0x18000cbef  lea     rax, ??_7CRchTxtPtr@@6B@; const CRchTxtPtr::`vftable'
0x18000cbf6  mov     r10, [rsi+48h]
0x18000cbfa  mov     ecx, [rsi+40h]
0x18000cbfd  mov     r14d, [rsi+44h]
0x18000cc01  mov     edx, [rsi+50h]
0x18000cc04  mov     [rbp+0A0h+var_E0], rax
0x18000cc08  mov     eax, [rsi+28h]
0x18000cc0b  movaps  [rbp+0A0h+var_D0], xmm0
0x18000cc0f  movsd   xmm0, qword ptr [rsi+2Ch]
0x18000cc14  mov     [rbp+0A0h+var_110], r12
0x18000cc18  mov     r12d, [rsi+54h]
0x18000cc1c  mov     [rsp+1A0h+var_144], eax
0x18000cc20  mov     [rbp+0A0h+var_C0], eax
0x18000cc23  mov     eax, [rsi+34h]
0x18000cc26  movsd   [rbp+0A0h+var_BC], xmm0
0x18000cc2b  mov     [rbp+0A0h+var_B4], eax
0x18000cc2e  mov     [rbp+0A0h+var_B0], r8
0x18000cc32  mov     [rbp+0A0h+var_A8], ecx
0x18000cc35  mov     [rbp+0A0h+var_A4], r14d
0x18000cc39  mov     [rbp+0A0h+var_A0], r10
0x18000cc3d  mov     [rbp+0A0h+var_98], edx
0x18000cc40  mov     [rbp+0A0h+var_94], r12d
0x18000cc44  test    r8, r8
0x18000cc47  jz      short loc_18000CC9C
0x18000cc49  mov     r9d, [r8+8]
0x18000cc4d  test    r9d, r9d
0x18000cc50  jz      short loc_18000CC9C
0x18000cc52  jle     loc_18000D47B
0x18000cc58  cmp     ecx, r9d
0x18000cc5b  jge     loc_18000D47B
0x18000cc61  mov     r11, [r8]
0x18000cc64  test    r11, r11
0x18000cc67  jz      loc_18000D47B
0x18000cc6d  test    ecx, ecx
0x18000cc6f  js      loc_18000D47B
0x18000cc75  mov     eax, ecx
0x18000cc77  imul    eax, [r8+10h]
0x18000cc7c  movsxd  r8, eax
0x18000cc7f  add     r8, r11
0x18000cc82  cmp     [r8], r14d
0x18000cc85  jnz     short loc_18000CC9C
0x18000cc87  lea     eax, [r9-1]
0x18000cc8b  cmp     ecx, eax
0x18000cc8d  jge     short loc_18000CC9C
0x18000cc8f  lea     eax, [rcx+1]
0x18000cc92  mov     [rbp+0A0h+var_A4], 0
0x18000cc99  mov     [rbp+0A0h+var_A8], eax
0x18000cc9c  test    r10, r10
0x18000cc9f  jz      short loc_18000CCF1
0x18000cca1  mov     ecx, [r10+8]
0x18000cca5  test    ecx, ecx
0x18000cca7  jz      short loc_18000CCF1
0x18000cca9  jle     loc_18000D483
0x18000ccaf  cmp     edx, ecx
0x18000ccb1  jge     loc_18000D483
0x18000ccb7  mov     r9, [r10]
0x18000ccba  test    r9, r9
0x18000ccbd  jz      loc_18000D483
0x18000ccc3  test    edx, edx
0x18000ccc5  js      loc_18000D483
0x18000cccb  mov     eax, edx
0x18000cccd  imul    eax, [r10+10h]
0x18000ccd2  movsxd  r8, eax
0x18000ccd5  add     r8, r9
0x18000ccd8  cmp     [r8], r12d
0x18000ccdb  jnz     short loc_18000CCF1
0x18000ccdd  lea     eax, [rcx-1]
  ... truncated ...
```
