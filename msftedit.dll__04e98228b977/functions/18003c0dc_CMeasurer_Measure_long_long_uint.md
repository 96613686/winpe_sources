# CMeasurer::Measure(long,long,uint)

- ea: `0x18003c0dc`
- end: `0x18003d261`
- name: `?Measure@CMeasurer@@IEAAJJJI@Z`
- size: `4485`
- prototype: `__int64 __fastcall(CMeasurer *__hidden this, int, int, unsigned int)`
- caller_count: `3`
- callee_count: `53`
- tags: `loader_planting, installer_update`

## callers

- `0x18004f130`
- `0x1800943dc`
- `0x1800fc104`

## callees

- `0x18000ea0c`
- `0x18000f0a4`
- `0x18000f260`
- `0x18000f2dc`
- `0x1800117e4`
- `0x18001189c`
- `0x180014128`
- `0x18001668c`
- `0x1800187f0`
- `0x180020258`
- `0x18003ab3c`
- `0x18003ada0`
- `0x18003aef0`
- `0x18003bfe4`
- `0x18003c0dc`
- `0x18003d268`
- `0x18003db44`
- `0x18003ec20`
- `0x18003ed40`
- `0x18003f4f0`
- `0x1800425b0`
- `0x180045af4`
- `0x180046cec`
- `0x18004b2c8`
- `0x18004ef64`
- `0x18004ef80`
- `0x180057560`
- `0x18005912c`
- `0x18005921c`
- `0x180066414`
- `0x18006800c`
- `0x1800a9834`
- `0x1800a987c`
- `0x1800a9a48`
- `0x1800b26ec`
- `0x1800b436c`
- `0x1800bd038`
- `0x1800bef04`
- `0x1800e2a78`
- `0x1800ead70`
- `0x1800f26b4`
- `0x1800fbfa0`
- `0x1801031c8`
- `0x18011214c`
- `0x180123080`
- `0x180123fc8`
- `0x180129010`
- `0x1801293e8`
- `0x18012961c`
- `0x18012baa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c86b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003c86b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c877`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c877`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18003c834`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18003c834`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18003c7f4`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18003c7f4`

## pseudocode

```c
__int64 __fastcall CMeasurer::Measure(CMeasurer *this, int a2, int a3, int a4)
{
  int v4; // ebx
  char v5; // di
  _DWORD *LockTelemetry; // rax
  _DWORD *v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rdx
  CLine *v12; // r15
  int DupLayout; // edi
  bool v14; // dl
  __int64 v15; // rcx
  int CaretWidth; // eax
  int v17; // edi
  int v18; // edi
  int v19; // eax
  int v20; // ebx
  int CchLeftRunCF; // r12d
  int v22; // edx
  int v23; // r11d
  struct CCcs *v24; // rax
  __int64 v25; // r11
  unsigned __int16 *v26; // rdx
  _BYTE *v27; // rbx
  char v28; // al
  int v29; // edi
  int v30; // ebx
  unsigned __int16 v31; // r8
  unsigned __int16 LastChar; // ax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r14
  unsigned __int16 v37; // di
  unsigned __int64 v38; // r9
  BOOL v39; // ebx
  int v40; // r14d
  bool v41; // zf
  __int64 v42; // rbx
  char v43; // al
  int v44; // eax
  int v45; // eax
  char v46; // cl
  int v47; // eax
  int v48; // ebx
  unsigned __int8 v49; // al
  int v50; // ebx
  int v51; // edi
  int v52; // ebx
  unsigned int v53; // edi
  char v54; // al
  int v55; // eax
  RTL_SRWLOCK *Lock; // rax
  __int64 v58; // rax
  int v59; // eax
  int v60; // edx
  int v61; // r9d
  int v62; // r15d
  int WordBreak; // eax
  int v64; // r14d
  int v65; // r12d
  unsigned __int16 PrevChar; // ax
  int v67; // r12d
  int v68; // r14d
  int v69; // r15d
  int v70; // edx
  struct COleObject *ObjectFromCp; // r12
  int v72; // r14d
  int v73; // r15d
  int v74; // edi
  unsigned __int8 Tflow; // bl
  int Descent; // eax
  int v77; // ebx
  CDisplay *v78; // rcx
  int v79; // eax
  int v80; // edi
  char v81; // al
  int v82; // ebx
  int v83; // eax
  CLineBasic *v84; // rcx
  char v85; // al
  int v86; // ebx
  int v87; // eax
  int v88; // eax
  int v89; // edx
  char v90; // al
  int v91; // eax
  unsigned __int16 *v92; // rax
  int v93; // r9d
  unsigned __int16 Char; // ax
  unsigned int v95; // eax
  int ObjectCount; // eax
  CRchTxtPtr *v97; // rcx
  const struct CParaFormat *PF; // rax
  const struct CParaFormat *v99; // rax
  int Height; // eax
  int v101; // edx
  __int64 v102; // rax
  __int64 v103; // rdi
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rbx
  __int64 v108; // rax
  __int64 v109; // rbx
  __int64 v110; // rax
  __int64 v111; // rax
  int v112; // ecx
  unsigned __int8 v113; // dl
  __int64 v114; // r8
  CLineBasic *v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rax
  WCHAR DestStr[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v119; // [rsp+54h] [rbp-ACh] BYREF
  int v120; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v121[2]; // [rsp+5Ch] [rbp-A4h] BYREF
  char v122; // [rsp+60h] [rbp-A0h]
  unsigned int v123; // [rsp+64h] [rbp-9Ch]
  int v124; // [rsp+68h] [rbp-98h]
  CMeasurer *Pch; // [rsp+70h] [rbp-90h]
  int v126; // [rsp+78h] [rbp-88h]
  int v127; // [rsp+7Ch] [rbp-84h]
  int v128; // [rsp+80h] [rbp-80h]
  int v129; // [rsp+84h] [rbp-7Ch]
  int v130; // [rsp+88h] [rbp-78h]
  int v131; // [rsp+8Ch] [rbp-74h]
  int v132; // [rsp+90h] [rbp-70h] BYREF
  CTxtEdit *v133; // [rsp+98h] [rbp-68h]
  int v134; // [rsp+A0h] [rbp-60h]
  int v135; // [rsp+A4h] [rbp-5Ch]
  int v136; // [rsp+A8h] [rbp-58h] BYREF
  int v137; // [rsp+ACh] [rbp-54h] BYREF
  int v138; // [rsp+B0h] [rbp-50h] BYREF
  int v139; // [rsp+B4h] [rbp-4Ch]
  int v140; // [rsp+B8h] [rbp-48h]
  struct CCharFormat *CF; // [rsp+C0h] [rbp-40h]
  int v142; // [rsp+C8h] [rbp-38h] BYREF
  int v143; // [rsp+CCh] [rbp-34h] BYREF
  int v144; // [rsp+D0h] [rbp-30h] BYREF
  int v145; // [rsp+D4h] [rbp-2Ch] BYREF
  int v146; // [rsp+D8h] [rbp-28h]
  __int64 v147; // [rsp+E0h] [rbp-20h]
  _DWORD v148[98]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Name[88]; // [rsp+270h] [rbp+170h] BYREF

  v4 = (int)CLockSharedData::LockOwner;
  v130 = a4;
  v5 = a4;
  v127 = a3;
  v126 = a2;
  v137 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v4 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v58 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v58 + 4);
  }
  ++g_cFCLock;
  v9 = (_DWORD *)((char *)this + 16);
  v10 = *((_QWORD *)this + 2);
  if ( v10 )
    v129 = *(_DWORD *)(v10 + 32);
  else
    v129 = 0;
  DestStr[0] = 0;
  v140 = 0;
  v123 = 0;
  v11 = v10 - 8;
  if ( v10 )
    v133 = *(CTxtEdit **)(v11 + 48);
  else
    v133 = 0;
  v119 = 0;
  v136 = 0;
  v134 = 0;
  v135 = 0;
  LODWORD(v147) = 0;
  v122 = *(_BYTE *)((v11 & -(__int64)(v10 != 0)) + 0x46) & 0x78;
  CMeasurerNoFC::UpdatePF(this);
  if ( (v5 & 1) != 0 )
  {
    *((_BYTE *)this + 110) |= 2u;
    if ( CRchTxtPtr::IsInOutlineView(this) )
    {
      PF = (const struct CParaFormat *)*((_QWORD *)this + 37);
      if ( !PF )
        PF = CRchTxtPtr::GetPF(v97);
      if ( *((__int16 *)PF + 16) <= -2 )
      {
        v99 = (const struct CParaFormat *)*((_QWORD *)this + 37);
        if ( !v99 )
          v99 = CRchTxtPtr::GetPF(this);
        if ( *((__int16 *)v99 + 16) >= -10 )
        {
          Height = CLine::GetHeight((CMeasurer *)((char *)this + 96), 0, 0);
          v101 = 11;
          if ( Height > 11 )
            v101 = Height;
          CLineBasic::SetHeight((CMeasurer *)((char *)this + 96), v101);
        }
      }
    }
  }
  v12 = (CMeasurer *)((char *)this + 96);
  *((_DWORD *)this + 25) = CMeasurer::MeasureLeftIndent(this, 0);
  if ( a2 >= 0 )
  {
    v18 = 0x3FFFFFFF;
    if ( a2 != 0x3FFFFFFF )
      v18 = CMeasurerNoFC::LUtoDU(this, a2);
  }
  else
  {
    DupLayout = CMeasurerNoFC::GetDupLayout(this);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 120LL))(*((_QWORD *)this + 19))
      && (!*(_QWORD *)v9 ? (v15 = 0) : (v15 = *(_QWORD *)(*(_QWORD *)v9 + 40LL)), (*(_BYTE *)(v15 + 176) & 4) == 0) )
    {
      CaretWidth = CTxtEdit::GetCaretWidth(v133);
    }
    else
    {
      CaretWidth = 0;
    }
    v17 = DupLayout - *((_DWORD *)this + 25) - CaretWidth;
    v18 = v17 - CMeasurerNoFC::MeasureRightIndent(this, v14);
  }
  if ( v18 <= 0 )
    v18 = 0;
  v19 = v129 - *((_DWORD *)this + 8);
  v20 = v127;
  v120 = v18;
  if ( v127 < 0 || v127 > v19 )
  {
    v20 = v19;
    v127 = v19;
  }
  CchLeftRunCF = 1;
  v22 = *((_DWORD *)this + 26);
  v139 = *(_DWORD *)v12;
  v131 = v22;
  while ( 1 )
  {
    if ( v20 <= 0 || CchLeftRunCF <= 0 )
      goto LABEL_102;
    *(_DWORD *)v121 = 1;
    if ( v122 )
      Pch = (CMeasurer *)((char *)this + 270);
    else
      Pch = (CMeasurer *)CTxtPtr::GetPch((CTxtPtr *)v9, (int *)v121);
    CchLeftRunCF = CRchTxtPtr::GetCchLeftRunCF(this);
    if ( v23 < CchLeftRunCF )
      CchLeftRunCF = v23;
    v124 = CchLeftRunCF;
    v128 = CchLeftRunCF;
    CF = CRchTxtPtr::GetCF(this);
    v146 = *(_DWORD *)CF;
    if ( (v146 & 0x100) == 0 )
      break;
    *(_DWORD *)v12 += CchLeftRunCF;
    v119 = 0;
LABEL_134:
    v20 -= CchLeftRunCF;
    v127 = v20;
    CRchTxtPtr::Move(this, CchLeftRunCF);
  }
  v24 = CMeasurer::Check_pccs(this, 0, 0, 0xFFu, 0, 0);
  v25 = 0;
  if ( !v24 )
  {
    --g_cFCLock;
    CWriteLock::~CWriteLock((CWriteLock *)&v137);
    return 0xFFFFFFFFLL;
  }
  v26 = (unsigned __int16 *)Pch;
  if ( CchLeftRunCF > 0 )
  {
    if ( Pch )
    {
      if ( *(_WORD *)Pch )
      {
        if ( (unsigned int)CRchTxtPtr::IsRich(this)
          || !(unsigned int)CDisplay::IsMultiLine(*((CDisplay **)this + 19))
          || (ObjectCount = CRchTxtPtr::GetObjectCount(this), v26 = (unsigned __int16 *)Pch, ObjectCount) )
        {
          if ( v139 == (_DWORD)v25 || *v26 != 10 && *v26 != 13 )
          {
            v27 = (char *)this + 111;
            if ( (*((_BYTE *)this + 109) & 0x10) == 0 )
            {
              v28 = *v27 & 3;
              if ( v28 == 1 )
              {
                v102 = *((_QWORD *)this + 15);
                if ( v102 )
                {
                  SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
                    *(int *)(v102 + 8),
                    &v144);
                  v29 = v144;
                  goto LABEL_38;
                }
              }
              else
              {
                if ( v28 != 2 )
                {
                  v29 = *((_DWORD *)this + 31);
                  goto LABEL_38;
                }
                v103 = *((_QWORD *)this + 15);
                if ( v103 )
                {
                  v29 = *(_DWORD *)(v103 + 16);
LABEL_38:
                  CMeasurer::RecalcLineHeight(this, *((struct CCcs **)this + 41), CF);
                  v25 = 0;
                  if ( !v29 )
                  {
LABEL_39:
                    v26 = (unsigned __int16 *)Pch;
                    v18 = v120;
                    goto LABEL_40;
                  }
                  if ( (*((_BYTE *)this + 109) & 0x10) == 0 )
                  {
                    v90 = *v27 & 3;
                    if ( v90 != 1 )
                    {
                      if ( v90 == 2 )
                      {
                        v105 = *((_QWORD *)this + 15);
                        if ( v105 )
                          v91 = *(_DWORD *)(v105 + 16);
                        else
                          v91 = 0;
                      }
                      else
                      {
                        v91 = *((_DWORD *)this + 31);
                      }
                      goto LABEL_184;
                    }
                    v104 = *((_QWORD *)this + 15);
                    if ( v104 )
                    {
                      SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
                        *(int *)(v104 + 8),
                        &v145);
                      v91 = v145;
                      v25 = 0;
LABEL_184:
                      if ( v29 == v91 )
                        goto LABEL_39;
                    }
                  }
                  v135 = 1;
                  goto LABEL_39;
                }
              }
            }
            v29 = v25;
            goto LABEL_38;
          }
        }
      }
    }
  }
  while ( 1 )
  {
LABEL_40:
    v30 = v128;
    if ( v128 <= 0 )
    {
      v20 = v127;
      goto LABEL_134;
    }
    v119 = v25;
    if ( v122 == (_BYTE)v25 )
    {
      v31 = *v26;
      DestStr[0] = *v26;
LABEL_43:
      LastChar = v31;
      goto LABEL_44;
    }
    v31 = *((_WORD *)this + 135);
    DestStr[0] = v31;
    if ( v128 != 1 || (*((_DWORD *)v133 + 70) & 0x8000000) == 0 || CchLeftRunCF + *((_DWORD *)this + 8) != v129 )
      goto LABEL_43;
    v121[0] = v25;
    LastChar = CTxtPtr::GetLastChar((CTxtPtr *)v9, v121);
    v31 = LastChar;
    DestStr[0] = LastChar;
    v25 = 0;
LABEL_44:
    if ( *((_BYTE *)CF + 4) != 10 )
    {
      if ( (v146 & 0xC0) != 0
        || ((v33 = *(_QWORD *)v9) == 0 ? (v34 = v25) : (v34 = *(_QWORD *)(v33 + 40)),
            (*(_DWORD *)(v34 + 284) & 0x200) != 0) )
      {
        LCIDToLocaleName(*((_DWORD *)CF + 6), Name, 85, 0);
        LCMapStringEx(Name, 0x1000200u, DestStr, 1, DestStr, 1, 0, 0, 0);
      }
      else
      {
        if ( v33 )
          v35 = *(_QWORD *)(v33 + 40);
        else
          v35 = v25;
        if ( (*(_DWORD *)(v35 + 284) & 0x400) == 0 )
          goto LABEL_52;
        StringUtil::CharLowerBuffW(DestStr, 1u, 1u, *((_DWORD *)CF + 6));
      }
      v31 = DestStr[0];
      goto LABEL_52;
    }
    if ( LastChar > 0xFFu )
    {
      v49 = Get8BitAnsiChar(v31);
      if ( v49 )
      {
        v31 = v49;
        DestStr[0] = v49;
      }
      else
      {
        v31 = DestStr[0];
      }
    }
LABEL_52:
    if ( v31 == 0xFFFC )
    {
      v70 = *((_DWORD *)this + 8);
      *((_BYTE *)this + 110) |= 1u;
      ObjectFromCp = CMeasurerNoFC::GetObjectFromCp(this, CchLeftRunCF + v70 - v30);
      if ( !ObjectFromCp )
      {
LABEL_161:
        v77 = v126;
        goto LABEL_162;
      }
      v41 = (*((_BYTE *)this + 277) & 2) == 0;
      *(_DWORD *)v121 = 0;
      v138 = 0;
      if ( v41 )
      {
        v72 = CDisplay::Zoom(*((CDisplay **)this + 19), *((_DWORD *)this + 49));
        v73 = CDisplay::Zoom(*((CDisplay **)this + 19), *((_DWORD *)this + 48));
      }
      else
      {
        v73 = *((_DWORD *)this + 46);
        v72 = *((_DWORD *)this + 47);
      }
      v74 = CMeasurerNoFC::LVtoDV(this, *((__int16 *)CF + 5));
      Tflow = CMeasurerNoFC::GetTflow(this);
      Descent = CLine::GetDescent((CMeasurer *)((char *)this + 96), 0);
      COleObject::MeasureObj(ObjectFromCp, v73, v72, &v119, (int *)v121, &v138, Descent, Tflow, v74);
      v77 = v126;
      v18 = v120;
      if ( v126 < 0 && (*((_WORD *)ObjectFromCp + 77) & 0x4000) != 0 && *((_DWORD *)this + 26) < v120 )
      {
        v78 = (CDisplay *)*((_QWORD *)this + 19);
        v119 = v120 - *((_DWORD *)this + 26);
        *(_QWORD *)v148 = *(_QWORD *)((char *)ObjectFromCp + 84);
        v148[0] = CDisplay::DUtoHimetricU(v78, v119);
        COleObject::Resize(ObjectFromCp, (const struct SIZEUV *)v148, 0, 0, 0, 0, 0);
      }
      v12 = (CMeasurer *)((char *)this + 96);
      if ( *((_DWORD *)this + 24)
        && v119 + *((_DWORD *)this + 26) > v18
        && (*((_WORD *)ObjectFromCp + 77) & 0x2000) == 0 )
      {
LABEL_162:
        v89 = *((_DWORD *)this + 26);
        if ( v89 + v119 > v18 && (v140 = 1, v77 < 0) && ObjectFromCp )
        {
          v41 = (*((_WORD *)ObjectFromCp + 77) & 0x2000) == 0;
          CchLeftRunCF = v124;
          if ( !v41 )
          {
            v59 = v18 - v89;
            goto LABEL_118;
          }
        }
        else
        {
          CchLeftRunCF = v124;
        }
        goto LABEL_68;
      }
      v79 = CLine::GetDescent((CMeasurer *)((char *)this + 96), 0);
      v80 = v138;
      if ( v138 <= v79 )
      {
LABEL_154:
        if ( (*((_BYTE *)this + 109) & 0x10) == 0 )
        {
          v85 = *((_BYTE *)this + 111) & 3;
          if ( v85 == 1 )
          {
            v108 = *((_QWORD *)this + 15);
            if ( v108 )
            {
              SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
                *(int *)(v108 + 8),
                &v143);
              v86 = v143;
              goto LABEL_158;
            }
          }
          else
          {
            if ( v85 != 2 )
            {
              v86 = *((_DWORD *)this + 31);
LABEL_158:
              v87 = CLine::GetDescent((CMeasurer *)((char *)this + 96), 0);
              if ( *(int *)v121 > v86 - v87 )
              {
                v88 = CLine::GetDescent((CMeasurer *)((char *)this + 96), 0);
                CLineBasic::SetHeight((CMeasurer *)((char *)this + 96), *(_DWORD *)v121 + v88);
              }
              v18 = v120;
              goto LABEL_161;
            }
            v109 = *((_QWORD *)this + 15);
            if ( v109 )
            {
              v86 = *(_DWORD *)(v109 + 16);
              goto LABEL_158;
            }
          }
        }
        v86 = 0;
        goto LABEL_158;
      }
      if ( (*((_BYTE *)this + 109) & 0x10) == 0 )
      {
        v81 = *((_BYTE *)this + 111) & 3;
        if ( v81 == 1 )
        {
          v106 = *((_QWORD *)this + 15);
          if ( v106 )
          {
            SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
              *(int *)(v106 + 8),
              &v142);
            v82 = v142;
            goto LABEL_153;
          }
        }
        else
        {
          if ( v81 != 2 )
          {
            v82 = *((_DWORD *)this + 31);
LABEL_153:
            v83 = CLine::GetDescent((CMeasurer *)((char *)this + 96), 0);
            CLineBasic::SetHeight((CMeasurer *)((char *)this + 96), v80 + v82 - v83);
            CLineBasic::SetDescent(v84, v80);
            goto LABEL_154;
          }
          v107 = *((_QWORD *)this + 15);
          if ( v107 )
          {
            v82 = *(_DWORD *)(v107 + 16);
            goto LABEL_153;
          }
        }
      }
      v82 = 0;
      goto LABEL_153;
    }
    if ( (unsigned int)v31 - 7 <= 6 )
    {
      if ( v31 == 9 )
      {
        *((_BYTE *)this + 110) |= 1u;
        v59 = CMeasurer::MeasureTab(this);
LABEL_118:
        v119 = v59;
        goto LABEL_68;
      }
      if ( v31 != 12 || (*((_DWORD *)v133 + 44) & 0x80000) == 0 )
      {
        CCcs::Include(*((CCcs **)this + 41), (CMeasurer *)((char *)this + 304), v31, &v136, 0);
        CRchTxtPtr::Move(this, CchLeftRunCF - v30);
        v50 = v9[4];
        v51 = CTxtPtr::AdvanceCRLF(v9, 2);
        CRunPtrBase::Move((CRunPtrBase *)(v9 + 6), v9[4] - v50);
        CRunPtrBase::Move((CMeasurer *)((char *)this + 72), v51);
        CRunPtrBase::Move((CMeasurer *)((char *)this + 56), v51);
        *(_DWORD *)v12 += v51;
        *((_BYTE *)this + 108) ^= (*((_BYTE *)this + 108) ^ (32 * v51)) & 0x60;
        if ( DestStr[0] == 13 || (*((_DWORD *)v133 + 44) & 0x80000) != 0 && DestStr[0] == 10 || DestStr[0] == 7 )
          *((_BYTE *)this + 109) |= 0x80u;
LABEL_102:
        v52 = *((_DWORD *)this + 26) + v136;
        v53 = v123;
        if ( (v130 & 2) != 0 )
          *((_DWORD *)this + 26) = v131;
LABEL_104:
        *((_WORD *)this + 134) = v119;
        *((_DWORD *)this + 66) = v52;
        if ( (*((_BYTE *)this + 109) & 0x10) == 0 )
        {
          v54 = *((_BYTE *)this + 111) & 3;
          if ( v54 == 1 )
          {
            v116 = *((_QWORD *)this + 15);
            if ( v116 )
            {
              SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
                *(int *)(v116 + 8),
                &v132);
              v55 = v132;
              goto LABEL_108;
            }
          }
          else
          {
            if ( v54 == 2 )
            {
              v117 = *((_QWORD *)this + 15);
              if ( v117 )
                v55 = *(_DWORD *)(v117 + 16);
              else
                v55 = 0;
            }
            else
            {
              v55 = *((_DWORD *)this + 31);
            }
LABEL_108:
            if ( v55 )
            {
LABEL_109:
              CMeasurerNoFC::AdjustLineHeight(this);
              CLine::CopyIMetrics(v12, *((_DWORD *)this + 49), *((_DWORD *)this + 48));
              goto LABEL_110;
            }
          }
        }
        CMeasurer::CheckLineHeight(this);
        goto LABEL_109;
      }
      CCcs::Include(*((CCcs **)this + 41), (CMeasurer *)((char *)this + 304), 0xCu, &v119, 0);
      goto LABEL_68;
    }
    v36 = *((_QWORD *)this + 41);
    v37 = v31;
    if ( v31 >= 0x3400u && ((unsigned int)v31 - 13312 <= 0x6BFF || (unsigned int)v31 - 63744 <= 0x1FF) )
    {
      v119 = *(_DWORD *)(v36 + 40);
      v39 = v119 != 0;
    }
    else
    {
      if ( (unsigned int)v31 - 55296 <= 0x3FF )
        break;
      v38 = *(_QWORD *)(v36 + 64) + 8 * (v31 & (unsigned __int64)*(int *)(v36 + 44));
      if ( v31 == *(_WORD *)v38 && *(_DWORD *)(v38 + 4) )
      {
        v39 = 1;
        v119 = *(_DWORD *)(v38 + 4);
      }
      else
      {
        v39 = 0;
        v119 = 0;
      }
      if ( !*(_DWORD *)(v36 + 60) )
      {
        ++*(_DWORD *)(v36 + 56);
        if ( v39 || (*(_DWORD *)(v38 + 4) ? ++*(_DWORD *)(v36 + 52) : ++*(_DWORD *)(v36 + 48), *(int *)(v36 + 56) < 64) )
        {
          v31 = DestStr[0];
        }
        else
        {
          CWidthCache::CheckPerformance((CWidthCache *)(v36 + 40));
          v31 = DestStr[0];
        }
      }
    }
    if ( !v39 )
      break;
