# ProblemInstance::Diagnose(long *,bool)

- ea: `0x180012b44`
- end: `0x18001371b`
- name: `?Diagnose@ProblemInstance@@QEAA?AW4tagDIAGNOSIS_STATUS@@PEAJ_N@Z`
- size: `3031`
- prototype: `__int64 __fastcall(ProblemInstance *this, int *, unsigned __int8)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a3e8`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x18000bca0`
- `0x18000c42c`
- `0x1800103e0`
- `0x1800121a8`
- `0x180012b44`
- `0x180013794`
- `0x1800144a8`
- `0x180015308`
- `0x18001b3a8`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180012ddc`
- `msvcrt!wcsnlen` at `0x180012ddc`
- `KERNEL32!CompareFileTime` at `0x180012f87`
- `KERNEL32!CompareFileTime` at `0x180012fa1`
- `KERNEL32!CompareFileTime` at `0x180012f87`
- `KERNEL32!CompareFileTime` at `0x180012fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001367c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001367c`

## pseudocode

```c
__int64 __fastcall ProblemInstance::Diagnose(ProblemInstance *this, int *a2, unsigned __int8 a3)
{
  __int64 v3; // r13
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // r15
  __int64 v9; // r12
  int v10; // r15d
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r12
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rcx
  int v25; // ebx
  __int64 v26; // r8
  wchar_t *v27; // rax
  bool v28; // zf
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rbx
  __int64 v32; // r8
  __int64 v33; // rcx
  tagDIAGNOSIS_STATUS v34; // ecx
  __int32 v35; // ecx
  __int32 v36; // ecx
  __int32 v37; // ecx
  int v38; // ecx
  __int64 *v39; // rcx
  __int64 v40; // rax
  unsigned int v41; // ebx
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  _QWORD *v45; // rax
  unsigned __int64 v46; // rbx
  unsigned __int64 v47; // r12
  unsigned __int16 *DiagnosisStatusString; // rax
  __int64 v49; // rdx
  int v50; // r10d
  int v51; // r11d
  const wchar_t *v52; // r9
  __int64 v53; // r8
  __int64 v54; // rbx
  _QWORD *v55; // rdi
  _QWORD *v56; // rax
  const unsigned __int16 *v57; // rcx
  __int64 v58; // r8
  __int64 v59; // rbx
  _QWORD *v60; // rdi
  _QWORD *v61; // rax
  const unsigned __int16 *v62; // rcx
  __int64 v63; // r8
  __int64 v64; // rbx
  int v65; // ebx
  __int64 v66; // r8
  _QWORD *v67; // rdi
  _QWORD *v68; // rax
  const unsigned __int16 *v69; // rcx
  __int64 v70; // r8
  __int64 v71; // rbx
  _QWORD *v72; // rdi
  _QWORD *v73; // rax
  const unsigned __int16 *v74; // rcx
  __int64 v75; // r8
  __int64 v76; // rbx
  int v77; // ebx
  __int64 v78; // r8
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // rdx
  unsigned int *TickCount; // rax
  signed __int64 v83; // r8
  int v84; // ecx
  __int64 v85; // [rsp+20h] [rbp-79h]
  unsigned int v87; // [rsp+54h] [rbp-45h] BYREF
  tagDIAGNOSIS_STATUS v88; // [rsp+58h] [rbp-41h] BYREF
  __int64 v89; // [rsp+60h] [rbp-39h] BYREF
  __int64 v90; // [rsp+68h] [rbp-31h] BYREF
  wchar_t *Source; // [rsp+70h] [rbp-29h] BYREF
  struct NetworkDiagnosticsEngine *v92; // [rsp+78h] [rbp-21h] BYREF
  __int64 v93; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int64 v94; // [rsp+88h] [rbp-11h] BYREF
  _QWORD *v95; // [rsp+90h] [rbp-9h]
  _QWORD *v96; // [rsp+98h] [rbp-1h]
  __int128 v97; // [rsp+A0h] [rbp+7h] BYREF

  v3 = a3;
  v88 = DS_REJECTED;
  Source = 0;
  v97 = 0u;
  v92 = NetworkDiagnosticsEngine::Instance();
  if ( !v92 )
    return 3;
  v96 = (_QWORD *)((char *)this + 192);
  v95 = (_QWORD *)((char *)this + 184);
  if ( (_BYTE)v3 )
  {
    v6 = *((_QWORD *)this + 23);
    v7 = 96;
    v8 = 200;
  }
  else
  {
    v6 = *((_QWORD *)this + 24);
    v7 = 100;
    v8 = 204;
    v95 = (_QWORD *)((char *)this + 184);
    v96 = (_QWORD *)((char *)this + 192);
  }
  v9 = *((_QWORD *)this + (v3 ^ 1) + 23);
  v89 = v9;
  v10 = *(_DWORD *)((char *)this + v8);
  v11 = *(_DWORD *)((char *)this + v7);
  LODWORD(v90) = v11;
  if ( *((_QWORD *)this + 36) && (_BYTE)v3 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v93);
    v12 = *((_QWORD *)this + 2);
    if ( !*(_DWORD *)(v12 - 16) )
      v12 = *(_QWORD *)this;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v93,
      L"Diagnose %s (v%s). LowHealth : initial state %d",
      v12,
      *((_QWORD *)this + 1),
      v11);
    v13 = v93;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 36) + 112LL))(
      *((_QWORD *)this + 36),
      0,
      v93,
      *((_QWORD *)this + 5));
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
    v11 = v90;
  }
  switch ( v11 )
  {
    case 1:
      TickCount = (unsigned int *)ATL::CFileTime::GetTickCount(&v94);
      v83 = (*TickCount | ((unsigned __int64)TickCount[1] << 32))
          - ((unsigned int)v9 | ((unsigned __int64)HIDWORD(v89) << 32));
      if ( v83 > 0x7FFFFFFF )
      {
        *a2 = 0;
        return 2;
      }
      v84 = 3 * *((_DWORD *)this + 56) - v83 / 0x989680uLL;
      *a2 = v84;
      if ( v84 > 0 )
        return 4;
      *a2 = 0;
      ProblemInstance::Cancel(this);
      if ( (_BYTE)v3 )
        *((_DWORD *)this + 24) = 9;
      else
        *((_DWORD *)this + 25) = 9;
      return 3;
    case 2:
      v16 = *(_QWORD *)ATL::CFileTime::GetTickCount(&v94);
      v14 = (unsigned int)v9 | ((unsigned __int64)HIDWORD(v89) << 32);
      v17 = v16 - v14;
      if ( v17 > 0x7FFFFFFF || (v18 = v10 - v17 / 0x989680uLL, *a2 = v18, v18 <= 0) )
      {
        *a2 = 0;
        goto LABEL_25;
      }
      return 4;
    case 3:
    case 4:
    case 6:
      return 1;
    case 8:
      return 2;
    case 10:
      return 1;
  }
  v14 = (unsigned int)(v11 - 11);
  if ( v11 == 11 )
    return 1;
  if ( v11 != 12 )
  {
LABEL_25:
    if ( (byte_180041BC1 & 2) != 0 )
    {
      v19 = *((_QWORD *)this + 2);
      if ( !*(_DWORD *)(v19 - 16) )
        v19 = *(_QWORD *)this;
      McTemplateU0z_EventWriteTransfer(v14, StartNDFHCDiagnose, v19);
    }
    v20 = *(_QWORD *)ATL::CFileTime::GetTickCount(&v94);
    v21 = *((_QWORD *)this + 9);
    v89 = v20;
    v22 = *((_QWORD *)this + 4);
    if ( (_BYTE)v3 )
    {
      *v95 = v20;
      *((_DWORD *)this + 24) = 1;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, int *, tagDIAGNOSIS_STATUS *))(*(_QWORD *)v21 + 24LL))(
              v21,
              v22,
              &Source,
              a2,
              &v88);
    }
    else
    {
      *v96 = v20;
      *((_DWORD *)this + 25) = 1;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, int *, tagDIAGNOSIS_STATUS *))(*(_QWORD *)v21 + 32LL))(
              v21,
              v22,
              &Source,
              a2,
              &v88);
    }
    v25 = v23;
    if ( (byte_180041BC1 & 2) != 0 )
    {
      v26 = *((_QWORD *)this + 2);
      if ( !*(_DWORD *)(v26 - 16) )
        v26 = *(_QWORD *)this;
      McTemplateU0z_EventWriteTransfer(v24, StopNDFHCDiagnose, v26);
    }
    if ( (_BYTE)v3 || v25 != -2147467263 )
      *((_DWORD *)this + 60) = v25;
    v27 = Source;
    if ( Source )
    {
      v28 = wcsnlen(Source, 0x400u) == 1024;
      v27 = Source;
      if ( v28 )
      {
        Source[1024] = 0;
        v27 = Source;
      }
    }
    if ( v25 < 0 )
    {
      if ( (_BYTE)v3 )
      {
        if ( *((_QWORD *)this + 36) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v90);
          v29 = *((_QWORD *)this + 2);
          v30 = *(_DWORD *)(v29 - 16);
          if ( v25 == -2147467263 )
          {
            if ( !v30 )
              v29 = *(_QWORD *)this;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              &v90,
              L"Diagnosis not implemented for %s.",
              v29);
          }
          else
          {
            if ( !v30 )
              v29 = *(_QWORD *)this;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              &v90,
              L"Diagnosis failed for %s with error 0x%x.",
              v29,
              (unsigned int)v25);
          }
          v31 = v90;
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 36) + 96LL))(
            *((_QWORD *)this + 36),
            0,
            v90);
          ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
          v27 = Source;
        }
        *((_DWORD *)this + 24) = 9;
        if ( v27 )
        {
          v32 = -1;
          do
            ++v32;
          while ( v27[v32] );
        }
        else
        {
          v32 = 0;
        }
        v33 = 80;
      }
      else
      {
        *((_DWORD *)this + 25) = 9;
        if ( v27 )
        {
          v32 = -1;
          do
            ++v32;
          while ( v27[v32] );
        }
        else
        {
          v32 = 0;
        }
        v33 = 88;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + v33, v27, v32);
      CoTaskMemFree(Source);
      return 3;
    }
    v94 = v20 & 0xFFFFFFFF00000000uLL;
    v34 = v88;
    if ( (unsigned int)(v88 - 1) <= 2 || v88 == DS_PASSTHROUGH )
    {
      v93 = 0;
      if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 9) + 112LL))(*((_QWORD *)this + 9), &v93) >= 0 )
        *((_QWORD *)this + 8) = v93;
      if ( (*(int (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 9) + 96LL))(*((_QWORD *)this + 9), &v97) >= 0 )
      {
        if ( CompareFileTime((const FILETIME *)this + 7, (const FILETIME *)&v97 + 1) < 0 )
          *((_QWORD *)this + 7) = *((_QWORD *)&v97 + 1);
        if ( CompareFileTime((const FILETIME *)this + 6, (const FILETIME *)&v97) > 0 )
          *((_QWORD *)this + 6) = v97;
        CProblemInstanceCache::Add(*((CProblemInstanceCache **)v92 + 6), (const FILETIME *)this);
      }
      v34 = v88;
    }
    v87 = 0;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        LODWORD(v90) = 10;
LABEL_88:
        v39 = (__int64 *)*((_QWORD *)this + 9);
        v40 = *v39;
        if ( (_BYTE)v3 )
        {
          if ( (*(int (__fastcall **)(__int64 *, unsigned int *, char *))(v40 + 40))(v39, &v87, (char *)this + 304) >= 0 )
          {
            v41 = 0;
            if ( v87 )
            {
              do
              {
                v92 = (struct NetworkDiagnosticsEngine *)(*((_QWORD *)this + 38) + 32LL * v41);
                std::list<tagHYPOTHESIS *>::push_back((char *)this + 120, &v92);
                ++v41;
              }
              while ( v41 < v87 );
              LOBYTE(v3) = a3;
            }
          }
          v87 = 0;
          if ( (*(int (__fastcall **)(_QWORD, unsigned int *, char *))(**((_QWORD **)this + 9) + 48LL))(
                 *((_QWORD *)this + 9),
                 &v87,
                 (char *)this + 312) >= 0 )
          {
            v42 = 0;
            if ( v87 )
            {
              do
              {
                v92 = (struct NetworkDiagnosticsEngine *)(*((_QWORD *)this + 39) + 32LL * v42);
                std::list<tagHYPOTHESIS *>::push_back((char *)this + 136, &v92);
                ++v42;
              }
              while ( v42 < v87 );
LABEL_108:
              LOBYTE(v3) = a3;
            }
          }
        }
        else
        {
          if ( (*(int (__fastcall **)(__int64 *, unsigned int *, char *))(v40 + 56))(v39, &v87, (char *)this + 320) >= 0 )
          {
            v43 = 0;
            if ( v87 )
            {
              do
              {
                v92 = (struct NetworkDiagnosticsEngine *)(*((_QWORD *)this + 40) + 32LL * v43);
                std::list<tagHYPOTHESIS *>::push_back((char *)this + 152, &v92);
                ++v43;
              }
              while ( v43 < v87 );
              LOBYTE(v3) = a3;
            }
          }
          v87 = 0;
          if ( (*(int (__fastcall **)(_QWORD, unsigned int *, char *))(**((_QWORD **)this + 9) + 64LL))(
                 *((_QWORD *)this + 9),
                 &v87,
                 (char *)this + 328) >= 0 )
          {
            v44 = 0;
            if ( v87 )
            {
              do
              {
                v92 = (struct NetworkDiagnosticsEngine *)(*((_QWORD *)this + 41) + 32LL * v44);
                std::list<tagHYPOTHESIS *>::push_back((char *)this + 168, &v92);
                ++v44;
              }
              while ( v44 < v87 );
              goto LABEL_108;
            }
          }
        }
LABEL_109:
        v45 = (_QWORD *)ATL::CFileTime::GetTickCount(&v92);
        v46 = (*v45 - ((unsigned int)v89 | v94)) / 0x2710;
        v47 = v46 / 0x64;
        if ( *((_QWORD *)this + 36) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v89);
          DiagnosisStatusString = GetDiagnosisStatusString(v88);
          v52 = L"LowHealth";
          if ( !(_BYTE)v3 )
            v52 = L"HighUtilization";
          v53 = *((_QWORD *)this + 2);
          if ( !*(_DWORD *)(v53 - 16) )
            v53 = *(_QWORD *)this;
          LODWORD(v85) = v50;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &v89,
            L"%s %s diagnosis status %d [%s] HRESULT %X [%d ms] description: %s",
            v53,
            v52,
            v85,
            DiagnosisStatusString,
            v51,
            v46,
            v49);
          v54 = v89;
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 36) + 96LL))(
            *((_QWORD *)this + 36),
            0,
            v89);
          ATL::CStringData::Release((ATL::CStringData *)(v54 - 24));
        }
        if ( (_BYTE)v3 )
        {
          v55 = (_QWORD *)*((_QWORD *)this + 15);
          while ( 1 )
          {
            v55 = (_QWORD *)*v55;
            if ( v55 == *((_QWORD **)this + 15) )
              break;
            if ( *((_QWORD *)this + 36) )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v89);
              v56 = (_QWORD *)v55[2];
              v57 = &dword_180033E1C;
              if ( v56[1] )
                v57 = (const unsigned __int16 *)v56[1];
              v58 = *((_QWORD *)this + 2);
              if ( !*(_DWORD *)(v58 - 16) )
                v58 = *(_QWORD *)this;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v89,
                L"%s LowHealth hypothesis %s %s",
                v58,
                *v56,
                v57);
              v59 = v89;
              (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _DWORD))(**((_QWORD **)this + 36) + 120LL))(
                *((_QWORD *)this + 36),
                1,
                v89,
                *(_QWORD *)(v55[2] + 24LL),
                *(_DWORD *)(v55[2] + 16LL));
              ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
            }
          }
          v60 = (_QWORD *)*((_QWORD *)this + 17);
          while ( 1 )
          {
            v60 = (_QWORD *)*v60;
            if ( v60 == *((_QWORD **)this + 17) )
              break;
            if ( *((_QWORD *)this + 36) )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v89);
              v61 = (_QWORD *)v60[2];
              v62 = &dword_180033E1C;
              if ( v61[1] )
                v62 = (const unsigned __int16 *)v61[1];
              v63 = *((_QWORD *)this + 2);
              if ( !*(_DWORD *)(v63 - 16) )
                v63 = *(_QWORD *)this;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v89,
                L"%s LowHealth hypothesis %s %s",
                v63,
                *v61,
                v62);
              v64 = v89;
              (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _DWORD))(**((_QWORD **)this + 36) + 120LL))(
                *((_QWORD *)this + 36),
                1,
                v89,
                *(_QWORD *)(v60[2] + 24LL),
                *(_DWORD *)(v60[2] + 16LL));
              ATL::CStringData::Release((ATL::CStringData *)(v64 - 24));
            }
          }
          v65 = v90;
          *((_DWORD *)this + 24) = v90;
          if ( Source )
          {
            v66 = -1;
            do
              ++v66;
            while ( Source[v66] );
          }
          else
          {
            v66 = 0;
          }
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 80, Source, v66);
          if ( v65 == 2 )
          {
            *v95 = v6;
            *((_DWORD *)this + 50) = v10;
            *((_DWORD *)this + 52) += v47 + 10 * v10;
LABEL_168:
            CoTaskMemFree(Source);
            return (unsigned int)v88;
          }
          *((_DWORD *)this + 52) = v47;
        }
        else
        {
          v67 = (_QWORD *)*((_QWORD *)this + 19);
          while ( 1 )
          {
            v67 = (_QWORD *)*v67;
            if ( v67 == *((_QWORD **)this + 19) )
              break;
            if ( *((_QWORD *)this + 36) )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v89);
              v68 = (_QWORD *)v67[2];
              v69 = &dword_180033E1C;
              if ( v68[1] )
                v69 = (const unsigned __int16 *)v68[1];
              v70 = *((_QWORD *)this + 2);
              if ( !*(_DWORD *)(v70 - 16) )
                v70 = *(_QWORD *)this;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v89,
                L"%s HighUtilization hypothesis %s %s",
                v70,
                *v68,
                v69);
              v71 = v89;
              (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _DWORD))(**((_QWORD **)this + 36) + 120LL))(
                *((_QWORD *)this + 36),
                1,
                v89,
                *(_QWORD *)(v67[2] + 24LL),
                *(_DWORD *)(v67[2] + 16LL));
              ATL::CStringData::Release((ATL::CStringData *)(v71 - 24));
            }
          }
          v72 = (_QWORD *)*((_QWORD *)this + 21);
          while ( 1 )
          {
            v72 = (_QWORD *)*v72;
            if ( v72 == *((_QWORD **)this + 21) )
              break;
            if ( *((_QWORD *)this + 36) )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v89);
              v73 = (_QWORD *)v72[2];
              v74 = &dword_180033E1C;
              if ( v73[1] )
                v74 = (const unsigned __int16 *)v73[1];
              v75 = *((_QWORD *)this + 2);
              if ( !*(_DWORD *)(v75 - 16) )
                v75 = *(_QWORD *)this;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                &v89,
                L"%s HighUtilization hypothesis %s %s",
                v75,
                *v73,
                v74);
              v76 = v89;
              (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _DWORD))(**((_QWORD **)this + 36) + 120LL))(
                *((_QWORD *)this + 36),
                1,
                v89,
                *(_QWORD *)(v72[2] + 24LL),
                *(_DWORD *)(v72[2] + 16LL));
              ATL::CStringData::Release((ATL::CStringData *)(v76 - 24));
            }
          }
          v77 = v90;
          *((_DWORD *)this + 25) = v90;
          if ( Source )
          {
            v78 = -1;
            do
              ++v78;
            while ( Source[v78] );
          }
          else
          {
            v78 = 0;
          }
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 88, Source, v78);
          if ( v77 == 2 )
          {
            *v96 = v6;
            *((_DWORD *)this + 51) = v10;
            *((_DWORD *)this + 53) += v47 + 10 * v10;
            goto LABEL_168;
          }
          *((_DWORD *)this + 53) = v47;
        }
        v79 = *((_QWORD *)this + 42);
        if ( v79 )
        {
          v80 = *((_QWORD *)this + 3);
          if ( !*(_DWORD *)(v80 - 16) )
            v80 = *((_QWORD *)this + 1);
          v81 = *((_QWORD *)this + 2);
          if ( !*(_DWORD *)(v81 - 16) )
            v81 = *(_QWORD *)this;
          LODWORD(v85) = v47;
          (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64, _DWORD))(*(_QWORD *)v79 + 40LL))(
            v79,
            v81,
            v80,
            (unsigned int)v88,
            v85,
            *((_DWORD *)this + 60));
        }
        goto LABEL_168;
      }
      v36 = v35 - 1;
      if ( !v36 )
      {
        LODWORD(v90) = 8;
        goto LABEL_109;
      }
      v37 = v36 - 1;
      if ( v37 )
      {
        v38 = v37 - 1;
        if ( v38 )
        {
          if ( v38 != 1 )
          {
            if ( (_DWORD)v90 != 10 && (_DWORD)v90 != 9 )
              goto LABEL_109;
            goto LABEL_88;
          }
        }
        else
        {
          if ( *a2 > 0 )
          {
            v6 = *(_QWORD *)ATL::CFileTime::GetTickCount(&v92);
            v10 = *a2;
            LODWORD(v90) = 2;
            goto LABEL_109;
          }
          *a2 = 0;
          v88 = DS_INDETERMINATE;
        }
      }
    }
    LODWORD(v90) = 9;
    goto LABEL_88;
  }
  return 2;
}

```

