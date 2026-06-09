# COls::MeasureLine(long,CLine *)

- ea: `0x180015a10`
- end: `0x1800165b8`
- name: `?MeasureLine@COls@@QEAAHJPEAVCLine@@@Z`
- size: `2984`
- prototype: `__int64 __fastcall(COls *__hidden this, int, struct CLine *)`
- caller_count: `5`
- callee_count: `19`
- tags: ``

## callers

- `0x18000ea70`
- `0x1800167f0`
- `0x18001e564`
- `0x180041874`
- `0x180048fe4`

## callees

- `0x1800064d0`
- `0x180015750`
- `0x180015a10`
- `0x1800165c0`
- `0x18001d87c`
- `0x18001d8b0`
- `0x18001db20`
- `0x180025fd0`
- `0x180026590`
- `0x1800391f0`
- `0x180039ecc`
- `0x180039f20`
- `0x18003a61c`
- `0x18003d764`
- `0x18003e054`
- `0x180042d30`
- `0x1800455c4`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18001601f`
- `KERNEL32!MulDiv` at `0x18001601f`
- `KERNEL32!EnterCriticalSection` at `0x180015a69`
- `KERNEL32!EnterCriticalSection` at `0x180015a69`
- `KERNEL32!LeaveCriticalSection` at `0x180015ae3`
- `KERNEL32!LeaveCriticalSection` at `0x180015ae3`
- `msls31!__imp_LsCreateLine` at `0x180015c14`
- `msls31!__imp_LsCreateLine` at `0x180016411`
- `msls31!__imp_LsCreateLine` at `0x180015c14`
- `msls31!__imp_LsCreateLine` at `0x180016411`
- `msls31!__imp_LsDestroyLine` at `0x180015a86`
- `msls31!__imp_LsDestroyLine` at `0x180015a86`
- `msls31!__imp_LsQueryLineDup` at `0x180015cbc`
- `msls31!__imp_LsQueryLineDup` at `0x180016380`
- `msls31!__imp_LsQueryLineDup` at `0x180015cbc`
- `msls31!__imp_LsQueryLineDup` at `0x180016380`
- `msls31!__imp_LsSetDoc` at `0x180015b54`
- `msls31!__imp_LsSetDoc` at `0x180015b54`

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
0x180015a10  mov     [rsp-8+arg_18], rbx
0x180015a15  push    rbp
0x180015a16  push    rsi
0x180015a17  push    rdi
0x180015a18  push    r12
0x180015a1a  push    r13
0x180015a1c  push    r14
0x180015a1e  push    r15
0x180015a20  lea     rbp, [rsp-30h]
0x180015a25  sub     rsp, 130h
0x180015a2c  mov     rax, cs:__security_cookie
0x180015a33  xor     rax, rsp
0x180015a36  mov     [rbp+60h+var_58], rax
0x180015a3a  mov     rbx, [rcx]
0x180015a3d  mov     rsi, rcx
0x180015a40  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015a47  mov     [rsp+160h+var_F0], r8
0x180015a4c  mov     [rsp+160h+nNumber], edx
0x180015a50  mov     rax, [rbx+90h]
0x180015a57  mov     r12d, [rbx+20h]
0x180015a5b  mov     r14, [rbx+78h]
0x180015a5f  mov     [rsp+160h+var_F8], rax
0x180015a64  mov     [rsp+160h+var_104], r12d
0x180015a69  call    cs:__imp_EnterCriticalSection
0x180015a6f  mov     rdx, [rsi+8]
0x180015a73  lea     r15, [rsi+8]
0x180015a77  xor     r13d, r13d
0x180015a7a  test    rdx, rdx
0x180015a7d  jz      short loc_180015A8F
0x180015a7f  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x180015a86  call    cs:__imp_LsDestroyLine
0x180015a8c  mov     [r15], r13
0x180015a8f  cmp     [rsi+30h], r13d
0x180015a93  jnz     loc_1800162CB
0x180015a99  mov     r9d, [rsi+48h]
0x180015a9d  mov     ecx, r13d
0x180015aa0  test    r9d, r9d
0x180015aa3  jle     short loc_180015ADC
0x180015aa5  mov     eax, [rsi+48h]
0x180015aa8  test    eax, eax
0x180015aaa  jle     loc_18001621E
0x180015ab0  cmp     ecx, eax
0x180015ab2  jge     loc_18001621E
0x180015ab8  mov     r8, [rsi+40h]
0x180015abc  test    r8, r8
0x180015abf  jz      loc_18001621E
0x180015ac5  mov     eax, ecx
0x180015ac7  imul    eax, [rsi+50h]
0x180015acb  movsxd  rdx, eax
0x180015ace  add     rdx, r8
0x180015ad1  inc     ecx
0x180015ad3  mov     [rdx+8], r13d
0x180015ad7  cmp     ecx, r9d
0x180015ada  jl      short loc_180015AA5
0x180015adc  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015ae3  call    cs:__imp_LeaveCriticalSection
0x180015ae9  mov     [rsi+10h], r12d
0x180015aed  lea     r12, [rbx+74h]
0x180015af1  mov     [rsi+24h], r13d
0x180015af5  lea     r13, [rbx+84h]
0x180015afc  mov     [rsi+18h], r14
0x180015b00  movzx   ecx, byte ptr [rbx+0A2h]
0x180015b07  test    cl, 2
0x180015b0a  jnz     loc_180015DC1
0x180015b10  xorps   xmm0, xmm0
0x180015b13  movups  [rsp+160h+var_E8], xmm0
0x180015b18  mov     ecx, [rbx+70h]
0x180015b1b  mov     dword ptr [rbp+60h+var_E8+0Ch], ecx
0x180015b1e  mov     edx, [r12]
0x180015b22  mov     dword ptr [rbp+60h+var_E8+8], edx
0x180015b25  mov     eax, [rbx+80h]
0x180015b2b  mov     dword ptr [rsp+160h+var_E8+4], eax
0x180015b2f  mov     r8d, [r13+0]
0x180015b33  mov     dword ptr [rsp+160h+var_E8], r8d
0x180015b38  cmp     ecx, eax
0x180015b3a  jz      loc_180015E38
0x180015b40  xor     r8d, r8d
0x180015b43  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x180015b4a  lea     r9, [rsp+160h+var_E8]
0x180015b4f  mov     edx, 1
0x180015b54  call    cs:__imp_LsSetDoc
0x180015b5a  cmp     [rsp+160h+nNumber], 0FFFFFFFFh
0x180015b5f  jz      loc_180015DFB
0x180015b65  mov     rax, [r14]
0x180015b68  mov     rcx, r14
0x180015b6b  mov     rax, [rax+80h]
0x180015b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b77  test    eax, eax
0x180015b79  jz      loc_180016319
0x180015b7f  mov     ecx, [rsp+160h+nNumber]; nNumber
0x180015b83  xorps   xmm0, xmm0
0x180015b86  mov     [rsi+20h], ecx
0x180015b89  xor     eax, eax
0x180015b8b  xor     r14d, r14d
0x180015b8e  mov     [rbp+60h+var_80], eax
0x180015b91  mov     rax, r13
0x180015b94  mov     [rsp+160h+var_100], r14d
0x180015b99  movups  [rbp+60h+var_D0], xmm0
0x180015b9d  movups  [rbp+60h+var_C0], xmm0
0x180015ba1  movups  [rbp+60h+var_B0], xmm0
0x180015ba5  movups  [rbp+60h+var_A0], xmm0
0x180015ba9  movups  [rbp+60h+var_90], xmm0
0x180015bad  test    byte ptr [rbx+0A2h], 2
0x180015bb4  cmovnz  rax, r12
0x180015bb8  mov     r8d, [rax]; nDenominator
0x180015bbb  cmp     r8d, 5A0h
0x180015bc2  jz      short loc_180015BD5
0x180015bc4  test    r8d, r8d
0x180015bc7  jz      loc_18001601A
0x180015bcd  test    ecx, ecx
0x180015bcf  jnz     loc_18001601A
0x180015bd5  mov     edx, [rsp+160h+var_104]
0x180015bd9  lea     rax, [rbp+60h+var_D0]
0x180015bdd  mov     [rsp+160h+var_118], r15
0x180015be2  mov     r8d, ecx
0x180015be5  mov     rcx, cs:?g_plsc@@3PEAUCLineServices@@EA; CLineServices * g_plsc
0x180015bec  xor     r9d, r9d
0x180015bef  mov     [rsp+160h+var_120], rax
0x180015bf4  lea     rax, [rsp+160h+var_100]
0x180015bf9  mov     [rsp+160h+var_128], rax
0x180015bfe  lea     rax, [rbp+60h+var_70]
0x180015c02  mov     [rsp+160h+var_130], rax
0x180015c07  mov     dword ptr [rsp+160h+var_138], 3
0x180015c0f  mov     dword ptr [rsp+160h+var_140], r14d
0x180015c14  call    cs:__imp_LsCreateLine
0x180015c1a  cmp     dword ptr [rsi+24h], 0
0x180015c1e  mov     r14d, eax
0x180015c21  jnz     loc_180016350
0x180015c27  mov     ecx, dword ptr [rbp+60h+var_C0+8]
0x180015c2a  cmp     dword ptr [rbp+60h+var_D0], ecx
0x180015c2d  cmovg   ecx, dword ptr [rbp+60h+var_D0]
0x180015c31  mov     dword ptr [rbp+60h+var_D0], ecx
0x180015c34  mov     ecx, dword ptr [rbp+60h+var_B0]
0x180015c37  cmp     dword ptr [rbp+60h+var_D0+8], ecx
0x180015c3a  cmovg   ecx, dword ptr [rbp+60h+var_D0+8]
0x180015c3e  mov     dword ptr [rbp+60h+var_D0+8], ecx
0x180015c41  movzx   ecx, byte ptr [rbx+0A2h]
0x180015c48  test    cl, 2
0x180015c4b  jnz     loc_180015DDE
0x180015c51  mov     eax, [rsi+30h]
0x180015c54  test    eax, eax
0x180015c56  jnz     loc_18001602C
0x180015c5c  mov     eax, dword ptr [rbp+60h+var_B0+8]
0x180015c5f  mov     dword ptr [rbp+60h+var_B0+8], eax
0x180015c62  test    r14d, r14d
0x180015c65  jnz     loc_180016442
0x180015c6b  test    byte ptr [rbx+0A2h], 1
0x180015c72  jnz     loc_180015FB8
0x180015c78  sub     eax, [rsp+160h+var_104]
0x180015c7c  lea     r9, [rsp+160h+var_10C]
0x180015c81  mov     [rbx+50h], eax
0x180015c84  lea     r8, [rsp+160h+var_108]
0x180015c89  mov     rcx, [r15]
0x180015c8c  lea     rax, [rsp+160h+var_F8]
0x180015c91  xor     r14d, r14d
0x180015c94  mov     [rsp+160h+var_138], rax
0x180015c99  lea     rax, [rsp+160h+nNumber]
0x180015c9e  mov     [rsp+160h+var_108], r14d
0x180015ca3  lea     rdx, [rsp+160h+var_108]
0x180015ca8  mov     [rsp+160h+var_140], rax
0x180015cad  mov     [rsp+160h+var_10C], r14d
0x180015cb2  mov     [rsp+160h+nNumber], r14d
0x180015cb7  mov     dword ptr [rsp+160h+var_F8], r14d
0x180015cbc  call    cs:__imp_LsQueryLineDup
0x180015cc2  test    eax, eax
0x180015cc4  jnz     loc_180016452
0x180015cca  mov     eax, [rsp+160h+nNumber]
0x180015cce  mov     ecx, [rsp+160h+var_10C]
0x180015cd2  sub     eax, ecx
0x180015cd4  mov     [rbx+58h], eax
0x180015cd7  mov     rax, [rbx+28h]
0x180015cdb  mov     [rbx+54h], ecx
0x180015cde  test    byte ptr [rax+0B4h], 1
0x180015ce5  jz      loc_180016056
0x180015ceb  movzx   eax, word ptr [rbp+60h+var_D0]
0x180015cef  add     ax, word ptr [rbp+60h+var_D0+8]
0x180015cf3  mov     [rbx+5Ch], ax
0x180015cf7  movzx   eax, word ptr [rbp+60h+var_D0+8]
0x180015cfb  mov     [rbx+5Eh], ax
0x180015cff  mov     esi, [rbx+20h]
0x180015d02  mov     [rbx+64h], r14b
0x180015d06  mov     r11d, dword ptr [rbp+60h+var_B0+8]
0x180015d0a  sub     r11d, esi
0x180015d0d  jz      loc_180015F82
0x180015d13  mov     r9, [rbx+10h]
0x180015d17  test    r9, r9
0x180015d1a  jz      loc_180015F82
0x180015d20  mov     r8d, [r9+8]
0x180015d24  test    r8d, r8d
0x180015d27  jz      loc_180015F82
0x180015d2d  mov     eax, esi
0x180015d2f  lea     ecx, [r11+rsi]
0x180015d33  cdq
0x180015d34  sub     eax, edx
0x180015d36  sar     eax, 1
0x180015d38  cmp     ecx, eax
0x180015d3a  jl      loc_180016202
0x180015d40  mov     ecx, r11d
0x180015d43  test    r11d, r11d
0x180015d46  js      loc_180016145
0x180015d4c  mov     r10d, [rbx+18h]
0x180015d50  test    r8d, r8d
0x180015d53  jle     loc_180016246
0x180015d59  cmp     r10d, r8d
0x180015d5c  jge     loc_180016246
0x180015d62  mov     rdx, [r9]
0x180015d65  test    rdx, rdx
0x180015d68  jz      loc_180016246
0x180015d6e  test    r10d, r10d
0x180015d71  js      loc_180016246
0x180015d77  mov     eax, r10d
0x180015d7a  imul    eax, [r9+10h]
0x180015d7f  movsxd  r8, eax
0x180015d82  add     r8, rdx
0x180015d85  test    ecx, ecx
0x180015d87  jle     loc_180015E52
0x180015d8d  mov     eax, [r8]
0x180015d90  add     [rbx+1Ch], ecx
0x180015d93  mov     ecx, [rbx+1Ch]
0x180015d96  cmp     ecx, eax
0x180015d98  jl      loc_180015E4F
0x180015d9e  lea     edx, [r10+1]
0x180015da2  sub     ecx, eax
0x180015da4  mov     [rbx+18h], edx
0x180015da7  cmp     edx, [r9+8]
0x180015dab  jge     loc_18001600E
0x180015db1  mov     [rbx+1Ch], r14d
0x180015db5  mov     r10d, edx
0x180015db8  movsxd  rax, dword ptr [r9+10h]
0x180015dbc  add     r8, rax
0x180015dbf  jmp     short loc_180015D85
0x180015dc1  mov     eax, [rbx+70h]
0x180015dc4  cmp     [rbx+80h], eax
0x180015dca  jnz     loc_1800162DE
0x180015dd0  and     cl, 0FDh
0x180015dd3  mov     [rbx+0A2h], cl
0x180015dd9  jmp     loc_180015B10
0x180015dde  mov     eax, [rbx+70h]
0x180015de1  cmp     [rbx+80h], eax
0x180015de7  jnz     loc_18001641F
0x180015ded  and     cl, 0FDh
0x180015df0  mov     [rbx+0A2h], cl
0x180015df6  jmp     loc_180015C51
0x180015dfb  mov     rax, [r14]
0x180015dfe  mov     rcx, r14
0x180015e01  mov     rax, [rax+88h]
0x180015e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e0d  mov     rdx, [r14]
0x180015e10  mov     rcx, r14
0x180015e13  test    eax, eax
0x180015e15  jnz     loc_1800162FA
0x180015e1b  mov     rax, [rdx+98h]
0x180015e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e27  xor     ecx, ecx
0x180015e29  sub     eax, 1
0x180015e2c  cmovns  ecx, eax
0x180015e2f  mov     [rsp+160h+nNumber], ecx
0x180015e33  jmp     loc_180015B65
0x180015e38  cmp     edx, r8d
0x180015e3b  jnz     loc_180015B40
0x180015e41  mov     r8d, 1
0x180015e47  jmp     loc_180015B43
0x180015e4c  mov     [rbx+1Ch], edx
0x180015e4f  mov     ecx, r14d
0x180015e52  sub     r11d, ecx
0x180015e55  lea     ecx, [rsi+r11]
0x180015e59  mov     [rbx+20h], ecx
0x180015e5c  sub     ecx, esi
0x180015e5e  jz      loc_180015EF6
0x180015e64  mov     r10, [rbx+30h]
0x180015e68  test    r10, r10
0x180015e6b  jz      loc_180015FF2
0x180015e71  mov     eax, [r10+8]
0x180015e75  test    eax, eax
0x180015e77  jz      loc_180015FF2
0x180015e7d  mov     edx, ecx
0x180015e7f  test    ecx, ecx
0x180015e81  js      loc_180016063
0x180015e87  mov     r11d, [rbx+38h]
0x180015e8b  test    eax, eax
0x180015e8d  jle     loc_18001624E
0x180015e93  cmp     r11d, eax
0x180015e96  jge     loc_18001624E
0x180015e9c  mov     r8, [r10]
0x180015e9f  test    r8, r8
0x180015ea2  jz      loc_18001624E
0x180015ea8  test    r11d, r11d
0x180015eab  js      loc_18001624E
0x180015eb1  mov     eax, r11d
0x180015eb4  imul    eax, [r10+10h]
0x180015eb9  movsxd  r9, eax
0x180015ebc  add     r9, r8
0x180015ebf  mov     esi, ecx
0x180015ec1  test    edx, edx
0x180015ec3  jle     short loc_180015EF8
0x180015ec5  mov     eax, [r9]
0x180015ec8  add     [rbx+3Ch], edx
0x180015ecb  mov     edx, [rbx+3Ch]
0x180015ece  cmp     edx, eax
0x180015ed0  jl      short loc_180015F02
  ... truncated ...
```