LABEL_63:
    if ( (unsigned int)v31 - 160 <= 0x1F71 || v31 == 0xFEFF || v31 == 0xFFFE )
    {
      if ( v31 != 160 && v31 != 173 && v31 != 8194 && v31 != 8195 && v31 != 8209 && v31 != 65279 && v31 != 65534
        || (*((_BYTE *)this + 110) |= 1u, v31 != 173) )
      {
LABEL_67:
        v18 = v120;
        goto LABEL_68;
      }
      v18 = v120;
      if ( *((_BYTE *)CF + 4) != 10 && (v119 + *((_DWORD *)this + 26) < v120 || !*(_DWORD *)v12) )
      {
        v134 = v119;
LABEL_171:
        v119 = 0;
      }
    }
    else
    {
      if ( !*((_WORD *)this + 135) )
        goto LABEL_67;
      v18 = v120;
      if ( (unsigned int)v31 - 56320 <= 0x3FF )
        goto LABEL_171;
    }
LABEL_68:
    v40 = v147;
    v41 = (*((_BYTE *)this + 109) & 0x10) == 0;
    v42 = 3 * (v147 & 0x1F);
    v148[3 * (v147 & 0x1F) + 2] = v119;
    if ( !v41 )
    {
      v44 = 0;
      goto LABEL_72;
    }
    v43 = *((_BYTE *)this + 111) & 3;
    if ( v43 == 1 )
    {
      v110 = *((_QWORD *)this + 15);
      if ( v110 )
      {
        SafeCastHelper<long,__int64,4>::CastThrow<SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>(
          *(int *)(v110 + 8),
          &v132);
        v44 = v132;
        goto LABEL_72;
      }
    }
    else
    {
      if ( v43 != 2 )
      {
        v44 = *((_DWORD *)this + 31);
        goto LABEL_72;
      }
      v111 = *((_QWORD *)this + 15);
      if ( v111 )
      {
        v44 = *(_DWORD *)(v111 + 16);
        goto LABEL_72;
      }
    }
    v44 = 0;
