# COls::MeasureLine(long,CLine *)

- ea: `0x180014850`
- end: `0x18001543f`
- name: `?MeasureLine@COls@@QEAAHJPEAVCLine@@@Z`
- size: `3055`
- prototype: `__int64 __fastcall(COls *__hidden this, int, struct CLine *)`
- caller_count: `5`
- callee_count: `19`
- tags: ``

## callers

- `0x180015670`
- `0x180020940`
- `0x180023cac`
- `0x1800427f8`
- `0x18004a138`

## callees

- `0x180006570`
- `0x180014580`
- `0x180014850`
- `0x180015448`
- `0x18001f1f4`
- `0x18001f230`
- `0x18001f4a0`
- `0x180031870`
- `0x180031e30`
- `0x18003a2f0`
- `0x18003ae40`
- `0x18003b0a8`
- `0x18003b828`
- `0x18003e4cc`
- `0x18003eca0`
- `0x180043d80`
- `0x1800466f0`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180014e93`
- `KERNEL32!MulDiv` at `0x180014e93`
- `KERNEL32!EnterCriticalSection` at `0x1800148a9`
- `KERNEL32!EnterCriticalSection` at `0x1800148a9`
- `KERNEL32!LeaveCriticalSection` at `0x18001492f`
- `KERNEL32!LeaveCriticalSection` at `0x18001492f`
- `msls31!__imp_LsCreateLine` at `0x180014a6c`
- `msls31!__imp_LsCreateLine` at `0x180015292`
- `msls31!__imp_LsCreateLine` at `0x180014a6c`
- `msls31!__imp_LsCreateLine` at `0x180015292`
- `msls31!__imp_LsDestroyLine` at `0x1800148cc`
- `msls31!__imp_LsDestroyLine` at `0x1800148cc`
- `msls31!__imp_LsQueryLineDup` at `0x180014b1a`
- `msls31!__imp_LsQueryLineDup` at `0x1800151fb`
- `msls31!__imp_LsQueryLineDup` at `0x180014b1a`
- `msls31!__imp_LsQueryLineDup` at `0x1800151fb`
- `msls31!__imp_LsSetDoc` at `0x1800149a6`
- `msls31!__imp_LsSetDoc` at `0x1800149a6`

## pseudocode

```c
__int64 __fastcall COls::MeasureLine(COls *this, int a2, struct CLine *a3)
{
  __int64 v3; // rbx
  unsigned int v5; // r12d
  __int64 *v6; // r14
  __int64 *v7; // r15
  int v8; // r9d
  int i; // ecx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  _DWORD *v13; // r12
  _DWORD *v14; // r13
  char v15; // cl
  unsigned int v16; // ecx
  int *v17; // rax
  int v18; // r8d
  int v19; // r14d
  int v20; // ecx
  int v21; // ecx
  char v22; // cl
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  int v26; // ecx
  __int64 v27; // rax
  int v28; // esi
  int v29; // r11d
  __int64 v30; // r9
  int v31; // r8d
  int v32; // ecx
  int v33; // ecx
  int v34; // r10d
  int *v35; // r8
  int v36; // eax
  int v37; // ecx
  int v38; // eax
  __int64 v39; // rdx
  int v40; // eax
  int v41; // ecx
  int v42; // eax
  int v43; // ecx
  int v44; // ecx
  __int64 v45; // r10
  int v46; // eax
  int v47; // edx
  int v48; // r11d
  int *v49; // r9
  int v50; // esi
  int v51; // eax
  int v52; // edx
  __int64 v53; // r9
  int v54; // eax
  int v55; // edx
  int *v56; // r8
  int v57; // eax
  int v58; // ecx
  int v59; // r10d
  __int64 v60; // rdx
  int v61; // ecx
  struct CLine *v62; // rdi
  _DWORD *v64; // rax
  int v65; // ecx
  int v66; // r8d
  int v67; // eax
  int v68; // eax
  int v69; // r8d
  _DWORD *v70; // rax
  int v71; // edx
  int v72; // eax
  int v73; // eax
  int v74; // edx
  _DWORD *v75; // rax
  int v76; // eax
  int v77; // edx
  int v78; // eax
  int v79; // eax
  int v80; // edx
  _DWORD *v81; // rax
  int Char; // edx
  unsigned __int16 v83; // ax
  __int64 v84; // rdx
  int v85; // ecx
  __int16 v86; // ax
  __int16 v87; // ax
  __int64 v88; // rdx
  int v89; // eax
  char v90; // al
  __int64 v91; // rcx
  unsigned int v92; // eax
  __int64 v93; // rdx
  __int16 v94; // cx
  __int16 v95; // dx
  __int128 v96; // xmm6
  __int64 v97; // xmm7_8
  CMeasurer *v98; // rcx
  int nNumber; // [rsp+50h] [rbp-B0h] BYREF
  int v100; // [rsp+54h] [rbp-ACh] BYREF
  int v101; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v102; // [rsp+5Ch] [rbp-A4h]
  int v103; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v104; // [rsp+68h] [rbp-98h] BYREF
  struct CLine *v105; // [rsp+70h] [rbp-90h]
  __int128 v106; // [rsp+78h] [rbp-88h] BYREF
  __int128 v107; // [rsp+90h] [rbp-70h] BYREF
  __int128 v108; // [rsp+A0h] [rbp-60h]
  __int128 v109; // [rsp+B0h] [rbp-50h]
  __int128 v110; // [rsp+C0h] [rbp-40h]
  __int128 v111; // [rsp+D0h] [rbp-30h]
  int v112; // [rsp+E0h] [rbp-20h]
  _BYTE v113[24]; // [rsp+F0h] [rbp-10h] BYREF

  v3 = *(_QWORD *)this;
  v105 = a3;
  nNumber = a2;
  v5 = *(_DWORD *)(v3 + 32);
  v6 = *(__int64 **)(v3 + 120);
  v104 = *(_QWORD *)(v3 + 144);
  v102 = v5;
  EnterCriticalSection(&g_CriticalSection);
  v7 = (__int64 *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    LsDestroyLine(g_plsc);
    *v7 = 0;
  }
  if ( *((_DWORD *)this + 12) )
    CArrayBase::Clear((char *)this + 40, 1);
  v8 = *((_DWORD *)this + 18);
  for ( i = 0; i < v8; *(_DWORD *)(v12 + 8) = 0 )
  {
    v10 = *((_DWORD *)this + 18);
    if ( v10 > 0 && i < v10 && (v11 = *((_QWORD *)this + 8)) != 0 )
      v12 = v11 + *((_DWORD *)this + 20) * i;
    else
      v12 = 0;
    ++i;
  }
  LeaveCriticalSection(&g_CriticalSection);
  *((_DWORD *)this + 4) = v5;
  v13 = (_DWORD *)(v3 + 116);
  *((_DWORD *)this + 9) = 0;
  v14 = (_DWORD *)(v3 + 132);
  *((_QWORD *)this + 3) = v6;
  v15 = *(_BYTE *)(v3 + 162);
  if ( (v15 & 2) != 0 )
  {
    if ( *(_DWORD *)(v3 + 128) != *(_DWORD *)(v3 + 112) && *v14 != *v13 )
    {
      v88 = *(_QWORD *)(v3 + 136);
      if ( v88 )
      {
        v86 = *(_WORD *)(v88 + 10);
        if ( v86 )
        {
          *(_WORD *)(v88 + 10) = v86 - 1;
          v15 = *(_BYTE *)(v3 + 162);
        }
      }
      *(_QWORD *)(v3 + 136) = 0;
    }
    *(_BYTE *)(v3 + 162) = v15 & 0xFD;
  }
  v106 = 0;
  HIDWORD(v106) = *(_DWORD *)(v3 + 112);
  DWORD2(v106) = *v13;
  DWORD1(v106) = *(_DWORD *)(v3 + 128);
  LODWORD(v106) = *v14;
  LsSetDoc(g_plsc, 1, *((_QWORD *)&v106 + 1) == v106, &v106);
  if ( nNumber == -1 )
  {
    v38 = (*(__int64 (__fastcall **)(__int64 *))(*v6 + 136))(v6);
    v39 = *v6;
    if ( v38 )
    {
      v89 = (*(__int64 (__fastcall **)(__int64 *))(v39 + 136))(v6);
      nNumber = CMeasurer::LXtoDX((CMeasurer *)v3, v89);
    }
    else
    {
      v40 = (*(__int64 (__fastcall **)(__int64 *))(v39 + 152))(v6);
      v41 = 0;
      v42 = v40 - 1;
      if ( v42 >= 0 )
        v41 = v42;
      nNumber = v41;
    }
  }
  if ( (*(unsigned int (__fastcall **)(__int64 *))(*v6 + 128))(v6) )
  {
    v16 = nNumber;
    goto LABEL_15;
  }
  v16 = 0xFFFFF;
  v90 = *(_BYTE *)(v104 + 16);
  if ( v90 == 1 )
  {
    if ( (*(_BYTE *)(v104 + 2) & 1) == 0 )
      goto LABEL_15;
    goto LABEL_171;
  }
  if ( v90 != 2 || (*(_BYTE *)(v104 + 2) & 1) == 0 )
LABEL_171:
    *((_DWORD *)this + 9) = 1;
LABEL_15:
  *((_DWORD *)this + 8) = v16;
  v112 = 0;
  v17 = (int *)(v3 + 132);
  v103 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  if ( (*(_BYTE *)(v3 + 162) & 2) != 0 )
    v17 = (int *)(v3 + 116);
  v18 = *v17;
  if ( *v17 != 1440 && (!v18 || v16) )
    v16 = MulDiv(v16, 1440, v18);
  v19 = LsCreateLine(g_plsc, v102, v16, 0, 0, 3, v113, &v103, &v107, (char *)this + 8);
  if ( *((_DWORD *)this + 9) )
  {
    v91 = *v7;
    v100 = 0;
    v101 = 0;
    if ( (unsigned int)LsQueryLineDup(v91, &v100, &v100, &v100, &v101, &v100) )
      return 0;
    v84 = *(_QWORD *)(v3 + 144);
    if ( (*(_WORD *)(v84 + 2) & 0x4000) != 0 )
    {
      v85 = nNumber - CMeasurer::LXtoDX((CMeasurer *)v3, *(_DWORD *)(v84 + 12));
      nNumber = v85;
    }
    else
    {
      v85 = nNumber;
    }
    if ( v101 < v85 )
    {
      *((_DWORD *)this + 8) = v85;
      *((_DWORD *)this + 9) = 0;
      COls::DestroyLine(this, 0);
      v92 = CMeasurer::DXtoLX((CMeasurer *)v3, nNumber);
      v19 = LsCreateLine(g_plsc, v102, v92, 0, 0, 3, v113, &v103, &v107, (char *)this + 8);
    }
  }
  v20 = DWORD2(v108);
  if ( (int)v107 > SDWORD2(v108) )
    v20 = v107;
  LODWORD(v107) = v20;
  v21 = v109;
  if ( SDWORD2(v107) > (int)v109 )
    v21 = DWORD2(v107);
  DWORD2(v107) = v21;
  v22 = *(_BYTE *)(v3 + 162);
  if ( (v22 & 2) != 0 )
  {
    if ( *(_DWORD *)(v3 + 128) != *(_DWORD *)(v3 + 112) && *v14 != *v13 )
    {
      v93 = *(_QWORD *)(v3 + 136);
      if ( v93 )
      {
        v87 = *(_WORD *)(v93 + 10);
        if ( v87 )
        {
          *(_WORD *)(v93 + 10) = v87 - 1;
          v22 = *(_BYTE *)(v3 + 162);
        }
      }
      *(_QWORD *)(v3 + 136) = 0;
    }
    *(_BYTE *)(v3 + 162) = v22 & 0xFD;
  }
  v23 = *((_DWORD *)this + 12);
  if ( v23 )
  {
    if ( v23 > 0 && (v64 = (_DWORD *)*((_QWORD *)this + 5)) != 0 )
    {
      v65 = 0;
      do
      {
        if ( SDWORD2(v109) <= *v64 )
          break;
        --v65;
        ++v64;
      }
      while ( v64 );
    }
    else
    {
      v65 = 0;
    }
    v24 = v65 + DWORD2(v109);
  }
  else
  {
    v24 = DWORD2(v109);
  }
  DWORD2(v109) = v24;
  if ( v19 )
  {
    CCallMgr::SetOutOfMemory(*(CCallMgr **)(*(_QWORD *)(v3 + 40) + 144LL));
    return 0;
  }
  if ( (*(_BYTE *)(v3 + 162) & 1) == 0 )
  {
    *(_DWORD *)(v3 + 80) = v24 - v102;
    v25 = *v7;
    v101 = 0;
    v100 = 0;
    nNumber = 0;
    LODWORD(v104) = 0;
    if ( !(unsigned int)LsQueryLineDup(v25, &v101, &v101, &v100, &nNumber, &v104) )
    {
      v26 = v100;
      *(_DWORD *)(v3 + 88) = nNumber - v100;
      v27 = *(_QWORD *)(v3 + 40);
      *(_DWORD *)(v3 + 84) = v26;
      if ( (*(_BYTE *)(v27 + 180) & 1) != 0 )
      {
        *(_WORD *)(v3 + 92) = WORD4(v107) + v107;
        *(_WORD *)(v3 + 94) = WORD4(v107);
      }
      else
      {
        CMeasurer::CheckLineHeight((CMeasurer *)v3);
      }
      v28 = *(_DWORD *)(v3 + 32);
      *(_BYTE *)(v3 + 100) = 0;
      v29 = DWORD2(v109) - v28;
      if ( DWORD2(v109) != v28 )
      {
        v30 = *(_QWORD *)(v3 + 16);
        if ( v30 )
        {
          v31 = *(_DWORD *)(v30 + 8);
          if ( v31 )
          {
            v32 = DWORD2(v109);
            if ( SDWORD2(v109) < v28 / 2 )
            {
              *(_QWORD *)(v3 + 24) = 0;
              if ( v32 <= 0 )
                v32 = 0;
              v43 = CRunPtrBase::AdvanceCp((CRunPtrBase *)(v3 + 16), v32);
            }
            else
            {
              v33 = DWORD2(v109) - v28;
              if ( v29 < 0 )
              {
                while ( v33 < 0 )
                {
                  v76 = *(_DWORD *)(v3 + 28);
                  v77 = v76 + v33;
                  if ( -v33 <= v76 )
                  {
                    *(_DWORD *)(v3 + 28) = v77;
LABEL_56:
                    v33 = 0;
                    break;
                  }
                  v78 = *(_DWORD *)(v3 + 24);
                  v33 = v77;
                  if ( v78 <= 0 )
                  {
                    *(_QWORD *)(v3 + 24) = 0;
                    break;
                  }
                  v79 = v78 - 1;
                  *(_DWORD *)(v3 + 24) = v79;
                  v80 = *(_DWORD *)(v30 + 8);
                  if ( v80 > 0 && v79 < v80 && *(_QWORD *)v30 && v79 >= 0 )
                    v81 = (_DWORD *)(*(_QWORD *)v30 + *(_DWORD *)(v30 + 16) * v79);
                  else
                    v81 = 0;
                  *(_DWORD *)(v3 + 28) = *v81;
                }
              }
              else
              {
                v34 = *(_DWORD *)(v3 + 24);
                if ( v31 > 0 && v34 < v31 && *(_QWORD *)v30 && v34 >= 0 )
                  v35 = (int *)(*(_QWORD *)v30 + *(_DWORD *)(v30 + 16) * v34);
                else
                  v35 = 0;
                while ( v33 > 0 )
                {
                  v36 = *v35;
                  *(_DWORD *)(v3 + 28) += v33;
                  v37 = *(_DWORD *)(v3 + 28);
                  if ( v37 < v36 )
                    goto LABEL_56;
                  v33 = v37 - v36;
                  *(_DWORD *)(v3 + 24) = v34 + 1;
                  if ( v34 + 1 >= *(_DWORD *)(v30 + 8) )
                  {
                    *(_DWORD *)(v3 + 24) = v34;
                    *(_DWORD *)(v3 + 28) = v36;
                    break;
                  }
                  *(_DWORD *)(v3 + 28) = 0;
                  ++v34;
                  v35 = (int *)((char *)v35 + *(int *)(v30 + 16));
                }
              }
              v43 = v28 + v29 - v33;
            }
            *(_DWORD *)(v3 + 32) = v43;
            v44 = v43 - v28;
            if ( v44 )
            {
              v45 = *(_QWORD *)(v3 + 48);
              if ( !v45 || (v46 = *(_DWORD *)(v45 + 8)) == 0 )
              {
                v50 = v44;
                goto LABEL_75;
              }
              v47 = v44;
              if ( v44 < 0 )
              {
                v50 = v44;
                while ( v47 < 0 )
                {
                  v66 = *(_DWORD *)(v3 + 60);
                  if ( -v47 <= v66 )
                  {
                    *(_DWORD *)(v3 + 60) = v47 + v66;
                    goto LABEL_75;
                  }
                  v67 = *(_DWORD *)(v3 + 56);
                  if ( v67 <= 0 )
                  {
                    *(_QWORD *)(v3 + 56) = 0;
                    goto LABEL_75;
                  }
                  v47 += v66;
                  v68 = v67 - 1;
                  *(_DWORD *)(v3 + 56) = v68;
                  v69 = *(_DWORD *)(v45 + 8);
                  if ( v69 > 0 && v68 < v69 && *(_QWORD *)v45 && v68 >= 0 )
                    v70 = (_DWORD *)(*(_QWORD *)v45 + *(_DWORD *)(v45 + 16) * v68);
                  else
                    v70 = 0;
                  *(_DWORD *)(v3 + 60) = *v70;
                }
                goto LABEL_75;
              }
              v48 = *(_DWORD *)(v3 + 56);
              if ( v46 > 0 && v48 < v46 && *(_QWORD *)v45 && v48 >= 0 )
                v49 = (int *)(*(_QWORD *)v45 + *(_DWORD *)(v45 + 16) * v48);
              else
                v49 = 0;
              v50 = v44;
              while ( v47 > 0 )
              {
                v51 = *v49;
                *(_DWORD *)(v3 + 60) += v47;
                v52 = *(_DWORD *)(v3 + 60);
                if ( v52 < v51 )
                  goto LABEL_75;
                *(_DWORD *)(v3 + 56) = v48 + 1;
                if ( v48 + 1 >= *(_DWORD *)(v45 + 8) )
                {
                  *(_DWORD *)(v3 + 56) = v48;
                  *(_DWORD *)(v3 + 60) = v51;
                  goto LABEL_75;
                }
                v47 = v52 - v51;
                *(_DWORD *)(v3 + 60) = 0;
                ++v48;
                v49 = (int *)((char *)v49 + *(int *)(v45 + 16));
              }
            }
            else
            {
              v50 = 0;
            }
            if ( v50 )
            {
              v44 = v50;
LABEL_75:
              v53 = *(_QWORD *)(v3 + 64);
              if ( v53 )
              {
                v54 = *(_DWORD *)(v53 + 8);
                if ( v54 )
                {
                  if ( v50 < 0 )
                  {
                    while ( v44 < 0 )
                    {
                      v71 = *(_DWORD *)(v3 + 76);
                      if ( -v44 <= v71 )
                      {
                        *(_DWORD *)(v3 + 76) = v44 + v71;
                        break;
                      }
                      v72 = *(_DWORD *)(v3 + 72);
                      if ( v72 <= 0 )
                      {
                        *(_QWORD *)(v3 + 72) = 0;
                        break;
                      }
                      v44 += v71;
                      v73 = v72 - 1;
                      *(_DWORD *)(v3 + 72) = v73;
                      v74 = *(_DWORD *)(v53 + 8);
                      if ( v74 > 0 && v73 < v74 && *(_QWORD *)v53 && v73 >= 0 )
                        v75 = (_DWORD *)(*(_QWORD *)v53 + *(_DWORD *)(v53 + 16) * v73);
                      else
                        v75 = 0;
                      *(_DWORD *)(v3 + 76) = *v75;
                    }
                  }
                  else
                  {
                    v55 = *(_DWORD *)(v3 + 72);
                    if ( v54 > 0 && v55 < v54 && *(_QWORD *)v53 && v55 >= 0 )
                      v56 = (int *)(*(_QWORD *)v53 + *(_DWORD *)(v53 + 16) * v55);
                    else
                      v56 = 0;
                    while ( v44 > 0 )
                    {
                      v57 = *v56;
                      *(_DWORD *)(v3 + 76) += v44;
                      v58 = *(_DWORD *)(v3 + 76);
                      if ( v58 < v57 )
                        break;
                      v59 = v55++;
                      *(_DWORD *)(v3 + 72) = v55;
                      if ( v55 >= *(_DWORD *)(v53 + 8) )
                      {
                        *(_DWORD *)(v3 + 72) = v59;
                        *(_DWORD *)(v3 + 76) = v57;
                        break;
                      }
                      v44 = v58 - v57;
                      *(_DWORD *)(v3 + 76) = 0;
                      v56 = (int *)((char *)v56 + *(int *)(v53 + 16));
                    }
                  }
                }
              }
            }
          }
        }
      }
      if ( (unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)(v3 + 16)) )
      {
        Char = CTxtPtr::PrevChar((CTxtPtr *)(v3 + 16));
        if ( *(_DWORD *)(v3 + 32) )
        {
          if ( (unsigned int)(Char - 56320) <= 0x3FF )
          {
            LOWORD(Char) = CTxtPtr::PrevChar((CTxtPtr *)(v3 + 16));
            if ( (unsigned int)(unsigned __int16)Char - 55296 > 0x3FF )
              LOWORD(Char) = CTxtPtr::NextChar((CTxtPtr *)(v3 + 16));
          }
        }
        if ( (_WORD)Char == 10
          && *(_DWORD *)(v3 + 32)
          && (CTxtPtr::PrevChar((CTxtPtr *)(v3 + 16)) != 13
           || *(_DWORD *)(v3 + 32) && CTxtPtr::PrevChar((CTxtPtr *)(v3 + 16)) != 13) )
        {
          CTxtPtr::AdvanceCp((CTxtPtr *)(v3 + 16), 1);
        }
        v83 = CTxtPtr::GetChar((CTxtPtr *)(v3 + 16));
        if ( v83 == 13 || (*(_DWORD *)(*(_QWORD *)(v3 + 40) + 180LL) & 0x80000) != 0 && v83 == 10 )
          *(_BYTE *)(v3 + 101) |= 1u;
        *(_BYTE *)(v3 + 100) = CTxtPtr::AdvanceCpCRLF((CTxtPtr *)(v3 + 16), 0);
      }
      v60 = *(_QWORD *)(v3 + 40);
      if ( v60 )
        v61 = *(_DWORD *)(*(_QWORD *)(v3 + 16) + 24LL);
      else
        v61 = 0;
      if ( SDWORD2(v109) <= v61
        || (*(_BYTE *)(v60 + 180) & 1) != 0 && !(unsigned int)CRchTxtPtr::IsHidden((CRchTxtPtr *)v3) )
      {
        CMeasurer::AdjustLineHeight((CMeasurer *)v3);
      }
      else
      {
        --*(_DWORD *)(v3 + 80);
      }
      goto LABEL_92;
    }
    return 0;
  }
