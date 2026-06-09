# _DataCollector<ITraceDataCollector>::CreateOutputLocation(short,ushort * *)

- ea: `0x1800b02f0`
- end: `0x1800b12df`
- name: `?CreateOutputLocation@?$_DataCollector@UITraceDataCollector@@@@UEAAJFPEAPEAG@Z`
- size: `4079`
- prototype: `__int64 __fastcall(__int64, __int16, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180012ef0`
- `0x180018420`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x180046c60`
- `0x18004d680`
- `0x18006b12c`
- `0x180072200`
- `0x1800b02f0`
- `0x1800f9c48`
- `0x180116404`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b094e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b094e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1280`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b03db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b03db`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800b0940`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800b0940`

## string_xrefs

- `0x1800b0395`: `_DataCollector<struct ITraceDataCollector>::CreateOutputLocation`
- `0x1800b0477`: `_DataCollector<struct ITraceDataCollector>::CreateOutputLocation`
- `0x1800b1221`: `_DataCollector<struct ITraceDataCollector>::CreateOutputLocation`

## pseudocode

```c
__int64 __fastcall _DataCollector<ITraceDataCollector>::CreateOutputLocation(
        __int64 a1,
        __int16 a2,
        unsigned __int16 **a3)
{
  WCHAR *v6; // r13
  unsigned __int16 *v7; // r15
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  unsigned __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  DWORD LastError; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  LONGLONG llVal; // r8
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  unsigned __int64 v41; // rdx
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  unsigned int v47; // ecx
  int appended; // eax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rax
  const unsigned __int16 *v52; // r8
  __int64 v53; // rax
  int v54; // eax
  unsigned __int64 v55; // rdx
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rax
  int v59; // eax
  const char *v60; // rdx
  int v61; // r8d
  __int64 v62; // rax
  unsigned __int16 *v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  int v67; // [rsp+20h] [rbp-E0h]
  int v68; // [rsp+20h] [rbp-E0h]
  __int64 v69; // [rsp+48h] [rbp-B8h]
  __int64 v70; // [rsp+50h] [rbp-B0h]
  int v71; // [rsp+70h] [rbp-90h] BYREF
  __int64 v72; // [rsp+78h] [rbp-88h] BYREF
  int v73; // [rsp+80h] [rbp-80h] BYREF
  DWORD nSize; // [rsp+84h] [rbp-7Ch] BYREF
  struct tagVARIANT v75; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v76[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v77[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v78[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v79[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v80[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v81[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v82[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v83[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v84[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v85[64]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v86[64]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 v87[64]; // [rsp+620h] [rbp+520h] BYREF
  unsigned __int16 v88[64]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 v89[64]; // [rsp+720h] [rbp+620h] BYREF
  unsigned __int16 v90[64]; // [rsp+7A0h] [rbp+6A0h] BYREF
  unsigned __int16 v91[64]; // [rsp+820h] [rbp+720h] BYREF
  unsigned __int16 v92[64]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v93[64]; // [rsp+920h] [rbp+820h] BYREF
  unsigned __int16 v94[64]; // [rsp+9A0h] [rbp+8A0h] BYREF
  unsigned __int16 v95[64]; // [rsp+A20h] [rbp+920h] BYREF
  unsigned __int16 v96[64]; // [rsp+AA0h] [rbp+9A0h] BYREF
  unsigned __int16 v97[64]; // [rsp+B20h] [rbp+A20h] BYREF
  unsigned __int16 v98[64]; // [rsp+BA0h] [rbp+AA0h] BYREF
  unsigned __int16 v99[64]; // [rsp+C20h] [rbp+B20h] BYREF
  unsigned __int16 v100[64]; // [rsp+CA0h] [rbp+BA0h] BYREF

  v72 = a1;
  v73 = 0;
  v71 = *(_DWORD *)(a1 + 56);
  nSize = 0;
  v6 = 0;
  v7 = 0;
  memset(&v75, 0, sizeof(v75));
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "_DataCollector<struct ITraceDataCollector>::CreateOutputLocation",
      65,
      &v72,
      8,
      &v71,
      4,
      v69,
      v70);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  PlaiVariantInit(&v75);
  if ( a3 )
  {
    v10 = *(_QWORD *)(a1 + 72);
    if ( !v10 )
    {
      v8 = -2144337918;
      LODWORD(v72) = 0;
      v71 = -2144337918;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_192;
      }
      PlaiWhoAmI(v77, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v77[v11] );
      goto LABEL_191;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 240LL))(v10, &v73);
    v8 = v12;
    if ( v12 < 0 )
    {
      v71 = v12;
      LODWORD(v72) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_192;
      }
      PlaiWhoAmI(v78, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v78[v13] );
      goto LABEL_191;
    }
    v6 = (WCHAR *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v67);
    if ( !v6 )
    {
      v8 = -2147024882;
      LODWORD(v72) = 0;
      v71 = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_192;
      }
      PlaiWhoAmI(v79, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v79[v14] );
      goto LABEL_191;
    }
    v7 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v68);
    if ( !v7 )
    {
      v8 = -2147024882;
      LODWORD(v72) = 0;
      v71 = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_192;
      }
      PlaiWhoAmI(v80, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v80[v15] );
      goto LABEL_191;
    }
    PlaiVariantClear(&v75);
    v16 = *(__int64 **)(a1 + 72);
    v17 = *v16;
    if ( a2 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64 *, CY *))(v17 + 144))(v16, &v75.cyVal);
      v8 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v18;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v81, 0x4000000000000800uLL);
        v19 = -1;
        do
          ++v19;
        while ( v81[v19] );
        goto LABEL_191;
      }
    }
    else
    {
      v20 = (*(__int64 (__fastcall **)(__int64 *, CY *))(v17 + 168))(v16, &v75.cyVal);
      v8 = v20;
      if ( v20 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v82, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v82[v21] );
        goto LABEL_191;
      }
    }
    v75.vt = 8;
    if ( v75.llVal && *v75.bstrVal )
    {
      v22 = StringCchCopyW(v7, 0x400u, v75.bstrVal);
      v8 = v22;
      if ( v22 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v22;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v83, 0x4000000000000800uLL);
        v25 = -1;
        do
          ++v25;
        while ( v83[v25] );
        goto LABEL_191;
      }
      v26 = PlaiPathCat(v7, v23, v24);
      v8 = v26;
      if ( v26 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v26;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v84, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v84[v27] );
        goto LABEL_191;
      }
      if ( (*(_BYTE *)(a1 + 88) & 2) != 0 )
      {
        nSize = 1024;
        if ( !GetComputerNameW(v6, &nSize) )
        {
          LastError = GetLastError();
          v29 = PlaiHResultFromWin32(LastError);
          v8 = v29;
          if ( v29 < 0 )
          {
            LODWORD(v72) = 0;
            v71 = v29;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_192;
            }
            PlaiWhoAmI(v85, 0x4000000000000800uLL);
            v30 = -1;
            do
              ++v30;
            while ( v85[v30] );
            goto LABEL_191;
          }
        }
        v31 = StringCchCatW(v7, 0x400u, v6);
        v8 = v31;
        if ( v31 < 0 )
        {
          LODWORD(v72) = 0;
          v71 = v31;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v86, 0x4000000000000800uLL);
          v32 = -1;
          do
            ++v32;
          while ( v86[v32] );
          goto LABEL_191;
        }
        v33 = StringCchCatW(v7, 0x400u, L"_");
        v8 = v33;
        if ( v33 < 0 )
        {
          LODWORD(v72) = 0;
          v71 = v33;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v87, 0x4000000000000800uLL);
          v34 = -1;
          do
            ++v34;
          while ( v87[v34] );
          goto LABEL_191;
        }
      }
      PlaiVariantClear(&v75);
      v35 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)a1 + 80LL))(a1, &v75.cyVal);
      v8 = v35;
      if ( v35 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v35;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v88, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v88[v36] );
        goto LABEL_191;
      }
      llVal = v75.llVal;
      v75.vt = 8;
      if ( v75.llVal )
      {
        if ( *v75.bstrVal )
        {
          v38 = StringCchCatW(v7, 0x400u, v75.bstrVal);
          v8 = v38;
          if ( v38 < 0 )
          {
            LODWORD(v72) = 0;
            v71 = v38;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_192;
            }
            PlaiWhoAmI(v89, 0x4000000000000800uLL);
            v39 = -1;
            do
              ++v39;
            while ( v89[v39] );
            goto LABEL_191;
          }
        }
      }
      if ( (*(_BYTE *)(a1 + 88) & 1) == 0 )
        goto LABEL_136;
      PlaiVariantClear(&v75);
      v40 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)a1 + 112LL))(a1, &v75.cyVal);
      v8 = v40;
      if ( v40 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v40;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v90, 0x4000000000000800uLL);
        v42 = -1;
        do
          ++v42;
        while ( v90[v42] );
        goto LABEL_191;
      }
      llVal = v75.llVal;
      v75.vt = 8;
      if ( !v75.llVal || !*v75.bstrVal )
        goto LABEL_136;
      v43 = PlaiExpandPattern(v6, v41, v75.bstrVal, v73);
      v8 = v43;
      if ( v43 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v43;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v91, 0x4000000000000800uLL);
        v44 = -1;
        do
          ++v44;
        while ( v91[v44] );
        goto LABEL_191;
      }
      v45 = StringCchCatW(v7, 0x400u, v6);
      v8 = v45;
      if ( v45 < 0 )
      {
        LODWORD(v72) = 0;
        v71 = v45;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v92, 0x4000000000000800uLL);
        v46 = -1;
        do
          ++v46;
        while ( v92[v46] );
      }
      else
      {
LABEL_136:
        v47 = *(_DWORD *)(a1 + 88);
        if ( (v47 & 0xFF00) != 0 && (appended = PlaiAppendAutoPattern(v47, v7, llVal, v73), v8 = appended, appended < 0) )
        {
          LODWORD(v72) = 0;
          v71 = appended;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v93, 0x4000000000000800uLL);
          v49 = -1;
          do
            ++v49;
          while ( v93[v49] );
        }
        else
        {
          v50 = StringCchCatW(v7, 0x400u, L".");
          v8 = v50;
          if ( v50 >= 0 )
          {
            v52 = *(const unsigned __int16 **)(a1 + 144);
            if ( v52 )
            {
              v54 = StringCchCatW(v7, 0x400u, v52);
              v8 = v54;
              if ( v54 >= 0 )
              {
                v57 = PlaiExpandVariables(v7, v55, v7);
                v8 = v57;
                if ( v57 >= 0 )
                {
                  v59 = PlaiValidatePath(v7, 1);
                  v8 = v59;
                  if ( v59 >= 0 )
                  {
                    v63 = PlaiAllocStringEx(v7, v60, v61);
                    *a3 = v63;
                    if ( v63 )
                      goto LABEL_192;
                    v8 = -2147024882;
                    v71 = -2147024882;
                    LODWORD(v72) = 0;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_192;
                    }
                    PlaiWhoAmI(v99, 0x4000000000000800uLL);
                    v64 = -1;
                    do
                      ++v64;
                    while ( v99[v64] );
                  }
                  else
                  {
                    LODWORD(v72) = 0;
                    v71 = v59;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_192;
                    }
                    PlaiWhoAmI(v98, 0x4000000000000800uLL);
                    v62 = -1;
                    do
                      ++v62;
                    while ( v98[v62] );
                  }
                }
                else
                {
                  LODWORD(v72) = 0;
                  v71 = v57;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_192;
                  }
                  PlaiWhoAmI(v97, 0x4000000000000800uLL);
                  v58 = -1;
                  do
                    ++v58;
                  while ( v97[v58] );
                }
              }
              else
              {
                LODWORD(v72) = 0;
                v71 = v54;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_192;
                }
                PlaiWhoAmI(v96, 0x4000000000000800uLL);
                v56 = -1;
                do
                  ++v56;
                while ( v96[v56] );
              }
            }
            else
            {
              v8 = -2147024882;
              v71 = -2147024882;
              LODWORD(v72) = 0;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_192;
              }
              PlaiWhoAmI(v95, 0x4000000000000800uLL);
              v53 = -1;
              do
                ++v53;
              while ( v95[v53] );
            }
          }
          else
          {
            LODWORD(v72) = 0;
            v71 = v50;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_192;
            }
            PlaiWhoAmI(v94, 0x4000000000000800uLL);
            v51 = -1;
            do
              ++v51;
            while ( v94[v51] );
          }
        }
      }
    }
    else
    {
      v8 = -2147467259;
      v71 = -2147467259;
      LODWORD(v72) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_192;
      }
      PlaiWhoAmI(v100, 0x4000000000000800uLL);
      v65 = -1;
      do
        ++v65;
      while ( v100[v65] );
    }
