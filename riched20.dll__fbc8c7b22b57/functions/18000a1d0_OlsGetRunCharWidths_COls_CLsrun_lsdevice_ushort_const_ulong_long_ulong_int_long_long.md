# OlsGetRunCharWidths(COls *,CLsrun *,lsdevice,ushort const *,ulong,long,ulong,int *,long *,long *)

- ea: `0x18000a1d0`
- end: `0x18000b071`
- name: `?OlsGetRunCharWidths@@YAJPEAUCOls@@PEAUCLsrun@@W4lsdevice@@PEBGKJKPEAHPEAJ5@Z`
- size: `3745`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180006570`
- `0x180008fec`
- `0x18000a1d0`
- `0x18000b0e8`
- `0x18000b5e0`
- `0x1800260d0`
- `0x18002e7e4`
- `0x18003c080`
- `0x1800486b0`
- `0x1800708e0`
- `0x180090024`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18000aac2`
- `KERNEL32!MulDiv` at `0x18000aac2`
- `KERNEL32!WideCharToMultiByte` at `0x18000ae13`
- `KERNEL32!WideCharToMultiByte` at `0x18000ae13`
- `USP10!ScriptGetProperties` at `0x18000afaa`
- `USP10!ScriptGetProperties` at `0x18000afaa`
- `GDI32!GetDeviceCaps` at `0x18000afeb`
- `GDI32!GetDeviceCaps` at `0x18000afeb`
- `GDI32!DeleteObject` at `0x18000a8b7`
- `GDI32!DeleteObject` at `0x18000a8b7`
- `GDI32!GetStockObject` at `0x18000ae6c`
- `GDI32!GetStockObject` at `0x18000ae6c`
- `GDI32!SelectObject` at `0x18000a71c`
- `GDI32!SelectObject` at `0x18000a7d2`
- `GDI32!SelectObject` at `0x18000a8a7`
- `GDI32!SelectObject` at `0x18000ae80`
- `GDI32!SelectObject` at `0x18000aedb`
- `GDI32!SelectObject` at `0x18000a71c`
- `GDI32!SelectObject` at `0x18000a7d2`
- `GDI32!SelectObject` at `0x18000a8a7`
- `GDI32!SelectObject` at `0x18000ae80`
- `GDI32!SelectObject` at `0x18000aedb`
- `GDI32!GetCharWidthW` at `0x18000a87a`
- `GDI32!GetCharWidthW` at `0x18000adb1`
- `GDI32!GetCharWidthW` at `0x18000a87a`
- `GDI32!GetCharWidthW` at `0x18000adb1`
- `GDI32!GetCharWidthA` at `0x18000a794`
- `GDI32!GetCharWidthA` at `0x18000ae41`
- `GDI32!GetCharWidthA` at `0x18000a794`
- `GDI32!GetCharWidthA` at `0x18000ae41`

## pseudocode