LABEL_72:
    v148[v42 + 3] = v44;
    v45 = CLine::GetDescent(v12, 0);
    v46 = v130;
    v148[v42 + 4] = v45;
    v47 = v119;
    *((_DWORD *)this + 26) += v119;
    v48 = *((_DWORD *)this + 26);
    if ( v48 > v18 )
    {
      if ( (v46 & 4) != 0 || (v25 = 0, *(int *)v12 > 0) )
      {
        v52 = v48 - v47;
        v60 = CchLeftRunCF - v128;
        *((_DWORD *)this + 26) = v52;
        CRchTxtPtr::Move(this, v60);
        if ( (v130 & 2) != 0 )
        {
          *((_BYTE *)this + 108) &= 0x9Fu;
          if ( DestStr[0] != 9 )
          {
            v62 = *((_DWORD *)this + 8);
            WordBreak = CRchTxtPtr::FindWordBreak(this, 6, v62 - *((_DWORD *)this + 24) - 1, v61);
            v64 = -WordBreak;
            *(_DWORD *)v121 = -WordBreak;
            if ( !WordBreak && v140 )
            {
              v12 = (CMeasurer *)((char *)this + 96);
LABEL_220:
              v53 = 0;
              goto LABEL_104;
            }
            v65 = 1 - WordBreak;
            if ( 1 - WordBreak >= *((_DWORD *)this + 24) )
            {
              if ( v64 == *((_DWORD *)this + 24) && v64 > 1 && CTxtPtr::GetChar((CMeasurer *)((char *)this + 16)) == 32 )
              {
                CRchTxtPtr::Move(this, 1);
                *((_DWORD *)this + 24) = 1;
                *(_DWORD *)v121 = v64 - 1;
              }
              else
              {
                CRchTxtPtr::SetCp(this, v62);
              }
            }
            else
            {
              PrevChar = CTxtPtr::GetPrevChar((CMeasurer *)((char *)this + 16));
              DestStr[0] = PrevChar;
              if ( PrevChar == 9 )
              {
                *(_DWORD *)v121 = v64 + 1;
                CRchTxtPtr::Move(this, -1);
              }
              else
              {
                v65 = v64;
                if ( PrevChar == 173 )
                {
                  *((_DWORD *)this + 26) += v134;
                  v52 = *((_DWORD *)this + 26);
                }
              }
              *((_DWORD *)this + 24) -= v65;
            }
            v67 = *((_DWORD *)this + 8);
            v68 = 0;
            if ( v67 < v129 )
            {
              v92 = (unsigned __int16 *)CTxtPtr::GetPch((CMeasurer *)((char *)this + 16), (int *)v121);
              if ( CTxtEdit::TxWordBreakProc(
                     v133,
                     v92,
                     0,
                     2,
                     2,
                     v67,
                     -1,
                     (struct CTxtStory *)((*((_QWORD *)this + 2) - 8LL) & -(__int64)(*((_QWORD *)this + 2) != 0))) )
              {
                v68 = CRchTxtPtr::FindWordBreak(this, 1, -1, v93);
              }
              *((_DWORD *)this + 24) += v68;
              Char = CTxtPtr::GetChar((CMeasurer *)((char *)this + 16));
              DestStr[0] = Char;
              if ( (unsigned int)Char - 7 <= 6 && (unsigned int)Char - 8 > 1 )
              {
                if ( Char == 13 || Char == 7 )
                  *((_BYTE *)this + 109) |= 0x80u;
                v12 = (CMeasurer *)((char *)this + 96);
                v95 = *((_BYTE *)this + 108)
                    ^ (*((_BYTE *)this + 108)
                     ^ (unsigned __int8)(32 * CRchTxtPtr::AdvanceCRLF(this, 2)))
                    & 0x60;
                *((_BYTE *)this + 108) = v95;
                *((_DWORD *)this + 24) += (v95 >> 5) & 3;
                goto LABEL_220;
              }
            }
            v69 = v62 - *((_DWORD *)this + 8);
            if ( v69 )
            {
              v112 = v69 + v68;
              if ( v69 <= 0 )
                v112 = v69;
              if ( v112 <= 0 || (v113 = v147, v112 >= (int)v147) || v112 >= 31 )
              {
                v53 = -2;
                v12 = (CMeasurer *)((char *)this + 96);
                goto LABEL_104;
              }
              v52 = *((_DWORD *)this + 26);
              do
              {
                --v112;
                v113 = (v113 - 1) & 0x1F;
                v52 -= v148[3 * v113 + 2];
              }
              while ( v112 > 0 );
              *((_DWORD *)this + 26) = v52;
              v12 = (CMeasurer *)((char *)this + 96);
              CLineBasic::SetHeight((CMeasurer *)((char *)this + 96), v148[3 * ((v113 - 1) & 0x1F) + 3]);
              CLineBasic::SetDescent(v115, v148[v114 + 4]);
            }
            else
            {
              v12 = (CMeasurer *)((char *)this + 96);
              if ( v135 )
              {
                v53 = -2;
                goto LABEL_104;
              }
              *((_DWORD *)this + 26) = v131;
            }
          }
        }
        v53 = v123;
        goto LABEL_104;
      }
    }
    else
    {
      v25 = 0;
    }
    ++*(_DWORD *)v12;
    v26 = (unsigned __int16 *)Pch;
    v147 = (unsigned int)(v40 + 1);
    if ( Pch != (CMeasurer *)((char *)this + 270) )
    {
      v26 = (unsigned __int16 *)((char *)Pch + 2);
      Pch = (CMeasurer *)((char *)Pch + 2);
    }
    --v128;
    if ( DestStr[0] == 32 )
    {
      v9 = (_DWORD *)((char *)this + 16);
      if ( (v46 & 0x10) == 0 )
        continue;
    }
    v9 = (_DWORD *)((char *)this + 16);
    v139 = *(_DWORD *)v12;
    v131 = v48;
  }
  if ( CCcs::FillWidth((CCcs *)v36, (CMeasurer *)((char *)this + 304), v37, &v119, 0) )
  {
    v31 = DestStr[0];
    goto LABEL_63;
  }
  v53 = -1;