LABEL_92:
  v62 = v105;
  if ( v105 )
  {
    v94 = WORD2(v109);
    v95 = WORD6(v108);
    if ( SDWORD1(v107) > SHIDWORD(v108) )
      v95 = WORD2(v107);
    v96 = *(_OWORD *)(v3 + 80);
    if ( SHIDWORD(v107) > SDWORD1(v109) )
      v94 = WORD6(v107);
    v97 = *(_QWORD *)(v3 + 96);
    *(_WORD *)(v3 + 92) = v95 + v94;
    *(_WORD *)(v3 + 94) = WORD6(v107);
    CMeasurer::SetUseTargetDevice((CMeasurer *)v3, 1);
    CMeasurer::AdjustLineHeight(v98);
    CMeasurer::SetUseTargetDevice((CMeasurer *)v3, 0);
    *(_OWORD *)v62 = *(_OWORD *)(v3 + 80);
    *((_QWORD *)v62 + 2) = *(_QWORD *)(v3 + 96);
    *(_OWORD *)(v3 + 80) = v96;
    *(_QWORD *)(v3 + 96) = v97;
  }
  return 1;
}

```

## disassembly

```asm
0x180014850  mov     [rsp-8+arg_18], rbx
0x180014855  push    rbp
0x180014856  push    rsi
0x180014857  push    rdi
0x180014858  push    r12
0x18001485a  push    r13
0x18001485c  push    r14
0x18001485e  push    r15
0x180014860  lea     rbp, [rsp-30h]
0x180014865  sub     rsp, 130h
0x18001486c  mov     rax, cs:__security_cookie
0x180014873  xor     rax, rsp
0x180014876  mov     [rbp+60h+var_58], rax
0x18001487a  mov     rbx, [rcx]
0x18001487d  mov     rsi, rcx
0x180014880  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014887  mov     [rsp+160h+var_F0], r8
0x18001488c  mov     [rsp+160h+nNumber], edx
0x180014890  mov     rax, [rbx+90h]
0x180014897  mov     r12d, [rbx+20h]
0x18001489b  mov     r14, [rbx+78h]
0x18001489f  mov     [rsp+160h+var_F8], rax
0x1800148a4  mov     [rsp+160h+var_104], r12d
0x1800148a9  call    cs:__imp_EnterCriticalSection
0x1800148b0  nop     dword ptr [rax+rax+00h]
0x1800148b5  mov     rdx, [rsi+8]
0x1800148b9  lea     r15, [rsi+8]
0x1800148bd  xor     r13d, r13d
0x1800148c0  test    rdx, rdx
0x1800148c3  jz      short loc_1800148DB
0x1800148c5  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x1800148cc  call    cs:__imp_LsDestroyLine
0x1800148d3  nop     dword ptr [rax+rax+00h]
0x1800148d8  mov     [r15], r13
0x1800148db  cmp     [rsi+30h], r13d
0x1800148df  jnz     loc_180015146
0x1800148e5  mov     r9d, [rsi+48h]
0x1800148e9  mov     ecx, r13d
0x1800148ec  test    r9d, r9d
0x1800148ef  jle     short loc_180014928
0x1800148f1  mov     eax, [rsi+48h]
0x1800148f4  test    eax, eax
0x1800148f6  jle     loc_180015099
0x1800148fc  cmp     ecx, eax
0x1800148fe  jge     loc_180015099
0x180014904  mov     r8, [rsi+40h]
0x180014908  test    r8, r8
0x18001490b  jz      loc_180015099
0x180014911  mov     eax, ecx
0x180014913  imul    eax, [rsi+50h]
0x180014917  movsxd  rdx, eax
0x18001491a  add     rdx, r8
0x18001491d  inc     ecx
0x18001491f  mov     [rdx+8], r13d
0x180014923  cmp     ecx, r9d
0x180014926  jl      short loc_1800148F1
0x180014928  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001492f  call    cs:__imp_LeaveCriticalSection
0x180014936  nop     dword ptr [rax+rax+00h]
0x18001493b  mov     [rsi+10h], r12d
0x18001493f  lea     r12, [rbx+74h]
0x180014943  mov     [rsi+24h], r13d
0x180014947  lea     r13, [rbx+84h]
0x18001494e  mov     [rsi+18h], r14
0x180014952  movzx   ecx, byte ptr [rbx+0A2h]
0x180014959  test    cl, 2
0x18001495c  jnz     loc_180014C2C
0x180014962  xorps   xmm0, xmm0
0x180014965  movups  [rsp+160h+var_E8], xmm0
0x18001496a  mov     ecx, [rbx+70h]
0x18001496d  mov     dword ptr [rbp+60h+var_E8+0Ch], ecx
0x180014970  mov     edx, [r12]
0x180014974  mov     dword ptr [rbp+60h+var_E8+8], edx
0x180014977  mov     eax, [rbx+80h]
0x18001497d  mov     dword ptr [rsp+160h+var_E8+4], eax
0x180014981  mov     r8d, [r13+0]
0x180014985  mov     dword ptr [rsp+160h+var_E8], r8d
0x18001498a  cmp     ecx, eax
0x18001498c  jz      loc_180014CA3
0x180014992  xor     r8d, r8d
0x180014995  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x18001499c  lea     r9, [rsp+160h+var_E8]
0x1800149a1  mov     edx, 1
0x1800149a6  call    cs:__imp_LsSetDoc
0x1800149ad  nop     dword ptr [rax+rax+00h]
0x1800149b2  cmp     [rsp+160h+nNumber], 0FFFFFFFFh
0x1800149b7  jz      loc_180014C66
0x1800149bd  mov     rax, [r14]
0x1800149c0  mov     rcx, r14
0x1800149c3  mov     rax, [rax+80h]
0x1800149ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149cf  test    eax, eax
0x1800149d1  jz      loc_180015194
0x1800149d7  mov     ecx, [rsp+160h+nNumber]; nNumber
0x1800149db  xorps   xmm0, xmm0
0x1800149de  mov     [rsi+20h], ecx
0x1800149e1  xor     eax, eax
0x1800149e3  xor     r14d, r14d
0x1800149e6  mov     [rbp+60h+var_80], eax
0x1800149e9  mov     rax, r13
0x1800149ec  mov     [rsp+160h+var_100], r14d
0x1800149f1  movups  [rbp+60h+var_D0], xmm0
0x1800149f5  movups  [rbp+60h+var_C0], xmm0
0x1800149f9  movups  [rbp+60h+var_B0], xmm0
0x1800149fd  movups  [rbp+60h+var_A0], xmm0
0x180014a01  movups  [rbp+60h+var_90], xmm0
0x180014a05  test    byte ptr [rbx+0A2h], 2
0x180014a0c  cmovnz  rax, r12
0x180014a10  mov     r8d, [rax]; nDenominator
0x180014a13  cmp     r8d, 5A0h
0x180014a1a  jz      short loc_180014A2D
0x180014a1c  test    r8d, r8d
0x180014a1f  jz      loc_180014E8E
0x180014a25  test    ecx, ecx
0x180014a27  jnz     loc_180014E8E
0x180014a2d  mov     edx, [rsp+160h+var_104]
0x180014a31  lea     rax, [rbp+60h+var_D0]
0x180014a35  mov     [rsp+160h+var_118], r15
0x180014a3a  mov     r8d, ecx
0x180014a3d  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x180014a44  xor     r9d, r9d
0x180014a47  mov     [rsp+160h+var_120], rax
0x180014a4c  lea     rax, [rsp+160h+var_100]
0x180014a51  mov     [rsp+160h+var_128], rax
0x180014a56  lea     rax, [rbp+60h+var_70]
0x180014a5a  mov     [rsp+160h+var_130], rax
0x180014a5f  mov     dword ptr [rsp+160h+var_138], 3
0x180014a67  mov     dword ptr [rsp+160h+var_140], r14d
0x180014a6c  call    cs:__imp_LsCreateLine
0x180014a73  nop     dword ptr [rax+rax+00h]
0x180014a78  cmp     dword ptr [rsi+24h], 0
0x180014a7c  mov     r14d, eax
0x180014a7f  jnz     loc_1800151CB
0x180014a85  mov     ecx, dword ptr [rbp+60h+var_C0+8]
0x180014a88  cmp     dword ptr [rbp+60h+var_D0], ecx
0x180014a8b  cmovg   ecx, dword ptr [rbp+60h+var_D0]
0x180014a8f  mov     dword ptr [rbp+60h+var_D0], ecx
0x180014a92  mov     ecx, dword ptr [rbp+60h+var_B0]
0x180014a95  cmp     dword ptr [rbp+60h+var_D0+8], ecx
0x180014a98  cmovg   ecx, dword ptr [rbp+60h+var_D0+8]
0x180014a9c  mov     dword ptr [rbp+60h+var_D0+8], ecx
0x180014a9f  movzx   ecx, byte ptr [rbx+0A2h]
0x180014aa6  test    cl, 2
0x180014aa9  jnz     loc_180014C49
0x180014aaf  mov     eax, [rsi+30h]
0x180014ab2  test    eax, eax
0x180014ab4  jnz     loc_180014EA6
0x180014aba  mov     eax, dword ptr [rbp+60h+var_B0+8]
0x180014abd  mov     dword ptr [rbp+60h+var_B0+8], eax
0x180014ac0  test    r14d, r14d
0x180014ac3  jnz     loc_1800152C9
0x180014ac9  test    byte ptr [rbx+0A2h], 1
0x180014ad0  jnz     loc_180014E28
0x180014ad6  sub     eax, [rsp+160h+var_104]
0x180014ada  lea     r9, [rsp+160h+var_10C]
0x180014adf  mov     [rbx+50h], eax
0x180014ae2  lea     r8, [rsp+160h+var_108]
0x180014ae7  mov     rcx, [r15]
0x180014aea  lea     rax, [rsp+160h+var_F8]
0x180014aef  xor     r14d, r14d
0x180014af2  mov     [rsp+160h+var_138], rax
0x180014af7  lea     rax, [rsp+160h+nNumber]
0x180014afc  mov     [rsp+160h+var_108], r14d
0x180014b01  lea     rdx, [rsp+160h+var_108]
0x180014b06  mov     [rsp+160h+var_140], rax
0x180014b0b  mov     [rsp+160h+var_10C], r14d
0x180014b10  mov     [rsp+160h+nNumber], r14d
0x180014b15  mov     dword ptr [rsp+160h+var_F8], r14d
0x180014b1a  call    cs:__imp_LsQueryLineDup
0x180014b21  nop     dword ptr [rax+rax+00h]
0x180014b26  test    eax, eax
0x180014b28  jnz     loc_1800152D9
0x180014b2e  mov     eax, [rsp+160h+nNumber]
0x180014b32  mov     ecx, [rsp+160h+var_10C]
0x180014b36  sub     eax, ecx
0x180014b38  mov     [rbx+58h], eax
0x180014b3b  mov     rax, [rbx+28h]
0x180014b3f  mov     [rbx+54h], ecx
0x180014b42  test    byte ptr [rax+0B4h], 1
0x180014b49  jz      loc_180014ED0
0x180014b4f  movzx   eax, word ptr [rbp+60h+var_D0]
0x180014b53  add     ax, word ptr [rbp+60h+var_D0+8]
0x180014b57  mov     [rbx+5Ch], ax
0x180014b5b  movzx   eax, word ptr [rbp+60h+var_D0+8]
0x180014b5f  mov     [rbx+5Eh], ax
0x180014b63  mov     esi, [rbx+20h]
0x180014b66  mov     [rbx+64h], r14b
0x180014b6a  mov     r11d, dword ptr [rbp+60h+var_B0+8]
0x180014b6e  sub     r11d, esi
0x180014b71  jz      loc_180014DF2
0x180014b77  mov     r9, [rbx+10h]
0x180014b7b  test    r9, r9
0x180014b7e  jz      loc_180014DF2
0x180014b84  mov     r8d, [r9+8]
0x180014b88  test    r8d, r8d
0x180014b8b  jz      loc_180014DF2
0x180014b91  mov     eax, esi
0x180014b93  lea     ecx, [r11+rsi]
0x180014b97  cdq
0x180014b98  sub     eax, edx
0x180014b9a  sar     eax, 1
0x180014b9c  cmp     ecx, eax
0x180014b9e  jl      loc_18001507D
0x180014ba4  mov     ecx, r11d
0x180014ba7  test    r11d, r11d
0x180014baa  js      loc_180014FC0
0x180014bb0  mov     r10d, [rbx+18h]
0x180014bb4  test    r8d, r8d
0x180014bb7  jle     loc_1800150C1
0x180014bbd  cmp     r10d, r8d
0x180014bc0  jge     loc_1800150C1
0x180014bc6  mov     rdx, [r9]
0x180014bc9  test    rdx, rdx
0x180014bcc  jz      loc_1800150C1
0x180014bd2  test    r10d, r10d
0x180014bd5  js      loc_1800150C1
0x180014bdb  mov     eax, r10d
0x180014bde  imul    eax, [r9+10h]
0x180014be3  movsxd  r8, eax
0x180014be6  add     r8, rdx
0x180014be9  nop     dword ptr [rax+00000000h]
0x180014bf0  test    ecx, ecx
0x180014bf2  jle     loc_180014CBD
0x180014bf8  mov     eax, [r8]
0x180014bfb  add     [rbx+1Ch], ecx
0x180014bfe  mov     ecx, [rbx+1Ch]
0x180014c01  cmp     ecx, eax
0x180014c03  jl      loc_180014CBA
0x180014c09  lea     edx, [r10+1]
0x180014c0d  sub     ecx, eax
0x180014c0f  mov     [rbx+18h], edx
0x180014c12  cmp     edx, [r9+8]
0x180014c16  jge     loc_180014E82
0x180014c1c  mov     [rbx+1Ch], r14d
0x180014c20  mov     r10d, edx
0x180014c23  movsxd  rax, dword ptr [r9+10h]
0x180014c27  add     r8, rax
0x180014c2a  jmp     short loc_180014BF0
0x180014c2c  mov     eax, [rbx+70h]
0x180014c2f  cmp     [rbx+80h], eax
0x180014c35  jnz     loc_180015159
0x180014c3b  and     cl, 0FDh
0x180014c3e  mov     [rbx+0A2h], cl
0x180014c44  jmp     loc_180014962
0x180014c49  mov     eax, [rbx+70h]
0x180014c4c  cmp     [rbx+80h], eax
0x180014c52  jnz     loc_1800152A6
0x180014c58  and     cl, 0FDh
0x180014c5b  mov     [rbx+0A2h], cl
0x180014c61  jmp     loc_180014AAF
0x180014c66  mov     rax, [r14]
0x180014c69  mov     rcx, r14
0x180014c6c  mov     rax, [rax+88h]
0x180014c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c78  mov     rdx, [r14]
0x180014c7b  mov     rcx, r14
0x180014c7e  test    eax, eax
0x180014c80  jnz     loc_180015175
0x180014c86  mov     rax, [rdx+98h]
0x180014c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c92  xor     ecx, ecx
0x180014c94  sub     eax, 1
0x180014c97  cmovns  ecx, eax
0x180014c9a  mov     [rsp+160h+nNumber], ecx
0x180014c9e  jmp     loc_1800149BD
0x180014ca3  cmp     edx, r8d
0x180014ca6  jnz     loc_180014992
0x180014cac  mov     r8d, 1
0x180014cb2  jmp     loc_180014995
0x180014cb7  mov     [rbx+1Ch], edx
0x180014cba  mov     ecx, r14d
0x180014cbd  sub     r11d, ecx
0x180014cc0  lea     ecx, [rsi+r11]
0x180014cc4  mov     [rbx+20h], ecx
0x180014cc7  sub     ecx, esi
0x180014cc9  jz      loc_180014D65
0x180014ccf  mov     r10, [rbx+30h]
0x180014cd3  test    r10, r10
0x180014cd6  jz      loc_180014E63
0x180014cdc  mov     eax, [r10+8]
0x180014ce0  test    eax, eax
0x180014ce2  jz      loc_180014E63
0x180014ce8  mov     edx, ecx
0x180014cea  test    ecx, ecx
0x180014cec  js      loc_180014EDD
0x180014cf2  mov     r11d, [rbx+38h]
0x180014cf6  test    eax, eax
0x180014cf8  jle     loc_1800150C9
0x180014cfe  cmp     r11d, eax
0x180014d01  jge     loc_1800150C9
0x180014d07  mov     r8, [r10]
0x180014d0a  test    r8, r8
0x180014d0d  jz      loc_1800150C9
0x180014d13  test    r11d, r11d
0x180014d16  js      loc_1800150C9
0x180014d1c  mov     eax, r11d
0x180014d1f  imul    eax, [r10+10h]
0x180014d24  movsxd  r9, eax
0x180014d27  add     r9, r8
0x180014d2a  mov     esi, ecx
  ... truncated ...
```
