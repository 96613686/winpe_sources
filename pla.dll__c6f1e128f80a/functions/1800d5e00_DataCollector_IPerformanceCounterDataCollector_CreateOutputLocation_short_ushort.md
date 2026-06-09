# _DataCollector<IPerformanceCounterDataCollector>::CreateOutputLocation(short,ushort * *)

- ea: `0x1800d5e00`
- end: `0x1800d6def`
- name: `?CreateOutputLocation@?$_DataCollector@UIPerformanceCounterDataCollector@@@@UEAAJFPEAPEAG@Z`
- size: `4079`
- prototype: `__int64 __fastcall(__int64, __int16, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800fd0b0`

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
- `0x1800d5e00`
- `0x1800f9c48`
- `0x180116404`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d645e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d645e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d6d90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d6d90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d5eeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d5eeb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800d6450`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800d6450`

## string_xrefs

- `0x1800d5ea5`: `_DataCollector<struct IPerformanceCounterDataCollector>::CreateOutputLocation`
- `0x1800d5f87`: `_DataCollector<struct IPerformanceCounterDataCollector>::CreateOutputLocation`
- `0x1800d6d31`: `_DataCollector<struct IPerformanceCounterDataCollector>::CreateOutputLocation`

## pseudocode

```c
__int64 __fastcall _DataCollector<IPerformanceCounterDataCollector>::CreateOutputLocation(
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
      "_DataCollector<struct IPerformanceCounterDataCollector>::CreateOutputLocation",
      78,
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
      "_DataCollector<struct IPerformanceCounterDataCollector>::CreateOutputLocation",
      78);
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
      "_DataCollector<struct IPerformanceCounterDataCollector>::CreateOutputLocation",
      78);
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
0x1800d5e00  mov     [rsp-8+arg_8], rbx
0x1800d5e05  push    rbp
0x1800d5e06  push    rsi
0x1800d5e07  push    rdi
0x1800d5e08  push    r12
0x1800d5e0a  push    r13
0x1800d5e0c  push    r14
0x1800d5e0e  push    r15
0x1800d5e10  lea     rbp, [rsp-0C30h]
0x1800d5e18  sub     rsp, 0D30h
0x1800d5e1f  mov     rax, cs:__security_cookie
0x1800d5e26  xor     rax, rsp
0x1800d5e29  mov     [rbp+0C60h+var_40], rax
0x1800d5e30  xor     r14d, r14d
0x1800d5e33  mov     [rsp+0D60h+var_CE8], rcx
0x1800d5e38  xor     eax, eax
0x1800d5e3a  mov     [rbp+0C60h+var_CE0], r14d
0x1800d5e3e  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800d5e45  xorps   xmm0, xmm0
0x1800d5e48  mov     qword ptr [rbp+0C60h+var_CD8+10h], rax
0x1800d5e4c  mov     rsi, r8
0x1800d5e4f  mov     eax, [rcx+38h]
0x1800d5e52  movzx   edi, dx
0x1800d5e55  mov     [rsp+0D60h+var_CF0], eax
0x1800d5e59  mov     r12, rcx
0x1800d5e5c  mov     [rbp+0C60h+nSize], r14d
0x1800d5e60  mov     r13d, r14d
0x1800d5e63  mov     r15d, r14d
0x1800d5e66  movups  xmmword ptr [rbp+0C60h+var_CD8], xmm0
0x1800d5e6a  jz      short loc_1800D5EDF
0x1800d5e6c  mov     rdx, 4000000000000400h
0x1800d5e76  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d5e7d  jz      short loc_1800D5EDF
0x1800d5e7f  mov     rax, cs:qword_180169748
0x1800d5e86  and     rax, rdx
0x1800d5e89  cmp     cs:qword_180169748, rax
0x1800d5e90  jnz     short loc_1800D5EDF
0x1800d5e92  mov     [rsp+0D60h+var_D20], 4
0x1800d5e9b  lea     rax, [rsp+0D60h+var_CF0]
0x1800d5ea0  mov     [rsp+0D60h+var_D28], rax
0x1800d5ea5  lea     r9, aDatacollectorS_40; "_DataCollector<struct IPerformanceCount"...
0x1800d5eac  lea     rax, [rsp+0D60h+var_CE8]
0x1800d5eb1  mov     [rsp+0D60h+var_D30], 8
0x1800d5eba  mov     [rsp+0D60h+var_D38], rax
0x1800d5ebf  lea     r8d, [r14+3]
0x1800d5ec3  lea     rdx, PLA_EVENT_METHOD
0x1800d5eca  mov     qword ptr [rsp+0D60h+var_D40], 4Eh ; 'N'; int
0x1800d5ed3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d5eda  call    EventingWriteEvent
0x1800d5edf  cmp     [r12+8], r14d
0x1800d5ee4  jz      short loc_1800D5EF1
0x1800d5ee6  lea     rcx, [r12+10h]; lpCriticalSection
0x1800d5eeb  call    cs:__imp_EnterCriticalSection
0x1800d5ef1  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800d5ef5  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800d5efa  test    rsi, rsi
0x1800d5efd  jnz     loc_1800D5FA6
0x1800d5f03  xor     edi, edi
0x1800d5f05  mov     ebx, 80004003h
0x1800d5f0a  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d5f10  mov     [rsp+0D60h+var_CF0], edi
0x1800d5f14  mov     dword ptr [rsp+0D60h+var_CE8], ebx
0x1800d5f18  jz      loc_1800D6D84
0x1800d5f1e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d5f28  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d5f2f  jz      loc_1800D6D84
0x1800d5f35  mov     rax, cs:qword_180169748
0x1800d5f3c  and     rax, rdx
0x1800d5f3f  cmp     cs:qword_180169748, rax
0x1800d5f46  jnz     loc_1800D6D84
0x1800d5f4c  lea     rcx, [rbp+0C60h+var_CC0]; unsigned __int16 *
0x1800d5f50  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d5f55  lea     rcx, [rbp+0C60h+var_CC0]
0x1800d5f59  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d5f5d  inc     rax
0x1800d5f60  cmp     [rcx+rax*2], di
0x1800d5f64  jnz     short loc_1800D5F5D
0x1800d5f66  lea     ecx, [rax+rax]
0x1800d5f69  lea     rax, [rbp+0C60h+var_CC0]
0x1800d5f6d  add     rcx, 2
0x1800d5f71  mov     [rsp+0D60h+var_D00], rcx
0x1800d5f76  lea     r14, qword_180147320
0x1800d5f7d  mov     [rsp+0D60h+var_D08], rax
0x1800d5f82  lea     r9, [rsp+0D60h+var_CE8]
0x1800d5f87  lea     rax, aDatacollectorS_40; "_DataCollector<struct IPerformanceCount"...
0x1800d5f8e  mov     [rsp+0D60h+var_D10], 4Eh ; 'N'
0x1800d5f97  mov     [rsp+0D60h+var_D18], rax
0x1800d5f9c  lea     rax, [rsp+0D60h+var_CF0]
0x1800d5fa1  jmp     loc_1800D6D4B
0x1800d5fa6  mov     rcx, [r12+48h]
0x1800d5fab  test    rcx, rcx
0x1800d5fae  jnz     short loc_1800D6026
0x1800d5fb0  xor     edi, edi
0x1800d5fb2  mov     ebx, 80300002h
0x1800d5fb7  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d5fbd  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800d5fc1  mov     [rsp+0D60h+var_CF0], ebx
0x1800d5fc5  jz      loc_1800D6D84
0x1800d5fcb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d5fd5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d5fdc  jz      loc_1800D6D84
0x1800d5fe2  mov     rax, cs:qword_180169748
0x1800d5fe9  and     rax, rdx
0x1800d5fec  cmp     cs:qword_180169748, rax
0x1800d5ff3  jnz     loc_1800D6D84
0x1800d5ff9  lea     rcx, [rbp+0C60h+var_C40]; unsigned __int16 *
0x1800d5ffd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d6002  lea     rcx, [rbp+0C60h+var_C40]
0x1800d6006  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d600a  inc     rax
0x1800d600d  cmp     [rcx+rax*2], di
0x1800d6011  jnz     short loc_1800D600A
0x1800d6013  lea     ecx, [rax+rax]
0x1800d6016  lea     rax, [rbp+0C60h+var_C40]
0x1800d601a  lea     r14, qword_180147320
0x1800d6021  jmp     loc_1800D6D1E
0x1800d6026  mov     rax, [rcx]
0x1800d6029  lea     rdx, [rbp+0C60h+var_CE0]
0x1800d602d  mov     rax, [rax+0F0h]
0x1800d6034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6039  mov     ebx, eax
0x1800d603b  test    eax, eax
0x1800d603d  jns     short loc_1800D60B2
0x1800d603f  xor     edi, edi
0x1800d6041  mov     [rsp+0D60h+var_CF0], eax
0x1800d6045  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d604b  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800d604f  jz      loc_1800D6D84
0x1800d6055  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d605f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d6066  jz      loc_1800D6D84
0x1800d606c  mov     rax, cs:qword_180169748
0x1800d6073  and     rax, rdx
0x1800d6076  cmp     cs:qword_180169748, rax
0x1800d607d  jnz     loc_1800D6D84
0x1800d6083  lea     rcx, [rbp+0C60h+var_BC0]; unsigned __int16 *
0x1800d608a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d608f  lea     rcx, [rbp+0C60h+var_BC0]
0x1800d6096  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d609a  inc     rax
0x1800d609d  cmp     [rcx+rax*2], di
0x1800d60a1  jnz     short loc_1800D609A
0x1800d60a3  lea     ecx, [rax+rax]
0x1800d60a6  lea     rax, [rbp+0C60h+var_BC0]
0x1800d60ad  jmp     loc_1800D601A
0x1800d60b2  xor     r8d, r8d; int
0x1800d60b5  lea     r14, qword_180147320
0x1800d60bc  mov     r9, r14; char *
0x1800d60bf  mov     ecx, 800h; dwBytes
0x1800d60c4  lea     edx, [r8+1]; int
0x1800d60c8  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800d60cd  xor     ebx, ebx
0x1800d60cf  mov     r13, rax
0x1800d60d2  test    rax, rax
0x1800d60d5  jnz     short loc_1800D6151
0x1800d60d7  xor     edi, edi
0x1800d60d9  mov     ecx, 8007000Eh
0x1800d60de  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d60e4  mov     ebx, ecx
0x1800d60e6  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800d60ea  mov     [rsp+0D60h+var_CF0], ecx
0x1800d60ee  jz      loc_1800D6D84
0x1800d60f4  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d60fe  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d6105  jz      loc_1800D6D84
0x1800d610b  mov     rax, cs:qword_180169748
0x1800d6112  and     rax, rdx
0x1800d6115  cmp     cs:qword_180169748, rax
0x1800d611c  jnz     loc_1800D6D84
0x1800d6122  lea     rcx, [rbp+0C60h+var_B40]; unsigned __int16 *
0x1800d6129  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d612e  lea     rcx, [rbp+0C60h+var_B40]
0x1800d6135  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d6139  inc     rax
0x1800d613c  cmp     [rcx+rax*2], di
0x1800d6140  jnz     short loc_1800D6139
0x1800d6142  lea     ecx, [rax+rax]
0x1800d6145  lea     rax, [rbp+0C60h+var_B40]
0x1800d614c  jmp     loc_1800D6D1E
0x1800d6151  xor     r8d, r8d; int
0x1800d6154  mov     r9, r14; char *
0x1800d6157  mov     ecx, 800h; dwBytes
0x1800d615c  lea     edx, [r8+1]; int
0x1800d6160  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800d6165  mov     r15, rax
0x1800d6168  test    rax, rax
0x1800d616b  jnz     short loc_1800D61E7
0x1800d616d  xor     edi, edi
0x1800d616f  mov     ecx, 8007000Eh
0x1800d6174  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d617a  mov     ebx, ecx
0x1800d617c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800d6180  mov     [rsp+0D60h+var_CF0], ecx
0x1800d6184  jz      loc_1800D6D84
0x1800d618a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d6194  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d619b  jz      loc_1800D6D84
0x1800d61a1  mov     rax, cs:qword_180169748
0x1800d61a8  and     rax, rdx
0x1800d61ab  cmp     cs:qword_180169748, rax
0x1800d61b2  jnz     loc_1800D6D84
0x1800d61b8  lea     rcx, [rbp+0C60h+var_AC0]; unsigned __int16 *
0x1800d61bf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d61c4  lea     rcx, [rbp+0C60h+var_AC0]
0x1800d61cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d61cf  inc     rax
0x1800d61d2  cmp     [rcx+rax*2], di
0x1800d61d6  jnz     short loc_1800D61CF
0x1800d61d8  lea     ecx, [rax+rax]
0x1800d61db  lea     rax, [rbp+0C60h+var_AC0]
0x1800d61e2  jmp     loc_1800D6D1E
0x1800d61e7  lea     rcx, [rbp+0C60h+var_CD8]; struct tagVARIANT *
0x1800d61eb  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800d61f0  mov     rcx, [r12+48h]
0x1800d61f5  lea     rdx, [rbp+0C60h+var_CD8+8]
0x1800d61f9  mov     rax, [rcx]
0x1800d61fc  cmp     bx, di
0x1800d61ff  jz      loc_1800D628E
0x1800d6205  mov     rax, [rax+90h]
0x1800d620c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6211  xor     edi, edi
0x1800d6213  mov     ebx, eax
0x1800d6215  test    eax, eax
0x1800d6217  jns     loc_1800D6313
0x1800d621d  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d6223  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800d6227  mov     [rsp+0D60h+var_CF0], eax
0x1800d622b  jz      loc_1800D6D84
0x1800d6231  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d623b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d6242  jz      loc_1800D6D84
0x1800d6248  mov     rax, cs:qword_180169748
0x1800d624f  and     rax, rdx
0x1800d6252  cmp     cs:qword_180169748, rax
0x1800d6259  jnz     loc_1800D6D84
0x1800d625f  lea     rcx, [rbp+0C60h+var_A40]; unsigned __int16 *
0x1800d6266  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d626b  lea     rcx, [rbp+0C60h+var_A40]
0x1800d6272  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d6276  inc     rax
0x1800d6279  cmp     [rcx+rax*2], di
0x1800d627d  jnz     short loc_1800D6276
0x1800d627f  lea     ecx, [rax+rax]
0x1800d6282  lea     rax, [rbp+0C60h+var_A40]
0x1800d6289  jmp     loc_1800D6D1E
0x1800d628e  mov     rax, [rax+0A8h]
0x1800d6295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d629a  xor     edi, edi
0x1800d629c  mov     ebx, eax
0x1800d629e  test    eax, eax
0x1800d62a0  jns     short loc_1800D6313
0x1800d62a2  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d62a8  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800d62ac  mov     [rsp+0D60h+var_CF0], eax
0x1800d62b0  jz      loc_1800D6D84
0x1800d62b6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d62c0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d62c7  jz      loc_1800D6D84
0x1800d62cd  mov     rax, cs:qword_180169748
0x1800d62d4  and     rax, rdx
0x1800d62d7  cmp     cs:qword_180169748, rax
0x1800d62de  jnz     loc_1800D6D84
0x1800d62e4  lea     rcx, [rbp+0C60h+var_9C0]; unsigned __int16 *
0x1800d62eb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d62f0  lea     rcx, [rbp+0C60h+var_9C0]
0x1800d62f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d62fb  inc     rax
0x1800d62fe  cmp     [rcx+rax*2], di
0x1800d6302  jnz     short loc_1800D62FB
0x1800d6304  lea     ecx, [rax+rax]
0x1800d6307  lea     rax, [rbp+0C60h+var_9C0]
0x1800d630e  jmp     loc_1800D6D1E
0x1800d6313  mov     r8, qword ptr [rbp+0C60h+var_CD8+8]; unsigned __int16 *
0x1800d6317  mov     eax, 8
0x1800d631c  mov     word ptr [rbp+0C60h+var_CD8], ax
0x1800d6320  test    r8, r8
0x1800d6323  jz      loc_1800D6CAD
0x1800d6329  cmp     di, [r8]
0x1800d632d  jz      loc_1800D6CAD
0x1800d6333  mov     edx, 400h; unsigned __int64
0x1800d6338  mov     rcx, r15; unsigned __int16 *
0x1800d633b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d6340  mov     ebx, eax
0x1800d6342  test    eax, eax
0x1800d6344  jns     short loc_1800D63B7
0x1800d6346  cmp     dword ptr cs:xmmword_180169738, edi
0x1800d634c  mov     dword ptr [rsp+0D60h+var_CE8], edi
0x1800d6350  mov     [rsp+0D60h+var_CF0], eax
0x1800d6354  jz      loc_1800D6D84
0x1800d635a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d6364  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d636b  jz      loc_1800D6D84
0x1800d6371  mov     rax, cs:qword_180169748
0x1800d6378  and     rax, rdx
0x1800d637b  cmp     cs:qword_180169748, rax
0x1800d6382  jnz     loc_1800D6D84
0x1800d6388  lea     rcx, [rbp+0C60h+var_940]; unsigned __int16 *
0x1800d638f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d6394  lea     rcx, [rbp+0C60h+var_940]
0x1800d639b  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