```c
__int64 __fastcall OlsGetRunCharWidths(
        __int64 *a1,
        int *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        int *a8,
        _DWORD *a9,
        unsigned int *a10)
{
  __int64 v10; // rbx
  int *v13; // r13
  int v15; // ecx
  int v16; // esi
  int v17; // r11d
  __int64 v18; // r8
  int v19; // r9d
  int v20; // ecx
  int v21; // r10d
  int *v22; // r9
  int v23; // eax
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // r9
  int v28; // eax
  int v29; // edx
  int v30; // r11d
  int *v31; // r10
  int v32; // esi
  int v33; // eax
  int v34; // edx
  __int64 v35; // r8
  int v36; // eax
  int v37; // r10d
  int *v38; // r9
  int v39; // eax
  int v40; // ecx
  unsigned __int8 v41; // dl
  int v42; // r8d
  BOOL v43; // ecx
  __int64 v44; // rcx
  int v45; // edx
  int v46; // eax
  __int64 v47; // rdx
  __int16 v48; // dx
  HDC v49; // rdi
  __int64 v50; // r8
  __int16 v51; // r9
  __int64 v52; // rcx
  int v53; // edx
  int v54; // eax
  __int64 v55; // rcx
  __int16 v56; // ax
  struct CCcs *CcsBullet; // r14
  __int64 v58; // rax
  int v59; // esi
  unsigned int v60; // edi
  bool v61; // zf
  int *v62; // rdx
  int v63; // ecx
  int v64; // edx
  unsigned __int64 v65; // rbx
  CWidthCache *v66; // rdx
  _WORD *v67; // r8
  BOOL v68; // r14d
  UINT v69; // r13d
  int v70; // edx
  __int16 *v71; // rax
  struct CCcs *v72; // r14
  __int16 v73; // cx
  HDC v74; // r10
  __int64 v75; // rax
  __int64 v76; // rcx
  _WORD *v77; // r14
  WCHAR v78; // cx
  HDC v80; // r13
  __int16 v81; // r9
  __int64 v82; // rcx
  int v83; // edx
  int v84; // eax
  __int64 v85; // r9
  __int16 v86; // ax
  char v87; // dl
  HDC v88; // r9
  __int64 v89; // rax
  BOOL v90; // eax
  int *v91; // r8
  struct CCcs *Ccs; // rax
  void *v93; // rax
  int v94; // r8d
  int v95; // eax
  int v96; // eax
  int v97; // r8d
  _DWORD *v98; // rax
  int v99; // edx
  int v100; // eax
  int v101; // eax
  int v102; // edx
  _DWORD *v103; // rax
  int v104; // eax
  int v105; // edx
  int v106; // eax
  int v107; // eax
  int v108; // edx
  _DWORD *v109; // rax
  __int64 v110; // rax
  struct CUniscribe *Uniscribe; // rax
  __int16 v112; // r13
  void *v113; // rcx
  __int64 *v114; // rax
  unsigned __int16 v115; // r13
  __int64 *v116; // rcx
  __int64 v117; // rax
  int v118; // edx
  int v119; // eax
  unsigned __int16 v120; // cx
  HGDIOBJ StockObject; // rax
  __int16 v122; // ax
  __int16 v123; // ax
  __int64 v124; // r9
  __int64 v125; // rcx
  int cbMultiByte; // [rsp+28h] [rbp-D8h]
  WCHAR WideCharStr; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  HDC hdc; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 MultiByteStr[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v131; // [rsp+5Ch] [rbp-A4h]
  HGDIOBJ v132; // [rsp+60h] [rbp-A0h]
  BOOL v133; // [rsp+68h] [rbp-98h]
  int v134; // [rsp+6Ch] [rbp-94h]
  int v135; // [rsp+70h] [rbp-90h]
  struct CCcs *v136; // [rsp+78h] [rbp-88h]
  HGDIOBJ ho; // [rsp+80h] [rbp-80h]
  BOOL UsedDefaultChar; // [rsp+88h] [rbp-78h] BYREF
  HGDIOBJ h; // [rsp+90h] [rbp-70h]
  unsigned int *v140; // [rsp+98h] [rbp-68h]
  _DWORD *v141; // [rsp+A0h] [rbp-60h]
  struct tagLOGFONTW v142; // [rsp+B0h] [rbp-50h] BYREF

  v10 = *a1;
  v13 = a2;
  v15 = *a2 & 0x7FFFFFFF;
  v16 = *(_DWORD *)(v10 + 32);
  v141 = a9;
  ho = a2;
  v140 = a10;
  v17 = v15 - v16;
  if ( v15 == v16 )
    goto LABEL_47;
  v18 = *(_QWORD *)(v10 + 16);
  if ( !v18 )
    goto LABEL_47;
  v19 = *(_DWORD *)(v18 + 8);
  if ( !v19 )
    goto LABEL_47;
  if ( v15 < v16 / 2 )
  {
    *(_QWORD *)(v10 + 24) = 0;
    v118 = 0;
    if ( v15 )
      v118 = v15;
    v25 = CRunPtrBase::AdvanceCp((CRunPtrBase *)(v10 + 16), v118);
  }
  else
  {
    v20 = v15 - v16;
    if ( v17 < 0 )
    {
      while ( v20 < 0 )
      {
        v104 = *(_DWORD *)(v10 + 28);
        v105 = v104 + v20;
        if ( -v20 <= v104 )
        {
          *(_DWORD *)(v10 + 28) = v105;
LABEL_16:
          v20 = 0;
          break;
        }
        v106 = *(_DWORD *)(v10 + 24);
        v20 = v105;
        if ( v106 <= 0 )
        {
          *(_QWORD *)(v10 + 24) = 0;
          break;
        }
        v107 = v106 - 1;
        *(_DWORD *)(v10 + 24) = v107;
        v108 = *(_DWORD *)(v18 + 8);
        if ( v108 > 0 && v107 < v108 && *(_QWORD *)v18 && v107 >= 0 )
          v109 = (_DWORD *)(*(_QWORD *)v18 + *(_DWORD *)(v18 + 16) * v107);
        else
          v109 = 0;
        *(_DWORD *)(v10 + 28) = *v109;
      }
    }
    else
    {
      v21 = *(_DWORD *)(v10 + 24);
      if ( v19 > 0 && v21 < v19 && *(_QWORD *)v18 && v21 >= 0 )
        v22 = (int *)(*(_QWORD *)v18 + *(_DWORD *)(v18 + 16) * v21);
      else
        v22 = 0;
      while ( v20 > 0 )
      {
        v23 = *v22;
        *(_DWORD *)(v10 + 28) += v20;
        v24 = *(_DWORD *)(v10 + 28);
        if ( v24 < v23 )
          goto LABEL_16;
        v20 = v24 - v23;
        *(_DWORD *)(v10 + 24) = v21 + 1;
        if ( v21 + 1 >= *(_DWORD *)(v18 + 8) )
        {
          *(_DWORD *)(v10 + 24) = v21;
          *(_DWORD *)(v10 + 28) = v23;
          break;
        }
        *(_DWORD *)(v10 + 28) = 0;
        ++v21;
        v22 = (int *)((char *)v22 + *(int *)(v18 + 16));
      }
    }
    v25 = v16 + v17 - v20;
  }
  *(_DWORD *)(v10 + 32) = v25;
  v26 = v25 - v16;
  if ( !v26 )
  {
    v32 = 0;
LABEL_33:
    if ( !v32 )
      goto LABEL_47;
    v26 = v32;
    goto LABEL_35;
  }
  v27 = *(_QWORD *)(v10 + 48);
  if ( v27 && (v28 = *(_DWORD *)(v27 + 8)) != 0 )
  {
    v29 = v26;
    if ( v26 >= 0 )
    {
      v30 = *(_DWORD *)(v10 + 56);
      if ( v28 > 0 && v30 < v28 && *(_QWORD *)v27 && v30 >= 0 )
        v31 = (int *)(*(_QWORD *)v27 + *(_DWORD *)(v27 + 16) * v30);
      else
        v31 = 0;
      v32 = v26;
      while ( v29 > 0 )
      {
        v33 = *v31;
        *(_DWORD *)(v10 + 60) += v29;
        v34 = *(_DWORD *)(v10 + 60);
        if ( v34 < v33 )
          goto LABEL_35;
        *(_DWORD *)(v10 + 56) = v30 + 1;
        if ( v30 + 1 >= *(_DWORD *)(v27 + 8) )
        {
          *(_DWORD *)(v10 + 56) = v30;
          *(_DWORD *)(v10 + 60) = v33;
          goto LABEL_35;
        }
        v29 = v34 - v33;
        *(_DWORD *)(v10 + 60) = 0;
        ++v30;
        v31 = (int *)((char *)v31 + *(int *)(v27 + 16));
      }
      goto LABEL_33;
    }
    v32 = v26;
    while ( v29 < 0 )
    {
      v94 = *(_DWORD *)(v10 + 60);
      if ( -v29 <= v94 )
      {
        *(_DWORD *)(v10 + 60) = v94 + v29;
        break;
      }
      v95 = *(_DWORD *)(v10 + 56);
      if ( v95 <= 0 )
      {
        *(_QWORD *)(v10 + 56) = 0;
        break;
      }
      v29 += v94;
      v96 = v95 - 1;
      *(_DWORD *)(v10 + 56) = v96;
      v97 = *(_DWORD *)(v27 + 8);
      if ( v97 > 0 && v96 < v97 && *(_QWORD *)v27 && v96 >= 0 )
        v98 = (_DWORD *)(*(_QWORD *)v27 + *(_DWORD *)(v27 + 16) * v96);
      else
        v98 = 0;
      *(_DWORD *)(v10 + 60) = *v98;
    }
  }
  else
  {
    v32 = v26;
  }
LABEL_35:
  v35 = *(_QWORD *)(v10 + 64);
  if ( v35 )
  {
    v36 = *(_DWORD *)(v35 + 8);
    if ( v36 )
    {
      if ( v32 < 0 )
      {
        while ( v26 < 0 )
        {
          v99 = *(_DWORD *)(v10 + 76);
          if ( -v26 <= v99 )
          {
            *(_DWORD *)(v10 + 76) = v99 + v26;
            break;
          }
          v100 = *(_DWORD *)(v10 + 72);
          if ( v100 <= 0 )
          {
            *(_QWORD *)(v10 + 72) = 0;
            break;
          }
          v26 += v99;
          v101 = v100 - 1;
          *(_DWORD *)(v10 + 72) = v101;
          v102 = *(_DWORD *)(v35 + 8);
          if ( v102 > 0 && v101 < v102 && *(_QWORD *)v35 && v101 >= 0 )
            v103 = (_DWORD *)(*(_QWORD *)v35 + *(_DWORD *)(v35 + 16) * v101);
          else
            v103 = 0;
          *(_DWORD *)(v10 + 76) = *v103;
        }
      }
      else
      {
        v37 = *(_DWORD *)(v10 + 72);
        if ( v36 > 0 && v37 < v36 && *(_QWORD *)v35 && v37 >= 0 )
          v38 = (int *)(*(_QWORD *)v35 + *(_DWORD *)(v35 + 16) * v37);
        else
          v38 = 0;
        while ( v26 > 0 )
        {
          v39 = *v38;
          *(_DWORD *)(v10 + 76) += v26;
          v40 = *(_DWORD *)(v10 + 76);
          if ( v40 < v39 )
            break;
          *(_DWORD *)(v10 + 72) = v37 + 1;
          if ( v37 + 1 >= *(_DWORD *)(v35 + 8) )
          {
            *(_DWORD *)(v10 + 72) = v37;
            *(_DWORD *)(v10 + 76) = v39;
            break;
          }
          v26 = v40 - v39;
          *(_DWORD *)(v10 + 76) = 0;
          ++v37;
          v38 = (int *)((char *)v38 + *(int *)(v35 + 16));
        }
      }
    }
  }
LABEL_47:
  v41 = *(_BYTE *)(v10 + 162);
  v42 = *v13;
  v43 = a3 == 1;
  if ( v43 != ((v41 >> 1) & 1) )
  {
    if ( *(_DWORD *)(v10 + 128) != *(_DWORD *)(v10 + 112) && *(_DWORD *)(v10 + 132) != *(_DWORD *)(v10 + 116) )
    {
      v124 = *(_QWORD *)(v10 + 136);
      if ( v124 )
      {
        v122 = *(_WORD *)(v124 + 10);
        if ( v122 )
        {
          *(_WORD *)(v124 + 10) = v122 - 1;
          v41 = *(_BYTE *)(v10 + 162);
        }
      }
      *(_QWORD *)(v10 + 136) = 0;
    }
    *(_BYTE *)(v10 + 162) = v41 & 0xFD | (2 * v43);
  }
  if ( v42 < 0 )
  {
    v125 = *(_QWORD *)(v10 + 136);
    if ( v125 )
    {
      v123 = *(_WORD *)(v125 + 10);
      if ( v123 )
        *(_WORD *)(v125 + 10) = v123 - 1;
    }
    CcsBullet = CMeasurer::GetCcsBullet((CMeasurer *)v10, 0);
    *(_QWORD *)(v10 + 136) = CcsBullet;
    *(_WORD *)(v10 + 158) = -10;
    goto LABEL_74;
  }
  v44 = *(_QWORD *)(v10 + 48);
  if ( v44 && (v45 = *(_DWORD *)(v44 + 8)) != 0 )
  {
    if ( v45 > 0 && (v46 = *(_DWORD *)(v10 + 56), v46 < v45) && *(_QWORD *)v44 && v46 >= 0 )
      v47 = *(_QWORD *)v44 + *(_DWORD *)(v44 + 16) * v46;
    else
      v47 = 0;
    v48 = *(_WORD *)(v47 + 4);
    hdc = 0;
    if ( v48 >= 0 )
      goto LABEL_58;
  }
  else
  {
    hdc = 0;
  }
  v48 = *(_WORD *)(*(_QWORD *)(v10 + 16) + 28LL);
LABEL_58:
  if ( (*(int (__fastcall **)(struct IFormatCache *, _QWORD, HDC *))(*(_QWORD *)qword_1800A72D0 + 32LL))(
         qword_1800A72D0,
         (unsigned int)v48,
         &hdc) >= 0 )
  {
    v49 = hdc;
  }
  else
  {
    v49 = (HDC)g_defaultCF;
    hdc = (HDC)g_defaultCF;
  }
  v50 = *(_QWORD *)(v10 + 136);
  v51 = -1;
  if ( !v50
    || ((v52 = *(_QWORD *)(v10 + 48)) == 0 || (v53 = *(_DWORD *)(v52 + 8)) == 0
      ? (v56 = -1)
      : (v53 <= 0 || (v54 = *(_DWORD *)(v10 + 56), v54 >= v53) || !*(_QWORD *)v52 || v54 < 0
       ? (v55 = 0)
       : (v55 = *(_QWORD *)v52 + *(_DWORD *)(v52 + 16) * v54),
         v56 = *(_WORD *)(v55 + 4)),
        *(_WORD *)(v10 + 158) != v56 || (*(_BYTE *)(v10 + 162) & 8) != 0) )
  {
    v82 = *(_QWORD *)(v10 + 48);
    if ( v82 )
    {
      v83 = *(_DWORD *)(v82 + 8);
      if ( v83 )
      {
        if ( v83 > 0 && (v84 = *(_DWORD *)(v10 + 56), v84 < v83) && *(_QWORD *)v82 && v84 >= 0 )
          v85 = *(_QWORD *)v82 + *(_DWORD *)(v82 + 16) * v84;
        else
          v85 = 0;
        v51 = *(_WORD *)(v85 + 4);
      }
    }
    *(_WORD *)(v10 + 158) = v51;
    if ( v50 )
    {
      v86 = *(_WORD *)(v50 + 10);
      if ( v86 )
        *(_WORD *)(v50 + 10) = v86 - 1;
    }
    v87 = *(_BYTE *)(v10 + 162);
    v88 = 0;
    if ( (v87 & 2) != 0 )
    {
      v89 = *(_QWORD *)(v10 + 104);
      if ( *(_QWORD *)(v89 + 8) && *(_BYTE *)(v10 + 160) == 2 )
        v88 = *(HDC *)(v89 + 8);
    }
    else
    {
      v110 = *(_QWORD *)(v10 + 120);
      if ( *(_QWORD *)(v110 + 24) && *(_BYTE *)(v10 + 161) == 2 )
        v88 = *(HDC *)(v110 + 24);
    }
    v90 = (v87 & 0x10) != 0 && *(_BYTE *)(v10 + 160) == 2;
    v91 = (int *)(v10 + 112);
    if ( (v87 & 2) == 0 )
      v91 = (int *)(v10 + 128);
    Ccs = CFontCache::GetCcs(qword_1800A6FC0, (const struct CCharFormat *const)v49, *v91, v88, v90);
    *(_BYTE *)(v10 + 162) &= ~8u;
    *(_QWORD *)(v10 + 136) = Ccs;
    if ( !Ccs )
      return 4294967294LL;
  }
  if ( *((_BYTE *)v49 + 32) == 4 )
    *(_BYTE *)(v10 + 101) |= 0x20u;
  CcsBullet = *(struct CCcs **)(v10 + 136);
  *(_WORD *)(v10 + 96) = *((_WORD *)CcsBullet + 49);
LABEL_74:
  v136 = CcsBullet;
  if ( CcsBullet )
  {
    v58 = *(_QWORD *)(v10 + 40);
    v59 = 0;
    v60 = 0;
    v133 = 0;
    if ( (*(_DWORD *)(v58 + 192) & 0x61086013) == 0 || (v13[6] & 0x3FF) == 0 || *v13 < 0 )
      goto LABEL_77;
    Uniscribe = GetUniscribe();
    v112 = *((_WORD *)v13 + 12);
    v113 = (char *)Uniscribe + 56;
    v114 = (__int64 *)*((_QWORD *)Uniscribe + 7);
    v132 = v113;
    if ( v114 || ScriptGetProperties((const SCRIPT_PROPERTIES ***)v113, 0) >= 0 && (v114 = *(__int64 **)v132) != 0 )
    {
      if ( v114 == &off_1800A6010 )
      {
        v116 = v114;
      }
      else
      {
        v115 = v112 & 0x3FF;
        v116 = v114;
        if ( v115 < (unsigned __int16)g_cMaxScript )
        {
LABEL_203:
          v117 = v115;
          v13 = (int *)ho;
          v133 = (*(_DWORD *)v116[v117] & 0x20000) != 0;
LABEL_77:
          v61 = (*(_BYTE *)(v10 + 162) & 2) == 0;
          v62 = (int *)(v10 + 116);
          v63 = *(__int16 *)(*((_QWORD *)v13 + 1) + 18LL);
          v135 = v63;
          if ( v61 )
            v62 = (int *)(v10 + 132);
          v64 = *v62;
          if ( v64 != 1440 && v63 )
            v135 = MulDiv(v63, v64, 1440);
          while ( 1 )
          {
            if ( v60 >= a5 )
            {
LABEL_112:
              *v140 = v60;
              *v141 = v59;
              return 0;
            }
            v65 = *a4;
            if ( !v133 )
              break;
            if ( (unsigned int)(v65 - 768) > 0xB50
              || (v70 = 0, (unsigned int)(v65 - 768) > 0x6F)
              && !(unsigned int)CW32System::IsDiacritic(v65)
              && (_WORD)v65 != v81 )
            {
              v70 = *((__int16 *)CcsBullet + 47);
            }
LABEL_93:
            v59 += v70;
            *a8 = v70;
            ++v60;
            if ( v59 + v70 > a6 )
              goto LABEL_112;
            ++a8;
            ++a4;
          }
          if ( (unsigned int)(v65 - 8203) <= 4 )
          {
            v70 = 0;
            goto LABEL_93;
          }
          v66 = (struct CCcs *)((char *)CcsBullet + 16);
          if ( (unsigned __int16)v65 < 0x4E00u
            || (unsigned int)(v65 - 19968) > 0x51FF && (unsigned int)(v65 - 63744) > 0x1FF )
          {
            v67 = (_WORD *)(*((_QWORD *)CcsBullet + 6) + 4 * (*(int *)v66 & v65));
            if ( (_WORD)v65 == *v67 && v67[1] )
            {
              v68 = 1;
              v69 = (__int16)v67[1];
            }
            else
            {
              v68 = 0;
              v69 = 0;
            }
            if ( !*((_DWORD *)v66 + 4) )
            {
              ++*((_DWORD *)v66 + 3);
              if ( v68 )
                goto LABEL_91;
              if ( v67[1] )
                ++*((_DWORD *)v66 + 2);
              else
                ++*((_DWORD *)v66 + 1);
              if ( *((int *)v66 + 3) >= 64 )
                CWidthCache::CheckPerformance(v66);
            }
          }
          else
          {
            if ( (unsigned int)(v65 - 44032) <= 0x2BFF )
              v71 = (__int16 *)((char *)CcsBullet + 36);
            else
              v71 = (__int16 *)((char *)CcsBullet + 38);
            v69 = *v71;
            v68 = (_WORD)v69 != 0;
          }
          if ( v68 )
            goto LABEL_91;
          v72 = v136;
          h = SelectObject(*((HDC *)v136 + 8), *((HGDIOBJ *)v136 + 9));
          if ( !h )
            goto LABEL_91;
          v73 = *((_WORD *)v72 + 48);
          v74 = (HDC)*((_QWORD *)v72 + 8);
          v69 = *((unsigned __int16 *)v72 + 58);
          v131 = v73;
          hdc = v74;
          if ( (unsigned __int16)v65 < 0x4E00u )
          {
LABEL_107:
            v75 = *((_QWORD *)v72 + 6);
            v76 = v65 & *((int *)v72 + 4);
            *(_WORD *)(v75 + 4 * v76 + 2) = 0;
            WideCharStr = v65;
            Buffer = 0;
            v77 = (_WORD *)(v75 + 4 * v76);
            v78 = v65;
            if ( v69 == 42 || (unsigned int)v65 <= 0x7F )
            {
              if ( GetCharWidthA(v74, v65, v65, &Buffer) )
                goto LABEL_109;
              v78 = WideCharStr;
              v74 = hdc;
            }
            v134 = 0;
            ho = 0;
            v132 = 0;
            if ( v78 == 8364 )
            {
              if ( GetDeviceCaps(v74, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(hdc) )
              {
                v134 = 1;
                StockObject = GetStockObject(12);
                v132 = SelectObject(hdc, StockObject);
                memset_0(&v142, 0, sizeof(v142));
                CW32System::GetObjectW(v132, 92, &v142);
                if ( CW32System::_dwPlatformId == 1 )
                  v142.lfOutPrecision = 7;
                else
                  v142.lfOutPrecision = 9;
                ho = CW32System::CreateFontIndirect(&v142);
                SelectObject(hdc, ho);
              }
              v78 = WideCharStr;
            }
            if ( CW32System::_dwPlatformId != 1
              || CW32System::_dwMajorVersion != 4
              || CW32System::_dwMinorVersion
              || (unsigned int)v78 - 128 <= 0x7F
              || v69 != 950 && v69 != 936 )
            {
              goto LABEL_117;
            }
            GetCharWidthW(hdc, 0x4E00u, 0x4E00u, &Buffer);
            v77[1] = Buffer;
            if ( (unsigned int)WideCharStr - 19968 <= 0x51FF )
            {
LABEL_110:
              v77[1] -= v131;
              LOWORD(v69) = v77[1];
              *v77 = v65;
              v72 = v136;
LABEL_111:
              SelectObject(*((HDC *)v72 + 8), h);
              v69 = (__int16)v69;
LABEL_91:
              v70 = 1;
              CcsBullet = v136;
              if ( (int)(v69 + v135) > 1 )
                v70 = v69 + v135;
              goto LABEL_93;
            }
            UsedDefaultChar = 0;
            v119 = WideCharToMultiByte(v69, 0, &WideCharStr, 1, (LPSTR)MultiByteStr, 2, 0, &UsedDefaultChar);
            v120 = LOBYTE(MultiByteStr[0]);
            if ( v119 == 2 )
            {
              v120 = _byteswap_ushort(MultiByteStr[0]);
            }
            else if ( v119 <= 0 )
            {
LABEL_229:
              v78 = WideCharStr;
LABEL_117:
              if ( v78 == 0xFFFF )
              {
                v78 = -2;
                WideCharStr = -2;
              }
              v80 = hdc;
              if ( GetCharWidthW(hdc, v78, v78, &Buffer) )
                v77[1] = Buffer;
              if ( v134 )
              {
                SelectObject(v80, v132);
                DeleteObject(ho);
              }
              goto LABEL_110;
            }
            if ( !GetCharWidthA(hdc, v120, v120, &Buffer) )
              goto LABEL_229;
LABEL_109:
            v77[1] = Buffer;
            goto LABEL_110;
          }
          if ( (unsigned int)(v65 - 19968) > 0x51FF )
          {
            if ( (unsigned int)(v65 - 63744) > 0x1FF )
              goto LABEL_107;
            v73 = v131;
          }
          v93 = (char *)v72 + 36;
          if ( (unsigned int)(v65 - 44032) > 0x2B9F )
            v93 = (char *)v72 + 38;
          v132 = v93;
          CW32System::REGetCharWidth(v74, v65, (__int16 *)v93, v69, v73, cbMultiByte);
          LOWORD(v69) = *(_WORD *)v132;
          goto LABEL_111;
        }
      }
    }
    else
    {
      v116 = &off_1800A6010;
      *(_QWORD *)v132 = &off_1800A6010;
    }
    v115 = 0;
    goto LABEL_203;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x18000a1d0  mov     [rsp-8+arg_10], rbx
0x18000a1d5  push    rbp
0x18000a1d6  push    rsi
0x18000a1d7  push    rdi
0x18000a1d8  push    r12
0x18000a1da  push    r13
0x18000a1dc  push    r14
0x18000a1de  push    r15
0x18000a1e0  lea     rbp, [rsp-20h]
0x18000a1e5  sub     rsp, 120h
0x18000a1ec  mov     rax, cs:__security_cookie
0x18000a1f3  xor     rax, rsp
0x18000a1f6  mov     [rbp+50h+var_40], rax
0x18000a1fa  mov     rbx, [rcx]
0x18000a1fd  mov     r15, r9
0x18000a200  mov     rax, [rbp+50h+arg_40]
0x18000a207  mov     r14d, r8d
0x18000a20a  mov     ecx, [rdx]
0x18000a20c  mov     r13, rdx
0x18000a20f  mov     r12, [rbp+50h+arg_38]
0x18000a216  btr     ecx, 1Fh
0x18000a21a  mov     esi, [rbx+20h]
0x18000a21d  mov     r11d, ecx
0x18000a220  mov     [rbp+50h+var_B0], rax
0x18000a224  mov     rax, [rbp+50h+arg_48]
0x18000a22b  mov     [rbp+50h+ho], rdx
0x18000a22f  mov     [rbp+50h+var_B8], rax
0x18000a233  sub     r11d, esi
0x18000a236  jz      loc_18000A42C
0x18000a23c  mov     r8, [rbx+10h]
0x18000a240  test    r8, r8
0x18000a243  jz      loc_18000A42C
0x18000a249  mov     r9d, [r8+8]
0x18000a24d  test    r9d, r9d
0x18000a250  jz      loc_18000A42C
0x18000a256  mov     eax, esi
0x18000a258  cdq
0x18000a259  sub     eax, edx
0x18000a25b  sar     eax, 1
0x18000a25d  cmp     ecx, eax
0x18000a25f  jl      loc_18000ACE7
0x18000a265  mov     ecx, r11d
0x18000a268  test    r11d, r11d
0x18000a26b  js      loc_18000ABC0
0x18000a271  mov     r10d, [rbx+18h]
0x18000a275  test    r9d, r9d
0x18000a278  jle     loc_18000AD5F
0x18000a27e  cmp     r10d, r9d
0x18000a281  jge     loc_18000AD5F
0x18000a287  mov     rdx, [r8]
0x18000a28a  test    rdx, rdx
0x18000a28d  jz      loc_18000AD5F
0x18000a293  test    r10d, r10d
0x18000a296  js      loc_18000AD5F
0x18000a29c  mov     eax, r10d
0x18000a29f  imul    eax, [r8+10h]
0x18000a2a4  movsxd  r9, eax
0x18000a2a7  add     r9, rdx
0x18000a2aa  nop     word ptr [rax+rax+00h]
0x18000a2b0  test    ecx, ecx
0x18000a2b2  jle     short loc_18000A2EC
0x18000a2b4  mov     eax, [r9]
0x18000a2b7  add     [rbx+1Ch], ecx
0x18000a2ba  mov     ecx, [rbx+1Ch]
0x18000a2bd  cmp     ecx, eax
0x18000a2bf  jl      short loc_18000A2EA
0x18000a2c1  lea     edx, [r10+1]
0x18000a2c5  sub     ecx, eax
0x18000a2c7  mov     [rbx+18h], edx
0x18000a2ca  cmp     edx, [r8+8]
0x18000a2ce  jge     loc_18000AA45
0x18000a2d4  mov     dword ptr [rbx+1Ch], 0
0x18000a2db  mov     r10d, edx
0x18000a2de  movsxd  rax, dword ptr [r8+10h]
0x18000a2e2  add     r9, rax
0x18000a2e5  jmp     short loc_18000A2B0
0x18000a2e7  mov     [rbx+1Ch], edx
0x18000a2ea  xor     ecx, ecx
0x18000a2ec  sub     r11d, ecx
0x18000a2ef  lea     ecx, [rsi+r11]
0x18000a2f3  mov     [rbx+20h], ecx
0x18000a2f6  sub     ecx, esi
0x18000a2f8  jz      loc_18000A398
0x18000a2fe  mov     r9, [rbx+30h]
0x18000a302  test    r9, r9
0x18000a305  jz      loc_18000AA26
0x18000a30b  mov     eax, [r9+8]
0x18000a30f  test    eax, eax
0x18000a311  jz      loc_18000AA26
0x18000a317  mov     edx, ecx
0x18000a319  test    ecx, ecx
0x18000a31b  js      loc_18000AAD7
0x18000a321  mov     r11d, [rbx+38h]
0x18000a325  test    eax, eax
0x18000a327  jle     loc_18000AD4C
0x18000a32d  cmp     r11d, eax
0x18000a330  jge     loc_18000AD4C
0x18000a336  mov     r8, [r9]
0x18000a339  test    r8, r8
0x18000a33c  jz      loc_18000AD4C
0x18000a342  test    r11d, r11d
0x18000a345  js      loc_18000AD4C
0x18000a34b  mov     eax, r11d
0x18000a34e  imul    eax, [r9+10h]
0x18000a353  movsxd  r10, eax
0x18000a356  add     r10, r8
0x18000a359  mov     esi, ecx
0x18000a35b  nop     dword ptr [rax+rax+00h]
0x18000a360  test    edx, edx
0x18000a362  jle     short loc_18000A39A
0x18000a364  mov     eax, [r10]
0x18000a367  add     [rbx+3Ch], edx
0x18000a36a  mov     edx, [rbx+3Ch]
0x18000a36d  cmp     edx, eax
0x18000a36f  jl      short loc_18000A3A4
0x18000a371  lea     r8d, [r11+1]
0x18000a375  mov     [rbx+38h], r8d
0x18000a379  cmp     r8d, [r9+8]
0x18000a37d  jge     loc_18000AA39
0x18000a383  sub     edx, eax
0x18000a385  mov     dword ptr [rbx+3Ch], 0
0x18000a38c  movsxd  rax, dword ptr [r9+10h]
0x18000a390  mov     r11d, r8d
0x18000a393  add     r10, rax
0x18000a396  jmp     short loc_18000A360
0x18000a398  mov     esi, ecx
0x18000a39a  test    esi, esi
0x18000a39c  jz      loc_18000A42C
0x18000a3a2  mov     ecx, esi
0x18000a3a4  mov     r8, [rbx+40h]
0x18000a3a8  test    r8, r8
0x18000a3ab  jz      short loc_18000A42C
0x18000a3ad  mov     eax, [r8+8]
0x18000a3b1  test    eax, eax
0x18000a3b3  jz      short loc_18000A42C
0x18000a3b5  test    esi, esi
0x18000a3b7  js      loc_18000AB47
0x18000a3bd  mov     r10d, [rbx+48h]
0x18000a3c1  test    eax, eax
0x18000a3c3  jle     loc_18000AD54
0x18000a3c9  cmp     r10d, eax
0x18000a3cc  jge     loc_18000AD54
0x18000a3d2  mov     rdx, [r8]
0x18000a3d5  test    rdx, rdx
0x18000a3d8  jz      loc_18000AD54
0x18000a3de  test    r10d, r10d
0x18000a3e1  js      loc_18000AD54
0x18000a3e7  mov     eax, r10d
0x18000a3ea  imul    eax, [r8+10h]
0x18000a3ef  movsxd  r9, eax
0x18000a3f2  add     r9, rdx
0x18000a3f5  xor     r11d, r11d
0x18000a3f8  test    ecx, ecx
0x18000a3fa  jle     short loc_18000A42C
0x18000a3fc  mov     eax, [r9]
0x18000a3ff  add     [rbx+4Ch], ecx
0x18000a402  mov     ecx, [rbx+4Ch]
0x18000a405  cmp     ecx, eax
0x18000a407  jl      short loc_18000A42C
0x18000a409  lea     edx, [r10+1]
0x18000a40d  mov     [rbx+48h], edx
0x18000a410  cmp     edx, [r8+8]
0x18000a414  jge     loc_18000AA2D
0x18000a41a  sub     ecx, eax
0x18000a41c  mov     [rbx+4Ch], r11d
0x18000a420  movsxd  rax, dword ptr [r8+10h]
0x18000a424  mov     r10d, edx
0x18000a427  add     r9, rax
0x18000a42a  jmp     short loc_18000A3F8
0x18000a42c  movzx   edx, byte ptr [rbx+0A2h]
0x18000a433  xor     ecx, ecx
0x18000a435  mov     r8d, [r13+0]
0x18000a439  cmp     r14d, 1
0x18000a43d  mov     eax, edx
0x18000a43f  setz    cl
0x18000a442  shr     eax, 1
0x18000a444  and     eax, 1
0x18000a447  cmp     ecx, eax
0x18000a449  jnz     loc_18000A9F4
0x18000a44f  test    r8d, r8d
0x18000a452  js      loc_18000AF8E
0x18000a458  mov     rcx, [rbx+30h]
0x18000a45c  test    rcx, rcx
0x18000a45f  jz      loc_18000A9E6
0x18000a465  mov     edx, [rcx+8]
0x18000a468  test    edx, edx
0x18000a46a  jz      loc_18000A9E6
0x18000a470  jle     loc_18000AD45
0x18000a476  mov     eax, [rbx+38h]
0x18000a479  cmp     eax, edx
0x18000a47b  jge     loc_18000AD45
0x18000a481  mov     r8, [rcx]
0x18000a484  test    r8, r8
0x18000a487  jz      loc_18000AD45
0x18000a48d  test    eax, eax
0x18000a48f  js      loc_18000AD45
0x18000a495  imul    eax, [rcx+10h]
0x18000a499  movsxd  rdx, eax
0x18000a49c  add     rdx, r8
0x18000a49f  movzx   edx, word ptr [rdx+4]
0x18000a4a3  mov     [rsp+150h+hdc], 0
0x18000a4ac  test    dx, dx
0x18000a4af  jns     short loc_18000A4B9
0x18000a4b1  mov     rax, [rbx+10h]
0x18000a4b5  movzx   edx, word ptr [rax+1Ch]
0x18000a4b9  mov     rcx, cs:qword_1800A72D0
0x18000a4c0  lea     r8, [rsp+150h+hdc]
0x18000a4c5  movsx   edx, dx
0x18000a4c8  mov     rax, [rcx]
0x18000a4cb  mov     rax, [rax+20h]
0x18000a4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d4  test    eax, eax
0x18000a4d6  jns     loc_18000A904
0x18000a4dc  lea     rdi, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x18000a4e3  mov     [rsp+150h+hdc], rdi
0x18000a4e8  mov     r8, [rbx+88h]
0x18000a4ef  mov     r9d, 0FFFFFFFFh
0x18000a4f5  test    r8, r8
0x18000a4f8  jz      loc_18000A90E
0x18000a4fe  mov     rcx, [rbx+30h]
0x18000a502  test    rcx, rcx
0x18000a505  jz      loc_18000AA51
0x18000a50b  mov     edx, [rcx+8]
0x18000a50e  test    edx, edx
0x18000a510  jz      loc_18000AA51
0x18000a516  jle     loc_18000AD67
0x18000a51c  mov     eax, [rbx+38h]
0x18000a51f  cmp     eax, edx
0x18000a521  jge     loc_18000AD67
0x18000a527  mov     rdx, [rcx]
0x18000a52a  test    rdx, rdx
0x18000a52d  jz      loc_18000AD67
0x18000a533  test    eax, eax
0x18000a535  js      loc_18000AD67
0x18000a53b  imul    eax, [rcx+10h]
0x18000a53f  movsxd  rcx, eax
0x18000a542  add     rcx, rdx
0x18000a545  movzx   eax, word ptr [rcx+4]
0x18000a549  cmp     [rbx+9Eh], ax
0x18000a550  jnz     loc_18000A90E
0x18000a556  test    byte ptr [rbx+0A2h], 8
0x18000a55d  jnz     loc_18000A90E
0x18000a563  cmp     byte ptr [rdi+20h], 4
0x18000a567  jz      loc_18000AF9F
0x18000a56d  mov     r14, [rbx+88h]
0x18000a574  movzx   eax, word ptr [r14+62h]
0x18000a579  mov     [rbx+60h], ax
0x18000a57d  mov     [rsp+150h+var_D8], r14
0x18000a582  test    r14, r14
0x18000a585  jz      loc_18000A9DC
0x18000a58b  mov     rax, [rbx+28h]
0x18000a58f  xor     esi, esi
0x18000a591  xor     edi, edi
0x18000a593  mov     [rsp+150h+var_E8], esi
0x18000a597  test    dword ptr [rax+0C0h], 61086013h
0x18000a5a1  jz      short loc_18000A5B3
0x18000a5a3  mov     eax, 3FFh
0x18000a5a8  test    [r13+18h], ax
0x18000a5ad  jnz     loc_18000AC66
0x18000a5b3  test    byte ptr [rbx+0A2h], 2
0x18000a5ba  lea     rdx, [rbx+74h]
0x18000a5be  mov     rax, [r13+8]
0x18000a5c2  movsx   ecx, word ptr [rax+12h]; nNumber
0x18000a5c6  mov     [rsp+150h+var_E0], ecx
0x18000a5ca  jnz     short loc_18000A5D3
0x18000a5cc  lea     rdx, [rbx+84h]
0x18000a5d3  mov     edx, [rdx]; nNumerator
0x18000a5d5  cmp     edx, 5A0h
0x18000a5db  jz      short loc_18000A5E5
0x18000a5dd  test    ecx, ecx
0x18000a5df  jnz     loc_18000AABC
0x18000a5e5  mov     r9d, 640h
0x18000a5eb  mov     ecx, 4E00h
0x18000a5f0  cmp     edi, [rbp+50h+arg_20]
0x18000a5f6  jnb     loc_18000A7E7
0x18000a5fc  cmp     [rsp+150h+var_E8], 0
0x18000a601  movzx   ebx, word ptr [r15]
0x18000a605  jnz     loc_18000A8C8
0x18000a60b  lea     eax, [rbx-200Bh]
0x18000a611  cmp     eax, 4
0x18000a614  jbe     loc_18000A6AB
0x18000a61a  lea     rdx, [r14+10h]
0x18000a61e  cmp     bx, cx
0x18000a621  jnb     loc_18000A6CF
0x18000a627  movsxd  rax, dword ptr [rdx]
0x18000a62a  mov     rcx, rbx
0x18000a62d  and     rcx, rax
0x18000a630  mov     rax, [rdx+20h]
0x18000a634  lea     r8, [rax+rcx*4]
0x18000a638  cmp     bx, [rax+rcx*4]
0x18000a63c  jnz     loc_18000A81D
0x18000a642  movsx   eax, word ptr [r8+2]
0x18000a647  test    ax, ax
0x18000a64a  jz      loc_18000A81D
0x18000a650  mov     r14d, 1
0x18000a656  mov     r13d, eax
0x18000a659  cmp     dword ptr [rdx+10h], 0
0x18000a65d  jnz     loc_18000A706
0x18000a663  inc     dword ptr [rdx+0Ch]
0x18000a666  test    r14d, r14d
  ... truncated ...
```
