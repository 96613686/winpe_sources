# SSI_INCLUDE_FILE::ProcessSsiElements(int *)

- ea: `0x180004afc`
- end: `0x18000545c`
- name: `?ProcessSsiElements@SSI_INCLUDE_FILE@@AEAAJPEAH@Z`
- size: `2400`
- prototype: `__int64 __fastcall(SSI_INCLUDE_FILE *__hidden this, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1800042fc`

## callees

- `0x18000395c`
- `0x180003a34`
- `0x180003c24`
- `0x180003d8c`
- `0x180003e9c`
- `0x180003fac`
- `0x1800040ec`
- `0x18000474c`
- `0x180004998`
- `0x180004afc`
- `0x1800054e4`
- `0x180005548`
- `0x18000559c`
- `0x18000574a`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180004eeb`
- `msvcrt!_strnicmp` at `0x180004f19`
- `msvcrt!_strnicmp` at `0x18000516e`
- `msvcrt!_strnicmp` at `0x180004eeb`
- `msvcrt!_strnicmp` at `0x180004f19`
- `msvcrt!_strnicmp` at `0x18000516e`
- `msvcrt!_ultoa_s` at `0x180004d14`
- `msvcrt!_ultoa_s` at `0x180005020`
- `msvcrt!_ultoa_s` at `0x1800050c1`
- `msvcrt!_ultoa_s` at `0x180005321`
- `msvcrt!_ultoa_s` at `0x180004d14`
- `msvcrt!_ultoa_s` at `0x180005020`
- `msvcrt!_ultoa_s` at `0x1800050c1`
- `msvcrt!_ultoa_s` at `0x180005321`
- `msvcrt!_wcsicmp` at `0x180005349`
- `msvcrt!_wcsicmp` at `0x180005349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ead`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800051ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800051ff`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180004f44`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180004f44`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180004f7e`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180004f7e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004c6d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800053ca`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000540d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000542a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004c6d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800053ca`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000540d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000542a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004d50`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004e88`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004d50`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004e88`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004daf`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004f5e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004daf`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004f5e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b5d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800052b8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004b5d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800052b8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004ce9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004ce9`

## pseudocode

