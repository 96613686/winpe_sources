# CSiteMap::ReadFromFile(char const *,int,CHtmlHelpControl *,uint)

- ea: `0x180056b00`
- end: `0x180057e05`
- name: `?ReadFromFile@CSiteMap@@QEAAHPEBDHPEAVCHtmlHelpControl@@I@Z`
- size: `4869`
- prototype: `__int64 __usercall@<rax>(CSiteMap *__hidden this@<rcx>, const char *@<rdx>, int@<r8d>, struct CHtmlHelpControl *@<r9>, unsigned int)`
- caller_count: `4`
- callee_count: `33`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001a0ac`
- `0x18001c3dc`
- `0x18003bbc8`
- `0x18003d298`

## callees

- `0x18000171c`
- `0x180013b94`
- `0x180013ee8`
- `0x18001a094`
- `0x18002018c`
- `0x180020210`
- `0x180025fa4`
- `0x1800261f0`
- `0x1800262c0`
- `0x18002e3e0`
- `0x18002ef28`
- `0x180037594`
- `0x18003a9e0`
- `0x180042da8`
- `0x18004e73c`
- `0x18004f65c`
- `0x180053b20`
- `0x180053df0`
- `0x180054050`
- `0x180055060`
- `0x180055b80`
- `0x180055d20`
- `0x180055f10`
- `0x180056b00`
- `0x1800582f0`
- `0x180058400`
- `0x180065cf0`
- `0x1800675c0`
- `0x180069430`
- `0x18006a7ac`
- `0x18006c384`
- `0x18006e4b8`
- `0x180075c90`

## import_xrefs

- `msvcrt!free` at `0x180056bb8`
- `msvcrt!free` at `0x180056c24`
- `msvcrt!free` at `0x180056c49`
- `msvcrt!free` at `0x180056dbe`
- `msvcrt!free` at `0x180056e64`
- `msvcrt!free` at `0x180056e72`
- `msvcrt!free` at `0x180056ead`
- `msvcrt!free` at `0x1800574c9`
- `msvcrt!free` at `0x1800574f5`
- `msvcrt!free` at `0x180057506`
- `msvcrt!free` at `0x18005752d`
- `msvcrt!free` at `0x180057908`
- `msvcrt!free` at `0x180057bf8`
- `msvcrt!free` at `0x180057ca2`
- `msvcrt!free` at `0x180057cb3`
- `msvcrt!free` at `0x180057ce2`
- `msvcrt!free` at `0x180057d93`
- `msvcrt!free` at `0x180057da4`
- `msvcrt!free` at `0x180057dcb`
- `msvcrt!free` at `0x180056bb8`
- `msvcrt!free` at `0x180056c24`
- `msvcrt!free` at `0x180056c49`
- `msvcrt!free` at `0x180056dbe`
- `msvcrt!free` at `0x180056e64`
- `msvcrt!free` at `0x180056e72`
- `msvcrt!free` at `0x180056ead`
- `msvcrt!free` at `0x1800574c9`
- `msvcrt!free` at `0x1800574f5`
- `msvcrt!free` at `0x180057506`
- `msvcrt!free` at `0x18005752d`
- `msvcrt!free` at `0x180057908`
- `msvcrt!free` at `0x180057bf8`
- `msvcrt!free` at `0x180057ca2`
- `msvcrt!free` at `0x180057cb3`
- `msvcrt!free` at `0x180057ce2`
- `msvcrt!free` at `0x180057d93`
- `msvcrt!free` at `0x180057da4`
- `msvcrt!free` at `0x180057dcb`
- `KERNEL32!lstrcmpiA` at `0x180056e4b`
- `KERNEL32!lstrcmpiA` at `0x180056e4b`
- `SHLWAPI!StrCmpNA` at `0x1800571e5`
- `SHLWAPI!StrCmpNA` at `0x1800571e5`
- `SHLWAPI!StrChrA` at `0x18005722a`
- `SHLWAPI!StrChrA` at `0x18005725d`
- `SHLWAPI!StrChrA` at `0x180057436`
- `SHLWAPI!StrChrA` at `0x18005759f`
- `SHLWAPI!StrChrA` at `0x18005793c`
- `SHLWAPI!StrChrA` at `0x180057b11`
- `SHLWAPI!StrChrA` at `0x180057c5a`
- `SHLWAPI!StrChrA` at `0x18005722a`
- `SHLWAPI!StrChrA` at `0x18005725d`
- `SHLWAPI!StrChrA` at `0x180057436`
- `SHLWAPI!StrChrA` at `0x18005759f`
- `SHLWAPI!StrChrA` at `0x18005793c`
- `SHLWAPI!StrChrA` at `0x180057b11`
- `SHLWAPI!StrChrA` at `0x180057c5a`
- `SHLWAPI!StrStrA` at `0x1800571c7`
- `SHLWAPI!StrStrA` at `0x18005731d`
- `SHLWAPI!StrStrA` at `0x1800571c7`
- `SHLWAPI!StrStrA` at `0x18005731d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSiteMap::ReadFromFile(
        CSiteMap *this,
        char *a2,
        int a3,
        struct CHtmlHelpControl *a4,
        unsigned int a5)
{
  struct CHtmlHelpControl *v5; // rbx
  struct _tagSiteMapEntry *v9; // rax
  struct _tagSiteMapEntry *v10; // rdi
  int j; // edi
  CInput *v12; // rbx
  char *v13; // rbx
  int i; // edi
  CInput *v15; // rbx
  int v16; // r14d
  PCSTR *v17; // rcx
  int v18; // r13d
  int v19; // ecx
  char *v20; // rsi
  COleDispatchDriver *v21; // rcx
  const char *FilePortion; // rax
  const char *v23; // rcx
  const char *v24; // rcx
  CHAR *v25; // rdi
  const char *v26; // rcx
  char *v27; // rbx
  const char *v28; // rax
  char *v29; // rdi
  CInput *v30; // r12
  char *NonSpace; // rbx
  char *v32; // r10
  const char *v33; // r11
  int k; // r8d
  int v35; // ecx
  int v36; // edx
  int v37; // ecx
  int v38; // r9d
  char *v39; // r10
  const char *v40; // r11
  int m; // r8d
  int v42; // ecx
  int v43; // edx
  int v44; // ecx
  int v45; // r9d
  char *v46; // r10
  const char *v47; // r11
  int n; // r8d
  int v49; // ecx
  int v50; // edx
  int v51; // ecx
  int v52; // r9d
  char *v53; // r10
  const char *v54; // r11
  int ii; // r8d
  int v56; // ecx
  int v57; // edx
  int v58; // ecx
  int v59; // r9d
  char *v60; // r10
  const char *v61; // r11
  int jj; // r8d
  int v63; // ecx
  int v64; // edx
  int v65; // ecx
  int v66; // r9d
  char *v67; // r10
  const char *v68; // r11
  int kk; // r8d
  int v70; // ecx
  int v71; // edx
  int v72; // ecx
  int v73; // r9d
  const CHAR *v74; // rax
  char *v75; // rbx
  PSTR v76; // rax
  PSTR v77; // rax
  char *Value; // rbx
  char *v79; // r12
  char *v80; // r10
  const char *v81; // r11
  int mm; // edx
  int v83; // ecx
  int v84; // r8d
  int v85; // ecx
  int v86; // r9d
  char *v87; // r10
  const char *v88; // r11
  int nn; // edx
  int v90; // ecx
  int v91; // r8d
  int v92; // ecx
  int v93; // r9d
  char *i1; // rcx
  PSTR v95; // rax
  const char *v96; // rax
  const char *v97; // rdi
  char *v98; // rdi
  CInput *v99; // rbx
  PSTR v101; // rax
  char *v102; // rax
  char *v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rcx
  const char *StringResource; // rax
  char *v107; // rax
  __int64 v108; // rdx
  char *v109; // rax
  __int64 v110; // rdx
  __int64 v111; // rcx
  char *v112; // rdi
  char *i2; // rcx
  PSTR v114; // rax
  __int64 v115; // rax
  unsigned __int8 *v116; // r10
  const char *v117; // r11
  int i3; // edx
  int v119; // ecx
  int v120; // r8d
  int v121; // ecx
  int v122; // r9d
  char *v123; // rdi
  int v124; // eax
  char *i4; // rcx
  PSTR v126; // rax
  const char *v127; // rax
  const char *v128; // rdi
  char *v129; // rdi
  int v130; // edx
  int v131; // ecx
  __int64 v132; // r9
  __int64 v133; // rcx
  unsigned int v134; // r8d
  char v135; // r13
  __int64 v136; // rdx
  char *v137; // [rsp+30h] [rbp-D0h] BYREF
  int v138; // [rsp+38h] [rbp-C8h]
  int v139; // [rsp+3Ch] [rbp-C4h]
  char *v140; // [rsp+40h] [rbp-C0h] BYREF
  char *v141; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v142; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v143[2]; // [rsp+60h] [rbp-A0h] BYREF
  char *v144; // [rsp+88h] [rbp-78h] BYREF
  int v145; // [rsp+90h] [rbp-70h]
  struct CSiteMap *v146; // [rsp+98h] [rbp-68h]
  CSiteEntryUrl *v147; // [rsp+A0h] [rbp-60h]
  int v148; // [rsp+B0h] [rbp-50h]
  struct CHtmlHelpControl *v149; // [rsp+B8h] [rbp-48h]
  int v150; // [rsp+C0h] [rbp-40h]
  char *v151; // [rsp+C8h] [rbp-38h]
  PCSTR *v152[44]; // [rsp+D0h] [rbp-30h] BYREF
  CHAR FileName[2096]; // [rsp+230h] [rbp+130h] BYREF

  v5 = a4;
  v149 = a4;
  v150 = a3;
  v151 = a2;
  *((_DWORD *)this + 85) = a5;
  LODWORD(v152[0]) = -1;
  if ( !(unsigned int)CAInput::Add((CAInput *)v152, a2) )
  {
    if ( v5 )
      AuthorMsg(0x1D805u, a2);
    v9 = CSiteMap::AddEntry(this, 0);
    v10 = v9;
    if ( v9 )
    {
      *((_BYTE *)v9 + 25) = 1;
      v141 = 0;
      CStr::FormatString((CStr *)&v141, 1025, a2);
      v13 = v141;
      *((_QWORD *)v10 + 1) = CTable::StrDupA(this, v141);
      *((_BYTE *)v10 + 27) |= 1u;
      if ( v13 )
        free(v13);
      for ( i = (int)v152[0]; i >= 0; LODWORD(v152[0]) = --i )
      {
        if ( i < 0 )
          break;
        free(v152[2 * i + 2]);
        v15 = (CInput *)v152[2 * i + 1];
        if ( v15 )
        {
          CInput::Close(v15);
          operator delete(v15);
        }
      }
    }
    else
    {
      for ( j = (int)v152[0]; j >= 0; LODWORD(v152[0]) = --j )
      {
        if ( j < 0 )
          break;
        free(v152[2 * j + 2]);
        v12 = (CInput *)v152[2 * j + 1];
        if ( v12 )
        {
          CInput::Close(v12);
          operator delete(v12);
        }
      }
    }
    return 0;
  }
  CSiteMap::SetSiteMapFile(this, a2);
  *((_DWORD *)this + 54) = a3;
  v16 = (int)v152[0];
  v17 = v152[2 * SLODWORD(v152[0]) + 2];
  *((_QWORD *)this + 28) = v17;
  *(_BYTE *)v17 = 0;
  CParseSitemap::CParseSitemap((CParseSitemap *)&v142, this);
  v18 = 0;
  v138 = 0;
  v137 = 0;
  v148 = 0;
  v19 = 0;
  v139 = 0;
  v20 = 0;
  v141 = 0;
  while ( 1 )
  {
    if ( v19 )
    {
      if ( !(unsigned int)CAInput::Add((CAInput *)v152, v20) )
      {
        if ( (unsigned int)ConvertToCacheFile(v20, FileName, 0x824u) )
        {
          CAInput::Add((CAInput *)v152, FileName);
        }
        else if ( v5 )
        {
          v21 = (COleDispatchDriver *)*((_QWORD *)v5 + 62);
          if ( v21 )
          {
            v140 = 0;
            COleDispatchDriver::InvokeHelper(v21, 211, 2u, 8u, &v140, 0);
            FilePortion = FindFilePortion(v140);
            if ( FilePortion )
            {
              *FilePortion = 0;
              CStr::operator+=(&v140, v20);
              if ( (unsigned int)ConvertToCacheFile(v140, FileName, 0x824u) )
                CAInput::Add((CAInput *)v152, FileName);
            }
            if ( v140 )
              free(v140);
          }
        }
      }
      v139 = 0;
      v16 = (int)v152[0];
      v23 = (const char *)v152[2 * SLODWORD(v152[0]) + 2];
      *((_QWORD *)this + 28) = v23;
      if ( !(unsigned int)IsEmptyString(v23) )
      {
        if ( v24 )
        {
          v25 = lcStrDup(v24);
          if ( !v25 )
            goto LABEL_35;
        }
        else
        {
          v25 = 0;
        }
        v26 = (const char *)*((_QWORD *)this + 24);
        if ( v26 )
        {
          v27 = lcStrDup(v26);
          if ( !v27 )
LABEL_35:
            OOM();
        }
        else
        {
          v27 = 0;
        }
        v28 = FindFilePortion(v27);
        if ( v28 )
          *v28 = 0;
        ConvertBackSlashToForwardSlash(v25);
        ConvertBackSlashToForwardSlash(v27);
        if ( !lstrcmpiA(v25, v27) )
          *((_QWORD *)this + 28) = 0;
        if ( v27 )
          free(v27);
        if ( v25 )
          free(v25);
      }
    }
    v29 = (char *)&v152[2 * v16 + 1];
    v140 = v29;
    v30 = *(CInput **)v29;
    if ( (unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
      break;
    if ( v16 < 0 )
      goto LABEL_315;
    free(v152[2 * v16 + 2]);
    if ( v30 )
    {
      CInput::Close(v30);
      operator delete(v30);
    }
    LODWORD(v152[0]) = --v16;
    if ( v16 < 0 )
    {
LABEL_315:
      if ( *((_DWORD *)this + 54) )
      {
        if ( v20 )
          free(v20);
        if ( v137 )
          free(v137);
      }
      else
      {
        if ( !v150 )
        {
          v130 = 1;
          v131 = *((_DWORD *)this + 8);
          if ( v131 - 1 > 1 )
          {
            do
            {
              v132 = *((_QWORD *)this + 2);
              v133 = *(_QWORD *)(v132 + 8LL * v130);
              v134 = *(unsigned __int8 *)(v133 + 25);
              if ( v134 > v18 + 1 )
              {
                v135 = v18 + 1;
                *(_BYTE *)(v133 + 25) = v135;
                LOBYTE(v134) = v135;
                v132 = *((_QWORD *)this + 2);
              }
              v18 = (unsigned __int8)v134;
              if ( *(_WORD *)(v133 + 22)
                && (unsigned __int8)v134 >= *(_BYTE *)(*(_QWORD *)(v132 + 8LL * v130 + 8) + 25LL) )
              {
                *(_BYTE *)(v133 + 27) |= 1u;
              }
              ++v130;
              v131 = *((_DWORD *)this + 8);
            }
            while ( v130 < v131 - 1 );
          }
          if ( v131 > 1 )
          {
            v136 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * v131 - 8);
            *(_BYTE *)(v136 + 27) |= 1u;
          }
        }
        if ( v20 )
          free(v20);
        if ( v137 )
          free(v137);
      }
      CParseSitemap::~CParseSitemap((CParseSitemap *)&v142);
      return 1;
    }
    v142 = 0;
    memset(v143, 0, 24);
    *((_QWORD *)this + 28) = v152[2 * v16 + 2];
LABEL_55:
    v19 = v139;
LABEL_20:
    v5 = v149;
  }
  NonSpace = (char *)FirstNonSpace(v137);
  while ( 1 )
  {
LABEL_58:
    v19 = v139;
    if ( !NonSpace || !*NonSpace )
      goto LABEL_20;
    if ( *NonSpace != 60 )
      goto LABEL_286;
    v32 = NonSpace;
    v33 = "<param name";
    for ( k = 11; ; --k )
    {
      if ( !k )
        goto LABEL_267;
      v35 = (unsigned __int8)*v32;
      v36 = v35 + 32;
      if ( (unsigned int)(v35 - 65) > 0x19 )
        v36 = (unsigned __int8)*v32;
      v37 = *(unsigned __int8 *)v33;
      v38 = v37 + 32;
      if ( (unsigned int)(v37 - 65) > 0x19 )
        v38 = *(unsigned __int8 *)v33;
      if ( v36 != v38 )
        goto LABEL_71;
      if ( !v36 )
        break;
      ++v32;
      ++v33;
    }
    if ( !v38 )
      break;
LABEL_71:
    v39 = NonSpace;
    v40 = "<UL>";
    for ( m = 4; ; --m )
    {
      if ( !m )
        goto LABEL_263;
      v42 = (unsigned __int8)*v39;
      v43 = v42 + 32;
      if ( (unsigned int)(v42 - 65) > 0x19 )
        v43 = (unsigned __int8)*v39;
      v44 = *(unsigned __int8 *)v40;
      v45 = v44 + 32;
      if ( (unsigned int)(v44 - 65) > 0x19 )
        v45 = *(unsigned __int8 *)v40;
      if ( v43 != v45 )
        goto LABEL_81;
      if ( !v43 )
        break;
      ++v39;
      ++v40;
    }
    if ( v45 )
    {
LABEL_81:
      v46 = NonSpace;
      v47 = "</UL>";
      for ( n = 5; ; --n )
      {
        if ( !n )
          goto LABEL_259;
        v49 = (unsigned __int8)*v46;
        v50 = v49 + 32;
        if ( (unsigned int)(v49 - 65) > 0x19 )
          v50 = (unsigned __int8)*v46;
        v51 = *(unsigned __int8 *)v47;
        v52 = v51 + 32;
        if ( (unsigned int)(v51 - 65) > 0x19 )
          v52 = *(unsigned __int8 *)v47;
        if ( v50 != v52 )
          goto LABEL_91;
        if ( !v50 )
          break;
        ++v46;
        ++v47;
      }
      if ( v52 )
      {
LABEL_91:
        v53 = NonSpace;
        v54 = "<LI";
        for ( ii = 3; ; --ii )
        {
          if ( !ii )
            goto LABEL_236;
          v56 = (unsigned __int8)*v53;
          v57 = v56 + 32;
          if ( (unsigned int)(v56 - 65) > 0x19 )
            v57 = (unsigned __int8)*v53;
          v58 = *(unsigned __int8 *)v54;
          v59 = v58 + 32;
          if ( (unsigned int)(v58 - 65) > 0x19 )
            v59 = *(unsigned __int8 *)v54;
          if ( v57 != v59 )
            goto LABEL_101;
          if ( !v57 )
            break;
          ++v53;
          ++v54;
        }
        if ( v59 )
        {
LABEL_101:
          v60 = NonSpace;
          v61 = "</OBJECT>";
          for ( jj = 9; ; --jj )
          {
            if ( !jj )
              goto LABEL_202;
            v63 = (unsigned __int8)*v60;
            v64 = v63 + 32;
            if ( (unsigned int)(v63 - 65) > 0x19 )
              v64 = (unsigned __int8)*v60;
            v65 = *(unsigned __int8 *)v61;
            v66 = v65 + 32;
            if ( (unsigned int)(v65 - 65) > 0x19 )
              v66 = *(unsigned __int8 *)v61;
            if ( v64 != v66 )
              goto LABEL_111;
            if ( !v64 )
              break;
            ++v60;
            ++v61;
          }
          if ( !v66 )
          {
LABEL_202:
            if ( v145 )
            {
              v145 = 0;
              if ( !(unsigned int)IsEmptyString(*((const char **)this + 41)) )
              {
                v112 = 0;
                if ( v144 )
                {
                  v112 = lcStrDup(v144);
                  if ( !v112 )
LABEL_312:
                    OOM();
                }
                if ( v20 )
                  free(v20);
                v20 = v112;
                v141 = v112;
                v139 = 1;
                *((_QWORD *)this + 41) = 0;
                v29 = v140;
              }
LABEL_235:
              NonSpace += 9;
              continue;
            }
            if ( !*((_DWORD *)this + 54) )
            {
              if ( *((_DWORD *)v147 + 3) )
                CSiteEntryUrl::SaveUrlEntry(v147, v146, (struct _tagSiteMapEntry *)&v142);
              if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 9) )
                CTable::IncreaseTableBuffer(this);
              if ( *((_DWORD *)this + 8) < *((_DWORD *)this + 9) )
              {
                v109 = CTable::TableMalloc(this, 40);
                *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8)) = v109;
                if ( v109 )
                {
                  v110 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8));
                  *(_OWORD *)v110 = v142;
                  *(_QWORD *)(v110 + 16) = *(_QWORD *)&v143[0];
                  *(_WORD *)(v110 + 24) = WORD4(v143[0]);
                  *(_QWORD *)(v110 + 26) = *(_QWORD *)((char *)v143 + 10);
                  *(_DWORD *)(v110 + 34) = *(_DWORD *)((char *)&v143[1] + 2);
                  *(_WORD *)(v110 + 38) = WORD3(v143[1]);
                  v111 = *((int *)this + 8);
                  *((_DWORD *)this + 8) = v111 + 1;
                  if ( (_DWORD)v111 )
                    **(_QWORD **)(*((_QWORD *)this + 2) + 8 * v111) = this;
                }
              }
              goto LABEL_235;
            }
            if ( !*((_DWORD *)v147 + 3) )
            {
              NonSpace += 9;
              continue;
            }
            CSiteEntryUrl::SaveUrlEntry(v147, v146, (struct _tagSiteMapEntry *)&v142);
            if ( *((_QWORD *)&v142 + 1) && WORD3(v143[0]) )
            {
              if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 9) )
                CTable::IncreaseTableBuffer(this);
              if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 9) )
                goto LABEL_220;
              v103 = CTable::TableMalloc(this, 40);
              *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8)) = v103;
              if ( !v103 )
                goto LABEL_220;
              v104 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8));
              *(_OWORD *)v104 = v142;
              *(_QWORD *)(v104 + 16) = *(_QWORD *)&v143[0];
              *(_WORD *)(v104 + 24) = WORD4(v143[0]);
              *(_QWORD *)(v104 + 26) = *(_QWORD *)((char *)v143 + 10);
              *(_DWORD *)(v104 + 34) = *(_DWORD *)((char *)&v143[1] + 2);
              *(_WORD *)(v104 + 38) = WORD3(v143[1]);
              v105 = *((int *)this + 8);
              *((_DWORD *)this + 8) = v105 + 1;
              if ( !(_DWORD)v105 )
                goto LABEL_220;
            }
            else
            {
              StringResource = GetStringResource(0x1D729u);
              *((_QWORD *)&v142 + 1) = CTable::StrDupA(this, StringResource);
              if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 9) )
                CTable::IncreaseTableBuffer(this);
              if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 9) )
                goto LABEL_220;
              v107 = CTable::TableMalloc(this, 40);
              *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8)) = v107;
              if ( !v107 )
                goto LABEL_220;
              v108 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8));
              *(_OWORD *)v108 = v142;
              *(_QWORD *)(v108 + 16) = *(_QWORD *)&v143[0];
              *(_WORD *)(v108 + 24) = WORD4(v143[0]);
              *(_QWORD *)(v108 + 26) = *(_QWORD *)((char *)v143 + 10);
              *(_DWORD *)(v108 + 34) = *(_DWORD *)((char *)&v143[1] + 2);
              *(_WORD *)(v108 + 38) = WORD3(v143[1]);
              v105 = *((int *)this + 8);
              *((_DWORD *)this + 8) = v105 + 1;
              if ( !(_DWORD)v105 )
                goto LABEL_220;
            }
            **(_QWORD **)(*((_QWORD *)this + 2) + 8 * v105) = this;