## disassembly

```asm
0x180012b44  mov     [rsp-8+arg_10], rbx
0x180012b49  push    rbp
0x180012b4a  push    rsi
0x180012b4b  push    rdi
0x180012b4c  push    r12
0x180012b4e  push    r13
0x180012b50  push    r14
0x180012b52  push    r15
0x180012b54  lea     rbp, [rsp-27h]
0x180012b59  sub     rsp, 0C0h
0x180012b60  mov     rax, cs:__security_cookie
0x180012b67  xor     rax, rsp
0x180012b6a  mov     [rbp+57h+var_40], rax
0x180012b6e  movzx   r13d, r8b
0x180012b72  mov     [rbp+57h+var_A0], r13b
0x180012b76  mov     rdi, rdx
0x180012b79  mov     r14, rcx
0x180012b7c  mov     [rbp+57h+var_98], 2
0x180012b83  xor     ebx, ebx
0x180012b85  mov     [rbp+57h+Source], rbx
0x180012b89  mov     [rbp+57h+var_50.dwLowDateTime], ebx
0x180012b8c  xor     eax, eax
0x180012b8e  mov     qword ptr [rbp+57h+var_50.dwHighDateTime], rax
0x180012b92  mov     [rbp+57h+FileTime2.dwHighDateTime], eax
0x180012b95  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180012b9a  mov     [rbp+57h+var_78], rax
0x180012b9e  test    rax, rax
0x180012ba1  jz      loc_180012EEF
0x180012ba7  lea     rdx, [r14+0C0h]
0x180012bae  mov     [rbp+57h+var_58], rdx
0x180012bb2  lea     rax, [r14+0B8h]
0x180012bb9  mov     [rbp+57h+var_60], rax
0x180012bbd  test    r13b, r13b
0x180012bc0  jz      short loc_180012BCE
0x180012bc2  mov     rsi, [rax]
0x180012bc5  lea     ecx, [rbx+60h]
0x180012bc8  lea     r15d, [rcx+68h]
0x180012bcc  jmp     short loc_180012BE2
0x180012bce  mov     rsi, [rdx]
0x180012bd1  mov     ecx, 64h ; 'd'
0x180012bd6  lea     r15d, [rcx+68h]
0x180012bda  mov     [rbp+57h+var_60], rax
0x180012bde  mov     [rbp+57h+var_58], rdx
0x180012be2  mov     rax, r13
0x180012be5  xor     rax, 1
0x180012be9  mov     r12, [r14+rax*8+0B8h]
0x180012bf1  mov     [rbp+57h+var_90], r12
0x180012bf5  mov     r15d, [r15+r14]
0x180012bf9  mov     ebx, [rcx+r14]
0x180012bfd  mov     dword ptr [rbp+57h+var_88], ebx
0x180012c00  xor     edx, edx
0x180012c02  cmp     [r14+120h], rdx
0x180012c09  jz      short loc_180012C6F
0x180012c0b  test    r13b, r13b
0x180012c0e  jz      short loc_180012C6F
0x180012c10  lea     rcx, [rbp+57h+var_70]
0x180012c14  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180012c19  nop
0x180012c1a  mov     r8, [r14+10h]
0x180012c1e  cmp     dword ptr [r8-10h], 0
0x180012c23  jnz     short loc_180012C28
0x180012c25  mov     r8, [r14]
0x180012c28  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180012c2c  mov     r9, [r14+8]
0x180012c30  lea     rdx, aDiagnoseSVSLow; "Diagnose %s (v%s). LowHealth : initial "...
0x180012c37  lea     rcx, [rbp+57h+var_70]
0x180012c3b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012c40  mov     rcx, [r14+120h]
0x180012c47  mov     rax, [rcx]
0x180012c4a  mov     r9, [r14+28h]
0x180012c4e  mov     rbx, [rbp+57h+var_70]
0x180012c52  mov     r8, rbx
0x180012c55  xor     edx, edx
0x180012c57  mov     rax, [rax+70h]
0x180012c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c60  nop
0x180012c61  lea     rcx, [rbx-18h]; this
0x180012c65  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012c6a  mov     ebx, dword ptr [rbp+57h+var_88]
0x180012c6d  xor     edx, edx
0x180012c6f  mov     ecx, ebx
0x180012c71  sub     ecx, 1
0x180012c74  jz      loc_18001368A
0x180012c7a  sub     ecx, 1
0x180012c7d  jz      short loc_180012CB6
0x180012c7f  sub     ecx, 1
0x180012c82  jz      short loc_180012CAC
0x180012c84  sub     ecx, 1
0x180012c87  jz      short loc_180012CAC
0x180012c89  sub     ecx, 2
0x180012c8c  jz      short loc_180012CAC
0x180012c8e  sub     ecx, 2
0x180012c91  jz      loc_1800136BF
0x180012c97  sub     ecx, 2
0x180012c9a  jz      short loc_180012CAC
0x180012c9c  sub     ecx, 1
0x180012c9f  jz      short loc_180012CAC
0x180012ca1  cmp     ecx, 1
0x180012ca4  jz      loc_1800136BF
0x180012caa  jmp     short loc_180012D10
0x180012cac  mov     eax, 1
0x180012cb1  jmp     loc_180012EF4
0x180012cb6  lea     rcx, [rbp+57h+var_68]
0x180012cba  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180012cbf  mov     edx, [rax+4]
0x180012cc2  shl     rdx, 20h
0x180012cc6  mov     eax, [rax]
0x180012cc8  or      rdx, rax
0x180012ccb  mov     ecx, dword ptr [rbp+57h+var_90+4]
0x180012cce  shl     rcx, 20h
0x180012cd2  mov     eax, r12d
0x180012cd5  or      rcx, rax
0x180012cd8  sub     rdx, rcx
0x180012cdb  cmp     rdx, 7FFFFFFFh
0x180012ce2  jg      short loc_180012D0C
0x180012ce4  mov     rax, 0D6BF94D5E57A42BDh
0x180012cee  mul     rdx
0x180012cf1  shr     rdx, 17h
0x180012cf5  mov     eax, r15d
0x180012cf8  sub     eax, edx
0x180012cfa  mov     [rdi], eax
0x180012cfc  xor     edx, edx
0x180012cfe  test    eax, eax
0x180012d00  jle     short loc_180012D0E
0x180012d02  mov     eax, 4
0x180012d07  jmp     loc_180012EF4
0x180012d0c  xor     edx, edx
0x180012d0e  mov     [rdi], edx
0x180012d10  test    cs:byte_180041BC1, 2
0x180012d17  jz      short loc_180012D32
0x180012d19  mov     r8, [r14+10h]
0x180012d1d  cmp     [r8-10h], edx
0x180012d21  jnz     short loc_180012D26
0x180012d23  mov     r8, [r14]
0x180012d26  lea     rdx, StartNDFHCDiagnose
0x180012d2d  call    McTemplateU0z_EventWriteTransfer
0x180012d32  lea     rcx, [rbp+57h+var_68]
0x180012d36  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180012d3b  mov     r12, [rax]
0x180012d3e  mov     rcx, [r14+48h]
0x180012d42  lea     rdx, [rbp+57h+var_98]
0x180012d46  mov     r9, rdi
0x180012d49  lea     r8, [rbp+57h+Source]
0x180012d4d  mov     [rbp+57h+var_90], r12
0x180012d51  mov     [rsp+0F0h+var_D0], rdx
0x180012d56  mov     rdx, [r14+20h]
0x180012d5a  test    r13b, r13b
0x180012d5d  jz      short loc_180012D77
0x180012d5f  mov     rax, [rbp+57h+var_60]
0x180012d63  mov     [rax], r12
0x180012d66  mov     dword ptr [r14+60h], 1
0x180012d6e  mov     rax, [rcx]
0x180012d71  mov     rax, [rax+18h]
0x180012d75  jmp     short loc_180012D8D
0x180012d77  mov     rax, [rbp+57h+var_58]
0x180012d7b  mov     [rax], r12
0x180012d7e  mov     dword ptr [r14+64h], 1
0x180012d86  mov     rax, [rcx]
0x180012d89  mov     rax, [rax+20h]
0x180012d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d92  mov     ebx, eax
0x180012d94  test    cs:byte_180041BC1, 2
0x180012d9b  jz      short loc_180012DB7
0x180012d9d  mov     r8, [r14+10h]
0x180012da1  cmp     dword ptr [r8-10h], 0
0x180012da6  jnz     short loc_180012DAB
0x180012da8  mov     r8, [r14]
0x180012dab  lea     rdx, StopNDFHCDiagnose
0x180012db2  call    McTemplateU0z_EventWriteTransfer
0x180012db7  test    r13b, r13b
0x180012dba  jnz     short loc_180012DC4
0x180012dbc  cmp     ebx, 80004001h
0x180012dc2  jz      short loc_180012DCB
0x180012dc4  mov     [r14+0F0h], ebx
0x180012dcb  mov     rax, [rbp+57h+Source]
0x180012dcf  test    rax, rax
0x180012dd2  jz      short loc_180012DFB
0x180012dd4  mov     edx, 400h; MaxCount
0x180012dd9  mov     rcx, rax; Source
0x180012ddc  call    cs:__imp_wcsnlen
0x180012de2  cmp     rax, 400h
0x180012de8  mov     rax, [rbp+57h+Source]
0x180012dec  jnz     short loc_180012DFB
0x180012dee  xor     ecx, ecx
0x180012df0  mov     [rax+800h], cx
0x180012df7  mov     rax, [rbp+57h+Source]
0x180012dfb  test    ebx, ebx
0x180012dfd  jns     loc_180012F1B
0x180012e03  xor     edi, edi
0x180012e05  test    r13b, r13b
0x180012e08  jz      loc_180012EB5
0x180012e0e  cmp     [r14+120h], rdi
0x180012e15  jz      short loc_180012E8E
0x180012e17  lea     rcx, [rbp+57h+var_88]
0x180012e1b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180012e20  nop
0x180012e21  mov     r8, [r14+10h]
0x180012e25  mov     eax, [r8-10h]
0x180012e29  cmp     ebx, 80004001h
0x180012e2f  jz      short loc_180012E4D
0x180012e31  test    eax, eax
0x180012e33  jnz     short loc_180012E38
0x180012e35  mov     r8, [r14]
0x180012e38  mov     r9d, ebx
0x180012e3b  lea     rdx, aDiagnosisFaile; "Diagnosis failed for %s with error 0x%x"...
0x180012e42  lea     rcx, [rbp+57h+var_88]
0x180012e46  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012e4b  jmp     short loc_180012E64
0x180012e4d  test    eax, eax
0x180012e4f  jnz     short loc_180012E54
0x180012e51  mov     r8, [r14]
0x180012e54  lea     rdx, aDiagnosisNotIm; "Diagnosis not implemented for %s."
0x180012e5b  lea     rcx, [rbp+57h+var_88]
0x180012e5f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012e64  mov     rcx, [r14+120h]
0x180012e6b  mov     rax, [rcx]
0x180012e6e  mov     rbx, [rbp+57h+var_88]
0x180012e72  mov     r8, rbx
0x180012e75  xor     edx, edx
0x180012e77  mov     rax, [rax+60h]
0x180012e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e80  nop
0x180012e81  lea     rcx, [rbx-18h]; this
0x180012e85  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012e8a  mov     rax, [rbp+57h+Source]
0x180012e8e  mov     dword ptr [r14+60h], 9
0x180012e96  test    rax, rax
0x180012e99  jnz     short loc_180012EA0
0x180012e9b  mov     r8d, edi
0x180012e9e  jmp     short loc_180012EAE
0x180012ea0  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012ea4  inc     r8
0x180012ea7  cmp     [rax+r8*2], di
0x180012eac  jnz     short loc_180012EA4
0x180012eae  mov     ecx, 50h ; 'P'
0x180012eb3  jmp     short loc_180012EDA
0x180012eb5  mov     dword ptr [r14+64h], 9
0x180012ebd  test    rax, rax
0x180012ec0  jnz     short loc_180012EC7
0x180012ec2  mov     r8d, edi
0x180012ec5  jmp     short loc_180012ED5
0x180012ec7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012ecb  inc     r8
0x180012ece  cmp     [rax+r8*2], di
0x180012ed3  jnz     short loc_180012ECB
0x180012ed5  mov     ecx, 58h ; 'X'
0x180012eda  add     rcx, r14
0x180012edd  mov     rdx, rax
0x180012ee0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180012ee5  mov     rcx, [rbp+57h+Source]; pv
0x180012ee9  call    cs:__imp_CoTaskMemFree
0x180012eef  mov     eax, 3
0x180012ef4  mov     rcx, [rbp+57h+var_40]
0x180012ef8  xor     rcx, rsp; StackCookie
0x180012efb  call    __security_check_cookie
0x180012f00  mov     rbx, [rsp+0F0h+arg_10]
0x180012f08  add     rsp, 0C0h
0x180012f0f  pop     r15
0x180012f11  pop     r14
0x180012f13  pop     r13
0x180012f15  pop     r12
0x180012f17  pop     rdi
0x180012f18  pop     rsi
0x180012f19  pop     rbp
0x180012f1a  retn
0x180012f1b  mov     rax, 0FFFFFFFF00000000h
0x180012f25  and     r12, rax
0x180012f28  mov     [rbp+57h+var_68], r12
0x180012f2c  mov     ecx, [rbp+57h+var_98]
0x180012f2f  lea     eax, [rcx-1]
0x180012f32  cmp     eax, 2
0x180012f35  jbe     short loc_180012F40
0x180012f37  cmp     ecx, 5
0x180012f3a  jnz     loc_180012FC8
0x180012f40  xor     r12d, r12d
0x180012f43  mov     [rbp+57h+var_70], r12
0x180012f47  mov     rcx, [r14+48h]
0x180012f4b  mov     rax, [rcx]
0x180012f4e  lea     rdx, [rbp+57h+var_70]
0x180012f52  mov     rax, [rax+70h]
0x180012f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f5b  test    eax, eax
0x180012f5d  js      short loc_180012F67
0x180012f5f  mov     rax, [rbp+57h+var_70]
0x180012f63  mov     [r14+40h], rax
0x180012f67  mov     rcx, [r14+48h]
0x180012f6b  mov     rax, [rcx]
0x180012f6e  lea     rdx, [rbp+57h+var_50]
0x180012f72  mov     rax, [rax+60h]
0x180012f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7b  test    eax, eax
0x180012f7d  js      short loc_180012FC3
0x180012f7f  lea     rcx, [r14+38h]; lpFileTime1
0x180012f83  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180012f87  call    cs:__imp_CompareFileTime
0x180012f8d  test    eax, eax
0x180012f8f  jns     short loc_180012F99
0x180012f91  mov     rax, qword ptr [rbp+57h+FileTime2.dwLowDateTime]
0x180012f95  mov     [r14+38h], rax
0x180012f99  lea     rdx, [rbp+57h+var_50]; lpFileTime2
  ... truncated ...
```