```c
__int64 __fastcall SSI_INCLUDE_FILE::ProcessSsiElements(SSI_INCLUDE_FILE *this, int *a2)
{
  int *v2; // r13
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 *v6; // rax
  __int64 v7; // r12
  __int64 v8; // rax
  __int64 v9; // rdi
  int v10; // ecx
  unsigned int v11; // esi
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rsi
  __int64 v20; // rcx
  unsigned int v21; // r14d
  __int64 v22; // rax
  int v23; // eax
  unsigned int v24; // edi
  void *v26; // rax
  int v27; // eax
  __int64 v28; // rax
  DWORD LastError; // ecx
  _QWORD *v30; // r14
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // r15d
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // r8
  unsigned int v38; // edx
  int v39; // eax
  signed int v40; // r10d
  signed int v41; // r10d
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r14
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int StringUnescaped; // eax
  struct STRU *v51; // rdx
  signed int FullPath; // r10d
  SSI_INCLUDE_FILE *v53; // rsi
  struct SSI_REQUEST *v54; // r8
  __int64 v55; // rax
  _QWORD *v56; // rdx
  __int64 *v57; // rax
  __int64 v58; // r8
  char *v59[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v60; // [rsp+50h] [rbp-B0h] BYREF
  int *v61; // [rsp+58h] [rbp-A8h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v63[32]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-70h]
  _BYTE v65[32]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h]
  unsigned int v67; // [rsp+D8h] [rbp-28h]
  char v68[56]; // [rsp+E0h] [rbp-20h] BYREF
  char Buffer[40]; // [rsp+118h] [rbp+18h] BYREF
  char v70[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v71[136]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v72[136]; // [rsp+290h] [rbp+190h] BYREF

  v2 = a2;
  v61 = a2;
  memset_0(v71, 0, 0x102u);
  STRU::STRU((STRU *)v63, v71, 0x81u);
  v4 = *((_QWORD *)this + 4);
  *(_OWORD *)v59 = 0;
  v5 = *(_QWORD *)(v4 + 32);
  if ( v5 )
  {
    v6 = (__int64 *)*((_QWORD *)this + 5);
    v7 = v5 + 8;
    if ( !v6 )
    {
      *((_QWORD *)this + 5) = v7;
      v6 = (__int64 *)(v5 + 8);
    }
    while ( 1 )
    {
      v8 = *v6;
      *((_QWORD *)this + 5) = v8;
      if ( v8 == v7 )
        goto LABEL_126;
      v9 = v8 - 32;
      *(_OWORD *)v59 = 0;
      v10 = *(_DWORD *)(v8 - 32 + 4);
      v11 = 0;
      if ( !v10 )
      {
        if ( *(_DWORD *)(v9 + 8) <= 1u )
        {
          memset_0(v72, 0, 0x102u);
          STRU::STRU((STRU *)v68, v72, 0x81u);
          FullPath = SSI_INCLUDE_FILE::GetFullPath(
                       (SSI_REQUEST **)this,
                       (struct SSI_ELEMENT_ITEM *)v9,
                       (struct STRU *)v63,
                       1,
                       (const unsigned __int16 **)this + 46,
                       (struct STRU *)v68);
          if ( FullPath >= 0 )
          {
            v53 = this;
            do
            {
              if ( !_wcsicmp(String1, *((const wchar_t **)v53 + 10)) )
              {
                v11 = -1073739306;
                v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
                v59[1] = 0;
                goto LABEL_121;
              }
              v53 = (SSI_INCLUDE_FILE *)*((_QWORD *)v53 + 3);
            }
            while ( v53 );
            v54 = (struct SSI_REQUEST *)*((_QWORD *)this + 2);
            *(_QWORD *)&SystemTime.wYear = 0;
            FullPath = SSI_INCLUDE_FILE::CreateInstance(
                         (struct STRU *)v63,
                         (struct STRU *)v68,
                         v54,
                         this,
                         (struct SSI_INCLUDE_FILE **)&SystemTime);
            if ( FullPath < 0 )
              goto LABEL_109;
            v55 = *((_QWORD *)this + 2);
            v56 = *(_QWORD **)&SystemTime.wYear;
            *(_QWORD *)(v55 + 792) = *(_QWORD *)&SystemTime.wYear;
            v57 = (__int64 *)(v55 + 1104);
            v58 = *v57;
            if ( *(__int64 **)(*v57 + 8) != v57 )
              __fastfail(3u);
            *v56 = v58;
            v56[1] = v57;
            *(_QWORD *)(v58 + 8) = v56;
            *v57 = (__int64)v56;
            *((_DWORD *)this + 171) = 3;
            STRU::~STRU((STRU *)v68);
            goto LABEL_125;
          }
LABEL_109:
          v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
          if ( (FullPath & 0x1FFF0000) == 0x70000 )
            FullPath = (unsigned __int16)FullPath;
          if ( !_ultoa_s(FullPath, Buffer, 0x20u, 10) )
            v59[1] = Buffer;
          v11 = -1073739323;
LABEL_121:
          STRU::~STRU((STRU *)v68);
          goto LABEL_122;
        }
        goto LABEL_48;
      }
      v12 = v10 - 1;
      if ( !v12 )
        break;
      v13 = v12 - 1;
      if ( !v13 )
      {
        if ( *(_DWORD *)(v9 + 8) <= 1u )
        {
          v41 = SSI_INCLUDE_FILE::GetFullPath(
                  (SSI_REQUEST **)this,
                  (struct SSI_ELEMENT_ITEM *)v9,
                  (struct STRU *)v63,
                  0,
                  (const unsigned __int16 **)this + 46,
                  0);
          if ( v41 >= 0 )
          {
            v41 = SSI_INCLUDE_FILE::DoFSize(this, (struct STRU *)v63);
            if ( v41 >= 0 )
              goto LABEL_123;
          }
          v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
          if ( (v41 & 0x1FFF0000) == 0x70000 )
            v41 = (unsigned __int16)v41;
          if ( !_ultoa_s(v41, Buffer, 0x20u, 10) )
            v59[1] = Buffer;
          v11 = -1073739320;
          goto LABEL_122;
        }
        goto LABEL_48;
      }
      v14 = v13 - 1;
      if ( !v14 )
      {
        if ( *(_DWORD *)(v9 + 8) <= 1u )
        {
          v40 = SSI_INCLUDE_FILE::GetFullPath(
                  (SSI_REQUEST **)this,
                  (struct SSI_ELEMENT_ITEM *)v9,
                  (struct STRU *)v63,
                  0,
                  (const unsigned __int16 **)this + 46,
                  0);
          if ( v40 >= 0 )
          {
            v40 = SSI_INCLUDE_FILE::DoFLastMod(this, (struct STRU *)v63);
            if ( v40 >= 0 )
              goto LABEL_123;
          }
          v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
          if ( (v40 & 0x1FFF0000) == 0x70000 )
            v40 = (unsigned __int16)v40;
          if ( !_ultoa_s(v40, Buffer, 0x20u, 10) )
            v59[1] = Buffer;
          v11 = -1073739321;
          goto LABEL_122;
        }
        goto LABEL_48;
      }
      v15 = v14 - 1;
      if ( !v15 )
      {
        switch ( *(_DWORD *)(v9 + 8) )
        {
          case 6:
            if ( (int)STRA::Copy((STRA *)(*((_QWORD *)this + 2) + 656LL), *(const struct STRA **)(v9 + 16)) >= 0 )
              goto LABEL_123;
            v11 = -1073739322;
LABEL_63:
            if ( !v11 )
              goto LABEL_123;
            goto LABEL_122;
          case 7:
            v38 = *(_DWORD *)(*(_QWORD *)(v9 + 16) + 48LL);
            if ( !v38 || (int)STRA::Resize((SSI_INCLUDE_FILE *)((char *)this + 704), v38) < 0 )
              v11 = -1073739322;
            v39 = STRA::Copy((SSI_INCLUDE_FILE *)((char *)this + 704), *(const char **)(*(_QWORD *)(v9 + 16) + 32LL));
            if ( v39 < 0 )
            {
LABEL_60:
              v24 = v39;
LABEL_20:
              STRU::~STRU((STRU *)v63);
              return v24;
            }
            goto LABEL_63;
          case 8:
            if ( !_strnicmp("bytes", *(const char **)(*(_QWORD *)(v9 + 16) + 32LL), 6u) )
            {
              *((_DWORD *)this + 174) = 1;
              goto LABEL_123;
            }
            if ( !_strnicmp("abbrev", *(const char **)(*(_QWORD *)(v9 + 16) + 32LL), 7u) )
            {
              *((_DWORD *)this + 174) = 0;
              goto LABEL_123;
            }
            break;
        }
LABEL_48:
        v11 = -1073739322;
LABEL_122:
        v39 = SSI_REQUEST::SSISendError(*((SSI_REQUEST **)this + 2), v11, v59);
        if ( v39 < 0 )
          goto LABEL_60;
        goto LABEL_123;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        if ( (unsigned int)SSI_REQUEST::IsExecDisabled(*((SSI_REQUEST **)this + 2)) )
        {
          v11 = -1073739307;
          goto LABEL_122;
        }
        v27 = *(_DWORD *)(v9 + 8);
        if ( v27 == 3 )
        {
          v11 = -1073739308;
          goto LABEL_122;
        }
        if ( (unsigned int)(v27 - 4) <= 1 )
        {
          STRA::STRA((STRA *)v65, v70, 0x40u);
          v28 = *(_QWORD *)(v9 + 16);
          if ( **(_BYTE **)(v28 + 32) )
          {
            v30 = (_QWORD *)((char *)this + 688);
            v31 = *((_QWORD *)this + 86);
            if ( v31 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 256LL))(v31);
              *v30 = 0;
            }
            if ( (*(int (__fastcall **)(_QWORD, __int64, char *))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 248LL))(
                   *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                   27,
                   (char *)this + 688) >= 0
              && (int)STRA::Copy((STRA *)v65, *(const char **)(*(_QWORD *)(v9 + 16) + 32LL)) >= 0 )
            {
              v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 24LL))(*v30);
              v33 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v32 + 80LL))(
                      v32,
                      v66,
                      v67,
                      1);
              v34 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 24LL))(*v30);
              if ( *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34) + 36) != 5 )
              {
                v35 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 24LL))(*v30);
                *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35) + 36) = 4;
              }
              if ( v33 >= 0 )
              {
                v36 = *((_QWORD *)this + 2);
                v37 = *v30;
                *((_DWORD *)this + 171) = 2;
                if ( (*(int (__fastcall **)(_QWORD, __int64, __int64, __int64, _QWORD, _QWORD))(**(_QWORD **)(v36 + 8)
                                                                                              + 104LL))(
                       *(_QWORD *)(v36 + 8),
                       1,
                       v37,
                       41,
                       0,
                       0) >= 0 )
                {
                  *v2 = 1;
                  STRA::~STRA((STRA *)v65);
LABEL_125:
                  v24 = 0;
                  goto LABEL_20;
                }
              }
            }
            *((_DWORD *)this + 171) = 4;
            v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
            LastError = GetLastError();
          }
          else
          {
            v59[0] = *(char **)(v28 + 32);
            LastError = 123;
          }
          if ( !_ultoa_s(LastError, Buffer, 0x20u, 10) )
            v59[1] = Buffer;
          switch ( *(_DWORD *)(v9 + 8) )
          {
            case 3:
              v11 = -1073739314;
              break;
            case 4:
              v11 = -1073739313;
              break;
            case 5:
              v11 = -1073739312;
              break;
          }
          STRA::~STRA((STRA *)v65);
          goto LABEL_63;
        }
        goto LABEL_48;
      }
      if ( v16 != 1 )
      {
        v11 = -1073739317;
        goto LABEL_122;
      }
      v17 = *((_QWORD *)this + 4);
      v18 = *(_QWORD *)(v17 + 24);
      if ( !v18 )
        v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v17 + 16) + 72LL))(*(_QWORD *)(v17 + 16));
      v19 = *((_QWORD *)this + 2);
      if ( v18 )
      {
        v20 = *((_QWORD *)this + 4);
        v21 = *(_DWORD *)(v9 + 28);
        v22 = *(_QWORD *)(v20 + 24);
        if ( !v22 )
          v22 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 16) + 72LL))(*(_QWORD *)(v20 + 16));
        v23 = SSI_VECTOR_BUFFER::AddToVector(
                (SSI_VECTOR_BUFFER *)(v19 + 800),
                (char *)(v22 + *(unsigned int *)(v9 + 24)),
                v21);
      }
      else
      {
        v26 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 4) + 16LL) + 80LL))(*(_QWORD *)(*((_QWORD *)this + 4) + 16LL));
        v23 = SSI_VECTOR_BUFFER::AddFileChunkToVector(
                (SSI_VECTOR_BUFFER *)(v19 + 800),
                *(_DWORD *)(v9 + 24),
                *(_DWORD *)(v9 + 28),
                v26);
      }
      v24 = v23;
      if ( v23 < 0 )
        goto LABEL_20;
LABEL_123:
      v6 = (__int64 *)*((_QWORD *)this + 5);
    }
    if ( *(_DWORD *)(v9 + 8) != 2 )
      goto LABEL_48;
    v42 = *((_QWORD *)this + 2);
    v43 = *(_QWORD *)(v9 + 16);
    *(_QWORD *)&SystemTime.wYear = 0;
    v60 = 0;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, struct _SYSTEMTIME *, unsigned int *))(**(_QWORD **)(v42 + 8) + 120LL))(
           *(_QWORD *)(v42 + 8),
           *(_QWORD *)(v43 + 32),
           &SystemTime,
           &v60) >= 0
      && (!v60
       || (int)SSI_VECTOR_BUFFER::AddToVector(
                 (SSI_VECTOR_BUFFER *)(*((_QWORD *)this + 2) + 800LL),
                 *(char **)&SystemTime.wYear,
                 v60) >= 0) )
    {
      goto LABEL_123;
    }
    v44 = *(_QWORD *)(v9 + 16);
    if ( SSIVarMap )
    {
      do
      {
        if ( !_strnicmp(
                (const char *)*(&SSIVarMap + 2 * v11),
                *(const char **)(v44 + 32),
                *((unsigned int *)&SSIVarMap + 4 * v11 + 2)) )
          break;
        ++v11;
      }
      while ( *(&SSIVarMap + 2 * v11) );
      v2 = v61;
    }
    if ( !*(&SSIVarMap + 2 * v11) )
    {
      v11 = -1073739319;
      v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
      v59[1] = 0;
      goto LABEL_122;
    }
    v45 = *((_DWORD *)&SSIVarMap + 4 * v11 + 3);
    if ( v45 )
    {
      v46 = v45 - 1;
      if ( v46 )
      {
        v47 = v46 - 1;
        if ( v47 )
        {
          v48 = v47 - 1;
          if ( v48 )
          {
            v49 = v48 - 1;
            if ( v49 )
            {
              if ( v49 != 1 )
              {
                v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
                v59[1] = 0;
LABEL_105:
                v11 = -1073739318;
                v59[0] = *(char **)(*(_QWORD *)(v9 + 16) + 32LL);
                v59[1] = 0;
                goto LABEL_122;
              }
              StringUnescaped = SSI_INCLUDE_FILE::DoFLastMod(this, (SSI_INCLUDE_FILE *)((char *)this + 48));
            }
            else
            {
              StringUnescaped = SSI_INCLUDE_FILE::DoEchoDateGMT(this);
            }
          }
          else
          {
            SystemTime = 0;
            GetLocalTime(&SystemTime);
            StringUnescaped = SSI_REQUEST::SendDate(
                                *((SSI_REQUEST **)this + 2),
                                &SystemTime,
                                (SSI_INCLUDE_FILE *)((char *)this + 704));
          }
        }
        else
        {
          StringUnescaped = SSI_INCLUDE_FILE::DoEchoQueryStringUnescaped(this);
        }
LABEL_104:
        if ( StringUnescaped >= 0 )
          goto LABEL_123;
        goto LABEL_105;
      }
      v51 = (SSI_INCLUDE_FILE *)((char *)this + 368);
    }
    else
    {
      v51 = (SSI_INCLUDE_FILE *)((char *)this + 48);
    }
    StringUnescaped = SSI_VECTOR_BUFFER::CopyToVector((SSI_VECTOR_BUFFER *)(*((_QWORD *)this + 2) + 800LL), v51);
    goto LABEL_104;
  }
LABEL_126:
  *((_DWORD *)this + 171) = 5;
  STRU::~STRU((STRU *)v63);
  return 0;
}

```