LABEL_220:
            v142 = 0;
            memset(v143, 0, 24);
            BYTE9(v143[0]) = v138;
            goto LABEL_235;
          }
LABEL_111:
          if ( (unsigned int)IsSamePrefix(NonSpace, "<!-- Sitemap", -1)
            || (unsigned int)IsSamePrefix(NonSpace, "<!--Sitemap", -1)
            || (unsigned int)IsSamePrefix(NonSpace, "<!Sitemap", -1) )
          {
            while ( 1 )
            {
              v101 = StrChrA(NonSpace, 0x3Eu);
              if ( v101 )
                break;
              if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
                goto LABEL_185;
              NonSpace = v137;
            }
            v102 = (char *)FirstNonSpace(v101 + 1);
            NonSpace = v102;
            if ( !v102 )
              goto LABEL_185;
            v148 = 1;
            v19 = v139;
            if ( !*v102 )
              goto LABEL_20;
LABEL_287:
            while ( 1 )
            {
              NonSpace = StrChrA(NonSpace, 0x3Cu);
              if ( NonSpace )
                break;
              if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
              {
                NonSpace = (char *)Class;
                goto LABEL_58;
              }
              NonSpace = v137;
            }
          }
          else
          {
            v67 = NonSpace;
            v68 = "<OBJECT";
            for ( kk = 7; ; --kk )
            {
              if ( !kk )
                goto LABEL_138;
              v70 = (unsigned __int8)*v67;
              v71 = v70 + 32;
              if ( (unsigned int)(v70 - 65) > 0x19 )
                v71 = (unsigned __int8)*v67;
              v72 = *(unsigned __int8 *)v68;
              v73 = v72 + 32;
              if ( (unsigned int)(v72 - 65) > 0x19 )
                v73 = *(unsigned __int8 *)v68;
              if ( v71 != v73 )
                goto LABEL_124;
              if ( !v71 )
                break;
              ++v67;
              ++v68;
            }
            if ( v73 )
            {
LABEL_124:
              if ( (unsigned int)IsSamePrefix(NonSpace, "<A HREF", -1) )
              {
                while ( 1 )
                {
                  v74 = StrStrA(NonSpace, "</");
                  v75 = (char *)v74;
                  if ( v74 )
                  {
                    if ( !StrCmpNA(v74, "</A>", 4) )
                      break;
                    v75 = (char *)HHStrStrIA(v75, "</A>");
                    if ( v75 )
                      break;
                  }
                  if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
                    goto LABEL_185;
                  NonSpace = v137;
                }
                while ( 1 )
                {
                  v76 = StrChrA(v75, 0x3Eu);
                  if ( v76 )
                    break;
                  if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
                    goto LABEL_133;
                  v75 = v137;
                }
              }
              else
              {
                while ( 1 )
                {
                  v76 = StrChrA(NonSpace, 0x3Eu);
                  if ( v76 )
                    break;
                  if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
                  {
LABEL_133:
                    NonSpace = 0;
                    goto LABEL_58;
                  }
                  NonSpace = v137;
                }
              }
              NonSpace = (char *)FirstNonSpace(v76 + 1);
            }
            else
            {
LABEL_138:
              NonSpace = GetType(v152, (struct CStr *)&v137, NonSpace + 7, (struct CStr *)&v144);
              if ( !NonSpace )
              {
                if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
                  goto LABEL_185;
                NonSpace = GetType(v152, (struct CStr *)&v137, (const char *)7, (struct CStr *)&v144);
                if ( !NonSpace )
                  goto LABEL_185;
              }
              if ( !v144 || !(unsigned int)IsSamePrefix(v144, "text/site properties", -1) )
              {
                v77 = StrStrA(NonSpace, "</");
                Value = v77;
                if ( v77 )
                  Value = (char *)FirstNonSpace(v77 + 1);
                while ( 1 )
                {
                  while ( 1 )
                  {
                    v79 = Value;
                    if ( Value )
                      goto LABEL_316;
                    if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
                      goto LABEL_185;
                    Value = (char *)FirstNonSpace(v137);
                    if ( Value )
                    {
LABEL_316:
                      if ( *Value )
                        break;
                    }
                    Value = 0;
                  }
                  if ( *Value == 60 )
                  {
                    v80 = Value;
                    v81 = "</OBJECT>";
                    for ( mm = 9; ; --mm )
                    {
                      if ( !mm )
                        goto LABEL_195;
                      v83 = (unsigned __int8)*v80;
                      v84 = v83 + 32;
                      if ( (unsigned int)(v83 - 65) > 0x19 )
                        v84 = (unsigned __int8)*v80;
                      v85 = *(unsigned __int8 *)v81;
                      v86 = v85 + 32;
                      if ( (unsigned int)(v85 - 65) > 0x19 )
                        v86 = *(unsigned __int8 *)v81;
                      if ( v84 != v86 )
                        goto LABEL_161;
                      if ( !v84 )
                        break;
                      ++v80;
                      ++v81;
                    }
                    if ( !v86 )
                    {
LABEL_195:
                      NonSpace = Value + 9;
                      v30 = *(CInput **)v29;
                      goto LABEL_58;
                    }
LABEL_161:
                    v87 = Value;
                    v88 = "<param name";
                    for ( nn = 11; ; --nn )
                    {
                      if ( !nn )
                        goto LABEL_171;
                      v90 = (unsigned __int8)*v87;
                      v91 = v90 + 32;
                      if ( (unsigned int)(v90 - 65) > 0x19 )
                        v91 = (unsigned __int8)*v87;
                      v92 = *(unsigned __int8 *)v88;
                      v93 = v92 + 32;
                      if ( (unsigned int)(v92 - 65) > 0x19 )
                        v93 = *(unsigned __int8 *)v88;
                      if ( v91 != v93 )
                        goto LABEL_184;
                      if ( !v91 )
                        break;
                      ++v87;
                      ++v88;
                    }
                    if ( !v93 )
                    {
LABEL_171:
                      for ( i1 = Value + 11; ; i1 = v137 )
                      {
                        v95 = StrChrA(i1, 0x22u);
                        if ( v95 )
                          break;
                        if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
                          goto LABEL_185;
                      }
                      v96 = (const char *)FirstNonSpace(v95 + 1);
                      v97 = v96;
                      if ( !v96 )
                        goto LABEL_185;
                      Value = GetValue((struct CAInput *)v152, (struct CStr *)&v137, v96, &v144);
                      if ( !Value )
                        goto LABEL_185;
                      if ( (unsigned int)IsSamePrefix(v97, "Merge", -1) )
                      {
                        v98 = 0;
                        if ( v144 )
                        {
                          v98 = lcStrDup(v144);
                          if ( !v98 )
                            goto LABEL_312;
                        }
                        if ( v20 )
                          free(v20);
                        v20 = v98;
                        v141 = v98;
                        v139 = 1;
                      }
                      v29 = v140;
                    }
                  }
LABEL_184:
                  if ( v79 == Value )
                    goto LABEL_185;
                }
              }
              v145 = 1;
            }
          }
        }
        else
        {
LABEL_236:
          for ( i2 = NonSpace + 3; ; i2 = v137 )
          {
            v114 = StrChrA(i2, 0x3Eu);
            if ( v114 )
              break;
            if ( !(unsigned int)CInput::getline((PCSTR *)v30, (struct CStr *)&v137) )
              goto LABEL_185;
          }
          v115 = FirstNonSpace(v114 + 1);
          NonSpace = (char *)v115;
          if ( !v115 )
            goto LABEL_185;
          v116 = (unsigned __int8 *)v115;
          v117 = "<OBJECT";
          for ( i3 = 7; ; --i3 )
          {
            if ( !i3 )
              goto LABEL_251;
            v119 = *v116;
            v120 = v119 + 32;
            if ( (unsigned int)(v119 - 65) > 0x19 )
              v120 = *v116;
            v121 = *(unsigned __int8 *)v117;
            v122 = v121 + 32;
            if ( (unsigned int)(v121 - 65) > 0x19 )
              v122 = *(unsigned __int8 *)v117;
            if ( v120 != v122 )
              goto LABEL_286;
            if ( !v120 )
              break;
            ++v116;
            ++v117;
          }
          if ( v122 )
            goto LABEL_286;
LABEL_251:
          NonSpace = GetType(v152, (struct CStr *)&v137, (const char *)(v115 + 7), (struct CStr *)&v144);
          if ( !NonSpace )
          {
            if ( !(unsigned int)CInput::getline(*(PCSTR **)v29, (struct CStr *)&v137) )
              goto LABEL_185;
            NonSpace = GetType(v152, (struct CStr *)&v137, v137, (struct CStr *)&v144);
            if ( !NonSpace )
              goto LABEL_185;
          }
          v123 = v144;
          if ( !v144 )
          {
LABEL_285:
            v29 = v140;
            goto LABEL_286;
          }
          if ( !(unsigned int)IsSamePrefix(v144, "text/sitemap", -1) )
          {
            v124 = IsSamePrefix(v123, "text/site properties", -1);
            v29 = v140;
            if ( v124 )
              v145 = 1;
LABEL_286:
            if ( !v148 )
              goto LABEL_55;
            goto LABEL_287;
          }
          v142 = 0;
          memset(v143, 0, 24);
          BYTE9(v143[0]) = v138;
LABEL_57:
          v29 = v140;
        }
      }
      else
      {
LABEL_259:
        if ( v138 >= 1 )
        {
          --v138;
        }
        else
        {
          doAuthorMsg(0x1D84Bu, v151);
          v138 = 0;
        }
        NonSpace = (char *)FirstNonSpace(NonSpace + 5);
      }
    }
    else
    {
LABEL_263:
      if ( v138 < 50 )
      {
        ++v138;
      }
      else
      {
        doAuthorMsg(0x1D84Bu, v151);
        v138 = 50;
      }
      NonSpace = (char *)FirstNonSpace(NonSpace + 4);
    }
  }