LABEL_191:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v71,
      4,
      qword_180147320,
      1,
      &v72,
      4,
      "_DataCollector<struct ITraceDataCollector>::CreateOutputLocation",
      65);
    goto LABEL_192;
  }
  v8 = -2147467261;
  v71 = 0;
  LODWORD(v72) = -2147467261;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v76, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v76[v9] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v72,
      4,
      qword_180147320,
      1,
      &v71,
      4,
      "_DataCollector<struct ITraceDataCollector>::CreateOutputLocation",
      65);
  }
LABEL_192:
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  PlaiVariantClear(&v75);
  if ( v6 )
    PlaiFree(v6, 1);
  if ( v7 )
    PlaiFree(v7, 1);
  return v8;
}

```

## disassembly

```asm
0x1800b02f0  mov     [rsp-8+arg_8], rbx
0x1800b02f5  push    rbp
0x1800b02f6  push    rsi
0x1800b02f7  push    rdi
0x1800b02f8  push    r12
0x1800b02fa  push    r13
0x1800b02fc  push    r14
0x1800b02fe  push    r15
0x1800b0300  lea     rbp, [rsp-0C30h]
0x1800b0308  sub     rsp, 0D30h
0x1800b030f  mov     rax, cs:__security_cookie
0x1800b0316  xor     rax, rsp
0x1800b0319  mov     [rbp+0C60h+var_40], rax
0x1800b0320  xor     r14d, r14d
0x1800b0323  mov     [rsp+0D60h+var_CE8], rcx
0x1800b0328  xor     eax, eax
0x1800b032a  mov     [rbp+0C60h+var_CE0], r14d
0x1800b032e  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800b0335  xorps   xmm0, xmm0
0x1800b0338  mov     qword ptr [rbp+0C60h+var_CD8+10h], rax
0x1800b033c  mov     rsi, r8
0x1800b033f  mov     eax, [rcx+38h]
0x1800b0342  movzx   edi, dx
0x1800b0345  mov     [rsp+0D60h+var_CF0], eax
0x1800b0349  mov     r12, rcx
0x1800b034c  mov     [rbp+0C60h+nSize], r14d
0x1800b0350  mov     r13d, r14d
0x1800b0353  mov     r15d, r14d
0x1800b0356  movups  xmmword ptr [rbp+0C60h+var_CD8], xmm0
0x1800b035a  jz      short loc_1800B03CF
0x1800b035c  mov     rdx, 4000000000000400h
0x1800b0366  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b036d  jz      short loc_1800B03CF
0x1800b036f  mov     rax, cs:qword_180169748
0x1800b0376  and     rax, rdx
0x1800b0379  cmp     cs:qword_180169748, rax
0x1800b0380  jnz     short loc_1800B03CF
0x1800b0382  mov     [rsp+0D60h+var_D20], 4
0x1800b038b  lea     rax, [rsp+0D60h+var_CF0]
0x1800b0390  mov     [rsp+0D60h+var_D28], rax
0x1800b0395  lea     r9, aDatacollectorS_42; "_DataCollector<struct ITraceDataCollect"...
0x1800b039c  lea     rax, [rsp+0D60h+var_CE8]
0x1800b03a1  mov     [rsp+0D60h+var_D30], 8
0x1800b03aa  mov     [rsp+0D60h+var_D38], rax
0x1800b03af  lea     r8d, [r14+3]
0x1800b03b3  lea     rdx, PLA_EVENT_METHOD
0x1800b03ba  mov     qword ptr [rsp+0D60h+var_D40], 41h ; 'A'; int
0x1800b03c3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b03ca  call    EventingWriteEvent
0x1800b03cf  cmp     [r12+8], r14d
0x1800b03d4  jz      short loc_1800B03E1
0x1800b03d6  lea     rcx, [r12+10h]; lpCriticalSection
0x1800b03db  call    cs:__imp_EnterCriticalSection
0x1800b03e1  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800b03e5  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800b03ea  test    rsi, rsi
0x1800b03ed  jnz     loc_1800B0496
0x1800b03f3  xor     edi, edi
0x1800b03f5  mov     ebx, 80004003h
0x1800b03fa  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b0400  mov     [rsp+0D60h+var_CF0], edi
0x1800b0404  mov     dword ptr [rsp+0D60h+var_CE8], ebx
0x1800b0408  jz      loc_1800B1274
0x1800b040e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b0418  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b041f  jz      loc_1800B1274
0x1800b0425  mov     rax, cs:qword_180169748
0x1800b042c  and     rax, rdx
0x1800b042f  cmp     cs:qword_180169748, rax
0x1800b0436  jnz     loc_1800B1274
0x1800b043c  lea     rcx, [rbp+0C60h+var_CC0]; unsigned __int16 *
0x1800b0440  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b0445  lea     rcx, [rbp+0C60h+var_CC0]
0x1800b0449  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b044d  inc     rax
0x1800b0450  cmp     [rcx+rax*2], di
0x1800b0454  jnz     short loc_1800B044D
0x1800b0456  lea     ecx, [rax+rax]
0x1800b0459  lea     rax, [rbp+0C60h+var_CC0]
0x1800b045d  add     rcx, 2
0x1800b0461  mov     [rsp+0D60h+var_D00], rcx
0x1800b0466  lea     r14, qword_180147320
0x1800b046d  mov     [rsp+0D60h+var_D08], rax
0x1800b0472  lea     r9, [rsp+0D60h+var_CE8]
0x1800b0477  lea     rax, aDatacollectorS_42; "_DataCollector<struct ITraceDataCollect"...
0x1800b047e  mov     [rsp+0D60h+var_D10], 41h ; 'A'
0x1800b0487  mov     [rsp+0D60h+var_D18], rax
0x1800b048c  lea     rax, [rsp+0D60h+var_CF0]
0x1800b0491  jmp     loc_1800B123B
0x1800b0496  mov     rcx, [r12+48h]
0x1800b049b  test    rcx, rcx
0x1800b049e  jnz     short loc_1800B0516
0x1800b04a0  xor     edi, edi
0x1800b04a2  mov     ebx, 80300002h
0x1800b04a7  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b04ad  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800b04b1  mov     [rsp+0D60h+var_CF0], ebx
0x1800b04b5  jz      loc_1800B1274
0x1800b04bb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b04c5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b04cc  jz      loc_1800B1274
0x1800b04d2  mov     rax, cs:qword_180169748
0x1800b04d9  and     rax, rdx
0x1800b04dc  cmp     cs:qword_180169748, rax
0x1800b04e3  jnz     loc_1800B1274
0x1800b04e9  lea     rcx, [rbp+0C60h+var_C40]; unsigned __int16 *
0x1800b04ed  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b04f2  lea     rcx, [rbp+0C60h+var_C40]
0x1800b04f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b04fa  inc     rax
0x1800b04fd  cmp     [rcx+rax*2], di
0x1800b0501  jnz     short loc_1800B04FA
0x1800b0503  lea     ecx, [rax+rax]
0x1800b0506  lea     rax, [rbp+0C60h+var_C40]
0x1800b050a  lea     r14, qword_180147320
0x1800b0511  jmp     loc_1800B120E
0x1800b0516  mov     rax, [rcx]
0x1800b0519  lea     rdx, [rbp+0C60h+var_CE0]
0x1800b051d  mov     rax, [rax+0F0h]
0x1800b0524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0529  mov     ebx, eax
0x1800b052b  test    eax, eax
0x1800b052d  jns     short loc_1800B05A2
0x1800b052f  xor     edi, edi
0x1800b0531  mov     [rsp+0D60h+var_CF0], eax
0x1800b0535  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b053b  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800b053f  jz      loc_1800B1274
0x1800b0545  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b054f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b0556  jz      loc_1800B1274
0x1800b055c  mov     rax, cs:qword_180169748
0x1800b0563  and     rax, rdx
0x1800b0566  cmp     cs:qword_180169748, rax
0x1800b056d  jnz     loc_1800B1274
0x1800b0573  lea     rcx, [rbp+0C60h+var_BC0]; unsigned __int16 *
0x1800b057a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b057f  lea     rcx, [rbp+0C60h+var_BC0]
0x1800b0586  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b058a  inc     rax
0x1800b058d  cmp     [rcx+rax*2], di
0x1800b0591  jnz     short loc_1800B058A
0x1800b0593  lea     ecx, [rax+rax]
0x1800b0596  lea     rax, [rbp+0C60h+var_BC0]
0x1800b059d  jmp     loc_1800B050A
0x1800b05a2  xor     r8d, r8d; int
0x1800b05a5  lea     r14, qword_180147320
0x1800b05ac  mov     r9, r14; char *
0x1800b05af  mov     ecx, 800h; dwBytes
0x1800b05b4  lea     edx, [r8+1]; int
0x1800b05b8  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800b05bd  xor     ebx, ebx
0x1800b05bf  mov     r13, rax
0x1800b05c2  test    rax, rax
0x1800b05c5  jnz     short loc_1800B0641
0x1800b05c7  xor     edi, edi
0x1800b05c9  mov     ecx, 8007000Eh
0x1800b05ce  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b05d4  mov     ebx, ecx
0x1800b05d6  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800b05da  mov     [rsp+0D60h+var_CF0], ecx
0x1800b05de  jz      loc_1800B1274
0x1800b05e4  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b05ee  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b05f5  jz      loc_1800B1274
0x1800b05fb  mov     rax, cs:qword_180169748
0x1800b0602  and     rax, rdx
0x1800b0605  cmp     cs:qword_180169748, rax
0x1800b060c  jnz     loc_1800B1274
0x1800b0612  lea     rcx, [rbp+0C60h+var_B40]; unsigned __int16 *
0x1800b0619  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b061e  lea     rcx, [rbp+0C60h+var_B40]
0x1800b0625  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b0629  inc     rax
0x1800b062c  cmp     [rcx+rax*2], di
0x1800b0630  jnz     short loc_1800B0629
0x1800b0632  lea     ecx, [rax+rax]
0x1800b0635  lea     rax, [rbp+0C60h+var_B40]
0x1800b063c  jmp     loc_1800B120E
0x1800b0641  xor     r8d, r8d; int
0x1800b0644  mov     r9, r14; char *
0x1800b0647  mov     ecx, 800h; dwBytes
0x1800b064c  lea     edx, [r8+1]; int
0x1800b0650  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800b0655  mov     r15, rax
0x1800b0658  test    rax, rax
0x1800b065b  jnz     short loc_1800B06D7
0x1800b065d  xor     edi, edi
0x1800b065f  mov     ecx, 8007000Eh
0x1800b0664  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b066a  mov     ebx, ecx
0x1800b066c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800b0670  mov     [rsp+0D60h+var_CF0], ecx
0x1800b0674  jz      loc_1800B1274
0x1800b067a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b0684  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b068b  jz      loc_1800B1274
0x1800b0691  mov     rax, cs:qword_180169748
0x1800b0698  and     rax, rdx
0x1800b069b  cmp     cs:qword_180169748, rax
0x1800b06a2  jnz     loc_1800B1274
0x1800b06a8  lea     rcx, [rbp+0C60h+var_AC0]; unsigned __int16 *
0x1800b06af  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b06b4  lea     rcx, [rbp+0C60h+var_AC0]
0x1800b06bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b06bf  inc     rax
0x1800b06c2  cmp     [rcx+rax*2], di
0x1800b06c6  jnz     short loc_1800B06BF
0x1800b06c8  lea     ecx, [rax+rax]
0x1800b06cb  lea     rax, [rbp+0C60h+var_AC0]
0x1800b06d2  jmp     loc_1800B120E
0x1800b06d7  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800b06db  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800b06e0  mov     rcx, [r12+48h]
0x1800b06e5  lea     rdx, [rbp+0C60h+var_CD8+8]
0x1800b06e9  mov     rax, [rcx]
0x1800b06ec  cmp     bx, di
0x1800b06ef  jz      loc_1800B077E
0x1800b06f5  mov     rax, [rax+90h]
0x1800b06fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0701  xor     edi, edi
0x1800b0703  mov     ebx, eax
0x1800b0705  test    eax, eax
0x1800b0707  jns     loc_1800B0803
0x1800b070d  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b0713  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800b0717  mov     [rsp+0D60h+var_CF0], eax
0x1800b071b  jz      loc_1800B1274
0x1800b0721  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b072b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b0732  jz      loc_1800B1274
0x1800b0738  mov     rax, cs:qword_180169748
0x1800b073f  and     rax, rdx
0x1800b0742  cmp     cs:qword_180169748, rax
0x1800b0749  jnz     loc_1800B1274
0x1800b074f  lea     rcx, [rbp+0C60h+var_A40]; unsigned __int16 *
0x1800b0756  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b075b  lea     rcx, [rbp+0C60h+var_A40]
0x1800b0762  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b0766  inc     rax
0x1800b0769  cmp     [rcx+rax*2], di
0x1800b076d  jnz     short loc_1800B0766
0x1800b076f  lea     ecx, [rax+rax]
0x1800b0772  lea     rax, [rbp+0C60h+var_A40]
0x1800b0779  jmp     loc_1800B120E
0x1800b077e  mov     rax, [rax+0A8h]
0x1800b0785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b078a  xor     edi, edi
0x1800b078c  mov     ebx, eax
0x1800b078e  test    eax, eax
0x1800b0790  jns     short loc_1800B0803
0x1800b0792  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b0798  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800b079c  mov     [rsp+0D60h+var_CF0], eax
0x1800b07a0  jz      loc_1800B1274
0x1800b07a6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b07b0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b07b7  jz      loc_1800B1274
0x1800b07bd  mov     rax, cs:qword_180169748
0x1800b07c4  and     rax, rdx
0x1800b07c7  cmp     cs:qword_180169748, rax
0x1800b07ce  jnz     loc_1800B1274
0x1800b07d4  lea     rcx, [rbp+0C60h+var_9C0]; unsigned __int16 *
0x1800b07db  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b07e0  lea     rcx, [rbp+0C60h+var_9C0]
0x1800b07e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b07eb  inc     rax
0x1800b07ee  cmp     [rcx+rax*2], di
0x1800b07f2  jnz     short loc_1800B07EB
0x1800b07f4  lea     ecx, [rax+rax]
0x1800b07f7  lea     rax, [rbp+0C60h+var_9C0]
0x1800b07fe  jmp     loc_1800B120E
0x1800b0803  mov     r8, qword ptr [rbp+0C60h+var_CD8+8]; unsigned __int16 *
0x1800b0807  mov     eax, 8
0x1800b080c  mov     word ptr [rbp+0C60h+var_CD8], ax
0x1800b0810  test    r8, r8
0x1800b0813  jz      loc_1800B119D
0x1800b0819  cmp     di, [r8]
0x1800b081d  jz      loc_1800B119D
0x1800b0823  mov     edx, 400h; unsigned __int64
0x1800b0828  mov     rcx, r15; unsigned __int16 *
0x1800b082b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b0830  mov     ebx, eax
0x1800b0832  test    eax, eax
0x1800b0834  jns     short loc_1800B08A7
0x1800b0836  cmp     dword ptr cs:xmmword_180169738, edi
0x1800b083c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800b0840  mov     [rsp+0D60h+var_CF0], eax
0x1800b0844  jz      loc_1800B1274
0x1800b084a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b0854  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b085b  jz      loc_1800B1274
0x1800b0861  mov     rax, cs:qword_180169748
0x1800b0868  and     rax, rdx
0x1800b086b  cmp     cs:qword_180169748, rax
0x1800b0872  jnz     loc_1800B1274
0x1800b0878  lea     rcx, [rbp+0C60h+var_940]; unsigned __int16 *
0x1800b087f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b0884  lea     rcx, [rbp+0C60h+var_940]
0x1800b088b  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