LABEL_110:
  --g_cFCLock;
  CWriteLock::~CWriteLock((CWriteLock *)&v137);
  return v53;
}

```

## disassembly

```asm
0x18003c0dc  mov     [rsp-8+arg_18], rbx
0x18003c0e1  push    rbp
0x18003c0e2  push    rsi
0x18003c0e3  push    rdi
0x18003c0e4  push    r12
0x18003c0e6  push    r13
0x18003c0e8  push    r14
0x18003c0ea  push    r15
0x18003c0ec  lea     rbp, [rsp-230h]
0x18003c0f4  sub     rsp, 330h
0x18003c0fb  mov     rax, cs:__security_cookie
0x18003c102  xor     rax, rsp
0x18003c105  mov     [rbp+260h+var_40], rax
0x18003c10c  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA
0x18003c112  xor     r15d, r15d
0x18003c115  mov     [rbp+260h+var_2D8], r9d
0x18003c119  mov     edi, r9d
0x18003c11c  mov     [rsp+360h+var_2E4], r8d
0x18003c121  mov     r12d, edx
0x18003c124  mov     [rsp+360h+var_2E8], edx
0x18003c128  mov     rsi, rcx
0x18003c12b  mov     [rbp+260h+var_2B4], r15d
0x18003c12f  test    ebx, ebx
0x18003c131  jz      loc_18003C861
0x18003c137  call    cs:__imp_GetCurrentThreadId
0x18003c13e  nop     dword ptr [rax+rax+00h]
0x18003c143  cmp     ebx, eax
0x18003c145  jnz     loc_18003C861
0x18003c14b  xor     ecx, ecx
0x18003c14d  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z
0x18003c152  lea     r13d, [r15+1]
0x18003c156  add     [rax], r13d
0x18003c159  add     cs:?g_cFCLock@@3JA, r13d
0x18003c160  lea     r14, [rsi+10h]
0x18003c164  mov     rcx, [r14]
0x18003c167  test    rcx, rcx
0x18003c16a  jz      loc_18003CFC6
0x18003c170  mov     edx, [rcx+20h]
0x18003c173  mov     [rbp+260h+var_2DC], edx
0x18003c176  mov     ebx, edi
0x18003c178  mov     [rsp+360h+DestStr], r15w
0x18003c17e  and     ebx, r13d
0x18003c181  mov     [rbp+260h+var_2A8], r15d
0x18003c185  mov     [rsp+360h+var_2FC], r15d
0x18003c18a  lea     rdx, [rcx-8]
0x18003c18e  test    rcx, rcx
0x18003c191  jz      loc_18003CFCF
0x18003c197  mov     rdi, [rdx+30h]
0x18003c19b  mov     [rbp+260h+var_2C8], rdi
0x18003c19f  neg     rcx
0x18003c1a2  mov     [rsp+360h+var_30C], r15d
0x18003c1a7  mov     [rbp+260h+var_2B8], r15d
0x18003c1ab  mov     rcx, rsi; this
0x18003c1ae  sbb     rax, rax
0x18003c1b1  mov     [rbp+260h+var_2C0], r15d
0x18003c1b5  and     rax, rdx
0x18003c1b8  mov     [rbp+260h+var_2BC], r15d
0x18003c1bc  mov     dword ptr [rbp+260h+var_280], r15d
0x18003c1c0  mov     al, [rax+46h]
0x18003c1c3  and     al, 78h
0x18003c1c5  mov     [rsp+360h+var_300], al
0x18003c1c9  call    ?UpdatePF@CMeasurerNoFC@@QEAAXXZ
0x18003c1ce  mov     edi, 0FFFFFFFEh
0x18003c1d3  test    ebx, ebx
0x18003c1d5  jnz     loc_18003CECC
0x18003c1db  xor     edx, edx; bool
0x18003c1dd  lea     r15, [rsi+60h]
0x18003c1e1  mov     rcx, rsi; this
0x18003c1e4  call    ?MeasureLeftIndent@CMeasurer@@QEAAJ_N@Z
0x18003c1e9  xor     ebx, ebx
0x18003c1eb  mov     [r15+4], eax
0x18003c1ef  test    r12d, r12d
0x18003c1f2  jns     loc_18003C9DF
0x18003c1f8  mov     rcx, rsi; this
0x18003c1fb  call    ?GetDupLayout@CMeasurerNoFC@@QEAAJXZ
0x18003c200  mov     rcx, [rsi+98h]
0x18003c207  mov     edi, eax
0x18003c209  mov     rax, [rcx]
0x18003c20c  mov     rax, [rax+78h]
0x18003c210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c215  test    eax, eax
0x18003c217  jz      short loc_18003C236
0x18003c219  mov     rax, [r14]
0x18003c21c  test    rax, rax
0x18003c21f  jz      loc_18003CFD8
0x18003c225  mov     rcx, [rax+28h]
0x18003c229  test    byte ptr [rcx+0B0h], 4
0x18003c230  jz      loc_18003CD83
0x18003c236  mov     eax, ebx
0x18003c238  sub     edi, [rsi+64h]
0x18003c23b  mov     rcx, rsi; this
0x18003c23e  sub     edi, eax
0x18003c240  call    ?MeasureRightIndent@CMeasurerNoFC@@QEAAJ_N@Z
0x18003c245  sub     edi, eax
0x18003c247  mov     eax, [rbp+260h+var_2DC]
0x18003c24a  test    edi, edi
0x18003c24c  cmovle  edi, ebx
0x18003c24f  sub     eax, [rsi+20h]
0x18003c252  mov     ebx, [rsp+360h+var_2E4]
0x18003c256  xor     r8d, r8d
0x18003c259  mov     [rsp+360h+var_308], edi
0x18003c25d  test    ebx, ebx
0x18003c25f  js      loc_18003C89F
0x18003c265  cmp     ebx, eax
0x18003c267  jg      loc_18003C89F
0x18003c26d  mov     eax, [r15]
0x18003c270  mov     r12d, r13d
0x18003c273  mov     edx, [rsi+68h]
0x18003c276  mov     [rbp+260h+var_2AC], eax
0x18003c279  mov     [rbp+260h+var_2D4], edx
0x18003c27c  test    ebx, ebx
0x18003c27e  jle     loc_18003C732
0x18003c284  test    r12d, r12d
0x18003c287  jle     loc_18003C732
0x18003c28d  lea     rcx, [rsi+10Eh]
0x18003c294  mov     eax, r13d
0x18003c297  mov     dword ptr [rsp+360h+var_304], eax
0x18003c29b  cmp     [rsp+360h+var_300], r8b
0x18003c2a0  jnz     loc_18003CD1A
0x18003c2a6  lea     rdx, [rsp+360h+var_304]; int *
0x18003c2ab  mov     rcx, r14; this
0x18003c2ae  call    ?GetPch@CTxtPtr@@QEBAPEBGAEAJ@Z
0x18003c2b3  mov     [rsp+360h+var_2F0], rax
0x18003c2b8  mov     eax, dword ptr [rsp+360h+var_304]
0x18003c2bc  cmp     eax, ebx
0x18003c2be  mov     r11d, ebx
0x18003c2c1  mov     rcx, rsi; this
0x18003c2c4  cmovl   r11d, eax
0x18003c2c8  call    ?GetCchLeftRunCF@CRchTxtPtr@@QEAAJXZ
0x18003c2cd  cmp     r11d, eax
0x18003c2d0  mov     r12d, eax
0x18003c2d3  mov     rcx, rsi; this
0x18003c2d6  cmovl   r12d, r11d
0x18003c2da  mov     [rsp+360h+var_2F8], r12d
0x18003c2df  mov     [rbp+260h+var_2E0], r12d
0x18003c2e3  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ
0x18003c2e8  mov     [rbp+260h+var_2A0], rax
0x18003c2ec  mov     eax, [rax]
0x18003c2ee  mov     [rbp+260h+var_288], eax
0x18003c2f1  bt      eax, 8
0x18003c2f5  jb      loc_18003C9AD
0x18003c2fb  xor     eax, eax
0x18003c2fd  mov     r9b, 0FFh; unsigned __int8
0x18003c300  mov     [rsp+360h+cchDest], eax; int
0x18003c304  xor     r8d, r8d; unsigned __int8
0x18003c307  xor     edx, edx; int
0x18003c309  mov     [rsp+360h+lpDestStr], rax; unsigned __int16 *
0x18003c30e  mov     rcx, rsi; this
0x18003c311  call    ?Check_pccs@CMeasurer@@QEAAPEAVCCcs@@HEEPEBGJ@Z
0x18003c316  xor     r11d, r11d
0x18003c319  test    rax, rax
0x18003c31c  jz      loc_18003D1F9
0x18003c322  mov     rdx, [rsp+360h+var_2F0]
0x18003c327  test    r12d, r12d
0x18003c32a  jle     short loc_18003C39E
0x18003c32c  test    rdx, rdx
0x18003c32f  jz      short loc_18003C39E
0x18003c331  cmp     [rdx], r11w
0x18003c335  jz      short loc_18003C39E
0x18003c337  mov     rcx, rsi; this
0x18003c33a  call    ?IsRich@CRchTxtPtr@@QEBAHXZ
0x18003c33f  test    eax, eax
0x18003c341  jz      loc_18003CE68
0x18003c347  cmp     [rbp+260h+var_2AC], r11d
0x18003c34b  jnz     loc_18003CC3D
0x18003c351  test    byte ptr [rsi+6Dh], 10h
0x18003c355  lea     rbx, [rsi+6Fh]
0x18003c359  jnz     loc_18003CD12
0x18003c35f  mov     al, [rbx]
0x18003c361  and     al, 3
0x18003c363  cmp     al, r13b
0x18003c366  jz      loc_18003CFE0
0x18003c36c  cmp     al, 2
0x18003c36e  jz      loc_18003D002
0x18003c374  mov     edi, [rsi+7Ch]
0x18003c377  mov     r8, [rbp+260h+var_2A0]; struct CCharFormat *
0x18003c37b  mov     rcx, rsi; this
0x18003c37e  mov     rdx, [rsi+148h]; struct CCcs *
0x18003c385  call    ?RecalcLineHeight@CMeasurer@@AEAAXPEAVCCcs@@QEBVCCharFormat@@@Z
0x18003c38a  xor     r11d, r11d
0x18003c38d  test    edi, edi
0x18003c38f  jnz     loc_18003CD24
0x18003c395  mov     rdx, [rsp+360h+var_2F0]
0x18003c39a  mov     edi, [rsp+360h+var_308]
0x18003c39e  mov     ebx, [rbp+260h+var_2E0]
0x18003c3a1  test    ebx, ebx
0x18003c3a3  jle     loc_18003D113
0x18003c3a9  mov     [rsp+360h+var_30C], r11d
0x18003c3ae  cmp     [rsp+360h+var_300], r11b
0x18003c3b3  jnz     loc_18003CC79
0x18003c3b9  movzx   r8d, word ptr [rdx]; unsigned __int16
0x18003c3bd  mov     [rsp+360h+DestStr], r8w
0x18003c3c3  movzx   eax, r8w
0x18003c3c7  mov     r10, [rbp+260h+var_2A0]
0x18003c3cb  cmp     byte ptr [r10+4], 0Ah
0x18003c3d0  jz      loc_18003C65C
0x18003c3d6  test    byte ptr [rbp+260h+var_288], 0C0h
0x18003c3da  jnz     loc_18003C7E2
0x18003c3e0  mov     rcx, [r14]
0x18003c3e3  test    rcx, rcx
0x18003c3e6  jz      loc_18003CE96
0x18003c3ec  mov     rdx, [rcx+28h]
0x18003c3f0  test    dword ptr [rdx+11Ch], 200h
0x18003c3fa  jnz     loc_18003C7E2
0x18003c400  test    rcx, rcx
0x18003c403  jz      loc_18003CE9E
0x18003c409  mov     rcx, [rcx+28h]
0x18003c40d  test    dword ptr [rcx+11Ch], 400h
0x18003c417  jnz     loc_18003C84B
0x18003c41d  xor     r10d, r10d
0x18003c420  mov     eax, 0FFFCh
0x18003c425  cmp     r8w, ax
0x18003c429  jz      loc_18003C9FF
0x18003c42f  movzx   eax, r8w
0x18003c433  sub     eax, 7
0x18003c436  cmp     eax, 6
0x18003c439  jbe     loc_18003C68D
0x18003c43f  mov     r14, [rsi+148h]
0x18003c446  mov     eax, 3400h
0x18003c44b  movzx   edi, r8w
0x18003c44f  cmp     di, ax
0x18003c452  jnb     loc_18003CEA6
0x18003c458  lea     eax, [rdi-0D800h]
0x18003c45e  cmp     eax, 3FFh
0x18003c463  jbe     short loc_18003C49F
0x18003c465  mov     rax, [r14+40h]
0x18003c469  movsxd  rcx, dword ptr [r14+2Ch]
0x18003c46d  and     rcx, rdi
0x18003c470  lea     r9, [rax+rcx*8]
0x18003c474  cmp     di, [rax+rcx*8]
0x18003c478  jnz     loc_18003C9D2
0x18003c47e  mov     eax, [r9+4]
0x18003c482  test    eax, eax
0x18003c484  jz      loc_18003C9D2
0x18003c48a  mov     ebx, r13d
0x18003c48d  mov     [rsp+360h+var_30C], eax
0x18003c491  cmp     [r14+3Ch], r10d
0x18003c495  jz      loc_18003C5C6
0x18003c49b  test    ebx, ebx
0x18003c49d  jnz     short loc_18003C4CD
0x18003c49f  lea     rdx, [rsi+130h]; struct CHDC *
0x18003c4a6  mov     [rsp+360h+lpDestStr], r10; struct CCcs::RunContext *
0x18003c4ab  lea     r9, [rsp+360h+var_30C]; int *
0x18003c4b0  movzx   r8d, di; unsigned __int16
0x18003c4b4  mov     rcx, r14; this
0x18003c4b7  call    ?FillWidth@CCcs@@AEAA_NAEBVCHDC@@GAEAJPEAURunContext@1@@Z
0x18003c4bc  xor     r10d, r10d
0x18003c4bf  test    al, al
0x18003c4c1  jz      loc_18003C8AA
0x18003c4c7  movzx   r8d, [rsp+360h+DestStr]
0x18003c4cd  movzx   ecx, r8w
0x18003c4d1  lea     eax, [rcx-0A0h]
0x18003c4d7  cmp     eax, 1F71h
0x18003c4dc  jbe     loc_18003C5E4
0x18003c4e2  mov     eax, 0FEFFh
0x18003c4e7  cmp     r8w, ax
0x18003c4eb  jz      loc_18003C5E4
0x18003c4f1  mov     eax, 0FFFEh
0x18003c4f6  cmp     r8w, ax
0x18003c4fa  jz      loc_18003C5E4
0x18003c500  cmp     [rsi+10Eh], r10w
0x18003c508  jnz     loc_18003CC5A
0x18003c50e  mov     edi, [rsp+360h+var_308]
0x18003c512  mov     r14, [rbp+260h+var_280]
0x18003c516  mov     eax, r14d
0x18003c519  and     eax, 1Fh
0x18003c51c  test    byte ptr [rsi+6Dh], 10h
0x18003c520  lea     rbx, [rax+rax*2]
0x18003c524  mov     eax, [rsp+360h+var_30C]
0x18003c528  mov     [rbp+rbx*4+260h+var_270], eax
0x18003c52c  jnz     loc_18003C5DD
0x18003c532  mov     al, [rsi+6Fh]
0x18003c535  and     al, 3
0x18003c537  cmp     al, r13b
0x18003c53a  jz      loc_18003D0D9
0x18003c540  cmp     al, 2
0x18003c542  jz      loc_18003D0F9
0x18003c548  mov     eax, [rsi+7Ch]
0x18003c54b  xor     edx, edx; bool
0x18003c54d  mov     [rbp+rbx*4+260h+var_26C], eax
0x18003c551  mov     rcx, r15; this
0x18003c554  call    ?GetDescent@CLine@@QEBAJ_N@Z
0x18003c559  mov     ecx, [rbp+260h+var_2D8]
0x18003c55c  mov     [rbp+rbx*4+260h+var_268], eax
0x18003c560  mov     eax, [rsp+360h+var_30C]
0x18003c564  add     [rsi+68h], eax
0x18003c567  mov     ebx, [rsi+68h]
0x18003c56a  cmp     ebx, edi
0x18003c56c  jg      loc_18003C8C7
0x18003c572  xor     r11d, r11d
0x18003c575  add     [r15], r13d
0x18003c578  lea     rax, [rsi+10Eh]
0x18003c57f  mov     rdx, [rsp+360h+var_2F0]
0x18003c584  add     r14d, r13d
0x18003c587  mov     [rbp+260h+var_280], r14
0x18003c58b  cmp     rdx, rax
0x18003c58e  jz      short loc_18003C599
0x18003c590  add     rdx, 2
0x18003c594  mov     [rsp+360h+var_2F0], rdx
0x18003c599  sub     [rbp+260h+var_2E0], r13d
  ... truncated ...
```