## disassembly

```asm
0x180004afc  mov     [rsp-8+arg_10], rbx
0x180004b01  push    rbp
0x180004b02  push    rsi
0x180004b03  push    rdi
0x180004b04  push    r12
0x180004b06  push    r13
0x180004b08  push    r14
0x180004b0a  push    r15
0x180004b0c  lea     rbp, [rsp-2B0h]
0x180004b14  sub     rsp, 3B0h
0x180004b1b  mov     rax, cs:__security_cookie
0x180004b22  xor     rax, rsp
0x180004b25  mov     [rbp+2E0h+var_40], rax
0x180004b2c  mov     r13, rdx
0x180004b2f  mov     [rsp+3E0h+var_388], rdx
0x180004b34  mov     rbx, rcx
0x180004b37  xor     edx, edx; Val
0x180004b39  lea     rcx, [rbp+2E0h+var_260]; void *
0x180004b40  mov     r8d, 102h; Size
0x180004b46  call    memset_0
0x180004b4b  mov     r8d, 81h
0x180004b51  lea     rdx, [rbp+2E0h+var_260]
0x180004b58  lea     rcx, [rsp+3E0h+var_370]
0x180004b5d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004b63  mov     rax, [rbx+20h]
0x180004b67  xorps   xmm0, xmm0
0x180004b6a  movups  xmmword ptr [rsp+3E0h+var_3A0], xmm0
0x180004b6f  xor     r15d, r15d
0x180004b72  mov     rcx, [rax+20h]
0x180004b76  test    rcx, rcx
0x180004b79  jz      loc_18000541B
0x180004b7f  mov     rax, [rbx+28h]
0x180004b83  lea     r12, [rcx+8]
0x180004b87  test    rax, rax
0x180004b8a  jnz     short loc_180004B93
0x180004b8c  mov     [rbx+28h], r12
0x180004b90  mov     rax, r12
0x180004b93  mov     rax, [rax]
0x180004b96  mov     [rbx+28h], rax
0x180004b9a  cmp     rax, r12
0x180004b9d  jz      loc_18000541B
0x180004ba3  lea     rcx, [rsp+3E0h+var_3A0]
0x180004ba8  xorps   xmm0, xmm0
0x180004bab  lea     rdi, [rax-20h]
0x180004baf  mov     r14d, 0C00009C6h
0x180004bb5  movups  xmmword ptr [rcx], xmm0
0x180004bb8  mov     ecx, [rdi+4]
0x180004bbb  mov     esi, r15d
0x180004bbe  test    ecx, ecx
0x180004bc0  jz      loc_180005283
0x180004bc6  sub     ecx, 1
0x180004bc9  jz      loc_1800050DE
0x180004bcf  sub     ecx, 1
0x180004bd2  jz      loc_18000503D
0x180004bd8  sub     ecx, 1
0x180004bdb  jz      loc_180004F9C
0x180004be1  sub     ecx, 1
0x180004be4  jz      loc_180004EC2
0x180004bea  sub     ecx, 1
0x180004bed  jz      loc_180004CA6
0x180004bf3  cmp     ecx, 1
0x180004bf6  jz      short loc_180004C02
0x180004bf8  mov     esi, 0C00009CBh
0x180004bfd  jmp     loc_1800053D0
0x180004c02  mov     rcx, [rbx+20h]
0x180004c06  mov     rax, [rcx+18h]
0x180004c0a  test    rax, rax
0x180004c0d  jnz     short loc_180004C1F
0x180004c0f  mov     rcx, [rcx+10h]
0x180004c13  mov     rax, [rcx]
0x180004c16  mov     rax, [rax+48h]
0x180004c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1f  mov     rsi, [rbx+10h]
0x180004c23  test    rax, rax
0x180004c26  jz      short loc_180004C7A
0x180004c28  mov     rcx, [rbx+20h]
0x180004c2c  mov     r14d, [rdi+1Ch]
0x180004c30  mov     rax, [rcx+18h]
0x180004c34  test    rax, rax
0x180004c37  jnz     short loc_180004C49
0x180004c39  mov     rcx, [rcx+10h]
0x180004c3d  mov     rax, [rcx]
0x180004c40  mov     rax, [rax+48h]
0x180004c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c49  mov     edx, [rdi+18h]
0x180004c4c  lea     rcx, [rsi+320h]; this
0x180004c53  add     rdx, rax; char *
0x180004c56  mov     r8d, r14d; unsigned int
0x180004c59  call    ?AddToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::AddToVector(char *,ulong)
0x180004c5e  mov     edi, eax
0x180004c60  test    eax, eax
0x180004c62  jns     loc_1800053E8
0x180004c68  lea     rcx, [rsp+3E0h+var_370]
0x180004c6d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004c73  mov     eax, edi
0x180004c75  jmp     loc_180005432
0x180004c7a  mov     rax, [rbx+20h]
0x180004c7e  mov     rcx, [rax+10h]
0x180004c82  mov     rax, [rcx]
0x180004c85  mov     rax, [rax+50h]
0x180004c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c8e  mov     r8d, [rdi+1Ch]; unsigned int
0x180004c92  lea     rcx, [rsi+320h]; this
0x180004c99  mov     edx, [rdi+18h]; unsigned int
0x180004c9c  mov     r9, rax; void *
0x180004c9f  call    ?AddFileChunkToVector@SSI_VECTOR_BUFFER@@QEAAJKKPEAX@Z; SSI_VECTOR_BUFFER::AddFileChunkToVector(ulong,ulong,void *)
0x180004ca4  jmp     short loc_180004C5E
0x180004ca6  mov     rcx, [rbx+10h]; this
0x180004caa  call    ?IsExecDisabled@SSI_REQUEST@@QEAAHXZ; SSI_REQUEST::IsExecDisabled(void)
0x180004caf  test    eax, eax
0x180004cb1  jz      short loc_180004CBD
0x180004cb3  mov     esi, 0C00009D5h
0x180004cb8  jmp     loc_1800053D0
0x180004cbd  mov     eax, [rdi+8]
0x180004cc0  cmp     eax, 3
0x180004cc3  jnz     short loc_180004CCF
0x180004cc5  mov     esi, 0C00009D4h
0x180004cca  jmp     loc_1800053D0
0x180004ccf  add     eax, 0FFFFFFFCh
0x180004cd2  cmp     eax, 1
0x180004cd5  ja      loc_180004EBA
0x180004cdb  mov     r8d, 40h ; '@'
0x180004ce1  lea     rdx, [rbp+2E0h+var_2A0]
0x180004ce5  lea     rcx, [rbp+2E0h+var_338]
0x180004ce9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180004cef  mov     rax, [rdi+10h]
0x180004cf3  mov     rcx, [rax+20h]
0x180004cf7  cmp     [rcx], r15b
0x180004cfa  jnz     short loc_180004D5B
0x180004cfc  mov     [rsp+3E0h+var_3A0], rcx
0x180004d01  mov     ecx, 7Bh ; '{'; Value
0x180004d06  mov     r9d, 0Ah; Radix
0x180004d0c  lea     rdx, [rbp+2E0h+Buffer]; Buffer
0x180004d10  lea     r8d, [r9+16h]; BufferCount
0x180004d14  call    cs:__imp__ultoa_s
0x180004d1a  test    eax, eax
0x180004d1c  jnz     short loc_180004D27
0x180004d1e  lea     rax, [rbp+2E0h+Buffer]
0x180004d22  mov     [rsp+3E0h+var_3A0+8], rax
0x180004d27  mov     ecx, [rdi+8]
0x180004d2a  sub     ecx, 3
0x180004d2d  jz      short loc_180004D47
0x180004d2f  sub     ecx, 1
0x180004d32  jz      short loc_180004D40
0x180004d34  cmp     ecx, 1
0x180004d37  jnz     short loc_180004D4C
0x180004d39  mov     esi, 0C00009D0h
0x180004d3e  jmp     short loc_180004D4C
0x180004d40  mov     esi, 0C00009CFh
0x180004d45  jmp     short loc_180004D4C
0x180004d47  mov     esi, 0C00009CEh
0x180004d4c  lea     rcx, [rbp+2E0h+var_338]
0x180004d50  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004d56  jmp     loc_180004F8F
0x180004d5b  lea     r14, [rbx+2B0h]
0x180004d62  mov     rcx, [r14]
0x180004d65  test    rcx, rcx
0x180004d68  jz      short loc_180004D7C
0x180004d6a  mov     rax, [rcx]
0x180004d6d  mov     rax, [rax+100h]
0x180004d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d79  mov     [r14], r15
0x180004d7c  mov     rax, [rbx+10h]
0x180004d80  mov     r8, r14
0x180004d83  mov     edx, 1Bh
0x180004d88  mov     rcx, [rax+8]
0x180004d8c  mov     rax, [rcx]
0x180004d8f  mov     rax, [rax+0F8h]
0x180004d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9b  test    eax, eax
0x180004d9d  js      loc_180004E96
0x180004da3  mov     rdx, [rdi+10h]
0x180004da7  lea     rcx, [rbp+2E0h+var_338]
0x180004dab  mov     rdx, [rdx+20h]
0x180004daf  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004db5  test    eax, eax
0x180004db7  js      loc_180004E96
0x180004dbd  mov     rcx, [r14]
0x180004dc0  mov     rax, [rcx]
0x180004dc3  mov     rax, [rax+18h]
0x180004dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dcc  mov     r8d, [rbp+2E0h+var_308]
0x180004dd0  mov     r10, rax
0x180004dd3  mov     rdx, [rbp+2E0h+var_318]
0x180004dd7  mov     r9d, 1
0x180004ddd  mov     rcx, [rax]
0x180004de0  mov     rax, [rcx+50h]
0x180004de4  mov     rcx, r10
0x180004de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dec  mov     rcx, [r14]
0x180004def  mov     r15d, eax
0x180004df2  mov     rdx, [rcx]
0x180004df5  mov     rax, [rdx+18h]
0x180004df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dfe  mov     rdx, rax
0x180004e01  mov     rcx, [rax]
0x180004e04  mov     rax, [rcx+8]
0x180004e08  mov     rcx, rdx
0x180004e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e10  cmp     dword ptr [rax+24h], 5
0x180004e14  jz      short loc_180004E3E
0x180004e16  mov     rcx, [r14]
0x180004e19  mov     rax, [rcx]
0x180004e1c  mov     rax, [rax+18h]
0x180004e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e25  mov     rdx, rax
0x180004e28  mov     rcx, [rax]
0x180004e2b  mov     rax, [rcx+8]
0x180004e2f  mov     rcx, rdx
0x180004e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e37  mov     dword ptr [rax+24h], 4
0x180004e3e  test    r15d, r15d
0x180004e41  js      short loc_180004E93
0x180004e43  mov     rax, [rbx+10h]
0x180004e47  xor     r15d, r15d
0x180004e4a  mov     r8, [r14]
0x180004e4d  mov     dword ptr [rbx+2ACh], 2
0x180004e57  mov     [rsp+3E0h+var_3B8], r15
0x180004e5c  mov     rcx, [rax+8]
0x180004e60  lea     r14d, [r15+1]
0x180004e64  lea     r9d, [r15+29h]
0x180004e68  mov     [rsp+3E0h+var_3C0], r15
0x180004e6d  mov     edx, r14d
0x180004e70  mov     rax, [rcx]
0x180004e73  mov     rax, [rax+68h]
0x180004e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e7c  test    eax, eax
0x180004e7e  js      short loc_180004E96
0x180004e80  lea     rcx, [rbp+2E0h+var_338]
0x180004e84  mov     [r13+0], r14d
0x180004e88  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004e8e  jmp     loc_180005413
0x180004e93  xor     r15d, r15d
0x180004e96  mov     dword ptr [rbx+2ACh], 4
0x180004ea0  mov     rax, [rdi+10h]
0x180004ea4  mov     rcx, [rax+20h]
0x180004ea8  mov     [rsp+3E0h+var_3A0], rcx
0x180004ead  call    cs:__imp_GetLastError
0x180004eb3  mov     ecx, eax
0x180004eb5  jmp     loc_180004D06
0x180004eba  mov     esi, r14d
0x180004ebd  jmp     loc_1800053D0
0x180004ec2  mov     ecx, [rdi+8]
0x180004ec5  sub     ecx, 6
0x180004ec8  jz      loc_180004F6F
0x180004ece  sub     ecx, 1
0x180004ed1  jz      short loc_180004F2F
0x180004ed3  cmp     ecx, 1
0x180004ed6  jnz     short loc_180004EBA
0x180004ed8  mov     rdx, [rdi+10h]
0x180004edc  lea     r8d, [rcx+5]; MaxCount
0x180004ee0  lea     rcx, String1; "bytes"
0x180004ee7  mov     rdx, [rdx+20h]; String2
0x180004eeb  call    cs:__imp__strnicmp
0x180004ef1  test    eax, eax
0x180004ef3  jnz     short loc_180004F04
0x180004ef5  mov     dword ptr [rbx+2B8h], 1
0x180004eff  jmp     loc_1800053E8
0x180004f04  mov     rdx, [rdi+10h]
0x180004f08  lea     rcx, aAbbrev; "abbrev"
0x180004f0f  mov     r8d, 7; MaxCount
0x180004f15  mov     rdx, [rdx+20h]; String2
0x180004f19  call    cs:__imp__strnicmp
0x180004f1f  test    eax, eax
0x180004f21  jnz     short loc_180004EBA
0x180004f23  mov     [rbx+2B8h], r15d
0x180004f2a  jmp     loc_1800053E8
0x180004f2f  mov     rax, [rdi+10h]
0x180004f33  lea     r14, [rbx+2C0h]
0x180004f3a  mov     edx, [rax+30h]
0x180004f3d  test    edx, edx
0x180004f3f  jz      short loc_180004F4E
0x180004f41  mov     rcx, r14
0x180004f44  call    cs:__imp_?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180004f4a  test    eax, eax
0x180004f4c  jns     short loc_180004F53
0x180004f4e  mov     esi, 0C00009C6h
0x180004f53  mov     rdx, [rdi+10h]
0x180004f57  mov     rcx, r14
0x180004f5a  mov     rdx, [rdx+20h]
0x180004f5e  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004f64  test    eax, eax
0x180004f66  jns     short loc_180004F8F
0x180004f68  mov     edi, eax
0x180004f6a  jmp     loc_180004C68
0x180004f6f  mov     rcx, [rbx+10h]
0x180004f73  mov     rdx, [rdi+10h]
0x180004f77  add     rcx, 290h
0x180004f7e  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x180004f84  test    eax, eax
0x180004f86  jns     loc_1800053E8
0x180004f8c  mov     esi, r14d
0x180004f8f  test    esi, esi
0x180004f91  jz      loc_1800053E8
0x180004f97  jmp     loc_1800053D0
0x180004f9c  mov     ecx, [rdi+8]
0x180004f9f  test    ecx, ecx
0x180004fa1  jz      short loc_180004FAC
0x180004fa3  cmp     ecx, 1
0x180004fa6  jnz     loc_180004EBA
  ... truncated ...
```