LABEL_267:
  for ( i4 = NonSpace + 11; ; i4 = v137 )
  {
    v126 = StrChrA(i4, 0x22u);
    if ( v126 )
      break;
    if ( !(unsigned int)CInput::getline((PCSTR *)v30, (struct CStr *)&v137) )
      goto LABEL_185;
  }
  v127 = (const char *)FirstNonSpace(v126 + 1);
  v128 = v127;
  if ( v127 )
  {
    NonSpace = GetValue((struct CAInput *)v152, (struct CStr *)&v137, v127, &v144);
    if ( NonSpace )
    {
      if ( !(unsigned int)CSiteMap::ParseSiteMapParam(this, (struct CParseSitemap *)&v142, v128, 0) )
      {
        if ( (unsigned int)IsSamePrefix(v128, "HHI", -1) )
        {
          *((_QWORD *)this + 41) = CTable::StrDupA(this, v144);
        }
        else if ( (unsigned int)IsSamePrefix(v128, "Merge", -1) )
        {
          v129 = 0;
          if ( v144 )
          {
            v129 = lcStrDup(v144);
            if ( !v129 )
              goto LABEL_312;
          }
          if ( v20 )
            free(v20);
          v20 = v129;
          v141 = v129;
          v139 = 1;
        }
        else
        {
          if ( *((_DWORD *)this + 54) || !(unsigned int)IsSamePrefix(v128, "Favorites", -1) )
            goto LABEL_285;
          CSiteMap::CreateFavorites(this);
        }
      }
      goto LABEL_57;
    }
  }
LABEL_185:
  if ( v20 )
    free(v20);
  if ( v137 )
    free(v137);
  CParseSitemap::~CParseSitemap((CParseSitemap *)&v142);
  for ( ; v16 >= 0; LODWORD(v152[0]) = v16 )
  {
    free(v152[2 * v16 + 2]);
    v99 = (CInput *)v152[2 * v16 + 1];
    if ( v99 )
    {
      CInput::Close(v99);
      operator delete(v99);
    }
    --v16;
  }
  return 0;
}

```

## disassembly

```asm
0x180056b00  mov     [rsp-8+arg_10], rbx
0x180056b05  push    rbp
0x180056b06  push    rsi
0x180056b07  push    rdi
0x180056b08  push    r12
0x180056b0a  push    r13
0x180056b0c  push    r14
0x180056b0e  push    r15
0x180056b10  lea     rbp, [rsp-970h]
0x180056b18  sub     rsp, 0A70h
0x180056b1f  mov     rax, cs:__security_cookie
0x180056b26  xor     rax, rsp
0x180056b29  mov     [rbp+9A0h+var_40], rax
0x180056b30  mov     rbx, r9
0x180056b33  mov     [rbp+9A0h+var_9E8], rbx
0x180056b37  mov     edi, r8d
0x180056b3a  mov     [rbp+9A0h+var_9E0], r8d
0x180056b3e  mov     rsi, rdx
0x180056b41  mov     [rbp+9A0h+var_9D8], rdx
0x180056b45  mov     r15, rcx
0x180056b48  mov     eax, [rbp+9A0h+arg_20]
0x180056b4e  mov     [rcx+154h], eax
0x180056b54  mov     [rbp+9A0h+var_9D0], 0FFFFFFFFh
0x180056b5b  lea     rcx, [rbp+9A0h+var_9D0]; this
0x180056b5f  call    ?Add@CAInput@@QEAAHPEBD@Z; CAInput::Add(char const *)
0x180056b64  test    eax, eax
0x180056b66  jnz     loc_180056C76
0x180056b6c  test    rbx, rbx
0x180056b6f  jz      short loc_180056B88
0x180056b71  mov     r9, rbx
0x180056b74  mov     r8, [rbx+0E8h]
0x180056b7b  mov     rdx, rsi; char *
0x180056b7e  mov     ecx, 1D805h; unsigned int
0x180056b83  call    AuthorMsg
0x180056b88  xor     edx, edx; struct _tagSiteMapEntry *
0x180056b8a  mov     rcx, r15; this
0x180056b8d  call    ?AddEntry@CSiteMap@@QEAAPEAU_tagSiteMapEntry@@PEAU2@@Z; CSiteMap::AddEntry(_tagSiteMapEntry *)
0x180056b92  mov     rdi, rax
0x180056b95  test    rax, rax
0x180056b98  jnz     short loc_180056BE5
0x180056b9a  mov     edi, [rbp+9A0h+var_9D0]
0x180056b9d  test    edi, edi
0x180056b9f  js      loc_180057557
0x180056ba5  test    edi, edi
0x180056ba7  js      loc_180057557
0x180056bad  movsxd  rbx, edi
0x180056bb0  add     rbx, rbx
0x180056bb3  mov     rcx, [rbp+rbx*8+9A0h+Block]; Block
0x180056bb8  call    cs:__imp_free
0x180056bbe  mov     rbx, [rbp+rbx*8+9A0h+var_9C8]
0x180056bc3  test    rbx, rbx
0x180056bc6  jz      short loc_180056BD8
0x180056bc8  mov     rcx, rbx; this
0x180056bcb  call    ?Close@CInput@@QEAAXXZ; CInput::Close(void)
0x180056bd0  mov     rcx, rbx; Block
0x180056bd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056bd8  sub     edi, 1
0x180056bdb  mov     [rbp+9A0h+var_9D0], edi
0x180056bde  jns     short loc_180056BA5
0x180056be0  jmp     loc_180057557
0x180056be5  mov     byte ptr [rax+19h], 1
0x180056be9  xor     r13d, r13d
0x180056bec  mov     [rsp+0AA0h+var_A58], r13
0x180056bf1  mov     r8, rsi; char *
0x180056bf4  mov     edx, 401h; int
0x180056bf9  lea     rcx, [rsp+0AA0h+var_A58]; this
0x180056bfe  call    ?FormatString@CStr@@QEAAXHPEBD@Z; CStr::FormatString(int,char const *)
0x180056c03  nop
0x180056c04  mov     rbx, [rsp+0AA0h+var_A58]
0x180056c09  mov     rdx, rbx; char *
0x180056c0c  mov     rcx, r15; this
0x180056c0f  call    ?StrDupA@CTable@@QEAAPEBDPEBD@Z; CTable::StrDupA(char const *)
0x180056c14  mov     [rdi+8], rax
0x180056c18  or      byte ptr [rdi+1Bh], 1
0x180056c1c  test    rbx, rbx
0x180056c1f  jz      short loc_180056C2B
0x180056c21  mov     rcx, rbx; Block
0x180056c24  call    cs:__imp_free
0x180056c2a  nop
0x180056c2b  mov     edi, [rbp+9A0h+var_9D0]
0x180056c2e  test    edi, edi
0x180056c30  js      loc_180057557
0x180056c36  test    edi, edi
0x180056c38  js      loc_180057557
0x180056c3e  movsxd  rbx, edi
0x180056c41  add     rbx, rbx
0x180056c44  mov     rcx, [rbp+rbx*8+9A0h+Block]; Block
0x180056c49  call    cs:__imp_free
0x180056c4f  mov     rbx, [rbp+rbx*8+9A0h+var_9C8]
0x180056c54  test    rbx, rbx
0x180056c57  jz      short loc_180056C69
0x180056c59  mov     rcx, rbx; this
0x180056c5c  call    ?Close@CInput@@QEAAXXZ; CInput::Close(void)
0x180056c61  mov     rcx, rbx; Block
0x180056c64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056c69  sub     edi, 1
0x180056c6c  mov     [rbp+9A0h+var_9D0], edi
0x180056c6f  jns     short loc_180056C36
0x180056c71  jmp     loc_180057557
0x180056c76  mov     rdx, rsi; char *
0x180056c79  mov     rcx, r15; this
0x180056c7c  call    ?SetSiteMapFile@CSiteMap@@QEAAXPEBD@Z; CSiteMap::SetSiteMapFile(char const *)
0x180056c81  mov     [r15+0D8h], edi
0x180056c88  movsxd  r14, [rbp+9A0h+var_9D0]
0x180056c8c  mov     rax, r14
0x180056c8f  add     rax, rax
0x180056c92  mov     rcx, [rbp+rax*8+9A0h+Block]
0x180056c97  mov     [r15+0E0h], rcx
0x180056c9e  mov     byte ptr [rcx], 0
0x180056ca1  mov     rdx, r15; struct CSiteMap *
0x180056ca4  lea     rcx, [rsp+0AA0h+var_A50]; this
0x180056ca9  call    ??0CParseSitemap@@QEAA@PEAVCSiteMap@@@Z; CParseSitemap::CParseSitemap(CSiteMap *)
0x180056cae  nop
0x180056caf  xor     r13d, r13d
0x180056cb2  mov     [rsp+0AA0h+var_A68], r13d
0x180056cb7  mov     [rsp+0AA0h+var_A70], r13
0x180056cbc  mov     [rbp+9A0h+var_9F0], r13d
0x180056cc0  mov     ecx, r13d
0x180056cc3  mov     [rsp+0AA0h+var_A64], ecx
0x180056cc7  mov     esi, r13d
0x180056cca  mov     [rsp+0AA0h+var_A58], r13
0x180056ccf  jmp     short loc_180056CD5
0x180056cd1  mov     rbx, [rbp+9A0h+var_9E8]
0x180056cd5  mov     edi, 8
0x180056cda  mov     r12d, 2
0x180056ce0  test    ecx, ecx
0x180056ce2  jz      loc_180056E78
0x180056ce8  mov     rdx, rsi; lpFileName
0x180056ceb  lea     rcx, [rbp+9A0h+var_9D0]; this
0x180056cef  call    ?Add@CAInput@@QEAAHPEBD@Z; CAInput::Add(char const *)
0x180056cf4  test    eax, eax
0x180056cf6  jnz     loc_180056DC4
0x180056cfc  mov     r8d, 824h; unsigned __int64
0x180056d02  lea     rdx, [rbp+9A0h+FileName]; char *
0x180056d09  mov     rcx, rsi; char *
0x180056d0c  call    ?ConvertToCacheFile@@YAHPEBDPEAD_K@Z; ConvertToCacheFile(char const *,char *,unsigned __int64)
0x180056d11  test    eax, eax
0x180056d13  jz      short loc_180056D2A
0x180056d15  lea     rdx, [rbp+9A0h+FileName]; lpFileName
0x180056d1c  lea     rcx, [rbp+9A0h+var_9D0]; this
0x180056d20  call    ?Add@CAInput@@QEAAHPEBD@Z; CAInput::Add(char const *)
0x180056d25  jmp     loc_180056DC4
0x180056d2a  test    rbx, rbx
0x180056d2d  jz      loc_180056DC4
0x180056d33  mov     rcx, [rbx+1F0h]; this
0x180056d3a  test    rcx, rcx
0x180056d3d  jz      loc_180056DC4
0x180056d43  mov     [rsp+0AA0h+var_A60], r13
0x180056d48  mov     [rsp+0AA0h+var_A78], r13; unsigned __int8 *
0x180056d4d  lea     rax, [rsp+0AA0h+var_A60]
0x180056d52  mov     [rsp+0AA0h+var_A80], rax; void *
0x180056d57  movzx   r9d, di; unsigned __int16
0x180056d5b  movzx   r8d, r12w; unsigned __int16
0x180056d5f  mov     edx, 0D3h; int
0x180056d64  call    ?InvokeHelper@COleDispatchDriver@@QEAAXJGGPEAXPEBEZZ; COleDispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x180056d69  mov     rcx, [rsp+0AA0h+var_A60]; char *
0x180056d6e  call    ?FindFilePortion@@YAPEBDPEBD@Z; FindFilePortion(char const *)
0x180056d73  test    rax, rax
0x180056d76  jz      short loc_180056DB4
0x180056d78  mov     byte ptr [rax], 0
0x180056d7b  mov     rdx, rsi
0x180056d7e  lea     rcx, [rsp+0AA0h+var_A60]
0x180056d83  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x180056d88  mov     r8d, 824h; unsigned __int64
0x180056d8e  lea     rdx, [rbp+9A0h+FileName]; char *
0x180056d95  mov     rcx, [rsp+0AA0h+var_A60]; char *
0x180056d9a  call    ?ConvertToCacheFile@@YAHPEBDPEAD_K@Z; ConvertToCacheFile(char const *,char *,unsigned __int64)
0x180056d9f  test    eax, eax
0x180056da1  jz      short loc_180056DB4
0x180056da3  lea     rdx, [rbp+9A0h+FileName]; lpFileName
0x180056daa  lea     rcx, [rbp+9A0h+var_9D0]; this
0x180056dae  call    ?Add@CAInput@@QEAAHPEBD@Z; CAInput::Add(char const *)
0x180056db3  nop
0x180056db4  mov     rcx, [rsp+0AA0h+var_A60]; Block
0x180056db9  test    rcx, rcx
0x180056dbc  jz      short loc_180056DC4
0x180056dbe  call    cs:__imp_free
0x180056dc4  mov     [rsp+0AA0h+var_A64], r13d
0x180056dc9  movsxd  r14, [rbp+9A0h+var_9D0]
0x180056dcd  mov     rax, r14
0x180056dd0  add     rax, rax
0x180056dd3  mov     rcx, [rbp+rax*8+9A0h+Block]; char *
0x180056dd8  mov     [r15+0E0h], rcx
0x180056ddf  call    ?IsEmptyString@@YAHPEBD@Z; IsEmptyString(char const *)
0x180056de4  test    eax, eax
0x180056de6  jnz     loc_180056E78
0x180056dec  test    rcx, rcx
0x180056def  jz      short loc_180056E04
0x180056df1  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x180056df6  mov     rdi, rax
0x180056df9  test    rax, rax
0x180056dfc  jnz     short loc_180056E07
0x180056dfe  call    ?OOM@@YAXXZ; OOM(void)
0x180056e04  mov     rdi, r13
0x180056e07  mov     rcx, [r15+0C0h]; char *
0x180056e0e  test    rcx, rcx
0x180056e11  jz      short loc_180056E22
0x180056e13  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x180056e18  mov     rbx, rax
0x180056e1b  test    rax, rax
0x180056e1e  jz      short loc_180056DFE
0x180056e20  jmp     short loc_180056E25
0x180056e22  mov     rbx, r13
0x180056e25  mov     rcx, rbx; char *
0x180056e28  call    ?FindFilePortion@@YAPEBDPEBD@Z; FindFilePortion(char const *)
0x180056e2d  test    rax, rax
0x180056e30  jz      short loc_180056E35
0x180056e32  mov     byte ptr [rax], 0
0x180056e35  mov     rcx, rdi; lpsz
0x180056e38  call    ?ConvertBackSlashToForwardSlash@@YAXPEAD@Z; ConvertBackSlashToForwardSlash(char *)
0x180056e3d  mov     rcx, rbx; lpsz
0x180056e40  call    ?ConvertBackSlashToForwardSlash@@YAXPEAD@Z; ConvertBackSlashToForwardSlash(char *)
0x180056e45  mov     rdx, rbx; lpString2
0x180056e48  mov     rcx, rdi; lpString1
0x180056e4b  call    cs:__imp_lstrcmpiA
0x180056e51  test    eax, eax
0x180056e53  jnz     short loc_180056E5C
0x180056e55  mov     [r15+0E0h], r13
0x180056e5c  test    rbx, rbx
0x180056e5f  jz      short loc_180056E6A
0x180056e61  mov     rcx, rbx; Block
0x180056e64  call    cs:__imp_free
0x180056e6a  test    rdi, rdi
0x180056e6d  jz      short loc_180056E78
0x180056e6f  mov     rcx, rdi; Block
0x180056e72  call    cs:__imp_free
0x180056e78  movsxd  rbx, r14d
0x180056e7b  shl     rbx, 4
0x180056e7f  lea     rdi, [rbp+9A0h+var_9C8]
0x180056e83  add     rdi, rbx
0x180056e86  mov     [rsp+0AA0h+var_A60], rdi
0x180056e8b  mov     r12, [rdi]
0x180056e8e  lea     rdx, [rsp+0AA0h+var_A70]; struct CStr *
0x180056e93  mov     rcx, r12; this
0x180056e96  call    ?getline@CInput@@QEAAHPEAVCStr@@@Z; CInput::getline(CStr *)
0x180056e9b  test    eax, eax
0x180056e9d  jnz     short loc_180056F05
0x180056e9f  test    r14d, r14d
0x180056ea2  js      loc_180057C90
0x180056ea8  mov     rcx, [rbp+rbx+9A0h+Block]; Block
0x180056ead  call    cs:__imp_free
0x180056eb3  test    r12, r12
0x180056eb6  jz      short loc_180056EC8
0x180056eb8  mov     rcx, r12; this
0x180056ebb  call    ?Close@CInput@@QEAAXXZ; CInput::Close(void)
0x180056ec0  mov     rcx, r12; Block
0x180056ec3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180056ec8  sub     r14d, 1
0x180056ecc  mov     [rbp+9A0h+var_9D0], r14d
0x180056ed0  js      loc_180057C90
0x180056ed6  xorps   xmm0, xmm0
0x180056ed9  xor     eax, eax
0x180056edb  movups  [rsp+0AA0h+var_A50], xmm0
0x180056ee0  movups  [rsp+0AA0h+var_A40], xmm0
0x180056ee5  mov     [rsp+0AA0h+var_A30], rax
0x180056eea  movsxd  rax, r14d
0x180056eed  add     rax, rax
0x180056ef0  mov     rax, [rbp+rax*8+9A0h+Block]
0x180056ef5  mov     [r15+0E0h], rax
0x180056efc  mov     ecx, [rsp+0AA0h+var_A64]
0x180056f00  jmp     loc_180056CD1
0x180056f05  mov     rcx, [rsp+0AA0h+var_A70]
0x180056f0a  call    FirstNonSpace
0x180056f0f  mov     rbx, rax
0x180056f12  jmp     short loc_180056F19
0x180056f14  mov     rdi, [rsp+0AA0h+var_A60]
0x180056f19  test    rbx, rbx
0x180056f1c  mov     ecx, [rsp+0AA0h+var_A64]
0x180056f20  jz      loc_180056CD1
0x180056f26  movzx   eax, byte ptr [rbx]
0x180056f29  test    al, al
0x180056f2b  jz      loc_180056CD1
0x180056f31  cmp     al, 3Ch ; '<'
0x180056f33  jnz     loc_180057C48
0x180056f39  mov     r10, rbx
0x180056f3c  lea     r11, ?txtParam@@3QBDB; "<param name"
0x180056f43  mov     r8d, 0Bh
0x180056f49  test    r8d, r8d
0x180056f4c  jz      loc_180057B08
0x180056f52  movzx   ecx, byte ptr [r10]
0x180056f56  lea     eax, [rcx-41h]
0x180056f59  lea     edx, [rcx+20h]
0x180056f5c  cmp     eax, 19h
0x180056f5f  cmova   edx, ecx
0x180056f62  movzx   ecx, byte ptr [r11]
0x180056f66  lea     eax, [rcx-41h]
0x180056f69  lea     r9d, [rcx+20h]
0x180056f6d  cmp     eax, 19h
0x180056f70  cmova   r9d, ecx
0x180056f74  cmp     edx, r9d
0x180056f77  jnz     short loc_180056F91
0x180056f79  test    edx, edx
0x180056f7b  jz      short loc_180056F88
0x180056f7d  dec     r8d
0x180056f80  inc     r10
0x180056f83  inc     r11
0x180056f86  jmp     short loc_180056F49
0x180056f88  test    r9d, r9d
0x180056f8b  jz      loc_180057B08
0x180056f91  mov     r10, rbx
  ... truncated ...
```
